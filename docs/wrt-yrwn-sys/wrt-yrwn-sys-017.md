# 017：动态内存管理 / 堆 🧠

在本教程中，我们将学习如何实现动态内存管理，即堆。目前，我们所有的内存分配都是静态的，例如在栈上分配对象。然而，有时我们无法预先知道需要多少内存，例如在遍历PCI设备并找到需要驱动程序的设备时。因此，我们需要一种方法来动态分配内存，并跟踪已分配和未分配的内存区域，以防止它们相互重叠和干扰。

## 内存布局与设计思路

上一节我们介绍了静态内存分配的局限性，本节中我们来看看如何设计一个简单的堆管理器。

我们的内存布局大致如下：我们有视频内存、文本内存、BIOS、引导加载程序、内核及其栈。之后，有大量可用的空闲空间供我们使用。我们将从栈指针之后的一个固定偏移量（例如10MB）开始，将这片区域作为我们的堆。

虽然这种方法不够优雅（理想情况下，引导程序应告知我们可用内存区域），但它是目前一个可行的起点。

## 核心数据结构：内存块

我们的堆管理器将基于双向链表实现。以下是核心数据结构：

**`MemoryChunk` 结构体**：
```cpp
struct MemoryChunk {
    MemoryChunk* next;
    MemoryChunk* prev;
    bool allocated;
    size_t size; // 此块之后可供用户使用的数据区域大小
};
```
**`size_t` 类型定义**：
```cpp
typedef uint32_t size_t; // 在32位系统上
```

每个 `MemoryChunk` 结构体（或称“头”）位于其管理的内存块起始处。`size` 字段表示紧随头之后、可供用户程序使用的内存字节数。

**`MemoryManager` 类**：
```cpp
class MemoryManager {
public:
    MemoryManager(size_t start, size_t size);
    void* malloc(size_t size);
    void free(void* ptr);

    static MemoryManager* activeMemoryManager;
private:
    MemoryChunk* firstChunk;
};
```

管理器负责初始化第一个内存块，并处理分配 (`malloc`) 和释放 (`free`) 请求。

## 初始化堆管理器

在构造函数中，我们进行初始化：
1.  将 `activeMemoryManager` 设置为当前实例。
2.  在给定的起始地址 (`start`) 处创建第一个 `MemoryChunk`。
3.  这个初始块标记为未分配 (`allocated = false`)，其 `size` 为整个堆区域的大小减去头本身的大小。它的 `next` 和 `prev` 指针都设为 `nullptr`。

![](img/78de33d16cf722ce44753100b4fc2326_1.png)

![](img/78de33d16cf722ce44753100b4fc2326_2.png)

![](img/78de33d16cf722ce44753100b4fc2326_3.png)

```cpp
MemoryManager::MemoryManager(size_t start, size_t size) {
    activeMemoryManager = this;
    // 确保有足够空间容纳至少一个 MemoryChunk
    if(size < sizeof(MemoryChunk)) {
        firstChunk = nullptr;
        return;
    }
    firstChunk = (MemoryChunk*)start;
    firstChunk->allocated = false;
    firstChunk->prev = nullptr;
    firstChunk->next = nullptr;
    firstChunk->size = size - sizeof(MemoryChunk);
}
```

## 内存分配算法

当请求分配内存时，`malloc` 函数会遍历链表，寻找第一个足够大且未被分配的块。

![](img/78de33d16cf722ce44753100b4fc2326_5.png)

以下是分配过程的关键步骤：

1.  **遍历查找**：从 `firstChunk` 开始，遍历链表，寻找 `allocated == false` 且 `size >= 请求大小` 的块。
2.  **决定分割**：如果找到的块远大于请求大小（即 `块size >= 请求size + sizeof(MemoryChunk) + 1`），我们分割该块。
    *   原块被分割为两部分：一个已分配块（满足请求）和一个新的未分配块（剩余空间）。
    *   需要调整新旧块的指针和大小字段。
3.  **直接分配**：如果找到的块大小不足以进行分割，则直接将整个块标记为已分配。
4.  **返回指针**：返回给用户的是内存块头之后的数据区域起始地址，即 `(void*)((size_t)chunk + sizeof(MemoryChunk))`。

![](img/78de33d16cf722ce44753100b4fc2326_7.png)

![](img/78de33d16cf722ce44753100b4fc2326_9.png)

![](img/78de33d16cf722ce44753100b4fc2326_11.png)

```cpp
void* MemoryManager::malloc(size_t size) {
    MemoryChunk* result = nullptr;
    // 遍历链表寻找合适的空闲块
    for(MemoryChunk* chunk = firstChunk; chunk != nullptr; chunk = chunk->next) {
        if(!chunk->allocated && chunk->size >= size) {
            result = chunk;
            break;
        }
    }
    if(result == nullptr) return nullptr; // 内存不足

    // 检查是否需要并可以分割块
    if(result->size >= size + sizeof(MemoryChunk) + 1) {
        // 创建新块（剩余空间）
        MemoryChunk* newChunk = (MemoryChunk*)((size_t)result + sizeof(MemoryChunk) + size);
        newChunk->allocated = false;
        newChunk->size = result->size - size - sizeof(MemoryChunk);
        newChunk->prev = result;
        newChunk->next = result->next;

        // 更新原块（分配块）
        result->size = size; // 分配块只管理请求大小的数据区
        result->next = newChunk;
        if(newChunk->next != nullptr) {
            newChunk->next->prev = newChunk;
        }
    }
    result->allocated = true;
    // 返回数据区指针（头之后）
    return (void*)((size_t)result + sizeof(MemoryChunk));
}
```

![](img/78de33d16cf722ce44753100b4fc2326_13.png)

## 内存释放与块合并

![](img/78de33d16cf722ce44753100b4fc2326_15.png)

![](img/78de33d16cf722ce44753100b4fc2326_17.png)

释放内存 (`free`) 时，我们不仅要将块标记为未分配，还要尝试与相邻的未分配块合并，以防止内存碎片化。

![](img/78de33d16cf722ce44753100b4fc2326_19.png)

![](img/78de33d16cf722ce44753100b4fc2326_21.png)

以下是释放与合并的过程：

![](img/78de33d16cf722ce44753100b4fc2326_23.png)

1.  **获取块头**：用户传入的是数据区指针，我们需要减去 `sizeof(MemoryChunk)` 来找到对应的 `MemoryChunk` 头。
2.  **与前一块合并**：如果当前块的前一块存在且未分配，则将当前块合并到前一块。
    *   将前一块的 `size` 增加（当前块 `size + sizeof(MemoryChunk)`）。
    *   调整链表指针，绕过当前块。
    *   将当前块指针指向前一块，以便后续操作。
3.  **与后一块合并**：如果（合并后的）当前块的下一块存在且未分配，则将其合并到当前块。
    *   将当前块的 `size` 增加（下一块 `size + sizeof(MemoryChunk)`）。
    *   调整链表指针，移除下一块。

```cpp
void MemoryManager::free(void* ptr) {
    if(ptr == nullptr) return;
    // 通过数据指针找到块头
    MemoryChunk* chunk = (MemoryChunk*)((size_t)ptr - sizeof(MemoryChunk));
    chunk->allocated = false;

    // 与前一个空闲块合并
    if(chunk->prev != nullptr && !chunk->prev->allocated) {
        chunk->prev->size += chunk->size + sizeof(MemoryChunk);
        chunk->prev->next = chunk->next;
        if(chunk->next != nullptr) {
            chunk->next->prev = chunk->prev;
        }
        chunk = chunk->prev; // 将指针移到合并后的块
    }

    // 与后一个空闲块合并
    if(chunk->next != nullptr && !chunk->next->allocated) {
        chunk->size += chunk->next->size + sizeof(MemoryChunk);
        chunk->next = chunk->next->next;
        if(chunk->next != nullptr) {
            chunk->next->prev = chunk;
        }
    }
}
```

![](img/78de33d16cf722ce44753100b4fc2326_25.png)

## 集成到C++的new/delete运算符

![](img/78de33d16cf722ce44753100b4fc2326_27.png)

为了让动态内存分配更符合C++习惯，我们可以重载全局的 `new` 和 `delete` 运算符，让它们调用我们的堆管理器。

**注意**：标准的 `new` 在分配失败时应抛出 `std::bad_alloc` 异常。由于我们尚未实现异常处理，这里简化为返回 `nullptr`。在内核模式下，对 `nullptr` 的解引用是允许的（访问地址0），这很危险。因此，更安全的做法是使用“placement new”在预先分配好的内存上构造对象。

以下是运算符重载的示例：

```cpp
// 全局 new/delete 运算符，调用我们的内存管理器
void* operator new(size_t size) {
    if(MemoryManager::activeMemoryManager == nullptr) return nullptr;
    return MemoryManager::activeMemoryManager->malloc(size);
}
void operator delete(void* ptr) {
    if(MemoryManager::activeMemoryManager != nullptr) {
        MemoryManager::activeMemoryManager->free(ptr);
    }
}

![](img/78de33d16cf722ce44753100b4fc2326_29.png)

![](img/78de33d16cf722ce44753100b4fc2326_30.png)

![](img/78de33d16cf722ce44753100b4fc2326_31.png)

![](img/78de33d16cf722ce44753100b4fc2326_32.png)

![](img/78de33d16cf722ce44753100b4fc2326_34.png)

![](img/78de33d16cf722ce44753100b4fc2326_35.png)

![](img/78de33d16cf722ce44753100b4fc2326_36.png)

![](img/78de33d16cf722ce44753100b4fc2326_38.png)

// Placement new 运算符，用于在指定内存地址构造对象
void* operator new(size_t, void* ptr) {
    return ptr;
}
void operator delete(void*, void*) { /* placement delete 通常为空 */ }
```

![](img/78de33d16cf722ce44753100b4fc2326_40.png)

在实际使用时，可以先调用 `malloc` 分配原始内存，检查指针非空后，再用 `placement new` 构造对象：

![](img/78de33d16cf722ce44753100b4fc2326_42.png)

```cpp
// 示例：动态创建驱动程序对象
AmdPcNetDriver* driver = (AmdPcNetDriver*)MemoryManager::activeMemoryManager->malloc(sizeof(AmdPcNetDriver));
if(driver != nullptr) {
    driver = new(driver) AmdPcNetDriver(...); // 使用 placement new 调用构造函数
}
```

![](img/78de33d16cf722ce44753100b4fc2326_44.png)

## 堆的初始化与地址

![](img/78de33d16cf722ce44753100b4fc2326_46.png)

![](img/78de33d16cf722ce44753100b4fc2326_48.png)

在实例化 `MemoryManager` 时，我们需要确定堆的起始地址和大小。一个简单但不够优雅的方法是将起始地址硬编码为内核栈之后的一个固定值（例如10MB）。大小可以从GRUB传递的多引导信息结构中获取（内存大小以KB为单位），然后减去堆的起始地址和一部分预留空间。

```cpp
// 示例：从 multiboot 信息获取内存大小（KB），并转换为字节
size_t memorySizeKB = *((uint32_t*)((size_t)multibootStructPtr + 8));
size_t heapSize = (memorySizeKB * 1024) - heapStartAddress - 10*1024; // 减去10KB预留

![](img/78de33d16cf722ce44753100b4fc2326_50.png)

MemoryManager memoryManager(heapStartAddress, heapSize);
```

![](img/78de33d16cf722ce44753100b4fc2326_52.png)

## 总结与展望

![](img/78de33d16cf722ce44753100b4fc2326_54.png)

![](img/78de33d16cf722ce44753100b4fc2326_56.png)

![](img/78de33d16cf722ce44753100b4fc2326_58.png)

本节课中我们一起学习了如何实现一个简单的动态内存管理器（堆）。我们基于双向链表设计了一个内存块结构来跟踪内存的使用情况，实现了 `malloc` 和 `free` 的基本功能，包括内存分割与合并以减少碎片。最后，我们将其与C++的 `new`/`delete` 运算符进行了集成，并讨论了安全分配对象的注意事项。

这个实现虽然简单且效率不高（例如分配需要线性遍历链表），但它是一个重要的起点，为操作系统提供了动态内存分配的能力。有了堆，我们就可以在运行时创建对象，例如接下来为检测到的PCI设备动态实例化驱动程序。

![](img/78de33d16cf722ce44753100b4fc2326_60.png)

![](img/78de33d16cf722ce44753100b4fc2326_62.png)

在后续章节中，我们将利用这个堆管理器来支持网络驱动程序的加载，并开始探索网络通信功能。更高级的改进可以包括引入虚拟内存和分页机制，以更高效、安全地管理内存。
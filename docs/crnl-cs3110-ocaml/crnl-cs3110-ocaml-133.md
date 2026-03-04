# 133：哈希表扩容实现 🛠️

在本节课中，我们将学习如何为哈希表实现动态扩容功能。我们将重点关注如何计算负载因子，以及如何根据负载因子的大小来调整哈希表的容量，确保其操作效率。

上一节我们介绍了哈希表的基本插入操作，本节中我们来看看如何实现自动扩容，以维持哈希表的性能。

## 负载因子计算

首先，我们需要计算哈希表的负载因子。负载因子是衡量哈希表“满”的程度的关键指标，其计算公式为：

**负载因子 = 表中元素数量 / 桶数组容量**

在我们的实现中，我们选择将负载因子维持在 **0.5** 到 **2** 之间。当负载因子超出这个范围时，无论是过大还是过小，我们都会触发扩容操作。

以下是计算负载因子的辅助函数实现：

```ocaml
let load_factor tab =
  let size_float = float_of_int tab.size in
  let capacity_float = float_of_int (Array.length tab.buckets) in
  size_float /. capacity_float
```

这个函数将整数类型的元素数量和容量转换为浮点数，然后进行除法运算，得到一个浮点数结果作为负载因子。

## 触发扩容判断

有了负载因子后，我们可以在插入操作中判断是否需要扩容。以下是 `resize_if_needed` 函数的逻辑框架：

```ocaml
let resize_if_needed tab =
  let lf = load_factor tab in
  if lf > 2.0 then
    rehash tab (tab.capacity * 2)  (* 负载因子过高，容量翻倍 *)
  else if lf < 0.5 then
    rehash tab (tab.capacity / 2)  (* 负载因子过低，容量减半 *)
  else
    ()  (* 负载因子正常，无需操作 *)
```

这个函数检查当前负载因子，并根据其值决定是扩容（翻倍）还是缩容（减半）。

## 核心：重哈希（Rehash）操作

当决定调整容量后，核心工作是 `rehash` 函数。它的作用是：用一个新的、指定容量的桶数组替换旧的桶数组，并将原哈希表中的所有键值对重新插入到新数组中。

以下是 `rehash` 函数的规格说明和实现步骤：

```ocaml
(* 规格说明：
   将 tab 的桶数组替换为一个大小为 new_capacity 的新数组，
   并将 tab 中的所有绑定重新插入到这个新数组中。
*)
let rehash tab new_capacity =
  let old_buckets = tab.buckets in          (* 保存旧数组 *)
  tab.buckets <- Array.make new_capacity []; (* 创建新的空数组 *)
  tab.size <- 0;                             (* 重置大小计数器 *)

  (* 遍历旧数组中的所有桶 *)
  Array.iter (fun bucket ->
    rehash_bucket tab bucket                (* 重新哈希每个桶 *)
  ) old_buckets
```

在重新插入时，每个键都会被重新计算哈希值（即 `hash key mod new_capacity`），因此它很可能会被放入与之前不同的新桶中。

## 辅助函数：重哈希桶与绑定

`rehash` 函数依赖于两个辅助函数来完成具体工作。

以下是 `rehash_bucket` 函数，它负责处理一个桶内的所有元素：

```ocaml
let rehash_bucket tab bucket =
  List.iter (fun (k, v) ->
    rehash_binding tab k v                  (* 重新哈希桶内的每个绑定 *)
  ) bucket
```

而 `rehash_binding` 函数则负责处理单个键值对：

```ocaml
let rehash_binding tab key value =
  insert_no_resize tab key value            (* 使用已有的无扩容插入函数 *)
```

这里巧妙地复用了之前编写的 `insert_no_resize` 函数。因为它不包含扩容逻辑，所以不会在重哈希过程中引发递归扩容。同时，`insert_no_resize` 会负责递增 `tab.size` 字段，我们无需在 `rehash` 函数中手动管理。

## 效率分析

最后，我们来分析一下 `rehash` 操作的效率。

1.  **创建新数组**：`Array.make new_capacity []` 的时间复杂度为 **O(N)**，其中 N 是新的容量。在扩容时，我们的目标是将容量调整到与当前元素数量 `n` 相当，因此这部分是 **O(n)**。
2.  **重新插入所有元素**：`rehash_binding` 会对表中每一个元素（共 `n` 个）调用一次 `insert_no_resize`。
3.  **单次插入成本**：`insert_no_resize` 的期望时间复杂度是 **O(L)**，即常数时间。

因此，整个 `rehash` 操作的总期望时间复杂度是：

**O(n) * O(1) = O(n)**

其中 `n` 是哈希表中元素的数量。这是一个线性的时间复杂度。

---

本节课中我们一起学习了哈希表动态扩容的完整实现。我们掌握了如何通过负载因子判断扩容时机，并实现了将表中所有元素重新哈希到新数组的核心 `rehash` 函数。通过将扩容逻辑与插入逻辑分离，并复用基础插入函数，我们构建了一个高效且清晰的实现。至此，我们完成了哈希表 `insert` 操作的所有关键部分。
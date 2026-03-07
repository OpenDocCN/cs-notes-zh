# 011：音频系统与混音器 🎵

![](img/7a07006fd44b8dede9f835fb4c96181a_1.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_3.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_5.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_7.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_9.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_11.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_13.png)

在本节课中，我们将为游戏添加音频系统。我们将学习如何使用DirectSound库播放声音，实现一个简单的混音器来同时播放多个音频文件，并支持音量、声像和音高调节等基本功能。

![](img/7a07006fd44b8dede9f835fb4c96181a_15.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_17.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_19.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_21.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_23.png)

---

![](img/7a07006fd44b8dede9f835fb4c96181a_25.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_27.png)

## 概述

![](img/7a07006fd44b8dede9f835fb4c96181a_29.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_31.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_33.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_35.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_37.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_39.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_41.png)

到目前为止，我们的游戏已经有了图形渲染、粒子系统等，但缺少了声音。本节课的目标是构建一个基础的音频系统。我们将从播放单个声音开始，逐步实现播放多个声音、声像调节和音高变化等功能。

![](img/7a07006fd44b8dede9f835fb4c96181a_43.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_45.png)

---

![](img/7a07006fd44b8dede9f835fb4c96181a_47.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_49.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_51.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_53.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_55.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_57.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_59.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_61.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_63.png)

## 初始化音频系统

![](img/7a07006fd44b8dede9f835fb4c96181a_65.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_67.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_69.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_71.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_73.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_75.png)

首先，我们需要初始化DirectSound库并创建音频缓冲区。DirectSound是Windows平台上的一个音频API，我们将使用它来播放声音。

![](img/7a07006fd44b8dede9f835fb4c96181a_77.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_79.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_81.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_83.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_85.png)

### 加载DirectSound库

![](img/7a07006fd44b8dede9f835fb4c96181a_87.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_89.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_91.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_93.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_95.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_97.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_99.png)

由于DirectSound库是动态链接库（DLL），我们需要在运行时加载它。

![](img/7a07006fd44b8dede9f835fb4c96181a_101.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_103.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_105.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_107.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_109.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_111.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_113.png)

```c
HMODULE DSoundDLL = LoadLibraryA("dsound.dll");
if (!DSoundDLL) {
    // 处理加载失败的情况
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_115.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_117.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_119.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_121.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_123.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_125.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_127.png)

### 获取DirectSound创建函数

![](img/7a07006fd44b8dede9f835fb4c96181a_129.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_131.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_133.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_135.png)

加载库后，我们需要获取`DirectSoundCreate`函数的地址。

![](img/7a07006fd44b8dede9f835fb4c96181a_137.png)

```c
typedef HRESULT WINAPI direct_sound_create(LPGUID, LPDIRECTSOUND*, LPUNKNOWN);
direct_sound_create* DirectSoundCreate = (direct_sound_create*)GetProcAddress(DSoundDLL, "DirectSoundCreate");
if (!DirectSoundCreate) {
    // 处理获取函数失败的情况
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_139.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_141.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_143.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_145.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_147.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_149.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_151.png)

### 创建DirectSound对象

![](img/7a07006fd44b8dede9f835fb4c96181a_153.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_155.png)

使用获取到的函数创建DirectSound对象。

![](img/7a07006fd44b8dede9f835fb4c96181a_157.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_159.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_160.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_162.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_164.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_166.png)

```c
LPDIRECTSOUND DirectSound;
if (SUCCEEDED(DirectSoundCreate(0, &DirectSound, 0))) {
    // 创建成功
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_168.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_170.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_172.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_174.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_175.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_177.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_179.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_181.png)

### 设置协作级别

![](img/7a07006fd44b8dede9f835fb4c96181a_183.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_185.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_186.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_188.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_190.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_192.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_193.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_195.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_197.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_199.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_201.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_203.png)

创建DirectSound对象后，需要设置协作级别，以便应用程序能够访问音频设备。

![](img/7a07006fd44b8dede9f835fb4c96181a_205.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_207.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_209.png)

```c
DirectSound->lpVtbl->SetCooperativeLevel(DirectSound, Window, DSSCL_PRIORITY);
```

---

![](img/7a07006fd44b8dede9f835fb4c96181a_211.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_213.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_215.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_217.png)

## 创建音频缓冲区

音频播放需要一个缓冲区来存储音频数据。我们将创建一个主缓冲区和一个副缓冲区。副缓冲区是我们实际写入音频数据的地方。

![](img/7a07006fd44b8dede9f835fb4c96181a_219.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_221.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_223.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_225.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_227.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_229.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_231.png)

### 创建主缓冲区

![](img/7a07006fd44b8dede9f835fb4c96181a_233.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_235.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_237.png)

首先，我们创建一个主缓冲区，但不会直接使用它。

![](img/7a07006fd44b8dede9f835fb4c96181a_239.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_241.png)

```c
DSBUFFERDESC BufferDescription = {0};
BufferDescription.dwSize = sizeof(BufferDescription);
BufferDescription.dwFlags = DSBCAPS_PRIMARYBUFFER;

![](img/7a07006fd44b8dede9f835fb4c96181a_243.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_245.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_247.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_249.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_251.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_253.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_255.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_257.png)

LPDIRECTSOUNDBUFFER PrimaryBuffer;
if (SUCCEEDED(DirectSound->lpVtbl->CreateSoundBuffer(DirectSound, &BufferDescription, &PrimaryBuffer, 0))) {
    // 主缓冲区创建成功
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_259.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_261.png)

### 创建副缓冲区

![](img/7a07006fd44b8dede9f835fb4c96181a_263.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_265.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_267.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_269.png)

接下来，我们创建副缓冲区，并设置音频格式（如采样率、声道数等）。

![](img/7a07006fd44b8dede9f835fb4c96181a_271.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_273.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_275.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_277.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_279.png)

```c
WAVEFORMATEX WaveFormat = {0};
WaveFormat.wFormatTag = WAVE_FORMAT_PCM;
WaveFormat.nChannels = 2; // 立体声
WaveFormat.nSamplesPerSec = 44100; // 44.1kHz采样率
WaveFormat.wBitsPerSample = 16; // 16位采样
WaveFormat.nBlockAlign = (WaveFormat.nChannels * WaveFormat.wBitsPerSample) / 8;
WaveFormat.nAvgBytesPerSec = WaveFormat.nSamplesPerSec * WaveFormat.nBlockAlign;

![](img/7a07006fd44b8dede9f835fb4c96181a_281.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_283.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_285.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_287.png)

BufferDescription.dwFlags = DSBCAPS_GLOBALFOCUS;
BufferDescription.dwBufferBytes = WaveFormat.nAvgBytesPerSec; // 1秒的缓冲区大小
BufferDescription.lpwfxFormat = &WaveFormat;

![](img/7a07006fd44b8dede9f835fb4c96181a_289.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_291.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_293.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_295.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_297.png)

LPDIRECTSOUNDBUFFER SecondaryBuffer;
if (SUCCEEDED(DirectSound->lpVtbl->CreateSoundBuffer(DirectSound, &BufferDescription, &SecondaryBuffer, 0))) {
    // 副缓冲区创建成功
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_299.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_301.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_303.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_305.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_307.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_309.png)

---

![](img/7a07006fd44b8dede9f835fb4c96181a_311.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_313.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_315.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_317.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_319.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_321.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_323.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_325.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_327.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_329.png)

## 播放音频

![](img/7a07006fd44b8dede9f835fb4c96181a_331.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_333.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_335.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_337.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_339.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_341.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_343.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_345.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_347.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_349.png)

创建缓冲区后，我们需要向缓冲区写入音频数据并开始播放。

![](img/7a07006fd44b8dede9f835fb4c96181a_351.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_353.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_355.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_357.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_359.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_360.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_362.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_364.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_366.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_368.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_370.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_372.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_374.png)

### 写入音频数据

![](img/7a07006fd44b8dede9f835fb4c96181a_376.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_378.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_380.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_382.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_384.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_386.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_388.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_390.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_392.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_394.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_396.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_398.png)

使用`Lock`函数锁定缓冲区，然后写入音频数据。

![](img/7a07006fd44b8dede9f835fb4c96181a_400.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_401.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_403.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_404.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_406.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_408.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_410.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_412.png)

```c
void FillSoundBuffer(DWORD ByteToLock, DWORD BytesToWrite) {
    VOID* Region1;
    DWORD Region1Size;
    VOID* Region2;
    DWORD Region2Size;

    if (SUCCEEDED(SecondaryBuffer->lpVtbl->Lock(SecondaryBuffer, ByteToLock, BytesToWrite, &Region1, &Region1Size, &Region2, &Region2Size, 0))) {
        // 写入Region1和Region2的音频数据
        // ...

        // 解锁缓冲区
        SecondaryBuffer->lpVtbl->Unlock(SecondaryBuffer, Region1, Region1Size, Region2, Region2Size);
    }
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_414.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_416.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_418.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_420.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_422.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_424.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_426.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_428.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_429.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_431.png)

### 开始播放

写入数据后，调用`Play`函数开始播放音频。

```c
SecondaryBuffer->lpVtbl->Play(SecondaryBuffer, 0, 0, DSBPLAY_LOOPING);
```

![](img/7a07006fd44b8dede9f835fb4c96181a_433.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_435.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_437.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_439.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_441.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_443.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_445.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_447.png)

---

![](img/7a07006fd44b8dede9f835fb4c96181a_449.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_451.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_453.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_455.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_457.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_459.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_461.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_463.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_465.png)

## 实现混音器

![](img/7a07006fd44b8dede9f835fb4c96181a_467.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_469.png)

上一节我们介绍了如何播放单个音频文件。本节中，我们来看看如何实现一个简单的混音器，以支持同时播放多个声音。

![](img/7a07006fd44b8dede9f835fb4c96181a_471.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_473.png)

### 定义音频结构

![](img/7a07006fd44b8dede9f835fb4c96181a_475.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_477.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_479.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_481.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_483.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_485.png)

首先，我们定义两个结构：`loaded_sound`表示加载的音频文件，`playing_sound`表示正在播放的声音实例。

![](img/7a07006fd44b8dede9f835fb4c96181a_487.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_489.png)

```c
typedef struct {
    S16* Samples;
    DWORD SampleCount;
    DWORD ChannelCount;
} loaded_sound;

![](img/7a07006fd44b8dede9f835fb4c96181a_491.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_493.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_495.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_497.png)

typedef struct {
    loaded_sound* Sound;
    F32 Position;
    F32 Volume;
    F32 Pan;
    F32 SpeedMultiplier;
    bool Looping;
    bool Active;
} playing_sound;
```

### 播放声音

![](img/7a07006fd44b8dede9f835fb4c96181a_499.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_501.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_503.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_505.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_507.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_509.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_510.png)

我们维护一个`playing_sound`数组来管理所有正在播放的声音。当需要播放新声音时，将其添加到数组中。

![](img/7a07006fd44b8dede9f835fb4c96181a_512.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_513.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_515.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_517.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_519.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_521.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_523.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_525.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_527.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_529.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_531.png)

```c
playing_sound PlayingSounds[32];
DWORD NextPlayingSound = 0;

![](img/7a07006fd44b8dede9f835fb4c96181a_533.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_535.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_537.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_539.png)

playing_sound* PlaySound(loaded_sound* Sound, bool Looping) {
    playing_sound* Result = &PlayingSounds[NextPlayingSound];
    NextPlayingSound = (NextPlayingSound + 1) % ArrayCount(PlayingSounds);

    Result->Sound = Sound;
    Result->Position = 0;
    Result->Volume = 1.0f;
    Result->Pan = 0.0f;
    Result->SpeedMultiplier = 1.0f;
    Result->Looping = Looping;
    Result->Active = true;

    return Result;
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_541.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_542.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_544.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_546.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_548.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_550.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_551.png)

### 混音处理

![](img/7a07006fd44b8dede9f835fb4c96181a_553.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_555.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_557.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_558.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_560.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_561.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_563.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_565.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_567.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_568.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_570.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_572.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_574.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_576.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_578.png)

在每一帧中，我们遍历所有正在播放的声音，将它们混合到音频缓冲区中。

![](img/7a07006fd44b8dede9f835fb4c96181a_580.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_582.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_583.png)

```c
void MixSounds(S16* Samples, DWORD SampleCount) {
    for (DWORD SampleIndex = 0; SampleIndex < SampleCount; SampleIndex++) {
        F32 LeftSample = 0;
        F32 RightSample = 0;

        for (DWORD SoundIndex = 0; SoundIndex < ArrayCount(PlayingSounds); SoundIndex++) {
            playing_sound* Sound = &PlayingSounds[SoundIndex];
            if (Sound->Active) {
                // 计算左右声道的音量比例
                F32 LeftVolume = Sound->Volume * (1.0f - Sound->Pan);
                F32 RightVolume = Sound->Volume * (1.0f + Sound->Pan);

                // 获取音频样本
                DWORD SamplePosition = (DWORD)(Sound->Position * Sound->Sound->ChannelCount);
                S16 SourceSample = Sound->Sound->Samples[SamplePosition];

                // 混合到左右声道
                LeftSample += SourceSample * LeftVolume;
                RightSample += SourceSample * RightVolume;

                // 更新播放位置
                Sound->Position += Sound->SpeedMultiplier;
                if (Sound->Position * Sound->Sound->ChannelCount >= Sound->Sound->SampleCount) {
                    if (Sound->Looping) {
                        Sound->Position = 0;
                    } else {
                        Sound->Active = false;
                    }
                }
            }
        }

        // 将混合后的样本写入缓冲区
        Samples[SampleIndex * 2] = (S16)LeftSample;
        Samples[SampleIndex * 2 + 1] = (S16)RightSample;
    }
}
```

![](img/7a07006fd44b8dede9f835fb4c96181a_585.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_587.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_589.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_591.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_593.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_595.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_597.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_599.png)

---

![](img/7a07006fd44b8dede9f835fb4c96181a_601.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_603.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_605.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_607.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_609.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_611.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_613.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_615.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_617.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_619.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_621.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_623.png)

## 高级功能

![](img/7a07006fd44b8dede9f835fb4c96181a_625.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_627.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_629.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_630.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_632.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_634.png)

上一节我们实现了基础的混音器。本节中，我们来看看如何添加声像调节和音高变化等高级功能。

![](img/7a07006fd44b8dede9f835fb4c96181a_636.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_637.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_639.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_641.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_643.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_645.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_647.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_649.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_651.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_653.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_654.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_656.png)

### 声像调节

![](img/7a07006fd44b8dede9f835fb4c96181a_658.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_660.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_662.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_664.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_666.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_668.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_669.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_670.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_672.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_674.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_676.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_678.png)

声像调节通过调整左右声道的音量比例来实现。我们使用一个范围在-1到1之间的值表示声像位置，其中-1表示完全左声道，1表示完全右声道。

![](img/7a07006fd44b8dede9f835fb4c96181a_680.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_682.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_684.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_686.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_687.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_689.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_691.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_693.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_694.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_695.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_697.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_699.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_700.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_702.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_703.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_705.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_707.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_709.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_711.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_713.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_715.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_717.png)

```c
F32 LeftVolume = Sound->Volume * (1.0f - Sound->Pan);
F32 RightVolume = Sound->Volume * (1.0f + Sound->Pan);
```

![](img/7a07006fd44b8dede9f835fb4c96181a_719.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_721.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_722.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_724.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_726.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_728.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_730.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_732.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_734.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_736.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_738.png)

### 音高变化

![](img/7a07006fd44b8dede9f835fb4c96181a_740.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_741.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_743.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_744.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_745.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_747.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_748.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_750.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_752.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_754.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_756.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_757.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_759.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_760.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_761.png)

音高变化通过调整播放速度来实现。加快播放速度会提高音高，减慢播放速度会降低音高。

![](img/7a07006fd44b8dede9f835fb4c96181a_763.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_764.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_765.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_766.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_767.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_769.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_770.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_772.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_774.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_776.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_777.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_778.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_780.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_782.png)

```c
Sound->Position += Sound->SpeedMultiplier;
```

![](img/7a07006fd44b8dede9f835fb4c96181a_784.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_786.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_788.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_790.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_792.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_793.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_795.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_797.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_799.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_801.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_803.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_804.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_806.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_807.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_809.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_811.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_812.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_813.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_814.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_815.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_817.png)

---

![](img/7a07006fd44b8dede9f835fb4c96181a_818.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_819.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_820.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_822.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_824.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_826.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_828.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_830.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_832.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_834.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_836.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_837.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_839.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_840.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_842.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_844.png)

## 总结

![](img/7a07006fd44b8dede9f835fb4c96181a_846.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_848.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_850.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_852.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_854.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_856.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_858.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_860.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_862.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_864.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_866.png)

本节课中，我们一起学习了如何为游戏构建一个基础的音频系统。我们从初始化DirectSound库开始，逐步实现了音频缓冲区的创建、音频数据的写入和播放。接着，我们实现了一个简单的混音器，支持同时播放多个声音，并添加了声像调节和音高变化等高级功能。

![](img/7a07006fd44b8dede9f835fb4c96181a_867.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_869.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_870.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_871.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_873.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_875.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_876.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_877.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_878.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_880.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_881.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_883.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_885.png)

通过本节课的学习，你现在应该能够：
1. 使用DirectSound库播放音频。
2. 实现一个支持多声音混合的混音器。
3. 调节声音的声像和音高。

![](img/7a07006fd44b8dede9f835fb4c96181a_887.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_888.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_889.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_891.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_893.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_895.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_897.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_899.png)

在下一节课中，我们将进一步优化音频系统，例如通过多线程处理音频数据，以减少延迟并提高性能。
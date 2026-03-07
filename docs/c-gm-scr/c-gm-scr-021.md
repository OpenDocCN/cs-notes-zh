# 021：资源系统与异步OGG加载 🎮

![](img/25984fe835474479d1617bc0acadfcd6_1.png)

![](img/25984fe835474479d1617bc0acadfcd6_2.png)

![](img/25984fe835474479d1617bc0acadfcd6_4.png)

![](img/25984fe835474479d1617bc0acadfcd6_6.png)

![](img/25984fe835474479d1617bc0acadfcd6_8.png)

![](img/25984fe835474479d1617bc0acadfcd6_10.png)

![](img/25984fe835474479d1617bc0acadfcd6_12.png)

在本节课中，我们将学习如何为游戏构建一个更健壮的资源系统。主要内容包括实现异步OGG音频加载以减小游戏体积，以及创建一个资源打包器，将所有游戏资源整合到一个文件中，以提高加载效率和项目组织性。

![](img/25984fe835474479d1617bc0acadfcd6_14.png)

![](img/25984fe835474479d1617bc0acadfcd6_16.png)

![](img/25984fe835474479d1617bc0acadfcd6_18.png)

![](img/25984fe835474479d1617bc0acadfcd6_20.png)

![](img/25984fe835474479d1617bc0acadfcd6_21.png)

![](img/25984fe835474479d1617bc0acadfcd6_23.png)

![](img/25984fe835474479d1617bc0acadfcd6_25.png)

![](img/25984fe835474479d1617bc0acadfcd6_27.png)

![](img/25984fe835474479d1617bc0acadfcd6_29.png)

![](img/25984fe835474479d1617bc0acadfcd6_31.png)

![](img/25984fe835474479d1617bc0acadfcd6_33.png)

---

![](img/25984fe835474479d1617bc0acadfcd6_35.png)

![](img/25984fe835474479d1617bc0acadfcd6_37.png)

![](img/25984fe835474479d1617bc0acadfcd6_39.png)

![](img/25984fe835474479d1617bc0acadfcd6_41.png)

![](img/25984fe835474479d1617bc0acadfcd6_43.png)

![](img/25984fe835474479d1617bc0acadfcd6_45.png)

## 概述

![](img/25984fe835474479d1617bc0acadfcd6_47.png)

![](img/25984fe835474479d1617bc0acadfcd6_49.png)

![](img/25984fe835474479d1617bc0acadfcd6_51.png)

![](img/25984fe835474479d1617bc0acadfcd6_53.png)

![](img/25984fe835474479d1617bc0acadfcd6_55.png)

![](img/25984fe835474479d1617bc0acadfcd6_57.png)

![](img/25984fe835474479d1617bc0acadfcd6_59.png)

![](img/25984fe835474479d1617bc0acadfcd6_61.png)

![](img/25984fe835474479d1617bc0acadfcd6_63.png)

上一节我们完成了游戏的核心玩法。本节中，我们将重点优化游戏的资源管理。目前，游戏的音频文件（WAV格式）体积庞大，而图片文件散落在多个目录中。我们将通过两个主要改进来解决这些问题：
1.  将音频转换为OGG格式并实现异步加载，以显著减小游戏体积。
2.  创建一个资源打包器，将所有资源（图片和音频）整合到一个`.pack`文件中，使游戏发布更整洁，加载更高效。

![](img/25984fe835474479d1617bc0acadfcd6_65.png)

![](img/25984fe835474479d1617bc0acadfcd6_67.png)

![](img/25984fe835474479d1617bc0acadfcd6_69.png)

![](img/25984fe835474479d1617bc0acadfcd6_71.png)

![](img/25984fe835474479d1617bc0acadfcd6_73.png)

---

![](img/25984fe835474479d1617bc0acadfcd6_75.png)

![](img/25984fe835474479d1617bc0acadfcd6_77.png)

![](img/25984fe835474479d1617bc0acadfcd6_79.png)

## 实现异步OGG加载 🔊

![](img/25984fe835474479d1617bc0acadfcd6_81.png)

![](img/25984fe835474479d1617bc0acadfcd6_83.png)

OGG是一种压缩音频格式，可以大幅减小文件体积。例如，一段音乐从WAV格式的14.5MB可以压缩到OGG格式的约500KB。然而，解压OGG需要时间。为了解决这个问题，我们将利用之前实现的任务系统进行异步加载。

![](img/25984fe835474479d1617bc0acadfcd6_85.png)

![](img/25984fe835474479d1617bc0acadfcd6_87.png)

### 核心步骤

![](img/25984fe835474479d1617bc0acadfcd6_89.png)

![](img/25984fe835474479d1617bc0acadfcd6_91.png)

![](img/25984fe835474479d1617bc0acadfcd6_92.png)

![](img/25984fe835474479d1617bc0acadfcd6_94.png)

![](img/25984fe835474479d1617bc0acadfcd6_96.png)

以下是实现异步OGG加载的核心步骤：

![](img/25984fe835474479d1617bc0acadfcd6_98.png)

1.  **集成OGG解码库**：我们使用`stb_vorbis`库来解码OGG文件。首先，将库文件引入项目。
    ```c
    // 示例：加载 stb_vorbis 库
    #define STB_VORBIS_HEADER_ONLY
    #include "stb_vorbis.c"
    ```

![](img/25984fe835474479d1617bc0acadfcd6_100.png)

![](img/25984fe835474479d1617bc0acadfcd6_102.png)

![](img/25984fe835474479d1617bc0acadfcd6_104.png)

![](img/25984fe835474479d1617bc0acadfcd6_106.png)

![](img/25984fe835474479d1617bc0acadfcd6_108.png)

![](img/25984fe835474479d1617bc0acadfcd6_110.png)

![](img/25984fe835474479d1617bc0acadfcd6_112.png)

![](img/25984fe835474479d1617bc0acadfcd6_114.png)

![](img/25984fe835474479d1617bc0acadfcd6_116.png)

![](img/25984fe835474479d1617bc0acadfcd6_118.png)

![](img/25984fe835474479d1617bc0acadfcd6_120.png)

2.  **创建异步加载任务**：修改音频加载代码，将OGG解码过程封装成一个任务，并提交到通用任务队列中执行，避免阻塞主线程。
    ```c
    // 示例：创建异步加载OGG的任务
    job_system_add_job(general_queue, async_load_ogg_callback, filename, &sound_to_load, NULL);
    ```

![](img/25984fe835474479d1617bc0acadfcd6_122.png)

![](img/25984fe835474479d1617bc0acadfcd6_124.png)

![](img/25984fe835474479d1617bc0acadfcd6_126.png)

3.  **修改音频加载调用**：将游戏中加载背景音乐和音效的调用，从直接加载WAV改为异步加载OGG。
    ```c
    // 之前：直接加载WAV
    loaded_sound = load_wav("data/music.wav");
    // 之后：异步加载OGG
    async_load_ogg("data/music.ogg", &loaded_sound);
    ```

![](img/25984fe835474479d1617bc0acadfcd6_128.png)

![](img/25984fe835474479d1617bc0acadfcd6_130.png)

![](img/25984fe835474479d1617bc0acadfcd6_132.png)

![](img/25984fe835474479d1617bc0acadfcd6_134.png)

![](img/25984fe835474479d1617bc0acadfcd6_136.png)

![](img/25984fe835474479d1617bc0acadfcd6_138.png)

![](img/25984fe835474479d1617bc0acadfcd6_140.png)

![](img/25984fe835474479d1617bc0acadfcd6_142.png)

![](img/25984fe835474479d1617bc0acadfcd6_144.png)

![](img/25984fe835474479d1617bc0acadfcd6_146.png)

![](img/25984fe835474479d1617bc0acadfcd6_148.png)

![](img/25984fe835474479d1617bc0acadfcd6_150.png)

![](img/25984fe835474479d1617bc0acadfcd6_152.png)

完成上述步骤后，游戏启动时音频加载速度更快，且游戏整体体积显著减小。

![](img/25984fe835474479d1617bc0acadfcd6_154.png)

![](img/25984fe835474479d1617bc0acadfcd6_156.png)

![](img/25984fe835474479d1617bc0acadfcd6_158.png)

![](img/25984fe835474479d1617bc0acadfcd6_160.png)

---

![](img/25984fe835474479d1617bc0acadfcd6_162.png)

![](img/25984fe835474479d1617bc0acadfcd6_164.png)

![](img/25984fe835474479d1617bc0acadfcd6_166.png)

![](img/25984fe835474479d1617bc0acadfcd6_168.png)

![](img/25984fe835474479d1617bc0acadfcd6_170.png)

![](img/25984fe835474479d1617bc0acadfcd6_172.png)

![](img/25984fe835474479d1617bc0acadfcd6_174.png)

![](img/25984fe835474479d1617bc0acadfcd6_176.png)

![](img/25984fe835474479d1617bc0acadfcd6_178.png)

![](img/25984fe835474479d1617bc0acadfcd6_180.png)

![](img/25984fe835474479d1617bc0acadfcd6_182.png)

![](img/25984fe835474479d1617bc0acadfcd6_184.png)

## 构建资源打包器 📦

![](img/25984fe835474479d1617bc0acadfcd6_186.png)

![](img/25984fe835474479d1617bc0acadfcd6_188.png)

![](img/25984fe835474479d1617bc0acadfcd6_190.png)

![](img/25984fe835474479d1617bc0acadfcd6_192.png)

![](img/25984fe835474479d1617bc0acadfcd6_193.png)

![](img/25984fe835474479d1617bc0acadfcd6_195.png)

![](img/25984fe835474479d1617bc0acadfcd6_197.png)

![](img/25984fe835474479d1617bc0acadfcd6_199.png)

![](img/25984fe835474479d1617bc0acadfcd6_201.png)

![](img/25984fe835474479d1617bc0acadfcd6_202.png)

![](img/25984fe835474479d1617bc0acadfcd6_204.png)

将所有资源文件打包成单个文件的好处是：管理方便、发布简洁、并且可以通过单次读取提高加载性能。

![](img/25984fe835474479d1617bc0acadfcd6_206.png)

![](img/25984fe835474479d1617bc0acadfcd6_208.png)

![](img/25984fe835474479d1617bc0acadfcd6_210.png)

![](img/25984fe835474479d1617bc0acadfcd6_212.png)

![](img/25984fe835474479d1617bc0acadfcd6_213.png)

![](img/25984fe835474479d1617bc0acadfcd6_215.png)

![](img/25984fe835474479d1617bc0acadfcd6_216.png)

![](img/25984fe835474479d1617bc0acadfcd6_218.png)

![](img/25984fe835474479d1617bc0acadfcd6_220.png)

![](img/25984fe835474479d1617bc0acadfcd6_222.png)

![](img/25984fe835474479d1617bc0acadfcd6_224.png)

![](img/25984fe835474479d1617bc0acadfcd6_226.png)

![](img/25984fe835474479d1617bc0acadfcd6_228.png)

![](img/25984fe835474479d1617bc0acadfcd6_229.png)

### 资源文件结构设计

![](img/25984fe835474479d1617bc0acadfcd6_231.png)

![](img/25984fe835474479d1617bc0acadfcd6_233.png)

![](img/25984fe835474479d1617bc0acadfcd6_235.png)

![](img/25984fe835474479d1617bc0acadfcd6_236.png)

我们设计的资源包文件结构如下：

![](img/25984fe835474479d1617bc0acadfcd6_238.png)

![](img/25984fe835474479d1617bc0acadfcd6_240.png)

![](img/25984fe835474479d1617bc0acadfcd6_242.png)

![](img/25984fe835474479d1617bc0acadfcd6_244.png)

![](img/25984fe835474479d1617bc0acadfcd6_246.png)

1.  **文件头**：包含魔数字符串（如"GA"代表Game Assets）、版本号和资源总数。
2.  **资源索引表**：为每个资源存储其在包文件中的起始偏移量。
3.  **资源数据段**：连续存储所有资源的原始数据。

通过偏移量索引，我们可以快速定位并读取任何资源。

### 打包器实现流程

![](img/25984fe835474479d1617bc0acadfcd6_248.png)

![](img/25984fe835474479d1617bc0acadfcd6_250.png)

![](img/25984fe835474479d1617bc0acadfcd6_252.png)

![](img/25984fe835474479d1617bc0acadfcd6_254.png)

![](img/25984fe835474479d1617bc0acadfcd6_256.png)

以下是资源打包器的实现流程：

![](img/25984fe835474479d1617bc0acadfcd6_258.png)

![](img/25984fe835474479d1617bc0acadfcd6_260.png)

![](img/25984fe835474479d1617bc0acadfcd6_262.png)

![](img/25984fe835474479d1617bc0acadfcd6_264.png)

![](img/25984fe835474479d1617bc0acadfcd6_266.png)

![](img/25984fe835474479d1617bc0acadfcd6_268.png)

![](img/25984fe835474479d1617bc0acadfcd6_270.png)

![](img/25984fe835474479d1617bc0acadfcd6_272.png)

1.  **定义资源枚举**：在头文件中列出所有资源（如图片、音效），并确保游戏和打包器使用相同的顺序。
    ```c
    // cooker_common.h
    typedef enum {
        ASSET_LOGO_LIGHT,
        ASSET_LOGO_DARK,
        ASSET_INVINCIBILITY,
        ASSET_MUSIC_MENU,
        ASSET_SOUND_HIT_01,
        // ... 更多资源
        ASSET_COUNT
    } asset_id;
    ```

![](img/25984fe835474479d1617bc0acadfcd6_274.png)

![](img/25984fe835474479d1617bc0acadfcd6_276.png)

![](img/25984fe835474479d1617bc0acadfcd6_278.png)

![](img/25984fe835474479d1617bc0acadfcd6_280.png)

![](img/25984fe835474479d1617bc0acadfcd6_282.png)

![](img/25984fe835474479d1617bc0acadfcd6_284.png)

![](img/25984fe835474479d1617bc0acadfcd6_286.png)

![](img/25984fe835474479d1617bc0acadfcd6_288.png)

![](img/25984fe835474479d1617bc0acadfcd6_290.png)

![](img/25984fe835474479d1617bc0acadfcd6_292.png)

![](img/25984fe835474479d1617bc0acadfcd6_294.png)

2.  **编写打包器程序**：创建一个独立的程序（不包含在最终游戏中），其功能是：
    *   读取原始资源文件（PNG, OGG, WAV）。
    *   按照预定顺序，将资源数据写入一个新的`.pack`文件。
    *   在文件头写入资源索引信息。

![](img/25984fe835474479d1617bc0acadfcd6_296.png)

![](img/25984fe835474479d1617bc0acadfcd6_298.png)

![](img/25984fe835474479d1617bc0acadfcd6_300.png)

![](img/25984fe835474479d1617bc0acadfcd6_302.png)

![](img/25984fe835474479d1617bc0acadfcd6_304.png)

![](img/25984fe835474479d1617bc0acadfcd6_306.png)

![](img/25984fe835474479d1617bc0acadfcd6_308.png)

![](img/25984fe835474479d1617bc0acadfcd6_310.png)

![](img/25984fe835474479d1617bc0acadfcd6_312.png)

3.  **修改游戏加载逻辑**：修改游戏初始化代码，使其从`.pack`文件中加载资源，而不是直接从分散的文件中读取。
    ```c
    // 游戏启动时加载资源包
    pack_file = load_entire_file("data/game_assets.pack");
    // 通过资源ID获取位图
    bitmap* logo = get_bitmap_from_pack(pack_file, ASSET_LOGO_LIGHT);
    // 通过资源ID获取音效
    sound* hit_sound = get_sound_from_pack(pack_file, ASSET_SOUND_HIT_01);
    ```

![](img/25984fe835474479d1617bc0acadfcd6_314.png)

![](img/25984fe835474479d1617bc0acadfcd6_316.png)

![](img/25984fe835474479d1617bc0acadfcd6_318.png)

![](img/25984fe835474479d1617bc0acadfcd6_320.png)

![](img/25984fe835474479d1617bc0acadfcd6_322.png)

![](img/25984fe835474479d1617bc0acadfcd6_324.png)

![](img/25984fe835474479d1617bc0acadfcd6_325.png)

![](img/25984fe835474479d1617bc0acadfcd6_327.png)

![](img/25984fe835474479d1617bc0acadfcd6_329.png)

![](img/25984fe835474479d1617bc0acadfcd6_331.png)

![](img/25984fe835474479d1617bc0acadfcd6_333.png)

![](img/25984fe835474479d1617bc0acadfcd6_335.png)

![](img/25984fe835474479d1617bc0acadfcd6_337.png)

通过这种方式，我们最终只需向玩家分发一个可执行文件和一个`.pack`资源包文件，极大简化了发布流程。

![](img/25984fe835474479d1617bc0acadfcd6_339.png)

![](img/25984fe835474479d1617bc0acadfcd6_341.png)

![](img/25984fe835474479d1617bc0acadfcd6_343.png)

![](img/25984fe835474479d1617bc0acadfcd6_345.png)

![](img/25984fe835474479d1617bc0acadfcd6_347.png)

![](img/25984fe835474479d1617bc0acadfcd6_349.png)

![](img/25984fe835474479d1617bc0acadfcd6_350.png)

![](img/25984fe835474479d1617bc0acadfcd6_352.png)

![](img/25984fe835474479d1617bc0acadfcd6_353.png)

![](img/25984fe835474479d1617bc0acadfcd6_355.png)

![](img/25984fe835474479d1617bc0acadfcd6_356.png)

![](img/25984fe835474479d1617bc0acadfcd6_358.png)

![](img/25984fe835474479d1617bc0acadfcd6_360.png)

---

![](img/25984fe835474479d1617bc0acadfcd6_362.png)

![](img/25984fe835474479d1617bc0acadfcd6_364.png)

![](img/25984fe835474479d1617bc0acadfcd6_366.png)

![](img/25984fe835474479d1617bc0acadfcd6_368.png)

![](img/25984fe835474479d1617bc0acadfcd6_370.png)

## 总结

![](img/25984fe835474479d1617bc0acadfcd6_372.png)

本节课中我们一起学习了如何优化游戏的资源管理系统。

![](img/25984fe835474479d1617bc0acadfcd6_374.png)

![](img/25984fe835474479d1617bc0acadfcd6_376.png)

![](img/25984fe835474479d1617bc0acadfcd6_378.png)

我们首先实现了**异步OGG音频加载**，利用任务系统在后台解压音频，既减小了游戏体积，又避免了加载卡顿。接着，我们设计并实现了**资源打包器**，将所有图片和音频资源整合到单个文件中，提高了加载效率，并使项目结构更加清晰和专业。

![](img/25984fe835474479d1617bc0acadfcd6_380.png)

![](img/25984fe835474479d1617bc0acadfcd6_382.png)

![](img/25984fe835474479d1617bc0acadfcd6_384.png)

![](img/25984fe835474479d1617bc0acadfcd6_386.png)

![](img/25984fe835474479d1617bc0acadfcd6_388.png)

![](img/25984fe835474479d1617bc0acadfcd6_390.png)

![](img/25984fe835474479d1617bc0acadfcd6_392.png)

![](img/25984fe835474479d1617bc0acadfcd6_394.png)

![](img/25984fe835474479d1617bc0acadfcd6_396.png)

![](img/25984fe835474479d1617bc0acadfcd6_398.png)

![](img/25984fe835474479d1617bc0acadfcd6_399.png)

![](img/25984fe835474479d1617bc0acadfcd6_401.png)

这两项改进是游戏发布前重要的优化步骤，为后续集成Steam平台等功能打下了坚实的基础。在接下来的课程中，我们将进行最终的打磨，并集成在线子系统。
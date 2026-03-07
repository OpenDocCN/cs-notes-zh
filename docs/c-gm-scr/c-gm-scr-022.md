# 022：游戏优化与配置文件

![](img/ab18094230a798259ac1baa49f82bf9c_1.png)

![](img/ab18094230a798259ac1baa49f82bf9c_2.png)

![](img/ab18094230a798259ac1baa49f82bf9c_4.png)

![](img/ab18094230a798259ac1baa49f82bf9c_6.png)

![](img/ab18094230a798259ac1baa49f82bf9c_8.png)

![](img/ab18094230a798259ac1baa49f82bf9c_9.png)

![](img/ab18094230a798259ac1baa49f82bf9c_11.png)

![](img/ab18094230a798259ac1baa49f82bf9c_13.png)

![](img/ab18094230a798259ac1baa49f82bf9c_15.png)

![](img/ab18094230a798259ac1baa49f82bf9c_17.png)

![](img/ab18094230a798259ac1baa49f82bf9c_19.png)

在本节课中，我们将对已基本完成的游戏进行最后的优化和打磨。我们将调整游戏参数、修复一些已知问题，并实现一个简单的配置文件系统，让玩家可以自定义鼠标灵敏度等设置。

![](img/ab18094230a798259ac1baa49f82bf9c_21.png)

![](img/ab18094230a798259ac1baa49f82bf9c_23.png)

![](img/ab18094230a798259ac1baa49f82bf9c_25.png)

![](img/ab18094230a798259ac1baa49f82bf9c_27.png)

![](img/ab18094230a798259ac1baa49f82bf9c_29.png)

![](img/ab18094230a798259ac1baa49f82bf9c_31.png)

![](img/ab18094230a798259ac1baa49f82bf9c_33.png)

![](img/ab18094230a798259ac1baa49f82bf9c_35.png)

---

![](img/ab18094230a798259ac1baa49f82bf9c_37.png)

![](img/ab18094230a798259ac1baa49f82bf9c_39.png)

![](img/ab18094230a798259ac1baa49f82bf9c_41.png)

![](img/ab18094230a798259ac1baa49f82bf9c_43.png)

![](img/ab18094230a798259ac1baa49f82bf9c_45.png)

![](img/ab18094230a798259ac1baa49f82bf9c_47.png)

![](img/ab18094230a798259ac1baa49f82bf9c_49.png)

![](img/ab18094230a798259ac1baa49f82bf9c_51.png)

![](img/ab18094230a798259ac1baa49f82bf9c_53.png)

![](img/ab18094230a798259ac1baa49f82bf9c_55.png)

## 概述与项目进展

![](img/ab18094230a798259ac1baa49f82bf9c_57.png)

![](img/ab18094230a798259ac1baa49f82bf9c_59.png)

![](img/ab18094230a798259ac1baa49f82bf9c_61.png)

![](img/ab18094230a798259ac1baa49f82bf9c_63.png)

![](img/ab18094230a798259ac1baa49f82bf9c_65.png)

![](img/ab18094230a798259ac1baa49f82bf9c_66.png)

![](img/ab18094230a798259ac1baa49f82bf9c_68.png)

![](img/ab18094230a798259ac1baa49f82bf9c_70.png)

![](img/ab18094230a798259ac1baa49f82bf9c_72.png)

![](img/ab18094230a798259ac1baa49f82bf9c_74.png)

我们的游戏开发已接近尾声。所有主要功能均已实现，在过去的几次直播中，我们完成了核心系统和游戏玩法。现在，我们将进行一些微调和整体改进。

![](img/ab18094230a798259ac1baa49f82bf9c_76.png)

![](img/ab18094230a798259ac1baa49f82bf9c_78.png)

![](img/ab18094230a798259ac1baa49f82bf9c_80.png)

![](img/ab18094230a798259ac1baa49f82bf9c_82.png)

![](img/ab18094230a798259ac1baa49f82bf9c_84.png)

![](img/ab18094230a798259ac1baa49f82bf9c_86.png)

![](img/ab18094230a798259ac1baa49f82bf9c_88.png)

![](img/ab18094230a798259ac1baa49f82bf9c_89.png)

游戏现已拥有Steam页面，你可以将其加入愿望单。游戏计划于2020年9月20日发布，将是免费的。同时，你可以在itch.io页面下载游戏及其完整的源代码，包括从第一集到当前第22集的所有代码。

![](img/ab18094230a798259ac1baa49f82bf9c_91.png)

![](img/ab18094230a798259ac1baa49f82bf9c_93.png)

![](img/ab18094230a798259ac1baa49f82bf9c_95.png)

![](img/ab18094230a798259ac1baa49f82bf9c_97.png)

![](img/ab18094230a798259ac1baa49f82bf9c_99.png)

![](img/ab18094230a798259ac1baa49f82bf9c_101.png)

上一节我们完成了资源系统，这是一个重大的重构。本节中，我们将专注于一系列小而重要的优化任务。

![](img/ab18094230a798259ac1baa49f82bf9c_103.png)

![](img/ab18094230a798259ac1baa49f82bf9c_105.png)

![](img/ab18094230a798259ac1baa49f82bf9c_107.png)

![](img/ab18094230a798259ac1baa49f82bf9c_109.png)

## 游戏内容与待办事项

![](img/ab18094230a798259ac1baa49f82bf9c_111.png)

目前游戏包含多个模式：
*   **基础打砖块**：经典的打砖块克隆。
*   **增强打砖块**：添加了各种道具（如**慢速玩家**、**强力方块**等）。
*   **打砖块版乒乓球**：将乒乓球游戏转化为打砖块玩法。
*   **打砖块版俄罗斯方块**：需要调整难度和速度。
*   **打砖块版太空侵略者**。

![](img/ab18094230a798259ac1baa49f82bf9c_113.png)

![](img/ab18094230a798259ac1baa49f82bf9c_115.png)

![](img/ab18094230a798259ac1baa49f82bf9c_117.png)

![](img/ab18094230a798259ac1baa49f82bf9c_119.png)

我们整理了一份优化清单，主要包括：
*   调整游戏速度（特别是俄罗斯方块模式）。
*   优化渲染循环和帧率同步。
*   修复音频循环和崩溃问题。
*   添加配置文件支持。
*   审查并调整游戏颜色方案。
*   修复一些已知的游戏逻辑Bug。

![](img/ab18094230a798259ac1baa49f82bf9c_121.png)

![](img/ab18094230a798259ac1baa49f82bf9c_123.png)

![](img/ab18094230a798259ac1baa49f82bf9c_125.png)

![](img/ab18094230a798259ac1baa49f82bf9c_127.png)

![](img/ab18094230a798259ac1baa49f82bf9c_129.png)

![](img/ab18094230a798259ac1baa49f82bf9c_131.png)

![](img/ab18094230a798259ac1baa49f82bf9c_133.png)

![](img/ab18094230a798259ac1baa49f82bf9c_134.png)

![](img/ab18094230a798259ac1baa49f82bf9c_136.png)

## 调整俄罗斯方块模式难度

![](img/ab18094230a798259ac1baa49f82bf9c_137.png)

![](img/ab18094230a798259ac1baa49f82bf9c_138.png)

![](img/ab18094230a798259ac1baa49f82bf9c_139.png)

![](img/ab18094230a798259ac1baa49f82bf9c_141.png)

![](img/ab18094230a798259ac1baa49f82bf9c_143.png)

![](img/ab18094230a798259ac1baa49f82bf9c_145.png)

在录制游戏预告片时，我们发现俄罗斯方块模式过于困难。本节中，我们来调整其下降速度。

![](img/ab18094230a798259ac1baa49f82bf9c_147.png)

![](img/ab18094230a798259ac1baa49f82bf9c_149.png)

![](img/ab18094230a798259ac1baa49f82bf9c_151.png)

![](img/ab18094230a798259ac1baa49f82bf9c_153.png)

![](img/ab18094230a798259ac1baa49f82bf9c_155.png)

游戏中的敌人（方块）有一个初始下降速度，并会随时间加快。我们需要调整这个速度曲线，使其起始更慢，加速更平缓。

![](img/ab18094230a798259ac1baa49f82bf9c_157.png)

![](img/ab18094230a798259ac1baa49f82bf9c_159.png)

![](img/ab18094230a798259ac1baa49f82bf9c_161.png)

![](img/ab18094230a798259ac1baa49f82bf9c_163.png)

以下是调整下降速度的核心代码逻辑。我们通过修改 `enemy->y` 的增量值来控制速度：

![](img/ab18094230a798259ac1baa49f82bf9c_165.png)

![](img/ab18094230a798259ac1baa49f82bf9c_167.png)

![](img/ab18094230a798259ac1baa49f82bf9c_169.png)

![](img/ab18094230a798259ac1baa49f82bf9c_171.png)

![](img/ab18094230a798259ac1baa49f82bf9c_173.png)

```c
// 在模拟游戏逻辑的循环中
for (每个敌人) {
    // 计算基于游戏进程的速度因子
    float speedFactor = ...; // 根据时间或分数计算
    // 应用速度，使下降更平缓
    enemy->y += 初始速度 * speedFactor * dt;
}
```

![](img/ab18094230a798259ac1baa49f82bf9c_175.png)

![](img/ab18094230a798259ac1baa49f82bf9c_177.png)

![](img/ab18094230a798259ac1baa49f82bf9c_179.png)

![](img/ab18094230a798259ac1baa49f82bf9c_181.png)

![](img/ab18094230a798259ac1baa49f82bf9c_183.png)

![](img/ab18094230a798259ac1baa49f82bf9c_185.png)

通过将初始速度值从60降低到55，并调整速度因子的计算方式，我们让游戏前期更易于上手，后期挑战性逐步增加。

![](img/ab18094230a798259ac1baa49f82bf9c_187.png)

![](img/ab18094230a798259ac1baa49f82bf9c_189.png)

![](img/ab18094230a798259ac1baa49f82bf9c_191.png)

![](img/ab18094230a798259ac1baa49f82bf9c_193.png)

![](img/ab18094230a798259ac1baa49f82bf9c_195.png)

![](img/ab18094230a798259ac1baa49f82bf9c_197.png)

![](img/ab18094230a798259ac1baa49f82bf9c_199.png)

![](img/ab18094230a798259ac1baa49f82bf9c_201.png)

![](img/ab18094230a798259ac1baa49f82bf9c_203.png)

![](img/ab18094230a798259ac1baa49f82bf9c_205.png)

![](img/ab18094230a798259ac1baa49f82bf9c_207.png)

![](img/ab18094230a798259ac1baa49f82bf9c_208.png)

![](img/ab18094230a798259ac1baa49f82bf9c_210.png)

![](img/ab18094230a798259ac1baa49f82bf9c_212.png)

![](img/ab18094230a798259ac1baa49f82bf9c_214.png)

## 实现配置文件系统

![](img/ab18094230a798259ac1baa49f82bf9c_216.png)

![](img/ab18094230a798259ac1baa49f82bf9c_218.png)

![](img/ab18094230a798259ac1baa49f82bf9c_220.png)

![](img/ab18094230a798259ac1baa49f82bf9c_222.png)

![](img/ab18094230a798259ac1baa49f82bf9c_224.png)

![](img/ab18094230a798259ac1baa49f82bf9c_225.png)

![](img/ab18094230a798259ac1baa49f82bf9c_227.png)

![](img/ab18094230a798259ac1baa49f82bf9c_229.png)

![](img/ab18094230a798259ac1baa49f82bf9c_231.png)

有观众建议添加鼠标灵敏度设置。这是一个好主意，我们将实现一个简单的文本配置文件系统。上一节我们优化了核心系统，本节中我们来看看如何让游戏更可配置。

![](img/ab18094230a798259ac1baa49f82bf9c_233.png)

![](img/ab18094230a798259ac1baa49f82bf9c_235.png)

![](img/ab18094230a798259ac1baa49f82bf9c_237.png)

![](img/ab18094230a798259ac1baa49f82bf9c_239.png)

![](img/ab18094230a798259ac1baa49f82bf9c_241.png)

![](img/ab18094230a798259ac1baa49f82bf9c_243.png)

![](img/ab18094230a798259ac1baa49f82bf9c_245.png)

![](img/ab18094230a798259ac1baa49f82bf9c_247.png)

配置文件将是一个名为 `config.txt` 的文本文件，玩家可以编辑它。我们将解析这个文件来读取设置。

![](img/ab18094230a798259ac1baa49f82bf9c_249.png)

![](img/ab18094230a798259ac1baa49f82bf9c_251.png)

![](img/ab18094230a798259ac1baa49f82bf9c_253.png)

![](img/ab18094230a798259ac1baa49f82bf9c_255.png)

![](img/ab18094230a798259ac1baa49f82bf9c_257.png)

![](img/ab18094230a798259ac1baa49f82bf9c_259.png)

![](img/ab18094230a798259ac1baa49f82bf9c_261.png)

![](img/ab18094230a798259ac1baa49f82bf9c_263.png)

![](img/ab18094230a798259ac1baa49f82bf9c_265.png)

![](img/ab18094230a798259ac1baa49f82bf9c_267.png)

![](img/ab18094230a798259ac1baa49f82bf9c_269.png)

![](img/ab18094230a798259ac1baa49f82bf9c_271.png)

以下是配置文件解析的核心步骤：

![](img/ab18094230a798259ac1baa49f82bf9c_273.png)

![](img/ab18094230a798259ac1baa49f82bf9c_275.png)

![](img/ab18094230a798259ac1baa49f82bf9c_277.png)

![](img/ab18094230a798259ac1baa49f82bf9c_279.png)

![](img/ab18094230a798259ac1baa49f82bf9c_281.png)

![](img/ab18094230a798259ac1baa49f82bf9c_283.png)

![](img/ab18094230a798259ac1baa49f82bf9c_285.png)

![](img/ab18094230a798259ac1baa49f82bf9c_286.png)

![](img/ab18094230a798259ac1baa49f82bf9c_288.png)

1.  **读取文件**：使用平台相关的文件读取函数将整个配置文件读入内存。
2.  **解析关键字**：我们编写一个简单的解析器，逐词读取文件内容。
    ```c
    internal String consume_next_word(String* data) {
        // 跳过空白字符
        eat_whitespace(data);
        String result = {0};
        // 读取直到遇到下一个空白字符或文件结尾
        while (data->size && !is_whitespace(data->data[0])) {
            result.data[result.size++] = data->data[0];
            data->data++;
            data->size--;
        }
        return result;
    }
    ```
3.  **匹配与赋值**：将读取到的关键字与预定义的设置（如 `mouse_sensitivity`、`windowed`）进行字符串匹配，然后解析其后的值（浮点数或布尔值）。
    ```c
    if (strings_match(keyword, "mouse_sensitivity")) {
        String valueString = consume_next_word(&data);
        float value = parse_float(valueString);
        // 将值限制在合理范围内并赋值给游戏变量
        gameState->mouseSensitivity = clamp(value, 0.1f, 10.0f);
    } else if (strings_match(keyword, "windowed")) {
        String valueString = consume_next_word(&data);
        gameState->windowed = strings_match(valueString, "true");
    }
    ```
4.  **浮点数解析**：我们实现了一个简单的 `parse_float` 函数，能处理整数和小数。
    ```c
    internal float parse_float(String str) {
        float result = 0.0f;
        float decimalPlace = 1.0f;
        bool inDecimal = false;
        for (u32 i = 0; i < str.size; ++i) {
            char c = str.data[i];
            if (c >= '0' && c <= '9') {
                int digit = c - '0';
                if (!inDecimal) {
                    result = result * 10.0f + (float)digit;
                } else {
                    decimalPlace *= 10.0f;
                    result += (float)digit / decimalPlace;
                }
            } else if (c == '.' || c == ',') {
                inDecimal = true;
            }
        }
        return result;
    }
    ```

![](img/ab18094230a798259ac1baa49f82bf9c_290.png)

![](img/ab18094230a798259ac1baa49f82bf9c_291.png)

![](img/ab18094230a798259ac1baa49f82bf9c_293.png)

![](img/ab18094230a798259ac1baa49f82bf9c_295.png)

![](img/ab18094230a798259ac1baa49f82bf9c_297.png)

![](img/ab18094230a798259ac1baa49f82bf9c_299.png)

![](img/ab18094230a798259ac1baa49f82bf9c_301.png)

![](img/ab18094230a798259ac1baa49f82bf9c_303.png)

![](img/ab18094230a798259ac1baa49f82bf9c_305.png)

![](img/ab18094230a798259ac1baa49f82bf9c_307.png)

![](img/ab18094230a798259ac1baa49f82bf9c_309.png)

![](img/ab18094230a798259ac1baa49f82bf9c_311.png)

![](img/ab18094230a798259ac1baa49f82bf9c_313.png)

![](img/ab18094230a798259ac1baa49f82bf9c_315.png)

![](img/ab18094230a798259ac1baa49f82bf9c_317.png)

![](img/ab18094230a798259ac1baa49f82bf9c_319.png)

![](img/ab18094230a798259ac1baa49f82bf9c_321.png)

![](img/ab18094230a798259ac1baa49f82bf9c_322.png)

![](img/ab18094230a798259ac1baa49f82bf9c_324.png)

通过这个约90行代码的简单解析器，我们成功为游戏添加了可配置的鼠标灵敏度和窗口模式设置。

![](img/ab18094230a798259ac1baa49f82bf9c_326.png)

![](img/ab18094230a798259ac1baa49f82bf9c_328.png)

![](img/ab18094230a798259ac1baa49f82bf9c_330.png)

![](img/ab18094230a798259ac1baa49f82bf9c_332.png)

![](img/ab18094230a798259ac1baa49f82bf9c_334.png)

![](img/ab18094230a798259ac1baa49f82bf9c_336.png)

![](img/ab18094230a798259ac1baa49f82bf9c_338.png)

![](img/ab18094230a798259ac1baa49f82bf9c_340.png)

![](img/ab18094230a798259ac1baa49f82bf9c_342.png)

![](img/ab18094230a798259ac1baa49f82bf9c_344.png)

![](img/ab18094230a798259ac1baa49f82bf9c_346.png)

![](img/ab18094230a798259ac1baa49f82bf9c_348.png)

![](img/ab18094230a798259ac1baa49f82bf9c_350.png)

![](img/ab18094230a798259ac1baa49f82bf9c_352.png)

![](img/ab18094230a798259ac1baa49f82bf9c_354.png)

![](img/ab18094230a798259ac1baa49f82bf9c_356.png)

![](img/ab18094230a798259ac1baa49f82bf9c_357.png)

![](img/ab18094230a798259ac1baa49f82bf9c_359.png)

![](img/ab18094230a798259ac1baa49f82bf9c_361.png)

![](img/ab18094230a798259ac1baa49f82bf9c_363.png)

## 修复游戏Bug与优化

![](img/ab18094230a798259ac1baa49f82bf9c_365.png)

![](img/ab18094230a798259ac1baa49f82bf9c_366.png)

![](img/ab18094230a798259ac1baa49f82bf9c_368.png)

![](img/ab18094230a798259ac1baa49f82bf9c_370.png)

![](img/ab18094230a798259ac1baa49f82bf9c_371.png)

![](img/ab18094230a798259ac1baa49f82bf9c_373.png)

![](img/ab18094230a798259ac1baa49f82bf9c_375.png)

![](img/ab18094230a798259ac1baa49f82bf9c_377.png)

![](img/ab18094230a798259ac1baa49f82bf9c_379.png)

![](img/ab18094230a798259ac1baa49f82bf9c_381.png)

![](img/ab18094230a798259ac1baa49f82bf9c_383.png)

![](img/ab18094230a798259ac1baa49f82bf9c_385.png)

![](img/ab18094230a798259ac1baa49f82bf9c_387.png)

![](img/ab18094230a798259ac1baa49f82bf9c_389.png)

![](img/ab18094230a798259ac1baa49f82bf9c_391.png)

![](img/ab18094230a798259ac1baa49f82bf9c_393.png)

![](img/ab18094230a798259ac1baa49f82bf9c_395.png)

![](img/ab18094230a798259ac1baa49f82bf9c_396.png)

![](img/ab18094230a798259ac1baa49f82bf9c_398.png)

![](img/ab18094230a798259ac1baa49f82bf9c_400.png)

![](img/ab18094230a798259ac1baa49f82bf9c_402.png)

![](img/ab18094230a798259ac1baa49f82bf9c_404.png)

![](img/ab18094230a798259ac1baa49f82bf9c_406.png)

![](img/ab18094230a798259ac1baa49f82bf9c_408.png)

![](img/ab18094230a798259ac1baa49f82bf9c_410.png)

![](img/ab18094230a798259ac1baa49f82bf9c_412.png)

![](img/ab18094230a798259ac1baa49f82bf9c_414.png)

![](img/ab18094230a798259ac1baa49f82bf9c_416.png)

### 修复“彗星”与“强力方块”碰撞问题

![](img/ab18094230a798259ac1baa49f82bf9c_418.png)

![](img/ab18094230a798259ac1baa49f82bf9c_420.png)

![](img/ab18094230a798259ac1baa49f82bf9c_422.png)

![](img/ab18094230a798259ac1baa49f82bf9c_424.png)

![](img/ab18094230a798259ac1baa49f82bf9c_426.png)

![](img/ab18094230a798259ac1baa49f82bf9c_428.png)

![](img/ab18094230a798259ac1baa49f82bf9c_430.png)

![](img/ab18094230a798259ac1baa49f82bf9c_432.png)

![](img/ab18094230a798259ac1baa49f82bf9c_434.png)

![](img/ab18094230a798259ac1baa49f82bf9c_436.png)

![](img/ab18094230a798259ac1baa49f82bf9c_438.png)

![](img/ab18094230a798259ac1baa49f82bf9c_440.png)

![](img/ab18094230a798259ac1baa49f82bf9c_442.png)

当“彗星”道具击中“强力方块”时，会导致游戏立即失败。这是因为碰撞检测逻辑在遇到“强力方块”时，错误地触发了球体尺寸增大的代码路径，导致球体卡在方块内。

![](img/ab18094230a798259ac1baa49f82bf9c_444.png)

![](img/ab18094230a798259ac1baa49f82bf9c_446.png)

![](img/ab18094230a798259ac1baa49f82bf9c_448.png)

修复方法是，在碰撞检测中，对“强力方块”进行特殊处理，避免在碰撞时改变球体大小，并确保球体的反弹方向正确。

![](img/ab18094230a798259ac1baa49f82bf9c_450.png)

![](img/ab18094230a798259ac1baa49f82bf9c_452.png)

![](img/ab18094230a798259ac1baa49f82bf9c_454.png)

```c
// 在方块碰撞检测函数中
if (block->type == BLOCK_TYPE_STRONG) {
    // 对于强力方块，不增大球体，只进行反弹
    reverse_ball_direction(ball);
} else {
    // 对于普通方块，执行原有的逻辑（包括可能的大小变化）
    handle_normal_block_collision(ball, block);
}
```

![](img/ab18094230a798259ac1baa49f82bf9c_456.png)

![](img/ab18094230a798259ac1baa49f82bf9c_458.png)

### 优化渲染循环

![](img/ab18094230a798259ac1baa49f82bf9c_460.png)

![](img/ab18094230a798259ac1baa49f82bf9c_462.png)

![](img/ab18094230a798259ac1baa49f82bf9c_464.png)

![](img/ab18094230a798259ac1baa49f82bf9c_466.png)

![](img/ab18094230a798259ac1baa49f82bf9c_468.png)

![](img/ab18094230a798259ac1baa49f82bf9c_470.png)

![](img/ab18094230a798259ac1baa49f82bf9c_472.png)

![](img/ab18094230a798259ac1baa49f82bf9c_474.png)

![](img/ab18094230a798259ac1baa49f82bf9c_476.png)

我们优化了绘制矩形函数的内部循环。原先的代码在每一行像素绘制后，都通过乘法计算下一行的起始位置。现在我们预先计算好行跨度（stride），然后通过加法来移动指针，提高了缓存友好性。

![](img/ab18094230a798259ac1baa49f82bf9c_478.png)

![](img/ab18094230a798259ac1baa49f82bf9c_480.png)

![](img/ab18094230a798259ac1baa49f82bf9c_482.png)

![](img/ab18094230a798259ac1baa49f82bf9c_484.png)

![](img/ab18094230a798259ac1baa49f82bf9c_486.png)

![](img/ab18094230a798259ac1baa49f82bf9c_488.png)

![](img/ab18094230a798259ac1baa49f82bf9c_490.png)

![](img/ab18094230a798259ac1baa49f82bf9c_492.png)

![](img/ab18094230a798259ac1baa49f82bf9c_494.png)

```c
// 优化前
for (int y = yMin; y < yMax; ++y) {
    u32* pixel = (u32*)row + xMin;
    for (int x = xMin; x < xMax; ++x) {
        *pixel++ = color;
    }
    row += bufferWidth; // 每次都需要乘法计算
}

![](img/ab18094230a798259ac1baa49f82bf9c_496.png)

![](img/ab18094230a798259ac1baa49f82bf9c_498.png)

![](img/ab18094230a798259ac1baa49f82bf9c_499.png)

![](img/ab18094230a798259ac1baa49f82bf9c_501.png)

![](img/ab18094230a798259ac1baa49f82bf9c_503.png)

![](img/ab18094230a798259ac1baa49f82bf9c_505.png)

![](img/ab18094230a798259ac1baa49f82bf9c_507.png)

![](img/ab18094230a798259ac1baa49f82bf9c_509.png)

![](img/ab18094230a798259ac1baa49f82bf9c_511.png)

![](img/ab18094230a798259ac1baa49f82bf9c_513.png)

![](img/ab18094230a798259ac1baa49f82bf9c_515.png)

![](img/ab18094230a798259ac1baa49f82bf9c_517.png)

![](img/ab18094230a798259ac1baa49f82bf9c_519.png)

![](img/ab18094230a798259ac1baa49f82bf9c_521.png)

// 优化后
u32* pixel = (u32*)row + xMin;
int stride = bufferWidth; // 预计算跨度
for (int y = yMin; y < yMax; ++y) {
    u32* rowPixel = pixel;
    for (int x = xMin; x < xMax; ++x) {
        *rowPixel++ = color;
    }
    pixel += stride; // 使用加法，更高效
}
```

![](img/ab18094230a798259ac1baa49f82bf9c_523.png)

![](img/ab18094230a798259ac1baa49f82bf9c_525.png)

![](img/ab18094230a798259ac1baa49f82bf9c_527.png)

![](img/ab18094230a798259ac1baa49f82bf9c_529.png)

![](img/ab18094230a798259ac1baa49f82bf9c_531.png)

### 修复断言（Assert）在发布版本中生效的问题

![](img/ab18094230a798259ac1baa49f82bf9c_533.png)

![](img/ab18094230a798259ac1baa49f82bf9c_534.png)

![](img/ab18094230a798259ac1baa49f82bf9c_536.png)

![](img/ab18094230a798259ac1baa49f82bf9c_538.png)

![](img/ab18094230a798259ac1baa49f82bf9c_540.png)

![](img/ab18094230a798259ac1baa49f82bf9c_542.png)

![](img/ab18094230a798259ac1baa49f82bf9c_544.png)

我们使用的第三方音频库（OGG解码器）直接包含了标准C库的 `assert.h`，这导致即使在发布版本中，断言失败也会导致游戏崩溃。为了解决这个问题，我们在包含该库的头文件之前，重新定义了 `assert` 宏，使其在非开发版本中为空操作。

![](img/ab18094230a798259ac1baa49f82bf9c_546.png)

![](img/ab18094230a798259ac1baa49f82bf9c_548.png)

![](img/ab18094230a798259ac1baa49f82bf9c_550.png)

![](img/ab18094230a798259ac1baa49f82bf9c_552.png)

![](img/ab18094230a798259ac1baa49f82bf9c_554.png)

```c
// 在包含可能引入 assert.h 的库之前
#ifndef DEVELOPMENT
#define assert(expression) ((void)0)
#endif
// 然后包含第三方库头文件
#include "stb_vorbis.h"
```

![](img/ab18094230a798259ac1baa49f82bf9c_556.png)

![](img/ab18094230a798259ac1baa49f82bf9c_557.png)

![](img/ab18094230a798259ac1baa49f82bf9c_559.png)

![](img/ab18094230a798259ac1baa49f82bf9c_561.png)

![](img/ab18094230a798259ac1baa49f82bf9c_563.png)

![](img/ab18094230a798259ac1baa49f82bf9c_565.png)

![](img/ab18094230a798259ac1baa49f82bf9c_567.png)

![](img/ab18094230a798259ac1baa49f82bf9c_569.png)

## 审查与调整颜色方案

![](img/ab18094230a798259ac1baa49f82bf9c_571.png)

![](img/ab18094230a798259ac1baa49f82bf9c_573.png)

![](img/ab18094230a798259ac1baa49f82bf9c_575.png)

![](img/ab18094230a798259ac1baa49f82bf9c_577.png)

![](img/ab18094230a798259ac1baa49f82bf9c_579.png)

![](img/ab18094230a798259ac1baa49f82bf9c_581.png)

![](img/ab18094230a798259ac1baa49f82bf9c_583.png)

![](img/ab18094230a798259ac1baa49f82bf9c_585.png)

![](img/ab18094230a798259ac1baa49f82bf9c_587.png)

![](img/ab18094230a798259ac1baa49f82bf9c_589.png)

![](img/ab18094230a798259ac1baa49f82bf9c_591.png)

![](img/ab18094230a798259ac1baa49f82bf9c_593.png)

游戏原先的颜色是随机选取的，缺乏一致性。我们使用图像处理软件（如Affinity Photo）对主要关卡的颜色进行了调整，目标是提高视觉清晰度和美感。

![](img/ab18094230a798259ac1baa49f82bf9c_595.png)

![](img/ab18094230a798259ac1baa49f82bf9c_597.png)

![](img/ab18094230a798259ac1baa49f82bf9c_599.png)

![](img/ab18094230a798259ac1baa49f82bf9c_601.png)

![](img/ab18094230a798259ac1baa49f82bf9c_603.png)

![](img/ab18094230a798259ac1baa49f82bf9c_605.png)

![](img/ab18094230a798259ac1baa49f82bf9c_607.png)

![](img/ab18094230a798259ac1baa49f82bf9c_609.png)

![](img/ab18094230a798259ac1baa49f82bf9c_611.png)

![](img/ab18094230a798259ac1baa49f82bf9c_613.png)

![](img/ab18094230a798259ac1baa49f82bf9c_615.png)

![](img/ab18094230a798259ac1baa49f82bf9c_617.png)

我们选择了饱和度较高但对比度合适的配色方案，确保玩家、球体和方块在屏幕上清晰可辨。调整后的颜色方案使游戏看起来更专业、更舒适。

![](img/ab18094230a798259ac1baa49f82bf9c_619.png)

![](img/ab18094230a798259ac1baa49f82bf9c_621.png)

![](img/ab18094230a798259ac1baa49f82bf9c_623.png)

![](img/ab18094230a798259ac1baa49f82bf9c_625.png)

![](img/ab18094230a798259ac1baa49f82bf9c_627.png)

![](img/ab18094230a798259ac1baa49f82bf9c_629.png)

![](img/ab18094230a798259ac1baa49f82bf9c_631.png)

## 尝试重构音频混合系统（遇到的问题）

![](img/ab18094230a798259ac1baa49f82bf9c_633.png)

![](img/ab18094230a798259ac1baa49f82bf9c_635.png)

![](img/ab18094230a798259ac1baa49f82bf9c_637.png)

![](img/ab18094230a798259ac1baa49f82bf9c_639.png)

![](img/ab18094230a798259ac1baa49f82bf9c_641.png)

![](img/ab18094230a798259ac1baa49f82bf9c_643.png)

![](img/ab18094230a798259ac1baa49f82bf9c_644.png)

![](img/ab18094230a798259ac1baa49f82bf9c_646.png)

![](img/ab18094230a798259ac1baa49f82bf9c_648.png)

![](img/ab18094230a798259ac1baa49f82bf9c_650.png)

![](img/ab18094230a798259ac1baa49f82bf9c_652.png)

我们尝试重构音频混合系统，将循环顺序从“为每个样本遍历所有声音”改为“为每个声音遍历所有样本”。理论上，这能提高CPU缓存命中率。

![](img/ab18094230a798259ac1baa49f82bf9c_654.png)

![](img/ab18094230a798259ac1baa49f82bf9c_656.png)

![](img/ab18094230a798259ac1baa49f82bf9c_658.png)

![](img/ab18094230a798259ac1baa49f82bf9c_660.png)

![](img/ab18094230a798259ac1baa49f82bf9c_661.png)

![](img/ab18094230a798259ac1baa49f82bf9c_663.png)

然而，在实现过程中，我们遇到了多线程相关的崩溃问题（空指针访问），尽管在调试器中变量显示非空。这表明当前的音频播放线程与主线程之间的数据同步可能存在问题。

![](img/ab18094230a798259ac1baa49f82bf9c_665.png)

![](img/ab18094230a798259ac1baa49f82bf9c_667.png)

![](img/ab18094230a798259ac1baa49f82bf9c_669.png)

![](img/ab18094230a798259ac1baa49f82bf9c_671.png)

![](img/ab18094230a798259ac1baa49f82bf9c_673.png)

![](img/ab18094230a798259ac1baa49f82bf9c_675.png)

![](img/ab18094230a798259ac1baa49f82bf9c_677.png)

![](img/ab18094230a798259ac1baa49f82bf9c_679.png)

由于时间关系且该问题较为复杂，我们决定暂时回退更改，将音频系统的彻底重构留到下一次直播中解决。我们仅修复了一个已知问题：在返回主菜单时，强制淡出所有声音。

![](img/ab18094230a798259ac1baa49f82bf9c_681.png)

![](img/ab18094230a798259ac1baa49f82bf9c_683.png)

![](img/ab18094230a798259ac1baa49f82bf9c_685.png)

![](img/ab18094230a798259ac1baa49f82bf9c_687.png)

![](img/ab18094230a798259ac1baa49f82bf9c_689.png)

## 总结与下期预告

![](img/ab18094230a798259ac1baa49f82bf9c_691.png)

![](img/ab18094230a798259ac1baa49f82bf9c_693.png)

![](img/ab18094230a798259ac1baa49f82bf9c_695.png)

![](img/ab18094230a798259ac1baa49f82bf9c_697.png)

![](img/ab18094230a798259ac1baa49f82bf9c_699.png)

![](img/ab18094230a798259ac1baa49f82bf9c_701.png)

![](img/ab18094230a798259ac1baa49f82bf9c_703.png)

![](img/ab18094230a798259ac1baa49f82bf9c_705.png)

![](img/ab18094230a798259ac1baa49f82bf9c_707.png)

本节课中我们一起学习了如何进行游戏发布前的最后打磨。我们完成了一系列优化工作：

![](img/ab18094230a798259ac1baa49f82bf9c_709.png)

![](img/ab18094230a798259ac1baa49f82bf9c_711.png)

![](img/ab18094230a798259ac1baa49f82bf9c_713.png)

![](img/ab18094230a798259ac1baa49f82bf9c_715.png)

![](img/ab18094230a798259ac1baa49f82bf9c_717.png)

![](img/ab18094230a798259ac1baa49f82bf9c_719.png)

![](img/ab18094230a798259ac1baa49f82bf9c_721.png)

![](img/ab18094230a798259ac1baa49f82bf9c_723.png)

![](img/ab18094230a798259ac1baa49f82bf9c_725.png)

![](img/ab18094230a798259ac1baa49f82bf9c_727.png)

1.  **平衡性调整**：降低了俄罗斯方块模式的难度。
2.  **新增功能**：实现了一个完整的文本配置文件解析器，支持鼠标灵敏度和窗口模式设置。
3.  **Bug修复**：解决了“彗星”与“强力方块”碰撞的致命错误，修复了关卡过渡时方块残留的视觉问题。
4.  **代码优化**：改进了渲染函数的内部循环，并解决了发布版本中断言意外生效的问题。
5.  **视觉提升**：为游戏选择了更协调、更清晰的颜色方案。

![](img/ab18094230a798259ac1baa49f82bf9c_729.png)

![](img/ab18094230a798259ac1baa49f82bf9c_731.png)

![](img/ab18094230a798259ac1baa49f82bf9c_733.png)

![](img/ab18094230a798259ac1baa49f82bf9c_735.png)

![](img/ab18094230a798259ac1baa49f82bf9c_737.png)

![](img/ab18094230a798259ac1baa49f82bf9c_739.png)

![](img/ab18094230a798259ac1baa49f82bf9c_741.png)

![](img/ab18094230a798259ac1baa49f82bf9c_743.png)

![](img/ab18094230a798259ac1baa49f82bf9c_745.png)

![](img/ab18094230a798259ac1baa49f82bf9c_747.png)

![](img/ab18094230a798259ac1baa49f82bf9c_749.png)

![](img/ab18094230a798259ac1baa49f82bf9c_751.png)

![](img/ab18094230a798259ac1baa49f82bf9c_753.png)

尽管在重构音频系统时遇到了挑战，但整体进展非常顺利。游戏已经非常接近可发布状态。

![](img/ab18094230a798259ac1baa49f82bf9c_755.png)

![](img/ab18094230a798259ac1baa49f82bf9c_757.png)

![](img/ab18094230a798259ac1baa49f82bf9c_759.png)

![](img/ab18094230a798259ac1baa49f82bf9c_761.png)

![](img/ab18094230a798259ac1baa49f82bf9c_763.png)

![](img/ab18094230a798259ac1baa49f82bf9c_765.png)

![](img/ab18094230a798259ac1baa49f82bf9c_767.png)

![](img/ab18094230a798259ac1baa49f82bf9c_769.png)

![](img/ab18094230a798259ac1baa49f82bf9c_771.png)

在下一次直播（预计也是最后一次）中，我们将：
*   彻底修复和优化音频系统，解决多线程安全问题。
*   完成优化清单上的剩余项目。
*   进行最终的测试和打包。
*   准备将游戏正式发布到Steam平台。

![](img/ab18094230a798259ac1baa49f82bf9c_773.png)

![](img/ab18094230a798259ac1baa49f82bf9c_775.png)

![](img/ab18094230a798259ac1baa49f82bf9c_777.png)

![](img/ab18094230a798259ac1baa49f82bf9c_779.png)

![](img/ab18094230a798259ac1baa49f82bf9c_781.png)

![](img/ab18094230a798259ac1baa49f82bf9c_783.png)

![](img/ab18094230a798259ac1baa49f82bf9c_785.png)

![](img/ab18094230a798259ac1baa49f82bf9c_786.png)

![](img/ab18094230a798259ac1baa49f82bf9c_788.png)

![](img/ab18094230a798259ac1baa49f82bf9c_790.png)

![](img/ab18094230a798259ac1baa49f82bf9c_792.png)

![](img/ab18094230a798259ac1baa49f82bf9c_794.png)

感谢你的观看，整个从零开始的开发过程即将迎来一个激动人心的终点！你可以继续在itch.io下载最新代码，或在Steam上愿望单关注我们的游戏。下次直播见！
# 2D游戏开发：第6讲：愤怒的小鸟 🐦

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_1.png)

在本节课中，我们将学习如何使用LÖVE2D内置的Box2D物理引擎来创建一个类似《愤怒的小鸟》的游戏。我们将重点介绍物理世界、刚体、碰撞检测以及如何通过鼠标交互来发射物体。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_3.png)

---

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_5.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_6.png)

## 概述

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_8.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_10.png)

本节课我们将探索Box2D物理引擎，它是LÖVE2D中用于模拟2D物理的强大工具。我们将学习如何创建物理世界、定义不同类型的刚体（静态、动态、运动学），以及如何处理它们之间的碰撞。通过构建一个简化的《愤怒的小鸟》游戏，我们将实践如何结合物理模拟与用户输入（鼠标拖拽和释放）来实现游戏的核心玩法。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_12.png)

---

## 物理世界与刚体

上一节我们介绍了课程目标，本节中我们来看看Box2D的核心概念：物理世界和刚体。

### 创建物理世界

物理世界（World）是Box2D中所有物理实体（刚体）存在的容器。它负责模拟重力、更新所有物体的位置和速度，并处理碰撞检测。

创建世界的代码如下：
```lua
world = love.physics.newWorld(0, 300)
```
这里，`(0, 300)` 表示重力向量：X轴重力为0，Y轴重力为300（模拟向下的力）。在LÖVE2D的Box2D实现中，通常使用“30像素/米”的比例，因此300大致模拟了地球重力（9.8 m/s² * 30 ≈ 294）。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_14.png)

### 刚体类型

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_16.png)

在物理世界中，物体被称为刚体（Body）。刚体有三种主要类型，它们决定了物体如何与物理世界互动：

以下是三种刚体类型的定义：
*   **静态刚体（Static）**：`love.physics.newBody(world, x, y, "static")`
    *   位置固定，不受重力或其他物体影响。
    *   其他物体可以与之碰撞并反弹。
    *   例如：地面、固定的墙壁。
*   **动态刚体（Dynamic）**：`love.physics.newBody(world, x, y, "dynamic")`
    *   完全受物理定律支配，会受重力影响，会与其他物体碰撞并产生相互作用。
    *   例如：游戏中被发射的小鸟、可被击碎的障碍物。
*   **运动学刚体（Kinematic）**：`love.physics.newBody(world, x, y, "kinematic")`
    *   可以通过代码直接控制其运动（如设置速度）。
    *   不受重力或其他物体的力影响，但可以影响其他动态物体。
    *   例如：移动的平台、旋转的障碍物。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_18.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_19.png)

---

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_21.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_22.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_23.png)

## 形状与夹具

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_25.png)

上一节我们介绍了刚体类型，本节中我们来看看如何为刚体赋予具体的形状和物理属性。

刚体本身只是一个抽象的物理点。为了让它具有形状并能参与碰撞，我们需要为其附加**夹具（Fixture）**。夹具定义了刚体的形状（如矩形、圆形）、密度、摩擦力和弹性等属性。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_27.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_28.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_30.png)

以下是创建并附加一个矩形夹具的步骤：
1.  **创建刚体**：`local body = love.physics.newBody(world, 400, 300, "dynamic")`
2.  **定义形状**：`local shape = love.physics.newRectangleShape(width, height)`
3.  **创建夹具**：`local fixture = love.physics.newFixture(body, shape)`

通过夹具，Box2D就能计算该刚体如何与其他形状碰撞、反弹等。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_32.png)

---

## 碰撞检测与处理

在《愤怒的小鸟》中，我们需要知道小鸟何时击中障碍物或敌人，并根据撞击速度决定是否摧毁目标。Box2D提供了碰撞回调函数来实现这一点。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_34.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_35.png)

### 设置碰撞回调

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_37.png)

我们可以在世界对象上设置四个阶段的回调函数，最常用的是 `beginContact`，它在两个夹具刚开始接触时被调用。

```lua
world:setCallbacks(beginContact, endContact, preSolve, postSolve)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_39.png)

function beginContact(a, b, collision)
    -- a 和 b 是两个发生碰撞的夹具
    -- 在这里处理碰撞逻辑
end
```

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_41.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_42.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_44.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_45.png)

### 区分碰撞对象

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_47.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_48.png)

为了知道是谁撞上了谁，我们需要在创建夹具时为其设置用户数据（User Data）。

```lua
-- 创建时设置
fixture:setUserData("player")

-- 在碰撞回调中获取
local typeA = a:getUserData()
local typeB = b:getUserData()
```

然后，我们就可以在 `beginContact` 函数中检查碰撞双方的类型（例如“player”和“obstacle”），并计算撞击速度来决定是否摧毁物体。

**重要提示**：不应在碰撞回调函数内部直接销毁刚体，这可能导致物理引擎内部状态错误。正确的做法是将需要销毁的刚体记录到一个列表中，然后在 `update` 函数的最后统一进行销毁。

---

## 实现发射与轨迹预测

《愤怒的小鸟》的核心玩法是拖拽弹弓上的小鸟，调整角度和力度后释放。这涉及到鼠标输入处理和基于物理的轨迹预测。

### 鼠标输入处理

LÖVE2D提供了 `love.mousepressed` 和 `love.mousereleased` 回调函数来捕获鼠标点击和释放事件。

```lua
function love.mousepressed(x, y, button)
    if button == 1 then -- 左键按下
        -- 开始拖拽，记录起始位置
        aiming = true
        startX, startY = x, y
    end
end

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_50.png)

function love.mousereleased(x, y, button)
    if button == 1 and aiming then
        -- 释放，计算发射向量并创建动态小鸟刚体
        launchBird(x, y)
        aiming = false
    end
end
```

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_52.png)

### 轨迹预测

在拖拽过程中，我们需要实时绘制一条预测线，显示小鸟释放后的飞行路径。这可以通过模拟物理公式来实现：

预测轨迹的核心是模拟物体在初始速度和重力影响下的运动。对于每一帧（假设1/60秒），我们计算其位置：
*   **X轴位置**：`x = startX + impulseX * t`
*   **Y轴位置**：`y = startY + impulseY * t + 0.5 * gravity * t²`

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_54.png)

其中，`impulseX` 和 `impulseY` 是根据鼠标拖拽偏移计算出的初始速度分量，`gravity` 是世界重力，`t` 是累计时间。我们循环计算未来几十帧的位置，并将这些点连接起来，就形成了预测轨迹。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_56.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_58.png)

---

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_60.png)

## 关节：构建复杂物理结构

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_62.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_63.png)

除了基本的刚体，Box2D还提供了**关节（Joint）**，用于将多个刚体以特定方式连接起来，从而构建更复杂的物理结构，这在《愤怒的小鸟》中用于创建由多个部分组成的可破坏建筑。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_65.png)

以下是几种常见的关节类型及其应用：
*   **焊接关节（Weld Joint）**：将两个刚体牢固地固定在一起，像一个整体。可用于创建坚固的墙体结构。
*   **旋转关节（Revolute Joint）**：允许刚体围绕一个公共点旋转。类似于钟摆或旋转门。
*   **滑轮关节（Pulley Joint）**：模拟滑轮系统，两个物体通过“绳索”连接，一方的移动会影响另一方。
*   **绳索关节（Rope Joint）**：将两个刚体的最大距离限制在一定范围内，像一根有长度的绳子。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_67.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_69.png)

在课程提供的示例和问题集中，你将有机会实现并使用一种关节来增强关卡的复杂性和趣味性。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_71.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_72.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_74.png)

---

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_76.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_78.png)

## 总结

本节课我们一起学习了Box2D物理引擎的基础知识。我们了解了如何创建物理世界，定义了静态、动态和运动学三种刚体，并通过夹具为它们赋予形状。我们实现了碰撞检测回调，用于处理游戏中的击碎逻辑。最后，我们结合鼠标输入实现了小鸟的拖拽发射和轨迹预测功能，并简要介绍了用于构建复杂结构的关节。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_80.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_81.png)

通过将这些概念结合起来，我们成功创建了一个具备基本物理交互的《愤怒的小鸟》风格游戏原型。在问题集中，你将有机会扩展这个原型，添加更多材料类型、小鸟技能和复杂的关节结构。
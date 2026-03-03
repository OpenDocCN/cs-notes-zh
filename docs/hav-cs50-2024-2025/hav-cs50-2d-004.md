# CS50 2D游戏开发：第3讲：Match 3 🧩

![](img/e8800affd520a96953ef90e4d2945527_1.png)

## 概述
在本节课中，我们将学习如何开发一款经典的“Match 3”类型游戏，例如《宝石迷阵》或《糖果粉碎传奇》。我们将重点探讨如何使用**四元组**（Quads）来管理游戏中的图块，如何利用**计时器**（Timer）和**补间动画**（Tweening）来实现平滑的动画效果，以及如何检测和处理图块匹配的逻辑。课程内容将涵盖从基础图块渲染到复杂游戏状态管理的全过程。

---

![](img/e8800affd520a96953ef90e4d2945527_3.png)

![](img/e8800affd520a96953ef90e4d2945527_5.png)

## 四元组与图块管理 🧱

![](img/e8800affd520a96953ef90e4d2945527_7.png)

上一节我们介绍了课程概述，本节中我们来看看如何利用四元组来管理和渲染游戏中的图块。

![](img/e8800affd520a96953ef90e4d2945527_9.png)

![](img/e8800affd520a96953ef90e4d2945527_10.png)

![](img/e8800affd520a96953ef90e4d2945527_12.png)

在2D游戏开发中，我们经常使用**纹理图集**（Texture Atlas），即一张包含多个小图像的大图片。为了从中绘制单个图像，我们使用**四元组**来定义纹理中的一个矩形区域。

![](img/e8800affd520a96953ef90e4d2945527_14.png)

![](img/e8800affd520a96953ef90e4d2945527_16.png)

### 基础四元组绘制
以下代码展示了如何创建一个四元组并绘制纹理的特定部分：
```lua
-- 加载纹理
local texture = love.graphics.newImage('match3.png')

![](img/e8800affd520a96953ef90e4d2945527_18.png)

![](img/e8800affd520a96953ef90e4d2945527_20.png)

![](img/e8800affd520a96953ef90e4d2945527_21.png)

-- 创建一个四元组，定义纹理中 (0,0) 到 (32,32) 的矩形区域
local quad = love.graphics.newQuad(0, 0, 32, 32, texture:getDimensions())

![](img/e8800affd520a96953ef90e4d2945527_23.png)

![](img/e8800affd520a96953ef90e4d2945527_25.png)

![](img/e8800affd520a96953ef90e4d2945527_27.png)

-- 在绘制函数中，使用四元组绘制纹理的特定部分
love.graphics.draw(texture, quad, x, y)
```

![](img/e8800affd520a96953ef90e4d2945527_29.png)

![](img/e8800affd520a96953ef90e4d2945527_31.png)

![](img/e8800affd520a96953ef90e4d2945527_32.png)

### 生成所有图块的四元组
为了管理游戏中的所有图块，我们可以编写一个函数，自动将整个纹理图集切割成多个四元组，并存储在一个表中。

以下是生成所有四元组的函数：
```lua
function generateQuads(texture, tileWidth, tileHeight)
    local sheetWidth = texture:getWidth() / tileWidth
    local sheetHeight = texture:getHeight() / tileHeight

    local quads = {}
    local quadCounter = 1

    for y = 0, sheetHeight - 1 do
        for x = 0, sheetWidth - 1 do
            quads[quadCounter] = love.graphics.newQuad(
                x * tileWidth,
                y * tileHeight,
                tileWidth,
                tileHeight,
                texture:getDimensions()
            )
            quadCounter = quadCounter + 1
        end
    end

    return quads
end
```

![](img/e8800affd520a96953ef90e4d2945527_34.png)

![](img/e8800affd520a96953ef90e4d2945527_36.png)

通过这种方式，我们可以通过索引`quads`表来访问任何图块，每个索引对应一个唯一的图块ID。

![](img/e8800affd520a96953ef90e4d2945527_38.png)

![](img/e8800affd520a96953ef90e4d2945527_40.png)

---

## 计时器与时间管理 ⏱️

![](img/e8800affd520a96953ef90e4d2945527_42.png)

上一节我们学习了如何管理图块，本节中我们来看看如何利用计时器来管理游戏中的时间事件。

![](img/e8800affd520a96953ef90e4d2945527_44.png)

![](img/e8800affd520a96953ef90e4d2945527_45.png)

![](img/e8800affd520a96953ef90e4d2945527_47.png)

![](img/e8800affd520a96953ef90e4d2945527_49.png)

在许多游戏中，我们需要在特定时间间隔执行某些操作，例如倒计时、定期生成敌人等。手动管理多个计时器会非常繁琐。因此，我们引入一个计时器库来简化这一过程。

![](img/e8800affd520a96953ef90e4d2945527_51.png)

![](img/e8800affd520a96953ef90e4d2945527_53.png)

### 使用计时器库
我们使用`knife.timer`库来管理计时器。它提供了`every`、`after`和`tween`等方法。

![](img/e8800affd520a96953ef90e4d2945527_54.png)

![](img/e8800affd520a96953ef90e4d2945527_55.png)

![](img/e8800affd520a96953ef90e4d2945527_57.png)

![](img/e8800affd520a96953ef90e4d2945527_58.png)

![](img/e8800affd520a96953ef90e4d2945527_60.png)

![](img/e8800affd520a96953ef90e4d2945527_62.png)

![](img/e8800affd520a96953ef90e4d2945527_64.png)

以下是使用计时器的示例：
```lua
Timer = require 'knife.timer'

![](img/e8800affd520a96953ef90e4d2945527_66.png)

-- 每1秒执行一次函数
Timer.every(1, function()
    print('每秒触发一次')
end)

![](img/e8800affd520a96953ef90e4d2945527_68.png)

![](img/e8800affd520a96953ef90e4d2945527_70.png)

![](img/e8800affd520a96953ef90e4d2945527_72.png)

-- 2秒后执行一次函数
Timer.after(2, function()
    print('2秒后触发')
end)
```

### 管理多个计时器
使用计时器库，我们可以轻松管理多个具有不同时间间隔的计时器，而无需手动跟踪每个计时器的状态。

![](img/e8800affd520a96953ef90e4d2945527_74.png)

![](img/e8800affd520a96953ef90e4d2945527_76.png)

![](img/e8800affd520a96953ef90e4d2945527_78.png)

以下是管理多个计时器的示例：
```lua
local intervals = {1, 2, 4}
local counters = {0, 0, 0}

![](img/e8800affd520a96953ef90e4d2945527_80.png)

![](img/e8800affd520a96953ef90e4d2945527_82.png)

![](img/e8800affd520a96953ef90e4d2945527_84.png)

for i, interval in ipairs(intervals) do
    Timer.every(interval, function()
        counters[i] = counters[i] + 1
        print('计时器 ' .. i .. ': ' .. counters[i])
    end)
end
```

![](img/e8800affd520a96953ef90e4d2945527_86.png)

在游戏的更新函数中，我们只需要调用`Timer.update(dt)`，库会自动处理所有计时器的更新。

![](img/e8800affd520a96953ef90e4d2945527_88.png)

---

![](img/e8800affd520a96953ef90e4d2945527_90.png)

![](img/e8800affd520a96953ef90e4d2945527_92.png)

![](img/e8800affd520a96953ef90e4d2945527_93.png)

![](img/e8800affd520a96953ef90e4d2945527_95.png)

![](img/e8800affd520a96953ef90e4d2945527_97.png)

## 补间动画与平滑过渡 ✨

上一节我们介绍了计时器，本节中我们来看看如何使用补间动画实现平滑的过渡效果。

![](img/e8800affd520a96953ef90e4d2945527_99.png)

![](img/e8800affd520a96953ef90e4d2945527_100.png)

![](img/e8800affd520a96953ef90e4d2945527_102.png)

![](img/e8800affd520a96953ef90e4d2945527_103.png)

![](img/e8800affd520a96953ef90e4d2945527_105.png)

![](img/e8800affd520a96953ef90e4d2945527_106.png)

补间动画是指在两个值之间进行平滑插值的过程。例如，将一个物体从位置A移动到位置B，或者将一个颜色从红色渐变到蓝色。

### 基础补间动画
以下是一个简单的补间动画示例，将物体从屏幕左侧移动到右侧：
```lua
local bird = {x = 0, y = 100}
local moveDuration = 2 -- 移动持续时间为2秒
local endX = VIRTUAL_WIDTH - 32 -- 目标X位置

![](img/e8800affd520a96953ef90e4d2945527_108.png)

![](img/e8800affd520a96953ef90e4d2945527_109.png)

![](img/e8800affd520a96953ef90e4d2945527_110.png)

![](img/e8800affd520a96953ef90e4d2945527_112.png)

Timer.tween(moveDuration, {
    [bird] = {x = endX}
})
```

![](img/e8800affd520a96953ef90e4d2945527_114.png)

![](img/e8800affd520a96953ef90e4d2945527_115.png)

![](img/e8800affd520a96953ef90e4d2945527_117.png)

### 同时补间多个属性
补间动画库允许我们同时补间对象的多个属性。例如，我们可以同时移动物体并改变其透明度。

以下是同时补间多个属性的示例：
```lua
local bird = {x = 0, y = 100, opacity = 0}
local endX = VIRTUAL_WIDTH - 32

![](img/e8800affd520a96953ef90e4d2945527_119.png)

![](img/e8800affd520a96953ef90e4d2945527_120.png)

Timer.tween(2, {
    [bird] = {x = endX, opacity = 255}
})
```

![](img/e8800affd520a96953ef90e4d2945527_122.png)

![](img/e8800affd520a96953ef90e4d2945527_123.png)

![](img/e8800affd520a96953ef90e4d2945527_125.png)

![](img/e8800affd520a96953ef90e4d2945527_126.png)

### 链式补间动画
有时我们需要按顺序执行多个补间动画。例如，先让物体移动到右侧，然后向下移动，最后返回起点。我们可以使用`finish`回调来实现链式补间。

![](img/e8800affd520a96953ef90e4d2945527_128.png)

以下是链式补间动画的示例：
```lua
Timer.tween(1, {
    [bird] = {x = VIRTUAL_WIDTH - 32}
}):finish(function()
    Timer.tween(1, {
        [bird] = {y = VIRTUAL_HEIGHT - 32}
    }):finish(function()
        Timer.tween(1, {
            [bird] = {x = 0, y = 100}
        })
    end)
end)
```

![](img/e8800affd520a96953ef90e4d2945527_130.png)

---

![](img/e8800affd520a96953ef90e4d2945527_132.png)

![](img/e8800affd520a96953ef90e4d2945527_134.png)

![](img/e8800affd520a96953ef90e4d2945527_136.png)

## 游戏板状态与交互 🎮

![](img/e8800affd520a96953ef90e4d2945527_138.png)

![](img/e8800affd520a96953ef90e4d2945527_140.png)

上一节我们实现了平滑的动画，本节中我们来看看如何创建游戏板状态并实现玩家交互。

![](img/e8800affd520a96953ef90e4d2945527_142.png)

![](img/e8800affd520a96953ef90e4d2945527_144.png)

![](img/e8800affd520a96953ef90e4d2945527_146.png)

在Match 3游戏中，我们需要一个网格来存储图块的状态，并允许玩家交换相邻的图块。

![](img/e8800affd520a96953ef90e4d2945527_148.png)

![](img/e8800affd520a96953ef90e4d2945527_150.png)

![](img/e8800affd520a96953ef90e4d2945527_151.png)

### 初始化游戏板
我们使用一个二维数组来表示游戏板，每个元素是一个图块对象，包含其网格位置、实际位置、颜色和变体等信息。

以下是初始化游戏板的代码：
```lua
function Board:init()
    self.tiles = {}
    for y = 1, 8 do
        self.tiles[y] = {}
        for x = 1, 8 do
            self.tiles[y][x] = Tile(x, y, math.random(18), math.random(6))
        end
    end
end
```

### 绘制游戏板
绘制游戏板时，我们遍历二维数组，根据每个图块的颜色和变体绘制对应的四元组。

以下是绘制游戏板的代码：
```lua
function Board:render()
    for y = 1, 8 do
        for x = 1, 8 do
            local tile = self.tiles[y][x]
            if tile then
                tile:render(self.x, self.y)
            end
        end
    end
end
```

![](img/e8800affd520a96953ef90e4d2945527_153.png)

![](img/e8800affd520a96953ef90e4d2945527_155.png)

![](img/e8800affd520a96953ef90e4d2945527_157.png)

![](img/e8800affd520a96953ef90e4d2945527_159.png)

### 交换图块
玩家可以选择两个相邻的图块进行交换。交换时，我们需要更新这两个图块在游戏板中的位置，并使用补间动画平滑移动它们。

![](img/e8800affd520a96953ef90e4d2945527_161.png)

以下是交换图块的代码：
```lua
function Board:swapTiles(tile1, tile2)
    local tempX, tempY = tile2.gridX, tile2.gridY

    -- 交换网格位置
    tile2.gridX, tile2.gridY = tile1.gridX, tile1.gridY
    tile1.gridX, tile1.gridY = tempX, tempY

    -- 交换游戏板数组中的位置
    self.tiles[tile1.gridY][tile1.gridX] = tile1
    self.tiles[tile2.gridY][tile2.gridX] = tile2

    -- 使用补间动画平滑移动图块
    Timer.tween(0.1, {
        [tile1] = {x = tile2.x, y = tile2.y},
        [tile2] = {x = tile1.x, y = tile1.y}
    })
end
```

![](img/e8800affd520a96953ef90e4d2945527_163.png)

![](img/e8800affd520a96953ef90e4d2945527_165.png)

---

## 匹配检测与处理 🔍

上一节我们实现了图块交换，本节中我们来看看如何检测和处理图块匹配。

匹配检测是Match 3游戏的核心逻辑。我们需要检查水平方向和垂直方向上是否有三个或更多相同颜色的图块连续排列。

### 水平匹配检测
以下是水平匹配检测的代码：
```lua
function Board:calculateMatches()
    local matches = {}

    -- 检查水平匹配
    for y = 1, 8 do
        local colorToMatch = self.tiles[y][1].color
        local matchLength = 1

        for x = 2, 8 do
            if self.tiles[y][x].color == colorToMatch then
                matchLength = matchLength + 1
            else
                if matchLength >= 3 then
                    local match = {}
                    for x2 = x - matchLength, x - 1 do
                        table.insert(match, self.tiles[y][x2])
                    end
                    table.insert(matches, match)
                end

                colorToMatch = self.tiles[y][x].color
                matchLength = 1
            end
        end

        -- 检查行末的匹配
        if matchLength >= 3 then
            local match = {}
            for x = 9 - matchLength, 8 do
                table.insert(match, self.tiles[y][x])
            end
            table.insert(matches, match)
        end
    end

    return matches
end
```

![](img/e8800affd520a96953ef90e4d2945527_167.png)

### 垂直匹配检测
垂直匹配检测的逻辑与水平检测类似，只是遍历的方向不同。我们需要遍历每一列，检查垂直方向上的连续图块。

### 处理匹配
检测到匹配后，我们需要移除匹配的图块，并让上方的图块下落填充空缺，然后在顶部生成新的图块。

以下是处理匹配的代码：
```lua
function Board:removeMatches()
    local matches = self:calculateMatches()

    for _, match in ipairs(matches) do
        for _, tile in ipairs(match) do
            self.tiles[tile.gridY][tile.gridX] = nil
        end
    end

    self:applyGravity()
    self:refillTiles()
end
```

### 应用重力
应用重力是指让上方的图块下落填充下方的空缺。我们从每列的底部向上遍历，寻找空缺并填充。

以下是应用重力的代码：
```lua
function Board:applyGravity()
    for x = 1, 8 do
        local spaceY = nil
        for y = 8, 1, -1 do
            local tile = self.tiles[y][x]
            if not tile then
                if not spaceY then
                    spaceY = y
                end
            elseif spaceY then
                tile.gridY = spaceY
                self.tiles[spaceY][x] = tile
                self.tiles[y][x] = nil
                spaceY = spaceY - 1
            end
        end
    end
end
```

### 补充新图块
补充新图块时，我们在每列的顶部生成新的图块，并使用补间动画让它们从上方滑入。

以下是补充新图块的代码：
```lua
function Board:refillTiles()
    for x = 1, 8 do
        for y = 1, 8 do
            if not self.tiles[y][x] then
                local tile = Tile(x, y, math.random(18), math.random(6))
                tile.y = -32
                self.tiles[y][x] = tile

                Timer.tween(0.5, {
                    [tile] = {y = (y - 1) * 32}
                })
            end
        end
    end
end
```

---

## 游戏状态与过渡 🚀

上一节我们完成了匹配检测与处理，本节中我们来看看如何管理游戏状态并实现平滑的过渡效果。

在游戏中，我们通常有多个状态，例如开始界面、游戏界面、结束界面等。我们可以使用状态机来管理这些状态，并使用补间动画实现状态之间的平滑过渡。

### 状态机
我们使用一个简单的状态机来管理游戏状态。每个状态都是一个对象，包含`enter`、`exit`、`update`和`render`等方法。

![](img/e8800affd520a96953ef90e4d2945527_169.png)

以下是状态机的简化实现：
```lua
function StateMachine:change(state, params)
    if self.currentState and self.currentState.exit then
        self.currentState:exit()
    end

    self.currentState = state
    if self.currentState.enter then
        self.currentState:enter(params)
    end
end
```

![](img/e8800affd520a96953ef90e4d2945527_171.png)

![](img/e8800affd520a96953ef90e4d2945527_173.png)

### 过渡效果
为了实现状态之间的平滑过渡，我们可以在状态切换时使用一个全屏的白色矩形，通过改变其透明度来实现淡入淡出效果。

![](img/e8800affd520a96953ef90e4d2945527_175.png)

以下是开始状态到游戏状态的过渡代码：
```lua
function StartState:enter(params)
    self.transitionAlpha = 0

    Timer.tween(1, {
        [self] = {transitionAlpha = 1}
    }):finish(function()
        gStateMachine:change(BeginGameState)
    end)
end
```

在游戏状态中，我们执行相反的过渡，从白色淡出到游戏画面：
```lua
function BeginGameState:enter(params)
    self.transitionAlpha = 1

    Timer.tween(1, {
        [self] = {transitionAlpha = 0}
    }):finish(function()
        -- 开始游戏逻辑
    end)
end
```

![](img/e8800affd520a96953ef90e4d2945527_177.png)

在渲染函数中，我们根据`transitionAlpha`绘制半透明白色矩形：
```lua
function BeginGameState:render()
    -- 渲染游戏内容
    love.graphics.setColor(1, 1, 1, self.transitionAlpha)
    love.graphics.rectangle('fill', 0, 0, VIRTUAL_WIDTH, VIRTUAL_HEIGHT)
    love.graphics.setColor(1, 1, 1, 1)
end
```

---

## 总结 🎯

本节课中我们一起学习了如何开发一款Match 3游戏。我们从基础的四元组和图块管理开始，逐步实现了计时器管理、补间动画、游戏板状态与交互、匹配检测与处理，以及游戏状态与平滑过渡。

通过本课程，你掌握了以下核心概念：
1. 使用四元组管理和渲染纹理图集中的图块。
2. 利用计时器库管理游戏中的时间事件。
3. 使用补间动画实现平滑的动画和过渡效果。
4. 创建和交互游戏板状态。
5. 检测和处理图块匹配。
6. 管理游戏状态并实现状态间的平滑过渡。

![](img/e8800affd520a96953ef90e4d2945527_179.png)

![](img/e8800affd520a96953ef90e4d2945527_181.png)

这些概念不仅适用于Match 3游戏，也是2D游戏开发中的通用技术。希望你能将这些知识应用到自己的游戏项目中，创造出有趣和精美的游戏体验。
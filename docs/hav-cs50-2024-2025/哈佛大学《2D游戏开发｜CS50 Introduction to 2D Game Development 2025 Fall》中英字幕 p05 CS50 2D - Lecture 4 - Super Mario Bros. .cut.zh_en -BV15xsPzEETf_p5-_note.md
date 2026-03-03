# CS50 2D游戏开发：第4讲：超级马里奥兄弟 🍄

## 概述
在本节课中，我们将学习如何构建一个类似《超级马里奥兄弟》的2D平台游戏。我们将探讨瓦片地图、2D动画、程序化关卡生成、平台游戏物理、简单的敌人AI以及如何实现道具系统。通过本教程，你将学会如何创建一个拥有可交互世界、移动角色和动态关卡的游戏。

---

![](img/67713fb931a2f422757f860cc32b6d07_1.png)

## 瓦片地图基础 🧱

![](img/67713fb931a2f422757f860cc32b6d07_3.png)

上一节我们介绍了课程概述，本节中我们来看看如何构建游戏世界的基础——瓦片地图。

![](img/67713fb931a2f422757f860cc32b6d07_5.png)

瓦片地图是一种使用网格和预定义图像块（瓦片）来构建游戏关卡的技术。每个网格单元对应一个瓦片ID，这个ID决定了该位置绘制什么图像以及是否可碰撞。

![](img/67713fb931a2f422757f860cc32b6d07_7.png)

![](img/67713fb931a2f422757f860cc32b6d07_9.png)

在《超级马里奥兄弟》中，地面、砖块和背景元素都是通过瓦片地图来绘制的。

### 核心概念与代码
我们首先创建一个简单的静态瓦片地图。以下代码定义了一个瓦片网格，并绘制了“天空”和“地面”两种瓦片。

![](img/67713fb931a2f422757f860cc32b6d07_11.png)

![](img/67713fb931a2f422757f860cc32b6d07_13.png)

```lua
-- 定义常量
TILE_SIZE = 16
SKY = 1
GROUND = 2

![](img/67713fb931a2f422757f860cc32b6d07_15.png)

-- 初始化瓦片网格
local tiles = {}
for y = 1, MAP_HEIGHT do
    tiles[y] = {}
    for x = 1, MAP_WIDTH do
        -- 第七行开始是地面
        tiles[y][x] = y >= 7 and GROUND or SKY
    end
end

![](img/67713fb931a2f422757f860cc32b6d07_17.png)

-- 绘制瓦片地图
function drawMap()
    for y = 1, #tiles do
        for x = 1, #tiles[y] do
            local tileId = tiles[y][x]
            local quad = tileQuads[tileId] -- 获取对应的图像块
            love.graphics.draw(tilesheet, quad, (x-1)*TILE_SIZE, (y-1)*TILE_SIZE)
        end
    end
end
```

![](img/67713fb931a2f422757f860cc32b6d07_19.png)

![](img/67713fb931a2f422757f860cc32b6d07_20.png)

![](img/67713fb931a2f422757f860cc32b6d07_22.png)

![](img/67713fb931a2f422757f860cc32b6d07_24.png)

![](img/67713fb931a2f422757f860cc32b6d07_26.png)

---

![](img/67713fb931a2f422757f860cc32b6d07_28.png)

## 实现摄像机滚动 📹

![](img/67713fb931a2f422757f860cc32b6d07_30.png)

上一节我们创建了静态地图，本节中我们来看看如何让地图动起来，实现摄像机的跟随效果。

![](img/67713fb931a2f422757f860cc32b6d07_32.png)

![](img/67713fb931a2f422757f860cc32b6d07_34.png)

![](img/67713fb931a2f422757f860cc32b6d07_36.png)

为了让玩家感觉在世界中移动，我们需要一个可以滚动的摄像机。这可以通过平移整个绘制坐标系来实现。

![](img/67713fb931a2f422757f860cc32b6d07_38.png)

![](img/67713fb931a2f422757f860cc32b6d07_40.png)

![](img/67713fb931a2f422757f860cc32b6d07_41.png)

![](img/67713fb931a2f422757f860cc32b6d07_43.png)

### 核心概念与公式
我们使用一个变量 `cameraScroll` 来跟踪摄像机的水平偏移。在绘制前，我们使用 `love.graphics.translate(-cameraScroll, 0)` 来偏移所有后续的绘制操作。

![](img/67713fb931a2f422757f860cc32b6d07_45.png)

**公式**：`绘制坐标 = 世界坐标 - 摄像机偏移`

![](img/67713fb931a2f422757f860cc32b6d07_47.png)

![](img/67713fb931a2f422757f860cc32b6d07_49.png)

```lua
local cameraScroll = 0
local CAMERA_SCROLL_SPEED = 100

![](img/67713fb931a2f422757f860cc32b6d07_51.png)

![](img/67713fb931a2f422757f860cc32b6d07_53.png)

![](img/67713fb931a2f422757f860cc32b6d07_55.png)

function love.update(dt)
    -- 根据输入更新摄像机偏移（例如，按右键）
    if love.keyboard.isDown('right') then
        cameraScroll = cameraScroll + CAMERA_SCROLL_SPEED * dt
    end
end

function love.draw()
    -- 应用摄像机平移
    love.graphics.translate(-math.floor(cameraScroll), 0)
    -- 绘制瓦片地图和其他游戏对象
    drawMap()
    drawPlayer()
end
```

---

## 创建与动画化角色 🏃

上一节我们实现了可滚动的世界，本节中我们来看看如何将玩家角色放入这个世界，并让它动起来。

![](img/67713fb931a2f422757f860cc32b6d07_57.png)

我们需要一个可以被玩家控制并能在屏幕上移动的角色。这包括处理输入、更新位置以及根据状态播放不同的动画（如站立、行走、跳跃）。

![](img/67713fb931a2f422757f860cc32b6d07_59.png)

![](img/67713fb931a2f422757f860cc32b6d07_61.png)

### 角色状态与动画
以下是管理角色动画状态的核心逻辑：

![](img/67713fb931a2f422757f860cc32b6d07_63.png)

```lua
-- 定义动画类
Animation = {}
function Animation:new(frames, interval)
    local this = {
        frames = frames,        -- 帧ID列表
        interval = interval,    -- 帧切换间隔（秒）
        timer = 0,
        currentFrame = 1
    }
    return this
end

![](img/67713fb931a2f422757f860cc32b6d07_65.png)

![](img/67713fb931a2f422757f860cc32b6d07_67.png)

function Animation:update(dt)
    if #self.frames > 1 then
        self.timer = self.timer + dt
        if self.timer > self.interval then
            self.timer = self.timer % self.interval
            self.currentFrame = (self.currentFrame % #self.frames) + 1
        end
    end
    return self.frames[self.currentFrame]
end

-- 在玩家类中使用动画
player.animations = {
    idle = Animation:new({1}, 1),          -- 站立帧
    walking = Animation:new({10, 11}, 0.2), -- 行走帧，每0.2秒切换
    jumping = Animation:new({3}, 1)        -- 跳跃帧
}
player.currentAnimation = player.animations.idle
```

---

## 实现跳跃与重力 ⬆️

上一节我们让角色可以行走，本节中我们来看看如何实现平台游戏的核心机制：跳跃。

![](img/67713fb931a2f422757f860cc32b6d07_69.png)

跳跃通过给角色一个向上的初始速度，并持续施加向下的重力来模拟。我们还需要检测角色何时落地，以允许再次起跳。

![](img/67713fb931a2f422757f860cc32b6d07_71.png)

### 物理模拟
跳跃的物理过程可以用以下简化的运动公式来描述：

**公式**：
* 速度更新：`dy = dy + GRAVITY * dt`
* 位置更新：`y = y + dy * dt`
* 起跳：`dy = JUMP_VELOCITY` （一个负值）

![](img/67713fb931a2f422757f860cc32b6d07_73.png)

![](img/67713fb931a2f422757f860cc32b6d07_75.png)

![](img/67713fb931a2f422757f860cc32b6d07_77.png)

```lua
local GRAVITY = 980
local JUMP_VELOCITY = -300
player.dy = 0 -- Y轴速度
player.onGround = false

function player:update(dt)
    -- 应用重力
    self.dy = self.dy + GRAVITY * dt
    self.y = self.y + self.dy * dt

    -- 检测落地（简化版，假设地面在 y = 某值）
    if self.y >= GROUND_LEVEL then
        self.y = GROUND_LEVEL
        self.dy = 0
        self.onGround = true
    end

    -- 跳跃输入检测
    if love.keyboard.isDown('space') and self.onGround then
        self.dy = JUMP_VELOCITY
        self.onGround = false
        self.currentAnimation = self.animations.jumping
    end
end
```

![](img/67713fb931a2f422757f860cc32b6d07_79.png)

![](img/67713fb931a2f422757f860cc32b6d07_81.png)

---

![](img/67713fb931a2f422757f860cc32b6d07_83.png)

![](img/67713fb931a2f422757f860cc32b6d07_85.png)

![](img/67713fb931a2f422757f860cc32b6d07_87.png)

## 程序化关卡生成 🎲

![](img/67713fb931a2f422757f860cc32b6d07_89.png)

![](img/67713fb931a2f422757f860cc32b6d07_91.png)

上一节我们实现了基本的角色运动，本节中我们来看看如何自动生成多样化的游戏关卡，而不是手动设计每一个。

![](img/67713fb931a2f422757f860cc32b6d07_93.png)

程序化关卡生成通过算法随机创建关卡布局。我们可以定义规则，例如地面的基础高度、随机生成支柱和沟壑的概率，以及放置装饰物和可交互物体。

![](img/67713fb931a2f422757f860cc32b6d07_95.png)

![](img/67713fb931a2f422757f860cc32b6d07_97.png)

![](img/67713fb931a2f422757f860cc32b6d07_98.png)

### 生成算法步骤
以下是生成一个简单关卡的逻辑流程：

1.  初始化一个充满“天空”瓦片的网格。
2.  从左到右遍历每一列。
3.  对于每一列，有一定概率生成一个“支柱”（将地面起始行提高）。
4.  有一定概率生成一个“沟壑”（跳过该列的地面生成）。
5.  在生成的地面顶部，放置“顶部装饰”瓦片。
6.  随机在地面或支柱上放置装饰物（如灌木丛）或可交互物体（如砖块）。

```lua
function generateLevel(width, height)
    local tiles = {}
    local objects = {}
    -- 1. 用天空填充
    for y = 1, height do
        tiles[y] = {}
        for x = 1, width do
            tiles[y][x] = {id = SKY_ID, topper = false}
        end
    end

    -- 2. 生成地形
    for x = 1, width do
        local groundHeight = 7 -- 默认地面高度
        -- 3. 随机决定是否生成支柱
        if math.random(5) == 1 then
            groundHeight = 4
        end
        -- 4. 随机决定是否生成沟壑
        if math.random(7) == 1 then
            goto continue -- 跳过这一列
        end

        -- 5. 从 groundHeight 到地图底部填充地面
        for y = groundHeight, height do
            tiles[y][x].id = GROUND_ID
            if y == groundHeight then
                tiles[y][x].topper = true -- 顶部瓦片
            end
        end

        -- 6. 在支柱顶部随机放置灌木丛
        if groundHeight == 4 and math.random(8) == 1 then
            table.insert(objects, GameObject:new({
                type = 'bush',
                x = (x-1) * TILE_SIZE,
                y = (groundHeight-2) * TILE_SIZE -- 放在支柱上方
            }))
        end
        ::continue::
    end
    return tiles, objects
end
```

---

## 平台游戏碰撞检测 🚧

上一节我们生成了关卡，本节中我们来看看如何让角色与这个关卡世界进行交互，即碰撞检测。

与之前使用的AABB（轴对齐边界框）碰撞不同，在基于瓦片的平台游戏中，我们通常将角色的关键点（如四个角）映射到瓦片网格，只检查这些点所在的瓦片是否可碰撞。这种方法效率更高。

### 点对瓦片检测
核心函数是将像素坐标转换为瓦片网格坐标：

```lua
function pointToTile(x, y)
    -- 将像素坐标转换为网格索引（Lua索引从1开始）
    local tileX = math.floor(x / TILE_SIZE) + 1
    local tileY = math.floor(y / TILE_SIZE) + 1
    -- 检查边界，然后返回该位置的瓦片
    if tileY >= 1 and tileY <= #map.tiles and tileX >= 1 and tileX <= #map.tiles[1] then
        return map.tiles[tileY][tileX]
    end
    return nil -- 坐标在地图外
end

-- 在玩家状态中检查左侧碰撞
function PlayerWalkingState:checkLeftCollision()
    -- 检查左上角和左下角
    local topLeftTile = pointToTile(self.player.x, self.player.y + 1)
    local bottomLeftTile = pointToTile(self.player.x, self.player.y + self.player.height - 1)

    -- 如果任一瓦片是固体（如地面）
    if (topLeftTile and topLeftTile.id == GROUND_ID) or
       (bottomLeftTile and bottomLeftTile.id == GROUND_ID) then
        -- 将玩家推到瓦片右侧
        self.player.x = (math.floor(self.player.x / TILE_SIZE) + 1) * TILE_SIZE
    end
end
```

---

## 实体、状态与游戏对象 🐌

上一节我们处理了与静态世界的碰撞，本节中我们来看看游戏中的动态元素：实体和游戏对象。

*   **实体**：具有行为、状态并能在世界中移动的对象，如玩家和敌人（蜗牛）。它们通常拥有自己的状态机（如“空闲”、“行走”、“跳跃”）。
*   **游戏对象**：静态或具有简单交互的对象，如可收集的宝石、可撞击的砖块。它们通常没有复杂的状态机，但可以有碰撞回调函数。

### 实体状态机
玩家实体可能的状态转换如下：

![](img/67713fb931a2f422757f860cc32b6d07_100.png)

```lua
PlayerStateMachine = StateMachine:new({
    ['idle'] = function() return PlayerIdleState end,
    ['walking'] = function() return PlayerWalkingState end,
    ['jumping'] = function() return PlayerJumpingState end,
    ['falling'] = function() return PlayerFallingState end
})

-- 在玩家更新逻辑中
function Player:update(dt)
    self.stateMachine:update(dt)
    -- 状态机内部会根据输入和条件切换当前状态
    -- 例如，在 IdleState 中按右箭头键会切换到 WalkingState
end
```

![](img/67713fb931a2f422757f860cc32b6d07_102.png)

### 游戏对象交互
砖块游戏对象在被顶撞时的行为：

```lua
-- 创建砖块对象
local block = GameObject:new({
    x = ...,
    y = ...,
    texture = ...,
    solid = true,
    onCollide = function(obj, player)
        -- 如果还没被顶过
        if not obj.wasHit then
            obj.wasHit = true
            -- 20% 几率生成宝石
            if math.random(5) == 1 then
                local gem = GameObject:new({
                    type = 'gem',
                    x = obj.x,
                    y = obj.y - TILE_SIZE,
                    consumable = true,
                    onConsume = function(gem, player)
                        player.score = player.score + 100
                        playSound('gem-collect')
                    end
                })
                table.insert(level.objects, gem)
            end
            playSound('block-hit')
        end
    end
})
```

---

## 敌人AI与行为模式 🤖

上一节我们区分了实体和对象，本节中我们以蜗牛敌人为例，看看如何为实体赋予简单的AI行为。

我们可以为敌人设计几种行为状态，例如“空闲”、“随机移动”和“追逐玩家”。状态之间根据条件（如时间、与玩家的距离）进行切换。

### 蜗牛AI状态
以下是蜗牛敌人可能的状态逻辑：

```lua
-- 蜗牛追逐状态
SnailChasingState = {}
function SnailChasingState:update(dt)
    local snail = self.entity
    local player = self.player

    -- 计算与玩家的水平距离
    local diffX = player.x - snail.x

    -- 如果玩家在5个瓦片范围内，则朝玩家移动
    if math.abs(diffX) < 5 * TILE_SIZE then
        if diffX > 0 then
            snail.dx = SNAIL_MOVE_SPEED
        else
            snail.dx = -SNAIL_MOVE_SPEED
        end
    else
        -- 距离太远，切换回随机移动状态
        snail.stateMachine:change('moving')
    end
end

-- 蜗牛移动状态（随机移动）
SnailMovingState = {}
function SnailMovingState:update(dt)
    local snail = self.entity
    self.moveTimer = self.moveTimer - dt

    if self.moveTimer <= 0 then
        -- 随机选择一个新的移动方向和时间
        snail.dx = math.random(2) == 1 and SNAIL_MOVE_SPEED or -SNAIL_MOVE_SPEED
        self.moveTimer = math.random(1, 3) -- 移动1到3秒
        -- 有1/4几率进入空闲状态
        if math.random(4) == 1 then
            snail.stateMachine:change('idle')
        end
    end
end
```

---

![](img/67713fb931a2f422757f860cc32b6d07_104.png)

## 总结

本节课中我们一起学习了构建一个2D平台游戏《超级马里奥兄弟》克隆版的核心技术。

我们从**瓦片地图**开始，构建了游戏世界的基础。通过实现**摄像机滚动**，让世界能够跟随角色移动。我们创建了可动画化的**玩家角色**，并为其加入了**跳跃与重力**物理，实现了平台游戏的核心操作。

![](img/67713fb931a2f422757f860cc32b6d07_106.png)

![](img/67713fb931a2f422757f860cc32b6d07_107.png)

为了创造无限的可玩性，我们探讨了**程序化关卡生成**算法，用于自动创建包含支柱、沟壑和装饰物的关卡。我们学习了针对瓦片地图高效的**碰撞检测**方法（点对瓦片检测）。

最后，我们区分了游戏中的动态元素**实体**（如玩家、敌人）和静态交互元素**游戏对象**（如砖块、宝石），并为敌人实现了简单的**AI行为状态机**。

![](img/67713fb931a2f422757f860cc32b6d07_109.png)

![](img/67713fb931a2f422757f860cc32b6d07_111.png)

这些概念共同构成了一个动态、可交互的2D游戏世界，为后续更复杂的游戏开发打下了坚实的基础。
# 133：配置文件定位与jQuery代码详解 🧩

在本节课中，我们将详细讲解如何构建一个带有个人资料和职位信息的自动评分系统。课程的核心是学习如何使用jQuery动态地添加和删除表单字段，并理解如何将这些数据存储到数据库中，特别是处理“一对多”的关系。

![](img/ab0a38ad2a20a9752f92b61c1a199f4e_1.png)

![](img/ab0a38ad2a20a9752f92b61c1a199f4e_2.png)

## 概述

上一节我们完成了基本的用户登录和个人资料管理功能。本节中，我们将在此基础上，为个人资料添加多个职位信息。我们将使用jQuery来动态管理表单，并学习如何在数据库中建立“一对多”的关系。

## 代码结构与数据库设计

首先，我们需要在数据库中创建一个新的`position`表。这个表将与之前创建的`profile`表建立关联。

以下是创建`position`表的核心SQL概念：
```sql
CREATE TABLE position (
    position_id INTEGER NOT NULL AUTO_INCREMENT,
    profile_id INTEGER,
    year INTEGER,
    description TEXT,
    rank INTEGER,
    PRIMARY KEY(position_id),
    CONSTRAINT position_ibfk_1
        FOREIGN KEY (profile_id)
        REFERENCES profile (profile_id)
        ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```
这个表通过`profile_id`字段与`profile`表关联，一个个人资料可以对应多个职位，这就是“一对多”关系。

## 核心功能实现

### 1. 登录与基础框架

登录功能与上一节相同，它检查用户表，并使用SQL查询和密码哈希验证用户身份。为了代码复用和整洁，我们将一些常用功能（如显示提示信息）提取到了`util.php`文件中。

### 2. 添加职位功能 (`add.php`)

这是本课的重点。表单允许用户为一个个人资料添加多个职位。

以下是表单中动态添加职位字段的jQuery代码核心逻辑：
```javascript
$(document).ready(function(){
    $('#addPos').click(function(event){
        event.preventDefault();
        if (countPos >= 9) {
            alert("Maximum of nine position entries exceeded");
            return;
        }
        countPos++;
        window.console && console.log("Adding position "+countPos);
        $('#position_fields').append(
            '<div id="position'+countPos+'"> \
            <p>Year: <input type="text" name="year'+countPos+'" value="" /> \
            <input type="button" value="-" \
                onclick="$(\'#position'+countPos+'\').remove();return false;"></p> \
            <textarea name="desc'+countPos+'" rows="8" cols="80"></textarea>\
            </div>');
    });
});
```
*   **功能**：当用户点击“+”按钮时，这段代码会动态生成包含年份输入框、描述文本框和“-”删除按钮的HTML块，并将其插入到页面中。
*   **变量 `countPos`**：用于跟踪已添加的职位字段数量，并限制最多添加9个。
*   **删除功能**：每个动态添加的字段都自带一个“-”按钮，其`onclick`事件会移除对应的整个字段`div`。

### 3. 数据验证 (`util.php`)

提交表单时，我们需要验证所有动态添加的职位字段。

以下是验证职位数据的PHP函数核心逻辑：
```php
function validatePos() {
    for($i=1; $i<=9; $i++) {
        if ( ! isset($_POST['year'.$i]) ) continue;
        if ( ! isset($_POST['desc'.$i]) ) continue;
        $year = $_POST['year'.$i];
        $desc = $_POST['desc'.$i];
        if ( strlen($year) == 0 || strlen($desc) == 0 ) {
            return "All fields are required";
        }
        if ( ! is_numeric($year) ) {
            return "Position year must be numeric";
        }
    }
    return true;
}
```
*   **循环检查**：函数循环检查可能存在的`year1`到`year9`以及对应的`desc1`到`desc9`字段。
*   **验证逻辑**：检查字段是否存在、是否为空，以及年份是否为数字。
*   **返回值**：验证通过返回`true`，失败则返回错误信息字符串。这种利用PHP动态类型返回混合结果的方式很常见。

### 4. 数据存储逻辑

当验证通过后，代码会执行以下操作：
1.  首先插入`profile`表的数据，并获取自动生成的主键`profile_id`。
2.  然后循环处理每个有效的职位字段，将其插入`position`表。**关键点**：在插入职位记录时，需要将上一步获取的`profile_id`作为外键存入，从而建立关联。
3.  `rank`字段用于确保职位在显示时保持用户添加的顺序。

### 5. 编辑功能 (`edit.php`)

编辑功能比添加更复杂一些，因为它需要预先加载已有的职位数据。

*   **加载现有数据**：通过`loadPos($pdo, $profile_id)`函数从数据库读取指定个人资料的所有职位，并在表单中动态生成对应的HTML字段进行展示。
*   **保存策略**：为了简化逻辑，编辑保存时采用了一种“先删除，后重新插入”的策略。即先删除该`profile_id`对应的所有旧职位记录，然后再将表单中当前所有的职位数据作为新记录插入。这样就能统一处理修改、删除和新增操作，代码可以复用添加时的插入逻辑。
*   **重要细节**：在验证失败或处理完成后进行页面重定向时，必须将当前编辑的`profile_id`作为GET参数传递回去（例如`Location: edit.php?profile_id=123`），否则页面会丢失正在编辑的是哪条记录。

## 总结

![](img/ab0a38ad2a20a9752f92b61c1a199f4e_4.png)

![](img/ab0a38ad2a20a9752f92b61c1a199f4e_5.png)

本节课中我们一起学习了如何扩展个人资料系统以支持多个职位信息。我们掌握了使用jQuery动态操作DOM来增加表单交互性，深入理解了数据库“一对多”关系的实现方式，并通过PHP代码将前后端逻辑串联起来。关键点包括：动态字段的生成与删除、前后端结合的数据验证、利用外键建立数据关联，以及在编辑功能中采用简化逻辑的数据更新策略。通过本课，你构建的Web应用功能变得更加丰富和实用。
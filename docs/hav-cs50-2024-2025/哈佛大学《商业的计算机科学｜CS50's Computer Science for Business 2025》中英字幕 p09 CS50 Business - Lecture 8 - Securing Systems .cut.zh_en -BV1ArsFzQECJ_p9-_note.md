# 商业的计算机科学：第8讲：系统安全 🔐

![](img/fb8f024423da279c5a8671bafebdcc5d_1.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_2.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_3.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_4.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_6.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_7.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_8.png)

在本节课中，我们将要学习系统安全的核心概念，包括身份验证、授权、密码安全、加密技术以及如何防御常见的攻击。我们将通过简单的例子和代码来理解这些概念，并探讨如何在实践中应用最佳安全实践。

---

![](img/fb8f024423da279c5a8671bafebdcc5d_10.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_11.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_12.png)

## 身份验证与授权 🔑

上一节我们介绍了课程概述，本节中我们来看看系统安全的两个基本原语：身份验证和授权。

![](img/fb8f024423da279c5a8671bafebdcc5d_14.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_15.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_16.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_18.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_19.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_20.png)

身份验证是证明你是谁的过程，例如通过用户名和密码登录。授权则是在你通过身份验证后，确定你可以访问哪些资源，不可以访问哪些资源。

![](img/fb8f024423da279c5a8671bafebdcc5d_21.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_23.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_24.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_25.png)

在现实世界中，我们经常通过密码进行身份验证。然而，人类并不擅长选择好的密码。安全研究人员通过分析泄露的密码数据库，总结出了最常见的密码列表。

![](img/fb8f024423da279c5a8671bafebdcc5d_27.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_28.png)

以下是安全研究人员发现的最常见的10个密码示例：

![](img/fb8f024423da279c5a8671bafebdcc5d_30.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_31.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_32.png)

*   123456
*   123456789
*   password
*   password1
*   qwerty
*   Qwerty123
*   111111
*   123123
*   iloveyou
*   P@ssw0rd

![](img/fb8f024423da279c5a8671bafebdcc5d_34.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_36.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_37.png)

这些密码的共同点是过于简单、可预测或使用了常见的替换模式（如用`@`代替`a`，用`0`代替`o`）。攻击者会首先尝试这些常见密码来入侵账户。因此，你的密码不应出现在此类列表中。

![](img/fb8f024423da279c5a8671bafebdcc5d_39.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_40.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_41.png)

---

![](img/fb8f024423da279c5a8671bafebdcc5d_43.png)

## 暴力破解攻击 💥

![](img/fb8f024423da279c5a8671bafebdcc5d_45.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_46.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_47.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_49.png)

上一节我们了解了弱密码的风险，本节中我们来看看攻击者如何利用“暴力破解”来攻击系统。

![](img/fb8f024423da279c5a8671bafebdcc5d_51.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_52.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_53.png)

暴力破解攻击是指尝试所有可能的密码组合，直到找到正确的那个。我们可以通过计算密码的可能组合数量来衡量一个系统的安全性。

![](img/fb8f024423da279c5a8671bafebdcc5d_55.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_56.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_58.png)

例如，一个4位数字密码（每位0-9）的可能组合数为：
`10 * 10 * 10 * 10 = 10,000`

对于一个4位字母密码（区分大小写，共52个字母），可能组合数为：
`52 * 52 * 52 * 52 = 7,311,616`

![](img/fb8f024423da279c5a8671bafebdcc5d_60.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_61.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_62.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_64.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_65.png)

对于一个4位字符密码（包含字母、数字和标点，共94个字符），可能组合数为：
`94 * 94 * 94 * 94 = 78,074,896`

![](img/fb8f024423da279c5a8671bafebdcc5d_67.png)

对于一个8位字符密码，可能组合数将是一个天文数字：
`94^8 ≈ 6,095,689,385,410,816`

我们可以用Python编写一个简单的程序来演示暴力破解一个4位数字密码是多么快速。

![](img/fb8f024423da279c5a8671bafebdcc5d_69.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_70.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_71.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_72.png)

```python
from string import digits
from itertools import product

![](img/fb8f024423da279c5a8671bafebdcc5d_74.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_75.png)

for passcode in product(digits, repeat=4):
    print(''.join(passcode))
```

![](img/fb8f024423da279c5a8671bafebdcc5d_77.png)

这段代码会快速输出从`0000`到`9999`的所有组合。在实际攻击中，程序会将每个组合尝试输入目标系统。

![](img/fb8f024423da279c5a8671bafebdcc5d_79.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_80.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_82.png)

虽然更长的密码（如8位字符）在理论上需要极长的时间才能破解（例如，以每秒尝试一次的速度需要数百万年），但这建立在密码完全随机且攻击未被限制的基础上。

![](img/fb8f024423da279c5a8671bafebdcc5d_84.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_85.png)

---

![](img/fb8f024423da279c5a8671bafebdcc5d_87.png)

## 防御措施 🛡️

![](img/fb8f024423da279c5a8671bafebdcc5d_89.png)

上一节我们看到了暴力破解的威力，本节中我们来看看如何防御此类攻击。

![](img/fb8f024423da279c5a8671bafebdcc5d_91.png)

一种有效的防御措施是**速率限制**。例如，系统可以在用户连续输错10次密码后，锁定账户1分钟，再次失败后锁定时间更长。这极大地增加了攻击者的时间和风险成本，使他们很可能放弃攻击。

![](img/fb8f024423da279c5a8671bafebdcc5d_93.png)

另一个关键防御是使用**密码管理器**。密码管理器是一个软件，可以为你生成并存储高强度、随机的唯一密码。你只需要记住一个主密码即可访问管理器内的所有密码。这解决了密码复用和记忆难题，虽然将“所有鸡蛋放在一个篮子里”，但总体上比使用弱密码或重复密码更安全。

![](img/fb8f024423da279c5a8671bafebdcc5d_95.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_96.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_98.png)

此外，**双因素认证**要求用户在输入密码之外，提供第二个验证因素（通常是手机接收的一次性验证码）。这样即使密码泄露，攻击者也需要物理上持有你的设备才能登录，大大降低了风险。

![](img/fb8f024423da279c5a8671bafebdcc5d_100.png)

---

![](img/fb8f024423da279c5a8671bafebdcc5d_102.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_103.png)

## 密码存储与哈希 🔒

![](img/fb8f024423da279c5a8671bafebdcc5d_105.png)

上一节我们讨论了用户端的防御，本节中我们来看看服务器端应如何安全地存储密码。

![](img/fb8f024423da279c5a8671bafebdcc5d_107.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_109.png)

最佳实践是服务器不应明文存储密码，而应存储密码的**哈希值**。哈希函数是一种单向算法，能将任意长度的输入（如密码）转换成固定长度的、看似随机的字符串（哈希值）。理想情况下，无法从哈希值反推出原始密码。

![](img/fb8f024423da279c5a8671bafebdcc5d_111.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_113.png)

例如，密码 `apple` 经过哈希函数可能变成 `1f3870be...`，而 `banana` 则变成 `72b302bf...`。

![](img/fb8f024423da279c5a8671bafebdcc5d_114.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_116.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_117.png)

然而，简单的哈希存储仍可能受到**彩虹表攻击**。攻击者会预先计算大量常见密码的哈希值并制成表格，然后直接查表匹配窃取的哈希值。

为了抵御这种攻击，可以采用**加盐哈希**。盐是一个随机字符串，在哈希前与密码拼接。每个用户的盐都不同，并随哈希值一起存储。即使两个用户密码相同，由于盐不同，其哈希值也完全不同。

![](img/fb8f024423da279c5a8671bafebdcc5d_119.png)

验证密码时，服务器取出该用户对应的盐，将其与用户输入的密码拼接，计算哈希值，然后与存储的哈希值比对。

![](img/fb8f024423da279c5a8671bafebdcc5d_121.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_122.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_124.png)

---

![](img/fb8f024423da279c5a8671bafebdcc5d_126.png)

## 加密技术 📡

![](img/fb8f024423da279c5a8671bafebdcc5d_128.png)

上一节我们探讨了哈希，本节中我们来看看更通用的信息保护技术——加密。

![](img/fb8f024423da279c5a8671bafebdcc5d_130.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_132.png)

**加密**是将明文转换为密文（看似随机的数据）的过程，而**解密**是其逆过程。这需要使用密钥。

![](img/fb8f024423da279c5a8671bafebdcc5d_134.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_135.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_136.png)

**对称加密**使用同一个密钥进行加密和解密。例如，凯撒密码就是一种简单的对称加密，将每个字母在字母表上偏移固定的位置（密钥）。其挑战在于，通信双方需要提前安全地共享同一把密钥。

![](img/fb8f024423da279c5a8671bafebdcc5d_138.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_139.png)

**非对称加密**（公钥加密）使用一对密钥：公钥和私钥。公钥可以公开，用于加密信息；私钥必须保密，用于解密信息。这样，任何人都可以用你的公钥加密信息发送给你，但只有你能用私钥解密。这解决了对称加密中密钥分发的难题。在实际应用中（如HTTPS），通常先用非对称加密安全地交换一个临时密钥，再用这个密钥进行更快的对称加密来传输实际数据。

![](img/fb8f024423da279c5a8671bafebdcc5d_141.png)

公钥加密还可用于实现**数字签名**（验证信息发送者）和**密码密钥**（一种无需传统密码的登录方式）。

![](img/fb8f024423da279c5a8671bafebdcc5d_143.png)

---

![](img/fb8f024423da279c5a8671bafebdcc5d_145.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_147.png)

## 数据安全与隐私 🗝️

![](img/fb8f024423da279c5a8671bafebdcc5d_149.png)

上一节我们介绍了加密通信，本节中我们来看看如何保护静态存储的数据。

![](img/fb8f024423da279c5a8671bafebdcc5d_151.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_152.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_153.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_154.png)

传统文件删除只是标记空间为可用，并未真正擦除数据，可能被恢复。**安全删除**需要将存储数据的比特位覆盖为0或随机数据。

![](img/fb8f024423da279c5a8671bafebdcc5d_156.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_157.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_158.png)

更现代和高效的方法是启用**全盘加密**。整个硬盘的数据都用密钥加密存储，看起来全是随机数据。只有输入正确密码（解密密钥）才能访问数据。这样，即使设备丢失，数据也是安全的。但忘记密码意味着永久丢失数据。

全盘加密等技术也可被恶意使用，例如**勒索软件**会加密受害者的文件并索要赎金。防御之道在于坚持良好的安全实践，并保持**离线备份**。

![](img/fb8f024423da279c5a8671bafebdcc5d_160.png)

**端到端加密**是另一种保护隐私的技术，确保只有通信双方能解密信息，即使数据经过第三方服务器，服务器看到的也只是密文。

![](img/fb8f024423da279c5a8671bafebdcc5d_162.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_163.png)

---

![](img/fb8f024423da279c5a8671bafebdcc5d_165.png)

## 总结与行动指南 ✅

![](img/fb8f024423da279c5a8671bafebdcc5d_167.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_169.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_170.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_171.png)

本节课中我们一起学习了系统安全的多个层面。

总结一下，为了提升你和你的系统安全性，可以立即采取以下行动：

*   **使用密码管理器或密码密钥**：生成并管理高强度唯一密码。
*   **启用双因素认证**：至少为重要账户添加第二重保护。
*   **寻求并使用端到端加密**：保护通信内容的隐私。

最终，我们无法实现绝对安全，但通过应用这些最佳实践，我们可以显著提高攻击者的成本，从而让自己相对更安全。

![](img/fb8f024423da279c5a8671bafebdcc5d_173.png)

这就是系统安全，也是商业中的计算机科学。
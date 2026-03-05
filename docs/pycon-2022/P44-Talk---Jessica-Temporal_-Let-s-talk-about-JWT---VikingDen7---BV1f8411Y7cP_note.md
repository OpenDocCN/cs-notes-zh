# JWT入门教程：P44：讨论 - 杰西卡·特波拉

![](img/f356ac2853ed923b3e15746d71ff0c34_1.png)

![](img/f356ac2853ed923b3e15746d71ff0c34_2.png)

## 概述

在本节课中，我们将要学习JSON Web Token（JWT）的核心概念、结构、工作原理以及如何在Python中安全地使用它。JWT是一种用于在网络应用间安全传递信息的开放标准。

## 自我介绍

我是杰西卡·特波拉，你可以叫我Jess。我的代词是她/她。我在ROT Zero担任高级开发者倡导者。ROT Zero是一个身份平台，旨在简化应用程序的身份验证。我还是Data Bootcamp和McKinsey Learning的讲师。我是巴西人，拥有一个关于数据科学的播客“Pizza, Judas”。我最近创建了Gitfishes项目，这是一个Git学习卡片集合。你可以在大多数社交网络上通过用户名“Justin Peral”找到我。

## 关于术语的说明

我来自巴西。我知道在许多非英语母语国家，人们更倾向于将JSON Web Tokens称为“JWT”。但在英语国家，你可能会听到“jot”这个发音。因此，在整个演示中，我会交替使用这两个术语。

## JWT与JOSE规范

讨论JSON Web Tokens时，不能不提及创建一系列标准和规范所付出的努力，即JOSE规范。JOSE代表JSON对象签名和加密。它为处理JWT和其他网络对象提供了基础。JOSE规范的一部分是RFC 7519，通常被称为JWT规范。这将是我们今天讨论的重点。

## JWT是什么？

JWT是一个标准化的字符串，代表一些信息，并根据上下文传达特定含义。它由三个词组成：
*   **JSON**：定义了我们要传递的信息的构建格式。
*   **Web**：指信息传递发生的网络环境，这是一个空间受限的环境。
*   **Token**：通常是一个唯一的标识符，传达某种意义。

## JWT的结构

如果你从未见过JWT，它看起来像一串随机的字符和数字。但实际上，它有一个清晰的结构。一个JWT通常包含三个部分：**头部**、**有效载荷**和**签名**。

### 头部

头部位于字符串的开头，通常包含关于令牌本身的信息，例如令牌类型、令牌ID以及用于签名令牌的算法类型。头部是一个JSON对象，会被转换为Base64编码字符串，构成令牌的第一部分。

### 有效载荷

有效载荷位于中间，也称为主体。它携带关于特定资源的信息。在身份验证场景中，这个资源通常是用户。有效载荷也是一个JSON对象，同样会被Base64编码。

有效载荷中的每个键值对被称为一个“声明”。声明有三种类型：
1.  **注册声明**：这些声明来自JWT规范本身，非常重要。例如，`exp`表示令牌过期时间，`iss`表示令牌签发者。
2.  **公共声明**：这些声明由IANA（互联网号码分配局）标准化，旨在提供系统间的互操作性。例如，用户的名和姓有标准化的键名。
3.  **私有声明**：这些声明可以由开发者自定义，用于携带应用程序正常运行所需的任何信息，只要保持为有效的JSON对象即可。

**关于有效载荷的重要提示**：
*   放入令牌的信息越多，字符串就越大，在请求中传递的数据量也越大。建议只保留相关数据。
*   因为头部和有效载荷仅是Base64编码（并非加密），所以**绝对不要**在令牌中放入敏感数据（如密码），因为任何人都可以轻松解码这些信息。

### 签名

签名是JWT最特别的部分。它需要使用头部和有效载荷（Base64编码前）、一个密钥（或密钥对）以及指定的算法来生成。签名确保了令牌的完整性和来源真实性。

唯一能够正确签署令牌的人是持有正确密钥（秘密或私钥）的人。验证方可以使用相应的密钥来验证签名，从而确认令牌在传输过程中未被篡改，并且确实来自预期的签发者。

## 签名算法

签名算法主要分为两种类型：
1.  **对称算法**（如HMAC SHA256）：使用同一个**秘密**进行签名和验证。这个秘密必须在签发方和验证方之间安全共享。
    *   **公式/代码表示**：`签名 = HMAC-SHA256( base64UrlEncode(头部) + “.” + base64UrlEncode(有效载荷), 秘密 )`
2.  **非对称算法**（如RSA， ES256）：使用一对密钥：**私钥**用于签名，**公钥**用于验证。私钥必须保密，而公钥可以公开分发。这是更受推崇的方式，常用于分布式系统。
    *   **代码概念**：`签名 = RSASSA-PKCS1-v1_5( base64UrlEncode(头部) + “.” + base64UrlEncode(有效载荷), 私钥 )`
    *   `验证 = RSASSA-PKCS1-v1_5-验证( 签名, base64UrlEncode(头部) + “.” + base64UrlEncode(有效载荷), 公钥 )`

## 在Python中使用JWT

上一节我们介绍了JWT的理论基础，本节中我们来看看如何在Python代码中实际操作JWT。我将使用`PyJWT`库进行演示。

首先，你需要安装带有加密依赖的PyJWT库。

```bash
pip install PyJWT[crypto]
```

### 解码和验证令牌

假设你收到了一个JWT，并且知道用于签名的秘密和算法（例如HS256），你可以这样解码并验证它：

```python
import jwt

# 你的JWT字符串
encoded_jwt = “eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c”

# 用于验证的秘密（示例，实际应用中应使用强密码）
secret = “your-256-bit-secret”

# 解码并验证令牌
try:
    decoded_payload = jwt.decode(encoded_jwt, secret, algorithms=[“HS256”])
    print(decoded_payload)
    # 输出类似：{‘sub’: ‘1234567890’, ‘name’: ‘John Doe’, ‘iat’: 1516239022}
except jwt.exceptions.InvalidSignatureError:
    print(“签名无效！”)
except jwt.exceptions.ExpiredSignatureError:
    print(“令牌已过期！”)
```

### 获取未验证的头部信息

如果你不知道令牌使用的算法，可以先获取头部信息（不进行验证）：

```python
import jwt

encoded_jwt = “你的JWT令牌字符串”
unverified_header = jwt.get_unverified_header(encoded_jwt)
print(unverified_header)
# 输出类似：{‘alg’: ‘HS256’, ‘typ’: ‘JWT’}

# 然后使用从头部获取的算法进行解码
algorithm = unverified_header[‘alg’]
decoded_payload = jwt.decode(encoded_jwt, secret, algorithms=[algorithm])
print(decoded_payload)
```

### 使用非对称算法（公钥）验证

当使用RSA等非对称算法时，你需要使用公钥来验证令牌。公钥可以从文件或已知的端点（如Auth0的`/.well-known/jwks.json`）获取。

```python
import jwt
from cryptography.hazmat.primitives.serialization import load_ssh_public_key

# 从文件加载公钥（示例为SSH公钥）
with open(‘public_key.pub’, ‘rb’) as f:
    public_key_data = f.read()

public_key = load_ssh_public_key(public_key_data)

# 解码并验证令牌
encoded_jwt = “你的JWT令牌字符串”
decoded_payload = jwt.decode(encoded_jwt, public_key, algorithms=[“RS256”])
print(decoded_payload)
```

## JWT的常见用途

现在你知道了JWT的构成和工作原理，你可能会问它们通常用在什么地方。以下是两种最常见的用途：

1.  **访问令牌**：用于访问受保护的API端点。客户端在请求中携带访问令牌，服务器验证令牌后授予对资源的访问权限。RFC 9068规范了JWT作为访问令牌的格式。
2.  **ID令牌**：在用户登录后由身份提供商（如Auth0）颁发。它包含用户的基本信息（如姓名、邮箱），前端应用可以直接从中提取用户资料，无需额外请求。

**请注意**：刷新令牌通常不是JWT，因此不在此讨论范围内。

## 安全最佳实践

了解了JWT的强大功能后，确保安全地使用它们至关重要。以下是一些关键的安全提示：

*   **不要将JWT存储在本地存储中**：这会使令牌暴露在跨站脚本攻击的风险之下。一旦JWT泄露，无法撤销。考虑使用内存存储或安全的HTTP-only Cookie。
*   **不要在前端验证JWT**：尤其是使用对称算法时，验证所需的秘密不应暴露给客户端。验证工作应在后端服务器进行。
*   **不要在有效载荷中存放敏感数据**：重申一遍，因为头部和有效载荷仅是Base64编码，任何能获取到令牌的人都能读取其中的内容。切勿放入密码、信用卡号等敏感信息。

## 有用的工具和资源

最后，我想分享一些工具和资源来帮助你更好地理解和使用JWT：

![](img/f356ac2853ed923b3e15746d71ff0c34_4.png)

*   **JWT.io**：由Auth0提供的在线调试器。你可以粘贴一个JWT，它会自动解码并显示头部和有效载荷的内容。这是一个学习和调试的好工具（但切勿用于生产环境的真实令牌）。
*   **JWT手册**：我们制作了一本包含JWT示例和用例的手册，我鼓励你去阅读以获取更深入的知识。

## 总结

![](img/f356ac2853ed923b3e15746d71ff0c34_6.png)

在本节课中，我们一起学习了JSON Web Token的核心知识。我们了解了JWT的三部分结构：头部、有效载荷和签名。我们探讨了对称与非对称签名算法的区别，并通过Python代码演示了如何解码和验证JWT。我们还讨论了JWT的常见用途（访问令牌和ID令牌）以及至关重要的安全最佳实践。记住，安全地处理令牌是构建可靠应用的关键。
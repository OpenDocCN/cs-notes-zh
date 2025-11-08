# 第四讲

> 原文：[`cs50.harvard.edu/cybersecurity/notes/4/`](https://cs50.harvard.edu/cybersecurity/notes/4/)

+   保留隐私

+   网页浏览历史

+   HTTP 头部信息

+   指纹识别

+   会话 Cookies

+   跟踪 Cookie

+   跟踪参数

+   第三方 Cookies

+   私密浏览

+   超级 Cookies

+   DNS

+   虚拟私人网络（VPN）

+   Tor

+   权限

+   总结

## 保留隐私

+   这本是 CS50 的网络安全入门课程。

+   今天，让我们考虑我们在不知情的情况下分享了哪些信息，以及我们如何限制这种分享。

## 网页浏览历史

+   你的浏览历史记录既是功能也是对隐私的潜在威胁。

+   你可能不希望有人访问你访问过的网站。

+   你可以清除浏览器历史记录。然而，你可能会从所有服务中注销。

+   服务器通常会有*日志*来跟踪用户活动。因此，即使你清除了浏览器历史记录，服务器仍然会记录你访问的内容。

+   服务器日志可能如下所示：

    ```
    log_format combined '$remote_addr - $remote_user [$time_local] '
                      '"$request" $status $body_bytes_sent '
                      '"$http_referer" "$http_user_agent"'; 
    ```

    注意这包括你的 IP 地址、你的本地时间以及其他细节，这些都在计算机之间共享的数字信封中。

+   我们如何控制我们可以分享的内容？

## HTTP 头部信息

+   正如我们讨论的，HTTP 头部信息是在你的计算机和服务器之间发送的关键值对。

+   考虑以下可能通过以下 HTML 文件中的链接访问的 URL。

    ```
    <a href="https://example.com">cats</a> 
    ```

    这个 HTML 展示了一个名为 cats 的链接，将用户导向`example.com`。

+   当你访问一个网站时，浏览器默认会分享将你带到那里的链接。

+   当你点击一个链接时，浏览器会与网站分享是什么网站将你带过去的。因此，以下头部信息是从浏览器发送到服务器的：

    ```
    Referer: https://www.google.com/search?q=cats 
    ```

    注意这个头部信息分享了你在搜索什么。

+   如果能够抑制共享的内容不是很好吗？考虑以下：

    ```
    Referer: https://www.google.com/ 
    ```

    注意以下只共享来源：不是你正在进行的特定搜索。

+   以下元标签可以添加到你的网站中，以限制只共享流量来源。

    ```
    <meta name="referrer" content="origin"> 
    ```

    注意`content`属性被设置为`origin`。

+   可以通过在你的网站中添加以下内容来进一步限制，以提供无引用信息。

    ```
    <meta name="referrer" content="none"> 
    ```

    注意`content`属性被设置为`none`。

## 指纹识别

+   每个浏览器比其他浏览器更多地或更少地展示你的身份和行为信息。

+   无论你选择哪种浏览器，服务器都会记录你的活动。

+   *指纹识别*是一种第三方可以根据可用的线索识别你的方式，即使你在尽可能限制浏览器分享你信息的情况下。

+   其中一条信息是 *User-Agent* 请求头，它如下描述你的设备：

    ```
    Mozilla/5.0 (Linux; {Android Version}; {Build Tag etc.}) 
    AppleWebKit/{WebKit Rev} (KHTML, like Gecko)
    Chrome/{Chrome Rev} Mobile Safari/{WebKit Rev} 
    ```

    注意到你的浏览器、操作系统版本和设备被识别。

+   Web 服务器还可以定位你的 IP 地址并记录它。

+   Web 服务器还可以发现你的屏幕分辨率、已安装的扩展、已安装的字体和其他信息。

+   当这些信息随着时间的推移而汇总时，它可以使你越来越容易被识别。

## 会话 Cookies

+   记忆 cookies 就像一个虚拟的手章，用于跟踪你个人。

+   *Session cookies* 是服务器放在你的电脑上以识别你的信息。

+   一个会话 cookie 可能如下所示：

    ```
    HTTP/3 200
    Set-Cookie: session=1234abcd 
    ```

    注意到这个 cookie 告诉服务器你的会话是 `1234abcd`。

+   每个用户的会话编号或字符序列都是唯一的。

+   会话 cookies 通常在服务器确定的某个时间段后过期。

## 跟踪 Cookie

+   *Tracking cookies* 是设计用来跟踪你的。

+   第三方使用此类 cookies 来跟踪你在网站上的行为。考虑以下情况：

    ```
    Set-Cookie: _ga=GA1.2.0123456789.0; max-age=63072000 
    ```

    注意到这个 Google Analytics cookie 持续两年，并通过向每个你访问的新网站展示自己来跟踪你的活动。

## 跟踪参数

+   在 cookies 隐藏在浏览器“引擎盖下”的地方，*tracking parameters* 在你访问的链接中是可见的。

+   考虑以下 URL：

    ```
    https://example.com/ad_engagement?click_id=YmVhODI1MmZmNGU4&campaign_id=23 
    ```

    注意到 `click_id` 的值 `YmVhODI1MmZmNGU4` 专门跟踪你。

+   当 cookies 在后台被跟踪时，你可以看到你访问的链接（基于 URL）如何跟踪你。

+   越来越多，浏览器倾向于清理跟踪参数。考虑以下 URL：

    ```
    https://example.com/ad_engagement?campaign_id=23 
    ```

    注意到这个链接 *仅* 跟踪你响应的活动。`click_id` 的值不再存在。

## 第三方 Cookies

+   另一种类型的 cookie 是 *third-party cookie*。

+   第三方（即其他服务器或公司）希望了解你如何在网站之间旅行。考虑以下 HTTP 请求：

    ```
    GET /ad.gif HTTP/3
    Host: example.com
    Referer: https://harvard.edu/ 
    ```

    注意到这个请求明确要求从 `example.com` 获取一个名为 `ad.gif` 的文件。

+   自动地，服务器会响应以下头信息：

    ```
    HTTP/3 200
    Set-Cookie: id=1234abcd; max-age=31536000 
    ```

    `Set-Cookie` 响应头设置了一个名为 `id` 的 cookie，其持续时间为三年。

+   如果你浏览了使用相同广告的另一个网站，`example.com` 现在知道你正在浏览 `harvard.edu` 和 `yale.edu`。假设你后来发出了以下 HTTP 请求：

    ```
    GET /ad.gif HTTP/3
    Cookie: id=1234abcd
    Host: example.com
    Referer: https://yale.edu/ 
    ```

    注意到之前提到的第三方 cookie `id=1234abcd` 现在再次显示给 `example.com`，从而揭示你后来访问了 `yale.edu`。

+   第三方 cookies 可以用来跟踪我们并货币化关于我们的信息。

## 私人浏览

+   一种帮助保护你活动的方法是 *private browsing*。

+   在一个私人浏览窗口或标签页中，过去的 cookies 会被消除。

+   尽管如此，网络仍然按照网络的方式运行！在私人浏览窗口的生态系统中仍然可以形成新的 cookies。

+   更重要的是，服务器仍然可以跟踪您在单个浏览会话中的活动。

## 超级 cookie

+   提供您互联网服务的人可以始终在您的 HTTP 标头中注入他们自己的 cookie，而您可能并不知道。

+   您可能可以通过您的互联网提供商选择退出超级 cookie。

## DNS

+   *域名系统* 或 *DNS* 是一种服务，通过该服务可以将网站名称，如 `harvard.edu`，解析为特定的 IP 地址。

+   按惯例，DNS 的流量完全是未加密的。因此，您向全世界宣布了您试图访问的网站。

+   您的互联网服务提供商和 DNS 服务知道您试图访问的确切位置。

+   另一种称为 *HTTPS over DNS* 或 *DoH*，以及 *TLS over DNS* 或 *DoT* 的替代方案，是一种您可以通过它来加密您的 DNS 请求的服务。

## 虚拟私人网络 (VPN)

+   请记住，VPNs 是一种连接互联网的方式，使得看起来您似乎是从不同的设备进行连接。

+   VPNs 建立了您自己的电脑 (`A`) 和一个受信任的服务器 (`B`) 之间的加密连接。然后服务器 `B` 将您的请求发送到互联网，因此看起来您的流量似乎来自 `B` 而不是 `A`。

+   如果您的电脑感染了恶意软件，VPN 不能保护您。

+   VPN 会使得您的流量看起来似乎来自 VPN 的 IP 地址而不是您自己的电脑。

## Tor

+   *Tor* 是一种软件，它将您的流量重定向到 Tor 服务器的一个节点。

+   流量将通过许多加密节点进行导向。

+   按设计，软件不会记住您的大部分活动。

+   利用此类服务提供了很高的可能性，几乎无法识别关于您的信息。

+   然而，请注意，如果您是唯一在工作场所或学校本地网络中使用 Tor 的人，通过其他手段完全有可能识别出您是谁。

+   没有任何技术能为您提供绝对的保护。

## 权限

+   操作系统按照惯例，会请求在您的设备上使用某些权限。

+   *基于位置的服务* 默认情况下会提供您的地理位置。最好注意，如果您向 Apple Maps 和 Google Maps 提供此类权限，它们非常清楚您在任何给定时间的位置。

## 总结

在本课程中，我们讨论了...

+   许多课程，希望已经提高了您对提供给第三方信息的认识；

+   计算机中、服务器中、软件中以及您整体隐私中的漏洞是如何产生的；

+   您如何通过提高意识来减轻这些漏洞；以及

+   您如何更好地管理您和您服务的他人的隐私。

这就是 CS50 的网络安全入门课程。

# 文件系统，第八部分：从安卓设备中删除预装的恶意软件

案例研究：从安卓设备中删除恶意软件

本节利用本 wikibook 中讨论的文件系统特性和系统编程工具来查找并删除安卓平板电脑中的不需要的恶意软件。

免责声明。在尝试修改您的平板电脑之前，请确保备份设备上的任何有价值的信息。不建议修改系统设置和系统文件。尝试使用本案例研究指南修改设备可能导致您的平板电脑共享、丢失或损坏数据。此外，您的平板电脑可能会出现功能异常或完全停止工作。请自行承担使用本案例研究的风险。作者对这些指南中包含的指令的正确性或完整性不承担任何责任并不提供任何保证。作者对本指南中描述或链接的任何软件，包括外部第三方软件，不承担任何责任并不提供任何保证。

## 背景

从亚马逊购买的 E97 安卓平板电脑出现了一些奇怪的毛病。最明显的是，浏览器应用程序总是在 gotoamazing.com 打开一个网站，而不是在应用程序的首选项中设置的主页（称为浏览器“劫持”）。我们能否利用这本 wikibook 中的知识来理解这种不需要的行为是如何发生的，还能从设备中删除不需要的预装应用程序？

## 使用的工具

虽然可能可以使用远程连接的 USB 设备上安装的安卓开发工具，但本指南仅使用平板电脑上的系统工具。安装了以下应用程序 -

+   Malwarebytes - 一个免费的漏洞和恶意软件工具。

+   终端模拟器 - 一个简单的终端窗口，让我们在平板电脑上获得 shell 访问权限。

+   KingRoot - 一个利用 Linux 内核中已知漏洞获取 root 权限的工具。

安装任何应用都可能允许任意代码执行，如果它能够突破安卓安全模型。在上面提到的应用中，KingRoot 是最极端的例子，因为它利用系统漏洞来获取我们的目的的 root 权限。然而，在这样做的同时，它也可能是最有问题的工具之一，我们要相信它不会安装任何自己的恶意软件。一个潜在更安全的选择是使用[`github.com/android-rooting-tools/`](https://github.com/android-rooting-tools/)

## 终端概述

最有用的命令是`su grep mount`和安卓的包管理器工具`pm`。

+   grep -s abc * */*（在当前目录和直接子目录中搜索`abc`）

+   su（又名“切换用户”成为 root - 需要一个已 root 的设备）

+   mount -o rw,remount /system（允许/system 分区可写）

+   pm disable（又名“包管理器”禁用安卓应用程序包）

## 文件系统布局概述

在运行安卓 4.4.2 的这个特定平板电脑上，预装的应用程序是不可修改的，并且位于

```cpp
/system/app/
/system/priv-app/ 
```

偏好设置和应用数据存储在`/data`分区中。每个应用程序通常打包在一个 apk 文件中，这本质上是一个 zip 文件。当应用程序安装时，代码会被扩展成一个可以被安卓虚拟机直接解析的文件。二进制代码（至少对于这个特定的虚拟机）具有 odex 扩展名。

我们可以搜索已安装的系统应用程序的代码，查找字符串'gotoamazing'

```cpp
grep -s gotoamazing /system/app/* /system/priv-app/* 
```

这没有找到任何东西；看来这个字符串没有硬编码到给定系统应用程序的源代码中。为了验证我们是否能找到

让我们检查所有已安装应用的数据区域

```cpp
cd /data/data
grep -s gotoamazing * */* */*/* 
```

产生了以下结果

```cpp
data/com.android.browser/shared_prefs/xbservice.xml: <string name="URL">http://www.gotoamazing... 
```

-s 选项“静默选项”可以阻止 grep 抱怨尝试 grep 目录和其他无效文件。请注意，我们也可以使用-r 来递归搜索目录，但使用文件通配符（shell 的*通配符扩展）很有趣。

现在我们有了进展！看起来这个字符串是'app'com.android.browser'的一部分，但让我们也找出哪个应用程序二进制代码打开了'xbservice'首选项。也许这个不受欢迎的服务隐藏在另一个应用程序中，并且成功地作为浏览器的扩展秘密加载？

让我们寻找包含 xbservice 的任何文件。这次，我们将在包括'app'的/system 目录中递归搜索

```cpp
grep -r -s xbservice /system/*app*
Binary file /system/app/Browser.odex matches 
```

最后 - 看起来出厂浏览器已经预装了主页劫持。让我们卸载它。为此，让我们成为 root。

$ su

## pm list packages -s

Android 的包管理器有许多命令和选项。上面的例子列出了当前安装的所有系统应用程序。我们可以使用以下命令卸载浏览器应用程序

```cpp
pm disable com.android.browser
pm uninstall com.android.browser 
```

使用`pm list packages`可以列出所有安装的软件包（使用`-s`选项只查看系统软件包）。我们禁用了以下系统应用程序。当然，我们无法保证我们成功删除了所有不需要的软件，或者其中一个是误报。因此，我们不建议在这样的平板电脑上存储敏感信息。

+   com.android.browser

+   com.adups.fota.sysoper

+   elink.com

+   com.google.android.apps.cloudprint

+   com.mediatek.CrashService

+   com.get.googleApps

+   com.adups.fota（可以在将来安装任意项目的远程包）。

+   com.mediatek.appguide.plugin

很可能你可以使用`pm enable package-name`或`pm install`和/system/app 或/system/priv-app 中的相关.apk 文件来重新启用软件包。

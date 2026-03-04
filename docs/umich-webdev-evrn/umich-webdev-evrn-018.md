# 018：在Macintosh上安装MAMP 🍎

![](img/13298febd9a063373fc9a38b377035ec_1.png)

在本节课中，我们将学习如何在Macintosh电脑上安装和配置MAMP软件。MAMP是一个集成了Apache服务器、MySQL数据库和PHP的本地开发环境，是进行Web应用程序开发的重要工具。我们将从下载开始，完成安装，并配置PHP以显示错误信息，最后创建一个简单的PHP页面来验证安装是否成功。

## 下载MAMP

![](img/13298febd9a063373fc9a38b377035ec_3.png)

首先，我们需要从官方网站下载MAMP软件。

以下是下载步骤：
1.  访问 `mamp.info` 网站。
2.  找到适用于Mac的MAMP版本并点击下载。

下载完成后，文件通常会保存在“下载”文件夹中。

## 安装MAMP

![](img/13298febd9a063373fc9a38b377035ec_5.png)

下载好安装文件后，我们就可以开始安装了。

以下是安装过程：
1.  打开“下载”文件夹，找到MAMP安装文件（例如 `MAMP_PRO_4.0.1.pkg`）。
2.  双击该文件以启动安装程序。
3.  在安装过程中，接受所有默认设置并继续安装。

安装完成后，MAMP应用程序会被放置在“应用程序”文件夹中。

## 启动与配置MAMP

上一节我们完成了MAMP的安装，本节中我们来看看如何启动它并进行必要的配置。

启动MAMP后，控制面板会显示服务器状态和系统配置信息，例如PHP版本和配置文件的位置。对于开发工作，我们需要确保PHP能显示错误信息，这有助于调试代码。

![](img/13298febd9a063373fc9a38b377035ec_7.png)

默认情况下，PHP的 `display_errors` 设置是关闭的。我们需要编辑PHP的配置文件来开启它。

以下是修改PHP配置的步骤：
1.  在MAMP控制面板中，查看PHP配置文件的路径（例如 `/Applications/MAMP/bin/php/php7.1.0/conf/php.ini`）。
2.  使用文本编辑器（如TextEdit）打开这个 `php.ini` 文件。
3.  在文件中搜索 `display_errors` 这一行。
4.  将 `display_errors = Off` 修改为 `display_errors = On`。
5.  同时，可以搜索 `display_startup_errors` 并将其设置为 `On`。
6.  保存文件。

![](img/13298febd9a063373fc9a38b377035ec_9.png)

修改配置文件后，必须重启MAMP服务器才能使更改生效。

![](img/13298febd9a063373fc9a38b377035ec_11.png)

## 创建第一个PHP页面

配置好开发环境后，现在我们来创建一个简单的PHP页面，以测试环境是否工作正常。

![](img/13298febd9a063373fc9a38b377035ec_13.png)

![](img/13298febd9a063373fc9a38b377035ec_14.png)

Web服务器的根目录位于 `/Applications/MAMP/htdocs/`。我们在这个目录下创建的文件可以通过浏览器访问。

![](img/13298febd9a063373fc9a38b377035ec_16.png)

![](img/13298febd9a063373fc9a38b377035ec_18.png)

以下是创建测试页面的步骤：
1.  在 `/Applications/MAMP/htdocs/` 目录下，创建一个新文件夹，例如命名为 `first`。
2.  在该文件夹内，创建一个名为 `index.php` 的文件。
3.  在 `index.php` 文件中，输入以下简单的PHP代码：
    ```php
    <?php
    echo "Hello from my first web page.";
    ?>
    ```
4.  保存文件。

现在，打开浏览器，访问地址 `http://localhost:8888/first/`。如果配置正确，浏览器将显示“Hello from my first web page.”。服务器会自动寻找并执行 `index.php` 这个默认文件。

## 总结

![](img/13298febd9a063373fc9a38b377035ec_20.png)

![](img/13298febd9a063373fc9a38b377035ec_21.png)

本节课中我们一起学习了在Macintosh上搭建PHP开发环境的完整流程。我们从下载MAMP开始，完成了软件的安装。接着，我们启动了MAMP，并修改了PHP配置文件，开启了错误显示功能，这对于开发调试至关重要。最后，我们在服务器的根目录下创建了一个简单的PHP页面，并通过浏览器成功访问，验证了整个开发环境已配置成功。现在，你已经拥有了一个本地的Web服务器环境，可以开始进行PHP和Web应用程序的开发了。
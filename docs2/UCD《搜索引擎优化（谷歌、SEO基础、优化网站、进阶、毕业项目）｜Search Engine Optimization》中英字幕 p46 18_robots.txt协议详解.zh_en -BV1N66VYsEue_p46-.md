# UCD《搜索引擎优化（谷歌、SEO基础、优化网站、进阶、毕业项目）｜Search Engine Optimization》中英字幕 p46 18_robots.txt协议详解.zh_en -BV1N66VYsEue_p46-

![](img/2cb9d91793a37fbca90bf0d7afe5dff9_0.png)

![](img/2cb9d91793a37fbca90bf0d7afe5dff9_1.png)

Hello again。Now that we've introduced you to site Maps。

 let's discuss another method for controlling how search engines crawl your website and discover new content。

The robots。text file is a protocol that allows you to specify which pages should or should not be indexed and specify the rate at which files are accessed by search engine robots。

In this lesson， we'll learn about the importance of these files。

 but also recognize their limitations。By looking at an example robots。text file。

 we'll learn how to create and place these files in your website。When we just discussed site maps。

 we learned that site maps are an inclusionary file。

 meaning they tell search engines which information you want included in search results。

You also have the ability to exclude specific pages from being crawled。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_3.png)

You can do this through a robot dot text file。 The robot dot text file is a protocol that was created in the early days of the internet to prevent robots from crawling areas of the web that were not supposed to access。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_5.png)

![](img/2cb9d91793a37fbca90bf0d7afe5dff9_6.png)

That protocol today is often referred to simply as robots dot text。

This is a simple text file that can be uploaded to your server。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_8.png)

If a robot wants to visit a page on a website。Let's say example dot com forward slash blue widgets。

The robot will first go to the website's robots text file。This file will be located at example。

com forward/lash robots。text。Search robots will then check to see if there are any instructions prohibiting it from crawling that page。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_10.png)

It's important to note that while robots。t files provide search engine and bots with your preferences for what should or should not be crawled。

Robots can choose to ignore information in this file。

Search engines like Google or Bing tend to respect this file。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_12.png)

But people create robots for many reasons， and these reasons can sometimes be malicious。

Some robots are created to scan the web for vulnerabilities so people can hack into a person's website。

Other robots will crawl websites and harvest email addresses to sell to companies or spammers。Also。

 remember that robots。tex is a publicly available file。

 meaning anyone can see what sections of your server you do not want robots to access。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_14.png)

For example， we can view the robots。text file of UC Davis Exsion's website。

If you go to extension douc Davisvis do Eduu forward slash robots text or robots T X T。

You can see what their robot text file looks like。

![](img/2cb9d91793a37fbca90bf0d7afe5dff9_16.png)

If you take a look at their file， you will see a couple different areas that provide key information to search engine and crawlers。

First is the introductory text that explains what the robots。 textext file is。

This information isn't necessary， but many website content management systems include this information by default。

You will also see here that the file points out that these instructions will be ignored unless it is placed at the root of your host。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_18.png)

![](img/2cb9d91793a37fbca90bf0d7afe5dff9_19.png)

This means that you always access a site's robots。text file at theexle。com forward/ros。text。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_21.png)

If it is placed anywhere else in the site， such as example com forward slash site forward slash robots text。

 it will be ignored under that area， you will see specific instructions。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_23.png)

For example。User agent。Specifies what user agents should crawl website content。For example。

 you can set up specific instructions for Google， Bing or Yahoo。Most of the time， however。

 there is no real reason to do so。The asterisk works as a wild card。

 and means that all robots should follow the below instructions。

The crawl delay sets how many seconds a robot should take before accessing a new page on your site。

This can help prevent overload of server resources， which may crash your website。

The pound symbol or hashtag。Is used to make a note。

This is for humans to read and is not read by robots。In this example。

 it's a note by the Webmaster to remind himself or other Webmasters that the below items are specific directories of the site。

The disallowed directive。Instructs robots not to crawl the content it is referencing。For example。

 do not crawl the directory forward slash includes。

 So now that we know what the asterisk and disallowed directives mean。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_25.png)

If we wanted to exclude robots from accessing our entire site。We would simply enter the instructions。

Use your agent。Followed by an asterisk。And then on a new line， we would enter disallow。

Followed by a forward slash。If we wanted to allow robots complete access to the site。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_27.png)

We would simply keep the disallow field blank。For example， we would simply enter Use agent。

Followed by an asterisk or wild card。And then on new line。

Type disallow and not include any information after that。

You could also simply not use a robots bot text file。

 which will automatically make all information public。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_29.png)

You should now understand what a robots that text file is used for。

How to create and read a robotst text file。

![](img/2cb9d91793a37fbca90bf0d7afe5dff9_31.png)

As well as where this information should be placed in your server。



![](img/2cb9d91793a37fbca90bf0d7afe5dff9_33.png)
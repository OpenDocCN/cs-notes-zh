# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P35：34_音频和视频.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Since the introduction of the smartphone and high speed Wifi， we now enjoy creating。

 consuming and sharing video and audio content daily on our devices。By the end of this video。

 you'll learn how react developers use audio and video assets within an app。

 you'll also explore how to find suitable react packages to use when working with audio and video files。

Let's begin by exploring a method to load a local video asset into your react app using just HTML。

You can use the readily available HTML5 video tag to load a local video asset to your react app like loading an image or any other kind of asset file you can just declare a variable somewhere above a components return statement and then add it as a JSX expression to the SRC attribute however this approach might not work as easily with some major providers of video content such as one of the several social media and social video sharing platforms。



![](img/0883d7e1fbca7843851c54321c4fd321_1.png)

In that case， you have the option of rolling out your own solutions。



![](img/0883d7e1fbca7843851c54321c4fd321_3.png)

This may be a bit more involved than just adding a video tag to an app it might depend on the specific instructions on how a given social media platform recommends that you embed their video and audio assets into websites very often you'd get a code snippet that you can copy and paste。

However， a specific implementation might be slightly different because you would， for example。

 like to add it as a separate react component。😊，You might be wondering。

 why do you want to prepare it as a separate component？

One of the reasons is that you'd be able to easily switch one video with another by passing the unique ID of a given video as a prop。

You can then control the video output that way。So far。

 you've learned about two ways of adding videos to your apps。

The first method involves just serving a local video using the video element and the second method is using embedded third party videos。



![](img/0883d7e1fbca7843851c54321c4fd321_5.png)

There's another approach you may consider， namely using a third party NPM package to streamline the process of adding videos to your app。

The NPM package ecosystem is huge。

![](img/0883d7e1fbca7843851c54321c4fd321_7.png)

If you visit the Npmjs。org website， you'll find millions of various packages。

To make it easier on yourself， type React video in the search bar of the NPpmjs。

org website to find some of the frequently downloaded NPM packages。To choose the right one。

 you might want to check the frequency of updates。A package that's frequently maintained and has many contributors is usually a sign of a solid package to use。

😊，Additionally， make sure to check the packages GitHub page。 Finally。

 you can also perform an Internet search for the package name。

These actions will help you make an informed decision on which package to choose。

An example of a package that fits all these criteria is the react player package。

Visit the packages Gitthub URL at Gitthub。com forward/lashcpeat forward slash react hyphen playerer。

You'll find that the react player package has over 6，000 stars。

 about 115 contributors and that it's regularly maintained， so what is the meaning of the stars？

When a developer visits any repository on GitHub， they can show their appreciation of the project by clicking the star button。

 this is known as starring a repo。This can be done for various reasons but if a project has been stard many times that's usually an indication of its popularity these are all good signs so if you want a custom open source solution for your video needs and react you can choose this package or a similar one Great job you now have a general idea of how to use audio and videoasseets in a react app and how to find packages using NPmjs。

org and Github。com。

![](img/0883d7e1fbca7843851c54321c4fd321_9.png)
# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P103：36_03_03_Flask框架解析.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/b7de90e53a0f0a4bcf49670012862c75_0.png)

So what is flask and how do you use it Well let's look at the official documentation here。

 you can see a minimal flask application is very small。 for example。

 this application says from flask import flask and I define the application and put a route so this route is where the URLs are created and inside of here encapsulated is the logic。

So let's go ahead and take a look at a real world flask application so here's a codespace in GitHub and inside this codespace you can see all of the logic for a flask application right and so it's pretty small here I say from flask andboard flask I define this app so that's really the boilerplay code and then here's the hollow world route and so inside of here I can print debugging messages。

And I also will return back a message now if I want to do something slightly more complex。

 which is in the real world typically what you want to do。

 I could accept parameters and so here's how you do that in flask I put in these brackets here around this parameter and then I capture it inside the function so this name matches to this name and then。

When I echo this out here， I say return hello， it will echo out whatever name I put。

 The only other thing that's important to know about is this last block here line 16 and line 17。

 I say if under under name equals main and this is a shortcut that tells your Python code。

 if it's run as a script here's some things to do。 So inside I say app right。

 so this goes back to this line 2 and I tell it to run on port 8080 on 12700。1。

 which is the local host， and then I also have debugging setup So how do we run this。 Well。

 I can just run in Python hello just like this and if I have flash installed。

 it will run locally and inside this Github code space。

 I can actually open this up in the browser and test it out。

 Now first all go through here and test out the s route。

 then I'll go to echo and test out that echo route。 So first step here， great。

 we've got hello world that。Appears to be working。 Now， if I go through and I put the echo here。

And I say echo。Let's put Bob in there。There we go。 So we see Bob is working。 What if we put Sally。

 let's go ahead and put Sally， there we go so you can see that I can quickly build web services that are fully functional by using this routebased approach and it's quite simple。

 This whole application is less than 20 lines of code and it fits in one block in your mind。

 So that's really the advantage of using a microservice like flask。



![](img/b7de90e53a0f0a4bcf49670012862c75_2.png)

![](img/b7de90e53a0f0a4bcf49670012862c75_3.png)
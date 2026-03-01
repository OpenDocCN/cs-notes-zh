# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P18：18_03_01_AWS云开发介绍.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

In this lesson， we create an AWS cloud development environment。

 let's look at the learning objectives。First， we get into what continuous integration is and why you want it in your project。

Next， we cover an AWS cloud9 continuous integration from zero， and we do it step by step。

Then we construct a Python project scaffold this is really the core components of what I would consider a best practice。

A make file， tests， Lint， and also a requirements TXT file。

Next we'll get into developing GitHub actions testing for an AWS project Let's dive into a few of these key terms and make sure that you understand them First a make fileile。

 what is it well a make fileile is a recipe for building software and it's a way to make sure that your application runs the same way in any environment and it really simplifies the steps of a software project so really it's a recipe that is available on all Linux systems and you can use it for your advantage。

Next， let's get into tests what our tests Well the main reason you have tests is that it ensures that your software works。

 there's a few different kinds of tests， one kind is functional。

 so this could be let's say a test of a commandlan tool or a web application so at high level make sure that it works another one is integration so does one piece of software integrate with another let's say the web frontend in the backend a load test is another one that is a very common form of a test and this would be ensuring that let's say 10。

000 users would be able to use your application this is really critical in the cloud is to do load testing。

So in a nutshell tests are not a waste time， they're actually a way to save time when you do automated testing。

 especially these different varieties and these are just a few it actually saves time in your project and this is a really key point to remember what aboutlyntting so Lntting is something that comes up a lot and this is a best practice really for all projects in Python and what it can do is it can check for bad syntax so let's say you have a variable that you forgot to you know declare the value for it well it'll catch it before it gets put into production。

So in a nutshell， that's really the purpose oflyntting is that it can catch bugs before they even occur and you can test it automatically。

It also enhances automation and so when you use LintIn。

 you can ensure that when you use a GitHub actions or build server that is running your code。

 that the L step will really ensure a certain level of quality。

Python virtual environments are often really misunderstood。

 and let's talk a little bit about that since we're going to be covered it in this lesson。

They isolate Python to a particular directory that's really in a nutshell what they do they allow Python the interpreter and the libraries to be fit right into one directory so how would you do this this is an example of one thing that you could use you could say Python 3。

 the interpreter dash M for module， use the virtual environment module V E and V and then inside of your home directory that tilled a slash create an invisible directory if you put a dot at the beginning it'll make the directory invisible and this is a great format to use when you're creating a virtual environment。

Later to use that， you would say source tilde do your hyphenproject hyphen A and V s bin/ activateivate and this activates that environment and they activate script is just a shell script that tells your project to listen to that directory and that's where you're going to put all your code and that's where Python will live and this really does isolate a lot of problems and eliminate them so in a nutshell Python virtual environments are a best practice to get into and they save you a lot of trouble and there's a lot of very exotic reasons why you should use them but in general if you use Python virtual environments you'll eliminate a lot of problems before they start。

Let's talk about GitHub actions next here， so what is GiHub actions。

 it's a SASbased build server that's available with GitHub and it allows you to do continuous integration and continuous integration which we'll get into in a little bit is a form of automated testing so when you checking your code this SASbased build server will automatically go in test your code and makes it very convenient if you're already using GitHub。

It's also Yaml based and if you're not familiar with YaAmL。

 it stands for yet another markup language and what it means is that it's a very high level simple configuration file where it looks pretty human readable and you would put in the series of steps like Li My code test Mycode you know deploy my code so in a nutshell GiHub actions is a SaSbased continuous integration server and we'll get into that later in this course。



![](img/77bd90c7938c58d89ee4d600e0ca582e_1.png)

![](img/77bd90c7938c58d89ee4d600e0ca582e_2.png)
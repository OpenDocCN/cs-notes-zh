# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P25：25_02_04_演示：创建新的Rust项目.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/7b320fdb2e6289d95e24356f4fc92e8e_0.png)

Let's see how we can create a new rust project for these。 We will actually be using cargo。

 so make sure that you have cargo installed。 In this case。

 I have it in my system that's not going to be a problem。

 So if you've gone through the rust stop and the installation process you should be good to go。

 it is not a requirement to use cargo however， so you can actually create a files from scratch if you want to。

 but there's nothing like having some automation and allowing you to make some progress very quickly by using the tool that will put everything in its right place。

 There are a couple of options here。 and I am in in a temporary directory that I've created and I've created this example temporary or subdirecty in my temporary directory and there's two ways that you can go about this。

 the first one is if you say cargo。In it and you say dot and what that does is actually utilize the same the same working directory。

 but using the name of the directory as the project so that is the thing that is going to happen so let me run it and youll show you what I mean。

 so by default it will create a binary application package， I'll tell you what that is in a second。

 if I do a S or tree， you will see that we have cargo Tamo source and main DataRS。

 So if I poke around what that cargo Tail you will see that the name is actually example。

 the addition is 2021， we'll take a look at what those things mean for for the cargot Tael file later but it is the important thing here is that is using an example and you saw that it created a binary that is because youll have a main datas with a main function if we were creating a live。

Then you won't need that， you won't have that and there's actually an option to do that with cargoes if we do cargo in it。

 help I'm going to clear my screen here。There is a way to use a library template。

 how about we go ahead and remove cargo that demo and remove。S R C， and then we clear。

 and then we'll run cargo。In it， but instead of doing not only a dot。

 but like a dash dash lip and say right here， we can take a look at what cargo thatammo looks like。

So looks exactly the same if I do three like3 will tell me that there's no longer a mains。

 but we have a Lib that Rs。 so let's take a look at how how is that and there you go we have a module test it gives us the ability to run some tests which haven't seen that and we have these public function called add so that looks pretty straightforward。

 those are two options for the current directory， but what if you want to create either a library or a binary package in its own subdirecty so let me clear these and the way we do this is with cargo new instead of cargo in it is cargo new and we do help it will be similar to what we had before except like similar as we had with cargo in it except for one thing we will be able to take an argument。

For the path and the path will give us the name of the actual package that we want to use。

 so if we say cargo new and let's just call this my F project then it will create a binary application fo。

 So if I clear all this and I do three， you will see that it will create this F directory with cargo So let me actually go ahead just for sake of clearing everything up let me remove that one and SRC from what we had before。

So now we have this full subdirecty and if I do three again。

 you'll see that we only have the like this it's contained all of the files that we've created are contained inside there。

 Now， why would you want to do something like that。 Well， it's up to you really。

 but if you want to have things contained in a subdirectory， you can certainly do this Now。

 if we do the same。 it's similar options to in it， really， if not almost the same。

 I can do I can remove that and if I do cargo new。And instead of just saying new Fo。

 I can say dash dashlib and similarly we'll see that create library Fo package if I do three now we'll get the Lib that Rs and no longer that main Rs So there you go those are four ways actually that you can create a new project either a binary or a library again we'll see what the core differences between those but you can imagine a binary package will be more of like an executable in a library will be something that you can utilize it's publicly available functions and methods and structures so that you can use them in your own in your own application So there you go those are the differences and that's how you get started creating a new R project。



![](img/7b320fdb2e6289d95e24356f4fc92e8e_2.png)
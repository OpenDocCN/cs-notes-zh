# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p48 48_03_03_使用Cargo Lambda与Rust.zh_en -BV11y411z7Dn_p48-

![](img/7d472d1f070a0a6d218a54838c9750ce_0.png)

Let's take a look at cargo Lambda， which allows you to have rust functions on Aws Lambda。

 in a really simple way。 In many cases， I think it's the easiest possible way to develop in any language for Aws Lambda。

 there's nothing needed。 There's no weird workflows。 It is a very straightforward process。

 So let's go ahead and first take a look at what you need to do。 So in order to install it。

 one of the ways that you can install it is to use Homebw。 So in this case。

 you need to install Homebrew on a machine， let's say cloud 9。 And then that's it。

 And then all you have to do is do cargo Lambda a new project and then dive into it。

 So now that I know that that's what we need to do。

What I'm going to do is I'm gonna show you something I've got set up。

 which is first I have the Lambda EFS set up here。 so I'm mounting the elastic file system on Lambda。

 I also have a lambda already running here that's working and let me show you how I developed it。

 So first up here， what I can do is take a look at this project。

 which is called EFs lister and inside of here， this is where all my code lives， which which is nice。

 but I want to show the deployment process。 So in order to do that。

 what I'm going to do is I'm going to show you that I can run cargo Lambda invoke and this will actually test this thing out locally。

 Now this is gonna to fail， because I don't have the cargo Lambda watch working。

 So let's first see it fail。 there's no emulator。 So what's great about this cargo Lambda service is that you can actually run it in watch mode。

 So if we go back to the docs here， take a look at this What is it you can just say cargo Lambda watch。

 Okay， let's do that。😊。

![](img/7d472d1f070a0a6d218a54838c9750ce_2.png)

![](img/7d472d1f070a0a6d218a54838c9750ce_3.png)

Go here and let's do cargo Lambda watch。 There we go。 So it runs like a local emulation。

 It's trivial because， again， Ru is a binary base language。

 I don't have to do weird docker images or anything like that。 So next step， how do I invoke it。

 Well， we can just do that same command。 So we can just say cargo Lada invoke。

 And it's gonna look for running service here In this case， the parameters I'm accepting are name。

And there we go。 So what it's going to do is actually interact with the actual code that the Lada would run in production。

 which is it's going to list files on my elastic file system。

 And what's awesome about this is I can also verify this， because if I do Ls dash L here。

 M and T EFs， we can see that's exactly what is on my file system。 So that's great。

 But what if I wanted to to deploy this function and test it。 Well。

 let's go ahead and read the docs here。 And let's see how this works。 So first up。

 that's how you test it。😊，That's how you invoke it。 Oh， so you can do it with a API gateway。

 But what if we want to build a release， Let's go ahead and build this。

 So let's go ahead and go back here and let's build this release。

 So we'll say cargo Lambda build release。 And let's see what happens。Very quick。

 it's compiling everything we need。And once we've done the release。

 it's going to create a binary that we can use to do deployment， which， in my opinion。

 is the way to go for a service like AW Lada perfect。 Now， what's the final step here。

Is that we can do cargo Lambda deploy Now， notice you could even deploy to arm 64。

 which is awesome because it saves you a ton of money。And we go here。 We do a release。 There we go。

 trivial right to deploy this。 I mean， I don't think of I can't think of anything that would be faster than using cargo Lambda to deploy code。

 Now what else can we do here we can do debugging we can run Github actions we can do etc cea。

 etc ce。 So in a nutshell， I think cargo Lambda take something that is truly a little bit scary in scripting languages and makes it trivial。

 I would recommend you check it out and the code is pretty easy to implement as well。

 and I'll see you in another demo video soon。

![](img/7d472d1f070a0a6d218a54838c9750ce_5.png)
# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P71：24_HEAD.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Previously， you learned about the hidden folder called dot git that is located in each project。

 you know that this folder is responsible for keeping track of all changes across a project。

 How does Git know what branch are currently on。Let me explain。

It keeps a special pointer called head， which is one of the files inside the dotge folder。

 This file refers to the current committee you are viewing。



![](img/82214927f7ca38f063814438e4007630_1.png)

You will now learn how to identify the current committee you are working on first。

 open the dotgit folder on your terminal， type C dotgit and press enter Next type CA head and press enter in Git。

 we only work on a single branch at a time。This file also exists inside the dot get folder under the refs forward slash heads path。

Let me show you type Cd。git and press enter next， type cat forward slash refs， forward slash heads。

 forward slash main press enter After you enter this command， a single hashed ID appears。

The single hash ID is a reference for the current commit。

Let's switch branches to see how the head is moved to point to a new branch。Type Git。

 check out testing， and press enter。Next， type get， branchnch and press Enter again。



![](img/82214927f7ca38f063814438e4007630_3.png)

This moves the head to point to the testing branch。

Let me explain how this happens by using a diagram。We have two branches。

 the main and testing branch when you run the checkout command and moves the head to now point to the testing branch to check the contents of the head file inside the dot gett folder。

 you have to enter the less command type less dotge/ head and press enter。



![](img/82214927f7ca38f063814438e4007630_5.png)

You can now verify that the head has changed from main to testing。



![](img/82214927f7ca38f063814438e4007630_7.png)

Now I will demonstrate how Gethead works with a simple example。

So I am here in the terminal to see what branch I am in。

 I am running git branch when pressing the enter key I can see I'm on the main branch to confirm that I run the cat dot git forward slash head command and press enter。

That brings me back to the reference to where it actually points to， namely refF， refs。

 forward slash heads， forward slash main。In this case。

 you can see the references pointing to the head's main。

If I change my branch to feature testing branches above， I use the git check out command， git。

 check out feature forward slash testing branches。 I then go to my head file inside the git folder by typing cat dot git forward slash head。

 The reff is now pointing to the feature testing branches。Namely， wraps， forward slash head。

 forward slash feature， forward slash testing branches。

Notice that my branch is up to date with origin forward slash feature。

 forward slash testing branches。 I'll go back into my main branch by typing git check out main and then check the reference file inside the main directory using the cat command again。

 Cat dot git forward slash refs forward slash heads forward slash main。 When I press enter。

 I get a hash I D。 This is a reference to the latest commits of that work in directory。

I can show you that if you make a change to any files within this directory that this I will then change after a commit has happened。

 So let's do a simple update to the Readme file。 You can do this with any editor such as V S code。

 or I can also do this by executing the Vim command。 type Vim， readme do M D and press enter。

 When inside the readme file， add some text In this case。

 add minor update to your my first repo line and save it。Then check the ID again just to verify。

 type CA， dot， git， forward slash refs， forward slash heads， forward slash main and En。

If you would like to learn more about VIM， there is a link to an additional reading at the end of this lesson。

The ID should be the same because we haven't committed anything we've just made a change to run the CA command。

 therefore the ID is exactly the same as before。If I do a get status。

 it is telling me that I have modified the Read me file on the screen， the words modified。

 read me dot M displays in red。I'll now add that file the shorthand to add a single file is git addspace dot。

Type the command and press the enter key。I am then going to do a commit type gett commit dash M for message by adding minor update to the command line and press enter。

The data confirms that one file changed， there was one insertion and one deletion。

I am using the CAAT command to verify what is in the reference file by typing cat。git forward/ refs。

 forward sheads forward s main， press the enter key to confirm that the ID is changed。

Originally the ID started with a 8B55 and now it starts with 9 C90 whenever a change occurs for a commit。

 this ID will then update to be the latest commit for that working directory。



![](img/82214927f7ca38f063814438e4007630_9.png)

And that's gett head。 You now know what the purpose of head is。

 You can also change the head to point to a different branch。


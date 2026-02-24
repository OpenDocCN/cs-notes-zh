# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P68：21_远程与本地.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

In the pre internetnet era， saving project files to different machines for backup and transfer was a tedious process。

 It required manually copying files between machines one at a time， making things slow for teams。

 Nowadays， the cloud has enabled a more efficient way to do this。 And in this video。

 I'll explain the differences between remote and local on Github。

 You have previously learned about the flows modified， staged and committed in a Git workflow。 Now。

 you will learn about pushing your changes from your local to a remote repository。

 Re refers to any other remote repository to which developers can push changes。

 This can be a centralized repository， such as one provided by Gitthub or repositories on other developer devices。

In this lesson you will be hearing some new terms such as clone， P。

 pull and repo don't worry these will all be explained soon。

The remote code is accessed through a UI which is unique and only accessible to those who have permission。

Local， on the other hand， refers to your machine， which can be a laptop。

 desktop or even a mobile device and is only accessible to you to demonstrate both of these in action。

 let's say we have a project called coding Project1， which is located on Github with a unique URL。

 In other words， This project is stored on the remote server。

 When a user wants to copy this project to their local device。

 they need to either perform a clone if it's the first time or pull it to get the latest changes。

 to clone a project， a user must first choose a folder on their local machine。

 Coing project 1 is then clone from the server and copied into the chosen folder。

 The user can then make changes to the project and push those changes back to the server。

 Other users working in on the code base won't see those changes on their local machines。

 unless they pull the latest changes from the server。

One of the advantages of Git is that you can work offline and then commit your changes when you are ready。



![](img/f78c59f06d0e11816b70d36f178e6bbb_1.png)

Now let's go through an example of how exactly you would do this in GitHub。In this video。

 I'm going to explain what local and remote mean in GitHub and help you to understand the differences between the two。

First off， I'm going to create a new local repository using the Git innet command。

 I'll start by inputting MKDIR to create a new directory and then I'll set the name as my second repo。

Next I'll use the change directory command， which is C followed by the name that I just set Finally。

 I'll perform the git in it command to create my new repository。

This will return a line telling me that an empty repository has been initialized under root projects。

 My second repo。 If I execute another command called Git remote， it comes back as blank。

 The reason for that is that I've only initialized a local repository。

 which has no connection to a central repository that sits either on Gitthub or another server。

 Right now， it's only available locally on my machine。Now I'll step back out from this directory。

And go into my first repo with a CD command again。This is a repository that I created earlier and does have a connection to GitHub using the remote UI。

 I'll then check it by using the Git Reote minus V command。

Gt tells me that it's set to git tutorials 101 my first repo。

git next I'm going to set this against our second repository。

I'll step into the new directory once more using the CD command。In this case。

 we're going to add this URL to the remote settings by using the command get Reote add。

 specifying a name， and then passing in our URL。The name that is typically used here is origin。

 so I'll stick with that。 So again， the full command with the URL should read git remote add Or git at Gitthub co git tutorials 101。

 my first repo do git。This time when I execute the Git remote minus V command。

 I have this set up against the Git tutorialials 101， which sits up on GitHub。

What I'm going to do next is use the Git pull command。

 which will connect with the GitHub server and pull down all the changes from the repository。

So on my local， I now have all the changes， but when I check the directory it's blank。

 The reason for this is that I haven't set up a branch that matches with what I have on the server repository。

 Fortunatelyly， I can change that by performing the command get check out main。

 which will set up a branch main on my local that tracks the branch main from the remote。

And now when I check my folder using the LS command， it confirms that I have the readme。

 test and test two files available on my local。

![](img/f78c59f06d0e11816b70d36f178e6bbb_3.png)

In this video， you learned about the differences between local and remote and GitHub。

This will help set you up to exchange data more efficiently within your development team。

 See you next time。
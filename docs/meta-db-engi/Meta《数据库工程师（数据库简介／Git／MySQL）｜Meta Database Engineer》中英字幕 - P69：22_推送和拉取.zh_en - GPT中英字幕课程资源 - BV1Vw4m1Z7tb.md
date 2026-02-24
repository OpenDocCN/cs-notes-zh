# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P69：22_推送和拉取.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

By now you should know how to use GitA and Git commit to add new changes to your local repository put them into the staging area and get them ready for a commit Now let me guide you through the next step and upload these changes to the remote repository using Git push I'll also demonstrate how to retrieve changes from the remote servers and apply them to your local repository with Git poll before we begin let's go over the command line and perform the command Git status。



![](img/c8f7f4f22ee07f2946d82b50c2891b04_1.png)

Gt tells me that I'm on the branch main， but also that my branch is ahead of the origin main branch by one commit。

 What this means is that all the changes that I have on my local repository are currently ahead of what is stored in the remote repository on Gitthub。

 That ties into Gits distributed workflow in which you can work in an offline state and then only ever communicate with a remote repository when you use the commands of Git push or Git pull。

 Now I'll guide you on pushing your changes to the remote repository。

 And then I'll demonstrate how to use the pull command to get the latest changes。

 It's always good practice to check which branch you're currently on。

 And you can use Git status or Git branch to do this。

 This is important because if you do make changes in a different branch。

 You need to specify where you're pushing up to。 So let's push up the changes using the Git push command。

 I'll specify the origin branch to be the main branch。 As in I'm pushing my。

Changes to the origin as the remote repository and then I want to push it to this branch as the main I'll be prompted for my login information as I am pushing using Https Once I enter my login information you'll notice that the commit is pushed from the local main to the remote main on the remote repository Let's refresh the page on the Github website you can see that my test do TXt file now appears there。

 that's taken the commit snapshot that I have in my local repository and pushed it up to the remote repository Git has then compared those files with what's on the remote repository to find any conflict or problems。

 If none are found itll just merged them straight through which is classed as an auto merge。

 If there are any conflict， my push will fail。

![](img/c8f7f4f22ee07f2946d82b50c2891b04_3.png)

Before doing a push， it's also good practice to perform a git poll in order to get the latest changes from the remote repository and reduce the odds of encountering a conflict because I only have a single file and this will be a new repository。

 I'm not going to run into any conflict or any issues。

 so now let's move on and I will guide you through how you can use Git poll。Normally。

 when you're working on a project， you could have several developers all submitting with different branches。

 different code， and different features。In order for you to get those changes。

 you need to use the Git pull command to demonstrate this， I will add a single line to the test。

txt file using the GitHub UI， and then add the commit change， updated the test。TXt file。

I'll then commit it directly to the main branch by clicking on commitmit Change。

The changes now appear on the UI， but because I haven't used the Gett pull command on my local machine yet。

 I should have no content on the test。txt file， let's verify by using the CAD command on test。txt。



![](img/c8f7f4f22ee07f2946d82b50c2891b04_5.png)

And sure enough the file is empty， which is what you'd expect as I mentioned before。

 I need to run the command git poll this will get the latest changes from the remote repository。

If any new changes were added， it'll be reflected in the shell output。I run the command。

 and in this case， Git tells me that one file has changed with one insertion。

 If I run the cat command on test do Txt once more。

 it shows that the line this is my change is now available in my local directory with Git pull you're taking all that data from the remote server。

 Git then merges the snapshot from the remote with the snapshot that's on your local。

 it will auto merge them if there is no conflicts。 Once that's complete。

 I'll have the latest changes on my local machine。 you have now learned how to push to and pull from your Gitthub repository。



![](img/c8f7f4f22ee07f2946d82b50c2891b04_7.png)

![](img/c8f7f4f22ee07f2946d82b50c2891b04_8.png)
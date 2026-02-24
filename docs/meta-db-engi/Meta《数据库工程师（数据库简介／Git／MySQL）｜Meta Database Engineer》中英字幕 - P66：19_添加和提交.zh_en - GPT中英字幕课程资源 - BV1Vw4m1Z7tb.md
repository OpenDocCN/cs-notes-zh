# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P66：19_添加和提交.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

![](img/8e103a3c07b3abc47226a4be6c739acc_0.png)

So I've opened up my terminal window， I'll have a look at what directory I'm currently located in。

 I can do this by running the PWD command which is short for print working directory notice that I'm in the directory my first repo。

Now， I can check inside that directory by running the LS L command。 I can see that I have two items。

 a readme dot M file and a hidden folder called dotgit Before I add any files or make any changes。

 It's always good practice to check if any changes or commits are currently there。

 I can do this by using the Git status command。 Git status also displays what branch I'm on In this instance。

 I'm prompted that I'm on the branch called main。 and that my branch is up to date with the origin main。

 This means that all the latest files on my local machine are exactly the same as what is displayed on the Github UI。

 which represents the server that everyone commits to Git status also tells me that I have nothing to commit and that my working tree is clean。

Now let me show you how to add a simple text file， I'll add a file called test。

tXT by using the command touch test。 TXT。Then I'll run the command Gi status again。

Now Git is telling me that I have an untracked file which is the test doTxT file that I just added。

 it's also telling me that I have nothing added to the commit but that untracked files are present and that I should use Git add to track them the purpose of the Git add command is that I'm essentially prompting Git and letting it know that I want to track this file and that itll be included as part of my commit。



![](img/8e103a3c07b3abc47226a4be6c739acc_2.png)

![](img/8e103a3c07b3abc47226a4be6c739acc_3.png)

The first phase of this process is just to run the command Git add test dot TXD。

 Now I'm going to run git status again to check that file is now being tracked。

 notice again that I'm notified that my branches are up to date。

 but it's also telling me now that their staged changes to be committed。

 which is this new file called test dot TXD。 It prompts me asking if I want to revert those changes for this。

 I can use the git restore command with the flag dash dash stage and the file name test dot TXD。

 running the command will unstage the file from the commit。

 I then run git status one more time to see the file is back to an untracked status。 So once again。

 I'll add the file using git add test dot TXT。 run git status。

 and now notice that the file is back in a track state。Okay。

 let me clear my screen before moving on to do this。 I use the clear command。 Now。

 any changes that I make from here on will be tracked。 and then at the end。

 I will use the Git commit command。 The staged area is really important because you're essentially preparing to get all of the files and changes that you want as part of whatever feature you're working on。

 Basically you are getting all of that content ready for commit。

 You also have to remember that this is only on your local machine。

 The distributed manner of Git means it will only push to the server using the actual push command itself but any change you make here is only specific to you and your local machine Anyone else who pulls down the project from Gitthub will only get what's available on the remote server Okay Now I want to explain to you how to run the Git commit command First type in Git commit。

 you can pass in a flag of dash M which stands for message allowing。

To type in a message which will be attached to the commit in this example。

 the message is adding a new file for testing next。

 press return on the keyboard and now notice that the response states one file change zero insertions。

 zero deletions。There is also a create mode statement with the name of the file test do TXT。 Finally。

 if I run the Git status command， the response says that there is nothing to commit and the working tree is clean。

 however， I want to be aware of the message at the top of my screen This message tells me to use Git push to publish my local commands and this ties back in with what I mentioned earlier All of these changes are on my local machine and they will only be uploaded to the remote server when I run the push command you learn more about the push and pull commands in a future lesson。



![](img/8e103a3c07b3abc47226a4be6c739acc_5.png)

![](img/8e103a3c07b3abc47226a4be6c739acc_6.png)
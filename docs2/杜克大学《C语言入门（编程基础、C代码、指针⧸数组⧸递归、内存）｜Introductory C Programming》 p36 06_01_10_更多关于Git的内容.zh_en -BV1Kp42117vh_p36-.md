# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p36 06_01_10_更多关于Git的内容.zh_en -BV1Kp42117vh_p36-

![](img/0bea18ca6c2c359d4041c8e647fe6816_0.png)

One reason Git is so popular amongst professional software developers is the features that it provides for working with others on a large project。

 Let's suppose that I have my Git repository here， and I want to collaborate with Genevieve。😊。



![](img/0bea18ca6c2c359d4041c8e647fe6816_2.png)

Not only do I need to get a copy of Drew's code， but we also need to both be able to make changes and merge those changes together easily。

 Drew's code is on his laptop， and I want to work on it on mine。

 Since our laptops aren't always available， we'll make another repository on some server。

 we both have access to。One of us runs Git and knit to set up an empty repository on this server。

Then I need to tell get on my laptop that I want it to work with a remote repository。

You can name the remote anything you want here I called it Xyz as our hypothetical server is xyz。

dukeedduu， and you give it the location of the remote。

The only thing this does is make an association with the remote location。Now I run Git push。

 specifying the remote's name in this case， XyZ， and the branch I want。

 which is called master by default， the main branch in a Git repository is called master。

The set upstream option makes this a default place to push and pull。

 We aren't going to go into branching， but it's an incredibly useful feature of get。😊。

Now Git will copy not only all my files， but my entire revision history。

 every commit I've ever made and the log messages that go with them over the remote Now I want to make a copy of the repository on the remote so I'm going to use Git clone。

 I specify the location to clone from This is the same location that drew specified but I'm using my own username to authenticate myself This will create an empty repository on my laptop and create a remote called origin。

 which is automatically set as the default place to push and pull。



![](img/0bea18ca6c2c359d4041c8e647fe6816_4.png)

Then get copies all the commits from the remote。Now， I write some more code。

 test it out and add any new files I created to get。 Then I do Git commit。 Now。

 my local repository has these changes， but nobody else does。 including my repository。

 which doesn't have her changes。 In fact， I may not even know that she has done anything。

 I want to send these changes to the server， So I run Git push。

 which will copy any new commits to the remote。Meanwhile。

 I've been writing some code of my own on this project。

 So I do get commit and create another commit in my own local repository。 Now。

 I'd like to make my changes visible to Genevieve。 So I run gett push。 However， I run into a problem。

 When I do get push。 I get this error message。 geez， Drew， that error message is log。

 You must really screwed up。 Well， let's take a look at it and see what it says。

 It says that the remote has work that I do not have locally。

 You mean all the code I worked so hard to write Testin debug。 Maybe I should get that first。

 In fact， get suggests exactly that。 I should use gett poll to get Genevieve's work first。😊。

If I run Git poll， Git will copy Genovve's commit to my computer。

 then it will merge my work and her work。 if we have changed different files or different parts of the same file。

 Git will handle this process automatically。 If we've both made different changes in the same area。

 Git will tell me that I have to manually figure things out。Now， Git will put Genevieve's commit。

 as well as a new commit for the merged work into my repository， since this is a new commit。

 Git will ask me to enter a message， the default message says it merged our work which is fine with me。



![](img/0bea18ca6c2c359d4041c8e647fe6816_6.png)

Now I can try to run Gitpush again。 This time， it works just fine and copies my new commit to the server。

And then I can get Drew's latest code by running Git pull。

 which will copy those new commits to my local repository。

That's an overview of the basics of working with remotes in Git。

 Use Git pull to git commits from the remote and use Git push to send your own commits to the remote。



![](img/0bea18ca6c2c359d4041c8e647fe6816_8.png)

We talked about this in detail not only because it's incredibly useful in software development。

 but also because it's how you interact with the grading system in this course。

 You push your code to a remote and the grader pulls your code。 It grades your submission。

 then commits your grade do T X T file and pushes it back。 You then obtain it with Git pull。😊。


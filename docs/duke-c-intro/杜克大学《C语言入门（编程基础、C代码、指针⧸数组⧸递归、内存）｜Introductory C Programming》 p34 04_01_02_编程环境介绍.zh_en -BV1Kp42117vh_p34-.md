# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p34 04_01_02_编程环境介绍.zh_en -BV1Kp42117vh_p34-

![](img/3d9924ba8be91f67edd47a734661e471_0.png)

Okay， now you're ready to start actually writing some code in a Uniix environment。

 We're going to take a little bit of time to introduce you to how to use this environment。

 how to edit files， how to use Gi and various other tools that you'll be using as you program so here I am in Coursera on the first assignment which is really just a walkthrough of using the environment。

 which will be coming up as the next item in Coursera so you can go ahead and open that up and follow along if you want。

I'm going to go ahead and sign that I'm going to obey the rules of Coursera's honor statement。

 I'm going to do my own work。

![](img/3d9924ba8be91f67edd47a734661e471_2.png)

And I'm going to click open tool and it gives me this window， which basically is a UniX terminal。

 so this is a thing called X term JS。 it gives you an X term。

 which is a standard UniX terminal in your web browser。

Now I'm going to make mine a little bit bigger， so I'm going to make it like 140 columns。



![](img/3d9924ba8be91f67edd47a734661e471_4.png)

![](img/3d9924ba8be91f67edd47a734661e471_5.png)

And 36 rows， just so I have a little more space to type。

 and you'll see that it says this is my first time here。

 it's setting things up and welcomes me to the practice programming environment。Now at this point。

 you're probably a little unfamiliar with UniX and command lines and stuff。

 you'll have some readings about these。 you'll get lots of practices you go。

 The first thing I'm going to do is type LS， which tells Uniix to list the current contents of the directory and we'll see that there's a readme file and a directory called learn to program and this learned to program directory is going to be where you have all your assignments。

 This first one is00 hello。 assignment 0 and the first thing we're going to do is just write a file called hellello。

 It's not really a programming activity， but just to get you used to these basics before you start trying to write some code。

So if I open up this file， readme using EmX， which is the editor you're going to learn to use。

 it'll take it just a little second open。 and then you'll see that there's a bunch of text here so I can scroll around and read this。

And as we just said， your goal is to create a file called Hello dot text with one line that says hello。

 and we've given you some instructions here to walk you through this。

 So use emax to open and create a new file called hellello do Txt and it says type C dash X C F。

 So in emax speak， this is control X control F。 So I'm going to hit control X and then I'm going to let go of X and hit control F and you'll see at the bottom here。

 it says find file and prompts me for the file name So it gives me the path that is the set of directories I'm in leading up to this and I can type hellello do Txt which is what I want and then hit enter。

And at the bottom of it says new file， you can see it says hello。txt here。

 which is the name of this file， but unfortunately I've just lost track of my directions because they're over in that other file。

Eax has this really cool feature that lets you look at two files at once so I'm going hit control X2。

 it's gonna split the buffer in half。 so I've got one buffer at the top one buffer at the bottom。

 they're both in hello do Txt at this point looking at two different places in one file can be really useful but I want to change what's open at the top so it control X B and asks me what would I like to switch to read me is the default so I'm just going to hit enter and now I've got readme on top hello do Txt at the bottom and you can see I actually had those instructions here and if I want to move back and forth between these control X O you can see my cursor is jumping between the two buffers as I hit control X O。

Okay， so now I want to go into this and I want to write the word hello， and I'm going to hit enter。

 So there's a new line。 We generally end files with new lines。

 and then I'm going save the file with control X control S。

 and you'll see at the bottom it says I wrote this， this file。 it's now saved。Okay。

 now I want to grade this assignment。 So what we're gonna do is we're gonna suspend E。

 I'm gonna hit control Z。 You'll see it says stop Eax。 Read me Emax is still there。

 It's just kind of frozen in the background。 If I wanted to bring it back because maybe I forgot to read the instructions that were coming up。

 I can type FG or bring it back。 and you'll see that it tells me to run some commands with Git。

 Git is a really popular revision control system。 It's used by lots of professional developers。

 you'll learn about it a lot coming up for right now。

 what we're gonna do is we're going to add commit and push this file。

 which puts the file into git and submits our work to the grader。

 So I'm going to do git add hello do Tx T。 It doesn't say anything that means everything work correctly。

 Then I'm gonna say git commit dash M。

![](img/3d9924ba8be91f67edd47a734661e471_7.png)

![](img/3d9924ba8be91f67edd47a734661e471_8.png)

![](img/3d9924ba8be91f67edd47a734661e471_9.png)

Did assignment 0。 So this dash M says I'm going to give my commit message on the command line。

 It's just a little note about what what I'm doing right now。Ts it committed it to master。

 and then I'm going to do get push， and it sends it over to a place that it shares with the grade。



![](img/3d9924ba8be91f67edd47a734661e471_11.png)

![](img/3d9924ba8be91f67edd47a734661e471_12.png)

And so now you can see that the next thing is to grade the assignment， so if I do grade。



![](img/3d9924ba8be91f67edd47a734661e471_14.png)

It checks some stuff， make sure I've submitted all my files， runs the grader。

 it says I've passed this assignment， and it tells me that it's releasing the next assignment and that I should continue watching videos until I've watched the week one video about grading and that's gonna cover the materials that we need to do this assignment。

It also says if I run Git pull， I'll get my grade report and the next assignment。 So Git pull。

 kind of the opposite of Git push。 I'm gonna get assignments that were released to me。

 If you were developing professional software， you'd be getting code that's written by your collaborators。

 and you'll see that I got。😊。

![](img/3d9924ba8be91f67edd47a734661e471_16.png)

![](img/3d9924ba8be91f67edd47a734661e471_17.png)

Now there's a file called grade。Txt。In this case， it just says my file match the expected output because there's not really much that it can tell me about this。

 But in general， this is where it's gonna tell you which test cases you pass。

 which ones you fail and， and something about your grade。 And so then。



![](img/3d9924ba8be91f67edd47a734661e471_19.png)

We have the next assignment will'll be ready for you to come back and do that after you've watched some more videos。



![](img/3d9924ba8be91f67edd47a734661e471_21.png)
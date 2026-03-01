# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p06 06_01_08_AWS CodeWhisperer Rust功能介绍.zh_en -BV11y411z7Dn_p6-

![](img/5bf5fcfa13359bf495adf0d037ccfdf8_0.png)

Amazon Code Whiser is an AIpe programming tool that helps you build code programmatically。

 Let's take a look at some of the documentation here。 You can see that it's an AI coding companion。

 and it integrates with an Ide。 So it works both with visual Studio code。

 which is an excellent way to use it， or it also works alongside the Aws cloud 9 environment。

 Let's go ahead and take a look at cloud 9 here first。 If we look at cloud 9。

 one of the things I like about it is it's easy to spin up new disposable environments to test things out。

 if I go through here and I say create environment。 we go ahead and say test。

 I could go through here and pick from lots of different options， including some beefy machines。

 for example， if I went through here， there's a huge list of really large machines。

 including raw metal machines。 If I wanted to play around with it。

 and I also can build something on Amazon Linux， which also helps me make sure that the code I writing is going to work well for the Amazon。



![](img/5bf5fcfa13359bf495adf0d037ccfdf8_2.png)

![](img/5bf5fcfa13359bf495adf0d037ccfdf8_3.png)

environmentvironment you can also set timeouts here。

 which is a great way to configure and you even can SSH inside and control it that way or even put it into a VPC。

 So I've already got one running here that I have some AWS codeWhi integration already going let's go ahead and take a look at how that works。

 So if we go to this icon here AWS you can see here that I have some information here about AWS I could control different services。

 I also could go to developer tools and here where I've got the codeWhi open here you can see here that it's actually actively serving out the instructions for my code。



![](img/5bf5fcfa13359bf495adf0d037ccfdf8_5.png)

Let's go ahead and go over to this particular example and notice with rust here I can actually put a comment in this case I said build a function that prints 1 plus1 and I was able to actually do that and then I was able to add this in so let's go ahead and find out where that's at this is in hello so let's go ahead and see the end to hello。

And from here， if I just type in cargo Run， you'll see that I'm able to actually use those suggestions and change my code。

One of the things to point out here is that in order to get rust working on cloud9。

 what you'll need to do is run this rust up command， if we go through here。

 we say run the following on screen， you just copy it。

 paste it in very easy to get working here and it's going to say you know proceed with installation。

 customize installation， cancel， I've already done this so I'm just going to cancel it。

 and I'm not going to need to do it again。

![](img/5bf5fcfa13359bf495adf0d037ccfdf8_7.png)

![](img/5bf5fcfa13359bf495adf0d037ccfdf8_8.png)

Now in terms of building more stuff， let's go ahead and build it from the very beginning here。

 let's go ahead and CD up a directory， and let's type in cargo and we'll call this CW project and this will be a code whisperhi project。

And we'll go ahead and say new。Qu。😔，Create that。Now go ahead and see the into this。And from here。

 if I go and I look at the file that's created inside of source here， this main do R S。

 this is the file that's got all of the intro level things inside of it。

 So it gives us the hell a world。 Let's go ahead and do cargo。Run， this will go ahead and run it。

 Now， let's go ahead and use code whispers now。 So what I'm going to do is I'm going to say。

 you know， build a calculator。 So let's go ahead and build a multiline rust comment first。

 which is a great way to you know get things cooking originally will say this is a script that acts as a basic calculator。

So this is this is setting up the context for our program。

 This is really important when you're building something with an AI peer programming tool is set up the context first Now what I'll do is I'll start to guide it so we can go ahead and say you know you standard IO great let's go ahead and write great。

And it's going to go ahead and give us suggestions。 Now。

 we don't have to take these suggestions if we don't want to。 In fact， in this case I'm not going to。

 I'm just going to go ahead and put my own suggestions。 I'm going to say， you know。

 create an add function。So it's up to you to really guide this thing just like you would with a coworker。

 and here we go。 This looks pretty good。And now it's going to go ahead and return the final bits of this particular function。

 perfectf。 Now， what I can do from here is I also can incorporate it。And we can say， you know。

 add to numbers。And we can go ahead and do this。 We can say let results Not with rust here。

 I'm actually defining a variable that's going to be used for my results。

 And then I'm going go ahead and print this out and notice it's going to do a substitution here to get this working。

 So now if I go ahead and I say cargo run。We can go ahead and do it。 And oh。

 it looks like there's a problem。 and it says， you know， undisclosed delimiter。 In fact。

 that is a problem。 This is one of the nice things about using a very powerful language like rust is with a conjunction of code whisper。

 It's really the best of both worlds。 The compiler tells me what's wrong。

 And then the AI pair programming tool helps me build out the code。 What's it going to do。

 It's going to say there we go。 It's going finish off that code block。

 Now let's go ahead and let's do this。 We can go ahead and say cargo run。

And now it's going to go ahead and it's going to build that out。 Now。

 a couple other things that are interesting to point out here is that if I go over to another project。

 I've got set up here。

![](img/5bf5fcfa13359bf495adf0d037ccfdf8_10.png)

What I'm going to do is look at a make file inside of your。

And notice one of the things that I like to do is I like to do formatting。 So if we go through here。

 one of the things that is nice about cargo format is that it will actually clean things up for me。

 So if we go back into this environment and I type in cargo format。

 notice how it actually cleans it up。 So really the combination of asking for the correct。



![](img/5bf5fcfa13359bf495adf0d037ccfdf8_12.png)

Thing to build。 So this is setting the prompt， then guiding it step by step and then going through here and running it。

 So going cargo run and then doing a format， you're really getting the best of all of the AI pair programming components along with the benefits of the compiler。

 So let's go ahead and do one last thing here， which is extended。 So if I go ahead and I say。

Create a subtraction function。 So it's pretty smart here knows what I want to do。

 We can go ahead and we can put this out。And it's going to give us this in bracket， perfect。

 And then finally， we can actually go through here and we can put the second result。

And we can say here。We can do let。Res2， and we can change this to result2。

And let's go ahead and do cargo formats， and let's do cargo run and here we go。

 we've got -1 and we've got five。 So I think this is really one of the ways to leverage a peer programming environment is in some cases。

 pick the exact deploy target in this case， Cloud 9 because it's running Amazon Linux go ahead and ask for the suggestions。

 go through and run your compiler， but then also use the peer programming tool to actually really create a feedback loop to get the best possible results。



![](img/5bf5fcfa13359bf495adf0d037ccfdf8_14.png)
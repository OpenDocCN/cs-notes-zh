# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p04 04_01_06_GitHub Copilot Rust生态系统介绍.zh_en -BV11y411z7Dn_p4-

![](img/b89b95b1310f80bc067fa4675053ba95_0.png)

All right， let's go ahead and get started with what I think is one of the more exciting ways to be a software engineer。

 And this is to use coppilot inside of the Github ecosystem。 So not just by itself。

 but with visual Studio code， with Gitthub codespaces with Github， all those things together。

 allows you to level up in the old days when I first got started with Python， it was amazing right。

 I got into Python。 and I was like， wow， know I can do all these things script code quickly move the speed of light。

 it's amazing。 that's really the same feeling when you level up to a more powerful language like rust using coppilot。

 It's really that original Python experience， but the difference is you have a modern language。

 a modern packaging system， you have 50 times better energy efficiency。

 you have 25 times at least better performance for computation。

 you have better memory usage because it's a very memory efficient。😊，And also in terms of security。

 right， you're building a very safe concurrent you know build through the compiler and also safe from a cybersecurity perspective。

 So there's all these awesome advantages。 So really the question is。

 is it worth the penalty to use a slightly more complex language with coppit It is。

 because you can use the existing knowledge you have as a Python programmer to apply that to rest to level up your company。

 So I think this is going to be an emerging skill in 2023。

 And Python programmers don't have to throw away everything they learned。

 they can apply that with the techniques I'm about to show you。 All right。

 let's go ahead and get started。😊，Alright， let's take a look here at a rust new project template using the Github ecosystem。

 and really this is the magic right This is why Copit allows you to level up your existing Python programmer you want to go to the next level I would highly recommend Github codespaces plus copilot plus visual Studio code。

 this is the secret sauce so if we go through here we take a look at this we have a docker file that configures my environment with all the things I need。

 we also have inside of your dev container that configure features for example。

 like copilot and in addition， what this means is that I can start this whenever I want with a new project and so this is really the secret here is I just say。

 hey， I'm gonna to go ahead and use this， I want to test my code automatically everything is set up for me。

 Let's go and use this template let's say create a new repository go ahead and select the additional options here。

 and pick a nice powerful machine so I can compile my code。😊。



![](img/b89b95b1310f80bc067fa4675053ba95_2.png)

All right， so we're inside of this environment here。 Let's just double check that everything works。

 One of the things that we can do is look at this make file here。

 which is a great idea to initially have in your project。 If I type in make rust version。

 what's nice about this is it tells me all the nice things the version of rust， all this stuff。

 and this comes for free this is the big difference with Python， you don't have to do anything。

's it's ready to go So if I want to create a new project。

 what do I do I just type in cargo new hello Marco let's go ahead and build a Marco Polo app。

 if I go through here， look at this。 I have a packaging system all set up for me。

 So what I need to do here is inside put the dependencies that I care about。

 And so what I'm going to do is I'm gonna to go ahead and put camemelan tool library here called Claap。

 which is a really popular one and then it's up to me to decide the structure。

 So if you're Python programmer， I would recommend going through here and going to source。😊，In。

Actually， first seed into the to the directory and then touch source and make a lived RRS。

 And this is where I like to put my logic。 And， and here is where we also can build out some。

 some amazing things here by using Copit。 And this really is allowing us to leverage essentially our skills from Python。

 So we can first create a comment here that says， you know， a Marco Polo game。😊。

And then it's up to me to create the right prompts。 So what I'm going to do is I'm going to say。

 you know， you know， if the name。Marco is given the program response with Polo。Otherwise。

 we'll say what's your name， right， That looks pretty good， right， So。

 so it's just like a real person。 We just need to to prompt it correctly。

 And then I'm going to say as well， some some additional prompts here。 And it's up to us again to。

 to really kind of guide it， right， So we， we want to， we want to do some stuff。 Here we go。

 and as long as you're。Helping it along the way， it's going to give you a good response。

 And in this case， we say look public so expose this to my main module。

 which I'm going to use for Cammean tool。 And then look at the rest。 it's actually pretty intuitive。

 Look we have a string here for the name。 we do some stuff with a string and then we return a string right very。

 very intuitive。 Now let's go to the main here。And the trick with this is a lot of times all command and tool libraries are boilerplate code。

 And so what I'll do is a lot of times if I'm building something。

 you know I'll just cut and paste it from some other program to again helped our prompt here。

 So I'm going go ahead and just throw some stuff inside of here a commandline tool to play Marco Polo Marco Polo game And this is all just boilerplate code the big takeaway here is that you map a subcommand to the function that you've created inside of your lip。

 And this is almost identical to Python except for again， I get 25 times better performance。

 I can deploy binaries， all this other cool stuff。 Once I've done this， I again can just look， okay。

 yeah， I want to I want to pass a name into this。 and then what happen is I just ask copilot to do the rest for me and look。

 let's see what it does it says you in this case there's one thing its screwed up。

 we see that it's been able to generate a reasonable suggestion。😊，That's not perfect， right。

 I want to， I want to tweak it a little bit。 And so what I'm going to do is I'm I'm going to instead of letting it do the print name here。

 that's not exactly what I to do， right I want to send it Marco Polo。

 What I'm going to do is I'm going to say instead I' I'm going to tab and I'm going to say let results。

And then I would guide it to the fact that I have a namespace in the module that I can use。

 And so this is one of the things that may trip you up a little bit when you're first using R is like。

 hey， wait， what is this， What is this you know namespace is that this in fact。

 is what's inside of this cargo file right it's this name And so you have to actually map it to be the same name Now。

 again， what I could do here is I could just say。Make format and just see what happens if I format my code。

 Does it clean it up a little bit and what does this do it says fail to use unresolved crate。 Well。

 in this case it is resolved because that's actually the name of the oh actually the crate name is incorrect。

 the Li was telling me the right right thing。 So we have to change it to in fact。Hello， Marco。

Right we have to say hello， Marco。How about that There we go。

 right So this is where the analog tools right the cargo system as well as the copit work together。

 write the format at Li or all the stuff works together。

 And then I just keep iterating to get the solution and look if the Li passes， we're in great shape。

And now I can use the final part， which is I can actually go through and run cargo to execute it。

 So this is a lot like running thing from the Python interpreter。

 All I have to do is type in cargo run dash。 And if we do the double dash right here。

 it passes in some command back into our program。 And here we go。

 it's going to compile it now for the first time。 And the Ruk compiler is just amazing because it does all this really cool stuff to make your program safe and fast。

 we can see that it works。 And now I can type in play。 and we can type in Marco。

 and this should turn back。😊，In fact， unexpected argument play because we need to do dash name。Right。

 there you go， polo， and if I put in Bob。Right， it'll say what's your name， right？

 So this is a great feedback loop。 And again， look at this target here。

 if I just go through here and I say target。Debug， and I type in。The Hello Marco here。 Look at this。

 right， We see， in fact， I get that executable。 So this is a huge win over regular Python。

 in my opinion， because of this fast feedback loop。

 the ability to use coppit to level up and also to leverage this existing tool chain to have a feedback loop。

 So it's an emergent property of these new pair programming tools available from Copit。



![](img/b89b95b1310f80bc067fa4675053ba95_4.png)
# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p29 29_02_05_在Rust中解析复杂命令行参数.zh_en -BV1Hy411q7Zm_p29-

![](img/b947862773d5b1b3489578bd0db97b7d_0.png)

We've added a subcomment to our LS blog， wrappper in rust。But now it's time to add some flags。

 let's take a look at what we have here when we run the help menu。

 we only have some help and version and then we do have the subcomds right here。

 We have info for the device and then help you help for printing the message。

 So that is fine and this help， by the way， is the same as the dash dash help。

 So how do we add commands and maybe adding more complexity。 what's what's the deal。

 well it depends where you want to add them for sure。

 but in this case we are going to look at the ops the optionstruct and in here we are going to make it essentially we're going to do is make it global。

 So we're gonna add some global global flags and we're gonna to put them here。

 So how will we go around that。First off， let's start by adding a flag and we're going to do this right here and we're going to say always with our feature here。

 we're going to say clap。And we are going to do both short and long。

 which by now you should be aware that this will give you the the short version。

 which is a dash in a single letter and the long one will will have the complete name So I think we're going to put something here。

 but this flag is going to be the debug flag。 So let's just say we're going to say provide a better。

Output for debugging purposes。 So I think thats that's pretty good。 And I'm going to say that。

 And now below that， I'm going to actually add these comments。 I'm going to say yes。

 I'm going make it debug and it's going to be a boolean So we are going to say this is going to be a false or a true。

 and it's going to be a bullan。 So now if I run these if I run this again。

 which will take a second because it's going to have to build。 it going to come up with an issue。

 and the thing here is that I wasn't paying attention。

 I thought it wasn't about and this is actually not about this is actually the help menu。

 So if I do that and run dash help this will take another second to run because it's building and that's the right one。

 So this is one last building。 Let's take a look at what we have here we are going to add a debug flag flag。

That's going to be dash D short and dash dashDbu for the long format and this will allow me to provide some extra flags here that are going to show so let's just wait until these finishes and shows me the help menu Okay so the help menu was generated and we can see that we got the provide better output for debuing purposes coming from this one。

When we want to add a constraint here with this one and we want to default to something。

 we need to we can use these default value。 Now the suggestion here from from compile it says that we can use false within strings。

 but we want to make it tie into the type So here we have a boolean I want to make it a real boolean。

 we want to make it false and you cannot do it in this way。

 So if I close that and update that I can do it this way because the default value will only take a string so I need to use this neat feature that is default underscore value underscore T which allows me to do exactly that Now to check on that new debug the value。

 I can go here and do that which is say print print line I'm going to say the options that。

bug this is how you access them to print out。 So I'm going to toggle the terminal and I am going to run how about dash d for debug。

 and I'm going say inbda1 and let's let's wait a second until this completes building to check on the output Great So we have here the output and you can see that that's true we did pass dash D。

 but what happens if we don't pass anything。 So I'm going to say I'm not going to pass anything here。

 and then it's going to be the full value is going to be false。

 So that's kind of like what I was expecting and that gives me a good idea of how to add like a simple a simple flag for enable in debug How about we add a one flag for verbosity to add one for verbosity。

 What I want to do is make something slightly slightly different and we're going do here I'm going to say。

We're going to say short， long。And kind of like what I wanted to show you。

 which is something pretty cool is to an action and this action is going to be arg。

It's going to be our action is' going to be count and I'll tell you in a second why why why that is going to be count and when I save our voice level。

And yes， when I make it an unsign integer with8 bits long。Now， in order for this to work。

 we're going to have to get arg action here。 and that means that probably I'll have to update this one right here and say Arg。

Action and then curly brackets because that's the right way to do it。

 And now that our is going to be here。 Alright， so what's what's the deal。

 whats what's going on And while we go and discuss what's going on here when I say help so that we see what's going on So what is going on with our count and and what is it that we what is it that we're trying to do here。

 So what we're trying to do with these vervasity level is we're going to pass an additive type of flag。

 So we're going to pass dashv many times and we're going to allow that action to to be possible。

 So the reason why is because sometimes in command line tools we see that addition of that possibility of adding multiple values of the same flag So that vervo level can work in an additive fashion So if we pass that。

Allow us to do effectively something like。Like this， you know。

 we could pass that and then info Vva1 and then that would that would enable that super extra level of verbosity that we want Now。

 how do we check that right Because right now we're not getting anything the output and with that we wrap up this portion of adding complex command line tools or command line flags into our command line tool and the way we can do that。

Is by doing a match right， So we' going to say match ops ver level。

And we can say depending on the level， we can say what are some of things that the levels that we want and GiH compileities there helping us out and we are looking at all of these different options we can allow from zero all the way to2 and anything else would be too much verbosity。

So let's clear these and run it again and wait until it completes Allright。

 so it it said that this is too much verbosity because we passed in too many values so let's try it out with less value so1 v and it says some verossity okay but perfect let's try31。

3 so too much verossity it we say2 it says more verbosity so this one is coming in from this one right here and0 would be no verbosity so we don't pass anything。

We'll say no verposity。 So there we go。 So we have the0 all the way all the way to no verposity from0 all the way to 2。

 So this is no flags。Some verbasities one and two will be more verrosity and anything else will be too much verbasity。

 So there you go。 Those are some of the things that you can do in this command line tool。

 adding more things。 We've seen the types。 We've been able to set that to a boolean。

 and we've been able to have like an a action count right here。

 This is very useful when we're using it with an unign enter in of8 bits and this will allow us to use it in an additive fashion。

 So you can definitely build more onto those values as， as you see fit。😊。



![](img/b947862773d5b1b3489578bd0db97b7d_2.png)
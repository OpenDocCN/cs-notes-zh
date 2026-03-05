# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p10 P10 Write your own Operating System 9： Tidying up -BV1BDBEByEBY_p10-

Hello and welcome back to the tutorial on writingrit your own operating system。Now。

 in this ninth video， we are going to finally do what I told you I wanted to do in the last video already。

 We are going to make this。Commonplace directory structure with the directory for source files include header files and object files。

 so to make the whole project more tidy and so it doesn't get confusing over time。嗯。

So what I'm also going to do is。Y， but as I said， I'm going to make this structure with some subdirecties。

嗯。And all the classes will be put in namespaces， which correspond to the directories that they are in。

And also the if not defined directives will also be changed so that they correspond to the directory names also。

嗯。Yeah， and one more thing。

![](img/f5da50bbcb77c4396473c69ecbf77480_1.png)

With in the。In the make file。We will tell the。😔，The compiler to you。To use this directory。Let's。

Let's just do let's just do it， okay。I just created a directories source。Include。And he。

 as a directory object。 I think I'm not going to really。Put it here。 I'll just。

I'll put code in the make file which will create the directory if necessary。Okay， so。Yeah。

 as I've told you， I'll just move the CPP files into source and。It tries to include。Okay。

 and in here I will just create three directories again。😔，One， I'm going to call a common。

 This will for now， just contain the file。Type dot H。



![](img/f5da50bbcb77c4396473c69ecbf77480_3.png)

But in here you would also put stuff like IO streams， vectors， maps， whatever。So。Basically。

 something like the standard namespace in。嗯。And the usual C plus plus world。

Then a directory for drivers。

![](img/f5da50bbcb77c4396473c69ecbf77480_5.png)

。And here we put the base class for drivers。The keyboard and the mouse driver。

And one directory for hardware communication。 So， so basically。

 drivers and hardware communication will be something like different layers in the Aussie layer model that you know from。

From the network architecture， you know with。With the Enet layer 2， and。

The IP protocol and then the TCP protocol above that， and then protocols like HTTP above of that。

So this is really lower level， this is the stuff which you need to communicate on a raw。

And on a raw data basis。With the hardware and the drivers are really the language that these devices speak。

And I'll do the same here。好。Then I'll just reload the。😔，The whole project in the text editor。O。

I will also put。Yeah， has a。嗯。

![](img/f5da50bbcb77c4396473c69ecbf77480_7.png)

An additional prefix to these defined directives。

![](img/f5da50bbcb77c4396473c69ecbf77480_9.png)

And also， the name spaces。Neexus。不し。And you probably want to fast forward now。

 because this is really going to be very boring。It's basically the same thing again and again。嗯ん。嗯嗯。

Yeah。嗯。嗯。没对。嗯。っとう。对。Yeah。嗯。Yeah。Thank。嗯。嗯。Okay。Yeah。嗯。一。嗯。Yeah。嗯。嗯。嗯。い。嗯。Okay。嗯。う。嗯。Yeah。对不对。嗯。え。

Yeah。嗯。一。できる。嗯。Yeah。嗯。Yeah。嗯。Yeah。嗯。Yeah。嗯嗯。嗯。嗯。Yeah。一。嗯。嗯。嗯。嗯。Yeah。嗯。嗯。一。Yeah。不。Okay。ギリギと。He。嗯。Okay。

Okay。うう。いうこと。手机看。嗯。对。Yeah。嗯。嗯。有一。Thank。嗯。Thank。Okay。嗯。你个。嗯。Yeah。嗯。嗯。Yeah。In。嗯。Yeah。Yeah。嗯。



![](img/f5da50bbcb77c4396473c69ecbf77480_11.png)

Okay。So the next things we have to do is。Yeah， the object files are going to be in a different directory。

 so we have to change this in the make file now。

![](img/f5da50bbcb77c4396473c69ecbf77480_13.png)

ううん。Okay。嗯。Yeah。嗯。嗯。嗯。没。一动。嗯。Thank。Okay。Yeah。嗯嗯。嗯。う。Okay。嗯。Okay， and now what I've told you。

So we don't have this object directory right now， so we have to create this。Like this。

 but only if it doesn't already exist。So we can do this like this。😔，And in the clean command。

 we will not delete every object It's on its own。 We will just。Delete the directory。

So objectject directory。Okay， this will probably not compile right now， but I'll just try。



![](img/f5da50bbcb77c4396473c69ecbf77480_15.png)

Yeah。

![](img/f5da50bbcb77c4396473c69ecbf77480_17.png)

One thing we have to do also is dash。Capture I。And include so we with this。

 we tell the compiler to look for the header files in this include directory。嗯。

And that is actually why。Why I have changed these includes here too。😔，Includes with。

What these pointy brackets。

![](img/f5da50bbcb77c4396473c69ecbf77480_19.png)

![](img/f5da50bbcb77c4396473c69ecbf77480_20.png)

嗯。Yeah。😊。

![](img/f5da50bbcb77c4396473c69ecbf77480_22.png)

![](img/f5da50bbcb77c4396473c69ecbf77480_23.png)

Yeah。嗯。

![](img/f5da50bbcb77c4396473c69ecbf77480_25.png)

うん。Okay， so I'm actually surprised we got through the compile process quite fast now。😔，ok。Now。

 the linker is complaining that。This。Methods handle exception。嗯。Don't exist。And yeah。

 the reason for this is we had this。

![](img/f5da50bbcb77c4396473c69ecbf77480_27.png)

I mean， I mean， in the。Interrupt steps here。We have these。

 these strange names for these handle interrupt methods that we created。

 which are supposed to correspond to。This static。Methods here， right。

And because of these namespaces here。The internal names have changed。

 so the names we put here don't work anymore。So what we have to do now is， so if you look closely。

These names are constructed like this， they start with underscore the N。

 and then you have class names or namespace names。Preceeded with the length of the name。

And then in the end， something for the parameters。Of the methods。

So what we have to do now is we just have to put the for here。

 my OS for the length of the string my OS。And the interrupt manager is in the namespace heart， where。

comよ你。😔，O now， until this has one。So this has 21 characters， so I'll put a 21 here。

So the new name should be like this。😔，And we can just copy and paste this for my OS hardware communication。

And put them here。

![](img/f5da50bbcb77c4396473c69ecbf77480_29.png)

![](img/f5da50bbcb77c4396473c69ecbf77480_30.png)

Hey， awesome， everything works again， so this was actually easier than I expected。



![](img/f5da50bbcb77c4396473c69ecbf77480_32.png)

So。

![](img/f5da50bbcb77c4396473c69ecbf77480_34.png)

Great。Now， our project is a lot more tidy， and we will not get lost in there as quick。

And how we can really go on with the peripheral component interconnect， the PCciI。

which we will do in the next video because at this point the next steps that we will take is we will just add more and more drivers and protocols and stuff and now we have divided everything up nicely so that。

So that we can put everything where it belongs in a tidy way。 and yeah。

So probably you aren't watching this right now even because yeah， this whole video was really。

 really boring。嗯。And。You probably skip this because it was a lot and a lot of the same thing over and over again。

 but。So at least we are now in a situation where we have everything quite tidy and nice and so in the next video we can really go on from here so see you next time and don't forget to subscribe so that you don't miss the next videos。

See you next time。

![](img/f5da50bbcb77c4396473c69ecbf77480_36.png)
# 【从零开始用C语言制作游戏】 p10 Making a game in C from scratch! Ep 10： -Bitmaps and Subpixel Rende -BV18i421a7DD_p10-

Hello everybody welcome to this new live stream in in fact this is the 10th live stream in which we are creating a game in from scratch if you watched from the first live stream all the way to this one we've seen the whole process of us creating a pretty cool game。

 we started out as a breakout clone， but we is low deciding to implement more gameplay stuff。

 gameplay ideas as well as the fundamental level of systems that we need in order to create that。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_1.png)

So first of all let me show you what we have now in this series of live streams。

 this is the point which you have so far， so we start out at this breakout game and we added you know improve the game played in the last couple streams and the last stream we actually inserted a support for rotated rectangles so if you can see when we destroy the block the particles are actually have random rotations to them and the trail actually has it in pretty cool random rotation。

诶。And then we had like more game modes， which has like power ups and power downs。And。Yeah， let's see。

 We can get like a power up here like this。 Let's see。Yeah， see。

 so that's the state of the game so far， I think is。😊。

It's pretty cool I think we are actually getting somewhere pretty nice in these past this past stream and we're also going to do that today。

 we're going to improve on the engine so we can do more stuff so if you can see the power up and the power downs are just squares see they're just color squares。

😊，What I want to do now is actually make them bitns so the player will know what is the power up and what's the power down。

So he can make more a more informed decision on whether or not he will try to get that or try to avoid that。

So that is the basic idea to implement BMap support in our engine。



![](img/7011eb2fe997e9d598bb4046015d583f_3.png)

If you go to the YouTube page， you can see all those streams that I talked about。

 all the nine of them that are already posteding this one's the 1th。

So you can watch all of them in sequence and see from the very first line of code that we wrote all the way to the point at we are now。

And you can also go to the HIO page。

![](img/7011eb2fe997e9d598bb4046015d583f_5.png)

And here you can download the game and the source code。

 so you can see a couple of cool G and then you can download each day has a separate executable and source code。

 so you can download to see what the game is at at this point and download source code to play around and improve and change and do whatever you want with the source code and learn too。

 that's one of the big points。

![](img/7011eb2fe997e9d598bb4046015d583f_7.png)

Okay， so in order to start implementing bit mapps。I'm going to first create a bitnet。Right。

 that's kind of a necessary。 I'm going to do like a very quick programming a programmer art kind of bit map。

😊。

![](img/7011eb2fe997e9d598bb4046015d583f_9.png)

![](img/7011eb2fe997e9d598bb4046015d583f_10.png)

Just so we can。Or do you like。I'll do an eight by eight pixel art。Yeah。

 just so you can start playing around with that that's make like start with a yellow。啊。

AYlow power up。Okay。😊，Hey Muji goes， dude， nice to see you here finally， right。

 although I think you have watched a couple streams， right？😊。

Today we're going to provide Bimap support to our engine。It's nice to see you。

 You have to hang out sometimes， right？😊，Okay， so let's do like this is the invincibility。Power up。

I to do that。Another layer。But let's also know which way is up。And。Thats just like a pure green。

And a pure blue。Oh， actually， that was not pure green。

Just so we know which way is up and which way is down our bitmap。

Because we'd probably got that wrong the first time。Yeser day I watched that was pretty cool man。

 the yesterday we kind of stumbled upon a lot of problems。We did a rotateator react， but today。

 I don't know。 I think I'm pretty confident into a。What we're going to do today。

 so I'm going to create a data folder。Inside our directory。 And I'm gonna have like。The power up。

Invincibility。D to P&G， so the first thing we're going to do is actually read this file。



![](img/7011eb2fe997e9d598bb4046015d583f_12.png)

And。So in the Windows platform layer， I'm going to create。A， a functional comment is like file I O。

 We're gonna do file writing later on。And， so the basic idea is。We're going to need。

 We're going to pass like a void star。 Let's call that O S read。Entire file。

And we need to get the file memory and the file size。 I think I'm going to create a string。

Data structure。In the code thing going to do like a string dot C。Just so we can I consider。Our bits。

 our， our files just as strings， because， in fact， what is the string， I to do for now。

 at least going to。Let's say we have a character pointer called data and a sign 64 bit for the size。

So that's what we have。Prorerate。Right right， and Dan， let's。That's a。For these guys。Maybe up here。

春月。Okay。😊，And then I'm going to do like an internal string。String。Result。Okay， that's the basic idea。

 Now， we have to fill this guy and the calls that we want are actually create file。



![](img/7011eb2fe997e9d598bb4046015d583f_14.png)

![](img/7011eb2fe997e9d598bb4046015d583f_15.png)

To get the file handle， create a file A student yeah， this guy。

We can do like create file and we can also do， yeah， let's start with this one。Then， we have。



![](img/7011eb2fe997e9d598bb4046015d583f_17.png)

嗯。Is that a read file？

![](img/7011eb2fe997e9d598bb4046015d583f_19.png)

And S DN。Yes， and read file because this one takes a file handle。

 so use create file to create the file handle。

![](img/7011eb2fe997e9d598bb4046015d583f_21.png)

And then we can。3 that five win。Okay。So I'm going to initialize this guy。To0。And then， okay。

 so the file。

![](img/7011eb2fe997e9d598bb4046015d583f_23.png)

咋个快呀。Desire to access。 Let's see。 generic read。

![](img/7011eb2fe997e9d598bb4046015d583f_25.png)

![](img/7011eb2fe997e9d598bb4046015d583f_26.png)

Share mode。Let's do file share read， so other people can read this file as well。Security attributes。

I don't think we care about this at all。

![](img/7011eb2fe997e9d598bb4046015d583f_28.png)

Creation disposition thing we're going to try to do open existing。

 So we're going to have like an invalid handle if we don't have the file flags and attributes。



![](img/7011eb2fe997e9d598bb4046015d583f_30.png)

嗯。Let's see， I don't think we care about any of this。



![](img/7011eb2fe997e9d598bb4046015d583f_32.png)

Yeah。And template file， I don't think。Okay。I'm thinking on start start watching handmade He dude handmade heroro is really cool。

 It's what actually made me want to start programming for real for those who don't know handmadehero。

 which is handmhero。org is a series by one of the best programmers I have ever seen。

 which is Casey oratorri。

![](img/7011eb2fe997e9d598bb4046015d583f_34.png)

![](img/7011eb2fe997e9d598bb4046015d583f_35.png)

His code， he wrote like an image system。Which is like granny。



![](img/7011eb2fe997e9d598bb4046015d583f_37.png)

Rely。😊，And this animation system that he wrote is in over 4800 games and you a pretty small games like I don't know。

 Actvision news it。😊，Like。Let's see bune uses this for destiny， I don't know if you guys an evil。

 that's like a pretty small game， right？And yeah， another couple of small studios like Disney and electronic cards use for the Sims。



![](img/7011eb2fe997e9d598bb4046015d583f_39.png)

苏以。And he created he is creating， which is not done yet， he's creating a series。

Of live streams as well， where he's creating a game an engine from scratch。

 but he's doing like a very complete。Yeah， that pretty small。 Yeah， just very small games。

 He used his library， and it's pretty cool because the guy who wrote game engine architecture。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_41.png)

![](img/7011eb2fe997e9d598bb4046015d583f_42.png)

Engine architecture。Which is one of the ancient leadss at nightdi Dog。

Actually commented on the book that Granny was the best library that he had ever used。

 And this guy probably used a lot of libraries， so。😊，Yeah， this guy。



![](img/7011eb2fe997e9d598bb4046015d583f_44.png)

Who wrote works on this small game as well， Yeah， and so Casey does this streams and out start out from scratch。

And he goes pretty much like from everything you can ever possibly once from a game。

 starts out pretty simple， like 2D Tm based， then you start doing like optimizations in 3D and lighting。

 pretty advanced global eliminations， things like that。And I'm pretty much。

Pretty much think's going to go into the gameplay But since he's an engine programmer。

 you focus away a lot more on the engine and in this case， which is to answer theels question。

 what am I doing， We are creating a game in from scratch。 So this is the game that we have so far。

 This is the 10th live stream。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_46.png)

![](img/7011eb2fe997e9d598bb4046015d583f_47.png)

![](img/7011eb2fe997e9d598bb4046015d583f_48.png)

And we started out with a breakout loan right， so breakout and then start doing some crazy ideas with breakout like this is P。

But as a breakout game， so let's see。I' try to get the ball behind。Okay。

 then we also have space invadevars。How do you speak English so good， I don't know， man。I just。

Listen to a lot of stuff。And also。Practice and this live stream is actually making my English a lot better。

 so that's also that。Okay， yeah， we've got a frame rate drop pretty。Pretty big one there。

' going to have to optimize that later on。 So this is the game that we're building。

 but our scope is way smaller than cases。 So I think that's the main。



![](img/7011eb2fe997e9d598bb4046015d583f_50.png)

![](img/7011eb2fe997e9d598bb4046015d583f_51.png)

Advantage we want to release this game pretty quickly。

I'd say I'm going to guess they we're going to go up to 25 episodes， and this is the 10th episode。

So estimating that we have 15 like 16 more apps， so it's counting with this one， right？

AndButhe and hero were like he has a lot of experience。

 has been programming games ever since I was before I was born actually。He knows his stuff， this guy。

 and he goes to really advanced topics。 And I really。

 I really suggest that you anyone who who wants to know a more about programming in general。

 especially like game engine programming， should really， really watch that。 But in our case。

 we are now doing our。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_53.png)

File stuff。 So we。Should be able to create the file， right， and let's do like file handle。Okay。

 if the file handle is a invalid。

![](img/7011eb2fe997e9d598bb4046015d583f_55.png)

Handle。嗯。

![](img/7011eb2fe997e9d598bb4046015d583f_57.png)

That can see in the documentations。Return value。嗯。Let's see。Raled。Toight invalid。Oh， okay。

 now I'm create file， okay。

![](img/7011eb2fe997e9d598bb4046015d583f_59.png)

In value handle value。If it's。You valid。 Are we gonna do now。Is actually a ct？

And they're going to return。Result。But we want to actually， like a。嗯。errorir message。I don't know。

 maybe you can just crash at this point and'm to surprise how much already improved since that cow game jam。

 yeah， and it's been like one and a half years。And it was a lot， you know。

I think you remember on that game， Jim， that we were doing I was trying to do bitnap and I like the whole night to spend one night doing bitns。

 Today we're gonna do bitns。 So I think this is actually my real test to see how much I improved since last time。

 Let's see how difficult it's gonna be to be to do bitns。

 And it's gonna be take some independent bits。 So it's a little bit harder。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_61.png)

Okay， so if the handle is not valid， now we can possibly。Read file。

 I think I'm going to get to the file size。Bites， red， bites to read。 Yeah， we also need a file size。

 so。Let me just copied this guy。And let's do like MSDN。File size。You're going to nail it。

 I believe I hope so。 I think think this is not going to be that hard。

 I don't know famous last words， right？So。😊，The5 size returns。

A pointer to the variable where the high order。Is returned。 Can be no。



![](img/7011eb2fe997e9d598bb4046015d583f_63.png)

I don't think we're going to use like double word。

![](img/7011eb2fe997e9d598bb4046015d583f_65.png)

Which is like for  64 bit file sizes。

![](img/7011eb2fe997e9d598bb4046015d583f_67.png)

He honest do like the word。Size。I'm going to have to step through that。Let's see。

 this is the file handle。And this is， let's just pass zero。ok。5 handle。The buffer， we have。 Oh。

 then we have to allocate it。 right。 I're going do result dot size equals file size。

And result equals data。Equals let's do the virtual A call and since we're going to have like probably going to pack this up to a single file。

I don't think we care that we allocate at this point。So yeah， suggest I're not going to use like。

More complicated memory allocation stuff。Let's just do the results that side。Okay。

 now the file handle， the buffer result dot data， number of advices to read， Let's do file size。

Number of bytes red， let's call that。

![](img/7011eb2fe997e9d598bb4046015d583f_69.png)

喂。And overlap， I don't think we care about that。

![](img/7011eb2fe997e9d598bb4046015d583f_71.png)

Yeah， we don't care about that。Okay。Now possibly we succeeded。

 and I have to test like if this succeeds。And。😊，The file size。

And the file size is equal to the bytes red。Right。Like。😊，You also like。It's okay。And if we succeed。

 we are going to。Yeah， that's you like。Yeah。That's about it。Bite thread as to A word。Rightite red。

Okay。Now。First of all， that's called this guy， right， So in the initialized。你。When we initialize。

 we are going to。Like image。We're going to O read entire file。 We're going to go to data， slash。嗯。

Hower。

![](img/7011eb2fe997e9d598bb4046015d583f_73.png)

Power up， I don't know what I called it。What I call the image， let's see power up。嗯。😊。

Power up invincibility。

![](img/7011eb2fe997e9d598bb4046015d583f_75.png)

Okay。Do PNG。Now。Okay， now we have two for declare this guy。

And I think I'm going to do that on the platform common。So like。Platform。S， this is。



![](img/7011eb2fe997e9d598bb4046015d583f_77.png)

So far we only care about this guy。Okay， now。Let's debug and see if you got the file。O。Let's see。

 file path。This looks great， oh， we have to run from the correct button。

Now we are running from the default path， which is a build folder。

 I'm going to run from the root folder， so to ignore that build thing。



![](img/7011eb2fe997e9d598bb4046015d583f_79.png)

![](img/7011eb2fe997e9d598bb4046015d583f_80.png)

Okay， now let's go back and try to read this guy。So do we have a valid handle。

 Looks like a valid one。 Okay， the file size is。450， let's see。If that makes sense。That is perfect。

 so we allocate 450 bytes。And okay， so we read successfully。Okay， so our data shows our P andG file。

That' same here。See so has the PNG magic word。And all sorts of crazy stuff。And then。I don't know if。

Yeah。You said in the first episode is very much true watching this and thinking man。

 I don't know how to code。Yeah， talking about heade heroes cause， right？😊，Yeah， man， I mean。

 it's really hard when you actually。No， tell the computer what to do if you haven't done that before。

So。But it's a great learning exercise。 So， and it's only been like。😊。

I don't know two years since I started。Programming for real， I mean。

 I started doing that when I released Iosza's Hunt and that was like pretty much two years。

 next month is gonna be two years that I released Eliosza's Hunt。 So when released the game。

 I was like， okay， I don't know how to code， I have to learn that。

 That's where I started for real learning。 And I've done a lot of cool projects。

 I can show you a lot of good projects。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_82.png)

That I did to learn。And I can pretty。I'm pretty comfortable now doing this kind of stuff。

 but I want to do like more and more complex games。especially like lower level engine stuff。

 maybe when I finish this game， I'm going to do like a more robust engine with like open GL and shaders and multiplatform with Linux support and I don't know online subsystem stuff。

That would be cool。 Which editor I did would recommend。 Well， I really like farholderer。

 so I do recommend it。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_84.png)

You can download it for free on H aisle。Like， for coder。



![](img/7011eb2fe997e9d598bb4046015d583f_86.png)

Wch。哎呦。😊，There is a paid version， which is like 12 if you want to get the customization layer。

How are you called vim。 No， that's not vim。 You're talking about me。 That's not them。

 That's far codeder， this guy。And I really like for quarterder and you can download the free version here。

 the demo。

![](img/7011eb2fe997e9d598bb4046015d583f_88.png)

But I compile and and the to you。Okay， so we are reading the file。

Now what we want to do now is convert this guy， which is compressing a PNG kind of way to our format。

 which is basically going to be uncompressed because we have to read each pixelel right so for that I'm going to use Seann Barret's awesome STB image。



![](img/7011eb2fe997e9d598bb4046015d583f_90.png)

If you guys don't know， Seanun Barrett。Here's the。He was the graphics programmer for the engine for the very first the game。

You're talking about the very first one when people didn't know how to do 3D that well。

 he was the main graphics guy exporting the 3D territory at that point in time。

 so he's the real deal and he created all these cool libraries that we can use it's in a public domain and one of them is SB image。

It's a single file library like this and it's pretty pretty easy to use， really， really easy to use。

 I'm going to use that now。Co I'm learning C and using VS code for the moment。 I'll try for our code。

 Yeah， I think VS code has too much if you're programming like lower level stuff like you do like JavaScript or PhP or I don't know。

😊，Python that's great I think， but for lower level stuff I don't really like it I use it I use it when I do。

嗯。啊。Moria says 7000 lines of code and easy to use Well， let's see。😊。

He knows how to do and now he works at Ra game tools。

 RaD Game Tool is the company that when I talked about Casey， Casey released the Granny Library。

 right？

![](img/7011eb2fe997e9d598bb4046015d583f_92.png)

![](img/7011eb2fe997e9d598bb4046015d583f_93.png)

Re？3D， when he was working at Red and red releases pretty much all the the tools that most game majors use。

 So pink video。You can pretty much make sure that all 3A games use that use a video which is like all of them use B video it's like the best video library ever and they also have like this awesome I haven't used any of this just just for disclaimer because it's pretty expensive。

They also have like awesome formats and they have like all this stuff and Sean works at red and the point of red is to make not only to make awesome libraries。

 but to be very easy to use。 Let's see Muus， how easy to use is this library so。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_95.png)

I'm going to copy this。I'm going to create SDbimage。h。Okay， this library up top。

 you can see a couple of like release notes and it already tells us how we should do like do this before I include this file should look like this。

 Okay， so this is how we're going to do it。呃。See， this is how we implement and now we compile， okay？

I think they already have an assert。No， this is just a warning and expression is always true。

If I can either delete that or just remove the warning， I'm going to remove the warning。Cause。

Warnings are not errors。Okay， so now we have the library。

 let's go back to the top and see how should we use it， Okay， so here are the image formats。

Do you recommend any source to improve the process of learning C。

 I'm going to have seeing my next term in college， but I'd like to start the course in some。

Good knowledge in advance。 Well， it depends。 Do you have like prior knowledge of programming。

 I suppose you do， right， If you do have a little bit of knowledge in programming。

 I recommend like Ham heroes introduction to see。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_97.png)

If you go like to He。org。You can go like watch。And then you have。Here intro to C。I mean。

 it's not like。It's not like a very easy to be honest I'm going to throw the link on the chat。

 it's pretty advanced， so you've got to have prior programming but it's going talk about everything you need to know to get started like everything and then I suggest you just go ahead and watch my series from the very start and his series as well。

😊，Yeah， Java node。 Yeah， I think you can you can pretty much handle that。 It's gonna be pretty cool。

 And then you can watch my series and his series as well。 my series are pretty short。

 So the C programming language。 Yeah， so Marcuscus gave gave a nice reference in case you want to learn C。

 but I do intend to do。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_99.png)

Some my tutorials beginner tutorials as well。To the you says， what's up main long Techno C， dude。

 to we have to do like a meeting， right to get everyone together and talk about what everyone's been doing。

So yeah， it's been a long time， actually。Yeah， I mean， you guys， you guys graduated when I was like。

One and a half years ago， I think already。I don't know。That's pretty cool。 Okay。

 so that's the documentation。😊，So it talks about the limits but here is how we're going to use the library。

Yeah， I can configure that primary API works in all images of all type。 So this is the primary API。

 All you have to do is like， load。SVI load from memory， I'm not sure no that's not correct。Like。Yeah。

 I kind of skipped that I suppose。嗯。See。Yeah I kind of know how to use it。

 but I'm just going to show you guys， okay， so basic usage， this is the basic usage。行。Yeah。

 so this how use markets， you call SCBI load and it past the file name and pointers to the X and Y and the number of bits。

Yeah， and then if you have if you need a specific number of bits。

 and then they return to you the memory uncompressed。

So that's the basic usage and then you can free later on， but we're not going to free。

So that's how we do it， but instead of passing the file name， since we already read the file here。

 we can go ahead in our game and US SDBI。呃。Load from memory。Same thing， right？So， let's see， yeah。

Same thing I'm going to say where are we reading from， so are we' reading from image dot data。

 we have like image dot size。And then I'm going to pass an X， pass a y。

Pass a number of channels in a file， but we do need four Vs for channels。

 so we're going to pass for here， designing channels。Okay， and this should return， actually。Our。

 let's call them like you 32 pixels。This should be our actual pixels。

If you're not very much mistaken， I'm going to do into X。Yhy and M。Okay， let's see。

Function difference from that。Char。This guy I suppose？I think they expect。A。Yeah。

 let's get your voice。Comparation from。Very a big to end。I don't ever have to do all these casts。呃。

Let's go ahead and see the documentation again load。And free。 Okay， but we can also do。Okay了 see。

Yeah， I think that's it。Not from memory。Yeah， I'm just good， it's going to。You're going to cast。Okay。

 so we cast white start then we cast。To year 32 and this guy since we read。From3 to a bit。

 we can pretty much just guess to end。It rather than the stuff， no。

 we are really close to doing the fat stuff markets。

 The plan is today we're going to pretty much do these two bitms and pixel。

Subject to accurate renderry。 So next time we're going to do， let's see， we're going to do audio。

And then the other one going to do threading。 So I think it's going to be on the episode。😊。

12 so like two episodes from now。 Then you're gonna to do threading。 It's gonna be so easy。

 You're gonna be disappointed。 So don't get your hopes too high。

 It's pretty easy to get what we are we're gonna to do like a simple job system for the Rainer。

 and we're gonna to do like the whole audio threaded。Why don't you have notification on your stream？

Don't I have notifications， I thought I did， I don't know how this works。

 I should probably check that。I you know the date and time when you're going to stream it？Okay。

 let me do like an estimate。 So today's fight， if we manage to get these two today。

 which I think we're going to do， it's pretty early still if we manage to do these two。

 I'm going to do another stream maybe tomorrow afternoon。I mean。

 today like seven o'clock here in Brazil。Part time like four o'clock am I doing stream。

 thats going to be audio， so Friday should be like Sunday morning I suppose or Sunday afternoon I think Sunday morning is better。

So Sunday morning， Sunday， like around nine or 10 a BRT so can。Yeah， probablyly。

If youre need any help setting up to each stuff like notifications you can come later， dude。

 I think I'm going to need that because we've been doing that this for。Way longer than I have。

 I just started like last week。And I still don't know all these。Things's going Sunday sounds good。

 Yeah， I think we're going to get to that Sunday。Okay， so STDI， well。

 let's see if we do have our image now memory， right？



![](img/7011eb2fe997e9d598bb4046015d583f_101.png)

So let's go back to the result。Okay， oh， I go out of scope。Well。

 let's see if you still have the pixels here。Dude， there's so much stuff from features studio do。



![](img/7011eb2fe997e9d598bb4046015d583f_103.png)

Yeah， we don't。So I have to do it like that。Just in your life。



![](img/7011eb2fe997e9d598bb4046015d583f_105.png)

Just so we can debug from here。I'm also my third stream。TThird streamer year， dude。Yeah。

 I've watched a couple of streams like the better man series did。😊，That's pretty cool okay。

 so let's see these are our pixels， let's compare that to what we think our pixels are。😊，So we have0。

0， full， full， this is our first pixel。Which is blue。That looks pretty correct to me。Then， have 0。

Full，0，4。 This is green。Then should have like yellow repeated。Yeah， this is yellow， this is yellow。

 This looks perfect。

![](img/7011eb2fe997e9d598bb4046015d583f_107.png)

But there's a small problem。This is perfect， but we are top down our arrangeer probably is going to be bottom up。

I mean， it doesn't really matter， but it is gonna be easier because you can set like the pixels here and then just increment the way we're doing。

 So I'm going to pass a。

![](img/7011eb2fe997e9d598bb4046015d583f_109.png)

I don't know， bottom， let's see has like a bottom up。Alright， top down。Yeah。😊，There's no patting。

Coing find。They do have。A helper function that we can set or we can do like ourselves。To do， like。

Refer lightingverse。Yeah， let me just cheat and look at another code base。

I don't remember what it's going to be like。SCBI。No it was not in assets。Maybe it's in。不跟要。

Yeah a be gel flip。Aerically， okay。So we are going to set it to flip verticalrkeley。

 and then we're going to set it。O。

![](img/7011eb2fe997e9d598bb4046015d583f_111.png)

So now if we run， we should， we shouldn't have actually should be yellow。

 should have like this guy first， let's see our pixels。



![](img/7011eb2fe997e9d598bb4046015d583f_113.png)

All right， these guys。And yeah， we start with yellow。 Okay， nice。

 Now let's do our actual routine to draw。 So in the render， soft render， we are going to。

 I think we can， we can delete these guys draw transparent。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_115.png)

Reecting pixels。And the other transparent one， Yeah， because we did the rotated and transparent guy。

いや okayッケ。So internal voice， draw bit。That's pretty cool， right， we need。

Let's do like a bitmatstruct。We're going to receive a bitmap。And then， a P。A half size。

Let's do just this for now， then we can get like a color later on。And do some blending。ok。Okay。

 now let's specify。What you like。Max， let's do ourstruct bit。All we need now is the pixels。And。

Let's do like X and Y。Yeah， okay， so we have it pointer to a bitmap。And all we're going to do here。

We're going to do like the four， yeah， we're going to do the same thing。We， we do， we do in the。

Drrect。This guy。😊，And we're not going to do like rotation or anything as a start。 And then later on。

 we can add to our。对 so。Okay， so this is what we have。 We don't have a color we're going to do like。

Is do black well I of them。Okay， now in the game。I'm going to do like here B map。我开。

Then I'm going to do bit math。Dot pixels。It's going to be this guy。And then this guy's going to be。

The point your bitmap。x。It can out by。Yeah， that that's。And then here we're going to do。

To draw bitm and past the bitm。Pointer to the bit。And let's see we are at 0，0。现在就。听。

You're using Vm commands。Dude， it's not them， I think you're just troing right now。



![](img/7011eb2fe997e9d598bb4046015d583f_117.png)

。Yeah。

![](img/7011eb2fe997e9d598bb4046015d583f_119.png)

Yeah。Okay， so we do have a blue guy。 So the challenge。

 and now you guys should pay attention because this is going to be， as you say in Brazil。

 the cats jump， right， This is the important part。 If you get this。

 the rest is going to be pretty easy。So I also have to make sure that I get this。

We need to get the color， right？And。

![](img/7011eb2fe997e9d598bb4046015d583f_121.png)

And let's say， let's say we were drawing like this guy， let's say our bit mad is this small guy。

We need to know in a relative coordinate system， which is called UVV。Which is like zero， one and one。

 And this relative coordinate is relative to the size， right？

We need to know where we are here and where we want to get the guy here。

If you are like on the very first pixel， this should be zero and if you are in the last one。

 this should be one。And if you do have this number， we can just。Go to this guy and then see。

 let's say it's eight by8， right？So one should be the eighth pixel and a zero should be the zero pixel and then everything in between。

 So this is the idea we need to get this number and then we just learn to get the texture then we can do like some more advanced sampling later on。



![](img/7011eb2fe997e9d598bb4046015d583f_123.png)

Okay， that's the basic idea that we're going to do。小。啊，O。We start at this guy。Right。

I think we already have that function in our math library， which is a math。Map into range。

We have that。I think he's just going to call that。I think。So if you do like， let's call that。

There's the you。It's going to do the map inter range for the。This guy， the。The x。X 0 is the min。

 We are the x， and then we have x1， which is the max。 We have to make these guys。All at 32s。



![](img/7011eb2fe997e9d598bb4046015d583f_125.png)

Okay， so this guy should give us where we are at。0 to one on our target square。This guy。😊。

And all we want to do now is to alertlop。

![](img/7011eb2fe997e9d598bb4046015d583f_127.png)

To get where we want to be in our。Proltic square， our source square， which is this guy。Right。

 and we have to do the same thingme for the。For， I think I can do this out here。hy one。O好靠在诶。



![](img/7011eb2fe997e9d598bb4046015d583f_129.png)

Let's just see if for' not like stupidly wrong。So I'm going to go inside the dropet that call and let's let's see in our first。

Call U is 0， and v is 0。 That sounds about right。Now we are moving a little bit to the side here in the U see。



![](img/7011eb2fe997e9d598bb4046015d583f_131.png)

This looks pretty correct。So now that we do have the E theP。All we have to do is the fetch bitmap。

So if we have the pixel， which is a bit map。Dixels。

 and we have to set the color right color going to be bitmat pixelels。That's U 32， correct。

 in effect just。Just we can do like very slowly。If we are。If we do this， we should be all yellow。

 which is I'm just getting the first pixel。Yes。Let's see if you have a yellow guy。No I no。

 this is unexpected。Yeah。

![](img/7011eb2fe997e9d598bb4046015d583f_133.png)

Let's see。Oh， maybe our pixel format is different， I'm not sure， let's see。We have FF0，0，00 f。

This should be yellow。Let's see hacks what our colorss are。Hm， that's weird。The color that we got。

From this guy。A so totally。Not。Correct。Where are you from， I'm from Brazil。Well， I think。

Is that we may have to switch。Our RGB。To be BRG B GR， I think。

 but let's just not worry about that and let's see what we have for our image。



![](img/7011eb2fe997e9d598bb4046015d583f_135.png)

Okay， now we're not going to fetch the first one。We have to add an X and a y times the bitmap。Yeah。

 we have to know like。Let's call that UI。And we have to add like a EI。Which is times that bit now。喂。

Okay。😊，Have your English is crazy Plaia Pia， dude， Where are you from here in Brazil。

 I'm here in Bel O。😊，I have a very strong。Aent from Minjes， my40s accent， everyone。

 whenever I travel around Brazil with our game， Io Hunt。😊。

Everyone could tell right off the bat where I was from here in Brazil。 Okay， so we have to。😊。

See where our。You pixel is， I should call it that like。APixel X。And our Excel flag。Exxle， X。

Let's speak so why。Brazil too， I'm living in Canada， dude that's awesome。That's pretty cool。

 Do you have like a。Were working with development there at Canada， they'll be pretty cool。

 there are a lot of awesome game companies right in Canada。Okay， so what we want to do。

 that's simple， pretty simple。 All we're going to do is learn。From the first pixel， which is0。

And in our view， coordinate all the way to the bitmap。呃。喂。Okay， this should give us。The pixel。

We should be brainery。But this guy is in float。So the way we convert this。2。

To our actual pixel becauses that's。就 see。😊，Let's see if we are right here。 We are not。

We're not in the green pixel， but we're not in the yellow one either， we're right here。

The way we choose each pixel so that we want to interpolate。That is our sampling function。For now。

 all I'm going to do is I'm going to。At 0。5， you're going to make it round。To the one。

 and then I'm going to floor it with the int。Okay。😊。

I think I'm going to call it a bitmap width and height instead of X and Y。I think that'll be easier。

St he said。 yes， that's awesome。 I love speaking English as good as him。😊，Well。

 it loved speaking as well as me， not as good as me， I'm just kidding you。

I got so much to improve of that as well， okay， he' speak better than me and I am already completing one year outside Brazil。

😊，Yeah。Okay， I was just joking。呃。One nice strategy to improve the English。Just prove my point exec。

AP nice tip。Is to like， listen。To a lot of people talking like Americans or a British depending on the kind of accent you want。

 right， a little bit faster than usual。 So if I watch like a stream。

I usually put it like a little bit faster。 So my brain kind of processes the language more than naturally。

 And that really comes over time。 So and have to。😊，I have to break it light as well。Okay。

 conversion from in to to after into2。Yeah。😊，And if we're not going to lose any data。

 trust me this as well。Okay， convert from end to to 32 what？Which one talking about this guy。

 this guy。The0。At 23。O。Conversion from float to end， possible loss data。Yeah。

 because these guys need to be in parentheses。My listening skills are pretty good my real problems when I need to speak right。

 that's what I did too， it really helped improve my a lot of my English， mainly the listening。

 watch online courses。Yeah， I don't know， my speaking kind of it just came from listening a lot。

 I suppose， and it's truth be told。The morning before my first dream。I was just walking on the park。

And then。I was repeating myself， I was talking to myself what I was going to start doing like the very first introduction that I explained like the context。

 things like that and I was I talked like four times the whole thing right so okay。

 that was gonna be way better when I do it right but yeah that was that was a one way to get a more confidence。

 especially in the streaming thing。😊，Right。But know呃。You should streaming English dude。

Even if it suck in the beginning。Like。I did some pretty， some pretty， you know， massive things on my。

 my first couple of streams。 I there's one that I was like。😊。

I'm going to do this nowh and now is the thing say in Brazil。 that means okay。

 so just came out naturally。 That was pretty funny。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_137.png)

Okay， now let's check out these values， so the UV are zero。And。Okay。

 so our lub should be the very first pixel， which is the zero pixel， yeah。

I don't know if zero is actually a word in our color。😊，Which is。Yeah， a bit weird。Let's see。

 next time around。We are still 0。Let's do like this a couple times。N， exactly。ねえ。嗯。Okay，0，15。

 since we are 8 by8 image。 I think we have to go like， wait， yeah。

This guy should be a different color。Pix up2。So we moved to the other pixel。

 I think this is going to work。

![](img/7011eb2fe997e9d598bb4046015d583f_139.png)

I think is going to work I don't need to do let me go back to the software。

 I don't need to do this every pixel so I can do I can do it like this。And I could probably。



![](img/7011eb2fe997e9d598bb4046015d583f_141.png)

That'll be good now let's see what we have。😡，Hello， man。 How are you today， I can see the game。 Sure。

 I'm great。 How are you doing， Oh， dude。 Look at that。😊，How about that， dude。

 So he brought pretty much good luck for us。 We have a couple of problems。😊。

But those aren't big problems， I think。The first problem is。Our colors are wrong。

This is just near on this stream slaggy here it is okay and it says that the bit rate is pretty good。

 it's like 2000。Okay， yeah， I see our colors。Well， you're very observant， very observant of you。

 Marus。So obviously we didn't get yellow， we got green， so green's correct。

We pretty much just swapped our red and our green channels， our red and our blue channels。



![](img/7011eb2fe997e9d598bb4046015d583f_143.png)

嗯。😊，Yeah， because Windows actually does B G， BGRA colors。You know what I think I'm going to do。

 I think I'm going to when I initialize。Our bitmap that's you like。

I'm going to like make a function out of this。Do like this for a while。I'm going to run the whole。

Bthmap。で、すね。はい。Yeah。😊，Okay， let's do y for X。なんです。Okay。

 so we're going to run through the whole bit mapap。

And I'm gonna do is I'm gonna set the that you like。Pixel。We this guy， and we're going to do pixel。

It's going to be。Let's swap these channels， right， the pixel。And with this guy。This is the blue。

 right？ So this guy， we have to offset。To search the red by 16。Proably gonna to be wrong。And okay。

 so now we lost the red。아。Yeah， let's do this low way just for us to understand。

R is going to be the pixel。Yeah， it's going to be this guy。ああ。Yeah。

 this is the R they and have the G and the B。Tixel。Which is our favorite language so far？

I didn't know the game would have a colorbld mode。Yeah， I mean， we try to do as much as we can。

 you know， in our game。In fact， I don't need to。 I don't need to do this guy。Im need to shift。

 this is like the G and this is the B I'm going to shift。Let's shift by 16。Okay。

 so this guy'm going to build it like red。Oh， B shifted by nothing。Right。Or with。I to。Green。😊，Also。

 don't need to ship to that because we didn't ship to the first place。Ored with R shifted by。Oh。

 it's going to be right。And appreciate it's going to be wrong， but let's see， X， yeah。

 we don't need x in Y。Type one bitmap with， thanks guys， whooped。But map what what's going on。

 right shift to large amount of data。あ。嗯。The blue one。Oh the blue one is actually。Yeah。

 this is wrong。Like this is what I can。Right。Yes。Okay， so you're going to do like B， G and R。

Shifted by 16。

![](img/7011eb2fe997e9d598bb4046015d583f_145.png)

Let's step to this guy because this is kind of finicky。And we probably get it wrong。

You could just do pixel zero at this yeah， if I run like pixel through U8。



![](img/7011eb2fe997e9d598bb4046015d583f_147.png)

But we've average are cooler， Yeah， dude， let's do the coolest thing。诶。诶。Static。

Nonstandard static function integration function scope。Dude。Do we forget this guy。Yeah， we did。Yeah。

Oh so the problem was I should cast to U8， that's why the right shift is。They're all crazy on me。

Now I should be able to write shift。No， I still don't。



![](img/7011eb2fe997e9d598bb4046015d583f_149.png)

I don't know。Let's just see what happens。When we。Let me try。Here。So R is 255。G is0， and B。



![](img/7011eb2fe997e9d598bb4046015d583f_151.png)

Well， I'm not sure I can't see the。You can't do you it and then order them all together。

Y 32 was right。If you order them。Can youate and then order them together？Okay， yeah。 dream。

 dream is wrong。 Yeah， I see what you mean。I see between this is also wrong。And this should be， yeah。

I think I'm going to do like the actual U8 for everybody。A cheaper to amount。O。So yeah。

 thanks for catching that。

![](img/7011eb2fe997e9d598bb4046015d583f_153.png)

Yes， so now we should be more correct。I think let's see R255 G 255 and B is0。

 so this is correct and now this should be correct as well。



![](img/7011eb2fe997e9d598bb4046015d583f_155.png)

But now I have to shift all these guys， so I'm going to shift this guy by eight and they're red。



![](img/7011eb2fe997e9d598bb4046015d583f_157.png)

By 16。

![](img/7011eb2fe997e9d598bb4046015d583f_159.png)

Maybe maybe we just get this wrong again。Due this the other shit。



![](img/7011eb2fe997e9d598bb4046015d583f_161.png)

Okay。

![](img/7011eb2fe997e9d598bb4046015d583f_163.png)

Let's see。啊。😮，Just fix the colors。

![](img/7011eb2fe997e9d598bb4046015d583f_165.png)

But I think you're going to add like Muji Go suggested and if。



![](img/7011eb2fe997e9d598bb4046015d583f_167.png)

If colorblind mode。Just kidding。

![](img/7011eb2fe997e9d598bb4046015d583f_169.png)

Okay， nice， yeah， that's pretty cool now we are a bit weird。

But I'm not sure this is how we're going to roll。

![](img/7011eb2fe997e9d598bb4046015d583f_171.png)

I mean。

![](img/7011eb2fe997e9d598bb4046015d583f_173.png)

We are actually weird in a couple points。呵呵。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_175.png)

The first point， let's just compare， right？The two images， the first point in which we are weird。

Is that。We are cutting half our first pixel， right？The other point。Is that， okay。

I think I see the problem the other problem is this。And if you guys can see。

 we are not actually centered。See， so this is the image we're supposed to be drawing。



![](img/7011eb2fe997e9d598bb4046015d583f_177.png)

So this is wrong， go back， this guy's wrong。We're getting the pixel。

But then were offsetting by half a pixel。Yeah。

![](img/7011eb2fe997e9d598bb4046015d583f_179.png)

Let's just see the other result and we cannot play around it。我我 appreciate。HaHow about。That， guys。

Dude， that was so easy for our bitma support。And the thing is。



![](img/7011eb2fe997e9d598bb4046015d583f_181.png)

That was pretty cool。Yeah， I mean， we have a very， very ugly bitm if you' be tolded this like pretty much the ugly bitmap I could think of in terms of programmer art。



![](img/7011eb2fe997e9d598bb4046015d583f_183.png)

But yeah。Now let's do some crazy stuff with this guy。We're going to do static X at 32 x equals 0。

 Then we're going to do。X times equals dt。Dt times five， I don't know。And then I'm going to do。

The size。Just so we can see how well we are working in terms of。In terms of texture sampling。

So we're going to change the size and here's the x。



![](img/7011eb2fe997e9d598bb4046015d583f_185.png)

Let's see。I see some animation going on。Look at that， man。That's pretty awesome。

I don't know if you guys can see。I don't know due to the stream and stuff。



![](img/7011eb2fe997e9d598bb4046015d583f_187.png)

I am a this guy。Why is it not one？Yeah， actually can， really。



![](img/7011eb2fe997e9d598bb4046015d583f_189.png)

Since we are not sub pixel so accurate。When we move。

 we have that little weird thing in terms of subdixel accuracy stuff。



![](img/7011eb2fe997e9d598bb4046015d583f_191.png)

And that's the next thing we' want to do。But before we do that。We are going to do some program art。

And because F we are tightening up the graphics of the three， right， is that not what we are doing？

I believe that is what you are doing and just for the record。The animation on the block。Looks cool。

 Yeah， we added a lot of put stuff on the blocks， man， like。



![](img/7011eb2fe997e9d598bb4046015d583f_193.png)

If you see like this one， which has the partups。We have not only particle systems。

But we also have like。That was pretty。Yeah， that's awesome。 frame rate was。Yeah。

 we're going to do an optimization pass in a while。



![](img/7011eb2fe997e9d598bb4046015d583f_195.png)

The player party， yeah that's what happens when we have a very low frame rate。😊，It's pretty much。

 yeah， fixed3s k at low frame rates， we're going to do that。Okay， now let's do some pixelel art。

 shall we。😊，This is going to be pretty bad， I think， but it just has to be better。

Then what we have now， which is not going to be too hard， I suppose。So let's do like a yellow block。

 oh that looks nice。And let's do like a slightly darker border。Maybe， like。Like this。I could create。

Not a bug it's a feature。I thought it was intended。



![](img/7011eb2fe997e9d598bb4046015d583f_197.png)

How long have the programming in this game， this game dude。

 not very much if you go to the YouTube page， which is YouTube。comam Z Dan。



![](img/7011eb2fe997e9d598bb4046015d583f_199.png)

You can see the whole process in which we've been creating the game that's just quickly out of approximately have two and a half hours and four。

 so six and a half。8 and 45。Then we have。11。Is that it 11， let's say 12， 45？Then we have。啊。1645。Oh。

 is that right， Yeah， that right， so 1645。Plus3， you have 1945。Plus two and a half。We have 21， 15。

 22， 15。24， 45。25。27， let's say 28 plus we have like one hour today。没系 didn的咩。So。

We've been programming this game for 29 hours。You can see the whole thing on stream so this is like。

Three days， I'd say four days worth of program。Yeah， less than four days。

 three and a half days worth of programming if you were to do in life this full time and you can see the whole thing。

And that's from scratch。So。I think that's pretty impressive， so this game's been pretty。

It's not not too long。 so let's just make this guy a little bit cooler。Maybe we can add like。

 I don't know。Battle effect。I know this is very little resolution， going to be weird。Yeah。

 I think this is kind of okay。Although， it' was pretty bad。 so this is the。Invincibility one。So cool。

 yeah， I think we're getting a pretty cool result。Okay， now this is weird。

Trying to make like a shadow guy。And maybe just like this。

 maybe it's going to work for it or maybe you can do it like more theses。

Yeah let's do like this for now and then you can do the other ones。So this is。The invincibility。

Let's just remove this guy。Andlan。So this the invincibility one， we have the three shot one。So。

Let's do a 3。The color again。3 shot one。Yeah， well。That's so bad。 I I don'。

 I don't know what I'm going to do。I'm almost hitting the jam deadline。

I don't think I'm going to do the Pixar on stream， I don't know， I'm kind of thinking about that。

 the three shot and a comment。Because I'm not really an artist， so。

Not sure if this is going to be interesting to see or not， so let's see like。Okay。

 that was that was better， maybe the tea can do like the same thing， maybe not do like a giant tea。

Let's do it。Maybe you can draw that that that would be cool。 So we can draw。Like this。

For triple shots。I don't know， I'm going to do it like this。So this is our。This is our， let's say。

Comment power up。And then we have the triple shot。All up。Then we can do better later， but。

One step at a time。Say data and the triple shot。Okay。

 now what we're going to do is we're going to load these。



![](img/7011eb2fe997e9d598bb4046015d583f_201.png)

Oh first of all， let's make this guy function right so in this salter rendering。

We're going to do like assets later on， because for now let's just do the software and you're going to do like internal。

Bitnap， correct？Yeah， load TNC。And that's what we want to do to load our PE。Return。Oh。

 let's do like yeah。咩？Dit map。Result。Okay啊。Yeah， we can free this guy later on。

 but I don't think we care。嗯。So goodn pixels。Reult pixels。Result。Okay。😊，Return result。嗯。Yeah。Okay。

 now let's do a lot of bit math。So， we have。Play your stuff， let's see where we have that。

The invincibility。Let's do the kidnap。Power up。Invincibility。It math invincibility。Good math。吹风。

Bit mapap。And then in the initialize， we're going to load all these guys。load片机。

And after in the final pass。We are going to do。PC file。Things like that。But for now， I don't know。

I don't actually know for now let's just like a comment。And。So this is a bitm。Insibility。

Triple and Gin。Okay。😊，Okay， now when we draw。Power up 70。Power block。Yeah。

 this is it so instead of doing this。I'm going to do a switch。On the power block。Kind。

Case we are a power。啊，嗯行。St？You're going to draw。Good map。Dipnap in vincibility。These guys here。Okay。

 then we' going do the triple shot。And then we're going to do the。Comment。Okay， and the default case。

 which is which are the par downs。I going to do the red gun。Again we can。ICould to make him later。

 cannot convert， yeah， it's going to be it。Are you return a local variable？

like this you're talking about。😮，For that。For bitmap。I'm just straight up copying that on the stack。

Because the bitmps is like two， yeah， the result， yeah， this guy is just a pointer in two integers。

So yeah， I'm just pretty much returning the whole variable I could like。Since this guy's allocating。

 right， this guy's allocating for us。The the actual memory， this guy is also allocating and not free。

 like。We should probably like。I don't know。But this is an eight by8 that map who heres。

 so I'm just straight up copying the whole bitm to this tank， which is like eight bytes。16 bytes。

 par， yeah。

![](img/7011eb2fe997e9d598bb4046015d583f_203.png)

Okay， let's see if we have what we want。Okay， guys， you saw that。 You saw that。

 That was a divvincibility。 This is the comment。 and I like comments。 So yeah。😊，Another comment。

 dude， we are really missing our frame rate we got a lot of particles going on。Yeah。Okay。

 our incibility didn't work。Yeah， see。We should probably limit in this different loop we are running。

This is the particles stuff。So， let's see。We are now supposed to do like。

A lot other particles this strain。嗯。I don't know if you guys remember we we were doing the particles。

We said， okay， let let's get the the ball travel this frame。And。Just paw that number of particles。

So if we do， yeah， so this gets incrementally worse。But it does look pretty nice。

We are going to have two。

![](img/7011eb2fe997e9d598bb4046015d583f_205.png)

And you know what？嗯。Like let's see the tree yeah， this guy。I'm not sure。

 but maybe we should really do like one ball。

![](img/7011eb2fe997e9d598bb4046015d583f_207.png)

For frame。Most。Yeah， I don't know。 Yeah， not really。 since we do have alpha。I don't know。

 let's see how this looks。But having bitmas is so cool。



![](img/7011eb2fe997e9d598bb4046015d583f_209.png)

I'm invisible， okay， so we got it， we got triple shot and we were explaining invincibility。bit。出保。

Maybe I exported that Oh no， yeah。That thinks just a title。电边是隔里。Yeah。确过。Dan。

 I have some work to do and got to attend a meeting soon。When we were streaming again。

 dude we're to attend a meeting like Friday， eight o'clock in the night。Come on， I'm just kiding。

When will I stream again， probably tomorrow？I say four o'clock。

And then we're going to do audio probably tomorrow at4 o'clock。Yeah， and then Sunday。

Probably at 9 or 10 in the morning we're going to do again。

 and then we're going to do see Mars Sunday 10 or Sunday9 o'clock， approximately a。Brazil time。

 which is VRT。We're going to do multiread。That is going to be cool。



![](img/7011eb2fe997e9d598bb4046015d583f_211.png)

So。😊，Yeah， now we should be limited to one particle per frame。

 which I think is actually what we want if you can play around with the alpha。

To be a little bit more intense。Based on how much we traveled。Yeah。

But we shouldn't have like a million bazillion particles now。

 we shouldn't keep a particle economy which just for fun。So you comment， yeah。

 so see that was pretty reasonable and I don't think we dropped。Friend rate。

Now we should really have an invincibility and we do have the comment， oh， and this is a triple shot。

Oh dude。Yeah。But anyway， it's good stream。 I'll be there next time。 Thanks， man。

 It was awesome to see you here。😊，Yeah。Dude， adding that bitmap made a lot of difference and it's a pretty bad bitm。

That says a lot about art and game design。You know how really even though？

You know the game design has pretty much nothing to do with the art。

The actual feeling that player has when he plays the game， which is。

What the games I tries to accomplish has a lot to do with the art。It's a little bit of paradox there。

は。Yeah。

![](img/7011eb2fe997e9d598bb4046015d583f_213.png)

Awesome。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_215.png)

Yeah， goodbye， goodbye， man。O。So。😊，I think that was it， let's do the power downs。

Let's do the pardowns， let's add like a human saturation adjustment and let's make them look evil。

Like。That's kind of evil， but that's not readable。So let me drop this guy to the bottom。

And this guy here。Yeah。But then。I don't know。 Let's see。I say we do like black。And we have。

Have this low player inverter control， strong blocks。And needss to kill。

Maybe we should do like B for blocks。呃。Let's try to do a B here eight by8。

 I think I'm going to do 16 by 16。Yeah， let's do that。16 by 16 pixels。

 and let's do this nearest neighbors recycling sampling。Did that do anything？What happened？

I don't know what I did。But now I can't change it to pixels anymore。Dude。That's weird。

 I'm just going to create a new one from scratch。Yeah， see， dude。

 there's a lot more pixelel than now。Let's get these colorss。あ。Okay， now let's do it like this。Adobe。

Yeah， I'm about not to use a Photoshop anymore。I think。Let's see。Yeah， let's do like this detail。

I wish suppose do you like three。嗯。Yeah。O。That was。Reasonable， and then let's do the giant eye。

The eye of Saran。Okay， and that's the tea。I's saved that。Let's say that。As the triple shot。Oh。

 I accidentally saved。That on。this guy。Let's just quickly do that again。Okay。Let's erase that。Okay。

Now， let's do the。The invinsibility one。Oh way better， yeah。Okay。And then。Where is my？

Where is my glass， Wheres my， Wheres that cup of water， Where's my glass of water， Did I not get one。

I don't think I've got one。Artistry now， absolutely。If you can call that art。

 I think you' pretty much a postmodern at this point， marvelous。And a comment。

No let's do a C like let's do an artist C， still like this。Hm how about that？Isn't that artists see。

I'll got that around。好啊。Okay， that， let's see， maybe this guy。Where I at this guy like this。

This is not symmetrical for some reason。呃。Yeah。It' is not symmetrical。 Let's try and do it like。

That's weird。So。Yeah。It has to be something like this。Okay， oh， this is the problem。でか。Yeah。Okay。

Now we're looking good， are we not？うん。How about that？That's cool。

 We can even do like this as transparent pixels。If you want to do like Binap and transparency。

That could be cool。So this is the comment。Now let's do our。Let's do our evil pickupups。ok。😊。

This looks pretty cool， let's try to do like a dark gray。And。Let's try drawing us call。

Just because now this is an artist stream。Oh， not that bad， is it？Good luck。Dude， how bad was this。

 It's not like really bad。Mean， it's not really。Doesn't look like。Very deadly cool。Is missing knows。

Oh dude， that was oh， but a nice reference。Yeah， but I don't think you're going to do this kind of smooth。

 we're going to do like nice sharp pixels， som I'm going to do these pixels and me just turn this opacity down a bit。

诶。Let's do these pixels。Dude， that was totally not what I was trying to do。

But I'll certainly take that。Okay， we are not symmetrical。 Now we are symmetrical。Let's add a nose。

That I'd like。Yeahや。Nos like this。They look deadly enough。Maybe we should like。Hed a mouth like this。

Yeah。そ是そ。Maybe we should do like the bones or maybe。

I think that's going to be cooler than a skull I'm going to do it like a TNT。Yeah。

 let's do a T And T。T。And。T。That was actually surprisingly good。How about that， I like that。

So this is our inst。Powered down。Insta。Yeah， that's nice， yeah， I like that。Okay。

 now let's do the other ones， which are。Thats slow player。



![](img/7011eb2fe997e9d598bb4046015d583f_217.png)

I do like。Let's try to get like a traffic。

![](img/7011eb2fe997e9d598bb4046015d583f_219.png)

Like slow。Traffic sign。

![](img/7011eb2fe997e9d598bb4046015d583f_221.png)

Just for fun， I'm going I got some water。Like。Because I've been talking for like。An hour and a half。

And I really need to drink something， well a minute break。Yes。Okay， I'm back。

So we were we were doing the。

![](img/7011eb2fe997e9d598bb4046015d583f_223.png)

Which one we do the yeah， we were going to get it like a slow traffic sign reference。Yeah。

 I think you want to do that just for fun。嗯。Yeah， let's try to write slow in pixelix hard。

That was too big。ああ。Okay。嗯。Maybe you're going to do like a small L。And猫。Almost。We need more pixels。嗯。

Let's try to do like a smaller S。Pretty bad。Can we do like a two by two S？I don't think we can。

I don't think we can。あ。Like。嗯。Yeah， the W also going gonna to be。Kin hard。Drt turtle。Okay。😊。

Let's try doing that。

![](img/7011eb2fe997e9d598bb4046015d583f_225.png)

That's do like a pixel art。吃东。Yeah， that's just something like this。Oh，This one's pretty funny。Okay。

 let's do a chilltle。Then I still like。Oh， dude that。It's so bad。

Should I should make this guy a bit bigger。this guy like this。Okay， that's better。Okay。

 now let's do the little。Thefeat。And the tail。Okay， maybe。Or should I put a table here？Okay， oh。

 that wasn't too bad。I don't think。Lets。Let's try now。Some drive response。

That a light spot because we're doing lighting guys， this is like some probe pixel art。Yeah。

Then let is some ice。Yeah。It'll be funny。If we could。耶。Yeah， that's。That's to make it like。

Let's turn out as pixel great， how do we？Sec C's head。 No， this is the head。

This one looks pretty bad。Let's make just a time good talk。And let's do like darker green。

How about that？That was， that's pretty cool， isn't it？I like that， okay， that's ours slow。Farre down。

Now。We need。诶。What are the other ones。 Pretty good。 Yeah， yeah， yeah， if they turn out， okay。

 actually， no kiddten。I mean， it you look like。From afar like this。We could have more detail。

It would be like invertted controls。That's pretty cliche， right？We do like inverted arrows。Like this。

啊， that's。That's a really badarrow。嗯。I should make the arrow head first because that's the trickiest part。

ok。😊，Yeah， okay， I'll take that。I'll take that。Let's flip that。Yes。I don't know。

Which one looks better？This full I think this one looks better， full arrow。

We also have to move this guy。Yeah。😊，Not too fancy， but I think that would work。Okay。

 this is the inverted。And， I don't think I'm going to keep things to just I don't know。

And now that we know what part down we're going to face is going to be way easier and strong blocks。

I really want to draw like a muscle block。I don't think I'll be able to do that let's see we have a block。

And I want like some huge arms coming out of it。で。I think it's going to be true to abstract。Oh。

 actually。This is not too abstract。Is it。I don't think we can be able to do in both sides。嗯。开始。

That was actually pretty good， to be honest。I'm surprised at this idea。

Let's try to make this guys a bit darker。あと。Like this。It's kind of funny。But。

Let's see if you can still do the strong blocks。呃。And this amount of pixels。This。

Does it still look like a strong block？Thank you， De。But now we are one pixel off well。

Just make this guy a little taller。Wider。Yeah， okay。 this is， I think this is gonna work。This。Yeah。

Dude， how about that？I'm really proud of myself here。Let's get the hands a little bit darker。

As well as like the muscles。Nice ice， yeah。I mean， how do you think people get this？



![](img/7011eb2fe997e9d598bb4046015d583f_227.png)

And I said， oh， let's try to get the block collar to be the same。Let's try to do a blue guy。

Just so the players can relate bit more。Yeah。😊，Maybe。Let's。Try to get the actual color。

Did I not print the screen， what happened？Yeah now I did。What's wrong， I can't print this screen。

Let's， let's try this guy。There's blue。嗯。I don't think there is enough contrast。

That's strand Victoria。Okay， there'll be the strong box。 This one is actually not bad at all。

 I think this is actually。Worthy of a pixel artist， like a programmer。

 pixel artist this I'll call art。Okay， data and the strong blocks， is that all？



![](img/7011eb2fe997e9d598bb4046015d583f_229.png)

Yeah， we did four。And half four okay。Now I have the bitmaps， let's do more bitmaps。Let'St bitm。

Goodit map， T N T。Bit map。What were the other ones？球。And bitm。Inver。Okay。Theyre going to load。

All of these guys as well。So're going to load the。I know let me just open here to make sure I'm calling them correctly。

That in queue。我这得TNT。L in the inverted。あのあ感です。我进。This one is the slope。

I should really keep them the same name， but。Who cares。这头。And this is strong。Okay。

 and now the default。Case we're also going to draw。You like。Inve default case。Okay， so comment。

Let's do in。Tokyo， and I'm going to draw the TNT。For the little player going to draw。Turtle。

That inverted。Cons。And the。是。From black。

![](img/7011eb2fe997e9d598bb4046015d583f_231.png)

Okay， dude that。

![](img/7011eb2fe997e9d598bb4046015d583f_233.png)

Making okay so。Oh， you didn't actually see what with the assert。Have we got a name wrong？Inverted。啊。

😮。

![](img/7011eb2fe997e9d598bb4046015d583f_235.png)

Oh， it's all。Call par downs。嗯。

![](img/7011eb2fe997e9d598bb4046015d583f_237.png)

Okay。Making games is a lot of fun because of this， you know， have to do a lot of different stuff。

 it changes it。Yeah， okay， so see vertical controls。Let's just test， oh， crap。

That wasn't a good idea。Insibility。Yeah， or if it's book yours。Comment。是不删。Yeah， T and T。

 So this one， we can' to actually get， Okay， so I had to get。😊，Yeah， okay。

Ands goingll be cool when we add the interface。To show how much time you have。

 maybe maybe we should do that today， I don't know what we're going。We're going to do the。Yeah。

 strong blocks， they're not readable， it's not enough contrast。I think。Oh crap。

The tunnel looks pretty cool。Oh。I don't know if you got to see that。😊，嗯。

The game looks really really good so far， thanks， I also think that。Can see the tur？

That's pretty cool， let's get the totalr or crap。Oh， not good。哦。ok。

And let's see this basically this one has turnip paragraphs。Yeah。

 I think I'm going to draw instead stuff of like the letters， I think I'm going to draw the symbols。

 let's just make this guy。A bit darker。Like this。It's going to help readability。

 I don't want to make the blue darker just the arms。Separate the body。

From the arms and then Ill make it talked。Like this。Yeah。Things going to be better。For the strong。

Blalocks。Maybe I should also increase the contrast of the total。I don't know。

I know I think the Tos looks nice。Maybe I shouldn't remove this guy。I don't know， I don't know。

 it's okay now let's do more interesting things for the comment。Any other guys？

So the comet Im actually going to draw。A commentt。Let's try like a white。Ororder and like a red。Edge。

 then let's do like。です。

![](img/7011eb2fe997e9d598bb4046015d583f_239.png)

And you know what， I think it'll be easier to print。Our comment。Okay， lets try that one more time。



![](img/7011eb2fe997e9d598bb4046015d583f_241.png)

Okay， now I think。That all have to do so。This is our comment。So we have a wide center NE。Red。来。

Body like this。Yeah。Maybe I'm going to do it like this， yeah。And then we get， we get。Un less opaque。

 so。Let's try to 80% brush。Yeah， that's right。で。It's like a 40% brush。That's too much， yeah。Okay。

 it's kind of a cool thing。And then a 30 20% brush。10%。And，5%。They're like2%。Yeah。

 I think that's really cool。But， I think。I think that was a。I'm going to do that again。诶。Okay。

 so we have a white core。不去。I the corner。And these guy is going to be 100% solid。Okay。😊。

Let's do like 90%。S。80%， this guy， 70%。 This guy is 60%。50%，40%。30%。Yeah。Okay。啊。Let's do。

Let's do 80%。Then a go， then it'll do like。150。40。30。20。1。Okay， yeah。How do you like that？Dude。

 this is almost real pixel art， almost。But again， somewhere。

 maybe I should take like a picture art a course on muting me or something。

Then I can make this pretty cool and they do like an art string for res， Okay， so this is the comet。

Let's do the， the。The triple one， yeah， triple one， that should be easy。



![](img/7011eb2fe997e9d598bb4046015d583f_243.png)

What are the colors that would di for the D1？嗯。If we manage to get one。Look at that comment。

That's really awesome， Oh I shouldt really get the comment。Oh， I'm slow。嗯。

I don't remember the colors we got。6。How many slow guys I got。 and still slow。



![](img/7011eb2fe997e9d598bb4046015d583f_245.png)

I don't know。Let's cheat。 and look at the。Good啊。The ball I see。Yeah， direct。So。We draw the ball。

Quite。Oh， yeah。 the， the difference is the。The trail。So if we aren't， we do。

So we are blue and yellow。 Yeah， I can't do yellow。Maybe I'll just do blue for all of them。いやらしい？嗯。

I don't know how well this is going to look。How。Let' say，40%。Can I do like 60%。不喜。It do like 20%。

It's going to be pretty cool， I think。Yeah。And 10%。Okay， I kind of like that。

I'm going to move him like one square。哎。And then， increase， like。

And carry one a little bit like Chris this guy increase this guy。Interesting， guys。Yeah。

Then I'm just going to。Da literature at game， and I want to program one of myself right now。

 dude that's the spirit， man， you should program on yourself。It's really， really cool。 Yeah， I also。

 I， you know， I started this stream because I was inspired by watching people make games dude I want to make。

😊，Okay。谢谢。😊，Has a failed copy。No， it wasn't a failed copy。啊。What happened。Okay。

 that was just Photoshop me。Yeah， you should program one yourself。It's really。

 really cool to make games， I think I'm going to increase the contrast on this blue guy just a little bit。

And maybe like this， not a contrast like。I think's looking good dude， dude。

 I'm really the pixel art field right now， this going to be like an art stream。Okay trick or shot。

 Invincibility。Do you guys have any。Ideas for the invincibility， guy。嗯。



![](img/7011eb2fe997e9d598bb4046015d583f_247.png)

I don't know， let's play it for a bit。I don't know。Yes。The maps make a lot of difference。 Yeah。

 the eye is pretty， it's pretty boring。 Maybe I should draw like a force field。Beneath the player。

Look at all those guys that I got strong blocks。Yeah。Okay。

That was a pretty cool strong black behavior， oh my God， I have to totally leave， oh。

 managed not to get all of these turtles。The game is fun， Ho。 Oh， missed it。😊，Okay。Yeah。See。

I had inver controls there， Oh crap， Oh， okay， yeah that was your idea， you can't complain now。



![](img/7011eb2fe997e9d598bb4046015d583f_249.png)

![](img/7011eb2fe997e9d598bb4046015d583f_250.png)

Let's a。That's free， this guy。你 just。Free。不要。We're only using these for files。And then free。Okay。😊。

Yeah， I don't know what to do， I think I'm going to make draw force field。

Maybe like a green force field。啊。What is that。Dude。

 I missed a semico and look at the error they gave me。干么？



![](img/7011eb2fe997e9d598bb4046015d583f_252.png)

Yeah， let's see。

![](img/7011eb2fe997e9d598bb4046015d583f_254.png)

I think I'm going to make a green first field。Because the player is green。So。Let's see what we have。

I don't know。We could also make like double points。For power apps。O，那。Not too bad。

 first time around players want get it。But。Maybe you should make like a white player。Yeah。Yeah I。

Yeah， they'll totally not get it the first time。But I think that's okay。

And we're going to get tests now。Our。Our guy， because we'm gonna make like a one by by 10 texture。

 you know， see。How well it managed to create architecture guys。That's do。A one by。10。

Let's do one the2。It's okay， somewhat smooth gradient so。This is 100%。Oh， actually really， okay。

 now I'm going to do like alphapha。😊，Yeah， I have a good mess。So 100%。耐里。诶。8，70。sixty。Oh， actually。

I'm going to get some sleep thanks for the stream was nice as well we see us Sunday for the f stuff bymorphus。

It was awesome that you could。Jo join me today， and I'll expect you Sunday when you do some awesome threading。

 This gonna be really， really cool。 Bye bye。😊，So， 95。They're good， they're going to do night。

 I'll be there see ya。80。5。This， this is kind of。The weird slash boringing part of making art。

 even program art because I want to do like quality program art。I want to do crappy program art。60。

Maybe I should really do like my10。Because I do want to see the pixels。啊。50，50。five。50，45。40，30。35。

30，25。20。Oh， did I miscalculate it？15。No， I don't， I need 10 and five。嗯。白海张点这。ok。

Now we don't have office for it yet。In mean fact， let's actually make the upper channel， right？

I think things going to look pretty cool。They lets do like everything plus the alpha。

Let's export with transparency。Okay， I'm not sure this is going to work。

 I mean even when we implant alpha， but I'll do it just for fun。

 then I'm going to do sub pixelix sampling。Okay。Now， break out data。Let's do like force field。



![](img/7011eb2fe997e9d598bb4046015d583f_256.png)

And。You see the bit maps。That's also good。Force。Yeah， price field。Then， if you are an invincible。

We draw this guy and then we are supposed to draw the faritude as well。So， draw。map？

I'm going to draw。This map？Forest field。The position is going to be。Let's say， it is。It is 0。Then。

 the player。Visual PY。And the size。It's gonna be。嗯。S me the arena。Left。Right。Plus。You're in a right。

And let's do like10。有问。Maybe I have should take a whole bit map。DDP。



![](img/7011eb2fe997e9d598bb4046015d583f_258.png)

Yeah， no， not DDP， think God it wasn't the D， that'll be a weird bug。



![](img/7011eb2fe997e9d598bb4046015d583f_260.png)

In fact， let's make us。

![](img/7011eb2fe997e9d598bb4046015d583f_262.png)

免费情 go。Okay。😊，With 0。

![](img/7011eb2fe997e9d598bb4046015d583f_264.png)

I couldn't around。 I didn't know。Moode。我的品质。Bit map。Forest feel this。



![](img/7011eb2fe997e9d598bb4046015d583f_266.png)

Dude， I should have done this earlier， this is really cool， it's really fun。



![](img/7011eb2fe997e9d598bb4046015d583f_268.png)

Okay。So。

![](img/7011eb2fe997e9d598bb4046015d583f_270.png)

Let's open the offer。The alpha landing。嗯。Yeah， let's do for all of them。瞓。Yeah， and we're， yeah。

 this nerves not like best thing ever。Yet。But。So， alpha。Will be clamp F of0， alpha and1。Then。

 I'm gonna take。The alpha well。This is wrong， This is wrong，'re wrong。The alpha。Will be the color。

Alpha， which is。0，0。そか。Yeah。Is that it or is it the。Yeah， I think that's it。Dided by2 feet。

I'm not entirely sure。

![](img/7011eb2fe997e9d598bb4046015d583f_272.png)

I am going to have to step through this capture。So our collar， see that in hangs。Is 0， green 0。Okay。

嗯。Take a while。是。Yeah。嗯，好。

![](img/7011eb2fe997e9d598bb4046015d583f_274.png)

Let's just see。 It's easier。Yeah， and we see nothing。



![](img/7011eb2fe997e9d598bb4046015d583f_276.png)

![](img/7011eb2fe997e9d598bb4046015d583f_277.png)

If， well， let's see about， let's see the pars。Well， kind hard to tell if you can't see him， right？

Okay， this is。

![](img/7011eb2fe997e9d598bb4046015d583f_279.png)

This's interesting。

![](img/7011eb2fe997e9d598bb4046015d583f_281.png)

嗯。I'm going to put like a break point here if alpha is greater than0。



![](img/7011eb2fe997e9d598bb4046015d583f_283.png)

Oh dude， this is going to be so slow。

![](img/7011eb2fe997e9d598bb4046015d583f_285.png)

And we're going to play that。Since our random number starts with the same seed now。诶。

I kind of know already which ones， yeah， I kind of missed the par ups。Okay。You know what。

Let's remove。The force。fe。你说啊。Before I do the draw call。Then that's the break here。Oh， actually。

 I thought maybe it's the second I thought the first one had a。P up。What。😮。

Maybe we're just invisible。Okay， no it' not it is。So the the color。啊行。Is zero， zero。This guy。

Maybe the alpha is 0。Yeah， I think theF is0。So the offer should be zero。But it's。



![](img/7011eb2fe997e9d598bb4046015d583f_287.png)

Yeah maybe I'm getting the wrong guy。 this is supposed to be the alpha。It's not right， I mean。

 when do we change the B。Oh， because we put zero， okay？Now I have to also get the outcome。And the a。

The office all the way， this guy。No， this is wrong。This is the alpha。4。And order that to the alpha。

Mo。So the first guy。Is the alpha like this guy？Okay， and I'm going to have to shift that。拜出。

And then we divide that。

![](img/7011eb2fe997e9d598bb4046015d583f_289.png)

And then。Thank you for。节点。那行。Iupp suppose the seed is kind of random， I don't know。嗯。😊。

This is like super wrong。Like even。Even if we were not supposed to have。EX。The actual alpha。

We should be like all transparent。

![](img/7011eb2fe997e9d598bb4046015d583f_291.png)

But we have like one line。

![](img/7011eb2fe997e9d598bb4046015d583f_293.png)

Let's think that again。番。Okay， the color is F F。 Yeah， this what be expected。And a color。

So if we end this guy with this guy。Yeah， just so big have actually we don't need to end just move and then we we move。

Ex bar right， oh， we didn't cast to you8。But I don't think it matters。Alright， so this guy。F32。

Divided by 2，55。1。Okay。So you should get 100%。Of the color。Oh we're not。

 we're not incrementing the pixelixel。

![](img/7011eb2fe997e9d598bb4046015d583f_295.png)

Because you copied this guy from the alpha。But for some reason the alpha guy not implemented the pixel。

Yeah。Because。This。Amission I don't have this condition because I'm not rotating。



![](img/7011eb2fe997e9d598bb4046015d583f_297.png)

Kです。A weird loophole。

![](img/7011eb2fe997e9d598bb4046015d583f_299.png)

Okay， now we're back to working。And we can do some nice nicer stuff with this guy now that we have。

Transparent bitfa now。

![](img/7011eb2fe997e9d598bb4046015d583f_301.png)

Let's go back。To drawing， I don't know。To draw a press field。



![](img/7011eb2fe997e9d598bb4046015d583f_303.png)

Oh， look at that。At。If that's not super， super cool， I don't know what is。

Draw that before the player。

![](img/7011eb2fe997e9d598bb4046015d583f_305.png)

Okay。哇。Oh， yes。Now'm starting to get。I think you're going to do the random sea today。

Shouldn't be super hard。 And are we actually going to。C。😊，Oh man， oh， but yeah， we are pretty slow。嗯。

😊，Oh， don't like that。Yeah， I mean， we're not super slow。We're not super fast either。

Dude this is starting to get。Really cool。Software renderry is awesome。Yeah。

 but this is like the unoptimized build。 You may actually be okay。Yeah， I probably。

 I also going to have to。To learn that。

![](img/7011eb2fe997e9d598bb4046015d583f_307.png)

To make a knot。As strong， let's do that。We did bid maps， Let's do like power up。

It map use cooler alpha。We're gonna do force。Field in and out animation。And it was one more thing。

It remember now。We're going to do the sub second。I am not sure， well。I know。

But I think we're going to do。For these guys。He's actually like got the eraser to 50%。

I'm going to kind of erase these guys。And these guys。I think it's going to be really， really cool。

And I have to export。All that again。Okay， so this。Comment。You know， I think we'm going to save。

This guy。I want to save that anyways。I'm going to create like raw。And I like， power ups。

Just so it's easier to go to the。And I export the PNG。哦。

And let me just see if you' just checking this transparency。

 it works or if I have to do like the channel thing。It may just work。嗯。



![](img/7011eb2fe997e9d598bb4046015d583f_309.png)

Let's see the comment。Oh， and there I seed。

![](img/7011eb2fe997e9d598bb4046015d583f_311.png)

A random initial。

![](img/7011eb2fe997e9d598bb4046015d583f_313.png)

I think one of these guys here in the bottom left wind up the right。Our comments。The forest field。

It's going to be a really subtle animation， but I think it's to be cool。And。I don't know。

 maybe we shouldn't do the forest field like this。Maybe should should do like。A呀。

Laterer on the CPU version of this。Don't need to do it like a bitmap。

Because it covers a lot of the screen。Now， it kind of worked， but it was kind of ugly。



![](img/7011eb2fe997e9d598bb4046015d583f_315.png)

Don't know if I liked that。

![](img/7011eb2fe997e9d598bb4046015d583f_317.png)

I've seen the spacinggators， yeah。I didn't like that。Yeah。Maybe just the board ones。No， no。

 actually I did like that that was pretty quiet， I I didn't like these guys。



![](img/7011eb2fe997e9d598bb4046015d583f_319.png)

So I think these guys， let me see。These guys are going to go back to 100%。This。

And the center ones I cannot keep。O。I think that'll be a cool solution。And it did work。

Just my doing the。Sa the transparency。When we were exporting。Dude， this is like pretty cool， I think。

Yeah， I am liking it。Okay， triple shot。Of coursese， field。

So now it can be called force few instead of like invincibility。But now it's a real force field。啊。

Okay， now we turn this guy on and then export。Strong locks。

Maybe we should do like a little bit of thicker， strong block Im thinking like。Yeah。Yeah。

 I think it's going to be way more readable。Kind of liked that。Then， we do。一次。Strong。Oh， okay。

 forgot this is supposed to be the strong。This guy。Yeah， we are going to do。

 we have to do some optimizations in the rendering now that we are doing some。Craer stuff。

 because I think I want to ship this Raer。 I don't want to ship a open gel Rainer this game。

Time will come when I'll do open GL games， but this first oh this first that I'm doing like。

Show you guys the process。Yeah， I think I want to do。Software。Turtle。

 we can probably improve that later on as well， tuurtle。Turtle。De着。Hard work to say。T到。いけい？

I's keep going。TNT。And we are done。Now。probably do the in and out animation。 Oh， let's also do a。



![](img/7011eb2fe997e9d598bb4046015d583f_321.png)

Optimize build。还 mean。We're not going to do any crazier things in the。Terms of。诶。Yeah。

 this is pretty cool。Not going to do any more crazy things in terms of。呃。No。And。almost got it。Okay。



![](img/7011eb2fe997e9d598bb4046015d583f_323.png)

I think this is perfect。 Let's do the， the player have the Indian。Sability T。

Let do like invincibility alpha。嗯。Eba what the best way to do this？Yeah。

I think we're going to do that。D bit mask。Okay， now if。Inconability alpha。Is greater than zero。

Whennt to draw。And if it is greater than zero， I'm going to subtract。Let's say the Dt times two。

And2 is not greater than zero。Oh， no， this's not correct it's。

If we are invincible and it's greater than zero， we should do nothing。If we are not。

If it's not greater than zero。Oh， let's say， if it's。If it's。Less than one。We're going to。

So the T times 2。I don't know。 Let's do。10。系啊。Okay， now else if。If it's less than 0。It's less than 0。

It should also， yeah。I suppose that's the only thing we've got to do。



![](img/7011eb2fe997e9d598bb4046015d583f_325.png)

If it's， yeah。 but in this case， if it's not。If it's not。One。

 we should probably render that for a couple of frames。 So if the alpha is。It's。Greater than 0。

We're going to decrease that。And。And draw course。Now this is kind of convoluted， I think。

But I don't know。

![](img/7011eb2fe997e9d598bb4046015d583f_327.png)

Let's see。Let's make all the wall blocks。Give a。Use the power。



![](img/7011eb2fe997e9d598bb4046015d583f_329.png)

Just so it's easier to test。

![](img/7011eb2fe997e9d598bb4046015d583f_331.png)

Okay， that's certainly didn't work。So。We expected。We expect it not to be greater than zero。Yeah。

 that was a problem。Oh， the invinibility T。 Yeah， expected it to be lessing month， So we would grow。

 Okay， yeah， it is correct， but we're not actually using it。So。Pass like the alpha。I。Multipier。

Then I'm going to do the alpha multiplier。And clamp at that。K。And here， we going to multiply。

Everything by the alpha multiplly。These guys should all be， that do like。1。Too many print okay yeah。

啊应该 see。Did I have an offer？No有。How phone declared， drop it map。Yeah。

 this may actually be smaller than zero。A greater than one， but。



![](img/7011eb2fe997e9d598bb4046015d583f_333.png)

I don't really care。Yeah， okay。

![](img/7011eb2fe997e9d598bb4046015d583f_335.png)

Let's see。How that looks。Perfect。

![](img/7011eb2fe997e9d598bb4046015d583f_337.png)

Okay。嗯。But why didn't we see the player。I think we delete it。Yeah， we did delete lead。

De player you got。That was weird。

![](img/7011eb2fe997e9d598bb4046015d583f_339.png)

Yeah。That。

![](img/7011eb2fe997e9d598bb4046015d583f_341.png)

Okay。😊，Let's see。 for invincibility is nice。Perfect。You could probably love the player's color。But。



![](img/7011eb2fe997e9d598bb4046015d583f_343.png)

It's going to be hard， Okay， but we're not finishing。 Yeah， fits。Fs诶。Last day are equal to 0。Yeah。

 I shouldn't have to test this if themiss alpha is greater than 0。Subtract that。

And then other question， I think the speed was pretty cool。



![](img/7011eb2fe997e9d598bb4046015d583f_345.png)

I liked that。

![](img/7011eb2fe997e9d598bb4046015d583f_347.png)

Or actually that I couldn't actually pay much attention because it was training night。Yeah， yeah。

I think I like that。That's just。Let's just remove the。Everyone giving fancy。可。😊，Of course。

 you animation done， Let's do random seed。

![](img/7011eb2fe997e9d598bb4046015d583f_349.png)

Today， we are。On a streak。Okay， they were pretty cool。Yeah， perfect。Oh crap。

 I think for control onces or the TNT。And back to normal controls， okay。Okay， this is pretty tense。

This is really cool。Yeah， thats is the round seed the thing is we need something。😊，That is unique。

For every playthrough， I mean， kind unique doesn need to be the most unique thing ever。

Kind of this game， right？Okay yy， okay， oh nice。And。What are we're going to do？Nice， again。Okay crap。

Oh， okay。

![](img/7011eb2fe997e9d598bb4046015d583f_351.png)

嗯。And what I think you're going to do。Let's go to math。Someone has to provide a seed， right？

Let's make the Windows platform layer。When you get like the。This first。Last counter。

Let's add the random state to that， and let's print it to see if it's unique。



![](img/7011eb2fe997e9d598bb4046015d583f_353.png)

Last count， I think the large integer。Has a。Large integer。



![](img/7011eb2fe997e9d598bb4046015d583f_355.png)

SDM。I think it has like the。it only has the quad part。I think， I thought。It had like the。



![](img/7011eb2fe997e9d598bb4046015d583f_357.png)

The little bits。Yeah， I suppose can just cast that。To quite part。And that's print random state。



![](img/7011eb2fe997e9d598bb4046015d583f_359.png)

可以。And I just make sure before we do that。Let's see if we got one， two， three， and we do。

Now let's see what we have。

![](img/7011eb2fe997e9d598bb4046015d583f_361.png)

Okay，5，4， four， and4， a lot of stuff。By 5，81。

![](img/7011eb2fe997e9d598bb4046015d583f_363.png)

I， 6。By 7。That's perfect。And then just by doing this。Even if it's like a small difference。



![](img/7011eb2fe997e9d598bb4046015d583f_365.png)

We're going to have， like。Substantially different random numbers。

So see before this first one pretty much always had。Right， guys， I it still does。Well。

 let's see if he is Ron does。It doesn't。Perfect。Nice。Oh， so there's this bug。



![](img/7011eb2fe997e9d598bb4046015d583f_367.png)

Let's try to fix that as well。Today is a crazy day。 Good day。呃。Thats I I think I I。你给呃。

LetSee block life。Yeah， I remember typing it， but I don't think we got that， so。

The invincibility only tests out when we are killed。And what we really should test， like let's say。

 the ball。Dateball， yeah。C。😊，We test if youre less than 50， if we lose a life。Okay， and if we don't。

We really are。We should hard code the desired。This guy to mine script。

I don't know if you guys saw what happened。 The idea was that the ball was pretty much already down when I got the。



![](img/7011eb2fe997e9d598bb4046015d583f_369.png)

The life。 So it it kept going forever。Kind of like that。



![](img/7011eb2fe997e9d598bb4046015d583f_371.png)

Okay， minus the ball he size， but that's not surprising。去一。It's the ball。Des key。

Minus half side is 50。 It's-50。If we are in principle， we lose a life if we are not。Ae for。

 if we are invincible。Set that in reverse。う。Yeah， let me test that， I think this may。



![](img/7011eb2fe997e9d598bb4046015d583f_373.png)

Surely actually pay around thisK。That。The failed attempt。Yeah。

 and we do have a couple of twitches in our。Okay， perfect。Now， we do have to test those harder cases。

Which like when the ball is pretty much is already past me。But I think this is going to work。

But it's harder to test。Nice。Really nice。Oh。Okay。It's nice when you like combo。

 a couple of a lot of it。Yeah， having animations like that on the forest field， it's really subtle。

 but it makes a ton of difference in terms of。Like that's the difference between an amateur game and a better game。

 I think， well that's one of the differences， but that's a pretty major one。



![](img/7011eb2fe997e9d598bb4046015d583f_375.png)

That was a wasted three shot。Okay。你好。Fixed that， fix the other thing that we didn't write down。

Real break were play with arts。Maybe would consider， so we can write out。Sspecix rainery。

 now let's do that。In order to do a sub pixel accurate rainry。I'm going to do a hack。First of all。

 let's really see。日系的 problem。So I'm going to draw a。Let's do like X。0。でデライク。I don't know。To， to。

What do you like。かんじない。Because。

![](img/7011eb2fe997e9d598bb4046015d583f_377.png)

When we have a slow moving object。That'cept to see this pretty slow。



![](img/7011eb2fe997e9d598bb4046015d583f_379.png)

Well， let's make it move a little bit slow。

![](img/7011eb2fe997e9d598bb4046015d583f_381.png)

If you have a slow moving object。Yeah。See how its shape kind of gets deformed。Like it crawls weirdly。

It doesn't move slowly。It moves like。Sometimes they move one frame and other times it doesn't move at all。



![](img/7011eb2fe997e9d598bb4046015d583f_383.png)

Hopefully you guys can see that。The problem is。

![](img/7011eb2fe997e9d598bb4046015d583f_385.png)

Let's go to our rectangle。Oh。Problem is。Yeah， here。We are。We just clamped these guys。

Anybody you like did other float to operations？

![](img/7011eb2fe997e9d598bb4046015d583f_387.png)

It doesn't matter the point is this conversion to int。We're probably going to lose half pixels。

 so let's say this is the pixels that we're trying to go。Inter life here。Perfect。

 this should be 100% wide。 Now， next frame， we're here。So。It draws that as 100% wide。

But in this frame that we are here， it draws that 100% white and it doesn't draw anything like this。

 so it stays two frames on this guy when it actually should be moving。quotes。

 and then it moves under attention of this guy。 What we you want to do is it's 100% white if it's in the standard here。

At this point。That's say it's like 80%。White or 20% white。And at this point， this is  zero%。



![](img/7011eb2fe997e9d598bb4046015d583f_389.png)

So I'm going to hack this， I'm going to create。A different。Call for the direct。'Go to do like a draw。

あ？十 pixel。Just because this would probably do more operations， probably。And。I think we only care。

For like fast objects like the player。The ball。

![](img/7011eb2fe997e9d598bb4046015d583f_391.png)

Probably the power ups， but the p ups since they are。Since they are bitmps， we have to。有十分。Yeah。

 but I don't know。They move fast enough that we don't see。But the ball especially in the beginning。

 that it goes slow。I don't know， maybe we don't need that at all， let's just try to do it for fun。



![](img/7011eb2fe997e9d598bb4046015d583f_393.png)

And we'll see if it makes it better， so this guy should be direct。



![](img/7011eb2fe997e9d598bb4046015d583f_395.png)

あさ bigそ。Okay。😊。

![](img/7011eb2fe997e9d598bb4046015d583f_397.png)

Yeah， so nothing changes Now the idea is。We have this X。Let's just do it for like one axes for now。

And。嗯。And then we maybe do like the two of them for the ball， it looks good on the player。

 so this like the first pixel。Let's call that X。0F。So this guy。Minus T X 0。

It returns a fractional value。That shows how much we didn't。Managed to get across like。



![](img/7011eb2fe997e9d598bb4046015d583f_399.png)

还你。😊，Let me explain when I had a break point here。

![](img/7011eb2fe997e9d598bb4046015d583f_401.png)

So。Well。

![](img/7011eb2fe997e9d598bb4046015d583f_403.png)

Oh， yeah， we are optimistic。Now I have to move that up。



![](img/7011eb2fe997e9d598bb4046015d583f_405.png)

Okay。And then I have to。Stop there。We are supposed to go to the pixel in quotes。618。41。

But we can't go to the 0。41 pixel。Right。We can't。So this guy says， okay， start at the。

It closed the sky。Its。Yeah。Okay。This one says to okay， so start at the 618。

And then we're going to ignore 0。41 dec。 So we should really draw before we draw this guy。

 we should draw one for it。That is actually a full row， a full column。



![](img/7011eb2fe997e9d598bb4046015d583f_407.png)

Pixels with this alpha。Sounds good， this sounds pretty， pretty easy I think。

 so good to draw rec well and pixel those transparent。Think we need that again。So。诶。The那儿。ですね。啊。Yeah。

Okay。😊，Same thing as before。clamlam。诶。O。Now， this is like what we did like $100，0。Now。

And now we're going to pass。V x0 f。But。What are we going to draw， We're going to draw？

Just the leftmost column， like。Like this。But we're going to draw the way from the y0 to the x0。

 so that's what we want to do， hopefully。

![](img/7011eb2fe997e9d598bb4046015d583f_409.png)

They should already work， any if you well。

![](img/7011eb2fe997e9d598bb4046015d583f_411.png)

We are doing something， but I think this is wrong。IThink this is wrong， but。

I don't know if you guys could see， maybe I should just。Amplify that， but we did have something。

Let' see。Okay。It's kind of hard to see。Because this also happens on this side。

Although I'm not entirely to sure why。Let's see that this is Mo。

So the idea is things are going to grow slowly So the thing is instead of doing like straight up。

Conversion to it like this， I'm going to add 0。5。Just to offset that to the center of the pixel。



![](img/7011eb2fe997e9d598bb4046015d583f_413.png)

So if we expect。

![](img/7011eb2fe997e9d598bb4046015d583f_415.png)

嗯。

![](img/7011eb2fe997e9d598bb4046015d583f_417.png)

I' know it doesn't look correct。That's just。

![](img/7011eb2fe997e9d598bb4046015d583f_419.png)

Let's just do this。食解。And that's path like three。

![](img/7011eb2fe997e9d598bb4046015d583f_421.png)

Oh， that's that was。

![](img/7011eb2fe997e9d598bb4046015d583f_423.png)

![](img/7011eb2fe997e9d598bb4046015d583f_424.png)

Okay， so this is what we expected。

![](img/7011eb2fe997e9d598bb4046015d583f_426.png)

啊。And just try and make this guy bigger， they'll easier for everybody to see。

 but it's still just one pixel。

![](img/7011eb2fe997e9d598bb4046015d583f_428.png)

So it won't be that much easier， you guys can see the green line， right？



![](img/7011eb2fe997e9d598bb4046015d583f_430.png)

Yeah， this is correct now。We should really do the transparent calculations。That's in the offer。Oh。

 you know what？I think then just print the sample it's going to be one separate frame and the house is going to move slowly so we were expected to start like some random number between0 and one。

 go all the way to zero， then start one again。That's what we expect。Right， but since this is a。

We should really do a print float。If we managed do this pretty quickly， which today will like us。

 nice week。佢刚就可有题。Okay。Print。And undefined。Just going for declare。bo。Out。This is actually x0 m。Very。

 very bad name。Flolow to int possible loss。First multiply in the image we do。Alpha。Okay。0。



![](img/7011eb2fe997e9d598bb4046015d583f_432.png)

Okay， let's see the number。Okay， so yeah， this is not what we totally expected， it goes from。

Goes from negative。0。5。To like zero， I think。Now， maybe too positive，50， yeah。



![](img/7011eb2fe997e9d598bb4046015d583f_434.png)

Let's check this。And then we can like the plug after that。So。



![](img/7011eb2fe997e9d598bb4046015d583f_436.png)

Let's say we want to draw。 well， that's S debug。Okay， so。This guy， oh。

 we actually we talking about this guy。Okay， so we want to draw this pixel。But we can't。

 so we're going to draw。Starting from， yeah，4496。But we want to draw 445。And so this was the problem。



![](img/7011eb2fe997e9d598bb4046015d583f_438.png)

Oh， we should really add。So let's call that x0 f。For wheels。And this will be。Next you will offer。

Yeah， we forgot to add the45 so there was a discrepancy there。O。



![](img/7011eb2fe997e9d598bb4046015d583f_440.png)

Okay， now let's see if you can see anything different。Crowd of failure is huge。



![](img/7011eb2fe997e9d598bb4046015d583f_442.png)

嗯。

![](img/7011eb2fe997e9d598bb4046015d583f_444.png)

Well， this looks correct， I think but it looked correct before。Now this guy。

 we want to draw it this piece。So we can't do that， we're going to draw。At the 46，7。Okay， so。

We want this is the 40。46。 So we are。Like 。33 in。And this tells us to draw that pixel。

So sure we added one。To that。And this one。It's going to give us like this guy。

Let's just see some values。 so have this guy。This guy。No， I think they look perfect now。Yeah。

So instead of starting off。

![](img/7011eb2fe997e9d598bb4046015d583f_446.png)

In the this guy。We start off at him plus one。This guy's going to go all the way from him to him plus one。



![](img/7011eb2fe997e9d598bb4046015d583f_448.png)

Okay， it's going to be better。

![](img/7011eb2fe997e9d598bb4046015d583f_450.png)

但是。

![](img/7011eb2fe997e9d598bb4046015d583f_452.png)

Well， the alpha looks really wrong for some reason and I oh， yeah， I'm print it wrong。

Should print be X。Oh times。0undred。

![](img/7011eb2fe997e9d598bb4046015d583f_454.png)

7。😊，Okay， this is better。

![](img/7011eb2fe997e9d598bb4046015d583f_456.png)

诶谁。I就是 like color。

![](img/7011eb2fe997e9d598bb4046015d583f_458.png)

To see if it's kind of slow， I'm going。Try to ignore it well， that's not。



![](img/7011eb2fe997e9d598bb4046015d583f_460.png)

That's not。Exactly。Should be， maybe this should be like minus。



![](img/7011eb2fe997e9d598bb4046015d583f_462.png)

1 minus this guy。It's going to in because they're supposed to。Yeah， I know we're doing with that。



![](img/7011eb2fe997e9d598bb4046015d583f_464.png)

Let's try to de book that one。

![](img/7011eb2fe997e9d598bb4046015d583f_466.png)

Okay。嗯。This guy says， well。I want to draw this guy at this position。Actually， disposition。

But I can't。Right， this is the46。Then what I'm saying here is， okay。Sure啊。The role， his role， right。

With 0。33 of alpha。Okay， so。This looks about， right？And then I'm going to do this guy plus one。

All the way to the end。I don't know。Kind of looks right。Let's try to make him super slow。



![](img/7011eb2fe997e9d598bb4046015d583f_468.png)

Like。

![](img/7011eb2fe997e9d598bb4046015d583f_470.png)

![](img/7011eb2fe997e9d598bb4046015d583f_471.png)

And you know what？I'm going to see myself going stepping really close to the monitor and just adding this。

Aagnified guy。

![](img/7011eb2fe997e9d598bb4046015d583f_473.png)

![](img/7011eb2fe997e9d598bb4046015d583f_474.png)

I think。

![](img/7011eb2fe997e9d598bb4046015d583f_476.png)

That was just a bit too much。Oh my God， no it's like。

And it's also hard for me to see if you guys can see。



![](img/7011eb2fe997e9d598bb4046015d583f_478.png)

Okay， let's。

![](img/7011eb2fe997e9d598bb4046015d583f_480.png)

Oh， the mouse is stuck。

![](img/7011eb2fe997e9d598bb4046015d583f_482.png)

ないです。It's like I don't even see any offer change， well。I sit getting stronger the alpha。 Yeah。

 it does goes all the way to one。It' is like the opposite of what we want。



![](img/7011eb2fe997e9d598bb4046015d583f_484.png)

So I think that's the only problem。So this guy should have been correct。It's like one minus this guy。

Well， I actually said。Niggate that result， which was wrong。So， let's do like 300。



![](img/7011eb2fe997e9d598bb4046015d583f_486.png)

Do those perfect。

![](img/7011eb2fe997e9d598bb4046015d583f_488.png)

Perfect， really， really， really perfect。That's make it move a little bit faster。



![](img/7011eb2fe997e9d598bb4046015d583f_490.png)

How about that？ Look at the difference。 I don't know if you guys can see。



![](img/7011eb2fe997e9d598bb4046015d583f_492.png)

Let me see in the stream。 Yeah， it's hard for me to see if you guys can see because I'm so zoomed in。



![](img/7011eb2fe997e9d598bb4046015d583f_494.png)

![](img/7011eb2fe997e9d598bb4046015d583f_495.png)

Let me try， okay， I think you guys can see now。Look at the difference between the left part。

 which goes smoothly in the right part， which does not。That's awesome。

Let's add that to the right part。And then I add that to the player。



![](img/7011eb2fe997e9d598bb4046015d583f_497.png)

That animation on the top speaker。Okay， I think you guys are really good to see that。I am not sure。

Yeah， you were， okay。

![](img/7011eb2fe997e9d598bb4046015d583f_499.png)

Let's add that to the other side。It's going to be pretty much the same thing。Right， let's。

 let's do it。嗯。Calculate this guy。Alpha  one， which is the Sky plus。Okay。And then we do this guy。

I this guy do？This guy。😊，Which is this guy， that's pretty explanatory， isn't that？

Great explanation of these guys。

![](img/7011eb2fe997e9d598bb4046015d583f_501.png)

And then。Let me step through that。This guy wants。

![](img/7011eb2fe997e9d598bb4046015d583f_503.png)

So theres results。

![](img/7011eb2fe997e9d598bb4046015d583f_505.png)

可以吗。Through these guys。Okay， sometimes it doesn't come， I don't know why。Okay， so we want to go past。

The 7，68 ge，o I suppose。The last one should be 768。It is。And so this one is going to be。Yeah。

So the offer， yes， I think this one we don't need to invert that， I think。



![](img/7011eb2fe997e9d598bb4046015d583f_507.png)

And okay， so this one's going to start out at this guy。This guy。And to this guy this one。

I we need to change。

![](img/7011eb2fe997e9d598bb4046015d583f_509.png)

That。see。😊，Dude。If that's not perfect， I don't know what's perfect。



![](img/7011eb2fe997e9d598bb4046015d583f_511.png)

Let me try to zoom in again for you guys。

![](img/7011eb2fe997e9d598bb4046015d583f_513.png)

And also so I don't like to take my face into the winery。



![](img/7011eb2fe997e9d598bb4046015d583f_515.png)

Yeah， but when you do stick in when you go this close。

 you can you can see like the pixel is changing。

![](img/7011eb2fe997e9d598bb4046015d583f_517.png)

So maybe the best solution is not to go that close。



![](img/7011eb2fe997e9d598bb4046015d583f_519.png)

And you guys can see right， this rectangle， this square is moving like extremely smoothing across smoothly across the screen。



![](img/7011eb2fe997e9d598bb4046015d583f_521.png)

That is the benefit of subpix accuracy and I'm pretty happy to hear what we got and I mean it is a hack。

 I'm not going to say it's not a hack， it is a hack， but it was a pretty easy hack to do。😊。



![](img/7011eb2fe997e9d598bb4046015d583f_523.png)

Now， the only thing we should do to add that to the player， I think。If I am not mistaken。

 I'm going to comment that。The vertical one。原告。Because the pay moves horizontally。

 so the only thing I should have to do。It's like。近い？And I think that's it。



![](img/7011eb2fe997e9d598bb4046015d583f_525.png)

Yeah。Let's see。The difference。

![](img/7011eb2fe997e9d598bb4046015d583f_527.png)

Okay， well， kind of hard to tell。

![](img/7011eb2fe997e9d598bb4046015d583f_529.png)

![](img/7011eb2fe997e9d598bb4046015d583f_530.png)

Yeah， especially， especially with the spring， I'll make this spring。😊，啊。Sa here。

Make scream less tough。

![](img/7011eb2fe997e9d598bb4046015d583f_532.png)

Yeah， I like that。It does for us to test。Especially at the end， it moves a bit weird well。

 but it's not， It know， wasn't that evident。

![](img/7011eb2fe997e9d598bb4046015d583f_534.png)

To begin with。

![](img/7011eb2fe997e9d598bb4046015d583f_536.png)

So maybe it wasn't worth， well， it was worth to learn， but it wasn't worth like visually。

I don't know it does。Look a bit better， I think。Well， I think it's a bit better。

But I don't think I'm going to add that to the ball。Just when you go fast。

 the ball doesn't move slowly like at all。Even， even like this， it's pretty fast。

The player can absolutely well， but the why。嗯。

![](img/7011eb2fe997e9d598bb4046015d583f_538.png)

I got these guys wrong。

![](img/7011eb2fe997e9d598bb4046015d583f_540.png)

Because she。The last row is getting messed up when I move slowly。



![](img/7011eb2fe997e9d598bb4046015d583f_542.png)

![](img/7011eb2fe997e9d598bb4046015d583f_543.png)

Yes， now I'm extremely confused。I thought I was only changing。 but I think I was pretty wrong。 Yes。

 I was。 I was wrong。

![](img/7011eb2fe997e9d598bb4046015d583f_545.png)

![](img/7011eb2fe997e9d598bb4046015d583f_546.png)

These guys are wrong， I should only change the first row， so it's going to be y zero。

In y zero plus one and why。玩。NY1 plus one。But I should go all the way from x to zero。No。

 it's the other way around。I want just these guys， so they go from y0 to I1 that's correct。

 but the x should really。啊。That's correct。That's what I was doing。It's like one pixelel。

The width and the height， the whole height。

![](img/7011eb2fe997e9d598bb4046015d583f_548.png)

Oh， maybe。

![](img/7011eb2fe997e9d598bb4046015d583f_550.png)

Because I do change the side。 Yeah， I'm going to have to do that for the player。 the both。 Yeah。

 because I do change the。The player， the player size in X and y。 So it does bigger。 So I'm gonna。

 I'm gonna to do the same thing。我的 w呀。Okay， and let me just see what。Pntdeor2。



![](img/7011eb2fe997e9d598bb4046015d583f_552.png)

I don't know。Okay， so see， we see the same problem and'm going to do the same thing。



![](img/7011eb2fe997e9d598bb4046015d583f_554.png)

Okay， so this is P I。欢迎 zero。Same thing for the wire。Okay， and then we do the same thing for the。

For the my one。If you guys have any questions， just drop them in the chat and I'll try to answer them。

Like about anything really better we're doing。Now， same thing here， but。

We're going to go from x0 to x1。So you go to the whole X。Then we go for my zero。

Tice zero plus one I'm going to go from y。From my one。2 y。W correspond。And possibly。



![](img/7011eb2fe997e9d598bb4046015d583f_556.png)

亲。

![](img/7011eb2fe997e9d598bb4046015d583f_558.png)

Yeah， well'll have to do like why。

![](img/7011eb2fe997e9d598bb4046015d583f_560.png)

![](img/7011eb2fe997e9d598bb4046015d583f_561.png)

It looks inverted。

![](img/7011eb2fe997e9d598bb4046015d583f_563.png)

Like。It should work。

![](img/7011eb2fe997e9d598bb4046015d583f_565.png)

No， it's wrong。 Okay， let's do it calmly。So the Y 0 F， okay。And the alpha。Okay。Plus。This guy。Okay。

 the values were correct now， these guys。Go to go from。X wants the whole row。AndWell。

 the four corners probably going to be problematic， but I'm not sure what to do with them many ways。

嗯。I don't know。

![](img/7011eb2fe997e9d598bb4046015d583f_567.png)

This looked correct。

![](img/7011eb2fe997e9d598bb4046015d583f_569.png)

The top one。

![](img/7011eb2fe997e9d598bb4046015d583f_571.png)

Looks important。

![](img/7011eb2fe997e9d598bb4046015d583f_573.png)

Let's just。

![](img/7011eb2fe997e9d598bb4046015d583f_575.png)

Let me step through that code again。Okay， again，好。Havent known this guy， okay。So。Let's to the top。

 we want to go。Like all the way to pixelixel 82。Oh， because we are。

Or we top them now we are bottom up， Yeah， all the way to pixel 82。

But I'm only going to drop to Pix 82 and I have 0。22 to the other guys， right？So this is the Y one。

 so the Y one。I'm going to go from the y1 to the y1， let's do and draw him with this alpha。

That looks perfect， I think。Oh， yeah， no， it is correct。And the y zero。It started out at 45， 44。

So I'm going to do that and then do。嗯。😊，It must to be a stupid mistake because。

I don't see the problem。Yeah。

![](img/7011eb2fe997e9d598bb4046015d583f_577.png)

I don't know。

![](img/7011eb2fe997e9d598bb4046015d583f_579.png)

And try to look up close， that helped the first time。



![](img/7011eb2fe997e9d598bb4046015d583f_581.png)

小垃圾。

![](img/7011eb2fe997e9d598bb4046015d583f_583.png)

Well， I don't even see。

![](img/7011eb2fe997e9d598bb4046015d583f_585.png)

I don't even see the proper， let's try to run that again。



![](img/7011eb2fe997e9d598bb4046015d583f_587.png)

I don't even see the proper。Al for blending like at all， they don't see it at all。



![](img/7011eb2fe997e9d598bb4046015d583f_589.png)

啊。

![](img/7011eb2fe997e9d598bb4046015d583f_591.png)

![](img/7011eb2fe997e9d598bb4046015d583f_592.png)

Let me just draw these guys。Ps。Yeah， well there are points go not align。



![](img/7011eb2fe997e9d598bb4046015d583f_594.png)

But why are there a point？Im going from x1 all the way， x0 all the way to x1。

It also should name should be x plus one， but doesn't matter。



![](img/7011eb2fe997e9d598bb4046015d583f_596.png)

我有。I see。I'm going from。This guy to this guy， so certainly not aligned。

And would go like one pixel high。 So this guy。I should go like。And in fact， I want see one point。

 not even two points。

![](img/7011eb2fe997e9d598bb4046015d583f_598.png)

It's weird， okay。Oh， the same stupid mistake last time。The same stick， well。

 last time wasn't like a natural stick。But if that's the case。How well， yeah， it worked。

 it worked for the other case because we only had one pixel of an X。😊，So we were like。

 do one pixel one and then go back， but in this case we should read。



![](img/7011eb2fe997e9d598bb4046015d583f_600.png)

Well， the other time I have managed to cut to catch this bug。Before。It was problematic。

 This case I did so。

![](img/7011eb2fe997e9d598bb4046015d583f_602.png)

I was intrigued for a while now。

![](img/7011eb2fe997e9d598bb4046015d583f_604.png)

Perfect。Perfect subtix so moving。 Now， let's add these guys back。



![](img/7011eb2fe997e9d598bb4046015d583f_606.png)

We should also have。more pilot。Just for fun。

![](img/7011eb2fe997e9d598bb4046015d583f_608.png)

D diagonally。Okay， that's perfect。And。

![](img/7011eb2fe997e9d598bb4046015d583f_610.png)

I think I am not going to go all the way。切。Like did this guy。And this guy。



![](img/7011eb2fe997e9d598bb4046015d583f_612.png)

Just so we don't like。Draw twice on the same pixel。The left side looks kind of okay。

But the right side doesn't because this is really a hack for pixel perfection subpixel。



![](img/7011eb2fe997e9d598bb4046015d583f_614.png)

![](img/7011eb2fe997e9d598bb4046015d583f_615.png)

I mean， don't expect it to be like the besttic surrenderer in the world。Yeah。

 I still don't like the border ones， they're like there's like one pixel over。Well。

 the only one I don't like is deep。

![](img/7011eb2fe997e9d598bb4046015d583f_617.png)

The why down。Oh， which is this guy。

![](img/7011eb2fe997e9d598bb4046015d583f_619.png)

ok。Now we are way better， I think。

![](img/7011eb2fe997e9d598bb4046015d583f_621.png)

We are way better I think， oh， I really like that。So。In the spring， I'm going to go back。

 maybe not a full， it was like 40 right I do。

![](img/7011eb2fe997e9d598bb4046015d583f_623.png)

Okay。Yeah， nice jelly player。Yeah now let's play around with the par ups。Okay， yeah。 I forgot that。

 I can cheat。And add myself some life， dude， that's awesome。TheFirst field。Yeah。

 how let's do the strong blocks just for fun。The attend looks looks awesome and frightening。Okay。

When we add the timers， it's going to be really cool。

 it's going to be like a perfect like the visual timers in the interface's going to be。

Reretty nice to see how much like。Intensibility time we have things like that。 Maybe you can add， oh。

 now that I'm thinking about it。Maybe we could't。That on this guy。I had them slowly fade out。

As we lose。

![](img/7011eb2fe997e9d598bb4046015d583f_625.png)

嗯。Let's try that。 That to me， and that probably。Would be better let's go back to the optimized build。

YeahSo we did sub pixelixel a rendering， at least for the player。

 which was the main thing that we wanted。So you know what。

 I think the compile times are taking like a bit too long now。Probably because of the。

Because of the library that we used。So， I'm going to。I'm going to like do P&G only。来偏激。Yeah。So。

 hopefully。It bit quicker。not really。CBI。No。Let's do no SDDIO as well。7。De could memory。

A through time。No failure strain。Yeah。We don't need video streams。No。Can I see what else you got。

No Cdy。 Now， please。 let's use Cdy。Yeah， that that was it。Or I didn't change much to pretty slope。嗯。

That's just。I guess。いアい。Let's just see if we compile a lot faster without this guy。Yeah， we do， but。

I don't think we're going to use that in the final game。



![](img/7011eb2fe997e9d598bb4046015d583f_627.png)

But was super fast， so I'm not going to complain too much。



![](img/7011eb2fe997e9d598bb4046015d583f_629.png)

Okay， so now we are back to the fast build and we're going to do the last thing for today。

which is the print float guide。And I'm going to do a very hacky weight。Let's go to the console。And。

Print to F32。I see that。There are two numbers。And the way I'm going to do this。Is， first of all。

I'm going to print。Ent。Number。Tncated。ok。Then I'm going to print。Okay， I have to。嗯。

You know what's the message。I'm going to do a message type。Message and。I mean。

 if we had like font rendering。Everything would just be a message。啊。

Everything would just be the message characters。But since we don't。Have fun， well。

It could at now that we have bitns。I don't know my。I think about that。Do you like interval。就这一下。ok。

So。You do have 32。This is what we do。I do like yesterday。It's never。The message。H close。32。Well。

Anbel。Okay， but this now I have to。Switch。的message。Hi。Case message。Yeah。We do that。Case。Message。

Inve default case。Now what we're going to do。You're gonna have， like。诶啊。好。Which is the。It well。

Yes to hint。And I have， like， Frank。Which is。The absolute。Often。Message。A 32 v。マイナステ。

Do I need threshold if it's like negative 1。5？それ minus1すて。It's going to be-1。5，-1。

And I'm going to do like two digits， so I'm going to do like 100 times。And便。

So it's not going to be the most perfect。F 32。But it'll do for now。Then we're going to draw a number。

 First of all， I're going to draw the frac form。And in fact， let's test。一個。

It's pretty cool that down here is where we tap are our stuff。Our test driven development， right？

Okay， we should do actually before。Or our messages。Oh it doesn't even matter。

Then I'm going to do print。At 32。F。But it goes这。

![](img/7011eb2fe997e9d598bb4046015d583f_631.png)

。

![](img/7011eb2fe997e9d598bb4046015d583f_633.png)

Okay， what't I expecting that？Well。Sing that。Let's do what we think。We know how to do。

Wehich is like the whole part。

![](img/7011eb2fe997e9d598bb4046015d583f_635.png)

I see 0，1，2。 Okay， this is correct。

![](img/7011eb2fe997e9d598bb4046015d583f_637.png)

And see things like one second， right？

![](img/7011eb2fe997e9d598bb4046015d583f_639.png)

1。这个面。So。What I expect to see is the number that goes from zero。



![](img/7011eb2fe997e9d598bb4046015d583f_641.png)

To99。

![](img/7011eb2fe997e9d598bb4046015d583f_643.png)

二。

![](img/7011eb2fe997e9d598bb4046015d583f_645.png)

Okay。啊。Stuper mistake。

![](img/7011eb2fe997e9d598bb4046015d583f_647.png)

Perfect。Really， really perfect。

![](img/7011eb2fe997e9d598bb4046015d583f_649.png)

You know what？啊。Our drug number。In our render。Instead of doing like this firstit digit thing。

 I'm going to do like。Number of。Zeroes。And we pass zero， like the first dig to。嗯。We can pass， like。0。

 and then the default will be one。 So if number or。Number of leading zeros。Number of。in minus。

 so this shouldn't change anything that we did so far。But then this guy should do like zero。

This guy should do like two。So there's like to zero to be zero zero。I think。

Yes see that's where default arguments。

![](img/7011eb2fe997e9d598bb4046015d583f_651.png)

I think I may have won too much， yeah I do。But。It is working。Although our D number is not。

 what happened？Though our draw number is not a。Probly do that。Make it。 I don't know。

 I'm thinking about making it like。Moonerospaced， but。Draw number。ok。Some reason。

The number of leading zeroes is very small， like。Really， really smart。That's weird。嗯。Let me just。Set。

Nextテ。Okay， so if you are3。2。嗯。And didn't go too long。



![](img/7011eb2fe997e9d598bb4046015d583f_653.png)

I don't know why that happened。I should say like while it is zeros。this guy。



![](img/7011eb2fe997e9d598bb4046015d583f_655.png)

Yeah。But。Not sure why it was so nice it's like in。

![](img/7011eb2fe997e9d598bb4046015d583f_657.png)

Oh， maybe， maybe。Yeah。😊，Yeah， this is correct now Yeah， I had to pass more than。



![](img/7011eb2fe997e9d598bb4046015d583f_659.png)

Three guys， so this guy kept going below zero。

![](img/7011eb2fe997e9d598bb4046015d583f_661.png)

I got it。 He's going to fix it。Okay， perfect。Now。Maybe you should do like。我要。No， not really。嗯。

I don't know， I wanted to pass two for this guy because I wanted them two。Numbers。Yeah。😊，Yeah。

 this is correct。 Then everyone gets one number。 So one。W。The game， the score。



![](img/7011eb2fe997e9d598bb4046015d583f_663.png)

Well， this core， just for fun， I couldn't edit it。

![](img/7011eb2fe997e9d598bb4046015d583f_665.png)

Yeah。ok。But we can get greater than that， but that's just for fun。



![](img/7011eb2fe997e9d598bb4046015d583f_667.png)

Okay。No。

![](img/7011eb2fe997e9d598bb4046015d583f_669.png)

So this guy should be just greater than zero。

![](img/7011eb2fe997e9d598bb4046015d583f_671.png)

Yeah。Perfect。😊，Now。A castle。嗯。Okay we're going to draw both of them， the hole and the frac。

And also going to you a like。Right， like a point。So this is going to be like， I'll have to a P。

 So draw the frac。We have to move left。A certain amount， and we don't know what amount。

Maybe the drawing number。Paassees like the。The X offset。P， X。Let's do that。Okay， so we moved left。

Now we should draw a point， like。Direct。And I'm gonna draw life， maybe。P。Well。

Let's make a certain2 P。And I'm going to subtract that。With a the two of 0。Let's do two。

My voice is really starting to fail me now， it's been like three and a half hours。Yeah。

 it's getting kind of late。呃。And then I'm going to do a like 0。5。5。

And then we offset the key a little bit。はい。完。

![](img/7011eb2fe997e9d598bb4046015d583f_673.png)

感谢。

![](img/7011eb2fe997e9d598bb4046015d583f_675.png)

This is like， super wrong。嗯。Yeah， well。Save like original X。这个 like P。Well， I just do like P do X。



![](img/7011eb2fe997e9d598bb4046015d583f_677.png)

Okay， now。

![](img/7011eb2fe997e9d598bb4046015d583f_679.png)

These guys are really crazy。I是理。And more， like one。I can move like by three。do it like 1。5。



![](img/7011eb2fe997e9d598bb4046015d583f_681.png)

![](img/7011eb2fe997e9d598bb4046015d583f_682.png)

Yeah。Oh， that was too much， let's do like 0。75 we do。



![](img/7011eb2fe997e9d598bb4046015d583f_684.png)

![](img/7011eb2fe997e9d598bb4046015d583f_685.png)

ok。

![](img/7011eb2fe997e9d598bb4046015d583f_687.png)

Better。Not quite。Let's do -1。 And then here we do like。Minus。嗯。



![](img/7011eb2fe997e9d598bb4046015d583f_689.png)

![](img/7011eb2fe997e9d598bb4046015d583f_690.png)

Okay， the X is wrong。 I shouldt do like。Well。Maybe， okay。Now， this is way too big。



![](img/7011eb2fe997e9d598bb4046015d583f_692.png)

Okay， starting to look decent。

![](img/7011eb2fe997e9d598bb4046015d583f_694.png)

![](img/7011eb2fe997e9d598bb4046015d583f_695.png)

ok。I can live with that well， I think our points are wrong。



![](img/7011eb2fe997e9d598bb4046015d583f_697.png)

呃。LetLet's do like。呃。

![](img/7011eb2fe997e9d598bb4046015d583f_699.png)

Let's do this one。

![](img/7011eb2fe997e9d598bb4046015d583f_701.png)

Yeah， the point is wrong。We should really subtract to。 It was correct。 Maybe two was too much。 Yeah。

 it is too much。

![](img/7011eb2fe997e9d598bb4046015d583f_703.png)

![](img/7011eb2fe997e9d598bb4046015d583f_704.png)

台湾。

![](img/7011eb2fe997e9d598bb4046015d583f_706.png)

Okay， that looks perfect without 065。Which is nice， I'm not going to round that， just go to it。

So let's again， but let's do that slowly。Now I can know。哦。delete the whole thing， just this。Thisport。



![](img/7011eb2fe997e9d598bb4046015d583f_708.png)

Okay。

![](img/7011eb2fe997e9d598bb4046015d583f_710.png)

Yeah， well that start out。

![](img/7011eb2fe997e9d598bb4046015d583f_712.png)

Swe夷。

![](img/7011eb2fe997e9d598bb4046015d583f_714.png)

ok。This is pretty cool。I I'm happy with that。So today we did a lot of stuff a lot。

 we saw like a lot of bugs。We did bitmaps， we drew the bitmaps and we implemented them。We did。

 and I'm not going to try to remember。 We did so much。 The game is starting to get pretty。



![](img/7011eb2fe997e9d598bb4046015d583f_716.png)

H that。The game。It's starting to get like really， really cool。And our engine， our renderry engine。

In terms of feature。I'm going to say that it's now complete， feature complete。

 we don't need any more renderrring。Stuff。But what we do need， in case you haven't noticed， is audio。

We have no audio and our engine doesn't support audio yet that is Next stream's goal to implement audio。

 so I do have to come up with some audio for play。Maybe I'll just play like last game's music until I can get like nice music going on。

Yeah， maybe I'll do that。We're going to bring audio。Next time。

 and then we're going to do threading the other time。



![](img/7011eb2fe997e9d598bb4046015d583f_718.png)

Maybe30 was too much too。

![](img/7011eb2fe997e9d598bb4046015d583f_720.png)

Because if we move slowly， we shouldn't really feel that， but if we move like fast， yeah。

 we we can feel it。

![](img/7011eb2fe997e9d598bb4046015d583f_722.png)

O。😊，嗯。Thank you all for watching this stream。 I had a lot of fun today was like a very productive day these three and a half hours if you want to download a game。

😊。

![](img/7011eb2fe997e9d598bb4046015d583f_724.png)

And play not only the game， but play around the source code for free。You can do so on HO。

 you can go to dzd。h。o。

![](img/7011eb2fe997e9d598bb4046015d583f_726.png)

And then you can just download out your record to give you a tip。

But if you don't want to just take them to that end then you can download all these files。



![](img/7011eb2fe997e9d598bb4046015d583f_728.png)

It choose which absolutely you want to watch， you want to download and play around the source code because we've been streaming this whole thing all 10 episodes now are on YouTube。

And you can see from the very first line of file that we wrote all the way to what we have now and the YouTube is YouTube got Comf Danza Dan。



![](img/7011eb2fe997e9d598bb4046015d583f_730.png)

So as it's for today， I hope you enjoyed it as much as I did。

And I hope to see you next time were going to command audio。That's going to be really successful。

 I think。Let's see our bit maps。Well， if our wereer， yeah， we also did like random seed。

If our renderer help us， if our Rer， if our random guy， okay， see Bimps perfect。

 that is just perfect strong blocks。crap got stronger。



![](img/7011eb2fe997e9d598bb4046015d583f_732.png)

Okay。

![](img/7011eb2fe997e9d598bb4046015d583f_734.png)

So that's it for me， thank you for watching and see you guys next time。


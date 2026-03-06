# 【从零开始用C语言制作游戏】 p11 Making a game in C from scratch! Ep 11： -Audio System and Mixer- -BV18i421a7DD_p11-

Helloello everybody， welcome to my new live stream where we are creating an entire game in C from scratch。

 This is the episode 11 of our series and if you have been following along we have come a long way ever since we started with a blank C file。

 so we're creating everything here on stream。😊。

![](img/7a07006fd44b8dede9f835fb4c96181a_1.png)

And let me show you what we have so far。So this is the game that we are creating。

 started out as a breakout clone。But they quickly started to adding in more interesting stuff。

 So this level。We added some pars。Okay， and。SoAnd we played around with the game played a bit。

 and so's pretty cool。Okay， and in the last stream， we finished our rendering。Kind of improvements。

Right。😊，We did Binap brainery， we created like this foritude effect， we created all sorts of stuff。

And hopefully。呃。This time， we are going to create the audio system。 Well。

 because I don't know if you guys can hear， there's no audio in the game。

So that's the goal for today。

![](img/7a07006fd44b8dede9f835fb4c96181a_3.png)

If you want to follow along， you can go to the HIO page and then you can download for free the game and the source code so you can download the game now it's a zip because now you have files。



![](img/7a07006fd44b8dede9f835fb4c96181a_5.png)

Have like data files？And then there's also the source code that you can download and play around with。

 do whatever you want to learn and all that stuff， and all of the episodes are available on YouTube。



![](img/7a07006fd44b8dede9f835fb4c96181a_7.png)

So you can come here on YouTube and watch from the very first episode。

All the way to where we are now。Hopefully to be on as well。



![](img/7a07006fd44b8dede9f835fb4c96181a_9.png)

Okay， now。Let's get started I'm go okay， I have this note here that I played around a bit and I found that it's hard to see the Bobby Y in the pg level not that we worry about that too much right now。

バラ。I'm going to just write it down so don't forget it later。以为。O。😊，Now。

 I think we're going to delete these guys we already did this。Okay， so the audio。

We can spend like a whole week or a whole month just on the audio system。

But let me like state some goals of what we want now we want。To play。Some like any， like any audio。

Any idea， that's the first step。And play an audio file。Play several audio your files。Like be able to。

你啊了。Mes like， would you like like？Left and right。Pany。To do like surround stuff。

Sttereo self should be it right， right name should be able to pan and then be able。

To change the pitch。Or的 are you。So this is like what we really wanted in our audio system。

 and then we can actually like input it。😊，So effect。And I don't know how much we can do today。

Hopefully you can do enough just to get started in the game。

And then we're also going to implement like music later on and then we can start。Doing。

Like reviewing some of the points that we're going to write today based on the specific demands。

 but that's the basic idea。

![](img/7a07006fd44b8dede9f835fb4c96181a_11.png)

And I have written like a little cheat file here。We all have like the main stuff we're going to need today because we are going to use Re sound as a library。

And using libraries are kind of finicky because they need like a lot of like no which colors are going to do and things like that。

 so I have written that。And I may take a look at that every once in a while。



![](img/7a07006fd44b8dede9f835fb4c96181a_13.png)

But hopefully。We'll be able to do that pretty smoothly and then start doing like our own stuff like if you manage to play an audio file。

Everything from down here is like our stuff。This is like the library and yeah， maybe you can。

Get along pretty well。 So first of all。I'm going to include the library。

 I'm going to go to your Windows platform。And we have like5 IO。And let's do like this like。好吧。

didn you have anything else。Let's do like call back and play。Okay， and now I'm going to create。

An audio section here in the file， and I'm going to do likeking it audio win 32。系あげ。

So we are going to， first of all， include。The Dso。h。Which is the library that we're going to use。

Okay， and。However， we also have to load the DLL because we can't statically linked。

In we've been statically linking everything。So far。Yeah， we've set links with user 32 and GDI 32。

But now we are going to have to load the libraries and DL。 So I'm going to like。

Let me show you guys the documentation for。

![](img/7a07006fd44b8dede9f835fb4c96181a_15.png)

Get Pra load library。

![](img/7a07006fd44b8dede9f835fb4c96181a_17.png)

So that's what you're going to use yeah age module， just going to call this function。

 pass out the library name。

![](img/7a07006fd44b8dede9f835fb4c96181a_19.png)

Which is just。李想。GoDLL and that should be everyone's computer。And that's called like D sound ELL。待ち。

Okay， and。We will have a ton of ifs here， so if we don't have a sound DLL。

 then we can go like step by。Maybe you should like a ct。So。0。Yeah， okay， because。Yeah。

 then we can do like better errors later on。 So now we're going to get the proc address。



![](img/7a07006fd44b8dede9f835fb4c96181a_21.png)

Inside the DLL， right， let me show you guys this call。

We're going to pass the call name in the module and then' going to return a procedure to us。



![](img/7a07006fd44b8dede9f835fb4c96181a_23.png)

The module is the D soundund。DLL and the procedure name that we need is direct sound。

That's the only thing we need。From the DLL， all the other ones are going to。



![](img/7a07006fd44b8dede9f835fb4c96181a_25.png)

Be based off that。 So the direct sound create Now let's go to the。は。8。Do we need。A type for that。

 Okay， so this is what we need。 So we're going type the here。



![](img/7a07006fd44b8dede9f835fb4c96181a_27.png)

Dect sound， create。嗯。Missing type testifier。Well。How am I supposed to do the type De and every once in a while？

I may actually cheat a little bit more。And。Yeah。And check out how we do the。In the other code。Okay。

 yeah。But I don't think you can do that yeah， we can't let's do like。Ex。Okay。

 now this is the call that we're going to get from the DLL。

So we're going to create a direct sound create。That's call that。Some create can be equal to that。

And we have to cast。To a direct some create pointer。Okay， that looks good now we can probably do。

This as well。And then we'm going to call that and the way it works on direct sound library have this like if succeeded。

Succeeded macro。Then we can pass like our calls。Like。When go， I direct some， create。And we need。To。

 yeah， to call that。 And I's see what it needs。 Yeah。 It's going need LP Gi G I D， Let's do like 0。

And we need a pointer to a directile， and this is like the structure we're going to use。

To interface with all the other functions so direct sound。ますでさ。I don't know if I need it， though。

Direct sound。And。Yeah。😊，I don't know if I should pass like the pointer。The pointer to the。

 the pointer to the pointer so。And then this guy can kill。O。😊。

Now that's trying to compile and run and just see if we managed to get this far。In the library。Okay。

😊，Now let's go well we should also call。We are doing it audio。And if everything works out。

 this next stream。We are going to。We are going to do the。

We are going to do the motor threading and make the audio AC。

 but for now I have do one step at a time， so win 32。



![](img/7a07006fd44b8dede9f835fb4c96181a_29.png)

イネーちゃ audioデオ。那行。Oh， nothing happens for a start。

![](img/7a07006fd44b8dede9f835fb4c96181a_31.png)

是。两得起。What。😮。

![](img/7a07006fd44b8dede9f835fb4c96181a_33.png)

Yeah， okay， we have to turn off。

![](img/7a07006fd44b8dede9f835fb4c96181a_35.png)

The optimization。

![](img/7a07006fd44b8dede9f835fb4c96181a_37.png)

Okay， yeah， that's starting it off。 And let's see now what happens。 First of all。

 we try to load and we do load。 Looks good。 Then we try to get the proc address。

 and we do have an address。Now let's try to create the sound and we succeed。

Now this guy is erect sound。s a pointer to a with all the info we need now to actually start building the。



![](img/7a07006fd44b8dede9f835fb4c96181a_39.png)

The objects we need and what we need。

![](img/7a07006fd44b8dede9f835fb4c96181a_41.png)

It's actually two things。We need actually we need one thing， but to get that thing。

 we need more things， so we need a sound buffer。Just like we did in the very first episode that we got a Raer buffer to draw our graphics。

 we're going to get a sound buffer from the library。And the way the sound bufferer works。

 it's a fixed amount of time because the problem with audio comparing to live graphics。

Is that audio is continuous， like graphics， you can just display a picture？

And if everything freezes and it works like that， that's okay。

 but the audio has to continuously update， you can't like freeze the audio。

They'll like stop in the middle and they'll probably sound weird。 So the way it works。

 we have a fixed buffer then let's say like one second it's like some fixed length right。

And then we start， you know。I don't know， feeling that buffer with our sounds right that we mix。

When they hit the end of the buffer， it just loops around to the other side so it starts overriding the beginning of the buffers。

 it's a circular buffer。And the thing is， and that's the trickyy part of doing sound we're going to get to in a second that we want to write。

As I don't know。As short a time as we can， like we want to write。

Just a couple of samples or frames let's call them that because we want like not a lot of delay。

 but if you do write just a little bit and we failed。2。To write when that finishes to play。

Then I'm going to get like weird talent here。So we always have to keep a ahead of the play cursor。

 which is like。What imagine like a train that is moving。And that train is the audio。The audio。

 let's say hardware， right， it has to keep playing something， even though even if it's nothing。

 has to be keep playing something。And we have to now lay the tracks in front of the train。

 and we want to lay them as closely as possible because we don't want any delay because if we lay them way ahead。

Like let say let's say we laid this track here in the players here and then like the player shoots and we expect like a shooting sound effect。

The shooting can't happen here because you already wrote all this stuff。So we've only won。

Just a little bit delay， so we want the train to be just。



![](img/7a07006fd44b8dede9f835fb4c96181a_43.png)

Close enough so we can lay the tracks in a。In a like updated fashion。

 but just far enough so we don't miss it。So okay， that's the basic idea。 So how do we get the buffer。

 we can use these create sound buffer calls， let me show you guys in the docs。



![](img/7a07006fd44b8dede9f835fb4c96181a_45.png)

As you like。Create sound buffer。And that's what we need， yeah。To raise sound buffer， however。

 we need to create actually two sound buffers。Because that's how it works one。

 which're just called the primary buffer we're not actually going to use that's for that's mostly for like legacy region reasons that's there because nowadays Windows does all the stuff for us。

 we don't write direct to the hardware。So we have to create the primary buffer we did nothing with it。

 then we create the other buffer， which is what we want， right？



![](img/7a07006fd44b8dede9f835fb4c96181a_47.png)

手痒。And the way we're going to create the buffer， I can just copied this guy is that we need a couple things。

So。And actually this call we're going to call from the direct sound and it comes with a virtual table。

 so it's a long pointer to a。Virtual table。I think that's it。I'm not entirely sure。

 but we're in a couple things， we need this guy which is a pointer to a DS buffer description。

So we need a buffer。Description。

![](img/7a07006fd44b8dede9f835fb4c96181a_49.png)

Okay now。And let's fill that up。 And all we need to do is actually， this guy set the size。



![](img/7a07006fd44b8dede9f835fb4c96181a_51.png)

To the actual size。So buffer description。That sized size off。But for description。



![](img/7a07006fd44b8dede9f835fb4c96181a_53.png)

And we also need flags。And。Yeah。We're going to do the primary buffer。



![](img/7a07006fd44b8dede9f835fb4c96181a_55.png)

For this this first guy， so buffer。That。E W。Flalash。I think that's all I need。Missing semicolon。Okay。

 long pointer to virtual table。

![](img/7a07006fd44b8dede9f835fb4c96181a_57.png)

Its like this。Let's go。 Let's go to the。

![](img/7a07006fd44b8dede9f835fb4c96181a_59.png)

Let's see。好。

![](img/7a07006fd44b8dede9f835fb4c96181a_61.png)

This guy is specified。So， you can know。

![](img/7a07006fd44b8dede9f835fb4c96181a_63.png)

The virtual table sign well。Think this is going to be another cheat。哎LP。NowP。BTBL。Oh。Well。

 forgot to do。It was one thing， but yeah， just at the cooperative level， the thing I saw it， right？啊。

However。I don't think。LP， BTBL， yeah， okay。So。Like we need to Yeah。

 but part we do that is set the cognitive level so same thing。

 but now we're going to do the call in the new way， so we're going to do like direct sound。LP。

 ETB else is points for virtual table anyone want to call。



![](img/7a07006fd44b8dede9f835fb4c96181a_65.png)

Se。Cooperative level。And this。This call。

![](img/7a07006fd44b8dede9f835fb4c96181a_67.png)

It's just like the set， which we know we're using， right？We dont need to pass the window here。

And it to a window。

![](img/7a07006fd44b8dede9f835fb4c96181a_69.png)

And then we need like some flags and I think we need like。嗯。Maybe're going to get explosive。Or like。



![](img/7a07006fd44b8dede9f835fb4c96181a_71.png)

In our in the other code example， I think I passed something like。看ry already。And yeah。

 and even though the documentation doesn't say in the C version of the direct sound。

 we do have to pass the direct sound to every call。てンク？嗯。😊，reasonable， let's see。

OPVTB does not remember a direct sound。嗯。来'这。Let's debug and see what we have。In our direct sound。

 I think that's going to be easier。

![](img/7a07006fd44b8dede9f835fb4c96181a_73.png)

If need to audio， that's best。Yeah。So our direct sound well。Let's see if we can access this sky。

I direct sound。Oops， I think we got that。Maybe we just call the methods and we don't need the V table。



![](img/7a07006fd44b8dede9f835fb4c96181a_75.png)

Yeah， let's just straight up call。S of call。The set cooperative level。知。

We have to do through the V table。So it's a long pointer to a virtual take。Okay。

 I guess it just misspelld it。BTBL。Okay。So let's get going。We should be able to create。

Orm a first guy。So we should pass the pointer to the buffer description。Then we should pass a。

A pointer to a pointer to a direct sound let's called that。Primary buffer。Okay。And then。Okay。

 incompatible， Okay， yeah， the first argument again has to be the direct。Okay。That looks correct。

And across test， I get succeeded。Again见。And。Let's feel like。



![](img/7a07006fd44b8dede9f835fb4c96181a_77.png)

And let's see if we succeeded or not。Okay， we did succeed。

Now we have a pointer to our primary buffer。But like I said。We actually need the secondary buffer。



![](img/7a07006fd44b8dede9f835fb4c96181a_79.png)

Which is the next one I're going to create。And for this next one。I don't even think I how to do it。

Yeah and for the next one， we also have to specified a wave format X。Which is basically。No。

 the specification of the kind of buffer we want， just like we passed our bitmap info。

Sa that we want like 32 bit with RGB with this width and height going to do the same thing for the audio。

And let's see how this guy is specified。

![](img/7a07006fd44b8dede9f835fb4c96181a_81.png)

Yeah。😊，So we have5 thing I format， which format do we want， we want PCM。



![](img/7a07006fd44b8dede9f835fb4c96181a_83.png)

Let's do one at a time。Wave format dot。W format。系。Can you close this guy？Syntax error。Okay。

Number of channels。Ne two channels we're going to do stereo。Samples per second。

So I don't know if you guys know。But like the way， just like the pixel is the like the。

The most basic unit of graphics。

![](img/7a07006fd44b8dede9f835fb4c96181a_85.png)

Audio deals with samples， so we draw like the waveform like this。

Which is like we usually dont see the audio， right， the way it actually is stored is like points。

Indescribe。Specify know how it looks in certain point of time。And。These points are usually signed 16。

Bit integers， but there's also like float， like 16 bit float。



![](img/7a07006fd44b8dede9f835fb4c96181a_87.png)

But the number of samples we're going to do is let's say 44。1 k。So when you say like， oh。

 this audio file is 45。1 kilohertz。That's what I mean how many samples there are in one second。



![](img/7a07006fd44b8dede9f835fb4c96181a_89.png)

Let's go back。Average bites per second and you know that's。



![](img/7a07006fd44b8dede9f835fb4c96181a_91.png)

Why I made my notes the average bike per second。Let's see。It's going to be 16 bits。Right。

 which is like the size of。This guy， this side of a 16 bit inger。Which is how many debates we have。

Times。Everage bikes per second。So yeah， time is this guy。



![](img/7a07006fd44b8dede9f835fb4c96181a_93.png)

Well， just check。Should be the product to the samples and the end black line， okay。

 so no actuallyley you are none right？

![](img/7a07006fd44b8dede9f835fb4c96181a_95.png)

I'm going to leave this guy for later。Hey， can I show my programming server？

What do you mean to show your programming here， I mean drop in the chat Discord server， go ahead。

 man。That's cool， no problem。嗯。Okay。Now， that's actually， we actually need more stuff。



![](img/7a07006fd44b8dede9f835fb4c96181a_97.png)

The block line and let do like the bits per sample， that's going to be the 16 bits per sample， right？



![](img/7a07006fd44b8dede9f835fb4c96181a_99.png)

Yeah， okay， that's yourmic experience Okay， thanks for sharing man maybe I'm going to check out later and for everyone that's watching。

 you want to check out Ox Hunters Disc server programming Disc server。That'll be pretty cool。Okay。

 so 16 bits for sample。And now we can do these things like the block line， things like that。

Like the block a line。Is yeah， now I'm going to cheat look at my。

Like the block line is the number of channels so I'm going。And of channels times the bits for sample。

Divided by eight because it needs like the bias。

![](img/7a07006fd44b8dede9f835fb4c96181a_101.png)

Okay， that looks reasonable and now we need the last guy， which is this guy。



![](img/7a07006fd44b8dede9f835fb4c96181a_103.png)

The average bites per second。And that is the samples。For second。Yeah。Times the block align。

Which gives us how many bites we have。

![](img/7a07006fd44b8dede9f835fb4c96181a_105.png)

Okay， and the size。The size invites。This ratio can be used for non。



![](img/7a07006fd44b8dede9f835fb4c96181a_107.png)

Do you have remember sent to。This is exactly zero Okay so we have our wave specification。

And that' what we're going to do。Is create our buffer， really。

So it's going to be pretty much the same thing。 But in fact， just like we created our。

Our aer buffer here。For the game to use， I think。I'm going to create， like。No。

 what the game time going is this。But we do need to global though， yeah。

 things are going to be easier。To create like a soundbook。Okay， and now we're going to create。Yeah。

 but also we need to like reset our buffer description because it worked for the primary buffer banana not。

So the flags we need new flags。And the flags we need let let me go back to the documentation。

For this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_109.png)

And the flags we need， let's see。Yeah， we have a lot of stuff we can play around with。

Like we're going to do the mixing ourselves so this pain and control stuff。We don't really care。

But this is pretty cool global the global focus means that it's going to be playing even though we don't。



![](img/7a07006fd44b8dede9f835fb4c96181a_111.png)

Are the primary window？And I think we're going to set that。



![](img/7a07006fd44b8dede9f835fb4c96181a_113.png)

Okay。😊，And let's see what else we need。size yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_115.png)

Fx buffer bites， yeah。就。The buffer bites are going to be equal。Two let's say one second。

 that's what we did the first time。It's going to be like the samples per second。Times。The 16。

Guide times the number of channels。And you're also going to store these helper variable like。Oh。

 how many bikes we have in our buffer like that？B her description were definition。Okay。To cast that。

Yeah， thats。有屁。No， it was just a DS book。ok。没有。

![](img/7a07006fd44b8dede9f835fb4c96181a_117.png)

Let's see if we need something else and we do need also in our buffer for description。Yeah。

 buffer for bites。And we're going to pass the wave format X。



![](img/7a07006fd44b8dede9f835fb4c96181a_119.png)

That we specified up there。

![](img/7a07006fd44b8dede9f835fb4c96181a_121.png)

嗯。

![](img/7a07006fd44b8dede9f835fb4c96181a_123.png)

You go to a pointer to the wave。Okay， now let's see if we succeed。

Call in this guy and it's probably a search。Success else， like。Inval。Do you have liking。Coode back。

 yeah we do。

![](img/7a07006fd44b8dede9f835fb4c96181a_125.png)

Okay。Now， let's see if。Reishize everything correctly。



![](img/7a07006fd44b8dede9f835fb4c96181a_127.png)

Okay， that's a success。Well， it was better than I expected。

 So now that we created the buffer this guy。We should be able to， first of all。

 write to it and then play it So I'm going to do like an internal void。To fill sound。My first， just。

Testing。And then you can do like an internal。Avoid。I mean 32， just make sure that。

Our name spacing doesn't well C name spacing， right？So we 32 and we are going to。Udate。三个分。

And actually， you don't need to do anything here， honestly。All we're going to do maybe is just。

And we're going to fill and then play it， Okay， yeah， makes sense。

So in order to fill the sound buffer， what we are going to use is a function。



![](img/7a07006fd44b8dede9f835fb4c96181a_129.png)

Called a lock， like。接例佢啊。Lock。Yeah。This is the function we have to lock the sound buffer for writing and then we're going to say。

 okay， where do you want to write where your startinging position and then a number of bytes。

And I don't know if you guys remember， but I said that we're going to use like a circular buffer。

That means that， maybe。We want to like from disposition。Half the buffer。

 So we know how are going to do that。 They're going to return towards us two positions。

So we're going to say the region one and like the possibly the region two。If we are to wrap。

 so we have to do this loop like。

![](img/7a07006fd44b8dede9f835fb4c96181a_131.png)

Two possible readings。Okay。😊，So的话。That's just as like you've succeeded。In the lock。

 we're going to come from the sound buffer。Some buffer and same thing I'm point to a virtual table。

 VTBL。Lock。Okay， and let's do like the whole buffer。是。Let's do， like， sound buffer。Thet size。Yeah。

 I'm going to start that and then we need a couple variables， so we're going to do a like lesion。One。

 and then a D word for like region。ion one size and same thing for you。So we're going to pass。

The audio pointer， that's going to be the reason。One。

 and then I'm going to pass a pointer to the region one。Size。And the same thing。



![](img/7a07006fd44b8dede9f835fb4c96181a_133.png)

For region 2。And the flags， I don't think we needed flags。Now we don。



![](img/7a07006fd44b8dede9f835fb4c96181a_135.png)

We good bestide book。But。Since they're not going to do the type of for every time。

 let's see if this works。Okay， now possibly now we have these guys and let's just know keep going step by step and see if we do have these guys so size not a number。

 yeah。And you know what， I think you're going to do something like。Sound buffer。

And we're going to do the same thing as we did here， we're going to have a platform nonspec。

And a platform specific。Well， it actually doesn't matter that this is platform from nonspec。

Because the game's not going to use it。Well。Maybe the game will yeah。

 let's make the game use this guy so。We need a couple things now first of all。

 let's do one thing at a time all we have is the size。Maybe， yeah， thanks Bford。Size in。Rights。O。😊。

a platform nonspec。Is the。Is this guy。I a specific。This is like B。And， I'm going to have buffer。book。

Some buffer undeclared。Oh， great。Sound buffer。The word。嗯。Yeah。

 all same thing you have to pass firstly。Sound buffer。Oh。

 not the sound buffer for maybe that directs。Yes， sound buffer， buffer。Okay， Reg one。

Size undeclared identifying。 Yeah， I call that。That's not gonna help。Function pointer2， yeah。

 we do have the last argument that we chose to ignore， but we do have to passive， okay。

Now I have to call the fill sound buffer going to and then we're going to try to play。

I am going toward warn you。That today is a audio day and that's an audio implementinging day。

 so we may have a lot of stuff going wrong。Charlie means you guys going to hear weird sounds。

I am't going to try to warn you and probably like turn the volume down here so guys you know don't go death and then sue me。

But it had been wrong。So the sound buffer。

![](img/7a07006fd44b8dede9f835fb4c96181a_137.png)

But we're going to call it that place， we're going to do like direct。Sound like。嗯，应该这样。Yeah。

 just got。So reserve must be zero priority， the lowest priority is zero。

 the highest priority is this guy。Well， probably do like the highest priority， rate， flags。

 and if it's loopy or not。Okay， so we're going to set it play continuously。



![](img/7a07006fd44b8dede9f835fb4c96181a_139.png)

And just expect。That we manage。To call that。

![](img/7a07006fd44b8dede9f835fb4c96181a_141.png)

To fill that on time， so reserved zero priority yeah。

 let's do like the full priority guy because we are a game after all。



![](img/7a07006fd44b8dede9f835fb4c96181a_143.png)

FF。Okay。😊，Fs do。I'm not going to call plays because we're not filling that with anything。



![](img/7a07006fd44b8dede9f835fb4c96181a_145.png)

小。So need worry about that for now， let's just try to see if we get。forget。This guy's successfully。

Yeah。O。No。Sound buffer， yeah， I have to feel that that's。



![](img/7a07006fd44b8dede9f835fb4c96181a_147.png)

That's weird because we change what the sound buffer is。嗯。呃。Yeah， this guy should actually be。Oh。

 we that's the primary buffer。So that was in mistake， so we're going to do a sound buffer do though。

Okay， nice。

![](img/7a07006fd44b8dede9f835fb4c96181a_149.png)

Okay， let's try that one more time。Okay， and we failed again。If we didn't crash。

 I'm not sure that was good or not， Okay， so we're asking us to lock and he failed the call。Well。



![](img/7a07006fd44b8dede9f835fb4c96181a_151.png)

We are asking。Zero bytes， right？So I can' argue with that。 So let's let's do like。

Some of the相 bufferer。Feeling sound buffer dot size is going to be equal to。This guy。

There are of channels。嗯。Yeah。Not sure， I think。第该。You're going to do like this。

Again we actually couldn do sound buffer dot。Channel count。And a samples per second。

Samples per second。そ。Oh， let's do like。No yeah， that's right for you。Okay， some buffer。Second。

And this one's going to be the sound buffer。Channel count。Okay， and。

I see this guy up here on the top。Just's like this sounds back。Then， this guy。Sound buffer。count。

This guy is sound buffer。Samples per second。Oh， this guy。

 I think might just hardcode that because we are assuming we're going to use sight of this guy。Yeah。

O。😊，Yeah， and the buffer for bites now。It be the sound buffer。Yeah we don't have council。

That do like channel。Count， and let's do。Which one was that？The other one， Sam percent。Okay。

 from int to word。

![](img/7a07006fd44b8dede9f835fb4c96181a_153.png)

Yeah， well。Whatever， okay。Now。Let's see， if we correctly。Are asking for， like。Yeah， a lot of guys。

 okay， now we have successful。

![](img/7a07006fd44b8dede9f835fb4c96181a_155.png)

Successful it might be。Now what I'm going to do is go through all the samples。

Whi's going to go like from one。To the region one。Size。Right。And。Let's do a square wave。

 let's fill this。This buffer with a wave like this。Okay。Let's do like square。

 and let's do like square frequency。可以。啊来。啊。Just for testing。And if' up。Let's say that sample is。

And this like of volume， this 500。The volume。Well non divide， let's see the intensity of the sound。

Okay， now we want to set the region one， so we're going to do like。Let's do， like， you 16。

I'm sorry S 16。 Let's do like。Sample。I'm going to start that Reg one。

And we're going to do like samples going to equal to O weR to havec。I still like。嗯。使かれ。This guy this。

Yeah。Okay， and。Sample？Sign on side。Yeah， thats to。Okay， I'm gonna do the same thing。For the region 2。

Okay。Okay， now。For every sample， we are also going to increment。The square frequency。

And if the square frequency， this is going to set the pitch of the sound so if this guy。

I'm not sure if this guy is greater than。I think it's like 400 something。

It's goes to the middle a note。I'm going to set this square to zero。And I'm going to。Change the。

It's just for us to test。Squarely so we can hear something。Okay。

 so I am going to explore this territory first and'm going to put my little earbuds。

And I'm going to turn the desktop audio off for you guys。 So you guys have no chance of going de。

 And maybe if it works， I'm going to。Go set the volume back for you guys。

And we also have to do the plate。Pla on member。It is not。Pass。价格。Okay。Now let's see。

 I'm going to turn the volume really down just in case item with F。



![](img/7a07006fd44b8dede9f835fb4c96181a_157.png)

And let's see if we have something。

![](img/7a07006fd44b8dede9f835fb4c96181a_159.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_160.png)

Okay， I don't hear anything， let's just debug to see if we fill that with something。So right here。

First of all， let's see， do we have valid data and we have a valid point for this guy this guy is the whole thing。

We are supposed to fill a well or not。

![](img/7a07006fd44b8dede9f835fb4c96181a_162.png)

Not incrementing the app。Pointer， so we're actually just。Feeling the first。The first sample。

That's not going to do anything。It's not even like video where just feeling one pixelel。

 you can see the pixelixel audio， you have to feel like the difference between them to select。



![](img/7a07006fd44b8dede9f835fb4c96181a_164.png)

For the airwa， for the air。To vibrate things like that， okay。

 let's go one more time and let's debug before we try to hear anything so。

Our region is correct apparently。So we're going to run and we're going to set the sample to 500。

 and then we're going to increment that and what we expect to see I'm going to see here in the watch window。

I catch that too。What do we expect to see， let's see like。64 of those well。And more than 64。

So we were filling these guys with 500， but if we get to like this point。Okay。

 and we probably didn't want。Exs violation。Okay， this size is bys。



![](img/7a07006fd44b8dede9f835fb4c96181a_166.png)

So I'm going to probably have to calculate like。D word。Tition one。Sample。

Which is this guy dividedd by。numberable of bytes per sample。

 And I don't think we have that in the sound buffer。Rights。呃。Same thing has to be done。For this guy。

In ran you with the region two。给看。And this one。Okay。Let's add this guy。Thats first sample。

And we also have to。Set them。Vice percent are going to be the channel count。Times the size of。Theax。

And now I can probably disappear。times like this。sound buffer times。By for sample。And let's see。

 Where else。

![](img/7a07006fd44b8dede9f835fb4c96181a_168.png)

有。Then place guess。Okay， again。Let' see。We are feeling these guys and let's try to go down here and we don't crash it's a good sign let's see like a thousand of those。

Okay， so we're setting 5095。So maybe now we should hear something。Well， I don't hear anything。



![](img/7a07006fd44b8dede9f835fb4c96181a_170.png)

I don't hear anything。嗯。We could play around with these values。

 but these sound kind of reasonable to me， I think。What I could do is try to turn them way up。

And the frequency。Yeah。We can probably turn that a little bit lower as well， we expect like a。



![](img/7a07006fd44b8dede9f835fb4c96181a_172.png)

A base your sound。No， I'm going to try to turn on my speakers that have a better。



![](img/7a07006fd44b8dede9f835fb4c96181a_174.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_175.png)

Let's see if our a place exceeded。If it didn't succeed。Sa。Frash。



![](img/7a07006fd44b8dede9f835fb4c96181a_177.png)

Yeah， and we do crash， okay。

![](img/7a07006fd44b8dede9f835fb4c96181a_179.png)

嗯。Play sound buffer 0，0。I's see if we' missing something that play。Oh， yeah。 Actually。

 you should set that to loop。

![](img/7a07006fd44b8dede9f835fb4c96181a_181.png)

I'Not sure that's the problem。

![](img/7a07006fd44b8dede9f835fb4c96181a_183.png)

And it was probably just。Try setting this guy to zero at first。

 then we could try and make that priority。

![](img/7a07006fd44b8dede9f835fb4c96181a_185.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_186.png)

Can you guys hear that， it's going through my speakers so I think you can hear that。



![](img/7a07006fd44b8dede9f835fb4c96181a_188.png)

That。

![](img/7a07006fd44b8dede9f835fb4c96181a_190.png)

う。Is somewhat working。So we do hear wave。I don't know。

 maybe I'm going to just keep that on my speakers。For now。And then later on， we can do like。

Desktop audio for you guys， these are just like sound。 Let's see this was the problem。



![](img/7a07006fd44b8dede9f835fb4c96181a_192.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_193.png)

Yeah。So apparently you can't set a priority high。Anyways。



![](img/7a07006fd44b8dede9f835fb4c96181a_195.png)

So why do we have just one guy？はい。They sound like a really crazy alarm and the answer is。



![](img/7a07006fd44b8dede9f835fb4c96181a_197.png)

It's because since we're doing stereo， we should really like do for both。Guys。

So when we are running through our loop， which we're going to do in a while。

This should like do like the right channel and the left channel or the other way around。



![](img/7a07006fd44b8dede9f835fb4c96181a_199.png)

Can you hear that beautiful sign？I'm going to make it run through your speakers。



![](img/7a07006fd44b8dede9f835fb4c96181a_201.png)

I see if it's I it's too low or too high， let's see。

Did you guys here that we should also be able to hear that there's a small problem when it loops around。



![](img/7a07006fd44b8dede9f835fb4c96181a_203.png)

So what we are drawing。He's actually this guy something like this。And。Yeah， we can hear， Okay。

 thanks， puzzle Dev。So the problem is。When we loop around。

 we should actually write from this point and not like just infinitely loop。

 that's not a problem we're going to have since this is just a test。 So for our fill sound buffer。



![](img/7a07006fd44b8dede9f835fb4c96181a_205.png)

Which I actually want to do is I think I'm going to set that to zero。

So I'm going to make no sound in the beginninginea。可。😊。

Just so you can clear the sound buffer maybe sure about it。Call that clear sound buffer。

 and then the fill sound buffer is going to be different。Okay。😊，啊。Okay。

 so this is going to be the clear。Sound buffer。

![](img/7a07006fd44b8dede9f835fb4c96181a_207.png)

And now we should have nothing。Can we have nothing？



![](img/7a07006fd44b8dede9f835fb4c96181a_209.png)

呃。Now we're going to do the fill， but the fill， as I said， has to be done every frame。Okay。

 so this is what we're going to do now， we're going to start building the actual thing。

 so let's go to our game。We managed to play any audio。So that's mission one succeeded， mission two。

 play an audio file。So this is a little bit trickier， I mean， just a little bit。

 so I have from the other project。你。Check out。Here if I have。To open that here。

I from the other project like a song that I did。I'm going to do like new ones for this project as well。

Yeah。So。Let's try to play that。And if you managed to play that。🎼This audio file。

 we're going to be in a great position to finish our。😊，How are going to do that。

 I'm going to first of all， copy that。ToThe breakout。Data folder。

 I'm gonna to call that like test dot W A P。 And just like we did in the。In the image。

T where we use the library， you're going to use the library to read this guy。

But this library I I wrote myself， so I think it's going to be easier for us to do have any problem。

But I am going to run through the code， it's not that big。呃。

The library is going to decode the wave file， which not that hard。 and it's going to give us a。

Uncompressed sequenceified， okay？So let's see the code and we have like a wave in order， yes， we do。

Let me throw that on the breakout。Cod folder。Okay。So。Breakout。Code wave part。 So this is how we use。

The way you can importer。We have a loaded tostruct which has a sample count， a channel count。

 and the samples。And then we just do it like this。He uses the Read entire file and it doesn't free memory。

呃。Yeah， or we can load from every。I think we're going to prefer to look from memory。

And the fast back， okay， so it to be dot wave PCm 16 bit per sample， one are two。Channels。

 and it interleas right left， right left， right left， which is exactly what we need。Okay。

 and this is the code for doing the thing。And let's see when we load the file。

 we just call the OSure entire file。But I think I may actually just delete this guy。From our use。

 well， yeah。Now， let's see。 that's also important here。Our wave importer dot C。And actually。

 I may be called that doh just because the librarian didn't write that。On stream。Yeah。

Call that waitingpart。 age。Just so we can there own counter lines that we wrote the counter lines that we didn't write。

But it's not that big a final。And it's like 200 lines。Okay。Now that we have a waving porter。

 we can go back to a game and just like we did the dipm guy here。We're going to do a loaded sound。

And call that test sound。And let's do like the bit map， same thing。So， loaded。Oh how that sound。

Load WAV and you're going to pass data。Test dot W A V。And we're going to go step by step， sound well。

楼点。Test sound。Okay。😊，L WV undefined。哦，我放那。Yeah， well。That's， actually。Let's actually keep this guy。

H个。Well， that's okay。Loaded sound。load系啲。I好。We're gonna do。Strerange。

0 S we can entire file or file name。Then I'm going to do load。Wayve from memory vi。



![](img/7a07006fd44b8dede9f835fb4c96181a_211.png)

Yeah。Let's see if if we have like a somewhat decent and let me just check out this really quickly if I actually allocate memory of I just copy。



![](img/7a07006fd44b8dede9f835fb4c96181a_213.png)

Samples？Result。That's hey， I just copied the sample。对车。So I don't free。

Let's go back with the documentation。Equals those weight。Cause。O S 3。Yeah。

 that was kind of always the time。And doesn't。O。

![](img/7a07006fd44b8dede9f835fb4c96181a_215.png)

Perfect。Now let's go back to the game。I don't know the game tab。

 I think when a pin it doesn't want at all to be stuck on the future studio。

 even though I did that like three times and let's try to pin that。Okay。

 let's see if we have a test count。That's sound sample count， channel count and samples。

 let's see the samples。Does that look reasonable。Yeah， I think it does three。Yeah。Okay。



![](img/7a07006fd44b8dede9f835fb4c96181a_217.png)

Now， what we need is to call。A function like。I think you'm want to call。

And createre a new file and do like audio vaccine。I'm going to do an internal void。

 Let's do like update。啊，牛。And the game， let's make call that updating instead of simulateim because we also do all sorts of stuff here。

So。We in 32。信用了。聞えましす。で game？And then let's also do a date audio。Yeah， let's do it like this。updateて。

Then。We should。Also， include。还有的し。嗯。Okay。Now， what do we want to do？Update to audio。

All you want to do for the game is going to pass。A。A memory that I began going to write。

And we're also going to pass。A呀。The count。For the game。Right， and you know what。

In order for the game not to worry about the circular buffer thing。

I think I'm going to allocate here in the in。are you。Yeah。Yeah， I'm going to do like。Sound buffer。

Dot。Then we're going to change the name。To from buffer， yeah。do at the end of time。Com buffer。

To like platforms。Buffffer。Just so the game doesn't worry about that。Then I'm going to have a buffer。

 which is for the game Tory about。Well。You know what？I think this guy。嬉し。Out here。So。

 this is the game。Game sound buffer。And I think when it do the same thing with a video。

It's going to be cleaner。Yeah，' well let's get this company first。And then。Then after this comp。

 I' was going to clean up the。You guys understood it。They're very。Okay。😊，Okay。

Sound buffer and it's also。Butut this guy。Up here in the platform comment。

So platform services to the game。こち？Yeah， we do， like。R迪哦。Graphics。S angry。ok。😊，Okay。

And for the rendering。That's the same thing。 So this guy。It's just going to be。We 32。

This guy should be。Bit map info， it's going to be clean， I think。Okay， kind of like that。

 let's see if we still get。Okay， now。Let's go back to our audio thing。 Now we have this structure。

The audio。Stuff， and we're also going to pass。I still like。Samples。The samples to write。Okay。

 that's all I' going on， and this is what the game cares about in the this more like for info and this is more for doing stuff。

Okay。😊，Now， when we emit。アデオ。They're also going to。Initialize the samples。You have virtual Alec。

Copy that。And。We have the size。But for dot size。Yeah。😊，Thats about it。Okay， so what we need now。

Is to know how many samples should we write in a particular frame， so the idea is。

Call update game audio。 and it pass out yeah。いや。The sound bufferer。And then we do like。Samme。

Sound buffer， she likes。Sound looker。Correct， now the only thing we're going to do here it's going to be pretty much。

 it's going to be even an easier thing。When do you like。Anant。

 which is sound bufferffer dots samples。Then we're going to do like for every sample we want to write。

Sound buffer。Dots， samples。To write。Then then we do like。Okay。

So that's the basic idea of what we want to do。The problem is。

 how do we know how many samples we want to write because I told you the problem that we had。



![](img/7a07006fd44b8dede9f835fb4c96181a_219.png)

Like， how much should we write， should we write like a lot a little， okay？



![](img/7a07006fd44b8dede9f835fb4c96181a_221.png)

So that's where more tricky thing comes into play。And that thing。Is。Trying to get the idea， you know。

 trying to calculate that。So here。We're going do。And like。Date audio。

And then we're going to we're going to clean that up later on。For now。

 I'm going to throw all this stuff here。So what do we need when you're updating the audio？



![](img/7a07006fd44b8dede9f835fb4c96181a_223.png)

We firstly need to know where we are at。Which is like the play cursor。

This is where we are playing right now， so let's see if we roll something like this。

 this is where we are playing。RightBut Windows also gives us a right cursor。We you saying okay。

This is where you're playing， but we should really write starting from this location if you want right。

 but there are also other problems like we already wrote possibly these guys。Till this guy。

 So we don't want to start before this guy。But if for some reason， we end up you know。

Going too far behind or too far ahead， we want to。Change that one， take that into account。



![](img/7a07006fd44b8dede9f835fb4c96181a_225.png)

Okay。😊，So。

![](img/7a07006fd44b8dede9f835fb4c96181a_227.png)

First things first， let's do the。Again。Current position。Or the direct。



![](img/7a07006fd44b8dede9f835fb4c96181a_229.png)

Okay， that that's。So， all we have。If we pass。

![](img/7a07006fd44b8dede9f835fb4c96181a_231.png)

Is that correct？Just pass a point D word。

![](img/7a07006fd44b8dede9f835fb4c96181a_233.png)

Okay， okay， yeah。 but we are。 okay， because we call this。thing from the River Joe sound bufferer。

From our long pointer to a virtual table， Okay， and I to like the play cursor。And right。对。😊，第一个。Okay。

Now we have these guys。 now we should really calculate firstly， which is not that hard。

 which byte we are going to write。' going to call that。The bite。

To lock because we're doing the lock operation up there， guys remember。And right now。

 we're passing the zero one。In fact。Let's do。Yeah。😊，So ofm doing our clear， let's do our fill。

So the fill sound buffer is going pretty much same， but we're going to receive a bitete。To luck。

And they bites。To write。ok。😊，Bite to lock and bites to ride。That's。Pretty much it。ok。😊，And。Actually。

 I think we can even remove。Well， no， let let's not to move。Well， let's skip going。So。

We're going to log from this guy all the way to this guy， so this should still work。

 but now we need to know where we are at。So in our well。

Im sure be sure to save all this stuff here in the game sound buffer。

 this should only be the sound buffer， this should sort like a sound state。I don't know。

We don't have a running。

![](img/7a07006fd44b8dede9f835fb4c96181a_235.png)

Sample index， which is like which sample are we at this moment， which is like this guy。

 need to know this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_237.png)

Okay， so every time increment a sample， set the。Sound buffer dots running。Sample index plus plus。

And yeah。Okay， that sounds good， so goodbye to lock just to take into account the running sample。

Running sample index。て right now。The sound。Buter， ready sampling index。However。

We need to know how many bytes because this guys invites right so it's the how many samples times the bytes per sample so。

S bufferffer。Like， for sample。

![](img/7a07006fd44b8dede9f835fb4c96181a_239.png)

Okay， but there's another problem， which is this guy may overflow， right？

Maybe we want to start doing this guy， then we should start OM and the way we deal with overflow buffers is pretty simple。

 I think we did that before。

![](img/7a07006fd44b8dede9f835fb4c96181a_241.png)

Just a mod with a size， so it's sample for that set。Okay， so this is the bite to lock。 That was easy。

 So now we can。When we go in call the fill。あ。We played the audio and then we call the132 Fi sound buffer。

 that's the bite to lock。And lights。right， and now we do the vice right。

And this is a little bit tricky。Because we have like unexpected bys per iteration of the loop。Okay。

And。Which is like the last DT equivalent， right？So okay， okay。 yeah， that was easy enough。

What we do have， what we do want to know is actually， we have a not unexpected。Bys。分儿。Tick。

 this should be like frame。Because we are inside the main loop， but later on when you take this out。

 we're going to change this right now， the expected bytes is the bytes per second， right？ok。Times。

Our left。Unless you're like。啊。This should。mark？Because we don't want to miss frames。

 but maybe're going to do a couple of missed frames or maybe just like a giant padding safety region。

Part today and maybe tomorrow， when we do。Fredie。です。It's going to be better。Okay。😊，Now。

So this is the amount of bikes that we expect we're going to ride。Okay， however， well。

 let's do like the expected。Expected。bitete。Like， let's see。啊。Boundary bite。

So these are the amounttes， but we are here in the play cur。 I mean， that's where。

That's where we are playing， right， so the boundary in which you're going to write should start at a play cursor。

Play cursor。 Then I'm going to add the expectedant。



![](img/7a07006fd44b8dede9f835fb4c96181a_243.png)

Nice for。So that's going to give us the bite that we are planning to end our writing to。



![](img/7a07006fd44b8dede9f835fb4c96181a_245.png)

Okay。😊，So that's one thing I'm kind of， I'm kind of a。



![](img/7a07006fd44b8dede9f835fb4c96181a_247.png)

Really my notes here just because this spine's kind of tricky。



![](img/7a07006fd44b8dede9f835fb4c96181a_249.png)

Okay， now。Let's find out。About the right cursor because we do have a right cursor but。



![](img/7a07006fd44b8dede9f835fb4c96181a_251.png)

Maybe， let's say， maybe are a right cursor。Is a。ItLike， let's see。

I see we expect the frame boundary to be like。Here。

We can't we have to write at least into this guy right so we have a couple of things to manage in terms of the rightcursor。

 which is actually where we are going to。

![](img/7a07006fd44b8dede9f835fb4c96181a_253.png)

Where are you going to。Consider the actual writing。That makes sense。So。

We're going to like a safe right booker。And the safe ones going to start out as just being the normal one。

I actually really use less the auto completelete because every time it gives me around results。

The right buffer and the if。The safe right， this guy， which is the same as the right buffer。

 If it's less than the play cur， which means that we wrapped。



![](img/7a07006fd44b8dede9f835fb4c96181a_255.png)

Okay， so that was the main thing if we wrapped。

![](img/7a07006fd44b8dede9f835fb4c96181a_257.png)

We should really consider this guy as correct right， that's the only case this should be true。

The yeah， let's do like the。No， okay， so the safe。The safe is going to be just where it is。

Because we're wrapped。Right。Plus equals the whole buffer size。

Because we want this guy to be in front of this guy because we're going to go in like sub3 two。

So this is like the sound buffer dots。I think that makes sense now， in case。We are not raping。

All we need to do is add a little safety。And。I think I'm just going to hardcode that in here。

Safety bys and we have like。Let's do this guy。小湾。Frame of safety。 And then maybe you cannot make。

Of 6。So in the case that we wrapped， we're going to do the whole buffer， and in the other case。

 all we're going to do is to add the safety device。Hopefully that makes good sense。Ill say my cursor。

来。Just so guys， no， this is actually。I you pretty much。因为。

By hand you know from scratch this kind of thing in terms of yeah we are using the library the calculations we could use the library to play the sound and mix the sound as well。

 but we're not going to do that just going use the library just like we did windows just to show our guy same thing so we do have to calculate these guys by hand and that's the not so fun part。

But once it's done。

![](img/7a07006fd44b8dede9f835fb4c96181a_259.png)

Should be easy enough so。Another case that I have to worry about。Is that if our。

Save guy that we going to try to write。If it's less then this guy。

 which is the one that we expect to end the right。If it's less than， which means that。

We are kind of good to go right so our target cursor。

 which the one are're going to write to can just go all the way from this guy。

To the amounts that we want to write。So you're going to add。

We're going to add just like another frame。From the frame that we already had。Okay。

But in case we are not。Doing that。We probably want to do like。And like a whole， whole not。



![](img/7a07006fd44b8dede9f835fb4c96181a_261.png)

Some of prefer frames， Well let's see how this works out。 So if the safe。Mike bufferford。

 it' less than the expected。Battery。Yeah。😊，This means that we are pretty fast。Our target cursor。

 which is where we're going to actually consider。To， to， to write， right。

Our target cursor is going to be the expected boundary guy。Right。Plus， the expected。Nice part。

So that's how much you're going to write。In this case。In the other case。Let's just do these guys。

In the other case， and we could probably clean this up later on once we get to working。

 this is kind of what I got from the previous guy。Okay， so in the other case。

 in the case that we are after the pro by then we should write a little bit more。

And which is going to be pretty much just like。The right。Csor， which is where weno wants us to write。

Right。Plus， the expected。Bs for frame plus the safety。Signs un site must much save。Expected， yeah。

 that's through all these guysises。I don't think I should give negative。Well。O。😊。

So now that we do have our target per， we have to just make sure that it。

It wraps around just like we did。Here， wrapping the sound size， Sam thing here。

Because since we are adding all that stuff like the。We wrapped there。



![](img/7a07006fd44b8dede9f835fb4c96181a_263.png)

The right cursor， so far we know， the right cursor is right here。



![](img/7a07006fd44b8dede9f835fb4c96181a_265.png)

And then we should wrap。Our target curor。As well。Okay。So the final thing。What do。

Is to see like if the bite are going to lock。So we calculate this guy， whichs the whole point right。

 so if the bite going to lock。Bite to love。Which is the first bite。Who would you write。

 if this guy is the main point？If this guy it greater than the target。



![](img/7a07006fd44b8dede9f835fb4c96181a_267.png)

Cser。The target is where we're going to stop writing。So if we are greater than the target person。呃。

It means。That we are going to do like this whole thing we're going to write。

Like from this to this and from this did this。

![](img/7a07006fd44b8dede9f835fb4c96181a_269.png)

Okay so that's what we're going to compute， so the bytes。T's can be。The sound buffer size。Minus the。

To luck。给 plus加。So this guy gives us this first part。



![](img/7a07006fd44b8dede9f835fb4c96181a_271.png)

This guy gives us this part。

![](img/7a07006fd44b8dede9f835fb4c96181a_273.png)

对。😊，This is， this is。This is。😊，Not that much confusing， and this is a little bit more confusing。

Calculating the target gap。 but okay， so once we managed to get the bytes to write。

 all we've got to do is do the target cursor minus the bytes log。



![](img/7a07006fd44b8dede9f835fb4c96181a_275.png)

In the case。Where we are not behind。 So if feel like this is the the by log and this is the target cursor。



![](img/7a07006fd44b8dede9f835fb4c96181a_277.png)

So we're going to do target minus by2。这个。That's how many bikes we're going to ride。So， I believe。

That's about it。And。Just to make sure。There we。Still have something saying。In our hands。

I'm going to do the same thing again where we going to do like a sign。Dont do like。よし。

It's really bad name。But same thing like if。Do you like sample？Of。先こですか。Sample， I don't know。

 Did do did。This guy。Might have changed that。Okay， then I're going to add。The sample， Remember。

 have to add the left and the right guy。 and then we're going to do the up。

Samples and if the up samples are greater。You can play around with this as well。Would you like。就看这。

So if the up samples is greater than 200。We're going to set the up samples to zero。

And we actually said， yeah， no， no correct and then we set the up。It's just for testing。

And I'm going to turn off the volume for you guys。

![](img/7a07006fd44b8dede9f835fb4c96181a_279.png)

And I'm going to。IDebug our code。Okay。Now， let's see。You guys think this is going to work？

Are you guys not think this one word is because this is a little bit confusing？We updated the game。

For the first time。Safety bagss。Oh， this is the first problem I advice。



![](img/7a07006fd44b8dede9f835fb4c96181a_281.png)

Yeah， should be like bitete per sec， not for sample。Yeah so。Ex first。Oh。

 we don't have a bites for a second。I thought we did， we have samples for sec。Samples per second。

Times。Rightights。Pcent。

![](img/7a07006fd44b8dede9f835fb4c96181a_283.png)

Let's multiply it。Okay。Solar safety bytes is。3，000 bikes。

 we're going to play around with that based on our results。

I'm going to play that with that even a little bit more once we get a multith around。

 so our play cursor is 1764。And all right cursorors at a， okay， that sounds reasonable。

Our vital log since we haven't played any sound。Should。Yeah， should be like the first band。企。😊。

The expected bites per tick。This should be a constant。好。



![](img/7a07006fd44b8dede9f835fb4c96181a_285.png)

But yes， it's same same power。Should be this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_287.png)

チャです。Okay。😊，Expected bys per tick， Yeah， so we're going to do 3000 bytes。This time around。

So the boundary by is going to be the 3000。Okay， the safe， right， the right curse is 350。

 let's just see the number be。Or the pres is zero， so I think that's even better。Okay。嗯。Nice。

 so in this case， the safe by cursor is as the play cursor。No， it is not less。

 and all we're going to do is going to add the safety。To that。Okay。

 because we do want to add it in this case， we should be less than yeah。Oh， we're not。

Wenal less than the expected boundarys are going to。Be the right cursor。Plus， the expected bites。

Plus the safety。9000。If you're going to write now 9，000 samples， let's see how much。That。可以。

This is like yes。That's seconds。 Yeah， that's seconds。Maybe that's a bit too much。

And I have to play around with that。Would you like the safety margin， guys？O， now。In this case。

 you buy to locke。Is greater is not greater than then all'll have to do is subtract this guy。

 so should' right。The 9000 lightss。Now let's update the game audio。

So we have the samples which are going to be overrun every time the samples are just for our convenience。

BecauseYou could write directly to theirs to their buffer and not have to copy。

 but we don't have to worry about the ring aspect。To adopt the sample buffer for。



![](img/7a07006fd44b8dede9f835fb4c96181a_289.png)

Okay， and。Samples right， okay， we didn't set samples right， to do have to send in here。We do the。

Sound cover dot samples。ToRight。Eals。Bikes to ride。Divided by。



![](img/7a07006fd44b8dede9f835fb4c96181a_291.png)

By itss percent。And let's just see if this number would make sense。So we should write 9，000 bytes。Oh。

 we did the math wrong， that's in bites so we may actually be yeah okay。4 bytes per sample。

 So we're going to， oh， that's a better number。 So we're going to write 2000 bytes to 2000 samples。

So 2000 and let's say 200 samples divided by。Okay， this is better， so considering frame is dot0，1，6。

Writiding this guy is kind of reasonable。And yeah， we're going to play around the safety。

 but this one's kind of reasonable。Yeah。Let's just see is it disgratified feasible by four？Should be。

 Yeah， okay， also assert that。Just as a note。

![](img/7a07006fd44b8dede9f835fb4c96181a_293.png)

This guy。She always。B啊。Should have no mod for results。



![](img/7a07006fd44b8dede9f835fb4c96181a_295.png)

Okay。Yeah well， crashed。

![](img/7a07006fd44b8dede9f835fb4c96181a_297.png)

But I didt expert， what？Is this guy on physical life for it。This is not。Yes。

 we're trying to write that many bytes。But can't。Because that's not aligned， why is it not aligned？哦。

Oh， this is wrong。Oh， this is right， the bytes to write divided by the bytes per sample。

So you have to give us the samples to write。嗯。

![](img/7a07006fd44b8dede9f835fb4c96181a_299.png)

Yeah， you know what？Bikes to ride。

![](img/7a07006fd44b8dede9f835fb4c96181a_301.png)

Well， let's go back and see。Which crash here。Well， should have not stop the game at that point。

Maybe that was because of our breakpoint。I don't know。Well， when you crash。

 you're going to have to fix that。 Now let's go inside here。 So we are supposed to write。Yeah。

 this way better。Yeah like。1900。Samples。Which is like。That's pretty much same thing。Okay。

And let's hope is correct。Okay， now I'm going to try。



![](img/7a07006fd44b8dede9f835fb4c96181a_303.png)

Listening to this guy here and let's hope I don't die。



![](img/7a07006fd44b8dede9f835fb4c96181a_305.png)

Okay， now we， we crashed， let's see。Wirite crash， the bikes to ride。It's not a multiple frauds。

 just make sure that's the case。No， it is not。Because the size size should be a multiple。

Ill you later。And it is。The V to lock is zero and the target cursor。

So the target cursive probably isn't。The target cursor isn't。

Because let's if the right crisis should be。And it is。The expected oh。

 the expected bites for tick probably isn't。And the  safety bys isn't also。So， yeah。



![](img/7a07006fd44b8dede9f835fb4c96181a_307.png)

I should probably。Allign these guys。Later on。So。Oh， maybe you can just do like， first of all。

 we multipied this guy by this guy。大概睡醒。Okay。Let's do like the ugly thing。Safety bites。

Plus equals 6 bytes。Moullo。Let's see。Vice%。On a frame of safety， we're going to clean that up。

Later on and also with this guy。But for now。That's also。Safety bikes。

 that's also change that to Dick expectedant。

![](img/7a07006fd44b8dede9f835fb4c96181a_309.png)

Bights。OkayNow that shouldn't happen and let's try to hear。



![](img/7a07006fd44b8dede9f835fb4c96181a_311.png)

Okay， we're hearing nothing， I'm just going to make sure that I can hear something because sometimes these speakers go to like sleep mode or something。



![](img/7a07006fd44b8dede9f835fb4c96181a_313.png)

So I think I'm going to put this on。

![](img/7a07006fd44b8dede9f835fb4c96181a_315.png)

Yeah， they were in state。Okay， now they're obviously promoting emergency。



![](img/7a07006fd44b8dede9f835fb4c96181a_317.png)

Yeah， can't hear any。Oh， okay。Well， we can't hear anything because our Phil sound buffer doesn't do anything。

I think。Yeah， he doesn't。That's kind of secret。呃。What we're going to do now we have the at。

 and now we're going to do like the。Oh， let's call that desk。And this is like the source。

So as going to be the sound。Leford。Dot samples。And it's like source plus plus。This is the test。



![](img/7a07006fd44b8dede9f835fb4c96181a_319.png)

Okay， and I just be extra confident that this is going to work。I'm going to put a break point here。

Next hear。

![](img/7a07006fd44b8dede9f835fb4c96181a_321.png)

Well。

![](img/7a07006fd44b8dede9f835fb4c96181a_323.png)

Isn't that very。Nice。

![](img/7a07006fd44b8dede9f835fb4c96181a_325.png)

We're not calling the full sound buffer， did this call fail？You have to call failed。

Why did the call fail？嗯。And you know what we should probably。



![](img/7a07006fd44b8dede9f835fb4c96181a_327.png)

In these succeeded guys。Probably make like。We've got it put pathway。Like。Yeah。On these two guys。

Just so， we are extra safe。

![](img/7a07006fd44b8dede9f835fb4c96181a_329.png)

This one， so we should crash now。几。😊，And well， let's see。These look pretty reasonable。😡，I think。

フ realな。Oh， yeah， so we crashed because we forgot to unlock the bucket。



![](img/7a07006fd44b8dede9f835fb4c96181a_331.png)

So the buffers already is locked， because I don't think I remember that。

There have been a pain to debug that you're going to have to get the less error and it'd probably be a weird error。

 so unlock'm。

![](img/7a07006fd44b8dede9f835fb4c96181a_333.png)

Let's do。さ？Okay啊。Okay， unlock。And we just pass。

![](img/7a07006fd44b8dede9f835fb4c96181a_335.png)

Well。you see succeeded。32 sound buffer。

![](img/7a07006fd44b8dede9f835fb4c96181a_337.png)

On French of virtual table。啦。3 pass。

![](img/7a07006fd44b8dede9f835fb4c96181a_339.png)

回一下。关。Reion，1 size。Reaion 2， region 2， with extra cheese。And。And that should be should be。

Function through point。 Yeah， I always forget。 That's only the C version of direct sound that have to pass this guy。



![](img/7a07006fd44b8dede9f835fb4c96181a_341.png)

And do like the virtual table thingme。C plus plus， you， you don't。



![](img/7a07006fd44b8dede9f835fb4c96181a_343.png)

Now I see， and that was it， but I have to do that on both calls。A this not going to work？

I think we won to do that if we succeeded the luck， but we should succeed the luck anyways。



![](img/7a07006fd44b8dede9f835fb4c96181a_345.png)

有言。Okay。Now， let's see。Okay， so now we're going to lock yeah。

 all the guys the first reason because that's the first writing we're doing。And our source。

Let's read our source。Looks pretty， pretty reasonable。 That's what I meant。

I'm going to do the sample counts， the money sample index。I don't know。

 and now if we do get the correct sign， we shouldn't hear that looping problem that we heard。



![](img/7a07006fd44b8dede9f835fb4c96181a_347.png)

So let's try here that。Okay。So we do have a。

![](img/7a07006fd44b8dede9f835fb4c96181a_349.png)

A sign， but we are 30。At this point， so at some point we couldn't get a lot。Bsn zero bikes to right？

Why passing zero bytes， right？

![](img/7a07006fd44b8dede9f835fb4c96181a_351.png)

Like guys to insert。

![](img/7a07006fd44b8dede9f835fb4c96181a_353.png)

rightOr maybe if it's just zero， just more。

![](img/7a07006fd44b8dede9f835fb4c96181a_355.png)

嗯。Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_357.png)

Well。If we're not going to ride anybody bike， it's sure let's not do anything。



![](img/7a07006fd44b8dede9f835fb4c96181a_359.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_360.png)

So we got a super ugly noise。

![](img/7a07006fd44b8dede9f835fb4c96181a_362.png)

Very very nice。

![](img/7a07006fd44b8dede9f835fb4c96181a_364.png)

So呃。This is probably very wrong now。Let's see if we understand。The way we think we understand。

And in the audio， we set this guy to zero。

![](img/7a07006fd44b8dede9f835fb4c96181a_366.png)

We expect just to hear that of the noise on one speaker。



![](img/7a07006fd44b8dede9f835fb4c96181a_368.png)

Okay， that's correct， so I only heard down on the right speaker。



![](img/7a07006fd44b8dede9f835fb4c96181a_370.png)

And let's say that that， so you guys， I don't know if guys could see the difference。



![](img/7a07006fd44b8dede9f835fb4c96181a_372.png)

This is working Okay， what else couldn't be working， maybe our。

Maybe our running sample index is wrong。いでか。I think this is going to be kind of hard to be bud。



![](img/7a07006fd44b8dede9f835fb4c96181a_374.png)

This is work。Like we expected。Just to be extra sure and discard that。Let's see。

What our sound buffer says。嗯。有一次。1911。Sounds。嗯。Okay， I meant actually like。This guy。Sound。For。

Samples， it's an 9。So we should just see them。Yeah， this is pretty reasonable。Yeah。

Now I'm the fill guy。This should be correct。 Let's see if this is correct。啊。

I don't know why I couldn't。Now。Let's see。 the region1。Samples。你公安。Poiner。The9 16。Yeah。

 so we are copying nicely。

![](img/7a07006fd44b8dede9f835fb4c96181a_376.png)

But the problem really is。This code。And I think I'm going to quickly see if there's anything really wrong。

Re went through that a couple times and then I'm going to compare that with the other code just because。

This is a little bit tricky。So the safety bites， well， let's try increasing the safety bites。



![](img/7a07006fd44b8dede9f835fb4c96181a_378.png)

Maybe you're a mistake for me。Oh， nice。

![](img/7a07006fd44b8dede9f835fb4c96181a_380.png)

So that was a problem， you didn't need to deote that。But for some reason， our guys still not aligned？

See our bite lock。Is it greater than this guy？No。Oh， sorry诶。No， it is not greater。Target cursor。

Let's see if this guy's a multiple and maybe I'm just stretching and we shouldn't care about it's not a multiple for。

And on a multiple for the target trace， it should probably be the same problem。

 except this guy should not be a multiple four。

![](img/7a07006fd44b8dede9f835fb4c96181a_382.png)

6，18。

![](img/7a07006fd44b8dede9f835fb4c96181a_384.png)

Oh。Okay，6，18。Our expected bys per tick is not。Shouldn't this work， I mean。Maybe you should you like。



![](img/7a07006fd44b8dede9f835fb4c96181a_386.png)

4 minus this guy。Yeah， okay， so this what's wrong should be。



![](img/7a07006fd44b8dede9f835fb4c96181a_388.png)

Okay。

![](img/7a07006fd44b8dede9f835fb4c96181a_390.png)

It's still pretty bad。It's。Really， really bad。

![](img/7a07006fd44b8dede9f835fb4c96181a_392.png)

As do you like。Those。

![](img/7a07006fd44b8dede9f835fb4c96181a_394.png)

Forly also through an optimized build， let's do an optimized build just to see。



![](img/7a07006fd44b8dede9f835fb4c96181a_396.png)

But if we。I know I don't like that。

![](img/7a07006fd44b8dede9f835fb4c96181a_398.png)

Okay。So I think I'm just going to check out the other code， lets go through it。And。

And see if there's anything。Really wrong。So we try to get the blinkr set in the enemy。

Create the by to lock， which is like the sample index。Times the。呃。Vice for sample。

And we do that the graphic size， okay。The bites for tick。This guy has two of those。

 but just the same thing。Is。The samples per second。Times the bikes per sample。 Oh， divided。 Yeah。

 divided by the refresh rate。 let's say it's one over。1 over 60。Let's try to hardco that。

Stop doing like the DT。Let's try doing that。

![](img/7a07006fd44b8dede9f835fb4c96181a_400.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_401.png)

So that fixed it。是。What is our frame rate， Let， Let's see now that we do have that。W too。So show it。

Let's do a print。F 32。来CT。

![](img/7a07006fd44b8dede9f835fb4c96181a_403.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_404.png)

Yeah， it's really， really fast our frame rate right now。So I'm not going to complain about that。

 and we are going to do the audio fixed frame。So。This part of the code。

Which apparently where the problem was。This part that code。

It's where we're going to not do be like this。We want to do like a fixed minimum sleep period and be better。



![](img/7a07006fd44b8dede9f835fb4c96181a_406.png)

But I think。

![](img/7a07006fd44b8dede9f835fb4c96181a_408.png)

Sounds like a nice loop， I'm going to put it for you guys to here。Is that reasonable？看一头。



![](img/7a07006fd44b8dede9f835fb4c96181a_410.png)

Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_412.png)

Okay， now that this is apparently working。All we have to do is now instead of doing， okay。

 so apparently we're done for the library use。给。😊，Which is awesome。

Now it's all up to us instead of doing like this。I'm gonna do， like。Position。And we're going to。

Get the test。Sound。Dot samples。At position。Plus one。Let we do position plus the question。



![](img/7a07006fd44b8dede9f835fb4c96181a_414.png)

Let's see。🎼どと。The。

![](img/7a07006fd44b8dede9f835fb4c96181a_416.png)

🎼，It may be some other thing。But I can hear a faint jump。Hm。

I'm going to try to put my headsets on to see if I can hear that jump as you did。Because well。

To be honest。This is a square wave， whichs not a very nice wave。

So you probably should hear like a strange。Square wave pattern， so it shouldn't be like a sine wave。

 which is perfect。So maybe that's what you're hearing。



![](img/7a07006fd44b8dede9f835fb4c96181a_418.png)

But okay， so we crash， but that's no just because the。I give position。It's greater than。Test sound。

s count。すすよ。Yeah， in fact， I'm going to go back and listen to。嗯。In to this guy。



![](img/7a07006fd44b8dede9f835fb4c96181a_420.png)

Just so we can check out together。If there is a faint jump。I know， I don't know， man。



![](img/7a07006fd44b8dede9f835fb4c96181a_422.png)

That looks a perfect square wave to me。Which is。That that doesn't look like a square。

 that sounds like a square way， you guys should say， okay。

 let's go back and now we should listen to our music。



![](img/7a07006fd44b8dede9f835fb4c96181a_424.png)

Which we managed to implement already。Let's do this。



![](img/7a07006fd44b8dede9f835fb4c96181a_426.png)

Okay。

![](img/7a07006fd44b8dede9f835fb4c96181a_428.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_429.png)

🎼，🎼，🎼，🎼，🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_431.png)

It also looks perfectly。So。Now it's really where they're funding it。So like do。Our mixer。

Now we're going to start implementing our mixer。Oh， that was， that was cool。

 We managed to get that out of the way。😊，And I are going to implement。Our mixer guy。

 and basically now we can play a lot of sounds together， maybe we can sing sounds and pan the audio。

 all crazy stuff like that。That's going to be fun， I'm going to quickly go to the bathroom。And like。

So quick to。Break。😊，When I come back， I'm going to go all crazy now with the system that really spans like two hours to create。

Like this basic system of playing audio files should be what we need to go all in。In Arab mix here。

 it's going to be awesome。几。😊，Two minutes。と。Okay。I think that was less than two minutes。

Which is even better。 So let's start doing our mixer。 First thing we're going to do。

For a mixer is to separate the idea of a loaded sound and a plain sound because if you load like a I don't know。

Block destroyed sound。We want to be able to play that multiple times。

 maybe one on top of the other without having to load that unable。So what I'm going to do is to do a。

P sound。And this guy， first of all， going to have a pointer。这个楼的枪。And a position。

It may be like a loopy。Then I'm going to have like。And。And volumeole。Then I add a lot of stuff here。

For now， that's just add these two guys。Okay。😊，And then。We're gonna have like， a plane。Sundry。

On the stack， let's say we have like 32 sounds max。At the same time， then just like the next。欢迎。香。

Okay， and now we're going to do a like meeting turnout。Play sound， play sound。And we should take。

A pointer to a loaded sound。Maybe that's it for now。呃。Plame sound。Result and vehicle to the plane。

Sounds。Plus， the next sound play， next play sound。And if the next plain sound is squared2 or equal to the array count。

Glay sounds。Then。I'm going to turn my mic down， but I think maybec cliping just of touch， okay。

And if the guy is created in the raid， then I reset him。Okay， now the result。

That sound is going to be。I think I'm just going to。Yeah， I don't know。

Result of sound will be a sound。These are that positions would be zero。Reizz Loki。で。Perhaps that is。

Yeah。😊，Okay。Play sound。Result。Arrow。The oldarrow versus。Theter results。Nice。Okay， now。At this point。

 for every。Sample。We are going to go。マイ？啊。Call that sound。Equals planes。Yes。And then if sounds。

 let's just。And if sound。It's different than the plane sound。Plus， here。Cot playing sounds。So plus。

 plus。We should also have like an active。Okay so if。This sounds not active。あ恭系。Okay。Now有。嗯。

If the sound is active。ItBa one and。Let I do like a。来 sample后。And the right sample。Okay， so left。0多。

And these guys are do like the left sample plus equals。 That's the basic mixing thing。So。Sound。

Samples。At the position。Right。At the， yeah。Would you like。不自信。Okay， now if the sound position。

Is greater or equal than the。Sample account。Okay， either we should look。In this case。

 I set that position。Back to zero。Or always， yeah， or。We shouldn't loop， in this case。

 I just said the active to false to false。So。And you know what？This is kind of wrong。I should really。

 yeah。This is wrong because let's say the beginning of the game。We go through。And play like。

 I don't know， five tracks。嗯。うん。And so this is what we're going to do。

 we're going to get the next thing sound。And if it's a looping sound。嗯。I don't know。Let's do， like a。

I could do a free list。Fort sounds。Well， we should actually ever hit 32 sounds。And you know， I think。

 yeah， instead of doing this。Actually， just。Not。They an nice plain sound。

If we have more than 32 active play sounds。Yeah but I still need to。Yeah。呢。This is kind of ugly。

I' going to hard code。A呀。Let's see。Safe sounds。先。😊，Let's say， I don't know。这1 of them safe。

Safe sounds are the。First。Well。I don't know， I think you guys are understand seeing the problem right problem is。

If we play the music， but we have like at some moment a lot of craziness going on。

 we shouldn't actually stop， we shouldn't actually get the music。And。Go back。So you know what？

Maybe I'm just going to loop through all this the inactive sounds。

Or the active sounds that don't have。Yes。Good evening， period the 3D。

We are implementing sound to our game and we managed to do that quite successfully even。

Let'll be sure you guys。Okay， yeah， we just broke the sound。But we're going to make a better naturer。



![](img/7a07006fd44b8dede9f835fb4c96181a_433.png)

And I think I'm going to care。About this for now and maybe。Maybe I should assert。And're like。

completelete。Do something。です。Yeah。Okay。So now we go through all the play soundss， yeah。

 this looks perfect， I think。Now， in the game。When do we load the sound？

Now I should actually play the sound。And we're going to set the look into true。Play sound undefined。

Okay。Yeah， this kind of sucks。Well， no I think I can just， I can just。Make the game match the audio。

I don't think they audio use the game， yeah， it doesn't。Test， it does use the test sound。嗯。Well。

Not sure this is a good solution。But let's just get text the test down。



![](img/7a07006fd44b8dede9f835fb4c96181a_435.png)

Okay。😊，Now。I'm going to keep my earphones on and'm going to keep audio for you guys as well。

Because now we shouldn't。We should have like weird sounds， we should have nice， nice sounds going on。



![](img/7a07006fd44b8dede9f835fb4c96181a_437.png)

Give you guys little bit sound。

![](img/7a07006fd44b8dede9f835fb4c96181a_439.png)

Oh， I don't hear anything。

![](img/7a07006fd44b8dede9f835fb4c96181a_441.png)

嗯。Let's go to play sound。

![](img/7a07006fd44b8dede9f835fb4c96181a_443.png)

好。s， yeah， I don't I did call play sound。

![](img/7a07006fd44b8dede9f835fb4c96181a_445.png)

没。let屎。

![](img/7a07006fd44b8dede9f835fb4c96181a_447.png)

然后。Iind it hard to debug you if we are optimized。

![](img/7a07006fd44b8dede9f835fb4c96181a_449.png)

Okay。So。You load this guy and you' had it play sound。Yeah， the result。Its  zero。



![](img/7a07006fd44b8dede9f835fb4c96181a_451.png)

Oh。Okay， I found a problem， but not B problem。

![](img/7a07006fd44b8dede9f835fb4c96181a_453.png)

Forge to implementcrement the next。But let's， let's see。Now the results sound as thisgu。Looking good。

And the result position is zero and looping is true O。



![](img/7a07006fd44b8dede9f835fb4c96181a_455.png)

Now， we added the active system， but didn't set。Okay。😊。



![](img/7a07006fd44b8dede9f835fb4c96181a_457.png)

F。Let see， that's here， actually。Okay。🎼，🎼あ。🎼，🎼，🎼Yeah。



![](img/7a07006fd44b8dede9f835fb4c96181a_459.png)

And。🎼，This song is not actually this game song， that was my other game song。

You guys can check out on HIO it this song。

![](img/7a07006fd44b8dede9f835fb4c96181a_461.png)

I think I'm going to make a nicer one for this game。I'm getting better at it。

So now what we should be able to do。Is play more than one sound。

Let me just copy from the other directory。Hello， man， how are you doing。How are you doing。

 We're adding sound， Let me just keep the sound going on。



![](img/7a07006fd44b8dede9f835fb4c96181a_463.png)

🎼，W I get the other music？Because that was a nice victory for today and we're not done yet。

 still going to do a lot of cool audio things like a panny。And changing the bitch， things like that。

 so data， well， the tour off using。🎼，It was a nice melody one。And I like this one。

So let's go back to the breakout data。Just to test。🎼，Okay， breakout， yeah。

 I think this game is getting really cool started out as a breakout clone pretty much。



![](img/7a07006fd44b8dede9f835fb4c96181a_465.png)

Like this。IPro saw that a thousand times Can you guys hear me with？

So you guys probably saw that a thousand times， right， this breakout kind of game。

And then we added like。🎼Some cool powerups on this level。🎼そ let你 see群人。Duealed with audio。

 this it going to be。So much nicer。Yeah， so that was like the invincibility power up。

That's like three shots per up。🎼いや。So I don't know if you guys could hear that we missed our frame rate for our frame with of the particles since this is not the optimized build。

And the audio glitch just for a quick second。That's what we're going to avoid nextstream when we do。

🎼We going do like。Multi 3 for the audio system。🎼おナイ。🎼い、。But this is the cool thing of the game。

 my opinion， we have。啊。We have like breakout pond。So we kind of like， well。The position is not。🎼Pect。

So it's kind of hard or impossible to get the ball behind you。I have to debug that radar on。Okay。

 and then。We have breakout spa majors。This one's pretty cool。🎼Yeah。

 especially when we get like the power ups。Yeah， look at that。Awesome or what？

And the idea for the game is to make。Uh， like a lot of old arcade games as if all of them were breakout。

 so we're going to do like u breakout Tes， breakout donkey Kongong， breakout， I don't know。

Whichever ones we can think of。And kind of a decently implement， we're going to do them。



![](img/7a07006fd44b8dede9f835fb4c96181a_467.png)

Yeah， I'm really excited to add side effects， side effects are going to be really cool。

 maybe're going to do that today。😊。

![](img/7a07006fd44b8dede9f835fb4c96181a_469.png)

诶 ok 。Let's try implement now the test。啊。Our audio test sounds too。What are using for the graphics。

 we built this entire engine M game from scratch。So we're not using anything for the graphics other than what we wrote ourselves。

 so now we open GL node direct X novo。This is our。This is our rendering。Sa。😊。

So we wrote everything ourselves。So yeah， we convert that to pixels and we fill the pixel。

We alert the colors for alpha blending。We do like rotate， yeah， we did with it bitmaps last stream。

Those were awesome lestream was awesome and then we did rotated rectangles before that so the particles can be rotated。

 we did like some me multiplication， thing like that that't a bit tricky。

So if you want to check out the whole process。

![](img/7a07006fd44b8dede9f835fb4c96181a_471.png)

Everything is on YouTube， you can go to YouTubebe。com sDanza Dan。

And you can see the making a game see from scratch。It's literally from scratch。

 it started out with like a blank file and nothing， no libraries not not。Well。

 we did use the library for the PNG guys so。But we could not use P and G。

 but we're not going to use P andng in the long run。 Well。

 we're kind of getting there really quickly。 So you can see the whole process from every stream all the way to this episode。

 So this episode right now is absolutely 11。😊，So we did a math last time。

 we think we did like 20 like 30， 28 hours of programming， 30 hours of stream。



![](img/7a07006fd44b8dede9f835fb4c96181a_473.png)

So in 30 hours， we're doing this。From scratch。We did all sort see so the BMs was the last thing we did onmi now it's audio right。

 but we did like particle systems and all sorts of crazy stuff for the game and re'finishing an engine pass。

In which we're creating light。🎼Audio and motor thread， things like that。😊。

And when we finish that engine pass， we're going to go back to the gameplay and add all the games that we want to add like Tes and Dunkey Kong。

 maybe Super Mario， I don't know， you guys can have a lot of ideas。That's well。Damn。

 I couldn't do that myself， I love my library right。If you love them， that's cool。

 but it's also nice to learn about how they work。So maybe you'll love them even more or maybe stop loving them。

 I don't know。🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_475.png)

It'retty cool。 You have to play the game sometimes because reminds me， oh， and it's also open source。

 you can go to HIO and download the game source code for free。



![](img/7a07006fd44b8dede9f835fb4c96181a_477.png)

Through the whole processor， you can go all the way from the first。

The first day which we did like basic injury all the way。

 basically the particle systems and all this stuff， the gameplay all the way to last time around。



![](img/7a07006fd44b8dede9f835fb4c96181a_479.png)

Cool， so let's test if we can play two sounds at once。Test sound。Then we yet。

Audio text sound too I don't like。I need to do this guy here oh。Actually。

 we don't need to do it this guy。Here。I don't know why I complain about this。YeahYeah。

 I don't think we need it。See test sound and test sound to。Oh， this is wrong。This is like old stuff。

Yeah， I forgot delete。 That's why it was on。 Now I have a pretty nice structure for the game。

 I'm working on a 3D engine， so I couldn't do stuff from scratch would be held without， yeah。😊，Yeah。

 well， if it's a 3D engine， that's really a lot more complicated。



![](img/7a07006fd44b8dede9f835fb4c96181a_481.png)

And both terms of performance， because this is a very simple game， graphics wise， we can do that on。



![](img/7a07006fd44b8dede9f835fb4c96181a_483.png)

🎼まです。Dude， that already worked。Can you guys hear like the other music thing？Like the melody。🎼だざそ。

Yeah， so3 the games are a different kind of beast。I wouldn't do them without doing OPGL at least。🎼バラ。

Yeah， this one's fun to learn。What those are under to here？



![](img/7a07006fd44b8dede9f835fb4c96181a_485.png)

Awesome， so we are， we are。Playing multiple sounds。So let's go back to our list。Do our mixer。

 So play several audio files。 Now， let's do penning。 Panning should be really， really， really。

 really easy。 If you guys can see what I'm doing， right。😊，Because we have。Like， let's do。Pen。

 which goes from one。 That's we goes from 0 to -1。And goes zero times one。 And then here。

 all we need to do。Yeah。From the left sample。Is to multiply this guy。By the sound pan。Well。

 the left sound， if it's minus-1 should be 100% on the left。I know what？I'm environment tech artist。

 so I actually have no idea what's happening， I program。

 I have no idea what's happening they're not alone。🎼It's cool though， thanks， yeah。

 yeah we've been doing that for a few hours so it's kind of hard to get the train going on but I think if you go to the very first。

😊。

![](img/7a07006fd44b8dede9f835fb4c96181a_487.png)

Stream， I think you'll be able to follow along pretty nicely， probably if that's your thing。

If you want to learn more about doing things from scratch。🎼イメージ simple game。



![](img/7a07006fd44b8dede9f835fb4c96181a_489.png)

But thanks， glad to see you guys think this is cool。I'm going to do like a。A separated like left。あ。

想太多。And this is来 some0。We going do the same thing for the right。Then when I play around。With the pan。

So the thing is the left sound sample should be on the left channel。啊个。The panny so。The penny。

 if penny is zero。If pen minus1 should be one， so it's going to be like。Actually。

 watch the first stream。 dude That's awesome。 It's nice。 see the chart person。 Yeah。

 definitely because I'm coming late hard to understand that goes for programming stream。 Yeah。

 that is true。 although today we did like another system from scratch。

 we started audio from scratch today。 So if you happen't watched the previous stream today was a pretty from scratch stream。

😊，As was yesterday， I think。he did a lot of stuff yesterday and it was crazy。Yeah， okay。



![](img/7a07006fd44b8dede9f835fb4c96181a_491.png)

So this is the math part that I'm not too familiar with。 our pen goes from minus-1 to one。Okay。

 that's variable right here。We are multiplying that by the left hand， so we want。If it's minus1。R 1。

 we want that to be one。So all I'm going to do is add。2。

We're going to evert that it's going to be one minus。



![](img/7a07006fd44b8dede9f835fb4c96181a_493.png)

1，- -1。Yeah。😊，So it should be one minus。Seems like you should have a lot more views， just Cstr。Yeah。

 I mean， I just started that like。Two weeks ago。And I did like no streaming beforehand before that。

Maybe the views will come in time， yeah and this is just pure seat。

Maybe next projects I'll do C plus+， I think people like that more because that's the UC standard。

 but since this is just small game for fun。诶。

![](img/7a07006fd44b8dede9f835fb4c96181a_495.png)

See seeing it is more fun thing， so I think that works so。One minus minus1。



![](img/7a07006fd44b8dede9f835fb4c96181a_497.png)

It's one plus one， so it's two。So you's probably clamp that。0。And if you are zero。

1 minus zero is still0， okay， so that looks good。And for the right channel。Right。Sweet。

 no more questions for me。 I'll just enjoy the stream。 too， if I ask question， that's okay。

 That's cool。 Yeah， I'm learning C in school， but I hate say that I suppose thats our almost failed course because I didn't want to learn C。

😊，Yeah， I mean。If you do all sorts of crazy stuff with a C++ language features。

You're going to miss that and see a lot。But that's not my thing。 When I use C plus plus， I was like。

Not not too much crazy features， although。I do miss like。Default arguments。

For that's the main feature that I wish C had different arguments。Because no。

 there's a place south thing， it's going to got crazy， we're going to pass the hamm here。Well， see。

 as thing I don't want to pass the pen here， I think I'm not going to pass the pen here and' going to let the guy receive the sound and then change the pen because see。

 otherwise this guy going to take like a thousand arguments， that's no good。So。South pan。Plus one。

Cllant from zero to one。I've seen C there， I have no idea。What do you mean？C。

 is pretty much like C plus plus。Except it's easier to read， in my opinion。It's easier to see。

What's going on？In terms of like a code， because there are not that many features。就。Yeah， I mean。

 if you know C++， you should be able to do something to see。I mean， yeah。

 unfortunately do like all sorts of crazy stuff with the S。SDD libraries。Thenen you should， I mean。

 if you lose like a defect for everything like。Things like that。Fan you can't do that see。

 you should be able to do your own。Like。S 16 or the at。You turn up for， yeah。

 I have no idea where those three are。So。呃。I did in the beginning of the stream。

 I have to have some types。 So S 16 is a signed。16 bit energy。

So that's just easier to type than like long。That's a short time actually。Li不 to do that short。

So that's what they。This guy is。And the at。This guy， well， Ed is a pointer。To an S 16。

So doing this means like doing this guy， which I'm assigning this guy to the variable where at is pointing at。

 and then I'm incrementing the value of at。So。Yeah， so that's more like pointer craziness。

Puzzled them。 I like what I like about see that' sort simple compared to most noise is exactly。

 that's the thing。😊，呃。没有。LetYou go back。C is not。But we can get some pretty complicated things in the。

You C， but puzzle depth is right， I think it's simple， I mean。

 there are fewer elements that you can play around with and the cool thing about C is that what you build。

Using those simple elements are what makes the program interesting。

 not exactly like doing other kinds of crazy stuff。

 although people sometimes do with meta programming， it crazy stuff and C。

I have done some crazy stuff， but。Like weird really crazy stuff， but yeah， for this game。

 thiss a smaller game going do one separate。Maybe next day， I'm going to do C++。



![](img/7a07006fd44b8dede9f835fb4c96181a_499.png)

Not sure， so let's see if we still have the same。We do。



![](img/7a07006fd44b8dede9f835fb4c96181a_501.png)

Sounds perfect Now what I should be able to do in the game。I should do like。

Bnk sound S should I should be able to do。S， can。

![](img/7a07006fd44b8dede9f835fb4c96181a_503.png)

Let's do it minus one。Let's see if were only can to hear that on the left of you。



![](img/7a07006fd44b8dede9f835fb4c96181a_505.png)

And we only hear that on the last year。

![](img/7a07006fd44b8dede9f835fb4c96181a_507.png)

大家咋死？And let's do that on the right of you。

![](img/7a07006fd44b8dede9f835fb4c96181a_509.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_510.png)

See， that's the good thing about writing things from scratch or at least having a good understanding of how things work。

 even if I were using like a full mix library。That it makes things easier to expand and understand and do things like that。

 that was pretty cool so if we did a pan。Actually， I have an uncertainty about the pan。

Should I also add to the left channel？The right channel pan。

Like if I've been all the way to minus one。Should I just exclude the left channel like I'm doing now？

Okay， include that。Other other year。海马 sure。And just were fun。When do we do like？Player P。A you。

Deigned to be。Let's do like。でか。嗯。W is divided by4。Yes。Yeah， that's just for fun' going to do like。

C sound later on the desk just to get started。Decoration of S。That's still late。



![](img/7a07006fd44b8dede9f835fb4c96181a_512.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_513.png)

Isn't that？🎼Really。🎼Really cool。And actually you should do like a listener kind of thing。



![](img/7a07006fd44b8dede9f835fb4c96181a_515.png)

Or the audio system。Like make the player the bass listener or everything from the laugh of him。

Yeah I can do that later on so yeah， I think I'm going to do the I'm going to add the other guys in the pan as well。

 so the left。Sample is going to be。This guy， which is。The left sound。The left ear。

 right clamped by the。This guy， and then I'm going to do the right one also clampify this guy。So。



![](img/7a07006fd44b8dede9f835fb4c96181a_517.png)

嗯。You think about this for a second。If it's zero。We should have left and right。If it's one。

 we should have nothing。Left and right。

![](img/7a07006fd44b8dede9f835fb4c96181a_519.png)

Yeah， so I'm going I have to add something else here。And which probably optimize this later。

This is like。Goodty crazy。

![](img/7a07006fd44b8dede9f835fb4c96181a_521.png)

So。Let's see。So we go from zero to one， we take the lab， so no need to。



![](img/7a07006fd44b8dede9f835fb4c96181a_523.png)

Do this。Just plan。And then we take。The right， oh， I'm doing the other way round。



![](img/7a07006fd44b8dede9f835fb4c96181a_525.png)

I here， so I'm taking the left。

![](img/7a07006fd44b8dede9f835fb4c96181a_527.png)

Adddie。From 0。出玩 ok k。And this guy should be。ShouldB。Minus one， yeah。知道。



![](img/7a07006fd44b8dede9f835fb4c96181a_529.png)

Yeah， that's better。If that's not super， super cool。



![](img/7a07006fd44b8dede9f835fb4c96181a_531.png)

I don't know what it is。I don't know what is， so。We can out pan the audio。

Let's change the pitch for the audio and we could also like after the effect like to make。The player。

 he。The listener。去 do。嗯。To do。

![](img/7a07006fd44b8dede9f835fb4c96181a_533.png)

Okay， let's change the pitch and the idea of the pitch is really simple So how how is the pitch controlled Well。

 if you have like a big wave。That's a very。Basy kind of sound。 if you have like a。Very frequent wave。

 that's a high pitch sal。If we have this wave and we want to make it higher pitch。

And imagine we have like these samples。I'm going to do like the poor man version。

Then we can do like a better version first， Okay， so don't go like too crazy on me。

 So what I'm going to do is just skip every other guy。And so we're going to do like this guy。

And then we're going to do this guy， then we're going to do this guy， we're going to do this guy。

Instead of doing。

![](img/7a07006fd44b8dede9f835fb4c96181a_535.png)

Like this， if should be able to do it like this。And this is not like this is bad for a couple of reasons。

 first reason is that we're going to compress the sounds。



![](img/7a07006fd44b8dede9f835fb4c96181a_537.png)

Length， are're going to speed up the sound。So that's one problem。

But no one cares because I'm not going to do that for the music。

 not for like small sound effects for variation and a pretty cool sound stack that I think we're going to add。

 it's going to be awesome。Okay， so that's the first thing， the first problem。

 the second problem is we shouldn't actually blurrp between these guys to generate no points。



![](img/7a07006fd44b8dede9f835fb4c96181a_539.png)

I don't think we should you going to do that just because it'll sound okay for this kind of game。

But if you want to expand that， maybe you can learn so the basic idea is instead of just getting the sound sample like this。

Some position。Plus， plus。I'm going to make the sound position A F32。And they're going to add。

To the position。Let's see。Let's do， like。Sample of this。So。Posciition。

So nothing should of change right， so we're going to do sound。Position plus equals。Two times sound。

Let's call that。Speed multiplier。给。😊，gonna他 add。And here。It's a good multiplier。

 It's going to be one。Startment。Okay， maybe you should clamp that but。So。You off changing the pan。

Let's change the speed multiplied。And I'm just going to play one sound。Because。

Since I've going to also change the。The speed of the sound and the pitch。

This is probably going to sound weird because it's going to overlap the other sound now。



![](img/7a07006fd44b8dede9f835fb4c96181a_541.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_542.png)

If we nothing。Let's see。If。This was a problem。And in fact at this。

 instead still of setting to zero now that we are have a floating point which just。Do it like this。



![](img/7a07006fd44b8dede9f835fb4c96181a_544.png)

Because we we can have a little fraction。So。

![](img/7a07006fd44b8dede9f835fb4c96181a_546.png)

This is back normal now why couldn't I multiply that by the sounds bin multiplied should be one， oh。

 it's not one， it's zero。Yeah， because we said that to zero。So I think we'm going to do like。

I'm going from approximately minus1 to one。Then to add two， so。Now I go from zero。To2。

Now I' going go from one to two。I'm sorry。So this is a real common I'm going from minus1 to one。

If I add two， I'm going to go from one to three。Yeah。😊，And gonna。I'm going to add one。

So I go from zero to two。Then I'm going to add half。So add one on a hand。It should be okay。

 so I should go from like。

![](img/7a07006fd44b8dede9f835fb4c96181a_548.png)

Have。I don't know， let's see。

![](img/7a07006fd44b8dede9f835fb4c96181a_550.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_551.png)

Yeah， that wasn't the most pleasant thing ever。

![](img/7a07006fd44b8dede9f835fb4c96181a_553.png)

欢迎主国。是。

![](img/7a07006fd44b8dede9f835fb4c96181a_555.png)

うん。嗯。Well， let's just set that like。我不唱一。

![](img/7a07006fd44b8dede9f835fb4c96181a_557.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_558.png)

Yeah， that sounds pretty bad。Th are going to have to do the alert。



![](img/7a07006fd44b8dede9f835fb4c96181a_560.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_561.png)

Let's try getting a sine wave and that's one of the main uses I do for actually pretty much the only use I do for this kind of effect。

I have a sine wave。啊。Let me throw that on the。Breakout folder。I have a sign。Da da。叫WVT1。



![](img/7a07006fd44b8dede9f835fb4c96181a_563.png)

Okay。😊，And I can show you guys what it sounds like， or， it's just a sign。

And it's not looping properly。

![](img/7a07006fd44b8dede9f835fb4c96181a_565.png)

So I have to fix that。嗯。😊，If I do this guy likes。0。ち。嗯。Let's go back to the position as a。

And then a sample。自信？

![](img/7a07006fd44b8dede9f835fb4c96181a_567.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_568.png)

So we have another bug。Unless the sound is messed up。Yeah。



![](img/7a07006fd44b8dede9f835fb4c96181a_570.png)

So you start to fix that before trying to add no features。But。The basic idea is。

I want to be able to do something like this。Well， let's try to do。



![](img/7a07006fd44b8dede9f835fb4c96181a_572.png)

Yeah， this guy sounded okay。I guess。

![](img/7a07006fd44b8dede9f835fb4c96181a_574.png)

Well， I should didn't do anything。Yeah， two times the sky converted by n to be same thing。

Let's go faster， let's try going faster。

![](img/7a07006fd44b8dede9f835fb4c96181a_576.png)

So for the sine waves。

![](img/7a07006fd44b8dede9f835fb4c96181a_578.png)

It works pretty。Pretty nicely， Yeah， well I suppose it does because this is a this is a crazy hack we're doing。

But if the waves like this and we have enough samples， which we pretty much do。Then we do like。



![](img/7a07006fd44b8dede9f835fb4c96181a_580.png)

From this guy to this guy， from this guy to this guy。It's acceptable， let's try to like one。



![](img/7a07006fd44b8dede9f835fb4c96181a_582.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_583.png)

That's try。Yeah， so the 0。 。5 thing doesn't work。呃。You can just get a reference because。

I think I did the same thing the other game。And it worked。就。Psition。Yeah， weologist。Yeah。

 we do that differently， we just added this guy。just had a sound multiplier。

And then when we got the sample。Yeah。And when we got the sample here。We do， like。

Last sample is the position。Yes the position。Yeah， should probably notes that position I is not going to be。

It's going to be for sample。じ、 sample。Which that explains， I think， oh。

 I think that's going to explain a lot of things。Yeah。😊，So whatever okay， we have a pretty weird bug。

The bug we have now。In fact。Well。Yeah。😊，The bug we have now is that。

Since the position is being added twice per sample because it's going like for a channel。

We actually are only playing half of the sound。And we didn't notice that when to looked to the music because the music is like eight bars。

And they are pretty much repeated。所以。So when we played half of the music， it also looped。

 that's why we didn't hear， but the sign didn't， that's why we heard we heard the sound sign problem。

So I think this should work right off the bat just by making a position at F32。

And adding like one position。Per sample。But now this guy has to be a little bit different。

 so this guy is going to be the sound position for the left。Right。Yeah。

 and this guy's gonna be plus  one。 And I did this like channel count thing。But。

Every really doesn't matter。And I just do a casting here。So that was a funny plug。

 I know I did find a bit weird。I thought we didn't play the whole sound， but I thought okay。

 maybe I didn't export whole sound。But no I was wrong facts， let' can do a sample for。

So this would be the sample。And this will be。后客是吧？INo， I don't think this is entirely correct。Yeah。

 I do have to multiply that by the channel count。Yeah。Yeah， okay。



![](img/7a07006fd44b8dede9f835fb4c96181a_585.png)

So I think that's going to solve a couple problems， let's see。



![](img/7a07006fd44b8dede9f835fb4c96181a_587.png)

So that's solved the loop problem pretty much perfectly and if I go back to the game。

And play both sounds and go back to the test sound。T2。Then， we do play。来。



![](img/7a07006fd44b8dede9f835fb4c96181a_589.png)

Notice that the music is a little bit longer。There you have it。



![](img/7a07006fd44b8dede9f835fb4c96181a_591.png)

Perfect， now let's try messing around with the music。 so again。



![](img/7a07006fd44b8dede9f835fb4c96181a_593.png)

Nice。诶。

![](img/7a07006fd44b8dede9f835fb4c96181a_595.png)

Yeah， this is not the best。Pitch shifter， but it's not。



![](img/7a07006fd44b8dede9f835fb4c96181a_597.png)

For this game。Try clean them both and go crazy。

![](img/7a07006fd44b8dede9f835fb4c96181a_599.png)

Okay， now we can start having some fun。Okay。😊，Can I start having some fun out？

Well I'd be having fun because today's been a great day， but。😊，I'm going to。Read。

 I going to start having more fun。 So I have that the sound。Okay啊。等一下。Remove this guy。

And then we do like loaded sounds， let's do。Let's do music。And let's do sign。Okay。

So music is going to be this guy。And we're going to do light。啊，没事。And then play。

And now I'm going to try to play restrict。Or let's do like player movements， sound movements。

And I'm going to add that。The sine wave， science。上。That just sounds。Now。Player movement sound。

 We don't have such things as play movement sound。 So let's add a player。系有。Let's go。

 where's the play？She was a player， I don't know。Pers step， players step。Go to add a plain sound。

Also， we don't have play sounds here。Player movement。And this guy， well。

 I don't remember we charge we chose this。

![](img/7a07006fd44b8dede9f835fb4c96181a_601.png)

ok。😊，And okay， so。

![](img/7a07006fd44b8dede9f835fb4c96181a_603.png)

We didn't load。S sign。たんです。Let's remove， yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_605.png)

嗯。😊，So。We got an invalided sample。 So because the sound。Sound count is 4，4，1。

 which is like one second and we sample to 45。Okay， because this is wrong now。



![](img/7a07006fd44b8dede9f835fb4c96181a_607.png)

If the position。Times。The sound channel count。Swe。

![](img/7a07006fd44b8dede9f835fb4c96181a_609.png)

Sound。想。Okay。That's still not right。

![](img/7a07006fd44b8dede9f835fb4c96181a_611.png)

是。Now， this was right， but for some reason。嗯。

![](img/7a07006fd44b8dede9f835fb4c96181a_613.png)

I don't know。Yeah。I'm pretty sure we should have stopped here。Yeah， we fetch that。

Let's do like this guy times to just to see。Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_615.png)

Sound。Sample position。So this is correct。

![](img/7a07006fd44b8dede9f835fb4c96181a_617.png)

Oh， okay。

![](img/7a07006fd44b8dede9f835fb4c96181a_619.png)

Well， no， I thought I had problem。I don't know。嗯。

![](img/7a07006fd44b8dede9f835fb4c96181a_621.png)

I see we are trying to fetch the samples at this sample。If we have these now， oh， we are mono。



![](img/7a07006fd44b8dede9f835fb4c96181a_623.png)

そうそうそんうん。Okay。So let's support mono so we can't do this。Have to do like plus。Sound， sound。钱了。

Co to minus-1。Yes。And this guy's too。Yeah， and this also should be like chunk。Okay， this sounds okay。



![](img/7a07006fd44b8dede9f835fb4c96181a_625.png)

And this sounds okay。Yeah。🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_627.png)

🎼Yeah。🎼，🎼Now。Hear that sound。

![](img/7a07006fd44b8dede9f835fb4c96181a_629.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_630.png)

And let's make that sound。Awesome。Okay。😊，Step 1。That sound will only。The oh。

 we don't have a fighting。 That's first of a flag。So first I doing that song， awesome。

Let's expand our。啊。Let's clear this up。So lets say two steps， that's implemented volume and it's。

Make this guy。Because maybe。I should make all these guys as a flowty。So。These guys。And then。Loat。

If float。And probably going to do the additioning flow test well。是。诶。Yeah。

 I can remove this parentheses here。This guy？仔7。Okay。Okay。So it probably didn't change anything。

Now we should be able to。Do。Time sound writing。And let's just see if we can optimize it some way。

We're multiplying。The left sample。 each one of these guys are is unique。 Oh， but the sound pan。Yeah。

 we could not make the。Camp every。Sample， let's try to do that， so。Oh。

But we are inside everything saying， okay， well， let's not worry about。Now the the。Vual。

 the default volume should be one。Let's see if we are back on。So first step。

 make our audio mix or engine and support what we want to do， second step。In our player desire。

 let's see。Desire。哦。Player。Desired P。Let set the target fee finally。

you know start rendering the player as we could do。Let's do it。明点。When the player。Movements sound。

120。So we only want volume if the player Dp。Has stuff。Now this didn't get loud。

 so I'm going to multiply that right。

![](img/7a07006fd44b8dede9f835fb4c96181a_632.png)

This guy。And let's try it slow。🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_634.png)

🎼，🎼Yeah。So it's got be good， I think guys got the idea， but this is pretty wrong for some reason。

This guy is if this bed is not smooth。Which maybe it isn't。Maybe we are。

And you have to smooth the volume by hand。嗯。Let's make it a little bit less intense。

And let's just try and set the volume to like half， just to see。



![](img/7a07006fd44b8dede9f835fb4c96181a_636.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_637.png)

But the problem is this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_639.png)

🎼Yeah， it it's really all over the place。😊，🎼。🎼，🎼Yeah。Yeah。🎼，🎼，🎼。🎼Yeah。🎼。



![](img/7a07006fd44b8dede9f835fb4c96181a_641.png)

Ouch。Sorry for that was too loud for you guys， that was too last for me as well。

So it's probably we clamped this guy。It's clamp can like。Thank个。clam。So， yeah， sub functions。



![](img/7a07006fd44b8dede9f835fb4c96181a_643.png)

🎼Yeah。🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_645.png)

🎼，I should really get the absolute of this。

![](img/7a07006fd44b8dede9f835fb4c96181a_647.png)

🎼Yeah。🎼Yeah。🎼，🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_649.png)

What if you get this the player？

![](img/7a07006fd44b8dede9f835fb4c96181a_651.png)

We have the player visual deeper。Straight that。

![](img/7a07006fd44b8dede9f835fb4c96181a_653.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_654.png)

🎼，Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_656.png)

I think I'm going to have to add my own。I think for the。I the deep be so unpredictable？

Because the mouse goes all over the place。嗯。Do you have other player DP stuff？See targeted P。

 targeted P have size， P D P。So I'm going to add。I'm gonna add the。A player。Movement， sound volume。

Yes。嗯。😊，So yeah， it's kind of sucks。 So I'm going to do like he。Player movement， sound。我点。滴滴。

They do the same。Sa smoothing thing we did。Well， it should be a easier smoothing function。

Because I've been doing like the。Just before we actually commit to doing that。



![](img/7a07006fd44b8dede9f835fb4c96181a_658.png)

Let's just see why the visual be。🎼So。

![](img/7a07006fd44b8dede9f835fb4c96181a_660.png)

The New shouldn't be that weird。It's decreasing quite nicely。Other here， it increases dramatically。



![](img/7a07006fd44b8dede9f835fb4c96181a_662.png)

Yeahや。Oh。Okay， because we actually should。Shouldt set。The DP directly to the volume。

You should make like a volume。Plus， yeah。Okay， so let's clamp。That。Like us do minus one and1。Yeah。

 so。I'm going to add。They campamped。Volume times the。呃。



![](img/7a07006fd44b8dede9f835fb4c96181a_664.png)

🎼いです。

![](img/7a07006fd44b8dede9f835fb4c96181a_666.png)

🎼Yeah。Okay。Now。This should be 0。啊，好。

![](img/7a07006fd44b8dede9f835fb4c96181a_668.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_669.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_670.png)

Now， I really want to set that to the。確か。That's what I want to do， really。

So it startss out zero and let's say go totally。啊，没有。



![](img/7a07006fd44b8dede9f835fb4c96181a_672.png)

Yeah， let's do the。🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_674.png)

You are the variable thing。

![](img/7a07006fd44b8dede9f835fb4c96181a_676.png)

🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_678.png)

Okay， so。I'm going to do the player。Movement sound。第。Which is the doubtta right？

I'm going to do the D D， so。I'm accelerating。Towards。This guy。

And I can clear around the values later。And then， my。Velocity。I this guy。

I'm also going to highlight like friction force for the sound。I don't know this's kind of hacky。

唱一下第七。Yeah。Not sure and a player。Oh this final guy。It's going to be。S。Very啊。Let's do。Eself。

我们上 volume。Plus， play movement sound。不尿。Yeah， D change D T。Plus， the滴D。Time D T squared。站起。

Movement sound fun。I convert from int。嗯。哦。ok。啊。

![](img/7a07006fd44b8dede9f835fb4c96181a_680.png)

Okay， now let's see。

![](img/7a07006fd44b8dede9f835fb4c96181a_682.png)

🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_684.png)

🎼Yeah。we have a positive acceleration yeah， but now that's1。



![](img/7a07006fd44b8dede9f835fb4c96181a_686.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_687.png)

Let's10。 Now this guy 20。 So gonna add a， a acceleration。That's gonna be。I'd say，40。Times。

Minus the velocity， which is。I want the velocity to go to zero。



![](img/7a07006fd44b8dede9f835fb4c96181a_689.png)

Well， if a lot， Yeah， I would say。

![](img/7a07006fd44b8dede9f835fb4c96181a_691.png)

I actually shouldn't be there。

![](img/7a07006fd44b8dede9f835fb4c96181a_693.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_694.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_695.png)

I'm going to add like。And they're going to start off with zero as well。



![](img/7a07006fd44b8dede9f835fb4c96181a_697.png)

嗯。

![](img/7a07006fd44b8dede9f835fb4c96181a_699.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_700.png)

Yeah。But's going be the visual。D P。I see。A。

![](img/7a07006fd44b8dede9f835fb4c96181a_702.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_703.png)

🎼，Maybe that was a big。🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_705.png)

I'm just going to start that player。はい。Set this guy。F。



![](img/7a07006fd44b8dede9f835fb4c96181a_707.png)

🎼Yeah。🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_709.png)

啊。

![](img/7a07006fd44b8dede9f835fb4c96181a_711.png)

This guy's。这是干。

![](img/7a07006fd44b8dede9f835fb4c96181a_713.png)

🎼Yeah。Okay， starting to be nice。🎼，🎼Yeah。🎼Yeah。🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_715.png)

It's not a very pure sound。啊。第一。😊。

![](img/7a07006fd44b8dede9f835fb4c96181a_717.png)

Think think you may have to think about that for a while。



![](img/7a07006fd44b8dede9f835fb4c96181a_719.png)

Because now we're doing is every time we move。We want to go faster， but we also。

Want to decrease the sound。

![](img/7a07006fd44b8dede9f835fb4c96181a_721.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_722.png)

Let's see。 our print。What we had。是。See， this job。Its a very bad。



![](img/7a07006fd44b8dede9f835fb4c96181a_724.png)

So， maybe。未必。I don't know if I clamp this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_726.png)

Yeah。You see that again。是。Yeah， because we do have some pretty crazy spikes。



![](img/7a07006fd44b8dede9f835fb4c96181a_728.png)

🎼Yeah。

![](img/7a07006fd44b8dede9f835fb4c96181a_730.png)

Let's change to the target。Dey。

![](img/7a07006fd44b8dede9f835fb4c96181a_732.png)

🎼Yeah。🎼Yeah。Yeah。🎼Yeah。🎼，🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_734.png)

🎼，It is a bit better。That's not 100%， so you know what I'm just going to do like move towards。Yeah。

 not the best。See。So the absolute of this guy。Clamped。By like 0。And three。This will be our target。好点。

这个镜头。Towards。This guy。😊，With the speed。下地铁。嗯。Yeah。So this is like the target。This is the。不道。

This slide。So if that is greater than target。Felll less than。Now is。Trgt。Al， let's say return。Return。

Pamp。Of if we are greater than a target。Surely surely go。Left， right， should really go negative。

So the clamp。Should be the target。Vll minus the speed。And the positive clamp。Okay。

And if you are less than a target， this would be the foul。Well， plus B。Target。

And him is going to return。Okay， now we're going to do a simple move towards this guy。

Moving towards this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_736.png)

。🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_738.png)

Now， if we increase the speed。I'm going turn off the music for a while。是。



![](img/7a07006fd44b8dede9f835fb4c96181a_740.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_741.png)

That was way too much。那自己 like plus。

![](img/7a07006fd44b8dede9f835fb4c96181a_743.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_744.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_745.png)

啊，O。I think I'm getting somewhere， but this is not 100% because there are like。

Why did I get this high。They start going downwards。It should really be like my speed。

Let's try to set。The volume D to this guy。And this guy is going to be。There。Like D。



![](img/7a07006fd44b8dede9f835fb4c96181a_747.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_748.png)

嗯。Okay， let's try to click this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_750.png)

Oh， this is， I thought that was going to be easy。

![](img/7a07006fd44b8dede9f835fb4c96181a_752.png)

Yes。I'm going to move this guy towards。I don't know。I don't know what kind of a math I have to do。

To kind of smooth this， this movement， so。Like the very stupid thing that I can do。Nice to。Like。😊。

Yeah， I think that's what I should have done。So。AndDDP。Which is basically just this map。Right。Okay。

Now the DP is going to have well。Kin of did that the friction。Let's go back to that state。

Kind of this guy。But I'm not going to get the absolute here。Okay。And let me go back。对。



![](img/7a07006fd44b8dede9f835fb4c96181a_754.png)

吓的人。Okay。

![](img/7a07006fd44b8dede9f835fb4c96181a_756.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_757.png)

嗯。Okay， let's take out。The control that。Let's take out the control that this guy has So what I'm going to do。

It's like if。This guy's positive。W to red like。Else。



![](img/7a07006fd44b8dede9f835fb4c96181a_759.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_760.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_761.png)

If you are moving to the right， or should make like。好。



![](img/7a07006fd44b8dede9f835fb4c96181a_763.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_764.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_765.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_766.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_767.png)

This is kind of a。Weird so get stuck for like long， long， long time。And if I don't manage to do that。

I may just call that a day we did pretty much everything to。

Then we maybe maybe do like threading next time。 and then we do like。

A day for just playing around with this kind of stuff。I know this was a victory today。

 but I really wanted to add this guy。Because the deep pe is really messed up and I did that in the other game that was really easy because the deep pe was already smoothed。

This D P is raw， I mean。Yeah。Well， you do have a mouse pe。Kind of like that。You you know what？

I think I just had a golden idea。はい。The volume。Will just be。拿所有。たです。



![](img/7a07006fd44b8dede9f835fb4c96181a_769.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_770.png)

Oh bad。

![](img/7a07006fd44b8dede9f835fb4c96181a_772.png)

Why is the Mil WorldDP so messed up？

![](img/7a07006fd44b8dede9f835fb4c96181a_774.png)

Let's try to get that。The actual。没有。

![](img/7a07006fd44b8dede9f835fb4c96181a_776.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_777.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_778.png)

Small number。Not that。

![](img/7a07006fd44b8dede9f835fb4c96181a_780.png)

So。I think I can say for sure。The problem is our mouse input is all over the place。Yes。

 since is not continuous。We have like six night。Like every frame have a different value。嗯。



![](img/7a07006fd44b8dede9f835fb4c96181a_782.png)

And what we want。So， yeah。Findund out about that problem。 so we can pretty much use the guide button。

The guy down there。现在。So the problem is。I let him take out this guy。



![](img/7a07006fd44b8dede9f835fb4c96181a_784.png)

So。

![](img/7a07006fd44b8dede9f835fb4c96181a_786.png)

We're going to get thismic oh oh， this sounds perfect。



![](img/7a07006fd44b8dede9f835fb4c96181a_788.png)

No。It does。

![](img/7a07006fd44b8dede9f835fb4c96181a_790.png)

这尾した。Right， so the problem is。We're going。Positive 100。If we are moving right， let's。Oh， yeah。

I didn't finish this。That's too like。It's less than。



![](img/7a07006fd44b8dede9f835fb4c96181a_792.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_793.png)

This is pretty decent。

![](img/7a07006fd44b8dede9f835fb4c96181a_795.png)

I mean， pretty decent。嗯。

![](img/7a07006fd44b8dede9f835fb4c96181a_797.png)

So if I were to change the position based on this。This would be like a frictionless。Space。

So that's version one， which is pretty bad。Now version two should be。The acceleration。



![](img/7a07006fd44b8dede9f835fb4c96181a_799.png)

This guy。Some reason our looks， not 100% anymore。

![](img/7a07006fd44b8dede9f835fb4c96181a_801.png)

Let see if it has to do without a flaw。

![](img/7a07006fd44b8dede9f835fb4c96181a_803.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_804.png)

不要。Sell like just something。

![](img/7a07006fd44b8dede9f835fb4c96181a_806.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_807.png)

So we fixed that。

![](img/7a07006fd44b8dede9f835fb4c96181a_809.png)

Okay， maybe I'm just tired now at this point。We did a long stream and we did a lot of stuff。嗯。P。

It's not 100%。

![](img/7a07006fd44b8dede9f835fb4c96181a_811.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_812.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_813.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_814.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_815.png)

Sangling back to。Position。

![](img/7a07006fd44b8dede9f835fb4c96181a_817.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_818.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_819.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_820.png)

Yeah。Plus， one。And you reach the sample count。If you are looping， you go back。Yeah。

 I know what we may actually just call it as a day。买好。

I don't like to read these things kind of solved。

![](img/7a07006fd44b8dede9f835fb4c96181a_822.png)

Very' a break point here。え。Our position is exactly。Right， and this should be 0。Again。



![](img/7a07006fd44b8dede9f835fb4c96181a_824.png)

Let's see if I set the pitch。Fire。

![](img/7a07006fd44b8dede9f835fb4c96181a_826.png)

To have。Forget like a less frequent， maybe just。Yeah， so it is the sound。



![](img/7a07006fd44b8dede9f835fb4c96181a_828.png)

Not the book。Suppose that's。嗯。Dude。

![](img/7a07006fd44b8dede9f835fb4c96181a_830.png)

I really don't know。I already don't know。I really don't know this looks pretty much perfect。

 Se that zero。Okay。And then next time around。Let me run like this guy。Be0。Times。

 what it's going to be。For a sample。Okay， why' is the volume that？Bs suppose doesn't matter。



![](img/7a07006fd44b8dede9f835fb4c96181a_832.png)

Is the volume of that。Do I not comment out of volume？啊。Now didn't come out。



![](img/7a07006fd44b8dede9f835fb4c96181a_834.png)

That's weird。再来 it。

![](img/7a07006fd44b8dede9f835fb4c96181a_836.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_837.png)

And let's take a step back through all this stuff。Let's do， like， volume。



![](img/7a07006fd44b8dede9f835fb4c96181a_839.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_840.png)

Let's try thinking。

![](img/7a07006fd44b8dede9f835fb4c96181a_842.png)

🎼，🎼，🎼，🎼，🎼，🎼，🎼Yeah。🎼The。🎼，🎼，🎼，🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_844.png)

🎼Yeah。So， we are only。Doing half the music again。Oh two we found out that problem。But。

We solve that problem already。 Maybe when we introduce something else here。

 let's see what we changed here。We went back and forth on this for a while。At the volume。Yeah。

 we re factored at this， but I don't know。Yeah， samples opposition times two。

So sound position starts out as being zero， zero times  zero。Then， we do。You个 one。

They do one times 2，2。Go，2 and 3。load two。Times two， four， four and five。And this。呃。

Times the channel count， right？ち。So， this guy。If you have one channel。Duplicate the same guy。

This looks correct。Time a sample count， which it also looks correct。Let's do， like。

Hard coat this guy， just check out this guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_846.png)

🎼，🎼，They well， why didn't we？Break。This guy。

![](img/7a07006fd44b8dede9f835fb4c96181a_848.png)

I'm very confused。Let's hear the test。🎼Yeah。🎼，🎼，🎼，🎼Yeah。🎼。🎼The。🎼。



![](img/7a07006fd44b8dede9f835fb4c96181a_850.png)

🎼，🎼，🎼Yeah。🎼，🎼，🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_852.png)

Okay， so we are correct。

![](img/7a07006fd44b8dede9f835fb4c96181a_854.png)

Now let's hear this time。

![](img/7a07006fd44b8dede9f835fb4c96181a_856.png)

I don't think youre。Never not。Dude， mom。

![](img/7a07006fd44b8dede9f835fb4c96181a_858.png)

Let me try debugging that。Breakpoint here and。Okay。Start off position is zero1 counts once。

 so we sample the zero gut。So the zero and0 plus。1-1， So 0 plus 0。Right and the left are the same。

Get the sample。Can we add one the position。And the position one， okay。Next MRI sample is one。

Maybe it's greater than the sample account。

![](img/7a07006fd44b8dede9f835fb4c96181a_860.png)

And we're missing once Sam。

![](img/7a07006fd44b8dede9f835fb4c96181a_862.png)

Sirle count。

![](img/7a07006fd44b8dede9f835fb4c96181a_864.png)

I did， they didn't crash。

![](img/7a07006fd44b8dede9f835fb4c96181a_866.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_867.png)

You should be。

![](img/7a07006fd44b8dede9f835fb4c96181a_869.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_870.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_871.png)

I think I'm going to sleep on that bug。Because that doesn't make any sense， you know what？Just。

Because we deep cheats。Two times today。Let's go ahead and see if there's anything weird going on。

 I mean， this no different。That well。Yes。Oh， and actually， here we do do a free list。Yeah。Okay。

 maybe we'll do a free list next time。Like the position。Physition type channel count。What we do here。

And this guys the position times the channel count。

Both you count minus1 the same thing we do here we。Add the position to the speed multiplier。

I don't know what could be wrong。Oh， I'm kind of sad now。Because it got to a great point， I me。

Let's go back to adding。This' music smart fund side。



![](img/7a07006fd44b8dede9f835fb4c96181a_873.png)

🎼，🎼Yeah。🎼，🎼，🎼So yeah。🎼That was really cool， we did a lot and I don't I don't hear any problems。

 maybem going to listen to that on my speakers。

![](img/7a07006fd44b8dede9f835fb4c96181a_875.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_876.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_877.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_878.png)

It sounds perfect。That's just one last time here， this guy assembly the speakers。



![](img/7a07006fd44b8dede9f835fb4c96181a_880.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_881.png)

So。

![](img/7a07006fd44b8dede9f835fb4c96181a_883.png)

We well， yeah， we changed the pitch。Even the side effects and make the player listening。ThePadding。

Let's also do， like， fix。Exign looking problem。Yeah。There呀。😊。

We only need a couple more things from the engine。

![](img/7a07006fd44b8dede9f835fb4c96181a_885.png)

And also， maybe I should collect like a couple of cotan effects so we can't implement them。

And then we'm going to feel a little bit better about the。



![](img/7a07006fd44b8dede9f835fb4c96181a_887.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_888.png)

![](img/7a07006fd44b8dede9f835fb4c96181a_889.png)

🎼The。🎼，🎼。

![](img/7a07006fd44b8dede9f835fb4c96181a_891.png)

🎼。Okay so I guess that's the part today， we did implement the South system。

 the audio did the whole thing， we implemented light use the library。

 and we did our own mixer that I can read files and deco code waves and we did all sorts of stuff today。

We're not 100% yet， we're getting there。啊。

![](img/7a07006fd44b8dede9f835fb4c96181a_893.png)

Okay， so if you enjoy the stream， you the whole you can watch the whole other streams。



![](img/7a07006fd44b8dede9f835fb4c96181a_895.png)

Where we created the game， started out with the blank file， did all the way to where we are now。

 we did like bits and audio， things like that。And。

![](img/7a07006fd44b8dede9f835fb4c96181a_897.png)

And you can watch the whole thing on YouTube， which is use。com sdandayd。

And then you can download the game on HIO， you can go to Danze DhDio， come here to click on the game。

And you can see not only like the full source code every day has its own source code。

 sorry in the first day that we been like the basics like a window and a ranger can download that source code and all source codes including I'm going to post like today's source code。

Along with the files。So hopefully you can learn along and also have fun。So that is for this stream。

 next stream， we're going to do thread， probably。And maybe it fixed this problem， not sure。Okay。

 so thank you all for watching and I hope to see you guys next time。



![](img/7a07006fd44b8dede9f835fb4c96181a_899.png)
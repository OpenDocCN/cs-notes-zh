# 【从零开始用C语言制作游戏】 p21 Making a game in C from scratch! Ep 21： -Asset System, Async Ogg Re -BV18i421a7DD_p21-

Hello everyone and welcome to this new live stream where we're recording the entire game in C from scratch we are almost done with the game I can see that we are on the final stretch to finish the game and so we can publish it and I got some good news I'm pretty sure I'm gonna to be able to release the game on steam。

😊，So， that's gonna be。A great plus。 And I think that's been a lot of fun as well。

 Both to learn itll be my first game。😊，With no engine on steam because the games I published on steam before I used done real and stuff。

 so it's going to be a new challenge， which I think is going to be fun to show you guys as much as I can。

If you are falling along and you can do so on my YouTube channel， which is YouTube。comdZDan。

 you can watch the whole process ever since from the first line of code we wrote on day one and now we are on day 21 so you can watch all the way to day 20 already on YouTube。

And。Hopefully it will be like 25 days， I think， I'm guessing， I'm going to show that to do list。

 there's not much stuff to do。There's just some cleanup to do and some engine improvements because last stream we finished the gameplay。

And we do all sorts of crazy stuff。Pretty much yeah。

 and on my YouTube channel you can also check out some tutorial series。

 I am creating this hot program a game C++ tutorial series。

And it's been really hard to edit because I really I really try to do something good quality。

 So yeah， it is taking a little bit time。 but if you subscribe。

 you can watch the whole thing and also there like these one off tutorials that you can。

Watch to go more in depth and understand this live streams better because these are a little bit more hardcore。

 Okay， then you can also download the game on HIo， which is Dand do o can open here to break arcade games out。

😊。

![](img/25984fe835474479d1617bc0acadfcd6_1.png)

![](img/25984fe835474479d1617bc0acadfcd6_2.png)

Soce code， and I'm also updated the page。 you can see there' is a lot of new。Gifts。Going on。

Or if they load anytime soon？And maybe it wasn't the best idea to put 100 gifts。Yeah。😊，Oh well。



![](img/25984fe835474479d1617bc0acadfcd6_4.png)

But you can download the source code in the download Now button。And you are welcome to give me a tip。

 but if you just click no thanks， you can download for free。



![](img/25984fe835474479d1617bc0acadfcd6_6.png)

All the gay Mens source code from the very first day。

 so you can watch and download the source code to make sure that everything is。Nice。

 if have you any questions， be sure to drop them on the comments or the chat or anywhere and I'll try to answer them。

Okay。😊。

![](img/25984fe835474479d1617bc0acadfcd6_8.png)

Okay， let's get started now let me just load the project。できるね。Coaller here Mr Pro。 hello。

 how are you doing， man。O。In order to do， what do we have to do， we only have like， I think。

Three or four major things to do one of them they want to tackle of today is to build a more robust asset system。

We're going to explain what it needs。And in a little bit and also some polish passs。

 some small things that we need to improve in the game。And then I have to integrate with the OSS。

 which means online subsystem， make sure that a game runs on steam and probably do achievements or a leaderboard。

 things like that so we have to implement that。And then it the game， I think that's the roadmap。

Just a couple things to do and there's a lot of other ideas that we had during these streams I'm not going to spend a whole bunch of time implementing every single idea on this game because I have to live stream the whole thing right and maybe I'm going to implement a couple of them offstream。

😊，So you guys can have a little of surprise when you play the game as well。

 that'll be quick think maybe some of these。Other game modes。

Who knows now we have to do the asset system so two things we noted to do in the system first thing is to do an OGG reader。

Because if you go to the game data folder。You can see。

That we have these wave files like and the music alone is 14。5 megabytes。

Which is a lot for a small gain。A lot of these hit files and they add up to be like four or five megabytes as well。

Yeah。😊，Because there is a ton of them。Okay， so。The great thing about adding a OGG reader is that we can I just converted these songs to OGG。

 so instead of taking like 7。2 nates of space， it take like 500 k。So it's a lot。

A huge difference doing compressed versus uncompressed。musicus。

And but there is a catch and the catch is， it does take time to uncompress them。However。

 we already implemented if you go back to my YouTube channel。

 you can watch you already implemented the parallel。



![](img/25984fe835474479d1617bc0acadfcd6_10.png)

Yeah， we did a job system for the game。And to watch this episode we can watch the whole thing。

 how we did the job system， so now we just have to use the job system。



![](img/25984fe835474479d1617bc0acadfcd6_12.png)

And I think that'll be pretty easy and after doing the OGG reader。

 we are probably going to cook all the assets into a single file， single pact。😊，File， well。

 a couple benefits to one of them is that it's going to be way more organized。

And to have all these PNG files。Spread all over here。And another benefit。

Is to be able to update the pack file independently from the game， which is also a plus。

Its also look more professional really to have all the assets code in ready to go and were also going to improve the performance quite a bit because we're going to read just one file and we could take this to the next level and do like memory mapping and all sorts of stuff for now just a simple asset cooker group do the job and it'll be a fun also to write that on stream to show guys you know how to specify file and things like that Okay As for the OGG reader just open here data so I have the OGG files that I convert it。

Just like we did the importer， the waving importer， I'm going to copy a OGG importer。

And let me show you what this looks like。This is based on the SB vors。

 so it's pretty much a STB vors that we use SB image for the PNG。

 this is the same thing and you can download on Sean Berack's website and the licenses。

 I mean as open as possible just like this game， the licenses we have to one with it。

And I create a couple helper functions down here。That can more easily decode either from memory。

Or using a file name。And just assert that well use these correct。Functions okay。

 so this what we want to do for now， all I want to do is to load the OGG。From， from a filing。

Because we're doing like the load。Web for everyone。 Let's try doing that for the music。We have the。

Break out music。We see， so loaded it。Mau music。It's going to be OG G。And this。Well， sure really。

Here should really bet OGG。O。And we also should。Cl this file now。See。

And we could probably make that a dot H。Just going to do that just so we keep the library separate。

 so it's easier to count the lines of code if anyone ever cares。

So I hope you're going to make this page。Let's load that Ogpartter。H。O。HYeah。

 we're all going to have to ignore this warning。Because the library kind of a。

Assumes that we don't care about this horn， we treat mostly don't exit， actually。Ex is not yet。

 I'm also going to ignore this other warning as well。Okay， and we call pile。

Now let's see what happens when we try to run the game。



![](img/25984fe835474479d1617bc0acadfcd6_14.png)

Let me see here in the game。We have the your load O G， so。



![](img/25984fe835474479d1617bc0acadfcd6_16.png)

Let's see how long it's going to take， it' probably going to take a while。😊，Oh， it's optimized， well。

Probably。Not do it optimized。

![](img/25984fe835474479d1617bc0acadfcd6_18.png)

Just so we can properly debug and measure。Okay， so this is the wave in part。

 that was pretty instantaneous。The ODG did take a while if you guys noticed that， but how。

 but let's see if you got what we want， like two samples， sample count looks okay。なんです。I mean。

 probably looks like ballot samples。Let's see if you can hear music。Okay。

 so apparently we are good to go in the OGG Read。

![](img/25984fe835474479d1617bc0acadfcd6_20.png)

![](img/25984fe835474479d1617bc0acadfcd6_21.png)

But we also have to report。The other music。Now， let's see。 We're probably going take a hit speed hit。

 let's see。Yeah。I mean， it's not that bad。But we can do better than that also from the hit。

We're also going to import all those as OGGs， let's see。Now that was pretty bad。浏来器。😊。

Doude that transition is so cool。Kind of forgot about that。Yeah。



![](img/25984fe835474479d1617bc0acadfcd6_23.png)

The game's feeling awesome。I think the wave sounds a bit too loud， the play movements sound。And the。

I that sound， let' see。The volume， I will multiply that by dot 3。Maybe you can multiply that about 2。



![](img/25984fe835474479d1617bc0acadfcd6_25.png)

Should be。More so。

![](img/25984fe835474479d1617bc0acadfcd6_27.png)

Yeah。Okay。Perfect。Now。Let's， I mean， if we didn't want to。



![](img/25984fe835474479d1617bc0acadfcd6_29.png)

Yeah， I mean， it wouldn't be that bad not to optimize。



![](img/25984fe835474479d1617bc0acadfcd6_31.png)

Though youber are going to do it anyway。Yeah， see， that was pretty quick。



![](img/25984fe835474479d1617bc0acadfcd6_33.png)

Yeah。But let's do that asche。 So the thing is， instead of calling。The load ODG， let's see， like this。

Let's just do a quick reminder of how we do the job system。We do that for the audio to， yeah。

 we have this job callback。Again we must do it as a function。Okay。😊。

And we're going to create an asset file later on， let's。I'd say， AC。Load。好主猪。

And then we're just going to load ODT to see。No。OGT。With the file name。

And I believe we do have a data around here。Let's do like。Call back or drop。Call back。Yeah。

 we do best of the data pointer。太棒。Call back。Yeah， we have the QN data。

 so I'm just going to pass this as。this guy。Okay。And now I'm going to have to create。

Another key which I' not to take because when we like。To createreate a queue。

 I think we only do one queue for the audio， yeah。And I'm going to create like a general few。

And we can use like two threads， I think。That'll be safe。And we're not going to add any jobs for now。

O。😊，However， whenever we try to load。OG G。诶。Yeah， you know what？

I're going to do like this would be the callback。みたのかなじ。老 o g。完没。

And then we're going to add the job to the general queue。This is going to be the Async OUG callback。

 and we're going to pass the name。Load OG G70 AC。What you do。General Q。

II'm going to add this as a global pointer。Let see wheres that here。Job or John， Oh。

 probably someone from the library and know some random'm John guy from the code。😊，Job Q O。小不呀。快点。

What's that job queue plan？Okay， nice， nice， nice， nice。And now all I have to do is calling。

The load O G。We should just call that the ACnc。楼都几钱。哎心到比哦。Cannot convert a loaded sound。嗯ん。

So this is a little bit more problematic。Yes we want to receive。This guy。

Is it a loaded sound pointer or a loaded sound to loaded sound？H interesting。

 let's take a look at the OGG reader。Per， yeah， we have the loaded sound from memory。

Maybe you can do just this part。Asynchron asynchronously。Right。

And then we got the pointer to the loaded sound。You know what？

I think we'm going to just take a quick peek at the other game。That I showed on the title page。

Because I don't remember how I did that。It's pretty much same thing。Oh， it takes。

It takes a pointer and then I write to that pointer。So it's going to be like load OGGE。Yeah。Yeah。

 okay， I think I'm going to do that。So。嗯。Let， let's do。 Let's do that。 So indeed。The callback。

 this is kind of a hack。But， I think it's。Okay， heck。Oops that can just close。Disord here。

 otherwise people going to send my messages。And call back。 I'm gonna take。Two data pointers。

It's kind of a weird hack。 It's see a jump to queue。But easier than to try to。

Try to manage that all the time。Load ODG， I'm going to do like same thing I'm going to write。

 assuming that the first data is appointed to a loaded sound。Yeah。Soing that's the case。

 I'm going to write to it。This guy。Yeah。And this would be the data two。

 and this would be the data one， I think that make sense yeah。Okay。

 and then we have to pass the name。And the loaded sound pointer， loaded sound。would sound？So yeah。

 this would be a little top point I're going to write to that。Okay。Okay。

 and now we have to do it like this。do like O to G。Slash hits。Plus。Right。And this just be the。

Loer the gameplay music。And these would the loaded menu music。Yeah呀，看了把太。But that that do for now。

 for now， I mean， for this game， I suppose。Because I don't want to do like a more managed memory thing。

Because there is really no need。Something's wrong。谢谢。Oh， crap。还是就这一点。Okay。で常に。Okay， same thing here。

Fction through pointer to argument for call。So this will be one。And2。And then job has to have one。

To as well。欢nyI think。😊，We already changed that here。Hello， this just the。Function curboite。

One and two。Okay， so entry data。1，2。It has zero4 the other data as well。Now。



![](img/25984fe835474479d1617bc0acadfcd6_35.png)

Maybe this is going to work， maybe this is going to explode， I don't know。



![](img/25984fe835474479d1617bc0acadfcd6_37.png)

And explodes zero size。We're trying to zero the queue。It was a no pointer。General Q。 Oh， okay， yeah。

It's just a multi。 So when we create the general queue， we have to set the general Q pointer。

To the address at that讲。

![](img/25984fe835474479d1617bc0acadfcd6_39.png)

So had nothing to do with what we were doing， I mean had somewhat to do。Oh。

 you guys don't have audio， so you guys didn't hear the manual and stuff。嗯。

So we probably have to assume。That well， let me turn on up。



![](img/25984fe835474479d1617bc0acadfcd6_41.png)

Optimizationations is back off。And we probably have to assume on the audio loop。



![](img/25984fe835474479d1617bc0acadfcd6_43.png)

That we we。Probably don't have audio。 I mean， we can't。 we can not have audio right。

 if that makes sense。 So the volume was one。

![](img/25984fe835474479d1617bc0acadfcd6_45.png)

I suppose。And and the sounds probably null。 But I think we tested this year。 Oh， the sounds not nu。

The sound is not an null。But the samples aren' no。So this is going to be no good as well。

 try to loop， so I think I'm going to continue。The samples are null as well。あ有ちか。チい？



![](img/25984fe835474479d1617bc0acadfcd6_47.png)

Yeah， I think。

![](img/25984fe835474479d1617bc0acadfcd6_49.png)

So now you guys probably heard， right？The takes a while to start。



![](img/25984fe835474479d1617bc0acadfcd6_51.png)

Because we are loading that， but I think I'm going to have set it to load first。



![](img/25984fe835474479d1617bc0acadfcd6_53.png)

The music， let me just close the other game。Yeah， does that this to load first。Yeah。

 that's where you better。And I can probably also set。The menu to load first。Yeah。啊0。And if we。

Go back to the optimized but it's been a little even faster。Yeah。That's perfect。

Isn't there an error in the hit sounds where you do plus 13 instead plus 12， probably yes？

Nice call man， well， I got something wrong。Ohow， that's weird。Oh， no， it's not wrong。Because， well。

 it。Now， it is wrong。It is wrong， you are correct。Because these sounds are named one to 16。

 but the memory is actually from zero to 15。Nice catch， man。No dead beef。Yeah， nice catch。

 so we were probably writing to some memory。There was invalid， and if you tried to use the hit 16。

 we would get no sound。Because we do have a lot of memory if I'm not mistaken。

I don't even remember where that memory is from。It sounds。 oh， it's。 Yeah， it's from the global。

 Yeah， so this was really wrong。 We were， we were writing。😊，Weird stuff， so nice catchman， thanks。

 thanks a lot。

![](img/25984fe835474479d1617bc0acadfcd6_55.png)

🎼打死了。

![](img/25984fe835474479d1617bc0acadfcd6_57.png)

So that easy， we did the AC CoDJ week。So now you can probably delete all sorts of crazy stuff here from the game from the data。

We can delete these wave files。We can delete。Every other hit file。Some reason。

 Windows did this like music thing that haveve just let me。Order the files from their extinction。So。

 yeah。And these guys， I don't need to do them ODG because they're pretty small， I mean。

 they're not that small to be honest。Yeah， the game over is pretty big。

 you know what maybe maybe we're going to do the game over。



![](img/25984fe835474479d1617bc0acadfcd6_59.png)

Yeah， that's just the game over。I just look forward like wave to ODG online converter。



![](img/25984fe835474479d1617bc0acadfcd6_61.png)

That was pretty easy， so it's nice for you guys to see。I'm going to drop。The game over guy here。

And there's going to be no change in the bid rate on the other sample of the channel count。

 the audio， whatever， and it's going to be the vors Koc。

And then we should be able to pretty easily convert that。And that's it， man， we yeah。

 we changed that from like 2。7 megabytes to like 100 and。25 kiloBs。So yeah。That's just huge， Yeah。

 that sounds。That sounds nice。

![](img/25984fe835474479d1617bc0acadfcd6_63.png)

So yeah， that is。 so game over。Sound。The OG G。比A型。偷偷支持。And let's。Probably going to do。All way down。

Okay。Now it should even be even lower。InTm of like data， so this is the total well。

 I have to include the bit maps as well， this is our data size。5 megam。 we went to 30 to5。

 You if you inspired me to go back to just use C sub pluspo my project。 feel like Hms， dude。

 that's awesome to hear。 Thanks。 you know， Yes， man， and you know what。😊，If you。

Do a little see for a while。 See was supposed to even look like a bigger mass than you thought it was originally because you already think it's a mess。

 but when you try to。When you take a look at the simplicity of C， I mean。

 you you don't need anything else I mean yeah， I're got to write your own libraries and stuff。

 download some cool libraries， but in terms of tools。

You hardly need it unless it's a huge project and there's ton of people involved。

 then you probably need。More like。Matta programming features and stuff。But。

It really adds a lot of complexity and it's a really great pleasure to be able to try to see and awesome to hear that man。

😊，Awesome。😊，Okay， I think we are good to go now， let's just test it before we have the game over sound。



![](img/25984fe835474479d1617bc0acadfcd6_65.png)

That was awesome。And that was super easy as well。Well。



![](img/25984fe835474479d1617bc0acadfcd6_67.png)

Yeah， okay， I heard that because that's pretty low， yeah， I heard that。

Because when I play the song it was huge I was like。F explosion。

 so yeah have five megabytes for this game。Looks reasonable five and a half。Sounds reasonable。

 to try to compare my robotic code in C versus possiblying manner of surprised C was much more readable。

 exactly， especially when you go back to it after a long time。

Because if you're interested to the project yeah， you can understand SQ++ pretty well。

 but if you spend like a couple of months off the project and they go back。

 man just to try to understand the project is's a huge。It's like a brain burden， right。

 you keep you know expanding neurons to think about how the product is laid out in terms of code。

And that's in terms of program and the structure， which is the most important thing。And yeah。

 sometimes you do have to， I don't know type a little more or whatever。

 like you could use templates in some some areas where you don't but。At the end of the days。

 program comprehension really is worth。Take a look， I mean。

You could use a little bit of simpleus+ sometimes， you know。

 but like to make like these full crazy C plus+， more simplepl+ and stuff， yeah， and also not a big。

So we've just finished our Aco D part and that was that easy。And now we want to do an asset cooker。

So this is the basic idea I can try to draw for you guys。



![](img/25984fe835474479d1617bc0acadfcd6_69.png)

So we have a bunch of assets， we have like Do PNG， have a bunch a bunch of PNGs。

We have some wave files， wave files， and we have some OGG files。Yeah， okay， so this is the this idea。



![](img/25984fe835474479d1617bc0acadfcd6_71.png)

And for every time you try to read like。

![](img/25984fe835474479d1617bc0acadfcd6_73.png)

Here。We not only have to do like pay call to windows to like open a file handle and things like also handmade hero was so amazing started falling back in 2014 but never really got onto it until now 2014 that was pretty much where it started。

 right？That was awesome。 I heard about it， about it was like。😊，The beginning of 2017。

 so it's been like two and a half years。And I watched a lot of it because it's really what taught me how to program really。

And you know， in this project it's kind of my take on the He heroro idea。

But just to make like a more simple project， people can watch from the beginning to the end and follow along and publish their game without doing like a full giant engine。

 you know it's a different take， although it's really awesome both ways， I think。

 I think one really adds to the other one。Because O and I learned so much from Casey。

 that was really， really cool。So we have all these files that we have to open file handles and ask windows to do all sorts of crazy stuff。

 and it's not that many， to be honest。But it is a while， and we also have to know。

Have to give that to the player in like a bunch of different files and it's kind of open for him to download and edit and whatever。

And what we want to do is take all these guys and do like a dot and we can do like a dot pack file for like back file。

 we could do like where is all the data？Whi's like from the doom guys。

That could be cool if we could do like it wheres all the data file。And。Or whatever。

 we can do like a dot breakout， break out， bro， dot bro。呃。

So we're going to have to read just one file。And then whenever we want these guys to be。

 whenever we want to find these guys， we just look for the offset。

And the best way I found of doing these kinds of。C acid systems。

But I kind of got to the top of just doing courses and not making anything。

 yeah this is a dangerous thing， I suppose。In the entrepreneurship realm。

 it's called like a book Enne， right， the entrepreneur that just like keeps reading books all the time and watching courses and stuff。

But didn't actually create any imp business right It's the same thing for programming。

 I got stuck watching like John blow's lives for live streams。

 Live is kind of interesting in John blowlow's lives。

 John blowlow live streams for some time and I wasn't actually programming my projects。

 but I love to watch， you know in programming。😊，And although there is value to learning through that。

 you do have to get your handss down on the chair and just program yourself in。

But sometimes they also compliment each other quite a bit。

 so it's nice that you got to hand me here on now， and that's the main point。

 I mean it's never too late to start anything really。Okay。

 so how are we supposed to structure these these tie What I'm going to do I'm going to create a new file。



![](img/25984fe835474479d1617bc0acadfcd6_75.png)

And going call this like cooker。好文。Got see。 and'm going to have a minimumum。

And these are going to be the files， the assets， so I'm going to have like。

I see we're going to have a bitm invincibility， so we're going to have like a。嗯电视。

The other two is going to take away。Sibility and you're going to have a bitm for a triple shot and have a bitmap for a comment。

Whatever， okay， then I'm gonna have a bit map。 Let's see we have sound effects。

 Now I'm gonna to have the sound effects。For the forest field。And stuff。

 so we're gonna to have a email for all the assets。 Okay。

 and this order is going to be used both by the game。 This why common， right。

 it's gonna to be used both in the game and by the cooker So the cooker is gonna it's going。

It's going to load the game in that specific order， okay？And source the game。

 so whenever the game loads， you're going to make sure that the cooker misspelld invincibility invin invincibility thanks。

You know， I spent quite a while writing that and I was appreciated it was wrong， sorry it was wrong。

 thanks man。So the cooker is going to use the same structure for the assets as the game。

And now when we go to read this， which is an important part， right again。



![](img/25984fe835474479d1617bc0acadfcd6_77.png)

It's going to be really simple， we're going to save like we may going to say like a magic word。

In the beginning， as well as like a version number， but yeah， we don't really care about that。

And then we're going to do。A asset count。So this is going to be useful for the game to check if we loaded the same assets that we are expecting and we can insert on that and then for every asset。

 let's say for。Every。Asset。We are going to store the offset like where it starts where。

Let's call this like。It'sGo to file。Offset。

![](img/25984fe835474479d1617bc0acadfcd6_79.png)

Okay， because now whenever we let's say we need the force field。

 So let's say we have the file like like this。 So I'm gonna going to add the header。Size。So。

 let's see。Another size， okay， which is these guys。In then I'm going to add。Like a youth 32。

Which is going to be the file offset。Times。What acid I'm trying to load？

And I think that's not the most robust thing ever if we change the assets all the time。

 but that's not the case in this game is's going to be pretty simple， I think。

And this going to give us the asset location， So asset。Start location。Okay。

 and I can just zero this out。This would be the asset location。

And we can also do the the proper well， then we we can just， you know， do the pack plus the。

Was the asset star location？This is actual the asset， so asset。ビです。ケケ。



![](img/25984fe835474479d1617bc0acadfcd6_81.png)

That's it。😊，And so we first stored allocations and then restore the assets。Okay。😊。

And if you need the size of the asset， we can get the next one and subtract this one。

So that's the basic structure for the files。

![](img/25984fe835474479d1617bc0acadfcd6_83.png)

And let's start programming that， so I'm going to create the cooker and the cooker is going to be a application outside of the game。

So we're going to compile that separately and we're not going to ship that in the user game。

So the basic idea is I'm going to go through all the essence。And structure that on the on the file。

 So let me just copy the right。白。Alright， entire file。 What it called。Oh right， Saify out， whatever。

So what is this gonna be。Right， Kyle。And then again pass the file name。Okay。😊，The file name。

Generic read， always create， okay？It's invalid to be assert and we exit。

 and I wanted to return a bull yeah。also going to include。Utilities。Okay。Okay， so this the result。

 we write the file。then yeah， this looks perfect。Okay， and now I'm going to create like a。

Memory for us to use。And we can do like 100 megabytes。Mala fat。

We don't really care about this program too much， but that's just build it right。

 it's kind of important。啊 see。You'm going to put that。Fth the game。

This would be like the game killed。And this will be the asset。Cooker。嗯。

And we don't need like the development of the profiling flag。Okay， handle， yeah。

 I have to include handles。加H。Result。好。Data。嗯，Yeah。The data。Do you have a string。We have strong。

 yeah we do。It's not like a proper string list of some very sequel。size在哪。A size and up number。

I think，And we don't have the me Nebytes。 I like， I like writing。On the code。Let's see。

Instead of like Kb for kilobytes。I like writing。KV bitetes， I'm not sure how we pronounce that。

 but the basic idea is this makes it really evident。There we are actually doing a 124 conversion。

Okay， instead of like the ambgu was。Kb， which you're not sure that it's like。啊。124，1024。

Or just the thousands of multiplications。So this， I like writing that on the cold base。で十。Okay， okay。

Okay。So this is the memory。And we probably have like a current pointer to the memory。

Make that global。ま？Okay， now first of all， we're going to just like I said。

 or I can probably comment。You like。Fileles spec。It's going to be like 16 bys。Magic。😊。

Word I do like break。Bek for breakout。BO是 break up。And that's to be over break now。

Or maybe game assets。Let's do G for the methods， then we're going to do 160 bytes。

 the version number。Delights。Pson number2。相比 one。Then， we're going to do 32 bytes。

For the asset count as。And that's the headache， right？And then for every asset。We're going to save。

32 pointss。Of asset location file。And then I'm going to save the asset。

For every asset later on and Im also going to save 32 bytes。Like。😊。

Total size because we want to get the next file as well so we can subtract the two and get the size of the acid。

And he's the last asset， 2。5 is' not going to have a next asset。I'm going to insert the total asset。

 the total size。So we can properly do the subjection for everyone。Okay。对。So that's the plan。

Now let's start doing。メージした。So。And I can probably do like a memory ad。嗯。Yeah， that's true like。

Face memory。Then'm going to do memory。because we're going to offset the memory and then later on we need the memory to save okay。

So， yeah， I'm going to， let's see。Said memory。To。AGA for game assets。

Then I'm gonna offset the memory by。2 bites。Then used。Theres two bites。没意思。嗯。Oh well。12。Well。

 I suppose I'm going to do it like this。Used， don't have it used， Use many。屋企。😊。

So that was the magic word。 Now I'm going to set。The version number。Memory。And be version one。

And we could do helper functions。Two， you know。And they you have like。CouldCould you do a mem copy。

 save the screen， yeah， I could， but things are just two characters。

I think it's just easier to do like this， but yeah， totally if we were more。

 we are go to a mancott who took copy the files。So yeah， you are correct， in this sense。

And we should probably do like were， if we were going to do like a bigger thing here。

 we should probably do like helpper functions to do any size like this。

But we're probably only on going to do this for the files。Okay。Yeah。😊，Nice， and another thing。

We can probably save the P& G。

![](img/25984fe835474479d1617bc0acadfcd6_85.png)

Since those are pretty small， probably save our own file。



![](img/25984fe835474479d1617bc0acadfcd6_87.png)

Instead of saving the P AndG。We could do that。Yeah， I'm can do one set at a time。O。😊，Okay。

 the memory and okay， so got the version number。And now we're going to probably like define a version。

Just so it's easier to change later on， but they're not going to change。And the assets count。

 So we are going to。we do this cooker comment thing。So we're going to include this。

And we're going to have all the assets。And let's just do。Like the logo。Ls for now。

So so of can test one thing at a time。And then we're going to do asset this is a bitmap。

This is the asset count。And then we're going to save as an S32 gas count。Okay。😊，Okay。

 so we finished the header and which probably was probably like。To the five spec。Here。

And we can define a couple things like fine。Haer size。The other size is going to be。A fines。Okay。😊，嗯。

二啊 yeah。Now we have to save this guy， okay， so first thing we're going to do。

 we're going to have to load it。Save its location on the file。And then save its location properly。

 so it's we're going to need the load PNG， right？Let's go back to the game。

Let's see whenever we do the logo， we do the load PNG。Like this。So we're going to do this in line。

 later on， I'm going to abstract that to a function so。Loing a kji。So this is a loaded。で man。Is this。

And。We havet where do we load this， we load that on the render。No电辑要 do。Or just caught it man。Yeah。

 so。Let's take this guy here as well。And then we load the PG and we are also going to need。Yeah see。

And the read entire file。And the free file， I don't， maybe we shouldn't free the file。Okay。Now。

We loaded the PNG， and I have to save it。But you know what， first of all。

 I think I'm going to save every guy， well， we don't know yet okay。Every we don't know the location。

 we should。I I'm going to create another pointer， to be honest。I'm gonna to create like， a。

They files。Like，5 memory。And。And it's going to be at the memory。Plus。The asset count。Times。

The size of a U32。Okay we're going to save the file at the file memory a and we're going to save the size。

At a memory。ok。😊，And weload the P andG。And you know what， I think I'm going to save。Yeah。

 I think we're want to save the uncompressed PNG。There arebit maps。

 let's see how much the weight's like， yes， 23 K ons。They blow up to be huge。

 which I don't think they will。It's not going to be worth it。Okay。So。So we load。The bidmap。

And now we should save。This size。Right。know。Yeah， because that way we don't need to uncompress PNGs in the game。

That's a better call。Memory。As。You 32。Will be。The bitmap。5位。Times the bitmap height。

Time to size up a U32， which are the pixels。ok。😊，And then we can offset that by the size of a U32 so we saved。

I'm going to save if this file。Oh， it's not correct， though it's not the file size。

To be where it is at。So it's going to be， yeah， I don't know what I thought。

 it's going to be the file memory ad。Minus。The base memory。Yeah。Okay。

 now it's better now we were saving where the file is。喂。です。Well where the asset。I in the file。

And the acid。And we're just said now I'm going to demand copy。Cia J Blaazing 93。

 I'm going to do the mam copy， So mam copy desk。The source is going to be。Well。I'm gonna do。

I'm not going to uncompress the P&G for now。Okay。😊，Imな个なか。

Maybe we're going to do this later on the first version。Just be a straight cop， okay？Now， let' see。

Sttrains file。O。File that data， file do size。Cannot convert？Oh well。

I don't think we're going to have problems。With that we probably a。

 but they're not going to have like two gigabyte。Ass it file anyways。So。I think this is correct。

 we're going to have to be plug down later on， but we're going to do this for every file and in the very end。

I'm going to write file。Call this assets。有た。And then I'm going to pass as a string。The used， oh。

 have to increment the used as browser。Yeah use memory。Plus。This。And this is going to be the used。

Yeah。Memory。Plus， the five cents。Take them。Use memory and a basement。This is okay。Oh。

 I think we do like。Memory and size。Yeah。This whole U8 versus cha thing。

What I suppose it was correct。It's size and memory。O。Okay， okay。Dude， what's the problem？

 What's our string。Our string is sharp。Mor。Yes。Nice。Let's put a breakpoint there。

Go're going to open the Vi Studio。My best in the asset cooker。



![](img/25984fe835474479d1617bc0acadfcd6_89.png)

O。Let see。So we got the memory， see our memory。And let's also see the used memory。Okay， so， oh。

 I think we are。Yeah。😊，We are optimized， which is no good to debug。



![](img/25984fe835474479d1617bc0acadfcd6_91.png)

![](img/25984fe835474479d1617bc0acadfcd6_92.png)

Wellow。Let's see，'s see。LetLet's go back and see the I think we already are in a good guesses。

 that's our magic word。And I use memories now two bytes。Persion number。Well， I don't see a one， okay。

 there's a one。Asset count is also one。Nice。The file memory at。It's going to be pretty close。

 I think， and I'd see。Then I'm going to read the files。



![](img/25984fe835474479d1617bc0acadfcd6_94.png)

好。This actually is in the wrong place。 I'm running this from the build folder， so I have to go back。



![](img/25984fe835474479d1617bc0acadfcd6_96.png)

Fhoer。边工我踩的啲。Okay， now read the file looks good。Let me just see where the base memory is again。Okay。

😊，So okay， so now it' saved where the file is at。Which is 12。I think that's correct。

And then we save the whole thing。This looks perfect。Is this really 12， see，1，2， three？6，8，9。2Yeah。

 so this is zero， so this is 12。Perfect， so we' got the base memory。And we've got the use memory。

And we're going to save that to the file。You' probably saved on the correct position though。

 but let's see it should be on the build folder。And we have assetss。 Pan， which is 1k。

So I let'd say 10 k and the logo was， let's see how much it was， Oh， we just gave pG， so never mind。

Never mind， I'm also going to stay that in the correct position， I' see。



![](img/25984fe835474479d1617bc0acadfcd6_98.png)

诶 data他。so it's easier， Okay， so now that's the first version of the loader。

 because if we manage to load that successfully， the rest will just be， I don't know。就是。You know。

 riding all these guys。Okay， loading a asset。And message。ok。😊，So I'm going to do like Kate。

Assit loader。Not see。And I'm going to do like。Yes。Internal。String。L pack。And for now。

 I'm going to hard codedly load a attack file。Assets stock pack。Data I back。 Okay。

 and then just going to return this guy。Then we can do like smarter stuff for this。

You know what I don't really think we need that。Let's just go to the game。Then I load。

 see what we are loading。So I'm going to do like。A pack file。I's do a string pack file。

Download a pack file looks good。Now let's load the logo， so the logo is going to be load acid。

And then I'm going to pass what asset is， so it's going to be a bitmap logoly。Light。Okay。

 so I'm probably going to make。This guy， a。可能不。Yeah， so it's more convenient。就。Loower。

Eternal void load acid。Then it takes the asset。Okay。😊，Now we have the pack。

 how it's supposed to load the asset we need。Instead of doing like a low asset。

I really want like a load PNG from tech。That's what I want。So， in the renderer。

This is not really the best place， I think we're going to move that。You're here， I suppose。没有。

I'm going to wait a little bit， Okay， so load asset， I' going to have a load PG same thing。From pack。

And I'm going to take。Asset。Instead of just doing the whole thing。It's going to load assets。

And all the rest should be the same thing。Yes， so I do need to be yeah， sorry。Anyways。Then in the。

C over。And do that on Windows。Okay， then I'm going to load the。First。And then the pack thing。Again。

Back5。Here。Okay， okay。 now this should be good to go， I think。

All I have to do is to write the load asset， which is pretty easy， right， and have like the result。

The result。Dots data。It's going to be the pack。Plus， Max probably。Make like。F a location。

Just to go step by step and the follow case would be the pack。What the header size。O。😊。

Because the asset。Time the size of the utility32， we already discussed that。

So that's the file location。I scroll had like the file end。O行。And it's the same thing。

SoBut the assets is worth。And just to make sure we are working on a cooker after doing all these guys。

I'm going to save one more。Which is like the final size。InC of the memory。

 so it's going to be the asset count。Oh， that was already correct， right？

Number of assets point yeah plus one。Plus one。Because we insert。The total file。ok。😊，で。嗯。Now， this。

 I'm just going to add the actual。有。There' the last file。

 the last filess end will be the end of the file， okay？And well。

 we don't need to offset the memory more because we finished。Okay， now。

This is going to be plus the file location。And the result， that size。

Will be the file and location minus the file certification。And I think we are good go， I think。

 let's see pack。Oh， it's back final。Her size don't include。the cooker comments。

That's legal forstruct。Oh， will。 yeah， Okay。 I thought that， we don't need。To add the final guy。

 we could use like back end。But if it's only if it's equal to the。Very end and whatever， okay。

Allocation。This。2。先生？ok。

![](img/25984fe835474479d1617bc0acadfcd6_100.png)

Okay， do guys think thist work？

![](img/25984fe835474479d1617bc0acadfcd6_102.png)

Oh， Charlotte， we also have to read the tag file。To see I was wrong， I can't do。

I can't do like the sea。Yeah， we can't do it like this。The load pack。

Does of you have to test your things。So。Load back file。And the fact5 could really just be a。

You8 pointer。Don't need to have the whole stream。This way we don't need to。Get the state apart。

I think we have to use its size。O。😊，Now。The back file is gonna be this。Plus。dot。Data。Okay。😊。

Again I'm just going to assert a couple things。 I'm going to assert。The p file。Equals to T。

Game assets。And then plus two， this is the version number。Pion number。

And this I'm going to do this as a S 16， is that a S 16 or a year 16？S16。Okay。😊。

And the last thing I'll do， well， I'm going make this as a shot。Kind of redundant to return and load。

 but I think that'll be more clear in the code。G this di version number and then we can also search the asset count。

Because like if we update。One of the guys and not the other one will be able to。Catch this here。

 okay。Now this is it。This is it， I think。Let's try doing the load at。



![](img/25984fe835474479d1617bc0acadfcd6_104.png)

In the game， let's see。H know。Do you guys think this work？



![](img/25984fe835474479d1617bc0acadfcd6_106.png)

That files was no pointer。Daタ。Let's just see where do we get the front？



![](img/25984fe835474479d1617bc0acadfcd6_108.png)

Oh， I don't think we saved。In the correct place。接。

![](img/25984fe835474479d1617bc0acadfcd6_110.png)

Eventuallypparently， we didn't yeah， we also had to make an optimized build。Find thing。 Yeah， okay。



![](img/25984fe835474479d1617bc0acadfcd6_112.png)

No funny。Well。I didn't see this load。

![](img/25984fe835474479d1617bc0acadfcd6_114.png)

Being called。See sometimes these break points go all crazy for some reason。Oh。

 I was supposed to remove this guy。

![](img/25984fe835474479d1617bc0acadfcd6_116.png)

So that was the reason。Okay， now let's load assets number zero。Hlocation 16。That was 12。哦。

And allocation。That's the PA file。So。This。Swan。Yeah，16， it is 16 location。

So you should start with this C4206 thing。7。No， that's weird。Oh， the fileations shouldn。

While it's weird in the packC file。You know what， I just learned like right now that I could write the variable name here。

Okay， so this is the version number。This。Let see，0，1，2，3，4，5，6，7，8。1012 see he was 12。

Why did it save 16？Oh， because of this guy。weird。That's。Let's try again。So it is 60， okay。

 this correct this。This is 16， so this is where the first guy is， this is the total size。Let's see。

 So it's。00，0，0パ6。Yep， this is correct now I should start with989， 50。See。Yeah。

 I think this is correct， I just make sure。It 950。Nice， now we correctly loaded。The first guy。

 and let's say the size is 99。0，8。 Let's just make sure。

That our size is the same as for the light logo。C99，08。Perfect。And well， let's see if you load。快学。

We do， we do， we do load the file。

![](img/25984fe835474479d1617bc0acadfcd6_118.png)

Our asset system is pretty much done at this point， pretty much done。



![](img/25984fe835474479d1617bc0acadfcd6_120.png)

It should be to。All we need to do whichs kind of boring， but we need to do this。

We need to iterate through。Yeah， you know what we probably do。你光。As you like the。Invincibility。

Be people。The comment。一。Power down， inverted。Well， probably just do。前梯。Turtle。Strong。

The light and the dark logos。ok。😊，Now。

![](img/25984fe835474479d1617bc0acadfcd6_122.png)

Right now， if we try to run the game， we should assert。



![](img/25984fe835474479d1617bc0acadfcd6_124.png)

And we do。Does the assets account change， so we should probably update。



![](img/25984fe835474479d1617bc0acadfcd6_126.png)

The cooker。If you guys have any question， just be sure to drop them。On the chat。

And I'll try to answer it。ok。😊，Just make sure。Okay嗯。Yeah。阿及。In the cooker。

We have to load all of these assets。Okay。😊，So I'm going to do something like load acid。Like load。

 yeah， could load acid。上次来。The only tricky thing about the system。And by tricky， I mean。

Affinity thing。Is that this order has to match this order。

And if we are supposed to do a more robust system later on， we have to keep that in mind， okay。So。

その終わい。Road asset。File。And one of the things we could do， we could。没有。I don't know。

But it'll work with this game， we don't have that many assets。Fよ。And it's。It。😊，Okay。😊，File。

File memory at well。Go make these guys globals。Do I need the basement area I also？Me。

Tur just happens。 Okay， so I think。If we go to the game。And ask it to load， see。

 so this is the thing we should probably do a better system now that we are capable at this point。

Right。Which is basically do like a far loop。You like last bit。

So we don't need to do all these files by hand and stuff。And then we can do like with maps。哎。

Because load P G。え。And the dark will be the last big map for now。

Kind of thinking how I want to use this system。嗯。Because whenever we call like the。The big map stuff？

Like the good map andip like this draw a good map。Probably do something like。If Matt。嗯。

Because we could do。The maps。Intencibility。But this will not work for audio。That won't be zero here。

Maybe get a bitmap。Yeah， maybe get it man forward。So。ok。😊，Okay， so。嗯，排。My acid loader。

And we're going to do an in line。D map pointer， get this map。Index。Well it's about this asset。

And then to get the itmap。I'm going to do is return like maps。Yeah， see。

 if this was supposed to be more robust， I wouldn't make this a global。

I'm done with Mor++ 11 I'm becoming insane by it， you said the truth right there。Whenever we。

Look at a C conase and then like a modern C plus plus， dude you。😊，I can't handle it， it's too much。

From my brain， I mean programming is hard enough when the language is it helps right。

 but when the language tries to be more complicated than that program you're trying to write come on。

But just like the other guy up there， you probably do like smaller things in see。

And you really have more fun and be more productive and learn a lot more。That's what I'm doing。

 these are just hobby projects as well。But they have modern C+ plus。Should really be avoidable。

 so in this case I'm just going to return with maps plus the assets。But in the audio。

 I'm going to have to add an outside stuff and we don't have a bit mapps。

And what I'm going to do is I'm going to create。bit mapap， bit maps。Last。お？第个。ok。😊，Perfect。😊，Now。See。

 this is way better， so now we don't need。You don't need all of this stuff。We don't need。

Invincibility， the triple， the comet， the TNT， the total invincibility， yeah。

 we don't need any of this。It's going to be way better our system。But now whenever we try to play。

 doesn't do like the cat map。I pass B。Logo light。Way better， way better man。See what else？Local dark。

or shot。Comment。前梯。知道。Invinsibility。可以先可。Oh， I think I was wrong。No， it's correct。

 it's inmissibility。O。😊，看。We should probably。Yeah， see。You probably do this in an easier way。Like。😊。

A way to associate。你的。Assoociate。25呀。I'm going to say the power up index to the asset index， right？

Okay。

![](img/25984fe835474479d1617bc0acadfcd6_128.png)

啊。Do you guys think we were going to work？I anyway don't worry， oh， this is the cooker。

And we don't worry either ask the violation。Reading location。Pixels。



![](img/25984fe835474479d1617bc0acadfcd6_130.png)

Yeah， probably fixs us。Okay。Let's see good maps。Go from the first to the last。

 it can oh should be equal。

![](img/25984fe835474479d1617bc0acadfcd6_132.png)

Are not。As it to1。Its our back file， yeah。That5 is not good。That's try I talking at the backfire。

I have one question but you see view studio install some other。Linker。

 because if it has for instance plus+ errors， why the code is in C。

I am compiling using the command line。

![](img/25984fe835474479d1617bc0acadfcd6_134.png)

So。When I compile using CL。And passing a C file。It compileIt compiles using the C compiler。

If I were to create a View Studio project， which is not the case。

Then it would compile the C++ project， and then it would be all sorts of problems， right？So， yeah。



![](img/25984fe835474479d1617bc0acadfcd6_136.png)

If you want to compile using the MSVC， a C program。

 you have to do it on the command line like we're doing it here， then no problem。

 it's going to run as a C program， but if you create a project like this， this will not work。Okay。

 so our back file looks good。Let's see if anyone does anything wrong with this guy， see。

We are changing。The pack file， somewhere。Let's just see。Pact file， O IC。 Yeah。

 So if you want to compile using a see program use the Microsoft compiler， you have to。

We have to do that on the command line。Oh， we can't free the image anymore。



![](img/25984fe835474479d1617bc0acadfcd6_138.png)

Okay， yeah。Because since now we're just one file。If we try to free the image。



![](img/25984fe835474479d1617bc0acadfcd6_140.png)

We're trying to refframeing the pact file。Which is no good， we can't free that。Okay， map colors。

Which kitm is this？The logo of light。Let's see the bit maps。



![](img/25984fe835474479d1617bc0acadfcd6_142.png)

Okay， no one loaded， no one。

![](img/25984fe835474479d1617bc0acadfcd6_144.png)

Loowed the correctly。Well， in fact， we don't really know。

It truth be told if we are saving correctly because you change the safe system。But well， let's see。

Okay， let's see。Yes， he。Interesting， our。Data looks correct， though。

 but the size is zero for some reason。切。File location 48 looks correct。File and location 48。



![](img/25984fe835474479d1617bc0acadfcd6_146.png)

Okay， so our cooker。It's not correct。And we load the asset。If oh。

 we are not increment the five memory yet。Youcrement the file memory at。The file outside。



![](img/25984fe835474479d1617bc0acadfcd6_148.png)

Okay， so you run the cooker。And we run the game， let's see。Okay， another problem。

 let's see our bitmps， well still problematic。Still problematic。 Let's， let's go again。 let's see。

Lad asset， allocationlocation 48。And location still is 48。Maybe I'm going to tap the cooker。

And see the problem。

![](img/25984fe835474479d1617bc0acadfcd6_150.png)

那你 just是。Before I can just think about this for。I am。F memory at。

Mine is the base I'm saving where I'm going to save this guy。Then I saved this guy。

Then I increment the file memory at。In the next time when I try to save it。Yeah。

 I know this looks correct。

![](img/25984fe835474479d1617bc0acadfcd6_152.png)

Let's。Let's try and load the asset I see。So。What。😮，Oh， same problem， man， we changed the。



![](img/25984fe835474479d1617bc0acadfcd6_154.png)

Yeah， so。Data will be。Well， that was wrong。Data will be dot dot。



![](img/25984fe835474479d1617bc0acadfcd6_156.png)

Okay。So yeah， our cooker was not。Working。Nowax次。

![](img/25984fe835474479d1617bc0acadfcd6_158.png)

Oh if truth be told， I don't think we use the bitmap。



![](img/25984fe835474479d1617bc0acadfcd6_160.png)

Forcuute anymore。But I don't think we encode that anyway， so let's see before us。Sound。Yeah呀，我就猜不下。

So next step is to do this with a sound。And that's going to be pretty easy， I think。

 we're going to do the same thing， same thing。UI'm just going to take like a two minute break just to get more water because I rain out of water。

呃。To be break。And then when I go back， we're going and finish and do all the assets through the asset system。

 then we can try。Try running the game with no assets in whatever。Okay。😊，So。Two minutes， everyone。

Okay。I am back。Okay， let's see。We should now do the sound effects and it's going to be the same thing。

 same thing。So I'm gonna to have like。First。So。And I should probably separate them into wave and OGG。

Probably just so it's easier to load。嗯。Or maybe we could add like a flag the beginning。

I'm going to do this， so the first sound is going to be the last big map。Plus one。This works， right。

And this works。So and I'm going to do， let's do like big maps。第一点的。Yes。Okay， so sound。Worace。Field。

Oh， you know what we should do？We should load all the Asnc OGT stuff。HerForload， anything else。Yeah。

Because this whole time rolling like the other waves， we could below the OEGs。Nice。So forest field。

Sod like's to do the ODG first。So we're going to do like the sound。Meュ。ューせ？え。Sound main music。

And that's where the sounds hit。1。其主一。One to 16 Oh I didn't even count that to be honest。😊。

And let's do the game。Over。So。Perfect。😊，Now we're going to do the force fields。For fuel。Worse field。

And I'm going to do this。Fireworks。I'm不 to let's see what。The spring。

And we're going to do the start game。And I'm gonna do the blue slide。Then redirect。I going the ball。

Com sound we're going to do。I'll just comment。北京？This would be the comment。这是你的欧三。Power。Or down。

In your face。H我。And。L sound。That's weird。The wind sound， I think I misspell that。就是。

Now it was actually called oh， because swear're going we load the game。看。Okay。Oh well。sound。

People call that load。And we've got five bricks。And we have a sign。

This is where a meta program would be。Cany。But yeah。I think we are done。I think we are done。Okay。

 I've got a bunch of sounds。And we have to load them all like we did last time。Let's go there。

 Let's go to the cooker。还是来。So maybe we should add like。Yeah， you know。

 I'm going to change post a little bit。For every asset， you're going to save like the asset。Format。

And then， the asset。And let's do like。8， right。From the asset format。And I're going to do light。

Asset format。点击。They're gonna have。waveave。Yeah I'm going to have OGT。ok。Now， instead of。

Instead of a。o o d g。但就是。If guys have any questions， just let me know。And I'll try to answer you。

And I I'm going to have pass a new parameter here。Which is what？T。😊，Is the sound。Yeah。K。Okay。And。嗯。

Pretty cool， so I'm going to pass here。The asset format。PG。I'm going to pass here。S。Wmat。好主机。

And here I'm going to pass。ho。And as the asset。Format。And now here the load asset。Gona take。That。

Ormat。Okay， and I'm going to save。一 see。Format we're going to save the format。As a UH。My hero。

 what do you mean， man？I have memory plus。Oops， this is wrong。By memory。And。Equals。Format。以为。

I love your codes， how are you doing doing I'm doing great， I've had a lot of work recently。😊。

But back to streaming。And this game is really close， I'm really excited because then I released it。

As said in the beginning of the stream， I'm pretty sure going to be able to release it on steam。

 which is going to be awesome， you know be my first game that I don't use any engines on steam。

And I want to show as much as I can how to implement an online subsystem， I can' to like show this。

 I can't show this team API。But if I do like my abstraction on top of it。

 I think I'm be able to show how to implement a general。Online subism。

That would be cool and there are just some cleanup to do and like some robustness things。

D on last subsystem。 and then I think it can replace。 So I'm doing great。 Everything seems to be。😊。

Moving forward nicely。The other format。And then。This guy， the asset。Think this is。Nice。

That's the dream where gaming see and release it on steam exactly man。

 that's also my dream because I haven't done that before。

 so I'm going to try to do this live actually。Yeah。

 I'm not sure I'm going to have to read the NA more calmly but。I think I'm able to do it know。

 like I said， I can't show the same code。But it'll be cool anyway。

 even if I've had camps show the implementation on this team stuff。

They'll be excited to release the game S team。And you know then the next game is going to be even more complex than this game。

 that's the idea。That's the idea。I think we should be good to go。Get a lot of stuff here。Yeah。



![](img/25984fe835474479d1617bc0acadfcd6_162.png)

Let's try running the cooker。 Okay， Oh， and yes， probably。



![](img/25984fe835474479d1617bc0acadfcd6_164.png)

Also， change the data。To this。

![](img/25984fe835474479d1617bc0acadfcd6_166.png)

Okay， okay， let's try running again。

![](img/25984fe835474479d1617bc0acadfcd6_168.png)

Nice， and now you should be able to go in the game。And the same thing we did。

For the audio to do with the rest。We're going to do a last sound。So first sound。

 I going to do with that sound。啊。Sound equals B。And this guy would be the first sound。

I guess it would start would be a classic paw。

![](img/25984fe835474479d1617bc0acadfcd6_170.png)

Yeah， well， we did a more complex game than a customer pun， this game is more complex， I think。啊。

Well， now we're crashing all over the place。And I can't show the gate， well， I can try it。

And try showing the game。In case no people on stream haven。



![](img/25984fe835474479d1617bc0acadfcd6_172.png)

还钱。This is the game。

![](img/25984fe835474479d1617bc0acadfcd6_174.png)

A you doing oh。Yeah， we're going to have to fix the bug。



![](img/25984fe835474479d1617bc0acadfcd6_176.png)

Then I can do a call。And again， I showed it again。Oh， that sucks。



![](img/25984fe835474479d1617bc0acadfcd6_178.png)

But why are we crashing again？We shouldn't be crashing。



![](img/25984fe835474479d1617bc0acadfcd6_180.png)

It' that color when it tried to。At the logo light。Logo light。



![](img/25984fe835474479d1617bc0acadfcd6_182.png)

Well， lets de booked that like we did before。I said loader。我来下这ち。

And I've seen the other features is break out different kind of acade games exactly。

 it's like breakout， it's like what if。😊，Every other acade game had to be like breakout that's the cool thing。

 but I'm doing on YouTube， let me show you guys。

![](img/25984fe835474479d1617bc0acadfcd6_184.png)

On the YouTube channel I have started doing a tutorial series and this tutorial series is a step by step approach so it's not like the stream which I just program like crazy it's when I really explain and there's like video that I draw and it's pretty cool I mean it's a lot of work。

Editing all these videos， but I think it's getting pretty cool。And I'm about release the other one。

 just finishing the editing。And this game I'm doing Po。

 I'm doing step by step palm and it's going to be really cool。

 it's more simple than this breakout game， but you can watch the whole thing。

 all the explanations and stuff if you a little bit of C or C++ you'll be running at home to create this first game。



![](img/25984fe835474479d1617bc0acadfcd6_186.png)

And I'll probably release it。So this looks okay， though。File data and file size， see。



![](img/25984fe835474479d1617bc0acadfcd6_188.png)

I think the file data oh okay yeah， because they haven't updated the code。



![](img/25984fe835474479d1617bc0acadfcd6_190.png)

Got excited for God to finish the code， so in the asset loader when I try to load the P&G from well and I try to load the asset。

 see。I'm going to pass what kind of asset I'm expected to load。Okay， so this is the asset format。骗心。

Soing the load asset。Here。This would be plus the signs of U8。And this will be the end。

What's the size up？You wait。And。And I do need。冇。Format。You're going assert。Asset format。Its equal。

Let's say， to this。S a。タ。Okay， now able， we should be good to go。



![](img/25984fe835474479d1617bc0acadfcd6_192.png)

![](img/25984fe835474479d1617bc0acadfcd6_193.png)

And we're crashing because we're expecting zero and we are getting what？TheP file。Oh yeah。

 we're getting。Oh， this is really wrong。

![](img/25984fe835474479d1617bc0acadfcd6_195.png)

Yeah， this is totally wrong。Never。Let's see you get the header。

You have the file again and the file end。And if I would begin， we're going to offset that。



![](img/25984fe835474479d1617bc0acadfcd6_197.png)

嗯。😊，All， let's put a breakpoint here， let's go step by step。So 208， okay。

I wasn't too much of step by step。Let's see。Weird， our pack file。嗯。

We try to go step by step again our pack file。ItTo be an offset。Cool dude， hey man， thanks。其实啊。

So weird。Oh。Yeah， okay， this is correct。Back 5 plus 2，0，8。



![](img/25984fe835474479d1617bc0acadfcd6_199.png)

Let's just go back and check out the。でくく。A see programmer。 Love it already。 Oh， man。

 I don't love when to see the game。 man， that's the most， that's the most cool thing。😊。

But we're just finishing the asset system and now we have a way for the asset to know what kind of asset it is。

嗯。So yeah。This should be good to go， send that as a format and then increment it， and then copy that。

File size， let's see。Oh， they used memory。入連なってですね。That was the problem。Is it an own extension。

 I see read no， it's not。 Yeah， Oh， and own。 you mean that we created。 Yes。

 this dot pack we just made up。This format。We specify it here。How it's laid out。

 there's like the GA for game asset。Which probably changed the。The extension。Yeah。

 it's GA for a game method， then we save the version number， the asset count。For every S save。

 where's located in the file。Then we saved the total size。

And then for we have asset we save the format and the asset。And I contribute。 Well， you， well。

 the game is almost done。 But if you go to my。

![](img/25984fe835474479d1617bc0acadfcd6_201.png)

![](img/25984fe835474479d1617bc0acadfcd6_202.png)

If you go to my HIO page， which dz。h。o， can download the whole source code for free。



![](img/25984fe835474479d1617bc0acadfcd6_204.png)

And you can download all the 20 days of it because I've been live streaming the whole process。



![](img/25984fe835474479d1617bc0acadfcd6_206.png)

And you can watch the whole thing on YouTube YouTubetube/danayd， so you can watch the whole thing。



![](img/25984fe835474479d1617bc0acadfcd6_208.png)

And for every day you can download the source code and then you can you know。

 and the license is pretty much like do whatever you want exactly exactly do whatever you want it's either like public domain or you can copy。

 modify， publish distribute。Whatever， you know， so you can download the last day。

 which I'm going to post just when I finished the stream。

 and then you can increment this asset system， which is pretty cool。



![](img/25984fe835474479d1617bc0acadfcd6_210.png)

You can just click download now you're happen to give me a tip if you feel like donate financially。

 but if you just want to download， just click no thanks and you can download each of the days as one to help you。



![](img/25984fe835474479d1617bc0acadfcd6_212.png)

![](img/25984fe835474479d1617bc0acadfcd6_213.png)

Yeah， the game is almost done。 It's really really close， really close。

 I think we really should can put to go， I think， now， Let's see。😊。



![](img/25984fe835474479d1617bc0acadfcd6_215.png)

![](img/25984fe835474479d1617bc0acadfcd6_216.png)

And if it's good to go， you'll be able to see， oh， man。



![](img/25984fe835474479d1617bc0acadfcd6_218.png)

Not yet。Let see。

![](img/25984fe835474479d1617bc0acadfcd6_220.png)

Well， did I compiled the game？That a cooker。So we set。File memory， and then we offset that。



![](img/25984fe835474479d1617bc0acadfcd6_222.png)

I see。To use the SDL， no， in this game， we're doing everything ourselves。

 So this is our platform layer。 so when we need to create a window。



![](img/25984fe835474479d1617bc0acadfcd6_224.png)

Create you know， we call the Windows version create window E X A。Where we need to draw。

 we don't use OpenGL in this game。You know， us do the renderer。

We do the rendering ourselves and we do like bit maps， we do rotator rectangles。We do also end。

 we do， yeah， this game has come a long way， man。It's kind of interesting because it's only been like 20 flash streams。

But we've done a lot of stuff。

![](img/25984fe835474479d1617bc0acadfcd6_226.png)

And you can learn the whole thing。And if it's too fast， you can also watch the tutorials。

 which are more like step by step approach， not like a crazy。



![](img/25984fe835474479d1617bc0acadfcd6_228.png)

![](img/25984fe835474479d1617bc0acadfcd6_229.png)

I'm going to sit down and program like crazy Ab。Let me try loading again。The file location 208。

That looks all right， Let's just see how much assets。We have 49 assets。Okay， this looks about right。

So the PAC file。So it's GA， then we have version one， and then we have 49 files。

First one is that 208， second one。Is that let's see how much is height。This guy。Yeah。Okay。

 so this is correct。Now， if we subtract。HThis is weird because if I increment this guy。Yeah。

If I go to this address。Oh if I go to this address。I see， I'm really DPC+ plus。Yeah，你呃。

If you love it。Then it's awesome for you， man。This is correct， though。This is 0。Oh。

 because I guess got the whole thing here。YouGo zero， man， this is correct。

But why is he trying to read？Two bites if you try to read。This。あ。Yeah。诶。Is this weird？Why is this。2。

7， because this is 0。Should read like two guys？First one is zero。Second one is。

I'bably doing something really stupid here and I don't see what。Yes。

Touch the first time your Mac bright for it。Client。So respond to theization， awesome man。

 doing client work is a great way to get a lot of money actually because。

People really need good programmers， you know I'm finding that。先睡。

Things that wouldn't do like game programming。Which is really hard when you go do like an enterprise software and stuff。

 which is way easier。U you can do like some really high quality stuff and the clients really like it。

 you can do like really fast and really high quality。That's what I'm okay。Not the problem。是。😊。

Let's see， whereas since I forgot acid loadry。

![](img/25984fe835474479d1617bc0acadfcd6_231.png)

The problem is we should be referenced after we do this。F fell in love with embedded stuff one week。

 I think I would also fall in love with it if I actually do some embedded programming because I really like the idea of it。

 I really like it。But I haven't done it yet， the client has the next budget from me already too exactly。

 that's what I mean， man。If you do like。Quality stuff。

 you are going to get a lot of projects and a lot of money。

And if you do like game programming and if you migrate to like enterprise software or embedded software。

 you're going' to be able to do like really faster and really high quality stuff。



![](img/25984fe835474479d1617bc0acadfcd6_233.png)

I think。So I think we found a mistake。Very stupid mistake。Okay， now we have a problem。Oh。

 that's a weird problem。First color， what？First color is such a weird number。So we got colors。

 color count， first color。Mual starting color， I think we are probably writing more than we should。

Pretty sure。Pretty sure。The work conditions you gave button should be the worst should be worse from whatever yeah。

Game programming is a harsh environment， exactly， I haven't worked on a tripleA game only on indie games。

So it's different， but still is's a lot of work making games it is really。

 really hard I mean look at some games in the critics exactly you know the way I'm kind of thinking about it now is that I do like random software。

😊，For money and games for fun because they got the best of both worlds in this this way。

 so I don't work myself to death making games。And have a really hard time making money because makingdie games is as a lot hard work man when I is my big game。



![](img/25984fe835474479d1617bc0acadfcd6_235.png)

![](img/25984fe835474479d1617bc0acadfcd6_236.png)

Which the。This game， I worked three and a half years for this game。

And I think it turned out pretty okay， I think I really liked it it's actually today。

 it's been two years there released it。Today， exactly， 15 of August。

 being two years that I released this game。呃。So yeah， and after three and a half years。

 the game didn't sold anything at all。And a lot of people liked it， a lot of people didn't like it。

 but it was most positive， like 81%， it's pretty cool， especially for my first game， first big game。

But I don't know I mean it' been like another three and a half years just to build another game and try to make money out of it。

's really crazy。Cool yeah thanks manam this was really really hard work we used the own Ri engine to create it and we did like motion capture for that we managed to a motion got a studio for free for the game and so we recorded all sorts I was the actor for the game we did all sorts of fun stuff。

😊，And yeah。It's really crazy， but if I wanted to try to do this for a living for real。I don't know。

I don't know， that'll be really， really tough。I wouldn't probably do games this size yet I to get I want to get to the games this size again。

But especially now that I'm doing this as a hobby， I really want to go smooth， in a way。

 I will buy it thanks man， it's really cheap， it's like 1110 bucks， 10。

 this is in Brazilian of Ha ice。

![](img/25984fe835474479d1617bc0acadfcd6_238.png)

Which is funny because the BrazilianI is just like。One fourth of the dollar。

 but you can buy for half the price year or so。呵。😊，Yeah。😊。



![](img/25984fe835474479d1617bc0acadfcd6_240.png)

Okay， let's just。Let's just go back。The game。And let's see here。 When we load。

 let's just make sure the cooker。They we're doing everything correctly。

 so the first guy is zero then。The last bitm is the last guy and then we do like the last bitmap plus one。

We don't need this， honestly， then the main menu is the first sound。

And then we do all the other ones and then we do the last sound， oh。

 because yes it counts one too much， yeah。Yes asked it。 Well， really。I think this is correct。

Make embedded and your earn 125k minimum with our six views， exactly， man。啊。That's the thing。

You can earn a lot more money， working a lot more productively， and not predictably， I mean。

We can ship a lot more features because games takes a long time to do all all the features and stuff by doing non games。

 So that's what I'm doing。 I'm not doing valuables。 I'm doing like。😊。



![](img/25984fe835474479d1617bc0acadfcd6_242.png)

Autom automationation software。Which is pretty cool。And。Oh man， so now we run， come on。What fuck man。

Don't running， I don't know， I think I just forgot to compile。你。



![](img/25984fe835474479d1617bc0acadfcd6_244.png)

🎼如果。Your game desktop brings your executive continuous mind on this level， yeah。



![](img/25984fe835474479d1617bc0acadfcd6_246.png)

That's the spirit。Okay， now the same thing we did。For the。

 I wonder if you to find a job at a level without a degree on your resume， though。

 that's an interesting question。Because I don't have a degree。And。But I I work like freelance。

 I don't have a job per se。I do like。Random work I found， I find this area。

No one ever asked me if I have a degree or not。But if I try to get like a corporate job。

 maybe maybe that would come in handy， but I don't know， man， there are so few good programmers。

That people don't care if you have degree or not as long as they're a really good program。

 but they have to be a really good one， not just the program have to be a really good one。Yes。

 I I really don't care about a degree I almost got it， I spent like like two years on college。

 but it's not really my thing。It should be toldwed。Loaded sound。

Let's remove all these loaded sound stuff。Brick and the hits。The next sound。Play。Yeah。

I completely gave a fuck about school because I fixed computer ready at age or eight exactly man。

 I guess if you're really good shouldn't be a problem， I mean， yeah， it shouldn't be a problem。

 but except for like really corporate jobs， then I suppose it will be a problem depends on what your goal is。

😊，Yeah， man， I mean， school， not only's really expensive， I mean。

 in Brazil's not nearly as expensive as it is in the US and Canada stuff。But still， I don't know。

I don't know， it's really， really expensive。So let's see asset loader。Now let's do some。Sound stuff。

I have a loaded sound。And we're going to do sounds。And this is like the last sound。

Mine is the first sound。That one。Correct， the last sound。Let's say last sound is like zero and one。

1-0 plus one， yes。They hide their stuff behind me eating graduates。

 free minds would instantly realize what's going on。That's why corporates don't like free minds。

You have a point， man， I maybe see your point。I really do。Asscept loader。

So I just probably do like a get and do like get sound。Yeah， really。So， you can't like。It sounds。

Plus， I'm going to do asset minus the。I really， I really know why see。See sharpen Java is。Advertised。

It's only because it's comfortable to go to just mention nothing's for free。What it mean exactly。

 I'm not sure I follow。Get sound。Sounds。Readuny virtual machines。嗯。😊，Oh。

 you have no idea what they do， yes， okay， now I know what to mean。Yeah， man I mean。This whole thing。

 this whole idea of getting away from the computer。I don't know。I。

I think if you're programming the computer， you might as well know what it's doing， right？

That's like。Basic thing。Its proprietary hidden， okay。Oh。

 so you mean you have no idea what it's doing in the sense of like。

The corporations that own it like Microsoft and stuff。That's also a huge problem。So bricks sounds。

So we' gonna do a。Break1。Plus。Rranandom integer in range sometimes。Y， our article。

 this name is not just a joke， Yeah， dude， I just watched the YouTube video about it。

Uh like the origins of Oracle and stuff， how I was tied to like the beginning of siliconicon Valleyion stuff。

😊，Through some shady stuff happening in these big corporations， man。

That's why I like doing like small freelance stuff for programming。This way， bricks。うん。😊。

I'm going to hardco that to life four。Yeah， they don't， they don't play around， man， these guys。

And you also work a lot， it's not only in games industry， if you work like for these huge companies。

Even the idea like to push and create like。Patentns and stuff。Just the same thing。Hit sounds。W。Coldd。

Based on information and horsepower， based on every mobile phone existing。

 they can get great convert transitions。You mean transactions？Control global transitions。Logistics。

 okay。Yeah， and， you know， Amazon is really， is really。It sounds。

Amazon is really you not playing around also when he's trying to get that market share。Right。

 in terms of。In terms of like。Controlling where people buy stuff and what people buy。And they may。

Start game sound。给。Nobal control， yeah， they get a lot of information there。

I guess for the good for the normal guys like us。They have so much information that they have a huge time。

 a huge， hard time figuring that out also because。They have a lot of stuff， a lot of people working。

There。Old sound。They have a lot of people working there。And so everything's really。

 really complicated。So I'm not sure how walls sound。Let's play a role。Play a role， okay。

I'mNot sure how well they're going to be able to type that grip if they want to。

Because' the sheer complexity I mean。So I suppose there is a bright side， right？Amazons paying 0。

1 taxes for you， I would go to jail。Only if they find out， right？Interface。Yeah。

 see the problem of doing。The system later on like we're doing now， so first break。

Is that we do have this。This kind of work， boring work of。Going back。And。

We're doing a lot of stuff we already did。But it's worth it because now we know exactly what kind of assets we want to program are。

啊知。Get sound2 main parameters。To gets sound。Our well sc concept hasn't to be complex in fact this year and simple。

It is。Yeah， but these big companies， I don't know， man。

 they look pretty crazy complex to me from the outside， I suppose。So I'm not entirely sure， right？

Because I haven't worked on a company like， oh， even people who worked there。

 they probably don't still have the big picture， right， and that's the biggest problem。I think。Aload。

So。Yeah， but I don't know theres。He got to a point that maybe not even the big shy guys。

Can I easily understand the whole thing all you can do like is to ask like the department leaders to do more stuff I suppose。

Doesn't we all live on a stage we do， man， we live in a circus， right？But that's good。

 that's why it's so fun。Loed MIdy， okay， so we done it。You're going to remove all these guys。

And these guys as well。These guys， okay。ame then we play it。ok。😊，This looks good， I think。

We're going to do the same thing here for the sound so。嗯。And do last。Sound。Minus。First sound。

 plus one。Ile plus。Circus， yeah， that's my word。Exactly， man， that's why it's fun， right？

Because it's really so crazy。😊，That we can't take of that too seriously， right。

 that's why making games is fun。Like the。The epiphany of not taking things seriously and just doing like simulated。

Crazy Rose that， you can play around with it。But it's also nice to have an understanding and see the whole thing。

 once you do have that understanding， that's a pretty cool thing。Blowom sounds from。Oh， but we did。

 yeah。This looks perfectly。Some。Cold never lies to me。 That's why I love low level code。

It does exactly what to tell do， right， That's why the fewer libraries I use。

 the better I like the code。😊，And the more for fun the project is like this one。

I'm going to use pretty much nothing， you know， acid loader， like load sort of from back。

Because you can need dig around and there's no like secrets。Right。That's a nice way to put it。

 I don't think I've ever thought about this but。No secrets from the code， load sound from pack。

So take an asset。It's going to be a loaded sound。The result。And then， let's see。

We're going toload the asset。嗯。I'm going to load in line here， or maybe。

I'm going to take a pointer to the S format。This way I can just make sure。Yeah。Yeah。

 I think I'm going to do it like this。Asset format。She。beです。Okay， this way。

 we're going to try to load the asset to T。We can pass like zero because we don't care and in here。啊。

Here。Assit format。I can you like。Format。Then we do like if the asset format。Is asset waveave？

St asset。Forormat。喂。😊，I mean， okay， I'm using SDL for graphics。

 but I would rely on third party socket。Yeah， I mean， SDDL is is probably fine。 Okay， yeah。😊。

but I really like being able to。Doing as close as。What Im supposed in terms of like the raw material。

 the raw API as I can， so I really like that。Let's do what else if。Asit format。Lets do OGG。

And then we can also， we can also。Asert， if it' send image， they want to do this。

When we load from the pack， I'm going to load like format。That the format here。Now we assert。Format。

It is the asset format。建议。Yeah， and here this。不是。This is invalid code。い guysくね。Okay now。

And we should be able to load the wave and the。The old did here。Now， you ate。Yeahep， like this。Yep。

 no way performance in abstractions is horrible and on the rate， exactly， man。

 abstractions is a dirty word。I mean， you have to be able to compress the code。

 right to make it manageable。But not for its own sake， right？Exactly。Lo town from Pe。

What was the problem？哦，别什没有。搂了下。Just see if the problem is。Yeah， we don't have that。Oh。

 because it's lowercase。I suppose。Yeah。So let's go back， we have to finish this later on。

 but let's get sound。想 gameplay。ユせ？Main music。え。The menu music。This is this。Sign。It's forest fields。

It's culturalized scripts with Python with everything and GPU of this person。嗯。

Is it really what I like to tolerate a rational Yeah， dude。

 this is this is I had a similar experience that I profiled a script language。😊，I was trying to。

Together， the script language could do in terms of like libraries and stuff。

But just the amount of time he spends trying to understand what you wrote， it's just the deepest。

 I just wanted to do a specific thing。Machine language is awesome， I mean。

 and if you can generate that for the user， that's what matters， man， Yeah， 7% depends on pars。

 exactly。😊，And that's。That's really weird。If people don't find it strange。 I mean。

 they could find it toler because that's a little bit subjective， right？

But not finding a little bit strange is strange in and of itself。Yeah。亲了亲。Oh呃 comment。

See what else far field。Start game， and we also have to check。After we。That's where finished。

And I'm going to have to play the game for a while to make sure that no sound got a。Swapped。

Which I'm pretty sure。Some sounds must have gotten swap because。I've been editing a lot code。

A lot of code wall。天包。The problem is everyone programming Python is authentic if you tell that fact。

People got to finish too much， dude。She all a circus， man just。It's just for fun。

 take that non seriously。I don't take hardly anything seriously at all。You just be told。Yeah。

 it's kind of hard to get me offended because。I know you shouldn't really power up。啊这样。

Surely you take things too seriously， man， see how the word is right now。

 If you try to to make sense and approved， Yeah have multiple times。 if you try to。

 if you try to make sense of it in a serious way。 Oh。

 this is meant to do this and this institution and all that stuff。 you're gonna go crazy， man。

 You gonna go crazy。Completely crazy， lose life， I don't remember doing oh we did lose life。

They were crazy and we're going to lose the joy。Of life， I suppose。Uninitialized。

 so let's initialize it。I don't say I would never use P， but I tell some facts， yeah。

 that's the thing， man。You can use whatever it's best for what you need at that time and another interesting thing。

Then most people who really understand like game engine programming and stuff would probably advise you to start using a lot of libraries。

But in a way that you， when you get deep into the project， that you can get them out of the code。

 like we can probably， I'm probably going to do it this day。

 then probably take the PNG reader out of the game。

It's going to be way better in terms of memory and like usage and stuff。啊。So yeah， that's the thing。

you don't have to not use it， but you have to know what its weaknesses are that's for like pretty much anything like I compile this like a thousand times for some reason。

 let's see if we have sound， let's see。

![](img/25984fe835474479d1617bc0acadfcd6_248.png)

Okay we crashed expression zero？As the format is0 when I try the reading。



![](img/25984fe835474479d1617bc0acadfcd6_250.png)

Sounds 0， okay。啊。This is wrong。 This should really be like I plus for sound。That's engineering。

 exactly。

![](img/25984fe835474479d1617bc0acadfcd6_252.png)

Jonathan blow love saying that。You know that people don't do like serious engineering anymore。

Just because they're kind of afraid of。Not lying to themselves， I suppose that's the 49。



![](img/25984fe835474479d1617bc0acadfcd6_254.png)

嗯。That's the huge one of the。Those serious problems lying to yourself， man， use we do。

 we do use multi threadreading for for the audio， the audio runs on a separate thread and we also do the OGG reader in another thread actually we implemented that today really。

We implemented that today and that was pretty cool。That's pretty easy because we did a job system。



![](img/25984fe835474479d1617bc0acadfcd6_256.png)

Let me see， I think it wasn't day， I don't know which day that was。11， 12， on day 12。

 we did a job system for the game。

![](img/25984fe835474479d1617bc0acadfcd6_258.png)

And then on the day 13， you use that on the audio， and today we use that for the OGG reader。



![](img/25984fe835474479d1617bc0acadfcd6_260.png)

What's with input event handling？

![](img/25984fe835474479d1617bc0acadfcd6_262.png)

Not， not much， really， I mean， I pick Windows messages。

Then I process like if we hit like a key that we care about。We care like for the youk left。

 right up downscape。And then I just said this is mystruct and I said mystruct is down to is down and changed。

If it's change or not。Yeah， so that's the basic。Input system we have and it's kind of basic。

 but it does everything we need。If we need it to be more complex， like accepting more than one。

Movement per frame， we could probably change this when changed。To like half transition and stuff。

But yeah， it's pretty easy。 And then we process the inputosing to gift to gain like a huge。A huge。

Strong I not a huge， but like astruct。With all the it needs so when I do like pressed。I can do a。

 like。Pressed button escape like this。 I can do like is down button up。 Press button down。

I can do like left mouse button。You have a lot of lips on the side， made yourself。

 I have a whole Github with examples I'm kind of building that。Progressively， so I don't have。Yet。

 I mean， a full thing， this OGG thing that I in today。

 that was partially the lip that I did with a lib from Sean Barrett。

 I kind of improved that a little bit。Not improved in the sense of making it better。

 improved in the sense of making the interface work better with my other libraries。

But the idea is to keep getting a。Mar solid engine。So to speak， and after this game。

 I'm going to spend some time on really solidifying the engine aspect of the game and not just the game。



![](img/25984fe835474479d1617bc0acadfcd6_264.png)

Okay。We are getting somewhere， I suppose。But we have a huge sample。Sound。嗯。What sound is this？



![](img/25984fe835474479d1617bc0acadfcd6_266.png)

Loing， a looping sound。Oh， yeah， let's see， it's the sound。Try it。Openening the windowで。

So get a little bit of wind。To make an example for everything you will need later and collect them。

I was astound after one year how much I reused。You know， this is really true。This is oh yeah。

 our code is really bus。 This is really true in the sense that。Oh， because we haven't finished it。K。

 that makes sense。It's really true in that sense that you really use a lot of the base code。

And the more you build it solidly， if that's a word。Rbustly， I suppose。

The better and faster you'll be able to do projects， and they'll also be pretty robust。For。L on pack。

 a low sound。Maybe I're not going to take the PNG out game， I don't think I would volunteer here。

 to be honest， yeah so。Result will be equal to load。Wave from memory。

Right so I'm going to take a string。Which is1 well。Collect sound。And the same thing here。

 load OGG from memory。Maybe reliable， robust， whatever， yes。Exactly。Okay。😊，Our sounds， okay。

 now it's run a little bit。 the first sound is really problematic。The other ones look。Look， okay。

 expert。Let's run。 Let's run through， through the。

![](img/25984fe835474479d1617bc0acadfcd6_268.png)

This guy， I's see。

![](img/25984fe835474479d1617bc0acadfcd6_270.png)

So we're trying to read in the assets nine。Is that correct？Asset9， which is。



![](img/25984fe835474479d1617bc0acadfcd6_272.png)

八？Bookooker。0， one， two， three， four， five， six， seven， eight。 Oh this is Ron。嗯。😊，Let's see。

What numbers is the logo dark？See this scanフ。Logo dark is eight。0，1，2，3， part， thanks， said。Oh。

 seven， eight， Oh， this is correct。So nine is supposed to be the menu music。



![](img/25984fe835474479d1617bc0acadfcd6_274.png)

AsIf many music is9， it is。So yeah， I suppose it' very good。And this is a OGG。

Yeah right now we're not doing that a sync， but we can work on that later on。Sample count。

 channel count， sampleple rate samples。Well， this looks perfect， I think。



![](img/25984fe835474479d1617bc0acadfcd6_276.png)

So， sounds。Yep， let's do the other one。And let's keep doing them。You know what this looks perfect。

I see when we screw that up。Here。When we do the。Here we screw that up。When we play the sound。

 maybe when we get the sound。

![](img/25984fe835474479d1617bc0acadfcd6_278.png)

We already screwed that up。That's really weird。I'm going to put a data breakpoint。

Daatabre points are pretty useful， sounds， zero dots。Co。The last bitm。Is the logo in dark？

First sound is9。0。eight。I'm trying to load bitmap eight。Reach is the lower dark。Oh。

 didn't have array。Bit map array。It's not big enough。Should be lessb than that plus one。See。

 last and count are tricky words。

![](img/25984fe835474479d1617bc0acadfcd6_280.png)

It's easy to get confused。系啊。Control， 100% control， Yeah， I man。I also think it's a lot more fun。

 to be honest than C++， because you can just take a look at the code and understand it pretty easily。



![](img/25984fe835474479d1617bc0acadfcd6_282.png)

🎼エろs！Awesome。And since this project is mostly about Had fun， I chose to go with C over C++。

I've been working， oh my God with MatLb。For the last year， and I'm so sick of it too high level。

Exactly， ma'， when you give up。Understanding of the program。

And the program is about making the CPU do stuff， right？

That's what the program is about when you give that up。You not only lose productivity， I think。

But you are really in risk。Of making the program have like weird bugs you can't ever solve and thats。

Not ever fun， right？Yeah， I feel it。Yeah，But sometimes you gotta do what you gotta do right。I mean。

 I shipped a PS4 game。Using like 99% of Uns visual script。

And when I needed to go down and like fix real stuff。You when I was about to ship the game。

He was really， really proud of that。🎼But， well。I had to do what I had to do。

 and I managed to ship again。

![](img/25984fe835474479d1617bc0acadfcd6_284.png)

I want to see framed difference。O can try the game on release mode Okay， oh， but it is locked。

 the frame rate I cannot lock， but it's probably going to break the game。



![](img/25984fe835474479d1617bc0acadfcd6_286.png)

Quite a lot， I think。

![](img/25984fe835474479d1617bc0acadfcd6_288.png)

So you're not going to see any difference at all because it's locked。At 60 frames per second。See。

 so it's exactly the same thing。

![](img/25984fe835474479d1617bc0acadfcd6_290.png)

But I can try unlocking it just for the fun of it， that's probably going to break things like particles。

 they are frame rate dependent。So yeah， that's not sleep。



![](img/25984fe835474479d1617bc0acadfcd6_292.png)

Let's never sleep。The menu is menu is going to take more time to run than the rest of the game because it has big bitmas and stuff。



![](img/25984fe835474479d1617bc0acadfcd6_294.png)

So yeah， the menu is two milliseconds per frame。The game' is like 1。2。Yeah。

 when we have like more particles， it's probably going to take better a little longer。你。

And so the particles， they look different。Because we smell like one for frame and stuff。

It's easy to fix， but since we're going to be locked anyway。We don't really care it。Yeah。

 that's pretty cool。Yeah， see you've got up to two。🎼あ。But it says smooth。

Like the wobble and it's pretty smooth。

![](img/25984fe835474479d1617bc0acadfcd6_296.png)

Maybe， maybe if you well， you know what， I think it's hard coded the 60 fans per second thing。

The target Dt。Maybe we could。You could get the user refresh rate。Next time around。

That would be a useful thing to do on the polished glass。嗯。what's happening？Hey man。

 I've seen your Danza D channel。It's about making a game see from scratch program and asset system。

You're the man I'm going to design an Nikco relay for your channel really dude， they'll be awesome。

The trail on the ball looks better。 Yep， have a look on my profile picture。

 science technology is one of the best games。 I will， man。 Thanks a lot， awesomesome。😊。



![](img/25984fe835474479d1617bc0acadfcd6_298.png)

The thing is， we could have that behavior。With a lower frame rate。

By having like this is the ball and this is how much you've got it went in one frame。

 we could insert more particles and lup。This position， thatll be the better， more robust way。



![](img/25984fe835474479d1617bc0acadfcd6_300.png)

The Chinao。I don't really think it's worth the trouble because it's kind of finicky getting these lup and stuff。

T 100%。So， and since we don't want to fry the user's CPU， right， just to run at。

 I don't know when we were running at one and a half， how much is like one and a half？

 it's like one over one and a half。600 frame per second， is that correct the math， I think so？

So it's not really worth it。To run that fast。

![](img/25984fe835474479d1617bc0acadfcd6_302.png)

But。Yeah， I think it's pretty responsible。 We could probably lock that at 120。

This looks pretty a response by think。Responsive。It's also not crazy， right， used。



![](img/25984fe835474479d1617bc0acadfcd6_304.png)

Could't make the part was a bit righter though， I think。Article。Partargo trail sp。Life。Yeah。

 well that's right me。

![](img/25984fe835474479d1617bc0acadfcd6_306.png)

How many lines is this all together， not including libraries， let's see， man。😊，来奇艺。It's like， well。

 that's it。This program is really slow。To count the lines。

 I think this is just some configuration that I should be doing。But yeah。

 because it's running for like the visual studio stuff。Yeah。So including libraries。

 you have 13K of code。😡，Expoing libraries。Well， it's not that much。3。7 k lines of almost 3。

8000 lines of code so 3700 lines of code and if we include blank lines and comments because this thing doesn't。

If we include it， we have like 37。Four。What， no， that was wrong。Well， that's right。Okay， we have 5K。

So we typed on stream 5000 line of code。whichch is is okay， I suppose its a nice game。Nice size game。

And in these three files are libraries， I only remember two files。



![](img/25984fe835474479d1617bc0acadfcd6_308.png)

So I got the OGgene Porter。七。Yeah， the image in the waving part， yeah。

 the odd so we have three libraries。For loading stuff and they have like9000 lines of code and if you add these guys。

Have like 12000。It's pretty good， yeah， I think that was pretty good and you can watch all those 500 lines that code being written on YouTube。



![](img/25984fe835474479d1617bc0acadfcd6_310.png)

Oh， and that guy that offered to make the cover， I do have a cover on YouTube。I made myself。

 I think it looks pretty， pretty cool。 It's from my my big game， the one that's also on my avatar。

 this game。😊，Yeah， look at the hat。It's pretty cool。



![](img/25984fe835474479d1617bc0acadfcd6_312.png)

I really like that game。It was three and a half years of my life after all， I better like it。Okay。

 so I think we should be reckoning up。Let's just try to see the size that we have。

Evaluate whether or not。We should do the。Yeah see this is 5。59 megabytes。In terms of data。



![](img/25984fe835474479d1617bc0acadfcd6_314.png)

Right。Of the game， and we're going to try to run the game。Oh okay， you know it's not。

 we forgot one thing when we changed two loads from memory。



![](img/25984fe835474479d1617bc0acadfcd6_316.png)

From the assets loader。Memory， where we did the。Okay， we did the OGG for memory， it's not a sink。

So we have to change that。Okay。😊，So yeah， we got to change that let see。

So right now we pass a pointer to this guy。This is going to really screw up。Well。

 now it's going to be if I guess load song。Memory then I pass， whats that sounds plus I as a point。

Yeah， it's not returning。We do a pointer here。And then we don't need to zero that。

Then here we do the。Sound equal to this。Can we do like async？O G for memory。

 and then we pass the pointer to the sound。Oh， we already have a sound。Let's call these。

So this would be the result。It's pretty good， yeah。See results。行。And we don't have the AC。

 so let's do the AC load ODG here。And these are sounds。And let's do I think from memory。

Do load OGG from memory。And yeah， So this is a string。S。Then we pass a pointer to the string。Then。

 here。What we do is training pointer data one， a little bit sound data2。Sound result。V。



![](img/25984fe835474479d1617bc0acadfcd6_318.png)

Yeah。Perfect。Perfect， at's see。Okay， so we little bit fast， but we crashed， so that's no good。

Odi Porter。嗯。We got pretty deep on the call stack。Open memory Decode from memory。



![](img/25984fe835474479d1617bc0acadfcd6_320.png)

哦， we didn't call we didn't call D心。

![](img/25984fe835474479d1617bc0acadfcd6_322.png)

Oh， we did。不知。😊。

![](img/25984fe835474479d1617bc0acadfcd6_324.png)

![](img/25984fe835474479d1617bc0acadfcd6_325.png)

Oh， because we are optimized， it'll be hard to debu。It's not build the optimized build。

 or this is the the cooker。

![](img/25984fe835474479d1617bc0acadfcd6_327.png)

WithThe game， let's see。Okay。So we are here on the load from memory， this guy。

 let's see if it's a balanced strain。And it's not a valid string。嗯。😊，Let's see， the load。Yeah。

 you know what， I have to do a string copy and not。



![](img/25984fe835474479d1617bc0acadfcd6_329.png)

And not this string， I's see。And does string itself。

I'm going to take a bath to see you later one question。Okay， let's see。Anchrop frame， not a ponyard。

嗯。Recall。Because this guy goes out of scope here。This is not going to work How many monitors we use。

 I used you one14K monitor。So I can go all the way from like here， so see。Let me see。

 I think I can show you。Quickly， and wonder。

![](img/25984fe835474479d1617bc0acadfcd6_331.png)

Oops啊。This is my full monitor， so youll see I stream this part。

And I keep up with chat here and then I say have OBS here。



![](img/25984fe835474479d1617bc0acadfcd6_333.png)

So yeah啊。

![](img/25984fe835474479d1617bc0acadfcd6_335.png)

唔千。Yeah。😊，One monitor， I really like having a4K monitor， really do， really do。

I used to have like two monitors。I tried to one wide monitor， but farK is the one I like the most。

 I think。So what what's okay。It better the point to the result。We need a train。

I think I may be a bad person at this point well。If I just pass the string here。想。嗯。う。Yeah， see。

 I'm not entirely sure。I'm not entirely sure how to solve this。



![](img/25984fe835474479d1617bc0acadfcd6_337.png)

Because this。'mNot worried when I try reading。来い。Data 1， C。What is this supposed to be？

It is appointed to a string， but if the string were not of scope。The point is all crazy。So。



![](img/25984fe835474479d1617bc0acadfcd6_339.png)

If I just pass the string dot data。And I do like。Well， we could do three well， you know。

 you know that saying in for a penny， in for a pound since we did two datas。

 which was this crazy hack， we could do three and build a string here。I don't know。

 I'm kind inclined。I'm kind inclined to do this。Let's do this data。I'm not sure， kids。

I was away we knew answered。I have one4K monitor， I really like it， I even showed。



![](img/25984fe835474479d1617bc0acadfcd6_341.png)

How呃。So yeah。This is what I see。And this is what you see。



![](img/25984fe835474479d1617bc0acadfcd6_343.png)

秀烟。Once far I came monitor， pretty cool。I really like it。 This is like memory and the size。Yeah。

I tried， I used two monitors for a while for a long time， actually when I use like on Rio engine。

 two monitor is way better because it's easy to snap。Different views。

 since I mostly work on one view。Sometimes I really like to make like the editor really tall and then I do like the debugger on the top right and then the bottom left。

 the bottom right the game。

![](img/25984fe835474479d1617bc0acadfcd6_345.png)

Also pretty cool。Yeah， those are some of the nice setups。

 I even have an image of that if I'm not mistaken on Nitrio。



![](img/25984fe835474479d1617bc0acadfcd6_347.png)

For the other game， I did the open source Sp that you guys can download the source code for。



![](img/25984fe835474479d1617bc0acadfcd6_349.png)

![](img/25984fe835474479d1617bc0acadfcd6_350.png)

Yeah， so this is a pretty cool setup I did for a while， it's a 4K monitor， so this is the editor。

 the debuger and the game。For a kids， a lot of space， you have three wide monitors speed up。

 but you do them， you keep them side by side。

![](img/25984fe835474479d1617bc0acadfcd6_352.png)

![](img/25984fe835474479d1617bc0acadfcd6_353.png)

はい。Let's say like this。Stren enough training or peripheral vegan， man。

But the thing about why monitors that I found， I did use there。A 2560 by 1080 minor for a while。

When you called， it's really about the vertical space， really。

But I'm not sure I haven't tried telling that vertically that that'll probably be a bit too weird。

 I think the4K was a nice。

![](img/25984fe835474479d1617bc0acadfcd6_355.png)

![](img/25984fe835474479d1617bc0acadfcd6_356.png)

I don't know， middle ground。In this sense， okay。Let me try debugging this guy。

Let's see the data one should be a string， let's see。



![](img/25984fe835474479d1617bc0acadfcd6_358.png)

It is OGG this is perfect so yeah I am going to do that hack sorry guys。

 we did the the ugly hack first common， so we might as well do the ugly hack again。



![](img/25984fe835474479d1617bc0acadfcd6_360.png)

So we're going to pass three data pointers。And at this point， I should probably think about。

About structuring this a little bit better。But。Since we are almost done with this game。

 I think I'm going to leave that。In the other game。To structure this better。So we don't have to。

 you know。So we don't have to。The3。So we have to think about memory for analysis we did pretty much everything pretty easily。

We even do the stack allocator earlier today。So。As of data， as of size。O。😊。

And this is going to pass the data。And this will be the。所该。Pameter 4。Before I got the client。

After I got the。跟定个别人急。Oh， Du， can I share that on stream， I think I can， right？That was pretty cool。

😊，Nice workstation， man。Looks awesome。Y， okay， so this is before you got a client。

That's pretty cool already。And this is after you got a client。

You didn' change the you didn't change the desk， I suppose。Awesome， awesome， awesome， man。

 really cool。Oh man， see it's really， really cool， man。

 you have to you have to learn how to make money programming because。

Because it seems smaller and exactly the table looks smaller， to be honest。I also changed my。

 but I don't have an easy picture now， but I did change my workstation a lot when I started making money。

With programming and we don't have to be afraid， man to make money programming Missmat for parameters four。

Well， let's just。Ca that as a voicer pointer to a few arguments for call。One more zero。

 and I think now and I think now we have 100% bootss build。



![](img/25984fe835474479d1617bc0acadfcd6_362.png)

I think now we are， let's see。🎼Okay， we shouldn't be able to。



![](img/25984fe835474479d1617bc0acadfcd6_364.png)

Okay， let's see how much it takes to load， I'm going to go back to the optimized build。

The client bought the monitors from me before even started， really。



![](img/25984fe835474479d1617bc0acadfcd6_366.png)

That's awesome。It loads super fast。Super fast， I can't really complain about E Lo。

 so I don't think you're going to get rid of the PNGs for now。It's fast enough for this game。

That transition is awesome。This one， it's really cool as well。🎼This one's really cool。Oh。

 this one's not that。🎼That well。🎼And。Let's see in the spacing video this part。

 that's pretty cool as well。What。Dude， this is crazy fast。

And I think we lost a little bit of people did you hear that stereo。

Would we've comment it on our audio system， a penny system？

And it's so easy to use that it made pretty much everything to stereo that was awesome the audio system。

Nice effects， thanks man， that was the idea man， the idea was to make it through really nice。

And I even to read it about the progress and it's pretty cool because the game looks pretty boring for a while。

Because we focus on gameplay for some time。But where have we got teams play？The actual effects。

 that was like。Huge progress， huge progress。同意。い？

![](img/25984fe835474479d1617bc0acadfcd6_368.png)

You're really talented， thanks man， it also involves hard work， though。😊。

I think they kind of go hand in hand， the more your work。

If you show this project to a company you get hired， not sure want to get hired， though。

Before they see it。I really like the way I'm working now， you know。

 I kind of work part time doing client stuff。And part time， just doing crazy stuff for fun。

And I really like doing this stuff for fun。 And this game is really close to being done。

 really close。 Let's just review what we have。 We finished today the asset cooker。😊。



![](img/25984fe835474479d1617bc0acadfcd6_370.png)

And it's really， really awesome。 I really like the way we did。 Oh， there's like one small thing。😊。

Re small thing to do。Before we load。The pack or we really cleaned up。

 we deleted a lot of code from the game today that was awesome when we load the pack file。

Loowed here instead of doing this， because。You want to make your work good。Yeah。

Because instead of doing like this。In some platforms。The asset file may be in different locations。

 so I don't want to hard code in the game where the asset file is like maybe if it's in the PS4。

 it's in a different place。So I'm going to just like OS， get get file， get tech data。

And the OS will care about where it is。In the Wintry2 platform。When we read entire file。

Browing the platform common， I suppose。Yeah。I'm going to do an in line。Streng， OS。

 or I'll forget what this was about。Yeah， yeah， thanks。Get tech data。And then， here。

In a file I have right say file， which is also platform dependent。Deep bandit， right。

 so I'm going to do。VOS gap tech data。Same thing。And just going to return this。

So it wasn't a big change。In terms of structure of the code。

 but this makes it way more way less platform dependent， I suppose。Okay， well， 12 people， man。

 today's dream is really， really something。Your first decor looks cool。 Yeah。

 you mean like doing this thing in one line and this thing and another， I really like it as well。😊。

I think it's really easier to read like this because this is usually not important。

Pretty much everything is internal or in line。You put a return tag Yeah。

 and it's also good for comment。 So let's see if I have like a return comment like this。

So I like internal B32， and what does that mean， Well it means if we should sleep。

It's really easy to read， I think。Yeah。So let's just review what we have and where we are going。

We well， if we were supposed to review the whole thing， we might as well do it。

 right or on my Twitter。

![](img/25984fe835474479d1617bc0acadfcd6_372.png)

Or you can watch the Apple like a gift for the progress。啊次。See， that was episode one。Eptilode two。

 that's pretty cool。Ampl three now starts look like the breakout game， right。

 E4 we got better colors。And we have like weird collision stuff。E so before。

 we also start doing like。Pick ups and other game modes and we did this crazy two ball one that we cut from the game That was cool After five。

 we did the pun。😊，game and as you can see， it really looked kind of bad from the at this point and we also did space invades。

 there's like no particle system， there's no animation， there's no like subtle things。

But it's all progress right， you have to get the gameplay nice before you make it like crazy stuff and this is where we started doing the things yeah。

 we started doing like the particle system and we change the particle color。

And they're still pretty bad， oh， we also did some animations on the walls， see when we hit the wall。

 this animation， now I have a better particle and we also did the play movement。

 the first version of it。Oh， and the particles when the blocks destroys。

And then we change the size of the particlecode when we collide do something。

So now I start having more things， more interesting。Behaviors。

 see now the particles look pretty cool， see though that's where we rotate the rectangles so the particles can look gray better。

I love the wobble。 Yeah， the wobble is awesome。 And I think it's it got even Mark in one point of think。

 Oh， this is where we implemented。😊，呃。The bitmps。In our software rangeer。

 so we can see the power up and the power downs at this point we started doing oh。

 this was audio can we listen to some audio yeah。This was the first music。

 which was the other game's music。🎼You I met it audio in episode 11。😊，And then we started， you know。

 doing some cleanup minimal more audio first version of the menu and the movement audio looks pretty bad。

 sounds pretty bad as well。But that was the first version。Because in episode 15。

 we did the better version of the game and also started doing the safety thing if I'm not mistaken。

Do the productss stack up， they do， they do， they stack up both in time。

 like if you get the same power up twice， have you have it for twice as long。And if you do。

Same power up。 If you're different powers， you can do it like crazy。 And if you stack like the。



![](img/25984fe835474479d1617bc0acadfcd6_374.png)

The triple shot and a Com power up。That's really cool man。

 oh and I didn't get to show the transition。The latter transition， Oh see。

 I'm going to stack up the transition， this guy。Look at that， man。Look at those points， oh my God。

 I missed it。Hammer， it collect like three greens， doesn't tripleple the time， it does。

 it does tripleple。And it's pretty cool cool and you can see it's kind of hard to see。

 but on the bottom left of the screen， if you look at the bottom left， you can see the timer。

Ls me to subtle， it'sman to subtle， though。And you'll see， I have one triple shot。Oh， crap。

Space invade invaders。Sorry for my German。I don't know what that means， man。But you're excused。

 it's okay。I guess speaking Portuguese as well， what's like what to get success stuff that going cruise matter。

哎。It means just amazing。 Okay， thanks， Oh， we got two people from Germany now。🎼On screen awesome man。

Thanks， man， I like， I really like that people are enjoying it。I'm really liking the process。

Although making everything on live stream is really hard。

 I think next game I'm not going to do the whole thing live probably going do just are going to do just parts of the live stream。

 parts of it。There's going to do offstream， maybe do it like a tablog or something。That's right。

 Palm。Yeah。Where are you from I'm going to take a guess Pakistan No man。

 I'm from Brazil that was really far from Pakistan。I speak Portuguese， Brazil and Portuguese。

 put against aboutzeal。Brazilian man。Okay crap。诶。Dude， I really like where the game are。

 I really like it。Hes still。Proing， okay。说 tell你大家团跟他都这一边。😊。



![](img/25984fe835474479d1617bc0acadfcd6_376.png)

Okay。

![](img/25984fe835474479d1617bc0acadfcd6_378.png)

So that's the point we got。It's funny because my friends's from Pakistan and juststics is like you。

Well， last suppose my English is pretty good， right？Yeah， I don't have that much of an accent thing。

 I don't have a funny， funny way to speak though。Yeah。There definitely similarities。

You also have a friend from Bast man， come on， Oh just making fun now。😊，嗯。

So the roadmap for now is a Po stream。I'mNot sure we're going to do like one or two polish。

 I have a lot of friends all that's awesome man， have friends all around the world。

I do have a couple of friends from outside Brazil and the US， but not that many though。呃。

That's awesome。Okay， so the plan is next stream you're going to do a polish pass。

 a final polish pass， probably going to be a part one for the polish pass， I'm sure。

But have a few things to consider。I can make full screen launch prettier， more optimizations or not。

40 point colors are not we're not going to do these optimizations。

 if quit probably not make return the player's mouse cursor。I think I kind， yeah。

 maybe the audio thing。That means most of and then we're going to do the probably maybe we're going to do the OSS first。

That's the online of sub online subsystem。Online subsystem network is one of the most important things in the program。

 that's true。But my brother is a partner of mine on these projects and hes a commercial guy。

He' is in charge of making friends。And I've been charge in making code， I like that deal。

You never know where it comes something when you need a collaboration to product。

 this is exactly man， you do need to know a lot of people and especially to make money， man。

That's entirely true。And they don're going to release。

So that's the roadmap and I think you're going to do this maybe later on offstream just for fun and listen to you guys in some way are another I'm not sure kind of think about some ideas。

So that's the plan， that is the plan， I hope you enjoy this stream I certainly have enjoyed it。呃。



![](img/25984fe835474479d1617bc0acadfcd6_380.png)

You can follow me， well， since I open the Twitter， you can follow me on Twitter as well。

 I like posting like small gifts of what we are working on and my tutorials and stuff。

 because on YouTube， I am not posting all sorts of crazy videos not only the live streams we are creating now。

😊，We also have tutorials。Like step by step tutorials and those are pretty cool。



![](img/25984fe835474479d1617bc0acadfcd6_382.png)

Some jazz play in the background？And I also like draw some things to explain a little bit better。



![](img/25984fe835474479d1617bc0acadfcd6_384.png)

The concepts that I really program fast here onstream， I'm a social media guy。

 I'm not really a social media guy either。😊，呃。And I also have like whatnot tutorials I'm going to like a little bit about what our point her function。



![](img/25984fe835474479d1617bc0acadfcd6_386.png)

So if you want to subscribe to my YouTube channel， you're going to see all sorts of great stuff and when this project comes to an end。

 which is pretty close now。

![](img/25984fe835474479d1617bc0acadfcd6_388.png)

We're going to do Marco stuff， I think I'm going to focus more on engine and then're going to do open GL stuff and're going to do bigger games and 2D than 3D games。

 all sorts of crazy stuff， really exciting， really exciting times。



![](img/25984fe835474479d1617bc0acadfcd6_390.png)

And you can download the game on each other for free。

This game break Arcade in I need a new background kind of ugly compared to the new Ponggu one。

 this is pretty cool， I think really liked it。This for the tutorial one。

 this is the one that we're doing on live stream， you can， oh， now the gifts are working properly。



![](img/25984fe835474479d1617bc0acadfcd6_392.png)

Yeah。Pongguan is' pretty cool spa invade invades， and you can download the whole thing。



![](img/25984fe835474479d1617bc0acadfcd6_394.png)

Allday source code for free。

![](img/25984fe835474479d1617bc0acadfcd6_396.png)

but please apply for a company， no way， man。No， I don't like working like for a company with fixed time things like that。

It may be cool for us for some。For some for some time。

But I really get tired of doing the same thing all over again。Not sure though I'm when I do this。

 I like doing like client work。Part time programming and part time game programming that's perfect for me you can download the game and the source code anyone ever to give me a tip if you are liking this can support me or download the game no problem man it can do whatever you want the source code whatever you want with it hopefully we are getting close to the release and then it's gonna be really cool。

😊。

![](img/25984fe835474479d1617bc0acadfcd6_398.png)

![](img/25984fe835474479d1617bc0acadfcd6_399.png)

And we're going to keep you updated， hopefully next time we can talk more about the release。

Kind of works really cool because you don't do the same thing exactly。

I really like kind work and if I work like my ass off。

 I could do that pretty quickly and get rid of it。So。Yeah， I really like it。

And since my brother is a commercial guy， he keeps getting cool clients as well。

 so it's pretty working or pretty nice to this partnership。Okay， so thanks for watching。

 I hope you enjoyed it and I'll see you guys in the next live stream。



![](img/25984fe835474479d1617bc0acadfcd6_401.png)

By拜。
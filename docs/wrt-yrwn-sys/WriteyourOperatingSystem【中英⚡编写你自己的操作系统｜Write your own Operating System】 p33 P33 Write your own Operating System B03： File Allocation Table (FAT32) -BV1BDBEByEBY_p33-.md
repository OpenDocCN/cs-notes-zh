# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p33 P33 Write your own Operating System B03： File Allocation Table (FAT32) -BV1BDBEByEBY_p33-

Hello and welcome to the third part of Appendix B to the tutorial on Writ our own operating system。

Now， we already had the code to access the sectors of a hard drive。嗯。And。

In part of one of the appendix B， we。We looked at the partition table at the beginning of the hard drive。

This gave us an offset to the beginning of the partition。Where we find the。Bas parameter block。

And yeah， going from there， we could。Find the offset where the file allocation table starts。

Find where the data， the actual data starts， the。The names and types and。All that stuff of the。

Individual files。Yeah， and。O， so。Let's go through a few things again。😔。

So this offset we get from the partition table， this offset here。

I's this reserved sector account here。This gives us the offset of the。Filile allocation table。Then。

The size of this table multiplied with the number of copies。Of the file allocation table。嗯。

Together gave us a pointer down here。 You know， you have multiple copies of the file allocation table。

This tells you how many， and this tells you how large is every of these copies。Solo。

The product F2 gives you another offset down here。Yeah， and then。Then down here， you have the。

Number of the root cluster。 This is。That was the root directory， C code on back slash。啊。Whatever。

So the top level directory on the disc。And。Yeah， so we iterate it through the entries in there。

And printed the files。In that directory。So that's what we did last time。Yeah， but the point is。

 we only。We only loaded the first sector of this directory and the first sector of these files。

So the question is， what is。Going on if the files are larger than one sector。

 I mean a sector is only 512 bytes。So that's not much。So。Yeah， says this here as file one。

So the first sector we have read。By the way， the cluster number of the route directory multiplied with the count of sectors per cluster is actually the offset of the start here。

So this number -2 multiplied with。Sectors per cluster that's。

That is the offset to the first sector offset， Okay， so now we have read the first sector offset。

Offf that file， okay。Now。So if the file is larger than 50012 by， then obviously you need to put。

To you need to put it into different sectors， right， So you put。

Different parts of the file in different sectors。And the first sector contains the first 512 bytes。

When the immediately following sector。Contains the next 512 bytes。The next sector after that。

 the next 512 bytes。The next sector， after that is the next 512 bytes。Okay。But， there's only。

This many sectors in a row belonging to the same file。 Okay。

 if you have a very large file and your hard drive is。Fragmented。

 then the operating system will put parts of your file here， parts there， parts there and。So the。

The idea here is。That theres only a limited number of sectors in a row， which together form one。

Cluster。So you read a full cluster and if your file is larger than that。嗯。

Then you need to look into this file allocation table to find the next cluster。Okay。

 so I've drawn a little。Diagram here， so here's the root directory it gave us the cluster of the first file。

And we've found out the first sector of the file and read it。So in the next step。

 we will read the consecutive。嗯。As a consecutive。Sectors of that cluster。

And when the cluster is finished and we still haven't reached the end of the file。

 then we have so this is cluster number five，5。O。So then we just have to look in the file allocation table into position5 and that will give us。

Whereas a cluster number of the next cluster， okay。So I think that sounds simple enough， right。

 So let's。Just jump directly into the code。Yeah。So here we have the file cluster now。😔。

Here we load the first， so this is the first sector of the file。😔，So in this loop。嗯。没事。嗯。

So inside this loop。Yeah。We read。😔，The current sector。Plus， sector offset。Okay。

 so we read the first sector and。Print that。So， we read the。The next sector of the fire。😔，Okay。

 so I don't think I'm explaining this very well right now。So this is the first sector。Off the file。

 right， oops。So this is the first sector of the file。Then we read the first 512 bytes。嗯。

And after that。We decrease， or we shouldn't make this unsign。We decreased the size by 512。

 so we still have to read this many slides。So， after that。We increase the sector offset。

 so in the next iteration we will read the next sector。Okay。But。

So this would only allow us to read files that are larger than a cluster that are smaller than a cluster。

Okay， now now we can read files which are larger than a sector， but smaller than a cluster， okay。So。

う。Okay。Okay， so。So here we set the first sector of the first cluster。😔。

But we will put this in a loop。Yeah。Yeah。So the point here now is。😔，If we exceed。Cster。

Then we will break this loop。😔，るいる。う。YeahI think we should do this minus1。😔，So in this case。

 the current iteration has exceeded one cluster。 So now we would need to get the next cluster。

And how do we do that， So we need to set next file cluster。嗯。

You know also that in the next iteration of this while loop。Within。

Go to that next cluster to that cluster。Go to the first sector of that next cluster and start over there。

Okay， so。So a fat start。Partition offset。 So that's a sector number。Yeah。

 so that's the second number on the hard drive。😔，Yet due to lack of time。

 I haven't prepared the code for this， so it might become a bit messy here。And。

So the point is we need to。😔，Find out。I mean， the file allocation table will span multiple sectors also。

So we need to find out which sectors。As a current。That the entry was a current。Cluster is in， so。嗯。

Yeah。So， I mean， this is just4， but 512 divided on that should give us a number。Of entries per。

First sector。ok。Okay， so。So this is the sector number where we will find the。Entry for the next。

 where the next cluster starts。So here we don't go to the file sectors offset， but to。Fat start。Okay。

Plus。Fed sector for current cluster。Read that into the buffer。Yeah， we we could check。

I think it would be better， if we。If we had another buffer。So that we would use。😔。

There's fat buffer instead。 and then always check。 does the fat buffer contain already contain the。

The information that we are looking for。And then we would not have to read that again in that case。

 but。Yeah， I'll leave that to you。 I think you can do that on your own。

So I turned the fat buffer into。😔，Into an area of。Inteegs and。From that。I read。😔，This offset。Okay。

I mean， of course， it would probably make sense to use a template here and。

Use size of that template so that you could also use that for other， for larger。Types later。

 but whatever， I'll leave it like that。So what I'm going to do now is I want to create a large file。

Okay， so。But I need to know how many。Of these。How large this file must be so that it spans multiple clusters。

Yeah。

![](img/9854e382383aef67870ded31676434c9_1.png)

Yeah。Okay， so we have eight sectors per cluster。 that means 4 kiloB。Clus。

So I'm going to boot tiny core Linux again。Yeah。So to do to create that file。😔。

I will boot tiny core Linux again。So I will mount the。😔，a hard drive。没。Okay， and in here I would。

Remove fire2。And now create a different file too。So I'm going to make file2 have a lot of A's first。

Okay。So you see we have a lot of face now。And how I will put。A certain string in the end。嗯。Yeah。Okay。

 so now I'm gonna。Thanks。Hard drive， because I have had really problems with。Tiny car。

 not saving the stuff to the disc。😔，In the end， so。Yeah。



![](img/9854e382383aef67870ded31676434c9_3.png)

So。Where were we。So if we have read a complete cluster and。The size is still not。Zero。分。

We will read this。😔，The product of file allocation table。Yeah啊。Yeah， I think that looks good。😔。



![](img/9854e382383aef67870ded31676434c9_5.png)

And let's see if that runs。Okay， this didn't work。😔。



![](img/9854e382383aef67870ded31676434c9_7.png)

![](img/9854e382383aef67870ded31676434c9_8.png)

So， I found a mistake。嗯。Actually， there were several mistakes here。So， here I。I set the buffer to。

The size that we got from the dare entry。 And this is really a bad idea because it might be just somewhere in the Ram。

嗯。We have to。To set it to the remaining size。 Okay。

 so not to the complete file size of the files somewhere， you know。啊。

So this is basically this directory entry size modulus 512。F does these iterations， okay？So。

That was one mistake here。嗯。Then another mistake was that there has been a break here。

I don't know why I had had it there。But that was clearly wrong， because。Yeah， because of that。

Of course， we， we only， we still only read the first。

Cluster and everything after that was just skipped。Okay， then this test here had。

A larger or equal must only be larger。じ。What else this test was between reading and printing the buffer？

So。Because of that， the last。The last sector of。Of a cluster was skipped。Okay。Yeah， that's。

 I think that was all the。Problems I had in here。 Another thing is。

Here when I read the new the next cluster number。I takes a bit twice and with。He has a 302id。😔。

Integer that has all F's。 But the first one is 0， because。Yeah， I mean。

 I don't think this caused any problems but。The other thing is that F 32 actually only uses 28 bit。

Its for addressing the clusters。So， yeah， some people call it F 28 because of that， but yeah。

This just makes sure that we don't interpret the bits。

That might be there and used for something else for anything other than the。For the address。



![](img/9854e382383aef67870ded31676434c9_10.png)

Okay， so。Let's run this。Okay， here we have A， A， A， A A。

And then here one final A and the end of file text。嗯。Wondering。Somehow， this is。Printing it twice。

 Why is it printing it twice。😔。

![](img/9854e382383aef67870ded31676434c9_12.png)

But yeah， I don't care， so I think this should be enough。

So that you can now iterate through directories， you can iterate through files。And yeah。

 I think it's relatively clear how to continue from here。You would have a class file system。😔。

Which has a virtual method。 get directory， Travera or something。And that returns you。An instance so。

We'll have a class system with。Something that could get directory traversal。And from that。

 you derive something like the F file system。Which overrs this with something that returns。呃朋 you。

Fat directory Traversa。Then you have an abstract class directory trare on。おそ。Dive from that fat。

Diectctorory trovis。😔，And then you。you would have something like。The file enummerator。

So directory Traverr would have something like。Get file。Enumerator。

The Feds directory Travera would overwrite that。Was。And you said。Director Re Fa file inummerator。嗯。

So。And that would have something like get name。😔，Yeah。Yeah， that would override get name。

To read the name in the way that we did it here and then maybe something like a fi reader。嗯。

With a method read， that gets some。巴发。And how many bys？And the that file enummerator would。Also。

 have something like next。嗯。Sort of。The F， I mean， the base classes are all abstract。

 okay and these derived classes。Get name， and get。Reader。And maybe something like。

So the directory Traveror should also have something like it file writer。Right， Tom。With a method。

 right。Was the buffer and the size。And derived from that to fat。😔，So right on。😔，Yeah。

 maybe something like。Slulash。哦。Close。Flash， clothes， and so on。Yeah， Rita doesn't need to flash。

I mean， closing doesn't even really make sense in this。But。Yeah， so。

 so this would be a really object oriented way of。Doing this。So。Yeah， going from there。

 you could just。You could just work with the abstract classes in something like a directory like a file manager。

Right you would just ask the operating system to if you point to an object。Of file system。

Then you would ask that to get a directory traverser that gives which。givesive you。

An object that points to the root directory。Yeah you should also have something like directory traversor。

 like change directory。And maybe something like make directory。And stuff like that。So。

But the point is that。That you have these abstract classes。

 which give you an abstract interface to everything and。And then you can just derive different。

Sub classes from these for other file systems。 You know， then your when your file manager can just。

Can just say， hey， operating system， give me。A fire system object。

Then you get maybe a fat fire system object， you don't know， you don't care。

So your fire system object gives you a directory traversa， which。嗯。

Which points to the root directory in whatever manner there is， I mean。

 you could actually make a completely virtual file system with that。嗯。Yeah。

 but then you have this directory Traversa and。With that， you can。 you can traverse the tree。

You know， you can go to a。To a subdirecty， To a parent directory。By the way。This。In fact。

 there is actually a directory and an entry in the directory。For dot dot。

 which is the pointer to the parent。Directory， so that gives you the cluster of the parent directory。

Okay， so this F directory Travera would need something like the cluster number。Which isn't。

32 bit integralte。O。So you could use that object to go down in the tree， go up in the tree。

And then you could ask the directory Travera， hey， now I want to know which files are in this directory。

 then you could。So you ask it， give me a file enummerator。That gives you a file enumerator。

 You ask this enumerator， hey， what's your name， You can go to the next file。From。Yeah， and。

So if this isn't the file you are looking for， you just。Called the next method。 And this should。

This route。Jump to the next entry in the。In the directory。And yeah。

 if you find the entries that you are looking for， the one was the correct name。Then you say， hey。

 give me a reader for that so that you don't have to think about things like。

Like clusters and everything。So yeah， then you have a file reader and then you just ask that object。

 hey， give me some data， give me some data， give me some data， okay。And this object。

 so the derived class， F file reader would then have to deal with a sector count with a number of sectors per cluster and how large is the file and stuff。

Actually， you should you should also do some have something like get size。This should also be。

AGood idea。Yeah， so then you could really completely work your file management systems。

 your file management programs can work completely on the abstract interfaces。



![](img/9854e382383aef67870ded31676434c9_14.png)

And。Yeah， your operating system just has to give you。Just has two pass。An instance of this fat。

File system object to your file management system and everything else is then completely on。嗯。

The the fire systems problem。 Okay， you just talk to the abstract interfaces。 You know， you say， hey。

 I want to。I want to go up in the directory， or I want to go into the subdirecty。

 I want to make a directory， whatever and。系ello。Yeah。

 the concrete implementations in here have to deal with all the stuff like。Yeah。

 with the file names and。Everything。😔，With the clusters and size of cluster and whatever。So yeah。

 that that would be a good idea， I think， so then you could really work on a very abstract way with files。

And don't have to worry in any way about。How the system how the file system handles this。So yeah。

 I think that's without it。😔，I was thinking about， I mean。

 last time I said that I have that I was that I thought I read that the patent for the long file names was invalidated。

I've looked that up and I have found an article about that。But to my knowledge。

 the legal stuff isn't through yet， so I'm not sure if the patent is already invalidated or if it will be invalidated and I don't know if there's any legal stuff。

 it's probably not finished yet。

![](img/9854e382383aef67870ded31676434c9_16.png)

If it's invalidated， Microsoft is surely going into revision or something and。Yeah。

 I don't know if it is。I don't know if it is invalid if it's invalidated。

 it's probably being disputed and then then you still I still cannot teach you how to do this and。

And even if it's invalidated， then I don't know if this applies worldwide or only to the USA or I mean I live in Germany and I've read that the patent was upheld in Germany。

So whatever， this is just too dangerous for me。 I'm not doing it so but you will find documentation online。

 so it's not that hard。You'll be able to do that on your own。But yeah， so have fun with this and。Hey。

 I was just going to say see you next time， but。Yeah， this is our last video。

 so I don't see you next time。Except maybe。Yeah， maybe I'll do some more videos some time in the future。

I mean， there are topics like user space， USB devices。We've scratched on HTTP， but yeah。Whatever。

 So virtual memory， we haven't touched virtual memory with paging and everything， so。So there's。

 there's still a lot of topics that we could talk about。 But the thing is that this room here。

Won't be available to me starting tomorrow。 So therefore this is the last video for now。

 as I've said， I mean， I have a whiteboard at home but。Yeah。

 maybe I will make some more videos in the future， but for now， this is it。 Okay。

 so if you like this video， hit like yeah subscribing at this point is maybe not。But true。

Feel free to subscribe， I mean， I'm thinking about other things that I might make videos about other than writing operating systems。

You know， like for example， writing puzzles。So that you can make， for example。

 a programming language for yourself。But。Yeah， as I've said， so from from this room here。

 this is the last video and。Yeahep。Maybe I'll as I've said， maybe I'll do stuff on other topics。

 but so feel free to subscribe。Yeah， see you then， hopefully bye。


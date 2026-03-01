# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p130 41_03_04_构建用于解析文件的Rust命令行工具.zh_en -BV11y411z7Dn_p130-

![](img/66b00e95edff66f4d79a5f0b139456eb_0.png)

Okay， so we have here our little main thatRS file that is crawling the file system we've separated things into walk path which is a function that takes in a path and it does a loop and it cross the file system but one thing that I want to show you is something that might be useful which is detecting if a given file is a text readable file or like a plain text file actually or if it's a binary like I've done this in the path and it's very useful and it might be you know a good use case to have when you're crawling the file system So right now everything is the same the main function just like takes in a single argument which is path and then it calls the walk path function if I scroll all the way up we're going to have the walk path function right here so let's start modifying the first thing that we're going to do is。

Let's start getting our our imports right here at the very top。

 So we're going to use standard Io not enough。 We're going to do both read。

And a buff buff reader and these are going to help us get what we need to。

 of course those are gray out right now because we don't have。

 we're not using them right so next we're going to still like do the loop but then we're going to let's just get rid of this one right here we don't want to print that one and then path is fine and then if path is directory。

 we're going to continue doing the recursion remember recursion means that we're going to call ourselves with the same argument right there Okay if。

Theres if it's not a directory， then we need to do our checking， so let's start doing the checking。

And the check is going to be well we need to say let file equal Fs file。

 we're going to missing a column here。 we're going to do open。That looks correct。

 and I'm going to be kind of sloppy here。 I'm going to do a lot lots of unwraps。

 I'm not going to handle the errors properly because I want to just show you how to do it pretty fast。

 and of course， you can add a better implementation that doesn't use unwrap in this way。 Alright。

 so let mutable buffer。 I'm going to create a buffer here。 and that buffer we're going to read。

1024 bys and this bytes is exactly were want to read that's how we're going to do the detection。

 We're going to get our mutable reader。And our mutable reader is going to be Buff reader new file that looks correct。

 So we'm going to use files， so now we're using these。And then we're going to do let bys。

 red is going to equal the reader that read。 And that's going to be the mutable buffer。

 Another unwrap here。And and then we don't no longer need to do this print line right there。

 but then we need to we need to say， okay if。If bites red。Is more than zero。

 So like we we have more than than0 bytes， zero things that we've read and standard。

I from Center Library Str from UTF。This is not quite right。

KHub compiled is suggesting something else， but we're going to save a string and then from UTF 8。

And what we're going to do here I'm going to say on buffer。

 and which is like the the we're going to pass in the buffer。 andm when I say。

In here we're going to do bys。🤢，Bites red。And， I mean， I I know this is a handful。

 but just stick with me for a second so that I can type all of these so effectively what I'm saying here。

 hey， if this is the case， then we're going to print line what， what do you think we should。

Print here if we're able to read UTF8。 Well， we're going to say D C's plain text， right else。

We're going to say。Bary file， right？So that that should work I think we're gonna remove that and I think that that should be good so now if we go and try togg the terminal and we pass in a let's pass in a path here which is cargo run bar log where all of the files are we can still we can now see that we're gonna to get binary files like this is definitely a binary well it's not necessarily binary file but it's not a plain text one right because this is a compressed file this is B2 GC compressed file right there and you can see those are properly detected now one thing in rust that I want to show you is that I'm going close this one out this read this trait I'm not using it directly right what I'm using directly is the Buff reader so if I click on Buff reader you will see that it appears。

So it appears right here these comes from here， but what about what about read So if I remove that I'm going to show you what what will happen so I'm going to save these Im remove the curly bracket。

Then this happens。 Do you see that red underline， if I hover。

 it will say no method name read found forstruct Buff reader in the current scope。

 It from trades can only be used if the trade is in scope。 So what does that mean。Well。

 like we I missed it right there， but like we need to do this suggestion and this is why Russ has such amazing compiler errors。

 the following trade is implemented but not in scope perhaps at of use for it is this one right here so this is something worth noting that you might get into trouble when you don't have the trades in scope that means they're not within the program and now we say that and everything goes away like we becomes correct again and we don't have no longer that problem with a compiler error。

 that compiler a complaint of this now working so why is this a good thing to do or some an implementation detail and implementation strategy that you may want to consider because。

Crawling the system is just one step in many different situations that you may face and I've done similar implementations before where I had to look for plain text files and make sure that I was dealing with plain text files not binary files in one case I was dealing with files that were in a disk drive that were configuring this drive and and I had to and I had to check well is this a file and I can safely open it programmatically without actually knowing them beforehand and something like this would come into play and doing it in rust well you're doing a super fast efficient implementation that might help you out so this is one thing to consider looking and crawling for the file system and doing it in this way。



![](img/66b00e95edff66f4d79a5f0b139456eb_2.png)
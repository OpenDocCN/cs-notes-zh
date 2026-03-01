# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p129 40_03_03_文件系统爬取.zh_en -BV11y411z7Dn_p129-

![](img/abec0121c34c9ef6ee56f89a244ab01c_0.png)

Let's work here with a rust application that is going to walk the file system。

 this is a very useful thing to know because it will allow you to not only well essentially walk through the file system but perform many tasks。

 this is a foundational knowledge that you need to have and in rustT。

 this isn't that terribly complicated， we have certain things here that are unused。

 this is a main R file。And all that we're doing right now in our main function is we're collecting a single argument。

 we're not using a CLI framework， we're just being very straightforward and just accepting a single argument which is going to be the last argument well in this case is the argument that is getting past in correctly and that is going to be well number one the first the second item in the index and index starts at zero so that we're going to consume is the number one and we're going to use that to effectively crawl the file system we're going to look inside now that is fine right now this doesn't do much if I toggle the terminal and I do cargo runs so say for example bar log it will say I have some things that are not used which we know which is the FS create will not create the module from the standard。

Liry and nothing else is happening。 So it's just printing if I pass something that doesn't exist。

 So it will tell me path bar who doesn't exist。 Okay， perfect。

 so let's start actually adding the code and see how that looks in order to take a look at what we need to do。

 So one interesting way that I really like to do is to separate the concern。

 So main will'll take care of processing the argument and then we can have a function that walks a path so we can say path is going to be when I take an argument and we can make this a path variable。

AOr or type right rather And that's going to come from the standard library path。

 I'm going to make that a module and we are going to open up the curly bracket here and we're going to just start walking walking through how we do that。

 Well， let's start with doing a。A loop， and' going I say four。Entry in FS。

 I'm going to say read when I read that directory， and when I say path unwrap。

Let's take a look at what's going on here。 we can we're just going accept what Copi that is suggesting and we're going to have like the entry。

 we're going to have the path here and if the path is a directory we're going to call we're going to do some recursion which is an interesting concept Otherwise we're going to display what that is so let's try and run this and well we can run it right now because this is not getting called right so first first order is to actually pass in pass in a path sos let's go ahead and do that。

Andre going we' already have our path as a new path here and we're going to call call our walk walk our path with path。

 there we go and were not we don't need to return that。

 So we're add a semicolon there if I can ever type that Okay， there we go。

 So I think that looks correct to me， we have a function here that is going to walk that path。

 And when I toggle the terminal。And I'm going to clear and I'm going to say cariggo run bar log。

 and'm going to C。 All right， so that worked very fast， actually。

So let's take a look at all the log files that I have。

 So that is that is quite the amount of files that he found。 so that's pretty good。

 and we did a little bit of recursion。 So the output is correct。

 The example is fine now let's take a look at some of the things that I mentioned I mentioned that we were doing recursion。

 so let's dive into a little bit onto that the walk underscore path function takes a single argument which is a path type and what we're doing is we're going through。

The directory， right， we're assuming the path is going to be a directory。

 and then we are finding all of the bits and pieces。

 we understanding what's the path and we want to know if the path is a directory。

 then we know we want to traverse， we want to go a level deeperper。

 So because we want to keep going instead of like doing that work here， we can just call ourselves。

 So we go all the way back here at the very beginning。 So as long as its said directory。

 we'll get that into calling into ourselves essentially passing that path into ourselves。

 if it's not a directory， we just go ahead and print out。

 Now that is a good way of traversing the file system and finding interesting things。 Now， you know。

 we have path display， but we don't have entry so we can say print line。

And we'm going to say entry path display and we can accept that and we can we can start seeing exactly what what are these parts and trying to debug a little bit what is going on unfortunately that deep do didn't tell me exactly what this was。

 So let's add that here。 I'm going to say entry path I'm going call it like that and then we'm going to run it again。

And we're going to see that we're getting all of these all of these right here and those are the entry paths and so we are essentially finding or trying to understand what are the parts that the read directory there is going to give us this entry that is going to be produced So that is a very straightforward way。

 I would argue that these looks even simpler than an implementation with say for example。

 Python and what are some of the interesting things that you can do here when you're crawling the path that we'll see later in detail。

 well， you can actually start doing certain things if you're looking at that directory， for example。

 or if you want to limit the numbers of recursions like if you're going deeper into the file system you might want to say。

 well I just want to go to the top directory only and I don't want to go traverse more than one level so you will have to control that。

Right here， but this is essentially a solid place to start when you want to crawl the file system。



![](img/abec0121c34c9ef6ee56f89a244ab01c_2.png)
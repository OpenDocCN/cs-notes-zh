# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p36 36_02_06_使用SHA-3检测重复数据.zh_en -BV11y411z7Dn_p36-

![](img/abea452d3003a64b73e894a4e6a089bf_0.png)

Here we have a example of rust crypto differences from M2 to M4 to M5 right these are all different libraries that you can potentially use and this particular repo is handy because it tells you the security level So notice that it says for new applications or where compatibility with other standards is not a concern we recommend Blake2 Sha2 or Sha 3。

 so you can see here that we have in this particular example Shah3 like the we call this the later standard we can actually look at this and see that it's very secure for using an encryption。

 So now that I know that I can use that library， I'm going move over here to my cargo file And if you want to use a particular dependency here you would just put it into your cargo do2Ml and then when you do cargo run it'll pull it in so very。

 very straightforward to pull。

![](img/abea452d3003a64b73e894a4e6a089bf_2.png)

dependencies Now in terms of what we're going to build here， notice that I had those other libraries。

 the random， etc ce。 I use the Shaw here is I want to grab a list of phrases from the book Old man in the sea by Hemingway you can see here I design a static phrases here and I also add in that there's going be 10 strings that are inside of this Now notice I can say you know this phrase second phrase。

 etc ceter。 and once I have these phrases together。

What I want to do is I want to generate a bunch of random phrases。

 So this in a way is a simulation to generate a bunch of text where there could be duplicates that's really the idea here。

 And so that's what this random phrases does。 and again notice that it accepts or it returns back a vector full of strings and then all we do is we use this static phrases here and we pull it in and then we generate a bunch of messages into a vector of strings Now the next function here is where we would pull in the power of the Sha3。

 So what we're going to do is we're going to create a unique hash using this hash map here and we're going to say here's the total number of phrases and we're going to say for phrase in phrases go ahead and create a unique hash for that particular phrase what this does is allows us to really quickly identify duplicates。

And then we're going to go ahead and put in a list of the unique number of phrases here and put some more descriptive statistics like total unique duplicates。

 total combined duplicates and then basically print it all out at the very end。

 So that's one of the use cases for the Sha3 here is to read in text and then determine whether it is a duplicate or not。

 So it's a very good tool for detecting duplicateplication。

 Now if we go to main here and we look at what what's going to happen。

 This code is going to generate random duplicate phrases from a list of phrases。 So in this example。

 we'll see that it was 24 phrases and it's going to give you the unique cache and it's going to say how many times it was able to detect that phrase and it's going to say how many unique phrases。

 So in the case of for example， 10 phrases in this case， there was only nine that were unique。

Duplicates， and there was a total of 14 combined duplicates。

 So like how many duplicate phrases out of 24。 So if we look through here。

 we can actually check this out and we can see it all work together。

 So all I need to do is type in Cargo run and we can see what happens here。

 So if we run this piece of code。

![](img/abea452d3003a64b73e894a4e6a089bf_4.png)

We're going to see that it generated 24 phrases and it generated we can see that this phrase was three times the next phrase was three times et cetera。

 so it's able to see that there was a total of 10 unique phrases and there was a total of of the duplicates that were found。

 there were eight different kinds of duplicates so we can see here 1，2，3，4，5，6，7。

8 and then of all of the duplicates right if you sum those together。 there's 14 duplicates。

 So 24 phrases here we can see these are the descriptive statistics about it。

 So this is a nice technique to use depending on what kind of problem you're solving。

 maybe you're trying to curate a data set or look at a file system and remove certain files。

 fortunately again， with rust is very easy to build a powerful command line tool that can detect duplicates and text and you know binary files and it's all done through existing。

Libraries， and you also can rest assured that it's going to be easy to distribute this because you can do a binary based deploy。



![](img/abea452d3003a64b73e894a4e6a089bf_6.png)
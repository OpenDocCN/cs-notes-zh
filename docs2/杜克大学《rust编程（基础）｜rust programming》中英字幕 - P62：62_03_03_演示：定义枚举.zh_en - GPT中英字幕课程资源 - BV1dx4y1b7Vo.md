# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P62：62_03_03_演示：定义枚举.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/dfd018de08434f0f22311a92b3c0e2c7_0.png)

Now let's see inums and we've already seen inums before。

 but we'll now look into them as in very technical details here。

 what we're going to try to do an inum stands for an en numerator and it is another way of grouping something in a category that holds different types a different variance rather of what we want to do so in this case a disk would can be like an SSD solid state drive or a speed drive。

 which is an HD and in some situations and we'll see this a little bit later this can also hold a little bit data these can have like an unsigned 32 bit size of an integer and we can definitely do that now as always you can add derived debug property onto the inums just like you would do for。

Strs as well。 in this case， I didn't add one to this type because I'm definitely trying to print out this size。

 So okay， so how do you use them what are some of the things that we can do？ Well， let's take a look。

 here we define variable online line 13， we have this type this type SSD perfect。

 we're saying that this type is going to be an SSD So what are some of the things that you can do。

 Well， initially you might be tempted to like try to compare in languages like Python and jascript youll have a compator and you'll say。

 well， is this type an actual SSD and well you can't we're getting the curly the curly red line and why is that well let's take a look at what the compiler says in this case。

 the binary operation cannot be applied to type this type and why is that well because we are not implementing we're not implementing the。

QualityAnd the partial equality with anything here。

 And so the normal way that you would see that is not is not using a。An quality operator like that。

 so what how would you do it， well you would do it with a match。

RightSo instead of doing it like that。Let's actually go ahead。

 let's leave the commented out code there for a second。 and yes， let's do a match。

And we'll say this type。 And yes， the rest looks okay。 So this means that the。For this type。

 if it's an SSD， then you will print that or a Y we'll print it a spin drive。 So if we run these。

 we get this type is an SSD。 ignore a warnings here because I'm not using absolutely everything that I have there。

 Allright， so that is how you compare That is how you do things with how you can find out about a certain inum Now。

 definitely not using the compator like that。 All right And what are some of the other things you can do well。

 you can you can assign a data to it in this case we say， hey。

 we have an 128 gigte disk how about how about that and we can actually print that out。And run it。

And we will get this representation here。 So at a very high level that is how you define your inum。

 you will use the inum keyword right there and then you have a name curly brackets as always opening and closing curly brackets and then you define these variants and sorry for scrolling there but these are called variants so these are not properties these are not fields like ins。

 So these are variants， this is H， the HD variant of the disk type and this is the SSD variant from the disk type and these variant denomination will also come in when you get error reporting from the compiler when you have errors with a compiler you will see these things be called variants and when you're missing some variants and when you're having trouble with variants well variants are part of an inum。



![](img/dfd018de08434f0f22311a92b3c0e2c7_2.png)
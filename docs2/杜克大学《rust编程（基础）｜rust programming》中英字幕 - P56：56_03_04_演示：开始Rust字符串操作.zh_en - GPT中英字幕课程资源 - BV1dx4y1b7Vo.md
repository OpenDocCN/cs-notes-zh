# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P56：56_03_04_演示：开始Rust字符串操作.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/d7daae5eb98e4195065d2322264bf447_0.png)

There are many operations that you can do with a string。

 We're going to explore a couple and one that we've actually seen before。

 So let's start at the very top。 we're defining a new sentence and in this case this sentence is not a string It's a string slice so let's quickly make it a string and make sure that we can actually start working with that and what are we going to try to do here is we're going to print try to get the first three characters so this is a using a slice this is a slice in a string。

We're getting the three first the first characters so let's just run these and actually let me comment this one now so don't we only get information of what we're trying to execute here so I'm gonna to run that so we're getting the right there now remember that ranges are you can actually go ahead and do inclusive which would be the equal sign here let's see if we're getting that so before we're getting TheE and the space and now we're getting the Q as well so that is definitely something that you can also cover here we've already covered ranges before so this is something that you can definitely try and do next let's take a look at I'm going to comment this out so that it doesn't bother us concatenating using format and this is something that we've seen before and in this case we we're creating a new a new variable we're saying format。

Wwhich is a macro and we're saying well we're gonna we're gonna add these。

 essentially this is a string right here， which is it takes an STR。

 a string and then we're passing in the sentence which is the string so we're doing both things and we're formatting and we're printing that。

 It definitely works and that is not a problem。 this would work even if sentence wasn't an actual string and it was a slice as we've seen before this was still work no problem because it would return and an string。

 a string types if we do we check that， this is STR， a string slice。

 and this is a string and it wouldn't be a problem。

 So lets let's give this to string to avoid hitting more problems than the road So definitely that's another thing that we've already seen and it definitely useful in some situation。

 So how do you iterate over characters world you can always。with the sentence。

 we're going to iterate over the chas and we're going to get an iterator in that definitely so we're going to get a cha。

 every single item is going to be a chart that is going to be looped over。

 So here we're going to do is for every single item。

 which is C for character we're going to check if it's a vowel。

 So we're going to have all of these possibilities。 And if that happens。

 we're going to print got a vow or Y， which is going to continue no problem。 So let's run these。

And we have definitely quite a few bowels there。 It's kind of like a silly example， but the simpler。

 the better to try to understand how we can actually make that go nice and and how to like with a simple concept。

 we can we can build upon our knowledge。 So I'm going to comment that out and go to the last one。

And going to un this one and say what happens when you want to split the words into whitespace。

 which is actually a very common operation and then you want to capture it as a vector we haven't seen vectors yet but you think about it as a collection of items kind of like an array in ja or a list in Python So we say we want to make it a vector and that has to be string type this way of defining variables is a way of defining the variable and saying exactly what you're expecting So in this case we're going to split by whitespace and then collect So definitely that's something that that you can do it do it that way and then we're gonna print the debug information and that's the actual response that we get you can actually there's many different ways。

of doing these you could also do let words， make it split on white space。

 we can say sentence that split and we can actually do space and then use the suggestions here from copilt so we're going to we're almost like reversing and we're saying hey when you collect these make it a vector of strings slices instead of doing it this way where we're saying a just get define that right there so if we say that and we run these we'll get the same the same the same result So that's it that those are a couple of the things that you can do and one last thing one bonus thing that you can do is we can reverse the string actually so we can say let reverse and we can do sentence that chas and then we can call that and then we can call reverse and then yes。

 we can collect that as。String， and then we can print line， we can say。

 we can say what's the reverse portion of it。 Let me comment this one out so it doesn't pollute the output。

 I'm going to run that。 And what we get is。The quick brown fox jumps over the lazy dog in reverse。

 So definitely something that you can try out as well。

 I usually don't have many situations where I need to reverse strings。

 but it is something like like I said， like it's a bonus。

 it is a nice way that we have something built in with string the string type where we can actually make that change。

 So there you go， those' are a few things that you can do manipulate strings and some like don't even require strings that you can use string slices as well。



![](img/d7daae5eb98e4195065d2322264bf447_2.png)

![](img/d7daae5eb98e4195065d2322264bf447_3.png)
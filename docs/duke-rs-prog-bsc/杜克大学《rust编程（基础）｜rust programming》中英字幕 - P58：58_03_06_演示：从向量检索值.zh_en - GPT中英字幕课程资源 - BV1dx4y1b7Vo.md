# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P58：58_03_06_演示：从向量检索值.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/d9373e9707e267894a6277d84d9e808e_0.png)

There are several different ways where we can retrieve the values from vector。

 so let's take a look at how we can actually do that。 Let's define a new vector here。

 It's not going to be modified。 So this is immutable。

 we' defining right there and we're going to look at how we can do this。

 So we're going to retrieve at a specific index。 So remember indexes start at0。

 So if we can say the third value is going to be the index of two。

 So that means this number right here， that's the third value and that will print the value in the vector is the third value。

 This being this thing because number two is actually the third item。 retrieve the last value。

 we have a nice method right here which is the last and then we have to call unwrap because this is probably an option So last value in the vector is the last value。

 actually if we go ahead and save that。You can see that we're going to get the return。

 It's an option。 Why is it an option because you can get either the value or you can get a nu because if if the vector is empty this is a safe way of retrieving the last value without getting into trouble that is why we're saying unwrap because we are saying yes。

 we want to actually get the actual value that it comes that's fine and that that will print the last value so that's why you want unwrap right there and then last one is say an interesting way which is with match you can actually say。

 well you know I want to I want to do something with with the values that I'm getting and then you're calling first which is again an option。

 if I go here you'll see that the option it's a return value so you could be a none or an option so if you're saying hey if I do have something well。

I'm going to say， well， what's the value Otherwise， if I'm getting a nu， then the vector is empty。

 So if I run these， you will see that。I'm getting the three， the five and the one。

 so what happens if the vector is empty well？If the vector was empty。

 we're going get into trouble here。 We're gonna to say let vector equals that。 So it's empty。

 and we're start getting red underlines because this one will cause a panic。 So we。

 if you're if you're retrieving values like these， the consequences that you can get into a panic。

 Actually， this is not a panic。 we're getting a， we have to explicitly say what we're trying to get。

 And in this case， we will be getting。We want to be an I 32。 and then that's fine。

 So let's try this again。 And now we're getting a panic because we're like that's you know we don't have that index that the vectories is all empty。

 We see that thread main panic。 that index out of bound。

 lend0 but the index is2 so we can' we can do that right the vector is completely empty。

 this is going to panic。 Al right， so let's comment these out and let's see how the other ones work。

 Well， this one's going to cause some problems。 we are expecting an i 32 here。

 and what is this well mismatch types， we're gonna find a reference all kinds of different things here。

 Let's try。Let's try that。 and let's run it。 And we're getting a panic again。

 because main panic are called option and wrap on a non value。

 So we're getting into all kinds of different problems。 Now， I believe that。In this case。

 the last one should work No problem， but we still need to say that we want to have the actual explicit type。

 So rust in certain situations will complain。 most of the time it would be fine。

 but if you if you are in a situation like this you have to say， well。

 rust cannot tell on an empty vector， what is it that you're expecting。

 So if you're expecting a value like like I32。 then this is obviously completely correct because like it doesn't have the I 32 values。

 but in a situation where you have a vector in the vector is completely empty。

 then you would get into trouble right there。 All right。

 so enough enough surgery enough getting into trouble here， let's go back to the beginning。

 let's all make it quite right。 and then let's take a look at this thing that I have here at the very top。

 and the reason I want to show you this is because。We are saying that this is a function。

 It requires an index， but let's just assume that there's no index here and going it's going to set the index here and it's going to retrieve the index So before in the previous example that was a three and then you do the get the index and then you print the value。

 So that's that's pretty pretty useful let me comment out the print lines so that we can only see the actual call to our little function right here at the very top so that's a get item So let's call get item right there and then let's run this and let's see what happens。

Alright， so the value of index 3 is sum4。 So what is that sum 4。 Well。

 we're getting a value or we're getting a none in this case， that's why we have that debug here。

 the value might be a none so we're getting that actual thing that we got here so we can actually call unwrap and that would give us the actual number So the value at index is3 is4 Otherwise we would getting an a sum like we did before now we're unwrapping so we're actually retrieving the value that we want。

 Now what if you wanted to have the ability of passing the index。 So you have to declare the type。

 Now this is this might be confusing because you might say well， this looks like an unsigned integer。

And we want to pass that in。 So you might be tempted to say something like index。

 and then we can say something like U8。And then， and then， instead of like。Doing that。

 we comment this out and we pass that in， right， So we say here， let's say we want index of three。

So now we get a red underline and that is because the type integer cannot be indexed by U8。

 What is the problem Now the thing is that you need to pass U size and that might be surprising because U size is the thing that you have to use for these types of operations So if you say u size here。

 the type then everything will just work and if I hover over there then the pointer sized unsigned integer type the size of prim is how many bytes it takes to reference any location in memory。

 for example on a32 bit target for bytes。And then and so on and so forth。

 but that is the way so now if we say get item3 and run these we will get the value indexix 3 is4 and everything just works so there you go。

 those are a few ways where you can actually retrieve retrieve values from vectors with U size item that we had to explain and to avoid getting into trouble。



![](img/d9373e9707e267894a6277d84d9e808e_2.png)
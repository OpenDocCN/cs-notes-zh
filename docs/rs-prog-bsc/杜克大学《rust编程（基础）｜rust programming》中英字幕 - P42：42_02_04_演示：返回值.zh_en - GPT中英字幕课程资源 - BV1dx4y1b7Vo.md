# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P42：42_02_04_演示：返回值.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/a185e46fab7d9ee73811b1c83af2f343_0.png)

In a language like rust， the return types and defining explicitly what a function is returning is very important。

 In this case， this function， the split string function is returning a string So that condition has to be met。

 So whenever we're not complying with that condition we're going to get into trouble。 Now。

 put aside the specific knowledge of what we you know what types of data structures and what types we're working with here。

 this is an absolute truth that has to that has to happen at the end of the day。

 it doesn't matter what this function is doing， It has to return a string。 And in this case。

 we are returning what we think it's a string， but things are not quite working。

 Now let's walk through what we are dealing with here。 we have this mean function。And we have。

Let's see we're calling the split string here。 it's a hello world string and we're saying we're passing three parameters to this function。

 the specifics of these it's not that important the problem here is that we're passing something and we're expecting the chunk is going to be a string actually we can use visual studio code with a shortcut here to tell us exactly what these types are so you can see here chunk is going to be a string。

 this is the limiter is going to tell me the the arguments here's an option。

 we're going to get an index so that that's pretty pretty good sos let's use the editor capabilities to help us out here。

 We're expecting a string back and apparently we're going into trouble。

 So first let's hover over the red underline and we're we're gonna see that the method two string exists for。

Inum option stream by a straight bounce score not satisfied that。

Might sound very complicated if you've never seen that， so let's just when that happens。

 my suggestion is to run it and see what happens and get some more context here。 Okay。

 so we're getting we're getting these it't it doesn't this is the signature and what we're expecting which is the string but it says。

 hey， consider using option expect one wrap the value panicking in the values and option none so it gives me the suggestion to say result expect to string。

So what is the deal here， what is actually happening Well， result is an option。

 an option is anum and anum has different values， it can have one or more well more than one ideally values it's an enumerator and this en numerator can have more than one value and in this case the option value has can have either a value or a none So if I go here you'll see this is the actual en numerator for option and you can have either a none or you can have some value of type T type T is the generic value that encompass every single or it kind of like a generic type in rust that can be any type really So I'm going to close these and in this case result can be either a none or something else。

 So when we say to string well this is not。Ping with this thing， so。If we were， actually。

 let me do this， let me comment this out。 if we were to return something like that to string。

 that will comply。 That will comply with the the constraint of returning a string。

 This is an actual string。 It will comply with the return type and everything would be right。

 Let's just actually try to make this useful and make this comp。 So what was the。

The suggestion was to say， expect。And say， you know， oops， something went wrong here。

And I'm going to close that and then to string， and I'm going to save it。That works if I run these。

 it totally works， a string word， that's great， it split the hello world using a comm limiter and it will get the first field。

So that's that's very good。 So what are return values。

 return values are things that functions are returning to us in this case we got into trouble and we we tried to make it better by actually doing an expect。

The particularities of expect are not that important for us right now， it is a way of saying， hey。

 if this is not quite right， you know it's okay， we're going to panic and we're going to get this return value which is not return value but this message when we are getting into problems and the way we do that is well by forcing the functioning into getting into an error which we're not going to do right now because this particular lesson was about return values in this case this is a string so whatever you see this thing right here it will be a string。

Function main doesn't have one。 So what's the return value。 Well。

 we're going to get the return value is going to be。The generic parenthesesis。

 the generic parenthsesis of a main function is the unit type。

 and we've seen that with simple unit functions。

![](img/a185e46fab7d9ee73811b1c83af2f343_2.png)

![](img/a185e46fab7d9ee73811b1c83af2f343_3.png)
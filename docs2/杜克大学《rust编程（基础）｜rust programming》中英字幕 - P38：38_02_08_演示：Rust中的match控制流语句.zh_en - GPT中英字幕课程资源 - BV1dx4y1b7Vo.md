# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P38：38_02_08_演示：Rust中的match控制流语句.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/21b34163574257a76dc38473419b00f6_0.png)

Match control flow is an interesting way of dealing with different scenarios that you want to handle in other programming languages。

 you might see these word this statement as or this keyword rather as a case in rust it's actually called match is not used they don't use case。

 the programming language doesn't use case so what it is is that it's trying to match in this case the name variable to certain possibilities each line here represents a distinct possibility and those possibility are defined by this thing here on the left so the way it will work is by having the actual value that is trying to match on the left followed by these character these two characters the equal and the greater than。

Character and then like a given action now this could be an expression as well。

 but in this case it will just be printing So what will happen here is that hello variable defined or assigned to name will go through these match block here so name will be hello and in this case on line number nine not is not going to its not going to match。

Goododbye， of course， but it is going to match number 10。

 which does say hello so in this case we will get high nice to meet you now those are on the things that will match or won't match but we we do have a catch all convention which is this underscore that means that we have a way to fall back to anything else that's very common on on this type of constructs for other programming languages in go when you have case you have something similar to that underscore but this is a way of basically saying we want to catch anything else that doesn't match these conditions and this is not necessarily going to catch only these three you could have five for example different types of conditions or or just two and not anything else all right with that said。

 let's just go ahead and run it。what we get。 So we do get high nice to meet you。

 and let's just change these to goodbye。And let's just save that and run it again。

 Sorry to see you go。 The message gets updated。 and finally， we can say。Hey， what's up。

And then we can run it。 And I can find a greeting goodbye。 So that's pretty good。 Alright， well。

 that's pretty straightforward。 Why don't we make it slightly more complicated。

 just slightly more complicated to make it a little bit more interesting。 Since this is。

 this is already basic。😊，So what we're going use and we've already seen this before by reading the input。

 we're going to use Io right here， we're going to enter。

 we're going to request enter a greeting and then we're going to create a new string that is going to be also mutable defined by these keyword right here then we're going to read the input we're failing to read the input。

 this will bubble up we haven't seen expect yet so let's not get ahead of ourselves let's just try to see how this can be made a little bit more robust so we have like the same messaging here and we'll just try to run it。

 so I'm going run it enter a greeting and I can say hello and high nice to meet you and that's fine run again we can say we can say hey I can't find a greeting goodbye so that's interesting so now we're able to combine a couple of things。

We've already seen before and as you can imagine， this could make it for a very robust way of dealing with input on the terminal if you wanted to do something with a while loop for example you probably have to put this somewhere in a while loop that keeps asking asking the greetings and then matching and then perform in certain actions so there you go that's say an interesting way of being able to to use matching so that you can actually perform certain actions now the last thing that I want to mention before before ending is that see that the name is not matching the name exactly it' doing a trim that's because it's way of any extra space on new lines that may come from the terminal input so definitely there's lots of things that you can do there but this will allow you to very accurately were very nice。

Syntax deal with many different situations that would otherwise require if and else if conditions。



![](img/21b34163574257a76dc38473419b00f6_2.png)
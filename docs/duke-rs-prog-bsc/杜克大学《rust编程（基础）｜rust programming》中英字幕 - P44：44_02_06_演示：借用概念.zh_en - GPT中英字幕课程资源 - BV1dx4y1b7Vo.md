# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P44：44_02_06_演示：借用概念.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/72c89a9eba92fb9e671d3a2e5952c9c6_0.png)

I've mentioned borrowing and I haven't really explained or dived into what borrowing is in rust。

 one of the things and you can see that。This example is heavily。

 heavily commented out because the reason is because this is kind of like a hard thing to grasp if you're coming from nonstically defined languages like like in this case rust like if you're coming from interpreter languages like JavaScript or Python。

 then this concept might feel slightly slightly odd。

 so let's go step by step and essentially there are a couple of things that you're going to get into trouble with borrowing concepts in rust。

So what it means is that you have a sense of ownership。

 like a concept of ownership and values and variables and definitions and can be borrowed like you're lending that for for a function and that function is going to do something with it and there's some certain constraints so let's start walking through some of the issues here So we have here a mutable vector which is kind of like an array that can be mutable we can make some changes okay so that's good。

 we're going to also define an integer which is number 10 and we're going to have a string which is a hello world string al right so these compiles。

 there's no problem So let's start a bit by bit here but this can get really tricky so there's an integer own integer function and then we're printing mind end so we're passing in passing in the my。

Into the own integer and then printing out from this is coming from right here。

 So what is going on with my end own integer， this function， it is taking the integer as an argument。

 that's x and then doing an x plus one okay so it's grabbing these is grabbing this x value and then adding one。

 So pretty pretty straightforward nothing out of the ordinary。

 So you might get used to something like this and then be surprised by the behavior with string。

 So let's take a look at what happens with string。 So own string we're doing the same thing。

 we're passing the string。 So we create a string right here and then we're passing it here。

 So the function is this one。We're taking the string the string argument right here and then we're just printing it。

 we're not modifying we're not doing anything to it。

 So let's just go ahead and print it print it right here。

 So when I save that and immediately this goes into red。 So what's the deal。

 I just passed it in for a function that is only printing it like I'm not modifying it。

 I'm not making any changes， what is the actual deal Well with strings unlike booles and integers。

 this is not going to be allowed behind the scenes behind the scenes for integers like this one's right here。

 rust is going to copy the value because that's very cheap to do so you don't have to worry about it but the same thing with booleans but with strings not so much because strings the size of the string is not known at the compilation time So rust can be confident of just copying that value。

 So what are we gonna。Do here to comply to make these a little bit easier and not get into problems。

 Well， there's a couple of things that we can do here。 One thing is that we can say， hey。

 let's just make this own string borrow borrow， not own because this is taking this is taking ownership。

 So this thing right here says I want to own this parameter So instead of doing that。

 we can say we want to borrow it， that's what the m percent is and now instead of passing it like that we are going to pass it with the m percent。

 So as soon as I add that m percent， everything runs and the compiler is happy。

 why because when I pass when I say is I'm going to send you an m percent。

 that means hey I'm borrowing I'm blending you these these argument in this case S and that there are certain rules。

You can just go ahead and be messing with that。 I'm just borrowing let let you borrow that。

 but I'm still owning that right before I was actually just not doing that。 So if I remove these。

 let's actually look at the what the compiler error is going to be。 So I'm going run it。

And then get into the actual the actual error。 So what we're having here is a move。

 So this is a move and why is's called a move because I'm moving the ownership of string。

Wwhich is is a my string， which is a type of string and that moves over to own string。

 so value moved here is key and you will see these similar messages sometimes it's copy and we'll see what in a second word copy means。

 but here is value moved and value borrowed here after move， it means that hey。

 you can't really print， you can do anything with that afterwards。So again。

 you can see here that the definition of this function takes ownership of the value it says， hey。

 this is mine now， nobody can access it， nobody can do anything with it。

 so either you passing the am percent or make it an an am percent so saying hey I'm borrowing like I'm letting you borrow this is fine。

Or you cant you can just do this， so if I comment this out。Right that will work。

 Or if I cut these and put it just before。Then that's， that definitely will be will work fine。

 But do you see the difference。 Like I actually， I actually cannot。

 I actually cannot do these because otherwise we'll get into trouble。 So there you go。 those。

 those are a couple of things。 and it similarly passes。 the similar thing happens with。With vector。

 if I say。If I want to do that， I'll get the red underline and we'll get into trouble and the has the value has moved。

 I can say that Im I'm gonna pass it in to vector。 and then this can be actually like that。

 actually in this case， it won't work because I added the mpers in the wrong place。

 I have to add it right here and that's fine and thats certainly a thing or a way to do this。

 Now another thing that you can do with this is to actually， well。

 I'm getting all kinds of errors here。 But one thing that you can do is actually instead of like you can see here that this is making some changes。

 you can actually if you want to modify something like a vector， yes， even if it's mutable。

 you can actually create a new vector， create a new data structure and return that and you will still be complying with the return type here。

 and you wouldn't be modify this one right here。 So in this case， vector that push says， hey I am。

Lending you this value， lendingending you this variable， do not modify it。

 and I'm not able to modify that right so in this case， if I wanted to make this。

 all this work as it is right now， I would have to create a new vector。

 So let's make use of compiler here and I want to say create new vector。

I'm going to say let new vector that looks good and then I'm going to say I'm going to do new vector that push。

 I'm going to say 10，10 is fine。And then instead of returning vector La push。

 which which is this one。I'm going to comment that out to make the compiler not complain about it。

And this one， too， I'm going to say I'm going to return。The new the new vector。 So in this case。

 if I do this， I'm gonna get a mismatch type because I'm returning， I'm returning these right here。

 that's I'm actually wasn't wasn't returning any value So let's actually return it and do that and save it and then we're good to go So we've made a lot of surgery here do this function to comply with it we've defined a return type now we're complying with that。

 and we have these mutable vector but then we're actually creating a new one and doing stuff to it and that's fine。

 So we're now we're not really using vector， but you could you could iterate over these values and apply them to the new vector and that would be fine and then you would do something like shadowing or creating a new variable when you are when you're doing things here so you could say you know let new vector the return type of that and that's fine and then we can say。



![](img/72c89a9eba92fb9e671d3a2e5952c9c6_2.png)

Itll printing that， we can say。We can say new vector vector right here。

And that would be fine because we're using the return value so in a nutshell that is borrowing and moving and copying values in rust it can be very complicated it is worth going through these notes because it will allow you to grasp even a little bit more what I just explained and the best way to do it is well to read all those compiler error messages and to try to make sense out of them with the concepts I just explained。


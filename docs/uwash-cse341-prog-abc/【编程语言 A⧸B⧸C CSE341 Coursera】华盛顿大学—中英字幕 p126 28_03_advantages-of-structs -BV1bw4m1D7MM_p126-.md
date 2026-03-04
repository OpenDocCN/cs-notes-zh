# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p126 28_03_advantages-of-structs -BV1bw4m1D7MM_p126-

Now that we've seen two ways to define our little arithmetic language and write a function that evaluates expressions。

 I want to emphasize the reasons why I think the approach withstructs is a superior one and it's good to have support for that sort of thing in your programming language so the idea here is to really contrast the approach where for each kind of expression。

 we just had one struck definition and then we got a bunch of functions for testing and accessing and building that kind of expression versus the first approach where we just did it ourselves using lists so we created lists where the first element of the list said this is an ad expression and then we use later list elements for the subexpresss and the thing I want to emphasize is thatstruct definitions are not syntactic sugar for the list approach。



![](img/b0f6a240ca1c88e8f4e6c67469538876_1.png)

![](img/b0f6a240ca1c88e8f4e6c67469538876_2.png)

So the key reason they're not。Is that when you call the ad constructor to build a new ad expression with thestruct approach。

 you do not get a list back。 So let me convince you of that。

 Here's the same file we had in the previous segment， we were usingstructs。

 And if I defined X to be add of const 3 and const 4。



![](img/b0f6a240ca1c88e8f4e6c67469538876_4.png)

That's a perfectly good ad。 If it prints like that， it is not a pair。 It is not a list。

 It is not a molt。Sorry， I'll multiply， that's what we call that other constructor。It is an ad。Okay。

So that's the key difference。What is really going on is it is like each struck definition is taking racket and adding a new kind of primitive data。

 which is the ad expression。 So the same way that cons is a pair and a number is a number addd makes things that are。

Ads。Now， of course， racket doesn't know that these fields need to be anything in particular。

 We could also have an ad just made out of 7 and 19 that's not correct in terms of how we wish to use ad but it is in terms of addd being a new kind of thing data that racket will allow us to make so that is that approach this is nice because if you try to use the wrong accessor functions for the for something。

 you get an error and that's good so that you don't silently do the wrong thing。 So again。

 x is just some ad， if I try to say treat it as a multiply and get the E1 field。



![](img/b0f6a240ca1c88e8f4e6c67469538876_6.png)

![](img/b0f6a240ca1c88e8f4e6c67469538876_7.png)

I get an error。 So by usingstruct definitions， it helps keep my ads and my multiplies。

 as well as everything else separate。 I can't take coter of X either。

 So I think I've made that point enough。 The list approach does not have any of these advantages。



![](img/b0f6a240ca1c88e8f4e6c67469538876_9.png)

Because all the things we're making with the add function。

 which is just a plain old racket function that returns a three element list are lists。

 they are con cells。So you can do all sorts of things in error that you might not expect to do。

 So you see some on the slides。 How about I show you some in the code as well。

 So now I'm just going over to the approach from two segments ago where we defined helper functions for everything。

 I've used capital letters here just to keep it straight in our minds。

 but I could define this X to be add of cons 3 cons 4。



![](img/b0f6a240ca1c88e8f4e6c67469538876_11.png)

![](img/b0f6a240ca1c88e8f4e6c67469538876_12.png)

![](img/b0f6a240ca1c88e8f4e6c67469538876_13.png)

Okay， it's a list。 And if I ask， is it a list， the answer is yes， And that's fine。

 But suppose that I wanted to do what I should do with the E1 function of x and get that cons 3 out。

 Well， I could instead take the car of the cutter of X。 And there's nothing to stop me。But worse。

 if I screw up and take the car of the car thinking I want the car of the cutter， I just get。Sorry。

 a cutter of the car or something。 I just， you know， I shouldn't be thinking about this。

 I shouldn't be thinking in terms of con cells。 I should be thinking in terms of ads and multiplies。

 and it's even worse because you would think in your head that calling the multiply E1 function on X would be an error。

 but it's not。 you just get the cons 3。 And that's because if you actually look up here。

 the addd function and the multiply function， the add E1 function and the multiply E1 function。

 They do exactly the same thing。 They both take the car of the kter of their argument。

 And so you can freely mix one with the other。 and you get a lot less sort of timely error checking when you program in this way。

So to summarize the advantages of thestruct approach， it's better style and it's more concise。

 Certainly that's probably the first thing you thought of is you just have one line with yourstruct definition and you get five functions for free。



![](img/b0f6a240ca1c88e8f4e6c67469538876_15.png)

They are about equally convenient when using data types correctly， even with the list approach。

 once you've defined all the functions you need， if you use them correctly。

 it is about as convenient as thestruct approach to use all of those functions。

 but if you misuse them and programmers always make mistakes， you get much quicker error messages。

 you get failures sooner from thestruct approach that often makes things easier to debug。😡。

I should add that with a couple features of racket that we're not going to emphasize so much。

structs are even better。The first is Raet has a very nice module system just like ML has a module system and in ML with our module system。

 we hid things by using abstract types Now Racet is a dynamically typed language so sometimes people wrongly think that in a dynamically typed language it's not possible to do type abstraction like we did in ML it turns out you can because of howstructs work if we put astruct inside a module and then only provide to clients of that module。

 the accessor functions but not the constructor function。

 then they won't be able to construct anything without going through our sort of functions that enforce invariance and do the right sort of thing whereas if your data is represented with lists。

 you can't keep anyone in your program for building any list that you want。

It could just create a list whose first element is the symbol ad。

 and it will appear like it's an ad expression， even though it might not have the proper invariance。

Second， racket has something called a contract system where you can put on functions and data types likestruct definitions。

 properties that have to hold， so you get even sooner errors and those properties can be user definedfined things such as the subexpresss of the thing in an ad have to also be expressions。

 that's not something I've shown you how to do here。

 but it's something you can do asstructs that again with lists it wouldn't make any sense because it's the same you know you would not put such a contract on all the lists in your program。

 you only want them for this new kind of data that you've specifically defined。



![](img/b0f6a240ca1c88e8f4e6c67469538876_17.png)

I should finish with one other thing which is to emphasize thatstructs really are a new thing we've added to racket。

 they're not something that you can code up with other features。

 a function in racket can't introduce multiple bindings like we just saw and even macros。

 which I showed you a little bit earlier can't create a new kind of data。

 what really makestructs special is this fact that when you make something out of a struct。😡。

It answers false to all the other types of data in the program。 It's not a number， it's not a pair。

 it's not anything else。 That's a key feature that programming languages can give you。

 but only via a built-in construct。 if you only build up new data out of existing kinds of data。

 then the things like number or pair or something has the answer true because you're building it out of some kind of data that already exists in your language。

And so those are the advantages ofstructs and why I find them a wonderful addition to a language like racket。



![](img/b0f6a240ca1c88e8f4e6c67469538876_19.png)
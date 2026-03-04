# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p22 21_11_nested-functions -BV1bw4m1D7MM_p22-

All right， in this segment， I want to show you how to define functions inside of other functions。

 when it's good style to do that， and how to do it in a way that's good style。

The neat thing about this segment。 What I find really exciting is I don't have to teach you any new language constructs to do this。

 All I have to do is point out to you that the let expressions we've already learned about have everything that we need。

 And the key point is that the bindings and a let expression are any bindings in the language and we've already learned that functions are just bindings So anywhere we have a let expression。

 we could have some of those bindings be functions that then can only be used inside that let expression。

 This is a very natural idea。 and it's actually pretty surprising that more languages don't have something like this。

 So why don't I show you an example and why don't I start this example without using that。

 just do this， the old fashioned way of having a helper function not defined inside of the function that it's helping So suppose that I define a little helper function count all this is going to do is take two integers from into and return a list of the integers。

😊。

![](img/d4c4cccea68934e18df0db6d3724bd71_1.png)

Between them。 So I'm gonna to do this inclusive。 So if from equals to。

 how about the one element list holding to or equivalently holding from。 Otherwise。

 let's start with from and then cons that on to the recursive call with from plus 1 and 2。

 So if you call this with arguments like 3 and 6， you would end up with the list 3，4，5，6。

 something like that。 Okay。But that's not the function I actually wanted。

 that was just a helper function， what I actually wanted was a function that counts up from1。

 so it just takes a single argument X of type int and well this is really easy now with our helper function just counts from1 to X。

All right， so let's make sure that works。 then I got that right。Okay。

 looks like I've got two functions there， count and count up from one， and I got the right answer。

Alright， now， this is fine。 This is good functional programming。

 unless this count function should really be private to count up from one。

 I don't want the rest of the world to be bothered with it or to know how it's implemented or anything like that。

 Then I can use a let expression for that。 So I could just say let in end。

 And then literally pick this up。😊，And say， I only want this count function to be in scope。

 to be in the environment over here。So now count can be used recursively because that's how function bindings work。

 It could be used for any later bindings in this lead expression。 I don't happen to have any。

 and it can be used in the body。 So this will also work just fine。

 And if I go over here to my reple and restart。And use the file again。

You'll see that there is no count function at the top level， if I try count， it's just not there。

But it's still a perfectly fine helper function being used to implement count up from one。Okay。

 so that seems good。 that seems like good style if we want count to be private。

 but now let me show you something even better， even more fascinating and quite natural once you get used to it。

And that is to recognize that here where I defined count， there's no reason to have a two。

Let's look at how this two variable is used when we call count up from one with some value for x。

 S we call it with seven， like we just tried out。Well， then x is going to be7。

 so we're going to call count where 2 is7。We'll say that one is not equal to7 and so on。

 Then we'll do a recursive call where we increment from， but two is 7 on the recursive call。

 just like it was before。 In fact， every time we call count recursively， two is going to be 7。

And yet。Why should we have to pass that around when we already have a variable that's a perfectly good value that we need。

 namely x。What if I used x everywhere I was using2？That makes perfect sense。

 because here in this let expression and therefore， in this function binding， X is in my environment。

 it's a parameter out here so I can use it。 Even this helper function can use X。

 So this code will work just fine。 but now we have some really strange style because I have this argument too。

 that I'm never using。So let's get rid of it。Let's get rid of it here。

 Let's get rid of it in our call。 And then sometimes people forget to do this。

 You better get rid of it in the recursive call， too。

So you don't have to write it in terms of two and then get rid of it once you get used to this style of programming and recognizing that you can use variables in the environment。

 we could have just written this version of count like this to begin with。Okay， now。

 let's make sure we got that right。 That's the final version I wanted to show you。 I've restarted。

Re includeclude my file， and let's try it out on 7。 Still works great。 Notice count is still。

 of course， not in the environment outside of the function that defined it。😊。

So that's the code I wanted to show you now let's just go back to the slides and emphasize a couple things about this。



![](img/d4c4cccea68934e18df0db6d3724bd71_3.png)

All。This is the version I showed you where we do have a local function a nested function definition。

 count is inside of count from one， but I'm still using this unnecessary two parameter so that's a good starting point to understand why this works and to understand that this is good style if count is only going to be used by count up from one。

 but if you want count to be usable in larger parts of your program。

 then you should put it somewhere where other code can use it。

Then the second version I showed you was this fancy version， if you will。

 where countant doesn't have a two parameter for this。

 the work it's going to have to be defined in some scope where you have the variable x so that you can use that in place of  two。

And I just can't emphasize enough that this is using all the rules we've already learned。

 We're just going to look X up in the environment where we define this function count and it's there。

 and it has the value we need， so we just use it。So when you can do this， you really should。

 it's certainly poor style to pass extra parameters that you don't need。

 why have a two argument when x will work just fine。All， so taking a step back。

 when should you use nested functions and when shouldn't you？Well。

 nested functions are great style If you want to make sure that the function you're defining is only going to be used there in that lead expression。

 If it's not going to be useful elsewhere， it just keeps your code cleaner to do that。

 if you're worried that other code might misuse it in some way like you need to call the function in a certain way for it to work correctly。

 then limiting the scope of where it can be used， makes it easier to check that。 And in fact。

 it makes it much easier to deal with any changes， you might make to that function in the future when you're maintaining your code。

 if you change a function， you need to check all the uses of that function And if you restrict where the function can be used。

 that process can be a lot easier。Now that said， nested functions are not always the right thing。

 and so this is a real fundamental tradeoff when you're developing software。

 you want to put your functions in a narrow enough scope that you can restrict how they're used。

 but a wide enough scope that they can be reused as much as is helpful in your program。

But in any case， we've now seen in ML how to define nested functions and how to do them in a way that's quite convenient and good style。



![](img/d4c4cccea68934e18df0db6d3724bd71_5.png)
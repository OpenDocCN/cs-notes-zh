# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p103 5_03_racket-lists -BV1bw4m1D7MM_p103-

We continue our introduction to racket by learning about racket lists。

 This will go quickly because racket lists work a lot like M's lists， in particular。

 the way we used ML lists in section1 where we used functions to access the pieces of a list。

 So let me just go over the primitives and then I'll write some examples and again。

 because it works a lot like an M， I expect this will not be too surprising in fact。

 it' will be reassuring to see some of the same ideas in a different language。

 the way we write the empty list is with the word null in M we would have written bracket bracket。

 the empty list we write null。

![](img/cd8d940b1305799b0db01a127b2b766f_1.png)

It's fine， by the way， if you have seen scheme， if this is different in scheme。

 you often wrote it parenthesis， parenthesis that will not work in racket。

 we will use null to write the empty list。If you want to build a list， use the function cons。

 it won't surprise us that in racket that's going to come first before the two arguments。

 just like plus comes before the arguments to plus。

 this is what in ML we wrote with colon colon between the two arguments。

 so cons will take an element in a list and create a list one element longer。

If you have a list and you want to get the head， use this built-in function car and if you want to get the tail。

 use this built-in function cutter， spelled CDR pronounced cuter。

 This is what in MLL was the head function H and the tail function TL and finally to see if a list is empty or not。

 we can use null question mark， which we often just pronounce null。

 or if you prefer null and this is what NML was the null function N ULL。

 so perhaps a little confusing that we write the empty list N ULL and ask if a list is empty with the null question mark function。

 but every language has its different names for things。

Just a couple more things on the slide that you see here if you wanted to build a long list you don't have to say cons of three of cons of four of cons of five。

 there's a provided function list that takes a bunch of arguments and makes a list out of those arguments so if you pass it n expressions it evaluates those n expressions and then makes a list of length N we had similar built in in fact syntactic sugar and ML for when we wanted to do this and finally I should talk about these names car and cutter why on earth would you have the function for accessing the first part of a list be called car and the rest of the list couldter don't try to figure this out in terms of English it's a historical accident going back several decades and sort of the original machines that this sort of language was implemented on these things should not be called this but it's too late we're stuck with them。



![](img/cd8d940b1305799b0db01a127b2b766f_3.png)

Okay， so that's everything we need， but it will make a lot more sense after we just write a few functions。

 simple things like we're used to。 So let's first write a function。

 I have a comment here sum all the numbers in a list so remember I could define a variable sum and then lambmbda take a list X's I prefer instead the syntactic sugar version of doing exactly the same thing。

 So I added that parenthesis and then the argument。 This is a one argument function。

 And now at this point， we're very comfortable with the recursive solution to this function。

 if the list is empty So I'm calling the null question mark function with my argument then0。

 it's the second argument to if the third argument to if will be a function call call the function plus with the result of calling the function car on x's i。

e the head of the list with calling sum recursively with the cutter of the list。



![](img/cd8d940b1305799b0db01a127b2b766f_5.png)

![](img/cd8d940b1305799b0db01a127b2b766f_6.png)

![](img/cd8d940b1305799b0db01a127b2b766f_7.png)

![](img/cd8d940b1305799b0db01a127b2b766f_8.png)

![](img/cd8d940b1305799b0db01a127b2b766f_9.png)

![](img/cd8d940b1305799b0db01a127b2b766f_10.png)

so that's the end of the call to cutter， the end of the call to sum。

 the end of the call to plus the end of the if and the end of the define。

 If you're not used the languages like this， you might find it funny that I ended with so many parentheses。

 It's incredibly natural。 You get used to it。 It's exactly that I have to finish all these calls。

 And then I have a perfectly good syntactic function。

 And I could go ahead and run this and try some of how about the list with3 and 4 and 5 and 6。

 and I would get 18。

![](img/cd8d940b1305799b0db01a127b2b766f_12.png)

![](img/cd8d940b1305799b0db01a127b2b766f_13.png)

Okay， no problem。 by the way， just while we're talking， we'll talk about this much， much more。

 but if you do something like this， this would quote unquote compile because there's no type checker to stop us。

 but we'll get an error And Dr。 Raett even tries to tell us where this error occurred in the code and it says that plus expects a number and you gave it a string high。



![](img/cd8d940b1305799b0db01a127b2b766f_15.png)

![](img/cd8d940b1305799b0db01a127b2b766f_16.png)

Okay， so that's our first example of a list function。 Let's do a couple more。 You know my favorite。

Which is a pen。 It turns out a pen is built into racket。 We could shadow it。

 but I find shadowing confusing。 So how about I call it my aend taking in two list X's and y's。

 By the way， in the previous segment and this one。 you'll notice I sometimes have hyphens in my variable names or here in my function name。

 that's perfectly allowed in racket。 It's a syntactic thing to get used to in many languages。

 we prefer to write it like this or like this。 All of these work。

 It's just a bit more of the convention in racket to separate the words of our variables and function names with a hyphen。

 Every language is entitled to its own conventions。 Okay， myopend is a function that takes two lists。

 X's and Ys if。

![](img/cd8d940b1305799b0db01a127b2b766f_18.png)

![](img/cd8d940b1305799b0db01a127b2b766f_19.png)

![](img/cd8d940b1305799b0db01a127b2b766f_20.png)

![](img/cd8d940b1305799b0db01a127b2b766f_21.png)

X's is empty。 Return Y， Otherwise， cons to cons， the first element of x's onto to the result of appending the rest of x's onto Ys。

 It was beautiful and ML。 It's beautiful in racket。 Let me show you those closed parentheses again。

 finish the recursive called to myopend， the call to cons， the conditional and the define。



![](img/cd8d940b1305799b0db01a127b2b766f_23.png)

![](img/cd8d940b1305799b0db01a127b2b766f_24.png)

![](img/cd8d940b1305799b0db01a127b2b766f_25.png)

![](img/cd8d940b1305799b0db01a127b2b766f_26.png)

This will work great。 so that's a pen。 And let's do one more。 about map。

 So we see something with a higher order function。 or it's just fine。 Again， this one is built in。

 So how about I call it my map map as an Ml takes in two arguments F and X's。 Remember in racket。

 this is really a two argument function。 So this isn't toppling or curing。

 And we know how map should work。 It should apply f to every element of x's and return a list of the same length with the result of those calls。

 So if you have a0 length0 list， you end up with null。 right， So I asked here is x's null， if it is。

 I want to return the empty list， I could have written x's here。

 But I wanted to show using the null value the variable null is essentially bound to the empty list。

 Otherwise， cons F of car of x's。 So what have I done so far， I got the head of the list。

 And I called。😊。

![](img/cd8d940b1305799b0db01a127b2b766f_28.png)

![](img/cd8d940b1305799b0db01a127b2b766f_29.png)

![](img/cd8d940b1305799b0db01a127b2b766f_30.png)

![](img/cd8d940b1305799b0db01a127b2b766f_31.png)

や。On that head of the list， with that head of the list。 So that's my first argument to cons。

 And then my second argument to cons， I can hit return here if I want it to indent nicely is the call map recursively with the same F and the rest of the list and the call to cutter called the my map called the cons。

 the if and the define。

![](img/cd8d940b1305799b0db01a127b2b766f_33.png)

![](img/cd8d940b1305799b0db01a127b2b766f_34.png)

![](img/cd8d940b1305799b0db01a127b2b766f_35.png)

so that's map。 And we can run all this。 And we'll see if we do that I do now have a function my append。

 The repple will say that's a procedure the same way。 Ml like to say that's a function。

 I'm not going to print anything else out for you。 My map is also a procedure。

 If I called it try to call my map with just one argument like lambmbda X X plus X1。

 This will be an error。

![](img/cd8d940b1305799b0db01a127b2b766f_37.png)

![](img/cd8d940b1305799b0db01a127b2b766f_38.png)

And that's because my map expects two arguments。 But okay。

 let's go ahead and call my map with two arguments。 In fact。

 let's define a variable fo to be the result of calling my map with this little anonymous function plus x and1。

 So what I've written just here， you see highlighted in the gray is just an anonymous function takes in one argument X that it's in its own parentheses and the function body is a call to plus with x and 1。



![](img/cd8d940b1305799b0db01a127b2b766f_40.png)

![](img/cd8d940b1305799b0db01a127b2b766f_41.png)

![](img/cd8d940b1305799b0db01a127b2b766f_42.png)

And then for my second argument to my mapap， how about icons 3 onto conzing 4 onto conzing 5 onto null。

 Of course， I could have used the list function to write this more concisely。

 But I want you to get it used to lots of parentheses。 This is not hard to read。

 that's the list containing 3，4 and 5。 close the call to my mapap， close the call to define。

 hit return。 that work just fine。 the repple doesn't tell us anything。

 It was happy to do that definition。 But if I ask it to evaluate fo。😊。



![](img/cd8d940b1305799b0db01a127b2b766f_44.png)

![](img/cd8d940b1305799b0db01a127b2b766f_45.png)

![](img/cd8d940b1305799b0db01a127b2b766f_46.png)

It will tell me that that is the list 4，5，6。 the way the Reple prints lists is with this quote and then the list elements。

 and that's fine。 that really is the list cons for onto cons5 on cons6 onto null and we'll see that because if I evaluate this。

 I will get the same thing printed by the Reel。 So that's our practice with list functions。 again。

 they work a lot like an ML。 they're just as convenient and powerful recursion is just as useful。



![](img/cd8d940b1305799b0db01a127b2b766f_48.png)

![](img/cd8d940b1305799b0db01a127b2b766f_49.png)

![](img/cd8d940b1305799b0db01a127b2b766f_50.png)
# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p32 31_04_datatype-bindings -BV1bw4m1D7MM_p32-

In this segment we start our study of data types， this is the language concept we'll use in ML to make our own one of types。

 which is a really important feature in programming。

 but ML does it in a very different way than other languages you've probably seen。

 so it take us a while to build up the ideas we need。

So what we're going to do is we're going to introduce our third kind of binding so far we've seen variable bindings with Val function bindings with fun。

 now data type bindings which start with the keyword data type these pack a lot more punch into one binding。

 so I have to tell you the different things that happen when you use a data type binding。

So what you do here is you see on the slide is you write some type name， any name you want。

 like my type is just a silly example to show you the pieces， then in equals。

 and then a bunch of possibilities。 These are separated by the pipe character。

 which you can think of as or。 So this says I want a new type my type。

And the way you make values of my type is either they carry an int star int。Or they carry a string。

 or they carry nothing。 So they are one of types。 Every value of my type is either going to have a pair of ints or a string or nothing。

 And we could have any number of possibilities that we want。Now。

 what I haven't explained yet are these things you see in the capital letters。

2 ints and stir and pizza。 I chose pizza just to emphasize that theres these can be any names that you want。

 It's conventional to capitalize them。 Some people even use all capitals。

 but I'll just capitalize them like you see here。 and these we call the constructors。

 So what is happening when you introduce a data type binding is that we are adding multiple things to our environment。

 both our static environment and our dynamic environment。 We're introducing this new type name。

 my type， and we're introducing the constructors， two ints stir and pizza。

Now these constructors have a couple purposes， but for now they are just functions that given values of the correct arguments return something of my type。

So two ins as a constructor。Is now in our environment and is a function of type int star int arrow My type。

 If you give it a pair of ints， you will get back a my type。

 Stir is a function from string to my type。😊，And pizza is not a function because it doesn't care anything。

 It already is a value of type， my type。Alright， so let's try this out in the Reple。

 I have the same example here。 Here's a data type binding。

 And then I just have a bunch of variable bindings that are using the constructors in various ways。

 So let's just load this up and use it and see if what we get back makes a little bit of sense。



![](img/738b3382edc399b7d1f4624bb18d3725_1.png)

So what the Reple prints out is first it evaluated the data type binding and it will just print the whole thing because it is relevant to what we see in the rest of the file and the rest of our program that we now have a type my type and it has constructors。

 pizza， stir， which takess a string and two its of instar int。

 the order of constructors in our binding doesn't matter。

 so as usual the repple has chosen to alphabetize them for us just like it does with record field names。

Then when I said Val a equals stir high， that makes sense。

 St as a constructor is a function from type string arrow my type。 So if we call it with a string。

 we get back a my type。 and that's why you see here in the reel that v A does indeed have my type。

But what's the value？Well， it turns out it is stir of high。 These constructors。

 you can also think of as as tags as things that are actually there in the values to say what kind of my type we have here we have the stir kind of my type and the underlying value。

 The underlying string is the string high。 So that's why a is bound to the value。 stir of high。

 So constructor applied to value is value is the value。 All right。

 if you just said stir without an argument。 Well， that is just a function from string to my type。

 So that's why Val B here is a function from string to my type。 There's a common programming error。

 you probably didn't mean that you probably meant stir applied to something。 but it does type check。

 and it just does something that you probably weren't expecting。On the other hand， with pizza。

 that makes perfect sense， pizza is a value of type my type。

 so if I have that as my expression for C， then C is going to be pizza。

 the same way A will be stir of high。 D similarly， if you want to use the two inch constructor。

 we'll pass it in instar int。 So in this case， we would evaluate 1 plus2 to 3，3 plus4 to 7。

 pass that resulting pair to 2 in。 And so the result is this value，2 ins of 3 comma 7。All right。

 once you have these values， you can use them however you want。 So if you say v equals a， of course。

 we look up in the dynamic environment， we get stir of high， and that is now the result of E as well。

 just like it has been with everything else that we've seen in the course。Right。

 so there are a few examples。 Let's go back to the slides and consider even some more。 Okay。

 so anytime you have a value of type my type， it's going to be made from one of the constructors。

 That's why it's a one of type。 And the value you cut back really does have two parts。

 It has what I'll call the tag part that remembers which constructor you use to make this value。



![](img/738b3382edc399b7d1f4624bb18d3725_3.png)

And then it has the corresponding data。 so for example。

 if you take if you have this expression 2 ins 3 plus 4， 5 plus4。

 that evaluates to something with tag part 2 ins and corresponding data part7 common9。

 Similarlyly stir if true then high else by would evaluate to stir of high。Okay。

So we now know how to build data type values， but whenever we introduce a new type in our language。

 we need a way to build the pieces and we need a way to access them。

For one of types and data types like my type really are one of types。

 there are two aspects to accessing the value。 We need some way to check which kind of thing we have。

 which variant of my type we have I。e。 What's the tag， which constructor made it。

And then we also need a way to get the underlying data if there is any， for pizza there isn't。

 but for two ants and stir there is。So this is a moment where it's worth looking at the other one of types we've seen。

 lists and options and seeing that they have these two aspects for accessing the values also null which tells you whether a list is empty or not and is some which tells you whether an option is some or none are the variant checking functions right。

 that's all they do， they tell you which tag is it the empty list or is it not the empty list。

 is it none or is it sum。Whereas the head tail and Valal of functions we've seen。

 those extract the data， head returns part of the list， tail returns part of the list。

 Valalive returns the thing under the sum， now we have an issue here what if you apply head to the empty list or val of to none while those raise exceptions for the wrong variant？

So now that we have data type bindings。One thing Ml could have done。

Is said that when you introduce a data type binding like data type my type equals all that stuff。

 in addition to getting the constructors， those functions to ins and stir in the constant pizza。

 you would also get functions for checking variance and extracting data。

 Maybe it would add to the environment functions like is stir of type my type arrow bo taken a my type and return true if that value was made from the stir constructor。

 and get stir data of type my typearrow string that would get you the underlying value if it is a stir and raise an exception otherwise。

 these would be direct analogies of how head and null work。

 null is like is stir head is like gettR data that would make sense。

 it would be a perfectly reasonable language， it would probably be easier to teach you right now。

 but instead Ml did something much better and we'll start studying it in the next section。



![](img/738b3382edc399b7d1f4624bb18d3725_5.png)
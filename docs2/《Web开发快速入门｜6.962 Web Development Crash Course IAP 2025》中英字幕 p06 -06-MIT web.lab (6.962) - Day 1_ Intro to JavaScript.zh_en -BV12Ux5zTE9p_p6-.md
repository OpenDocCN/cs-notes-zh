# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p06 -06-MIT web.lab (6.962) - Day 1_ Intro to JavaScript.zh_en -BV12Ux5zTE9p_p6-

Alright， can I have everyone's attention。 We're gonna get started of our last lecture of the day。

 Congratulations， you guys for making it almost to the end。

 I know that sitting in 26100 from 11 to3 is kind of a marathon。 So thank you guys。

 y'all are amazing。 So the way this lecture is going to work is it's on basic JavaScript we're assuming that most of you guys are coming from a background where you have some programming experience in a language like Python because that's what most of the MIT classes is teach。

😊，And most of you guys are probably not gonna have experience with jascript specifically。

 So this lecture is designed with people from that background where we're just gonna quickly like blaze through a bunch of jascript syntax。

 And then you can just sort of look at the slide， map it into mentally how it lines up with what programming you already know like。

 oh， this is this syntax is a little bit different this way。 And then you should be good to go。

 But if you have no programming experience at all， this might be a little bit fast for you。

 in which case we recommend a resource which is gonna be linked on our website that will go through the basics of coding and jascript more step by step。

 So if all of this flies over your head， don't worry， just go into that resource after class。

 and then you'll be able to get caught up。😊。

![](img/5bddf958ef7be8f24b217b4a8fd082f9_1.png)

So。Earlier， we talked about H T L and CS SS， H TM L being sort of the bones of what your website actually has in it。

 And then C， S S being the presentation of it， making it pretty， etc。Now。

 how ja fits into this picture is if HTML is the bones and CSS is like the clothing and stuff。

 then JavaScript is like the organs and muscles that make everything work。

 So JavaScript is a programming language that takes the content of a web page and manipulates it。

 So it's what allows the website to change as you're interacting with it。😊。

And it's used by basically every website in existence。And it is not related to Java。Please just note。

So where we run jascript code is there are a few places we can run it later today before class tomorrow。

 you guys are going to need to install node Js， which is a program that allows you to run ja on your own machine。

 But every all of our web browsers know how to run ja。 So if we。😊。

Want to run JavaScript and if you want to play around with it， I'd recommend opening up the console。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_3.png)

So you can do that by going to inspect element here。Opening up here。

 And then the console is going to be one of these tabs here。And then。In the console。

 I can type in any sort of JavaScript I want。 I can print something。That's a typo， but whatever。

And I can do math。2 to the power of three is 8， etc ce。

 I can run any jascript that I want in the console here。And so for the time being。

 we'll be using the console to just play around with it。 Feel free to open up your computers。

 open up the console and just play around with things as I'm going through a syntax。😊。

So now back to actual JavaScript。

![](img/5bddf958ef7be8f24b217b4a8fd082f9_5.png)

Javascript has five primitive data types。 So if you notice in some languages， such as Java。

 they make a distinction between int and float， like integer types and ones with decimal points。

 Javascript does not。 So everything is just a number or a boolean true or false string or jascript has these two funky types called null and undefined。

 We will get into what those are later。 They're a little bit tricky。For operators。

 things pretty much work exactly as you would expect。 You can add subtract， multiply。

 raise something to a power， divide and concatenate strings。😊。

But the thing that doesn't work exactly as you would expect from most other programming languages is comparing things。

 So if you want to compare whether two things are equal， typicallyy in Javascript。

 we use the triple equal sign， or if it's not equal， the exccclamation point and2 equal signs。So。

In most programming languages， we would use double equal sign to compare whether two values are equal。

 And Javascript does have the double equal sign operator。But so question。2， double equal s 2。

 Is that true or false， Open hand true， closed hands false。Yeah， it's not a true question。 It's true。

 What is this。True or false。Okay， I'm getting a big mix。

 like maybe half and half for true and for false。 So in most programming languages。

 we kind of want this to be false because if we have two things of different data types。

 those are different entities。 In memory， we can do different things with them。But。In Javascript。

 it doesn't do this In Javascript 2 double equal sign2 as a string is true because jascript performs type coercion。

 So it just converts one of the types to be the same as the other type before it compares them。

 which is generally what we don't want in programming because we don't。

 it causes a lot of unpredictable behavior。 And so in jascript。

 basically the bottom line is we always use triple equal sign when comparing things。Alright。

 let's go over some pretty basic syntax。 Javavascript has a semicolon at the end of every single statement。

 So any command that you do ends in a semicolon。😊，You。

 it doesn't matter whether you indent things properly or not。

 So if this was a complete garbage mess with no indenting whatsoever in white space all over the place。

 Javascript would be able to execute it just fine， but please indent things properly for readability。

You use curly braces to denote where blocks begin to end。 So in Python， you would have a function。

 the function signature and then a colon and then an inegent block in JavaScript， it's different。

 You use an open and closed curly brace to indicate that block。And similar Lily for loops。

And then you can make comments using the double slash。So in jascript。

 defining variables is kind of different from how you would have done it in most other languages。

 The standard way of defining variables is by using the keyword let。

 So you use let your variable name。 And then you can set it equal to something。

Convention for naming variables is Caml case。If you're like me。

 you will start coding in jascript and then use the snake case with the underscores and everything。

 And then you will be sad because your code base is not up to Javascript convention。

 So use Caml case。So normally， we use let。 but if we have a variable that we want to where。

 we don't want to be able to reassign later， we use cont。So if we say conant answer to life equals 6。

1，4，8。 That's the old course number for Weblo。And then we try and reassign this variable to something else。

 JavaScriptscript will give us an error。You might ask why we bother using constant at all because let just does the same thing。

 but。It's generally safe code practice to define something as constant。

 If you know that you're not gonna want to change it so that if things change later。

 jascript gives you an error， you know somethings wrong。

And then there's also another keyword that you can use to define variables in JavaScript is called V in old。

 if you Google around， you might see code that uses this。Basically， just don't use it。

 We don't use that anymore。 technicalically speaking， var is function scope。

 So a variable defined with var exists within the function that it was defined in。 but that is。

Very different from any other the way any other programming language works。

 where your variables are typically block scoped， defined within whatever curly braces they're defined or that exists within whatever curly braces they're defined in。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_7.png)

And so just don't use Var。 It's kind of sad。Any questions on what we've gone over so far。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_9.png)

All right。So null and undefined are two things that you might not have seen before。

 undefined is means that you have not assigned something of value yet。 So you can declare a variable。

 let first name and then a semi colonlon without assigning it any value。

 And then jascript will automatically assign that the value of that variable to be undefined。

And alternatively， we can also use null to explicitly say there is no value for this variable。

 And yeah， if， just， if in the purchase of your code。

 you want to know whether this variable has like no value。Pretty simple。 Con dot log。

 print something。And it's good for debugging。 So you can put console logs all over your code。

 and then I'll print out things that are useful for you to know。Oops。Okay。

 jascript also supports template strings。 So if you want to， normally。

 you define a string using the quotation marks， regular quotation marks。

 But if we define a string with the back tick， which is in the top left corner of our keyboard， then。

We can。Put in little bits like this that have the dollar sign and then curly braces。

 And then inside those curly braces， we can put any jascript expression we want。 So basically。

 this will evaluate this jascript expression， multiply these two variables together。😊，And then。

Stick that right into the string。So these are called template strings。Another way of debugging。

 if you want， you can use an alert， which will generate a pop up on your Web screen。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_11.png)

Okay， any questions about what weve covered so far。 Sorry。

 we are just like blazing through this one thing at a time。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_13.png)

Alright， so for arrays， this is pretty similar to lists in Python or whatever。

 but we can fill our array with literally anything we want。

 Remember that in all programming languages， arrays are zero indexed。

 which means that the first index， if we want to get out the。😊，Element at index 3 of pets。

 which is what this is doing then。This is index 0。 Thiss index 1， index 2， index 3。

 So this one is bird。This is not index 1。And then we can replace。

An element of our array with whatever we want。 So if we want the second。

 the element at index 2 of pets to be hamster， then we goes index 0，1 to replace that with hamster。

Any questions on this？Okay。And then another thing we can do with arrays in jascript。

 that's kind of unique to jascript。 is push and pop push allows you to just add something directly to the end of the array and pop takes something off of the end of the array。

 So here we're popping off。 We have cat， dog， Guinea pig and bird。

 We're gonna pop off the last element， which is bird。 And now our array looks like this。

 And then we're gonna push rabbit onto the end。 And so now our array looks like this。😊，Gions。Okay。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_15.png)

Conditionals work as pretty similarly to every other language。 We have if， if elsesif and else。

 So if whatever value is stored in our variable hour is less than 12， it'll print this。

 but if it's not less than 12， then it will go on to the next statement here and check if that is true。

 if it's so if it's not less than 12， but less than 16， then it'll print this。

And then if it's not less than 12 or 16， but less than 20， it'll print this。 And then finally。

 if it's greater than 20， it'll print this。O。An indentation is good。

 but not necessary for your code of work。While loops also pretty familiar。

 You can define some kind of variable and then perform an action as long as this variable is satisfied。

 So if we set Zig to be one， then。It'll go here。 check if this condition is true， if it is。

 which it is because E is one， then it'll go execute。What's inside of here。

And then come back up here。 check if the condition is still true。 If it is。

 we execute it again and so on and so on and so on until this condition becomes false。

 So this block of code will print everything up until and including 1024。

 because we console dot log at first。 And then we go back up and check if it's less than 1000。

And if we want to iterate through an array， we have to do this funky thing。

 which you will have seen if you're familiar with Java C or one of these other languages。

We define an array， define a。Index that are variable that contains the index of our array that we're currently looking at。

 So we'll set it equal to 0。 And then we iterate through every index of the array until we hit the length。

So if the length here is four， so this is four elements in the array。Then。We're going to。

 I is going to start at 0， and then it's going to keep incrementing until I is 1，2 and 3。

 And then once it's equal to the length， because remember the length is 4， then it will stop。

 So we'll iterate through indices 0，1，2，3 and iterate through the entire array。Any questions on this。

系。And then if you've seen array iterating through arrays in Python。

 this might look a little more familiar to you。 This just iterates not through the indices of the array。

 but through the elements themselves。 So we define a variable constant animal。

 and then we say of pets。And then， that will。And then animal， sorry。

 jascript will just keep going through and reassigning or reelaring animal to be the next element of the array。

 So animal will be at first， the string cat and then the string dog and then guinea piggan bird， etc。

Questions on this。And now we're going on to some more complicated stuff In jascript。

 There are some things that we don't have primitive data types for。

 more complicated entities that we want to represent in code。

And so we can use something called jascript objects。

 This is kind of different than objects in most other languages。

 most other object oriented languages。 A jascript object is more similar to a Python dictionary。

 because it's just a set of keys and values。😊，And you can。

Access the properties of an object using the syntax。

 It's very similar to up a dictionary in most other languages where you use the square brackets and then the string for whatever。

Whatever the property name is， or you can use a syntax that's more similar to objects in other programming languages。

 such as Python。By using the name of the object， which in this case。

 we're defining as a car and then the dot and then the name of the property。cusestions on any of us。

All right。And then something kind of special that you can do in jascript is object de。

 If you want to get multiple properties at once， then。

You can either use multiple lines like this and just set two variables。

 make a model to be whatever we pulled out of this My car object， or we can also。

Put these fancy little curly braces here and stick， make and model in here。

 And then this code is exactly equivalent to this code。

 So its just a shorthand way of assigning variables to the values in a jascript object。

 And we'll probably be using this a bit in our web programming。😊，Okay， so earlier。

 we talked about equality where we can check if two primitive values are equal using the triple equal sign。

However。What does this mean for arrays and objects， so。

If we have two arrays and we initialize them with the exact same values。

 But then we do triple equal sine。On these two arrays。We get that。 This is false。

Turn it and talk to someone next to you why you think this is the case。Yeah。Yes。2。

I'm going to pull it back。So the reason why these are false。

As I'm guessing a lot of you know is that object variables are references。

 So they point to the location and memory where this is stored。 So what we're doing when we say。

 let person  one equal this is we're creating a new object。😊，Okay， oh， wait， wait， Sorry。

 I was gonna do this on the board。So when we create a new person one object， we are。Creating a new。

Variable in memory。 some new object。That has named Bill Gates。Sorry， my handwriting is terrible。

 And then we say person one is pointing to that。And then online line， too。

 when we create a new person， we create person， too， we're creating another objective memory。😊。

That also has name Bill Gates。But， and we have person 2， pointing to that。

And when we check if person1 is equal to person 2 with the triple equal sign。

 then we're checking actually whether the location of memory that person 1 is pointing to is the same location of memory as what person 2 is pointing to。

 And they're not because they're different。😊，Places in memory， even though they have the same value。

But if we were to do something like the code we have here on the bottom where we say we create a new object with the name Bill Gates。

 but then。We define person 2 by setting an equal to person 1。

Then they're pointing to the same location of memory， and。This will evaluate to true。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_17.png)

And because of that， that also means that copying arrays in objects is not so easy because if we。Had。

Array pointing to an array 1，2，3。 And then we set copyright to the array similar to what we had over there。

 We have two variables pointing to the same location in memory。

And so if we do something like copyright at index 1 is equal to 10 gazillion。

Then it would update and edit not only copy array， but also array because they're pointing to the same array in memory。

 So this will not work。 This will make you sad。With lots of bugs。

 But you can copy arrays and objects using the spread operator， which I mean。

 what it does is it literally just takes all of the elements of this array and unpacks them。

 And then we can create a new array or a new object with them。😊。

Any questions on any of this that we've gone over so far。All right，y， then。We are moving right along。

Last main topic for today， functions。Functions take in an input and do something with it。

 And sometimes we want to return an output value。 Sometimes we don't。

The jascript function syntax is quite different from what you have seen in other languages。

 So in jascript， there are multiple ways to define a function。 So if you go poking around online。

 you might see different ways of defining a function。

 But the way that we're gonna use for Webla takes in。Parameterters in parentheses。

 And then it has a little arrow。 And then it has the body of the function and curly braces。

 And this is kind of nice because it sort of mirrors this diagram that I have above where we have our function that takes in an input and feeds it into the body of a function to do something with that input。

😊，哎。So here's an example of a function definition。 It takes in a temperature in Celsius and then feeds that into the body of the function where we're computing the equivalent temperature in Fahrenheit and then returning it。

Any questions on this code？Cool， I'll give you a minute to like， digest it。Allright， and so。

If I have this function definition that exactly the same as what I just showed you。

The only problem with this is that we can't quite call this function。So just think for a sec。

 what do we need to add so that we can actually make this refer to this function in college。Well。

 for that， we need to add a name。 We need to have some kind of way of referring to this function。

 And so let's call， let's say we want to name our function， Celsius to Fahrenheit。

And so we have this function stored as stored a memory somewhere on our computer in this big gray box。

 And then we want to have a name or a variable that can point to that location in memory。😊。

And so in order to do that， we define a variable and set it equal to the function itself。

So cons just means that this cannot be reassigned where， where in memory this points do。

 which we don't want it to be。And then this is the name of our variable。

 We're setting our variable equal to this entire function。And then， of course， theres a semicolon。

And so the bottom line of this is that function， a function is this big gray thing。

 a value stored in memory， just the same as a string and int array， etctera。

 So that means that we can assign a variable to point to it。

 And that's how we give our function a name。😊，And then if we want to call our function。

 we use parentheses， just like any other programming language and put in whatever input we want。

 And then this Celsius to Fahrenheit of 26 will be 78。8。

 And then that value will be assigned to the variable room temp。Alright。

 and then as a quick preview to the lecture that we're going to talk about。

 where we're gonna to talk more about this tomorrow。 But as a preview。

 we can pass around a function just like any other value。

 So that means that we can give a function as an argument to another function。

 And we call that a callback。😊，So， one。As a quick practice。Actually， not。

 I'm gonna skip this for the sake of time， but。We have an example of set time out。

Which is a jascript library function that calls a function after a certain delay。

 So this function takes in two parameters。 of function to call and the delay。

 So if I call the set timeout function， I'm gonna say， okay， do this。

 whatever function I'm passing in after this many middle milliseconds。😊。

So how can we print our message Call this print something function that I defined at the top of the slide after 5 seconds。

So， give me。Actually， know it。Take a minute。 Look， Think about whether these。

 which ones of these are valid。 Talk to someone next to you。About which ones of these will work。

And raise your hand if you have any questions。I detect general confusion。

 So could someone raise their hand and。Ask me to re explainplain something about what they're confused about。

All right， in that case， I guess。I will just keep。Plowing forward， then。So。If you think a will work。

To give me open hand。 if you think it won't work， Give me close hand。Okay， I'm getting a mix。

All right。A does work。 So print something is a variable that holds the。

 that holds the value that is this function。 And so we're giving this function into the set timeout and saying。

 call this function after 5 seconds。😊，Give me open hands if you think B works。

 close hands if you think it doesn't。Also a mix。 So B does not work。V will call print something。

 So when you put these parentheses next to your function， that calls it right away。

 And so we're gonna call the function right away and then take whatever this function returned and pass that into set time out。

 which is not what we want， because this function returns like nothing。 No， no。

 or undefined or something like that。And raise it open hand if you think C works， close hand。

 if you think it doesn't。O。All right， most of y'all are getting it。

 C does work because this function here。Defin and C is exactly the same as the function that we set the variable to print something。

 So it does the exact same thing。Yes。Exactly， it will be a different object， a different function。

 or like define it a different place of memory。 but it'll be a function that does the same thing。😊。

Yes， so don't do B。 Don't call your function。 And you need， you need to pass in the function itself。

Alright，It like yall got C。 So I'm not going to spend time and explain it。

 But these are two functions that you might find useful in your projects at some point。 set interval。

 Call a function after a delay， set time out， Call a function at like every at at certain intervals。

 So if we want to call a function every like 10 milliseconds or something。

 we would use set time out and pass in our function as a callback。😊，Alright。

 this is slide is just here。 so you guys know that classes in Java exist。 They're a thing。

 We're not going to be using them in Webla。 So you don't need to know how they work for the purposes of Weblab。

 but they， they exist。Okay， and if a lot of this lecture went flying over your head， don't worry。

 that's very normal。 we have。I found this website online that I thought was pretty good。 It goes。

 It introduces jascript concepts pretty in a pretty begetter friendly way。

 And you can go through some exercises to practice so you can see that afterward。😊。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_19.png)

Okay， time for feedback。 if you can。Pull out your phones or whatever or devices and fill out this form。

 It only takes one minute。 That would be much appreciated。I'll give you one minute to do that。

 and then we'll move on to announcements， and y'all will be。Free。Just like。

 look at me and give me a thumbs up when you're done with the feedback form。 So I know。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_21.png)

All right。If you're not done with the feedback form， feel free to continue。 But for the sake of time。

 Im going to segue into final announcements， so。😊，Important announcement is that if you have not done the second part of homework 0 of our setup to install node Js on your system。

 you're gonna need that for class tomorrow。 So make sure to do that。 It's super quick。

 If you run into any issues with setup or you had run into any issues today that you weren't able to get resolved during lecture。

 Feel free to come to office hours，7 to 9 PM tonight in the basement of the status center right over there。

 or if you're new to programming and you just want to like you just want to talk about it with someone and we can。

 we can teach you stuff in office hours。 we have a lot of staff。😊，Another thing is team finding。

 So if you need a team， please join the Zoom。 Webla dot is slash zoom。

 or if you're on the zoom already， then that's great。😊。

We will have a little team finding mini mixer in like a couple minutes。

And then teams finalizing your team and submitting brainstorming and submitting 10 ideas for your website is due by the end of day the end of the day on Wednesday。

 So just have that on your radar。 And for recordings for today， you will have that posted。

As soon as we edit and finalize things， but you should be able to。

 I think you should be able to see the live stream still on YouTube like right after this is over。

 And then it should also be available on Panopto on Weblab do slash Panopto。

 We'll send out that link as well。😊，一。Okay， so if you need to find a team。

 feel free to stay here and just hop on Weblab do slash zoom。Yeah， thanks， Aby。

 a few more announcements。 We have a few extra shirts from last year。 It's free， free mergerch。

 You can go up to the top where Stanley and Daniel are to pick up free shirts。😊。

And there's also extra pizza。 So if you want extra pizza to take it， please。

 We're otherwise left with a lot of。Peter， we don't know what to do it。It's up。

I tried doingming like something with accountinging groups in the。



![](img/5bddf958ef7be8f24b217b4a8fd082f9_23.png)
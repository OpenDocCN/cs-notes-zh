# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p20 -20-COMP6080 - Javascript 🐻 Language Features & Syntax.zh_en -BV17RXGYuEaM_p20-

Hi， everyone。 My name is Hayden， and I'm here today to talk about a syntax introduction to jascript。

 Now， Javascript I'm sure is a language that you've probably heard about before through your friends or yourself。

 and it certainly has a reputation both in the positive and the negative。

 We're not here today to talk about whether it's good or not， I think it's great。

 We're here to talk about how to use it at the most fundamental level and a lot of the other things that we're going to learn in this course are built off these fundamentals。

 So the point of this lecture is so that you can learn the absolute basic principles of jascript that you can go and apply out there when we learn about no JS and the next lectures and jascript in the web browser and react Js and other declarative frameworks。

 whatever it is。 So we're pretty much just going to go through a whole bunch of examples that should demonstrate language features。

 There's not really any new ideas in programming。That are going to be thrust upon you here。

So thankfully， we're not explaining concepts as's very much just to how do you use this language。

 So starting off with one of the simplest examples here。😊。

You have a program and you have block comments and line comments at the bottom。

 That's exactly the same as the C programming language。

 One area where jascript differs is that to print something to the terminal or the console。

 you don't use a printf in C or a print like Python， you actually use a console dot log。

 That's like the equivalent of the print function。 And in this case here， just like Python。

 I'm printing both hello the string and on the next line。

 I'm printing the result of the one plusus2 addition， you know， that kind of statement。 Now。

 you'll notice that as we go through this， that this is actually be very similar to Python。

 So if you are familiar with Python3 is a language and the Python interpreter。

 you are going to find this very straightforward pick。 Now， how do we run these things。 well。

We can run these a couple of ways everything in this lecture that you see today can either be run in the web browser or it can be run on the command line with the node JS interpreter and in terms of setting up that interpreter。

 you can actually go to the comp 6080 website。

![](img/66087a5991774271c6a1069657ed2916_1.png)

啊。Give it a sec。 and if you go and log into the site， obviously。Like this。

 And you go to installation。 You will be able to see a section on how to get set up for the course。

 right， so like you can get set up to run the stuff on a web browser and you can get set up to run the stuff through the node interpreter。

 Now， there is a lecture on the node interpreter and we're gonna talk about that more in another lecture。

 But for now， I'll just kind of show you that you can you can run these in two places。

 So let me get those two places up for you。😊，So the first way that we can run this as I mentioned on the No Js command line interpreter。

 So if you have no Js installed and you're in that directory like this。

 I can actually just simply run node0 simpleim do js just like a python file and it will execute it and give me the result。

 So this kind of makes sense。 It's like okay I'm running this code I get hello I get one plus2 is3。

 The other place that you can run this code is you can run it inside of a web browser。

 So what I've also got down here is a page test hm where I've got an h1 tag at the top and then a script tag at the bottom with some jascript That's how you can run jascript on a web page。

 Now when I have this you might think well， this page printed hello and it's actually printing this top hello hello hello but it's not printing the string hello or I could call this hello3 and it's not printing the number3。

 and that's because where it's actually printing it is inside the console So web browsers are a little bit interesting and this will start to make more sense。



![](img/66087a5991774271c6a1069657ed2916_3.png)

![](img/66087a5991774271c6a1069657ed2916_4.png)

As we explore ja through the frontend lectures but with web browsers when you kind of print to the terminal it isn't there is no terminal to print on a web page because this is like a rendered image it actually prints to this console that's inside dev toolss but in the end。

 what's printed here is exactly the same to what's printed here everything that we're learning today in this lecture works in both the no JS interpreter on command line and it works in the web browser on the console there We're going to learn in the next lecture about the differences between those two and dig into that a little bit more but that's enough background。

 Let's talk a little bit more about the language so。



![](img/66087a5991774271c6a1069657ed2916_6.png)

Very simple。 I can print stuff to the terminal。 The next thing is。

 we're gonna to have a look at ways you can declare variables。 Now， like Python。

 it is a loosely typed language jascript， which means you have things like strings， numbers。

 decimals。Bolean， that's kind of like your base types。 Now， there is a bit more than that。

 in jascript， though， compared to something like Python。

 you can actually declare a variable as a constant or as just a normal mutable variable。 So again。

 in languages like Python when you just say variable value equals0。 It is by default mutable。

 and in jascript， we use the let syntax for that because the let here is kind of like saying I'm going to create a variable that can be modified and the constant to saying that it can't be modified。

 So if you try and run this at the moment， it's not going to print anything because there are no console logs。

 but if I tried to say modify constant value equals by I'll get an interpret error that says assignment to constant variable。

 whereas if I try and change variable value to buy it works。

 And you can also see here that I've changed a number to a string。

 and this is just as you'd expect from a loosely typed language。

 I can do that because nothing is strongly type。So that's buried。Simple。

 the main takeaway there is the constant theette。So next thing are some more complicated types in jascript。

 Obviously， we have a constant string， a mutable number。

 We can also have a notion of what we call objects in jascript。

 This is very similar to what you would call dictionaries in Python。

 maybe hash tables in another language， but it's essentially a key value store where I've got a key in a value。

 I've got you know my wildlife warrior， It has a name of name Vdy。

 it has an age of age which is 22 and a of F It's like its cisge here。

 Then we have we'll print hello world to console and now we're printing that to the console and you can start to see how how we can actually use the console dot logg。

 So I can print a variable directly in console dot log。 I can print it just by comm separating it。

 which will essentially just print it with spaces， or I can print it with。Age here。Plus。

 to concatenate。 So this combines things。 Unlike Python， you don't have to cast things to a string。

 Javascript's a bit more relaxed。 And then just another case here of printing out two things with a comma。

 You'll also notice here that the wildlife warrior。

ItIf we try and print out that whole object you will see that we kind of get the whole object so if I print out that we get the binddi and binddi and then their age and then we get their name age and again cisgender assuming that someone identifies that way so。

That's really the crux of it。 You can add more stuff here if you want， such as you know。

 height is 170 that will print it out too。 These are just objects。 Let me just undo that。

 So I don't ruin the code example。 Also got some more stuff with types。

 We got decimal string strings can be double apostrophe or single apostrophe again， just like Python。

Which is called things can be null undefined Booleans and then a few other things。In this case。

 you can see we're constantly reassigning the value the variable value because it's a let variable。

 right， You also see that we have this idea of null and undefined。

 Now this is actually a really tricky part of Java。

 undefined and null are both different things in Java。

Unfined generally as trying to say that this is literally nothing。 There is nothing defined here。

 It's the absence of something。 whereasas null is， it's very hard to explain。

 I would say null is a little bit more saying it's a thing。 It's just null。

 So undefined typically is trying to say it doesn't exist。 It's never existed。 whereas null is a bit。

You know， a bit more like it's kind of got a value and that value is saying that it's nothing。

Did that make sense， Probably not， But， you know， the main thing and the main trope to be aware of is not to interchange these two because they're not equal。

 So if you kind of want to represent nothing using undefined for that or nulls find for that。

 just don't mix those two concepts together。There are a bunch of other things that you can look into in your own time。

 like this symbol function。 But the point is that it doesn't have to just be primitive types。

 It's like other object based languages where things can be numbers or they can be whole objects or they can be lists and and various other things。

So now we'll move on to a slightly more interesting part of this， which is functions。

 So if we have a look at functions， Javascript is very interesting in that there's kind of multiple ways to define a function and this is both a great and a troubling thing。

 So one thing you'll see here is that I've got these three different types of functions。

 Now I'll just quickly take you through essentially the the three formats of a function in jascript right So firstly。

 we have if I have a function called add where I give two numbers and it's going to console log those two numbers。

1 and 2。 Now the sum of those two numbers， right， Very， very simple， silly function。

 I can call that function like this with one and 2。 Now， I'll just comment out the rest of the code。

 which we know how to do。 I'm going to run that。 I'll just run for functions。 and I get three。

 The other way you can write the add function is that you can write it like this。

 You can say that con add equals function like that。 And it's the same thing。 Now， I'll have to。

 I'll have to change the names of one of these。 but。😊，This syntax difference， I think。

 is really interesting because it's going to tie into a concept that we're going to cover at the end。

 which is the idea of first class functions， or the idea that functions themselves can be treated like variables。

 because you can see here what we're saying is not that there's a function called add。

 but that there's a variable called add and that's equal to a function。

 And this will do the exact same thing。 There's your output。 The third way。

 which is the way that we probably encourage you to write because it's a bit more modern。

 is you say con add equals one to like this。 Now， what's the difference here。 Well。

 it's really simple。 It's a lot like the second format except the function has disappeared And there is a equals greater than sign between the parentheses and the braces。

 It's just a bit more compact。 And that also gives you the same result。

 So they're like the three different ways to write to write a function。

The main benefit of the last way is that it's more compact， which is very helpful。

 So if we have a look here at the functions， you can see that we've got。

 I already let value beat something up the top。 So I can see here that value is a function with two parameters。

 It just prints those two things out。这体。And then here， I can say value equals function。

 So a very similar thing， just like the methods I had before。

 we're letting this be a function with one parameter。

And now we have another function that takes in bar and returns that。

 And then and then this is where we start to start to understand that functions can return things。

 just like every other language。 right， It's not just about console logging。

 like in in all of these cases above here。 These are functions that do something。 They console log。

 but they don't return anything。 This function actually return something。

 So in the previous examples， I was just calling ads like this。

 but I wasn't doing anything with a return value because it didn't have it。

 whereasas here I'm actually saying， you know what， the result is actually equal to F 10。

 So now I'm passing 10 into the F function and it's gonna return me the parameter bar plus one。

 which means result here will be 11。And then I'm going to pass the result 11 into value and value is defined as this function here。

 which should print pram equals 11。 You know， so you can really trace this logic through if you want to。

 And then at the end here， I'm not 100% sure why this is shoved at the end， but。Can't remember。

 but it's just to point out too that whilst there are certain number types in ja and string types and it is loosely typed。

 you can still kind of cast things a little bit like Python in this case here I'm like。

 I want this to be a big integer。 we don't really cover this much and there's no real need to kind of have us teach to you because it shouldn't be super critical。

 but it is also something else worth noting。So we've been talking a little bit about types。

 which really leads us on to the next example， which is looking at the type of function。 Now。

 this is a bit of a builtin function in jascript。 and even though just like Python。

 even though there's no types that you declare in jascript jascript still has a notion of a type for instance。

 here if you were to create a value。1 or a string or nullar undefined or true or symbol。

 all of these， if you tried to get the type of it will actually print out a value like it'll print out like so what TO does is it takes a value like a variable and it prints out the type of that variable。

 which would in these cases be number string object undefined bullole and right So you can see null here is actually an object Now when you hear people complain about jascript most of the time what they're complaining about quirks of jascript。

 for instance， it's kind of strange how null is an object Like that's a bit of a strange thing undefined beingfined。

truerue being a bull， all of these other things make sense。

 If you look at other types of objects such as this one here， you create a other types of variables。

 you create an object here with key has value key as a string。

 another key which has value 10 as a number。 if you try and print the type of value you're going to get object which makes sense。

 very strange that this and null have the same type， for instance。

 you have type of function when you create a function And if you do some other kind of manual casting like big end or int which we're not going into in this lecture。

 you'll also get those various types。 Sp of undefined and null。

 there's certainly some very strange behavior of these things。 Now if you create a variable。

 if you declare a variable but you don't define it like we have here on line one。

 then the type of that variable will be undefined like that。Now。

 here's where things get a little bit tricky。 I think this might be in a later example， too。

 but I just want to cover it here briefly。 if I say that cons a equals null and I say that cons B equals undefined。

 here's what you'll see， if we print both of them， you'll see that they print out somewhat as you'd expect。

 we get null and undefined。 where things get kind of weirder。 is if we check if is a equal to be。

That's true Okay， well， this will come into play in the next couple of examples。

 but keep that on your mind， right so？On the topic of types， continually。

 we've been talking about big ants and strings and saying how we can convert things。

 This is how you actually convert some of these things。 Now， the third and fourth example here。

 you don't need to worry about too much again because you don't do a lot with big ants and numbers。

 But one thing that you'll do often is converting numbers to strings and strings to numbers。

 So in this case here， if I've got a number called 10。 and I want to convert it to a string， right。

 I can just say， well， string value is equal to value dot2 string。Which in this case， is like。

Going to output a string。 And you can kind of compare the value， right， Like， if compare the types。

 If I print these out， you'll actually see。What's the complaining about？

Numb value has already been declared。 I'll call that one nu value 2， right I get 10 and 10。

 And you actually see that the node interpreter can tell that one's an int and one's a string because of how it's printing it on the terminal。

 So 10 the yellow text， in this case is a number。 And then similarly， I can take that string 10。

 and I can convert it to a number。 Now， this 10， you see here is not has nothing to do with the initial value。

 it's actually all to do with the base。 it's a little bit weird。

 but essentially when you turn a string into an int， you actually want to tell it what base it is。

 So in this case here if I had 50。And I try and console log nu value。 You'll see that I will get 50。

 But if I put this as， oh， let me， let me say 100， right like that。 I get 100。

 But if I change the base from 10 to 2， I'm gonna get 4。

Why do I get four Because what's base2 binary， So now it's trying to like convert this value up here。

 which was a number to a string。The string 1，0，0。 And then we're trying to convert that string to an intertegerb base 2。

 a bit weird。 Honestly， I've never used that before， but that's what that number is for。

 So it's there as 10 to say base 10， which is kind of what you just call a number。 So that's。

 that's kind of there， as you'd expect。So PAs end and dot two string are how we move between them。

And then we got on comparisons。 So we've been talking a lot about strings and numbers。

 So where things get very strange is on comparisons。 Now in Javascript。

 there are two ways to compare values。 You can compare with a double equals or with a triple equals。

 Now， in this case here， if I have a value 10 and another value， the string 10。Are they the same。

 Well， it depends who you ask。 So if we have a look at these first two console logs that print to the terminal here。

 you can see we get true and false。 So how the jascript a quality operator works is that a double equals is referring to whether the value is the same。

 whereas the triple equals is checking whether the value and the type are the same。 Now。

 you might think， well， how a 10 and 10 the same value。 Well， it kind of makes sense。

 they're both 10。 They're both 1，0。 Like maybe think about it a bit more。

 if you converted them all to a string would they be the same。 That's kind of what they might mean。

 not literally with， you know， is the value the same。 whereas triple equals is。You know。

 other values in the types the same。 Now， what this means is that you should always be using triple equals。

 There's pretty much no scenario where you would want to use double equals。

 If you only care if the values are the same same， you should take the time to just convert that。

To the same type so that， you know， you can use triple equals。

 The reason we like to avoid double equals too is because you get strange things like this。

See here how I've got this string called object object。 And here I've got this sum。啊。You know。

 this other thing here， this object with cat say meo， dog， say Wolfof。

 The problem here is that if you compare those two things。

When Javascript tries to turn an object to a string， you get this。Right。

 I'm not sure how to do that off the top of my head。 I think you might be able to say like。

Consel log， can you do this， Can you do string。A is a， let me see if this works。 This is impromptu。

Yeah， see you get that right。 So if I try and print。That object is a string。 I get this like。

 I get a literal string with all these ASII characters in it。 So here's the funny thing。

 If you try and compare if an object is equal to that string。

 it's actually true with the double equals because jascript coerces the object to a string and then compares the value and it looks the same。

 But the types they started with were different。 So that's why。

 that's another example of why we really want to use that triple equals whenever we can。😊。

So then the next part here is we're going learn a little bit about like， you know。

 we've kind of done this like really deep dive on types right like types types types。

 true and false bull and undefined。 Let's talk a little bit more about structures So we've already explored the idea of an object dictionary。

 whatever you will where we have over here you know， a series of keys and pairs。

 and we understand that we can print it。 What we haven't talked about is accessing it。 So again。

 if you if you lean on your python knowledge you can access values within a dictionary through its key like this with the object。

 So， you know， the object by the key is a value。The next thing， right， is that。

You can also do it just with this dot。 So you can say like either key with the braces in the apostrophe or you can just say dot。

 these are， these are literally equivalent。I think you would argue that maybe this one is a little bit cleaner The benefit of this one though is obviously that you can inject to variables like I could say like cons key equals key and then I could actually put key in there and treat it as part of a loop。

 you can't really do that with this method very easily。

 but you know they're both kind of the same and they're both able to be used interchangeably。

Ls or arrays in Javascript are exactly as you'd expect。 and very similar to Python。

 There is no distinction between arrays and link list。 There are just the idea of lists。

 or I think they're more commonly referred to as as， but。Doesn't really matter。 very similarly。

 it's like you have。They can be a collection of any object type generally you'd use the same type。

 you know， all numbers or all strings or all this in this case here though we're kind of saying well。

 let's get the first element， the zero with index as you'd expect， the type of it is an object。

A little bit weird right， there's no different typing for objects dictionaries and list arrays。

 but that's okay。 And then to get the length of the array。

 it makes sense that it's just a property of the array。

 So if you start thinking about arrays or lists as you know typical objects like in an object oriented language。

 then this is just a property of it that will give you the length。

 that makes a reasonable amount of sense。In newer versions of jascript。

 there are also explicit map and set types， which essentially are think of them like rappers for like the base jascript object up here。

 You do not need to use these， but you can a map， as you would expect。

 is essentially a key value store， A set is just a key store where you can add a key check if a key exists。

 remove a key and a map is very similar except you're adding a key value。

 you can check if there's a value at that key， you can remove a value at that key。

 you can you know the key and the value You can look into those more if you want。

 they exist in you know they're not in the old school versions of Javascript but they're still there so。

Yeah。Moving on to the next bit if we talk。If we move on from collections right so we've been through types and comparisons and collections。

 we're going start getting on logic for the next few examples， probably like the next five or six。

 So the first one is if statements in ja， exactly like what you'd expect pretty much the same as C to be perfectly honest。

 you've got your if， your if else， your if else， if else。

 you can do if statements without the braces， you can just say if condition in that and runs the statement on the following line。

 So very simple stuff there， you've got switch statements， again。

 I'm pretty sure this is basically identical to C in terms of its structure and layout。

 obviously the language itself is a little bit different but。Fundamentally。

 the the flow is the same case and breaks。 so again， not going to cover that very much。

One thing that。Starts to pull it away from languages you might have worked with before is some of the turnernary statements。

 So you've got like turnernary of statements here where you say， you know， condition。

 you give it a condition and then it executes something if it's true otherwise if it's false。

 So a good example here is， you know， if I say。You know， two old or like a grade equals。

 And then I give it a condition which is like mark is less than 50 than I say it's a fail otherwise I say it's a non fail like that。

 you know， So I say cons mark equals 45。 you know， and this is really the equivalent of an if else statement generally where we use turnernary statements instead of if else statements are when its it kind of follows a pattern where it's like if A then return B else return this A there's not like different logic。

 So you can see here the logic for the if and else case is exactly the same and it's kind of being reduced to a single value。

 That's generally where you use turnernary if statements Use extremely commonly throughout jascript。

 So it's something you should get very used to。A few other things that you'll see。

 I don't think we'll talk about these until later when we do some of the declarative framework react stuff。

 but you can also be a little bit cheeky with JavaScript if you want to。 and let's say we want to。

For instance， someone has a mark of 45 and we want to print their mark。 and I say， you know， node。

13 hero。Result。Yops。You know。啊。There's a few conditioners not defined， oh my Lord。

I don't think this code was meant to be run， I'm sorry。

 I'll add a note up that are not meant to be run。But if I just take like。

 if I just take this first little bit as an exampleca this will print for us right， here I get the。

 the 45。What I can do is if I want to only print fail when someone fails。

 normally you do something like this， you say if Mark is less than 50 console。log。Fail like that。

 Where if I want to make myself。You would argue thiss a little bit ugly。

 but you could also actually just say this。 Mark and Mark is less than 50 and console log。

 And what this is relying on here， because you see we got the same result。

 What this is relying on is just the standard programming short circuit approach whereby。

The language is treating this like an if statement， right， you know， with an if statement， you say。

 you know， if A and B， but what's happening here is that this is just executing as a statement and this condition is being executed。

 and only if it's true， do you execute the second condition。So this whole line itself here。

Would actually return a value， but we are discarding that return value。

 We're just kind of leveraging the the and logic here。 So if Mark is less than 50。

 then we go on console log this like that。So， you know， that's just a little bit of fun。

 That's not something you need to worry about， but you will recognise that later。

 probably like in week  seven when we talk about that。 So the next few。

Examples are to do with what we call the truthiness of a value， which is kind of a funny。

 a funny term in jascript。 But truthiness just refers to whether something is true or not。

 And it's kind of， it's funny that this is a topic at all。

 but it has to be a topic in Java because its truthiness behavior is very strange。

 So you can see here， true is true。 That makes sense。FF false always， that makes sense。

 Any string is always true。Any empty string is always， sorry， any non empty string is true。

 and empty string is false。A string of zeros。True and the number zero is false。Right。

 a little bit funny。 And the reason， you know， it's funny is because， obviously。

 if we console log give 0 equals 0， it says true， right， Like it thinks this is a true statement。

 even though。You know， you checked it Like it's， it's funny， right， Like think of it like this。

 It's like0 and 0 have the same value， but a different type。Okay。

 if they have the same value in theory， they should give you the same result when you do an if check。

 but they don't。 So the value N type 0 gives a different conditional result。 It's very strange。

 And to be honest， again， these kind of make it look like， oh my God。

 there's so much you have to remember。 But in reality， I don't think about this。

 you're not gonna to think about this。 And you're just gonna try it out if you aren't sure。

 this is more just trying to point out that there are some obcurities that you need to keep in your mind。

Some other examples， every number， except for zero is true。 null and undefined are falsey。

 We call them truthy or falsey。 So null and undefined are falsey。 all objects。

 all objects like this are truthy。 All symbols are truthy。 All functions are truthy。

 And you can kind of see what this has really gone down to is that the zero number empty string null and undefined are all falsey and everything else is pretty truthy。

 So it's fairly logical overall。 And then just a few other examples here。A few of。

 a few of my favourite ones here， because。😊，They do some strange things。 I'm gonna skip over。

 like there's a couple at the bottom。 Like if you go and create a new string or a new number。

 they're always truthy and you might be thinking what in the world is that It's a little bit confusing。

 but essentially this creates a string object。 And again， you might be thinking。

 what's the difference between that。 Well， let's try it out。 What's the difference between Hayden。

And the console log。New stringhaden。Let's see what the difference is here。Okay。

 one like they're both kind of strings， one of them is a strange string object。 generally again。

 you're not going to interact with string or number objects。

 but if if you use Java in like comp 2511， you might understand that there is a difference between say a primitive integer and a object integer。

 it's kind of a similar thing here， but again， don't worry too much about those bottom2。

 the ones I really want to draw your attention to to show you how strange Java can be are these two。

And what these two are is this what this is showing you is that when you try and take the string one and subtract the number one from it。

 what JavaScript does is it actually coerces the string， I believe。To be a number。

 and then it subtracts it。You can see we get the0 there。

 So it courses a string to a number subtracts it。 The result of this is 0。0， the number is falsy。

 So that never prints on the opposite side。 Well， on the same on the same principle。

 if you take the string 0 and you plus it like a unary plus。

 what happens here is that this turns in this gets casted to a number 0。

 And then the plus turns it to one， oh， I think actually， why does that one never print。

 I think I might have mistaken myself there。 So if we do this， we get0 as well。 Oh sorry， yeah。

 the plus doesn't sorry， it's not addition。 that's very silly of me。 that's like minus， right。

 So like if you put a minus in front of a0， It turns it into a-0 or plus 0。 very， very strange there。

 Again， those two examples are not something that you have to。Think too much about。

But that's the background， some truthiness of things。

 If you ever want to find out what the truthiness of anything is。

 you can kind of just console log it if you want to if you want to actually see how truth it is。

 you can do the coercion， which is the double exclamation mark。 And then what you want to convert。

 So if you want to see whether 1-1 is truthy， you can do that。 And it will show you that it's not。

 That's kind of a shorthand way of getting a true or false value without having to write if statements。

 anyway， enough of that， the last few examples have been very theoretical and just trying to tease out the language。

 But let's talk a little bit more about language features。

So we move on to loops now loops in JavaScript again， thankfully very。

 very similar to C you can see here we've got our four loops， our while loops， our do while loops。

 which to be honest I don't think anyone uses， but you get the gist。😊。

I don't think there's a lot to say here。 It's pretty much identical to see。 So thankfully。

 you can reuse a lot of that knowledge。 Gred Javascript does have some like four range loops that。😊。

A python like in the sense that if I have。Say， you know， a list of。Names。You know， like Hayden， Jake。

 Emily like this。 Then I can do a follow Ks name。Of names like this now。

I don't think we talk about this very much。In the other slides， so I'll just quickly mention it now。

What this will do for you here if we look at just the bottom parts so again a lot of this code wasn't meant to be run so it's getting very confused Hayden Jake Emily。

 so the syntax is a little bit weird but essentially it's saying that take a list and then for each item in that list we want you to take that take that item as a variable called name the one subtle difference is that if you use of。

It goes and gets each value。 If you use in， it goes and gets each index 0，1 and 2。

 So if you're looping through a list， typically you want to。呃。You want to grab the value。

 not the index。And a similar but opposite thing is true for a dictionary if you have say oh like an object。

 if you have， say you know name is Hayden and age is 20， not 20。

 where if you say four attribute of attributes， the dictionary， let's console log what happens here。

Um， it doesn't like it。All right。That's because the way that objects are set up is a little bit different。

You can see though， that if I loop over use the in for objects， I get the key instead of the value。

 but I can then use that key to look up the value like this。So you know。

 I go through all the keys and I print out the values like that。

 Now there's a little bit more to this， but just to start you off therere just the considerations to think about just you know you can do this like four range style looping in and of if you want to there is a lot more to the looping stuff there。

 but that should get you through pretty easily newer versions of jascript have classes in this case we've got a class called S I don't think I want to spend much time on these。

 you can work through them in your own time because they're just not use that commonly but as you kind of expect you can have constructors。

 you can have members， member functions， you can have member fields， you can use this dot operator。

There's another example with classes， you can use inheritance， so one class can extend another class。

 you can use static variables， you can do super construction。

 so again a lot of this would rely on knowledge that you might have acquired through like an object oriented language such as Java would be the classic example。

 though a lot of python carries through here as well instead of self you have this。

 so it's all relatively straightforward， but that kind of is the crux of it。Some other examples here。

 now we're looking at a meal class where we have a constructor that takes in a list of snacks and it populates like a class field with that list of snacks and then we've got two methods here and eat sum and a log calories and the eat sum just goes and loops through all those snacks。

 a log calories loops through them as well and they both just do different things with it。

Do should you use classes in this course， maybe I don't think it's。

You're often not doing things that are super front end logic heavy。

 but you can definitely try to do it if you want。 The one downside of classes is they tend not to be JSO serializable。

 so it's very hard to like export it to JSO， but that's okay。

 And then the fourth example with classes here is that。

How you might create that class so if I just go and say copy and paste these together like this。



![](img/66087a5991774271c6a1069657ed2916_8.png)

This should work now。Pizza， that's right。We'll just say that like， you know， snack is 800 like this。

嗯。That's okay。 A lot of this code， but， by the way， was never meant to be run。

 I'm just feeling in the mood to to run some of it。 But there's a little bit。

 there's a little bit of like， we're missing the other， the other classes here， so。

What we might do really quickly is just slap all of these things together。In a single file。

I'll go and take that and I'll put this one in this one too。 So now we've got our snack class。

 our pizza class， our crisps class， our meal class， which should use those。

 we create a list of snacks， which are pizza and crisp。

 we create a meal pass those snacks in and then we call a few member functions on it and then we get a result right So here like I mean。

 I'm not going to take you through what all this is。

 But have a look at the type of if we print out the type of meal， which was a class。

 you can see that we get a function。That's interesting。 Think about that。

 It kind of what it does there is it shows you how ja designed classes。

 they're basically the very sneaky function closures， we'll talk about closures later。

 but the type of meal is an object。 So if you think about a class as essentially a factory like it's a function that produces a new object meal itself is a function and then meal the meal you know uppercase meal class is a function。

 lowercase meal variable is an object that gets created So there's a little bit two classes there。

Last few things。We have a Fibonacci example here where this is just showing you how you can combine a few ideas like if statements。

 returns， loops， function calls， this is an iterative Fibonacci super fun I guess。

 but again not a lot to talk about here just showing you that you can do some interesting things with the language and then the last kind of two big things are on a run through are firstly mappro and filter。

What map produced and filter are are an idea where。

There are three really common things that you do when it comes to data manipulation in particular lists。

 One is to take a list and take a list of 10 items and go and convert it to a list of 10 modified items。

 or it's to take a list of 10 items and to select some from that list。 Now， if you've done comp1，5。

31 at unSW， then you've probably been taught this before what map produce and filter are in the context of Python。

 if you haven't done it before in you're a postgrad in particular。

 You don't actually need to know any of this either。 And I'm making it sound really hard。

 but it's not。 But the whole idea is that quite often because you can go and look at this example in your own time。

 But quite often if you have a list of numbers like this。

And you want to go and get all the numbers that are。

Less than five right this is what you might do New nus equals empty list for constant nu of nus if。

Num is less than5 new nus dot push。 pushes an array function。 it's like a pen。 You push to the end。

 I push numb like that。 And then I'll just console log new numberss。

 And then this will be the first number that we print out。 So we've got 23 like that。 You can see 1。

2，3，4。Filter。Is a much quicker way to do this where I could say new nus2 equals nus dot filter。

 And then what I do is I give it a function to filter that with。

RightNow this is going to tie into our next bit with the idea of first class functions。In JavaScript。

 you can actually pass a function。In is a variable so here I can call dot filter on a list and inside of that I'm going to give it a function to sort it so I'll create a function called lesss than five and what that's going to do is going to take in a number and it's going to return where the number is less than5 like this。

So now I'm going to pass that into filter。And then I'm going to console log new numberss too。

It's actually relatively straightforward， right， and it makes a lot of sense by saying like， okay。

 take numbs the list。😊，Filter it， which means go get all the items。

 search through them will go through one by one and choose whether to keep them or not。

 And it always returns a new list too。 That's a really important thing about like filter is that it's not modifying anything。

 It's always returning new items。 And this less than five function that's being passed in。

 It's calling every time it checks against each item。We can also make this more shorthand。

 We can say cons less than five equals nu。With the new function syntax。Right。

 same kind of thing again， we're printing out this line here。We can make this even shorter。

 and is this is why this example exists in JavaScript， if you emitm the braces。

It will return will return the next about like the next line。

 so this is really handy for one line functions， so if your function just has one line。

You can emit the braces。 And what it will do is it will return that next line， and therefore。

 you can drop the return statement。 So suddenly， if I take something like this， right like that。

And I just give you like a shorthand example， these two things are actually equivalent。

Less than five theres like that。Since this line is so short。

 it's very common practice to actually go and pop it up on the next line like this。And then。

What do we know here while we're passing this function into this filter。We're this。

 we're passing a function in as a parameter， but all this function is is just this here。

So I can literally copy and paste that and put it in there like that。

And it's a very strange series of steps that got us to this point。

 but if you take the time to go through them， it's like， oh。

 actually that makes a lot of sense because what happens is as filter is taking a function and that is simply a function that has parameter numb and it returns the result of nu is less than five which is a boolean value。

And this is cool because somehow we've gone， you know。

 now we've gone from this whole thing to filter numbers less than 5 down to this。😊，Right， very。

 very elegant。You could you could make this even more complicated here， for instance。

 like what do we know about？What do we know about this Well we you know we figured out that this is a shorthand way to do a function。

 I could say you know number has to be less than five and greater than one。so again。

 I could just go and take that whole thing and just dump it right there。Like that。

And theres my know that works the same。With JavaScript functions too。

 if your function only has one parameter， you can actually drop the braces as well like that。

 that's optional， you don't have to do that， but you know it's something you can do as well。Filter。

 sorry， so that's filter。I'm explaining this in the assumption that you understand filter map and reduce。

 but you haven't used them in JavaScript， if you aren't familiar with them you should probably go spend some time Googling them。

 but I'll just quickly demonstrate map as well because they're the two most common you use。

 same kind of thing with map。If I want to say turn all these numbers and double them。

 I would go and say create a function called well this is the old school way to do it。

 it'd say new nus and then like for each number you would like push number times two like that and then you print it out but the shorthand way is you would say nus dot map and then you would maybe pass in a double function I got my function double which takes in a number and it just returns nu times2。

But if I use the new function syntax can't double equals function。

 and then like the newer function syntax can't double equals that。

And then I can drop the parentheses around the parameter because there's just one parameter right and now because there's only one return line I can drop the braces in the return and now because the function is so simple I don't really need to define it I can just go and put it here now we've got this really powerful shorthand way where we are able to take a list and simply double all the numbers in it。

Like that， so now we've got you know a list of 246，8 10 1214。So it's really， really， really powerful。

😊，Map and filter and I would strongly recommend that you get comfortable using them This example here is one you can look through in your own time where it shows you how you can go and take numbers and get the even numbers。

 get the positive numbers， get the numbers over 400 I don't think there's any mapping here but that's okay a lot of filtering and reducing so map in particular I think is a really really really common thing to use so get get comfortable with these things。

😊，That ties up this example on like map and filter and also gives you a bit more background on Java functions in terms。

 you know parameters and shorthand functions。 we I try and save those for the end because earlier on。

 I think， you know， we're just trying to cover the basics， but。This leads us to our last bit。

Which is on something I've just done there where I passed in functions。As。

Varis and we're going to make our own example here to demonstrate this concept further because it's really important to understanding lots of things that are subsequent。

So first class functions are a really interesting idea you'll see these on the internet if you Google it like when I say first class functions again。

 it's just a fancy way of saying that in JavaScript functions can be treated as variables and what I mean by that is if I create a function here called。

Greeting and all it's going to do is return hello。Right， or again just to really。

Emphase this point further。 Let's make it shorthand。

 coneting is just a function that returns hello like that。

 Then I can go and make another function called。Print name。Which can take in a function。

And it can take in a name。 And it's just going to consoleci log the calling of that function and the name。

 And then I can go and call it。Print name with the greeting function。

 I should call this likeum function and the name of Hayden， right？So like。

 and this is something that we will use extensively and as very。😊，Oops， sorry。

Is very important to getting your head around。And again。

 I could simplify this further if I wanted to， but I don't think that makes it any clearer。

It's kind of just starting to get a bit confusing。And in fact， I might even just undo that。

 so it's a little bit easier。By the way， JavaScript is pretty relaxed about semicollinons if you haven't noticed already like here。

Didn't have semicols， I do。It's all right it'll figure it out so yeah they're Iprinting hellohead and you can take this like further and further where you know you could put it you could have greeting take in a function you know。

😊，Actually this will like really demonstrate the point so you might get this。

 I'm hoping you get this you think okay well reading is a function。

 print name is itself a function that takes in two variables， one of those variables is a function。

 the other one's a name and it does stuff with them now。The naming doesn't matter。In fact。

 if I just don't call it like JavaScriptscript doesn't think oh I'm getting a function and a name。

 JavaScriptscript just says I'm just getting two variables of stuff so it gets two variables of stuff and when I just print it normally it says。

 oh thanks one of those is a function， the other one is a string name there you go If I try and call this as a function I get a result if I try and call name is a function JavaScript gets confused it's like name is not a function。

I don't know what to do there。 So this example is relatively straightforward。

 where things get strange。Is when we start to like layer functions on top of one another。

 And what I mean by that is imagine that your greeting function takes in another function。Right。

 so greeting takes in， say a function that's like。You know。What would you say？Second part。

And what happens here is like we return hello。Plus， a space plus the result of second pot。

And we pulled that。Okay。And now down here， let's keep things really simple。I could say， well。

I'm going to simply。Cal grading now。And the second part I'm going to give it is another function。

 and that function might be like。Print there。This will just return there。You know。

 so it's trying to do hello there。 So now it's like I can call greeting and I can give it the print there function。

 And then if I console dot log。Greeting print there。 I'm going to get， you know。

 hello there like this。 And then you think， oh， okay， well。

What happens if I want to pass that greeting into print name？Well。

 here's what you can't do and you have to be really thoughtful about this。

What happens when I do this？Now this this might you might think this makes sense， okay。

 I've got print there， I might move that up the top core。

 I've got another function called greeting which takes a function and says hello and then the result of that function。

Now I've got a print name function which console logs the result of a function and the name。

 So when I call print name， I want to give it greeting。Which expects a function print there。

 and I want to give it my name， but this won't work。 I get an error。

 It says function is not a function。 And the reason for that is because what we've done here is we have not passed a function into print name。

RightI'll just call this O。Arg here is not a function。 Arg is of value。

Because greeting returns your a value， right， it returned hello there， so we actually need to return。

😊，Bit weird is a function。And all that functions is going to do is return greeting。Very confusing。

 Ho there Hayden。This kind of。Intimate understanding between functions and values is really。

 I think one of the biggest things that takes a moment to get your head around and the idea of passing functions through functions and those functions through functions。

In wrapping functions and other functions。 and I will talk about this a little bit in the closures lecture so you can go watch that after you watch another few。

 but。The idea here is very simple。Here I've got a function that returns another function that。

But passes in another function。 and all of this， The point is that all these things are variables。

 I can go and print them out。 I can go and print， print out， print there。I can go and print out。

Greing， I can go and print out， print name。 I can go and print out A， all of these things。

 I can print them all out。 They're all functions， but I can treat them like variables。

You know and and I think just whilst we're on this topic to really reinforce the point here。

 a really common thing that you will do by accident is that something will expect a function from you and you will give it a value so please keep that in mind and what I mean is that if you will have a print name function and you will come along and you will do exactly this you will say yeahep print name greeting hello there right because we know greeting does hello and there and then you'll give it the name Hayden and you'll expect this to work。

You'll be like， yeah， that should work and you'll get this error。 In fact， if it's in the browser。

 sometimes you won't even get this error depending on what you're doing。

 So how do you get around this， Well， we've done this already， I don't want to loop through it again。

 But what I want to explain is that。诶。If you're new to it， you're probably gonna do this。

 What we did before。 Probably gonna say， like my function equals。

And then you're just going to retire grading。And you're going to pass that in。By。

And I'll just keep the original line up the top here so that you can see what we used to have like that。

But what do we know about shorthand functions if I take this？Because it's a one line return。

 I can just get rid of the braces and do that。Right。En。Because it's so simple。

 I can just take the result of my function and copy it in。

 And what do you notice has happened to you， The line is like exactly the same。

 except that we just have this random。Pentheses and and equals error equals a side bracketet there。

 which at first， you might think， oh， that that's really weird。

 but it actually makes sense because this one here is the calling of a function。

This one here is providing a function， and that function's job is to call something。

So there subtlety between， you know。Calling a function and providing a function that later calls a function is is really critical。

 But again， we'll talk about that later。 This is probably a little bit confusing。

 but it will start to make sense。 And hopefully， we've just canvassed the background。 Anyway。

 that covers like a lot of the basics of。Everything we want to talk about so hopefully you feel confident confident to go and write some simple JavaScript with node or some simple JavaScript in the browser and thanks have a great。

 have a great day。😊。

![](img/66087a5991774271c6a1069657ed2916_10.png)
# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p25 24_PHP关键字.zh_en -BV1Lr421A75d_p25-

![](img/3350603b1a17d4ed4cfc72f93217d505_0.png)

![](img/3350603b1a17d4ed4cfc72f93217d505_1.png)

So an important part of any programming language is the keywords， and their reserved words， keywords。

 these are the words that you can't use for any other thing。

 meaning if you say the word class or clone or do or else，PHP is going to say。

 I know what you mean by that。 That has a very specific meaning to me。 and I'm going to ignore you。

 You might treat that as a variable， et cetera， et cetera， et cetera。 But that is reserve for PhP。

 And so you don't get to do what you want with that。 It just means that you have to avoid these。

 Most of these like case maybe or as。Class and。Some of these you might mistakenly use as a variable name or so just avoid these and sometimes you' get a syntax error so these are just the basic things。

Probably one of the weirdest things when I go back and forth between PhP and another language and I love programming in multiple languages is the fact that in PhP all variables start with a dollar sign。

 and that's weird it's kind of a throwback to pearl followed by a letter or underscore so after the dollar sign it's the same rules as to most variables。

 letters， numbers and underscores after starting within letter or an underscore。

 we tend to not use underscores unless it's sort of something internal so that we don't collide if you'm building a library and don't have a variable I might stick an underscore in the front of it that I don't want anyone else to see not that they can't see it it's just that you hope that there's no collisions。



![](img/3350603b1a17d4ed4cfc72f93217d505_3.png)

![](img/3350603b1a17d4ed4cfc72f93217d505_4.png)

![](img/3350603b1a17d4ed4cfc72f93217d505_5.png)

And so the weirdest thing about this is that if you leave the dollar sign off。

 it may or may not be a syntax error， and so you've got to discipline yourself when I'm coming from like JavaScript or another language。

 I will start typing it and leave the dollar sign off and then I cost myself bugs。

There's a little bit of weirdness when you leave the dollar sign off because there's a syntax where you can have something like x with no dollar sign and it's a predesfined constant that it seems to be zero。

 this may give you a non fatal error。Or it may just silently turn that into zero。

 It's not going to turn into2， right， it's not x equals2， that's not2 there。

 That's a nonexistent predified constant that might turn into zero。And give you an unfa error。

 On the other hand， if you put it on the left side of the assignment statement。

 it's going to actually give you a par error。 So all you mean is just put the dollar signs in。

 but PhP is a little weird when you make syntax errors。

Sometimes earlier versions of PhP would do things like this as an array that that is a key value array it maps x to value hello。

 and you could put x in square brackets to kind of look that thing up but PhP and early versions allowed that without the quotes JavaScript kind of has a similar kind of idea there that you can do it with it without quotes and so it sort of stick quotes in here these days it'll stick those quotes in there and it'll give you a nonfatal error。

 So again。

![](img/3350603b1a17d4ed4cfc72f93217d505_7.png)

I is just kind of letting you know that sometimes you if you don't use dollar signs it has a weird behavior so strings are a little bit different than in other programming languages and part of why I focus so much on differences is that I assume at this point you already know one programming language hopefully it's Python and so I like you am going back and forth between programming languages。

 Python， JavaScript， PhP， etc ceter and so I'm trying to highlight the things that are different。



![](img/3350603b1a17d4ed4cfc72f93217d505_9.png)

So strings in PhP are awesome， I actually like them。

 I wish other languages would do the kind of things that PhP does， but they don't。

 which sometimes gets me in trouble when I go from PhP to another language。

So you can use single quotes or double quotes， and they function a little bit differently。

 Backslash is used as the escape character。 That really is kind of an a C inspired idea。

 Strings can span multiple lines。They can just go and they can do a round， round round。

 You can start one and then stop it。 I love that。 I absolutely love that。 and double quoted strings。

 variables are expanded and variables have dollar signs in them。

 This is kind of one of the weird things about why there's dollar signs in variables and a thing that I absolutely love。

 but unfortunately it's not the same in any other language is dot is concatenation。

 which I think is awesome and plus as a mathematical operator wherein most languages。😊。

Even though I love PhHP， most languages plus as the concatenation operator for strings。

 so we'll talk about that in a little bit。So here is the use of a double quoted string。

 so double quotes and single quotes are different， so double quotes are I think a double quotes in PhP as smart strings。

 you can do more things in them so for example， a new line works in double quoted PhP string。

You can have embedded new lines。 You start the string here， and it comes all the way down to here。

 and there is a slash n here and a slash N。 the PP automatically adds， I think that's supernatural。

Very natural， I wish more languages did it， other languages。

 you have to work a lot harder to have a multiline string， and so this is quite natural。

You can have a new line in the middle of a string。 And so this will， you know。

 the new line will cause the text to go back to the beginning of the next line。

 And here's kind of the weird thing that you learned to love after a while。 It's both。

 it's both wonderful and dangerous。 So you got to be careful about it。

 If inside of a double quoted string。 you see a variable dollar expand。

 It actually puts the 12 in there。 So it wipes this out and reads the 12 that's in expand and puts the 12 in there。

 That's cool。😊，It's also dangerous。So we'll learn about when you don't use this。

 You certainly don't use this when you're producing SQL statements。 But actually。

 if you know what you're doing and you're careful about it。

 this is a really way to write really nicely easy to read code that makes a lot of sense。

 So single quotes I think of as sort of not such smart strings。

 And so single quotes start and stop strings。You can also have embedded new lines。

 so this one starts here and stops there and there's new lines。Slash n。

You can put double quotes in a single quoted string just as a normal thing。

 if you want to put a single quote in， you have to backslash it to escape it。

And this is something I don't like。This is probably my least favorite feature of single quoted strings。

 and that is new lines do not backslash n doesn't work inside of a single quoted string。

I have to sort of I'll sometimes do something where I do a single quoted string。

 then I'll concatenate it with a double quoted string just so I can put a new line in。 you know。

 I was like，h why do I have to do that？Sad face。 But just remember， that wasn't my idea。

 But if you put new lines in a single quoted string， a backs slash in a single quota string。

 it doesn't expand。 And the whole trick of dollar signs don't expand。 And that actually is good。

 I mean， I like that。 So， you know， when you're using a single quoted string。

 dollar signs are not going to expand。 You know， when you're going to use a double quoted string。

 dollar sign variables are going to expand。Comments and PhP are truly awesome。

 You can use comment style。 It came from C plus plus， which is slashlash to the end of the line。

 You can use the comment style from Pearl and shell scripting。

 which is pound sign to the end of the line。 and you can use the comment style from the C line。

 which is start of comment， which is two characters that goes all the way to the end comment。

 And so this is really nice。 we use this for document and code。 know。

 So if you write little API documentation at the beginning of some code that you're writing。

 that's really nice。 this is C plus plus， This is the C language and this is like Pearl。

And shell language。Comments， so they just made it， hey。

 why not take all the existing comment styles on the planet and use them all。

 which is really quite nice becauseuse again， I go back and forth between P P and lots of other languages。

 And so there we go。The output。There's more than one way to do it。Echo is a language construct。

 so you can say like echo dollar x， or it can be treated like a function， echo a new line。

 you can have more than one parameter， dollar x comma。

 and it does not add a space here there is no it just concatenates these things together and then there's a print statement it's actually a function that happens to not require the parentheses if you don't have the parentheses。

 the difference between print， they do the exact same thing the difference is is echo can have more than one and print can only have one parameter。

For whatever reason， I tend to use echocho all the time and not print。

 I think echocho came from the bashel， and then print came from Pearl， I think。

Certainly looks like it also came from Python。Yeah， it could be from Python。

 Pear and Python use print， I think。

![](img/3350603b1a17d4ed4cfc72f93217d505_11.png)

PP philosophy is like， hey， if you want to do it， you can do it。

 we'll let you kind of pretend you're in more than one language。

So up next we'll talk about operators and expressions。



![](img/3350603b1a17d4ed4cfc72f93217d505_13.png)
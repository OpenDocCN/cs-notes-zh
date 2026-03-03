# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p14 14_03_04_JavaScript语言特性.zh_en -BV1rNibBuEwD_p14-

So now we're going to talk about JavaScript as a programming language now we're just going to talk about like the syntax。

 so we'll start out， say with comments。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_1.png)

So I love the comments in jascript。 There are two kinds of comments。

 and they have to do with what languages did the influencing。

 And so the slash star star slash is a multiline comment， right。

 So this is all comment from here all the way to here。

 And you can have new lines is great for writing documentation。 That comes from the C language。

 Java also supports it as well。 And then the C plus to plus language has slash slash to the end of the line。

 Well that's much more like the pound sign comment in Python。 But I like both of those styles。

 I like using these for documentation sections， and I like these for short comments。 So nice。

 Thank you very much。 Light space and new lines do not matter。😊。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_3.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_4.png)

Statements and in a semicolon， it turns out that that's not technically true。

 But if you just pretend that all statements end in a semicolon。

 then if you move to Java or C plus plus or C or Ph B， then you're not like， oh。

 when do I have to put the semicolon on。 Well， in those language。

 you have to put it on just about everywhere。 So just put semies at the end of every line。

 And you can just pretend you're writing C。 And then when you get to C， be like， well。

 this is just like JavaScriptscript， even though under the。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_6.png)

And the implementation is very different， very， very different。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_8.png)

So here's just an example of some really nasty JavaScript where， you know。

 x equals3 plus5 times 4 on two lines and then this lines jammed up in console。og。

That's okay that it just doesn't matter， I mean JavaScriptscript in these seast languages just don't care what the white space is。

 they're looking for characters， you know， blah， blah， blah， blah， blah。

 blah semione and that must be the end of the line blah， blah， blah， blah， blah。

 blah semione and that's the end of the line so just the new line is just like another spacelike character ultimately in these languages。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_10.png)

Variable names。Are kind of normal， they can start with letters。 I mean。

 theirre letters and numbers and underscore and dollar sign。

 but they are not supposed to start with a number， and they are case sensitive。 Just please。

 we use case sometimes as a signal because different very kinds of variables。

 we like either camel case some or。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_12.png)

All upper case， I use case to signal things。And it turns out that。Because。

Because JavaScript sort of saw what PhP and Pearl looked like。

 they allowed dollar signs at the beginning variables because PhP and Pearl are the places where dollar signs are allowed。

 but it。When people started writing JavaScript， they want it to be more like Java。

 Java doesn't allow dollar signs in variables， and so there was kind of like this unwritten rule which we will come back to just don't start a variable with dollar sign。

 even though JavaScript allows it， just kind of don't do it it's not cool。String constants。

Single quotes and double quotes function the exact same way。 I like that a lot。 Stylistically。

 what I tend to do is I tend to use single quotes as much as I can in ja because ultimately double quotes are part of HTML and when I'm mixing my HTML in the ja。

 I tend to want to look at it and say that single quote is a ja quote versus a HTML quote So if we take a look at this little code you see like this text equal jascript that's in double quotes and it has to be So the one line and two line I could use single quotes or double quotes for that but for me I try to use single quotes as much as possible when I'm in jascript So I can take a look at this code and no HTML ja If I'm in double quotes。

 I'm generally dealing with HTML and because JavaScriptscript is sometimes writing HTML it's writing double quotes into the document。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_14.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_15.png)

Because it has to， because that's how HTML requires it。

So I have a single quote string that has a double quote in the middle of it because I'm writing HTML T in JavaScript。

That'll make more sense to you later。You can do either one and you'll see examples where JavaScript just uses double quotes。

 but I prefer single quotes as much as I possibly can。

Unnumeric constants are pretty much like every other language but。But。

There is only one number type in most languages， there's like an integer and a floating point。

Sometimes there's double and float， there's different kinds of long integers。In JavaScript。

 I think in a way they were smart and they basically had made one type。

 one numeric type called number。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_17.png)

And so for example， if you take five3， that is a floating point number， 1。666 repeating forever。

 if you want to turn that into an integer， you just trunccate it。Like Math。trunk。

 math is a library that's in JavaScript。Now when you get back in X。

 it's still a floating point number， it just is shown as an integer because you've chopped off the decimal part。

 and so you have to be careful because they're really floating point numbers， every one of them。

 some of them are shown as integers when you print them out， but in general。

 there are no integers in JavaScript。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_19.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_20.png)

So there's a whole bunch of operators plus minus multiply， divide。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_22.png)

Trunet。Those are pretty much like every other programming language。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_24.png)

嗯。More operators like the modlo operator。Modulular operator is the percent sign and that is the remainder operator。

 so 45 divided by seven is six remainder three and that remainder， you know， 45。7 is 6，42。

3 remainder three。 that three is what goes there。 So， so division。

With truncation will give you the six， but the remainder will give you the three。

And it turns out that that modulo is really quite useful。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_26.png)

If you want to do something every 1 hundredth time through an iteration。

 you take the iteration counter like 123 and if you modo 100 and the result is zero。

 remainder is zero， it's an even multiple of 100。And that means every 100 times you can do something。

It's we like modo。There are side effect operators， oops， come back。

 There are side effect operators K plus plus says retrieve K。

 have it be part of an expression perhaps and then add one to it store back down。

 So if I say K plus plus it says three， but then afterwards K has become4。

 So after it retrieved the K im printed it， then it turned it into4。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_28.png)

These are there's a very few places that we actually use these and then we use them all the time。

 but in general you can hurt yourself if you write too much of this stuff。

 there is a pre increment minus minus k and that says subtract1 from K then print it out which is3 and then the three goes back into K。

Then there are some side effect operators， j is equal to J plus equals is the same as J equals J plus5 and the same is true for all these things。

Actually， this is just that's a typo there， slash equals。Most people do not use these formats。

 I just show them to you in case you ever see some code。

 I always prefer to write my increments and decrements and divisions out it's not particularly faster that way it's just it's a syntax this comes from C all of these fancy bits come from the C language and JavaScript was just and Java do the same thing and so those two languages are represented here and so that's why these operators are here。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_30.png)

Comparison operators。All C style languages， one of the trickiest things you got to realize is that the single equal sign is an assignment statement。

 and I like to think of that as changing so the 10 is being stored into the J。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_32.png)

To say， is J equal to 10， this is like a question mark。 I wish this was like question equals。

 That would be like， is it equal to。 but that's not what they do。

 They decided double equals was the one that was the question mark。 And that's asking the question。

 I J equal to 10。 and it returns a true or false when it's evaluated。 So J equals 10 is true。

 J not equals 17。 That's exclamation equal。Again， I wish this was question mark equal。

 but you know that's going back to 1972， I had to catch them and say， no， don't make double equals。

 make question equal。Not equal， less than greater than less than or equal to。

Now there's a special operator。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_34.png)

And you see this in Python in the is and is not operator。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_36.png)

So the double equals is a comparison with type conversion。So it says。

 can the left side of the double equals the J be converted？Eventually， to become equal to 0。

 And so in this particular case。J is false， so it is of tight Boolean。

But a false can be coerced into zero， so false is equal to zero with some conversion。But then。Then。

If we want to compare two things in terms of both their type and their value with no type implicit type conversion。

 if I say is J triple equals 0， that says is J。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_38.png)

The same type as0 which is a number and has the same value。

 Well j is a boolean because it's true or false， and so this turns out to be false。

 so j is not triple equals right and j is not triple equals true。

 and so you have triple equals and not it's like not equal equal but I call it not triple equals。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_40.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_41.png)

So there's a whole series of logical operators much like that that return for you true and falsees。

 and so we've got our greater than， so we've got double ampersand。

 which is and so for the whole operation for the whole expression to be true。

 both sides have to be true， so is k greater than1 and J less than 10 and in this case the answer is yes。

Is k greater than 10， No， and and is J greater than 10。 So that's true。 But this one's false。

 false and true become false。Or is k greater than 10 or j greater than 10， no， neither are true。

 so the result is false。And then there is a uninary not operator that you can put in front that's like saying k greater than 10。

 well that's false， but then if I apply not to it， it becomes true。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_43.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_44.png)

Streng concatenation is a little different than Python， it uses the plus operator but。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_46.png)

It will convert things to string， right？X equals 12 is a number。And I'm adding a number to a string。

 And it's like， I'll convert that into a string。 And so that 12 becomes a string。

 And you end up with a string。 that's hellello 12 people with one，2 characters。

 the number 12 is long gone at that point。 So there is a conversion。Normally， if this were in Python。

 you'd say， stir parenthees to force it to a string。

 The plus is smart enough to automatically convert it。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_48.png)

You can debate which of those things you prefer。And I can come down on either side of it。

 there is something to respect about Python that basically says， if you want it to be a string。

 you as the programmer should say it， languages that are sort of loosely goosey that do things to make it most convenient like PhP and JavaScript sometimes can get you into a trouble。

And this is where this is where you can always tell it。Nan。

 if you see Nan in a user interface anywhere in the web， you're like， oh。

 somebody did a JavaScript calculation just like this and something went wrong。

Because that's what happens when。Additions go wrong。We'll see that in a second。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_50.png)

So variable typing。Is a little confusing because we're using plus。

 sometimes we're using it for concatenation， sometimes that we're using for addition。

 So in this particular case， where we take the string 1，2，3 and add 10 to it。

 it sees that as a concatenation and gives us back a string。But if we say the string  one， two。

 three times1， then it converts that to an integer times 1， and that's 10 so it becomes 133。

 but that is a number， but what happens if we take something that's not even a number？Well。

 multiply it by one， that is not a number。And then we add 10 to it， and it's still not a number。

 and this is the not a number and that's why you see Nan。On all these web pages。

Percent complete naan， that's because it was adding one to something like a fall， you know。

 that wasn't a number and couldn't be conversed into a number like a string or something。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_52.png)

And once you get something that's a nan， it's very， very， very sticky。But it doesn't blow up。

 it just keeps running and shows you Nan in your user interface。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_54.png)

So if a string can't be converted。Because of mathematical operation， you get a Nn。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_56.png)

There is a function called is Nan that gives you a true false。 Like is there。

 is there a Nan Nan is a value， It's not the lack of a value。

 something like null or a null would be a lack of a value or empty in Python would be the lack of a value。

 I Nan as an actual value。 Its just like a value that's the indication within a number that is。

 it's a number。 If you divide by two， you get another value that's not really a value。

 It's a special value called infinity。 And if you like add one to infinity， you still get infinity。

 If youtract one from infinity， you still get infinity。

 there's no amount of ones that you can subtract from infinity to get anything less than infinity because it's like。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_58.png)

Infinity。And there's a function called is infinity that lets you know if the variable you're working with is infinity。

So。This seems kind of silly， but it turns out that in some ways JavaScript has one of the coolest number classes because it uses this internal number format called。

I TriE 450 something， 455 or something， and it's actually the scientifically thought out really good way to do number calculations。

 And so in some ways， it does a better job of flow point numbers than some other programming languages that just kind do unpredictable things at things like infinity and dividing by zero or multiplying by an undefined or something。

So you got to respect JavaScript because they stuck to their guns on numeric calculations and they're pure。

 they're the way research computer science researchers suggest this is the way you do it and that's exactly the way you do it seems a little weird。

 I make a little fun of it， but it's actually pretty cool。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_60.png)

。If you're in an untyped language and you're passed in like a variable and you want to know is this a string or is this an array or is this an object。

 there is a unary function， which is just takes one parameter type of。That's PPEOF。

 that's like function， that's like multiplication or minus sign， type of x。

 and that returns a string， so type of a number is the string number， if we say what is Y weapon？

🎼The stringing WY it's a string and you can ask for a variable that doesn't exist yet and that will be undefined and so you can say is this variable defined yet it's well it's not defined yet so this is where you're writing code and maybe past a parameter and you don't know what it is and you say is it a string as an array or whatever so it's good to be able in an untyped environment to take a variable that you might have been given by somebody else and check its type。



![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_62.png)

So up next， we're going to talk about functions and arrays。


# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p32 11_04_03_C语言面向对象模式的独特之处概览.zh_en -BV1v2421P7pt_p32-

![](img/b9fec47463f205ed85a6d66fb83b7f3b_0.png)

So I want to talk about the C++ programming language for just a bit because C++ plays a really。

 really important role in the development of object oriented programming。C， of course。

 came out like 72 through 78 and then C++ came out in 80。

 and then both C++ and C coevolved through the early 1980s。

 and then you see things like C sharpp and Java and Python and PhP all。Informed heavily by C++。

If we look at how object render was happening kind of before C++ it there was there was。

It was like C++。Wasn't really appreciated by the typical mainstream procedural programmer of the day。

 And so things like alal and Sima， it was kind of like there were tribes that liked procedural and tribes that liked object oriented。

 but then C++ came along and sort of pretty much unified it， which meant that，You know。

 you probably learned Python as your first programming language。

 and you were using object or your programming from the time that you started。

 And C plus plus is what sort of unified that。 And it was the C plus plus as the。Quickly。

 number one procedural programming language， and then C++ as the number one objectorient programming language that kind of brought order to the notion of procedural object oriented hybrid。

 etc， and sort of everything that kind of came after 1980 was really strongly influenced and informed by C and C++。

So let's take a look at how this sort of changed over time by looking at some syntactical influence。

So C++ which was the earliest， which is a preprocessor plus a compiler。

 it turned into a compiler on its own eventually， but it has this concept of a map that has a separately selectable type of the key type of the value and it uses the square brackets。

 map open square bracket Z closed square bracket equals8， and that is in effect a put。

 that's like an insert into the map or update of the key and it's a pretty succinct syntax。

And so Python。Came up with a way Python really didn't want to make a more complex syntax than C++ so Python worked on its language to make it so that you could just say d equals DicCT and it was a typeless language and so we don't care the fact that it's going to be strings mapping to integers because you can map lots of things to lots of things in Python but it did follow the D sub Z equals8。

 and again， you use from the beginning when you first started programming in Python and you thought that was just natural but what's really going on is more like what Java did in 1995。

 we're not going to use the square bracket to put stuff into a map we are going to be more pure here and we're going to create methods Now if you look under the covers in Python you see that that is really a method that does that insert of the key of Z and the value of8。

If you look at job it says map string integer， so we again have this notion of a generic class capital map。

Maap stringing integer。Map， which is our object variable， equals new tree map string integer。

 which of course， is choosing the underlying implementation。

 and then they have the syntax of a setter style map dot put。

And then they're giving the key and the value is two different parameters。

 there's choices that each of these languages are making and I'll try to highlight them as we go through it。

 I want to talk a little bit about how C+ plus and its object under approach and design made it so that a class like the map。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_2.png)

Works almost the same as like a sort of a low level class。

 like a float or an in and has access in particular to kind of the special characters or properties like square brackets or plus or minus。

 how that happens。 And it is that you can create a specially named method。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_4.png)

Inside of a C plus plus class that the compiler will consult and call。

When it encounters certain what you think of is language syntax。

 meaning that as it's parsing the language syntax like square brackets， it's like， oh。

 I've got some code to do some work here。 This concept is called operator overloading。

 meaning that the operator。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_6.png)

The behavior of the operator is controlled by the writer of the class。

 you are writing a class so in this bit of code here。I've created。For no particular reason。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_8.png)

A class that I call 10 integers in a row， and I have a array of 10 integer values。

 but that's private， so that's something that the outer class can't talk to right so you can't say 10 in 10 like in the main 10 dot values is like no。

 you're not allowed to touch that because it's private。

But then what I do is I create a public method。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_10.png)

Which is the square brackets operator method， the method to be called when the compiler encounters square brackets。

My class name， my object name， followed by square brackets， call me。

Now the first thing we see is the return type of this operator square bracket operator code is an integer reference。

 an integer that can either be read or written， which means it can be on the left or right hand side of an assignment statement。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_12.png)

And the parameter that it's being given is an integer index。

 which is the thing inside of the square brackets。 now it is a reference because of the ampersand。

 but it is a constant reference meaning we are not allowed to change it。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_14.png)

Inside of this function。Okay， so conk means we're leaving it alone。

 which means we are not allowed to say index equals 42 inside the square bracket operator method。

And so what we're returning is that private variable values subindex。

 but we are returning a reference to it， so wherever it appears in the original C+ plus code in the main。

 what happens is that reference can be， like I said on the left or right side of an assignment state。

 so let's take a look at how this works in the main code。

 I am going to create a variable called 10 of type 10ent。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_16.png)

And I say 10 sub 1 equals 40， which means I'm storing 40 in position 1。

 but when it sees that 10 sub1 it says， oh， oh， this little class has an operator。

 square bracket operator so I better call that little method past the one in then that returns a reference。

To values sub 1 and then into that reference， the 40 is assigned Now Python doesn't have return a reference and it doesn't have a caller reference。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_18.png)

C kind of does， but。It's very their're pointers。 And so references and pointers are different references。

 you'll notice there's no special syntax to dereference a reference， whereas when you get a pointer。

 you got to have special syntax to dereference a pointer。 So this notion of。

Call by reference and return by reference is like impressive in C++ and allows it to do a lot of things and allows us to have this seemingly native line of code 10 sub 1 equals 40。

 which is really just a bunch of method calls。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_20.png)

Amazing， and then we immediately say print 10 sub one contains。 And then 10 sub1。 And again。

 when this is kind of a right hand side of an assignment statement， it's looking it up。

 It calls the method the operator to square bracket operator method passes one into it。

 And then we return value sub1。 And then that's what gets printed out。

 And so then we say 10 sub 5 equals 10 sub 1 plus 2。

And now we see10s of one on the right hand side of an assignment statement。

 which calls that same code in the operator brackets method within the class。

 passes in the one returning the reference to values sub1。

 but then that reference is just 40 and then we add two to it。 and then we assign it into 10 sub 5。

 which is again， calling the in operator method to get a reference to values sub 5。

 and then assignment happens。 All I really。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_22.png)

Did was kind of faked it， but I， I used it to show you this like lovely ability to do operator overloading。

 When I first found my way into Java。😊。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_24.png)

My greatest disappointment。 And because I taught a C plus plus class。 And then I learned Java。

 I wasn't a whiz at C plus plus， but I really thought it was pretty elegant。 So for me， my brain was。

 so I didn't learn Python first。I learned to C phosphos and I'm like， hey。

 that's what object are you ought to be， and then I'm like go in Java and Java didn't do that。

Java basically does not want and did not want as a choice。

To take values by reference in method calls and even more it did not want to return references in the return values of method calls that those two things。

 the ampersand in the return type and the ampersand in the call parameter call。

 those are essential for C++ to accomplish this and Java did not want to return references in particular because it has to do with。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_26.png)

Garbage collection variables going out of scope， et cetera， et cetera。

 and if you return a reference you don't know when it's out of scope。Et cetera。These are powerful。

 complex and potentially quite dangerous things right， but the C++ design was hey。

 you are a samurai warrior and you are going to you are going to use these very wisely and we don't want to take power away from you。

 we want to give you all the power that you might want。

And just trust that you're not going to make mistakes， right？

And so choicess that Java make and Python make are like， no， no， no。

 we don't want you to make mistakes。 so we're not even going to give you this kind of thing。

 But there are other ways to do everything。 things like tuple returns in C is a good example of。

Kind of an homage to this notion of returning things is not always just a single thing so but C++ is kind of unique now again。

Python。Emulated the C。Syntax that was quite beautiful。 That was a result of C's support。

For operator overloading。And here's the thing where like it all comes together。

So Python saw the beautiful syntax that C++ when you did the right things。

 the compiler would give you this， let use this beautiful syntax and still call your methods inside the object。

But they didn't want to do the call by reference and by return reference。That C++ did。

And so what they did is they did basically a syntax transformation if you look。

 Python is in a sense very Javalike in that everything has to happen through methods。

 but then there's these hidden methods okay， let's take a look at the code。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_28.png)

So I'll create a dictionary named x and then we say x sub 1 equals 40。

 and again we know what this means， that means somewhere in the key， the key under the key1。

 there's 40。Now， I can print this out by saying x dot double underscore get item。

 double underscore open print one close print that's taking the index inside of the square brackets and passing it to a predefined。

Python understood rule for what get the square brackets turn into double underscore get item。

 double underscore， or the x is the object and the parameter is the syntax。

 So if we think about it on the right hand side of an assignment statement where we're just reading it It's just doing the get right iss kind of doing a getter like thing give me item1 and then outcomes the 40 and that's how the print of x of 1 is a 40。

 That's really what happens the covers is there is a class which has underscore underscore get item underscore underscore defined find in it as a method。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_30.png)

And that's how it loads x sub1。So if we go down another line and we say x of 5 equals x of 1 plus 2 seems simple enough and literally for years。

 Python software developers don't even need to know that this is miraculously and beautifully complex。

 but what this translates into at runtime by compiler syntax transformation is。

The x sub1 on the right hand side turns into a x dot get item friend 1， which pulls up the 40。

And then plus two gets added to it。But then that expression is passed into X dot set item in position 5。

 so the left hand side of the assignment statement is。The x of 5 equals part。

 and that's calling set item。 So if it's doing a square bracket， look up on the right hand side。

 it's calling get item， and if it's doing a square bracket on the left hand side of an assignment statement。

 it's doing a set item。 So this means that there was no need to return references。

 no need to process references。 None of the hoops。C++ went through and so you see that Python did not choose to implement the way C++ did。

 but they supported the very elegant syntax now， and then you'll see that Java。

In 1995 takes it or 94， takes it one step further in that they're not even going to give you that cool syntax。

 they're like， no， we're going to say just do x dot put and x dot get and call it good if you know that x is an object and you need to do a get in the put。

 do the get in the put， we're not going to do this little syntax transformation that makes it pretty and we're also not going to give you operator overloading because again。

 operator overloading requires references because it allows the class。

To return a thing that can be used on either the left or right hand side。And again。

Java did that because they did not want to make their memory management more complex。So it so。

Hard to argue。But what this kind of shows you is like the amazing。Interplay between these languages。

 Yrn Strrowstrip， went to school in Denmark。And started working on C++ in Denmark。

 but then was hired to go to Bell Labs in New Jersey。

Where he met and worked with for a number of years。

 Barrn Strosstrip and Dennis Rci and and all the folks at Bell Labs that gave us Uniix and C over the decades。

 And so C plus Plus kind of came to the world from Bell Labs from Murray Hill and and Giiv Van Rossam。

 who was in Netherlands at the time really was just looking at all this stuff and using all this stuff。

 and an expert in C and C plus plus。And back in those days we tended to look a lot at like the code that C++ generated and getter's like I'm just going I'm going to borrow these are really good patterns and so that's how we see so much influence of not just the syntax but the actual runtime conventions and like。

If you look at some of the generated C++ code， the concept of private is often done with underscores。

 they use underscores a lot， Python's like，  yeah， I'll just borrow that。

 I'll just use double underscore as my signal of this private and then away you go。So to show。

The influence that C+ plus and C had over Python， both in the syntax and in the runtime。

We can take a quick look at some internal details of how Python works and Python turns out to have almost identicalally implemented operator overloading in as C++。

 but we don't see it， it's all internal you have to kind of look so on the left hand side that's the code that I just got done going through that's the C++ code that has the private values and then the public operator overload。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_32.png)

And now if we look on the right hand side we see a class ten and I'm creating a double underscore values which is values private as a dictionary。

 and then I'm going to define the set this is like a private method called set item and then private method called getite Python basically has the left side and right side assignment of bracket lookup operators different and the set item is the left hand side and the get item is the right hand side you'll see that in the set item I'm just taking selfvalue subindex equals value and in the getter I'm returning self underscore values subindex so that's the right hand side。

So if we look at the code， I see， let's make a ten end when the variable 10，10 sub one equals 40。

 Now， Python transforms that10 sub one syntax into a set item of。10。Coma the number one comma 40。

 and then call set item and you can see of course it worked， right？The three values are self。

 index and value。Well， self is。10， which is the object instance。

 The index is the thing inside the square brackets。

 and the value is the result of the expression on the right hand side。 It's not just 40。

 but it's the expression on the right hand side。And so that goes in， right， we see the print。

10 sub 1。 Well， that is a right hand side reference to 10 sub 1。 So that's going to call get item。

 self is 10。 and then index is the one。 And we're going to just return it。

 and that's going to print out a nice little happy little integer， which is exactly the variable 40。

 So it says 10 sub1 contains 40。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_34.png)

And at this point it should be obvious what's going on when I say  ten0s of5 equals 10 sub 1 plus2。

 well the 10 sub1 on the right hand side。Turns into a G item。That gives us back the 40 value。

 then the 40 and the two are added together to finish the right hand side of the expression。

 then we're going to sign that into tens of 5， which then turns into a set item of 10 comma 5 comma 42。

 and then that stores 42 and position 5 in our private variable values。Private values variable。

 and then I print it out which is a left hand side lookup of 10 of 5。

 which calls get item again with self is 10 and index is 5 and so we get the 42。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_36.png)

And so you see how they're so similar inside， I mean， again。

 like if you look at generated C++ code from early C+ code compilers。

 you'll see these double underscores used in various places。

 which means that Python in its internal implementation use the same patterns as C++ did in its internal implementation。



![](img/b9fec47463f205ed85a6d66fb83b7f3b_38.png)

Plon chose not to do call by reference and return by reference。

Java chose not to be not to do call by reference and return by reference。

 and Java chose not to do the fancy syntax transformation。But you know， who knows。

 maybe maybe one of these days， Java could do that syntax transformation and be like， whohoa。

 Java has everything。And then to some degree， Python has shown the way about how you do this without doing call by reference。

 and again， that Ampersand operator and Amperssand index on the lefthand side。

 that's the like scary part where language designers are like。

 oh'm not sure I want to go do that because。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_40.png)

C++ is not a garbage collected language， but Python and Java are garbage collected languages。

 and that's not the only reason。That Python and Java didn't want to do call by reference。

 but it is one of the reasons that you kind of just simplifies。To know that when a function is done。

 it's done and there's not like sneaky little pointers inside that function that need to stay alive。

So it allows you to throw stuff away with functions of French。🎼Okay。ough for that just again。

 I'm just trying to show you in the simplest possible examples。

 the kinds of design decisions that all these language and library designers were doing as they built the languages that we know。

 love and use。🎼Yeah。Yeah。🎼嗯。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_42.png)

🎼Yeah。

![](img/b9fec47463f205ed85a6d66fb83b7f3b_44.png)

Yeah。
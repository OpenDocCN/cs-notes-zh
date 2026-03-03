# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p05 5_02_01_第一部分：从Python到C——编程语言罗塞塔石碑讲座.zh_en -BV1v2421P7pt_p5-

![](img/c93c9bc8e969937e8f00ded963b57369_0.png)

Hello and welcome to C programminging for everybody。 I'm Charles Severance。

 and I'm your professor for this course In this lecture。

 we are going to do a very rapid translation from Python to C。

So as I've shown you in an earlier lecture， C is kind of like the mother tongue of advanced programming languages。

 Python itself was written and still is written in C， and Python is deeply influenced by C。

 even though the syntax looks very different right and if you've taken all my other classes。

 you will have seen PhP， you'll have seen JavaScript， and to some degree。

 even CSS takes some of its inspiration from the syntax of C。

And so I'm not intending for this to be your first programming class。

 I intend for you to be an expert at Python Well not expert。

 but certainly I'm not going to tell you what a if statement is。

 I'm not going to tell you what a variable is。 I'm going to just tell you how to use variables in C and I going tell you how to use if statements in C and so that's why a solid foundation of Python。

 not wizard， but solid foundation of Python is essential and frankly。

 I would rather that you learned a bit of PhP， some JavaScript and。

All this other stuff before you come， I see that C Pro。

 I think C programming is not the first class that you should take。

 but instead it is your gateway to the advanced work that you're going to do and so I think C is very。

 very important， I just don't think it's your first programming class。So。

You might think Python and C are not very different， although Python is written in C。

Python has white space that is part of its syntax， C whitespace is ignored。

I do like see better in that Python is very objectory， if you read an article I wrote on Qua。

 you'll see I rank all my languages and I put JavaScript and Python is the most object rank languages。

Java is a little less object orient and C is like the least unobject orient。

 C is not object orient at all。Python has wonderfully convenient data structures in the form of lists and dictionaries。

 PB has arrays and。Javascript has objects， the all beautiful， beautiful stuff。

 very object running structures。By a seat does not， it's fast， it's efficient， it's powerful。

 it's got strs and pointers and bigolly。 you will use them， andre not they're not convenient。

 but they are scorchingly fast。 and by the time we're done with all this。We will see。

How to usestructs and pointers to build lists and dictionaries。 And that really is。

 we will follow down the path of building Python。 So you'll see a common theme throughout this class of。

How Python achieves what it's trying to achieve by R C。

Python has automatic memory management to the point where if you've been a Python programmer or a PhP programme or a Java programmer or JavaScript programmer。

 you probably don't even know what memory management is。Well。

 you're going to by the end of this class and by the end of this class。

 you're going to be able to see how Python。Autommateates memory management for you。

 right Python is written in the 80s and C was written in the 70s。 and in many ways。

 I see Python as a convenience layer that was built on top of C。Just。C programmers look at C。

 it's like， it's great， it's great， it's great if we just had this layer of easiness on top of it。

Then things would be better and so。That's what Python is Now Python also introduced things like quite different syntax to make it indentation。

You know， required because they thought it was a good idea。

 So we we could argue one way or the other。 I mean。

 I'll tell you when I'm writing a million lines of code。

 I white white space is not to me a good way to have syntax。

 So we're going to look at C through a Python lens and we're going to learn by example。Now。

 most of the time I tell you。Don't copy and paste， don't。Cheee， don't look for solutions。

This lecture is the exception to that rule。 I've written this lecture as a Rosetta stone。

 It's just a little tiny bit of connection to what you already know in Python to what you're going to do in C。

 And so。I'm not intending at this point for you to build your own stuff based on reading a book。

 I actually just want you。 And if I give you assignments to do these particular things。

 I really do want you to just watch this lecture。 grab the PowerPoint and feel free to cut and paste from my PowerPoint into my assignments。

Because this is。I don't know if you've ever seen it where the mama tiger is teaching a baby tiger how to hunt and the mama tiger goes out and gets something or other and brings it back and puts it near the baby tiger and let's the baby tiger chase it。

 Well， that's kind of what I'm doing。 I'm the mama tiger。 And I'm giving you some C code。

 And I'm putting it right in front of you。 And then I want you to take that C code。

 And I want you to run it and play with it and understand it。

 So I'm not expecting in this lecture that you're going to derive it。

 that you're going to sort of somehow read the textbook， look at a problem and solve the problem。

 That's later， that is that's absolutely later。 So this is the beginning。

 This is trying to make connections， conceptual connections to the complex knowledge you have about Python to little places where you can hook things on in C。

 And so the idea is to go through it quickly so。I do assign some of these as programming exercises。

 it's intended for me， my intent is that you'll watch the lectures and just work on the code at the same time。

 I'm not trying to test what you learned。I really want you to watch and listen and type。

 that's how we learn。You could cut and paste it or you could type it and you could type it one piece at a time in the mere act of you typing。

 even though you're just looking at a slide and typing it in， at this point in the course。

 that is the learning objective of this lecture now。

That whole rule of just typing code in that you're looking at something from someone else。

Don't do that forever。Later， I want you to do things like synthesize what you learn in the book。

 synynthesize it， Str through it and figure things out and do the assignment yourself。

 So don't go search it。 if you want to gain maximum benefit。

 If you're just in the biggest hurry of all， just go ahead and search。 But please。

 if you want benefit from this class。Don't cheat yourself。

There's a lot of similarities that I'm not going to cover。

 You can go read the textbook like the plus minus asterisk slash in percent。 Hey。

 probably when you were learning Python， you're like， whoa， what's this percent thing。

 And why did they choose percent。 And The answer is， that's what C chose。

 And so modulo is just percent in all these other languages。

 Because they flipped a coin in C and decided percentcent was modulo。The comparison operators。

 the assignment operators equal sign， which means that the equality operators got to be double equals。

 exclamation equals less than greater than less than equal， all that stuff's the same。

Variable naming rules the same， you start with a letter underscore and then numbers。

 letters and underscores and case matters both languages。W loops， the concept of break and continue。

 which， you know， some people get all worried about。

 I love break and continue if you've taken my other courses and you'll see when we talk about it in C。

 I love B and connu C2。Maybe because's I learned C first and I just love breaking and okay。

 enough about that， I love breaking T De， okay， enough about that。

Constance about the only thing that's really different in Consts is like strings and characters and Booles。

 and strings and characters are like the biggest thing in the beginning。

Both have int and float and char and bite。 Now， again， B and string and char are not the same thing。

 C has no stir class， which is the string class list or dictionary。

 and Python has no concept of struct or double。 And in a sense， you could think of。

Python's float is really seas double right， and so by the time Python was written。

 the notion of shorter floating point numbers is less less critical。There are some differences。

 A lot of this， I think， was in the design of Python trying to be a little less obtuse and a little more convenient。

 For me， it's annoying。 I write the C versions of the operators like and double ampers sand。

 not as exclamation point。 We call that bang or double vertical bar and。In Python。

 they're all convenient， we use the word A and D， but okay， whatever。嗯。😊，So there in C。

 we have a four loop， but it' it's an indeterminate loop。

 If you remember the definition from Python for everybody。

 Interminate loop is one that you have to examine to see if it's got an infinite loop。

 whereas in in Python。 if you say4 X in some list。 You're going to go through the whole list。

 It's a determmininate loop， It only runs until that list is exhausted C does not have such a thing。

 right， it just every loop has got a condition to finish it。

 Now we write loops like 4 I equals 1 to 100 or 0 to 99。

 We write them and you can look at them and say， yeah， that's not an infinite loop。

 It's just technically， you have to look at the loop to make sure that you have an inadvertently。

Made an infinite loop。 There's no predefined， true and false。 I find this really like， wow。

 couldn't they got EF， capital EF for end of viency。None and all are similar concepts。

 but quite different。 None in Python is its own type。Nll is the number zero。

That's cast to be a pointer to nothing and so。None is like， specially marked empty。 null is。A zero。

We'll get there， we'll get there。Stringings and character arrays for a while。

 you can kind of pretend that character arrays in C are mostly like strings like when you throw a constant and you pass it to a function。

 they kind of look the same。But like once we start working with them， you'll see they're very。

 very different。 that's kind of the first fun part of first part of this class is like strings are now your responsibility。

 there's no there's no help right and see， of course has no list or dictionary and Python has no concept of like tightly packed data。

 which is whatstructs are and and doubles and floats So here we go， let's get started。

 let's see if my pen is working here。 Yeah so what we're going to see is on one side we're going to see some Python another side we're going to see some C。



![](img/c93c9bc8e969937e8f00ded963b57369_2.png)

And so this is just talking about output。 This is Python 3， of course。

 And so we have a print function， and it takes any number of parameters。

 One of the things you'll notice about the print function is like hello space world。 Well。

 that's part of this constant， but answer comma 42 puts a little space in between answer and 42 and the output。

 So if you want to suppress that kind of automatic addition of spacing。

 you have to maybe concatenate things together or some other trick。

 the print statement automatically knows if it's got a string or a float or an integer and it just does things kind of all automatically。

 And so if you want to see something， usually you just print it。Okay。

 so let's take a look at the compare and contrast。 So first off。

 you pretty much you're going to have to start every one of your C programs with pound include standardIo。

 H commentsments are different。Python comments are pound sign to the end of the line。

See comments are slash starred。Across multiple lines to star slash。 So everything in between there。

 that can be multiple lines。 later versions of C also add the what's called the C plus plus style of comments in the jascript uses those as comments。

 which is the double slash。 So when you're writing。

 you probably can use double slash in the C that you're using， but I'm kind of being kind of strict。

 And so I'm pretending I'm in 1978， So I'm not using that C plus plus style comment。 Again。

 that came from C plus plus， it didn't come from jascript。



![](img/c93c9bc8e969937e8f00ded963b57369_4.png)

Some of you have taken Python classes where there's this like underscore underscore main。

 and it calls this thing， and it makes a function and calls it and indentense everything one tab。

 And they're really imitating C in that respect。 And I think I don't like that style。

 I think those people who do that in Python。 I'm sure they have a good reason。

But I think they're just like wishing it was C because the definition of C is code a program starts when it starts running。

 it searches for a function named main。 And later we'll see that this function can actually have arguments。

And it returns an integer as to the successor failure， so really。Main is a function。

 And so that first line there int main open brandclo print open curly bras。

 That is the definition of a function that happens to be named Maine。And then we have print F。Now。

 again， I don't know if you' learned Python 2， but in Python 2， there was a print statement。

In Python 3， there is a print function， and so here we're using a Python 3 print function and。

C never did the statement， so C decided， as we'll talk about later， to not have any input output。

 any reading or writing in the language itself， but instead put them in standard libraries。

 and that's what this pound includes STDI O do H is saying， Okay， I'm going to do some I O here。

 input output here。 and so include the C input output library。Okay， and so print F。

Takes as its first parameter， a string。The other thing you see and see is you can't use single quotes for long strings。

 later we'll see single quotes， but in C there's a major difference between single quotes and double quotes。



![](img/c93c9bc8e969937e8f00ded963b57369_6.png)

Single quotes are single characters and double quotes are a character array。

Not a string character array。 The other thing is things like the end of line。 So in Python。

 the new line is added implicitly。And see。You have to add it explicitly。

 And so that's basically saying print hellello world and then go to the beginning of the next line。

Now， this first parameter is actually not just a string。 It's a string with embedded format codes。

That start with percent。Percent D says， there is a corresponding。Inage your number。

And I want you to convert that into a string and print it out。

I guess I should probably just erase some of this， so it says answer and then a number。

And so you can have more than one of these things。And then they match so that says there's an integer as another parameter so you can have one parameter。

 two parameters， et cetera。 and so for beyond one parameter， like in this one。

 x percent do1 F that corresponds to this first floating point number and this percent D corresponds to the integer 1。

So you have these percent things now we will learn that these percent things have a language unto themselves in chapter8。

 and this is basically saying please print me a floating point number with only one digit of precision right so percent dot1 f says print a floating point number。



![](img/c93c9bc8e969937e8f00ded963b57369_8.png)

And then if we want a string， it's percent S。 But this really Sarah here， double quote Sarah。

 double quote is a character array， and it's actually。Not five characters， but6。

 because there is always a terminating zero character at the end。

 And so percent S says the parameter needs to be a character array。

And properly terminated by an end string indicator， which is a zero character。So that's this， right。

 it's pretty simple， but we got a lot of stuff to cover here and this is the Rosetta Stone。

It's more complex and see， you have more control， you're doing things that more explicitly。

 and it's not doing it for you automatically。So let's take a look at a simple number input。

 and you'll see that some of these things come from my。My Python for everybody class。

 this is the famous US floor to European floor elevator converter。

So we're going to print something out。Now， one thing about C is that you've got to declare all your variables。



![](img/c93c9bc8e969937e8f00ded963b57369_10.png)

Python is sort of a typeless language， it's increasingly getting moretyy。

 but it's a typeless language， so we have to declare that we're going to have two variables USF and EUUF。

 and they're going to be integers。We print the statement。

 but the only difference there is we have to put the backslash n in。

 otherwise it won't automatically do that。And then we have this IO routine again coming from STdi。

h called scanf。And its first parameter， much like printf， is actually a formatting string。



![](img/c93c9bc8e969937e8f00ded963b57369_12.png)

And what this says is this says。Read for a lot little ways， find me a number。

 as long as it seems like a number， keep reading and turn that into an integer and give it back to me。

 and so it actually has got some scanning built into it。

And it reads until it finds a non digit and then stops and says that's the number， so it turns out。

In C， the way you could type a lot of different things here， we won't go into that too much detail。

 we'll hold that until chapterer 8， but the idea is it doesn't work exactly the same。

 although this input in Python reads a line。 Now， again， I got this little note here， if you recall。

 if you recall， in Python 2， there was an input and a raw input and raw input was what read a line。

 which I tended to use when I was teaching Python 2。

Input was a weird thing that had some kind of scanning thing going on。

 and it scanned and threw stuff away and it grabbeds something。 it might go from to multiple lines。

And it was totally inconsistent。 and it was worse than scan F。

 So I was really glad when they just got rid of it in Python 3。 And then they changed the name。

 what used to be Python 2's raw input became input in Python 3。

 So the old input from Python 2 is kind of like homage to scan F in C。 But it's not exactly the same。

 And the reason it's not the same is。😊，The input in Python 2 was deriving the type of the data from what it encountered so it might give you back a string。

 it might give you back a floating point and might go like  oh。

 that's dangerous right and that's because the type of USF and Python here is determined it's not predclared so it's known because we're going to convert it to an integer。

And by the way， both the input and the scanf， we can write stuff that confuses it badly and causes it to blow up。

 but we're not we're not worrying too much about that right now we're just kind of getting the basics done so we have a。

We read an integer， we subtract one， we print it out， right， we read an integer， oh。

 I forgot to say this ampersand。Call by reference and call by value。 So in Python。

 this is coming back as a function return。 So it's really easy to assign it into USF， whereas in C。

 we put these parameters on the scan F call， and we have to say。Oh， and by the way。

 I want you to change it because ultimately， if we don't put ampersand on。

It's what's called call by value， not call by reference。

 and Ampers USF is a way to tell C to actually give it the address of the USF variable rather than the value in the USF variable。

And in that is a whole chapter that we will cover like。

 I think4 and 5 will be all about the Ampersand and call by reference。 and call by。

 I' we're way ahead because I don't think chapters  one through four all they ever do is mention call by reference and then say。

 oh， that's in the future。 So I'm going to just say， oh， that's in the future。

 I will tell you that that ampersand is really important And the code doesn't work without it。

 because it is the way that C does call by reference for simple variables like integers and floats。

As you're going to see on the next slide。It was always an exception。String input。Okay。

 so here we're going to this help my Hello Sarah thing， right。

 we say enter your name and then we say name input now the beauty is here in Python is input gives us a whole line okay。

 and then we just print hello name and you'll notice that there' is like this little space that comes out automatically。

So switching over to C， we have our included the library， we have the int main， which is the。

And then we have to predelar a character array。 There is no like， make it a string。

 If this were Python， we could say， hey， let's make a string， but you can't。

And what's even more important is you've got to tell it how long。

Which means that we could type too much stuff in here and blow our program up。

 And that's one of the difficulties of C。 is the fact that arrays， including character rays。

 have fixed length， and they don't ought extend。 There is no There is no dot append。And see。

You can't like， say， oh， name not a pen。 You can't do it。 Python， it's an object。

 It's not an actual array。 Python， it's an object。 Name is a string object here。

 nameme is a character array with 100 elements。 And if you put 20 in， you'll be fine。 if you put 80n。

 you'll be fine。 if you put 101 in， it's going to blow up。Well， that's okay。That's why C is fast。

We'll get to all that we'll get to all that so we print out a prompt and we say scanf and we say in this case percent S。

 give me a string and you can put a limit on it so we're saying look only read up to 10 characters and you'll notice there is no ampersand on name and that is because name is an array。

And so when you put name in with no square brackets， no index operator。

 then you're passing the address of the beginning of the array。And so that is。

 in a sense an ampersand， that is the location of the beginning of 100 character array。

 we're going to scan up to 100 characters into it， and so it really is roughly equivalent to the input。

And then we just again say for hellello percent S， and then name is the corresponding thing。

 and so it saysHo， Sarah。🎼Now， a lot of what we did in the Python for everybody is read whole lines of input。

 and we tended to use string parsing of those lines， like we would trim the stuff off the end。

 and then we'd split it and do all these things。 And there's there's no good split and C。

 So we won't be doing too much of that， but it does help to understand how to read a whole line of input。

 So now we're going to read something that doesn't have It has lots of spaces。

 We're going to read the whole line and we're just going to echo the whole line。 right enter line。

 read the line， print the line。 So now we're going have again。



![](img/c93c9bc8e969937e8f00ded963b57369_14.png)

We have to declare how big of a string we're willing to take char line。

With a thousand characters in it。The prompt by now should be pretty easy and we have a really weird looking。

Percent square bracket。Carrot， backslash and closed square bracket， 1000 S well。



![](img/c93c9bc8e969937e8f00ded963b57369_16.png)

If you took Python for everybody and you remember chapter 11 regular expressions。

 that should look familiar to you。Open bracket， Carrot。

 backslash and close bracket says matchch any character that's not a new line。

So that says scan up to the end of a line。🎼Or until you hit  a thousand0 characters。

 that's what percent， open square bracket， carrot， backslash N。Close square bracket。

 1000 S means as the first parameter to scanf， read a whole line but stop at 1000 characters and then of course a line is just a parameter and then we print that thing out。

Okay， and so a lot of C programmers probably never written this particular line of code。

 but it gives you a sense that there's a lot of sort of programmability and things like regular expressions。



![](img/c93c9bc8e969937e8f00ded963b57369_18.png)

That we， you know， that Python had， well those are kind of an old concept， those are seven。

 1970s concepts， this C language had that concept in it in 1970。



![](img/c93c9bc8e969937e8f00ded963b57369_20.png)

🎼。
# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p19 -19-COMP1531 22T3 - 1.4 - 🛠️ Javascript.zh_en -BV17RXGYuEaM_p19-

Hi， so welcome to the second lecture of Com 15，3，1。 today。

 we're gonna be going through the rest of the week1 topic。

 as you would have seen from the Monday lecture。We covered quite a bit on Monday。

 particularly in relation to a bit of a course overview and then everything to do with Git。

 whereas tonight we're just focusing on lecture 1。4， which is the Javascript lecture。

If you haven't already seen the lectures from Monday and， you know。

 this is true for all future lectures， They are snipped up and placed here like this。

 So you can go back and watch those lectures at any time。Big hello to everyone online。

 I understand that there are gonna be people who are watching this to。

Have discovered the anomaly in relation to USW timetling。

 where they decided to make a mistake and not put one of our lectures on the timetable。

 So it's kind of been on the timetable now。 And， but it also， they didn't enr anyone in it。

 It's very weird， but we do have these lectures on a Wednesday typically。 occasionally， we will。

You know， run them in person now and again。 and we will move them around a little bit。 But again。

 everything's recorded。 So， you know， it's all， it's all pretty fine。 You know。

 there's nothing particular to worry about or stress about now。Bonri has already asked。

 how will we know if it's in person， That's really easy。 I'll tell you many times。Right。

But generally speaking， it's because it's written on the timetable page。

 You can go and look at that anytime and just see what's happening with the lectures， right。

 It says it very it says it here very clearly， you'll get told many a time in advance as long as you're reading your emails and you're actually looking at the course website。

 you will not miss that memo， you will have all the information that you need。So valor Valerinnova。

 Valornova has also asked the question， which is， isn't it weird that we have labs before our second lecture。

 though。Let me touch on this briefly， so。It's an interesting question。 Why。

 why do we sometimes have labs before our second lecture。So。You know。

The answer is because ever since UNSW moved to trimesters。

 they've done particularly strange things with how they structure courses。

 There has been some pushback to ensure that there is at least a lecture before the labs is very common now。

 but the shorter answer is that。Throughout the rest of time。

We make sure that what's in this is true from week to onwards。

 We make sure that there are only the content in your shoots and labs in a given week。

Are based off the lectures from previous weeks。 So essentially。

 this is the only week where you will have， you know， lectures， if you will， that maybe lag。

 you know， the content slightly。 And that's just because the only other alternative was that。

 you know。We just simply do not。 How would you put it， We just simply don't do anything in wecorn。

 right， We just do nothing at all。So， yeah， to the people again， who've asked who've you know。

 made a comment about， oh， you know， we're not really sure what's going on with the lectures Again。

 you can just go look at the actual timetable page， right。嗯。Yeah， okay。

Some people haven't been looking at the timetable page as the conclusion。

 All the information sitting on Web C M S 3， you can just go look at it at any time。

 As I mentioned in the Monday lecture  too， we have a one off。

 we had a one off in person lecture on Monday， and the rest will be pretty clearly signpost， right。

 so。Go read Dreammails， go check out the websites。 You guys are funny。



![](img/af879d0ef4b899e7e429a73a844847fb_1.png)

Mhm。Alright， we're gonna get stuck into it。 So today' is pretty much all about jascript。

 We are going to be learning。About a programming language。

 And we'll do a little bit of prefacing and some other stuff。 So why are we talking about this today。

 Why are we learning about the language Javascript？

 The reason is because jascript is an extremely valuable tool to know and it's necessary for the project。

 What we're going to be talking about today is we're going to be learning about how to learn a second programming language。

 because for many of you here， particularly those who've come straight from 1511。

 This will be the second time you've learned a programming language。

 you probably haven't learn many others beyond C。 So there's a little bit of a new thing for you there。

 We will be talking about jascript with respect to see。

 because that's just kind of how some people learn right？

 Some people just want to understand jascript based on what they already know。

 And then we're gonna to spend a lot of time on core jascript。Language features。

 so essentially just get into more of what the language can do。Now， a bit of a disclaimer。

 I kind of mentioned this， I think at another point， maybe or I dreamt it。

 but because you already know C we're going to be teaching jascript very quickly。

 and mainly focusing on the differences between that。 And this is again。

 kind of the case throughout your university degree。 So when you learn your first language like C。

 we kind of go through everything。 you know， if statements while loops like literally everything from scratch。

 and take it really， really slow， whereas as once you start learning other languages。

 you really speed through it。 And in fact， when you get to like a later point in your degree。

 you won't even have stuff like this。 I think I've mentioned this before somewhere where later courses。

 they'll just be like it's time to learn a new language， go and teach it yourself as you go。

 And that's like very， very kind of common as well and something you might experience in industry later on。

 So unlike C， though， and this is really interesting。 Javascript has a sprawling set of capabilities。

 What that means is that the language itself will。F much bigger。 One of them。

 And this is true for actually most programming languages， right。

This is less about jascript and more about C。 C， the coolest thing about C is that。

It's a really small programming language。 You， you can kind of write it down on the back of a card。

 like a little piece of paper， right so。That's why it's so great to teach。

 because you can essentially teach it all in a nutshell。 Javascript。

 like many other languages will feel a bit bigger。 And that's an experience you're going to have as you do this as you're going to go。

😊，Damn， this language is quite large。 I feel like I don't know everything。 And that's totally normal。

 Don't stress out。 So don't expect to know everything about Javascript this term。 It's not like。

 see where you will finish the term be like， I get the language。 I can't solve all the problems。

 You will finish the term and go， I feel like I still have a lot to learn about it。

 And that's totally okay。 So don't put that kind of pressure on yourself。 You know。

 that's what really matters。Now， what in the world is jascript。

 So jascript is a high level multipar scripting language。 Wa。

 what is a high level multi multi paradigm scripting language， so。

Being a high level language means that it is further and further from hardware。 right。

 So C is a low level language。 You're dealing with things like memory and pointers。

 high level languages。 you don't deal with stuff like memory and pointers。

 You don't need to worry about malicin free。 So it's a high level language。

 It's a multipar language because it has elements of And there are many multipar languages。

 but it's got kind of functional is elements。 It's got imperative procedural elements like C。

 It's got some object oriented components。 And， you know， maybe languages similar to Java。

 And it's a scripting language。 And what scripting languages are are essentially。

Languages that you don't。You can kind of just like， you know。

 write one or two lines of code and execute them， right？ Now。

 many of you are still quite young in your degree。 So you probably don't have a lot to draw on。

 But languages like Python and Javascript de scripting languages， whereas languages like， you know。

 C plus plus Java C， theyre， you know， less scripting languages are a bit more kind of structured in their approach。

The interesting thing about jascript， it is has， it has a massive。 Yeah。 So yeah。Valor andnova。

 I hope I'm saying that right says， so no int main。 Yeah， Yeah， basically。

 like in see if you'd like in jascript and we'll see this， you can just write like print how high。

 whereas in C， you have to be like int main， you know。

 this that return this and all that kind of stuff。The reason jascript' is interesting is because it has an absolutely massive popularity in the web based software engineering space。

 Basically， if you're building some software on the web these days。

 you are probably doing it in Javascript。 That's one of the many reasons why we teach this language in this course。

Because most software is web based these days。 And this is a very popular。

 is the popular way to deal with web based software。 And therefore。

 jascript has become the universal go to language to build web applications， which is really。

 you know。So I said pretty much the co common way that we build。

Applications these days is for the web， you know， so very interesting。

 here is a very simple sample piece of jascript。 Now， this by itself doesn't do anything。

 but it kind of gives you just an early hint of the syntax。 You can kind of see here that， you know。

 we're declaring a variable called a。 It's equal to3。

 We're creating a function called hello that takes in three different parameters and that function returns。

😊，That's a typo。 That's silly。 This should be A。 This function returns A here。



![](img/af879d0ef4b899e7e429a73a844847fb_3.png)

Right。These are all very new lecture slides。 So I do apologizelogise。

 We will come across the old typo throughout the term。 So this is like should be a here。

 So basically a function that takes in A， B and C。 And， you know， it prints out A I mean。

 it's not even really a typoca this code doesn't make any sense， right。

 Like you've got a here and a in the parameters。 It's not really meant to actually run。

 This code doesn't run。 It's really just like。

![](img/af879d0ef4b899e7e429a73a844847fb_5.png)

This is what it looks like， right？ now you see this and you're like， okay， well。

 that looks kind of like C， except I don't know what data type cost is。

And you can see that we're passing in these parameters。

 but it's not really clear what types the parameters are。

 And then we've got this strange dollar sign braces inside these back ticks。

 which is a little bit weird， right？ So there's a few weird aspects of this。

 but it kind of looks like programming。 You know， So we're gonna keep going deeper into that now。

Other reasons that we talk about jascript in the course and why we tackle this it actually has not a lot to do with the language itself right's always there's always people who like to complain about things who like to complain that jascript isn't a good language。

 but why we teach it is actually because jascript has an incredible rich open source library and package manager that allows you to build apps really quickly。

 basically jascript can help you not have to reinvent the wheel and we're going talk a lot more about that next week。

 Javascript is high level， which means it's really quick to write code。

 it's super well supporteded in industry， it's probably like the most well supported language。

 So if you're the kind of person who wants know a typical job in computing。

 it sets you up very well core and foundational and particularly it's really。

 really common in large software engineering projects these days。

 So you go to a large company building a large project there's a very strong chance you're going interact with this language。

 but it's the infrastructure around it that makes it really interesting。

And we're gonna to be talking about that in future weeks。

 We're gonna be talking about automated ways to manage style， to download packages， to do testing。

Lots and lots of stuff that interests us much further beyond just the language itself。Now。

We've been talking about learning another language。

 and we talked about the whole multi paradigm thing。

And let's just have a little bit more of a deeper look at this to kind of get a sense of know where some of the differences are between a language you might have already learned like C and then jascript。

 So you can see C at the top of the table here in jascript at the bottom。

 Now C is a procedural programming language， which means that you write code and it runs from top to bottom or like it jumps around。

 but it goes in a linear flow pretty clearly and it's not object oriented。

 Now most of you again would not have been been exposed to object oriented programming because you haven't done2511 yet。

 but you'll see other languages like C plus plus and Python can do both procedural and object oriented coding languages like Java are only object oriented that's why we call jascript multipar because it can kind it can kind of do different things。

 languages like C and C plus and Java。 they have types int doubles chas whereas languages like Python and jascript。

 they can have types， but it's not built into the language So you know the language itself doesn't necessarily mean that。

There are types。 That is a typo Jacob has pointed out that C plus plus should have pointers。

 That is correct。 Thank you。 C plus plus and C deal with pointers， right。

 But Java Python and Java don't。And then CC++ and Java are all compiled languages， right？

Which mean that you actually go and take the code。And you turn it into， like。

Like a machine code that you then run。 There's like a separate compilation and running step。

 whereasas for languages like Python and Javascript， we don't have that。

 They're what we call interpreted languages。 And that's， that's a big difference。

 which we'll kind of chat about a bit。 Jed's asked a question。

 What's the difference between Java and Javascript。 That's a great question。A lot。They。

 they have really nothing in common。 That's like asking。

 what's the difference between Java script and C， They're just very different。So。

The summary of what we just said before， JavaScript has object oriented， unlike see。

 JavaScriptscript。Does not deal with types。Right as out of the box like C。

 JavaScript won't deal with pointers， JavaScript's high level， and it is not compiled explicitly。

Now let's actually start having a look at code because I've been talking a bit too long。

 So if we have a look at code and we want to write ourselves a function that takes into numbers and returns the smaller number。

This is how we do it in C on the left hand side， right int minimum。

 int the return type minimums the function name， int A int B， If A is greater than B return。B。

 if else， you know， return A， when we look at it in jascript， it's quite similar。

There's only really two things you'll notice that are different。The first one is that。

 instead of saying。Int for the return type， we actually just say function。

 And then you'll also notice instead of saying int A and in B， we just have A and B。

 So the main thing that you're noticing in this particular use case， right。You know。

Is that we just don't have types。 It's really， really that simple。

Just that simple Javascript doesn't have types。 And this is kind of usefulca it means we don't have to worry about what something is or what it can turn to。

 But you will also notice that， as we'll touch on later， when you define functions in jascript。

 you still need that kind of function keyword there， you know。

So now that we've defined these two functions， both minimum， let's actually call them， you know。

And calling them looks very different。So we see here in see that to call it and C you need to obviously create your int main int A C Char star Rv。

 then you need to do a printf and you do the percent D to get the number and the new line to get a new line and then you call minimum between three and5 right that like that right。

And because you're using the printf， which is a function that you didn't define as part of the C library。

 you need to actually also include or a cache include2。 H， whereas in JavaScript。

 all we actually have to do to print out the minimum of 3 and 5 is write the statement console dot log minimum 3 comma 5 like that。

Now， that's super interesting because it's simply just saying you don't need to do anywhere near as much。

 you know。Work to actually make something happen。 and how does this actually manifest。 Well。

 what I've got up here is I've got Vla up here。 and I've actually got all the lecture code。 You can。

 you can find the lecture code just by like on the slides you can just click on it and get access to it。

 you know， but I've got a dumper the lecture code here。

 And I'm gonna show you how we might run something like this。

 So I'm just gonna go into the folder that this stuff's in。 Give me a sack。 And I。

 you can see I've got what file I got here，1。3 compared  to dot J S。😊。



![](img/af879d0ef4b899e7e429a73a844847fb_7.png)

![](img/af879d0ef4b899e7e429a73a844847fb_8.png)

![](img/af879d0ef4b899e7e429a73a844847fb_9.png)

So that's my file now。因 the。

![](img/af879d0ef4b899e7e429a73a844847fb_11.png)

Let me just double check。 I'm not missing a slide。 Yeah， okay。 there we go。I was jumping ahead a sec。

 So in C， if we wanted to run that， we would have to。

 maybe you might use DCC or some other kind of more helpful compiler。 but you would have to。

You would have to actually write like GCC， dash W， or， D W， error， dash capital O。

 D little O or something like that。 You need at least the dash little O， youd， you know。

That that second dash， the first dash should not be there。 you have to write something like this。

 you know， And then once you wrote， did that first line。 Once you executed that line。

 you would create a machine code piece called runnable。

 and then you could run the runnable and it would run it， whereas in jascript with Javascript here。

 All we actually need to do to make it work is just to write node and then this。Now。

 you might ask the question， what is no， You know， that's a very strange word。

 Like it's not jascript or or something like that。You know， it's just called node。

 So let's actually touch on what that is because it kind of feels a little bit too easy。

So no JS is something you might have heard of before and it has a lot to do with JavaScript。

 No JS is really just a command line interface that interprets JavaScript code and runs it。Right。

And that's， that's all there is to it。 You can kind of get deeper in that and get into like runtime environments and and core engines。

 but it's quite literally a program that takes in JavaScript code， which is just text。

 right because code is just text and it actually just compiles and runs it。It's kind of， you know。

 and we've written it here， it kind of follows in a very similar idea to what GCC was if GCC not only compiles it。

 but it runs it right after。嗯。And therefore， right。

 because this compilation and running is in the exact same step。

 this is why we call Javascript and interpreted language， right。

 This is no J has known' the language there might not be totally correct。

 but it's just when it's all part of the same step now。

What's the difference between something like C， which has that explicit compiled step and something like Javascript。

 which doesn't have that explicit compiled step？ Well， the difference， frankly， is just that。

With that kind of a collapsed into one step。What ends up happening is that it's a little slower to run。

Because you have to kind of recompile it every time， right。Because normally， if you're just kind of。

 you know， coding in C， you can compile it once and then run it many times after it's been compiled。

 whereas with JavaScript and node， you kind of have to go and recompile it each time。

But one of the benefits of that is it can be a little bit more convenient to work with。

 So it's really just a trade up between like you know convenience and performance at a very high level。

 So you'll find that it actually feels a little bit easier to code in JavaScript because you can just run the code all the time。

So it's just that standard thing。Let's actually go and run the code we saw before。

 before we look at some more examples。 So if I've got all this code here， I can just run node。

 and then I can do 1。3。

![](img/af879d0ef4b899e7e429a73a844847fb_13.png)

Compare 2， which is the code we have， right。And then I run it， and it outputs 3。

 It's really that simple。 And the print equivalent， if you haven't already seen in jascript。

 is that console dot log， because all you are doing is you're actually， it's， it's a weird syntax。

 but。It's really just saying。Log something to the console。 You know， I mean。

 that's what when we say print， what we really mean is right to the console。 So， you know。

 console dot log kinda makes a lot of sense if you think about it。All right。um。Next。



![](img/af879d0ef4b899e7e429a73a844847fb_15.png)

We're going to go into some more language features，A lot of the rest of this lecture。

 if we kind of skip ahead， is just a whole bunch of light。Which is a whole bunch of javascript。

 I don't。 I hope we won't di the full time， Cause I already used some of your extra time on Monday。

 which I appreciate。So。In Javascript， we've mentioned already that variables don't have types， yeah。

So there's no ins or doubles or chas necessarily， but what is interesting is that when we create variables in JavaScript。

We need to do one of two things， which is either say that this is a constant variable or a non constant variable。

And therefore， before the name of the variable， like you can see here on line 3。

 we either need to write Kt， CONST or let LET， and if something is let。

 what it means is that it can be changed and if something is cont， it means it can't be changed。

So when I say cont years equals 5， what I'm really saying here is that I'm going to let the years variable be equal to 5 and it's not going to change ever。

 and it can't be changed。 whereasas if I said let years equal 5。

 maybe I could change it to 8 or 10 or something like that。嗯。So Boonrika said based on。

 based on the comments line 3 looks like it's meant to be let， not cons。 That's kind of true。

 But just for compiling and liing reasons， which will make more sense later on。

 it's kinda the code has to make sense。 So I'm gonna change that in the example。 B yeah。

 you're right。 Like it， it would normally be let。 but that will cause some errors with how things are set up。

I'll go through some demos in a sec。 If we keep kind of looking here。

 you'll also see that what's interesting is because we don't have these types。

 you can kind of very weirdly just start giving random variable names， random values。

 So I can say that， well name is d， a string and ages 18， an integer in height is 204，8。11。

 which is a double and not exist as undefined and exists but nothing as null。

One thing we will talk about more as we go in Javascript is the difference between null and undefined you're probably familiar with C where we have like null。

 which was like a pointer to nothing we don't really have pointers in Java so there's nothing particularly you know interesting or exciting about that but there are kind of two ways in JavaScript to define nothing not a pointer to nothing just nothing。

 and they're both undefined a null they're both different things but they kind of mean something similar but we'll come back to that again later Nga says is a possible to access memory using JavaScript No。

 there is no pointer arithmetic in jascript which means you can't access memory directly like you can and see。



![](img/af879d0ef4b899e7e429a73a844847fb_17.png)

Now I can go andfin all these variables and then just print them out。You know。

 and I can easily go and look this up。Variables， great。你哪？So I've got some code here。 Year， name。

 height。 I can just console log。 I can also just console log strings directly just like I can and see。

 So if I run， you know，1。3 variables， ego， I get 5 giraffe 2048 11。

 You'll see if I change this from cons to let。 Everything still works。

 It's just I can now change that variable here I could say years equals 8。

 and you'll see that that will change。Right it's now instead of it being5 here， it's 8。

 But if I change this to cont， if it was const the whole time。No JS。

 the compiler will actually throw an error and it'll say， hey。

 you try to assign a value to a constant variable and that constant variable was years。

So this is one way that， you know， it can be quite useful because if you make something as con。

 it's kind of like a guarantee that it's going to stay con， which is again very。

 very useful for help making sure your program behaves。Lockland says。

 so it's just like a hash define。I don't know。 Like， look。

 it depends in what way you're asking that question。

 So is it like a hash define in the sense that you use a hash define for constant variables。Yes。

 is like a hash define in any other way， Probably not。 hash define finds a kind of pre。

Pre compilation steps。They are constant， but。You know。

That's also largely just because of how it's set up。 You know。

 they're not actually constant at run time。So， you know， if you don't think about it too much， Yeah。

 sure it's send letter hash defines。And yeah， weve got all these different types here。

 and you'll see that they're actually printed out on the terminal as different types as well。

 So it's really cool about jascript。 We can just go and declare random things randomly like that。

 okay。😊。

![](img/af879d0ef4b899e7e429a73a844847fb_19.png)

嗯。Strings the way things get more interesting。 The one of the weird things is that。

Interacting with strings is pretty similar in most programming languages， except C。

 where interacting with strings is quite specific'ca you're dealing with， you know。

 strings or arrays， strings or pointers or this kind of shit。 But in jascript and stuff， it's much。

 much， much simpler。Much simpler， in fact， right， And that simpler nature is that you can。

 you can just manipulate them like that so easily。 So if we look at the code we have up on screen here。

 we've got， you know， line 2， we're saying let sentence equals my and why。Pretty straightforward。

Yeah。😊，I create a variable called sentence。And I let it be my。嗯。Easy， then on line 3。

 because the sentence is a let variable。 I say that sentence is equal to sentence plus name is。

 So I actually， like I do with numbers。 You know how you can say， like I equals I plus 1。

 I can do the exact same thing with strings。 It's just that strings aren't numeric。

So because strings aren't numeric， it means you can't like add two strings together to get you know like numerically。

 but you can join them together。 So when you plus two strings together。

 you kind of shove them or join them together。 And then similarly here。

 I can say sentence plus equals another string， which will just join it together because as you know this already。

 like I equals I plus1。Is the same as I plus equals1。And Jacobs asked a good question。

 does it matter if there's a single quote or double quote， so no in JavaScript。

 you can use single quotes and double quotes interchangeably？



![](img/af879d0ef4b899e7e429a73a844847fb_21.png)

Right， and if I just get rid of this bottom code for a second here and we just try and run this top part。

Oh， wrong language。You can see here that it says my name is Piachu because I went and got my and then I joined plus name is。

 and then I joined plus Pikachu to it， right。If I look at the bottom stuff here。

 we're gonna learn something slightly different with strings。

 which is how to print them out or how to actually， you know。

 work with more complicated ones when we print it。I can create a constant variable called age that's 7。

 a constant variable called name that's hidden。 and then a constant variable called phrase。

 And this is where things get kind of interesting。 If I want to create a string that's made up of other variables。

 there's a few ways I can do it。 But the easiest way to do it is to essentially write your string。

 But everywhere you want to put a variable， you simply put the variable name。

 you wrap it in braces like this and you put the dollar out the front。



![](img/af879d0ef4b899e7e429a73a844847fb_23.png)

So when I write this within a string， I'm basically saying that， hey。

 dollar means like I'm going to do something interesting here。

 Braces are where I put the interesting thing。 And then what's inside of that is typically a variable。

 The one caveat here is this only works when your string uses the back ticks。

 which are typically in the top left of your keyboard， Not the single or double quotes。

 So you can use single quotes or double quotes。 if you like， They're both totally fine。

 But you need to use these back ticks for strings that are going to have interpolated information inside of it。

 So if I make the smaller again。

![](img/af879d0ef4b899e7e429a73a844847fb_25.png)

And I run this。 You'll see that， you know， it says my name is Pikachu。 Great。 whereas here it says。

 hello， my name is Hayden and I am 7 because it's printing out the string and it's injecting those variables here like that。

 Now， those backtics are critical。 Watch what happens when I change those back ticks to double apostropphes or single apostropphes is the output changes。

 And the output now instead of saying hello， my name is Hayden。 It says， Ho。

 my name is dollar name and I am dollar age， right。😊，um。Very interesting。

 So those back ticks are critical， right， because without those back ticks， then。

It just printed out literally， which makes sense。 That's how string should behave。

 Some interesting questions from people。 Someone said， how do we print out。

How do we actually print out single and double apostrophe， It's really not too different from C。

 If I wanted to put a single apostrophe here， like Haydens， I can just put it in， because。



![](img/af879d0ef4b899e7e429a73a844847fb_27.png)

The string is defined by the double apostrophe like this。 So it just works fine。

 What happens if I am using a single apostrophe for my string， Well。

 you can just escape it like you do and see with the back slash。

So if you do back slash and then a character， it escapes it， which essentially mean， you know。

 lets you use it。 whereas obviously， if you didn't have that， it would there would be a problem。

 right。And naturally， if you're in the back ticks， you can use either of these because， you know。

 like the， the language doesn't care what you you use。

 it's more just like you can't use a single apostrophe if it's also being used to define the start of the string'cause that would。

 you know， that would be a bit of a headache， right。But strings are very。

 very easy and fun to work with like that。Bm， dumb。

Any other questions about string strings before we keep moving on。Just give everyone a second。Yeah。

 so Nathan， say not Nathan。 Anthony says， so not much fiddling with memory， like can see， correctect。

 Yeah， there's F there's far less fiddling。嗯。You know， then there isnt C。Yeah。

 there is some good and some bad size to these high level languages right now。

 I think you're getting， you know， of strong taste of some of the good parts。 But， you know， we'll。

 we'll get to some parts that you might find harder。 Yeah， I guess you are Nathan now， Anthony。

 I think my brain read A N T H and the N， I read N E T H， for some reason。

Someone did ask a question before， which was， can you do like， I plus plus and stuff。

 You can like that's easy to do in jascript。 You could just do like， you know， age plus plus。

 but you'd have to make it a let because you're gonna modify it。 That's totally fine。 It's very the。

 the fundamental syntax of jascript is actually very similar to C。 It kind of feels like， you know。

 C， easy C， easy， E C， ha。嗯。Now， if we kind of move on。Cjiia asked a good question。

 What's the difference between let and v。Vars， like an older style of。Let。

 which I won't go into becauseuse the differences are quite subtle。But think of var like Let。

 If you see var on the Internet， just read it like let， or it doesn't really matter。Okay。

 so moving on to some control structures， we again， assume you already know what if。Ese if， else。

 while and full loops are。 So we don't need to cover how they work。

 But let's just look at the syntax differences。 Here's a piece of code where we define number equals 5。

Right， then we say if numbers greater than 10， we're gonna consoles log something else， if this。

 then do nothing else consoles log something else。 Then we consoles log a new line。

 We create a while loop， you know， letter I equals 0， while I is less than 5 I plus equals 1。 Great。

 And then we have a four loop at the very bottom。 you know，4 letter equals 0。

 I less than 5 I plus plus like this。What's really cool about this example。

 in my opinion is that and one of the cooler things about teaching JavaScript soon after see is that if you don't look at the console log part。

And you don't look at the let。Part and the lack of types。 this。

 this example is quite literally the same as what you do and see。 So there's actually very little。

 I think we need to talk about here。Just kind of works， right？Cool。I mean， I。

 I shouldn't just move on p preemptively。 Like， do， do you have any questions about this。

 Like I just wanna ask a few people who are online 'cause it's， it's very。You know。

 it is very straightforward。If you've already learned， see。Yeah， depending on the term， you did one。

1，5，1，1。 Sometimes they taught full loop。 Sometimes they didn't。 but you're all super like。Smart。U。

And four loops are just condensed while loops。 So you look at it。 if you haven't seen it before。um。

It looks as， it is as simple as it looks。 like， wow。

 a our loopt consists of three primary components that set up the condition and the increment。

Fuall loops are just like that， but syntactically a little bit tighter。Right。嗯。So， you know。y。

 that's it。Functions in jascript， very straightforward。 We saw them before。 things don't have types。

 So therefore， you we kinda just need this function keyword。 Why does this function keyword exist。

 It's an interesting question。 You know， someone could ask like， like a question I've always had。

 or I've had people ask me， I should say， is that sometimes someone might say， hey， why is like this。

 Why do we need to write function。 Why can't we just like do that。



![](img/af879d0ef4b899e7e429a73a844847fb_29.png)

It's a very profound question because like， it's not like there's a， F， you know。

 a law of physics reason that we have to。Do that。Right。That we have to have function here。

It's really just about how the language designers design the language。

 And like a really simple thing is like， if you're a compiler trying to understand a language。

 if you see that。It might not be immediately obvious to you that this is a function definition。

 depending on how the language is defined， right。This could be a function call。 Like。

 if you just look at that in isolation， how do you know that's someone defining the minimum function and not someone calling a minimum function。

 right？ And I think Bori summarised it well， Why do we have to put function in front of our functions？

 Well， Because a person who built this made it that way。你呢。That you can get to the deeper reasons。

 But there's nothing like， you know， again， there's nothing like without it。

 a computer can't actually， you know， it's， it's just how the language is defined。

Languages like Python have similar things with different words， but functions are， again。

 one of the easier， easier parts of this。

![](img/af879d0ef4b899e7e429a73a844847fb_31.png)

Okay， now when things start to get a little bit more interesting is when we get into。Data structures。

And before we get into the actual coding element of data structures， it's a really important time。

 I think to take pause and talk about the two main types of data structures that we'll use in JavaScript。

 which are collections of information and those two collections that we're going to deal with are sequential collections。

Basically， ordered lists of things and then associative collections， which are kind of just。

These random boxes of lots of things mixed together。And we're gonna talk about them both。

 And you've kind of experienced these a little bit， particularly the sequential containers。

 So collection， sorry， so let's chat about them。 So sequential collections are essentially。

Bunches of data。They basically， as。Hint， but the data in them。Are referenced by their index。

 Basically， if you have a sequential collection， a raise you。Have data that has a sense of order。

And each item， because of that order， has a specific key。

 It has a specific number that you can use to index it。So if you know this。

 if you have an array in C， every single item in that array has an index。 You can be like， yep。

 I'm going to get the first element， the second element， the third element like that。In JavaScript。

 we also call these structures as。😡，But the interesting thing is that the distinction in jascript between a and link list is not a thing。

 It's just generally not a thing in many high level languages。 But even， even that's the case。

Here is well。That means that you don't really have to ask yourself questions like。

 should I use a linked list or should I use an array。In my code。

 because they're all kind of the same thing。 And generally， generally， if you' using jascript。

A couple things are happening that makes your life easier here。 The first one is that。嗯。

Because the language is higher level， the performance difference between them is pretty minor。

 And then also， there's actually quite a lot of things that go on under the hood with languages like jascript。

 which means that you kind of like。It can do lots of optimizations that you're probably not used tocause if you kind of come from。

If you kinda come from sea land， you're used to kind of being like。

 I need to make the best decisions。 But with these high level languages。

 it can kind of do it for you。 whereas associative containers are a little bit more new to you。

 And in associative containers， values are referenced by this。

By their string key that maps to a value。A。And。The easiest way to kind of explain this。

Is to say that associative containers are most similar if sees your only language。To a seastarstruct。

Right， and if you have a struct in C， you know this。You'restruct。Does not really have an order。

 Like if you create a struct in C in that structure， you know， likestruct a student。



![](img/af879d0ef4b899e7e429a73a844847fb_33.png)

You know， and you're like。You know， Charstar Z I D， Charstar name in Wham， right。

 You know that you can't say something like student。Student student， student0 right or student1。

 It doesn't really work like that。 You know， the only thing you can do is simply access it by the name of the element inside of it。

 student dot Z I student dot name student dot Wham。

 This is what we call a an associative collection or associative container because back to the definition。

 the values inside of an associative collection are referenced by their string key。

 basically their name like name， agent height。 and they don't therefore have an inherent sense of order。

 That's the thing with likestructs right in astruct。

 you don't say does Z I or name or WM come before one another。

 Now obviously you can get technical and be like well。

 Z I is probably stored in memory further up the name because it's of how it's stored。

 But there's no way you can again say student0。 So that part's very different。



![](img/af879d0ef4b899e7e429a73a844847fb_35.png)

![](img/af879d0ef4b899e7e429a73a844847fb_36.png)

![](img/af879d0ef4b899e7e429a73a844847fb_37.png)

One difference with C is that in Cstructs need Strs actually really rigid。With a sea all struck。

You have to。You have to define all of the names of what's in it at compile time。

You can't just kind of add them as the program runs， they're not dynamic like that。

 whereas in other languages like JavaScript they are dynamic and you can adjust them like that。

 which is very， very powerful and we'll see some of those examples in a second。

Right I am just seeing how much we have left。A we don't have a ton left。 that's good。

Let's actually take a five minute break or。Maybe like an eight minute break before we get further into coding。

 Then we'll kinda go into the actual like， you know。

 let's apply sequential and associative containers。 But for now， let's take a break and。Start up。

 We'll start up again at  Six，58 PM for those who are watching live。Okay。

We were just talking about sequential and associative collections， right。

 and the first one we're going to get a bit more practical with is the sequential collections。

 and in jascript， we call these arrays。And arrays are mutable ordered structures of the same type。

You get what an array is。 It's the list of things， right。

 But the important thing is that they're mutable is in they can be changed。

 You can add stuff to them and you can change them later， and。Typically。

This isn't always strictly enforced， but at least it's philosophically enforced。

 They should have the same data types in them in terms of like， if you have an array of things。

 they shouldn't be an array of string， number， string， number， number， number， string。 No。

 they should be like string， string， string， string string or like number number。

 number number number。And how you actually create a in JavaScript is really quite similar to how you create a arrays in C。

😊，You， and you can see this here where in this particular case。

 I have gone to create an array called names。 It is a constant array。

This is a little bit interesting。 We'll come back to what that means in a second。

 and then I use the same square brackets that I'm used to， and then I add elements to it。

 and I put a comma between them。 very similar to C。

The way we access array items and mutate them is also very similar to see we can console log。

 for instance， here， the whole array that's a little bit different。

 We can console log one element of the array。 that's similar。

We can modify a particular element of the array。 That's also similar。

 We can push something to the end of the array。 That's interesting。 And that's new because in C。

 when you create an array with four elements in it， that array is exactly that size。

 and it is that size forever。But， yeah， until you go and do something to change it。 But in jascript。

 you can just kind of say， actually， I want you add a fifth thing， add a fifth thing to the end。

 please。Right。9 games says， can you push something to the middle。 You can。

 There are functions that allow you to do that。 You can put。

 you can do tons of stuff we haven't even begun to talk about yet， right。

 So you can do tons and tons of stuff。 But we'll get to that in a second。

 Let's actually have a play around with this， though。

 because this is certainly a little bit different。So oh my eye。 when we look at this here。

 that's like me creating the array。When I consolesol log the array。

 it will actually print something for me because JavaScript is smart enough to know that if I say can you print the array？

It will actually just print out the values。 And you can kind of see that here。

 That first line here with the one will actually just print out all of the array items with a comma between it。

 That's， that's kind of how it knows to do things。 If you say print the array it or print everything with a comma between it。

 It's quite， quite easy like that。The next line， console log 2。

 you're obviously just printing one item。 And you can see that when I change。Names 1。

 which is the second element。 Jake to Jco。 And then I push Rennie to the end。

 And then I print the whole array again。 It now prints out Hayden Jco， Nick Emily Rennie now。

This is very cool and very easy to work with。 And you can also see this as yet another example of printing a string with the back ticks。

😊，So I use the backtics here instead of the apostrophees。

 and that allows me to do something like the dollar brace so I can actually print out variables within my string。

Super， super， super handy。Really nice and easy。Now。Let's keep going。

 and then we'll keep learning some， just looking ahead。

 We'll keep learning some more interesting things about arrays。

 So the next thing is that you can use arrays within loops， too， right。

 And this is kind of how you'd expect。 we'd kind of just expect that you can use arrays within loops。

 And that's the case here。 if we look at。Yeah， there's our arrays within loops。

 So I can go and create like an array of5 I，5 items， A， B，C， D， E。Then I can come along and say。

 well， you know， here's my while loop。 you know， console log and I can。

 I can console log each element out of the array really easy。 just like C again。

 I can do it with a full loop， really， really easy， and I can do it with another full loop here。

 except instead of needing to use the five， I can actually do items dot length。

 And this is where things get really interesting in Javascript。

 And we're gonna touch on this in another couple of slides。 It dot length。 So items is an array。

 But where things differ so dramatically， is that in C。😊，An array。Is typically， as you know。

 just a pointer。Right。Just a pointer to the beginning of a piece of memory， whereas in Javascript。

 an array is actually a very complicated object。 And you're not going to know a lot of what happens with it。

 But it's got a lot of interesting information under the hood。

 And that includes a self awareness about its own length。So， here。Items， the array。

 If you actually do items dot length， you will get the number 5。 And if you add stuff to it。

 it increases， too。 So you don't need to have an awareness externally。

Of what the size of a particular array is。 It's all stored within it。

 So really easy ways to loop through the array。 that should be relatively similar except the items do length part。

 So really， really intuitive and really， really friendly like that。嗯。Cool。

Let's actually do something with an array now， something more interesting。

This is starting to feel like a bit of a real program here。I've got myself a function。Call get Es。

That function takes in nus。Which is a parameter， which is an array。 Very interesting。

 Nobs is an array。 can be anything in Javascript。 It's one of the good and bad parts。

 And let's come back to what that function does in a second。At the bottom of my code here。

 I'm creating an array called all numbers， which has， you know，1，2，3，4，5，6，7，8，9，10 in it。

 And then I'm going to console log。 I'm going to print what get evens returns when I pass it all numbers。

 So I call get evens with the array and it returns something and then I print that out。

 So when I call get evens with all numbers， this function is called with an array here 1，2，3，4，5，6，7。

8，9，10。😊，And what I'm basically going to do here is loop through。All the elements。

 and any time an element is even， I'm going to push it to a new array。 And again。

 this is where kind of some of the power of these high level scripting languages comes about。

 because as I enter this function， I'm going to create a new second array called Es。

 and it's going to be empty。 It's going to be an empty array。

Then I'm going to loop through the input array， so I'm going to go through all of the all numbers from0 to the length of the array like tick tick tick tick looping through it。

 And then for each number， I'm going to check if that particular number is even with the simple。

 you know mod to equals 0。And if it is even。I will push that number。To my evens are right。

And then at the end of the function， I will simply return that new array。

 So this is really cool because I basically created an array out of thin air。

 added stuff to it and returned it without worrying about any malic staff， any free staff。

 anything like that。 You know， really easy and friendly。 Jacob says。

 assuming we don't know what is inside the function can numbs be either an array or just a variable。

 So this is the downside。😊，And we'll touch on this more in week 3。

 This is the downside of this kind of。No vary， no type approach。 It makes it really easy to program。

 but nothing， nothing really stops a compile time。You calling get evens with something weird。

 It's just the program will simply break， and we can show we can show you that。 So if I get this one。

 1。3 functions here。

![](img/af879d0ef4b899e7e429a73a844847fb_39.png)

And let's run this。In fact， let's change it up。 Let's pass in5 instead of an array。

 Watch what happens。1。3 functions。Well。mm。This is interesting。 So why did this work， Well。

 I didn't work。 It broke， but。Obviously， if I put 4 there。

 it's not gonna work it's not like it's doing it'cause it's odd。 So 4 gets passed in here， great。

Constevens is an empty array。 Great full loops set up。 We let I equals 0。

 cool eyes less than nus dot length。What is numberss dot length。 It's very odd。Let's try it out。

 Let's console log it。Let's use the back ticks。Numbs dot length is nus dot length。 bit of debugging。

There go。 Ns dot length is undefined。Okay， so he said before that in Javascript。

 there are two main ways。嗯。Of。Two main ways of saying that this is nothing。 and one of them was null。

 and the other one was undefined， right。A。And in this case， it's undefined。

 And this is one of those weird quirks of the language where what happens is that。

With nus that length is undefined。 Like if， if you try and get like the length of a random number。

 Javascript instead of crashing will actually just give you the result undefined。

 There's some obscure parts of the language And therefore， in this case。

 what actually happens is that this check here says， okay， I'm going to let I be equal to 0。

 And then I'm going to check is I less than undefined。 We can try that out pretty quick， right。

 is0 less than undefined。False。😡，Is 0 greater than undefined， false。Is 0 equal to undefined。False。

 bit weird。 But， you know， this is just me playing around the node interpreter。

So this basically this fall loop never gets entered when you enter in a number。And。嗯。Therefore。

 we just get an empty array。 What happens if we pass in a string， Let's pass in dog。Oops。

 wrong thing。Same kind of thing。 This one's a bit more interesting， though。

 because numbs dot length in this case is not undefined。It's actually three because like in C。

 a string is actually just an array of characters， you know。um。And therefore。

 numberss do length is 3。 But when we loop through it。

 each individual nus is in like and you can see it here， right， I'll say， like， you know。

 checking numbs I like that。See that checking D， O G。 But when you try and get the modulus。

Of D O And G， it's never gonna give you 0。 Like we could try it out， right， you know， trying。

 And then we'll put in more debugging code here。What'sn's eye， Mo，2。NAN。What is that。

Then there's another obscure part of JavaScript。Which is that like jascripts a really easy language to code in with some obscure aspects to it。

 That's the best summary I can give you， right， N A N stands for not a number。 and it's the result。

 it's basically。That again， there was a question that C CGia asked， which is。

 why wouldn't it just break。It's a good question。 Why wouldn't it just break。 What did。

 what did Daniel or someone say above， Because some person just decided that one day。

 It's just how the language is defined， right， And you can try this again。

 Watch what happens in jascript when I do like 5 divided by 0。 I get infinity。

 You know what happens when I try and do a divided by 4。 I get noted number。You know。

4 divided by twos， obviously， two。 What's dog divided by cat。Not a number。 You know。

 So it's a little bit of a weird thing where basically。

 some other languages would crash or throw an error in Javascript。

 there's a bit more of a tendency for it to give you a result that kind of implies an error。

 So this isn't inherently bad because。You know， you can just deal with it。

 But the point is that what you expect might be a little bit different。

 The program might not crash as often as you think。

 And then back to a really interesting question that Jacob asked， Jacob said。

 so as far as debugging is concerned， jascript is harder。

I don't know if I want to answer that like in a very blunt way。

 because jascript' is much easier to debug than see。 What I would tell you is that。

Because Javascript is a pretty generous language， and it's not typed。

There is a tendency for things to maybe seem like they're working when they're not working。

More so than what you're used to， because it's so forgiving。You know。

 so that's just a subtle kind of thing to deal with。But obviously。

 if we run this correctly with an array。We would。We would see it work like that。 And we would get。

 you know， nubs do length is 10， checking1， trying 1，2。 So， you know， odd， even， odd， even， odd。

 even odd even。Look， Anthony and Nikkhil have asked a question， know。

 is there more false confidence in jascript and like。

Do we need to test our code more often in jascript？ And like， look。No， like， really， it's fine。

 This is a very traumatic first example。 I think you're getting quite a bias of things here。

It's a bit weird sometimes， but it's not like， it's not like I give any extra thought programming in jascript than I do in Python or something else like that。

 You know， it's not that dramatic at all。 So we don't， we don't need to worry。

 It's just something to kind of be aware of。 And， you know， think about， you know。

 there'll be a few confusing things。 And we'll figure those out together。

 And the last thing on a raise is that。

![](img/af879d0ef4b899e7e429a73a844847fb_41.png)

Because we're working with JavaScript， which is a higher level language。

 we actually have the ability to do much more clear and concise syntax when doing looping。Right。

 this is cool because。From a language point of view， someone kind of just said， you know what。

When we deal with arraysin stuff， we seem to be doing very similar things a lot of the time。

 We tend to just be looping through them。Let's find some easy ways to do that。



![](img/af879d0ef4b899e7e429a73a844847fb_43.png)

So。You would have seen before。 We had some loops like this。You know。

 while eyes less than5 console log items， I。Right。Or if we look at this loop down here， now。

 if I kind of butcher this example for a second。What we're really saying is that Javascript acknowledges many languages do this that you know what。

 there's many times you're going to do this。 There's many times you're just going say that Let's start from index 0。

 Let's go to the length。 Let's print out the element， done。

So they came up with a more concise syntax， which was。Let。😡，Item。Of items。Console dot log item。

These two things do the exact same thing。Right， and I'll put another console log in between just so you can see。

ABC D， ABC D E。Really simple。You don't actually need this lead here。 typicallyy。

 this will be cons' because you don't actually change the item。 That would be a bit weird。

 But there you go。 So instead of saying， you know， for all this K and index stuff。

 you can actually just take your array items， say， well， let's loop through it。

 And each time we loop through it， Can you just create a temporary variable called item。

 And then I will just use that inside my loop。There's a slight variation of this， too。

Which uses instead of the word all of it actually uses the word in。And in this case。

 in means don't get me the value each loop， but get me the index。

So you'll see that this one will just get you 0，1，2，3，4 like that。

So they they're two sides of the same thing。 They're just a compact way to loop through an array in one case to loop through the values and in another case to loop through。

The indexes。 Now， Bill's asked another good question。

 and Bill's actually pointed out something that I kind of glossed over。 I must have forgotten。

Is that if you haven't already noticed。We need， we don't need to put a back slash n at the end of a line when we console log it。

This is once something we needed to do in C。 Remember， you know， print F back slash n in Javascript。

 every console log we deal with has a new line added to the end of it automatically。

This is just because people kind of figure it out。You know， that。A。You nearly always use it。

 So let's make it that by default。Jed's also asked。

 why don't we just directly print console dot items。 That's a good question， Jed， so。

You can directly print console dot items。 But the thing is when you。

 when you print console dot items， you don't have control。Over how it's printed。 That's it。

So if all you need to do is just print it out for debugging reasons。 then yeah。

 just print out the array like that。 That's absolutely fine。 However。

 if you need to print stuff out for like， you know， put it on a new line or display it a certain way。

 or like， you know， let's say I wanted to maybe clean this out a bit and say， well。

 maybe I could change this one to index。Right。And say， well。I'll be like， well。

 index or I I'll even tidy up at the， you know， index like this equals。Items index。 So basically。

 I'm saying this is like printing it right。 The yellow bits the string。 I'm saying， well， items。

 And then what I'm putting in the brackets， the index of where I'm looping to。

 And then I'm actually gonna print out the value at that spot。

 And now I can get a slightly cleaner looking code。 right， It 0 equals a Its 1 equals B。

 So most of the benefit of these like loops is just when you want to， you know， format it。

But back to the question about the new line， because all of these are adding new lines。

 what if you don't want consoles log to add a new line， Google it。



![](img/af879d0ef4b899e7e429a73a844847fb_45.png)

![](img/af879d0ef4b899e7e429a73a844847fb_46.png)

javascript。Console log， no new line。Right， to answer your questions。

 if you're running in a browser then default， no， blah， blah， blah。

There's a lot to unpack with JavaScript If using node， then you can use process。

 standardout dot right message okay。

![](img/af879d0ef4b899e7e429a73a844847fb_48.png)

So if I don't want a new line， then I could say use instead of console log， I could do。

What was it process。Dot standard out dot right。 And then I it wouldn't add a new line。Go。

 there you go。How hard was that？Quick Google， figure it out pretty quick。 You're gonna do that many。

 many times in this course and many， many times in your life， of course。

There was another question about this which was， why is this cons and not let？

And the rash now behind it。Is that， well， surely it should be let because with let。

 every time we loop item is index or item is changing。Therefore。

 it can't be constantst because constant implies that it doesn't change， sort of。

How it actually works if you wan to think about it is like， it's actually like every single time。

 Like， So if you get your like items array， right， So say we have our array up here of items like blah。

 blah， blah。

![](img/af879d0ef4b899e7e429a73a844847fb_50.png)

With the fourth thing， what it's actually going is like， let's go into the first loop。

 and it's actually creating a whole new variable。And then it's using that variable until the variable is killed。

 And then on the next loop， it's creating a whole new other variable called items。

Until that's killed。 And then on the next loop， it's doing the exact same thing。 So each loop。

 it's actually creating a whole new variable。 That's why we have it as cons。

 because in each of those loop iterations， it's like a new variable。

 and you're not going to change it within that loop iteration。 So that's why we。

 that's why we do that that way。

![](img/af879d0ef4b899e7e429a73a844847fb_52.png)

![](img/af879d0ef4b899e7e429a73a844847fb_53.png)

![](img/af879d0ef4b899e7e429a73a844847fb_54.png)

Cool， there were a few questions about。And I will talk about it here becauseuse we're just talking about objects。

 and then we'll talk about associative collections and stuff。

 And then we're getting close to the end。U。Arayse were the Javascript implementation of trying to solve the sequential collection problem。

Objects in Javascript are the way of trying to the associative container problem。

 and objects are mutable associative structures likestructs that may consist of many types。

 So likestructs too， if you have an associative collection or what we call an object in JavaScript。

 it can be many， many different types， right you can have strings and ins and everything else。

Generally。You use them when you when you need a collection of items that are identified by like a particular name or string description rather than some kind of numerical index or order。

 And you can see that here， right， like you like we said before。

 if I have a student that student has a name or a score or a rank。Well。They're different types。

 but that's okay。 They're not ordered。 They don't have a， you know。

 none of these come before another。 These are all just different types。Like Strs too。

 when we create one of these in Java and I'll look at this here。



![](img/af879d0ef4b899e7e429a73a844847fb_56.png)

I can create it， And then what I can do is I can print out the whole thing。Noode，1。3 objects。

Like that， I can print out the whole thing， or I can print out more specifically a property of it。

Through a key。 And what we generally say is we say the name is the key。

 scores the key rank is the key。 This is a key。 That's a value。 This is a key。 That's a value。

 This is a key。 That's a value like that。And similarly to array， I can mutate things。

 I can change things。 I can say that， you know what， student， my object， See likestruct。嗯。

I'm going to change the height in that object from something。 but in this case。

 the height doesn't even exist。 And this is crazy。 This is where things really differ from C。

 because in C， once you define astruct it stays that way forever。

 But here I'm actually going to add a whole new property to it， which is height。

 which is just going to be the number 159。 And now when I run that you'll see that I print out the whole object。

 then I print out each of those values at each of those keys。

 and then I print out the whole object again， which now has a new property height。😡，Cool， easy。

 How fun's that。Super cool。You know， I can go and modify stuff to student dot name equals Hayden。

Anything can do lots of stuff。There we go。嗯。Any questions about that so far。



![](img/af879d0ef4b899e7e429a73a844847fb_58.png)

Quick pause， or despite vote yeah。People to share their thoughts。kuuo。

The interesting thing about objects in jascript is that you can create them different ways。

 So one way you could do it is actually just to create a。



![](img/af879d0ef4b899e7e429a73a844847fb_60.png)

An empty object like this。 Nothing inside of it。And then you can go and add things to it。

 And then you can print it out。 And this one is like totally fine， right，1。4 object。Basic one， Okay。

 name Sally age 18， height，187。Console dot log user data。 easy。

 Another way you could do it is by populating them like we saw in the other example or at once。

 and then just adding to it later。 You know， there's nothing that stops you doing what we did before where we。

 you know， we， we kind of create an object by default like this。

And then we simply go and add things to it off to the fact。That's totally fine， too。So it's very。

 very versatile。 Now， the interesting thing and no one's asked this yet。But。😡，The const。

For the object， normally that throws some people off。We're like， wait， wait， wait， wait， wait。

 How are you changing age， Shan。You said it was consed， you know like。



![](img/af879d0ef4b899e7e429a73a844847fb_62.png)

How are you changing that if it's cons， It's a little bit tricky to understand。

 But you can kind of get this if you understand pointers， right。

 If I create an object user data there。What is happening is that I've created a variable。

Called user data。And this variable essentially references an object over here。

 And this object contains my key value pair， my key value pair， my key value pair。

And we're saying that this is const。 And when you say that the variable is const。

 what you're really saying is that， you know， in the case of these objects。

 what it references has to be that。So what that means is that user data will always。

 always point to this object， but what's in that object can change。

Nothing can you we can't stop that。 So it's not so much that you can't go user data dot age equals 19。

 It's that you can't say user data equals a new empty object。



![](img/af879d0ef4b899e7e429a73a844847fb_64.png)

Then we'll get the error because user data always has to refer to the same thing。

 even if that thing itself can change。Jed has said， how do we change the order of keys。

 What Jed I'm pretty sure is referring to is when we printed it out like this as a general rule。

If you want to control the order in which keys are printed。

 you're probably gonna manually start printing things out。

 right rather than you can't really like easy there is no order to it。

 I don't even know what the specification says different languages will say different things about there。

 Some languages will be like we just printed it out randomly or the order it was defined or something depends on the language。

 I don't know what it is for ja。9ine game says， what if you do a con variable inside。

 you can't do a cons variable inside。Miss， you know，9 games。

 basically like objects like a raises and。嗯。Things like arrays and objects can't like they can always just be changed。

 you know？Anthony has a good analogy， he says it's just like a box when you say user data is always that box。

 but it doesn't it。User data refers to a box。 You can keep adding and changing that box and what's inside of it。

 But you can't say user data goes to another box。 And Jacob says， can you use L for objects。 Yeah。

 I can definitely use Let for objects。 If I use L here。

 then I would be able to change user data later on to an empty object and this code would function totally fine。



![](img/af879d0ef4b899e7e429a73a844847fb_66.png)

And then just to reiterate the point home， Aliison says， so the variable insidestruct can be changed。

 either it is let or const。 Yes， the data inside the box inside the struct object can be changed regardless of whether you've defined the object itself as let or conts because let or cont refers to what the name points to not to what's。

You know， the underlying properties inside of it。Okay。One slightly obscure thing。

As well about JavaScript。Is that。You can actually also reference keys of objects a separate way。

You can reference it the kind of C style struck way。Right， where you do like dot。

 So I say user data dot name equals Sally， or you can actually reference it a bit more of the。

I don't know how to put it。 It's really not much in C， but you can reference it this way。

 which just does the exact same thing。 So if I say node object more too like this。

 then it actually has the exact same behaviour here。

 So whether you use the square brackets and then the apostrophees or whether you just use the dot both of them work。

 There are scenarios where the square bracket apostrophees a little bit more useful。

 And like I'll give you an example， like。Let's say， I wanted to， like。Bk。Add or， or like。

 I'll give you an example。 Let's say that I， I， I appear here say my key is gonna be age and my value is gonna be 18。

Now I'm not going to expand this example too far because we're doing very basic things today。

 but what's cool about this is that I could come along here and say use data。

Key equals value like that。 so I could actually kind of inject a variable into that key component so that I could like more dynamically construct my。

 my structure here。I can't do that with the dot right because if I do like dot key。

 Javascript from a language point of view doesn't know whether the dot key whether the key is meant to be what it knows'ca it defines it。

 but it doesn't think that that key is like a variable。 It thinks that that key is the name。

 It literally looks for the key called key。You know。

 and Anthony also says so variable look up of an object。 Yeah， here's an example。

 Let me give you an example of where the dynamism is really useful。

 So I print out that user data there， oops。Like this。

Where you might use that kind of square syntax we saw as if you say， you know， you wanted to。

 not this was a bit weird， but let's say you had a list of properties which was name， age and height。

Like that。And then you loop through it。You say， you know。

 for cons property of properties because that's the easy way to loop through an array。

 I could console log user data property like that。Right。

 so I could like loop through each item in this array。

And then simply kind of access that particular property of， of the object like this。

So that's where that square bracket is particularly useful。Generally speaking。

 I think most people tend to。Tend to use the dot syntax unless they're doing something dynamic。

 in which case they'd probably use the square syntax。

 But the much of a muchness you can kind of do either either way。However， what I just did。

You don't really need to do see how I did this thing here where I wrote out all the properties。

 because JavaScript has some more handy helpful capabilities。Right。

Which you can see in our more props file where if we create a user data object like this with name agent height。

 we can actually use some funny JavaScript syntax to get properties of that object。

It's a little bit weird， but if I say object dot keys， and then I give it my object。

 it will return me an array of the keys。 name agent Hy。 And if I ask it for object dot values。

 it will give me an array of the values， Sally 18 and 187。

 And if I ask it for object dot entries of the object。It will give me back an array。

Of little arrays where each littleer array is the key and the value。 You know， now。

 this is all quite useful because now I can come along and I can。

Do this and have a look what each of these three things gives me。

 Keys gives me an array of the keys of strings。Values gives me an array of the values as whatever type they are。

And entries gives me an array of small arrays， which are just the key value pairs。This can be useful。

 maybe， you know， the point is that there are many different ways here to collect data， you know。

Yeah。Good fun。So that's why you don't need the example we show before becauseuse you can do lots of stuff like this。

 And this is really useful。 You know， if you want to say loop through all the keys or loop through all the values or loop through both and you can just Google these things。

 like you know I I'd forget some of them。 I always remember object dot keys。

 but I can never remember what these two do again like off the top of my head sometimes。 So if I。

 if I know it， maybe I'll Google it or maybe I'll just try it out。 know。

 it's so easy to try things out。 then the last part of objects here is that。

You can loop through objects like we do with arrays。

 It's just that the default behavior of looping through objects if you just give it the object is to loop through the keys。



![](img/af879d0ef4b899e7e429a73a844847fb_68.png)

So if I do something similar to what it did with arrays where I say it actually makes a lot of sense。

 Right，cause if you have an array of five items， you know， we go back to our。Thing here。

I got five items， ABC D。When I do like a four con item of， you know， a four， oh I deleted it。

 but let's say you have a four constant item in items or something， right。U。

In these particular cases。This is saying that I'm going to loop through each element and you're going to give me the index。

Whereas when you loop through a dictionary， you get the key。

 which actually makes sense because the in syntax for arrays don't give you the value。

 it gives you kind of the equivalent of the key， which is the index， but for objects you get the key。

And you'll see this here， right， If I have my user data and then I have that for loop there。

It'll actually go like through and print that out。 And you might think， well。

 what if I want the values， Well， it's really easy if you want the values， just go and like。

Go and print out the， the get the user data object and get the value at that key。 and you're done。

Like， there you go。 You know， really， really easy。 And then there's another syntax element of objects that can be really useful。

 which is this one， which is to say， check if name a particular key is inside the object。

 And if it is inside the object， you know， then then that particular condition will return true。

 and you can do something interesting like this has name key。 if you change。

If you change this to say height， it'll also say that it has it， whereas if I change it to you know。

 bh， it's not gonna print out that line because that's not true。

 So this one is also kind of useful if say， you have a key that you sometimes add to an object。

 But you want your code to be able to ask， you know， is that key currently present in the object。



![](img/af879d0ef4b899e7e429a73a844847fb_70.png)

Now。One thing we've seen。Is we created an array。And then we cons logged the length of that。

And this was a bit weird， you know？Like a lot of what we talk about is pretty similar to what you've seen before。

 But this one was a little bit weird， and。This touches on something I mentioned before。

 which is that a lot of what we deal with in Javascript， particularly arrays and objects。

 They're really easy examples。 Like I said， they're not just in sea where they're just data next to each other。

 They're actually these like boxes with all this other stuff in it that you don't need to worry about。

 you know， So it's like if you get your array。 It's not just like all the data you have in it， right。



![](img/af879d0ef4b899e7e429a73a844847fb_72.png)

Like this。It's also like probably some metadata， like the length of it and a few other things。



![](img/af879d0ef4b899e7e429a73a844847fb_74.png)

And in this sense， most things。This is kind of getting to it。Let me just jump ahead。Cool， okay。

 let me explain it a bit bit more detail， so。In C。If you have something like an in A， it's just4 bys。

In indidigenous  four bytes takes up the space it takes up。If you have something like a struct。

 it'll only take up 8 bys because in this case， you know， because you have two ins and each inchs。

4 bys。So these simple types in C were really just basic types that occupied limited memory。

Andstructs were just collected， were just collections of primitive types wrapped into an object。

 We called it， you know， and every time we， you know， we created a a copy of a struct with Malik。

 we would create copies of these objects， right， So if we try and expand this concept into jascript。

Nearly everything in JavaScript is an object。The arrays， numbers， strings， in fact。

 every kind of thing is， but in Javascript， it's not just made up of the underlying data。

 It's often made up of some other properties hidden and some functions as well。

 And if you're not sure what I'm talking about， this starts to get into the area of object oriented programming。

 which we don't really do of any we don't really do any of that in this course， but。

The easiest way you can model it in your head。Is that in JavaScript。Everything is an object。

 and an object。Is basically astruct with functions。Right。

So you know that a struct is just a bunch of data。But。An object in jascript is like that。

 but with more functions。

![](img/af879d0ef4b899e7e429a73a844847fb_76.png)

And some examples of， like。What we mean by this， and I'll show you is if we go and get ourselves。

 say， a stock standard。Aay。Like this。You can actually call some pretty interesting functions on it。

 Like you can actually say， well， you know， if items dot includes a。Andtains the letter A。

You can actually do something like that。And that's quite interesting， isn't it， Because， again。

 if you've come from a sea background。An array doesn't have a like wait。

 way like calling a function on an object。 It's all a little bit weird。 So like。

 my advice here is don't think about this stuff too much because every。

 everything in Javascript' is an object。An array， an actual object objects such a loaded term。

cause like。You know， an object is just an object and as an object technically and gets all a bit confusing。

 but the point is that whether it's an array or an object or an integer or a string。

 everything in Java is a box， and each box has a bunch of data and a bunch of functions in it。

And arrays have this stuff people have asked before。 arrays have a pop so I can print items dot pop。

And I'll get an A。E， sorry， pops the end。 And if I pop it a few times。

 I get all the different letters。

![](img/af879d0ef4b899e7e429a73a844847fb_78.png)

And there's much more than that。 You can go look it up， Javascript array。Just Google this。

Aray object。And I look， and it shows me a whole bunch of stuff like， oh。

 I can get the value at a particular element。 I can concatenate。 I can get the entries。 I can。

 I can fill it， filter it， find it， find index， find last flat， flat mat。 What was the one we did。

 Dot includes dot pop dot push。 There's so much you can do， I could say console log。

 let's see if find， Let's see if B is in that particular one。 oops。😊。



![](img/af879d0ef4b899e7e429a73a844847fb_80.png)

Bs not a function。

![](img/af879d0ef4b899e7e429a73a844847fb_82.png)

What。😮，What have I done wrong。

![](img/af879d0ef4b899e7e429a73a844847fb_84.png)

![](img/af879d0ef4b899e7e429a73a844847fb_85.png)

What do you mean based on a function。Oh， if I pop too much， isn't mean， I duno。Am I going crazy。Yeah。

 I think I'm gonna crazy。Oh， it's a function。 I'm an idiot。 Yeah， okay， I don't wna get into that。

 It's too complicated。Okay， yeah， let's not do that today。嗯。

But some other examples might be index of where index of for instance。

 index of is a really old school function， where if I do that。

 it'll actually look up that particular value and it'll tell me what index it's at。

 So I could actually for instance， here say con index equals items dot index of B and then I could say console log items index and print B。

Like that。 You know， so there are lots of these kinds of functions on particular objects that allow us to do cool things。

 The same is true for strings。Right。Javascript string。

It's got a whole bunch of things you can do on it if you scroll down as well。

 This one's gonna be very big。 Pa end。 There you go。 Here's a function。 Pa end。

 You give it a number of things you want to pad the end of a string with and what you want to pad it with。

 So， for instance， if I down here have a string that's like high Hayden。Can'ts， you know。

 name equals high height and I could console log name dot pad。 Was it pad left or something Pa end。

With say，20 dots。Well， technically they're sorry， this isn't add 20 dots。

 This pads the end until the whole string is 20 dots。 And this is really。

 really useful because let's say you had a bunch of names。 like， you were like， names equals。

 you know， Hayden and Nkil and。Allison like this。 And now I could start saying， well。

 for cons name of names。 I would like to console log。The name。

 but I wanna pat it out all 20 characters。 Why are all our names the same length That was a bit silly。

 That was not the example I was looking for， you know， Jacob。Say， and goat。

Like that's not a name I know。 But， you know， now you have something like this。

 You can actually see that it's very powerfulca， you know。

 it'll actually make sure the strings are 20 dots And you can， there's 70， there's70 great， amazing。

 easy things to do。 But this is what I mean about the language will feel bigger because all this stuff I kinda have to Google。

😊，You know。And there's a lot to it。 There's crazy amounts of stuff you can do。 So you。

 you're just not gonna feel like you get everything。

 And that's just a simple side effect of a more powerful language。

When you deal with a more powerful language， there's so much more that。You don't know。

 And that's okay。 You know， Yeah， Nkil says it's very expansive。 That's definitely the case。



![](img/af879d0ef4b899e7e429a73a844847fb_87.png)

Sir。In Javascript， can you make your own objects？ Yes， you can。

 But we don't cover that in this course。Most of what you do in Javascript will be arrays and objects and strings and numbers and basic things。

 Does this mean that jascript is object oriented？ I hear a lot about object oriented programming。

 You say is this mean I'm programming object oriented。No， not really。

It's a it's a bit of a different thing。 I'd say that， you know。

 you're going to deal with aspects of object oriented programming naturally in this course。

 but don't get too caught up on on the definitions and stuff。 Just， you know。

 let's write code and make sure it works as the main thing。

 So the last set of slides before we get to the feedback at the end is。Basically。

Talking about that we can combine these ideas together， in particular。

That we can combine our knowledge of arrays and our knowledge of objects together。

So what we've done so far is we've just had variables that have either been an object or an array。

But here。I am saying that user data is an array。😡，That contains objects。

So user data is an array with two items， and each item is an object。

 and each of those items has three keys， and each of those keys has a value。

So if we go and play around with this now。O， why is that different。Loop 3， okay， I started with。



![](img/af879d0ef4b899e7e429a73a844847fb_89.png)

Loop 3， apparently。You can see here that what I can do is if I say get me the keys of user data。

Right。Like this。Well， user data is an array。 So when I call object dot keys on that array。

 they're just going to give me back the two keys of the array， which are just the indices。

 just the indexes。 that's why I get 01。 But if I ask for the entries of the particular array。

 it's going give me， you know，0 and then the value at that point， right， because it's an array。

 two items， each item is an object。 So it's going to try print it all out for me。 Now。

 that in itself is not particularly useful。

![](img/af879d0ef4b899e7e429a73a844847fb_91.png)

But， you know， you can kind of see what's going on inside of it。

 Let's say we actually wanted to try and print out everything inside the array。



![](img/af879d0ef4b899e7e429a73a844847fb_93.png)

Okay， so what I might do there is I might say， well， user data is an array。

 So I'm gonna loop through user data， you know， dot length with the， the keys。

And then for each item in the array， which remember， there's just two。I'm going to console log。

For that particular object，'cause remember， user data I。 and like just for context， I'll show you。

 right， If I console log user data I here。Right。It's just gonna print out oops。

So it gonna print out that。 it's just that， you know， user data， I object 0， object 1。

So when I print out user data， I name， I'm going to get the name of the first object， and it says。

 you know， the person's properties are and then it goes name agent height。

 and I go name agent height like this。And I get this， you know， kinda ugly， kind of useful print out。

 Sally's properties are named Sally age 18， height，1 86。Very tall people。



![](img/af879d0ef4b899e7e429a73a844847fb_95.png)

Cool。That kind of we get。But we can make it even more dynamic if we wanted to by simply using what we already know。

 So we know if we use slightly tighter syntax that we can loop， even though this one's a loopops。



![](img/af879d0ef4b899e7e429a73a844847fb_97.png)

Oh， why did I do that， That's weird。 I should change this to a。

Actually let me stay back here for a second， I know that I could clean this up a little bit more by simply going。

Const keys equals object dot keys。 user data I， right， because user data I is an object。

And then here I could say well， for con key in keys， I could now say console log here。

 and I could say， well， the key is user data I key。Maybe let me make this a bit bigger。



![](img/af879d0ef4b899e7e429a73a844847fb_99.png)

We don't need that much spice。And I could get rid of this down here。Oops。What have I done wrong。

So I'm getting the， because。Object do keys use it out eye。Oh， of keys。 My bad。It's really weird。

 right，cause remember， in gets you the index。 And this is like clearly me just getting confused because like。

 if we actually console log keys， you'll see that， you'll see that keys is actually a bunch of names。

 right。See that keys as name age height， but because I did the in loop and not the of loop， I got 0。

1，2 because I got the indexes of name agent and height in their array。Whereas here I'm。

 I'm actually going to I meant to be of。 sorry it was always meant to be of。

 whereas here I'm actually going to get the values out like that。

 So you can see just by using what we know about object dot keys and stuff like that。 And in fact。

 we didn't even need to do this object dot keys thing because we learned before that if you simply take a an object。

 And you say， you know， const key in that object， it will go loop through the keys anyway。

And I get that kind of result。 Now， I know some of you are probably sitting there right now。

 kindnd of， you know， thinking and going like， oh my God， this is really。Sounds like a lot， you know。

 and I'm getting really confused about arrays and objects and arrays and objects and keys and indexes and ins and ofs and stuff。

 And yeah， it is like a lot of information。 But you， you'll， again， you'll pick it up。

 You'll play with it for a， you know， an hour and you'll start to very quickly get a good sense of it。

 The last example we have here was actually just trying to demonstrate。

 Well the second last example is that you don't always need to have。



![](img/af879d0ef4b899e7e429a73a844847fb_101.png)

![](img/af879d0ef4b899e7e429a73a844847fb_102.png)

Oops。You don't always need to have lists of objects。 you can also go and have objects of objects。

Where is that。So in this case here， I've actually got objects of objects。

Where my user data is an object with two keys， Sally and Bob。Each of those keys itself is an object。

 so Sally is an object with age 18 and hide86。And then I can just loop through these differently。

 as well。Now。When would you create lists of arrays of objects or when would you create objects of objects。

 There's no real straightforward answer。 It's， it's really just that。You know。Objects。

Orre when you want to identify information based on a string generally。So in this case。

 it's kind of nice just to say， well， here's Sally's data and here's Bob's data。

Arays are really useful when you want things to have a sense of order。

That's that's one of the main things。Right， fairly， fairly straightforward。Yeah， so Anthony's right。

 Sally and Bob are the keys in this case。 Sometimes they get questions from people like。You know。

 decay keys need apostropphhees like this。It's optional in Javascript。 You。

 they do need the apostrophees if you have funny things in there， Like generally。

 as long as it's just literal letters， it's okay。 But like， if Sally has like a funny thing。

 like a dash， then you do actually need like the apostropphes here。嗯。Why is that。Not working。Oh。

 wrong one。Then you do need the apostrophees'cause if you don't have the apostrophees。

 jascript starts to get really confused。 It's just like， is this minus a minus， like。

 I don't know if it's a minus or a。Just like， help me out。

 So the only time you really need to put the apostrophees there when you're actually， you know。

 having funny characters there。So Anthony's asked another good question， which is。

 so what's the syntax if we want to access Sally's age。 Yeah， that's a great question。

 It really is just a case of saying user data dot Sally dot age。 It's， it's that simple。

That's how you get Sally's age。You know， or you could do it the other way， you could say， well。

 use the data Sally age。Like this。

![](img/af879d0ef4b899e7e429a73a844847fb_104.png)

Same thing。 Get the exact same result。This is the very last example of this lecture。



![](img/af879d0ef4b899e7e429a73a844847fb_106.png)

Just before I talk about that， though， the one thing I forgot to mention tonight。

 just the one thing is that。I， I wanna firstly reiterate that。We do have。

Nll and undefined as ways of saying nothing。 We'll talk about the difference between them more later。

 In the meantime， the point is， you can use one or the other， but just try and use it consistently。

 So that's  point1。 Point2 is that what I haven't talked about as comments。

 commentsments in jascript are just the same as sea。A double slash for a single line comment。

 Or if you wan to do a block comment， it's the slash star star slash approach。 So that's just。

 another quick reminder。

![](img/af879d0ef4b899e7e429a73a844847fb_108.png)

So if we do look at this last example here。What's going on here is we are creating three students。

And each student is an object。 and the object contains， you know， keys， name and。嗯。Score。

And then I'm creating an array called Student， which is just made up of three objects。

 so now I've got an array of three objects and each object has two keys in it。

 Then I'm going to print out or console log the students。



![](img/af879d0ef4b899e7e429a73a844847fb_110.png)

So that should be pretty doable。Which one is it。Where is it。What's it called。1。3 combining， yep。So。



![](img/af879d0ef4b899e7e429a73a844847fb_112.png)

I can just go and do that， right， Oh my God， no wrong file。Yep， there I go。

 I print out the students a list array of three objects bam done。

 but there's a few different ways that I can approach kind of printing it all out。

 The first one is that you know I could say， well， I'm going to go and get the number of students。

 which is students length， which will be three。 I'm then going go and do like four let and I'm going to loop over those number of students each time I loop through it。

 I'm going to get that particular student so this is an object so student here is an object that hast a name key and a score key and then I'm gonna to check if the student score is greater than 85 and if the student score is greater than 85 then I'm going to console log that that student's name got an H D。

Now， this is a very kind of C style approach， a very straightforward approach， what you might do。

 And all the point of this example is， is to encourage you to say， go and get excited。A。

Go and get excited。4， the cool things that ja can do。Right。

Because you can make that all very compact underneath here。You can simply say well。

 for student of students because if you use for of you are looping through all of the values in a list。

 so each time you loop now student is an object and then you can just simply say student do score is greater than 85 so you can really condense things down if you know how to use the language。

That's the last example for tonight。 If you have any questions。

 please post them in the next minute'cause we're about to wrap up and let you get back on with your evenings。

Bonri says， can't you just use students' eye score and students' I name。You can。 Yeah， yeah。 I mean。

 there's， there's some elements of like， just。Poor， you know， efficient syntax here and stuff。

 It's a bit dramatised to make a point。 But yeah， know。

 there's some things that are less to do with the language in order just to do with how the programmings happen。

Daniel says， what microphone do I have， It's a cheapas microphone from。Cogan， it costs like 25 bucks。

 If you Google like Cogan。Microphone， you'll probably find it。 It was very， it's okay。It。

 it's not high quality。嗯。they' debuggs for jascript。 Yeah。

 but we're not gonna go into it in too much detail。C C G R says unrelated。

 but is declaring an array in C essentially just mallicing some space for the array， yes。

9 games says first hour of the lecture is a smiley face。 Last hour of the lecture is a sad face。

 That makes sense。 I mean， the first hour of lecture。

 I was kind of telling you what you're reading new。 You know， just with a different colour。

 whereasas the last hour of the lecture， obviously， we're teaching you stuff。 So， you know。

 don't put too much pressure on yourself。 It's just new things to pick up。 You'll figure it out。

 Nathan says what's happening with next week's Thursday lab since it's a public holiday。

 Your tutors will talk to you about that。 I'll email about Friday。

 I don't have anything to say right now。 We will， we will sort it out。Lockland says。

 how do you create a jascript file to use G edit。 Yeah， you can just use G edit literally。

 like you can just open up Vla and just be like file dot J S。

 And you can just write console dot log My first file。 and then you can save it and close it and。



![](img/af879d0ef4b899e7e429a73a844847fb_114.png)

You can just run it node， file dot J S， and it done。 It's， it's really that simple， super， super。

 super simple。Is there anything front end in this course， No， there's not。

 And the last question I'll answer， I'll ask that everything after this point we post on the forum just to wrap up for everyone。

But there's so much to unpack tonight。 There's so much that like we could keep talking about， but。

The only thing I kind of forgot was the comments。 But to be honest。

 I don't even think I forgot the comments because I。

 I remembered when I was explaining it to you that。

We decided that because the comments are the same as C that we wouldn't talk about it much。

 but there has been a really good question from Danny。Because I， I was touched on in the slides。

 but I， I didn't explicitly cover it， which was。Where was it。Where was it， Danny。

 Ive already forgotten。Something me about equals。Yeah。Back on these array slides。

 this 1 I just kind of forgot to touch on， so。It's a bit weird， but in Javascript。

 whenever you're doing the kind of double equals things， you always need to do the triple equals。



![](img/af879d0ef4b899e7e429a73a844847fb_116.png)

The reason for this is， is kind of odd。But。Basically， if。In ja。It'sOne of the dumb things。

If you check if like， let's say we have const。Var equals our constantino。 name equals 2。

And then I say， you know what， let's check if name is equal to 2。And if name is equal to 2。

 we're gonna console log yaea。Pretty， pretty straightforward。 What I do。Yeah， yay， name is two。

In Javascript， a double equals by default actually compares the value， not the type。

 which is a really annoying language feature。What this means is that's also true。

Even though it ones a char and ones a number， because if the double equals what Javascript tries to do is convert them to the same type and compare them。

 So if they're the same value with a different type。It's the same。 So to get around that。

 pretty much literally every single time。You do it equals。You do a triple equals because。

That compares value and type。And that's how we end up， you know。

 avoiding this scenario where that's not the same。But that is the same。

 And the same is true for the not equals。 instead of exclamation mark equals。

 we do exclamation mark equals equals。You know so just basically always add an extra equals to your equality comparisons。

 That's all that's the whole story there。 So we're at time， I'm gonna end things here。

 Thank you for coming along If you have other questions feel free to post on the forum C next Monday will be online next Monday I think but we'll make decisions about what we're doing next week on a Friday but I'm pretty sure we'll be online next Monday。

 but you'll find out on Friday night we'll get some feedback I'm getting feedback from students and figuring it out as we go so everything streamed online and record it anyway so it doesn't matter。

😊，Thanks for coming。 It was so lovely to see everyone on Monday， whoever's。

 whoever was listening to this and was there on Monday had a great time。 So thank you。

 And have a good evening。 and hope you get some sleep tonight。😊。



![](img/af879d0ef4b899e7e429a73a844847fb_118.png)
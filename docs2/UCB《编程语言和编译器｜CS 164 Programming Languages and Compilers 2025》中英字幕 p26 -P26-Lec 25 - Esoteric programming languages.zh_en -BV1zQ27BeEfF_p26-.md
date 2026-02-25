# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p26 -P26-Lec 25 - Esoteric programming languages.zh_en -BV1zQ27BeEfF_p26-

Hello， hello。Hello， hi， hello。嗯。You'll see。But I think。原告方。Holy see， specifically， I think。

It's the product of a lot of dedicated time and effort。That's right to say about。哦。Okay。

 can everyone hear me？Is a single one。Cool， okay。Yeah。

 we'll give it one more minute and then we'll get started， hello。Yeah。

 feel free to sit sort of closer。 Yeah， we'll be。Doing pair discussion。嗯。Hello， hello， hello。What'塞。

😀Yeah。😊，Oh yeah， how's Har y'allza？Pre Thanksgivings going。 Any fun plans。 go okay， yeah。

 that's fair。Do we feel excited for the break？That's real。I it mostly just work is it like yeah。

Now it's difficult， I feel like at the end of the semester， things just sort of pylon。Hello。Yeah。

 so if y'all want to come closer a little bit。We'll be doing sort of pair group activities。Yeah。

 you can filter just sit closer to the front。嗯。Cool， okay， it is。340。

 so I'm going to go ahead and get started。Yeah。Hi， welcome back to C S 164。 I am very。

 very excited to get to guest lecture for y'all today。 I know it's the week of Thanksgiving。

 And I'm sure folks are feeling a little tired at this point in the semester。

 I know I'm also feeling a little tired at this point in the semester。 And so today。

 we're not gonna be doing 90 minutes of Ocal。 instead。

 we're going to take a little detour and talk about something a little bit difference。😊，Yeah。

 before we get into that， just some quick logistics announcements。

 The first part of homework8 is due today 8。1。 so make sure you have your benchmark submitted if you haven't already。

 And then there's an announcement made about this on B courses。

 but homework 8 in full is due next Thursday， So not during the holidays。

 but it'll be due next next Thursday， the fourth。 And then also we'll be making an announcement about finals logistics soon。

 So be on the lookout for that in your B courses announcements。But yeah。

 I'm sure y' all can see the slides。 today we're going to be talking about esoteric programming languages。

 And so to explain what I mean， I'm going do， we're gonna to do a little bit of reflecting on the course so far to begin with。

😊，Yeah， so up to this point in the semester， y'all have been very hard at work building your own language from the ground up right and a big part of what we've been trying to show y'all is that a lot of the features that are in the programming languages we use every day。

 these features and these decisions don't come from nowhere right In fact。

 these language features were decisions made by people just like us。

 and they often weren't obvious decisions to make at the time。

 and so languages over time have made have had different features and made different decisions depending on what worked and what hasn't worked with previous languages and so in the process of designing our language we've had to make a bunch of these choices for ourselves。

For example， closer to the beginning of the semester。

 we spoke about using lexical versus dynamic scope and that being a like explicit choice that we had to make around how we want variables to work in our language And in our case。

 we decided to use lexical scoping for our language and when we were thinking about why we might make that decision。

 you know you can think of a few reasons why you'd want to use lexical scope rather than dynamic scope right maybe you could say oh。

 like lexical scope is easier to visualize if you just look at the text of the program。

 you could say you know like functions will behave the same regardless of where they're called。

 So there's no dependence on kind of the like dynamic environment at any particular call site right And in general。

 we might say that you know having lexical scope makes code easier to quickly understand and maintain。

 And so for those reasons we're going to choose lexical scope。

And so the sort of broad lesson here is that the decisions that we make about these languages are informed by the priorities and values that we're bringing into this process。

 right， What do we think is important work to do with this language。

 who are the kinds of folks we want to support。 and you know。

 these are the same kinds of questions that inform the designers of all the languages that we use today。

 right， So Python O Camm will see the rest of it。And so， yeah， today。

 we're gonna be talking about some more out there， more speculative programming languages。

 And I want to give y'all a taste of what else is out there in sort of programming language design land。

 and to sort of frame our discussion。 We're going to be starting with a little bit of a hashtag throwback。

 We're going to be doing the brainstorming activity from the beginning of the semester。 So。😊，Yeah。

 so this is， I just took a screenshot of the reflection activity we had from， I think， a week 1。

 And I want you also to take a few minutes to think about。😊。

Your experience of the course so far and I want y'all to think about both the values and the goals that brought you into this course and I also want y'all to think sort of retrospectively right how has the course been helpful or maybe not helpful to your values and goals how have your goals and values changed as results of being in the course know what brought you to this course initially and is that the same or different as what brings you to the course right now。

 So yeah， what we're gonna to do is I'm gonna give you a few minutes to sort of think on your own just sort of quietly brainstorm about this。

 And then in a few minutes I'm gonna to have us transition into paylash small group share time。

 and for the folks in the back if y'all would like to push up to the front at that point for the sort of pair discussion portion。

 y'all can do that then But yeah I'll give you a few minutes we will just reflect on this for a moment and then。

Yeah， I'll put you on or sort of have us go to pairs afterwards。Yeah。

 and if typing things out or writing things out would be helpful for y'all。

 y'all are free to do that as well。Yeah， I'll give us until 350 to keep thinking and then we'll start discussing。

Okay， I'm going to have us turn to a neighbor to discuss if you are neighborless right now。

 I'd encourage you to move closer to the front so you have a discussion partner to discuss with。

 and yeah， we're gonna reflect on these these questions a little bit be prepared to share afterwards I will be asking for folks to volunteer their own answers if that feels comfortable for folks。

 So yeah， we'll have five minutes turn to a neighbor and we'll discuss。

So thanks everyone for sharing， it's excellent getting to hear y' all discuss。Yeah。

 so today we're going to be talking about some fun and quirky languages and languages that are a little more speculative than sort of the ones that we've been exposed to so far。

 So I think we're having a discussion about being able to make our own languages and making sort of these more domain specific languages。

 And to that point， I put up this image on the screen here。

 this is a colorful sort of abstract looking image And I'm trying I'm going to try to convince you today that this is code in a programming language。

 in particular， this picture is code in a language called Pit created by David Morgan Mar in 1991。

 And if you run this program in a Pit interpreter it will produce hello world。

 So I'm going to try and convince you that this is a hello world program。

 And in general today we're going to be going over languages that look like this these sort of more esoteric programming languages as they're called And you know partly I'm doing this because it's fun。

 some of these languages are often a little silly。😊。

But I think they can be sort of productive for us too。

 A lot of these projects are inherently speculative， right。

 They're not designed to be efficient or optimal or even useful necessarily。

 but they're designed to explore questions people have around languages and around programming。

 So you know what might it look like to have a language that's designed for beauty or for aesthetic quality。

 How can we use existing technologies in novel or surprising ways。

 What would it mean to design a language that's unusable or difficult or frustrating。

 right I think it's useful seeing sort of the other questions we can ask with our languages other than can we make a language that's easy and fast for some particular target domain in some particular definition of easy and fast。

😊，嗯。😊，And I think these esoteric languages also make it very obvious that。

 you know these languages are a constructed things that they're made by real people who make decisions constantly about who and what they think is important。

 And so y'all have spent the better part of a semester now thinking really deeply about how to build and design a language from the ground up。

 know you've seen firsthand sort of all the decisions that we kind of take for granted in languages today。

 and you know these are all ordinary decisions that regular people make and so I want us to think expansively about why people code about why people create languages and the values in politics that come with that kind of work。

 And I want us generally to think about how values in politics come with the work of doing computer science and about the kinds of values you want your own sort of computing artifacts to inhabit。

So yeah， it's a lot of intro。 So we're going to start with a tour of some of these languages。

 after that， we'll do a little biobreak and then we'll break into another brainstorming activity for the rest of class time。

 if that sounds good with folks。😊，Am。Cool， and you know， as we move through these languages。

 we're gonna be returning to this central question a lot of what values are these languages designed around。

 And we're going try and put ourselves in the shoes of the folks who made these languages and do the same brainstorming for them that we did for for ourselves earlier in the slides。

 And so yeah， if you have any questions at any point。 feel free to just shout it out。😊，And just yeah。

 stop me and shout out your question if you have any， very happy to answer questions as we go， yes。

question。And are centered around。What is that do like。In like， that's with Vietnamese or like。

We will get to this。 In fact， we have some languages explicitly asking this very question。

 So a good question， yes。Oh sorry， never mind。But yeah。

 we'll get to why sort of languages are predominantly in like written with English keywords as opposed to other languages。

Okay， so we're going to start with the first language and the sort of central question at the heart of this particular language is what if we wanted to use programming to express mathematical ideas。

 So to give you a little bit of background， this guy right here。

 his name is Ken Iverson and in the 60s。He was trying to come up with a notation for math that was more standardized。

 right， So he's trying to express these algorithms。 He's doing you know。

 like whiteboard writing on the whiteboard， teaching math classes， that sort of thing。

 teaching algorithms classes。 And he realized that， you know。

 existing math notation isn't ideal for this。 It can often be kind of nonstandard。

 It can be difficult to express these kinds of algorithmic ideas。 And so he was thinking about it。

 And he was like， okay， you know， I'm looking for a notation that's kind of standardized that has some kind of like standard syntax and semantics。

 And he realized， oh， like what I'm looking for is a programming language。

 I need to make a programming language to express these kinds of algorithms。

 particularly these kinds of like mathematical。Problems right， And so in 1966。

 he wrote a paper called a programming language APL for short。

 And this is the first language we're going to be walking through。

 So I've put up a sample APL code on the screen。 it looks pretty normal here we're adding two things。

 two variables together。 A and B。 So one of the interesting things about APL in the way that he that can Iverson design this language is that it will operate on lists the same as it does on like individual items。

 right， So let's say a is a list like numbers  one through 4。 B is another list，5 through 8。

 I don't know， right。This expression right here will work if A and B are both lists。

 And so what will happen is if A and B are defined this way， it will perform an element wise edition。

 So each element of a will be paired with each element of B。 And then you'll add those items。

 element wise together。 and then you'll get back another list of those things added together。

 So that's the sort of first kind of like interesting， interesting thing about the language。

 the second interesting thing is that and this is often what AL is kind of infamous for is that a lot of operations aren't expressed using natural language。

 but rather with these fun and funky symbols。 And so I'm showing you here a function that computes the average of a list。

 And you might be saying David。😊，That is is not say average。 I don't know what's going on。

 So we're gonna break down what's happening here。 So those outer curly braces are denoting please define a function。

 So if you think of the like defined keyword that we have in 164。

 those braces are doing the same thing and they are binding the omega keyword to the argument of this function。

 next evaluation proceeds right to left。 So if we start with the sort of right the rightmost expression that sort of three lines with a line through it。

 that represents get the number of items in this list。 So when we apply that to omega。

 we're getting the number of elements in our argument list。

 the division sign is dividing into and then the sort of parentthesized left expression is take the sum of all the elements in omega in the argument that we have。

 So plus represents addition。 the sort of slash sign with a little horizontal line through it that represents reduction。

 So what we're saying is do a plus reduction over this list。 In other words， sum together。😊。

All the list。 And so this is the kind of other defining feature of APL， right is。

A focus on terseness and sort of representing these more complex operations with symbols because it's meant to be mathematical notation。

 right， This is supposed to be intended to be things that you could write on a whiteboard。

 It was never intended to be typed to begin with。 And so when Ken Ivererson was designing this language。

 he was designing it around。 What are symbols that are easy to handwr and express sort of complex operations very。

 very tersely。Yeah， so we'll keep moving。We're gonna walk through a couple other examples of some programs。

 I can't explain what's happening here。 I'm gonna be fully honest with you。

 but just to give you a taste of what AL programming looks like。

 here's a Sudoku solver written in what is that five lines of AL。 this does all of Sudoku solving。

 Yeah， so that's one example。 And then y'all are very familiar with implementing a compiler at this point。

 This is the entirety of an APL compiler。😊。

![](img/6ebca2159f47b9f2732989a54be75e7b_1.png)

Not including the runtime。 So this is not complete， yes。This is compiling to。

I believe it's compiling to a byte code that is interpreted by the。By the run time。

 but that might be incorrect。 if you're looking for more information。

 The compiler is called Codens spelled CO O， hyphen， D， F N S。

So we can check in about this afterwards because I think that might be。

 I think what I just said might be incorrect， so I don't want to spread misinformation。

 but you can look that up and it should have more information。 but yeah。

 this is this is a an APL compiler。😊，And so yeah， just to give you an idea of how Terse you can get with APL code。



![](img/6ebca2159f47b9f2732989a54be75e7b_3.png)

This is an example。Now， I think one of the interesting things about looking at APL is seeing how it has influenced sort of later programming language development。

 So here I've put up another snippet。 This is find all prime numbers between one and 100 again terse。

 as we would expect and here I've put up a snippet of nuy code next to it if you don't know is this sort of like scientific computing library for Python for sort of processing lots of data And if you know。

 if you like squint at the code in the right way。 and you like rename the functions in the right way。

 and you like you kind of like angle it just write you can see that there's kind of like like a family resemblance between the Ny code and the AL code。

 And in fact， you know， a lot of the nuy operations。

 one of the defining features is that they apply across an entire array So you're not doing like explicit for loops or anything。

 you're writing these sort of functions that will apply element wise to lists in this way。

 And so you can see this sort of like。😊，General kind of influence of AL's sort of style of computation。

 moving forward into Ny。And in fact， we can。You know。

 we can get even more sort of explicit about looking at where inspiration has taken place。

 For instance， Numpy has this function called ravel。

 which kind of like flattens a bunch of nested lists into one sort of flat list I'm going to be honest with y'all。

 I would not have picked ravel as the name for this function a little bit of a strange selection。

 Why would they do that And it turns out the reason why they did that is because they're looking at AL right And so the original operation that they're pulling from is AL's ral operation。

 which does the same thing in the original implementation of AL And so I think what I want to highlight with this particular example is that。

 you know， these languages have history and they're often very historically contingent。

 people are making language decisions and naming things and making design decisions based on what they're familiar with based on inspiration they've taken from other sort of languages that are common at the time。

😊，Yeah， so yeah， that's APL。Okay， so I think one thing that you might have noticed and about these。

 these programs is that they seem pretty hard to write and pretty hard to debug。

 This is sort of a common critique that's leveled at A is like。This is like right once programming。

 right， You write this program。 And then it's this like inscrutable mess of symbols。

 And so we can start asking questions about that。 right。

 What if we don't care about making it easy to programming the language。

 What if we just sort of let go of that expectation。

 This is something that an expectation that is sort of。

Kind of implicit or common when we think about programming languages。

 but that doesn't have to be the case， right， That's a choice that designers make。 And so we can say。

 what if we care about other things， For instance， what if we wanted to make the simplest possible language to implement And so this is the second language we're going discuss。

 It was made by Urban Mueller in 1993。 for the purposes of course lecture， I'm going to call it B F。

It stands for something that you can look up in your own time， I will not elaborate further。😊。



![](img/6ebca2159f47b9f2732989a54be75e7b_5.png)

So as I mentioned， this language was designed to be as simple as implement as simple to implement as possible。

 Again， here's the entire compiler for this language。 It is 240 Btes。

 and this does compile to straight to assembly。 And yeah。

 this is the entire compiler for the language。😊，Includes everything， the runtime， all the rest of it。

 The reason why it can be so simple is that it only has eight operations。

 So you can imagine basically this language is modeling a kind of like really simple turing machine。

 You have a strip of cells。 you have some operations for increment and decrement at the current cell moving around which cell you're pointing at。

 And then the square brackets denote this kind of like looping operation of like if the current cell is0。

 go to the matching bracket。 So you can think of it as a kind of like conditional jump that you might be familiar with。

 So yeah， this is kind of like a really simple sort of assembly kind of kind of situation。

 very simple simple language。😊。

![](img/6ebca2159f47b9f2732989a54be75e7b_7.png)

And so again， we can look at some example programs。

 Here is the program for adding two values together。 And again。

 you might be looking at this and being like， what's going on， So we'll break it down。

The brackets the note a loop。 And as long as the current cell is not zero。

 we are going to remove decrement from the current cell and then add one to the adjacent cell。

 And so if you do this in a loop， what you end up with is adding two numbers together and storing the result in the second cell。

Yeah， any questions about this or anything confusing about this so far？Cool， okay。Yeah。

 I think what's interesting about B， F。 or one of the things that's interesting is that idioms will still emerge。

 So even though this language is incredibly simple and very， very bare bones。

 people sort of communities of practice will still spring up around these languages and sort of common phrases or idioms or patterns。

 design patterns， if you will， will still emerge around these languages。

 I've put up a few examples here， one of the the bottom one。

 the bottommost one is just the code for clearing a cell。 So just setting a cell to 0。

 And then the middle one is the copying the value of the current cell。 And then。😊。

Putting it into the next two cells and then sending the current one to zero。

 And so sort of BF practitioners will sort of build up a kind of repertoire of these different phrases。

 right。Here is a BF interpreter written in BF。We we're getting real meta here。

 But this is a complete implementation of an interpreter of B， F in B F。

 And you can run this on a B F program。 And it'll give you what you'd expect。 As you can see。

 people who make languages love making interpreters for other languages。😊，It's how it goes。Yeah， so。

 you know， returning to the original reason why this language was made， you know。

 I think it's cool that this language exists and that folks are able to make complex programs in it。

 that's pretty cool。 But also， you know， having a language that's incredibly easy to implement ends up being fun for some other reasons。

 too。 And so one is that it's a useful place to learn about compiler optimizations。

 So the language is incredibly simple and there are lots of low-han fruit for implementing for different strategies of how to optimize code。

 And if you search up like Bf compiler， you'll see bunches of folks on Github just like figuring out different optimizations and ways they can compile B F code。

 I mentioned this because it can be helpful to look through these examples for homework 8 in which you are expected to implement compiler optimizations。

 hint。😊，U。Yeah， so that's sort of one thing。 Another thing is that people like implementing B F in a variety of different languages。

 It's such a simple language to implement that people will have fun just sort of trying to write B F interpreters or B F compilers in really interesting and strange。

Interesting in strange ways。 So as an example。How many of y'all are familiar with Typescript。Okay。

 okay， that's like a good， a good， a good swath of the community here。

 So as I'm sure y'all are aware， Typescript， it's jascript， but you can add type annotations， right。

 One thing that you might not have known is that。😊。

You can implement a BF interpreter using the Typescript type system。

So this was this particular implementation was here has the like we have this import type BF thing going on。

 We pass in the program as a a type parameter。 And if you go into VS code and you do the sort of like highlight this type。

 what is it please， as you can see， it will。Run this B， F program at。Compilile time。

And so you can actually implement a full BF interpreter using the Typescript type system。

 and you can get stuff like that going， which is fun， and I think is is is very fun， yes。😊。

I believe it is turncomplete， yes。The question was is Type scripts type system turn completele。

 I think the answer is yes。嗯。Yeah， and so we get to do fun things like this。Yes。Like making。ly。Yes。

 yes， yes。Cool， okay， we're going to keep moving， but yeah。

 this is a fun thing that folks implementing languages can get to do。U。Yeah， so， you know。

 that's one example of what happens when we stop caring about is programming easy。

 but we can go further。 And in fact， we can ask ourselves what if we made programming intentionally difficult。

 right， What if we tried to make a programming language that we did not want people to write programs for and so。

This is the goal of a language called Mulge， it is I pulled this sort of summary off of Wikipedia。

 apparently it's named after the eighth circlecle of hell。

 which gives you a sense of the kind of vibe that the language designer that Olmted is going for with this language we'll go over this sort of a little bit quickly。

So this language has8 instructions。 So sort of similar to B F in some ways。

 And these are sort of like， it's sort of like， again。

 like a kind of bare bones assembly kind of language。 The things that make this language interesting。

 I'll highlight two different features。One is that there is no move operator， right， So normally。

 even when we looked at B F， we could sort of like directly set memory with the sort of plus and minus operators。

 obviously， with assembly， we've been using the move instruction and all these things。

 Here we have access to none of that。 The only way that you can set memory is via this operator called the crazy operator And there's a table for like。

 here is the particular like operation of the crazy operator。

 And all values are stored in Turnernary。So yeah， numbers are allern in this language。

 So you have to use that table to figure out if you want to set values together， how to do that。

The second interesting thing about this language is that when a program is run。

 it's sort of loaded into memory。 And then whenever a an instruction is executed。

 it is encrypted afterwards， so。😊，You can't run like the same program will not run twice， right。

 because when you run an instruction， the instruction will change in memory so that if you get back to that same。

 if you know， reset the instruction pointer， quote unquote， to where it was before。

 it will be executing a different instruction。😡，This makes programming in this language quite difficult because you don't really know what's going to happen。

When you run the program。And so again， I'll give you some example programs。 here's Hello world。Oh。

And not only does it look kind of ridiculous， It also took two years after the language was invented to be discovered。

 And so basically， somebody wrote a Lsp program to search。

Different possible programs in this programming language and came across this language that prints out Hello world。

 Here is another example program。 This one is a clone of cat。

 So if you're familiar with the Unix cat command that just prints out the contents of a file。

There's cat for you。And here is the first1 thousand bytes of a listsp interpreter written in this language。

I genuinely cannot explain what's happening。 And not only that， the full like。

AFile that implements this list interpreter is 300 MBbyte。Am。It's a little big。 And so， yeah。

 this language was sort of intentionally designed to be as， as a。

Imposible to understand and impossible to write as possible。Yeah， was there a question over here？

Yeah， any， any questions at this point。Cool， okay， we'll keep moving。So。That's fun。 You know。

 we took a tour through some languages that are designed。 maybe for not。

 the definitions of Easiness or。😊，Yeah， usability that we might sort of normally gravitate towards。

 but now I want to pivot us to a slightly different question。

 And so here I'm going to introduce you to the abstract art of this artist named Pit Monreion。

 He was a sort of abstract painter from the 20th century。

 and I've put up a few examples of some of this art here on the screen。And yeah。

 he's sort of considered to have pioneered the field of kind of geometric abstract art。Now， you know。

 around the 90s， someone took a look at these paintings and they're like， wow， these are really。

Interesting and really beautiful pieces of art。 I wonder if we could make our programming languages look like this or sort of code in our programming languages look like this。

 And so that is exactly what David Morganmar did with the language Pit in 1991。

 This is the language I alluded to from the very start of the lecture。

 Here we have a few example programs in this language。 we have on the far left。

 a program that tests if a number is prime in the middle。

 we have a program that prints the word Pit and on the far right。

 we have a Valentine's card that someone made for their partner when you execute the program that prints out a little Valentine's。

😊，Yeah， so I'll walk over what's going on with this because you might be looking at this。

 you might be thinking， hey， that's a picture， that's what's happening。And basically。

What's happening is we can break down。A picture into a bunch of pixels， right。

 And we can interpret those color values as information。RightAnd so once we can do that， we can say。

 okay， like if we see this color and then we see that color， we can interpret that as an instruction。

 And then you have yourself a programming language。

 So here I've made this sort of very simple example program。 And in this language。

 changes in H are interpreted as different instructions。 So we have a sort of like color chart。

 These are the like 18 primary colors that you're allowed to work with。

 In addition to black and white。 And there's also a sort of predefined list of like。

If you see a change in hue of if you see sorry if you see a change in hue or a change in brightness。

 this is the instruction that you should run。 So basically what's happening is when you start execution。

 you have you can imagine yourself kind of starting at one pixel and pointing towards the right the interpreter will move to the next color in that direction and will evaluate a run an instruction based on the change in hue or brightness from the previous color to the next color。

 if we run into one of these black squares， we will rotate ourselves 90 degrees like the direction we're facing and then。

Yeah， if we run into four， I believe， four blank cells in a row that will end execution。

 So this sort of snippet here just adds to the current cell in the sort of program state。嗯。So yeah。

 so if you start with that kind of starting point， you can do a surprising amount of things。

 And here I've put up a a range of sort of example pieces of art slash code from different folks in this language。

One thing I would like to point out。 So the second image from left at the top row。

 the character to ASI code program。 That actually was not originally a Pi program。

 That was a piece of art that somebody had just made， and then somebody else came along and said。

 hey， this kind of looks like a Pi program。 Is't that funny。 So they took a picture of it。

 And then they turned it into a Pi program sort of like transcribed it， if you will。

 using the primary color palette。 Turn out it's a valid Pi program。

 And it what it does is that if you give it an ASI character。

 it'll print back the sort of ASI code of that character。

 which I think makes it the first accidental Pi program。😊，But yeah。

 I think what makes this sort of set of programs interesting to me is that it makes very visible the kind of alignment between creative practice and programming。

 You know， oftentimes we use the phrase like code style。 And here。

 like it is a very obvious manifestation of what code style means， right， like all these。😊。

Pieces all these sort of snippets of code look very， look very different， right， And I think also。

 it's interesting how， you know， you have this like， very constrained environment for。

For programming， and yet people are able to take it in very different and very creative directions。

So yeah， that's the Piat language。Um。Yeah so as I mentioned at the start of this lecture and as y'all have seen。

 you know both in y'all's work sort of filling up 164 Lng and in these sorts of case studies when people design languages。

 they're making explicit decisions about who they want to design these languages for and what kinds of work they want these languages to do So if you think about like Oca or Python maybe we want to help like software engineers write more correct code。

 maybe we want to help like scientists write code more quickly like these are the kinds of like motivating sort of stories that we tell ourselves when we design languages and in the languages that y'all have seen during this lecture。

 these goals have been a little more speculative So maybe we want to make a language that's interesting to implement or yield programs that are aesthetically pleasing and the design of these languages is not separate from history or broader society but it's deeply embedded in the context that it's created we see how future language features and vocabularies are informed by past language work with Pi。

 we can see how like language design can be influenced by contemporary like art and culture right。あ。

And， you know， I think another way of saying everything that I just said is that like language design work is political。

 right， And I don't mean this in this sort of like politics as in like the electoralpoli political system。

 But I mean that in the sense that these languages and their designers are trying to affect change in the world in some way。

 and the ways in which they're trying to affect change are informed by the past and current social political situation。

RightAnd so， you know， when people do language design。

 they have a sense for the kind of world they want to live in and the kind of world they want to make possible with this language。

 And that sense is informed by the world they live in now and how that world came to be。

 And so I want to go over a few examples of language where the kinds of politics they embody are very clear and maybe a little different from the languages we've seen so far and one common thread that's going to run through these two languages I'm going to discuss is that they're both trying to do language design in service of historically marginalized communities know in the society we live in today。

 There are lots of folks who face sort of different and overlapping kinds of marginalization。

 folks of color Koreanan trans folks， disabled folks， poor folks。

 These are all people in communities who are。Either ignored or actively discriminated against as a result of the structures that exist in society。

 And so， you know， for folks who do language design。

 oftentimes they see it as kind of not their problem， of sort of like， you know。

 we think of our work as like purely technical as not having any kind of politics or any or language designers not having any agency over how society is structured。

 But I think as we've gone over in this lecture This isn't true， right。

 these politics aren't always visible， but they're always there。

 if you're designing languages for big tech software engineers doing big tech work。

 that's a kind of like political statement。 And so I think the next two languages do a really good job of breaking that misconception。

 of showing and teaching us what it means for language designers to come in with a very explicit kind of politics。

And yeah， a politics that sort of prioritizes folks who are at the margins of our society and sort of invites them into computing spaces。

Okay， so what does this mean so the first language I want to talk about is a language called Creeharp。

 The big text of big block of texts I've placed on screen is from a blog post that I'll be explaining。

 But yeah， Crharp was created by this person named John Corbett he's currently a faculty member at Simon Fraser University in Canada and he's also Meti。

 which means he is of mixed indigenous descent。 and in particular。

 John is a member of the Cree people， which is one of what Canada calls its first nations。

 So nation or people of indigenous folks who lived in what we now call Canada before European settler colonists arrived。

 And so his goal for building this language， was to build a programming language for the Cree people and thinking about what it would mean to build a language around Cree language。

 culture and way of life part of that is language right So I think coming back to this question of well why are all the keywords in the languages English a lot of that just stems from the fact that a lot of the early languages that came about were from the。

We and from like military institutions and economic institutions， housed in the United States。

 They speak English。 They ended up using English keywords。

 And now we just have English and all the programming languages。 and so。You know。

 if you'd like to learn more， I would highly encourage you to look up John Corbet。

 There is a very helpful blog post online an interview that happens between him and this artist named Daniel Tempkin discussing this language。

 But yeah， I guess just showing a little bit of the language on screen。 So yeah。

 part of it involves thinking about the spoken language of keywords in our programming languages as part of this work John replaced these English keywords with C keywords part of this work also means thinking about incorporating Ccult logics sort of deeply into the language and the constructs that the language provides。

 And so one example I'll give is that in this language every program has to open with something called a smudge。

Essentially， what a smudge is is a kind of like cleansing ceremony to reset things before they're used and this ceremony is common in preulture。

 And so in this language， before every program is run。

 it is required that you issue a smudge command to sort of prepare the rest of the program to be run。

 And in this way， it's doing a kind of like cultural representation of what the computer is doing。

 You're resetting it to prepare it to provide whatever the rest of the program is going do。 So again。

 if you're interested in hearing more。 I've just sort of skin the surface here。

 But I would really recommend looking at more information about this。Because yeah， I think yeah。

 the interview is full of very interesting tidbits and insights。A。Yeah。

 and then the last language I'll touch on is a language called wordplay。

 so wordplay was initially published by Professor Amy Coh in 2023。

 who is at the University of Washington and she does work with both programming language research and sort of human computer interaction research and in 2023。

 she built this language called wordplay。 partially as a kind of art project。

 partially as a way to teach younger sort of middle and high school students programming and the language is designed to help folks create interactive stories。

 animations， performances， that kind of thing。 It's a bit of a synthesis of a lot of the other discussions we've had with the vast。

 the past five languages。 It's also kind of speculative。

 It's asking artistic questions and it's a little bit funky。

 but it's also very clearly grounded and political in a few ways。

And so she also wrote a blog post about the development of wordplay。

 and she was very explicit about her goals with the language right。

 similar to John Cortt and similar to the discussions we were having earlier。

 she was thinking about how to decenter Englishlishspe countries and cultures and the design of her language and she's also thinking very critically about disability and the ways that we can make programming language more accessible to folks with different disabilities And we had some exposure to this in 164 during discussion we had the screen reader exercise where we implemented screen reader support for 164 Lang。

 And so thinking about that extensiveively about what it means to make accessible languages and so。

In thinking about wordplay， we can see how these politics sort of manifest at every kind of micro point at every micro level point of the design of this language。

 So for instance， all the sort of corear syntax in this language is purely symbolic。

 So there's no defined keyword or let keyword you define variables with the kind of like infied colon operator that you can see up there。

 And as with C sharprp we're moving away from using English words to like define or let to allow folks of different cultures and backgrounds to engage with with the language。

 we can also sort of squint and see some like resonances with AL thinking about using symbols as。

A way of describing operations， right？The other choice that was made during the design of this language is that all of UniIcode is considered a valid language construct。

 So you know， in some other languages， including， I believe 164 Lng。

 identifiers are limited to ASCI characters， right。Obviously， for many languages， this does not work。

 And so the choice was made to explicitly allow all of Uniiccode to be used as identifiers。

 So I'm showing some example code up here。 I'm a Vietnamese。

 And so I've chosen to have two of the variable names be in Vietnamese。 and then the first variable。

 Ive named the gender neutral person emoji。 And things just work， right。

 You can just have variable names that are emojis。 know， Vietnamese words。

 words in any sort of language that can be typed with unicode。 And it'll just work。😊，Right。

The other thing is that the language is sort of explicitly designed around teaching and debugability right so when the language was being designed。

 it was very explicitly the choice was made very explicitly to not prioritize like speed or efficiency or things like this but rather to give programmers the sort of maximum flexibility to be able to learn from their code and debug their code。

 what's being shown in the video right now is stepping through the execution of the code and seeing the results from each subexpression show up and this language features something called time travel debugging。

 which means that you can literally go to any point during the execution of the program and see the state of the program at that point。

 so you can go straight to the end of the program like just running the program。

 you can rewind and go back to the beginning。 you can skip to the middle you can skip around at any point along that sort of timeline and see the state of the program。

And then lastly， thinking about accessibility， there are few sort of ways that this language has been designed around accessibility。

 thinking about sort of different ways to input programs， So not just being able to type。

 but being able to sort of like drag and drop things sort of scratch style right or using like touch if you're on a phone or like an iPad or something being able to program that way。

 it's designed for screen reader support。 So again。

 sort of hastag throwback to our 164 assignments and adding screen reader support sort of similar treatment happening there。

And also， the sort of more sort of quotidian things of like。

 it follows like web standard accessibility guidelines， right， there's color contrast。

 like the links are sort of made clear， that sort of thing。An。Yeah。

 so that's a little sort of lightning tour of all these different languages。

 and I hope y'all have been able to see just sort of getting a sense of what's out there in terms of language land So yeah。

 we're going to take a very short five minute break just to give everyone time to stand up stretch。

 breathe， do whatever you need to do， get water， etc ceter。

 and then we'll come back into brainstorming activity。😊，Yeah。Okay， we're going to come back together。

Yeah， and we're going to do some interactive activity time。Yeah， we're gonna ya。 So I'm gonna put up。

 I've put up a prompt here for y'all to pause， ponder and think about。 Yeah。

 So I want you all to think about a community of folks for whom you want to make computing or programming easier for。

 So this can be very general。 or it can be very specific。 Maybe it's like。

Your grandba or your friends right it can be very， very particular if you so choose and I want you to think about if those folks have programming needs or if you could imagine those folks have programming needs and if so。

 what would a language design for them look like So yeah I'll give us a few minutes to just sort of sit and ponder about that and then I'll have y'all break out into pairs afterwards。

Okay， let's turn to our partners and。Discuss。We're going to come back together real quick。

 I've heard some excellent discussion from both sides， if y'all would like to share。Yeah。Actually。

 a question we had。Would' it be suitable to like slap AI on like L else？

Or like just like non professional coder。Like a condo， right？所的L。Like。

 you gave like natural language。He a natural language。Yeah， so I guess the question is like。

 what about adding LLMs as a kind of like interpreter， I think。I。

 and feel free folks can correct me if I'm wrong。 But I think that is a lot of the。Like。

Proported benefit of things like the sort of Microsoft Office Copit is there're like。

 we put the chat box in Excel and we can do accounting for you。Which is interesting。

 And I think within like P L research， within HCI research。

 there haven't studies done by like looking at whether or not。

Giving folks L O Ms actually improve folks a with coding。 I don't know the specifics。

 but there are some studies。Where they looked at programmers who were given these tools and found that oftentimes the code that was produced using these tools was took both longer time and also was less correct。

 And I'm happy to talk more about that after class。 because I yeah。

 the details are a little fuzzy right now。 But I think in practice when Lms are introduced to these environments。

 they often。You know， people will feel better， they'll be like， I'm so productive。

 like I ate that up and in fact， like it makes things more difficult for everyone。嗯。Yeah。

 other thoughts that folks have。Yes。嗯。Yeah， yeah。 so thinking about。

Computing education and pedagogy and how to design our languages。Aaround pedagogy。

 this is where things like Snap， as you mentioned from Berkeley， Scch from MIT。

 also things like wordplay， you know， come the come to the scene of how do we design our languages to present computing in approachable way and not in this kind of like intimidating or sort of。

Isolating kind of kind of way， yes。嗯。嗯。Yeah， cool。Sa， so yeah。 So。

 So having a like tactile programming interface where you can， I guess you are literally。

 you literally have building blocks for sort of visually impaired folks。 That is super s。

 Do you know the name of the the lab。😊，disabilityisability La， you said， sick，Yeah， no。

 that's super cool。 And I think folks have。😊，Yeah， I'm trying to think of the name。U。Yeah。

 there was this installation space called Dynamic Land by Brett Victor。

He used to do a bunch of computing computing research or does computing research。

 And I think for different purposes。I don't know if he's taking a necessarily like explicitly disability justice oriented lens。

 but his system is like programs are like printed out on pieces of paper and it's this like whole room setup up。

 there's like projectors and cameras reading like QR codes on the paper and you can it'll like read the program and like the sort of inputs are all like projected onto the tables and on the workspaces they have literally likelet like they literally have folders with like the program and you just like take out the program and like put it on the table a similar kind of vibe。

 I think of like what if our programs are very material I'm very physical very tactile in this way in case folks are interested。

Yeah， thank you。Any other thoughts？For example， right。And then you have like another language。保损。なって。

So the question is， how many layers of abstraction can you have？来 that。trade up like。

As many as you want， yeah I think it's。Yeah， in terms of how many layers of abstraction you want。

As many as you want， barring is sort of computational。那 it's。Okay。

 we are approaching the end of class， and I don't want to hold y over so。Yeah。

 thanks for coming to lecture。 and really appreciate you' all being here。 I hope you all have。😊。

Learned about， felt good learning about these fun languages and feel your brains expand in some way。

 And yeah， I hope you all have an excellence and most restful Thanksgiving holiday。

 We'll be back on Tuesday with more of 164 Lang。 So yeah， thanks y'all。😊。



![](img/6ebca2159f47b9f2732989a54be75e7b_9.png)

![](img/6ebca2159f47b9f2732989a54be75e7b_10.png)
# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p01 01 - Overview -BV17jcReyETC_p1-

です。Good afternoon， everyone。Welcome to the fall 2017 offering of 15213， as well as 18213。

And there might be a few students here from 15， 513 as well， so as you know。

 this course has three different numbers。And there's slight differences between the graduate version 513 and the undergraduate versions 213。

 but for the most part we run this as one sort of monolithic course。

 one of the largest courses on campus in fact。And so。This is of course， my name is Randy Bryant。

 you might have seen my name on the book that you've bought。

 or I was one of the first people to teach this course many years ago。I taught。

 I'm not sure how many times， but a lot。But I still really enjoyed this course。

And I enjoy the students really find and get a lot over this course， it means a lot to me。

And to my coauor Dave O'Haeran， who hasn't been teaching this course for the last several years。

 but he's also taught him many times。Today our two co instructors as well， Phil Gibbons。

Is also going to be giving lectures just like I am。

And then Brian Raing is not only in charge of the graduate part of this course， but again。

 we all work together in many aspects of it。啊。So the first day。

I was preparing lectures for this course。About when you were born。好。

I typed in that number and I said， I have typed this number a lot of times， 15，213。

And that was lo and behold。 I got this idea， here's a tagline for the course。 We give CMU a zip。

I just looked up today 18213 doesn't exist as an area code and 15513 is somewhere in Kansas。

 so it doesn't really work。Quite as well there， but it works great for Pittsburgh。So today。

 it's an introductory lecture。One thing is to sort of do the big picture， what's this course about。

 why are you in it， what we hope you get from it？What it will give you for the future。

 that kind of stuff， what are some of the major course themes？And then another part。

 we're going to do a special discussion about academic integrity because that's been a major issue for this course and for other courses。

We try to address it right head on， as well as some topics about logistics and policies。

 so that's our agenda for today。So this course as you know。

 it's called introductionuction to computer systems which is a kind of brand and generic name。

 but the idea of this course is for the most part， many of you have sort of touched computers in this somewhat abstracted way you've written code maybe in Python or other languages where you're fairly far removed from what's really going on with the machine in terms of what bits are being set。

 what bytes are being stored， where is it being put。

 what packets are being set across networks and things。

 and so the purpose of this course is to kind of get you started on the road to understanding more about what's really inside that box and how it works。

And。There's a lot to be gained from that just on its own and one of the things we like about this course is even if this is the only systems course you've ever take your life。

 you'll walk out of this course with some very useful stuff that you can apply to your job to your further studies whatever your endeavors are because you'll understand more。

 you know what quirky features are happening when things aren right how can I kind of dig in and patch up some code to make things work that wouldn and other work and and just that kind of stuff and then the other part of this is for those of you who go on and take other courses。

 particularly in computer science and ECE in networking compilers， operating systems。

 distributed systems， computer graphics， embedded systems， computer architecture， all those topics。

 this course is designed to sort of be the。You're on trade point。

And all those courses over the years have evolved to very much build on the assumption that you've mastered the material in this course for them to get started。

In fact， the origins of this course was。To help students get ready through the operating systems。

Of course。410。So it's very important， they here this twofold。

 one is it's good right from the start and second is it will be real helpful for the future。And。

Part of the reason is in an ideal world we shouldn't have to know all of this stuff。

 things would just work the way they're supposed to and you'd write programs and you'd run them and it would just do what you want it to do and all that stuff that maybe you should see in a science fiction movie。

 but the reality is of course things never quite work the way they should。

 and so if you really want to fix things that are broken。

 if you want to make things I'm sure the things are secure。

 you want to add some features that aren't otherwise available。

 you have to understand more how things work。And you know， computer science and in fact。

 all engineering is based on a set of principled abstractions that we can， for example， in physics。

 you can understand Newlutonian mechanics and realize that's an abstraction。

And it works a lot and you can do a lot of stuff with it until you're going really fast。

near the speed of light and all of a sudden it doesn't work so well。

 so you know that principle is fairly profound across science and engineering that there's some layer of abstraction that works 90% of the time。

And it's very useful to think in terms of that abstraction， but the abstractions don't always hold。

 and that happens over and over again in computer science and computer engineering。

And so part of this is to sort of explore the boundaries between the usual abstractions you get as a programmer and what's going on more at the hardware and the system software level to be able to be effective。

So let's just give you some examples。And the saying I have， ints are not integers， you know。

 when you declare a very boring C， you called them int。And so for example。

 I learned in algebra that if you square a number， it should always be greater than or equal to zero。

Either a real number， a rational number， or integer。当。So let's test this hypothesis。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_1.png)

And。So I actually wrote this really simple program here。Called SQ。c。

And what it does is it has one function， can you see that， it's a little hard to see？嗯。

Try to make it easier to see。

![](img/2400c3a1a38b4e97ad5adb5687e1abae_3.png)

那本。That it just computes x star x and we can run this and you see it takes it。

 it reads values off the command line argument， so I can run it on a number like 40，000。

And it returns 16 followed by auto of zeros， which is what you'd expect。But what if I run this on？

50000。So it should be2，5 and a bunch of zeros。But no， it's minus。179。49，6，7，2，9，6。

 So that doesn't look like the square of any。Number with the five and a larger of zeros。

 right it's negative， it has no zeros in it。And something's funky。

This is an example of ints are not integers。The reason， of course， is that on this machine。

 this is a Linux machine。で？It uses a 32 bit word size， so all numbers have to be represented。

All the numbers that are int are represented in 32 beds。

And the square of 50000 is too big to fit in that representation。 So what happens is it overflows。

And that causes it to。Change the bit pattern very much。

So you can imagine this could get you into really big trouble if you were like controlling a rocket and you wanted to go at the square of 50。

000 and it was sending you somewhere negative。And in fact。

 there's been examples of exactly that happening with rockets going bunnkkers because it was getting some bad numeric values。

Due to overflow so this is an example of where the abstraction is not working now you might。

 if youre used the Python， you'd say， wait a minute， I've done stuff like this all the time。

And it works just fine and in fact you can。Do some really big numbers and it will halfway keep going because it uses a。

A way of representing numbers is that they just add as many bits as it means to represent that number。

So。For better or worse， Python sort of gives you this more abstract wire that seed does not。嗯。

About how numbers are represented that lets it handle very large numbers。 So again。

 understanding what languages can do， what is an important part of。

Of being more effective at systems。

![](img/2400c3a1a38b4e97ad5adb5687e1abae_5.png)

If I type floating point numbers， on the other hand， if I keep squaring a number。

 it will always be positive。But actually， that turns out to be mildly interesting too。

I Im trying to demo right here。So。Another property you're used to with numbers is the Associative property of arithmetic。

You can， for both addition and multiplication， you can move the parentheses around and your final value will be the same。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_7.png)

And let's see， I didn't write a program for this， but I can fire up。

A program that you will get to know very well in this course is called GB。

 it's called the Ganew debugger， so it's used to help it's a program that lets you examine。

 operate and execute other programs and see what's going on。

And it has built into it a little interpreter， so again， I can do my 40，000 trick。

And it will work and if I change it to 50。It will give you that funky result because it's also mapping the idea of in 32 bit integers。

So I can use this for a floatinging point as well。And again。

 multiply some really big numbers and it won't。Ill go negative on you。But if you go really big。啊。

Well that's interesting。I honestly don't know what happened。😀YeahYeah。It's not really negative。

 but it's a really little negative number。啊是。So anyways， you can see things。

I don't always what you'd expect。But what I really wanted to show about4ing point is。

I can take numbers like 10 to the 20th， which is a pretty big number。And subtract1 to the 20th。

And add some other number。And except for。3。14 being turned into 3。13 and a bunch of nines。

You see that I got what you'd expect， you take a big number you and it's negative that zero。

And then add zero to 3。14 and it's fine， but if I take， I move those parentheses around。

And I get zero。 And the reason for this is if I am。3。14 minus-10 to the 20th。

In think of scientific notation where you only keep some number of positions past the decimal point。

1 the 20s kind of dwarfs 3。14 and so that sum there on the right computed is just minus1 to the 20。

There真窗。And I add that to it。1 to the 20th million0。

 So you can lose floating point numbers can handle a much wider range。

 but the tradeoff they make is they don't have the precision。 And so you can lose significant things。

 And again， if。If you don't understand this and you're trying to do numeric computation。

 you can get yourself in trouble。So we'll spend a fair bit of time in this course learning about numeric representations。

 what their actual formats are in some of their properties because it turns out that's a certain cornerstone that you really need to understand in a lot of parts of computer science。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_9.png)

![](img/2400c3a1a38b4e97ad5adb5687e1abae_10.png)

They some years ago made this course a prere for the computer graphics course because they wanted the students coming in to understand floating point arithmetic。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_12.png)

So sometimes you see these numbers and they look completely random， you know， minus 1967。

 whatever that was， but there's actually a very predictable set of properties that determine what numbers pop up when that happens except for that one I just showed you that I really don't understand。

It's just that it doesn't always match your intuition about if you've had algebraa calculus as your background。

This isn't what you'd expect because it doesn't match it。

 it has to do with this sort of finiteness of the representation。But on the other hand。

 they do have certain principles that you can know and understand and those are important。

So that's one of the first themes and we'll spend a fair bit of time in this course just going over that both in lectures and in a lab。

Another big chunk of this course is about assembling language and machine level programming。

 so understanding the actual low level instructions that get executed when you run a program。

And it's a little bit。 There was a trend。Before this course started， that was getting away from。

Students ever learning assembly code basically， they say， look in this era。

There's no essentially no reason to write significant amounts of code directly in assembly or assembly languages。

 just to let you know is a sort of cleaned up textual version of the low level machine code that gets executed。

And so there're really a very direct correspondence between assembly code and machine code and Ill tend to。

Go back and forth between those two terms。But。The idea that we found we found is that no。

 you're not actually we're not training you to write code in this rather arcane notation。

 but we're training you to be able to look at code that's been generated by say a C compiler and understand what that compiler did to transform your C code into the machine code and what that implies when that code then runs on the machine either because it's running slowly or it's got some quirky bug or it's part of a。

嗯。security flaw that attackers are trying to exploit some of the weaknesses in your code and use it to gain access to the system。

 those are all the kind of places where the actual low level machine code is very important to understand。

啊。So we'll spend a fair amount of time covering that topic as well and looking at programs from sort of。

Both directions from high to low and go to high。Another part we'll look at is a lot of times when you write a program。

 you know that it uses a lot of memory but and a modern computer gives you this。

Abstraction that you can access huge amounts of memory in it。

But the reality is that amount of memory that's physically in your computer is limited。

 and it has some characteristics that there's actually a hierarchy of memories。

From some things that are within the processor chip to parts that are chips outside of it to even a disk drive are all layers in this memory hierarchy and。

The operating system and the hardware all work together to kind of make you think that you're accessing a lot of memory。

But what it gives you is very different performance characteristics。

 depending on what your memory access patternss are。

And it can be really somewhat bizarre until you understand how it works and what the underlying system does。

 And this attributes becoming more and more important over time that memory systems。啊。Are growingrow。

 you can easily get a computer with 32 or 64 gigabytes of memory。Of RAM。

 but the access speed of those is much slower than the processing rate of your actual processor。

 so you see more difference between the memory performance and the processor performance over time。

And there's also other features， especially in a language like C or C++ about how。

You reference memory that can lead to some really， really awful and nasty and painful bugs。

 So this is a very simple example of a structure of structure。

In C that has an integer array called A with two elements followed by a double D。

And this function that。Well， write some number to an arbitrary position in that array A。

And if this were in Java or another language， it would only let you use A of I。

 it would only allow you to reference either a of zero or a of1， of course。

But in C and other languages， there is no a bound checking。

 And so it will gladly let the reference A of 39， say， and you'll be effectively assigning。

 you'll be storing in memory someplace。A number that has absolutely nothing to do with what normally should be stored there。

So if you look at this function， what it should do， you realize is essentially nothing， right。

Set some value。The double to 3。14 and that's the value of returns， so it just should return 3。14。

And it sets some memory position， but there's no obvious way that setting would affect the program behavior。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_14.png)

Well， let's just give it a try。

![](img/2400c3a1a38b4e97ad5adb5687e1abae_16.png)

So I call that the program Str and I can give that value of I command linearch。

So you'll see if I give it either0 or one for the value of I。It returns just like you'd expect 3。14。

If I give it the value2。先。😊，Things start to look curious that it's not really 3。14 anymore。

 So that looks pretty weird to think about。

![](img/2400c3a1a38b4e97ad5adb5687e1abae_18.png)

That。哦。Okay，' pretty exciting would you be overriding the double？Yes， you got it。Good observation。

 so。We'll go into that， but you've got the idea thatve basically。

 I'vemacked a little piece of that double。And so it's no longer quite 3。14 it。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_20.png)

Then if I do that to。3。Then my 3。14 turns into two。And if I go to four。Then I crash the system。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_22.png)

啊。Because it detected that this is。Not a valid access。Which is good， actually。

 you'd rather able would detect it。SomeYou'll see other places。

 you'll have this experience you maybe already have that。You can modify。

 you know write to some bad pointer， it'll set something。 your program will go merrringly along。

 It might run for minutes， hours， days or weeks。And then eventually。

 it will come to a place where it has to reference that memory location。

 and it's screwed up and some awful bug occurs。 But can you figure out where that bug got injected No way。

 So that's one of the more painful classes of。A bugs to try and。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_24.png)

Yeahject down。But at least。With this course， you'll know why， even if you don't know where or how。

And the example I show here gave slightly different results on a different machine。当。So yes。

 the observation that was made is if you look at the way memory is organized for thisstruct。

I'm starting with the lowest addresses at the bottom and each of those rectangles represents four bys。

So the two ins of A are each four bytes there， so first a of zero and then a of1。

But then theres8 bites to make a double。 And the first eight of them are the low precision。

 low order bits of D。And so when I zapped them， I didn't totally fry the number。

 I just kind of knocked some of the lower decimal points。

And then the upper part of it is the sort of high level bits， the more higher precision bits of D。

 and so when I whacked that， I really changed the value substantially。And then in this case。

 when I hit four， it was hitting some kind of critical state that could detect。

That there is some corruption of memory that occurred here and it gave a fall。

In other times on different compilers， this can run where it will happily let you do some of those。

 but not all。So that's an example again of if you understand more the sort of underlying how memory is weighed out。

 how data structures is weighed out， what can occur then these things。Are at least understandable。

 even if they're annoying embarrassing。And that's sort of a reality， if you write in C or C++。

 and so a lot of people choose not to。呃。By writing in another language， which is fine。

 I have nothing against other languages。 but the reality， of course。

 is a lot of this code in the world is written in C or C++。 and that's just one of its features。

And there's ways you can try to avoid some of those problems。

Another part we'll look at in this course is sort of program performance。

 and we look at that at many different levels。And so。I actually， of course。

 like 122 or other courses， you've learned sort of big O notation and the idea of asymptotic complexity。

One program is quadratic， another is N log N， N log n is a lot better than quadratic， so do that。

 use Quick sort， don't use bubble sort。By嗯。There's more to it than that， you know。

 a lot of times if you're running a video encoder and you want to have a frame rate of 30 frames per second。

And you can only get 15 frames per second。 Then it's not an asymptotic complexity problem。 It's just。

 can I make my code go twice as fast？And it will make a big difference to you。

 so there's a lot of times in the engineering world where you're also worried about constant factors too。

 and there's a lot of swack in the system usually that you can overcome if you understand enough about program execution to be able to optimize performance。

So we'll spend some time on that too， that's a useful outcome。

So one thing that sort of combines this idea of。大装。The memory system and performance。

Is this these two。上品。That both perform absolutely the exact same thing。

 their purpose is to copy the elements of a source array。

To destination array where both of those arrays are。呃。Of size 2048 rows and 2048 columns。

And so you see that the two programs are absolutely the same。

Except for the order of do you do the copying row wise or column blocks。Right， and the one in the。

The left in the inner loop， you see it's J， which is the second index。

 so logically you're going through the row kind of like this， each row。

 one row at a time top of the whole row。And the other one， I' flipped it around。

 so the inner loop is I， so I'm sort of going through it column wise。

 I'm stepping through it vertically。But note that the outcome is the same。Same thing it's just。

Do I do it real wise or calm？And if I fire up a machine and run this， though。

 you'll see that it makes I at  or 20 times difference in performance。对。The R ice is much。

 much faster than cony。And this is an example of this memory hierarchy， as mentioned earlier death。

Basically， the row wise and we'll see exactly why is more tuned to the way the memory hierarchy sort of anticipates how you're going to access memory patterns and the column wise messes it up。

So if you。In fact， if you look at the cover of your book， you'll see this picture。

And it's an explanation of why Roweis is better than Commonwe。So the upper one。

 what this shows is for various different access patterns， how many megabytes per second。

We can access the memory app and this is measured just by running programs like you saw here and seeing how fast they go。

And you'll see that the first one， the row wise is up in a pretty good spot as far as through aput of over。

8，000 megabytes per second。And the one the coffee JI is at the worst possible place。

 it's sort of down there in below1 thousand。Omegabytes per second。So again， we'll understand this。

 we call this the memory Mountain for obvious ideas。

 a reason it was actually this way of visualizing memory system performance was developed by it。

A fellow who was a graduate student here at the time， he was from Switzerland。

 so I guess this is his way he liked to think about this。啊。So again。

 this is one of these topics that we cover in this course that really can make a big difference in the programs that you write。

And then another part of this course we'll talk about is。

Beyond sort of writing little programs that square numbers or。Access memory in various ways。

 There's a lot of interesting other parts of the computer system， in particular。

 the whole business of hook computers together and having them talk to each other over networks has many。

 many layersors of complexity to it and various standards and protocols and hardware and software and so forth that we won't get deeply into。

 you have to take a networking or distributed system， of course， you really do that。

 But when we give you a sort of starting point in that direction so that you'll better appreciate what's happening with your computer when you're using a wireless access or when you're getting web pages through a web browser。

So one thing about this course， that's different from the way most systems courses are taught。

 including the more advanced ones that you'll take after this。

 is most systems courses are kind of designed or built around what how it takes to build a system。

 so if you're an operating systems course at CMU at least you'll spend a lot of time writing。

The core code of an operating system in the compiler course， you write a compiler。

 the computer architecture course， you design microprocessors。

 so that's all really interesting endeavorron。 It's really interesting to do。

But we don't think it's the right way to start。When are your first warning systems。

 the way we like to start our systems is what we call them。A programmer centric。

So how you as a programmer in this course， we mean a C programmer are how you write code that exercises。

 makes use and interacts with different parts of the system。

 and how you can be more effective and better at。So it gives us an angle on it that lets you now after this。

 when you jump into an operating system course。And they teach you how to write a signal handler。

You from this course have learned what a signal handboard is and what use and value has in sort of applications programs。

 so we're mostly looking at application code here。But it will give you a launching point so that when you go into。

More sort of advanced systems programming， system design。

 you'll understand what it is you're trying to achieve。And that works out really well。

 this user perspective or programmers' perspective works out really well for an introduction and also for satisfying。

This。Goal we have a you should learn something useful in this course。

 even if you never take another systems course。Because the chance that you're actually going to go off to a company that designs cache memories。

It's pretty small。There's only a couple of them。And。So you know in the whole world。

 the number of people who design microprocessors who design cache memories who implement operating systems is only a small fraction of the total number of people who use this stuff at various different levels of sophistication。

And so。We're instead preparing you more for that broader task。A life of programming in various sort。

And a part of what we do is a lot of the material that we cover is stuff that historically people just kind of learned on the job or learned from their friends or pokeed around or heard from somebody else or read it on the internet or something before there was an internet。

嗯。But a lot of this what we've tried to do is conify it and put it in one place so that even if you don't have this sort of。

Driving urge to dig up everything and learn it on your own， you can learn it through us。

So as I mentioned， there's a lot of courses if you look at that require this course as a prerequisite and I know a lot of people are in this course mostly because they want to do other stuff and that's fine。

 but over time this course started as a CS course， but it's been adopted into ECE and it's a core course in both programs as well as people from a number of other programs on campus。

 both undergraduate and graduate who take this course as a launching point for many other courses and so one。

Property of all our advanced courses at CMU is they expect you to know this material。

 and that's part of the reason we have it。So at this point。

 I want to turn over the microphone to Brian who wants to talk something about how he uses the teaching of this course as a research endeavor as well。

That's more applaus than when I teach it over the summer。

So I just need to give a brief two minute quick spiel， which is that。

Every semester we basically do a little bit of educational research。

 so not only are we teaching you all about computer systems， we're trying to understand better how。

 well to teach you computer systems。So this is going to entail just two particular things， one。

 we are continuing to revise and change up the recitations， two， as Randy is not in， mentioned。

 there will also be some sort of in class quiz。Now today。嗯。And they're not even really graded。

But these things are both two things that we're trying to do。

 we're trying to update we're going to just going to measure at the end of the semester basically to see how old you learned。

 Did you learn better than the students last fall， Did it actually help you learn。

 Did it help you use your time better， All these different kinds of questions。

 What do you need to do not。I mean， you're just in the course。 you're already learning in the course。

 you don't have to do anything particular to participate If for some reason you don't want your data included。

 then you can email myself or you can email Chad per shock who's at Everly Center and say don't include my data Now all your data is going to be anonymized no one's going to look at your ID。

 no one's going to look at your pass grade specifically and we're just going look at this and see some hash code that says。

 you know， some long sequence of letters and numbers scored this well in the course and this will each of the assignments and we'll look at that and we're not even going look at it until January。

So。😊，However you did on it， it doesn't matter， it's not going to impact your actual parade that Phil and Randy are going to assign you。

 we're just going to be doing the measurements and look at it retroactively and say，Did it help。

 did you learn better or not？そすよ。You don't get any compensation for doing this。😔，ああ。Sorry。

' deception。Yeah there's no actual deception I'm telling you honestly exactly what we're doing。

 we're trying these things we want to see that you actually learn so forth better if you have further questions。

 I'm always happy to take emails I'm happy to meet with you and discuss these things you know this is one of my passions of not only do I care about things like you know actual computer systems but I care about making sure that you're learning the material and that we're doing that the best and most efficient way possible so that's it the text is fully in the syllabus you're also welcome to read it there and otherwise it's back torany。

So if that seems a little weird to you that we had to say no。

It's because technically you are human subjects in a expert research experiment。

And as human subjects， you have to be apprised of what's going on。And this research， though。

 is very much oriented。 It's educational research。 So how to make。Of course。

 is the CMU and elsewhere more effective？So now I want to jump into one of the less pleasant parts of this course。

And that's the issue of academic integrity。 So academic integrity is sort of a broad term。

That counts various forms of cheating and plagiarism。

And I know you've heard a lot about this in other courses from other places。

But it says especially a problem in computer science。

 there's many tools and techniques that make it very easy and very tempting to acquire information in ways that you're not supposed to。

And it's been a problem for this course and others that we really take very seriously and part of it is。

We as instructors feel this special obligation in this course that if you are going from this course into say Operaing systems course。

We wanted to make sure that you've really mastered the material in a way that those people expect you to have mastered it and if you've done it by illgo means。

 chances are you haven't growing around the material， and that's a problem。

So it's not just that I'm a mean person。Vengngeful and things， it's like to us， all of us。

 we feel like this is our one of our real obligations as instructors。And also。

 I should say one of the least pleasant parts of the job that I have。So in general， then。

 and you'll see in the syllabus a fairly in depth discussion of what's allowed and what's not。

 and I really advise you to look very carefully at that。But in general， all the assignments you do。

 the labs in this course use eight of them are done on your own and we need really on your own。

 you can make use of information that's in the textbook on the class web pages。

You can talk to the TAs or the instructors， but you really shouldn't be collaborating with each other in any significant way in getting your assignments done。

Also， the reality is there's a lot of stuff on the web that makes it possible to bypass some of what our goals for this course are is for learning this textbook gets used at 320 schools around the world。

And some of the labs were developed and are made available。

 although we've tended to tweak the labs that you see here。

 they're not quite the same as the textbook ones。But as a result。

 there's a lot of little hidden places on the web that have material that might be relevant to some of your assignments。

And。So it can be easy tempting and sometimes feel almost necessary to make use of that information。

 and we really aim to make that not happen。So in general。

 acquiring information from others from the web in ways that isn'tapp is not about and the other part of it is it's the other side of it is we also don't want you supply information to students in this course。

Or in future versions of this course and we。Undue and obligation now and forever。

To not be disclosing information relevant to the labs in this course for other students。

And I can say this， you should realize that if you look at the academic integrity policies of the university。

 one of the things they say queries is no statute of limitations meaning。Even if you。

Get through this course。And you're not caught doing something。And you get a decent grade。

 you're not really home free。If we detect something in the past。That was unauthorized。

 we can go back。And through a process of change your grade and possibly revoke your degree。

So not sound too scary， but it's true。And we've done。好。

There's a special problem with GitHub that a lot of students like to use Git。

 which is a great way to do version control， but GitHub。

 there's ways that your account if you might have it as a private currently。

 but it will become public after some period of time and so you can inadvertently leave。

Stuff lying around that really is effectively disclosing information to future students。

So what is not cheating then and I use the term cheating plagiarism interchange ofably。

It's okay to work with other students if they're having trouble getting their code to compile the debugger to work。

 sort of system level stuff， that's fine。Very， very high level design issues。

 and that's one where people often misinterpret what we mean by high level design。 so if you're。

Here's an example of a case I had several years ago。We didn't I didn't cheat， I was reading my code。

And my friend was typing it in。So I was in。Or we went on the whiteboard and worked it all out in pseudo code。

And。But then we all did the coding aerosol that pseudo code is code。And even if it's pseudo。

 the point is if it's at that level of detail where you have to be writing it down to explain it to somebody。

 that's not a high level anymore high level means just in general， oh， I found it best to。You know。

 access and array row wise rather than columnize。In general。

 there's a lot of code available through the book webage， the course webp pages and things。

 and of course you can make use of that。So again， as I mentioned。

 the syllabus goes into a fair amount of detail on that。So what happens。

 so I should mention that we're pretty good at tracking this stuff down。

 I'm probably better or as good at using a web search as you are。啊。And so we find these things。

 if you found a copy of some code on GitHub from some student in Iowa。

We've probably already found that code and mentioned and have copies of it。

 and we also have copies of every single submission made in this course over its entire history。

And we run these programs are called cheat checkers that we' just take we can。

Literally make this big pot of all the assignments that ever been created and then throw in your code and it does this analysis and comparison that doesn't get fooled by things like changing comments or variable names or indentation or things like that。

 and it comes back with matches and some of the matches or faults or just sort of happenstance。

 but others will look very fishy and suspicious to us， and that's when we start looking more closely。

So。It's actually pretty hard to trick these programs。And once that happens。

 we begin a process where we， several of us will look more closely at the code。

And if it's suspicious， then we'll call you in for a meeting。

 which can be a very uncomfortable meeting。And just as a consequence。

 our minimum penalty is always a。Minus100% for that assignment， so it's always worse。

Then if you hadn't turned in anything at all。But that's actually when we're。When things， you know。

 when there's some。Extenuating circumstance or you're honest about it there's other cases and not uncommon。

 in fact， the default case is that we give you a failing rate the assignment that goes on your permanent record。

And all of these are marked as an AIV by the university and the rule at the university is one AIV。

 okay， I hope you learned you lesson， two AIVs， you get counted in front of a board consisting of faculty and other students。

where you have to explain it and they can assess a penalty。

 which can be the maximum penalty we as instructors can impose is to fail a course。

But they can impose expulsion， and they do。I've been in several of the hearings for somebody who is on their second instance and they were。

Expell from me just。So just as for example， two years ago， we had 20 students。

Who held the course due that， that's about 5% of the students in the course。

One at least one of whom subsequently expelled from the university。LastA couple years ago。

 we came across some code that showed up that a lot of people's implementation in one of the labs。

Track down where it come from。And then went back through several years of。

Submissions and found this same source in a lot of。People's assignments。

 and so we went back and through a process that involved multiple professors and the university Dean of Student affairffairs。

We actually penalized， regraded and assigned new grades to 11 different students who had already taken the course on some who had already finished at CMU。

So we really do take that no statute of limitations seriously too。

And one thing I'll just say personally is I don't like doing this and I don't even like talking about it。

😔，I feel like there's a tremendous waste of my time to be looking at somebody's assignment and trying to figure out whether it's a copy of this other one that's on GitHub。

😔，And is spending time talking to the students and hearing their， you know。

 they're kind of dodging the issue until they finallys up confess them。

and state what they really did and going through this whole process， it's very painful。

 it's emotionally actually very difficult for me， and it's way more difficult for the students。

And I know all of you here have no intention of cheating in the course。

 but what happens is as that deadline draws near and you're just not getting the assignment done and you know there's a copy line out there。

 it's just so tempting and you kind of cross the line and you know it's bad to do but。

rightAnd so it happens and it's。But the consequences are really， really terrible。Question。

 have you ever had any false positives with whatever like？

s or whateverMaster generates a lot of this question is good one。

 what about false positive there's a lot of false positives？

And there's been a few times when we'll have that meeting with the student and there is some explanation and nothing happened。

But you have to realize that we as instructors don't have to。

Have your confession to be able to apply consequences。 We can say， I believe you cheated。

 I'm going to give you this penalty。 You have the right to appeal it。

 And I think it's a good thing to appeal if it really was unjust。 and we try not to do this。 But。

 you know， we don't， we're not the judge or the jury。 we don't have to。

Have proof beyond reasonable doubt that this occurred， we can say。

 I believe that this is what I believe。You can appeal it。

 so I've never had that happen to me in that case， but I've had some number of students where they come in and there's some explanation and that's okay。

So let's just go through a few examples here。好。If you start using searches for 213 bombwab。

Which will come up actually with some interesting YouTube videos。Yeah。I know。

And I've looked at those videos and I've watched。So。

We kind of know what's there but you shouldn't be doing that right that's clearly a case where you're trying to gain information to do an assignment。

 not the technical information， but something to help you do a solution。In general， of course。

 supplying a code， that's a fairly evident thing， giving a file， that's pretty evident。

 but as I mentioned also writing pseudo code on a whiteboard is also sharing of information。嗯。

On the other hand， if you need reference material about some library functions， that's fine。

Or a particular program that's fine TAs， we have a lot of office hours。

 it's always fine to talk with them。I'm going to in the interest of time， skip this over。

 but I recommend you look at some of these scenarios that I are very typical of what I've experienced。

 that some student， as I said， the deadline is approaching， you have to get this in。It's not working。

 you find on GitHub， a student from some of the places， written code that more or less works。

 make a copy of it。Try and fix it up some。Submit it， fine。But then we。

 we find that we can and do find those cases and then have these meetings that I described to you。啊。

Heres some a little bit more scenarios then。So Alice is working on a lab， it's not working。啊。

And Bob is sitting next to her he's done。And Bob is。next to Charlie and Charlie is not doing so well。

Charlie gets up for a break， and Bob makes a print out of his own code in Ruvan Charlie's chair。

 Who is cheated。T weer Bob。それ of Bob。I don't know what he's doing， you know。

 it probably is what his intention there was it just because that was the nearest thing to put it on or not。

 but it's definitely sketchy， Charlie obviously is oblivious to this at this point。

But then Charlie finds a copy， looks it over and copies one function and fixes it up。 So that one。加入。

啊。Bob sits down with Alice and they go over her code together， what's the problem。Bob or Charlie。

 both， right， they're working together。Charlie looks at the screen that Bob left behind and sees what's going on and who cheated there。

Well clearlyy Charlie did， Bob Pricery shouldn't have left his screen unattended。

 but you there's some level of expectation you can have in this world。

It's called expectation of privacy that you don't expect you have to。

Lock everything you do and put passwords on it， but in general。

 that was not good for Bob to just leave a screen with。Alice is having trouble with GDP。

 how to set a break point in it， he shows her。That's okay， that's fine。Joy goes to TA for help。

 that's fine。So one thing we're doing that just started last spring in this course。

Because a lot of students were using GitHub as their code repository and in fact。

 I'm a fan of GitHub myself， but the best thing about GitHub is the Git， not the hub。

 So Git is a general purpose version control program that。

As long as you can find a server that supports Git， you can use it。

 you don't have to use the commercial one called GitHub。And so ECE has a version control。

 runs a get server， and we are really going to strongly push you to use that。Instead of Gitthub。

And there's a sort of a carrot and a stick involved here。

 so one is it's really a good habit to use version control as you make changes to programs。

 you want to be able to recover if you made some change and find out it was really a bad idea。

 you want to get back to some previous state， you can do that， you can create different branches。

You don't have to worry about your computer crashing and losing files and things like that。

You can document your changes， all those are properties of gett or any version server。

 but get is especially good。Now， the reason we want you to use this is this can actually also be a record of your effort in this lab that can be very important if we start asking questions。

So if we at this happened， I haven't done this yet， but both last spring and last summer。

 there are multiple instances where students got called in because we thought some of their code looked a little fishy。

And some of the students actually had a pretty significant record of the work they'd done。

Through get and could show that this had consistently been something that you're working on and therefore they were absolved of any wrongdoing。

 but other students all of a sudden， oh no I didn't save anything or yeah I saved a bunch of stuff but then all of a sudden。

It changed in this massive way。That looked like maybe some new code was imported into it。

 So you can think of get being。Your record that we can look at。

 we can look at the get logs of your code on this ECE server for this course。As a record of it。

 so we really want you to make use of it both for your own benefit as a programmer。

 but also as as a sort of record that can determine。

That this is really your own code that you've been working on。So a few logistics， three instructors。

For the undergraduate， we have lectures and recitations。

One thing that we're going to introduce that we started last。TheSum is Canvas。

 which is the new Blackboard。In which I'm generally not very familiar， anybody's Blackboard either。嗯。

It has this facility where we can do little in class quizzes and these aren't like quizzes like write down on paper and pass。

A few multiple choice questions and these actually are very useful for the instructors as a way to kind of gather a sense of where the class is in their understanding and dynamically in real time modify what're as a way to do that if you ever been in a class with the clickers。

 have you done that。I've never used him，That it's the same general idea， it's just you'll use。

 so you should plan on bringing off a laptop or a， I guess you can use your smartphone to do this too。

就啊。Now， we're not really grading them， but。In the end。On the grading。

 if there's sort of a borderline case on a student where they're right at some the cutoff or one letter grade versus another。

If we see sort of an active participation as。I'm sorry。

 I won't be able to track who's in the class on a regular basis。You know。

 the record we have for your participation in these will be an indication of how actively involved you were in the class and that could。

Affect your grade so there's not a like numeric value。 If you miss a class， don't worry about it。

 we have them on we， we have them on video， there's a lot of material on the web。

 we're not taking attendance in any formal way， but your participation could be beneficial to your grade。

Besides the fact you learned the material better of course too。Okay， so the book。

Get the third edition， don't get anything else， don't get the international edition。

 they really screwed it up。The Chinese version is okay。We know the translator really well。嗯。But。呃。

That's the book and then we also strongly recommend you get this the C book written by Kinean and Ritchie。

 Richitchie was one of the originators of the C language at Bell Labs。

 both of were at Bell Labs one time。This book is really old。

And really a little bit out of date because he has evolved over time。

 but it's still the best book because it's not only the language itself。

 but it gives you some really。Nice little programming examples so to show style and how to think about programs and things that is better than any of the other books we've seen。

This course is going to have eight labs if you know anyone who's taken it before they've had seven labs。

 and I'll tell you about that。And the labs are really the main。

T you'll do for this course and the main way you'll learn in this course。

And you've probably heard that from your friends already。

There's two exams they're both done using an online exam system。

 so we're not scheduled in a room with and no paper test at all。So there's a lot of resources。

 the class web pages has a lot of stuff on it。We use piazza as a way of。Having。

Questions from the students and also making a lot of announcements will be there too。

 so that's the way you should definitely be on Piazce and following。By default。

 any post you make will be private。To the instructors and we recommend you keep it that way if there's some question that recurs and seems like it's worthwhile for the whole class to know。

 then we might turn your private post into a public one in an appropriate way of course。

Just as a way to present that information bill class， but in general。

 it's more of a private way that you can reach either us or any of the 20 teaching assistants。Don't。

 on the other hand。Post code there not because we don't like code。

 but it's just not the right way to do it we have autoWb which is the way we submit assignments so if you ever need help with code what you should do is submit it to autoWb。

And then tell us about it， and then we can go to AutoA and get hold of your code and look at it instead of us dealing with big files。

 yes。Say submit to。The question was。What wouldn't submitting to autoLb count is a submission for all of our assignments。

 you're allowed to submit as many times as you like， there's no penalties whatsoever。

For everyone one ofbaron。So email， we don't have a class email list。

But you can contact any of the instructors or the individual teaching assistant。

We have office hours every day of the week except for Saturday。

From 530 to 730 in the Wan Hall clusters and that's， but they're not going to start until next week。

There's walk in tutoring that。Exists and we'll put information that online once we have it。

And you can always schedule office hours， all three of us have regular office hours or you can schedule time。

There's fairly extensive information in the syllabus about a procedure if you feel like you've been graded unjustly in either an exam or a。

Assignment， there's a process for doing that that has a time limit of typically a week or so。

 so we definitely understand thatre we make mistakes in grading and we're very willing to hear。

Request for grade changes。 But don't expect at the end of the term to come back with， oh。

 on the lab 1 and lab 3 and the midterm， I was graded wrong。 It's too late by that point。

 So look at these syllus on that。Question in terms of how the assignments work。

 is it similar to 122 where there's some aspect of it that's like an auto grader you can see on autoL or is it all just handed in blankly so the question was。

 is this like 122 we actually taught 1 in 22 how to do auto ratingd？I'm a big fan of autograding。

 I used to say I would rather spend three hours writing auto graders than one hour grading paper to sell we autograde like crazy。

 so in fact， for everything you do， you will know almost your entire score auto graded and then there's some small part that we do manually like style points and some of that。

 but we like the autograding kings of the world。So， in general。

This is actually a personal belief of mine of all of us。

You benefit a lot more from the quick feedback you get that you have something wrong and have the chance to fix it rather than submitting something that's buggy and then two weeks later you're told。

 oh， there's a bug in your code。Too bad so I think there's much more learning value of giving that quick feedback。

 so it's not just that we're lazy so you can just you can submit and submit them。Yes question。进不去。

翻0做。有。Yeah。😊，Yep， early and often， that's a great thing about computers。

So we have some special machines that are reserved for this course called the Shark Ma。

Most of the work you do in this course you can do on。

Essentially any Linuxix machine and even some non Linuxix machines。

But the grading autoWb is actually run on a set of Win servers maintained by computing facilities。

 but we have these very specific machines， the shark machines that where we kind of make sure the software is configured and designed to run properly on that。

 so when in doubt use those machines for doing your work。Question。I do you have some question。

Just for reference so let's say that we're working。あさ。え画。So that 70%。I没什么。

Submit one to make sure we at least get it。And start working on the other。We have that done。

 we submitted yet。Turs out correct。Let we resubmit the one。This was an interesting question。

And I'll give you a short answer， which is make sure whatever you submitted last is the thing you want grade because that's the only thing we actually grade okay。

I this is a good question。嗯。So。Just a few other policy things we do have grace days as a way for you to sort of deal with your schedule。

 there's deadlines for every assignment over the course of the term。

 you're allowed to accumulate a total of five。Late days， we call those grace days。

 some assignments allow up to two， some allow none， some allow one。

 it's all in the schedule and that's what we want you to use if you're pressed because you have multiple classes you're going off on a job interview。

You have to go home for the weekend for your grandmother's birthday， any of that stuff。

I you know that's the purpose grace days so that we're not having to deal in a class of this size with every special case of can you give me an extension through this or that？

Well don well， if you don't， if once you've used up your grace days and those are assigned automatically。

 you have no control over you which assignments you're using grace days are not on as soon as they're late you start eating into those。

We give also often up to three days late total for assignments where there's sort of just an increasing weight penalty to it。

And so we expect that we'll take care of almost all the cases people might not be able to get things in time if there's something really serious that goes on in your life and this happens in one form or another。

 those are generally significantly。Not just for this course， but your whole。

Participation in all your courses， and so that's the time when you need to go talk to your course advisor。

And the adviser can get in contact with us and basically work out a plan for how to get back in schedule。

 One of the things that's difficult about this course or pretty much any courses。 we get this。

 There's a lot of momentum rolling in this。 And once you start falling behind。

It's really hard to then get caught up again， you get mo down and you get further behind in things。

My main advice is。A， don't use the grace days till you really need them。

 try and save them up toward the last few assignments in the course。

 which are the ones that are the most significant。And also。

 you just never know what might come along that will prevent you from getting things done on time。

 so try to， you know， be prompt， keep on top of things throughout the court。Generally。

 it's fine to have laptops here， but we don't want you other things and we want you doing productive work in that。

 not Facebook。咁。The course grade is half exam and half labs。The labs have different point values。

 you can see on the assignments page， the point distribution for the different assignment。

We tend to grade just down the point old。Standard grading scale with no。We don't curb the course。

 We often will have quite a few A's and quite a few Bs in this course。

 and that's fine if we feel you've。Shown mastery in the material。

 we have no problem giving you a good grade。As I mentioned。

We sometimes will bump people in a positive direction if they're right on the border and there's some circumstance that seems to argue in favor of。

One thing I want to mention。啊， it a。There's a new lab that's available today。

 you can get it from the course page if you should all have autola accounts already if you were registered for this course by noon yesterday。

But in general， there's a new lab out called Web Ze， which is a little exercise in C programming。

 which if you've done any C programming， if you've taken 122。

Should be a very straightforward exercise and we hope that's the case。

 but what we found is some number of students coming into the course they're either weak in it they're a little rusty。

 some reason。Haven't done much seed programming， and they find they get。Stuck。

 and the problem is that the problem occurs not in the first few webs。 but later on in the course。

 about a month in when you have to start writing more significant programs。 So La 0 is our。

 our new attempt to sort of help give you some assessment。

 It only counts two points total in your grade。But it also should only take you one hour or so to do。

But you can get onto that right away， it's due a week from theory state。Otherwise。

 the labs are ones we've had in this course for some time。

 although we keep tweaking and improving them in various different ways。

I'm just moving on a little bit here。So the labs are really a big part of this course。

 and I'm sure if you've talked to people who've taken the course before。

 that's what they remember the most。It's a great way to learn material is to actually get your hands on and do things。

We use a system called the project Zone for passing out the handouts， the write ups for the labs。And。

So a way that actually kind of reveals the handout slowly over time as you answer questions on what you've already seen。

 and only when you get to the very end you get this little pass key。

 which is a set of digits and letters that then you include as part of your submission and that's what lets you submit things to AutoA。

And the reason we do this is often we get questions in piazza where our answer is， read the handout。

And so this is a way to encourage you more strongly to read the handout carefully before you jump into assignment。

And as I mentioned， we'll have a Gi server。The last thing I want to talk about is there'll be a boot camp this Monday。

 which I know is waiver Day。At 7 pm in Raid audititorium， the TAs will run。

On gettingting familiar with Linux and Git。So a lot of you， this isn't mandatory at all。

 but if you're sort of a little shaky on using Linux using command line tools， using G。

 they'll cover a lot of that and so I recommend you you put that on your schedule。Otherwise。

 I think we're good to go， so we're forward to working with you。



![](img/2400c3a1a38b4e97ad5adb5687e1abae_26.png)
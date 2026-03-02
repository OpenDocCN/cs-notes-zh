# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P1：-02-Lecture 1_ Safety in Systems Programming - GPT中英字幕课程资源 - BV1D142147he

![](img/7c1569cae66c8d0c7328f708d070553c_0.png)

Cool， awesome。So just before we start some quick zoom things。

 please enable your your video if you have a webcam， if you don't， that's fine， don't worry about it。

Um， but it will just help for us to feel a little more like an interactive community and a little less like watching a YouTube video。

Try to mute yourself if you're not talking just so that there's not background noise and I think there's like a raised your hand feature on this like I've seen it in other classes。

 but this is my first time really using Zoom so I don't really know what I'm doing。

 but if you can find like some button to raise your hand or to indicate that you have a question that'll help us out。

 but I'll also try to stop pretty frequently throughout the lecture to make sure that we answer any questions。

Just hit no。Yeah。Oh， maybe it's because we're， we're like hosts of the meeting so we can't raise our own hand。

 Oh， that's neat。 Okay， now I can see things popping up。 This is good。 Arman and I were like。

Up late trying to figure this out。 and we were like why is there nose raised hand thing and I'm like。

 I can't see anybody and like， yeah， we we'll make it work so cool。 thanks for your oh yeah。

 there's more things popping up。S以。Okay， so this is the chat。 I feel like an 80 year old。 there's。

 I think in the desktop client。 So I'm sharing my screen right now。

 I don't know if you can see other people's videos。

 but there's some like side by side mode that you can enable to see other people at the same time。😊。

If that's something that you like， go ahead and enable that。

And I think most of all and this is a tip for me as well。

 just like let's relax and have fun with this if you need to go take a poop or like you want to eat during class that's totally fine。

 we really want this to be an enjoyable experience for everyone。

None of us really asked for this online class， but it's going to happen。

 so let's make it work the best that we can and let's have some fun with it。Yeah。

 so thank you for your patience in working all of this out。So some quick introductions。Armen。

 you want to go ahead？Yeah I'm Ryan， similar to Arman also a coterm also focused on systems and security。

 I really like growing things so just before I the quarantine happened。

 this is my avocado farm and there's a little guy that's sprouting now it's the only one but I like growing a lot of avocados and different things。

I'm pretty into music， I used to record a lot of music， but I have not done that in a while。

 but I am really to funk jazz and fusion。I also love doing pottery， rip coronavirus。

 I wish I could still do it， but everything is closed。I am actually a complete imposster。

 so you all are taking this class thinking I know things but I don't so Arman is our resident rest expert I am going be learning alongside all of you all as this is also new to me but I do know a lot about systems I've taught 110 in the past and I've seen a lot of problems that come up and I've worked in a lot of different contexts and so I'll be bringing some of the systems Z background to this class。

In terms of structure， the two of us are kind of going to tag team on lectures。

 so you'll be seeing a mix of us throughout the quarter。A huge shout out to Will Christ。

 he has generously met up with us several times in planning this class and given us a lot of advice and a lot of review。

 and we'll be borrowing a lot of his materials as well throughout the course。Yes。Yeah。

 so if you ever see him walking around， a huge， huge thank you to him。So who are you。

 who are you all taking this class there are about 33 people registered I don't know if that has changed since yesterday and we also have a few auditors so I'm really excited about the turnout because for a while we had like two people enrolled in Armend and I were like should we teach this but there's been a lot of interest lately and we're really happy to have a strong community here？



![](img/7c1569cae66c8d0c7328f708d070553c_2.png)

Most of you are in the Pacific Times zone， but we do have people from all over the world and。

I think one of the coolest things about this online quarter is that we are going to get people from many different environments tuning it at the same time。

Why are you taking the class I went through the survey results and there were a few kind of themes that were pretty common。

 almost everyone said that they were interested in rust specifically either because it's a new language like maybe employable in the future or they just want to learn about it。

The other part of this class is designed to support what you're learning in 110 and enrich your experience。

 and a lot of people have focused on that as well。I hate errors。 me too。

 And I think in  one10 you will。Experience a lot of the motivation for rust。

 you'll probably see why some of this was designed the way it is。

 and you'll come to experience a lot of errors。 this class is about like handling those errors and trying to build robust systems。

A lot of people said that they were interested in maintaining secure code and rust is very security oriented。

Some people commented that they're interested in the projects， so we have two projects。

 I'll talk about those later。Zoom is blocking the slide for me。

I genuinely thought the content of 107 was really interesting。Oh yeah， systems is difficult for me。

 but despite this， I thought 1 of7 was interesting props to whoever wrote this。

I don't usually try to。Pursue things that that don't work out very well for me。 so huge props to you。

 I think one of7s also raises some really interesting topics and hopefully we'll be able to touch on those in this class。

嗯。Have you heard about anything about rest before， the vast majority of you said no。

 most people don't know about it or if they have heard of it， they don't have any experience with it。

 So if that's you， you're in very good company and that's really our expectation。

There were two people who mentioned that they had taken CS242 before。

 which is a programming languages class， and if you fall into that category， just a quick note。

A lot most of the first half of this class is probably going to be repeat for you。

 you'll probably have seen all of the introductory rust material and in fact you're probably better at it than I am in the second half of this class you may get a lot out of our discussion of threading and networking which ties into the 1-10 material that you may be learning this quarter or who may have learned in the past。

But most of the first half will be review。And in going through the survey responses。

It was I was not expect most of the time like in section， I always ask that question。

 tell me something about you that has nothing to do with CS。 and a lot of people are like。

 I'm from Illinois and I'm like。Okay， tell me something a little more。

 but I got some really great responses this time and I think we have a really awesome community with a lot of different backgrounds。

 So if you are not already on Slack， let us know。 and if you haven't already said hi in the social channel。

 go ahead and post a quick intro to yourself because I think we've got a lot of neat people and I would love for you to virtually meet each other。

😊。

![](img/7c1569cae66c8d0c7328f708d070553c_4.png)

So that's it about like。呃。Us and people in this class。

 let's talk about why this class exists and why we wanted to teach it。



![](img/7c1569cae66c8d0c7328f708d070553c_6.png)

And in order to do this properly， there are two angles we need to take a lot of systems code is written in C and C++。

 and so naturally we have to ask why not continue using C and C++， which we've been using for 30。

 40 years。And then the flip side is， well， there's a lot of much newer languages。

 like Java and Python and some new languages like go。

 why don't we try writing systems code in these languages instead？

These languages also like don't have memory leaks or。Or some of the issues that you find in velgrind。

 they seem a lot easier to use， I don't have to mallic or free。 Why don't we just use these instead？



![](img/7c1569cae66c8d0c7328f708d070553c_8.png)

Let me make sure that there's nothing in the chat What is GCd good question so GCd is garbage collected。

 don't need to know what that means yet， I'll talk about that in a moment。



![](img/7c1569cae66c8d0c7328f708d070553c_10.png)

嗯。

![](img/7c1569cae66c8d0c7328f708d070553c_12.png)

So。Let's first tackle why not use C and C plus plus just like we've been using for so long。

 and we're going to elaborate on this more on Thursday， but this is kind of a。Just one aspect of it。



![](img/7c1569cae66c8d0c7328f708d070553c_14.png)

So here are some code that is copied and pasted from tutorialials Point tutorialials Point is one of those websites that like whenever you search how to do something and C。

 it's almost always one of the top search results。There is a pretty significant error in this program。

 like a major flaw。Take a minute to look at it and see if you can tell me something that jumps out at you as being wrong with this program。

Okay， a lot of people are saying it in the chat。And I want to ask why you think that this getS function is a problem。

But before I do that， I want to make sure that everyone has the context to understand why this is such a huge issue。

So we're going to go back to 107 a little bit and refresh on some material you don't need to know assembly for this class。

 but I am going to show some assembly to explain like what is happening behind the scenes when you run C programs so that you can。

Understand why this code is so problematic。So when you are calling functions in C that gets compiled into assembly and when you call a function the first thing that you do is you push the arguments onto the stack。

 so we have some memory that's our stack and we push some parameters to the function that we're about to call onto the stack。

Then the next thing that we do is we we run this call instruction in order to invoke the function that we want to call and what call does is it pushes。

Your current address onto the stack。So that when the function that you're calling returns。

 it knows where to return to。Because in programming， like you call a function。

 the function returns is supposed to return to the next line of your program。

But if we didn't save where we are in the program， the function wouldn't know where to return to。

 so that has to be saved somewhere。 We pushed that under the stack in this call instruction。

And then the column instruction jumps to the definition of the function。

 so let's say that this is our function， I've labeled it colly here。

What it does is it saves the base pointer， don't worry about what the base pointer is。

 if you don't remember it's not significant for our purposes right now， and then it does stuff。

So if the function has some local variables declared。

 there will be stack memory allocated for those local variables and you can do things with those local variables and like do whatever you got to do until the function is finished running。

Is this good with everyone so far？So once this function finishes doing stuff and it goes to return。

The first thing it does is its， it pops these local variables off the stack because we don't need them anymore。

And then it pops off the base pointer and restores that into the registers。If that's confusing。

 don't worry about that， again， the base pointer is not significant here。

And then we return and what that return instruction does is it pops the return address off the stack。

And then goes to that address。That way we end up back in our original function。

 which can pop the function parameters off the stack so that we free that memory。

Is this good with anyone， is anyone confused about what's happening here？Yeah。嗯哼。😊。

That's exactly what we're talking about next。Very smart。Cool， so let's talk about that。

 So this is where we were before like we've invoked some function and that function has allocated some stack space。

 some stack memory for its local variables， and now we want to do stuff so let's say that one of those local variables is some buffer。

 some character buffer that you're going to read a string into。

 which is what that previous code was doing。😊，And I've kind of drawn that buffer in these dashed lines here。

So you read some string into the buffer and that ends up filling it up the way that stack memory works by the way is the stack grows down。

 so you start the high addresses and then you work your way down towards the lower addresses。

 but if you're filling a buffer you start at this bottom ish of the buffer and then you work your way upwards。

Because the this bottom address is the start of the buffer， that's the low address。

 And then as you write into the buffer， you're increasing the address that you're writing to so it' it's working its way up。

So this is fine， like there's nothing wrong with this picture yet， but like Serria mentioned。

 what happens if you read too much and if the contents that you're writing to the buffer ends up being bigger than the buffer itself？

If you do that。You can end up with a situation where you actually。I mean。

 you're just writing memory here right you're saying like write memory to this address。

 right memory to this address， right memory to this address。

 you're working your way up and by default， C does not do bounce checks at runtime like there's nothing in C that's going to raise an exception if you end up going out of bounds of your array that's standard in Java's standard in Python and standard in most languages but it's not standard in C and so there's nothing to prevent you here from just overr memory willy nilly going up the stack as far as as you want if you go too far and you go outside of the stack then you will seg fault and so then your program will crash but if you go just a little too far you haven't gone off the stack and so the computer's like well you're writing too valid memory like you're still writing to the stack there's nothing wrong here and you can end up overriding the return address。

Which is a big problem now your program doesn't know where to return to。Even worse。

Let's say that there's some bad person that has supplied the input to this buffer that is dictating the contents of this buffer。

If that bad person can write their string such that they know what is going to end up overwriting this return address。

They can supply a pointer to the beginning of the buffer。

And then they can fill the beginning of the buffer with assembly code， their own assembly code。

 whatever they want to write， such that when this program executes the return instruction and it pops this return address off the stack and goes to it。

Instead of returning to the previous function， you're now returning to the beginning of your buffer and executing whatever malicious assembly an attacker has placed inside of it。

Does this make sense to people， this was like a mind blowing moment for me when I realized that this is possible。

Is everyone good with this？Thumbs up thumbs down。So， this is。

A huge problem and this is a problem known as a buffer overflow。

 if you've ever heard the term buffer overflow， that's what this is returning to， referring to。

 you have some buffer and you've overflowed the buffer with data such that you end up writing arbitrary data to different places in memory that it wasn't supposed to go to。

There was a famous virus called the Morris wormm。 It was the first really big virus on the Internet。

 really the first like。😊，Virus at all that， that had widespread。Effects on the internet。

 and this is back in 1988 before I was born and before most of the internet， as it is today existed。

Take a look at this code and see so some context， there used to be a program that would run on all computers called fingeringer D and fingeringgerD would allow you to send a request to a computer and get back some information about who the computer belongs to and the idea was like if you're working in a research facility and there are like a couple of different computers there and you want a query like。

There's this computer on the network， who owns it， like who do I talk to in order to get information about this computer。

 you could send a request to fingerer D and fingeringger D would send you back like， okay。

 this computer belongs to such and such and and it was kind of like the first social network in a sense that like。

You can't see very much， but you can kind of see a profile of like who lives on this computer。

 who works on this computer， so on and so forth。So this is code from FingerD in 1988。

And there's a vulnerability in this code that allowed this Morris wormm to spread all over the internet。

 It took down， I think， 10% of the internet at the time。

So the natural question is like where is this issue in the code？

And you don't have to recognize all of these functions。嗯。But do you see。

A problem with how this code is handling memory。Line is only 512 characters。

 so why is that a potential problem and feel free to unmute yourself？Yeah， so。Car line 512。

 this is where we're allocating memory on the stack for for the request that is being read in and then we're reading in the request here and if you're not familiar get S is a C function that。

Reads from Standard In， which we haven't talked about yet in 110。

 but Standard In is just like if you're typing into your terminal。

 then that's where the input is coming from。Now Fingert actually had a different setup where instead of getting input from the terminal from like somebody typing。

 it was getting input from somebody typing over a network and later on in 110 you'll see how this works。

 but really this input is coming from somebody on some other machine somewhere else and so it was reading input from that somebody into this buffer。

And we know that this buffer is 5， 12 bytes long， if you look at this code。

 you can see there's only 5 12 bytes of space， but GetAs doesn't know that you've given it a pointer to some region of memory and you haven't told it how big that region of memory is。

And so there is nothing in here。Like it's not about the implementation of getS。

 it's like you haven't given it sufficient information。

 there's nothing here that could prevent it from reading too much memory into this buffer if somebody types a string that is longer than 512 bytes。

 getis is happily going to copy it into this buffer。And if they type more than 512 bys。

 you're going to go past the end of this buffer up into the base pointer and the return address。

 And when you go to return， you're going to be losing control of the program。

 The program is going to end up。Going somewhere that you didn't expect， and hopefully that's a crash。

But in the worst case scenario， the attacker is actually taking control of your program because they could have it return to some code that they have written that they have supplied and that's exactly what happened somebody would send a request。

They would send some input that contains the Morrisseorm code itself。And。When this function returns。

Main does return， by the way， mainine is just another function that can return somewhere。

 when that function returns， it goes and ends up running the Morseorm code itself。

 which propagates itself to other computers。Spread all over the internet took down 10% of the internet and was a huge problem。

So get us is the issue here。This。That's a really good question。 Why does it take down a computer。

 It doesn't actually have to take down a computer， right。

you could just crash this one instance and you're not really taking down the entire computer。

 but the way that the Morseorm was written， it used too much system resources such that the computer was constantly spending time trying to infect other computers and so for that reason it ended up going down。

So this is advice on the internet， on like the front page of search results on Google in 2020。

And we actually have the exact same problem like I was trying to find examples for for you all of like。

But for overflows that happen in very simple terms。

 And this was even better than I was hoping for because I saw this and I was like。

 are you kidding me， Why are you calling get us in。In 2020。And you think like， okay。

 well I'm smarter than that I just won't call get us or I won't call these like dangerous C functions that that don't take buffer lengths so that I can avoid overflows like professional engineers don't make stupid mistakes like this。

 right？There was this really interesting paper that I would recommend checking out that Ar and I read last quarter in a security class and the authors of this paper。

 they basically went out and bought a car and they were like。

How many ways can we attack this car and take over this car。

 like what different attack vectors are there and how can we take control over this car？Some。

 some quotes from this paper， so like most modern cars have cellular capabilities。

 even if the car doesn't have a web browser inside of it or have like entertainment features that use cellular capabilities。

 most cars have capabilities so that it can report crashes， for example。嗯。

This car in particular had a 3G modem， but this papers from 2011 and 3G service wasn't widely available。

 so it also had a like an analog cellular modem， the kind that you make cell phone calls over。

 and it had some code to translate analog sounds like pitches。Into digital bits and bytes。

And they used some proprietary software from Airbiquity in order to do this。

 so they the authors did not have access to Airbiquities software。

 but they did some incredible reverse engineering， I'd encourage you to read about it if you have the time。

and they figured out that this protocol， this this proprietary protocol supports packet sizes up to 1024 bytes。

 but there was no code inside of their control software that assures that the buffer is not going to overflow。

They had some issues with actually exploiting this， like in theory。

 it is possible to overflow the buffer， but it was not obvious how to because there were other constraints。

 but they ended up figuring it out。And even worse， they figured out a way that was so simple to attack these cars that they could just record an audio file and they could play it back over a phone like they could literally dial the car from an office phone and then play it from an iPod speaker。

 and they would take control over the telemetry module of the car。

And if you know anything about cars， cars don't have the best software practices。

 the different components of the car are not very well isolated。

 so if you can take over one component， you can take over the entire car。

 you can send messages to the bus that wires everything together and you can do things like you can cut the transmission sometimes turn off the engine。

 can sometimes turn off or control the steering and it's pretty frightening the consequences of this。

And so you say， okay， well， I just won't work for a car company。

And so that I would give you countless examples of。Top tier companies that invest a lot in security。

Just being completely helpless in trying to squash vulnerabilities。

 this vulnerability here in the Chrome browser is from April 2， which I think was last Thursday。

 so if you haven't updated your browser recently， make sure that you're on the latest version they're countless issues and most of them are from buffer overflows if I was searching for buffer overflows and vulnerability database and I was just scrolling forever these are just from 2019 because they're everywhere。

 they're countless， they're very difficult to mitigate。Most of them are simple， silly mistakes。

 so this was an overflow in Chrome OS， which powers Chromebooks。

And it was just a silly off by one error。You would think that， okay， well。

 if you just overflow a buffer by one by like。That's unfortunate。

 but can you really do anything with that and if you check out this article。

 it turns out that you can these researchers spent a long time trying to figure out how to exploit this and they were able to compromise the Chromebook operating system。

But some of them are more subtle。I argue that this code is vulnerable to a buffer overflow。

Take a minute to look at it， and。Let me know if you can identify what's wrong here。Wow。

I'm very impressed because。I I didn't get this the first time that I looked at it。

 So let's look at this together。 at first glance， this actually looks pretty good。

 So we have a proper balance check here。 Like we're making sure that the number of bytes to copy does not exceed our buffer。

 And just for context， by the way， the context of this code is somebody sends us some network request。

 some data over a network。 So it' it's not trusted Any could have sent this sent us this data。

 but they， they tell us how much data there is as well as the data。😊，Itself。

 and this is pretty standard in in networking code。

It's pretty standard in C code in general because buffers， like where you store data。

 arrays don't have an associated length stored inside of them。

 you always have to keep track of how long they are and past that length。

 so this is a pretty standard type of scenario， you have a length and you have some data that you're reading。

And this looks pretty good because we're making sure that the amount of data that we're copying into our buffer is not going to overflow the buffer and we're using stir end copy Stir copy is a very dangerous function。

 by the way， and you'll probably encounter this in 110。

 remember this for assignment two because a common mistake is to use stirR copy。

And if your string is too long or if it's missing a null terminator。

 you'll overflow your buffer because stirir copy will go until if it sees a null terminator in a string and that may copy past the end of the buffer。

So using Steing copy， like this is all good and well。The very。

 very subtle problem here is bytes to copy is an int， which is a signed number。

And stir end copy takes a size T， which is an unsigned number。

 And if an attacker were to give us a length like negative one。When we cast that to a size T。

 which is unsigned， that ends up underflowing to the maximum int size。

 which is going to be like 4 billion。And as a result。

 we're actually copying way more data into this buffer than we think we are。 and you might say like。

 okay， well。We should just not allow implicit casts from signed numbers to unsignented numbers and like maybe that's true。

 but the fact still stands that in C if you try to compile this code by default。

 it will not give you any warnings or errors， it will be perfectly fine with this and you look at this code and you're like that looks totally fine to me but actually there are huge issues with this。

Does that make sense to everyone， everyone follow。So we'll talk a little bit more on Thursday with some more reasons and some more issues that arise in C and C++ programs that make safety so difficult like you can be a professional developer for all your life and spend a lot of time dealing with these issues and at some point you will still make a mistake it's just so impossible to be perfect here and that's what we want to illustrate in this first week so that it's clear where rust's design comes from。

If you go back the， oh， another side point。A question that you might reasonably ask is。

 don't we have tools to detect these kinds of things like I've run or vgriand on my programs before。

 And I've seen this error like invalid right of size 8。 In't that a buffer overflow like。

Why why can't we just run tools to detect these kinds of things Does anyone know feel free to talk。

W why wouldn't you always be able to define it？Yeah， yeah。

That's basically it is valgrind tells you about problems that happen。

It doesn't tell you about the problems that could happen， but haven't。

You have to have the right input to actually cause the buffer overflow。

 and if you don't observe the buffer overflow happening。

 Valalgrind doesn't realize that there's potential to be a buffer overflow。

And so there's kind of two approaches here， you can either run your program and look at what is actually happening。

Or you can look at the code and theorize about what could happen。In the first case。

 what Valelgriin does， this is called dynamic analysis。

 you run the program and you analyze what is going on here and what kinds of problems are there in this case you end up missing a lot of problems because if you don't have a malicious input that causes a buffer overflow。

 you won't see it and you won't realize that a buffer overflow has happened。On the flip side， if you。

If you look at the code of a program and try to predict what might happen。

 This is called static analysis。 you end up with a lot of false positives because from just looking at the code。

 you say， okay， well， somebody might supply this input that causes this effect。And in practice。

 it turns out that nobody could supply that because you have this if statement somewhere else in your program。

Code that is very complex is very hard to reason about。

 and so most static analysis ends up producing a lot of false positive saying， oh。

 you might have a buffer overflow here when in reality it's not actually possible to have a buffer overflow there because theres some complexity in your code that addresses that。

And in practice， a lot of static analysis has so many false positives that it's just not helpful。

And so yes， we have tools to try to help with these things。

And we've gotten a lot better in the last 30 years。 And yet， despite all the progress。

 this is still such a huge issue。 I mean， you saw the the scrolling list of buffer overflow vulnerabilities。

 and we still have a very long way to go。Yeah， Sarah。

 I see your question about the static analysis point。

 we're running a little short on time so I'm going to follow it up in Slack with a clearer explanation。

 it's not important to this class， I just want to make the point that even though we have made a lot of progress。

 there are still some pretty fundamental problems with trying to use traditional approaches。



![](img/7c1569cae66c8d0c7328f708d070553c_16.png)

So the other flip side of this is like， okay， well， if we don't want to use CNC++。

 why don't we use garbage collected languages and if you're not familiar with the term garbage collection。

 that just means that you don't have to allocate memory and free memory yourself。For example。

 in Java you just say I want a string or like I want an array and you just use the things and the language itself figures out how to manage the memory for you on your behalf。

 so it figures out when you're not using that array anymore and it calls free for you to release that memory。



![](img/7c1569cae66c8d0c7328f708d070553c_18.png)

And to illustrate this， here's an email that we got back when I was staffing in Kimball。

 so a resident emailed me suggesting that。We pay for a garbage collection service and this person wanted to volunteer or not volunteer but to take out everybody's trash in exchange for payments and so this was a。

Pretty long email that。I said。Trash is a big issue。

 let's take care of it and so they said I have a painless solution for you， it's all set。

 I will collect a trash from every room， every week to maintain cleanliness for less than 50 cents quarter per student per weekday we will'll take out the trash for all 10 weeks of the quarter。

It's a great use of dorm funds because it benefits every member of the dorm equally and it's free for the residents and you'll just have to pay it out of dorm funds。

So what are your thoughts on this email？Good idea。 Ba idea。Feel free to unmute。That adds up quick。

 yeah， it does， it actually turns out that this was like a third of our budget。Other thoughts。

That's a really good question， probably not。So yeah， that's another issue with this kind of setup。

Let me throw in an additional twist and say that， instead of。You leaving your trash outside。

 which I presume is the premise of this， leave it inside your room and the garbage collector will come knocking on your door when it's time to clean up and will come in and pick up your trash。

What's that。Yeah， what happens if the resident's not there or like what happens if you're busy and you like really don't want to be interrupted？

I like to sleep， do not bother me， yes， me too。Right， like you don you don't want to be interrupted。

 And so some issues with this， this is actually a pretty similar proposition to garbage collection in programming。

It is a huge benefit。 Don't get me wrong。 And like I don't know if we have some grad students here。

 but if you've lived in the dorms。You know， you've seen like the dining hall plates left in the hallway and the cockroaches and like garbage being left around is a really big issue。

 and it is true that this does a big service to everybody by cleaning this up and making sure that things stay well maintained。

However， as you guys pointed out。It is really expensive。 and in programming。

 there are a lot of different kinds of garbage collectors。

 but no matter what kind of garbage collection you use， there will always be nontrial overhead。

It's also really disruptive， like imagine having to work and then somebody comes knocking on your door to get the trash and like wakes you up if you're sleeping。

 This is actually what happens in a software garbage collector there are what are called stop the world posits where like when the garbage collection runs。

 you have to stop doing everything because the garbage collector needs time to go and figure out what is garbage。

 what is memory that we can discard and what is memory that's being used that we need to keep。😊。

It's very disruptive and it causes a lot of pauses in programs， it's also nondeterministic。

 you don't actually know when garbage collection is going to run it runs whenever we're low on memory in the dorm example。

 like it's going to run whenever it's getting cluttered and trash is piling up and it's time to take it out。

When are we going to hit a GC pause， a garbage collection pause， we don't know。

 depends on how much memory is being used。And this is a smaller point。

 but in some situations you really need to control memory for yourself because you want to lay out the memory in a way that's ideal for cash performance。

We'll talk a lot more about cache performance later on in 110。

 And so this is probably a point that will make sense towards the end of the class。

 but in some cases， you want to lay out the memory yourself。

 And if you're using a garbage collector where the garbage collector manages the memory allocation for you。

 you can't really do that quite as well。Disord is a very popular chat that you may have heard of。

 that used to be written in Go which is a new alternative to C++ that is garbage collected。

 so it's different from RE rest， you manage your own memory similar to CNncC++ Go is more similar to like Java or Python and that it manages the memory for you。

And these are some charts from this blog post you can see every two minutes there are pretty significant latency spikes you go from this is probably like 10 second or I'm sorry 10 millisecond latency all the way up till 300 milliseconds in some cases and these are these are really significant spikes and these spikes correspond to GC pauses when the garbage collector says hey everybody stop it's time to pick up the trash and it's pretty big issue LinkedIn also had a similar issue that they wrote about they said that in production they were seeing stop the world pauses。

 that's when the garbage collector says hey stop drop everything time to pick up the trash of more than five seconds and that's really。

 really really long latency if you add in internet delays like networking delays from somebody using an application to the server back to the person using the application you can end up with。

Very sluggish response times。 And so this is a pretty important issue。 You can imagine。

There was a stock overflow comment that I read once that said I'll add garbage collection to the long list of reasons why I die in games and that's true like if your game stops for just a fraction of a second to do garbage collection that can have a huge effect on performance you can imagine that you don't want self-driving cars to have to stop for a fraction of a second to clean up memory because that could get you killed。

 it's a really important issue in a lot of other areas as well。Um， and the thing is。

 even if you have garbage collection。That's nice， you won't have to worry about freeing memory and allocating memory and having issues there。

 but there are a lot of other kinds of memory issues that we're going to talk about later in 110 and in 110 L that garbage collectors don't help you with and rest is more oriented about safety than it is about convenience so even though garbage collectors are convenient。

 they don't necessarily give you a complete win in the safety arena。

So I'm going to skip this for the sake of time some really quick things about the class you should be taking this with 110 or have already taken 110 we're going to lean heavily on 110 material throughout this class so if you haven't taken 110 yet it is going to be very confusing to follow the class like everything else is past fail。

 you're going to get out what you put in where we don't anticipate failing anyone。

 probably everybody is going to pass but if you don't put time in to work outside of class you probably won't get too much out of it。

The first half of the class is going to focus a lot on CS107 material and memory safety。

 and then the second half of the class is going to say， hey。

 look at these things that we are learning in 110 and building with 110 material。

 how can we guarantee safety in these contexts as well？

The components of the class are lecture exercises， projects and participation we would love for you to come to lecture we're going to try to make it as interactive as possible。

 but if you can't make it the lecture will be recorded the exercises are I think I had a slide on that I'll go to that quick note about participation。



![](img/7c1569cae66c8d0c7328f708d070553c_20.png)

![](img/7c1569cae66c8d0c7328f708d070553c_21.png)

Don't stress about it if we see through surveys and Slack that and your work that like you're engaging with the class and you're trying that you'll do fine and if you're in a time zone that makes it very hard to tune into lectures。

 don't worry about that as well like you can email us and we'll arrange something。

There are two projects in the class。 There are details written up on the course website， CSs110。

tanfordedduu。 And so you can check those out there。

 We'll also send out some some information on Slack。 We're only gonna be grading on functionality。

 You'll find that the rust compiler actually has really great error messages。

 And it catches a lot of the style mistakes that we would comment on in C S110。

 The majority of our style comments are are actually compiler errors in rust。

 and and the rust compiler will actually interactively help you to become a better programmer。

 So I think that's really awesome。 And hopefully that's an aspect of this that you enjoy。😊。

If you have a different idea for a project at any point throughout this course。

 something that you would like to do instead of doing one of our projects。

 please let us know we think it would actually be really interesting and awesome if if you worked on something that you are interested in rather than something that we have come up with and we're happy to help you walk through whatever process it is that that you would need to go through so please let us know if you have something that you would want to work on and we'll make that happen。

The exercises should be pretty short， you'll expect to dedicate like one to three hours per week on those。

 most of the time it'll be one， two hours， but occasionally it may take a little bit longer。嗯。

And this is just。They're intended to be small and fun and reinforce the week's material before the projects so that you don't learn something。

 Sp two weeks， then a project comes out and by that point you've forgotten things。

So we'll send out this information over email and before Thursday。

 if you can take a quick look at this link， just spend 10 minutes looking at the code on this page and try to find as many bugs in the code as you can there are seven different bugs in that code that。

Have a variety of different conceptual errors that really motivate rust's design。

 and we'll be talking about that on Thursday。

![](img/7c1569cae66c8d0c7328f708d070553c_23.png)

So that is all， thank you so much for coming and let us know if you have any issues or if you need to be added to Slack。

 I'm going to stay on for a while， so if you have any questions， comments or concerns。

 please let me know， otherwise thanks so much for coming and we'll see you on Thursday。


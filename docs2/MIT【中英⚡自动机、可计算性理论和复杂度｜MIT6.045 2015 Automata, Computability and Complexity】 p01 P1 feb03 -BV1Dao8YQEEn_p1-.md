# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p01 P1 feb03 -BV1Dao8YQEEn_p1-

对。拿出来。こいつかった。They。超了。T。来。哎呀。こ。可。でスでも。just like。设起来。が？な分ちだ。そい个。No。上午。でまま。はは。😊，It's wrong。や。爬。嗯。Okay。

 so， I guess we'll get started。 So try to give a few minutescause I know that you have to trudge in and unfavorable conditions early in the morning。

 but。Sorry about that。 I don't choose the time for the class。 but so welcome to 604，5。

 This is automata computability and complexity。 that's the formal name for the course。

 it's it nickname is great ideas in theoretical computer science。

 So I'm Scott Aaronson this is my seventh time teaching it since I've been here。

 So I'm starting to get some idea of of how to teach it， although， although I'm still learning。

 and we have three Ts So we've got Adam Eidia， who's there。 hi Adam we've got Saed Meribon。

 who's there。 and we've got Kevin Wu， who I think has not who emailed that he hasn't made it in yet because the delays on the red line caused by the snow。

 But when he gets。😊，And we will point him out to。Okay， so， so。

 so this is the stellar site for the course there。 And we do have a a syllabus online。

 I didn't I didn't print out paper copies because I just seemed too old fashioned。 I don't know but。

So and and， and I， and I will go go through the syllabus in class a little today before we get started。

 So we， we have what， what what looks like a record enrollment this year for， for 6，0，4，5 that。

 you know， that could be because of this huge surge of intellectual curiosity about， you know。

 computability theory， maybe it's that， you know， everyone saw the the movie， the imitation game。

 raise your hand if you saw it Okay， fair fraction。 Allright， well， it has， you know you know。

 it has something to do with with with Alan Touring movie you know， took a lot of liberties。 But。

 you know， we'， we'll learn some sauce some of the reality of what Alan Touring did in this class along with with giel with with。

😊，Shannon with a lot of really great stuff。But anyway， you know， the， you know， it。

 it could also be just that， you know， all the core sex enrollments have been have been surging and it。

 and it could be that that， you know， for the， for the first time since I've been here this course count now counts as a header。

 So you can take it or， or  sex04， sex， right， for， for， for a header and sex，3 or you know， or or。

 or what， what I'd recommend， you can do both。 Okay， but。Alright， so， so let's see。 let's。

 so let's go through a few things。 We do have a piazza site for this course。 You。

 there's a link to it from the stellar site。 piazza is just like a a Q And A system。 So， you know。

 I've used it。 I think the past three times that I've taught this course。 students have really。

 really liked it。 So。😊，So， you know， anything that's unclear to you in lecture， you know， any。

 like clarification questions about the homework， not like， you know， do problem 3 for me。 But like。

 you know， I don't understand what the question is asking or， you know， things like that。 you know。

 so you can， you can ask。 And then， you know， the questions could be answered either by the T As by me or by other students。

 you know， and then if you know， if we have student answer questions like we can endorse them as being good answers or we can add our own comments。

 So it's it's， it's，s it's it's a really good resource。 Okay， so I， I encourage you to use it。

 you know， of course。😊，You know， you should， you should interrupt。 And， you know， I mean， the。

 the class is not， you know， even though this is kind of a a little bit of a forbidding lecture hall。

 you know， you should just please interrupt any time you have， you have questions。 I mean， you know。

 look， I mean， you're all coming here at， you know。9，30 in the morning， right I I I。

 I would like to provide you some sort of value added for actually， you know， physically being here。

 right， I mean， you know， if it was just me standing in， you know， and and talking right。

 then you could just， you know， watch a YouTube video or you could just stay home and read the textbook。

 Okay， so so let's try to， you know， provide some， some value added。 I mean， you know I， I love to。

 to interact with the class， you know， the one， the one danger is that， you know， if you say。

 you know， if you raise something interesting， you know， I can very easily get sidetracked。

 I could very easily just， you know spend 10 minutes of， you know， on just， you know， like， oh。

 you know， that's an interesting direction， I'm glad you ask， So just just， just beware of that。 and。

😊，呃。What else。Oh yeah。 so， so books。 So so this is the main textbook for the course。

 It's intro to theory of computation by by Michael Spsster， who's now the dean of science here。

 guess So you know，'， it's not sort of my my style to follow any one book， too closely。

 So you know like I'll， you know， I'll assign my own problems。 I mean， you know。

 you could even get get through this course without， you know， using the book at all。

 but I recommend it。 Okay， so， so， so， so Ser's book will roughly cover what we do for like the first 60% of this course or so。

 Okay， and so it doesn't cover the stuff that we'll do toward the end of the course。

 But you know basically you know， it covers like the， you know， the basics of you know。

 theoretical computer science。 Okay， but the basics that it does cover it does a really。

 really good job。It has a lot of intuitive explanation， like， you know。

 like for each one thing that I love and that I wish would become standard is that like every time he proves a theorem。

 he said， like like first， here's the idea of the proof。

 And now here's the gory details of the proof， right， And he just， you know， has， has， you know， but。

 you know， but， but， but we always just states the idea first。 And。😊，So。Let's see。 I mean， you know。

 then then the stuff that we'll do in the rest of the course。 there are several books。 This is。

 this is a book I wrote。 It's called Qua computing Since Democrus。 you know， I don I don't want to。

 you know， sort of advertise it or you know， push it too hard on people。 But you know。

 if you it does cover some of this the stuff we'll do at the end of the course。

 There are other books to do that there's one by more in Mers that I really like there's one by aurora and Barack。

 these are all strictly optional。 You know， in addition to books。

 we're also very lucky to have lecture notes。 we've got from the first time taught this course at MIT in 2008。

 We have scribe notes and those are all just available on the stellar site。 you know。

 they're not perfect。 They have， you know they've got some mistakes and them you know。😊，Theyre。

 they're， you know， they're， their scribe notes。 That's what they are。 But and they， you know， and。

 and we're not gonna be perfectly following them， but we'll be， you know。

 we'll be more or less closely， you know， following those。 So those those are also a resource。Okay。

 so in terms of grading and what's expected of you。 So， so there are going to be six P sets。

 in the course， you'll generally have have， have about two weeks to do each piece set and。So， so。

 so we haven't yet set the due dates for all the P sets。

 but we'll we'll do that this week and we'll we'll put that up on the stellar site。 and so you。

 you're welcome to you know， collaborate you know， form study groups you know work on the problems together but we just ask that。

 you know， sort of the usual rules that know， you write up your solutions yourself and that also you list the names of anyone who you collaborated with。

 Okay so and unfortunately we we， we do require you to turn in the fet theet sort of physically， you。

 not not not not just by spirit or by telepathy， you know。

 and not and and and not online either because we， we've done sort of online submission。paPast。

 then it's kind of been a a mess for， for， in terms of grading。 So， so you know。

 we'll I have like P set boxes outside my office where you can turn them in。

 You can also turn them in during recitation， which I'll get to or， you know， or， or in class。 Okay。

 all of that's fine。And。Let's see。Okay， so there will be two。

 there will be one midterm and one final。 So we know。

 and we haven't yet set the date for the midterm。 know。

 if any of you have dates where you know that you'll definitely be away or definitely cannot make the midterm。

 now is the time to tell me send me an email and I can try to， you know， accommodate you know。

 request。 I， if， if I get them now。 Okay， so we will。

 will set a a date for the for the midterm and then the final， you know。

 I don't even control the date for that。 That's just during finals week。 Okay。

 and that's the midterm will be in class。 Okay， and So so yeah。

 so the midterm I think like 25% of your grade finals，35%， the P sets are 40%。

And then we also have like a small participation component。 So if， you know。

 you're someone who's been participating in class a lot， coming to recitation。

 participating in recitation， asking questions， participating on the piazza site coming to office hours。

 that's all stuff that， you know， can， you know， if you're， if you're， if you're like。

 right on the boundary between， you know， and now， you a big or something that can。

 that can make a difference。 Okay， so。😊，Let's see。Okay， office hours， I should say。嗯。呃。Okay， so。

 so my office hours are。Tuesdays，11 to12。 So basically just write after lecture。 Okay。

 or if you can't make that， then you're always welcome to email me and make an appointment。

 And we're going to figure out office hours for the T As to， you know。

 try to maximize the chance that， you know， everyone will be able to make at least some office hours。

 Okay， say my。My office is。32。Is that， But， you know， you can also just， you know， like。

 come to me after class and well， and we'll walk back together to the office if you wan to go to office hours。

 Okay， so。What else。Yeah， okay， so recitations recitations are on Fridays。 So we you know。

 we have like6， you know slots that are available to us for for for doing recitations。

 We're not going to use all of them you know， I mean， we only have three Ts。 And I think we'll。

 I think we'll do three3 recitations。 And so we still have to choose slots for them。

 I think we have like 1011，121，2 and3。 So we'll， we'll try to choose slots to you know。

 maximize the number of people who can make who can make a recitation you know。

 hopefully all of you will be able to。 And then you'll， you know。

 choose a a recitation that you'll go to， you know， and if if you want to switch once in a while。

 that's fine。 But you should sort of have a main a main recitation that you're that you're going to。

😊，On， on Friday is okay， and the recitations are actually important because you know， I I， my， my。

 my lecturing style， you know， I tend to be a big ideas person。 you know。

 I love talking about you know， the history where things come from， what they mean， you know。

 in terms of working out examples you know， this is something that I where I， where I know that。

 you know， I'm not the best in the world。 I try， I really do。 Okay， but but but in terms of。

 you know， you know， I might do one examples of something right， But then， you know。

 you want to see more examples， you want to see you know。

 how to solve problems like the ones that you're getting on the， you know， on the P at than。

 you know， recitation is really useful for that。 Okay， So any。

 any questions about the administrative stuff。😊，Anyone。Okay， so。呃。If not， then we can get started。

 so。Okay， so， so what's， what's the point of， of 604，5， right， why are you taking this course。 So。

 you know， there are lots and lots of course6， you know， courses where you， you。

 you learn something that will be， you know， useful to you in the real world industry this isn't one of them。

 So I mean， you， I mean， I， I mean， I mean， you might learn something useful in this course。 Okay。

 but if you， if if you do， will be sort of accidental。 Okay， this is the。

 the course where we try to show you why you know， computer science sort of deserves the name science。

 right， where we， you know， try to show you the， the， the， the， the intellectual depth of the field。

 you know， this historical routes its you know， the speculative places。😊。

Where it could go in the future， you know， And then， you know， this is a course where we。

 where we try to blow your minds by， by showing you what's possible， you know， in terms of。You know。

 undecidable problems， you know， girdel's theorem， cryptography， the P versus NP P question。

 quantum computing， things like that。 Okay， so， you know， and。Look， you know， it's， you know， when。

 when， you know， in the future， you know， you， you hear， you know， news about， you know。

 exciting new developments in， in cryptography or in you know， physics and computation or whatever。

 right， you know， this， this course will sort of give you an intellectual context for it。 I mean。

 the， the good news about this course is that what we teach here， you know。

 is not going to go out of date anytime soon。 Okay， so。😊，So。So， you know， there， there's， there's。

 there's a quote that I really like from Edgar Dicstra， who was， you know。

 the inventor of Dykstra's algorithm， you know， famous computer scientist。 And he said。

 computer science， you know， is no more about computers than astronomy is about telescopes。 Okay， so。

😊，You know， what did， what did he mean by that， He sort of he meant that computer science is a。

 you know， is a sort of set of tools， you know， often， you know， a mathematical tools， you know。

 this course will will concentrate on sort of the mathematical side of things。 But， you know， there。

 there are other sides as well， right， it's， it's a body of ideas， you know， by which you can try to。

 you know， understand anything， really， right， any kind of rule govern system whatsoever。

 whether it's a cell or or a brain or， you know， set of physical laws or an economic market or。

 you know， yes， a computer Okay， and and。I mean， you know， I， I sort of got into computer science。

 you know， as a kid because I wanted to understand how video games worked， right， and， you know。

 I mean， I mean， clear right， I mean， you know， really， I'd like to understand the physical universe。

 but who， you know， you know，'s it's very hard to ask the the creator of the physical universe。

 You know， why did they make the design decisions that they did， why why did they choose， you know。

 for there to be three spatial dimensions rather than， you know， two or 17， but but you know。

 but video games， I mean， I mean， someone created them， right。

 So someone must must know the answers to these questions and you know。

 and and and and so you could have imagined a priorityi， creating a video game， you know。

 would have been kind of like building an airplane， it would have been this big， you know。

 engineering problem， you know。😊，You you would have a factory， you know， like， you know。

 maybe like for each for each level of the video game。

 there would be like a different part of the factory where that level was assembled。 you know， but。

 but no， it's actually， you know， it's really just these lines of code you know， it's like you know。

 which are which are which are in some sense just expressing mathematics， you know。

 and they're not just some kind of summary of the game， you know。

 they are the game you change them in the game does something different。 you know when I you， I mean。

 I mean， it's very， very easy to take these sorts of things for granted because theyre they're very obvious to us now。

 you know， when when when when I， you know， first saw it you know， was like， you know。

 learning where where babies come from or something， right， it was was a revelation。 So， so you know。

 so， so one， you know， one thing that we try to do is you know。

 to sort of you know reawake just sort of， you know how。😊，How。

 how surprising some of these ideas were， you know， when， you know， I mean， someone。

 someone had to discover， you know， in the first place the idea of computational universality， right。

You know， and， and sort of taking you through the， the thought process that， you know。

 that LED people like like touring to these ideas。 Okay， so。Let's see。 so， so， you know， I mean。

 the the， the field that， you know， is normally sort of seen as you know， trying to understand。

 you know how they， you know， how how how the universe behaves， how it's put together is physics。

 but you could think of physics， a sort of working in the opposite direction from computer science。

 you know， with physics， you start from the phenomena and then you sort of work downwards。

 you find better and better theories that you know。

 that explain more and more that are more and more explanatory and then you know you hope that eventually you'll have this。

 you know， grand unified theory that will basically just be， you know， the code of the universe that。

 you know， you just execute it and you get you get us So computer science， in some sense work。

 you know， I think of as working in the opposite direction that you know。

 you start from set of rules。You know， which don't， you know， they could be inspired by physics。

 but they don't have to be。 They just have to be some kind of wellspec rules。 And then， and then you。

 and then you work upwards。 you say， what can we build by using these rules， right， What。

 by composing these rules together， What kind of behavior can we get， You know。

 and what kind of behavior can we not get， Can we， you know， understand that mathematically。Okay。嗯。

So。So just to sort of wet your appetite a little bit with， with where we're going。 And， you know。

 in the course。 So there's one little of vignette that I that I like to use and the the first lecture just to sort of give。

 give you an idea of the sorts of things that that we'll talk about。And。

This is the problem of how do you set up an online gambling site， Okay， so。Let's， you know。

 we'll assume that you've sort of gotten past all the， you know， the legal issues。

 you've set up your server and the the Cayman Islands or or whatever。 Okay， and， and， and。

 and you w to run an online gambling site。 Okay， so， you know， for simplicity， let's say that you're。

 you know， you have you want to have an online roulette game。 Okay， so， you know。

 people can bet on either red or black， you know， that that a wheel will land on and you know。

 if you know， if they get it right， then they win a dollar and if they get it wrong。

 then they lose a dollar， you know， plus some commission for the House。 obviously， okay， so。Okay， so。

 so you you set up this site， you know， you start running it。 Okay， and then， you know， there's， but。

 but there's， there's sort of an obvious difficulty， which is that， you know。

 the way the Internet works you know， messages get sent one at a time， someone has to speak first。

 So so， so， so the the gambler could say， well， you know， I bet on red。 Okay， and then， you know。

 the website could send a message back， which says， sorry， it was black， Okay， and then you know。

 the gambler could say well， I bet on black。 and then， you know， the House says well， sorry。

 it was red。 Okay， and then they say， well， all right， I bet a black again。 you say， well， sorry。

 it was red again。 they say I bet all right fine， I bet I bet red， know， they say sorry it was black。

 Okay and you know， and you know， this goes on enough times。 you know。

 you might begin to suspect for yourself that， you know something is wrong。M， you might， you know。

 stop using the site。 Okay， you know， I mean， I mean， this is problem。 you know， real， real。

 real casinos have also。 you have to pay out sometimes。 So people will just stop playing。 Okay， but。

 you know， let let， let's say that you， you just had a really big， you know。

 you you just had a one time gamble for really high stakes， right， someone's gonna bet， you know。

 a million dollars on red or something。 Okay， then， you know， we would like，We， you know。

 we you know， I mean， I mean， you know， such a A a discriminating customer would， you know。

 would would， would really like to， to have some kind of guarantee that， you know。

 that the that that the software isn't cheating， right， that the software actually picked you know。

 whether， whether the。wheel was going to land rather or black before the before the gambler came in。

 right， So， so then you know， the question is， how do you do that， right， I mean， in the， you know。

 the you know， in a physical casino， you just set the ball in motion。 And then， you know。

 you people place batsball the ball is still rolling， right， but that's not gonna work online， Okay。

 so， so what else could you do， Well， you could have the the， you could have the house just say。

 Well， okay， you know， the ball landed on black， What do you bet， you know。

 and then the customer says， oh， what what a coincidence， you know。I happened to bed black。 right。

 so， so allright， so is clearly that's not going to work either。 Okay， so does anyone。

 can anyone suggest another solution to this， yeah。Yeah， so basically， you know。

 what you want is some sort of you know， way of committing yourself right So so physically like if we were doing this over paper mail。

 you know， you could just you know take your bet， put it in you know a sealed envelope or put it in a safe or something And then so you haven't revealed it to the casino。

 but you you have sort of committed to the casino that， you know， here is a place where you know。

 I I have committed my decision and and I'm not able to change it and I can reveal it to you later these are all properties that are important and then the casino could。

 you know could say the bull landed on black and then you know。

 you can open up the safe and show what you bet， Okay so so then the question is。

 you know how do how do you do that over the Internet where you don't have physical safes。

 Okay and you know， the modern solution。😊，To this sort of problem is do it， you know。

 by assuming that that certain problems are interactably hard， right， not literally impossible。

 You know， we will， we will talk in this course about problems that are literally impossible to solve。

 you know， with， with any， you know， computer。 we we think you can build in the physical world。 but。

You know， we're， we're merely talking about problems that we think， you know， could take you。

 you know， longer than the age of the universe to solve。 Okay， so that， you know， yes your， you know。

 computer。 you know， operating on some idealized laws of physics could could solve it， But in fact。

 you know， long before it had done so， you know， the whole， you know。

 the sun would have gone called the whole universe would have disintegrated into black holes and radiation。

 you know， you' would have a problem just finding a power source for your computer。 Okay， so。

 so so this is， this is the the sort of thing that we're after。 And you know。

 in order to get that kind of behavior。 you know， what helps is to， you know。

 find a problem which is exponentially hard by which we mean， you know。

 for which the amount of time needed to solve it， you know。

 increases exponentially with the size of the problem。So。You know， here's。

Here's what linear growth looks like。 You know， here's what quadratic growth looks like and exponential growth。

Kind of looks like that。 You know， it doesn't fit on the board。 Okay， so。So， so， so what。

 what kinds of problem， you know， what， what kinds of problems are there where， you know。

 for all we know， they're， they're exponentially hard to solve with， with today's computers。 Okay。

 well。So one famous example is the factoring problem。 Okay， where， you know， I give you a。You know。

 a number， you're supposed to factor it into primes。 Okay，21， you know，3 times 7， right， you know。

 or。I give you some other number。Okay， factor this， right。Okay， here I can， you know。

 I can at least make it so that， you know one of the factors， right， you know， you know。

 by just picking the last digit。 Okay， but but， you know， it even then defined all the other factors。

 right， You know， it could take some time， right， I mean， there's a reason why， you know， they in。

 in elementary school。 They teach you how to multiply， you know， they teach you how to divide， right。

 but they don't tell you an algorithm for factoring， right， because， you know。

 the obvious algorithm could say the you know， the。

 the trivial one is just try every possible divisor right， and just see if any of them work。

 Does anyone know， can anyone suggest an algorithm that's at least a little bit better than that。

Yeah。Yeah， try all the prime divisers。 Although， you know， one issue is that， you know。

 you got to know which ones are prime。 But you know， you know， but， you know， but there， you know。

 there there there are things you can do there， right。

 there's like the sieve of Erto thans where you just cross out the ones that are divided by something else。

 right， There's also， we're gonna come back to this point。 And of course。

 but if you just want to know if a number is prime or composite and you don't need to know what the factors are。

 if it is composite。 that turns out to be much， much easier than than actually factoring the number。

 Okay， and that's a very important point for cryptography for all kinds of things。 So， yes。

 you could do that， you know， you could only test the primes。 But all。

 but there's still a fairly large number of primes。 So yeah。Yes， you can， you can you。

 you only ever have。 this is an important。 You know， this is good point。

 You only ever have to go up to the square root of the number。 You're trying。 Well， why is that。嗯。

Exactly， exactlyly， yeah。 because， you know， if there's a divisor that's larger than the square root。

 then clearly， there's also a divisor that's smaller than the square root。 right。

 so say you're gonna find the smaller one first。 And then， you know， and then you're happy。 right。

 once you find a divisor， then you can just divide it， and then you've got a smaller problem， right。

 so。😊，Okay， so that， so if we think of。Let's talk about asymptotics。

 If we think about n as say the number of digits in the number。

 say the number of decimal digits could also be the number of binary digits。Yeah， let's， allright。

 let， let's， let's， let's take， let's actually take n to be the number of bits needed to specify the number。

 Okay，'s the number of of digits when you write it out in binary。 that'。

 that's about three times the number of， of digits when you write the number out in decimal， right。

But。So so then， you know， the， the， the sort of the stupid trial， you know。

 trying every possible divisor， that's something like2 to the n time， right。

2 to the n times the number of time， you know， there are two to the end divisors and then， you know。

 maybe it takes n and you know， n squared time somewhere around there to try each given divisor。

 So let's just say， you know， the leading order term is， is， you know， is， is2 to the n。 Okay。

 if you only go up to the square root。 then， then， then what's the leading order term。Well square。

 yeah。Yeah， exactly。 It's the square root of two to the n， which is 2 to the n over 2。Okay。

 still a lot。 You know， it's a little bit of a milder exponential。Now， turns out that the。

 the fastest known factoring algorithm that we have today is called the number field sve。

 It's from the， the late 1980s。 think， you know， it uses elliptic curves and it's running time。😊。

Is conjectured to be。About2 to the cube root of N。 Okay， so， you know， so so like there's some very。

 very plausible， you know， an experimentally true number theory conjecture that assuming that it runs in that amount of time。

 you know， if you want to rigorously prove in running time。 then it's two to the square root of n。

 Okay， but。But but empirically， you know， the running time should be about 2 to the cube root of n。

 And so， so what this says in particular is that， you know， you can you you。

 you absolutely can beat the just trying every possible divis。 You know。

 that's not the best that you can do okay， but on the other hand， you know。

 we would still generally call this exponential growth。 in particular， if n is in the， I mean。

 first of all， the constant， you know， in the in the exponent in front of this big out is pretty large。

 But second of all， you know， if n is in the thousands， right， then， you know。

2 to the cube root of n， you know， still reasonably large number。 And you know， and， and so this is。

 you know for better or worse， this is considered good enough that we， you know。

 base the security of almost all of our electronic commerce on， you know。

 the belief that this that the factoring problem is hard。 So，嗯。I mean， we base it on that， you know。

 in， in combination with a whole bunch of other beliefs， like that， you know， the， you know。

 the company that you've， you know， your trusting just hasn't made some， you know， back deal with。

 with the NSA or whatever， right， which， you know， in practice。

 I would actually be much more worried about those other beliefs than I would be about the the efficiency of factoring。

 But。Alright， But so now how， how could so supposing that we believe the factoring is hard， meaning。

 you know， that the， the best algorithm for factoring that there is， you know。

 takes something like this amount of time， which you know， this is not a proven belief。

 let's be clear about that， But， you know， but， but but supposing that we're willing to make that hypothesis。

 how could we use this to solve the online gambling problem。So the question is。

 how can we use factoring to fulfill the， the role of the， of the， of the safe or the。

 or the envelope that we wanted before， yeah。m。Yeah。Yep。Yep。嗯哼。😊，你。Yeah， excellent。 Yeah。 So yeah。

 all right。 So we， we should be a little bit careful about the digits， right。

 the only prime that ends in five is5， right， But but but， you know， okay， you know， you know。

 but like， except for stupid stuff like that。 You know， what you said， basically， you know。

 you know works。 So I mean， okay， so we， we do have to make an assumption， you know。

 strictly speaking， it's a little bit stronger than just that factoring is hard。

 we need some like binary property of the factors to be hard to， to determine。 So like， let's say。

 so let's make a stronger belief or let's make a stronger hypothesis that， you know。

 it is intractable to determine whether， you know， your given composite number has a prime factor that ends in a3。

😊，Okay， you know， now now that that that doesn't follow from the mere belief that factoring is hard。

 right， You could imagine that there could be an algorithm。 It just tells you， yes。

 your number has a prime factor ending in3， say what is that prime factor。 And the algorithm says。

 I have no idea， I just， you know， like， you could imagine that， you know。

 it sounds a little bit silly。 but you know， then again， we do have， you know。

 we do have algorithms that are kind of like that。 like they tell you， yes。

 your number is composite and you what are the prime factors。 And they say， I have no idea right。

 So so you， you could imagine that。 Okay， but as far as we know today， you know， there's not ane。

 you know， as far as we know today， the fastest algorithm。

 even just to determine whether your number has a prime factor that ends in 3， you know。

 would be this number field。😊，Okay， so， so， so， so supposing that we or， were willing to。

 to believe that then what you could do。let's say you're the， you're the user。 So you'， you're。

 you're the gambler。 So you place your bet by choosing two huge prime numbers。 Okay， and。

 and already here， there， you know， there， there's， there's a bit of a question of， you know。

 how do you do that， Well， so as we， you know， said before。

 there are efficient primality testing algorithms。 There are efficient algorithms。 You know。

 something like N cubed algorithms。That just。Tell you whether your number is primeer composite。 Okay。

 we've known probabilistic algorithms that do that since the 1970s。 And you know， well， well。

 we'll discuss probabilistic algorithms later in the course。 And， you know。

 maybe even say a little bit about how these algorithms work， okay。A deterministic。

 fast algorithm to tell whether a number is prime or composite that was only discovered in， you know。

 in， in 2002 by3。People in India， to， two of whom were were undergrads at the time。 Okay。

 and that's the kind of， you know， discovery that like you， you， you you。

 you remember where you were and what you were doing when you， when you heard about it。

 at least if you're in this field。 Okay， so anyway， we know。

 we know how to do primity testing efficiently。 Okay， so， so okay， but， but then， you know。

 there's still a remaining question， you know， you know。

 about how do you pick two large random primes or what what。

 what what's the other question that we would have to deal with here。I mean。

 besides just knowing whether a given number is prime or composite。Well。

 we'd have to know something about how many primes there are。Right， because， you know。

 if the primes were just really， really， really thinly spread out， then， you know， you could just。

 you know， keep guessing， you know，200 digit numbers。

 like for an incredibly long time before you happen to find one that was prime。

 So this this still wouldn't work for you know， if you wanted to generate a huge random prime number。

 So fortunately， we know we you know， like the question of of how you know。

 how are the prime numbers distributed， how spread out are they。

 this is not a question that's escaped mathematicians' attention， to put it mildly， you know。

 like much you know， you could say like a large fraction of all the mathematical effort， you know。

 in the history of math has gone into questions like this one。 you know， you know。

 I'm sure that some of you read about the the breakthrough that there was just like year or two。ago。

 when Yang Zang， you know， proved that there are， there are infinitely many pairs of prime numbers that are that are only at most 70 million apart。

 you know， and that's since been improved know， there are infinitely many pairs of prime numbers that are only 100 apart。

 you know， the the ultimate the ultimate， you know， and， and this。

 this was all over the media that it'， it's in the it's in the New Yorker， you know， this week。

 I think， because of， you know， Zang's， you know， personal story that he couldn't get a job。

 He was working at subway and he was， you know， But meanwhile， he was working on， on prime numbers。

 Okay， so。But， you know， the ultimate goal here is to prove the twin primes conjecture that would say that there are infinitely many pairs of primes that are two apart。

 Okay， but so， so we don't know that。 But， you know， one thing that we do know is。嗯。

Let me put it this way。Okay， if I suppose I choose an end digit number completely at random。

 Does anyone know roughly what is the chance that it will be prime。Someone else。Yeah。Yeah。

 it's about one over n。 Yeah， it's， I think it's about， so， so sorry。

 to the number of primes up to capital n。 Let's say is asymptotically。 it's about， you know。

 n over the natural algorithm of N。 And from this， you can work out the， you know。

 exactly what's the chance that that an n digit number is prime。

 It's it's C over n for some constant C that I that I don't remember。 but。You know， and， you know。

 so， so， so as you get， go out to larger and larger ends， this becomes， you know。

 a better and better approximation。 You know， the question of exactly how good an approximation it is。

 is not， we don't know the answer to。 you， as anyone know what that question is called。

 how good an approximation this is。WellIt's called the Riman hypothesis。 So， so that's。

 that's a big question。 Okay， but we know that eventually， you know。

 it does become better and better approximation， yeah。Oh， I'm sorry， Capital N。

You could think of it as like2 to the little N。 So， so， so capital N was like， if I ask。

 how many primes are there up to。You know， a given number。You know。

 how many primes are there up to capital N， then that will be about capital N over natural log capital N。

 right， You know， then if I ask， what is the chance， you know。

 that a number that has little n digits is prime， right。

 And the largest number with little n digits will be， well。

 depending on whether we're talking about binary or decimal digits will be 2 to the little n or 10 to the little n。

 then that will be capital N。So。嗯。Yeah， and okay， this by the way， this。

 this is sort of something you should get used to in this course that sometimes we have to sort of shift up and down by by an exponential。

 Okay， so sorry， so anyway， So， so what this means is that like， yes。

 the primes do thin out as you go to larger and larger numbers。

 that's not very surprising And you know， we've sort of， you know， like notice this in。

 in in grade school， it's like yeah， know， as you go out to larger numbers。

 there are more possible things that you're， you know， that could divide your number。

 And so there's the less there's a smaller chance that your number is prime Okay。

 but this thinning out process， you know， what， what this is saying and the theorem that that does thin out at this rate It's called the prime number theorem to give you some。

 some idea of its importance。😊，For math， you know， it was approved。A little over 100 years ago。 Okay。

 and。So， so what what the prime number theorem says is that the rate at which the prime thin out。

 you know， is not， is not that great， right， There's， so even when you get up to say。

 thousand digit numbers， there's still roughly one in1000 of them that are going to be prime right。

 which means that， you know， you would merely have to choose about 1000 such numbers， you know。

 before you happen to hit a prime。 Okay， and， you know， in fact， any time that， you know。

 like like like have any of you like had to generate a curbos I and it says like waiting， waiting。

 you know， you know， you have to spend， you have to sit there for like 10 seconds。

 all generates your， your I what's it doing， it is。Trying to find some huge random prime numbers。

 Okay， it's trying to verify that they're indeed prime。Okay， you know， and then once it finds them。

 then it can multiply them， you know， And that's that， that's a public key。

 And the prime factors themselves are a private key。 Okay， and we'll， you know。

 we'll explain exactly how it works Li later in the course， Okay， but。To， to， to come back to。

 to online gambling。 what you can do is so。It actually doesn't matter for this purpose。

 which player starts。 It could be either one。 Okay， but let's say。

The gambler chooses numbers P And Q Cho， you know， chooses two huge random prime numbers， P And Q。

Okay， and if at least one of the， the numbers ends in  three。

 then this is taken to mean that the gambler is betting on， on black。

 And if neither of them ends in 3 and this is taken to mean that the gambler is betting on red， okay。

 so。And then。The gameboard multiplies the numbers。 Okay， and multiplying， you know。

 is something that your， you know， at least your computer can do very efficiently， right， you know。

 certainly like in the， the number of digits of the numbers squared something like that。 You know。

 in fact， you can even multiply numbers better than that。 Does anyone know what's the。

 the fastest multiplication algorithm。 I'm sorry。So。

 so there are multiplication algorithms that take time。

 which is like to multiply n digit numbers and something like in time like n times log n times some really。

 really， really， slowly growing stuff like， you know， the iterated logarith and， you know。

 this really slowly growing functions。 Okay， basically and and n log n。 Okay。

 these are algorithms based on the fast Four year transform。 But anyway， you know。

 you use one of these algorithms multiply the numbers， you send n over to the casino。

 And now the casino essentially has you know， your bet in a locked safe。 right。

 that that's what they effectively have。 Okay， so now the casino can go ahead and tell you the。

 you know how the， what the ball landed on。 whether it was black or red。😊，Okay， and then finally。

 we have what's called the the decommit stage， which is。When you reveal the factors of the number。

 Okay， so， so you now， you know， so， so at this point， you can say， you know， the gamler can say。

 here's the factors of the number。 The casino can then check to make sure that， you know。

 that those really do multiply to n。 Okay you know that that's important。 otherwise。

 you could obviously cheat。 Okay， and， you know， and then they can check that， you know that， yes。

 P and Q do encode the bet that you know， you know。

 they can then check what whether that bet was a winning one or not。 Okay。

 can anyone think of anything else that the casino should also check besides the P times  Q equals n。

 yeah。Make sure they're both prime。 Yeah， what could go wrong if one of them was not prime。Yeah。Yeah。

Exact， yes， yes。 okay， everyone understand that， right， if， if。If， if the numbers were not prime。

 right， then you could have sent a product of more than two primes。

 and then you could have just factored the number in a way of your choice， depending on。

 on what you wanted。 Okay， so， but， you know， as long as P and Q are both prime。

 there's an important theorem that that sort of helps us that sort of proves the soundness of this protocol。

 It's not the prime number theorem， it has a different name。 Anyone know， the。

 the other theorem that we want here。Well， we want the the fundamental theorem of arithmetic， Okay。

 which says that every， every positive integer can be factored into primes in exactly one way。

 you know， up to the ordering of the of the prime factors。 Okay that's you know。

 that eli proved 2300 years ago。 And and that's important for us because otherwise， you know。

 if your number had multiple factorizations， then you could always just wait for the casino to say whether the ball was black or you know。

 landed black or red and then just you know， give the factorization that that， you know。

 that corresponded to to whatever would win。 Okay， so。

 so it's important that every number has exactly one factorization and that's， that's by the way。

 that's not true over arbitrary number fields， there are other， you know。

 number fields you know other rings other than the positive integers where you don't have this property of unique factorization。

 Okay。😊，Yeah。Oh， no， the casino doesn't need to。 Okay， So this's， that's a good question。

 It's important that the， the casino doesn't need to have a giant list of all prime numbers。 Instead。

 they can use one of these primity testing algorithms that I mentioned before。 right？ So， so again。

 it's very important that。That there are fast algorithms， you know。

 to tell you whether an in digit number is prime or composite。You know。

 so they can run those algorithms on P And Q。Mm。Yeah， so， yeah， so， you know。

 in both of these properties， of the factoring problem， the fact that factoring as far as we know。

 is hard， but also the fact that telling whether your number is prime or composite is easy。

 Those are both of central importance in modern cryptography。Right。嗯。Okay， now， one thing that。

 you know， we're going to， to do a few lectures on at the the very end of the course will be quantum computing you know。

 happens to be what what I work on much of the time。 and as it turns out。

 it was discovered 20 years ago by by Peter Sho， who's in the applied math department here that a quantum computer could factor numbers efficiently。

 Okay， which means that if the if， if the casino has a quantum computer in its basement。

 then this entire scheme is broken。Okay， you know， now there are， as， you know， as， and， and。

 and we'll explain a little bit about about how that how that works。 Now， you know。

 even even a quantum computer would not be able to do absolutely anything。 So， yes。

 it can factor huge numbers， you know， the way that it does that exploits sort of very special properties of the factoring problem。

 Okay， ironically， you know， some of the same properties that make factoring as useful as it is for cryptography。

 kind but very special sort of number theoretic properties。 we do know of， you know， if。

 if you just want to run this online gambling site。

 then we do know of other cryptographic methods to do that， that as far as we know， you know。

 would not be breakable， even with a quantum computer。😊，Okay， so。Alright， so， so actually， you know。

 when when， when I said that everything that you learn in this。

 in this class is going to be completely useless， I mean， you know， it's， it's like， you know， in。

 in in， in， in， in the history of math， you know， like like like aim， you know。

 aiming at usefullessness has repeatedly sort of been this， you know。

 one of the best ways to achieve usefulness， right， and so， you know， so， so。

 so cryptography is one of the clearest examples of that， right， And it's， it's， it's one of the。😊。

You know， it's a cryptography is sort of the place where， where you know。

 the sort of theoretical concepts that we're talking about， you know， are the most directly you know。

 most obviously you know， have have real real world implications， you know。

 there there are you know there are other places。 But but but cryptography is， you know。

 is certainly one of the most striking。 Okay， so， you know， and that's， you know。

 and and part of the reason is that， you know， with cryptography you know。

 it's like you don't you don't have to just just you know。

 theorize about maybe there's a hard case of your problem you know， if there's a hard case。

 you know for God's sake that that's what you're using， because you're trying， you know。

 you've got someone who's trying to make the problem hard。 And， you know， if and and now you really。

 really had better be confident that this problem is hard And you better be confident that no matter how clever anyone is。

Not gonna be able to solve it efficiently。 Okay， because， you know。

 because the entire setup is adversarial。 Okay， and so， you know， and， and that's what， you know。

 theoretical computer science is all about。 It's about， you know， how， how certain can you be， right。

 about， you know， what are the the ultimate limits of， of what someone can or can't compute， Okay。

 so it's a great field for， for， for， you know， anyone with like a mathematical cast of mind。

 It's also a great field for， for really， really paranoid people right， who are， you know。

 sometimes are the same people，😊，Okay。Good， so that was just a kind of wet your appetite。 Okay。

 but you know， so， so， but， you know， to， you know。

 we're going to circle back to to cryptography to know。

 efficient algorithms to quantum computing to sort of all the different things that werere sort of illustrate it by this little vignette。

 Okay， but we've got a lot of stuff to sort of build up to before， you know。

 we can really rigorously talk about these things。 Okay， like what exactly is an efficient algorithm。

 you know what's even the right way to formalize what we're talking about And you know it took people a while to to figure that out。

 know， and get it right because it wasn't obvious， you。

 and you could say to some degree it's still not obvious。

 because people came up with a definition of what they meant by efficient computation and that definition worked extremely well。

For decades。 But then it left out quantum phenomena， right， And the result was that， you know。

 people were LED to believe that the factoring problem is hard when， you know， when you。

 when you take in， when you take quantum phenomena into account， actually， it's not hard。 Okay。

 so so we're still， you know， sort of trying to， to figure all these things out。 Okay， but。嗯。But。

 you know， we're gonna have to， you know， start somewhere。 And so， so， so， so roughly like a。Sorry。

 a rough outline of， of this course will be like for， for a third of it。

 Maybe we will talk about automata theory and formal languages and computability。 Okay。

 so we'll sort of see the， oh， and， and， and circuits。 sorry so。So we'll sort of， you know。

 and these are just sort of models that will sort of get ourselves get。

 get get ourselves used to talking formally about computation。 Okay， proving theorems about。

 you know， what you can do in a given model of computation and also what you can't do。 Okay， so。

I mean， to some extent， you， you could say， you know， any anyone who's， you know， who's really。

 you know， who's who's done Euclidean geometry in high school， right， and who， you know。

 got good at like doing rule in compass constructions， you know， is already familiar where。

 in some sense with a model of computation， Okay， you could say that that the， the， you know。

 what kinds of geometric figures can you construct using a ruler and a straight edge only right。

 this was sort of the， the first theoretical computer science question， you know。

 that that that humans ever asked if you want to be a little bit anachronistic about it。 Okay。

 so you know， the。The the ancient Greeks were very， very interested in questions like， you know， I。

 you know， I'm given two points in the plane。 Okay， now I'm allowed to， you know。

 given any two points。Construct a circle that's， you know。

 contains one point and is centered at the other point。 So I could do that。 I could do that。

 I'm allowed to。You know， any place where two things I've drawn intersect each other， I'm allowed to。

 you know， note that as a point。 you know， anytime I've got two points， I'm allowed to draw。

 you know， a line that passes through them。 look， I just bisected this line， what they do right。

 so you know， so， you know， and then once I know how to do something。

 then I can just sort of encapsulate that thing， I can treat it as a subroutine， right。

 I can now say any， any future time that I might want to bisect a line。 Okay， you know。

 or construct a line that's at right angles to another line。 Okay， now I can just do that because。

 you know， I know it can be done。 Okay， so， so so， you know。

 so just like with any other model of computation， you're allowed to use modularity。

 you're allowed to build up subroutines and then call them you know， and then。You。

 but then when when where things really， you know， and you can do amazing things in this model。

 right， So， so so Gauss， when he was a teenager， figured out how to construct a regular 17 gun using you know。

 ruler in straight edge only also a regular 65537 gun， and you know， and so on for certain， you know。

 for primes of the form 2 to the two to the end plus one， I think， and you know。

 he was so proud of that you know， even like at the end of his life when hed done so many other things that he asked that a regular 17 gun and be inscribed on his tombstone and you know。

 apparently you can， you can go there in Germany and you know， and it's there。

 But but the carver just basically made a circle because it's like， you can't， you know。

 you try to carve a regular 17 gun。 It really just looks like a circle okay， but。😊。

But where things really get interesting is when you start asking， you know。

 what are the ultimate limitations of this model， what， what， what。

 what kinds of figures can you not draw， right？ And there was this ancient question of。

 of squaring the circle， you know， of trisecting the angle， right， And then。

 and there was this problem of duplicating the cube， right， it was a strange way to put it。

 But the in modern terms， what the， what it really meant was just。

You're given a line of length 1 you're a line segment of length 1。

 And now you would like to construct。A line segment of length cube root of 2。So。

If you want to construct a line segment of length square root of 2， that's easy to do。

 How do you do that， anyone。Yeah。Yeah， yeah， exactly。 You can make a right triangle。

 which there are various ways to do it。 But， you know， here you go，1，1， there you go。

There's your line segment of length square root of 2。 Okay， but now， you know。

 you want to make a line segment of length cube root of 2， much less obvious how to do it， right。

 There's no， there's no analog of the pythagorean theorem involving cube roots， which is， you know。

 which is itself an interesting fact， but but you know you know people just know for almost 2000 years。

 people just figure all right We' probably just not clever enough， Okay， and you know。

 and and again and again， there would be people who would come up with know。

 ways to do it right they would have proof that here I can duplicate the cube here's my。

 And often it would it would kind of look close， right， it would be， you know。

 some would construct some segment that was know， length was the cube root of two up to a few decimal places which you know。

 which indeed you can do you know， and and sometimes， you know， you would have to really。😊。

Sint that in really study it to sort of figure out where the error was。 Okay。

 on a not completely unrelated note。 like I get， you know， every week or two。

 I get an email proving P equals NP P， okay。So。You know， and sometimes， you know， you really have to。

 you know， you know， you know， if you really wanted to pinpoint where the error was。

 it would take quite a bit of time， Right， Okay， you know。

 if someone claims to prove P is not equal to NP p， then， you know， then that's。

 that's kind of you know， can be a hard case sometimes you have to find the error。

 If someone says that they prove P equals N p。 And they say that even the algorithm is efficient。

 Then I just say， you know， so go factor， you know，2000， you know。

 this 2000 digit number that I'll give you a link to。 And then， you know。

 after you've shown me the factors。 You know， and I've checked them。

 then then I'll be happy to discuss further。 And then， you know， sort。

 sort of never hear back from them after that。 But but。😊，Okay， but。But， but it， it took， you know。

 until the， the mid 18 hundreds for people to really sort of step back and say， well， you know。

 can we engage in meta reasoning about this ruler in straight edge model of computation， You know。

 what are the ultimate limits of this model， Okay， and you know， and then they， they， they。

 they started thinking about it， like algebraically， about just like what， what。

 what possible lengths of line segments can you construct， You know。

 starting and what they realized was that。呃。You know， anything that you can construct， you know。

 is going to involve just starting from 0 and 1 and then doing some arithmetic operations on them。

 like adding and multiplying and dividing and also taking square roots。Okay， why， well。

 because basically， if you， if you switch， if you did geometry in the Cartesian coordinate system。

 right， So， you know， you had an X Y plane， you know。

 you could label at every point by its XY coordinates and then。You know。

 every time you're constructing a circle， you're constructing a line。

 you're looking for the intersection of them， right。

 The intersection of like a line with a line is just a solution to some linear equations， right。

 you know， two variables and two unknowns， right， the intersection points between a circle and a circle or between a circle and a line are the solution to a quadratic equation。

 right， in a quadratic equation， I'm sure you remember from high school can be solved using square roots。

 right， So， so you're always just。😊，Basically， using knees。Operations。And so then， you know。

 the question can be boiled down to a simpler one of can you by starting with 0 and 1 and then iterating these operations some finite number of times。

 can you produce。The cube root of 2。Okay， you know， I mean。

 certainly you can get closer and closer to the cube root of two。 That's that's not hard to see。

 But can you get exactly there after a finite number of arithmetic operations and square roots。 Okay。

 and， you know， so that's a very interesting question。 The answer turns out to be no。

 And there's a very， very lovely proof using Gawa theory。

 which I won't show you because it involves Gaa theory， but it's actually， you know。

 if you if you take an abstract algebra course， is's one of the easiest ones of this form。

 like if you want to prove that you can't square the circle for that。

 you need to know that pi is a transcendental number， you know。

 and that's that's a much harder theorem to prove。 This one is is comparatively easy。 Okay。

 but but but we won't， we won't do it。 But， but in this course。

 we will see many other examples of impossibility theorems for models of computation。 Okay， where we。

 you know， we we。😊，We define a set of rules， you know， here are the allowed operations。

 and then we see some examples of things you can do with those operations。 But then we step back。

 And when we say， here's what you're never gonna be able to do。

 no matter how many times you iterate these operations。 Yeah。

 and and that that tends to be that the kind of result that we that we really prize in this field。

 right， you know， I like the way that that Ser puts it， right， which is that， you know， a。

When you discover an algorithm， you know， you discover how to do something。

 all you've really done is just found an obstruction to an impossibility proof。Okay， so。

Becauseuse you know， the， the the， the， the， the， the impossibility proof for the things that really require you to understand。

 you know， all the possible ways that you could do， you know。

 ever hope to do something and really just understand the entire space of possibilities， right， So。

 you know， and， and impossibility proofs can be hard to come up with， right， And you know， one。

 one of the the， the， the central reasons they could be hard to come up with is sometimes they're false。

 Sometimes you actually can do the damn thing， right， And then。

 and that that that that's kind of annoying when it happens， okay， but。嗯嗯。ButAllright， so， so anyway。

 so we'll， we'll we'll， we'll get our feet wet in sort of the first third of the course talking about。

 you know， models of computation and their limitations we'll talk about circuits and then finite automata which are like computers。

 but that are only allowed to scan the memory in one direction， just like from left to right。 Okay。

 and you know， the nice thing about finite automata is that we。

 we more or less completely understand them。 Okay， so， you know， there's a whole， you know， very。

 very elegant theory of them that was more or less completely worked out in the 60s and 70s。 right。

 I mean， you know， not that there aren't open questions that you can ask， right， but there's a very。

 very， very， very nice story， you know， and and it's very pretty and you know， and it's useful。

 you know， again， you know， you know， useful。 But you know， you know， it does。😊。

Get used in in compilers and， you know， programming language， semantics and， you know。

 also in computational biology， things like that。 So it's really worth knowing， okay， and。

And then we'll talk about touring machines。 and the theory of computability will relate it to Grdel's incompleteness theorem。

 You know， because those two were sort of born around the same time。 And， you know， they're not the。

 you know， touring's unsolvability of the halting problem and girdle's incompleteness theorem are not the same thing。

 but they're very related to each other。And you can actually use touring machines to prove girdle's theorem。

 We'll see that。 Okay， and then we'll we'll start talking about complexity theory。

 So what changes when you put in a notion of efficiency。 You say。

 you want your algorithms to terminate within the lifetime of the universe。 Okay。

 and then that will lead us to you know the P versus NP question， which you know。

 I'll assume some some of you have heard of but it's a very if you haven't， It's a。

 you will have heard of it by the end of the course。 it's a very very big question。

 and we'll talk about NP P completeness。 Okay， which is one of the you know。

 the major things that we do know about the P versus N p question。 Okay。

 and we'll see how to take you know a huge number of problems and say even though we cannot say for any one of these problems。

 whether it can be solved efficiently or not， we can say that you know。

 these are all the same problem， in some sense。Any one of these can be solved efficiently than all the rest of them can be as well。

 And then we will talk about， you know， what changes in the theory of computing once we incorporate the notion of randomness and we'll。

 we'll circle back to cryptography if we have time we'll do a little bit of machine learning。

Which is another application of these ideas。 And then we'll do a unit on like four lectures or so on on quantum computing。

 Okay， so any， any questions about， about that about， okay， so， so I guess。All right。 alright。

 I'll just let you out early。 alright， and。on Thursday， we will talk about circuits。 Okay。

 that will be our first model of computation。Hey， yeah。 yeah。 sure。 taking both this plastic 604，6。

 I'm wondering how people Oh， no， they， they don't。 They're， they're different classes。 Oh， yeah。

 what， what， one thing oh， oh well， yeah， one thing I， the other thing I was gonna talk about is 6，0。

4，5 versus 6，8，40 is a question a lot of people have。 But so， so 6， so， so 6，8。

40 does overlap with this class。 Okay，😊，Yeah，1840，4 does overlap with this class。 But， yeah。

 that's the graduate level version of this class。 And compared to 6，0，4，5，6，8，40 has， I think。

 less breadth and more depth。 So it won， you know， it doesn't do crypto。

 It doesn't do quantum computing， it does a smaller set of topics。 But those topics。

 it does like with greater rigor。 And， you know， in more depth。

 And it goes into more depth about space complexity， for example。 So， you know。

 if you just want like one theory course that will expose you to， you know， as much as possible。

 than I'd recommend this one， if you want something more mathematically rigorous， I'd recommend that。

 you know，184，0，4， if you want。😊，You know， if you really， really love this field。

 then it wouldn't hurt you to do both。 Okay， and， and， you know， and also。

 if you really love this field， then I would strongly recommend doing both this one and 604，6。

 because they， they they， they， they have only a very， very small overlap。60，4。

6 is mostly algorithms is mostly figuring out how to do stuff。 You know。

 And this class is mostly trying to， you know， prove what are what are the ultimate limitations on what you can do。

 So there're sort of the compliment to each other。 Okay， yep。😊，Yeah。

 it matter if it's the second or third of the。 it doesn't really。 not， not， not， not， not， Yeah， not。

 not that much。 I mean， if you have a choice， get the more recent one。 But， you know， yeah。

 but it doesn't matter that much， yeah， hey。Yep。Absolutely， of course。

And also this one the same place。 Okay， it's one form for each school。 All right。Thank you so muchep。

Okay， there you go。 Yeah， welcome， yeah。Hey。Yeah， sure。 Of course。 Let me take my microphone。いいこえ。

about。
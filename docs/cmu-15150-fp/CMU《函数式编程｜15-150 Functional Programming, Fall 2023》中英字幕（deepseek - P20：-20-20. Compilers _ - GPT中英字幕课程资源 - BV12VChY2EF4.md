# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P20：-20-20. Compilers _ - GPT中英字幕课程资源 - BV12VChY2EF4

Anyways， welcome， welcome to the first of our special topics lectures This one is gonna be on compilers before next week's and by next weeks I mean this Thursdays on program analysis I'm glad everybody can make it I am extremely T I got here three hours ago off red eye from San Francisco but I actually I flew back for the weekend to my work because we had a hack week this week and I told everyone I'm going be here today and then fly back because I got a class at 11 a tomorrow and then one was like say and I was like no I got to teach so you're welcome but anyway we're talking about compilers today we've done a live stop of compilers in this course so far we've gotten type error messages we've gotten all sorts of crazy zany stuff from the SML and J compiler and I've said a lot of random nonsense related to the compiler will do blah the compiler is blah as if the compilers an anthropomorphic entity today we're gonna try and demystify a little bit what exactly the compiler is so that you can at least think about it if not implement it and I just say some of you are ready at this point。

😊，To try to implement a compiler now， if not within the next like year， okay。

 because the stuff that we did in this course exactly relates。😡。

But let's get started so this lecture sure like so many before it is going to start with a story and this story is a true story。

 it's also a scary story， but I'm going to pique your interest by telling you this story the story of the world and of programming languages so。

😡，Here's where we got on the docket today I'm going to tell you a story where we're going to talk about the theory of compilers and then how we can implement a compiler and this is kind of like a rundown of the 12 weeks of content or 14 weeks of content you would get in 154 11。

 which is compiler designed， which is one of my favorite courses at CMU。

 but if you like the content this lecture definitely take that course。😡，'llBut back to the story。

 so let's start shall we the history of programming languages。

 well actually I had to look on Wikipedia for quite a bit to figure out this story myself。

 but let me tell you a story。😡，One day in the farar past a long time ago。

Programing languages were not real。Programming languages did not exist。

And there were an idea you see people thought what if I had actually something most people didn't think。

 but some people， very smart people were like what if we had programming languages。

 but they still weren't real okay， there weren IDEs there was no VS code。

 there was no standard ML I know this is the horror part of the story okay。😡，And once upon a time。

 computers also were not real。 Somehow that bothers me less than the programming languages part。

 computers were not real。 There was no Twitter。 There was no， no hard drives。

 There was nothing that you could do。 Everything you wanted to compute。

 you'd have to do by hand by a simple machine。 No calculators， you know。

 when when your math teacher said when you grow up。

 there's not gonna be a calculator in your back pocket。 Like back then they were right。 Okay。

 But in this case， the history of programming languages takes us back to the 1800s。

 when there was a loom， which is a thing that spins cloth of some kind from what I gathered on Wikipedia。

 Okay， and it leaves a certain pattern based on punched cards that you would put into the thing。

 a punched card， a literal card with holes in it Ped as like the one that you get at the yoga shop on。

P and yourt place， the Fourer place I can't remember the streets name but like that place okay for a discount okay and this was an early example of what we could consider programming。

 which is I'm going to take this thing and then put it in and it'll adjust its behavior based on the data I put in input output programming okay。

😡，But then a little bit later， Aidda Lovelace and Charles Babbage worked on something called the analytical Engine。

 raiseise your hands if you've heard of these people or that project。😡。

Wwhich is what we consider to be one of the first general purpose computers this actually has very little very little relevant standing thing I'm going to say today。

 but I wanted to give wanted to give ups to my girl Ada and Charles all right cool so we have these sort of like simple machines but no no computers all right。

😡，But then by the end of the 1900s， this guy called Hermann Holliith with a very alliterative name had this idea that maybe we could put data in a machine via a punch card and use it for data processing with the US Census like keeping records and doing basic math and he found of this company called the tabulating machine company to use punch cards for data storage and then he realized that that name sucked and then they became IBM international business machines Corporation which were big players in the original history of programminging languages and computer hardware massive players a couple of decades later。

 this guy called Conrad Zeus comes out with something called the Z3。

 which is an actual programmable electrical computer albeit still via this punch card idea I have to keep a literal card and let me walk you through what that looks like right so。

😡，Some people say， oh man， programming and SNL sucks the error messages are terrible。

 I don't know what I'm doing。 Why do you have to pick such a terrible experience for me to program in You know nothing。

 I also know nothing but from what I've gathered onlinere going put this scenario in your head so you're a talented programmer in the 19th century or the 20th century and you're one of the first programmers ever。

 ever， ever and what you do is you take these cards you take these cards card suck and you punch cards with them you punch holess in them via the special card punching machine。

 but it's only you have a room and you got to use it and you got to reserve that machine so you punch some things and if you make him typo by the way。

 you got to start over if you punch the wrong place you got to start over and then you finish it and then okay when me try to run my program well now you got to walk all the way over to the other room wheres no air conditioning stand and line tap tap with everyone else who wants to run their goddamn code and by the way you haven a stack of these you have a stack of them you have all these cards and if you mess up on any one of them。

You're screwed and if you drop the whole stack。Well， then goes you're weak All right。

 you got nothing left， I'll pick it up after the lecture， it's fine， No， you can't so。😡。

My point being， if you want to complain to me about standard Mel of New Jersey， all right？

Don't but second we also this is kind of motivation for that okay so thinking all the while while while I'm on the floor。

 you know picking up my my punch cards programming languages are still not real。😡，Oh my god。

That's the end of the lecture， no not， so in the 1940s now we could write programs in assembly language。

 whos heard of assembly language， raise your hand。😡。

So okay and now now put your hand down if you're not in 213 or have not taken 213。 All right。

 great cool， which is like the bar machine code that can be understood by computers。

 you've probably heard computers only understand zeros and ones。 that's kind of true。

 They only understand this thing called assembly language， which is very。

 very hard to read and here's an example。 Okay， so like I might write an assembly like syntax。

 that's like add r one to R2。😊，And I compare on the result of that to zero and if it's zero。

 I jumped to 0 x 00067 A3 EF otherwise， you know clearly I must go here if I didn't go there。

 I go to blah blah blah，lah okay and the point is that this will be everywhere in your code all right and I'm sure some of you have read such assembly okay so this is what people were working with when they didn't have punched cards。

😡，That's okay， that's better， it reads like human syntax， that's cool。

 but what's the first thing I said to you on the very first day we can do better， let's do better。

 let's program a program better。😡，So I'm going to quote Wikipedia here that I found online。

 but it was eventually realized that programming and assembly language required a great deal of intellectual effort。

 citation needed。😡，The only people that would put citation needed there are people who have never had to write assembly。

 okay， to be clear， so you know don't trust Wikipedia， but what's the point？😡。

So program is spent like hours the days they pour over these cards or these symbols over assembly and they want to write hope but they have to think about everything that's happened in the program up to this point。

 where did I tell you on my first say imperative programming you have to think about the whole state of the program except now with assembly you can't even have a good mental model of that you have to know everything that's happening at every point and if you make an incorrect assumption if you make an incorrect assumption。

 there's no recovery from a typo， there are no ty errors。

 God cannot save you here okay assembly is no man's land。😡，And still。

Programming languages are not real。What？😡，Someone has an idea probably miserable people have an idea actually I don't want to give you a conclusive like this person did at first because that's actually not very clear but one person is John W Baus in the 1950s who was working for big IBM and he was thinking。

 you know this assembly stuff sucks this is terrible， I don't want to do that at all。😡。

What if I had a program that could take in？😡，Wait for it next that's human readable in a programming like。

 oh he means that word。😡，And then it could turn it into assembly。

And he called that for Tram and by the end of the decade。

 he had implemented along with a team of talented programmers。

 a program that could do exactly what I just said。😡，And that was the first four trend compiler。

And then programming languages were real， and there we are now。All right， thanks for coming。

So let's get into the theory now compilers， what the hell is a compiler All right。

 so very broadly I can explain it to you this way a compiler is a program that translates data from one form to another and that encompass is a lot of things。

 but usually when we say compiler we mean a compiler that turns text in a programming language into。

😡，Some other form， but usually assembly language， machine language for a computer on some kind of computer。

😡，SML and J， for instance that you've been using all semester is a compiler that takes in an SL program written as text like in your IDE and turns it into machine code that can run on your computer okay and you know there exist numerous computer architectures。

 we're going to assume that there exists exactly one in this lecture okay I don't care。😡。

Another idea that is kind of sister that is an interpreter。

 an interpreter is something that takes your code and then it reads it and it executes it directly。

 it doesn't translate it explicitly to something else in the process necessarily at least not visibly to you okay so these are kind of similar ideas。

😡，And the SL and J Reple that you've used in this course is also an interpreter， okay。

 but S&J is also a compiler。😊，And in S terms which I have to do， you know。

 we can actually have a tight signature for these things。

 so let's give a signature from what I'm talking about。😡。

Compile is a function and what it is is it's a this is not going to be a very illustrative type。

 but it's a function of string to string。😡，Takeickson。SML text like programs and outputs。

 like let's say assembly， okay， some kind of generic assembly。😡。

And then also we have this notion of run， which is a function that all computers can pre packaginging。

 but it takes in assembly language， text。😡，And it returns a unit because it just executes it directly。

 okay， so this would be assembly again。😡，has anyone done the thing where you do like C mod plus X like file name。

 that's what you re marking it as an executable and then when you do dot slash of that file path。

 you execute it， that's this you're running it， you're running that thing as code and also we also have this idea of Val interpret where interpret is going to take in the original SNL text。

 which is a string。😡，So SL text。And it's just going to skip the nonsense and is going to execute it directly and what we should have actually is ideally we should have that interpret。

😡，And you didn't think this is going to be 150 lecture。

 but actually I'm going to throw some 150 stuff in here。

 should be equivalent to the composition of compiling and then running。

Does this read correctly to everyone Like Does everyone understand understand what I'm going for here Yeah。

 in in theory， at least okay， in practice， there's a few things that send the way of that。

 But this is the idea interpreting and compiling and running very sister ideas okay。

And that's exactly what I just wrote。And we should have this okay but here's another way you can understand compilers and interpreters I am second Gen Chinese I always forget which ones which my parents are from China and I am a compiler for Chinese because when they speak Mandarin Chinese to me I have to translate it in my head to English and then understand the English which means that I have a lot of log time but I am an interpreter for English which is my native language。

 so you speak English to me and I can just understand you off the bat that's the difference between compiling and interpreting so some of you are compilers。

😊，嗯。😊，Thank you one that I always want to to get across to people that I think is kind of interesting is this idea that a programming language。

 you can implement a programming language in that programming language。

 raise your hand if this like makes sense to you。😡。

Becauseuse I think it's a very non obvious sort of thing personally。 Okay。

 too many of you raising your hands。 Put your hands on。 I think it's kind of not obvious。

 And partly it's because someone tried to explain it when I was like a freshman。

 and they explained it to me wrong And looking back like years later， I now know it was wrong。

 And I know why I was confused。 And now I'm upset about it。 So now I have to explain it to you。

 So there's something called P pie。 It's a Python implementation written in Python。

 the SML and J compiler is written in S Ml。 If you remember me complaining about the SML and J compiler。

 I was reading SML code for hours。 It's written in compile Sml。 and the Ru compiler is written in Ru。

 It's a very common thing。😊，Why can I do this Well you have to of separate this idea so let me use some notation we're going to say that compile subscript Lng is a function of type string the string which this iteration takes in code written in this language L and outputs assembly I don't know what this compile function is written in yet okay I'm just saying that this is our notation for that specification okay so compile SML is a function that compiles SML okay。

😡，But remember a programming language is an idea， it's an idea in your head。

 okay before it ever gets real before theres a compiler。

 so before John Bas was able to implement Fortranne he had this syntapse in his head he had this idea of what it should look like but nothing could understand Fortt at the time and there was no computer that could run Fort code。

😡，But we had this staff and this graph on the board on on the ground， we had assembly。

 and it turns out that with assembly we can write any function， any function at all。

 which means that， well isn't one function。😡，This one well， this one， this is one such function。

So if I have assembly， I can write compile_4t in assembly。😡，Now I have a Fortran compiler。

 I have something that can understand Fortran now Fortran is real。😡，But using this。

 I can now use my Fortranran code， my Fortran compiler to write anything in Fortn。😡。

Including compile underscore foresread。😡，So my point basically being that before you can ever implement a language in itself。

 you have to have a compiler for that language， you can't go back for infinitely。

 but because we have assembly， we can code this and once we have this we can code compile for trendren and anything。

 including forT， I feel like I'm losing some of you。😡，Yeah。Yes。

 that has to happen first and now now the computer is capable of understanding Fortran before you did that nothing in the world other than your head could understand Fortran but once you write compile fortran in assembly now you can understand the computer can understand Fort now that the computer understands Fortran you can write random programs at fortran like hellello world like Quicksort like。

😡，Compile Fortran again。You have to implement it twice。An assembly must be or something else。

 something else basically， yeah。That is I didn't necessarily say it like here。

 but that is in practice what it happens that's called bootstrapping if I bought how to choose today I give you one。

 you can bootstrap a compiler by writing more of your compiler and using the parts of the compiler you already wrote。

😡，Yeah， bootstrapping because you lift yourself by your own bootstraps right， yes， there a question。

 no you， yes。There are things called assembblers which can take assembly and like prep it for usage by the computer。

 but assembly is like very very close to like the point where you can like execute directly Yes I won't say that you can like execute directly like assembly is still kind of a lie but it's a very very close lie okay yeah。

😊，Cool okay I think this is interesting， it's not super important to probably what you came here for。

 which is how do I write a compiler so but I think that this sort of distinction between implementing the compiler versus using the compiler it's a very important distinction to have in your head raiseise your hand if you feel shaky on this thing。

😡，Okay， either you're lying orre all geniuses， let's go either way I win well actually。

If you're lying， I don't win。All right and yeah， so this is actually exactly what I just said。

 yeah okay。😊，So Py Pe SL andJ， the Ru compiler， they all worked the same Gta Venraom Bless his heart。

 had Python in his head in the 80s， actually met Peterta Venraam。

 I got to present to him because I did work for Python the type checker but Gi Bless his heart had this idea of Python in his head and it didn't exist。

 but then he took some language of choice and implemented compile Python in it let's say it was C okay and so he used C to implement a Python compiler and then once he had that Python was real computers couldt understand Python so then he wrote Python code to compile Python。

😊，Yeah， that's pretty much it。 that's all that matters。

 Okay cool that's all I want to say that's that's compiles from 5000 feet。

 Let's talk about how we are going to implement a compiler and this will take the majority of the lecture okay so let's say we right compiler SML is going to be written in some language and have type string the string where we take in SM text and compile it to assembly let's think about how we might do that and the way that this typically happens is a compiler will take a program as a string and translate it through a bunch of different passes。

 a bunch of different phases and then kind of like simplify and optimize along the way which is how we get how powerful compilers we have today where they can do frankly。

 quite magic of things Okay but we're going to go through exactly what those phases are。😊。

So before I do that though， why are we studying compilers in a class on functional programming。

 or rather why am I talking about it in a class on functional programming？😡，I always say this。

 even the most determined functional programming hater， okay。

 like like someone who's like a complete like bathwater like like they hate functional programming entirely like like。

 you know like。😡，好。那个。They we can deny that functional programming is incredibly good for writing compilers。

 by the way doesn't he's coming to work at my company to do functional programming in case you didn't know that okay so I win anyways it's very。

 very good for writing compilers that's almost like its purpose okay and partly because a compiler is just a transformation on data through a bunch of passes right and having tight guarantees on or you can't mess this up makes that process a lot easier makes it nicer and pattern matching and data type declarations we're going to find are essential for writing a compiler if you don't have data type declarations you're working like enums or something you're going cry you're going cry if。

😡，I do Iamp for this I'm gonna to say I was recruiting at Sanford like a year ago when I was in the bay and then I was talking to people and you know what I do is close to compilation So I asked them have you taken a compilers course and all of them like invariably they're like yeah like they kind of grown in a bit and I'm like why would you do that compilers is so cool what do you mean I go and I look up their compilers course online afterwards because I'm a doctor and then I find out that the Sanford compilers course is mandated in C++ and I was like that'll do it I understand now I understand the whole curriculum so no shaing on schools but also。

😊，Thanks， all right， so let's for rest of this presentation except for the last part。

 we're going to assume we're implementing a SMmL compiler and SML and I'm going to show you kind of like pseudocode okay we're not going to go we can't go through everything because that would be incredibly hard。

😡，Okay喂。2 minutes compiler implementation， well what are we going to do so most compilers have exactly the same structure and it'll look like this。

😡，I have lexing what happens is I take in a program let me do this on the board actually so I start with a program that's like text right I start up with a string and I need to somehow in part meaning to that so I take a string。

😡，And I turn it into something called a list of tokens basically if I'm reading a program。

 if I'm reading human language， I want to kind of think about the parts of it rather than the individual characters when you read English。

 you don't read like B kit no you read back like a word right you read the granularity of words。

 This is word separation in terms of programming languages okay let's separate each thing into like a semantically meaningful token right so this is called Leing。

😡，The next step is called parsing parsing is where we take this token list and we turn it into a syntax tree。

 I may have alleged to this earlier， but programs are just trees right as you saw in your midterm one。

 so a syntax tree is what we get when we do parsing。😡。

And then after that we translate it to well I'm not going to have room for this but we're going translate to an intermediate representation which usually takes some form of something that looks like assembly but it's not quite all the way to all the stupid physical constraints of the real world okay and I'll elaborate more on that later but we say like this is abstract assembly or intermediate representation and here we do a lot of optimization most optimization in the compiler happens here we stay in the IR for a while we have a little self loop and we optimize our code okay。

😡，And then eventually， once we think we're ready， once we know are finished with our optimization process。

 we say let's go over。😡，To real assembly okay， which is itself kind of a Rduuous process so these sort of phases。

 these edges I've drawn here are kind of what is of interest to us。😡。

And we'll go through all those in tandem or in。Okay， and I you know nicer as always。

 a nicer version of what I draw on the board is available on the slides okay。

 but let's start at the first step， let's go back to the beginning。

Leexing what how we do Leing so again。😡，Words， right， if I want to read a program。

 if I want my computer to read a program， and do you think I'm going to， I'm going to case on。😡。

Hashtag， F cons。Hashtag U cons hashtag N cons rests is this how I'm going to write my compiler no okay。

 let's try to do something better al right so generally the acceptedive practice is this is going to be our toy program for this first little part and actually it's so important to have this up I'm going to write it on the board and while I write it on the board I'm going to talk I'm going to filibuster because if I stop talking for a second you're going to lose interest and you're going to get bored but if I continue to talk while I write you will not get bored know actually I wrote a story about our senator who like read the entire Harryry Potter like on the on the floor because they wanted to filibuster if you didn't know what filibustering is from a social studies it's fine。

Anyways， I'm done with that we tokenize this program so instead of thinking about as VL blah bh blah。

 blah， we're going to link them together， we're going to。😡，Combine them。

 but separate them by the white space because in SMML as we know。

 we don't care about white space and SML right so what we're going to do that I already you that。😡。

So here's how it's going to run。 We're going to color in almost every single part that's meaningful。

 So V A and L go together。😡，One is it's a standalone minus is separate， these pres are separate。

 and you see I've kind of colored them here by what they represent numbers are red。

 keywords are blue。😡，Regular identifiers that could be any name are green and then like syntax like equals and minus those are orange and there's a reason for that okay and the reason for that is because。

😡，Well， because we're going' to have to represent these tokens in SML。😡，And in SL。

 here's how we might represent tokens。 It's going to be a gigantic variant。

 It's going to be a gigantic some type。 Okay if I have a token。

 I might be holding a token that's vow。 I might be holding a token that's fine。

 I might be holding a token that's type or it could be like can identifier in which case like I don't know what the identifier is。

 but I've got a string along with it that explains to me what it is or I might have a number where the number is 1。

2，3 bla bh， blah， bla associated data if I have syntax， know。

 I also have a variance for each of these things。's you might seem exhausting for you to do this。

 but like I don't know for SmL that's probably not more than like。

30 of these and that seems like a lot like in terms of a language that's actually pretty small okay this pain this cost to print by like writing this code is going to pay off when we write our lectureer when we write our parser actually okay do people see why like we could use this to represent an SL program？

😡，Separated by the white space we're guess getting rid of the white space by toadizing Okay。

 I think people are good do you have a question。😡，Minus？So this is a variance。

 So I'm saying that a token can be any of these things separated by bars。 It might be vowel。

 It might be fun。 might be type。 It also might be an identifier with a string attached。 so on and so。

 Yeah， we say no strings attached。 But in this case of I。 that's not true。 Allright， Okay。

 so after that， we tokenization process， we get this。😊，And here's why I picked the colors I did。

 I separated them by the samet that they correspond to。 So vows vowel。

 this should technical be8 of string X， but I highlightedlighted it because it gets really wide。

 I was trying to fit it on one side， but this is actually going to be exactly the list that SL will tokenize to if in our pro compiler okay this rather。

😡，Yeah。Because int you might think into is a keyword and it could be a keyword。

 there's a small syntactic difference which means that like I'm pretty sure we can use inch for other things like if you can rebd the name int but like a keyword messes up everything like you can't use fun as a name ever this is kind of like a stupid silly distinction I was graded on when I was in 10th grade computer science but like it doesn't really matter but there was a small difference between a keyword and an idifier。

😊，Do people see by this， given the type on the previous slide， this is an SML value。😡。

Lo a token list that correspondent。哦， ok 。That was it， that was lasting。

 I didn't show you how to implement it， it's boring。But we're going just skip that and move on。

 so pressing。So programs are naturally recursively defined。

 right and some people are like all always suspicious of that， so I do this okay。

 I say do you agree with me？😡，Do you agree with me that this is a program？😡，Yeah， yeah， okay。

 do you agree with me？Whats。That this is a program。Okay， do you do you？Do you agree with me。

That this is a program this I'm hearing yes， I'm hearing， you're saying was all I'm hearing is yes。

 all right， so， so anyways， this is a program it's recursive。 deal with it， all right。😡。

All your programs are recursive， that's the whole point Okay。

 and you can write finite if you can write finitely length programs like what what's the use。

 what is the use of you my parents also yelled at me for being finite Okay， so anyways。😡，Oh yeah。

 actually my example is funnier， if true and big， yes， okay， anyways。

 so this makes programs a great candidate for a rehesive data type。😡。

Let's do it well remember Op trees at least I'm sure some of you know Op trees we did on RPN right and we had we avoided the tree part explicitly。

 but if I had an arithmetic expression it might be corresponded to by this tree and what is that expression can anyone tell me？

😡，What's that。😡，Well that was not clear to me at all， actually。

 you need to audibly like it's hard to express view。No后然 was是。Okay， I。

My practice is I say one minus2 quantity plus3 and that makes it like more clearer where the limiters are。

 but yes， like note for you if you ever need to explain something like say quantity afterwards anyways that's this to people see why the plus is at at the top because it goes last one minus two happens first right the minus binds tighter so that's that expression and we see that this is just a tree Yes wow。

😡，Arithmetic expressions are just trees。 Well， what else could be like an arimetic expression and then possibly be benefiting from a tree like structure。

 Oh， by Joe。 Look at that。Programs， well， the next thing I want going to say is actually。

 this is abstract syntax。😡，The difference between abstract and concrete syntax is in my thing here I got parents yeah but there I don't have any parents I don't need them because the pers here kind of indicate to me what the tree structure is I don't need this pers to tell me because once I'm holding the tree I understand that there are parents here right so I don't need the pre that's why this is an what we call an abstract syntax tree it's not a syntax tree that has everything that was in the source。

 but it conveys the same essential information just in an abstract way so this is what we call an AST or an abstract syntax tree。

😡，Okay。😊，Wass that？Mic。Okay， thank you。😊，So the tree structure is what the trends were trying to hint at us at the whole time。

 so let's focus on the abstract syntax okay， concrete syntax is boring right text is boring。😡。

But we can do something very similar to this optre idea with programs。

 we're going to have an abstract syntax tree which shows me the structure of this program。

 so for instance。😡，This guy on the right here。This is going to be the same as the program on the left here。

 vow x equals that same arithmetic expression I just showed you。😡，Is the same。

Valdeck is going to be a node of a tree where my left child is my pattern I want to bind to in this case is x。

 it's a blue box of x and my right hand side is again。

 the Op tree I showed you earlier it's kind of like a refinement of the ideas's not too far from the Op tree I just showed you and again like what do we get rid of we got rid of the pre because we didn't need it to indicate the meaning we also got rid of the equals because the equals doesn't matter like once we have the equals oh。

 I understand the reason it's there is so I can know where my pattern and my expression begin and end so the confidence syntax tree boring abstract syntax tree based we get this and we get rid of the we get rid of the equals and we get rid of the pre all right。

😡，Does everyone see why like we don't need those things？有。Cool， all right， you don't need them。

 you can move on。Okay， so for the running program I've got， which is that guy。😡，We can get this tree。

That his idea。At the top level of any Sl program， I need a certain number of things called top decks。

 top level declarations。 So I'm saying I have two。 My first one is a Val deck where my。

Pattern is x and my right hand side is  two minus1， yeah。😡。

And then my right hand side well my next thing and my next top deck is a upon deck it's upon declaration。

 I'm using shorthand here where my name of my function is F the pattern argument I take in is a typed pattern where I type X at int right sorry that should be Y my。

😡，And then I add5 plus x as the body of my function now do you see why like all these components through y colon and inch5 plus x these are really just subservient to the greater fund declaration right does everyone see why these are yeah。

😡，V样。Well is that doesn't even work very well because this is going to be a literal a literal SL value in like a second here。

 like the lital okay， anyway。😡，Like， like。So the SNL code。

 how we might represent that AST looks similar to the CO problem that was on your homework。

 it looks like this。😡，And then I'm writing a lot here， okay， but here's AD and EP is a type。

 it might be an int with an associated int， it might be an identifier with an associated string。😡。

It also might be plus of two expressions， right？😡，A declaration might be a Bde in which case it just has a pattern and an expression right a fund declaration is just a fund with an identifier。

 some number of patterns right because I can take in any number of cur arguments and then on my right hand side I have an expression here。

😡，And then the pattern can itself be like， you know， just a string or it could be。😡。

A list of patterns because I have a twople of them yeah。

 so do people see roughly like this kind of its like your understanding of SML there are some imperfections。

 but it doesn't really matter， the point is that we can write this structure and this is a tree that denotes the structure of an SML program and this is what we're going to parse to thats。

😊，All right so that's the thing that we're parsing to at the end of the parsing step。

 we translate it to this abstract syntax tree， okay but no equals， no equals， no vow。😡，No， plus。

 I don't care。 They're just there to get me to the right tree。 Okay。

 the syntax guides me to the tree， okay， uncle。😡，All right and I want to talk about implementation a little bit an abstract syntax tree we can get this via something called a recursive descent parser remember mutual recursion well mutual recursion comes in handy for a recursive disscent parser it means that everything every EXP declaration pattern。

 all these types will have its own function and its job is to parse one of these from the list of tokens I'll show you exactly how that looks。

😊，So。Here's the idea I'm going to have a parse Pat takes in a token list and then munches off a pat from the front and then returns to me the rest of the token list I'm going to have parse expP which does the same it munches off an EP and then returns to me a token list same with X okay why does it return to be the rest of the token list so I can continue so I can keep parsing the rest of it so if I add vow X equals2。

😡，When I call pars Pat， I'm going to parse this guy with pars Pat。

And it's going to return to me the rest of the list。

Of tokens such that I can get the equals and then I can call H's EP on this guy as well。

 okay it's actually very much like the regularg expression match that you saw remember we bit off a string that corresponded to a rex。

😡，Similar things happening here but we're binding off strings that represent programs or ESpss or paths yeah so if I if I'm doing like like a vowel declaration like do you care that the equals is there once you know that it's a vowel declaration because the Val declaration if you think about the information in that I really just care what am I binding I'm binding。

This expression to that hat， I already know that I'm doing the equals because in the type Valdeck is called Valaldeck。

 it already it tells us we're in a Valalck。😡，But the patent and ESP aren't things that we can get from the name。

I guess you can also say that Vdeck implies with these things existing。😡，交正能力哪点 yeah good question。

Okay， heres and here's how the SL code looks and its a little scary， okay， but welcome me here okay。

😡，Pse deck we're parsing the declaration from the front of a token list that means I case on my token list Ts。

 I got to hit back two things I give back the declaration I munch off and I give back the token list Well if the first token is a vow doesn't that mean I should be parsing a vow declaration so if the first thing is a vow。

 what do I do that means I'm here I'm here now。😡，I'm here， I pose this and now what is Ts2 this？😡。

Is Ts2 yeah and then what do I do oh well I got to get a pattern。

 but I don't know how long a pattern is， so I got to use my parse Pat to parse it from here。😡。

But after a pattern， I always expect to see in equals。😡，So I go and I use this expect function。

 it'll basically munch off and equals from the list and all the while we're getting new and new newer and newer suffixes okay and then I parse an EP and I get Ts4 okay basically I'm saying get this from the bow。

 then I get Ts2， get this and then get Ts3， take this off， get T's 4。

 and then take this whole expression off and get T'。😡，Maybe I was off by one there， okay？

But once I have the patent in the XP， I can pull it into that variant I showed you the Valdeck。

 and now I have my declaration， I'm holding it。😡，And I have to give the rest of the list once I munch off everything corresponding to this Sp declaration。

 I have to give you everything that comes after that's just my invariant。😡， yes。

Doesn't need to actually I think cleaner if it doesn't yeah separation from concerns but your question。

 yes， I think people are confused here， please ask questions。

Me looking in this side of the room does not indicate that I think that this side of the room is more confused than this side okay to be clear。

 yes。It says declare all these and then be that return that。😡，And that's yeah， yeah， yeah， yeah。

question yeah and that dialal deck is a variant of this type deck yeah okay。

 any questions on this item。😊，要。😡，We chunked it into bits for tokenization。

 but once we if I had like two plus three plus four in my tree， I want to see these together。😡。

We break them part into tokens so we can put them back together at parsing。

Yeah we're stitching on the other now but good observation like when I call parsy it's exactly because this thing could be unboundedly long it could be arbitrarily long right it could be two plus three plus four plus5 plus6 plus7 so on and so forth right that's why you need to call a different recursive function because that function pre condition or post condition it parses an expression。

So once I get the expression， I'm done with the Valeldeck。

 then whatever comes next can be another declaration， maybe， could be a structure。

 could be a Valeldeck， who knows？But all I'm saying is that once I see a vow I'm hard committed to parsing a vow declaration because what else could be next that's the reason why keywords exist because once you see a keyword you're like oh I see font or type I know what I need to parse text it's to tell the parser what to do once you appreciate pars you appreciate why some languages have great syntax I think okay yes。

😡，It's returning the tree correspondingbin to the expression and then whatever comes after， yep。

 yeah yeah， okay。There was something I was going to say about this and I can't remember。

 but this can look scary， but if you look at it， it kind of should just look like the declaration like the structure of the syntax right what does the syntax look like it looks like that comment I left up there vow。

 and then a Pat。😊，Equals and then an exP， right？And that's what the code exactly is doing here。

 It says， give me a vow。 it says it says like in a cheerleader voice like give me a vow。

 give me a pat， give me equals， give me an EHp。 and then it gives you back the tree。

 That's what it does。 That's literally what the code is doing。 Okay it reads naturally to me。

 it takes a little getting used to。 But I'm going to tell you like this is very。

 very boring code okay so boring actually I have a different side of sentence。

 But most lectures and parss nowadays or actually autogene like this code。

 you just write we've written programs that will generate this code for you from a specification of the language。

 So that's how boring this code is okay。😊，Yeah don't feel bad about that right you can call those Lexer and personal compilers。

 it's confusing。😊，啊 okay。😊，I sure show you this earlier。

 but basically here's the idea right when I have a token list which is Blue it's going off a little bit longer parse deck munches off this guy from it but it stops right before the fun it says give me a vow。

 give me a pat， give me an equals and then pary XP goes a little bit further that it stops right here and then we iterate the process that's all it's happening。

😊，Forgive me for spending a little bit longer on this this is a large portion of what my work is I deal with the front end of programming languages。

 so parsing syntax tight tracking like all all my jam。😊，Okay， all right， let's move on。😡。

I have even more， even more pictures I've neglected to show you but parse pack gives me back this node with the X and then par Z Xp will give me back this syntax tree of the equals and I just stitch them together to return the final value of parseec if you want to visualize it that way my Proive calls give me nodes and I stitch them together once I want to return。

😡，All right， blah， blah， blah， parcels are boring， that's what the side says。

Okay but once you have ASTs you can do everything interesting the syntax tree gets you away from the shackles。

 the feathers of the concrete syntax because once you have a tree you now no longer need to think about stupid things like oh is this nested inside that like oh should I visit this before that oh oh is there a pre here no because the friends are gone only the bare meat of the program are left so that means what we can do is we can write programs that transform ASTs to other ASTs or return things based on ASTs？

Sree functions， okay。Compilation is nothing more than transformations and operations upon those trees。

 okay， for instance。😡，Was that asked about， type checking is a great one。Okay， so so's talk of this。

 talk this before I do that， look at this。😡，Iith have the data type tie representing types。

 it's one of three things and possibly more ints， strings and reels。

 these are constant constructors I'm just using syntax you've seen before yeah。😡，No。

EXN is the only sensible type， that's actually literally something we yeah， anyways。

 there are a couple variants， including int tie， string tie and real tie Okay。

 if I wanted to type check an arbitrary expression that's like the one I showed you earlier。

 here's what I can view。😊，EXP is a type with a bunch of constructs I showed you like two here are the two the other cases I don't care about if I have an int。

 what is the type of an int it's an int tie， right？😡。

But what's the type of plus of E1 and E2 what's that rule I gave you very early on in this course。

 I told you something like，😡，If E wanted to say inch。😡，And E2 is a type inch。😡。

Complies that E1 plus E2 is a type n yeah， on the very first day we did this。😡。

That's actually exactly what this is saying。 It's saying that if I type check E1 and E2 individually。

 and I both of them， I get int tie。 Oh， that means the type of my plus must also be an int。

 but also the Sml has a stupid thing。 So obviously showing you into the Sml compiler。

 This is a stupid thing I've been complaining about all semester。 something isomorphic to this。 Okay。

 if there's a line of code in there that does this。 and it's infuriating。 Okay， basically， it says。

 oh， also， we can type check it at real and real and give back a real stupid。 It's terrible。😡。

But I realize the syn like the data types are new， the syn is old。

 this is just a recursive function on a tree folks， right？😡，Yeah。

No this we are currently verifying the types right now parsing is capable of of parsing things like one plus pi it willturn to you an AST。

 but it's on us afterwards so look at this AST and be like yo， what is it you enemy garbage。

 what is this？😡，Essentially that's what this is doing yes yeah but the point is that if we can type check the whole program。

 we can attach the types to each node， I didn't show that here or we might just like be like。

 yeah looks good to me and then continue on because once we pass the type checking step we're like good。

😊，No， no type errors。Yeah again this is a very much a toy implementation I've simplified things very much so I hope that you guys can follow along okay but if you look at this recursive function on a tree ins return ins plus returns plus blah blah blah things okay all right let's move on。

😊，对。So type tracking is just one thing we can do on ASG， but also some people do things like this。

 some people do kind of silly things and some of those people are some of us some of the time。

 but sometimes that's fine okay and the point is this。😊。

What on God's green earth would possess me to write this？In my SL source。Why do I like this？

Why should I write this？Yeah。That's the only reason I will accept why would you do this and like like in general if I'm doing this。

 probably what I could do is this， I could change my SL text to be this。😡。

Or my compiler could be a real smart homeie and do it for me optimization。😡。

And often optimizing this is going to be just a tree transformation。😡。

So I want to turn v deck of x equals， I'll read it up for you okay。

 this is what it says it says v x equals 2 minus-1。

 okay I want to change this to v x equals1 that's all I want Okay how do I do it？😡。

It's called constant folding， I'm going to write a recursive function on a tree。Okay。

 I have a lot of shit to say here。 Okay， point I was gonna to say was basically like why should we simplify 2 -1 because you're like。

 oh， it takes constant time bla bla b which is actually a good answer in this course。

 But in the real world， optimizations are going add up if I can simplify an expression。

 that might lead me to further simplify expressions Like if I can simplify one-2 plus3。

 if I simplify this now I can simplify this。😊，ItDoesn't matter so much at the source sex level。

 but at the assembly level， this stuff adds up， okay？😡。

Computers also repeat themselves like all the time， if you are in a for loop。

 you might run like billions of times and if you shave off a nanosecond that's going to add up。

 I don't know by how much I can't do the math in front of you。

 but it's going you're going to get some amount of time out of it okay。😡，Yeah， you know。

 adjust the exponent by a couple and if you have less operations。

 you have less float in your code Okay one real constraint is like the size of executables and this was more of a problem back in the day but you don't want to ship like a 10 g be executable okay no one's going to be able to download it and no one's gonna want it okay if people people won't even wait 200 milliseconds to look at your web page what makes you think we're going to wait five minutes to download your file Okay so larger file sizes are bad and also more instructions are bad means you run less fast so let's do some optimizations because it'll help us a lot。

😊，Here's how we might implement constant folding。 It takes in an expression tree and gives me back an expression tree。

 Okay， if I have plus of two ins， and this must mean I have two ins， like in of I1 plus I2。

 That's what this means。 I1 plus I2 must be what I just read in this tree。

 I turn to in of I1 plus I2。 If you believe me， this will type trick okay。If it's minus。

 I do the minus， if it's div I do the div， okay， and this is how I simplify。😡，Yeah。Usually yes， yeah。

 we don't want to change it before we touch up yeah。Is this good with that one？

Why did I ask you that， why did I ask you if this is good with everyone？

It would't be if it wasn't completely utterly wrong， oops， oops， oops， all right， here's the problem。

😡，This problem hungryary crash。If I'm trying to compile a program that has did by zero。

 right I want my compiler to still let me compile it， it'll run a runtime， it'll crash。

 I don't want to crash while I'miling it。😡，My compiler should never crash。 That's on me。

 So let's not do that。 Okay， this is unsafe。 A compiler whose job is always to terminate。

 always to give you an executable unless you do something done like don't type check Okay。

 but this is a perfectly valid Snl program， right。😡。

Minus other parts I need to make it a real SL program Okay。

 so what we can do is we can add in this clause here。😡，If it's zero， don't do it。

 we guard the div by zero。😡，All right， I'm going to give someone a chance to say what error number two is。

😡，Yes。It needs to call itself because if I have something like， I think I'll give oops。😡。

If I have something like this， this tree right here。😡，This is plus this is minus of。

Two things that are not ins， right， you agree with me？Which means that in terms of this function。

 where does that go？😡，Wild card， we get wild carded out all right straight out。

 so what we need to do is we need to fold this guy and then fold recursively。

So we're going to add this case in and we'd actually have to do this for every single node of our syntaxtry like if we had a bunch of expressions that are not these we'd have to keep calling it recursively I'm going to tell you right now like in practice there are techniques and functional programming that mean you write like not even this okay you write very。

 very little but I can't show it to because this is kind of advanced but I'm basically motiv you you don't have to write this but this is how we would do it okay we forward our arguments。

Okay， and we need to do it for every construction in the ESP type。

 but this is how you write a recursive function that does constant holding okay it's just a recursive function on the tree and that way when I write stuff like this。

 actually the compiler will understand that this is actually just two。😊，Okay， any questions on that？

Recursive programs， recursive functions， yeah， recursive solutions， yeah。😊，But。

Because if I have a plus， these two things might not be ends。

 so I have to constant pull this guy first。😡，And call it recursively because this thing you got to fold too and that guy might have children that you got to fold so on and so forth。

 you got to keep going all the way down because with the program there's no end， there's no stop。

 not always。😡，Other questions。And I'll make it to the high level， it's fine。Okay， so this is okay。

 but also like how many times in practice do people write this in rationall code okay when they're not teaching 150 like not that often so like this is kind of silly optimizations usually happen I said at the assembly level。

😊，So we're gonna to go there before we get any closer to this kind of thing。 Okay。

 I spent a lot of time up here。 I like it。 We're gonna spend less time here。

 but I I'm just giving you the concrete idea。 Okay。

 if you come out of this knowing like vaguely what a compiler does， I'm cool with that。 I'm okay。

 if you don't remember any of the code。 I just want you to get the idea so our generation。

 we're gonna go from the syntax tree to what's called abstract assembly。 Basically。

 it's gonna look like assembly。 but we're gonna assume we have infinitely many variables。

 In practice， we can't do that when we get to assembly。 Okay。

 but we're going to assume we have infinitely many variables。 things called temps。

 places we can put data。 Okay， it's essentially very， very limited programming language。😊。

So I generation and then the optimization， let's do it。😡，So abstract assembly looks。😡。

So for the rest of the lecture， we're going to be in a pseudoPython variant because it's actually very。

 very hard to describe what SNL does because it offers us a bunch of nice things and so I need to go to a language that has less nice things because it's easier to compile。

😡，But Python here， we have F which takes an Xy and then apparently x again。

 but that was supposed to be Z， and it returns to me the sum of all these things。😡，In assembly。

 here's how it looks。😡，In abstract assembly here's kind of how it looks I have a temp T1 like a place just like random name and I assign it to Y plus Z right because that's the first thing to happen。

😡，Then I assign T2 to be x plus t1。😡，And then I returned T2 yeah the reason I have to do this is abstract assembly doesn't allow nesting。

 we want to get as simple as possible， one thing at a time。

 so plus can't take in two expressions plus can only take in variables。😡。

Plus can only take in like like things that are already data okay this is just a restriction we're placing on ourselves because this is real assembly logbes we're trying to get closer to assembly so we have to unfold and we'll notice that actually this makes our evaluation order very concrete it says first do y plus C。

 then do x plus that then return that。😡，If you squint your eyes and you're really on top of it。

 this should look to you like CPS， but if it doesn't， then it's okay。

 it took a few years for me to get it。Um， but the point is that it should look very specific like like like we're doing things very explicitly。

 okay？One at a time， no nesting all right， what was my putnot saying here Okay yeah， all right。

 I read the footnot I as I read my presentation。😊，This is fine this assembly here is fine for things called straight line code straight line code is where you don't jump around you don't have an if you don't have a while you don't have any jumps because it means that I go from this to that to that but how do I express in like linear order like via a line of instructions things like jump there and bh without go tos okay we're going to have something called a basic block and let me。

😡，Let me draw you a picture because I think this going help we're going to separately think of each sequence of straight line instructions as its own block that means that if I have like T1 gets1 plus2 and then T2 gets T1 plus3 and then at T1 right this was an an uninterrupted stream of instructions but if I ever have the case where I say actually like if T2 equals zero and this is I'm ammenting syntax。

😡，Theres two scenarios， either equals 0 or it doesn't。

 but I'm going to have to express that in my basic blocks。 If it's equals 0。

 I go to a different block than if it's。😡，Not equal to zero。Because this is a branch and logic。

 I can either go here or there so I can't just have it be a block okay this will make our reasoning simpler it's called a basic block and in general this is called a control flow graph okay again ideas。

 ideas。😡，Right so for instance， let's take this random function okay， F of x。

 if x is true I return f of x again， otherwise I return f of non x and yes， this looks forever， okay。

 it's fine。😡，I set x equal to true and then I guns away， I go straight or it。😡。

What should I say about the control flow graph of this guy well I think I'm not going to draw it up for you because I have better pictures but here's the idea right when I hit an if than else I have to branch I have two possibilities I get two blocks and when I eventually return from my function I just end but also when I call a function that's also control flow I call a function and I jump somewhere else okay so here's how I's going to look。

😡，And I've colored for you the constituent parts that correspond to each other in the hopes that this will make more sense to you。

My my entry point is down here right because I don't enter the function until I call it I start up here。

 I say x gets that's true， sorry if it starts hard to see X gets true， then I say Y gets。😡。

Calling F on X， Okay， then what happens is I jump over here to mystery land and I go to this orange block。

 which corresponds to my if。😡，Now that I'm in the if I use this command called CMP doesn't matter what does。

 but basically I'm executing this comparison， if the comparison is true， I go to this red block。

 otherwise if it's false I go to this yellow block。😡，But also。

Oops this should go back to both of you should go back here basically sorry。

 there should be an edge from here to here if I ever call up again。

 that means I have an edge back to CM， I have to go back to the CM so in terms of like actually how I'm evaluating this I say X X X I say X it's true。

 I call it， I compare it， then I go to the true case that's here。😡。

So I go here and then I return call of X， so I go back and it turns of actually just staying here the whole time。

 but in terms of the control flow graph， like we could conceive of a world where you could enter here。

😡，If I hold F with false， okay， I'm just displaying how this stuff happens。😡。

I don't need you to get the motivation behind why we're doing this。

 but'd like you to understand how it works yeah。Then then what？

This is just a different presentation ofottos this way we can say like a nice property is that every single instruction in a basic block if you're in a basic block。

Everything else is guaranteed to run versus if I left go tos right if I said like blah bla blah bh blahh go to a blahh blah now I have to like help myself block before I get to the end of the basic block we're just doing some preprocessing to save ourselves the trouble later so that when I get to the end of this I know oh yeah。

 I have one out edge I definitely go here。😡，But here I have two out edges。

 so I have to think for a bit I CMP do to do it this will make our analysis a little bit later。

 a little bit easier okay。😡，But what's something that you noticed about the CFG why I kind of already pointed it out to you。

 okay， oh well， I pointed out to you the fact loop， but also this is true。

Isn't it true that any way we go， we end up calling F？

So like even if it were true that like we inverted the thing here。

 it would still be an infinite loop because we always loop because there's a missing edgeop and no matter what。

 I always end up looping forever。😡，That means that once we have this。

 it's actually quite easy to write a program that can be like， hey。😡，This is an infinite loop。

 This is， this is something you should not be calling Have you ever done that in like a Python IDdeE。

 like you'll like write like while true and it'll like gray up the rest of your text。

Because it knows that you're in an infinite loop， and in fact。

 I would be surprised if it didn't do something that was pretty much just this。

This is the simplest way to do。Okay same thing with like a function that loops forever maybe it'll complain at you'll be like oh this function never returns okay so this is the simplest way that we can do something like that okay that's the whole point here all right。

😊，嗯。So SAC analysis is easy。These are the two callss to F， we always end up there。Okay。

 are people following me here？Okay all right。But controll graphs are also pretty handy because they let us know even more importantly than when an optimization can be done is more importantly when can you not do the optimization because when does an optimization become not an optimization when the compiler writer got too eager and move something where you shouldn't have or they shouldn't have and then you mess up and you're doing this instruction when you shouldn't have had to the problem with compilerrs is we have to produce an equivalent program we have to produce always in any optimization any simplification set the same program if you change anything about the behavior of your program and your compiler your hose no one's going to use your compiler I myself will write you an angry letter okay don't do that。

😡，So let's look at another one and I think this one is actually easier to understand even though it looks scary。

 here's the point right， we're in the body of this function okay we enter at yellow。

 I set red is equal to zero。😡，And then I have to go to the while okay at the while。

 I compare res with numb and there's two things that can happen here rather than's one thing I can happen here。

 I have to enter the body of this or I go oh yeah have two things sorry either I return if it's false in which case I go pink。

😡，Or it's not true， or sorry， it is true， in which case I go here。😡，Cool。And then once I'm here。

 well I have another if I check whether or not this number is even so I you know I have to compute it separately。

 I compute res modd2 and I check whether or not it's equal to zero and if it's true I go orange。😡。

Otherwise if it's true I go green okay and then once green and orange finish， I'm in a while loop。

 by the way， so I got to go back to blue， I got to compare this guy。😡，Okay。

 does that intuitive explanation make sense like I'm just I'm reading each to you what this code does。

 but reading what that code does also induces this structure here。😡。

It tells us this is what the code's really doing and depending on deciding which edge that we pick like I don't care about that like don't concern yourself with that okay but this is what the graph looks like okay cool。

😡，Hmm one thing I'm wondering here is what can we optimize here？😡，Anyone have a guess。

 what's like a big computation I'd like to potentially optimize？😡。

What's something I'd like to optimize maybe it's a better question like something I'd like to not do a bunch of times。

 imagine this while it runs a million times yeah。mind too。So reslon2， yeah。

 but except for the fact that res is being changed， so here's the thing right exactly。

This control is going to be very helpful for us because you might think let me sort the res and if you move the res up here。

😡，Well now you've got a wrong program you've done something different than what the original program said。

 so the real reason we have this is so we can know when is it not safe to do this optimization what I had in mind was basically I wanted to move this guy。

😡，20 times numb because I don't want to keep multiping by 20 also the numb I'm pretty sure doesn't change yeah it doesn't okay。

 so I have a few candidates here。😡，What if I wanted to optimize out this guy 20 times numb， well。

 I have a few choices？😡，I can insert it out of the function entirely。😡，可来。😊，Why？😡。

That's out of scope now， so I can't put it there， okay so junior compiler Red we're figuring it out。

 we can't put it there。😡，And why did I read that out， I don't even go。Oh， that's probably a mistake。

 I don't know， I made it this morning， by thewise， I could put it here。

A we go with this so instead of I made this temp， this is right for probably no reason and I made this temp equal to 20 times now。

 is this cool？😡，I hear I hear that like okay， do you think this says the same thing？Oh sorry， sorry。

 so before before this yellow thing， this is where it was， right？

All I've changed is this yellow stuff， we can move it here， so does this yellow do the same thing？😡。

That's a separate question， then is it good？😡，I agree with you it produces an equivalent program blank。

😡，I don't know if this is what we should do why can someone give me a reason why we might not want to do this。

 yeah。😡，I'm doing this kind of like an intention， like we're going to do this by the assembly level。

 so we don't have to worry about that， but that's kind of related to what I'm thinking about。

Why is this unrelated， what do you mean by that？Unrelated。

 you said this temp is like unrelated or collides or something。😡，Create a new variable。 Sure， sure。

 Okay， yeah。I'll take one more， yeah。Yes， can you tell ahead of time just by looking at this whether or not we really entered this case？

😡，For this case， I don't know。 if you looked at this long enough I cookeded up a random example。

 maybe you could figure it out。 Okay， but the point is the compilers aren't smart。

 but they're not that smart。 If I do this up here， yes， it'll be the same program。

 but I also compute 20 times numb。😡，Even if I always go in this case。

 if my function always goes in this case， I'm going to always compute that 20 times now and to show in this case it's a constant thing like maybe it doesn't matter that much。

 but this can matter okay do you have a question okay this is a contrived example。

 but there are a lot of examples where this will matter like if you hoist too far out of your loop or out of your function。

 you're going to introduce extra cycles because you don't have magic eyes。

 you don't know that this always happens。😡，So。😊，In terms of the control field graph。

 like what this means is basically like。What happened is that this， we moved to this。

 where do we move it， we moved it， I think here， pretty much we moved it like before this okay。

 before the CMP。😡，Except that now this thing is here， which is a different path than this。

 right here。😡，Is a different path than here？😡，Blue， red， green。

Be red green is different than blue red orange， so people see what I'm getting at。😡。

Sometimes that's nobueno okay controlable graph will be your friend it will tell you how we do this we do this by a very classic compiler technology called dataful analysis if I have time next lecture I will describe it to you but it's kind of involved okay but yes all you can trust is that yes we can we can figure this out all right。

😊，Okay， why the hell did I do this？Oh no， this is the different thing okay。

 and also I have another question which is like if we placed it out here， what if it was div。

 what if it was div？给他觉 that。Is this the same program。

 Does this do the same thing If it was multiply， it would be the same program， I agree。

 just maybe less efficient， but also if this is div yeah， your hose。

 you can't do that because why what if numbers 0， if number is 0 and we always enter this case。

 We would never compute the div by zero， we've return。

 but here we always did by zero compiler writers have to think a lot about this。

 they have to think about like what does it mean for a program to do the same thing It's easy for this example。

 harder when you have like a bunch of random widgets in your language compiler compiler people are pretty smart。

So combined optimization is interesting because you have to always preserve equivalence。

 but you have to make sure you don't change the behavior。😡。

Here's a kind of a check your understanding， I don't think I'm going to check it now because I feel like tasting other things。

 okay。I always said the thing on data analysis， okay。

All right with CFG's optimizations are just easier it's really easy to say something like oh this value will be used everywhere from here on out。

 therefore it's okay to like optimize up to here or it's really easy to say oh there's a path along here where I don't use this variable so I shouldn't move it here okay these are the kinds of questions we usually ask with control Fs okay that's the whole point why we have them all right。

😡，And then I'll also give you some boocab this is not super important。

 but local optimizations we call those optimization that work on just a block so for instance if I had like one plus two even here I move this to three right and maybe I also move that okay that that works within a single block of straightline instructions I don't need any。

A knowledge of how the functions go， I don't need you knowledge of how loops。

 I can just do it here because it's always better because I can always make this three that's fine。😡。

A global optimization is an optimization that you have to like look around your graph。

 you have to like look at everything， those are harder。

 those are way harder because that introduces a lot of cases。😡。

Okay so those include like dead code elimination the thing that Python does where it grays out your code when it knows that you can't reach it that's like a it's not optimization。

 that's an interprocedural analysis okay unused variables this one I have to look at every single path from me and see that like oh wait none of them are using my variable X this is a very classic thing that you should have in your IDE if you don't have this life ispan。

😊，And function in learning， which I don't feel like talking about。😊，Okay， thumbs up， thumbs down。

 thumbs minus， where is everyone with me right now， more people come on。😡，All right。

 now let me let me do an experiment。 So can everyone like like like hold their thumbs up。

 I guess why does they can and just like like even if you't， yeah， can you just use thanks， Okay。

 Okay， no I didn't you did have time。😊，Those things please。呃。They off yesterday， wait okay。

 look this this is this is more important， this isn is more important， have I taken my bele？ huge。对。

Thank you。 All right， Thank you。 good suggestion。 I will give a high。

 I will give a high shoot for that one。 All right， we're almost at the end， we're almost at the end。

 Okay， we're actually like pretty much just at the end。😊，Okay。

A lot of crap happens here there's like two kinds of people that are interested in compilers Okay you have programming language people and you have systems people this is actually a massive political like thing in the department don't tell anyone I said that but it's not it's not secret But the point is the systems people are all here they want to optimize for certain architectures they want to do really cool things where they make the assembly instructions take less time and take less space and be more efficient I。

😊，Im a P all kind of person， I work up here。I like I like tech checking this might seem boring to you。

 but there's a lot of cool stuff you can do with the semantics of program when you stay at the level of the source that's actually what I do for work thats sounds but yeah here Cogen is also kind of pretty well defined Okay we'll see what we do so we're at the object assembly We did a bunch of optimization and we have assembly that we are fairly sure is equivalent to the original program but it's smaller now I got to make real assembly how do I do that Okay well here's how I'm gonna to have to do it。

😊，Abject is something I told you assumes you have infinitely many variables whenever I have an intermediate computation。

 I call it T1 or T2 or whatever right I can just do that。😡。

Computers don't have an infinite amount of memory okay and computers have even less memory that's like fast to use Okay。

 there are certain locations around your computer's CPU that need to be used to make sure the operations are very fast there's like 810 20 of them Okay so if I want to make sure my operations are very fast I have to make sure I'm using those as much as possible Okay so。

😊，This is the problem called register allocation it's very very far beyond the scope of the course and my ability to explain to you。

 but I will give you an analogy in a second okay。😡。

But the idea is basically just like if I tell you like I want to put this in they're called registers。

 I want to put like my data in some register at some point I no longer need that data in which point someone can overwrite my data but it's a whole synchronization problem where I need to make sure if I put myself stuff here I know exactly when I need to overwrite that data and I'm overwriting optimally like if I put if there's the register called R1 maybe okay if I'm putting like like random crap in here okay if this is here until the end of my program。

 I probably have done something stupid okay because I should be hot swapping with these guys because the reason is that certain locations these registers are really brig fast they live right next to the CPU and then main memory like。

Alllder the way in Texas over there okay， so it takes a long time。

 so this is the systems level of the thing where like principally I tell you I don't care about this。

 but it does matter right。😡，Here's an analogy for you， All right， I know you love analogies。

I am really popular。 I have a lot of friends， okay。

 and it's my eighth birthday party and I I only have eight seats and my birthday party at Chucky cheeses。

 but most of them hatey each other， How do I make sure that all my friends can go to my birthday party。

😊，Without you know like well personal of all killing each other and second of all。

 they're only available at certain times my plans have busy schedules too they're eight year old you know they're too busy learning function composition and if they're not there for the full time。

 they're going to get angsy they're going get they're going get really mad if they're not if I'm like if they're like I'm available from two to five and I put them there from two to2 to459。

 they're going to anomy I got to make sure they're there for the full time okay。

This problem of scheduling like， oh well you can come in at this time and then oh but this guy leaves then and then。

 oh there's a seat open now and that you can come here oh but you'll be here from a full time like so maybe I won't put you there that's registered allocation。

😡，That's the problem and you can imagine it's a big planning problem okay。

 if you know the termmp complete， it is NP complete， yes。😡，Yeah。

 more specifically this problem is one called graph coloring how many color you have a graph。

 how many colors can I assign such that no two colors are next to each other but take 251 for more okay。

 I didn't sign up to teach you theoretical computer science I signed up to teach you functional programming。

😊，Okay， yeah， how do I plan a schedule such that every friend can come for the full time they can and I want to maximize their and my happiness。

 everything that sugars to a happiness problem and a graph problem。That's their analogy。

 I can't explain it any further， yes。😡，So definitely not because consider I have eight registers and then I have nine variables and all of them live for the entire duration of the program。

They go to Texas， they go to Texas I take my parcel of like my real data and I'm like sorry in terms of the birthday analogy。

 I tell Timmy like you can call him I got to begin to voice in。

 you got to zoom call me from Texas and I ship out I ship him out and then probably Bridge a millconds later he's up journey he calls me and you know he's not happy about it at least he got to go right。

the farm is I had too many friends， if I had seven friends， I'd be okay， they'll get a see。

like sure if I had1 friends like yeah two of them， two of them might have to go to Texas。

 but it's not always guaranteed they up to okay， this is like pretty much exactly what's happening Okay。

 we go to the main memory， we go take like 500 milliseconds。

 which is a long time Okay good question give me a good give me a good analogy cool I for there awesome。

😊，Do you see my joke？啊， ok 。Okay。There's a problem called all available you try so hard。

 try lambda when to meet yeah okay。😡，O。😡，After a lot of index cards and going to Texas。

 a surprising amount。😡，We're at the assembly， we have the finally we have the real assembly from the abstracttract assemblyly and we can run the executable stories over。

 we are finished with the compiler。😡，This is like the 5000 like five mile up view of what the compiler is okay a lot of parts of each phase have a lot of nuance。

 mostly the fact I didn't show you any real code that runs Okay but the intuition I hope is what gets you right where I want you to think about is what I want you to think about is。

😡，What I want you to think about is this， this， this， burn into your brain， blue， green， purple， red。

 yellow， okay。😡，It's graph colored what you want from me， okay， no not the colors but。😡，Well。

 that's optimization， you get to do that， yeah。My point being。Compiles are magic。 Okay。

 I've said this a lot。 I've said I'm sure you no， compilers are pretty magic， right。😊。

Now they're little less magic okay you should know like what your computer is where your program looks like。

 all of this is subject to these constraints that a lot of smart people are thought about that John Bas backca IBM in like the 1950s was thinking about when he wrote that for train compiler and he logged it uphill both ways So what I'm trying to say is。

😡，If you have the bird's eye of the compiler， sometimes it's all unique once you know how a compiler works。

 you can become a better programmer， better software engineer。 This is not the end。

 I have something else to same functional programming is good for compilers。 I said that to you。

 I didn't spend a whole lot of time motivating it。 I kind of like set a sentence or two。

 but I wanted to recap here， but like yeah。😊，IllS you the SC dog up here。

What do you mean imperative things？If your language has imperative features at the source level function or imperative is something we only use to describe things。

 living up there at the language level once you get to the assembly everything's physical hardware。

Yeah， abstraction， again， abstraction， we invented it so we could serve us。

 I live up here in abstraction land， people down there are manning the trenches， okay。😊，Okay。

 but yeah， any other further questions I'm about to wrap up。😊，Okay。

 last thing I want to say basically， I want to motivate to you。

 functional programming is good for compilers for a few reasons。 Okay compilers， again。

 I said this a couple times。 they're just tree transformations。

 I promise I won't ask you a question about on the final， even though it would be totally valid。

 Okay compilers are just really fancy tree transformations。

 we run functions on trees because programs are trees and trees are a happy place。 Okay。

 for functional programmers。 We're very good with them。😊。



![](img/6530e3c65db55893b5cc95c68a6dce24_1.png)

And also compilers cannot be wrong the day that a compiler is wrong。

 society shuts down and I swear to God， I swear to God we there should be no programmers left， okay。

 if you compile if you compiler code you can't trust it， that is the doomsday scenario no more hope。

 no hope at all， society is done。So we got to write a compiler that works what's the thing I said on the per class？

😡，We're not in the interest of writing code， we're in the interest of writing correct code okay that's what we're here for so compilers cannot be wrong type checking。

 algebraic data types， data type declarations like you saw in this class。

 all of these contracts that are enforced by a functional language ultimately help us when it comes to writing a compiler。

😡，2。5 which I haven't put here is that functional programmers are language nerds like P people are functional programming people therefore compiler writers are usually functional programming people that's not like meta reasonson and then finally compilers are here if I give you like a program an input program any input program I expect you to get the same AST with the same input I expect you to get the same list of tokens out of the same output and also I kind of expect you to optimize it the same way because what if you optimize it differently well now two runs might be different and if you write a bug now I've got nondetermin asistic compiler I've got a compiler that does it work。

😊，And which means I don't have a compiler， I had a piece of junk that I spent $5。

000 for that's very little for a compiler， okay， yeah。😡。

So okay the simplest way to describe undefined behavior in in the language of like C like oh this program's undefined behavior is that the compiler writer got too lazy and they didn't want to define what it would do so they just said。

 yeah， up to your interpretation it's failing a precondition same way that fact is allowed to do whatever on a negative input compilers allowed to do whatever on an undefined input that's the whole reason the only reason is just because they didn't wanted to define it maybe it was too hard maybe it was just not worth it it's just like a missing case in yeah it's like a pattern match with the missing case exactly and they tell you oh if you run into the missing case that's your fault undefined behavior。

😊，So now doesn't have undefined behavior okay oh wait， I was going to show you this latest thing。

About that about that， Anyone remember this from Piazza， Soone posted？😊。

This hilarious thing remember the thing I said about re allocation？



![](img/6530e3c65db55893b5cc95c68a6dce24_3.png)

Yes。This is a compiler bug。I slowly showing it to you。

Yeah they try to choose the victim for the Reg allocator and son and as I'm almost done I'm no mutability needed deterministic compilers functional programming I hope this helped you understand compilers of it I assume your questions on this I'd appreciate if you'd answer okay thank you。

😊，Thursdays will be even cooler。Thank you。😊。
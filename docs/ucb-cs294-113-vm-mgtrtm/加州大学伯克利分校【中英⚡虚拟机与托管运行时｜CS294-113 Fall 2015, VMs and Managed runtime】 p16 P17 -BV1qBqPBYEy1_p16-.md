# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p16 P17 -BV1qBqPBYEy1_p16-

Work together oracle and some since the early9s Michael is an alumnus of this fine institution and has been working more or less in tools for your entire career maybe some little science trips here and there much and is the。

You know， often the lone voice in the corner of the room who talks to the compiler of the VN guys in six what。

I you use that。And so yeah， people， yeah， people is the operative word。

 it's not computers and software， there are people involved。

And Michael thinks about people and how they do stuff and what they do。

And have their job they do their jobs and what we need to support to do so I think this。

It is the last part of the course， so it kind of does look like an afterthought。

Always supposed to be， but at least there is a slot on the course and so I think that's a very much appreciated to actually have this opportunity。

What was。ItI it in yet， so okay， it did work so I hopefully it will work again。嗯。他的。ち now。啊。Cool。

 actually works， okay。Okay， well， thank you， Mar， for the invitation。

Let's see make one more adjustment here。Why is my cursor not join？Okay， so let's see， let's。

There's still the operator area here。O。So yeah， thanks Mariio。

 I'm going to introduce myself a little bit more to so you know where I'm coming from because that's especially important because I'm not a VM guy that you've had a long time now to learn how a VM guy thinks about the world。

Which is almost as important as anything technically you learn this is how do you think about the world if you are doing this or that okay。

 so I'm not a VM guy and I always have that disclaimer so anything I say about V you should distrust。

So but so who am I， what do I actually do？So okay， so Mario just said this。

 I think it was around 1993， we've been more or less in the same place of actually I've reported to Mario at least once maybe more must track。

It's all very fluid in a good lab。嗯。And so we sort certainly know where each others coming from。

 so I've had a very checkequered career， three trips through school and they were discontinuous by several years in each case right so each was a different phase of my life starting with sort of sort of really things that I was interested in。

And then when I did by MS， I was actually thinking about programming proving correctness of programs and stuff and there was a language implementation system that had an advanced parser that wasn't just a algorithm was and whole parsing system for languages I did a correctness pre that was really cool and then I went off and did other stuff for eight years and then landed at Berkeley working in Sraham's work with that time had been migrating from compiler work to interactive program editing systems work and so I joined the work doing on that and。

Focused a lot on the human factors and how work actually gets done with such things。

We've talked about that over lunch a little bit。In between there I taught for four years on the computer science department at Cal Poly。

 which was a very formative time the students here are extremely smart。

 they all come in like with four plus GPAs and stuff， it's a very hard department to get into。

And I remember the single thing that was hard is teaching undergraduate programming。

Was that they didn't seem to have very good tools and so that kind of refocused me and so when I did come to Berkeley。

 I came me with a specific intention of working on developer tools to make programmers more productive。

Because it had seemed to me by that time that most of the subjects I had been studying in graduate school previously my previous tour didn't really help any programmers get their work done。

 so that's been my focus pretty much ever since。And in almost every project I'm the To guide right so and here's just a quick sampling Mari I will remember some of these names from the past。

 but I've touched on all lot of different areas of tooling。Over the years。

 including some that we'll come back to so you probably you heard a little bit about the MaxI inspector I believe and so that was my project before this。

 that was my first encounter with the VM world I should say before that I spent three years studying the HPC world which I didn't know anything about and before that a whole series of other things I didn't know anything about so part of my history is sort of starting a new project on something I don't know anything about but with a stance that it's important to figure out how we help program get work done。

So here's what I want to talk about today， first thing I want to do is sort of do my review of the entire course that you've had so far from a different point of view。

I can get away with this the second thing is， camera。

I want to talk a little bit about how I think about developer tools and again that will sort of emerge from this。

 but it's really important， I think that's as important as actually the technology itll tell you why I'm doing what I'm doing in the context of this work with Mario。

And then Mario has given me license to rent a little bit about。

Strong opinions about developer tools and the role they play and why we have them that don't always have them。

And then finally， I'll get to some technical stuff and tell you what I'm doing personally about tool support in the truffle growl world。

 okay， and then maybe by then end you'll be back on sort of more familiar footing。So okay。

 so starting the review， so I went back and looked at some of our slides and here's one language Use dilemma。

 so I take language user to be a programmer。And so their dilemma is what wouldn't this say？すみす。

A big team of implementation experts to build an optimizing VM。As a language user。

 my question is like， how do I get worked at you know， where's my debugger， no debugger really？

So I looked around Nao's slides some more， and then I found what looks like a solution。Itys， oh yeah。

 is it resolved， we say yeah， it's really fast now and I look at this and I say， well， okay。

 let's reevaluate。I'm still looking for my debugger， where's my debu？You know， so that's my summary。

 actually no， here's one more thing。 yeah， this is another one of Mario's slides。

Here's a system architecture， okay， so you've probably seen this so we knowt want you to look at and think about it a little bit and now if you're me。

What comes to life？Well。Okay。Where tools， how do you use any of this stuff What is a programming language？

What is there between a programming language that sits there and runs and a person trying to recode。

And so that's the sort of。Okay， end to review， okay。

 so the whole point is that when you think about VMs or any other language implement technologies。

 usually tools don't show up。And by implication， people don't show up。Okay。

 so that's my starting point。And you saw all the different kind of stuff that I've worked on in terms of projects。

I had a wonderful opportunity， courtesy of the US government and DARPA to think about this for about three years。

During that time I didn't do any development of ion， it was a project for DARPA in the area of hyp。

Performance computing。The big。100 200 million machines like out Lawrence Livermore and those things。

 supercomputers。And some Korean and IBM were in a competition。This particular project。

Uniquely said we want to take a left turn here in our next round of procurements。12 years ago。

We want the next generation of machines， by then the target was petestscale。

 petabyte petaflo type machines， we actually want them to be more productive。Now， what is productive？

Well， that was one of the problems， nobody had any understanding of what productive was。

So in the HPC world at that time for many years。A proxy for productivity had always been what they call speeds and feeds。

How many 40 point operations per second are potentially available？

And what is what they call the bisection bandwidth。

 how fast can you get how much data in and out of the machine？Now。

 my suspicion is that the latter was really because their number one problem was checkpoint because their stuff was so unreliable。

If you have stuff that runs for a very long time， you spend a certain amount of your overhead checkpointing your progress so you don't have to repeat it if you get a crash。

So one of those little secrets。嗯。So。And the challenge for them， okay， supercur pet of scale。

 but part of the challenge was to come up with a notion of what productivity means because they admitted they met but we want more of it。

 so they said an arbitrary target of 10 times more productive。Which was our mantra。

 So designed a supercomputer， which means all the way from chips to self system， you know。

 maintenance management。 And we want to be able to get more work done with it。 Well。

 that means that somebody has to go try and figure out。How you get work done way？

That was astonishing， that was the high astonishment factor at all that they were interested in doing that and willing to put some money into it。

So Sun， actually as the leader in the area of productivity。

 he put together a series of cross functional teams and I was on one of them。嗯。

The core productivity team。 So we were one of four cross functional teams。

 And by that means that if you were to look at that normal system stack。

 what with chips at the bottom and。All this other stuff at the top。

 a cross functional team has a responsibility at every single level。Okay。

 so our job was to investigate。Systems at every single level and try to understand how we would。

 in principle， achieve this goal of making a supercomputer 10 times more productive。

And even more interestingly， the person who hired me to do this had an interdisciplinary team that was quite a pleasure to work with so for three years worked I was the only person who was actually a computer scientist with a software engineering background。

I was working with a physicist。I mentioned an expert HPC programmer。

 very wizard at writing the kinds of programs that takes to run on these supercomputers。

 unlike anything you know。And a cultural anthropologist， what？Well。

 if you're going to study how people get work and that means you have to study people if you want to study people。

 that's what cultural anthropologists do it's this funny mishmash science of psychology， sociology。

Culture and stuff I can't even remember。 it's it's a synthetic science It was created in the last century。

So that's and this person suits Squiires。Was a practicing cultural anthropologist， she didn't teach。

 she didn't do research， she worked for big companies and studied these kinds of questions she did early work on cell phones before there were cell phones。

 she studied breakfast foods or busy families I mean you name it。

 she had kind of got out and done field work。So this is pretty wonderful stuff and quite interesting。

So I wanted， yeah， is the physicist in this case， your end user， no。

 the physics software program or is a physicist someone who understands。

 if somebody who understands the world of HPC， most of the HPC cycles go to people doing big physics at the Department of Energy。

 but not exclusively if you look at the customer list。

 you'll see that Department of Energy is only one of them。Okay， no such。'm sorry， no no sense agency。

Out there somewhere beyond the fringe， the kind of place where when Craig sells them a machine they'd never see again。

Yeah， they were also a customized and as it turns out。Had very。

 very different requirements than the DOE people。You can talk about that later because it's off topic for me。

 but they're all fully understandbsstandable now。Yes。

 let's just say that what part of the project was to try and evaluate。In advanced。

 how good a machine would be as one of the problems because you can't build a prototype of these machines。

 right， You spend $100 million to build one。 You really don't know。

 so they had a whole sub area of work was to build。

Benchmarks that you could simulate that would tell you something about a proposed architecture at this scale and they had to be scalable they had to like you know really scale out and so a new round of these things were developed as part of the project。

 some of the parts we collaborated with IVM and credit and then other parts we competed。

The productivity teams were collaborative and worked together with the others because our job was to define productivity。

The synthetic benchmarks， you let's just say that there were a series of them that were all quite understandable and then the last one was graph partitioning。

Okay， the DOE doesn't do graph partitioning。So moving on。So let's look at some models。

 some of the things that came out of our final report。To just summarize what I think we learned。

About the topic in hand and I just happen to have this in our report， so let's yeah。

 models of a customer HPC system。Just for a little bit of context。

 here's what a software project typically looks like in that world。嗯。

The software takes five years to develop。Really， to start testing， this is expensive software。

 A typical project has no more than a few hundred thousand lines of code。

It's a very difficult software to write。And then it is in use typically by customers and the customers tend to be scientists around at。

The DOE and government lab， the software is normally open so it's shared by people at universities。

 they did open source before it was a thing， for example。

 a government software was mostly by definition， unclassified and available。

And then people use it for their research and has continued testing。

 although their notion of testing is different than they think you would recognize。

And then they tend to be retired when nobody is willing to fund the next。PortDid I mention porty。

 okay？As supercomputer， they tend to be one off unusual。

And they tend to also go through phases of different architectures， so when we started the project。

 clusters had just become big。W replaced a previous generation of purely vector machines。

 which replaced I don't remember what。So the fashion changes， but even within that timeframe。

 the lifetime of a supercomputer is about four years。And after four years。

 they're usually not useful enough to be worth the electricity to run them。

So you port these software， so you do the math， how many times a piece of important software gets ported。

And it may be from a vector to a distributed memory cluster。So think about that。

 So it's expensive software。嗯。So when you look at this diagram， you can say， well。

 where are the tools？Well， there's tools everywhere， right everything you see。

 every test that gets done is both people and tools and you can't do any of those things on that list without tools so clearly tools are a big part of what they do。

And one of the things I learned in my first year was that the HPC world in general of government funded labs has a seriously broken model for tools。

And I wrote a paper about it that said， you know， this is really screwked up。

But I tried to identify the causess and you'll see that when we come to one of my next models， Okay。

 so that's one model。How do people model computer systems here's another common one。

 this is looks like kind of like Mariio's， this is kind of a cartoon version of a normal system architecture。

 the one that we had for our pedestscale computer，Had about 10 levels in it， okay， if you will。

 is very complicated， but this is kind of representative。

 notice that I kind of sneaked in that one called development environment normally it's just application systems software。

 hardware， something like that right。So again classic how computer systems people think about computer systems it's a systems approach and you have a model so where are the tools well like I say。

 I put it in here so that to me then implies it that's where people go so when you look at this though think about my colleagues。

Okay， so one of my colleagues， we collaborated with other people around the project。

So one of the colleagues who was working on sort of the memory model stuff。

 he really cares about the bottom two boxes。You know he had his own view of the world。

 our HPC expert programmer， well he cared about the top two things。

So everybody has a different take on which piece of this really is important to them。

 so that's to think about for this particular model。

 so there are different people with different concerns and this helps you map that out。

boundaries on the different parts of the system， most people usually only care about about two levels。

Here's another model， okay， a little bit different。

This is a software engineering workflow model as it applies to the kind of organizations we were talking about。

This is very different。Notice that it's got three levels so at the very bottom is what you would recognize in other words。

 somebody with a objective and they need to produce a solution。

And write the code until it works okay。And there's lots of those。

 that's what we normally think of in computer science is a person even with the tools。

 there's some person there， they've got some tools。

 they have some workflows and they produce die software。

But notice that most projects actually have more than one piece of software。And at the project level。

People think about it differently that's what managers up there they think about the overall project and so they're making trade offs and allocating resources of people and money。

And they're looking at iterations， they may be doing something over time and they may replace software from by one thing with another。

 they've got maintenance issues。All of a sudden reuse becomes important so if done if you're a programmer at the bottom resource reusing software is not a thing because it takes extra works and most people rewrite everything from scratch。

 right？And anybody who's the smartest program around， which is most of us is going to say， oh。

 I can do better than this and I'll rewrite something from scratch。

Reuse normally gets imposed organizationally as a budget as an overall budget optimization to say no。

 we can't afford to keep rewriting and youve got to reuse the parts Now all successful stories of code we use I've ever seen were imposed by some structure so that's the kind of thing that goes on at the project level。

When you go up to the big organization level that operates many projects like a big lab or a university or a big company like Oracle。

 you have an overall mission。And projects come and go。

And you have to then allocate investment very strategically in these missions， okay。

 but they happen on a different time scale。And that's the important thing here， different time scale。

 and in every case you're allocating resources， and in every case there's ways of thinking about it。

嗯。And if you are a person down there writing code， you in a sense are participating in every level。

 even though there's decisions being made， Okay， so this was one of the issues I identified with the developer tools in the DOE labs was that。

Any individual project can't afford to invest in tools they don't have the money or they can't take the time to build them。

So normally at project level you might want to invest in tools。

 but even then that doesn't always happen because it's expensive to develop tools。

 especially if you're working on platforms that change out from under U。よし。It's a problem。

 so you'd say well at the organizational mission level is really where you should be thinking strategically about tools because you want to make your people more productive and you want to sort of nurture them over time and in the case of the DOE labs。

 the issue we found and identifying and reported on in a paper that I wrote is that the US government wasn't funding the tools for the labs。

 they would buy machines， they have big expensive machines， but there was no budget for tools。

So what you found in practice was down at the project level。

 people were stealing time and resources without telling anybody and using them to try and develop the tools they needed。

This to fact。Okay， so there's a model and there's people and there are some tools if you know how to ask the question。

Here's Suus Squire's model of the world， this is a cultural model， if you will。

And notice that an anthropologist persuade say that every person lives in many cultures。

As an individual， you're a computational scientist。But you have actually。

Respon and obligations and a role to play in every one of these circles somewherewhere out there you're a citizen。

 okay。嗯。And。1。For example， in her world one。Characteristics of a well performing environment is when the goals of these things are all well aligned。

When you have them not aligned， you also run into really interesting sets of problems and'll leave it to your imagination。

 what happens when different parts have priorities and alignments that go in different directions。

You read about it the news。So where are the tools， well， this doesn't talk much about tools。

But where are the people， well， this is about people。

 so the example I just mentioned of why the DOE labs seemed not to have the tools they needed。

Is the culture of the US government？And it's not just that they're incompetent。

 it was the cultural issue。People in Congress who vote to allocate $100 million for the next great supercomputer to one of the DOE labs。

Do that because you get a lot of exposure for it and you get a lot of press and you get pictures。

You don't get pictures for tools。You don't make the press。 You know。

 nobody sort of cheers you on for building the next great thing Like the world's fastest supercomputer。

 right， It's there's this arms raised in supercomputers。

 And so if Congress approves the next great one， it's like， this is great。

 It's an America game we're building the next great supercomputer。

 but yeah have better development tools doesn't happen。 So it's cultural question。

 And that was really the root comes there。 So so we say， well， we kind of take a synthetic view。

 If you're looking at the whole system， you really have to look at the whole system。

 So a synthetic view says， well， a actual HPC system installed， doing work。

 looks something like this。 at least this is one model of it。 notice there's people there。嗯。

And there are tools there there're still a development environment。

I think there's a bug in this diagram and the order is probably wrong in some places。

 you could argue about that。嗯，But。Tools are there tools are a necessary part of this right I gave a talk at the JVM language sumum a couple years ago and I introduced myself as the user interface guide for their technologies I said you guys all make code run fast but it's nothing if you don't have a UI for it and the UI are tools。

 editors debuggs you know all that kind of stuff so you should be nice to tools people。嗯。

So it's a critical part of what's goes on here。嗯。Okay。

 so to summarize kind of what we came about just for completeness。

 here is our model of what we think。Its going to take to achieve the goal for dark but we didn't get the following on contract so we never carried on。

 but the way to read this picture， this is kind of a two dimensional now spreading out of the previous picture plus。

The goals we got， the targets we got from DARPA， and they broke out the productivity goals for us into programability。

 portability， performance， so far， okay。And so our team， our greater team。

 the whole team really came up with these as the key ideas we were proposing。

 So there's listed as five。Design requirements we felt that were important to meet those goals with sort of the lines there connecting them。

And the five major innovations we felt were necessary。

 some of which we felt pretty strongly we had something to say about would it take to meet those design requirements。

 so this is one view of the chart of how we expected to meet DartA's 10 x。

Proectively challenged for the whole entire computer system。

 and you will see that languages and portable tools is one of those things。Very， very important。Okay。

 so that's my how I think about it and what I learned thinking meta about it for those three years for DarAA。

 where I didn't have to write any code， our job was to just like make a case for what it's going to take to get a huge jump in productivity。

And I think the real world is not that much different than HPC。Yeah。

Specifically were applying to government。Yes。To me。

 seemingly the biggest difference between webC computers and webCAM tool is that it's easy to say how fast your computer is going。

Much hard to say how So understand and that as I mentioned， I mean。

 one of the darkest tasks for us was to say and by the way， all three of you vendors should。

Work on a good definition and metrics for productivity and you should work together because we need a good operational definition of productivity。

I can't say that we succeeded very well with that， to be honest。It's very hard， yes。

 it's about people and it so contextual。Yeah， that's why we have an anthropologist right。

So how do you major in isolation， how productive a tool is？ whereas you know。

 being the fastest supercomputer is completely objective and they know how to measure that。

 is it useful， not particularly？Because if you ask the HPC people about there's。

 you know the megalops or petaflops they can get they say， well。

 how how many of them do you actually use， it's called utilization？Usually not very good。

Because the technology is a good enough programming technology。 Yeah。

 would people argue if you leave this to the private sector。

 languages with to trends not normally win the work。Normally， I mean， you have a， yeah， I mean。

 you feel private computations， you would think。But here's the question to you。

 what do you think the average amount of money per program are most companies invest in software development tools？

Just a thought。Yeah， pretty small。But the thing is they will discover productivity by theyre using it。

 so that is non intuitive defined to the economics。It's a great question。

 you really hit the core of the problem， right？Why don't we invest more money in the tools for our program？

There some economic incentive。Well， doesn't sound like there should be if they really made them twice as productive the long term economic part of it's the long term again that' that's that level of organization right doesn't make sense in the small it makes sense at the or at least at the organization level if not the mission level that make the government the right stage governments designed long term so as the HPC case the fix would be for the government to fund tool is that exactly right。

It's a great question to why it doesn't happen elsewhere。We can all spend our own theories。

 but in fact， it really doesn't， people just don't invest in tools for programmers much。I mean。

 I mean， I'm curious。 this is a recurring issue。 And people have seen this over and over again。

 Then why isn't this。Now tracked into project budgets before proposing the budget， great question。

 I don't know。嗯。Other than just the usual cynical things we say， right？foro's management， probably。

 I mean I can guess management don't have confidence that schools actually will make the difference。

It be my first guess。 are there like a clean studies that show like。

Objectable numbers of tools doing X quantity factors it hasn't been a fashionable area of research for a while。

 there's some great work done in this at Bill Labs about 25 years ago。

they learned a lot of really interesting things， for example， about code reviews were very wonderful。

 big big then and there was a whole research literature on how the right way to do that was。

 and they did some empirical studies on code reviews。And you know， it was very revealing。

A high little bit of that work。And the reason I know this is the chairman of that group was the physicist I mentioned here。

 did empirical software engineering bill for years。He said， the higher of it is。

Will the code be reviewed or not？And if it will be reviewed。

 then you get a very definite productivity increase and if not you won't。

That's empirical and that's and so there have been some small workshops for years there was one called the empirical studiesudies of program where it's not happening anymore。

And there have been other related ones， but it's generally not a particularly well fund research just doesn't。

It's hard to ramp up the resources for。So yeah， I want to move on here。

 so this is the end of my sort of here's how I think about it as objectively as I can say now leaving objectivity completely aside。

I I want to express some wrong some opinions， okay， so we don't have it all okay。

 we have lots of languages。But usually when they show up， they don't have tools that come with them。

It was a very long time before there was a working debugger for Java， for example。

 and a lot of the dynamic languages now come they don't have debuggers and people sometimes write them they don't work through so what's that about you know？

And when they do arrive there's usually they're not as great as you would like so there's a lot of compromises so here's some typical tradeoffs。

 let's just say for debugggers， but more generally for anything that relies on runtime information is there are at least one of these compromises where okay you know either you can't be fully optimized or there's really there are cases where you can't use certain functions if you're debugging。

Sometimes you have to ask compiler writersers to do heroic efforts that they don't want to do to of provide stuff。

You got to run in the special mode， you got to restart your program。

 you can't debug if you don't have dash genome on or whatever it is。So。

 why do we make all those compromise lines？So that's one of my complaints。

 we don't really have what we want， we don't have full service tools all。

And it seems to be getting harder well， there are some reasons why it's harder the challenges are getting worse first of all debus famously by definition they cross abstraction boundaries and do things that you went to a lot of trouble to make sure couldn't be done when you wrote your software right。

And so that's an issue for any of you leverage it some sort of built in and platform dependency。

 eitherre not as portable as you'd like。And you know one of the fundamental disconnects is that if you're a hot compiler engineer。

 your job is to get rid of information you don't need as fast as possible in your pipeline and it's almost always exactly the information a person needs when the debugging the code。

 I could go on about this access journal paper about that very topic it's a real problem。

 it's a real tradeoff right and all that and if you do want that information you know the standard for native code lately has been several decades now you got to have a separate thing the compiler outputs andwar format that helps you reconstruct the state of execution。

 but you kind of on your own if you're the debugger writer and getting it right is tough。

And in optimization， it's even worse， okay， because again。

 the whole point of optimization is to get rid of information that's not necessary for the result。

There have been lots of PhDs written on debugging。Optimized code， I know personally two of them。

They were both came out of Su group like 15 years apart， that's just not a problem that goes away。

And now then the world of dynamic optimization， oh my gosh。

 you know how do we figure it out what things are being optimized on the fly so that's my second ran。

 it's hard。And finally， there's this mindset。And you know。

 one of the root causes for all this is that if you're and I've alluded to this and the way I speak about it。

 if you're an engineering compiling an engineer， you make an assumption that basically says the machines are expensive and so we have to make。

Our machine code run as fast as possible， so we use less machine。And so what do you focus on。

 what do you focus on benchmarkmarking make things fast， okay。

 that's absolutely it now if you're me and you're working on tools。

 well you make an assumption that people are expensive okay。

 that their time is what's important and therefore you focus on human behavior。

You might imagine it's kind of hard to collaborate across that sort of boundary， that gap。

 if you will， of concerns or priorities and assumptions。At the end of the day。

 you end up with people that， you know。Don't have the skills to do the other person's job。

 And part of what's come out of that then you， it is。The disconnect between the two worlds。ついた方は。so。

My personal experience with this of course being a tool person。

 I've almost always been around performance people and so I have certain and not just performance but others。

 but I have certain ritual arguments that have played out over time in the several decades I've been doing this。

 so for your entertainment here are some of them。Okay， ritual argument number one。

This is a quote from a CAM article， which was actually the main technical journal at that time。

It says， how。Tools should treat programs for the benefit of people using them。

What's the viewpoint Well， they're not really clear it says here， okay。哎，嗯可。W， have it， I think so。

给你带到。O。So we were just talking about these guys over lunch， Ta them and perhaps， they argue that。

Yeah， it's actually a hierographicical composition of structures and all the tools should be like that and programmers should think about it that way and like I say this original argument well no they actually aren't that's just not true MLVV that's me。

Okay对不。And so， so。This keeps coming up over and over and over。

 right I mean that's why people think that。Structure editors were a good idea。

 and these guys did the original important structure editor and a decade of experience with them usually only by people who had no choice。

That proved that they really weren't all that great。 So here's another one。

This actually is more personal and a project I was on this time is I was， guy says， well。

 we're building a really advanced tool for really smart people so therefore it's okay that it's really。

 really complicated because these people are really smart。And so the focus was on features。

 but really， you could do all this amazing stuff。我要。Here's my point of view， well， actually no。

 we're building tools for busy people time is something。Therefore。

 we should invest in making it easy to use， doesn't matter whether there's。Okay。

 so that one has come up over and over again， Here's another one。

The most important thing is to make the language run fast。 We'll build the toolss later。Yeah。

No that's my response to that one， so I could go on and on。

 but that's three typical ritual arguments you get when talking across this gap between the people who worry about productivityivity and the others。

Well， it wasn't always this way， there were languages that had tools with them。

 it was kind of understood and each of these three languages in its own way made a contribution in the area of good tools for programming。

 but it was simply understood there was no such thing as separate debuggs for any of these things。

 for example， okay。In addition to those three。There actually are other programming environments you've never heard of that are just systems that have their own lab view from figure。

It's all kinds of stuff。That for you。And the distinction is they're programming systems。

 they're not just a programming language and Dick Gabriel's paper that I mentioned。

Its full of a lot of deep dive on some technical issues。

 but at the bottom he sort of observes that that shift in focus away from systems to languages in the research world changes your focus。

 you only think about languages you think about sort of rareified semantic models and performance and stuff。

But if you think about a programming in system， you think about work getting done， okay？So诶。

So there's a lot more history there but let's just say what can we do about it。

 so right now I think we can have it all and that's what my technical work has included here in the last while。

And I'm going to get my bottle of water for。Still getting over gold。

Voice is only good for 10 minutes at time。So two big ideas that I believe will allow us to actually have it all you know。

 tools that work fast， don no compromises all the time okay， so here's the first one。Okay。

 look at your language implementation platform and build the hooks for tools right into it。Okay。

 and the specific piece I'm focusing on is you know。

 execution events where you're not ready to execute something in you're in this particular computational state where you just did it。

 okay？And but build it into the platform in such a way that instead of working at cross purposes with optimization that you were part of the optimization。

If you're a martial artist blend， it become part with it。

And do it in such a way that there's not a lot of extra work。On the part of the language implementer。

So that you have this available all the time so deep into the platform and really rethink this notion of how we connect tools into runtime so again focusing here on runtime information。

 making it available so that's the first one build it in， make it fast。And then build up tools。

And build out the core of the tools in a language independent way we call them language agnostic。

 that they provide the same service， whatever language you implement。And if you do that。

 and if the language implementers provide a little extra bit that's needed。

Then they'll actually have a working debugger before the language is even finished。

And how would that be or maybe profilerss or maybe other things that we built？

So always available extends backwards across the release barrier right into the development process itself。

Okay， and at the same time， we want there to be an API that allows。

External people to add new tools to do more kinds of analysis。

 both for research or other products sort of related projects。That's。😊。

Those are the big ideas that have been guiding what I've been doing now for a couple of years。

Trffle and growl， it represents a really interesting opportunity in this respect。

Since it's a complete reversal to what it looks like to build tools for native code based environments where reconstructing the execution state is really quite a challenge and often impossible。

Here， the basic execution state is an AST interpreter， which is very straightforward。And even better。

 it's expressed completely in Java， okay a high level language where we actually have a lot of facilities available already。

 so it's just big data structures， I mean the stacks there， the frames are there。

 everything you need is there。That's the first most important thing。

 it's really a clear execution model。And second of all， the optimization。

 okay the optimization code in truffle is language independent。

 it's all about tree rewriting and specialization， okay。

 and then aggressive inlining all the stuff you've heard about okay so make sure that the tools just basically participate in that because it's actually an advantage。

 turn a bug into an advantage。And finally， and this is really the trick。

 this is the one thing that makes us all possible。Is that for its own purposes。

 the platform knows how to de optimizetimize。 So all that aggressive optimization that's done。

Must be。D optimizeimize so that you can have access to the execution state simply for the purposes of the speculative optimization it's part of the architecture of the system。

 so now you don't have an externally imposed requirement。From a debugger or other tool， this says。

 oh， by the way， stop everything I want access to the execution state。

We're actually now leveraging kind of the internal power of the platform itself to do that as needed。

 so the debugger again becomes a participant， so a debugging event then。

Looks like that and well let's just the one from there so so that's the real thing so the blend is something i've described is to say automate as much of this as possible so just sort of build it right in in the first place。

Here's the case， breakpoint conditions， okay， famously。

 conditional break pointss are slow system zones enormously。The trick though。

 and this was actually done in a small talk world， who knows as well。

 was to well just rewrite the code and then feed it back into the runtime and the way you go。

And if you have an aggressively optimizing runtime and you attach it in just the right way。

 it becomes part of the program， so breakpoint conditions now run as fast。

 you know when fully optimized， as fast as any of the other surrounding codes so we completely reversed the issue with breakpoint conditions so a long-running program with a breakpoint now can have a condition at very little extra cost。

 no more than the actual cost of the expression and the framework costs。

 so all the framework costs prop propagating events。

Has very close to zero overhead in terms of runtime speed， Okay。

 there's almost no speed because the optimizer。Basically inline all that stuff and if you have some machinery there's nothing attached to it if you're not listening。

 it will get in line away to nothing。And you'll simply have no machine code generated at all。

That gives us the option of having all the stuff empowered all the time， it's always available。

Where we're going and finally， I mentioned the API。There's some stuff for that。

 so let me talk a little bit more about how it actually looks inside the system。

 what the abstract model is。So depth to and pictures are more fun。So here's an AST。

And there's a note of interest， so let's just say you know that's a note we care about it's piece correspond to a piece of source code okay so this is a conceptual model now we'll talk about actual implementation sort of next okay。

 so here's some of the basic。Abstractions around this okay， first of all。

 there's this notion of a probe。So this is back to my electronics background when I was a hobbyist。

Is a probe is a place where you can connect to get events that's just about。

It's not's just events are available here， there's one way to think about it， okay。

 there's just a place you can connect。So that's attached to an AST node and it says， okay。

Interested parties can find out what's going on at this note， so we'll call that a pro。

And related to the probe is a separate mechanism called a tag， it's an annotations。

 it's dynamic annotation， it's not part of the AST， it's not part of the type system。

 it's not part of the language。It's basically an annotation that's there。

Whose purpose is to configure the behavior of tools。And the typical way to do that。

 the most common one is to say， oh， this node。Is a statement。Okay。

 it's not a statement in the grammatical sense， like this is a statement in the grammar。

 we're not being driven by the grammar。This annotation saysAny tool that cares about where statements are should treat this note as a statement。

The debugger， that means if you're stepping， this is a place you want to stop。

It's a critical distinction to have the tool behavior be configurable outside the engineering of the AST and outside the grammar。

On the paring structure， I went into that the hard way here on the other。Okay。

 so so the tags are this sort of external configuration mechanism。Okay。

So execution events then at this place that's been notated as a statement again and there's sort of this before and after。

 you can say I'm just about ready to execute this statement or I just executed it and maybe' something here's a result thinking came from something like that。

So that's an event。And an instrument basically is the thing that connects。

Then a probe with a tool that really wants to hear the events。So I'll call that an instrument。

And again， it's just an agent， if you will， it's the agent of。我就。🤧All right， sorry。

 that's the first thing。And again， you should be able to attach as many instruments。

 you should have three different tools if you want listening to the event stream from any one place at a particular statement。

 they should be operating orthogonically。So you could be statement counting。

 but you could also be debugging and you could be doing anything else。

Kind of the rough idea and finally， and this is again the most important thing is that optimization should apply to this whole framework。

So everything here gets optimized as much as your actual end user code， okay。

 so that's a conceptual model for what we want to accomplish okay。

So let's talk a little bit of engineering now now that this next diagram。

 these are actually nodes in the concrete data structure sense， okay， so here's an ASD。Okay。

 and notice now I've pushed down my blue in there， that node。

And the important thing to notice about that is that there's a wrapper。

 wrapper is the way that we intercept events， we intercept them by sticking another node in the tree。

And that nodes job is simply to get the requests from the parent。

And then notify the instrumentation system that we just got a before events。

And then delegate the execution of that down to its child and then do the reverse when the event returns。

It's important that the rapper be part of the language because it has to be a type that can fit into the tree so it's a language type。

And then there's this second note over there I call it a probe note。

 it's the agent for the instrumentation system， It job is to manage instruments and delegate flows。

And you can dynamically add and remove instruments so all that gets handled by this thing called a pro。

It's actually a node and it plays by the truffle rules， which means it can get optimized。

Now here's the real ringer， you can be working along with your tools and doing all this stuff and then truffle without telling you can all of a sudden clone this tree and now you have two different data structures that represent the same piece of running code。

So what you thought was statement three now actually isn't actually a node， it's two minutes。

 they're both statement three executing in different contexts happens when you in line。

 specialize differently， that sort of thing。So how do we do that with our tooling okay。

 well that's a problem when you get a clone so we have to sort of understand that and it clone again just to review you probably heard this it's a deep copy。

Of all the things that are actually trule nodes， so in this case。

 both the wrapper and the probe node are deep copied。And then we have to manage them somewhere。

 we have to track them。And the way the tracking should tracking done is that this thing called the probe now actually。

Goes and tries to figure out when you get cloning， so it actually knows that it corresponds to statement three and it keeps track of all the nodes that are executing statement three anywhere in the system。

 there could be any number of them。Which means that when you want to attach an instrument now gets a little complicated。

 you say instrument to this probe， and it actually has to go and modify the chain in each one of those。

Those things， okay， so it starts to get kind of complicated and there's a lot of objects here。

And that's the basic idea， okay， right now， the crank limitation。

I'll come back to ways in which it's changing。But again。

 the overriding principle here is that it's just part of the AST to the optimizer。

 it looks just like any other code， it will get inline， it will get optimized。

 it will get speculated on， it will get get restored All I have to do is know how if I put in a debug or break point to know how to sort of say de optimizetimize me because I want to do something now that's how we get inside the system you。

How's our performance well it's pretty good， the Ruy paper that if you happen to read it was handwritten example of putting those wrapper notes in to see if we could get trouble too。

Basically， partialsha will evaluate them away and the answer is yes。And。

So the runtime overhead was asymptotically zero when things were running in the fast path。

 so this was pretty successful and encouraged us to go ahead and build out the more general framework。

Rubby has a built-in mechanism for attaching trace functions anywhere you want in the program and so our first measurements is to see how fast we could do that Ruby has a number of highly optimized implementations。

 every one of them falls down badly when you turn on tracing because you have to go and sort of inter the events and in traditional compiled environments that's really tough it's like the break point condition problem same problem。

We were able to demonstrate that we could do set trace funds without annual loss of performance again once it starts running。

 gets optimized back into the vast path， it's just like as if you had handwritten it and so we could actually compare the compiler graphs and say you know。

 we're getting the same code as if you had actually just rewritten the program so that's really a good validation so very encouraging。

Results limitations well there are some limitations for one thing the early prototypes eagerly went into the ASDs and put those re nodes in that turns out to expand the trees a lot especially if you're not really going to need it so if you want to have it always on then you need to be a little more careful about your object allocations。

And so we're actually rewriting the low level stuff to make it more lazy。

 it will still look the same， but it will be more lazily instantiated in the idea is to keep the object footprint down a little bit lower。

 the performance characteristic should stay the same。

 other than the delay is when you sort of start something up we need to do a little more allocation。

 but at the end we'll really reduce the footprint a lot。

So I mentioned that the language imper doesn't have to do much。

 so just here's a real quick summary of what they do， they just basically， first of all。

 need to distinguish which nodes correspond to pieces of the program。That's the most important。

This note corresponds to a statement。If you looked at some of the examples in the other papers。

 you'll find lots of other nodes that do complicated things that have to do with the implementation that they don't directly correspond to a piece of syntax。

 so identify those nodes。And then tag them and say， well， what interest should a tool have in this。

 well， this is an assignment or this is a statement or it's both。And there's a category for those。

And so the implementer needs to do that， and then finally there's just a few basic methods。

That are extra and the extra one of interest really is eval or you could say take a fragment of code and evaluate it。

Most dynamic languages already have a valveel built in， so it's probably not a big problem。呃。

It's a little harder to add the ability to evveil at a frame in the middle of the stack， for example。

 a lot lot of languages aren't prepared to do that because that doesn't happen in runtime。

But we've been able to sort of make sure that happens。And that's kind of it。

 there's a few other small things about how do you visualize what's the value look like if you want to turn it into a text string that anybody needs to do that。

That's it， if you're a language implementer， you do that， that's the price you pay for anybu。

So we think that's a pretty good value proposition。Caabats， well。

 okay I've already mentioned the implementation is changing， it was prototype code。嗯。

There's been a big architectural change， we now have a set of API frameworks that include everything。

 so things that were prototypes that are being folded into that new。

I mentioned that probes are now kind of virtual。And again。

 there's this focus on the relationship between a place and the program we call that a source。

So that needs to be cleaned， so we're working on that stuff。So what have we built， well。

 first of all， let's sort of look， this is the ecosystem， if you will。

 that we built out as this project has progressed。嗯。

I'll call this the tool ecosystem now so at the bottom is gral truffle and instrumentation。

 this is actually already progress， the reason that's progress is that instrumentation needs to get a separate box。

in the prototype world and after a recent round of work with the framework APIs which are new。

 instrumentation now buried deep in our code base and buried so it's no longer useful to distinguish instrumentation for the rest of the system that's a victory。

 that's sort of the enabling thing that we've done。Okay。

 things we've built with it I mentioned that Ruby does this trace function thing。

our language implementation。Requirement for a shell that has stepping， so it's not really the bugger。

 but you can kind of step and it turns out that that's something that we were able to implement with the instrumentation framework with almost no extra effort。

 so that was a victory。So those are internal kinds of things。We have some external collaborators。

 I'll say a little bit more about some of them in a minute。

 but folks at Irvine did a profiling on their Python implementation。嗯。Let's see the， oh yeah。

 folks in Luganana that one's just kind of starting up， they want to do dynamic program analysis。

 I'll be meeting with them next week。The Kings College folks， they're doing kind of front end tools。

 you front end editors and visualizers and stuff， they're particularly interested in the multiple language environment。

And we'll see actually some examples of that in a minute。

So these are all people who are not part of our labs who have been using this kind of for their own projects。

I mentioned also the debugging API now that's just a service， does a lot of basic stuff。

And for testing and internal use， I built a command line debugger that looks vaguely like an old GDP debugger。

 but It nobody uses that stuff anymore， anybody ever used a GDP command line debugger？Oh good。

 all right so。I'm not that old， okay。Cool， there's no better tools。The best ID for。yeah。

 and why there's no ID previously is another interesting conversation but we don't have to。Yeah。

 I worked with James for a number of years and I know why Java is a better language for。To leniency。

You probably haven't configure figure that out haven't already so but we have another collaboration going on within Oracle with our Ne beanss division and we there's a version of Ne beanss now that uses the Connect to programs running and truffle because you can't use ordinary debugging technology on truffle programs so our API allows net beans that you can actually debug truffle programs。

 anything implemented a truffle you can debug with net beans。

It's not an experimental branch to collaboration ongoing。

 but we're actually thinking that Ne means is becoming to become the full service。

IdeE for anything implemented in truff including this multiple language stuff。

 so we'll see a little more about that。So now I want to show you three demos， we did time。

I'm going to show you something about net beans， which I just mentioned。

And then I'm going to show you my command line client， which I just found a new bug in this morning。

 it's always reliable。And then the work at King's College that's when just now started up。

That I'm sort of supervising at the moment， but they're really interested in editing and they're really interested in editing the problem of if you're combining languages。

Traditional editors so if you're doing multiple language stuff。

But you want to work with a normal file system， a normal editor but you still have to have every language in a different file。

 so we're looking at ways to kind of complete that so let's look at ni meanss。

Here is Ne beanss Poised in some Java code。If you can read that basically there's three little static variables that have snippets of code in three different languages。

SL is our demonstration language， SL for short。Ruby and JavaScript。So those are。Kiny。

 tiny little program code， pieces of code， and but we're a Javava now。And。

The Java code has looked for a globally exported symbol， I believe。

 and is about ready to invoke that symbol， so this is now a cross language method call， if you will。

So you step in there and you find yourself in a piece of JavaScript code。This is not new so far。

 Nemes has been able to step into JavaScript before。

 but only when running on the NASW implementation of JavaScript。

 which is the one that ships with the DK。This now works with the truffle implementation in JavaScript。

And you can see that theres some Java code or rather some JavaScript that imports these two external symbols to implement factorial and so we're going to do this the hard way。

 so the line that we're stopped at is going to do a decrement operation implemented in simple language。

So we'll step into that so if you look you'll see。You can kind of all see what's on the stack and see what's in the frame there what's going on。

So we'll step into again。Now you're in this simple language。

 which I could say it was a point language， but it works， okay。

 so here we are decprementing this variable， and again you'll see there's some simple now then there's some JavaScript and then there's some Java。

 so we've got a multiple language stack going。And then you step back out。

And there we are on the next line， we're about ready to do the next thing we're going to do。

A multiplication operator between two numbers， so let's do it the hard way。

I're going to do that in Ruby， I don't know why。And we're going to step in and now order a piece of rubyco。

As a different syntax。The export operation looks different because you identify methods differently and Ruby just doesn't look the same。

 but it still goes back to this global symbol。And so again。

 this is kind of just a snippet of what it might look like in a multiple language world。

That we can support fairly seamlessly and the interop work they've done is pretty interesting。

It's not a general solution to all languages for all things。

 but there's a lot of situations where you really do want to pass some basic information for one language to another to take advantage of stuff that it can do so for example。

 we have an our implementation there's things are can do that's built hard in other languages。

 for example， so that's a good example where。It's much more easy to see use cases where that really patterns。

And you need tools。How many of you have ever worked in a mixed on environment？Fel your pain。

 usually there's no debugger that we'll do both of them once right。

You step through the interpreter with G。In there gentlemen。掉。When I was here。

 our system was basically implemented in Frances version of columnists with sea for all the。

Gy rendering。You can， you can switch with my team on the same word。And you change the rent。Okay。

 you different if you use different。So again， all tools all the time， it's productivity questions。

 that's why we're trying to focus and leverage this stuff here。So， that's a。That is。

And that means demo just for goods， I'll show you to see if I could make my command line deluer work without too much。

Afulness。嗯。Does that look legible。边个呢。对你。You me make it bigger。Okay， so let's see。

This is actually a subset of the previous demo， so we're in JavaScript。Um，So let's see。

 so this actually， you know， it has a has a respectable command set and actually is anybody who will do stuff。

嗯。And we said， let's say， let's say what languages。So what language is， so there's three languages。

 where they come from。Well， we now have a platform API for registering languages。

 and you basically put a language implementation on your class path。If you put it on your class path。

 the debuggger will find it and you have a fully truized interoperability language available。

And the current language is JavaScriptscript， okay， so I can change。

Change that but I in JavaScript if I could just say a vow。Seven。

 and this is just a top level evaluation right I mean there's no programs running yet but I can just it's kind of like to ripple and I can change to simple。

But if I try and do that。It doesn't work。 reason to work is that the。

Simple is an example of a language that doesn't do naturally having a valid and you can't parsese fragment。

 so that doesn't help。So let's load some code。And let's see。That's load。

So you should recognize this name， this is the simple language decrementer。

And then let's load a version of the factial。Okay， and there we are。

And so now we're at the top level and just like in the Java， we look for an exported symbol。

Except I think it's broken right now。In fact， I know it's broken if I try and call that symbol little break。

That I should be able to do this。It is。那。Okay， so that is a debugger call that。Says， you know。

 here's a global symbol， here's some arguments actually run it， and as if it were an interoper call。

 I know upbreaks， I'm not even going to bother I run it。嗯。The debuer won't break。

 it just throws an exception that the debuggger says。

But I can also do anow since I'm in JavaScript also I'm in the environment so I'm actually in the language environment of what's on the top of the stack。

 which is JavaScript， wherever you stop， there's a language context for the halted program and it says right there that that's JavaScript so I know what language is listening。

Its， so I can still as before I can say， you know， you validate， but I can also say。Oh。

 that's broken， too。ok。Oh， no， because they haven't run yet。Okay， so that's what I can do though。

 yeah。Well。Okay， so that's a legitimate JavaScript thing that's been defined and so if I run that it's just going to work okay。

 so I'm in JavaScript。But I can also step into so I can say DLS。This is the standard debugging thing。

And I say yes， I means I want to step into and halt at the first statement。Well， well。

 the first statement as it turns out， is my F of five called curious， so if I say what's on my stack。

 well， I'm in this program called F of5 okay？嗯。And I need to step twice to get out of it。 It's about。

 okay， and now I've actually stepped into this function， so if I do。see here I am okay。

 so I in two different places。嗯。And this is， nowll， I'm just an ordinary debugger。

 I can sort of say step。I can say next and whatever OK。

 but here I'm poised now to make that same cross language call now if I say you invalidin。

You'll see that actually there， mean I'm in this actual language context。

 I say step into and cheer enough there I am in simple。You can see where I'm in the back trace。

 you'll see there's a separate frame stack frame in there that's at the interop call。

 not particularly usefully displayed at the moment， but again， it's a multi languagegu stack。

And then I can say well what's this frame look like see the commands are all pretty much language agnostic right this is a frame in JavaScript。

 this is a frame and simple， I just can't out here if I step。Back out again， you know， here I am。

And I can say， well， what's the frame here and you can see again。

Just basically abu just the only difference is it's sort of language agnostic in almost every case。

 there's very， very， very few things here that are language specific so far。

So that's an example of a client of the debugging code。Second client， if you will。

And for the third client。I'm going to show you a video of what our collaborators at King's College have most recently done。

 they've only been doing this for a couple of months。

I'm going to have to turn the audio up really loud。There might be an audio plug somewhere is there。

 I don't know if it'll work。是。Okay。对我。あそうした。Okay。したオ。Is this actually shown up。It。楚。

anythingThere's another one over on。这是一号人2。I've had good success with just running off the exiting。

关灯我呢个备。Yeah just。这个大。We'll hear action。そしてと。会复是。Point in your direction so you can hear it。

Eco is a unique editor developed by the softwareware development team at King's College Land。

It has the look and feel of an ordinary text editor。

 but has the ability to parse multiple languages with the power of a syntax directed editor。

It allows us to write and view polyglot or composed programs with ease， as we'll soon see。

This program is written in Oracle simpleple language， a cutdown version of JavaScript。

The blue overlay here shows a new feature of ECO that we are working on。

 the automatic visualization of runtime behavior of polyglock code。

The blue highlights show the results of the Tffle Code coverage tool， the darker the heat map。

 the more times the line of code will be executed at run time。

 to see more detailed information from the profiler。

 the programmer can hover over the text here to see textual information on tool tips。切。

Profile of information here is stored with the AST notes， so if we change some of the code。

 we can readaw the heat map automatically to show the new changes。Yeah。

This file contains Pocock code， the code with the white background is written in J Ruby and the code with the pink background is in simple language。

Cel has support for running these polylo programs and Eco allows us to view and edit Poclot code in a single farm。

 Eco also enables us to visualize cross language profiling in exactly the same way that we were able to examine the simple language example earlier。

As with the previous example， the heat map here is drawn by the code coverageage plugin from travel。

The simple language function clam。It's been called by the Ruy code at the end of the file 10 times。

 so the number of paths through clam that the profiler has taken will add up to 10。

This is easier to see if we turn off the visualization of the language boxes which denate the boundaries between the J Ruby and simple language code。

As with the previous example， the heat map is drawn live， so if we change the code we're editing。

 we can rerun the profiler to refresh the information we're seeing。As we have seen in this demo。

 Eco allows users to do two unique things。Firstly， we can write and run polyglolock programs in a single text view。

 and secondly， Eco can easily visualise cross language program analyses。Thank you for what。

So three different clients of the instrumentation framework and debugging API。嗯。

And we're pretty optimistic， this is a one year collaboration that we're only two months into。

 so I'm really looking forward to seeing。What they give up会。

How much demand is there for multiple languages in one file。Well。

 if you're going to deal with true multi languageage systems。

 it would be a productivity improvement not to have to have them separate。

 files a lousy abstraction for programming anyway。Sure， but I mean。

 like and presumably your file shouldn't be that big to begin with。

 You probably want to I don't know， few hundred lines right language， of course。嗯。我理系好。

Maybe a little bit different， but we have or here so seaful is always jammed in。Right， so yeah。

 people do program for Or program in PL SQL， which is。

PL SQL is an Elum that allows you to embed SQL queries。

And then you can actually embed code fragments into de sequL in some situations as well。

And as we are， we are。Pioneering a trajectory that we hope will let us run some of these dynamic languages。

 Ruby R， JavaScriptscript in the database safely and quickly and fast。

we think this is an opportunity， but again， this is obviously the kind of research that's one of the reasons it's being done by a university collaborator because it's kind of one of those slightly over the horizon things。

Thereforefore properly done by university research group and they've been doing multiple language work for years they actually have some very interesting history behind them in this area。

 so having them poured onto our system creates some opportunities for stuff that we can try。

So even though in a sense we're looking towards the issues that are understood at our。

 part of our job is to create opportunities for things that haven't thought about yet。Yeah。

 do you have to run the problem Ali once to figure out。So how many times。Well， yeah。

 I mean I think I understand your question it's a dynamic tool， so yeah。

 you run it in count background。The tour actually rest。Yes， oh yeah。

 she would pull on the menu that would say run。And it would rerun the code and then refresh the numbers down。

 so she was explicitly running it。What the program takes in parent so they changes Yeah， well。

 you'd have to write a call method somewhere in the file and then say run this line or something？You。

 if fell this line then we would do the same thing， but yeah。

 that she was sort of manually changing the constants right but it would be the same way。

So the profile is for certain。Yes， exactly。And one can imagine a lot of audit。

 I mean this is a two month prototype right， this is really just a proof of concept that they can get runtime data back out of truuffle them into their head。

One can imagine a framework。That whole IDD framework that anybody just has this stuff done。

Pretty interesting。To be able to sort of get some approximate performance feedback on your changes sort of step by step。

たく。Another question that since this is a modified version of Galva on travel。

So how do you guys manage to think is the mainstream JavaScriptscript。Well， actually。

 I don't think of it as modified， they're actually ahead of some other groups on ECN6。

 right I ours is the only fully compliant ECN6 implementation that we we are ahead of the curve。

So it's there slow movie you guys that have a problem？Yeah， okay， so I mentioned these guys， so okay。

 so here's my finale， so for those of you who decided that you have a career ahead building virtual machines。

I'm quitting it straight to you， here's what I want。

No language implementation is complete without tools for programmers， remember programmers tools。

The people。No language implementation team is complete without tool builders。

 even if you have one random person such as myself to sort of stand up and make the argument。Okay。

 and gather the data and help create the use cases。

 you should not let people who are in charge of running curves fast think about what users want to do。

It's established scientific fact that people who write compilers cannot think about programs the same thing。

They trained out of them， it's just an effective life。嗯。

And I cited a book one of my earlier slides where you I say no， it's really not right。

 the programs are not like that。It's a whole book about the cognitive issues around programming and how people think about code。

And the one way in which people do not think about code is as abstract syns。是是。

And no platform is complete without tooling support， and that's us， so go。

A few brief acknowledgeknowgments， a subset of Mario's， basically all YouTube builders， however。

And so let me thanks， thank you for listening， some of these papers here I listed you've already seen in。

 I think maybe one of you haven't seen yet， that's the across by Detens book on softwareft Design cognitivetive aspects。

 it's an old book， but it's best we have。And ask me about summer internships。

 we have sent a thing and there's my email。So any questions or discussion before we？こまる。Beer。

A trash right。PaPatrick， I've been called Peter。So optimizing away in the checks that you've shown。

I notice that。You still have this reliance that the checks。Executing in the same way。optimizeマま。

So we're doing。Reersal type。That's a great question， I don't have a good answer for you。

So let me understand the question a bit more， I。And so what's this give me an example scenario。

If you arrive， tune nest the loops。Let's say major is multiplied if you assume that。

You can't observe the intermediatemediacy of the program。

And anything that calculates the same result is the same right。

 and fancy compilers often switch the orders， right？Yestra has。

Which means that if you while it's running， you click brick here。Well。

 now you're in the middle of an execution stream that doesn't actually have a analogous。 No。

 what what what we do， what our system would do was it would de optimizetim and。

The system would look as if it was always executing the loops the way he wrote them。

 where the state would be wrong then， yeah， like there is no equipment。

So it depends on where the safe points are inserted。If there's a safe point on the inner looppe。

 then it's on the inner loop， they can't。The safe point has to be able to recover to a canal state as if you were interpreting。

And loop any optimization， which validates that as an incorrect optimization。

If you don't want to observe the insides of the loop。

 then you don't put the same in and then you can't observe it well this is the problem I often have with like turning the bugging on is that the bug doesn't show up until 10 minutes later and so turning the bugging on means I have to wait half an hour until I actually can see where the bug failed so removing optimizes not be should only happen small section that I need it everywhere else it should be just fully optimized as possible。

And I haven't seen a very good tool to did this。给这么多给。Okay。

 let's take Simon minute break and just in case you're curious。回。apologizesacle。

Its mostly garbage' collection。A couple of other minor things worth mentioning。

Now as I said in the original memory management。Material， it's not just reclamation。

 it's allocation and all of the other the barrier stuff as well。

 so we'll talk a little bit about those things too。嗯。First about stacks。

 so if you have multi threading you need multiple stacks。

 multiple stacks gives you the opportunities of fragmentation because how big do you make your stack you know it's easy in the world where your data grows in one direction and the stack goes down。

And you own a memory when they meet， but when you've got multiple liness you to do something different。

啊。So the crew solution is to use virtual memory tricks， you know。

 prelocate a bunch of address space for stacks， but don't populate the address space with actual memory。

And every modern OS lets you do that。And that's what most implementations do。

 it's crude what effective， you know， a dress space special on 64 bit machines is plentiful 32 bit machines。

 maybe not so much。And that's what they do all back in the autumn days。

 people used to do much more complicated stack management regimes when memory was tighter or maybe they didn't have virtual memory。

And they did things like spaghetti snacks， there's also something called a capa stack。

Where your stack is， you know， discrete segments and you have to deal when you return out of one with sort of。

Making sure the frame and the stack pie are la at the top of the， the one below it。

But it's possible a little bit of extra code generation and some trampoline codes and it's possible and that gives you then the ability to have a piece of stack in any chunk of memory that happens to be phrased the stacks don't have to be contiguous and they can grow and shrink and they don't end up you know you know you don't die when one threads stack is exhausted。

 memory has to be exhausted to die and it's surprising I find it surprising that this solution is still。

Used almost everywhere and that you know， I look at say the GVM and the fact that you have to specify the threads stack size on the command line。

 that's just like a boat。Why do I have to do that and why do I have to know what the stack size is。

 I got this memory and just use it。But that's what the current Vs do。And。

There doesn't seem to be any need。Strong motivation to fix it。嗯。

The other thing we're saying a little bit about is allocation， we've got multiple threads allocating。

 they're all allocating in the same heap， we don't want to take a lock on the heap every time we do an allocation because I'll just serialize everybody it's really really bad and those were a simple technique which I'm sure everyone could invent。

30 seconds of thought， which is thread local allocation buffer。

 basically what you do is you take the lock to allocate a big object。You know， 100 kilobytes。

 and then you allocate little objects over the big object。And because it's thread local。

 you don't need a lock for the internal allocations。

 you do get the same issue as of resource allocation。

 you know how big should that guy be the bigger you can make it then the more internal allocations you can do without locking before you have to get locked again。

What you more space you waste and if you have a big server application with hundreds of thousands or many thousands of threads。

 you're allocating a big chunk for all those threads that are sitting there doing nothing just waiting for an incoming request。

Is clearly wasteful so the elaboration here gets into adaptive schemes that detect when the threads beginning to get aggressive about allocating space and giving get ever bigger so typically if you allocate if you use your Tla within a certain time。

 the next one you make twice as big in the next one twice as big as that and so on and then you shrink them back stuff like that it gets kind of messy but it's doable this is the way Mopot does it。

嗯。The the unfortunate part of that， of course， is that you can only have。

As much contention as you have hardware threads， but you have a lot more software threads than you have hardware threads Yes。

 we have an atomic memory operation that would take this for to just allocate the。

Not have to lock you just allocate that mountain memory。And when you run out。

 then you have to walk and then you have to create up up until that point you should be fine。

 you only need to have a dedicated buffer space for each to rent。

I can out do a whatever my heat pointer is I atomically add not I need and I check to see if I go overflow if I done that I every lock it out and then go。

It's under the assumption that I run out of heat rarely。

You have to also deal with I'm not saying that this is not addressable with what you said。

 but you also have to deal with the fact that in that interval the thing is in an unneationialized state right and so anyone else their peaks in there ask to not seeing but when you in the Hue pointer they can't peek down right？

So you've already had you pre allocatelocate， then you start setting a load of your stuff。

 but you do the pre allocationlocation first and then you do all sensation。When you using cast yeah。

 something like a cast yeah， quite。Now there is sort some costs。mean CAS are still right。

 but that maps a very nice low overhead thing right well let's still traffic out deal with actually overhead。

呃，跟正行业。虽了。So， so yeah， I mean， the C lab is， you know。

 effectively doing that for the big chunk and then in the and because it's thread local。

 you you know， they a walking。你唱。So I was going to say it seems to make sense。

 I do this have one of these per processor and not one per thread。

 but unfortunately the general purpose O is don't give you all scheduler information to really avoid that。

Idally， if you do your own in the West， then you can make that work。

What General Court O is it doesn't seem to be profitable to try and make that work。

There have been tricks where people have run with exactly the same number of native threads as hardware threads and then multiplex the language threads onto those threads attempt to exploit this。

No one really seems to have pulled it off completely successfully。Okay， so let's talk about。

Let's talk about garbage collection， we'll start with some terminology。

So this is the picture that we've kind of been operating under so far。

 which is a single thread where we alternate between mutation and collection。嗯。

The easy extension is to go to this kind of a picture with multiple musa threads and a single collection thread。

And a barrier that says when we decide to collect， we have to suspend all the new as we do our collection and we'll resume them all。

嗯。But what you'd really like to get to is something like this where you're doing all of the collection in parallel。

When you decide to collect now， of course， that picture。

 this is a picture you find in the books and that's not the reality right， the reality is this。

Which is one of these guides decides it's time to collect。

 the others all have to be brought to a hole。Then all these guys have to be restarted and in the interim nothing useful is happening in these gaps and the same but every time you do a stretch in this kind of a scheme。

 so this is known as parallel collection， the terminology here I find is bizarre。

 so parallel means the collectors are running in parallel。

 but not at the same time as a mutator and concurrent means the collector and mutator is running。

At the same time。Seems like kind of arbitrary they could have picked either way around and it would have。

You know， the previous meanings of those words would not have affected the outcome。

 but that's the way the literature is settled and so I tell you this just so that you know what when you see the words you'll know what they mean。

So so how do we get there Well first let's do a little bit of revision because there's some terminology that makes this all a lot simpler to think about I mentioned the tricolder abstraction we're backing in the GC slides and this is the same material from there so the idea is we where every node in our graph every object in the heap is。

One of three colors， white means might be dead or alive。

 we haven't done anything whether it we still have to visit it， G means we've decided it's alive。

 what we haven't yet processed yet to figure out what it refers to and color it nows。

And black means we're done with that and we don't want to go back to it。

And we want to progress from white to gray to black or white to black。

 and we don't go backwards generally speaking， we'll get to some exceptions to that later。

And just to make it concrete， you can watch of the movie again， so as we color out from the roots。

 we color things gray as we process them。We make them black。So we've dealt with B andC they at black。

Scan E， which means coloring the things it refers to。

And then we color that black and so on and so forth。Fairly。

Straight now in the well we'll get to the concurrent world in a minute with。Collction forest。

So in a parallel collector， the correctness problem is not so difficult because the mutator and the parallel collector are not really put concurrently right they are。

 that's a bug， that's the first bug you have to fix which you are overlapping because they're not mental overlap lack。

The challenges are all in efficiency so what you've got to do is be able to suspend all the news heaters and then restart them in a timely way and do the same with the collectors and that's the tricky part making that scale well so that you could do that for large numbers of threats。

 particularly you on a big system and I refer you back to Cl clicks。

Points about this and in particular the scheme that they used。

 which was to always make sure that when you suspend a threat it's suspended out a safe point so you don't have to resume it just to get it a safe point so that you can actually do the stack or the stack scanning。

嗯。And that's easier done with hardware support or a schedule of support， yes， the previous。

And why as many strategies have processors。I wish is some multiplepls， yes。With that。Yeah。

 that helps with that because then your scheduler， if you write the scheduler。

 you could make this work。But if you're relying on stock OS and stock preemption。

Then you get into this problem that stuff gets preempted at arbitrary boundaries and before you GC a thread。

 you have to be able to advance it to where it's safe to G safe which meanss。

 taking it to a GC safe point or doing something even more devilish like tracking， you。

 being able to abstractly interpret up to that point from the last GC point or something。

So what did I。呃满呆呆啊。They're there。 And， you know， they're own everybody's machines， so。

When you build a language implementation， it's not a strong selling point to say， oh by the way。

 you need our customer I to learn this language。呃。我嚟嚟呢俾佢。かす。Yeah。

 but that's really a simple thread of implementation isn right， yeah。

 so there you get no concurrtency advantages。designsigning kind of system。I would launch as many。

That processors。It's been done。 It just wasn't very successful。

 It's hard because everything you're going against the grain on everything。You know。

 the underlying system is trying to preempt you。And you're trying to not be preempted or to manage the preemption。

Okay， so suspending and restarting。You've were armed alls law to deal with if there's anything serial and they're collective and parallellyzizing isnt going help。

And you're going to spread the load evenly because you're walking the graph。During collection。

 you don't know what the shape of the graph is。 You don't know how far you're going to go down it from any particular。

From any particular starting point， so you have to probably do something like work stealing to balance。

What you can do， however， is to have just the same number of parallel collective threads as there are core because you know not use the same threads for collection as you're using for mutation。

 so you bring all the mutators to a start of the parallel collection threads and now are evenly balanced that leads in thread camps and then resume all the mutators。

When you're down， so that's a trick that does work and it's quite effective。

So the general power Valley。In a parallel collector is each thread is running a loop that looks something like this。

 you know， is there something left to do， then I'm going to figure out what I'm going to do next。

 I'm going to do it and there's a side effect I'm going to generate some more work to be done and put that into the pool for either me or one of the other threads to do we keep doing this until there is no work to do and there has to be some kind of you know termination condition that that will get us to that do the first two steps required some sort of the coordination or looking pulling work so it depends exactly we'll look at out an example or two So the example of this is parallel marking Okay so the work list here is the set of gray objects because that's the frontier up。

Of where you know， you've got to go。After all of the things you've visited and you don't want to visit again and the white things you haven't got there yet so you don't know that so the set the things that you're working on is the set of gray objects and so the the acquire phase is take one at least gray object from the work list know atomically so though you have to have some kind of coordination and say I'm going work on this。

 you don't get to work on this， I'm going to deal with it So actually deal with it you've traced its reference and share them。

The appropriate color and stick them on the last。That's the alter generating work and doing work are combined and then once you're done that thing's done and we want to picking up the next one so and we're done when the set is empty。

Now， if you do this literally on one object at a time。

 then you're going to contend for the lock on the set。Hugely right。

 So you probably want to grab more than that or you want to come decompose the set into bigger entities which are thread local and then have stealing to pull stuff out of the other guy。

 So when yours is empty， you look around and go he' still got a lot to do。

 I want to take some of his stuff。This is not really tied directly to parallel stuff。

 what it's worth mentioning at this point， which is if you're going one of the difficulties here is because you're walking a graph through memory and the pointers can point anywhere many of the first loads to an object are going to miss in the caches and so you can mitigate that partly by doing a prefecture as soon as you've got the object that you're going to process in your hand you find some pointers from that thing and you issue prefectures because you know you're going to visit those again soon now that only works if you're going to visit them again soon on the same processor there's not point doing a prefechture here when the other guys going to take the thing off the cube so one solution here would do to pull a bunch of things off the set for you to work on issue a bunch of prefettures。

 make sure that all of those things are going to be yours and then。

Let the other guys work on their own piece。So as I think I just said this。

 having a single list of gives contention per worker lists lead to unbalanced processing because you don't have the shape of the graph so you know one。

W one starting point might only refer to a single object and the other one might revive everything else in heap。

And if you just run those without any work steal， it's not any faster bi parallelizing because you' only get one thing done in parallel with the medicine。

就话。Okay， parallel copying， that's a little harder because parallel marking marking is generally speaking of emputton。

So copying is not。So you have to be a little bit more careful about how you do stuff you don't want to copy things in。

 you have to install a point for in pointer you know。

 acquire and install and copy all in a way that makes sure that no one else is going to。

Do that in trip over each other。嗯。When you get into copying rather than mark a common technique is divided。

 the heat painted chunks， you know I on this chunk of your that chunk I have a work list of things to do in this chunk。

 if I find a pointer into your chunk I give you the thing to do and everybody works on their chunk and you also helps with things like uniformity and memory access。

 you know if you can make sure the chunks are mapped into your piece of memory attached to your processor then that helps with the performance there too。

Paraallel sweeping is kind of an interesting thing because you actually don't have to do it。嗯。

With the muts off right， sweeping only touches the dead objects。 And so as soon as you're done。

Identifying the dead objects， you can restart the mu。

 and they can start running and the sweeper can start running can running parallels。

 running through memory， finding the dead objects and putting them onto the list。

 It has to deal with。You know， has to make we'd be able to walk and use hittingating heap so scanning the heap might be a little challenging。

 but if they're if for example， all your dead things are on the free list or on lists that are generated as a side effect of marking。

 then you can process those things separately and add them onto the。

The lists that the muts are taken from so that can can be these can run in parallel with mutation。

And if you do that， however， you' need to put some synchronization in the allocator because if the allocators get ahead of the freer and you run out of memory。

 you want to wait until the freer is done free before you decide that you really have run out。

There's a bit of synchronization。Okay， so parallel collection is being used。

 there's a parallel generations scavenger and hotpot， which is used in very big installations。

 you know， big multiprocesor systems typically in the financial world where they make。

Most of the memory being the new generation。And it。

 you know kicks in and it runs in parallel and a whole bunch of cores and scavengs。

But it's otherwise， it's a fairly。Fly ob。If you look in the literature。

 you find much more on concurrent collection， so instead of this picture。

Where stuff is happening in phases， we have this picture， which is。

 you know the collector is running。啊龙。In parallel the mutation， kind of an arbitrary period。

 in fact there's a much better categorization of this in the book。With with finer distinctions。

 but I don't know enough the time you go into that。So they。

The interesting thing with this is that this picture is actually。呃，是。

The losses over the some of the truth， which is that really if we zoom in on this and we take our two threads and we get them down to the size that we can see individual instructions now what's really going on is we are barrier code even in the mutator that's doing stuff which has to synchronize with the collector。

So it might look gray， but really you've got barriers in there。

Read barriers or write barriers around the pointer reads and the pointer arise。

 and the purpose of those is to make sure that the invariance that the collector needs are maintained by the mutator and everything is hunky Do。

So the challenges are manyfold。嗯。So the collector has to be correct and correctness is non-trivial now。

 it's really really difficult to figure out what's going on because know you have a graph that's being mutated under your feet as you're walking。

 which is challenging in the best of circumstances。It has to be fairly efficient。

 so it needs to be able to keep up with the mutators， you know。

 if you're reclaiming but you're recclaiming so slowly that youre run out of memory。

 that's not useful。It has to have。So pauses are as low as possible because the whole point of having a concurrent collector is to spread the pauses out among solar mutationsus so there isn't a stop the world pauses。

 you know， holding up any individual thing for very long and you know holding up the system at all。

And。It has to be timely， so it can't leave garbage floating in the heat for long periods of time because now then you need a massive heap。

to deal with a relatively small set of live objects and perhaps the most difficult thing is to do this without slowing the muters down a lot。

 So those instructions that you have to sprinkle in the muter code have to be short enough。

And cheap enough that you're not making the muts horribly inefficient。You know。

 if we relax any of these things sort of to its extreme point。

 then all of the others become almost trivially easy to solve the difficult problem here is making them all balanced so that you've got a system which has good characteristics。

Reasonably good characteristics in all of those， no terrible characteristics。

And he's good in at least one or more。或者 fundamental里面都 check。Sorry。So the tension。

 is it just hard to get everything right at once or is there actually there is no known solution for how to get them all？

Good at the same time。've been the same algorithm。That's an open problem and whether it's an insoluble problem as well or a soluble problem。

 but where it's just not smart enough， I'm not smart enough to tell you。

And no one else has come up with a good argument one way or the other for whether it's like。

 sort of the equivalent of MP hard it's obviously not a complexity issue there。

Isn there some kind of an engineering obstacle？What't this what a Z is doing with their custom hardware though？

With the barriers built into the hardware。You know， you get to a point where。

You're just pushing the dirt under a different part of the rug and it looks good。

 but when you look at where the dirt is it's somewhere else so in their system for example。

 it looks like there are new policies。But right after you do a flip。

 you've invalidated a whole bunch of page mappings。

Because the GC relies on TLB naps being different for the GC you're just invalidated a bunch of those and there's going to be a storm of remapping events which well a pause is a pause right the end user isn't going to look at it and go well that of TLB reapping pause that doesn't happen as a pause you know I can live with that it's still a pause right and there's actually extremely scan data I believe it's because they prohibit publication of。

嗯。Metrics on the system when you buy one， you can't measure it and publish the data so no one really knows。

And if I knew I couldn't tell you， but I don't actually know I've never hard。

 but I look at the paper and I think， oh that looks like a weakness to me。So。Okay， so。

So I said correctness is difficult to establish here， debugging is a nightmare because you know。

 no two runs the same right unless so actually there's been a bunch of people worked on trying to establish a framework in which that's reproducible。

So you make a run and you can reproduce the timings and everything so you can de bucket it。

 but in real production systems you can't and so the nightmare here is someone gives you a thumb drive with a 50 gigabyte heat dump and says this crashed。

There you go， find out what went wrong。And you don't get to rerun it and you have to try and figure it out from there and there are people who did this。

 you know， for a living。They were underpaid， they were underpaid。YeahIt's really hard。Also。

 you can't do some of the tricks that are I mentioned in the earlier lectures which。

Are invalid in the presence of apparent concurrent mutser so you know reversing the pointers through stuff that's fine in some techniques。

 but the muters is going to have to deal with whatever you do so that takes a whole bunch of techniques off the table。

And then the barrier code。The barrier code is really hard to do in a system like this in make light is bad enough to get this light enough in a right barrier。

 but if it's in a re barrier you know，The frequency is probably five times higher than it was in a right barrier and if you add 10 instructions into a eat barrier。

 the system is going to be really slow。So。Solving all of those things is non trivial。One interesting。

 so this book， my admiration for this book has gone up。

Since I'm going to look through it again this week。嗯。

Half of this book is about concurrent and parallel GC。And the real contribution。

 which is kind of unstated。Is that they've taken a whole bunch of the literature on concurrent and parallel collection。

And they've put it in a framework which didn't exist before which makes it very easy to describe the differences and the variations in the techniques。

 and that's something that's a really valuable thing that you know should have been like a good research pay somewhere。

 but it's just in the book as far as I know。And is motivated by this scenario。

Which is we have this group of objects bike and way。

 and our garbage collector is walking there or you know， there are other objects。

 obviously on this picture， walking them。And it's trying to color the gray things。

 the black and the white things， the gray and then ultimately black， and while it's doing that。

We copy the pointer to the white guy。In the black guy。And we drop。That pointer。

 and now we have a white pointer and a black object， which we're never going to revisit。

So if we never revisit that and we never caught that move and or the destruction， we're dead， right。

 this is incorrect。 We're going to reclaim the Y object。And。然后。

We're going to get that heated up in the mail to analyze。Somewhere down there。Down the road。

A good research contribution from some years ago analyzed the situation and said there's two things that need to happen for this to be a problem。

One is that you store a pointer to a white object into a black object and。

All passed from any of the gray objects to that wise object get destroyed。

Both of those conditions have to be trued for this problem to occur。

 and so there are now a couple of different ways of attacking the problem。

One is to adopt what's called the strong tricolic variant。

 which is never pull pointers to white objects and black objects。

That means when you try and do that pointer door， you have to color the white object before the pointer door succeeds。

And thats that has to be adopted by anything that's never going to revisit the black objects or copy and collector and when I want you copy it。

 if you put it on the other side of the fence， you're never going to go back and visit that guy again。

 you have to adopt this strategy。The alternative is to break the other condition。

Which is that all white objects pointed to by a black object are gray perspectiveceptive。

 not quite as crisp as the previous slide， which was easy to understand。But that means that path。

 if you break that path。You have have to detect that you've broken the path and do something。

 either prevent the path from being broken or just the colors in the way that's legal and this is like a weaker condition it's implied by the earlier one if you guarantee the earlier one you guarantee this one。

 but it's used in some cases。To success and this is a really nice way of classifying all the different approaches。

 because if you go through the literature。You know， you have， I don't know。

100 papers all written by different people in a different style。

 very different languages and different approaches and trying to figure out what the differences are amongst all of these things from the papers。

 it's just a horrible， it's a horrible， horrible job。And this has done all that for you。

 right it's gone through they figuring out what all of the different conditions are of you know。

made it all neutral relative to the languages and the systems that they were implementing and just say。

 okay， this is one that relaxes that condition of works。

 that condition and here's how it does it and here's the various different barriers。

That's good practice。Okay， so one of the ways they do this is that they think about the mutators themselves having a color。

So。When。When you scan the stack of a thread， then you've colored it in somewhere way。

 you've either colored it gray or you've colored it black。

 depending on what you've done with the stack scale。

The stack can be a frame at a time and when usually you pause the thread when you're scanning it。

 it's kind of hard to make that workwhile running。But you pause the thread。

 you scan one or more frames， you color those frames， maybe you do the whole stack。

 and then you let the thread resume。And that gives you whether that color is black。

Or gray is one of the distinctions in how you classify the algorithms。

So a gray frame can refer to objects of any color but black frames after。After refer to grayframes。

 if using it's a gray object， if he're using the strong invariant。

And the other way of thinking about it is what's the color of a newly allocated object？

I it white or gray or black？If it's gray or black， that means that by implication in this GC cycle that's never going to be reclaim price。

 you're going to have to work for the start of the next cycle for it to be eligible for it to be white again because you don't reclaim gray or black。

Thanks， so。But black mutators can't allocate why objects in their roots if they're following the strong invari whereas a gray mut account。

 so that's another axis of division。And then the barrier actions that are performed within a read or write barrier help distinguish so you've got only a few things that you can do。

 you can take a white object and you could she it gray， adding it to the wave front and shading。

Greray or black。 sorry， and。Changing the color of。The object。

And then they treats sheing of gray or black as they know up。

You could scan a gray object to make it black and thereby advance the wave from in some situations they retreat the wave from by reversing an object from black to gray。

 and that helps with the second invariant in some cases。

And all the other actions break one of thosevaris。 so it's kind of a combination of these things。

 so what combination is it and how are they。They're composed one of the classes of solutions called snapnapshot at the beginning。

 which logically speaking takes a snapshot of the heat as it stands at one moment in time。

And the collector only considers that version of the world because that already has some garbage in there。

The objects and it may change， but if you look at the graph as it was at that point。

 then you can reclaim the garbage that existed at that time。

 so logically it's a snapchshot physically you can actually implement this using virtual memory tricks as a snaptshot。

 but there are also tricks that maintain a logical view but not a physical view。

And then the right barrier protects against the deletion of。

 so when you're mutating objects in the live copy， you make sure that you don't violate the weakvari by deleting pointers to things that might get snued away。

And because it's a snapshot， we're basically taking all of the threads。

Coloring them black at the beginning。Another class of techniques has the mututators being gray。

 and they use the strong invariant and the right barrier to prevent storing wide pointers into black object。

 but you don't need to read barrier in those cases。And an example， there are lots in the book。

 I pick this one because it should be very close to what you're familiar with Baker's algorithm is you're copying garbage collector with a little bit of a tweak。

So in the Baker's algorithm， what we do is that the beginning of collection。

 the heap in frontron space is white。We stand the stack。

And everything that we find referred to from the stack。

We copy a two space and we colorerate gray hair bypoing it into space and then our mutator was effectively called black that's exactly the same as what you've implemented。

 I believe。The trick is， though that we then resume the mutator。Having done that。

 the mutator has never own it。And to make sure that everything works correctly。

 the mutes add a read barrier so that anytime it tries to read a white pointer。

The read barrier traps， the object referred to is copied into two space and it gets a pointer back to the new copy in two space。

 so it never sees anything in front spaces anymore。

 The mutator only sees stuff in two spaces tries to access anything in from space to see a pointer it gets mutated。

 So in effect the mutator is driving the copying before you。

 Everything it sees that hasn't already been copied， gets copied。

And in parallel with that or interleaved with it， you have your normal copying garbage collection process。

 which can be incremental now， the minimum increment is one object。Finds a thing opposite。

Resumeness of the mutators and finds a in opposite， essential。

 that's just nice serial implementation。The original version of this was a serial implementation and it was one of the first incremental algorithms because the max。

 the pauseime was bounded by the time to copy one object。

And then eventually the combination of the mutator and the collector drive all of the white objects into the gray area。

 you process all the gray things， they'll become black and you don't， you flip。

 you go back and it's actually the only thing you have to do from your code to make this is really put the re area。

And then you'd have a working incremental collector。So I present that one only because it's。

Clloose to what you're familiar with， the book has many others and there。

From difficult to mind bendending I mean they're really very。

 very challenging algorithms to understand， especially if you start from the original descriptions。

 the book has done a very nice job of distilling out the differences and saying。

 well it deals is this thing in the right bar and it's a gray mutator with why new objects and kind of that's all you need to know so it's really really nice。

 you can go through it and try and match。Match the algorithm to your requirements all of them however。

 have weaknesses in some case or another， sometimes the witnesses are very hard to figure out they all have weaknesses because otherwise one of them will dominate now and they don't。

And there's a lot of material in book I haven't had time to talk about concurrent reference counting。

 which is another chapter in the book， I actually don't know anyone who does that and realtime GC which I just don't understand as all。

Which is the last chapter of the book and just seems like an ox moumto me， but I still have to。

Figure out what they mean by that。The final thing I'll mention。

There's something that isn't in the book， which is layering of collectives， right。

 You can build a system using a whole bunch of different GC techniques just by layering them one on top of the other and having。

Barriers maintain sets of pointers from one space and the politician the he， a barrier says， okay。

 this guy is pointers to that space of the roots for that space's collection。And。

It's fairly straightforward to do this actually it's not very difficult so you can think of generation scavenging as a layering of copying collector over a mark sweep collector。

Hotspot does parallel scavenging for the young generation and a variety of concurrent techniques with the old generation。

 and I've worked on a system that used marking， copying and reference counting reference counting is attractive in bulk storage because。

Pointers on desk don't change。The reference can is don' up there except from memory and you can store Dltas。

The updates and the pointer。In memory so that when you bring it back in。

 you can combine that with its original reference cabinet reclaim it's an interesting technique for bulk storage。

Okay， that's the end of the GC section， any questions on that before we go to the composition？

So just a general question on congrent D what， I mean。

 what kind of performance overhead do they have。like on the total runtime of maybe any so for example。

 if you have a server process， which is not really interactive。

 it's a pretty substantial penalty depending on。How small you want the pauses to be。

So tens of percent is not unusual， even with occasional long pauses。

 if you want no occasional long pauses， your pause intolerant， 2 x，3 x。Kind of in that range，5 x。

 depending on how well engineered it is。The last you know， percentile of long pauses is very。

 very hard to eliminate without losing a lot of efficiency。

 that seems to be where the practice is right down。If you look at something like hotspot。

 it has this G1 collection， which is concurrent in the old space。

And that's probably 20 or 30% lower than if you said， I'm running a batch program。

 I have no user interaction， I don't care what the pauses are。

 you know I'll use Moweep or something like that in the old space because the barrier。

 it's like 10 instructions it's not revealed。从那吃。Okay。Ptition time。有啊。So， we have five。

Applicant teams。诶。Anyone bring a drum？真的。Okay， so I just have a bunch of measure times。

So I took all of your benchmarks， the score was， you guess。

Whoever runs past this gets 100 points for that benchmarkmark。

 everyone else gets the percentage of whatever the achieve quality class is one。

So this is benchmark one， is benchmark？So。な是。Right。

 do you want to explain what the benchmark is supposed to do This was actually just a simple reunite of pseudouttu。

 which used box intes instead of inte。Every box level box at the， so it's it's a class。 I mean。

 you have the value inside an object and its it's actually like a big two or three levels of。第系。

And yeah， that's what was on the what did you， what optimization are you got。Well， yeah。

 so I guess I guess the main one for this was the fact that。

A lot of the operations were on gettings and setting slots of。

That were defined in a type that was higher up from the type of the actual object as as method。

 so that's not something that we introduced to do between these prototype。

So what we did was we had a。So in our VM types represent the entire chain。

 which means that if you create a new object of type T1 and that inherits from an object of type T2。

 then now this object is of a type T3， which essentially represents the combination of T2 gives T1 so every type has a。

Has a fully defined chain。 So so if you have a method goal and like P1 T3 now。

 you can catch that same with cloud axises。 So the tab itself has the entire hierarchy。 Yes。

 the object itself still have a link in it to go some print。Yes。

 you has a link to go the there but you probably don't know the type when you read an inherited slot what do you have to do to get to that thing you have to follow the link Yeah you still to follow the link because I mean it's a product because said us lot of an object which belongs to a parent and then you have from the current point or you still need to have the So you do that So what we do when you're getting in setting slots is we also cache the debt So we've got if it's at this type then this is slot index3 the depth of two So we got。

Marra， did you do actual parent in lighting？I'll tell you thats come out and I just thought my idea for that。

I think of like creating just。First， emitting a bunch of get power instructions like just a serialal and after that they guess lot。

And then at the call side， you just jump to the corresponding slide of that。

 So you but I didn't do that。 I just thought that。okay you don't runs so we can do is you can generate actually of's pretty theres another we actually have the benchmark that optimization So when you use box in teachers。

 for example， and create billions of them it causes D to bevo in that。

But the fact is that boxing teachers are immutable。

 they have a sort which is never modified once the object is allocated。

 so if it was possible just to detect immutable objects then and not create many copies of them。

 we would just have， for example， the students who would just 10 in。

As that seemed too hard to implement I mean not to implement。

 but I mean it seemed like the analysis to figure that out would not really in box and theres some other languages that would be better fit F doesn't have a definition for immutable spots right very hard to know what Yeah it's they're musicalable I you can't find a right。

Well， I room there's norye in path。So there's no set slot with that slot name。

And you can dynamically create because there are languages that have a definition of the s。Okay。

Who is a benchmark to。Or so hires better right hires better okay， this is points， 100 points。还是差是对。嗯。

I shouldnt have a rename all these benchmarks。Show the SOS code。We have linear。

 that was very strange we do。well four layers deep。

Because so our original plan was actually to have basically do exactly what he did。

 limit except do it like limit the amount of layers we go down and then just kind of the reason for four is because an end is like you assume there's at most 156 classes so that you can use it based to represent。

A class name。 So you have like dual harsh function。

 which you put up in my And these guarantees no flashing。 we don't have time。 Yeah， so yeah。

 I actually tried I't so we just kind of assume the referralflows and we can。

We assume we not 56 but we didn't even get around to getting bucket。 So， so the thing is。

 we found a bunch of bugs we were fixing。 and also we tried to do。

top of S cash because that seemed more relevant， that was very important Yes so we did that but debugging that enough time。

Because every groups pop us that。no， not around。Okay， so there is this general theme where。诶。

Fer in my cash， you want a very quick check to know。Even if the method isnt apparent。

 you want to jump to the public this plot and that requires some sort of hash of your hierarchy yeah right？

Which you did， which you did， Jens also did。 but there's an important part， which is。

The this has could collide。So how do you handle this collision？

because we put exactly the hash was supposed to be that you basically just do a shift。

 so you're guaranteed。Right what if your， I mean， there's does not have a finite length on Okay。

 but you assume there are not more 6 Yeah the assume there's no program hurricane over you can but then your program fails。

 cur in the end we just So James have to have a real elegant solution for detect overflowing top Sure。

 basically pick the maximum number passes you expect。 it could be， you know，3。

32000 whatever number fit。The trick is， though， is that you use the uppermost bit。As's always high。

And so when you shift， you're shifting up that uppermost bit as well。

 it's always high so when the most significant bit of your number is high， you know you overflowed。

And after that point， you know the trap， and you assume this behavior is rare。

But you always handle the scenario and you'll never have this issue of， oh， shit。

Ha function is a shift， but it's a shift with keeping the most bit hot， upper most bit high。

And that way， you can always check to see if you've overflowed。

So I guess we we create new types completely， so if there is more than， I mean， if you're old thing。

 you just don't。But you still have to decode it back yet and the ratio has high。Okay。

What was this so it's basically like what you talk about。

 we used a wallop to create a bunch of chain of operas right。😊，Yeah。YeahIf you notice， wait。

 if you notice this one。1024And then it also requires to have a pulling more for England。对垃圾的是。

But actually actually， I just noticed that ours task can be in line and then it will never be gl。

So what do the other bars mean the ones that don't exist are they I they're just really small I think they're just really small。

 I I wasn't going to try to optimize this。Yeah， there is something special about this graph。

 If you notice there are only 4 at the bottom of。 this one was passing for us。 So okay。

 so maybe wasn't huge。 So this killed someone initials are there。 So is here next there。 No， no。

 but we did we specifically fixed bug。I guess when he ran it。

 it didn't be doing the OSX if you commitment in my environment。Okay， which are the dog questions。

s 1024 parents， right？Because we didn't use the harshing function。 So this算数 work。Actually。

 true we did the transitioning as needed， but we also cache the parent type so that every time we create a topic of the type we've seen before。

 we un cache and then we just don't have to do that transition before。I don't understand what。

you said that when you see a parent hike？八かに回て。Do do you going you want care and you parent create new type so basically we keep track of the runtime type that does the type be created also the base type of the object。

So that the basetime mean just the the object tag we we have。只快。It's not one。

That's for that's for slot slot。We just keep track wrong。 But but also that。Inside of这 code。

 we also have a in my cash。Det。That's a time I've seen before。If your burning color来。Okay。

 oh so I when you're I look something。因我 are的。So transition but I'm not sure's within the object language then but then you have to look the table right so we just ignore that table then so that creating the。

Okay， this is So basically zip elimination， you probably。

 if you had any GC bus you might have got exposed to something in here Also since I have register allocation。

 by GC is faster than everyone else's the loops is the one the pi calculation you have the pi calculation Yes Okay And then lastly。

 if you have to do static analysis to remove the jumps or the test on the integers。And after that。

 the only way that beat me would to have register allocation。

How long did the whole benchmark run the whole benchmark runs Well this is actually longer than mine。

 my system runs at 2。72。7。喂。That' part six， I think this I only got five。No。

 there was one those added Okay， Im saying。 All right， Oh， this is the funny point1， yeah from。

From Jack yeah us honestly， just wanted to have fun I the throwing point library about。Okay。

 and then here's stuff that I wrote， this was a very， very short running program every start of time。

So it's not so like I said， yours is pretty simple right so you got a really good score on this one actually。

 and this is important。😊，Chas啊。でそれです。Okay。This one。

 I actually tried to break people who cash the parent wing。Because it has different terms。😀。Ja。

 you want to explain one Yes， you'll notice it never prints so you can analyze whether it prints and just kill the program immediately。

最最。やい。So Kit is not as simple as like looking to see if there's any prints because there are prints。

If you do a trace of reachability analysis， tell that whatever you reach never calls。

So that' reachability analysis if you do the reachability analysis， you realize it's not reachable。😊。

For you have to be。Do you do result and remove games to see theize？this one was fascinating to me。

 actually， so this was big known implementation， Fiminacci on bignuns with a really inefficient big no implementation that allocates tons and tons of tos of objects。

😊，啊。John Charles Smith， do you have。I knowThe explanation for lawyers is so。Do don knowいや。

Any other other subject the allocation operation that you mentioned， so lots of allocations。

object mean that's only not sure。I well， for whatever reason it's very fast。

 I was going impressed with this one。 I didn't think。This one is very optimize。

 I don't think this one。那是。Another fast earn one， soacci， not the worst。

Here's your recursive handling。This is another this is another one that allocates a lot。

 so we're seeing a pattern that。Smerica and Genile was really good at adocating。

And here's it up here。Wish James Op is Helen。So that is also just print 200。I consider doing that。

 in fact that would have killed benchmarkchpar one too， I have reachability from printf。

Well I didn't think anyone would have done that anyways。

 but that was the next trick to do implementation optim complex because it doesn't print anything I can analyze it's not printing anything just now it's clever thing is the reachability to a print app and you just follow a trace and you can cut all that but no。

 this is actually just running Sudo。Okay， so time for the results。Results。This place。

Micha' well done。😊，喂。On third play， is Jack and Ben， that's you guys， right？Good place， well play。

Second place， second place， close put no cigar。Wonder who I？James your name will look forever。Okay。

Well done， everybody who entered even if you didn't enter。

 if you build a working implementation that ran well。The course had its point， that was great。Who？

Who looked at this in a loop for me， the speed loop， I got a couple of traces。 Okay。

 what were the instruction counts you got got 400 and。200 okay。

 so this program I wrote this program to see see show how difficult some things are to implement。

 So what I did was I implemented this loop with a counter in it to look through what the loop does T is just a simple variable。

 It's just counting the number of trips in the loop just to verify that the computation is correct F is where all the exciting is F is a fool。

That's made。And the fo is made by inheriting from an object which is a counter， so this counter。

Has a method in it。Which counts down So you call this count has an initial value。

 you call this done method， decence account and tells you whether it's zero。And I use that。

To control the loop。And I use it。Inside the loop， I calculate。

 I'm make an array of the same length of an， and in each element of the array put the square of the corresponding n。

嗯。And then the final thing， the reason I thought this in at the end was you have this weird type system with zero and null in the system。

 you know， which if you either have to tag， you don't tag it， even box it， boxing is painful， etc。

So that was the point of doing that when you break it all out， it sort of looks like this。

 you're doing a set。Oor an inherit array of an array element with you get the array element and you do an addition and a multiply。

 then there's the loop and then the test at the end is an F。

Which is finding account from a inherited law and testing it against zero。

So I showed with you last week I had aphie implementation done in truffle。

 I got that working to my satisfaction correctly about last weekend and then I got a little help from Christian。

To tune this up using truffle techniques so I did the obvious thing myself which is I put in specializations for ins。

 which means all the computations are done on unboxed ints unless we mix types。

We put in the inline catchching the for all the dispatch so Grl can do the inlining through all of the dispatching we did the shape catchching trick so this is the idea of for each object you compute shape which representsent the the names of the slots and in addition what Christtine did was he put the reference to a method slot as a shared。

Attribute in the shape， so it's not in the object， it's in the shape， or they're shared。

 and so when you compare two objects for shape， if they are different methods， they're different。

But if they have the same methods and the same slots， they're the same。

 and then what he did was the trick of combining the shapes down the inheritance chain to get a compute shape for the final one。

That summarizes all of the inherited information。So the methods of constants in the object here。

 as just said there， I put in an int， a specialization for enter arrays。

 so if your array has nothing but int， it' stored as a bunch of unboxed integers and it converts only to the box representation if you store a unboxed thing in。

And Gl has a special way of doing while loops， which will make it easier so if you want step replacement and using the Java while loops。

 so use that too。And we also did using a substrate VM machinery。

 an AOT build and integration so that we ended up with a small bindr that didn't need a JVM。

You said the shape has the。Yes， but in the actual value， it's there still。Yes， yeah。

 when you make the object， the links of that。Tns out that's not really a problem。So let me show you。

 so you got 200 instructions for your in a loop， 400。

 but actually that's worth doing a bunch of static analysis。Okay。

 and I basically figured that the cost was not。So let me show you this is a run of grow。

 I meant the loop run long enough that it would get grow optimized。And。

Some way down here if I didn't just deselect the tip。

Because it's hard to do this when you're looking。DidNo， there it is。That's。

That's the entire life as optimized。So one of the clever things is here。

 Grl scale analyzes the Azal loop and allowing the object allocations， only the array gets allocate。

And the field slots in the object become scaleless。So you're basically doing just a rare in。

Mplication， you need multiplication of summation into the array in the loop can。

 there's a safe point in the double increment because there's two basically two counters in that loop。

You number line number jumps from 2，0，3。Or you that line number， no， no， these are address。

 these are nodes in some graph。There's a bunch of data it。后面我。等好。希望。依家系。

That's one instruction it is one instruction there's someone。 See， this are just a。

 this are just the， this is the mess data they're seeing。So I got it down， it's 13 instructions。

s an instruction I spent about a week building the basic implementation Christian spent two days。

I I've run it against the ones I have， but obviously not on the same machine so I can't compare the times I have a runnable binary here if anyone wants in order to magnitude still same。

It's in the same ballpark， right， it's just I didn't lose last。

So it's a fairly big bindr it takes a while to start up， so the very。

 very short running things are not super fast。let me。So I'm just curious what to go。对。

not seeing Let me turn the mirroring on so I can see what I'm doing。Yes。three were some。

B you didn't submitted did benchmark benchmark。I did it just best for。Oh， that's their own model。

你接下就得啦，先，你叫佢话。Okay， sorry。那听日。对啊，对。你那个。对。Okay， hold three。Let's see it okay。你。なし？是系我。This morning。

 Su。没回来。よさ。I mean， most of these programs don't rely enough to do a co decentcent compile us the real problem with our excuses。

怎么样？That's pretty good actually when I looked at this last time。

 it was actually still compiling on the program still run way does solve there's still run this to solve。

Meaning， meaning it's not reachable by Prince。We don't eliminateinate anything。Isn't connected。


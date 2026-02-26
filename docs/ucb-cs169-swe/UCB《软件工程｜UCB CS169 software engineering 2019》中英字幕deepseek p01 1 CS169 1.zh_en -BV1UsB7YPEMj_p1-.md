# UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p01 1 CS169 1.zh_en -BV1UsB7YPEMj_p1-

Where are we。

![](img/d63e327fd4549d49cb3a9e53ec3f2433_1.png)

Okay， and not cooperating。All right， so it is， yeah， it's Berkeley time cool。All right， everyone。

 so welcome， welcome back to the fall semester， welcome to CS169。I'm Michael。

 I am the newest lecturer in the CS department， I graduated from Berkeley three years ago studying CS education and I've been working at grade scopepe for the past few years。

 which I assume all of you have used and have various relationships with it is you know the tool that you get your scores with is it's always a fun thing to use so this is CS169 it is software engineering。

 we will be talking a lot about how we build software， the process behind it。

 there will be a lot of coding。 the code is also not the point of this class so we'll talk about that today and as soon as my computer cooperates。

😊，We will actually get going， there you go， so does anybody know who this is？



![](img/d63e327fd4549d49cb3a9e53ec3f2433_3.png)

Oh that yeah， why？That is not very effective。

![](img/d63e327fd4549d49cb3a9e53ec3f2433_5.png)

呃。こない。Okay， you know what？

![](img/d63e327fd4549d49cb3a9e53ec3f2433_7.png)

One second， this Icler app。

![](img/d63e327fd4549d49cb3a9e53ec3f2433_9.png)

It's not exactly cooperating。干嘛呢？

![](img/d63e327fd4549d49cb3a9e53ec3f2433_11.png)

Yeah。た。And。Okay。No。Can be ones。Okay， there we go， does anybody know who this is？

So this is Margaret Hamilton。And what one of the things that we'll do in this course is have a little bit of computer history sewn in throughout every so often。

 And the reason for this is it illustrates the。Sort of the history of software engineering as a discipline as a practice。

 but also there's a lot of generally interesting things。😊。

Margaret Hamilton is one of the people who was on the original Apollo software engineering team。

 and so we're going to play a quick clip assuming this new。It's going to make me， that's actually。



![](img/d63e327fd4549d49cb3a9e53ec3f2433_13.png)

This。No， youre not going to cooperate。Al the 2，5200 feet。Well。Daniel take the bill。



![](img/d63e327fd4549d49cb3a9e53ec3f2433_15.png)

Okay。W sec， why are computers so annoying？Okay。干嘛？Roger Co。

Alaltitude 42 in your goal for landing over。Ira up and Gopa landing 3000。S alarm。201， 1201。

 Roger 1201 alarm。Where go， F tight， where go。So。It's a little hard to hear， but in this clip。

 there's the word alarm that said and this is one of the interesting things about。

Talking about computing and computing history。 So what's happening here is on the Apollo space。

On the mission， they have antennas， which are processing various signals as they are landing the computer。

 which is a 1969 processor that is being sent to space。 So limited by computing resources in。



![](img/d63e327fd4549d49cb3a9e53ec3f2433_17.png)

A million different ways compared to what we would think of today。

It couldn't process all the data that it needed to process at the same time。

 so one of the things that Margaret Hamilton invented is this idea of dynamic resource scheduling and what had happened was one of the astronauts had left an antenna signal open that it was trying to process and instead the computer was dropping that task to focus on processing the landing maneuvering so that you could actually land on the moon and so what the computer is saying is alarm and that it was dropping some tasks and so。

This is just one of those bits of things that as we look at software engineering as a discipline。

 there's not just the code that we write， but the tools and ideas that we have to end up processing this code。

嗯。There is also？Why are there。So there's also a GitHub repository of all the code that was used for the Apollo missions。

 it is in the public domain， it was a taxpayerfunded project of course。

 so that is something that if you're interested in taking a look at some old code can be a very interesting thing so this is Margaret Hamilton with the team of MIT software engineers。

 it is a very 1960s photo。But they're the ones who wrote much of the software that runs or that ran on the Apollo missions。

So。Does anyone have some ideas of what they think we're going to talk about when we talk about software engineering versus just programming in general And if you are in the back。

 it's a bit dark and my eyesight is not the best。 So just like wave your hand and I will or shout out if I miss it。

 but otherwise， yeah， does anyone have some ideas as to what software engineering would be Like what are we talking about when we say that there's a difference between just software engineering and programming or writing code。

What might we care about？Meeting in water。Requirements， yep。

 absolutely so it's not just something that you know we can just build for ourselves。

 there might be a customer， there might be a specification to follow。

 that's certainly going to be a part of it。 what else might we have as a distinction with software engineering engineering。

Pro。Yeah， absolutely。 yeah， so definitely going to be programming。

 it would not you know be a computer science course if there wasn't a significant amount of programming in there。

 what else is there any other big things yeah。Yeah， you could say extensive。

 We'll talk about how extensive it needs to be and whether or not we always need it to be that extensive。

 There's one other aspect。 What is a core piece that you've hopefully heard about this course。Yeah。

Yes， absolutely。 so working as part of a team。Really。

 I don't care that you can't join the Wifi Network computer。Yeah。

 so working as part of a team is absolutely one of the biggest distinctions here and so working as part of a team includes multiple things。

 this is you and your five other teammates for this course。

 this is you know when you go off to take an internship， a job after graduating。

 this is your immediate team， this is an organization。

 this might not be people let you know if you're working you know on an open source project on GitHub。

 you are potentially collaborating with any number of people around the world who might even speak a different language than you。

All sorts of things， you know， you might have as a team。 So multi person is a key， as a key piece。

 So this is a photo of David Parnas， who is。Influential in software engineering。

There are going to be names and photos of people They give illustrations as to where some of these ideas come from。

 The point of this course is not to memorize who these people are or know their names。

 but they are there as a background and to point out that we are not just inventing all of this material。

 So this is a quote from Fred Brooks， who is a Turing award winner And this is a really interesting piece to combining separately written programs and making them suitable for use by people who had not written them。

 And I think the part there that's interesting is the idea that software that gets used in production is not just a single piece of code in CS61A。

 you're writing assignments that largely live on their own towards the end of the course you get into some more complex projects。

But in general， it's one sort of encapsulated bit software evolves over time for people who had not written them is also a critical component。

And one of the things that we'll focus on。All the bits around your code that help you with this aspect。

 So， you know， and it's worth noting that people who had not written them will repeat again and again will include you in three months。

 know， in a course project and in internships， you don't often get the chance to go back and look at your own code months later or even years later。

 But you know when that happens， you don't always have the same context。 So having the tools。

 the processes， the infrastructure around your code to help with that will make things easier when you do have to modify。

 maintain and adapt things so。Those are a bit about。

 you know sort of a high level what we think software engineering will be in this course。

 so when this course was developed about six or seven years ago。

 professors David Patterson and Armando Fox went and surveyed a bunch of industry partners who worked with the ES department and they said yeah what what are。

No， that is actually the next slide。 Well， they went and surveyed a bunch of things about what we need。

 And then at the same time， this is now， I believe， only three years ago。

There was another survey that was done by Microsoft and the University of Washington。

 which is what are know some of the aspects of an individual software engineer that are looking for。

 so these are individual aspects so improving self- drivenrive you what makes you work well on a team。

We have。The team aspects of， you know， what are you doing， not just within yourself， but， you know。

 how do you operate on a larger team， So giving feedback you know， the。

 the important one here and this is true of education is creating a safe haven。 So how do you。

 you know， respond to questions when someone is uncertain about a process， you know， you say。

 I am trying to。Let's say load a million users into a database efficiently。

 And you're wondering how you can do that， You know。

 making sure that it is a safe space for those questions， which， you know。

 at any time within the projects in this course， you will run into something that you absolutely do not know how to do。

 There will probably be things that you will ask your GS Is or myself that， you know。

 we do not have an exact written script for how to do those either。

 And it is perfectly okay to throw out rackacky ideas， you know， just say， I think this might work。

 I have no idea。 So within those course within a software engineering team。

You know that is an important aspect， and so I hope that as you're working together。

 you you can cultivate this within your smaller project groups， but also the course as a whole。

 you know we'll talk about that。So。Other sort of important aspects on the technical side of being a software engineer。

The interpersonal stuff and the interpersonal stuff is all super important。

 but of course if you are building code having the proper technical background is important and at this point in Berkeley you've hopefully had two intensive years of lower division courses maybe an upper division course or two as well and so you are already well in your way of having the technical the technical chops there。

But that will be another big piece。And so， you know， the final bit is。

Just you know in the pieces of decision making， what are you going through the steps。

 are you thinking critically， are you helping document and define those processes and。

You know there's a lot more here， but these are sort of the highlights of each piece of the process so this is what you know one of the surveys as to what makes a great software engineer。

And you can sort of。Distill this course down into one slide， which。

 you know disciplined customer focused agile。 So， you know when we talk about this。

 we'll spend a lot of time in this lecture and in the next week， sort of what the word agile means。

 I'll note that it is a lowercase A here in terms of not trying to be too dogmatic and in software engineering。

 which is the discipline and software service。 So what we'll be working on。

 what you'll be working on our projects that are web applications back by database that solve some customers needs that are deployed to the cloud。

 So if you've had an internship， you've probably worked on something similar。

 it is sort of the backbone of what you know you think of today when you think of a modern technical startup or even not a startup anymore but。

Most the projects and programs that you use in your daily lives are probably software as a service now or have a component of it as well。

Expectation setting for this course we assume you know how to code pretty well you have made it this far in your Berkeley career that is not too much of a problem Second assumption you have a Github or Github student account you don't need the student specific features of Github but if you sign up for them there is a lot of great freebies if you don't have a GitHub account already you can just go ahead and create one that is where you'll be working on your projects we'll talk a bit about that in a second。

But you know， that is。GitHub will be a great， a great piece of this course， both for。

 you know how we manage projects and something that you will probably use in the future as well。

 And if not Github， you will very likely be using a similar piece of software wherever you go to work。

 So the goal， know the goal here is to prepare you for the future of what you're going to be doing in an industry setting。

 you know， in a lot of research settings， anything like that where you're building software that is more than just。

 you know， a weekend hack project。😊，So。Does anyone want to guess the answer to this question。

 will this course teach me JavaScript React， Ruen Rails， Django， your framework of the day。

 does anyone have a guess of what the answer to this question is？No， yeah。

 and the reason for this is frameworks come and go， right？😡，They， they change rapidly。

 they also you know， rails itself， which we will be using has， you know。

 more than a decade long history now。 it is， you know， I believe about 15 years at this point。

 so you know， they do。They don't just totally come and go。

 but the goal here is not to learn or not to teach you。😡，You know。

 just the mechanics of rubyion rails， you know will you learn them。

 you absolutely have the opportunity to learn them if you get invested in your project that will be the most you know extensive way to really get your hands dirty with a framework we are going to focus in this course on the serverside component。

 but you know when I took CS169 Angular was the hot JavaScript framework at the time。

 you know and a number of project groups dove in and built you know really nice experiences in Angular because they wanted to learn it。

 it delivered a feature of their project where it was appropriate to do so but you know while we will use rails as a vehicle for this course。

 the intention is not necessarily to help you become a rails expert。

And so in terms of what is necessary for this course， you really need both components。

 lecture is necessary but not sufficient， reading the textbook is necessary but not sufficient as well。

😡，The textbook is， we'll talk about that a little bit more specifically in the logistics section。

 but， you know， it is designed to go deeper on specific topics than will be presented in lecture。

 we will have some new draft sections for you as well。 And so， you know。

 do make sure you're reading the textbook。 It is not a heavy textbook。 It is meant to be you know。

 concise and to the point。 but it does have a lot of good examples。 it is。

 I'll say this as when I was a student， one of the few textbooks that I actually read。 And so。

 you know， take that for what you will。 But I actually did enjoy reading this textbook as a student and it's been improved since then so。

😊，You know， will。We'll make sure that everyone you know hopefully has good experience there。

 So this is a slide that I meant to jump that was jumping at to earlier is what is missing from students technical skills So some of the things that when you talk to employers that you ask them what do students come into an internship come out of school what do they not have experience with So one of them is legacy code at this point in your school career you have pretty much worked on projects which you have either been scaffolded a homework assignment where you're filling in a piece of code or you're starting something from new and C a6 to1 B you pretty much get a blank slate and write everything from scratch and it is an inable way to learn every project starts off as having you a blank slate in some form another but one of the skills that you really need to have is working with legacy code。

 So a lot of your projects in this course will be starting from a project that other。

169 students have taken that is being used by a customer and you will get to continue you know having that application live on you'll be working with code that is written by maybe6。

18 you know 30 other students over the past few years who you basically get to pretend do not exist you know they all very much exist they are around graduated working but you know you can't go ahead and say。

 you know hey， how does this piece of code work what's in the project repo is sort of you know the piece of that So legacy code is one aspect some of you will work on new projects but you know most of you will be working on legacy projects。

 we will have homework assignments that are designed to sort of give you that experience regardless。

Working with non technical customers is also a huge component。

One of the great things about CS169 in the project component is the groups that you work with are nonprofits。

 campus organizations， NGOs。That need some software built。

 And they don't always have the technical experience。 to describe。

 they're not going to tell you this is the schema that I want for my user model。

 They'll tell you a set of requirements and you get to go work with it。

 A few of you will be working with technical customers for your projects。

 And so I will probably be the customer for one or two projects。

 your Gss might be a customer for one or two projects as well， depending on which ones you get。

 So you will definitely have， you know some projects for the customer technical。

 but the goal there will be， you know we're still not going to tell you like how to spec out the user model。

 and working with a a technical customer sort of has its own different set of challenges。

 but we're gonna to try and act in the most sort of nontechnical way as possible。

 Professor Fox will be customer for a couple projects as well。 And when he's a customer。

 he works in the same way。And of course， the big one testing， definitely a thing that everyone says。

 introductory software engineers don't have as much experience with。

This course will go through the aspects of testing different types of tests。

 how we can make it easier to test our apps， and so we'll be doing this as homework assignments throughout your project you'll have you know intimate experience with other people's tests when you start adapting their legacy code and you get to decide how helpful or not those test cases were but by and large we hope that they would be very helpful so the project theme of this course is you know I think an extension of being a public university。

Is do well by doing good。 So you are going to learn a lot in this course and the projects that you take on will be helpful to those in the outside world。

You know you know these what these teams need， what these other groups need are often you automating processes。

 keeping track of data， things that software is particularly good for doing。

 and by building these applications， you can really help a group you know。

 accomplish their mission in a way that they're definitely not going to have， you know。

 millions of dollars to go out and hire a consulting firm to build an application。

And so that is that is the goal of this course， I'm going to pause right here before we get to this questions so far on the course。

 how people are doing anything like that， we will have a logistics section in a bit。

 so say the logistical questions， but any any questions so far on CS169 or anything that I've said。

to look in the back。 No， cool。 So this is an overview in two slides of what your projects will of what your projects will look like。

 So there's repository code， it lives on a server， it usually also lives in Github and it's deployed most commonly to Heroku。

 If you haven't used Heroku， it's a very nice and easy to use platform for deploying your software。

And in this version， this is sort of the canonical live example of an application。

 most of these are in use today。You know， you'll be working on taking over some of these projects。

 but that application is going to live there is going to be in use during the semester。

And what you have is your team's copy， so it's called a forkcon GitthHub。

 but terminology doesn't matter。😡，and there will be sort of one canonical repository for your team this semester。

 you will each work on your own local copies， and we're going to use this model called branch perfi atware。

Your team members will work you know in a team of six。

 you'll have you know two or three different features going on at any one given time。

 so you'll learn how to work with Git， you don't need to become a Git expert。

 you know you don't even need that much advanced knowledge。

 but you will get experience with it if you haven't already。

And the idea here is that you're going to be having access to see how a codebase evolves and multiple people are working on it at the same time。

 taking it in a similar， but also potentially different directions of adapting various parts at once。

You'll be doing this with multiple teammates。And then you will as the semester progresses。

 make PoQu back。 so as you do each iteration of the project， you'll say I'm finished， you know。

 you'll have an opportunity to discuss that as a team with your GSI。

 and that will go back into your main repository。And along the way， when we do this。

 we're going to be working with some industry standard tools， so Travis CI is a framework。

is a tool which lets you use a framework called continuous integration that helps you essentially test your code as many times as possible。

 every time you push to GitHub， you'll be able to run a series of tests。

And you'll get those results back so the idea here is you know。

 we're going to use tools to make your your lives of building better software easier。

Code Climate is a tool which has a series of things like lis and static analyzers。 No Siri。

 I don't really need your help。CoodeClimate has Lter's static analysis tools。 It gives you a score。

 so this score will be loosely part of your project grade。

 you know it's not that you have to get there scores I believe at a 4。

0 because it used to actually be a letter grade but the idea is that are you taking steps to improve the quality of the code base and the great thing here is that it is a robot doing tasks that robots are well suited to are you following the conventions of the existing code base It's not going to be strictly about your projects we're not saying you have to have 100% score all the time but it's about maintaining a healthy code base and coveralls is a similar application it tries to measure test coverage all these tools are meant to be used as tools they all have their quirks and metrics that make no sense at times but the general idea of ensuring。

😊，That as you write code， you have parity that it's covered in tests will be an important part and these tools will help you reflect that so you will see badges like this on many open source projects。

 you will have the opportunity to see those reflected in your own readmes in your projects that you work on。

And then assuming everything is good， you'll be deploying a second copy of your application to Heroku throughout the semester。

 And so that will be an opportunity to actually experience the whole life cyclee of software development。

 And then once that code is deployed， your customers will give you feedback on how it's been going so far。

 so。😊，You know， you know， they will be interacting with a version of their application。

 hopefully most of these customers that are returning customers will also have experience with the previous semester's version of the app as well。

 though not all of them will， sometimes it'll be a new person from that group。

 but you they will be able to tell you you know what's changed how that you feels you know sometimes they will find bugs for you。

 but you know they are not， you know they are the customer。

 so you know you're building things for them， but they are also not necessarily your QA team。

And at the end of the semester and maybe sooner， if everything is good。

 your work will be merged back into that live application。

 so the intention here is for every team to have software that actually gets put into the real world is in use and many projects from this course have lived on for years。

 you know some live on for a semester， but the goal here is to have something that is long lasting。

So those are the tools you will be using a lot of tools don't worry too much about the specifics。

 you don't need to go and sign up for all of them right away。

 you know take them one step at a time as you get set up with your project。

 you know sort of you know as you're working on things， learn a tool at a time。

 we'll go through each of them in the beginning so。😡，You know， this is sort of the human side of。

 of what this process looks like。 So you're gonna to start talking to a customer。

 Then you're gonna probably have some form of a mockup。 So this could be a sketch。

 This could be a PowerPoint slide。 You know， we'll talk about tools for doing that。Newve。

And then what you're going to do is you're going to take that mockup and you're going to write a user story。

 So when a user logs in， this should happen when a user creates a new entry， whatever that may be。

 maybe it's something that tracks some sort of customer interactions， you know， this will happen。

And youll work with your customer on those user stories。😡。

And then we're going to use this tool called cucumber。

 which helps you write these user stories as useful software tests in a very Englishlike way。

 so the idea is that when you're looking at a test file。

 you will have a very clear description of what you expect that software to do so you'll be able to take those user stories。

 turn them into tests。Then。Yeah， so the next kind of piece is with tests。

We're going to try and get you into a test first mindset。

 It is not always natural to write your test first。

 so you know it is something that I think will be a little bit foreign at first if you've done it on an internship that'll be great。

 but I expect most people have not had test first software development as a discipline give it some time you're going to write test。

 they're going to fail and you're gonna to see a bunch of red dots and that's never the best feeling but what will happen is as you build your future。

 those things will pass and so it is a great feeling to see something go from red to green as well along the way you and your customer will have access to pivotal tracker to track these stories that you're building。

😊，And then at the end of it， you'll deploy。 So deploying， you know。

 this will be multiple times throughout the project whenever you have something ready。

 So we're gonna to work in iterations， but you can， you know， get your code out there as a team。

 You know， we you don't have to always。You know， wait for us。

 but you know we're going to encourage you to keep testing and deploying code as long as you go through this process so the faster。

 you know， your team works， you'll have more opportunities to actually push your code out there and see it working on a live server。

And at the end of each iteration， we kind of start all over again。

 so you will hopefully be doing four of these iterations in the course that'll be four two week iterations。

But， you know， that。that will kind of depend on the actual flow and speed of the course。

 but along the way what you're going to get is some experience here， so legacy code。

 after you've built a feature you might wait a month to adapt it again。

 you know you might be adapting someone else's code in the past semester。

And then you'll learn some design patterns。You know we'll talk more specifically about those。

 but the idea is that we're going to help you write code in a structured way here。

 so that is software engineering in two slides there is a lot there don't worry too much about the specifics but you the goal will be as we go in to get into a natural process so。

There are a few of these slides about the course， which is how to have a poor time in CS169。

 how to do everything wrong，Skipping lecture， you know， we don't need to do it， right。

 it's all webcasts。 just， you know， watch online。You know。

 don't do the homeworks because they're just homework assignments， they're contrived， they're small。

 you know， nothing nothing to learn there。You know， work alone， this is， you know。

You knowYou're going to be competing against your peers because everything is curved， right。

 so don't help your peers。You know。Yeah。I cannot talk today。嗯。You know。

You don't need to learn anything new because you've already had an internship right。

 so don't worry about that one。Ignore ignore process， you know you't that the steps don't matter。

Everything， you know I think especially the you know gopher points right。

 like the learning here doesn't matter， we have a you know everything will be graded。

 just try the exams， don't worry about anything else。U。And then obviously， you know。

 cheat because if you cheat， we probably won't catch you， you know， don't do any of these things。

 The thing that I will highlight， especially is on the point side with this course。You know。

 your project grade will be based not just on， you know， are your test passing you know。

 is code climate looking pretty healthy， but it'll be about all the bits and pieces that go into that work so are you working with the team Are you you know trying to keep up on GitHub。

Are you documenting things with user stories are you writing tests。

 I'll tell you that the grading of this course is a pain， it will be a little bit messy at times。

 but the idea here really is that throughout this course the thing that will matter most for your grade is participating in all the different areas possible so。

You know， I don't have the clicker base station working today， so there's not gonna to be any today。

 but you know， we'll be doing clicker questions and we'll talk a bit about that。 But you know。

 in the project grading， it's very holistic， there will be surveys of how your team members are working which will impact their grade you cannot just say。

 hey， my teammate sucks and we're not gonna fail them because you somehow got into a fight the last week of the semester。

 you know， we're gonna to take everything into account。

 including you know the code that you write the surveys from your teammates。

 your practice on the homework of course exams will be a component of this course。

 but you know the goal here is to make sure that you really have a well-roed experience because when you are in you know in an internship when you are building softwareer professionally。

 every piece counts and a project can be derailed for any you know one thing going wrong。

 So just remember that you know。The goal here is to sort of balance out the lecture with the。

You know with the code with the project work， you know， with everything like that。

 so for anyone who's also you know using webcasts， there are a bunch of slides that say end these are meant if you're reviewing the webcast as a place to pause and reflect they also sort of chunk up topically the lecture into various sections。

 so any new questions on this stuff so far。If you're in the back。

 just wave your hand because it's our yeah question in the front。Oh yeah， go ahead。嗯。

We try very hard to push people towards using rails if you're doing a new project。

Because it's the place that we can offer you help。If you have a project in mind that is an existing client。

 you know， and there is some reason that it can't be rails。

 we can talk about that in the past five or six years I think there are maybe two examples of rails not being in the framework。

But those examples have used something like Django where。It's the exact same setup。

 you work with a customer， you have tests that are written as user stories。

 you have continuous integration， you have code climate， you have GitHub。

There may be a limited circumstance in which rails is not the framework。

 but it will very likely be the framework for your projects。

 It will be the framework for all your home assignments。

 and it will be the examples that we use on exams。 So exams are not going to test your knowledge of rails we're not going to say。

 you know， like。pull up a document and figure out you what the heck is going on。

 what is rails doing here， but you know we will be using that syntax。

So that everyone has a common base， so if there's a need we can talk about it。

 but I expect most projects will use rails on the front end side。You know。

 we try and not have people build super front and heavy apps as a requirement。

Teams are more than welcome to as long as they are meeting their customers' needs。 And so you know。

 the focus。Well be on。Will be geared towards the back end。

 but it's really about meeting your customers' needs。 So if you need to。

 if you want to learn and react and it solves a particular problem。

 you're more than welcome to use that。 But the goal is make sure you solve your customers' needs first。

Any other questions before we？Go on。Is there one in the back or middle？Yeah okay， or if there was。

 just shut it out because the lights are kind of my eyes。So we have three TaAs for this course。

Jeremy Sruge and Nick。They all have experience with building software。啊。

Tuja and Nick recently took CS169 so they can give you all the tips and tricks specifically to this course。

 Jeremy is a PhD student。At Berkeley is studying CS education。

 so his experience is also super valuable here in terms of how are we giving you the tools that we need but three sections you will be meeting with your project team in your section and your GSIs will be your guide in terms of working on your project working with your customers managing that interaction so it will be imperative that everyone goes to section and that you go to section as a team。

So this is our bookSoft Engineering as a service， it is available online。

 you can get the ebook version， you can get a physical version， it is about $10。

And if for whatever reason you have a financial hardship， let me know and we can get you a copy。

If it's an issue， don't worry about it， just let me know you can email or private not piazza everything you need will be all linked through B courses so everyone should be enrolled automatically。

You know， we are making sure that all the bits are updated， but there'll be a schedule there。

 the syllabus has all the lectures will have links to readings and things like that。嗯。😊。

Okay waitlist enrollment， the not so fun stuff of having the largest major on campus。

 we will try and you know get through as much the waitlist as possible。

 this is an early drop deadline course so until next Friday you have to decide if you want to be in this course if you're in this course past next Friday you have to appeal to the dean to drop the course。

I don't have personal experience with this， but past stories have told me that it is not very easy to drop the course after an early drop deadline course。

 so make sure that if you are wavering and whether or not you want to you know take CS169。

Pay attention to the deadline next Friday to drop the course if you are a junior and you're unsure and you think it's not going to work out。

You will hopefully have multiple times to take this course but you just be mindful of that after a few people drop we'll try to process the wait list right now enrollment is full at 90。

 we may be able to open it up to close to 100 as you can see this room is full so that is a limiting capacity there as well as the fact that we only have 3GSI。

You， we will do our best to make sure that we let everyone in who wants to be in the course。

 but if you think you will not be able to take the course， if you're unsure about the project。

 please be mindful of the early drop deadline and give your peers a chance to enroll if you won't be taking it as well。

If you have DSP accommodation letters， I've gotten a few。

 but please still post a private note or email on Piazza about it。

 you know regardless of what your letter says， if you have a DSP letter I want to hear from you about what you need to be successful。

 you know the letters don't always describe in your own words。

 what you need to be successful so please let us know as soon as possible so that we can provide you with the things that you need and if there's something that's not in your letter that's reasonable you know just let me know。

So this is the book， there's you can get it on Amazon， you can get it， Sasbook。info has it。

 there will be a couple chapters of the book that we are linking from the syllabus that are draft chapters including some stuff late in the semester that is actively being written。

 so you will need to copy the book and then we'll just highlight when we have additional links for newer material。

But there's been some really exciting developments since the first edition in that you know software engineering is not a static discipline。

 things evolve and adapt， so there'll be some new focus on API first development。

 how to better separate your front end from your backend， what concerns look like there。UmAnd。

Ie clickers， so we will be using eye clickers， they are annoying， they are finicky。

 but they work better than lots of other things。I will try and enable the online sort of reef pulling option if you want to use your smartphone。

 but usually the easiest thing to do is to rent a clicker if you have someone who is not taking CS169 and does not have a lecture at this time of the day and you are comfortable you borrowing a clicker from a friend you I've been told that the registration thing works as long as you're in two different courses。

 you can share a clicker so。You know you don't need to buy your own。

 there is an ASUC program to rent them for I believe$5 and we'll make sure that link gets on piazza。

 all the Berkeley stuff links to Facebook page that has been updated since 2018。

 so I don't know exactly where the most current information is but there's some emails on the Berkeley page about iCers。

Yeah， and we will have a webcast， so if you are absent for a day， if you can't make it to lecture。

 you know the webcast will be available。And then section is required。For Tuesdays sections。

 please kind of。know just go to a section， if you have a group of people that you expect to be you know a team。

 please try and make it to that section together， that will be the hard requirement on section attendance is that all of your project members need to be in the same section together。

And then other than that， just go to section after Tuesday sections。

 we will try and you know respect your preferences。

 there'll be a sign up sheet for getting people you know in the sections that they need。

But that will be for next week， just go to a section and then after that we'll have。

You know you'll have your time for the rest of the semester。

 so slides will be on B courses after lecture， just you know make sure they're there if you need to review them。

We're going to try new thing for CS 169 this semester。

 so please bear with us if it is a little bit bumpy at first， but。

We're going to be doing all the auto grading through GrScope this semester。

 so past semesters of CS169 have used edX as a platform andedX is its own beast。

 we are trying to limit the number of places that you need to log into and submit things to so you will already be using GrScope for exams。

You should already have all used gradecope if you're a Berkeley student and haven't used gradecope。

 I highly encourage you to start because you've been missing out and reviewing your exams and。

You know just make sure you're paying attention to that and then。You know next week， homework zero。

There is， you know software is always a challenging piece。

 so late next week we'll try and have some office hours dedicated to helping everyone get you know installed and set up with the tools that you'll need for this course。

 hopefully it should be。You know， easy for most people。

 we're going to try and have some online resources as well， but you know。

 just be mindful of that that is the part of software regime that does kind of suck， you know。

Errors dealing with insulation， but once you get through it once。

 you know you should be good for the rest of the semester。

We'll have all the TS officers upload soon mine right now are Tuesdays from 5 to 7 pm。

 so I know that there is a 5 to 6 pm section on Tuesday， I'll be available after that。As well。

 but we'll have all those available on PR1 B courses。

There will be two midterms for this course if you have a time conflict with either of these。

 we will send out a survey soon。😡，But you know please make sure that you are writing these on your schedule they will both be 7 to 9 pm。

 The midterm on 115 right now they did not confirm the room yet， so it may change that is a Tuesday。

But it will be Tuesday， Wednesday or Thursday of that week and as soon as we have a confirmation on the room。

 we will get that out to you as well and just a reminder if you need accommodations for DSP。

 please just let us know and we'll work with you to make sure you have everything you need there。

So micro quizzes， There's already been a question about this。

 I'm not sure yet whether well announce micro quizzes in advance。

But the idea here is that frequent quizzing really does help you learn the material better。

 you know these micro quizzes are going to be simple。

 there are going to be you know one question usually that is about five minutes。

 will send you a link to probably B courses， maybe gradecope something you're already using but。

What this chart shows， this is one of the better studies on quizzing。

Is the retention of people who had frequent quizzing and how long after they remembered the material。

 So you can see that cramming works pretty well if you're going to only try and retain something for five minutes and with quizzing it has the complete inverted effect with after a week of quizzing or one week after。

When you have more frequent quizzing， you are much more likely to remember the material and so the amounts of time that people spent studying are cramming。

 cramming and a little bit of quizzing and then mostly quizzing and no cramming。

 which is basically you know if you are keeping up doing the readings。

 if you decide to do them right before lecture， a I applaud you for getting up early and doing something before a morning lecture。

 but you know that is sort of the point is to help you just encourage you to keep up with the material。

😊，But if you end up having missing a micro quiz or two， it is not a big deal。😡，嗯。

They will not be anything that are designed to hurt your grade， they can only help your grade。

 you know if you are just randomly getting all of them wrong。

 that's not going to help you you know if you're struggling on you homeworks and exams and we're doing grading and it's like well。

 you haven't answer to any micro quizzes that will be you a concern。

 but if you're keeping up with the course then micro quizzes can only help your grade there。

We're still kind of messing with the exact details of grading。 but the idea here really。

 is that for all these bits and pieces。You don't need to focus on the points。

 If you are keeping up with the work， you will be able to to succeed in the course。 So you。

Take them seriously， but don't stress about them。 You know， there are very few instances of。

Microquizzes sort of becoming a blocker for anyone taking 169。

 they are meant to just keep you sort of， you know。

 give you checkpoints along the way to make sure that you're doing。

You have some feedback and you're doing well。嗯。😊，The other bits and pieces of sort of course policies。

 so a couple past runs of CS169 have had sort of a lunch where I'll probably do this Tuesdays around lunchtime。

You know， 12， 30 to one or so north side or soda， but if you are reading about software engineering。

 have questions， want to talk about that。Seemly not necessarily just class questions。

 but the wider world of software engineering。You are welcome to come， just bring a lunch。

 if you've read a good blog post， if you want to hear other people's interesting blog posts that they've read。

 thatll be a great place。Reference letters so past versions of 16 I have also done this is if you are keeping up with the course。

 if you're making a good faith effort， you are doing reasonably well in the course。

 this does not mean a plus， but you know you are keeping up your studying your practicing for exams then。

You know I will write you a reference letter if you give me enough notice。

 you can tell me the day before that you need a reference letter because that will not happen。

 but the point being here that you know we will see your work on projects。

 we will see how you work in more than just an academic setting in this course and if you need that for grad school for an employer you know that is something that we want to be available and provide you with as well。

And so the other thing that we want to do to keep you engaged in the course is allow you to submit exam questions that you think could be good candidates for the exam so when it comes closer time to getting the midterm setup up we will post more about this。

 but the idea is that if you are paying attention you know what are the types of things that you think would be very interesting problems to solve on the exam so these are not memorization questions。

 these are not you know the nitpicy details of you know rails and the active record framework like these are things that if you were presented a problem on an exam。

 a scenario situation you would find interesting you could submit that to us and then assuming you know we get enough we will a review them and make sure that they're appropriate level of difficulty we will tweak them as we need to to make them appropriate you know for everyone to answer。

But then we will provide the other questions available to students as well for studying materials。

 so you know you'll have plenty of examples that look like the midterms to study from you'll also have past midterms available we provide those out as well。

 so there'll be plenty of opportunities but the idea here is to keep you engaged in the course。

As well。That is the end of the logistics section， we are also about you know most way through。

 so questions on logistics， the course， things like that。Yeah， there will be， yeah， correct。

 There will be no final for this course。嗯。Ym。Yeah， there will be no final。

Your projects you know are what are really in place of the final for this course。

 that is your body of work， that is where you should focus your time and effort you know into the projects that you're working on as a customer。

😡，When it comes time to the final， we will do， it will not be an exam。

 but you know there'll be some project presentation tasks which will are to be determined right now。

 but in the past we've done sort of review videos， you know。

Previous iterations have included a poster session。

 I don't think we're going to do that this semester。

 but know there'll be something like that which will give you notice on anything that needs to be scheduled。

 but no final exam。Yeah， in the back middle。That。Yeah， yeah。

 the first edition of the textbook is the only one that's released right now。

 there will be a couple chapters， the two that are like coming up first are noted on the syllabus where there are drafts of the second edition。

 but there's a link to the PDF so anyone can just download that draft chapter。Yeah， other questions。

Oh yeah， inside。We will send out a sign up form this weekend or early next week。

 go to any section on Tuesday。If you have an idea of what time is going to work best for you。

 if you have an idea of your project groups， try to go to those sections first。

 since that will kind of give us an idea of how things will balance out。

 but we'll get you into sort of finalized sections for the week after next。Other questions， yeah。

 in the middle， I think。Was someone raising the hand over there， yeah go ahead。Yeah。

 they are on classes。berrkeley， they are all， I believe now in 405 soda， so Tuesday one to two。

 two to three and  five to six， I believe。mThere。there are in classes like Berkeley。

 theyll also be on the B courseurs homepage tonight if they're not already， but yeah。

 they're all in 405 soda。Other questions， yeah。The list of which。Yes， that'll be on B courses。

 it's not right up now， but it'll be on B courses。Yeah， other questions， yeah in front？

Final presentations will be more towards the class so in the past we've done short videos that you record as a team which our demo walk through and。

Some semester students have wanted to sort of vote unlike best presentation or most interesting project。

 I don't know if we'll do that this semester， but it'll be more geared towards the course with what we do。

 but we'll have more details on that later in the semester don't stress about it now。

The end of the semester is practically， you know。Infinite time away， as far as everyone's concerned。

Other questions， just wave your hand if I'm missing anyone or just shout it out。Yeah。い生とプケションは。

The book right now is not free。You know， it is available online though as an ebook。

 if you have a problem paying for the book， please let us know and we can work that out。

But it is available on Amazon， there's also a paper edition if you would like a paper version。

 and then certain chapters of the second edition will be linked just on the syllabus and address state。

Anything else questions logistics？I'm missing seeing no one。

Cool and if I do ever miss someone as a question and I can't see you raising your hand。

 just feel free to shout out and stop me we'll have a fun thing hopefully next week regarding questions。

So， but we can talk about that then so for the last 20 minutes or so。

 this is an introduction to software engineering as a discipline， the the changes， the history。

And so on。This is a brief sketch of the transition from what is。You know。

 called plan and document to Agile as we know it today。 So assuming these videos work。

 these are a couple。Let's see。Of software engineering's greatest hits。Yano。Yeah， I。Come on， computer。

Okay。We are going to try this again。Oh。That's。O哎。嗯。O。你高了20。So。That was a software bug。And。

Let's see if the other one works as well。No， no。Okay。hy is the internet not cooperating？Okay， well。

 the internet is not cooperating with me today， but the other of software's greatest hits is a test of an airline autopilot which was being flown entirely on autoPt and it ends pretty much the same way as the first video So there is a whole list of history's worst software bugs。

 but the point being here that。😊，You knowSoft engineering as a discipline matters。Because， you know。

 in certain situations， the stakes are extremely high， fortunately for you， fortunately for you know。

 the projects that you'll probably be doing in industry。

 these stakes are not so high and there is a lot of solace in the fact that if I were to put a bug in gradecope。

 which has occasionally happened， no one is going to die by that bug， you know。

 if it takes a few more minutes for someone to get their grades， that is， you know。

Unfortunatelytunate， but it is not a huge disaster。 So there are cases where the stakes matter。

You know， there are a whole list， though， of interesting things in this Y article。

 So if you enjoy reading about explosions， disasters， things like that。

 I encourage you to take a look at the article， so。😊， you know。1968， the late 60s are when。

The idea of software engineering as a discipline starts to exist。嗯。And you know， one of the ideas。

 you know， that's supposed to happen， aircraft manufacturers have tried to fix that problem by designing the out of the cockpit。

This is the first fully automated plane。Fung by a computer。これ呢。no。You can hear at the very end。

 oh no。Well， so aside from the fact that the you know。Internet led test spoiler。

Don't know why that happened， but that's okay。The point being here that， again。

 software software matters。Yeah， there's a lot of things that are know， unique to software。

 So you know， we compare。the early days of building software compare it to a lot of infrastructure projects。

 how do we build public infrastructure well， we go out， we plan， we gather all the requirements。

 we estimate costs， we hire people to document， we generate timelines。

 and then we start building and we end up with a bridge of public transit system that hopefully meets all the requirements that we have set out。

This process is roughly called plan and document， which is before we do anything。

 let's plan everything out as detailed as possible， you know。

 let's create a timeline for which we can measure progress， you know。

 let's make sure that we understand everything you know and then。If anything changes， you。

 let's go back and make sure that's documented。 that's clear。 we update everyone in the process。

 and then you in some cases， maybe have to start over building something or revise that and。You know。

 it can certainly work out。 So this is also known as by the name waterfall。

 which you've probably heard of if there are， you know， sort of。Two。You know， two dogs in the fight。

 then it's waterfall and agile， but in a lot of ways， you know。

 there are elements of each that we'll see are similar。But。The basics here are pretty consistent。

Start with for waterfall， start with requirements。Write your design。You know。

 implementation integration。You know， write everything， design it。Build it， test it。

 and then put it out there and maintain it。😡，And so， you know。

 the idea here is that each of these steps is finished before you you know。

 begin the next one and so that you know， ostensibly makes a lot of sense right。

 like why are we going to build something if we don't know what we're building。

 but as we'll find out。You know that there's a lot of potential reasons that so this is a really great example of where waterfall types of you know。

 methodologies succeed。 So the space shuttle program is about 420000 lines of code and in the sort of past three major version。

 So you know， there has been any development in the past。F or six here， eight years now。

 I believe since it's been retired， but the past three versions。

 there is less than one bug in each version， which is pretty amazing for a project that has almost half a million lines of code。

In almost any startup type environment， that rate just doesn't happen。

 the circumstances are obviously different there。But。You know， that is。

That is to point out that these methodologies can be successful， they are appropriate in many cases。

And when we're looking at the success。You know， the Software Engineering Institute at CMU rated it as the highest maturity for a software project。

hich again， like measuring kind of quality by one measure and then adding GPS to the shuttle program。

This was， you know， obviously now more than a decade ago。

 but 6000 lines of code generated 2500 pages of documentation。

 So changing 2% of the code base leads to 2500 pages of documents to be able to write that change。

 And so that is an investment。 you know， that leads to。A very different process needs。 But what。

 if we could classify something that's different about the space shuttle program。

 what is something that's different about， you know。

 this process or the needs of the shuttle software then， you know， some of the apps that。

You'll be building today or you might work on in the future。

 like what's one piece that would be different about them？Anyone。

And I want to take a guess at what might be different。So what's our hand？Oh yeah， go ahead， sorry。

 lights。I was going to say constant feedback in。We' grade customer。Yeah。

 so in terms of our software has constant feedback or the Stle program needs it or。Yeah。

 so I think feedback is an important piece， what is is there anything else that would be a good reason why this might be different as well yeah？

Yeah， definitely cost。😊，I think those two combined kind of sum it up and a corollary to the feedback piece as well is that once the shuttle software is built。

 it's very stable， right？There is a known entity of the shuttle program。You know it。You know。

 there's only six you know， there were only ever six space shuttles that were built and that were running。

 not all of them were you know， all running the same version of the time。 but， you know。

 that was a sort of known entity。 And so today's software， the projects that we're working on。

 you know， the costs are not as high。 The feedback cycles are much quicker。

 and that software will adapt and live on much more than something。You know。

 then something like a space shuttle program would so this is。

A great quote that you will all learn to have experience with。 It's just what we asked for。

 but not what we wanted。 And if you've taken a design course， C S 160， you know。

 whether or if you work through like Berkeley innovation as a club， you know。

 anything like that where you have gone and worked with a customer， if you've done any consulting。😊。

You will become very familiar with this phrase。 you know， users do not always know what they want。

 sometimes， you know， that's just getting something wrong， but。In other times。

 that's just changing requirements。You know。And this is， if you take something away here。

 another one of the big things。 software is adaptable， right。

 We can deploy code hundreds of times a day if we need to， right， like Facebook， Google。GitHub。

 all these tools that you use are rapidly evolving， responding to changes， you know fixing bugs。

 adding new features on demand。 We don't have that ability with a space shuttle right once it goes into space。

 however long， you know there's not going to be any time there or necessary the resources to address something。

 if you build a bridge。Then you know， you can't just go ahead and add a lane to that bridge， right。

 it's built， it has been done。I forget when exactly was finished。

 but the Sanito Bridge in the South Bay， they added an additional lane because Bayer traffic is bad。

 so it makes sense something logical to do。 adding one lane of traffic costs more than the entirety to build the bridge in the first place because once something physical is out there。

 adapting it and maintaining as hard。 Soft is amazing and that we have that advantage that we can just adapt it and build it so。

😊，Just a few examples of software projects， the green bits here are the from three various studies of projects that were completed on time。

 you will see that they are all in the very low teens or even as low as 10% of projects that were completed on time and on budget and the projects that were delivered over budget were at a rate of three times more costly and three times longer than expected in some cases。

You， there is a need to adapt the way that software gets built even you know。

Agile will not solve all these problems， of course， but it will help make it。

A little a little bit easier， a little bit better to adapt to that process。And so， you know just。

Just a reminder of， you know what， what sort of the costs are out there in the real world。

 So this is a former Israeli Prime minister， which I think is a great quote。嗯。Oh sorry。

 next slide is the Israeli Prime Minister， but so this is again Fred Brooks。

 which is planned to throw an implementation away， you know the idea here is you probably don't want to throw everything away。

 but while you're building code， expect it to adapt。

 expect to be able to rewrite someone else's code anything like that。And then。

So where are we on time， we have a few minutes left。嗯。😊，So the。The spiral life cycle is another one。

 This is more of an illustration。 Again， don't worry about the specifics of the names with all of these。

 But this is sort of a bridge in the 80s between agile。And waterfall。 And the idea is， you know。

 you build a prototype and you do sort of things in smaller steps。 So you work with a customer。

 you got the requirements， you test， you build， you start it again at each time the steps get bigger。

 So， you know， your initial prototype is small， your second round of prototypes get bigger。

But the challenge here is that the timeline still between interacting with a customer can be a little bit long and a little bit。

 you know。On sortr of unstructured in that。 you don't necessarily get as much feedback as you want。

 So， you know， the goal with Agile here is to speed this process up。 So we have。

About let's see five minutes left。And any questions on sort of other methodologies so far？Yeah。Yeah。

我心里听。This software。あ。So in terms of professional titles that really depends on the companies。

 the question is what's the difference between software developers， software engineers。

 those are generally just what companies title are their positions you in a production sort of environment。

 what you're building is largely sort of around your team culture， I would say that most companies。

 most startups are somewhere between very diligently practicing， software engineering best practices。

And others are sort of in the space of， you know， just if it's a startup with five or six people。

 whatever you know you say goes， and so titles don't always have a bearing on that。

 but I would say most of them， you know we will be in an environment where you're trying to follow these practices so。

There is。This is sort of an introduction to all the pieces that preday agile。

 I'm going to end it here today， an hour and a half lecture is a little bit long。

 there's sort of a lot of logistics at the beginning。But。

You know what what will be important is sort of just making sure you get a feel for how things adapt and change over time in terms of announcements。

 we will have some emails you know and some piazza posts this weekend if you're not on piazza。

You'll be able to find it at CS169 if you just added the course recently。

You know that may be why you're not on there but you can selfenroll make sure you have access to the B courses site。

 it should be you know up and published if you can't access that but you can find Piazza please post there otherwise you know make sure that you do come to lecture in section next week and for next week we will start with icler questions hopefully it cooperates more next week but。

Yeah， thank you， and then I'll be outside for a few minutes as well。



![](img/d63e327fd4549d49cb3a9e53ec3f2433_19.png)

Yeah。so for grateful， if you do provide us the entry code。


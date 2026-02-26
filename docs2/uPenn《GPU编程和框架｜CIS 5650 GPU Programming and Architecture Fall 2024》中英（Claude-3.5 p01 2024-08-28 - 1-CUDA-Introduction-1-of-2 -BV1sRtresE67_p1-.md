# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p01 2024-08-28 - 1-CUDA-Introduction-1-of-2 -BV1sRtresE67_p1-

我们。All right hellello everybody let's get started welcome to our new fall semester here at Penn fantastic to see all of you in the class here today so we'll get started with the 565 first lecture today of course it'll be a lot of introduction and then we'll also get into some early Quda learning。

😊，I know three hours is a very long time， we'll take a break for sure。

 likely between the first introduction and then as we get into Ka。

Few logistics I'll just share right off the top I am recording so you don't have to worry about taking pictures of the slides that are already available so let me just pull up my browser and I'll show you a few things。



![](img/227a0511064268582643d942dd8ad682_1.png)

By now， all of you should be。Aware of the website， of course。

 so all of the links that you need will be handy。

![](img/227a0511064268582643d942dd8ad682_3.png)

嗯。Our GiHub is available as well project zero and project one are both out don't worry about hey project ones already out we'll do the recitation next week you'll have enough time to finish it。



![](img/227a0511064268582643d942dd8ad682_5.png)

At discussion， those of you who were registered and were in Canvas already were pulled in。

Those of you who are waitlisted I add you probably after the class in the evening so you can add questions as well。



![](img/227a0511064268582643d942dd8ad682_7.png)

Our schedule is available again on the website so if you go to Co syllabus and schedule you'll see the Google sheet here and I've already linked to the slide for today so each class right before class starts I link to the slides so all of you have access to it if you want to take notes and stuff。



![](img/227a0511064268582643d942dd8ad682_9.png)

嗯。And then finally， you Project Ze， if you're not already downloaded and tested your laptops with this。

 please do that that'll make sure that you're ready to go on all the hardware and software front for the rest of the course。



![](img/227a0511064268582643d942dd8ad682_11.png)

All right， so with that let's get started sorry one more thing if you have a question raise your hand ask no problem。

 the only thing I'll say is for the first few lectures。

 just say your name so that I get to know you by your name as well that'll help us throughout the semester for various reasons that I'll share later。

Okay， all right， so let's get started。Iや。

![](img/227a0511064268582643d942dd8ad682_13.png)

All right。So a little bit about me why am I teaching this class most of you have probably never seen me before I know a few of you have so my name is Shahzaan Muhammad。

 I currently work for a company called Casium it's a software technology company making geospatial software so imagine Google Earth but in a more open platform way for everybody in fact recently Google open all of the Google Earths data using our platform so now people can build 3D geospatial applications using that。

😊，There I serve as VP of Product and engineering， I started off in these chairs about 15 years ago no not  14 years ago。

 I graduated CGGT in 2013 since then I spent a little bit of time at AF and then moved to CU where I was doing a bunch of programming then started doing a little bit of product and now taking care of all of the product and engineering。

So if you're wondering， why is the Vi President of Product and Engineing teaching GPU programming？



![](img/227a0511064268582643d942dd8ad682_15.png)

That's because like I said I was in your seats and then my first job was literally writing GPU programs so AF is one of the best and still the best open source GPU libraries for QudDa OpenCL and other backends that does a lot of vector matrix linear GP types solutions where you don't have to write the GPU programs all you do is call an API like a plus B and it all happens on the GPU I left afi at the end of 2016 and it's pretty crazy to think that I'm still the second highest contributor there I wish somebody overtook me but still there I'll keep that as a badge of Hoauna。



![](img/227a0511064268582643d942dd8ad682_17.png)

嗯。All right last thing I'm not a PhD I've been called a lot of different titles that I'm not honorable of so you can call me Shaazan if you feel like you need to give me a title Mr or Sir is perfectly fine Im not one for lofty titles so feel free to be more casual with me than maybe you are with other professors。

😊，嗯。I'll introduce our Ts we have a fantastic team of A+ TAs this year really proud of them and what they're going to be able to do we have Crystal in the back and Han as well so both of them interned at Samsung this past summer and then other T still at Nvidia he's wrapping up his internship in the next two weeks and he'll be joining us after that all of them did fantastic in last year's plus and have really positive internships that they're going to be able to help you from the other thing that I'll say is all of them are working on either upgrading our old projects or adding new projects that are super exciting for this year so you guys will be both in a way receiving the latest and greatest projects but also a little bit of guinea pigs as well but we'll try to minimize any risk to you。

So， that's about our Ts。And then。Very quickly， because this class is very collaborative。

 I want to ask a question of are there any students who looking around you don't see a former classmate。

 a former or current friend or anybody， just raise your hand so that you know other people can come say hi。

There a tie so that other people can come say hi。All right。

 we have a few so you guys know who to go talk to during the break。

So most of the projects that we start with are individual。

 but they are going to be collaborated in a way where you'll be discussing problems and solutions together and then the final projects of course will be a lot more collaborative where we have teams of two or three working together。

All right let's get into the course logistics spoke about the website that's going to be our home I had a question earlier about if you're not using Canvas how are we doing it so course website remains a home I'd like to keep the course public should anybody outside want to use the resources I believe education should be you know available and accessible to everybody so all of our resources will be there。

All of our projects will be on GitHub， they're all public。You are free to keep them public。

 which is what。I think 98% of students throughout my teaching time have done。

It's it's also great because most of you are going to be interviewing right either for full time roles。

 most of you for full time roles and then some of you for internships and one of the questions you'll get asked most frequently is hey。

 can we have a project example， a code example a writing example？

The best thing is at the end of this class you'll have all of these you'll have five regular projects you'll have a final project all on GitHub and all you'll have to do is send a link and that also add credibility because they can see the history。

 they can see your work and that's been real positive when you've seen students go from the class to industry that's something they always command was a really good part of the class anybody who's new to Gi。

Wow， so this is really interesting back when I was taking the class。

 everybody was new to it maybe there was one student who had learned it and this is back in 2012 right。

 and it's fantastic to see all of you already know it we don't have to do like a tutorial on it or anything。

Our forum will be on Ed like I said if most of you should be subscribed already if you're not by today evening I'll go in and add the waitlisted students into there as well so you should have access to please use it for all of the discussions especially things that are helpful to other students that you think other students may run into please ask there if there's something you discussed in office hours one on one with our Ts or with me that you think will be helpful to to other students please go post it on there this is something that happens a lot in the industry right like when you work for a company that is all you're doing you're sharing information so that everybody is successful。

That's what I want to happen in this class is that all of you succeed later I'm sure I have a slide where I say I don't do be curves。

 your grade is your grade so you helping other students does not take away from your grade it's making sure that everybody is learning and participating in the class。

We also have a LinkedIn group for all the alumni so please add yourself to that it's an invitation base so if your request I'll add you to it。

 then you'll be able to connect to other alumni for jobs and interviews and other things。

Any questions so far？Okay。Lectures so we we have two lecture times one is Monday 515 to 815 and then we have another one on Wednesday where。

Officially the C Reggistrar says it's 515 to 645 because it's a recitation because we need to front load the class a little bit so that we can get through all of the projects early on in the semester we'll do both。

 but as we go later in the semester itll most likely only be Monday or maybe sometimes only Wednesday。

But otherwise， we'll try to make sure that we don't use as much time on militaryries as possible。

This is a feedback reckon every year it's from 2017 so you see I haven't updated the slide no it's true sitting in a classroom for three hours is very hard I try not to go to 815 most likely I go to about 730 and even in that we make sure that we give a break about midway usually 5 to 10 minutes so that you can walk around ask me any questions asked tears any questions so making sure that we have a good healthy environment where we are all able to concentrate。

嗯。Office hours， so find a seat。We've set up office hours in a way that is distributed throughout the week。

嗯。So I'll do office hours Monday and Wednesday along with the class signs because I travel in and then Han Crystal and Aya once he's back will do class let office hours here they all said that levin 57 is a great spot for office hours so please use that if you need special appointments from me to talk about interviews or anything please let me know this。

Anybody don't know where living 57 is。All right we have one hand Han crystalryt。

 do you want to explain where 1157 is？Where the living 57 lab is。那这个。哦，我呃我会证明一下。ぱ。发票。好。一はさ。よか。

Small go， go down and very selective base。Okay don' okay。All right， so so nicknamed the dungeon。

 the office hours happened in the dungeon。So these are office hours that we guess will work really well。

 they follow trends from previous years where we know students are available and can attend。

What well do is we'll try these in the first few weeks as we maybe we get to week two and week three I'll ask all of you how the office hours are working out and if you're able to attend at least a few every week。

If most of you are not attending even like let's say nobody can attend Ctals Thursday， 10 a。

 then we'll change them and find a better spot so we want the office hours to work for both you as well as the TAs as their classes go。

So please give us feedback on how they're going and how you can make them。

Sorry one more thing sometimes they may change so the TAs have labs research office hours。

 sometimes they may change if they're changing well post it in advance in a discussion so please make sure that you're subscribe to notifications there。

And then finally we add some office hours， especially on project heads。

 if we see a lot of questions on Ed discussion where we see some of you struggling we'll make sure to add some time there。

All right。Resources。We pretty much teach everything you need to know in the class。

 especially through both the lectures and the recitations。But of course GP programming is very big。

 there's a lot of things to do can't teach you everything about GP programming。

 AI and other things in the course， so I've linked to a lot of the resources here。

 there's no official textbook either but you're free to take these as resources and read there's a few in the lab as well so feel free to try them out。

All right， let me pause there and take any questions before I go into more of the course details。

I'm sure there are at least a few questions。No。All right。

 I'm doing a fantastic job or all of you are very shy。Okay， all right， I'll carry you on again。

 raise your hand and ask a question I'm not going to bite。嗯。

So let's talk a little bit about what you need to take this course how many of you have heard that this course is really hard？

Okay， pretty much everybody， okay I'll explain， I'll give more context about that。😊。

So 565 is really all about the project。With us teaching lectures and recitation to help you do those projects。

 so we want to make sure that。The work that you do is the fundamental part and what we are doing is supporting you right so that's the output。

 the output of the class is you're learning your projects and we are here to support you。So。

What what we want to do is I'm here the Ts are going to be here your your fellow students are here。

 there might be other students who took 565 last year that you're friends with who can help but we also want to connect you with people in the industry you have an idea for a fantastic project and you want some advice on how to even get started on that and I don't just mean in 565 I mean you want to start let's say your next AI research or something like that more than happy to connect you to somebody in the industry who can that's one of the benefits like for me is that I have these connections whether it's NviIDdia Facebook Me。

 Samsung， anywhere else like more than happy to get you guys connected with both alumni as well as industry experts who can help so' that's a big part of this class。

嗯。As I said before， a lot of you will be interviewing。

People ask about graduates of this course all the time one of the reasons I teach the course is because C is interested in hiring graduates of this class right a lot both Han and Crystal interned at Samsung from a guest lecture we did last year where they got interviews through that so we have a lot of these connections that we want to get you guys connected right the goal of universities to get a nice job get a good pay here to help with that as well。

😊，Here are some， definitely not all of the companies that have hired from the class。

 if I tried to update this slide the logos would have to be very very small now that I think we've graduated about close to six or 700 students from here。

All right， let's talk about difficulty。 So these are student reviews right from previous years。

The amount of work required for this class is high。

The difficulty according to students is high as well。What？This graph this table says。

 which is the official course reviews that students do。Is that the course is extremely demanding。

But also extremely rewarding at the same time， what you put into the course is what you're going to get out of it。

The course is not hard。Because we are giving you complex nuclear physics equations or something like that to solve。

The course is hard because a GPU programming is nothing like what you've done before。1。2。

It's going to be so much fun doing it because it's so much faster that you wouldn't want to do any other projects。

And I'm being very honest about that， that's what students have said and before， they're like， you。

 hey， I'm enjoying doing this so much， I want to put all of my time in it that I'm not able to give time to other class。

Time management is for you， but definitely you know。😊。

Make sure that you understand that hey this class will take time， there's no doubt about it。

 but so make sure that you're not taking four other hard classes that will also take time and stuff so please balance that out。

So really the prerequisites for the scores， even though I say 460 is a strong prerequisite。

 is really a passion for computer programming， performance or computer graphics。

What you need is a very strong base in CC++ because there's going to be a lot of low level programming that you're going to do lot of pointer math and stuff like that that are going to be required so if you've done those kind of things before you have a good foundation to get started。

All right a couple of questions here， lots of students are waitlisted this year way more than ever before。

 so the course register is full with 40 we have about 50s waitlisted right now so usually what happens and I'll be completely honest here。

A bunch of you will likely drop the course seeing how hard it was no offense or anything so if you're waitlisted just make sure that you're watching the course register and add yourself whenever there's an open seat I will try to work with the restrar and the engineering administration to see if we can add more seats into the class if needed this has hasn't happened before every year we get we end up with about 30 students in the class which is perfectly the ideal size in my opinion if we need to add a few more no problem you know we are here for you so just we'll see over the next week or so but how many students drop and how many of youre able to get in if last minute you're still waitlisted。

Don't hesitate to contact me， we'll try to get something done with the university。Um。

Any questions on that， any questions on being waitreed？Okay。嗯。

The other question that we get often is the graphics background so the way we teach GPU programming is via graphics projects right and that's what makes them rewarding in a way that you program something and something pops up on your screen that's very beautiful and you want to do more of that。

And if you drill down to graphics， it's really a lot of math and physics and geometry more than physics。

嗯。So if you have a good base in that you'll do fine， like I said。

 have a good base in programming in CC Plusrus programming that's the first thing and then if you have a good base in math and a little bit of physics you'll do well the resources I pointed out before if you haven't taken 460 at all or haven't done any sort of graphics projectss let me go a little bit back。

I didn't know how many slides I have to go back， I forgot about that。All right。

 this rate tracing in one weekend，s a it's a open project essentially with tutorials on how to build a project it's in C+ plus try it out。

If you like that， you'll probably like the Str if you don't like that。

 you're better of dropping this class in my opinion， so try that out。

It's literally it's designed to be done in a weekend so you can take the time to see if you like it。

All right， let's come back。All right， any questions so far on this？

Okay so next I have a few quotes from previous years about what students have found valuable in this class and they're more not to boast about the class or anything but it's for you to look out for what you can get out of it as well right so so think if it's something out of the box that you haven't thought of that can be discussed in a classroom。

You know please bring it up you know I'm here to help as I can， you know we'll have the lectures。

 we'll have the education， but I'm happy to help otherwise too。

So our first quote is from Ruthha Joshshi who graduated in 2022。

 and this is what I was saying when I was talking about GitHub and the projects， right？

TheThe readmes are extremely useful in the interviews。

 what you guess asked is so one of the things we do in the readmes that you'll see is we want you to do performance analysis or ask a question about debugging or something。

Which is exactly what you'll get asked in your interviews。

 you'll be like tell me a time when you faced a challenge or tell me a time when you optimize something。

You'll have the exact resource， you'll have the exact write up and you'll be able to tell the interview hey。

 if you pull up my read me the chart is there I can talk more about it so that that's something that students find really helpful。

U。How many of you have truly used debuggs and profilers so far？I see a few hands raised。

 one of the things that you learn in this class is to live and die by them。

epBecause in GPU programming， you're not running with hundreds of memory locations you are running with。

Millions， if not billions and trying to debug that in parallel is nearly impossible without the help of a debuger you can't use print appss anymore right so these are tools that you're going to really enjoy working with the way well do it this year is better than I think we've ever done it before。

There's normally a recorded lecture that I put out that you know can be watched over Labor day and you can try it out and get a feel for it。

 but on September 11th， D Lou who is a graduate from 2022 currently working at NVDdia on the De Tool team。

She's going to come and give a guest lecture， So who better to learn about debuggs and profilers than the person programming them。

So that's going to be amazing and really excited for that。Rachel was a graduate in 2021。

 she went out to work for unity。Didn't see here at Siggraraft this year saw at Siggraraft last year。

 fantastic student and doing amazing things at Unity。嗯。So here's an interesting one。

You've all read and implemented papers in some form， how many of you emailed the authors？1。

You haven't right， So this is an example of。Well you absolutely should email them。

Even if it's just to say I read your paper thank you thank you for your work it's really rewarding to authors and people who are putting their essentially the life's effort into creating this research that somebody's reading it and trying to replicate it they find it really rewarding so I encourage all of you if you read a book。

 you read a paper just email the author if you have a question definitely ask it they'd be excited to respond I'm going to say that with firsthand experience that they're going to be excited to respond。

😊，Worst case is just say， thank you， I read your paper， I found it really wonderful。

So I encourage all of you to do that。All right I have a few more quotes here that you can read in your own time I won't go into more detail so yeah I'll keep that well I will pick up on the stellargraphs portfolio thing to say。

From having students who take this class。Beyond like one or two exceptions。

 I can pretty confidently say that。The number one and number two projects on their resumes become their final projects from the course and the co up rate so that well do in project three。

Like that's like almost guaranteed certain if if one of you are not doing that come out to me I'd love to know about which project you have even higher than that。

 probably a PhD thesis but what I'd love to learn。😊，All right。

 professional development I think I've beaten that horse enough now， so I'll skip these。

 you can read them again these are more for things that you can get out of the course and have help from me or the TAs to help you。

All right。Before I move on any questions？How's my day going？

So I think my day has been good I've been like excited to come here and teach。

 I don't know if all of you know， I did take a break last year from teaching。

 Wayne was teaching the class， Wayne was student in 2021， T8 in 2022 taught in 2023。嗯。

I took a break because I had a baby born last January so 2023 January and life at Cium was crazy as well so I thought okay I want to take a step back relax for a year and come back so I'm really stepping into this classroom other than a few times last year really since 2022。

😊，I couldn't be more excited right I love doing this I have a full day's work at Cium but when I come here it's like a new found energy talking to all of you。

😊，The and the。I'll hold for the last slide to explain why， but yeah， thank you for asking。

Other questions。Okay。嗯。No。All right， so let's move on， why GPU programming？

Should I answer this with AI and move on？Okay， so GPUs right they really stand for graphics processing units and V is kind of trying to change that。

 but well start with graphics processing units。😊，嗯。Once upon a time they were for graphics。

 they were for games and other things， but now as all of you know。

 they're for pretty much a lot of different things that all need a lot of compute and acceleration。

So。嗯。Let's go into the next level of why， right we know theyre for high performance compute。

 but why are they for high performance compute？So here's one of the latest Jan Intel CPUs right and when you talk about performance youll hear this term often called flops which stands for floating point operations per second really basically how many calculations can it do on？

A computer is basically all bits and calculations right so this flops represents how many calculations can it do。

So an In CPU can do about 12。3。Tererolops of calculations in a second。

A GP like the 4090 which some of you may have， does 82 and a half teraflops per second。

That's like seven times faster。So that's where you get your performance。

The other part is so here are the trends so on the left we have the compute how many gigabflps and on the right we have the bandwidth of how many gigapflps second sorry how many gigabytes per second the memory moves as you can see both of these charts are slightly old from 2015 I think maybe 2016 and Rdia hasn't provided new ones so I can't use those but the trend still remains true。

This curve is only getting steeper。😡，RightSo that's where the performance differential comes between CPUs and GPUs。

 especially as you think about so these are single precision and double precision as you start thinking about half precision and now NVD has come with six bit precision for。

The blackwell architecture， this is going to accelerate。So。

When you think about GPUs and when you think about flops， there's also another component。

 it's not just how fast can it go， like when you think about a car sure the top speed matters。

But you also want to think about mileage， you know， how long with the tires last。

 how long do I have to get a servicing done， etc cetera， etc cetera？In case of GPUs。

 you have to start thinking about cost。You have to think about how much battery and power it uses。

You have to think about the die size which is the manufacturing cost all of those things come into place so you whether you're manufacturing a drone or putting a GPU in a car or a GPU in a cell phone。

 these things matter a lot so it's not just pure performance but how much performance are you getting within the constraints that you have。

😊，All right， let's look at it another way。Here's a die shot of an optical CPU， a 9900 series。

 which is about four or five years old。But I think it still remains true。嗯。

Any of you want to guess what the colors are？Take a guess， no wrong answers。여렇た？Con。

Transistent density， yeah， perhaps。But more， I think， around the use。

What do you think the areas in the different colors are？그。you correct。All right。

 so that that's a good guess。 Yeah， what else？Anybody want to take one last guess and then I'll show you。

All right， so so yeah， the the CPU cores are right these the yellows were the CPU。

 the blue was the GP and then there's a bus and some cash in there。く。

What I want you to take away from this is the amount of transistors required to build8 CPUs versus how muchever theres GP space right there's more for eight cores of CPU。

Then for the entire GPU right， and then there's a little bit for the caches。嗯。

Here is an NviIDdia GPU， a G 100， the MPR architecture， which is fairly recent。Here's how much。

The computers， all the green is all compute， they're all cores as Nvidia calls them， right？

All the blue is basically memory and caches that serve those scores。So now if I go back。

 you can see that。From a hardware perspective， when you're actually building the transistors。

 how much more。Compute is dedicated to these transistors and these chips in a CPU and a GP and that's where some of the performance comes as well。

So this course is basically going to teach you how do you leverage all of this？😊，How do you leverage？

Thousands， of course， billions of threads， all of the memory in a manner that you can extract maximum compute out of。

So from a use case perspective。All of these。Or some of these are why all of you are in this class。

 you know？Computer graphics and high performance computing has been traditionally what's been the bread and but of this course。

But a bunch of you are here for the machine learning and AI without doubt， right？

And then you start thinking of enterprise applications like computer aided modeling， simulations。

 weather systems， all of these now use GPUs to be computed。Data mining is big with social networks。

 scientific computing and biotechnology and bioengineering to do DNA sequencing， protein sequencing。

All of those are now done using GUs。It's。Being an expert in GPU programming。

Its not just going to make you a better programmer。

 it's going to make you attractive to a lot of different industries than just the traditional ones that you may be thinking of it'll open up a lot of doors if you want them to be open。

Any questions here before I move on？For the coursework。How would you say it's distributed between。

Graphics， applications versus like。Yeah， that's a good question so I spoke about having five projects and then we have the final project。

The way I would describe the projects is。They have a visual output。P as as the end result。

 but most of the computation that you're doing is math sometimes for indexing。

 sometimes for performance that's going to get you that end result so probably the main。

Graics projects， you could consider pass ratess to be a graphics project。

 but at the same time you could consider to be a math project as well。

 I think projects four and five will have a little bit more graphic stuff in them。

But there'll also be web projects so you'll be able to share them out more easily to others the first two projects are definitely more on the compute side as you get to know GPU programming more。

The other part I'll say is all of the projects have extra credits built into them。

 however you want to take it。If you're into， you know。

 let's say rendering and you want to get into a movie studio and you want to make your best render。

 you can take extra credits in that direction。You want to focus on performance there performance extra credits and you can take it in that direction if you have ideas to do other extra credits you are more than open to it and want to hear you are so so there's enough flexibility built around the directions you want to take the projects as well。

And of course the final project is completely open， it's on what you're interested in。

 so that way we've seen a lot of different things come out of it and more than open I excited for that。

Other questions。오케？so let's talk a little bit about the course topics。

 so on a foundation we'll be talking about GPU architecture and GPU programming to get started。

That we are going to do primarily， at least in the first part of the class using Kuda Kuda has compute unified device architecture it's the most。

Broadest use direct GPU compute architecture， so that's the easiest way to get started。嗯。

We learn about parallel algorithms and how do you take。Traditionally， what would be a CPU algorithm。

 what all of you may have programmed， how do you put it on the GPU and make it a thousand times faster？

tThen we'll talk a little bit about graphics and how graphics APIs are used to program the GPU as well so there'll be a big part webGL is one for the web we'll actually be evolving the course this year to introduce web GPU which is。

Better in a lot of ways and also perhaps easier to learn because it's more compute so open webGL is built on open GL which you know is more graphics web GPU is called web GP because it has more GPU components。

As somebody who doesn't do a lot of graphics programming。

 I can say that web GPU was a lot easier to learn because the concepts map very easily one to one with KUuda。

 so later on in the semester I have a lecture that's titled a KUaDevelops introduction to Web GPU so that it's easy for all of you to learn。

We'll also have welcome that Han has volunteered to do to intro lectures on to teach you that Walcome will be an optional project later on in the semester。

 so we'll make that available。All of this is of course backed with the overall goal of how do we get the maximum performance。

 whether youre using a compute library like KudDa or you're using a graphics API。

 how do you make something things go really， really fast？That's going to be done by principles。

Let me pause that again and take any questions。Any topics that you want to see that we haven't covered？

Okay。

![](img/227a0511064268582643d942dd8ad682_19.png)

All right， so let's talk a little bit about the core structure。嗯。So the。

The main thing that limits the topic is how much time we have。

I could try to fill the entire semester with lectures and lectures and lectures。

 but that's not of what make you better programmers。

 it's really the project so you want to make sure that we are maximizing learning in that way。

One of the things we do is have a lot of guest lectures and I actually have two slides of guest lectures because we've had that many in the past so it's really a credit to all of them that they make that time available to us。

嗯。What we try to do is we try to pick out the latest greatest topics on GPUs and computing and have their speakers come into the class and educate us about it and I literally mean educate us because I'm learning all the time from them as well。

So this year， we already have five confirmed guest lectures。I mentioned D from En Whit of course。

 Eric Kings has perennially done a guest lecture on rendering and ray tracing if you don't know the name Erics or know him but can't place it。

 Eric Haynes is one of the authors of realtime rendering and a fantastic speaker。The Chrome GPU team。

Is actually quite filled with 565 alumni。And they're all working on the Web GPU API right now。

 they're literally working to standardize it。Kai is one of those people。

 and he'll be most likely coming in person to talk to us about the Web GPU API。

Some of you may know Liam already， Liam graduated from the class， I believe in 2018。

 TA a few years later， worked at NVDdia， worked at Roblox in AI and natural language processing。

 he's going to do a twopart series on a GPU and machine learning introduction。

And then Gibe Dganhani from SAsung， he'll be coming in November to talk more about GPU programming and GPUs on mobile phones。

嗯。So the one thing I say is if you don't want it in most of the lectures， that's your preroggrative。

 you know， the focus is on the project， but for guest lectures I do make attendance mandatory because。

They're giving all of their hard time and effort to come here and speak to us。

 the least we can do is show up， right。That's the least but actually you're going to get a lot more out of it so you know I definitely look forward to seeing you the one exception I'll make is if you have interviews and you need to fly out that conflict with those guest lectures totally fine you don't even have to email me but make sure that that is the only exception。

All right， grading， I think I need to update that slightly。

De grading is really divided into projects， it is your project。

 how you do it that's going to result in your grade。The final project I should update this。

 I think well make it 40% this year， even though it's equally important。

 we'll make that 40% so that we can add slightly more to the regular project side but really what this says is the final project does have significant importance we spend about five weeks on it towards the end of the semester it's really the star showcase coming out of the class we don't have any exams。

 we don't have any finals we don't have to worry about them focus on the projects。Okay。All right。

 let's talk a little bit about projects。So I mentioned before that we use projects based in graphics concepts。

 but really the outcome is performance and making things faster。

Each project has of course the coding component that you need to do。

 sometimes they'll be choose a certain set of features that you want to run with and so that'll give you the flexibility to make a project your own。

One of the things you know you'll always hear about is stand out from the crowd type things right stand up stand out from your room so we want to make that possible as much as we can in giving you the options on the features you get to work on in these projects。

The other part that I also mentioned is this written performance analysis as well as having beautiful readmes that communicate to your audience。

 not to us， your audience who are external who are your interviewers。

 your recruiters about what your project is like think about that for a second you're doing GPU programming one of the。

Most difficult concepts in computer programming。And you're going to be having a non technical recruiter。

 most likely looking at these projects。How are they going to understand the impact of what you've done？

And you have like maybe three sentences to tell them that。

That's kind of how you make your read me better， right you want to talk to them。

And say I took this algorithm and made it a thousand times better。

 that's what's going to get you that next interview rather than being put into the pile with all the generic interviews the resumes that they get。

Um。Show off your work。You share it on social media， I'd have to retweet it， I'd love to share it。

 share that that will gain a lot of popularity former students will always vouch for that。

And then one of the things I try to do， which has been up and down depending on time is have a show and talent in class randomly。

 so call a few or you up to come show your project not to test， it's not a test。It's more。

You're walking down the street and you meet somebody that you'd be interested to work with。

How are you going to be prepared to tell them that。

 how are you going to take 30 seconds or a minute and talk about your project。

 so that's kind of the preparation I want all of you to have。It's， it's not for， it's not for。

Testing or finding any kind of satisfaction for me。 it's more about preparing all of you。All right。

Projects almost always， except for the final project will be due at midnight on the day， so 11。

59 pm on the day off。You'll be submitting using GitHub。

 so you'll be opening pull requests so you you'll fork a project， you'll do all of your coding。

 you'll do all of your work， and then you'll open a pull request back。

We'll use the times of the comments and the pull request to make sure that you are within the deadlines。

You'll have four late days to work with throughout the semester。

 not counting final project because no late days for that。You can use those late days as you wish。

What we do is we don't penalize you when you use the late days。

 so let's say you use two late days for project one， two late days for project two。

 and maybe three extra late days for project three I'm making this up right？

We want to make sure that we maximize your potential in your grade so that we at the end of the semester。

 we will take a look at how many layers you used and distribute them accordingly so that you're not getting penalized unnecessary。

嗯。If you use more than one week for any project。We'll have to give you no grade because we will be moving on。

Now， there will be exceptional circumstances that come up。

Whether it's something happening to you personally or you have too many job interviews。

What I don't want you to do is come to us after and make an excuse。

Right when you work in the industry， you can't go to your manager a month after a project is you and say。

 here are all my excuses。You communicate upfront， send us an email， just be like， hey。

 I've got this thing going on。how can I make sure that I'm able to complete the project while also being fair to all the other students in the class who are doing it on time？

Again， I'm here for you。Giving you a C instead of A。

Changes nothing for me giving you an A instead of a C also changes nothing for me I to make sure that all of you the work that you are doing is fairly graded and is reflective of your work so if something is going on you need extra time please reach out。

That's the number one thing reach out early so that we know and we can prepare for it and we can help you in ways whether it's extra office hours or anything else。

 we want to help you there。嗯。All right this is kind of I put a 5% on class participation again because I want you guys to be engaged this class haven't had too many questions no problem please as we go forward ask because。

One of the things that's going to be most important。

And you're going to find out this pretty quickly in like half an hour's time when they go talk about quoa。

Is that。You will be confused。You will have questions， right？Please ask。If nothing else。

Ask it for your fellow students who might be more introverted and scared to ask。喂。

When I was a thr I asked questions。But I was also introverted as N。嗯。So， so my。

My advice to all of you is ask questions for yourself。

 I'm more than happy to clarify I'm more than happy to take all the time needed。

Don't ask unnecessary questions like this is not I'm not counting how many questions you guys are asking over a semester。

 I just want to make sure that we as a whole are an engaged classroom。嗯。

II think I already covered this。 I kind of covered this before where I said， you know， use。

The classroom versus Ed versus his office hours strategically。

 questions that can help the whole class， please make sure that you are communicating them across the board that would be extremely helpful。

嗯。As much as possible。Avoid anonymous questions in that discussion。

 because what happens is especially early on。If you think， oh。

 I'm not sure if I'm asking a stupid question。And one thing there are no stupid questions。

 we are all learning。If one of you， like people who are asking the first few questions， if you think。

 oh， I don't know if I'm asking a stupid question， I don't know if this is my problem。

 I'm going to make it anonymous。What that does is it causes a chain reaction for everybody else they're like yeah。

 that that question didn't reveal their name so I'm not going to reveal my name。咁。

Don't do that just say your question it puts a。Fellow student behind that。

 it creates a camaraderie that is really helpful in those kind of discussions。

Because you all want to get to know each other and help each other。

 especially as you think about final projects where you have to be a team。

 it's going to create a really good environment for that。嗯。So。Intensity。Don't do this。

Youre not this class can't live with it， you can't do it at all， you will have trouble。Do this。Sure。

Open the GitthHub page， read the instructions。Here wait for the recitation that's totally fine right but get started。

 at least know what the project is going to be and if you need to do any reading that's going to be super important。

I won't deny that most students submit 1159， 1204。That happens， no problem。

But make sure that you're not doing。6 PMm here， right， don't do that。mentioned this before as well。

 you can do open source， highly encourage doing open source。

 I don't think any other class does as much open source as we do。

 so it's a big advantage and take advantage of that。

Private tpots are allowed if you need to use them， let me know and let the TAs know。

Academic integrity， I take it very seriously。Everything I've said so far has been about your learning。

If you copy。It's your loss。Right first first in a learning way， second。

 unfortunately I'll have to give you an。I have a zero tolerance policy on that。

What I will say is if you have a problem it is perfectly okay to talk to a fellow student。

 please do that if you if you need to debug something if you how many of you know what rubber ducky debugging is？

Okay， a few rubber ducky rubber ducky debugging is。

The concept actually let me hold that how many of you have been in a position where you've been working on a project。

 doing something， programming or otherwise？You're stuck， you call a person over。

 you tell them what you're doing and you find the problem yourself。

Pretty much everybody right in some way or the other。

 whether it's a woodworking project or a programming project that is rubber ducky digbuging you may not always have a friend。

😊，But you may have a rubber duck， you may have something else and you are explaining to that inanimate object about what you're doing and you'll find the problem yourself。

😊，So yeah you can use your fellow students for debugging and other problem solving， so no problem。

 just dont make sure you're copying their main parts of their core base into your own project。

What is policy and policy about。I。嗯。That's a good question first time I'm getting that so to be honest I haven't thought about it and I don't think I've read P policy I don't know if they have one。

U。I would say。嗯。Use it， use it in a way that。Is assisting you， not replacing you。

I know that can sound ambiguous， but essentially what I'm trying to say is。

Use it for for things that are trivial that you know how to do already and you just want to make sure that you know you're not you're not getting it dry or you're confirming what you're doing if you let's say you know we have the Kuda Boy project if you're telling。

Charge GT or whatever to。Write me a kernel that does Boys。

 that's defeating the purpose of your learning。It's true that half of a developer's job is knowing how to search。

 right， how to do Google search， how to use stack overflow， no doubt about it。

Just make sure that you're learning in this class before you're doing that。Good。嗯。

Any other questions？이렇게。One of the things that may have popped up in your head now is we are doing open source。

All of your code is going to be open。😡，All of the former students code is open。

How is there no cheating？And it's basically built on the philosophy that you are learning。

 it's your disadvantage to cheat。Right in fact， because it's open， it becomes more blatant。

 it becomes more public。😊，And should should it happen then everybody else is going to see it as well。

 so don't do it， it doesn't happen in this class。It's more about how do I make differentiate myself。

 having been able to see what other students have done。

 how do I differentiate myself so that I'm more attractive to the companies that I want to work for。

All right， closing thoughts for the introduction and this is what I was I held off on saying before。

Without a doubt。Every one of you in this class。By the end of the next three months。

He's going to do amazing work that I haven't even dreamt of。

The projects are there sure I've done some of them， haven't done some of them。

 but your final projects are going to be things that。I haven't dreamt of I couldn't do if I tried to。

嗯。So I'm here。Not say that I know everything and I can teach you everything。

I'm here to facilitate your learning， I'm here to facilitate where you want to go。

 how you want to graduate， what jobs you want to get。When I。

Im going on slide on this I probably have a future one。

 it's in a future lecture I'll tell you the story later， but but really goes to say that。嗯。

Your work is going to surpass things I've done， your work is going to surpass things that other students have done previously in the class。

 so really take take advantage of it， that's going to create a fantastic career for you going forward。

So before we end this part of the lecture， take a break and come back。Here's a few reminders。

 join that discussion。If you haven't taken the student survey。

 please do because that'll help us make the learning better for you。

 how we teach and how we interact with you better。Join the LinkedIn group so that you're connected with the community。

Project zero， which is all about making sure that your setup is going to work is due Friday。

 you really don't have to do much other than set your computers up so that's why it's that fast。

Project one is due next Sunday and we will have the recitation for that next Wednesday so again。

 when you think of the curve。Open project one， read it。

 no problem if you don't write a line of code until next Wednesday。

 but make sure that you're cloning it， you're running it。

 building it so that you don't run into unexpected issues later。All right。

 so that's it for the first part of the lecture， happy to take any questions that I may not have covered。

Hello。你。The first five projects are individual， the final project will be a team one。

the caveat I'll put out there is if you and a team member want to do something creative。

 that is GPU based。We are more than happy to hear you are。

 so let's say we get to Project five and you're like， hey， we have the school idea。

 we want to try it out more than open to it like talk to us and we want to make sure that we are catering to that。

Other questions？You问。That's just new。认为。Oh you and you're on the wait list， right？😊。

I think problem with that。Okay， I may have to sync it with the canvas thing。

 but hopefully by tonight all of you will have access。Other questions。Yeah。Yeah。

 so I've been recording on my laptop after the lecture I'll upload it so usually what I say is within the 24 hours after the class you'll have the recording available。

😊，If you don't post it on Ed discussion， it'll be a reminder for me and I'll link it up posted on the class website。

Yeah。Unless I forget I always link the slides before the lecture so it may be like check it after 430 and will most likely be there。

Any other questions？行。这个。So。Oh， crystalsal or hand， do you want to answer that the question is。

Is most of the difficulty in codinging the project or in debugging the project？那这无的。I probably agree。

Yeah， so so the amount of lines of code you're going to write is not going to be that many。

What you're going to find interesting and of course we'll get into the next part with Kuda is it's a very different programming model。

There's a lot of indexing there's a lot of different memory reads。

 there' will be edge cases that you'll have to think about and making sure that things are working smoothly is going to be an important part。

 then you'll get also get into profiling and improving the performance site so。

I would say it's not too drastic， I would say。It could be 60，40 on some projects。

 it could be more code on one project and less debugging， so it could flip based on projects。

 but you definitely need to know the tools well to do the projects well as well。Other questions？嗯。嗯。

嗯。Yeah。So most final projects will be two to three people。We do create exceptions for one。

 but they have to be pre approveded， so we want to hear about your idea and why it needs to be one person。

The most common reason why a one person project is approved is if you're doing something in a PhD。

Or in a research lab let's say you have a CPU algorithm and you're putting it on the GPU and there's IP constraints and things like that so that's one of the most common reasons but otherwise we want it to be a project of two or three because ultimately the output that's going to come out of it the shared output is going to be a greater than the sum of its part so more than what two people will do two times one。

So that's why the team projects are much more impactful。行。或者都看。Should we just go over every step。

I software。S from our。嗯。最活れ。That's it yeah， that's all we want project zero to be it's not it's not challenging it's making sure that when you get to project one。

 you're not facing challenges installing the software。

 testing all of that so project zero is really designed to make a baseline work for you。

Other questions？Okay， goinging once， going twice。😮，Okay， so so please keep the questions coming。

 we are at 620 right now， let's take a 10 minute break and come back at 630 and then we'll start learning about Kuda。

Oh。So。the end time so。For Monday it it's the three hours for Wednesday， like I said。

 we do extend a little bit at the start of the semester just to make sure that we are covering enough material so that you' are able to do the projects well most of the time I try to end。

Or I thought before 7，30 or in that ballpar。No problem I totally understand you know again the recordings are there for that reason。

 so take as much as you can and then watch the recordings later。😊，是是。Yes事。不。O。Soです。Let kind forward。

Sorry， I didn't hear your question。Okay。What。The project deadline and your registration are completely independent。

First of all， Project Ze has no grade。Right， so it's purely for your setup。Second。

All you need to do is open a pull request which has no connection to your registration。Yes。

Most of the time you can check more lab and other labs， they'll have GP few computers as well。

I have to ask sets for a list of computers that they'll give that have GPUs and I'll put that on that discussion tool。

Don't be say very much。I would recommend not because what I'll do is I'll make it a surprise and I'll have you come and talk about your evening。

Let me just drop this so then I'm not recording all of the。黄。There's still working。我你看。This。没事你们。😊。

Whatし。Okay。你とで。放面的接边。this isけない。So。And like you， that'll be。哎。Yeah。是的。I。都你你为水的。你这谁。对不错。S。はすれて。

Maybe something。啊是微信吗？你是我你。Yeah。是。す。给对。Similar just like。好的我的。So。2s。

youre going to bail who's going to say。Yeah。你个。对对。It's a's a。喝酒。对，是活这边是一定的。それがう。一。Yeah。这个话他。我以是。Yeah。

就是一思。It' so。 It's like。This。这里。I feel like we get dollars。可以。那这个的关注区别。You think。对。你。Yeah。我。I。你没有。It。

你说。给一。I think that makes her the place like easily。Oh以。W only do alone to be。Thank you。Okay。Yeah。对そ。

我是很这意。H course。You。Good。s number。Yeah。这是。可以。It definition。Oh。Yeah。This。Yeah。So。The有。原个。这时间。就只能够我。

So what not。嗯。Yes。Very。你对不了。It。This。5确定。でなと興味をまってます。关心。Yeah。They can got third one。This is how。

But well， you're not out。We not。So啊。他是。Thank。We asked。It's like。

 I'm sure everything was very easy to get。这。这。です。一。Yeah。here。Okay I want to。

It not music theory I don't what doing。Do you suppose。So。这个年定。But this like never。I。我不这个。这注意事情上人。

这个职业。做以这个问。Yeah。还是是可。Re。Yeah。啊第一个呢第一个。必须负责。Yeah。这个。Yes。よ。多。It just。そさ？OkayGood。Youce。哎的他。而且是。Oh。是。

Okay。Please。为什。ね。No， exactly。That's。This just excuse me。ま。Shes teacher。And。今天。Yes。有吃。Yeah。对。

H right everyone， let's get started。

![](img/227a0511064268582643d942dd8ad682_21.png)

So。嗯。没有。Can I ask you to shut the door？Thank you。😊，All right。

So we're going to get started learning KUDa， how many of you have done any QUDa program in the past？

Any whatsoever。Okay， no problem whatsoever， I would say even better。All right。



![](img/227a0511064268582643d942dd8ad682_23.png)

So when we talk about GPU programming， it has， I would say a recent history。

 it hasn't been around for as long as you know general purpose computer technology has been around。

In the late 90s and the early 200s is when the concept of GP GPU came out where it was general purpose GPUs before that it was essentially working towards games like Wolf 3D and other games that you may have played。

So the early 200s is when GGP was born as taking those graphics hardware and trying to put them to use for more general purpose。

2007 is when I would say the true general purpose was born with Ka and that's what we'll get into today。

Inspired from Kuda， then we got open SEL， which was much more vendor agnostic。

OpenCL was adopted by AMD， Intel and pretty much every other platform as well。

 but the adoption on the developer side is a lot less。

 Kuda is by far the market dominant general purpose GPU way to program。

We've seen a bunch of graphics APIs come about WebGL， Open GL， with compute shaders， Walkin。

 and then NVIDdia more recently released RTX GPUs right for ray tracing。

Apple release metal and you know 2023 is when web GPU started being talked about in the open and will become standardized soon。

 so this is kind of more of a history if you've used any of these APIs that kind of puts a frame of reference around it。

Okay， so let's get into what coulda actually is。How many of you' have done this？

Pretty much everybody right if you've written a C++ program， you've read a file from the system。

 you've run some CPU code and there's been a single credit code。

A typical GPU program looks something like this， where you still have that host side。

But what you're doing is using the GPU to run a whole lot of things in parallel。😮。

And that's where the performance side comes into play。

So a few terms that we'll start using very often that you know you'll get used to。

So the first is the host， the host is the CPU or the main device that you're going to be programming on。

So the code is typically written in CSC++ or other languages if you do Python or anything else。

And then you have the device， which is actually running the data parallel code。

 which is normally the GPU， so we'll use host and CPUU and device and GPU usually interoperably。

 but the technical terms that you'll see in the documentation is host and device。

Most of the time they have separate memories， except on system monitor。

 which we'll get to later in the semester。A coa program， thus by definition。

 has both host and device code， you write the host code that calls the device code and so on。

A kernel is a function that runs on the device。It is the data parallel function which will spawn a whole lot of threads and that's going to run on the device itself。

So the flow looks something like that on the right， you do some CPU work。

 you call the GPU that runs the kernel， and then you get back control on the CPU。

So here is what a very simple Kuda program would look like， which is adding n numbers in a vector。

So there is an array that has n elements， we want to add it so on this on the host side you are going to have your main function。

You are going to call your kernel just similar to how you do and see。

You are going to have this invocation here， which is the configuration of how the kernel is going to run。

In this case， we are saying we want to run n threads。The array is of size n。

We want n threads and that's going to launch the kernel so in here we have the first thing you are going to see this as global。

😊，So this is a specifier。That says to the compiler and to the device that this needs to run on the device。

So we are going to run where to add as a kernel。That's going to。Have a bunch of threads。

 the thread IDX defines the index of the thread so when you have n threads。

 you want to know which thread is going to operate on which memory。You are going to use i for that。

 you are going to use the equation to add。So the question I want to ask is。

You need a for loop for this， don't you where do the for loop go？Like if you were writing this。

 if you were doing a vector addd operation on the CPU， you would write a follow。

 what happened to the follow loop here？What's it in the fact。

chExactly so what's happening here is you go from an O of n operation if you think about computer algorithms where you have followed that runs n times to n threads that all run in parallel in O of one time。

 so the loop becomes implicit。No。So。In。Coming back to what a program would look like is you have C code。

You have a GPU kernel that has blocks and threads， then you'll get to definitions of those pretty soon。

That becomes a grid。The kernel runs as a grid， execution finishes。

 it comes back to the CPUU serial code。It may do more work。

 it may call under the kernel and so on and so forth。So functionally there are a few declarations。

 so we saw global which is a kernel that runs on the device。😊，And is called from the host。

So a kernel runs in parallel， it can only run on the device and it can be called from the host。

A device function。Is a regular function right its not necessarily parallel and I'll come to that in a bit。

😊，But it's called on the host and it's callable from the device。So for example。

If you have a device function that says find me the max of two numbers， not two vectors， two numbers。

 and you say that's device， what that will mean is your kernel can call that function。Right？

The host one is basically if you don't have any specifier。

 you know how you write your functions in CNC+ plus， that's what Ht does。

 it's a CPU function that runs on the CPU itself。A couple more conditions。

 the global must always return wide。Anybody want to take and guess why？嗯。

Because the device code is calling it asynchronous and so it wants to not walk Okay。

 asynchronancy is good。 You want to try。这想我有。Thevic doesnt myself to for the staff。Yeah， okay。

 not right to the stack。Don't share the stack， don't share memory。我们这里天尽量回他。

You have a limit number of communication or probably over PCIE。What is one more reason？

One last guest， anybody。能。If you return something， oh Mike。Records memory。Okay。对不对。Yeah。

That that's that's true to some part， you want to try。You know， you up for training。一瞓觉。

Exactly so so that all of those are true， not one more than any other。

 but all of those are true in the fact that if you are launching these thousands if not millions or billions of threads。

 if you return， let's say an end， what is actually that end？

Is it an in from every thread is it an integer from all threads as one value what is it so to not get into those kind of complications this is a hard and fast rule that it should always return void。

😊，Devicice functions are in line by default， which means they are optimized by the compiler。

For all device called， essentially no static variables are no MalX。

 and I'll explain that later on as to why。Anybody want to take a guess at what these do？

What does the first one do？The function can be the。Exactly， so this this kind of function is。

 like I said， you know， if you want to find a maximum of two variables or something like that。

 that is very generic and you are essentially。Removing duplicate code instead of writing the function twice。

 one with device， one with host and having to maintain that。

 you can have this and make sure that it can be the compiler will essentially create two functions for you。

What about the second one， what does the second one do？We're going to try again，I hope是这。睫目。Okay。

 one theory。Who wants else wants to try？So what's the role of global？😡，有。用能穿。

So global runs on the device， right？😊，What does horse mean？Hosines run on the CPU。

Can this actually work？No， it's invalid， can't do that don't do a global end。

 there's no such thing can't have a kernel that's meant to run on the device runner on the host impossible。

😊，Okay。I'll ask a few trick questions like that once in a while。嗯。

Cuda supports the CC plus for standard library math functions so you'll be able to use。

Most of the standard CAT library that you've used throughout your programming in both host and device code。

 there are few special functions as well， interested device function that you won't have to use in this class。

 but I'm sharing this as information， basically what happens is because we are trying to maximize for performance。

If you know that youre not dealing with big numbers where precision really matters or you're not dealing with scientific applications or precision matters you're dealing with like you know cur algorithms where you either in integers or smaller number of floating point you can use these double underscore functions which are called intrinsic device functions because they have special hardware dedicated them and they run with 24 bits instead of 32 bits so they are inherently faster again you don't have to use these these are here。

And whole the complete list of functions is there in the programming guide so please check it out。

Okay， any questions so far？어째？All right， so we talk about the concept of threads， blocks and grids。

 what do they mean okay？So thread， I think is pretty simple to understand， right。

 it's one line of execution， one serial execution。A block is a group of thread。

And it has some properties to it that I'll get into。It can be。One dimensional。

 two dimensional or three dimensional in its arrangement， in its indexing essentially。And each block。

For the kernel that you launch has the same configuration。

 you can have one blocks that's 10 threads another block that's 100 threads。

 all blocks have the same size。And threats in a block can do a couple of things they can synchronize and they can use shared memory that will cover in the next lecture next Wednesday。

 but for now the theoretical understanding of that is totally fine。A grid。Is。

one or more blocks for that kernel a kernel always have has one grid。

 it never has more than one grid so and that grid essentially if you think of it is a group of blocks that can be arranged in 1 d。

 2D or 3D。So， a thread has a scalealar identifier so we saw thread ID x dot x before that is used to identify the index of the thread that you launch。

Again， repeating what I said before。You want to know which thread is working on what data。

 if it was random， then you wouldn't be able to get any useful work done。😡。

So the thread index allows you to compute which memory each thread is going to work on。

 so when I say I may have said to you before that project one is like a math and indexing project。

This is what Project one is going to have you do is make sure that you understand how indexing works。

嗯。A 1 d thread， you know it will be serially incrementing a 2 d thread will be like a matrix。

A three dimensional thread will be like a volume， so that's one way to visualize it for ourselves。

This kind of computation。😊，I is going to be super important。

 get used to that and we'll talk more about it。So a block， like I said before， is a group of threads。

It can be up to 10， 24 threads in a block。Here's another prototype。Get used to powers of two。

GPUs love powers of two。2，4，8， 16 32 really 32 is where it starts， 32， 64， 128，256， 5， 12。

1024 and then beyond that 2048 and stuff。I'm going to be repeating those numbers all the time。

 create a few if you start having that you know be implicit in your head so blocks can be 1D。

 2D or 3D have a maximum of 1024 threads in a block so if you think about it，嗯。

There is different ways of arranging them that I'll show in the next slide。

 but before that like we have thread IDX， you are going to have block IDX as the block index。

 so just like you have thread index to determine which thread in the block it is the block IDX is going to tell you which block in the creditors。

The block dim is going to tell you the number of threads in the block right so block dim is number of threads in each block。

Grid dim will be the number of blocks in the kernel。Any question on this slide。

 this is really important， this is like bread and butter。

 let's go to here and then well come to here。あい school。咁。I've never been asked that question。

 I don't think you need more dimensions because once you have three dimensional threads。

And three dimensional blocks， that's six dimensions already。So you get that dimensionality with that。

When you see the image of what。Does it have to be the sameYes。Yes， same dimension， same size。

 same configuration， yes。Other questions。Okay。So here's like a visualization of what you have。

 so if you have let's say oney and I've made these small obviously for the slides。

If you have a 1D block， that's going to increment like this。😡。

Right and I've kind of drawn it in these grids so that you can associate them with memory so index thread index0 is going to operate on memory index0 thread index1 is going to operate on memory index one and so on。

In a two dimension， what you're going to have is this is known as X major ordering。X changes first。

 then y and then z right so you're going to have x first and then y and then in the volume case z changes。

嗯。Again， these numbers here represent memory indices。

If you want to think about what thread ins look like。For x。

 they are going to be 0 to 7 for all columns。😡，And then y is going to be zero column， first column。

 second column， third column， and so on。😊，Right， and that's where。

These equations are really important because youll have repeating indices for x and y and z。

But you can use those to calculate a globally unique index as I called it。😡，So a grid。

 like I was saying， is a collection of blocks and you can use the keyword grid dimm again with X， Y。

 and z components。To know the number of blocks within that kernels。嗯。Any questions on this？Okay。

 so let's look at a simple program。Let's talk about matrix addition。

 so we saw vector addition before， lets talk about matrix addition， so this is now two dimension。

 right？Let's start with Ma。So we will say blocks is one we will keep our problems size small。

We are going to define a two dimensional thread block right so we will use the dim 3 structure so that's again defined within the Qa APIs so dim 3 is like x Y z you can give it component。

And then we are creating a threat per block of N by N。Quiz here， what is the maximum N we can have？

32 exactly so maximum threads in a block is 1024， so maximum n here can be 32 by 32。😊。

And then we used the same configuration that we had before。

 we called blocks followed by threads per block。😊，So that will tell the kernel how many threats to invoke。

On the GPU we have the global and then we have the first thing we do and this is almost always the first thing you do is you calculate what the global unique thread index。

😊，You find out which thread is going to work on what index。😡，And so in this case。

You have IDX for a matrix， you are going to compute that as y times blocked in dot x plus the thread index x。

 so that will give you unique indexs throughout and then you can add your matrices。

Any questions on this micro programgram？No。😮，Everybody clear on how this is working and how the indexing is working here？

Okay。All right。嗯。There is one caveat here that you kind of don't need to know anymore which is GAT and GT 200 which were the earliest sc architectures。

 those had a limit of 512 threads。But all current GPUs have 1024 threads the reason I share this。

I don't hardco this。Use use block then use grid， don't hard code these numbers。😡，All right。

So when we talk about the next level where we don't just have one block。But we have multiple blocks。

 right We have a bigger matrix that we want to add。 So we saw here。😊。

That maximum threat size or block size was 32 by 32， right？

What does that mean for our maximum matrix size？What is a maximum matrix size that we can run with this code？

嗯。T24 the matrix size is 1024 by 1024 as well， anything that' is bigger than that。

 the kernel won't run， you're not launching enough threads to do that。😊。

So when you have a bigger matrix， you're going to have to do something like this where。

Our threats for block this time will define as 16 by 16 okay？

We don't always have to maximize 32 by 32。So we'll define that as 16 by 16。

We will calculate that now we have to calculate how many blocks we need right so we have a certain number of threads we want to calculate how many blocks we need based on the matrix size。

So， we are going to use the equation like this where it you are dividing the number of rows by x and the number of rows number of columns by y of course in this case we are using a square matrix so you could do it both ways so once you have that。

You can now launch any number of blocks in the T per block for your kernel。

 and that'll mean the matrix size skillss。Now， what that means is you have to take the block indices into account to calculate your global indices right so you have to calculate your global x。

😡，And your global why？😡，Before you translate the global IDX of that specific thread that is going to get counted。

So。You first calculate your x like this， multiply block IDx times block ti dot x plus thread IDx。

You multiply block IDX times block di dot y or sorry block idx。y， block dim doty at threadidx。y。

 so this is going to give you your global row。This is going to give you your global column now you can multiply those by n to get the specific element that that thread and block need to work on and then you can add your actual values。

Does it make sense how we went from one thread block in the previous example to having multiple blocks in this example？

Okay。Anybody have questions on this again this is going to be the bread and butter the every kernel you write one is going to have this so I want to make sure that all of you understand that very clearly。

行。啊。It does， yes， when if you don't pass all three arguments， one is the default there。So yeah。

 dim3 is basically a if you open the kuda headers， D3 is basically a struck with X， Y。

 and z components。Other questions。Everybody get the two dimensional indexing。Okay。Al right。

So you just kind of the math behind it so let's say。We have an example of n equals 32。

 and I'm making this small so that the math can be easily understood。So let's say N is 32。

And we have 16 by 16 as our thread block size。Which means a thread indices go from 0 to 15 on x and 0 to 15 on y。

That indexing is always0 index， so it's always going to go from 0 to the dimension minus1。

On both on athletees。So now you have this 2D block。

Now you need to have the blocks in a grid and you need2 by2 right so if you have 16 by 16 threads and you have a 32 by 32 matrix you need four blocks that are two rows and two columns right so that means the block index is going to go 0 to1 and 0 to1 if you had more blocks then they would go0 to n minus1。

And then block them。😡，Which is the same。On both dimensions here is going to be 16， right？

So these are our equations that we calculated in the indices。

 the global I and the global J as the global row and column。So let's look at this example where。

I is essentially block IDX can go from 0 to 1。And then thread IDX can go 0 to 15。喂。Block IDx。

ty can go 0 to 1。And thread ID Xt y can go 0 to 15。So the minimum value of x is 0。😮。

The maximum value of x is 31。Same for why。Why am I telling you this if you think of a 32 by 32 matrix。

 you have 31 rows and you have 31 columns。That's what these are covering。

All the values between these ranges are going to be somewhere in between that。😡。

So you get your full matrix coverage。So that's why doing this indexing correctly is like the first challenge of QUa programming。

Let me pause for any questions。Yeah。So王。然回。这。U3。Fature calculation of just like a one by one brand because it's yes you good。

 yes。This is an example just to show how the math works here。Other questions。I curiosity。呃，因这个。15。这点。

放过去。If they change it it may break a lot of ka programs， I don't think they'll change it。

They'll change other parts， but that is one of those things and war size which we learn later is probably another that they won't change because it'll affect the performance of certain QUDRA programs a lot。

啊，算。是。Yeah， I'm not talking about memory at all， but yes， yeah。Other questions？All喂。All right。

 so let's continue。嗯。So。The one thing to remember。Is that blocks execute in parallel。

Just because a block ID may be zero and another block ID may be4。

Doesn't mean block IDd0 will execute before after or simultaneously with block 4。

There is absolutely no guarantee that Kuda gives you and you should assume none。Okay。嗯。

The reason they are that way。Is purely for performance。

The scheduler is really smart to figure out what kind of GPU you have。And configure it based on that。

 so if you look at an example like this where you have a number of blocks that you want to run。

And we have two examples， maybe there's a GPU with two Ss and a GPU with4 SM。

 so this can be a laptop GPU that can be a desktop GPU。

The scheduler will figure out what your ordering is。😡。

You have no control over that and that is something that is both an advantage to take off as well as helps with performance so so yeah don't assume that even within a block。

Even within a block， all threads execute simultaneously。

There' is no guarantee on which thread may or may not execute at the same time and I'll share that in a little bit。

Everybody clear on this？😮，O了。All right， so let's talk about memory。

So one of the things I didn't discuss was memory so far we've just seen AB and assuming that they all work magically。

So let's talk about memory。Logically， this is what it looks like。

We had the big high level architecture before， so CPU that has ran that all of you have 16 32 GP or something like that in your laptops。

The GPU has high bandwidth memory， which again would be 8， 16， 12 GBb as you have on your GPUs。

The the GPU can only communicate with the memory it has so when you are running a kernel that can only talk to high bandwidth memory。

The CPU， when it's running serial code on the CPU， that's only going to talk to Ram that can't use data from the device memory。

Everybody clear on this？😮，So。The host。Or before I talk about that。

 so how do you how do you get data into high bandwidth memory for the GPU to even process， right？

So that's where the Kuda memory transfers come into play。

The host can write to what we call the global memory in Kuda。😡。

There are two types of memory on the global side， there's the true global memory。

 and then there's constant memory， there's textures， but we don't really get into that in this class。

嗯。Global memory is what you're going to use most often it's when you say you have a GPU with AGB of memory。

 that's what it's talking about， it's talking about the amount of global memory that you have。

to allocate and do the transfers first you have to do kudamalc。Which is allocating memory on the GPU。

Like we do in C。C has a Malic function that most of you may have used that's going to allocate memory on the CPU。

 Kudda Malik allocates memory on the GPU。And just like you do on the host。When you call Malik。

 you have to call a free as well， you have to call a kuda free to free up the memory。

This is how the API works You have the Kuda Malik and the Kuda freecon。

what you have to do is you have to give it a pointer to the device memory so you declare a float like this。

which is a pointer and then you are unindexing it even more to get the address to the pointer so that the ka memory pointer can be stored into that。

Okay， so always make sure that you do this dereencing and the void star star and then pass the size in bytes。

Any questions on this API？Yeahep。Kudamalic is also free of any types。

 so that's why we use void it's all it's doing is allocating a bunch of bytes on the GPU。

 the type is defined by whatever flow or rent you may want to have。

Then there's four types of mem copies， so we allocated memory。

We want to copy information into that memory or maybe from that memory。

 so we have four types of me copies。First， host a device。Wwhich goes between the host and host。

 you really don't have to use kuda me copy for this right。

 you just use meM copy or any other copy function in C or C++。

Here's the API first you call Kuda M copy。It's always the destination first。Then the source。

Then the size and then you have an enum that tells which direction you want to be copying because a men copy like this if you just give it two random pointers it's not going to know which pointer is on which device so thats why that enum is important so here we are doing a host to device copy。

Where we are copying some information from the host and CPU Ram into the GPU。

So you're going to pass the device pointer， host pointer。

 the size in bytes and the direction of the copy。Now you want to copy the information back so you copied the information from CPU to GP。

 let's say you ran a kernel and now you want to copy that memory back the API is the same the ordering changes now you have the host point as the destination first。

Device point as the source and then the direction is device to host。不者。Finally。

 you have a device to device copy， so let's say you want to create a copy of your memory on the GPU。

You are going to use the same API in this case both the pointers are on the device now you can see why this enum matters a lot to tell the API which direction to copy it so both pointers on the device the size as the amount of bytes to copy and the enum to tell which direction to copy it。

Questions about Re behavioran。Just是。No， because here I have variables that say source and destination and source right if I hide this and hide hide this essentially。

 can you tell me if they are on the host or the device？If they're just pointers。That's information。

 that's an address。You cant tell if that address refers to CPU。

 host side memory or device side memory。Because they don't have to be unique。

 you can have address one in both host and device。So let me take an example。

 let's say Market Street exists in a lot of cities right if I say 100 Market Street without specifying the city。

 youre going to ask which city。Kind of like that。Other questions？Mike a simple example。Soそ。

So let's take our matrixtri edition that we did。You are going to allocate memory on the host。

Before you run the kernel， you have to copy， host your device。You run the kernel。

 it's computed C right， so a plus B， you're going to transfer host to device。

Cangculate C on the device。And then you only need to bring C back because A and B are the same you haven't changed those。

 so for C you are going to do device to host。Then you are going to do。

 let's take an example of device for device， let's say you're doing a transpose on a matrix。

You want to keep your original matrix， but you only want to transpose a copy。

 so what you do is you make a copy first and then you can do a transpose in place。

So those are just very high level examples。You had a question？知要吧。Absolutely。

 so so you get it's regular C indexing right so if you want to copy let's say half of the bytes。

From the start， you can give it the same pointers and half the size。

 let's say you want to copy the second half。You can do source pointer plus whatever the offset is。

Give the sizes half and copy that so it's completely regular pointers。

 nothing special about them compared to what you do on the CPU。Other。じ。So。

 so device addresses are always going to be given to you by Kuda Malik so when we go back。

So this Malic address。So device memory here is null， right so we are saying。😊。

Give me a float that towards the address null， that's what this line is。😮。

What we are doing here is given kuda Malik。A reference to where that pointer is stored to go right the address of the pointer on the device。

So， the value stored in device memory after this line of run is the address of the memory in the device。

So when you pass something like this kuda Maluk。To。

To this API now you see that you are getting the address directly。

 so Kuda Malik is taking the data the reference to the address and then putting the address in there。

😊，Yeah。Just load just to insert turn that intos the right size。

It's it can be any type so you can have an int， you can have an unsigned and the type of the pointer that's why it doesn't matter。

 that's why it's like white star star。The type of address is purely for human reading。

Other questions？No，Thatt hard。で道。上说了吧。啊好。Very good question。

 so your question is is this APIynchronous or asynchronous？

The way it is written its synchronous so this function will wait until the memory copy is completed before moving on there is an asynchronous version of this function that we will get later in the class but for now this is good enough。

Other questions。Everybody understand basics of memory copies and how to use them。Okay。All right。

 so let's take a look at an example。We look at SA XPY。

 how many of you have written a very simple SA X PY on the CPU？

How many of you know what SAXPY I am talking about？So SAXPY is essentially this。

It is single precisionion， so S standing for single precisionions of float。A times x plus y。

So any equation you've written that does8 times x plus y is a SAXPY equation， very common。

 especially when you think about AI and stuff。😊，So you have two vectors in our example we will take the as2 bit floats。

Of n elements each and a scalar value a。The output is a z vector that has。

The same length and all you're doing is a times x plus y in an element wise manner。

So CPU implementation is something like this where you have you pass in the size n。The scalar a。

 then you pass x and y is vectors and a z for output。

And you go through the follow loop that does element wise SAxpyY。

Then this is like the function call that passes it for let's say，1 million elements。

Here's the KUDa program for that。This is the host code and it's basically in full。

 so this is we were talking about micro programs before we are looking at a full program now。

First let's initialize how many elements we want to have here we will hard code it。

 you can do it other ways of course so lets say we want to do SAXPY on 1 million elements。

We'll calculate the size and bytes just to store it for reuse。We will also assume that the CPU。

Fill that data。Especially for x and y okay you can do it in any way you can use random functions。

 you can use other things， we assume that's done and ready。

On the ka side we are going to do three ka Mals for x， Y， and z。

One of the things you want to use often is and this can be， however you like it。

A notation that tells you which pointer is on host or device。This again。

 purely for your programming and your style guide， you can use DNH， you can use other forms as well。

But use something so that you know which variable is on water and you don't confuse them。So。

 we have DhDY， sorry that is a typepo there clearly we need to have DhDY Dz。

So you do quo amalic on that and you pass size and bytes。Okay， again。

 notice that while we are declaring float here， these three callss are completely void of any types。

😊，So they allocate purely in bytes。Once you've done that， you copy X and y to the GPU。

You don't have to copy Z because that's not computed， so you only copy X and y。

Then you launch a kernel。In this case， it's a one dimensional computation， a vector， right？

So I'm going to simply pass 496 blocks of 256 threads each。Just a very simple one。

 you can do other configurations as well。That isThat is a simple one， I'm going to pass n。

 I'm going to pass my scalar whiles2 along with Dx， DY and DCz。Once that's done。

I want to copy the memory back。So I only need to copy Z because I haven't changed x and y at all。

Again， you're going to copy size and bytes and note the device to host。Any questions on this。

 any questions on the whole side？嗯。Dbut the。Yeah， so your question is。

 how do you choose dimensionality？Most of the time it's up to the type of algorithm you're running。

If you're running a matrix， you want to choose 2D， if you're running a vector， you want 1D。

Can you run a matrix operation with 1D configuration。

 absolutely because ultimately all you are calculating is t in piecesesis and how they map to memory？

😊，Memory is always one dimensional。So all you need to think about is how does my threat inds map to my memory？

You want to use something that makes sense like 2 d for matrix because we can understand and program it better that way。

对。The way to the biggest on the beach。I think our dimensionity is for us as the programmer to be able to better understand what writing。

Yeah， most of the time yes， it does have some implications of performance。

 but if you are indexing your straightforward， then that's going to be minimal。Other questions。

If there ever be a case， we want to。dimensional。Flocks over。So poisonly。

 we could have like one block of 16 Yes， we ever won 16 by 16 blocks or one。Yes。

 but not that extreme like for I'll change your question to say， do you want？

Four blocks of 1024 threads， so 4，000 threads or 16 blocks of 256 threads， so also 4000 threads。

That is definitely something you have to consider and actually a question you have to answer on project one。

And so I won't answer the why once you do Project one， it'll become pretty obvious。Yeah。It just的。

すごかこ。Pos actually be faster with all the overhead brokens。Do clean stop on posting Z here on the day。

What do you think the answer is？Okay。Who else has a different opinion？Yeah think。那你。到。判月。

Hundreds of thousands times faster， are opinions？Yeahep，Exactly。

 it depends on the size of the elements so both of your right in your own right like would I do this for 100 elements now never would I do it for a million。

😊，Probably would I do it for a billion definitely。So yes。

 it very much depends on the size and something you'll see in project2 about how size matters for getting acceleration over CPU。

Other questions？Okay， so we've seen host code， let's look at device code。😊，So。

Here I've kind of truncated the main function。And from here we are calling SAXPY right so we have global as we did before because it's a kernel devoid because a kernel doesn't return anything SAXPY and then we have our variables note how we are passing cons float x and cons float y to indicated the compiler that we are not going to be writing to x and y and then float Z is our output。

Our 1 d indexing block IDx time block 10 dot x plus thread idx again said this many times get used to this。

You want to check indexing for out of bounds because 1 million is great because its a power of two。

 but if it's not that you always want to check out of bounds。

And then actually do the element wise is SAXPY operation。Any questions on the kernel code here？哦，对这点。

Build嗯哼。我没。Imagine hes checking down。It better。 Would it be better to write two different device code and then launch common twice。

Most of the projects definitely mean Zs， not check。That's a very good question。

The answer to that is what you learn throughout this class is on the GPU。Computer is basically free。

What that means is。There's essentially two things that you're always doing when you write a line of code。

You're reading memory， doing an operation and writing memory。

The memory operations are a lot slower than the compute operations。

 even though they are built like really fast and much faster than the CPU。

 the computer is always going to outpace the memory almost always unless it's a very complicated algorithm。

So this con here。😮，Is basically going to be maybe two cycles at most three cycles to execute。

 so it'll be very very quick so it's not as something you have to worry about。

But it's a good thing that you're thinking out of the box that way because it will apply to other algorithms。

Other questions。All right。So positive of performance。Here's an example of why you' run on a GPU。

So this is running on it。2 AMD CPU server with 128 cores， 256 sets and nothing to laugh about。

 so that CPU versus an A100 NviDdia GPU。And。I believe if I remember correctly。

 this is the number of times it's faster。I think this is for forget the size。

But I think it's like a billion or in the order of a billion elements。

 and you can see that it's 20 to 25 times faster no matter which algorithm you use。Basically。

 because the CPU has a follow up that' is going to run or O ofn， even though you have 256 threads。

 you still have an O ofn。Whereas the GPU is basically constant with some scaling based on the number of blocks you've done in launch。

So that's why now for much smaller sizes， the CPU will be faster， there's no doubt。

 but when you're thinking about GPs， you want to think about big sizes as well。

Questions about this performance slide。嗯，你是是意的。So。No。

 so if you compare just the CPU fall loop to just the kernel， the kernel will be faster。The overhead。

Is in the memory copy， it's in taking CPU memory， putting it on the GP and GPU memory back to the CPU。

 that's the overhead in using GPU programming。Other questions。Okay all right。

 so let' us look at matrix multiplication and we will you look at a simpler form of it then in the next class we will look at how to actually optimize it。

😊，So a reminder， a matrix multiplication is p equals m and we use star here for matrix multiplication m times n。

Where if you break down the matrix multiplication。😊。

You want to think of it from an output perspective， so matrix addition SAXPY。

 you can think of it either dimension it's totally fine because it's element wise。

Matrix multiplication you want to think of fit from an output perspective。

 so when you're doing your indexing you want to think of the output first。So。

Breaking it down each element of the result P， So this each element is the dot product of row M and column n。

Where each of those dot products is an elementwise multiplication。

Okay so there there layers of operations now， you have element voice multiplication。

 you have dot product and that is going into a single element。

 so there is an addition involved as well。😊，In this example。

 we'll assume M and are squared for simplicity before we look at a more complex example in the next class。

Before we look at the actual algorithm。If you have a1 thousand0 by00 matrix。

 how many operations is that？Anyone want to take a guess。T0 to the power of 12， how many is that？

That is。대라？I think it's right。1，000 billion。Okay。So let's look at a CPUview example before we come to dance answer。

So I assume all of you have written matrix multiplication code at some point。

 but it's good to have a refresher。The first two four loops are going to do your CPU the itration over the row and column and again think of it from an output perspective so each row and column of P is what you are thinking about。

The sum is your accumulator， the k is doing the dot product。

 so it is it tradingrating over element y is this row and this column。

You are calculating the dot product with the indexing note that even on the CPU you have the same style of indexing now。

Then you do the sum of a times b and then finally write the output to P。嗯。

Any questions on this just to confirm？Okay。So when you think of this。

 each00 by000 matrix has 1 million dot products。😊，Which has 10 ads and 10 multiplies each so going back。

Thous0 element，00 times this fall loop， thousand0 times this fall loop and then this k is  thousand0 as well and in that you have one multiplication and one sum we ignore the indexing indexing is overhead right so the pure computation is what you are calculating for the result。

So you have one edition， one multiplication， and that is 1 billion ads in 1 billion multiplies。

Just for 1 thousand0 by0 matrix， it grows really， really quickly。

So you want to have considerations of the GPU， it's a lot of simple math operations。

 just addition and multiplication， so like I said， it's all basically free compute。

And it's highly parallelaling。If you think about matrix multiply and think of it from the output perspective。

😊，It's an element wise operation on the output。Which means。

Each element on the output is completely independent of all the other elements。

Element1 and one or one and 2 is independent of one and three and so on。

 so that's where your parallelism comes in， thats where you want it to have the advantage of the GPU。

So let's look at how to do this。Let's do a skeleton first on main like we've seen with SAXpyY。

You want to allocate and initialize MNNP and then populate MNN。

And then you want to copy M& N to the device。Second。

 you want to do the matrix multiplication on the device。Third。

 you want to copy P back or to the host and then free of the memory。

So step one within that is the memory transfers。So let's look at the horse scoring。

So we'll do the size and bytes just so that we are saving it and then we have the floor pointers。

 we are doing ourkuuda Malik as we've seen so far， so nothing special here everything that we've seen and all the other examples exactly the same。

Again， note how I'm using different notations to give you examples here I'm using dev as a prefix。

I use D underscore before now I'm using dev again completely it's up to you how you want to use the notation。

 just use some notation。Once you've done the allocation。

 you want to do the Me copy and we' are assuming that host and host and are defined somewhere and populated。

 so that's why we are getting that as input here for the function。

You want to copy size and by and then do the hostster device direction。

We'll come back to the kernelel in a bit。Let us assume the kernel is done。

 you want to copy the memory back from defp to host P right that direction and that is the device to host direction。

And then finally， you want to free all of the memory， you want to be good C and C++ programmers。

 we want to free the memory。All right， step two， let's implement the kernel。

Here's a matrix multiply kernel for a square matrix multiply。

few things that we will call out first global to specify a kernel white to specify that there is no return value。

Use const for。Memory that you are going to be reading from and not when you are going to be writing so DP does not have constant with it。

You're going to use indexing to get the memory address for the matrix。You have an accumulator。

We'll call it a P value here。You have a fall loop。So the question I want to ask is what happened to the other two follows that we had in the CPU code？

Anybody shout it out？Which is perfect。Exactly part of the threads now the threads are doing those two follow loops for you。

 so you are essentially removing that O of n squared and now you have a two dimensional kernel that is going to run in parallel。

😊，All right， so you still have the K for doing the dot product because that is a sequential operation that we can't。

Do in parallel， so we have the K。You're going to do the 2 d matrix。

 but 1 d indexing like we saw in matrix addition as well。

And then we are going to do the accumulator like just like we did on the CPU。Finally。

Write the value into FP。Any questions on the kernel？

No questions now that you've seen Matrix Ed SAXPY， this feels straightforward。어때요？All right。

 so we've done step two， let's do step three， which was involve the kernel that we said we'll come back to。

So heres here's how we want to call it， we want to have width by width threads and blocks being one by one。

And then we'll launch the kernel just like we've seen before with the kernel in vocation blocks。

 threads and all the memories past it。So any questions on the matrix multiply example？

I have a few questions， but I want to ask those after you guys ask。No， it好。A threat。

 a block can have 10，24 threads maximum。是的。No。So that's why you need to divide it into multiple plot。

Other questions？Could I ask Mike？You have a question？So in this case。

The CPU will wait for the kernel to finish。There are asynchronous operations that we learn a little bit later。

 but for now you can assume that this is aschron。Other questions？All right。や。Nothing。Yeah。

 if you just do dim three blocks of one or even just open and close bracket， it's the same thing。

The default values are 111。Any other questions？Okay， so you hit are my questions。

What is the major performance problem with our implementation？

I'll go one by one on the question what's the major performance problem？Yeah。你你也有好。哦。😮，对呀。30天。How。

That is not the problem， but your clothes。 Think of it in a different way。 the。Your cop。

 like as in like， we could just transfer them once to like share move。

Which are you talking about dev and dev and D？No， we are not copying them because once we put them in kam and copy that's happening once and then if you want you can invo the kernel multiple times。

 but again I'll say the same thing I said to him， you're on the right track。

 think of it in a different way。Yeah。😊，叫林下。Which member read？你好。What does that mean？で、すね。你讲。哦。

WeAs said reading memory compute exactly。For each of these。

 let's say 10 by000 matrix right k is going to be 1000。

You're reading a thousand devNs and a thousand dev ends。For each of the dot products。

Thats 2000 memory reads for each dot product and that is multiplied by a million elements in P。

So youre doing a lot of memory reads， how to fix that we will come back in the next class。

 but yes global memory is a problem。嗯。All right， next question， what is the major limitation？

H welcome back here。Yeah， each matrix is just one block， right。Exactly。

 so we did a very simple matrix multiplication。😊，That was one block and which means 32 by 32 threads maximum。

 so our maximum matrix skies would be 32 by 32。I asked the question that was asked before。

 is that even worth doing on the GPU？Probably not 32 by 32 with the overhead of memory copies is likely not worth it on the GPU。

 so that's something we want to fix as well。My last question is what were the assumptions we made in our kernel。

 so let me show you the kernel。What are the assumptions we made here？

So definitely that it fits into one block is an assumption， what other assumptions are we making？

Yeah。That the index is never out of bounds， yeah， we are not checking for this index out of bounds。

In what way？呃，P标。Well， let's assume that it's not yeah。😊，Other questions？Yeah。Yeah。

 so that's definitely an assumption， what else？There's one more assumption we've made。それ？

It' is a square matrix so this kernel is also limited to a square matrix we don't have to worry about rows and columns being different dimensions。

So。Going back here。So those are the limitations。Of our very simple kernel。

What we'll go through in the next class is the next level of memory memory things， threat things。

 and then we'll conclude with how do you optimize matrix multiplication。

 how do you take this very simple？Matrix multi and make it bigger。

 faster better in every way possible so this was purely introduction to Kuda you know you you learn about threads blocks。

 how to invoke curl the memories。Next class willll start getting more advanced。

 so when you go back and do project zero take a look at the code because it's a very simple code all it's doing is assigning colors to inds。

In the memory， so take a look at that code， try to see how it's working and stuff and then in the next class we of course dive much deeper。

I'm happy to take any questions， but otherwise that's the end of the lecture today。

 so I'll just pause if there's any hands raised。嗯。嗯。You might not be able to enter。考后。

Like being able to use like practically in what you do。A lot of different ways。

Lets say take I'll take this example from my time at A fire was。Medical company。

 I'll just be vague about it， they were doing image comparisons。

Let's say they had some sort of device that was capturing bacteria cultures。

And they were capturing two images， they were capturing a very big image。

 and they were capturing a very small image。And what they wanted to do some analysis on that to identify features and how many bacteria cultures than there were。

So what we helped them do was。Image processing is a very parallel algorithm。

 so we took the big images， put them on the GPU， very small images parallellyzed them on the CPU and now it was like  a thousand times faster。

Pretty much everything nowadays has a GPU running behind it。Use Snapchat filters。GPUus。

 Google's new AI that does the adme thing where you can instead of taking yourself and you can add yourself to a picture GPUs。

 So simulations， whether simulation， GPs， pretty much all of the examples that I showed before。

Are using either kuda or some form of compute APIs to do it in the background。

 the visualization is the end result。Unless you're playing a game or a movie the visualization is the result only that they care about。

 but most enterprise applications use Quda for analysis， performance and stuff like that。

Any other questions？Yeah， program。When would you use Ko versus a computer？

LetLet me ask a question to anybody who's done an internship where this might be applicable。Yeah。

 그 ahead。I。嗯。我你天。谢。Right so so that is spot on the compute shaders live within a graphics pipeline that's the best way to put it and that's why we are starting with Kuda and we learn about web GPU and Vcan later。

 whereas the other way around where if we started teaching about web GPU and Walcan we would have to also teach about graphics pipelines and triangles and all of that we didn't single time talk about triangles today。

 but if we were to do that we would have to about triangles pixels all of that。

 so Kuda is pure programming whereas a compute shader lives within the pipeline of a bigger visualization context。

Other questions。All right， I know we went a little over 730 so thank you for sticking around hopefully you guys will continue to come back for 565 and not get scared and I'll see you all next Wednesday。

😊，没有。

![](img/227a0511064268582643d942dd8ad682_25.png)

有这。Yes。
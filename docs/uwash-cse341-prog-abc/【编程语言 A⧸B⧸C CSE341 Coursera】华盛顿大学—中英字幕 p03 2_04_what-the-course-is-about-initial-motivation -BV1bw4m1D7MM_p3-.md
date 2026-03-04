# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p03 2_04_what-the-course-is-about-initial-motivation -BV1bw4m1D7MM_p3-

In this video I want to talk about what the course is really about programming languages and why one might want to take a course about this sort of material The idea is that we are going to learn the basic concepts that underlie all or almost all programming languages and how those pieces fit together and while we're going to use the standard ML programming languages here in part A of the course racket in Part B and Ruby and Part C。

 we're doing so because it lets the concepts that we want to study really shine and focus on the key ideas in real languages where they tend to be easiest to learn and focus on what we want to focus on and by using multiple languages。

 we can see how the same concepts because we'll see some of the same concepts over and over again using all three languages can look different when they sometimes are a little different and more often when they're quite similar with just some basic syntactic differences in the different languages。



![](img/7b3eda6801ffa6700f1051d86eb18306_1.png)

You could ask， why aren't we using Java or C sharpharp or Python or scholar or JavaScript， Well。

 in many ways， the languages we're using are simpler。

 and when we're trying to study the core concepts， simplicity is a virtue。

The other thing I would emphasize， even though it's not in the course title is that we will emphasize functional programming throughout most of the material that we study so what does that mean well we'll learn when we get there but it means we're not going to have assignment statements or much in the way of mutating or updating the contents of memory which may surprise you and if you've never programmed in that style before。

 don't worry about it， we'll get lots of practice it also means we'll use firstclass functions and function closures a really important topic but one that I can't explain in a short video so let me just leave the jargon there and don't worry if you've never heard it before and of course we're going to do much。

 much more as well。

![](img/7b3eda6801ffa6700f1051d86eb18306_3.png)

So normally you would spend some time at the beginning of a course motivating why you should learn the main topics in the course。

 but in my experience， it's very difficult to do that until we've built up some shared experience and shared terminology and you've done a homework or two or actually three to understand the basic ideas behind functional programming in particular and programming languages in general So what I've done instead is made a collection of videos that motivate the course that will be delayed and will come after section3 in the course Now unfortunately that means you kind of have to trust me for now or trust the students who've come before you who like to say things like you know at the time I was learning in this strange language and doing this strange stuff but afterwards I was able to go back and learn things I had tried to learn before and found it so much simpler because you gave me the perspective and the terminology and the concepts I needed to pick up new program。

Lguages and understand the programming languages I already knew better。

 So I'm asking you to trust me because if I try to motivate the course without having taught you the concepts。

 I'll just be using a bunch of fancy words and talking in abstract terms that don't make a lot of sense。



![](img/7b3eda6801ffa6700f1051d86eb18306_5.png)

But what I would like to say is one highlevel idea that I deeply believe。

 which is that learning about this material will give you a new way to think about software that will make you a better programmer even when you go back to the environments and programs and languages that you already feel comfortable with that on top of that give you the mental tools and experience you need for a lifetime of confidently picking up new languages and ideas and for being able to reason carefully precisely and correctly about the software you're writing and I fully admit that as you get into the first couple hours of material in this course and do the first homework。

 it will feel like nothing you've done before and writing programs if you haven't done this kind of functional programming before and maybe the best analogy I can think of are these movies the karate kid I remember it for my childhood and then it was remade in the 21st century in this movie if you've never seen it。

 I don't claim these are particularly great movies but they are。😊。

what they are you have a kid who wants to learn how karate。

 a martial art and is told instead to spend days and days cleaning windows and washing cars and doing other menial tasks and it turns out that he's building or she I think in the remake the mental the muscle memory to do exactly what you need to be successful in karate now I know nothing about karate but I do know some things about programming languages and writing software and I believe what we're going to do in this course particularly early is building those basic muscular skills and basic ideas that will then be able to build on very quickly in order to understand in a compositional way how more complex software and algorithms and programs can fit together in an effective way so perhaps that analogy will resonate with some of you it's certainly a good way to motivate yourself early in the course when you're doing something that feels very uncomfortable。

😊，Or unfamiliar。

![](img/7b3eda6801ffa6700f1051d86eb18306_7.png)

And indeed I want to emphasize that here in part A of the course。

 we're going to use the standard ML language which probably very few of you have used before。

 we may use the text editor you're not familiar with what editor use is optional but you may not have a familiar development environment that you're used to for other languages and we're going to evaluate our programs using this thing called a readdevelopval print loop that will feel different than the normal compile and run cycle that you may be more familiar with you're going to have to install software you're not familiar with and you're going to have to get these things up and running before you can really start on the content of homework One and I understand that's an extra burden but I think it's also something that you will grant that in computing is fairly common that as you take different courses as you take new jobs as you new new things。

 you're always working in strange new environments and installing new tools and while it may not be fun and often causes complications and it can be aggravating at first it's something you get more comfortable with time。

And this course， like many， requires you to do a little that right at the beginning so you can get started。



![](img/7b3eda6801ffa6700f1051d86eb18306_9.png)

Let me emphasize again as I did in the very first video that this course is not about M。

 and when you get into Part B， it's not about racket and part C is not about Ruby。

 these are means to other ends。 these are chosen as languages that are particularly good fits for the topics we want to present you could teach these concepts with other languages but I've chosen these because I think they're particularly good tools for what we want to accomplish and let me say right here in introducing the course that standard M in particular is not a fashionable language that these days is used for real software and that's okay because we're not in the homeworks in this course trying to build real software we're trying to give you the background for building better real software in other languages in the future。

 So there are closely related languages that are very active and effective and still in much more common use today in sort of decreasing similarity from standard M。

 you have Ocal F sharpp， Scala and Haskell each。Be an okay choice for part A of this course in various ways。

 I think standard ML is a slightly better choice and in fact I could argue and will argue here briefly that it's a bit of a feature and not a bug that we're picking a language that doesn't have a lot of modern libraries that doesn't do a lot of things in the modern software ecosystems that way we can focus just on the core ideas。

 We won't be distracted by trying to do anything fancy。

 we won't have a lot of complications that are common in modern software development。

 we get to focus on standard ML， which in many ways。

 even compared to these other wonderful languages， is clean。

 compositional and elegant in ways we're going to start seeing even in the first week of this course。



![](img/7b3eda6801ffa6700f1051d86eb18306_11.png)

Let me also emphasize that these introductory videos are a lot of text on PowerPoint and me just telling you stuff that's not the way most of the course works。

 I think that you learn about software by writing code and trying things out and you'll see that we do that in a lot of the videos there's in video questions with quick quizzes on things in short I actually think that most the videos in this course are better than the introduction videos but introducing things is just something you need to get through and we'll get on to the good stuff soon enough。



![](img/7b3eda6801ffa6700f1051d86eb18306_13.png)
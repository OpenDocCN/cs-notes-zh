# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p04 2024-09-09 - 3-Parallel algorithms -BV1sRtresE67_p4-

Okay all right， so for recordings I'll start with the schedule so we are here on September 9th。

 so today we'll cover a couple of decks， we'll cover parallel algorithms and we'll cover the readme tips so that'll help just think about how you did your read mes again no wrong answers it's more about how do you improve。

Normally before this lecture， I would do a GPU architecture overview on lecture。

 but this year what I've decided is that。It's great to have that but I don't need to do it as a full in class just so that I can teach new topics I web GPU and Vcan。

 so to make space for that we've made this a recorded lecture it's good for you to watch but it's not mandatory it's not going to affect any project it's more of a theoretical lecture on how GPUs are built essentially and I don't mean in how theyre manufactured I mean more in the sense of how did we come from the 90s where you had you Pentium core Intel CPUUs and video cards essentially not GPUs video cards。

To having very powerful GP is now how at the scale and stuff so that gives a little bit of understanding of why is warp 32 of 32 threads you know why is single precision floating point faster than double precision floating point and so on so that's recorded from 2022 so feel free to watch that at any time。

嗯。All right。Project 2 is out so its available for you to see here this does work with WSL for those of you who want to use it because it doesnt have a graphics output when I tested project 2 it worked so if you want to try it out using WSL and Kuda fine to do that。



![](img/0fffef76cafb255ef64c2303232fa23a_1.png)

Okay projectject one good good feedback from all of you so a bunch of pull requests open I'll just show a few pull requests that I thought were well written the descriptions doesn't mean others were bad I've just pulled out like three random ones that I thought were well written to just showcase how how you should be writing these first by Alan and I'll zoom in here you know it talks about the features completed and then some feedback which is always very helpful like I said。

嗯。Mike also highlighted the extra credit completed so that tells the TAs when they're grading and finally from Carlos。

 there's a note about doing extra credit but he wasn't entirely sure so again。

 good to communicate that to the TA so that when they are grading the projects。

 they know what to look at。I haven't looked at all the readmes。

 so Im not I don't have them pulled up maybe in the next class I'll pull up some good readms and also show you about those。

Any questions on this？

![](img/0fffef76cafb255ef64c2303232fa23a_3.png)

O。All right， so let's jump into。The treatment tips。

So this this is a short deck and it's independent of GPU programming itself。

 it does obviously borrow a lot from GPU programming。

 but you can use this for any project that you're working on and really talks about。

And don't take this the wrong way， it talks about how to market your project。😡。

And I'll get to why in a little bit。So what？What does the read me do for a project。

 what does it actually try to communicate， what do you guys think？What should be in a good dream me？

Yeah。对什关。And so construction of。Use how you can pull those steps。Okay。

 summary of the project and how to build and run it Matt have some background understand。

Whatever terminology or whatever you need to。You have background on technical terms， Paulina。继续。

So how much of a great work you've done， yeah， Allen， known issues and bugs， yeah。😊。

License information very important here。other things that should be in readby。A demo， yes。All right。

 maybe one or two more。Yeah， which one。Expected output is a good one yeah so so yeah all of you're right and sometimes you might think oh this might make my read me too long but there's different ways to break it out for example you may say most of the people who are seeing this re are not going to be nondevelopers or I'll put the build steps in a different file or vice versa you may say most most people who are seeing my report developers so I'll put the build step first so there's different ways to slice and dice that that you can think about based on your audience who's the audience for your 565 projects。

😊，Employers，Employs。What kind of employers and who among your employers？喂。

Anywhere from a hiring manager to an engineer。Okay， so somebody technical。

Maybe one more kind of people among employers who's looking at your projects。そし。C is a company。

 but what kind of roles within companies are looking at your projects？是。HRs， yes。HRs。

 And so when you think of engineering managers versus technical leads versus engineers。And HRs。

 whats the common denominator？The common denominator is HR right among technical understanding and these are very technical projects。

 HR has the minimum understanding， thats where you want to start。😊。

If the HR doesn't get your first paragraph， he's going quit how many resume is does an HR look at on a daily basis。

 maybe like tens if not hundreds and they are spending a few minutes on every resume and they want to see how you stand out so the read me is a great way to make that happen。

😊。

![](img/0fffef76cafb255ef64c2303232fa23a_5.png)

Okay。So， the first thing you want to do。😊，Especially in neo cases is provide context for the project and maybe contact info that's why we have you fill out the top part of the readMe right with like your LinkedIn or website and stuff and then have a representative image。

 ideally the best image you've generated or a G if you want。

Um so that way it really communicates what the project is about， what you've done and so on。

You can use screenshots or architecture diagrams to walk through the different features of the project。

And these are pretty much all screenshots from 565 project unless there's maybe one or two minor exceptions。

So what these kind of images do as well as。Other images that I'll show in future slides is communicate that this is an original authored work。

 like sure it may be part of the class， but you've done it yourself， you understand how it works。

 you understand how each of these steps work。嗯。When you have images。

 especially when you think of people like HR。You show them a racial image。

 they may not know what all the features are。😮，Like maybe they work for a movie studio and they may get it。

 but most you know companies won't have an HR that understands the features of a rendered image。

 so highlight them。I'm showing you a render dimensionmentia。

 I'm sure this applies to various other projects highlight and annotate things that are important。

Dbu screenshots are a great way to show that you understand the project and what you've done sure they may not look the prettiest。

 but it shows that you have a level of technical understanding of each of the steps and you've taken the time and thought process to evaluate it same goes for engineering managers。

 like if I' see debu screenshots for candidates I'm reviewing I love it。

It gives me an understanding that this person knows how to use a debugger。

 this person knows how to look at a problem， break it down and solve it。

 so that becomes really important。Side by side comparisons are really good。

 you know showcasing what you have improved， especially with things like extra credit or new features that make you stand apart from your classmates。

 side by side screenshots are a huge deal if you didn't have this and you just had this。

The HR would think it's pixelated。Right？But you have to show it in a relative sense about what is the relative difference between the two so you may have absolute。

😊，Master classes， but also showing the relative differences can get you a long way。



![](img/0fffef76cafb255ef64c2303232fa23a_7.png)

嗯。Bloopers， I mean have， yeah， this is a side on blooper， bloopers are always fun。Now you may think。

 oh， I'm trying to put my best foot forward， why am I showing blueerss？Again。Original authorship。

 the fact that you show a blooper means you faced a problem and you fixed it。

That is the message you want to send you want to send the message that， hey。

 I understand at a deeply technical level how to solve problems。

You're not going to any company and build a void simulation for them。Right， extremely rare。

 maybe one in a million chance， if not one in a billion。

 but you're going to go into companies and solve problems， solve engineering problems。

And they're going to look for what are the problems you faced and how did you solve them and again I mentioned this in a previous class these kind of things are great to talk about your interviewer asks you tell me a problem you solve you can be like open the read me and I'll show you right you're not make up a story then you're telling you're telling an original thing that you went through。

😊，Video is also great。 There is from bloopers from。I think a few years ago， I can't remember。

 but yeah， anything like this is always fun。

![](img/0fffef76cafb255ef64c2303232fa23a_9.png)

Here's a couple more。I think the Z depth buffer in this was kind of flipped or something so it looks all weird and then this was supposed to be a crowd simulation。

😊，Okay， and you're only seeing legs， so I'm not sure if they walking underground or， but yeah。U。So。



![](img/0fffef76cafb255ef64c2303232fa23a_11.png)

Sometimes blueber look amazing this so you know I won' I won't take any pros but can anybody tell me what's going on here it's an open GL app by the way in the old 563 class when I took it in 20。

😊，22 or not， not 2022， 2012。So。Anybody want to take a guest before interview？

I'll actually slow it down。Yeah， what the blueprinters， yeah。I'll slow it down。So the。

The feature here was that I didn't clamp the colors。😊，So the colors were exceeding。😊，One essentially。

 so between  zero and 1 they were exceeding one and that was creating this really cool banding effect。

😊，Which was like， it's like a。icece beam or something like that or a five beam and sometimes it can look amazing I put that in my demoel right so I'm not shy of it so those kind of things can be good too。

😊，All right。Readme tips this is kind of what you want to focus on right you know bopers are write it first but really it can be at the end of your readMe you want to have videos or animated J or live demos if you can think about the process and documenting the technical aspects of your project。

 again， think about who's looking at your readmes iE employers。

And what kind of depth they want to go to start with the high level。

 you know target your HR target your engineering manager who are limited on their time and then make them want to see more right they should want to dig in more and that's what you'll get from this。

Have like some big statement upfront， for example， if you've done the I don't know if it's in 460 or 461。

 if you've done a CPU ray tra project or parts tracing project and you do the coa parts tracer。

 you're going to be。1 thousand times faster， say that up front that this is thousand times faster than my CPU ray tracing project and people will want to know why and how。

performanceformance analysis and we'll get into build instructions I already mentioned。

 you may want to either put it in the readme or have a separate document that's linked from the readme。

 at least link it from your read that becomes what is important。嗯。

Here are a few good readmes I haven't updated this for a couple of years but I think they're all very good so take a look at all of these there's a few more links here and then Patrick who was my teacher back in the day also as a guide on how to write good readmes you may want to take a look at that。

😊，Any questions so far？Okay， so again， not none of this is 5。

65 specific what I'm trying to tell you as。As an employer of。Students like yourself。😮，If you do this。

 you have way better chances， I would rather see a better read me than a better resume。

That especially for engineering students， that's really important。Okay。

 so lets switch gears a little bit to charts， so here's a chart from Anont。

Who sadly shut down recently to my surprise。But looking at this chart， what are some。😊。

Critical features of good charts you can pick out。And then I'll show you some mad ones。Oh。嗯。Yeah。

 they're all on the same scale， very important。other good aspects of it？Yeah。

 it is the actual problem。L list。Yeah。😊，Yeah， list the data points， you know。

 hard to differentiate between 160。8 and 159。2。What else？Alyssa。And help thing like hire。

Extremely important， I couldn't tell you how many people missed that， Paulina。Clearlyly labeled， yes。

 both have units and names。You人呢？嗯。Right， so for example， you have 2018 TI and 2018 TI founders Ed。

SBas the same GPU， but having the black colors here means you can compare it more visually。What else？

the basic set of they used for。Yeah， they call out what the chart is。Maybe one more。Okay。

 so so let's take a look at some mostly from this class about。How， how most rooms will。

Well do charts and I haven't picked from any from this year so don't feel bad about it。

 even if you have done chart similar to this it's a chance to improve when you go to project2 Matt。

thing I know I think。Probably typically you would like if I made this graph， I might export the axes。

 but it's easier to read the labels when you put put there Yeah。

 the direction in which you're transposing your chart could be important as well， absolutely。

All right， so let's take a look at some charts。The first one is label your aes。😊。

I have no idea what's going on here。I have no idea what's going on here， is this zero to 10 elements。

 is it 10 million to a billion elements， I have no idea what's going on here。😮。

So if you don't label your charts， they are not going to make sense again as an interviewer as a reviewer of your read meanss。

 I'm not going to understand did you get 2 x performance improvement。

 did you get 100 x performance improvement， I have no idea so labeled your axes。Units。

 extremely important， again， I can't tell you how many students miss this time and milliseconds and array size。

 extremely important， but also what is important is to pick the right size and represent it in a good way。

😊，I've told you throughout the class， powers of two are your best friend， right。

 especially for GPU programming。Not for your HR。Can you imagine your HR reading this？😮。

Like they have no idea what these numbers mean。They'll read 1，2，3，4，5，6， right the other thing is。

ThisIn this chart。80% of the space is wasted。There's absolutely no value to all of any of the space。

 maybe this is what's important。😡，So think of the unit size you're thinking about earlier before the class started I was answering a few questions during office hours and you know there were questions about。

 hey， I'm not seeing a big performance difference， this is why think about the sizes you want to be testing。

 Matt。😊，preferredfer to see that graph have a log scale on the Y axis or just cut it off so in the context of GPU programming。

 I just want to see this part maybe start from 18。There may be other classes where it does matter and you can have a log scale so that's not wrong。

 but GPU programming is big size is big data and you'd rather focus on that part of it。

Other questions on this？Okay。All right。So。I think Paulina mentioned that higher is better was there on that an stack chart。

I have no idea if slower is better or hard is better again think of the HR you know for a technical person I've seen this chart a thousand times I kind of get it。

😊，But。And HR won'， and HR will think。Higher is better， which is what humans are designed to read。

 but if you are thinking of running time no higher is not better。😊，Lower is better。

 so either you make one overrun time or you say lower is better and call it out very clearly。

So that becomes really important。嗯。Name your ranges， right？

You want to have the best performance again， this goes back to the earlier chart right but I said wasted space。

Again， look at this left hand side。You don't need that many zeros。😮，ふ呵呵。😊，Right。

We are not doing scientific computing you don I don't know is this microsecond， nanosecond。

 I don't know but。😊，Second， as an integer it totally fine and then number your elements。

 choose your right sizes and so on。😊，嗯。Okay。This one we called out you having similar colored lines for visual relation。

 I think is good， it always helps with the direct comparison。So yeah， those were my tips for charts。

 any questions on these？No。Yeah，Can we this with them。Can you make changes to your graph sum？

You should。If you make it obvious in the pull request that youve like add a new comment and say hey I'm adding a new chart and only the chart has changed。

 not the data， that is okay， we will take that okay we don we don't docu points for unless the chart is really bad and not good we want docu points at least in Project one。

But from a point of looking at your employer， yeah I want you to have the best chat so that you have the best interview going forward so I don't have a problem with your updating chart。

 just call it out very clearly in the pull request。So that when we grade。

Well see the last date to count your late days， but in the case where you're only updating the chart to make it better。

 totally fine。Good question。Other questions？Okay。So the next part I want to talk about is promoting your projects。

I'll start that by asking this question。All of you have potential employees。

 all of you know which companies you want to work for， how many of them use social media？

To talk about their work。The next game is coming out。

 I don't know which one's the hottest GTA6 I know is coming out at some point you know。

How many trailers are they putting out every week， right？Is GTS6 complete no， not even close。😮。

But did they put out a fantastic trailerer yeah and they generate a lot of buzz yeah so don dont be shy about putting yourself out there I know it may feel scary。

😊，But unless you do it。You're not going to gain what is out there。

 you're not going to get the eyeballs unless that's basically what will happen is only if you submit your resume。

 which is kind of like a black hole， you're not going to see any feedback。

 whereas if you talk about your project on social media，Of your choice。

 you know I'm not recommending any one of them， then you're going to get some eyeballs。

 I'll share it， I'll reweet it， other people retweet or share it on LinkedIn。

 you'll start getting more eyeballs， you'll start getting more questions， so it's really important。

Kind of covered this already。So here are a few examples of when that happened。

 so in 2018 Zard Liam and Henry did the first RTX project。😊，And in my opinion。

 I may be wrong about this， but I think this was the first DXR project in an academic classroom。

And they shared amazingly on Twitter and stuff and they got fantastic amount of buzz look at the amount of retweets and life and again these are students right they're not like Twitter celebrities or anything。

 but it it makes a difference you know you get a lot of in this case a lot of interest from Nvidia and others who are really working on this。

😊，And don't just share it on social media write a blog about it if you want to you know you have you read me but you can add to that using a blog so Henry wrote a fantastic three series blog here and then link it to your readme if you want to that gets you a lot of interest as well I can't tell you this and I've learned this through my career if there's like a superpower I would love to have it would be I'd be a better writer and writing will get you a long way in your careers。

嗯。Here here's another example， so this was also from Henry I think。

 where they were doing a final project on this flow simulation。😊，They tweeted it。😮。

And then the author of the paper， this person dragged。Or yeah。

He is the author of the paper and he is replying say， oh， this looks good， right？😊，嗯。

So so you get a lot of interest that way too， similarly this was also in the final project where they they ran into a problem。

 they weren't making progress， they emailed the guy because he replied on Twitter。😊，To be like， hey。

 I'm stuck， can you help me any help？😮，There's nothing surprising in that like 99% of all authors。

 if you're working on that project and you ask them for help， they will help you。

RightSo please do that。

![](img/0fffef76cafb255ef64c2303232fa23a_13.png)

Here's another one that Emily shared， I think this was from 2017。

 maybe on Twitter and again it got a lot of love there。And yeah， I got her job as well on that front。

嗯。Finally围。That's me。So here's my personal story of how I got here today。

I was in your seats and we were in more 212 downstairs back then。

 so I took the class in 2012 as you can see。And back then we did the past racingcing project。

I will not show you any screenshot because it's not as good as any what any of you will build data in the semester。

 but what Patrick did back then was he shared this tweet。

 he would make us write a blog and share it as a tweet。Okay， and 2012 social media。

 if you guys remember， not the same world it has now， it was much smaller。

But what it did was it got me who probably had maybe five followers at that point。

It got me a like or follow from a company called Aize back then。

And I was like who is this company trying to follow me a random student at Penn。

 went to their website so oh they're doing GPU libraries。

 okay that's interesting I'm looking for jobs oh let's go to their career page。

 I'll go to the career page and theyre hiring， I hit apply。Got a couple of interviews。

 got my first job。If this tweet didn't happen， I wouldn't have my first job。

 I don't know what I would be doing right I got my first job worked on Quda， OpenCL， Open GL。

Came back to this class and did guest lectures just like how D is going to do on Wednesday and my first guest lectures were on debugging and profiling because that's what I didn't learn in the classroom but I learned on the job when I joined the dreamname the company RAF。

So that's why I joined a learn on job， so I came back to give a guest lecture on how to do debugging and profiling。

That kept me in touch with Patrick， I joined Cium a few years later and now I am here。

if that chain of events starting from this tweet didn't happen， I wouldn't be here。Right。Again。

I can't emphasize to you how important this stuff is having a good read， having good charts。

 having good information in there。That will literally change。The step in your career。

 it may be a few hours of more work。But it can make a drastic you know。

Like it'll change the curve of your career trajectory almost。

So that's all I have to share for this part， any questions before I switch over to actually teaching you guys？

How many of you found this useful？Because I don't want to like if I do it next year I don't want it to be useless or something okay all right so so before you submit project2 look at this okay。

😊，And go tweet about project two afterwards if you want again it's it's you don't have to be anything spectacular right just be like。

 hey， I finished project two where I did stream compaction and I made it 100 times faster。😊。

That's good enough。No nobodybody's looking for a Pix level trailer from you， it's like hey。

 what are you doing in classroom， share that and you'll get a lot of interest in that。



![](img/0fffef76cafb255ef64c2303232fa23a_15.png)

可。Allright， so let's pause there。

![](img/0fffef76cafb255ef64c2303232fa23a_17.png)

And we're going to make sure the recording is working， yeah。All right。

 so let's talk about parallel algorithms。So we in the past few lectures。

 we've touched on a bunch of matrix math， we've touched on some SAXPY。

And all of those you can see are what we call on GPUs embarrassingly parallel。

 that there's some obvious parallelism that you can see as soon as you see it， you know。

 it can be made paralyzed and you do it。Here are some algorithms that on their face won't look parallel。

But with some minor tweaks you can make them parallel and gain a lot of performance so what they are designed to do is allow you to think differently in a way into how you can take any algorithm。

 almost any algorithm， put it on the GP and gain a lot of performance from it。



![](img/0fffef76cafb255ef64c2303232fa23a_19.png)

So we will start with parallel reduction， how many of you know what reduction means？Okay。

 I'm sure you know what the operation means， so we'll look at that。😊。

So parallel reduction is given an array of numbers。😊。

You want to have an algorithm that returns a result。

For example you do some of an array and you get the total sum as the result so you have n inputs and you get one output thats that's a reduction one of the things you want to think about as we go through these lectures is the arithmetic intensity that is。

How much compute are you doing how much real compute are you doing for how much memory access right so an example of this is lets take vector edition element wise vector edition。

You're reading two variables。Or two memory for each edition operation。

So that's like a issue for matrix multiplication。Kind of similar but now you have the dot product and stuff so there's a different arithmetic intensity there so one thing we look at repeatedly during this lecture is this arithmetic intensity how much computer are you doing for how much memory access。

ok。So parallel reduction， like I was saying is a parallel algorithm designed to take n inputs。

 give one output the operation。Is is an implementation detail almost which can be a sum a max a min average。

 anything like that， so the the bottom line of these algorithms is that。

The algorithm is the same all you're changing is one minor operation in one statement in your code。

Okay。So。Parael or regular reduction does the operation act commonly in serial， I would say， I mean。

 you can do some and multi threadd， but commonly in serial。Pel reduction， do it in pattern。

 hopefully on the GPU，So let's take a look at this。So if you want to find the sum of this。

Let's say on the CPU， how you're going to do it？What is the most common way of doing some finding the sum of this on the CPU？

Fol loop， yeah， you write for I equals0 i less than8 i plus plus。

Result equals result plus the next element。Right of an algorithm， that's the arithmetic intensity。

So let's look at how we would do this at pattern。Okay。You would say that before I jump into that。

 you would say that this is on the face of it a serial algorithm right you are adding one element。

 youre adding the next element and so on。😊，So let's see how to do it in Pa。First。😊。

You add multiple elements。In Palu。None of these are dependent on each other。

 you can run them in parallelable。What evening happens next？Yeah， Nick。

 you add them in parallel again， you add them in parallel again， maybe fewer elements。

 but you add them in parallel and so on。that this is like the foundation of how to change what you think might be a serial algorithm into a parallel algorithm。

😊，So this may look like a March Madness bracket， you know it may be slightly offset but it looks like a March Madness bracket。

 so what you get is N log n essentially you have n elements and you have login passes for those and elements that's the arithmetic complexity right now。

Y Nickick， in practice， would you actually want here the basic degree be2 you？

Do you want your base of your love to be。We actually add more than two。

So an arithmetic operation by default is two right so it doesn't matter if one thread is adding two or four or eight ultimately the that becomes an implementation that you can change at runtime。

What。Like I assume that there's some thread seekinging。

Stage here what happens like you don't need as many resources as the as you reduce。

 so what happens to those。We'll get to that in a little bit， but yeah。

 very good question and keep thinking about that。Other questions？Okay。All right。

 so let let's take a look at some pseudocode so in this lecture I'm not going to show you the full algorithm like I was doing with matrix multi and show you some pseudocode and then you can think about how it may look in implementation。

😊，So， the first thing for a parallel reduction so some terms here d is the depth okay so d is the depth to and then this is kind of the pseudocode here where you have for depth0 to depth log n minus1 and then。

The K is the number of iterations you need to do in each step and also gives you the strides so here you have in this past k it can be20246 and then this is the operation you're doing so that's pass number one。

嗯。Then you do pass number two and you update the values of D here。And that updates the values of k。

So now you can see that K is only zero to four in our range， of course this is。

Mified for the sake of slides， but it expands to any number of elements。

And then for the third death pass， now k can only be 0， so this is the addition it's performing。嗯。

And then note the。Note the plus equals in place so in this case what we this is an in place parallel reduction where it is modifying the array that you gave as input that itself is changing and the last element of that input is going to be a final result。

So any questions on parallel reductions？嗯。Seems obvious。😮，不 no。Okay。

 how many of you think this is optimized？What I just showed is optimized。No right。

 by now you we are third lecturer， Mike。音泉が。Thank about。我不老师。side。嗯哼，这。Yeah。So this is an in place。

 so what you're doing is literally in place you're modifying it and we'll see an example literally in the next section about why an in place addition can be useful as well。

But yeah， I think by now， you know， third lecture that I never show you the optimizer version first。

 this is an unoptimized version and we'll see how to optimize this later。

But any other questions on parallel reductions？Yeah， so I don't know for other country KIs。

 is it sufficient equation to like find the compute pipeline motor times and creating like memory barriers。

Guared that the previous。So I'll say this that I'm not an expert in graphics APIs。

 but most or at least when we go look at web GPU， for example， later in the semester。

 this should be pretty optimized。OpenG maybe not Wal can probably yes。

 so maybe depends on which API you're trying to use as well。Other questions？All right， so next。

 let's look at scan。 So how many of you may have done a scan algorithm again。

 it's totally fine if you have。不知道。All right， so scanner algorithm looks something like this。

 it's slightly different from a reduction。😊，Whereas scanner algorithm can also be called an all prefix sum。

Where what you are doing is something like this for an array of n elements。

 it look like this right a 0 a1 a2 a and so on， and you have some binary operator。

It doesn't matter if it's addition multiplication less than greater than。Doesn't matter。

What you are going to have is the identity I， so for example， multiplication has an identity 1。

 which means you multiply anything with I。It remains the same。For addition， there will be0。

For less than it will be。Positive infinity for greater than it will be negative infinity right so identity is anything that you do as a binary operation with any element should return the element itself so just remember that。

The output of a scan starts with an identity。Then the first element。

 then the boundary operation of the first two， then the boundary operation of the first three and so on。

 so with every increment you are doing the operation on all previous elements。Okay。

 so that's a scan reduction was you have an array， you get one element as output。A scan。

 the entire array is the output？So。Here's an example of this。You have this random array here。

This gets transformed to if he says it's an addition operation。Es identity is 0， so you start with 0。

 you copy the first element。Then the second element is addition of all elements before it。

 so3 and 1 is four。For the fourth element， addition of all previous elements， so7， one and  three。

 right and so on。Now， this obviously seems sequential if you think about how to program this on a CPU。

 you are thinking for I equals 0 i less 10 n。😊，Result or the element the next element is previous element plus the current element that is all you have to do you don't have to add n minus1 elements each time you are taking the previous result element。

😊，And adding the new element。So you may think it's O of n。Often sounds pretty good for this。

 it seems sequential and doesnt really seem like an obvious way to parallellyze this because it seems so sequential。

 you want to find the result of this element， you take 11 and add 4 that's just one binary operation per element。

😊，So how do you make this parallel？Yeah你讲真拿。So in this case。

 the array size remains the same and I'll get to it in this slide。😊，So there's two types of scans。

It's one is an exclusive scan where you exclude。The first element becomes identity。An inclusive scan。

 the first element is the same number as the first one。😊，So。It's if you compare it like this。嗯。

YouAll you have to do is。To go from inclusive to exclusive。

 you can do shift right or shift left and vice versa。嗯。DoesDoes this answer your question。

If you do it in the exclusive way you don't have the last one， that's true。How would you solve that？

入れちゃいま。我的。That's one way to do it， what could be another way？Nick， just like edge at CPU side。

InEach case it's CPU side， but that could be slow。We are doing eight elements here。

 but think of eight million elements。Yeah， but then this element is going to be on the GPU。😊。

So it's not a wrong answer， but if you are copying this to the CPU sure that works。

 how do you do the last one？You could potentially do the reduction。

On the GPU itself to copy that or you do always do inclusive scale and then you shift one as a shortaway so it's easier to go from inclusive to exclusive。

 but then the amount of compute you are going to do kind of remains the same。All right。

 any questions on scan itself the algorithm and the result we want Ly it？

This might be kind of so fun。Do you have any examples of like when this would be like useful to the moment。

 like let's say use some scan。Yeah， we'll see a couple of uses for it， the other use is for example。

 when you get through your path tracing project。Scan is used by stream compaction。

 which is project 2， and then stream compaction can be used in Pa so。

 so there are quite a few users off scan to understand the progression of data through an array。

And other question？That reminds me of like a Pascal's triangle to generate。Yeah， the Fibonacci， yeah。

 is there like some sort of。Give it here where you can build。

Something that would allow you to do this constant time or something I've never seen it done in constant time that would be extremely difficult。

 but I'm sure we can probably get close in this class yeah。Other questions on the algorithm itself。

All right， so let's see how to build this。So our goal here is。😊。

Design an algorithm and we will do an inclusive scan first， so design an algorithm for these inputs。

 how do we get that out？Okay。So on single credit。This is kind of what the algorithm looks like right so you start you don't have to start with j equals 0 because that is predone for you。

You start with k equals 1 k s 10 k plus plus and then like I said before all you are doing is for the next element you are doing the out plus the next element of n so n minus1 adds for length of3 n。

That's of an ads。Right。Anybody want to guess how many ads our parallel version will take before I've even shown you the parallel version。

Nextick， I'm going to guess log and loggan， okay。Other guesses？老牌。Log n minus1， okay。

 that's good guess。Anybody else want to try？All right， so let's get into it。So， no surprises here。

 but this looks kind of similar to reduction。😊，The difference here is going to be that all the elements are going to add。

😊，So the first element， right？In death equals 0 is the original array。Death equals 1。

 you are going to add two elements only。You are not going to add n elements just add two elements。

 that is depth 1， so you just adding element and the neighbor the next element okay。😊，In depth2。

You're going to add。That， but had an offset of two elements。So zero elements， one element offset。

 two element offsets in the next step。You're going to add。An offset of four elements。

Whathy does this work？😮，This is， this is the entire。

Enre depth of it we only need three depths why do you think this works shouldn't we have one that does smaller and smaller chunks here？

Yeah，Exactly because of in place addition， so let's take this final element here okay。😊。

Let's start here。This final element needs all of these elements to be added to it， right？Corrllect。

X7 for the result in the seventh element。Or the8 element。

 you need x 0 plus x1 plus x2 plus x all the way to xm。We get that。 So it may be。

Intuitive to think that you need seven depths。But let's take a look at how it's done。At d equals1。

 you are adding six and 7。Okay。At depth equals2， you are adding。😊，Five and seven。

 but look at five here， five is already four and five。😊，So in depth2， the seventh element is4， five。

 six， and 7。😊，In depth three。Now you need to add。We've already had to 4，56，7 now you need to add 01。

2，3，4，0，1，2，3。That 01 to 3 is already calculated in this third element here and if we look at this third element。

😊，2 and3 added。And then here it's adding one and  three， which already includes0 and 1。

So we have by the time we get to3 depths， x7 has all of them combined。

So this makes it really parallelent， so this one is an inclusive。

Where each thread does one sum and reads two values， so that's again the arithmetic compute。

In this case， the algorithmic compute intensity is N log n and we'll see how to optimize this a little bit。

Okay， so let's jump into the steps。So you have this array and in this case we will just take sequential elements。

You put0 first， you're copying the first element， then you are adding youre adding。Adding， adding。

So while I'm showing this units in sequential slides。Really， we can do it all in parallel。

 so that's step one。In the next step， you want to increment the depth and thus increment your pseudo code so that the offsets of k。

And D2 to the power d minus2 or 1， sorry are are set so。After d equals 1， that's your inplaceary。

A this is an example again， as I was showing off the last element where。After d equals1。

 this is kind of where you're at。For d equals 2， which is what the slide is。😮。

22 is the addition of 13 and9 because of those offsets。

 so by the time you get to 22 you already added  four， five， six and 7。So in parallel。

 that gives you the entire array updated at depth through。Now let's look at step3。

Now you're going to add this way with the offset being four， right？So you're going to do this offset。

So element4 adds0， element 5 adds 1 and so on。So again， looking at。Element7。

 this is kind of the visual representation of how we got that that element。

And then if you do it in parallel， you get all of those elements。So what do you think about this。

 any questions， what do you think of the performance on this？O可。He works。Like in terms of clothing。

In terms of floatinging point operation might be worse than sequential。For the right sizes。For the。

Because you're doing N log n。On the GPU for bigger sizes， this will still be faster。But yes。

 the bar will be higher， the amount of numbers you'll have to run through it will be higher。

Other thoughts on this or questions if you haven't completely understood。

 I'm more than happy to go over it again。Because next we are going to look at how to optimize this。

So if you don't understand this， I'll go over it again before I get into optimization。No questions。

 staying awfully quiet today， man？Common trend when parallelzizing an algorithm。

Fraed off of like doing more operations， but because it's in parallel。

Very good question I would say that generally to about GPU is not just parallel algorithms where。

Compute is kind of free。you have so much computer available that you don't have to think about doing an extra operation。

I mean， in reality， the fact that you do indexing is the extra operations。😊。

But they are so fast because all of them use registers that you don't really have to care about the overhead of that。

 what you have to care more about is the memory。😊，Side of it。 That's why arithmetic intensity is。

Important so that you reduce the number of steps。So that you'd reduce the number of memory genes。

That's what you're trying to optimize here。But yeah。

 doing doing additional compute can still result in a faster time than what a CPU can do。

Other questions on this。Should we switch over into optimizing？

And this is where you're really going to see how different you need to think of GPUs。Looking at this。

 does anybody have an idea of how？We might optimize this further。I'll tell you one thing。

 it's not about adding or removing steps。In fact， we may do more steps like Matt was suggesting。Okay。

 so let's take a look， this will be pretty unintuitive， but let's take a look first。😊。

This is kind of the graph of the different algorithms， right？In terms of total number of ads。

 the amount of arithmetic we are doing。😡，We are doing more。

 so sequences can be do of n like we saw in the simple fall loop。But in the ninth parallel algorithm。

 we are doing N log n。😊，Wwhich is more more than n。

 so compare off n is the blue line thats straight up diagonal whereas n log n。

Ihy isn't it on this chart， I don't know why analog log here isnt on this chart。

 but it's going to be higher， right？嗯。But on the compute side， right。

 how quickly the algorithm runss as a whole， this is where you get the performance improvement of n for sequential。

 but off log n for the GPU right on the knife fer scan。😊，That's faster。 So again。

 when we think of the break even point， which is this here， that's where。😊。

Sequent or parallel is faster than sequential。You still have a pretty good amount of sizes where the GPU won't be faster。

And then you add overhead of doing the memory copies and stuff like that。

 that's only going to increase this。So we want to make this faster。😊，Nick。

Ide for going faster not sure if this makes sense we can express like any number k as a sum of powers of two right like so if we just have like a separate buffer for like each like power of two like chunks in the array then like we can。

Like just some like one number from each of those buffers in order to get like every item in the scan。

对以。That won't give you a complete solution， but not a bad idea。

 and you'll see why not a bad idea really short soon。Okay， so， so there is some amount of。

Impprorovement we want to make。The question is how？

So we did reduction where we had N and we said okay。

 intuitively we can divide it into pairs of two and do multiple recursions of that。😊。

In scan we said okay let's add a bunch， let's do multiple recursions and okay we' will get the sum but how do we make it faster and this is where you have to think a little bit differently。

Please ask questions this next part。Is perhaps the most unintuitive thing that I'll teach you。Okay。

 please ask questions。Okay。So the next part is called work efficient parallel scan。😊，Okay。

The first thing to know about how to do work a parallel scan is to have this balanced binary tree。

Okay， which is a tree that has。I think the algorithmithmic definition is it has。

Lower equal or less less nodes on the left side than the right side。mIn our case。

 in this example we are just going to see eight elements or it'll be a full and complete tree and anywhere。

😊，The other key thing to remember is that。😊，We are still using an array。We're not changing to a tree。

We're going to think about it as a tree。Again， I told you it's going to be unintu。

Think about it as a tree so if you think of these eight elements really think of them as a tree here as this element is the root this element is you know leaf。

 this element is somewhere in the middle and so on。😊，Okay， so let let's start。

So it has depending on the array size， you will have log n levels and then each level will have two power d nodes again nothing。

Different from a balanced binary tree。We haven't started the algorithm here， okay？

To do work efficient patterns scan， we are going to do it in two steps。😊。

Not two steps as two iterations， two completely unique different steps。In the first step。

 which is called up sweepep。😊，We are going to do parallel reduction just like we've seen before。

 no change， okay？The next step will be called downstream。Okay， so again。

 right away so far we can see that， okay， this is new。

We are breaking an algorithm into two completely different phases。

That have nothing to do with each other。Or maybe there is a dependency， but in an algorithmic way。

 they have nothing to do with each other。😊，So again。

 this when you think about GPUs and parallel compute being。Novel and different。😮。

This is kind of what it gets through is how do you break up our algorithms to gain more performance？

All right。Let's look at upwe。Nothing new here it parallel reduction as we saw it before。

 we have an input array， its kind of upside down from the diagramm we had before。😊。

Where you're doing an in place reduction。And you get the final result 28。Okay。

The key thing to remember here is even though we are looking this looking at it as a tree。😊。

After in place reduction。Your array is actually going to look something like this， follow me， okay，0。

😊，1。2。6ix。4。Nine，6， 28。That's what your values in your array are。😡，After an in place reduction。

 if you want， I can scroll back all the way to the slide with the parallel deduction and you'll have that same data。

Okay。So。You have a tree， but think of the tree as an array。Any questions so far？Okay， yeah。

So the tree is。And this space is the array。嗯。Is eight elements long or is it？

All thoseSa elements wrong， yeah。So one way to think about this and again very counterintuitive。

 think of it as you're only storing the node and the node's left child。

 youre not storing the right child anywhere。Okay， so， for example， left child node。Left child node。

Left child， node。Left child node， so you're not stoning any right children in a way。

That's another way to think about this。Everybody get this。Okay， seeing if you had nones。All right。

Now we get into the really complicated part。😊，Or at least I've taught it enough that it's not complicated so so here's kind of the visual diagram of how that array looks so this is the in place array after an up sweepep。

Okay。Should I move on？有。是。这是我穿嗯哼。我就说。我说我的。I in this case the end terrible well we just。

 is I just there。三。But zero to7。然后你。Yeah，0 to seven now bad， yes。啊对他。I how。

So I'll frame your question a little bit different。Here we have in a array that's power of two。

That results in a balanced binary she。Your question is if I have an array of 5，247 elements。

How do we get a balanced boundary from that？Hello， just round the size to the next part to and a bunch of zero。

Exactly。Exactly， and Ill you correct yourself that what you do is you power up the amount of memory you have to the next power of two。

And then you fill the rest with identity and that identity depends on what operation you' are doing。

 but the rest is identity。😊，So that way you have， youll always do power of two operations。

 but they won't affect the end result。Other questions？But very， very good question。

 I usually address this later because nobody asked but great question。Any other questions on this？

Okay， up sweepep， parallel reduction。This is what we have right。

 like this is the output from the in place reduction。Or者。In dance sweep。😮。

This is called Traverse back down so up sweepep we kind of went up right we swept up and calculated the reduction now we are going to come back down to calculate the down sweep。

There's two rules or two rules with the second rule having two more subros， okay？

The first rule happens only once。😡，You set the root to  zero， which element is the root？

Whichhi element of this inplace array is the root？28， this is the root， right， that's the tree。

So you're going to set that to zero。The next step。😮，You' are going to do two operations at a time。

You can read it here。😮，But we'll get back to it， I'll have it written again。You're going to。

Pass the value to its left child， then you are going to do an addition。😮，On the。

On the value of the left child and its own value。Don't worry if you don't get that。

This is kind of the algorithm here。But more importantly， I think let's take a look at it visually。

All right。First up。Set the root to 0， so we are sending 28 to 0。Happens once。

 don't have to think about this ever again。Now here's the next part。

What you are going to do is copy the value to its left child。😮。

Then add the the left child and the value into that element again， all in place， right？

So what you are going to do is take the0。This array still exists。

 even though I'm showing you only two values， the array still exists。

So you are going to take zero copy to the left child。

Then you are going to take what was in the left child， store it in a temporary variable essentially。

😮，And the value and add and put it into that variable。Okay。

Let's take a look at the next step to get a little bit more sense of it。Here's what happens。

We'd start from the right again。Copy 6 represented by the orange arrow。

Then you add nine and six into 15。Okay。Similarly。You copy zero， then you add 0 and1 here。

How do we do we get one？The left child of six is one。Similarly， how do we get9 left child of0 is 9？

Again， array， but you have to think of it as a tree。Let's do one more。Here you have。Copy。Addd。Copy。

 add。Copy， add and copy add。So this is a rule based algorithm where all you are doing is for each iteration。

 you're computing the depth。Compututering the offsets based on the depth and doing two operations。

 one copy。The other one， an addition。Okay。Questions。

I'd be surprised if all of you understood this in the first try。

I've done a fantastic job of explaining or all of your timid to ask。I mean。

 no question other than just like why does this work， right？Yeah， I have a question about 1 night。

 so。デなは。9， Yeah，1 and 9。 we just copy it from。Right， so this array still exists at every depth。

The full array is there， I've just not copied it into each step。OkayBut we didn't do that additional。

てか？Right， so we are doing it here， right？Right， no， we are copying this exactly as is， yeah。

Other questions on this？你么。Its this。完。Then the other method or just like。That's a very good question。

 so let's save that for the next slide。Other question。

So this works because in every death level we know exactly。Which are B L element will get。

嗯你 don know我嘛啲快。Because every event element so the reason this works is because if we go back what a scan scan is making sure that you've added in our case edition。

 you've added all of the previous elements into into the current element， right？So part of that。😊。

Is being done by reduction。Okay。And then the remaining part is being done by the swap downstream so basically you are device separating instead of doing three itration for eight elements to power or log log n。

What you are doing is you are diving it up into two different phases。

 one parallel reduction and another one， this down sweep。😊。

And you're making sure that the same number of additions into each element are still happening。So。😊。

If let's think of the first element， right， first element is 0。😊，In an exclusive scan。

First element is zero， so identity essentially。How are we getting identity to be placed here？

Because it gets copied all the way left。Oops。Look at this red arrow， red arrow， red arrow。

That's why we are setting this replace with zero here。😡，这个对选。Yeah， exactly， yeah。

So you would replace with identity first。So。This element here。😮，The zero element，0th index element。

 again， a array， right？All you have to do is make this identity and the way to make this identity among this rule set is to make sure that the root is identity and it will copy it all the way left。

😊，The second element is identity。Plus whatever the element is。

And a reduction will place it correctly there。So all you have to do is copy that back down。

And so once you start propagating that， the combination of up sweepep。

 which is a parallel reduction and the down sweepep will make sure that you have a cardiac scan。Yeah。

But许军。Ling of an exercise。So in this case， we are doing an exclusive scan。😊，So， identity。

First element， what was the first element in our source0， so that's why we have two zeros。So we did。

Exclusive scan， how would we do inclusive scan？No， inclusive scan。

 you would need 28 at the end of it。Yeah， so I was like。No， no， you would shift the elements left。

 how would you get 28？You already have it from the reduction。So now。じ普提。

No you don't have to do that what I'm trying to say is you can take this and before you do the down sweep save this in a variable。

And then at the end of it， you'll do a left shift and just place it there。Other questions on this？

Was this un intuitivetu？Yeah。Does it work？😮，Yeah， it does。And。

So now Matt raise a good question right and again， if you have questions I'm more than happy to come back。

Matter raised a question。Is this faster and does it do more more steps， so upweep is off an ads。

Right。D sweep is off and adds and off swaps。Compared to what， compared to a knife version。

Which was N login。So we are doing3 o of n， which is algorithm O of n。😊。

So we are reducing the amount of work we do。The number of total additions we do is reduced。

 thats why it's called work efficient we are reducing the amount of additions we do。So。

 work efficient。What does that mean， it means less global memory reads。😡。

Which means better performance。So the way we are improving the scan algorithm。

I by reducing the amount of ads we do which reduces the amount of global memory and the more performance so if we go back to this line。

One more。If we go back to this slide。Number of ads often compared to en log n so n log n is worse right so in parallels can be had it worse。

Arithmetic complexity of n of n log n okay in compute we were fine。

 so in compute the parallel algorithms was scaling fine。

What we wanted to do was reduce this so that we reduce the amount of memory we are reading so now that we have O of n memory reads that reduces the amount of global memory usage and thus more performance。

Any questions on the stream scan， work efficient scan before we move on？Okay， all right。

So let's it's about 635， let's take a break and maybe come back at。643 or something like that。

 and then we will continue with a few more algorithms。😊，舒楚。然嗯。下对。个是什么是。我主播音乐啊。Yeah。有关点。喂。Okay。那我。

So if you want to figure out why it works。Do it on a piece of paper。And。As you are doing it。

 have a table where you are writing down which elements have been added。And at the end of it。

 you'll see that every column has the right elements added。俾食嚟肯定有。打。Cing of results。First。

Yeah that basically the left side has the least adss， the right side has the most ads。

 so that's how that's how you get to the result。そす。Based on the down。

It looks like there should be a longer somewhere is in some complexity。 that is the the amount of。

For bigger ray， the tree is going to be bigger， so you will have more steps in the down sweep。

 but compared to the overall algorithm， that's not the the log n for reduction is the same level。

 same log n for down sweepep。A， I don't know。啊，这次呢。of questions before。Yeah， so。Yeah， yeah， so。

We'll cover that in the Monday lecture。What's next on。 Yeah， we'll cover that in the Monday lecture。

Because D is doing the guest lecture on Wednesday， so I'll cover it in the Monday lecture。

 but it's a very good question because there are wasted threads and how do we optimize that as a very good question。

本人。H I'm here to say hello。呃，嗯 on你好好。苹工你喺里边里边。Thank you。All right， let's get started。啊，对。いくらい？

So as it happens every year。Students come to me in the break and ask， why does this work。

 nothing new？Always happens。Very， very average and common。

Average among exceptional studentss I should say that。 All right。

 The reason this works is if we go back all the way to。😊，Actually he put many slides to go back。

Basically the thing you have to remember about scan。😊，Is the fundamental nature of the algorithm。

 which is。At the n element， any element， at the end element。

 you are doing an operation on all previous elements。😊，Right？Some operation in our case。

 we are doing arithmetic addition， but it can be any other algorithm。😊。

The point is at any random element。You're doing some。Operation on all of its previous elements。

That' is a fundamental algorithm and that's the output we want。嗯。

So let's take a look at two elements。Okay。First， let's take a look at。Element 3。The fourth element。

 which has value 3。What is a scan arithmetic scan result？😮，For the for the fourth element。

It is0 plus 1 plus 2。Okay， so the value is3。And let's take a look at the fourth element。😮。

Or the fifth element。Which contains the value 4。What is the standards for that？

That is going to be 0 plus 1 plus 2 plus3， which is 6。Okay。

 let's keep those number two elements in mind。So once we do the reduction。😊。

This is kind of the array we are looking at。0ero，1，2， six， four，9，6 and 28。오케이。Now。

 let's take a look at what this is essentially doing is a partial sum。Right。

Element 4 has nothing added to it。😊，There' is no partial sum stored in this element now。

Whereas this element。😊，Does have a partial sum stored in it， what is that partial sum？

0 plus 1 plus 2 plus 3。It's stored in six in the fourth element。Okay。

0 plus 1 plus 2 plus 3 is the scan for which element。The next element， right？So。

 how do we get six which is stored in this element into the next element？😊，In a way that scales。

 so you can't just do a right shift in a way that scales。That's what these。

Albeit confusing and intuitivetuitive rules are doing， let's follow6。So we have six here。

We are adding it here to identity， right， so six remains。Then what are we doing？Copy。告py。😡。

So in a way， just think of this subre now， okay， this this subre。All we are doing is copy copy。

 so the fourth element is the left or the fifth element which contains the value4 is the leftmost child of this sub。

😊，This sub， so that is going to copy all the values left。So that's how。This6。

 which is the partial sum comes here。Now， maybe lets take a look at another element。

 lets take a look at the sixth element。The sixth element， which contains the value5 originally。

After parallel reduction。Contains the value 9。So it's a partial sum of four and 5 right9 is the partial sum of  four and 5。

What is the scan for the sixth element？Its all the values before， right。

 so 0 plus 1 plus 2 plus 3 plus 4， 10。At the end of our algorithm we want 10 to be scored stored in the sixth element lets see how we get there so we have nine currently stored but lets see how we get 10。

So。Again， we copy six all the way left。Okay， then we do a copy to the left element and then we do an addd4 and 6。

 so the6 from here is coming here。😊，From here is coming here， so this is the partial scan。😊，Of0，1。

2 and 3 is stored here， what do we need to add we need to add four so that gets added here。

So it's pretty。😊，like I said， an intuitive way of how you do a scan， but it works because。😊。

Paraallllel reduction does some of the partial sums。

And then the down sweep does the remaining partialsian sum。

That's why it works I was recommending to some students earlier。

Take this home and do it on a piece of paper， have the original array write down the partial sums above it and then as you are doing both the up sweepep and downstream you'll see that every element has been added in the partial sum or in the full sum at the end of it。

Does that make sense？Any other questions on scan before I move on？No。O。All right。

 so let's look at stream compaction next， which is Project two。I think this might be the only。

Algorithm that I teach as a lecture that is actually a homework。

 the rest of the algorithms are you know we teach the APIs and stuff and then you're implementing something。

 so let's take a look at stream compaction。So the goal of steam compaction。😊。

Is that you have an array of elements。Some of which you want to remove based on some condition。

 right？So if you have this element here。Or this array here。

And you want to remove all the red elements。For some reason。And you want to preserve the order。

 how do you do stream compaction so the result of this would look something like this。

Where you remove all the elements and you get a smaller ACDG。Okay렇。Again。Something like this。

Looks very serial， it looks very sequential is a green yes copy it is b green no dont copy is c green copy into the next element and so on looks pretty uns but how do you make it parallel。

嗯。So this this kind of algorithm is used actually in a bunch of places。Including Pa tracer。

 which you'll be doing as Project three。The reason is for something like this is essentially performance optimization。

Kind of what Matt asked earlier， you know， are there wasted threads in a path tracer？

You can have threads that don't hit anything and you want to exit early。

But in the next depth of the path tracer， you don't want to launch as many threads because not all the threads are active。

 so you can do a stream compaction， get rid of the threads that are not active and now you are launching a smaller number of threads。

Same with collision detection sparse matrix I think a fantastic example because you know if you have a changing matrix that has more or less zeros。

 it's going to change how sparse that matrix is so you can use stream compaction again for that。😊。

This can also reduce the amount of data you're transferring GP to CPU because if all you have to do is transfer the results in green。

 you are sending less memory over the PCIE， thus less time， so it improves performance。Okay。

Everybody understand the goal of stream compaction。Any questions？No， all right。

 let's take a look at how to implement。So this this is going to be generally intuitive。

 unlike work efficient panel scans， but still please ask questions if you want。😊，So。

 the first thing we are going to do is compute temporary array containing1 and zeros。

 one if it meets the criteria zero if it is not， okay so all the greens，1， all the reds are 0， right？

I'm showing it to you as sequential， but again， completely parallel， right？That's first step。Step 2。

T an exclusive scan。😊，On that early。Okay so on this array here。

 this not on the source because the source can then be of any type。

 like I was saying for pass st so it can be rays which are active。

But this array here is going to be Boolean or if you want an inte right so you are going to have that and you can run as exclusive scan。

😊，What would be the first element of an exclusive scan in this case？

0ero right or false so you're going to have that， then the next result will be。One， okay， and so on。

So this runs in Pa， again， we've covered scan， we've covered a work efficient panel scan if you run an exclusive scan。

😊，You get this result here。What do you think this result says？Nick。

 what index are we agreed to away from this。What index what index should you write to Yeah that is one one pretty good guess。

Any other guesses？It's pretty close， but not exactly Matt。

 of an array you need to write how big of an array you need to write to。佢。Each carries like one。这个问题。

Right。Exactly， so。Yeah， so this array represents how many true values you have before that present element。

So， how many true values do we have before the element0 because there is none。

 how many true values do we have before the element 1 a？😊。

How many true values before this still1 a and so on， how many true values before the last element4？

Right so you get four elements here so it this array is counting how many true values do you have before that element？

Which can help with where you write the next result as well。All right。

So what you do next is you use the value of this scan result to compute your index。😮，So。

A scandals on 0， write a。😮，Okay。B， this is false， so you skip。Okay。

 so we are never going to write falses， right， so you skip false。C。True index1， right to c。D1。

Which is true， so you want to include it element 2， so right to element 2。And so on。

And that is your result the final number here gives you also gives you the length of the array itself that you need。

😊，嗯。The other thing， even though I showed it sequentially， again， this is completely in parallel。

 each element can run completely parallel and there's no dependency on other elements。

Because the indices are coming from the scan。So。You have the source。😮。

The bulloleions are a parallel algorithm。There is no dependency its an element wise operation。

 scan is a parallel algorithm and scatter is a parallel algorithm。So you can do a stream compaction。

Completely in parallel。Any questions here so you see how we are building upon existing algorithms to do new work。

A stream compaction， like I was saying， can be used in pass tracing can be used in spa matrices。

But it builds on these fundamental algorithms。A stream compaction uses element wise operations that we covered in the first lecture。

It uses a scan which we are covering today and a scan， especially a work efficient pal scan。

 uses reductions。😊，And it uses downstream， so you're kind of combining these different algorithms to build new algorithms that also run in parallel。

😊，Let me pause there and take any questions。嗯。The呢？So。

The reason we're like we're doing all this stuff is so that。

Go to this scan main leader so that we can get the size of the final array。

You can get the size of the finalry as well as the inds where you want to write。

Because if you don't have this， how do you check which how so if you don't have the scan result right imagine it is not there。

 how do you know which element D gets written to？The only way to do that is by counting。😊。

How many elements before it， A and C， right？And that's what scan is doing here。

 it's doing a scan on the Booles。😮，To calculate how many true values before that element so that you know which element to write that element into。

So it's kind of like， how do you break apart a serial operation into parallel components that then do everything in parallel？

Yeah。So， instead。You。Yeah， so so when you do the scatter， you are using three buffers。

 you are using the input。😊，You' are using the boion to test if you should even write it。😮。

And then if you should write it， you are using the scan result to find the index on which you should write。

So again， you're using more memory。😊，Right。But you're doing it faster because everything is in parallel here。

Yeah。他的。不说。Yeah， you can launch these many number of threads。

Or you can launch all the threads because computer is free and then just return early from the values that of false。

Other questions？Everybody gets stream compaction again， this is homework。

 so this is what you should be asking me about。😊，All right， should I move on？Okay。All right。

 next one is some data tables。So， somed tables are 2D and they are generally used in like in mostly image filtering and stuff where you kind of calculate different filters from that so heres an example of it so let's say you have a 2D array your subd table is all the elements that come before it。

😊，And I will pause here and take a diversion and say all of these formatting things that you see including what happened in the previous class I went back and looked at all the slides the slides are great。

 I don't know why everything is messed up here so so I don't know I need to figure that out but in the slides if you take a look at it on your laptops all of these are fine。

😊，This one's in your slides okay， but definitely in the last class everything was like super weird。

 but the slides were okay。😊，All right so back here so for this element here what you are going to do is calculate a sum of all the previous elements from that okay so9 is going to do you know this three by3 matrix here okay。

😊，So the benefit of using this is basically calculating like filters and stuff in every pixel and because you do it in parallel。

 you can do it in constant time essentially。😊，So some example users of this in graphics are like this depth of field of glossy and reflection algorithms that you can end up doing in image space。

嗯。Questions on this before we actually look at how to do it algorithmally。No。Okay。All right。

 so let's take a look。So， let's say we have an input image， let us look at the output first。

 so what will this first element have here？What's the sumday table value of the first element？Yeah。

Just one first first element， nothing before it it going to be on， what about the next element？

That's going to be true。Right， next element。Two next element。4our。That's going to be cool。

Next element。Three or no five， sorry， because you're adding the square。Next element。6ix。And then six。

 oh， sorry， this two gets counted eight。So， and then you populate the whole thing， you get 12 there。

 and then you are going to add。0，0 and 2， and you get 14。Okay， so again。

This this seems kind of like sequential， but also could be done in parallel。

 so how would we implement this on the GPU？Of the algorithms we've done so far。

 which one makes most sense to use on the GPU for some data tables。Scan withcan。嗯。看了。嗯。

And why do you do inclusive？Because the first。Exactly。

 you do an inclusive scan because the first element is inclusive if your sub tables was all the elements before excluding that element then you could do an exclusive scan but right here we are doing an inclusive scan okay so let's take a look。

😊，So。To do this in parallel， we will do it in two steps。First。

 we'll do an inclusive scan for each row。1102 that is going to give you a result。

 no change there okay。The second row， 1，3，3，4 now， what does this represent， 1，3，3，4？

It's a partial sumday table。For this role。Lets take for this element4。

 which elements do we need to add？We need to add all of these second row。

And we need to add all of these second row， first row， right？The second row is added。

In the next step we will see how to add this so first we will do what row wise in the scan。

What do you think we do next？Columnwise， right so now。Let's take this element again。

 what did we need to add here， we needed to add the sum of the full first row。

And that is already stored here， so now as we do a columnize inclus a scan that gets added。

So we've taken again what looked like。😊，A chaish sequential algorithm in 2D。

And using two inclusive scans， which can run in parallel。

We have converted into a fully parallel algorithm。Any questions on this？No questions， easy enough。

Again， you see how it builds upon each other right you are taking fundamental algorithms and doing something new with it。

😊，Let's look at red sort， which is completely different from everything we've seen so far。

 everything we've seen so far is binary operations that have some element wise component to them。

R exc is completely different， there is no arithmetic here， its all compare and swap， right？😊。

So how do we do swapping on the GPU？The way redix sort works。😮，Is that it's efficient for。

Small number of sort keys， so if you have a K bit number。You need K passes。Okay。嗯。

So the way it works is you have。You start with the least significant bit。

And then you go to the most significant bit， so in our example here there's four bits。

You start with the right and then you do four passes moving one towards the left。오케이。

So let's take a look at an example。This is an unsortted or randomized。

A of values0 to 7 right we have and correct me if I'm wrong here，4，7。Three or two。Oh。6ix。3。F。

 one and zero。Okay케。Now we need to sort this。And we'll use Raic sort in parallel to do that。Okay。😊。

Again， this algorithm will be completely different to everything we've seen so far。In the first step。

 you take the least significant bit。And。You move it to the other side。Okay。So。

Look at all the bolded values。We're moving those to the left。😮，We' are moving the ones to the right。

Now I'll call one thing out here。In my example， I've used the value 0 to 7。😊。

Which means there's equal number of values with ones on the left and ones on the right。

 so it's divided in half。Doesn't mean that's true for every array。

So this this dotted line here may not be right down the middle。It can be one way to left or right。

 which is not a problem。all you have to do is if you are looking at an element that has0 bit at the end。

😊，Move it to the left hand side， if you are a one bit， move it to the right hand side。Okay。

Second step。Do the same thing。Except use the middle bit。If it's 0， if the middle bit is 0。

 move it to the left。😊，If the middle bit is right， it the middle bit is 1， move it to the right。😡。

Make sure of the order okay you don't want to be randomly placing things left right make sure of the order。

 but regardless of the what the first part。What the least significant bit was move the middle bit accordingly okay。

So， for example。😊，The least significant bit here is0， but now this number is on the right。

Because the middleter bit。Is one。Okay。Next。Do the same thing again。

Except for the most significant bit。Now you move it to the right。

So now if you see all the zeros are on the left for the most significant bit。

 all the ones are on the right。But what do you also see？This is a saed array。What。

I feel like maybe I'm missing some implicit thing that's going on here， like I'm just looking at00，0。

When it gets shuffled over to the leftage time。Or at least in the first step。

 it happens to be to the right of like 010 and 110。

Is that because of something sorted in that first Yeah so the reason this works。

And the reason we do it least significant bit to more significant bit is because the most significant bit has the biggest impact on the size of the number and the magnitude of the number right so that's why that happens last if you did this first。

You wouldn't have the right order。So you do the least significant bit first so that among two values that may be neighboring。

😮，You're sorting them。Then as you do the next significant bit。

 you're sorting those and then the most significant bit where you actually change the whole value。

So that's why this works， it's completely okay that in the partialian step。That they're unsorted。

 what you want to think about is the combination。😡，Of the sorted bits。😮，Is ordereded， so for example。

Let's take this step。Okay。嗯。Actually， I'll go to the previous slide so that it's more obvious。

Let's look at this。And only look at the two least significant bits。

 the middle bit and the least significant bit。😡，What do you see，0，0？0，0，0，1，0，1，1，0，1，0，1，1，1，1。

Among those two bits。It is a salted array。Right。And then when you sort the third bit。

 the most significant bit， the entire array is sorted。So that's how Raic sort works， even on the CPU。

 that's how Radix sort works， except that here we can do it in parallel。Yeahep。好通す。Yes。I was。

Can you repeat， I don't hear your entire question if you don't mind us。I think为是毛。So。

Yeah so in an array you are going to I mean Ra sort only works on integer so that that's one part of it and if you whether you use integers or half or long it doesn't matter to this algorithm because the number of passes depends on the size of the type。

Not on whether you're padding zero， three， zeros or four zeros or anything。That much。This。不是。So。

 so in this is your question whether we are sorting only three bits or is your question like。

0For a 32 bit inte， we would have 32 passes。With 32 yeah， so for a 32 bit in Dja。

 we would have 32 passes doing this。没有。But it would still be faster because it's all parallel。Yeah。

So， for。Yes so there is。And so。The laws process。Yes。でこな。啊知是。不的。You have to， yes。

Theres so many causes。嗯。Not on the GPU。On the GPU this operation is really fast。

 so you don't have to worry too much about that because everything will run in parallel so even if you have millions of elements of 302 bit each。

 this will run really really fast。Yeah， how that second there。secondYeah。First second how would you。

Know that you're putting like。There's 101 into the fifth spot and like 110 into the sixth spot right so that's something I didn't cover here but you could use the same thing like we did in the scatter operation。

 you could use that here by running an exclusive scan and counting it in two different ways。So。

 you could。You could run an exclusive scan for zeros and an exclusive scan for ones。

And the number of the final result of exclusive scan for0 will give you the offset for all the ones。

And that's where you start the ones and then you can use the exclusive scan array。For all of that。

 and I think I may have slides for that once。Yeah， I do have slides so that I can cover it。

 but lets let's see the if you have questions more on the core of the algorithm itself。

 how to implement it on the GPR show。 kind of fighting missed this question。

 but how do we determine how much to the right？Yeah， so I'll cover that in a couple of slides。

Other questions on the core of this algorithm themselves。

 just understanding how these things are moving。Okay， all right， so let's see the implementation。😊。

All right， so here's kind of the steps。😊，The first thing would be to break the input into tiles and here we are going to consider a very large input where that spans multiple blocks and you know across SMs and stuff。

You want to sort each tile into that raic sort。😮，And then you want to sort the whole thing using byomic panel merge。

So。Looking at the sorting。You want to sort within the tile first。

And the parallelism in that is all in between the。Passes on each sequence， okay。嗯。So like we said。

 between the passes， no parallelism， right you have to complete。

Lease significant bit before you step to the next bit and so on。

 but within each pass we can parallelze it。There is something we need to solve about which index we need to write something in because the order is important like we were seeing with the arrows。

 the order is important。So how do we parallelize that？

So here's kind of how and this kind of relates back to stream compaction and scatter， okay？

So here's the input area。Okay。And this is for each pass， okay， at each bed。So for array B。

You want to store true or false。😮，Or straight up the bit。For the bit n。

 so in the first part that will be the least significant bit so that is what we are stored here01。

0ero， zero， one，1，1， and zero。Right so only store the least significant bit。The arbitrary。

With the false keys before the two keys looks something like this。

 so this is again what we were seeing in the previous slides with all the zeros first and all the ones and order is preserved。

So how do we compute where things move， what is a swap？Without knowing。

or without assuming that there equal zeros or equal ones right that there is no guarantee of that。

So here's how we do it。So we have the inputary， the IRA。Then we have the bits array。

 the B right so on each pass this is the least significant bit。

 then we will do the next bit and so on。Then let's compute the E， which is not B。😮。

I'm keeping it here in a GPU you may or may not decide to store that it's up to you you can calculate it。

 like I said， computer is free， right？But here let's have this era， which is not B。Then for the FE。

 we are going to do an exclusive scan again， I said it is similar to stream compaction， right？😊。

Do an exclusive stand for the FRA， what do you think this F array does？Again。

 think of stream compaction and you'll know the answer。W wants 선생님。

How many entries before that cell have taken the bit？呃。自己后的。Exactly。

 it tells you how many zero bits there are before this element。😊，Look at this 333，3， why？

Because none of these have zeros in them。They're all ones now and so on。So that's F3。

What this also gives you is the total number of falses。

 so it kind of gives you that dividing line where the true value should start。Okay。

 no assumption that half and half it do the exclusive scan and that will give you the total number of falses。

Okay？Any questions so far？一系啊呢度呢断啲。Not the。If you do it on this， if you do it on B。

 what do you think you get？You'll get a number of ones。We don't need that right away。

We need the indexes for zeros as well。You could do it the reverse way you could do。😊，You could do B。

 you could do the exclusive cannon B， which is kind of the next step。So， the T value。

So we will introduce a new theory， which is kind of like this。I。RightSo IRA。Mine or index， sorry。

 not diary index T or I。Equals i minus f of I plus total number of falses。

 so the total number of falses gives you how many ones there are right？

So T of I gives you the index on which any value should be written。Okay， so let's calculate that。

So for index0。So， I equals 0。Iイ0。Minus f of I， which is0 so 0。Plus total number of falses。

 so the value here would be four。Okay。Let's do one。I is 1 minus f ofhi1。Which is  zero？

And the value will be4 for that as well。Now， this value。Is。2， because the index is 22 minus f of I 1。

Class total faults is  four。So you'll get that and so on。So， the T array。😊，Gives you。

The index of the1 values， the zero values you get from this。From the effortity。

The index where zeros should be written you get from FRA。

 the indices where one should be written you get from the T array， so that is why falses true。

That's why we call them the FRA and the TRA。Now， your final result is。😮，B， data。Equals b of I。

 is it0 or 1？If it's b of I。D the index is T of I or F of I。So this is0， index is0。

 so B of I is false。So F we choose f of P， which is 0， so we like 0。One is true。

 so we use the T array， one is true， we use the T array， so we write 4 here。This is false。

 we use the F， we write one here and so on note how we are not using。bititier。Okay。

 you could do that， but here Im just using this directly， which is the final indices。Of this area。

 again， you want to think it parallel， right？We are not writing the data these are in this case these are inds。

Then we take the IRA and the D， and then that becomes the output。

The slight confusing thing here is because we have0 to7 in the values and 0 to 7 in the indices。

 which might be slightly confusing， but ultimately the D。

Could be calculated you could calculate without this without this without this and without this in a compute way but to explain it as a step by step algorithm on these slides those are all helpful to have so the final step you do is you take。

😊，I output equals。The I at index T， so you kind of mix that up。So any questions on this？

On how we do ra sort on the GPU and this remember so far what we what I've shown is。1 per。

Bit so you repeat this n number of times for n bits。Second is within a block。

RightThis algorithm so far only works within a block， you can't scale this across blocks。

Because there's no communication across blocks for synchronization。

So all of this runs n times within a block， you can use shared memory。

 you can put sync threadreads and run it n number of times and you will have a sorted block。

Any questions on this？그냥。Yes so。The theory is an exclusive scan。😊，On the total number of true bits。

So b is the total number of false bits or well。Is the BRA is the bits array？The T array is。

How many truths you have？At a certain element plus the FRA。Right， so if I go back here。

So heres the formula for the TRA T or I。Is the index itself minus how many falses you had before that element？

Right？And then you add the total number of falses， so it's kind of giving you the offset。

For each element。Of what the final result what the index in the final result is。

So remember how you want to move all the ones to the right。And you want to maintain order。

 you do that by creating this theory。And this is a constant for all the elements in the T because the total number of falses is how many zeros you have so you can have。

X number of zeros， it doesn't matter， this offset will make sure that all the ones come after that。

HelloSo this formula seems to that here。Depenent on yes。Do exclusive。On scan on BRA and then on F。

 like because theyre not。Depenent thought very much。 And then we just。

The final destination is to sleep。对。The excuse kind of be plus some constant that we compute after。

So。So walk me through that again， I didn't completely follow Yeah B and E can be computed in pattern。

What I'm saying is that。要にちか。呃， after。Why don't we just compute？

The T of I to exclusives can of be without the total horses so that we don't rely on that。

So Ill do you one better you don't need the TRA at all。

You can just replace this T of I value as a formula of FF。So you don't even need to do that。

So you can just take this formula here。Which is constant。And just plug it into this T of I。

So you dont， Im showing here so that there is a flow in the slides。

 but when you actually implement it you don't need to store t， you don't need to store E either。我的。

Yeah， good。Other questions on this？Okay。Let's。So I said that this works within a block right so how do we scale this across blocks？

So。嗯。To， to merge。That ties into a final sorted array。You have to do a bionic merth sort。

That can be on the CPU or it can be on the GPU depending on the size of your array。

 but once you have it within a block， let's say 10 24 elements per block。

 then you can pretty quickly scale that up in terms of performance by doing a byonic me sort which I won't teach here because it defeats the purpose of。

Telling you how to think of these algorithms， but you can explore it online in different resources as well。

嗯。What I will tell you is。How to do scan across multiple blocks again。

 most of these algorithms we covered today。Were around how do you do it within a block？So。

The question is how do you scale it up across multiple blockss one question was asked earlier。

 what if you have not power of two elements， how do you do that？

The answer to that part is you pad it with identity and that way you have powers of two elements of memory at all times。

If you have multiple blocks， here's kind of how you do it。

And here I'm making a small number of blocks， but you can see how it scales。

So you have the input array， you are going to divide it into a certain set of blocks right。

 you have n threads doing work for n elements。Okay， pretty common so far。

The first step is to run scan。On within a block。 So here you see。You're doing。0，1。

3 on the first block。On block1， we are doing 3712 notice how we are not adding anything from block0。

 we are starting with  three as the first element and then we are adding it up。Same thing for block2。

 start with 6， 6 plus 713， 67821。So you're doing a partial scan within each block。Okay。

Any questions on this so far？No right， the one thing I'll call out。😊。

Remember how in up sweepep and down sweepep we were talking about？

The scan of any element is all the elements before it， so for example。4。For the scan of 4。

 you have to add 0，1，2， and 3， right？It doesn't matter how you get there。

 the end result should have 0， one，2， and 3 added。So in over here。

What we are going to see is that we have computed partial sums within a block。

But we haven't added the previous block to it。😡，What do you think the next step is？blocks sorry。

blocks merging your blocks， but that that won't necessarily create parallelism。난요？Exactly。

 so look at this for this value here， the scan is the whole of the previous block， right？😊。

All you need to do is add this。So you take all of the final results of each scan。😊。

Store it into a new temporary area。Again， can all be done in parallel。

 you know how many blocks you are launching。createreate a memory of that many elements and then copy each one of them in parallel。

Okay。Next。Do a scan on that。Because if you think about it here。Sure， you can add three to this block。

 but for block6 or this block tool， you need the sum of this and this block。😮。

So now you need to do a scan of the partial sums。So you are going to do this stand here。

And that's an exclusive scan， right？能。What you're going to do is。

You get blocklo sums from the original scan。Do a partial scan on that and then you are going to add it back so the first block is going to get zero because you don't need to add anything to it。

The next block， you' are going to get three from here at threes。

The next block you are going to get 15 at 15， the next block you are going to get 36 add 36 to it。

So now you have a scan that cans for any size。All done in parallel， so you may have multiple steps。

 but all done in parallel。Okay。And any questions on this？This applies to reduction。

 it applies to radix or it can apply to anything when you are breaking it up like this。

 you essentially allow it to scale across multiple blocks。

 you just have to figure out what are the elements that you need to add and control across multiple blocks。

What。Wash increments。我的。So。If we think about block three。

We' have computed the partial scan within block 3， right？But what is the。

We need to add to block each element of block 3。😡，All of the previous elements that have come， right？

How do we get all of the previous elements that have come？We get the sum in block 2。

 we get the sum in block 3， we get the sum in block 0。And then we added。

 so 3 plus 12 plus 21 equals 36。So now we have 36 which should be added to each of these elements。So。

 again it' is all about how do you make sure that every element of all the previous elements is being added to that element here in block 3 weve done the partial sum now we need to make sure that all the elements from block01 to 1 and2 are added to all the elements of block 3。

啊，那个。But is it possible that before you add the increment data？That you might actually have。

Another scan that like break， break it up into。Yes， recursion， right， so for example。😊。

Let's say you have。I'm going to say two million elements。Roughly okay。

 so 2 million elements and let's say you have 1024 threads for block， how many blocks is that？

That's 202048 blocks right 28 48 blocks you can't run in one block， you need two blocks。

So you do another scan on that， so depending on the size of your array。

 you may do this multiple times， yes。😊，Other questions？哪里？All right。This I kind of already discussed。

 so I won't go into more detail。嗯所以啊。Pael algorithms for GPUs are all about thinking out of the box。

Thinking about how like you really have to think at the advent of general purpose GPU。

I should really know the name of the researcher who invented work efficientff parallels scan。

 but I don't remember， somebody went and thought， how do I break this up？

And that's what GPU programming is all about， how do you break up what are generally counterintuitive examples of performance gains and then gain performance from that。

Same applies for spa matrices， same applies for matrix multiplication。

 you have to think about how are you going to break up any given algorithm to extract maximum performance from it。

嗯。So that's the end of the lecture。I wanted to do some。

Inside debugging and show like some general overview of that inside debugging inside compute。

Would you guys stick around for maybe 10 to 15 minutes and we can do that and then that'll help you both for project two as well as for Dee's guest lecture on Wednesday。



![](img/0fffef76cafb255ef64c2303232fa23a_21.png)

Okay。All right。

![](img/0fffef76cafb255ef64c2303232fa23a_23.png)

All right， so here I have。😊，I call this the performance lab and we'll take a look at it a little later in the semester。

 but I'm going to use that code， the solution for that code from last year to show you how to do debugging so in the performance lab we do basically the goal is how do you take something that's a super naive algorithm and make it super fast。

I generally like to make it a quiz。Like a fun quiz when I do the lecture。

 so I'm trying how to do this in a way that doesn't give away all the performance， but let's see。

 let's do a reduction， set a start a project。嗯。Okay。

 so I walk you through the code a little bit here we are doing 32 million elements and I'm going to use thread block size of 256 threads each。

Using a 1D block and I think there was a question on how to do kDa check error and things like that so this is kind of a macro on that basically kud error you run the call and then if it's an error you do a printf so again just these are all helper things that you can use in your projects Dev just make sure that the block size is greater print results is a helper function again。

Po process kind of throws the error I will reduce CPU to calculate the CPU result。

 and then I have a bunch of reduction stages here。All right， so let's do reduction stage zero。

 which is kind of what we did today， that's reduction stage zero it's the naive reduction algorithm I'm going to put a big point here I have debug。

And then I'm going to say in， start kuda debugging。

And please ask questions out of curiosity about how do I get here， how do I get there， and so on？嗯。

All right， so we we've hit the breakpoint here inside a kernel。

Right you could potentially have a breakboard outside the kernel and then you'll hit this as well。

 I just didn't have one outside the kernel。嗯。The first thing you'll notice is that our auto variables are already populated。

 that's a great thing about Insight， especially on visualual Studio that it gives you all of these auto populated variables that you' are using in it。

 so Bdm， threaddm IDX which is not calculated DX， so all of that is there。

We're going to step over and you will see that index is calculated n is basically 32 million elements in powers of two。

嗯。All right。I'm going to step down。If IDx has an n true so Im going to step down again now we hit a sync threads。

 what is sync threads it iss a barrier， it will make sure that nothing moves as long as all the threads have not hit this。

 right？So before I do the next step， I want to open one of these windows。And I'll go to Warpenfo。

How many threads are in a warp？3리도。So this is my Warp view。And I'm sorry if not all of it is visible。

 I'll try to zoom in in a second。So for 32 million elements right so let me open a calculator。

So I have 32 times 1024 times 1024 right so that many elements which you can see in the os it's not there in the os but I'm going to divide that by 256 thats the number of blocks I have。

And if I。In a 256 thread block， you have 8 W， right so。I'm going to multiply that by 8。

So that's1 million wps is what I have， I mean they're all not going to show here。

 but they're all here。The thing to remember from this work view is that is to see these green things。

These are your threads。A。32 threads in each warp。Right。

 so these individual green things here is one thread。This value you here this thread。

Is the starting index of that warp so x equals 0 y equals0 z equals 0 the next warp starts at x equals 32 right because warp 0 is 0 to 31 and so on。

The CTA is essentially the block。So as you can see， the first eight here all have zeros。

So block zero。The next eight have block one。And see how the thread values repeat。Okay， so again。

 you can explore this more on your own time。I'll show you something cool here。

 Im going to click this value okay at this green and I'm going to double click it。And boom。

Look at this index 4。So I'm trying to move this。Index 4， y 0 z0。

 so by double clicking this thread I've moved the debugger execution to that point。Okay。I couldnt。

Click it in another warp if I wanted to， so I'm going to click it， let's say here。嗯。

It didn't go to sink threads。The previous warp。😮，Again。

 because all threads execute at the same time within a war。

 that previous thread was on sync threads already。😊，This thread wasn't。

 this thread never got to sync threads， it's still at the initial breakpoint。

Right so let me do what I did before I'm going to step over。All right。

Look at the IDX at 74 so it's in this block and if you count that I'm on the 10th index of War3 and thus it's 74。

I want to hit the sync threads and then I'll click another thread in that way more。All right。

 so now I'm going to hit this in。And because they are all executing in lockstep。

 this thread would also be at the same threads。Okay。嗯。Again。

 so what you can do is you can go to any warp here visually double click it and you'll get all the debugger values for that warp。

嗯。You can also filter here， I don't use it very often but you can。

 so you can use a search filter to get to a specific thread and block if you wanted to。

I'm going to close this swap info and then go to board Watch。So this watch variable or window。

Is like a debugger window for all the values。Except its limit to a ver so I can add。IDX。I can add。啊就。

I can add thread。Idx。look at how it's populating everything accordingly。

 so you can fill it with all the values you need to so that you don't have to just track one thread like the autos or the watch window here will show you。

 you can track all the threads in that warp。嗯。Let' us look at on the window。

 the lanes window is kind of the within the wart view。😊。

And it shows something like this and remember how I was talking about active threads and inactive threads in the previous class here you will see all the active threads here as well。

嗯。All right， let's look at the next window， which are the resources。 Okay。

 so there is an interesting one this。Is across your execution so you remember how in the previous class I was talking about resources and how many registers you have and how much shared memory you have that's what you're going to get from this this window here so on my GPU for example。

 if I search shared。Memory。😊，I'm going to get shared memory per block for me it's 48 kilobytes。

 you may have something completely different， but you can query these things in a program to make it optimized better。

嗯。Then you have a bunch of dropdowns here， which you can also check out the one I'll show you is Kuda kernels and sees。

See how I have different kernels here， so I have if I show you I have reduced stage  zero。

 reduced stage1， and so on which are different levels of optimization。

And you can see all the kernels here and these kernel id would be the same as what you see in inside compute。

You can look at different memory allocations， so all the kuda men copy you do you'll see that。

Host memory allocations so if you do like pin memory。

 you can see all of those here and then you can jump to those pointers and see the memory for that as well。

嗯。Let's see so again explore all of this more on your own time and try to give you a tidbit project2 is great for exploring the debugger because there's no visual element to it it's all numbers so you can try that out。

I've close this。And then， you can look at。If any of you are interested in assembly language？

You can look at all the PTx stuff， so PTx is co as assembly or intermediate language essentially。嗯。

Any questions on the sofa， Mike？Any。哦。I是。I'll fill it up great。Yes。How filled up it might be。

 I don't know。But you can definitely let me delete this break point here。

And let's put a big point here。So I'm going to hit continue。Because here well write to shared memory。

 right so I'm waiting for the breakpoint。So now。Again。

 let's open our board watch and then we are going to add。Sm。

But it wont give up it won't fill it up because we haven't give it an index， so let's do。s。

Thread IDX dot X。And now you'll get that filled up。So yes， there is a way to view it。

 you just have to make sure that you're adding it to your watch windows。嗯。그吃样对。

There used to be more windows and stuff that you could see， but this is。

 I think what insight shows so far。Any questions on this or anything else you want to do one of the things I didn't show sorry Matt one second is you could add a condition here。

And say， I want to hit this thread。In terms of let's say scrolling down on the wars and stuff you can say I want block IDX equals 128 and then thread ID equals 132 and it'll take you to that thread as well so you can add conditional breakpoints Matt。

I just wanted to call out that。I found that。嗯。In order doesn't seem to work very with GLM。

Ps like a known。Yes but there are ways around it， I think if you ask the specific thing that you're trying to do in that discussion I'm sure we can tell you how to get around there。

 basically like how you're seeing thread IDX like if I just like thread IDX in this War pinfo or no not not War pin for War watch window。

嗯。You see how thread IDX populates it as astruct？It doesn't always do it for GLM type。

But there's a way to dereence that and get at least single values so you can add GLM。 xglM。

Y kind of thing。Sorry， the one other thing I'll show is。In the debugger， you can query GPU memory。

I'm trying to remember how to do that。I may post it online， so what you can do， I think is。

I'm going to copy the。Poイント。From global memory。So， let me add。What's so d date of I。

 so I'm going to copy this value。Okay， and I'm going to take it to the memory window。

Let's see if this works， it's been a while since I tried it， so I may completely fail on this。好逼。😔。

Okay， so you got something， but you got gibbish and I don't know if this is I don't know if this is C or GPU。

 so I'm going to set columns to four。No so this didn't work clearly there's a way to do this I forget。

 but if any of you ask in that discussion I will post it there there's plenty of videos online that show how to use the memory tab to look at the full global memory you got a question。

学生生ば。This is谁。好两个问题。要考虑。不具你就。嗯哼。😊，有啥す。You could yes， yeah again I forget exactly how this is done。

 you have to do pointers and tell the what type of memory it is， but yeah， you can do that。All right。

 so let me stop this。But I'm going to open insight。Compute。

And you see open to here because the inside compute works with WSl as well if you get WSL working on the project。



![](img/0fffef76cafb255ef64c2303232fa23a_25.png)

But I'm going to open this up。And I'm going to say start activity。

I'm going to browse for my executable， which is。😔，Performance lab， bear bin。

I already have the release built， actually I'll use release with debug In for because it has more stuff。

And I'm going to give it a place to write the file。

We select folder and then I'm going to write compute。😔。

You can give it pretty much any final name if you want。

 but usually there's like en Pro for something that you can give。

You can set a bunch of settings here， I don't really care to set any right now。Again。

 you can change different values。For now， I'm just going to hit launch。

It's going to run a bunch of stuff which I have running on my command line。

 I'm not going to show you that because I don't want to reveal how fast you can make this because that's the Challed performanceance La。

 but giving a second while this runs。All right， so better time。

No quaing there there are there are performance optimizations where I'll show you so again this kernel shows or just is going to show all of your kernels how much time they took clearly stage zero is stage zero of optimization whereas stage four and stage five you' are going to get a lot of optimizations so clearly there's improvement over time。

😊，嗯。You can see compute and memory throughput these are like the important stuff if you're not maximizing your compute and memory throughput。

 something is wrong。And that's where you want to optimize number of registers， number of grid size。

 all of this kind of gives you how many blocks you're launching so for example in these。

Clonnels here， it is telling me I'm launching too few blocks right its telling me I' am launching too few blocks compared to all the other threads。

 all the other kernels。All right， let's dig in a little deeper。

 I'm going to go to this state zero kernel okay， and it gives me all the details。Compute throughput。

 I have 69%， memory throughput， 61% again， may seem great， but on a GPU not so great。嗯。

But it also gives you advice compute and memory throughput are balance to reduce runtime。

Both computation and memory traffic must be reduced。

 remember in reductions we said it's unoptimized that's what reduction state zero is。

So it's saying hey， reduce both compute and memory， and it's giving us some examples to look at。😊，嗯。

第。You can also look at literally the PTx code， the assembly code of your kernels if you wanted to。

 this is the kernel code for the reduction operation。嗯。Trying to look at。

No not so session kind of gives you all the information about the computer you ran on because you can send these reports to others and have them analyze at so they'll know what computer you add at on。

So I'm going to expand this again again you get a few charts。

 I want to talk about GPU and memory workflow distribution。

So here you see how it tells you how many active cycles there are and how many memory cycles there are。

So the DRAm active cycles is how much time was spent essentially pulling memory。

There one area I'm trying to look at， they keep changing the UI so forgive me because。

It's always I have to keep up with where they move things。嗯。Terical occupancyだ。嗯明。No。Oh， I'm sorry。

 it's right here。Occupancy is the ratio。 another way high occupancy does not， no， no mind not that。

Okay you。嗯。OhIt's standing into profile against certain detail metrics then okay。

Let me try to run this again。And I'm sorry I'm taking more time， but hopefully this is very helpful。

 especially as you do。So I'm going to set I'm just going to set the full。😔，And。

Did it sit on roofline？With the detailed。O。And is gonna run for。

So it's going to produce a new report now and then you can potentially use the different reports to compare stuff as well。

So this may take a little bit。Because you're collecting more metrics now。

 more performance counters and stuff so may take a small amount of time here。我。

That's measuring these things。こな。So Nvidia claims not to a significant degree。

 and I intend to believe that。TheBecause what it's doing is it's really getting into the schedulers and stuff and counting it rather than affecting the performance itself。

 there might be small percentage of hit that you take but it's not significant that it changes the like it's not a 50% hit or anything like that again you have to run it in release mode not in debug mode you'll get different results in debug mode。

All right， I think I'm going to kill it dead。So， let's see。Alright， let's go to。Details and no look。

 we have we have more inputs here。Of what's going on and also suggestions。

L2 slices workload imbalance， estimated speed up 6。44% if we fixed that and so on。



![](img/0fffef76cafb255ef64c2303232fa23a_27.png)

Instruction thread divergence， so we spoke about thread divergence before about having different different thread doing different things and it saying oh。

 if we fix this well have 16。9% of improvement， but this is the main killer right？

Global memory access patterns if we fix it52% improvement now we did fix that I have I have quod in here that fix that so I'm going to go to let's say。

Reduce stage 2 and I'll pick a random kernel in there。嗯。And here， again， if we go back to summary。

Reduce stage two was like much faster than any random reduced stage zero here。嗯。

So if we go to the details again， you'll see AU is highest utilized in 29% again this is a memory limited algorithm right computer is kind of free here。

嗯。So again， it tells you where you're unopimized where you have shared memory。

 where you don't in this kernel， we use shared memory。You have the SM busy SM active cycles。

 how much shared memory you've allocated and stuff allocated here。

Save with this more especially as part of project2 you'll get to use it a lot the one last thing i'll say is you can add a baseline as a kernel and then you can run it again and then you can compare it between a performance improvement you can make and then you can use various tools in here again I'll say that I've only explored this about half the key adding new features。

And then on Wednesday D will show the graphics version of this for like welcome applications and stuff and maybe touch on the compute side a little bit as well so we'll stop here I've taken a little bit more time hopefully this was helpful and then this guest lecture on Wednesday and then we'll also do the recitation for project2。

あ。ます。
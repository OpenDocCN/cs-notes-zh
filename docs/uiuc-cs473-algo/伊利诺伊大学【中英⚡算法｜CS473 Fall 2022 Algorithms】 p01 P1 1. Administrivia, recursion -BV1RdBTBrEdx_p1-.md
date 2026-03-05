# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p01 P1 1. Administrivia, recursion -BV1RdBTBrEdx_p1-

![](img/a94010fc80a6c2b9a4a65fb3a8e23075_0.png)

I'm asking for so many to a message and I bet at the beginning he's like。

 what are this firing the old man taking all these but I would like。



![](img/a94010fc80a6c2b9a4a65fb3a8e23075_2.png)

。在发。发回问。你你。开住你温发。但是上没。你非个到。か。好。我没。Yeah。Okay。We seem to be live， I'm not sure what happened there。

It's only a computer， it's not like we know how it works。All right。

Let me go ahead and get started just by introducing myself， I'm Jeff Erickson。

 I'm the instructor for CS/lash mathth 473， which is where you are welcome。Um。

Before I start talking about anything else。😡，One thing I want to emphasize over and over and over again。

Please stop me and ask questions。😡，This whole experience of being in the class more generally。

 but in the lecture specifically is going to be a lot more interesting if people interrupt me and ask me questions to try to stump me。

 it'll be a lot more helpful if one of you is brave enough to ask the question that you think is stupid and isn't because believe me there are 15 other people that have exactly the same question。

Please do not be afraid to raise your hand interrupt me。If you see somebody next to you waving。

 you know， holding their hand up， hold your hands up and point at them。

Eventually the entire class will be waving their ends and pointing at one poor soul in the middle。

 but at least I' get to answer their question。8ight。Um so。Please interrupt me at any point。😡。

Not just today， but and at any point ever。All right， so just to start off。

Let me make sure that I'm actually recording， yes， good。What is this？😡，What is this class， okay。

 so this class is a bit of a strange creature。😡，Because it's designed。

For a mixture of students that is somewhat different from the mixture of students that are actually in this room。

So the class is primarily designed as an advanced algorithms class for undergraduates who have taken CS374。

 that's our 300 junior level roughly undergraduate theory class。

Or graduate students in computer science or closely related areas。Hey。Um。

 if you have never had an algorithmist class before。

 if you don't aren't comfortable with big O notation。

 if you aren't comfortable with binary search trees， if you aren't comfortable with recursion。

This might not be the class that you want to take if you find yourself in a situation where you feel like the class is moving too fast for you。

 please let me know that may mean that I'm just going too fast。

 it may mean that we want to recalibrate which class you're taking there is another class called CS401 that' specifically designed for people who have an undergraduate degree in a noncomputing background like say linguistics or biology and don't have the same kind of experience that we normally would expect coming into an algorithms class like this。

😡，That would be a better class to start with than this one。Now， generally speaking。

 people even who don't have computer science degrees tend to do fine in this class。

 provided they have some programming experience and provided that they have some experience with proof based math specifically for discrete math。

😡，We're going to play a lot with graphs， vertices and edges， not plots of functions。

And so having some background familiarity with graphs is really helpful。

 but really having that sort of。Proof based math background where you're not just computing an answer。

 but actually trying to prove something is true， the process of proving something is true and the process of designing an algorithm is very similar and so that background is really helpful。

😡，Um。Generally， my attitude about this is。If。See how it's going to go for the first week or so if you're not completely sure if it's going fine。

 great， stick with it， you'll be fine。If you find yourself falling behind， please come talk to me。

 please come talk to the TAs because we can't help you if we don't know that you're having a problem。

😡，Okay， so those of you who've had 374。Those of you who are undergraduates in mathematics or mathematics in particular。

😡，You're probably also fine， even though you couldn't get into 374 because you've had math in particular math。

😡，347， which is probably going to give you the background that you need。And。Um so。This is。Algorithms。

4。See us。Undergrads。And gras。UmOr nearby fields。Then。嗯。

There are a lot more people in this room than there are normally。So on average。

 this class tends to have an enrollment around 75 or 80。This semester， right now。

 we have an enrollment of 183。187， sorry。Part of that is because we've seen a rapid expansion of the on campus Master of Computer Science MCS program。

A plurality of your NS students， welcome。But one of the consequences of this rapid growth。

Is that we are slightly under provisioned。In terms of our usual cohort of TAs and CAAs。

 so graduate teaching assistants， undergraduate course assistants。

 we're still looking for more people to add to the course staff。

 but I do want to warn you up front that we are a little bit short staffed at the moment。

 if this starts to become a problem either because people can't get attention in office hours or because we can't keep up with the homework grading。

 please continue talking with us， we'll let you know if we think there's a problem。

 please let us know if you think there's a problem。In terms of。Other resources。

Pretty much everything in this class is going to be on the web。I will be here in this room。

 I'm not going to lecture over Zoom， I'm using Zoom right now。

 but only because this is the most convenient way to record the lectures because Zoom automatically does recording and puts it in the cloud and then I can post the video of every lecture quickly。

😡，So you can find the course webp page by Googling for my name and clicking on the first link that you see or Googling for CS473。

😡，Once you get to the webp page， you'll see a bunch of other stuff theres the schedule of lectures that you would normally expect。

😡，Don't take this list too seriously yet it's likely to change as the semester progresses。😡。

Behind each of these links， you'll find lecture notes or textbook chapters。

Or things that look like textbook chapters， but are not actually textbook chapters again。

 those things are likely to be revised。Overtime during the semester。嗯。

We're going to be using grade scopecope， well I don' have a I don't have it myself set up to log in on the iPad。

 but gradecope is a program where you submit PDF。😡，Versions of your written homeworks。

 which should be assigned every week。Homework zero is due next Tuesday。It's already up there。

You are already enrolled on Gr scopepe。😡，You should just be able to upload PDFs as soon as we actually opened it up for Home Ze submission。

嗯。You can also when we'll grade these things online， we'll return it on gradeSpe。

 you can submit regrade requests directly on gradeScope， we'll have in person exams。

 but we'll scan them and upload them to gradecope so all graded work will eventually appear there。Um。

We're using a platform called Ed。😡。

![](img/a94010fc80a6c2b9a4a65fb3a8e23075_4.png)

's eitherer Ed STEM or Ed discussion as an online discussion forum。

 you should be able to log in using your Illinois IDEDU credentials and just go straight in。

 I've already checked that several students have already followed the link and are already in the roster。

But if you find yourself unable to get in。Um， I'm going to dread saying this， please send me email。

And I'll just upload the entire roster the nice thing about this is you'll be able to participate anonymously。

😡。

![](img/a94010fc80a6c2b9a4a65fb3a8e23075_6.png)

So you can ask questions anonymously， you can post comments or answers anonymously。

And it really does mean anonymously， even I won't be able to tell who it is。Again。

 everything I said about asking questions goes for the online discussion as well。

 if you have questions about the course material， please ask there。😡。

If you have questions about course policies， please ask there。As a general rule。

Questions about course logistics or administration will answer right away questions about technical material we the course staff is deliberately going to hang back。

😡，For a few hours and give you an opportunity to answer each other's questions before we step it。

We'll still vote on your answers up or down or put comments on the answers。

 but we're going to hang back。😡，And let you use this as an opportunity to discuss amongst yourselves。

this is something that you know， I think。Really one of the best pieces of advice I can give。

For this class is find other people to work with。😡。

You do not get any extra points by sitting in a cave and doing everything yourself。😡。

The goal here is to try to get better at things and it's a lot easier to get better at things if you're working with other people who are also trying to get better at the same things。

嗯。嗯。😊，There are you know some other useful resources， some of this needs to be updated。

 but there's videos and lecture notes and homeworks from several past semesters of this course。

 you can find any number of algorithms courses all over the web again there's this textbook that I wrote you do not have to buy it it's available free。

 you go here and you just download the PDF。😡，m but don't feel like you have to use my book。

 if you have an algorithms book already， and it covers the topics that we're covering， but great。

 feel free to use it， feel free to recommend it to your friends with just， you know。

 providing this specifically because I happen to know the author。😡，All right。

Anything else that I need to talk about in terms of resources， I don't think so， but again。

Please stop me and ask questions if you have any。U。Policy stuff。

So there are really only a few things and that I need to say and I need to just need to say these quickly。

 one is in terms of group work。😡，You are welcome to work with anybody that you want。

 you are welcome to use any resources at your disposal whatsoever。😡，However。嗯。

When you actually submit。Your homework。For homework zero。

 each of you needs to write the solutions yourself。😡，In your own words。And if you used any resources。

 you need to tell me what resources you used。That includes other people now。

Big study group in the basement of Sbel just write big study group in the basement of Sbel。

 you don't have to list everybody by name if you don't know people's names。

 but we do want you to get into the habit of saying well I found this stack overflow post really helpful I found this handout on ch really helpful my brother took this class last year。

 he was really helpful。The only person that you don't have to cite is me。If I help you find。

 that's my job。😡，Right， but if you do anything else， just let us know。

 this is not because we want to penalize you again。

 you don't get any extra points by doing everything completely by yourself。😡。

The more you do by yourself， the more you'll learn。

 but I assume at this point you're adults and you know that， but we don't want you to just steal。

Right。We do want you to actually write things down yourself in your own words。😡。

Once we get to homework one， which will be released next week。

 you can submit homeworks in groups of three。But even if you work in larger groups。

 you need to split up into groups of two or three to actually write things up。😡。

And I'll say more about this then， but whatever you turn in really needs to be a group effort by all three people。

😡，嗯。UAnd。The last thing。Is。The department has posted in many different places。

 including links on our course webp page to a declaration of values and code of conduct it's really summarized by those four words。

😡，So it's unfortunate that there's historically been a very small minority of people in our department who don't follow that rule that you've seen instances of。

😡，Gender bias， we've seen instances of racial bias， we've seen instances of sexual harassment。

 we've seen instances of physical violence。U we they're very rare， but when they happen。

 they really have a very outsized impact on the atmosphere of the class。

 we really want to prevent that from the get go just by saying you know's here's where we stand。

 this is what we think it means to be a responsible contributing member of the Illinois computer science community。

😡，This goes for online discussions on Ed， this goes for behavior in office hours。

 this goes for me or the TA is interacting with you just as much as it does with anyone else。😡。

If you run into something where people seem to be violating this policy。

 we have a committee within the computeruter science department， I'm a member called CS CARs。

 if you just aren't sure what this means， come talk to me。

 if you run into something you think might qualify， just come talk to me。

 if you're not comfortable talking to me， can find pointers to other people that you can talk to。😡，嗯。

And I guess the other elephant in the room。I see some of you wearing masks。

 you are welcome to wear masks。😡，If anyone tells you you're not welcome to wear masks。

 see the previous line。Um。If you are feeling unwell。Do not come to class。😡，Everything is online。

Don't feel like you're obligated to be here just because it's a class and everything is online。

 it's fine， even ifre you're going into an exam。😡，If you are not feeling well。

 let us know that you're not feeling well， but do not come to the exam this is not just because of COVID。

😡，There are lots of other reasons why people sometimes don't feel well。

 sometimes this is a disability related issue， sometimes you know parents get divorced， dogs die。

 people slip on the ice and break their wrists， all sorts of bizarre things can happen that mean you're not going to be acting。

 you're not going to be able to participate in the class with you know complete attention。

If things like that happen， let us know we will make room for you。哎有。

And I mentioned disability related stuff。If you。Do need disability related accommodations。

 extra time， low distraction environment for taking exams。

 please talk to the people that Dr as soon as you can and please get me a letter describing the accommodations you need from them as soon as you can。

 but at a minimum at least a week before you actually need those accommodations。😡，All right。嗯。

I think。😡，That's all the Adistia that I really need to cover only took 20 minutes。But again。

 I'm happy to answer any questions if people have questions。😡，Yes。然后什么什呢？是。Yeah。

 don' me or the course staff， we just assume that you're talking to me the TAs and the Cs so that's sort of given。

😡，Yeah。No， up to three。You do not have to have three people。Yeah， put you know， it should be clear。

 but probably better to put it at the end than at the beginning or like on five， I got this idea for。

 you know， no just at the end， just tell us what resources used。😡，Yeah。here啊牙子。So that I pointed on。

Of course， website to this thing called Ed discussion， that's our Piazza killer this time。嗯。

Basically， I'm not using piazza because it's kind of old and clunky and it has ads。

And the campus doesn't like it， I'm not using campus wire even though the campus likes it because it just doesn't work。

There's already a post on Ed。😡，For an informal discord。For this class， you please by all。

The course staff is not going to answer questions on discord。

 so this is entirely for discussion amongst yourselves。

But if you find that more useful than Ed than by all means。Use it。Other questions？Okay， yes。

I'm sorry。はい。Oh， the question is， are we required to type homeworks？😡，No。

If you decide that you want to handwrite homeworks。

 I'd encourage you to like use a tablet or something and then export a PDF that way。

 if you want to write on paper that's fine， but please use black ink on white paper not gray pencil on heavy grid graph paper。

😡，Please use a scanning app and not just raw photograph so that you can do things like remove the background。

 remove any key sing， increase the contrast， so it looks like something that you could print out and it would still be readable。

This normally isn't the problem， but on occasion we've just gotten stacks of JPEGs and。🤢。

That are kind of unreadable because the shadow of the camera is covering half of the answers。

Don't do that， practice a little bit with with scanning the paper before you hand it in if that's the way you want to go。

But typing is not required if you do want to type。😡，There is a lotx。😡。

Template for types setting answers again， if you decide you want to use Lotech。

 you're welcome to use that template but you don't have to。😡。

Just just set up the way that has all the information we want。Other questions。Cool， so。嗯。

Maybe we should talk about algorithms。This is a song about algorithms。All right。So。Sure。

There's a lot of。Sort of。Foundational stuff。That I'm not going to talk about unless you ask me questions like。

You know， loops and function calls and arrays and binary trees， we kind of assume that you know that。

But as a warm up， I do want to talk about what I think is probably。😡。

Single most important design tool for algorithms， which is recursion。😡，你好。

For those of you who've had 374， everything I'm going to say for the rest of the day is going to be review。

 not that's not true for the things I'm going to talk about on Thursday。😡，So。So recursion。

 the basic idea is。You're given some instance of some problem。

And the way you solve it is not by solving it。The way you solve it is by making a little bit of progress。

😡，Until you reach a state where you have one or more smaller instances at that same problem。

 and then you delegate those smaller instances to the recursion ferry。😡，He， now。

So you can think of this as kind of reduce to smaller instances。And then delegategate。

Or if the instances are small enough。That either you can't or it's not worth bothering reducing them or just do it yourself so if instances are small fine just do it brute force。

 whatever。😡，Um， any algorithm running on input of constant size takes constant time， so fine done。

 that's your base case for every recursive algorithm。When the input has constant size。

 use brute force that takes constant time。系。Now， as a sort of canonical example。

There's the so called Tower of Hannoi problem， which I'm sure everybody has seen and everybody is sick of。

 but I just I want to review。The solution in the way that I would recommend thinking about it。

So the Tower of Hanoi is a physical puzzle that was designed in the late 1800s by the French mathematician Edward Lucca。

😡，Um，U， it consists of three pegs sticking out of a wooden board and on some those one of those pegs。

 there is a stack of circular discs of different sizes。😡。

All stacked up in order from smallest at the top to largest at the bottom。

The goal is to move those discs。From the。Poll on the left to the pole on the right， say。😡。

Subject to the following rules。😡，You can only move one disk at a time。😡，And you can。A larger risk。

On top of the smaller disk。And so the question is， how do you do this？ok。😊，So。

You probably have seen this puzzle before， you probably have an idea how to do it。

 but here's how I want you to think about this。😡，I really want to move that big disc there at the bottom。

😡，But in order to do that， I have to get all the other disks out of the way。

 I have to move those other n-1 disks to a different peg。What was the problem I was trying to solve。

 right， move a stack of to a different peg。Just taken move a stack of n disks to a different pe and came up with a step in the solution as move n minus one disks。

😡，To a different peg， that's a smaller instance of the same problem。

And so once I have a smaller instance of the same problem。

 I'm just going to assume that I can solve it。Then I great now I I can move the larger disk。

 I made sure to move those n minus1 disks to the。Hold that I don't care about when I'm not going to move the largest disk。

 so now I can move the largest disk to where it goes。😡。

Now I need to move all of the other discs from wherever they are。😡，To the rightmost pole， again。

 that's a smaller instance of the same problem and so I just assume I can do that。😡。

The algorithm for solving the Tower of Noi has exactly three steps。😡，Move all disks。

 accept the biggest one， move the biggest one， move all disks except the biggest one。

It's really tempting when you first see this。To go， yeah。

 but how did I move those smaller disks and start opening up the boxes and start thinking about， low。

 wait， there's this pattern of disk moving around。Don't do this。You're working way， way。

 way too hard， you really， I it sounds like a joke， but it really isn't a joke。

It's really useful to believe in the recursion fairy。

The recursion fer is going to move that smaller pile of disks， you don't have to worry about it。

 it's none of your business， how the recursion ferry does its job。😡，Don't think about it。

 you're calling a subroutine， think it of if you like。

 that somebody has implemented a library that can solve every instance of your problem except that smaller than the one you're given。

😡，Don't rewrite the library， just call it。😡，嗯。嗯。So if I want to solve。

The problem where I'm moving end disks from some source peg to some destination peg。

 and I'll call the third peg temp。Then。The first thing I do move the top n minus one disks from source to temp。

Using well， the third thing is， well， I have to put three things in， so that's the third one。

And then move。Just can。And then Hanoi。And minus1 from temp。To destination。

Using source as a placeholder if I need it。Three steps。Just three steps。For purposes of design。嗯。

I'm actually done。Something。Is that is it really？South。There's this thing I heard of once。

Something about a base case。You've handled the trouble case， we need to handle the base case。

Let me think about a little bit about about like。So。Again。

 this is how I recommend thinking about this let's just think about， you know what is N。

N is some integer greater than equal to0。咁。Does that algorithm？Work in any meaningful way whatsoever。

For all possible values of N。😡，I started off saying， I really want to move the largest disk。

Does that goal make sense for every possible value of N？They're no， there has to be a largest disc。

That means n has to be positive in order for that strategy to make sense。😡。

So this three line code that I've written， actually， I needs a condition。😡，Here， which is， you know。

 this only works。If n is greater than or equal to1。If n is zero。

 then such it doesn't make sense to call Hannoi minus1， there's no such thing as negative1 disks。😡。

So I can't， you know， I've fallen off the bottom of the earth。

I've reached the edge of the Minecraft map。嗯。啊。So。The recursive strategy just doesn't work。😡。

So I have to solve the only remaining case。😡，Differently。

Now I'm going to ask a really easy question and you're all going to get it right。😡。

How do I solve that last remaining case？不。Some of you didn't get it right， most of you said nothing。

All of you who said nothing were right。How do you solve the Tower of Hannoy when there are no disks？

It's already solved。There's nothing to do， so there's a story that Lucca tells about monks at a temple moving these golden disks from one diamond tip needle to another。

 but these are good Buddhist monks。And so when they get to the base case。

 when there are no disk left， they're very， very good at doing nothing。😡，All right， so the base case。

 it's not in the code because I just don't have an else， I don't need it， but now I really am done。😡。

There is my algorithm for the Tower of Hannoi。So。嗯。The， you know。

The bit of advice here is believe in the recursion ferry。嗯。 you know。You know， check the。

Boundary assumptions。嗯。So when you come up with a high level recursive strategy， you need to check。

 am I making any assumptions about the input？😡，you need to design an algorithm for your problem that works for arbitrary input and those assumptions might be very。

 very simple， but still they need to be written down explicitly。And then finally。

The empty set is your friend。Um， it's， you know， a lot of people when they first start doing this stuff are a little uncomfortable using zero as the base case instead of one。

 but this recursive strategy works perfectly well when n is equal to one。😡。

So why not let it now it's not wrong to special case n equals one or n equals two or all n less than a Google。

 but it's just more complicated than it needs to be。😡，All right。So。Once you've got an algorithm。

 though， we also need to analyze it。😡，Yeah， sorry， question。Which is the second condition， I'm sorry？

Well， the induction ferry never puts a smaller disk on a larger disc on top of the smaller disk in any of those recursive subproblem。

😡，All of the discs that the recursion failure are moving are smaller than the big disk that's sitting on the ground。

 so yeah， I can put stuff on top of it， that big disc is never moving。

 so it's never moved on top of anything。😡，That's it。Okay。So。You need to think about running time。

And in this case， know， running time I want to think of as the number of moves。Okay。

So I'm going to define this function thats just sort of traditionally called T of n for the time when the input is n or the input size is n。

😡，And I'm just going to transcribe what the recursive case of the algorithm does。U，I guess I should。

 you know。Just to be complete， you know， make this explicit for once。If n is equal to 0。

 then I don't do anything think， so the T of 0 is0。Otherwise， I make a recursive call。

The recursion ferry moves n minus1 disks， and so they make t of n minus1 moves。Then I move disk N。

 and then the recursion ferry once again makes T of n minus1 moves。Yeah。Now。This is， again， the。

Recurrence that describes the running time of the algorithm exactly mirrors the structure of the algorithm。

😡，But this is not a particularly。Useful form to describe the running time if I want to compare the running times of different algorithms。

 I really would like now against my own previous advice to open up the black box and just to get a nice simple closed form expression in terms of that。

😡，Now there are lots of ways to do this， but the one that works best and the one that works the most often is to look on Wikipedia where it says how many running。

 how many moves you need to solve the。😡，Ter Han problem and Wikipedia says 2 to the n minus1。Now。

 if you don't trust Wikipedia or if your internet is out。😡，You could also do something like this。

I could write down a few small values of N。And write down the corresponding values of T of n and just by grinding through the formula。

 you'll。😡，know fill in a table that looks like this。

So the reason that T of 5 is 31 is because T of4 is 15 and two times 15 plus1 is 31。😡，同意。嗯。

And then you look at this and go， wow， that looks really close to powers of two except it's off by one。

 let me guess that the answer is2 to the n minus1。Now that guess is neither more nor less believable than Wikipedia。

Until we actually prove the answer is correct。So。How do we prove。Something correct。

About something recursive。Induction。You'll get really sick of this。

But pretty much every time I say the words how then do and then you and improve in that order。

 the next word out of your mouth should be induction。

We're using induction in the first lecture and every lecture that comes after a lecture with induction will use induction。

😡，Okay， so now。I can already feel the math majors seething。

Why are we doing this junior high school nonsense？This isn't for you。Trust me。

 there are people who did not see induction in junior high school。Some of them。

Then I'm deliberately trying to show easy examples to make sure that everybody's on the same page before we start doing more interesting things。

So what do I want to prove， the theorem that I want to prove is t of n is equal to2 to the n minus1 now。

Or all n greater than equal to zero。Now I'm going to do something that is going to annoy the math majors even more。

How do you prove a statement about all integers greater than equal to zero？

There's only one way to do it。You pick an arbitrary integer greater than equal to zero。

 and you prove something about that integer。😡，This is the way you prove all universally quantified statements。

See an enemy pointing at you， okay， thank you。是。我 thank you。So there are many paths up the mountain。

😡，So one way to do this that actually works out surprisingly well a lot of the time is just to start by trying to write an induction proof。

 only you leave a black box there。😡，And you sort of。

Go through the motions of an induction proof and say， in order for this induction proof to work。

 certain constraints have to be satisfied， those constraints solve to the closed form solution that I want。

😡，There are other somewhat more intuitive techniques and drawing out a recursion tree。

 which we'll actually do later， or if you've used things that recurrence is very similar in spirit to differential equation and we can borrow techniques from solving differential equations to solve recurrences。

That will just lead you directly， like just mechanically derive the solution。😡。

But part of the reason I'm showing you this is because I have strong opinions。

About how induction should be done。How do your son say？Out to your sense at the end。

I'm going to do this no matter whether I think I might use induction or not。

 there is only one way to prove a universally quantified statement。

 assume an arbitrary object and prove something about that arbitrary object。😡。

Now that I've done that。😡，U。I'm going to use。The recursion fairry。

 only they're wearing their math hat instead of their CS hat， so we'll call them the induction ferry。

And my induction hypothesis is assume for all integers less。Then N。

On non negative intes there' is less than n that t of k is equal to2 to the k minus1。

You'll notice something about this deduction hypothesis。😡，It doesn't talk about n minus1。

I also don't assume something about n and then go on to prove something about n plus one that's stupid。

 I'm trying to prove something about n， just prove something about n。

 just like the way that you wrote the code。😡，Right you。

You're given an object and you compute things with that object don。😡。

Like assume you have an object and build things bigger。So。

I'm going to state a strong induction hypothesis up front because I haven't thought enough about whether I really need weak induction or strong induction or no induction at all。

😡，But strong induction will always work。😡，So I may as well use it。Now I don't have to think。😡。

I just need to do case analysis。Two cases， one case is again。

 mirroring the structure of the recurrence。😡，Either n is equal to0 or n is not equal to0。😡。

If n is equal to0， then t of 0 is0 by definition， which is equal to 2 to the zero minus1 done。😡。

The brute force in the algorithm is reflected by the brute force calculation easy calculation in the proof。

😡，For the more general case。I chase。嗯。Definitions。I substitute by the induction hypothesis。And then。

 I do math。Here's my directional hypothesis and NAda。That's foolproof。😊，嗯。Oh look。

 I actually only use the induction hypothesis at n minus1。😡，So what？I'm done。

I could go back and replace that with a reion hypothesis， but that would be work。

So I'm not going to do it。Neither should you。And。Okay， so。嗯。Again， the general idea behind， you know。

 when you're writing the proof in this case， the cases are directly copied from the cases in the algorithm。

 but as a more general rule， I would approach the induction proof the same way that I would approach a recursive algorithm。

 try to come up with an argument。😡，That works for general N。

And that might invoke the induction hypothesis and then look where in this argument。😡，Do I not。

 do I use something about and other than the fact that it's a non negative integer， Well， right here。

😡，When I say t of n minus1， I'm using the fact that n is positive。😡。

Because t of n isn't defined when the t of a negative number isn't defined。

 so I need to separate out the argument for n equals zero separately。😡，O。Yes。个有提。

I'm sorry to say that again。I actually actually use the notation key in the green for instead of earth。

N has a meaning。N is the arbitrary integer you want to prove something about。😡，So in the green part。

 I'm proving something about that integer， which has a name， and that name is n。😡。

so there's no need to introduce another name for the same object。😡，right。Yes。😊。

The base case is the one that doesn't use the induction hypothesis。

 or more generally when you have eight cases， the base cases are the five that don't use the induction hypothesis。

😡，As long as the case analysis is clearly exhaustive。😡，Yes。

 a non negative integer falls into one of these categories。N is zero， n is one。

 n is prime and is composite。Maybe for in prime， I don't use the induction hypothesis for it and as composite。

 but I do。😡，I don't then need to say this is a base case。😡，Because the question is just。

 did I prove the theorem for the case and equals zero， yes？😡。

The other thing is until you write down the argument。

 you don't actually know whether the case is a base case or an inductive case。

 so it's always tempting to write things in the same order you're going to read them。😡。

You write down base case before you've written the argument you might find yourself backed into a corner。

😡，嗯。Yeah。喂。U in the blue line， this is Tn minus1 plus1 plus Tn minus1， this simple algebra。Okay。

So let me do something。Slightly more interesting。All right so。

I'm going to go back from junior high school for some people to elementary school for everybody。嗯。

Now， not everybody learns to do this in exactly the same way。

 but it's relatively common these days for people to learn to multiply large integers by reducing it to the problem of multiplying single digit integers。

 usually using some variant of what's called lattice multiplication。😡，So three， seven， five， and3。

 15。😔，Somebody's going to check my math because I'm going to do it wrong。2，9，4， and then。0，6，5。

 okay so。You multiply each digit of one number by all of the digits in the other number。

 you write that down as a partial product。😡，That gives you a sequence of partial products。

 which you add up。😡，If you are multiplying two n digit numbers。

 you're going to write down about n squared digits。😡。

You're going to multiply every digit of the first number by every digit of the second number。😡。

And so。This is going to run in。N squared time， it's just two nested for loops。

 not doing any recursion or anything here， I'm reducing to the case of single digit multiplication for which I have a lookup table in my brain。

😡，And addition。Which。There's a simpler algorithm we know how to do with the For loop。

Algorithms from multiplying integers。😡，In particular。

 evidence exists for this algorithm or variants of this algorithm for integer multiplication have been known for millennia。

😡，The Babylonians。Used a。Floating point base value numerical notation let's simplify in just say base 60 where they did fairly large calculations like this。

 there's a stone tablet with uniformform minute dating back to about 2500 BC that contains a fairly large list of pythagoreore and triples integers A B and C such the a squared plus B squared equals C squared。

 you can't do that unless you can multiply C by itself。😡。

So you have to be able to do this kind of multiplication。

This is not the only algorithm that was known in antiquity。

 but all of these classical algorithms run in n squared time。😡，嗯。Its a commongraph。😔。

This led Kmagorov， who's a Russian mathematician in the 1950s。

To formulate what he called the n squared conjecture。😡。

The conjecture is any method whatsoever for multiplying two engine numbers must use a quadratic number of steps。

😡，Whereas step is something like add two digits， multiply two digits。😡。

Dividideed digit by two write down a digit。So you can define this fairly generally。And。嗯。😊。

He decided that he would have a seminar。And he would invite people to try to work on this conjecture。

嗯。And。And its totally called it Subba。Was a student。

who came to the first seminar and they discussed it and he went home and he thought about it for a while。

 23 year old graduate student。He came into。Kmoovv's office the next day， and said。

Think your conjecture is false。And he showed Kmogorov。

 the algorithm I'm about to show you at which point Kmogorov went。😡，Seminar canceled。

 that was it for the semester。But he was nice and he wrote up the algorithm and submitted to the Russian Academy of Sciences actually without telling Ktsba that he was doing it。

 a little iffy， but you he did attach Ktsubba's name to it， so it's all good。

So the idea that Kt Sububba had， well， let's start with this idea that I've got this number x that has n digits。

嗯。I can write it as a combination of smaller numbers that have and over two digits。

 let's just for now imagine that I'm working in baseTime。😡，I have another number one。

Ihenoid debt is C time。And over to plus D。Now。In effect。

 what I want to think of is x as a number written in base 10 to the n over 2。😡，It has two digits。

And y， as a number written in base 10 to the n over 2 gets two digits。😡。

And I'm going to multiply these two to digit numbers。😡。

So x times y is a times c times  n0 to the n plus a times d plus b times C times 10 to the n over 2 plus b times d。

And right here。I have four instances of a smaller problem。

I've reduced one instance of multiplying two end digit numbers to four instances of multiplying two and over two digit numbers。

 so I can let the recursion fairy do all the real work。😡。

And then writing down extra zeros doesn't really take any work。😡，This is not actual a multiplication。

 this is just writing down zeros and addition is an easy for loop。

So you get an algorithm whose running time satisfies this recurrence。

The order N is the overhead for doing Ed。嗯。😊，Well。We'll see how well that works。

I need to solve this recurrence。Now I could guess the solution。

 but I'm going to actually derive the solution fairly quickly using using a。😡，Back of the envelope。

 cartoon graphic device called a recursion tree。😡，So I'm going to draw a tree of boxes where the boxes correspond to the non recursive work used to solve some subproble。

 so at the top level I'm given two indigit numbers and I need to do about n units of work not counting recursion。

😡，And then I'm going to make four recursive calls。Each of those is。

Corresponds to an instance of multiplying two n over two digit numbers。

 the non recursive work that the algorithm performs on those n over two digit numbers in each of those cases is n over two。

And then each of these is going to split and make four recursive calls。

The problemsble of size n number four and so on。So all I've done is write down all of the work that the recursive algorithm does if you open up all the recurion recursive calls。

 I've just written it down。😡，Of structured。The way I write it down in a way that mirrors the recursive calls themselves。

😡，And then what I'll do。Is all sum up。Along each level。

And this will give me a nice series that I'll be able to sum up so at the top level Ill only one。😡。

Instance of size n and I do order n work at that level。😡，At level1。

 I have four instances and each one of them I'm going to do about n over two work。

 so the total amount of work at level1 is 2N。😡，At level two。

 I have 16 instances of multiplying n over four digit numbers， so 16 times n over4， it's about4 n。

And we' generally at the elf level of this tree。I'm going to do about2 to the L over N work。😡。

So the total amount of work I do in the entire algorithm is the sum of all the values and all the nodes in the entire tree。

 which means since I've already summed up horizontally。

 now it's just the sum of these things I've written over here on the right。😡，All right。

 so the total work here。Is the sum of little e goes from zero up to some maximum level？

Of2 to the L times n。Let me factor the N out front。Okay。Now。This is a geometric series。

The nice thing about geometric series is that up to big O。

 the only term that matters is the largest term。😡，There's a closed form thing I could write it down。

😡，I'm doing algorithms that this big O glasses that I can put on so I don't really care。

 This is n times big O of two to the capital L， where capital L is the maximum depth。Of recursion。

Okay。So I still need to figure out when the recursion is going to bottom out。😡。

So let's think about this， well， maybe you have an idea of how long the recursion is going to go。

How many levels deep do I need to recurse？So log in， but can you tell me why？Okay。好。嗯。Right。

 every time I recurse， I reduce the size of my instance by a factor of two。😡，The definition of log N。

😡，As far as we're concerned is the number of times that you need to divide by two。

 starting it in until you reach one。😡，Or some number smaller than one。Right so。L is equal to。

About log base two of N。😡，The precise value here depends on the base case of the algorithm。

If I stop doing this weird recursion when I get down to four digit numbers。😡。

Then the recursion depth will actually be log based2 of n minus2。😡。

If I stop it at Google digit numbers， it'll be log based 2 n minus at Google。

But in the end that's only going to contribute like lower order terms to the running time and those all get swallowed by the go。

 so I don't care this is a feature of a lot of analysis of recursive algorithms。

 the precise base case doesn't matter， it's always when the problem has constant size。

 use brute force that takes constant time。And。嗯。And so this ultimately comes out to。Order n squared。

我 didn't help。And I'm reasonably sure that。Pmagorov probably showed this in his first seminar。So。

One intuitive way of seeing how this works， why this is n squared is imagine putting your left index finger on one of the digits of x and your right index finger on one of the digits of y。

😡，There's going to be one recursive call where both of your fingers go down to the recursive level。

 which means eventually there's going to be a base case where these two digits get multiplied。

So every pair of digits is at some point going to be multiplied。😡。

N squared really is the best we can hope for。For this algorithm。But。

Then Ktsba came off with the following。嗯。Let's see one way。

 how I can write this a minus C times B minus D。Let's multiply this out。That's a B minus a。

D minus Bc plus B D。That's so let me rearrange things here。Sorry。Yeah， that's right。

Now you'll notice here。I don't actually want a times D。I don't actually want B time C。😡。

The thing that I want is AD plus BC。😡，And there's more than one way to calculate that。

 so in particular， I've already， sorry thought I knew something was wrong here。嗯。Sorry。

I'll get this right。We just start over。Yeah。A minus B， C minus D thats。AC minus。AD minus BC plus B D。

Which means the thing that I want A D plus BC， I can write as AC plus B D minus。ABCD。ok。

This is the expression that I actually want to compute。😡，As that sort of intermediate coefficient。

I've already computed AC， I've already computed BD， so in order to get this expression。😡。

I don't need to do two more multiplications。😡，I only need to do one more multiplication。So。

This changes。My recurrence。Now my new algorithm。Does。Three instances of N over2 digit multiplication。

And then a bunch of linear time stuff。In this case。

 the one difference is of doing a little bit of subtraction to create the arguments that I'm going to pass the recursion fairry。

 that's fine。😡，We're allowed to manipulate the data however we like。😡。

It's not hard to realize that these are also an over two digit numbers。😡，So。Fine。

 let the recursion ferry handle it。And now when I change that that three into a four and I try to redraw the。

The recursion tree。嗯。Something really nice happens。I said， well， no。

 actually I only have three children per node。Which means。This is now three havebszen。

And this is9 fourths n， and the amount of work at level L is three halves to the L times n。

So the total amount of work。Is。Big O of n times3 halves to the L。The capital L。

Not two to the capital level。With be so far？All right。

 so capital L is still log base two of n every time I recur I'm dividing the problem size by two。

 so this still comes out to n times。😡，Three halves to the log base two of n。Now I pull out。

One of those log identities that no one ever remembers from Preout。

A to the log base B of C is equal to C to the log base B of a。This is really useful。

 This is both of these。You can see is E to the log A log B or log C or no that's。😡，Yeah。

Loug A lu C everlooked it。Okay， but just remember that you can swap。The base of the log。

 if it's in an exponent with the base of the exponent。😡，系。So that means this is。

N to times n to the log base two of three halves， which comes out to about end the 1。6 something。

So this really is sub significantly subquadratic it is no longer the case that you can point at two digits and at some point those digits will be multiplied because in the subproblem that involves those two digits。

 they kind of get things get kind of smeared around by doing those attractiontracts first。😡。

And so you're sharing work between what used to be independent subproblem。

 they get merged together and so you end up with something faster now in practice。

 Katsuba's algorithm really is faster than the naive lattice multiplication when and is bigger than about 50。

😡，There is a whole slew of improvements on Kt Suba's algorithm let's break。

The number into three pieces， which I can combine using only five multiplications。

 let's breaking into four pieces， which I can combine using only seven multiplications。Um。

 eventually this leads to like something where you can set the number of pieces as a parameter itself and fine tune that。

😊，But ultimately， the fastest way to do multiplication is based on something called fast Fourier transforms。

😡，Um。Which as of 2019。Actually gets down to。嗯。En log N time。

The same running time is sorting the digits。Um。This is only the algorithm that you want to use if the number of digits in your numbers is larger than the number of electrons in the universe。

😡，But it still， it's nice to know that it exists to sort of solve the problem。

So on Thursday I will talk about fast Fourier transforms。

 I will not describe this N log N time algorithm because I don't know enough group theory。😡，Um。

 but at least I'll get you part of the way there。Again。

Please feel free to come up and ask me questions afterwards， but we're done for the day， thank you。😡。



![](img/a94010fc80a6c2b9a4a65fb3a8e23075_8.png)
# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p07 -P07-Lec 07 - Tagging activity; Conditionals.zh_en -BV1zQ27BeEfF_p7-

![](img/06b64ed60f73afee8ac480659611e102_0.png)

All right， hello， everybody and happy Thursday， Happ old time music convention to those who celebrate very exciting stuff。

 I hope everyone has been having a really nice week。😊，Today。

 your week is about to get better because we're gonna get to talk about fun compiler stuff。

 So let's dive right in on some activities。 I promised during last session that you could hold your questions about why we're using specific tags because we're about to have an activity on it on this day。

 now we're gonna do that。 So let's go ahead and quickly cover what we're gonna talk about today and then we'll do our activity。

 So our topics today， we're going wrap up that boolean related stuff。

 we're going go ahead and start talking about conditionals。

 which will involve talking about flags involve talking about jumps。

 we're gonna dive in a bunch of stuff in that space。

 And if we look over at our big summary slides for the entire class。

 The things we're thinking about today are mostly we're going to be about assembly anding control flow jumps。

 and then we're still thinking a bit about types and type checking。

 We've still got that numb question mark operator that we're gonna put in place。

 But we're gonna dive in first with our activities。 So let's go ahead。😊。



![](img/06b64ed60f73afee8ac480659611e102_2.png)

![](img/06b64ed60f73afee8ac480659611e102_3.png)

And take a look at this cellularul activity。 You can see we have some things that look rather like that numb tag rather like that bull tag。

 but this time we've got a made up type called unicorn and what I'm going to ask us to do is two separate activities and you can go ahead and write this down on a piece of paper if you've got a piece of paper handy you can go ahead and write this down in your notes app doesn't really matter how you record it but I want you to do is go ahead and fill in this and then fill in this based on going through the process of tagging this value with the unicorn tag So go ahead and go through the process that we saw in the compiler on Tuesday that we used to actually apply a tag。

 remember sort of what we were using from our information about shift mask and tag and then go through that process in here to finish tagging this value with our unicorn tag and then over here on this side we're gonna to go ahead and try to figure out is this value does this in fact represent a unicorn and again。

 go ahead and go through the process that we already。About on Tuesday。

 So this is just to remind ourselves of what we were doing。

 Go ahead and spend about a minute with folks nearby fill in these boxes。哼哼哼。😊。

Always takes a moment to read it back into our memory。

I'm going to give us a little bit longer than that original minute since it seems like we're still remembering。

 which is totally fine。Allright， I'm guessing we're probably feeling at least pretty close the answer now。

 So let's go ahead and do it。 So what is the very first step that we should take， right？

 What is the thing that we want to have happening sort of around here in this transition。

 we're still thinking。Do we want to go back and actually see the compiler from last time。

 would that be helpful？Okay， yeah， let's do it。So here we go， we've got。Our compiler。



![](img/06b64ed60f73afee8ac480659611e102_5.png)

Let's swap over。

![](img/06b64ed60f73afee8ac480659611e102_7.png)

Okay， so here's an example。Of how it looked when we were doing this for Booles。

Go ahead and take another one minute and let's figure out how to use。Our shift， our mask。

 our tag to do this task。if you'd like to swap back to the boxes diagram。

If you'd like to stay on this one。Oh， it's so mixed。 how do I make these both happen？Well。

 I'll give you another 20 seconds on this and then we'll swap back。



![](img/06b64ed60f73afee8ac480659611e102_9.png)

All right， let's swap back to our activity。

![](img/06b64ed60f73afee8ac480659611e102_11.png)

AndNow we want to do the same thing that we are doing there for Booleions。

 but we want to do it for unicorns。Okay so hopefully after seeing the compiler it was pretty clear that the thing we are doing when we are trying to add our tag onto an existing value is just taking whatever was currently in that register。

 whatever was in those 64 bins where we could put zero or1 shifting it in order to leave enough room for the tag and so in that case that would mean let's go ahead and leave three spaces we can see that we've got this unicorn shift of three so that's going to go over there and that's going to go over there that's0 and that one and then we've just got these three0s left in that are just going be the gap where we will then apply the tag and so now we're ready to actually or with the unicorn tag which is 101 and so these bits will remain unchanged but we will go ahead and or with 101 to get those bits at the end。

 and so now we have a value that is in some ways the same as the value we started with but in others different except that it。

IsTgged with this unicorn tag for us。 Now， what has changed about that sort of header value。That。

We are now tagging， but it's maybe not quite the same anymore。

Anyone notice anything weird happened there？Yeah， go pray it。Yeah。

 we lost some bits off the top there。 We have experienced overflow。

 And so another activity in two activities from now is gonna help us wrestle with。

 what does that mean for us specifically in the context of numbers for booleans。

 we're not really gonna be worried about it because we have only those one and0 there。

 We're just not gonna be running into that。 But for numbers， this is going to matter。 So okay。

 now let's go ahead and turn to checking the tag。 So here。

 this was the thing that we are coming up with where we're like， wow。

 it's kind of weird that we're doing this thing where we're actually like blanking out everything except the tag。

 It's really weird that our mask is actually just those numbers that are appearing in the tag slot and not sort of the whole rest of the 64 B。

 But oh， this is because we're going to actually do some checking of the tag to see if we have actually landed on something that has the tag we want。

 This is the kind of process that we would do for trying to figure out。

 do we want to print this as a unicorn。 do we want to print this as a number。

 And so here if we go ahead and just and with our oops， let's bring the。😊，Thing back。

 if we want to go ahead and just and。With the mask。Then we will go ahead and get zeros here。

 101 here， and we will be able to see that， okay， yep。

 this entire number is exactly the same as our unicorn tag and therefore this is indeed a value that has type unicorn。

So that's where we've landed on how we're actually using our tags。

 how we're actually doing all of this shifting and ending in ordering in order to use these funny values we've introduced。

 It's nothing fancy it's just going ahead and shifting over our value and then going ahead and applying this tag that is going to tell us in the future what is the type associated with value with this value as we're sort of passing it around in our compiled code。

Please。Absolutely， so the thing that we did was we said， okay。

 I'm going to go ahead and end with this value right。

 and so that means that we are going to just blank out everything except the things that have ones in the mask right everything else becomes zeros and so immediately even though there was a one here。

 we blank that out， we go ahead and just blank out everything except these last digits。

 the last digits remain as they were up here。And what's interesting to us about that。

 the reason we care about that is because we are going to then compare this whole value with the unicorn tag。

 and we want to figure out if that's the same as the unicorn tag in order to figure out if this original thing that we were originally looking at。

 in order to figure out if that was a unicorn value。Yeah。

 so if you remember what we talked about on Tuesday， the same way that we can write。

To mean the exact same thing as 345。That's exactly where it is's the exact same thing， but in binary。

Great question。All right， are we ready for our next activity？Fabulous， let's do it。All right， so now。

We're finally going to think about why would we pick specific tags， not a deep compilers topic。

 we won't spend too long in it， but I do want us to just think through sort of how our decisions are having implications for our later decisions。

 And so the thing that Im I'm talking us through right now is let's say that we have been told that this is going to be the tag that we should use for numbers right we are going to be using the single digit zero for numbers for some reason right。

And now， in the course of adding a bunch of new features into our language。

 we realize that for some reason， we're going to need a bunch of tags to sorry。

 a bunch of types to all have tags that only have exactly three Bs， specifically for strings。

 functions， pairs and vectors。 this part is true。 We are， in fact。

 going to need tags for all of these that have only three Bs。 So that part， three or fewer。

 So that is actually going to turn out to be true。So what I want you to now go through with folks nearby is for about two minutes。

 I want you to figure out， given this constraint that numb is going to be just one single digit zero。

 what can we actually use for strings， functions， pairs。

 and vectors that is only going to be three or fewer？

So here's one thing I'm already hearing a lot that I'm liking。

 which is people recognizing that anything that ends in 10 is going to be off limits right because that's going to look like a number。

 so let's cross those out right off the bat and then I'll let you keep brainstorming。おごしいしし。

Basically， there's like there's slight variations of that one answer。All right。

 here's the next reasoning I'm hearing people go through， so I'm hearing people say， well。

 let's try putting strings here whoop now everything that's got ones at the end is off limits。

 which is to say everything right like that's all the rest so we better not put strings there so that means we can't use or put in fact anything there so that means we can't use this length one tag either。

All right， keep brainstorming。All right。Let's finish this out because I think we've sort of started to figure it out。

 So here， let's say we go ahead。 We try to put string in here， right， Okay， well。

 now the things that have01 at the end are off limit。 So let's cross that out， let's cross that out。

 We are now left with a pretty difficult situation because now if we try to put functions here。

 right， This can be our function tag。 Well， now that one has to go out of bound。

 That one has to go out of bound， right， because they still share that end So okay， let's back up。

 let's back up。 And in fact， we're gonna find the same thing with all of our， our。Length to tags。

 So let's cross out both of those。 And instead， what we can do is say， okay， this can be string。

This can be function。This can be pair。And this can be vector。So okay， that's a satisfying solution。

I now want you to go ahead and with the folks nearby。

 figure out what tag should we use for Booles now that we have settled on these five tags。那多。Okay。

 so hum if you think this task is possible？H if you think this task is impossible？Great work。

 everybody。 Right， Yeah， there is no way for us to do this。

 given the constraints that I have laid out， right， So basically， say we have a value like。

This that we intend to be the value true， right， That is， in fact。

 how we would represent the value true in our compiler。

 But then also say that somewhere down the line， we have something that's like 1，0，0，1，1。

 And we intend this to be a vector。 And so we go ahead and we sorry， let's see。 what would it be。

 We would have。Do I have this wrong yet， okay。Yeah， we intend this to be a vector。

 And so what we do is we go ahead and we make three spaces next to it。 We add in the tag for vectors。

 And now these look。The same from the perspective of something that's trying to figure out if this is the Boolean value true or if this is a vector。

 right， So regardless of whether we first check if it's a vector or we first check if it's a boolean。

 we are going to get it wrong some of the time， right， We'll either decide that that vector is。

 in fact， a boolean or we'll decide that the boolean is， in fact， a vector。

So that's not going to work for us。 So let's go ahead and actually change our constraints。

 Let's go ahead and say， now I want to have the nu tag B2 zeros。 So basically。

 what we had back in our actual。Compilr and I'll get rid of these other things and now I want you to go through and basically do this exact same process of deciding what tags to give everything。

Given that numb is this。Discuss for one minute。All right。

 go ahead and hum if you think this is possible。Oh， how if you think this is impossible？Okay。

 we're building confidence。 Let's work towards a solidr idea。All right， hum if you think possible。

H if you think impossible？Yeah， I agree， right so let's go ahead and just try out a fairly unstructured approach where we just start with the things that have three right。

 and so let's go ahead and put string。Fengsun。Pair。Vctor， right。

 And we know that none of those are going to conflict clash look the same because those are all ending with exactly three digits。

 neither of the this is not a case where both of the last two digits are0。

 So they're not going to look like numb。 And then we can go ahead and add a boolean tag。

 We could just go ahead and add this as a boolean tag。 But again。

 we don't actually need that much space for restoring Booles we're only going to store two Boolean values。

 And so we could just go ahead and use the exact same thing that we actually used in。

Our own compiler， which is this right And so this would mean that we can't just straight up use this tag。

 but we certainly could use the bit of it that doesn't actually clash， or we could use that。

 for example， or all these right so there's a bunch of other tags that sort of remain on the table if we use this slightly longer tag。

Okay， so hopefully we have the idea that sharing a suffix is bad in this situation right。

 we don't want the situation where you can confuse something that has a given type with something that has another type。

 So， for example， we have figured out that we absolutely cannot have any other type tags where the last two。

Digits are zeros。If we are actually trying to avoid clashing with numbers。If we know。Great question。

 Yeah， numb tag。 like tag length。 How important is it why would we choose a long tag versus a short tag。

 So obviously， in some cases， it does have big ramifications for what our programming language can do。

 So if we had made our numbers tag longer， then it's really gonna matter because it changes how many bits the integers are that we can store And so that's a case where it would really matter whether we're using a long tag or a short tag in general。

 if we're trying to use a short tag， it's probably so that we can have other other things represented at the sort of head of the register。

 right So that's probably something like the numbers case。

 if we're trying to do a long tag it is probably because we're trying to save some space for other tag that we might want to use down the line because we might want to evolve our programming language down the line。

 But yeah if we knew that these were absolutely the only types that we were ever gonna have in our language。

 and we never want to extend it ever again whatever。😊，Good question。

I think I understand the question you're asking。 So this question was broadly。

 could we have sort of suffixes of the tag representing some part of the information。

 And then as we're sort of going to the left， we're actually finding even more information。

 We're sort of getting something even more specialized about this。 absolutely。 Yeah， like we're。

 we're in charge。 we get to do what we want to do。 If that's what we want to do。We do it。Yes。

We could absolutely do that。 So this question was why not have basically a 63 bit taggged for booleanians because we know we only need one bit distort true versus false。

 Abolly， we could 100% do that。 It's annoying to type， and that's the only reason we're not doing it。

Other questions。Amazing， okay， let's go into one last little tag constraints activity。😊。

Quick humming pull。 Who here knows about Tu's compliment， hum for Yes。Home for no。

Totally fine if not。 You're really not gonna need to understand whos complement in order to do this class really at all。

 But real quick， let's just go through this activity where we are doing add one applied to negative1。

 and we're gonna do it with two alternative tagging schemes。

 So one where we have decided to sort of alter what we did in the actual compiler and we decided to just go ahead and put the tag at the left。

 and one where we did what we actually did in the compiler， which was to put the tag on the right。

 Go ahead and discuss for a minute。Alright， so hopefully we remember our addition and we figured out that there are some advantages to the approach that we've actually chosen。

 which is that overflow continues to work the way we want。

 even when we're dealing with with negative numbers so we are in fact getting back a zero at the end。

 which is what we should expect from adding one to negative one whereas over here we're maybe kind of getting that right like this part still looks like zero。

 but all of a sudden our tags changed This is not a number anymore right we would be going down that weird path of our compiler that we said we should never go down in the runtime where there's maybe well actually a couple things could happen。

 So it could happen that we're actually using that same tag to represent something else in which case all of a sudden our value is being treated some other way or it could be okay now we're actually seeing this situation which again。

 our programmer should never see So one of the advantages is we get to sort of keep overflow working the way we expect overflow to keep working。

I'm going to now take us into， if you recall where we actually left off with the compiler。

 we had left off having true and false， but that was the only thing we actually finished in Boolean land。

 If you recall from our interpreter， we had decided there are a couple other things we wanted to add。

 such as not。0 and none。 So let's go ahead and just real quick wrap up adding those to the compiler。

A bit more complicated than most of the other assembly we have generated。

 so I am going to actually have us look through some examples。So let's take a look。

Which one do we want to look at？Yeah， let's take a look at not true。

I'm going to try to take us through this pretty slowly just to sort of talk through what's happening because we are seeing some new stuff here right so if I go ahead and take my highlighter out。

 here's this thing， here's this thing what are we up to over here we've got this compare right so I'm going to go ahead and actually introduce us to a couple of new ideas here。

So these are the new instructions that we're interested in today。 We have comparison。We have set Z。

 So what is actually going on here。 Well， the real thing that's new is that we have added the concept of a flag。

Now a flag is not a register。But it is some state that is going to be changed by us running some particular assembly instructions。

And even though we won't read it out like we would read out the value stored in a register。

 it will then change the behavior of other instructions。

And so just to run us through a quick example with these two instructions。

 here's what's going to happen if we compare X and Y， right， We're going to go ahead and say that if。

X minus y is equal to0， which is to say that if x and y are the same the same bits stored in each of those registers。

 then we're going to go ahead and set the ZF flag。 I've put this nices little flag icon on our flags。

 then we're going to set the Zf flag to one。Otherwise。

 we're going to set the Zf flag to zero to indicate that they did not match。

Now this is weird because we can't just read off this one or0， right。

 it's in a flag and it's not a flag it's not a register。

 we can't just go in there and see what's in there。😡，It does， in fact。

 change the behavior of an instruction like set Z， right。

 So set Z is taking in a register as its argument as its opera and。 And then it's saying that if Z F。

Has been previously set to one by some prior instruction。

 then we're going to set the last byte of register R to1。

 otherwise we will set the last byte of register R to0。Now， under the surface。

 what's actually happening is all of the， the flags are being represented as teeny tiny portions of one register。

 It's all getting packed into one register to save space。 That's what's actually going on underneath。

 But for our purposes in this class， we don't even need to understand beyond that level of abstraction。

 We can just imagine， okay， there's a flag it's set or it's not set。Now do we have questions？

About this。We're feeling pretty comfy with these new instructions， we like them。I like them too。

 Okay， cool。 In that case， let's use them。 So we are， in fact。

 going to use these in order to implement our not construct in the compiler。 So first。

 let's just do our thing that we do where we run through the assembly that we are going to generate。

 and then we'll go through and actually write the part of the compiler that's going to generate them。

 So first things first。 Here we are。 We've got our move。 we are moving into RA X。

 the representation of true， the runtime representation of true。 If you remember that is this tag 2。

0s，51s， then one representing that is true instead of false。 So let's go ahead and write that in。😊。

My writing 1，2，3，4，5， great。 we've got true represented in there。

 And now we are going to use our new compare instruction to compare this representation of true with the representation。

Of false， because if you remember， we actually have not behaving exactly the same way as our sort of prior truthiness discussions。

 right， So only false gets treated as false。 Everything else is going to be treated as true。

 So we're going compare to false in order to decide what to do。 And in this case。

 we're going to go through。 we're going to say， well， that does not， in fact， look like false。

 And that means that the Z F flag is going to be set to 0。

 So at this point we have done those two instructions。

And now something really weird is going to happen。 We're going to say， blank out what's an RAX。

 right？ We previously had this true value there。 And now we're just， we're getting a rid of it。

 We're just popping in 0。So why is that？ Well， we're about to actually put something into RAX that is going to write into the last bite of it。

 if you remember what happens in set Z， it says it's going to write into the last bite of something。

 and we're about to try to represent the truth of whether true was false oop。

We're going to try to represent this information about whether our operaand was false inside RAX。

 so the first thing we need to do is blank out what's currently in RAX。

So we blank that out with our move Rx0。Okay， so that's blanked at what we previously had in there。

 And now when we run our set the RAX star， I put that star in there basically because if you look at the assembly that we actually generate。

 you'll see that we're doing something a little bit different than just saying RAX because we are intentionally addressing that last byte。

 but for our purposes it's totally fine to just think of this as addressing RAX the entire register。

So okay， we go ahead and we say set Z R X star， which means that everything is getting changed in there。

 except that it's not right。 We are writing zero into the last bite。 So okay。

 we have now written zero into the last bite， fantastic。

 We are now ready to do our shift right So this is just going go ahead and do our shifting for us and so we can go ahead and have 1。

2，3，4，5，67 with our0 at the front there。 but we've left room for the tag， fantastic。

 we have shifted it so that we're gonna have room for the tag。

 And now when we go ahead and or with our tag that we use for Booleions。

 we're gonna have0 another  two0s，1，2，3，4，5。😊，And with that。

 we have the runtime representation of false， which is in fact the value that we should expect to get back from not true。

Now I know that was a little bit fast， and this is still somewhat new concept。

 So let's also walk through what happens when we not false。

 but maybe a little bit more quickly this time。 So here we go， we start by representing false。

Right here in RX， great。 we've done that first instruction。 Let's compare it to false。

 What should happen to Zf。 Well， remember from before Zf is going to be set to one if the things were comparing are in fact equal and set to0 otherwise。

 So go ahead and hum if you think we should set Zf to1。H， if you think we should set Zf to0？Okay。

 great， yeah， right， these match right in the last time when we were comparing our representation of true。

 the thing that we had in here and we were comparing that to false。

 we said those do not match In this case， we're saying， hey， I'm comparing this to this。

 those do in fact match， which means our flag should get set to one。😊，So okay， great。

 We have found that those two things are， in fact， the same。 fantasticastic。

 Now we can go ahead and0 out R X， right， So again。

 we're just blanking it out so that we can write into that last bite。

 Let's right into that last bite。 We get one in there。 Great。 We've got one in there。 Now。

 let's go ahead and shift left，1，2，3，4， oops， sorry， the other way around。😊，One，2， three，4，5，6，7。

 fantastic。 we've shifted at  seven。 Now we can go ahead and apply the tag， let's do one。One， two。

 three， four， five， fantasticastic。 we've got our tag on。

 and now we are ready to return control to our runtime and what we actually have inside RAX is the runtime representation of troop。

 which is to say exactly what we expect to get back from running not false。Yes。Just so we can。

Exactly that question was why are we doing this zeroing out of what's in reX。

 iss it just so that we can zero everything out before we put that piece of information from our flag in。

 and that's exactly why right we don't want to have some random stuff hanging out off to the left and then change that last by We want to just have everything zeroed out put in the last bite。

Yeah。Great question。Are there questions about this or we're feeling okay？Okay。

 if we like where this is heading， then we will take our five minute break， we'll come back at 426。

 and then we will actually change the compiler to do this。Yeah， what's up？

This what's actually being done。There's like shifting value。

figure out It totally depends on the particular language that you are， well in fact。

 it doesn't even depend on the language， it depends on the particular language implementation。

It dependss on the language implementation。Yeah， like we get to decide。 No。

 Ocal is using one extra bit inside their integers for something that we will talk about later in。

The semester， So we're going to talk about garbage collection。

 And so the fact that O Camel has 63 bit ins is because they are using one of the bits for garbage collection。

Interesting because like I was wondering when you like run the program like see program。

And you would expect to register value to me。I don't know， like 16。

 you wouldnt see 16 something but shift。 Yeah So is there like any like modern languages that use like shifting。

Because it would be pretty rare， honestly， we lose a lot of space。You live without arranged。Yeah。

I mean。Again， there's thousands of language implementations out there。

 like there certainly are ones that are doing this， but in general。

One of the huge things that you're trying to do， and in fact。

 there are people who argue for static typing specifically of being able to do type erasure。

 so with type erasure， the idea is that you're not keeping track of any type information at runtime。

At runtime at all right like the whole point with static typing is that basically at the end of compilation。

 you don't need that information anymore you already figured out a compile time and you've now changed the program to actually do the right thing based on knowing the right type at that time so like it wouldn't ever make sense to have a scheme like this for an implementation of OKM。

Because you know all of the types。At compile time， you don't need to know them at runtime。

So is there a reason why？We're talking about like， tagging， should they。

so tagging is common right so again OM has 63 bit integers。

 that's because one of the bits is being used for something else right so I'm basically trying to give you a sense of the space of possibilities that is open to you as a compiler designer and to emphasize the fact that you don't need to you know even if you have an idea in your head of what would be an intuitive way to represent something in 64 bits。

 you don't necessarily need to actually do that。You have freedom to sort of manipulate that。

 and it's sort of one of the things that's on the menu of options。Thank you yeah。

 this is also going to become relevant down the line when we start talking about functions and first class functions and we'll sort of revisit this general scheme at that time。

Thank you。All right， so here's our friendly neighborhood compiler that we have been playing around with。

 The only thing that I have changed so far is I have added in this match case for not。😊。

And I've figured that the first thing we're going to want to do is make sure that whatever assembly we need to omit in order to be sure that the value associated with our argument to not。

Whatever assembly we need to admit in order to get the value associated with that into RAX。

 we had better admit that first。 And so now at this stage where we pick up。

The value associated with Arg should appear inside R X。 So given that knowledge。

 what do we want to do next， Well， let's do that comparison that we talked about。

Right so we want to compare whatever is in REX2。Now， I don't know about you。

 but I'm personally starting to get pretty annoyed with having to write that out every time。 like。

 okay， we get it。 We are shifting left in order to leave space for the Boolean tag。

 And then we're oing it with the Boolean tag in order to get that。 That's fine。

 But this is getting a little bit boring to do this over and over again。

 What if we make ourselves a little bit of a helper function。😊，So， let's go ahead。Copy that。

 And let's make our helper function。 Let's do， let operaand。Of播。can take a bull as an argument。

And it will look quite similar to what we've already been typing。

 but it's going to be a tiny bit different， right， so we don't want to just have it be 0 every time。

 oops， and I have to spell operaand right。We don't want to just be 0 every time。

 We want it to be a Boolean that depends on this B that we're getting as input。 So if B。

 then one else0。 So okay， that feels a little bit nicer and cleaner to me。And also。

 now I'm starting to think that we could do something similar for numbers。 But okay， first。

 let's use opera and of Bo a couple of times。 So let's get rid of。Our one that we've got there。

And let's do opera brand a Bo troop。Good， that looks better。And let's do opera random of bo。Fse。

For making false。 Okay， that's starting to look nicer。 And here we're comparing to false， right。

 That's because we know that the only thing that should behave like false is false itself。

 So let's do opera end of blue false。 Okay， nice， we have something a little bit cleaner。

 We can sort of read more closely。 What our compilers are actually doing。

 Let's do a similar thing for numbers。Let's do operaand of nu。And we can do X。

 and that can be our int。 And then we can just go ahead and have that be the thing。That we are。

Notifying。Great， Prince seem to be behaving。 So now let's go ahead and say， okay， well， this。

 instead of being， you can see that right here， we actually didn't do the thing where we actually applied the number tag because we knew it was zeros。

 I'm doing it here just to actually，op， nope， I'm doing bull tag。 That's bad。 numbum shift。 numb tag。

I'm still doing it with the the tag here， even though we know that actually makes no difference just to sort of make it clear to us as readers。

 what is happening there。 That is just to communicate with the humans reading this code。

 this is not because it actually has an effect。So now let's go ahead and do operaand of nu。

Applied to one。Same deal down below。And I think up here， we've got to apply it to N。Okay。

So that's starting to look a little bit cleaner。 We're not having to do all these shifts and tags and whatever directly in the program。

 So that's a little bit nicer。 Great， So now we've gone ahead。 We've done our comparison to false。

 Does anyone remember what we do next。We saw the code that comes out the other end。

 but we haven't actually generated it yet。So pretty soon。

 were want to go going to want to go ahead and put in something based on the Z F flag into R E X。

 And so we decided better actually go ahead and zero that out first。 So let's just move。Into RA X。

 let's just move0。 right， We're just trying to make sure that that's all zeroed out before we start putting messing around with that last bitete。

 And now we can mess around with that last bite。 Let's go ahead and do seti。Apply to ReX。Okay， cool。

 We're getting closer。 We're not quite there yet because now we actually need to go ahead and do the thing that we do in order to represent that this is a boolean。

 So now let's go ahead and do。Our left shift apply that to RAX。

And the amount we want to do is our Boolean shift， right， so seven。

And then we want to go ahead and or with the tag。 So let's do again， RAX。And let's do the bowl tag。

Now okay。Last time that we were chatting through all this stuff。

 we chatted about whether this left shift is happening at compile time or runtime。

So I want us to ask the equivalent question here， so is this left shift？

Happening at compile time or runtime don't answer yet。

 go ahead and discuss with someone nearby for 30 seconds。All right。

 go ahead and hum if you think this is happening at compile time。

Hum if you think this is happening at runtime？I totally agree right and to a certain extent we can tell just by figuring out what language is in charge of this right So if we look up here。

 we're seeing that okay， this left shift is being done with the Ocal operation for left shifting right this left shift is being done with the assembly operation for left shifting right the thing that is running at compile time is our Ocal program the thing that is running at runtime is our assembly program and so we can use that just to think through okay should this be happening at compile time versus should this be happening at runtime。

Okay。Questions we're feeling good with that so far。Yes。😊，Its say like their value is shifting。How。

 how would brother。How would it like shift？I think this question is what if？The argument to。

One of these helpers was only known at runtime and not at compile time。

 Could we then run these helpers。 Could we do that computation at compile time。

I will set that question to the class for a moment， I want you to think through。

 could we ever use these helpers for a value that we don't know at compile time？

Go ahead and chat it out for half a minute。All right， so it's okay if you don't know this， but hum。

 if you think， yes， we can use this on a value that we don't actually know at compile time。

 hum for yes。Hum for no。Yeah， this is kind of mind bendy， right like it is so weird。

 but if we sort of step back for a moment and we just think about the fact that this is just a program implemented in Oaml。

And what we're going to do with this program is provide it to the OKMl compiler in order to run it。

 right， Could we just run this computation not knowing what our argument is。No。

 right like if we are gonna to be actually executing this program on a value。

 we have to know what that value is， which means we are never gonna to be in this situation in answer to the original question。

 we're never going to be in the situation where we can use Ocals implementation of left shift on a value that we don't know until runtime We can use Ocal's version of leftshift on values that we know we are already confident of at compile time So as an example of the places where we've used it here are some places where we just know that it's always going to be one right Here's a place where it's not necessarily always going to be the same number right we can see that this is n that's going in but we have read that value out from the program text so that value is known at compile time。

 We're not going to need to wait until runtime to figure out what that n is Now in contrast。

 this is an example of a case where we are not going to know what we are applying。

ing this left shift to until execution time until runtime。

 right Because in order to figure out what value we are running that left shift on。

 we have first had to do this comparison at runtime。

 And then we had to use set Z to put something into RX at runtime。

 We only figure out what that value is going be that we should left shift at runtime。

 And so that's exactly the reason why we chose to do this with the assembly at runtime instead of with the Ocal implementation。

 When we can do something at run sorry compile time with the Ocal， we prefer to do that。

 because that means we get to do it just once， and then we can run the program a million times without having to repeat that work。

 So in general， if we can get work done at compile time， we prefer to get worked on at compile time。

 But sometimes we just can't。 and that's exactly this situation。So this question was， okay。

 I's gonna to throw an error。 if you're trying to use a dynamic value in an argument to one of these。

 How would we even have a dynamic value？ Like， what would you mean when you say dynamic value。Right。

 like this is just an Ocal program。 Like if we have a value that we're providing as an argument to a function。

It's just got to actually be a value。Like we are expecting to get an int into this one or Boolean into that one。

That's what we're expecting to get in。Yeah， kind of mind， Beny。

 I do encourage folks to sort of play around with this at home。

 though the compiler is a really good place for sort of exploring these， these ideas。

Other questions we're feeling pretty okay so far about our。Our implementation of not。Okay， cool。Well。

 let's go ahead and in that case， turn to the next construct that we want to implement。

 which is to say no question mark。And the only thing I'm not gonna to actually run us through this because I think it's gonna be pretty obvious what we're。

 well， do we want to do， You know what， before we move to numb us， actually。

 let's finish up 0 question mark first， because that's gonna be actually super similar to not。 right。

 If you think about what's going to happen in0 question mark， it's going to look so， so similar。

 except that。The thing we're going to put inside REX that we want to compare to instead of false is going to be operaand of numb。

0。Right， that's the only thing that is going to change between these two， which makes me think， okay。

 I would really like to just sort of be able to reuse these。

 This doesn't seem like something I need to be repeating multiple times。

 So let's just make ourselves a convenient little list of instructions that we can think about what role they actually play。

 but we're definitely gonna want to use them repeatedly。

 So let's go ahead and give a name to not quite all of these， but almost all of these。 So let's do。

Let。Z F to bo， right， We're actually giving a pretty informative name， directive list。Okay， great。

 let's get rid of this comparison because we don't always want to compare it to zero。

And this will just be some instructions that we can use。 So why am I calling this Z F to bo。

RightThe assumption is that right before this sort of first instruction this list。

 we have gone ahead and done a comparison。 We don't know to what， but a comparison。

 and then we want to blank out R E X， set the last bite of R X according to what got changed in Z F。

 and then go ahead and do our left shift to turn it into a boole and a tagged boole and our left shift followed by our tagging。

And so first quick understanding question here， go ahead and chat with someone nearby for 10 seconds。

 Is this a function。All right。 how if you think this is a function？

How if you think it's not a function。Oh， uncertainty。 Yeah， so does this take any arguments。

I'm hearing that we don't have arguments。 I agree。 Yeah， this is not actually function。 right。

 There's nothing varying here。 We're not actually changing anything。

 This is just a convenient name for a fixed list of directives。

 This is gonna be the exact same list of directives every time， every single time that we use it。

 We don't need to change anything in here in order to actually convert whatever is currently in Z F into a Boolean。

 So we're gonna be able to just reuse this exact same sort of string of directives。

Is there such a thing as a function with no arguments？Mathematically， that would not be a function。

But， you know， certainly， there are many programming languages that let you define a function that accepts you know。

 no arguments and still has a function body。 And you're still using all the same syntax you would use to create a function。

 for sure。Yeah。I love this。 Isn't this still a function just because we're in a functional language。

 I would call this an expression more than a function， but I do like where your head's at。😊。

Other questions？Okay， cool。In that case， let's go ahead and actually use this。

 So we will keep the comparison that we've got in there already， right。

 We want to first compare to false。 But once we have compared to false， we can go ahead and。

Paste in our Z F tuboo。That looks pretty good to me。 I like where we're going。

 Let's go ahead and do the same thing down here。 We still want to compare to 0。

 But at the end of that， we want to go ahead and paste in our Z F tooo。😊。

And that's starting to look pretty good。Now， there is still one more thing that we haven't actually implemented yet。

And that is our numb question mark。 Let's maybe first make sure that this all works the way we want it to。

 And then we can continue on to our numb question mark。 So let's。Get how to hear。Let's do。

What should we like， maybe。You can do not true。False， nice。 We can do not false。We can do。

Cero falses。Great， so far， everything looks pretty good。

Let's go ahead and do one last thing that's using our new instructions， and that will be。Our numb。

Now。It's not too much different， really， in many ways， from what we have seen already with 0 and。Not。

 but we're not doing the exact same thing of just quickly comparing to one value and then going and turning that into a Boolean。

 We're gonna have to do something a little bit different because we want to actually isolate that tag and then see if that tag is the same as something that we're trying to compare to。

 And so that's what we're gonna be doing right here。 So first。

 we've got our runtime representation of2， right， which as we recall， is 8。

 So now we're gonna go ahead and compare that Sorry， we're gonna go ahead and actually。

And that together。 So we've done our move R X 8。We're going to add that together with one1。

 Now I want everyone to pause and consider， remember our tagging activity from right at the beginning of class。

 Why are we ending with one，1。 Why would we be doing that。

 discuss for just 10 seconds with folks nearby。Alright。

 so hopefully we have remembered that this is our mask for numbers。

 This is the way we can blank out everything except those last two bits， right。

 So those last two bits will remain whatever they were before。

 but everything else will get blanked out。 And so that will leave us with this value at the end of our and。

 And now we're ready to see if what we're left with after blanking out everything except the tag is。

 in fact， the tag we were looking for。 right， So now we're ready to go ahead and actually compare with the number tag And in fact。

 in this case， it is going to be the same。 Very cool。 We see that Z F turns to one。

 We' have done our comparison。 Now we're ready to blank out whatever we have in R X before turns out that's actually doing the same thing we already had in there。

 but that's okay。 Now we can go ahead and set it based on what's in Z F。😊，We go ahead and do that。

 we can do our shift， leave a bunch of spaces。Did I get seven No that was six， Okay，7 great。

 and now we're ready to go ahead and tag it with our tag so we can see that that last process。

That we were doing looks a lot like what we did before when we were doing our classical Z F to bo transformation。

 But the thing that happened before was a little bit different because the first thing we did was blank out everything that was in the original value except for the tag portion so then we could compare directly to the tag。

 That's the main difference from what we were doing before with our comparison。

Questions about that before we code it up real quick in our compilr。Lovely， all right。

 let's swap to our compiler。So here we are back in compiler land。

 Let's go ahead and implement this last little Boolean function thing that we are creating。

 So we're going have something for。No question mark， we'll take an argument。

 what's the first thing we're probably going to want to do while we're going to want to get the representation of the argument into RAX？

That looks good to me。 What do we want to do next？ Well。

 now we want to go ahead and do that ending with the mask。 That's the first thing that we did in our。

 in our sample。 So let's do and。😊，RX。Noun mask。So far so good。 What next？

What do we want to compare against， we want to do that comparison。For sure。

 we want to do that comparison。ButWhat do we want to compare with？I'm hearing our two zeros， right。

 the thing that represents our numbers tag absolutely， so let's do that。

And let's spell REX with the capital R so that it's happy。And what do we want to do after that。

 right， at that point， we have changed it。 So that's what's in Z F is going to represent whether we actually saw the number tag at the end。

 So what would be a good thing to do next。 We can meet Okay， great So I'm hearing Z F to bo。

 Let's do it。C， F Tbu。We're just doing that exact same thing we were doing before where we blank out RAX。

 we go ahead and use whatever we had in ZF in order to set the last by of RAX， we do our left shift。

 we do our ore。So that's how we can go ahead and turn this sort of comparison with the number tag into a Boolean。

 So let's quickly run this and make sure it behaves nicely。

 And then we can go ahead and answer any questions that we have about that。So， compile。Cun。

 and let's run。No question mark true。Our compiler says that true is not a number。

 What does it think about the number 5。Oh， it thinks that is a number。

 So I'm feeling pretty good about what our assembly is telling us about what is a number versus what is not a number。

 So we have reached the point where we have， in fact。

 implemented numbers and Booleions and our compiler， and we can mess around with them。

 We can do things with them。😊，What kind of questions are coming up？Okay， lovely。

 if they come up as we go along， that's all right。 So let's now start thinking about what we could do next。

 We now have this idea of comparison that is letting us sort of do different things based on something that we're figuring out at runtime。

 not just based on things that we're figuring out at compile time。

 that might start to get you thinking to yourself。 I can think of something in the programming languages that I am familiar with that might be a little bit like that。

 Perhaps I might think to myself of。Conditionals。Right。

 we have those in most of the languages we like to use。 They are pretty useful。 We use them a lot。

And so we are in fact going to next add conditionals and so this is going to look probably a lot like what you would expect just based on seeing this。

 so I'm going to write down a couple of programs that use this conditional and I'm going to ask you to make some predictions about what it will do So let's go ahead and chat about if 1。

2，3。Go ahead and start chatting， and I'll also write down another one for you to play through。

All right， I think there are two reasonable outcomes for this first program。 So hum。

 if you think too。Home， if you think three。Cool， yeah， I agree。 That's going to be too。

 So why is that going to be too， Well， it's because of this right here， right。

 So anything that is not false is going to behave as true。

 That was what we decided for not and we're going to do the exact same behavior for our conditions。

So if we have the specific value， false， the Boolean false。

 that's the condition where we're going to go down the false case， Anything else， true case。

What about here， what do we think about for this following program？Anyone want to shout it out？

I feel like that's gonna to be 5。 Let's do 5。 Yeah， that looks great to me。

 So the only thing to call out here that we want to be a little bit careful with is let's say that instead of this。

 which is just sort of a pretty small value wouldn't take us a long time to compute。

 Let's say this is something that would run for a day。😊，And let's say that the。

 the condition is the same， right， We're going to actually end up returning the value associated with that。

 Would I be happy if we end up evaluating both that and that。😊，Yeah。

 I think I probably would not be super happy with that。

And so that is going to lead to our next key assembly idea。I'm hearing it in the audience。 Yeah。

 absolutely。 So let's go ahead and meet some new instructions。 We are going to have access to jumps。

 Oh my gosh， it's wild。 And so if we take a look at the programs weve been generating up to this point。

 Let me try to show us a program real quick。 Oh， this is kind of a boring program。😊，Well， let's see。

Let's see if we can get a program that's a little more interesting， don't save。あ。

That should be an interesting program， I think。Okay， great。

 So one thing that's kind of weird about this program。Is it's just all kind of in a straight line。

 right？ in fact， the official fancy programming languages term for this kind of program is a straight line program。

Right very fancy official term， just meaning that we're going to do this thing and then we're going to do that thing and then we're going to do that thing and then we're going to do that thing。

 and we're just going to go through it in a line。Not super exciting for us。

 We might want to be able to do other things。 And so now， finally。

 we are going to go ahead and get the instructions that let us do other things。😊。

And so this is still reasoning with that flag's idea that we introduced earlier today right and it's saying that if we run this instruction。

 JZ， if we run this instruction at the time when ZF is set to one。

 then we are going to go ahead and jump to the label L。😊。

And then this one is just like you're always gonna jump。 You're jumping every time。

 So that one's not doing anything conditional， but it is gonna be able to sort of move us up and down in our sequence of assembly instruction。

 So even though we are still having to write out our assembly instructions sort of all in a line。

 right， we're still going to see it sort of laid out all in a row。

 We do now have a way to move around within them by using these jumps。Great question。

 Do we know what a label is。 We do， in fact， know what a label is。

 So all this time we've been using exactly one label。

 So this label entry was how our runtime knew where to go in order to get the body of entry right So down here。

 we were going ahead and saying call entry， call entry and we're saying we're not telling you what entry is。

 but it's going to be provided externally。 And the way that it actually found it was by going into our program。

 our assembly and finding that label entry。 So yeah。

 that we have already been using just a single label Now we're going to start adding more label。😊，Oh。

 great question。 So does the name of the label in our assembly need to match the label that we see in the runtime？

 Yes， absolutely。 So in the the labels that we're gonna to be using going forward。

 our runtime is mostly not going to be referring to the labels that we are using internally。

 And so the sort of broader lesson here isn't that it needs to match with the runtime。

 but that it needs to match with whatever is going to try to jump to the label。

 So at some point we are doing something that adds a label into our our assembly instructions it puts it somewhere in the sequence and that needs to match with whatever is going to be calling it So whatever it is that's going to be trying to jump there。

 calling is actually the wrong terminology there， but that's something thats sort of rings for people right So whatever it is's going to be trying to jump to that label had better be using the same string as the label that actually got added in there。

😊，Was there a question over there？No， okay， we're feeling good。Cool。

 so these are our new instructions。 Fastic。 How are we gonna use them。 Well， we have three minutes。

 which I think is just enough time for us to add our if expressions to the interpreter。

 I'm gonna be honest， We're not going get to doing it in the compiler today。

 But I think we can do the interpreter because we can basically just piggyback off of how O Camel already does it。

 right， So let's do basically the same thing that we would expect。 Let's do。😊，Same if。Test expert。

Then X， sorry， I shouldn't have put an R there。 I want to be consistent。 then X else X。Great。

 that looks pretty good。 I like where we're headed。

 Let's go ahead and make sure that that gives us something reasonable back。

 What is it probably going be。 Well， it's probably going to actually be using the same expression that or sort of the equivalent expression in Ocal。

 which is to say or if， So if interpret， yes。😊。

![](img/06b64ed60f73afee8ac480659611e102_13.png)

Oh， I'm so sorry。 Oh my gosh。 Yeah， you have to yell out at me when when I switch to the computer。

 you can't see it。 I'm so sorry。 I'm gonna do that all the time throughout the semester。 Please。

 please please yell at me。 Okay， sorry， allright， let me talk us back through what we have been doing over here。

 which is basically just saying， okay， if we see the symbol if followed by one expression then another expression then another expression。

 we're gonna want to go ahead and actually first figure out what is the value associated with evaluating the test expression。

 So let's do inter X applied to test X。 if we see that that is booley and false。

 the only thing that is falsey。😊。

![](img/06b64ed60f73afee8ac480659611e102_15.png)

So if that isoley and false， then interpret X， let's apply that to the else X。 On the other hand。

 in any other situation， if it's anything other than booleyan false。

 then we do want to go ahead and interpret X。Then X。Okay。

 so let's just real quick make sure it works。 I'm so sorry for typing without y'all。

 I do forget what y'all can see。 I'm like， I can see it。Doesn't help okay， so let's see。If one， two。

 three。不。Great， we've got two back。 What if we do false。Great， what if we do。Plus 4 or5。Oops。

 I forgot we don't have that yet。 Add 1，5。 We'll get that soon。 Don't worry。 Okay， great。

 we've we've got it working。 So in our interpreter。

 we now have it's real quick because we're just sort of piggybacking on what O Mill does for if expressions。

 But it's gonna be a little more fun in compilers land。 So we'll get to that next week。

 I look forward to seeing you then。😊，拜好。诶て。Hi，ello。How are we doing？Absolutely， yes。

 I think Im still like I don't think I write understanding of what。Canも built。

Orre they compiled time functions specific。So when we run our file， compile。m， right？

This is just a program。Right， as far as the Ocael compiler is concerned。

That's just an Ocael program and so everything that we run when we。



![](img/06b64ed60f73afee8ac480659611e102_17.png)
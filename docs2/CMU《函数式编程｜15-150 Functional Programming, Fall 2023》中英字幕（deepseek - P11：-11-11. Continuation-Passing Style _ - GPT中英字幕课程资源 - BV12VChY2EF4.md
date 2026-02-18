# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P11：-11-11. Continuation-Passing Style _ - GPT中英字幕课程资源 - BV12VChY2EF4

Alright， we're going get started with continuation， passing style。 Okay， so here's lamentte code。

 I presume most of you know by now， if you， if you need to remember this。

 you can just look up the slide online。 So I'll just skip through this。 anyways。😊，Okay。

 we're gonna be talking about this idea of pipelines。 If you were not clear on pipe。

 the usage of the pipe operator from last lecture， we will be using it a lot today。 Alright。

 we'll talk about what this thing called continuation passing style even isops。

 and then we're gonna be talking about how we can translate functions into a style that is this CP style。

 and then we'll talk about the implications for control flow。 Okay， but that's our schedule。 So， oh。

 my goodness。right， so this is gonna be embarrassing because here's what I' gonna have to do really fast。

😊，So。Alright， anyways， does anyone have any questions about the homework about the class。

 about this thing called CP。 What we're doing is we're waiting for my lotx to compile because I forgot to compile the lecture slide specific version before this lecture。

😊，And that will take a pretty second， like around 40 seconds。

 But last time we talked about higher order functions， right， and we talked about staging。

 which doesn't have a whole lot to do with this lecture。

 But what's important is the fact that we did it。 And what's also important is the fact that。

We can do currying， right， and we can have map and fold， and we can have these pipes。

 which let us sequence operations in a way that's more particular。 That's nicer to read。

 If I have F of G of X instead， I can write X， pipe G， pipe F， right。

 And that's just a nicer way for me to structure my computations。

 We're gonna be talking about another way we can kind of do that。😊，So here's the idea。

 We defined pipe last lecture as such， right？And this lets us produce code like this。

 I take the the the list 1，2，3。 I pipe it into map In 2 string。

 right which means I apply map In 2 string to this list。 So I get the list string 1。

 string 2 string 3。 Then I pipe that into fold R， Can someone actually tell me what this does。

 Does anyone have any hypothesises or what this does。Yes，limd by delimd by commas。 Actually。

 a weird corerk of that is that it actually produce， itll actually produce one comma 2 comma，3 comma。

😊，Which is unfortunate， but sometimes that happens。 It's not important what this does。

 But the important part is that we can pipe these operators like this that lets us read it in a nicer way。

 It lets us read it linearly， right from top to bottom。And this works pretty well for our purposes。

 But what if I change up the problem a little bit on you。 Okay。

 what if I have a list of strings and I want to turn the main integers and I want to get the average。

 Okay， like I'm summing up your grades， for instance， Find the average of your grades。 Well。

 suppose to get a string 1 string，2 string。 Well， it's now of the strings。 Okay，1，2 and3。

 Here's what I'm gonna do。 I'm going to map them with the function in dot from string。

 which unfortunately returns an option。 So I'm going to use option dot。 Don't do this。

't that function just takes things out of some and raises an exception if it's none。

 I know that this won't happen， but please don't actually ever do this。

 Okay so now I have at this point， I have the list 1，2，3， right。

 and then I pipe it into a land expression。 I bind it to the name L。I do fold R up plus 0。

 which is the sum function， right， So I sum up everything in the list。

And then I divide it by the length of that list L。 I everyone clear on why this should produce the average of all of these numbers interpreted as integers。

So this is one thing I can do。 But here's my claim to you。

 This is gross because I kind of hate having to write this lambda that I pipe into。 right。

 when I write map into drum string， I can write it without the lambmbda。

 I could write it with the lambda， but I don't have to， okay。

We're gonna see how we can improve upon this by making our computations more explicit because one nice thing about piping is that every operation comes after each other。

 I have this。 Then I do my map。 Then I do my map。 And then here I do what do I do。

 I have to go read the body of this。 And I figure out， oh， it's a div。 So I do the full。

 and then I do the length。 and then I do the div。 It's not clear it's nonexpl。

 when I write code like this， it's up to the order of operations of the Sl compiler as to which operation happens first。

 I don't know which one these happens first。 You know。

 I told you that we evaluate tus and left to right， right。

 but you have to rely on your knowledge of that。 whereas here I know that I must do the map and then the other map。

 Okay， there missing my point like it's more explicit to do this。

 Then it is like bind it to Lada and then just do whatever on the inside。

 so we're gonna try and reco that advantage by making it a very explicit step where every line is its own operation。

 Allright。😊，And， you know， we had to， also another comment is like， we could。

 we had to write it this way becauseuse we need to reuse the list L inside of this length list length。

 I couldn't like pipe it immediately into full R because then I'd lose the list， okay。

Remember the promise。 Okay， Allright， can we do better is the question。 And the answer， Oh my God is。

 yes， we can。 Alright， here's what we're gonna do。😊，Remember the idea of Ada expansion。

 which means that if I have a function F。That is extensionally equivalent to F N X goes to F X for any function value or valuable function expression F。

 Okay， and you should believe me on this。 I just have introduced an argument and given it explicitly。

 But these two things are。Equivalent， okay， let's use that to explicitly call each of these things。

 Each of these lines a lambda geez。 I don't know if that says， but that's okay。

 We're gonna use this to call everything a lambda。And this looks scary。 Okay。

 so let's work through it。 Allright， What I have done is I have taken each previous line。

 and I've explicitly turned it into a land expression。 instead of， instead of map。Induct two string。

We know that this is actually extensionally equivalent to a land expression。 F M X goes to。

Map into two string。X， right， This is essentially equivalent。

 So I can just translate this to that by referential transparency。 So here that is all I've done。

 Okay， I introduce an explicit list L 1， which is what 1，2，3 strings are。

 And I gave it to map into our problem string。 Then I piped this whole result into another lambda that takes in that result and calls it L 2。

 So L1 is a string list。 L 2 is an int list。😊，Then I do map option do of L2。 And I pipe that into L。

 So now I get， actually， this is a in in option list。 and I get inlist。 Okay。

 and then here now we see every operation happens on a single line。1 line。

 I do the map into from string。1 line， I unpack the options。1 line， I sum1 line I get the length。

 and then the final line I divide。 Okay， all I'm doing is making this very， very explicit。😊。

Even though it's quite hard to read。Another comment about this is I've seen some people asking this on piazza。

 If I have something like F X。Pippe， GX， or any Iex operator。I'm used to this at this point。

 but this bears noting， when you want to read this。Infiix operators go last。

 That means that if I ever see like a large amount of， of in operators surrounded by other things。

 for instance， X cons， Y cons， Z or F X cons， G， Y cons， H， Z。 Okay。

 the way I read this is I read this as three groups of things。Because the in operators go last。

 So they always partition the other things。 Okay， that's the way you should think about it。

 At least in the absence of mixing several in operators。 But that bears noting， okay。

Is everyone relatively clear on what this says and what this is doing， I'm just， it's a different。

 I haven't introduced any special syntax。 It's just lands and pipes， okay。Okay。So we can do this。

 Allright， but we actually prefer to indent things a little bit differently。 Okay。

 I actually this is exactly equivalent。 I've just changed the indentation a little bit。

 So now when I do 1，2，3， I pipe that into a lambda that has L1。 So I bind this to L1。

 Then I do the map into string L1。 And then I bind that to L2， and then so on and so forth。

 So the thing I'm binding it to is the end of the line on which it appears。

 Okay and is everyone relatively assured like this will produce the result of the total divided by the length。

 because of how I constructed this。 The advantage now is that I've explicitly named every single argument。

 and now I have free license to use this L twice。 now I now it's no big deal that I can do the list length of L。

 so this is these pipes are verbose， but they're more explicit is the idea。 Okay。

 but this is just equivalent to the previous。😊，Okay， and I already said that。 Okay。

 so this is nice in sequential。 And it doesn't rely on your intuition or your understanding of how S M L does things。

 It's just top down。 Okay， And in case you're having more trouble reading this。

 which I was concerned about。 I've， I furthermore made it like this， so。

The thing that you realize is that this is a gigantic lamb expression Every from this red left print to this red right print is just one big lambda expression that I'm putting it into。

 Okay， but the body of that land expression is map into from string L1。

 where I pipe that into yet another orange， very large lambda expression。😊，Whose body is。

 so on and so forth， Right， But these lambs are just containing each other。

 Theyre very large land expressions， but we're just evaluating the body。

 which is itself like a nested land expression panadial。 Okay。

 I thought this might be easier for you to read。 given how we traditionally indent things， Okay。

 but this is exactly the same thing as this。 I've just indented them slightly differently。 okay。😊。

Yes。Yes， yes。 So I haven't exactly applied this books because then I would have just piped into F N X goes to map in do Brostr X。

 I've actually made it a little bit more complicated because I wanted to surround this entire piping expression。

😊，So this is not the exact equivalentence I'm applying or correct about that。

 but it's similar in intention where it'll maintain equivalence。 Yeah， essentially。

 you can think of it as these， these pipes left associate。

 It's like Pars pipe map end uping pipe map option develop Pars。 But here actually。

 what I've done is I've right associated it。 It doesn't actually matter。 But I have for， I think。

 readability purposes。 This makes it easier to read。😊，Okay， but good point。 Okay。

 but we're gonna move on， alright。Okay， so this is just a very large lamb expression。 Okay。

 it's a very large sequence of operations。 but let's move on。 So， let's， but let's revisit this。

 right。😊，Every time I'm doing a thing， it's destined to be piped into a lambda that does the next thing。

 right， that's， that's what I this， this sort of protocol I've adopted。 But why should I do that。

 Because I kind of want to save on these characters。 I don't want tona have to pipe explicitly。

 So what if here's an idea。Here's an idea for you。What if instead of having to do？F， X， Y， pipe。

 this function。 And we're gonna call it K for a mysterious reason。 Okay。

 what if instead we had a it's this， right， we compute this。 We go this to a value。

 and then we go to K of V， right？ That's the way that this works。One if instead of that we did this。

😡，F prime X， Y K。K is now a cur parameter to this new function called F prime， where F prime has the。

まあ。That F prime X， Y， K should be extensionally equivalent to K。Of F X，Y。

Do you agree with me that if this law holds， then we could write this instead of that？

If this function were defined in a way that F prime。

 given the the next function to do K was equivalent to k of its result。This would be okay to do。

 by definition， I would actually step the definition of pipe and we'd see that this would be the same thing as what this is equivalent to。

 right。So we're gonna roll with it。 I'm not gonna tell you why yet， but we're gonna roll with it。

 Okay， and we're just gonna get rid of these pipes。

 We're gonna make each of these lambdas an argument to the function that appears before it。 Okay。

 and what it look like is itll look like this。 we're gonna call such a function cool。 Okay。

 a function that takes in this K and is equivalent to K called on this original function is called a cool function。

😊，And I hope you believe me that all I've done is I've changed these names to cool。

 and I've eliminated the pipes。 So now it is。Sorry， this pipe should still be there。 But now it is。

 I pipe into this Lambda。 What's the body of the Lambda。 It's map cool， given this argument。

 given this list and given this argument， not piped into this lambda， given the lambda as argument。

 okay。😊，And our protocol is just that hopefully， since Mapcool is defined in this way， right。

 we can literally use referential transparency to show that this is equivalent to what I had before because we have a law saying Mapcool F LK is equal to literally map F L pipe K K apply to map F L Does everyone believe me that if I apply these equivalences。

 If I replace every instance of map coolol folder Co length cool with the right hand sides。

 we get exactly what we had on the previous slide。😊，You can take a second to think that through， yes。

The Y will come late， I'm not claiming readability yet the Y will come late， the why is the hard one。

 yes。😡，K is not argument here， sorry， that should be an argument， you're correct。佢头佢头。Okay， okay。

 so I just want you to follow me along why this should happen， Yes， why should be true。Yes。

 because functions are values。 So this K is indeed that landverse。Yep， yeah。

 So if we apply equivalences， we'll get that this is literally just pipe of that， Right， Okay， okay。

As long as everyone's on the same page， we'll move on。

 I just want what I'm trying to show you is we're trying to arrive at a very complicated thing。

 And I'm trying to take very small steps of equivalence to show you that if you're following along。

 what I say at the end should be true。 Okay， as long as you can follow along， each step I'm saying。

 then what I say will naturally follow， okay。Okay， but again， why should we do this。

 Because actually， one of the motivations was， oh， we bind this the same thing on the same line。

 Well， we have that。 It's called a Val declaration。 So why didn't we write this。

Which you all agree is much more readable， right， You all understand what this says quite handily。

 I imagine。 why didn't we do this。The question is。Can we do this for every single function。

 What happens if I wanted to do this where I kind of de sugarugar everything to these explicitly named arguments。

 these explicitly named declarations on each line。 What if I did that for a recursive function。

Here's what I get。Let's write fact with that， right， So what I'm want to do is again。

 we're trying to keep with this protocol where I explicitly name each result。 Okay， on each line。

 I get a new answer， and I explicitly name it。 So the first thing I do is I compute fact of n -1。

 I bind it to the name Re ns。 And then I do n times that。 bind it to the name Res。 And I return res。

 Okay So this is， this is in the hypothetical of why don't we do the lets。😊。

Does someone see a problem here， Why should I not do this？

There is a reason why we should not do this， yes。The non tailored person was what I was hoping for。

It is not tail recursive。 If I do this， if I do this for a recursive function， specifically。

 if I have to bind my recursive result and then do something after。

 that's the definition of not being tail recursive， right。

 So I can't do this thing and maintain my tail recursive property。 Okay， if it was fine up here。

Up here， it was fine because we weren't finding a recursive function。

 This was just some sequence of operations。 But in a recursive function。

 sometimes I have to make a recursive call。 And if I did this， and I did do this here， No， Bueno。

 because now I have to do this and then wait to come back later and do something else。

 Not tail recursive， not efficient， Not good， okay。😊，So let's make it tailcursive。

And I'm just gonna work work through this。 I don't think it's worth writing out on the board。

 But if I wanted to write a tail recursive version of that。

 I could write it such that I keep an accumulator of type int at the beginning， it's gonna be one。

 And I return it。 Well at the end I'll return the accumulator。 And every time I do T fact n-1。 Sorry。

 that's a typo T fact of n -1。 And I multiply the accumulator by n right， And designer I believe me。

 this is how you'd write factorial tail recursively。😊，You can take a second to process that。

 I know I'm moving fast。So I just multiply it by each step， right。

 not not disim than T length or T red。 Okay， if that were N -1。That's okay。

 And that's straightforward。 Now we have our tail recursive effect。 What's the problem， Well。

 let me give you this， actually。So let's try to do that， but let's do it differently。

 let's do a tail recursive map。So， F。L， and then an accumulator， right？At my base case。

 I'm going to return my accumulator。In my recursive case， I take F。 I take in x con Xes。I take an a。

And I'm going to evaluate this to TMap。Of F of x is。Where in my accumulator， icons。Fx to it， right？

Well， what's the big book。 Why did I do this。What's the issue。Yeah。I reversed the list。

 Remember T rev。 This is actually pretty much T rev， except I now incorporated this F function。

 So the problem here is that I reversed the list。 This is not map。

So I thought it would be super cool to like do this like tailcurive thing。

 Let's like do the tailcurive thing。 But it's not obvious。 It's not obvious how I should do that。

 I'd probably have to reverse the list afterwards， okay。😊，So。This is incorrect。

 I just want to show you that T map of In 2， stringing 1，2，3 is gonna be string 3， string 2 string 1。

 because of the reversing thing we talked about， right。And if you follow this， basically。

 I reim the map I just showed you。 I re I redo T rev， which we've already seen。

 and I show you that we can do map by doing the T map backwards and then T rev。But wow， but wow。

 I had to jump through some hoops to do that， okay。

The reasoning for why we're doing what we're doing。 Okay。

 and it seems really weird and like unintuitive。 The thing we're doing is not strictly meant to be human readable。

 This is an idea where we're having we can always derive a tail recursive function for any function and computers can do it for us。

 we can write a program that takes in map and then brings us the tail recursive version。

 What I'm showing you today， is how we're going to kind of think about， first of all。

 understand why it works。 And the second of all， understand how to do it。 It's called CP。

 and it's called CP translation。 Okay so our our end goal at the end of the day is automatically create tail recursive functions。

 because my motivation do is it's not obvious how to write tail resive functions for many functions for map like this I mean。

 by way of analogy， you know， t versus and this almost looks right。

 but it's not rely less on your intuition， rely on proof。

 so this is an easy mistake to make to think that this is team map， but it's not。😊，Alright。

 is everyone filming so far。Right。Okay， can we make this more natural？

 How do we do this translation in an easier way， Well， I'll show you。 Okay。

 and it's going to have to do with pretty much this thing we just showed， so。Let's recap。

 How did we get here。 How did we get go on this journey and arrive where we're at now。

 We wanted to write nicely sequenced operations。 We wanted to put things on their own lines and make it very。

 very explicit。 What we did at each step。 And then two。

 we wanted to be explicit about what they were called。

 We wanted to bind each result to a name because we might have to use it in a later step。 Okay。

 binding it to a name is more powerful than not， even though it's not human readable。 I agree， Okay。

😊，嗯。And one way to solve this is what we did earlier。

 which is by making cool functions that take lambdas of what they need to do next。 Okay。

 these cool functions are going be the crookux of the argument。 Okay， they're going to be the core。

 the core part。😊，We can do this with lead expressions， right。

 except that it doesn't get tail recursion。 Okay， I agree with you that lead expressions would get everything except it wouldn't be tail recursive。

 We're trying to do this because in a part， we're going to try and get tail recursive functions。

 okay。All right。And we call this continuation passing style， okay。Further questions on this？

I realized I't told you about CP is。 I won't a bit。我 going版。Okay。What is this CP thing。

 What is continuation passing style。 I had a friend who once called itCustom problems solutions。

 It's actually not what it stands for。 It also doesn't stand for childproduct services。

 But what this CP thing。 Well， first of all， let me tell you what a continuation is。 Allright。

 a continuation is really。And， a function that tells you what to do next。

 remember those cool functions that took in argument K。 and then that they gave their。

 their they gave their return value to that function K。 That K is called a continuation。

 A continuation is a function that you give as an argument that says what do I do next。 Alright。

 It tells you what to do next。😊，It's named as such because it tells the function how to continue in a sense。

 When I'm done， how do I continue。 What's my next move。 Alright， don't let them know your next move。

 Well， the continuation is the next move。 So if I had map coolol here， which takes in this K。

 this is a cool function that takes in the continuation K because it takes map F L。

 and it pipes it in decay， right， so we call that a continuation function。

 It is not a continuation passing style function loop。 Okay， There's a difference here。

 And I will get to that in a second once I see people stop writing。😊，Okay。

 but this is our idea of a continuation。 Allright， it's just an extra functional argument。

 It's a higher order function。I'll tell you that the type of a CP function changes in a very predictable way。

 If I have a function of type。T1 to T2。If I want to obtain the CP version of this function。😡。

Call it F underscore CP。The type is going to become this T1arrow， T2 to alpha。To alpha。

 All I've changed is I've replaced the T 2， or I'd rather。

 I've added an extra argument of type T 2 to alpha， which is the return type。

And then I changed the return tape to alpha。 Okay， and you should see this because of the fact that map coolol originally。

 actually， let's not do that one。😊，If I had fun， add。X， Y。It was x plus y， right， This is type。

Inst inch。2 in。嗯。Oh， sorry， it's cur。 right， in to in to int。

 We can arbitrarily generalize this for as many cur arguments as we want。 actually。 And if I wonder。

 I add cool。😊，Well， what would I do X， Y， and then I add the continuation K。

And then I just say that it's equal to K of x plus y or x plus y pipe K， right， And this is type。

Int to int。2， well， this K must take in the result， which is of type int， right。

 So it must take in something of type int， and it must return。Anything， it's， it's not constrained。

 I don't know。 So it's polymorphic。And my return type is whatever the return type of my K argument was。

 So it's alpha。Does everyone see why this should have the type it is？

So when I'm telling you that like continuations change in a predictable way， it's very predictable。

 right， I just added in an argument that takes in the return type and returns whatever。

 And my return type is whatever。 Okay， that is the type of any C。 Well， almost every CP function。

 okay。So it's very predictable。 Alright， we're just adding a continuation。

 That's all that's happening。 Alright， Again， we're building on， we're building。

 This is probably the most cumulative lecture so far。 Okay， we're adding to your knowledge， alright。

😊，And the return type is polymorphic because we don't care what the continuation does。 It might be。

 It might be a return an end。 It might return a pool Who cares， yes。Yeah。

 so here I was doing an example that only had one type arrow in it。

 This is confusing because T 2 itself is a function type。

 I'm gonna to say this where T 2 is not like like， I could。

 I could generalize the process for T 1 arrow T 2，arrow T 3。 Unfortunately。

 there's not an easy way to write this out because it actually like， because he's right associate。😊。

This would be true were to take or take in one argument and give back one value。

 but this derivation should still make sense。Yes。Are not the same thing。If you gave this one。

 the identity function， which is。FN x goes X。This should evaluate to the original function given the same arguments。

Because then we'd say， what do I do So F F just does something， F does anything， but the law we have。

 the law we want to have is that FC。Let's say it takes in a single argument， Okay， X K。

Any CP function should have this be true。The CPS version， given the continuation as an argument。

 needs to be equivalent to calling the continuation on the result a CPS function has a pact a contract。

 a protocol， it always passes its return value to a continuation that is a guarantee okay and you that should make sense also because in this type。

 how else would it return an alpha type it couldn't return anything of type alpha unless it got an alpha via this okay。

😡，Which might not be obvious to see so it's okay if you don't get that exactly。

 but this is the idea that's driving us okay， this is why we're doing the translation okay。Okay。

 so the type changes in a predictable way， that's the idea。then I actually already did this for you。

 but。 Yeah， so we wrote our ad。And if I add out， if I do add CP， this  one I claim to is CP。

 but let's call it cool。 Okay， I just taken the cane apply it， right。

 That's what I put on the board already。But the type changes in a predictable way。

But is it always this simple because what if I wanted to write in the factorial function in CPS。

 okay， and actually I don't think I'm right this yet？So。I could write this。

But one of the reasons why I wanted to do the CPS thing， remember， is I wanted tail recursion。😡。

This is very not tail recursive if I get remember this is the original fact right if I give this fact 10 billion。

 my computer is going to die because it's going to have to remember to do 10 billion things Okay so this is not a good idea。

 This is what we'll call like cheating we're going ask you on your homework。

 we're going to say write this function in a CP way。

 And if you write the direct style function and then pass that into K you're going to get constraints off you're you're gonna to get no points because this is not CP this trivializes the problem because it's not tail recursive So how can we write this Well we're gonna to have to rewrite。

That's entirely。So basically the thing I just want to say is that was basically at very understand。

 Okay， we're now to rerite the fact function from scratch in order to make it CP right this will be true for any recursive function we want to write in CP。

And I believe we do this on this next slide。Okay。Oh， sorry。 Oh， yes。 Okay。 Oh no， yeah。

 Another note also is like this， this idea I've been building up and staging with you is cool functions。

😊，CPS is cool。 That's a life lesson， which means that any CP function is a cool function。

 It takes on a continuation。 It passes its result to the continuation。

 but not every single cool function is CP， because we can see that this。😊，Fact CP quotation is cool。

 It takes in a continuation and passes it。 It's not CP because it's not tail recursive。 Okay。

 so another way to think about it is。😊，Cool。Plus， tail recursive。Equals CP。

That's another way to think about it。 Okay， We cool is again， as I defined it earlier， right。OK。

We're going to define a cooler function that manages to be tailor recursive。

 even through its recursion。So here are the rules for CP。 Okay， we say a function is CP。

 If it fulfills these three criteria。 One， it needs to be cool， right， It takes in a continuation。

 and it uses its continuation。😊，지요？It makes cost weather functions with continuations as tail calls。

 That means that is like it makes cost weather functions that are cool， but only as tail calls。

 you can't like call two CP functions and then use the results。

 It needs to be tail recursive all the way through。 That's the idea。 Okay， And then three。

 it only calls its continuations as tail calls。 So you can't do something like K， X plus Y。😊，Plus，2。

 we can't do this because this would also constrain the output type of the continuation K， right。

 The K shows us what to do last。 It's the very last thing that happens。

 So I only can do it as a tail call。Alright， all three of these things must be true to make a CP function。

 Alright， So we'd say like the original fact。Did not satisfy one。2 is not satisfied by， I guess。Well。

 I guess it wouldn't be satisfied by this one we just defined up here because it makes a non tail call to fact。

 which is not tail recursive。And then if I did this like K of x plus 5 plus two thing that would not satisfy 3。

 Okay， so the recursive all the way down， basically and cool。 right。

 I realized we haven't seen a whole bunch of definitions。

 but hopefully this will make more sense once we see a couple examples， okay。😊，All right。

Remember that this is what we had when we tried to do fact， right， We wrote this giant let thing。

 which is fine for if， if not readable。 and we want to convert this to a CP style。 Alright。

 so actually， we're gonna do that on the board now， I think。😊，How do I rewrite this function in CP。

 Well， okay， it's most helpful to write a function in CP。 if you are starting from。It's。Originally。

So we're going to do fact n equals。Let's。Bell， Re ends。Equals fact n -1。And then Valreez。

Equals n times。 I should have written this earlier。 Sorry， Re ends。And then we just returned Res。

 right？And sorry for those of you on the left where， this is hard to see。

 But it's just what's on the board right there， all right。For recursive functions。

 I have to do this a little bit more， more elaborately， right， because I can't do this。

 I can't just say， let this equal to this。Right， why， because this is now no longer a tail call。

 I can't just add the continuation and expect to get the result。 Another thing is。

 remember what I said about the type。 fact， n -1 of K should now return to me an alpha。

 which means I， I can't use an alpha。 I can， I can only return an alpha， right。

 because it could be anything， if I do anything， basically， if I do anything with an alpha value。

 I I'm probably gonna to constrain the type。 Okay， so to do this。

 I don't want to do what I just showed you here。 So how can I possibly make this happen。

Here's what we're going to do， al right。The difference between writing a function and CP versus not between doing this and then doing what I'm gonna to show you is the difference between what I'll call writing down instructions and remembering instructions。

 Okay， the difference between now and later。 if I want to do something if I want to do anything。

 I can write down instructions for what to do right now。

 and then give it to someone and have them do it。 Or I could have someone come back to me with something and then remember that I have to do something to it later。

 Let me give you an example。 Allright， Can I get a volunteer from the audience。

There's a precisely one， yeah， okay。All right， has volunteered。Okay， here's someone do。

 I'm gonna stand over here。 and then my legs are tired。

 So can you go over there and get that paper that's on the table for me。 Don't look at it yet。

Just give it to me。All right。你。All right， can you go get me another one， actually， thanks。Anyways。

 so what we're going to talk about is this difference between now and later and。Now in later。

 can you guide me another one。 things。 now and later， which is that to do anything。

 I can remember to do it right now and then write down the instructions。

 or I can have a subservient person do it， thanks。😊，And then， oh， oh。

 you remember to do it cool and then。And then and then do it later。

 But the point is that every single time，ez， can you stop handing me these。 Actually， you know。

 every single time that he does this， I have to remember to rip this up。

 and I I get distracted in the middle of my lecture。 So actually， you know。

 can you go over there and grab it and just rip it up yourself。 Thanks， No do it。

 And then now I'm free to do whatever it is I want。

 And now I don't need to think about what he's doing because I know someone will do it。 Allright。

 thank you。 That was it。😊，Thank you。 Good job。 Good job。All right。

 the difference here was between me saying。Go do this and then bring it back to me。

 And then later on， I have to remember， oh， you handed me this thing， now I got to rip it belt。

 I have to remember to do that。Well， and that takes up space in my brain。

 and it interrupts me in the middle of what I was doing。 Or I tell， hey， can you go do it for me。

 Then I don't think about it anymore。 I know that it's gonna get done。 Allright。

 this is the distinction。 All right， and and I'm going make the analogy make sense in the second here。

 okay。Alright。Here is another analogy here， which is my friend， Oh， actually， no。

 I'm not gonna to give you this analogy。 This was the alternate analogy。

 This is the analogy for people who aren't in the live lecture。 So that's gonna， allright。😊。

This is what I call the later mindset。 Okay， This is the later mindset。 I say， do fact of n -1。

 Give me the result。 Go get the paper。 And then later on。

 when it comes back to me with n -1 factorial， I have to remember to multiply it and return it。

 That's later。 I have to do that later。 And later is bad。 Later takes up space in my brain。

The difference is now， now if I were to tell the computer， go do the multiplication later， well。

 not later， but like now I'm going to tell the computer to do something for me。😡。

Then I don't have to remember to do it later。 I'm gonna to show you the alternative。

 This is just the later example。 Okay， now is good。 now is dynamic。 now gets in to parties。 Okay。

 so we're going to do the now。Alright， so the idea is just that we're trying to prevent this thing where we have to do stuff later。

 We're trying to prevent tailcursion。 So how do we do the now。We're going to write f CP。

 which is of type int to。Priends into alpha to alpha， okay。

And here's how I claim we're going to do it。Alright。

 I think I just give you the whole implementation。 Yeah， okay， here's my edit edit distance。 Okay。

 I'm being very deliberate about what I do to show you the difference， okay。系。Give it a K argument。

 right， then， oh， sorry， I'm gonna to move this back， actually。

I call K wherever I was originally returning a value， right。

 because I give the output value to my continuation。 So I call K on every time I return。

 I I return the function returns。 Okay And then finally， I can't do this nontail call。

Here's our menu you。This is out of scope。 This hasn't been bound。 What if I did this instead。

I put this entire thing in a lamb expression。I'm gonna to show you on the board。

 So it's actually like easy to see。 Okay， This is the edit distance。

 I What I happened is I took this entire thing that I said we were originally going to evaluate to。

 And I put it in a land expression， where I said。😊，First， first， first， right now。

 do the fact CP on n -1， and then recursive leap of faith。😡。

Whatever this landda takes in is the result of factorial of n -1， right。

 I pass A CP function has to pass its output to a continuation。 So therefore， I get it。

 But now I'm in here。 But the key is now I don't have to make a recursive call。

 I made the recursive call first， and I got the value。 This is all tailed recursive。Okay。

 the difference I want to illustrate to you between what I had on the board earlier and what and this。

 That's later。 That's， let me do the fact。 And then later remember what to do。 Okay， here its。

 I make a singular tale called a fax CP。 And I never come back。

 The last thing that happens here is this call it a fax CP。 because right now。

 I wrote down an instruction， I said when you get your answer。 When you get the factorial of n -1。

 do this。Later。Now。I okay， I realized later is an unfortunate choice。 Let me say after。 Okay。

 with the continuation， do this。 But do， do you see how this fact CP thing is a。

 is a tail recursive call。😊，It's the last thing that we do because， oh。

 maybe it's actually not clear。Everything here。Is in a lamb expression， right？

And that means that things inside land expressions don't get evaluated。

 If I have F and X goes to one plus1， I don't get F and X goes to goes to 2。

 I get F and X goes to one plus1。 A land expression freezes its contents in time。 So here。

 when I freeze the contents of this in time。 The last thing I do is I call factsax CP。

 but I give it a lambda。 I give it a lambda that says what to do。With the continuation。

 So this Lada is what I call an instruction， right， It doesn't do anything。 It's。

 it's because it's frozen in time。 It can't do anything until it gets an input called Re ends， right。

 functionss are instructions， in a sense。嗯。😊，But later on， once this continuation is used。

 when the continuation is eventually used here or here。 and I'll show you what that looks like。

 then we will do what this is is。 Okay， so this is kind of an analogy where it's a little more clear to me that I think it is to you necessarily。

 But to me， this looks like telling Stephen， rip up the paper later。 Okay。

 I'm gonna tell you to rip up the paper。 So I don't have to remember to do it later。

And I give it a lambda， I give him a lambda that says rip up the paper， okay。That's how I see it。

 Allright， It might be confusing。 Any questions on this。I know this is just conceptual right now。

 We will。 I will， I have a lot more padding to do， yes。I just thought itd make the difference nicer。

 I thought it make it easier to see the the difference。 I。

 I replaced the recursive call with putting everything into a La expression where I had the recursive call。

 Yeah， okay， we're gonna move on。 yes。😊，So on the first call the K can be anything。

 The K is an argument to fact C。 If I want to call fact C。

 I can give it an original K that says to if I gave it like F and X goes to X。

 then it would be equivalent to。Fact， okay， but it could be different。 Okay， it doesn't need to be。

 but it could be。 Look， for all intent purposes， Think about K as originally being this， okay。嗯。

I know I haven't shown you how this K changes， but this K is changing。

 What I want you to think about Okay is recursive leap of faith before you go and step through it recursive leap of faith。

 If fact CPps does what it should do， which is that it satisfies the law I just erased。

 which is that fact CP， given K should evaluate to K of fact。

 That means that this thing should evaluate to this lambda given the factorial of n -1 right And if it did。

 that would be the correct return value right。😡，So recursive leap of faith think about it。

 I know that this doesn't make any sense because you haven't seen how this changes。

 but I will show you， but recursive leap of faith think about the fact that what I'm saying is that I'm taking a lambda that takes in my result if this is the result。

 this is the answer， yes。We should， because the K is changing。 the case is an accumulator， actually。

Yeah， I I'll talk a little bit more about that。 I suspect we should move on， yeah。

I' am not piping it。 I'm doing the cool thing。 Or instead of piping it。 Remember。

 we got rid of the pipe by giving the argument that was gonna be piped into。

 the lambda that was gonna be piped into into the function itself。 The function calls itself on the。

 the continuation， right， instead of doing， instead of doing F X。😊，pipe케이。

I instead made a function F prime that if you give it K， it's extensionly equivalent to k of Fx。😡。

This is what I did。This is the idea of a cool function。

 A cool function just takes some continuation and then calls it。 Okay。

 I think we're gonna move on because this will be more clear with more examples。

 And I really wantan to make sure we finish。 Yeah， okay。😊。

I don't exactly know you mean by double function。We would pass an original K。

 which was the double function。 We would like say fact CP。3， double。And I would。

 I guarantee you that this would evaluate to 12。I'll show you a trace them a little bit。 Yeah。

 I'm gonna to get moving， though， because I suspect we're going to run out of time otherwise。O， yeah。

 sorry， O， so。The point is， writing instructions now versus remembering later。 Okay。

 that's the distinction I want to show。 And the distinction between that is the distinction between telecursive and not。

 what was say on this slide。 Yeah， I think I was pretty much what was gonna to say， Okay。

 the continuation is a functional accumulator。 That's another thing I should say。

 We're making the accumulator。 We're doing back CP with an accumulator。

 It's just that the accumulator is a function。 Allright， that's another way to think about it。 Okay。

 key， this is the key conceptual divide。 right It's a accumulator that is also a function。

 I think I'm gonna to get to the trace。 I think that's the important part right now。😊。

And then once more， okay， the， the analogy I'm trying to draw here is in a direct style function。

 which is。Fact， as I originally drew it， I had to remember to do this after the fact versus in a CP function。

 I write down， I write down this lambda。 This lambda is what I write down right now because then it's what's done。

 It's what the continuation will do。😡，Okay， allright。

 we're gonna get to the trace because this is going to help a lot。 Oh， yeah。 and more。

 more cred to this idea of lambmbda's instructions。 If I have something like F and onions。

 goes to onions， pipe， chop， pipe， grill， pipe， put sandwich。😊，In intention， conceptually。

 what I've done is I've written down a laundry， a recipe list that said， take the onions。

 chop the onions， grill the onions， and then put the onions on a sandwich。 But it wasn't done， right。

 because lambes are not evaluated until you give it an argument。

 so I'm just trying to cod this idea that land instructions can encode information。 And they are。

 they do it by being these things that are like instructions， okay。Alright， here's the trace。

 Or if I really want to simplify facts C， here's what it look like。

 This is the less complicated version to write。 When you write your homework， write it like this。

 Okay， don't write it like this。 You might， I think there's actually good things to do in both cases。

😊，Alright， so we multiply by n now。 and then O， let's， let's move on。Okay。

So if I take this thing that I had here and I indent it differently， here's what we get。

And this looks like what we had earlier， right， which is that I do fax E of M S1。

 And then I give it this continuation that says with my recursive result， multiply by n。

 and then later do K。 Alright， I'm gonna show you the trace by showing you how this thing is built up。

😊，Okay。Suppose I have fax CP 3 and then given an arbitrary K。 Allright， how how is this gonna step。

 Well， we're gonna use the simplified version I had earlier， Okay。

 but you can believe me that here's what's gonna step to。 I will decrement this3 by  two。

 Itll be a tail call And I will instead change this K to a new lambda that says three times res 1 and pipe into decay。

Another thing I did also is I， I changed the definition of fact CP a little bit。 Sorry。

 I change it So Ill be pipe in decay， rather than。2 K of this。 It's， it's essentially equivalent。

 but I change the notation because I think it'll make your understanding easier。 Okay。

 hopefully this should make sense， though， Okay， so I change it to this。 So it says fax E of2。

 then do three times， then do K。 Okay， once more， let's step it。 Let's step it again。

 We're going to get one。I make the lambda bigger by making another thing on top where I take in back CP of one。

 Then I do two times that。 Then I do the same thing from before。 So it's， it's the same pipeline。

 I'm building a pipeline by building up the top。 Okay， and I added print on the end too。

 because I have to。 Okay， that's not important。😡，Final step， I decrement by one。

 and I add a new layer which says take in faxy P of 0， multiply it by one， and then pipe it。

 And by the way， this is like exactly what it steps to， right， I'm not lying to you。

 I'm not doing essential equivalents。 This is the trace。 It's just indented nicely， okay。Okay。

 so this is， if you believe me， this is how fax C will build up its accumulator。

 Do you see how the continuation has been an accumulator。 I just keep recalling my recursive thing。

 but I make the continuation bigger。 Alright， by these yellow things。 Allright。

 now let's see how it's broken down。 How do I break down this continuation。 I'm going to do this。

 So we know that fax C of 0， says that and K says call the K on one。 call the continuation on one。

 So let's call the continuation on one。 So I pipe one into it。 This is extension equivalent。

 Allright， but it's， it's equivalent。 So I'm just trying to present it too nicely。

 So when I pipe one into this， I bind one to re3。😊，Right， and then that's one。

 So I bind that to rest2。Whi is one。 And then I multiply the by  two。 That's 2。

 And I pipe it into this function where I bind it to as 1。So I get two and then I do three times 2。

 which is 6。 and I pipe it into。Okay。The picture I want you to have here is what did I do here。

 other than build up a list of instructions at every single step。 What I did is I said， hey。

 at the first time I said， hey， hey， hey， can you， can you take your result and multiply by 3。

 Thanks， And then at the next step， I said， hey， hey， before you do that。

 can you take your result and multiply by  two。 Thanks， And then next I said， hey。

 before you do that， take your result， multiply by one。😊，And then eventually。

 when it came to actually discharging this function， I gave it one。And then the instructions ran。

 We broke down the instructions 1 by one。 Another way we can think about it， also is。

This is like a list， right， I， I I put， I prepen it to the list。 So I cons。

 I cons instructions onto my function。 And then at the very end， from left to right。

 I break down the instructions。And eventually， I come up with6 pipe K。

Does everyone see what happened here。I think this is the final picture you should have in your head for what is happening。

 Okay， I had to write it with these pipes。 This is not exactly how you'll write it on your homework。

 but you you can。 I mean， I think， actually， I think it makes it easier to understand。

 but we're just accumulating a list of instructions instead of a list of data。

 We're accumulating a function。 Okay， that is the key idea。

 and you should be relatively as without even stepping this。 Okay。

 I'm going tell you that what this does is it's the identity function。😊，Cause icons on， icons on。

What to rather， okay， onto my list of instructions， I prepen to the front， right， I have。

Let me actually give me an example。Actually， I， I guess I will show you in theory。 Okay， if I 1，2。

3 as my argument to mystery， right， What do I do at each step。

 I cons on to my list of instructions that I should cons on the thing on top， right？

 So the very first instruction I say is， hey， can you cons one。😊，Right， that was the first name。

 And then I take this off， and I do another rehearsive call。 And then I say， hey， can you cons on2。

Right， I'm running pseudocode， and then I take this off。And the next thing I do is I say， hey。

 can you con on three。And I take this off， and I'm at the end， so I give it nil。

And what is three cons now。It's three。And what is two cons3？It's two comma 3。And what is one cons。

2 comma 3。One， comma  two， comma 3。If you got the intuition correctly。

 you should see why this will just be the identity function， okay。But this is what we're getting at。

 okay。All right。And I would like you to check your understanding and verify this。

 I think it really helps to write it in this way。 Okay。

 like if you can see the the list of instructions， just， we're just pre pening instructions。 Okay。

 alright， I'vequibbled on for long enough。 let me think about if it's a good idea for you to do this quiz because I'm considering skipping it。

😊，I will skip it。 I will skip this quiz because I would like more instruction time， yes。Yeah。

 you wont get house points。 Oh Yeah sure why not。 Sure。 All right。 Oh yeah。

 I haven't done this in a while。 plus 10 points to every house。 Thank you。 Sorry。 Alright， no jokes。

😊，No， anyways。Well， okay， anyways， let's move on。 No joke。 serious spaces。 we got lot to cover。 cool。

 Alright， so I showed you this thing。 And first of all， is everyone on board。

 but like the CP thing works， You saw how it worked。 You understood how it worked。 Like。

 is everyone clear on that。 This is very important， okay。😊，That being said。

 it's not necessarily something I can rectify now， but I I want to make sure everyone on board。

 So let's see how we can do this thing called CP conversion on an arbitrary function。

 We want to turn an arbitrary function into its CP equivalent。 I already told you this， right。

 to change the type。 We just give it the extra continuation， and we do the thing。😊，Allright。So， O。

Here is what we're gonna do。 This is our entire formula for how we make a CP translation function。

 Okay， so you start with a function called F。 Alright。

 for a function with return type T T 2 in this instance。

 we add a continuation of type T to alpha and change the return type to alpha。 Okay。

 I already told you that。 That's step 1。😊，Step 2， we call the continuation on every single return value。

 I actually already demonstrated this to you。 But I'm gonna show tell this to you in general。

 And if there's a recursive call， which is like the expression E， like， like fact of n-1。😊。

I take that， and I cross it out， and I replace it by a variable， a new variable rec ends。 Okay。

 and then I wrap the entire function in。This thing。

 but the continuation says to do the what the whole thing is。

 I'm gonna show you this in actionction on fact。 Okay。

 I'm gonna show you basically what I show on map， actually， alright。😊，So we have map。 This is map。

 right。First step， I add the continuation。 next step。

 I apply the continuation anywhere I would have previously returned a value。😡。

So that means I call k on nil and I call K on the body right， in the recursive case。Next step。

 I have to take any recursive call and I replace it by a free variable。

 a new variable called rec ants， so that's my recursive call。

 and I replace it by rec ants right and then next I wrap the whole thing in a lambda that that does the recursive call。

So I do the map F Xs， given a lambda that does everything that we just constructed。

Does this procedure kind of make sense。 I don't want you to just follow this becauseuse you probably won't be able to on the homework。

 to be honest， like this probably won't generalize super nicely， but。

I don't want just follow this step and then not think the idea is what did I do。

 I added a continuation， wherever I returned， I had to call my continuation。 why。

 because the continuation is my promise。 My promise is whatever I return。

 I will give it to the continuation。 So that was adding K。😡。

And then by doing this thing where I replaced the recursive call。

 it's because I had to be tail recursive。 I had to be tail recursive。

 So I bound this recursive answer in the lambmbda I gave as an argument to the CP function。 Okay。

 That's what I did。😊，And that produces a CP function，3 components， the continuation。

 the pact and the tail recursion。 So actually， that's another way to think about， okay。😊。

Step one is add the continuation。Set two is fulfill the pact。

 and what I mean by pact is the fact that F of CP。Xk， which I've written three times now。

Shell be essentiallyly equivalent to F K of F of X。 This is my pact to be a CP function。

 I have to fulfill this。There are other ways I could fulfill the other ones by like looping forever。

 for instance， that would like make a tight check。 But this is the only way that fulfills my pact。

And， then 3。Is make it tail recursive。Allright， that is my procedure。 Okay， that's all。Okay。

 and this is the CP version of map。 Okay， any questions on this。Or why we have these three criteria。

系。All right。嗯O。And I have to apply K because it's， yeah， that， that's the fact。 Allright， cool。Okay。

 oh wait， maybe I do well have time。 I don't know。 We'll see。 I'll turn in。 and， yeah， okay。Alright。

 if everyone's cool with what we just did， we can move on to a slightly more interesting example。

 which is if I have a function that returns an option。 Okay， and you should think about this way。

 Alright， if I have a function like search。😊，Which has this type。so it's also check Menty both。



![](img/6753b175e449c8050a6cbb7aeee2595e_1.png)

Can you demonstrate yes， I did？

![](img/6753b175e449c8050a6cbb7aeee2595e_3.png)

Let's go。 Alright， Al pool to alpha tree to alpha option。 You agree with me。

 This is the type of the search function。 I believe I actually implemented for you here。 Yes。

 we already implemented this function。 So I won't go to the depth into it。 This is my type。

 And what I want to say is to CP this。 I have to turn it into well， I turn it into the same thing。

 but now we take in a continuation。😊，Of type alpha option brings to beta a new polymorphic type。

 Does everyone agree， this is what the type of the CPified version should be。If you think about it。

 a function that takes an alpha option。All it does is it cases on if it's none。

 like if it's a function that if it's none， it does something。And if it's sum of x。

It also does something。 but like maybe with the knowledge that it's X。 Okay。

 I claim to you that this is pretty much like， if you can think about as two functions。

 it's a function that does this that you call if it's none。

 And it's a function that does this with the argument if it's some。 Okay。

 it's like the information is kind of the same。 So what I'm gonna to say is that we're actually gonna change the type signature of search CP to be this one。

😊，I take in my original predicate function， I take in my alphapha tree。

But instead of taking in one continuation， I'm going to take two。

 I'm going to call it my success continuation and my failure continuation。

 because this thing already codifies kind of two pieces of information。 The option case。

 the none case and the sum case。😊，So， I'm going to take in。

A function of type alpha to beta note that it's not in the option。 and it'll take in。

 I'm gonna put it on a new line here。 unit to beta。Remember。

 that unit is the type that has exactly one value， right。

 So it's unit to beta is kind of the same thing as the nun case because I give it no， no information。

 in a sense。And I will term data。So， I will do。I will do this。Instead of this。Okay。

This is just the way I'm going to structure it for any， for any function of that returns an option。

 we can do this。 Okay， we're gonna have a failure a success and a failure continuation， right。Okay。

I totally all this， okay， so。And I， I defined it for you there。 Okay。

 success continuation of type of of the return type to alpha and a failure continuation of unit to alpha。

 yeah。Skip over。 What you mean。Yeah， but you would have anyways。

 Like if you called this function on none， you would have skipped the logic in the function that dispatched on this up。

This is just2， two Korean。 I put on a new line for legibility。 Its it's not。 I took two arguments。

 Yeah， We'll see， okay。So we're gonna take two continuations。 And our promise now， our pact。

 our new pact， okay。Our new p is going to be this， all right？Our new pact is that for a function F。

 which returns like an option。We're going to have that Fcps。Of K。 And then we're gonna， oh， sorry。

 of x， and then。S C and F， this is what I call my success continuation and my failure continuation。

 The pact is that。If Fx is equivalent to none。Then it should evaluate to F given unit， and otherwise。

If Fx is equivalent to sum of y。Then this function should evaluate to SC of x。Alright。

 as everyone clear on this p， this new updated pact。

 instead of justre evaluating to the continuation of it， we have two continuations and it dispatches。

 In either case， if I were to return it on， Id just call it failure continuation。

 If I were to return a sum， I always call the success continuation， yes。😊，Why， why， why， why why。

 I was thinking about that as I was writing。 I was like， what should I choose why？

 And then I was like， well， what if I forget about that。But this is the， yeah， good， good。

 good point。 But this is the new pact。来，我客张丹。😊，So here's before and after， right。

 I actually wrote for you on the board already， but you can write that again if you want。

And actually， sorry， sorry， this is wrong。 Sorry， it should be actually the pact I have on the board。

But yes， this is the idea。 Okay， we're gonna try and implement it。 Okay。

 and we're gonna try actually better。 We're going to， try to automate it in a sense。

 We're going to follow the procedure for how I would do it。 Oh wait。I might not write this on the。

Ceez okay， let's write the fun search and let's just do it because it's important for you to see it in front of you。

 I think。So in the empty case， I return none， right？And then in the other case， what I'm gonna to do。

 I will also take questions while I'm writing if anyone has them。Yes。😊，Yeah。

 this is just search and we will do the CPS version in a second， okay？あ。

We book the failure of continuation might change， so it might not always have the same effect。

 but we give it， the input we give it is not important。

 so we give it in yes because it has no data to take in maybe I will just write this。

Let me let me tell you the algorithm。 Okay， the algorithm will be if I have a function of return type T option。

 I get two arguments。 I already tell you this， the success and the failure continuation。

 If I return none， instead call the failure continuation。 That's just my pact。

 And then for every time I return sum of X， call the success continuation on X。 Again。

 this is the pact。 Okay， And then three， if there's ever a case for the for the function。😊。

If there's ever a time we case on the function， then instead。

 what I'm gonna to do is I'm going to replace it with a recursive call to the search CP function。

 but I'm going to change the success continuation to take care of the some case and the failure continuation to take care of the none case。

 I thought there was a hand。 Okay， that's the two things I'm gonna。 I everyone clear about this。

 And I'm gonna show you this example right now。 Ill show you I think。😊，Okay， search P。呃L of。9。

Search PR。This is not an in order search。 It's a preorder search， actually， but it doesn't matter。嗯。

And if it's some y， I return some y， okay。This should be search。 Okay， let's follow the algorithm。

 Alright， this is my original function。 Let's make a CP。 First step， continuation， K， K。😊。

Second step， fulfill the pact if I get none， oh sorry， okay， my。S C，FC。Next step。

Fulfill the pact if I were to return none， don't。Fc of unit for none， right， And in the sum case。

 instead of sum of y， I return。S C of y。 And here instead of sum of x。S C of x， okay， that's part 2。

 part 3， there is a case。 Instead of doing this case， here's what I'm going to do。Well， first of all。

 this doesn't doesn't make sense， right， because search takes two arguments。

 search takes four arguments， rather sorry， But here it takes  two。 So we're gonna change it。

Instead of the case。Sorry， this also should be an else。Instead of the case。

 do a recursive call to search where I give it two things。 One of them will be。F N， Re and sorry。

 this is actually this， the success continuation。Jeez， okay， it'll be better to show you。

 I realize actually you have to switch the order。So I do the S and X C。

I replaced the places I were to return。And then the next step， I identify， where are my cases。

 I have two cases， the non case here and the sum case here。

I'm going to make this a recursive call where this is the failure continuation instead。

 and this is the success continuation。😡，So I make it this。

 I'm gonna go back and forth real fast just so you can see the difference。 I。

 I switch the order also。😊，My failure case， if I didn't find it in the left and that means my failure continuation was called。

 I go to the right。😡，If I succeeded in finding it in the left。

 that is my success continuation was called。 I continue to call the success continuation on it。

 Do you see how I just took the code from the the yellow and red code。

 the thing that's outside after the arrow， and I transplanted it into here。😊。

And I gave the extra arguments to the rehearsal call， okay。This is search CP。

 and you change the name。Alright， this is search C T S。 And the way you should think about this。 So。

 firsts of all， I wanted to show you the derivation。 I wanted to show you how we get it 2。

 I want to show you。😊，I want， I want you to be able to reason about what this does and be able to write this yourself if you have to。

 okay。When you're reading this code， think about it as I didn't find it bam failure。

 I call my failure function。 If I do find it， bam， I call success。But otherwise。

 what do I have to do， I have to make a rehesive call。 But remember， in CP。

 instead of making a rehesive call and using that recursive call， I make a recursive call。

 and I put my next actions。 What I do next in my continuations。 Okay， right now。

 I write instructions as to what I should do。 Alright， so I go and I search on the left。

 If I find it， I succeed。 baam， I'm done。 If I don't succeed， I search on the right。😊。

And this will upkeep or keep up our p。 This is a correct search function that maintains this。Idea。

 this invariant， okay。对。嗯。This gets really complicated to the point where I don't think it's productive to show you a trace of this。

 The lambdas are simply。A little large。 Okay， but recursive leap of faith。

 you should be able to think about why this works。 Okay， any questions on search CP， this idea。

You' all have no questions following along perfectly。Yes。In the recursive call。

 we are building up data， we're building up instructions is how I would say。Yeah， yeah， yeah。

 So that's actually a good point for so。嗯。Oh， I have a much crap on this board。

So one thing to note is that there's this idea of customizability。

 which is that with the CP function， I can give it whatever continuation I darn will please。

 As long as the types match up。 Okay， so let's do it。 suppose I have a T tree。 Okay。

 let's call it search CP。😊，Let's give it a lambda。 Let's say F M X goes to X mod 2 equals 0。

 So it is even function。 essentially。 Alright， so that's argument 1。 I give it T。

 assume that I have some tree。 Okay， and then I'm gonna give it next two arguments。

 which are S and F。 Okay， in the success case。I take in res， which is of type int。

 It has to be because it is an int tree apparentlypparently。 And what do I do with it， actually。

 sorry。I'd rather， oh， no， no， here we go。 Yeah， I can make it a string。foundound。Shrinking cat。

Int right。Inch that two string。Res， maybe I should have just written this out to you in the terminal。

 That's fine。 And the failure continuation F N unit goes to。 I have to return the same type as this。

 So I return the string。 I just said。Did't find。Jack。This would type check。

 And what would happen is that if it ever found an element。

 this would evaluate to found string and cat whatever that inch was。 So like found 2， found 5， 1，50。

 And if there weren't to be such a thing in the tree。

 it would evaluate to the string didn't find Jack， Okay， but I could customize that behavior。

 I could do whatever I could return whatever value I want because the continuation has the final say。

 yes。一。It's building up in front of it。 Yes， yeah， the exact same picture as I probably can't show you now because it was a long way away。

 But remember that list。 yeah， no it's going be too far。

 if you remember at the very end of our instructions when we did this fast trace。

 We always had this pipe K。 and that was always at the end。

 that K is one of these by analogy it's the original K is at the very very end。

 we always keep it around， but we just add stuff above it。

 we say do this to this to this to this to this， the same thing will happen here except twice we'll build up with this thing。

 It'll be。😊，Complicated because it'll be building up on both of them at once， okay that's the idea。

I haven't actually admittedly tried to do them Tracing Logan。

 but I think it would probably confuse you more than I would help in this case。

So I'd say that this is hrorosive because this essentially is a piping indicator decay。

 right S is essentially okay and we do this after so what's the again， why is it hoccursive。

 it's because it's in the lambda。😊，Because it's in the landda， we don't actually do it out here。

We do it。 the call to search GPS has the job of doing it， not this call。 essentially。

 we shift to the burden。 We write down the instruction of doing it。

 but we don't have to actually do it ourselves if that makes sense。

 even though even though I agree with you， eventually at some point in time， we will call this SC。

 we will call this guy if we find anything， but it's still tail recursive because we make a tail recursive call and it's the last thing we do。

Okay， we're just shifting everything onto the inside of the lambda。 Was there another question yes。

I think it really helps honestly when I was making these slides。

 I thought it really helped to like do that derivation， I'd encourage you to try。

 and then if but the algorithm might not always like work in a way that it might be confusing。

 I'd recommend you to try at least because I think conceptually this really helps in terms of understanding what's going on when I took the course。

 I didn't do this because I didn't come up with this year。No， so yeah I think it helps personally。

 you all can be the first getting based on that。Okay， was there another question from someone？

Otherwise one。Okay， but this is our idea。 Okay， and we can use it in whatever way we want。

 We can use it in a very general way。 I was making sure there wasn't another one that wasn't ripped。

 I'd have to rectify that， if not， okay。收。I'm gonna to spend the last eight minutes talking about the other things that happened previously。

 the idea here， though， is that CP conversion is just mechanical。 It's very， very mechanical。

 It's very very boring。 Okay， when I did all this stuff。

 like it was an algorithm to get the CP version。 And it's because again。

 this motivation is that computers can do it。 Every single function that you write in S M L can be made tailsive。

 I think is madecurive by the compiler。 can automatically be done That doesn't mean that you need to write your functions like this。

 Again， this is not a point in favor of readability of this。 I do not think that's true。

 There are problems in which this is actually very helpful specifically we'll look at one in two weeks。

 sorry， two lectures about regular expression matching。 it's really。

 really nice to do this But the real point here is that this is cumulative。

 if you have a deep understanding of like how passing in La work how works， how evaluation works。

 Everything I told you today have not been new。 There's been no new syntax's been no new like anything It's just an application of what you've already seen granted very heavy application but an application。

😊，S， okay。I think I want to go back and kind of stress the point here where which is。

So when I look at this code， right？The idea is that this SC is not going to be your original SC at an arbitrary recursive call when I enter this case。

 this SC will not be this。😡。

![](img/6753b175e449c8050a6cbb7aeee2595e_5.png)

It's going to be like。F N Res goes to b， goes， it builds up on itself。

 I'm accumulating in my accumulator。 I'm accumulating in my continuation。 Alright， So like。

 although we're saying S C and F C， and that might make it unclear to you。

 how this recursion is even happening in the first place。

 the thing to realize is that it's because the accumulator is changing。 We're saying。😊，And。

 in particular， this function really accumulates in its failure continuation。

 The failure continuation gets really big， okay。Yes。Inside of a record。Yes， you could， but yes。

 if you were to define the regular fact， then you would just so for instance， we can do fat。

 n is equal to fact CPS。And FNX O X， this is true。Yes， yes。 Also。

 you've never actually really used this。 There's almost no reason why you should write this。

 but you know。Over this sum。 We'll see。 Okay， I just wanted to show you this trace just so we can see it again and see how this thing is changing in the last two minutes。

 But I， I basically have defined fact C， but I'm giving it the original K of the incrementing lambda expression。

 Okay， that's the thing we'll do last。 So that means that what I want this thing to reduce to at the end of the day。

 is the factorial of three。 And then I add one to it。 because that's my original accumulator。

 My original continuation。 Okay， first step， I case on it。 I enter rather here we go。 Oh shoot。

 I'm gonna that's annoying。😊，Oops。I'm going get rid of this because it's annoying me， okay。Alright。

 first step， I case on the other thing。 I have 3， or I have 0， or I have n。 I have n clearly。

 So I enter here。 And do you see how this lambda has changed because。

This thing here is my original K， but it's K applied to this guy。 Again。

 like when I showed it to you with the pipes， it was this piped into that。

 This is just the original way， which I think honestly makes it a little harder to read。

 But I want to show you this。 So you have intuition for it。 Okay， so I apply my original K to that。

 But I put this into a lambda。 Okay， in terms of my stack in terms of like my stack and instructions。

😊，啊。In terms of my stack of instructions， what I've said is。😡，Essentially， I have a stack， right。

 and at the very bottom of my stack is。Cll K。Alright， and then my next step unravellling is I put in。

 wait， first， before you do that， do three times res。Okay， and then what I do， I do another step。

 I case and I get this， which is why this。Thing right here。Is my original K or not my original K。

 The previous K， right， This one is the one from the previous step。And I apply this to two times res。

 and I put that in a lambda。 I'm expanding my instructions by adding a layer onto it。

 Something else I say is that CP is like a jelly donut。 Okay。

 because like a donut because I take this thing and I wrap it in a big lambda。

 I wrap it in a lambda where I now I'm applying it to two times res。

 So that means that in terms of like my stack， I put two times res on the stack。Okay。

 and what happens， Okay， Another two steps or three steps。Now。

 you can probably predict what I'm going to say next this。

Is my old continuation or the continuation from the previous part。 And I wrap that in a lambda。

 and I give it one times res。 So on my stack， I finally put one times res。😊，Okay。

 and then we're finally done。 So we get0。 and we apply this gigantic lambda to one。

 And then what happens， I break it down from out to in in terms it's also a stack。

 You can think of it from out to in or like a stack。 I think this is easier。

 But we see that we're gonna take off this layer， right， because one will be given to res。

 So I break down that layer。And I get one times1， so I break this down。I get， one times one。Okay。

 and then I break down the outer layer once more。I get one。 I give it to that。

 So I take off this thing。And now， this is one。And now I feed it again into this。😡。

So I get the inner one， and I do three times。So I get three times two。And then finally， I just apply。

 multiply that by 2 and get 6， and I apply it to my original K。 Okay， So then finally， I'll get。😊。



![](img/6753b175e449c8050a6cbb7aeee2595e_7.png)

K of 6。And then I'm done。 Okay， I just wanted to show you this from two different angles。 I。

 I do think the original way I showed it in the sidess is clearer。 but like in terms of like the SML。

 like the way without pipes， this is what's happening。 Again， pre pendingending instructions。

 All I'm doing is that Im adding instructions to a list of instructions。

 Allright That' and that's what's happening for any one of these CP functions。 If I do this。

 What am I doing， if not just adding something onto my list of instructions where that thing is go look at R。

 where I build up except that now the picture you should have is that I have two continuations when I go look at node of L R。

😊，And I know that we're about to get out， but I'm going to finish saying this one thing。

If I'm looking at node L X R， my first action is I go and I look left。

 but I put on the failure stack。Hey。Search CP PR，R du da da。 Go look at R。Go look at R， Keep a sack。

 but now I'm going to go look at R。 And then if I fail at any point， I pop off the failure sack。😡。

And then if I haven't put anything on else by then， I go look at R， okay。

It's easier to understand like this。 but I realize it's difficult to go from the code to that。 Okay。

 but that's what's happening， Allright， okay。That's the end。


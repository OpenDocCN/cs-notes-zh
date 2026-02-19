# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P18：-18-18. Lazy Programming _ - GPT中英字幕课程资源 - BV12VChY2EF4

To be listening。 Okay， anyways， So we got a nice little graphic here， anyways。😊。

So we're entering into the last legs of the course this is the second last lecture of course content so to speak what I mean by that is that this lecture and then Thursday's lecture imperative programming are going to be the last scheduled 150 things after that I get to have three lectures of fun because I'm going to give you two lectures on special topics I'll teach compilers and program analysis and I highly recommend you come to those because it's going to be fun and I'm going to be teaching things you wouldn't be able to learn at this level anywhere else really okay and also the final lecture which I'm mandating all of you go to。

The lazy programming will be what we're doing today， so let's go ahead and get started。Oh。

 that's the happy sound。 What is this。There we go， Okay we're gonna to be talking about a few things today。

 but we got ladies lazy evaluation， we're gonna to be looking at a structure for doing such and we're gonna talk about this thing called infinitefin data structures。

 which is kind of a flashy term but it's actually really really cool and it will kind of open up the kind of array of things that we are allowed to do in SML and in functional languages in general and then some addendums on like what will actually test you on is national laziness and streams and if we have time we'll get to primes which I think are really cool。

So firstly lazy evaluation well I've got a question for you here all right you know we weve we've we've been programming an MLL for kind of a long time now I'm going to define a function for you we're going to do a little what is this code do Okay I'm going to define a first function for you this is the function gets the first projection the first component of a Tple and I'm going to ask you this。

😡，What is the behavior of first given one。And one divs zero。What's a su， that's funny。

 that's not necessarily true。Yeah。It raises dipb， absolutely why， why is it raised div？

Ca either evaluation， but like isn't that kind of silly I asked for the first projection of this tuple and this tule has one in it I know it's one why can't I get one well。

😊，This is how SNL plays the rules， but it's not the only way to play the rules。 Okay。

 so you're absolutely right that by eager evaluation， so eager evaluation。

Is going to imply that we get re to div。😡，Right。But we're not always going to be able to have that behavior depending on how we decide to structure things。

 okay？so。😡，This would only happen if the second component looped forever or raise an exception if we didn't do that。

 we would be able to do this properly。 but either way， like even if those two cases happen。

 we want to make sure that this first function works。

 and we can imagine that also if we were to have not just something that looped forever or raise an exception。

 like some really， really long computation， I don't really care enough to wait for this computation。

 if I'm going to immediately throw it away with the first function right I don't care enough。

 So let's try to be lazy about it。 let's try to do less work。

 So the way that this works biology analog also is suppose I do map F of L and the the list L is like 9000 elements long and then I cons off the verse2。

I only wanted the first two elements， but what map FL is going to do is because it's eager it's going to go and fully commit and apply F to every single element in the list now that's kind of kind of silly right so again this whole idea of by the rules of eager evaluation by doing things kind of as we can we're wasting work we're wasting cycles of our computers okay and that's kind of bad so let's try to be lazy about it。

😡，Lazy evaluation is a kind of evaluation scheme that's completely opposite to that of eager evaluation in lazy evaluation we only compute expressions。

 we reduce them to values only when their value is needed so in this example I have here for instance in a lazy language。

😊，We would get one。Okay， and the general theme about lazy languages is if I have anything like bow。

X equals E。No matter what E is， this runs in constant time in a lazy language， why。

 because what's going to happen is what normally happens right is we say。

 oh man E goes to some value v right， remember a notation from foreverbrogo E goes to some value V and then I produce an environment where I have V bound for x right。

 and then I march on my merry way。😡，In a lazy language， and this is the eager case。In the eager case。

 this is what happens in the lazy case。I just say。Let me bind E to X。I don't simplify it whatsoever。

 this E might be a super ginormously large expression like a giant concatenation of strings or addition of numbers。

 I might be able to to I should be able to apply it， but I won't。😡，So in a lazy language。

 we can also do something like this。Suppose I had this list 9999998。

997996995 and I fold over it where I take the previous thing and I multipied by the next thing and then I compute fact to that twice。

 I do a double fact all right。You can imagine this number might get slightly large on us。

 but in a lazy language， this is o of1， this runs instantly because what do I do。

 I bind res to this computation， exactly this expression。😡。

But in an eager evaluation case this would take between ludicrousacy long and forever。

 and in fact what would likely happen is it'll raise overflow in your machine。

 but let's set that aside for a second because that we usually pretend that doesn't happen。😊。

So we're going to get some benefits here in that we only want to be able to have this happen if we need that value to be computed。

 okay， and for instance， something that might warrant't needing a value is suppose I do something like this。

😡，Case。X of。1 goes to E1 and then otherwise goes to E2， right？

In in an eager language if I have x that is a value then like x is a variable right which means it must have a value。

 this is very fast， I just compare in a lazy language this is going to express the intent to what I'm going to say force we force the value here so here we have no choice but we take the you know the E for x that's the E that's bound to x and we evaluate E to a value and then we dispatch on what that value is but only once we get to like actually like scrutinizing the contents of that variable do we actually compute this expression okay。

😡，I think this is going to be somewhere here where I'm yeah so。

Basically the key conceptual conceptual difference here is variables are bound to expressions in a lazy language versus variables being bound to values in SML。

 does that make sense like in SML we always always only ever produce a binding if it's to a value in a lazy language we can bind to an expression always so there's a distinction between the cases of when I do when I do vowal x equals E。

😊，This could loop forever or raise an exception on me or just take a really long time。

 but in a lazy language all of these cases are completedflated okay I realize it keeps saying in a lazy language and we haven't worked in a lazy language so maybe it's hard to get the intuition but we're going to find that actually we can do a kind of lazy thing still in SMM。

😡，Yeah， oh I had a something simple。 okay， cool。All right， so laziness in in concept， it seems okay。

 it seems all right right payve for what you need right Only pay the computations that you actually want to use。

 which is great， I don't want to waste cycles。 Nobody wants to waste cycles right we could be doing other things for those compute time。

 we could be trading chat U for 4。5 right but instead of this。

 what we should actually be doing is we should feel more careful about pleaziness because it has some benefits。

 but also has some detriments to it。😊，So。😊，The main detriment here being something I've harped on about before。

 but predictability as a programmer as a software engineer as somebody who works with computers。

 okay you want predictable behavior if I open up Microsoft Word today and it's in tea okay and then and then the star bars on the right hand side I want to be I'm gonna to be sad about that okay I don't use Microsoft Word but if I did I'd be upset about it。

😡，Point is that when you're running software， you want predictable behavior from your language and when you're running software you want predictable behavior。

 so let me give you an example， let me set the stage。😡。

Suppose that you're in a lazy programming language like SL but lazy and you have an API that returns an int list to some user okay you've implemented some library that returns an int list all right and then somebody read your documentation online and they find your open source code and they're like that's exactly what I need I need that in list so they pull your code onto their computer and they run it and then they run your function and they take the result and they bind it to a variable right in some lazy language。

😡，And then they they go and they do those thing and they're like， thanks， all right。

 now I'm going to go do my thing and forget you existed。Well， 120 production hours later。

 their web server crashes because of an unexpected error。And you know what happened？

You handed them this list。 You handed them ra div， ra div， ra div。ok。

This can happen in a lazy language。 I can say I'm giving you an in and I can hand you nonsense and you won't know。

 you won't know until you force these values。 So suppose they were pulling on like a like some kind of API to I don't know。

 like like some bank balance。 I I don't know what the ins actually are。

 But the point is that they they passed it around to the web server and they didn't touch it and they didn't look at it for like 120 hours。

 and then eventually somebody clicked the button。 They said。

 let me look look at my transaction value。 and then raised it。😡，All right， terrible。

 absolutely awful。So。😊，It might seem ridiculous， but in a lazy language。

 every every exchange of data， every time I give you data， I'm not giving you data as in like values。

 I'm giving you completely arbitrary computation。 I'm giving you anything that fits into a variable。

 which is anything at all。 very， very dangerous， very， very unsafe， So in an eager language。

 if I'm able to get an output， and I'm able to bind it， I know it's a value。 I know it's safe。

 I know it'll never do anything bad to me。 I can trust that that variable。 All right。

 it's my best friend。 But for this poor consumer， they got three ticking time bombs。

 And that's what they were raise， raise raise time bombs that would go off eventually。

 once they were actually looked at by whatever code。

 and they didn't have the opportunity to handle it， they didn't know it gonna be ra。

 and this is actually probably a totally believable mistake。

 Like suppose this was like computing some kind of average。

 And then it divided by what the number of things。 and then the number of things was zero by accident。

Raised it， right， perfectly believable explanation。

But that you know your consumer is not going to be happy with your perfectly believable explanation of why you should handle on a time bomb okay。

 so don't hand people time bombs let's do better all right so。

It doesn't need to be necessarily even raised because what would happen is more realistically right in a lazy language I go and I hand you some list。

 I hand you X1 through XN okay and that's fine but each of these X1 through XNs might be a lengthy computation suppose I'm computing like scraping through a database to find your searches or whatever then forcing this becomes very。

 very unintuitive in terms of how long does this take if I do a case if I ever case on some kind of variable is it going to take instantaneously if it's already a value or is it going to take like two seconds。

😡，Might not seem like much， but are you going to if there's a there's a great study I read once about O。

😡，How browserrow traffic relates to how fast the page loads it's actually really insightful and basically the idea is simply that it matters a lot how responsive to the website is for how many people use it and some people claim I think that there's some popular website there that it's popularity can be attributed in part to the fact that it。

Tighly prioritized reactivity and consumer friendliness。 This is the same idea。

 If I go to click your button and it takes two seconds before I can go there， you're done。

 You're not making it on the free market。 Okay， capitalism。 capitalisms going eat you why。 All right。

 you're out so。😊，Let's not do that All right， doesn't need to be era if it could be anything。

 that's the point okay。😡，so。Ultimately in a lazy language。

 the idea is just that things like map app are constant time and only when you force it do you get linear cost and that makes it really difficult to give any sort of rigorous treatment to asymptotic analysis because then what do I do in lazy language every single one of your work span questions this semester almost always is0 of one。

😡，You're done。 right， It's constant time。 And then you ask， what about later And you're like， oh。

 yeah， you didn't ask me about later right now， it's all of one。嗯。

I remember hearing about someone who had a interview and they're in their interview。

 they were asked to reverse an array in O of1 okay and it sounds impossible。

 but like what they did is they used to return to the same array and they had like an updated access function that just like does the n minus thing。

So like laziness is kind of interesting in a sense that you can just do no work as long as you set yourself up to do the requisite work later。

 so it is possible to reverse a list to01 yeah。I literally don't worry about it， see me after class。

 this is purely a technical detail I'm obliged to put because I've heard this for years。

 butt it does not matter in the context of this class。Okay。Okay。

 I gave you a lot of negatives for lazy evaluation。

 but you know SL' is an eager language anyways right so why am I kicking the horse。

 why am I punching the bag well we can actually still do lazy stuff。Insofar as it serves us， right。

 lazy， lazy evaluation can be a cruel mistress， because what happens is when you implement laziness or when you're working in a lazy language。

 you have no choice。 Everything is lazy all the time， okay。

Be lazy some of the time we can take advantage of this for ourselves and take a few lessons from lazy evaluation when we're dealing with just regular S。

 okay？😡，So here's a question then based on that， like what does it sound like when I say binding a computation to a to a variable instead of binding。

😡，Some kind of value， that what does that kind of make you think of？I can't hear you。Okay， cool。Yeah。

 thank you。 I actually could not hear you。 indeed， it's just something a function。

 So suppose that in the lazy language， we have this， right Val re equals mathF。

 And what will happen is this won't be evaluated。 We'll just bind the computation of it to re。😊。

In an eager language。We're just going to do this。Doesn't need to be unit。

 but the point is that we put it in a lambda， we put it in a suspension。😡，This thing。Remember。

 lambdaists do not evaluate their arguments or their bodies until they get an argument doesn't matter if the argument is stupid and they totally could evaluate this that they wanted to。

 they don't， which means that this is equivalent。😡，To doing that in a lazy language。

In an eager language， this is the eager language to be clear， okay， but by by analogy。

 we can do this kind of thing where we don't do the computation okay？😡，All right。

 so the point here being and you know， in a different class I might harp on more about this。

 but eager languages can simulate laziness using these lambmbdas and that's exactly what we're going to do today。

😡，This is called a thunk。 It's a technical term。 I'm so serious about that。

 A thk is a value of type unit to T or some type T。 We can also call it a suspension。

 It's called a thunk。 You can go back in the literature。 I don't know why it's called that。

 But the point is that for any expression E， I can turn it into a thunk by encasing it inside of an FN unit goes to。

 And then now it's suspend。 Now it doesn't do anything until I go and I actually evaluate it， right。

😊，Okay， so the key factor here is that lambdas will suspend the contents of their bodies right always。

 always always， if there's one plus one inside of a lambda。

 it doesn't happen okay until you get the argument。啊 okay。Sure。

 and I'll say again like like the point of laziness is that we can do it when we want to so we're going to see select cases where it's useful to be lazy in SmL。

 but the things about like， you know having an API and me handing you three taking time bombs like that will not be a problem in SL okay。

 that will not be a problem in what we're doing。😡，And this is a general concept of if you have a language feature。

 generally it's better to be opt in than opt always okay we saw this with mutability in a sense what we're going to do next lecture we're going to see that mutability is only a demon if it's on all the time okay opt into language features that are contentious don't I have the one by default and this is a general kind of like。

😡，APpiI design thing probably I guess I don't I never took a class in API design， all right。

So that's going to be our policy， simulate laziness， don't opt in all the time Okay， all right。

 that'll give us the benefits without any of the detriments， any questions on this section。😡，Yeah。

Yes， but like limitedly like like yes， but in like a hacky like stupid way or a Haskell has some certain Haskell is the premier example of a purely functional very lazy language and it has certain things that let you force expressions but the fact that you always by default have these things around means that it's it's just not good for you at all yeah and I think there's also some technical problems with that there's a blog post about that I can make it yeah good question Okay anything else。

😊，No， I'm running low and high shoes， so the answer is no。

Okay let's do a lazy structure so laziness is so powerful that we're gonna to have our own module in our own type for laziness so that we can be very。

 very clear about when something is a lazy value right here is our signature right the signature for lazy is going to be containing some type alpha t and alpha t is like and the way you should always think about alpha t is some manner of box some manner of box that has something to do with alpha and the point of this box is that a lazy box is one where the box contains alpha but only once you force it okay it contains a suspension of type alpha and what I mean by that is we're gonna to have a function lazy that takes in a literal funk that returns alpha and then it promotes it into a lazy a lazy value okay。

And then Bo is going to take a lazy value and then give us back out lazy the lazy value that or it's going to take a lazy value and give us the value that that computation evaluates to。

😡，Okay， and we can implement a like so。So。If I wanted to implement this structure。

And we call it lazy， and I want to scratch opaquely to lazy。In caps。

 it's a little confusing that these things read the same。not saying sub。And okay， so。

Note that I've left the type of alphapha T abstract it's because to a user they shouldn't have to think about what the heck this type even really is okay it could be anything right but the point is it encodes a su computation so you know like we could do a lot of work。

😡，Or I could just say this。This is going to have the same type。

It's going to have the same type on the inside， but now to someone using the structure。

 like they don't know， they get to maintain that conceptual divide between something of blazy type and not。

And that means that。Fun lazy is simply going to take in a unit to alpha and return alpha T。

 which is also a unit to alpha， so it'll be the identityi function。And then my forcing function。

Which takes in a alpha T， which is a unit to alpha function， takes an f。

And then it just calls Ethon unit。And then I amm done。Anything contentious about this。

 everyone clear on this？This are very young。Yes， indeed。

 if we wanted to have this be alpha to alpha T， this would no longer work because what would will happen is that we'd say lazy。

You know， like。Luke Breer。And then wed loop forever before we entered blazing， so yes。

 in in either language we do need to create the T first， the T has to be static。Yeah， okay。

 that's a good observation。Yeah， so one thing I'll note about that also is a， well， okay， huh？哦啊嗯。

You can get a vote so okay。All right， okay， what is this what is this Ha ch communism You're just passing all around distributing。

 Okay， all right， we got two left to do that too， so make it a good one， I guess Okay。

 so was I saying oh my God。😊，Oh yeah， in certain extensions of San MLl there。

 you can do this kind of thing where you do give it like a keyword lazy。

E and then it does create the T tree automatically， but that doesn't happen。

 so forget I told you that don't do that on your homework， you'll mess up。

But just saying that like that can be a syntax extensioncension， right。

 most things can be syntax extensionions okay。Alright。

 so that's how we're going to use this lazy structure。 All right。

 and we can use this because what happens is that eventually I get to pass around values that have type alpha。

 lazy。Dot T。And that's pretty darn indicative， this says I'm holding a lazy value。😡，So again。

 this type level distinction is also a useful conceptual distinction in your brain on what the heck this thing really is。

😊，O。All right， okay， and then I showed you the implementation，lah blah blah， blah。😊，Alright， so if I。

 for instance， gave you this code where I said tabulate a list of length 100。

 such that each entry is going to be lazy applied to a thk that computes the， you know。

 I square number。 Now I'm not holding a list of the of the one through 100 square numbers。

 I'm now holding a list of lazy values of suspensions of those square numbers。

 It means that I this will， first of all， in an eager language。 Okay。

 we're not talking about the lazy language anymore or this is eager。 This also runs in like， well。

 it runs an O event， but it runs in not needing to compute。😊，This。rather， it compete this。

 but it doesn't compete this。Okay， you know， the language that's confusing for this。

 they are suspensions of each square number that can be forced later。 All。

 And and this is contrived because you know， this costs almost nothing， right。

 But you can imagine putting some really freaking expensive operations behind each of these suspensions at work。

 this is something we do because one such use case for you doing this is not having to do I O not having to read from the file or make a network call unless you have to Okay so like this kind of thing like if you know you're eventually gonna do it。

 but you don't need to do it now， maybe it's better to wait dynamically and see if you really need the suspended value。

 So the point is that like depending on what the code does after this。

 we might see whether we actually compute the square number。 but that's on a case by case basis。

 I don't need to。 So I might as well not。right， So this can be very useful。

 even though this examples contrived is what I'm trying to say。

And then finally in languages like Haskell， we also memorize these lazy values。

 so that means that we only compute it once and once we've computed it once we remember always what that result was。

😊，This does not do that there is no memorization here as in as in if I force the same lazy value twice it will take the same amount of time approximately and I will have if forcing it once takes three years。

 forcing it twice will take six years it doesn't need to but it will all right so that's something to know as well we couldn't implement this in a memorized way and I believe there's actually a review web problem on this called Haskell I don't know if we're running it but it exists and I kind of like it。

O。What time， all right。They put yourself lazy in the lazy mindset， okay。

 you might as well not have take in the quiz until you get the until be fourth of the grades， right？

Okay。Part 3， something very flashy。 I got it for you。 Infin data structures。 Allright。

 infinitefinite power，80b leaving space。 All right。

 so we're gonna be talking about data structures that can be potentially infinite。

 And I'm gonna put this little scenario into your brains。

 and we're gonna think about it for a second。 But suppose the CEO of your company walks in the room。

 And she says she wants all the integers。 And you you pause for a second。 And you're like。

 I don't know about this boss。 I don't know if you know， but the integers are infinite。😊。

And she says， yes， actually I'm very perfectly aware of that are you talking back to me and you say。

 okay， yes， I will have the integers on your desk by next Tuesday， All right。

 realistic corporate example， by the way， don't backtlk right， she knows the yeah， anyways。Oh。

 you know， this is not dissimilar than the following image， okay？Mom， can I have all the integers。

 no， there is all the integers at home， but all the integers at home is this code where I say integers n is N cons negative N cons integers n plus1。

😡，And then I run I run this on one and icons zero to that I don't know if you know this。

 but this code loops forever， okay， they only need justification as to why this code loops forever。😡。

没有。Can I trace it through it's going to be an infinitely long trace， so no。No， well yes， but okay。

 the point is basically actually to be fair， I've actually never tried the negative operator so it's possible theres a bug there。

 but anyways。This takes an infinitely long time to evaluate。

 This will never terminate because guess what， the integers are infinite。

 I can't hand you a list containing all the integers， okay， so。😡。

All the integers this is not this is not a okay， we need to think of something better So we're going to be able to write a function that's very similar to this actually。

 but we will actually be able to hold all the integers okay。

 and then you will be able to appease your CEO who wants all the integers Okay here's the issue。

 We need to make sure this doesn't loop forever So let's contain the looping forever Let's use laing it。

😡，All right we can nicely define the integers but the fact that we can't do it because we don't have infinite amounts of space like that's that's kind of a lame excuse okay if anyone ever says physical constraints is the reason why you can't do anything that's a lame excuse okay so I remember I took a class on quantum computation and on the very first day the professor comes in and he says all right this is nothing to do with engineering nothing to do with like physically housed is possible。

 assume you have things called measuring devices which are the key of quantum computation and then we assume that they existed and then we did that for 15 weeks okay same thing here all right except better so physical constraints kind of lame。

We also know that it's impossible to have infinitely made processors though right and that didn't stop us。

 so let's not let this stop us now all right physical impossibility is secondary to our concerns。😡。

Infinite data structures are a kind of data structure that can store infinitely many entries and they don't need a loop forever to do it okay but they can store they can quotation mark store and the reason why this works is because we're going to play around with the idea of what store means。

😡，Memory concern is legit， we can't use a list， but what we'll use is we're going to use something called a lazy list。

 which is a list that can be infinite， can have infinitely many entries okay。😡。

It's sort of like this right if you told me you wanted all of the natural numbers。

 it is perfectly fine for me to say。😡，Yeah， I'll give you all the natural numbers。

 you can have zero and you can also have successor of any natural number。

I have given you every single every single natural number okay。

 that's a perfectly fine way it's a just satisfying way to do it。

 but you didn't say to do it in a satisfying way， you told me that you wanted all the natural numbers so it's like kind of the point of laziness is is kind of like malicious compliance in a sense okay here's the idea。

I can define for you this data type， which is real SML code for ones。😡。

And this sttype alpha list prime will be the new constructor or the cons constructor of alpha and an alpha list prime Okay。

 so you should be able to convince yourself this is pretty much exactly equivalent to the real lists。

 Okay， but I'm showing you that we can do this so I can draw an analogy Okay so this is almost exactly equivalent to alpha list it is exactly equivalent。

😊，But here's how we're going to define lazy lists。Instead of storing a value or rather。

 like storing the list value of the rest of the lazy list。

 we are going to store a suspension of a lazy list。

What this practically means is that a lazy list can。

Not necessarily have to come up with the rest of the list。

It only has to have the ideas of how to make the rest of the list。

 this is kind of like the zero and successor of zero of any natural number idea， okay？

And with this data type， we are going to be able to encode infinite data structures， okay？😡，Okay。

 so what does this mean if I want to make an alpha L list。

 I have to I don't have to come up with exactly the La list。

 I just have to come up with a lambmbda or any kind of function。

 a recursive function would sice as well。😡，So sort of by analogy to what I was saying in CP lecture we have a list that has instructions that tell us how to make the rest of the lazy list and that is itself a perfectly fine list so heres some examples of values of type T list L list actually I think all these are of type in list this one's actually alpha Neil is going to be a type alpha L list makes sense right if you if you remember polymorphism that's how it works。

😡，Cons of one comma， a thunk of nil， right， it needs to be a thunkk of nil or a won T check。

Howuse type int L list。Cons of one comma， a thunk where this thunk itself is cons of two comma a Tunk of nil is also of in L list right it looks the same as like a list。

 but now instead of being able to just cons onto something directly I have to take the suspension first okay but also this one I don't need to have the cons there in fact I don't need to give you anything at all is an alpha this is an in L list that has one out on it okay and then when you ask for the next element it's going to loop on you forever。

That's the price of laziness， yeah。Thank you。Oh actually， I think it's less readable that way。

 But yes， So we can just do this book you point me off my rhythm。 You expose it and it loops forever。

 That's the price of laziness。 When you expose a lazy structure， you might get anything。

 You might get a lazy， You might get infinite loop。

 You might get a really long time and you might get a lazy exception。

 Okay and it might also come up to you with cons again or nil or whatever。 Okay。

 But the point is that this thing here can be like a recursive function call or a recursive function。

 And that's where we get into the really interesting territory okay。😊，Yes， okay。

All right so now instead of writing down something in a finite amount of space。

 what we're going to do is we're going to use a rehearsive function to encode the instructions of the rest of the list。

 so here's how I would write the natural numbers as a lazy list。😡。

I saynats from so I need a place to start I have an accumulator which is the nat I'm currently on okay and then I say okay this this la list must be cons where I have n my current thing and then a suspension that generates every natural number from n plus one on right and that should intuitively make sense to you if I want to give you。

😡，All of the natural numbers greater than n， I give you n and I give you the rest of the natural numbers greater than n。

 it sounds dissatisfying， but in code like this is a perfectly fine way to do it。😡。

And then if I wanted to get all of the natural numbers， I'd say。Start at zero。

Note that like one thing about this function here is that it doesn't have a base case it doesn't need one most I would say yeah。

 most stream functions sorry most lazy list functions don't need a base case you can just do it like this Okay so we're not looping forever we're just。

😡，Petering out our we're segmenting。Our evaluation if we wanted to go and compute all of the natural numbers。

 yes we would loop forever， but what we do is we chop them up into discrete bite sized time periods and then separate them by each end and that is fine in practice。

 yeah。😡，If you want to have a lazy list， you might want to be able look exactly okay so one one reason so you can reverse a list over one and pass a job interview okay the second reason for this and the second reason is for this being that having lazy data structures is sometimes useful because you don't want to actually pay upfront the cost of what you're doing laziness can help you if you're trying to save on like performance and you don't really care about and you're aware you are careful about the detriments I told you about previously but there's no reason why like this is any less useful to you than having the list in a real form so to speak。

😊，Oh that is those are two very different。 That's it's kind of funny how those are Okay。

 how do you extract the value from this， Yeah， so let's get into that Well what's going to happen is that you can pattern match on an alpha Els right and alpha Els has the same structure where you say it's。

😊，Goon to be da。Nil or its's cons of an element and then the rest of the tail of the L list。

 so an extracted value from a lazy list， you just pan or match on it。

 you have Neil in which case you have nothing or you have cons in which case you have the first thing and then if you wanted to get more you could optionally force the rest of the L list。

Okay so it doesn't look super different it's just that when you pattern match you don't you're not guaranteed to get the rest of the L list you have to go and compute it for yourself however many okay it's a cool function take where you like can convert an L list into a list by saying I want to take the first and elements I haven't put it on the slide for you here but I highly suggest that you try to implement it yourself I think it's a good exercise okay and probably you'll it on like the lab or the homework whatever but it's a good exercise。

Okay， all right， extract value， Jesus， okay。Suppose I wanted to construct a lazy list from an arbitrary function that is I wanted to tabulate in the same way as I have my list I tabulate and I'm sure what all of you are familiar with by now your sQ list sub tabulate okay lazy tabulate is going to take in an into alpha function and give me back an alpha a list and in fact what it's going to do is what's kind of interesting is I don't need an n right I don't need to say of length n it'll just do。

😡，Whatever that function is defined to be， maybe it raises an exception， maybe eventually。😡。

It says that loops forever， but lazy tabulate doesn't need an index， okay it doesn't need a limit。😡。

Okay， and here's how I would define it， oh whoops， I should write this on the board， sorry bye。Okay。

 let's do it。So let's do lazy tabulate。And what I'm going to take in is I'm going to take in a function app and now I need to come up with a list right so what I'm going to do is well。

😡，I also need to have some kind of like index， right I need to know where I am。

 so we're going to do this recursively and by storing。😡，An index okay。

 we're going to say that we're going to calculate tabulate from I onwards， Okay。

 this is kind of a recurring theme with La list we saw this kind of like onwards thing。😡。

And then what do I say， I say cons， actually let me do it this。😡。

I'm going to say that I'm going to have kinds where I take the thing I'm currently at。

 which is F of I。😡，And then I return a suspension。A suspension of lazy。Tabulate prime。

 right my helper again。Where I give it F and I give it I plus1。

And then if I wanted to define lazy tab， I'll just do it。No one can't do it that way。Sad。

I could partially apply it， but I can't actually。So lazy tabulate of F is just going to be lazy tabulate。

😡，Which is a really long function name I realize now。Prime given F given zero。

Does that make sense for everyone？Yes， it does it does indeed very good observation we're going to get to that in like three slides here that's precisely what it does next thing I wanted to to tell I'll get to it we'll see what that is al right。

😊，So this is gonna to be the function and I'll get to the what he just said in a second。

 but do people trust me that this is like lazy tabulate from zero onwards I just straightforwardforly do it。

 I don't have a base case because I get to run wild in here I like to call this place Tunkland。😊。

When you're in a Tunk， this you're in Tkland and in Tunkland nothing happens。 Okay。

 but things could happen。 All right， it's like a job offer like like everything could happen。

 but in practice， nothing happens。 Okay， sometimes， all right， so if we tried on a specific use case。

 what I could do is I could make a lazy list such that I get， I don't know， for some reason。

1024 divided by every single natural number ever by every every single natural number ever right I could do that。

😊，But what do you think is going to happen based on what you said？Raise deep。

It purportedly contains all of the results of dividing 1024 by every natural number， but doesn't。

 because the first natural number and fight me on this if you don't think this is the case is zero。😡。

Which means if divided divide by 0， I'm going to get raised it。

So we're not going to have anything and that is not lazy enough okay。

 this is like pretty lazy it's like marginally lazy like it's not it's not to the point of laziness that I like it to be the right because all I said was all I said was I wanted to be able to have。

😡，A lazy list that every entry was 1024 divided by I。

 but I never said I wanted to look at each element there's a difference there okay so what we're going to find with lazy list is that they're not lazy enough because we have no choice if you go to and look back at the definition which is way too far now。

 but we haveil of nil or we have cons of you know。😡，Alpha star， whatever， okay？

But the point here is that if I have cons， I must be holding the first element even though my value must be holding the first element。

 even though I never necessarily said I want to look at the first element。

 these are two different things having to hold it versus expressing the intent to look at it。

 those are not necessarily always go together okay so we're going to try and come up with something where we don't need to have this problem。

😡，We're going to have an improvement on lazy lists called streams and the point of streams is that a stream doesn't have this issue。

 a stream。😡，Is like a maximally lazy data structure， let's say okay。In that。

I only ever have to compute something if I expressly say， yes， I want it okay。😡。

Is this concrete enough of an example for everyone？Does everyone get what I'm saying here between。

 okay？Okay， speak now or don't。All right。Maximmal laziness and streams。

 so the definition of maximum laziness is one that definitely doesn't compute any element until it's absolutely needed。

😡，Maximmal laziness will mean something slightly different on your homework。

 but in intentiontion in intuition， this is what you should have it mean， okay。

 it means we don't do any work until we absolutely， absolutely have to the first element。

 we should have to express the intent to look at it before we force it。😡。



![](img/4d720fc990d9282f09aeb2a8fc786573_1.png)

Okay and this is going to be our type let me write it down on the board just so that you have this proposterity。

 but it's gonna to be two types actually and the cool thing about this type is that it is mutually recursive which is an idea that I've alluded to and I'm pretty sure I showed you a mutually recursive function at some point but it's going to be this so we have a stream a stream is just something where it is a lazy a lazy list essentially but a stream you need to explicitly say yes I want the first element before it gives it to you so that means that a stream is going to be a suspension it's going to be a thk of something called an alpha front。

😊，And what is an alpha front， well， let me tell you。

I use and this keyword here because I'm defining a mutually recursive type。

 both these types will see each other。😡，And I have that in alpha front。Is going to be？

The same thing we said earlier， nil or cons。Of alpha star。 But now。

The tail of a front is another stream。Now this this might look very。

 very similar okay and it is very， very similar， but it's not exactly the same because what's going to happen is we essentially adjust for this off by one。

😡，If I am holding a stream， I'm always holding a suspension。😡，Whereas with the lazy list。

 I would always have to be holding a value of the first element， yeah。



![](img/4d720fc990d9282f09aeb2a8fc786573_3.png)

Like if I had taken away the stream and I had alpha lazy dot T here， alpha rather alpha， you know。

 front lazy dotti。That would be equivalent to lazy list and wouldn't be equivalent to streams。

 I need this guy here to make sure that I am mask me lazy and I don't expose the person element。Oh。

 oh， I see what youre， you're going to make this lazy。Yeah， thatll be fine as well。

 Thatll be fine as well， yeah。Yeah， that would be financial。Yeah， yeah， yeah。

 you could do that as well because as long as you don't do the work to do this until you really have to go。

I think you could also there's the thing i'm when you get into like these kind of stuff that you start playing type isomorphism i'm pretty sure that would work but there's like a bunch of different ways you could structure it yeah if you don't quite see what you're saying it's fine this will be the clonical way that we do it it is kind of interesting to think about different ways that we could formulate this but。

😊，That is the point of type ismorph results， which you can take 32 to learn more about。

 okay all right。Okay， does everyone see， though， like， actually。

 I have another slide to explain this。 Let me explain it first。 Okay， so conceptually。

 how I want you to think about a stream in a front。A stream is a delayed front。

A front is an exposed stream。This might seem like a circular definition and it is。

 but it's not circular in a way that's not useful， okay？😊，A stream is a data structure。

 a kind of lazy list where you have no license to look at the elements yet。

 there's a type level distinction between if I have a lazy list versus a lazy list where I'm permitted to look at the front。

😡，A stream is a lazy list full stop， I'm not allowed to look at it。

A front is a lazy list where I have license to look at the first element to turn to be able to look at something。

 I have to mutate the not mutate， but I have to change the type from an alpha stream to an alpha front before I get reason to look at it okay so we can be very very clear with where our computations fall based on whether or not we have an alpha stream or if we have an alpha front but if you have an alpha stream no no dicey you can't see anything this is just a suspension nothing nothing to it okay but if you have an alpha front now we can play ball now we can now we can actually you know look at what's in the front all right。

😡，Another way to put it is the only thing you can do with the stream is force it。

 but when you force it you get a front where you have that intent to force I alluded to earlier。

 you don't necessarily have the intent to force with the lazy list。😡，The front is our raification。

 that manifestation of intent to force， you have a question？Let's start with the stream。

 let's start with the stream stream will be the canonical thing point is that upfront is like a degraded stream where we have expressed intent of force。

 but the stream comes first。Okay， yeah， yeah， but that's a good question because we can start from anywhere。

 Yeah， and if we started from here， actually， I we would have the same issue。

If we started with the front， we solved it off by one really iss what we did， okay。ok。

Where I put the end， this one needs to be heard the second if it has the end at any rate like I could I could do I could have done data type alpha front equals and alpha strain equals stream is first because the conceptually shame is the first thing yeah yeah yeah but doesn't actually matter yeah okay。

Okay we're going to have our own signature for streams and it's going to look like this and I'm just going to tell you this part which is we already saw。

 but the point I'm making is that stream is an abstract type to users of the stream library and this is the real stream library you will be using on your homework you don't know what a stream is。

😊，And that's kind of problematic because now you need to be able to interact with the stream。

 you need to be able to make a stream so let's expose some helper functions that will help us with that okay。

 but this is defined exactly the same way we're going to have a structure stream that we're now talking about implementing that okay。

😡，So at the online 150 documentation we're going to see this。

 you can see this structure but it'll be implemented like so with the same type that I just showed you right and then we're going to talk about what comes after so first of all I need a way to make a stream we're going to call it actually I think I give you the specs first。

😊，We're called delay it's going to have the same sort of same sort of vibe as a lazy dot delay right if I have delay I taken in a unit to alpha function sorry that should be alpha stream my bad。

😡，You take in a unit to alpha stream， a suspension of an alpha stream， and you turn it into an oh no。

 no， I'm wrong， it's a unit to alpha front。Sorry， yeah。

 basically the point is that we should be able to define delay as such， this is the point， okay。

If I delay F， I just。Good that。Sorry， yeah yeah because I take in the unit to alpha front function and I just wrap it in stream Delay is very uninteresting in terms of what it does。

 But the point is that this will let us do the type level hackery that we need So units to alpha front quantity。

And then promote that to an alpha stream。 Okay， we've。

 we promote a suspended alpha front into an alpha stream and then expose， takes the stream， and then。

Expresses that intent to force and then we get an alpha front so as soon as we do expose we are now holding a value that tells us yes。

 you have you have asked for the first element this is like the ultimate case of parse don't validate like by holding an alpha front you know that you force something I cannot be holding an alpha front without having forced something okay。

😡，Or creating them manually， and so exposed will be defined as such。😊，If I have exposed。

 I take in a stream and stream is one constructor， so it's actually okay for me to do this。😡。

I use case on the one constructor here in this clause， and I don't have any other the cases。

And then I just say。Let me use this F function of type unit to alphapha front and get back in alphapha front as a result。

 because that type check to everyone？😡，Very uninteresting functions。

 But the fact is that these two functions are going to be exposed in the stream signature and it's how you interact with streams。

 and someone asked during during the quiz about like why I should want to do delay and expose as opposed to like just using function application This is very deliberate if you want to define everywhere in a program where you expose or delayed you just control F for delay or expose So it' it's very very explicit in the program text what you're doing right these are our functions。

 we will use them to define cool things now okay。But not that one。单神。everyone clear on this。

Allright and that was the implementation blah， blah。

 blah all right so we're going to use these helpers and then we're going to define some cool functions the first thing we're going to do is we're going to do the natural numbers and the key to doing I'm going to have time to do the prime example that's so said the key to doing the natural numbers is that what we're going to do is define two functions。

😊，One function operates on streams and outputs a stream。😡。

The other function operates on a front and outputs a front okay， actually for the NA example。

 we don't need to do that hu we're going to do this is shoot you know。😡。

We're going to illustrate to this， so here I have a function that gives back a stream and a function that gives back up front I'll do the other example on the board。

😊，If I want to form an in stream starting from I， NAts will be the one that's taking care of the stream。

 I delay a call to the front function， okay the front function is responsible for just coming up with a front and it says I want to have cons of I and then a stream。

😡，Where the stream is NAA by+1。You could also inline this okay。

 you could do FN Uni goes to cons of I you know NAts I+ one that would be fine。

 but the reason why we do this is because particularly if there's some later functions。

 this will be helpful in terms of like making it conceptually very very clear。

 one function gets a stream， one function gets upffront okay one type one function right one function。

 one type。😡，That's not true in the presence of polycy。Yeah。

 so we could have done it this way all right， do however you like， I recommend this way。

 I find it useful okay。😊，Let's do tabulate again， but let's do it for streams well what we're going to do is something similar。

😡，If I wanted to do tabulate but a function， I would say f I。

And this is going to be tabulate prime actually， what we're going to find。

 and then this is going to be。Delay， the same stream of delay I told you about。

I've taken a suspension of an alpha front， so I say tabulate prime。😡，呃。Well。Let's say this is prime。

 this is prime prime， okay？😡，Tabulate prime prime given f and I where tabulate prime prime is responsible with coming up with the front okay。

 we could call them other things， but in practice in this class what we do is we call it one，😡。

And then we call prime， the other one。It's not necessarily great， okay。

And what we're going to do is we're going to do cons of F given I。

 and then I need to come up with the stream if you remember the type the types over here that's so convenient。

 I need to come up with an alpha stream。😡，So I call the original function again。😡。

So I call it tabulate prime。Give an F and then I plus1。Note the circular idea， Okay， sorry。

 I need to end don yeah。I need and so I can define them so they are also mutually recursive because what tabulate prime calls tabulate prime prime。

 then tabulate prime prime calls tabulate prime Okay mutual recursion。

 we just use and Okay this is the same idea as。Same idea and then these helpers。

 then we you just write tabulate where we start at zero， okay。

 usually for these index based things we need a helper that takes in the index。睇。😊，Iこで。Okay。

 we haven't used expose yet， expose is usually used when we're writing a function on a stream。

 not a function that simply produces a stream。😡，And I want you to also understand like understand why this tabulate is more lazy than the lazy tabulate we saw earlier okay。

 try it on the same example， see what happened and some of you some of you might get it now but there's a reason why this is we did this and this that's because this tabulate is actually more lazy okay。

😊，All right， but like most data structures， what we can do is we can write a map function on streams and you should be very familiar with this type signature which says I take a map function。

 I take an alpha something and return a beta something okay。😡，Here's how we're going to do。

I'm going to have map right， and I take an F and I take in a stream X。😡。

Here's where the divide becomes useful。 I want one function to take in the stream。

 which is map right and output a stream， right， So let's write that function。😡，Well。

 here's what I'm going to do。I'm going to delay。And then I'm going to make a suspension。

That simply takes the front of this stream and produces the corresponding beta front I don't just want an alpha to alpha stream function。

 I want an alpha front to beta front function assuming we had such a function and it was called map prime。

😡，We're going to do this okay and it'll make sense once I write the next function， Okay， actually。

 let me write this ston。😊，So map prime， and I'm running with very little chalk right now。

This one takes an a front， so this one has two cases。😡。

Two cases get to I get a case on the front now， so if I've emied。If I have the empty front。Well。

 I can only give back the empty front， right？And then if I have。Cez。

 I need to break this whole thing out。F given cons。Of x， and then what do I have， I have a stream。

X comma S。I want to map this front， so what do I do， I just map the personce there， right？😡。

And then I recurse right， so for this stream， if I wanted to map this stream， I call map。😡，哎。S。

And now we have to make the types work map Prime takes in a front and gives back a front right so I have to give map Prime a front which s is not so what do I do？

😡，Before I pass the stream to Ma Prime， I expose the stream。😡，Okay。

 it's a little subtle how this works， but here's I want you to think， okay， first function。

 first function。😡，Is simply alpha stream and gives me back a beta stream。

 It does more stuff than that， but in the intention。

 that's what it does right And then the second function takes in an alpha front。

And then gives us back a beta front， okay？What is a stream， a stream is a delay of a front。

 so we map the front， but first we have to expose it。😡，And then when I deal with the front case。

 this is easy， I just do the empty and cons thing， but I have to map the stream how do I map the stream。

 oh， I happen to have a function which already maps streams。睇。😊，You can inline this。

 but I think this is a useful conceptual separation。

 I think this makes it a lot easier to write these functions， one function for streams one reference。

 yeah。Yeah， yeah， you know， I do I do the scoping in my head automatically， but yes。

 S prime would be fine as long。Yeah better了。Any questions on this function？

Maybe a little time to get to the right yeah。It's it's not an interesting case really like you can define a function of take which takes the first and elements of the stream and then you just do stuff on list pretty much and this is a function which takes right because look what we what do we have to do I had to look at each element of this strain in order to do that so it's both where this is generation and disruption of the stream。

Yeah。Is that a question？All right， cool， no worries， okay， if everyone's cool with math。

 we will move on with Gusto。And that's， in fact， what we have to do。

 but I'm going to caution you here because we could have done this in a pretty bad way， okay。

 here's the bad way we could have done this。😡，I'm not going to write it all out。

 but here's how we could have done it Okay okay so we're back in that。

 this is a stream and I want to produce a stream right so the first thing I do is I expose the stream and if it's nil I return the delay of Neil。

😡，And if it's kinds， I return the delay of the right thing， right？😡。

There's a big gaping problem we got here， what's our problem？What's the issue with this code？F of X。

Well that was fine。It has something to do with the thing about here's the thing right if I'm mapping a stream。

 I have a stream which is like a delay of a lazy list that's maximally lazy。

 it means I have not expressed the intent of port。😡。

So why should mapping a stream cause an element to be exposed Why should mapping a stream cause an element to be forced without me first saying I want to force it The problem here is as soon as I call map the first element of this function is exposed which means that I try to expose this but it might loop forever it might raise an exception it means I just mapping a stream is going to force the stream which is not want to ask for I want to be massively lazy I don't want to force if I'm producing another the stream on end the stream。

 I should not force elements of the input stream until I have to and until someone forces the mapped stream。

😡，That that intent has not been displayed merely mapping is not the same thing as forcing okay so what happens is I got two gung ho about it do you see the difference here with this function in that function this function I delay all this front nonsense I was going to do so the front nonsense only happens if I exposed and I get rid of this stuff but here with map。

😡，Automatically， I suppose， even if I didn't。😡，Do an out call to expose on the produced map stream。

 okay？😡，I have pretty much exactly the same sort of problem as Tvit where I got to Gusto and I looked at the first thing before I had licensed it。

Do people see why this should be the case？And speak up now， please， if you don't。Okay。

 we'll move on about from that， but yes， try running this code in your re and see and see what happens if the first element should be like whoing forever right you'll see that mapping merely mapping is going to cause the first element to be exposed and youll look forever which is big bad okay we don't like mapping but we don't like whoing forever。

😊，Okay， so only in general， when you're writing these functions and your homework will make this very clear to you。

 but don't do stuff on the rest of the stream， don't expose unless that expose is locked behind a delay in general。

 okay， in general is not a good idea， especially if you're operating on a stream okay。😡。

All of this stuff should be in Tkland because exposed for expose。

 but here you get exposed either way， all right？So just be careful with that。

 the fact that it's not under a b is the big problem here， right？We'll move on to that。

 and I just wanted to talk about that。Bh， bh， blah。

 bla okay I told you earlier and let me also give you this definition。

 which is you'll see on your homework a productive stream is one where expose always terminates with empty cons。

 which where the S prime is again productive productive is just a keyword we use it's a vocab word we use to mean a stream that has well defined infinitely many elements rather not even infinitely but it has well defined elements it means expose never loops forever。

 it never raises an exception that's all it means it means that you can continuously expose and you will always get empty cons。

😊，And that's all the intuition I need to give you for that。

And generally we like productive streams because again。

 we don't want loop forever or raise an exception， but map has a curious thing where you could take in a productive stream and make a non-productive stream。

 right， because what if this F raises an exception？😊，So be careful with stuff like that。

 that's something to be wary of， okay。But also this will help us describe the specification of certain function okay for instance。

 we have the stream append function where if aend takes in two productive streams it should produce a productive stream so again this is append is exactly the same as our normal list toend。

 but we're going to do it with streams。😊，Do people see why productive will help us in this specification。

 like if I get two productive streams， a pending them should again produce a productive streamemia。

 like one that has wild elements yet？What does Roten mean？

Productivity is a word we used to describe streams that is to say like you can expose it continuously and it will always give you empty cons。

 always always always and so on and so forth if you keep exposing。😡，Basically。

 it will never loop forever to get the next element。

 it will never raise an exception to get the next element， which are possible scenarios。😡。

We want to avoid that， so we use productive to describe streams that don't do that。Yeah， oh yeah。

 okay， cool， but sorry I know I glaz over this kind of fast。

 I I just really like the prime example I want to get to it， I don't know， I'm selfish。

 I think it's cool。😊，Okay， so okay， well， I'll write it out， Ill write it out。

So if I wanted to append two streams， same deal， all right。

 I'm going to have one function which operates on the stream and gives us back a stream。😡，啊。

S1 and S2。Nub for nub。A little better。And then S2， and this is going to do the append thing so first off。

 immediately what I do， I delay。😡，I delay a call that does the thing on the front。

But what do I delay， let's wait on that for a second， okay。

 and then I'm going to define a pen prime which gets a front and produces a front。😡，So in particular。

 I don't need to force both of these guys， I only need to look at the first stream I claim to you to do this app thing kind of the same way how we only have to look at when we' we only have to look at the left list right when we're apping right so same deal here。

😡，If I have empty。And just trust me that this is how we're going to do it if I have a empty here and I asked you。

What stream is aend of the empty front NSU？S2， thank you。 Indeed， that's correct。

 And then if I wanted to append prime， what's my next case。I'm going to do cons， right？

And I have x and then S prime， let's say。S1 prime maybe even。And then I have S2， again， okay。Well。

 if I wanted to append this， I'm going to keep X on the front and I have to I have to produce a front right that's what this function does Oh sorry it。

😡，啊。喂。I don't have a front。Let's just do em ma。O。Sorry。

 I have to make the types work out I have to return a frontier if I return S to I'm getting a stream sorry my bet in fact I probably made the same type on the slides we'll see okay。

😊，Just trust me here。 This one takes up front gear is back up front。 Okay。

 and we're just going to keep。 I'm trying to make the type match。 Okay。

 and then if I want to give back up front here， I say cons。😡，And I keep the first element。

 but now I have to come up with a stream， right， do I have a thing that can make a stream out of two streams。

 oh， I do。😡，Call the pen， right， exactly。So I append the S1 prime， the tail of S1， and then S2。

And then here I only have one thing I can do， which is that I have to make the types match。

 so I have to give it a front and a stream。😡，So we're going to do append prime。Where to get a front。

 I expose S1。And I'm going to run of room here， but I'm going to put them on top of each other。

As good computer scientists too。Sorry if you can't see that。Yeah。This is coming here。那话。O， thank you。

 thank you。Yes， indeed So now that yeah。Yeah which is a good thing yeah we never will access it until this thing is empty which it never will be that's fine it means that our append function will always carry around S2 but never force it if if the first thing is infinite because what's the case where we force S2 only when the first thing is empty the bi hypothesis utop is infinite。

It'll just always be carried around as a useless argument the code doesn't know thats important you you know。

 so that's fine。明白。Yes indeed yeah it would be in the closure of the function Yes indeed yeah good observation okay is everyone clear why this function should work and and if you have concerns about this expose being like maybe not nationalally lazy。

 the reason why this is useful again is when we operate on a front we already have been given permission to expose so that means that if I'm buying to expose S to because I was asked to expose the pen of these two things and if I can't do this then I have to do this。

😊，No， I' have no， I have no choice。 So by doing this type level thing， I kind of enforced。

 I'm forced to do the right thing here。 That's kind of why I like this， yeah。Yeah exactly。

 so like the second function you have license to expose because your're inside phone clam you have to get here you had to have already exposed yes。

 yeah。A pen takes in two streams and gives us back the stream。

A pen prime takes in a front end stream and gives you a front when I say front to front。

 I mean also with the stream in toe okay but yes okay。Yeah， product in Street。

I was a little brief on that， but yeah， if you look at the constructs。

 this is the only interpretation that makes sense。And then this one gives us back a stream also。

 and then this one gives us back in front。Okay， do I give a specification？😊，Oh， I did。 Sorry。

 I should have I should have well， a pen prime wasn't there。 I should have written a pen prime too。

 but yes， thank you okay。😊，All right， one more for the road filter。

 I'm not going to write this one out。 I'm just going to tell you what it does。 Okay。

 I want to filter a stream。 Co， All right， I'm not goingtivate this here。 We just want to do it。

 All right， This is how we do it。😊，I want filter， takes in a stream， returns a stream。😡。

I want filter prime， takes in a front， returns up front， same deal here， okay。

 I should do expose here， right？😡，AhWhat's going to happen is I delay my call to filter prime。

And in doing so， I have to expose S because filter prime takes in the front， right？

And then filter prime， if it's empty， I can't filter the empty front so I return empty。

 but if I have cons I check if p of x is true if p of x is true I keep the x right so I do cards of X where I filter the rest of the stream you could call this S prime if you wish that might have health yeah。

😡，Otherwise， this is actually going to have to be an exposed I'm going I'm going to filter the rest of the stream and then get the first element of that。

 I have to make the types match okay this is actually a useful thing。

 which is that like I'm lying to you here like this is not correct but like this is a very clear kind of lying where if you plug this code in it's not going work so like the best kind of lying is lying where you can check it mechanically so I'm lying to you here but what should be here is exposed the types will not work unless I expose S or filtering out of S。

😡，I know that is brief， but this should feel the same sort of way okay where if I don't have anything。

 I have to come up with it eventually so I expose and also I maintain this duality of operations on streams and operations on fronts is everyone clear on that？

😡，Because I won't go with this because I will talk through the sea if I swear to God， I will。

It's fine to ask questions also its important。Okay， cool。

Okay so one thing to note is is map is interesting because map might give you a nonproductive stream if you give it a nontotal f right if F loops forever or if F raises an exception。

 you might get a stream that when you force the next element。

 it raises an exception or loops forever， that's what nonproductive means， right？😡。

But filter might give you a nonproduct stream， even if you give it a total P。

 S I gave a predicate function filter to filter that was always false。😡。

If you expose the stream that you're working on， it will loop forever。

 assuming the input stream is infinite。Does that make sense for everyone because you're always going to look for something that satisfies？

False， which will never be the case， yeah。Yes， exactly yeah。

 but it'll only happen when we get to that element yes indeed yes so this is also something I wanted to kind of just briefly mention can I think it to yourself why you can get a nonproductive stream from filtering with any predicate function even a total one okay this is kind of like good conceptual knowledge to have。

Okay， all right， for three minutes， I want to talk to your about prime So I think this is super cool。

 Okay some people will tell you the primes are infinite and those people would be correct。

 but some people will tell you that。 and in fact， that makes it a really cool application。

 a prime candidate， if you will， for talking about streams because streams are also infinite。

 So let's try to make a stream that has all of the primes。

 Okay we're gonna to use something called the Cve of eraosthes。

 which tries to find prime numbers by excluding numbers， which are not prime。

 Okay the idea behind the sleeveieve is simply this。 Okay as soon as I see it so okay。😊。

I like am looking at all the natural numbers。😡，So I'm looking at these。

I'm looking at all the natural numbers that I know to not be zero1 because I know that they're not prime。

 okay， but all of these guys， and the first one I look at， okay？Well， too， it must be prime， right？

So I exit out and then I exclude any element， which is a multiple of two。 So gone is4， gone is6。

 gone is8， gone is 10， and then I look at the next thing that satisfies， so I look at three。😡。

Well three now must be a prime because it's not a multiple of any previous prime。😡，Sorry。

 I look at two and then I cross it it's multiples Yes thank you I look at three and then I cross out it's multiples so I double cross that six and then I cross out9 and I you know somehow we're done here I cross out 12 and then I'mdone so this is a prime I look at the next guy that's five which is a prime I cross that 15 and 20 right you get the idea so on and so forth。

This is hard to do in a list because。I can't have a list of all the natural numbers。

 but I could have a stream of two through infinity。

I'm just going to talk you through this implementation right now， but here here it is， okay。



![](img/4d720fc990d9282f09aeb2a8fc786573_5.png)

Divided by x Y returns true if y is divisible by x。

 okay so y mod x must be0 for that to be true right y is divisible by x and then my Cieve is going to take in a stream of natural numbers S。

 I assume that that's the case。😡，And then I just delay seeve prime on expose S。

 this is just type level so okay， that's not interesting。This case is going to be if I have empty。

 which will never happen if I have the infinite stream of natural numbers。

 and this is where the magic happens。😡，If I get an element like two or like three， I keep it。

 I know it's prime， but but。What I do is I filter out the rest of the natural numbers to not keep anything which is divisible by X。

That's why I inverted the order here a bit like divided by as such that Y is divisible by x so that it would read nicely when I partially applied it。

 but the point is that I filter the rest of the sequence， the rest of the sorry。

 the rest of the stream to not keep this， not keep this， not keep anything divisible by2。😡。

And there is a issue that's not divisible by right， and then I see that again。😡。

I continue to see on whatever the rest of this is to recursively ensure that our algorithm keeps going。

And then I， you know， I get， I used tabulate to get all of the naturals from two onwards。

 and then I se that to get the primes。I think this is like freaking coolest heck like this is like 10 lines and I've given you all the primes okay。

 if your CEO walked into your office and was like I want all the primees on my desk。

 this is how you do it。😡，I'll leave this as a bonus to you to figure out why this works。

 I just wanted to briefly talk about it yeah。Numbers are not interesting。

 but streams are interesting All right， cool， okay， streams are fun numbersumbers are not Thank you。

😊。
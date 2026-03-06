# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p05 P5 -BV1qBqPBYEy1_p5-

。Okay， so this is the review for Simon two， which is the AST interpreter。

Everyone's code seems pretty much great were two main。Gouchchas that no needs to look out for。

 so in an interpreter or in any language limitations。The primitive。

B codes are never what you usually get wrong， so what you always get wrong is the correct handling of scopes。

So like if statements have their own scope， and while statements have their own scope。

And this is just really subtle okay， because often you don't exercise this code path and it seems to work more in many cases。

 so that's one。And the other part that is always a major source of complexity is the object system。

So Fi has this prototype system where you have to link， go up these parent links。

And then when you set a variable， you have to set it at the appropriate stage in the link。

 so that's also a little bit subtle so some of you got shut up by those two things。

 so those are the main things。As for measurement goes。

 the main statistic that you guys should have been aware of is this ratio between the time spent looking up in the environment。

Versus the total execution time。So when you looked at the Sudoku。Bchmark， for example。

You would notice that nearly half of the execution time is searching through this environment。

The other major statistic is。What percentage of method calls is on the integers？Aorly large amount。

Simple interteger primitive operations， and yet you're still doing this very expensive general lookup each time。

So mostly that's what we'll be concentrating on for optimizations。

 how do you eliminate the time spent located environments？

And how do you get primitive operations as fast as they should？Or at least faster。は。

So this is just going through， we only had two questions this time。So the first one is。

 how do you extend your ASD interpreter to support return？And everyone mentioned one of。

Two general words。So the first way is you take advantage of your language constructs。And in C。

 that would be long jump and said junk， okay。So。Every time you enter a function or you enter a method。

 you set。John Bcker or John point。And then when you execute the return， you long jump to。

Jump out to the nearest jumper。The only tricky part is you have to make sure。

To you handle recursion properly， you have to make sure you save the jump buffer。

On each native function im。And also just because of the way Se John thead is implemented。

 you need to pass out your return value somewhere， so most people have just said just use a global variable and that's totally fine。

In Java or ML， you do something like throw an exception in scheme， you request a continuation。

 so each language has their own way to do。So， this is。Method number one， this is method number two。

So we can augment the return value for eval。 So right now。

 Eval directly returns the result of the operation。 Now we can box it up into。This thing。

It's either the result and you wrap up the value in this result strapped。Or it's a return str。

 and you're roughly with the value of the return str。

And then every time you evaluate one of your sub expressionions。You get the thing back。

 they have to check is it a result or is it a return if it's a result， then you proceed as normal。

 if it's a return， you need to stop evaluating the rest of subions and then thread it back up。So。

This is probably the cleanest way of doing it， but unfortunately it also takes the most cut。

It's probably also the slowest way。L jump can set out on Facebook extremely with。

For those Hake programmers out here， you'll notice this is basically。Where you might use a phone at。

 But I won't talk about that。嗯。So basically， not all languages are created equal。The。

The implementation with the lease code was lo on the said jump。

And if your state nation doesn't have long jump jump， then you're forced to do it the other way。

So if you're playing around the languages and you're investigating in different ways of maniping control flow。

Scheme continuations is probably the most powerful construct there is。

I'm just going to throw that out there。Okay。The second big question was on other clinic。

So the first part of it， I asked you to precisely define。

 give your own definition for what the  sesymmetrics of cloning are。And。Basically， I was looking for。

 are you going to do a shallow clone or are you going to do a deep clone？And specifically。

 are you going to do a shallow clone or deep clone of the parent link？

One or two of you did a semi shallow semi deep。G。I told you you've probably said it that way。Okay。

 so a shallow clone is something where you don't re curse down the clone。

 you just copy the pointers in your subfields。So。If you clone an object and you modify。

A child object through your reference to that object。对那。

All your clone numbers will also see the results。Is your pen cloned or not cloned？

There's good reasons to do either。呃。Various languages in history have done both。So按那跟难。因为我就觉得。

If you do deep clo， there's an additional。Caatat， which is Fi is not a pure language。

 there's assignment， and because of assignment， you can get these cycles in your optgraph。

So if you want to do deep cloning， you have to tell me how you're planning on handling these cycles in your object graph。

So semanically， you can define it either way。I think very。

 very few languages have ever provided a deep film facility。Not because of any intrinsic difficulty。

 I think it's just， it doesn't。It's not that useful a lot of the time。Okay。

 so it cannot be written as a purephi function。Or if there is， I have no idea how to do。

And your implement is very easy， just make a coffee and you coffee on the points over。Now。

 the next question。Gives me a chance to monolo for a little bit。The question is。

What are the negative consequences of implementing clinic？

And my sweeping statement about this is that。The most powerful language feature。

Is not anything syntactic。It's not like， oh， our language can do it in one line。

 what he can do in three lines。Like that， the most powerful language features are thevaris guaranteed by your language。

So。As you'll see， after cloning， destroy some variant。So here's a use case。

We want to supply this contract to the program。We want to create a function a function to create pairs。

And it supports get x， get Y functions and set X and set Y functions。

So really anything that implements。This contract should work properly。So， let's say。

You hand this officeordinateinate and he hands the back some code。And this is what he writes。

So to track the state of the pair， the allocates an array with two elements。

He's going to store x in the first element of one in the second element。

So and why in the second moment。So getX just returns the first element in A and getY returns the second element in A。

And set X and set Y。Assigned to those slots。Okay。So your sport hands you this and you decide that。

This is not very good code。Why don't we make it bit clear， we only have two elements anyway。So。

 let's just。Be quite on like that。So now you expand the array out into its own individual fields and then you retrieve from the field and set to。

So what's the problem with clo？Well。For those of you that define it as shallow cloning。

Deepco doesn't have this problem， but for those of you that defined the shallow cloning。

 youll notice that。Under a shallow clone， this array is not cloned。Right。So。

This pair is created using the first method。If you clone it。

Then updates to one pair will effect of the other pair。Whereas in this version， if you clone it。

 you'll actually get two different pair。So if you implement shallowlo cloing。

 it breaks its invariant， it means that。You cannot。

Take that code and transform it into this code and expect it to work。みちゃなのオッケーです。So。

The program is not merit to this transformation under the presence of planning。So to me。

 this is a big note， I think this is a really。Bad property of the language。Okay。

 so that's negative consequence。So。Like I said， imvariance are features。

 Phine is not a great language， but it's not a horrible one， it has some other imvaris as well。So。

Fniing programs are memory safe， you'll never get a segmentation fault ever。

So this is something you're used to from。GC languages。You can out write any malicious program in FNi。

 right？I can take famous passwords。I can take any of your training programs directly run this on my laptop and assuming I implement the interpreter correctly。

 there's nothing you can do to my laptop。😀。Theres a not a challenge don。I that throw out the memory？

Okay， and then just one last fun one。So F has a wildlife loop right so if you're right well I less intend then do something。

And outside the wild， after the wild。This is an environment。 You know， this is true。

 I is definitely greater equal to 10。And this is true in PhA。

 but it's not true in some other language。So that drug made a big deal out of dismart in particular。

 but I think nowadays we see that it's not such a big deal。Okay。

 so that's enough review Oh yeah are there any negative consequences of deep？

Are there negative consequences of deeping， I thought long and hard about it。

I couldn't really come up with any， actually。Yeah。Small talk had。

A shallow and deep clone does both neither are， well I think shallow might be implemented as a preitive。

 but deep is just implemented in small talk using reflection of staff。

 but it actually loops if you have a cycle。It doesn't know how to deal with cycles and you find actually if you start deco copying things。

 they're often linked to you know the rest of the system so bad things happen because it's hard to know when to stop when deco copying iss usually some programme or intent that knows where the Bary should be。

 but the system can't often cut for。I think that's the primary reason why deep cloning doesn't turn out to be all that useful because you have this like little pointer link that you forgot to in the lab or something and it just ends up making a clone for your entire system。

Can talk about some the native consequencess of doing like a halffty clone and capshot like cloning only the things in your direct parent and thank。

还子。Oh， so there are some hybrid games。嗯。Some hybrid schemes I've seen is like four arrays。

 you do a deep clone before objects， you do a shallow clone and stuff like that。

 there's the only downside。Is that you have to explain this value your user it。Let's see。

 How does the power go。Anyway some designer made a post that。

The most awful thing you can do in language design。

It's to design a feature that technically is right。

 but no one gets because then it's not actually a bug。

 but you just have to answer everyone's question open number again。呵。All right。

 so the next assignment is to actually write the BIcode compiler yourself。Okay。

 and then after you do that， then you have like a self contained ph system。

The compiler is actually not that difficult， it should take you very little time。

 but I want you to take this time to refactor your microcode interpreter。Because as I said。

 this is the base I will rebuild building everything on top。So in particular。

 after the compiler will be garbage collection and garbage collection。

ItCan be either difficult or hard depending on how you lay out your values。On the heat。

So this is a recommendation， a very strong recommendation。啊，系。When you allocate these values？Okay。

This is the format I would strongly recommend you to hear too。Every object has。

A little word or a cell at the front of the object。This simply at the front of the object。

As some editor that tells you what type of object。So there be a special tap that ends the special tap for null for arrays。

And then for classes， there will be different。Time， depending on what class you younger。For array。

 you have a length followed by a variable number of slots。And four objects。You have a parent。

And then you have a variable number of slots， as just for the variable slots。

The methods slots don't need to go on here。And。The biggest advantage of this layout is that there are no pointers in this representation。

Yeah，啊 sorry。for the class one， don't be one to type a type。Foration as well in some。 Yeah， okay。

 so ants might be like zero。1，2。Jennifer Gla， you had like threes。Okay。

 so the biggest advantage of this lab is that。You don't need to follow the linked lists。

And that will make your garbage collector much easier。And also。呃。So something about pointers。Right。

I think that's true still yeah。Yeah， so no link list， every object is like flat， a flat thing。

It's a contiguous thing。And also， because all of your ta words are in the front of the object。

It makes her heap parable from one direction， which Mario said。Okay。So please make this refactoring。

 otherwise your garbage collector will be。Very difficult，I don't have the slide for it。

But I also mentioned in the taSA post that some of the bikecode operations I consider simple。

Simple being defined as it's basically straight line code。

 it doesn't require any call outs to functions。So I would recommend doing the quickipening phase and making sure as many of your operations are simple。

And the primary reason for this。When you go in and you start generating。

Assembly sequences for your byco operations。You don't want to put a function column there because then you have to do with。

Colllic conventions and all that。So quick show of hands。

 whose Bcode interpreter got faster than their AST interpreter assuming measurement。

Anyone can get a slower bike。Now factor two。我冇啊冇嘢我。What full illustration。反事。

So the idea of the exercises is things are going to get faster and smaller and sort of more efficient。

Leading up to something that's actually hopefully quite running quite well。

 in fact we're just discussing at the end， I think we're going to have。

 you know you can submit your running version， your final version for sort of a tod competition。

 and I'll give away a copy of this book into the fastest one。本当で、すね。Okay， so's。で。Stw to。気？Okay。

 so I'll wrap a little bit on。Some dynamics language techniques which I think are going to come up in the exercise after the next one and also we'll summarize a little bit of the stuff that you'll have been exposed to by virtue of reading the Drt Schiffman paper so hopefully one of the two things maybe we' get a little clearer。

But then after that， the main purpose of today's session is interaction to memory management and Dev' spend quite a lot of time looking at several different garbage collections。

And。A wakeake you up when we get in the one that want。So。So dynamic languages。

 I hinted at this last time， the challenges are that you know a lot less in the source。

 when you see the source of a dynamically type program。

 you don't know the types of the things you're operating on and that sort of cascades into all sorts of other things so you don't know the the types ahead of time usually most dynamically language dynamic languages allow even programs to create new types at runtime。

 so it might not even be closed。Beginning of the execution。

The types in name particular fragment vary over time， did you have a question。

 well can you define dynamic？No， not really， not really。

 it's one of these things where it's kind of there's a gray line between the two。

 but broadly speaking， I would say it languages where there are no type declarations。

If they're top declarations， usually if the designer is intended to those things to capture some。

basically restrict what's going on at runtime so that you can check ahead of time。

That those restrictions are there， but that's not universally true。

 there are type systems that don't satisfy that。Prorovideder guarantees， but broadly speaking。

You don't know what's happening until you actually get to run the particular fragment of code。

So let's look at some examples。So if I write FxY and there are no type declarations， who knows。

 you know what's X， what's Y， they could be of any kind of value。

And here's a typical example familiar for anyone who uses the dynamic language。

 you can call a same function withins and floats and the program has to figure out。

You might even be able to call intermingled structured and unstructured things。

 so you know if F in JavaScript was the plus operator。

 so both of those would be legal right because plus his addition and string contaminatcarnation。

And then you could do。Reflective stuff， you can have strings past。

 you know this could be a string typed in by the user which you're going to eval is going to cause a piece of program to run and you can't in principle。

 know what that's going to do ahead of time because you can't read the user's mind。

And you could even maybe be able to redefine chunks of the program for reflection。

I'm not saying that that's a good idea， but implementations have to do there are types of systems that allow you to do this and still have the same。

Safety yes if you have each one in particular， Yeah， but no one。Two or first approximation。Really。

ちちわて。Okay， so let's look at a little bit in more detail about what the consequences are in particular what the implementation。

Trericks are to optimize these things at run time。So we don't have any type information on the variables。

 but that doesn't mean that the values don't carry their own type information right it's not like C where you know C just operates on strings of bits in memory and you can kind of operate on anything right you can write a union which has an name and a flow and a string pointer and anything and you just choose which flavor of the union you want to operate on and it looks at the bits and treats them like that now I should point out even C says。

That behavior is undefined right what happens in that case is not defined by the C language。

 but there are conventions that all the implementations follow and people depend on that stuff。

But you can you can go you can basically subvert the type system and you're sort of encouraged to subvert the type system in the name the system programming the dynamic languages you can't subvert the type system it's just that there aren't any types declared on the variables the types are sort of associated with the values so the idea is if if you have an object and you try and do some operation on that object which isn't defined by the object then you should get our own time out and so we have to be able to。

They'll figure out what we're supposed to be doing and also whether that's a language by the language at Rome。

嗯。Obviously value does vary in the space requirements and so when we allocate space for a variable。

 you know you've got two choices， you either make as big as it's ever going to have to be to accommodate all the choices that might be there or more typically use an in direction so basically what happens in most of these languages all variables become pointous to something to a value。

You can in some languages。Get away with a form I think I have。

I'll look ahead and see whether there's an example of that。I don't seem to have an example。

 but for example。In。A basic。You write a string， it has a dollar sign after it。

 the other variables don't have the dollar signs or they don't have array brackets。

 and those are all scalealar variables， at least the earlier versions of this。

So you could tell just by looking at the lexical structure of the variable name。

 whether it was a scalar or whether it was going to be a structured thing。

 and if it was a structured thing， you'd need a pointer and if it was a scalar。

 you could just hold a value and reserve a space big enough for a number and you' get away。Okay。

 so let's have a look at。嗯。An example of this and what I'm going to do is take that little expression bycode interpreter and I'm going to change the assumption。

 change it so that any variable can hold an in or a float at any time。

 So now it's not a typed system and the bikecodes are untyped in that the bikecodes just tell you what operation you're supposed to perform in the line。

Representation。Has to figure out what's going on。So the rule I'm putting in place here is if you write an expression using floats。

 then you sort of wide don't have floats wherever necessary。So in this particular case。

 because I'm not having any structured variables， I can allocate for the biggest case。

I don't need to do an interaction， I can use a C union。

To have a space that's big enough for an ink or a float， whichever of those is bigger。

And use that as my value type， and then all of the elements in the interpreter are just made of that value type so the stack and the variables just contain that contain。

Those unions we've a to tell me which particular one is in use at any particular time。

 So now we've gone from a。A simple scaler in the implementation to a slightly more complicated structure。

 but not very complicated。And what does the interpreter look like， it's a little bit more tricky。

 but not bad。Again， I've kind of unfolded everything here。

 so you see through to the bottom typically this will be more wrapped in macros to make it a little bit more abstract。

 but if you read through this you can see exactly what's going on so in this case。

I have a literal which pushes an int onto the stack。I'm going to increment the stack point。

 so in this case I'm doing checks or max deck for the stamp。哦哦。

Checking whether an error occurs if I observe the stack。

 otherwise I push a value onto the top of the stack。

 which is tagged as an in and then has the integer extracted from the four bytes that follow。

The bycode。说的。And then for add。Now I have a little bit more complexity because I have to figure out exactly what I'm at。

while matting is determined by the types of the two things on the top of the stack。

So if the two things on the top of stack are integers， I'm going to do an in tag。 now C makes this。

Less obvious than it might be by the fact that C does automatic coercions when you mix in some floats。

 so for a little bit more clarity here I've got explicit casts in。

Where I'm where I'm actually going for vintagetes to float so in the case where we've got two ins I just do an in tab。

 but I've got a float in an in and I have to cast the into the flow and then add that to the flow。

When they're both floats， I'm doing the flow ad and when I'm doing the other direction around。

 I'm doing another cast。But it all fairly straightforward， nothing too tricky there。

And then for the G operation， which is just reading the variable。嗯。

Then we can do use the C structure copy to copy both the tag and the。And the value at the same time。

Hopefully that's pretty straightforward and clear。And questions。O。

If we were going to do the abstract interpretation of this bycode。啊。

We could do that in this particular case by modeling a stack with types only we don't need the values now so this might be something you would do if you were going to do a prepass over the bikecodes to figure out the type of an expression or to figure out in advance whether a particular operator was going to do an integer or a floating point atom so this is the replacement for the earlier abstract into a particular cell。

 so here we're just pushing tags onto the stack which represent the type of the thing that we're computing with。

Now。Suppose I had division here。And suppose I changed it。So that the division operator。

If the two things were if it was equally divisible。

 it put an int on the stack and if it was a fraction， it put a float on the stack。

 how would that affect what was going on？Could I do that in this scheme？

We't be able to do an abstract。Exactly。Exactly， because now the specific values at runtime define the types on stack。

 the not。Uniform， overall income values。 And so you can't model abstractly what's going on and get get an answer。

 You'd have to extend the type system to carry that uncertainty along with it。

And you might end up with something that was so conservative that it would useless because it would soldble was just degenerate a flow。

 but in the case where you didn't have a division， it would still be fine。

The other thing you can do with an interpretation like this is just use it to model a stack depth。

And so if you， even in the case where you're doing the conversion trick。

 if you can model the stack depth accurately， that gives you the chance of removing these stack tests。

If you know it's not going to overflow， if you can always allocate and of stack。For the worst case。

 then you can remove the statutet checks， even if you don't know the type information。In the JVM。

 as you've seen， this is basically done twice， once by。Java C。

 when it generates the type information that it's putting out。

 it has to compute this model so that it can know that it's generating the right bikecodes and then again a verification time when the bikecodes are。

Okay， so that trick works fine on small data where you can allocate for the worst gains。

 but it doesn't work for large data。So if you imagine a language in which a variable can reference a booleing or a million element array。

 we clearly can't allocate for the worst case there。嗯。

Even if we wanted to allocate for the million elements right。

 it might be a billion or a trillion or some of it and by sell。

 but in that case we need to use an interaction to reference the value and at the end of the interaction allocate cell is big enough to hold。

The data that out we're executing in effecting the heap。And of course。

 the other thing that gives us is sharing because now we can pass pointers to things around。

Instead of passing the values。So that might be important in the language semantics too。

 so in effect fact every variable now contains an address。

Or equivalently an index into some kind of table which contains an address。你 look at sir。

We look at that， as I said， basic only needs the indirects on as and strings I think there are other languages that have that sort of syntactic flavor on some of the variable types。

The open paper is often talking about using an object table。

 what is the main difference between that？ok。So imagine we have a narrow language in which we can have。

Simple types and some structured types， so in this case I have。An integer， a floating point number。

 and an object containing an intesger and a floating point number， how would that look in the heatap？

Or if we had a direct he organization， each of the variables would contain that address of a cell。

Wwhichch contains the value that we're interested in。

 but it has to also carry the type information around with it so that we can tell dynamically what the associated value is so typically when you allocate。

 you allocate these contiguous objects that Patrickrick was mentioning you put some stuff in a header there's usually some amount of woodcaving information that goes in there we'll see some of the information that might be required for a garbage collector later on today。

If the language was class based， you probably have a reference to the class or some other type information in a normal location here。

 so the point here is that the first two words in themselves always looks the same。

 it' always the head are followed by the class so that whenever you get appointed of something you can figure out。

What the class is without knowing the class， end up with this horrible circular thing that you have to find the time for something。

And you need to do that you have to know it's type。

 so you have to have something nailed down in a fixed location and then then after that you can have。

Variable amount of information and in this case I have an extra cell for integers which contains the integer value。

 one floats， which contains the floating point value。And for the points， you know。

 I saw the X and Y in order。 and then off to the side you'll have。

Your metadata that describes what's going on in each of these cells。So these。

 I've drawn this as three separate columns and they could indeed be three separate areas in your implementation。

 for example， at least the named variables could all be on the stack。

This could all be on the heat and this could all be metadata， for example。

 if the language if you're compiling a language that has all of the classes embedded in the source。

 you could generate all of this compile time and it like the constant put right it's metadata it's off to the side。

 but it need not be like that it can be。Two different areas， for example。

 these things might be runtime objects as well， for example， if you get to load stuff dynamically。

 this all might be the heap。And if you go as far as something like Smo talk where stack frame are objects。

 then these are also in the heat。So it all depends on your semantics and what you're trying to model as to how you partition things。

 you actually find that making it。Uniform and using a single thing for everything is simpler because you end up by writing only one allocator。

 one garbage collector， you don't have to do separate management。

But the characteristics of these things tend to have。Sort of very different longevity right。

 these things tend to last for most of the life of the program， whereas these things come and go。

Fairly frequently and stack frames come and go really frequently so putting them all in the same structure will be easier but probably slower in the long term and so as you look at more tuned implementation。

 they tend to try and separate these things out and deal with them using special purpose techniques。

 tunes to the individual behaviors。Now， you're going to do this with an object table。

What you do is you'd add。The somewhere in here。A table which basically contains a pointer to every object。

In the system。 And you instead of the picture that you see there， weve now。Substit each pointer。

With a pointer into the table。And then the table pointing to the actual object。

 so we're adding an extra level of interaction here。Every point I go through the table。

To its ultimate destination。And if your classes are also objects。

 then those would also go through the same。What that gives us。

Is now every allocate Excel is only pointed to from one place in this object table。

 so if we want to change this， we want to move it somewhere else。We we want to resize it。

 which often means meat is moving it somewhere else。

 then we only have to find the place that pointed to from this table to do that instead of finding all the pointers to it。

As we would have had to do before。This。These things need not be actual pointers。

 they can be indices right because this is probably a contiguous table allocated as an array in elements nor to whatever。

And so these can just be indices to the table and the other benefit of doing that is for the table is a lot smaller than the address space。

 then the width of the indices can be a lot smaller than a full pointer。

So if you want a nice compact implementation with restricted numbers of objects。

You can make this table， you know， 16 beds or 32 beds or whatever。

And define the point as the indices as much narrower。Which makes them much betterness of the space。

Is this commonly done？还。We'll get to that， not anymore usually。Because seems truly yeah， yeah。

So a couple of penalties for doing this， one is it slow right now when this stuff was common。

In the 60s and the '70s。It wasn't slow because the cycle time of the machine was usually at same the cycle time of the memory all very close to it and so going the extra interaction was like what extra cycle or two it wasn't a big deal now of course that's not true now so there's a big performance penalty of putting that table in memory。

It also costs you some extra memory because you've got an extra slot now off to the side for every object。

Anybody give her an idea for how much？What' do you guess for how much extra up an object costs？你没。

You can hands it for those who think it' 2 x。1。5。1。3。五 point one。1。01。So a good rule of thumbhe off。

One of the things I've observed in looking at a lot of different object systems over time is that when the object size is defined when objects are defined by programmers。

 programmers cognitively can't think of more than a certain number of objects。

 fields in an object before they say， it's too big now and split they split it into a smaller thing。

And so you tend to get the average object size somewhere around seven to10 fields。Very common。

 very common and with this very bimodal distribution of arrays it's a way off to the side。

 arrays tend to be big。What named things tend to be small and so with a10 field system。

If the average is 10， then it's an extra 10%。Typically is best footprint by having a back level of interaction。

 it's not a message。Cost。The cost is really more the time cost。Of doing the。

That's there's got to be a short couple of mine。し。そで。Okay， but it does also allow， as I mentioned。

 the incremental relocation of objects because now you can move one and you onlyt have to change its address in one place。

 which as you will see。Can make for a much easier life in some cases now。

 this was the sort of the way most things were done through to around the mid8 and then Dave Bungger's PhC thinks as heA。

In 1986 kind of established that not really such a good idea anymore。

 you know he did a lot of measurement and analysis and came up with that alternate GC system。

Which did compaction and garbage collection without needing the extra directions and stuff。

And and sort of it's been pretty much abandoned since then as a high performance of ways ago。

 It's still used a lot in systems in which。嗯。Foooteprint。You know。

 if you can compress the pointers down， you can get your 10% back easily if you can make every 64 bit pointer into a 24 bit pointer around because there are a lot more pointers on the right than there are slots on the left。

So in small systems， sometimes it uses a trick just for encoding addresses into a compact space。

But it's not very common these days。Maybe in the space。对。

It other it enables these other operations to be done in constant time。

 so in places where you need constant time guarantees on some of the other memory management operations。

 it's also a benefit。You'll see as we go along that all of these decisions sort of tie together in holistic ways and so you can't just sort of pick the best in class of any individual technique。

 put them all together and end up with what you want， usually you end up with。

A particular desired direction in terms of what your footprint wants to be or pause times that you want to admit。

 and that then guides you two other choices which are interrelatedted。嗯，不差说。To relations。

When you catch the translation？I'm sorry， couldn't you catch the translation don't code。But。

We're going to watch her again。Well， there are a lot of these and they're changing a lot。And so。

The hit rate on a translation here is probably not going to be that high， I mean。

 or rather the miss rate is going to be high enough。That it's going to be hard to our mat。

So if there were hardware support for this sure you could do that effectively， but in software。

 what would you be doing， you'd be having some kind of table off to the side indexed by this that would give you you know that would save you a load right I mean how do you do that without a load in the table a translation look or？

Yeah， so they。The obvious way is to make this look like a TLB。

 but the problem there is that for any reasonable system。

 there's going to be tens or hundreds of thousands of these or many millions。

No one's going to go build you an MME that big。You know， that's。

 that's a big piece of associated memory， As me， sort of practical in。

Numbers of up to1 of1000 not hundreds of thousands。 I don't think it's a good idea。

 but he be lives and dies the on the idea that not much is actually Yeah， well， so the problem is。

 and I could speak to this with some authority because I've done some measurements in written papers on this area is that the。

The usage of this is。Much bigger than the usage of a TLB and there's a simple reason for this。

 right each one of these is associated with 10 words on average。

 whereas each entry in a page table is associated with 10 kilograms。

So there's a factor of100 or more in terms of the coverage of memory from each one of those entries and so for the same working set。

 you're going to need 10 to 10 more of them。So for the object table。

 every time you create a new object。To create a new ID forSo when you run garbage collection。

 you also need to garbage collect the object table Well what happens is that the unused entries here are threaded using a linked list so you have a free list going through that which is easy because they're all the same size。

When you want to allocate one， you pull one off the free list and use the next one。

 when you reclaim an object， you have to put the associated ID back on the free list。

What ultimately tends to happen is that the order of things in here gets all jumbled up so the locality in the actual object table itself sort of goes to hell over the time。

And this is all for a reference kind of system I both ways， both ways。

 So the dot Shi system used an object handle。That small f is use an object table。

 and I think still does。I couldn't find certainly Peter didn't know of any rewrite that had been done that removed the object table I'd have to talk to one of the more modern antennas to see whether they've。

Chaanged its sense， but throughout its life， it was an object table based。Implementation。

There's got a better way of doing that。Q。Auction right。Control right。应该。嗯。Either way。

Whether it's with an object able or no， basic arithmetic operations in this arrangement are painful because imagine what we're going to do now。

Do a simple addition。And an assignment， right， so now instead of I containing a number because it's a pointer to a cell that contains a number。

And our 123 is presumably awesome but also in a cell， so assuming that this is， you know。

 it is really I plus J rather an I plus a constant。How do we implement this Okay。

 so we firstly have to extract the values out of the sales， then do the arithmetic。

Then we have to make a new cell because Conter use the old one。RightWe can't store at that。

The126 in here because now everybody who shares this value， right because when we pass parameters。

 we pass pointers， we all make copies。 everybody who shares this would have to。

Would see the value of 123 become the value 3 become 126。

 which is generally speaking not considered good language semantics。

 so we have to make a new cell and store the new value in that and that's the expense here now we're generating the cells like they were going out of fashion。

嗯。The other thing is， of course， this is now going to put a huge load on the garbage collector。so嗯。

Give me a guess as to how much slower your language goes if you make this transition from。

Primitive numbers with primitive operations to boxed numbers。Anyone got a sense。For， you know。

 take any sort of normal program and do that rerite。

 how much slower do you think it will go like factor two， three to four O more like？

It' more like five to 10。It's a pretty big hit。It's a pretty big thing because you know arithmetic is really common。

And then he's just doing a ton of work for every hour。C。

Okay so there's the result now we store a point when we have to garbage collect。

If those things are not reference anymore。So， this are。

There's that really needs tagged and rot take Yeah that's what。

So we've got these primitives in the heat and they're cost lay out。

 well this high high allocation and delocation costs and the memory hole beds and the load and store penalty of every indirect that we're have。

So the alternative， one alternative allow anyway is to restrict the value range of our primitives and squish them into a slightly smaller space and use a freed up bit or bits。

To represent this tag information。So。Heres an example， typically on the。A word aligned machine。嗯。

For example， 32 bit machine objects will start on four bike boundaries。

 which means every address has two zeros at the bottom。嗯。

If we put type information into the two lo order bits， for example。

 we use two zeros for addresses and a different combination。For some other things。

 then we could use the remaining 30 bits to contain primitive data so in a 32 bit word the two low orbitbits would tell us what the other 30 bits mean if the two low orderbits are0 then the rest of it is an address and point to an object in the heap。

 the two low order bits are0 one， we have a character if the two low orbits are one0 I mean you can make these choices arbitrarily right this is just one example。

But the two that you always want are address and integer， those are by far the most common to。

 so sometimes people use only one bit。But for 32 bit machines， which are very widespread， got2 bit。

Advantage is often pressed into surveys。I should just mention now。For your assignment。

 I'm going to stress that your integers be tab 00。Reをする。

I'll show a couple of alternatives because there are pros and cons to different tangging this game。

So in this scheme now we have to do the tag test before we do anything else。

 you have to look at those two low order bits if the tags are zero。

 we can do an object tax if the tags are non-ze for rent then we have to strip them before we do it as yourrithmetic enough for floats what do we do with floats I mean you've got a sign。

Amanesa and exppoum， which part are you going to squeeze out？Who thinks we lose the sign bet？

The mantesa。Yeah， exponent。Bad idea to shrink the mantis a bad idea。Decrease the range。

 don't decrease the precision， there's already not enough precision anywhere in 32， 32 bit float。

 so you really probably want to chop out a couple of bits of Mantesa and you just end up having a smaller range of float in plates。

就是当。I'm sorry， sorry， the eggs， yes。The of course now imagine what you have to do to do a floating point ad right because now the floating point ads are not in the hardware format。

 so there's some bit twiddling to be done on every daytime before you present it to a floating point instruction which is much more expensive probably than the floating point instruction is itself these days。

Now this again was a great idea in the days when all floatinging point was done in software。

So there's some alternatives which sort of shuffle the pain around into different places。

 one alternative is to use zero， zero for integers and one1 for addresses。

And that means that interarrithmetic doesn't need to strip or a replace tank。

 you can just do the addition in effect on multiple to four， and most things are pretty cheap。

 you still have to do the test of course。And removing the tank before the load of the store is small compared to the cost of the load of the store。

 at least that's the reasoning。And it might even not be necessary if you using index loads to do field exercisees。

 so when you see when we get to compiling the way you compile field loads is a load with an offset and now all you're doing is subtracting three from the offset。

I份。The other thing nice thing this gets you is if the addresses are unaligned and you forget to do this in your implementation。

 you'll get an unaligned harder exception， almost certain systems that say， oh。

 you try to load a word from this address that's not word aligned。So that's an alternative。

 I have some example code。Of the呃。The expression evaluator。

 you'll be doing something like this in a future exercise to your pen implementation。

 so you start off by type defing some flavor of in。That's big enough。

Because C doesn't tell you what the size of inar so you figure out for your implementation。

 what size of the right size and type get that to be a word。

 and then in this case I've encoded the tags so that zero is an int， one is a flow。

And one one is an object， and I have a bunch of macros now to do manipulation of the associated work because you don't want function calls on all of this stuff that whole。

That tell your performance too， because you're doing a lot of tagrithmetic now。

So I have a way of stripping the tag off， I have a simple way of testing。

 whether the taggged an in or af floatat。or an object and pulling out the underlying value。

 the flow bonds I kind of just delighted on a horrible bit twiddling that would be functions off to the side that you'd have to do stuff with the union end bit。

I look in themateole manual and stuff like that to figure out exactly where the bes are。

 which I couldn't bother doing that。And then for objects， you。

 we have a way of stripping off the tag。And a way of basically converting into an object to its underlying address。

And then our stacks variables are just these tagged words。What does it look like in the interpreter？

It it was a title。You have't used Tago and they out there yet。好。Oh on the next I right here over。

Okay， so I've just illustrated that here。So。In this case I'm using the macros to make them do a little bit more readable so isn't is the thing that tests for an ink tank if the two things are ink tank。

 then we have to pull out the hint values and then do the conversion。

And then pulling them back again， and the macrobes here are just kind of highlight the fact that in this particular case。

 think we don't do anything。And then similar things for the flow， and again， by by maxizing things。

 you can make this code fairly readable。嗯。There's anything particularly。

Unusual I know where they are。Now， you just got to get all the cases wrong。Family strength。

So this was a。Common technique in language implementation。

Used a lot in LspP systems and small talk and others， and in the 70s and the 80s。

 special purpose list machines were quite popular， there were quite a few companies building them。

And quite a few systems use hardware support for tacking。So this format。

 the representation of you know， some number of bits in a word was actually understood by some of the instructions in the machine。

And you could leverage that to give you higher performance， so for example， if you did a Tgged ad。

The tagged ad operation could strip the tags and check them in parallel with doing the reference so that the actual cycle time of the ad was no worse and if the tags were incompatible or they gave you some combination that you couldn't the instruction couldn't handle it would either set a flag or raises them in。

So that was fairly common and in fact， spark when it got introduced was right around the time where this was still fairly widely used and it has support for some instructions that do this so does's the taggged a and subtract two flavors of each。

One that just sets and modifies the integer condition codes and the other one does a trap when there。

A combination outright basically between the tanks。

It does a trap on overflow which is kind of confusing because it's not an overflow's a tag error。

 there's no separate trap for tag errors， so the overflow handler has to figure out exactly what's going on。

So these were put in Sp。Unfortunately， the trap overhead。

They're so high that I don't think these ever really got used because it turns out it's just cheaper in smallhawkck。

 for example， the frequency of a plus operation being something other than ins like floats is common enough that it's just cheaper to check。

Before you do this instruction， then pay the price to the trap。On one in 100。

That actually evokeked the traps， so the traps ones were sort of a disaster。

And these ones got used a little bit。But as Peter mentioned last week。

 there are compiler techniques that we'll get to。Lessen the impact of the tagging the good thing about tagging is that there's some memory operations involved it's just sort of register to register stuff you're just fiddling around with the bes and and that's still cheap the memory the loads in the stores have got worse most over time。

 but the bitwidling and registers is still cheap。So time manipulation is not too bad。

Is it since it's late into the hardware does it mandate a specific tagging scheme？Yes。

So does this mean that if， I mean， the decision whether or not to use Tularrithmetic is on the language and not on the implementation because the use of Tularrithmetic will necessarily change the range of。

 for example， these so it depends on what your language is willing to admit， whether it says。

 it says you know integers are some size that is implementation defined， of course， you just say。

 okay， now're 30 bits and too bad。But in things like。

Small talk integers don't overflow when you add two numbers together and they don't fit in 30 bits。

 then it goes to a heat cell representation。So from that point of view。

 there's a discontinuity in performance， but not in behavior。

Other languages have different different decisions on this JavaScript tends to do tagging for all its variables。

 I don't know how it does that whether it restricts floating point ranges to some smaller value as in general。

 certainly the default type of value in。Six are got 62 bits of but it does it reduce them， mantesa？

Okay， problem maybe I'm a 64 bit number maybe you can you reduce the。Sorry。

 reduce amount rather than the exponent because you don' you don't care on a double， but yeah this。

That's definitely a price there。Okay so。At some point you'll be doing this。

 adding tags tagged arithmetic to your feeding interpreter and measuring what difference it makes on your performance。

Okay， so。Other thing I want to talk about is the absence of static type information on code。

 which we talked about data， Yeah， sorry， we is it taggged resume in F。

 like there's no ad instruction， it's all like function calls。是没有的嗯。cause yes。

 but you can still in the method you can。Do the right thing。

It's a representational change and what it should give you is the ability to do arithmetic without having to allocate for the cells for the values。

O。三没 sense。I'll think about it okay， well， we can talk at a break if you're。I the questionsOkay。

So for code， you know， the biggest downside of this is now you see an invocation and you don't know what you're invoking statically because you don't know what X is。

there's no type of system given with that so it could be invoking the F method in any class that he finds or it could be trying to invoke it in a class that doesn't define it which is an error。

 you know this new class of error now which is， you know I'm calling something which isn't there in the particular object I'm calling it on so the system implementation has to deal with that。

And in the worst case， you're doing， you know， a full look up and dispatch for every。Invocation。

 which is really painful。嗯。Now， many of the dynamic languages to give you sort of a more powerful abstraction。

 they tend to pull。All of the primitive operations under sort of a method lookup semantics。

 so pluses and minuses and sometimes control structures。

 they're all in theory done through the same invocation mechanism and so if you had a full lookup and dispatch for every single one of these。

 the performance would be truly awful。And so making these things go at least a little bit faster is really critical for the performance in most dynamic languages。

 so you want things like addition and subtraction and variable assignment and if tests and stuff like that to have sudden reasonable performance。

 not a full look up on every upper。So some examples in JavaScript， right A plus B。

 it could be a flow ad， most implementations optimize the case where the parameters are integers and have a separate taggged representation of integers and would do an int as an operation。

 it could also be shrink of that nation。If I write A+ B in small tool。

 it means send plus to A with B as an argument and any class can defining+ do anything at life。

But in self it goes even warm further in that the control structures are dispatches。

 so in the way to read this is we do a test A less than B。

 that's a send of less to a with B as a parameter， and that gives us one of two objects back the true object or the full subject。

And we send to that a closure， pair of closures， one for the true case， one with the false case。

 and the true object evaluates that by evaluating the true closure and the false one evaluates the false closure。

 so in this case， you know control is a full dispatch and a closure of evaluation implemented naively which is really。

 really painful and then when we finally done't， this assignment is also all assignments in are also fully looked at dispatches in theory。

And then in R， the square brackets are methods。And you can redefine what that is there。

 so you can't even look up an element of an array without invoking your methods。

 So you've got a deal。Withre eliminating this lookup cost。

As much as you can to get something that's even half reasonable performance。嗯。

In most of these languages， so firstly the lookup is very language specific。

 the semantics of what it means and how it operates is language specific。

 so you have to look at of specific language mandates。

 but in general in most cases the target method is determined by。

Two or small number of things in the coal， typically the class。Or the type of the receiver。

 the thing on the left， usually， and the name of the method， it's usually that combination。

Determininees the lookup and for that， if that's the case。

 we could use a simple global method lookup cache。To try and speed things up。

 and this is like the simplest speed of technique。What we're going to do here。

 I have a cartoon here that we're involvingvo X。F。X refers to one of these objects， in this case。

 it's an end containing the value 3， and the object refers to its class。

 which contains a bunch of methods。And the method name points to the code of the method which has the bycodes in。

 and normally what youd do is youd follow the pointer from the variable to the object。

 you'd get a value， okay it's three， follow that from the class。The class a method。

 you looked down this list trying to find a match of the names and invoke the code and if this was a。

 you know if you had inheritance， this would have a point to a superclass and you follow the pointer the superclass。

 etctera， etc cea。What we can do instead。Is。Do a simple hash。

 and in this case what we're doing is we're hatching into class。With the name of the method。

We're computing some bit string derived from those two。

 and off to the side we have a table that's probed by this bit string that contains the true value。

In this case， in math。And I hate。Would be appointed directly of the bikeca。And so。

In this case when we're doing the cash look we're just going to find the class。

 we're going to get the name， which is usually there is the literal in the bikecode。

 do a simple arithmetic thing， usually usually some Xs and bit strings。

 probe this guy if these two match those two。Then we're off to the races we have our bikecodes and we can start executing without having to go through all the intermediate stuff。

 and this is pretty effective at making stuff。St faster。How is this modified by tagging？

Suppose X is tagged， what else do I have to do？Show the target。Yeah。

 so I have to look at the tag bits and figure out。Whether it is indeed a pointer to an object or whether whether it's a primitive type and if it's a primitive type。

Then I'll probably have a direct。😡，Point us to the classes of those things in my hand。

 you know I'll just keep those around as constant so I can basically do that translation from variable to class。

As a constant time lookup and then I hash based on that class and the name and we can go do the same thing。

 so it just saves， it adds an extra test at the beginning that's all。stripppping of the tank beds。

So I'm not going to walk you through all the code。All the code for that。

 so I'll give you a flavor of how it works。 this is lifted directly out of that small talk interpreter that I ran last week on the screen which was my master's thesis interpreter and that's basically a C clone of the small talk book。

哦。And in that， there's a cache which has four。Enreries in every entry， four fields in every entry。

The selector， which is a reference to the name of the method， is basically a symbol， the class。

Apoints to the thing we're going to call the method itself and in small talk the way you invoke primitives is that in place of a method body you can have a number which is basically a vector into a primitive table off to the side so if it has a primitive index that's nonze then we're calling one of those primitives instead of by executing bycodes。

So with that structure， then the method lookup。Routine looks something like this。

 so in this case we're sending a selected to a class。Because it's a bycode interpreter。

 a lot of the state is kept as global variables。In this case。

 the message selectedor was pulled out from the Bcode is often global variable but the class has passed in as a promise。

In this case， we do an exor between those two bit strings， module or the cache size。

 which has to do a power of two。And then we look up an entry in the cash。嗯。

Check whether we've got the match， the satellite selection class fields and if so。

 we set the global variables that are the place we're going to go to next when we're executing otherwise in this particular case。

 this cache doesn't do any repro。 It just goes it of a full lockup the fitness is the first time。

Those whole but， many papers have been written about alternate schemes。Dealing with these caches。

 reproing and all of that stuff。But this is such a simple technique。

It's not worth optimizing you want to put in better techniques rather than working on speeding that。

So this does a full lookup otherwise， which sets the same variables and then populates the cache with what it looked up and then off we go executing the next message。

Yeah， so you're saying like， you might not always update。In honor miss。YouNo， in this case。

 all those subjects can， but you could。Have another which didn't update the cash Well no what you end up with is different caching structures like the inline caches。

 which are not this is a global cache， this is one for everything。

And it's just hard to make the hit rate on this really。

 really good or the re probebes really effective。It's。

It's sort of okay for a low level simple implementation that without high performance。

 but rather than spend a lot of time tuning this， it's better just to putting in a better technique。

How big is the cat。Usually order about 1000 entries。Sort of you know， more than three digits or more。

 but not more than four digits， at rarely at any point in having it been。So the alternative scheme。

 which we look at in some more detail。The better scheme is to use a coalside cache。

 so instead of cashing globally and have doing the cross products of the payers into a single global cash is to have a coalside cash which was introduced in the pay last week which is and then you do the other tricks with compilation to put the branching in specs FL。

 but we look at sort of how you implement this when we look at compiling in a bit more detail。

So another thing probably coming up is adding a method look of passion to your interpreter and seeing how it speeds up just the simple one of these should make some difference。

Okay， so thats ends the。The section well take a break。

 and then we'll come back to memory management after the break。 Are there any。

Closing questions on my material。O。Oh， actually， what we'll do is after the break。

 we'll have a couple of presentations from the submitted。嗯。Obsent， so let me look up the nose。

Right right。By today， right by today because' I've already done that in some of slide Okay。

 and I think up and downarrow， we'll get you what you want。Okay， and yeah， Jack isn't here today。

 so just going to be a alone on this， I guess。嗯。Allright， so it this is。

But it's just it's just a web pages just。D容。So we made some new assumptions to try to simplify the white code。

Conceptally， there's no or first， first of all。We talked about like Java having annotations like two weeks ago in the class file。

 which is basically what's used to do type checking， among other things now。

So figure why not just make use of those annotations， why do we need type based icon codes。

 which is I think kind of the common idea most people followed。

And and you can also use the same thing to probably ensure data hiding so you can like kind of do an abstract interpretation like。

 okay， are we trying to access a field or method that's private or protected in an invalid context and the other thing is forget in the byte code spec completely forget about having different inger fluid sizes。

 everything is eight bytes， this makes everything so much simpler conceptually but the implementation can handle it however it wants because that's obviously wasteful and inefficient。

To finally just try to retain a lot of the Java spec so we don't want to modify a lot of the structures in a constant pool。

 just want to keep that like you know， change the bytecode set without changing too much of the way the data structures are implemented and and stuff like that。

So this is a bytecode set， it's cut down to 48 byte code instructions from what I counted was about like 160。

70 in the original spec。It's like not bad。 could have done better， I guess。嗯。

Probably notice some things。 there's a lot of things that stay from Java， but some things。

Definitely like all the type based stuff is all gone。

And I'll walk through like each of these sections is the only section I think I don't walk through is synchronization because that's exactly like the Java by code spec like we make no changes to that。

想说。Consts so we put a null constant on the stack so that that I think there is something in the Java bytecode for that so or like a null object you can put a constant on the stack so it's an op code plus the8 byte constant just very simple just a literal wasteful for smaller types but it simplifies the bytecode if。

If the implementation wants to do something smarter， go ahead， but I mean。

 by code size isn't really that much of a worry for my understanding。

 but someone could probably correct me on that。 And then we introduce a new type that's void and it's invalid to do anything with void except just removing it from the stack。

 And the reason it's there is just so that return you'll see later then just it just makes return like kind of uniform like you can do one return for whatever type。

 you don't need a separate return for Boy。啊。And so in control flow。

 we kind of took the idea from the Java bycode instruction compare。

 which just gives either a negative one， a zero or a one onto the stack。

It's used to compare addresses and integers and we needed a a separate floating point one because you can't just do a naive greater than a less on an integer type and expect to get the right answer for floats so that's kind of like the one downside we we figured that because of the complications of floating point types we kind of just ended up having to do this but compare eliminates a lot of the other things so we don't need a greater than greater equal less than less than equal。

And。Because we can just use this one and plus arithmetic for everything so we have an if as well which is it's just a branch it's two branch offset bytes instead of one so basically there I think there was a there was multiple different ifs in in the Java byte code to handle like a one by offset and a two byte offset just went for the higher one like you know you know。

Need one or the other， at least I don't think so， so it just pops one valley off the upper end set compares it to zero branches of true。

Go to is the same as Java Go to except branch offset is4 bytes by default so you don't have a go to underscoresco W that is4 byte offset right。

 you just have one go2 instance of is the same as Java instance of and return is exactly the same as the Java byte code so you pop the top thing off the opera end stack go back to the previous frame and put it on except you don't care about what the type is because everything is fixed with。

And if， you know， you can put a void on the back in the void case。

So stack manipulation just pop is the same and pops one value dupe same thing duplicates the top value swap so we are eliating a lot of the stack manipulation instructions by simply having one swap that has two unsign by offsets which basically tells you what to positions on the stack do you want to swap So this way you know all of these du 2 X1。

 du X to do 2 X1， you don't need them anymore because you can just use any number of swaps in dus to do it like it's lower but the micro set is much。

 much simpler。Next is bit manipulation， also fairly straightforward。

 a bitmin manipulation is only defined for unsigned inteerger types。

 but again the type checker can or the verifier can make sure that you never run any of these bycode instructions on something that's like a float type or like an address or something like that。

Next we have arithmetic operators again we couldn't really get past having float because we do need to handle float types separately that are fundamentally different。

We also need instructions to make the explicit cast to one help the verifier and also you know when we're actually like when the code is actually running。

 you know like kind of what type。Which like the the structure is right。So next variable manipulation。

 load in store all get rid of all typed loading stars just every bitete offset is so this it's a bite offset into the。

A local variable pool， but except you avoid the wide modifier by just simply saying that the index is two bytes long。

So yeah， you don't need many different stores because they're fixed with elements and yeah。

 so type checking on storage and loading it's all just done with the verifier and then we can just do everything naively。

Next object。 So there's I think two slides on this one we have。

We have new right we can't get rid of new get field get static put field and puts static so the reason we have these four still is because the way classes are and objects are kind of store or is different enough that we don't it just seemed too hard merge to try to merge and to just get and put。

So we just leave it with the exact same way that the Java implementation has it。So invogue。

So the same idea here so we have to invoke invoke static。

 but we kind of figured we can get rid of invoke interface and invoke special because we can verify interface types again through the verifier So invoking through an interface doesn't really need to be checked。

 it's really just another method implemented as part of the class So it's almost like when you actually run the code interfaces don't really exist anymore and with invoke special it was used for three situations data hiding So private methods constructors and superclass calls but all of these can kind of so the data hiding can be statically checked and you can like so you can't you actually do need to do a dynamic lookup。

 which is a performance cost， but I mean。You have less bikecodes， which is the goal。

 so constructs can be just normal virtual method calls and superclass calls。在啊。

You can just look at the superclass。Another normal virtual call and invoke that it is necessary for the same reason as before。

 and we left invoke dynamic because it was a necessary optimization for I read about what dynamic language languages previously had to do to work on the JBM and I just felt pity。

And finally arrays arrays also different two differently implemented to be handled those as like just treated like an object right so we have new array array length a load a store so technically in the whitete code you can have any type of object in your array so it's not that basically the verifier has to make sure that the types are fine but that way we can just blindly load and store anything into the array。

And yeah， that's the whole micro code that48 instructions。Questions。

Why didn't you just get rid of void and make all your void methods into like Ns？

ULially absolutely mean by that， I mean， you could just make all your like you could just make all your boy methods return zero and just be any another time。

Like see and it does not have a void Yeah that's true I mean it just felt a little cleaner I mean I mean it also arounded it off to 48 instead say 47。

😀Yeah。Again， yeah，'s we could have done something like that if we wanted to eliminate。Table switchs。

Oh， so basically we just said， yeah， table switch and lookup switch are useful for performance。

You can if you want to get rid of them you can just simply do bunch of those statements right so I mean yeah it's just it's just another decision we want to go minimal performance costs isn't that important to us。

But yeah， I mean adding those two wouldn't be such a huge cost because this doesn't make or a huge effect on other things。

There just be two extra instructions for your like。So more performance。

I may have mentioned whether through instruction Oh， I guess I forgot to write it down。

 There was originally a throw instruction。 I can show you my notes in my notebook。 Yes。

 there is a anymore， but there there is a throw and and it's untyped。

 there's a th It's just untyped in the same way。Okay。So in your opinion。

 is Duke and swap really necessary？Its by without。 Yeah， I was， I was thinking about that。 I I mean。

 I was thinking about whether you， whether you needed all of those things at all， but I。

Didn't look deeply enough into it I just kind of figured well。

 I guess there's good enough use cases for Duke 2 X1 for someone to have like gone through the trouble to implement it so I might as well just have a way to do the same thing。

好。喂呀你。Probably could do without them。So just to comment on that I've seen du being used heavily。

 at least for object constructors in Java。UD there's a new followed by a do and then a construct code so that the constructor is called and yet you still have reference on the stack。

And if you were to not have a Duke， you would probably have to store it in a local variables lab。

 so if you had an expression whether were constructors， which were not assigned to any variable。

You would then necessarily have to make space for those and local available slots issued in groups。

 so I think maybe that's the reason why。我跟住嘅。So I didn't quite follow how super was going to work。

 Yeah， that's that's one of the things I kind of hand waved a little bit。 Okay。

 well I was thinking there probably would have to be anvo super because that that was the case that kind of。

Kind of。 I doesn't， I don't think you can handle up by the generic。 Yeah， probably not。

 because you like you know， Bo saying it's super on right exactly So just add another。

 add another like bite。Just dynamic part of that。Okay， thank you。Thank you。

So this was actually pretty representative of many of the presentations in bringing up sort of similar kinds of things I was mainly looking for。

The realization， the type stuff could be exploited in the verifier to generate the information that's redundant in the bikecodes。

 and I think most people got there。あ。One or two people talked about the cost overhead of doing that in the interpreter。

Anyone see a way of。Doing removing the type information from the bikecodes。

 but still under the interpreter if。Like anyone actually had a solution what if you do check calculationilation sort of do like actually interpretation do to like to turn the types and then emit the proper code。

 proper code with right so you can basically translate the bycode into typed bycode if you want to interpret type bycode you to use some of the bits that have left over exactly exactly。

A of cashching。Yeah， you know what it is， yeah。And then I think most people had some alternate arrangement of the stack to avoid the weird schizophrenia that the JBM stack has the other one I saw in a couple of presentations which I thought was a good ones basically you know whatever's on the stack is on the top of the stack and the item sizes are not specified it's like the implementation has to figure it out how big the thing is and it gets to decide So making it sort of uniformly big is one way and just saying you know punting on the exact space requirements is in I think a fine way to go。

Let's see we had the Nathan and whoever the other guy was presentation you had some interesting monitor changes Yeah so what you summarize your proposed。

Basically the unlock monitor， it references the instruction of the monitor so that way because when you do the unlock。

 you're still doing a lot of type check like checking like does this thread on it have I done it multiple times and if you could like statically do it because you could just check the code tab Okay so you're basically checking for next thing of the。

I think one thing is like， you know， currently you could just pass like any object into like the unlock and like at least in the Vicode sense and。

 that doesn't really make sense like you， like I don't know of any language on the JVM that would like make use of some weird structure。

ok 啊。And then the other idea I thought that was interesting was merging the gas and the puts all into like a generic gaton port。

Bcode and using the information and the descript is a constant pool to distinguish between the variant。

And you can sort of push the information around semi arbitrarily or wherever you want it。

It all depends what you're trying to accomplish。Okay， now the other presentation I wanted to。

Seeing with the。Very different。We're getting something extremely old。it's actually not minimal。

 but it's so someone gets kind up to you。Walk us through the idea you don't have to give us。

 you know the huge details just walk us through the basic idea because this is very different I'm extremely tired so hopefully there will be semi coherent speaking and pushing data wherever we want so there a proof。

Recently， there's actually a single Intel instruction that is turning complete。

We did not do that We did close and did three instructions So the lengthda calculus allows you to be very complete with just invo we put go to if null because line increase a stack frame when you can just stay in the current stack frame and then we have CL which is basically the transfer between stack information。

 constant a method name， so on into our dynamic context So if we want to do function I did just before the constant pool then has to have reference to the something we know is going exists。

 which is the stack， the call frame， opera stack。They have methods。If those， if no they exist。

 you know they exist during runtime， so you put them in constant by some reference so you can load them and then go to them。

嗯。Yeah， so the bikecode is extremely unrestricted， less so even lend the calculus than the calculus is restricted by con carson。

嗯。就班咁有。so what you're doing is basically you're putting the names of all of the things that you need to get to or symbols in the constant and you're sort of insifying all of those operations and is just calculating using those insified operations verification is no longer in any way shape form possible。

😀呵呵。😊，Everything on the stack is a pointer， so in your objects are pointer to a tag and value。

 playing point be similar， so on and so forth。Though you could obviously it other ways。Cea load。

 you give it。Given identifying constant pool， it load it when I say constant pool， I mean items。

 it's a pool of items that we know exist via static information。

 the objects there can point to things that change so it's a constant pointer。

 not a pointer constant。き。Tisms。If just give me an example， go to live Nll。

 so it takes top the opera stack it's null， goes the label label is just offset。

Invoke is the fun part， so we have two arguments， the could commit three to make it look logical invoke is always a method call so the receiver object is always on the staff and then you also have。

The method index is also on the stack upfront stack， though we could have made that static。

 but that we can support some cool things。Argument numbers。

 how many other things you need to power up the stack， and then we have a exception table。

 which is should exception be thrown， which is called by a method on the stack object。

 it looks up the exception table and calls a function there and fill a function there。嗯。Yeah。

 do you have any questions， everything's invo， the example of I hopefully make things more clear。So。

 yeah。Do you want to one，Okay， so so this is an example。 So we since we only have three instructions。

 So we will simulate all the other G instructions by just using these three instructions。

 So this is the example we simulate a through。 we first load the cost stack from the constant code。

 Then we will load the through instructions pointer to the native function and we will invoke it。So。

And this is an example， this is a constant pool is cellburn stack and that's the instruction pointer。

And so when we first。Okay， so when we exclude the first instruction。

 we first load the cost that from the constant pole。

 Then we load the instructions pointer into the constant pool that will invoke。

That is a negative function。 Well， first of。Pop out the call stack of the receiver object。

 then you will pop out one argument。But the argument to the native function call and will evocate。

So here are some other thoughts。Basically， because in our。Biko design。

 Biko can operate on any met data structures so that load in the store can actually be simulated by put fuel and get fuel on the free module。

And。Totally of get feel can stimulated by invoke。It trails all the way down。This is another example。

 simulates equals B plus。So。So this first block simulates log A from local frame。

And we were first load say。This local index， then will load the cost that bring。

 Then will load the get fuel operation。 then we will invokecate。And then similarly to loading B。

 and then add up， we just belows the add instruction， then evokecate。Finally， stole。O。Questions。

Comments。Roughten fruit。So let me let me prefacerase before I answer questions。

 we went with the orthogonal instructions just to f ran so and we can be more orthogonal。

 we can get rid of go to of null and。Actually' as far as I'm letting you know but a。

Suppose if you ignored opera brands per second， and you just assign one bit or two bits to each one of these instructions。

 how did they compare？Oh sorry。I feel like you would actually have a blow up because the instructions set。

You should have a blog， I feel like the information the entropy there is that you have a blog。

 but it'd be cool to see how that actually works。Any questions。Comments this is a horrible。

 but our restraints were very thin， so our result is very extreme， thank you。

How many are you programming fourth？I read for it， was that a conscious influence， no？但我也希望。Okay。

 so just a couple of other。Sort of discussion points So， so， so why why in general would you。

 you know， redo the bike on saying， Anyone think of good ideas。

 good reasons for why you might want to redesign it what would you， what would you get out of it。

It will make it easier for people to wire terms language both language contents and that's like you wouldn't have to be through a mayor the state vote to figure out how to generate the proper code。

 okay。So users of the system would have an easier time in effects the people who are the clients of the bikecode。

稍等。One interesting constrain is if you can。dynamicynamic language interface correct with original Java byte code without having some special magical handling。

Whi is not by the constant。If the bikete code， if the instruction sets easier to reason about。

 then it's easier to jit over。Maybe。Maybe I think you can be more clever in your。

It's sort of the risk argument I say that you can have a if your compiler is clever enough。

 you may as well just have simple things compile so that I buy in general。

 one of the things I've observed is that there's a lot of code。

In a complex VM which is just dealing with this particular the particular encoding that's present。

 so you get that switch statement you know across all the light code types and a loop around it doing abstract interpretation。

Many times right and just reducing the size of that reduces the maintenance burden on the VM considerably if you can do that and not pay for it in some other way and in general simplifying that。

That is a is a win。So that's another good reason？The size of the compiled programs， you。

 in the Bcode format。Is that important？When， what here's it。Yeah。We are pushing on CPU bandwidth。

Of the， of the。By code set， not of the。Genenerated code the stuff that you get， you know。

 the equivalentant of what's in a dot classifier。Bytransworth。

 but I'm not sure how much an issue that is for look。 You're working in the JBM only what the。

 I'm not sure much issue is And there's been a lot of work done to shrink the size of the files down because it turns out that actually shipping the jar files around containing all the stuff is to significant。

Barrier to uptake and some problem some question to an open question is。

 is the right way to do that by bycode design？Or just putting a compressor on the transmission medium。

 right？I'm decompressing when you get to the end and who cares about what the size of the file is on。

So how big do these things get me， I've never gone around？I will ask staff dressing。

megabytes is very common and tens of megabytes is not unusual， I mean， have up for like the。Oh。

 there's the time。Those lecture files and zip files I。Yeah。

 exactly exactly so if you if you're geeey thing anywhere。

 does it really matter how densely encoded this is because you know it's not it's not what you're going to run and it's not going to be what you distribute you' going the entropy is going to be removed by the compressor typically to see biggest assets or right right exactly exactly。

在出来。So this was designed in。In the 90s。Yeah， and the context of the design is important because the context of the design was that they were going to put this implementation in set top boxes。

And remote controls because this was prewe， right， this was before people appreciated。

That the internet was going to be the distribution mechanism for content， executable content。

 they thought cable， the cable TV system was going to be that medium。

And they were going to put interpreters in set top boxes and in smart remote controls。

Which are obviously in 1991， enormously space constrained。

So the design assumptions have changed radically Ab and Gosling had this great line in this paper we talked about reducing the tyranny of the instruction set and now we have this instruction set that has lived I did a back in the envelope calculation to while it goes and get some sense of how much implementation effort was going into hotpot。

And I think it's somewhere on the order of three to 500 person units。And I， I would guess。

Fully 25% of that is due to that 50。Just dealing with the ins and absolutes and the complexities。

 and if you'd picked a simpler one， it would have been a lot。

Do you think full employment for virtual machinists is a good thing then？

And maybe you don't mind about that。But it it is a very complex。O。

I think that was all I wanted to see about。 any， any questions before we move on or comments。

Let's make a start on memory management thing。Okay。

 so this is gonna to be drag out over probably several sessions， although I'm going。

Amit the more e satoteric parts until very long， depending on what schedule pressure is we might not may or may not get a concurrent and parallel collection。

 but I'm going to cover the basics of ce collection now or next week for sure。There are two。

 unlike the rest of the course， there are two really really good books in this area。

 both by the same guy as the Richard journals。W wrote this one in the mid-90s with his call for basically just contributed one section。

 so it's mainly Richard Jones's book。And then he got updated a few years ago with a couple of good co-authators who reorganized the text and added new material because in the interval。

 you know sort of the first one was written just as Java period a Java spawn just a massive amount of work on GC and so a lot of the papers in the intervening 10 years and nicely summarized and this is the book itself。

And I have to copies because I did a review for the publisher， so one of them is the prize。

Practed implementation of fee。You're not eligible。Does that， does that a replaced person。

Not entirely as a practical handbook， it does if you're looking for things that you want to implement as a work of scholarly description。

 it doesn't。Because the first book describes a whole bunch of things that were in the literature。

 but theyre really never one， you know， they're sort of interesting if your objective of study is GC。

 but they're not things that you're actually going to。

Put into an implementation so this is the one to start with this is the one that has all the good stuff in and occasionally you know you'll find other techniques or rather even cross reference it'll say and there's this all obscurer thing then go really the block if you want to learn about。

Okay， so let's start from the very beginning， which is。Why do automatic memory management at all。

 you could do static allocations？You can have names， bounds to locations， compile time。

 the link time。The size of everything is fixed， there's no stack。And you know that really works。

 people have written real programs using that once upon a time。

 all programs were written like this and it's still used in the embedded and realtime world quite heavily because you know if you don't do this stuff。

 you don't pay for it， there's middle costs that run time for doing all of the management of the stack or allocation of GC or freeing or whatever。

 but more importantly， you can't fail because you're on our memory you've decided up ahead of time exactly how much you need to run your program correctly。

And that's what you use。 And you're not going to run out of memory at run time。嗯。

I'll tell you one funny story， which is when I was learning to code back in high school。

 we used to write programs in basic。And the basic system used this technique。

 it was like Fortranran in every subroutine had a link address allocated in the compiled arena for the return code。

 because I didn't know any of that because I was just a beginning basic programmer but halfway through the course I picked up a book on Al Go and read about recursion and thought。

 oh， this is cool。And tried it unfortunately or fortunate。

 depending on which way you're looking at it， when I went to the next time to the computer so back then we handed in sheets of paper with our program right now and they gave us back the listing of what happened when around when I went back to pick it up I got a line printer output that was about two inches thick instead of the usual you know three pages。

U because， you know， the recursion I'd written had'd over written the return address。

 the link return address and the thing that caught up， so I got， you know。

200 pages of ocal dump with a note from the programmer in charge of that manframe saying come and see me and he explained what happened。

 he'd have to wade through the core dump to figure out what happened and said don't do that again。

Well， you know when back then paper was in scarce supply， lasted me years that last。Oh。So you know。

 it used to be done like this all the time， in fact if it still is done in the realtime world。

 if you want to have a hair raising experience， you'll find the expert witness testimony in the Toyota trial of two or three years ago where you know there was this thing where there were unintended accelerations in Priuses and other cars and an expert was brought into to look at the code and they found things like a recursion。

In the source code of the controller for the engine management system， right， which。

Stack overflowing your car， not a good idea。So worth knowing about the alternative， but， you know。

 it's not been widespread used by any Australia。So the downsides， there are numerous ones。

 mainly in that you know life is just difficult as a programme or when you have to live with static allocation。

 you can't you have to do all of your calculations for the worst case up from and's maximally sized structures and you can't change the subdivision dynamically so if you're in an environment where you can do any kind of time sharing or resource sharing this is not going to be good because it sort of grabs everything and keeps it all the time。

Its a fix of divisions can't adapt， you kind use the recursion。

 you know you can still do it in things like the Java realtime spec there's a sort of a you can write critical realtime critical sections in Java and if you do that you can only use static allocation in those parts to avoid this problem so basically you're punting the dynamic behavior is the noncritical part of the program and if that fails no big deal you know that part of the system gets restarted but the critical part keeps running。

Okay， and I think I answered the question myself。So。Dynamic allocation and stack。

You're all familiar with stack based routines， mostly follow a life or principle。

 as you saw last week in small talk systems， some don't。

Some follow a nonlife or discipline and so you have to deal with heallocation of stack frames in some form or another。

 but if they don't， you can most easily do things as a stack and processes that acknowledge the presence of a stack by adding in things like color snack pointers in the 60s。

And so all life is good， if you don't have life or activations。

 then life is difficult and you have to do some amount of you know fiddling about with a stack and copying sort of continuations and scheme。

 you have to do this small talk activation records。

pot first class objects and it all sort of all implies that you know things are heat allocated which will make you green。

 but as you saw last week there are tricks to get around that I'm not going to go into the detail here because these languages are still pretty much in the minority and the chance that you haven't to implement this in a high performance where to probably remote and if you have you've got many more problems。

So mainly we're going to be talking about the heatEPA。So the heap is。Arbitrary memory pool。

 you know the program can make requests of any size in any order and the pool has to give back chunks of memory and the sizes that were asked for and if you can't give back a chunk。

 you say sorry but I can't give you back a chunk and then you've got either the language or the programmer has to decide what happens in those cases the programme gets to do something and behave differently all the system just stops dead in its tracks at that point you know either of those it's all dependent on the semantics of the system but usually you're making your best effort to give back。

Give back the memory thats successful the pool can consist of many separate contiguous areas。

 right it used to be that you know。Memory was this linear thing that was not virtual you just got a big chunk of it and you allocate it out with the chunk these days。

 the way you get memory in OS based systems is you call down to the OS and it gives you a chunk of mapped virtual memory back and it might not be contiguous with the last chunk it gave you you have to deal with disc。

Conti the hate。But that doesn't usually make for much of a problem。

 the only case situation in which that really covers a problem is somebody asks for a piece that's so big that none of individual pieces can satisfy it。

 but that's very rare and unlikely。So your first order problems really are you know allocating and delocating。

 that's the thing that's most common， that's what you've got to get right first。

 so let's look at allocation。The classic technique you see is a free list。

 so here are all your free cells， there are of different sizes， they're linked together in a list。

When a request comes in， you have a number of choices of how to satisfy it。

 you can pick the first thing that satisfies it。So that's just， you know。

 you walk along the list and as soon as you find a piece that's big enough。

 that's the one you're going to give back。What you have to do is split that chunk in two if it's too big。

And thread the remaining piece onto the west。Very simple， straightforward。 No difficulty there。

There are many other scheme variants on the scheme best fit is another common variant and that best fit means find if you find a size that's the exact right the chunk that's the exact right size。

 give that back。Otherwise give back the next biggest one。that you found， so in this case。

 there are none the exact right size， that's the closest fit， it's just a little bit。

Too big And so you chop off the tail and add that to the list Now you can come up with some interesting redefinitions of best here because the problem with doing it in this way is that you end up with an awful lot of small pieces that are mostly useless best can be the opposite extreme night the biggest。

ive the get the biggest piece and chop that up So there's a number of variations on these and you have to figure out sort of which one is appropriate in your system I'm not going to go through all of this in a lot of detail because it turns out this is the wrong way anyway。

We'll get out to better ways。So you can you know you can keep these things off to the side。

 you can have you know special lists of useless pieces， you can do all sorts of techniques。

 you can re up the size of the request suppose this is only one word and your minimum object size is two words well this one word thing is useless right you can't do anything with it so you're either going to keep it off to the side you don't want it on the free list because you're going to have to traverse it every time you look down the list you might keep it off to the side as a separate list of chunks well you might just re up the request and then keep an extra word with this object。

That's also a common technique。Yes do they sort no， not usually sorting is not considered。

Cap enough typically so they usually。Usually the list gets really chaotic after time if you've got a single free list because the requests sort of break it up into pieces and the distribution of sizes。

这个单。そ。Yeah， well， it's so if it's the same， then it's best and then what you could do is go down the list and keep the smallest thing that was bigger and use that。

That's a common benefit。These are all， by the way， things that are typically done in malloc。

 and malloc is really slow by comparison to what we're going to do。Okay， so ass the。Next。

 fit is another。A commonmon technique and that's in next bit what you do is imagine that we started with a list and we were allocating from the front of there as you allocate from the front。

 you're chopping up the big pieces of the front and you end up with a lot of small things the front of the list。

Often those things are so small they aren't really useful。For much。

 they might be useful for something， but they're not dying at the frequency of their usefulness is not very high。

 And so rather than traversing that prefix of the list that contains a bunch of useless stuff。

 what you can do is remember the last place you got a block and start there And to do that you need to make it instead of a list into into a a cycle a queue So in this case。

 what we do is when we split this into two， we next start the search from this part。

And we were round and round the cycle looking for things because obviously you need another pointer in your hands to figure out when you've gone once round and come back to the beginning。

Because you don't have the mill point end the less to do that。

But this is another fairly common technique。So unfortunately， this is all slow。嗯。To implement it。

 you need a loop。The number of iterations in the look can be large because you working down to be going for a long time。

 you need a size test because you know how big piece you want don't know why a bigger piece is coming next on place and you need to be able to split up a block And by the time you can the logic for all of those into one thing there's no fast path。

 you can't inline that whole thing at every allocation side which is really what you want to deal it's just too big。

 So you don't want to do this as your basic technique So how do we deal with this。Well。

 I haven't talked about the distribution of the sizes in the system。

 either the requested sizes or the allocated sizes， and obviously that depends on the program。

 but it's heavily influenced by the language and the style in which the language is used and the available libraries。

 if all the data structures in your program are coming out of the library。

 then the sizes are going to be succeed by the library。

 if it's the standard library that goes with the language everywhere in everybody's program is probably going to have。

obbjects of sizes distributed dictated by those libraries so you end up with very skewed distributions of sizes。

 so examples you know on lesssp then there's going to be a lot of two element consoles around this just the language you know that's the way you do stuff and lesssp and so you're going to see a lot of those。

As I said earlier， in object oriented languages， most requests of small objects。

2 to 10 fields is the common size， very rare that you see stuff much smaller than that one field。

 zero fields， you know， sometimes there are zero field objects， but they're not very common。

 and it's very rare that you see stuff with more than 10 named fields because programmers just can't carry that many names in their head when they're writing writing programs right。

 There's this old psychology result that says you can remember on average。

 about seven things in short term memory so that's how people write their programs they push the other stuff often into subobjects are into super classes and abstract over it。

 That's why we are abstraction mechanisms。 So that。Dictects demographics a lot。

And the only exception to that typically is arrays which you know there the abstraction is the index and so programme doesn't make the programmer's life any harder as to whether it's got 10 elements or a million they're all treated the same way。

 so you tend to get this very bimodal distribution of sizes of very large number of small objects and a few large objects that contain the arrays in the other data structures。

And we don't have。Optimizations for coalescing objects that are really effective。

 There's been some amount of work done and trying to figure out in a compiler how to take。

A graph of objects as described by the programme and gl a bunch into a bigger object and manipulate that。

 but none of those things have turned out to be really practical。

 we don't have them in VMs maybe if someone's looking for a PhD topic there's a good way to go if you know you can make an end bike。

Figuring out how to coales objects at runtime and that then would change the assumptions underlying GC fairly dramatically and we' have to revisit all this stuff again with different techniques。

So one of the things we can do if most objects are small is deal with the small objects with specific cases and then sort of pun to a free list for only the big stuff。

So for the small objects we can have a free list per size right so the one field object which is typically three words because there's a header can have its own free list。

 etctera for two fields， three fields， etc cetera， and that eliminates the size check because now everything in the list is the same size we know the thing on the front of the list is the right size by definition。

It eliminates the splitting of objects in the pass path because you go down this list and they're all the right size。

 you only need a general free list for the large stuff and for when the smaller free lists exhaust space so if you end up with a small free list that's empty you know you look down the thing and there's nothing there well you take a bigger chunk and you chop it into pieces and populate a free list and this is a very common technique。

It's used a lot and sort of look graphically as you might expect。So， you take。You take these guys。

 which are the freeest heads and you stick them in an array。

And then you index using the size of the thing that you're trying to look up and if you you'll need typically at the allocation point。

 you'll either know the size because it's an instance of a class and so those things are compile time size known or it's you're allocating an array which basically it could be any size and you're going down this list anyway。

 so typically at the allocation site you'll know which list head。

You're concerned with and so you can compile that in and start but basically it's a simple test to see if it's known。

 if it's not known pull the front finger off the front and you're done。

So this is sort of the best you'll get with free lists。

 typically constant time lookup in the common case。Now， the。

The demon in all of this in managing stuff by freeless is fragmentation。

So as free memory gets chopped up into smaller and smaller pieces。

 it fragments and then you get the problem that you want a big piece。

 see somebody asks for a bigger array or an object that's not allocated very commonly and there's tons of free memory。

 but there isn't a piece that's big enough to hold the thing that you've got and now life is bad because have you have to somehow reorganize the system to coalesce things or you just say sorry。

 we're dead program is over。Reta。Which is what is the common case right and we see that's what happens you call malloc。

 if Mallan gives you back zero because you can't find a space。

 you don't call the garbage collect it because there isn't one， you die。

So this is common and painful andd rather not't go there if you can。

Now there are two types of fragmentation， the one that I mentioned earlier where you over allocate because you have some constraints on your allocation sizes and this is more common in some kinds of allocation schemes where for example all your allocation sizes or powers of two socalled body system that's common in operating systems page sized things but it's not common in language implementations so you might get a little bit of internal fragmentation。

 another cause of this is alignment things so you want so you're on a 64 bit system and you want every object to begin on a 64 bit boundary well they're not all exactly multiples of eight bytes long you know all the bos and shorts and stuff in there and so you might have to pad a little bit at the end and thatll give you some internal fragmentation。

But the more serious problem tends to be， or at least the more solvable problem tends to be external fragmentation。

 which is you know the fact that you've got many small free blocks， but no big ones。

And we'll deal with that with collections， so we'll get there in the end。Now。

 how fast does the allocator need to be， is this important？And actually， it is。

In any object oriented language， you objects are common， so allocation is frequently。

 allocation is happening all the time。嗯。Now it's worth remembering that initialization is typically linear in the object size。

 the bigger you make the object。The more it's going to cost you to zero it out or set it up before it can be used。

 and so the pressure is to making the small objects cheap to me as close to free as you possibly can。

 so very light costs for allocation and very efficient reclamation。

When it comes to recycling that memory tip， so that's the pressure， the large object， you know。

 somebody asks for a million element career， they're not going to expect that to be ready。

 two cycles later don have to。Fer care all this space and fill it out and they're probably going to fill it with some days that who knows where that's coming from that might eye out it's the small stuff that you really。

You really want to make fast and this。So there's a more general point which is worth bringing out here。

 which is that objects are a kind of abstraction。in programming languages just as methods or functions are and it's a good goal。

 a really good goal to try and make abstractions as cheap to execute as possible that more you can reduce the cost of an abstraction the more people are likely to factor their program is in good ways and shape them and divide them up and so sort of our goal as VM implementers is to try and make abstractions really cheap you'll see when we you cover the compilation stuff that。

Practically you can make method calls as close to free as makes no difference by the inlining techniques。

 that's an achievable goal， this is much harder no one has got this down to zero， not even close。

 but it can be made reasonably cheap。And the cheapest technique for allocation is bomb allocation。

 and the setup for bulk allocation is we have a big contiguous region of memory。

We start allocating from one end and we keep a pointer that says we've allocated up to this far and when a request comes in。

 we do the easy thing。We bump the size up。For the requested piece and we're done and the only other thing we need to do is check if we fell off the end。

It's very cheap， it's very fast。The code。Look something like that。

 which is definitely something that you could put in line at every allocation site Okay。

 so we have a P is the thing we're going to give back。Free is our free pointer。

 and end is the end of our free block， we increment free by the size of the things we want to give back if that's going to fit within the region。

We just bump the three pointer up and return the thing we that it used to point to。

 It's very simple and fast， but you may ask。Right。Didn't did we cheat， I mean， hold on。

 what's the sale Peter， What happens when this thing fells right。

 and we free stuff up and aren't we going to just degenerate back to a free list。

Is it like a one shot thing for one？Itseration of the heatap。

 you get cheap allocation and then after that it's all free less。No， but to get to the end point。

 we have to go through this circuitous detour through some other techniques of garbage collection because it's not straightforward to explain all in one go so the target will be a compacting garbage collection which basically starts with a heap that looks like that with everything at one end and when it's done after you've allocated the GC it looks like that again that's the end point the cyclic if we look at some others in between。

Okay， so the complement of allocation is deallocation。

 so you know if the language says the programmer does that Hooray， we're done， you know， great。

 it's that problem。But alas， it probably isn't going to be。Your problem。

 why is it what are the advantages？Gbage collection， Why do people put it in？

Do they push the burden onto the programmer？Because it or goes wanted to think about it。Yeah。Yeah。

I mean， it's worse than that， right？Even when they have to think about it。

 they get it wrong and when they get it wrong， really bad stuff happens。

 So it eliminates main reason is that it eliminates a class of unsafearrows。 and the unsafearrow is。

You free the thing that a pointer is pointing to and you use that memory for something else。

But you keep using the old pointer as if the old thing were still there。Right， and that's， that's。

Bad stuff happens because you know no one detects when that happens and your program is incorrect。

 but you don't know it until sometime later when either you know your bank balance goes to zero or youve got segmentation or something like that right it's a really。

 really nasty class of error because it's not the triggering of the error behavior doesn't result in a flag saying something bad happens。

 that happens much later if you're lucky。Maybe not at all， maybe you just get corrupted data。

Is there any system or is it possible to have explicit delocation but still have bulk allocationlocation？

Splicit deallocation end。呃，20。I have to think about that，Do it internally and see all the time。

So like I've written lots and lots and lots of things to see where we write a stack alligator。

We call it a stack algorithm it the same thing and you just All。

 you ask all to give you like a megabyte right oh so you didn't the allocation from your own region Yeah sure and then you give it to like。

Module， right， so like Ivoke some sub thing， a function or like something more complicated。

And you just give it a megabyte of memory。And then when it's done， you just free the whole thing。

 so that's region based， it's collection so you give a chunk of memory。

So within say the scope of a function， it has a chunk of memory which can bump allocate it but when the function returns。

 it just gives it all back because it isn't。Well， that's probably not what you were thinking of。Yeah。

 I mean， the most general case I think I have to think about。

So Philip Res wrote this paper about hinted garbage collection。

 which where delocation structures become him for a conventional garbage collection。

 so that one is I think is kind of interesting。It might be a hint just to run the。う。

 if I can get Peter Kessler in。Peter was the implementer of a lot of the garbage collection stuff in Hotspot。

 and the ban of his existence is System。gC， which is the Java entry point that says。

Do a garbage collection for me because it's like programmers never。

 ever know when to call that properly， they always make both things worse。

So the other really good reason for doing this is if your program is written by more than one person and you're composing things together。

If you have to compose stuff。With memory management and explicit delocation。

 you have to come up with some really good discipline a regime for who's going to do that because when you put stuff together。

 someone that have be in charge of each individual cell and know what it's going to be deallocating and that's like the being of really large systems programming using explicit deallocation is kind of figuring out the rules by which everybody operates and enforcing them in a way that's acceptable。

Yeah had a question well， so what do you mean by explicit de so the programmer says I'm done with this。

 you can free it so like Ru is not a government of language that has safe pointers because it's all stack。

啊。Would you consider access the language， meaning what by pointers because they're statically checked there a you need to like to solve the alting problem No you don't because just restrict the use course to the in certain cases。

So if you're familiar with C++ each pointer， so basically all points are unique pointers。Yeah。

 actually， your rest of all points are unique point。

 So it's aesthetic static property the table check where you consider that a it's like an ownership and yeah。

 it's literally ownership applies the language is that a。Slyd if you can figure it out ahead of time。

 then yes， even if it's not coming from a programmer。

 but you can derive it from the type information， yeah， I would consider that explicit deation。

And in fact， one of the goals of some compiler optimizations。

 even in languages in which you can't do it in general is to figure out some specific cases where the compiler can say。

 oh I know now this thing is free until teller system to free it up but you know most languages it's like either one or the other。

 you either get explicit deallocation or you get automatic memory management and then sort of the burden is on the implementer to tell with the automatic system。

Okay， the one thing of course this doesn't prevent is memory leaks right。

 because you can still build structures that you're not going to use and have them referenced in a way that the garbage collector can't figure out that you're not going to use them。

It's not a cure all by any means。Okay， here's a little quiz for you。There's a little C Java program。

 excuse me。Is the main this is the whole program minus the junk at the sides and I highlighted a tricatch which needed here for to make it run so I'm taking in the argument strings。

 I'm going to read the name of one as a file read the whole thing into a list of strings and then I'm going to count how many。

Lines are in that file and printed out。 Can I reclaim this data structure。

 which is the list of strings right here just before the the print line， I'll give you。

15 seconds to think bow in， and then I'll take a show of hands。Isn't it reading the program file。

Isn't it what， In't it read， I mean， as presumably zero is No，0 is the first argument。一家这。

This is just a random file。 Okay， who thinks I can reclaim this data structure at this point before Prince statement hands。

我们其这个。Who thinks it can。We going be sick you can。Why do you think I can？おび。

Is extremely conservative garbage collect。canActually sure you can in this specific example。

 sure you can because it's not used， right， the whole point。

Things are reclaimable when they're no longer going to be used。

 so an ideal definition is that an object's dead when it's no longer needed。The unfortunate part is。

 you know， the system has a very limited crystal ball looking into the future to figure out whether it's going to be needed or not the programmer might know that。

And that's why you can do free， In fact， you have to be able to know that to do free because it's call free。

 you have to apoint it to the thing right， which means after you've called free chances are you can still access the thing so it's the programmer knows this。

 but the compiler usually or the VM usually can't figure this out It can't figure out whether something's going to be used in the future or no So instead we use this other weaker definition for all GC work。

 which is reachability from the rooms。So the roots are typically the elements of the program that are declared like the variables。

 the stuff that's on the stack， the globals， statics， stuff like that。

 and if by following pointers from those， you can get to an object then there might be some way that it's going to be used in the future you haven't got the ability to prove that it won't be used。

 but if you can't reach it。Then for sure， it's dead。 Yes， So you said that the system can't do it。

 but then we have this really intelligent system called the verifyifier。

And you're saying that the verifier can't verify。对。Holding problem。In general， you can't do it。

In specific examples， you can't， but in the general you can't。我的。Okay。

 it can still fail to verify that it's。Can。Dispo of this if you can prove that it's not going to be needed sure you can remove it so in a case like that example a compiler could say well that variables dead there's no way that that thing can be removed so I can look at this point reclaim it but it's a limited set of circumstances。

is 99% Now in this case， it turns out to be very limited， very limited。

If you only implemented compiler style flow analysis and did only the reclamation that that gave you。

 you'd run out of memory real quick。That's actually a question about hotpot。

 so would your compile generate codes to remove this example。

 the list from a local slot in order to make it。based on life analysis。

 the example where the compiler actually does something。

Its typically in escape analysis where it's trying to in a body of code prove that something that's being allocated can't escape that region so it doesn't actually really have to allocate it at all it's very rare that an example like that comes up。

Where where the compiler can go， oh yeah， I could remove this here and it goes ahead its not so infrequent it's not worth bothering。

But Martin， so but the compilers do often they use life analysis to allocate many things and not allowed the same time to the same step slot's we over each other。

Right， right。You couldnt have language math I said that once it' it can only be used once so as soon as it's used。

 Yeah， sure， sure functional languages get a lot of knowledge from sort the fact that stuff isn't mutable yeah。

Okay， so reachability is a。A picture showing roots and a bunch of objects and a bunch of pointers。

 and take a quick look and try to figure out which ones are the live ones and which ones are the dead ones。

哼。大さ。你是诶。Go and check。Yeah，对。Okay， so this one is right these are all。

These are all dead are all dead。And the reason is。When you follow the pointers in the directions of the arrows out from the roads。

 those are the only ones you can get to。So if you look back at the earlier picture of the rawands pointing into this graph。

 but theyre ont count， they're not reachable from the roots。O。

So let's start with a problem the easiest and all memory management technique。

 which is reference counting and is surprised if you don't know what this is already。

So the idea is with each object we maintain a reference camp。

 which is the number of times the object is referred to。

 the way I think of it is the number of incoming arrowheads。

 the other end of the arrow doesn't matter because the number of incoming arrowheads。

that you care about and so when you copy one of those you increment the count。

 when you destroy one of those references， you decrement the count and if the count falls to zero。

 well then nothing is pointing into it and you can free the object because if nothing is pointing into it。

 there's no way to get a pointer into it。Unless you have a type onsafe language and you can do random casts of stuff in which gets none of their supplies anyway。

So in this particular case there are the reference counts， I hope I got this right。

 so count the number of incoming arrows and that's the reference count。Okay， so。

That one can be reclaimed because it's zero。And when we reclaim that， that destroys the pointer to a。

 which drops to zero and so that one can be reclaimed。We can't claim anything else。

Which is the problem。So how do you implement this， The easy thing is sticking into your field and your object。

You build operations that do the counting up and the counting down。

 the countdown has to test for zero and do the free。And then the free has to call the kdown， right。

 so because when you frame an object， you find all the references within it and that you count those down。

And then once you've gone through all of that process， this is recursive， you know。

 it's a free as calling countdown， countdown is calling free objects finally at the end。

 you can actually free the memory。That's the simple implementation。However。I got confused。

When you decrease your reference。And then you remove this object。

You have to follow all of the outgoing pointers from that object and decrease their reference cancers because you're about to throw that object away out a tree。

Should I run the animation again？Okay， so when something vols zero， it becomes garbage。

 but all its pointers are about to be destroyed and so the things that it points to have to have their references decremented。

And they may fall to zero and hence the recursion， that's what the recursion is doing。Now。

 one downside of this is we're allocating。And in here and it's usually pretty wasteful to allocate a whole word for the count Okay so how many was's the maximum reference count you can get in the system well you know if every word memory points to one object at the end of memory then sort of it's the number of words in your address base right which is sort of typically a word sized quantity。

U but it's very rare that anything like that is going to happen。

 mostly you end up building trees in which half of the leaves have got a reference count of one。

 you know， half of sorry the leaves have a reference count of water and the interior areas。

Might be something more or something like that。 reference camps are usually very small been some empirical studies done of life systems that show you know one is the most common two is occasionally there3 a few objects are really popular but most things are really small it's kind of wasteful to allocate a whole word for the count So a common trick is to restrict the size of the count to a much smaller quantity like 8 bits Well the problem there is once you get to the maximum value of8 bits the next increment isn't going into increment beyond 255 it's going to stick at 255 and so now you can never decrement because you don't know what the real count is you just knew once it was a 255 and now it's just going to have to stick at that point so that's called a sticky reference scams or saturation of reference counts。

It's very common and it modifies your code like this。

 so before you do the increment you have to test whether you've reached the maximum and when you do the decrement and you test whether you've reached the maximum because you can't do anything if it's the maximum count otherwise you do what you did before。

There's an interesting clever little trick that's used to make that quicker， which is。

 suppose you're doing eight bit reference counting。

 if you put the sticky bit at the least significant end， not the most significant end。

 so basically when the number is odd， it's stuck and went even it's not stuck。

Then you increment in twos and your decrement is easy because when it's stuck， decrementing by two。

 still it stuck and you don't have to。So you've aligned a test。In this case， it。

It was used commonly in small f systems， I don't know if Jonathan remembers this。

 I think Elier came up with this one。Or at least I heard it from6 I was Saturday。ve seen a。

Maybe as I say well， but you need the test right it's got to tell you whether it's saturated if it did。

 so it's going to be a saturated ad with some flag beings countdown。Yeah。So in use。

 we now have to rewrite some of our code， some of it might be to the studio they just stay around。

It would get to that。There's quite a stack of pending problems that this have to be resolved， yes。

Could you keep a second table somewhere that just sort of have all the you only need to look up Yes。

 that's another way doing it， but that costs then you have to put some more tests and logic and admittedly at the slow path and not the fast path but yeah you can do it that way。

Absolutely， and if you get the， you know， the book has like infinite variation somewhere。Okay， so。

So I were earlier into one of the earlier ones， and don't remember which one now had a couple of lines that looked like this where we were pushing a value onto a stack and we were popping a value off the stack。

You might think you can just get away by rewriting the pushes and the popps to do the reference counting。

 can anyone see what the problem is if I just do that naively？This one。

 this specific example might work， but in general。Why can't I just sprinkle the bushes and pops with？

With increments and decrements and sort of leave it at that level。Well。

 so you end up with things like。A reference being popped。😡。

Before it's pushed and count falls to zero in between。That can be a problem。

You also have to deal with a situation where you copy a pointer onto itself。And so。You know。

 if you decrement， then increment。Bad things will happen。So you can't in general just。

Decorate some of the low level stuff in this case， I've rewritten the book。

To do things more directly and one of the reasons is when I do this put here because I'm doing a pop。

 I mean in fact， the reference count of the thing on the top of the stack doesn't change because the reference moves from the top of the stack to this other location。

 It doesn't actually you increment anywhere it's just the move of the thing。

 and so in that case you don't want to do a decrement and an increment。

 you just want to optimize that pair away and save yourself the hassle and that's what this slightly optimized version does it only counts down the value that was the old top of stack's sorry the old value of the variable that's being overwritten。

So this is a common kind of thing and you sprinkle these current up and countdowns in your code and you debug it for weeks and weeks and next weeks。

 trying to find out where you missed one or you put one in where it shouldn't belong and eventually hopefully it works。

嗯。Notice a common misconception here is we're copying references into the implementation languages variables。

We don't count those too。The invariant here is that the references from the roots and the system objects are being counted。

 not the transient things in the implementation because these are。These are going to go all right。

 they're just artifacts of the implementation that we can't copy something without that point it somewhere else。

So you， otherwise you end up with this horrible knot way of incrementing the counts and then you have to increment the counts and the routine that increments the counts。

It doesn't end well。Okay， so a few little practicalities and then next week we'll look at tracing collection so in this straightforward implementation you have to reference camp everything。

 all of the variables in the language being implemented on the stack。

 the global variables in that language in the heap。And even when you return from a stack frame。

 right， if you have pointers in the stack frame， you have to decrement the references of the things being pointed to from that stack frame。

So there's a lot of increments and decrements going on here。 The basic thing is， you know。

 you're writing an assignment people's queue and there's an increment and。A decrement going on there。

 in fact there's yeah， there's the increment of the thing。

 the Q and the decrement of what P used to point in。

So there's a lot of extra science stuff going on here。If we're tagging。

 then we also have to layer the tagging code around this to make sure we're not trying to reference count ends because they don't point to anything。

And you also have to deal with things like null pointers which I alled from this。

 so if you're doing reference counting， you don't know that you're not being past a null pointer and so you have to exclude nulls from being reference counted some systems also have certain objects which are critical to the operation of the system must never be reclaimed and so a common technique is that you assign those objects。

 low numbered addresses so when your system boots up you allocate those things and then remember the maximum address of the things you want to keep and then a single test。

Can allide to those and no because they're all less than a certain address。

 And if you arrange your tagging so that all the taggged variables are negative。

 so you put the tag bear at the high order end。Then you can align to those two。So a single chip。

 a single comparison eliminates all the tagged variables and null and the system objects that you don't want to reclaim。

And that's also a nice， nice little trip for a ra camping system that avoids extra tests because this is happening so often you really have to think about。

this is implemented， you can in a annual implementation。

 you spend 50% of your time just implementingcrement the decrement。嗯。

Another trick is that count up and countdown are usually defined as macros rather than functions because you don't want a function column overhead for those or if you're generate code。

 you generate them mid line one of the reasons I wrote them，That is a pair。Like this。

 instead of in lining this into here and having a single thing is you could make this a macro。

 but if it was recursive。So you can macroize the fast path and just leave the slow path as a function call because freeing is an infrequent activity relative to everything else。

Yes， if I'm implementing this， are there any。I don't like debugging consistencycycl to make sure。

 I just forget one count it seems impossible to well。

 so the main one is we'll see next week that because of the cycles。

 you need another collector as well。And the other collector can recompute the counts and when it recomputes them。

 it can check that the ones that were stored were the right one。

That unfortunately doesn't tell you where the bug happened。

 it's just since last GC you got a account wrong。Because maintaining it globally and checking globally unless you force a collection really often。

嗯， that will ask。What about in the presence of saturation？Yeah。

 so what it will do is it'll recompute the fact that the saturated thing should be saturated。Okay。

Okay， so。A couple of the things worth noting is when decrement the camp of an overwritten reference。

Uual get a cache miss because you're decrementing something that we used to point to。

 but you don't point to anymore that thing might not have been used for a long time。

 but you're going to the object and you're incrementing you're decrementing its camp so there's often a cache miss at that。

When you increment the kind of a copied reference。You have to do a right to the object to increment its count。

 even if you're only reading the object。The object might be shared across a whole bunch of things in read only mode。

 but the counts are being incremented。So the implications here in a multiprocessor environment are not great。

 but you have other problems with race conditions in a multiprocesor environment。

 which we'll get to you later。So making this concurrent is sort of a challenge to make it concurrent and reasonably efficient。

Okay， there are a couple of practicalities around the freeing。So。Is the frameing code。

Can anyone see a possible of downside of this implementation？

Think about what happens when I have a large structure like a tree and the point is at the head of the tree falls to zero。

 what's going to happen？中发。Whenever it goes in。Well， a couple of problems， one is that。

You' want to get a lengthy pause while you free the whole thing up and you're doing nothing else while you're free。

So you're not running the program， you're just walking down the tree。

 decrementing counts and adding things onto a free list。

So you've got a pause induced from the freezing of a large objects and that pause is limited only by the heap size and the worst case the structure fills the heap and you have to wait for the whole age would be traverse before anything else is going to happen。

Another is that we have effectively unbounded recursion here。

And you might blow out the stack the worst cases is you have a linked list that's the size of the whole heap。

free the thing， each call decrements and calls free for the next then you're having one stack frame or object in the allocation。

 which is obviously not a good place to be。There is。

Some mitigation for that it's not really a solution。

 but I would say I should have put mitigation really here。

 which is that instead of doing all of this all at once。

 you basically push the free operation onto a thing that you're going to free later and you go back to processing because you can take as long as you like free things。

And you've used this list to maintain which things you're going to free rather than using recursion to do that。

 and so in the worst case you're damn now to a word of overhead to put a list item。

 but it's still unfortunately not really a good solution， a good general solution。最新。Yeah。

But the biggest downside of this whole thing is cycles。

On that first picture I had a cycle of three two objects with something referenced from the cycle and I couldn't claimclaim all of them because the reference camps didn't fall to zero and they'll never will。

 they'll just stick up one or more。For eternacy and so in some systems you can live with that。

 for example， there are languages in which is' impossible to create cycles in armor you won't create a cycle it's all just nested array。

 you can't make cycles so you don't have to worry about that but in general cycles are common in most languages and or。

Easily implemented in a program that common in practice， but they're easily implemented。

 and you've got to deal with them somehow。 So reference counting isn't adequate。

You have to have some kind of a backup scheme that's going to deal with it the easiest thing is to have a separate tracing collector and we'll look at collection next week。

 there are schemes which do incremental cycle dissection in reference cancer systems but they're basically variants of tracing collection run on small sections of the graph and you basically run a trial deletion if I were to delete this pointer which stuff go away and if it does then you're good and you found something but it's basically tracing and we'll look at tracing in detail next week so that is the end for。

Today with the exception of， well， you said the exercise already， or I have some reading。あん。

I don't think I have a slide for it， so there is a paper mentioned in the bibliography and I'll send out an email on Piazza。

To read a Dave Bungga paper on generation scavenging， which is an advanced。

GC technique and next week we'll have Dave via Skype to ask him questions about that and anything else related to sell if their programming languages or virtual change。

The auditorium， will be in the auditorium。昨年万。Okay。T are due today， compiler due next week。

one last question could show hands， which is we about a third of the way through？


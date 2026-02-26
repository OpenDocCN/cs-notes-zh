# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P15：-15-COMP6771 21T2 - 7.1 - Templates Intro.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Hello， good evening， everyone。😊，Nice to see all your well。 I don't really see your faces， but。

 you know， nice to， nice to chat to you anyway after what was no doubt a fairly just turning the mic up。

😊，Well was no doubt， like a fairly。Stressful time this morning for those who were around for the UNSW power outage。

 whether you were at UNSW or whether you were just you know trying to use UNSW resources。 sorry。

 I guess for any stress that was caused there， I wasn't particularly responsible for the outage。

I assume everyone who's kind of watching this lectures either watching it after the assignments due or alternatively。

 they're already aware about the extension， but we did extend the assignment to 2 pm on Tuesday。

That's a little bit of extra time for everyone。Should take the pressure off a little bit。

I guess I do want to apologize in advance for， you know。

 the problem with outages like this is that it， it inevitably means that some students who。

Did they doing the assignment on VLb or through the VS code server or something that's like not local？

Technically， it's like， you kind of， you know， lose a little bit because。

Other people could work on it for a few hours today， you know。

 And I know that doesn't really make any massive difference。 But， you know， I don't。

 I don't love things that don't feel fair sometimes。 So， sorry about that。 you know。

 it's one of those life things。 But we kind of get on with it。



![](img/4593240dd453c0786024802f0f9d9ea0_1.png)

But yeah。Today， we're pretty much just going start a new。Kind of round of content。Which is。

Here where we're going to sew there's a bunch of topics over the next four weeks。

 which are essentially all about templates and iterators。

 And then there's some more advanced topics around C plus plus types and stuff and。Essentially。

This is all about assignment 3。 We're really we're really tying together the last parts of C plus plus that we teach in this course and most of it falls around an idea of polymorphism in relation to classes。

 often not always classes and also a little bit of。You know。I， iterators。

 So now like this one we'll talk about on tomorrow night， that's like iterators。

 you're all kind of familiar with STL iterators and that's why we talk about actually making your own but。



![](img/4593240dd453c0786024802f0f9d9ea0_3.png)

Today we're going to be talking about templates or C++ templates。Super interesting。

 This is one of my favourite topics。 I don't know why I couldn't give you a good reason why it's one of my favourite topics。

 It just is one of my favourite topics。 I think it's just kind of interesting， personally。😊。



![](img/4593240dd453c0786024802f0f9d9ea0_5.png)

But。This topic about templates is all about understanding what we call compile time polymorphism or static polymorphism and templates are something that you probably have a vague idea about because of know maybe working with a language like Java or something where you have like an array list or a linked list。

We're going to get into some more detail and learn more importantly about how this works with C++ or how it works with the language like C++ So。

We're going to be talking about templates， non type parameters， exclusion exclusion principles。

 classes statics and friends all in the context of templates as well。😊，So first thing， polymorphism。

 you might have heard this word in another course， what does polymorphism mean。

 Well polymorphism is providing a single interface to entities of different types you often this is talked about when it comes to classes if I use like a Java example here。



![](img/4593240dd453c0786024802f0f9d9ea0_7.png)

Where you say something in Java， like， if you say have a。Say you have a class like an animal。

 like you have an animal class in Java， and then you have another class that's like say dog that extends animal。

And you have another cloth like a cat that extends animal。In Java。

 we would say that you could do something like An D equals new dog like this。

 and animal C equals new cat。And you could kind of， you know。

 use polymorphism to allow you to refer to these subtypes as like a supertype。

 And the idea here is that you have these multiple types like animals。

 cats and dogs that you can interact with via a common interface， which in this case。

 is the interface of animal。 So again， you know that if animal has a。You know， a public。

Public function that returns a string called get name。And it could just return hello like this。

Then you can call D dot hellello and sorry D dot get name and C dot get name because it's using any common interface。

 So that's that's all polymorphism really is because it's meant to be assumed knowledge according to the CSE programs。

 we don't really need to go into that in in excessive depth， but。



![](img/4593240dd453c0786024802f0f9d9ea0_9.png)

What is an important distinction that's very different with C plus+ is that in C plus+ there are two types of polymorphism we're focused on。

 One is called static polymorphism and the other one is called dynamic polymorphism now static polymorphism means that it is polymorphic at compile time static means a compile time if you're statically analyzing your code。

 you're doing it before it compiles， if you're dynamically analyzing your code it's happening while the program is running So dynamic polymorphism is a kind of polymorphic thing where it's happening as your program runs and that's actually what's happening in Java most of the time。

 So if you've done a course that like if you've learn a language like Python or Java which are probably the two most likely object classbased languages that have polymorphism that you've likely dealt with then often you have probably dealt with dynamic polymorphism in the case of Python it's because Pythons a runtime in the case of Java it's because it it does its polymorphism at runtime。

Even though it is a compiled language。Static polymorphism。All that means is that we。

Resolve the common interface that compile time， because my point here in this other example is that we have this code。



![](img/4593240dd453c0786024802f0f9d9ea0_11.png)

And when you say， you know， animal D equals new dog and then you say D dot， get name。

How does this code figure out what function to call because D？Is of type animal。

But it kind of points to a dog。So it's like how does it do all that figuring out what it should call how does it deal with that polymorphism and the point is it deals with that as the programs running so it deals with that at runtime C plus+ it can deal with it at runtime and it can deal with it at compile time and the first part of this lecture templates is dealing with it at compile time and it's basically a form of function overloading this all falls into a broader bucket of what we call generic programming。



![](img/4593240dd453c0786024802f0f9d9ea0_13.png)

Which is just about generalizing software components。 And， in fact。

 you've been dealing with templates since the start of the course because。

That's exactly what all these types you've been using are， like S TL containers。

They're all just classes。That you say， I have a vector of ints。 I have a list of strings。

 I have an unordered set of ints and doubles like。These are all templates。

 that's all static polymorphism。😊，What we're talking about now is actually making those ourselves。

 So before we get into class templates， which is really the bulk where this is it's really important to understand this idea of static polymorphism。

😊，And essentially just like what it actually means in terms of compilation。Normally。

If you have a function like a min function that can take in two ins or two doubles and you want to have those two separate use cases where it takes in two ins or two doubles you would say create a function like this Auto min2 ins returns it in automin double returns a double Now you kind of have to do this in a way because if you want a function that returns the min of two doubles。

 you want it to return a double right and if you have a function that wants you know that let me let me load this up in V S code。



![](img/4593240dd453c0786024802f0f9d9ea0_15.png)

It'll be easier if I talk to the code。啊。Yep， here so。This here now， ideally。

 you could maybe just do this， right。We could have a program that does this。

 it's just a function takes into doubles and returns a double。 I could build it， I could run it。And。

Yeah， if I try and run it。Demo oh， forgot the build。So what happens when you do a flex week。

 I figured how to code。

![](img/4593240dd453c0786024802f0f9d9ea0_17.png)

Dmo 701， right？One and one。 Now in reality， this is returning as a double and it's just printing without the decimal point。

 but you know what happens if I don't want to return a double right I don't want that I don't want to do with floating point errors that I want to deal with like potentially larger data type。

 So if I want a case where like comparing to ins you know just gives me an int that's why I use function overloading function overloading fairly standard concept most languages we should get that hopefully。

Where things get slightly more tricky is when we start then looking at function templates。

 which is the next slide， looking at some of this funny syntax before we look at function templates though let's take this source code here I'll copy and paste it and we're going to open it up in a compiler Explorer。

 which is essentially where we can put in some C++。



![](img/4593240dd453c0786024802f0f9d9ea0_19.png)

![](img/4593240dd453c0786024802f0f9d9ea0_20.png)

And we can have a look at the essentially the assembly that it craps out right so like what's actually in the binary so you compile this to a binary。

 the binary is a you know basically an encoding of all these different assembly commands that are ready to be executed on an X86 machine so this is a binary ready to go on a X86 instruction set。

嗯。And you can see it's a， it's a fairly， you know， there's some real garbage here。

 but you can see the basics in terms of you got， youve got a function here。

 and you have another function here。And then you have a main function down here。

It looks really long and scary。You know， that's not the whole main function。

 That's the main function。 And that's like the program。 you know。

 some other interesting things here while like while we're exploring， just refreshing your memory。

 So you can see here that the actual hard coded string is actually stored there in the binary。😊。

So that's that's， that's basically where this is stored， right。 So again， you probably。

 if you haven't explored this in a while， it's like， where's that question of like。

 where is this string， I didn't mallic anything， Is it on the stack， Is it whatever， It's like， no。

 it's it's sitting here in the source code ready to go。 We got these two functions。

 Our min function for ins it。Does its return type I'm not a massive fan of assembly。

 we take our two arguments in。So in T and N P， then we。The the compare is like a if statement right。

 and we have some jumps and then， you know， it's essentially a conditional jump。

Depending on whether this condition is true， right， So that's the function。 you know。

 you can see it all here， like those lines are what's represented here。 really cool tall。

Fund to play around with for really simple programs then you can see a double one's kind of the same except it's got different commands。

 which is definitely due to you know double precision floating points so processes deal with floating points differently to integers so very separate functions and at compile time the compiler figures out which one call you can actually see here that we're first calling where is it。

We're calling min int， and then we're calling min double， right。

 So two separate function calls calling different things。This stuff here looks like。 yeah。

 you can see here's the operator output。Being called for ints。

So this is actually the assembly trying to call the integer operator output overload here and you can see the same thing happening for the string because it's trying to print out first the return of this function and then this so it tries to do the operator overload for an int then same for the string and you can see the same thing down here it's doing the operator overload for a double I believe。

And then an operator overload for the string once again， so fairly straightforward。Well。

 shouldn't say fairly straightforward。 It's like， you， you can kind of clearly see the steps here。

 There's， there's garbage and half of this doesn't make sense to me。 And to some of you。

 it makes perfect sense to most of you。Makes half or less sense and that's totally fine。

 you should remember enough of this from maybe some other courses to be like， yeah okay。

 assembly it's that thing that looks hard to read。

![](img/4593240dd453c0786024802f0f9d9ea0_22.png)

Now we can make our code even simpler。If we tried to。

Then function overloading by using function templates。

 and a function template is simply an instruction for the compiler to generate particular instances of a function that vary by type。

So instead of doing int min for ints， instead of doing auto min for ints and auto min for doubles。

I can actually say I want to do an auto min except I'm going to replace all my ints or doubles with a T。

 and then above my function I'm going to write template， type name T。Now。

 this template type name T above the function is sent to the compiler， this function。

Is a templated function。 It's a templated type。And there's going to be a wild card， a variable。

 a placeholder。In that function。That I will denote with the letter T。

So I'm creating a template and there's going to be a wild card type in there， T。

And then I give the definition， and it looks like a normal function。 It's just I use t as a type。

 instead of ins instead of doubles， it's just T。 T is the type I'm using here。



![](img/4593240dd453c0786024802f0f9d9ea0_24.png)

And then this program will one run perfectly fine as well。 so if I open my function template too。

And I try and build and run 702。It goes one and one so it figures out how to do this。 Now， again。

 this is a concept you might be familiar with from other languages where you know you can kind of take in a generic type and then you know in Java you could say。

 well if you know if the type is an in do this if the types are double do that but that's all dynamic polymorphism that's all stuff happening at run time and what I want to show you here that really emphasizes this point is let's go back to the compiler Explorr and let's have a look at this。

Peace occurred。And pay attention here to how we have our main function， sure。

Looks pretty similar to before。But we still have two separate min functions。

We still have a min function for ants and a min function for doubles。

So in the actual compiled binary。We have two separate functions， even though we only defined one。

 and this is where the difference between static and dynamic polymorphism really stands out because static polymorphism is saying we want to create many functions or many capabilities with the same interface at compile time。

Where his dynamic saying make one at compile time and figure it out later。

So when this code actually runs。😊，It doesn't run a templated function。

Right the C++ compiler turns this into two functions。

 it does what we call instantiates two different functions， so again。

 a templated function or a class is an instruction to the compiler as to what functions to generate。

So the compiler will generate two and it'll put it straight into source code here now why does it do that。

 Does someone want to give me a bright idea about why why that happens。

 why not just do what Python or Java do。It'll take 10 seconds for the YouTube to come back。

My throat hurts， and my water bottle was empty， better。My housemate was in the toilet。Very sad。

Matthew says with the compiler complain if we gave it a type T that doesn't have a less than operator。

 absolutely it would， because what the compiler is going to do is the compiler is going to basically take your type T。

Generate all the things that it needs。And then see if it's valid。 So if I say， for instance， some。

Tried to do this with a type。 What's a type that's not comparable。 sayy standard vector。

Say a standard a vector of ins with like one。And then two。So you see this one will fail to compile。

Because。You'll see the errors that you're kind of used to， beside not having hash included vector。

Yeah， a call of overloaded men standard vectors ambiguous it's like， where is it？OhYeah。

Maybe the compiler is not super clear， but it's like yeah， the problem is that it won't work because。

 you know it's all just types at the end of the day。嗯。So Jin says it'll be quicker this way。

 Pink Oomega says faststar Sush says resource management， Davanche says less code。

I don't know about resource management。 I think that's a good guess。

 I think the rest of the answers are。Probably accurate enough， I think the biggest one， though。

 is speed， She says it's quicker this way。Pink Oomega says it's faster， and the reason for that。

 it's very simple， it's because you aren't having to do a check at runtime。

Because what actually happens when you say， when you have a program and you say。

 I want to create a standard of vector of events。The compiler goes and generates an entire。

Funs like a class for a vector of ints， all baked in， ready to go。

 It's like a premade package for that particular type int。And that means when the program runs。

 it's just like look， create this class made that class。

 it's not like create this very broad generic class and then have to do some type checking and type conversions during runtime right it's basically less runtime checks and that's a big part of where performance comes from。

😊，Deep Boy in 1990 says， because it's safer， well it's also probably definitely safer in a type checking ability in a type checking sense because we always want to move things to compile time if we can right and moving our code to like a compile time type check here is absolutely going to give us some better certainties when it comes to safety because any type incompatatibilities will be known to us at compile time it won't be determined at runtime。

😊，So again， this performance boost comes from being able to。嗯。

Generate different instantiations of the same template because templates an instruction for the compiler to generate copies of functions so that when we run the program。

 it's just like call that function， no type checking needed， nothing needed。

 It's already ready to go for that particular type。



![](img/4593240dd453c0786024802f0f9d9ea0_26.png)

So it does create more code sometimes， which we'll talk about， but it's also faster。



![](img/4593240dd453c0786024802f0f9d9ea0_28.png)

Now I mentioned this before， but some very straightforward terminology。

Is that when we define a template like the min function。

The T is what we call a template type parameter。And the， the actual。Oh， sir。

The list of type names is what we call the temperate parameter list。

 So they're just two really helpful pieces of， I guess， language to use。 Sam says。

 will portability be another advantage of creating templates。

I think portability is an advantage of polymorphism in general， whether it's static or dynamic。

 because yes， it does allow you to reuse code essentially。

Richard says assuming this may impact the size of the compiled code。 so Richard's very correct there。

 So when you when you're using C plus plus templates。

 it will increase the size of the compile code because you're actually basically creating a function for every type that you use。

 So instead of just creating one like mono function。

 massive function that can handle any type we're now creating like two little ones really ready to go really fast and yeah it does have an impact because the size of your binary is going to be bigger and the compilation time would be finitely longer。

 I don't know how long I have no idea。

![](img/4593240dd453c0786024802f0f9d9ea0_30.png)

But， your binary is gonna be bigger， which most of the time won't matter。

 P people would often probably prefer bigger bin to。Slower code。 But， you know， that being said。

 there's lots of different applications。 You know， there's lots of scenarios where you might be running C plus plus on a。

 on， you know， high performance， low memory。You know。

Chip or something where you just don't have the kind of memory to store a giant binary or something like that。

 But generally speaking， it's not a massive concern in the majority of use cases。



![](img/4593240dd453c0786024802f0f9d9ea0_32.png)

Yeah， PGs， all that kind of low level fun， compend， Jale end kind of stuff。

So the next topic this is a bit of a weird little segue but it's kind of interesting just to get the syntax down of templates。

 so we saw in the previous example that you can use templates by saying template type name T。

And template specifies that this is this is an instruction to generate as many of these as you need。

 Tpe name T is the wild card that we use to know what to generate and。

We said before as well that this is called a template type parameter。

 that T is a template type parameter。 There's actually another type， another thing we can use here。

Which isn't just T。 so this is a template type parameter。

 and this is what we might call a template non type parameter。

Now the difference between a type parameter and a non type parameter is actually really simple and you can notice it pretty quickly。

 a type parameter says tight name and then a type like a T， a wild card， a variable if you will。

 for a type。This one here has a type。And then a name for that type。So again。

 it's kind of like this is the wild card here is actually a type。

 the wild card here is kind of a variable， like a value。

So that's why we call it a non type parameter because it's basically representing a value no。Here。

If I have a function that I want to find the minimum。In an array， right， like a STL array， say。

An STl array， so I pass in a con standard array。Sorry that the conson is wrong there。嗯。

So it should be standard of AT size cont A。And it's going to return me a type T。

 Now that makes sense if I have an array of type T so you know， I have an array of ins。

 then it's going to find me the min and return me a type T。 It's going to return me the smallest one。

 And yes， in this case， it's going to copy it out。 That's okay because we're probably going to be dealing with some pretty simple types like primitives like insel doubles。

And you can see that yeah， also C starfo loops。 Oh no， I'm gonna get hit。 Yes， that's right。Yeah。

 so you can also see here it's like we're looping through the array and we're keeping track of the minimum and if we find the minimum here。

 then we return the minimum。Very， very first year style function。Oops。

One thing that we've done here though， is we've actually encoded the size。嗯。Let me， let me。

 let me take this code and show you what it looks like。

 I I think I might be potentially confusing people in a sec。

 So if I take this code and I get rid of the non type parameter like this。



![](img/4593240dd453c0786024802f0f9d9ea0_34.png)

Then you can have a fine min function that takes an arrays of size  four， for instance， like this。

Okay， and let's say all of or yeah， all of our rays have to be of size 4 like that。

So now your function is ready。For any kind of array。Of some random type that's of size4。

So it's generic in the sense that it can be any array of size 4， any typed array of size 4。

 but it has to be size 4， so this code here would work if I try and run it。😊。



![](img/4593240dd453c0786024802f0f9d9ea0_36.png)

Okay， Min of x is1 min of。X is 1。1， so I found them in those two things。However。

 what happens if I want this to be more generic， What happens if I want this to work like this， Well。

 I could try and change that number from a 4 to a3， But now let look。

 let's look at what happens when I try and compile it。 I'm going to get an error。

 And the error here is saying there's no matching function call。 Now。

 this makes sense because think about how C plus plus works。

You make a function call and it looks for a function with the same name that takes in the same types。

 Now， even though an array int3 looks a lot like an array of T4， it's not。They're different types。

A standard array of int 3 is just different to a standard array of T 4 of int4。

 So the compiler here literally just says。Sorry， but I can't find a function for you here。

I don't know how to find a function where at the type of x is a parameter， it just doesn't exist。

So that's where we can use non type parameters， because I'm now gonna say， you know what。

 Let's use what yes before standard。 Let's go back。Standard size T size。

 I'm going to replace all my fours。With this variable size。

Except instead of size being an argument which would not make a lot of sense in the scenario。

 I'm going to actually say it's part of the template parameters。Very interesting。

 So it's kind of like these two are now wild cos。It's just this is a type and this is going to be a value。

Because that's how the array works right like when you create a standard array。

 the first one is a type， the second part is a value。😊，That's what I'm going to say there。 Now。

 this will compile again。And it will print out everything fine。Because it can match that type。

 So when I call fine min with X， it says， O， I have a standard array in 3， Does this satisfy this。

 this type here。 Yes， it does。 I can replace T with n， and I can replace size with3。Okay。

 a couple of questions， so Alex says can you do min equals a0 instead of t min equals a0。

 no because you need to give a type to any variable name。🤢，嗯。Yeah。

 you'd need to say to every name needs a type in C style languages。

Do you need to specify the wild card？Are you talking about when the function is called？嗯。Oh no。

 that's the same question。 No， you need to specify the wildca because every name needs a type。

 Pin says， so we can't do standard array T。Standard size tea。

So you you so the question is why you know， can we do that And the answer is no because that's just not how standard array works。

 So most of the time you've put something between those brackets。It's been a type。

 but not every STL container is like that。 In fact， you know。

 let's go have a look at like standard unordered set right So if we go look at standard unaudered set。

You can see here that it shows us that it is a templated class that takes in four things。

 it takes in a key。Oh， I ordered maps， or that's what I meant。This one takes in a key and a T。

 and then it can take in more stuff if you want。 So if you've worked with an unordered set before。

 which you probably have in assignment one， you know that you can give it two types。

RightSo that first two are types。 whereas as if you look at something like array。

 you have a look at these， notice that the first one's a type。



![](img/4593240dd453c0786024802f0f9d9ea0_38.png)

The second one， though， is basically a value of n。So N N is like a wild card here like。

' it's looking for a number， not a particular class type。

 so you can't do that just because this is looking for a value it's looking this is a non type parameter and this one's a type parameter because we've already got the type here you know。

嗯。Sus says， can we not write standard size T directly into the argument， So， yes。

 you could add a standard size T here。 You can say， all right， there's also like a size here。

 But the problem is the compiler， even if you specify the size here。

 still needs to know the size of your array。To actually have it as a valid parameter right。

 because every array has a fixed size。And it won't compile if it doesn't actually know that size。

 So yeah， you could pass in as an argument， sure。But。Yeah。

 it's like it just makes things a little bit more complicated。嗯。

Alex says what I meant was why can't you Oh， auto min。 I'm sorry。 I missed you before。 Alex is like。

 can we say this， I don't know。 Let's try it out。 What happens if we use auto instead of T。

Works fine。A little bit harder to read。 I think I think it's really good if you use template types to really specify。

Where you're using it， But that's just probably personal preference on my part。嗯。Dvanche says。

 can you type cast something with size。You can't type cast something with size。

 So I just want to go back to the slides here so。

![](img/4593240dd453c0786024802f0f9d9ea0_40.png)

The important thing to point out here is that type parameters are types。

 non type parameters are not types。Nonty parameterss are known types， with an unknown value。



![](img/4593240dd453c0786024802f0f9d9ea0_42.png)

So when you ask a question like。You know， can I type cast， Can I say。In know。呃。Auto J equals size4。

 That doesn't make any sense。 That's like saying auto J equals min for min is a value。

 size is of value。 A non type parameter is a known type with an unknown value。

 A type parameter is an unknown type。

![](img/4593240dd453c0786024802f0f9d9ea0_44.png)

So just very different there。Size is a value here， teaser type。 we're using size as a value。

 It's used as a value here。Its uses a value here， et cetera。So yeah， that's all quite important。

Why do we want to do this， Why would we want to put a non type parameter in there。

 Why would we not just hard code a bunch of different arrays？Well。

The reason here is kind of twofold right one is that this function now works with arrays of any size。

 so you know it's nice and nice and dynamic you can use a arrays of size5 with doubles like you can use any size or array basically the other thing that's good is that sometimes you can get these interesting speed ups in your program。

Because you've actually hard coded in those values at compile time。

You've actually made it so that inside this compiled function and we're not going to be able to see it here because the code' is probably too complex。

Inside our fineynmen of ints。Where would it be。Yeah， you can actually see this here。呃。

Where's that less than size part。I'm no expert at assembly。 Someone else can probably see it， but。嗯。

Yeah， I wouldn't feel confident。 I have a couple of guesses。

 but I wouldn't feel confident pointing out exactly what it is。

But essentially the point is that you're actually hard coding the value right into the function now so that at compile time it doesn't have to go and like you're not passing it in by a function call and putting it on the stack or whatever it's like。

 no it's actually baked into the actual assembly here。嗯。Pink Comomega says。

 can we have something like an unknown type an unknown value， no that doesn't really work。And。



![](img/4593240dd453c0786024802f0f9d9ea0_46.png)

Also， the other question was， would the course prefer team in or auto， doesn't really matter。

 not not too fastsst。

![](img/4593240dd453c0786024802f0f9d9ea0_48.png)

And yes， as I've just said before， when use like type parameters。

 like nontype parameters here or anything， we create an instantiation of this function in the assembly for every type of that。

 So if you have， if you have an inter with three elements an inter rate with four elements an inter with five elements。

 a double array with four elements， that's four separate functions that will be added to the binary after the C plus plus compilers done with it。

 the thing we need to be careful of here， of course。

 is how many instantiations are actually generated with this。 It's probably again。

 not a big issue because most of the time these days。

 the size of your binary is not a massive concern， compilation time is probably a bit of a concern。

 but generally this is only。😊，A problem when you are dealing with。Something of。

Like dealing with such a wide array of things， like literally if you're generating standard arrays with 1000 different sizes of 100 different types。

 like sure， now you're going to be adding 30000 functions to your binary。

 you'll probably notice that both in terms of file size and compilation time。

 but for a general day to day purposes。Most of the time， you're。

Tempated functions or classes are not going to have that big an impact。

 So it's something you need to be aware of that it does make your binary bigger。

 but it's not something you need to stress about。Okay。Clas templates。 Let me just see。

How we going go with this topic。Okay。So class templates。I throw it's starting to kill me。

Most of the time that we deal with templates in this course is actually going to be dealing with them as classes。

Very rarely do you actually want to use templates for functions And in fact。

 a lot of the time and I don't think you'll even come across these much in the course。



![](img/4593240dd453c0786024802f0f9d9ea0_50.png)

嗯。You don't even need。Templates to like do this ever since C plus plus 11。

 I think you can pretty much just use auto here。 So this also works fine。

 So auto really changed the motivation for this for function Ts we mainly show you function templates because they're an easy concept to understand functions are very simple comparatively。

 but generally speaking we don't you know just use auto for function templates or explicitly overload them if the behavior is not identical。

 you can use templates too， but the majority of the reason we talk about templates is for classes。

When we talk about dynamic and static polymorphism， it's all about class types。



![](img/4593240dd453c0786024802f0f9d9ea0_52.png)

And。They're more complex， and more importantly， they're much harder to overload than a function。

 A function is pretty easy。 You know， it's parameters， stuff， return。

Whereas classes have tons of members and methods and overloading them gets really complex。 So。

 for instance， here， if I wanted to have two stacks， make my own stack， standard stack， comp 6，7，7。

1 stack。 And I was to create an int stack and double stack。 That's a lot of administrative overhead。

To kind of have these two different types with like different。Tights in the data structure。这份。

So different types in the perimeter list， different return types， all this kind of different stuff。

So we want to use templates to try and generalize these， you know。

 really use generic programming here where we need it the most。This stack class makes sense， right。

 you've got public and a bunch of methods and you've got private， which stores your actual data。

 but how would we actually go about making a class template and C plus plus well。



![](img/4593240dd453c0786024802f0f9d9ea0_54.png)

I should have an example here。

![](img/4593240dd453c0786024802f0f9d9ea0_56.png)

So the way we go about making a class template in C++ is pretty similar to making a normal class。

 you're just going to see the variable T around here。

 I'm going to come back to what's happening here and towards the end but for now I'm just going to put this here。

This is a templated class and and this is kind of the beginning of stuff that will become a fairly relevant part of your life for the next few weeks。

 but it looks like a normal class it says class stack， it has public， it has private。

But we put a template type name T at the top。 so remember template again is saying， okay， compiler。

 what you're about to see is Table and it's an instruction that you can generate many of these if you want to and then type name T is saying one of the parameters that we're templating this type across is a type called T It's an unknown type。

With no value， T。And then we have a bunch of functions。

 Now most of this also should hopefully click in terms of okay。

 instead of having a standard vector of ints or a standard vector of doubles。

 I'm now just going to have a standard vector of T。 And instead of saying， okay。

 I'm going to push int or double to my stack， I'm just going to push T and instead of saying my top is going to return a reference to int or double say T reference to T Sam from my overloads。

 this is a cons qualified thing。 So we have like a cont overload and a nonconst overload for top。

And then I have an output operator that of taking instead of printing out。Actually， this one's fine。

 This one doesn't need the template because it。It is used as a full loop。So， there's nothing。

You don't actually use it。A girl。Why I so tired。 You're not actually using the intel the double here。

 You're just using like。You know， the cap is figuring that out for you is the point。So。

These are just declarations。 This one's a definition。

 but I've got five declarations of these class member functions here。 I need to implement them。

 so when I go to implement them。Things look fairly similar。In the sense that I say you know。

 auto push and then I give all my function stuff and I give it detail。

 but the two main things you'll notice are that I have to put template type name T above every single function defined out of the scope。

And I， as usual have to put in my stack class scope specifier here to give it scope。

Now I actually find putting the template type named tea part。

Fairly logical because you know that you can't just say。Auto push that。

Because the compiler won't know。Who like what's using that。 So you have to say。

 you have to say stack T。 Now， you already know that from assignment too。

 if you define things in like a CPP file separately。And similarly。

 because youve had to scope it with the stack scope， you also have to say template type name T。

Because T doesn't make sense here， like the compiler is not just going to figure out what T is。

Its a template， type name T or。sorryrry about the noise， template。

 type name T or whatever type you're dealing with。Is basically just going to be like。

Above any functional class that uses it。The easiest way I think about thinking of it is you put this template keyword above every single functional class。

Except you don't have to put it above the functions inside a class in general that you've templated。

 so try and think about putting it everywhere， but you can get away with it inside of this class like I don't need here to say template type name T。

And I don't need to say that because it already knows it's templated type name T because it's a member function of a class that's templated type name T。

😊，But this is the gist of this one。 I go through and I implement each function。



![](img/4593240dd453c0786024802f0f9d9ea0_58.png)

Pretty， pretty okay， I think。And then we could use that， too， if we want to。



![](img/4593240dd453c0786024802f0f9d9ea0_60.png)

Yeah， let's try and use that quickly。I've got myself a stack here。It's templated。On a type T。

 And then if I want to use that stack。I simply say， okay。

 well I'm going to hash include my library and then I have an int main function。

I'm going to create a stack and in stack called S1。 I'm going to push two things to S1。

 I'm going to create a stack called S2， which is copy constructed。 I'm going to print out S1 and S2。

 I'll pop it， I'll push it， I'll print out S1 and S2。

 I'll create another stack of strings and then I'll push to that stack。

 so let's see if this one compiles。So this one does compile and the reason it compiles right is because it's pulling the separate。

嗯。TemplatesNow how many templates are instantiated here inside the compile code？RightThe answer is2。

 there are two templates that are instantiateated， one for int and one for string， So again。

 that you have to reflect the way that the compiler works here is that the templated functions or templated classes are not actual things to put in the binary。

 they are information for the compiler to put things in the binary。

 and just to go back to another our earlier example to really drive this point home。



![](img/4593240dd453c0786024802f0f9d9ea0_62.png)

![](img/4593240dd453c0786024802f0f9d9ea0_63.png)

If you have a look at code like this。We generate a min function for every type that uses it。

 so if I make another call to a min function that tries to say do A and B， the string。

And then does another one that's trying to do A And B。 the character like this。

 Have a look how many we create， we create。A min for， A min for doubles， A min for char。Con stars。

 which is strings and an wind for charts。 So we generate  four here。 Watch what happens， though。

 if I。Just say。Standards say out high。The program does not generate any min functions。

 So the compile， there is no min functions in this binary。 It doesn't exist。 Now， yes。

Optimiseizers will probably not include this function in the binary if you had those flags on because it'll be like that's a pointless function。

But here， even without optimization， it's not going to include it because it had no instances of that template to create。

RightIt's like a templates and instruction ready to go。 We didn't use it。

 so none of them were instantiated as opposed to four previously。



![](img/4593240dd453c0786024802f0f9d9ea0_65.png)

So in this case here we generated or we instantiateated two， one for int and one for string。

 and if we had another stack of vectors of doubles， we would generate a third one and so forth。嗯。嗯。

Now。The point of this slide here。😡，Is mainly just to show you that。

This is how you would have templated functions that take in or return other。 sorry。

 This is how you'd have templated。Template classes member functions。In this case， the， you know。

 rule of five constructors。Copy constructors move constructors， copy assignment。

 move assignment and destructor， this is how you would have them deal with other templated stack classes。

 so you can see here that for the copy constructor， you know the copy constructor is called stack。

It's inside the scope stack T， and it takes in a constant stack T reference to S。

And then it constructs it， you know， so the point here is like this is slides just a really useful reference for anyone who needs to get the head around like oh。

 how does copy construction and that workca the thing about templates is the part that always screws people up and even me is like where do you put the tea？

😊。

![](img/4593240dd453c0786024802f0f9d9ea0_67.png)

You know， I say you have a piece of code like this。

It can get really confusing really quick'cause you'， you know， you'll， sorry， one second。

 Let me just get this。

![](img/4593240dd453c0786024802f0f9d9ea0_69.png)

![](img/4593240dd453c0786024802f0f9d9ea0_70.png)

quick， quick， quick。Yeah， so you look at something like this and you'll be like， do I put a T here？😊。

You know， like how do I， why do I put a tea after that stack in this stack， but not this stack。

You get used to that one pretty quickly。Generally speaking。References to types require the T。 Like。

 what do you notice about these different stacks， Like we have five stack references in this line of code。

 Well， these two stack Ts are classes。 They are types。 This stack is a function name。

 and these two stacks are obviously a private data member。 Similarlyly here， this is a class。

 This is， it's a type。 It's saying return a reference to this type。嗯。This here is also a type。

 it's a scope， right， Scs and types is a classco。This here is also a type。These are data members。

 So generally speaking， if， if you're dealing with a type， then that's when you need the template。

Cool， are there any questions about this so far， we're going to take a five minute break。



![](img/4593240dd453c0786024802f0f9d9ea0_72.png)

Then need to drink some water， and then we'll keep talking more about templates and just lots of different things about it。

Shouldn't shouldnn't take the whole two hours， hopefully， but yeah。

 any questions about templates can do do some questions before the break。Maybe you're all dead。

Matthew says， is there a difference in binaries for templated functions and auto functions， No。

 there's not。 So they're all just instructions for the compiler to generator function and there's no difference between them。

 I don't think you you wouldn't be able to。To。Okay so。In the examples I gave， no。

 there is no difference。

![](img/4593240dd453c0786024802f0f9d9ea0_74.png)

In other examples。So。Let me show。 like， so if we， if we do this， I'll。

 I'll probably try and demonstrate this。 So if we do this and I replace these two auto with T。

Or sorry， auto， sorry。 If I do this， this code will compile。Okay。嗯。

One thing you have to be careful about in using autos is that autos if let's let's say like watch this if I try and say let's tell the difference between an in and a double。

 So if I try and find the min between one， an integer and two a double。

 then what we'll end up with here is a compilation error because basically it's trying to deduce a type of T here。

 but it can't because it's like sorry you're trying to call a function with two separate types， but。

I found a candidate function。It's just that it only takes in one type。

 The one difference you have to be thoughtful of with auto is that auto will allow things to compile in certain circumstances like this one。

 I believe， not this one。Oh， wait， no， sorry， let me get rid of that。 Maybe I think it's this one。

 I'm pretty sure this one works fine。Yeah， it does。

 So you can see this one actually compiles because auto was able auto is kind of resolved on a per argument basis or per parameter basis in this case。

 There's no way to kind of at least that I know of。Specifically， be like。Yes， let's。

 let's say that this certain auto， these two autos have to be the same type。

 And Nathan' ping in the chat at the moment。 I assume that he's probably maybe I can be one step ahead。

 but I don't know。 But essentially， the second one we've just written。 Yeah， that's good。 Now。

 I don't have to。 This is what I wanted to write。 But now I don't have to think about it。

It's basically the equivalent of。This。Except the return type， I guess you could leave as auto。Yeah。

 it it's like kind of like the equivalent of this。 It's like saying I've got these two wild card types that should be deduced at compile time。

 but they're separate。 So in this case here， if you just had this as well as a template。

 this would be able to compile with two separate types there。

 But this this assumes that the two types have to be comparable too right because remember like everything in C plus passages bootstrapped on top of each other。

 So if I try and say what's the minimum of one and Hayden。

 it's going to be a compile error because even though it'll find a candidate function。

That the parameters type match in。The problem is it won't be able to actually build it。

Because it can't compare A and B。 And you'll probably be able to see this here。 Yeah。

 comparison between pointer and integer， it has no ability to overload those two things。

it has no like relational operator that it can apply to those two separate types。

Generally we shy away from macros and C++ just because there's so many powerful things that can be used。

嗯。Aan says can't we use another name for the different entities。

 like why are we using stacks for all of them？I'm not too too short you mean。

By a name for the different entities。The point with the stack is that it's it's the same。

 It's a container of elements that。Ass can be made up of anything。Um。

Typically you use templates where。😡，The the type is somewhat irrelevant in， or at least it's。

 it's largely acceptable。 So there's a reason like a vector is a templated class because you can have a vector of literally any type because it's not really operating。

On。Like a type， right， like a vector is not doing much。With your type。It doesn't really care。

 It could be an in。 It could be a super。 It could be Euclidean vector。 It could be a vector of。Yeah。

 you could indirect this。It， doesn't really matter。 So that's， that's most often when you find。

Tempated class types。 Anyway， let's， let's take a5。

10 minute break and we we will get keep going and start moving into inclusion exclusion principle next。

 So yeah， let's take a short break。

![](img/4593240dd453c0786024802f0f9d9ea0_76.png)

From the break。I thought I nearly thought I nearly forgot to fill up my water bottle thus defeating the point of the break。

Okay， well。Either you're all tired or this is all making sense so far。Hope it's the latter。Templates。

Sure。I get it， we get it。 It's kind of whatever， but one thing you might have noticed in the previous slide was that at the bottom of the dot H file。

 the class temp main dot H file。

![](img/4593240dd453c0786024802f0f9d9ea0_78.png)

There was this little line here that said hash include demo 705 Class temp dot TPP。 and then right。

 it was。Used right here， right， That's where I included it。

 So it was basically just not a C file now。Conceptually。This is just an extension。Of a dot H file。

 like imagine it's like dot H file main and then it's like a subpart that I've just like pasted in because remember in C。

 hash includes our literal copy and paste pre compileile so。



![](img/4593240dd453c0786024802f0f9d9ea0_80.png)

Why did we do that？ Well， for the sake of the the demo。

 I just copied and pasted them in so we could see them in the same spot， but。Watch what like。

 let's have a look at what happens if I try and separate that out。 So because of assignment to。

 at this stage in the course， you should be familiar with， okay。

 I've got a main function or a test function that's actually。Executing。

 I've got my HPP or my H file that's the library， and then I have my CPP file that's attached to the library and I compile those two CPP files together。

Now， why do we like， well， we do that to help。We do that to speed up compilation。

 We do that to help separate things out， but we struggle a bit with that when it comes to。U。Temps。

 and， and I'll show you why， right， Let's I might even just use G plus plus for this'cause it'll be a bit easier。

 So let me just make a random folder inside of week 7 lectures。 I'll call it。



![](img/4593240dd453c0786024802f0f9d9ea0_82.png)

Inclusion for like inclusion， exclusion principle。 And then let's make a few files in here。

 So first file I'm gonna make is I'll make Min dot CPP， main dot CP，P， and。



![](img/4593240dd453c0786024802f0f9d9ea0_84.png)

![](img/4593240dd453c0786024802f0f9d9ea0_85.png)

Yep， so I got Min dot CPP。

![](img/4593240dd453c0786024802f0f9d9ea0_87.png)

うんうん没。All right， well let's get that in， so Min dotcPs are really simple。



![](img/4593240dd453c0786024802f0f9d9ea0_89.png)

Program， let's make another one。Alright， B S code。I'm pretty sure they can hear me。

 not that me telling you that helps， sorry。Someone will tell you that they can hear me。

 I don't think anyone one's had been listening to me for three or four minutes。

 without saying anything。And then I have Min dot H， right， So I've got these three files now。

These make sense。 I will need to hash include。Min dot H here like this。

 and I will need toh include it inside my Min dot CPP。 So again。

 this is the model that you might have been following when it comes to assignment too。

 Does someone tell me， is that columns？ How do I great， Can I do another one。Perfect。Oh。

 that's the same file。 That's not what I want。 Okay， Min dot CPP。 So here's our three files， right。

 I got my dot H that just as a prototype。 and then I do a definition in my CPP。 and I do a。

My executable main function in another CPP。 Now， it doesn't matter if this is classes or functions。

 It could be the same thing。 The same rules apply here。 Here's the problem。

 When I go to compile this。 If I go into lectures， lectures 7 and I go into inclusion down here and then I go G plus plus I know the text is really small。

If I go G++ dash O inclusion， and then I give it the two files， mean。cppP and Min。cppP。😊。

So how you compile things， and I run it。We get an error。Which I think is the error we expect。Yes。

 okay， which is undefined reference to int min int int int。Now。

 what this is saying is that when it tried to compile the main function as part of mainine docP。

It failed to find a definition。For the min function。Now。

The critical thing to kind of understanding here is that a template declaration。

 just like saying Min T AB， is in itself not an instruction it doesn't mean anything because the compiler actually needs to know at compile time what the definition is and I think some of this is written in the slides here。

 so when it comes to templates， we need definitions included at compile time。



![](img/4593240dd453c0786024802f0f9d9ea0_91.png)

Okay。

![](img/4593240dd453c0786024802f0f9d9ea0_93.png)

They can't be instantiated at link time。Now， if you've forgotten the kind of classic model of like。

 you know， computing or whatever。And I just， you know， say I'd comment these out for a second。

 I think this is really important to drive home。 If I create a mint min function like inte in B。

 like this。 Okay， and then I'm going to create a。Definition of that min function， int min and int A。

 int B。That simply just does what does it return， A less than B， A。B like that。

 And then I call min here like that。 I don't， I don't need a template because it'll look for a min。

 It'll find that match for me there。 Now， this will compile。No， why't。

 because I didn't compile it properly。 What didn't I save， Did I did not save these filess。

It will compile right because what does the compiler do。

 it compiles Min dotcP and Min docP separately。😡，And all a compiler needs to compile a function is just the declaration。

 It just needs to know what's the return type， What are the parameters。

 And that's enough for it to say， okay， I get how it works。

 I will link the definition up later I can because every file is kind of compiled in a vacuum and then linked up later The problem is when it comes to templates we don't really have that luxury。

 it's just not really how the compiler works。 So when I say for instance。

 here that I have a min12 and it includes min dot H。

 which remember for a compilation reasons is basically CPP that main dot CPP gets compiled by basically copying that in。

RightSo this is the file that has to compile in a vacuum。

 But the problem is the compiler will not instantiate。Templates into functions。

 It will not kind of generate all these functions unless it knows the definition。

 it needs to know these definitions of compile time。 So this here won't work。

Like this won't work here， but if I was to say， put the definition in there， this will work。 In fact。

 I don't need the Min dot CPP anymore。

![](img/4593240dd453c0786024802f0f9d9ea0_95.png)

Right so the whole point is that you need the definition of templates at compile time。And it's again。

 I'm stressing， I'm separating here compile time and link time because they are two separate things。

The downside of this is that we have to expose implementation details in the dot H file Now you can put it all inside the class body。

 you could put it at the end of the class body like we did in this example here。

 how we kind of made a class body and then instead of putting it in a separate CPP。

 we just put it right at the bottom。

![](img/4593240dd453c0786024802f0f9d9ea0_97.png)

![](img/4593240dd453c0786024802f0f9d9ea0_98.png)

嗯。😊，You know， that's totally fine。The one thing that this does do is it does slow down compilation。

Because if you have， say 10 different， imagine you have 10 different CPP files， right。

 and they all use a min function of ins。Remember， I said every file compiles in a vacuum and then is linked back together。

 so if you have your entire definition。I'm going sneze， I'm sorry。不。Wof。

If you have your entire definition inside of the dot H file and that's included into every 10 of your CPP files。

 and then they're all compiled separately， you're essentially asking the compile to instantiate the same function 10 different times。

 so there is a compile time performance overhead to this。

RightThat's that's the important line to stress。 This doesnt make your program slower。

 has nothing to do with like nothing we've talked about today。D like， well。

Templates make your programs run faster than if you were to use dynamic polymorphism。

 but like generally speaking， your programs like don't run slower by because templates exist as opposed to defining things separately。

 It all runs the same in the end。 It's all just about how fast does it compile and how easy it is to read and write the code。

 So because of that。We have to put out all of our definitions in the dot H file Okay so you've learn kind of an understanding about you know classes and like a dot H a docP from assignment to。

 you just have to understand if you're dealing with templates。

 you need to put those definitions inside the dot H file you can still do things outside of the class This isn't about whether you put a definition in a class or out of a class it's literally about file you put it in。

Another way to do things which we don't really recommend is called。



![](img/4593240dd453c0786024802f0f9d9ea0_100.png)

嗯。Explicit instantiations。Or what。I mean， I don't even want to really demo this to be honest。

 This has been in for a while。 And this has been in for a long time。

 And we've kind of mused about getting rid of them， but。Essentially。

 you might run into this as instances where if people really do want to keep the。

The the definition separate， then you can you can essentially force the compiler to be like， hey。

 this is definitely the template you should create because there's a whole topic that we haven't really kind of chatted about。

 which I think we chat about at the end， which is like how does the compiler even know which ones to generate？

Like the compiler just looks at this here and it just figures it out。

 it just figures out where the type is。And just goes and。Creates a， you know， instance of type ins。

 And， and just to really drag this， this topic on， it's like a question you should really ask yourself is like。

 well， you know how。

![](img/4593240dd453c0786024802f0f9d9ea0_102.png)

You know how vectors work， right， you have a vector。 So if I include vector。And I say auto vehicles。

 standard vector1 intz。1，2，3。 Well， what do you notice here， Well， in this case here。

 I have to specify that it's a type in。Right， I have to actually say this as an int for this to work。

 It's like， why I don't have to say this here。 Why don't have to say that it's an int int or an int。

 I guess， just int。Like， why do I not have to do that。 we'll kind of chat more about that later。

 But the compiler can deduce things sometimes right， Like the compiler is pretty smart。 It's like。

 well。HWhat should this be， Well， this is going to be the type of these two things。

 So I guess it's that。Anyway， the point of me mentioning that was just that。



![](img/4593240dd453c0786024802f0f9d9ea0_104.png)

Sometimes you can be explicit to the compiler and tell it what that is。

 but you largely don't need to worry about this slide。



![](img/4593240dd453c0786024802f0f9d9ea0_106.png)

This this is a technicality point here。I'll just answer this question。

 so Pson says since auto is kind of the same as template。

 will all autos also have to be defined in the same file？A。I don't know。

I feel like there's an easy answer to that。 my brain's not。 Yeah， Yeah， yeah。

 I so basically just to really make that。Question easier if we got rid of this。And we just said auto。

 auto auto here like that。嗯。This would need a definition to be able to work， I believe。



![](img/4593240dd453c0786024802f0f9d9ea0_108.png)

嗯。But generally speaking， it's like you don't have to worry about explicit instantsiation and you know putting in any things like this to explicitly say I need to instantsiate these。

 can you can just stick with what we've told you which is that your definitions need to end up be in the dot H file。



![](img/4593240dd453c0786024802f0f9d9ea0_110.png)

嗯。And I think just to stress so it's like since auto is kind of the same as templates。

 it's like the way I think about auto is like Autos are great。

 Auto is as far as Im concerned and Nathaniel might have some opinions if he's floating around the chat。

 but it's like auto is really a way to simplify your source code and remove benign or unnecessary typings。

😊，I wouldn't go so far as to be like， you know， auto and templates are the same thing。

 but different ways because templates are a way of essentially creating type wild cards where you can say like a class like this。

 where you can say， oh， well， I'm going to generically say that the stack。Has a。Variable type in it。

But I expect that type to be the same in here， here， here， here and here。

 Like if you just kind of lid auto throughout your code。

 you'd be making functions that could compile under a whole range of conditions。

 So there's more constraints you can apply through the use of templates because you're essentially saying this has these these。

My references of these types all have to be common。

 whereas auto is something that's resolved at an expression level。You know， there's， there's no。

 you can't establish as much structure with it。 So auto is very useful a lot more in like a function sense。

 And as we've said before， you you don't really use templates。In the context of functions。

 we just encourage you to use auto or function overloading because they're quite simple。

 typicallyyp the main use case for templates is is classes。

 which you would struggle use auto in generally。 So one of the last kind of technicality points of inclusion。

Did I say inclusion exclusion principle？What in the hell have Ive been talking about， I'm sorry。

What is that。I feel like I learnt that and then suppressed it。

 And then I've just started saying it today，啊。I didn't bury discrete maths deep enough inside my brain。

 Apparently， I'm really sorry for anyone who's outpt to listen to me say that that's terrible。 When。

 if I've said inclusion exclusion principle， I've meant inclusion compilation model。

I'm sorry about that。

![](img/4593240dd453c0786024802f0f9d9ea0_112.png)

That's quite funny。 I just went to read the title again and was like， oh。What？

So the last thing about the inclusion compilation model beyond all the other things we've talked about is that there's this notion of lazy instantstaniation。

 which。Essentially says only member functions that are called。嗯。

When a function is used are instantiateated。 So what this means is like， okay。

 so you have a function template。A function template for men。 When someone says min of int。

 it goes oh， I'll generate  one for you up there。 And when someone says min of double， it goes up。

 I'll generate a second function up there。 That's really simple because functions are just a thing。

 right， A functions is just a unit of the thing。 But a class is more complicated because a class is a。

Big box that has a series of function definitions。 and then it has like some data members in it。

 right， So it's a big box of stuff。 And what， what lazy instantiation rules say is that。

When I create this box for a class， you know， like a stack of events or a stack of doubles。

I won't go and create a function for everything。 I won't go and just create a constructor， pop。

 push and everything else。 I will only create what I see you use。So in this case here。

 we've got this like template for a stack say。And what's essentially being said here is that if someone comes along in a main function。



![](img/4593240dd453c0786024802f0f9d9ea0_114.png)

And as this。Right， stack into S。The compiler will look at this and it'll create an instance of this somewhere。

Right， it'll replace all of the T's with ints， right， So it sees all the T's。 and it goes up。

 that's an int and。That's an ant。And。You know， that's an int。 And like。

 this is literally what the compiler does。 It's like， yep， and that's an int。 And that's an int。

 Great。 And now I've got my class。MyMy concrete class， my instance you had a class， but now it says。

 hey， I can see that someone's only really using the constructor and push。

 so I'm not even going to bother up adding that pop function to the class。嗯。

We call it lazy because typically in computer science， right。

 lazy means that it doesn't do something unless it has to like by， by default。

 it tries not to act until it has a motivation to act。 And then it will act。 So in this case。

 what that's saying is that。It will only。You know， instantiateated it。Once it's。

 it can see someone's using it， it's not just gonna go and create all this stuff for fun。



![](img/4593240dd453c0786024802f0f9d9ea0_116.png)

What implications does this have。I have no idea to be perfectly honest with you。 Obviously。

 it's going to make the binary smaller somewhere like it's going to avoid unnecessary binary bloat。

 I know that's the technical reality of it。 I don't know if there's any real practical real world implications。

 I at least haven't been exposed to them personally。Pyn says。

 would this only apply to template classes or classes in general？

It only applies to template classes and the reason for that can be conceptualized pretty straightforward because with a normal class you go and actually give the definition here。



![](img/4593240dd453c0786024802f0f9d9ea0_118.png)

The compiler doesn't decide。What。The the compiler doesn't decide what this。Like does like， okay。

 so let's say this is a class。 Like let's call this like in。The compiler doesn't just say， oh。

 they're not using a function in their ins class。 Therefore， I will omit it。

 What's actually happening is you have a template up here。Right， like stack tea。And when you use it。

 like， you know， this might have three functions in it。 The compiler will say， oh。

 they're using that one， they're not using that one。 They are using that one。

 So when it goes to create。Right， when it goes to create a stack of ints。Like this。It says， well。

 I'm only going to create two。So my point is that it's not a compiler deciding what to ignore about a concrete class。

It's a compiler deciding which what it should build a concrete class with from a template。

 So the question of would this certainly apply to classes in general， no， it doesn't because。

The compiler， once it has a class， does not just decide what to include in the final binary， right。

 it includes everything。 The question is all about how much of it comes down from the template while it's creating it。



![](img/4593240dd453c0786024802f0f9d9ea0_120.png)

And just just for completeness。Nathaniel commented on my。

Comments earlier saying it's harder to spot bugs sometimes because if you have a typo in a function。

 but you don't test it， you won't know until later。 Yeah， so。Basically， it's like in this case here。

 if you have a typo or a bug or something inside the pop function。The。

 the compiler might just not bother instantiating it。 And therefore， it won't try to compile with it。

 And therefore， you may。you may miss bug。 So sometimes you might actually write code that you think worksca it compiles until you actually use it。

Which triggers the lazy instantsiation to actually add it to your concrete class。

 And then you get a compile error suddenly。 So I think that's a great tip。 Thanks， Nathaniel。Okay。

 what do we get left， Sta friends， constant expression， and that's it， so。



![](img/4593240dd453c0786024802f0f9d9ea0_122.png)

A couple of tidbits about how this plays out in other parts of code， so firstly。

 how do templates interact with static members？嗯。Static members。

 which you should know from week three， are members that belong to a class type。

 not to a particular object that's created of that class type。

The rules around templates and statics are really straightforward。

The idea is that each template instant staiation has its own set of static members。

 And this actually makes sense， because。There's one static member for a class per type。

 So if you have a class there's one there's a static member for that class。

 So you know you say nu stacks， if you have a stack or an in stack and you say nu stack is0。

 there's one variable called nu stack， nu stacks， and it's associated with your class。

If you have a template。For a stack。And that template creates four concrete classes。

 then you will have a static for each of those concrete classes。

 so you don't actually have to overthink this too much。

 You just say the same rules of static and classes apply。

 It's just that a template is able to create many different typed classes。You know sure。

 they're very similar， but they are。 they are unique types as far as the language and compilation is concerned。

 So for a program like the one we have down here。This， for instance。

 if I create a stack of floats and a stack of ints。In our overall program。

 we will have two static members called NM stackacks on two different types。

They're not on the same stack or anything。 Remember stack float and stack int are for all intents and purposes。

 totally different types。There's no real correlation between them in the actual like compilation model。

Insant doubles， ins and chas。 like， sure， conceptually， they might be similar， but， but。Literally。

 they're they're different。 So it is just two different static members。 There's nothing。 I mean。

 I could run this code for you。 We give it to you in the lectures repo， it just。

I think that's a little bit of。Well， let's actually see what this looks like in just'cause we have a tiny bit of time here。



![](img/4593240dd453c0786024802f0f9d9ea0_124.png)

Let's see what this looks like in the compile Explorer if I so I have a hash include for a dot H。

 I'm just going to paste that dot H in here。😊。

![](img/4593240dd453c0786024802f0f9d9ea0_126.png)

And let's have a look at this together。 Oh my head's in the weird spot。う。

So we have a main function here sure， it a whole it does a whole bunch of stuff。

You can see that we call a constructor for a stack of floats。

 we call a constructor for a stack of ints。嗯。You can see this one is called like once because it's like a default construction。

And then you can see we call some other things。 There' some destructors。 Oh。

 look some destructors are called。 really interesting， right， Like I mean。

 this is a fun thing to play around with。 You're like， oh cool。

 I can see that the function ends and it's starting to destruct everything for me。😊，By the way。

 we're creating three stack stacks events here just to be clear。

 sorry that's why we're popping off four oh， so there's four， there's four。😊，There's， oh no't。

 Let me stop。 We're creating four stacks，1，1， a stack of floats，3 a stack of ints。

 We end up with two static。Data members， because there's only two types we're working with。

 So all three stacks events， Is 1， I2 and I 3 all share。The same static member。

 because they're all the same type。If I scroll further down。

 you can actually see our stack of floats here。This is the constructor。This is the destructor。

 This is the constructor for a stack of ins。 This is the destructor for a stack of eventss。

 but what you'll also notice is because of lazy instantiation。

 none of these functions here have been generated。We used the constructor and destructor。

 even if we didn't define them， it would still generate them， right。

 because of the synthesized constructors and destructors， right， this would still generate them。 No。

 it wouldn't。 Why wouldn't it， What did I miss。Oh， I've got the definitions down here。

 Obviously we want these to be。 we want us custom define these so that the static thing works。

 but these are still generated otherwise， right， They're still generated for us。

But these aren't being used， but if I suddenly use one， like if I suddenly say FS。 push 5。0。

The compiler。Oops。What's wrong， Is the problem that this is a float？I just wound up push。

 takes a reference， oh。When it takes there's an interesting thing right， Like references are L value。

 So you actually can't pass an R value into this because like5 is not a refer like it's not an L value reference。

We're going to talk more about those next week and my brain's gonna hurt。

So you'll see here because I used to push， if I scroll further down， you'll actually see that。

We have。I scrolled past it， right。Wass the push function。They just miss it。Am I crazy？

Someone tell me I'm crazy。Oh， why did it compile then？W why didn't you give me a compile arrow。

That's weird。Oh， well。Yeah， but like we could， we could easily， I mean。

 the problem here is I didn't define it， right， Like Nathan's right。

 It's like we didn't define this here。 So I can just define it。

By copying and pasting that line and then implementing it。 And how would we implement it。

 Well we're using a vector underneath。 So I could say stack dot push。Ag， which should work。I guess。

Stack was not declared in the skull， right， the。cope your classes。

 scope your class functions outside of your class， everyone don't be like me。嗯。

And then push wants to take in a what's that， has no member named P。 Yes， it does。

Why is it so grumpy， Oh right。

![](img/4593240dd453c0786024802f0f9d9ea0_128.png)

Push back。 Thank you。Flex wake， everyone。 Yes， and hour to work。Should be here。Stack push。

 There it is。Yeah， so's that's an example of the lazy instantiation happening there。嗯。Got it。

 So just to recap， I'm pretty sure what Nathaniel is telling me is that。We。

 it was kind of compiling because it wasn't。Trying to actually build an executable yet。

 it was just compiling the file， is that what was happening？Oh yeah， okay。

 so we didn't have the compile to binary。Or something。 anyway， interesting tool。 I'm not an expert。嗯。

Just quickly moving on to our semi related topic， friendsend。 you are familiar with friends。Well。

 hyp most you。Because it was a topic of week four with the operator overloading and。

The rules for friends are very similar to the rules for statics。

 which is that each stack instantsiation has one unique instantiation of a friend。

 because what do we kind of learn about about friends is like a friend function。

Is kind of like a global in the scope of the class。 That's kind of how we talked about it。

 So there was one。Like friend function per class， not per like。Function inside the class。 So。

 you know you have member functions and member functions apply at an object level。

 and then you had friends which typically apply to the whole class like static。

 So it's a very similar concept here where if we have a friend like an operator output。

output stream operator overload， then how many of these function definitions do we have？Remember。

 this function is not part of an object。 It's kind of global in the stack。Scope words escape me。

 however， similar to statics。 We have an instance of this operator output stream for every single stack we instant instantate。

 So if we create a stack of ins and a stack of doubles and a stack of chas。

 we're going to have three different operators。In the source code。

 which which actually makes a lot of sense， right， Because you're gonna need an operator for each type of stack because。

 you know， the operator is， is basically an instruction of how do I deal with this specific type。

 And we can see the same thing here if I。

![](img/4593240dd453c0786024802f0f9d9ea0_130.png)

![](img/4593240dd453c0786024802f0f9d9ea0_131.png)

Copy and paste this in。So if we have our stack here， I didn't try and compile this in an advance。

I'm probably gonna have some problems。Push is wanting a。Oh nope。

 I misunderstood that I S was not declared in the scope。 Yes， it is。 It's right there。

Someone gets to point out all my mistakes for me tonight。Semi， it's not that's not the problem。

 though， is it？What's wrong with Yeah， like thanks on the semicolon。

Is was not declared in this declared in the scope。 Is that not the name of it。So strange。

NeTo zoom in on this。 I can't really see I'm looking at like a smaller window on my screen。 Oh， okay。

 there we go。 Thank you。wow， semicollons， bless。 So problem there just for context was that this semicolon was basically tanking the next line。

 So when we got to this line here， line 29 never actually got like。



![](img/4593240dd453c0786024802f0f9d9ea0_133.png)

Processed right， so。Let's got the semi Collins in。And as you can see here， right， same kind of thing。

There's an operator， less than overload。And how many of those are we going to create， Well。

 there's two instance， there's two times we're using a stack， one for a string， one for an int。

 So we should be able to see those as we go further down right， we have a stack here。 Okay。

 there's our two there's a first operator overload that takes in a output stream。

A reference to an output stream。 and it takes in a stack。Of int of string。

 This is a very long winded C plus plus way to describe a string。嗯。

But that's essentially saying a stack of strings。 And then we'll have another operator less than down here。

 That's like a reference to an output stream and a reference to a cont stack eventss。

 So a similar thing。Even if we create more stacks events， even if I create like another three instax。

 there's only two types of stack that are instantiated in our code from the template。And， therefore。

We only have two friends actually added to the binary。Any questions on that。

 just I pause for 20 seconds just to checkca then we'll talk about constant expression。

 This is a bit of a tack on the end of this lecture。Cool。Oh， really random topic。 And I think this。

 this just， this isn't critical earlier on in the course， but it just comes up here， I guess。

 because。We're talking a lot about like compile time and performance and stuff like this in this lecture。

 and。Basically， there's this topic。 There's this， there's this keyword you can use in C plus plus called a constant expression。

 and a constant expression is where。Just double checking。

 we can provide default arguments to template types。Where the defaults themselves are types。No。

 that' sorry， that's the wrong text。I'd moved some stuff around， and I missed this one， so。

I don't think that makes any sense。No， it doesn't。 That's a separate that's a separate thing we're going to talk about next week。

 So let's start here So constant expression basically constant expression is a keyword you use to instruct the compiler that there's a variable that can be calculated at compile time and a constant expression function is a function that if all inputs are known at compile time。

 it can be run at compile time。Now， philosophically。You have to think about for a second。In theory。

 the programs you write。Could be all calculated at compile time。If it wasn't for unknown inputs。

 right， if it wasn't for waiting to see what that fetch request on the network returns。

 if it wasn't waiting to see what the user input or what text is in that file。

 you know in the case of Euclidean vector， it's like well。

 you know what inputs am I going to get given in the case of word ladder it's like。

 what inputs am I going to get given， but if you have a program or a part of a program or even a function in a program。

That does not is not variable or is not conditional upon some kind of input unknown to you at compile time。

 then it can all be calculated at compile time， which makes sense right。

 because what's one of the quickest ways to make your program run faster， it is to。

Make it do more compile time。 This factorial example is an example of that， whereby。

What we're showing here is that。Forget the constant expression for a second。

 We'll talk about the keyword。 but it's like， if you have， say。

If you want to figure out the value of 10 factorial。

I'm in to call a function called constant expression factorial， which will simply you know。

 do the recursive factorial call of like you know， if n is less or equal to one than return1。

 otherwise return n times myself n-1 right if you're not familiar with factorial recursion。

 pause the video， go read on it for five minutes and come back。

 But fairly straightforward factorial recursion。 Now if I take this code。



![](img/4593240dd453c0786024802f0f9d9ea0_135.png)

![](img/4593240dd453c0786024802f0f9d9ea0_136.png)

And I'm gonna go back to the compiler Expr again。 And I， I cut out some of this stuff。

 So this might be what a。What like a simple。Program you work with might look like。

Something like this。And。How， you know， how this compiles is it's like， okay， well。

 I'm going to compile this。 And I'm going to， I'm going to create a factorial int function。

 It's going to take in an int。 And then I'm going do some， you know。

 moves and jumps and stuff because I'm， you know， recursive。 and I've got， I've got a。

Another call here。 So that's the recursive call to itself。 And then my main function here。

 basically just。Calls factorial with an int and it calls it with9， which it moved into the EDI。

 I can't remember what that stands， but what is EDI。It's like the， the thing that。

Pass it in by parameter or whatever。 So that's that's like， you know。

 that's kind of the programming model， right， like the computers， they set things up。

 they call it function， the function calls itself。 and the compiler turns the left hand side to the right hand side。

 which is a bunch of CPU instructions that are ready to execute this and calculate it。

 But think again， philosophically about this program。It the the answer is noable to us right now。

 we don't like we don't need to compile it and run it。 It's not waiting for an input。 Obviously。

 if we did something like we said， you know， In equals 0。 and then we said standard C N。

 read that into a。An I variable like that。 Now， this program can't be known at compile time because we don't have all the information we need。

To determine the answer。 So we have to go to runtime to figure it out。 But in this case here。

 we do have all the information。Now， if we have all the information and we want to tell the compile。

 we want to give the compiler instructions to basically say， hey。

 if if you can figure this out at compile time， then do it。

Then we can use the constant expression keyword Now I'm not an expert on this。

 so I apologize if I get a couple things wrong here， but it's like。

 let me just try one for a second if I say like into equals 3 and in b equals 4 and then I say in C equals A plus B and we have a look at how this compiles。

You can see that what the compiler does is it tries to translate the this is a non optimized code。

 So an optimizer might do something similar。 but like the non optimizeised code will take this and it'll try and translate it to the right here where it will literally。

You know。Say okay， well first I'm going to set a variable to be 3 and then I'm going to set another variable to be 4 and then I'm going to add them to and I'm going move them to some registers and then I'm going to add them together So the compiler's job is to actually translate the instructions in C code C++ code to assembly to run on X 36 and。

If I suddenly， though， put a constant expression， syntax evades me just before all these ints here。

 if I say constant expression。And equals 3。I will get the same result because the compiler will say。

 yeah， I can calculate that a equals 3 at compile time。D， we've already done that for them。

 If I put it in front of the B， the exact same thing happens here。Right， but once I put it。

It was actually done it already for me， but not with that one。Oh， no， okay， sorry。

 let me take a step back。This is really interesting because notice here， watch this like three here。

 So before。What happened was the compiler was like， I'll have to add these two registers together。

 okay。Yeah， and there's， there's there so much funky stuff happening here that even I don't understand。

 So I'm， I'm just trying to convey the concept to you in a more tangible way。

 But the details get very complicated。 But let me just put it in front of all three variables here。

 And what you'll notice is that have a look at what the compilers done here。 It's basically got your。

2 variables。 And it's like already added them in together。 So I just want to be clear。

 like this is not， this is now saying that during run time。Set the variable C to be the value 7。

It's not saying go calculate 3 plus 4 when you're on the program， right， It's saying no， no， C 7。

 You don't need to add anything。 you don't need to do any。

 You don't need to run anything through the processor C is 7， because the compiler Gcc。

Is able here to say， well I can figure that out for you now right now， why we're compiling。

 Let's do that together。 And that's what a constant expression variable is。

 And a constant expression function is the exact same thing。

 except if the function can figure out the value at compile time。 It'll do so。 So let's try this。

 And I'm just trying to reverse engineer this。 And。We will eventually。

 I'm I I can't remember the exact。 There we go。 Well， that's。

 that's the only place I had to put it here。 I just want to stress again。

 And Nathan's typing in the chat again。This's one of those things where like the details really play into it。

 like some。Some compilers with certain optimization flags will do this for you like it will try and make all of your inscont expression if it can。

 So like in a way， this is a little bit like constNormally remember how you said before that the compiler will make your variables const if it can because it can make optimizations with const。

 It's a similar thing here。 there are there are circumstances where the compiler will be able to。

Tell that something could be constant expression。 And if it's， if it's kind of。

 if it' behaviour set to optimize， then it will set that。 So by making this function up here。

 constant expression。In this particular instance of compilation， watch what happened。 Let me just。

 let me undo that。So notice here that the way this this main function worked is we called factorial online。

 we got the number nine and we called factorial。And then this we had a whole function here。

 But once I made this constant expression。It doesn't even create the factorial anymore in the binary。

It's gone。 And， in fact， that cold factorial is gone， and it's just given me the output。

 So if I was to run this program。This program's job is just to start。Print 362880， and then finish。

That's a massive optimization。 There's no， there's no recursive function calls。

 There's nothing like that。嗯。This is another form of compile time optimization。

 That's the short story。 So constant expression， you can apply it to functions。

 You can apply it to variables。 if the compiler is able。



![](img/4593240dd453c0786024802f0f9d9ea0_138.png)

To， if， if， what is it， if everything's known， if the inputs are known， Yeah。

 if the inputs are known at compile time， it'll be run at compile time， essentially。嗯。Yeah。It's。

 it's less applicable than you think， because you。Kind of the whole reason we have programs is for variable input。

 right， like if。If you can know a lot of things at compile time。

 you're probably solving the problem with Excel or Google sheetets or something like that。

 right So so don't don't think this is some magical secret。 It's like the majority of the time you。😊。

You know。You can't really apply this。But you can sometimes now Aan says。

 would it make compilation time longer， though， Yeah， definitely， well。

 you're just shifting computation to compile time。But often， that doesn't matter because often。Like。

Compile time is usually pretty okay to be slow。Like the impact of a slow run time is very broad。

 Like it， it can be user frustration。 It can be lost money。 like think about it， you know。

 think opttiva， right or high speed trading firms trying to。You know。Get things done quicker。

Like most things really want faster run time because it's kind of like， like。

 like if you think of a program， runtime time as like you being like programs like。

 here's the problem， Figureig it out there's a solution， right， And like that's。

 it's trying to solve a problem in a certain amount of time。 So if you can shorten that。

 the better in pretty much all scenarios。 yeah， it makes compilation longer， but it's like。

You can solve compilation by getting more powerful computers a lot of the time。

 You can do compilation offline， pretty much the only real downside of。Bloated compilation。

 in my opinion， as。呃。It's just painful for developers， right？嗯。That's， that's the main thing。But。

 but and you know， sometimes that's a real problem， but you know， in many cases， it's like。In。

 in cases where you're dealing with high performance stuff， you're。

 you probably wouldn't be too stressed about speeding up compilation slightly。

 Someone askeds what happens if the factor is really big。 Well， the I don't know G Cll be like。

 I can't do that just like your program。 if you say 5000s。



![](img/4593240dd453c0786024802f0f9d9ea0_140.png)

Complain。Oh。No， it doesn't。 Oh， that's smart。 I didn't even think of that。 That's a good question。

 I never asked myself that particular question。 Look at what it's done there， little。Cey thing。

So in this case with the number nine， it's basically just said。

 I can calculate it here you go and if I give it a number 15。It。doesnn't like big numbers。So， I mean。

 I guess， I guess the question here。Nathaniel。Because he might know Nathanthanielll love C plus plus he's just the best。

 So you can see that， you know， doing factorialula 12 and stuff did generate。

Did it or is it I'm lost。Yeah， it generated it for us。 but once we get bigger。

 it seems to rever it to a function call， is it。Yet， it reverts to a function call。Yeah， okay。 so。

 so the comment Nathaniel's made here is that， and I。

 I was wondering about this beforeca I didn't actually expect this to work。

Because normally with constant expression， you kind of need to put it everywhere like you kind of need to put it like here as well。

 like your functions need to be constant expression， your variables need to be constant expression。

 everything needs to be constant expression for it to work and the comment Nathaniel's made here is that when we didn't have this as constant expression before what we're basically saying to the compiler is that。

The compile is are allowed to make a constant expression if it wants to。But it doesn't have to。

By making this。Const expression。 We're now telling the compiler you have to meet this constant expression。

 in which case it has。嗯。Faaiil to compile。 And here， what is the said。

 expansion of factorial 5 overflow and constant expression。 So essentially， there's been。

 there's been an overflow on the stack because， you know。Recursive factorials are ridiculously。

Demanding on the stack。Well actually， I mean， no this's not， that's not even the case。

 It's not even a function call。 So I'm thinking of Fibonacci。

 It's like that number would just be ridiculously large。I would imagine。Cool。嗯。Great。

Well's let's wrap up there。 I think that was a fun little electrode。

 but that was a nice introduction into templates。 I don't know what I said on the notice。

 I said on a notice today that your assignment 3 is being released at 8 PM tonight。😊。



![](img/4593240dd453c0786024802f0f9d9ea0_142.png)

![](img/4593240dd453c0786024802f0f9d9ea0_143.png)

That means I I forgot to release it。 so I have to do that right after lecture。

 so you'll probably get it at like 830。 sorry about that。😊，You know， so。I'll really start soon。

 You don't have to look at it。 You got other things to worry about。

 but we'll talk more about iters tomorrow， which should honestly be most of what you need to start itca a lot of the assignment 3 is actually based on like smart pointers and。

Same stuff as assignment2 it's pretty similar to assignment2 just harder。

 but anyway let's let's wrap up there and I'll see you all tomorrow night and for those again in my tu I'm going to move it to Wednesday because I got a work meeting tomorrow that I can't move I'm sorry。

😊，But it's all recorded anyway so so who really cares can you ask questions about assignment too Id probably I'd probably ask you to put them on the forum。

 I still have a backlog of some forum questions and we'll try and get to them。It will do our best。

Soir。Yeah， I'll try and help you out there。 But thank you， everyone。

 And I hope you have a great night。 Oh， and before you leave， I forgot， oh my God。😊。



![](img/4593240dd453c0786024802f0f9d9ea0_145.png)

So mad。 How many people have I lost already， not many。Feedback， can you fill out the feedback。

 That would be great。 Thank you。 and get some， some good feedback。



![](img/4593240dd453c0786024802f0f9d9ea0_147.png)

6，7，7，1 feedback。 Don't you love 6，7，7，1 feedback。Anyway。

 pause the video if you want to take a screenshot I'm gonna。 I'm not just gonna sit here。

 So thanks everyone。 have a great night。😊。

![](img/4593240dd453c0786024802f0f9d9ea0_149.png)
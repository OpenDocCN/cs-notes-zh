# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p07 1695651300-Compliers.zh_en -BV14PAUejE98_p7-

All right。All right， good afternoon everyone。😊。

![](img/9b0cf13e407e569bd4a962ad31dba6e9_1.png)

Hope you all had a good weekend。And not all of it was spent on homework  too。Announcements。

 so first big announcement is we're gonna be moving classrooms。 So say goodbye to this classroom。

 This is the last lecture we're having in this room。 As of Wednesday， we're gonna be in secec 1。402。

 So we're moving up in the world，2 floors up， ground level， It's flat classroom。

 We will see how it goes。 I'll send out an email reminder。 But please remember on Wednesday。

 We're in a new classroom。😊，Homework 1 grades have been returned。 You should have all received those。

People did well on it。 In general， it was a refresher on Ocal， of course， and。

We went straight from that into homework 2， which， as you know， is due on Wednesday。 Again。

 there are up to three late days that anyone can use without any need for for permission。

 and we will， again， try and get you the graded homework tos within a week after that last submission。

 So that is by。Fday， essentially Friday next week。 Well， we should get you back the grade homework2s。

Hhoook three。Is going to be released on Wednesday。 L O V M。

 we'll be talking about that today and on Wednesday。 And essentially by the end of Wednesday's class。

 you should have all the information you need to be able to start working on homework 3。Will be。

Doing study group assignments for homework 3， either tonight or tomorrow。

If you want to opt out of it， if you had previously filled in a study group form and you want to opt out。

 please email me to let me know as soon as possible。

 I do know that there were some people who did not fill in a study group form and time for homework two who have subsequently filled it and will be incorporating you into the homework3 study group assignments will be trained to have it with mostly new people modulars。

 some other constraints as a chance for people in the class to get to know others in the class and figure out how it's going。

I appreciate that we're giving you the homework 3 study group assignments a little in advance for homework 3 before we've actually had a chance to hear feedback from you about how the existing study groups went。

 So sorry about that。 That means there will be a bit of a lag in hearing your feedback about the study groups and that playing into the study group assignments。

 But we did want to get these study group assignments out earlier so that。

You all can hit the ground running with homework 3。

 maybe schedule a time to meet over the two weeks or so that you have to work on homework 3。

Any questions at the moment on homeworks， administrative aspects， anything else？Okay。So。

We've been working on。Looking at intermediate representations。 and at the end of last class。

 kind of went through a series of intermediate representations， adding in more expressiveness。

And kind of seeing how we were reaching a design that was getting closer and closer to LL VM。

 And that's what we're gonna be looking at for most of， well， for a chunk of today's class， LL VM。um。

And then after that， we'll be seguing into looking at how we represent structured data。

Within a machine。 and the goal of that representing structured data is essentially getting you to be able to connect。

How we take sea level data structures， Sostructs， arrays and so on。

 How we represent it at a low level。And that's going to feed into Wednesday's class when we think about some more of the implementation details of how LLVM works and how。

 as you'll see in homework 3， as you'll be doing in homework 3。

 you end up translating LL VM into X 86 assembly。Okay， but for now， let's jump into L LVM。

 low level virtual machine。So this is an open source compiler infrastructure。

 You can take a look at L L VM dot org for a whole lot of documentation。

 There's a lot of things out there。There's a lot of information there。

L V M is actually really interesting。 It was created about 20 years ago at University of Illinois。

 Uana Champaign as part of a master's project。 So Chris Laner was doing a master's thesis with the Viram ave there and developing a modern compiler implementation。

😊，A modern compiler of infrastructure。From there， it clearly took off。 It's， Chris ended up， I think。

 working for Apple computer when Apple adopted it as their compiler in about 2005。 And since then。

 it's continued to grow。 working。Working for a number of different source languages。

 So we'll look at the infrastructure of V V M， the architecture of it later。

 But it essentially has a number of different front ends。For the C language， for Swift。

 which is Apple's language for writing App certain。Ada Scalar， Haskell， a whole lot more。

 It also has a whole lot of different backends。 So that is you can support X 86， power PC， Apple Sil。

 which is a variant of arm。 I believe you can also target Java bike code in it。

If I remember correctly。So what this means is that you've got this compiler infrastructure that has a whole lot of different front ends and a whole lot of different backends that has a common intermediate representation and a lot of common infrastructure。

 A lot of the passes that happen can be used on many different languages。

 And so you can imagine the wind that this gives you。Right， so by if you develop a new language。

 if you were able to translate it。Into L VM intermediate representation。

 So that is put a new front end on。 Sudden， you're able to compile to a whole lot of different back ends。

So this can be a for little no with it。 So this is very， very elegant。It's widely used in industry。

 but also in academia and research。 It's open source。

 and it's quite elegant and quite easy to use to end up developing new passes。

 new constructs and so on。I mentioned that it's open source。 And what that means is。

Open source means a variety of things。 One of it is that the L O VM is essentially free to use for a variety of uses。

 including commercial use。 So what that means is that with possibly a few exceptions。

 companies are able to use LO VM and use it in their infrastructure take it and modify it and use it as appropriate。

嗯。It also means that people can contribute to the code base。 It's kind of open。

 and there's a process for having contributions。 A lot of the actual development of L of VM is really funded by large companies who rely on L of V M as critical infrastructure。

 I mentioned that Apple is kind of very much invested in L of V M。

 And so these companies might devote resources to helping develop the infrastructure。

What's interesting is that。Many compilers are， in fact， open source for a variety of reasons。

 There are still proprietary compilers， although I'd say that's becoming less common。嗯。And indeed。

 we're going to be looking in our embedded ethics module in October。

At some of the ethics that's around open source， the positives and the negatives about it。

 So stay tuned for that。 But the reason why that's the embedded effects module for this class is really due to the way that open source approaches really permeate a lot of the compilerrs's world and the programming languages world as。

 as a way of building this infrastructure。And making it widely available。Oh。

 I should mention the L V M logo。The awesome Kckas Dragon。

So there's a tradition among compilers of having dragons as logos in some ways。 This， I believe。

 originated from a textbook in the mid 70s， Si and Omen。Think the title is compilers。

 I have like three copies of it sitting on my bookshelf。

 but I think the title might just be compilers。 Some can correct me if you remember。

 but the cover illustration was a dragon。 And so it's just commonly known as the dragon。On compilers。

And so L O V M choosing this logo was， was definitely a。An acknowledgecledment of that。Okay。

 I've already talked about how L O VM actually has supports a number of different front ends。

See C++ and so on。Has a number of different backends， but a common。Mi layer。

The middle layer that it has is a typed SSA。Single static assignment， intermediate representation。

So the design that we got to at the end of Wednesday's class really has a lot of the key concepts there that we're going to be using in L O VM's intermediate representation。

Within this IR。We perform a number of passes and analyses。 So transforming it to simplify constructs。

 optimizing it， performing analyses on it。Definitely as we go through the compiler。

 the instructions that are present in the IR will change and as we get closer and closer to the back end。

 we might see instructions that are say specific to a particular architecture but overall this general idea of the intermediate representation is shared by many。

 many different languages and turns out to be a powerful and useful representation for a lot of。

Work that the compiler needs to do。One of the nice things about LO VM is it actually offers a nice textual representation。

Of the intermediate language。 So that is， it's actually possible for humans to look at this and understand what it means。

 It also has other representations， including essentially a bait level encoding of it。

 that's more compact， more efficient and machine readable。

 But the textual representation turns out to be really， really useful。呃。

What we have here on the slide is。Showing you an example of。A C program here， a recursive， sorry。

 a non recursive program computing factorial of the input in。嗯。Simply looping over in。

 accumulating and returning the result。What I have here on the right is。

A version of this program in L O VM。嗯。We're gonna dig into it in a bit more detail。 But this is。

ASlightly purified version of what's actually produced by the L VM compiler。嗯。Let me。

 let me jump and actually show you。Let's look at this quickly。

 and then we'll look at it to see the real code coming up。 So we see up the top here。

 we're defining the factorial function。 that at at the beginning essentially means that this name is available throughout the compilation unit。

 We're defining a function， and it's taking a。An argument in as the input。

 that percent in front of it is what we're using for these locals， these unique identifiers。

 which can be strings and or numbers。嗯。We have a representation that's。Essentially。

 a sequence of basic blocks。 This first one is the entry basic block。

 It doesn't have a label at the front of it because you can't jump to it， but it's。Allocating。

2 stack slot on memory， percent1 and ACC for the accumulator。

 It's storing in into the memory location that it just created on the stack。

 Storing what into the accumulator， and then jumping to the label start。 That is to this basic block。

At start， what it's doing is。Loading the value from percent one。From that stack lot created。

 comparing it to0。 And then based on the result， either going to the then block or the else block。

The then block is essentially the body of the loop。 and start was the guard of the loop。

 So inside the body of the loop， we're essentially loading the accumulator。

 loading our current value of n， multiplying them together， putting the result into the accumulator。

Loading in again， subtracting one from it。And storing the result back into the memory location into when jumping back up to the start of the loop。

Okay， so the ideas here are very much the things that were seeing in our intermediate representation。

At the end of last class， and notations may be a little different。But hopefully。

 relatively intuitive。呃。Down here， this else branch， if the guard is false as exiting the wild loop。

 And essentially， what we're doing is loading the accumulator。 and that is the。

The 64 B value there and returning it from the function。Yeah， very。First time， we sign。

A variable of value。 We have to use。Assignment， then if we want to update that value。

 do we use store。That what store and load。Would， we dig this into this more in a bit。

 But these local variables。Our。They can only be。There's only one place in the program where appear on the left hand side of an assignment。

嗯。If you want a。Mutable variable， something that you end up。Changing the value of。

It's going to need to be a memory location。And that's what alllaque is doing。

 allocating a some memory for it。And the result of alllaque is actually a pointer to the location。

And so that's what's going on here。 It's creating a pointer。

It's creating memory locations where it's going to be storing those mutable variables in and ACC。

 the accumulator。 And then what's going on here is percent1 and percent ACC。

 Those local variables are actually pointers to memory locations。And as the program is going through。

 it's reading that is loading from those memory locations and storing to them。

When it reads a value from that memory location， it's gonna be a 64 B sign integer that of them might be manipulating through multiplication。

 additions， subtraction and so on。嗯。Those memory locations。

 you can think of them for the moment as being memory on the stack later on in the course。

 we'll see how we might try to compile those efficiently。

 saying to registers and not to pay the price of the memory access。 But at the LL VM level。

At this level of representation。We're not actually needing to think about the difference between registers and stack slots。

 We're kind of just thinking about it abstractly as memory that's allocated specifically for this function andvocation。

I said howLVM was typed for it。Yeah， let me show you some real L VM code because this is not typed。

 but this doesn't have the type annotations rather。Right。OK嗯。



![](img/9b0cf13e407e569bd4a962ad31dba6e9_3.png)

Alright， here's the factorial program that we had again。With a mains stub invoking it。呃。

Here's the pretty L O VM file。 Essentially， this one does have type annotations in it。

You should probably just copy those over to the slide。

 And so what we're able to see is things like when we allocate on the slack， we're on the stack。

 we're providing the type of the value that's going to be in that location。 So a 64 bit integer。

64 B integer。 when we do a store， we're saying， well。

 what is the type of the value that I'm storing into the memory location，60，64 B int percent N N。

And here's the memory location I should be putting it into。 Their memory location is a pointer。

That is， it's referring to a location whose contents are by 64，64 B integer。Similarly。

 with this store here。With something else that's useful。He was saying in the。Comparison operation。

 where we're。Performing a sound greater than comparison。 One argument is percent 3。This local。

 which is a 64 B integer。The result of loading from percent one。And the constant the。嗯。嗯。Yeah。

 so you're seeing in here explicit type annotations。This is slightly simplified。

 Let me take a look at。Let me actually compile。That factorial function。

I'm going to be telling the compiler to om LL VM。Okay。So that actually ended up producing。

Factctorial 64。Dot L L。Should I open that up。Take a look。 This is the。

This is what's actually produced by the compiler。 So you can see it looks pretty similar。

 but a few more annotations in there， including let's see。

 alignment information telling it that when we're creating this， these data they have to be aligned。

With their aligned memory。 But it's looking pretty similar， right。

We don't have nice handy human readable names。We have。These numbers for the basic blocks。

I' also note that L VM is recording what the predecessors are to the basic block。

 So what are the places that can jump to the basic block。 It's from。The basic block labeled 7。

And the entry basic block。Now， this Lium code， it， it really works。 We can。Compil it。Down to。

We can compile it down into working code。Produces factorial of 6，7，20， exactly as desired。嗯。

I should also point out that I'm not actually using GCC， the Gnu C compiler。 if we。

 what's actually going on here is。It's actually Kang L O VMC front end。

But they have a version of it that accepts all the GCC command line arguments so that it's a drop in replacement for GCC。

 And in fact， when。呃。I can't remember ships with GCC U installed it with when I installed Xcode。

 but essentially it creates this GCC executable that is really LVM。In the back end。嗯。Okay。Okay。

 I think I've covered。Most of this showing you real LO VM code permits numeric identifiers。

 has those alignment annotations。 It ends up keeping track of the predecessor basic blocks as well with additional information。



![](img/9b0cf13e407e569bd4a962ad31dba6e9_5.png)

And it has the type annotations in there， I 64，64 but integer。A 64 star is a pointer。To that。

I 1 is one bit of information。 And that's the result of comparison。嗯。呃。So where， for example。Yeah。

 so when we did a comparison here。In the loop guard， put the result in percent4。

The type of percent4 is an I1。A single bit。I've already kind of waved my hands and talked about how this representation is these labeled basic blocks。

 These correspond to a control flow graph。So this is me explicitly showing you the labeled basic blocks。

Plus， the distinguished entry block。And showing you the edges between them。

Based on the branches and the conditional jumps。So， there are。Some。

Restrictions that we need on our VM code， essentially in order to make sure that it's a well formed control flow graph。

In our representation and Ocal， some of these are going to be enforced just by the way we're representing the data。

So， for example， as we saw last class。嗯。Our representation of a block。Is a record with two fields。

 a list of instructions。And a single terminator instruction。

So what this means is any block we have is gonna be a sequence of instructions with a terminator That is a branch。

 either conditional or unconditional branch or a return operation。嗯。

We also make sure that our representation of a control flow graph。

Has a single distinguished entry block。 And that's because our control photograph is a pair of。

A block that's the distinguished entry block with a list of labeled blocks， the rest of the CFG。

There are some other restrictions， though， that we're not able to directly restrict just based on our the way that we're representing a control flow graph。

 So， for example， no two blocks should have the same label。

 The label should all be unique when we have a terminator that's jumping to another label。

 That label has to be defined within the same function。Okay， within the same set of basic blocks。

 And this is to make sure that all the jumps that we're doing are local。 right。

 You're not jumping into another function or somewhere else in the code。

Any questions at the moment on these ideas， Nicholas。Maybe prefer a hash。We could do that。

 We could end up with a hash table。This is nicer for some iterations。 But yeah， you could。

 you could move back and forwards between。You know， a map and a list of these key value pairs。嗯。

But the， the direct manipulation in this forms。A little easier。Thanks。O。Within LOVM。

 we have several kinds of storage。So've got the local variables， those temporaries。Percent U I D。

 unique identifier， either a string or a number。嗯。呃。We also have global declarations。

That uses the at prefix indicating that the name is available within a global scope。

We have these abstract locations that we saw an example of with the Alc a。Cre。

 creating a stack slot with allloque。You should think about those stack allocated storage as having a lifetime of the function invocation。

Simst thing might be， as I mentioned， to think of them as living on the stack。

 memory location on the stack。 but as we'll see later on。

 they might end up being compiled to be register only。

But that's essentially just a performance optimization。 At the L of V M level。

 you want to think about them as abstractly some memory location whose lifetime is the function。

 the function andvocation。We also have he allocated memory locations。 And this would be created by。

 for example， calling Malik to create memory allocate memory in the heap and be able to use it。😊。

For local variables， these temporaries， they are defined with instructions of the form percent U I D equals。

 and then some instruction。嗯。As I mentioned， any given U I D。

 there can only be one place in the program that has that U I D on the left hand side。

 There is only one place that assigns to it。 This is the SSA form， static single assignment。

 So that is statically looking at the program text。 There's only one place that assigns to it。

This is not the same as dynamically being a single assignment。

 because that assignment might occur inside a basic block that gets executed many times within a function andvocation。

 right， within the body of a loop。So it might be that that variable is assigned multiple times。But。😡。

The way it's gonna work out is the lifetime of that variable。 during the lifetime of that variable。

 it's immutable。Right，That is once it's been assigned to。

 it doesn't change again during its lifetime。 It lifetime might end that same U I D。

 that same variable in the name might be reused another time within the within the function。

Ittheically， there is only a single assignment。Yeah，No， you cannot store into a U I D a。

A store is an operation on。One of these abstract memory locations。

 So on the something that's produced by alaque or by Malek。So these temporaries。

 once you've created them， once you've assigned to them， they are fixed， immutable for their。

 for their lifetime。Yeah，关键就是。嗯。It helps us with。Analysis of programs。

 it turns out that knowing that there's a。There's only a single assignment site for this local variable for this temporary helps us。

 lets us be a bit more precise if than if we had multiple assignments to the same variable。

 It doesn't restrict our expressiveness。 We'll see later on in the class how you can end up encoding。

A mututable。Lcate a mutable variable as into these temporaries through the use of a special construct known as a fine node。

 We'll get to that later。嗯。But the。呃。And it turned out to be kind of a clean。

Representation of the program。We're not going to dig into it much in this。Course。

 but the SSA representation allows you to kind of see the data dependencies of temporaries。

In a way that's kind of independent of the control flow graph。

So this turns out to be essentially give you for free and easy alternative way of looking at things。

 You can see which variables are defined in terms of which other variables， essentially as a tree。

Right。And then the control flow graph is telling you the order that these instructions are interleaveed in。

 But sometimes it's useful to know。 Well， I don't care which of these is computed first。

 Just tell me what the dependencies are。 So SA turns out to be。You get that for free， essentially。

 just。By way of the representation。没有。What determines that lifetime。

What determines the lifetime of a local variable。Well， if we're looking at a high level language。

 we actually have an idea of scope and then the the scope that a the name is available in the context for。

 So if you declare a local variable inside some deep inside some while loop， right。

 that variable name is only gonna be available in within that the body of the while loop and an outer scopes。

 it won't be available We don't actually have that directly in control flow graph representation because there's no notion of these nested scopes。

 you've just got these blocks where almost arbitrary jumps between them。You can still， however。

 talk about the idea of the lifetime of a variable as being。Is there any point。In the future。

 there is any path that I can get to from this point in the program。

Through the instructions following the basic block edges where this variable is red。

Without encountering an assignment to the variable。Right， and so by that， I mean。Can I have a path。

That， that will give me to an instruction。 and that path has neither an assignment to this local variable。

And， and and I get to some place where it reads the stuff。

That's what it means for're variable to be live that it might be used。

 that the current value in it might be used in the future。

And so what we're saying is once it's a signed， while it is live， the same value is going to be read。

Does that clarify。That was very hand wavy。 We are actually gonna be looking at live variable analysis in more detail in a month or something。

 Yeah， Madeline。Would book home global variables， are those on the registered。Yeah。Local variables。

 yes， correspond to。Registers， in fact， they're often， they're sometimes called virtual registers。

 And later pass on the compiler we'll actually take care of saying， well。

 how do I assign these locals into actual registers。嗯。Globals， though， are typically not registers。

 They're typically memory locations， either。You know， read only global strings， for example。

 or memory allocated in some part of the memory in the heap or in like a data segment。Okay。

 so we'll get to global soon。Locals。Stack allocated storage rather can be created with this all A instruction。

So the way to think about it is allocate。Takes as an argument， the type。

That's going to be stored in the location it's creating。 right。

 That's how it knows how much spaces to assign for it， essentially。

 And the return of the aque is a pointer to the newly created location。So here's some example code。

 We're calling aque， saying， I'm w to。Some local storage。

 some stack based storage enough to store a 64 B integer。 We get back a pointer， ACC。嗯。

We can then use that pointer in loads and stores。Okay， so here we're storing the integer 153。

Into the newly created location。ACC is appointed to6864。

And here we're loading from it and putting the result into the temporary percent X。

Any questions at the moment about。L K， yeah。Whathy is necessary。

In this attacks that we have to specify the type of。

The value that we're putting in also the what the。Like wouldn't it be implicit that maybe？Yes。

 they pretty much should agree。So part of the cell of the MIIR representation is that it's being very explicit about the type annotations。

You will find this useful later on， as you。One， both understanding what's going on and debugging。

As well， like trying to figure out， well， what is going wrong here。 So you're absolutely right。 You。

 there might be within the real L of VM， there might be some。Slight allowances for。

Some implicit type casting where these are not where the store and the pointer to the element are not。

 the types do not exactly correspond。 But for our purposes， they pretty much always will。Yeah。

 very you。我。这。A value that we've allocated。But， it's not top。

They didn't believe this type at all of work。that location。Now， when， when I'm saying the stack。

 I'm meaning the stack frame。Right， so that is when you invoke a function and you， you know。

 change your base pointer and your stack pointer to allocate memory for this function andvocation。

What we're talking about， that's going be the concrete implementation of allque is that it's going give you a space on the stack。

So by top of the stack， did you mean the top call frame or did you mean。

 or were you thinking a stack of values like we might have right。

 So I want to clarify that this is not a stack of operaan values like we saw in some intermediate languages。

 you know， like in Java byte code or something where， you know。To add 35 and 7， you push 35， push 7。

 and then call add， which pops those two values off and pushes on the result。

 We're not talking about stack based instructions here。

 When I'm talking about stack allocated storage， I want you to think based on the stack frame。

We'll see later that。 yeah， you could。If you think about your programming in C， you could。

 you can take。The address of a stack allocated variable。

 like of a local variable within your C program， but you need to be careful about it。

 You need to make sure any time you dereence that variable。

 your stack frame is still either at the very top of the stack。Or it's， it's dereenced in a coolley。

 That is the stack frame is life。 I have an example， later of。Whating go wrong。不的。Alright。

 thanks for the questions。 Anything else。About anything in L O VM we've encountered so far。O。

We're going to switch gears a bit。Okay， so we've gotten。Learned a bit about L of VM。Next lecture。

 and in homework 3， we're gonna be learning more about L of V M。

But what I'm going to do now for the rest of this lecture。

 probably the beginning of next lecture as well， is talk about how we're going to represent structured data at a low level。

 So that is structured data that we see in a C program，structs and arrays and so on。

How does that get represented in at lower levels， at assembly level。And also at essentially。

 at L L VM level。 And so the reason why we're doing this is when we understand how we're going take these high level structured data and represent it at a low level。

This is going to motivate and explain some of the constructs in L L VM。But in some ways。

 it's a bit of a detour。 right， We're going be learning about essentially compiling structured data in order to give us insight and understanding of what's going on in L L VM。

Okay。So， with that。Let's think about。Compiling some C。Structures。So here I have some code。

We declared a structure point。It contains two integers。

 I'm gonna be using 32 B integers for simplicity。 So 4 B。Used to represent a 32 bit integer。

And then we have astruct rec rectangle。Which has four elements， each of which is a point。

 So itself for structured data。 the lower left corner， lower right corner， upper left corner。

 upper right corner， not the most efficient representation of this rectangle。

 but hopefully the intuition is clear。We have a way of a method to construct a square。

That's going take two arguments。 the lower left point of the square。

 and then the length of each of the sites。 And what it's going to do is return。

One of these rectangleularular rectangular structures。 Okay，rick square。

So let's talk our way through what's going on here。 I'm going to use。Some animations to help with us。

 So conceptually， we have these four points that make up a rectangle data structure。

We initially start off this function by setting all four of these points of our square to be the。

Argument， L， L， lower left。Then what we do is。2 square dot L R dot X。 We add the length。

 So that is for the x dimension of the L R member。 we're adding the length。For the U R dot X member。

 we also add the length。 U R dot Y， we add the length。U L dot way， we add the length。Okay。

 so this is a way of constructing the square。Let's think about how we're going to represent these drugss in memory。

So let's consider first with a point struck with two elements， X and Y。

What we're gonna to do is use two contiguous words of memory。To represent an element of type。

 Str point。Okay， so the two fields， X and Y。So what you can do。

 you can think of a value of type point。As being like the memory address at the beginning of these two contiguous words at the beginning of the representation of the two fields。

 X and Y。Does is that team？ O， We're comfortable with this idea。

 We're representing thestruct just by using contiguous locations and memory to representsent the X field and the Y field。

So the same idea applies when we're representing。Erectstruct erect。 Okay， it's got four points， L， L。

 L R， U， L， U R。 What we're gonna do is lay out that data in contiguous memory locations。

So we're going to have a location to represent L L。Right after that， we're going to represent LR。

 After that， U L， after that， U R。But of course， each of those points requires two contiguous words。

So the representation of our square value。A value of type struck react is actually 8 contiguous words of memory。

Right。first word is LL dot X， then LL dot Y。Those two words together， represent L L。

And so on for the other four point the other three points。

Are we comfortable with this idea of kind of linearly laying out this nested structure。Great。

So let's think about what the compiler is going to need to know。In order to do this。Well。

 first of all， it needs to know for each element of thestruct。The size。Of that element。And from that。

 it's gonna be able to figure out the size of the struct。 right。

 If I wanted to create some memory that was big enough to store astruct direct value。

How much memory am I going to need to sit aside， The compiler needs to be able to figure that out。

The compiler also needs to know the shape of the structure and memory。

But it needs to know how exactly it's laid out so that when the program wants to access some element of the structure。

 it knows how to index into it， how to compute a memory address to reference the right piece of memory。

So let's think about this a little more。Okay， we have our square structure that has8 contiguous words。

Let's suppose we were accessing square dot U， L dot Y。And thinking about， how do we。

Compile this down。The approach would be taking in， you know。

 that we saw in some of our compilation approaches is the compilation。

 the meaning of this squaredt U dot y is going to be a sequence of instructions。

It's a assembly instructions， x 86 instructions to compute。The address into there to load the value。

 And then the result of that is going to be stored in some X 86 opera end for us to access when we need to use that value。

Let's assume that the register R C X holds the base address of square。

In order to access square dot U L dot way。What we're going to need to do is figure out。

From a pointer to square。How do we get to a pointer to UL？Once we have appointed to UL。

How do we get to a pointer to the element why。Now， if we take a look at the layout。

From the beginning of the pointer to square。To get to the beginning of the U L value。

There are two struck points in between L， L and L R。So， that is。To access the U。 L element。

We're going to need to add to RCX， the base address of square。Two times the size of struct point。

Okay， that's going to allow us to skip over。The memory representing L L and the memory representing L R and get us to the beginning of U L。

From the beginning of U。 L to get to the element Y， we need to skip over the field X。Which is an int。

 That is， we need to skip over the memory being used to store the int。32s。 So4 Bs。For an inch。

8 by for a point。 What that means is that to access。To access square dot U O dot way。

 we want to take the address in R C X。Add 20 to that address。Right，5。2 times 4 plus2 times 4 plus 4。

To get the appropriate address to， to read。So the cool thing here is that。

From the base address to this。Complicated data structure。

Figuring out the memory address of the field to access。

Is actually just some constant number of fights。From the beginning of it。

Figuring out the number of bytes。Is maybe a little complicated for the compiler。But ultimately。

 it's just a single number。Right and computing the address that we need to read。

Required no memory accessors。Just by knowing the base address of the struct。

 knowing which field we wanted to access， we were the compiler was able to figure out that we want the address 20 beyond the base of the struct。

We didn't need to access memory to do that。OK。Meed on the program。

To compute the address of square dot U， O dot Y。Required no memory accessors。Right。

 we had the base address obstruct。We needed to figure out how many baits beyond that to get to the wayfield。

And that might be complicated。 right， We had to add up sizes ofstructs and fields and things。

 but we figured out it was 20。Now that we've got the address， yes。

 we can read it to actually read the value in squared do U dot Y。

 But the key thing that I want to emphasize， because this is gonna be really confusing in homework 3 is that to compute that address required no memory access。

And I'll emphasize that again next lecture when we look at how LL VM computes addresses。Okay。

 any additional questions on， on this， I appreciate。Actually， was this coveredvenant 61。

This kind of stuff。Fantastic， good。 So I'm glad it's a refresher for many people。

 It's something that。😊，Making sure you're very comfortable with will be useful in homework 3。그。Okay。

 I've obviously gloss over a whole lot of details。 And in for those who' have done 61。

 you know about padding and alignment， right， The idea that if I have values that are not。嗯。

The right length I might run into problems。 So let's， here's。

 here's an example structure that contains。An integer，4 by。2 characters， A And B。

 characters represented with a single bite。And another integer Y 4 B。

 So if it LED them out contiguously， it looked like this。 X taking up4 B， A And D，1 H Y taking up 4。

 the problem。Is that Y is not 32 but aligned。 It's not aligned on one of these dotted boundaries。

 And what that means is that depending on the architecture。

 either we won't be able to read that value directly。

 And if we wanted to read why would actually need to break it up and two separate reads and then do some bit manipulation to reconstitute the result。

Or we might be able to read it， but it's quite likely the architecture will be slower for reading that。

 that particular address。So instead， what we might want to do is provide padding。Have。

 within our representation of the struct， some unused bites。Now。

 there may be some options for how to do this。 So in this example here， the second line。

 we're using some padding to have two empty bys so that A And B are packed in。Why is 32 bit aligned。

Wonderful。But， of course， this means that。Accessing A And B， again， depending on the architecture。

 might either be inefficient and or require some bit manipulation。

 So in order to read the value of a。 So another option for padding might be that we use 4 Bs to represent each of A And B。

Right， so there's more padding involved here。Of course。

And even though we're wasting some space in the representation of thestruct。

This may end up being more efficient in terms of the computations to load。

 store and manipulate those values。嗯。Right， so the compiler is going to need to make choices for this and。

 you know， figure out how many bytes are needed to represent astruct。 And that， of course。

 is going to be part of what's used in the computation of figuring out what is the right address to access a particular element。

Any questions at the moment about the spanning and alignment， Nicholas。In some ways。At a high level。

 it doesn't matter。 but I was thinking of it as lower addresses here， Ha addresses here。

 so that if this is the address at the start of the struct， you know。

 if F is the address at the start of the struct， F plus 4 would be the address of the A field。

 F plus 5 would be the address of the B field。 F plus 6 would be the address of the way field。Like。

 why would there？Oh， you might want to have the char being represented in the8 least significant bits of a word。

嗯。the。Which might make some of the manipulation easier。有。Okay。Yeah， is that a question Ta。

finding out。So optimal is a really interesting idea。So is。

 is there an algorithm for finding the optimal alignment。

Opttiical is gonna depend on a lot of things。 So it might depend on the architecture they're using and how much the cost is of。

 of reading at certain values or the cost of reading and doing bit manipulation。

 But its also gonna depend on access patternss。Right。

 and also was going to depend on which resources you constrained under。 Are you tied on。

 Are you short on memory， Are you short on computes Are you short on bandwidth to go to the memory layer back to where you are。

 So it's actually really hard in general to figure out what is actually optimal is。

 What ends up happening is there's often heuristics and compilers might make decisions on the layout based on heuristics。

 maybe based on their understanding or experimentation or guidelines about particular architectures。

But my guess would be that for any particular layout。

 you could probably come up with a workload where it is suboptimal。And actually。

 as we get to optimizations in the class we。Kin of realize that optimization is often a misnoma it's。

Becauseuse it's， it's unclear what exactly what the objective function is that you're optimizing。

All right。Let me just point out that。In the C programming language。We wei。Do an assignment。嗯。

For one of these trucks。Let's say this line here， Res do L R equals L L。

What's actually happening there is that we're copying all the elements from the source and putting it in the target。

 So that line of code， Re dot L R equals L L is really equivalent。

To copying over each element of the field。 So it's actually copying over multiple words and memory in order to accomplish aing astruct value into some other location。

So what that might mean is that the compiler。If it's wanting to compile an assignment of astruct value。

 maybe it'll break it down into field like assignments for larger things that might actually use meM copy。

 like directly using a lower level routine to copy large sections of constiguous memory from a source to a target。

So this idea of actually copying the values， moving large amounts of memory。um。

Unless you're kind of aware of what's happening。It can， It can be a little transparent。

 You may not be aware of it happening in the code that you're writing。So for example。

 if you pass in as an argument。To a C function， astruct value。

It's actually going to be copying that entire truck from the source location into a target location。

 So that is， say， into somewhere on the stack of the core E。In a similar way。

 if you were returning a result。Returning a result of astruct value。

 it's actually that doesn't fit into the RA X register， you know。

 which is where you'd normally return 32 B results from a function。

 So instead what you'll be doing is needing to allocate some memory somewhere in order to put those return results。

嗯。So this is sometimes called core by value， which is not great terminology。

 because it's really hiding this idea that you're actually copying these values。

 So copy and copy out is an alternative name that's maybe more accurate。嗯。So， of course。

 the benefit of this copy and copy out is that you copy the value into some memory location。

 Let's say into some static allocated memory。 And then you might get some nice locality。

 As you're using that value， you're accessing memory locations and the stack frame。

 you copied it into your current stack frame with all your other local variables that you're manipulating。

 So things work nice and fast。The downside， of course。

 is that you're paying to copy into the function and then back out again。

 which for large records might end up being expensive。

An alternative to this copying in and copying out。Is， of course， passing a pointer。To the value。

 right， this is essentially called by reference。And C。

 you would do this explicitly by instead of taking astruct as an argument。

 you'd take a point to thestruct as an argument。In some languages like Java and Ocal。

 it actually automatically passes by reference。 If you pass in a structured piece of data。

 what it's really doing in implementation time， compile time is passing in a pointer for anything that isn't。

Word sized and able to fit inside a register。So。If we go back to our make square example。

And instead of using copy and copy out， if we did call by reference。That is， if we took in a pointer。

To。LL。As an argument。And we're going return。Put the result into the memory location pointed to by Res for the result。

You can see the code can be pretty similar， but it's also doing this de referencing through the pointer。

 right， accessing fields through pointers with this arrow notation。The nice thing though was。

 of course， the arguments being passed in。is just a single word a pointer to thestruct instead of all of the information needed in the value of thestruct。

So this seems great。 You can just pass references around。Okay， and that gives you。

You're passing fewer data between functions。 You've maybe got some memory accesses through。

 Maybe you lose some locality， but it's generally worth it instead of copying large amounts of data back and forths。

One thing you need to be careful of， though， is pointers to stack allocated data。So。

Is this familiar to people who' have taken 61。Taking the address of a stack variable is dangerous and you need to be careful。

Sounding familiar。Okay， let's take a look at an example。s。Al right。



![](img/9b0cf13e407e569bd4a962ad31dba6e9_7.png)

Here's a C program， unsafe Sta。Right， so the name is sensing of what's going going to happen。Alright。

 we have a function called bad。Now， what bad does is。It puts some。

It gets some stack allocated storage。X。It's going to take the address of X。And what that means is。

The compiler is gonna end up putting that variable， that storage for the variable X into memory。

 right， It can't be a register because the address is being taken of it。

 So it's gonna be on the stack。And then returns a pointer。To that variable。To that out。

 to that place on the stack。Problem is。The the function then returns。Okay。

 so pointer is now pointing to a memory location。On the stack。

And we're going print out the contents of the result of that。 So what would you expect to be here。

In this line。Call it up。1，53， right， the value we put into that location，1，53， we then call foo。

What food does is。Create a local variable，42。Local variable secret and assign a value of 42 into it。

And returns。Back here in Maine。We do the exact same。

Ling that we had previously before we invoked food。

 that is we de referenceence pointer and print out the result。

What value do you think is going to be printed out。扣的。42。Maybe。Let's see what happens。um。Ohh。

 good question。 What does Prif do to the stack。Yeah， let me。Let me make this。

 All I'm doing here is compiling using L VM。 We're gonna run it。哦。Now， of course， as。

 as we hinted at by calling that variable secret。Maybe， maybe that call was， let's say。

 getting a password from the user。Right， putting it on the stack。 And now somebody is able to access。

 well， that was。Bad practice， actually， just leaving it on the stack without overriding it。

 But this idea that。You can have unexpected behavior。And indeed， in the C spec。

 this is actually undefined behavior。 The language specification doesn't say what should happen if you end up with a pointer to a piece of memory that's no longer valid。

Okay， so when you do reference it， when you look inside say it， what's going to happen。

It's up to the wims of the compiler。 And as you can see， what this compiler ended up doing was。呃。

Giving us the bad result， let's see if we can。So here's the assembly of what was going on and you can kind of work your way through it。

And see what's going on。Well， one of the key things that it's doing is。

The value that it is returning。Contents of RBP movies X。 Yeah， here it is is。

Loading the address of the base point of minus-4， putting it into RA X。

 and then essentially returning that value。From the function。 right。

 So returning the address address from the stack。And then you can see later on how F turns out to be using that exact same address to put 42 in。

All right。Any questions at the moment。We've got about 8 minutes left。 So let me get started on。



![](img/9b0cf13e407e569bd4a962ad31dba6e9_9.png)

Kind of the next chunk of things， even though we weren't。B finish it。

 So we kind of looked at how structured datastructs are represented at a low level。

Let's now think about a raise。And how an array is represented。嗯。Here we have on the left hand side。

 we have a function foo Thiss declaring an array of characters， buff。Or length 27。

And then what we're doing is putting in the alphabet in lower case， putting a into into x 0。

 B into index 1 all the way through into Z。 We're putting the0 with a null character at the end of it。

 characters and see a null terminated。 They have to have a。A 0 by indicating the end of it。Now。

 what's actually happening here。Is。Space is being allocated on the stack frame for that local variable buff。

Right。And it turns out that when we're accessing the index of an array。

 all we're really doing is computing an address to access。

The zero of an array is just the beginning of the array itself。

The I element is simply I times the size of the elements of the array。 right。

 So the base of the address plus I times the size of the elements。

This should be comfortable and familiar， right， this idea that if I'm accessing an array。

 A the index is telling me how many bytes to move from the beginning based on the size of the element。

Now， of course， for nested arrays or multidimensional arrays， rather。

 the element might itself be an array。And so， for example， if we have the two dimensional array M。

With four rows and three columns。We can conceptually think of it as this two dimensional array。Right。

3 by4。But it's actually laid out in memory， in a particular way。Alright， in C。

 they're later in what's called room major order。 And by that， I mean。

When we think about how they're laid out， each row is laid out contiguously。 So here， we。

 first of all， have the row M 0。La out the three elements there。

 followed by the representation of the row M1 and so on。 then the row M2。

So what this means is that when we have an array axis， M I J。

The way that we compute that element is we started at the base address of the array， M。嗯。

Based on the row that we want to get， the I throw。We're gonna need to add I times。The size of a row。

Which is three integers。 right， So i times。Three times the size event。That gets us to the eye throw。

And then we to access the J integer of that， we need to add J times the size event。

To get us to the right element。Okay。So。This is a little more complicated， but the same idea is true。

 right， to access the earth element， we need to know what the size of element is。 In this case。

 it is an array of 3 ins。And then kind of recursively。

 once we're at the beginning of an array of 3 ins， we need to know to access the J element。

 And we just multiply J times the size of。The integer and there。Right， so this is reminiscent。

Ofstructs as well， right， over the way that to access a neststruct， we needed to figure out， well。

 how do I， what's the size of my structs that I need to jump over beforehand。

 How do I access a particular field of astruct。So Rome， row major order is。Pretty common。

 But some languages actually choose what's called column major order。

Right so some column major order， they're laid out。A little differently。

 Each column is laid out contiguously。So what this means， of course。

 is that to figure out the right memory address to access。Sa my dear kind of holds true。

 but you'll end up thinking， well， I have to jump over J columns。

In order to get to the beginning of the column， And then I have to access the correct row within the column。

So the computation is， is similar。In M， L， there's actually no such thing as a multidisional array。

Instead， what you end up having is。An array of pointers where each pointer is a pointer to an array of ints。

Okay， so you've kind of got this tree like layout of this of a two dimensional array。

 an array of pointers。 and those are pointing to， let's say， the rows of the。呃。Of the array。

So does me。not continues。我哋出边。An M L two dimensional array。

 a multidial array is not laid out contiguously in general。And。

What it means is that to access an element to compute the address of the I J element will likely require a memory access。

 You need to get the access， the I element。Get the pointer to the to the row。

 And then from that base pointer to the row， figure out the offset。Right， so that is to load。

 to read the value of the I J8 element is going require two memory accesses versus in C。

 where you have the。A two dimensional array laid out contiguously。 It would be。A single memory axis。

 You can compute the address without needing to do any reads。

 and then a single read to get read from the right location。So。Well。

 let's ask the question on the slide。 Why is it， Why is it important to know the memory layout strategy a compiler is using as a programmer。

Turrk。哎有万了。哎行。Right， the memory layout can have a huge impact on cash behavior。

And what that means is if you're accessing a two dimensional array in a particular way。

 if it works well with the way the cache operates。Then fantastic。 You might。Be。

 your computation might be very quick， whereas if you're accessing in a way that doesn't。

Ling up with cash behaviour。 You might find that it's。The performance is terrible。嗯。

Have you seen experiments where just changing the order of loop iterators cause a huge explosion and behavior。

 You can try it out if you want， like access Racy program， create a large array。

 access and road major order。 you know， I J， where you're going through。J。

 the columns swap the order of the indices and see how long things take。Another question for you。

 we've kind of sketched out three different layouts， right， row major order， column major order。

 nested， like pointers to a。What are the advantages and disadvantages of， of some of these。姑娘。

What you just mentioned is that there's probably no way。Advantage。That's right。Right。

 so downside of the nest pointers is that we may not have good memory layout。

 We may not be able to get。 And so common access patterns of say going through every single El element of the two dimensional array are not gonna get the benefits of。

 or maybe not as many benefits of。Caashching and or predictive prefeting that modern architectures have。

Are you， me。You need more space for the nested pointer representation， right。

 because you have the memory locations for each element。 Plus。

 you've got this layer of needing an array of pointers。 Yeah， he， did you have a， was that a hand of。

 Yeah， yeah， we've heard some attractiontracts from this pointer representation。

 But like if you want to swapamp rows。Swing rose is really cheap with the pointer result。With。

 with the array of pointers from a programmer's point of view， Why is having this。

This representation， an， an array。An array of point is useful as well。

 So summer operations is going to be simpler and easier from an expressiveness point of view。为什。

気持ちいい？Okay， so some operations of maybe easier。 Like it's maybe easier to add a row to the array。

 maybe add a column to every row of the array doesn't require as much。I take that back。 Actually。

 it's going to require a lot of memory accesses。 Actually。

 did you have raise your hand like operations that。He's higher row。So for example。あみましたです。Right。

 okay， so some， depending on what it is you're trying to represent。

 some things might be more efficient。Another one is variable sized rows， right。

 if you don't actually know。If you have an array of arrays of variable sizes。

 it's hard to represent contiguously and get any sort of advantage。 So the nested pointers is useful。

 Okay， I'm actually now we're a few minutes over。 So let's stop it there。 Wednesday。

 we'll continue talking about arrays， memory accesses and then bring it all back to L of V M and homework 3。

Thanks so much， everyone。 I'll see you on Wednesday in the other room。 First floor of the sec。

 two floors up。😊，嗯。B。あ。好行。

![](img/9b0cf13e407e569bd4a962ad31dba6e9_11.png)

絶対も。在这里。かた。Yeah， my handwritten test does that。Indeed， run those on other people's code。

 and that's a requirement that you put it on that。I don't know like my。



![](img/9b0cf13e407e569bd4a962ad31dba6e9_13.png)
# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p24 P24 Compiler implementation： Pointer ref and deref (COP-3402 Fall 2024) -BV1v6vdBKEHB_p24-

![](img/679125bc73ccd8e5ac21a4b467bceb89_0.png)

Welcome back to System Soft， we are going over how on CoN3。

We can use this wrapper that I've given you in order to test this part of the compiler。

 just the arithmetic and branching without having the full compiler written。

 so it basically gives you a。

![](img/679125bc73ccd8e5ac21a4b467bceb89_2.png)

Template。A pre compileiled template of this。IR file。

 so this IR just declares a function set of local variables。

It calls print int this C function that I've。That I've implemented here。For you。

 it prints an integer。I think we talked about this last time。And then it returns zero。

 so that's what this IR function does。 and I've given you a pre compileiled。



![](img/679125bc73ccd8e5ac21a4b467bceb89_4.png)

Assembly version of this。It's broken into two files， wrappper end andpper start。

 wrappper start and R end， why would it be in two pieces？



![](img/679125bc73ccd8e5ac21a4b467bceb89_6.png)

This IR， why wouldn't I just give you the assembly？Why bother breaking it into two files yeah？

Not quite so if I compile， let's say I compile this program where I say result。Equals 10。

What's this assembly file going to contain， the compiled version of the assembly file？

What's the first thing that it contains yeah？Yeah， yeah。

 all the assembly metadata and the function prologue。

And then it's going to contain the compiled version of this assignment。

 and then what's the end going to yeah。不。まだ。No， the files I've given you is the compiled assembly。

Version of this so that yeah， so as your col saying。When you compile this program。

 you get the function prologue。And then you get。This。

Assignment here and then you get the call statement and then you get the epilogue in return。

So what I want to do here is I want to allow you to put code here。Put your code here。

But be able to plug that into a pre compileiled function。

And so the function has a prologue and an epilogue。

 so we at least need something before and after your compiled version。



![](img/679125bc73ccd8e5ac21a4b467bceb89_8.png)

Let the full let me get a full version here to show you what I mean。



![](img/679125bc73ccd8e5ac21a4b467bceb89_10.png)

This is Cogen 3。So if you look at this， IR。

![](img/679125bc73ccd8e5ac21a4b467bceb89_12.png)

The beginning of the function。Is the prologue and all the parameter handling？



![](img/679125bc73ccd8e5ac21a4b467bceb89_14.png)

That's the beginning。And the end is the epilogue and return value。



![](img/679125bc73ccd8e5ac21a4b467bceb89_16.png)

So the part of the compiler you're working on today is the part that does。



![](img/679125bc73ccd8e5ac21a4b467bceb89_18.png)

Arithmetic and branching statements， which are always inside of the function。

So if you just don't compile the function part， then you're not going to have a complete assembly object file。

 so I've given you。The beginning and end of the assembly file。

 and then you'll put your compiled content in between the beginning and end。

Of the compiled dis assembly function。 Does that make sense， that kind of make sense。

So this is the full IR program， you're only compiling this part。You're only compiling this part。

So I've given you the compiled versions of this and this。The stuff that comes before and after。

the content you're compiling。That makes sense？放。Yeah， I mean。

 if you remember when we compile a function， this gets compiled into this assembly code。



![](img/679125bc73ccd8e5ac21a4b467bceb89_20.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_21.png)

Defins the function and gives you a prologue。So you need， if you want to compile this whole thing。

 you'd have to compile all of the constructs in the language。

 this project you're only compiling these constructs。

So I've given you pre compileiled versions of the constructs before and after。The content。Anyway。

 so there's a little explanation here describing me if you want to read it in more detail。

 but I've given you these。

![](img/679125bc73ccd8e5ac21a4b467bceb89_23.png)

There's wrappers。The start is just the beginning of a function， has the。

Function prolong in definition。And the end has。The呃。Has this part， the call to。Print int。

And all the return stuff in epilogue。So it's all this stuff at the bottom of the function。



![](img/679125bc73ccd8e5ac21a4b467bceb89_25.png)

So you can use the wrapper。By just following these instructions， just download it。



![](img/679125bc73ccd8e5ac21a4b467bceb89_27.png)

Unzip on Taret。

![](img/679125bc73ccd8e5ac21a4b467bceb89_29.png)

And then if you follow these directions， this is the template that I gave you， main。ir。

 and then you can just add your code here where it says。

 add your code here and do not change the ones where it says do not change。



![](img/679125bc73ccd8e5ac21a4b467bceb89_31.png)

And then you can just use the make file。2。Build it to build the wrapper。

So if you just follow those directions， it will give you。This rapper。Llf binary。

 and you could just run it and test your program。Test the compiled what you've compiled。



![](img/679125bc73ccd8e5ac21a4b467bceb89_33.png)

And it'll print out whatever you put in the result variable。

So this is what you might see if you try to keep your CoN1 and Cogen2。

 there'll be two definitions of main。So if you just follow these directions。

 you should be able to use the wrappper just。

![](img/679125bc73ccd8e5ac21a4b467bceb89_35.png)

呃。Put your code here after this comment。Put whatever value you want to get printed out into the result variable。



![](img/679125bc73ccd8e5ac21a4b467bceb89_37.png)

And then。Build and compile with your compiler。Yeah。い場を。No。

 so you can compile your program without having to implement CoN1 and Cogen2。



![](img/679125bc73ccd8e5ac21a4b467bceb89_39.png)

So you know， there's like you， 10 or 15 compiler functions in this project。

 you only have to implement three of them， but in order to have a complete program that can be compiled and run。

 you need to implement functions。So in lieu of doing that， I've given you a pre compileiled function。

Andll and these instructions will put your compiled versions of just operations and branching inside of this pre compileiled main executable。



![](img/679125bc73ccd8e5ac21a4b467bceb89_41.png)

So if you want to do this sort of by hand， you can。Follow these instructions。 You can。

Run your compiler。And save it to some file， I call it main。s。

body and then you can use the cat command， what does cat do is remember what cat does？Yeah。

 just prints files it prints the files in order that you give on our command line。

 so it prints the start of the precompiled wrapper， your body that you compiled。

 and the end of the precomped wrapper。And then it redirects them into main dots。

 and then you can compile as usual。Link with IOlibOC because that contains the print function。

So if you want to do this by hand you can you can follow these directions and I think this is what I've done yeah。

 this is what I've done in the self check。 So if you run the self check you'll。



![](img/679125bc73ccd8e5ac21a4b467bceb89_43.png)

Build up this dotS file by hand It's not always too much if we don't completely understand the wrapper。

 but it's just because you're only compiling part of the language。

 I've given you the pre compileiled versions of the rest of the language for a specific。Programs。

 yeah。I don't know what you mean by the argument， what arguments？



![](img/679125bc73ccd8e5ac21a4b467bceb89_45.png)

で？No， there's no parameters。It's just a main function that defineds locals。thatか。Yeah。

 this is given to you and the enterlocals function is given to you in the template。

 in the code template up here。

![](img/679125bc73ccd8e5ac21a4b467bceb89_47.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_48.png)

So don't worry too much about the details of it， you can read over this and try it by hand。

 I suggest just trying it by hand and then you'll kind of get it。

 I think it'll make it easier to get。

![](img/679125bc73ccd8e5ac21a4b467bceb89_50.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_51.png)

嗯。But if you just follow these directions， you should be able to test。

Without having Co Gen1 and Co I2。All right questions on this， so that was a good question。

Any questions on？

![](img/679125bc73ccd8e5ac21a4b467bceb89_53.png)

Branching。We went over last time how branching works。What？嗯。

What assembly instruction corresponds to if go to or what assembly instructions？Okay， jump。

 which so jump。What does Ju do？Sometimes or always。Always。

 so what can we use that for conditional go tos？No。

 you can't because conditional go tos only happen under certain comparison。



![](img/679125bc73ccd8e5ac21a4b467bceb89_55.png)

Recall that this is what an ifF go to looks like。You have a condition and then only if this condition holds。

 do you do the branch？But in the Intel world， a jump， JNP is an unconditional branch。

 so it'll always it'll always branch， yeah， so yeah， what instructions do we use for ifCO2？



![](img/679125bc73ccd8e5ac21a4b467bceb89_57.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_58.png)

タプ。Right， you have compare followed by。AOne of the variations of jump， one of the conditional jumps。

 so this is like a template of what it looks like you populate operas。

 I have RAX and RBX call the compare function with bad indentation here， sorry。

 and then you call the corresponding jump corresponding to the condition。



![](img/679125bc73ccd8e5ac21a4b467bceb89_60.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_61.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_62.png)

いうか？No， no， it'll take any legal opera。

![](img/679125bc73ccd8e5ac21a4b467bceb89_64.png)

It just subtracts the arguments。So this is the it works just like a subtraction。

Except it doesn't save the result of this subtraction。早ず。对。はそい。Yeah。

 so every operation sets some flags in a kind of hidden register。In the machine。

 which is you just have to read the manual that'd like to know this。

 but when you run a subtraction or an addition。Additional。

 the special flags register sets things like was the result zero， was the result negative or greater？

And even though you won't directly look or copy data or process data from that。



![](img/679125bc73ccd8e5ac21a4b467bceb89_66.png)

These these jump opera will look at that flag and determine whether to do the jump or not based on those flags。



![](img/679125bc73ccd8e5ac21a4b467bceb89_68.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_69.png)

And so we use a subtraction， if you remember from last time， the reason we use subtraction。Is。

Because。We're effectively convert converting a comparison like this into。

This because there's a flag register that tells you whether it's zero or not or whether it's greater than zero。

And so we do a subtraction and then effectively compare to zero。

And those flag registers will give you various comparisons to zero of the result of the competition。

It's just how the architecture is designed。

![](img/679125bc73ccd8e5ac21a4b467bceb89_71.png)

All right， other questions on branching？Okay， so that was code Gen3。



![](img/679125bc73ccd8e5ac21a4b467bceb89_73.png)

And you have all the instructions here， hopefully you have the way to test it。



![](img/679125bc73ccd8e5ac21a4b467bceb89_75.png)

I'll be grading it with。Assuming that Cogen N1 and Co N2 aren't there as well。

 maybe i'll do some work to。Pull out your functions， I don't know。

 I don't know yet if I have time to write the the grading trips to do that。

But I'm thinking that maybe another bonus project could be having a complete compiler since know in the course of the class。

 we don't never really get to put together the complete compiler officially but that could be like a bonus project a complete compiler。

 Of course it depends on getting all four of the projects right， but that could be one potential。

Yeah， you just put them all in one contentent file and then you'll see the full compiler。



![](img/679125bc73ccd8e5ac21a4b467bceb89_77.png)

For the full language working。

![](img/679125bc73ccd8e5ac21a4b467bceb89_79.png)

All right， other questions on cogen3， branching， arithmetic。Cogen1， Cogen2。

So I think cogenn1 is graded and then cogen2。Yeah， CoN2 is do this Thursday。

 remember to get something committed。Before that time you if you're not done。

And I'll try to get grades out on Friday for that。

![](img/679125bc73ccd8e5ac21a4b467bceb89_81.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_82.png)

Okay， and I've also put up Cogen4's。YouThe setup is very similar to CoN3。

Except we're going to be doing the pointer。Parts the pointer compilation of pointer operations。

To assembly so this is these are kind of on paper pretty short functions。

 but pointers I know are always confusing a confusing part of C and so the tricky part here will be just getting the concept right in order to do the compilation correctly and then you know testing it yeah。

No， the functions are very short。Just like with actually with codegenN3。

 the functions are generally short too， except if code2， you have to test the。

Which condition you're using， but the functions are really quite short。

But understanding them is the key， and so yeah， that's what we're going to over today is we're going to go over how pointers work。



![](img/679125bc73ccd8e5ac21a4b467bceb89_84.png)

And we're going to see this at the assembly level and I think hopefully。

If you've been confused by pointers and C seeing it at the assembly level will actually， I think。

 make it easier to understand what's going on because you're not working at this kind of high level abstract version of pointers。

 you get to see at the physical level at the machine level what's happening with pointers。

 And they're actually pretty straightforward。 It's just trying to reason it about them can be kind of confusing。

 But once you see the。how this works with the stack frame and with assembly operations。

 I hope and expect that it will be a little easier。

 so who struggles with pointers or who doesn't like pointers？Or wants to admit it。

 who loves pointers and totally gets it okay？So for you you'll see how this actually works at the machine level and actually a little bit why the language is designed the way it is and also why the assembly language is designed the way it is because it's designed around handling pointers。

 so what are pointers to get this started， what are pointers in like C yeah。🤧Yeah， they're addresses。

 theyre addresses， I mean， that's really all they are， they're really addresses。In the C level。

 you can think of them as addresses to variables。But now that we've done some compilation of variables。

 what are variables in。The in the low level what are variables， Yeah yeah， they're also addresses。

 So this is where things get a little confusing because we have several sort of layers of addresses going on。

 but hopefully today we'll go through it slowly and carefully and hopefully you'll have a good understanding or at least a good basis so you can go through yourself how pointers work yeah。

Yeah， yeah， so today I'm going to cover like reference and dereference and next time my plan is to cover pointer assignment。

 but we'll just go you know as we go I think we'll I wanted to leave lots of space and time because pointers are so confusing to make sure we get a good understanding of how they work and then you have to compile them you know it's another kind of meta level of reasoning you have to do because you're not only reasoning about the pointers in the program you're compiling but you have to do this for all programs so it gets you know kind of abstract and a little mindworkping very quickly but so but let's take it concretely。



![](img/679125bc73ccd8e5ac21a4b467bceb89_86.png)

Let me get。The slides up。Yeah。WellOh。Oh， yeah， that's a good question。 I don't know。 I mean。

 pointers are the， I guess the C world name for them。Well， Java， I guess the thing is like Java。

 you don't explicitly work with pointers， everything is a reference or everything is a pointer。

 but I think pointers are explicitly when you explicitly manage them。

 I think that's probably why difference。Yeah， I think so。

 I think that's probably a good way to say it。

![](img/679125bc73ccd8e5ac21a4b467bceb89_88.png)

That makes sense to me。

![](img/679125bc73ccd8e5ac21a4b467bceb89_90.png)

Here we go。

![](img/679125bc73ccd8e5ac21a4b467bceb89_92.png)

Okay。So let's first look at the semantics pointer operations in simple IR。

 they work basically just like C， so we'll do a little review of C as well if you havent don't remember this All right。

 so what does Ampersand do in C？

![](img/679125bc73ccd8e5ac21a4b467bceb89_94.png)

Let's some， yeah。Return。Returns the address to the variable memory now when you're working with C。

You don't really have a notion of what this variable is。 It's just some symbol on the page and you。

You just are told that in the mental model of the machine。

 these variables correspond to addresses somehow now we know how they correspond to addresses。

 so for a local variable like X， where is it stored or how is it stored。In memory， yeah。Yeah。

 that's exactly right， sort of in the stack frame， so this reference， at least for local variables。

 is actually just getting the address of this variable that it's associated with。In the stack frame。

Okay， so now what kind of data type does T1 hold after this assignment？An address， yeah。

 now at the machine level， everything is just binary data。

You can think of them as binary numbers I guess， but it's really just bits， sequences of bits。

So in terms of the if you look at the data， you won't be able to really know for sure whether it's an address or a number。

 it turns out it's really just how the data is used and we'll see at which assembly instructions we use in order to treat something as an address。

But semantically， this T1 is now holding an address。And so what is an address。

 just to make sure we're on the same page， what is an address？Yeah， it's a memory， so memory memory。

 memory is just each memory slot is an a addressed。Memory each bite is given a number。

Some sequential number from zero up to however much memory you have， and that number is the address。

 that number corresponding to the byte in memory is the address， yeah。せ年？

When you say like you have a certain。Yeah， ran basically justice。Call them every。

It's not just the stack， it' also the heap， so Malick。It also stores the program code itself。

 the machine code of the program， and any statically allocated。Yeah， yeah， but it's yeah， yeah。

 it it's used for a lot of different things， but you can think of the stack on the heap as just different ways to manage data with the programming language every one time。

All right， questions on the reference operator。So it gives you the address of。

A variable and then stores it into whatever the left hand side。Yes。Okay， so Dre。

 I call it D referenceence。There's multiple ways to do rereference。

 but I call it dereference and simple IR。So what does a D reference do if I have some variable T1。

 yeah， what does the reference do？Right， so if T1 has some so T1 has some value and this is where things get very confusing because T1 itself。

 the variable is an address， it corresponds to some address and memory。

 but in that location is a number and when you use the dereference operator you're telling，C。

 you're telling the machine to take that number that's in the memory slot associated with T1。

Treat it as an address， follow that address and get the data from that。Addres that's given at T1。

Yeah。Yes， exactly right， and in fact， RBP effectively is a pointer。And when you get an offset。

 you're dereferencing it， you can also think of the RVP as an array because of what is an array。

 an array is just a pointer， and when you do the index。

 it's just adding the offset to that pointer and then dereferencing。All right， questions on dereence。

So we don't have multiple pointers in this language。

 but you could emulate them with several temporary variables。

 so C has also multiple layers of pointer which makes things even more confusing。

 but you can always break it down into individual pointers。Double point or， triple1， yeah。Yeah。

You can。But you can't express a triple pointer。In this language。You would have to be reference。

You'd have to do the individual dereference operations yourself one at a time。For each layer， yeah。

Yeah， yeah， and that's what's got to happen at the assembly level， the assembly level。

 there is no assembly instruction for tripleD reference for me， there's only a single de reference。

Anyか。Would automatically。T pointer。Yep， yep， and and it'll unwrap each dereference one at a time。

 one instruction at a time in the same way that if you have a long mathematical expression with like you know eight different arithmetic arithmetic operations。

 the compile of the assembly does not have an instruction for eight operations at the same time well。

Outside of like， I don't know， like single instruction， multi datata or vector operations。

 but in kind of the classic ALU， it's one arithmetic operation at a time。

And so you'd have to use temporary variables to help you do that。Okay， questions on dereference。

 the meaning of dereference。Okay， so and then we have what I call de referenceence assignment。

 so I just needed to make a distinction between when we're loading。

A value using a de referencefer when restoring it。 So what's the difference here。

 What does it mean to store or have a de referenceence assignment。Yeah。はこい。あか。あそのはド。Yeah。

 so in the same way in the previous one where T1， which is a variable， something stored in memory。



![](img/679125bc73ccd8e5ac21a4b467bceb89_96.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_97.png)

It's contents or an address。And then when we assign to the dereference of that address。

 we don't assign to the memory associated with T1 itself， we look up the value of T1。

 that value is an address。And then we go to that memory location and that's where we store whatever's on the right hand side。

So this is a constant so will just store 11 into whatever address T1 holds。

So I'll show this I'll diagram this all out， but this is where things get confusing because variables themselves are in a sense like a reference。

 I mean they are a reference， they map to some memory location and so what gets confusing is that you have a map to a memory location holding a memory location。

 that's where things get confusing and then of course if we have a variable on the right hand side here we're going to have to load that value for memory and then store it into the dereference。

Address from T1。All right， questions on just the semantics， kind of high level semantics to this。

 I'll go through， we'll diagram all this together， but the questions on this。Yeah。あじほ。Yeah。

 so as I mentioned before， the machine will only handle a single pointer at a time for you。

 so if you had a double pointer you would just do each dereference one at a time。

 so youd first dereference the first pointer， sort into a temporary and then dereference that temporary variable and you can do that however many times you like。

So just like with arithmetic operations， you can think of multiple references as being broken down into individual operations at the。

Machine level。Okay， so let's do a little test， here's a complete example using all three。

 I have a single function here， I set x to8， y to9。All right， so when I run t equals ampersand x。

 what's the value of t1？Yeah， the address of X。And now I assign the dereference of T1 to T2。

 so what's the value of T2？8， good because T1 holds the address of x。

 and when I dereence that address， I get the value of whatever was in that address。Good， okay。

 so star T1 and x are like kind of equivalences， they're aliases。The start。In a sense， yeah。

 it's like you get the reference and then you dereence the reference， yeah， you think yeah。

 you could think of it that way。All right， so now。What does this do， I de reference a s T1 yeah。

AhSo x equals 11， y does x equals 11 because T1 holds the address of x。

 and I do a dereference assignment to that address。

So even though I don't have any explicit operation on x here because T1 is alias to x， or that is。

 it has the same address as x。I've now assigned。X to 11。It's one way to think of it。

 you can think of it as boxes or arrows pointing to them。Yeah， several visualizations。

 I'll do the kind of arrow based one because I'll show you the stack frame and then if you sort of reason on this at like the individual step level。

 it'll make it easier， you don't have to kind of think， try to think conceptually， okay。

 what's the value of x， you can just step through one operation at a time。

And hopefully get the right answer that way。All right。

 questions on this complete example showing all three。What's that。Yeah， good question。

 what does it return， so this assigned x to 11。😊，This assigned T3 to 11。

 It's not touching the value of x。 And then， yes， this returns 11。 Yeah。

 I forgot to answer the question。 Yeah， it returns 11。6。Okay， so let's review stack allocation。

 so how our functional local variables start at runtime。



![](img/679125bc73ccd8e5ac21a4b467bceb89_99.png)

On the stack。 Okay， so let's draw the stack for。

![](img/679125bc73ccd8e5ac21a4b467bceb89_101.png)

This example。All right， so I'm going to try to do this in as much。Detail。As possible。

So let's all right， so what goes on what's the first thing in a stack frame？或者。

Even before we turn to dress。Face point is a register， what does the caller add to the stack？

Prameterters， yeah， there's actually parameters first。And then the return address。

And what's the next thing on the stack frame？There's something else for us， yeah。The old base one。

 yeah， pointer to the old， so I'll just call that old。2比P。And if I've set this up correctly。

 the current RBP will point to。The stack frame entry that holds the old RVP， yeah。ぜひあ？必要や。Okay。

 that's a good question， so good point， good point， so for this example there are only two prouders。

 so you're right， the first thing， okay， good point， good point。

So I was conflating asking in general versus asking specifically， so you're right。

 the first thing in this stack frame would be the return address。

 you are right about that for this example， I thought I was asking a trick question but I wasn't so this yeah。

 you're right， this example doesn't have them so forget about parameters for this one。Okay。

 and then what's next on the stack？Yeah， the local ours。So conceptually。There's。

A slot for each of these local barss that I probably made way too many。So let's give these。

Physical seeming addresses here。 I'm going to， let's just start at like。

Let me move this aside for a second。Let's give these。Physical seeming addresses。

 so they wouldn't be this low。In。Memory space unlike like a real machine。But here。

If I can add eight properly。Okay， so let's say this。And of course。

 I did this wrong because it actually counts down。It counts down from high memory addresses。So' it。

 let's do it this way。All right， did I do my math right？不则。table yeah， that's why I like computers。

 I don't have to do math。😊，Or calculation all right， so what's the value of RVP？80 address 80。

 so these are like decimal addresses。So RVP holds the literal binary representation of the integer。

80 to represent。I mean。There's nothing enforcing what it represents。

 but we as a compiler writer are using it to represent the memory location that's addressed。80。

 decimal 80。estQuestions on this so far。There's a little slightly more concrete view of the stack frames。

Okay， so this is our stack frame layout refresher and you know these。Symbols here。

 these are not stored anywhere。😡，You know， without except for debugging symbols。

 these aren't stored anywhere， don't have to be stored anywhere in the assembly file these are just。

The mappings that the compiler has， actually， what mappings does the compiler have at runtime for A？

And B and C， et cetera。So what does the compiler store for these yeah？

AsSo as offsets from the base pointer。So let's call this。A symbol。

And I'll put the offset here for each of these， so this is offset。Negative a。Beegative 16。

Negative 24， let's see， is this what I had， I want to make sure this lines up with what。

I put in the actual examples。Negative 24， okay。I think it' 24。Negative 32。Negative 40。

Negative 48 and negative。54。All right， questions about the yeah。that这テワ。your apple。This says T1。

I just have very bad handwriting。So this is the actual。Address and memory。

For a specific run of our program， yeah。Yeah，Yes， did I mess something up， Yes， you're right。

 you're right。Thank you。Okay， questions on this， so this information here， this is what。

The compiler is holding， and it's going to use this to generate instructions that。

Do stores and loads。As offset for RVP， whenever we have just regular variable assignments and variable usages。

These are not pointers per se。These are just what the variable usage is without pointers get mapped to。

All right questions on the setup here。Okay， so let's take a look at， okay， oh yeah。

 I have a refresher here for assignment， so how does assignment work？



![](img/679125bc73ccd8e5ac21a4b467bceb89_103.png)

In assembly， if I've got， say。

![](img/679125bc73ccd8e5ac21a4b467bceb89_105.png)

Let's say I just have an assignment like x equals seven and let me。Get rid of the highlighting。

If I x equals 7， what happens to the memory？Okay， so's yeah， that's how I did it so I can move it in。

A temporary register and then we move whatever that value is into。

 no remember how we did the assembly to store into a variable source specifically into the variable x。

Okay。Yeah， negative 24 RVP。 Yeah， exactly right。 So this is what we used this。Move instruction。

 This is how we。Stored whatever the value of Rx is into。

Whatever the runtime address of x is going to be， we don't have to know what this address is。

 we just have to just use RVP and it all set from it 24 yeah。I want to make sure you also like。

Absolutely， yeah， yeah， so the prologue， I'm assuming this is assuming that the prologue has run an allocated space for it。

So because the runtime value of RVP is 80。This 80 minus 24， if my math is right， will work out to be。

Addres 56。So this is why we don't need to know these addresses at compile time。

 we only need to know the offset and maintain RVP。Every time we have a function called。

 maintain it correctly。All right， questions on this。All right。

 so that's how normal variable assignment works。

![](img/679125bc73ccd8e5ac21a4b467bceb89_107.png)

Now let's make things more confusing by looking at how we do assignment from。

Or should we look at assignment from a variable first， would that be helpful？Okay。

 let's look at assignment from a variable。So let's say we have。Let's do T3。Equals x。So how would we？

Load from x， yeah。Exactly， so we'd use this。Yeah， exactly， we use the same register， indirect offset。

 whatever whatever。The official name for it is you'd use this same upperand。

Which gives you the offset of negative 24 from RVP。Save it into some temporary variable。

And then do the same thing we did before to store this into whatever T3 is。

 So T3 here is negative 56 from。The base pointer。Add well off， we've got。An assignment of x's value。

 there x's value。Okay， so I made it seven here。And then I moved whatever this value was。

I addressed it using。This register indirect offset from RVP and stored it into RAX and then stored that value into。

This offset negative 56 from the base pointer。Making this step。Questions on。

Kind of normal variable assignment。All right， so now let's make this。Yeah， yeah。Look with the temper。

You can choose， you can choose， I tried to make it simple by having everything the RAX and RBX。

 even though RBX is like technically call save， which makes it a little more annoying。

 but yeah you can use for these move operations they'll take any register。Okay。

 so let's take a look at now。How we。Get a reference。2。A variable。All right。In this example。

 what is the address of X？56 do we know that address at compile time？What do we know at compile time？

Yeah， thank you were first。セト。We know it's offset from the base pointer。What else well。

 we don't actually know the address the base pointer。But what do we know about the base pointer？Well。

 it'll change during run time， yeah。No， well， the base pointer is it's just a register。Yeah。Well。

 yeah， I mean actually that is actually correct。Always pointing to the stack rate。

It's always pointing to the address of whatever the stack frame is。

And we designed RVP to point to the stack frame entry， the middle of the stack frame。

 the stack frame entry that holds the old base pointer。

 So the point is that RVP always points to some address where。

These fixed offsets will give us the variables。For our functional local variables。

So we know that RVP holds the address。That points to the stack frame， and we know the offsets。

 we know the actual concrete numbers of the offsets。

So the trick is that if we want to get the address of x。We can use。

The fact that we know RVP is going to hold a pointer to the stack frame and the fact that we know the offset of x to compute。

 in order to generate code that computes。The address of X。Atron time。With me so far。

So we're going to generate code。That we know， because we've guaranteed RVP points to the stack frame。

 we're going to generate code that we know will compute the address of X。

 even though we can't know in general the address of X at compile time。

We can use what we do know that RBP will always point to the stack point or stack frame。

 and we know the fixed offset of x we'll use that to generate code。

That will compute the pointer for us， the pointer address on our behalf at runtime。Makes sense。

 so this is the tricky part about compiles is that。

You won't be able to in general write a compiler that computes the answer for you。

So what you'll do is you'll use some clever logic to generate code that will compute it for you。

At runtime， so there's no。Plus symbol and assembly。

 but we can generate code that we know will compute the arithmetic that our developer asked us to compute in our language。



![](img/679125bc73ccd8e5ac21a4b467bceb89_109.png)

Okay， so how this let's see the steps for this to work。



![](img/679125bc73ccd8e5ac21a4b467bceb89_111.png)

We'll start with RVP because we've generated code using a convention that will ensure that RVP always holds a pointer to the stack frame。

That so RBP holds an address。We'll generate code that adds the offset of our variable to RVP。

 and then we'll just save that result because as soon as we've added the offset to whatever RVP is。

 we've got the pointer， we've got the address of our variable。



![](img/679125bc73ccd8e5ac21a4b467bceb89_113.png)

Okay， let's see how this works in our diagram。So we'll just use informal assembly here。

🤧So were the steps， we take RBP。And。Let's get rid of this， so we take whatever RBP is。

So the kind of like pointer to x is whatever RPP is plus whatever x's offset is I can say。Syim tab。

 I'll just say offset set of X。Yeah， it will end up being subtraction， yeah。

So what's the offset of x in our table here？Negative 24。

 and what's RVP in our current execution of the program？80 so it'll be 80 plus negative of 24。

 what do we get？56。And is that indeed the address of x？It is。It is the F ofS。

So our goal is to generate code that will compute this for us for whatever our variable is。

So let's first look at what the assembly will be for。This offset。

So well we'll save RVP into a temporary register because we don't want to blow it away。

 We don't you know remember arithmetic in the assembly world or in the Intel world only two registers so you're going to overwrite one of the registers so we're going to save the value of RVP into RAX so now。

RX。呃。I guess， equals。RBP。And then how do we do addition， well， we know how to do this right。

 but is the ad instruction。So what's the ad instruction look like here？Yeah。So it'll be RAX plus。

Equals 24， how do we express that in assembly？Yeah。Or sorry， add the offset。Good， so yeah。

 this is the remember， the second parameter is。The left upper end and the destination。

So this is how we express RAX plus equals negative of 24。In the entire world。

 and so now RAX holds or will hold that runtime it will hold the pointer to x。Yeah。エエ三ム二エ。でミリ。Yeah。

 yeah， because these offsets， at least in our language。

 we' we design it so that the offsets are fixed from RVP and those fixed offsets are just numbers and we can use an immediate。

To compute that。

![](img/679125bc73ccd8e5ac21a4b467bceb89_115.png)

Okay， so now RAX holds our pointer。Our address。So what do we need to do to finish up this？

Reference assignment。Save it， save it to where。T1， good， so how do we save RAX？T1。Yeah。いぱに。Good。

 negative 40 RBP because our offset of T1 is negative 40。And if you just remember this as a kind of。

Iiom， this is how you。This opera here is how you store and load to variables。 They're offset。

From RVP。Yeah。You mean the negative 40 RVP？It's just the design of Intel。 So Intel is like ci。

 you know complex instruction set versus risk， reduced instruction set。

 It just gives you the sort of higher level assembly operations that'll do multiple steps for you。

 There are other architectures where that's not the case where you'd have to。

I think actually I haven't done much arm compiling， but I think you'd have。

 I don't know if they have register offset， I'm actually not sure。

 but there are you can imagine other architectures where you don't have this。

complicated instructions that can do many operations for you。

 and actually under the hood I think Intel is using microcode。

 a kind of risk architecture under the hood and then it's translating or interpreting your high level assembly instructions into that。

All right questions on this so far。So that's review。Our goal here， remember our goal here was to。

Aside the。Address of X。The T1， that's what the reference operator does in C。



![](img/679125bc73ccd8e5ac21a4b467bceb89_117.png)

And in our runtime here our。Actual address of Act 56。

But depending on when your function is called or how often it's called。

 this address may not be the same every time you run the program。But。

What will be the same is that RVP。Assuming that the compiler is correct and no attacks。

 RBP will always hold a pointer to whatever the current stack frame is for the function。

And we also know that these all sets are fixed because we designed the compiler that way to use a fixed offset for every variable。

So in order to assign this address， 56 to T1。We can generate code。

That will compute the address for us at runtime。 And that code is this。 It will take RVP。

And so add the offset of x to it。Questions， questions about this。Yeah。別に。Another。Would it just work？

😔，Another program。You mean like a different process or the same process。Oh yeah， yeah。

 you don't have guarantees that yeah， the function has the same address across processes。I mean。

 the data across processes。これ。Well， there's， I mean， I guess if well。

 so for one thing is if this function were called multiple times。Or yeah。

 if they were called in different places。Then even in the same program。

 X may not have the same address for every call imagine factorial， you have factorial。

 the address changes the stack name address changes for every call。五十才。Address in memory。

you wanted to。Oh， so yeah。 So this is the virtualization of the memory。 Yeah。

 this is what you learn about otherwise。 So processes have their own。Virtual address space。

 basically starting from zero。And so without additional help from the kernelel， you can't even read。

The memory you're not supposed to be able to read the memory from other processes。

 This is process isolation。 Now， there are you know， vulnerabilities where。You can subvert that。

 but that's one of the protections that the kernel provides is isolation between processes。

 so even if you knew the address， you should not be able to read it。

 you'd end up reading your own address spaces address。U。

Now there are kernel features like memory mapping， what is it memory mapped？

Canmer remember on what's called there's like oh shared memory， there's shared memory。

 so you can allocate a space of memory that's shared between two processes and I think。

They'll have the same if I'm not mistaken， I think they'll have the same。



![](img/679125bc73ccd8e5ac21a4b467bceb89_119.png)

Address。So there's a function called MMap。

![](img/679125bc73ccd8e5ac21a4b467bceb89_121.png)

嗯。So I am not much of a Colel hacker， but I think you can share。



![](img/679125bc73ccd8e5ac21a4b467bceb89_123.png)

Yeah， you can share these。Pretty sure the addresses will be the same across them。嗯。So this， yeah。

 this creates lots of headaches if you're trying to do cross now if you're doing multi threading。

 it's easier because of the same process， but across processes。



![](img/679125bc73ccd8e5ac21a4b467bceb89_125.png)

![](img/679125bc73ccd8e5ac21a4b467bceb89_126.png)

Yeah， pointers will。

![](img/679125bc73ccd8e5ac21a4b467bceb89_128.png)

Cause issues if they're not in the same address memory。This also causes issues with persistence。

 like trying to store data to disk。If you have some complicated data structure and it uses pointers。

 well， you can't just store that to disk because those pointers may not be the same addresses as the next time you run the program。

 so you have to serialize it。There's some。Modern hardware called persistent memory。

 which is basically turning your RA， the RA bus is actually accessing solidli day drive。

So instead of RA being flushed。As soon as you take the signal off of it。

 it's persistent memory and pointers cause a lot of headaches for that work。

 I think is actually current research and how to deal with this stuff。But yeah。

 that's a good question so across processes， the kind of without any other functionality processes have isolation and that they should not be able to read memory from other processes and they have their own memory addressing。

 they have their own virtual memory space。So that's a good question。Take an OS class。

 hopefully they'll go deeper into that more than I know about operating system sorry operating systems。



![](img/679125bc73ccd8e5ac21a4b467bceb89_130.png)

But yeah， good question。All right， any other questions on？Taking the pointer， taking a pointer， yeah。

Just。

![](img/679125bc73ccd8e5ac21a4b467bceb89_132.png)

So。找一个。Yeah。Yes， we have destroyed RAX， we've updated RAX。

 but RAX is just think of it as a temporary register， it''s a temporary value。RBP holds， yeah。

 RBP holds this pointer， holds 80。Yeah， we're not updating RVP， that would be bad。

Just like do the last move。Ah okay， you mean this command。Okay， what's the difference。

 so this is where the point， this is why。Doing this at the machine level will hopefully make you understand pointers more。

 and it's also why it's so confusing。Because variables themselves。

 like you can think of variables as references， as pointers that the compiler manages for you。

So in some sense， x is being translated or x is being like this offset is actually a kind of is a relative pointer。

So in the compiler， it's actually holding an address。 It's a relative address to RVP。

 but it's holding a pointer。 So any operation you do to a variable is， in some sense。

 using a pointer like thing because RBP is RVP is a pointer。 It's an address。

So this step here is just。So remember， this is register indirect。

 This is saying store any address given by this opera brand and that address。Is here 20 with that。

Reencing。Yeah， I guess that's one wide way to say it。😊，呃。Yeah。

 if if that helps syntax is not the same as actually。Yes， that's right， that's right。 Yeah。

 using this syntax is。Intel's way of。Doing I mean， it is doing the same computation as this。

It is doing the same computation as this。In some sense， because I mean。

 it's not the exact same because it's 24 plus 40。But these two instructions are doing effectively the same thing as what this operaand is doing。

The difference is， is that this opera end is like a shorthand for saying do this arithmetic for me and then store in that location for me。

So in that sense， it is like a pointer dereference because it's you're telling the machine here's an address I'd like you to update actually all stores are really like pointers because you' given an address if did。

twenty4？RBP。valueで。Exactly， exactly， so let's make this more concrete。

 so I think in my program what did this have originally in my program eight I think。So x hold eight。

And then after I do this computation。So RAX holds 80 because that's RVP and then subtract negative 24。

 that's 56， and then we store that value in T1。So now T1 holds。56。So the question was what if we had。

 what if we had tried to be clever and be like， all right， well， I mean， you can't actually do this。

In。The intel world， you can't do to a load in the store at the same time。 But let's pretend we could。

 Let's pretend we could。Do a store in the load at the same time。What would the result， I mean。

 we'd have to use it RAX you as a temporary rich what would the results？Of。This speed。

 so we read what would go into T1 now when we do this， yeah。Eight， yeah， good， eight what happen。



![](img/679125bc73ccd8e5ac21a4b467bceb89_134.png)

And so this is equivalent to T1 equals x。Whereas this one is T1 equals。The address of x。

And that's a good question because this shows exactly the distinction between。Intel's， you know。

 sort of fancy。Dereferencing that it does for you in order to handle variables。

 which variables themselves are pointers， so that's why in some sense it is kind of like a double pointer。

Because X itself is like a pointer because it's an address or it's an address。

 maybe it's not a pointer， it's an address。But then we're taking the address of this。

We're getting the literal address of that thing and storing it into another variable in that store。

Is also using a pointer like thing， a reference like thing in order to do the store。

So good question at the result here。T1。Is 8 the value of x。 So you know。

 one way to distinguish here say the value of x means the memory value at that location versus the。

Addres。Of X， which is。RBP plus the offset， the address of the memory location。So this is。

 this is why this is so confusing。 So one thing that makes pointers different from variables is that you can think of all variables as references because they are。

 they map to some location and memory。 And anytime you have an address， an address is。

It's not a pointer， but it is a。Reference to a memory location。

What makes something a pointer and what distinguishes， say negative 40 RBP from。

From T1 holding the address of X。Is what makes something into a pointer is that the value。

Stored in the memory is intended to be used。😡，As a reference。

Is that more confusing that's more or less confusing？So okay。

 so one of the main problems here is that just looking at memory。There's no general way to say， well。

 this is an address versus this is an integer， or this is an integer is an address。

 it's all just binary data。What makes this？An address is that some operation is going to use it as an address。



![](img/679125bc73ccd8e5ac21a4b467bceb89_136.png)

So we've used this reference operator here。And that's what makes this an address。

 and as soon as we put an address as data。That's when we have a pointer。

When we use an address as data。That's where a pointer comes from。

 so that's why this x here is not literally a pointer。In C。

 but why T1 is a pointer because t1s value。Is an address whereas x in the compiler， yes， it uses。

References in order to access the memory associated with it。

But the data that's stored at that address is not intended to be used as an address。

 whereas the data stored at T1。Is intended to be used as an address。As given by the operations。

So to like show that this is a pointer we can draw an arrow here from this data to say。

This data is intended to mean。An address in memory。Yeah。

Not at the machine level because it's just storing binary data。How一个。Yeah， exactly， yeah。

 data type is really an annotation of your intention about using it and in languages that are。

I can't remember the definitions here untyped like a simple IR。

 you don't make any declarations explicitly about what the data type is going to be used for。

 so you can think of a type kind of in the formal definition of a type is a set of values and a set of operations on those values。

 so a of operations set data a set of values themselves。I mean， in the math world。

 that is like a type， you have like the set of integers， but in the computing world。

 a type is the data， the type， the set of values and the operations on those values。

And so that's what a type checker uses in order to validate whether you use the correct operations on the data and whether you're using them correctly。

 but strictly speaking at the hardware level， you just have bits。And the only reason that this 56。Is。

An address versus an integer is because we loaded it from。A pointer reference。

 we loaded it from RBP plus the offset。And when we go to D reference， I mean。

 this is why you have problems with pointers and actually Y C。

We'll do some checking of pointers for you， but you can subvert that and don't have ready to be go it in prior classes I would show how we can。

Make the compiler turn an integer into a pointer and vice versa， and you can do pointarrith。

tic can see， limited amounts of point。This is also the source of vulnerabilities。

 like stackming attacks。Where we blow away addresses with the data that we'd like， you know。

 we violate the whole stack frame invariant that we've tried so hard to make the compiler respect。

How that that answer， does that answer your question？clear， questions on this， questions on this。

Yeah。Second。Tey registers。So so variables， you can think of variables as memory locations。

That's why this is confusing because memory locations also have addresses。

And so when a variable is not a pointer。You never need to think about the address。

 the compiler is managing the addresses for you。And when you don't have pointers。

 the value that's stored at that memory location is never intended to be used as an address。

When you have a pointer， pointer is when the values at these variable locations。

 at these memory locations are intended to be used as addresses。

That's what makes pointers difference from variables。That's also why languages， all languages。

 I guess technically all languages have references if they're working on a state machine like this。

But they may not have pointers。Because pointers are when the data at a variable is explicitly meant to be an address。

Questions on this， questions。owOkay， let's do D reference。Finish this up with your reference。Okay。

 we already went through this。All right， so let's look at dereencing。All right， so how do we？Load。

A value from an address given in a register。Yeah。I read Stern。Okay， it's similar to offset， yeah。

 yeah。我せこ。Memory honor。なでいう。咁で you。对吧。그변이 없어。Okay， so we're circling around something see。

 we're going to have to get this value。This is the value that we want。Did I show the yeah。

 so what we so let's say we want to。Get the we want to dereence T1， so we want to get so what value。

 what value will T2 hold after we do this assignment？E， because we dereence T1。

 which means we look at the value of T1， T1 is meant to be an address。

And we don't get the value of T1， but we take whatever its value is， and we look that up in RAM。

And get the value of that address， which is eight。So there's。

A addressing an Intel that will look very familiar。This is effectively how you do a dereference。

In Intel， now， you already saw the more sophisticated version of this， the offset version of this。

 which is like an array。This， putting parentheses around a register is basically just doing a dereference for you。

It's saying don't copy the data at RAX。But go to the address that RAX holds and get the data from that address。

Questions on that， so it's very much the same that we used for our whole variable lookup。

 but we're going to use it for pointer theoretical reference yeah。RBX。No， well， no。

 I haven't said RX， I just wanted to show the operation here， so let's go over。

What this will look like， is it's slightly more complicated。

So we're going to get the value of the variable， so in this case we're going to get 56。

Actually get the value of the variable。Yeah， we're going to get 56。

 we're going to get the value of this variable。And then we're going to get the value of the memory at that address。

And then we're going to。That doesn't look right。Why did I make that so complicated， All right。

 let me I'll just go over what exactly you guys said， So we're going to get this address。From T1。

We're going to。Use this register indirect addressing to get the value at that address。

And then we're going to store that result in you know the variable that we were trying to store so what was my。

So T2 equals star T1。This is what we're trying to compile， so what we need to do is。

Get the value of T1。Load the value of the。Address that T1 holds。And then store that value。Into T2。

So let's start with storing the value into T2。 So let's assume。



![](img/679125bc73ccd8e5ac21a4b467bceb89_138.png)

So this is what the code。It's going to look like all right yeah， just let's go one by one。

 let me just show this address here for the sake of time。So。This is how we load the value of T1。

 just like before。So this is the same as we've seen for loading the value of T1。

 it has offset negative 40 from RBP。So this is the instruction we use to load the value of。

T1 into RA X。 So now RA X holds what value。那。RX。It holds 56， it holds the value。

So this is how we load the value of T1， so now RAX holds。56。So， let me。Put a note here。

And then this is how we take。RAAX and treat it as an address instead of just its data。

 if we didn't have these parentheses， RBX would just hold 56， would just copy RAX to RBX。

The parentheses indicate that you do a look up to memory of whatever addresses is in 56。

So what value do we get from parentheses RAX？We get a， so RAX is 56。Prenheses， RAX。Is 8。

So parentheses RX is effectively the star T1 in assembly。 So this gives us the value our of。

The address， the value of the memory at address 56， and it stores it into RBX。

So we use another temporary variable here to hold。Our value。

And then this last instruction is just storing T2 just like we saw before。

 so this is so if we had just if we skippped this line here and just had move you negative 40 RBP into RAX and then moved RAX into 40。

 that would just be a regular assignment between two variables。Here instead。

 we're first taking the value of the variable。And then using this register indirect load to get the value of memory。

The memory location that RX holds。And then storing that。

Into so the offset is pretty much adding negative 4 to。So is there an implied zero vi？Yeah， yeah。

 yeah exactly yeah， so this is no offset， it's just whatever RAX value is。

 go to that memory location， so RAX holds 56 right now。So this says。

 go to address 56 and load its value。I think so， yeah， this should be the same thing。So this here。

Prirenheses RAX because RAX。It's 56 right now。That parentheses is saying。

Go to address 56 and load its value， which is。And sorted RBX。

So this is the key difference between assigning。T1 to T2 versus aing star T1 to T2。

 This is the star part。

![](img/679125bc73ccd8e5ac21a4b467bceb89_140.png)

The parent is the start part and we need an extra register。

To hold the address and then hold the value。It doesnn't matter what they are。分性会。Yes， exactly。 Yeah。

 yeah。All right， questions on this before we go。All right。

 so take some time to wrap your head around in a little bit， look at this diagram。

 I'll put the diagram up， put the video up， and then yeah we actually got through all everything that I was going to cover today。

 so we'll go over the reference assignment next time。All right， everyone， a good， have a good one。たか。



![](img/679125bc73ccd8e5ac21a4b467bceb89_142.png)
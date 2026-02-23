# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P6：-06-Rust.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video， we are going to study rust， which we are going to use as the safe foundation for concurrent programming。

 so it provides a way to abstract all the unset within a safe API。

 and we are going to use how to do that。

![](img/0738fc9de7947304e392d4eb5665765f_1.png)

So first things first， what is rust rust is a safe systems for language in a sense that it provides a programmer to achieve safety。

 absolute safety without worrying about all the implementation details。

 so the motivation here is that。

![](img/0738fc9de7947304e392d4eb5665765f_3.png)

Basically， C++ is unsafe。 That's the reason why Ross came。

So the motivation is achieving safety and control at the same time here the safety means that if you write a program in rust and it satisfy some condition。

 then it is guaranteed that when you compile the program into assembly。

 the assembly program should not go wrong， it is guaranteed by the compiler and the type systems。

At the same time， it achieves control in the sense that it supports all the low level features that are necessary in programming for example operating systems。

 So in our laboratory， we are also building an operating system on top of this rust so it。



![](img/0738fc9de7947304e392d4eb5665765f_5.png)

It supports operating systems or database management systems or all the other kinds of systems programming。



![](img/0738fc9de7947304e392d4eb5665765f_7.png)

Because he supports all the features。To this end， the prior art should be CN andC+ plus。

 but they are very much unsafe because as we discussed in the previous video。

 you can easily shoot your foot by， for example， licking a pointer inside a a spin lock。

CNC++ cannot detect such such an unsafe user of API。 So that's the main difference。

 key difference between CNNC++ and rust。So as I said。

 the worst is best fit for this course because its ownership and lifetime captures the essence sense of concurrency。



![](img/0738fc9de7947304e392d4eb5665765f_9.png)

Recall that concurrency is fundamentally about shared meable states and in order to reason about these shared meable states。

 a notion of ownership and lifetime is very much useful because they are fundamentally about sharing safely sharing resources so RuT provides such a tool and we are going to use it to program concurrency。



![](img/0738fc9de7947304e392d4eb5665765f_11.png)

![](img/0738fc9de7947304e392d4eb5665765f_12.png)

So here are a few assignments you I want you to read at the book， which is the book about Ro。

And the book is consisting about about 212。No， 220 chapters and each chapter is not so long and after reading all the book。

 the final chapter is about building a parallel web server and Ho 1 is about extending these parallel web server and implementing Thr tools and caches and controversy C handlers。



![](img/0738fc9de7947304e392d4eb5665765f_14.png)

![](img/0738fc9de7947304e392d4eb5665765f_15.png)

So that is about the homework one， and in order to do homework one。

 you probably should read all the entirety of the book。And it， it started long。

 So please read the book。And the second reading assignment would be reading a book that is named RosS by example that enumerates many examples in RoOSS programs。

 and these examples lets you know， lets you have a hundred0 experiences on the RoOS compilers and RoOS typepe system。

They are very much。嗯。More practical than the book because it contains all the examples。

 so please read the book。And there will be also programming assignment throughout this course。

 I expect there will be five or six assignments in this course。

And all the programming assignments will be in rustOST。

 so you need to write down some Ro programs for assignments。

So please set up your programming environment and the provide server or your own machine。 So。

 so we support only even to。呃。20 do04。 and any machine with that U to that version is okay。

 but probably you want to use machines with more many cores。

 So that's the reason why we provide servers。

![](img/0738fc9de7947304e392d4eb5665765f_17.png)

Anyway， instead a programming environment and make sure that you can compile， for example， a CrossBm。

 or for example， you can compile the homeworkO。So if you can compile and run the web server。

 that will be probably okay。Okay， now let's start looking at examples here is an example that shows the power of the rust。

😊。

![](img/0738fc9de7947304e392d4eb5665765f_19.png)

So here is a function that is named main。And in the main function。

 it is at first declaring a vector of size 3。That is consisting of 1，2， and 3。

So V is a vector of size 3。Now， P is the pointer to the the the first element in inside this vector。

 So P gets the pointer。And now you're going to push4 to the end of the vector。So now vector becomes1。

2，3， and 4。And after that， you are going to print the value inside P。V1。Coown and the value。

 which is inside this pointer。Okay， so far it good。But。As many of you are letting know。

 it is very much unsafe。The reason is that the push operation may relocate the underlying vector。

 The vector is allocated inside a hip。And inside the hip memory， one，2， three are stored。

But if you push4， it may be the case that the size is the hip memory can no longer contain all the values because the hip memory is size 3。

So you need to relocate。 in other words， you need to allocatecate new hip memory that has a size at least bigger than three。

So and copy all the values from the old HB to the new hip。And if it happens。

 the pointer here pointer to the first element of V may be invalidated。

Because the underlying vector is relocated。That's the reason why it can be unsafe。

 It can be de reference to an unused memory area which may invoke a page handlezr。So you can。

 you can just click click this link to go to the example that you can play with on your browser。

 So if you click on this link， there is a IDE that is running inside your browser。😊。

And it will compile this file， and then you can execute it when you can see the compile error messages as well。

Okay， so。In C++， this code can be compiled。Yeah， it is bad code， but anyway。

 C++ allows you to do that because it cannot detect the errors or box in this program。

On the other hand， it is not compiled in rust because of this message。

 So it says this and then reject this program cannot borrow V asmable。Here at this line。

 V push cannot borrow V as mirrorable because it is already borrowed as immutable so。

Is he saying that， oh， V is immutably borrowed here at this line when you are getting a pointer。

And then。Because of that， you cannot borrow V in this line mutably because it is already imably borrowed。

So it is the reason why Ross rejects this example。So let me explain this bit a little bit more。



![](img/0738fc9de7947304e392d4eb5665765f_21.png)

V here is the owner of the vector。 Ve is inside the hip and is owned by this A V。 V is the。Name。

 and it is the owner of the vector。And here， P is imly borrowing the vector because you're going to。

Reference to the first element of V here。 And this P is later read here。In order to print it。

And from this line to this line， the value the vector v is borrowed by P。

P immutably borrows the vector from the second to the fourth line。

And at the same time we that push V here this line。

 this line is mutably borrowing the vector as well because you are going to push the value。

 so you need to borrow it， but at this time you need to mutably borrow it because you are going to mutate it by pushing the value4。

😊，Now it is the compilers said， oh， there is a conflict between the two operations or two agents because the typey Shaicker detects that there are shared meurable accesses。

P and with push， they are she Mu accesses。So P is also accessing the vector， I borrowing the vector。

 and this P Vta push is also borrowing the vector。And one of them is mutable。

 so that's precisely the reason why it might go wrong。You cannot guarantee that P is good。

 P is a good reference because V can be changed in between。So as a result at this time。

 peak cannot be read safely。Because it may be the case that we may be vastly changed in between these two。

Okay， so far second。

![](img/0738fc9de7947304e392d4eb5665765f_23.png)

Then how to detect such a conflict， such a shared removal accesses。 So how to。

Systematicically detect those kind of conflict in rusts。

It is by calculating what is called a lifetime。So here here there are onerous or bs of the vector。

 VPN， the line that is executing withta push。Vace lifetime is from line 1，2，5，1，2，3，4，5。

 and peace lifetime is 3，4 and 5。And with that precious lifetime is just line 4。

 The lifetime is basically the range in which the agent is living。

V lives lives from here to here and P lives from here to here， and V that push lives us at this line。

 that is basically lifetime。And you can list up the pairs of overlapping lifetimes。 for example。

 V and P are overlapping because they are executing at the same time at line 3，4 and 5。

V and V push that also are also overlapping and P and P we push are also overlapping as well。

 So all pair of these three are overlapping at least at line4。

And now you can safely ignore those that are borrowed and borrowing。So single single object。

 for example， v is a borrower here and P is a， I mean， P v is the borrow we。MP is a borrower。

The vector is borrowed from V to P at this line。So there is a relationship between VMP。 they are Bus。

 Bui and Baroor。Similarly， we and this wayta push are also the same。 V is borrowed from here to here。

So you can safely say that， oh， they are safe， even though they are overlapping。

 the one is borrowed and one is borrowing， they are happily coexisting。😊。

But P and V push are different， they are not a borrowed and borrowing relation。

P and we push withta push are coexisting， but they are not not。Happily equal existing。

that's the reason why the remaining pairs， for example， V and with a push are regarded as a conflict。

 They are shared durable accesses that can be potentially dangerous。



![](img/0738fc9de7947304e392d4eb5665765f_25.png)

![](img/0738fc9de7947304e392d4eb5665765f_26.png)

And because they have such a pair， Ro just bail out and。Refused to compile by saying that。



![](img/0738fc9de7947304e392d4eb5665765f_28.png)

Oh， cannot borrow V as meable because is already borrowed as imable。

 it is precisely the reason why P and Wita push can conflict。😊。

You cannot not do with a push because it is they are a P。



![](img/0738fc9de7947304e392d4eb5665765f_30.png)

So this kind of reasoning is statically sound。 It compile time。

 you can detect all conflicting sharemable accesses at compile time。 So without any missing。



![](img/0738fc9de7947304e392d4eb5665765f_32.png)

You canically figure out the entire pair of conflicts。But on the other end。

 it may be incomplete in the sense that not all pairs。Are actually a conflict。 I mean。

 even though the program is safe， the rest may reject this program based on the fact that they are。

 it cannot analyze the ownership relationships between the agents。So it may happen， but in practice。

 it is not that not that。Um。Not that difficult to cope with a compiler。

 You can just move the code around a little bit and make it happy about this ownership。

So that more of the story is that。Yes， it is statically sound。 It is very much important。

 Unlike CNC plus plus， Ru can detect all the all the bug relating to ownerships and lifetimes and memory safety at compile time。

 Thats the main main difference from CNC plus plus。😊。



![](img/0738fc9de7947304e392d4eb5665765f_34.png)

And how， how it this does that， it is based on the lifetime and borrowing concepts that is explained with this example。

Okay， let me summarize what's going on behind the scene for this example inside rust。

 so the key concept of rust is ownership， the ownership is the ability of an agent to access and destroy a resource。

And if you have an ownership of resource， for example， a vector， then you can safely de it。

 or you can safely push a value to that， or if you can safely pop a value to that from that。😊，Okay。

 and ownershipship is by default， exclusive。 It means that if I own a resource， if if I own a vector。

 then no one else can own it。 The vector is only owned by me。But in order to allow sharing。

 it can be borrowed。 So even though the ownership to a vector is exclusive， it can be borrowed by。

 for example， P。So it can be mutably borrowed by a single agent or immorably borrowed by multiple。

So in this example， viata push is。Mutably borrowing the vector。

But the fact is that if it is mutably borrowing a vector。

 no one else can borrow the same vector at the same time because I am temporarily writing the value to this vector so no one else can read it or write it。

That's the reason why mutable borrowing can happen only for a single agent。



![](img/0738fc9de7947304e392d4eb5665765f_36.png)

On the other hand， and the same resource can be shared borrowed by multiple agents if it is immutably borrowed。

If multiple agents are only reading the resource， then it is very much okay because there is no shared mutable mutations。

I mean， so。This is the key invari behind this ownership。 you can mutably borrow a single resource。

 or multiple agents can immutably borrow the single resource。

This idea again is fit for a concurrency because each thread can be considered as an agent。

 so it is an agent that is accessing resources and by the borrowing rule。

 you can may be quite sure that a resource cannot be shared and mutated at the same time。😊。

Because it is mutably borrowed by only a single agent or immutably borrowed by multiple agents。

So Ru Tcher is statically enforcing this discipline。

 no sharemable accesses to an underlying resource by default。So the type mandates the rule here。

 mutably borrowed by a single agent or mutably borrowed by multiple agents。

And this is statically enforced by types。 So this is ownership principle。

And it is quite easy to use in the sense that if you violate any ownership。

 then compilers will report every violations。So for example， in the previous example。

 when P and Vta push are conflicting with each other， the compiler just detect the line。

 the line where the ownership principle has been violated and you can just you can be immediately knowing that。

😊，The word of the ownership problem happens。And you can easily pinpoint work to fix。And as I said。

 it is statically sound or correct in the sense that if a program is type checked by the rust compiler。

 then it is guaranteed that the program doesn't go wrong in any case so。

Because this ownership principle is enforced to a program and that is side checkeded。

 there is no way the program can go wrong， for example。

If you manage to fix this example so that the program is compiled by the rust。

 then it is statically guaranteed that the program doesn't go wrong in any case。



![](img/0738fc9de7947304e392d4eb5665765f_38.png)

![](img/0738fc9de7947304e392d4eb5665765f_39.png)

Okay so far is what is explained with an previous example， but it is not the end of the story。

 so for concurrency we specifically need a third story that is about bending the discipline。

 bending the rule with what is called interior mutability。😊，So。The motivation here is that。This。

Discipline， no sharemable accesses。Is too strong。 So in conquercur programming。

 it is never satisfied by the actual realroad programs。 For example， if you are having a shared。

AStack shared among multiple stress。 Then it is quite intuitive that this stack resource is mutated by multiple stress at the same time。

 There are actually share mutable conflicting accesses。 So we need to tame it。 but we don't。

 We should not remove it because it is the essence of this shared stack。

But what we can hope for in Rus is that。Okay， we can systematically ban the discipline。

 we allow sharemable accesses for stack。But we can do that in a safe manner。

 systematically safe manner。So shared mirror access are inevitable in concurrency。

 but you can tame it。How we can en。Possibly unsafe implementation within Safe API so that。Okay。

 there are shirt stack， concurrent stack。 and that is ta as a very。Unsafe implementation。

 and that cannot be analyzed by RoOS compiler。 Ros compiler cannot digest that the implementation is absolutely safe。

But what we can do here is that， okay， we implemented this task using a very。Barry arcane magic。

But its API is completely safe， the user of the stack doesn't need to know about all the details of the implementation in order to write the Sa program。

😊，The user knows only API， which is absolutely safe in the sense that if the Se is used with only this API。

 the same guarantee is applied， the program doesn't go wrong always as far as the API is used。😊。

In any combination of these API， invocations doesn't go wrong。

That's basically the meaning of this interitability。So in essence。

 what is enforced by this intermodability or setally bending the discipline is that。😊，The Con stack。

Is working as if there are no sharemable accesses from the viewpoint of the user who uses the API。

The API is as if there are no shareable excesses。So let me show you an example of this of interimability。

😊，A ref cell is the first example of。The interurability。



![](img/0738fc9de7947304e392d4eb5665765f_41.png)

And it is basically containing a value。And you can borrow it or you can mutably borrow it。

But unlike the usual references， you can beably borrow it and borrow it at the same time。

So let me explain it in little bit more， so here is a code。

 you can say that there is a function F1 and F2 and there are a function returning a value。😊。

William Val。And let's assume that by some complex invariant。

 it is not happening that F1 and F2 are returning to at the same time。

 So it is implemented in simply just simply by returning a simple value。

 but let's say that there are some complex invariant， and it is more complex and。

The environment is that at find F2， doesn doesn't happen at the same time。Okay。

 and let's look at this program。 There are two values， V on and V2。

And you are borrowing a value at here P1， depending on the condition F1， If F1 is true。

 you are going to borrow V1 and F1 is false， then you are going to borrow V2。And in F2 in and if F2。

 then you are going to borrow V1。And right to the value。I'll write to the V1 and read to the V1。

 as well。And after this if condition， you're going to print the value of P1。

And you can see that there should be a ownership conflict because。P1 is borrowing。

 P1 may borrow V1 from here to here。So， yeah， P1 is actually borrowing V1， but you don't。

 So suppose that rust cannot analyze if1 can become true or false。 It is as an O parkC value。

Rost doesn't know precisely the value of this F one。As a result。

 rust should safely de that either V1 or V2 can be borrowed at this line。

 but it doesn't know what is borrowed。Anyway， we1 or V2 are borrowed here until the last line。So so。

In particular， V1 may be borrowed from here to here。But at the same time， in this if condition。

V1 is also borrowed mutably from here to here。RightAnd there's a conflict V1 is borrowed by P1 and P2 at the same time。

 from here to here。So that's the reason why Ross rejects this program by saying that， oh。

 V1 is beably borrowed。Can not borrow V1 as mutable here at this line because V1 is also borrowed as immutable。

😊，A here， so the Ro compiler will pinpoint where this ownership conflict happens。

 so you need to fix it。Okay， so far so good。Russ cannot deduce the safety of this program， but you。

 the programmer， no， it is actually the safe。Why， because F1 and F2 cannot happen at the same time。

So if F1 is true， then V1 is borrowed here。😡，But after cannot be true at the same time。

 So we so V1 is actually not borrowed at one time。OtherwiseOtherwise， if F2 is true。

 then P1 is borrowing V2。And it is borrowing V2， and this is borrow V1。 they are not sharing。

 not but borrowing the same resource at the same time。At one time， you know that。

But RoOSs compiler doesn't know that that's the problem。



![](img/0738fc9de7947304e392d4eb5665765f_43.png)

So in order to program like this， you need a。A rough cell， basically。

Rap cell is basically a wrapper around the value。 It is a value for it2。 It is a value 666。

 but it is wrapped by a ref cell。And at this line of the code， P1 is also borrowing V1。

 but at this time by calling what is calledTBor。And it is。

Checking if the borrow the ownership rule is in the first at one time， that at compile time。

 but at one time， it is checking if， for example， V1 is borrowed by anyone。Here。

 let's say that F is true， and let's say that V1 is borrowed by。Not borrowed by anyone。

 So P1 can successfully borrow it。Now， F2 is not executed at all， and is's okay。

So the program is running Sa。If iPhone is false， then here V2 is borrowed。

And you can enter this if condition， and this free one is borrowed beautifully at。😊，And yeah， me。

But at this point of time， V1 is no longer borrowed because V1 is。Try borrowed here at Comp time。

 the Ro sees that， oh， it is try borrowed and it doesn't need to track their ownership here。😡。

At this point of time， it says that oh V1 is not borrowed and I am borrowing V1 freshly here。

 and it is very much safe and very much okay， though so Ro allows this program to be compiled and run。

😊，So， this。R sell and Tri entryB mutute is baning the ownership discipline。

 ownership discipline mandates a statically safe program， staticically no ownerships are overlapping。

But here， ownerships seems like overlapping， but we can somehow。An Eliice at run time on that。

They are never V1 is never borrowed at the same time。

 So that's the reason why this we can write this program in this way。

 and that's the reason why it can run without any hasstle。It doesn't go wrong。If the。

But this is under the condition that F1 and F2 are not true at the same time。

But what if F1 and F2 are2 at the same time？Then you are borrowing V1 here and mutably borrowing V1 here again。

And it will exit at one time at one time it pens by saying that， oh， I cannot borrow mutably here。

 so you already borrow it here， so I cannot borrow it again here。

 so it is represented by this error message。😊，So you can play around with this example in this play rustst ground。

So to summarize， ref cell provides an inter remutability that is encapsulating shared mut axises。

 statically completing aes in。😊，In a safe type， that doesn't involve the say share renewable access。

So the reason why it has a safety API is that virtually or in API it。

It is as if there is no shared mutable excesses。Try B mut is immutably borrowing the underlying value。

It is as if immutably borrowing the underlying value， even though it is actually borrowing mutably。

The underlying value。So this so this implementation should be unsafe。

 the words cannot reason about the implementation of this。

 but the fact that if the implementation is inspected by the programmer， you can just say that， oh。

 ref cell try borrow mut is immutably borrowing the value。😊。

It is is acting as if the underlying value is immutably borrowed。So that's the key idea here。So。

It is actually in the implementation。 It is actually unsaly。😊，U accessing shared mutable accesses。

But the API is as if it is not mutably accessing the value。

So that's the key idea of this interimitability。😊，So in this implementation you need to write down you need to wrap the implementation around the unsafe keyword and this unsecured is a bridge between the API without short accesses and implementation with short rem accesses。

 you need to insert unsafe in order in order to implement interior mutability。😊。

And this unsafe cure acts like the the tag that， oh。

 the programmer needs to inspect all the unsafe occurrences。 So it needs manual inspection。

 The the rust compiler doesn't guarantee any safety out of this unsafe blocks， but user needs to。

Usr needs to。Manualally inspect that So that actually like attack。 if you grab unsafe。

 then rust the inro program， then it really stop the all the unsafe blocks and those blocks are only the the only fragment of the program that needs inspection for safety。

😊，So that's basically the key idea behind interabilityD。😊。



![](img/0738fc9de7947304e392d4eb5665765f_45.png)

The API is safe， but implementation is potentially unsafe， and that needs manual inspection。



![](img/0738fc9de7947304e392d4eb5665765f_47.png)

Okay， here is finally the example that is related to concurrency。😊，So as I said。

The C plus plus lock is unsafe because it can dereence the underlying value。

And its pointer can be leakliced。But it should not happen because after releasing the lock。

 the underlying value should not beed at all。So， in order to。In order to dis allow this in rust。

 it implements what is called a D trait。😊，And you can direct the underlying value out of lockguard。

 that is basically the meaning for this program。So from the lock guard here， data guard here。

 then you can dereference you can get a reference to the underlying value。But it has a lifetime。😡。

It is slide here， but this data ref cannot overlie the guard。It should be。

Disdistructed before the guard， it is guaranteed by the Ro type system。And it is lighted here。

 but there is this end here and end here means that this difference target。

 which is meant to be this data ref， should not outli the enclosing type that is lock guard。🤢。

So as a result， data ref is not a na data guard。And this line violate that。 and as a result。

 it is not compiled。 It says that there is an ownership problem。

 There is a borrowing lifetime problem。😊，ALive data ref should not outnve this card。

 but it is outniing it， so that is what RoOS compiler will say and reject this program。

And as you can see， all the concur difficulties like this can be reasoned with ro types。😊。

And that's the reason why we are going to use Rus as an implementation language of for concurrency course。



![](img/0738fc9de7947304e392d4eb5665765f_49.png)

Okay so far we studied a rust ownership type and the motivation here for rust is safety and control at the same time in the presence of shared renewable resources。

😊，And the key ideas of rust is first enforcing ownership discipline。😊，By default。

 that means there should be no sharedm accesses。But at the same time it allows you to bend the discipline by using interutability。

That allows you to control shared moable accesses in a very controlled way。😊。

Systematicically control your sharedmable excesses。

The benefit is that you can safely analyze the safety of removalable essence。 So if。😊，If the。

Interimutability are safely implemented within a type， for example， lock or left cell。

 then the user of this library can no longer worry about the safety of these programs they can just safely use without any worries because the API are safe。

It is statically guaranteed if the implementing unsafe unsafe mutations are actually correct。

 then all possible API usage are safe。😊，That is guaranteed by Ro compilers。

And the second benefit is that， oh， there are unsafe implementations。

 but there are explicitly tagged。 You can only see those code only you can。

 you can only manually inspect those code without worrying about the。😊，At the rest of the coat。Okay。

 so that's the reason why we are going to use rust for concurrency。

 which is about shared reable excesses because they are relevant for these two reasons。😊。

In the next lecture， we are going to understand。 we will continue to study lock based concurrency with safe API。

 So many of you already know stresss or。😊，Sres or atomic variables orx or lockx or conditional variables。

 But you are going to study those concepts again。 but in this time using a safe API。



![](img/0738fc9de7947304e392d4eb5665765f_51.png)

So that is the， basically the。topic of the next video。



![](img/0738fc9de7947304e392d4eb5665765f_53.png)
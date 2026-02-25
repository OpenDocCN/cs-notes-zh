# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P7：-07-Lock-Based Concurrency, API of std.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video and the next few videos， we are going to study the worst concur libraries。

The key point of this library is that the implementations are potentially unsafe because the Ro type system cannot analyze the safety of those implementations。

But they are enveloped within Z API， which means that the user of the API doesn't need to take into account the implementations at all。

 the API is correct and every possible uses of such API will not。

Incur undefined behavior or any kind of unsafe behaviors。

 So this is the key abstraction that is provided by rust。

 and we are going to study such libraries in this in the next few videos。



![](img/09c92e290f820bf38997580ee22fd04c_1.png)

Okay， so the key point， as I said， is the user don't need to worry about the safety at all。

 they just can use the API without worrying about the safety。

The famous libraries include those inside STD， which is the standard Library of Ru and what is called parking lot。

 which provides the low level concurrency features like mutt or conditional variables。

And those inside these courses reposory， and they include the spin log or sequence log that is widely used in the low level con。

And the Curbin， which provides many things， including the scope thread。

 which will deal with the difficulties or challenges that is imposing the Standardup Library Str Library。

And also we are going to study what is called cash pad that is for defeating what is called full sharing。

And we are going to study channel that is also used in the skeleton cut for homework  one。

 A channel is basically。

![](img/09c92e290f820bf38997580ee22fd04c_3.png)

Q where you can send the data and you can receive data。

So this is a channel and is provided by Crossbm with a safe API。We are also going to study rayon。

 which is a parallelism library on top of course beamm and other things。

 and the prominent feature of this rayon is into par iter that is converting， for example， a vector。

 a list of elements into a parallel iterator so that if you are just sending a function to this iterator then the function is automatically parallel executed for each element in the vector。

 so it can be done without any worrying about the concurrencies or parallelism。

As far as you can call this into powerit and then run some function。

 then it is automatically and well parallelzed， so this is the higher level API than CrossLam and other concurency libraries and in this course we are going to study the API of Lewis Raym。

So let me start with the standardout library。So here is an example of a standard library's features。



![](img/09c92e290f820bf38997580ee22fd04c_5.png)

As you can see， there are a few imports of the send library features， including。



![](img/09c92e290f820bf38997580ee22fd04c_7.png)

![](img/09c92e290f820bf38997580ee22fd04c_8.png)

Reference counter， atomic reference counter or a str， and just the single str reference counter。

And sleep function that slips a threat that puts the current thread into sleep for a predefined duration。

And yeah， thiss all。So in this program， let's assume that we have the value five that is named5。

And we want to share this value among multiple stress。



![](img/09c92e290f820bf38997580ee22fd04c_10.png)

And there's the reason why we spawn multiple stress here。And for 10 times。

 we are spaning a threat 10 times。First， we are going to put this value 5 into atomic reference counter so that it can be shared among multiple stresses。

 So in。Usually a data alone cannot be shared among multiple threats。

 If you want to share a value among multiple threats。

 you need to put them into a atomic reference counter。

 This atomic reference counter means that you have a counter for this value。

 So as far as you have a pointer， a reference countered pointer。

 then it is guaranteed that the underlying value will not be deed。 So as far as you have five here。

 that is a counter， then the value is live。 It is proven by the API。Okay。

 so we are cloning the reference counter that is effectively increasing the reference counting number。

 So here when the5 is declared， the reference counter is one because there is only one reference to this5。

And in this four iteration， the5 is cloned as a result。

 the reference counter is incremented from1 to 2。And this5 is the holder of this another count for this underlying value。

And this five is then transferred into into a new thread。 A new thread is pawned with this API。

 and in the new thread， this function is executed。 This is a nottation for a function。

 This is also called a closure in program languages theory。



![](img/09c92e290f820bf38997580ee22fd04c_12.png)

![](img/09c92e290f820bf38997580ee22fd04c_13.png)

And this function is newly created， and this function is given no argument。

 It is quite expected because we cannot， you can in this API。

 we cannot send an argument to the new function。 We just phone a new thread with the function。

 and that function should not be given any argument。Also。But the the。

But the fact that this five is transferred from the enclosing function into this function。

 So it is not s argument or。Argument parameter， it is the sent as a reference。

So this move means that， oh， there was5， the variable 5， and it is used here as well。

 and as a result， this value here， variable here should be transferred or moved into the view another start。

So five is moved to another thread， that's the meaning of this move。That effectively means that。

Before execution of this threat spa， the owner of this reference counter is the main thread。

 The main thread has a five variable， and this variable holds the reference counter for the underlying value。

But when it is moved into this enclosed function， the reference counter is being transferred into this thread。

And especially this variable5 is。Holding the reference counter。

And when the thread is x ended and the scope is ended， the variable 5 is no longer used。

 and as a result， the de for this variable 5 is called and in the de of this5。

 which is an atomic reference counter， the reference counter is decremented by one。So overall。

 in an iteration of this four。Statement。Reles counter is incremented and it is moved into the new thread。

And at the end of the new thread， the atomic reference counter is decremented。And as a result。

 at this point of time， when all stresss are executed and finished。

 only the reference counter for this variable 5 becomes1。It is incremented to 11。

 which is 1 plus 10 and then decreementmented 10 times。 And as a result。

 it is its final value is one。Okay， so after waiting for all the threads， all 10 threads to finish。

 here we are just waiting for one second， but there is a better way to wait for another thread。

 But let's for now， let's， let's wait for just one second so that all threads are finished beforehand。

The reference counter is1， and at the end of this main function。

 the five is also destructed or dropped。 and as a result。

 each reference counter is decremented from 1 to0， and the underlying value is also dropped。

So this is basically the internal working of this program。 So overall， more of the story is that。



![](img/09c92e290f820bf38997580ee22fd04c_15.png)

L。There's an underlying data that is shared among multiple stress， which is 5。

 and this data 5 is cloned and they move to the thread and it is executing some function。

 and then the reference counter is dropped。

![](img/09c92e290f820bf38997580ee22fd04c_17.png)

And at the end of the day， when all stress are executed and the main thread is finished。

 the all the references are gone。 And as a result， the underlying value5 is dropped。

So when you execute this。You can see that each thread is executing its own print function。

 And as a result， 105s are printed in this code。So that is basically what's going on inside this code。

So let's see the API of those the things are presenting， presented in this code。

 The first thing to see is stress bond。

![](img/09c92e290f820bf38997580ee22fd04c_19.png)

This is a spa。You are giving this function a closure。Or a function here， F N here。

 app is a function that is given nothing。And it returns a value of type T。T is a type parametermeter。

 It can be anything。 So it is as a function。And as a result。

 it is returning what is called join handle and this join handle is used to join the thread。

 So instead of waiting for one second， for example。

 you can create a thread and get the join handle and you can join it。

 So it is a more traditional way for waiting for a thread to finish So if you are going to so this will be also used in the homeworkock one because you need to implement what is called a threat pool and in the implementation of a thread pool。

 you need to wait for all the handlers to be all the threads to be joined。



![](img/09c92e290f820bf38997580ee22fd04c_21.png)

At the end of the execution。So， okay， so firstly good， it is a standard library function， Strbone。

 and this just create a new thread and the function alpha is executed。😊，And the return value is T。

 and when the thread is joined like this， then the return value will be the value T。



![](img/09c92e290f820bf38997580ee22fd04c_23.png)

![](img/09c92e290f820bf38997580ee22fd04c_24.png)

So he this basically the。Internal working， I mean， API of this。



![](img/09c92e290f820bf38997580ee22fd04c_26.png)

And you can see that this function is marked as safe。

The meaning of this is that you can arbitrly call this point function and you don't need to worry about the safety of this function call because it is safe。

As marked as rust in the library。 And even though you've spun， for example。

100 times of this function and it' will be okay as far as the function is marked as safe。

 then you can do anything with this API。 That's the guarantee that is provided by rust。

Compare this with the C or C++ API， for example， if you pass a no pointer as the function closure in the C or C++ API and then the behavior will be undefined and as a result you need to deal with such an error case on your own。

But when using a Ro API， you don't need to worry about that because this type FN1。

 the trade F M1 guarantees that the function that is given to this bone。

Is satisfying a certain requirement。And one of the cl is that it is a function that can be called at least once。

And it is given no values。No arguments basically， and returns of value team。

It is the information that that contract is described in this function signature。

 and that's the reason why we don't need to worry about the safety of this function。Okay。So。Here。

 this is an way to create a function that implement FN once on on the fly。 Basically。

 you don't need to you don't need to create a function outside of outside of this FN function here。

 You can just create a function in line in this slide。

 So this is what is called closure in the pro language theory。

 which is also deployed in most modern program languages， including C+ plus。

And just you can execute that function here。Okay， so fars are good。



![](img/09c92e290f820bf38997580ee22fd04c_28.png)

And。And I'd like to see the arc here， so here is an example arc。

In an example of arc at reference counter。 So we already saw a similar example to those in the Roport playground。

 So it is a little more involved， but basically they do the same thing。 It is creating 10 threads。

 and for each thread or a reference counted pointer to the underlying value is past。

 and then it is printed。

![](img/09c92e290f820bf38997580ee22fd04c_30.png)

![](img/09c92e290f820bf38997580ee22fd04c_31.png)

![](img/09c92e290f820bf38997580ee22fd04c_32.png)

So the domain idea is the same。The main idea of this reference counter is that。



![](img/09c92e290f820bf38997580ee22fd04c_34.png)

It is a reference counting pointer that can be。Safely shared among the track。I mean。

 safely sent to another thread。So this is what is meant by this ThrSa。

Atomomic reference counter can be aly sent to any threat。

 so that is the meaning of this search safety here。So。So in this example。

 the reference counter to underlying value is another thread。

 so that's the reason why we use atomic reference counter Arc。Okay。

 then now let me explain a little more little bit more about the con that is imposed on the threat function。

 Str function。Okay， this requirement is quite straightforward。

 F should be a function that is returning T。So far sicker。

But what is required additionally is that the the F function is it should be send and it should be static scope。

Furthermore， the written value T is also send and it is statically scpt。

So let me explain what the meaning of this with an example。Send an code。

Let me show you an example of this。This example here。给。Instead of。

 instead of wrapping the value inside a reference counter。

 we want to wrap a value with a single spread reference counter。

 RF C is also provided by the standard library。 And let's say it is。



![](img/09c92e290f820bf38997580ee22fd04c_36.png)

It's a single stranded reference counter。And it will be a better example here， and let's run it。

And it is going to say， oh， this RC cannot be sent between thread safely。

So it basically means that R C doesn't implement the trade send。

 So that's the reason why the it is 5 cannot moved into this closure。

 So since5 is moved into disclosure。 The closure itself。 The function itself cannot be send。

 So that's the reason why this is rejecting the compilation of this。

 because the F must be implementing the send trait。



![](img/09c92e290f820bf38997580ee22fd04c_38.png)

So let me explain why Ros requires that。So5 is the implementation of reference counter assumes that the increment and decrement are are not。

 not concurrent at all。 So when you increment or decrement。AA reference counter for this Rrc。

 then it should be the case that this that is the only thread that is incrementing or crementing the reference counter。

However， in this program， if it would be compiled， it is not the case。 The reason is that。

At the end of the stress execution， the five was dropped。 and as a result。

 reference counter will be decremented。But this decrement can be executed by multis。

 say test threat at the same time， because they are or all executed in peril。

So that's the reason why this RC cannot be used for this example。

 because the decrement is not meant to be run concretetly。

So that's the reason why the RC here is not bar as send。

 this reference counted pointer cannot be sent to another thread。

That's the meaning of the fact that R C is not more to cent。On the other hand， ARC。

 which is atomic reference counter， is。It takes into account the possibilities that the increment and decrement can be executed at the same time。

 contly by multiple threats， so that's the reason why Arc is arc atomic reference counters or markers ascend and they can be sent to another thread。

So recall that when this5 was ARC。Then it is just safely executed。But on the other end。

 if this five is single for the first counter， the worst compiler reject this program。



![](img/09c92e290f820bf38997580ee22fd04c_40.png)

![](img/09c92e290f820bf38997580ee22fd04c_41.png)

![](img/09c92e290f820bf38997580ee22fd04c_42.png)

By saying that， oh RC cannot be sent between threads safely。 as a result。

 I I am bailing out this compilation。 RRC is not more send， but F is more send。

 so they are some mismatches so I fail to compile it and I just give up in comp this。



![](img/09c92e290f820bf38997580ee22fd04c_44.png)

So that's the meaning of this send here。Only the the closure should be。

Safe to send to another thread because it will be executed another threat。Similarly。

 the return type should also be implementing send because the return value should be sent from a threat to another threat。

So if it is executed in the sp thread， then the thread that sped this thread。

 which I will call Sponer， Sponer will have the join handle and it will eventually get the return value。

 that's the reason why this T should be sent from the Sp thread to the Sponer。

ButThat's the reason why TOB should be also be sent。Okay， so first good。

 and I'd like to explain the meaning of the static of now。Now。Let me change the example a little bit。



![](img/09c92e290f820bf38997580ee22fd04c_46.png)

In this example， there is a five。And。5 the reference to the value 5 is taken。

 and the5 is now a reference to the value 5 that is declared here。

And the references move to this sponsor， and it is referenced。So it looks like save。

 but actually it is not because。Because。When。This slip is not there。

 It may be possible that the main thread may exit before the spa thread。

Because there is no order between the execution of those stress。

 that's the reason why the main thread can be finished before the sponsor thread。If that happens。

 then the five declared here is dropped here。It can be dropped and disrupted before the execution of another threat。

And as a result， this five can be a dangling pointer。Dangling pointer to the stack。That was valid。

 but now invalid because the main function returned。And as a result。

 this print function is very much unsafe because it is referencing a dangling pointer。

 It should not happen in the safe part of the rust。😊。

That's the reason why the S function requires that the F here。

 the function closure and the return value are statically scopept。

 that means that the value should be valid for the entire execution。

 the static scope means that it should be valid from the beginning of the execution of the program until the end of the execution of the program。

It should be valid for the entire execution of this program。 That's the meaning of the stethoscope。

Here， five is not the stoscope。😡，Because5 is constructed after the execution。 I mean， I mean。

 the the invocation of the main function， and it is dropped or deed before the end of the invocation of the main function。

 So each scope is from the line number 7 to line number 23。

And it is not guaranteed to leave or when this threat function is executed。

It is well before the execution of this print function that the five variable is destructed or dropped。

So that's the reason why we should reject this program。

 It is very much okay or even desirable to reject this program because5 is not guaranteed to be alive at this line。

So let's see what it says。 Ross says that。 oh，5 does not live long enough because it is。

It should be steady as required by the API of the Str bomb， but it is dropped here。

 which may be before the5 is used here。That's the reason why I'm going to bail out this compilation。

 And it is safe to do。 I mean， it is desirableable to do so because it is actually a buggy。



![](img/09c92e290f820bf38997580ee22fd04c_48.png)

So that's the meaning of the stethoscope here。In addition to requiring that the closures and the return value are sent。

 which means that they can be sent to another thread。They also should be static。

 That means that the value that is in the inside the inside the the closures and the written value should be live for the entire execution。

 So that's the meaning of this requirement。So as far as these three conditions are met。

 it is guaranteed by the RoOS library that the sponge function is very much okay。

 it does not incur any kind of oneafe behaviors including dangling pointers or undefined behaviors or other very scary things。

 it is absolutely safe that is guaranteed by Ro standardal library。

But interesting fact is that the implementation of this implementation of this bond may not be 100% safe。



![](img/09c92e290f820bf38997580ee22fd04c_50.png)

![](img/09c92e290f820bf38997580ee22fd04c_51.png)

啊Let's say that。Inside this phone function， it is calling what is called the spa on chapter F onafeway。

Which means that RoOS compiler cannot analyze itself that this implementation of this function is 100% safe。

But the library also somehow manually inspected this implementation and guarantees that。

AreGant by this contract of this function definition， a signature that， oh， it should be safe。

 even though Ro doesn't know。 Ro compiler doesn't know the safety of this。

 I know I D library author knows that this is absolutely safe。

 This's the reason why I am marking this a safe function instead of unsafe function。



![](img/09c92e290f820bf38997580ee22fd04c_53.png)

So Standard library provides a bunch of conclive features that has safe API。

 including thread or can some other things， and you can use this with absolute safety guarantee。



![](img/09c92e290f820bf38997580ee22fd04c_55.png)

And learning this learning this。😊，Requirement is a good thing。 So in general。

 when you want to sponsor a thread， these three things should be satisfied。

So it is not only specific to rust， but also generally applicable to systems programming in C S plus plus also F。

 if F is a function pointer， it should be actually a function。 And in addition addition to that。

 it should be it should not be。Dealing with some federal local cost storage。

 and it should be safely sent to another thread， and it should be statically sc because we don't know whether the threat is going to。

Unnive the enclosing function or not。So this knowledge itself is not only applicable to rust。

 but also applicable to other systems programming languages what is learned here。

 what is imminent evident in this RoOST API is that this folo knowledge is somehow codified or somehow explicitly contracted in the RoT API。

And if you are well aware of this Ro API， it is， you will have higher chance to write a safe program。

 not only in rust， but also in other pro languages。Okay， so first a good。

 So we learned a few API APIs and the using this simple program。



![](img/09c92e290f820bf38997580ee22fd04c_57.png)

Which which which。

![](img/09c92e290f820bf38997580ee22fd04c_59.png)

Prince the 105s。And intense rest。 So it is。Interesting example that motivates most of many of the APIs。



![](img/09c92e290f820bf38997580ee22fd04c_61.png)

And Arc has another API rather than new。 It has a what is called to weak。

 but the details of this are not not covered in this course。 So if you're interested。

 please read this reference and see what's going on there or with the the weak type and other APIs。

Also， I believe that you will be interested in threat markers， including sand and sink。

 A send is basically marking that a type is sent to another thread， as I said。

Ts can be transferred across threat boundaries。And all concurrency libraries of rust are developed on top of this marker。

 so you need to somehow make explicit what is sendable and what is not sendable in concurrent programming。



![](img/09c92e290f820bf38997580ee22fd04c_63.png)

Okay， there are there are many， many types are basically asendable。



![](img/09c92e290f820bf38997580ee22fd04c_65.png)

What is interesting is that a scope reference are also sendable because we have a scope here。

 and if if T is sync， which means that it can be accessed by multiple stress。

 then the reference can be sent to another thread。So the meaning of that is that。

 So T think means that it is。It can be accessed by multiple stress at the same time。

 So that's the meaning of the sync， which will be deal here。 And if it is the case。

 then the reference can be arbitrarily sent to another thread because the T underlying value T is concurrently accessible in a safe way。

So it is basically the meaning of these two implementations。

And the other side of the coin is the sync trait， which means that， as I said。

Think types are those that it is safe to share references between the strip。So the， the。

 the send and think are very much related。 This is the definition。 T is think。

 if and only if the reference to T is asendable。 So this is basically the meaning of the。

 the relation， the formal relationship between send and z。

And that's the reason why this is implemented this way。 If T is think， then the references are sent。



![](img/09c92e290f820bf38997580ee22fd04c_67.png)

Probably the， the， the， the。

![](img/09c92e290f820bf38997580ee22fd04c_69.png)

Yeah。Yeah， that the information is represented， formally represented in this code。

 and please memorize the meaning of these two。

![](img/09c92e290f820bf38997580ee22fd04c_71.png)

These two lines are worth memorizing for all concretecur programming in rust。

 and this formal relationship between the pointers and。



![](img/09c92e290f820bf38997580ee22fd04c_73.png)

I mean， the pointers and references and the underlying type are also worth memorizing。



![](img/09c92e290f820bf38997580ee22fd04c_75.png)

![](img/09c92e290f820bf38997580ee22fd04c_76.png)

And when you're going to implement your own con libraries。

 you should mark on what is expected for argument and written values。

 whether they should be sent or whether they should be think or etctera。

 So that's one of the reason why you need to。

![](img/09c92e290f820bf38997580ee22fd04c_78.png)

Understand the concept behind the stand and think trash well。



![](img/09c92e290f820bf38997580ee22fd04c_80.png)

So going back to this point function， the reason why the closure and this return value should be sent is the value should be sent to another thread。

And similarly， arc。ARe that。Let's see the。You function。



![](img/09c92e290f820bf38997580ee22fd04c_82.png)

![](img/09c92e290f820bf38997580ee22fd04c_83.png)

好。Okay。Yeah。So。

![](img/09c92e290f820bf38997580ee22fd04c_85.png)

Yeah， here， gi。Okay。

![](img/09c92e290f820bf38997580ee22fd04c_87.png)

啊。

![](img/09c92e290f820bf38997580ee22fd04c_89.png)

So Arc somehow requires that the underlying value， underlying type T should be。呃， sentence think。

Oh yeah， here。Arc of T will implement send and sink as long as the underlying type T implements send and sync。

 So that means that if the underlying type is can be accessed among multiple stress and it can be sent to another thread。

 then the arc type is also on send and sync。Which means that the reference counted pointer can be sent to another thread as far as the underlying value is sync as well。

 So that's the basically the contract that is imposed by this arc type and please please investigate the types of this arc APIs and as I said。

 the send sync will provide a formal contract between the programmer or user of this arc and the implementer of the standard libraries feature and that is made it means that the T that should be put inside this arc should be sent and sync。

And。And。Indeed， the value integer， integer values are sandable and think。

 And it's a reason why this arc。Arc new， the result of this arc new， which is the five here。

 is also sendable and think。 That's the reason why we can send the five value here。 And as a result。

 the entire closure is sendable。 It implements send。



![](img/09c92e290f820bf38997580ee22fd04c_91.png)

あ、バイバイク。Conforming to the API of this arc。

![](img/09c92e290f820bf38997580ee22fd04c_93.png)

Okay， so far， we studied the four。Of the four members of the center libraries regarding concurrency。

 including thread Arc， which is reference counter and send and sync。

And you can see what's going on here and please read the documentation more carefully so that you are 100% aware of all the APIs。

 AAP APIs。

![](img/09c92e290f820bf38997580ee22fd04c_95.png)
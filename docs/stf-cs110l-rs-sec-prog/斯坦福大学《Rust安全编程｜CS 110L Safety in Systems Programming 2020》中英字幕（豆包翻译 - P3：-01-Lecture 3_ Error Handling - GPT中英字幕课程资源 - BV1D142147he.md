# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P3：-01-Lecture 3_ Error Handling - GPT中英字幕课程资源 - BV1D142147he

![](img/69e0baa6ef3dd584d596b134dc202e6c_0.png)

Cool。So let's get started first of all congratulations on finishing week one I know it was probably really tricky for some people getting used to zoom and everything and just a lot going on at home so congratulations you made it we went through the survey results and it looks like we probably overshot this assignment a little bit apologies for that it looks like a little under half the people took longer than three hours which is not what we're aiming for so we'll try to trim the scope a bit for the second week's exercises that it doesn't take so long but we hope that it was helpful to you and that you got something out of it and that you feel a little more comfortable with rust and of course this is just week one and we're using in so don't feel concerned if things still feel a little confusing in fact I plotted a word cloud of the reflections and the biggest thing you see is frustrating rest assignment which I thought was funny。



![](img/69e0baa6ef3dd584d596b134dc202e6c_2.png)

Some good things here definitely helpful， understand。

 but I think this is actually everyone's first experience with Ru。

 like everyone I talk to when they start letting Ru， they're like。

 damnn it's so frustrating and that's always a word that everyone uses and I think it is and we'll talk a little bit this lecture about why that's the case and why it's so frustrating and maybe what we can do about it。

Some general notes， if you ever need an extension on an assignment just let us know in the course info we said that at least for the weekly exercises that there aren't any late days and that's because we want people to generally be on top of the material。

 it makes lecture easier and it makes your life easier if you don't fall behind but also this is supposed to be a chill class an enjoyable class and we want you to have fun with it and we understand that there's always a lot of things going on and also sleep depreation causes coronavirus。

 this is true facts and so really like we would rather you not stay up and work on these assignments and if you're staying up just send us as message and we would be happy to give you an extension。

Also there's a lot of really good discussion on Slack and a lot of good comments about rust and about rust features。

 and I think it can be a little intimidating to somebody who has never seen this before and never heard about a lot of these things before to see all this and be like holy crap am I behind like am I supposed to know all these things。

 all these things and I just want to make the point that although we're teaching this class in rust。

 it's not actually a rust class and you're like Ryan what like that doesn't make any sense？

The point of this class is to expose you to ideas that you can take with you。

 We want you to see the problems with CNncC++。And rust is really a response to those problems。

 People have been fed up over the last3，4 decades with problems that keep coming up。

 And so this is one way that people are responding。

 It's really the first language I would say that has actually gotten traction as a viable C and C plus plus replacement。

And so I think it's good for you to see how people are responding to those issues。

 and then also to experience firsthand， what are the problems with the response to the problems？

I'm not going to pretend that rust is a panacea that like everything is going to work out great because rust also has a lot of problems and there are reasons why we haven't seen mass adoption in rust just yet。

 and so it's good for you to experience firsthand some of the barriers that come up。

So yeah if you see， first of all feel free to ask questions。

 we love to talk about this stuff with you， we just want to make sure that you feel comfortable and that you don't feel intimidated when there's a lot of like fancy terminology flying around or like you see top talk of advanced features on stack Overflow or whatever。

 we don't expect you to be rust programmers in this class。

So hopefully that's helpful roadmap for today we're going to recap some ownership stuff that Ar introduced on Thursday。

We're going to show some concrete code examples so that you can see how ownership works or more often than not doesn't work。

And then we're going to introduce error handling and rust。

 and Arman's going to show you a worked example on Thursday of like how all of this plays out in live code demo。



![](img/69e0baa6ef3dd584d596b134dc202e6c_4.png)

So let's get started with ownership in C， actually。

 we're going to take a pause on rust and look at how you may actually understand some of the stuff that we're already talking about。



![](img/69e0baa6ef3dd584d596b134dc202e6c_6.png)

So this is a comment from some C code， it's from a project called OpenVSitch。

 and let me minimize these Zoom videos because it is blocking the screen。

And so this comment says get status of blah， blah， blah， returns zero， blah， blah， blah。

 and it stores an error string in star aP and returns positive ano value。

 the color is responsible for freeing star AP with free。

And you don't have to understand the context of this or like what it's talking about the key here is this call is responsible for freeing ERP This function is allocating some memory for this error string and it's returning a pointer and it's saying the call is responsible for freeing that pointer。

 really what's happening here is this function is returning ownership of some memory to the collar。

And we're designating that ownership in a comments because C doesn't really have any compiler notions of ownership。

 but this is really ownership， this function owned some memory。

 now it's giving ownership of that memory to the call and the caller is now responsible for freeing it。

Here's an example of borrowing。And so this function takes some dictionary。

 this constant AV dictionary vowel。I'm sorry， it takes some dictionary instead of this void star object and it says any old dictionary present is discarded and replaced with this constant Avie dictionary star。

 the caller still owns this vowel pointer and is responsible for freeing it So this is really like an immutable borrow in Rut we're kind of borrowing a reference here we're using this pointer temporarily but we're not taking ownership of it we're just borrowing it the caller still maintains ownership and the caller still responsible for freeing it。

 whoever has ownership is responsible for freeing this memory。So that's an example of。

Seeing the same kind of thing that we're seeing in rust in C comments。

Here's something a bit more complicated so this isn't a simple case of。

 oh you have ownership now I'm taking ownership。 it's a little more complicated than that it says note the boot CfS Lib will free the data passed in for the call when all refs to the target K object have been released blah blah。

 blah lots of big words but what this is saying is thatm as this function I'm taking ownership but I'm actually going to immediately pass it on to what they call the boot CfS Lib and the bootfS Lib is going to be responsible for freeing this data I'm not going to free it just yet it's going to survive a little bit longer but I'm going to take ownership from you and I'm going to pass it on to this library to free that data once all the references have been released。

To give you some context， this is actually pretty similar to what happens this is inside of the Linux kernel。

 and this is similar to what happens when you deal with entries in the open file table or in the Vn table。

It's maintaining a reference counter and when the reference counter hits zero。

 it's saying that the library is going to free the data， so really this library。

 which is this abstract notion， a lot of different functions is kind of taking ownership of this data and is responsible for freeing it eventually。

Ownership gets really complicated and like managing memory and C gets really complicated because sometimes。

Libraries will implement their own free functions， they'll return you a pointer to memory。

 but you can't free it using the free function， you need to free it using their own free function。

 and that could be because there's some extra cleanup required and so their free function takes a pointer to astruct and then it frees a lot of pointers inside of that struct and then free the struct so maybe there's like multiple allocations that you need to free。

Sometimes libraries will implement their own memory allocators if you ever run if you've ever run sanity check under vgrind。

 like you do vgrind sanity check， blah， blah， blah。

 you'll see tons and tons of memory errors and that's because sanity check is a Python script and the Python interpreter implements its own memory allocator Valaggrind doesn't know about that So it freaks out。

 it's like wow， there's lots of memory errors， not actually。

It's just that Python is using its own memory allocator。

 and so you need to use its own specific free function。

So this comment is saying the caller owns the data and must free it with not free。

 but this other function when that data is no longer needed， this becomes very challenging and see。

 fortunately， it's a bit easier and rust because we just have the notion that the caller maintains ownership。

And Rus already takes care of freeing the memory when the owner goes out of scope and when the owner is not needed anymore。

And。Rus takes care of figuring out which destructor functions。

 drop functions should be associated with which data and it handles that for us。

Here's another example。Let's see。 why did I have this in here？嗯。Oh yeah。

 here's another example of like a different free function being needed。

 and let me check my notes to see if there's anything else that I wanted to say about this。Oh， yeah。

嗯。Ownership is。And you're going to see this in rest2。

 the biggest ownership problems happen when there are strs involved。

Ownership is easier to reason about when you just have a variable and like ownership gets passed here。

 you're passing a reference here， blah， blah， blah。

 but when you havestructs that that can own or like have pointers to other pieces of memory。

That's when ownership becomes very challenging in rust and also in C。

 And this function is dealing with a struct that。Also has pointers to other memory and this function free is the struct。

 but it doesn't free memory that is allocated elsewhere that the struct points to and so you end up with these complicated problems and see where you may think that you're freeing a data structure but you're actually only freeing part of the data structure and you really needed to call another function to clean up the other part of the data structure R doesn't let you make those mistakes but it is also frustrating because it forces you to figure out all the ownership issues up front。

Here's another example of this where this is function ends with free。

 it's supposed to be freeing memory， but actually it only frees part of the memory and some other function takes care of freeing the keys。

 so this like partitioning of memory management is pretty challenging and C and it shows up in rest as well。



![](img/69e0baa6ef3dd584d596b134dc202e6c_8.png)

So。Ownership is very complicated that's something that has come up in pretty much every survey response。

 Everyone said that ownership is confusing and it's hard to wrap your mind around。

 but that's not actually because ownership is challenging in rust It's because ownership as a concept is challenging ownership is challenging in general。

 it's very difficult and see this is why we mess up so many times and have so many memory related vulnerabilities and see and because the compiler is forcing you to work out all your issues at compile time。

 such that you can't have any possibility of issues in the future。嗯。It's。

It's like going into a relationship with some baggage and it's like， no。

 you need to fix everything now we're， we're not going like。which is trial。

 run this and like see how things go and like let things fall apart in the future。

 you need to fix all your issues now and the rest compiler is kind of like that that friend that makes life difficult for you。

 but it's actually really good for you in the long run。Um。

There was some confusion last lecture year also about the performance implications。

 like what is actually happening under the hood？When you pass ownership of something or when you pass references and there's a key distinction to make between what is happening at compile time and what is happening at runtime so at compile time rest is very different from C because it has this ownership model and it forces you to like figure out all your ownership issues。

 blah， blah， blah。But at runtime， it's actually pretty much the same as C， so if you pass ownership。



![](img/69e0baa6ef3dd584d596b134dc202e6c_10.png)

You're really just passing a pointer， it's like passing a pointer and C。

 except that the compiler is doing some work for you and it will insert the appropriate free call for you。

If you pass references that's also just passing a point here so there's no performance downside or there's no real performance difference between passing ownership and borrowing a reference and passing that reference。

 they're really the same post compile if you explicitly copy some memory then of course the compiler will copy the memory for you but。

Hopefully this is helpful to get a sense of。What the RE compiler is actually doing on your behalf。

Does this make sense to everyone so far， thumbs up thumb down。

Letly thumbs up cool Feel free to unmute yourself and interrupt if there are any questions at any point since I'm going a little fast。



![](img/69e0baa6ef3dd584d596b134dc202e6c_12.png)

Alright， so I'm going to do a quick demo with some examples of rust code。 And for these examples。

 I want you to think about。

![](img/69e0baa6ef3dd584d596b134dc202e6c_14.png)

Will this code compile first some of it is valid rust code， some is not if it doesn't compile。

 how could we fix it and if the equivalent C code or C++ code would compile。

 why is it not allowed in rust， like what sorts of issues come up if we write that kind of code in C？



![](img/69e0baa6ef3dd584d596b134dc202e6c_16.png)

So here's our first example， hopefully this is big enough for you。😊。

Take a look at this code and think， will this compile thumbs up or a thumbs down。And well volunteer。

I'll give everyone just a few moments。Then can I get a volunteer to unmute themselves and then？Say。

 will this compile yes or no？Yeah。😊，Yes， it is。 Can you explain more？That's exactly right。

We have an immutable variable here。 It hasn't been declared with the mute keyword。

 so when we do this push string which modifies the string， that's mutating the object。

 but we said it was im mutable so that should not be allowed and the rest compiler will complain if you do rust C then you end up with like cannot borrow as mutable because it was declared im mututable Okay。

 so what if we add this mute keyword， does this fix our issues。



![](img/69e0baa6ef3dd584d596b134dc202e6c_18.png)

![](img/69e0baa6ef3dd584d596b134dc202e6c_19.png)

哪你问。

![](img/69e0baa6ef3dd584d596b134dc202e6c_21.png)

Yes， so this is a very simple warm up if we declare this as mutable。

 then rest has no problem letting us mutate this string， so cool。



![](img/69e0baa6ef3dd584d596b134dc202e6c_23.png)

There's some discussion about like whether this would work in C and C++ and why not I'm going to skip it for the sake of time。

 but I have some lecture notes up on the website if you want to check this out。

 long story short it works the way that it probably should work in C++ C has a very weird notion of cont and unless you declare the string a certain way。

 C will let you modify a cont string which is very weird and not good。So。

No points to see for this example。Al right， let's move on to just a slightly more complicated example。

 Does this code work， Yes， or no， Think about it for a few moments。

 and then I'll ask somebody new to volunteer。All right， what do you guys think？



![](img/69e0baa6ef3dd584d596b134dc202e6c_25.png)

Yeah。Yeah， so this actually works fine。

![](img/69e0baa6ef3dd584d596b134dc202e6c_27.png)

Re see。Excess2 and it compiles fine And what's happening here is so we declare this variable when you declare variable。

 you get ownership of it because it's yours you declare it and there's no ampersand here。

 so we're passing ownership of this variable to Ammm Ammmm takes ownership of that variable it prints and and then we're good like that's it there's nothing after this program that's the end of the program So nothing bad happens。

 What if we were to do this。This is example from Armand's lecture on Thursday。一。That's exactly right。

 and I want to make sure that everybody understands this because this is a really crucial example to understand。

We start with ownership， then there's no m percent here。 So we're passing ownership to Ammm。

 Ammmm runs。 and it actually like exits this function returns。

While still holding ownership of this string。Because it's going away and it had ownership。

Rust will free the string after this function finishes。 like at this point here。

 that's when that memory gets freed。 And then we try to go back to main。

 We return to main after this line。 And now we try to execute this line。 And， of course。

 this doesn't work because。Conceptually， we no longer have ownership。

 like we gave ownership away to Ammmm the first time， but concretely。

 it doesn't work because the memorys actually already been freed。

 Like that buffer doesn't exist anymore。 And so it would be unsafe to call Ammmm a second time because that memory's been freed。

 And most people look at this example。 And they're like， oh my gosh， this is really frustrating。

 This is really annoying。Why is it？

![](img/69e0baa6ef3dd584d596b134dc202e6c_29.png)

The error message。So if I run rust C， it says that we move to the value here。

 we passed ownership to Ammm on this line， but we're still using rust or I'm sorry。

 we're still using S after that and that's not allowed because we gave away ownership。



![](img/69e0baa6ef3dd584d596b134dc202e6c_31.png)

So most people look at this and they're like， wow， that's really frustrating。

 why does rust prevent such a simple thing from working？

My answer to that is this looks simple only because it doesn't have any mals or freeze inserted。

 Like， if we look at this code in C。This is one way that you could have written the code。 right。

 We allocate our string， Call Ammm Nm， call Amm nom Nm again。 Ammmm just does printf。

 This is the same thing， but we have a free inserted。 You could have written the code this way。

Or you could have written it this way。Or you could have written it this way， oops， nuts。This way。

Or you could have written it。This way。And of those four ways that you could have placed the freeze。

You either have no free。 So it's a memory leak。 you have a double free。

 which is a potential security vulnerability。 You have a free and then a use after free。

 Or this is the only proper way。 So of those four ways， only one really works and。

Rus is forcing you to be clear， like which way are you intending here。

 where do you want the memory to be freed， and it's not going to let you be ambiguous and it's not going to let you make any mistakes。

 it's not going to let you do a use after free or anything like that。

 it's forcing you to be clear about your intentions。

And I think that's unintuitive when you start writing Rt because this may not be something that you think about。

 but I think you'll find that as you practice doing this。

 it actually makes you a better C programmer because ownership is something that you need to think about and see it's very。

 very， very crucial that you get ownership right and see even more crucial because the compiler won't catch your mistakes and that's really what R is trying to do here is to try to get you to think about ownership and be clear。

About what you mean。Does this make sense to everyone？Alright， so let's。

 let's talk a little bit about references and about borrowing and hopefully that we can。Yeah。

That's a really good question and so this is how we would write the C code right。

 we want S to be freed inside of Maine and so really what we want is to retain ownership inside of Maine such that S is freed when Maine finishes when this S goes out of scope。

In order to do that， instead of passing ownership， we can pass references。

So here we would change this。Such that Ammm takes a reference to a string。

 and then we borrow a reference here。And this way， we're keeping the ownership of S inside of this scope。

 inside of this function， and it'll be freed at the end of this scope when when S goes out of scope。

 and then we're just really passing a pointer to Amnomnom so that it can be used inside of this function。

Great question。Does this make sense to everyone？Alright， so。

Let's talk about references because you can also have a lot of confusion and references as well。

What do y'all think about this code， Does this work？Why or why not？Anyone want to take a guess？

That's a really good question。It kind of looks like we're taking S and we're transferring ownership of S into S1。

Which means that it's no longer in S。 And so you can't use S again。

 That would be true if we didn't have these ampersans。 if you don't have the ampersanands。

 that means like you're taking S and you're moving it into S1。

 The ampersand means borrow a reference。 So what this code is saying is take S。

 B a reference to S and put that reference in S1。 borrow a reference to S again and put that in S2 and then use S along with those references。

 Does this work。 This is not actually super intuitive if you haven't written rest before。Yeah。

 think about this in a C program if you have a value that never changes。

Then or or think about this in the Google Docs example。

 Like if you have a bunch of people that are looking over Google Doc that never changes。

 you can't have any issues where the Google Doc changes when somebody's looking at it。

 like the whole reason that we introduced this notion of。

 of borrowing references and immediaable references and whatnot is because we wanted to avoid that。

was I forget what the term that we used last lecture was。

 but we wanted to avoid that issue where somebody's looking at the Google Doc and somebody makes a sneak change to it such that that person is confused about what that Google Doc is now。

This came from that vector example where like we thought we had a pointer to something inside of the vector。

 but then somebody reallocated the vector underneath our feet， and now that pointer is invalid。

That's the kind of issue that we want to avoid， but this doesn't have that issue because everything is constant here。

 nothing changes。Because S is immutable and all these references are immutable。

 it's totally defined to have multiple references at the same time to something and so this code works fine and if we compile it the compiler comes back happy with no errors。



![](img/69e0baa6ef3dd584d596b134dc202e6c_33.png)

![](img/69e0baa6ef3dd584d596b134dc202e6c_34.png)

What if we were to do this？With this code compile。Okay。

 so there's one reference here to mutable string， and we said that you can have at most one reference one mutable reference to string。

 so this checks out。Does anyone want to make a counter argument？That's exactly correct。

 Rs model is you can either have one person modifying and nobody else doing anything at all。

 or you can have as many people as you want reading。

 But as soon as you have one mutable reference or like one usage of a mutable variable。

 you can't have any other outstanding references。So you say， okay， well， that's fine。

 let's get rid of this。And'll remove S2。 All right， now we have one mutable reference。

 Does this code work。Why not？Yes， exactly。 S is actually declared immutable again by default。

 and here we're trying to take a mutable reference。 If this were allowed。

 you would be able to modify the strain using S1， even though we declared it as immable。

 and that's probably not good。So okay， well。What if we did。This。Does this code compile？How come？Yeah。

 you you don't have two mutable references， but you kind of have two mutable references in some sense。

 right， like S is mutable S1 is mutable。 They both are pointing to the same thing。

 and so that kind of seems like a bad time， right？

![](img/69e0baa6ef3dd584d596b134dc202e6c_36.png)

And you are correct if we try compiling this。It says， hey， this code doesn't work。

 you've got two references trying to be used at the same time。



![](img/69e0baa6ef3dd584d596b134dc202e6c_38.png)

So let me throw， before anyone asks another question， Let me throw something confusing into this mix。

 What if we split up this print line， So we have two print line。And let's do S。And。S1。Does this work。

How come。Exactly， when I first look at this， I say， hey， this。

 this should not be allowed because you have two mutable references and not both references。

 but you have two ways of mutating the string outstanding。 and that should not be allowed。

 but the rest compiler is actually really smart。 And it'll look at this and say。

 but in between where you create S1 and the last time where you use S1。

 like in between the lifetime of S1。You're not using S。

 There's nothing in between these two lines where S gets used。

 And because S is not used between the first time you use S1 and the last time you use S1。

 we're going to treat this as okay。 What's really happening here is you're taking S。

 You're borrowing a reference to S， you're using it for some stuff。

 And then the last time that you use it， you're kind of returning oops。

 you're kind of returning the reference back to the owner。And so after this line。

 we get S that reference kind of returned back to S。

 and we can use S as if there are no outstanding references， which is the case here。

Does this make sense to everyone， this is a little confusing and it will definitely take practice to get used to。

What is the。Question， would it still work if you print S before S1。 great question。

 And if you want me to try anything live code， you can just jump in because I don't have the chat window open。

 So does this code work。DoesAnyone want to guess？

![](img/69e0baa6ef3dd584d596b134dc202e6c_40.png)

What's that。So this actually has less to do with borrowing and more to do with like a reference counting issue。

Anyone else want to guess why？So for the sake of time。

 this doesn't work because we have a mutable reference to s and then S itself is mutable as well to keep in mind。

 so we have a mutable reference to S， which is still alive because we're going to use it later down here。



![](img/69e0baa6ef3dd584d596b134dc202e6c_42.png)

And then we try to use S。And。In effect， this is basically having multiple like writers of a variable。

 multiple things changing a value and memory at the same time。

Because you could change this string through S， or you could change it through S1 at the same time。

 and we want to forbid that in rust。The compiler says， hey， you have this mutable reference here。

 it survives all the way down here， but while it's still alive。

 you're trying to use S S1 is mutable so this should not be allowed。

We also like we also have like a mutable borrow occurring while we have an im mutable borrow。

 So it's like you have like a writer and a reader at the same time。

 it's kind of what the compiler is saying like there right Yeah。

 it's smart enough to know that even though S is declared mutable， you're using it as a mutable here。

 but that really doesn't matter because you have a mutable B here like somebody could be changing the string and at the same time that the string is being changed somebody is trying to read this like intermediate contents。

Yeah。That's a good question。 And Armen， feel free to jump in if you have a better understanding than I do。

 but。I think Rus just looks at the way that you've declared the reference and that is what the reference is going to be。

 even though printline isn't actually changing what's inside of this string。

 it says you have a mutable reference here， you're using that mutable reference。

 and so I'm going to treat that as a mutable borrow。Printline， by the way。

 is not actually a function。It's what is called a macro in rust and we'll talk about what macros are and how they're used later on。

 so that's why we see this mutable borrow reference here。

 even though printline isn't actually mutating anything。So in the interest of time。

 I want to make sure that we get to some of the later contents。

 but if you have more questions about this， definitely ask in the chat and Armen can answer or。



![](img/69e0baa6ef3dd584d596b134dc202e6c_44.png)

Feel free to ask on Slack and we'll help you out there too。Alright。

 so let's let's move on to error handling。 I'm running a bit short on time。

 so we may not make it through all these examples， but I want to bring this up because it's really important to have some understanding of of how rust handles errors。

 It's very different from C and C++。

![](img/69e0baa6ef3dd584d596b134dc202e6c_46.png)

So here's some code， it takes a packet from the network and it does something with it so this is kind of similar to the example that I showed on the first day where we receive some packet。

 we allocate enough memory this doesn't have a buffer overflow。

 we copy the packet data into the buffer and then eventually we free the buffer。

I move on to make the argument that this code has a security vulnerability。

Does anybody know what's wrong with this？嗯哼。😊，Yeah。

 I think most implementations actually return you a pointer to a buffer of length to zero。

 and so this actually ends up working fine in that case， but you're on the right track。

 there's something involving something else here。Sorry。Oh， yes。 Yeah。

 You have to assert that it actually return some kind of pointer And and why might it not return a pointer。

 Well， Malik， if Malck fails， and the only reason that Malik will fail is because it can't successfully acquire memory like there's not enough memory left。

 If this length is really large。 there's a very good chance that Malick will not be able to allocate that much memory。

 And you just don't have that much memory on your system and it will return。

A null pointer saying that the allocation failed and we're not doing any error checking here and so this code is going to happily chuck along and use Buff when Buff is null and you'll get a sink fault。

 so this is what is called a denial of service attack you're denying service you're taking down a service really by exploiting some vulnerability like this is not as bad as remote code execution which we saw from buffer overflows but it's still considered a security vulnerability because you may have some service that you don't want to go down some critical infrastructure。

And there's two real problems here the first problem is that we're using null as a substitute for a real value。

 such that it's possible to take this buff and like look at this code and think that that's a valid pointer and the other issue is is there's not really a great mechanism happening here to signal that something has gone wrong。



![](img/69e0baa6ef3dd584d596b134dc202e6c_48.png)

So I think I'm only going to have time to go through this first one and then Arman will pick up that second point in the next class。



![](img/69e0baa6ef3dd584d596b134dc202e6c_50.png)

So null pointers have caused a lot of issues all over the place。

 I have this link here where there are 1627 vulnerabilities that are related to null pointer geo references。

And most of them are just denial of service vulnerabilities， which is like still bad。

 but not quite that bad， but sometimes you also end up with remote code execution caused by N null pointers。

 I don't think I included the link to that one but there's a link in the lecture notes and the inventor of N Nulls calls it his billion dollarar mistake because it is so small and like so seemingly innocuous but has caused so much grief in software。

So why are nulls so dangerous， like what's problematic here？That's true。 So part of it is like。

 there are。Pretty significant consequences for misusing a null。

 It's like a pointer to invalid memory。 That's true。

Would it be better if it was a pointer to valid memory？Yeah。

 maybe it shouldn't be a pointer it definitely would be worse if it was a point to to valid memory because then instead of having denial of service。

 you can easily have remote code execution so that would be bad I think the real reason that nulls are so problematic is because they place a huge burden on the programmer to keep track of what can be null and what can't be null oftentimes in C null gets passed as a parameter you see this in weight PID where it's passed as like the second arguments if you want to say I'm not interested in getting more information about how this process terminated。

And it's used all over the place and then it's also returned as a value and if you're implementing a function。

 you have to like look at all your parameters and keep track of what could be null here and make sure you do all the proper error checking and if you're calling a function and getting a value back you have to think could this function return null and if so you have to make sure that you handle that appropriately there's a lot of burden on the programmer to keep track of everything and if this list is any evidence we just can't do that successfully。

So what should we do about it？Rust solves this issue by introducing a type called option。

And option can either be some。Or it can be none。 None is really the rest equivalent of null。

 but the difference is instead of like having null and like valid values mixed together in one type。

 and you're not sure which is which it introduces this option type that makes it abundantly clear。

 hey， this value could be null， it could be none。 So if you're trying to return an option。

 you do something like this。 if you want to return a value， you return sum that value。

 and you put it inside of there。 Otherwise， if you want to return null， you just return none。

And this is option containing a string， so whatever you put inside of the sum has to match whatever type is declared as part of that option。

And then if you get a null back， how can you actually deal with it？

So feeling lucky returns an option， option is kind of an object。

 it's actually an enum and we'll talk about rust enums a little bit later。

 but it kind of works like an object like you can call methods on it。

 and so we can say is this option is it done or you can also say like I didn't put it in the slide but you can say is some to see if you got back valid a valid value？

You can also call this unwrap or function， which says if it returned some。

 unwrap or will give you whatever that value is， so like if this returned I'm feeling lucky then message is going to be I'm feeling lucky。

But if it returns none， then use this as the default value。So if this function returns to none。

 then message is going to be not lucky。And then really like the most idiomatic way to handle this。

 and you'll see this a lot in rest code。Is to use what's called a match statement a match。

 The match keyword is kind of like switch in other programming languages。

 It's a lot more powerful than that。 And I feel like I'm doing a disservice to rest by explaining it like that。

 But I think that's the most concise way to understand this。 You say。😊，Call I'm feeling lucky。

 take the return value， and there are two possibilities here， it's either some or it's none。

So if it's some， then do this and message is going to be whatever that option contains。

 or if it's none， then do this。And you can run this code and it will either print Scott message。

 whatever the message was， or no message returned。So this is really how rust handles nulls and it makes it abundantly clear like when you can have a potential null value。

 if you can't have a null value， then you just work as normal and a lot of times that's the case。

 But if there is the potential to be null this forces you to think about like how am I going to handle this the compiler won't let you get away with just。

Passing that off and not worrying about it。Any quick questions about this？



![](img/69e0baa6ef3dd584d596b134dc202e6c_52.png)

We'll talk about error handling on at the beginning of Thursday。

 if you want to jump ahead you can read through the lecture notes that should be pretty comprehensive。

 but the essence is that rust uses this thing called result， which is very similar to option。



![](img/69e0baa6ef3dd584d596b134dc202e6c_54.png)

And if you want to get a head start on the assignment， which is going to come out today。

 you may want to take a look at this to make your life just a little bit easier。



![](img/69e0baa6ef3dd584d596b134dc202e6c_56.png)

So hope that was helpful， we'll pick this up on Thursday and thanks for coming。


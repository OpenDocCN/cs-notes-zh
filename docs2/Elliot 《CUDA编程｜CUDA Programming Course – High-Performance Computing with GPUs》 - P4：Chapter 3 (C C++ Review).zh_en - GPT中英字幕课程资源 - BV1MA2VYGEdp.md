# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P4：Chapter 3 (C C++ Review).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

![](img/f91eaaaa20eab9bb9bb5b79d7c4bc048_0.png)

So now we can finally get into some coding in order to really understand how to use Cuda。

 you need to first cover C and C plus plus。 So this course isn't actually about C and C plus plus So I'm just going to provide some resources for you guys to learn this stuff。

 and then I'll jump into some more advanced topics just to touch over and review the subjects。

 So for those of you who are new to this stuff for those of you who are new to lowlevel C C plus plus coa programming。

 I have some resources for you， some good articles， some good things to manage through。

 And if you are already experienced。 just pretty much skip this part or even even still look at it to maybe touch up on the basics and I'll cover some more advanced topics right after this so。

Learning C in C plus plus is hard。 And so you really have to define what the best resources are and how to actually learn things properly。

 What is the best use of your time， right， This is a common dilemma that we have。

 So I came across a Reddit article on best resources to learn C plus plus and it。

It pretty much said learn C plus plus dot com plus a bunch of other links that you might like。

 So learn C plus plus dot com is good。 I've never used this before。

 So I don't know how comparatively good it is。 So that that's an option， of course。

 And then there's best way to learn C。 So looking through this。

 I pretty much found that everyone likes the。😊，The modern Sea， this one。

C programming a modern approach。 That's a， it's a newer book。

But that's how people found best way to learn to see if you are just trying to learn this for free and try to。

 you know just go through the syntax and understand it as quickly as possible。

There are some resources I would recommend and have looked through a little bit。

 So freeedcodeC has some good stuff on this C programming just a bunch of blogs。

 essentially on how to just pretty much just learning the language。

 and then you have C+ plus just you know， maybe some more advanced things。You know， libraries。

A bunch of modern sea+ plus stuff。So freecodecamp is a great resource and then the one that I've personally stuck with for a long time and continued to use is W3 schools So it's pretty much like a nice easy to read easy on the I documentation on or just an intro rather on how to use C and C++ so I have both here I'd recommend if you're new to this just look over each of these and do do a bunch of practice questions on every single one of these all these are super important there's some of them we might not actually use explicitly in the course。

 but it's still good to know it regardless just for you having that you low levelvel brain so that you can dissect problems on co applications that we may not cover in this course。

So I'd recommend just like looking through all of these， go down all the way to like these examples。

Like everything。 And then same with C plus plus as well。 So all all your basics， your functions。

 your classes， and then down to examples as well。 So that's。

That's pretty much all I have for the basics of CNncC++ Now we're going to go ahead and touch on pointers。

So we're going start off with pointers If you go to Github。

com s inputputtohi//kuuta course and then pop over to you're not going to pop over to dev this is going to be all pushed up and ready once you're seeing this but essentially you're just going to get cleanness into a directory of your choice and then we can go and get started with the C and C++ review So I have this all in my VS code here and it's all zoomed in and nice for you to see。

But we'll start off with a simple pointer example， so we initialize an integer integer x to 10。

 this is the data， this is the data part of x， and then we initialize a pointer type so this asterisk that means we're doing a pointer to an integer and we're setting that we're setting the name equal to pointer and then this ampersand is saying we're going to get the memory address of x so we have x here which is 10 and the ampersand says we're going to get the memory address of x which is which is going to be the pointer to 10。

And then we can， we can just print this out。 So if I go Gcc and we need0。01， can then run that。

You'll see that we get an address， so I have the pointer I have the pointer type here。There's。

 there's an index where you can find these。 if I pull up a tab here and go point。Brint app。Like end。

 for example。So you have all these different things here on C++。

com that you can use and these are just like the formats and stuff so。We have， we have a pointer。

It's this value that we're returning we get a memory address to the value 10 and to get 10。

 we're passing in pointer， and then we do the asterisk to dereence it。

 So dereence means we have this essentially we have this data thing， which is 10。

 We have the memory address to 10 just a level above and de referenceence is just going go downward it's just going to go back to back to that。

 So we have this memory address dereence and go back to 10。嗯。

The next example here is a little bit tricky but it's fine。 it's relatively intuitive。

 so I don't expect it to be that hard， but essentially what we're doing is we initialize a value of 42 and then we make a pointer an inger pointer type called pointer1 and we set that equal to the memory address of value so it's ampersand memory address of value so it's going be like 42 and then we create pointer1 which is a memory address or a pointer2 42 and then we do the same thing so we make a pointer to a pointer which is what a double asterisk is for and then we do again ampersand of pointer1 so memory address of this pointer so then you have you have 42 and then you have memory address which is you have the pointer 42 and then you have another one above that which is pointer to a pointer to to a value and then we just do that another time so it's pointer。

to a pointer， to a pointer， to a value。And。This logic checks out。And when we print this out。

 we're going to return the integer type So D， and then we're just going to triple D reference it。

 So we have these multiple different layers， So we're going up a pointer like level1。

 pointer level 2， pointer level 3 and D referencing is just like going down a level so we go down one to3 levels and back back to that value of 42。

 which is an integer and we can safely return that。So if I just go GCC and then。Pile 02。

We can go in and run that， and we get a safe output value for these too awesome。



![](img/f91eaaaa20eab9bb9bb5b79d7c4bc048_2.png)

So now me pop over to number three， which is where things start to get a little bit weird and initially this was kind of a funky topic for me as well。

 but this this is void pointers， So void pointers are a little funny and they actually allow us to do a lot of tricks that allow for things like polymorphism and stuff。

 but we're not going to go over that a ton that's like other。That's not covered in this review。

 So we initialize an integer called nu to 10。 We initialize a float called F nu equal to 3。14。

 and then we have this this void pointer。 So what this means is like if you had an integer and then an asterisk that would mean it's a pointer to an integer But void is no type。

 So it's like a pointer to no type， And that means we can actually change which type it is pointed to。

 which is a cool little feature that you can do in C。

So we say void pointer is going to equal the memory address of nu， which is this， right？

 And then what we can do here in this in this print part， we essentially we take this。

 We cast it to an int pointer type。 That's what this part is for these brackets and then inside the int and then after the asterisks。

 the pointer cast， and then we dereference that。So we have a void pointer。

 which we cast to an integer。We cast to an integer type。

 It's originally holding the memory address of int。And then we dereence that after it's cast。

 so it's going to go up to this memory address and then it's going to go back to 10。

 which is the value of nu。And then we essentially just do the same thing for this F nu here。And。

I have nice little descriptions here that you can read on your own and then a fun little fact。

So Malick。Actually returns a void pointer， but we see it point to a specific data type after the cast。

 so。You typically see Malick as like these opening brackets， this brackets。

 and then you have the actual cast inside of it so what we did over here is what you see in Malick so it's actually returning a void pointer and then you cast that to a specific like integer or a floating point pointer and then you can use that for something like an array。

嗯。So if we go ahead and just GCC compile this。And then run， we get our integer。

 which is integer type， of course， and then we get our float 3。14， which is a float type。

Sovo pointers are not void pointers， sorry， noll pointers are really interesting。

 and you probably found void pointers interesting as well， but these are a little bit different so。

No pointers can actually make our code more robust through if statements。

I'm going remove those binary files for now to clean some space up。

But we we initialize a pointer to null if we try to print this out it's it's going to essentially return like there's nothing right there's like no space actually here。

 there's nothing that you can't you can't use that pointer for anything because it's null that's the whole idea here so what we can do is we can check if the pointer is equal to null。

And then we just essentially just report that maybe we throw an error message or we we put a warning up cannot dereference this right if the pointer doesn't have anything you can't dereference nothing to something you can't do that so。

We actually change that up and we we allocate memory to pointer to this pointer so that we can use it safely later on。

 So I'm just going to actually compile this so you can so you can see what it's doing。

Initial pointer value is nil， so we have the pointer type we cast to a boy pointer。

 which is going to be no， null， of course， so nll， that checks out。Pointer is null。

 cannot de reference。 Good。 So this， this was true。After allocation。

 so this is where we get into this part。 Malik is going to return a void pointer。The size of int。

So that means there is actually something there Now。 there， There is something there。

 It doesn't have an explicit data type。 but we have something there。 That's like int， I think，32 B。

 So4 Bs。And then we check if pointer is equal to mill again and it doesn't print memory allocation failed so that that's good。

 And then we get to number four after allocation pointer value is this so we cast this to a void pointer and we can actually see this this memory address we can actually see that it works and then we can you know we know that this exists now so we can use it for something so。

We， we essentially check it for null。 It's safe to use now。 And then we have this。We have this。

De referenceference pointer。 So you de referenceence that memory address back to the data part。

 and we set that equal to 42。 So now you have this safe to use， you have this。

 safe to use memory address and the data associated with that memory address。

AndThen we can free that pointer， set the null after freeing， and then we see that it's null again。

Yeah， if pointer is null， so we know that it is null。Sttafely avoided use after free。 A。

 So the the whole point here is that we can use no pointers to do little tricks。

 and we can make our code more robust by checking if it is null。

 We can avoid running into unexpected errors like sg faults and other weird things that are hard to trace back。

 right？ Sometimes you don't want to have to go through all of that just to figure out an error。

 So it's better to just write more robust code in the first place and ensure that it works properly。

So in this example， there's quite a few things going on here。

 but I'll try I'll try to explain this as best as possible。 So we have an array。

 We just declare an integer array，5 numbers， and then we have an pointer an integer pointer equal to array。

 So in C， because we're just leaving it as array alone。

 it's going to point to the first element because that's how memory is lined out right it's going to point to essentially where does this thing start and that's going to be that's going to be 12。

 of course， but we know that an array is a pointer on its own if we don't dereference if we don't index that array it's just going to be a pointer alone right。

 So if I if I print F andmi go， we just go array。Sure， I'll let Get up Coilt to complete that。那那。

We'll see that this array， if we don't de referenceence it just on its own and it is a memory address with a pointer to this array。

So we set， we set let me just delete it that。We set an。An integer pointer equal to that。 So that's a。

 that's a memory address that we have。 Awesome。 Now we look at our position 1， which I printed out。

 that's going to be 12。😊，So we have that start of the array in memory。

And then we just dereference that number， so it goes back to 12。That's what this asterisk is for。

 and we print as the integer type。Awesome， now we have a forlip going on here。

 So what the hex is doing。We have， we have I， starts at zero。

 we want to stop it it go whenever it equals 5， we stop it， and then we increment by one each time。

So inside of here we have an integer type and that's going to be the dereferenced pointer。

 So whatever pointer is， we're going to dereence that back to the original value that it was。

 and then in here we're going to do the pointer type of the actual pointer itself So this is the memory address that we're seeing。

And then we're just going to increment this each time， each time this for loop goes。

 we're going to iterate once and we're going to increase， we're going to increase pointer。

 which is the memory address， we're going to increment that。So。

I had a little example here that I wrote out。 These obviously won't be like the same examples every time。

 they're going to be different， but notice how this pointer is incremented by4 bytes right So this is not in bits。

 this is in bytes。 So if we do 8 Bs in a byte times 4 Btes， we get 32 Bs。

 which is the integer 32 type， the classical integer 32。

So hopefully it makes a little more sense now about how memory is laid out， at least on the CPU。

 So yeah， we just have these essentially skipped by four bytes every time，4 bytes times。

8 B per by is 32 B， and we get our in 32 from that。 I also make a point that。Well， right now。

 pointers are not in 32 B in size， but we'll see why having them as in 32 right now can be a major issue。

 So if you actually do。If we go Python and we do2 to the 32。 We'll at this number。

 So look how big this is。 This is 1，2，3，4，5，6，7，8，9。 So that's， that's about 4。2。

 that's about 4 GBtes。In powers of two， of course， that's four gigabytes。So if you have， say。

8 gig of memory， which isn't actually that much on this machine， I actually have 64。

 So if I of 64 gigs of memory taken up by like a single array。 I mean， that opposite wouldn't happen。

 That's a really large array。 But let's just say I have like one that's like you know，64 gigs long。

 Well， we're actually going to get overflowed when we try to index that way。

So you're going to see later on that it's more useful to use a certain type for these pointers。

 So if we do2 to to 64。 So it a double precision integer。 So in 64。

 you'll see that this is like extremely massive。 This is like。I don't know。

 somewherewhere in the exabytes。 It's like ridiculously high。Yeah。

 just we're going to deal with this later。 but right now。

 this is the general intuition for how how these pointers are printed out。

 So if I scroll up a little bit， you'll just see we print out the dereferenced pointer at that essentially take that memory address and then we dereference it based on the index that it currently is。

 so we just bump up the index one。 we jump ahead 32 B or 4 bytes and then we print that value out each time and you see that vertically here。

嗯。I just。When that again， efforts it cleared。You'll see that it's just like vertically just just skips ahead as we'd expect and then this pointer which is just that memory address。

 and then I just put this out for testing sake。 you don't need to worry about that。

 but yeah this is the general intuition on how these things are laid out of memory So number six is an interesting one It kind of goes back to example number two or we have this we have this value and then pointer pointer point just stacks up that's essentially what six is So we have these two arrays array1 and2 and they're essentially just these vectors or these these arrays 1。

23，4 and then we have an array25，6，7，8 and then we just have an integer pointer to those arrays。

And then we store another， you could say array， I just name a matrix to differentiate and we store those pointers essentially on top of each other。

 So what it looks like is we have this we have this matrix， So it's pointer1 and pointer2。

 pointer1 is the its it's the pointer to that array。

 the array 1 and then pointer two is is the memory address for array2 So essentially what we have is if we if we look at this this array of like this matrix。

 it is pointer1， pointer2， if we flip it。 So instead of like this and this we stack them on top of each other。

 So it's pointer1 then pointer two， it actually looks like a matrix。So you'll have your array 1。

 which is one，2，3，4， and then the one underneath， which is 5，6，7，8。

 And so it actually is like a it's like a grid right And if we iterate through this。

You'll actually see we just essentially iterate through these so。We， we， we do J and4， and we。

 we print out the D reference matrix at position I。

 So that position I is going to give a memory address for。It's going to be， you know， number two。

Which is going to be these two arrays。And then we're going to dereference that。

 which is going to give us our actual values。 And then we're going to iterate this each time。

 of course， as the fore loop goes on。 and then we just do it next line so that it looks nice。

 So that's that's pretty much all I have for pointers。 We're going to jump into custom types now。

 which is more what I was talking about for this for these weird pointer sizes。

 We're going to dive into this。And I'm going to show you pretty much the equivalent of the torch dot long type。

 So you might have seen this before if you're you know I assume you have some knowledge of Python and Py torch。

 so I figured that's the best way to illustrate this。 We have this size T， this size underscore T。

 This is typically how you you write these out and C is you'll have whatever the type is and then you'll have underscore T to say that this is like a custom type that you made T is for type。

And this is specifically for like big， big numbers， right。

 So the idea here is this is gonna to be an unsigned long。 So you in't。Long， so。Int at Sviia。

 you int。64， that's what it's going to be。嗯。If we do this in in torch， you'll see。I Python。

Import torch。 and then we can make X。This。Just an array of inteters。

And then we go x dot D type We'll see a horseshot in 64。

 So it's just like that 64 bit precision that we want to store really big really big matrices right so especially in Kuda when you have like really。

 really big tensors that are occupying like multiple gigabytes like on my GPU I have 8 gigabytes of storage。

 So if we're using int 32 that。You might get some overflow errors。

 You might get some just some some unexpected bad behavior that is going to like mess with things。

 So you don't necessarily want that。 And that's the whole point of this size type。

 I kind of wanted to show you that this isn't so bad after all， so。You know。

 just to step through this， we have the same array that we went over last time we do this size T type。

 we use size and then size of array divided by divided by the size of an individual integer。

 so it's like the total size of this entire thing divided by the the size of each individual thing in it so you get the total length of the array。

And so if we go01 already compiled this， you'll see we get that five， right。

 so there's five elements in here。呃。We print this size out。

 I'll go over this this ZU part in a second here。But we get that output five and then this eight。

We print out the size of this。 So that's in that's in bytes， by the way。We， we。

 when we do like size of int， we， if we do like， let's see， print F。We'll just say， int size。

And then we'll go。Sure， in bytes， we'll do that。I just compiled this again。We'll see int size and ps。

 So this is an int 32。This just is an n 32 and it's 4 bytes or 32 Bs。 So when we have this。

 that means it's 64 bits just to put that in perspective there。 So when we go to this size T。

 we'll see it's an unsigned type def。 So we do a type definition unsigned So it's it's only going to be positive because we're storing like you can't have like negative size。

 That's the logic and then we have this long， which means it's going to be it's going to literally tell the operating system where we want 64 bits。

 not 32， we want it to be long。And then just the the size T type so we can actually go into this and we can see oh type def size type。

 and then we make this we declare this thing。 where did this come from Oh。

 right here long unsigned integer boom just like that super easy， right。

And I guess to sort of clarify like what the whole deal is here。

 we could just pop back to this link if I just open it on my second screen here and pop it over。嗯。

We can search for the。I'll make this a bit bigger。And go， can I make a bear。 There we go。

So if I go up。We'll see that we have this。 We have this。 We have this Z， and then we have the U。

 So Z is。Z is just going to be。I can't remember exactly what this is for。But then we have this U。

 which is essentially just the unsigned and right， So it the U is unsigned。

 and then we have this size T type， which is what the which is what the Z is for。 And then we just。

 we just map that out。 So you know， if we had a。If we had just a regular integer。

 it would still be size T because you can have you。It's still an manager。 You can do stuff with it。

 but when we have a U end。Then you know， it's just kind of explicitly。

 you're going to have the size T type。 So that that's kind of how we map things there。

 and we can use the Z followed by the U to properly print that out， to print out the type of that。

 So you know， you have all these other ones to like pointer di type。

But that's generally the intuition there。And then next up。

 I just wanted to cover declaring your own custom types。

 so you know we saw one in the standard C library， the standard ID C library。

 the standard definition library， whatever you want to call it the headers。

And it's also important that we can declare our own because we might even we might need to use these and we actually will use these later on in the course。

 So typically how it goes is you do this thing called a type def， which is a type definition。

 and for let's just say we're going to make a point， for example。

 it has X and a Y in their floating point values。 So we do this struct。

 which is going to have some elements inside of it， it's going to have some。

 it's going to have some of these， I guess objects you could say these items。

And it's kind of a float X and a float Y。 and then we we say this is going to be a type point。

 we do type definition， it's going to be astruct， and we're going to make that a point type essentially。

 and then inside of our int main here since this is already declared we can say a point type like you know you could like you would do an int P or something。

 we're just replacing replacing int or whatever that type is with point。

In order' making that variable named P。 and then we're populating it with some values here。

 So this is going to be our float X and our float Y。And then if we go you， size of point here。

 if I just compile this。And then run。You'll see size of point is 8。

So 8 bytes is four bytes plus4 more bytes， so each of these is a float 32 number that occupies four bytes in memory。

 so when you add these together， it occupies a total of8 bytes。

 so this point this point type is going to cover8 bytes or 64 bits in memory。

And then just as other C+ plus script is literally the identical to this so you can。

 you can declare things the exact same way in in C++ except you might just want to use like the I O stream instead of。

Like you maybe in C plus plus， you would comment us out and you would go include。Io stream。

And then you would use using namespace STD。And then， you would。Then you would see out that。

Identifier C is undefined。Okay， I guess not。 I don't know why that's not working。

 But but you get the point。 So very minimal changes。 So now if we pop over to type casting。

 I have two files in here。 So just just a single C file and then a read me。 So inside of here。

I have static cast， dynamic casts， constant casts and reinterpret casts。

 So we're only going to be covering these static casts because these are the safe ones。

 These are mainly what you're going to end up using， if any。 So in here， it's very simple。

 you have just a like， say， a floating point number 69。69。 And then we have we just declare an int。

 And all we do is just。Have this F。 And then we do brackets in。We we put these。

 we just literally put this right in front of it and that'll statically type cast the float69。

692 an int。 And what this will do is it'll just truncate that last part。

 So in memory in essentially in binary and bits， it'll be laid out as。It'll have that first part。

 So the first the first integer piece， and then it'll have the decimal。

 and then it'll have the it'll have it'll have the decimal bits afterwards。

 So it'll it'll be like that decimal and then after。

 So what it'll do is when it's when it's type casting。

 it'll just trunate this part and then give give us more precision for these for these essentially in 32 Bs。

 So that's essentially all it's going to look like It's it's just going to be 69。

It's not going to have any decimal places， it's going to effectively round down， you could say。嗯。So。

 if I just pop into。Allright。Qupt casting。And。Run this。You'll see we get this integer format。

Just truncated and then when we do a character， this is actually going to convert to ASI。

 So if you remember your ASII tables， I'll go in and bring this up on the side here。Aspy table。Oh。

 it's right literally right there。 Okay， askItable。 com。嗯。We can see that。

This one right here is an uppercase E， right。So。Uppercase E。Upper Caey。 Look at that。 How。

 How easy was that， right， It's not not crazy doing an integer to a character conversion。 So that's。

 that's all type casting is。 I'm not going to go over this extensively because it isn't like a crazy piece。

 We end up using inkuuta， but just to throw it out there and remind you guys of how how simple this type of thing is。

Another topic I thought was briefly worth touching on was macros and global variables。

 So we can we essentially have these basic ones like you know if if defined if not defined LF else and then end if So we're essentially going use these later on to declare hyperparameters and just different global things that we'll need access to that we don't want to just pass in as an extra know bloated function argument when you have like 20 arguments in a function。

 you might want to reduce that and just declare some of those locally so you can use them wherever you want as long as they're not changing or you're not doing anything you're okay right So like in this example。

 I do pi like uppercase pi and then we set that equal to a double right。So。呃。

We can do these functions too， so it's kind of like a lambda function， if you will。

 a Lada function of Python。 We do this area and then we pass whatever we want in。 So R is our radius。

 and then we do essentially the the radius is pi r squared。

 so we just do pi times r times R and we get that。 So it's just a little lambda function you can do as a macro。

And then we have if not defined radius。 So radius isn't defined here。 If and de。

 if not defined the radius。 And we set that value to 7。So it's going to be an integer 7。

 we end the if we end this this whole block and radius is a new now a declared macro equal to 7。

And then we have some if logic down here， so if radius you know it's bigger than 10 which is not let me define this so this this is like gray out it's not smaller than five also gray out and then else so it's just going to stay at  seven and then it's going to end if so we can do if logic in here as well。

And then if I just go ahead and pop out of this to。Macros， and we go GCC like this。We're going to。

Double。We'll do。Perfect。So area of circle with radius 7。Is going to be this much。 And that's。

 that's a floating point number， which we have here。 So this radius， I was not careful there。

 This radius is actually an inger type。 So we just set that back to D。And then it works flawly。

 so that's how you do macros pretty easy。This part is where my understanding gets a little bit fuzzy。

 I haven't worked with compilers extensively， but I have found some really good resources on the C and C++ compilers。

 so I've just provided some links here for you to go learn Gcc is the most popular C compiler so that's GnuU C compiler and then G++ is the same thing but for C++ so you know I have different articles on here from freecodecamp that you can go and look at so there's this one and then we have the other one as well。

What does a compiler explain for beginners so like an analogy。

 essentially just convert converting your machine code down to assembly。

 and you have all these representations in between that the computer will work with to help understand things better and then it'll convert that assembly code down to essentially the CPU instructions in bits and bytes。

 so binary ones and zeros and that'll get sent as essentially electrons and charges through your circuitry in the computer and that is what actually executes this stuff。

嗯。And then just the C C+ plus compiler is a little bit。Might be a little bit higher level。

 I know C++ is a higher level language than C。 But these are just like really good explanations that I can't really top myself without messing up。

 So I provided these links here。 hopefully this all make sense。

 but we won't really need to understand too much about compilers downstream。

 it's good to know what they're doing。 But in order to debug code。

 You just need to know kind of the architecture of what the compiler is， what it's doing。

 like where where it's putting stuff， not necessarily like all the math and representations happening。

 It's good to know， of course， but it's not needed to write functioning code。

 So we'll see that later on， Like we're just going essentially type in these compilers legs and all this。

 And that's what the next section actually is。 it's on make files。So make files are really useful。

 They're going to help you be more efficient about developing C C plus plus and coa code。

 So instead of going into here and just typing you know Gcc every single time and maybe maybe you have autocomplete like me。

 But either way， you just want this to be a faster process。

 And you want to be able to automate and have more control over what happens and just manage things better。

 make files is what you want。 So inside of make files。

 it looks really complicated and it's like learning this new language， but it's really not。

 it's not that bad。You can define variables。 So like GZ equals Gcc and order to use these I can just do dollar sign and then brackets and then put that variable inside the variable name inside and it'll just pretty much reference this when it's called this is a command by the way So you we'll see this in a second。

 I'm going to do a little experiment with the kuda script here but we just have this NVcc maps to the NviDdia couta compiler and then we have couda flags。

 So it is just a little thing that's like my GPU architecture we're gonna to see this later。

 you don't have to worry about this now， but this is just like my GPU architecture is a 8。

6 compute capability。诶。Or compute。Compatibility， I think it's capability。 Either way。

 this is just we could just have flags and we can just have more variables that we plug into this stuff。

 But if I go back to the re for this。We have these targets。Prerequisites。

 and then our commands nested inside of that。 So how does this work exactly， Well。

 I'm going to show you this just by pretty much example， so。If I go。If I go。

 I can actually delete this line。If I just go， make 0，1。Xton makes a binary here。

And then I can run this binary， and they'll say boo。This， this print F， just it's just print boot。

 like it works。 just from make 0，1。 So what we're doing is we have this make command。

 which is for make files， kind of maps there。 And then we have the 0，1 part， which is the target。

 So this， this is the target left side of the colon。 And then after is the prerequisites。

So notice how I remove that other part， the 01。c。This essentially means we're going to either confirm that this is or that this already existed or has been done。

 And if it hasn't， we're going to do it。 So you'll see that in these examples down here， but。

Just to fill in the rest so we have a bunch of things happening we have this we have this variable GCC。

 which is just saying， you know，s it's essentially just going。

 you know GCC it's just doing that and then we put this at sign in front of it。

Which means don't print this out in the terminal。 So if I just remove this。And go。

And just remove the at。And go。mean。And Ill， I'll just remove this for。

So that it makes the most sense。And then I go make at 01。

 you'll see that it actually shows us this in the terminal。What if I put an ad there。Then。

 it doesn't。Right so that just removes it。 that just makes things more clean and just it's like a best practices just easy to see things。

 You want to maybe like look at the ones that might do weird things and you just want to like ensure that all your variables are correct。

 but this is a very simple。 you don't need to print this out。嗯。

And then just jumping down to I number two here， so。呃。Number two is essentially the same thing。Oh。

I'm not even going to execute that。 We don't。 We don't even either run this。 And then 0。

3 is just the couta compiler。 So we do NVCC and then the kuta flags。

 So it's essentially what it's going to look like。 It's， it's it's going to go N VCC dash arch。

Get rid of that。And then。It's going to pass an O。0，3。See you that that's the binary。

 we want it to be。 And then。对。That's going to run。 and we should be able to go 0。

3 z and it's going to say boo from here。 right， So just just the same thing。

 we just include like coupa runtime in all this just to be fancy。 but it just。

 it just outputs the the boot math。嗯。Yeah， this this is this is a very simple example。

 So is essentially just converting。 it's converting these variable names and not printing anything out。

嗯。Whi go make a 03 and it'll do the exact same thing。 See it takes a little while。Same exact thing。嗯。

We have this clean command。Which is going to actually remove all these bin。

 So when we want to clean up everything and just， you know， make it nice and presentable。

 like we haven't done work。 Like what I'm doing with you guys is I'm deleting these binaries before doing the lessons because it looks ugly when I have more files。

 So I can just go。呃 make。Clean gone right， So that that's just like a very， very simple example。

 And it's just， it's just like make and then whatever the target is。Going back up to these ones。

These are a little interesting， so。0，1， underscore O P J， which is for object。 This is going to GCC。

It's going to take in this C code and it's going to output this O or this object file。

 So it's going it's going to essentially this， but it's just going to do object file instead of a binary。

And then this01 OBJ。 So this object execute run。That's going to take in this。

 this previous one as a prerequisite。 So that means this one has to already be complete。

 And if it's not complete， we're going to run it and make sure it's complete in order for this to work。

So。We're going to。Compile this object file into a binary。 So you have this like the C。

 the C representation， and then the object file， which we do here。

And then this one takes that new object file and converts that into a binary。

 And then we execute that binary on this line。 So if I go make。And then 0，1， O BJ execute run。

And we don't have any of these files in here。It's going to。

It's literally going to ensure that this is called first， because it hasn't yet。嗯。

So it's going to it's going to convert this E file into object。

 and then it's going to convert that object into a binary。 and it's going to execute that binary。

 So this is just。I probably overex things a little bit。

 but this is pretty much the idea on how you you can automate just C compilation。

 C+ post compilation， we're going to use this more for kuda scripts down the road。But that's。

 that's the general idea。 And then this phony part at the top might look a little weird。

 but this essentially means we're not going， we're not going to。It's just like a way to make。

Things easier to use。 make it。 so you don't run into errors I a decent explanation here。

 So say we had a make fail make file with a target named clean。

 So in this in this clean up command that makes everything nice again。

Suppose we have a directory named clean in the same directory as the make file。 So here。

 if we have something named clean， if we run make clean， make will not run the command。

 It will not run the command in the target clean， because clean already exists。Instead。

 it will see that the director of clean already exists and will not it will not run it。 So in short。

 we essentially take a bunch of mappings from target names to command。嗯。

Thats that's where this phony thing comes from so it's's like a phony if you will I don't know what the philosophy was behind that naming。

 but that's how it works。And then we have some just some other stuff in here。

 So I already went it over the at symbol。 And then there's this one， too。 So the the colon equals。

I don't think we use this in here。But equals is used for dividing variables。

 or it's called a recursive assignment。 So both use for dividing variables。 Both these are。

 This one is a recursive assignment。 So value of their variable is reevaluated each time it's h。

And then this one is a simple assignment or immediate one。

 It's evaluated only once at the point of definition。

 So this is like typically the safer option you want to go down。

 If you get really complicated make files， you might end up running into weird things with these recursive assignments。

 So generally， it's safe to use these ones。 but it looks， it looks a little funny。

 So I didn't include it in this example。 We will， we will use it down the road though。

So last but not least we have debuggers So debuggs are awesome for just an alternative to just adding print lines just print this print that。

 did we make it here， Yeah， we made it we failed whatever just adding those just blows your code up。

 So having debuggers makes that a lot easier on you you can actually go down to literal assembly and see where the electrons are in your code like in your in your script like what is happening on the hardware So debuggers are super useful and in particular。

 we're gonna to be talking about the GDP debugger for CN andC++ So use them for both。

 I'm not going to like explain these super intensely。

I don't feel comfortable in my own explanation for these because there's just a lot happening。

But there are some commands that you generally want to be familiar with。

 It's mostly just commands and knowing what to look for in your script。

 So I have these in the Read me file。 just， just with some explanations。

 But a really good overview is here。 So this is done from low level learning。

Has an advertisement here， but。Essentially， it's just a really good overview on GDP。

Just going into assembly and doing a bunch of cool tricks and debuing seat code that way。

 So I do recommend you watch。
# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P14：1 - Spring 2023 Discussion 04 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明发明。🎼Ba比。

![](img/783c8711a07d8ce4c849ab7048602008_1.png)

🎼And。🎼Yeah。

![](img/783c8711a07d8ce4c849ab7048602008_3.png)

![](img/783c8711a07d8ce4c849ab7048602008_4.png)

Hello everyone and welcome to CS6 Q and B spring 2023's walkthrough of discussion number four。

 which is about inheritance。 I'm switching things up a little bit today。

 so I'll be going through the content on notability instead of clicking through the regular slides they're on the website so I make a little like a few scribbles here and there on these slides that won't be reflected on the website but if you'd like a plain copy of the slides and you like to follow along you can find those just linked in the week for part of the data structures website Okay so before we begin some quick announcements that may or may not once again be relevant to you by the time that you watch this video so midterm1 is going to be this Thursday。

 February 9 of 7 to 9 PMm seating assignments should have been sorry not seating assignments room assignments should have been sent out so you should know which room you're taking the exam but not necessarily like a seat because we're not doing seating assignments this semester for midterm1。

😊，There is no lab assignment this week， feel free to show up to lab but it will be more of a project one Workday。

 so like the TAs and the AIs will be there to help you with Project one or to answer any conceptual questions that you might have before the midterm speaking of Project1 1A is due this Monday。

 February 6， 1 B a Radeck is due next Wednesday February 15 on the last part of the project Project Part C is due next the Tuesday after that which is February 21st and don't forget that the weekly survey3 is also due on Monday。

 February 6 okay？So now let's get into some content so first up we have classes so you might have heard like parent or child class here we're going to refer to them as subclasses and superclass so subclasses or child classes are classes that inherit from another class this means that they have access to all of the functions and variables of their parent class in addition to any functions and variables defined in the child class there's a very teeny tiny caveat to this they don't inherit private variables or functions of their parent class we don't really teach about access modifiers yet we haven't really learned about them in discussion for us so you don't really need to worry about them right now。

 but I believe Josh will cover it later in the semester which is when you can think more about access but for now you can kind of think about。

Child classes having access to functions and variables to their parent class。

 excluding the private ones， okay？So in the example over here。

 we have this dog class and we see these two arrows down to Corgi and pit bull and in this example over here。

 Corgi and pit bull would be subclasses or child classes of the dog class Okay。

 in an inversion of that super classes or parent classes are classes that are inherited by another class we are saying class a lot but up here we have this superclass dog and we have these subclasses Corgi and Pi bull that inherit from dog all right。

😊，So something that we'll often see inside of classes are different kinds of methods and sometimes you'll see some methods with familiar- looking signatures or similar signatures to each other so the first kind of thing we see is called method overloading and it's done when there are multiple methods with the same name but different parameters so as an example you might see this public void bark at which takes in a dog and Prince w it's another dog and you might also see a bark at CS62 andB staff that printwoof what is this so they are both called bark at but they take objects of different types right they have two different parameters。

😊，And usually we think about method overloading in the context of like the same class。

 So let's say this bark at belongs to like the dog class。

 the dog class might also have a bark at that barks at a CS 61 B staff object as well Okay and a little bit of food for thought like。

Why do we even have method overloading Like what is the use here and I think a good example of this is system do out dot print So maybe you've like encountered this maybe you haven't it's totally okay if you haven't。

 but maybe you've noticed that when you call print normally we would call print on a string right but also if you passing an integer to system do out dot print it'll print the integer for you versus I think in Python if I'm recalling correctly you always have to print a string so like when you want to print an integer it would be like print STR the integer right you make the integer interesting string and you print it that way but in Java。

When we run print， it'll print an integer and it'll also print a string and it'll print a flow。

 it'll print a double things like that。 So the idea here is that there isn't one system do out print method that's just magical and takes in that takes in like variables of all types it's actually that system do out print is an overloaded method in Java so there's a system out print that takes in an integer and another one that takes in a string and another one that takes in a cha and another one that takes in a double and that's how Java figure out which which functions are called based on the type of the variable that gets passing so it's really useful for us when we want to generalize like a function like print which is so commonly used to variables of lots of different types okay。

On the other hand， method overriding is done when a subclass has a method with the exact same function signature as a method in superclass and it is usually marked with the override tag so remember how up here I mentioned that method overloading is often thought about in the context of the same class method overriding is often thought about in terms of like a superclass in a subclass having two methods that have the same signature so for example remember how up in the previous slide we have this dog class and Corgi was a child class of the dog class if we have in the dog class public void to speak in the Corgi class which inherits from dog we might also have a public void speak so you'll notice that they have the exact same function signature right it's called speakak and it takes no arguments。

😊，One more thing about this override tag I had a really great question during discussion from one of my students this week that I thought I might share with you all they asked what the purpose of the override tag is and so the purpose of the override tag in Java is basically to tell Java that whatever is below this override tag we're expecting this method signature down here to be found in the parent class and what I mean by that is if you put an override tag in the Corgi class it's going to expect that whatever function you put down here is going to have an exact match in function signature in the parent class。

😊，So if we if we were coding up this corgi class and corgi like inherits from dog and we were doing this in intelligence or something like that。

 if we had an override tech and we did like public oops and we did like public，Actually。

 now let's do like override public void bark。And let's say the dog class doesn't have a bark method In would be like wait wait wait this doesn't make sense to me you told me that I'm going to be directly overriding this function called bark but I don't see a bark I don't see a bark method inside of the dog class so it's basically just like a failsafe that's put in place for you to ensure that like you know what you're overriding exactly in Java and at any given time that being said though an override tag once again it's just a failsafe it's not a requirement when you're actually overriding a method you don't actually need the override tag but it's good practice and you should do it anyway okay。

😡，Cool。Now we have interfaces which are a little bit different from classes so interfaces are implemented by classes okay so we use the implements keyword when we're inheriting from an interface so they describe a narrow ability that can apply to many classes that may or may not be related to one another they do not usually implement the methods they specify we'll talk about this in a bit as to what that means but can do so with the default keyword interface methods are inherently public which must be specified in the subclass that implements them。

And remember that subclasses must override and implement non-deult interface methods One last important thing is that interfaces cannot be instantiateated so if we did something like a friendly f equals new friendly where friendly is an interface that's not going to compile because Java is going to see this and be like this is an interface like this is friendly I know that like an object can be friendly but like what does it mean for us to instantiate a friendly object doesn't make sense so Java is like you cannot instantiate an interface okay。

And as an example down here you see that we have these two classes CS6 UB staff and we have dog and we have these two interfaces in these dotted boxes that say friendly and cute CS6 UB stuff implements the friendly interface and dog implements both the friendly and the cute interfaces okay and so this is what will you mean by describing a narrow ability that can apply to many classes that may or may not be related to one another like CS62B staff and dog are ostenenssibly like not related to each other right but they are both friendly which is why we say that this is like an ability that。

😊，might pertain to multiple classes that don't seem to have any other real relationship and I could like go off on a tang into like interface design and like picking between like an interface versus like a class and like when to inherit from a class or like an abstract class but i'm not going to do that right here all you really need to know is that like an interface just defines some kind of behavior and I think a good example of this that you've already seen is like。

😡，With abstract data types right which you saw in like discussion two and homework zero this idea that like the list interface。

 for example right like there are many different kinds of lists like array lists linked lists so on and so forth right they all have the same behavior it's just what's how they're implemented that's different like you know that an array list you can call get you can call add same with a linked list you call a get you call add because we know that these are the kinds of behaviors that a list should have right so that's the ability that we're referring to the interface tells us what we want something to do but not how to do it okay。

😊，So a little bit on the difference between interfaces and classes because I think this distinction tends get a little lost sometimes but a class can implement many interfaces and extend only one class so you'll see up here that we had our dog class that implemented both friendly and cute right and the reason for this I think the design behind this when like the creators of Javaba were doing this were like oh okay like we can。

😊，We can like have as many interfaces as we want attached to one class because interfaces describe like a very narrow kind of ability right versus the extension of a class that's like direct inheritance that's like as an example like a Corgi is a type of dog right it doesn't make sense for Corgi to extend from another class。

And then like I mentioned previously interfaces tell us what we want to do but not how and classes tell us how you want to do it so classes actually implement methods right and interfaces can have empty method bodies that must be filled in by subclasses or default methods that do not need to be overwritten by subclasses and we will see this in a bit in question one okay and then with the extend keyword subclasses inherit their parents instance and static variables not including the private ones like I previously mentioned but you don't really need to know the details of that right now they also inherit their methods which can be overwritten as well as nested classes but they don't inherit their constructors if we want to refer to anything in the parent class we can use the super keyword and then we'll see this in question two on the worksheet but what I mean by that is。

We don't we don't inherit the constructors， so let's say we have public。Class4gi。Extends。Dog。嗯。

Let's say the dog constructor takes in like a string， like a name。

If we have the Corgi Conor take a string name as well， like string。namee。

If the dog constructor does everything we want like a quagi to have at instantsiation。

 then we'd be like， oh， okay， then there's no need for us to really。

Repeat ourselves there's no need for us to like rewrite the body of the dog constructor。

 we can do something like this。Where super refers to the parent class of Corgi and so this is basically saying hey call the parent classes' constructor for me on name okay that's all you really need to know about super this week and then you won use it exactly this week but just a bit of terminology for when you see it on the workssheet in question two okay。

Cool。So next a quick note about implementation， so if we have this diagram over here。

 we would see that we have an interface called Q and an interface called Friendly right in these dotted boxes over here。

 we would say class CS6 be stuff implements friendly right because friendly is an interface we want to implement an interface and then class dogg implements cute and friendly and then dog we see over here there'sarrows from friendly and cute which are interfaces and because their interfaces classes can implement many interfaces right but they can only extend one other class which is what we see down here class coordinate sends dog and class pit bull extends dog and just like a quick reminder that。

😊，When we implement an interface， the class that implements the interface must fill in any of the methods that are not default in that interface。

What I'm mean is like， let's say friendly has。Let's say friendly defines a function called is friendly。

 This is very silly I know， but trivial example just so you can envision it。

Let's say this function is declared inside of the interface friendly body so you'll see that it ends in a semi colonlon there's no brackets。

 there's nothing that goes inside of its method body that doesn't have one so that means that because CS62 andB staff and dog both implement friendly they have to define and implement their own definitions of is friendly so maybe in CS62 andB staff wed see something like at override I don't want to forget my override tag we do something like public。

Bolean。Is friendly。And then we feel listen， that's what we mean by。

Classes that implement interfaces need need to fill in those empty interface bodies。Method bodies。

 yeah， there you go。Okay so now that we've learned a little bit about inheritance and interfaces and classes。

 things start to get a little bit interesting when we consider static versus dynamic type so in the beginning of the course maybe in like discussion to we talked about how Java is a statically typed language Java is a compiled language and basically what that means is that when we write code in Java we have to tell the compiler exactly what type each variable is what each method returns so on and so forth right which is why we have these like declarations variable declarations that have types attached to them so。

😊，There is a difference between what we consider the static type which is relevant at compile time and the dynamic type of a variable which is relevant at runtime or when your code actually executes so a variable static type is specified at declaration like what we see over here whereas its dynamic type is specified at instantation for example。

 when using new I like to think of it like the static type of a variable is whatever is on the left hand side of the equal sign and the dynamic type of a variable is whatever is on the right hand side of its equal sign so over here we see。

😊，That this variable D itss static type is dog on the left hand side of the equals right and on the right hand side of the equals we see that its dynamic type is cogi so the static and dynamic type of a variable have to complement each other or else the code will error and what we mean by that is over here we'd like to we' like to generalize this with a rule of thumb of given this left hand side equals this right hand side is the right hand side guaranteed to be a left hand side and if you are following the example from above or you just know by intuition you'll see that the right hand side is a coregi and we'll ask ourselves is cogi guaranteed to be a dog。

😊，Well， yes， if you knew that like a Corgi was a dog。

 but also because of what we did up here where we explicitly said that Corgi was a subclass of dogs。

 so a Corgi is a dog as Josh would probably put it in lecture or they're in like a superclass subclass relationship。

 parent and child class， okay。So coming back over here。

 another way to think about it that I've talked about in the past with my students is let's say I'm going to redraw the hierarchy over here。

Orggy。劈过。I like to think about it in terms of like at the very top of your inheritance tree。

You have a very large box， and each time you get further down the inheritance tree。

Everything gets represented by a smaller box。So。Let's say we have this variable D。

And we say it is of type dog so it is this large box over here Okay so when you ask yourself。

 can I put a corgi into my dog box right like if a corgi is on the right hand side of my variable and my left hand side is a dog will it fit how I like to think about that is oh I know Corgi is further down the inheritance tree right so I have a smaller box and therefore I can put the smaller corgi box inside of the larger dog box。

I can do the same thing with Pi bull， right， I can put the smaller pit bull box inside of the bigger dog box。

However， what I may not do is， let's say we had like Corgi C equals new dog。For example。

 this line down here， if we have something like this。We'd have， like。This little Corgi variable。

And we'd ask ourselves， is dog guaranteed to be a corgi。

 Can I put my really big dog box inside of this corgi box and then it will realize that oh。

 actually my corgi box is smaller than my dog box right a corgi is more specific than a dog。

 therefore I cannot do that and this line will not compile okay。😡。

So one more note is that though interfaces cannot be instantiated they can be static types so as an example you could say cute C equals new corgi and remember how up earlier in the example we defined cute to be an interface that's what we mean here where the interface is the static type right it's the type on the left hand side of the the equal sign it just can't be on the right hand side of the equal sign it cannot be a dynamic type okay because we can't instantiate an interface and this works because Corgi inherits from cute right like corgi implements cute so we know that a corgi is something that is cute and that's why this works all right。

😊，So next we'll move a bit on casting， this is not in scope for midterm one。

 but I am covering it in this discussion because this is going to be the only week unfortunately that we really formally get to cover casting and it is kind of important and casting allows us to tell the compiler to treat the static type of some variable as whatever we want it to be the important thing though is that the cast needs to have a superclass or subclass relationship and I'll talk a little bit about that when we go through this example if the cast is valid for that wine only we will treat the static type of the casted variable to be whatever we cast it it to okay。

So let's draw this out a little bit。So in this example over here I have the variables A， D， and C。

 okay， and then I'm going to draw the little hierarchy， so let's do the hierarchy over here。

 so animal is this parent class and its child classes are dog。😊，And cats。Okay。

 and then I'm going to say like。Animal A。Maybe like dog D and cat C。

 so this animal is pointing off to some dog somewhere。Dog D is pointing to whatever A is pointing to。

Actually， I'm not going to draw that arrow because it' it's going to arrow。

 but I'll talk a little bit about why and then cat C points somewhere to a new cat， okay。

So first off in this line we have animal a equals newde dog if we say is our right hand side guaranteed to be a left hand side given this hierarchy over here is a dog an animal yes it is so we're good oh I just realized that my I think my zoom I think my zoom little square is blocking this so。

😊，Let me shift this over a little bit。Okay。Okay， I think that's better， awesome， yeah。

So we can say that a， even though it's a static type animal because a dog is a kind of animal。

 we can point a off over to a dog in memory okay， however。

 if we come to this line and we see dog equals a， we're going to get a compiler error and the reason for that is because at compile time we care about the static types of our variables only and what I mean by that is over here we know that a static type is animal right。

😡，And even though its dynamic type is dog at compiled time。

 we only look at the static types of the variables。

 So here we're saying trying to set this dog D equal to some animal that's in memory。

 we don't know that it's dog during compile time though right we only know that a is static type animal so that it's effectively saying on the right hand side we have an animal on the left hand side we have a dog and we're going to ask ourselves is an animal guaranteed to be a dog and the answer there is going to be no so we're going to get a compiler error okay so basically this line doesn't work or this line doesn't work。

However， if we do something like this， dog D equals a cast it to a dog。

 we're telling Java that for this line only I want you to treat a like it's a dog， okay。

 and what that's going to look like is it's going to see a is a static type animal and it's going to see that the cast type is dog and the compiler is going to ask itself。

Could an animal animal feasibly be a dog， Is it possible that an animal is a dog， right and？😡。

What I mean here by this superclass subclass relationship is they just need to be in some kind of hierarchical ancestral relationship with each other。

 the cast type and the static type of the variable that you're trying to cast right so we ask ourselves is the animal could it be a dog it might not necessarily be a dog but could it be an animal could be a dog right so we let this cast slide during compile time。

Okay， and then at runtime after the code compiles， we luck out because we're like oh cool like actually even though you told me that a to treat it like a dog during compile time。

 it turns out that a actually points to a dog in memory so we're good a dog cast to a dog great。

 sounds good to me。😊，And then in the next slide， if we do D equals new dog。

 so this points off to a different dog in memory。If we do in this next line over here。

 a equals D cast to an animal， we'll see D D is of static type dog at compile time if we try to cast a dog to an animal that definitely works because animal and dog are in a hierarchical heart hierarchical parent class the child class relationship right we know a dog is an animal so this cast is good for us at compile time and at runtime it also works because we're like hey cool over here we have this animal right？

A is of static type animal and you're telling me that D is an animal at compile time。

 that's fine with me Anim is an animal， and then at run time。

 it all works out because even though D is actually a dog， a dog is an animal cool awesome or good。

And then in this line， we set cat C equal to some new cat。😊，Now。

 when we get down to this line here where we say D equals C cast a dog。

We run into an issue because C is of static type cat and we're trying to cast a cat to a dog right but dog and cat have a sibling relationship even though they're both types of animals they're not in a superclass subclass relationship right so this cast does not compile and we're going to get a compiler error okay。

😡，And then in the next slide if we do something like a equals C， let's check the validity of that。

 so a is static type animal C is static type cat if we set a equal to C that's kosher for us because we know that a cat is a kind of animal so we can totally do this。

😊，And finally， when we get to this last slide，re we're going to encounter something very interesting called a runtime error。

 which is only really possible with casts when we're doing。😊，These kinds of like variable matchups。

 Okay， so this cast compiles during runtime Oh sorry。

 oh compiles during compile time because an animal could reasonably be a dog。

 So what I mean by that is over here， we know that these static type is dog。And then over here。

 we have this variable a which is static type animal and we're trying to tell the compiler to treat it as a dog。

 so when the compile comes across this it sees that a is an animal and we're trying to cast it as a dog and we're like。

😊，Is there a superclass subclass relationship could an animal feasibly be a dog and we're like， yeah。

 an animal could be a dog it's not necessarily a guarantee but it could be so during compile time job is like okay。

 I'll let it slide and we can figure this out later but for now you get a pass you get to compile。😡。

However， during runtime， when we're looking at the dynamic type。Of the variable。

 we're going to revisit this cast and say， hey。I have this variable A and I know it past the it past compile time check like the compiler said you're okay for now。

 but during runtime when we're concerned with the dynamic type of a a's dynamic type is actually a cat right this is pointing to a cat in memory and we're trying to cast a cat to a dog which doesn't work as like we did up here right because a dog and a cat are in a sibling relationship so that cast does not work at runtime so that's the difference it passes that compile time but it doesn't pass at runtime and how I like to think about this is a compile time we ask ourselves is the cast possible。

And then at runtime， we ask ourselves， is the cast true？Okay。

That's how I like to think about casting。So。That what we talked about with like the matchup of like static and dynamic type is pretty complicated。

 but it can be pretty much summarized into a set of ruless when we do something called dynamic method selection which tends to be like one of the most difficult one of the most difficult topics for students in 6 andv because it's just really confusing and honestly it's mostly stems from the fact that like Java and statically typed languages and there are limitations that come with that okay？

😡，So at compile time， your computer only cares about the static type of the invoking or calling instance。

 what we mean by that is like let's say we have some animal A equals new animal。

When we do dynamic method selection， we're concerned with things like A dot greet。Um，C。

 let's say like C is like new cat。I know its like horrible syntax， but this is just an example。

So at Dyn methodth selection at Compile time we only care about the static type of the invoking your calling instance。

 so we only care about the static type of A here which is animal right actually I'm going to spice this up let's make this like a dog or something。

😊，Cool。So what we do during compile time is first of all we check for valid variable assignments which is kind of what we were doing up here with the casts right is the right hand side guaranteed to be a lefthand side then we check for valid method calls only considering static type and static type superclass this is so so important because I think this is something that students sometimes get lost in the sauce on they're like wait but what about the dynamic type no at compiled time we only care about the static type of a variable okay。

😊，Then we want to lock in the exact method signature as soon as we find adequate one traversing parent classes as we go if necessary。

 so what we need to deny that is we if we don't find an appropriate method in the static type of the calling variable then we'll go up to the parent class of that variable until we keep until we find the method that we want and if we don't find a method that we want we throw a compiler error okay。

😊，Then at runtime， we care about the dynamic type。Of the invoking or calling instance so if the locked in method is static the locked in method that we found during compile time if it's static we're going to skip these following steps and just run the method that we locked in during compile time if it's not static then we want to check for overridden methods in the dynamic type of the invoking or calling instance so in the example over here。

😊，We'd look inside of the dog class， okay？And when we want to check for overwrittendden methods。

 we mean does the lockedin method signature have an identical method signature in the dynamic class or the dynamic class's parent classes？

And if we do find one， then we want to run the new one that we find based on a dynamic type during runtime okay and if we don't find one that's totally okay。

 we'll just run the one that we locked in during compile time Lastly we also want to ensure casted objects can be assigned to their variables which is kind of once again what we did above with these like casts over here okay。

So dynamic method selection is like super confusing and like last semester I made this like giant flow chart about like variable assignment rules and method call rules and this is like a lot to take in and some of these like rules are a little bit of overkill for the way that we're taking DMS this semester but I'll leave I'll probably pull up this like diagram when we're doing the actual dynamic method selection problem which is question two on a workssheet just so we can work through a flow and get used to what we're looking for here okay but I believe with that that's the end of content review。

😊。

![](img/783c8711a07d8ce4c849ab7048602008_6.png)
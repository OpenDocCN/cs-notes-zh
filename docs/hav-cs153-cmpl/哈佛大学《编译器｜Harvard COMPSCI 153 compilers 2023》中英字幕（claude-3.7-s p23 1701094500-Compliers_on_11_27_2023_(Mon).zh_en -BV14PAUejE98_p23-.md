# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p23 1701094500-Compliers_on_11_27_2023_(Mon).zh_en -BV14PAUejE98_p23-

The samebri。As has come up on， it， although we've been talking about some ideas。

About register allocation for those who are implementing it in homework six。

It's going to be hard to actually implement all of the ideas we talked about in part due to the interface of register allocation。

 but also due to the limitations that we have on L O VM light。

 where we don't actually have what are known as fine nodes， which are a way of。

Making sure that we can have local。Mutable local variables represented in SSA form。

 If you're interested in that， you can definitely look it up or post on an edit all point for reference。

 fines used an L VM， but we don't have an equivalent in our L VM light， which means that in oat。

 all of the local variables end up getting put into。Directly into。

Into stack slots for those who are working on the register allocation and you'd kind of like to see and participating in the leader board and wanting to see that。

 you can definitely submit。LLVM light code that you'd like to see put through your register allocator for performance reasons。

 so that might give you a wider range of LLVM code。

For your register allocator and optimizations to address rather than just what can be produced from the Oat front end。

Okay。Any questions？On the Eddmund side。hoomework。诶。

I will go over the final exam details and information structure in the last lecture on Wednesday next week。

Okay， so。The last few classes we are just going to touch on a whole bunch of different topics for today。

 we're going to be looking at object oriented programming and in particular。

 how to compile object oriented code。😊，Who？Kowose what object onient codes。They'll feel they do。

I guess people encountered it very lightly in 51， not in depth。 I will say。

Probably my equivalent of CS 51 we know was an undergrad was actually。You know。

 design and abstraction and computation was actually really all about object oriented programming in C++。

 so essentially it spent a semester digging into object oriented programming。😊，嗯。It's。

 I think a very effective way of designing computer systems at scale。

 The key idea is that it's built on an idea of objects。

 and you should think about an object as containing both code and data。That is。

 you've got the data to represent。An object， often so a concept like the information say for a person or say the information for a course or whatever it is you're representing your system。

The key the idea of object oriented programming is that together with that data also comes the code for using that data for manipulating that information。

Now in non objectject oriented systems， these things are typically separate。

 right your data would be instructs in records or something。

 and then the code that uses that data is written elsewhere in files that might take one of these things as an argument and so on。

The idea of object oriented programming is that it's in many ways， natural to think about。

 not just how we represent an entity with data， but also。

It's closely coupled with the things that you can do with that entity。

 the code that manipulates that data， and so being able to put them together and having language constructs that allow you to easily tie those things together turned out to be a really great way to model entities within your program。

There's a number of other things that object oriented languages typically have some form of encapsulation。

 information hiding to support modularity， so that is you can。When you think about an object。

 code and data， some of that data and some of that code might be public。

 might be available about things you could do with the entity and others might be really just implementation details。

 very similar to an OCMl module， how it has an interface and implementation details。

Many object oriented languages also support。codeode reus via inheritance。

 the idea that from an object or a class， you can inherit code from another object or class and thus reuse the code。

Thiss two main families of object oriented languages。 One is known as prototype based。

 and this includes JavaScriptscript and its variant and Lua as well。呃。Versus class based O languages。

 which include things like Java， C++， C sharpp， Python as well。In this class。

 we're going to be focusing on compilation of class based object oriented languages。呃。We'll touch。

 I think， towards the end of the class on prototype based。As well。

 once we have a better understanding of class based。So object oriented programming， it started。

As a concept， it kind of was introduced in the early 1960s。In a variety of languages and programs。

 notably sketchpa in Simcrt， but it really took off in the late '60s with S。

 which crystallized a lot of the ideas that are in use today of classes， objects。

 the idea of subclass， the idea of dynamic dispatch， which we'll be talking about very soon。嗯。呃。

Small talk was a key language in the development of object oriented languages introducing。

I think some of the principles of object oriented programming。

 this idea of combining the code data and encapsulating it。呃。Together。

It continued to develop Moular 2， later Moular 3， EFiffel was another significant language that also introduced a notion of contracts。

 which is。呃。A powerful mechanism for runtime checking of specifications。

That we are not digging into in this class， but are very interesting。

But it was in the 90s that object oriented programming really became mainstream with C+ plus an extension of C with the object oriented ideas and various other features。

 but also definitely the Java programming language and these were，嗯。呃。

So this was the object oriented was some of the buzzwords of the 90s that if your language was object oriented。

 was。Very。Very hot。Okay。Let's jump into some of the technical details of object oriented programming。

 in particular， let's talk about classes。The way to think about a class is that it's a blueprint for objects。

So the idea is that an object is around at runtime。And it will represent a specific entity。

So for example， if we have if within our systems， we are using object oriented programming to model students and the classes they take。

 there might be one object per student。Okay， so that object for the student will include data。

 things like your HUAD， name， address， whatever else you want。

But all of these student objects are kind of similar to each other。

 right they're all going to have the same fields， even if they'll different the values。

 the same methods， the same code that you can do with them。

And the idea is that a class provides a template， a blueprint for us to be able to create these objects。

So that is， even though we might have thousands of student objects around。

There might just be a single class that we use to instantiate or to create these student objects。

So the class as a blueprint for the objects is going to typically describe what the fields。

 what the data is for a given object of that class。

And even though the values may typically the values will be different from object to object。

 many object oriented languages are mutable， so that is the fields of an object can change。

 but doesn't have to be the case， you can definitely design pure object oriented programs。

 programming languages where once an object is created， those fields are immutable。嗯。Okay。

 so the class is going to contain。The fields， the instance variables。

 the data that is's going to be associated with each object， as well as the methods。

 the code that is going to be shared by all objects of a class。

Now it's when a class declares the methods。🤢，That every single object of that class is going to have。

 this is where you get to use inheritance。To inherit code from the superclass。That is。

 you might end up saying either explicitly or implicitly。

This method of objects of this class is going to be exactly the same code as。

This method from my super class。Methods are typically immutable in object oriented languages。

 but not always， for example。嗯。Let me。Rephrase this for class based object only languages。

 methods are typically immutable。 That is once a class has been declared and saying what its methods are。

 you can't at runtime change the implementation of those methods。

 You can only change the implementation of the methods by。

Creating a subclass and overriding the behavior。嗯。Talking about overriding。

 so this idea that we're going to have classes。Classes are going to inherit from other classes。嗯。

When you inherit or when you have a subclass。Of a superclass， you can overide methods。

 You can end up saying this operation and object for this subclass， it's going to be different。

To the implementation in the superclass， that is you're going to override the method and provide new implementation。

You typically can't override a field。Right， if the superclass。Has。

Information associated with an object。That continues to be associated with the object。

 You can't change the type of that field。 You can't say， instead I'm going to have a field。

 replace that field with something else， right， So fields typically can't be overridden。

a look at some Java code to try and make some of these concepts a little more clear。

So this is a declaration。Of a class called vehicle And the intent here is that we're using this class to model。

Vehicles in the real world。嗯。In Java， every class。Extends or inherits from another class。

So here we extend object。The one exception is object， which doesn't inherit from anything。嗯。呃。

Here we see in this。Class declaration， we have one field called position of T int。

The initializerizer zero here means that when you create a new object of this class。

Every object is going to have a field called position。

 and the initial value of that field is going to be zero。Okay， so here we are。

Talking about vehicles in a one dimensional space， so they have a position somewhere in this one dimension。

In this declaration we also have a single method called moveve。It doesn't return anything。

Is the void， but it does take an integer argument， X。

 and the idea is that it is going to update the position， adding x to the position。Now。

 in Java and many object oriented languages， you often have a keyword， this。

 which refers to the current object。So that is when a method is invoked。 Remember。

 every object has both code and data associated with it。 when you invoke a method on an object。It's。

A specific object， often known as the receiver object。嗯。

Is referred to implicitly with this this keyword。Okay so this is， so if you invoke。

 move on a given object， it's going to update the position of that specific object。

Any questions so far about the syntax or the concepts？Of this Java class declaration。Yeah不但脆嗰啲。

The syntax for creating a vehicle would be。The expression， new vehicle。Open and close parenthesis。

 And at runtime， that would create an object of the class vehicle。 We'll be seeing some examples of。

 of this。I don't think I have any examples in my slides but。In addition to methods。

 classes can have special kinds of methods called constructors。

 which help you construct an object and constructors can take arguments。

 so when you call new vehicle，You might be passing an argument to the constructor。

 which might use that to initialize the new object。嗯。Yeah。My， yeah。

Remember and where you joblin JavaScriptscript or prototype please？Java is a class based language。

 Java scripts， you are correct， is a prototype based language。

So I'll talk about prototype based languages later， but in brief， they don't have classes。

 they don't have templates for creating objects。They use a different mechanism for inheritance and code reuse。

 but also in JavaScript you still have this idea of an object and an object containing data。

 so fields and methods， code that can be run。On that object。Thanks。Any other questions at the moment。

Okay， so that's our class vehicle We're going to have another class called Car which extends vehicle。

 so car is a subclass of vehicle vehicle is the superclass of car。😊。

Here in car we also have a field passengers， the number of passengers that are in the car。

 we're going to have a method called a weight that takes vehicles as an argument and essentially。

Is going to move vehicle V up to the same position as us， otherwise it'll do。Nothing and no up。

 the smooth0。Okay， so if we created an object of class car。It would have。Two fields。

A position field inherited from vehicle and a passenger field from car。

 it also has two methods on it。The method move， inherited from vehicle， and the method of weight。

So given an object of class car， you can invoke。Either move or a await。On that object。

reason to move by 10， or should that be0 Oh， sorry。That's so funny， I misread that。

 I thought it was a zero。I don't really care what the code does。Yeah。

 it's moving forward at 10 units per。Unit。So， yeah。

 and magically transports the other vehicle up to its current position without moving。 So， yeah。

 this is a very accurate model of the way the real world works， which is important when you're。😊。

Okay， here is another class， truck， this extends vehicle。

 so truck is a subclass or vehicle and it overrides the move method。😊，And as you can see。

 it is limiting how much it can move， how many units it can move in a given invocation of this。

 So it's only going to update the position if x is less than 55。Yeah， Luke。

 generally think a function is being over doesn't either have the same arguments and about Yeah。

 great question。In Java， yes， it needs the。We'll touch on this later in the lecture。

 but essentially it needs the same arguments and the same type of the argument。

I think later versions of Java allow the return type to be covariant。I think。I can't remember。

But yes， we'll get into later。Some of the specifics about what it means to override。Okay。

So we've talked through a few of this， every vehicle is an object。

 so if I have an object of class vehicle， that's also an object of class object。

 every car is a vehicle， so that is every object of class car is also an object of class vehicle。

 every truck is a vehicle。嗯。And so what that means is that every vehicle and thus every car and every truck has both a position field and a move method。

😊，Car also has a position's passengers field and an await method。嗯。Sorry， get me sick。

It was meant to have turned off。嗯。All right。O嗯。Because。Every car is a vehicle。This means that。

If you have an object of class car， that can be used anywhere that the program is expecting an object of class vehicle。

Okay， so this。Is。Similar to the idea of subtyping， and indeed in Java， subclassing is subtyping。嗯。

We'll dig into this a little more later。If you think about why this is okay。

 why a car can be used anywhere a vehicle is expected， suppose somewhere in your program。

 you'd ridden some code that was expected to be given a value of class vehicle。

 so an object that's a vehicle， what are the things you could do with it？



![](img/8e4111571a13adcddfe73fe8486b661e_1.png)

![](img/8e4111571a13adcddfe73fe8486b661e_2.png)

You look at the position field。You could invoke the move method。



![](img/8e4111571a13adcddfe73fe8486b661e_4.png)

Pass it off to somewhere else。 that's wanting a vehicle。 and that's about it。

And if somebody gave you。An objective class car。Well， that's okay， right。

 it does have a position field， so you could look up the position field of an objective class car。

 It does have a method move in addition to more methods。So you canvoke， move on it。Okay。

 so intuitively the subclassing。Car is a subclassus of vehicle and so car can be used in a rear vehicle can be used。

As weve talked about， truck overrides the move method。The syntax and Java for invoking a method。

 O dot move I invokes the move method of the object O。If O at runtime is a truck。

Then Odot move is going to invoke this code。The code for truck。

Now what's really interesting in Java is that the same piece of code， ODt move。If at runtime。

 O is an object of class。😡，Car。Then O dot move。 I is going to invoke the move method for an object of class car。

 which is。The move method inherited from vehicle。All， so that is this OOt move method。

I's somehow going to be able to figure out which piece of code to invoke。Based on the runtime。

Object O that is passed in。Any questions at the moment。

 kind of at this incredibly brief introduction to Java？The syntax and semantics of Java。

As we've talked through declaring a class。Subclassing， overriding methods， invoking your method。Okay。

So this is a compilers class， so what we're actually going to focus on is how to generate code。

For an object oriented language， so given this brief introduction to Java。

 hopefully it's enough for us to think about some of the challenges that are involved in compiling object oriented code。

So with respect to methods， one is how do we generate。The method body code。How do we invoke methods。

 How do we dispatch to the right code when， as I wave my hands about， the same bit of code。

 O dot move is somehow going to be invoking。Different code based on the runtime class of the receiver object。

Related to that to invoking methods is how we handle inheritance。

The idea that if we have a subclass it can inherit code， inherit a method from the superclass。

 how do we make sure that the correct code gets in vote？When we're dealing with fields。

 some of the challenges are how we lay out the fields in memory， how we get alignment。

Those are actually related in a pretty similar way tostructs。

 but we do also have to think about handling inheritance。

 that is we inherit fields from the superclass。 So how do we make sure that the layout is appropriate。

O。As we talked about。We need to somehow or other at runtime figure out which piece of code。

To dispatch a method andvocation to， we somehow need an idea of dynamic dispatch。

 dynamic meaning at runtime by contrast， static dispatch would be about at compile time。

 f knowing which piece of code is going to be invoked and just always invoking that code。

 we can't do that in an object oriented language instead we need some runtime mechanism。嗯。

So to kind of talk through this in a bit more detail， methods look like functions。

But let's take a look at the following code。 This is an interface in Java。

 so an interface is essentially a declaration of the methods that are available。

Interfaces are not directly tied。🤢，With a class， multiple classes can implement the same interface。

 So here is an interface for a set of integers。 So we have a method to。

Insert an integer to check whether an integer is present in the set and to get the size of the set。

We might have different implementations of the same interface， so here is a class in set one。

That implements in set。 and here we're using a list of vintages as the representation of the set so you can。

Read through and see how we end up handling it， but essentially。嗯。

Checking whether the list already contains the integer and so on。

We might have a different implementation of the same interface， so here is inset2。Implementing inet。

And this is using a tree data structure to represent。The set。um。Okay， so when and face。

Two different classes that implement that interface。 Okay。

 so inset1 is an inset anywhere that's expecting an inset could be given an objective class inet one。

In a similar way， an objective class inset2 is an inset anywhere that's expecting an inet could be given an objective class in set2。

So what this means is。嗯。Let's suppose this piece of code is expecting an inset。

 It gets one returned from the method fo。And then it invokes the method size on that inset。

So this piece of code needs to work regardless of which class it got given。

regardless of whether it got an object of class in set one or in set two。

Which means that when we're generating code。Set out size。We can't simply。

Translate this to calling the code for inset1 dot size。

That is the size implementation from Inset 1 or the size implementation from Inet 2。

 This client code doesn't know which piece of code。To invoke。So， somehow or other。The object itself。

The object set somehow it has to know which piece of code to invoke。

 The object knows what class it belongs to。And so the object is going to have to be responsible for invoking the correct piece of code。

So we need to figure out some way to make this happen。The solution to this problem。

Involves what's known as a dispatch table， also known as a virtual method table or a V table。

The idea is that。Every class。I is going to have a table， an array of function pointers。

And each method of that class is going to be at a known index of the table。

So to be clear about what this means。If we have an object， O。😡，Of class and sit one。

This is the representation for the object O。So in here it may contain things like the fields that you have for an inset。

 but one of the key things generally in the zero width offset of the object。

 is a pointer to the class information for that object。A key part of the information for that class。

 let's say， and see it one。Is going to be this dispatch vector， so for each method。

Insert has and size， there's going to be an entry in this table。

 and that's going to be a function pointer， so that's going to point to code。 So for example。

 for the insert method， it's going to point to the code， the implementation for insert1 do insert。

So whatever we translate that to to an L of the M like function。

That's going to be pointing to the address。Of that code。

To see this again a little more explicitly for this。Snippet of code and set， set。

So we have a local variable called set。That's going to be。

A reference to an object is going to point to an object。Here is the representation of the object。嗯。

From what we know about set， we know it's an interset， but we don't know what kind of object it is。

 We don't know if it's an implementation from in set 1 or in set 2。Okay， however。

 this class pointer table。This class point is going to point to。A dispatch table。

That has at each entry， at a non index of the dispatch table appointed to the correct code to invoke。

 So when we want to invoke size on set。We follow our set pointer to the object。

Follow the class pointer。From the object to the dispatch table， go to index2。

To invoke the size method。And what that means is。Whether or not the object is in set one or in set2。

 we're going to end up jumping to the correct code。

Any questions at the moment about this key idea of a dispatch table？So multiple different objects。

 and I'll share the same table。Yes， I have a slide on the s of bit。We might have many objects。

 all of the same class and they can share the dispatch table， so we would have many objects。

 all of which would have a class pointer to the same dispatch table。Okay。Great， so this is nice。

High level idea。It's a little more complicated， though， right， So we have this idea of subclassing。

We have this idea that。If。B is a subclass of A。And C is a subclass of B。What that means is that。

Every object of class B。😡，Is an instance of A。 So when you're in the program that expects an A might be given an object of class B。

So the dispatch table for B。😡，Somehow has to have the same layout as the dispatch table for A。

And similarly with。An object of class C， the dispatch table for C has to。

Fit the dispatch table for A and the dispatch table for B。Okay。嗯。There is， however。

 a pretty straightforward solution， which is going list。The methods in order。Of the。

they had declared in the class hierarchy。So， the methods from。Class A are going to be first。

Followed by the methods from Class B。Followed by the methods。From class C。And by methods I don't we。

Don't want the overridden methods， we just want the newly declared methods。

So if in our dispatch table， we list the methods in this order。

 this ensures that the dispatch table for class C also looks like a dispatch table for class A and it looks say a dispatch table for class B。

So to see that a little more explicitly。嗯。The dispatch table for Class A。

There's just a single method declared on aF。Which means that the dispatch table just has a single entry。

For the method food。A dispatch table for class B。Has entries for food， bar and bez。And for foo。

 bar bears and quacks。So what that means is。If somebody gives us an object of class C。

We look up the dispatch table for Class C that gives us this table here。

And even if the code was expecting an object of class B。The works out。

 we can look up the indices appropriately for the methods foo。

 bar and baz at the appropriate offsets。嗯。The nice thing about these dispatch tables is you'll note that the。

Aress we can use is really how we're implementing overriding right so for class B。

 we inherited the code for F。So the address we use in an objective class B for the F method is the same。

Code that we used that was declared in A， the address of a dot food。

 the implementation of food from class A。 By contrast in class C， we overrode。The definition of fo。

And so the address of the code to jump to is the。The code specific。To class C。That we implemented。

 so the address of C。fo。Okay， any questions at the moment about。Subclassing and dispatch tables。Okay。

Generating code for methods。 It's actually pretty similar to generating top level procedures。

 so like。In compiling C like functions， sea like procedures that you've seen already。

 it's very similar to that， except。Methods have the implicit argument， the receiver object。

 the keyword this， it's pretty easy to actually translate it。

 So the method bar declared an object of class B。Method bar that takes a single argument X。

 we actually end up translating it into a function。

 like a top level procedure that takes a new first argument。Called this of the appropriate class。

Class B。And so what that means is when we。ACompiling an invocation， as I say。

 Odot Barr passing in the argument 54。We end up translating this into code vets。

Essentially takes that。Object O。Appointer。It follows that pointer to the class pointer field。

Of the object。We use that to get the dispatch table， we look up the appropriate offset for bar。

 which we know statically because statically we know that O is of type B。呃。So that function pointer。

 we put it into F， and then we invoke that function passing in the receiver object O。

 and then the actual argument， 54。Okay， so we use the V table to get appointed to the appropriate function and then invoke that function。

With the receiver。Okay， as William pointed out。All instances of a class can share the same dispatch table。

This is assuming that methods are immutable， which they are in Java， C++。

And many other class based object oriented languages。嗯。

So the key idea is that when we are creating an object， constructing an object。嗯。We need to。Point。

The class pointer to the appropriate dispatch table。

But they can share the same one without any problem。As we talked about earlier。

These dispatch tables allow us to implement inheritance in a clean way。That is。If C， class C。

Extends class B and class C inherits the code of B dot bar。

 then it's very straightforward in the dispatch table for class C at the offset from the method bar。

 we simply point to the code that it inherits。So this dispatch table mechanism allows us to implement that inheritance。

 that code reuse in a clean way， it allows us to have the dynamic dispatch。In a pretty clean way。

As well。Great right， any questions about compiling methods？And classes。Well methods， really。Yeah。

 I guess one quick question about going back like compiling the table， I think in Java， at least。

 theres the ability to like implement multiple interfaces。So in that case。

 you use like a hashback instead。Yeah， that's a great question。Glossing over a lot of details。

 but essentially the way it works is an object is going to have a pointer to information about the class。

It's more than just a dispatch table for the methods。

There's going to be additional information ros for the class One is like。

Things like the name of the class and you just metadata about the class。嗯。

You're typically going to have one dispatch table for。The methods for the class。

And then for each interface that the class implements。

 you're going to have another dispatch table for that interface。 So the idea is that。

If you're static。Type of an。Of an expression is an interface。Let's say ins。

What you actually need to do is from that object pointer。

 you need to get your hands on the dispatch table for that particular interface for that object。

The way that would normally work is youd from that object， you would go to the class information。

From the class information from there， you'd have something like。Not quite a hash table。

 but essentially way for you to be able to find the dispatch table for that particular interface。

 and then you'd proceed from there。So， yes， you would also have。

More than one dispatch table for a given。From an object essentially based on what type you're using that object at。

I'll touch on it later as well， but in some languages you have what's called multiple inheritance。

In Java a class can only inherit from one super class。

In some languages you can inherit from multiple super classes。

And this can be challenging if both of your super classes， let's say， declare the same method。

The maybe has no relationship to each other。But it's got the same name and it's got the same arguments。

So you got some challenges in the language design to let the programmer know which method they're wanting to invoke。

 but also in the compilation， the idea is that a given expression。

 you need to find the appropriate dispatch table。In order to。To do the dynamic dispatch cleanly。

Thanks for the question。Okay， so this is methods。 We're kind of seeing how this fundamental thing of object oriented programming。

 the dynamic dispatch of methods is implemented。And in large part。

 some of the power of object oriented programming as a paradigm is really coming from this idea of dynamic dispatch。

 the idea being that I've got an object。There's something an action that I want to take on that object。

 moving it， moving its position。 The idea is that I invoke it on the object。

And the object knows how to take care of it。 The object knows which piece of code to actually invoke。

And this is where object oriented programming as a。Design paradigm， actually， really。

Is incredibly powerful to allow us to associate。The code with the data appropriately。

 clients of the object don't need to know what kind of object it is。

They don't need to know what subclass of vehicle it is they just get to invoke move。

And the object knows how to handle it。In addition to methods， objects have fields。

 So we need to be able to compile fields。 But tomerist is the same basic idea for fields as for methods。

 So that is given。Fields of classes。呃。The idea is that we would number them appropriately。

And essentially layout of struct。So that the representation of the data of a subclass。

Matches the representation of data of the superclass with some additional fields added。

 So this is very much like。With subtyping。What some timingim？

With subtyping ofs that we talked about when we talked about subtyping and compilingstructs。Now。

Because different objects can have different values。For the fields。

 we store fields on an object right so here would be a representation of an object O of class 3D point。

 The first element would be to the class pointer allowing us to find the dispatch table and other meta data that we need。

 but then the rest of the object would be the fields， the data specific to that object。

 So 2D point x 2D point Y 3D point Z。Generating code for the field access is。Pretty straightforward。

 X is going be represented as a point to the object。 We do need to know the static type of X。

 So if we knew the static type was say 2D point。 That's enough information for us to figure out which。

The offset for the field that we want to access。Yeah。Sore pretty straightforward。

When we create an object。The basic idea is that we are needing to allocate memory。

For a record that's big enough to hold an object of that class。

We need to initialize the pointer to the dispatch table or the the class information。

 we need to initialize the instance variable， and then we。

A new expression you C would evaluate to a pointer to the newly created object。As I mentioned。

 many languages often have constructs to help you with creating and initializing objects。

 so Java has these constructors， special methods that are actually invoked when an object is created。

So I've kind of talked about the key ideas for compiling。🤢，An object。

 if we think a little more concretely about how it compile to L ofVM。嗯。

It's actually pretty straightforward。During the type checking phase。

 we end up creating a class hierarchy so that is in the front end as we read through the information in the program。

 we would be constructing information about each class。

 its super class information about constructors， if we have the field and the methods that they have when we compile that down into LO VM IR。

 What we're going to be doing is，An LLVM IR struck type for each class。It should replace update this。

 that is an LVMstruct type for each class。嗯。Such that we'll be creating one of these new struct types for each object of that class。

We're going to have a  struck type for each dispatch table or the met information。

 the metadata for a given class that's going to be shared by all objects of that class。

And then we're going to have essentially top level procedures。

 top level functions that are implementing。The methods。

And that we're going to be using to populate the dispatch tables。So from this hand wave thing。

 the idea of how would use LLVM。To encode or to compile OO。

Object oriented classes down should hopefully be straightforward。And from that point onwards， it's。

Pretty much the same as。Other compilation of LOVM。I've。

Given a really quick and rough outline of object oriented programming。

There's a whole lot of extensions。I already talked about multiple inheritance。

 the idea being that a class could inherit from other classes and let's say。诶。

I think one of my favorite ones to use is let's suppose that we are modeling people at a university。

So we might have a class。Person to represent a person， there's a subclass。Student。

And another subclass employee， right， every employee is a person， every student is a person。

 there are things that you want， the fields of a person might include things like name and so on。

 but there'll be things that a student has such as expected graduation year that an employee doesn't have。

However， you might have a student worker。😊，So that student。

 you might have another class student worker that extends both students。And employee。Okay。

 and now you fantastic， you have an object that has both spent the graduation year and other things like tax information。

That you need。嗯。There's some interesting things involved here about how you end up。呃。

Having appropriate V tables。One particularly challenging thing is this thing I sketched out person。

Student， employee and student worker。So with a student worker， it inherits from student。

 which inherits from person。It also inherits from an employee that inherits from person。

There are going to be attributes， data associated with a person such as name。Should。

Student worker have one name or two names。That is， are the attributes of a person。

Common to both the employee instance and the student instance， or should they be different。

Turns out it depends what it is you're modeling right in this particular person example。

The intuitive thing would be that they share in this diamond inheritance。

 the attributes associated with a person via employee and a person via student。

 they should be the same attribute。But there'll be other situations where they should be different。

so ideally， if your language is allowing multiple inheritance， it should allow the flexibility。

To resolve those issues， that diamond and inheritance problem appropriately。 And then as I mentioned。

 you might need also ways at the language design level to help that resolve， indicating。

 let's say which method you're trying to invoke。 if you happen to have methods with the same name。

 same arguments that are unrelated to each other defined and。To unrelated classes。

Another key thing that we might be interested in when we're compiling object oriented programs is separate compilation。

The idea being that if you have。A large program。 It's going to be split up into different files。

 And you want to be able to compile files separately。 and then just at the very end。

 link them together or load them at runtime。 Now， this is a problem in object oriented programming since。

We might have code for a superclass and a subclass in different files。

And when we compile the subclass， if we want separate compilation。

That means we shouldn't really depend on information in the superclass。

The superclass might be edited， might be changed， might be recompild without the subclass being compiled。

 so this is a challenge because we were planning on using that superclass information to figure out the layout of our dispatch tables。

 the layout of our fields within an object。So to support separate compilation。It can be a bit tough。

 Some of the ways you could do it is。Not actually resolve those offsets until later on。

 until when you know the code that's going to be combined。At link time or at load time。呃。

Alternatively， you might just say， you know what， if you changed the superclass and you're actually changing some type information about it。

Well， then you're going to need to recompile the subclass。

 and it's because some of the changes to the superclass might， in fact。

 invalidate some things in the subclass， such as。Myethod overriding， right？Another extension。Oh。

 prototype based languages。So I touched at the very beginning on this idea of JavaScript。

 Lua as two examples of prototype languages。The key idea with the prototype based language is that there is no class。

 right， There is no template for objects。Instead， the dispatch table。😡。

That is the code to invoke for a given method and object。Essentially。

 every object has their own copy of that。😡，And object itself knows exactly which code to invoke for a given method。

The way that prototype based object or into languages work。

 you still want to get the kind of code reuse。嗯。Or similar behavior of objects。

 The way that this would work is when you create a new object。

 you would typically clone an existing object or say。Essentially。

 I would like this object to behave like that prototype， like that other object。

 which is a prototypical implementation of a student。 And so my new object that I just created。

 that's the prototype for it。😊，U。So conceptually。The dispatch table for。

In a prototype based language belongs with each object。But at runtime。

 a lot of objects are going to have identical dispatch tables。So， so for performance reasons。

 we actually end up sharing the dispatch table。And then using a copy on write approach。

 if an object wants to modify that dispatch table。 Are people familiar with copy on write。

As an implementation mechanism。You often see it in。Does it come up in 61， C' 61？You cover it， okay。

 great。Go。Let's see what else。呃。An object oriented programming。Because this idea that objects。

The behavior of an object actually depends on its runtime class。It's actually often very useful。

At the programming language level to be able to ask of an object， hey。

 are you an instance of class C， so a runtime type check of an object。嗯。So in Java， for example。

 the expression O instance of C。Willll evaluate to a booleion truee or false is the object on an instance of class C at runtime。

 This is actually pretty easy to implement because every object is going to contain a pointer to its class。

 which contains the metadata for the class。 and so from that information about the class。

 it's possible to figure out iszo class， a subclass of C。

There's actually some really interesting work on。Representing the class hierarchy efficiently。Right。

 so there's actually a lot of instance of calls and a lot of code。😊。

And if you're representing the class hierarchy as let's say， a tree。This might be bad， right。

 you end up walking a tree every time you are。Every time you're doing an instance of test。

Right so how do you do？How do you do better than that So there are ways of efficiently storing inheritance information to really reduce the runtime cost。

Of those kinds of tests。All right， the type system of object oriented programs。I mentioned that。

One of the key things about object oriented programs is they provide some form of encapsulation that is of information hiding。

This often crops up。By the visibility restrictions that a programmer can declare on fields and methods。

 So in Java， for example， there are。Several visibility settings， private， protected public。

 there's one or two more。The key idea is that if a field or method is declared as private。

Then that field or that method is accessible only for the implementation of the class that is essentially within that same file that's implementing the class。

A public member is accessible by anyone as part of the public interface of the class。

 they can access the。The field or the method。😊，And protected is somewhere in between。

 it's accessible only to the implementation of the class。And subclass。

 So it's something that you want to allow。Subclass to access， but not the general public。嗯。

One of the other visibility that Java has is what's called package level visibility。

Packages are a way within Java of they're essentially a namespace。

 they're a way of trying to group together related classes。They're not quite modules。

 They're not quite namespaces。 they're kind of a little。Hacky and。

Uncle exactly what they're providing。In some ways， it's more an organizational technique rather than a clear modularity mechanism。

呃。We've been talking about both subclassing and inheritance within the Java programming language。

 these are conflated to a large extent that if one class subclass is another。

 then it inherits code and the methods。嗯。Part of what this means in Java is that subclassing is actually subtyping to a large extent。

 as we talked about if B is a subclass of C， then anywhere the program expects an objective of class C you can give an objective class B。

 that's essentially the same as the principle of subtyping。That we talked about earlier on this。

In this course。嗯。Interestingly， some languages actually separate this idea of subclassing and inheritance。

 so for example， in C++ one class can inherit from another class。

 but declare that that inheritance is private。So it can actually have visibility on its inheritance。

 and if a class says that it privately inherits from another class。Essentially。

 what that means is it's using that inheritance that as a。Implement mechanism。

It's how the implementation of the class is choosing to implement its functionality。

But it's not making it publicly known。That it is inheriting。Right and so the fact that it inherits。

That's very much separating the inheritance from the subclass in relation。

 You can inherit code from a class without being a subclass of it。

Something else that's related to the difference between subclassing and subtyping。

When we talked about subtyping of functions in a functional programming language。

We had this thing where。We had contravariants of argument types and covariants of return types。U。

Within Java。We don't actually allow any contra variance in the argument types of Java methods。

In particular， if you are overriding a method。You have to have the exact same static types。

In the signatures of the method order a few to override so given if C is a subclass of D。

 D declares a method M with types S1 up to SM。And you declare a method M， same name in C。

 the subclass with types t1 to Tn。C。M overrdes D。M only if those argument types are exactly the same。

😡，If you have different types。There's no overriding relation。

 you are doing what's known as overloading。Of the method， the method happens to have the same name。

 which might be semantically meaningful for you as a programmer。

 but there's no specific relationship between those methods with the same name but different arguments。

And like I say， I think in some version of Java， maybe Java 5， they started allowing。

Covariant return types。嗯。Which works out nice and cleanly and doesn't affect the overriding relationship。

Let's see。Oh， in Java， we have a special null value， like we do in oat and null is。Essentially。

 this polymorphic value null can be the type of any class。 So it's kind of like。In Ml。

 the option type。嗯。There's a whole lot of object oriented programming ideas。 As I mentioned。

 I took an entire class on it as an undergrad。 I ended up。

Before I went to grad school to get a PhD and I was working as a software engineer。

 the main implementation language I was using was Java， which is still widely used today。

 not so much in the classroom as it used to be， but definitely a lot of companies end up building their enterprise backs in Java for a variety of reasons。

And yeah， object oriented programming design can be an incredibly powerful way to structure code。

And large scale programs。But that's all I have to talk about for object oriented programming。

 Any questions。At the moment。Okay， good luck finishing up homework 5 on Wednesday's class。

 we're going to look at garbage collection， so essentially managed memory and find out how we end up thinking about and implementing that。

😊，See you in a couple of days。

![](img/8e4111571a13adcddfe73fe8486b661e_6.png)

![](img/8e4111571a13adcddfe73fe8486b661e_7.png)
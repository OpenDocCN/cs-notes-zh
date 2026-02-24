# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p32 -32-#31 OOP Part-3_ Polymorphism in C++.zh_en -BV1fRt2efEms_p32-

![](img/c42426ea13a50a8c38cb6cf21a3a1284_0.png)

Welcome to the modernern embeddeded systems programming course。 My name is Mirosak。

 and in this lesson， I continue the subject of object oriented programming。 Today。

 you will learn about the concept of polymorphism and you will see how it works in C++ and how to emulate it in C。

🎼Yeah。Unlike the previously discussed notions of encapsulation and inheritance。

 polymorphism is a uniquely objectoriented concept that has no direct analog in a traditional procedural language like C。

 therefore the plan for today is reversed compared to the previous two lessons in that you will first see what polymorphism is and how it works in C++。

 and only with this knowledge you will see how to emulate it in C。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_2.png)

![](img/c42426ea13a50a8c38cb6cf21a3a1284_3.png)

![](img/c42426ea13a50a8c38cb6cf21a3a1284_4.png)

![](img/c42426ea13a50a8c38cb6cf21a3a1284_5.png)

So let's get started today by making a copy of the previous Les than 30 underscore CPP directory and rename it to Les than 31 underscore CPP。

Get inside this new directory and double click on the Microvission Project lesson to open it。

To remind you quickly what happened so far， in the last lesson。

 you learned about the concept of class inheritance and you've created a rectangle class that inherited all attributes and operations from the shape base class。

But rectangle also added its own attributes and operations such as the draw operation to draw the rectangle on the LCD screen and the area operation to calculate and return the surface area of the rectangle。

However， both added operations actually make sense for the shape base class as well。

 because any shape could be drawn on the screen and has a surface area。

The only problem is that the shape class is so generic that you don't really know how to implement the draw and area operations at this high level。

But by now， you probably have noticed that object oriented programming is all about separating the interface。

 the what can be done from the implementation， the how it is done。So in this spirit。

 the shape class could at least provide an interface to the draw and area operations and worry about the implementation later。

 So let's have a look how it could work。Let's at first simply copy the area and draw signatures from the rectangle subclass to the shape superclass。

Let's also copy the implementation of these operations from rectangle。And adapted to shape。Of course。

 at the high level of the generic shape class， you cannot provide real implementations because you don't yet know if you are dealing with rectangles。

 circles， triangles， or lines。So you provide only some dummy code。

But now when it comes to testing this new shape interface in the last lesson you learned about upcasting。

 which is casting the derived class to the base class。

 this is always safe and object oriented languages like C++ perform such upcasting automatically without complaining。

This opens an interesting option of upcasting the pointer to a rectangle object R1。

 to a pointer to a shape PS， and then calling the draw and area operations on such an upcast pointer。

As you can see， this compiles error and warning free。

 so let's check in the debugger which operations are called in this case。And。As I step into the call。

You can see that the shapes implementation is called。

 which is rather unremarkable because the compiler evident it shows the function corresponding to the type of the pointer。

 not the type of the object。But let's go back to the code and modify the declaration of the shape class by adding the virtual keyword in front of the draw and area operations。

With this change。The compiler raises some warnings。

 but let's ignore them for now and just open the debugger。

This time around as you step into the draw operation。The rectangle implementation is called。

The same happens for the area operation call as well。This means that all of a sudden。

 the calls select implementations based on the type of the object， which is rectangle。

 not the type of the pointer， which remains shape。This is polymorphism in action。

 The term polymorphism itself comes from the Greek roots， poly， meaning many and morph， meaning form。

 So polymorphism means multiple forms。And indeed， that's what's happening here。

 the same operation such as draw or area can take multiple forms depending on the type of the object that the pointer happens to be pointing to。

This is all good and perhaps interesting， but what is polymorphism good for in practice？Well。

 among other things， polymorphism allows you to write generic code at the higher level of abstraction than you could without it。

For example， suppose that you want to draw a graph consisting of multiple shapes on your LCD screen for simplicity。

 supposeose that the graph is an array of pointers to various shape objects。

Now that the shape pointers in a graph might actually point to different types。

 but because all of them inherit the shape base class， all can be safely upcast to the shape type。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_7.png)

![](img/c42426ea13a50a8c38cb6cf21a3a1284_8.png)

Now you can declare a generic function draw graph at the shape class level。

And implement it in shape that CPP。The draw graph function simply looks over the shape pointers in the graph array until it encounters a zero pointer。

The pivotal point of the implementation is the graph of I draw call that employs polymorphism to correctly select the draw implementation depending on the type of the object。

 not the type of the pointer， which is evidently shape。

Now it's time to address the compilation warnings that the draw and area declarations in the rectangle class implicitly inherit virtual。

The warnings appeared after adding the virtual keywords in the shape based class。

 and as you saw in the debugger， this has turned on polymorphism with respect to the draw and area operations。

But polymorphism means that the draw and area operations in rectangle are not completely new operations added in that subclass；

 instead they are merely different forms or different methods of the draw and area operations specified already in the shape based class and inherited from it。

So to introduce some object orient terminology here。

 methods describe the different forms of the same operation and the different methods in the subclasses are set to override the original method inherited from the base class。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_10.png)

But going back to the code， the compiler noticed that the draw and area operations in rectangle are just different methods of the operations already declared in the shape base class as different methods of the same operation。

 they are automatically virtual， meaning polymorphic。

 so the compiler strongly suggests to make these methods explicitly virtual。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_12.png)

And indeed， adding the keyword virtual to the drawing area declarations in the rectangle subplus gets rid of the warnings。

Okay， so with this out of the way， I'm sure you are interested how your high level draw graph function will perform。

 so let's quickly test it in main docP。First， declare an array of shape pointers。Which could be cons。

And initialize it with say， pointer to the rectangle r1 and。

The pointer to dynamically allocated shape PS3。You need to terminate the array with a zero pointer。

Now you can simply call the draw graph function on this graph array。The project builds cleanly。

 so let's move the breakpoint to the draw graph function and open the debugger。

When you step into the Dr implementation。You can see that the first graph of I draw operation invokes the rectangle draw method for r1 as the this pointer。

The next graph of I draw operation invokes the shape draw method for PS3 as the this pointer。

Then the loop finds the zero pointer and terminates。So as you can see。

 the draw function does exactly what it was supposed to do in a very simple and intuitive way。

But to let you fully appreciate the extensibility of the design based on polymorphism。

 let's create another subclassus of shape， such as circle。

 The circle subclass is similar to rectangle， so let's just copy rectangle dot H and rectangle do CP and rename to circle dot H at circle do CP respectively。

Quickly add the new circle files to the project and adapt them。In the her file。

 simply rename the inclusion guards。And a class name。

The change in attributes is to replace width and height with radius of a circle。

 The circle constructor takes r 0 as the initial value of the radius。

 The circle class also needs to provide its own specialized methods for the draw and area operations inherited from shape。

 so the virtual declarations stay the same。Now in the implementation。

 you include circle do H and again replace the class name。

The constructor takes the R0 parameter and uses it to initialize the radius attribute。

The circles method for the draw operation will call the primitive draw ellipse function。Finally。

 the circles method for the area operation will calculate the area of the circle as pi times radius squared for simplicity here I will use only integer math and I will approximate the pi to 3。

With the circle class complete， the last step is to test it in maint CPP。

You include circle H header file。And instantiate a circle object C1 with the given values for X， y。

 and the radius。Then you add pointer to C1 to the graph array so that the circle C1 becomes part of the graph subsequently drawn by the draw graph function。

When you build the project， please note that only circle。cppP and main docppP have been recompiled。

 but specifically shape。cP with a D algorithm has not been recompiled。

 This means that the final image in this case uses the D implementation compiled before introducing the circle class。

When you run the program now。And step into the draw graph function。You can see that it calls。

The correct circle draw method for you see one object as the this pointer。

 the other graph of I draw virtual calls invoke the correct method for the rectangle R1。

And shape PS3。I hope this shows you the power and extensibility of polymorphism。

But also that the virtual call mechanism must be quite different than the regular function call。

So let's now see how virtual call really works。For this。

 let's add a regular function call right before the virtual call to compare the two。

Please note that the operation invoked on a full object like the rectangle R1 is always a regular nonvirtual function call。

 even though the operation itself might be declared virtual。

 This is because the exact type of the object is known at compile time Indentally。

 the connection between the function call and function body is called call binding。

The connection established at compile and link time is called early binding；

 this is the only called binding used in the procedural languages like C。But in C++。

 a virtual operation invoked on a pointer like PS here establishes a different called binding because the exact type of the object is not known at compile time since the pointer might be actually upcast from a derived class。

This type of binding is called late binding， dynamic binding， or real time binding。All right。

 so let's build the project and move the breakpoint to the early binding call to finally see how it compares and differs from the late binding。

When you launch the debugger。And continue to your break point in the disassembly view。

 you can see that the early binding call consists of moving the value of this pointer into r0。

 and then using the branch width link BL instruction to call the rectangle draw function hard coded in the BL instruction itself。

And indeed， when you step into the BL instruction， you end up in rectangle draw function body。

While you are edit， notice the address of this function in Ram， which is hex 250 c。Now。

 when you return back to main dotcP， you can see that the late binding machine code is significantly different than the early binding right before it。

It all starts with loading a 32 bit word from R 6， which is later used as the this pointer in r 0。

 So this 32 bit word must be coming from the this object。

 This word is subsequently used as the base address。

 So the word from the this object is a pointer itself。But wait a minute。

 you certainly didn't add any pointer attributes to the shape or rectangle classes。

 so let's take a closer look at this pointer in RAM。And indeed。

 you can recognize the 16 bit attributes， X and y inherited from shape。

 as well as width and height added in rectangle， but now all this is preceded by a pointer which apparently was added by the C++ compiler when you introduced virtual functions in the shape base class。

So the overall size of the rectangle object is now enlarged by a pointer。Now。

 regarding the edit pointer inside the rectangle object。It looks like an address in Ram。

 so let's see this ro address in the memory view。When you change the memory view to 32 bit quantities。

 I hope you can recognize that the first word at the wrong address is suspiciously similar to the Hex 250 C。

 which was the address of the rectangle draw function， In fact， it is this exact address plus1。

As I explained many times in the earlier lessons of this video course。

 the program addresses in Cortex M are stored as odd numbers because the least significant bit is not used for addressing。

 but rather it is always set to one to represent the T state of the CPU， so in short。

 the first word the ro address is the rectangle draw function address。

But what about the second word at the wrong address。Well。

 let's look for it in the disassembly window， remembering to subtract one from the address。

 which means that you are looking for。Hex o0 o。2，5，0，2。And indeed。

 this is the address of the rectangle area method， which is the second virtual function of the rectangle class。

All this reverse engineering can be summarized as follows。

 The compiler has added a pointer at the beginning of the class attributes。

 which points to a table in real that contains addresses of all virtual functions。In the literature。

 the table of virtual functions is called the V table and the pointer to it stored in the object is called the VPTR。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_14.png)

But continuing with the debugging， you can see that the address of the rectangle draw function is loaded from the V table into R1。

 and finally that this pointer is set up in r0。The actual function call is performed by the branch with Li and Exchange BLX R1 instruction。

 which jumps to the address provided in R1。And indeed， when you step into the BLX instruction。

 you end up in the rectangle draw method。Here， when you examine this pointer。

 you can actually see that the first attribute of the object slice inherited from shape is the VPTR。

So in summary， compared to early binding， the overhead of late binding is the additional VPTR in every object in RamM。

1 v table per class in Ram and two more instructions per function call。

 This is not a large overhead for what you are getting。

 but still it is not negligible and therefore C++ applies this mechanism only to functions specified explicitly as virtual。

 This is to prevent the overhead for functions that don't need late binding。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_16.png)

Other object oriented languages such as Java， for example。

 treat polymorphism as such a fundamental feature that all functions are virtual by default。Also。

 please note that the VPTRV table double indirect is just one possible implementation of late binding。

 and the C+ mass standard leaves it completely open to the compiler designers。Having said that。

 essentially all existing C++ implementations for a wide range of CPUUs use the VPTRV table implementations that you just saw。

So the last remaining question for today is who sets the VPTR。

 I mean the constant V table per class in RAM can be easily added just like the code itself。

 but the VPTR needs to be set in each and every instance of a class。

 which often are allocated at runtime， for example， as automatic objects in functions。

I hope that at this point you can guess that the ideal place where the VPTR can be established is the class constructor。

But of course， you didn't do anything about the VPTR in your C++ code。

 which means that the C++ compiler must have secretly synthesized some code to do this for you。

As an embedded engineer， I am sure you must be especially curious about any such secret code。

 So let's set a breakpoint in the rectangle constructor， for example， and start the debugger。

The break point is hit right away because there is a statically allocated instance of rectangle。

 which is initialized even before main。 When you expanded this pointer。

 you can see that the VPTR is still not initialized。 So step in。

And you end up in the shapepes constructor， which is invoked from the rectangles constructor initializer list。

That this pointer now changes type to shape， but the VPTR is still not initialized Now。

 looking at the disassembly， you can see two lines of machine code that apparently set the VPTR。

But wait a minute。 Which V table is it pointing to。Well。

 you can inspect the V table in their memory view。Take， for example。

 the second entry in the table and locate it in the disassembly。As explained before。

 you need to subtract one from the address in V table， so you are looking for Hex 00024 EA。

And you end up in the shape area method， which means that the V table belongs to the shape class。

So at this stage of initialization， the rectangle instance is still treated as its shape base class。

But let's continue stepping through the initialization of the shapes attributes and return back to the rectangles constructor。

Here in this assembly， you encounter similar instructions that apparently reinitialize the VPTR to a different value。

So again， let's find out from the memory view which V table this is by inspecting its second entry。

Now you are looking for the address Hex 0，0，0，2，5，0，2。And you end up in the rectangle area method。

 which means that the V table now belongs to the rectangle class。So as you can see。

 the VPTR is initialized and reinitialized in every constructor to point to the V table of that class。

But the order of constructor calls is such that the super classes are always initialized before S classes。

 so the VPTR ends up pointing to the last derived class， which is correct。

This concludes this quick look at polymorphism in C++ In the next lesson you will put your understanding of virtual functions to the test by implementing late binding in C。

🎼Yeah。If you like this channel， please give this video a like and subscribe to stay tuned You can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/c42426ea13a50a8c38cb6cf21a3a1284_18.png)
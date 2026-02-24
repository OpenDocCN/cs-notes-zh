# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p31 -31-#30 OOP Part-2_ Inheritance in C and C++.zh_en -BV1fRt2efEms_p31-

![](img/294a6dc5b7306caf6b62097193a0eb07_0.png)

🎼直说。Welcome to the modern embedded systems programming course。 My name is Miroamak。

 and in this lesson， I continue the subject of object oriented programming Today。

 you will learn about the concept of class inheritance。

 and you will see how it works both in C and in C plus plus。As usual。

 let's get started by making a copy of the previous lesson 29 directory and renaming it to lesson 30。

Get inside the new Lesson 30 directory and double click on the Mivision Project lesson to open it。



![](img/294a6dc5b7306caf6b62097193a0eb07_2.png)

To remind you quickly what happened so far in the last lesson you started to learn about object oriented programming OOP。

 and you have implemented the first fundamental OOP concept of encapsulation。

 encapsulation means that you organize your code into classes that package data and functions together。

 specifically you have implemented a shape class in C and later in C++ to represent shapes on an LCD display。

Later， you created a few instances of the shape class， which are called objects。

 These objects then were manipulated exclusively by the class operations。

 which was the whole point of encapsulation。But in real software for an LCD display。

 you would need not just negulous shapes。 You would need concrete rectangles， circles and triangles。

Of course， now that you know the concept of a class， you could create a rectangle class。

 a circle class， a triangle class， and so on from scratch。But as you will do this。

 you will notice that all of them would contain attributes for their position on the screen and operations to move them around and to determine the distance among them。

 plus some other attributes and operations。By wait a minute。

 didn't you just implement these exact attributes and operations in your shape class？

Could this be somehow reused in your rectangle circle and triangle classes？



![](img/294a6dc5b7306caf6b62097193a0eb07_4.png)

The answer is yes， and it is known as the fundamental OOP concept called inheritance。

 which is the ability to define new classes based on existing classes in order to reuse the code and organization。

 This is the main subject of this lesson。

![](img/294a6dc5b7306caf6b62097193a0eb07_6.png)

So here is how you go about creating a rectangle class based on the shape class in C。

You start the same way as you did for the shape class by adding the rectangle dot H here file to your project and placing the usual includes guards in it。

Then you create the attribute structure。 but instead of starting from scratch。

 you add the whole shape instance as the very first attribute， which by a naming convention。

 you call super Later， you will see in which sense you can think of the super attribute as inherited from shape。

 But for now you just stated in the comment。Of course， you need to include the shape。

 H header file with the shapestruct for this to compile。

Now you can add attributes specific to the rectangle class。

 such as the width and the height of the rectangle。Finally。

 you are the operations specific to your rectangle class。In the constructor。

 you provide parameters for all attributes， the x0 and y0 for x and y inherited from shape and W0 and h0 for width and height added in rectangle。

Finally， you can add operations specific to the rectangle。 For example， you can add Op draw。

 which will draw the rectangle on the LCD screen。There is no reason why draw should change the rectangle so you could add cont before the start to the me pointer。

Similarly， you can add the area operation which will calculate and return the area of the rectangle。

 again， the area operation will not change the me instance。

When it comes to the definition of the rectangle class， you add a C file rectangle to your project。

Next， you need to include the rectangle dot H headed file with the class interface。

After which you copy over the prototypes with the class operations。In the constructor。

You first call the shape constructor for the member super。

This takes care of initializing the inherited attributes。Only after this。

You initialize the attributes added in the rectangle class。In the rectangle area operation。

You simply return the product of width by height promoted to U in 32 T。Finally。

 in the rectangle draw operation， which is potentially more complex。

 you can simply use some commented out pseudo code for drawing vertical and horizontal lines on the LCD。

This is good enough for today because all you really need at this point is the ability to set a break point inside this operation to determining in the debugger that it has been called。

So now to exercise your rectangle class， you need to instantsate it。

Initialize it with the constructor。And call the rectangle operations on it。Like draw。An area。

The code builds cleanly， so let's open it into the debugger。

The most interesting thing I would like you to see here is the layout of the rectangle object in memory。

For this， open the memory view and set it to the beginning of your Ram that is at Hex2 followed by all zeros。

Next， run to the rectangle constructor and step into it。Here。

 note the me pointer value and find it in the memory view。

Now step into the shape constructor and note that the me pointer value is the same。

 even though the type of the me pointer has changed from rectangle to shape。Before continuing。

 change the memory view to display signed short values because the attributes of shape and also of rectangle are 16 bit integers。

Now， as the shape constructor runs， it fills out the memory at the beginning of the rectangle structure。

When the control returns back to the rectangle constructor。

 it fills out the memory after the shape portion。In the end， your memory layout looks as follows。

 The whole recal structure is aligned with its first member super。

This is not just a coincidence for the rectangle tract。

 but rather a rule that is enshrined in the C language standard。Here， for example。

 is the International standard ISOIEC for the C programming language。

In the section about structure and union specifiers you can read that。

A pointer to a structure object suitably converted points to its initial member。

 There may be a named padding within a structure object， but not at its beginning。

All of this is of course， a rather complicated way of saying that the pointer to a structure can be always safely cast on the pointer to the initial member of the structure。

This has rather important implications for your rectangle class because it means that any pointer to rectangle can be safely passed to a function expecting a pointer to shape。

This means that all operations for shapes apply to rectangles as well。For example。

 you can call the shape move by operation on your rectangle object。

And you can also call the distance from operation as well。In this sense。

 the rectangle class inherits all operations from the shape class。However。

 for this to compileil and C， you need to explicitly cast rectangle pointers to shape pointers。



![](img/294a6dc5b7306caf6b62097193a0eb07_8.png)

But truly object oriented programming languages like C++ know that such pointer casting called upcasting is always safe。

 and OOP languages perform upcasting automatically。

 as you will see in the second part of this lesson。

Now you'll probably wonder where the term upcasting is coming from。

 so it's time to learn a little of terminology and graphical notation。



![](img/294a6dc5b7306caf6b62097193a0eb07_10.png)

Here is a class diagram which is drawn in a traditional way with the base class shape on top and the derived class rectangle below from this。

 you can see that casting from the derived class to the base class goes up， hence the term upcasting。

The inheritant relationship itself is drawn as a arrow with a big triangular end pointing to the base class。

 which is often the exact opposite to what most people initially think。

This is because the arrow points in the direction of generalization that is from a more specialized class like rectangle to a more general class like shape。

Therefore， inheritance is also alternatively called generalization。

 The base class is alternatively called super class or parent class。

 and the derived class is alternatively called subclass or a child class。Finally。

 you should also realize that class inheritance is not limited to only one level。

 The rectangle class itself can be further specialized， for example。

 in a filled rectangle class for which rectangle becomes the base class。

All of this can lead to whole family trees of increasingly specialized classes。

With this bigger picture in mind， let me offer a few guidelines of how to best think about class inheritance。

First， the term inheritance itself， as well as the terms like parent class and child class。

 might suggest the family tree analogy。But this is an incorrect analogy。

 and I would discourage that you think about class inheritance that way。

As you saw in the rectangle class emulation in C， every instance of the derived class literally contains the whole instance of the base class。

 like rectangle contains shape as the attribute super。With classes。

 this is done in such a way that any derived instance can be treated as an instance of the base class。

 In other words， inheritance establishes the is a relationship such that it makes sense to say a rectangle is a shape。

In contrast， the family tree analogy does not work that way。

 Donald does not contain inside an instance of his parent， Marianne。

 and it makes no sense to say that Donald is Marianne， or Donald is Fred， for that matter。

So which analogy could you use instead？

![](img/294a6dc5b7306caf6b62097193a0eb07_12.png)

Well， a good analogy that will shape your thinking correctly is the biological classification of living organisms。

In the biological classification， it makes sense to say， for example， that a house cat is a fearless。

 meaning a cat like animal； Further， it makes sense to say that the house cat is a carnivore。

 meaning a predominantly meat eating animal， and even further and at the same time。

 it makes sense to say that a house cat is a mammal， meaning animal that feeds their young with milk。

Also， the behaviors introduced in the higher level classes make sense to be inherited by the lower level classes。

 For example， the mammal class might introduce the lactate operation。

 meaning to secret milk to feed the young。 This operation makes them sense in all subclasses of mammal。

 such as carnivores， feelless and house cats。To finish this longish somewhat theoretical digression。

 I'd like to compare class inheritance to class composition so that you understand the difference。

So going back to the code， you implemented inheritance by literally embedding an instance of the superclass inside the subclass。

This means that the subclass is a composition of the superclass。

 plus some added attributes and operations， this points to some similarities between inheritance and composition。

And in fact， both approaches can accomplish similar goals。

 but there is an important difference inheritance is there is a relationship which comes about only when you embed the superclass as the very first attribute so that every instance of the subclass can be treated as an instance of the superclass。

If you move the superclass instance to a different position， you still have composition。

 which is the has a relationship like rectangle has a shape。

 but you can no longer legitimately perform upcasting。Instead。

 you would have to explicitly reference the component attribute inside the rectangle class。

 which would break encapsulation。So let me undo the changes and close this project as we are done in C for today。

In the last segment of this lesson， I'd like to show you how class inheritance is implemented in C++。

Just like in the previous lesson， this will allow you to directly find out how your C emulation of inheritance differs from a truly object oriented language and how C++ differs from C。

So let's start with the C++ code from the previous lesson 29。

 copyied and renamed to lesson 30 underscore CPP。Also， go back to the today's lesson 30 directory。

 copy the files rectangle。h and rectangle。 C， and paste them into the lesson 30 underscore CPP directory。

As the last touch， rename the rectangle dot C file to rectangle。cP。

Now you can drop the project lesson onto the microvision IDE to open it。After opening。

 the first thing you need to do is to add rectangle dot H and rectangle。cP to your project。

So let's open the rectangle。h header file and convert it to C++。

You start exactly like in the previous lesson， you replace type detract with the keyword class followed by the class name。

But now comes the new element of inheritance For this key object oriented concept。

 C plus plus providess a special syntax， which is column。

 followed by the base class name and the keyword public in front。

This means in C++ that rectangle publicly inherit shape。

 The other option would be to inherit shape privately。

 but private inheritance is an advanced concept that you don't need to worry about right now。

So this is really all that's new。 The rest of the rectangle class， like the private attributes。

And public operations are very similar to the previous lesson。So again。

 you adjust the operations by removing the class name pres and removing the me pointer。

 remembering to preserve the con before the asterisk at the end of the prototypes。

Now regarding the derived class implementation。The most interesting changes in the constructor。

Just let you see， the derived class needs to call the base class constructor， but again。

 C++ provides a special syntax for it， which is based on the constructor initializer list introduced in the last lesson。

The draw operation， even though it is just pseudocode at this stage， offers an interesting dilemma。

 which is direct access to the inherited attributes from shape coded in C as super dot X and super dot Y。

If you check in the shape class， these attributes are declared as private。

 which restricts the access to them to their own class only。

In order for derived classes to have access as well。

 the base class needs to grant the protected access to its attributes。

 This means that the derived classes at any level can access such attributes directly。

 but the attributes are still protected against any public access。Now in the draw operation。

 you can remove the me super indirection because C++ allows you to access the inherited attributes directly as though they were declared in the derived class。

Of course， you can also remove the me pointer from all other parameters because they are now accessed via the implicit this pointer。

Finally， you apply the same changes to the area operation。As you can see。

 the rectangle implementation in C++ compiles error and warning free。

The last remaining step is to actually instantiate and use the rectangle class in the main dot CP file。

 just like you did it in C。For this it is convenient to open the previous maint C file in the side view for reference。

 please note that the C file is not added to the C++ project。So first。

 you need to include the rectangle dot H header file in your main dot CPP。Next。

You can statically allocate a rectangle object in C++。But in C++。

 you need to immediately initialize the object via a constructor call。Next。

 you can call the operations introduced directly in the rectangle class such as draw and area。

 which you modify the same way as before for the shape class。

But now you can also call the inherited operations from shape。

And here you can remove the explicit upcasting because the C++ compiler performs upcasting automatically。

 knowing that upcasting is always safe。The project builds cleanly so let's see how the C++ implementation looks inside the CPU before starting the debugger。

 however， let's set a break point in the rectangle constructor only now you start the debugger。

As you can see， the breakpoint is hit right away， which means that the C+ mass static constructors run even before main。

 as you already learned in the last lesson。The locals view shows you that this pointer through which you can conveniently see the object's attributes as consisting of the inherited shape part followed by attributes added directly to rectangle。

But let's also set up the memory view to see the exact layout of the rectangle object in raw memory For this。

 set the memory view to the beginning of your rem。 That is at hex 2 followed by all zeros。 Also。

 set up the view to show signed short numbers because that happens to be the size of shape and rectangle attributes。

Now step from rectangle into the shape constructor and note that this pointer value is the same。

 even though the type that this pointer has changed from rectangle to shape。

As the shape constructor runs， it fills out the shape attributes。

 which are clearly at the beginning of the rectangle memory。

When the control returns back to the rectangle constructor。

 it fills out the memory after the shape portion。In the end。

 your memory layout in C++ looks identically as in your C emulation of inheritance。

 The whole rectangle object is aligned with the inherited shape object。

 which is at the beginning of the rectangle memory。

Now let's step over the shape class operations from the last lesson and step into the rectangle operations such as rectangle draw。

Here， like in the rectangle constructor， you can use the local's view to very conveniently examine the rectangle object through the this pointer。

Same goes for the rectangle area operation。But now come the operations inherited from shape like shape move by。

 as you can see in the locals view that this pointer still points to rectangle R1。

 but is automatically upcast to the shape type and only the shape portion is now visible in the locals view。

The move by operation changes the shape attributes， which you can see in both views。

 locals and real memory。Finally， the same upcasting of that this pointer happens for the distance from operation inherited from shape。

This concludes this quick introduction to the object oriented concept of inheritance。

Today you've learned what class inheritance is and how it is a mechanism for reusing common attributes and operations both in CNC++。

But this is not the whole story。 Inheritance enables even more reuse。

 as well as extensibility through the third fundamental object oriented concept of polymorphism。

 This will be the subject of the next lesson。If you like this channel。

 please give this video a like and subscribe to stay tuned You can also visit statemachine。

com/quistart for the class notess and project file downloads。🎼，🎼う。



![](img/294a6dc5b7306caf6b62097193a0eb07_14.png)
# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p30 -30-#29 OOP Part-1_ Encapsulation (classes) in C and C++.zh_en -BV1fRt2efEms_p30-

![](img/7b87d1694b6cac6803994c7f2b54e77c_0.png)

，Welcome to the Moern embeddedded System Program course。 My name is Miosannic。

 and in this lesson I'd like to introduce object oriented programming。

 which is an important stepping stone in understanding modern software of any kind。

 not just modern embedded programming。Today you will learn about the high level concepts。

 but as usual in this video course， you will also see how object granteded programming works at the low level inside your embedded microcontroller。

This lesson lays the foundation for understanding most modern trends in programming。

 and almost all upcoming lessons in this course will in one way or another rely on the concepts introduced today。

As usual， let's get started by making a copy of the previous lessons 28 directory and renaming it to lesson 29。

Get inside the new lesson 29 directory and double click on the microvision project lesson to open it to remind you quickly what happened so far in the last seven lessons you'll learned about the real time operating system。

 Arts and the associated programming paradigm based on Bing and sharing of resources among concurrent threads such as your By 1。

 By 2 and Blinky 3。

![](img/7b87d1694b6cac6803994c7f2b54e77c_2.png)

Indeed， the most important and complex parts of the artist turned out not to be the context switching and thread scheduling。

 but rather than numerous mechanisms for blocking， synchronization and mutual exclusion to support a shared state concurrency programming paradigm。

From the historic perspective， the arts went mainstream in the 1980s and the arts based shared state concurrency model with blocking。

 essentially unchanged， continues to be in the mainstream use to this day。However， during the 1980s。

 other important trends went mainstream as well， and these include object oriented programming and event driven programming。

And since all these trends are essential to understanding modern embedded software， today。

 I will explain the main concepts behind object oriented programming while I promise to talk about event driven programming in the future。



![](img/7b87d1694b6cac6803994c7f2b54e77c_4.png)

Many people think that object oriented programming。

 OOP must necessarily be done in an OOP programming language such as C++， Java or Python。



![](img/7b87d1694b6cac6803994c7f2b54e77c_6.png)

But actually， OOP is not the use of any specific language。

 but rather a way of software design based on the three fundamental concepts of encapsulation。

 inheritance and polymorphism。

![](img/7b87d1694b6cac6803994c7f2b54e77c_8.png)

Today you will see how to implement these concepts in standard portable C After that you will see the exact same design implemented in C++。

 which will allow you to compare C to C++ and also to get a taste of programming in C++。

So let's start with the concept of encapsulation， which is closely related to information hiding and abstraction。

You have actually already used some of these concepts in the design of the board support packageP here you have specifically separated the what needs to be done in the bP。

h header file from how it is to be done in the BP。c implementation file。

You have used the concept of abstraction because all the details of handlinging the LEDs on your TVVC launchpad board are abstracted away and simplified into just three operations on off and toggle。

You have also used the concept of information hiding because the information about specific ways of performing these operations on the LEDs is hidden from the users of the LEDs。

 such as your blinky threads。All the users of the LEDC and all they really need is the Bsp。

h header file。But thus far， the design based on abstraction and information hiding within the BSP module has an important limitation。

 which is that the design handles only a fixed number of LEDs， red， blue and green in this case。

 and it cannot be easily extended to handle an open ended number of LEDs。For example。

 imagine that your project uses a graphic LCD display on which you need to draw various shapes。

 such as rectangles， circles， and triangles。It is very hard to tell upfront how many of these shapes you would need。

 so it is difficult to hide all this in a module without resorting to some kind of dynamic memory allocation。

 which is generally a bad idea in real time and embedded systems。Instead。

 you need to give the application programmers a chance to allocate as many shapes as they like in any way they like。

 statically， automatically inside functions， or even dynamically on the heap if they choose to do so。

🎼。You can achieve this by creating a different shape interface than the BSP。h。

Inside the new shape to each other file， youll represent the data needed by each shape as a C structure which then can be instantiated in any way you want。

For example， every shape has a specific position on this screen given by the X and Y coordinates。

Since the LCD screen is small， the 16 w integer provides adequate dynamic range。

 but lets allow negative that is signed values to represent shapes that are off screen。So far。

 all this is really nothing new compared to lesson 12 of this course。

 which introduced C structures and time depths。But now comes the encapsulation part by a coding convention。

 you disallow accessing the members of the shapestruct directly。

 and instead you provide a set of functions specialized to work with the shape structure。For example。

 you provide a way of initializing a shape called the constructor。

This function takes a pointer to the shape structure as the first parameter。

 which by convention you will call me。Since the me pointer should always point to the same shape instance。

 let's prevent changing it by making it const。 Please note that the const is after the star。

 which means that the me pointer cannot change， but the shape instance pointed to by the pointer is allowed to change。

 which is the main purpose of the constructor。Next。

 you can also provide a function to move a shape on the screen by a given Dx and DY increments。

And one more function with a return value to provide the distance from the me shape to another shape other。

This other shape should not need to change， so let's make it con。

 Please note that now the con is before the star。But actually。

 the mehave should not need to change either， so let's make it const as well again。

 by adding cont before the star。Please note that you establish the association between the shape data and the shape function by means of the following two coding conventions。

First， the names of all associated functions start with the name of the associated structure。

And second， all these functions take the me pointer as the first parameter with the purpose to specify which specific shape instance the function is operating on。

As you will see later in this lesson， the me pointer corresponds to the implicit this pointer in C++ and the cell variable in Python。

 if you are familiar with Python。Now you can add the C file， shaped C。

And provide there the implementation of the shape functions prototyped in shape to age。

The constructor performs the initialization of the me structure。

From the provided x0 and y0 parameters。🎼う。The move by function modifies the position of the me shape by adding the provided Dx and D offsets。

And finally， the distance from function calculates the distance between the me shape and the other shape。

This function uses the simple taxicab geometry， which is adequate for shapes but does not require extracting square roots as the standard Cartesian metric。

So all this is quite straightforward， isn't it？😊，But what you have just created is a shape class。

 which is quite a fundamental concept in object oriented programming。A class combines both data。

 which are called in ROP attributes。And functions， which are called in OOP operations into one entity。

 the class。One nice aspect of classes is that they can be drawn in class diagrams which show a class as a box with the class name at the top。

 then attribute and then operations Later， when you have more classes。

 a class diagram can also show the relationships among classes。

A class realizes the concept of encapsulation because it presents to the outside only the outer shell in form of the operations。

 while the internal data and internal implementation remain encapsulated inside the shell。

But back to the code， you can think of a class as a cookie cutter from which you can create any number of instances of the class called objectsject。

So now let's include the shape that H class declaration in the main that C file and create a couple of such objects of the shape class。

First， you can allocate a shape object as one statically。

You can also allocate another shape object as to automatically on the stack inside the functions such as main。

And finally， you can also allocate yet another shape object dynamically on the heap using the Maoc function from the standard library SDdL。

h。As always with dynamic memory， it is also a good idea to immediately add the explicit free library call for this object to prevent a memory leak。

As I already mentioned， dynamic memory allocation is typically a rather bad idea in real time embedded software。

 but it is a possibility for instantiating classes， so I show it here only for completeness。

But to finish this point， since you are using dynamic memory now。

 you need to make sure that your heap has adequate size。In the project Option dialog box。

 choose the ASM tab， here you can find two symbols for the C stack and the heap because the sizes of these memory areas are determined in the startup code in assembly。

 you need to increase the size of the he to say 1 kilobyte that is  thousand24 bytes。

But going back to the code， another important convention of OOP is that the objects get initialized before any other operations can be performed on them object oriented languages called the class constructors automatically。

 which you will see in a couple of minutes in C++。But in C。

 you need to do this manually by calling the CorR functions explicitly。By the way。

 you might recognize the same pattern already used with respect to the QX thread objects from the QPC framework。

 so now you know what it is。After the initialization。

 you can perform any defined operations on your objects， for example。

 you can move them around with a move by operation。

Or you can check their relative distances from each other here I use the assertion macros from the QPC framework to assert the basic properties of the distance operation which are the distance from a shape to the same shape must be 0。

The distance from shape1 to shape 2 must be the same as shape 2 to shape 1。

And the distance between two shapes， S1 and S2， must be less or equal to the sum of distances to any other shape like PS3。

🎼Yeah。At this point， you can also check that the move by operation is not allowed for cont shape objects。

 for that you can declare a shape con pointer PS1 pointing to the S1 shape。

When you try to call the move by operation on this pointer。The compiler protests with an error。

This is an example of the main guiding principle for designing class interfaces。

Your interfaces should be easy to use correctly and hard to use incorrectly。

Now let's have a look at how encapsulation works internally and how to de back of the oriented code based on classes。

First， as you step through the main code， you can watch the call to the MaO function。

The function takes the size of shape parameter， which turns out to be 4 bytes。

 This makes sense because the shape tract consists of two2 byte integers。

Next you can see that the call to a class operation such as the constructor places the me pointer in the R0 register。

 this is per the arm applicationplication procedurecure call standard AAPCS introduced back in lesson 9。

As you step inside the class operation， you can see in that this assembly window。

 then the access to class attributes uses the offset from a register addressing mode from the me pointer in r0。

 this is very efficient。🎼う。Also， inside the class operation。

 it is always convenient to watch the me pointer， which is at the top of the locals window。

 this means that you can very conveniently see the class attributes。

As you keep stepping through the code， you can see that this pattern of placing the me pointer in the R0 register repeats for all class operations。

So in the end， the me pointer helps you not only in understanding the code。

 but also in debugging because you always easily see the objects you are dealing with。

 as it turns out this also results in excellent performance。

So this is how you can emulate class en calculationulation in C。

 but what about real object oriented programming languages， how would that work in C plus plus。

 for example， Well， let me show you right now。Specifically。

 let's take this whole lesson and translate it into C+ class。

 this will allow you to directly find out how it differs from C。In the first step。

 let's just copy the whole lesson 29 directory。🎼Yeah。And rename it to lesson 29 underscore CPP。

Get inside the new directory and rename all dot C files to dotcP。Finally。

 drop the project lesson onto the microvision ID to open it instead of the previous project in C。

The ID has obviously problems opening the no longer existing dotC files。

 which you need to remove from the project。🎼The。Instead。

 you now need to add the existing new dotcP files。うん。う。You rebuild the whole project。

Which produces some compilation errors。The first error is in converting the void pointer returned from Maoc to the shape pointer PS3。

 This was fine in C because void pointer implicitly converts to a pointer of any other type。

 but C plus plus is stricter and requires exact match between the types。

The other errors are of the same exact nature because void pointers are used instead of pointers to the QPC event type Q EVT。

But after these few cosmetic changes， the project compiles and links error and warning free。

That's very interesting because it shows you that C++ compiler accepts the C implementation just fine。

 it is only a bit more strict in terms of type checking。

This means that you can get into C++ programming quite easily from C and that you can treat C++ at first as a better。

 more strict version of C。But， of course， C plus+ offers you much more than this。

 It is truly an object oriented language that supports classes directly。

 So let's now convert your shape class emulated in C into a true C plus plus class。😊。

The first thing is to replace the keywordstruct with class followed by the class name。

You also don't need the awkward type de anymore， because the name after the class keyword in C++ can be used as a type by itself without the class prefix。

Also， because the C++ class encompasses both attributes and operations。

 the closing bra goes now after the last operation。Now。

 because class operations are truly inside the class。

 you no longer need the prepened class name in front。

 but this concept of mangling the name of the class with the name of the operation is not completely lost。

 as you will see later in this lesson， the C++ compiler actually also performed such name mangling behind the scenes。

The class attributes should be encapsulated， meaning that they should be inaccessible outside of the class in C。

 it was just a coding convention， but C++ provides a special private keyword to restrict the access to these class members。

On the other hand， class operations need to be publicly accessible for which C++ provides the public keyword Now。

 regarding the constructor operation， C++ supports class constructors directly and calls them automatically whenever the class is instantiated because of the special status。

 the construct must have a special name， which is the same as the name of the class。

A C++ constructor also cannot return any value。Now the most interesting aspect of any class operation。

 including the constructs， is that in C++ they all take an implicit parameter called this。

That is exactly like the me pointer you applied in C。Therefore。

 because the pointer to the class instance now called this is already provided implicitly by the C++ compiler。

 you don't need to duplicate it， so you need to remove the me pointer。

The me pointer in the distance from operation is a bit tricky because it has the cast qualifier that you don't want to lose。

C++ provides for the specials syn where you move the con qualifier after the operation。By the way。

 you could have named the me pointer as this in C， and the C compiler would happily compile such code。

 but that original C code would not compile in C++ because this is a keyword in C++。

The moral here is to avoid using keywords for your identifiers。

 even if they are in different but related languages like C and C++。Okay。

 so this is the complete shape class declaration in C++ Now let's move on to adjust the definition of the class operations in the shaped CPP file。

So here it is。Let's skip the constructor for the time being and focus on the regular class operations。

The first thing you need to change is to replace the underscore with the column column scope resolution operator。

 which tells the C++ compiler that the operation belongs to a given class。

 such as shape in this case。Next， you need to remove the me pointer from the signature。Now。

 inside the body of the function， let's replace the me pointer with this pointer to show you that this implicit pointer really exists and is indeed used to access the class attributes。

The same goes for the distance from operation， except that you need to be careful with the Kt qualifier just as you did in the declaration of this operation。

In this case， let's simply remove the me pointer also from the body of the function without using the this pointer。

 because the C++ compiler will recognize the names of class attributes and will implicitly add this pointer in front of them。

And finally， with a constructor who can also apply the same adjustments。

And it will also compile like that。But the truly C++ way of initializing the class attribute in a constructor is by means of the constructor initializer list。

 which looks like this。Now let's try to compile just this one shaped the CPP file。As you can see。

 the C++ compiler accepts the shape class without any errors or warnings。

To finish off the conversion to C++， you still need to adjust the actual use of the shape class in the main dot CPP file。

Here you need to replace the explicit cost to the shape constructor with initialization right at the point of allocation of the shape objects。

For example， the static object S1 needs to be initialized right where it is allocated。Similarly。

 the automatic object S 2 must also be initialized at that point of allocation。

A dynamic object like PS3 here is located in C++ by means of the C++ new operator。

 which is followed by the class constructor。While you are added。

 any object allocated with new must be disposed of by means of the C++ deletete operator。

Now the syntax of calling class operations is different in C++ and is performed by means of the dot operator that was in C used only for accessing data members of the structure。

Specifically， the move by operation is invoked by first specifying the object then the dot operator。

 and then the operation name and argument list。An operation on a pointer to an object is invoked by the arrow operator。

 which in C was used only for accessing members of a structure。

 but in C++ just like the dot operator is used for both attributes and operations。

Please note that while the syntax might be different between CNC++。

 the actual information supplied for each operation is identical in both cases。

After completing all the changes， you can see that the project builds cleanly。

So now comes the most interesting part， which is to see the machine code generated by the C++ compiler and compare it with the previous code generated by the C compiler。

But first， even before opening the debugger， go to the shape class implementation and set a break point in the shape constructor。

Now， launch the debugger。Interestingly， the code stops at the break when in the shape constructor。

 even before the main function was called。Indeed， when you examine the call stack。

 you can see that the shape constructor is not called from main。

 but from some CPP initialization code。This is an interesting observation， for two reasons。First。

 you just learn that in C plus+ the constructors of static objects like S1 are called even before the main function。

And second， you just learned that C++ requires an extra step in the startup code to invoke these static constructors。

But when it comes to the actual machine code generated by this very different C++ syntax of constructor initializer list。

 it turns out to be actually identical to the code generated by the C implementation。

When you continue from here， you can see that the shape constructor has been called again。

 but this time from main。Indeed， this is the construct of the automatic S2 object inside main。

 When you keep stepping from here， you can see the invocation of the new operator。

 Keep single stepping。 and as you can see you arrive at the call to malloc。

 So you just found out that the C plus plus operator new calls malloc internally。Moreover。

 the parameter pass to Maoc in r0 is 4， which means that the size allocated for the C plus plus shape object is4 bys。

This is， again， exactly the same as it was in sea。When you continue。

 you can see that the shape constructor is invoked for the third time。

 which means that the new operator also calls the constructor for the object allocated dynamically。

 So to quickly summarize， you just saw how C plus plus ensures that the constructor is invoked in every case after allocating an object。

 so now let's move the break point from the constructor to the first invocation of the move by operation。

 When you continue and hit the break point you can compare the C plus plus for calling move by with the corresponding calling C。

As you can see， they turn out to be identical。After you step inside the move by operation。

 it is a good idea to watch the local's window where conveniently that this pointer shows at the top。

 This is exactly like the P pointer was in sea。😊，Moreover。

 the actual machine code for the move by implementation in C++ turns out to be again exactly the same as the C code before。

I am not going to repeat it for the distance from operation because I hope you are getting the idea。

 The C+ plus compiler generated identical code as your original C emulation of classes for both the invocations and implementations of the operations。

So now I hope you know how classes and encapsulation work and what's going on behind the scenes in C++。

Before I wrap up for this lesson， the last aspect of encapsulation I'd like to explain is how it relates to the art because of course you can use classes and art together。

Imagine， for example， that you move the static object as1 to the top of the file。

And that you invoked a move by operation from the blinky one thread。

🎼You also copy the distance from operation on the same object as one to your By2 thread。

Please note that the assertion that a distance from S1 to S1 must be0 should be always true。

 and that it is checked downstream from the semapho weight。

 which means that it will run only after you press the SW1 button on your TVC launchpad board。

As you can see， the project still builds cleanly。So let's open it into debugger。This time。

 before running the code， set a break point in the Q on Aser handler so that you immediately know should any of the assertions fail Now。

 run the code free。And start pressing the SW1 button。

As you can see most of the time the code keeps running。

 which means that the assertion in By2 evaluates successfully thousands of times。

 but keep trying and whoops， you hit an assertion。

![](img/7b87d1694b6cac6803994c7f2b54e77c_10.png)

Check it。And indeed， the assertion failed inside the U Blinky2 thread。

The reason is a race condition around the shared as one object。

 which is being modified in one art of thread， By1， while it is used in another art of thread， By 2。

If you don't remember what race condition is， please refer it to lesson 19。

The important corollary from this is that even though you applied encapsulation for accessing the shared object as1。

 it didn't really prevent the race condition。And after what you have seen today。

 I hope you understand why。You just saw that encapsulation works internally in C++ exactly the same way as you emulated it in C and boil down to simple function calls。

 this might hide the internal implementation， but does really nothing to prevent race conditions。

To achieve a true encapsulation for concurrency， you need to go beyond the concept of a simple class and employ the so called active class。

 also known as the Act object design pattern。This active object pattern is a fusion of concurrent programming。

 object oriented programming， and ein programming， and I will talk about active objects in the future lessons。



![](img/7b87d1694b6cac6803994c7f2b54e77c_12.png)

But this is it for this lesson today you have learned about the concept of encapsulation that is classes and objects both in C and C++。

In the following lessons on object oriented programming。

 you will learn about the two other fundamental concepts of inheritance and polymorphism。



![](img/7b87d1694b6cac6803994c7f2b54e77c_14.png)

If you like this channel， please subscribe to stay tuned， you can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/7b87d1694b6cac6803994c7f2b54e77c_16.png)
# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p15 15_02_02_new关键字.zh_en -BV18U411U729_p15-

![](img/cfd01eb965b589baef3aefa5fa6cf39a_0.png)

Now that you have the high level concepts， let us delve into the step by step execution of our example point code。

 We're going to start in main， which we'll talk about more later。

AGs gives you access to the command line arguments， which you won't need for quite a while。

 so we are just going to ignore that。The first line declares point P1 and initializes it to a new point。

 note that classes are types so we can use class types that we make to declare variables here we want P1 to be a point。

Until we finish evaluating the right hand side， we are going to draw this as an arrow with a flat end。

 We'll use this notation to indicate when a variable does not reference an object。

 Note that this is a bit different from numeric variables like ins， whose initial value is 0。

 We've colored this flat ended arrow red to remember that we have not yet explicitly initialized this variable。

Now let us evaluate the right hand side of the initialization expression。We are doing new。

 which will create a new object。 What type of object are we going to create。

 We look right after new and see that we are creating a new point。

 so we are going to draw a box for a point which has fields X and Y。

Note that the box we just drew is not in the frame， but is outside of it。

 It is in a different area called the heap。 Anytime you use new， you create data in the heap。

 The important difference is that data in the heap does not go away when a function returns destroying its frame。

Note that we have put zero in the fields of this new point and colored them red as we have not explicitly initialized them yet。

Speaking of initialization， remember that we said that the whole point of a constructor is to initialize a newly created object。

 The next thing that happens is that we call the constructor to initialize this point。

As with any call， we set up a frame and pass parameters。 however。

 constructors and methods take an additional implicit parameter。

 which tells them which object they are operating on。

That parameter is called this and its value as an arrow which points at the object that is being acted on In this case。

 this points at the object that we are creating to tell the constructor which object to initialize Now we enter the code for the constructor and begin executing statements there。

The first line says X gets star X。 So's no X in this frame。

 So where do we store the value of star x here， x refers to the field inside of this object。 That is。

 we want to put start x's value into the X field of the object we are initializing。

 So to find the right box。 we follow the arrow for this。

 and then look for the x field in this object， and store the value3 into that box。On the next line。

 y again refers to the field inside of this object， so we update that field to be4。

Now we have finished the code inside the constructor and are ready to return to Maine at Call site1。

Back in Maine， we need to finish this assignment statement To do that。

 we need to store the value of the right hand side into the box for P1。

 A new expression evaluates to an arrow pointing at the object that it created。

 So we will make P1 to point at the newly made point。The next line does a similar thing。

 It declares P2 and initializes it to a new point。So once again， we create a box for P2。

 We haven't initialized it explicitly yet， So we have a default value of a flat ended arrow。

 meaning it does not point at any object yet。 We color it red to remember that it is a default value。

We then create a new point with its x and y fields set to default values of 0。

 and we call the constructor to initialize this point。

 Notice how this points at the newly created point。 with multiple points in our world。

 It is important that we can keep track of which point we are working on。

 We then initialize the X inside of this point to be 6。As before。

 we found the right box by following the arrow from this。

 and we initialized the Y inside of this point to be8。

Now we have finished the constructor and are again ready to return to Maine。In Maine。

 we finished the assignment statement setting P2 to point at the newly created object。

 we'll stop there and pick up with executing the method call in the next video。


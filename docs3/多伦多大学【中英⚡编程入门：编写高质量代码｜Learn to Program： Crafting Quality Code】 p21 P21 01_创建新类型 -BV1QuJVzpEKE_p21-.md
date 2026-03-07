# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p21 P21 01_创建新类型 -BV1QuJVzpEKE_p21-

![](img/66d1f9d580ada6014f60441e0aaca052_0.png)

In this lecture， we're going to explore classes a little bit more。In particular。

 we're going to write a class to represent a cash register。Before we get there。

 I wanted to show you a Canadian coin。 This is $1。 It's called a looy。 I don't know if you can see。

 but there's a picture of a loon on it。 That's why it's called a looy。

We also have a $2 coin called a tuy， which has a bear on it on one side。And the queen on the other。

So。Looneies and Tuniies are going to play a part in the lecture that we're going to do today。



![](img/66d1f9d580ada6014f60441e0aaca052_2.png)

![](img/66d1f9d580ada6014f60441e0aaca052_3.png)

Here is code that uses a type called Ca register。Here we create a new cash register。

 and it has 5 loonieies，5 tunies，5，5 bills，5$10 bills and 5$20 bills。 That comes out to $190。

 So we're going to print whatever the total value is in the register。

 Then we're going to add  three tunies to our cash register。 and then remove to 20s。Finally。

 we'll print the total amount of money in the register。$10 and90 plus 3，$2 coins is $196。

 Take away $40， And I end up with $156 in my register。

 So that is hopefully the answer we will see when we print the total after we have done these modifications to the cash register。



![](img/66d1f9d580ada6014f60441e0aaca052_5.png)

![](img/66d1f9d580ada6014f60441e0aaca052_6.png)

![](img/66d1f9d580ada6014f60441e0aaca052_7.png)

The problem is that when I try to run this。I'm told， hey， cash register is not defined。

 It's a name member。 There's no such thing yet。We're going to have to define this new type ourselves。

In order to define this type， we'll write a class cash register。

The init method with underscorees is the method that is called in order to initialize a new cash register object。

Because it's the method like convention， the first parameter is called self。

Self will refer to the cash register object that's being initialized。

We also are going to be passing in the number of looNies， tuies， fives， tens， and $20 bills。

Here's an example。This creates a cash register object and then calls the inniit method passing that object in as the first argument。

After this object has been initialized， we hope that it has a variable loonies that refers to the number of loonies in the cash register。

 Similarly， we hope that it has tunies，5s， tens and 20s as variables inside the object。

The first parameter self， refers to a cash register。The rest of the parameters refer to ints。

Method in it has no return statement， and so it returns none。

If I have self do Loies on the left hand side of an assignment statement。

 that assignment statement is going to create a variable loonieies inside the cash register object the refers to。



![](img/66d1f9d580ada6014f60441e0aaca052_9.png)

This assignment statement is what creates variable looies so that register dot Lonieies is valid and refers to 5。



![](img/66d1f9d580ada6014f60441e0aaca052_11.png)

We create the rest of these variables， in the same way。When we create a cash register object。

 we call that an instance of cash register。

![](img/66d1f9d580ada6014f60441e0aaca052_13.png)

We also call all these variables， instance variables because they exist inside an instance。



![](img/66d1f9d580ada6014f60441e0aaca052_15.png)

Here's a quick description。Let's try running this。Here we get a different error。

 we have created a cash register object successfully。

 but now we're told that that object has no attribute yet total。Even though we get this ever。

Our class cash register has been defined。In fact， we've created a cash register instance。

That instance has variables， lunies， tuNs， five， tens， and 20s。

 here are examples of examining those instance variables。When I type register and the dot。

And I wait a second Up pops the list of。Items that are inside the object that register refers to。

 so all of these variables exist inside that object。

I can actually just pick one of them in order to examine it。Now。

 let's make another cash register and have variable register to， refer to it。

The cash register that Register2 refers to also has all those instance variables。

Register tos number of 20s is 7。We can reassign the number of 20s。

Our first cast register still has its original number of 20。 We have not modified the first one。

 We've only changed the contents of the second one。Let's take a look at the memory addresses。

As you can see， the two cache register objects exist in different places in computer memory。

Let's go back and continue working on our class so that we have methods get total， add and removed。

 defined。Here's the header for method， get total。Again， the first parameter is self。

 It will refer to the cash register whose total is being asked for。

We create a cash register with these values， we expect the total to be $190。

Self refers to an instance of cash register。Yet total returns an int。

This function will return the total amount of cash in the register。Each looney is worth $1。

 Each tuney is worth $2。 Each $5 bill is worth $5。 Every $10 bill is worth 10。

 and every $20 bill is worth $20。When we run our program again， register。

gettoal produces 190 just like we wanted。And then we're told there is no attribute add in a cash register object。

Let's define one。Method add has self as the first parameter， as always。

 And then the number of items to be added and the denomination， for example。

 we might call register dot add and ask to add two tus to the cash register。

That means that when we examine Tuce， we should see 7。We can also add one to the tens。

 And then when we examine that， we should see6。Self will refer to a cash register object。

 count to an it and denomination to a string。This method doesn't f anything。

At the Bad count items of the denomination to the register。

 And we're going to spell out the denomination must be one of Loney's Tu's fives，10s and 20s。

We're going to write an if statement to determine the kind of denomination that is being added to the cash register。

If we're adding looies， then we'll add count the self do Lonieies。Wise。

 if we've been told to add tus， then we will increment tus by。Copying and pasting to save time。

We will deal with fives， tens and20s in the same way。

Method remove is going to look remarkably like method add， so we'll copy and paste it。

We need to fix the name， the description。And the dog tests。

We start with five tus and remove two of them。 We expect there to be three。

 When we start with five1s and remove one of them， we expect there to be 4。

 rather than adding to the appropriate instance variable。 we want to subtract。Scrolling to the top。

 we see that we're defining a class。The indentation indicates that underscores in knit is a method inside this class。

We also have a get total method。And an addd method。And a remove method。Looking at our main program。

 that's all the methods that we use。

![](img/66d1f9d580ada6014f60441e0aaca052_17.png)

When we run this， we see that we get exactly the values that we were hoping for。

We've defined a new type。And we can use it just like any other type that comes with Python。


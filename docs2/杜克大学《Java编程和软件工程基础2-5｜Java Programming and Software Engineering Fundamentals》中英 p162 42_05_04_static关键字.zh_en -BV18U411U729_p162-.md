# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p162 42_05_04_static关键字.zh_en -BV18U411U729_p162-

![](img/12e638987b6b96ac40e83ed1a777314f_0.png)

You just learned about the main method， which is static。



![](img/12e638987b6b96ac40e83ed1a777314f_2.png)

But what does that mean， It means that the method belongs to the class in general。

 but not any particular instance。 to see what this means。

 let us first look at non static fields for which there is one copy per instance of the class。



![](img/12e638987b6b96ac40e83ed1a777314f_4.png)

![](img/12e638987b6b96ac40e83ed1a777314f_5.png)

![](img/12e638987b6b96ac40e83ed1a777314f_6.png)

As an example， suppose you are writing some banking software。

 you decide to make a class for a bank account and declare fields for the account balance and account number。



![](img/12e638987b6b96ac40e83ed1a777314f_8.png)

![](img/12e638987b6b96ac40e83ed1a777314f_9.png)

These are great fields for a bank account class because each instance that is each different bank account has its own account number and its own balance。



![](img/12e638987b6b96ac40e83ed1a777314f_11.png)

![](img/12e638987b6b96ac40e83ed1a777314f_12.png)

If you made three instances of this class to store the data for three accounts of your bank。

 they might look like this。 You can see here how each instance has its own account number and balance。

 These fields are not static。 They exist in each instance。

Now suppose that as you write this software， you want to keep track of the next account number to assign。

So that when you create a new account， you know what number to give it。

 creating an instance variable for this next account number， as shown here， would not work very well。

 Declaring this field makes each bank account have its own next account number。

 which is not really what you want。Let's see the problem this creates by looking at a constructor you might want to write。

 which uses this next account number to initialize the account number of the bank account being constructed and then increments that next account number。

 as you see here。When you create the first bank account object。

 all the fields will start with zero values。 Then you will execute the code in the constructor。

 The first line will initialize this object's account number from this object's next account number。

 setting it to 0。Then the next line will increment this object's next account number to one。So far。

 this behavior is fine， but you will see the problem when create a second bank account object。

This newly created object has its own copy of each field。 Now。

 when you execute the first line of the constructor。

 it uses the object's next account number to initialize this object's account number。

Then you increment the account number inside the object to be one。 Oh， no。

 you've ended up with two accounts with the same number that will cause problems with your banking software。

 In fact， every account you create will be numbered 0。

The problem here is the next account number is not a property of each different bank account。

 but rather， something shared by all bank accounts。

This is exactly what static is for when something does not belong in each object of a particular type。

 but rather is shared by all objects of that type。Here you can see that we declared next account number to be static。

Now that the next account number data is not stored in each bank account， but rather。

 there is one copy of it shared by all of them。When you want to refer to a static field or method from outside of its class。

 you can do so by naming the class before the dot， since it does not belong inside of any particular object。

For this field， you could write bank account dot next account number。



![](img/12e638987b6b96ac40e83ed1a777314f_14.png)

So now you know a bit about static for static fields， there is only one copy。

 not one copy for each object instance。

![](img/12e638987b6b96ac40e83ed1a777314f_16.png)

These tend to be much less common than instance fields。

 Often you will want to describe objects in terms of properties that each instance of them have。



![](img/12e638987b6b96ac40e83ed1a777314f_18.png)

![](img/12e638987b6b96ac40e83ed1a777314f_19.png)

However， there are times when static is appropriate， so it is good to know about。



![](img/12e638987b6b96ac40e83ed1a777314f_21.png)

You can also declare static methods with regular methods。

 You can think of them as being inside of each instance， but with static methods。

 as with static fields， you can think of them as being only one shared by all instances of the class。

 Sta methods can only access static fields and other static methods of the class they belong to。



![](img/12e638987b6b96ac40e83ed1a777314f_23.png)

![](img/12e638987b6b96ac40e83ed1a777314f_24.png)

![](img/12e638987b6b96ac40e83ed1a777314f_25.png)

However， they cannot directly access non static fields or methods。

 If you wanted to access a non static field or method from a static method。

 you would need to specify which object instances， field or method you would want to operate on with that object dot。

 the field or object dot， the method。
# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p68 p67_03_demo-abstract-classes -BV1tAygYoEj5_p68-

![](img/dee62a7210d8288c23a5fdf23b60988d_0.png)

Hi， there。So it is a high time to implement abstract classes and abstract methods to understand their real time implementation。

 so let's get started。

![](img/dee62a7210d8288c23a5fdf23b60988d_2.png)

Here I' am going to create a bank account class because I understand this is the very nice example。

We have different types of bank account， and each bank account will have a common functionality like deposit withdrawal and some get balance。

 but they have different calculations。 So here I， I'll be creating。Abstract。Vid deposit。

 I will not add on the functionality。 will just add on the。Structures make you guys comfortable。

 With and balance。If the classes are abstract， if we have any method inside the class as an abstract。

 that class needs to be abstract。Forourcefully， then I'm going to create a concrete class。

 That's a saving account。I want this selling account class to extend the bank account。

When we inherit any abstract class。Inside the concrete class。

 whatever abstract methods we have in that class， all needs to be implemented。 So I'll just。

 although I can write， but I can keep my cursor onto this saving account right click on it。

Here we have sews， if you will go to the sew， there is a concept to overrite on or implement the methods。

 so it is saying that you have three abstract methods that needs to be implemented。

 would you like to do that， Yes， definitely。And that's how your deposit withdrawal and balance account definition gets created。

 I'm not making the code more complex。 Just printing the method， saving in。

Deposit and saving account。Here I'm keeping up a method。Withdraw from。四点嘅觉。Valance in sitting。

You can go to the saving account of dec creationation。Saving account， dot deposit。Saving account。

 dot withdraw。Saving account， dot balance。Similarly， you can have。More than one concrete classes。

 I can create current account as well。Current account is also going to extend the bank account abstract class。

And then all the methods needs to be over itone there。 So I'll just copy these methods。



![](img/dee62a7210d8288c23a5fdf23b60988d_4.png)

![](img/dee62a7210d8288c23a5fdf23b60988d_5.png)

I'll keep it into the current account。I'll just change the message here， current account。

Current account。And here too。Same way we have created an object of saving account。

We can create a current account。 We can create a menu driven application that press for。Press1。

4 saving account， object creation， press 2，4 current account， and so on。Current account， dot。Deposit。

Parent account， dot withdraw。Current account， dot balance。Now， let me just run this program。

And here is the deposit withdrawal。And balance in saving account。

 deposit withdrawal in balance in current account。 I think I just。

Shifted my savings account balance in the last line。Next is you can have one more iteration。

First of all， let me put a separator in between of them so that I can just see the difference。

It's not like that this is an extreme base class。 We can have any base class。

 even though I am trying to create。One more abstract class。

 abstract class can also inherit another abstract class。

 Let's say I am creating ABC bank ABC bank have two methods， two abstract methods right here。 Ab Vo。

 open account。And close account。The moment I will， I cannot。

Extend bank account and ABC bank at one given point of time in the selling account。

 because as I told you， one class can inherit only one class at a time in Java。

 but I am going to extend the ABC bank into the bank account。Right there。

 So saving account needs to overrite the open account and close account as well。 in a similar way。

 I can just go to the source。And I can override the unimplemented methods this way。So here。

 the open account and。Close account method， I think I escaped。I need to do it again。

 Just give me a minute。Not sure where it has gone。I need to go to the sew。

Override the unimplemented methods。哦。So here are the methods this way。



![](img/dee62a7210d8288c23a5fdf23b60988d_7.png)

![](img/dee62a7210d8288c23a5fdf23b60988d_8.png)

These methods needs to be。Over it done in the saving account this way。

And I am just renting a message here， says outuch。Open account。And to his account。

Same way I'm doing it with the same message in the same current account because current account is extending the bank account and bank account is extending the ABC account and I can invoke it up right from here。

Saving account。Dot open。Account and saving account。Dot close account。Saving account， dot。

 open account。And saving account， dot close account。So that's how it works。Next is what I can do。

 I also want to tell you one thing it is not required that all methods needs to be abstract only if the class is abstract。

You can create any normal non abstract method。 Let's say， message。 And here I say。Size out。

Welcome to。ABC bank。I should not write this message here。 I should write it in the ABC Bank class。

So as I told you， I cannot create the object of an abstract class this way， ABC bank。

ABC equals to new ABC bank。 I cannot do this。 So what I can do to call the non abstract method。

 I can call the non abstract method right with the help of the object of。Child class this way。

So this is how it works if you don't want to do this way also you can do one thing。

 you can make this method static so you don't need to take in help of object。Or reference variable。

 you can directly call with the class that is ABC bank dot message。That's how it works。

 Let me just run and make you guys comfortable。 So here is the exact what I'm trying to explain you。

 This welcome to ABC Bank is also coming。 So you could understand， guys。

 these two classes behaves like a contract， but you can write some functionalities along with。😊。

And all the concrete classes， which follows this contract。

 needs to implement all the abstract methods as well。 So see in the upcoming session until next time。

 Stay tuned。 Thank you。

![](img/dee62a7210d8288c23a5fdf23b60988d_10.png)
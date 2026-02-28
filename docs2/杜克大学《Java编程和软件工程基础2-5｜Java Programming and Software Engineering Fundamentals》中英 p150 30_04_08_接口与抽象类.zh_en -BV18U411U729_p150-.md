# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p150 30_04_08_接口与抽象类.zh_en -BV18U411U729_p150-

![](img/2f362bd2f867d77d4e9d2e692262126a_0.png)

Hello， we're going to look at using interfaces and abstract classes to capture common features shared among many classes in the Markov programs。



![](img/2f362bd2f867d77d4e9d2e692262126a_2.png)

![](img/2f362bd2f867d77d4e9d2e692262126a_3.png)

We developed code in the method run Markov of the Markov runner class to create random text。

 We first used Markov 0 to generate random text。 Then we changed the variable Markov from the Markov0 class to the Markov one class。

 and the code in run Markov still worked。😊，This happened because we used the same method names in Markov 0 and Markov 1。

This means Markoff。 set training worked in both classes and Markov。

get random text worked in both classes。We'd like to capture these commonalities with a Java interface so that we can use the classes in many ways。

 You may remember the interfaces comp and comparator when sorting and the filter interface we developed to search for earthquake data。

We'll design and implement a new interface to capture the commonalities here。

Let's look at developing the interface。

![](img/2f362bd2f867d77d4e9d2e692262126a_5.png)

We capture the common methods in the Markov classes by including their signatures in the interface。



![](img/2f362bd2f867d77d4e9d2e692262126a_7.png)

Here you see set training and get random text。

![](img/2f362bd2f867d77d4e9d2e692262126a_9.png)

The interface name here starts with an I。 That's a common practice。 So we've created I Markov model。

Each class that implements the interface indicates that with the Java keyword implements。

As we see here with Markov1。And again， here with Markov， too。

We already have the required methods with the required names in each class。

Using an interface will provide both utility and flexibility。 Let's look at these。



![](img/2f362bd2f867d77d4e9d2e692262126a_11.png)

We can write a method that has a parameter with the Mark model Markov model interface as seen here with the method run model。

The first parameter Markov has type I Markov model。

This means we can call run model and pass a Markov zero object as a first parameter。

 or a Markov2 object as a first parameter。The object named MZ can be passed because it has type Markov0。

 which implements the I Markov model interface。And we can pass the object named M2。

 because Markov 2 also implements the I Markov model interface。

This called a Markov dot set training will call the appropriate method in Markov0 or Markov 2 or any other class that implements the I Markov model interface。

This call to markoff。getrandom text also calls code thats specific to the object in class past as the first parameter。

This example illustrates what's called the open closed software design principle。

 The idea is that classes are open to be extended， but closed for modification。



![](img/2f362bd2f867d77d4e9d2e692262126a_13.png)

![](img/2f362bd2f867d77d4e9d2e692262126a_14.png)

Using an interface and other concepts， we'll see soon you can create a new class and use it in place of an already tested and proven class。

 you shouldn't modify code that works to extend the functionality of that code。

The I Markov model interface provides flexibility。 As you've seen。

 we can develop a new general I Markov model class that takes a place of Markov 1。

 Markov 2 and so on。😊。

![](img/2f362bd2f867d77d4e9d2e692262126a_16.png)

![](img/2f362bd2f867d77d4e9d2e692262126a_17.png)

If this class implements the IMarRRCov model interface， we can use it with existing code。

That means we don't have to modify Run model， for example， to use the new class。

We could develop a more efficient implementation using a hash map and uses this in place a Markov model。

For example， in the code， you wrote the helper function get follows that might be called hundreds of times to find the characters that follow T H。

Each time the entire text is rescanned to find the characters that follow T H by storing and reusing the follow characters。

 your code might be more efficient。 and you could use it with run model and other code because of the interface。

The I Markov model interface provides great flexibility。

 but there is some some shared code that we can avoid by developing what's called an abstract class。

Each Markov class we developed shares state and code。Sometimes that's duplicated in each class。



![](img/2f362bd2f867d77d4e9d2e692262126a_19.png)

For example， each class has a random object and the text used to model random text stored in instance variables my random and my text respectively。



![](img/2f362bd2f867d77d4e9d2e692262126a_21.png)

Many of the classes share the exact same get follows helper method that was copy pasted into each dot Java file。

We'd like to avoid this duplication by capturing the common state and code in what's called an abstract base class。

This will rely on inheritance， an extremely important object oriented concept。

 We'll touch on briefly here。 You can learn more about this and other object oriented concepts in the UCSD specialization in Coursera。

😊，Abstract based classes are used extensively in the Java。

 U package with classes like abstract list and abstract map。

 classes like Array list and hashmap are subclass of these abstract classes。

Subclass can inherit state and code or behavior。Let's take a look at the abstract base class。



![](img/2f362bd2f867d77d4e9d2e692262126a_23.png)

The abstract base class abstract Markov model is marked as abstract。With the abstract key word。

 we'll see what this means soon。The states shared across all classes like Markov 1。

 Markov 2 and Markov model。 The subclass of this class is marked as protected， rather than private。

These instance variables will be accessible in each subclass that extends this abstract based class。

 We'll discuss the word extends next。Let's take a closer look at abstract and shared methods。



![](img/2f362bd2f867d77d4e9d2e692262126a_25.png)

The class is abstract because there is one method in the abstract Markov model class labeled as abstract。

That method is the get random text method。Which is implemented differently in each class that extends abstractject Markov model。

 These are called subclasses。The helper function gi follows， is labeled as protected。

 It can be called in each subclass just as the protected instant variabless can be accessed。

Let's look at extending the base class。You can see the class Markov model that inherits state and behavior from the class abstract Markov model we've been looking at。

The keyword extends， means that this class gets instance variables and get follows code from the super or parent class。

Because this super or base class implements the I Markov model interface。

 This Markov model class implements the same interface that's inherited from the super class。

This class has its own instance variable， my order， marked as private。

 as you've done in previous coding examples。Classes that extend an abstract class must implement the abstract methods。



![](img/2f362bd2f867d77d4e9d2e692262126a_27.png)

The abstract Markov model class has one abstract method， get random text。

This means the class Markov model must implement this method， as you see here。

The Markov model subclass ins protected state and behavior from the superclass。

This includes the protected instance variables， My random。And my text， the training text。

Someclass can call inherited methods too， like get follows。

We'll summarize the interface and the inheritance example。

The key idea of an abstract based class is to implement the interface。

And to supply default functionality when that's possible。

To avoid duplicating state or behavior in each subclass。



![](img/2f362bd2f867d77d4e9d2e692262126a_29.png)

Subclasses like Markov 0 or Markov 1 will extend the base class。



![](img/2f362bd2f867d77d4e9d2e692262126a_31.png)

Extending the class means that the subclass inherited the interfaces of the parent or superclass so that subclasses implement I Markov Model 2。

This means client code won't change the code that relied on the interface will still work。

Some methods in the abstract base class are labeled as abstract。

 Subclasses must provide implementations。We saw different implementations of Gett random text in Markov 1 and Markov2。

 for example。Happy programming。
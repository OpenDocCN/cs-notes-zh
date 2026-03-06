# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p45 p44_05_dependency-injection-using-constructor-and-setter-method -BV1fryaYgEqb_p45-

![](img/fd3b7edd7f7a7794bcd4974530505a04_0.png)

Hey guys， in this session we will discuss what is dependency injection in spring and what are the different types of dependency injection so lets get started。



![](img/fd3b7edd7f7a7794bcd4974530505a04_2.png)

Basically， dependency injection is a fundamental concept in the spring framework。

 and it refers to a design pattern。Objects that are provided with their dependencies。

 rather than creating them internally。So dependency injection is achieved through the Ioc where。

The object of one class needs to be injected into the another class rather than instantiating it。

 so there would be no。Type coupling into two classes or two objects。

 So if you consider two classes A and B， say that the class A uses the functionality of class B。

Then it's implied the class A has a dependency of class D。It mainly involves three classes。

 client class， service class and inject class。

![](img/fd3b7edd7f7a7794bcd4974530505a04_4.png)

When we talk about this architecture， that。Service is the something that is created as a dependency。

That being used by the client and the injector is something in which the constructor or setter needs to be created。

 Let me help you out practically。Benefits of the dependency injections had to increase the cohesion of the part of the application reduced the coupling between the part of the application that also helps in creating a loose coupled architecture。

Better designing of the application， as I said it a part of the design pattern also and reduces the boiler plate code。

There are two types of dependencies， there are two types of dependencies that you can implement one is a constructor based dependency and one is a set based dependency。

 some people say it as a field based dependency also。In the constructor based dependency。

 the constructor needs to be there in your bin to iterate what properties you wanted to pass just like this code。

And in the case of set based property that we discussed already in the last session。

 we need to pass on the properties and for that we need at least one default constructed and the set methods associated to the property that we wanted to instantiate。

Let me help you out practically how the dependency injections can be achieved in real time。

So guys in the previous demo I already discussed that we have a hover dot Java as a be and where we have the getter and setter of this。

 so here we could see that first of all， if I do not write any constructor inside this。

 I should not get any error， let me just save it。And go to the application dot。

Java and run the program。Perfect， so here you can see that if I go to my resources package where application dot context is there when we are saying it's a property。

 it is a set property， you can also go to your hollow word Se property of this message and try printing a message by writing a out。

Setting message property。And that's how you will call your application。

 Java your you can evaluate that your set method is also invo and your ho message is going right there。

 but if you would like to inject it into the constructor via the constructor。

 you need to go to your context。Let's say here I'm going and saying that it's a hello again。哦。

Another。Here， rather than property， I would like to set the constructor argument。

Where I need to define a couple of things like we need to define the type。

So you need to come here and say that constructor argument and you can define the name of the argument that is message。

And that you can define with the value that you would like to assign into it， let's see hello。

But for that， you need to have constructors in your beam， first of all。

 you should have a default constructor and then the parameter is constructor。

So just come up and say you wanted to generate the default constructor。

 I don't want to write it by myself。And once this construct is generated。

 will go for a parameterized one。You can also it a message here just to check whether your constructor gets called up by not。

Default constructor。Invo。And the same I wanted to print for the parameterized one。

So I need to go to the application D context， application context dot Xl。

 the constructor is passed argument is passed。This one I just wanted to use by halo beam。

 rather halo another beam rather than the hollowlo。

 because over there the constructor is getting injected。

So here you can see that the default constructor invoked set message property invoked and the parameterized constructor invoked。

So this is how you can specify your constructor and the set property as well。

I hope the concept is pretty clear to all of you how the dependency needs to be injected。

 and we are all set to use this dependency in our spring or spring boot application until next time I see in the next session stay tuned。



![](img/fd3b7edd7f7a7794bcd4974530505a04_6.png)
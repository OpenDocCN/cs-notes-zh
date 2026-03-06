# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p44 p43_04_spring-bean-spring-scopes-and-life-cycle -BV1fryaYgEqb_p44-

![](img/6768ed855cc1acf4f1e89e298f2d5a8e_0.png)

Hey， guys， today in this session， I will talk about spring beans。

Spring scopes and the whispersp lifecycl。

![](img/6768ed855cc1acf4f1e89e298f2d5a8e_2.png)

Basically， the objects that form the banbone of your spring application or web application using spring that are managed by the spring I you see。

Containers called the beans。 So a bean is nothing but an object that is instantiated assembled。

And managed by spring Iioi container。As I said， you can configure the spring met information with the help of Xzel definitions or Java annotations。

I have already demonstrated you with the help of the Xzeel。

 There is a bean can that be defined with the help of this bean tag。And in the annotation。

 we use aate bean annotation to create or configure any beam injection。

We do have some other annotations like aggregate rate component aggregate rate service container and repository on the top of the class definition to be used in the spring be life cycle。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_4.png)

Whenever we work with creating the beans， we do have a beam scopes that is singleton prototype request translation。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_6.png)

Basically， when defining a being， you have the option of declaring a scope for that being。

 for example。You would like to create a new bean instance each time when the spring produces or generates。

 so you should declare the be scope attribute to the prototype that is as a single turn。Otherwise。

 we have singleton prototype request session as well as global session that is known as an application。

Singleton scope is basically set to the singleleton when it creates exactly one instance of the object for the entire application。

The singleton instance is stored in cacheier of such singleton beam and add the subsequent request and references for that named bean returns the cacheier object。

The default scope is always a singleton， However， when you need one and only one instance of a bean。

 and you can set the scope property to singleton in the bean configuration file as well。

Next we have prototype scope in the prototype scope， what gets happen is。

If the scope is set to the prototype， the spring Iio container creates a new bin instance of the object every time a request for that specific being is made。

As a rule， use the prototype scope for all stateful beans and the Sleton scope for the stateless beans。

So this is how the scope prototype needs to be given while creating a being as well。Next。

 we have request a。Prototype， request scope。In the request scope what gets happen is the container creates a new instance for each and every HTP request。

 so if server is currently handling 50 requests a 50 individual instance of the bean class needs to be created。

Any state changes to the one instance will not be visible to the other instance。

 their scope is completely individual。Session scopepe container creates a new instance for each and every HP request。

 so if the server has 20 active sessions 20 individual instances needs to be created。

 but request within a single session will have the access to same single bin instance。

Any state changes to one instance will not be visible to the other instances that you can define with the help of aides scope session。

Application scope is also known as a global scope that container creates one instance per web application at runtime。

You can if you have any idea about ser context or s config in the GSP and Sur s context associates to the application scope that you maintain to escalate the data to be used throughout your application as well。

Weap soet is being depreciated in the latest versions。

 but if you use any previous version that allows the two way communication between a client and remote host。

And that has opted into communication with client。So， this is。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_8.png)

How this scope needs to be given。Next， we have a spring life cycle。Springbe life cycle。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_10.png)

Basically， the life cycle of any object means when and how it is born and how it behaves throughout its life and when it and how it dies。

 Similarlyly， the bean life cycle refers to when and how the ven is instantiated。

Being life cyclist managed by the spring container。 When we run the programme， then， first of all。

 the spring container gets started。After that， the container creates the instance of a bean as per the request and the dependencies are injected。

 And then finally， the bean is destroyed when the spring container is closed， Therefore。

 we want to execute some code on the bean instantiation。 And just after closing the spring container。

😊，We， we can write the code inside the custom in it method and destroy method to write any specific code inside it。

As I said， you can implement the beams using Xl annotations or Java basede and configuration。

So this is how the life cycle works in spring。So as I said that， first of all， your。

Life cycle is managed by the spring container。 Your bin is created。

When we run the program and then the bean has started and just after that the container creates the instance of the bean and as per the request dependencies are injected。

And finally， if you have any in it or destroy code can be written。

 which is a cleanup code you can maintain in these methods。And finally， when the bean is destroyed。

 the spring container containers are closed， and we want to execute some coat on the bean instantiation。

 And just after closing the container， we can write in the init method and the destroy method as well。

 and your bean is ready to use。You can also create the custom beam life cyclee by providing the four ways for controlling the life cycle events of the beam。

 just like initializing the beam disposable beam colible interfaces。

Writing your custom code for initializing the bin in the init method and destroy method for any cleanup code。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_12.png)

![](img/6768ed855cc1acf4f1e89e298f2d5a8e_13.png)

As well， any post， construct and pre destroytroy annotations are also given if you wanted to write down any。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_15.png)

Initialization in those。

![](img/6768ed855cc1acf4f1e89e298f2d5a8e_17.png)

Stay tuned to learn more about spring， spring dependency injection as well。 how the set methods and。

Properties help in injecting the dependencies in the spring。



![](img/6768ed855cc1acf4f1e89e298f2d5a8e_19.png)

See you in the next session。
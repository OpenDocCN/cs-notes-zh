# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p148 p76_05_angular-module -BV1tAygYoEj5_p148-

Hi there in the previous video we learned about angular components now in this video we will learn angular modules so let's get started。

In Angular， a module is a way of organizing and packaging related components， services。

 directives and other building blocks of an application。

It kind of acts as a container that groups together the functionality required for a specific feature or a set of closely related features。

So in angular， we have two types of modules。Root module and feature module。

So the root module typical named as art module is the entry point of the application。

It bootstrapps the main component and imports other features， modules and angular libraries。😊。

The root model is responsible for orchestrating the initialization of the application。



![](img/fe58e986bcfb4163364fb5341a12e491_1.png)

So if we go here and you can see we have app dot module or Ts and this is the root module that we are talking about。

And it is normally by the name of app module， as you can see here。



![](img/fe58e986bcfb4163364fb5341a12e491_3.png)

Next， we have feature module。A feature module is a module that encapsulates a specific set of related components。

 services and other artifactacts for a particular feature or functionality。

Feature modules can be independently developed， tested and reused in different parts of the application。

Creating angular modules provide several benefits like modularity encapsulation。

 dependency management， lazy loading and code organization。😊，So， to create a module。

You can use Nng module decorator provided by angular。

 and this Nng module decorator is used to define the metadata for that particular module。

 such as its declaration like components， directives and pipes or imports。

Exports and providers as well。 So let's try to create one module ourselves。



![](img/fe58e986bcfb4163364fb5341a12e491_5.png)

So let's go to this project and this is a basic angular project up and running on the server。



![](img/fe58e986bcfb4163364fb5341a12e491_7.png)

So in the terminal， I will run a command， let's say Nng and generate。

And we need to generate module so we can put module here and lets put the module name as user off。

Now let's click on enter。You will see that a new module has been created by the name of user O and if I go to user or dot module or Ts。

 you can see this is the default structure we get and there are some default configurations like common module imported here。

So this is considered as a feature module， or you can see normal module here。Now。

 we want to create a components inside it。 So for that。

 we can go to the terminal and we can say N G generate。Component this time。And if I。

 let's say create a component logging like this， it will create the component globally。

 but we want to create it inside user Earth so we can say user dash o slash login。

And now I press on enter， you will see that a new module has been created and login component has been declared in our user O dot module。

So here it is declared， but first of all we need to import this user Earth module into the main module that is the root module here。

So here we can call our user。Outh module from user o and user o module。

 So this is how we connect the user art module with the root module。Now， inside the user or module。

 we have this login component。 So we need to export it as well。 So after the imports。

 we can say comma， and we can create exports。And we can export。Our login component。

And if I go to the login component dot HTMLm， so you can see we have login works here。

And if you go to component dot P S， you will see that we have a selector as app log。



![](img/fe58e986bcfb4163364fb5341a12e491_9.png)

So to put this into our app， currently， our app is like this。

 we can go to and we can load our app login at this point。



![](img/fe58e986bcfb4163364fb5341a12e491_11.png)

![](img/fe58e986bcfb4163364fb5341a12e491_12.png)

So if I click on save， you will see that we have login works here。

So congratulations you have created your own module inside that you have created your own component。

So， let's summarize this。By leveraging the concept of angular modules。

 you can create a modular scalable and maintainable application。That promotes code reviews。

 separation of concerns and efficient dependency management。This is all for this video。

 See you in the next video。 Thank you。

![](img/fe58e986bcfb4163364fb5341a12e491_14.png)
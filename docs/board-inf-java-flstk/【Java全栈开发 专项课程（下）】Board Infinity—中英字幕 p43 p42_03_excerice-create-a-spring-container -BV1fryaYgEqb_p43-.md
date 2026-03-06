# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p43 p42_03_excerice-create-a-spring-container -BV1fryaYgEqb_p43-

![](img/8c2cc21e3feb84bdaf1d91592cbce2e7_0.png)

Hi there。 Today In this session， we will discuss how to create spring I OC container。😊。

That is responsible for instantiating， configuring and assembling the spring beanss。As I discussed。

 this configuration of the metteradata can be represented by Xzeiml Java annotations or Java code。

So I will be using Xzel configuration for this demo。So let's get started。



![](img/8c2cc21e3feb84bdaf1d91592cbce2e7_2.png)

For this spring application， I will go to generate the Mevin project。

As I said that you need to select the project skeleton type。

 but I will go for a simple project I don't want to generate any web application or something。

Giving a group I D S Comd Pana Gvani spring I O C container。Example。And just finish it off。

 So it's a simple core Java project developed by Mevin。

 where I will configure my spring I O C container。Project generation sometimes takes time。

 so don't worry about it。But I am using the working set。

 so I need to edit my working set by the project that's being generated to be added into the working set。

So here is a project gets generated successfully。 there is a SRC main Java。

Where all the files needs to be kept。There is a palm dot TimL file where each and every iteration will happen。

 dependency， storage or any configuration that needs to be done。So first of all。

 I need to change this GR system library， although I can keep it writing directly into this Pm dot Xl。

Otherwise， I can just right click on my application and go to the properties。Over the properties。

 there is a J。Compilr， Java compiler by default， It's coming as 1。5。 Let me just change it to 1。8。

 at least。And just apply and close。Once this change is done。

 you need to just go to the Mevevin and update your project。So once you will update your project。

 any changes done in the application or in the Po dot Timl that gets modified。Lately。

 I need to go to the podo Ximl and add the dependencies。And you know。

 from where I need to take up these dependencies， the website， which I have told you。



![](img/8c2cc21e3feb84bdaf1d91592cbce2e7_4.png)

So from here， I can take my。Spring context or a spring core。

 spring context is imbibed with the spring core as well。

 so I can just take a spring context to create my IO container。



![](img/8c2cc21e3feb84bdaf1d91592cbce2e7_6.png)

Whichever version you are compatible， you can take it up I'm just checking 6。0。9。



![](img/8c2cc21e3feb84bdaf1d91592cbce2e7_8.png)

And this dependency I kept inside it。Once you will save this change。

 the dependency gets added into your project。 You can see that here is a meven dependencies where all the spring core context。

 this is the benefit of adding the dependency into the meven。Project。

 whatever supported libraries or the packaries will require that gets added automatically。Guys。

 in case your project is not getting updated by G or you want to do it manually in your application so you can just come before the dependencies and go and add the properties。

And here you can just select the Mevevin compiler by your own Mevin dot compiler。Dot target。

I can write 17 here because I'm using 17， so that's fine。And here I need to also provide the source。

Whenever you make any change into your。Pm。eximl always suggested to update your project。

 just right click on your application go to the Meven updateate project。

So you can see that your Java standard edition is modified with the latest one， which the。

Id E could support， also。Once it is done， what next you need to do is you need to。

Provide your I O or a beam So under the SRC name Java。Going to create a class。

Keeping this class into Commd Ppnaganvanni。Comm dot。Bapnaguwani dot， spring dot i O。

Naming this as halllo for the time being。Just keeping one property here。 That's private。

String message。Then I'm going to generate the getter and setter for dystro。In case required。

 I am also generating the two string method。Where I'm simply returning。Whatever I want to print。

Once my I O C is ready， I need to configure it。Further， we need to go。

We can just generate this with the help of the generator， no problem。Once it is done。

 what next we can do is we need to go to the SRC main resources and create the application context do Xml。

You can name this file anything generally we keep it。

 name name it as application contact so that it contains all the big information。

I will go to the sewers。 I need to modify the name spaces， which my being required to generate。

 You can use the same as mine。And inside this being。

 I can simply instantiate whatever classes we have and the object we wanted to pass。

 So I have a hollow word， so I will be creating a be for hollow word。Where the beam is I D。Helloever。

From the class coming right where Com dot Pna Gwani dot spring dot ioc。Inside that。

 I have one property to be passed property。Where the name of the property is message。

And the value that needs to be passed inside， it is halled。So once my bean is ready。

 I need to create the spring container。I will just right click on my application。

Will generator mean class。Under the base package。Comm dot Pabna Gmanni。 that's already written。

I can write applicationli。That will have a main method。Under this main method。

 I will instantiate application context from the beam context。Context equals 2。

As I am using Xl configuration to Ximl application context under the resources package。

 you have kept it as application。Dot context that you can application context dot examine that you can refer here to read the beanss。

And just to retrieve the beans， you need to say hellover。

Object equals to you need to typecast your context to the how word class， context dot。

 get being whatever be ID you have given there， I have given it as a camel case Huello。

That needs to be typecasted into the ha type。That it， your object is ready。

 You can try printing your OBj that will display whatever you are instantiating from your XML beaman container。

So here I'm going to run my application， that is Java application and my bean details are ready。

So this is how the spring I O container can be created with Xzel the same configuration that I have done in my。

Application context or Ximl can be done in the Java annotation based or a Java file itself。

I hope the concept is clear to all of you stay tuned to use these beans in your upcoming spring projects。

See in the next session until next time， Stay tuned。



![](img/8c2cc21e3feb84bdaf1d91592cbce2e7_10.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p103 14_01_06_Rust与Python的对比使用.zh_en -BV11y411z7Dn_p103-

![](img/3e937e6e71bd009bd1d3af2ebbcad753_0.png)

There are several reasons why you may want to consider using rust instead of Python and we'll cover a couple big reasons here in this lesson。

 so one of the things that I want to mention is that and I have here the Azure the Microsoft Cloud。

 Azure side here for container apps to give you an example as to kind of like are what is one of the main problems here when when you start or challenges rather when you start trying to decide which one which programming language to use。

 so specifically look for the Azure container apps pricing here because I want to demonstrate what's the difference between one of the big differences between Python and rust and that is the consumption of memory and CPUs。

 when you want to deploy your applications to the cloud you will start trying to figure out how much is that going to cost。

Well for us it's going to be an order of magnitude cheaper because it's much。

 much less memory and CPU requirements than to run Python。

 so for Python you're going to have to put at least a gigabyte in containers to try to do something useful of course it always depends on what you're trying to do。

 but it is going to be much more expensive so let's take a quick look here at the pricing explore pricing options in the consumption plan。



![](img/3e937e6e71bd009bd1d3af2ebbcad753_2.png)

So I've been able to actually deploy a rust application。

 a web API by using a quarter of a CPU do you see here the free grant per month and it says 180。

000 virtual CPU per second so by being able to deploy in a quarter of a CPU that means you're quadrupling the free grant because you're able to use not a single not a fully single virtual CPU for every second and the memory requirements I've been able to go as low as 100 mebyte of RA for applications and you have here this is measured in gigabytes per second and you have 360。

000 gigabytes per second so you start seeing a stark difference between these options and what is possible with rust and Python just by using a simple dollar。

Amount in a calculator， you can see that this is a pretty compelling reason。

 but beyond that you're getting sheer performance by rust and the ability to run and publish your project easily to one of these cloud providers and as well if you don't care about a cloud provider you want to deploy locally well the same thing happens where you're getting a lot more processing power。

 less less ra consumption， less memory consumption and an amazing an amazing performance。

 Now I mentioned that distributing your project and and sharing it and deploying it Well。

 one of the problems here with Python is packaging in general whenever you want to distribute your project in Python things can get complicated if you are looking at dependencies Now traditionally historically Python packaging has been problematic and although there's been。

Any different positive changes in the Python packaging universe there's still several challenges that are kind of tricky to deal with and kind of to try to understand First off when you get a Python installation the first thing that they'll tell you is that well you have to try to make sure that you have Pip Pip is a Python package installer but it doesn't it kind of like comes bootstrap with your Python installation。

 but it also tries to make you get like a newer version of the installer Now there's several different ways to installer and to your dependencies And here in the official packaging the Python org website。

 they have this official guide where they will actually give you several different ways of well actually try to give you one but they don't give you the actual。

There's no strong single opinionated way of doing things and you will see here on the creating the package files that it mentions a Tamil file which actually is one of the many different ways where you can define your dependencies you can also have a requirements。

 the text file， you can also have a set of that P file and in our projects have like different other ways。

 although the P project that TmL is kind of now one of the official ways of installing and defining your dependencies。

 you will still need something like Pip to be install which is the package installer or you will have to install these other package called build that it doesn't come with Python that you need to install it separately and build comes from you have to install it with PP and you need to make sure that whenever you're installing it well you will have to use a virtual environment that haven't mentioned virtual environments before。

 but it's a way。Of installing your packages in an isolated way。

 I also mentioned setup pie and that is supported by setup tools and you can see here that other tools are mentioned。

 you have fl pm and other things that you can actually use so there's many。

 many different things that you have to start defining how these things going to get packaged and distributed Now setup tools。

 I don't really understand I haven't used F before， but setup tools for sure。

 and then you can configure your metadata， which is you know pretty straightforward looking。

 but this is very highly complex once you have everything ready like the readme and the license。

 you might want to make sure that you're ready to build your project and here it tells you well you will probably need to install this other thing called build which I mentioned before and then you're gonna have to upload your distribution archive。

So whenever you're ready to publish your project， you're going to probably look at installing a different tool and for this is twine so now we're like at four or five different tooling for packaging alone This is very complicated and is not opinionated to use like a single tool one of the main benefits of rust is that you will use something like cargo in cargo and if we take a look at the cargo book it is the rust package manager it will allow you to install。

 it will allow you to build it will allow you to test it will allow you to format to Li to upload to publish and do all kinds of different things it is the single tool that that you need and the cargo package manager will use the cargo that Tael file which is similar and it' a structure to the。

ophil but this simplicity and highly opinionated way of doing things will allow you to do without the complexity of having several different tools and fragmentation of tools for installing publishing and doing anything else that you see in Python beyond that when you create a cargo binary you're ensuring that absolutely everything will be included in a single binary or a single executable that will run in a system that has the same CPU architecture so once you build it。

 it is very easy to distribute the application to many different systems。

 so tremendous benefit allows you to easily distribute your your tool allows you to have like a single opinionated way of doing things with a package manager that is that has a much straightforward。

Way of building， installing dependencies and publishing your package later。



![](img/3e937e6e71bd009bd1d3af2ebbcad753_4.png)
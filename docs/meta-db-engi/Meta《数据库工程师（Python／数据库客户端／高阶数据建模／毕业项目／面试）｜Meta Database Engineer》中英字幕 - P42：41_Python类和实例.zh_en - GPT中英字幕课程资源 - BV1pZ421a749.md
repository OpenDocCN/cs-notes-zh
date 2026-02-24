# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P42：41_Python类和实例.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Classes have the ability to combine data and functionality。

 which is a very useful feature when you are coding By the end of this video。

 you'll be able to explain what classes， instances and objects are in Python。

 you'll also be able to create a class instantiate it and access its variables and methods。

 You may have also heard of classes discussed in terms of attributes and behaviors。 In general。

 attributes refer to variables declared in a class while behaviors are associated with the methods in a class。

 C a class creates a new type of object from which you can create instances。

 an important thing to keep in mind is that everything in Python is an object or derived from the object class。

 to demonstrate how this all works。 I'll create a class that I can then derive objects from in a new VS code file。

 I first type the keyword class。 followed by the name my class and a colon。

 I do need to take one more step so that Python doesn't throw an error。😊。



![](img/8791cafe15c5994abba6df25d6f07558_1.png)

And that is the type the pass keyword on the next line。

 The pass keyword plays the role of a placeholder where nothing needs to be executed。 In practice。

 this tells Python that I won't do anything with this class just yet。 Next。

 let's create an object for this class。 I create a variable called my class。

 and then assign the class to it by typing equals my class followed by parentheses。

If I run this code， the output shows that it has executed without errors。However。

 just to check that it's working as expected， let's add a print statement to the class。

So that would be print followed by the string Ho in parentheses。When I run the code again。

 the word hello appears in the output。 Let me clear the terminal before continuing。

 You may have noticed that I used the same name for both the class and its object。

 but the object name can really be anything。 For example。

 if I change the object name to M Y C and run the code once more， it will execute the same as before。

 Everything I've typed is part of the instantiation process in Python。

 which involves three key steps。1 class definition，2， creating a new instance and three。

 initializing the new instance。 Since everything in Python is an object。

 it makes sense to follow naming conventions to make things less confusing later。 In this case。

 I have my class for the class object and M C for the instance object。

 There is a third type of object called the method object。

 which you can use to call a method whenever it's needed。

 Class mainly perform two kinds of operations。 attribute references and instant。

I've already written an example of the latter， so let's try building an attribute reference this time。

First， I create a variable A for the class object and assign it a value of 5 to print this variable。

 I first need to refer to the class。 So under the instance object， I type print and then my class a。

When I run the code， it returns5 in the output。To confirm the class reference is necessary。

 I delete my class from the print statement and run the code again， and Python throws an error。

So I'll correct the code and put my class back in。Let me clear the terminal quickly before continuing。

 So you know what happens if you reference a class object。

 but what if you reference an instance object， let's find out by typing a print statement for MC do a and then running it in the output。

 I get5， which shows that attribute reference still works with instance objects。Finally。

 let's finish up by creating a method inside this class。

 I'll use the deaf keyword and follow it with Ho， a pair of parentheses and a colon。😊。

On the next line， I type a print statement for the stringHello world。

 I'll also delete the first print statement to avoid confusion。To call this method。

 I add a new print statement at the end of the document for MC dot hellello。

 which uses the instance object。 This should work just as I successfully called the variable through an instance object。

 right， running the code results in an error。 So methods are not quite as simple。Fortunately。

 I can resolve this by adding the keyword self within the parentheses of the method as defined in the class。

Running the code again produces the wordsHlow world in the output。

You'll also find the word none printed below as there is no return value from the given function。

 That's a brief demonstration of classes， instances and objects。 I created a class。

 then I was able to instantiate it and access its variables and methods。



![](img/8791cafe15c5994abba6df25d6f07558_3.png)

![](img/8791cafe15c5994abba6df25d6f07558_4.png)
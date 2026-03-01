# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P15：15_02_02_万物皆数字.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/855a4da2a41511271556f7d030e48ae9_0.png)

Welcome back In this lesson。 you're going to learn an important principle of computer science。

 Everything is a number or put a different way。 Comps only work with numbers。

 If we were to delve into the hardware， we would find that it only deals with bits， zeros and ones。

 We are not going to look into the particulars of the hardware。

 But the important thing to know is that computers can only work with numbers and really can only do math。

 In fact， there's nothing that a computer can do that you cannot do。

 Comps can just do math really fast so they can operate on large sets of data billions of times more quickly than you or I could by hand。

 Fortunately， you do not typically need to think about the details of the bits due to a wonderful principle called abstraction。

 before we talk more about how everything is a number we'll take a minute to talk about abstraction。

😊，Abstraction is the separation of the interface， what a thing does or how you use it from the implementation。

 how it does that， or how it works。You can understand abstraction and its usefulness when a noncomputer related example。

 Think for a moment about driving a car。 Abtraction lets someone drive a car without knowing how it works。

 I know that if I press down on the gas pedal， my car will go faster。 However。

 I do not know about the complicated inner workings of my car that make that happen。

Abstraction often comes in layers and what layer you need to work at depends on what you need to do for someone driving a car。

 the level of abstraction appropriate to think about is what the controls of the car do。

 The inner workings under the hood are hidden and nonimportant。However， for a mechanic。

 the details under the hood are important and are what she works with day to day。

 but even there there is a different level of abstraction。

 the mechanic is concerned with how the parts of the engine fit together and work together。

 but maybe not with the physics that go into designing the engine。

The engineers who designed the car would have worked at that level of abstraction。

 applying physics to make a car that works properly。 Of course。

 there is an even lower level of abstraction in a more theoretical physics that they did not concern themselves with。

 We could keep going down until we reach the most theoretical physics at the boundaries of human knowledge。

 All things that you do not need to know to drive a car。These same concepts apply in programming。

 the level of abstraction that you need depends on what you are doing before this class you have probably used a computer without knowing anything about how programs work Now you will learn how programs work but there will be deeper levels of abstraction that you generally will not need to know about。

Now that you know about abstraction， let us return to the principle that everything is a number。

 giving you a bit of a peek under the hood。You may be a bit surprised by this idea since you're used to using your computer working with things that do not seem like numbers。

 such as letters， however， these are relatively easy to encode as numbers。

 we could go with A equals 1， B equals 2 and so forth。

What computers actually do is represent characters， symbols that can be letters， digits。

 punctuations， and so on。 One way to encode characters is ASCI in which capital a is 65 lowercase A is 97 exclamation mark 33 and various other characters have other numerical values if you needed to look up the numerical value of a character。

 you could find them in an ASCI table， however， you generally do not need to worry about the particular numerical values due to the joys of abstraction。

Once we have characters， we can also have strings， sequences of characters。

 such as Hello exclamation mark。Strings come up quite often in computer science as programmers frequently want to manipulate text。

 In fact， you've seen strings in HTML。Strings are another great example of abstraction。

 you can write hellello exclamation mark and it gets turned into numbers that your computer can work with。

 you generally do not have to think about the numeric representation。

 but you can manipulate it if your programming task calls for it。

So why is it so important to know that everything is a number Well sometimes you want to do math with things that do not seem like numbers cryptography。

 the science of keeping information secure， relies on the ability to do math on strings when you visit a website using HTTPS the information sent back and forth between your computer and the web server is encrypted so that nobody else can read it that process involves doing math on that data。

Another reason that it is important to understand that everything is a number is because this is why programming languages have types which tell it how to operate on these numbers。

 even though everything is a number， programmers want to interpret those values in different ways Do the numbers mean letters do they mean pictures。

 do they actually just mean plain numbers do type of the data tells what the numbers mean and thus how to operate on them。

 if we add two strings together， we might want to concatenate them。

 put one after the other to form a longer string。In that case。

 the string 1 plus the string 1 would be the string 11。

If we have just the number one and we add it to one， we would get two。

A third reason why everything is a number principle is important is that whenever you have data you want to work with。

 you need to represent it as numbers， you may be able to use existing types such as strings which already represent information as numbers to help you out。

 such as the joy of abstraction。One other thing that may surprise you is that programs themselves are numbers。

 then again it may not surprise you since you just learned that everything is a number。



![](img/855a4da2a41511271556f7d030e48ae9_2.png)

As you have already seen， you express your algorithms to the computer by writing text。

 the code that you type in is a string。Another program takes this string and figures out how to turn it into numerical instructions that the computer can execute。

The fact that programs or numbers is actually quite powerful。

 it means that you can download and run new programs on your computers。

 they are just data like everything else。The fact that programs are also just like data is at the heart of many security issues hackers give program input。

That have the numeric encodings of instructions they want to execute and then trick the program into running it。

Of course， as you write programs， you do not need to worry about the numerical encoding details all because of the wonderful ideas of abstraction。

So in this lesson you learned that everything is a number。

 an important principle since computers can only do math， you learned about abstraction。

 the separation of interface from implementation， and how that means that you may not always need to think about how things are numbers to compute with them。


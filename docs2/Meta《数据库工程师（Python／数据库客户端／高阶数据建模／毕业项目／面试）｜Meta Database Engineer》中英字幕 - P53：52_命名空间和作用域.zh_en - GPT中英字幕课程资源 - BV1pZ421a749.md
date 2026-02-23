# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P53：52_命名空间和作用域.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Now you should be fairly familiar with how modules work。

 let's look at another related concept in Python， namespaces and scopes。

The official Python documentation defines namespace as mapping from names to objects。

 and scopepe is the textual region of a Python program where the namespace is directly accessible at this point the dictionary with its key value pairs serves as the ideal data structure for the mapping of names and objects。

You have also learned how every Python file can be a module。

 You can view the same module as a place where Python create a module object。

 A module object contains the names of different attributes defined inside it。 in this way。

 modules are a type of namespace。 Namespaces and scopes can become very confusing very quickly。

 and so it is important to get as much practice of scopes as possible to ensure a standard of quality。

 There are four main types of scopes that can be defined in Python。 Local enclosed。

 Global and built in。The practice of trying to determine in which scope a certain variable belongs is known as scope resolution。

Scope resolution follows what is known commonly as the LEGB rule Let's explore these local。

This is where the first search for a variable is in the local scope。Enclosed。

 this is defined inside an enclosing or nested functions。

Global is defined at the uppermost level or simply outside functions。And built in。

 which is the keyword present in the built in module in simpler terms。

 a variable declared inside a function is local， and the ones outside the scope of any function generally are global。

Here is an example， the output for the code on screen shows the same variable name Greek in different scopes。

There are three possible declarations of the variable。At the global level。

 inside the function B or inside the nested function C， which is called from within B。

The ID function is used here in the print statements， which return to the identity of the objects。

 you can make some observations from the output。The ID for the global variable alpha remains same as defined after the code is completely executed。

 the ID for the local variable beta inside the function B remains unchanged before and after the execution of nested function C。

The ID for gamma is assigned only within the scope of the nested function。

And the ID for all three variables is different， even if they all have the same variable name variabless in Python are implicitly declared when you define them。

 That means unlike other programming languages， there is no special declaration made in Python for the variable which specifies its data type。

What it also implies is that a given variable is local。

 not global when it is declared unless stated otherwise。😡。

This contrasts with most other programming languages where variables are global by default。

 So when a variable is declared in a global space， it is also local to that space。

 This can be understood with a simple example。If you look at the content of both of these dictionaries。

 you can see how the value for the key country is different in both of the cases。

You have also used two special built in functions called Locals and Globals that list the contents of the dictionary inside both of these scopes here you can see the output in this example you can see the global variableable declared remains unchanged。

While global variables are acceptable， they are discouraged for a number of reasons。

When you are working with production code， the project structure can get complex and working with global variables can be hard to diagnose which lead to what is called this spaghetti code Other paradigms such as access modifiers。

 concurrency and memory allocation are better handled with local variables While you are just beginning our journey using Python。

 it is always a good idea to integrate good practices in your code。

 There are two keywords that can be used to change the scope of the variables Global and nonlocal the global keyword helps us access the global variables from within the function。

Non local is a special type of scope defined in Python that is used within the nested functions only in the condition that it has been defined earlier in the enclosed functions。



![](img/2d9ad7995fe99753cf448c7f1a04cd69_1.png)

Now you can write a piece of code that will better help you understand the idea of scope for an attribute。

You have already created a file called Animfarm。pyY You will be defining a function called D inside which you will be creating another nested function E。

Let's write the rest of the code you can start by defining a couple of variables both of which will be called animal。

 the first one inside the D function and the second one inside the E function。

 note how you had to first declare the variable inside the E function as non localal。

You will now add a few more print statements for clarification for when you see the output。Finally。

 you have called the E function here and you can add one more variable animal outside to the D function。

This will be a global variable you can add a call for the D function and a print statement for the global variable。

You can save this file and run the code。First， the global animal variable gets assigned to CAl。

 then call this function and once inside it， assign elephant to the local animal。

Then declare the inner function E and proceed by printing before calling functions animal where the value of animal will be the local value which is elephant。

Once you are inside the inner function E， you use the nonlocal keyword to declare that you are going to use the animal variable and you change the value to giraffe and here you can see that the print statement will give inside nested function。

 the value is giraffe which stays consistent even after you get out of the inner function。

So when you print after nested function， the value still remains giraffe。

Once the function is fully executed， come out to see that the value of global animal will be camel。

 which you had assigned at the beginning。So you can see the changes that you have made inside are not going to affect the value of the global variable let's look at one last thing if you comment the local variable out。

 this will throw an error。You can see there is no binding present of a non local animal present inside the D function。

 which was required here。

![](img/2d9ad7995fe99753cf448c7f1a04cd69_3.png)
# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P45：44_父类与子类.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

When instantiating objects from a class， you may find that the class is missing some properties that you use frequently。

In that case， you could decide to make a new class that replicates the first one。

 but also adds a few more properties。It would be cumbersome to rise everything from scratch。

 but thanks to inheritance you don't have to。😡，By the end of this video。

 you'll become familiar with inheritance in terms of child classes being derived from a parent class。

Inheritance is a core concept in object oriented programming generally and in particular in Python。

 and it's a major part of code reusability。You may know that everything in Python is an object。

 but let's explore that idea more closely。😊，It specifically means that every class in Python inherits from a built in based class called objects。

 which is found in built in dot objects。 In other words。

 a class declaration such as some class with empty parentheses implies some class with object as its argument。

When speaking of class derivation， the originating class is known as the parentent class。

 superclass or base class， the class which inherits from it is the child class。

 subclass or derived class。Any name parenting is acceptable。

 but the important thing to know is that the child class extends the attributes and behaviors of its parent class This allows you to do two things you can add new properties to the child class and you can modify inherited properties in the child class without affecting the parent。

So now let's explore an example of how this is done in Python。

 here you have a parent class P which holds the variable A with a value of7。😡。

Then there is the empty child class C in which Class P is passed as an argument。😡，And finally。

 a lower case C represents an instance of child class capital C If you write a print statement for C。

 A and run the code， the output is7。So even though C itself is empty。

 it still holds the attribute inherited from P。😊，Keep in mind that any changes in the parent class will also affect any child classes。



![](img/18248f400f73d152280b91cb42f7250e_1.png)

Now that you have an idea of how inheritance works。

 let's explore an example that demonstrates the flexibility it provides。

I begin by creating a new file called employment。 pi and my first step is to create a parent class called employees where I'll define two variables for first and last names。

 I do this by typing class employees， colon and on a new lineDe double underscore in it to trigger and select the init method suggestion。

For the first variable， I type self dot name equals name on a new line and for the second I advanced another line and type self dot last equals last。

I then add name and last to the init argument online line2 after the word self。Next。

 I'll create two child classes that both extends the employee class。

The first one I create is supervisors and to call the employees class， I type class， supervisors。

 open parenthesis， employees， close parenthesis， and a colon。

I then need to modify the in its method of the supervisor's class so that I can add another variable named password。

😊，Again， I trigger and select the init method， but this time it already includes the name and last variables。

😊，By calling the employees class， the super method has automatically been applied to access the variables there and initialize them within the supervisor's class。

 I proceed with adding the third variable password inside of the init method I then make it an instant variable with the line self dot password equals password Now I'll write another child class called Ches。

Again， I extend the employees class by adding employees as a method inside this class。

I want this one to contain a new function called leave Re。

 so I typeDeaf leave requestquest and then self in days as the variables in parentheses。

The purpose of the leave request function is to return a alive that specifies the number of days requested。

To write this I type returnturn the string， may I take a Le for plus STR， open parenthsesis。

 the word days， close parenthsesis， plus another string days now that I have all the classes in place I'll create a few instances from these classes。

 one for a supervisor and two others for chefs。First， I type Adrian equals supervisors。

 followed by the values Adrian and A in parentheses。

I can then copy and paste this instance two more times to serve as a template for the chef's instances。

😊，The first chef is Emily and will hold the values Emily and E。

 while the second Che Juno has the values Juno and J finally as an instance of the supervisor's class。

 Adrian needs another value for the password variable so I'll assign Apple here。😊，Next。

 let's call the instance method over Emily and pass a value to it。

She wants to request three days off， so I type printemily。lea request and the number three。

I'm also going to add another print statement that will check the value of the incidence variable over the supervisor Adrian。

 I type printadrian dot password。😊，The third print statement prints the value of Emily's name variable。

Now I run the code and get the following outputs， the words。

 may I take leave for three days from the first print statement。

 the wordapp from the second one and the word Emily from the third print statement。

Note that both the instance variables and methods inside the individual inherited classes are present along with the variables from the parent class。

😊。

![](img/18248f400f73d152280b91cb42f7250e_3.png)

In this video， you've learned how inheritance in Python helps to make code reusable， organized。

 and less redundant。
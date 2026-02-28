# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P45：11_模块3 1 2 类的支持（上）.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 3， object orientation and Go， topic 1。2 support for classes。



![](img/d59eb0b96ec8792b6e2841bceeadc8b4_1.png)

So there's no class keyword in go。 So go doesn't officially have anything called classes。

 although it has something that's just like em， but doesn't have a class。

So other objects orient to language objects to language， they have this class keyword。

 and then the data fields and the methods that are associated with the class。

 they're defined inside the block defined by the class Okay so the code that I'm showing here is not go the code is Python yet looked like Python that I wrote and this is to make a point class in Python just as an example。

😊，So in this case， you got you say class point and then everything in that block is associated with the point class。

 Now I'm defining a function called in it， which is its constructor and you'll notice inside there it defines self do x equals self y equals so selft x self y those are the data that are associated with the point and we're assigning them it' initialization function so it's assigning them to values x and y values。

But this is normally how it's done in other object oriented languages。

 Go does not do it in the same way， it doesn't have a class keyword like this。

 but you can get similar effect。Okay， so and go。They have a different way of associating methods with data。

 So remember that's what a class really is a class。

 It's a bunch of data associated with a bunch of methods that operate on the data。

 And together the methods and data make what what you would consider to be a class。

 So you need to have a way to associate a method with with some data。And the way that's done。

Inside inside go is using a receiver type。 So when you define the function。

 you give it what's called a receiver type， which is the type that that method is associated with。

 So the data is going to be some type and the method。

 the way you associate the method with that data is you define when you define that function you give it a receiver type and that receiver type is the type that that method is associated with。



![](img/d59eb0b96ec8792b6e2841bceeadc8b4_3.png)

And then when you want to call the method， you use standard dot notation to call it。

 So let's show an example。 So let's say I make up a new type called my int。 and it's just an int。

 okay so type my int int。But it's my aunt。 so I can make up methods for my for this type。 by the way。

 I can't add methods associated methods with existing types actually as a rule。

You can't whenever you associate a method with a type like this using a receiver type。

 associated with a receiver type， you got to make sure that the type is defined in the same package as the method that you're associating with。

 They have to be in the same package。 And so you can't do that with built in type like in or string or something like that。

 and you can't just add methods onto that because they not they're built in。

 they're not defined the same package as your code。So I make myantt now I make a function。

 this function double， and I want to associate double with the myantt type。

 so double is going to be something that it's going to double an integer and it only works on my ant。

😡，So when I define the function， notice it is slightly different than a normal function definition before the name of the function double to the left of that highlighted in red。

 I have。The receiver type defined find。 So myant is the receiver type。

 and Mi is the variable that refers to the particular receiver receiver object that this double is going to be called on because remember when I call double when I invoke double。

 I'm going to say I'm going to have to say， you know say I have an actually let's look this look at the invocation down here if you look at the bottom Func main I declare a myant to V V equal call an equal Mayant 3。

 So I make it and that's what V is then when I call see highlighted in red， when I call double。

 I say V dot double。And so what happens is when it's trying to figure out this double。

 it looks back at the things of the left of the dot。

 The object to the left of the dot looks what type it is， and it knows， oh。

 that's the double that I want。 The double is associated with that type。

So so that's what the dot notation is for。 Basically the thing the objects to the left of the dot tells you what type you're looking for。

 what type so the double because double could be defined in lots of different types。

 but I'm specifically looking for double for Vs type， which is a Mayant。

So anyway back to the definition of the double function from myant， the double method。

 I have to associate it with the Mayan type by putting the MI Mayant in parentheses。

 the highlighted red part before the name of the function when I define the function。

 when I declare the function。😡，So， and then what happens is inside the definition。

 so if we look inside double， it just returns into MI times 2。😡，Now， notice that。

It takesMI now is it refers to MI because basically what's happening is that MI。

 that object to the left of the dot， when you make the call。

 that object ends up being an argument an implicit argument to double。

 we'll talk about that in a second。But it takes so this function just takes MI。

 whatever integer it is， multiplies it times 2， turns it to an integer， and returns it as an integer。

And so then in the main， I can just call v do double and it calls the double that is associated with the type of V。

 which is my ant。So what I'm showing here is just that this type Mayant is the receiver type for this function double that I have defined。

 So whenever I call double I have to prefix it with this using this dot notation。

 I prefix it with an object of that type of the Mayan type。

 so V dot double so that the machine knows， okay this is the double that I want。

 the one that's associated where Mayant is the receiver type。And implicit method argument。

 So what I'm saying here is that。Even though it looks like double takes no arguments。

 If I look at the definition of double is no arguments there。

 But there is an implicit argument whenever you have a receiver type， whenever there's a method。

 it has a receiver type。 the object of that receiver type that is to the left of the dot。

 that is an implicit argument to the function to the method rather。

 So even though double it's like it has no argument。 It really has one argument。 I hit an argument。

 You do not pass it explicitly。 So when I call double， I say v dot double in parenthees。

 I have nothing， right， But that V is going to be passed to the double function when you actually make the call。

 So it's passed automatically invisibly。 you the programmer doesn't have to see it。

 But it's important that you as a programmer are aware that it is actually being passed。

Reason why is because it's past call by value。 So this is how passing argument passing is done and go iss called by value。

 So what happens is。When that V， that object to the left of that dot。

 gets passed to double implicitly， it is passed by value。 A copy of V is made and passed to double。

 So this impacts how， how what double can do。 So it's important to realize that V is actually being passed。

 the object to the left of the dot is being passed as an argument。

 even though it doesn't look like it in an obvious way。Thank you。


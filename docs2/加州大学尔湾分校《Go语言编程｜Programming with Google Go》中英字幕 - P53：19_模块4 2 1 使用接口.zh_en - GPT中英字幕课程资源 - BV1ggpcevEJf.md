# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P53：19_模块4 2 1 使用接口.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 4 interfaces for abstraction， topic 2。1 using interfaces。



![](img/357382e87697b0159cdc410b71f48d8d_1.png)

So interfaces we've talked about them and one thing we want to talk about now is a little bit of how to use them。

 So what do they use for language wise in the language why would you need an interface， you know。

 and I already said interfaces， they express some sort of a conceptual similarity between different types。

 So if you the idea is that if you if two types satisfy an interface。

 then they must be similar in some way that is important to the application。😡，So。😊。

One common or practical thing that you would use an interface for is when you need a function。

 you want to write a function which takes multiple types as a parameter。

 So specifically normally a function， it takes say it takes an integer has this argument。

 right it can only take an integer。 But what if you want to take an integer or a float。

 something like this， maybe a integer or a float or a string。

 It wanted to take multiple types and different types。 it'll do different things。

 but you wanted to be able to take different types。You can use an interface for that。

So giving an example， say I've got a function fo。And it's got to take a parameter。And this parameter。

 it could be either type X or type Y。 And I'm talking very generically now I'll give you a concrete example in next slide。

 But so I got this fo， It's going to take a parameter， which is type X or type Y。

 I want to take either type。 So the way I can do that is I can define an interface called Z。

And x's parameter be it can be an interface type Z。

Then I define x and y to satisfy Z so x and y are both satisfying the interface Z。

 then since it can take anything that satisfies the interface Z。

 it can take x and y as its arguments。So this is， this is a common way to use an interface and to basically an interface in in this way。

 it sort of generalizes， right， it says。It hides the details of the differences between the types。

 it's like， look these two types are similar in the way that's important to me and so that your function can just take the interface。

 it means it takes anything that is similar in that way。So to be a little bit more specific。

 I made up a problem about a pool in a yard， right so I have a backyard and I want to put a pool in my yard。

But the pool， before I can put the pool in the yard。

 it needs to fit in my yard and it needs to be fenced because。

 you know I don't want my kids to fall into the pool， so I need fencing around the pool。

 and it needs to fit in the yard。 So to fit in the yard。

 the total area of this pool needs to be limited less than the area of my backyard。Also to fence it。

 I only have so much fence because fence costs money， I only have a limited amount of fence。

 so the perimeter of this thing has to be limited to to within some limit。

 know depending on how much I can afford。So I need to determine if a particular pool shape satisfies these criteria because I'm trying to go through a bunch of different pool shapes and I want to pick one that satisfies these criteria that's sort of small enough that it can fit in the yard and also the peri is small enough that I can afford to fence it。

So I'm going to write this function called fit in yard， and this is going to return a boolean。

 So it takes a shape as an argument， some shape， like maybe I got some triangular shape。

 I pass that to fit in yard and it returns true。 if the shape satises the criteria， criteria。

 So if the area is small enough and the prim is small enough， then it says true。

If I pass it a shape like rectangle， and it's a big rectangle。 And know it doesn't fit in my yard。

 then it'll return false。 so that's what fit in yard is。

 Now thing about fit in yard is it's got to take a shape as an argument。

 but I want to take any shape as an argument。 I don't care if it's a triangle， circle， square。

 rectangle， whatever。 It could be any shape。 I should take it as an argument。

 but I have to be able to compute the area and compute the peri。

 So not any shape it's got to be a shape whose area and peri I can compute。

 So my fit that's the should take rectangles， triangles， whatever。

 but but a valid shape has to have an area method and a peri method。 So if the shape。

 if I can't compute the area， then I I won't be able to tell if it's enough it fits in my yard。

 say it's a sphere or something There's no area，'s a 3D shape。 that's a 3D object。

 I can't compute area of a thing like that So that is not a valid shape that I want to try to fit in my yard。

So any shape that has area and perimeter， that's okay with me。

So what I can do is I can define this interface for shapes that have the area perimeter。

 so I make my shape 2D interface。 we already talked about this。

 but I make my shape 2D interface it specifies area and perimeter， which return flows 64。

Then I can make my types， a triangle type， rectangle type， whatever types I want。

And as long as these types， I don't care how they define what data is inside them。

 as long as they have methods that use them as receiver types that it has area method and perimeter method。

 So triangle， you got area that has triangles a perimeter as a receiver method， also perimeter。

 same thing for rectangle， it's got an area and a perimeter。

 as long as they have area and parametermeter， I should be able to take this as an argument。

 So they satisfy this interface shape 2 D。 So in my fit and yard implementation。

I you can see that the argument that it takes is called S and its type is the interface type。

 shape 2D。So what that means is that its argument can be any type that satisfies that shape 2 D interface like rectangle。

 triangle， whatever the types are。 And it returns a boolean。 And all the function does very simple。

 just as if S dot area is less than 100， say 100 is the。Size of my， my， my backyard， right。

 And as that perimeter is less than 100cause that's all the fence I can afford。

 then return true else return false。So and any valid argument。

 a valid argument to this is anything any type that satisfies the shape 2D interface。Now。

 the empty interface is that standard interface is predefined， and it just specifies no methods。

 So what that means is that there any type， any type can actually satisfy that interface。

 And what you use it for is when you want to have a function。 a function argument be any type。

 you don't want to restrict it at all。 in terms of the type that this function can accept。

 Then you just give its type， make us type the empty interface。 So as example， we got this function。

 print me。 and its vow argument is called is is the empty interface。

 that's how you specify the empty interface that I haven't read。

 So that means that Val can just be any type。 And all this does is just print it。

 So it will print any type you give it。 You give an int float string。

 whatever Itll just print that to the screen。

![](img/357382e87697b0159cdc410b71f48d8d_3.png)

Thank you。
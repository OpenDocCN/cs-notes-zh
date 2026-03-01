# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p22 22_02_06_七步法实战：代码翻译.zh_en -BV18U411U729_p22-

![](img/517d73439b50a29cbcf901ad9e8d3b35_0.png)

All right。 Now you've developed the algorithm to find the perimeter of a shape。

 and we want to turn it into Java code。 You've seen a lot of Java code as we've talked about the syntax and semantics。

 And so what we're going to do is step by step go through and take the algorithm that we wrote and turn it into code that has semantics that match what we wanted our algorithm to do。

So here I have a class called Permeter runner， it's going to have the method get parametermeter which takes a shape and returns a double。

 it's got some other code in here so it has a main that we can run which will make an instance of this class and call test parametermeter。

 which will use file resource to read from a file and create a shape and call the parametermeter and then print that out。

We're going to go through and translate this to code。

 And I've written our algorithm here as comments， which are things for people that the compiler will ignore。

 So the first thing we say is start with total perm equals 0。 So this sounds like we need a variable。

 We called it total perm。 We're going to set it equal to 0。We need to think about what type we want。

 since we said it equals 0， we might want an int。 But if we think a little more more carefully。

 we might realize we want to double since we're working with floating point numbers that might have fractions。

 So double。Total per m equals zero。 and if we'd written this as int。

 we hopefully would find that out in testing when we come up with answers that should have fractions and we don't have them。

Then we say start with previous point equals the last point。

 so we need another variable previous point， What type of variable is this。

 Well this is going to be a point。And it's going to be the last point we meant in as even though we didn't write that down。

 so we'll call get last point。 How do I know that was there。

 I looked at the documentation for shape before I started doing this video and saw that it has a get last point method。

Then we say for each point， which we wanted to call car point in the shape。

 so this sounds like a for each loop。Each point curve point in the shape do get points。

 which is going to give us all of the points。 We want to do these steps。

 and I'm going to go ahead and put them in curly braces。

We want to find the distance from previous point。To the current point， and name it。Cur distance。

So anytime we want to name a quantity， we want a variable。

And so that's going to be the distance from pre point。To her point。

Then we're going to update total per to be total perm。Plus， current distance。

And then we're going to update previous point。To be current point。



![](img/517d73439b50a29cbcf901ad9e8d3b35_2.png)

Last， we said， total perm is my answer。 Whenever we know our answer， we're going to return that。

Because that's how we give our answer back to whoever called us。 So now that I've written this code。

 I'm going to come up here and I'm going to click compile。

 and it says cannot finds a symbol variable shape。 It's because my shape was called S。

And now it says class compiled with no syntax errors。

 So now I'm going to shrink this window down a little bit smaller。I'm gonna come over here。

 and I'm going to do main。 even though that's how we run programs outside of blue Jay。

 If we've written a main， we can do that， we're going to give it no argument。

 So I'm just gonna click O。 and it's going to ask me。What input file has the points for this shape。

 So each of these files has。嗯。Some points， so for example， example1 has negative 1，3， negative1。

 negative 1，4 negative 1，1，3， which is what we used when we developed our algorithm。

 So that's a good first check。 Make sure we get the answer we expected。And that gives us 16。

 which you may recall is what we came up with when we worked this example ourselves。Of course。

 using that might be bad because if we made a mistake。

 we wouldn't necessarily catch it since we've already used those values in developing this。

 so we might want another one。And so， this says that。



![](img/517d73439b50a29cbcf901ad9e8d3b35_4.png)

This other shape with points of negative 34， negative 3 negative 4 and 3 negative 4 has a perimeter of 24 if you work that out yourself。

 you'll find that that's the right answer and so we become more and more confident that this code that we just wrote is correct。



![](img/517d73439b50a29cbcf901ad9e8d3b35_6.png)

So that's how you turn your algorithm into code， you go through step by step， take each step。

 write down the code that corresponds to what you wrote。


# CppCon【中英⚡CppCon 2024】 p11 P12 Back to Basics： Lifetime Management in Cpp - Phil Nash - CppCon 2024 -BV1NHEEzdE92_p11-

A lot of interesting stuff happens in the hallway。 It happens。 you know， you get to walk out of。



![](img/303780061141744569c03ed7800007b8_1.png)

Of a session and there's a collective experience that you just went through and so there will be a hallway conversation that springs up discussing the material。



![](img/303780061141744569c03ed7800007b8_3.png)

![](img/303780061141744569c03ed7800007b8_4.png)

Welcome to Life management。

![](img/303780061141744569c03ed7800007b8_6.png)

In C+ plus， you are on the back to basics track。If you are an expert in lifetime management。

 you're welcome to stay， but please no heckling。

![](img/303780061141744569c03ed7800007b8_8.png)

This is gonna be a tricky enough subject to cover at a back to basics level as it is。

 So you may to bear bear with us。At some points。It's yeah， a bit of a contradiction in terms。

 lifetime management is。One of the more complex areas of C plus plus。

 but it is also something that we should all be fairly familiar with and able to understand what's going on。

Fortunately， we are going to look at some things that are going to make it simpler。

 we'll come on that。 But I dot want to emphasize this warning。6 plus pass is a complex language。

For many reasons。Most of it， historical。But also， a big， focus on efficiency performance。

 and they're mixed with。A bit of history as well。 really gives us a recipe for， for complexity。

 And this is one of those areas that that really shines through。So。C plus bus is complex。But。

One of the things that's going to help us to simplify this。Is understanding that by default。

 C plus pass is value based。It's like a value first language。 It supports other modes as well。

 And that's where the complexity starts to come in。

But if we can embrace the value based nature of C plus plus， it's really going to help。

Because values are simple。 And let's just look at an integer。We know how to use integers。

 We can just。Iitialize it with a value。We can， we can assign it a new value if it's not constant。And。

If it's in some scope， we know that at the end of that scope， it's gone away。

It didn't have any memory to manage。But you can no longer access it。Simple。

 nice and easy to reason about。That's what we want。But even looking at integers。We can see there's。

 there's a few phases that they go through。We've got the construction phase。

We're giving it an initial value。We've potentially got an assignment phase where we may assign it to a new value。

And that point where it goes out of scope。Okay， there's no actual de structures running。

But there is a destruction phase there。 it's no longer accessible。

 And if anything else was referring to it， say by point or a reference， that's。

 that's a problem at that point because it's gone。So those things apply to interviews。Obviously。

 we could do the same thing with some an extra string。

St string models of antype in the same way that that in intos。So we go through those same phases。

 We can construct strings。We， with initial values， we can assign them new values。And， of course。

 at the end of their scopes。The goscope they' no longer accessible。

But now there is actually a deor that runs and does some work。One more。Vecta。Same thing。 Same phases。

Everything is nicely managed。 It presents itself as a value type。

You can reason about it as a value type。Even though under the hood。

 there's actually more complex stuff going on。So these are our models to follow。Ideally。

And none of this should be surprising so far。 I hope， even if you're an absolute beginner。

 this is probably all very familiar。And that's the point。

We want these things to be non surprisingurpri。So how many people know this book。

Effective C plus plus。 So a good number， but not everyone is bit bit of an older book Now。

 C plus plus 98 era。Buts still lot of wisdom in this in this book and the the follow up book。

And one of the things I remember for this book is。This phrase。Do is the insster。

You might remember this。So we we just talked about how ins work。

How vectors and strings are modeled the same way。And this is really good advice。

 I'm here talking more about operator overloading there。

 but also in the context of lifetime management。It's so important to Scott Mayers。

 the author that in the second book， More effective C plus plus， he repeated this phrase。

And when he did so， there's a few other quotes that I want to pull up。

 because I think it's really worthwhile。Reflecting on these。First of all。

 the are the principle of least astonishment。We know how ints work。

 And so we know how strings work and vectors work to a large degree。

We're not surprised by how they manage themselves。But also。

 recognizing that anything somebody can do， they will do。 So they'll throw exceptions。

 They'll assign objects to themselves。 They'll use objects before giving them values。

We've all seen this， I'm sure。But。We need to be able to work with these things。

All three things that you mentioned there are going to come up a bit later as it happens。

And final quote this， like， there's only about three paragraphs that I'm pulling these quotes from。

 It's actually quite dense。So， as a result。Make your classes easy to use correctly。

And hard to use incorrectly。Really good advice。 But to really follow through on that advice。

We need to really understand how lifetimes work and how to manage them。 You C， plus。

 plus with the tools available。So， we're up to。Ints， strings， vectors， robot pointers。

 They follow the same pattern， pointers。Are also value types。

There's nothing about a pointer itself that inherently implies ownership。

 That's something we put on top of it。The point is themselves， they're just an address。

 just a number。Now Val times。And making sure we remember that is also going to help us because pointers are one of the。

 one of the things that makes this is quite tricky。So， the three phases construction。

Assignment destruction。 that's fairly easy It's's holding your head。

gets a little bit more messy from here。There's 8 different ways that we can deal with these。

They break down a little bit。 So construction， well， we've got the default constructor。

Easy to understand。 Custom construct is just when you're passing。Arguments then that you want to。

Used to initialize member variables， that sort of thing。So just whatever you write there。

Can consider a default construct a special case for that。

And then we've got this sort of split between copy constructor and move constructor。

And we've got the copy assignment operator and the move assignment operator。

You've got this extra dimension here。 Copy and move。And then finally， just， just one distractor。

Nice and simple again。So all of these， except for the custom constructor。

Are what we call special member functions。They have special properties。

Mostly that the compiler will generally write them for you you， if you give it space to do so。

And this is the good thing。This this something we want to happen？

But we need to understand how it happens and what it does when it。When he does do that。

So in the ideal case， we shouldn't have to implement any of these。

And that's when we we get the gold standard。And when we don't。

 we're gonna need to know how to implement them ourselves， so。This is where that warning comes in。

 This is where it starts to get complex， but。D bear in mind that when we get over this hump。

 there's gonna to be a nice， easy run the other side。 So something to look forward to。

So let's go down the rugbbby hole。Let go back to our gadget type I introduced earlier with the pointer。

So。Simpt possible class is an empty class， of course。We can instantiate one of those。

As a value type on the stack。Does't do anything， but it works， and it's easy to reason about。

But not useful。 So let's give it a。Thank， member。An integer。Again， we know how ins work， so。

We also know now how our gadget type works， because it effectively inherits what it can do from the integer。

 What do I mean by that。不。Let's ask the gadget。What the value of its integer is and try to print it out to。

A stream。So think for a moment what this is actually gonna do。AndYou're probably right。That， yes。

 it is undefined behavior because we haven't initialized integer。 We know how winds works。

If we don't give them an initial value， they just take garbage from， from memory。

 But then the class doesn't change that automatically。

The compiler has written a constructor for us here， a default constructor。

And it's effectively called the defaultpot constructor of an int。Doesn't have one。

 So that's why it's it's effectively a no up。So， oh， I should say。

 just to save a little bit of clatutter。 First of all，m making all of these things public。

So I don't have to write。

![](img/303780061141744569c03ed7800007b8_10.png)
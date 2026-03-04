# CppCon【中英⚡CppCon 2024】 p34 P36 Numerical Integrators From Scratch in C++ - Vincent Reverdy - CppCon 2024 -BV1NHEEzdE92_p34-

🎼The benefit of me being here with a person is seeing all of those names that you've heard of or seen on YouTube and you get to see them in real。

 you get to interact with them， you get to ask them questions。

 you get to understand that of really nice people。😊。



![](img/bf90330d502982bec81f692175f112ff_1.png)

![](img/bf90330d502982bec81f692175f112ff_2.png)

![](img/bf90330d502982bec81f692175f112ff_3.png)

So hello everyone。 I'm Vcent。 I'm very happy to be here at TPCon。😊。



![](img/bf90330d502982bec81f692175f112ff_5.png)

And today， we talk about high performance molecular integration in the age of plus 26。

So at least that was my original intention to talk about high performance numerical integration in the N of C plus plus 26。

But last year， I gave a talk about how to achieve， how to build symbolic systems。

 symbolic equations in in Cpl+。 And this was a lot focused on numerical numerical high。

 high performance computing。And why preparing that， that token and hyper numerical integration。

 I will like that because it's in C+us+ compared to our language that many language have like libraries that are ready to use and users can just like bring the library and doing numerical integration。

 C+ we done to have to。Inclement everything from scratch。

 So I started to delve into numerical integration。 And I realized that there was。

 I couldn't find the talk at CP PPcon and numerical integration。

 So most of the talk will be actually dedicated and。

 and the basis and the foundations of numerical integration。 And I hope that you will。

 you will learn some stuff。😊，So as I said， I'm Vincent Hovidi。

 I'm coming from France at La Boattoa and sit de particular。

 so I work with with physicist as a computer scientist。

 and I work at the interaction between physicists and computer scientists。

 and as you will see during this talk， there will be some physics and some computer science also so。

😊，So the first part of the talk will be focused on how to implement a very simple numerical integrator so that。

 you know in a few lines how to implement how it looks like it。

 it looks like when youre trying to implement such I thing。And then I will。

 I will go into the The foundation to try to see what kind of software architecture we can。

 we can do in Mad and C to try to tackle this problem。

And then I will outline an implementation and maybe some stuff and I will give some picture of what can be done in Cyepus26。

 but I would say I will compare to last year where I gave a lot of details of how to implement things。

 This year， I didn't want to go too much into details。So first， I will start with an introduction。

So we'll start with an example。 So the coding style may not be the best。

 but the goal is to try to understand what what's going on。

So the goal is to guess what this program is doing。So first。

 we have some pro importing some C plus plus headers。

 and then we have the main function that declares some constants and some type。 Well， it should be。

 yeah， and some values。Then it declares some parameters。

 and it it is getting some default parameters。Or it will first see if there is an argument given as an input of main and if there is not。

 it will take a default value。Then it will call a function compute。

 and that will return some structural evolution。 And then end。

 it will output the last element of evolution divided by 1 billion。

And if we look at what computer is doing。 So compute has a bunch of parameters as input。

So it will first declare two variables， it will initialize them。

Then it will initialize the vector that is called evolution and it will reserve some space。

And then it will declare a function that will be integrated。 So the function is this one。

 So you have the parameter a times other parameters and the square root of， of a combination of。

 of a。😊，With different powers。And then there will be a loop that will add things to the。

 to the vector and and like update the value of a and the value of T。And then at the end。

 when a will be less than epsilon Then it will return the vector evolution。And the question is。

 can anyone guess what the output will be on that program。Kind of a wild guess for like 13。

 some billion years。Yes。So it will return this number。And there is a problem with this number first。

 which is。There should be some units because a number like this。

 like you cannot really say anything about it。So quantity and un label would be very nice for these kind of things。

😊，So if we put the unit， then it， its 13。7839 billion years。

So what we just computed in a few lines of C+ is the edge of the universe。And as I said。

 so we computed the the edge of the universe in about 60 lines of surplusus。

So this will be the basic example that I will follow during the talk to try to understand what's going on。

So we'll， we'll dive into the little bit I into the details。 So， the。

 so it return the age of the universe， but also， it compute the evolution。

Meaning that you can trace back to the a to the to the big bang。

 the evolution of the sc factor the sc factor is typically you you you measure one meter now。

 And the question is， how， how will the matter evolve。

 I mean the matter of space time evolve in the past。

So at the big bang then it's zero and now we say it's by normalization， it's equal to 1。

 and this curve show that in 13。8 billion years how it evolved。And this。

 the thing we computed is basically the。The outer， outer shape of this， this diagram。

So this is what we computed。So if we come back to the core of computation。

So the function we integrated was the following one where we had the， So a is the scale parameter。

So we have scale times， some constant times to and multiplied by roots with some powers of a。

And then， as I said， the integration is just this one。And what it does。 So it， it。

 it computes a by taking the previous value of a and going back in time by doing a minus small parameter H times the derivative that is computed by the function just before。

😊，And what it does， it's the most basic numerical integrator you can have。 It's a method。

 which is just this， the formula showed here。 If you have some function。

 the next step will be equal to the previous step。Plus， this parameter h times the timer function。

 which is will compute the derivative of everything。 So basically。

 the numerical solution will take steps and ex integrate the the function。In our case。

 integrate the evolution of the universe back in time。

So the equation we are integrating comes from a simplification of general relativity。

 so if you take Enstein's equation， which is the leftmost one of the square。

 it equals the metric of the space time to some matter or energy content。😊。

And when you say that the universe is isottroic and homogeneous。

 then you can obtain a set of two equations， which are the freedman equations。

And then when you do some， when you say that the universe is filled with a perfect thread。

 then with a mix of perfect thread， then you can， you can have the inte， you， the。

 the function we integrated。😊，As an evolution with a mix of several components。 So as our components。

 we have radiation like photons and such， we have matter。 We have a curva parameter。

 which indicates how cur is the universe at large scale and then darking energy。



![](img/bf90330d502982bec81f692175f112ff_7.png)

And the equation we integrate symbolically is this one。 So as you see。

 the D AD T in C plus plus just correspond to this equation。

 And this is the first order ordinary differential equation。

Which are pre in physics because in physics， most equations are second order。

 but this one its one of the most simple I could find。And like。


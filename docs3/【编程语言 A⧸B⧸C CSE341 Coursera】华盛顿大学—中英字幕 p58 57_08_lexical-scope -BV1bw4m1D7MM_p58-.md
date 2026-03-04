# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p58 57_08_lexical-scope -BV1bw4m1D7MM_p58-

So it turns out that first class functions are a lot more powerful than we've seen so far。

 but before we can understand that， we need to take a step back and carefully reason about this idea called lexical scope。

 so we're going to start that here。So this is a very important concept。

 but it's not actually anything new， it's something we just need to focus on and reconsider now that we have higher functions。

 We know that a function body can use more than just its arguments and any local variables it defines it can use anything already in the environment。

 anything in scope。But the question is which scope。

 which environment and the answer in almost all programming languages these days is lexical scope that we use the environment where the function was defined。

 not the one where the function is being called。Alright。

 there are lots of good reasons for this semantics， which we'll get to in the next segment。

 We'll even later in the course， learn how to implement the semantics。

 which you will do on one of your later homework assignments。 But at this point。

 we just want to make sure we understand what the rule is and the way lexical scope works。

 This is one of the most important concepts in the course。

 because we need it to use first class functions properly and as powerfully as we can。



![](img/33f4fb6bf5f424e628e7c425fb803118_1.png)

So let's look at an example， and I'll do this with the code。 Allright。

 this example doesn't actually have higher order functions in it。

 but we can still see lexicalco being used。 So here after line 1。

 I have an environment where clearly X maps to one。



![](img/33f4fb6bf5f424e628e7c425fb803118_3.png)

So in the next line， when I add F to my environment， I'm not going to repeat X， I'll just add F here。

 F maps to a function that adds1 to its argument。And that is because whenever we call this function。

 we're going to evaluate this body X plus y in an environment that we had when the function was defined。

 And when we defined this function， we had an environment where X maps to1。

 So this function that F maps to， always adds one to its argument， no matter where it is called。

That is the rule。 So now let's see what happens here on line3， I shadow X。 So in this environment。

 x maps to2 that has no effect on F has no effect on the environment where F was defined。

Clearly here， we now have an environment where x still maps to 2 and y maps to 3。

So now we get to the all important call here。😡，We look up F in the environment。

 We get the function that adds one to its argument。 We look up x， We get 2。 We look up Y， We get 3。

 So we call。The function。Defined on。Line  two with5。

 because we looked up x and Y here in the environment at the call site。

But then when we make the call， we pass five， we add one to the argument。

 and so in the end Z maps to6， that's the essential part if you thought Z was going to map to seven。

 you're using a different rule which is not how ML works and not how most programming languages work。

Okay。So that is the key idea and the key example for this segment。 Now。

 let's go back to the slides here。 I've said the same thing we just talked about。

 The point is that on line 5， we evaluate x plus y in the current environment at line 5。

 which gives us a5。 But then when we call the function， we evaluate that function body。

 the x plus y on line 2 in the old environment where x maps to 1， extended with y， of course。

 mapping to 5， because that's how function arguments work。



![](img/33f4fb6bf5f424e628e7c425fb803118_5.png)

So this is why we need function closures， which we have not talked about before in our language。

 right because you might be thinking that seems a little magic to me。

 how can a function be evaluated in an old environment that isn't around anymore once we've shadowed X。

 how can that body of F use the old X。😡，And the fact of the matter is it's not magical because the language implementation。

 the ML interpreter and compiler and whatever else that implements ML。

 has to keep around those old environments so that we can implement lexicalco properly。

So the way to think about the semantics of functions in general is that we know functions are values。

 we can pass them around however we want， but a function value actually has two parts。 So far。

 we've only been talking about the code part， which is sort of obvious。

 you can't have a function without a body to that function。But a function value。

 this closure has a second part。 it has with it the environment that was current when the function was defined。

So we really have a pair。 It's not an M pair。 It's just something with two parts。

 And those parts are the code and the environment。 This thing is called a closure。

 And when you call a function， you're actually calling one of these pairs， one of these closures。

 And what you do is you evaluate the code using the environment。 So use both parts of the pair。

 and that's how a function call actually works。So in our example。

 we can now go back to it and see what actually happened， another way to reason about the semantics。

 which is that at line2 we created a closure。And that closure had a code part that said。

 give me an argument Y， and I'll evaluate the code X plus y。

 and it had an environment part that said， I will evaluate that code in an environment where x maps to1。

So then when we did the call on line5， we passed to that closure， the argument 5，2 plus3。

 and then the result of the call used the code in the closure and the environment in the closure with the one edition that Y maps to5 for the function argument。

 and that is once again why we got six back。All right， so that is lexical scope。

 and that's how closures implement lexical scope， and that's how you can think about the functions we're going to be passing around in ML。

So to give you a bit of an outline of where we're going from here。

 that is the rule of lexical scope now what I want to do in the next segment is continue with these sort of silly examples。

 but examples that use functions taking functions or functions returning functions because that shows that it's a pretty powerful feature it's a maybe a little harder to reason about so I want some more advanced silly examples then we'll get to the why why would you implement why would you want the semantics of your language to have this lexical scope will contrast it with the other possibility which is called dynamic scope and then we're going to talk a lot about programming idioms。

 how once you know that a language has lexical scope。

 there's a number of very powerful things you can do with first class functions that rely on the fact that we have lexical scope。



![](img/33f4fb6bf5f424e628e7c425fb803118_7.png)
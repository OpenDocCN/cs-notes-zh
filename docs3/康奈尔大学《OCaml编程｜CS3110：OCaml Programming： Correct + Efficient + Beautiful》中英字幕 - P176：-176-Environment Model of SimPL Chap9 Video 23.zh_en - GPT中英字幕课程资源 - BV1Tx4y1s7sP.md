# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P176：-176-Environment Model of SimPL Chap9 Video 23.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Substitution is a great mental model for the dynamic semantics of a language。

It's an easy way to think about computation。😡，Except for when we have to think about capture avoiding substitution。

 of course。But the substitution model is not a realistic model of machines。In a machine。

 code and data are usually kept separate。 We have a separate area of memory for storing code and a separate area of memory for storing data。

 classicalically anyway， these days， sometimes the two blur together a little bit。In a real machine。

 we don't edit the code to do a substitution at runtime for a variable。

 instead we keep the data in memory and look it up as needed。For example。

 with this little program here that binds X and Y and then uses them。 instead of doing substitution。

 what really happens at run time is there's some area in memory in which the value of X is stored。

 It might be a register。 It might be in main memory。

And then when we get into the interior scope here， that area of memory also will have y stored in it。

And then when we go to add X and Y together， we'll look up the values of those variables in the appropriate place in them。

These memories here are called dynamic environments。

 They map variable names to their current values in that scope。

This is opposed to a static environment which would math variable names to their types。

 we're going to come back to static environments much later for now we'll just stick with dynamic。

So the dynamic environment is really implementing a kind of lazy substitution。Eventually。

 the variable name could get substituted for its value， but we don't do it。

 And so we actually need to look up that value。So maybe you have a very large piece of code that binds x and then binds B and then binds X again and eventually uses them both。

Well， that's going to create a dynamic environment， a memory that binds x to 0。And later on。

 eventually there will be a dynamic environment that's binding B to some value and x potentially to some different value since it's been rebound。

All of the pieces of code here are going to look up those variable names， X in particular， as needed。

In the very first case of let x equals 0 and 42， notice we won't even have to look up x there ever because x is not used at that point。

So we've actually saved a little bit by not having to do that substitution actively。😡。

To model this kind of evaluation， we're going to introduce a new big step relation。

As opposed to the substitution model big step relation we had before， this is the environment model。

 big step relation。It looks pretty similar。 we've still got the big arrow。

 we've still got an expression E， and that's being evaluated to evaluate V。



![](img/395f59ef13f76abb6b800962ff6b6281_1.png)

But additionally， now， on the left hand side， we have an environment。

 That's that dynamic environment that maps variable names to their current values in the scope。



![](img/395f59ef13f76abb6b800962ff6b6281_3.png)

So this thing on the left of the arrow in the funny looking angle brackets is called a machine configuration。

 think of it as like the current state of the machine as the program is executing。And in fact。

 you can think of the first components of that as being like the memory， the environment。

 and the second component of it as being like the program that's the expression being evaluated。

Now I've chosen these funny looking angle brackets to emphasize the fact that even though this kind of works a little bit like a pair。

 it's not truly an ocal pair， this is not ocal syntax we're using here。

 this is a mathematical syntax we're using to define this relation。😡。

Environments we will treat abstractly as maps， so we already have a notation for that and I'm just going to use that abstract notation again。

 so curly braces will be the empty environment and then if I have X colon 42 and y colon red。

 that would be the environment that maps the variable name X to the value 42。

 the variable name Y to the value the string red。And I'm going to treat environments here as partial functions。

 if I have an environment， I'll just write parentheses X next to it to mean look up that variable x inside of the environment。

Of course， if you go to look up a variable that isn't bound in the environment that's unbound。

 so that's why it's a partial function。We can now give the dynamic semantics of a language using this big step environment model relation。

 We'll start with the language simple。So in simple， we have variables。

 we can just look up a variable in the environment。 This is the lazy substitution occurring。

 So whenever you go to evaluate a variable name， just look it up。😡。

Notice how this is different from the substitution model。😡，In the substitution model。

 we would have said at this point， this is an unbound variable。Here it might or might not be unbound。

 It's an unbound variable error if x is not actually mapped in the environment。😡。

But it's just the final result of doing that lazy substitution at long last if x is bound in the environment。



![](img/395f59ef13f76abb6b800962ff6b6281_5.png)

For let expressions， if we want to evaluate let x equal E1 in E2 in an environment N。Well， first。

 we will evaluate E1 in that same dynamic environment。😡，To evaluate V1。



![](img/395f59ef13f76abb6b800962ff6b6281_7.png)

Then instead of doing a substitution of V1 inside of E2， we will record what X should be。



![](img/395f59ef13f76abb6b800962ff6b6281_9.png)

So we'll take the environment end and we will bind x to V1 in it。

So I'm introducing a new notation here that means extending an environment to bind or perhaps rebind if a variable is already bound to a value。

So now we will evaluate E2 in that extended environment that records the lazy substitution of V1 for x。

That will get us a value V2。And the result of evaluating the entire lead expression will be V2。



![](img/395f59ef13f76abb6b800962ff6b6281_11.png)

Values simply evaluate to themselves， the same as they did with substitution model。

Binary operators work almost identically to the substitution model。

 we just have to add the machine configuration part around it。

 but there's no interesting use of it here， we just keep pushing the same environment down into evaluation of the sub expressionions。

😡，And the same is true for if expressions， we're really just pushing that dynamic environment down through the semantics。



![](img/395f59ef13f76abb6b800962ff6b6281_13.png)
# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P69：-069-Functors Chap5 Video 17.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

I said before that module values and regular values are distinct in OCML。

 you can't mix a match between them， and therefore you can't have functions on modules。

Although technically speaking that's true， there is something else that's a lot like a function that you can have。

 and that's called a functer。A funter really is just a module level function。

It's a kind of function that can take in a module as input and produce a module as output Like everything else that we've seen so far with the OCMl module system。

 it's syntactically a little different from the rest of the values in the language For a really simple example of functionss。

 Let's start off by writing a very small module type and module。



![](img/490020692a88e6b09ce80c8f7b2105af_1.png)

So I have a module named A now， and it has a value X inside of it。

That value is specified by module type capital X， and indeed I could seal a at that module type。

Suppose I want to create another module that's just like module A， except。😡，Its X is one bigger。

 So think of this as I want to write a function that takes in that module A and produces a new module just with a little change to it。

Here's how I can do that with a funter。

![](img/490020692a88e6b09ce80c8f7b2105af_3.png)

All right， let's pick apart the pieces of what I just wrote。

The module keyword at the beginning of this， remember， is how we start a module definition。

 It's how we create a module value， just like how the let keyword is how we create regular values and bind them to names。

The functer keyword here says I am creating a funter， I function as it were。

 from module values to module values， so it takes in a module value and produces a module value。😡。

The module value that it takes in is named M here locally。And it's specified to have module type X。

 we define x up here above we already know what that is。😡。

The module value that's returned by this feter is the structure here on the right hand side。

And that structure creates a value named x， and what does it bind that to whatever x was inside of the input function plus1。



![](img/490020692a88e6b09ce80c8f7b2105af_5.png)

So all I'm really doing here is the module level equivalent of something kind of like the increment function or the increment function you remember looks like this。

It takes in an argument X then returns x plus1。Here I'm taking in a module。😡。

With an identifier X inside of it， and returning another module， with identifier X inside of it。

 it's just in the output module， it's bound to a value that's one more than in the input module。

Let's give this a try in Utah。So notice how I can't just directly apply the efucter here in Utah。

 this is the same reason why I can't write say something like an anonymous structure right here。

I'm not allowed to just directly write module values at Utah's prompt。😡。

What I can do is use the module definition syntax to bind the result of that Fter application to a module name。

Now I have a module named B and inside of it the X is one more than the x that was inside of A。

 I've now got one instead of zero。And I could keep on doing this。

 I could create C that's one bigger still。So you see how I can apply this function as a function to other modules and get modules back as results。

Just as we learned for functions that there is a syntactic sugar with the keyword fun。

 there's also syntactic sugar with the keyword functer。

 although you can write funcctorters with this anonymous funter version as we did here。

 you can also write it with the module being on the left hand side of the equal。

So this exactly parallels how there are anonymous functions as well as syntactic sugar for them。

 there are anonymous functions and syntactic sugar for those。One difference， though。

Is that with funcctorters， you must always specify the module type of the input。

 You're not allowed to leave off the colon X。Not in either place here。

And that's for the sake of good type inference。The type inference engine in Ocaml does require that you specify the input type of the Fter。

Now， the input type for the funter， we know that we can pass in A because it has module type X。

Turns out we don't have to seal a at Ty X as long as that module can be given that module type。

 Ocama was happy to have us pass it in here。So notice now that even though I've left off the module type annotation in the definition of A。

 this code compiles perfectly fine。A just has to match that module type X。

 it doesn't have to be sealed at it。

![](img/490020692a88e6b09ce80c8f7b2105af_7.png)

The syntax for Fters really is just a straightforward extension。

 therefore of the syntax for module definitions， you just have to write the input modules and their types in one of two places either on the left hand side of the equals or on the right hand side with keyword funter。



![](img/490020692a88e6b09ce80c8f7b2105af_9.png)
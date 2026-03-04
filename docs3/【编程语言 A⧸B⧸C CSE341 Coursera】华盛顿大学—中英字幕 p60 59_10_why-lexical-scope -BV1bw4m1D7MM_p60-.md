# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p60 59_10_why-lexical-scope -BV1bw4m1D7MM_p60-

Okay， now in our study of lexical scope， we can get to the motivation of why this is the semantics you want。

So remember， lexicalcope is using the environment where a function is defined to look up variables in the function body。

The other natural thing you might think of does have a name It's called dynamic scope。

 If you have dynamic scope， use the environment where the function is called So decades ago these were considered reasonable options and in a programming language course you would study both and think about which one a language might have。

 I think it's fair to say that these days lexical scope is considered the one that makes sense。

 We'll talk a little bit at the end of this segment about things that do work with dynamic scope。

 it is occasionally useful， but lexical scope is really how programming languages work these days。

So there are reasons for this and these are precise technical reasons。

 sometimes in programming languages， things are just a matter of taste。

 but I'm about to show you things that lexical scope lets you do ways it lets you reason about code and dynamic scope simply does not。

 and that much is not a matter of opinion， the only opinion you might have is whether or not those reasons are good or important。

So let's just get started。I'll show you three main reasons。 The first two are actually related。

 The first one， I'll say that the meaning of a function does not depend on what variable names you use。

 This is nice because you can go in and change the names of your variable。

 say to make them more informative or to port them to a different human language or something。

 and you can know that it's not going to affect any of your calls。So， for example。

 look at this first function we see here。 We've seen a function like this before and suppose that you come along and you say。

 you know X isn't a very good name for that。 I want to call it Q or fo or pizza instead。

 You could change it here and you could change it here and you would know that no color can tell it's a local variable and the name of local variables should really never matter。

 It's good abstraction。 It's good modularity。 It's good software engineering。

 and it's only lexoco that gives us that。 Let me show you that with the code here。

 So here I have the function that we had on the slide。

 I've just called it F1 to distinguish it from F2 here。 and F2。 I've done the variable renaming。

 I suggested it's exactly like F1， except I've used Q for my local variable both in its definition and its use instead of X。

😊。

![](img/8cf374a1cc184537ee27e26ece174065_1.png)

And it turns out that no one will ever be able to tell if I call F1 was7 and get a function back。

 that function is going to add 15 to its argument to y plus1。 If I call F2 with 7。

 I will get back a function that adds 15 to its argument。

 All callers can tell that I get back a function that adds 15 to its argument。

 So both a1 and a2 will be 19。 it doesn't matter that there's an x and scope here。

 If we had dynamic scope， if we evaluated these function bodies， x plus y plus Z Q plus y plus Z。

 where we called these functions， instead of where they were defined， then under dynamic scope。

 one of these functions， would end up using this 17。

And the other one would actually end up with an undefined variable because we would try to use Q。

 and there would not be any Q here。 That's actually one of the other reasons we're going to get to。



![](img/8cf374a1cc184537ee27e26ece174065_3.png)

So that's our first reason is that functioning does not depend on the variable name used。

 I actually already showed you another example of this。

 which is the second example down here that it lets you remove unused variables in the previous segment I showed you an example where we had a function body that was let v x equal 3 or something like that in G called with 2。

This v x is irrelevant， so it would be fine to remove it。On the other hand， if we had dynamic scope。

 then if the call to F passed in some G that had in its function body X。

 we might end up using that X because here's the call site and under dynamic scope。

 which is not what ML has。 We would end up using the environment where the function was called。

 So you really need lexical scope to reason about these functions these way this way。

 And this is essential for modularity in software。 and modularity in software is one of the most important features you want from your programming language。

On reason2， somewhat similar， functions can be type checked in reason about where they're defined。

 not where they're used。So let's look at this example。 We can just look at it on the slide here。

 I look at this function F， which it's the same one I've been showing you。

 and we can reason about the fact that it returns to y plus1 and it's a function that when called returns to y plus1。

 excuse me， and it type is taken int and return an int arrow int。 So its type is int arrow。

 int arrow int。Once we know that it type checks， we know that if we call it with an int。

 that shouldn't lead to any problems and indeed， when we call it with seven here on the second to last line。

 we get back the function that will add 15 to its argument， and then when we call that with four。

 we get 19。What if we had dynamic scope？If we had dynamic scope， then down here at the bottom。

 when we end up calling this function， we go to evaluate x plus y plus Z。

 what we're going to get back。 we're going to look up X in our environment。

 We're going to get a string That's a really bad idea since you can't add strings in M。

 We're going to look up Y in the environment。 We're going to get an undefined variable。 Well， no。

 Y we might get or Z， because there is no y and Z here。 Those are undefined variables。

 So our whole purpose of type checking just got thrown out the window with dynamic scope because we end up using the wrong variables in the wrong places。

OkayOn our third and probably most exciting example， because it's gonna let us do new things。

 closuresures just got much more powerful because we can use this lexical scope idea to have them store whatever data they need。

 And this works particularly well with functions like map and filter that I've shown you before that iterate over data structures。

 So I have the same code over here。 Let me get to it here。 Alright。

 So we have seen the function filter before。 This is just a function that takes a function F and a list X's and returns a list that only contains the elements of X's for which F returns true。

😊。

![](img/8cf374a1cc184537ee27e26ece174065_5.png)

So suppose that I wanted to filter on all of the I wanted all the numbers that were greater than negative one。

 all the non negative numbers， here's the way I could implement that in these two lines using filter。

What I'm going to do is I'm going to define a little high order function here。

 It takes in a number x， and it returns a function that takes a y and returns true If y is greater than x。

 So greater than x has type in arrow into arrow int。😊。



![](img/8cf374a1cc184537ee27e26ece174065_7.png)

So down here， where I call greater than x with -1， I'll get back in into arrow int。

So if I call filter with the result of this call， that's essentially going to be a function that takes in a y and s is y greater than minus1。

Filter that over the list。I get a function that takes a list and returns all the non negative numbers in the list。

 zero or positive。So where are we using lexical scope here？

In the creation of this function that we pass the filter。Greater than x， when called with -1。

 returns a closure that captures stores in its environment that x is -1。

So when we pass this function into filter， we will be asking for each element of the list。

 is that element greater than minus1？It does not matter that up here in the body of filter。

 there's a different X。 if we had dynamic scope， would not this we'd ask is a number greater than itself。

 we would get false and we would filter everything out of our list。😡。

What's going on here in general is that filter just says， giveive me a function。😡，Any function F。

And it does not care about the fact that the closure passed in can have whatever data it needs in its environment。

 In this example， it's using this  -1 that was stored when we created the closure here。

Let me show you a second example using an anonymous function。 We also call filter。

 This is a function all greater than or all greater that takes in a list and a number and filters out all the numbers less than n。

 less than or equal to n。 So it only returns things strictly greater than n。😊，So I call filter。

 I call it with this little anonymous function and x's， and notice that when I pass in this function。

It's going to end up getting called in the body of filter between if and then。

But we look up variables in the body of that function， not where the function is called。

 but where the function is defined。 So when we look up this n。

 we will always get the n that was passed into all greater。 so this will work correctly。

 if you call greater with a list than 17， we will filter out anything that is 17 or less。

 and we need lexical scope to do that。系。Let's go back to the slides。

 we will see more examples of this after I show you some other high order functions。

 but this is really where we get a lot of the power of closures。And now let me ask the question。

 if dynamic scope is such a bad idea， why do we even have a name for it。

So people now do realize that lexo scope for variables is definitely the right default。

 It's a very common behavior across programming languages。

 It's important when designing a language to get this right。Now。

 dynamicy scope is occasionally convenient in some situations， and so some languages， for example。

 racket， which we'll use later in the course， have special ways to do it。

 You can add to your language， a special kind of variable separate from the regular variables that works with dynamic scope。

 Most languages don't bother， but it can be convenient。

 An example is trying to change through dynamic scoping where output is redirected to certain files and things。

 I'm not going to show an example here。The other thing I would like to point out is if you squint a little bit and think about it。

 exceptions， which we saw previously in the courserus act a little bit like dynamic scope。

 If you think about a handle expression And when you raise an exception。 What handler does it go to。

 It's not lexical。 you don't look at the structure of the code。

 it's not the closest handle expression where the raise was defined It's the closest handle on the call stack in the current dynamic nesting of calls and that is much more like dynamic scope。

 you look up the current handler is it did your caller want to handle this exception。

 did its caller want to and it's not based on where things were defined and lots of experience with exception handling just suggest that for exceptions。

 that's a better default， people find that more convenient and better styllistically when designing their software。

😊。

![](img/8cf374a1cc184537ee27e26ece174065_9.png)
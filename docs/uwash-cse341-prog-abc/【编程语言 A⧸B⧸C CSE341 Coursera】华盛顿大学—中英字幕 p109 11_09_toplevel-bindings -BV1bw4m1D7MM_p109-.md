# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p109 11_09_toplevel-bindings -BV1bw4m1D7MM_p109-

So now that we've discussed how local bindings work in the semantics of them。

 I just want to tell you the semantics of top levelvel bindings， the defines in a file。

 because it would be an omission not to go through that。

 So the short version is when you have a bunch of bindings in a file。

 they work like a letre or they work just like a local define。

 So you can have things refer to later bindings。 So like an M。

 the things are evaluated in order and you can refer to earlier bindings， but unlike M。

 you can also refer to later bindings。 Now because this evaluated in order issue。

 you should only refer to later bindings in function bodies and you should make sure that those functions do not get called until after the thing you're referring to has had its expression evaluated。



![](img/7664d62fb3f117af2c34fba779464f04_1.png)

Unlike inside of functions where you get an undefined result。

 you will actually get an error and racket， but that's a detail that we don't need to focus on。

 but you might be thinking， oh great， finally I can refer to later things， everything is better。Well。

 it turns out there's a couple disadvantages to the semantics。 One。

 as we've seen is you can get these errors if you refer to something too early。

 but the second is you cannot shadow inside of a file。 that wouldn't mean anything。

 if you have two bindings of the same variable in the same file this doesn't make any sense because we're trying to add them to the same environment and you'll get an error if you try to do that。

 So a quick example here， this is just silly code And this first line， I define a function F。

 And if you look in its body， it not just uses its argument。

 but it also uses some variable B that is actually introduced later in the file。

 This is okay because the body of F is not called until after we have the binding B initialize to three。

 In fact， in this file we don't call it at all， but once someone uses this module uses this file or clicks run B will be bound to3 and any call to F will work correctly。



![](img/7664d62fb3f117af2c34fba779464f04_3.png)

![](img/7664d62fb3f117af2c34fba779464f04_4.png)

Now you can go ahead and use an earlier binding， even not inside a function body。

 this works just like in ML or just like with let Re， we evaluate things in order。

 so by the time we get to this plus B4 B is already3， so C would be evaluated to7。

 there's no trouble。

![](img/7664d62fb3f117af2c34fba779464f04_6.png)

![](img/7664d62fb3f117af2c34fba779464f04_7.png)

You cannot do this to a later thing。 So this we emphasizing， if I uncomment this line。

 then trying to execute this line D will give an error。 I can just click run here。

 It says reference to an identifier before its definition。 That's exactly the mistake we made。

So and then on this last line to find F17， this would also be an error because you can't introduce two variables F in the same file like this。

 and you would get duplicate definition for identifier in F。



![](img/7664d62fb3f117af2c34fba779464f04_9.png)

![](img/7664d62fb3f117af2c34fba779464f04_10.png)

So that's the advantages and disadvantages of this let Re style semantics for the toplevel bindings。

 And that's really what you need to know from this segment。 Now。

 a couple other details just to finish up。 One is the repple doesn't quite work like letre。

 It doesn't quitework like let star。 In fact， it doesn't quite work properly at all。

 And I'm not going to go into the details of how the repple works because in normal uses。

 the repple will do what you want， just like we've been using a repel and M and now in racket。

 but it turns out there' are some things that don't work well。

 if you shadow something that's already been defined even in the standard library and you're defining a recursive function。

 things can go very wrong。 And so the easy work around is in the repple do not define your own recursive functions。

 It's fine to call recursive functions that have been defined by a file that you are running。

 don't define your own in the repple， go ahead and put them in a file and then we can avoid this issue。



![](img/7664d62fb3f117af2c34fba779464f04_12.png)

![](img/7664d62fb3f117af2c34fba779464f04_13.png)

And then one other optional thing。😡，ILater in the course。

 I'd like to at least optionally study rack's module system。

 and I'm being technically incorrect here。 inside a file and racket is not really toplel bindings。

 which is what I call this segment in racket every file is implicitly in its own module。

 Now that module still has let Re style semantics。 So all the code I showed you as correct。

 but it turns out that a cross file。 It's not one big letre。

 It's actually a separate letre for each file， and you can include things from another file。

 and you can shadow things from another file from another module。 So in fact。

 since plus is just a function， and it's just defined in some other module that's part of the standard library you can even shadow the plus function inside your own file。

 but each file can only define it once。 Of course that's sort of shadowing is poor style。

 but it helps explain rack's module system， which as I mentioned will be an optional topic later in the course。



![](img/7664d62fb3f117af2c34fba779464f04_15.png)
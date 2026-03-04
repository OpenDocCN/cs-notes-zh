# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P58：-058-Scope and Opening Chap5 Video 6.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

When we want to use many functions from the module， sometimes it can get a bit verbose。

Here I've created a stack by doing an empty stack which I've pushed 42 on and then peaked。

That caused me to have to write list stack three different times。That kind of repetition is no good。

There are various ways of getting rid of it。Here's one of them。😡。

I've written list stack dot and then parentheses。Inside those parentheses。

All of the names from List staff will be in scope。That means I don't have to repeatedly write list stack dot in front of each of them。

By the way， another nice way to write this code would be with the pipeline operator。

Can you see the pipeline there， I'm taking the empty stack。

 then pushing 42 onto it and then peaking another way of writing the same code is to use a local open。

This is a peculiar way to use the let expression syntax。

When you write let open and then a module name。It makes all the names from that module in scope inside the body of that expression。

So everything from List stack is in scope online 42。



![](img/c124618216f37385d6970a92c98a41c1_1.png)

This is useful when you have a long body of the lead expression。

And you want to open a module for all of the lines inside of it， rather than just a single line。

 which is what we did above with the parenthesis syntax。Finally。

 another way to write this code would be to do not a local open， but a more global kind of open。

So when I write open list stack here， henceforth in the rest of this file。

 all the definitions from list stack are in scope， so empty here means the empty inside of the list stack module。

The problem with this and the reason it's discouraged is that if you open two modules that happen to define the same names。

You're going to have one name shadow the other。In fact， at this point， if I wanted to use my stack。😡。

Up here from above。I'm in a little bit of trouble。Because empty here now is always going to mean lists stacks empty。

And if I opened my stack。Now， empty will mean。My stacks empty。

So I'm back in the same boat that I was before， before we introduced structures。

I have shadowing of names going on。For that reason。

 it's best to be very sparing in your use of this kind of global open inside of an Oaml file。

One of the few times we do that regularly is when we open O unitt at the top of testing files because we know that we want its definitions of the O unit operators and testing functions。

Inside of your own code base， you might be creating modules that you know that are safe to open。

 and that's fine too。But global opens of data structures， which all will typically define。

 map and fold and maybe empty in other similar names， is going to be problematic。



![](img/c124618216f37385d6970a92c98a41c1_3.png)
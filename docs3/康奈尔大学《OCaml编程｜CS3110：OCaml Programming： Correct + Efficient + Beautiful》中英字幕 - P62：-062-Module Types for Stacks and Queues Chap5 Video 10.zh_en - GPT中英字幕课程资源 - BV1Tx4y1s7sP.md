# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P62：-062-Module Types for Stacks and Queues Chap5 Video 10.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's write a signature to describe the stacks that we implemented before。

We'll start with listist stack。So I have created my signature for stacks now by specifying all the values。

 their names， their types and their behaviors with these documentation comments Now I can tell O Camel that I want to check that list stacks do have that signature。

And indeed， they do。Now what about My stacks though， which we implemented up here above before？

I'm going to grab that code and put it below。Could I say that my stack has type list stack SIig？

I get a compilation error when I do that。The values do not match empty is not included in empty。

 and notice the two types there， Alpha stack is not included in Al list。

What's going on here is that my stack signature required empty to have type alpha list。

And inside of list stack， that is exactly how it's implemented。But of course inside of my stack。

 I'm not actually using the list type to implement my stacks， I'm using something very similar。

 but it's not exactly the same thing， and so empty does not have type alpha list here。

 in fact it has type Alpha stack which is defined up here。

So the signature that I wrote for Stas was not general enough。

To describe related stack implementations， and only described that particular implementation with lists。

Let's generalize the signature。Now I have a signature for stacks that doesn't mention lists anywhere。

 it just mentions that there's a type alpha stack that is used to represent stacks。

List stack does meet that signature because it provides a type alphapha stack。

And my stack also meets that signature because it provides its own type alpha stack。

Let's also create a signature for cues。So it took me a while there to develop that specification as I was going along。

 I had to work out what I wanted to do with options and write down the behavior of each of those functions。

Now that I have my Q signature， I could move this code all the way up above the definitions in the file of two list Q and listist Q and specify that list Q and two list Q need to have that module type。

 but let me show you one other way of doing this I can also below here say module。List Q。Has type Q。

And is equal to list Q。Now that's a little confusing because I'm rebinding a name that has already been bound before I'm shadowing。

 so in order to get rid of that confusion。Let me go back up here and just change this name up here。

 This is the implementation of listist Q， let's say。And down here。

 I can say that's the implementation of L Q。So this is our first example of the right hand side of a module definition not being a structure。

 but just another module value so listist Q Iple is a module value that was defined up above in the file and I combined it to the name list Q and at the same time I'm binding it I can also specify a module type Of course I wouldn't have to do that I could leave that off。

Now I could do the same thing for my two list cues。Now， okay。

 Emma is satisfied that both of those modules have the correct module type。


# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P40：6_模块1 2 3 函数指南.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module1， functions and Orization， topic 2。3 function guidelines。



![](img/f6bc54ee5a8dd0bfc6bdb563d32234d4_1.png)

So another thing that you want to do with functions is you want them to be not too complicated。

 right， you want to be understandable。 they shouldn't be too complex。 Now。

 this term complex complexity， when you measure the complexity of a function。

 this is definitely arguable。 People have different opinions on what comprisisees complexity。

 what makes up the complexity of a function。So we'll start off with function length because that's sort of the most obvious。

 right， Everybody uses that。There's a very rough approximation of function complexity。

 so functions need to be simple。And one way to make them simple is make them short。

 Okay now this doesn't always work because short functions can be complicated。

 I have definitely seen that especially in like a C or something。

 You can put everything into one line， right， Yeah， yeah。

 I'm not counting lines that are you could technically write a whole go program in one line， right。

 assuminging you use regular line separations。 that's what I'm talking about when I'm talking about function length。

And， you know， you could rely on number of lines， line count。In fact。

 I remember like one professor here， he basically insists for and see that all of his students write their code。

 every function is no longer in 10 lines you know now I think that's too strict。

 you know sometimes you got to go over that but I see where he's going with the idea right it forces you to have some measure of simplicity in each individual function。

So。😊，The question then is sort of how do you write a complicated piece of code with these really simple functions。

 right， I mean， some code you write， it has to be complicated and there's no real avoiding it， right。

So what you can do is you when you define your functions。

 you can make sure that each individual function isn't too complex。

 you can make attempts to limit the complexity of an individual function。

And what's going to happen is in your code in general。

 there's always what I'm calling here a function call hierarchy。

 meaning you got a function and it calls some other functions。

 which calls some other functions and so on。 So that's I'll call that a hierarchy right this calls that which calls that and so on。

😊，So you can use that hierarchy to simplify the complexity of each individual function。

 so as an example， I got option1， option1， you write everything in one function。

 one big fat function，100 lines long， or I can go to option2。Now option2。

 I write now I have three functions instead1， I've divided into three。

 The first function in this case is really short， just a few lines。

 but it calls the other two and then the other two functions are each 50 lines law right。

This is an approximation of what you would do， but in option 1。

 you got one big complicated piece of code 100 lines long in option 2， you got three pieces of code。

 two of which are 50 lines long， but the complexity of each individual function if you're measuring in terms of lines of code is less in option 2 than an option 1。

 so presumably option 2 would be easier to debug。😡，Now。You know。

 this all depends on a bunch of other factors。 So， for instance。

 you don't want to take a piece of code that's 100 lines long and just chop it straight in half and say this is function top half function1 bottom has function2。

 you got to group the functions in a reasonable way。

 We already talked about this each function should map an operation that makes sense in in your application。

 So you can typically you can't just cut it in half。

 But you might be able to take this 100 line piece of code and say， well， the first 30 lines do this。

 and the next 70 lines do that and maybe chop it up like that。

 And even that's an improvement And then you can take the 70 line piece of code。

 7 lines function and chop that up and do a 30 chunk and a 40 line chunk and so on。

 So there's this decomposition and hierarchy that you're making implicitly when you define these functions。

 And the goal is part of the goal is to make sure that each individual function isn't too complex so you limit the complexity Now in this case。

 we're talking about complexity in terms of lines of code。

 But we'll talk about another form complexity next。😊，Control flow complexity。

 So another way to look at the complexity of a piece of code is to look at how much how complicated this control flow is。

 So when I say control flow， I'm talking about the paths from the top of the function to the bottom from the start to the end。

 the control flow paths。 So how many options there are。 So， for instance。

 if you had a piece of code that had no if statements， just straight line code。

 just a sequence of assignments， let's say assign sign assign sign assign sign assign sign a sign that has exactly one control flow path from top to bottom。

 there is one sequence of instructions that you will execute in that code。 So one control flow path。

 But if you put an if statement in there。 if this is true， you do one thing， if that's true。

 you do the other， if you put one if， then you got two paths。😊。

Now code gets more complicated than that you can have nestative statements。

 you can have loops which are implicitly conditional statements and things like this。

 so a typical function can have many different control paths。

 many different sequences of instructions that are executed when you execute that code。

 many different sequences that executed depending on the input parameters， right。😊，So。😊。

Here I got this function actually here I got this function fo。 and it's got two conditionals。

 actually one's nested within the other。 So if a is equal to one。

 then then you go into this next conditional， If b is equal to1。 So if I look at this code。

 Id say this has three control flow paths。 assuming there's no other control flow operations here。

 you got three paths， three paths1 is where A is equal to 0。 if a is equal to or sorry。

 not if a is equal0。 if A is not equal to1。 A is not equal to1。

 then you skip that whole inner inner conditional， the if b equal1。

 and you just finish to go to the end。 Okay so that's one1 path。 A is not equal to one。😊。

Then another path is a is equal to one， but B is not equal to one。

Then another path is A is equal to1 and B is equal to1。And in each one of those three。

 three sets of conditions， you're executing different sequences of instructions inside this program。

So there are three control full paths inside this piece of code。Now。

 one way to measure the complexity of a piece of code is how many control flow paths does it have so I can say look。

 this has three。So say I want to simplify that， and I might be able to use functional partitioning to reduce the control flow complexity a little bit。



![](img/f6bc54ee5a8dd0bfc6bdb563d32234d4_3.png)

So say take that function， fo。And now I take remember it had two conditionals， right。

 So now what I've done is I define two functions。And I've separated the conditionals。

 split them out across the two different functions。 So now Fo still has the first conditional。

 if a equal equal 1。 still got that。 But then the next conditional check it doesn't exist anymore more inside that function。

 Instead， it calls a function called check B。 Now， if you look at check B on the other side。

 that has the other conditional。 If B is equal to one than whatever。

 So I've separated these two conditionals。Now，Now that I've done this。

The fo function now has two pass to it。 A is equal to1 and a is not。 and then B check B。

 It has two passs。 B is equal to1 and B' is not。 So now each one of these functions has two control flow passs instead of the three control flow paths that I had when I merged them together so this is just a tiny example。

 But the idea is you can separate the conditionals into different functions and reduce the max complexity。

 right the max number of control flow passs， you can reduce that overall。

 making the code easier to debug typically。😊，Thank you。


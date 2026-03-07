# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p09 P9 03_编写主程序 -BV1QuJVzpEKE_p9-

Importing a module executes all the code in that module。 This is what you want。

 If the module contains function definitions， But if there is other code。

 then you can often have unexpected behavior。In this video， we'll demonstrate that。

 and then we'll show you how to fix it。In the palindrome functions。

 versions 1 and 2 both used a function called reverse。

 We copied and pasted that function from version 1 to version 2， but that created duplicate code。



![](img/97c9114d4fc253a97b32fb2317764848_1.png)

![](img/97c9114d4fc253a97b32fb2317764848_2.png)

If we find an error and function reverse， we would have to fix it in both places。

 This is clearly not a good situation。Instead， we could have imported version1 into version 2。

Before we get to that， though， let's add some code at the bottom of version 1 to ask the user for a word and report whether it's a palindrome。

When we run this module， we're asked to type a word and then murt told whether or not that word was a palindro。

Now， let's delete the reverse function from version 2。 and instead import the one from version 1。

We're about to run this version of our code。And notice that we have no code down here that calls input or print anything。

But when I run this module， because we're importing palindrome V1， we're asked to enter a word。

And were told whether or not it's a palindrome。The problem is that when we import palindrome V1。

 not only is it doing the function definitions， it's also executing the code at the bottom。

 even though we don't want that to happen here。I wouldn't be able to have my own program where I called input and print。

 because。That stuff is happening in the first version。

We need a way to specify that this code should only be run when this is the module that we're selecting run module on and not。

When we import that module。Every module has a variable called name。

Because this variable is built into Python， It begins and ends with two underscores。

Let's print its value in this program。When we run this module。

 we see that variable underscores name refers to the string containing underscores main。

 because it is the main module being run。

![](img/97c9114d4fc253a97b32fb2317764848_4.png)

![](img/97c9114d4fc253a97b32fb2317764848_5.png)

We'll interrupt this with control C。 switch back to version 2 and run this again。



![](img/97c9114d4fc253a97b32fb2317764848_7.png)

Notice the value of the module name now。When we ran the program and imported palindrome underscore V 1。

When we got to the print statement， the underscore's name variable referred to the string palindrome V1。

 not underscores main。Let's go interrupt this with control C。

Come back here and add a print statement to this version。

Where we print the name just to see what value we have。Now。

 both versions print their underscores name variable。When we run palindrome version 2。

 it's going to import palindrome version 1。That is going to print in version 1。 the module name is。

 And then whatever underscores names， value is。And then it's going to ask us to enter a word and report whether it's a palindrome。

 And then it's going to come back here and define function is palindrome V 2 and then print the underscore's name value again。

When we do this， we see that version 1's underscores name variable refers to the string palindrome underscore V1。

And that version 2's underscore's name variable refers to underscores main。

Underscoore's name only refers to string underscores main when the module is the one that's being run。

 So we can actually just write an if statement checking for that。 And if the name isn't main。

 the code won't be executed。Here， when we run the first version， we see that indeed it is executed。

But when we switch back to version 2， that code is not executed。

Only the print statement in version 2 is executed。 Nothing else is printed。We have a new rule。

 If you have code that should only be executed when a module is run and not when that module is imported。

 you should make sure to put that code inside。 And if underscores name equals， underscores name。

 if statement。

![](img/97c9114d4fc253a97b32fb2317764848_9.png)
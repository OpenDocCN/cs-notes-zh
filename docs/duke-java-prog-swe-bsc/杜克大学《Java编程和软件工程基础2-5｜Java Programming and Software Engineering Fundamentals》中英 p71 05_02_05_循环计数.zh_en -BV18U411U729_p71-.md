# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p71 05_02_05_循环计数.zh_en -BV18U411U729_p71-

![](img/1d760021039bbfbcce4b2aa253b27c0d_0.png)

Hi， as you get ready to solve problems that are slightly more complex。

 you'll learn some new programming constructs to help In this video。

 you'll learn about counting loops。

![](img/1d760021039bbfbcce4b2aa253b27c0d_2.png)

You've used different kinds of loops in solving problems before。



![](img/1d760021039bbfbcce4b2aa253b27c0d_4.png)

You'll use a wild true loop in finding codons in DNA or tags in a web page。

 and you've used a for each loop with an iterable many times。

 as in reading lines in a file or processing pixels in an image。



![](img/1d760021039bbfbcce4b2aa253b27c0d_6.png)

You've also used indexes to access and reference parts of a string。

 You know that indexes start with 0 in Java and with many other languages。

 So when you use dot index of， you know it returns 0 when a match is found at the first character in a string。



![](img/1d760021039bbfbcce4b2aa253b27c0d_8.png)

Both dot index of and dot substr use indexes to access the elements or characters of a string。

We'll look at code to access individual characters in a string。

We'll do this in the context of looking at the reverse of a string。

Where the reverse of CGA TTA is A TT AGC。And the reverse of T TIP is pit PIT。

Scientists studying genomes often have to look at a string backwards to analyze the DNA。

It can also be a source of fun or word play to look at phrases that are palindromes。

 the same red backwards as forward。Here's a sentence in Russian that you can see reads backwards and forwards。

 if you understand the cyrellic alphabet， it means the bore pressed the eggplant。In Spanish。

 we have a palindromic sentence that means they jogs the tortilla。While in French。

 the sentence a Saavlavash means and how is the cow？Finally。

 we see an English sentence draw O Caesar erase a coward。

 which is particularly appropriate as we implement a Caesar cipher in this module。

 We'll use a new loop， the counting loop， to reverse a string。😊。



![](img/1d760021039bbfbcce4b2aa253b27c0d_10.png)

Indexing a string in a loop can be done in several ways， but we'll look at a very common approach。

We must understand a loop with three parts。 Each part is separated from the other parts by a semicolon。

 as you can see in the code on the slide。The first part of the loop is called the initialization here。

 the variable K is assigned the value 0， and this happens once before the loop guard and the loop body are executed。



![](img/1d760021039bbfbcce4b2aa253b27c0d_12.png)

The loop guard is evaluated each time before the loop block or body may be executed。

 when the loop guard is true， the body is executed， and when it's false， the loop executes。

 Sometimes the loop guard is called the loop test。The increment here happens after all the statements in the loop body are executed。

After the increment， the loop guard is evaluated again to see if the loop continues or exits。

 We'll look at this more closely。To understand the for loop。

 we'll compare it to the while loop that you've seen before。



![](img/1d760021039bbfbcce4b2aa253b27c0d_14.png)

Though not with this precise style of counting in a loop。

The for loop does not provide more power than a while loop or allow you to solve different problems。

 The forlo is simply syntactic sugar or dressinging up of a while loop。

 The for loop puts all the parts in one place， and many programmers think this makes the loop easier to write and to read。



![](img/1d760021039bbfbcce4b2aa253b27c0d_16.png)

As we've discussed， the initialization happens once before the loop guard is tested。

 You can see in the comparison here how initialization happens before the while loop， too。



![](img/1d760021039bbfbcce4b2aa253b27c0d_18.png)

![](img/1d760021039bbfbcce4b2aa253b27c0d_19.png)

The loop guard is evaluated to see if the loop body will execute when the loop guard is false。

 the loop is over。 Both the while and the for loop exit when this loop guard or test is false。



![](img/1d760021039bbfbcce4b2aa253b27c0d_21.png)

![](img/1d760021039bbfbcce4b2aa253b27c0d_22.png)

When the guard is true， the loop body executes， and as the last statement in the body。

 we see the increment statement， which will execute。

Well trace through the execution of a for loop in a particular example of a reverse function to better understand the loop。

 And to trace this， we'll look at the call reverse pit。

 This means the value of parameter S is the string P I T。



![](img/1d760021039bbfbcce4b2aa253b27c0d_24.png)

![](img/1d760021039bbfbcce4b2aa253b27c0d_25.png)

The local variable R or RE will accumulate the reversed string。

 It's initialized to the empty string before the loop。 As we trace through the code。

 the green arrow indicates the statement that will execute next。

The loop index or control variable K is initialized to 0。

 Remember that the loop initialization only happens once in a for loop。

 and the variable K is only accessible within the loop， but not after the loop。 its scope is limited。



![](img/1d760021039bbfbcce4b2aa253b27c0d_27.png)

![](img/1d760021039bbfbcce4b2aa253b27c0d_28.png)

When the loop guard is checked， the value of k， which is0， is less than s dot length。Which is three。

 since Pitt has three characters。 The loop guard evaluates to true。

 Lo guards are always Boolean expressions。The loop body now executes。

 and the string method careat acts as as a character at a specific index。We should point out here。

 some people say care at the way I do， and some people say cha at either one is fine。Since k is 0。

 the expression S dot care at 0 evaluates to P。We've shown the character P with single quotes。

 which is used in Java to indicate the primitive type care。

The value of R is shown as the empty string in double quotes。

 because these double quotes in Java indicate a string literal Concatenating the character P to the empty string yields a new string P。



![](img/1d760021039bbfbcce4b2aa253b27c0d_30.png)

The variable RE will be assigned the value P， the string variable changes。

And it's no longer pointing to the empty string as it used to。

 Remember that strings in Java are immutable。 We can create new ones， but we can't change a string。

The increment executes after the loop body。 This changes K so that it has the value1。

After the increment statement， we're ready to trace the next iteration of the loop。



![](img/1d760021039bbfbcce4b2aa253b27c0d_32.png)

The local variable RE has the value P， the loop control variable K has the value 1。

 and we're ready to continue the trace。K has the value1。The length of S， the string pit is 3。

 and so the loop body executes since the guard evaluates to true。

Remember that the dot Careat method accesses the Caith character。Here that's the character I。

 whose index is one。The character I is prepened via string concatenation to R， which is P。

 And this creates a new string， I P。

![](img/1d760021039bbfbcce4b2aa253b27c0d_34.png)

The assignment statement changes RE so that it references this new string。

And now the loop increment will execute。The value of k is 2。And the loop will continue to execute。

Will now trace through the last iteration of the loop。 The local variable RE has the value I P。



![](img/1d760021039bbfbcce4b2aa253b27c0d_36.png)

The loop variable K has a value 2。 And as we can see here， the loop guard will be evaluated。



![](img/1d760021039bbfbcce4b2aa253b27c0d_38.png)

Since two is less than three， the guard is true， and the loop body executes。S dot care at T。

Evaluates to T， as you can see here。The character T is prepened to the string IP to form the string tip。

Variable R now references tip。And the loop continues。The increment statement executes。

Which changes k to have the value 3。Now the loop guard will be evaluated again。😡。



![](img/1d760021039bbfbcce4b2aa253b27c0d_40.png)

As the loop guard is evaluated here， you can see that the value of k is 3。



![](img/1d760021039bbfbcce4b2aa253b27c0d_42.png)

And the length of S is 3 as well。Since three is not less than three， the loop guard is false。

Control in the program continues to the statement after the loop。The value of RE is tip。

The reverse of the string parameter S， so tip will be returned。



![](img/1d760021039bbfbcce4b2aa253b27c0d_44.png)

It's good to know that you'll see others write code and you should understand that。



![](img/1d760021039bbfbcce4b2aa253b27c0d_46.png)

Many programmers use I as a loop control or index variables。

 Some programmers think the letter I is hard to distinguish from the number one。



![](img/1d760021039bbfbcce4b2aa253b27c0d_48.png)

![](img/1d760021039bbfbcce4b2aa253b27c0d_49.png)

But I is more common than K in reading other code。

![](img/1d760021039bbfbcce4b2aa253b27c0d_51.png)

Many programmers use the post increment operator I plus plus instead of I plus gets1。

 we won't explain the nuances of I plus plus here， but it's a very common idiom in using loops。

 and it's fine to use I plus plus by itself in the loop increment。



![](img/1d760021039bbfbcce4b2aa253b27c0d_53.png)

Sometimes it's useful to define the loop index variable before the loop。

 rather than inside the parentheses of the loop。

![](img/1d760021039bbfbcce4b2aa253b27c0d_55.png)

This allows the value of I to be referenced or accessed after the loop is over when the variable is defined within the parentheses of the loop。

 that loop control variable can only be referenced within the loop body， but not after the loop。

Have fun programming and programming and programming as you loop and loop and loop。


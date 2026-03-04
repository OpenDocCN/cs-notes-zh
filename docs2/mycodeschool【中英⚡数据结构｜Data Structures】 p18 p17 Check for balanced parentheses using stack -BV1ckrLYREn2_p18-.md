# mycodeschool【中英⚡数据结构｜Data Structures】 p18 p17 Check for balanced parentheses using stack -BV1ckrLYREn2_p18-

In our previous lesson we saw one simple application of stack。

 we saw that stack can be used to reverse a list or collection or maybe to simply traverse a list or collection in reverse order now in this lesson we will discuss another famous problem that can be solved using stack and this is also a popular programming interview question。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_1.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_2.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_3.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_4.png)

And the problem is given an expression in the form of a string comprising of， let's say。

 constants variables， operators and parenthesis。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_6.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_7.png)

And when I say parenthesis， I also want to include curly braces and brackets in my definition of parenthesis。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_9.png)

So my expression or string can contain characters that can be upper or lowercase letters。

 symbols for operators， and an opening or closing parenthsesis or an opening or closing curly brace or an opening or closing square bracket。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_11.png)

Let's write down some expressions here， I'm going to write a simple expression。

 we have one simple expression here with one pair of opening and closing parenthses。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_13.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_14.png)

Here in this expression， we have nested parenthesis。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_16.png)

Now given such expressions we want to write a program that would tell us whether parentheses in the expression are balanced or not。

 and what do we really mean by balanced parenthesis。

 what we really mean by balanced parenthesis is that corresponding to each opening parenthesis or opening curly brace or opening bracket we should have a closing counterpart in correct order。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_18.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_19.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_20.png)

These two expressions here are balanced。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_22.png)

However， this next expression is not balanced。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_24.png)

A closing curly brace is missing here。This next expression is also not balanced because we are missing an opening square bracket here。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_26.png)

This next one is also not balanced because corresponding to this opening curly brace we do not have a closing curly brace and corresponding to this closing parenthesis。

 we do not have an opening parenthesis if we are opening with a curly brace we should also close with a curly brace these two wantt count for each other。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_28.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_29.png)

Checking for balanced parenthesis is one of the tasks performed by a compiler。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_31.png)

When we write a program we often miss an opening or closing curly phrase or an opening or closing parenthesis compiler must check for this balancing and if symbols are not balanced。

 it should give you an error。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_33.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_34.png)

In this problem here whats inside a parenthesis does not matter。

 we do not want to check for correctness of anything that is inside a parenthesis。

 so in the string any character rather than opening and closing parenthses or opening and closing curly brace or opening and closing square bracket can be ignored this problem sometimes is better stated like this。

 given a string comprising only of opening and closing characters of parenthesis braces or brackets。

 we want to check for balancing。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_36.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_37.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_38.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_39.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_40.png)

So only these characters and their order is important while passing a real expression we can simply ignore other characters all we care about is these characters and their order okay so now how do we solve this problem？



![](img/f4cd63dafe8a5d075cd8592475fb40a6_42.png)

One straightforward thing that comes to mind is that because we should have a closing counterpart for an opening parenthesis or opening curly brace or opening square bracket what we can do is we can count the number of opening and closing symbols for each of these three types and they should be equal so the number of opening parenthesesis should be equal to number of closing parenthesis and the number of opening curly braces should be equal to number of closing curly braces and same should be true for square brackets as well but it will not be good enough this expression here。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_44.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_45.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_46.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_47.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_48.png)

Has one opening parenthesis and one closing parenthesis， but it's not balanced。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_50.png)

This next one is balanced， but this one with same number of characters of each type as the second expression is not balanced。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_52.png)

So this approach won't work。Apart from count being equal。

 there are some other properties that must be conserved。

 every opening parenthesis must find a closing counterpart to its right and every closing parenthesis must find an opening counterpart in its left which is not true in the first expression。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_54.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_55.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_56.png)

And the other property that must be conserved is that a parenthesis can close only when all the parenthses opened after it are closed。

 this parenthesis has been opened after this square bracket。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_58.png)

So this square bracket cannot not close。😡。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_60.png)

Unless this parentheesis has closed。Anything that is opened last should be closed first。

 well actually it should not be last opened first closed in this example here。

 this is getting opened last。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_62.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_63.png)

But this guy。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_65.png)

That is open previous to this is closed first and it is fine the property that must be conserved is that as we scan the expression from left to right any closer should be for the previous unclosed parentheses any closer should be for the last unclosed。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_67.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_68.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_69.png)

Let's scan some expressions from left to right and see how it's true。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_71.png)

Let's scan this last one， we will go from left to right， first character is an opening of S bracket。

Second one is an opening parenthesis。Let's mark opening of unclosed parenthesis in red。Okay。

 now we have a closer here。The third character is a closer。

 this should be the closer for the last unclosed， so this should be the closer for this one。

 this guy。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_73.png)

This opening parenthesis。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_75.png)

Last and closed now is this guy。Next character once again is an opening parenthesis。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_77.png)

Now we have two unclosed parenthsesis at this stage and this one is the last enclosed。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_79.png)

The next one is a closure， so it should be closer for the last andclosed。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_81.png)

Now the last ten closed once again is the opening of square bracket now when we have a closer。

 it should be closer for this guy。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_83.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_84.png)

We can use this approach to solve this problem what we can do is we can scan the expression from left to right and as we scan at any stage we can keep track of all the unclosed parenthses。

 basically what we can do is whenever we get an opening symbol。

 an opening parenthesis an opening curly brace or an opening square bracket， we can add it to a list。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_86.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_87.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_88.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_89.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_90.png)

If we get a closing symbol， it should be the closer for the last element in the list。

 in case of an inconsistency， like if the last opening symbol in the list is not of the same type as the closing symbol or if there is no last opening symbol at all because the list is empty。

 we can stop this whole process and say that parentheses are not balanced。

 else we can remove the last opening symbol in the list because we have got its counterpart and continue this whole process。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_92.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_93.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_94.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_95.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_96.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_97.png)

Things will be further clear if I will run through an example。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_99.png)

I will run through this last example once again， we are going to scan this expression from left to right and we will maintain a list to keep track of all the opened parenthses that are not yet closed we will give a track of all the unclosed parenthsesis opened but not closed initially this list is empty the first character that we have got is an opening of square bracket this will go into the list and we will move to the next character。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_101.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_102.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_103.png)

The next character is an opening parentheesis so once once again it should go to the list。

 we should always insert at end in the list， the next character is a closing of parenthsesis now we must look at the last opening symbol in the list and if it is of the same type then we have got its counterpart and we should remove this。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_105.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_106.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_107.png)

Now we move on to the next character， this is once again an opening parenthesis。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_109.png)

It should go in the list at the end。The next character is a closing of parenthesis。

 so we will look at。The last element in the list， its an opening parenthesis so we can remove it from the list。

And now we go to the last character， which is a closing of square bracket once again we need to look at。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_111.png)

The last element in the list we have one element， only one element in the list at this stage。

 it's an opening of square bracket， so once again we can remove it from the list Now we are done scanning the list and the list is empty once again If everything is all right if parenthsesis are balanced we will always end with an empty list if in the end list is not empty then some opening parenthesis has not found its closing counterpart and expression is not balanced One thing worth noticing here is that we are always inserting or removing one element at a time from the same end of the list。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_113.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_114.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_115.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_116.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_117.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_118.png)

In this whole process， whatever is coming in last in the list is going out first。

 there is a special kind of list that enforces this behavior that element should be inserted and removed from the same end and we call it a stack in a stack we can insert and remove an element one at a time from the same end in constant time so what we can do is whenever we get an opening symbol while scanning the list we can push it onto the stack and when we get a closing symbol we can check whether。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_120.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_121.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_122.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_123.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_124.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_125.png)

The opening symbol at the top of stack is of the same type as the closing symbol。

 if it' is of the same type we can pop if it is not of the same type。

 we can simply say that parentheesis are not balanced。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_127.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_128.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_129.png)

I will quickly write pseudocode for this logic， I am going to write a function named check balanced parenthesis that will take an expression in the form of a string as argument。

 first of all I will store the number of characters in the string in a variable and then I will create a stack and I will create a stack of characters。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_131.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_132.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_133.png)

And now I will scan the expression from left to right using a loop while scanning if the character is an opening symbol。

 if it's an opening parenthesesis or opening curly brace or opening square bracket。

 we can push that character onto the stack， let's say this function push will push a character onto S else if expression I or the character at Iat position while scanning is a closing symbol of any of the three types。

 we can have two scenarios if stack is empty or。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_135.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_136.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_137.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_138.png)

Top of stack does not pair with the closing symbol If we have a closing of parenthesis。

 then the top of stack should be an opening of parenthsesis。

 it cannot be an opening of curly brace in such a scenario we can conclude that the parenthsesis are not balanced else we can perform a pop Finally once our scanning is over we can check whether stack is empty or not if it's empty parenthsesis are balanced if it's not they are not balanced。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_140.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_141.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_142.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_143.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_144.png)

So this is my pseudocode let's run through a couple of examples and see whether this works for all scenarios all test cases or not let's first look at this expression the first thing that we are doing in our code is that we are creating a stack of characters I have drawn logical representation of a stack here okay now let's scan this string let's say we have a zero based index and the string is just a characteristic array we are starting the scan we are going inside the loop。

 this is a closing of parenthesis so this if statement will not hold true so we will go to the elses condition。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_146.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_147.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_148.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_149.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_150.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_151.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_152.png)

And now we will go inside the Ls to check for this condition。

 whether stack is empty or not or whether the top of stack appearss with this closing symbol or not。

 the stack is empty。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_154.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_155.png)

If the stack is empty there is no opening counterpart for this closing symbol。

 so we will simply return false， returning means exiting the function。

 so we are simply concluding here that parenthsesis are not balanced and exiting。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_157.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_158.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_159.png)

Let's go through this one now first we have an opening square bracket so we will go to the first if and push next one is an opening parenthesis once again it will be pushed next one is a closing square bracket so the condition for this else if will be true we will go inside this else if now this time the top of stack is an opening parenthesis it should have been an opening square bracket。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_161.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_162.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_163.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_164.png)

And then only we would have a pair， so this time also we will have to return false and exit。Okay。

 now let's go through this one first we will have a push。

The next one will also be a push now next one is a closer of parenthesis。

 which pairs with the top of stack which is opening of parenthesis， so we will have a pop。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_166.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_167.png)

We will go to the next character and this one once again is an opening parenthesis。

 so there will be a push。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_169.png)

Next one is a closing parenthesis and the top is an opening parenthesis， the pairs。

 so there will be a pop。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_171.png)

Last character is a closing curly brace so once again we will see whether top of stack is an opening curly brace or not do we have a pair or not。

 yes we have a pair so there will be a pop with this our scanning will finish and finally stack should be empty it is empty so we have balanced parenthesis here。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_173.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_174.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_175.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_176.png)

Try implementing this pseudocode in a language of your choice and see whether it works for all test cases or not if you want to look at my implementation you can check the description of this video for a link in the coming lessons we will see some more problems on stack this is it for this lesson thanks for watching。



![](img/f4cd63dafe8a5d075cd8592475fb40a6_178.png)
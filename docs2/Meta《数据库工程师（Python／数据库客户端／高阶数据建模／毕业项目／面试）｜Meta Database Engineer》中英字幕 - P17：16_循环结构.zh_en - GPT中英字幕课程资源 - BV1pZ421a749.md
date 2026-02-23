# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P17：16_循环结构.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Have you ever come across a song that you like so much you want to listen to it again and again。

 you select the loop option so that you can listen to it repeatedly。😊。

This action of repetition is known as looping and also exists in Python。In this video。

 you'll learn to use looping constructs when the same set of steps must be carried out many times。

Python has two different types of looping constructs for iterating over sequences。

 the for loop and the while loop。Looping is used to iterate through the sequence and access each item inside the sequence。

Let's start with a basic example of looping using a string。First。

 you declare a variable called STR which is of type string。

 recall that a string in Python is a sequence which means you can iterate over each character in the string。

A sequence is just an ordered set now let's break apart the for loop and discover how it works。😊。

The variable item is a placeholder that will store the current letter in the sequence。

You may also recall that you can access any character in the sequence by its index。

The for loop is accessing it in the same way and assigning the current value to the item variable。😊。

This allows us to access the current character to print it for output。😊，When the code is run。

 the outputs will be the letters of the word looping each letter on its own line。



![](img/4eeba068a1196d3d49a186b19c0ee7d3_1.png)

Now that you know about looping constructs in Python。

 let me demonstrate how these work further using some code examples to output in a array of tasty desserts。

Python offers us multiple ways to do loops or looping。

 you'll now cover the for loop as well as the while loop。

Let's start with the basics of a simple for loop。😊，To declare a for loop。

 I use the four keyword I now need a variable to put the value into in this case I am using I I also use the in keyword to specify where I want to loop over。

I add a new function called range to specify the number of items in a range in this case。

 I'm using 10 as an example。😊，Next， I do a simple print statement by pressing the enter key to move to a new line。

😊，I select the print function and within the brackets， I enter the name looping and the value of I。😊。

Then I click on the Run button。The output indicates the iteration looped through the range of  zero to9。

It's important to note the three main points。The iteration starts at zero based on the index of the item itself。

Every for loop usually starts with zero。Most arrays start at zero the reason for that is that it's the first item in an array or the first item in the index in this case the last item in the array or index will be9。

😊，Now I want to change what I loop through as an example。

 I will enter a simple array above and call it favourites。To do this。

 I start by removing the hash sign in front of favorites。😊，Next。

 I replaced the range function in the current four loop with favourites to loop through。

The eye that I declared as part of the for loop can change to any value。

 and in this case I'm using item。😊，I now change my print statements to include item in my print loop。

I also change the text to I like this dessert， I click on the Run button to print the value stream。

In this case， It calls each of the five dessert titles in turn and our print statement combines them into a sentence。

The next looping option I'm discussing is the wild loop。

The wild loop differs slightly from the for loop。😊，To demonstrate this type of loop。

 I first comment out the four loop on my screen， Let's start by using the while keyword As in the for loop。

 I need to specify a condition to make the loop over n times， depending on the value itself。😡，First。

 I need to declare a counter， I do this by typing count equals zero above my looping statement。

Next I enter count after the while keyword followed by the less sign and the word favourites Now I insert the function L to provide the length of favourites This means the loop will run while the count is less than the length of favourites in other words。

 while it is less than five。To print the value of the looping statement。

 I press the enter key and move to a new line。Then I select the print function and within brackets。

 I enter the text， I like this dessert。The key difference here is that I need to use the index to access the items within the favorite array to do this。

 I type favorites and add count to represent the index。

It's important that I now increment count so that it will essentially match the loop statement。

If I do not increment count， I'll end up with what is called an In loop。😡。

This means it will just keep looping and looping until the compiler stops it from running out of memory。

To increment the count， I press enter to move to a new line and add counts plus equals to one。

I clear my screen and click the Run button。I get the same print output as the for loop。

It's important to note that in a standard4 loop I don't have access to the index。

 but I can use the enumerate function to do that， so I change my current for loop statement by adding IDX and it becomes for IDX item in that I call the enumerate function with favorites in parenthesis。

On the next line， to print the output， I replace the text I like this desserts with IDX and click the Run button。

The results display the index and the value of the item within the array。



![](img/4eeba068a1196d3d49a186b19c0ee7d3_3.png)

Congratulations in this video you learned about looping constructs in Python using the Fort loop。


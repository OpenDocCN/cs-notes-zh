# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P39：38_Python反转字符串.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

One of the basic ways to test the Python developer's problem solving skills is by asking them how they were to reverse a string。

Knowing how to do this is very useful in the production environment。

 Some programming languages have a built in function to reverse a string。

 Python doesn't have such a function， but fortunately， due to the language's flexibility。

 there are several ways to do this。 In this video， I will show you two ways to reverse a string in Python。



![](img/91420748a68131aabf9f539c98e33edf_1.png)

First， I'll demonstrate how to do this with the slice function。To start off。

 I create a file called stringing reversal dot Pi。The format or syntax of a slice function is that it always starts with the name of a string。

 open square bracket， the start parameter， colon， the stop parameter， another colon。

 and then the step parameter followed by a closed square bracket。

 I'll add a hash symbol in front of this line to indicate that it is a note。

This is called the extended slice syntax。 The start and stop parameters are the indices between which the function manipulates the string。

The step parameter is the hops or jumps the function makes wallcher versus a given string。

I will now first define a string， then manipulate the string with a slice function and finally print the string。

 I'll call the string trial and assign the word reversal as its value by typing trial equal sign。

And the word reversal between double quotes。To manipulate the string。

 I create a new string called New trial。Now I assign a value to newtri with the slice function。

I type in equal sign， trial， and open square bracket。To instruct Python to use the entire string。

 I leave the value of the start and stop parameters empty。

 I simply type two colons and then add the value of the step parameter as the number minus1。

 followed by a closed square bracket。The negative value of this step parameter indicates that the string needs to be traversed from the right。

 one index position at a time， instead of the conventional method of starting from the left。Finally。

 I print the manipulated string to test if it works。I type print and between parentheses。

 I add the string name， new trial， I click on Run。Great， in the terminal。

 the string has successfully been reversed。In summary。

 the entire string is traversed from right to left， one index position at a time。

This new sliced object is then copied to another string which is then rearranged and printed。

It should be noted that you can use the slice function to manipulate the same variable。

 I only used a second variable in this example， for clarity。

The slice function is the simplest way to reverse a string。

 I will now demonstrate another way you can use the slice function to reverse a string。This time。

 using recursion。I start by creating a new file and saving it as string reversal 2 dot pi。Next。

 I define a function and pass a string variable to it， namely STR。

 I type de and the function name string reverse and STR between parentheses followed by a colon。

This function will act as a conditional if statement。I type if。L EN， Open parenthesis。

STR Close parenthesis， two equal signs， the number is 0， followed by a colon。On the next line。

 I'll return the value of STR。Now let's add the else statement。

The L statement will recursively call the slice function， but with a modified string every time。

On the next line， I add El and a colon。Then， on the next line。

 I type returnturn stringing reverse STR。But before I close the parentheses。

 I add a slice function by typing open square bracket， the number one。

 and a colon followed by the closed square bracket。This time， the string is traversed from the front。

 skipping the first character in every loop。And this first character skipped is appended to the remaining string。

So I now add a plus sign， STR， and the value 0 in between brackets。Outside the function。

 I give STR the value of reversal。Then I create a second variable that will store the value of the return string。

All'll call this variable reverse and assign to it the value of the function。Finally。

 I add a print statement for the variable reverse。Let's run the code。

Success the string displays in reversed order in the terminal。Essentially。

 the function calls itself by passing a different string in each recursion and appending the element it has kept right after it。



![](img/91420748a68131aabf9f539c98e33edf_3.png)

In this video， you learned two different methods to reverse a string in Python。

 the first by just using a slice function and the second by using a slice function with recursion。



![](img/91420748a68131aabf9f539c98e33edf_5.png)
# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p105 105_04_11_编程演示-文件转字典.zh_en -BV13E421M7FF_p105-

Let's write code to create a dictionary from a file。



![](img/c9d5ec74e7308a6b1c76d30858bff209_1.png)

Here's the file we want to load。 Each line on the file has an expense for a user。

 You'll see the user's name。 followed by a comma， followed by the expense amount。

 Our code will calculate the total expense amount for each user in this file。

So let's create a function。We'll call it import and create。Dictionary。

It'll take a given file name to load。This function is used to create an expense dictionary。

From a file。Every line in the file should。Be in the format。Key comma value。The key。Is a user's name。

And the value is。An expense。To update。The users。😔，嘈咯。😔，Expense。If we look at the file again。

 we'll note that there are certain lines that are either blank。Have a missing expense amount。

Or have an invalid expense amount， meaning it's not something that can be interpreted numerically。

So our code will ignore these three types of lines。The value should be a number。However。

It is possible。That there is。No value。😔，That the。Value is an invalid number。

Or that the entire line is blank。So let's write our code。

 we'll start by creating an empty dictionary。 we'll call it expenses。Create empty。Dictionary。

Then we'll open the given file name and read the lines into a list。F equals open。

The given file name will open it in read mode。And then we'll call the read lines function。

And read the lines into a list。 We'll call it lines。

Open file in read mode and read all lines into a list。

Then we'll iterate over each line in the list of lines and split it into a list based on a comma separator。

 So for each line。In the list of lines。We'll take the line and we'll split it。

Into a list based on a comma separator， and we'll call it LST。If we look at the file。

 we could see that there are particular lines that have white space at the beginning and potentially at the end。

 So let's go ahead and handle that。 So here on this line。

 let's go ahead and remove any white space at the beginning and the end of the line。Will you strip。

We'll do that before we split。So we're going to strip white space from beginning and end of line。

Then split into a list based on。Coma separator。From the list that we create from the line。

 we're going to extract the key in the value。 So let's get the first and the second thing from the list。

 We'll call the first thing key。From the list， get the first thing using index 0 and then strip any white space from the beginning and the end of that。

And then get the value from the list using index 1。

And then strip any white space from the beginning and the end of that。

The key is the first thing in the list。 That's the name。

 and the value is the second thing in the list。 That's the expense amount。 If we look at the file。

 we could see it here on each line， we'll have the first thing in the list。

 which is the name followed by a comma， followed by the second thing in the list。

 which is the expense amount。So get key， which is the name and value， which is the expense amount。

From list。As noted， if we look in the file， there are particular lines that might be missing in expense amount here on line 7。

 we can see the name Brandon， followed by a comma， but there's a missing expense amount。

 So we want to consider these lines on our code。To do that。

 let's check the length of the list before we extract the first and the second thing in the list。

So if the length of the list is less than or equal to one。

 let's go ahead and skip that line or continue to the top of the for loop。 So skip line， if missing。

Value or expense。Amount。Next， we want to cast the value or the expense amount to a numeric value so that we can treat it like a number and do math with it。

If you recall from the file， there are particular lines that have an expense amount that can't be considered numeric per se。

 For example， here on line 8， the expense amount is 22。 The string。

 Python won't know how to convert this to a numeric value。

 So we'll need to consider that in our code。So we want to make sure we cast inside of a try except in the event that the casting doesn't work。

 meaning we're trying to cast a value that can't be considered numeric。

So let's go ahead and add a try。Inside of the try。We'll take the value。

And will cast the value to a float。And in the event it can't be casted。

 we'll go ahead and catch that in the accept block。We'll continue to the top of the for loop。

 This means we'll move on to the next line in the list of lines。

So here we're going to cast value to float。😔，Otherwise。Go to top of for loop。

To next line in list of lines。Next， we want to take the value or the expense amount and associate it with the key or the name in the dictionary。

So， let's reference the。Expenses dictionary。Willll associate a value with the key。

 The key is the name that we extracted from the line here。

And the value we're going to set is going to be based on the current value already associated with that key if it exists in the dictionary。

 So let's look it up。So from the expenses dictionary， let's get the value associated with the key。

If it doesn't exist， let's default to 0。And then let's add the new value。

Look up the key or name in the expenses dictionary。If it exists。

 get the associated value or total expense amount for that key。If it doesn't exist， default to zero。

In either case， add the new value or expense amount for this line and then associate with the key or the name back in the expenses dictionary。

This is how we calculate the total expense amount for each key or name。

Add new expense amount to current。Total expense amount。Associated with。The key or the name。Or 0。

 if it doesn't exist。And then associate the new total。Expense amount with key。Or name。

In the expenses dictionary。The last thing we're going to do。Let's go ahead and close the file。

 We're done with that and then return the new expenses dictionary from the function。Turn expenses。

To run this， let's create a main method。Let's call our function， import。

 and createre dictionary the file that we're going to load。Is expenses TxT。

 We'll get the return value， which is a dictionary。 We'll call it expenses。



![](img/c9d5ec74e7308a6b1c76d30858bff209_3.png)

Then we'll print expenses。Expenses。Then let's launch the main function。If the name。Is Maine。Caoming。

Let me run the program。Lad expenses。You the output。And we can see our final dictionary。

 the key or name is Brandon， To expenses is 443， The key or name is Ted， total expenses 93821。

 Barbara has 102， and Betsy has 86431。And if we take a look at our file。

ExpensesWe could see that Brandon had an expense of 342。Brandon also had an expense of 101。

This one was ignored， and this one was ignored， but the total expense amount for Brandon is 443。

 Similarly for Ted，9，38，21。 So Ted had an expense of 7。 He also had an expense of 9，31，21。

 So Ted's total expense amount is 9，38，21。

![](img/c9d5ec74e7308a6b1c76d30858bff209_5.png)
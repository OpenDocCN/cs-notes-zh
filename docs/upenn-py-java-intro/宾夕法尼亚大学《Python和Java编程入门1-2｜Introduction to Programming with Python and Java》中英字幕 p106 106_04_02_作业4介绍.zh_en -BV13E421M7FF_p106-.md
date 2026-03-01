# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p106 106_04_02_作业4介绍.zh_en -BV13E421M7FF_p106-

![](img/1eef50235c62c6372eb63440126382b0_0.png)

In this assignment， you'll implement an online banking system。 Use can sign up with the system。

 log into the system， change their password and delete their account。😡。

They can also update their bank account balance and transfer money to another user's bank account。



![](img/1eef50235c62c6372eb63440126382b0_2.png)

You'll implement functions related to file I O and dictionaries。

 Two of the functions require you to import files and create dictionaries。

 Use information will be imported from the user' dot text file and account information will be imported from the bank dot text file。

 Take a look at the content in the different files。

 The remaining functions require you to use or modify the two dictionaries created from the files。

 Let's go ahead and take a look at the files that will be imported by your program。



![](img/1eef50235c62c6372eb63440126382b0_4.png)

To view the files， you can go to file open。In the current directory。

 you'll see the bank TxT file and the user Txt file。 Let's view the user Txt file first， click on it。



![](img/1eef50235c62c6372eb63440126382b0_6.png)

This file contains user account information。 Your program will import this file and create a user accounts dictionary file based on the information contained in this file。

Each line in the file contains information about a single user account。😡。

The format on each line should be the same。 You'll see the user's name， followed by a space。

 followed by a hyphen， followed by another space。 followed by the user's password。

 Your program will read each line in this file and create an account in the user accounts dictionary。

Note that particular lines in the file could be missing a password or contain an invalid password。

 Your code will have to consider these lines when it imports the file。

Now let's take a look at the bank。txT file。😡，Click on it。This file contains bank account information。

 Your program will import this file and create a bank's dictionary based on the information contained in this file。

 Each line in the file contains an initial deposit amount for a particular user's bank account。

The format of each line should be the same。You'll see the user's name， followed by a colon。

 followed by an initial deposit amount。 your program will load each line from this file and calculate the total initial deposit amount for a particular user。

😡，Note that particular lines in the file could contain an invalid deposit amount。

Or have a missing deposit amount， or could be completely blank。

Your code will need to consider these different types of lines when it imports the file。

 Let's go back and start writing some code。

![](img/1eef50235c62c6372eb63440126382b0_8.png)

![](img/1eef50235c62c6372eb63440126382b0_9.png)

I'll get you started。The first function we're going to write is the import and create bank function。

 This will take a given file name and create a bank dictionary from the file。

 The file we're going to read is the bank do TXT file。😡。



![](img/1eef50235c62c6372eb63440126382b0_11.png)

So let's go ahead and start writing some code。This function creates an empty bank dictionary for us and then returns that bank dictionary at the bottom of the function。

 We'll put our code here。 The first thing we want to do is read the file。Let's use the open function。

Give it the given file name。And then we'll open it in Read mode。

 and then we'll store the file or the connection to the file。In variable F。

Then we can read all of the lines in the file using the Read lines function。That will return a list。

 We'll store that in the variable lines。So we can say open， file in read mode。Get all lines in file。

 as。List。Next， we'll iterate over each line in the list of lines and extract the information from each line。

 So for each line in the list of lines。We're going to go ahead and first strip the white space from the beginning and the end of the line and then split the line based on a colon。

So let's take the line。 Let's strip the white space from the beginning and the end。

 and then let's split the line into a list。Based on the colon separator。Store that in a variable LST。

So iterate。Over each line in list of lines。Sttriip white space from beginning and end of line。

Split line into list。Based on。Colin。😔，Separator。So let's go ahead and take a look at our bank dot TXT file again。



![](img/1eef50235c62c6372eb63440126382b0_13.png)

Open。

![](img/1eef50235c62c6372eb63440126382b0_15.png)

They open this in its own tab。What we're doing is reading each line in this file。

 We're taking each line。 We're stripping the white space at the beginning and the end。

 and then we're splitting the entire line into a list based on a colon and separator so that we can then extract the name and a deposit amount。



![](img/1eef50235c62c6372eb63440126382b0_17.png)

So let's go back to our notebook file。

![](img/1eef50235c62c6372eb63440126382b0_19.png)

So after we strip the white space from the beginning and the end of the line and then split the line into a list。

 we want to extract the name and the deposit amount from the list。To do that。

 let's go ahead and get the first thing in the list using In 0。

We'll strip the white space from the beginning and the end of that。And we'll call this the key。

 And then let's get the second thing in the list using index 1。

 strip the white space from the beginning and the end of that， and we'll call that value。

We'll use these to create an entry in the dictionary。

 The first thing in the list will be whatever comes before the colon。 That'll be the name。

 We'll use that as a key in the dictionary。 And the second thing in the list will be whatever comes after the colon。

 That'll be the deposit amount and we'll use that as a value associated with the key in the dictionary。



![](img/1eef50235c62c6372eb63440126382b0_21.png)

![](img/1eef50235c62c6372eb63440126382b0_22.png)

So， get key。Or name and value or deposit amount from line。

Before we get the first and the second thing in the list。

 let's make sure that the list actually has two things to get。



![](img/1eef50235c62c6372eb63440126382b0_24.png)

If we take a look at the data file， we could see that particular lines in the file do not have a deposit amount。

 and in some cases， the line is completely blank。 so let's consider this in our code。



![](img/1eef50235c62c6372eb63440126382b0_26.png)

We can do this by checking the length of the list if the list has less than two things。

 ignore this line。

![](img/1eef50235c62c6372eb63440126382b0_28.png)

If the length of the list is less than or equal to1。Continue。

Continue will immediately take us back to the top of the for loop。

 thereby skipping this line and moving on to the next line in the list of lines。So skip line。

 if it does not have a name and。Deposit amount。This will essentially skip lines like this on line 4。

 where there's no deposit amount。 Itll skip lines like this on line 5 that are completely blank。

 It'll also skip line 12， which is completely blank。



![](img/1eef50235c62c6372eb63440126382b0_30.png)

![](img/1eef50235c62c6372eb63440126382b0_31.png)

Our code is also taking care of any white space that might be around the name or the deposit amount by calling strip on the first thing in the list and strip on the second thing in the list。

 were taking care of any white space that might be contained here before the colon or here after the colon。

😡。

![](img/1eef50235c62c6372eb63440126382b0_33.png)

![](img/1eef50235c62c6372eb63440126382b0_34.png)

So， strip white space from。Beginning of key， which is the name and value。

 which is the deposit amount。Before we add the key in value to the dictionary。

 we want to cast the value or the deposit amount to a numeric value so that we could treat it like a number and do math with it。



![](img/1eef50235c62c6372eb63440126382b0_36.png)

If we take a look at the file again， we could see that there are particular lines in the file that have a deposit amount that can't be considered numeric per se。

 For example， line 3， the deposit amount is X， Y， Z。

 Python won't know how to convert this to a numeric value。 So we need to consider that in our code。



![](img/1eef50235c62c6372eb63440126382b0_38.png)

So we want to make sure that we cast inside of a try except in case the casting doesn't work。

 meaning we're trying to cast a value that can't be considered numeric。So we'll do try。

And then we'll cast， so we'll say value is equal to the value casted to a float。



![](img/1eef50235c62c6372eb63440126382b0_40.png)

Then we'll add our accept if the casting doesn't work。

 we'll continue to the top of the for loop and skip this line。

So try to cast value or deposit amount to numeric。Value。Otherwise， skip this line。

Once we've casted our value or deposit amount to a numeric value。

 we can go ahead and add it to the bank dictionary and associate it with the key or the name on the account。

So let's go ahead and reference our dictionary。And then use the key。

 and then we're going to set it to a value。Let's first check to see if there's already a value associated with this key。

 So let's look up the value associated with the key bank dot get。Look up the key。

This will give us the value or the deposit amount associated with this key。 If it doesn't exist。

 let's just use 0， and then let's add the new value or the new deposit amount。

Look up the current value associated with the key。If the key doesn't exist in the dictionary。

 use 0 and then add the new value or the deposit amount and then associate with that same key in the dictionary Here。

 we're calculating the total of all the deposit amounts associated with a single key。

If we look at the file， we could see that the deposit amount 5 and the deposit amount 100。

5 will be added together and associated with the key brandon。



![](img/1eef50235c62c6372eb63440126382b0_42.png)

![](img/1eef50235c62c6372eb63440126382b0_43.png)

Add new。Deposit amount to current。Total balance。Associated with the key。Or the name。Or zero。Finally。

 let's close our file。Call the close function。 and then we're going to return the bank dictionary from this function。



![](img/1eef50235c62c6372eb63440126382b0_45.png)

Let's run the code in this cell。

![](img/1eef50235c62c6372eb63440126382b0_47.png)

Then let's run our test in the next cell。

![](img/1eef50235c62c6372eb63440126382b0_49.png)

I can see that all the tests pass。 I see success here。Specifically， if we take a look at this test。

 we could see that we get the account balance associated with Brandon， and that should be 115。5。



![](img/1eef50235c62c6372eb63440126382b0_51.png)

If we look at our file， we could see that Brandon had a deposit of five。A deposit of 10。

 and then a deposit of 100。5。 The total there is 115。5。



![](img/1eef50235c62c6372eb63440126382b0_53.png)

If we look at the test here， we try to get the account balance for Joel and assert that it's none。

 That's because if we look at the file， Joel is not here。 There are no deposits for Joel。



![](img/1eef50235c62c6372eb63440126382b0_55.png)

![](img/1eef50235c62c6372eb63440126382b0_56.png)

If we want to see and print the bank dictionary， we could print it in the import and create bank function。



![](img/1eef50235c62c6372eb63440126382b0_58.png)

Let's do that here。Print。😔。

![](img/1eef50235c62c6372eb63440126382b0_60.png)

Bank。Let's rerun this cell。

![](img/1eef50235c62c6372eb63440126382b0_62.png)

And then rerun our testing cell。

![](img/1eef50235c62c6372eb63440126382b0_64.png)

And this shows us our entire bank dictionary。 We could see that Brandon has a balance of 115。5。

 Patrick has a balance of 18。9， and we have Sarah， Jack and James。



![](img/1eef50235c62c6372eb63440126382b0_66.png)

![](img/1eef50235c62c6372eb63440126382b0_67.png)
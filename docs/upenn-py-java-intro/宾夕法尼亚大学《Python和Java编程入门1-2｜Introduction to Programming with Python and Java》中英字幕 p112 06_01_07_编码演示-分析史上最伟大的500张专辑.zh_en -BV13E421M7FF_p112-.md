# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p112 06_01_07_编码演示-分析史上最伟大的500张专辑.zh_en -BV13E421M7FF_p112-

For our analysis using the CSV module， we're going to look at the 500 greatest albums of all time。

This is Rolling Stone Mag's 2012 list of 500 greatest albums of all time with genres。

You can read more about that here。Here are the columns in our data file number。

 which is the position of the album on the list year， which is the year of release album。

 which is the name of the album。Artist， which is the name of the artist genre。

 which is the genre name and sub genre， which is a comma separated list of sub genrere names。



![](img/ad6786a85e8551a7b06284eeddded9c1_1.png)

Let's load and read the album list CSv file using the CSv module。 So first。

 we're going to import CSV。Then we're going to use the width statement。Call the open function。

 Give it the name of the file， album list dot CSv。 I'm going to open that in read mode。

Will store in a variable called CV file。And then I'm going to read that file into a diict reader。

 which is a dictionary。 We'll call it reader equals Csv dot diict reader。

Give it the name of this variable here， CV file。This will load the file into a reader。

 Let's print the type of that reader。Print the type of the reader。

 And then let's print the column headers by accessing the field names attribute。 So let's print。

From the reader， the field names。So here we see the type is Dt Read。

 and here are the column headers in the file。Now let's print each row in the file using a for loop。😡。

So the first thing I'm going to do is load the file again using the width statement。

 and then I'm going to read the file into a diict reader。

 and then I'm going to iterate over or step through that reader to print each row。

 We'll use a for loop。For each row in the reader。Print the row。And this loads the file into a reader。

Iterates over or steps through it。To print each row。



![](img/ad6786a85e8551a7b06284eeddded9c1_3.png)

And here we can see each row in the file， It's a dictionary， an order dictionary。

 and we have the column name， the value， column name， value， column name。

 value for each album on the list。So important note， by default。

 a dict readerator only allows you to iterate over it once。

 This is because a dict readerator reads the file directly and does not store the data in memory。

There are workarounds to this， but don't try them for now。

 the best solution is to reload the file every time you need to use the dictator。

Now let's print the first 100 rows of data using a for loop。



![](img/ad6786a85e8551a7b06284eeddded9c1_5.png)

Let me add a few cells here。 First thing I'm going to do again is to reload my file。

 So I'm going to copy this， paste it here。 We're going to open the file and read mode。

 load it into a reader。 and now I'm going to use a four loop to print just the first0 rows。



![](img/ad6786a85e8551a7b06284eeddded9c1_7.png)

So first I'll set a variable rows。To be 101， then I'm going to iterate over the reader using a for loop。

For each row in。Reader。We're going to subtract one。From Rose。

And then we'll just test the value If rows is greater than 0。Print it。Else。Break out of the loop。

So this reads the file into a diict reader。 It iterates over it or steps through it。

 decrementing or subtracting one from the row count。 If the row value is greater than 0。

 it prints the row。 Otherwise， it breaks out of the for loop。



![](img/ad6786a85e8551a7b06284eeddded9c1_9.png)

Let's run our code。And here you can see the first 100 rows of data。



![](img/ad6786a85e8551a7b06284eeddded9c1_11.png)

![](img/ad6786a85e8551a7b06284eeddded9c1_12.png)

![](img/ad6786a85e8551a7b06284eeddded9c1_13.png)

Now we're going to copy the data from a diict reader to a list。😡。



![](img/ad6786a85e8551a7b06284eeddded9c1_15.png)

Add a couple cells here。 First thing I'm going to do is。Open the file and load it into a reader。

 I'm going to do that here。 Then I'm going to create an empty list。 Als equals empty list。

 I'm to iterate over the reader or step through it and then append each row to that list。

For each row in reader。Let's go ahead， and。A panthro。To the list。

So for each record or row in the reader， add it or append it to the list。

 then let's print the length of the list， which is the number of rows in the file。So， we'll print。😔。

Number of albums。Which should be the length of the list。Run our code。

 There's 500 albums or 500 rows in the file。So note。

 we can now use the albums list for the remainder of our analysis。

 There's no need to reopen the file and reread it into a dict reader。

So another way to add records to a list is by using list comprehension。

 an elegant and concise way to create a new list from a data structure。

 This consists of an expression followed by a for loop inside of square brackets， meaning。

 do something for each iteration of the loop and add the result to a new list。

Using list comprehension， let's get the number of albums released in 1974。

So I'm going to create a variable。Albums，1974 equals a list。

Then I'm going to start with my for loop for each row in the albums list。Followed by a condition if。

😔，Year column， notice that's in square brackets as well。 If that is set to the string1974。

 then we're going to proceed that with the element we want to add to the list。

And then we'll print the length of that list。 So we'll print。 We'll say number of albums in 1974。

Will be the length of albums underscore 1974， which is our new variable， storing our new list。

So for each album or row in the album's list， if the year is 1974 append it to a new list。

 we'll call that list albums 1974。 and then we're just going to print the length of that list。

Let's run our code。There are 14 albums released in 1974。 Now。

 let's print the albums released in 1974， along with the artists。We'll use a for loop。For each album。

In Als，1974。Let's print from the album， the album。Column or the value in the album column。And。

From the album， let's get the value in the artist column， printnt that。

So for each album in albums 1974， print the album title and print the artist。Let's run our code。

 we could see here for each album， the album title， and then the artist。Album title and the artist。

What if we only want to list 10 of the albums released in 1974 to go ahead and scroll down。



![](img/ad6786a85e8551a7b06284eeddded9c1_17.png)

So we're going to use list comprehension and then get a slice of our data。So we're going to print。

A list， we're going to use list comprehension。 So for each row in the albums list。

If the year of the album。Should be uppercase。Is set to 1974。Add the row or the album to our list。

 And then from that list， let's get a slice。We'll use our slice syntax from the beginning of the list to index 10。

This gives us the first 10 albums on our list of albums from 1974。

For each row or album in our list of albums， if the year of the album is set to 1974。

We're going to add the album。To our new list。 and then we're going to take a 10 record slice from that list and print it。



![](img/ad6786a85e8551a7b06284eeddded9c1_19.png)

Let's print the album， artist， genre， and release year for albums in the rock genre and in the pop rock or fusion sub genre。

And to do this， we should remember that the sub genre column contains a list of values。

 We can use list comprehension。 Let's start by creating a variable。 Rock albums equals a list。

Then we'll start with our for loop for each row in albums， which is the list of all albums。

 Then our condition， if the。Gre for the row。Or the album is equal to rock。 That condition is true。

 and the following condition is true。Pop rock。Is in the sub genre。Column， that's a list。Or。Fusion。

Is in the sub genrere column。Then we're going to append the row to the list。So again。

 how does this work。For each row in albums， if the genre is rock and pop rock is in the list of sub genres or fusion is in the list of sub genres。

 then add the row to the list。Then for each of these albums， we're going to print the album name。

 the artist， the genre and the sub genre。So let's iterate with a for loop for each album in rock albums。

We're going to print from the album， the album name。And then we're going to print the。Artist。😔。

And we're going to print the genre。And we're going to print the subgen。Let's run our code。

 and here we see for each of those rock albums where the genre is rock or the sub genre is pop rock or fusion。

 We have the album name， the artist， the genre， and the subgen。



![](img/ad6786a85e8551a7b06284eeddded9c1_21.png)
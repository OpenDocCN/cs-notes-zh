# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p94 094_04_06_代码练习-成绩考勤簿.zh_en -BV13E421M7FF_p94-

Let's do an exercise。 We're going to create a great attendance book for our teacher's students。😊。

And it's going to contain a dictionary of dictionaries。



![](img/503acde6669ea7ded2286aff59887689_1.png)

So we're going to start by creating a dictionary for each student。So for Billy。

We'll have a dictionary where the key is the name。And the value。Is Billy。K is grades。😔。

And the value is a list of grades，100。80，67。100。😔，89。And then， the key is attendance。And the value。

Is a list of Boolean values， true。True。😔，Chu。😔，True， true， perfect attendance。

 The other students will have a similar format in their dictionaries。

Soll create a dictionary for Sarah。Name。Sarah。😔，Gres。😔，Here's the list。0，99。0。😔。

100 kind of all over the place。Attendance。True。😔，False。😔，True。😔，False。😔，True。Finally。

 third student Ben。Create a dictionary name。Has been。Greeds。😔，60。😔，82。😔，71。😔，92。Hundred。

then attendance。False。😔，False。Fals。😔，False， false。 Not good。

Now we're going to add each student to another dictionary using a unique student ID for each student。

 so students。Will be another dictionary。 The key will be one， the string one。And what's the value。

 the dictionary for Billy。2。😔，What's the value the dictionary for Sarah。3， what's the value。

 dictionary。For Ben。

![](img/503acde6669ea7ded2286aff59887689_3.png)

Save that。Get the length or number of students。

![](img/503acde6669ea7ded2286aff59887689_5.png)

Get number of students。So we can actually get the length of the student's dictionary。

 This is actually the number of keys。And we'll print that。There are three students。

 No surprise there。We can get all the student Is or just the keys。

 So get all student Is for the student dictionary。 We're going to call the keys method。

 This gets all keys in the dictionary。

![](img/503acde6669ea7ded2286aff59887689_7.png)

![](img/503acde6669ea7ded2286aff59887689_8.png)

We'll go ahead and print that。 It's actually going to return a di keys object， containing the keys。

Dick the keys object， and what are the keys， 1，2， and3。



![](img/503acde6669ea7ded2286aff59887689_10.png)

We can also just iterate over the dictionary to get the keys， so iterate over students。



![](img/503acde6669ea7ded2286aff59887689_12.png)

So four key in students。Let's print。I say key。Okay， this will print just the keys。😔，Let's run that。

 What are the keys，1，2， and 3。Let's get Billy's attendance。Okay， so get Billy's attendance。Okay。

 so let's go ahead and get the dictionary associated with the first key in students。K 1。

 that's actually gonna be Billy。 right， That'll be his dictionary。 And then let's print。

From the Billy dictionary， the value associated with。The attendance key。Here's Billy's attendance。

Let's get Sarah's grades。 Get Sarah's grades。So from the student's dictionary。

 let's get the value associated with the key two that will be Sarah's dictionary。



![](img/503acde6669ea7ded2286aff59887689_14.png)

And then we're going to print from Sarah。The value associated with the key grades。



![](img/503acde6669ea7ded2286aff59887689_16.png)

Those are Sarah's grades。Now， let's get all the key value pairs associated with Ben。Get all。

Key value pairs for Ben。 How do we get Ben， So from the student's dictionary。

 get the value associated with key 3。 This is going to be Ben's dictionary。



![](img/503acde6669ea7ded2286aff59887689_18.png)

![](img/503acde6669ea7ded2286aff59887689_19.png)

![](img/503acde6669ea7ded2286aff59887689_20.png)

Then for Ben， we're going to call the items method。

 And this basically returns a sequence of tuples where the first item is the key。

 The second item is the value。

![](img/503acde6669ea7ded2286aff59887689_22.png)

![](img/503acde6669ea7ded2286aff59887689_23.png)

We'll call these items， and then we can iterate over those items。 So for。Ki。And value in items。

Let's print the key and the value。This is Ben's information， name， Ben grades， list of grades。

 attendance， list of Booleing values。Let's get the average student grade for all assignments。Okay。

 so let's go ahead and get average student grade for all assignments。

So we're going to start by creating an empty list called grades。

Then we're going to get all of the key value pairs associated with students。 So what's the key。

 the student I D and what's the value each student dictionary， So students。Dot items。

We' call those items。And these are key value pairs。For students。

Then we're going to iterate over those key value pairs。 So for key v。In items。Remember。

 the key is the student I D。 The Val or the value in this case is actually the student。

 So let's iterate over the student's list of grades，4 G in。Val， that's the student。

Looking at the grades key， iterate over those grades and then add it to our list。G。

 then we have all of the grades for all students in this list。



![](img/503acde6669ea7ded2286aff59887689_25.png)

Then let's go ahead and print。 We'll get the sum of the grades will divided by the length。

Of the grades。 And just for fun， let's go ahead and round it off。So， this is average grade。

To run that。Average grade for all assignments is 69。



![](img/503acde6669ea7ded2286aff59887689_27.png)

And there's an even easier way to do this。 We're actually just going to concatenate the lists of grades。

 So let's go ahead and。

![](img/503acde6669ea7ded2286aff59887689_29.png)

Do with this another way， another way to do this。 We'll start by creating grades concateated。

 That's an empty list。 So we're starting the same way。

 Then we'll get the key value pairs associated with the students。 So students dot items。Right again。

 this is key value pairs for students。 What are the keys the student I Ds， What are the values。

 the student dictionaries， We'll call that items。 We're going to iterate over those。

 So for each key value in items。We're then going to get just the list of grades for each student。

And we're going to add it to our grades concateated list。 So for each student， that's the value。

 Get the grades。There's the key。 I want to get the value， which is the grades。

 We're going to add this list of grades to this list。 We can add lists。

 and all it really does is append those values to the end of the list。So concatenate list of grades。



![](img/503acde6669ea7ded2286aff59887689_31.png)

And then we're going to actually just print the average in the same way。



![](img/503acde6669ea7ded2286aff59887689_33.png)

Except we're gonna use。Gras concateated， and grades concateated。We'll run that。



![](img/503acde6669ea7ded2286aff59887689_35.png)

Again， the average grade for all assignments is 69。



![](img/503acde6669ea7ded2286aff59887689_37.png)
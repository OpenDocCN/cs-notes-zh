# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P15：14_字符串数据类型.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

You probably already know that when you create a table in a database。

 you must define the column names and the data type of the content that will reside in those columns。

You can use a string data type to define a column's data type。

 particularly in instances when it accepts both numeric and text characters。

In this video you'll explore the string data type and by the end of the video。

 you'll be able to explain the string data type in a database and differentiate between Cha and VCha data types。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_1.png)

When you create a table in a database， it is important for data integrity to ensure that only valid values are inserted in your table。

 for example， you should use string data type when you intend to store data that contains a mix of character types。

So if you define a column as a string， then any type of text can be inserted。

 this includes alphabet characters， numeric characters， and special characters。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_3.png)

![](img/6efa610b7db5e5fe8d98981bbe7f5968_4.png)

Let's explore an example to find out more about how string data types work。

Let's take the example of a student table from a college database this table stores student login information for the college's online portal。

 it stores this information under the following four columns， student name， username。

 password and email address。The student name column contains only alphabet characters。

 the username column contains alphanumeric characters。

 and the password and email column contains a mix of character types。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_6.png)

String data type is a generic term used for different string data types in the database。

The most used string data types are ChaHR， which stands for character。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_8.png)

This data type is used to hold characters of a fixed length。

 and varchar stands for variable character。 This holds characters of a variable length。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_10.png)

Let's explore these string data typess further CharR means that the given length of the characters is predetermined。

It can't be changed after decoration。Coolum attributes are defined as char followed by a character length in parentheses。

 for example， chaR 50 means that a column only permits 50 characters of space in each field。

Chahar is the best option if you' have a predefined size of character that you want to maintain。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_12.png)

In the student table， you can set a maximum length of 50 characters for the username。

 column in SQL with Cha 50。For example， the table contains the records for a student with the username Mark 123。

 which is a total of seven characters， however， because the column is defined as Cha 50。

 this username occupies the length of 50 characters within a space。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_14.png)

The Varchar data type works in a similar way to char， whoever it is a variable length。

 This means that the length can be changed， it's not fixed。

Varchar is often used when you're not sure how many characters might be inserted in the column field。

 so you can type varchar 50 in SQL to allow for any input up to a maximum of 50 characters。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_16.png)

In the student table example， the student name column would most likely contain names of varying length。

 so you could define the student name column as varchar 50 in SQL。

This means that the name of each student only occupies as much space as there are characters in their name。

For example， Mark Simpson occupies far less than 50 characters。

 but this field could hold a name up to the value of 50 characters if required。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_18.png)

Finally， let's briefly explore some more commonly used examples of string data types。

Tiny text is used to define columns that require less than 255 characters， like short paragraphs。

Text is used to define columns of less than 65，000 characters like an article。

Medium text defines columns of 16。7 million characters， for example， the text of a book。

 and the long text data type stores up to 4 gigabtes of tax data。



![](img/6efa610b7db5e5fe8d98981bbe7f5968_20.png)

You should now be able to explain the string data type as used in a database and you should also be capable of differentiating between string data types。

 including ChaR and Varchar。Great work。
# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P83：15_使用Python访问MySQL函数.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

As a database engineer， you can use date and time functions to extract time and date values from a database and you can perform similar tasks using the functions available in Python's native D time library。

In this video， you'll learn about the different date time functions available in Python and how you can make use of them。

😊，Little Le has received several bookings from guests for to night。 However。

 the restaurant has encountered a scheduling conflict。

So they need to push each booking slot forward by one hour。

Python's date time functions are a great way to solve this problem。

Find out how daytime functions work， then help little lemon to update their booking slots。



![](img/443a3edda57dc61ada8b786d3b286ee8_1.png)

Let's begin with an overview of daytime。Daytime is a Python class with several built in functions that can be used to format and change time and date variables。

😊，It's native to Python， so you can import it without requiring Pip。



![](img/443a3edda57dc61ada8b786d3b286ee8_3.png)

Let's review the functions that Python's daytime Library offers。

The date time now function is used to retrieve to day's date。

 You can also use date time date to retrieve just the date or date time time to call the current time。

And the time Dlelta function calculates the difference between two values。



![](img/443a3edda57dc61ada8b786d3b286ee8_5.png)

Now， let's look at the syntax for implementing daytime。To import the daytime Python class。

 use the import code followed by the library name。Then use the as keyword to create an alias of Dt。

You can now use this alias to call the library instead of typing date time every time you need to use a function。



![](img/443a3edda57dc61ada8b786d3b286ee8_7.png)

You now have a daytime object created within your Python environment。

So let's find out how to make use of its functionality using the datetime now function。😊。

Begin by creating a variable called current time。 Next， type the D T alias as the module name。

Then use it to call the datetime now function。Finally。

 instruct Python to print the current date and time values。



![](img/443a3edda57dc61ada8b786d3b286ee8_9.png)

Execute the code to print the time and date of your location。Python returns the date。

 and then the time。The data is displayed in year month day formatash。The time is displayed in hours。

 minutes， seconds format。 But what if you just need to know the current time。

 or maybe you just want to day's date。 You can use the same code again。 But this time。

 give Python two separate print instructions。The first instruction tells Python to print the current date。

 and the second instruction tells Python to print the current time。When the code is executed。

 Python displays each value separately。Let's look at a slightly more complex function， time Delta。

When making plans， it can be useful to project into the future。 For example。

 what date is this same day next week， You can answer questions like this using the time Delta function to calculate the difference between two values and return the result in a Python friendly format。

So to find the date in seven days time， you can create a new variable called Week。

Type the DT module and access the time delta function as an object instance。

Then passed through seven days， as an argument。Finally。

 instruct Python to print the results of the variable。 When executed。

 Python returns the value of the date one week from now。😊。



![](img/443a3edda57dc61ada8b786d3b286ee8_11.png)

Now that you know how datetime works， let's see if you can help little lemon。😊。

As you learned earlier， little Le have encountered a s in conflict to resolve it。

 They need to push each booking slot forward by one hour。

 You can carry out this task by instructing Python to retrieve the data from the bookings table and then adding one hour to each booking。

Let's assume that little Le have already passed through their login details。

 created a new cursor instance and pointed the cursor at their database。

 Your first task is now to import the day time library so that you can work with date time。😊。

Use the import keyword and import the library using the alias Dt。

 This alias is used for greater efficiency。😊。

![](img/443a3edda57dc61ada8b786d3b286ee8_13.png)

Next， write a SQL select statement to return all data from the bookings table。



![](img/443a3edda57dc61ada8b786d3b286ee8_15.png)

Pass the statement to the execute module from the cursor as a string argument。



![](img/443a3edda57dc61ada8b786d3b286ee8_17.png)

Before entering the loop， Instruct Python to print the column names from the bookings table so that you can view each item in the row。



![](img/443a3edda57dc61ada8b786d3b286ee8_19.png)

You can assign these values to variables and create a new variable called New booking slot that holds the values for the updated time slots。

To add an hour to each time slot， pass an argument of one hour to the time Delta function and then add the function to the booking slot variable。

Finally， instruct Python to print the values for the new booking slots in the form of a text string。

😊，This text string details the values of each booking ID。

 along with its respective of old and new booking slots。

Loop through the results from the query and extract the rows from the booking ID and booking slot columns。

😊。

![](img/443a3edda57dc61ada8b786d3b286ee8_21.png)

As the results show， booking ID is the first value and booking slot is the fourth value。



![](img/443a3edda57dc61ada8b786d3b286ee8_23.png)

You should now be familiar with the different datetime functions available in Python and how you can make use of them。

Working with daytime functions can be difficult， but you've made a great start towards mastering this topic。

😊。
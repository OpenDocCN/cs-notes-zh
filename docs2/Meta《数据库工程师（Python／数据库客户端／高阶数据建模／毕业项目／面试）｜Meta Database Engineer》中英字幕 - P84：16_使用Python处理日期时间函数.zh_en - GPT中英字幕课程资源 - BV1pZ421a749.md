# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P84：16_使用Python处理日期时间函数.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

As a database engineer， you can use date and time functions to extract time and date values from a database。

 and you can perform similar tasks using the functions available in Python's native date time library。

😊，In this video， you'll learn about the different date time functions available in Python and how you can make use of them。

😊，Little Le has received several bookings from guests for to night。 However。

 the restaurant has encountered a scheduling conflict。

 so they need to push each booking slot forward by one hour。

Python's date time functions are a great way to solve this problem。

Find out how daytime functions work， then help little lemon to update their booking slots。



![](img/43307e27fff38c1e54fc72c53f0a82dd_1.png)

Let's begin with an overview of daytime。Day time is a Python class with several built in functions that can be used to format and change time and date variables。

 It's native to Python， so you can import it without requiring Pip。



![](img/43307e27fff38c1e54fc72c53f0a82dd_3.png)

Let's review the functions that Python's daytime Library offers。

The date time now function is used to retrieve to day's date。

 You can also use date time date to retrieve just the date or date time time to call the current time。

And the time Dlelta function calculates the difference between two values。



![](img/43307e27fff38c1e54fc72c53f0a82dd_5.png)

Now let's look at the syntax for implementing daytime。To import the daytime Python class。

 use the import code followed by the library name。Then use the as keyword to create an alias of Dt。

You can now use this alias to call the library instead of typing date time every time you need to use a function。



![](img/43307e27fff38c1e54fc72c53f0a82dd_7.png)

You now have a daytime object created within your Python environment。

So let's find out how to make use of its functionality using the datetime now function。😊。

Begin by creating a variable called current time。 Next， type the D T alias as the module name。

 Then use it to call the date time now function。Finally。

 instruct Python to print the current date and time values。



![](img/43307e27fff38c1e54fc72c53f0a82dd_9.png)

Execute the code to print the time and date of your location。Python returns the date。

 and then the time。The date is displayed in year month day formatash。The time is displayed in hours。

 minutes， seconds format。 But what if you just need to know the current time。

 or maybe you just want to day's date。 You can use the same code again。 But this time。

 give Python two separate print instructions。

![](img/43307e27fff38c1e54fc72c53f0a82dd_11.png)

The first instruction tells Python to print the current date。

 and the second instruction tells Python to print the current time。When the code is executed。

 Python displays each value separately。😊。

![](img/43307e27fff38c1e54fc72c53f0a82dd_13.png)

Let's look at a slightly more complex function， time Delta。When making plans。

 it can be useful to project into the future。 For example， what date is this same day next week。

 You can answer questions like this using the time Delta function to calculate the difference between two values and return the result in a Python friendly format。

So to find the date in seven days time， you can create a new variable called Week。

Type the DT module and access the time delta function as an object instance。

Then passed through seven days as an argument。Finally。

 instruct Python to print the results of the variable。 When executed。

 Python returns the value of the date one week from now。😊。



![](img/43307e27fff38c1e54fc72c53f0a82dd_15.png)

Now that you know how daytime works， let's see if you can help little lemon。😊，As you learned earlier。

 little Le have encountered a scheduling conflict to resolve it。

 they need to push each booking slot forward by one hour。

You can carry out this task by instructing Python to retrieve the data from the bookings table and then adding one hour to each booking。

Begin by creating a connection between the front end Python client and the back end database。

 Then pass through your login details。This creates a new cursor instance and points the cursor at the little Lemon database。

😊，Before you can begin working with datetime， you first need to import the daytime library。

Use the import keyword and import the library using the alias Dt。



![](img/43307e27fff38c1e54fc72c53f0a82dd_17.png)

This alias is used for greater efficiency。Next， write a SQL select statement to return all data from the bookings table。



![](img/43307e27fff38c1e54fc72c53f0a82dd_19.png)

Passt the statement to the execute module from the cursor as a string argument。

Before entering the loop， Instruct Python to print the column names from the bookings table so that you can view each item in the row。



![](img/43307e27fff38c1e54fc72c53f0a82dd_21.png)

You can assign these values to variables and create a new variable called new booking slott that holds the values for the updated time slots。



![](img/43307e27fff38c1e54fc72c53f0a82dd_23.png)

To add an hour to each time slot， pass an argument of one hour to the time Dlta function and then add the function to the booking slot variable。

Finally， instruct Python to print the values for the new booking slots in the form of a text string。

😊，This text string details the values of each booking ID along with its respective of old and new booking slots。

Loop through the results from the query and extract the rows from the booking ID and booking slot columns。



![](img/43307e27fff38c1e54fc72c53f0a82dd_25.png)

As the results show， booking ID is the first value and booking slot is the fourth value。



![](img/43307e27fff38c1e54fc72c53f0a82dd_27.png)

You should now be familiar with the different datetime functions available in Python and how you can make use of them。

Working with daytime functions can be difficult， but you've made a great start towards mastering this topic。

😊。
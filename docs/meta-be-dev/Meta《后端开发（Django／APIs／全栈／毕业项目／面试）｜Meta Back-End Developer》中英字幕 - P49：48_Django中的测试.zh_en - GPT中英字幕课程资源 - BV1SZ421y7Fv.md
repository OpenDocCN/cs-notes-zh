# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P49：48_Django中的测试.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Testing is an important component in the software development lifecycle。

While debugging is more driven towards removing the application's errors and bugs。

Testing considers metrics for quality， reliability and performance。

It effectively saves a lot of time for the developer。

Every language and framework has many testing options。

 and developers make appropriate selections based on the project's requirements。

Many testing packages and tools work well with Django。A popular method is unit testing。

 which you can use to isolate a function， class or method and only test that piece of code。

When working with unit testing， you need the following baseline information。First。

 the test targets granular features in your code。The smallest possible testable units。

Then the output of the test will be pass， fail， or an error。In this video。

 you will learn the concept of testing in Django using an example of the unit Test module in Python。

In Django， the unit Test module uses a class based approach。

You add the tests inside a class that inherits a class called test case from the Dngo test package。

Suppose you wrote a model called Reservation and want to test it first。

 import the test case class that inherits test case。Then import the reservation model。



![](img/782e46c284697cff0c8ce8d911fc627c_1.png)

Once you create the tests， use the command Python 3 manage dot Pi test。Additionally。

 you can add specific configurations to run all tests within a specific package， for example。

Run the command， Python3 manage。 Pi test reservationations。To run a specific test case。

 use the command Python 3 manage。 Pi test reservationservations。t。 reservationservation test case。

Or suppose you want to run a specific test method inside a test case。 for example。

 a method to calculate the seat count。You can run the command like Python 3 manage。

pi test reservationservations。t。reservationtest case。t seat count。



![](img/782e46c284697cff0c8ce8d911fc627c_3.png)

It's important to know that developers generally add these test cases under one or more files created under specific app folders。

In a small project， it's common for developers to name the file tests。 Pi。

In large projects that may contain multiple test files。

 it's common for developers to use names like Test modelsels。pi and Testviews。 Pi。



![](img/782e46c284697cff0c8ce8d911fc627c_5.png)

Okay， now you know about the concept of testing in Django。

Let's open VS code and explore an example to create a unit test。

Earlier you learned how to use unit tests in Python to test code In this example。

 you will explore how Djangle uses the unit Test module with the test case package。

Let's explore how you can test the model data inside a Django application using a test case。

Notice that the project is already created and the app configuration is set up inside the Settings file installed App list。

In this example， you will work with two files， models。pi and Test。pi。Inside Models。pi。

 you create a model and add the test code inside the Test。pi file。

If either of these files does not exist， you can create them inside the MyApp directory。😊，So first。

 you add a model inside the Models dotpi file。This model will record the first name， last name。

 and the booking time for a reservation a customer makes at the Little Lemon website。

The auto now field inside the booking time logs the system's current time and is set to true。Next。

 save the file and go to Test DiI。Notice that the test case module inside the Django dot test package has already been imported。

Additionally， you must import the required package called date time。

You also must import the model that you must use， which is the reservation model。

The next step is to create a class called Reservation model Test and inside it past the test case。

Next， you add a setup test data class method and pass a class object inside it。

Setup test data is a method present inside the test case that you use to add data inside the model。

So in this example， data is entered for the first name and the last name。

It is important to note that booking time automatically updates as the auto now parameter is set to true。

Next， you create a function called as test fields to check if the first name and the last name that I received are in a string format。

You perform the check using theAser statements to check both the first name and last name are of the string data type。

Similarly， you must create another function called as test_ timestamps。Inside this function。

 you insert another assert statement， such asAst instance。And this time。

 compare the booking time to the imported date time。Okay。Once this ch is ready。

 you must run the migrations since you have a newly created model。😊。

The final part of this step is to remember to add the class method decorator。

Since this is a class method。😊，Now save the file。With this code complete。

 you are now ready to run the tests by typing Python 3 manageage。P test in the terminal。

Press enterter and notice that the application ran and passed two tests。

The running of the tests is represented by the two dots displayed in the terminal。Back in the model。

 let's change one of the fields from string to int to see if the test produces a different result。

So save the file and run the test one more time。Notice that one of the tests has failed。



![](img/782e46c284697cff0c8ce8d911fc627c_7.png)

Additionally， an assertion error is displayed， stating that the last name you have assigned is not an instance of an integer class。

The asserttation error is also indicated by the characters F dot。

 which means that one of the tests has failed and the other one has passed。

If you are familiar with using unit tests in Python。

 notice that the implementation is similar to that which you will find in conventional Python code。

This example demonstrated how to implement a basic test in jjangle。

Jango as a platform and framework is pretty huge。So it's important to remember that many testing configurations and options are available to be explored by the developer。

In this video， you learned about the concept of testing in Django。

 using an example of the unit Test module in Python。


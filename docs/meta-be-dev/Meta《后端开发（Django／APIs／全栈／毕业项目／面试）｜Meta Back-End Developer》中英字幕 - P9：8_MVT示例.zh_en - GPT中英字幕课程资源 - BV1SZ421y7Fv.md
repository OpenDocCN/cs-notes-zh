# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P9：8_MVT示例.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

You've already learned that Django projects can get quite large。

 I understand that for an aspiring developer it's easy to get intimidated as Djago projects can have many moving parts。

In this video， I'll give you a broad overview and demonstrate how Django organizes a project using models。

 views， and templates， commonly known as the MVT architecture。



![](img/eeff767a48f8f793c4acd05a8ae1d663_1.png)

Don't worry if you don't fully understand all the concepts in this video as you'll be learning all about them soon instead。

 please focus on the concept that the data， logic and display are separated in the Jjango framework。

You can even think of this video as a sneak peek into the future of how developers use the Django framework in backend development previously I created a folder calledBuilding MVT If I expand it notice that I've created a virtual environment called tutorialial EMV I also created a project called Chef's Table and installed Django in that project。

Inside the Che's tableable project， notice that I created an app called Little Lemon and notice that Django has automatically created the associated files for the project and the app。

Before I demonstrate the files of the MVT architecture， I first need to update the URLs。

pi file in two places so that Django can match the different URLs to the correct view。

In these files I've added the URLs that will invoke the view functions。

Now I will demonstrate the concept of the MVT architecture by using three examples the first example will contain only views Next will be an example containing models and views Finally。

 there'll be an example with models， views and templates。

Let's begin with the first example that only contains the view if you open the file views。pi。

 notice it contains a Python function that sends some data to a web page that runs on the development server on a local host In this example the data returned as the text Hello world。



![](img/eeff767a48f8f793c4acd05a8ae1d663_3.png)

Let me demonstrate this now by launching the development server。

 I open the URL in the browser and notice the text Hello World displays。



![](img/eeff767a48f8f793c4acd05a8ae1d663_5.png)

Okay， let me close the browser window and quit the server For the second example。

 I've made some code changes to demonstrate how views can work with the models notice that I created another function in the View p file This function communicates with a model to retrieve data stored in a database table and then dynamically returns it to the web browser Let's now explore how a model communicates with a database and open the model p file notice that this code contains a Python class which represents a table in the database and each of the variables created acts like a column in that table。

If you're familiar with the concept of relational databases， you might wonder how this is possible。

 for now， just know that Django maps the code in the class to a corresponding table stored in the database。

Okay， let me run the server again。This time when I go to the URL。



![](img/eeff767a48f8f793c4acd05a8ae1d663_7.png)

The output will display the text pasta type of Italian cuisine。

Jengo dynamically fetched the text from a database table based on the numerical value sent in the URL。

And this corresponds to some entry in the table。At the moment it has the value of one。

 if I change this from one to two， notice that different text is output to the browser。

This is possible because of the logic created in the views。pi file For the final example。

 I need to modify the view to return a template I created inside the app folder。

 Not that if I expand this folder， it consists of a file called menucard H。



![](img/eeff767a48f8f793c4acd05a8ae1d663_9.png)

The file contains three HTML elements with some basic styling。In this final example。

 I have not made any other changes except adding a template and modifying the ViewSt P file。

If I open the web page again and refresh the page， the output will display with the HTML and CSS applied。



![](img/eeff767a48f8f793c4acd05a8ae1d663_11.png)

The format and style will be applied to all the pages where I've made the changes it's important to note that while this output may seem basic。

 the concept is very powerful by splitting the data， logic and display into MV and T。

 developers can rapidly create large scale data driven applications。

The MBVT architecture allows developers to easily update the database， logical code， presentation。

 and styling to create dynamic web applications。While the number of files present inside your project folder may seem intimidating。

 you'll explore these files when you need them throughout the remainder of this course。

And as I said at the start of the video， you will soon explore this MVT concept in greater detail it's also worth remembering you're already familiar with the code you'll be dealing with as it's primarily Python。



![](img/eeff767a48f8f793c4acd05a8ae1d663_13.png)

In this video， you learn how Django influenced the model， view and template， or MT architecture。



![](img/eeff767a48f8f793c4acd05a8ae1d663_15.png)
# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P30：29_表格.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

The majority of web applications need to collect data from end users。



![](img/d0c830a24aedc476197bebac5b62929d_1.png)

This can be anything from user details for login and authentication。

 registration details for a new application， or order details for online shopping。



![](img/d0c830a24aedc476197bebac5b62929d_3.png)

Recall that web applications use forms to collect data input from users using HTML form tags。

Any form elements such as inputs or check boxes are sent to the server for processing when the form is submitted In this video。

 you will learn about forms in Django and how developers use the form class to automatically generate HTML for elements from classes。

 You will also learn how developers can use models to automatically generate forms to remove potential processing errors In Django。

 the most common form submission is a post request which will send the data down in the post body。

The server side code handles the incoming request and processes the data on the back end。

 for example， suppose you create a basic form using HTML to submit a name。

You can use a label to display text describing what the input should have the input set to type text accepts input from the end user。

In this example， the input stores their name。The second input of T submit is a button that displays the text S name When the button is pressed。

 the action will be triggered to make a post request to be processed by the order view。

And this is all defined in the form action and form method attributes。😊。



![](img/d0c830a24aedc476197bebac5b62929d_5.png)

While this process works well， the code can become tedious and complex when dealing with large forms。

 for example， forms can have many different ways of gathering data with conditional flows。

 also designing forms in this way can lead to errors as each form elementss name or ID attribute needs to match what the backend code expects。



![](img/d0c830a24aedc476197bebac5b62929d_7.png)

![](img/d0c830a24aedc476197bebac5b62929d_8.png)

To assist developers with form creation and processing， Django uses a form class。

In this class you can define all the expected attributes that will be passed down in the request。

 this means that you can use a form class to represent the expected attributes and render the form elements in the HTML。

For example。The Subbitit name form can be represented by creating a class。

Let's step through this code line by line。First， you create a class called name Form。

 which accepts a parameter of forms。form。This is essentially what has been passed in the form itself。

Next， you create a variable called your name， which is assigned formss。

car field to represent the HTML input element。Notice that you also can set some validation by setting the max length value to 100。



![](img/d0c830a24aedc476197bebac5b62929d_10.png)

Finally， when the name form class is rendered， it's rendered to a view containing the HTML form code。



![](img/d0c830a24aedc476197bebac5b62929d_12.png)

It's important to know that the form tags are not represented。

 so you need to add the form tags and then use the templating to append the form elements inside。



![](img/d0c830a24aedc476197bebac5b62929d_14.png)

Don't worry too much about the concept of templulating， you will learn about it soon。For developers。

 the advantage of creating forms in this way makes it much easier to manage any changes to the form。

Instead of worrying about the names on inputs， matching with the server side code。

 this is handled entirely by the forum class。

![](img/d0c830a24aedc476197bebac5b62929d_16.png)

Also， because you are working with classes， you get all the benefits of object oriented programming。



![](img/d0c830a24aedc476197bebac5b62929d_18.png)

For example， you can split complex forms into sub classes to make them more manageable unfortunately。

 learning about these features is outside the scope of this video， but it's good to know they exist。



![](img/d0c830a24aedc476197bebac5b62929d_20.png)

And if you would like to learn more， there is an additional reading at the end of this lesson。

 lastly， let's explore the use of forms with models in D Janngo。😊。

Sending data to the back end using the post method requires you to persist the data somehow。

 for example， suppose you are setting up a new user to gain access to your site。

You will need to persist their details such as email and password and some general user information such as name or address。



![](img/d0c830a24aedc476197bebac5b62929d_22.png)

![](img/d0c830a24aedc476197bebac5b62929d_23.png)

Luckily， developers can solve this by using models。



![](img/d0c830a24aedc476197bebac5b62929d_25.png)

A model in your application will represent the table to store this information。

 so the model itself can then be used and be directly converted into ajanangle form。

This makes sense as you want your forms to map to what you need to persist。

And this feature is excellent for ruling out any potential issues or errorss。



![](img/d0c830a24aedc476197bebac5b62929d_27.png)

The code for the model form is placed in the file forms do Pi and implements the structure of the model。

 and you will learn more about both form types in more detail later in this lesson。



![](img/d0c830a24aedc476197bebac5b62929d_29.png)

In this video， you learned about forms in Django and how developers use the form class to automatically generate HTML for elements from classes。

You also learned how developers can use models to automatically generate forms to remove potential processing errorsRS。


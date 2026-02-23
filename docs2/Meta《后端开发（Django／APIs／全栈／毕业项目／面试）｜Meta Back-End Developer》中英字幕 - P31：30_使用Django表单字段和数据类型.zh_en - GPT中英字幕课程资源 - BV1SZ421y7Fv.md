# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P31：30_使用Django表单字段和数据类型.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Often web applications collect data from the user through a HTML form。

 and it's sent to the server for processing。You create a H form using various form elements。

 such as input elements， radio buttons， drop down lists and check boxeses。 In this video。

 you will learn how to use form fields to store correct data types in Django。

 Suppose the manager of little Le has asked you to build a customer form containing a customer's name and H。

First， you build a HTML form that contains three input elements。One for the name， one for age。

 and one for the submit button。Previously， you learned that Djangle creates and processes forms using the form class This class defines all the expected attributes that will construct and process the form Once you lay out the structure of the form。

 form fields are the building blocks that help build the form。

While fields are an integral part of models， they are especially important while using forms as they help define the visual element of the form。

The custom logic behind the fields is defined in the fields class used inside the form class in Django when defining attributes you can choose from various field types。

 Let's explore some of these briefly now。First is Car field。

 which accepts any string input and is equivalent to the text input element in HTML。

 next is email field， which accepts input that follows email format。

 Its equivalent to the email input element in HTML Integer field accepts only integers and is equivalent to the number type input element in HTML。

Multiple choice field offers the choice of multiple options。

 It's equivalent to the select and option elements in H。 Finally。

 file field allows you to choose a file for upload and is equivalent to the file type input element in Hm。

Additionally， these form fields have different arguments that can be passed to them。

 while specific arguments that can be passed vary according to the field in use。

 there are a few core arguments that are accepted in common among all the fields。

These are required label， initial and help text， Let's explore each of them now in a little more detail。

Required， each field assumes the value is required by default；

 you can change this by setting required equal to false。

Label the argument helps specify a label for the field。

Initial initial values can be set for specific fields。Help text。

 specify descriptive text for the field。

![](img/a4490ba5e18f2dfc52e80231763fa5da_1.png)

It's important to remember that every forum that you build will have different data requirements。

For example， a customer feedback form or a survey style form for a customer's favorite menu items。

Knowing what field type to use is essential to building effective forms。

Let's open VS code now and explore the different fields that can be used to create a form and the customization options available。

The Django project is set up with a file called Forms。 Pi created。

And notice that the file imports the forms package。

Now let's begin by creating a form and exploring the different form fields available with it。😊，First。

 you create a demo form that will contain a car field。

Let's explore this form in the browser and notice that Django creates the label name in the form。

This name comes from the value of the attribute that is defined。If you change this。

 it will update on the form。You can edit the form further by passing a parameter such as a widget with the value formss。

t text area。This text area will override the default widget for it。

 which is the equivalent of rendering the input field present in HTML code。



![](img/a4490ba5e18f2dfc52e80231763fa5da_3.png)

![](img/a4490ba5e18f2dfc52e80231763fa5da_4.png)

If you refresh the page again， notice the form is updated。Okay， so the code works。

 but suppose you want a smaller text area to display。You can pass a parameter inside the text area。

 such as attributes with a certain number of rows。

![](img/a4490ba5e18f2dfc52e80231763fa5da_6.png)

Apply this update， save the file and refresh the browser。



![](img/a4490ba5e18f2dfc52e80231763fa5da_8.png)

Notice that the text area is smaller with space for five rows。



![](img/a4490ba5e18f2dfc52e80231763fa5da_10.png)

Next， let's explore the email form field。Replace this code with email equal to Forms。

e field and save the file。

![](img/a4490ba5e18f2dfc52e80231763fa5da_12.png)

Refresh the page and notice the form updates with an input for the email form field。

It's also important to note that Django form fields have basic validation applied by default。

 for example， suppose I enter an invalid email address and try to submit the form。

Notice that an error is displayed， stating that you must enter a valid email address。

If you add a valid email address and press the submit button again。

 notice that the form does not display an U。

![](img/a4490ba5e18f2dfc52e80231763fa5da_14.png)

To help the user know what to add in each form field， you can use the label parameter。For example。

Add a label parameter with the text to enter an email address。



![](img/a4490ba5e18f2dfc52e80231763fa5da_16.png)

Save the code and refresh the page。Notice that the label now displays in the form and replaces the default attribute value。



![](img/a4490ba5e18f2dfc52e80231763fa5da_18.png)

Let's now explore another example using the date field。😊，Inside the code。

 you can use a widget called numberumb input that requires additional input from formss。wiidget。

Suppose you want the customer to enter a date in the date field for a reservation date at Little Lemon。



![](img/a4490ba5e18f2dfc52e80231763fa5da_20.png)

If you save the file and refresh the page， notice that the reservation date displays。

 you can click on it to open a calendar and select a specific date。😊。

One last example that you can explore is the choice field。



![](img/a4490ba5e18f2dfc52e80231763fa5da_22.png)

This example uses a constant to be passed as a parameter inside the choice field。

The values saved in the constant allow customers to select their favorite dish at little lemon。

Once again， save the file and refresh the page in the browser。



![](img/a4490ba5e18f2dfc52e80231763fa5da_24.png)

Notice that there is a drop down menu for the choices。



![](img/a4490ba5e18f2dfc52e80231763fa5da_26.png)

However， suppose you want to display all three choices simultaneously。

You can achieve this by using another widget option with the value of Radio Select。



![](img/a4490ba5e18f2dfc52e80231763fa5da_28.png)

Save and refresh and notice that the choices are now visible as radio buttons that the user can select。



![](img/a4490ba5e18f2dfc52e80231763fa5da_30.png)

![](img/a4490ba5e18f2dfc52e80231763fa5da_31.png)

It's important to note that these examples showcase just some of the available form fields and parameters you can use in Django。

 exploring the Dngo documentation for all available options to help you create forms is a good idea。

😊，And you can do this from the link in the additional reading at the end of this lesson。

In this video， you learned how to use form fields to store correct data types in Django。


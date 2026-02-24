# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P32：31_创建表单.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now you should be familiar with the concept that developers use the form class to automatically generate HTML for form elements from classes。

In this video， you will learn how to create a form using the form class in Jjago。

You will also learn how to render a form using a template。Finally。

 you'll explore some of Jingdo's form features such as validation。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_1.png)

Let's begin creating the form first I need to create a file called Formt Pi inside the app directory。

In this scenario， I will create a form on the Little Limon website that allows the employees to log their entry times of work。

In this video I will be only demonstrating how to build the form using the Forms API in Jjango you will learn how to process forms in Jjango later in this course。

The process of building forms of Djago is very similar to creating models。

First I use the import statement to import forms from the JjaNgo module。

Next I create a class called inputput form， which will hold the form and pass it forms。form。

This class needs four attributes， the first two attributes are first name and last name。

 which will be character fields with a max length set to 200。The third attribute is shift。

 which will be a choice field， it will let employees choose between morning。

 afternoon and evening shifts for their work。Inside the choice field。

 I pass the choices as one constant called shifts。Then at the top of the code。

 I assign the value of this constant to an iterable of tus inside a tuple。

I need to add one final attribute called time log， This attribute will log the entry time for a given employee。

So I type forms。time field okay， my code looks good and that's all I require for creating a form。

Let me now switch to the View that pie file and just like I did with models。

 I need to create a view for this form。I do this with the import statement to import the form from the app directory。

Okay， now I'm ready to create a view first I create a view function called Form view。Next。

 I create an instance of a form and pass it to a variable called form。

Then I create another variable called contextt， which is assigned to a dictionary with form as the key and the instance object of input form as its value。

Finally， I pass this variable inside of the render function。

 which will display the output of an HTML page called Home。h。But for this to work。

 I must build a web page by creating a template， so I first create a template folder inside the app。

Next， I create a home。 HTML file and paste the HTML code inside of it。

It's important to remember to use the form method of post as I'm sending the data from the form and creating an object from it。

I've also included a submit button represented by an input field with type and value such to submit to finish this form code。

 I have to add something called a CSRF token， which is simply a way of telling Djago that the form data is safe。

 Finally， I pass the form that I've created。Okay， so my code looks good， let me save all my files。

And before I continue， I ensure I update the URL step high file both inside the app and the project folder。

I also need to update the settings that P file with the reference for the app。

 I'm now ready to run the server in the terminal I type the command Python manage that Pi run server。

I navigate to the local hostst URL and enter the path for the form。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_3.png)

Success， the form displays on the web page with the form elements first name， last name。

 shift and time log。 You may notice that the form does not have any styling applied。

 While I could use some C SS。 I'm not going to just yet。 Instead。

 I want to demonstrate a trick to structure the form elements using paragraph tags。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_5.png)

So back in the fileH。htm， I can modify how the form is rendered by amending the form to form dot as underscore P。

This will tell Janjago to render the form elements as paragraph tags。

 so save this file again and refresh the webpage。

![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_7.png)

Notice that the form elements all appear one after another when I press the submit button。

 notice that Django also provides basic form validation where all the elements are required If I want to change this。

 I can pass a parameter inside the forms file for each attribute I can type required equals false。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_9.png)

So I save the file again and refresh the web page。

![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_11.png)

I press submit and notice that the field first name is not required at this time。Similarly。

 I can pass other parameters。

![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_13.png)

For example， inside the time log， I can type Help Tt equals and then the text enter the exact time。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_15.png)

Once again， I save and refresh and notice the text is displayed beside the time log field。Finally。

 I can open my H M file to add some inline styling to the form Inside the form declaration。

 I add a background color。

![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_17.png)

![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_18.png)

I save the file one more time and refresh it。Notice that the form displays with the background color。

Working with forms can be complex， so developers can use Djago's form functionality to simplify and automate vast portions of this work。

By creating forms this way， developers are guaranteed to add Djainggo's layer of security。

It was not possible to demonstrate how to process and save the form in this video。

 but I hope you're thinking that maybe Django offers similar functionality to process and save forms as it does with creating them and if you're thinking that you're correct and you will learn how to do this soon。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_20.png)

In this video you learn how to create a form using the form class in Django。

 you also learned how to render a form using a template Finally you explored some of Djago's form features such as validation。



![](img/62fbfcb3d62fc9adbeb53c2ecc261e08_22.png)
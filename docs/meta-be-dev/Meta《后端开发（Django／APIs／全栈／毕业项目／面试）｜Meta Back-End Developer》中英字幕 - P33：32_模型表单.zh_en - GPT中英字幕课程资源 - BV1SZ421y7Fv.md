# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P33：32_模型表单.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

So far in the course， you have learned how to create models as well as forms using class implementations by Djangle。

But what if you want to use them together to save entries entered in a form inside a database？

Jngo provides a very efficient way to do that using model form by providing a means to save received data as a response directly to the database。

In this video， you will learn how to use model form。

The process of creating such a model form is similar to that of creating a model and form。

Just like in the case of model and form， Django provides another helper class called model form that helps in an easier implementation。

Let's take an example。Say you want to create a reservation form for the little Le restaurant。

In the example， you first import the model you want to bind with your form。

Then you add implementation details for it using in Me class。 And finally。

 you create an instance of that form。 Note that instead of having separate classes for form and model。

You have just one that inherits the model form and implements it。

 since this is an implementation that involves sending form data back as a response。

 you also need to add some implementation details about the post method inside the view。



![](img/a264a2fcfd7a6524ff15a5fba52f9ef1_1.png)

Let's now examine how you can implement this。😊，Previously。

 you learned that you can use the Form's API to generate a static form using Django。

Just as a reminder， notice the code in the Form。pi file。

And how it is used to render a form in the browser， building on the project that's already in place。

 let's modify the form to use model form this time。 So first to simplify。

 remove the shift's attributes。And since this is a model form。

 copy the contents and paste it inside the Models。pi file。Next。

 you need to reconfigure all the details so that it matches the configuration code for a model。

Notice how the class name changed from log form to logger， which is the name of the model Next。

 let's go to Form dot Pi again， delete the existing content and then create the model form based on the model that is in place so first import the model using from dot model's import logger。

 which is the name of my model。Then type Class log form， which is the name for the model form。

And this time， pass model form inside it。Next， add class metata followed by the name of the model。

 logger， and another attribute called fields， and instead of assigning individual fields。

 let's just enter the value of all， which will import all the fields inside that particular model。

Let's save this file。Next， you must make sure that you register the model for this， go to admin。

pi and update the details。Next， switch to the views。 Pi file。Once inside the view。

 notice that there is already some basic configuration that helps render the form。If you recall。

 the form object， which this time is the model form， is passed inside a context dictionary。

 which is then passed inside the render function。Now。

 you must add some code that will help accept the form data and send it to the model database。So。

 let's add a conditional statement such as if request dot method equal to post。Next。

 add form equal to log form and then pass a requestquest。

 post inside it what this code does is update the form object with the contents opposed inside the request object。

Next， check if the form is valid and if so， save the form using the save method。Let's save this file。

 You already have everything you need in terms of the form template。



![](img/a264a2fcfd7a6524ff15a5fba52f9ef1_3.png)

After you run the migrations， run the server。Go to the browser again and refresh it Next enter the name Kyle McGreor。

And the time，11 minutes past 11。

![](img/a264a2fcfd7a6524ff15a5fba52f9ef1_5.png)

And once you press the submit button， notice that the post method is logged on the console。

In the left panel， you can go to the database， right click on it， and click on Open Data。

Inside SQL Lier Explorer， once you expand it， click on my app underscore Loger。

This is the name of the table created from the model。

 click on it and notice that the entry has been updated inside the database。



![](img/a264a2fcfd7a6524ff15a5fba52f9ef1_7.png)

You can add as many entries as you like， and every time the entry will be added inside the database。



![](img/a264a2fcfd7a6524ff15a5fba52f9ef1_9.png)

This is an example of how the model form can be used to create a form and save the form data to a corresponding database table。



![](img/a264a2fcfd7a6524ff15a5fba52f9ef1_11.png)

In this video， you learned how to create a model form， well done。


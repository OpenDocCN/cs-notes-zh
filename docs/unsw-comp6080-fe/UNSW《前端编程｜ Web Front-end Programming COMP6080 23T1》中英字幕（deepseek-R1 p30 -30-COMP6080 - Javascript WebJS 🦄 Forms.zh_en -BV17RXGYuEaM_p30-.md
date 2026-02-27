# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p30 -30-COMP6080 - Javascript WebJS 🦄 Forms.zh_en -BV17RXGYuEaM_p30-

Hey everyone， it's Anna here and in this lecture we're going to have a look at forms so we're going to have a look at what forms are and how we can write them in HTML and then how we can actually do something with the data that the user inputs in JavaScript。

So basically a form is a type of element on a HTML page or a webp page which allows a user to enter in data。

 so some examples of where you might use this is a survey。

 a login or sign up form or something like a Java application form。

The data that the user enters in can be in different formats like text， numbers， date pick。

 and checkbox or radio buttons， and then the client or the server is able to receive this information which the users entered into the form and do something with it。

So in this lecture， we're going to look at actually making forms in HTMma and then reading the data client side in JavaScript。



![](img/de9ec9acf828c269a97494ae91975815_1.png)

All right， let's dive in。So let's start with how to make a form in HTMma。

And the basis of making a form in HTML is the form element。

So this element is a way of defining a form and inside this tag we put the contents of the form。

 which is usually things like labels so here you can see we've got first name label and last name label and different types of input elements so in this example we have a form tag and it has first name and last name input elements。

Notice that we've specified the type equals text attribute so we can use the type attribute of an input tag to specify the type of that input so some valid attribute values of this attribute are button。

 radio checkbox or email or anything like that， there's plenty of others。



![](img/de9ec9acf828c269a97494ae91975815_3.png)

So we've taken a look at how to write the HTML for a form。

 now we want to be able to read those forms in JavaScript。So firstly， on your web page。

 you might have one form or you might have multiple forms in your document。

 and we want a way of accessing these forms in JavaScript。

So the document object in JavaScript has a property called forms。

 which is where you can find all of the forms in your document， that's how you can access them。

So document dot formss is something called a named collection。

 which means we can index it like an array， and we can find a form using the name of the form。

So looking at the sample code， I can do document。forms。

 test to access the form with the name test and I can also do the same thing by indexing in the list with a string of the name of the form。

 so document dot forms square brackets and the string test also works to get the form with name test。

So just quickly jumping back two slides here in my example form。

 I've provided the form named user for I'd be able to access this form in JavaScriptscript using forms document。

forms。user form。

![](img/de9ec9acf828c269a97494ae91975815_5.png)

![](img/de9ec9acf828c269a97494ae91975815_6.png)

嗯。Cool so lastly I can also just use an index so looking at this last example I've got document doforms zero which gets the first form in the document and the format of document dotform of what we get from this is a HTML collection so kind of like an array of HTML form elements。

Objects of the HTMLt form element Do type。Al right。

 so we just saw how to access the HTML form element once we have the form we also want to know how to get the actual input elements in the form。

 so form elements have a field called elements。And Form dot elements is also a named collection of all the input elements in that form。

So being a main collection， it means just like in our last example。

 we can access elements by both index and by name。Here our house and sample code for a HTML form。

So you can see it has an input for first name or F name， which is a text input。

And that has two radio input buttons which both have the same name age。

 but they have two different values。Then over on the right hand side， we'll have some JavaScript。

So in the JavaScript first， we retrieve the form element via documentcument。forms。

And then just getting the zero form， which is the first and only form on the document。

Now I want to retrieve what the user has typed in for first name or ene， so to do this I do form。ars。

fne。Anding form elements zero， getting zero element would also be valid。

And we actually have a nice shorthand notation for this where you can do Form。f names directly。

 you don't need to always type dot elements， so there's just a shorthand。

So that's how you access the value of an element in a form for something like a radio button。

 so you can see with those radio buttons we have two radio buttons with the same name。

 they're doing form。 elementsments。age is going to return a collection for us。Cool。

 so that's how you can read values from a form。

![](img/de9ec9acf828c269a97494ae91975815_8.png)

One core feature of form elements is back referencing， so when you have a DOm element。

For one of the input elements in a form， this element actually has a form attribute which stores a back reference to the form which it's contained in so you can see in this diagram that we have a form and form has all its children elements。

 the elements that are in it and then each element also references the form that it's contained in。



![](img/de9ec9acf828c269a97494ae91975815_10.png)

Here I just have a little quick example of background referencing。

 so on the left hand side I've got some HTML model with a form and it has one input tag。

If I do document。forms zero， I get this form。And then I can do dot login to get the login element from that form。

 then on that form element。Like the specific element in the form。

 I can do dot form to get the contained form so this line。Consult。log oflogin。

or will give us a variable form。

![](img/de9ec9acf828c269a97494ae91975815_12.png)

Allright， so the last piece of the puzzle， once we get access to an element inside a form。

 we want to be able to read its value what someone's actually typed into the field。

So there's a few way of doing this。You can see in the first line of code for a text input。

 you can just do input dot value and that will give you a string of what was entered。

For something like a checkbox or a radio button， you can do input dot checked。

 which gives us a bullyan of whether that checkbox is ticked or not。

And then a slightly more complex one is a select tag， so a select tag is something like a dropdown。

 so you can do select options which gives you a collection of all the options in that select。

You can do select value which gives use the currently selected option。And you can do selected index。

 which is an index of the selected value into the array of all options。



![](img/de9ec9acf828c269a97494ae91975815_14.png)

So now we've learned how to read what a user has inputed into a form now let's take a look at how we know when a user has submitted a form。

Like how we know when we should run the code when they user access。是 me。So when you make a form。

 you should add a special type of button called a submitm button and when that's flippeded。

 it fire a submit event。So we're able to listen for a submit event in JavaScript。

 so once the form is submitted we can write a call back。

You should listen to the events like Ja to have a better idea of how to add event listeners。

 but here I'm just adding an event listeners platform for the submit event。

And inside there I'm able to run a callback so I can run some fl validation。

 I can do something with the data in this callback。

So now let's take a look at some live coding examples of how to use forms。



![](img/de9ec9acf828c269a97494ae91975815_16.png)

Alright， so now we're going to put together everything we've learned and we're going to make an example form and then write some JavaScript to do something with the data in that form and the form example which we're going to do is a create account form so we want to have a form see someone's sign up for a website or something and needs to print that personal information。

So let's start by making the actual forms tag itself。

 so I'm going to put a form tag and I'm going to give it a name。Co。

Now we'm going to start them in some input fields， so I want one through the username and like maybe their date of birth。

I'm also using the placeholder attribute here， which is the text which grows on the ankle field before anyone type something in it。

So I put in a name field， a username， now I'm going to put in a date of birth field。

So I've used the type equals date attribute， which will make it a date drop down pick field。

And now I want to do a password field。So you can actually do typey equals password and what this does it'll basically work out the word like on any other password entering finger or use dots instead of characters。

嗯。replace place holds up， plays enter your closeword。

I'm going to do another one for confirming your password。2。

Now I'm going to do an example of a select tag， sort like a dropdown。

 and we're going to do this so that the user can select which state they live in。

I'm going to do a select tab， I'm going to put meaning equals state。And then inside the select tag。

 I want to put a bunch of option tags， which is all the options in the select tag。

So this is the value of it in the JavaScript and this is the name which is going to appear on the actual tag。

Finally， I'm going to put a file input so that someone can upload a photo of themselves。

So that's just input type equal file。The last piece of this is to put a submit button so that we can actually run add a submit listener in the JavaScript for when they submit the form。

 so this is just another input type submit。hi will look just like a button。

And the value is what this says on the button。All right。

 so now let's just quickly run this code to see how it looks in the browser。Cool。

 so you can see here I've got normal text fields， a date pick where I can choose a date。

 password fields so when I tracking these shows up with stock instead of letters。

I've got my select drop down where I can choose a state and my submit button。

So now what I want to do is I want to write some code in the driving script so that when I hit the submit button。

 we will just show an alert we're not going to actually try and access the data。

 we just want to add that listener for when we hit the submit button。

So first thing I'm going to do in my JavaScriptscript is I'm going to try and access my form element。

 so I named my form element create account so I'm just going to do that。Sina。

It will document do forms do create account。And now what I'm going to do。

 just like this on the slide， I'm going to add an event list enough for this submit event。

And I'm going to pull back， which takes in benefit bit。そ。Now， inki， I'm just going to do inter。

Which says form submitted。

![](img/de9ec9acf828c269a97494ae91975815_18.png)

All right， refresh this page and I click submit。I'm getting an network same form submitted。

Now you'll notice that when I submit what it does is it creates a request which puts all these values which I entered into the URL now if we don't want this to happen。

 we can just prevent the default behavior of the event so let's open up the code again and event Dr on default。



![](img/de9ec9acf828c269a97494ae91975815_20.png)

![](img/de9ec9acf828c269a97494ae91975815_21.png)

没事。です。系啦哦嗰时间你。So now when I submit。

![](img/de9ec9acf828c269a97494ae91975815_23.png)

I make my life。

![](img/de9ec9acf828c269a97494ae91975815_25.png)

All right， so now when I submit it。I'm no longer getting the URLl friends。All right。

 so now what we want to do is we want to get the values that the user has typed into the form and we want to actually alert these。



![](img/de9ec9acf828c269a97494ae91975815_27.png)

So first I'm going to get the username form， when I call the username， I called it name。

 so I'm going to do。sナ风的 elements的。nameam。And I want to do dot value to get the actual stream value。

From the element。Co， now what I'm going to do is I'm going to get the date that they entered。

 so very similar。I want to get the password one and password two。And now I only to get the file。

 which they entered。So oh， I want to get the state as well。So first。

 I'll hit the file to school photo。嗯。And finally， I want to get the state。Cool。

 so now I've done all the values I'm just going to。I'm just going to alert these in the string。



![](img/de9ec9acf828c269a97494ae91975815_29.png)

I run this again。就为成包意。Cool， so you can see it's consulted below to my name， my date of birth。

 my password both times， the name of the file and my。



![](img/de9ec9acf828c269a97494ae91975815_31.png)

So the last thing I'm going to add is a bit of form verification。

 so we want to make sure that if the user doesn't fill in all the fields that would prompt them to actually fold these in。



![](img/de9ec9acf828c269a97494ae91975815_33.png)

So I'm just going to check the values that I entered。And see if they've been defined。

So here I'm just going to alert that please enter all fields。



![](img/de9ec9acf828c269a97494ae91975815_35.png)

Okay let's try this again。So if I just type in Anna， but I don't feel in the rest。

 so now I'm getting in alert saying please enter all fieldss。



![](img/de9ec9acf828c269a97494ae91975815_37.png)

Now let's also checked to make sure that the passwords match， so I'm going to add another statement。



![](img/de9ec9acf828c269a97494ae91975815_39.png)

Let's try that again。So I' fill in more of the fields。嗯。Make sure to choose this。

 but I'll type in a different policy like page。そうで、すよね。Okay。

 so I'm getting an alert that says passwords don't match。



![](img/de9ec9acf828c269a97494ae91975815_41.png)

So that's the basics of making a form and adding in some really basic form validation in JavaScript so that's the end of this lecture thanks so much for listening that hope you learn something。



![](img/de9ec9acf828c269a97494ae91975815_43.png)
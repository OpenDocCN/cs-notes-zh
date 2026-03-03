# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p90 30_06_03_Django表单数据验证.zh_en -BV1Kt421V7EE_p90-

So now we're going to talk about data validation。 Data validation is what happens when you hit the submit button and then that data is sent the to the server。

 And what the server does is it checks that post data that it's getting to see if it's。



![](img/7d906d29070f7df4d568a84a68e51039_1.png)

Proper according to its rules， so if you go back to this picture I showed you in the create form。

 the part we're talking about now is really this part right here。

Where the user has entered their data， they've hit the submit button and we in the server are going to look at that data。

 and then we are going to decide if it's an error， send back a form or store the data andre going we're actually sort of just have a comment say store the data and then go to the success so we're really looking at this part right here of receiving and validating the data and then taking all those actions okay。



![](img/7d906d29070f7df4d568a84a68e51039_3.png)

![](img/7d906d29070f7df4d568a84a68e51039_4.png)

So the idea of data errors is you know， you're typing in a form and you forget your zip code and you hit the button and a little red box pops up and says zip code is required。

 Now you can also tell the fields in the browser that they're required so that the browser won't even send the data that's different and not all browsers do that so you still have to check if you really want the zip code。

 you got to check to make sure the zip code is there。 Now in this one。

 I made it just to generate errors。 I made a。A validator on that form。

 if you recall the said that all the titles have to be at least two characters。

 and here's a little message， please enter two or more characters if that's not true。

 because otherwise， you know the fact that it's not a string or a number or whatever because the browser is a little too smart for us。

 So I had to come up with a validator that would fail in the server and not fail in the browser。

 you still need to validate data in the server。So you type some stuff in。You make a mistake。

 like in this case， the title was only one letter， I hit the submit button and now what I want to see is a thing that tells me what the errors are and gives me a chance to fix it。

 including putting the old data that I just posted right so it gives me my post data back and and then I get a chance to resubmit。



![](img/7d906d29070f7df4d568a84a68e51039_6.png)

So again， here's the data form and the validator there is it's a inleth validator。

 there's if you go to look into documentation， there's a jillion validators。

 I just this was really simple and it fits on a slide。

 so basically in addition to whatever the fact it's got to be a character field。

 I want it to be at least two characters。

![](img/7d906d29070f7df4d568a84a68e51039_8.png)

And that's not a crazy validator to have because you might have a post that says look。

 you're not going to have a title of one character when you're doing a blog post or something like that。

 you might say look at least five characters。

![](img/7d906d29070f7df4d568a84a68e51039_10.png)

So now we're going to walk through that process and so if you take a look at this code from the form。

In comeses a get request and that get request is going to show up with some old data。

 it's going to create the form with the initial settings。

 it's going to build a context that is going to pass into the render same render form that just makes the thing with table tags and CSRf and form post and so at this point we are a get request we are returning to 200 which is returning the HTML for that page right so that is that's the first part of it and that is the in the edit process。

 get the old data。

![](img/7d906d29070f7df4d568a84a68e51039_12.png)

Show it to the user and give the user an opportunity to change the data。

So now we change the data right and let's just you know say we didn't make any mistakes。

 you changed a few numbers， you hit the post which gathers up all this stuff and sends it as a post request to the server so then what happens is it comes into the post method see how these class based views are so dang pretty right so pretty。

And it comes and so request post， read all that data coming from the form comes into request post and you just construct a basic form and say。

 hey， basic form， your old data。

![](img/7d906d29070f7df4d568a84a68e51039_14.png)

Is from the post and all the fields are named the right way and the key value pairs， I mean。

 this is basically a dictionary。But the form made the key value pairs。

 it knew what names to name all the forms， so it named them。

 and so it's not surprising it knows exactly what to expect in there， right？



![](img/7d906d29070f7df4d568a84a68e51039_16.png)

And so it takes a look at the post data and then it constructs us a form object。

It constructs us a form object and basically says if there was a validation failure。

If not form is valid， then。We're going to do one thing。

 but in this case I didn't make any changes so form is valid so it drops down。

 this is where we would normally store the data off to the model， but I'm keeping this really simple。

And then I'm going to redirect with a 302 to form success。

 The other thing I might do is put a message in the session so that the message makes it into here。

 but I'm keeping it simple， and the browser immediately comes back and does a get to slashform s success。

 and then I return， Thank you very much I might have pulled a message out as we've seen in an example where I from the post method to the next get。

 I drop a flash message into something。 but there's better ways to do that and I'll show you that in an upcoming lecture series。



![](img/7d906d29070f7df4d568a84a68e51039_18.png)

And so that's the success flow。

![](img/7d906d29070f7df4d568a84a68e51039_20.png)

And it works great。 Now， let's take a look at what goes wrong。 So in this case， I got my form。

 I put in the wrong kind of title。 it's too short。 I send a post。 It gathers up all this data。

 sends it along with the post that comes in and request do post。 And so now。The form comes back。

And now form is valid as false because I've violateated a rule。Now。

 the interesting thing is in this form object is not only the old data。

 but also all the error messages， because at this moment it is constructed a form object。

And part of the form object is error messages。Okay。😊，So if it's not valid。

 let's make a little context。Okay。Let's make a little context and。Pass that in。

And then out out it comes and and at that point that format table is going to print out all of this stuff。

 all those error messages come back， so I render it back now。

I render it back and then of course you can submit it and maybe get to a success Now there is one sort of interesting question about this page which I have asked a stack overflow question about and I'm not sure I'mstatically happy about it and that is this pattern is exactly how django wants you to write it it wants you to write this and if you'll notice I'm doing something I told you not to do Django is telling me to do something that I don't want to do and that is return a 200 at the result of a post so I got a post。



![](img/7d906d29070f7df4d568a84a68e51039_22.png)

Now the key thing is the thing that everyone will agree on is once you store data。

 you have to return or redirect and so the Django people。



![](img/7d906d29070f7df4d568a84a68e51039_24.png)

ho've done this for years， they consider it okay to return the 200 and a page after a post if no data was changed。



![](img/7d906d29070f7df4d568a84a68e51039_26.png)

Now the problem is， if you hit refresh on this， you're going to get the weird funky message。

 but this is how Django works。And so I don't know what to tell you。I can write my forms differently。

 it's a few more lines of code in here and I've written that and I've made it so that I pass the error message and I serialize the form and put it in the session and do something。

But I'm not going to fight City Hall on that one， I'm just going to say if Djago thinks it's fine is the thing we do agree on is if you're going to return to 200。



![](img/7d906d29070f7df4d568a84a68e51039_28.png)

Don't return to 200 after you've saved data because then you'll double save the data。

Like you'll double commit a transaction， you'll double do a transfer， you'll double order。

 you'll do whatever， but in this case， all we did is looked at the data。

 came back and then sent back an error message。You can look at the stack overflow where I sort of argue for a little bit。

This has been a long lecture series。We talked about HTML， we talked about HTP。

 how get and post are different ways of doing it， we've talked about the idea of you can't how to fix the refresh。

 we talked about cross crosss request forgery， CSRF and how Django handles CSRF and then toward the end here we've talked about how to define forms in Djago to sort of outsource all that HTML generation and how we do validation now there's much more to learn on this and we're going to learn more of the features of form objects as we go forward and build increasingly complex applications。



![](img/7d906d29070f7df4d568a84a68e51039_30.png)
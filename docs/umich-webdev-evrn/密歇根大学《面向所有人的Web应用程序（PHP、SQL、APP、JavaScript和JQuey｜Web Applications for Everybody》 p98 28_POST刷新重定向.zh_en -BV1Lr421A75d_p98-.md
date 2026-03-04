# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p98 28_POST刷新重定向.zh_en -BV1Lr421A75d_p98-

![](img/abb749aefbb1afed3dd64e1029a624e6_0.png)

![](img/abb749aefbb1afed3dd64e1029a624e6_1.png)

So now that you understand the mechanics of redirect and how it generally works mechanically。

 now we're going to start talking about why we might use it。So。

One of the things we've talked a bunch about is when you get and when you use post。

 you're not supposed to use get to modify data。 You're supposed to use post to modify data。

 The problem is， is if you go and you post a screen and then you get it back another screen post and literally every bit of code I've shown you that does post are doing this wrong up till now。

 So I'm sorry。 Now I'm going to show you the right way to do it。 you get to know about redirect。

 right， So you need to do post what's called post redirect。



![](img/abb749aefbb1afed3dd64e1029a624e6_3.png)

The problem is if you do a post to a screen， hit the submit button and then hit the refresh button。

It's like， oh do you want me to send that post again And what if you you know made $100 payment and they hit the post again and you make a second00 payment and you get refresh。

 And so the browser goes like， time out。 I'm not， I don't want to do this because I know that posts are dangerous。

 and it could be that you giving money away or whatever。 And so they get a little pop up。

 and that pop up is often kind of badly worded。 And it's not something that you control。

 This is something the browser is doing to avoid double posting the same set of form data。

 And so it just means that we don't want to do a post。

 And we don't ever want to return HTML for the post。



![](img/abb749aefbb1afed3dd64e1029a624e6_5.png)

So。If the pattern here is you have a form， its method equals post。

 you press the submit that does a post。 And it gets me back a page。 And then I get this page。

 And then after I hit refresh on the page that came back， It says this is the browser talking。

 The page you're looking for， had information entered it。 You might cause action to be repeated。

 It's trying to explain to you that you don't want to do this， So everyone puts cancel。

 But then like， what are we supposed to do next， right， So and that's because we had H T M L。

Returned on a post。Meaning that you pretty much are supposed to do a redirect after a post and return no HTML and then post redirect back a get that actually returns the HTML。

 so we end up with a post。Redirect get。

![](img/abb749aefbb1afed3dd64e1029a624e6_7.png)

Is the pattern？So let's talk about how we're going to avoid these double posts right， like I said。

 posts are adding and modifying getss are looking at stuff， you don't want to do the same post。

It's really a bad user experience because you aren't controlling it as the developer。

 it's just bad in general， it's really very tacky and literally every postcode I've shown you in this class so far has been wrong。

 but not anymore。So the simple rule as I've said， is you're never supposed to generate HTML content when you receive a post and you're supposed to redirect。

 usually we redirect right back to the same script， so do post redirect。



![](img/abb749aefbb1afed3dd64e1029a624e6_9.png)

And here's a sort of a picture of how it works。You're in a form。 that's a post。 You submit it。

 It does something， updates the database。 and then it sends back a screen。 But this is a post。

 the response to the post， you hit refresh。 The user refreshes the page。

 And then it asks the questions， like， are you sure you want to do this because if you're going to really do it。

 And you say yes。 Then it's going to send that same data twice。

 And then do whatever it did into database twice。 So that's not the way we're supposed to do it。

 What we're supposed to do is we fill out the form。 We do a post。The data gets updated once。

 then you send a redirect and then silently blink， blink， blink。 It does a get back to the same page。

And then the confirmation page is the result of the get， right， so that there is， this is not a post。

 that's a get。 And now if you hit refresh， and you can do this as many times as you want， there is。

 it's a get request， not a post request。 So this post data is not being done twice。

 This is only done once。 here it's being done twice 3，4 dot da dot dot。 here it's only done once。

 And so this is the post。Redirect get pattern。Post， redirect， get pattern。

 just so that the refresh ultimately works。

![](img/abb749aefbb1afed3dd64e1029a624e6_11.png)

Awesome， okay。So。Here is bad code。 I am so ashamed that I ever showed you this code。

 but I had to show you this code Ca you didn't know what a redirect was until like 20 minutes ago。

 So remember， we have the model in the controller。I mean， the model in the view。

 the controllers sort of， we're going to learn more about controllers like orchestrating at all。

 And we have this thing called the context， remember。That context falls through。

 We put stuff into the dollar guess and dollar message， so we have sort of no logic down here。

 we start the code， and we look at dollar message and dollar gas。

Properly using HTML entities because we're nice people right So that's a sort of model view controller。

 but it's not a model view controller that properly does the post redirect Okay。

 and so we're using just a falling through of this message okay。



![](img/abb749aefbb1afed3dd64e1029a624e6_13.png)

But it's bad because if you hit refresh on this， Who knows if it will actually do it depending on the browser。

 But you might get that error message。

![](img/abb749aefbb1afed3dd64e1029a624e6_15.png)

Okay， so here we have to come up with a way。To pass this context information from the model to the view。

 because。Remember that Do underscore get and Do underscore post。Are gone in between requests。

 and comes a post request。 You've got to underscore Sc post。

 A later get request is not going to have that data。 So we have to save it。 Well。

 where are we going to save it。Sessions to the rescue。So we start our session。

 which basically sets a cookie。 We talked about all that before， right。

 sets a cookie has a little bit of data on the server。 little data for a little session。

 And then when we do all our stuff， the thing that we want to pass down to the context。

 We're going to put in the session。 So we're going to have the sessions sub guests。

 So we have guests equals 42。 And then we're going to do our test。

 and then we're going to have a message equals blah， blah， bla， blah， blah in the session。

 Remember that you can write to the session。 So we're writing from the session。

 So we've put the context， the information that we want to pass down to the view。

 We put it in session。 and then。We redirect right back to ourselves， right back to ourselves。

 and then we return and go out。 So we turn。 and this one is done。

 That request response cycle is done。 Then what happens is a get request comes in。Right。

 the second request response cycle starts。 Now， that's a get request。 There is no post data。

 The immediate one before that had post data， but。We start the session and look what we have in the session。

 So that pulls all that stuff into session。 It goes straight down to here because there is no post data。

 and the session is ready for us to use down in the view。 So two request response cycles post。

Redirect， get。Then。In we come。 This is a get request now。

 is either the first get request or a get request that happened right after a。

 And so we check to see， is there something in the session。 If it is。

 that's what we're going to put out as the message， the guess。

 old guess and the message the same way。 We're going to put a false a blank。

 And then we're just going now we're going to do our view at this point。 we just do the view。

We just pulled this stuff out of session。 We use session momentarily to hold the old guests and the old message to passed from a post。

To session。To redirect。To get。And then it pulled it back out of the session。

That's what we just did post redirect get and we had data in the post that we wanted to pass to the get。

 but this is a second request response cycle and that's a first request response cycle。Oh， yeah。

 that's pretty darn cool。 Pret darn cool。 We are going to use this Like all day long。

 we're going even name it the flash pattern where you put a flash message in session。

 but we have to delete that first。 So， and again， I warn you that maybe your browser and won't show both of these。

 but you can see how we'll do a submit the response come back 302。 and that says。

 go immediately retrieve a guess。 but we have passed the session data。



![](img/abb749aefbb1afed3dd64e1029a624e6_17.png)

Between these two things。 and that's where these two things come from。 So we've processed a post。

 we put our data in a session， then we send the redirect。

 and then we read the data from the session on the success of get。

 And then this is a real 200 with the real HTML that makes the page。



![](img/abb749aefbb1afed3dd64e1029a624e6_19.png)

Yay， this is finally getting fun。

![](img/abb749aefbb1afed3dd64e1029a624e6_21.png)

This is finally getting fun。

![](img/abb749aefbb1afed3dd64e1029a624e6_23.png)

You're learning like awesome post redirect stuff。 Oh， and then， of course， if you press refresh。

 you don't get any bad error message， and it's a get request。And it gives you 200。

 And it gives you back the stuff。 Why， Because it pulled it out a session conveniently。

It was still there。 Those two key values are sitting in session， still there。



![](img/abb749aefbb1afed3dd64e1029a624e6_25.png)

And here I have my favorite picture in the whole world。So。We have a post， we have the form。

 we do a post。Post。The post comes in， and then it takes the data and puts it in the session。

And then it immediately sends a redirect。And then。The browser does another get request。

And then it pulls the data out of the session。And then it produces the HTML。

With the old guess and the message。 And it sends that back to the browser。

 which parss the response and puts it into the dom。 And then you。See it。And then。

If you press refresh。You press refresh， it sends a get request in。

Which then pulls the same data out of session。Produces the same HTML。

And then the response comes back to you。And so that's post， redirect， get refresh。



![](img/abb749aefbb1afed3dd64e1029a624e6_27.png)

Now you've got it。So now that we got this all figured out。

 we're going to do log in and log out using session so understand that just having a session is not the same as being logged in or logged out。



![](img/abb749aefbb1afed3dd64e1029a624e6_29.png)
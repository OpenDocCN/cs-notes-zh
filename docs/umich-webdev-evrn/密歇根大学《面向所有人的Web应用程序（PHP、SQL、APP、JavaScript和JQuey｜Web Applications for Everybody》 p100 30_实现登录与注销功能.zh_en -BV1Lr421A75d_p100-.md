# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p100 30_实现登录与注销功能.zh_en -BV1Lr421A75d_p100-

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_0.png)

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_1.png)

So now we're going to actually build a fully functional and respectable log in and log out because we have to use session and we used to redirect and we have to use this concept called a flash message。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_3.png)

So to review sessions are not the same as being logged in。

 we indicate that we're logged in by sticking a little bit of data in the session。

 The session starts when you hit the website and the session data is changed the moment you log in。

 and what we do is we look at session data the rest of the application looks at data in the session to decide if you're logged in or not。

 and then logging out simply removes information from the session logout PhP is my favorite code to write all the time。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_5.png)

Okay， I guess I'll show you sort of how it works， right， you send in a post。To log in。

It looks in the data， read some data to see if you're logged in， if you are logged in。

 it changes the session that says yes。That you're logged in， and then we do a redirect。

 and then we do a get request， and then we come back。

 And then this code somewhere else in the application Later。

 all the rest of the get requests or whatever， they check the session and they ask。

 are you logged in and they look at the session by logging in。

 The cookie is still there because it's the thing that determines which session is active。

 But basically， the fact that you're logged in is logged in equals true or something like that。

 We are not going to do quite like that， But that little fact that you're logged in is stored in the session。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_7.png)

Okay。So we're going to have a couple of use cases here。

We're going to have an application and we go right to this application。

 it's going to notice that you're not logged in and say please log in and so then you click on login。

 you're going to go login。 PhP。Then you're going to type an account and a password that's wrong。

 You'll press log in， and that'll be a post。 It'll do a redirect。 And we got to put this message out。

 So we got to post redirect。 But you already saw in the previous example how we can pass a message into the future using session。

 but this one's going to be a little different。 This one's called flash。

 meaning that you only see at once。 And then if you type in the right account and password。

 then you'll come back to the application except now it will know your loggedin。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_9.png)

So that's all the scenarios that we're going to work through。So let's take a look at the code。

 Let's first go down to the code。 that's the view code。 So this is the view code。The view code。

So we'm going to put it， please log in。 This is part of the flash message。

 which I'll come back to Here we have a form。Nothing special Just on account and a password method equals post。

 you want it to be method equals post because you don't want to be bookmarking login URLs and putting passwords in get parameters。

 Okay， so that's our form。 We'll come back to the stuff in a second。 So now here is the model part。

Here's the model。The top part。And so we're going to start the session， first line。

 nothing before the first line。 start the session。 If we have some post data， post and password。

 then what we're going to do is we're going to un sessions sub account So we're going to use the fact that the account key is in the session as our indication whether or not you're logged in or not。

 But what we're doing is the beginning of a login process is we're logging out any previous user by deleting it。

 so unset is the PP way to delete a key from an array。

 So that says delete the account key from the session array。

And eventually we'll put some database and SQL in here in later things。

 but for now we're just going to have a hard coded password。 if the password is right。

 then what we're going to do is copy the account name into the session because the post date is going to go away as soon as we redirect right and we're going to have a message and we're going to call that message success and we'll call it logged in and then we're going to redirect app do PhP right now we're in login。

 phP。 we're going to redirect appt PhP。If， on the other hand， the password is wrong。

 we are going to put an error message in the session， S sub error。

 a key in the session incorrect password， and then we're going to redirect back to login dot PP。

 So the fact that in this case， we're going to redirect to one file， in this case。

 we're going to redirect back to the same file， this is very much a controller function。

Routing controller deciding where to go next based on the data based on whether your password is right。

 I'm deciding to send you A or B Okay， and we always have a return right after the header。

 so that's the model code for the login dot PhHP。Now。

 let's trace this little bit through here on that previous screen。

 so we're going to set session error。And when we drop back into login。 PhP。

 we're going to say if is set S of error。We're going to print out the session。

 but we're going to call it。Red， we're going to print out in red。 And then what we're going to do。

 this part right here is really important。 This is the flash part。

It means that once we've shown the user the login error message。

 we're going to delete it from the session。 So if they hit refresh， they won't see it。

 So it's a flash is as defined as one， a message that's shown to the user once。 it's flashed。

 and then it's gone。 The moment you see it is the moment that you delete it， okay。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_11.png)

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_12.png)

You're going to be really tired of this code by the end of this class where you're going like， oh。

 you got to put the flash code in part way through， we just write a function that does this code。

 you might want to even write a function that does it all the time where you just put the error in the session and redirect and then it comes out。

But you then throw the error away or success。differenceifference between success and error is you just have the success message green and then you delete it in the same flash pattern。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_14.png)

And so that's how if you type the wrong ID and password and you come here。

 you see this flash message， but then if you hit refresh on this page， it goes and looks like this。

 This is not there on this page because the very moment that you showed this。

 you also deleted it from the session。 so thats how that's how flash works。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_16.png)

Post redirect flash， right， so post detects an error， puts the message into session。

 redirects the get back to itself， sees it。And then deletes it， by the way， we have app。

t PhP and login。t PhP session is shared across all of them right so it's also a way to send data from one file to another。

 It doesn't have to send data just back to the same file。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_18.png)

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_19.png)

So if we take a look at how this flash works。We get a post。And if something goes wrong。

 we put the message in the session， we redirect。And then the browser does a get request。

 And then in that get request， it pulls out the session from the session。

 it pulls the error message out of the session， and then it responds to the get request Now。

 with that message unread。 But then it also has wiped it out of the session。 And now in the future。

 if you do like a refresh。You see no error message because that's gone out of the session。

 This session kind of goes along with all things。 But this one deleted that。

 And so now you don't see it anymore， so。

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_21.png)

Let's look at Appdot PhP now one thing you'll notice about Appdot PhP is it has no model code up here。

And that's perfectly okay because we're not posting to app dot PhP。 we're posting to login。t PhP。

 So there's no model。 This is all view， basically。So the first thing it does is it comes in and checks to see if there is a success message。

 if there is a success message， it prints it out in green and then deletes it。

That is how we see this little message right here。Now。

 this last little bit is how we check to see if we're logged in。 Now， remember。

 we got session start up here， sorry， there's a session start up here somewhere。Otherwise。

 none of this would be working， that's up here。If we have the account variable or account key is set in the session。

If it's not set。Then we tell them that they have to log in。 If it is set。

 then we say welcome to our cool application。And then we put a link into logout。

phP so that we can log out。

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_23.png)

Okay。So。This is the success we go with a good password that goes into login dot PhP， loggan。

t PhP puts the account in the session and it puts the success message in the session。

 and then it redirects to app dot PhP。An app dot Ph P both looks at the logged in message and prints out the nice little message。

 And it also checks the account and says welcome by knowing that account is there。

 It says welcome now later。The flash message been is gone， but the account stays in the session。

 so the account sort of lives in the session the whole time。 so every time we go to app do PhP。

 no matter how many times we refresh this， it knows that you stayed logged in because we don't auto it's not a flash message。

 it's just a piece of the session and unless you get rid of it explicitly。

 it just stays there forever。

![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_25.png)

Okay， so this application doesn't have to just be a out PhP can be any number of files。

 and they just look to see if a account is set， and then if it is， we assume that you're logged in。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_27.png)

Now， my favorite code to write in any application is the logout code。😡，Because。

I do is you start the session， you wipe out all the key value pairs。

 and then you redirect back to the application， so if you press this log out。

 it actually goes to logout。 phP。Does this code and then redirects。

Back to Appdot PhP and AppOt PhP comes in and checks is the account set in session and the answer is no because you just wiped it but all out。

 so it tells you to log in so that's how you kind of take the complete step of logging in and logging out。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_29.png)

Okay， so that's app dot PhP。So in this， we sort of have zoomed through the mechanism of redirect。

It's just an HTTP concept can redirect anywhere， we've talked about redirecting with post redirect get the way you have to the fact that you can't。

 you don't want to hit refresh after a post， and we've talked about how you can put a message in the session that lasts really only until the next request response cycle and then how you have long-ter longli data that you put in the session to support things like log in and logout。



![](img/f5d3164a7c3e7ad8b8a2fc61f2fe2b8e_31.png)
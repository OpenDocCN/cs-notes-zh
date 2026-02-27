# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p70 -71-UI Testing.zh_en -BV17RXGYuEaM_p70-

Hey， everyone。 So in this video， I want to expand more on what was already set in the lectures。

 as well as the prereded video about Cyppress and U I testing。



![](img/6e4bae155f2baed27a50327310d6a174_1.png)

I'm going to show you how to write a happy path， as well as how to write some test cases for end to end testing。

 But before we jump into the code， I've made up this application here。

 which I'll be using in the demonstration。 That's few things that I want my test for a happy pathd to do。

 First， I want to check if it navigates to the home page。

 Then I wanted to try logging in successfully upload a file successfully and finally logged out successfully。

 So just to give you a quick overview of how that looks like we have our。😊，Our home page。

 which we will then try to log in by clicking the login button， filling up some。Example， inputs。

Clicking the login button， which logs us in successfully。 And now that we are on the dashboard。

 we are going to try and upload a file successfully。And as you can see。

 we have uploaded our picture correctly。 and now I want to try logging out。

So now that we have all that down， let's jump right into the code。



![](img/6e4bae155f2baed27a50327310d6a174_3.png)

So what I have here is a is the login form。And notice how I've given my inputs， names。

This will come in handy later on when we are trying to select the inputs using Cyprus， so。

Taking a look at our package do Jasonson， we don't currently have Cyrus installed。

 but we can change that real quickly by using yarn add Cyrus。And now， it's Cypress install。

We can go ahead， and。Modify our scripts a little bit。Just so。It's easier for us open Cyprus later on。

And now， all we have to do to start up Cypress is use command ban yan crus。



![](img/6e4bae155f2baed27a50327310d6a174_5.png)

So when you first run Cyrus open in your project。Yo。You'll get this display here。

And all you have to do is come over here。 Click enter and testing。

Which will then configure these files for you。 And as you can see from the left left bar of our V S code。



![](img/6e4bae155f2baed27a50327310d6a174_7.png)

It has nicely created this cppress file for us here。 So if we go back to Cyppress。



![](img/6e4bae155f2baed27a50327310d6a174_9.png)

Click， continue。And choose a browser。 So the default browser that we'll be using in our marking is Chrome。

 So I highly recommend you start the testing thing in Chrome。

And all you have to do is to create your test。 and all you have to do to create a new test file is just to click this create new em back。

And let's rename this file to something more meaningful。 So I'm going say。User。Flow。Rend the spec。

And as you can see here， it generated a file， an example file called userflow dot cpress dojs。

 and it gave us a really simple test case。

![](img/6e4bae155f2baed27a50327310d6a174_11.png)

![](img/6e4bae155f2baed27a50327310d6a174_12.png)

Which， if you open up here。Which when you open up here， it runs the test and it says it passed。

 So now we want to modify this test so that it so that it actually represents our happy path。

 So I'm going to come come over here。 I'm going to delete this。



![](img/6e4bae155f2baed27a50327310d6a174_14.png)

I'm gonna to say。Describe a test。要 set。Okay， so now what do I want to do first。Well， I think。

Before every test starts， it should navigate to us in URL， right？ So in this case， it should。你记。这好村。

And then we are just going do a simple check for URL， such that it。诶。Shit。2。You are啊。



![](img/6e4bae155f2baed27a50327310d6a174_16.png)

Okay， and now when we go back to our crus test。And werun the test。It passes。

 So we are currently on local host 3000 at。

![](img/6e4bae155f2baed27a50327310d6a174_18.png)

The slash index。Next， what we wanted to do， We wanted to navigate the login screen。小别。



![](img/6e4bae155f2baed27a50327310d6a174_20.png)

![](img/6e4bae155f2baed27a50327310d6a174_21.png)

What we want to do is we actually want to get this button。



![](img/6e4bae155f2baed27a50327310d6a174_23.png)

What we want to do is actually get this button， the login button。

And we want to click it such that it redirects us to the login。



![](img/6e4bae155f2baed27a50327310d6a174_25.png)

So taking a look at our login form， Oh， sorry， taking a look at our navigation bar。

 I've given the login button a name of login button。So we can come over here。Can see。

I wna get the button。With the name。What do I want to do after I get this name。这等的。And the should。

Redirect this to the login page。 But just to be sure， we are also gonna check。That our URL。Shi。系。要多通。

Address。But also， it should contain our login。呃 in该。



![](img/6e4bae155f2baed27a50327310d6a174_27.png)

Okay。Let's check on Cypress skin。rerun the test。We can see that we've end up on the lock in screen。



![](img/6e4bae155f2baed27a50327310d6a174_29.png)

Cool， that's what we want。Next， we want it to actually log in successfully by filling in forms。So可以吃。

log in successfully。但。Fillling in some forms。 Okay， so looking at the form。

We have a couple of inputs。 We have a input for email and password。

 I notice how I've given both of these， the names like respective names。

 So this one for the email has the name of email， and this one for the password has a name of password。

 and we also have this button to submit， which I've given the name of submit。So let get。My input。

With。呃。Email。And I wanted to focus on this input。And now we can type in our email。

 So let's say is send an email。嗯。诶。And we want。And we wanna do the same。For our passive field。Okay。

かし。Oh， now that that's done， we are gonna try to select our button and make it click。Okay。呃。嗯 with你。

Of。And。

![](img/6e4bae155f2baed27a50327310d6a174_31.png)

And now let's see if that works。

![](img/6e4bae155f2baed27a50327310d6a174_33.png)

Co。And we are now on the dashboard， but just to be sure。We can also check that or URL。是。跟佢。

Our local host。这第。Index of dashboard。

![](img/6e4bae155f2baed27a50327310d6a174_35.png)

Now that we're actually on the dashboard。We want to upload an image。But how do we do that。

 So we need to first click on this， and then we actually need to select the file， right， But luckily。



![](img/6e4bae155f2baed27a50327310d6a174_37.png)

I've already got a file set up here。My source assetss and this cute Leohiba pick。

So we're gonna try to upload this。So I want to write a test case that it should。他个。诶 a file。Success。

Okay。So know that well， in the dashboard， we w to get。第边台。

So let's take a look at dashboard and see what name I've given this input。 Okay， I've given the name。

 I've given the input the name of your image。 So we're going select that。食天可。And。To upload a file。

I am gonna use the select file。I met from Cyprus。And I'm going to give it the relative path name。

That my image。Okay， thats that should be fine now。 Let's check that again。



![](img/6e4bae155f2baed27a50327310d6a174_39.png)

哦。As you can see here we're filling the stuff uploading。 and one second later。

 our receiver pick pops up。 Okay， that looks good。

![](img/6e4bae155f2baed27a50327310d6a174_41.png)

神 now。Pry logging out。嗯别吃老。Successfully。

![](img/6e4bae155f2baed27a50327310d6a174_43.png)

So。Coming back here。 We have this log out button， which。



![](img/6e4bae155f2baed27a50327310d6a174_45.png)

Should be in our application bar。 I have given name of logout button。 so we're going to use that。

Something get。2本。那个。And then I'm going to click on it and just to make sure that it actually ends up at the correct place。

 I'm gonna， I'm gonna check the URL。每个是。佢。嗯sorry。我偷屎。But just the slash index。



![](img/6e4bae155f2baed27a50327310d6a174_47.png)

Hey， now that that's done， let's check our crus and make sure everything is working。Okay， cool。

Before that， there is actually。Something that I would like to check， as well。

So if we come with it here。If we try， log in again。And upload our ship a pic。

You'll notice that there's a delay before。Does shea picture actually pops up for preview。And so。

Just to be extra pedantic。 and also to like check whether our picture actually renders。

We're gonna try to select。

![](img/6e4bae155f2baed27a50327310d6a174_49.png)

This container。And we're gonna to check if that image is actually there。So in our dashboard。

 I have this image tag here that only renders if both states are true。So I'm gonna come over here。

So I'm going go over to my user offlow。 And in this test case here。

 it should upload it file successfully。 I'm also gonna check。That。嗯。Did I give this image name， Yes。

 I did。 I give it a name of image preview， which we gonna use here。So I have this。

 I'm gonna check if that imaged tag is there。And then just to be safe。

 I'm gonna check that it should。Actually， be there。



![](img/6e4bae155f2baed27a50327310d6a174_51.png)

Okay， now we can go back to Cypress。 I'm gonna see if it works。It doesn't。

Let's see what's happened here。 So it says that it expected our image tag to be visible。

 but then it says that it timed out after retrying after  four seconds。Okay， okay。

 so this is what's this is what's happening。So when， whenever a test case runs in Cyprus。

There is a limit to how long a test case will run for。In this case， it timed out after four seconds。

 and that's not what we want， because sometimes like our image might be loading a little bit slow。

 our promise may not be resolving in time。 our fetch may not be passing us back the data in time。

 And so when this happens， our UI testing will obviously fail because because the tests will just time out。

 So what we can do to get around this is by using the weight method。



![](img/6e4bae155f2baed27a50327310d6a174_53.png)

So。Go to come over here， Cyprus。 And basically， what I'm going to do in this wait minute。

Is I'm going to specify a certain amount of time that I want my test to pause for before executing the next line。

 So in this case， I wanted to wait for。Approximately 6000 milliseconds or 6 secondsd。

 And so if we come back to Cyprus。

![](img/6e4bae155f2baed27a50327310d6a174_55.png)

We can see that we've uploaded our。Sorry， if I run this again， you see that we've uploaded our image。

 It's taking a while to render。In。Now it's rendered。 And while we were waiting， it rendered。

 and then the test was able to continue successfully。



![](img/6e4bae155f2baed27a50327310d6a174_57.png)

So， that's basically it。For the process of writing a happy path。



![](img/6e4bae155f2baed27a50327310d6a174_59.png)
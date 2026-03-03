# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p131 23_表单与jQuery.zh_en -BV1Lr421A75d_p131-

![](img/9a1bc3e5c71c57167ec504d53963008c_0.png)

![](img/9a1bc3e5c71c57167ec504d53963008c_1.png)

Okay， so what we've been doing up till now is in our Jquery， in our JavaScriptscript。

 we have been asking to register an event， which means call us back。

 JQury is supposed to call our little bit of code back when something happens like the documents' ready or a resize or。



![](img/9a1bc3e5c71c57167ec504d53963008c_3.png)

We are going to do something like grab a piece of the dom， and then do something to it。

 change its background color， hide it， show it or whatever。 Okay。

 so the next thing we're going actually do now is we're going to have Jquery talk to the server。

 So everything we've done up to now as Jquery going this way， talking to the document object model。

 Now， what we're going to do is have Jquery both talk to the document object model。

 but also talk to the server。 So Jquery is going to initiate request response cycles。

 which is different than you， as the user clicking on something and doing a request response cycle。

 And so as we do more interactivity， we see that Jquery starts to increasingly talk even talking to the database。

 We're not doing that yet in this example。 and then update the Dom。

 And so without a full request response cycle， you can actually get new information from the database。

 And that's how something like Facebook has the things that blink。



![](img/9a1bc3e5c71c57167ec504d53963008c_5.png)

You just got a new message from somebody blink without you actually refreshing the screen because it's checking to see if there's any messages。

 And when you get a message， you go blink， and it can do that with a loop blink。



![](img/9a1bc3e5c71c57167ec504d53963008c_7.png)

Now we're not quite getting there yet right now we're just going to look at how JQury can look at and then talk to the server。

 okay？

![](img/9a1bc3e5c71c57167ec504d53963008c_9.png)

One little example。So。We have a little bit of code that does us S 5 and then just prints out some post data just so we can kind of see it。

And I'll work through an example of this for you。 We'll just kind of cover the code。

 and then you can see it again while I just run through the example code。

 So we're going to put a form out and this form is pretty much the same as any other form。

We're going to give it an ID。We're going to have a name and a value。

 and we're going to put a spinner in the form， and we're going to start it with display none。

And so this right is going to just have like a， you know， a box。But no submit button。

 So you'll notice that there's no submit button in this。 But then there's a spinner here。

But it's hidden for now， so it's a hidden spinner。Okay， so we got a form， its name is1。

It's got a value of hello there。Okay， and there's a hidden spinner right next to it。That's our form。

And then we have a little div， and you start increasingly。

 the more you move some you're rendering into the browser。

 the more you find you just make an empty div， Give it an I D as a place to put something。

 We're going to put something in here later。Okay， so that's kind of the static stuff we have this code that echoes output。

And so here is。The code that we're going to do afterwards， we're going to this。

 We probably should have put this in a document ready， but it doesn't matter。

 So we can see a few different kind of techniques of Jquery in this。So what we're going to do。

 this code's running as the screen is loading。 and we're going to say dollar pound sign target。

 So dollar pound sign target says。This form。So so we're telling JQury to look up in the document object model that form。

 dollar pound sign target。And dot change now what we're doing is we are registering an event。Okay。

 so this parenthees goes all the way down to here。 So what we're saying is。In this field。

 hello there。If someone comes in here in types like an X and then leaves the field。

That is a change event。 And when that event happens。Come and run my code。 So again。

 first class functions。 All this code is code that we've got sitting here waiting until something happens in that form。

Waiting until something happens in that form。And we get past a variable in。

 which is the thing that happened。And we'll be able to do stuff with it。 So now， once this runs。

 this， this code in the middle hasn't run。 It's just， it's just hung off of the end。

Of the change event。

![](img/9a1bc3e5c71c57167ec504d53963008c_11.png)

Nothing happens。 And if you don't change anything in the form， that code never runs。 It's registered。

 but it never runs。 again， asynchronous， event based programming。

 something you kind of got to get used to。It doesn't run right away。

 the registration runs right away， but the code doesn't run right away。



![](img/9a1bc3e5c71c57167ec504d53963008c_13.png)

So we go in here， blah， blah blah， and we type an X， and then we type leave。

That triggers a change event， and so that causes this code to happen。So if you recall。

 there was a spinner here。So the first thing we do is we say dollar pound sign spinner。

 The spinner has an idea of spinner， and then it shows it。 So this spinner is an animated g。

 And so it starts spinning。So as soon as this code runs。

 that spinner appears and goesttt dot has nothing to do with JavaScriptscript。

 It has to do the fact that it's just an animated gif。



![](img/9a1bc3e5c71c57167ec504d53963008c_15.png)

And you can go download spinner animated gifts。 The animation is part of the image itself。

 not part of the code that we run。 The code we run revealed the image。 Now。

 this pattern of revealing the image， the moment we start writing something。

 this code we're going to do for a while is going to run for a while。

 And so they show you that spinner to say， oh， we started doing something。 Don't freak out。 Hang on。



![](img/9a1bc3e5c71c57167ec504d53963008c_17.png)

The user experiences when the spinner appears you're supposed to hang on。

 and then when it's done doing its thing， the spinner is going to go away okay。

So the first thing we do is we show the spinner。The second thing we do is we go grab the form。

And then this form variable is the form itself。And we just put an X in here。

 And we're going to do form dot find。 And we're going to search。

 This is a search string within the form。 There's a whole form here。 We're going to find this。

 The name equals one。 If you remember， that was the name of the form field And then Val extracts whatever the current text is in that form field dot Val is another piece of jque。

 So this was just this is a big long jque statement that says， let's get that stuff out。

 get the X out。 And so what text will be is whatever it was in this form like hello。

 And then you Louis， the word hello will be in the variable text。

That's what we're going to accomplish。Put out a log message。

And now we're going to call a bit of code inside of JQury Do。

 and then this is a method within that dollar object。Dollar is just an object。

 and post is just a method within it。And now we're going to call a server based script and so the first parameter is the name of the server based script。

First parameters is the name of the server based script。

 So if we go back and we take a look at the server based script。

 that is going to run this code on the server， which is going to sleep 5 seconds so that your little spinner stays up for a while and then it's just going to print some print out and then going to go back。



![](img/9a1bc3e5c71c57167ec504d53963008c_19.png)

The thing about this is that。This is now another asynchronous。 It's like inception。

 It's an asynchronous thing that's happening within another asynchronous thing。

 So the on change is running code。 but then we start up a thing which sends data to the server。

 And we can't。 We don't know how long that could take。 That could take。 in this case。

 it's going to take 5 seconds because I made it take 5 seconds。 And so you can't really。

 at this moment in the code。 Wait for the result。

![](img/9a1bc3e5c71c57167ec504d53963008c_21.png)

So， oh and we got a second parameter because this is a post request， which is key value pair。

 So we're going to send Val in and this text that came from the form is going to be sent in。

 And so that's why up here we say post a Val。 So that that is that form field。

 It was named one in the form， but we pulled it out and we've posted it as Val because we sort of extracted the data from the form。

 And now we're making a post request manually in jQury。Okay。So this is first parameter to post。

 second parameter to post。 and then there's a third parameter post。 and what this third parameter is。

Is code that will run when the post is complete。So this is delayed code。So JakeQurry sends the post。



![](img/9a1bc3e5c71c57167ec504d53963008c_23.png)

And then time passes。And we cannot sit and wait at this point。

 We have to move on because the browser could be doing a whole bunch of other things。

 And then eventually， when the post comes back， Jquery runs our code。

 and so it runs this code right there， and it passes in this parameter data， which is the response。



![](img/9a1bc3e5c71c57167ec504d53963008c_25.png)

Which is blah blah bh， blah， blah， which is the output of that script。

 So the output of that script comes into this variable。Like I said， its inception。

We are asynchronously being called because of a change method。

 and then we are calling something which is going to asynchronously call us back when the post is completed。

So this post happens。 It comes back。 It activates this。 And so we're just going to log it。

 And so then what we're going to do is we're going to take that div。

Remember this div with an  ID0 result， it has nothing in it。Now this might happen more than once。

 so the first thing we're going to do is go find it， remove anything if we put it in before。

 and then append the data。 so there's just some text that come back in this variable data and that's going to show up in that div we're going to change the dom and you're going to see something different。

And then。We're going to hide the spinner because all this time， that spinner has been spinning。

And now we get the data back。 We put it out on the screen blah， blah， bla， blah， blah。

 And then we hide the spinner again。 Spner vanishes if it works。Okay， so this then is the post。

Post itself returns an object。And we're going to add another asynchronous activity。 And that is。

 if this thing that comes back is like a 404 or a 500， some kind of server error。

 and you you would create a server error by making maybe a syntax error or something or just making this be auto echocho 1 dot when that is a wrong file。

 then you get a 404 back。 And so what happens is if you get a 404 back。

 it's not going to run this success code。 It's going to come down here。

 and this is different asynchronous code。 So by the time this is all said and done。

 you have a post that's gone in。And you have two pieces of code。You have the success code。

And the fail code。They are sitting there waiting。 Time is passing。

And then when JQury gets the response back。If it's a 200， okay。It runs this code。

If it gets a 404 not found， then it runs this code。

And so we're going to turn this thing red and put an alert up and away you go。

 but this whole thing is constructing and this is time passing。Wo。Take your time。

I should have a demonstration of this actually running code， watch your console。

 figure all this stuff out， I try to keep this as simple as possible。



![](img/9a1bc3e5c71c57167ec504d53963008c_27.png)

We're kind of entering the part of the course where if you say to yourself。

 I'll understand this code later， it's going to get bad really fast。 So you're gonna be like。

Because you just。You need to understand every curly brace， every line of this。 I mean。

 it as simple as I possibly could。 But at some point。

 I'm just going to expect that you're going to know how to throw a post back and put in some success code and some fail code。

 and not just say， whoa， that was a car accident with a bucket full of syntax， right？

 It's all very beautiful， it's all amazingly elegant。 And it's all surprisingly easy to write。

 as long as you really know it's going on。 If you're just cut and paste in and then cut and paste some more and then cut and paste some more。

 you'll ultimately。😊，You'll just it'll turn into mush for you。

 So don't come back to this and watch this later if you're confused。So like I said。

 I wasn't going to tell you everything about JQury。

 I just wanted to kind of show you the shape of the kinds of things that we're going to do with JQury。

 we'll be using it going forward， we can you know set things up， we event handle。

 we do things in the Dom， we change things in the Dom， we can handle form data。

 we can send post requests and get requests back and forth。

 we can do stuff with that and then change the Dom。

 it really is a beautiful way that we can build increasingly interesting applications that have amazing interactivity and it's really only limited by how much creativity that you have。



![](img/9a1bc3e5c71c57167ec504d53963008c_29.png)

![](img/9a1bc3e5c71c57167ec504d53963008c_30.png)

![](img/9a1bc3e5c71c57167ec504d53963008c_31.png)
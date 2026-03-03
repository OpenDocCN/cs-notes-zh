# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p39 39_07_05_DJ4e JSON聊天示例代码详解.zh_en -BV1rNibBuEwD_p39-

Welcome to another walkthrough for D django for everybody in this particular walkthrough we are going to walk through the Cha on sample code。

 It's a application of fetch and Ajax and set time out and it brings a lot of these JavaScriptscript in the browser ideas altogether in one simple example。

 So the idea is we are doing something that's asynchronous we're going to have we're simulating two people logged into the same system and。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_1.png)

![](img/249a4ce6f6138e185a6c5f82f7a17af5_2.png)

Wanting to see the messages from one screen to another， so let's second message， So this is one user。

So the whole page redisplays and we saw the spinner come up there and so if we come back and we just go over to this other screen。

Second message shows up。 And so we didn't do anything on screen。 We didn't refresh the screen。

 And so some asynchronous thing is happening。 And so let's just take a look at the。

We have developereler tools， let's take a look at the network。嗯。

And so what's happening is there's a timer。And it's requesting this chat。

 and in this chat there is some JO， if we take a look at the response。

 we' get an array of these messages， right？Arays are not really good style of Json。

 So I apologize for that。 So there's a timer that's running。 And so this， this。

Is just getting that it looks like about every five seconds。And so if I go on。

 I'll just say third message over here。So what happens here is I'm doing a full post redirect you know I'm posting and it' going to do a post redirect and then a rediplay and it takes two seconds we'll see that in a second。

 but then we have the third message but over here third message merely appears and so it's doing it about every five seconds which this is a polling pattern which is a really bad use of reason network resources is a really bad use of server resources。

 so don't use the polling pattern， but it's the way I can show you this the simplest okay。

And so let's take a look at how this is working， so let's start with URLs。

pyy I've got the talk page which is this main page and then I've got a JSON page JSON endpoint called Mesage and then I've got a little thing so that the spinner shows up that's nothing fancy so。

The main we've got a get request which simply renders this page and let's take a look at talk。

 HTML so we've got you know a form for the chat。 we got a CSsrf token and we got this div that starts with the spinner and so if I come here and I just hit refresh you will see for a moment that the spinner shows up So this is the code that came from the server is this spinner and then what we're going to do is we're going to update this and and then replace this text and that's what we're going to do is replace it by the JSON and then over and over and over we're going to delete you're not even seeing it because it deletes this whole thing and then it respond to it。

And then what we also have。

![](img/249a4ce6f6138e185a6c5f82f7a17af5_4.png)

I let's take a look at the chat messages。

![](img/249a4ce6f6138e185a6c5f82f7a17af5_6.png)

And so let's look at the raw data and this is an array of message and time。

 and so it's using this thing called let's take a look here。

 it's using this thing called where is it where natural time。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_8.png)

Using natural time for them make this one minute ago。And so if we take a look at this messages。

We can， we can。Let's take a look at the browser tools but developer tools network tab for free refresh here so we can see that this is got a it's JSON 125 characters。

 the responses JSON we can see the raw version of it so that's just us hitting the JSON endpoint by hand So if we look at what goes on in the JSON endpoint。

We are going to。This is just a cleanup message so you can kind of ignore this。

 I'm going to get the most 10 recent messages ordered by the created at time。

 and then I'm going to loop through those messages that I got from the data model。

 I guess I could take a look at the。The model， I got a simple data model here。

 I got the owner user key created at updated at intex， so not much to it。

But I'm going to create these results and I want to escape the text in the back end remember to do HTML entitiess because I don't want to do it in the front end because that will make my front end code a little too complex so I'm just going to escape it in the back end。

 I would not say that that's a good idea。And so all I'm going to do is I'm going to make。

 I'm going to escape the message text， and then I'm take the natural。

 make a natural time of the created app。 and then I'm going toend it， and I'm going to return。

Json response， safe equals false。 And that debt has to do with like letting certain things go through。

 But this is taking an array。 Now， I would， it is not best practice。

 It's actually bad practice to return an array。 But we're going to keep this as simple as possible。

 And this is， we're just going to the to the model and getting the most 10 recent messages and then sort of creating an array of the kind of stuff we want to hand back。

And so this message is， you know， JON is not just give me the data in the model。

 it's often give me the data。Take the data from the model， do some augmentation to it。

 make it pretty， make it ready for display， and then hand that back as the JSON response。

And so that's the JSON response。

![](img/249a4ce6f6138e185a6c5f82f7a17af5_10.png)

And then if we take a look， how does that JSON response turn into this text， well。

 if we take a look here。We are fetching。That messages URL。And we're using the promises。

 not a single away were doing。pulling the response back。

 and then we are taking the JSON post parsing of the JSON and we console log that let's view。

 let's do look at the browser tools here， web developerer tools。

Let's look at the console and you see that it says I'm requesting the JSON。Requesting the JSson。

 and then in once the first and second promise resolves， I have this thing I call rows。

 and then I console log it and it's really just an array。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_12.png)

It is an array with all of these messages in it。 And by this point in time， by this point in my code。

 that is a jascript array， not。Not a string right it's the thing that causes it to go from string to a JavaScript array is response JSON。

 this says parse the response as JSsonN and give me back the object that results from that and so this you know at this point this is we've seen this kind of pattern before and we get the JSON data now what we're going to do is we are going to now do document object dom modification。

So the first thing we're going to do is wipe out see this chat content dot div。

 we're going to set its integration HTML to nothing which actually deletes that spinner so that's where the spinner is there and then the spinner vanishes and is replaced by that text so the thing that came from the server as a matter of fact。

 if I do a view source it here。This is a good example of where。

The source and the document object model are not the same team。

 The source that came from the server includes this spinner。

 But if I come back and I do an inspect element here。You see。

That chat content doesn't have a spinner Now this is because the document object model is being changed by the JavaScript and the first thing it does is throws away the spinner and again。

 JavaScript owns the document object model so it can delete stuff it can change stuff and so you sort of saw that highlight happen。

Where it sort of this stuff comes and goes every5 seconds。 It wipes it all out。

 and then it builds it again。 But it happens so quickly。

 We don't notice it as long as it's not changing。 And again， I'm not telling you this。

 like pulling every5 seconds is a great way to do it。 It's the quickest way to do it。

 but it is not a great way to do it。 Okay， there are many other things。

 and you can take an advanced jascript class to learn that。 But so we're starting here。

 We wipe out the content。And then we just loop through rows， which is an array。 It's got a length。

 We loop through it， and we're going to take get element by ID chat content enter HTML。

 and we're going to append this string。 we're going to app print a P tag。

 we're going to append the message， we're going to append a Br2 nonb spaces。

 and then the time and then a s P and strangely enough if you take a look at this in inspect element。

It keeps vanishing， but here you go， you spec。This is coming from my JavaScript。

 I'm building all that stuff， right， and it wipes out every five seconds because that's just how it works。

Okay， so you see that it's going to wipe out and then regenegenerate it， but we if you look above。

 it doesn't even flash， right？

![](img/249a4ce6f6138e185a6c5f82f7a17af5_14.png)

Okay， so then all we've got to do。And we can， we can put a little catch in here。 Hey。

 let's make a mistake and see what happens here。 Let's see if I can put something in this views。

 Let's let's mess this up。And watch it blow up。

![](img/249a4ce6f6138e185a6c5f82f7a17af5_16.png)

So you see it blew up so that was when this catch just blew up and alerted the air and I。

 when you write code， please put this catch in， at least alert the air and the key thing is is what error did we do。

 we just like totally screwed up the view， right？Oh， and let me show you one more thing。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_18.png)

I'll keep this broken for the moment。Let's just hit refresh and let's go into network and hit refresh。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_20.png)

And now it's gonna hit it and you're gonna to get a 500。 if you've got this catch。

 it tells you something。 But to figure out what's really wrong， Like where's the bug in my code。

 you have to come in here and you have to look at it and then you have to look at the response。

 and then you have to move this guy up and you say， oh。

 at line 31 in get infusesed py X Json oh look at that。 It's line 31。 I'm on line 31 So the point is。

 is if you don't put this alert in， you don't even know something went wrong。

 and that alert is sitting right here in the catch。 So again。

 you don't have to make this super beautiful right。

 just this is a good enough alert because it's not supposed to happen。 I mean。

 it only happens when I have a bug in my server code。

 So now I've taken the bug in my server code out and I refresh it and away it goes。

 So this chat this catch here is cheap， cheap insurance that basically said。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_22.png)

![](img/249a4ce6f6138e185a6c5f82f7a17af5_23.png)

![](img/249a4ce6f6138e185a6c5f82f7a17af5_24.png)

![](img/249a4ce6f6138e185a6c5f82f7a17af5_25.png)

![](img/249a4ce6f6138e185a6c5f82f7a17af5_26.png)

It doesn't just silently fail if I just made this a console， let's make this a console log right？

And you're just crew， let's go on console， let's clear it， let's hit refresh。Oh wait。

 and I got and put the air back in， sorry。Okay， so it's working， it's working。 Okay， it's blowing up。

 I got a console log， but the problem is is that。If you're not looking at the console log and you just have this bug in there and you say。

Happy days。Or。Nothing works。And now all we see forever。Is the spinner。

Because the AjaX request is not working。 And if you have the cleverness to turn on web developer tools and see this and go like some funky there and then you go to network and we've got to hit refresh because the JavaScript set time up we haven't talked about set time up we'll talk about that in a second。

When this blows up， you see the 500， and then you have to have the presence of mind to go in here and look at the response and go like。

 oh， that's why the spinner is just sitting there and not working。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_28.png)

Okay， so let me go ahead and fix this once and for all and talk about how the timeout works。

 So let's clear the badness， let's hit refresh， let's have it work。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_30.png)

Come on， there you go， let's go into the console now。

There is one more thing that's going on here and there is an event， right？

ACo of events that are going on。So the first thing that we have to do is we have to get this function update message called。

And so we do that。 we define this function， update message， right and then。It at the moment。

 while our while R Dom is being parse coming from the server。

 we're going to add an event listener Dont content loaded event listener。

 which basically waits until the whole page is finished。 And we're going to call set time out。

 We're going to say， let's run the update message function。 This is a string。

 So it's not calling the update message。 It's in effect。

 registering a string to be parsed and executed。Two seconds later。

 and the second parameter is two seconds later， so you'll see it waits two seconds。

The spinner waits two seconds and then it runs this function updateate message。OSo 01，002。

 now it runs update message， we get the JSON， this code all runs。

 but then what happens is when it's successful and that's when this second promise is properly fulfilled。

 then it calls update message again and oop， don't do that I don't know what just happened there undo undo undo and do undo and。

 oh let's let's go back to the alert okay。So the second promise。Is resolved successfully。

 and it console logs it， and it updates the thing just like we all talked about。

 But the last thing it does is very important。 It says， now run me again for 4000。

 You'll note that I don't start the timer again if I blow up。Like， what's the point？

And that's why if it blows up， it doesn't keep trying。

 I could literally put the set time out down here， but I don't want to。 I mean， at some point。

 this catch is exceedingly rare。RightIt really means I messed up in the server。

 I messed up in the server。 It's not like the world is broke。 Now， if the， you know。

 if the person's network goes down because that network could go down at this point。

 I could lose a connection to the server。And alert will tell me that。

 tell a user that like I cannot retrieve， blah， bh， blah blah， blah。

's hopefully they get the sense that their network is bad。

And and so this is a real as simple as I can make it。 simpleple chat。 nothing's best practicing this。

 I'm using an array for my Json。 I am， I am polling every four seconds。 Don't do any of this， but。



![](img/249a4ce6f6138e185a6c5f82f7a17af5_32.png)

It is a very simple， elegant that brings together a number of these asynchronous ideas and the notion of timers and the notion of fetch and all those things。

 and so it's a good place to start。

![](img/249a4ce6f6138e185a6c5f82f7a17af5_34.png)
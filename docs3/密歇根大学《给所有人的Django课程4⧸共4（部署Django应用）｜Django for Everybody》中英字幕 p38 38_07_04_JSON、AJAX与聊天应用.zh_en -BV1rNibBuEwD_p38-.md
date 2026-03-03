# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p38 38_07_04_JSON、AJAX与聊天应用.zh_en -BV1rNibBuEwD_p38-

So now we're going to bring all this together， and we're going to build a simple multius chat application that moves data through the server using Ajax and Json。

 So the idea here is， we've got a simple chat。And things are going to happen and we're going to use two tabs to simulate two users and the idea is is whatever you enter in the first tab。

 it's going to asynchronously merely appear in the second tab and we're going to use polling to do this and we're going to use poll every four seconds which is a very inefficient way to do this but for now it's the simplest way I can show you in a hurry what's going on every four seconds both windows are making a request to this URL called messages that is a JSson endpoint and they get back an array of the recent messages。

 both the message text and a little nice time indicator like a minute ago or two minutes ago or something like that。

 so this happens every four seconds， and that's why this is not at all best practice not only is it not best practice for that。

 but I used returning an array in JSO and you're really not supposed to do that you're supposed to return an object even if the main data is an array you want an outer encapsulating object。

 but again。

![](img/b5c74425154500cbe4a6abf6e8b62cae_1.png)

![](img/b5c74425154500cbe4a6abf6e8b62cae_2.png)

I'm trying to keep this as simple and short as I possibly can， So if we take a look at the URLs。

pyy and again， I got a nice walkthrough if you want to see this version in walkthrough。



![](img/b5c74425154500cbe4a6abf6e8b62cae_4.png)

I have the main view that's talk and then messages is that a JSON view and I have a little spinner that you can see when it first starts up and then there's a simple model where we've got some text and who typed it in and what time it was created and if there's 70 updating in this case there's no updating but we need the date of the thing so we can say it's two minutes ago。



![](img/b5c74425154500cbe4a6abf6e8b62cae_6.png)

And so if you take a look at the viewss pY， the talk main simply shows the main page and then is done。

 and when we hit the chat button or post button， it comes back to the post and we save the message and then we redirect back to ourselves back to the talk。

So if you look at the template。Talk。htM， you see we have a simple form。

 that's got a text field and a submit button name post。

 and importantly this div ID chat content that has a spinning G。

As it content and you're going to see that we're going to delete this and so one of the reasons I make it wait two seconds is that you can see this when it comes up and you can see the spinner happening。

 but then once the JavaScriptscript takes over it actually deletes the spinner and replaces it with the messages So this div is a placeholder for us to put the chat content which we're going to put in using JavaScript and here's the main JavaScript。



![](img/b5c74425154500cbe4a6abf6e8b62cae_8.png)

![](img/b5c74425154500cbe4a6abf6e8b62cae_9.png)

We have a function called updated message and it does a fetch and it does a fetch to the URL messages cash note storage just says every time I asked to fetch it。

 give me a new copy of it， and then I have a couple of promises the first promise says the response has been started and I'd like to retrieve the response and convert it as if it were JSON data。

 and then the second promise takes as its parameters， the converted JSON data。

 meaning the rows with a Z is an object， which in this case it's an array and so we basically log that so we can see it。



![](img/b5c74425154500cbe4a6abf6e8b62cae_11.png)

![](img/b5c74425154500cbe4a6abf6e8b62cae_12.png)

Then we go and say document getl my ID chat content， that's that div Inter HTMLtmail is nothing。

 that is deleting either the previous list of messages or the spinner。

 so we're going to emptied it out and then we're going to fill it back up。



![](img/b5c74425154500cbe4a6abf6e8b62cae_14.png)

![](img/b5c74425154500cbe4a6abf6e8b62cae_15.png)

So we're going to loop through this set of rows that we got back。And for each row。

 we're going to append a paragraph tag。 So plus equals there is appending to the current inter HTMLtml and we can just treat this inter HTMLtml as a variable right。

 we can read it and we can write it in plus equals means we're appending to it。

 we append a P tag we append the first part of the row。

 which is the message then a Br tag in two non-breaking spaces and then the second part which is how long ago it was which we generated in the server and then a end of a P tag。

 And then we set a timeout so that we do this again in4 seconds，4000 milliseconds actually。

 And then there's a catch that just alerts。 Now the way this stuff usually works is that。

It usually works or it blows up badly and so I just have a catch that says here's the air and hopefully it doesn't happen very often but maybe the error could either be I made a mistake in the server and if you're doing software development。

 chances are good that you're going to make a mistake in the server and that's a reason to put this alert there in the real world once your server code is nice and clean and doesn't have errors in it。

 then they probably lost their network connection or your server went down or something like that in the middle of every four seconds getting this new data。



![](img/b5c74425154500cbe4a6abf6e8b62cae_17.png)

And then at the end we have an Adv listener， Dom contentt loaded， which we've talked about before。

 and we simply run a function to do a set timeout of update message two seconds after the Dom content is loaded and that's what these lines。

 tell us to do and remember that update message doesn't actually call it right there it's in a string。

 and it says after two seconds。

![](img/b5c74425154500cbe4a6abf6e8b62cae_19.png)

Paarse this JavaScript string and run it， and that's what's happening here。

So we take a look at views。 py。 we're doing a get request and this is the one where we're sending a JSON response。

 We're going to retrieve the messages， the most recent 10 messages ordered into sending order by created at and then we are going to process it。

 Now it's pretty common not to just send the objects back。

 we want to do a little processing and so we're sending back the message text and then this natural time which is ajango library that makes up this 13 minutes ago。

 14 minutes ago， we go through the array that is。

![](img/b5c74425154500cbe4a6abf6e8b62cae_21.png)

The list of objects that we got from Django's model。And then we're going to make another one。

 which is the only the pieces we want to give to our front end code。

 and then we return a JSON response with results which is an array which then is serialized into an array and it's actually an array of arrays。

 and that is serialized then into an array of an arrays and sent back to it。



![](img/b5c74425154500cbe4a6abf6e8b62cae_23.png)

![](img/b5c74425154500cbe4a6abf6e8b62cae_24.png)

And then we go back to the code here if you look there that is looping through the data that came back from the messages view in JSON。

 and so you know again， that's what happens， it just every four seconds。

 it runs through and retrieves the JSON clears out that div。

 then fills it back up with whatever they are and。

![](img/b5c74425154500cbe4a6abf6e8b62cae_26.png)

![](img/b5c74425154500cbe4a6abf6e8b62cae_27.png)

If nothing changed， you don't even see a blanket， it all happens so rapidly， partly because。

It's all done asynchronously and that is that we are not actually touching the DOm until we've got the data to replace it。

 and then we do it so fast and we're done and then we give the browser back the thread and then it redisplays。

 which means it's not kind of displaying one piece at a time。

 you are modifying the DOm and that it doesn't update the window until you return from the function。



![](img/b5c74425154500cbe4a6abf6e8b62cae_29.png)

So in summary， JSON is very powerful， and these are pretty short lectures actually it is very well supported and performs extremely well in many languages。

 I mean it's over 20 years old now and it's every language has to be really good at JSON back in the early days youd have to go find a JSON Library now its just built in it's built into the browsers。

 it's built in Python is built into PhP， it's built into everything and so Python and Django and JavaScript have excellent support so it's a great way to build applications。


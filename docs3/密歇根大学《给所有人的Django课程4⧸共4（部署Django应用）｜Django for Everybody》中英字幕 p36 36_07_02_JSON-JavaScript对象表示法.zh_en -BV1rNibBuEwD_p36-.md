# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p36 36_07_02_JSON-JavaScript对象表示法.zh_en -BV1rNibBuEwD_p36-

Hello and welcome to our lecture on Ajax and Json， I'm Dr。 Earl Severance。

 so I'm your professor and I just want to I got a nice Father's Day gift from my daughter and so I'm to thank her I'm wearing it for this particular lecture so we have been doing a whole bunch of stuff with the request response cycle right。

We go in the server， we run through URLs， we enter views， we write templates， we send HTML back。

 and the browser pars that response and puts it in the document object model。

And then most of what we've done has been just sort of fiddling with a document object model with JavaScript。

 but now we're going to take another important step。And that is。

 we are going to do things in the document object model and to the document object model where the JavaScript itself is going to make requests to our server code。

 going to run through the views， run through the URLs and send data back。

 So the difference is we're not just sending markup back HTML is our markup format。🤧咳。

And JSON is our data format。

![](img/953241a537f9a4aedd8d5f4e2f235fe8_1.png)

So the web is pretty old now， we started on 2003。And the request response cycle was pretty cool。

 and lots of software， lots of libraries， lots of languages knew how to talk back and forth across the Internet and get data。

 the question was is， why don't we get something other than HTML。

 And then the argument became what was the syntax that we should use。

 and you can look at my shirt here somewhere here。 right There's my shirt。 You got some curly braces。

 and then you got some slashes and then actually turned out to be the argument。 The argument was。

 whether or not you would use X M L。😊，use XML or curly braces now XML was the first thing and if we hear the word AjaX。

 that x stands for XML， but most of the time we are not sending XML back and forth。

 we're sending JSON back and forth。So the idea of。Moving data across the network。

 we had to agree on a what's called a wire format where you could think of it as the network as if we're watching it on a wire and it's going by。

 what would we actually send。

![](img/953241a537f9a4aedd8d5f4e2f235fe8_3.png)

Because in PhP， we have arrays and Python we have dictionaries and JavaScripts。

 we have objects and Java hass， things like hash maps and array lists。

And the question is what are we going to send back and forth。

 we got to agree on it so that we can write something in Python and read it in JavaScript and similarly write it in PhP and then read it in JavaScript so we have to agree on a wire format。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_5.png)

And XML is one of the wire formats， we're not going to talk about it because that argument is kind of over XML is not bad for documents at rest。

 but it's not a real good wire format， so we'll just pretend that JO is the wire format even though it is a wire format。

The idea is， is that we have to take。A structure that's inside a server， and we have to serialize it。

 which means convert it to a string。 So it's a Python dictionary。

 which is you know object oriented mechanisms that make all this stuff work。

 And then we have to like say， oh， let's turn this into a string because we have to send characters across the Internet。

 And then when we receive it on the far end。 we do what's called desialize。

 And the word serial means that we're sending it kind of one character at a time back in the old days when we use modems and lease lines and things like that。

 see my internet history for some of that。 So we desialize it。

 and it becomes sort of an object in javascript in this case。

 what we're going from Python to jascript。 But the idea is that the wire format is something we agree on。

 And so it doesn't matter what language we're dealing with。

 the wire format is something each language has to be able to serialize to send and desialize to receive。

 So I have a video an interview that a long time ago with a fellow named Douglas Crockford。

 he does not claim he's the inventor of Jason and he's just the。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_7.png)

![](img/953241a537f9a4aedd8d5f4e2f235fe8_8.png)

![](img/953241a537f9a4aedd8d5f4e2f235fe8_9.png)

Person who said， wow， this is a really cool format。 and let's write it down。

 And it's really nothing more than a slight。Adjustment to the object literal notation meaning the constant。

 what a constant is in JavaScript when you want to just assign a constant。

 so we say x equals 22's that constant， but you can also say x equals curly brace。

 something and so he's like， well why don't we just use this？



![](img/953241a537f9a4aedd8d5f4e2f235fe8_11.png)

![](img/953241a537f9a4aedd8d5f4e2f235fe8_12.png)

And he called it JO and he registered Json。org， and it just turns out I really wish I knew the extent to which。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_14.png)

Imitating the Python dictionary syntax was part of the goal。

 in some ways it's almost more similar to Python dictionary syntax when you're doing key value pairs。

When the keys are strings in Python dictionary， so this is some。Legitimate。Javascript code。

 This is a constant。 I could say who equals X， or I could see who equals open curly brace name Col Chuck age colon 29。

 College colon true。 you know， strings in a jurrisbuoleions。

 you can have lists and you can have objects within objects and lists within objects bh blah blah bla。

 bla， bla。 So it's a pretty simple syntax。 I mean， part the part of the thing that Crockford argues is that it's just a syntax that any developer if left alone long enough。

 would would it just invent it。 And I have to agree with that。

 I have to say that this syntax I can't say， whoa， I don't like this。

 I wish I could improve on it somehow。 So the Json syntax is a it's not exactly the same as a jascript syntax。

 It's kind of like， let's keep it simple and have a subset of the jascript object literal syntax。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_16.png)

And so I've got to sample some sample code that you can go play with。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_18.png)

And all it does is it says who equals open curly brace，lah， blah， blah， blah， blah。

 Ex the code I showed you before in console dot log it。 That's all it does。 It doesn't print it。

 It doesn't send it across the network。 It doesn't do anything。 It just consolet logs it。

 And you see that that is the way we define a constant object。 An object is a constant。 and so。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_20.png)

嗯。😊，But that's not so interesting what is more interesting is when we can produce code inside of the server in say Python and then send it to a browser so here we have a very simple view and the sample code is up there on DJfr。

com for you to look at and we are going to have a JSON fun path this is going to be a function style view time sleep is just so that when you play with a sample you can kind it pauses for just a moment normally you wouldn't pause so we just construct a dictionary that's a Python dictionary and again wow。

 it looks a lot like a JavaScriptscript object but if you do it in PhP it looks quite different if you do't job it looks quite different。

 but it turns out in Python in JavaScriptscript they're very similar and then we're returning JSON response and then handing that dictionary now normally when we have a normal HTML page。

 we're sending back on HTTP response。

![](img/953241a537f9a4aedd8d5f4e2f235fe8_22.png)

We're sending a string back， but this time we're sending a JON response and we're sending an object back。

Jango sees JON response and says，  I'm going to set the headers the right way。

 I'm going to serialize this， and I'm going to send this thing out as a string。

And so if you go to this endpoint， JSON fun and you look at it in raw data。

 you see that it's been compressed into a string that's really curly braced and double yada yada now you also see your browser sometimes shows it parsed。

 meaning it's showing it after parsing so you can see the raw data before parsing and then you can actually see the JSON data after parsing it's kind of the same thing as just runs a string and one is an object。

And part and parcel of moving JSON back and forth to the browser is you've got things like the content type。

 which is application slash JSON rather than text/lash HTML。

 and then there's other things like content size， etctera， etc cetera， etc。



![](img/953241a537f9a4aedd8d5f4e2f235fe8_24.png)

![](img/953241a537f9a4aedd8d5f4e2f235fe8_25.png)

So that's about all there is to JSON， it's so simple， it's so elegant。

 so up next we're going to talk about doing a chat app which really brings together a lot of this JavaScript。

 JavaScript objects， JavaScript in the browser and JSON。


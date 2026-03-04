# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p136 28_JavaScript对象表示法(JSON).zh_en -BV1Lr421A75d_p136-

![](img/f8bb76561137cef2aebf329479c2d8e2_0.png)

![](img/f8bb76561137cef2aebf329479c2d8e2_1.png)

So in this lecture， we're going to talk about jascript object notation。 JSO。 Now。

 everything we've been doing lately has been really extending what we're doing in the browser。

 JavaScriptscript talking to the Dom in the previous lecture， we actually had。

 we went back and forth where we sent post data back and brought stuff back Now with JSO。

 what we're really focusing on is this little part right here。

 and that is what we did before was called aha asynchronous， H， H something。

 HP and HTML because we sent HTML back， But really what we want to send is data back and forth。

And especially when we're going to go all the way to the database。

 get some records back and then send them。 We need a way to represent those records that are coming back so we can read them in jaqueQury and then put out like a table before what we did was we would have this。

 we'd get the records。 There's a bunch of records。 Then we write a loop that would write the table。

 and then Don would come out。 right That's how we do it in PP。

 But what we're going do is we're going to move this little loopy bit。

 We're going to move that into the browser even。 So now we're going to send a request in。

 we're going to get a page back。 If then this page is going to make a request。

 It's going to do loopy stuff。 sendend the data。 and then loopy stuff here to actually print the table。

Whether the loopy stuff happens in the server or happens in the browser。

It's six and1 half a dozen in the other， but I'm showing you now that you can move this back and forth。

 and the question we're asking is， what is the format？Of the data going back and forth。

And the answer。And 95% of the situations is JO。

![](img/f8bb76561137cef2aebf329479c2d8e2_3.png)

Javascript object notation。So the request response cycle is something that by now。

 I hope you understand and the market in the early 2000s understood it as well。 We knew what it was。

 we were starting to sneak stuff back and forth the concept of X HtTP request was actually I think the Internet Explorer was the first one to allow ja to make requests back to the server and originally the idea was that XML would come back because we were sort of arguing that XML was like the greatest way to represent data ever。

 so you would send a request back and you get XML back that led to a thing called AJX。



![](img/f8bb76561137cef2aebf329479c2d8e2_5.png)

Asynchronous JavaScript。

![](img/f8bb76561137cef2aebf329479c2d8e2_7.png)

And XML， I think is what AjaX stands for。 So this Ajax pattern of request response cycles initiated from JavaScript and returning XML。

 but XML turns out to be kind of a painful format by the time it's all said and done and so we kind of argued about what format of this return data is for a while。



![](img/f8bb76561137cef2aebf329479c2d8e2_9.png)

And so the idea is is that you know in the server you might be running JavaScript or PhP or Python and then browser。

 you might be one and it might be JavaScript Java or whatever。

 and there's different sort of each of these have different ways of thinking about key value pairs。

 each of these languages， but if we're going to send the data across the internet。

 we need to agree on what's called a wire format that the notion that there is a known syntax that can be translated into a PhP array or translated from a PhP array or translated into a Python dictionary or from a Python dictionary or to and from a JavaScript object。

And so the question， this is the wire protocol。 and' it's because these used to be wires。 Now。

 they're probably fiber optic， but the Internet is a bunch of wires， right， if you were to watch。

The characters going by on the Internet。 What would you see， Curly Bra， new line， and A M E。

 So the wire protocol is literally the exact characters being sent between the system。

 It's not how these are represented internally in any of these things。

 because that's in the memory of the computer。 And so there's sort of the internal representation。

 The wire format is an external representation。

![](img/f8bb76561137cef2aebf329479c2d8e2_11.png)

And so。JSON is the one we're going to talk about right now XML would be the other one and you'll run across XML once in a while。

 sometimes XML is a good idea， but the idea is is that say we have an array of stuff inside PP that has a particular shape and then we do what's called serialize on the way out of PhP sending across the internet we take whatever this is and we move it into the wire protocol。

 So then we send the wire protocol across the internet and then in the other end we receive the wire protocol and then we parse the wire protocol。



![](img/f8bb76561137cef2aebf329479c2d8e2_13.png)

You could think of this as in code。Format。The notion of taking something you know and in coding it or in formatting it in the wire protocol or parsing it。

And the nerd term for this stuff is serializing and desializing。

 serializing is the preparation of an internal structure to the wire format and decsializing is receiving the wire format and creating a different structure。

 and so we're going to take a PhP array and end up with a JavaScript object。

 these are different things。And what we're going to find is that。



![](img/f8bb76561137cef2aebf329479c2d8e2_15.png)

JSON is so well supported in PhP， it's just like a line of code。

 and it's like one or two lines of code especially if you're using JQury and JavaScript。

 and it's so easy after a while you kind of don't even notice that you're doing it。

 the notion that you can take a PhP array and a couple lines later turned into a JavaScript object that came across the network。



![](img/f8bb76561137cef2aebf329479c2d8e2_17.png)

If you' could imagine how hard that was to do in like 1999 compare it to today。

 it was infinitely difficult because we didn't even have a wire protocol in 1999。

I always like to talk about the people that invented this。 and Douglas Crockford。

 we have a video for Douglas Crockford。 He's sort of funny in his own way。 He's a really smart guy。

 And part of his humor is being smarter than you。 And there was point in time where there was a Twitter feed。

 It may still exist for his beard。 And the idea was that Douglas Crockford's beard is smarter than most programmers on the planet。



![](img/f8bb76561137cef2aebf329479c2d8e2_19.png)

There's a cool cool video that I've got。 And I encourage you because again。

 it's their personality of these people sort of is reflected in the kind of technologies that they invent。

 Now， Doug Crckford would be the first one to tell you that he did not invent Json。 He discovered it。

 He said it was just there。 It's just in jascript。 So what Json， the reason it's called Json。

 is it's the way we write Constance。 And if you go all the way back to the arrays。

 the arrays lecture。 I said， you know， X equals square brace，a， Y equals curly Bra， you know， blah。

 blah，a blah， bh。😊。

![](img/f8bb76561137cef2aebf329479c2d8e2_21.png)

That's JO， kind of reduced it a little bit。 and he basically said the syntax that we use to define JavaScriptscript constants is also the wire protocol。

 So JavaScript， it's a little easier for JavaScript to understand JO PP has to work a little harder。

 Java has to work a little harder。 All the other languages have to work a little harder。



![](img/f8bb76561137cef2aebf329479c2d8e2_23.png)

But we had to pick something。 And so JavaScriptscript JO was really good and it's。

You you could subtly change it。 You've got to be able to have lists of things and key value pairs。

 And other than that， the rest of its syntactic craft。

 And so he took the object literal notation in jascript and said that is a wire protocol。

 whether you're using Java or C plus plus or whatever。 Let's just use that as a wire protocol。

 And he gives a really good explanation in this video about why Xml is what it's good for。

 what it's bad for， don't assume that JSson is great for everything there are some things like word documents are represented in Xml。

 PowerPoins represented Xml because they're hierarchical structures。

 Hiercrical structures is not the best thing for JSson。

 But if you're just moving an array of stuff back and forth。

 Json is the absolute 100% answer and it's really quite wonderful， He talks about how he convinced。



![](img/f8bb76561137cef2aebf329479c2d8e2_25.png)

The world that Json was a thing。 And they were like， oh， there should be a standard。 And he's like。

 well， it jascript。 That's the standard。 And so he created Json。 org。

 And he just documented it's a couple pages。 and the world has beat a path to his doorway。

 And he coined the term。 And he just said， hey， look at this thing。 And then finally today。

 it's just assumed to be part of the profound infrastructure of all distributed computing as that Json is available。



![](img/f8bb76561137cef2aebf329479c2d8e2_27.png)

So it's really cool because it had sort of very humble beginnings。



![](img/f8bb76561137cef2aebf329479c2d8e2_29.png)

And so up next we'll have at a little bit of example code and how we can use JSON and talk back and forth both in PhHP and in JQuery。


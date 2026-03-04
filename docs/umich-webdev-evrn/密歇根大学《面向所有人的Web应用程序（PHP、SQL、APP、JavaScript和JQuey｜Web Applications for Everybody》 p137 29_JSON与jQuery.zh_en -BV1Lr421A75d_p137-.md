# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p137 29_JSON与jQuery.zh_en -BV1Lr421A75d_p137-

![](img/b44945fd4cb2fd258edc54e5b42370ae_0.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_1.png)

So I'm going to go through a very a couple of very simple examples of Json， JQury and PhP。

 And it's another one of those things where I don't want you to blink and miss anything because it turns out to be super simple。

 but underneath it， there's amazing things happening。 So first， let's remember that in ja。

 we use objects。 they're not exactly associative arrays。 They're key value pairs。

 and they can be accessed with either the sosociative array syntax or object syntax。

 So like X sub bob。Is the same as x quote， Bob quote。

This this is the kind of the this is the O O syntax and this is the array seemingly array syntax。

 this is what's really going on。 And this is kind of a shortcut to that same thing。 So either one。

 and just has you're reading code， some programmers use one to exclusion and the others use the other to exclusion。

 I tend to use the dot format when I can， but sometimes you have to use the double quote format。

 So just remember that those two syntaxes in jascript mean exactly the same thing They're not a different thing。

 They're the same thing。

![](img/b44945fd4cb2fd258edc54e5b42370ae_3.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_4.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_5.png)

So here is a little bit of example code， here is a constant object。

And it's it's not that different than those objects we've been creating。

 It's just that the attribute， variable， golf， tennis and ping are being set in this constant。

 So there is an object being created with three instance variables， golf。Tennis。Ping。

 and then there are some strings in here。 So this is really an object。

 and it's being assigned into the variable balls。So that's an object， it's a real live object。

If you do a console dot dur of it， you actually in the console have a nicely expandable thing where you can sort of look at everything。

 And this is the two syntaxes。 This is kind of the O O syntax where you can assign a new soccer thing。

 right， balls dot soccer。 That's kind of object name balls with a attribute。Object attribute。

 object dot attribute。 That's the common way in most objectary languages to do this。

 But then we have what is kind of like， I'll put in quotes， the associative ray look。

The associative array look is Bas sub quote Larosse， quote。These are equivalent syntaxes。

 Don't get stuck on the fact that somehow there's something different going on。

 And I just emphasize that because it took me a while to figure this out myself to go like， whoa。



![](img/b44945fd4cb2fd258edc54e5b42370ae_7.png)

I kept。The syntax is so different looking and to me in PhP。

 they mean very different things and in Python and other languages。

 they mean different things where in JavaScriptscript they don't。

 And that just threw me for a loop for a while。 Maybe they won't throw you for a loop at all。

 Maybe you're an expert in this。

![](img/b44945fd4cb2fd258edc54e5b42370ae_9.png)

So let's take a look at some JSO syntax， it's really just JavaScriptscript syntax So this is we're making an object。

Begin end。Key value， key value with colon。 you can have different types of things。

 They don't have to be numbers can be Boolean， and you can even have a list， right。

 So this says the attribute offices maps to a two element list of two strings。

 and then you can have skills mapping to an object within an object， right。

 So we got this object and then in skills。We have another object and that has C plus plus and Python。

 So these are key value pairs， key value pairs inside that。

 And so it's just you can just construct these like you can in any programming language you can have in PhP。

 you can have arrays within an arrays within arrays and they can be a linear array and a key value array。

 but this is an object。

![](img/b44945fd4cb2fd258edc54e5b42370ae_11.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_12.png)

Object， this is an array。And then this thing here is an object。

And I just I I keep emphasizing that because I just want you to。

Not confuse the fact that objects and arrays are not exactly the same thing。

And so if we take a look at some JavaScript that just runs this stuff， right， you know， here we go。

 here's a machine mail we go into script， you can just type this stuff。

 This is just JavaScript code that's aneable this is an executable assignment statement in JavaScript。

This happens to be Json syntax and the jascript constant syntax。 That's like saying who。

Equals 42 semicolon。 Well 42 gets stuck into who。 It just so happens that it constructs an object with the all key value and then assigns that into who。

 So just kind of just doubly emphasizing that this is just a syn It's a wire product。

 We haven't made it a wire protocol yet。 It is still just the jascript constant syntax。



![](img/b44945fd4cb2fd258edc54e5b42370ae_14.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_15.png)

Now we're going to make it a wire protocol。This is an important slide。

 It would almost be easier if this was 40 lines of code on this slide。

 because then you would expect that it's difficult and challenging and amazing things are happening。

 This is amazing。It's just like four lines of code。 Okay， so。

 and I' and I'll go through this in a demonstration as well。 In addition to these just these slides。

 So we're going have a file called Json dot P P。And so sleepep2 just makes it so this thing slows down a little bit so you can see what's happening as you're watching it in your developer console。

If we're going to send JO back to the browser， we want to tell it the content type。

 And if we go all the way back way， way， way back， content type can be text， it can be HTML。

 It can be a Jpeg， It can be a PNG。 So this is a response header that tells the browser what it is that this next blob of stuff is。

 and we can tell it this is Json。We tell it's UTF8 in case we have Asian characters or whatever。



![](img/b44945fd4cb2fd258edc54e5b42370ae_17.png)

And so that's just that's a header and just like anything inside PhHP， we're in PhP no。

 anything inside thing in PhP before you produce any output， you've got to set all your headers。

 so that's why that's first。

![](img/b44945fd4cb2fd258edc54e5b42370ae_19.png)

So now we have some PhP code now really this will do something maybe like read some stuff from a database。

 but we don't worry about that right now For now， we're just going to make an array。

 This is a PhP array first maps to first thing， second maps to second thing。

 This is when we're inside of PhP， and then we're going to serialize。

And then we got the wire protocol。We we're going to send the wire protocol and then we're going to receive that。

 and then we're going to parse it in JavaScript。 That's exactly what we're doing in this picture right now。

The act of serializing a PhP array uses a function that's built into PhP called Json Underscoring code。

 You pass in array。 It can either be a linear array or a key value array， and it automatically makes。

The right Json in this case， it's a key value array。

 so it makes a Json object with key key value value。Right and then this。This。Is what gets echoed。

 I mean， literally the output is this when you look at it， that is serialized version of a PhP array。

Getting sent out， if you just hit this page， you will just see this in your browser。

 That's what you'll see。It'll actually be all scrunched up， but then you can pretty print it。

 there's that's called pretty printing when you see all the pretty little spaces because Json doesn't care about spaces either or new lines。

 So if you see ugly Json that's like curly braced or curly brace。Just Google Pre print。

 and then paste that in， and it'll put it indented。 So it's actually readable。

 They tend to not pretty print this stuff when we're sending it back because mostly it's being parsed by code。

 not by human beings。 And so we tend to copy and paste it and then pretty print it。



![](img/b44945fd4cb2fd258edc54e5b42370ae_21.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_22.png)

Okay。This PP code runs， says Im must send you some JSON， creates an internal structure。

 this could be lots of code， serializes it and sends it back。

That's the request response cycle on the PhP side。 That's what that does。

Now we're going to talk about the JavaScript side， what we're going to do on the JavaScript side to pull this stuff in。

And I'm not going to put this in on click method， I'm just going to do it and show you how it works。

So we got some page， blah， blah， blah， indexed。phP。It's got some stuff okay。

 and we're going to document that ready again， this is idiomatic that says run this code once the document is finished loading。

Think of that as after the slash body tag and after the slash HTML tag。So after this is all done。

 I want to call Doll get JSON before we did Do post。And that sent post data in and got HTML back。

This is going to ask for a get to a get request and expect J to come back Okay。

 so then we're going to specify the server URL。Which is this code right here running on the server。

And this knows that what's coming back is JSO and so it's going to decsialize it。

It's going to decsialize it。And then pass the decsialized data into our code。Remember。

 this is the code that runs when it happens， it's going to pass the dealized code in。

 this is a jascript object。 It's not this string。 So you got to separate the wire protocol。

 which is just a string of characters from the post decalized thing， which is a live ja object。

 So data in this case， is a live jascript object。 And so I can print out data dot first。

 which is this thing right here。

![](img/b44945fd4cb2fd258edc54e5b42370ae_24.png)

![](img/b44945fd4cb2fd258edc54e5b42370ae_25.png)

Like holy crap， that's just like so amazing。So let me see if I can walk through this。

So we're in the browser， we come in。We do Do get JsonN。So we send a get request。Into Json。 PhP。That。

Could do anything Talk to the database。 I'm keeping this simple， right， It creates a thing。

 It serializes and then out a string， curly brace and all that stuff。 This is the wire protocol。

And time is passing here， right， So time is passing。 So this is asynchronous code that's waiting。

For this to come back。 But before it comes back， it gets decialized。 And so the code that runs。

This is being passed into data。Is already dec serialialized。So the notion of retrieving it。

 waiting for it to come back， serialization， Deialization， this is the serialization。

This is the D the desialization is actually just built in get Jasonson。

 It desalizes it before it gets back to us。 So that's like 1，2，3，4，5，6，7，8，9，10，11，1213。

14 lines of code。

![](img/b44945fd4cb2fd258edc54e5b42370ae_27.png)

And like I said， this would be thousands of lines of code 10 years ago， 15 years ago。



![](img/b44945fd4cb2fd258edc54e5b42370ae_29.png)

It's really simple。 Under every single line of code here， because as soon as we understand this。

 we're going to go and make far more complex bits of code。 And so you got to understand this。

 So don't just sit there and go like。Yeah I'll figure this out later。 no。

 because later I'm going to send you this much code and it's going to do this four times。

 and then we're going to talk to database， et cetera， et cetera， et cetera。



![](img/b44945fd4cb2fd258edc54e5b42370ae_31.png)

So now let's talk a little bit about how we can turn this into a simple chat tool。



![](img/b44945fd4cb2fd258edc54e5b42370ae_33.png)
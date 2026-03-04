# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p86 16_PDO错误处理.zh_en -BV1Lr421A75d_p86-

![](img/4e3c82116e5a9cecdce1b129edc56293_0.png)

![](img/4e3c82116e5a9cecdce1b129edc56293_1.png)

Okay， so one of the weird things about PDO is how error handling happens。

 meaning that there's all kinds of things， everything I've done so far。

 other than like when you made your P。 PhP work， everything I've done so far has pretty much been syntactically correct。

 so I want to talk a little bit about the kind of things that can go wrong。



![](img/4e3c82116e5a9cecdce1b129edc56293_3.png)

And so this is kind of going back to where I was saying that you can have different air modes。

 and so this is air mode warning， it can give you a warning， it can blow up。

 I prefer the one during development that it blows up。And so here is a perfectly legit thing。

 It's going to take a user ID from the get， you know， right here， it's a get parameter。

 it's going to take the user ID， it's got a substitution variable X， Y， Z， It runs。

 so this is all good， right， It doesn't blow up。But now。Let's make a mistake。

 So this is a kind of a mistake here。Okay， this is a mistake where I've got this in my SQL and in my execute。

 I tell it that。 So this is going to blow up。But because I've got error mode warning。

 it doesn't actually stop。 This is failing。 this statement right here。

 right that says P execute in parameter number。Do not defined inve parameter on error line 9。 blah。

 blah， blah。 These aren't the best of error messages。 But this line right here is blowing up。

But the problem is is that the fetch fails。 This is a kind of a non fatal error。

 This should blow up but it keeps on going。 And so it comes down here and still says user ID not found。

 So if something so badly wrong this blew up， putting on a warning is really a bad strategy okay。



![](img/4e3c82116e5a9cecdce1b129edc56293_5.png)

And so this is why I prefer air mode exception， and you'll see in my P。

 PhP code that I'm always doing error mode exception Air mode warning is one way。

 Air mode silent is the default mode that is really bad。That's why I want you to set it every time。

 An air mode warning is almost useless。 You can check with an if statement at the end。 But really。

 if you got a syntax error in your S Q L or something that bad。

 you might as well just blow up because you can't really recover from it。

 You just go back and fix it。 So that's why I suggest you always use air mode exception。



![](img/4e3c82116e5a9cecdce1b129edc56293_7.png)

And so if I turn error mode exception on， which is my recommendation for my database。

 So it still gets the same thing Unval parameter， not defined。 It blows up and it dies。

 which means it's it quits right there。 This is a die。 It stops。

 and it doesn't run the rest of this code。 And so that's what I like。 because really。

 this is a syntax error of the S QL。 P P can't know because it's valid P P， but it's not valid SQL。

 And so that's why I want you to just set this in your P dot P P。All the time。Okay。

 just set it and forget it。Now， you can do a try and accept and you can catch these things and sometimes it's really important for you to do that because sometimes these things can print out data that you don't want to show to the end user and so you can put a try except around these things。

So now I've got to try accept， try catch around this thing， so I told it I want it to blow up。

 but I've also told it that I want to catch the exception。So this runs， this is okay。

 this blows up because this is where it detects that there is in parameter。

 and instead of coming down here， it comes to our catch spot。

 and I get an exception variable because it passes the exception that caused the explosion inside here。

 it blew up， but it sent us back a little little bit of a breadcrumb as to what went wrong and we can say get the message。

And that gives us this message right here。That message comes out and I print that out and then I return so I don't。

 I don't， this is a way to get out of this script and if it worked。

Which iss not going to because it's totally broken。 It continues and runs。

So sometimes you want to do a try and a catch of those exceptions and then print your own thing out。

Now， the interesting thing is is when you're in production。

It really doesn't do much good for your user to see an error message like this。

 because you are the developer in here。 This is you。 And then your end user is seeing this， right。

 So the user is using your application someday， we're not just writing applications for ourselves when we're developing。

 We're seeing the application and error messages a really helpful， but。

When we're showing it to users， you don't necessarily want to show these because like this can have sensitive information。

So in production youll sort of want a different pattern。

 so what you do in production is you turn on exceptions， you do a try。

 of course this is constructed to blow up so it runs the catch。Okay。

 and the exception comes in and the thing that we show our user， we send this to our user。

So we say internal error， please contact support。But then what we do is we put an error log message and we've talked about error logs before。

 an error log message is sticking a message in the log， the file we can go look at later。

And what it does， it's， it's like I'm saying， oh， I'm coming from this file error 4 dot PhP。

 And then I take this message， and I print it out， and I stick it in the log。

 So this does not go to the user。 This goes to the log。 And then I quit。 So now I， you know， you'll。

 you see this all the time when youre on applications is like。



![](img/4e3c82116e5a9cecdce1b129edc56293_9.png)

Unknown internal error。 Hopefully， it's logging a bunch of stuff so developers can say， whoa。

 I can see what's going on。 So this is way better to log the errors than it is to actually display them to users unless you're the developer and developer。

 you can be watching log anyways。

![](img/4e3c82116e5a9cecdce1b129edc56293_11.png)

And then remember where the logs are at。 Well， the logs are at。 you can do the PhP info。

 and you can look for the string error log underscore log， and then you can find the absolute path。

 I have in running mapamp， and this is a Macintosh。 and it says that is where the logs are stored。

 app slash applications， map logs P P error log。 So then I can go take a look at that file。

 And that's where I will see those errors。 So under different scenarios。

 You have different places for them。 There's this really cool thing that you can do if you have a window。

 And this you'll see me when I'm coding。 I have a tail running of the log。

 and there's this thing called tail it's on Linux and Mac tail minus F。😊。



![](img/4e3c82116e5a9cecdce1b129edc56293_13.png)

Takes and looks at the alog file， and it just sits there。 And if a new line gets shown。

 it adds to the end。 And so you can dynamically watch it。

 you don't to keep opening it in a text editor。 you can use tail。 And on Windows。

 you might find it interesting。 I don't know if this is free or not， but you can find a Windows tail。

 and that's super useful so that you don't have to keep every time something goes wrong。

 I just like to keep a tale of the a log going in a window somewhere off to the screen or if I got two screens。

 I have the tail on on one side of the screen。

![](img/4e3c82116e5a9cecdce1b129edc56293_15.png)

And so this is what it looks like sort of in my screen， the way I do it is， you know， I've got。

 I'm in the logs file and I tail minus FPP errorlog。

 and then it just sits here and then when something goes wrong。When something goes wrong。

 Air 2 is blowing up， whereas's Air 4 yeah， Air 2， So this is just showing me the errors but this is showing the stack trace。

 showing me all kinds of great stuff。 Oh， and here's Air4 sorry， here's Air4。 PhP。Right there， Air4。

 PhP。And so it blows up， tells me I an Air 4。 PhHP。 And then it gives me that error message from it。

 but never shows it to the user。 That's， that's the cool thing about logs is that you never show this to the user。

 But you can come in later。 or while you're developing just watch it。

 So developing and watching the log at the same time is not a bad strategy at all。Okay。

 so we've sort of zoomed through a whole bunch of things where we have got to the point where we make stuff in a database。

 we've figured out how to use PDO to make a connection and send data into the database。

 retrieve data from the database， and here at the end we sort of looked at some of the more subtle details of dealing with database errors in the PhP code that we write。



![](img/4e3c82116e5a9cecdce1b129edc56293_17.png)
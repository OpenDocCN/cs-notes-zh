# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p28 02_01_06_理解模型-视图-控制器-MVC.zh_en -BV1Kt421V7EE_p28-

Now I want to talk a little bit about a concept Model view controller。

 It's not super essential to understanding how everything works in web servers。

 but it's a great set of terminology that we use among web developers And I think as you move into your role as a web developer you ought to understand this。

 So this is a picture of the request response cycle at the bottom we have the browser and top we have a web server。

 talking on port 80。 the user clicks on a page， clicks on a link。 the browser intercepts that link。

 opens a connection up to the web server sends a get request the web server does its work and returns a web page。

 And so that's sort of the basic request response cycle。

 And now we're going to as in much of this class really expand what we're going to do when we're in that web server。

 So that's where we're going to take a look at this。



![](img/41ca20ead04e378f06208927b75aa780_1.png)

![](img/41ca20ead04e378f06208927b75aa780_2.png)

![](img/41ca20ead04e378f06208927b75aa780_3.png)

So basically， model view controller is really a set of terms that allow us to say this。Aspect。

 this part of the work that's going to be done in the web server， it's either the model。

 it's the view or the controller， and so it the most value that it has to say oh that part right there。

 that's controller so model view controller is independent of the programming language that you use independent the operating system that you use。

 it's pretty universal across is a concept is an architecture has a way of talking about web servers。

So the three parts of it， it'd be probably better to call it controller view model or。

Model controller view model or something like that。

 but model view controller rolls off our tongue better。

So the definition in my mind of these terms is the controller is this sort of abstract idea of what happens next。

 what is the sequence of events that happen， and then where do we start from。

 what do we do when we get a request， and then afterwards， where do we go at the end of that。

The view is all the stuff we see。 It usually is at the end of the request response cycle。

 We produce a view and we return the view back。 And one of the things that the request response cycle often does is either interacts by storing data in a database like an insert。

 or it edits something and puts it in a database or it just reads stuff from the database and shows it to us。

 in the view。 And so that's called the model。 The database itself and sort of the notion that we have persistent storage inside the application that's what we call the model。

 The view is what we see and the controllers kind of the glue that puts it all together。

 So the controller orchestrates all this stuff。 And so sometimes you don't say that's the controller。

 but the controller is like several places and the actual shape of your application。



![](img/41ca20ead04e378f06208927b75aa780_5.png)

![](img/41ca20ead04e378f06208927b75aa780_6.png)

So when we receive a request， we have a number of tasks that we often have to do for each request。

 sometimes if it's like a form that's been sent to us， we have some data that we have to receive。

 validate and then process， and then stored in a database maybe。

 and so that's often thought of as the model work。Then once we've done that。

 we make a decision like I stored this。 Where do we want to send the user up do we want to show next what page to show next。

 Maybe we show them you know a thank you page or maybe we send them back to the top page of the application And so once we know what page we're going to send back to them and that page has some data that we might have to pull from the database and so we retrieve that using the model and then we produce perhaps using a template some HTML response and then put it back So these are the four typical steps that we break down to say in comes an HTML request first thing we do is if it has data that we're supposed to do something with。

 we handle it maybe store that data in a database then we talk to the database and retrieve more data to produce the next output that we're going make。

 and then we produce the HTML or the other form of output and we send it back to the browser。



![](img/41ca20ead04e378f06208927b75aa780_8.png)

![](img/41ca20ead04e378f06208927b75aa780_9.png)

And so if we take a look at this in our Django application， the Django application。

I pretty much a model view controller application in that you know the routing is very much the controller。

 it is that which we it's like here comes a URL， it's a request for something。

 where do we go and so when you write URLs。pyy， you're informing the controller so the URLs。

pyy I would say is part of the controller action。

![](img/41ca20ead04e378f06208927b75aa780_11.png)

The controller activity the views is named the view。

 so the view is is a little bit controller in that sometimes the view is storing some data in the database。

 sometimes that's the job of the view here comes some data before the view produces the next。

Output it actually has to store what came in on this request and then the view will do some controller activity like it might decide。

 you know I don't want you this is the wrong page now that we've processed your data I'm just going to send you over to some other page that's kind of controller activity so it might say I'll store the data it might see here can yeah so it might say you know here I go I'm going to store some data and then I'm actually just going to send you to a different place I'm not even going to give you an and I'll talk about that redirect that's called a redirect it a bit。

Sometimes there is no data and so sometimes you get some data you route it to the right view and maybe some data has to be retrieved from the database merged together and result is processed。

 So when we think of views do Py that is to me。Both the controller and the view production。

 So sometimes it's making decisions about where to go next。

 Sometimes it's just handling incoming data or sending data out and similarly， the models。

🎼Is taken from Model view controller because the models do py is where we basically do all the work to talk to the database。

 whether it is storing stuff in the database or retrieving stuff in the database。

 we use the django model capability to implement the concept in model view controller of models。

 So just a quick summary I like to think of URLs do py， and some of the use do py as the controller。

 The models， of course， is all the things that talk to the database。

 And then the views are like the second half of views do py。

 So produce using templates and forms do py， and et cetera， et cetera。

 that produces the output and send it out。 And so that's how I map the model view controller onto the django architecture。

 And again， Django architecture was probably inspired by the model view controller。

 and that's why it takes some of its names of some of its capabilities from the model view controller concept。



![](img/41ca20ead04e378f06208927b75aa780_13.png)

![](img/41ca20ead04e378f06208927b75aa780_14.png)

![](img/41ca20ead04e378f06208927b75aa780_15.png)
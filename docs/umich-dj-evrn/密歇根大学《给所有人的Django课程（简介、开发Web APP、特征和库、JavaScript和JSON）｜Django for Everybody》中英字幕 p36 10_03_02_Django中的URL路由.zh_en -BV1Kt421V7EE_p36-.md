# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p36 10_03_02_Django中的URL路由.zh_en -BV1Kt421V7EE_p36-

So now we're going to start producing the actual output of our application and the views and using templates and there's a lot to cover here So up till now we've been starting to talk about URLs。

 which are simple it says when you get the request the URL of this format。

 choose a view and send it to that view we're going to talk a lot about views。

 Py and templates and upcoming like you' talk about forms and we spend a bunch of time talking about models Py and how the models can talk to Python code。

 talk to the shell， how the models can inform how we write to the database and how we read from the database So we're starting to fill parts in as we put the views together we're really starting to really create our entire application and I know it's taking a while to get to the point where we can update get to the point where we see the whole thing So I just want to say that from time to time wherever you have DJ4 samples。

 whether it's on your laptop or whether it's on Python Pyon。



![](img/fbe7467db4f5f2daa8bd0765a8edb881_1.png)

![](img/fbe7467db4f5f2daa8bd0765a8edb881_2.png)

![](img/fbe7467db4f5f2daa8bd0765a8edb881_3.png)

![](img/fbe7467db4f5f2daa8bd0765a8edb881_4.png)

Anywhere you should do a gi poll from time to time because I'm always working on these samples and I want you to make sure you have the latest copies of these samples。

 sometimes I add little bits I don't change the samples but I add bits of documentation as I'm like。

 oh I should have added that。

![](img/fbe7467db4f5f2daa8bd0765a8edb881_6.png)

So views are like the core of the application， I mean the URLs find their way to views。

 models tend to serve the needs of views， act as this layer to allow views to write and read the database and so the views。

 Py has a model aspect and it handles incoming data when we get the forms and post data then we copy that into the database the views。

 Py decide sometimes whether or not to send the user to a different screen or if it's going to produce the actual screen in the HTML it produces that HTML often using template and then sends it back So the views are where the work really gets done and what you see is you write a lot of code in the views you write one line in the URL few lines in the models file and then lots of stuff in the views and I consider the templates kind of part of the views as well。

So the first thing that Django does when it receives an incoming document， a request for a document。

 it basically parses that URL and the first thing after the domain name is generally the application so remember that Django has a project and then underneath that there's one or more applications and each of the DJ3 samples you see lots of application。

 each application kind of to show a little bit of sample code for a topic。

 and so second that second part of the URL that is the application name in for intents and purposes it's also the folder name within the Django project。

Now within that， usually the next chunk is the view and so that view within an application。

 the view within an application is。Defined in URLrs py and then after that there are two kinds of parameters。

 one is like a key value parameter that comes after a question mark， it also uses ampersss for that。

 and then sometimes we just put after slashes this is more of a rest style URL that's very pretty and you put the parameters right on the URL rather than the question mark which is sort of the old school for doing all this stuff。



![](img/fbe7467db4f5f2daa8bd0765a8edb881_8.png)

So there is this thing in Django called the URL dispatcher I sort of call it router on my picture。

 It's basically to get you to be able to define the URLs and how those URLs are to be parsed and handled and how those URLs to be routed to the various bits of view code。

 and so we do this in URLs Py。 There are three basic patterns。



![](img/fbe7467db4f5f2daa8bd0765a8edb881_10.png)

First， you might route a particular URL pattern to a predefined class。

 and you'll see the example thats coming up， or there there's sort of functions。

 really old school function that take， this request。

 which which is an object that captures all of the data， the parameters， the URL。

 whether it was a secure request or not， what host it came from what's the IP address it came from all that stuff is wrapped up into this request object。

 which we'll talk about in a second， and that view function looks at that request object decides what to do。

 talks to the database， maybe and then sends back some a response。

 whether it's a redirect or some HTML。And the function is kind of the low level thing。

 but you can also then define a class and defining classes as we'll see is really quite nice。

 the classes have methods like forgetge and for post depending on the kind of incoming HTP request that we're handling and it also in those methods the request and any other URL parameters can also be sent in。



![](img/fbe7467db4f5f2daa8bd0765a8edb881_12.png)

So let's take a look at a sample URLs。poui from viewss and we see examples of all three kinds of these routes。

 URL patterns is a global variable， it's just a list but it has very special meaning。

 this list has very special meaning to Django。

![](img/fbe7467db4f5f2daa8bd0765a8edb881_14.png)

You see these path commands， and there's other ways to describe these things。

 and then you have the path and the blank path means sort of just slash right after the application name。

 And then we have which view to send it to。 And so this template view as view。

 this is basically to save you from writing code。 If all you want to do is take a template out of the templates folder and return it。

🎼So you don't have to write your own code in views Py。 And so this it's already there。

 And that's why we go into Django views's generic import template view。 And we're gonna to say。

 you know what I'm gonna write I mean I wrote this I wrote that template and I just don't want to write the code to go send that re just read that template and send it back。

 And so this is a predefined bit of Django that does this for us。

 So of the more old school thing is this syntax right here and basically from dot import views pulls in views s views do py and then this you will see our functions inside there。

 and then these are classes also from our views do py for this particular application and the syntax is a little weird this is the module we imported。

 this is the class from that and then as view is a static method that returns a function that then can respond to the incoming requests。

 and we'll see these as we。

![](img/fbe7467db4f5f2daa8bd0765a8edb881_16.png)

Go through these。So up next we're going to actually look at theview。pyy and take a look at the views。


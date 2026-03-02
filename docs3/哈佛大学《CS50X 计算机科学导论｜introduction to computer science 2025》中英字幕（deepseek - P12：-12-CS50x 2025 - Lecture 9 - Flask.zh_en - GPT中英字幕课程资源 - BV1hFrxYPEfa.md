# 哈佛大学《CS50X 计算机科学导论｜introduction to computer science 2025》中英字幕（deepseek - P12：-12-CS50x 2025 - Lecture 9 - Flask.zh_en - GPT中英字幕课程资源 - BV1hFrxYPEfa

![](img/c0e4be0df203b599d64dc2c7b3218c55_0.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_1.png)

🎼Yeah。Alright， this is C S 50。 and this is our last week in this year studio as we focus finally on web programming。

 using not only Python， but a framework within Python called Flask。

 and combining with web programming H Tl， C， perhaps some jascript and so many of the ideas that we've been exploring over this past several weeks。

 Indeed today is really about combining all of those various building blocks so that ultimately you can build something of your own。

 not only for this week's problem set， but perhaps if you so choose for your final project as well。

 Now， let's consider where we left off last time， which was introducing H TTP hyperpertext transfer protocol。

 whereby we introduced you to how the browsers of the world and the web servers of the world intercommunicate using H TtP and a whole bunch of other protocols underneath those like I and TCP in particular。

 So last week， though， when we began to write H TM L and C SS and even a little bit of jascript。

 recall that we served up the web pages that we wrote by using a very simple command in。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_3.png)

Yes code that we preinstalled for you， namely HttP server。

 This was a little program whose purpose in life was just to listen for HtP requests coming from your browser or really any browser and respond to them by sending the contents of files from your code space to the browser。

 typically a do HMl file。 But if you had an image like a ping or a it too could get sent a jascript file。

 a Cs file， really any files stored in your codespace could be servedd up by HttP server static。

 And indeed that's the keyword here is that everything we did last week was within the context of Hml and C static We wrote it we saved it or autosa it。

 and then we loaded it in our browser。 If we wanted to make a change。

 we would go edit the file resa it or let it autoa and we would reload in the browser。

 But only once we got to jascript did we have any kind of dynamism when I demonstrate it。

 for instance， very briefly how we might implement something like autocomple。

 searching for all of the words that start with C A and that big。Dctionary from problem set5。

 but today we're going to focus on things more server side。 In fact。

 even the little bit about javascript that we introduced last week was all client side。

 that jascript code was written once on the server downloaded to the browser and then executed in the browser but as a result that jascript code didn't have access to。

 for instance， any information that might be stored in a database unless somehow we enable it to somehow communicate again and again with that server So really what we're going to do today is dive into the world of web programming where we're actually going to write code in Python using functions and loops and conditionals。

 and unlike last week， we are going to use code to generate our HTML for us so that we can stop doing everything by hand。

 especially for webs that might have dozens， hundreds。

 thousands of web pages there's no human manually generating each of those web pages it's somehow dynamically generated through web programming So let's begin where we began last time focusing on the structure of。

We might request web pages because we're gonna make a little tweak this week in particular last week。

 we looked at a canonical URL like this Htps， which is the protocol or scheme a colonlash www example co and recall that the typically indicated that we wanted the default web page for the website Now that wasn't really gere last week when we were playing with a whole folder of files but if you were to request the default webpage on a website it's typically by convention。

 literally a file called index html， at least on a lot of platforms。

 sometimes it might be called index htm sometimes it might be called default asPx there's different conventions but very often when you just request you're technically referring to a very specific file that has been configured on the server to be the default page that served up but you can of course be specifying specific files or even folder So we looked at URL formats like this if you want file htl you simply append that to the end of the if you want。

The default web page inside of a folder， you might do slash folder slash and the server would serve that file up for you if you wanted to be more explicit。

 you could specify slash folderlashfi html so that you can actually grab a specific file from a specific folder and suffice it to say you can nest these things again and again if you've got multiple folders and subfolds。

 but today and really onward we're gonna start talking about everything after the TLD as really being the path that the browser is requesting Solash path is just meant to generically mean whatever files and or folders are being requested in URLs。

 and we're also going introduce slightly different nomenclature this week too that yes technically that's a path specifying a specific file in a specific folder or set of folders but in the context of web programming。

 what's especially powerful Those files and folders don't actually need to exist using web programming using Python for instance you can specify specific path that don't actually exist in your code space。

But that represent a resource， indeed， uniform resource locator for URL。

 a resource that you want to be able to access via your browser。

 So route generically means what path do you want to select on a web server。

 Now what's this going to mean for us。 Well， once we have configured a route in code。

 we can even specify that that route takes user input and recall that from last time we introduced you to how Google do com works。

 And we didn't implement the backend of Google。 we let Google do that。

 but we did implement our own frontend for Google that allowed you to fill out a very simple form。

 click enter and the web browser would then send automatically a request to Google server that somehow had key equals value。

 particularly queue for query equals for instance， cat and all of that followed a question mark。

 So the same URL format here whereby we have slash route which refers to some path and then question mark key equals value。

 and maybe an ampersand and more key equals values。😡。

Means that today we're gonna have the ability to implement the backend of Google if we so aspire or really the backend of a website and backend just means the part that really the programmer implements and touches frontend generally means the part that the human。

 the user interacts with so with that said let me propose that if we want to be able to read URLs of this format that have some key equals value and maybe some other key equals value。

 we actually do need to introduce a bit of code。 So let's consider now how this request this Http request is getting to the server。

 Well， recall that when you request something like cat via a web page submitting to Google via a form technically inside of that virtual envelope is a message like getlash search question mark Q equals cat。

 then some mention of the version of the protocol being used like version 2 of HttP。

 maybe a reminder of the host of the server that specifically being requested and then a bunch of other stuff that we saw last time as well and ideal。

We want the server to respond to that request。 But here's where things get interesting。

 How in the world do you go about writing code that opens up that virtual envelope。

 reads that getline and the search and the question mark and all of those keys and values Well we could write code very methodically maybe using a for loop and iterating over every character。

 But that sounds like a lot of work And in fact， it's been much better in CSs50 alone that once you understand some concept rather than reinvent that wheel yourself use a framework or rather use a library instead。

 And indeed， that's what we're gonna to focus on today is a very popular micro framework in the world of Python。

 which means a relatively small library that solve some very common problems and saves us the trouble of having to write all of the code that reads the insides of those virtual envelopes and figure out exactly what web pages requested or route and exactly what keys and values were passed in to do so。

 we're going to go ahead ultimately and not use H。TP server anymore。

 that recalls a command that only serves up static content。 starting today。

 we're actually going run a command， namely flask run。

 So not only is flask a library as we'll soon see， which means we have functions and other features of it we can use in our own code。

 it's also once you install it a command that you can run in a terminal window like your own code space。

 And so ultimately instead of running H server today。

 we're going run flask run to still start a web server but a web server that's even smarter than HttP server because it's not just going spit out the raw contents of files to the browser it's actually going execute your and my Python code to generate those web pages dynamically So in order to get to that point。

 we're gonna have to start creating some files of our own and really writing some programs of our own in the convention when using flask this popular micro framework。

 which again is' just a library that standardizes how you and I solve some common problems we're going need typically。

These two files， one by convention called app dot pi and a second one called requirements text or TxT and each of these files in conjunction will be understood by that flask command because flask knows to look for a file like appt pi and knows how to execute it and as we've done so many times in past languages here for instance now in Python while using the flask framework is how we might implement the simplest of web applications So at a glance this is going to look a little strange because there's a lot going on on the screen。

 but clearly that first line indicates that we are importing from a library called flask some kind of feature known as flask capital F So it's a little weird but that's often a convention to import from something lowercase something that's capitalized to make clear that it's really what's called a class in the world of objectoriented programming but more on that down the line and then the second line of code says to flask please turn this file into a web application So this is。

Arcane， but underscore underscore name， underscore。

 underscore is something we saw so briefly a few weeks back in week 6。 when I said at the time。

 you sometimes need to check what the name of this file is and does it equalqu underscore underscore main underscore underscore because that enables you to more correctly implement libraries of your own。

 which we did not do。 but I just mentioned that you might see it in the wild。 Well。

 here it is again in a different form。 underscore underscore name。

 underscore underscore is essentially a special variable that refers to the name of this current file So the second line of code is essentially telling flask please turn this file into a web application and let me refer to it via a variable called quite simply app AP Now after that。

 there's some new weird syntax， but this is technically just Python。

 a feature we haven't yet seen technically you're seeing now the at sign for probably the first time app。

 which is that same variable do route。 and then an argument there too。

 So this is what's an example in Python of what's。lledA decorator and a decorator is a feature of Python。

 whereby you can wrap one function inside of another for our purposes today。

 what this third line of code essentially means is hey flask。

 please turn the following function into a route that can be served up by the server to a browser。

 What is that function。 Well， the function that I want to associate with that route is literally a function called index。

 but I could call it anything I want。 I could call it fo bar ba or anything。

 but index makes sense if this is meant to be the index of my website。

 and the only thing that function does for now is literally return a string or stir in Python speak。

 namely quote unquote hello world。 So that is it。 And the fact that the argument to the app route function。

 whereby route is a function or method inside of that app variable or object the quote unquote just tells flashask whenever the user visits like example co please call this function and send to the browser。

Whatever this function returns Now， long story short。

 this is not the only way to implement a web application， but this is the way to do it using flask。

 this very popular micro framework。 If you were to use something else like in Python。

 there's a framework called django and there's many others in many other languages as well。

 This just standardizes for us。 what are the conventions when I want to create a route And I want to return some Hml because you can solve that problem any number of ways。

 but what's important today is really the application of last week's ideas even though we're using a very framework。

 and this is not meant to say that you're learning flask and C50 per se。

 but you're learning a web framework that's gonna be representative of many others out there as well。

 but we chose one that's both and relatively simple。 So with that said。

 I think let's go ahead and implement the very first of our web applications here namely by switching over to Vs code here。

 And within my Vs code environment。 I've sort hidden somes。

 I've already closed my activity bar and I've closed the file Expr so that as always。

 we have room for some。Ts and we have my terminal at the bottom。 but like last week。

 I also have an additional tab inside of my terminal area here for not only the terminal window itself。

 but also these here ports。 recall that last time we talked about TCP ports in particular unique integers that identify certain services like 80 for web servers or 4。

43 for the secure version Htps thereof here again， we see port 1337。

 which is meant to connote L because this is a CSs50 specific use of this TCP port but soon we'll see another port just like we did last week when I launched HttP server So let's go ahead first and create a file for instance called app dot pi and just to keep things simple。

 I'm going to isolate all of these files to a specific folder。

 So I'm going create a new folder with makeD and I'm going call it hello for my first application called hellello I'm going Cd into hello and indeed now I'm in there and now I'm going run code of appt pi to begin writing the content of this here web application。

😊，And for this， I'm pretty much just going to use the contents of the sample program we saw a moment ago by doing the following。

 I'm going to say from flask import flask， lowercase F and uppercase F respectively。

 Then I'm going to say app equals capital flask， underscore underscore name， underscore underscore。

 which is the line of code that says， hey flask turn this file into a web application and give me a variable called app via which to reference it。

 and then down here I'm going to do at app do route and then in parentheses pass in a single argument slash。

 I could use single quotes， I could use double quotes for consistency with C as we did in week 6。

 I'm going to keep using double quotes most of the time。

 Now I'm going to go ahead and define a function in Python called index。

 but I could call it anything I want this particular function is not going to take any argument。

 So all it's going to do is return a string or stir of text。 hellello comma world。 and that's it。

 Now just to be consistent with style 50。 I've actually deliberately left a couple of lines blank。😊。

Between my function and everything above it。 And that's just a stylistic convention in Python。

 But otherwise， this is just some relatively little Python code。

 albeit using a couple of new features， a new library and using a new piece of syntax。

 the at sign for that so-cal decorator。 And again to be clear。

 all a decorator does in Python or in this particular case is it says hey。

 Python turn the following function into one that should be called automatically whenever the user requests the forward route。

 All right， I need to do one more thing at least on some systems。

 let me go ahead and run code of requirements Txt。 And in this file。

 I'm going simply specify what are all of the libraries that I want this web application to use。

 And I'm quite simply going to say flashask capital F here。

 But strictly speaking it's not necessary because in Cs50 because we've pre-installed flashask for you。

 but in general， and certainly in the real world。 what I'm doing now is associating with this application0 or more list of。

😊，Tendencies， librariesbraries that I want someone to install in order to ensure that this thing here works。

 That's all I need to put in this file。 But even though it's already been installed。

 what I can do is this， let me go ahead and maximize my terminal window here。

 and let me run that command。 we ran briefly back in week 6 when we wanted to install libraries。

 I'm gonna do Pip install And instead of installing cowi or something silly like that again。

 I'm gonna to do Pip installs R requirements text。 And what this command would do for me if flask is not already install is it would install it for me on this here system。

 So I'm not gonna bother executing that because I already did it earlier for everyone's code space。

 but that's indeed how we could use that requirements file to automatically install things。

 but I have to manually typing that and other things out。😡，All right。

 well let's go ahead now and do something incorrectly。 suppose I'm in the habit of forgetting things。

 and I run HttP dash server in my terminal window。 I can certainly run it。

 and it's certainly going to work， especially if I override this helpful reminder we put in place to discourage you from doing this。

 but I'm gonna say nope， I want to go ahead and run it。

 I'm gonna see the same kind of output as I saw last week。

 I'm going to be prompted to open in a browser that particular web application。

 but that particular web application is not really my own per se it's just the contents of this folder。

 So if I go ahead and zoom in on the directory index of that there folder。

 We see my two files app pi and requirements text。 if I click on app pi。

 I'm not going to get a hello world。 In fact， it was a little subtle。

 but what my Mac just did was it downloaded app pi which is not the goal I want and in fact you've just let the world access your source code if there's anything sensitive in that there program because the browser doesn't know what to do with an app pi file inside。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_5.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_6.png)

Of my browser。 So that was incorrect。 So I'm gonna go ahead and go back here。

 but just to make clear that we do indeed have a second port running now just like last week because Htp server can't use port 80 or 44。

3 because code spaces that is C50 dev is already using that for you it did choose the default port of 8080。

 which is commonly used for development purposes and that's why we see not only 1337。

 but 8080 now as well。 So let me go ahead and back to my terminal window。

 hit control C to interrupt Htp server， and let me now do things the right way by running flask run enter And what we'll see now is that my application is running not on 8080 but on 5000。

 which happens to be flasks default choice of ports。

 but you can override this if you so choose but I'm gonna stick with that one And now even though it's a little underwhelm。

 I'll zoom in now I see hello comma world And in fact， if I right click or control click on。



![](img/c0e4be0df203b599d64dc2c7b3218c55_8.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_9.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_10.png)

Chrome here or your browser more generally。 And for instance， view page source。

 you will see that there's really no even Hml here just text because what I've essentially sent to the browser is just literally hello comma world。

 but already we have a building block here。  clearly。

 I can write Python code that generates output that is sent to the browser。

 So really there's nothing stopping me from now sending not just raw text。

 but actual HTMLml to the browser。 Let's do this sort of poorly at first。

 let me go ahead and hide my terminal window just so we can focus on code now for a moment。

 even with flask actually running。 and this is gonna look deliberately ugly for the moment。

 but let me go ahead and do this。 if I want to send the browser a proper web page Heck。

 I remember some Hl from last week。 So open bracket exclamation point doc type Hml close bracket and then open bracket Hml then laying equals quote unquote for English。

 then I'm going to go ahead and do head for the head of the page and then title for the title therein。



![](img/c0e4be0df203b599d64dc2c7b3218c55_12.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_13.png)

I'm just gonna say something like hello comma title like I did last time。

 let me close that title tag， let me close that head tag。

 let me open now my body tag inside the body I'll say hello comma body I'll close the body tag I'll close the HTML tag and I'll close my quotes but I'm going to be careful here notice that I used an attribute value in here with double quotes that's probably going to confuse Python because I have these outermost double quotes so I can fix this in a couple of ways。

 I'm going to go ahead and use there for single quotes on the outside of this Python string which unlike C is fine for strings not just chas as and see and I think that will at least assure that the quote marks don't get confused。

😡，Alright， this is probably not gonna be the best design。

 And hopefully this is not how we generate web pages。

 but let me go ahead back to my other browser tab， which previously said hello world。

 let me reload now。 and I seem to have changed not only the output of of this web program。

 but really the contents underneath the hood as well。

 Let me right click or control click on the white portion of my screen here。

 and there is some proper Hml。 It's not particularly pretty printed， there's no new lines。

 there's no indentation。 but if I scroll from left to right in my browser here。

 there is a wellform web page， as I intended。 So again， not particularly fun。

 not particularly pretty， but we seem now to have the capability of writing code that generates not only text。

 but Hml as well。 So how can we go about improving this program further。 Well， let me do this。

 This is not really the nicest design。 So let me go ahead and highlight all of this H。 I just wrote。

 and let me go ahead and。😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_15.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_16.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_17.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_18.png)

Cut it to my clipboard。 and let's come back to that code file in a moment。

 Let me go ahead and reopen my terminal。 I don't want to kill flask run just because it's convenient to keep it running。

 So I'm gonna to create a second terminal window by clicking plus and I can toggle between them right here。

 So one is still running flask。 The other is now a blinking prompt。

 I'm in the wrong directory by default。 So I do need to go back into my hello folder with Cd hello。

 but in here， what I'm gonna do now is this I'm going go ahead and create another folder inside of this that by convention is called templates。

 And when I hit enter here， I'm gonna then do Cd templates to go inside of it。

 and now I'm going create an actual fullfledged Hml file index do hml by convention enter and inside of this file。

 I'm going go ahead and paste that long string of HTMLl。

 and I'm gonna go ahead and clean it up to look a little bit more like it looked last week and I'm going even stylize it further here。

 So everything's very pretty printed and human readable and I'm going put the head up there。

 I'm going put the。Down here and below low that。 I will close my Html tag。

 So no different in terms of the content。 But now I have all my Hml in an actual file。 Allright。

 what do I now do with this， Well， wouldn't it be nice if I could go back into app and say。

 don't return just hello world， don't return this long， messy string of Hml。

 but return the content of a file called index do Hl。 Well， to do that。

 I can import not just flask capital F from the flask library。

 I can also import a function called render template。 This is a function specific to flask。

 but it does exactly that， it will render a template for you in the sense of it will go open an Hl file for you。

 it will then send it from server to browser。 And as we'll soon see it will can even do some fancier stuff than that。

 But now instead of returning quote unquote hello world or quote unquote， a big long string of Hml。

 What I'm actually gonna do is something like this。 I'm gonna say like。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_20.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_21.png)

TL equals render template。 And what template do I want to render index dot Hml。

 And I'm going store that template， so to speak in an Hml variable。

 and then I'm going to return that variable。 Of course。

 as we've seen in seeing in Python and even jascript， we don't really need variables per se。

 if we're just defining them and using them once， So I can actually tighten this up a bit。

 let me go ahead and highlight the actual function call， get rid of the variable。

 and let me just immediately return the return value of render template passing in index do Hl。

 Now notice a subtlety。 if I go back to my terminal window， recall that。

 I created index do Html inside of my templates folder， which is inside of my hello folder。

 But render template is smart by as its name implies。

 its purpose in life is to render a socalled template more on what we really mean on that in a moment。

 But by default flask knows that if you're trying to render a template。 Oh， sure。

 it must be in your templates。😊，Folder， it's got to be all lowercase templates。

 Your file has to be exactly named as I'm specifying here。

 But this is now how a web server can associate a route like slash with a specific file on the actual server。

 No matter what folder it might be in。 So let me go and go back to my other tab。

 let me go ahead and cross my fingers as always and click reload。 And so far so good。 And in fact。

 just to prove to you that this is the new version of my Hl that was pretty printed。

 let me go to view page source。 And there indeed， it is printed in the browser's memory just as I wrote it on the server。



![](img/c0e4be0df203b599d64dc2c7b3218c55_23.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_24.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_25.png)

Alright， so now let's take a look at the code as we left it。 whereby for the slash route。

 we are returning the return value of the render template function once passed an argument of index do Htl。

 And let's see if we can't make a web application truly more dynamic so that it's not just saying hello title hello body all of the time。

 but ideally saying hello to a particular person。 Now。

 how can I possibly pass user input to a web application。

 because my users on the Internet certainly don't have access to my keyboard。

 let alone my terminal window， they only have access to my website via a browser。 But of course。

 as we saw on the Google example， if you were to pass in somehow at the end of the URL。

 not just a route， but also a question mark and key equals value。

 maybe an ampersand key equals value， maybe another ampersand key equals value。

 we can somehow send from the browser to the server user input， Of course。

 that user input ideally does not come from the human typing it in manually to the URL。

 but filling out a form hitting enter and letting。

![](img/c0e4be0df203b599d64dc2c7b3218c55_27.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_28.png)

Browser convert that form to the appropriate get request in the URL。

 But let's start to simulate this for now。 Let me go back to this URL here。

 put my cursor at the end of it and say question mark name equals， for instance， David。

 the intent being that I want this site to say hello David instead of hello title and hello body enter。

 Unfortunately， when I hit enter nothing changes。 and I can confirm as much by viewing source。

 and indeed nothing about the page has changed because we haven't done anything dynamic in code。

 but I do think we can fix this。 Let me go back over to vs code here。

 and let me propose that we go into the template first。

 which currently only says hello title hello body， let's go ahead and simplify the title for now and focus on just dynamically changing the body and let me propose that what I really want this thing to say is hello and then a placeholder。

 So I don't want to literally say placeholder where placeholder is just something into which we plug in a value because now I'm gonna see a website that says hello comma placeholder。

 So the syntax you're about to see as a。

![](img/c0e4be0df203b599d64dc2c7b3218c55_30.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_31.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_32.png)

A bit different， but it's going to be a technique via which I can tell Python specifically flask to substitute a value for this here placeholder。

 And the syntax for that when using flask is to do two curly braces on the left。

 and two curly braces on the right。 It's a little different from our F strings or format strings in Python alone。

 but in the context of an H template， the way you specify， hey。

 flask substitute a value here is indeed with two curly braces on the left and the right。 Now。

 of course， nothing's going to happen yet until I go back to app I and actually tell the template somehow to plug in a value therein。

 Now， how can I go about doing this。 Well， the simplest way which is says follows In addition to importing flask and render template。

 I'm also going to import another variable that comes with the flask framework called request。

 And this is a special object that's going to give me access to all of the H T。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_34.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_35.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_36.png)

Pameterters， the user input in the HttP request that's causing this code to be executed。

 So how do I use that。 Well， let me go down here and let me create a variable called anything。

 but I'll call it name。 and I'm going go ahead and set that equal to something like request orgs Open bracket quote unquote name close Now what in the world is going on here。

 Well， it turns out what we've introduced here now is a special variable request orgs that somehow magically automatically stores all of those key value pairs。

 And here again is why we're using a framework like flask because it's not going be particularly fun code to have to write code that opens that virtual envelope reads the HtP message inside of it parses or that is analyzes and figures out what is each key。

 what is each value， what route is requested like every website on the Internet practically is probably doing the exactly that nowadays。

 we might as well not reinvent that wheel ourselveslf So in request orgs we have。



![](img/c0e4be0df203b599d64dc2c7b3218c55_38.png)

This special variable that comes with flask that just gives us a Python dictionary that contains all of those key value pairs。

 And in fact， think back to week 5， when I propose that dictionaries or in Python are so very useful because they allow you to associate keys with values。

 Keys with values， that's what flask is doing here。 So if I go back to my code。

 what we really see is that I'm creating a variable called name。

 and I'm setting it equal to the value of the name key inside of this dictionary。

 That is request ors is a Python dictionary at this point。

 How now do I pass in the value of that variable to my template so that we actually see hello comma David or hello comma someone else。

 Well， in app pi， I have to pass now a second argument to render template。

 and the convention for that is placeholder equals name。😊，In other words。

 I can use Python's feature for named parameters， which we've seen before。

 like the print function in Python has that end parameter that we can use to override the line ending。

 which is by default slash n here I'm passing in a positional parameter in Python。

 which just means the first one first position but then I'm passing in a second parameter that has an explicit name and the name I'm giving it is literally placeholder y because I want flask to replace placeholder in this template with the actual value of the name variable So if I go back to my second tab here。

 which previously said hello title hello body but notice a moment ago。

 we passed in question mark name equals David， which was previously ignored now if I reload this page having changed my python code in apptop pi there is my hello David and my tab is more simply now just hello unfortunately this is not the best solution why because suppose。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_40.png)

A user doesn't visit this URL and certainly doesn't have the wherewithal to type in manually。

 Quetion mark name equals David。 Let me go ahead and delete that HttP parameter， the key value pair。

 Let me go ahead and reload this page now And now I got a bad request a 400 error。

 which means I did not request this website correctly。

 Now that's just kind of bad design because surely the user should be able to visit a URL without having to manually type in parameters So how do we fix this。

 let me go back to my other tab for VS code， let me go ahead and open up app pi and it seems to be the case that I'm just blindly assuming on lines 8 and9 at the moment that there will be a key called name inside of this dictionary and clearly that's not the case if the user has not visited URL that has question mark name equals something。

 So I think we just want to use some week1 style logic using Python syntax specifically to say something like this。

 Let me go ahead and change line8 to ask a question first。😡。



![](img/c0e4be0df203b599d64dc2c7b3218c55_42.png)

If there is a name key inside of request do orgs， then and only then go ahead and create a variable called name whose value is request do orgs quote unquote name else。

 if there is no name key in that dictionary， we've got to handle that situation。

 which I wasn't a moment ago。 All right， fine， let's create a name variable and set it equal to some default value like world。

 And now line 12 can remain unchanged because no matter what。

 I'm passing in a legitimate value for name， that's either whatever the human typed in in the URL bar。

 for instance， or it is by default world。 So if I go back now to my other tab。

 and without changing the URL， I just click reload now we're back to something correct。

 if underwhelming that says hello comma world。 Of course。

 this is a little maybe suboptily designed in that， well， I've used my placeholder already。

 what if I want to say two placeholders or three placeholders or more。

 I probably shouldn't be in the habit of literally。



![](img/c0e4be0df203b599d64dc2c7b3218c55_44.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_45.png)

Using the word placeholder in my template， even though that's what it is。

 let me go ahead and be a little more descriptive， just like with our variable names in general。

 and let me go ahead and say what I really want here is hello comma name where I want the value of name to be interpolated just like in an f string inside of these double curly braces。

 but I now need to change my code because I've now changed my placeholder to literally be name this is going to look a little weird but the convention in using this library is quite often to say now name equals name。

 why because the name of the parameter I'm passing in to the left of the equal sign must match the name of the parameter that I'm using in my template。

😡，Though the value that I want to pass in for that placeholder can be anything I want。

 it can literally be quote unquote， David， But if the value is in a variable。

 then what I want to do is pass in the name of that variable。

 So this looks a little stupid admittedly。 But this is the convention for better for worse。

 name equals name means plug in the value of the name on the right for the template placeholder called name on the left。

 That's all。 But this is indeed a common convention。 Now， is there a better way to do this。 Well。

 this feels a little bulky to have four lines of code if this elses that just to check if an HtP parameter was passed in。

 And in fact， there is the convention in flash would actually be to not bother with this explicit if else。

 but instead to do something like this name equals request dot orgs and then specifically call method or a function called get。

 whose purpose in life is to get the value of a key。 What key， Well。

 the name key and what the get function also does for us is if it can't find a value there。😡。

You can specify a default value。 So if you want the default value to be world。

 you pass that in as a second argument。 So the behavior now is gonna be no different。

 But if I go back to my other tab and click reload， nothing changes， but it's still working。

 It's not showing some error。 However， if I go into my URL bar at top and add question mark name equals David zoom out and hit enter。

 it's still working in that case as well。 but I've distilled those four lines of logic now into something a little simpler by actually having now a use of the get method which is doing more of that logic for me。

 Allright， so suffice it to say this too is not the best design because you certainly don't want to make a web application where your users to provide user input have to manually edit the URL that would be like searching for Google by only being able to edit the URL by adding search question mark Q equals cats anytime you want to search for cats。

 let alone some other value。 and certainly if you want to type in your email address or a credit card number or anything that we're in the habit of typing。



![](img/c0e4be0df203b599d64dc2c7b3218c55_47.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_48.png)

Into forms on the web， you don't want to have to manually do that instead in the URL。

 which is to say， how can we make this now a more typical web application that still takes user input。

 but takes it via a proper web form。 We saw how to make forms last week。 For instance。

 we made a frontend for Google。 Let's now implement the backend thereof。

 So let me go back over to VS code here now。 And let me propose that we will create a actual form and index html。

 So index htmls purpose in life is no longer to be a template that says hello comma so and so。

 all it's going to display is a template。 So let me go ahead and delete this line here。

 And let me delete this use of a placeholder。 And let me go into index html and remove the body here that we had for that placeholder。

 And let's actually now in this here body create a web form。 So I'm going do form。

And then inside of the form tag， I'm gonna create an input and the name of that input is going to be name because I want the humans name and the type of that text the type of that input is going to be text。

 even though that's the implied default。 But recall from last time there's some nice features I can enable anytime I make a form。

 I can turn off autocomplete。 So it doesn't remember the previous person's name I can autofo that input so that the cursor is blinking and ready to go。

 and so that the human knows what to do with it， I can say placeholder equals quote unquote name so that there's little gray text that's explanatory text。

 Now notice there's some potential confusion here。 my use of name here is to define the name of the H parameter that I do want to end up in the URL。

 the name here is the name of the H attribute that it comes with the input tag if you want to use it。

 placeholder here is another attribute that can be used with the input element。

 So even though we're seeing lots of names and lots of placeholders They're the same。😡，Idea。

 but they mean different things in different context。 Now， we're looking at H Tm L alone。 All right。

 besides that input field， let me go ahead and create a button。

 The type of this button is going to be submit so it knows to submit this form。

 And I'm gonna have that button， say greet。 So it's obvious that I click on this button to greet that person's name。



![](img/c0e4be0df203b599d64dc2c7b3218c55_50.png)

All right， what more do I need in here。 Well， this is just a form， which is fine visually。

 But I haven't told the browser where to submit it just yet。 And if I don't specify that。

 it's actually going submit back to the same URL， for instance。

 slash if that's what's serving this up。 So if I actually want to change the action that the browser should really take there turns out there is indeed an action attribute。

 which allows me to specify where I'm submitting this。

 I'm not going submit it to Google for instance this week。

 I'm instead going submit it to my very own route， which doesn't yet exist， but it will in a moment。

lash greet。 and the method I want to use， is going be specifically get。

 where if I in contrast with post， because I do want to use get so that the parameter is very visibly appear in the URL。

 if only so that I can show you what's happening。 if I were to use post instead recall that sort of hides the input。

 It's still in the envelope， but sort more deeply inside of it。 So it's not exposed in the URL。

 which is appropriate for anything personal， maybe an email address， maybe a credit card number。

 a password or the like but this is just a person's name。 So I'm okay。😡。

For now with revealing it in the URL。 Allright， let's now go back to my other tab。

 If I delete the URL parameters there and hit enter and go back to my default template。

 I see indeed a form asking for a name and a button to greet someone So I'm gonna type in my name David and I'm gonna click greet and notice what happens to the URL at top it does automatically bring me to slash greet question mark name equals David So I the human did not need to type all of that in as I have been the browser knows when submitting a form via get do that Unfortunately I get a 404 not found why because my app dot pi file only has one route for s there is no route yet for slash greet So I think we can fix that to by just practicing what I've been preaching here as follows let's go into app pi and say app dot route quote unquote slash greet and here too I can call it anything I want。

 but I want I want parity with what I just put in my form and inside of this。



![](img/c0e4be0df203b599d64dc2c7b3218c55_52.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_53.png)

Under this decorator， so to speak， I now need to specify exactly what function I want to be called when this route is visited。

 I can call this function anything I want， but to keep myself sane。

 I'm going to use a name for the function that kind of matches the route itself。

 So I'm going to call this function greet， even though it can be anything I want。

 And then after this function which is not going to take any arguments。😡。

I'm going to go ahead and do this。 I'm gonna say in here name equals request dot orgs do get quote unquote name to get the value of the name parameter from the get string but if there's no such value there。

 let's grab a default value of world。 And then as before。

 I'm going to return the return value of render template。

 but this time I'm going to render a different template that to be fair does not yet exist。

 but I can solve that problem too， greet dot Hml， and I'm gonna pass into that template once it exist。

 the value of name equaling the value of that variable。 So same ideas as before。

 but I've now moved a lot of my logic into a brand new function and route called greet。 Allright。

 so what's now going to happen here。 Well let me go back to my browser。

 which previously was 404 and not found because the route didn't even exist。

 I'm gonna to click reload and I'm gonna see a new problem， I think because the route exists。

 but I don't think that template exists。 greet do Hml yet。 So let me hit enter。😡。



![](img/c0e4be0df203b599d64dc2c7b3218c55_55.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_56.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_57.png)

Reload and now I've got an internal server error， which welcome to web programming。

 This is gonna be the new segmentation fault of C。 but in the context of web programming。

 When you see 500 internal server error。 as much as you might like to hope otherwise it is your fault。

 You have made a mistake somewhere as I just did。 So let's see how to diagnose this。

 let me go back to my other tab， let me reopen my terminal window。 And thankfully。

 within my terminal window， I should see among any number of other errors。

 some hint as to what went wrong。 So to be clear， when you see a 500 error in your browser。

 internal server error。 one， it's your fault。 But two。

 there's probably diagnostically useful hints in your terminal window。

 if you've created two terminal window。 that's fine。

 you have to realize that your commands are gonna be left alone。

 You have to go back to your other terminal window where flask run is still running and you might want to scroll up and down。

 look at the most recent error in there and。

![](img/c0e4be0df203b599d64dc2c7b3218c55_59.png)

You'll see something useful。 And indeed， I do think I do template not found greet do H。

 And that's pretty much hitting the nail on the head and telling me exactly what there is wrong。

 but interestingly， we haven't seen this word yet， Ginja exceptions exceptions we've seen before and you might recall that we can try to do something but if an error happens in exception might indeed be raised Ginja though is a new term。

 and this is just referring to another library that anyone on the Internet can use。

 but the folks who invented flask decided to adopt this other library themselves called Ginja and what Ginja is is essentially a templating library。

 It purpose in life is just to handle everything inside of that template's directory。

 So if I go back to my own index do Hm It is technically a library called Ginja that is reading that template top to bottom left to right looking for among other things pairs of curly braces so that Ginja can do the substitution for you now。

flask using ginja。 Well， flask realized the folks who invented it。

 we don't have to reinvent the wheel of templating because some other people on the Internet already created a templating library called Ginja。

 So we might as well use those in conjunction。 And this is gonna be more and more common。

 Even though when we started using libraries and see they were very small and welldefin and only did one thing once you get to web programming and really software engineering in the real world。

 You're gonna be using multiple libraries often in conjunction with each other。

 some of which our dependencies for other libraries。 So we're just seeing an example of that。

 So this is to say ultimately， this problem is still mine internal server error means I messed up。

 we know now from my terminal window that the template is not found。 So what's the solution。 Well。

 let's go ahead and create that template。 Well， let me go back into my terminal window。

 but not the one with the error， but my other terminal window that gives me access to a working command prompt。

 Let me go ahead and type code greet Hml and hit enter。 And just to make the point。

 let me kind pedantically type。This whole file again。

 So open bracket exclamation point doc type HTML， then below that HTML Lng equals E。 Then below that。

 let's put the head of this page。😡，Inside of that， let's put the title of this page。

 We'll call it greet。 just so I know which template is which。

 Then let's put the body of the page here。 And then let's go ahead and do hello comma name using the same placeholder as before。

 So in essence， my greet do Htl template is now what my index do Htl template used to be before I deleted the ladder and replace it with that interactive web form。

 But now， if I go back to app do pi， will'll see that greet dot Html， which is to be rendered。

 should now work as intended。 And I'm passing in name equals name so that I can have that template。😡。



![](img/c0e4be0df203b599d64dc2c7b3218c55_61.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_62.png)

Use of this placeholder substituted with the actual person's name。 Allright， let's cross our fingers。

 Go back to my other tab and reload this page。 And there we have it。 Ho comma David。

 Let's now go back to the code via which this current application is implemented and consider what could be done better。

 In fact， let me reopen my terminal window and clear it temporarily and type in Ls in my templates folder。

 just to confirm that I do indeed have two files。 Let me do C dot dot Ls in my hello folder。

 just so that you can see what files are therein。 And in fact。

 what you see here now is a pretty representative structure for a web application implemented in Python using the flask framework Before long。

 we'll see one more folder in here， not just templates。

 but something called static because up until now， we haven't served off any images。

 any javascript files， any Cs files， we can And by convention。

 those such files will be stored in another folder called static。 So indeed。

 what you're seeing here is the representative list of files and or folders。



![](img/c0e4be0df203b599d64dc2c7b3218c55_64.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_65.png)

That you typically need to create at some point when building a flask application。

 But I dare say even though we're following these conventions。

 we haven't necessarily done things the best way。 Why well case in point。

 let me hide my terminal window and open up again index hml。

 let me go ahead and open up greet do hl and if I go back and forth between these。

 you can clearly see that they're not changing all of that much。 there's a lot of commonality。

 the doc type at the top， the Hml tag， the head tag， the title tag， the body tag。

 it's really only the contents inside of the ladder head title and body that are actually changing。

 Moreover， let me point this out。 let me go back to my user interface here。

 let me go back to my web form here and you'll see that I've zoomed in a few times。

 So everything is very visible but let me go ahead and open up this feature。

 Let me go to right click or control click on my viewport。

 let me click inspect to open the developer tools that we talked about last time and notice that I can。



![](img/c0e4be0df203b599d64dc2c7b3218c55_67.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_68.png)

Click this button here at top left， which is a useful toggle for changing the type of device you're visiting a website on。

 So for instance， if I type this now， what you'll see if I shrink my developer tools。

 you'll see a mobile version of this web page So what that button does in Chrome at least and other browsers have similar features you see what this web page would look like on a mobile device and suffice it to say like I can barely tell what's on the page like the default font is clearly way too small and at least on my phone。

 there really is no easy way to like zoom zoom zoom you can tinker with the settings。

 but you don't want your users having to zoom in just to use your website which is to say that my website as implemented now is not responsive to the type of device that's visiting it。

 It is not mobile friendly Now there's many different ways to address this including using libraries but minimally a solution to this problem typically is to go in and add an additional tag to the head of your web pages So let me go back。



![](img/c0e4be0df203b599d64dc2c7b3218c55_70.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_71.png)

Indexed Hl。 Let me go into the head here。 And this is a bit of a mouthful。

 but I'm gonna to use a tag called meta， which refers to metadata。

 I'm going give it an attribute called name and set that equal to viewport。

 Why I'm just following the documentation。 Then I'm going specify that the content of this meta of the content for this meta tag is going to be cryptically initial dash scale equals one comma with equals device with this is a mouthful。

 and technically I'm reading it off of a sheet of paper because I can never remember exactly what to type here。

 but this tag alone will make my application and my website more generally more mobile friendly。

 It's not going to fix all of my potential problems。

 but it is going to tell the browser in particular that it should size things to the specific device with be it an iPhone and Android device and iPad。

 a tablet of some sort or the like。 And case in point， if I now go back to my other tag。

 which is still in my mobile view mode， let me。Like reload now and notice。

 even though there's the tiniest of forms up there in the top corner when I reload now。

 now it's at least more usable。 still relatively small， but it's at least readable at this point。

 So that one meta tagag alone goes a long way to making your website responsive in the sense that things are gonna be resized automatically by the browser based on the device type。

 I mentioned that only because it's gonna lead to another design opportunity。

 let me close my developer tools， let me go back to V S code here。 and you know what。

 my template still doesn't have that mobile friendly tag。 So all right， fine。

 let me just save myself some keystrokes。 let me highlight this whole line 6。

 let me go into into its head paste that there。 And okay now I had argue that I've solved this problem on this page2。

 But where are we going with this。 Well， almost any time in C 50。

 when I've copied and pasted something， it's almost always been the wrong solution to a problem。

 It's suggest say poor design because why copy paste if I can somehow factor。



![](img/c0e4be0df203b599d64dc2c7b3218c55_73.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_74.png)

Out commonalities。 And indeed， this is the point now to be made。

 if we toggle back and forth between these two files， index dot Html and greet do Html。

 there is so much commonality。 I dare say now all of this is common from line 1 through part of line 7。

 All of this is common from line 15 down through line 17， wouldn't it be nice if in Hl。

 we can somehow factor out that code to。 And here is where templates start to get very powerful because the answer is indeed yes。

 we can actually factor out all of those common lines of H Tml in such a way that we don't need to type them again and again。

 So now let me propose that we'll create one more file。

 even though this will allow us to make these two files simpler as follows。

 I'm going go into my terminal window where I have a command prompt。

 I'm gonna see back into my templates folder And I'm gonna create a new file called layout do H Tl。😊。

Wwhich is a file name you need to adhere to when using flask because that's the default name。

 all lowercase one word layout do Hml enter。 I've now got a new tab。 I'll close my terminal window。

 and for the last time， hopefully I'm gonna type out doc type hml then I'm going to do HTMLl lang equals quote unquote then inside of that I'm going have the head of my page inside of which I'm gonna have the title of my page and because this application doesn't really need to change that much。

 I'm just gonna say the title for every page in this application is hello。

 but we could parameterize that if I wanted I'm also though going add that meta tag So meta name equals quote unquote viewport content equals quotequote initial scale equals one comma with equals device with close close bracket。

 and then I'm gonna have the body of my page but here is where the website really varied by template in index that HTMLl was a form。

 but in Greek do hl it was hello so and so。 So what I really want is a whole block of content potentially to go in here。

So in fact， what I'm going to do inside of the body is use some weird looking syntax。

 This is more gingja syntax。 and I'm going to say this open curly brace percent sign， block body。

 close percent close curly brace。 And then with nothing in between there。

 I'm again going go open curly brace percent sign。 And this time I'm going to say end block one word no space percent sign close curly brace。

 So this is weird syntax。 you'll have to look it up to remember it over time。

 but this is the way to specify to flask， plug in the content of another template here。

 not just a variables value， but another file should go here。 you can call this anything you want。

 I could call this fo or bar or ba， which are the go to terms in computer science。

 but I'm going to call it body only because one I only have one such placeholder for now。

 and it's in my body。 So let's just say this is the placeholder for the body of this web page。

 Keep it simple。 So now what can I do in my other files。 now。😡。



![](img/c0e4be0df203b599d64dc2c7b3218c55_76.png)

That I have that template here。 I can go back to， for instance。My index dot H Tml。

 and I can delete all of this， and I can delete all of this。

 So now an index do Html is literally only the form that is going to vary for this particular page。

 though， I now need to tell flask， how to embed this snippet into my full layout。

 And the way to do that is as follows。 at the top of mirror template opencurly brace percent sign extends as a verb quote unquote。

 layout dot Hml。 And this is a line of saying is is the way of saying in flask。

 Please extend layout dot Html with the contents of this file。 I do need to do one more thing。

 I need to define the block of code that I want flask to substitute for me。 And so here， too。

 I'm going say block body just like I did a moment ago。 And then in here。😊，I'm below this。

 I'm gonna to say end block。 and it's weird。 This is a ginja thing。 It's block space body up here。

 but it's just end block down here。 The word E D is is prepened to the name of this ginja tag。

 just to be a little nitpicicky。 I'm going to go ahead and indent this properly。

 So it's only indented once there。 and that's it。 And admittedly， this looks a little weird。

 But what's important is that now I've only implemented in this file。

 The minimum amount of HTMLml that differs for this particular route。

 What am I going to do in greet dot Hml。 Well， I'm going to delete all of this up here。

 and I'm going to delete all of this down here at the top of this file。

 I'm again going to say extends quote unquote layout dot Hml close quote and then another percent sign and close curly brace below that I'm going to say block body percent sign close curly。

 And then down here， I'm going say as before end block and close that tag。 I'm gonna fix the。

ation here， just to be consistent。And now I have a second。

Block that will be plugged in when greet do Html is used。 So again。

 these files now differ only in terms of the contents of that block。

 So if I toggle back and forth here， you'll see that let me add spacing just for consistency here。

 indexex do Htl has the form。 G do Htl has the hello and the placeholder for name。 All right。

 after all of that work。 let me go back to app pi and surprise， don't need to change anything。

 because I'm using the render template function， it knows not only how to handle those curly braces with variables as placeholders。

 it also understands curly brace percent signs， percent signs。

 curly brace as per the documentation for Ginja itself。 So in fact。

 what I'm gonna go ahead and do now is go back to my web page without changing anything in app pi just for good measure。

 I'll reload this page here。 wasn't expecting this to happen。 but I've clearly induced a problem。

 I'm now getting one of these 500 internal server errors。 So how do I diagnose this。



![](img/c0e4be0df203b599d64dc2c7b3218c55_78.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_79.png)

Well， a good programmer would know to go back to their terminal window。

 go specifically to the one that's running flask。 And here we have another gingeringja exception template syntax error。

 expected token end of statement block Go string。 Now， where is that。

 Let's go back into my layout Hml。😊，And this looks correct。 Let me go back into index。 HTMLt。

 super subtle。 I did something dumb。

![](img/c0e4be0df203b599d64dc2c7b3218c55_81.png)

Can anyone spot the mistake before I reveal。Anyone see it。 Very subtle。And I think， yes。

 we have someone pointing it out。 I stupidly forgot my double quote。 So that's all。

 And that's why it was seeing a string or a stir instead of the tags as it expected。 So subtle。

 and I was holding my breath that I was actually gonna be able to solve that in front of everyone。

 But the solution was clearly or the hints of the solution was clearly in my terminal window。

 So now' tied my terminal window， go back to my other tab， cross my fingers。

 which maybe I forgot to do before， which is the problem， reload there we go， index Hml is working。

 And if I type in my name and hit enter or click read now the whole thing is working again。

 But more importantly， if I view page source， notice that I indeed see that the same template has been used。

 the same blueprint， if you will， for this page as well as if we go look at the other。

 all of this stuff is common to these files。 Now as an aside。

 once you're in the browser viewing the output from the server， it's okay。

 if not everything is pretty printed perfectly， what matters when it comes to style with web programming as with programming in general is what you and。

😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_83.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_84.png)

Developer see on the server， the browser is perfectly okay with there're being less or more white space just because it was all dynamically generated。

 but indeed if I go back now， not just to hello not just to my greet route。

 but this one and view page source you'll see that's what's been generated by the server is indeed almost the same up until a point All right so up until now we've only been using HttP get requests whereby any user input whether it's from the form or manually typed in is indeed being sent from browser to server via the URL itself。

 but it turns out there are methods that we can use besides get recall that there's also post and post treats your data a little more privately in the sense that it still kind of puts it into that virtual envelope。

 but it shos it down deeper such that it doesn't appear in the user' URL bar this of course is compelling if it's a password credit card or anything personal or private So how can we switch our own application for instance from using get to using post instead let me propose that we go back first。



![](img/c0e4be0df203b599d64dc2c7b3218c55_86.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_87.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_88.png)

To index Html， because it's in index Htl that we explicitly specified a method of get before。

 So it's very easy in Hml to change the method that this form is going to use from get to post。 Now。

 weirdly， again， in HTMLl， you should lowercase get and post。

 even though when you see them inside the actual virtual envelope or in your developer tools。

 it's capital。 it's an uppercase get and an uppercase post。 But that said。

 let's go ahead and see what happens when I make that simple change from get to post in my form alone。

 because I've changed my HTMLl， I'm going reload the page。

 just to make sure I have the latest HTMLl in my browser's memory。 I'm gonna type my name as before。

 And I'm going click greet。 And notice this time that the URL is not going to display name equals David。

 because I've switched from get to post enter。😊，But even though I'm ending up at slash greet and I'm not seeing question mark name equals David the method is not allowed。

 This is a weird 40，5 error。 Now， why is that？ Well， it turns out if I go into app do high。

 by default， when you create a route using flask as in line 6 or in line 11。

 by default only get is going to be supported。 But if you read the documentation or follow along here。

 you can tell flask what additional methods， if any， to actually support。 So， in fact。

 if I want this greet method。😡，To actually support not get。

 But instead post what I can do is pass in a second argument。

 aname parameter and say methods equals and then pass in a python list of methods that I want to support。

 If I only want to support post， I can literally just do quote unquote post。

 If I want to support get and post。 I can do both as a comma separated list inside of this python list。

 because again， from week 6， recall that square brackets imply that this is indeed aython list。

 But for now， I'm find with just supporting post。 And so I just pass in as the value of methods。

 a list with one valuequote post and all caps。 Allright， let's now go back to my browser tab。

 Let's go back to the form。 let me type in my name again， crossing my fingers and greet。

 and now so close。 the error is gone。 but it's not greeting me， it's using that default value。

 Hello comma world。 Now， this makes sense at a glance。 because clearly。

 there's no parameter being passed into the URL。 but my。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_90.png)

It turns out， was assuming that if there were a parameter， it would come in via get， not via post。

 and this is among the weirder design decisions in flask。

 but whereas get parameters are stored in request。 orgs as we saw a dictionary that gives you all of those key value pairs from the URL。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_92.png)

Post requests， keyvalue pairs are stored in flask using request do form。

 So it makes sense that they come from the form， but it's a little ambiguous。

 at least to me like why we say args here in form here。

 you just kind of have to memorize it or look it up。

 request orgs is forget requestquest form is for post The implication then is if I go back to Vs code here。

 It's a pretty simple change。 I just have to change request orrg to request form。

 So I look in the right place for that key value pair。 Let me go back to my other browser tab。

 click reload， noticing that the browsers now gonna caution me。

 are you sure you want to resubmit this form。 and that's useful because you don't want to accidentally pay for something twice on a website by submitting your credit card twice you don't want to type in your password maybe more times than needed。

 And so in this or send you your password more times than needed。

 So the browsers cautioning me because I'm using post underneath the hood。

 do I actually want to resubmit this form。 So yes， in this case。

 So I'm gonna click continue and now I do see。😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_94.png)

Hello comma David because it's been passed in underneath the hood， if you will。

 inside more deeply that envelope and we can actually see this。 let's do one other thing here。

 Let me go back to the form， let me right click or control click on my viewport and click inspect to open up the developer tools let me go under network here and let's go ahead and do this let me go ahead and type in my name and then clickG and like last week when we were poking around all of the Http request going back and forth from browser to server。

 let's see what the browser is actually sending when I clickG。

 I indeed see that the URL at the top change tog， but there's no mention of David or name but if I go down here into my developer tools and click on that HttP request in my log I can now scroll down and see the request method was apparently post and if I scroll down further。

 I'll see not only the response but if I keep going I'll also see the request headers which are sent inside of that envelope as well。

 but what I really。Ca about in this case， is payload。 If I click on payload。 This is a term of art。

 That means what inputs are you sending from browser to server。

 you'll see a list here of all of the form data name Col David。

 So you can actually see in your browser's developer tools exactly what was sent。

 And you can do this on any website。 The next time you log into a website buy something online。

 you can poke around the network tab of your developer tools and see all of the key value pairs。

 And frankly， you're gonna to probably see many more values than you might have expected because browsers。

 of course， have lots and lots of features more than we're implementing in these simple examples。

 but it's just key value pairs again and again。Allright， so we've solved a bunch of problems now。

 In fact， we've even added a layer of privacy if you will。 In so far as the data is still being sent。

 Yes， but it's not showing up in the URL， which means it's not going to end up in my autocomplete。

 which means it's not going to end up in my history in the same way。

 which is indeed great for anything private like credit cards or the like。

 But what more can we do here。 Well， as we've often done in the past。

 let me see if we can tighten up our code a little bit For instance。

 could we use a single route and still implement the same application。 Now。

 this might not be desirable。 So consider this an example of how you could collapse some of your code into fewer lines。

 But this isn't necessarily to say it's the right way or the only way to do things。

 but I do think it's compelling in some cases， as you'll see， for instance。

 in the problem set for this coming week wherein we adopt a similar paradigm to try to keep the code a little bit simpler。

 So let me go back into app。 and let me propose to do this。

 Let's just have one routelash that does everything。

 including presenting the form and also displaying hello so and so。 But。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_96.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_97.png)

Support both get and post for this route。 So I'm going to say methods equals。

 and then in a python list quotequ get comma quote unquote post overriding the default。

 which again is just get Then inside of this function what I'm going to do is this if request method equals equals post。

 then let's do this else let's do this In other words， if the request coming in， happens to be post。

 and this is just another special variable inside of the request object， which we imported earlier。

 turns out there's another variable， if you will， called method and you can check what is the method that came from the browser。

 is a get is a post， is it something else too And if it is， let's go ahead and do this else。

 if it's not， it's presumably get So let's just render the default template So what can I now do I can grab this code from greet and delete it。

 let me delete the greet function entirely。 And I think。

I can do is just move all of this functionality in here。 Let me fix my indentation。

 but now if the request method is post， then I'm gonna do exactly what we did before else I'm going to display the form to the user So what more do I need to change。

 let me go back to my index HTMLml wherein previously I had an action value of s greet。

 but this is no longer applicable。 There is no more route。

 I just want to submit to slash and frankly at this point。

 I can also just get rid of action altogether because the browser by could default will assume you want to submit to the same URL from once you came。

 but to be explicit。 I'll go ahead and leave it for now。

 Let me go back now to my browser tab and go back。 Let me reload to get the very latest of everything。

 Let me go ahead and type in David and watch now that the URL does not in fact， change to s greet。

 but I am in fact greeted。 There's no s greet anymore but it was in fact sent from browser to server using。



![](img/c0e4be0df203b599d64dc2c7b3218c55_99.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_100.png)

Post and my web application now using just a single route is handling both methods now in this case。

😡，Alright， so we've tightened things up， which might be useful for larger web applications wherein we might want to not have as many functions and complexity in our app pi。

 but what more can we now do。 Well， it turns out Ginja。

 the tempating library that flask uses has its own documentation page。 And frankly， it's super long。

 but there's some fairly simple features documented therein。

 And I'll show us at least one of them here。 So at Ginja thus far。

 it allows us to place values inside of those curly braces。

 It also allows us to do that block feature， which is really templating by definition to grab the contents of layout do Hl and plug in this particular templates block of code。

 But we can do other things conditionally even in Ginja as well。 So， for instance。

 suppose I want in app pi to just get rid of this logic whereby。😊。

I am not only getting the form from the value from the form。

 I'm also passing in a default value in app dot pi。

 supposeuppose that I want to relegate these default values to the templates because after all。

 if what the templates or what the humans actually see。

 it's pretty reasonable then for whoever is creating the templates put the default values closest to the user in those templates。

 So this is to say， let me just get rid of this default value of name for name of quote unquote world。

 And just no matter what is in the form， go ahead and just pass it into the template。 and frankly。

 as before， we don't strictly need this variable at all， I can get rid of this whole line 9。😡。

And just replace name equals。 And then the return value of request dot form do get quote unquote name in order to get that value。

 samee thing， just getting rid of a variable。 if if nothing else。

 but I have gotten rid of two the default value quotequote world。 How can I restore that。 Well。

 here's what's cool about Gingja and templating techniques in general with web programming。

 if I go back to Greek do Html， I don't want to just blindly say hello comma name。

 because name might be blank， it might not have an actual value。 but it turns out that's okay。

 what I'm gonna to do here is the following。 instead of just saying hello。

 I'm gonna go ahead and say hello comma。 And then if there is a name value。

 then let's go ahead and spit it out inside of these double curly braces。 else。

 if there is no name value， then let's go ahead and spit out the word world。 And then as before。

 use end and the same name as the first tag。 And if So we haven't seen the syntax yet。

 but it's clearly similar in spirit to the block。😊。

Stax and this is ginja syntax for doing something conditionally。

 If name has a value that's not empty。 like quote unquote。

 then go ahead and just display the name right here。 else。

 if it is a blank value or absent altogether， go ahead and spit out world instead。

 and that's it for the if conditional。 Now notice I've used like several lines of code here。

 which seems weird because I don't want it to say hello comma。

 And then the person's name on the next line。 But remember how Hm works。

 It's gonna to ignore anything more than a single white space。

 So even though the name or the word world or on different lines。

 all of that whitespace is going to get collapsed into a single space visually for the user in the browser。

 So if I did this right， let's go back over to my tab here and let's go ahead and hit reload on the page itself by clicking on the URL and hitting enter。

 I didn't want to hit command R or control R because I don't want to resubmit the form。

 I want to reload the page And the best way to do that would be。



![](img/c0e4be0df203b599d64dc2c7b3218c55_102.png)

To just go ahead and click on the URL and hit enter， let me go ahead and type my name in and clickG。

 and hopefully there I am again。 Hello， comma David， if I view page source here。

 notice you see the template and you even see that my name is on a new line because that's where it was in the conditional but the browser doesn't care。

 it's consolidating all of that multiple white space into a single white space instead。



![](img/c0e4be0df203b599d64dc2c7b3218c55_104.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_105.png)

So that's a lot of examples just to say hello world。

 But the overarching goal here thus far has been to implement really the simplest of web applications that takes user input produces dynamically Hl that corresponds to that input effectively implementing our very first back end。

 Of course， all of these examples thus far， really just say hello world to the user。

 So let's go ahead though， take a break。 And when we come back and say let's say five minutes。

 we will see how you could implement your very own website for a freshman intramural sports program just as I did like 25 years ago by teaching myself web programming After having taken Cs 50。

 Unfortunately， the Internet back in the late 90s looked quite like this。

 I don't know to this day why I used a repeating background image。

 But that's what the web looked like。 but we'll see ultimately how you can implement something like this。

 when we return in five minutes。 See you soon。All right， we are back。 So back in 1997。

 the way that Harvard Undergraduates would register for freshman intramriural sports。

 otherwise known as Frosh I ams， was they would pick up a piece of paper。

 they would write down their name on it， they would like check off a box for any of the sports that they wanted to participate in。

 and then they would walk across Harvard Yard open up one of the dormitory doors and slide the sheet of paper under the door of what's known as a proctor。

 a resident advisor who was running the sports that year。

 Suffice it to say there was an opportunity to move all of this online。

 even though the Internet itself was still rather in its infancy， or at least as we now know it。

 However， I had already taken C 50 and fall of 1996， this was probably the spring or fall thereafter。

 And I decided even though C50 at the time didn't even introduce people to web programming。

 I actually tried to learn a bit of it on my own。 And I undoubtedly did not do things very well and certainly not the best way possible。

 But at the time， I taught myself a language called Pearl。

 which was very popular for web programming Now。😊，We have languages like Python and PhP and Java and Ruby and Javascript and many others as well。

 But the point is that even after just CS50， maybe one other programming course。

 you really should have this solid foundation via which to teach yourself new languages much like the trajectory we've had you on from scratch to see to Python to sQL to jascript and now bringing it all together in the context of web programming So let's without the ugliness recreate a little bit of what I build way back when to allow students to register for Fro I ams via web browser instead of a piece of paper。

 Let me flip over here to Vs code where in advance of this demonstration。

 I prepared a few files based on the hello demos from before in particular in a Fro Is directory which I created a new I have the following files already app up requirements text and templates and inside of templates。

 I have index Html and layout Hl and let me go ahead and hide my terminal。

You can see in the latter the following layout， which is identical to what we used a moment ago for our hello examples。

 but I've changed the title from hello to Frosh Is。 the index template， meanwhile。

 extends that layout or equivalently inherits from that layout。

 but I haven't put any body inside of this block here。

 I deleted what we had before just so I don't have to type as much to get us started now。

 And then in app pi similarly， I copied the first couple of lines of code but deleted all of my routes just so that I dig don't have to type all of those from scratch。

 But let's go ahead now and implement the simplest of registration forms for some number of sports。

 And what I'm going do is the following I'm going go over to my index hl。

 which again extends already layout hml。 and let's begin to put together a registration form。

 I want this page to very clearly be about registration。

 So I'm going like an H1 tag and I'll say register for instance。

 And then below that I'm gonna have the start a form tag The action of which I could make anything。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_107.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_108.png)

I slash itself。 but let's keep things clear。 and let's have the action B slash register for this one。

 and the method for this one will be quote unquotepost inside of this form tag notice now I'm going to have an input I'm going to turn off autocomp as before I'm going turn on autofocus for that input and I'm going to specify that the name of this input is itself name because this is going to be for the student name who's registering the placeholder value I'm going to use is capitalized name to make clear in gray text。

 what they should type in and the type of this just to be explicit is indeed going to be a text box Now I'm going introduce another form element that you see all over the place on the web even if we haven't necessarily had occasion to use it ourselves。

 I'm going to have a select menu， which is equivalent to a dropdown menu in a browser and the name for this menu is going to be sport because I want this dropdown menu to be a list of sports that the student can select inside of that let's come up with three sports for now option value equals basket。



![](img/c0e4be0df203b599d64dc2c7b3218c55_110.png)

Ball and then inside of the open tag and close tag for option， I'm going to just repeat myself。

 Ba ball。Then below that， I'm gonna have another option whose value is going to be soccer American football in this case。

 Then I'm going type soccer inside of the open tag and close tag。

 And then the third and final option will have a value of quote unquote， ultimate frisbe。

 and then inside of that open close tag。 I'll say again， ultimate frisbe so。

This clearly eces some redundancy。 However， what this reveals is that with a select menu。

 much like with links with the anchor tag， you can have the human see one thing。

 but the value actually used is another， even though for simplicity。

 I'm keeping them exactly the same。 Now， let me go ahead and go into my other tab。

 which up until now has been saying hello， David and hello world。

 but I haven't stopped running flask。 And so if I keep doing this and reload what if I keep visiting this URL。

 I'm going to keep seeing that form。 And if I type in David。

 I'm gonna to click greet because my previous web application is still running。

 So I can't just start making a new web application and expect that this browser tab is going work。

 even though it's still port 5000， let me go back to V S code open my terminal window。

 go to my very first terminal wherein we see all of the logs from flask that have been running。

 And in fact， among the error messages there is actually some diagnostically useful output sometimes what flask is showing you in this terminal window。

 even though I've hidden it most of the time。😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_112.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_113.png)

Is a log that is a recording of all of the get requests and all of the post requests that came from a browser to the server and you're seeing dates and times。

 the IP address and so forth， some of which is going to be not very useful in this environment because we're using a code space instead of putting this website on the actual web publicly everything is private now to me but there is some diagnostically useful information there。

 for instance， this get request at the top return status code of 200 as did every post and get below that。

 but this too is again where we'll see any errors and if we start introducing SQL before long。

 we'll even see copies of our SQL queries so that we can diagnose any problems in those But this is all to say that I don't want flash to be running in my hello folder anymore。

 So I'm gonna hit control C to interrupt that I'm going hit Cd to get back to my default folder。

 I'm going type Cd Fro I ams now which my other terminal was already in and indeed if I type Ls in here I see those same files。

 But now I'll clear my。And I'm gonna rerun flashask run in my Frosh Is folder。

 turns out that's going to open up the same port 5000 by default。 So in fact。

 I can just directly go back to this tab， which previously was my hello app and just by reloading that URL enter now I see not found404。

 So I've clearly broken something But why is that I don't have any routes in this fro Is application yet because I started almost from scratch。

 So let me go ahead and close my terminal window for now and go back to app and let's just start serving up that default template quite simply。

 let's do app route as before quote unquote let's create a function as before called index that we could call it technically anything we want and let's have this function do very little let's just return render template passing in index Hm Now for this new web application that route exists which means if I go back to my other tab hopefully it will be found when I click reload。



![](img/c0e4be0df203b599d64dc2c7b3218c55_115.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_116.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_117.png)

And sure enough， there is my registration form with a name field and the cursor is autofocus inside of it with the cursor blinking。

 And there is my select menu。 Indeed， if I click on it， I see basketball soccer and ultimate frisbee。

 So this form doesn't really do anything yet。 And frankly。

 I'm not sure I love the fact that basketball is sort of the implied sport。

 like it would be nice to maybe see a default value or blank value。 That's just an aesthetic detail。

 if I go back to VS code here。 go back into index。 There's a few ways I could fix this。 I could do。

 for instance， option value equals quote unquote maybe nothing because it's a default value。

 and I could just say something like sport to be sort of a title for that dropdown。

 let me go back to my browser reload。 And yeah， sure enough， I now have sport as the top option。

 but this is a little weird because I don't want the user to be able to register for sport。

 I don't really want it to be a selectable option。 So it turns out there's some other attributes we can play within this context。

 And in fact， if we want to display a title like。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_119.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_120.png)

That sport， we can actually specify that the option itself is disabled。

 but it is selected by default。 So these are two other H attributes that you can use with the option tag in Hl。

 They don't need value。 so they don't need equal signs or quote marks。

 you can just say disabled and selected。 But now when I go back to this tab and reload once more。

 notice that it indeed still says sport but it's grayed out。 So I can't actually submit that value。

 I can only choose from these three things here。 And using libraries like bootstrap for CS。

 you can style these things even more beautifully than this。

 but this is perhaps the simplest way to at least have a title for that there select menu。 Allright。

 I need one more thing in this form。 Let me below my select menu here。 let's do a button。

 the type of which is submit。 And then that's gonna be a register button now instead of greet。

 So if now I go back here and reload one more time。 Now I have the name。

 the sport drop down and the registration button as well。

 But we're not yet in a position to do anything with that information。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_122.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_123.png)

Until I think we implement another route。 So let me go back to VS code。 let me open up app pi。

 And in addition to my index route， which is just serving up that web page。

 let's create another route app dot route quote unquote register This one just for privacy reasons is going to use post instead of get。

 So I'm going to say quote unquote post inside of a Python list there。

 Let's define another function called register。 So again， it can be anything I want。

 But I like to name them exactly the same as the routes themselves to keep things straight。

 And then let's go ahead and do this。 Let's go ahead and check whether the user has registered or not and then tell them whether we're successful or there's a failure。

 So for now， let's actually well， let's do this。 How about we return this to keep it simple。

 return render template and let's pretend like a template exists for success do Hml。

 This suggests that I should probably have a template called success Hl。 So let's whip。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_125.png)

Really quickly and in success do Html， let me do this。 first。

 let me open my terminal and get to a prompt so I can type code actually first C templates to make sure it's in the right place。

 then code success Html in this file I do need a bit of boilerplate。

 So extends quote unquote layout do Hml with the close quote this time， then block body over here。😡。

Then I'll do an end bloody body。 so close。 block body。 Then let's end block down here。

 And inside of here， let's just say something successful。 Like you are registered， well， not really。

 because we not， We haven't actually done the hard part yet。 Let me go back now to app pi。

 just to confirm that， okay， when this route is called， no matter what for the moment。

 we will render success dot H Tl。 So let's try it。 So's go back to the browser here， type in David。

 let's choose say basketball for the sport and click register。 And internal server error 500。

 which we know is my fault。 So let's go back to V S code。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_127.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_128.png)

Let us open up my terminal window。 Let's go to the first one that's running flask run。 And。

 I did it again。 somehow， a template syntax error， unexpected curly brace。 Alright， well。

 where could that be， I did it again， But this time with a different character。 Okay。

 so I was so focused on adding the double quote， I did not add， in fact， the。

the curly I'm so focused on adding the double quote。 I did not add the second percent sign。

 So now let's go back to my internal server error。 click reload。

 resubmit the form that I just submit it。 And now I'm told you are registered Well， not really。

 That's because the route's not doing anything intellectually interesting yet。

 It's just rendering that template blindly。 All right， well， let's improve upon that。

 I think what we should require is that to register for a sport。

 the student should have to provide a name and have to provide a sport。 Unfortunately。

 that is not a current requirement。 For instance， if I go back to the form。

 And I don't type in a name and I don't type in a sport and click register。

 I'm still told you are registered to be fair。 I'm told， well， not really。 So， you know。

 let's make clear that this is a bug， let's get rid of the parenthetical。 let's go back to the form。

 Let's not type a name， let's not choose a sport and click register。

 Now it's clearly buggy because I am not in fact， registered。

 I've done nothing with this information。 Allright， let's go back to VS code here。

 Let's go back to a。😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_130.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_131.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_132.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_133.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_134.png)

And let's express this idea of if there's not a name or there's not a sport。 It is a failure。

 Do not let the user register。 So let's try this。 We can express this in a few different ways in Python。

 I'm going propose to do it like this。 if there is not a value for request form get quote unquote name or there is not a value for request dot form do get quote unquote sport。

 then go ahead and return render template quote unquote failure Hml else if there is a value for name and for sport。

 great， let's go ahead and render template success do hm Now I can tighten this up slightly strictly speaking。

 if I'm conditionally returning a template in line 14。 I don't really need the else。

 So just to type this out， I'm going to remove that all together。

 but this is just the same kind of logic we could have done in C or in Python before we introduce flask or。

😡，Javascript， this is equivalent to an if else because returning， of course。

 immediately returns from this register function。 So you don't strictly need the else。

 And I'm doing this just to tighten up the code， but it's not logically necessary。 Of course。

 failure do htl does not yet exist。 So let me save a couple keystrokes here。

 Let me copy the contents of success Html。 Let me go into my terminal。

 create another file called failure html。 I'm going to go ahead just to save a moment in class to copy paste that there。

 but I'm going to say this in this template。 You are not registered。 Now granted。

 I'm copying and pasting which almost always is a bad thing。

 but when it comes to using templates in flask using gingja here， you do still need lines 1。

3 and 7 to make this work So those are necessarily copy pastable or retyable。

 But now I think we have two scenarios。 Let me now go back to the form。

 Let me go ahead and type in my name。 and choose my sport and click register and we're still good。

 we haven't done anything with the data， but at least the human cooperated。



![](img/c0e4be0df203b599d64dc2c7b3218c55_136.png)

Go back now， Reload the page。 Don't type a name。 Don't choose a sport and click register。

 Aha Now we're at least telling the user they are not registered。 Allright， so we're making progress。

 We are conditionally checking whether or not the user has actually registered for sport。😡。

Let's now make sure that they can't really hack us or do something malicious because right now。

 if they type in their name and they type in a sport。

 we will register them or so we say but recall that anything client side isn't necessarily robust。

 In fact， let me go back to index do Hm and let me actually do this。

 let me add the required attribute here and let me add the required attribute here。

 You don't need to give it a value within an equal sign and quote unquote。

 let me go back to my browser and click reload and now let me try to click on register without giving a name or a sport。

 unfortunately， the browser prevents me。 or fortunately， the browser prevents me。

 so let me type in David， let me not choose a sport register。 okay。

 so we seem to have error checking now preventing the human from submitting this form without valid data。

 but not quite because indeed， all of this is happening client side。 If I view source in my browser。

 I can see。😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_138.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_139.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_140.png)

The required attribute at the end of the input tag and at the end of the select tag here。

 but recall that this is my copy of that HTML and if I want to be malicious。

 I could control click or command click on my viewport and choose In to open my developer tools。😡。



![](img/c0e4be0df203b599d64dc2c7b3218c55_142.png)

Recall from last time I can look at the elements of this page。 Pre printed like this and notice here。

 Let me shrink the CSS part of this window。 Notice that I can actually edit this HTMLml if I want。

 For instance， I can sort of click on required click delete and then save it and now the registered the required attribute is gone。

 I can do the same here on the select field and get rid of that。 And now it's gone。

 And now I can type in David， but I can， for instance， skip the sport and click register。

 and it doesn't stop me anymore from doing that because I've disabled client side validation。

 Moreover， things can get even more malicious。 suppose that in a protest vote。

 I don't want to register for basketball or American football Aka soccer or Frisbee。

 like I want to register for like actual football。 So in the European sense， for instance。

 So let me go into my attributes here。 Let me change the value of soccer to。😊。

Let me change what the user sees from soccer to football。 And now let me go ahead and save that。

 now let me confirm that I still got my name， but notice now I can register for football and of soccer click register and now I'm registered for a sport that at least semantically is not even supported in the web application itself and frankly by that logic。

 I could have register for any sport that I happen to type in into the web pages HTML。

 which is to say we need server side validation。 it is fine to use client side validation as by adding the required attribute in places if you just want to give the user immediate feedback and prevent sort of good users from doing something incorrect or foolishly you can't prevent the adversaries。

 the malicious users from messing around with your form using client side techniques alone So let's go into Vs code again。

 and let's this time open up app dot pi and in app dot pi。

 let's go ahead and make a canonical global variable containing。



![](img/c0e4be0df203b599d64dc2c7b3218c55_144.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_145.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_146.png)

All of the sports that are officially offered this semester。

 so let me create a variable and I'll call it sports in all caps。

 even though Python does not have constants per se。

 still conventional to capitalize the variable just to make clear that you shouldn't change this and it's global let me go ahead and set this equal to the followingython list this list is going to contain basketball quote unquote soccer quote unquote and ultimate frisbee here as well and you can it's often conventional to have a trailing comm even after the last element just to make it easier to copy paste and reorder things in code。

 even though logically it's not in fact necessary。 what am I going to go ahead and do next now， well。

 if I have now this variable containing all of these sports I don't actually need to hardcode them into my template so I'm actually going to do this let me pass in a placeholder called sports into this index template and set it equal to that global variables value and now in。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_148.png)

Indexed Hml， let me go ahead。 and instead of enumerating all of these sports manually。

 let's use another feature of Ginja， which is gonna to make our life easier and much more dynamic。

 whereby I can use a ginja for loop instead。 So let me go into my select tag here below that disabled option let me use open curly brace per sign for sport in sports。

 So notice this is ginja syntax per the curly brace and per the percent signs。

 but it's very python like。 it's very similar to the exact syntax you would use in python。

 but there's no colon and strictly speaking we're inside of the template here。 Below that。

 let me just proactively say end4 and it's a little weird。 but again。

 this is how ginja does things you end the name of the ginja tag that you began per its documentation to。

 and then inside of this loop， let's just generate one option at a time。

 So open bracket option value equals quote unquote and this is where temp and gets really powerful。

 curly brace curly brace sport curly。

![](img/c0e4be0df203b599d64dc2c7b3218c55_150.png)

curly brace， close quote。 And then so that the human sees the same。

 Let's do it again out there as well。 But technically。

 those could be different values from what the human sees and the browser sends。

 So now we don't have three sports here manually typed in。

 we're doing this dynamically because we're passing in a placeholder called sports。

 But instead of just spitting out its value， we're using a for loop in Ginja to iterate over that loop and generate 1。

2，3 options programmingmatically instead。 So here is the programming in web programming。

 we are generating all the more Hm now using some logic。 Allright， let's now go back to my other tab。

 go back to the original page and click reload。😊，I screwed up somewhere else。 Allright。

 so let's go back to VS code。 Let's open up my terminal window。 Let's click on the first terminal。

 And， oh， name error。 sport is not defined。 Did you mean sports。

 So now Python is very graciously trying to be nice to me here。 Yes， I did mean that somewhere。

 So let's go back to app up high stupid mistake， Sports equals sports。

 So now if I go back to my browser， click on reload。Now I have another error。

 So we go back to V S code， reopen the terminal。 Now， I'm just an idiot。

 So it's not sports with two Ss。 So that was a mis click。 Let's delete that。

 And let me stop touching the keyboard。 Let me go back to the browser。Let me reload a third time。

And there we have it。 Very impressive。 I know。 So now I've gotten thank you for the applause。

 Now we've got the name field。 the sport field， all of which are still there。

 but they were dynamically generated based on the value of that variable。

 So what's valuable about that technique。 Well， one。

 I'm not manually typing out all of these options anymore and think about the extreme。

 if it's not three sports， but 30 sports or 300 sports or whatever。

 you don't want to manually type all of that out， you probably just want to have a simple Python list of those values。

 or heck， we could put even put it in a text file or a database if we wanted。 But more。

 now that the server knows what the value sports are。

 We don't have to just naively check if there is a value for sports， as we previously did。

 I could probably do something logically now where I make sure that the sport we did get is one of the supported value。

 So now we have server side validation as well。 So how can we do this。 Well。

 relatively straightforward。 if we have this variable called sports。😊，Capital S， at the end。

 I can instead do something like this。I can change my logic to say if there is not a value for name or the current sport is not in the sports variable。

 then consider it a failure。 It's a very nice pythonic way to let Python essentially search through the whole list of valid sports checking for the value that human actually sent。

 and if it's not there， we are going to return the failure template。 So now if I go back to Frosh I。

 let's reload to get the fresh copy of the form。 let's type in David。

 let's go ahead and not choose a sport and click register。 I still have the client side validation。

 That's fine。 but let me go ahead and hack that by removing it， let me open up inspect。

 let me go under elements inside of this form let's get rid of the requirement for the name。

 even though I gave one， let's get rid of the requirement for the sport。

 even though so that I don't have to give one close my developer tools notice I still have not chosen a sport。

 click register。 it goes through。😡，But we catch it and we tell the user no you are not registered。

 Moreover， watch this。 Let me go back to my developer tools。😡，Let me go into the form again。

 Let me not only delete the required aspect of this from both of those tags。

 let's also change soccer to football， which while technically the same sport across countries is not the same string that we want in the server。

 So let's change soccer to football here and soccer to football here。

 And now close my developer tools， type in my name。

 but choose an invalid sport that the server does not know about， click register。

 still catches it because now we are doing server side validation。 And I cannot express this enough。

 if you proceed after CS50 or even for your final project。

 let alone problem set 9 to implement validation of user input。

 you should never ever trust what the human themselves are sending and you should never rely on client side validation alone。

 It's all too easy for someone who's just taking a single introductory course to disable all of your client side validation。

 So if you value the safety of your server， the integrity of your data。😡。



![](img/c0e4be0df203b599d64dc2c7b3218c55_152.png)

Always check server side for valid values。

![](img/c0e4be0df203b599d64dc2c7b3218c55_154.png)

Alright， so what more can we do to improve this kind of application。 Well。

 we can tinker with the user interface a little bit。

 if only so that you've seen different UI user interface mechanisms， let me go back to the form here。

 And indeed， we have now this dropdown menu， otherwise known as a select menu。 Well。

 there's other ways we could get input from the user。 In fact， let me go back to my index do Hml。

 and we don't have to strictly use， for instance， a select menu。

 we can actually use input tags to achieve what are called radio buttons。

 Those little circular things that you can choose among sort of like oldtimey car radios where you would push one button and it would pop another out。

 you pushing in that button。 and it pops another one out。 same thing with radio buttons in the web。

 they are mutually exclusive。 You can choose one but not multiple radio buttons by design。

 So how can I do this。 Well， in my index Hml。 Let me go ahead and get rid of the select tag there and the select tag here。

 Let me go ahead and get rid of the disabled option。 And then。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_156.png)

Just go ahead and still iterate over all of the sports。 But instead of spitting out an option tag。

 which is only relevant for the select menu， let's go ahead and spit out an input tag whose name is quote unquote sport。

 the type of which is no longer text but radio， the value of which is the current sport in this current iteration of the loop。

 quote unquote and then to the right of it just so the human has something to look at。

 let's also repeat the name of the sport。 So again here， we're making a distinction。

 just like with anchor tags for links。 what the human sees and what the server see。

 but they can be one and the same。 Let me go back to my other tab。

 let me go ahead and reload this and my select menu will now be replaced with some pretty ugly。

 but still functional radio buttons。 Let me go ahead and zoom out。 So it all appears on one line。

 And now if I type in my name。 and I select something like basketball and click register everything else is the same。

 But I've changed the frontend by changing the Hml。 Of course， whether we're using。



![](img/c0e4be0df203b599d64dc2c7b3218c55_158.png)

Select menus or radio buttons。 We're still never actually telling the user why they're not registered in those cases where something goes wrong。

 where， for instance， they accidentally leave a field blank or even maliciously。

 they try changing those fields。 So how can we go about being a bit more informative。 Well。

 let me go back to Vs code here and inside of our register route， which is doing the validation。

 let's do a little more validation than we are at the moment。

 And let me propose this let's be a little more verbose with our error checking。 And how about this。

 Let's first go ahead and grab the name that the user typed in if any。

 So name equals request form do get quote unquote name。

 and then let's ask a question just like we did before， but with a shorter block of code if not name。

 then go ahead and return render template。 But instead of just simplistically returning failure do hl with no clarity as to what has gone wrong。

 Let's return a different template error Hl。 And let's pass in a specific error message to the template that the human will see。



![](img/c0e4be0df203b599d64dc2c7b3218c55_160.png)

That's somewhat informative。 And in this case， I'll say aptly missing name， quote unquote。

 just so that there's more informative errors。 Otherwise， let's go ahead and do this。😡。

Let's first get the sport from the user from request form get quote unquote sport。

 And then as before， if not sport， let's go ahead and return an error。

 but this time with a message return， render template， quote unquote error Hml。

 but the message this time will be missing sport。 But there is something else that can go wrong here。

 if the sport， the user typed in is not in our sports global array global list。

 then let's return render template， quote unquote error do Hm。

 but the message this time will be in valid sport。 Now， ideally。

 users should never see this latter message at least because only if they tried to hack our HTMLml。

 so to speak， would they actually be able to submit an invalid sport。 but for good measure。

 you should assume the worst， and you should absolutely be handling this error。

 even if you don't strictly speaking need a user friendlyly error message for those same adversaries。

 But otherwise， I think we can assume it success as before。 but we do need。

To create this here template。 So let's do this。 Let me go ahead and close success do Html。

 Let me go ahead and openfa dot htl。 but now close it。 and let me go ahead in my terminal window。

 create a new file code of error do Html paste the contents of failure do Htl。

 just so we have a starting point。 But in error do Html， let's actually have a more useful message。

 instead of just saying you are not registered。 Let's instead say something like H1 error to make clear that this is an error page and then maybe put a paragraph of text below it。

 even though it's accinct and plug in that message that we passed in via get template。 Okay。

 let's now try to induce this here problem。 Let's go back to index do Htl let's get rid of the required attribute so that I don't have to keep hacking my own Hml。

 but let's now go back to the tab with the web application， go back to the form itself。

 which in its most recent incarnation is indeed these radio buttons and let me not type a name and not type a sport。



![](img/c0e4be0df203b599d64dc2c7b3218c55_162.png)

Click register in just a moment at which point previously I saw you are not registered。

 Hopefully this time I'll see a more useful error。 indeed， missing name。 It's not a very pretty page。

 but at least it's giving me some information。 So let me go back and type in my name Now let me register without choosing a sport a missing sport and if I did again hack my HTMLml so to speak by changing soccer to football that too which show an error but invalid sport according to my logic Now just for fun。

 we could make these error pages look a little more interesting and in fact。

 what I'm going go and do is this let me go back into Vs code let me go ahead and open up error do hml and below that informative error message。

 let's choose an image tag let's specify that the source of this image tag is gonna be that of a file maybe a picture of a cat However。

 as I hinted earlier when we have static files like images or CSS files or javascript files by convention they should be in a folder called static。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_164.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_165.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_166.png)

InMy Hml， I'm going literally say slash staticlash cat do jpeg。

 I happen to know already that this is gonna be a grumpy cat。 hence the error message。

 I'm going to give an alternative text for accessibility of grumpy cat whoses internet famous and now I'm going open up my terminal I am going to clear it Cd do dot to go back into Fro I where again at the moment we have just app pi requirements text and templates。

 I'm then going to go ahead and make a new directory called static all lowercase。

 I'm gonna Cd into it。 And then with a wave of my hand I'm going to go ahead and copy from today's distribution code a copy of cat jpeg so that now when I type L I indeed have a cat jpeg that I came prepared with earlier。

 Let's now go back to my browser tab let's click reload to still submit a form that's missing a sport but now we should see per the image tag we've introduced and the cat jpeg in the static folder that I indeed now see。

😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_168.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_169.png)

Very grumpy cat for this error message。 Now， using some CS and such。

 I can make it prettier and make the cat and not take up the entire web page。 But for now。

 we've at least demonstrated how we can have a static file alongside dynamically generated content by putting that static file in the static folder。

 Allright， so now let's actually do the most useful thing and start storing in memory these names and sports for which students have registered。

 let's go back to app and acknowledge that at the bottom of this register route。

 all I'm doing is blindly saying success Hl， you are registered。

 even though I've not done anything with the actual data。

 So it's an app high that we have the opportunity to save some of that data。

 And so what I'm gonna do is this at the very top of the file， but below my sports variable。

 let's create one other variable and all cap registrants and I'm using all caps again to signify that this is a global variable。

 even though it's not constant。 let me set that equal to opencurly brace closed curly brace。

 which even though we've been doing。😊，Curly braces all over the place in our templates per gingja syntax。

 We are just in app pi Now。 This is Python syntax from week 6。

 where I've now created an empty dictionary or diict object in Python by using curly braces。

 This is the same thing as saying dit open per endclo per N。

 which is returns to me an empty dictionary， but it's a little more pythonic just to use the syntax of open curly brace close curly brace。

 But why this。 Well， if I've got names and sports， names and sports， that's like keys and values。

 I might as well store that kind of data in a Python dictionary where the keys are the names and the values are the sports。

 So how do I do this。It's actually pretty simple right before I declare that the student is registered。

 let's just go into that registrance array。 sorry let's just go into that registrants dictionary。

 lets index into it at the name location that I want to put into the dictionary and set it equal to the value of that sport and I'm simply using the variables that I created earlier。

 for the purposes of doing error checking and using the name and sport in different places。

 but I'm now using that same variable name and that same variable sport as my key and value pair Now as an aside。

 this is a little naive of me and it's not the best implementation as written。

 this will not let to Davids， for instance， register for two different sports why because we're allowing one name to overwrite another identical name So if two Davids try to register for these sports。

 probably not a good outcome because we're going to cloer or overwrite the previous persons registration but let's consider a simple world in which there's only one of any name in the world so that we dont。

😡，Have have to worry about that just yet。

![](img/c0e4be0df203b599d64dc2c7b3218c55_171.png)

Now， let's go back to my other browser tab clicking back in that。 So get back to the form。

 Let's type in David。 let's type in basketball and register says that I'm registered but who knows at this point。

 Let me go back to the form， let me type in Ulia and let's register Ulia for soccer click register claims that she too is register even though who knows but hopefully in app pi before success HTML is rendered。

 We're indeed adding David and then Ulia and then anyone else to that global dictionary And so long as the server stays running that dictionary of keys and values is just gonna get bigger and bigger and bigger。

 but let's see if we can't show ourselves those registrants。 Well。

 maybe the simplest way to do this is to give ourselves a third route。

 So let me say app route quote unquote slash registrants and then below that decorator let's say de registrants to define a new function called exactly that and let's keep it simple return register。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_173.png)

sorry， return render template， quote unquote registrants do Html。

 but I got to pass in those registrants to the template。 so it knows what registrants to show。

 That's fine。 registrants equals registrants in all caps。 So same convention is before。

 but I'm providing the registrants hl template with that global dictionary of names and sports。

 Of course， I need another template。 So let's do that。 let me open up my terminal window。

 let's go back out of the static directory。 Let's go into the templates directory。

 Let's create a template called registrants do Hml。 I'll close my terminal。 And up here。

 I'm gonna do the same boilerplate as before。 extends quote unquote layout do Hml。

 and I'm gonna type every keystr correct this time。 Then I'm gonna say begin no， I'm not。

 then I'm gonna say block body sign closed curly brace down here。 I'm gonna say end。😡。

And then the same。 And in here， I am going to output a list of all of the registrants。

 and I can do this in a number of different ways。 but frankly。

 I think it suffices to maybe just kind of do maybe a bulleted list initially。

 So how might I do this。 Well， I could do something like an unordered list tag there。

 inside of which I have a whole bunch of list items or L tags。

 How well I could do something like this。 for name in registrants。

 which is the placeholder or the rather the variable， the parameter。

Which was the parameter that was passed in。 Then let me proactively close that for tag in Ginja。

 and then in here， let's do li。 and then inside of the open andclo tag， let's just do name for now。

 before we take a look at the effect of these changes though I am going open my terminal window and I'm gonna hit controlr C just to stop the server。

 and then I'm going rerun flask run just to ensure that flask knows about this very latest version of my code into which I've added that global dictionary。

 Now I'm going go back to my same browser tab as before， which is still running on TCP port 5000。

 and I'm going try to register a couple of people。 So I'm gonna register myself for basketball for instance。

 and I seem to be registered， I'm then going to go back and I'm going try to register Julia。

 say for soccer and I'm going to click register and now my hope is that both David and Yulia are in the server's memory in that global dictionary as keyvalue pairs So if I go up to my URL here and zoom in and I change register to registergistrants and hit enter。



![](img/c0e4be0df203b599d64dc2c7b3218c55_175.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_176.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_177.png)

I indeed see now a bulleted list of all of the names of people who have registered for sports thus far。

 Now it doesn't have to be a simple bulleted list because it would be nice to know what sports we registered for。

 but that's just a matter of HTML。 Let me go back into VS code and hide my terminal window Let me go into registrants Hl。

 and we can go all out in this if we want。 For instance。

 let me go ahead and do this Let me get rid of the unordered list tag there。

 let's give ourselves a proper title of registrants this time in an H1。

 Let's then begin a table inside of which is going to be a tablehead initially。

 and inside of that tablehead will be a table row and inside of that table row will be two table headings namely name as well as another table heading of sport。

 In other words， I want to have a two column table if simplistic that shows me name sport name sport or more generally keyvalue pair below the tablehead。

 Let's go ahead and do a tbody for table body inside of that table body。

 Let's now iterate over that same dictionary。 but。

![](img/c0e4be0df203b599d64dc2c7b3218c55_179.png)

Do it a little more pedantically such that I'm going to do for each name in the dictionary in that registrance dictionary。

 Then let's proactively put an N4 below that。 And inside of this four loop。

 let's create a table row for each person let's create a table data inside of that row inside of which is going to be that current name Then in the second column via a second table data tag。

 let's go ahead and put put the value of that key， the syntax for which just like in Python is registrants but index into that dictionary at that specific name with curly braces on both sides。

 As in Python， when I inerate over a dictionary in Ginja here in this your template。

 I'm indeed iterating over all of the keys in that dictionary。

 So if I want to get at the value I need to use that key that is name to index back into that dictionary。

 Now if I go back to my browser tab here previously I saw all of this as an unordered list。

 but if I now click reload on my registrants route， I now see a big。



![](img/c0e4be0df203b599d64dc2c7b3218c55_181.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_182.png)

H1 tag registrants， followed by a simple H table， one column for name， one column for sport。

 It's not the best formatted， but I think if we introduced some Cs， whether my own or bootstrap。

 for instance， we could make that even prettier as well。



![](img/c0e4be0df203b599d64dc2c7b3218c55_184.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_185.png)

All right， with all that said， I think we' have an opportunity for maybe one final version of Frosh I ams whereby we can actually store all of these registrations in a database。

 The problem at the moment being this。 if I go back to VS code here and open my terminal window。

 and either intentionally or accidentally hit control C such that the server stops or worse。

 the server loses power or somehow the server reboots。

 everything I've stored in the server's memory and that global dictionary is going to get erased by default because I'm gonna get a brand new dictionary when the server restarts。

 In fact， if I rerun the server now with flask run， go back to that very same tab。

 which had David and Ulia and click reload， all of a sudden we gone and the table is empty except for that heading。

 So that's not the best way to persist data。 In fact， if that could happen。

 we might as well go back to yesterear's pieces of paper to keep track of everything。

 But I think we can fix this。 So wouldn't it be nice if we could use a proper SQL database instead to store all of these key value pairs。

 Well， in fact， let me go。😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_187.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_188.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_189.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_190.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_191.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_192.png)

Back to Vs code here。 and inside of Vs code。 let me show you a database file that I prepared in advance。

 Let me maximize my terminal window。 and I've just copied over already a file called Frosh ims do Db。

 which is a database just for these intramural sports。

 Let me run our old friend SQL light 3 on Frosh Is do Db that puts me inside of the SQL light program and recall that if I type dot schema。

 I can see what table or tables are inside of this database。 sure enough。

 there's just one table here called registrants， and it seems that that table has three columns。

 an I column which is an integer， presumably the primary key， a name column。

 which is text that cannot be null and a sport column that's also text that cannot be null。

 And sure enough， the primary key of this table is that first column Id So if I now take on faith that this table exists。

 even though at the moment， select star from registrants seems to have no rows in it。

 I think I can write some code to put registrants there。 So let me go back to app。😊。

Here and at the top of my file， let's do this from CS 50 import， it's SQL feature。

 And then down here， a few lines later， let's go ahead and create a connection to that database via a variable called Db set it equal to SQL quote unqu SQL like colon s So even though looks like a URL。

 you do need the third slash in this case Fro ims do Db and recall that from week 7。

 this is how I'm going to be able from Python talk to that SQL database let's know scroll down to this registrance variable。

 which previously I was using to store these key value pairs and let's just get rid of it all because I don't want to keep storing these registrations in memory let's go down further to my register route and get rid of the use of that dictionary because instead I want to do something now with SQL in particular。

 I'm going to do this Db dot execute quote unquote insert into registrants。

 maybe two things name comma sport。 I'm gonna let SQL light automatically fill in。😊。

The with auto increment， the IDd column therein the values I want to plug in though are these two with two placeholders。

 question mark question mark close quote and the two values I want to plug in for those placeholders in SQL are name and sport respectively。

 So here too I'm using the same terms placeholder， but in the context of SQL not in the context of Gingja。

 the syntax and the purpose is a little bit different。

 but that's exactly what we explored in week 7 with SQL and Python。 Now after that。

 I think we're good with the register route What we do still need to do is get rid of this final use of that dictionary。

 previously I was passing into my registrants route that global dictionary。

 So I have all of those key value pairs。 Now a sQL tables， not all that different from a dictionary。

 If we focus on just two of its columns name and sport。

 So how can I get at those columns inside of my registrants route。 Well。

 let's create a registrants variable said it equal to Db do execute and this part's easy select name comma。

Sport from。Registstrants to select exactly those two columns。

 that's going hand me back a list of dictionaries， each of which itself represents a name value and a sport value。

 So if I now change this value from registrants in all caps to registrants lowercase。

 this is the variable being passed into template， this is the value thereof。

 and I think if I go now into registrants do hm， I just need to make a tweak whereby now if I'm iterating over。

Those return values from Db dot execute， I need to be a little more explicit。

 So instead of iterating over a dictionary as I did before。

 I'm going to more generally iterate over a registrant in that list of dictionaries and I'm going spit out here regrant do name and down here I'm going to spit out registrants dot sport。

 And it turns out in some context I can use either the square bracket notation or even the dot notation。

 the dot notation being a little easier to read because there's less syntax but the reason I can do that is because again。

 the regstrants variable that I'm passing into this template is itself a list of dictionaries and each of those dictionaries represents a row from the SQL table And so if I want to access the name column therein。

 I can say regrant dot name or the sport column therein。

 I can access registrant singular this what is about to be my next typo regrant do sport And so now crossing figures B time this time。

 let me go。

![](img/c0e4be0df203b599d64dc2c7b3218c55_194.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_195.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_196.png)

And go back to the form itself。 Let me go ahead and register myself for basketball because we cleared the memory when switching to SQL。

 Let me now go back again and register say Ulia this time for soccer and register and now let me manually change my URL to be registrants big time crossing my finger and there we have it David and Yulia。

 I was surprise as you as at work this time， But David and Yulia are registered and more importantly。

 if I go back to VS code here， select star from registrants in my database， there are those two rows。

 Moreover， if I exit out of SQL light， and I go into my other terminal and even control C and restart flask with flask run and go back to slash registrants in my browser and reload the data is still there we have made now a fullfledged web application。

 if ugly that is actually storing data permanently full time that survives clearing of memory and even re。



![](img/c0e4be0df203b599d64dc2c7b3218c55_198.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_199.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_200.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_201.png)

It'sOf the server。Alright， still more to come。 Let's go ahead and take a five minute break。

 And when we come back， we'll add some of lastly some of the most familiar features that you see in today's actual web applications。

 See you in 5。Alright， so up until now， even though we've been building an application that's very specific to Fro Is。

 it's actually representative of a paradigm when it comes to web programming and software engineering more generally。

 In fact， up until now， what we've really been implementing is a couple of concepts。

 One is what we generally know in software engineering is a controller。

 So app pi is representative of a type of program that you might call controller for exactly that reason。

 it's controlling everything about your application。

 it contains the so-called business logic for your application。 Meanwhile。

 though there is a part of the application that the user season interacts with and that's generally known in some circles as a view。

 So everything in the templates folder really is a so-called view。

 But in that most recent example with Frosh Is， once we started writing and reading data to and from a database。

 we introduced a third piece of the puzzle， which is generally known as a model and model refers to the database or some kind of storage that you're using to read and or write。

😊，And collectively， these three ideas of model and view and controller are generally referred to as MVC model view controller。

 and it just describes one type of architecture when it comes to implementing a web application or really other types of application whereby when you sit down to design them。

 you don't just implement everything in one massive file。

 which we've kind of been doing throughout much of CS50， but rather you separate concerns。

 you put all of your templates Aka views over here。

 you put all of your model related code over here and then you have a controller thats somehow orchestrating between those two concepts。

 it doesn't change anything we've yet done， but it does slap some industry standard labels on top of them。

 speaking of industry， it turns out it's incredibly common on websites， of course。

 to log into them as like your Gmail account for instance。

 if you use or Office 365 or some other email service or really any website nowadays for which you have a username and password and log in and indeed up until now。

 neither of the applications we wrote the hellello。😡。

World application or F I am had any notion of individual users。 there was no login。

 which means anyone who sits down at the keyboard could type in some input。

 What that means similarly， is that anyone who's at the keyboard can see all of the information therein。

 including the form itself， the list of registrations。

 the confirmation pages and that might not be ideal because if we really are implementing the idea of those paperbased forms back in the day。

 Well， really only that resident advisor or Proctor should have access to the forms once they submitted。

 everyone shouldnt be able to just change their URL to registrants and be able to see something which is to say if we did want to add the ability to log into a website so as to exercise finer grainined access control so that I can see this you can see that we need to somehow add more functionality to these applications much like Google has added to their own Gmail page。

 Unfortunately， the way HttP is designed is that every piece of information that goes between browser and server has to be sent all。

Once for the browser to know about it。 And yet， when the user then clicks on another link， ideally。

 in some cases， the server would like to remember， oh wait a minute。 This is the same user。

 and I already logged them in before。 You don't want to have the user to have to log in every time they click a link or every time they submit a form to prove to you that they are who they claim to be。

 In other words， you'd like to be able to remember that someone has already logged in。

 So for instance， in the real world， if you go into a club， an amusement park or a bar。

 sometimes they put a little bracelet on you or sometimes they stamp your hand。

 And that hand stamp is meant to confirm if you come and go through the same door。

 you we've already authenticated you。 We've already checked who you are so that we don't have to pull out your I and look at it again。

 So in fact， I actually have a little hand stamp here。

 And so if you imagine that here is my hand with no stamp on it being presented to get into some fun amusement park。

 once I've shown them my ticket or my I what they might very well do is if not a bracelet。

 put a stamp on my hand like this here， smilemiy face。

And so long as I show that to the bouncer or the ticket taker again and again。

 they will remember that I have already authenticated myself by showing them my ticket or showing them my Id in the past。

 Now， it turns out that H TTP funny enough， can implement exactly this same idea albeit more technically。

 recall that when using H TtP， you see a message like this in the browser being sent to the server。

 for instance， For instance， when you log into Gmail specifically inside of that virtual envelope goes a post message followed by or some such some s route followed by the version number of HttP and then maybe some reminder as to what host name is being posted to。

 Meanwhile， the server hopefully responds as we saw last week with HttP 200 which is a status code meaning okay But wait a minute。

 if we have already this mechanism where by the browser can talk to the server and the server can talk to the browser could we implement from the server to browser。

 this notion of a hand stampamp。 Well we can。dwelled on these too much。

 but recall that inside of that virtual envelope， such as one pictured here is a HttP header。

 One or more of those things。 And in fact， every time I've pulled up developer tools。

 there's actually been a whole bunch。 This is just a key value pair。

 So maybe if we could somehow implement this notion of a hand stamp as a key value pair。

 we could remember that someone has logged in。 Moreover。

 we can remember who has logged in somehow as well。 And in fact。

 the way that HttP has browsers and servers do that is as follows When you log into Gmail or really any website。

 What that server does in its response message to you is unbeknownst to you really。

 is it stamps your hand。 specifically it includes in the virtual envelope among all of those HtP headers。

 another key value pair。 namely set dash cookie colon and then some value。

 And while you could somewhat foolishly just put the users email address like set cookie colon session equals mail in it Harvard。

generallyer， the value inside of that HtP header is like a big random value。

 a big string of text and or numbers that somehow the server keeps track of and remembers that okay。

 I gave David this big random number。 I gave Julialia this big random number。

 So we don't all get the exact same smileyface handstand。

 But the next time the user from that same browser clicks a link submits a form unbeknownst to you。

 the browser sends another header。 in addition to the usual namely a cookie header。 cookie colon。

 and then the exact same string。 sessionession equals value， for instance。

 and session itself is kind of a term of art， sessionession refers to the concept of maintaining state between the browser and server。

 even though HttP by design is really meant to be state list。 once the browser icon stops spinning。

 you've gotten all the data you're gonna get from the server。

 But so long as the browser knows that once it receives a cookie， send it back to the server。

 send it back to the server。In every subsequent virtual envelope， the server can remember that， oh。

 I've seen that smiling face before。 I've seen that big random number before。 that must be David。

 that must be Ulia。 And so it's a very clever way of just reminding the server who you are。

 And to be clear the cookie itself could be your email address。 Heck。

 you could even use your password just to constantly remind the server。 Here's my username。

 Here's my password。 Here's my username， Here's your password。 But that's generally not a good idea。

 and you should not be doing that nowadays， because it's all too easy。

 potentially for the data to get intercepted。 and certainly don't send username and passwords over the Internet more often than you need to。

 just as a good principle。 So with that said， if we have the ability to stamp the user's hand in this way。

 and to remind the user what's there。 what you're looking at， indeed， our cookies。 And in fact。

 this fast so long already， it's a good thing we brought some snacks for today。

 So these here cookies。 These are what cookies actually are。

 And all of us have probably heard about cookies and the context of the Internet。😊，Sometime。

 whereby cookies get saved on your computer from the servers that you actually visit。 Well。

 what is a cookie。 There's really no academic value to what I'm doing here。

 But what is a cookie in the context of the web， Well。

 it is just typically a big random value that's stored on your computer and it doesn't have to be random。

 it can be， for instance， your username。 It can be your email address。

 Hopefully it's not your password。 But if you've ever checked that box that might remember your email address and auto populated。

 it may very well be the server that's reminding you of that same value。

 The reason that cookies get kind of a bad rap， though。

 is that there's a lot of cookies typically being stored on your browser from servers around the world and a lot of those cookies are used to track you and me。

 Now it stands to reason that if I've logged into a website。 Well， of course。

 the websites going be able to track my behavior on that website because I literally told them who I am。

 But when the world of advertising， for instance， it turns out that even if you're not logged into a website。

 There are enough unique features to your computer and your。😊。

And the way that you use it that servers can typically plant cookies on your computer。

 even without your logging in。 And even though they don't know that I am David， and that is Julialia。

 they do know that I'm the same user again and again and they can effectively build a profile of who you are based on all of your clicking behavior。

 So if you recall last week when I first was demonstrating various features of Hl and the like。

 I was actually deliberately using incognito mode sometimes because I wanted to start with a fresh slate。

 And so among the things that incognito or private browsing mode typically does。

 is it gives you a brand new empty cookie jar。 so to speak。

 it clears the browser's memory just for that window that you've opened privately。

 And it makes sure that you have no cookies by default。

 And you have no other settings by default being sent back and forth to the server effectively ensuring that you're starting from scratch。

 But if you're using the same nonincognito or non-private tab again and again and again。

 you really are accumulating a lot of these cookies。 And in fact， if you open up developer tools。

 you can。😊，Under the storage tab or thereabouts and other browsers。

 all of the key value pairs that servers are storing on your computer。 So with that said。

 let's use cookies though not for evil but for good and to actually use them to remember that a user has logged into a website and to do that we're gonna leverage a feature of flask that is built on top of these cookies known as a session which is again just some form of memory that keeps track of the fact that we have seen some user before。

 In effect， a session is the technical way to describe something like a shopping cart。

 Anytime you've bought something online or added something to your shopping cart。

 you can come back a few minutes， a few hours a few days later。

 and depending on how the website is implemented， it can remember what is in your cart thanks to these cookies。

 Similarlyly， we can remember that you're logged in via these cookies using this here feature。

 So let me go into VS code here and in advance during break I went ahead and created the beginnings of a loginbased application。

 If I type L in my login directory here well see app。

text and a templates directory inside of which as before is just index do html and layout do html。

 But let's go ahead and implement a website that now keep knows if I'm logged in or not。

 albeit simplistically let me go ahead and open up my index template in templates and I'll close my terminal window And in here I'm going to use some ginja syntax that we've seen before。

 if the current user has a name Well， then they're clearly logged in。

 So let's go ahead and say you are logged in as name period。

 and if it's not the case that there's a name value。

 then let's go ahead and say you are not logged in period and I'll going to add an and if down here。

 So at the moment， I'm just assuming that name is a thing。 and it actually exists。

 but I'm going to need to implement now that logic next。

 So let me go into my terminal window again this time opening up my app pie。

 which isn't really doing much yet and start to make a few changes。

In addition to importing flask and render template and request。

 I'm also going to import a feature called session。

 and then down here I'm going to configure flask to use sessions as follows and this is the kind of thing you can copy paste from documentation or these here examples。

 but I'm going to say app dot config quote unquote session permanent equals false capital F for false and Python and app dot config。

😡，Quote unquote， session type equals quote unquote file system in lowercase。

 This essentially enables the ability to store sessions。 Put another way。

 This turns cookies on for this web application。 It ensures that the cookies are not permanent in the sense that what cookies I'm using should disappear when the user quits their browser ultimately。

 But I'm using on the server， the file system， like the files and folders locally to keep track of who is logged in。

 And then lastly， I'm going to say session capital S。 and specify app there too。

 And I'm going to import one other line that I forgot from。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_203.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_204.png)

Fask session， import session capital S。 Again， there's some step there's some hoops to jump through here。

 I too have to check the documentation or my own examples to remember what。 But in short。

 I'm importing flasks support for sessions。 I'm importing this session specific library as well。

 I'm specifying these configuration options。 And I'm now turning on sessions with this final line of code。

 Of course， for this to work。 I actually need another requirement。

 So let me open up requirements do text， which up until now。

 we've not needed because we already put flask in there。

 but I actually now want to use the flask session library as well。 strictly speaking。

 you don't need to do this in CS50 do dev because we've preinstalled it。

 but for a typical realworld application。 We would need to tell the server that we indeed have another library and install it with Pip。

 Allright， So that's mostly copy pastsable boilerplate。 Let's go ahead now and implement a route。

 So app do route， quote unquote slash for my default route to find a function called index as before。

 And let's very simply return。

![](img/c0e4be0df203b599d64dc2c7b3218c55_206.png)

Reendnder template， quote unquote index dot H TM L。 And then that is it for now。

 Let me hide my terminal。 Go back to my other browser tab。

 which still shows the previous application Fsh I ams。

 But so long as I run flask run in this tab here。 and go back to that tab and click reload。

 I should now see this new application。 And indeed， I do。

 it just as you are not logged in because I haven't done anything related to logging in yet。 Well。

 that's okay， How do I want to go about implementing this then instead。 Well。

 let me propose that if we want the user to be able to log in。

 we need a form via which they can tell us who they are。 So let me go back to V S code。



![](img/c0e4be0df203b599d64dc2c7b3218c55_208.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_209.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_210.png)

I'm going go back to my second terminal window here and I'm gonna to seed into my login folder to be in the same place。

 into my templates folder to be in that place。 and I'm going to create one more template called login do hm inside of login hml I'm going carefully type extends quote unquote layout hml close percent sign down here I'm gonna to say block body as always and then end block down here and then in here I'm going to whip up a very simple form。

 So form action equals quote unquotelash login the idea being in a moment I will create a new login form。

 the method I'm going to use for logging in for privacy sake is going to be quote unquotepost then inside of this form I'm going to have a text field where autocomplete is off Also for privacys sake。

 autofocus is on for convenience's sake。 the name of this field is name for the user's name The placeholder they'll see is quote unquote name and the type of this field to be clear as text for simplicity sake。

 I'm not gonna to bother with a password。We'll see that in the next problem set。

 but for now I'm just going to allow the user to log in just by telling us their name and no password。

 so I'm gonna to have a button the type of which is submit and then the label for that button shall be log in。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_212.png)

How now do I actually render this template so that the user sees it when it's time to log in。 Well。

 I think this is fairly straightforward。 If I go back to app do pi。

 I can create another route down here。 app dot route， quote， unquote， slash login。

 Then I can create a function called， for instance， login to keep it simple。

 And then I can simply do render。😊，Template， quote unquote， login。htm。Now。

 I could go manually to slash login to access that page。

 But let's make this template a little more user friendly that we began with。

 Let's actually give the user a link。 A Hf equals， quote unquote， slash log in。

 and then inside of that anchor tag， log in period。 Otherwise， let's proactively do this。 A Hf。

 quote unquote， log out。 and then inside of that anchor tag， log out。



![](img/c0e4be0df203b599d64dc2c7b3218c55_214.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_215.png)

That is backwards。 So let's do it correctly this time here， we're gonna say log out。

 If the user is logged in down here， we're gonna say log in。 if the user is logged out。

 So I think now it's consistent with the English I already had earlier。

 let's go back to the original URL whereby it says you are not logged in。

 but it now gives me a link to log in。 If I hover over that。 super tiny。

 but in the bottom of my screen， I will see that it's going to thelash login row。

 And indeed if I click on that， I find myself at the first Well the 10th of many errors today。

 So let's go back into Vs code， let's open up my terminal window。

 click on the one that's running flask and the view function for login did not return a valid response。

 the function either return none or ended without a return statement。 So user error on my part。

 let's scroll down and sure enough， I did something dumb。

 I need to return the return value of render template。 Allright， let's hide that。 let's go back。

 Let's click reload enter and now we see the login form。 Of course， it doesn't do anything useful。

 If I type in。😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_217.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_218.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_219.png)

and click login， it goes to the login route， but it's saying method not allowed because I haven't done anything yet with post。

 That's fine， too。 Let's go back to my login route and let's do this if the requests method equals equals post the implication being the human clicked the login button after typing in their name。

 then let's do this session， then in square brackets name equals request dot form do get quote unquote name。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_221.png)

And then we will， let's say。Return， redirect quote unquote slash。

 So what's going on here if the user indeed submitted the login form using a request method of post。

 which is implicit because that is the method I'm using in login do HTML thereby allowing me to distinguish between whether the user just visited the form or they submitted the form if I go back to apptop high。

 I am in the case of submitting the form going to store in a special global variable which I imported up here on line1。

😡，A key called name。 And I'm gonna set the value of that K key equal to whatever the human's name actually is。

 Now， as an aside， I'm not bothering with error checking now。

 So it's possible to just click the button and not type in a name， but imagine from Fro I ams。

 we could borrow some of that， if not logic to make sure that the human gave us a valid name。

 But the point here is that this special global variable that I've now imported and enabled by way of these lines of code here is essentially giving me a global variable that's in essence。

 a global dictionary in which I can store any key value pairs。 The first key I'm storing is name。

 the first value I'm storing is the human's actual name。 And what I can now do more interestingly。

 I this when I comes to displaying the default page， which recall is index dot Hml。

 recall that I was checking， is there a name being passed in。 Well， there can be。

 instead of just rendering the template index dot Hl。 Let's pass in。😊。

The user's actual name by using session。 get， quote unquote， name。And here， too。

 I'm using a feature of this session global variable whereby it。

 too like request do orgs and request do form， comes with a get method built in that allows me to get the value of that specific key。

 And as an aside， if there is no such value， it will at least return none， capital n in Python。

 which is similar in spirit to null， but unrelated to memory。

 But it's a special value that indicates， there was no such name。

 But so long as I'm using this logic in indext HTMLml checking if there is a name that's either going to be a valid name or blank or missing。

 In either case， I will display the user's name， I think。 So if I've done everything correct here。



![](img/c0e4be0df203b599d64dc2c7b3218c55_223.png)

Which I haven't。 but I caught myself this time。 I did one last thing on line 20。

 If the user has submitted the form via post and per line 19。

 I've remembered in my session that they're logged in that sort of equivalent to stamping their hand storing their name in the session effectively remembering who they are last thing I'm gonna do is redirect the user back to s Why we think about most any website you loggged into if you try to visit a page and you're not logged in you log in hit enter and you're usually redirected back to like the homeage or the default page how can you do that will slash represents the default homep page So I just need to import one more feature of flash the redirect function。

 So I'm gonna add that to my comma separated list on line1 and that gives me the ability to send if you recall from last week one of those 301 status codes or 300 something that tells the browser that the website has moved to this other。

😡，Location， for instance， from this to this other one。 Allright。

 let me go back now to the browser here。 Let me click back to the main page such that I'm told you are not logged in。

 Let me click on login。 Let me type in my name crossing my fingers， enter。 And now darn it。

 I'm still getting method not allowed。 But this is something we've seen before。

 that's just because I'm trying to use the login route for both get and post。

 So I think I need to add methods equals quote unquote get and quote unquote post just as with thro I am。

 And now if I go back。 And I try to resubmit this form。

 and click continue now you are logged in as David period。

There's still a bug or really a missing feature。 If I click log out。 I go to slash log out。

 which is not found at all， but that's just because that route doesn't exist。 That's fine。

 Let me go back to Vs code here。 Let me create one final route app dot routes。

 quote unquote slash log out。 And then in this route。

 let's define a function called log out to keep it simple。 And in here。

 I just need to clear the session。 I need to like clear off the hand stamp from the user so as to tell them stop sending me this cookie。

 And so we can actually do a function called session dot clear。

 which clears the contents of the session。 And then I can go ahead and return redirect quote unquote slash so that once you log out。

 you're just sent back to the homeage again。 So if I try this again over here，404。

 let me go back to where I was。 let me click log out now， and notice I'm still at slash。

 but I'm no longer logged in。 I can do it again all day long。 typey in David log in。 Click log out。

 I can log in now as youlia。😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_225.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_226.png)

Log in。 Now she is logged in。 and now she's logged out。 And even though I keep saying slash。

 recall that browsers are typically just in the habit of hiding values that don't really need to be there all the time。

 So if you see nothing after the T LD in the URL， it's implied that you're visiting slash the default page。



![](img/c0e4be0df203b599d64dc2c7b3218c55_228.png)

Allright， so with that said， what we've just introduced then is this idea of a session whereby because of how HP works and because of how cookies can be sent back and forth from browsers and servers。

 and because flask is used by so many people， they've implemented all of the functionality for us to keep track of those cookies and reading them and figuring out who is who what's nice about the session global variable is that you can implement one web application And if you want to store something in memory for a specific user。

 you can store it in the session dictionary。 instead of in a global variable。

 instead of in a database。 So if you want to keep track of who is logged in on a per browser basis。

 you use session if by contrast， you were to use a global variable like registrants like we did a little bit ago。

 every user of your website would have access to that memory which you don't want。

 So session is sort of like a per user variable and you don't have to know or care。

How it's implemented， but being in CSs50， you know now that that session abstraction that per user global variable is really implemented under the hood because Flask is opening that virtual envelope。

 looking for the set cookie and the cookie headers back and forth and taken care of all of that to ensure that you can just use session as we intended on a per user basis。

 All right， let's go ahead and implement another application that also implements a very common feature using sessions but this time to implement full-fledged shopping cart。

 For instance， if you want to implement a bookstore online via which people can add books to their shopping cart。

 Well， let's see where to begin In advance， I've created this folder called store and inside of it。

 I've got a few files， apppi requirements text store do db。

 which is new and templates and inside of templates is the usual index do Html and layout Html。

 Let me go ahead and use SQL light to open store Db。

 Let me go ahead and maximize my terminal window and simply do a dot schema。

To see what's inside here seems that there's a single table in store Db called books that has three that has two columns。

 One is an ID which will be a unique identifier aka primary key。

 the other of which is title if I want to select star from books I can see all of them and in this database。

 there's only five sort of5 of my favorite books if you will。

 Allright so now that we know that we have that database。

 can we go about implementing our own version of Amazon， if you will。

 our own shopping cart to buy these books。 let's go ahead and open up requirements text。

 And as before let's also include as a dependency flask session。

 even though it's already installed on the server， but if you use this application anywhere else。

 you'll need to install that to via P。 Now let's go ahead and open up app pi close my terminal and let's add some of those same features up here。

 let's import as well redirect as well as request as well as session let's above that go ahead and import from C50。

 the SQL feature as we've used earlier。 and let's also import from flask。Session。

 the feature called session capital S。 Then down here。

 let's proactively connect to the database with the SQL function specifying SQL light colon slash slash slash store dot DB。

 Let's then configure sessions as before with app dot config， quote unquote。😊。

Session underscore permanent equals false。 Then let's specify app do config。

 quote unquote session type equals quote unquote file system， all lowercase。

 And then lastly to enable session session passing in app。

 essentially wrapping the web application with this session functionality。 Now。

 let's do something simple。 a very simple template that just spits out all of the books。

 So let's define a route for slash that function therein shall be called index as before。

Inside of that function， let's do this， create a variable called books。

 set it equal to Db dot execute， quote unquote， select star from books to keep it simple。

 and then let's return。Reendnder， template， passing in the templatebook。 HTMLt。

 which I'll create momentarily and passing in those books as we've done many times now with a key and a value as a named parameter。

😡，Okay， let me open my terminal。 Let me open up a file in templates called books dot H Tm L so that I can create now this template。

 And this one will be relatively short， but dynamic in that， we're going to do the following。

 Let's extend layout dot H Tl， as we keep doing。Let us then define a block called body as always。

 and the block down here。 And inside of this block， let's do this。

 How about a nice big H1 that says books to list what's in the catalog。

 Then let's do this for each book in the books parameter that was passed into this template and proactively。

 I'll do N4 down here。 Let's go ahead and output How about each of the books title。

 So how might I do this。 Well， let's go ahead and maybe start like we did earlier with a U tag。😡。

Down over here。And inside of， let's do a bunch of lis where inside of the li。

 I'm going to go ahead and do the books dot title to spit out its title。 Allright。

 now I'm going to go back to my terminal window and as before I'm going to do flask run having previously stopped the other instance of flask in my other tab。

 enter And now I'm going to go ahead and open up the application as always。 And when I hit reload。

 we should see no longer our login application。 but store and sure enough， there is a very simple。

 if unusful， book store that just lists all of the titles therein。 Allright。

 well let's make this more interesting now， let's actually enable the user to add things to their cart。

 we can do the user interface in a bunch of different ways。 but let me propose that we do this。

 instead of a U tag， let's do an actual form。 So let's actually do how about this for each book in books。

 let's go ahead and output an actual usable form for every book。

 Even though this is not necessarily the。😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_230.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_231.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_232.png)

Only way to do it。 It's perhaps the simplest to start with For this book。

 let's go ahead and output in H2 tag with its title。 So book dot title。 And then down here。

 let's do a form for this book。 form action equals quote unquote cart。

 which I'll claim is a route we'll implement in a moment。

 The method I want to use for privacys sake is going to be post for this form。 Now。

 I'm going to go ahead and include a button whose type is submit and。

The value of that button is gonna to be add to cart and now I need to actually specify what I want to send to the server so that it knows what book to add to the cart so I can do this。

 for instance， input name equals title of the book。

 the value of which is quote unquote the bookss title as before and the type of this box could be text。

 Now let me go over to the store tab again， let me hit reload and if I haven't messed up I think I should if ugly have for each book an input that shows its title and a button that will allow me to submit that title to the server。

 Now this is silly because I already have the book's title here and it certainly shouldn't be the case that I can change the title of a book to add it to my cart so I don't think I want an input of type text so there's another way I can do this。

 I can actually make those inputs hidden by changing the inputs type from text to hidden Now if I go back to that tab and click reload。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_234.png)

I still have the buttons and underneath the hood， I still have the book's titles such that when I click add to cart。

 the book's title will be sent to the server， but this too is a little sloppy because recall that the database that we're using if I see D in my other tab into the bookstore and do SQL light of store Db and do select star from books recall that I have for each book not only a title but also unique identifier。

 and this is good because even though this database is small， what if two books have the same title。

 that's definitely the case in the real world， but they might have different authors and they definitely have different Is So much better practice than sending a string of text is to use what we learned in our week on SQL use the primary key to uniquely identify these books and so by this I mean let's change our template here to pass in not a hidden title but a hidden ID so that what's actually going to be submitted is the number one。

😡，2 or three on up。 So if now I go back to that other tab and reload， visually nothing has changed。

 but notice if I right click or control click view page source。

 I indeed have a bunch of forms on this page。 But notice this form will submit value 1 to the to the server。

 This form will submit value 2。 this form will submit value 3。

 This is exactly how websites like Amazon and the like work， such that when you click add to cart。

 your browser is sending a unique identifier for that book or whatever it is to the server and the server is then saving that Id in its database or its session or somewhere else to remember what book or item is in your cart。

 So we too can do that。 let me go back to Vs code and let me go into app pi。

 and let's add a bit more logic that's going to allow me to add those numbers to my cart。 Well。

 what is the cart gonna be。 Well， we have to implement a route for this。

 So let's define app route quote unquote cart。 And then down here， let's define。



![](img/c0e4be0df203b599d64dc2c7b3218c55_236.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_237.png)

A function called cart。 And then in here， let's do a couple of things。

 Let's first say if request do method equals equals post。

 the implication of which is the user clicked a button to submit a form。

 then let's go ahead and get the I from that form。 I'm gonna get request form get quote unquote I。

 Now just to keep myself saying， I'm going to call it book underscore I just so I know it's a books I and not some other identifier here in Python。

 As always， I'm going to do some error checking。 if the book I exists。

 then I'm going to add that book I to the shopping cart in my session by appending it to that cart。

Now， what's going on here， I'm assuming at the moment that there's already a shopping cart in my session。

 What is the type of that cart。 Well， because I'm using a pen， which we have used in the past。

 it's a method that allows you to append a value to a list of items turns out I'm assuming at the moment that my shopping cart underneath the hood is implemented as a simple Python list。

 but to do that， I need to make sure it exists。 I don't want this to be some global variable。

 I just need in my route to check that the cart exists for this person。

 So what I'm gonna to do is this。 if the cart key does not exist in this user session。

 Then let's go ahead and create a shopping cart for this user in their session that equals an empty list。

 And again， you can think of a session as a global variable for this specific user and it flask that handles all the cookie stuff to make sure that abstraction works。

 But the very first time someone accesses your。😡，Shopping cart and tries to put something in it。

 It literally won't exist because the session itself is completely empty。

 but I can put a key in there， the value of which is an empty list。

 and then subsequently I can add anything I want to that list just as I'm doing with this append function down here Once now something has been added to the shopping cart。

 let's return the user by redirecting them to their shopping cart Otherwise。

 if the request method is not post and it's get， which is to say the user just visited the cart。

 let's show them the contents of their cart let's create a variable called books set it equal to Db do execute quote unquote select star from books where and here's where we can use more SQL skills。

 the idea of the book is in this list of I using a placeholder and parentheses to make clear in sQL that I want to check if it's in a list of values。

 much like we talked about nested queries in week 7。 But what list of values Do I want to pass。Well。

 that's easy session， quote unquote cart， pass in the list that I've called cart to which I've been appending all of these IDs and once I have those books and recall that Db execute returns a list of dictionaries。

 I can return render template of quote unquote cart。htm passing in those books。😡。

As the value of that named parameter。And so if I now want to actually see what is in that cart。

 we need just one more template。 So let me open my terminal window， let me exit out of SQL light。

 Let me go into my templates folder and create a cart dot Hl template， hide my terminal window。

 extends layout do Html。😡，Close quote and percent sign， then block body as always。

 and down here and block as always And then in here。

 let's do something super simple H1 for cart to make clear this is your shopping cart and not the catalog of books。

 Let's do an ordered list just so we can see the order in which things were inserted。

 And now we'll do four book in books and inside of this Ginja for loop and for let's go ahead and specify a link a list item of that books title。

 And again， you can use different syntax and Ginja。

 you can do book do title or you can do book quote unquote title indexing into it in that way。

 but I'll use slightly simpler syntax as we've been doing for a while。All right。

 if I've now made no mistakes， which is low probability， let's reload the application itself。

 The cart now we now see the same catalog of books。

 Let me proactively go to slash cart in my URL up top and hit enter and you'll see that my cart is empty at the moment。

 But because of all of the logic I've added to my cart route。

 watch what happens if we add these to the cart。 Let's try adding the very first book。

 the hititchhicker's Guide to the galaxy。 click。😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_239.png)

All right， I screwed up here。 I did get redirected to cart。 but but but that method is not allowed。

 We know I'm using post because that is what was in my form。 but I think this is an easy fix。

 If I'm using method equals post here， I need to support that route here。

 So I need to specify the methods I want to support are indeed not just get but also post for my cart route。

 All right， let's go back again。😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_241.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_242.png)

Back to the catalog and click add to cart。😡，ANot only has it been added to the session。

 I've been redirected to slash cart。 And because it's in my session， there is the first book。

 Let me hit back now。 Let's add the last book to the book to the cart mostly harmless。

 click And now I have those two books in my cart。 Now， to be clear。

 these are only stored in the session， they're not yet stored in a database。

 So this isn't like the user has placed an order。 It's more like they have added something indeed to their shopping cart temporarily。

 And in fact， you can kind of see what's been going on all this time as follows。

 If I see back to my store directory。 and let me clear the terminal and type Ls。

 notice this other folder magically appeared called flask session。 And in fact。

 if I look inside a flask session。 you'll see it turns out a couple of files now。

 because I've been using this for some time。 I've created two sessions over time。

 And I essentially have two cookie values stored in this folder that's keeping track of what the user has been doing on my way。

😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_244.png)

In short， these files that are stored temporarily in that folder are the result of having configured the session as follows to use a file systembased session so that Flask is creating these files for you and storing in those files as much information as it needs to remember what is in whose cart。

😡，And it uses cookies ultimately， to main that kind of state。Alright。

 I think we have time for one final set of examples whereby we'll connect all of the dots2 from week 6 and week 7 together and a final implementation of an application。

 Let's do this。 Let me close all these tabs here。 Let me open my terminal window。

 Let me hit control C on flask and go into now our final example called shows。

 And in my shows directory， which I created in advance。 I have similar files。

 but not the same app pi and requirements do text shows do Db， which is our old friend from SQL。

 wherein we have thousands of TV shows from imMDb， as well as my templates folder。

 which as before has index do html and layout do hl as well。 What I'm going to do now。

 though is go ahead and introduce。😊，That much bigger database and make an application that's gonna let a search IMDB。

 albeit with a simpler U I than at IMDB dot com。 So how might I do this， Well。

 let's go ahead ands implement app pi first， Let me open up app pi and hide my terminal。

 And from this list of this from this starting point， Let's do this。 add to it from C 50， import SQL。

 and down here， let's go ahead and create a connection to that there database。 Db equals SQL。

 quote unquote， SQL light colon slashlash slash shows dot DB。😊，Now。

 I'm going to go ahead and create a route app dot route。

 quote unquote slash for my default define an index function。

 And this function's purpose in life quite simply is to return， render template of quote unquote。

 index dot H Tml。 Now， what's that route actually going to do。 Well。

 that index dot Hml is going to be very simply a search form。 So let's implement that。

 Let me open my terminal and go into templates and then open up index dot Hml。

 which has the starting point of our body as before。😊，And in here。

 let's do this form action equals quote unquote slash search。

 which will be the next route that I implement。 The method I'll use now is get just to make clear what's going back and forth between the browser and server。

 Let's create as we have in the past and input with autocomplete equaling off autofocus on for this field the name of this field will be Q。

 just like our Google example from a last time the placeholder for which will be query for Q。

 and the type of this just to make it is slightly better is search， which is almost the same as text。

 but it usually gives you a little x you can click to clear the search box。

 Then I'm gonna have a button， the type of which is submit。

 and the label on that button will be search。 and that's it for that form。

 Now this isn't fully functional yet。 but let's test it out。

 Let's go back to my terminal window back to my shows' folder run flask run in this one after making sure that it's not running in my other tab。

 And in my other tab too， I'm going to go into my shows folder。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_246.png)

But only in one of these am I gonna run flask run。 Allright， I'm going go back now to my other tab。

 which still shows my shopping cart。 I'm gonna shorten the URL to just slash and hit enter。

 and now we see my showss application。 Of course if I search for something like the office enter nothing actually happens why because even though the browser brought me to slash search question mark Q equals office。

 there's no search route yet。 So let's go back to VS code。 and in VS code。

 let's go back to app pi and implement that route Now in this route。

 I'm going go ahead and in app pi， I'm gonna create app dot route quote unquote slash search。

 So creating the route is super easy to a function called search or whatever And then now let's go ahead and search for titles that match what the user typed in。

 So shows equals Db dot execute quote unquote select star from shows where the title equals question mark as my placeholder let's now pass in request orgs get。

😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_248.png)

quote Q， which is the query that the human typed in to the form。 I could create a variable。

 but it's so short enough line of code。 It fits on the screen。 I'm going to leave it as that。

 Then I'm going to return render template， quote unquote。Search dot HTML comma。

 and let's pass these shows into this template， shows equals shows。

 Now I don't have a search do HTML template yet， so let's go and create that。😡，In search do H Tml。

 I just want to print out those titles。 So let me go into my terminal window。

 specifically the one not running flask。 Let me see the into templates。

 And then let me go ahead and run code of search dot H Tml hide my terminal and really quickly do an extends quote unquote layout do H Tml Then let me do a block body。

 Then let me do an end block， as always。 And in here。

 let's just do a simple unordered list of these titles of shows。 for。😊。

Show in shows where shows is the variable I passed in is my name parameter。

 And let's end that for loop。 Then inside of here， a link。

 a list item passing in show dot title as my value to interpolate。 Allright。

 let's see what happens now。 Let me go back to my other tab。 back to the form itself。

 Let's search for office search。😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_250.png)

Ha nothing。 So no actual results on the page。 In fact。

 if I view page source by right clicking or control clicking， notice that I've got a U。

 but no list items。 Allright， well， technically， the show is not called office， but the office。

 So let me do that。 the office search oh we actually have a bunch of versions of the office。

 which we saw not only the American one， but the British one and others as well。

 So it seems that my equal sign in my SQL query is behaving exactly as we learned in week 7。

 whereby I'm literally searching for a specific title that I'm plugging in for that placeholder。

 So I think we can improve this slightly， recall that you can make things a little more flexible by not using equals。

 but we could actually use like Unfortunately， we need to when using like use those wild card characters like a percent sign to the left and or right of the thing that we want to match on。

 So the easiest way to do this might actually be this。

 Let me create a new variable here called query and set it equal to short request。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_252.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_253.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_254.png)

orgs do get quote unquote Q。 However， let me actually prepen to that a percent sign to be my wild card。

 and I'm going to use plus， which we is the concatenation operator and Python。Alternativelyly。

 we could use an F string or some other technique， but to be pedantic。

 I'm gonna literally add to this string， Another percent sign at the end as well as the beginning there。

 So if I type in office。 This will just construct a Python string or stir。

 that's percent O F I C percent。 These percents have nothing to do with ginjas templates。

 They have everything to do with SQL per week 7， which are wild card characters。 Then over here。

 I can plug in not the raw value that the human typed in。

 but I can pass in that query so that it is placed where the question mark is。

 and it is properly escaped to avoid any SQL injection attacks。

 So now let's go back to my other tab and hit back。 instead of searching for the office。

 let's search for office。 click Now I get back not only all of those。😊。



![](img/c0e4be0df203b599d64dc2c7b3218c55_256.png)

Oices， but also every TV show that has ever had the word OFfi ICE in it or a substring thereof。

 So maybe overkill， maybe not what I want， but it did， in fact。

 make the search a little more versatile。 But it turns out we can improve upon even this user interface。

 But notice up until now， what we've really been doing now is combining Python and SQL and HTMLml and well。

 no Css and everything's quite ugly for it。 But we've combined almost everything。

 What if we introduce to the mix a little bit of jascript code as well。

 whereby I could move away from this model where every time I want the browser to talk to the server。

 I don't necessarily need to send data from browser to server and then reload the whole page。

 perhaps at a new URL。 much like our autocomplete example at the end of week 8。

 recall that we could populate the body of the web page。

 the Dom or docu and object model using jascript as well。 So in fact。

 even though we haven't done this yet。 I bet I could。



![](img/c0e4be0df203b599d64dc2c7b3218c55_258.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_259.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_260.png)

r a little bit of jascript code that talks to the server and says， give me more results。

 Give me more results and just displays them instantly in the existing web page without having to generate everything server side。

 In other words， you can actually use Javascript to generate some code client side as well。

 So let's see how this might look。I'm going to go ahead now and implement in this next example。

 the following。So let me propose to tweak our implementation of index do Htl such that it still has a form。

 but it additionally has some javascript code that goes and fetches from the server any book titles that match what the human has typed in rather than have any submit button at all that sends the whole form to the server and lets the server generate all of the Hl together。

 let's instead do a little more client side。 So I'm going to go into index do Html here。

 and inside of this template。 I'm going change the way this form here is implemented。

 and I'm gonna to simplify it as follows。 I'm going get rid of all of this。

 this traditional form and I'm just gonna give myself inside of the block body and input type for which autocomplete as before is off which is autofocused as before。

 whose placeholder is still quote unquote query whose type is actually search What I'm not gonna bother doing though is giving this thing a name because I don't want1 to submit this form to the server per se。

 I just need a form。😡，That I can use jascript to grab the value from What I'm next gonna to do is create weirdly an empty unordered list with nothing in it。

 But I'm gonna fill it dynamically with jascript ultimately。 In fact。

 here comes a script tag as we saw at the end of last week， whereby inside of this script tag。

 I can write some actual jascript code。 And this is gonna look a little cryptic at first。

 but I'll walk us through it as follows。 First， let me create a variable called input in jascript and set it equal to document do query selector quote unquote input。

 This code will grab from the web pagess dom or document object model。

 That is the tree that's been built up in the computer's memory。 The tag of type input。

 So this will give me javascript access to this here， Hl tag。 Now。

 I'm going listen to that input for any keystrokes。 And I'm gonna say input dot add event listener。😊。

And I'm going listen for the input event， which just means I've inputted a keystroke。

 So I'm not caring about key down or key up。 I'm just saying when something's been inputted。

 go ahead and call this function。 So I'm going to use a slightly new feature today that's called async。

 which means what's about to happen is going to be asynchronous for reasons we'll soon see inside of this function。

 I'm going now do the following。 I'm going create another variable called response and set it equal to the result of waiting for a function in javascript called fetch that will know how to request via H TtP。

 a specific route specifically slash search question mark Q equals and then some value that I'm going to append。

 And what I'm going to append is the value of that input box。 In other words。

 this line of code is going to make an H TtP request from jascript to the server requestinglash search question mark Q equals office or whatever I've typed in。

 But I'm therefore using code to。Simulate and induce an actual HTTP request without the human actually clicking submitit。

😡，After that， I'm going to say let shows equals a await response text。

 which just means wait for a moment until I get back the text of this HttP response in jascript and then I'm going to do document query selector quote unquote UL I'm going to fix my capitalization and I'm going to change the inner HTML of that U element as we did once last week to be equal to whatever the text in that variable is In other words。

 these lines of code do the following This line of code listens for human input in that text box this line 13 makes an HtP request from JavaScript to the server asking for slash search question mark Q equals something where the something is whatever the human typed in。

😡，Line 14 waits for the response from the server。 Line 15 uses the response and plugs it into the inner HTML of the UL element。

 effectively putting a whole bunch of L tags therein。 Unfortunately。

 search as a route does not quite do what we need just yet。

 So I'm actually going to go back into apptop pi here。😡。

And I'm going to modify the behavior of app pi， such that it behaves as what we generally call an API。

 an application programming interface， which is a way of standardizing how you provide input to a service and get output therefrom The API here is going to be super simple。

 All I'm going do now is this。 I'm going to go ahead and search for， as before。

Some shows in the database as I've done here， and what I'm then gonna do is actually render the same template。

 search do html。 But now that I've confirmed that that part itself doesn't need to change。

 I am gonna change the template in search do Html And of sending a proper U tag， which I don't need。

 I'm just gonna send a whole bunch of L I elements instead a snippet of Hml， if you will。

 Now I'm definitely going cross my fingers this time。

 I'm going to go back to shows here and click back I'm gonna reload the form and that still works。

 but notice I indeed got rid of the button。 I didn't bother using a submit button。

 Why because when I type in O F F I C， what I want to have happen underneath the hood is autocomple。

 I want to get back every result that says office。 Now what just happened。

 let me actually go into the developer tools of Chrome。

 let me go into the network tab and let me actually start over。 Let me click。



![](img/c0e4be0df203b599d64dc2c7b3218c55_262.png)

Reload button here。 Let me clear my log here and notice last time I specifically clicked on doc because I only want to get the tople document requests today。

 I'm gonna click all so I can see even these jascriptbased HP calls and very simply I'm going type in oh it indeed takes a moment but notice in the logs here of my network tab I can see the request that was sent from jascript to the server。

 if I click on that you can see in this query here and it's a big one。

 so we're seeing a little spin under the response tab。

 I don't have a fully formed web page I have a whole bunch of li tags and the titles of those shows in there hundreds of them if not thousands of them。

 which is why it was a bit slow whereby the server generated not a fullfledged web page but just a snippet of Hl instead And so this is an example of indeed what's really an API albeit a naive one that's just returning a minimal amount of HTMLl that you need to populate your own onor。



![](img/c0e4be0df203b599d64dc2c7b3218c55_264.png)

ListBut generally speaking， this isn't really the best way to do this。 really， when it comes to APIs。

 you should be not sending back snippets of HTML， but really the raw data。 And so， in fact。

 very common in the world of APIs as to use something called Json Javascript object notation。

 bit of a mouthful， but what it means is that instead of sending back all of that HTML。

 what you should probably send back is really the equivalent of a Python dictionary。

 Javascript doesn't have dictionaries per se。 Javascript has what the world calls objects but for our purposes here。

 they are the same。 And in fact， what you see on the slide here is a snippet of jascript object notation that wonderfully happens to be the same format that we use in Python for dictionaries kind of a coincidence。

 but probably deliberate， But finally， things are looking the same。 And in fact。

 if I select all of the columns from my shows table in that database。

 I'll get back not just the titles， but the I of the shows the year in which they started as well as the number of episodes。

😊。

![](img/c0e4be0df203b599d64dc2c7b3218c55_266.png)

So in VS code， I'm going first go up to the very top and import one last feature from flask。

 namely a function called Jsonify， which as the name kind of suggests it's going to turn into Json anything you pass into it。

 So for instance， if I pass to it a list I'm gonna get back a JsonN version at that list。

 if I pass in a list of dictionaries， I'm going get back a JsonN version of a list of dictionaries In short。

 it converts whatever is in Python's memory to the corresponding jascript object notation。

 So let me scroll down now to my search route and let's make a change as follows。

 let's go into the last line and instead of rendering a whole template of HTML。

 let's actually return the return value of Jsonify passing in all of those shows。

 though for good measure， let's actually fix a couple of other things as well if for instance。

 the user did not actually type something in we probably don't want to search blindly for some value we know is empty So let's actually tweak even this part as follows I'm going go。

Into my search route further I'm going to define query whoops query equals request do orgs do get quote unquote Q。

 but then I'm gonna to ask a question。 If there is， in fact， a value for that query。

 then let's go ahead and query the database for thats query but prepen to it a percent sign first plus the query itself plus a percent sign after closed parenthesis else if there is no query that is they didn't type in anything at all。

 then let's go ahead and specify that the showss list is really empty。

 There's no result so that at least when it comes time to Jsonify that variable where jasonifying either an actual result set of results or nothing at all。

 but consciously so and just to speed things up to。

 instead of selecting thousands of shows that might contain the letter O。

 let's limit this to like the top 50 just to speed things up， even though in the real world。

 you probably want all of them。 All right that。Let's now go back into our index do Htl。

 which previously was expecting back a snippet of HTMLtl， namely all of those Li tags。

 But let's change it now to actually expect a proper Json response。 In fact。

 to do so what I'm gonna do is a couple of things。1。

 I'm gonna tell my jascript code on line 14 is tell jascript to treat that response。

 Indeed as Json and not text because what I don't want is a big string。

 what I really want in the browser's memory as a proper array of objects。

 that is to say a proper list of dictionaries in the browser's memory。 But after that。

 I don't want to just blindly plug that code into the inner HTMLtl of the U。

 Rather I want to build up my Hml myself。 So I'm going do this as follows。

 I'm going create with let another jascript variable called Hl and set it equal to quote unquote I could use double quotes。

 but I'm using single quotes for parity with jascript conventions。

 but it's just an empty string at this point。 Then I'm going say in a four loop。😊，Javascript 4。

 let's show of shows。 And this is gonna to be my way of iterating now over all of those shows。

 The of preposition is a little weird in ja。 But this allows me to iterate over each of the objects in that array。

 So let's go ahead and do this。 Let me go ahead and append to that HTMLml string with plus equals or concatenate a li tag of my own making。

 followed by that shows title followed by a close li tag of my own making。

 And then outside of that for loop。 Let's do document do query selector。😊。

Quote unquote U to get access to that same empty U element that we do still have and change its inner HTML not to be what came back from the server。

 but my own dynamically generated HTML instead。 Now as an aside。

 I should note that it's possible that this code might be a little buggy because if the show's title contains any special characters like the less than sign or certain other characters that have special meaning in HTML things might very well break。

 and I should probably replace any such characters with their corresponding HTML entities For now I'm gonna wave my hand at that just to keep the code relatively simple。

 but know that we might need to do that kind of escaping of the strings we're pasting in。

 let me now go back to my browser here。 let me reload the page。

 So I get the latest version of the code and let me go ahead and type something like O for office。

 and there we have it。 and unordered list generated not by the server， but by me client side。

 such that now I can search for O or office or anything else。 and all of that is happening。



![](img/c0e4be0df203b599d64dc2c7b3218c55_268.png)

![](img/c0e4be0df203b599d64dc2c7b3218c55_269.png)

Now by generating the list items for that UL within the browser itself and in fact。

 if I reload here and open up my developer tools again via In and go to the network tab and search for oh。

 I can click on that row and under the response tab I can see that I'm not getting back any HTML per se I'm getting back Json albeit pretty printed here and in fact that then reveals to me that indeed I'm getting back JsonN and I'm plugging it in to the browser accordingly So all that said it seems that now we have the ability using HTML and CSs and jascript with a bit of Python with a bit of SQL。

 can we build fullfledged web applications that increasingly are being used not just on our desktops but in laptops but also on our phones as well In fact using all of these languages can you build backend and a frontend that communicate with each other to build things like your own freshman intramural website your own problem set 9 or we hope your own final project。

😡。

![](img/c0e4be0df203b599d64dc2c7b3218c55_271.png)

That's it for CS50， we will see you back in Sanders Theater one more time。😡。


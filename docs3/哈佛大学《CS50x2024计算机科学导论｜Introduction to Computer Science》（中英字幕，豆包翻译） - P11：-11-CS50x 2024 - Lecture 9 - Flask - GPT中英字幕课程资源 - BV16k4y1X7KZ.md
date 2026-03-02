# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P11：-11-CS50x 2024 - Lecture 9 - Flask - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/9e2f9fda28bc5aece4246768d8d754a6_0.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_1.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_2.png)

All right， this is C S 50， and this is already week 9。

 and this means this is the week where we synthesize the past several weeks from Python to SQL to Hl to CSS to javascript。

 each of those languages that we've rather looked at in isolation now would rather come together toward an end of just making more modern applications be them webbased or be they mobilebased as well。

 So up until now we've been using to serve all of the web stuff that you've done this program called HttP server。

 Now this isn't a CS50 thing。 It's just a standard program that we've installed into code spaces So it's a Linux program that just runs your own web server and it allows you to run it on nonstandard ports。

 for instance， you've been using it on port 8080 only because codespaces is using 80 and 443 recall which were the default。

 But up until now this program's purpose in life was just to serve static content。

 So like web pages written in Hl， maybe some cS， maybe some jascript that you wrote in advance that just never really changes。

Until such time as you log back into the server， save the file after making some edits and then someone reloads their page。

 But， of course， the web that we all use today be it Gmail or any website is so much more interactive when you search for something on Google。

 There's no Google engineer that in advance has written up an HMl page containing a list of 10 cats or 10 dogs or 10 birds just waiting for someone to search for that particular keyword。

 Rather， there's some database involved， the Hls being dynamically generated and it's all indeed very dynamic。

 So whereas last week we focused on websites this week well focus really on web applications and really the key difference is's just that applications。

 take input and produce output whereas websites are really generally thought of as static。

 but it's a blurry line。 It's not necessarily a technical distinction。

 But today things start to get much more interactive。

 So we're not gonna be able to use HtTP server alone。

 We're gonna need something a little smarter that knows how to take input from users via the URL。 So。

 in fact， let's look at some sample URL。That we looked at last week just to remind ourselves of some of the jargon and really the syntax。

 So here's a standard URL and slash recall is just the default page on the server。

 and usually the file is called index html by convention。

 But depending on the operating system or web server you're using it could be a different file。

 but index hml is probably the most common default。

 So you could explicitly state the file name on most web servers like file htl index html。

 whatever it is。 you can have folders or directories on a web server。

 And this would imply that your index htl file is in a folder called folder in this case。

 or you can have a folderlash file or even folder folder folderlash file and so forth。

 So this is a very direct mapping from the URL to the file system。

 so to speak like the hard drive on the server。 But today we're gonna do like most computer scientists tend to do is more of an abstraction of this like this is how URLs look But it turns out once you control the web。

With code， you don't need things to line up with actual file names and files。

 You can really put your content wherever you want。 And so in general。

 we're gonna focus today on just thinking of everything after the domain name as a path generally speaking and a synonym for this in the context of the Web would also just be a route。

 So a route is just some number of letters， maybe some maybe a file extension that refers to some part of your application。

 But more interesting， and this is what makes things an application and not just a static website。

 recall that this is how websites can take input in the form of URL。

 a question mark key equals value pair or if you want two or maybe3 or4。

 you separate them with ampers。 But like that's kind of it。

 like the web today is going work just like it did last week。

 but we're gonna start leveraging these primitives in a much more powerful， more interactive way。

 So here recall is what might be inside of the virtual envelope。

 when you search for something on Google co It's going to request of the Web serverlash。

Whi is the name by convention of Google's search application because they've got a lot of businesses running on their servers。

 And if you have question mark Q equals cats。 this is essentially the message。

 the HP message that would have been in last week's virtual envelope when I searched for cats。

 hopefully you get back a response from the server containing those actual cats。 But again。

 there's probably a lot more logic going on with a database and somehow generating that Hl that Google's doing for us。

 So we today are going to introduce really what's called a framework or technically a micro framework。

 which means it's relatively small versus alternatives that are out there。 and it's called flask。

 So flask is really a thirdparty library， and it's popular in the Python world。

 that's just gonna to make it easier to implement web applications using Python。

 There are alternatives， a very popular one is called django。

 which some of you might have heard of before。 And there's dozens of others in decreasing popularity。

 dares say， but flask is among the most popular micro frameworks。

 which means you can really just solve a few problems pretty simple。

Without feeling like you're learning some third party library as much as you are learning concept that transcend one particular implementation。

 So we're gonna introduce you to a program framework called flask。

 And that's going to allow us ultimately to start web applications not by running HtTP server today。

 but literally running flask space run。 So this framework literally gives you a command on your Mac。

 your PC， your code space once it's installed， that allows you to start a web server by running flask run instead of HtP server。

 So again， last week， it was all about static websites this week。

 it's all about dynamic websites instead。 And by framework。

 we really generally mean not just using some thirdpart code but thirdpart conventions that just some human or humans decided is the way you will build your application。

 usually this is just based on like lessons learned after making application after application。

 humans around the Internet realized you know what we should probably standardize the names of our files。

 the names of our folders and how things are laid out。

 And so even though this is not the only way to do things。



![](img/9e2f9fda28bc5aece4246768d8d754a6_4.png)

The way that flask prescribes that we programmers do things is this We'll starting today always have a Python program called app dot pi by convention like in our folder。

 and we're gonna have a folder called templates inside of which is any of the actual HTMLl。

 maybe CsS， maybe jascript that we write but you can actually put some of that content elsewhere and in fact you'll see there's gonna be generally two other files or folders you'll see we create or we use today。

 one is called requirements do txt which is literally just a simple text file wherein you specify one per line what thirdparty libraries you want to use this file just makes it easy to install those libraries with a command and then lastly a static folder and it's in this folder that you put images or do css files or js files like literally files that are meant to be static that you might change them once in a while。

 but they're not changing every day and so you just want to isolate them to a particular folder。

 Why is it this way like a bunch of humans decided。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_6.png)

This feels like a clean solution， but reasonable people will disagree and different frameworks lay things out differently。

 So when using a framework for the first time， you sort of take a class or read a book or read the documentation and it will essentially guide you to how you should lay out your application。

 So let's go ahead and do exactly that and make an application that quite simply and by design underwhelmly implement hello world。

 but rather than do this statically let me do it in a way that starts to use this framework so that in the next version of it。

 we can actually take user input and have it say not hello world。

 but maybe hello David or hello Ulia or anyone else。 All right。

 so let me go over here to VS code and let me go ahead and initially。

 let me start with the familiar and let me go ahead and start by simply creating the Hml page that I really want to show to my visitors when they visit my application。

 So I'm gonna go ahead and somewhat incorrectly initially。

 but just to make a point I'm gonna go ahead and do code index Hml。To open up a new tab。

 I'll hide my terminal window just to give myself some more room。 and then really fast。

 I'm gonna type out some boilerplate Hl。 So doc type Hml， just like last week。

 open bracket Hl Lng equals E just to tell the VS code that I'm to tell the web that I'm largely using English here in the head of my page I'm gonna have of course the title of the page and I'll keep it simple and just say something like hello but just so that this website actually renders nicely on mobile devices。

 I'm going use one of those meta tagags we talked briefly about last week whereby if I say meta name equals view port and viewport refers to just the big rectangular region of your browser the content of this meta tagag is going to be initial scale equals one and with equals device with I always have to copy paste this or look it up myself。

 but this line here essentially tells the browser that no matter how wide the device is。

 whether it's。aptop or desktop or maybe a vertical cell phone or tablet size the viewport to that device。

 Otherwise， your website might look super small on mobile devices。

 if you don't use this tag to tell the browser， take into account the actual device with rather than shrinking the 12 point font to something that's hard for folks to read。

 So for now， I'm just gonna generally copy， paste that or type it out from my print out here。

 All right， beyond that， we need the body of the page。 we'll keep that simple。

 So body and then in here， hello comma world。 So that's it for my website thus far。

 It's static nothing about this is gonna incorporate my name or anyone else's。

 So I could technically use H TTP server to serve up this web page， open it in a browser。

 And I would see the actual content。 But let's instead create a bit of work for us and sort of over engineerer this problem。

 but to set the stage for actually taking in dynamic input like a user's name。

 So let me go ahead and do this。 I'm gonna go ahead and open my terminal window again。

I'm going to close the index dot Htl file。 I'm going make a new directory called template。

 which again was the default folder name I mentioned that this framework expects。

 and I'm going to move index dot Htl into that templates folder using Mv Linux command。

 If you're more comfy， you can open up the file the file Exper at right， You'll see in advance。

 I downloaded a directory I'll occasionally borrow content from today called source 9。

 But there is my templates folder。 And you could click in the GuI in order to do what I just did at the command line。

 All right， and after this， let's go ahead and create one other file app dot pi。 and in app dot pi。

 let me go ahead now and do this。 I'm going to import some some functions that come with this framework called flask。

 So I'm going say from flask in lowercase import flask capital F and also a function called render template and an object called request。

 Now how do you know to do this like you literally read the do。Or you listen to someone like me。

 tell you to begin your program this way in the flask framework comes three pieces of functionality that are just useful to incorporate into my own program as we're about to see。

 Here's the line of code via which I can tell this framework to treat my file app do pi as indeed a web application。

 I create a variable， typically called app。 I set that equal to the return value of calling this flask function and pass in it somewhat weirdly。

 the name of this file。 So this is the only weird thing for now。

 in that we haven't used this much if at all， underscore， underscore name。

 underscore underscore is a special variable in Python that literally refers to the current file name。

 no matter what file name you gave it。 So it's a nice way of referring to yourself without manually typing the file name。

 which might change down the line。 And then lastly， I'm gonna do this。

 And this is one other piece of new syntax for now。 I'm going use an at sign and say app。😊，Dot route。

 And then in quote as an argument to this route function。

 I'm going specify the route for which I'm implementing some code slash being the default by convention。

 I'm going to define immediately below that a function that I can technically call anything I want。

 but I'm going to get in the habit of using reasonable default。

 So I'm going to call this function index by default， but that's not a hard requirement。

 And then inside of this function， I'm simply going to return this return。😡，Hello comma world。

 quote unquote， and that's it。 This， I now claim is a beginning of an actual web application。

 It looks a little magical or cryptic as to what's going on。 but per the jargon I introduced earlier。

 this function here， app dot route is defining a route for this application that implies that whenever a human visits slash on this application。

 What should happen is this function index should get called。

 and that functions purpose in life at the moment is just to return。 quote unquote， hellello world。

 and that's it。😊，So let me go ahead and do this。 Let me open my terminal and just to keep everything clean because we're gonna have a bunch of applications today in the works。

 I'm going create one other folder called hello and I'm going to move app pi and templates into that hello folder。

 So if I now type Ls in my own personal account。 I've got that folder hello and also source 9 which I brought with me today。

 So if I now Cd into hello and type Ls again， I'll see the two things we just create it together app pi and the templates folder。

 And if I go one step further in Ls templates itself， I should see， of course， indexed Hm。 Allright。

 so a lot of steps to go through just to get started。

 but you'll see that this is fairly boiler played eventually， I'm not going run HttP server。

 but I am going run flask run， which will turn this apptop pi into a working web application。

 the output after I hit enter is going look a little more cryptic。

 it's gonna warn me this is a development server like you should not use that same command in the real world。

 you should actually configure flask a little differently if you're gonna use it。In the real world。

 But it does show me the random URL that Github created for me。

 And I'm gonna go ahead and open this URL。 It's gonna open a a new tab。 and voila。

 like that is my web application。 completelyte underwhelming。

 but you'll notice that even though Chrome is hiding this。

 this is the equivalent of my having visited at the end of this URL simply a slash。 All right。

 if I zoom out here， though。 and maybe right click or control click。

 and I choose view page source recall this is available in most every browser。

 you'll see that this isn't actually HTMLml。 because at the moment。

 I'm literally just returning quote unquote hello world。 So yes， it's text。

 it's being rendered as a web page， but it's not technically a web page that has valid Hml。

 So what I'm gonna do here is this。 I'm going go back into Vs code。

 I'm gonna open a second terminal by clicking the plus icon toward the bottom right of my screen。

 just I can keep the server running。 but actually let me go ahead and do this。

 Let me kill this terminal。 Let me actually。😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_8.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_9.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_10.png)

Oops， I held the wrong one。 Let me instead go into my hello directory again。 Let me open up app pie。

 And this time， instead of saying hello world， let me do this。

 I want to return the contents of index do Hml， which is that whole file I created。

 but I can't just specify its file name， but I can do this。

 I can call a function called render template， which comes with flask。

 and its purpose in life is to go get that file from a folder called templates。

 open it up and then send all of those bytes。 All of those characters to the user's actual browser。

 So let me go ahead and do this。 Let me open my terminal again。

 let me do flask run inside of this same folder。 Hello， I'm now gonna go back to my tab here。

 click reload。 and nothing appears to have changed。

 But if I right click and choose view source this time after reloading now you'll see all of the Hl that I composed。

 Allright， so this has taking way more steps to do。😊。



![](img/9e2f9fda28bc5aece4246768d8d754a6_12.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_13.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_14.png)

We achieved by just running HtTP server last week。 But here's where now things can get a little interesting。

 whereby now that we have this framework laid out， we can actually introduce other features of the framework to make things more dynamic。

 So for instance， what I'm going do is this。 I'm going now introduce a feature of that variable that I also imported called request。

 which refers to any HttP request。 And it turns out there's a property inside of there called Args。

 which is actually going be a dictionary of all of the key value pairs that the human might have provided via the URL。

 So I don't have to figure out how do I find the thing after the question mark。

 I don't have to worry about parsing the ampersands flask does all of that for me and just hands me anything after the URL in a Python dictionary instead。

 So let me do this。 Let me go back to VS code here。Let me go ahead and hide the terminal。

 But in apptop pi， let me go ahead and make a relatively simple change。 Let me go ahead and do this。

 Let me go ahead and open up in my hello folder。 Let me open up index Hml。

 And let me go ahead and get rid of world and just put a placeholder here， using curly brackets。

 two of them on the left and right， I'm gonna go ahead and plug in a variable like name。

 So here's now where I'm treating index H， not as like literally an Hl page anymore。

 but more as a template in the literal sense。 So a template is kind of like a blueprint whereby you can construct most of what you want the human to see。

 but then leave little placeholders in a blueprint where you can fill in certain blanks。

 The double curly quotes here is actually a feature of technically another language。

 It not a programming language called Ginja。 but Ginja is simply a language that a bunch of other humans came up with that standardizes what syntax you can use for。



![](img/9e2f9fda28bc5aece4246768d8d754a6_16.png)

Placeholders and some other features as well。 So this is gonna happen more and more as you progress more in programming and C like it's not gonna to be as simple as oh。

 I'm implementing something in Python or oh， I'm implementing something in C。

 It's generally going be oh， I'm implementing something with this full stack of software including Hml Cs Python。

 some SQL， some ginja and so forth。 So into your vocabulary is now going generally come a list of technologies that you're using when solving some problem。

 no longer individual languages。 So by this， I just mean this the flask framework took a look around the Internet and saw。

 okay the humans the Ginja group came up with a nice simple syntax for putting placeholders in。

 let's support that syntax in。 So it sort of one framework collaborating with another。

 So if I go back to app pi now， how do I actually pass from my application to that template。

 whatever the human has typed in。 Well， it turns out I can go ahead and do this。

 let me go ahead and in my index function， which again， is what's going to get。

Anytime someone visits that slash route。 I'm going go ahead and create a variable called name。

 I'm going set it equal to request do orgs。 And then I'm going to go ahead and say how about unquote name。

 I claimed a moment ago， that as is a dictionary that just comes automatically with flask。

 And whenever a human makes a request to this server。 and it puts in that dictionary。

 All of the key value pairs from the URL。 And the last thing I'm going to do here is this。

 I'm gonna actually say， and actually just let me make this more explicit。

 let me call this placeholder， literally placeholder。

 And what I'm gonna to do now is in render template。

 I'm gonna to take advantage of one other feature that comes with this function。

 It can take one or more arguments。 And if you pass in more。

 you can specify variables that you want the function to have access to。

 So I can literally do something like this， placeholder equals name。😊。

So recall that Python supports named parameters， which just means that you can pass in multiple arguments to a function。

 but you can specify them by name。 So I am calling one of these arguments placeholder。

 and I'm setting the value of that argument equal to name。

 which itself is a variable that I defined just a moment ago。 So now what's gonna happen。 Well。

 let me actually go back to my V S code。 I'm gonna go ahead and run flask， as I did before。

 the URL is not gonna change in this case。 I'm going go back to my other tab。

 I'm going go ahead now and change the URL manually。

 Let me zoom in here to be slash question mark name equals David。 I'm not gonna hit enter yet。

 Let me zoom out。 But when I do zoom out here。😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_18.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_19.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_20.png)

I think we should see now hello， comma David， so here we go， enter。And voila。

 we see hello comma David， but more interestingly， if I view source here by right clicking or control clicking on the page or opening developer tools and so forth and go to view page source。

 it appears that what the server sent to my browser is literally a web page that says hello comma David Like there is no more placeholder。

 There is no more curly braces， literally the content that came from the server is that string。

 And so this is the distinction now between being a static application versus dynamic。

 what I wrote statically was literally this index Hl file。

 But what got served dynamically is that file plus the substitution or interpolation of that placeholder variable。

😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_22.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_23.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_24.png)

So we have the beginnings it would seem of a web application。 And think back to Google。

 Google is essentially implemented the same way。 slash search question mark Q equals cats。

 they're doing more with the key value pair than just spinning it back out。

 but we have the beginnings now of a dynamic application。

 Any questions on any of this code or this framework thus far。😡，Any questions thus far。No， all right。

 Well， let's see what happens if I don't cooperate like a human。

 Let me actually go ahead and get rid of that parameter， hit enter again。

 And I actually now got an HtTP 400 error。 So this actually seems bad。 And it's a little subtle。

 But if I zoom into the tab here。 It indeed says 400。

 That's one of the H TP status codes that you generally shouldn't see unless something goes wrong。

200 meant okay，40，4 min file， I found 400 means that something went wrong。

 Like I guess I didn't pass in a name as I was supposed to。

 But that's only because I was sort of blindly expecting this placeholder to exist。

 So let me be a little smarter and code a little more defensively now as follows。 Let me say this。

 How about if there is a name parameter in the requests arguments。



![](img/9e2f9fda28bc5aece4246768d8d754a6_26.png)

Then go ahead and create a variable called name。 set it equal to request dot orgs。

 quote unquote name。 So treat it as a dictionary with that key。 else， if there is no name in the URL。

 let's just default this variable to being something sensible like quote unquote world。

 So now let's proactively using some sort of week one style conditional code。

 albeit in Python now from week 6， let's just check is name in the URL， If so， grab its value。

 otherwise default to world instead。 So I'm still gonna leave this code as is passing in the placeholder for this template to get plugged in here。

 But now if I go back to the browser， and I just reload without passing a name equals David or anything else。

 Now we have a sensible default。 And if I go back to my view source tab and reload， I'll see that。



![](img/9e2f9fda28bc5aece4246768d8d754a6_28.png)

I have hello comma world in this case。 However， if I go back up to that URL and do slash question mark name equals David。

 now we have David。 if I change the URL to be name equals Carter， now we have Carter。 So indeed。

 we do have the beginnings of something that's more dynamic。 Of course。

 this is a little tedious to have to write out this if and this else。

 There's ways to kind of condense this code to be a little tighter and a little faster to actually implement and in fact。

 let me go ahead and propose that we just do this。 instead of treating args as a dictionary as we did with square brackets。

 which can cause problems if that key does not exist。 In fact， let me go back to that version。

 let me undo undo undo， whereby I'm just blindly going into request orgs to get name。 In fact。

 instead of just blindly indexing into this dictionary called args， turns out we can do this instead。

 let me go ahead and say request do as do get， which is a function that comes with a dictionary。

 And I can specify the name of the key that I want。



![](img/9e2f9fda28bc5aece4246768d8d754a6_30.png)

Get and by default， if there is no key called name in a dictionary。

 you're gonna get back a default value of none， which is kind of sort of like Python's equivalent of null。

 but it's none capital n in Python。 But if you want to give it a different default。

 It's handy to know that this get function， which you can use with dictionaries in general。

 can take a second argument， which will be the default value that you do get back if， in fact。

 there is no such key called name。 So what this means is I can actually now keep all the code the same。

 but it's a little tighter， there's no if or else， I can go back to my other browser window。

 click reload。 and it still works for Carterter。 But if I get rid of that I can now have hello comma world still working just as before。

 And just to add one more potential point of confusion to the mix。

 it's a little do to say placeholder literally in your template。

 especially if you're gonna be using multiple pairs of square of curly braces for one variable or another or another。

 So better style would be to actually called variable。



![](img/9e2f9fda28bc5aece4246768d8d754a6_32.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_33.png)

What makes sense for what it is your plug in。 So hello， common name with the name and curly braces。

 This is I show this though， because it gets a little confusing if your variables is called name。😡。

And that's still going to be the value pass in。 You're going to very often see in the world of flask this convention where you literally write something equals something where the names there are exactly the same。

 And the only thing to keep in mind here is that the name This is the name of this parameter。

 This is the value of this parameter。 The fact that everything seems to be called name in this program is because these technical terms are colliding with the English word that you and I know as name for my name。

 Carter's name and so forth。 But get past that only because it will be very common to literally see something equals something where just for visual convenience。

 the variables name is exactly the value that you want to pass in。 So that to here is conventional。😡。

All right， a little cryptic， but。Common boilerplate that you'll start to see again and again。

 Any questions now about this。No， okay， so let's make things a little more interesting and representative of a real world app。

 Let me propose that now we go about implementing maybe a second template altogether。 In fact。

 let me go ahead and do this。 It'd be nice if the human doesn't need to be technologically savvy enough to say that if you want to be greeted by this website。

 you have to literally change the URL yourself type in name equals like no one does it。

 That's just not how the web works。 in terms of user interface。

 But that is how browsers and servers do work。 But of course， in the web。

 we're almost always use form。 So let me go ahead and do this。 Let me go into index Hl。

 And let me get rid of just this hello comma body。 And instead， let me actually create an Hl form。

 This form is going to use the get method if only so that we can see what's going on inside of the URL。

 This form is going have an input where I'm going turn autocompte off just like last week。

 I'm going do autofocus just to move the cursor there nicely by default。 somewhat confusingly。

Give this input a name of name， because I want Carter's name， my name or someone else's human name。

 But I'm gonna give it placeholder text of quote unquote name capitalized just to be grammatically clear as to what we're prompting the user for and the type of this field is going to be text。

 although that's the implied default if I don't give it a type。

 I'm gonna lastly have a button in this form， the type of which is submit so that the browser knows to submit this form。

 And the label I'm going put on this button is like。 So I'm going type in my name， click。

 And I want to see helloa David or the like。 But I need to specify the action for this form。

 and recall that when we implemented Google unquote we did a little something like this H www Google co search。

 we're not gonna punt to Google today， we are implementing our own application。

 So if this were a search application， I could literally have an actionlash search。

 But let's do something a little more semantically sensible。 Let's create our brand new route called。

😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_35.png)

This is not the name of a folder。 It's not the name of a file。

 It's more generically a path or a route that is now up to me to implement。 If I go back。

 though to this application and reload this page， notice that I have the beginnings of a more user friendly form that's asking me for this name。

 However， if I do type in David and click。 I'll zoom in in just a moment notice that the URL does change tolash question mark name equals David just like Google co works。

 But of course， we're getting a 404 not found because I haven't implemented this route yet。

 So let me zoom out。 let me go back to the code。 let me open app pi and make a little bit of a change there。

 Let me make a little bit of a change and say this in app in app instead of just getting the user' name in this default。

 Let's simplify the index route and just have it sole purpose in life be to render index Ht the thing that contains the。



![](img/9e2f9fda28bc5aece4246768d8d754a6_37.png)

I'm going to now though create a second wrap route。 So app dot route， quote unquote slash greet。

 And I could call this route anything I want， but greet it seems sensible。

 I'm going to call the function below it anything I want。

 but just to keep myself saying I'm going to call it the same thing as the route。

 even though that's not strictly required。 And then in this route， I'm going to go ahead and do this。

 I'm going create a variable called name set it equal to request dot orgs dot get quote unquote name。

 then quote unquote world。 So the exact same line as before。 and then I'm going to return render。😡。

Template， which is the function that comes with flask。 I'm going to specify this time， though。

 render a template called Greek dot H Tl， which doesn't exist yet。

 but that's not going to be a hard problem to solve and pass in that variable。

So the last thing I need to do is this。 And I'm gonna kind of cheat and copy and in a moment。

 paste the contents of index do html into a new file called greet do html as follows。

 Let me open up Vs code here in my other term and all let me go ahead and write code templates greet do html notice that I'm making sure to put the new file in the templates folder or I could Cd into it and then run the code command。

 that's gonna give me a new file。 I'm gonna hide my terminal。

 paste that code and I'm gonna get rid of the form and frankly。

 I should have just copied and pasted this earlier because the only thing I'm gonna put in greet do html is hello and then in curly braces my placeholder。

 which we started to call name a moment ago。 So to recap if I go into my terminal again。

 if I type Ls。 I've still got app up pi， I've still got templates。

 but if I look inside of templates now I've got two templates index do htl and greet do htl。

 index html is the thing you see when you visit my website， greet do html is the thing you see。

When you submit that form， it would seem。 So indeed。

 if I go back to my browser and hit back so I get back to that form for good measure。

 I'm gonna reload because I want to make sure I have the latest version of everything。

 I'm gonna now try typing my name David I'll zoom in。

 you'll see that the URL will again change to slash greet with the question mark in my name。

 but hopefully we now indeed don't see a 404 because the new route actually exists。

 And if I zoom out right click or control click and go to view page source。

 you still see what appears to be a HTML file just for me。

 even though it was dynamically generated instead。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_39.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_40.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_41.png)

All right， if you're on board that this seems to be a correct application insofar as it does what I wanted it to do。

 let's critique the design as we've been in the habit of doing。 I've now got three files， app Pi。

 Greek dot HTMLl and index do H。😡，What might you not like about the design of this web application。

 even if you've never done this stuff before， yeah。Yeah， greet and index Htl have the same contents。

 except for like that one or few lines in the middle of the body。 I mean。

 I literally copied and pasted， which generally， even though I do it sometimes in class to save time。

 if I end up with the same code in my files that's probably cutting some corner and not the best design。

 what if I want to go in and change the title of this application from hello to something else。

 it's not a huge deal， but I have to change it in two places。

 what if I've got some pretty Cs that I've added， and so I've got some Cs up here in one file。

 I need to copy it into another file， change it both places like generally having duplication of anything is bad design。

 So it turns out there is a way to solve this。 And this is one of the features that you really start to get from a web framework be it flask or anything else。

 You get solutions to these problem。 So what I'm gonna do now is this I'm gonna create a third and final file for this application by starting by copying what I have already。

 let me go back to my terminal window here。 and let me create。

A third template in the template folder called layout do Html doesn't have to be called that。

 but that's the convention。 So I'll always do that here。

 And when I create this file and hide my terminal， I'm going go ahead and copy paste all of that content。

 but I'm going to go inside of the body of this file called layout do Hml。

 which is otherwise identical across all of my files and what I'm going do is use slightly weird syntax this is more of that ginja syntax that some other humans came up with years ago。

 and I'm going do this single curly brace and a percent sign。 I'm going to specify the word block。

 and then any name I want for this block and by convention。

 I'm gonna keep it simple and just use the exact same thing as the name of the tag that I'm inside。

 So block body and then I'm going to put a percent sign just before the closed curly brace。

 I don't need anything inside of this。 So this two is gonna look weird at first glance。

 but it's a convention， I'm going to do another curly brace with the percent sign and then literally the word n block。

 No space。And I'm gonna open and close what isn't an Hl tag。 It's a ginja tag， if you will。 So again。

 you see yet more evidence of like reasonable humans in the world kind of disagreeing on syntax or at least using syntax that's similar in spirit。

 but doesn't clash with the syntax。 the angle brackets that Hl already uses long story short。

 this is a way of specifying that you want a placeholder， not just for a single variables value。

 but for a whole block of code。 maybe it's simply a sentence。

 maybe it's a whole web form element or more， this is a placeholder now for a block of code。

 And the way I can do this or rather the way I can use this templates。

 And this is where template now is getting all the more literal in the sense of what templates do。

 I'm gonna go ahead and do this。 I'm gonna go into my two other files， like greet do Hml。

 The only line that's different in this file Vi the index Hl is which line number。

9ine is the only line that is unique。 So what I'm gonna to do is this。

 I'm going highlight that and copy it。 and then I'm gonna delete everything else in this file because it's just redundant。

 Everything I need is in layout H at the top of this file。

 I'm going use another curly brace and a percent sign。

 but I'm going use a special keyword that comes with Ginja called extends and I'm going specify in quotes here。

 the name of the template that I want to extend， so to speak。

 So this is an example of what's in computer science known as inheritance。

 I want to take everything from that layout and sort of inherit from it。

 all of its lines but plug in some of my own sort from like a parent child relationship inside of this file now。

 I'm going to specify that the custom body that I want is this block body just like before and then down here I'm gonna to preemptively say end block just to sort of finish my thought in advance。

 and then inside of this block body， I'm going simply paste that line。

codeode that I stole from the original version。 So Ill can see that this is pretty ugly。

 Like I've added three cryptic looking lines， all of which relate to Ginja templating， again。

 syntax that humans invented to give you the ability to write templates or blueprints。

 But the point is that this single line now line 5 is going to get plugged into that template called layoutt Hl。

 wherever that body block is meant to go。Lastly， I'm going to go ahead and do this。

 The only lines in index。 HTML that are unique are these here， 9， 10，1112。

 so I'm going to highlight those and delete everything else。

 and then I'm going to do the exact same thing， extends layout HTML at the top of this file。😡。

Then below that block body inside of the block body， I'm going to then say end block at the end。

 and in the middle of that， I'm going to paste those lines of code。 Just stylistically。

 I'm going to indent them just so I'm super clear visually on what is inside of what。😡，But that's it。

 So ugly， yes。 But as soon as your web pages get longer and longer。

 this ends up being a drop in the bucket。 It's three ugly looking lines relative to a lot of Htl that you be plugging in and customizing for your application。

 So now index Hl looks like this， Greek Htl looks like this。

 And the only way they differ is the actual content of that block of code。

 layout Hl is sort of the main blueprint that's gonna govern what the whole website looks like。

 I can change the title in one place。 I can add some pretty CS in one place and so forth。

 it's going apply to each of those files。 And now somewhat underwhelmly。

 perhaps if I go back to this application。 and I click reload like nothing is different because it's still just works。

 but I've made arguably a better design because now when I change things to Carter here or I get rid of it all together and just visit the default rather。

 if I just visit slash there。 I'll get the form。 I've at least handled the situation where I've。



![](img/9e2f9fda28bc5aece4246768d8d754a6_43.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_44.png)

This situation where I've just copied and pasted the same boilerplate code。

So odds are someone like Google is doing something like this。

 It's probably faner certainly this example。 but anytime you search for something on Google。

 generally like the top of the page looks the same， maybe the bottom of the page looks the same。

 there's maybe some ads always at the top and then there's 10 search results。

 So probably what they've done is they have some template that looks roughly like this with all of the boilerplate stuff that they want every human to see on every page of search results。

 and then they're just somehow customizing the block， a block of code somewhere there in the middle。

😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_46.png)

All right， questions on any of this actual templating technique。Anything at all。 No all right。

 How another question about design。 If I go back to this URL here and I search for something like David。

 it's not that big a deal that it ends up in the URL。 And in fact。

 what's nice about HtP parameters ending up in the URL is that URLs are therefore stateful。

 Like if you copy this URL and paste it into an email assuming the web server is still up and running at that URL。

 like it will just work。 And the human to whom you send that link。

 they will see David or Carter or whatever names actually in that form。

 which may be is useful behavior， not so much for this application。

 but imagine now that you want to send someone a link of Google search results。

 It's a good thing that Google puts Q equals cats or dogs or birds or whatever in the URL because then the URL itself is stateful。

 What you see is what the recipient will see because all of the input to the server that's requisite is in that URL。

 But suppose that this form field if I go back wasn't asking for my name。

 but like my credit card number or my password up here。



![](img/9e2f9fda28bc5aece4246768d8d754a6_48.png)

Like that should start to rub you the wrong way because it feels like no good will come from exposing private information in the URL because if you have like a nosy sibling look over your shoulder。

 there it is in your search history， a roommate goes through your autocomplete and finds the data there。

 Or if you do， for whatever reason， copy paste it， you're accidentally including private information in these URLs。

 So I said last week that there is an alternative to sending things in the URL。

 and that alternative is to use something that's not called get but a verb in the world of HttP that's called post instead。

 And it's actually relatively simple change。 If I go into index of H。

 I can simply change the method from get to post get is the default。 post is an alternative。

 even though in some context， you'll see capitals in HTML， it should be lowercase。

 another example of sort of left hand not talking to right。 But in this case， if I go now。😡。

To my other tab with the browser， reload the page because I want to get the latest version of the form if I now type David and I'll zoom in before hitting En。

😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_50.png)

If you watch the URL now， you should not see that question mark name equals David is up there。

 nor would be your credit card or your password。 Unfortunately， we're seeing another HtP status code。

 we haven't seen yet。40，5 method not allowed。 Well， why is that。

 That's because now that I fully control the Web server。

 I need to tell the web server that I do want to support， not just get。

 which is the default but post as well， the method the user is using is not supported。

 So this is an easy fix， even though it's gonna look a little cryptic at first。

 if you want your method to support not just get but post。

 you can specify another argument to this route function。

 So the default is literally this methods equals， and then in square brackets。 quote unquote。

 get So what is this， Me is apparently a named argument being passed into the route function。

 I claim it's default value is this。 What do the square brackets indicate in Python。



![](img/9e2f9fda28bc5aece4246768d8d754a6_52.png)

Not a dictionary。 Square brackets。A list。 So it's a list of strings or stirs in this case。

 This is the implicit default。 So you don't have to type this。

 It's just what works out of the box automatically。 But if you want to change this from get to post。

 you have to include methods equals a list of the methods that you do want to support for another time there's other HttP methods。

 there's delete there's put theres those are the two biggies that you might use as well。

 those are generally not supported as easily in the world of browsers。

 but get and post certainly are。 if you wanted to support both for whatever reason。

 you can literally have a comma separated list of those methods instead。

 but we don't really need both for privacys sake。 I claim I'm only gonna use post now So now if I go back to my other tab go back to the form。

 reload to make sure everything is as expected。 and now type in David and zoom in you won't see my name in the URL but or you won't see it good not intended。

 but nor will you see it even。😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_54.png)

In the body of the web page， so it's super secure。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_56.png)

Why？I screwed up， but why？Yes。Its not going to be。Yes， so good intuition。

 even if you knew that before， you might think through rationally like how might this be why might this be behaving this way。

 Well， if I go into app pi， it seems that if world is the value of the name placeholder。 Well。

 it must be the case that there is no name key in request do orgs in this case。 However。

 there's an alternative to request orgs and it's called request do form。

 This is another example of like visible and hidden being opposites of one another request do orgs and request form。

 at least for me are not obvious mappings to get and post respectively。

 but that's what the flask folks did。 And so the simple fix now if I go back to VS code is to change request orgs to request do form。

 if you want to use post instead of get this is a weird misnomer because they're both coming from forms。

 whether you're using get or post but this is what some folks decided。 So let me go。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_58.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_59.png)

Back to my browser， go back to the original form， reload to make sure I get the fresh H。

 type in my name now， David， zoom in and click。 And this time， you won't see my name in the URL。

 but you should see it in the body of the page。 So we've achieved some form of privacy， if you will。

 better apply to things like credit card numbers， passwords and the like。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_61.png)

Other questions。On any of this thus far。Anything yet？No， all right have yes， in the middle。

A good question to repeat if you were supporting both get and post。

 should we have a second line that's also checking request orgs。 Yes。

 if you were either decided at the last minute only to support post， not get。

 So I don't have to bother with that。 But your question is a perfect segue to a final example of this hello application where you can actually consolidate different types of functionality into individual routes。

 why at the moment， this application is super simple。

 It's literally got one form and then one resulting page。

 but it's implemented therefore with a pair of routes， like a pair of functions。

 no big deal for small applications， but if you imagine more complicated application be it Google or anything else that has many different web forms on different pages。

 it's a little annoying if every form needs two separate routes。

 if only because you now have to keep track of literally twice as many functions。 your colleagues。

 your teaching fellow needs to know which one is related to which So there's something to be said designwise about consolidating related functionality into one single route so that everything is together。

 Well we can。

![](img/9e2f9fda28bc5aece4246768d8d754a6_63.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_64.png)

achievechve that relatively simply as follows。 Let me go ahead and completely eliminate this greet route and simply have everything exist in the slash route。

 And I'm gonna go ahead and highlight and cut these lines out of there altogether。

 But if I want my single slash route to support multiple methods。

 I indeed need to use methods equals and then in square brackets get and post order doesn't matter。

 but I'll keep them alphabetical in this case。 inside of my index route。 I need to know in advance。

 I the user visiting me via get or post， because if it's via get， I want them to see the form。

 If it's via post， I want to process the form that is do something with the user's input。

 So it turns out it's relatively simple。 if request dot method equals equals post。

 then I can do the following。 So you can literally check the request object。

 which comes with flask to figure out the word get or the word post in that virtual envelope and would depending on the answer。

 you can do something like。😊，I can paste those lines from earlier。

Whereby I get the variable name from request dot form。

 and then I render the template greet do Htl passing in that name。 Otherwise。

 you know what I could just do else。 return the template itself。 So if the method is post。

 go ahead and process the form just as we did before， else。

 go ahead and just render the index template， which contains the form。 Strly speaking。

 I don't even need the else。 I can get rid of that just to tighten this up a little bit and unindent my last line。

 Y， because recall that from C from Python。 as soon as you return a value。

 Nothing in that function is gonna get executed thereafter。

 So you might as well kind of tighten up the code so that you don't bother adding undo indentation if not needed。

 So notice now， if I go back to my browser。😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_66.png)

Reload here。 It's not going to work yet。 but let's see if you can diagnose the issue。

 If I type in David here and click greet。Now I'm back to getting a 404， but for different reasons。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_68.png)

Good， I haven't changed not the method， but I haven't changed the action in the form itself。

 So if I go back to V S code here， and I go into the web forms， the Htl post is still fine。

 but there is no slash greet route anymore。 so I actually can just specifylash。

 or it turns out if you will omit that altogether， the form will assume that you want to submit it to the very route from which you came。

 So that is fine as well。 I'm gonna go ahead now and go back to that other tab and go back I'm gonna reload the page and just for a good measure this time。

 I'm going control click or right click view page source and hereep the action has indeed updated。

 So I think I fix the bug。 Now， if I type in David and click greet we' back in business with it working。

 So notice that this still allows me the convenience of having two separate two separate templates one for the form。

 which shows the which collects the user input。 and one for the actual greeting。

 which displays the user input。 So I'd argue that still make sense to keep those separate。

 but I can avoid bloating my app by having two methods for every single feature。



![](img/9e2f9fda28bc5aece4246768d8d754a6_70.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_71.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_72.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_73.png)

That I might want to implement Now， there is still a bug in this implementation。

 even though it's a little bit subtle。 So recall that previously we introduced this default value of world just in case the form doesn't actually contain the word world。

 as might have happened I if I manipulate it into the URL that I was requesting manually as I did before。

 But it turns out that if you're using an actual form and not。

 of course expecting the human to type anything into the URL bar， which no human would do。

 it turns out that the browser is still going submit a name parameter， even if it's value is blank。

 that is empty。 the so-called empty string。 And so even if it's the empty string。

 it's still going to be considered to be a value and therefore not worthy of having the default value of world plugged in。

 In other words， if I open up my terminal window here。

 rerun flask run and go back over to my browser and load this example， if I type in David as before。

 I'm going to be greeted with hello comma David。 But if I try this again and don't provide an actual name。

 but just click。

![](img/9e2f9fda28bc5aece4246768d8d754a6_75.png)

Greet， it turns out the name parameter is still going be submitted to the server in which case request form get is not going to rely on the default value。

 but rather that empty string value。 And so we see what appears to be a bit of an aesthetic bug hellello comm nothing So how can we go about fixing this。

 Well， perhaps the simplest way is to no longer rely on this default value here inside of app dot pi。

 So in fact， let me go ahead and delete that default value altogether and pass name in as the variable it still is into greet do hml or template。

 but in greet do hl let's add a bit of logic there whereby we conditionally display the name if and only if it's not empty。

 In other words， before I output blindly name inside of these curly braces。

 let me borrow some syntax from Python and actually use within my ginja template。

 a conditional like this open curly brace and then a percent sign because this time I want logic。

 not just interpolation of。😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_77.png)

Variable and I'm going to say if name and then I'm going to do another percent sign and a single curly brace。

 And then after that， I'm going to still use my variable name name inside of two curly braces。

 but after that， I'm going to do again a single curly brace， a single percent sign。

 and then I'm going to say else followed by one more percent sign。 and then after that。

 I'm going to go ahead and actually put my default value world。

 and then close this if conditional with a single curly brace， a single percent sign and end if。

 and then I'm going to go ahead and close that tag there。

 So in Gingja turns out that we can use it not only to plug in values。

 we can also do a bit of lightweight conditional logic using an if and an else and an end if in this case。

 which isn't quite like Python indeed， the end if is a little bit different。

 but this is particular now to the ginja template。 and I've done it all on one line just because this is a fairly bysized conditional。

 either print out the name or print out world， otherwise I could actually put these。

Template tags on their own minds in order to spread things out all the more。

 We'll see now before long that there's actually some other control flow capabilities of Gingja。

 including loops and more。 But for now， this is a nice way to solve that one problem because now when I go back into my application and I go back to the form and type in D I。

 it's still going work as expected。 Hello， comma David。 But if I go back one final time。

 type nothing in thereby sending an empty value to the server and click greet here to demonstrate as much。

 now we do， in fact， see hello world。 All right， Any questions。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_79.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_80.png)

On this final example of just saying hello。From those basics come pretty much all of dynamic web applications today。

all right， so if you'll indulge me， here's an actual web application that I made back in the day。

 So when I was a sophomore， I think I was not very athletic。

 So I didn't so much do freshman intramural sports as I did run them with a roommate of mine。

 So we were sophomores in Ma house he was the athlete。 I was the aspiring computer scientist。

 And so this was actually a screenshot of the very first web application I ever made。

 And this will sound old too。 But back in my day， freshman year when we registered for Frosh I am or freshman intramural sports。

 You would literally like walk across Harvard Y to wigglesworth where a certain proctor or R lived who was running Frosh I am。

 And you would like literally slideest sheet of paper under the door with your name on it and your choice of sports that you want to register for。

 So that was the that the art in 1995。 This was ripe for disruption。 as people would now say。

 And once I actually took C S 50 in the fall of 1996。

 which did not teach funny enough web programming at the time。

 I think I spent that winter or spring sort of figuring out how to do stuff with Web programming。

 not using C and。😊，using Python at the time， I was using a language called Pel。

 which is still with us， but not as popular was it was back in the day。

 But what you're seeing here is a hideous screenshot of what the user interface was。

 this was me learning how to repeat background in images infinitely no matter how big the page was back in the day。

 there was no CS I think even at the time。 So every one of these menu options was actually an image and even though this is a screenshot。

 So it's not animated if you would hover over any of these words what I would do using jascript which did exist in an early form was just change the image from like a blue image to a red image creating the illusion of the trickery we did last week with text decoration as you might recall and hover。

 So the webs come a long way， but this is still representative amazingly like some 20 years later of how web applications still work。

 I used a different language， I used a different backend for my data or database。

 but everything I did then we will now do effectively today and beyond because the principles。

HaveNot changed。 It's all based ultimate line H T TP and all of the stuff we discussed thus far this past week。

 And now this。 So let's go ahead and make the beginnings of this website。

 though perhaps without as many of the hideous images underneath it in my V S code。

 I'm going go ahead and close all of my prior tabs。

I'll open up my terminal and I'll hit control C to exit out of flashask。

 just like you can hit control C to exit out of the HTP server。

 I'm gonna go ahead and hit Cd to go back to my main workspace。

 and I'm gonna create a new folder with make their called Fro I am so that all of my new application is inside of this folder。

 I'm gonna Cd into Fro I am。 and let's go ahead and make a very simple application that essentially pretends to let first years register for a sport。

 So I'm gonna need to do a bit of typing up front， but I'll do the first one from scratch and then we'll start just evolving that same example。

 Let me go ahead and do this。 Let me go ahead and actually we'll do this。 we cut one corner。

 I'm gonna go ahead and copy from my hello example app up into this folder。

 I'm gonna go ahead and copy from my hello example templates。 My layout into this folder。

 I'm gonna create a new folder called templates。 I'm gonna move that copied layout。😊。

Into templates so that if this is important in the story。 if I clear my screen and type Ls。

 I've got the beginnings of a web application， even though it's specific to just saying hello。

 but I'm gonna to go ahead and into the templates folder and go into layout that Hml。

 Let's just change this ever so slightly to say Fro I ams as the title just so we know we're looking at the right application And now let me go ahead and create a new file called how about index do Hml inside of templates that just as before is going to extend that there template。

 So extends layout do Hml inside of here， I'm going to say block body just as before preemptively going say n block and then inside of here。

 I'm gonna make the beginnings of a super simple web page for first year intramural。

 So I'm gonna to use an H1 tag that's sort of big and bold that just says register at the top of the page sort of like a title below that。

 I'm gonna have a form the action of this form。 I'm gonna to say proactively is going say。

lash register。 So that's it to do。 We're gonna have to go implement a register route。

 The method I'm gonna use is post just for privacy sake so that if roommates are sharing the same computer。

 they don't see in the autocomplete， who's registered for what inside of that form。

 I'm gonna have a single input first where autocomp is off autofo is on the name of this field will be named because I want to ask the humans for their human name。

 the placeholder just to be self-decrib is going to be quote unquote name capital end gramatically。

 And then lastly， the type of this field， though it's the default is text。 So so far。

 this is actually pretty darn similar to the hello example soliciting someone's name。

 But now I want to maybe implement like a dropdown menu via which you can select a sport and back in the day。

 I think the first version of f am students could only register for basketball soccer and ultimate Frisbee。

 So those were three of the fall sports。 So let me do this。 It's a little weirdly named。

 but a dropdown menu in Hl。Is called a select menu because you select something from it。

 The name of this input， which is really what it is is going to be sport。

 though I could call the input anything I want。 and inside of this select elements。

 I'm gonna have a few options。 I'm gonna have one where the option is how about basketball another option。

 the value of which is soccer and lastly a third option， the value of which is ultimate frisbee。

 So just those three sports， but suffice to say we could add even more。

 And then outside of this select menu， I'm gonna have a button just like the hello example。

 the type of which is submit just to be super explicit， even though that's not strictly necessary。

 but it's another attribute you'll see in the wild。

 And then the name on the value of this button will be register。

 So it's clear that you're not being greeted， but you're actually registering for sports。

 Now we're not quite good to go yet。 but let me go into Vs codes terminal again。

 let me open up app up pie and close my terminal again。 and let's。

Whittle this down to something super simple。 I don't want to get overwhelmed just yet。

 I don't want to support even posts。 So let's just whittle this down to the essence of this。

 So I can do a quick check mentally and make sure now。

 when I run flask that I'm serving up that registration form。 So in my terminal。

 I'm gonna run flask run in my F I ams folder。So far so good。

 it's gonna to be by default the same URL unless I've rebuilt or created a brand new code space。

 So let me go back to my other tab and reload that URL。 And okay。

 we've got the beginnings of a more interesting form now， So it's got place for my name。

 It's got a dropdown for the three sports。 So let's see what happens。 D A V ID We'll say soccer。

 And when I click register， just to be clear， what route will I find myself at perma URL。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_82.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_83.png)

Slash。What was it to be if I go back into my index。Slash register。

 But what error will I see presumably at this point in time。

 given that apptop Pi has only been implemented to this extent。



![](img/9e2f9fda28bc5aece4246768d8d754a6_85.png)

So probably 404 because the route won't be found。 So if I click register。

 I indeed end up at slash register， but if I zoom in up top here，404 not found。 All right。

 so it's the beginnings of an application， but I've implemented the frontend so to speak the user interface。

 but not the backend， the business logic that actually does something with the user input。

 but a couple of enhancements here。 but these are largely nice cities in HTML。

 it's a little bad user experience that by default， you're registering for basketball。 I mean。

 that's fine， but arguably you're biasing people to registering for basketball or they might not realize that they're registering for basketball because they didn't explicitly choose a sport So having an arbitrary default that just happens to be the first word alphabetically is a little weak when it comes to design。

 So there's different ways to fix this。 But one way is to do this at a new option at the very top。

 but go ahead and disable it so that the user can't themselves select it because you want them to select an actual sport。

 by default。😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_87.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_88.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_89.png)

You can specify that it's indeed selected and it has no value not to judge any sport。

 but this particular option has no value。 but what the human sees is like the word sport。

 for instance， So this is kind of a hack ideally， the select menu would just have a placeholder attribute like the actual input boxes does but that does not exist。

 So if I reload now it looks a little more user friendly。 So it says sport。

 I can't select sport ever again， but it is the default， but I can select one of these three sports。

 which just increases the probability that the human does what you might expect。 Of course。

 there's something else I can add here。 Supp I don't even give my name。 It still went through。

 It didn't work。 It's still a 405。 but the 404， but the browser didn't stop me。

 So recall that we do have some other tricks。 for instance， I can say that this drop down。

 the select menu is itself required sorry， not this one。 The text box is itself required。

 for instance。 So now if I go back to the form and reload and I。



![](img/9e2f9fda28bc5aece4246768d8d754a6_91.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_92.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_93.png)

Ignore the name question and click register the browser is going to yell at me Now recall that this is not robust like client side validation is not good why？

😡，What we learned last week？Yeah， I mean， I can literally write clicker control。

 click and open up developer tools。 I can go into that form using the developer tools。

 I can literally find the word required， delete it。

 and voila this form will now go through because the browser is gonna do what I change。

 So it's useful for user experience sort of making just things a little prettier and faster to validate。

 but it's not gonna be robust defense。 All right， so let's go back now to VS code into my actual route and implement at least something here that resembles registration。

 So I'm gonna go into app pi， and an app pi， let's create this second route。 So at app dot route。

 quote unquote slash register to match what is in my Hml。 let me define a function。

 I can call it anything I want。 But again， good convention to just call it the same thing as the route name so you don't get out of sync。

 And then there's a couple of things I might want to do。

 Like when you register for this particular form， What are the two things that the server should probably check for。

😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_95.png)

What kind of logic should I have here。呀。Okay， so let's make sure that the name is present and the sport is present ideally。

 So let's actually validate the user's input， just like get into did back in week 1。

 just like get get string， get float and all of those。 they made sure that you actually got input。

 So there's a bunch of ways I can do this。 but I'm gonna go ahead and take a relatively canonical approach if not request dot form dot get quote unquote name。

I'm gonna go ahead and then return how about， let's just see failure， quote unquote， failure。

 just as a quick and dirty solution。 So if it is not the case that there is a value for the name field。

 just assume that there's a failure。 So how can I test this。 Let me go back to the other tab。

 Let me go ahead and not type in my name and click register and notice， well， okay。

 I need to get rid of the required。 if I actually want to see this thing go through。 So， you know。

 let's just change the the template。

![](img/9e2f9fda28bc5aece4246768d8d754a6_97.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_98.png)

Let's get rid of that。 So I don't have to hack into it and delete things manually。

 So let me reload the form。 Let me not type a name， click register and dang it 4，0。

5 method not allowed。 What's the fix for this in my app。



![](img/9e2f9fda28bc5aece4246768d8d754a6_100.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_101.png)

What line number needs to change。Yeah， over there。Yeah。

 I need to allow both or at least post at this point。 So I'll keep it more restrictive。

 So methods equals。 and then in en list， quote， unquote， post。

 because that's what I'm using in my template as the method。 Alright， let's try again。

 I'm gonna go back。

![](img/9e2f9fda28bc5aece4246768d8d754a6_103.png)

I'm gonna not type a name and I'm gonna click register。 Okay。

 so it caught the fact that the name was not provided。

 Let's now go back and try again and actually cooperate， David， register。 Okay。

 now internal server error。 So something's gone even worse here。 And unfortunately。

 you're gonna start to see this over the next couple of weeks。

 This is like Python and the web's equivalent of segmentation fault。 it's a different issue。

 but it's gonna hurt just the same。 unfortunately， So let's go back to V S code here。

 Nothing seems to have gone wrong， But that's because I've hidden my terminal。

 Let me open my terminal window。 okay， so it looks like I made a crazy number of mistakes here somehow。

 But let me go ahead and focus on and the formattings a little weird for some reason。 here we go。

 It's a little cryptic at first glance。 But here's the most important line of output。

 The view function for quote unquote register did not return a valid response。

 So you're not gonna see this one too often， most likely， unless you do what I did。

 which was you didn't have an else like didn't。

![](img/9e2f9fda28bc5aece4246768d8d754a6_105.png)

the situation where there is a name and something should have come back。

 So maybe I could do this by default。 I could just say something like success as a catch all。

 even though I've not done anything useful yet。 let me try this again， let me go back。

 David is typed in no sport register。 okay so now I'm making progress again。

 So just like week one stuff， I make sure I'm always returning some value。

 whether it's success or failure in this case。 All right。

 let's do something a little more interesting though， I could do this。

 How about L if not request do form get sport， I could similarly return failure。

 but this is a little silly to have two nearly identical conditional。 So actually。

 let me just tighten in this up。 let me go ahead and instead get rid of those two lines。

 and maybe just do something like this in Python or not request dot form， get sport。

 This is maybe the tightest way just ask two questions that are essentially the same。

 but for two different keys。 But returning quote unquote failures。



![](img/9e2f9fda28bc5aece4246768d8d754a6_107.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_108.png)

We like， that's not a valid web page。 It's literally the word failure。 So maybe we do this。

 render template， quote unquote， failure dot H Tml。 And you know what down here。

 render template success dot H Tl。 So we actually send the browser a valid webp page。

 not just a single English word。 Of course， we're gonna need those templates。

 So let me go in and do something like this。 If I go into。How about？My terminal window。

 I need another terminal because flask is still running in that one。 And let me go into Fro I ams。

 And let me do code of templates success dot H T M L。

 I'm gonna save a few keystrokes and copy paste all that stuff from index。

 But I'm gonna delete most of it。 And I'm just gonna keep it super simple today。 You are。😊。

Registered and then not really， because we're not gonna bother doing anything yet with the user's input。

 Let me do something similar now for failure。 So code templates， failure dot H Tml。

 I'm gonna copy paste the same thing And now I'm gonna say the opposite。 you are not registered。

 but I'm not going be very useful， and I'm not gonna even yet tell the user what they have done wrong。

 But at least now we have the beginnings of a f I ams app。 So let me go back reload everything。

 let me not cooperate at all and click register。 Okay。

 so you are not registered because of some failure。 I'll type in my name。

 let's at least do that much。 I'm still not registered。 Let's go back。

 let's leave David and choose soccer。 now now you are registered。

 So I got the success template instead。 Allright， so that seems to be better progress or at least the beginnings of an actually useful application。

 but let's actually do more validation。 because notice what the human could still do。

 suppose that you know of principle， you really want to register for like a different sport like。



![](img/9e2f9fda28bc5aece4246768d8d754a6_110.png)

you're not a fan of like soccer。 You want like American football。

 Okay so let's right click or control。 click on that。 Cho In。 and you can even do this client side。

 Let me right click on the select menu in Chrome。 let me select edit is HMl。

 you can start adding any Hl you want。 So let me add an option football close option enter and now you have to support football as well。

 Of course， this is going to work because if I type in David in football and register。

 even though I'm not doing anything response， I got through that validation filter because I was just checking that there's an actual value So this is now no longer really correct right because like some annoying first year who's just like taking CS50 is now going do something like this to my web application and we're gonna have bogus data in the database ultimately。

 So how do you defend against this properly when it really is that easy。 And honestly。

 as soon as you put a web application on the Internet。

 like bad things will happen to it because of people with too much。



![](img/9e2f9fda28bc5aece4246768d8d754a6_112.png)

Every time so。How do we defend against it。What would be a better approach？Nice。

 so add another conditional such that the only things allowed are the sports we actually are offering this semester。

 And in fact， you know what， we can take this one step further。

 the fact that I hardcoded into my form， my select menu those three sports。

 it'd be nice to maybe factor out those sports altogether so that I have one authoritative list that's used for generating the form and also validating the user's input。

 So let me do this in app pi。 let me go in here。 and I can put this about the top of my file to be conventional。

 I'm gonna create a global variable called sports by convention in Python。

 I'm gonna make it all uppercase， even though that doesn't mean anything functional。

 There's no constant keyword in Python。 So it's more on the honor system that like no one else should touch this。

 but inside of my list here。 let's go ahead and do only the official three basketball soccer and ultimate frisbee。

 So now I have a Python list of values that it would be nice to use to generate that other form。

 So this is maybe。Not obvious， but I think it's just an application of past ideas。 What if I do this。

 What if I pass into my index Htl template， a placeholder called sports and set it equal to the value of that global variable sports。

 Now I'm trying to adhere to best practices like the placeholder called sports and lowercase。

 but the actual variable， I called all uppercase just to make clear that it's a constant。

 even though that's on the honor system， but this too is conventional。

 This is a pythonic way or a flaskcentric way to do this。 But now in index do Hl。

 this is where Ginja gets interesting this lightweight syntax for using placeholders gets interesting。

 because I can now do something like this。 I'm going to delete all three of the sports。

 but not the disabled option， which is just the placeholder text inside of this select menu Now I'm going to do this just like Python。

 I'm going say for sport in sports using the curlib notation and the percent signs， which are。

Gingja specific， even though Ginja and Python use almost the same syntax。

 and that's one of the upsides of it。 You're not learning two things。 You're learning like 1。

1 new things。End4， which looks stupid， but this is a convention in a lot of languages to literally say end and the name of the keyword that you are ending with no space inside of this gingja loop。

 I'm gonna write an option element once option and then inside of the two option tags。

 I'm going to do my placeholder syntax with two curly braces and just say sport like this。

 And if I now go back into my browser tab and hit back here and I reload the page。

 notice that I still have a dropdown that's still automatically populated because indeed if I go to view page source and look at the actual HTMLm。

 there's some extra weird white space。 but that's because I hit enter in my template and it's generating literally what I put inside of that ginja tag it's generating that list of sports。

 And it turns out I'm going gonna to do this just to be thorough。

 It turns out that the option element technically lets you specify a value for that sport often they're one in the same like what the human sees。



![](img/9e2f9fda28bc5aece4246768d8d754a6_114.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_115.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_116.png)

Is what the value of the option is， It's kind of like the AHf thing in the world of URLs。

 but this is not going to change the functionality， but it's going to do this if I reload now。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_118.png)

And I view page source。 This is maybe a more common way to see options where in orange in my browser is what the server is going to receive in white is what the humans going to see。

 They don't have to be one and the same for reasons we'll soon see。

 But what's nice now is that if I do actually want to officially support American football。

 I can go in here， add football quote unquote to my list。

 go back to the form reload and whilea now I have a list of all four。

 But I haven't on the second side of what you proposed， which is actually validate those sports。

 So let me do that， let me go over to app pi。 And in app pi。

 and will no longer support football there。 Let's do this in my registration route。

 So instead of just checking is there a value。 And the whole point of using not is kind of like in see where you use an exclamation point to invert the meaning。

 So if it's empty， but it's not then a whole value is true， let's get rid of this line。

 And let's instead do something like this。 How about if not request。



![](img/9e2f9fda28bc5aece4246768d8d754a6_120.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_121.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_122.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_123.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_124.png)

t form dot get name。 So let's still just check for a name or request dot form do get quote unquote sport is not in the sports list now。

 go ahead and say there's a failure。 So what does this mean if I go back to the browser and reload。

 I now see only three sports。 And I think this will work。 okay， David， will register。

 say for soccer register and it seems to work。 But if some hacker comes along and really wants to register for American football。

 I'll right click there。 I'll inspect this。 I'm gonna sort of hack the form and add a bogus option at the very end just for myself and down here。

 I'm gonna say option value equals quote unquote football and then。



![](img/9e2f9fda28bc5aece4246768d8d754a6_126.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_127.png)

Inside of the option。 I'm gonna say football， just to be consistent。

 even though they're one in the same。 save that， close the developer tools。

 chooseose the hacked option， register。 But no， we caught it this time。

 So this is like hugely important。 And there are so many darn websites in the real world where the programmers either don't know or don't care to actually validate stuff server side。

 like this is how servers quite often get hacked。 You might have client side validation using HTMLl or jascript。

 and it looks nice。 It's immediate， it's very pretty and graphical。

 But if you're not also paranoically checking on the server。

 this is indeed how servers get hacked or at least in the best case here。

 your data set is sort of polluted with sports that you're not actually gonna offer。

 So this is not a very harmful attack。 but it's representative of what kind of what kind of actions can be taken on your server。

 if you don't distrust the user。 So unfortunately， this is kind of a negative day， Never。

 ever trust user input。 We saw that already with SQL and injection attacks。



![](img/9e2f9fda28bc5aece4246768d8d754a6_129.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_130.png)

All right， any other questions， Any questions thus far on this。Otherwise。

 we'll add a bit of spice in just a moment。No， all right。

 Well just to show you an alternative to this， let me change the Gui。

 The graphical user interface slightly。 dropropdown menu is pretty compelling here。

 but there's other techniques。 and we won't dwell on Hl tags， which you can pick up largely online。

 but let me go into maybe index H TMl just to show you one different approach here。

 And if if you really like radio buttons like a little circles that are mutually exclusive。

 This is a throwback to radio before my time in cars where when you push button for one radio station。

 it would pop out the buttons for another essentially for like your favorite channels。

 radio buttons are by definition， therefore mutually exclusive。

 So if I want to see those radio buttons and not a select menu， let me go into index Hl。

 And instead of this select menu， let me actually delete that And even though this isn't gonna be super pretty。

 let me do this for sport in sports just as before and for just preemptively inside of this gingja loop。

 I'm going do this。 I'm gonna do an actual。

![](img/9e2f9fda28bc5aece4246768d8d754a6_132.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_133.png)

Input tag， but it's not going to be text， but the name of this tag of this of this element is going to be sport。

 The type of this element is going to be radio for radio buttons。

 And the value of this button is going to be， whatever that sport is。

 But what the human is going see next to the radio button to the right is the same thing。

 The name of the sport。 So this is going to look a little different。

 And it is going to look ugly in my black and white viewport here with no CS。

 But it does speak to how you can change the user interface just using different building blocks。

 Let me reload。

![](img/9e2f9fda28bc5aece4246768d8d754a6_135.png)

And okay， it's probably not the right call here because it's just kind of making things ugly。

 but it's as simple as that because if I now click on this or this or this。

 they're indeed mutually exclusive。 However， suppose that you want to allow the particularly athletic first year to sign up for not one。

 but two sports or all three， in no case now can you support that right now， the work around now。

 for a bad website would be， just go register twice or go register three times。

 It's not a huge deal because you just hit back and then you change the dropdown and submit。

 you hit back， you change the drop down and submit。 but that's just bad design。

 Like surely we can do better than that。 So in fact， let's make one change here and use checkbox。

 And if you've never really thought hard about this in the web like radio buttons in checkbox have this distinct property where the former is mutually exclusive。

 And the latter is inclusive whereby you can check0 or more of those boxes collectively。

 So if I actually just go into that same template and change the type of this input from radio。



![](img/9e2f9fda28bc5aece4246768d8d754a6_137.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_138.png)

Checkbox and then go back to the browser and reload。

 you immediately get what you and I see in the real world as checkboxes。

 and the upside of this is that you can check now zero or more of them。

 but the catch and this is subtle the catch with our code right now is that we're only expecting one value。

 So it's a minor fix， but it's a useful thing to know if I go back to app pi if I actually want to get all of the sports from the users。

 I'm going have to change my validation slightly。 So I'm going to do this I'm going check for the presence of a name as before。

 but then I'm gonna to use a loop to validate the sports because I don't want them to slip like football back into the list even if it's not there。

 So I'm gonna say this in Python for each sport in request do form do get all if you know it's a checkbox。

 you want to get all of the checked values， not one for the sport parameter then go ahead and do this if the current sport is not in that sports list。



![](img/9e2f9fda28bc5aece4246768d8d754a6_140.png)

Top， then go ahead and return render template failure。Dot htm。Did I make a mistake here。

 I think we're good there。 So we're checking against every value that was checked on the form。

 Is it actually valid。 And so now if I go in here， reload， type in my name， David。

 and I'll just check one of them for instance， because I've not hacked the form and added something bogus like football。

 maybe someone was alluding to this。 I see now in error。 So let's do this together。

 Not sure what I did wrong。 I'm gonna open up my terminal and go to here And oh， interesting。

 my spacings a little weird here。 but attribute error。 immutable dictionary has no attribute。

 Get all。 So this is me lying to you。😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_142.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_143.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_144.png)

I don't think so， but。Bronongshin， are you here did this did flask change since I last did this， no。

Okay， so flask post form。Get all。Alright， here we go。 Well，2012， this is probably out of date， but。啊。

You know， that's not a bad idea。 Okay。All right。Okay， in Flask。

 how do I get all of the values from an HTML？Input of type。Checkbox from request。form。哎呀。Well。

 this is horrifying， okay。Get list， damn it， okay。What a good duck， all right。



![](img/9e2f9fda28bc5aece4246768d8d754a6_146.png)

All right， so we'll rewind in time so， thank you。That's a good lesson。 Just do as do as I do。

 Alright so get a list， we'll get you a list of all those values。

 So now if I go ahead and register as David， click just soccer without injecting something like American football and register now I'm。

 in fact， register， but not really， not really in the sense that we haven't actually done anything with the data。

 So this is to say ultimately that there's a lot of these building blocks。 not only in Hl。

 which is mostly a throwback to last week。 But also now in flashask where you can process all of those building blocks and take control over what up until now is usually the domain of Google or websites that you actually use。

 now you actually have more of the building blocks via which to implement these things yourself。

 So let's go ahead and add some final features to Frosh I am here where we're actually doing something with the results。

 And for this， I'm going to open up version in advance。 So I'm going go over to VS code here。

 And let me go ahead and close these tabs。😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_148.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_149.png)

But go into my second terminal window。 and I'm gonna go into today's source 9 directory and I'm gonna go into version 4 Frosh Is。

 which has everything we just did plus a bit more。 in particular， I'm gonna go ahead and do this。

 I'm gonna show you app pi， which additionally has some comments throughout， But in app do pi。

 what you'll notice is that after all of my validation。

 I'm actually got a couple of new features here， It's a little weak in terms of U I to just tell the user failure like you are not registered That's all my template previously did。

 But what if I borrow an idea from my index template where all of this time for hello and F Is。

 I've been passing an input。 So what if I do this， let me show you in templates failure do Html。

 or rather let's say in templates error do HtMl， So notice this。

 I can make the beginnings of like a common format for an error page。

 So in error do Htl of this fourth example， I've just got some big bold error message at the top。

 But I have a paragraph tag。Inside of which is a placeholder for an error message and then I've gone one step further just because and put a happy grumpy cat as an image to sort of let you down easy that something has gone wrong。

 But this is like now every website where there's generally some customized error message when something has gone wrong or when you have not cooperated with the rules of the form So what am I doing instead instead of rendering failure html very generically。

 I'm rendering this new template error do Hl。 and I'm passing in a custom message why because now in my app dot pi。

 my logic， I can actually say you're missing your name。

 you're missing a sport or I can tell the human what the error is。

 which is much better user interface down here though。

 on this new line here's where I'm now beginning to actually register registrants What's the easiest way to do this let me scroll to the top of this file and you'll see that in addition to a big list of sports。

 I also have a empty dictionary initially of registrants why。

dictionaries are this nice like you know Swiss army knife key value pair。

 key value key value names could be keys， and maybe sports could be values。

 at least if I'm supporting just single sports。 So I could have a fancier structure。

 but this seems sufficient two columns key value for name sport name sport and so forth。

 So how do I put a person's name into that global dictionary Well I use the syntax from week6 registrants bracket name equals sport that associates that value with that key。

 And now what you'll see in that I've added a new route slash registrants and this is where things get interesting if I look at this premade route as you will too。

 is you look at code that's been written for you in the weeks to come。

 Well this sort of invites me to look at registrants HL Y。

 A this registrants htl template is being passed this global dictionary。 How might I use that。 Well。

 let me go into VS codes terminal。 Let me take a look at registrants Html。And interesting。

 we haven't used this Hl much。 I used it super briefly last week。 This is an Hl table。

 It's not gonna look super pretty because I'm not using bootstrap or CS more generally。

 but notice that in the tables head， There's name and sport from left to right in the two columns And then in the table body or T body。

 notice that I have a whole bunch of T R T R T R 1 for every registrant in that ginja loop。

 Each of the cells， the table data have the person's name。

 And then if you go inside of that dictionary and look up the name you get the value thereof。

 So name sport， name sport。 And the route， of course， again。

 is just this render reants Htl by passing in that dictionary。 So what is reants Htl。 It's just this。

 So I think if we go and run this version of the application， we have some nice new features。

 let me go ahead and do flask。 let me kill flask in the other window。

 just so it's not using the same port。 let me do flask run inside of。I am4 so far so good。

 Let me go over to my other tab。 Let me reload so I get the latest HTML。

 I'm gonna go ahead and type in something like David， but select no sport using radio buttons。

 So again， you can only pick one and now not only am I seeing one grumpy cat there。

 It's also telling me at the top that I'm missing the sport conversely if I reload the page。

 don't give my name， but do give the sport and register now you see that I'm missing name and not sport。

 So again， the UI is not very pretty， but it has the building blocks of being much more appropriate。

 Let me now cooperate on both fronts。 David wants to register for soccer register。

 And now notice where I am apparently I got redirected to the registrants route inside of which is this two column table。

 It's not very interesting yet。 So let me go back to the form and let me register Carter。

 for instance， for say basketball register and now there's two of us。

 let me actually go back to the form， let me register Uah for ultimate Frisbee register now there's three of us。

 And again， the CS is。

![](img/9e2f9fda28bc5aece4246768d8d754a6_151.png)

But I do have an Hl table。 And if I right click and view page source， you'll see David Socc。

 Carter basketballball， Julialia Ulimate Frisbee， all is T R T R T R。 So again。

 if you now think about an app like Gmail in your inbox odds are if your inbox is indeed a big table。

 then it's probably T R T R T R T R and Google is rendering all of that Html dynamically based on all of the emails in some variable somewhere。

 Well， let me go back here and see how did that redirect work let's watch this a little more slowly。

 let me go up to the main form at slash let me type in David。

 let me type in select soccer and let me zoom into the URL and notice that when I submit this form。

 even though the action islash register， I'm indeed ending uplash registrrant。

 So how is that actually happening。 let me go back one more time。

 But this time let me open up developer tools let me go to the network tab。

 which recall we played with last week and let me go ahead and do this again so。



![](img/9e2f9fda28bc5aece4246768d8d754a6_153.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_154.png)

David soccer。 and I'm gonna click register。 And now notice interesting。

 Two routes were actually involved。 The first one here is register。

 But notice if I go to headers302 found 302 indicated some kind of redirect。

 What's the redirect going to。 Well， if I look scroll down here at response headers。

 there's a lot of stuff that's not interesting， but location was the one we cared about last week slash registrants。

 Oh， that's why the second request over here at left is actually slash registrants and it is 200 okay because it's all of these basic building blocks from last week and now this where did that redirect come from。

 Well， now you have the ability to do this notice that in my register route。

 the last thing I said we had done was add the name and the value to this global dictionary。

 But the very last thing I did was redirect the user to the slash registrants route。

 What is redirect。 Well， at the very top of this file， notice that I proactively imported not。



![](img/9e2f9fda28bc5aece4246768d8d754a6_156.png)

Just flask， render template and request。 I also imported redirect this time。

 which is a function that comes with flask that automatically issues the H TtP 302 redirect for you without you having to know anything about those numbers or otherwise。

 Let's do one final example before we break for snacks In this final example， Fsh I5。

 let's actually do something with SQL SQL， after all。

 allows us to persist the data because this version here with this global dictionary。

 What's the downside of using this global variable to store all of our registrants。

What's the downside， yeah。Once the shape goes。Exactly。

 so as soon as the server quits or if something goes wrong。

 like maybe the power goes out or we have multiple servers or something like that。

 we'll lose the contents of that dictionary。 And so that's not really good to store data that you care about in the computer's memory alone or Ram。

 You want to store it on disk using something like F open and F right and all of the file I O stuff we talked about。

 But in week 7， recall， we introduced SQL。 So that writes things to disk in a dot Db file。

 So let's actually do that with one final example。 Let me go ahead and close these tabs here。

In my terminal， let me go ahead and close the old version of Frosh I ams and go into Frosh I ams 5 now。

 And in this version， let me show you in app do pi， the following。😊。

It's almost the same in terms of what we're importing from flask。

 but I'm also going to import from C S50's library a SQL function。

 which we used briefly when we wrote code in Python to talk to a SQL light database。

 This is the one example of a C 50 training wheel that we actually do keep on deliberately through the end of the term because it's actually just really annoying to use most thirdpart libraries with SQL in as user friendlyrily away。

 you're welcome to。 But I do think that even though you shouldn't be using get in get string get floatat anymore。

 like the SQL functions is actually pretty darn useful， I would say So how do we use this。

 everything in this file so far is pretty much the same， except for that import。

 including these lines here。 But notice that I am opening up a file called Fro Is do Db。

 And that's a database that's empty initially， But it is in my account。 So actually， let me do this。

 Let me run SQL light 3 on Fro Is D。 Let me increase the size of my terminal， hit enter。

 What can I type to see the structure of this database。😊，sorryrry。Wait what what。Oh， yes， thank you。

 Dot schema should show me。 Okay， It's actually a very simple database， a registrance table with 1，2。

3 columns， an Id for a unique identifier primary key。

 The name of the person and the sport for which theyre registering。

 And presumably the I will be automatically incremented for me。 So let me exit out of that。

 go back to app do pi。 And this line 8 here is just giving me access to that SQL light database and recall that the three slashes are appropriate。

 It's not a typo relative to something like a URL。 Here's my three sports that I want to support。

 Look like my index route is pretty much the same。 So nothing new there。 In fact。

 I'm using that same lesson as before in passing in the whole sports list。 Notice that okay。

 this is interesting。 dereg。 This version is gonna let users sort of bow out of a sport It tends to happen over this course of a semester。

 but we'll come back to that。 But let's look at register now。 register is almost the same。

 even though I do have some comments here。 We're making sure to validate the form。

 But this is where it gets interesting。😊，Now inserting rows into the database to register these registrants Notice that I'm using C50's library to insert into the registrants table into these two columns name and sport these two values。

 and I'm being very careful to use question marks to escape the user's input to avoid injection attacks。

 And then I just redirect the user。 But what's gonna be interesting about this version is this twolash registrants no longer just uses gingja and iterates over a global variable in this version。

 we're selecting all of the registrants and getting back a list of dictionaries。

 And then we're passing that list of dictionaries into the Gingja template called registrants do Hml。

 So just to make clear what's going on there。 let me open up templates and registrants html。

 It's almost the same as before。 notice that I'm using the dot notation this time。

 which Ginja also supports， and it's almost always the same as the square bracket notation。

 So you'll see both in documentation online。 But notice that I have a third。

Column in the registrance table that's a little interesting。

 And this will be the final lesson for Frosh I am a button via which people can deregister themselves like a bow out a fro I am。

 So let's do this open the terminal。 Let's do flask run in version 5 of this here。

 Let me go into my other tab。 close the developer tools go to the slash route。

 and I have a form quite like before。 But now when I register David for soccer and click register。

 notice that it's ugly Ui。 but there's a button next to David to dereg themselves。

 Let's go back to slash let me also register Carter， for instance， for basketball and so forth。

 There's now two buttons。 This now is what really ties together our discussion of SQL and primary keys with the world the world of the web。

 supposeose that there were two Davids in the class， which there surely are two Carter。

 to Uli two of any names。 like we clearly can't rely on first names alone to uniquely identify humans in a room like this。

 So we probably should use like。

![](img/9e2f9fda28bc5aece4246768d8d754a6_158.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_159.png)

Idententifiers， that is like those numbers 1，2，3。 Indeed， if I go into VS code。

 let me open another terminal and make it bigger。 And in my source 9 Fro Is version 5。

 let me run SQL light 3 of Frosh Is do DB。 And sure enough。

 if I do to select star from regstrrant semicolon， I'll see the two of us thus far。

 and we've indeed been automatically been assigned in auto incrementing primary key 1 and2 respectively。

 that's useful now in the web， especially or user interfaces in general。

 If I view this pages' source。

![](img/9e2f9fda28bc5aece4246768d8d754a6_161.png)

Here in my browser， notice that both David and Carter have their own form in a third TD element next to them。

 and that's what gives us this。 But notice that form。

 even though it's an ugly UI is a form that will post to a deregister route a hidden input the name of which is IDd to match the primary key column the value of which is one for me and two for Carter So this is how you kind of stitch together a browser and a server when there's a database involved。

 you just uniquely identify the things you care about by passing numbers around from browser to server and back。

 you might visually show David and soccer and Carter and basketball。

 but the server only needs the unique identifier and that's why we dwelled so much in week 7 on these primary keys and in turn foreign keys So when I go back to this form here and click on deregister。

 this is gonna to submit ID equals one to the deregister route which should。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_163.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_164.png)

This was the only route we didn't look at earlier， let me open up App Pi again。😡。

You'll see that this happens in D register， in the D register route， which only supports post。

 I'm going to get the ID from the form。😡，If there is， in fact。

 an ID and it wasn't missing for some reason， I'm going to execute delete from registrants where IDd equals question mark as a placeholder passing in that number。

 and then I'm just gonna redirect the user back to registergistr so they can see who is still actually registered So if I go back to my browser here and I deregister myself we should see that now that's gone and if I deregister Carter that's now gone。

 And if I indeed go back to VS code， open up my terminal window， make it bigger。

 run select star from registrants now no one is registered for the sport and so we've effectively stitched all of these things together。

 So that's all how we might implement Fro Is just so you've heard the vocabulary。

 what we've implemented is a paradigm known as MVC model view controller where the view is everything the human see like the templates。

 the HTMLl， the CSS， the jascript， the controller is everything that's in app do pi。

 the logic that we've actually been implemented。 But when as soon as you introduce a database especially。

😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_166.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_167.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_168.png)

Even a global dictionary， then you have the M in MVC a model。

 which is where all of your data is stored。 Now you don't have to think about it this way。

 but humans over time realize that wow， most of our web apps follow this similar paradigm so they started thinking about different components of the application as having these different identifiers So there's still a lot more。

 we have not yet considered how when you log into a website the website remembers that you've logged in。

 we've not remembered how you can like keep track of what's inside of someone's shopping cart。

 This is a lot of effort just for a two second joke。

 but let's go with that said for rollups and Ss are certainly's take a 10 minute break。

 we'll see you intend for that and more as we wrap up。



![](img/9e2f9fda28bc5aece4246768d8d754a6_170.png)

All right， we are back and let's consider now how web applications typically work when you actually have to log into them。

 which is like most every web application nowadays somehow or other。

 even though you only log in once at least at the start of the day or the start of the browser tab that you open somehow our other websites are still able to remember that you've logged in already。

 And that's how you see your Gmail inbox or your social media feed or the like。 So here。

 for instance， is a representative login form， this one here for Gmail or for all of Google services and let's consider what actually happens underneath the hood with respect to those virtual envelopes。

 when you do log in with your username and password to a site like this。

 Well typically inside of the virtual envelope that your browser sends to Google servers that is accounts Google co is a request maybe for that form So get hp version2 or whatever version your browser is actually working and some other headers do do do but for the most part。

 that's what we've seen thus far when you then actually log in。



![](img/9e2f9fda28bc5aece4246768d8d754a6_172.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_173.png)

Or rather when you visit that page， hopefully you get back a response from the server saying that everything is okay that is 200 okay。

 and the response that comes back is textlash htl。 So same as last week。

 this is just what's inside of those virtual envelopes back and forth。

 But when you log into a server， it turns out typically what's happening is that the server is unbeknownst to you stamping your hand once it's verified your username and your password to remember that you have logged in in particular。

 what Google server is going send back after you visited that form and submitted that form as by a post is you're gonna get back a response that looks like this。

 it's gonna hopefully say 200 okay it's probably going be a web page written in texttm But in additional HP header that we didn't focus on last week。

 which is this one the set cookie header and the set cookie header specifies yet another one of these key value pairs。

 the name of which can actually be anything depending on the server。

 the value of which is some unique id。FireSo you've all probably heard about cookies in the context of the web。

 You've probably heard that they're not good for your privacy。 and that's generally true。

 but cookies need to exist。 If you want web pages to be or websites to be stateful。

 That is remember a little something about you。 And so session is the name of the session is a word that describes the maintenance of state between a client and a server。

 That is to say if the server is remembering something about you。

 you have a session with that server。 the equivalent really of a shopping cart。 So in fact。

 if you go to Amazon do com or any website via which you can not only log in。

 but add items to a shopping cart or equivalent like that is a session。

 shopping cart is sort of the real worldor equivalent thereof。

 So this set cookie header is essentially a directive from the server to your browser to store this value in the browser's memory somewhere。

 Either for the life of the browser tab or maybe even longer for an hour a day a year depending on the。

Time that's actually set The idea， though， is that because your browser is designed to understand HtTP also just like the server。

 you're on the honor system， your browser， such that the next time you visit Googles same server。

 you should remind the server what cookie was set。 That is to say the browser should send back to the server。

 not set cookie because it's already been set but a cookie header that contains exactly that same value。

 So the metaphor here is kind of like when you go into like maybe a bar or a club or an amusement park and you showed your ticket or you' paid your fees。

 ideally they do something like stamp your hand。 such that the next time you go through the line。

 you don't have to take out your ticket again or your I and prove that you have paid or that you belong there。

 you just show your hand stamp。 And the idea is that the bouncer can trust that if you're presenting this hand stamp And maybe it's the right color in the right picture for that particular day。

 They should just let you in without prompting you again for your ticket or your money。In this case。

 your username and password。 So cookies are a very good thing functionally。

 they are a feature of HttP and they are how servers implement state between themselves and you because after all。

 when you click on a link on a web page or another link on a web page eventually the browser icon stops spinning and it's no longer connected to you typically but so long as the next link you click results in a virtual envelope going from client to server containing this header。

 it's the equivalent of just reminding the server who you are。 This value is generally a big number。

 like a big alphanumeric number， So it's some unique identifier generally speaking cookies do not need to contain your actual username。

 your actual password that's generally frowned upon useful information like your username your password What's in your shopping cart can be stored entirely server side。

 This cookie is just a reminder to the server who you are the problem with cookies though nowadays is that they' are used so often for advertising for tracking and the like。

Why is that？ Well， this is a natural result of that basic primitive If your browser unbenst you is in the habit of just presenting this hand stamp every time it visits a website。

 you're proactively reminding websites who you are again and again。

 at least who you are in the sense of if you lo in now they'll always know who you are even if you're in incognito mode。

 for instance， private mode browsing， your hand is still getting stamped。

 your incognito window is still sending that same unique identifier again and again。

 and so long as you don't log in， they might not know that your Carterter or David。

 but they do know you're the same user or the same person using that browser or rather the same browser visiting the website because that hand stamp is going to be sent again and again。

 but when you clear your cookies， or when you close your incognito window。

 that's like washing your hand and starting fresh， getting a new unique identifier。

 so you appear to be someone different， even though as an aside。

 even if you're in the habit of using incognito mode and clearing your browser tabs and all of that。

With very， very high probability， servers can still track you nowadays based on your IP address。

 of course， which is on the outside of those envelopes based on the particular browser extensions that you have installed based on the various fonts that you have installed there's some crazy high percentage likelihood that a browser can uniquely identify even if you're scrubbing your tracks in this way。

 So just FYi but for today's purposes it all derives from this thing called cookies and this is how they are then set So let's actually use this a little more productively and leverage it in the context of flash flask by using another global variable that comes with Flask that you can import that gives you access to the equivalent of a shopping cart。

 That is to say Flask deals with all of this stuff like setting cookies and checking for cookies and all of the plumbing。

 someone else have solved that for you and flask just hands the content of the shopping cart or the username to you in the context of a variable。

 So let me go over to VS code here and during the break I created a new folder called login if I type LS。

I've got the beginnings of an app Pi and a templates folder。 And in the templates folder。

 I've got the beginnings of a layout Html and an index do Ht。

 just so I don't have to type quite as many characters to get started。

 What I'm going to do with this app though， is let's implement a very simple app that allows the user to log in and demonstrates how a server can remember that you are。

 in fact， logged in。 So let me open up app Pi。 And at the very top of this file， which is otherwise。

 let me shorten this even further。 So it looks as simple as possible。In this app pie。

 let me go ahead and simply add one more import up here called session。

 And that's gonna give me the equivalent of a shopping cart at my disposal。

 But I do need to configure it。 And there's some different ways to configure it。

 But the conventional way or a recommended way here is as follows to run app dot config And then set this configuration variable。

 which is flash specific called session permanent equals false so that this will indeed be treated as a session cookie。

 So as soon as you quit your browser or close your tab typically what's in the session will be deleted。

 This does tend to vary by browser。 Sometimes things might be kept around longer than you expect by default。

 This is going to ensure that essentially the cookie is deleted when you quit the browser。

 I'm also going do this。 app dot config session type is going to equal quote unquote file system。

 This just ensures that the contents of your shopping cart or equivalent are stored in the servers。

In the server's files， not in the cookie itself for privacys sake。 And lastly。

 I'm gonna activate sections on this app by just running this line of code。

 These for today's purposes are sort of copy paststeable lines that just get sessions working in a recommended manner for you here after now we can just use them as we expect。

 as we would hope。 So let me do this let me now open up another file in templates called say index do hml and an index do HTML。

 I'm gonna make a very simple web page that's just gonna check if the user is logged in or not and explain as much if they are。

 So in the body block of index h， which I prepared in advance。

 I'm gonna do this I'm gonna use ginja not to have a loop or a placeholder。

 but an actual conditional like this。 if the user is logged in with a name then go ahead and output inside of and let me do this else here and actually let me proactively do this just you can see the structure。

And if so I've got the beginnings of an if else block in Ginja。

 If there's a name variable in this template， sayy this you are logged in as name period。

 And then let's give the human a link actually no let's do this else。 if you are not logged in。

 You are not logged in。 So super simple English text that's just gonna tell us is the user logged in with a name or are they not。

 And I'm not even going bother with a password， we're gonna keep it simple with just a name to demonstrate。

 Allright， so now what am I gonna to do in my controller。 That is to say app。

 let's go ahead and do this。 let's go ahead and create an app dot route called login。

 So I have a route that just handles logins for the user。

 and I'm going go ahead and do this initially， I'm going to define a function called login。

 And I'm gonna have it return render template of log。Html。

 So this is gonna be a login form by default。 Well， let's create that。

 Let me go into my templates directory。 I'm gonna go ahead and create a new file called login do html and in login do ht Im going to borrow some of this Ht。

 this template from before。 in login do ht I'm going just have a very simple form for logging in again。

 no password per se， just a user's name。 So let's keep it simple as follows form action equals quote unqulash login the method for privacy sake will be post inside of this form。

 Let's just ask the user for an input with autocomplete off by default and autofo on and the name of this field will be name for the human name。

 the placeholder text as before will be quote unquote name capital N and the type of this field will be the default。

 which is just text。 And then lastly， let's have a button。

 the type of which is submit because it's purpose in life is to submit this form。

 And inside of that button will see the words login。 So very similar to greet。

 very similar to register。😊，But we're now just implementing a login form。 Okay。

 now let's go back to app dot Pi。 The only thing login does right now is display this form。

 But let's actually handle the users logging in。 So I'm going to do this。

If the request method equals quote unquote post， and therefore the form was logically submitted。

 let's do this。 Let's use this session variable。 So this session variable that I imported globally here is essentially a dictionary。

 It's an empty dictionary with two columns ready to receive keys and values。

 So if I want to put in someone's name from this login form， I can just tuck it in the session。

 and it's similar in spirit to this thing that we did last time for Frosh I am is giving myself a global dictionary。

 but the problem with that was that as soon as the server quits all of the memory contents are lost。

 and it was also global。 So no matter whether it was me or Carter orullia visiting the same URL。

 there was no distinction among users。 All of us were treated as the same user。

 But what's brilliant about this session variable is that flask。

 because it knows about HttP and set cookie and cookie， it creates the illusion。That whether you。

 the programmer， have one user or a million users， the contents of session are guaranteed to always be unique for me or for Carter or U or whatever human is visiting your code at that moment in time。

 You have the illusion that everyone has their own session object or dictionary or really everyone has their own shopping card。

 just like you would expect on an Amazon dot com。 So let's use this session object like a dictionary。

 Let's do this。 Let's remember the user's name from the form by going in session。

 quote unquote name and set the value of that key equal to request form do get name。

 So whatever is in the form， let's plop it into this global session dictionary to remember the user。

 And you know what， just for user interfaces sake。 Let's do this。

 Let's return a redirect a 302 or whatever to slash。

 like let's just redirect the user back to the homeage to see if they are， in fact。

 logged in at that point。So I think at this point， that's the entirety of my login route。

 If the user has submitted their name via post， store their name in the session and then redirect the user back to the homeage。

 The home page， meanwhile， looks again like this。 If there is a name in this template。

 We're gonna see that person's name else， We're gonna see that they're not logged in。

 So how do we get at that name back to app， let's just assemble these building blocks in my index route。

 I'm gonna do this name equals session dot get quote unquote name So you can treat session similar to request do org。

 similar to request form。 but it's like a more permanent thing。

 at least so long as it's the same human logged in。

 I'm gonna get my name or Carter's name or yourlay name depending on whose browser is visiting my URL at this moment in time。

 Allright， so let's cross my fingers because I wrote a lot of this on the fly let me open my terminal window。

 in my login folder and do flask run。

![](img/9e2f9fda28bc5aece4246768d8d754a6_175.png)

And okay， I screwed up already。 sessionession is not defined。 Did I mean session in lowercase。 No。

 not in this case。 It turns out what I should have done is one more line from flask underscore session import session。

 Why this is another flask library。 It's technically a third party library that other smart people wrote to for flask users to use。

 So I copied and pasted that line from the documentation。 So clearly forgot about it。

 Let me get rid of this register and dictionary， which has nothing to do with this example。

 Let me now open my terminal again and do flask run。 Okay， now we seem to be in good shape。

 No error message apparent。 Let me go back to my URL and reload and notice I am not logged in。

 Now this is not very user friendly because the only way I know I can log in is by going to slash login。

 So let's actually improve the UI in index do H Tml。 If you are not logged in。 Let's do this a。



![](img/9e2f9fda28bc5aece4246768d8d754a6_177.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_178.png)

A A equals slash login。 And let's give them a link to log in。 And otherwise， you know what。

 let's do this。 A Af equals quote unquote slash log out， even though it doesn't exist yet。

 if we want to facilitate the user logging out。 But I think this will be a nicer U I because if I reload now。

 I'm told that I'm not logged in， but there's my new login link shown conditionally。 Well。

 let's do this。 If I click on this， it's super small。

 but in the bottom left hand corner of my browser， I'm seeing the slash login route。

 if I click on that， there is that login form， No password， super simple， just a name。

 I'll type in D V I D。 And now notice if I zoom in here。😊。



![](img/9e2f9fda28bc5aece4246768d8d754a6_180.png)

I'm indeed currently at the slash login route。 But when I log in， I'm gonna be damn it。

 I did make a mistake。4，0，5 method not allowed。 I think we fix this before。

 I can go back into app high。 Which line number do I need to fix。



![](img/9e2f9fda28bc5aece4246768d8d754a6_182.png)

Method was not supported for which route。So， yeah， line 16。

 So I think I need methods equals both of them。 So get so I can display the form and post so I can process the form。

 Let's try this again。 I'm just going to go back。

![](img/9e2f9fda28bc5aece4246768d8d754a6_184.png)

And I'm gonna click type David and click login， and I'll zoom in on the URL log in。

 You are logged in as David。 Now I can log out。 And indeed， if I log out this one's not gonna work。

 I think I'm gonna get a 404 not found。 but that's fixable too。 So let me go back into VS code。

 let me go down to the bottom of the file， and let's add another route for slash log out just get as fine because I'm not posting anything to it。

 I'll define a function called log out just to match the name of the route。

 And you want to know this without reading the documentation。

 But if you want to clear the session and forget the user's name。

 forget the items in their shopping cart， you can do session clear。

 and that will just clear the contents of the session wherever the server is storing them。

 and then I can just return a redirect redirect to， for instance， slash So let's see this in action。

 Let me go back to the browser and hit back。 I'm logged in as David。 But now when I click log out。

 I'm gonna quickly go to。 and I'll show you in the inspector In Network tab。



![](img/9e2f9fda28bc5aece4246768d8d754a6_186.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_187.png)

Let's click on logout。 I indeed end up at log out first， but then I'm redirected to this long URL。

 which is unique to my code space， but the first log out URL redirects me with a 302 until I see a 200。

 and I'm back at the home screen。 So even though that was a bunch of steps for me to do。

 like that is how every website implements the notion of logins and also shopping carts。

 Now you might add some faniness with usernames and passwords and the like。

 maybe two factor authentication and the like， but it all boils down to storing stuff in the session and using those cookie headers in order to keep track of who is who。



![](img/9e2f9fda28bc5aece4246768d8d754a6_189.png)

Any questions on these techniques thus far。No， all right。 How about an actual Amazon。

 If a simplistic one， Let me do this， Let me go back to VS code here。

 Let me close these tabs and let me open up an example that I wrote in advance。

 This one in my source 9 directories store folder。 So the beginnings of an electronic commerce store online。

 Let me just dive in blindly and do flask run for this one。

 and let me go to my browser tab and reload because I'm gonna see my new app now。

 and it's super simple， also ugly， there's no Cs or fancyiness there。 but it's just Hml。

 And this is the earliest version， if you will of Amazon 1。

0 where they just sold books and only these five books for instance。 So what's going on here。

 Well here is how using all of today's like primitives， you can start to infer how websites works。

 So let me view page source。 And even though the Ui is not very pretty。 Let's see what's inside here。

 There's an H1 tag for books just like the title of the page。

 there's a whole bunch of H2s each one of which represents apparently the title of a book。

 and below every title is a unique form。 Every form though。



![](img/9e2f9fda28bc5aece4246768d8d754a6_191.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_192.png)

An action of s cart and everyone submits via post to that cart。 But notice this trick。

 just like the deregistration for Fsh Is。 every one of these forms has a unique I that's hidden but the value for this one is one。

 the value for this one is two， the value for this one is three。 So even though for Fro Is。

 we use it to like deregister people to like opt out of the Frosh Is here you're using it to effectively add items to your cart。

 why well， where is this data coming from。 Let's poke around further。

 I'm gonna open another terminal window in VS code。

 it'll make it bigger I'm gonna go into source 9 and store And if I type Ls。

 you'll see app pi requirements text templates， all of which I predicted would exist。

 there's a temporary folder called Flask underscore session。

 This is where surprise surprise like your sessions are temporarily stored on the server。

 So even if the computer quits or reboots， the files are still there。

 the shopping carts are still there。 but you shouldn't need to go in there and definitely don't change things in。



![](img/9e2f9fda28bc5aece4246768d8d754a6_194.png)

Because things will break， but notice store do Db， which came with my folder today。

 Let me run SQLL 3 of store db do schema to see what's going on in there。

 It's a super simple database table called books with an I column and a title column and that's it。

 Let's see what's inside。 select star from books semicolon not surprisingly there are the five books。

 So again， you see how we're stitching these technologies together using these basic building blocks。

 So let's look now let me quit out of SQL light let me shrink my terminal window and open up app dot pi and there's some comments in here。

 but for the most part， it's the same as before。 I'm importing some of the session stuff so I can keep track of who shopping cart is whose' I'm opening though in this version the database called store Db。

 I'm doing that same stuff copy paste with the session just to make sure that it works。

 And then down here this is where things get really kind of interesting and again。

 representative of like web apps everywhere。 My slash route that is my index has this line of code first。

Variable that gets the return value of the C S 50 function， C 50 execute functions。

 Select star from books return value。 What is that return。

 Well recall that when using the C 50 library and you're using the SQL function。

 this execute function within SQL， you're getting back from Db execute。

 typically a list of dictionaries。 and the keys of those dictionaries represent the columns from the database table。

 So here is a Python list per the square brackets。 every element in this list is a dictionary as per the curly braces not to be confused with ginjas curly braces today and's the Ht files here's one key here's another value and value respectively。

 So again， Db dot execute when using select returns， just a list of dictionaries as simple as that。

 So if I go back to V S code。😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_196.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_197.png)

I have a string of sQL inside of my argument to this Python function that gives me a variable called books。

 which is a list of all of the books in the database。

 so I can certainly pass that in as an argument to render template so that when books do Html is rendered。

 It has access to all those books。 So let me do that。 Let me go into templates， book do Hml。

 And perhaps not surprisingly， Here's that same boilerplate as before。 We extend the layout。

 Here's my body block。 Here's that H1 tag that just says books at the top of the page。

 And here is a Ginja 4 loop in the template。 that is going to output for every book in H2。

 which is smaller， but still bold for the title。 And then inside of that or below that is a form that's identical for every book except notice that I'm very cleverly outputting a unique value for every one of those forms。

 Just relying on those primary keys back and forth back and forth to implement this notion of adding。

😊，And so what is the slash cart method， Let's kind of follow these breadcrumbs and I'm doing this deliberately live。

 like if you were to receive or inherit code like this from a colleague， a friend， a class。

 like you really just kind of follow these breadcrumbs to sort of wrap your mind around what's going on and honestly start with the files that feel the simplest like I did like index dot HTML。

 start with the entry point， So let's see the cart route。😡，It's a little longer。

 but let's walk through it step by step。 So the cart route supports both get and post。

 It looks like with these lines， which I haven't had occasion to use yet。

 I'm just checking if there is no cart in the session， create a cart that's an empty list。

 And I'm doing this logically in this program， because I want to make sure that the cart always exist。

 even if it's empty sort of。Even if it's empty initially。

 like that's what that line of code is essentially doing。 So we can put things in it。

 So if we have submitted something to this cart。 and thus the method is post。

 let's go ahead and grab the idea of the book from request form。

 let's go ahead and make sure that that I is actually valid and it's actually a number。

 So it doesn't evaluate to false。 And if so do this go into the sessions cart。

 which is initially an empty list。 and just like we saw in week 6， append an item to the list。

 append， aend toend。 So we just have a list of book Is。

 And then when you're done with that redirect to the cart route。 Well。

 that's a little weird and almost recursive because the cart route that we're in is redirecting to itself。

 but redirects are always get requests when done like this。

 So even though we ended up here via a post this redirect is gonna send me back via a get to the same route。

 And that is why now outside of the conditional， these final two lines apply here is。Books variable。

😡，I don't want to get all of the books because I'm not showing you the catalog now of Amazon co。

 I'm showing you your shopping cart。 And how do I do this。

 I'm selecting star from books where the idea of the book is in this list of Is。

 and you haven't seen this yet most likely but in the C50 library if you use parentheses in a question mark。

 So placeholder as always， you can then plug a list into that question mark and the library will separate them all via commas like you might have for a past problem set manually we will generate the commas for you。

 So everything is nicely escaped。 And then we're just rendering a template。

 cart do Html passing in those books。 So what's cart do hl。

 That's the last breadcrumb to follow cart do Html。

 and really nothing going on that's that interesting here。 There's an H1 tag at the top。

 There's an ordered list， which is a numbered list just because and then there's this Ginja loop that's outputting a list item or li element for every book showing its。



![](img/9e2f9fda28bc5aece4246768d8d754a6_199.png)

色ろ？So if I go back to the store here。😡，And actually start adding things to the cart。 there。

 I've added that to the cart。 Allright， Just one book。 Let's jump to the last one。

 So the hitchhiker's Guide to the galaxy。 How about mostly harmless。 click that。

 Now there's two items in the shopping cart。 Let me go back。

 There's now three items in the shopping cart and so forth。 But if you。

 if I were to make this URL public， It's currently private by default。

 So not everyone on the Internet can visit it at the same time。

 If I were to make this public in any one of you were to open it on your phone or laptop。

 You would see an empty cart because you would have a different hand stampamp， a different cookie。

 But the server would be keeping track of all of our shopping carts in if you will。

 that flask session folder。 Just all sort of happens automatically。



![](img/9e2f9fda28bc5aece4246768d8d754a6_201.png)

Okay， so that then is how Amazon dot com is implemented。Questions。Yeah。' say if you。杭州首份都在。毕金确。呃，张正。

我社费东。A really good question。 How does the browser， How does the server know to give you a brand new session the first time you visit a website When you visit something dot com for the first time。

 your browser will not send a cookie header。 There will be no cookie colon session equals value。

 It's just gonna be blank。 It's gonna be like my showing you my other hand that has no ink on it。

 Then the server will know， if you didn't send me a cookie。

 I'm gonna set one for you by stamping your hand with the set cookie header。

 It's just gonna generate typically a really big random number that's different for you for me for you to keep track of us individually。

So that's all。 It would just happen by default。 And flask makes all of that happen because we have not only imported these lines at the top。

 We have also used these configuration lines， too， to ensure that the server does exactly what I just described。

 If you had to do all that manually， honestly would be so annoying to make web applications because you do copy paste all of the time。

 This is still some copy paste， but it's way less than implementing all of this cookie stuff on your own。

Alright， how about a final set of examples that allow us to escalate quickly to a larger data set and make this more like an actual Amazon do com or maybe an actual IMDB do com。

 And we'll do this by way of a tour of some in examples rather than do all of these here from scratch。

 So I'm going go into my terminal window。 I'm gonna hit control C to kill the previous version of the store。

 And I'm gonna go into shows version 0 initially， which has our old friend shows do Db from our SQL lecture。

 which has all of the latest TV shows from IMDB using the same schema as then。 And there's an app pi。

 There's a requirements text。 and there's a templates folder just as predicted because we're still using flask。

 So let's go ahead and take a look at what's going on inside of this file app do pi as our entry point。

 Allright， so I see some pretty familiar imports now。 I see shows Db using the SQL library。

 So nothing too interesting there。 The index route is super。😊，Simple。

 it's just rendering index do H Tml。 And then there's a search route。

 So this is kind of an amalgam of Google do com and IMDB com。

 I want to implement a relatively simple search website for IMDB， just a search box。

 Well we can kind of preemptively infer how this is gonna work。

 a shows variable is being set to the return value of Db execute where I'm executing select star from shows where the title of the show equals this question mark And what am I plugging in。

 just like Google， I'm plugging in the value of the Q attribute from the URL apparently then I'm rendering a template called searchml and I'm passing in those shows as a list of Python dictionaries。

 So like that's it like's only that's the entirety of the backend logic here。 It's a search engine。

 So what might I want to do next。 my mind goes to index Hl。

 Let's just see what the template looks like so I can wrap my mind around index HtMl。

 Okay it's pretty darn simple。 It's just a form that has an action of search。

 which aligns with the route we just saw。😊，I get it's got an autocomplet input called Q as expected and a button called search。

 So not really that stimulating there versus past examples we've done。 Let me go into search do Htl。

 which is the other template in here。 So let me open my terminal and do code of template search H Tml close the terminal。

 Okay， this is kind of like the bookstore too， it's just iterating over the shows output list item list item list item。

 but I'm using anor list， instead of ordered。 So there's not that much to this application to enabling search。

 but recall that two weeks ago， when we introduced Htl and C and jascript。

 we completely punted to the actual Google do co like today， we are， if you will。

 Google do com or IMDB do com。 So let's go into the terminal window， do flask run。

 I'll go back into my browser and reload。 So we no longer see the store。 We now see IMDB。

 And it's this pretty simple search box。 Let me search for the office as in the past。

 click search and notice two things at the top。😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_203.png)

Of the URL is question mark Q equals the plus office。

 the plus is own way of encoding spaces and URL so that it's just one long string。

 but that's conventional。 And then there's a lot of offices。 But why is this， well。

 there's like the American one， the UK1。 There's some prior ones that weren't nearly as popular is either。

 So there's a bunch of offices in there。 But you know。

 we could probably we can kind of tie our ideas together here。 Let me open another terminal。

 make it bigger， go into source 9 shows 0 SQL light 3 of shows do Db do schema。 Oh yeah。

 there's a lot of data in this this database， let's do dot schema shows specifically Okay so we have the year of every show。

 So this just means I can kind of play around now with the intersection of SQL and Python as follows。

 let me go back to how about search do search do Html。 And instead of just showing the title。

 why don't I do something like curly curly brace show quote unquote year。 curly curly brace because。

😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_205.png)

Well， every element in this list is a dictionary。 So I have access to all of those SQL columns。

 So let me reload。 And now you see， oh， that's why there's so many offices。

 They're each from different years。 So every piece of data you have access in SQL。

 you have access to in Python， you have access to an H by just knowing how to stitch these ideas together。

 Alright， so what's not so good about this。 Well， if I go back to the search box and I search for just office enter。



![](img/9e2f9fda28bc5aece4246768d8d754a6_207.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_208.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_209.png)

Like， there's apparently no show called literally office， at least cap lowercase O。

 Let me try a little more specific office as someone might type。 Okay。

 so there's one version of office， but's not the office from 2013。

 But what if I want to kind have more of a wild card search。 we can borrow these ideas too。

 So let me go back into V S code here in my app pi。 And I think here。

 instead of using equal what was the keyword， Yes， so we can do like， for instance。

 but this we have to be a little careful of we don't want resort to like a python F string where we plug in values with percent signs and the like。

 So this is a little bit tricky， but it's worth knowing that if you want to do wild card searches safely。

 we still should distrust the user's input。 So what I'm gonna do is this。

 even though it's gonna look a little cryptic。 I'm gonna just do question mark。

 But instead of passing in request do org dotet of Q first let's tuck this in a variable。

 So the code is a little more。

![](img/9e2f9fda28bc5aece4246768d8d754a6_211.png)

Q equals that， even though that's not changing anything fundamentally。 Let's do this。

 Let's put my percent sign here， concateate Q with that and then put another percent sign here。

 So that this whole string after joining and joining three things together gets plugged into the question mark and therefore escaped you should not use an F string for this thing you should always use the question placeholder as we keep preaching。

 Allright， So now that I've done this， I think my search functionality just got way better why So if I go back to the form And I'll reload to clear everything。

 I'll zoom in a little bit。 Let's type in just office in lowercase with no the。

 And I think I should get now every TV show that has office I and it's somewhere even if it's office sir so that might not be quite what we want。

 But there's indeed a much broader match here。 So more like the IMDB do co But now it's kind of a design decision。

 do you want to be really nitpicking and require users to type in。



![](img/9e2f9fda28bc5aece4246768d8d754a6_213.png)

Office， do you want it to be capitalized。 This now becomes more of a user interface or design decision。

 not so much code。 All right， well， let's make one tweak here。

 that's representative all the more of like today's modern apps It turns out that this approach of generating new HTMLl。

 every time a user submits input or visits a new URL is kind of increasingly dated。

 whereby every URL is sort of unique， as opposed to apps being much more interactive。

 So it turns out there's this technique in general， whereby in the world of the web。

 where you use something called Ajax， which used to stand for asynchronous jascript and Xml nowadays。

 it just refers to using jascript to get more data from the server。

 So the user's URL doesn't even change and the whole browser screen doesn't flash as though the whole page is being reloaded。

 So this is gonna look a little more cryptic。 But let me go ahead and sort of show you。😊。



![](img/9e2f9fda28bc5aece4246768d8d754a6_215.png)

An alternative to this relatively easy approach， like a lot of today might be feeling like a lot。

 It's about to feel more like a lot， but not in a way that you need to replicate just to give you a taste of what more modern web apps are doing。

 I'm going to close these two tabs。 I'm going go ahead and exit out of SQL lights。

 I'm going to kill my previous version of flask。 and I'm going go and just shows version 2 now。

 And in shows2， I'm going to do flask run。😊，So the app is running。

 I'm gonna go back to my URL here and just reload and notice I've gotten rid of the search button altogether。

 Min aesthetic detail。 But what I like about this now is that if I search for like O F I C you're seeing the beginnings of autocomp。

 which is kind of everywhere。 but you can't implement autocomple。

 if you have to reload the whole page reload the whole page why。

 if nothing else the user is gonna see a big flash of white as the whole page redraws itself。

 which is not what we're used to if I start over F notice the URL is not changing nor is the whole page flickering just the U is getting。

 And if I really go， there it is officer now I have only this many bullets on the screen。

 There's no more below the break。 So how can I do this。 Well。

 let's try to infer a little bit here and demonstrative of how you can kind of infer how thirdpart websites are working if you want to if you want to sort mimic their behavior just learn better how they work。

 So let me do this let me open。

![](img/9e2f9fda28bc5aece4246768d8d754a6_217.png)

Developer tools。Let me open the network tab and let me search for O and watch what happens in my network tab。

 even though the URL of the page is not changing， O。😡。

Apparently an HTTP request was sent from my browser to this URL。

 which is essentially representing slash search question mark Q equals O。

 notice that the response was 200 and what is in that response。 Well let me click on that row。

 let me click on response and very interestingly notice what came back it's not a whole web page it's just a bunch of li elements which you can kind of infer are probably the ones that are getting like snuck into the page dynamically So if I go back to the top there's no UL here。

 it's just a bunch of lis and watch what happens this time。 let me close that panel。

 let me search for OF without even hitting enter here we go O F now there's a second request and if I zoom in there it is Q now equals OF。

 if I click on that and zoom out you'll see a whole bunch of lis but let me claim there's fewer of them now because fewer strings match OF and if I finally type in like office let alone the office notice now。

😡，bottom of this， every time you're doing an autocomplete， it's sending an HP request， HP request。

 HP request。 back in my day， you'd have to click submit the whole page would reload and you'd see the list again and again。

 This is sort of more modern。 And this is an example indeed of what's called Ajax Asynchronous jascript that's sort of getting you more data and slipping it into your existing web page。

 So how does this work。 Let me go to VS code here。

![](img/9e2f9fda28bc5aece4246768d8d754a6_219.png)

Let me open up a new terminal。 Let me go into source9 shows2。 and let me open up， for instance。

 the index template， which is the entry point。 everything at the top is sort of boring。

 Here's the head of the page。 Here's the input。 I didn't even bother with the whole form because I'm not even submitting a whole form。

 So I don't need an action or a method or anything like that。

 I'm just using it as a dumb input box only but notice that it is indeed an input of type search here now is an empty U initially So this is why when you visit the page。

 you see a text box， but no no bullets because the list is empty。 and in fact， watch this。

 if I click on elements in the developer tools， click on body， expand the body， there is the U。

 if I zoom in， there's nothing inside of it。 Yes， that's why we see no bullet。

 but if I go back to the template， here's some jascript code， which we haven't spent much time on。

 but you can start to wrap your mind around this line by line as follows me。



![](img/9e2f9fda28bc5aece4246768d8d754a6_221.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_222.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_223.png)

A variable called input set it equal to the element from the dom。

 the tree in the computer's memory for the input element。

 So that rectangle from our pictures from last week。

 Then listen to that input for the input event I showed briefly last week a list of like dragging and clicking and mouse up and mouse down and key up and key down and input just means generally inputting into a text box。

 here I'm calling a function。 it's an asynchronous function in the sense that it's gonna get back to me eventually if the server is slow。

 it might take a moment or two。 But inside of this function， give me a variable called response。

 go ahead and fetch the URL whose path or route is slash search question mark Q equals and then concatenate onto that whatever the user's input is。

 that is the value of that input。 then create a variable called shows go into that response from the server and get its text value。

So we're not gonna spend much time on this， but fetch is a function that comes with browsers today in jascript that lets you make an HTTP request。

 fetch more content from the server， and you essentially pass it in the URL that you want to fetch or get this function here。

 response text just grabs the text from that response。

 which means if I go to the network tab and I type in O as before。

 and I click this response do text is all of this stuff that we manually looked at earlier。

 So you're just getting all of the text that came back from the server that happened to be lis Lastly。

 go into the document。 the Dom select the U element go into its inner Hm and change the inner Hl to be that text Aka shows And so what's happening here and watch this now when I let's reload the page。



![](img/9e2f9fda28bc5aece4246768d8d754a6_225.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_226.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_227.png)

Let me show you the elements tab， Let me highlight and zoom in on the UL element in the bottom of the screen。

 Nothing's there yet， but watch as soon as I type O。

 and I get back all of those lis and they get crammed into the inner HTML of the UL。

 watch the U as I type O， there's now more stuff there and indeed。

 if I expand it there or all of the lis， that is the inner HTMLtl that just got automatically populated。

 And if I type in more officer notice that if I scroll down， there's only so many of them。

 And if I just type in nonsense like notice it's back to zero because there's no text coming back from the server。

😡。

![](img/9e2f9fda28bc5aece4246768d8d754a6_229.png)

This then is an example of the beginning of an API。 and I've used this term over time。

 but an API is an application programming interface。

 and it's a standardized way generally of getting data from someone else's server or server into your application。

 Now in this contrived scenario， I am both the Web developer and I'm the author of the API。

 but they're sort of implementing they're being implemented in the same application but you could imagine actually  querying Amazon com for actual books and actual prices and actual photographs thereof from their servers instead of your own and so they might very well send to your server those kinds of responses by just sending you a whole bunch of text that again might just look like all of these lis。

 but the lis is kind of a sloppy way of sending information nowadays it's not common to use HTML nor something called XMl to send back your data rather it's more common to get back something called JSO jascript objectject notation and odds are for your final project if you do any。



![](img/9e2f9fda28bc5aece4246768d8d754a6_231.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_232.png)

With an API， you'll encounter this in the real world。 And Json looks very。

 very similar to what a dictionary and a list looks like in Python。

 The syntax is almost the same as you've seen， however。

 in the world of Json jascript object notation。 you have to use double quotes around your strings。

 you cannot use single quotes and generally， it might look like this。 So here， for instance。

 is a response from a more modern version of a server。

 that's not sending back tags and like a messy bunch of Hl。

 It's sending back something that's more machine readable。 So this text ugly as it is。

 it's much easier for Json parser， like a function to read because it's all standard。

 It's all square bracket， It's currently braces quotes， Cols and all that。

 And even though it looks like a mess on the screen， it's very standardized， unlike Li tags。

 which who knows what might come back in those aesthetically。 Since there's so many Hl tags。

 not to mention CS。 So let's make a change here。 Let me go back to V S code here。😊。

Let me close this tab and quit out of this version of my application and let me show one final version of shows by going into showss version 3。

 And in this version， I'm gonna go ahead and do this。 I'm gonna open up app do pi。 and an app do pi。

 I'm gonna import one more function from the flask framework called Jsonify。

 which is not necessarily a technical term。 It just means turn something into Json。

 So what does that mean。 Well notice that down here， I have a search route that looks like this。

 But before we look at that， which is going end with this spoiler like Jsonify。

 let me actually do this。 let me open up also from shows's version2 the previous version of this。

 which looked like this here， This was the app the search route from the previous example。

 Here's how I got Q。 Here's how again， I did the escaping of the user's input with the wild card。

 but notice that I also did this。 If the user got back no results， then I just gave it an empty list。

😊，Instead。But let me show you two from last time， search do Htm looked like this and shows2 in template shows dot Html。

 whoops。Search do H TML。 What you'll see here is the very simple template that generated all of that text。

 all of those lis just again and again and again。 So we're gonna get rid of that template in this third and final version here。

 So if I go into shows3 notice I'm doing the same code as before I'm building up a Python list of shows that results from that SQL query。

 But instead of passing it into any template， I'm just jasonifying that text。

 What that means is that when I'm essentially going send from the server to the browser is literally something that looks like this here on the screen。

 So if I go back to VS code here and run flask run in this final version and I go over to my other tab here and reload。

 I have the same responses before， and it's actually gonna work the same like office is going still work the same。

 But if I undo that and go to inspect and go to my network tab here and now search for0。

 same paradigm as before therelash search。😊。

![](img/9e2f9fda28bc5aece4246768d8d754a6_234.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_235.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_236.png)

Question mark Q equals0。 Let's click on that。 But notice。

 and let me make this even bigger on the screen。 this even though it looks more verbose。

 and it is it's way more standardized。 And this is the quote unquote right way to send data over the Internet when you want two pieces of software to generate and consume it respectively here now。

 we have not only just the titles of the shows。 But I've even been generous and sent the number of episodes。

 the unique I， the title of the year。 I've essentially sent the entire SQL database in a standard portable textual format that my code can now use。

 So when you think about most any modern application。

 we come back to Gmail When you access something like Gmail in your browser and you are waiting and waiting and waiting in a new email comes in what has happened tonight。

 for instance， open up the inspector， watch the network tab and odds are every few seconds。

 every few minutes。 you'll see some kind of response coming from the server。 maybe Json。

 maybe some other format containing your email， including at least its subject line。

 because that's what's adding more and more Hl to。

![](img/9e2f9fda28bc5aece4246768d8d754a6_238.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_239.png)

Browser indeed， if you open up the elements tab and just watch it in the most sort of watching paint dry kind situation。

 you'll see probably more and more emails appear in the underlying Dom or document object model inside of the browser So I can't stress enough that even though we've spent just a few weeks on SQL and then HCs in JavaScript and now flashask together like that is how the web works。

 that is how all of today's modern apps work and hopefully YouTube with your final projects。

 That's it for today。 we will see you one last time next week for the end of CSFD。😡。



![](img/9e2f9fda28bc5aece4246768d8d754a6_241.png)
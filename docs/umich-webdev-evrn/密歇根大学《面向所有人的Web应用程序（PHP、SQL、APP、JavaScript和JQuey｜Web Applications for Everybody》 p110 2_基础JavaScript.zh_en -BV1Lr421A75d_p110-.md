# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p110 2_基础JavaScript.zh_en -BV1Lr421A75d_p110-

![](img/81dcd7e18c112898a77e5ef0db7c26e9_0.png)

![](img/81dcd7e18c112898a77e5ef0db7c26e9_1.png)

So like in any programming language we can make syntax errors Now it's a little different。

 and so you'll notice that one of the things I have had to bug you about in every programming language like in PP。

 you had to set the error error display message in the PPI and I file。

 you had to set the error mode on your PO so that you would see the errors。

 the problem with having errors is you got to see them as a developer。

And so jascript is kind of weird。 and it runs in the browser as a sort of a side effect of loading a web page。

 and the person。Looking at the browser is usually not the developer。

 and so the default is that the browsers just hide all of the errors。

Sometimes I'll put a little red mark in the lower right hand corner or something or a question mark or something。

But you don't see it。 And the reason is， is the person who is standing looking at the browser is not likely the person who wrote the code in the first place。

 and they're probably not a programmer， they're the end user of your application。

And so what happens is it detects an error and it stops the script execution。

 but it doesn't notify you， there's no error log like we have in PhHP， et cetera， et cetera。

 et cetera， so it's important to know how when you're writing software and doing development。

 how you can catch and notice errors because you're going make mistakes as you're developing a JavaScript。

So this is an example of some broken JavaScript code。So we have two script tags。Two script tags。

And this script tag has a mistake。 It has a single quote ending a single quotes and double quotes are equivalent in jascript。

 which is actually quite nice。 And so that's a broken tag。 And so what happens is。

 is that it comes in here and it starts the script。 and it's running it。 But this is a syntax error。

 So it doesn't run。 and it blows up。 And what it does。

 is it it doesn't run any of the remaining script code。 So it never says I am good。

 It basically gets out of that script block。So that's what happens。

 And there's tries and accepts and things like that in jascript。 and we can talk about that。

 But in this case， we don't have a try or an accept。 And so it just stops that block。

 So this is one block of jascript， this is another jascript。

 What it doesn't do is it doesn't stop all jascript processing。 It just sort of blows up this block。

 and so even though it comes down here and gets the paragraph， then this runs。

 and this is good jascript and it runs。 And so that's why we see this alert second time is that hope springs eternal in jascript And when it sees a new script tag it's like well。

 I'll run this。 but it doesn't bother as soon as it sees a single error。 it doesn't go any further。

 And sometimes this is library code and it's defining functions and stuff and you make a syntaxt error and then all the rest of the functions in the file are don't exist。

 So you have to realize that a single error and a jascript either a jascript file or between a script and N script tag one error sort of throws everything after that error away。

 you got to get used to that doesn't run。Any more after that。But we have to see the error。

 And like I said， the end user is the one looking at the browser。 And so we need to be able to say。

 hey， where's this error at。 And so we need to make it so that programmers can see errors。

 but users are not sort of they're not thrown in the user face。 Now。

 the user notices the draft stops working， but maybe it's not critical or something like that。 So。

 and so we， we as developers， though we want to see it。 So we always have to turn something on。

 What's super convenient these days。 Thankly， is that the browsers have a debugger mode in it。

 a developer mode in it that shows you this stuff。 And so you can see the errors。



![](img/81dcd7e18c112898a77e5ef0db7c26e9_3.png)

By going into the developer mode。 Now， sometimes you got to go how to enable developer mode on Chrome or how to enable developer mode on Firefox。

 because sometimes they don't even put the menus up for how to do developer mode。

 So that's the first thing you've got to figure out is how to get the developer mode。

 But once you get into developer mode， you basically get a split screen and you can actually pull this out and make it on two screens or whatever。

 And there's a lot of ways that you can show this。 I think this little thing moves it out。

But under console， you can see all the error messages and you see the fact that there is an error message。

 So some developers will actually you know make this like the bottom part。

 So you have a screen and like the bottom part， they just leave the console all the time。

 And sometimes I write I'm running other people's code and I just watch the console for a little kind of Easter eggs。

 One time I saw a console where a company was asking you to apply for a job So if you're going to their website and you happen to be watching the console that would go like。

 hey， apply for a job because you can actually send log messages。

 which will soon see out to this console。Now， it's usually pretty effective。

 sometimes you do have to refresh the page， but if it sort of knows that you're in developer mode and it finds something。

 you can click on this actual link and it takes you right in the source code。

 So you do not have to go view source fool around it knows all the source code it knows what line you're in Now some of these things look really ugly there's this little thing that if you end up with this what's called Minified jascript it's all one big long line with crappy stuff you can actually make it pretty so you can read it but this is taking you right to line3 of the exact code that was broken telling you what's wrong。

 you can kind of hover over it unc syntax error so that you know that's how you debug it。

 And so you'll find increasingly as you're writing jascript。

 you'll just have this split screen on all the time。 and you'll do things like clear the logs。

 hit the refresh button and see what errors you've got and now you're debugging your jascript and you using the browser do it and the fact that there's a debugger right in the browser is one of the reasons people kind of think the jascript is a good first。

Programming language， but this whole thing is actually monstrously complex for absolutely beginning users and I think it's cognitive overload。

 but enough enough of me talking about whether or not I love Python it's the first programming language。

 and then PhP and then SQL and now ja because ja is an awesome language I talked about the alert message but the alert message is really not very practical because it stops everything I use alert when everything is like nothing makes sense and I'm like I'm sticking an alert in here I just got like stop right now because sometimes I don't know what order things are happening in and so an alert will be like stop and it's not like it goes flying somewhere else you can see okay this alert is happening right here。



![](img/81dcd7e18c112898a77e5ef0db7c26e9_5.png)

![](img/81dcd7e18c112898a77e5ef0db7c26e9_6.png)

![](img/81dcd7e18c112898a77e5ef0db7c26e9_7.png)

But a far more useful thing to do is console log and console。 log。

 you can kind of look up all the different functions of console， but console。

 log basically puts a string。 you can also log variables and see the contents of those variables and it's really quite nice And so you can see the console log is these are messages that you're putting out And if you look at this one you'll see that the first log appears then the dialog box stops。

 the second one does not happen because the dialog is suspended you know and away you go。

 but the nice thing about this。 and I actually in production systems that you'll use in mind。

 you will sometimes see log messages coming out because I'll be debug him like I I'll say they'll say the iframe didn't resize and I'm like。

 oh pop up to developer console and look in the log and I'm like。

 oh why is that What's that red error message screenshot that for me and show it to me And so you know I will leave stuff in my running applications sometimes nothing that's like revealing secure information。



![](img/81dcd7e18c112898a77e5ef0db7c26e9_9.png)

Of nothing that JavaScript does is really secure because like cookies。

 it's in the browser so the user can look at it， a smart user can watch the JavaScript running。

 can look at the JavaScript can change the JavaScript so you can't trust the JavaScript even if you wrote it。

 the thing that's running in the browser may or may not be your code。Okay， so in older browsers。

 sometimes the console was only there if the debugger was running。

 I don't know which browsers did it， and I don't what versions the browser did it。

 but if I'm leaving stuff in production， I will tend to say this。

 So Windlet console will retrieve true or false without blowing up。And then and console do log。

 And so if this is false， then this doesn't run。 And if this is true， this does run。

 and it's a way to avoid getting a syntax error inside of the debugging statement。

Another way to do this， and you can sort of ask in stack overflow like what about console do I really。

 you know as console always there and there's a whole bunch of other things And so this is really for older browsers。

 but I'm still a little conservative in my applications that I write you probably won't bother you'll just say console。

 log and you'll run in Chrome and it will just be fine and so you'll be you'll be okay。

There is a debugger。 If you get into a source view。

 you can find your way in a source view and you can click on a line of jascript to set the breakpoint。

 Sometimes you sort of have to be in source view and hit refresh one time because or if you hit the break point then you had to hit refresh unless you're in the pause tobugger because the page is already done you hit refresh the page is done and you're looking at this line of code。

 well that code execute a while ago， then you can set a break point and then refresh and the next request response cycle is when you're going to see it。

 So sometimes to activate the debugger， you have to refresh the page after you set a break point。

 And so at some point you're sort of finding your way around in some source code you find the code and then you hit the button in this little flag this little blue flag shows up to say that you are in the debugger that you set a break point and then you hit refresh and then it knows it remembers and it says oh。

 I'll stop here。 So now what it's basically saying as it stopped right here in the debugger and then you press this to continue but you can look around variable。



![](img/81dcd7e18c112898a77e5ef0db7c26e9_11.png)

And other kinds of things。 And that's really quite nice， but it's also。

I'm always having trouble finding my way around， so it's not。

 I don't think it's really great for beginners， but once you get good at it， it's a really powerful。

 powerful environment to figure out what's going wrong with your JavaScript。



![](img/81dcd7e18c112898a77e5ef0db7c26e9_13.png)

So up next， we're going to talk about JavaScript kind of as a programming language。



![](img/81dcd7e18c112898a77e5ef0db7c26e9_15.png)
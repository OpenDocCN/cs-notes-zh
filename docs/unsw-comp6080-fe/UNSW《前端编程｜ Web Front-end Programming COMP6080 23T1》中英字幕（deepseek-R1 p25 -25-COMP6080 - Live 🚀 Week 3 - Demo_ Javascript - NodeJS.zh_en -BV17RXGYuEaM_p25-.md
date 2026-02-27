# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p25 -25-COMP6080 - Live 🚀 Week 3 - Demo_ Javascript - NodeJS.zh_en -BV17RXGYuEaM_p25-

![](img/9b2334de6b7bce29a33363e7b68f3198_0.png)

Hi， everyone。It's nice to see you all today。 Thank you for coming to our first fully online lecture。

 I'm sorry I can't be there with you in person today。

 I'm looking forward to being back in person next week。 I'm travelling for work right now。

 I'm in North America currently so it's pretty late here so apologies if my energy levels aren't。😊。

The same as maybe they would be in person。And I've also just done a little different thing with the screen today。

 So instead of sharing my whole screen， I've actually got three separate windows being shared。

 which means that。I can kind of change look at YouTube comments and stuff without taking away from the core。

Core visuals。 So I like some feedback if maybe you find this easier because we could try this with the。

 the live lecture too， potentially in person just because it can。

 I know sometimes the screen changing can be kind of annoying。

We have not a huge amount of people here tonight just 36， which is okay because today's lecture is。

It probably the easiest live lecture in the course。

And the background I've given that for that is that。How we teach things in this course is that。

 you know， in week one we do CSS， HTML and CSS， and then in week two we come along and we learn a little bit of JavaScript。

And I'll just show you that here， so in week two we go and we learn the real basics of JavaScript。

 which is what we're covering today。

![](img/9b2334de6b7bce29a33363e7b68f3198_2.png)

These few things here。And the reasons we do that are to set you up for week three。

 which are the rest of the lectures you should watch this week。

Where we talk about jascript in the web now， a really important lecture that you should watch。

 like if you haven't watched it， it's like I'd suggest like literally pause this video and go watch it is this jascript ecosystem lecture And the quick recap of that。

 whether you've watched it or not is that jascript is a language and historically it was used to run in the web browser on a client side with HTML and CSS。

 but it also runs on servers or computers through something called No JS。

 So there's two different kind of existences of Javascript and。Today。

 we're going to be talking about the no Js part。 Now。

 the funny thing about this is understanding this。 The reason we do this is because using no Js。

 using jascript in the terminal is。Is easy。 That's why we like to start with it because it's really digestible but also it's necessary for later weeks because what we actually do with the more advanced stuff later while it's still front end。

 it's actually kind of powered by the terminal。 So it's a little bit confusing that way。 But again。

 we do this because it's relatively easy。😊，What this means is that what you learn today will help you understand JavaScript and a few things for like week seven。

 but it won't have a lot of immediate impact and help on your assignment 2 or your assignment 3。

The stuff that's really going to help you with assignment2 or assignment 3 is going to be this content here I mention this in the notice it's going to be all of the Web JS Dom events。

 JavaScript closures forms and local storage Some of those lectures are done by me some of those lectures are done by En exam at Canva these are the ones you need over here for your assignment too Now remember go watch those lectures go try and do assignment too if you get stuck go do a couple of tutorial questions these lectures are also pivotal for assignment3。

Now， what we're going to be doing next Monday is a big， big demo。 We're going have a big fun lecture。

 It's going to be a lot more。 It's going to be much longer than the lecture tonight。

 where we focus on。😊，Demoing everything that's happened that week and we give you a chance to start your next assignment。

 assignment three。I know that feels like a lot sometimes like a lot of things being thrown around。

 but at the end of the day we've kind of broken the course up into smaller pieces which makes it。

Digestible and smaller chunks， so there's the context now。



![](img/9b2334de6b7bce29a33363e7b68f3198_4.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_5.png)

If。Yeah and Vincent says if this lecture is going to be one of the easier ones。

 we we'll be going for the full two hours， I don't think so no that I just don't see why we talk for two hours generally there's like a minimum amount like if I just went as fast as I could and there was no questions a lecture like this is maybe 4045 minutes with questions that's kind of as long as it's going to be but I'd expect it won't go too far past the hour mark and again there are some lectures we have in this course that run long and there are some weeks that have lots of prerecord so I try not to overwhelm everyone with live lectures of course。

 but we can always go as long as people want。I'm in America， yes， it's not super relevant。

 so I probably won't answer too many questions about that。

 but it sounds fancier than it is when I say travelling for work it makes me sound like some big high flyer。

 but I don't really travel for work， this is a one off so there's nothing exciting happening。At all。

 so appreciate your your second hand excitement for me， some of you。

 The last disclaimer here is that。😊，嗯。Two thirds of you are undergrads， one third of your postgrads。

The JavaScriptscript material that we cover here is。If you're an undergrad。

 it's fairly simple because you're already done this course，1531 that I've probably run on Python。

 If you're a 1531 student who has done it in the last two terms where we actually swapped 1531 to jascript。

 I would nearly recommend that you just skip this lecture and go do other things with your life。

 like go watch other lectures or I don't know， go play with your dog or something。

 I don't think there's gonna to be anything new in this。

 so if you're a 1531 student who's done it in 22t2 or 22t3 you could probably just stop right now。

 if you're a1531 student who did it a while ago， maybe it's a good refresher because basically all the principles we talk about today are the same things you learned in Python we're just going to be doing it with a different language and different tools and if you're a postgrad student you're probably in a similar boat where there's a good chance you know Python but this might be a good opportunity to reframe some of that knowledge in the context of Java。

So that's kind of what we're going to be doing today。Should be pretty okay。Now。嗯。What we've got here。

Today is our demonstration of nodeodegis This is truly just there was a couple of lectures on well a basic lecture on JavaScript syntax。

 which was like an hour and then there was a lecture that talked about the JavaScript ecosystem and then there was a lecture that talked about the node package manager which again came straight from a recent version of 1531 right。

So some of this for some of you is recap for others it's new content all we're going to be doing today is demonstrating the use of no JS。

 which is again JavaScript run on the terminal and we're just going to be doing that by doing two quick demos together。

 which means that we have two problems that we'd like to try and solve。



![](img/9b2334de6b7bce29a33363e7b68f3198_7.png)

Now remind you again。These demos are help you get comfortable with JavaScript the language。Okay。

That's their main purpose。嗯。Just a recap。Because I'm getting a few more questions just before we get into it。

Sandy says， weren't the last three videos shot in 22 T3 I saw from the PDFs URLs that you're using in those recordings。

I don't know what last three videos you're referring to are but。

Some of the jascript material has been taken from 1，5，3，1。 That's not because I stole it。

 That's basically because I lecture both courses a lot of the time。

 So there's some overlapping content。 So I just。I have one way of teaching it so we just reuse it there's nothing too exciting about that And then lastly just a recap I won't probably answer the same question again。

 Reuben says sorry miss the beginning did you mention we need this week's content for assignment too so final recap on this right？



![](img/9b2334de6b7bce29a33363e7b68f3198_9.png)

For。Let's look at it All of this stuff in week 1 and this little bit in week  two is necessary for assignment one。

These three lectures here are not super critical for any assignment soon。

 they're just really important background understanding that really helps in week three。

Same with the demo today。The prerecors for week three are super useful for assignment2。

 which is what you're meant to be doing this week。 So if you're like man Hayden。

 I don't care just I got I got one hour I need to focus， go watch the ones I'm highlighting。

Go to assignment 2， done。These ones are also critical for assignment three。

 week four is critical for assignment three， and then pretty much everything else in the course starts to become more relevant for assignment  four。

You've all kind of made me think， too， that maybe in future terms， I'll maybe put like a little。

 some little icons against lectures so that people can kind of better understand how things piece together in assignments。

 but hopefully that。Loose description is a good starting point， at least。Now。



![](img/9b2334de6b7bce29a33363e7b68f3198_11.png)

So let's look at today's demo for nodeGS， so again， assumption that if you're at this point。

 you should know enough about nodeGS。That's a pretty fair assumption。 Now。

 this problem that we're being asked to do here。 write a simple node Js script that reads in up to 20 dates in the format。

 Y， O Y Y Y MM DD from R V for each date calculates how many days since that data passed and then creates a list of keys value pairs from。

That store。Yeah， that's stored。Date and days since the date outputs this as JO to a file on the system。



![](img/9b2334de6b7bce29a33363e7b68f3198_13.png)

Because most of you have pretty much guaranteed 90% of you here， 95。

 probably even 99% of you know Python， a lot of what we're going to be talking about today is just like the JavaScript Intro lectures is just bouncing off what we've learned with Python。



![](img/9b2334de6b7bce29a33363e7b68f3198_15.png)

Everything we do in node JS which remember is JavaScript on the server。

 typically we create an empty folder， I've got a file in here already。

 but we go and we create ourselves a little node package node package manager repository and I'm just going to click through those and now we have our kind of fancy file here packaged JSON which gives all the basic information about you know this little piece of software we're writing。

Now， in that folder， I also have this file called Hello dot Js。

 which is just an empty folder right now。 And we can start off by seeing Con log hey， which will。

Give， which is basically a file that just prints hey， and I can run that file with node hello。

 and that runs that。 Now that's， that's a really simple recap。 right。

 Most of you should know that by now。But if we have a look at the problem here that we're trying to solve。

 we want to read in up to 20 dates。 We want to， you know， for each date， do something。 Well。

 first thing， it says， okay， we want to read them in the format that from R V。 And then you think。

 okay， well， Rrg V， how do I。How do I work with Rrgv so maybe I'll just start Googling Rrgv node JS okay？

What do I get， I look at the top link。 there's something there。 I go to the website。

 Sometimes I find these， I don't know if you'll find this， but。Sometimes I can find these。

Websites are the official documentation kind of hard for someone who's like a beginner。

 sometimes I prefer to look at。

![](img/9b2334de6b7bce29a33363e7b68f3198_17.png)

Like a stuck overflow article or something because they often give me like more examples。

 but it's really up to what you find particularly useful。

 See something like this I kind of like a lot because it's like oh okay。



![](img/9b2334de6b7bce29a33363e7b68f3198_19.png)

I can just go and copy and paste that and that might work for me。So I copied and pasted that。

 let's see what happens now when I run it。Okay， I get this。 Now if you went and watch the。

Package management lecture which you should have if you don't already know the content。

 you'd know that some packages don't have to be installed。

 but some packages do and we're going to kind of compare the two later right but in the meantime this simple package we have it just prints out the two values arly which in the first case is the process we're running and in the second case is the file name that we're running and both give the full paths。

But we want to read in 20 dates in that format from AGV。 So that means that when we run this program。

 we're going to be entering dates such as say today's date， right， or let's do three days ago。

 which is 2023 slash 02。Slash 23， and then we might put in another date， which。I don't know。What's a。

 what's a reasonable exciting date。Let's do， you know， the 30th of December 2008。So we've got 30。

 So now we've got these two dates here。 and you can see that this process variable。

 which has come from this required process， whatever that does， that is capturing all of that data。

 Now this con process equals required。 Obviously， this is an import。

 So this is like using it a hash include or an import andy a hash include and C or an import in Python。

 and we're storing the information that that library provides us in this file here。

 And I might call this even， you know， oh that' that's all of the process and process do argv is the actual av variables themselves。

 So if I just kind of redefine that and said， you know that's what Argv is。

So now we have something cleaner like that and then you think， okay。

 well how do I capture all of those dates now Well to capture all of those dates， What can I do。

 Well， I can make a new list called dates， So this is a list or array in JavaScript I can now say four you know let I equals 0 remember let is the way of saying that I want to create a variable that can be modified whereas constant saying I want to create a variable that can't be modified and let's say we start I at 2 and then we loop while I is less than the length of Rrgv and then we just go I plus plus。

So what we're doing in here is we're taking， you know， if we were to kind of loop through。

 say all of our like this， which is just your standard four loop and we just said date， stop push。😊。

Arg V I。 This is like a really standard old school C style loop where we。

 we will basically be cloning something here。 So you can see we console our Arg V。

 and then we kind of clone it by looping through it and pushing to a new list。

 except we want to kind of skip the first two elements。 So we'll start from two。

 And that'll just give us a list of dates like this。So we don't need that first console log at all。

So now we got our two dates， right， pretty simple so far。嗯。Heyden。

 can you make the text editor bigger。 Yeah， I can。 Thank you。

 That part's really easy to make bigger so I can do that pretty easily。嗯。Good idea。

 The terminal' is quite small， I know its。But you don't need to see too much on the terminal。

 to be honest。I can make my stupid head a bit smaller。

Kind of don't need to see my head at mouth to sit over to the side every year。不对。

Attle bit strange Look， this is a bit of a fun experiment。 So now we've got this。

 So that makes sense。 We've somehow kind of。😊，Gone through those and extracted what we want。 Now。

 we're breaking down this problem at this point in smaller and smaller steps。

 So the next one is for each date， we want to calculate how many days since the date has passed。

 And it's like， oh God， that's， I don't know because you think of these dates as strings， you know。

 which is kind of tricky。It's like， oh， okay， how many days since the dates passed， Well， you know。

 if you were like a， if you were a programmer that had。

You'd this problem had never been solved before。 You would probably sit down and you would， you know。

 you'd start splitting the string out。 So then I'd say， you know。

 for each And we could do the other full loop now， which is say for， you know， date all the dates。

 That's how in C you， sorry， that's how in Javascript you loop through each date。

So here if I want to loop through each date。I would just do something like that。To makes sense。

 right？嗯。Prints out。dates， let me， let me， I like sometimes when I run commands putting clear in front of it because it kind of clears the terminal as is a little fun hack for you if you want。

 I like to do this。 If you put clear then semico and it clears the terminal， then runs your command。

 It just makes it a little bit kind of easier to read all the time。

 Cleans up the screen for the OD like， which is useful。 So I got my two dates there。 pretty easy。

And again， if you're at olds school C programmer you'd start doing things like you know breaking it off and saying。

 well you know my year， my month and my day is like the date dot split based on a slash and you'd split that up into three strings and then you can vote those strings to numbers then you multiply them by you multiply the year by the number of months and the number of days and then you turn that into a number of seconds since a certain time and you could spend like half an hour trying to get that right or。

We could do what these languages were designed for and what No JS was designed for。

 which is to use all of the libraries available on the internet。

So if you're trying to code something in node JS， you think， okay， I've got some dates。

 well now I'm going to Google node JS days since date。Right。

 how to calculate the number of days between two dates。Now， what gets really tricky。Is that。

And this is a unique challenge of JavaScript in general。Is that。

Because Javascript works on terminal and the web as we cover in our lecture。

 some things you Google will be answers for web and some things will be answers for the terminal and sometimes。

They'll actually work on each other， right， Like this jascript here， parts of it would run on web。

 some parts of wooden and vice versa。 So we do have to be a little bit careful of this。 Now。

 sometimes there are easy ways to do things with like built in in jascripts you might call them。

 but other times。We want to use specific libraries。



![](img/9b2334de6b7bce29a33363e7b68f3198_21.png)

And one library that's really popular for node JS is the D functions library。

And the date functions library is essentially， literally。A whole bunch of。functions for dates。

 so we can go and solve a bunch of problems。By providing。嗯。呃。What you say。

By providing a library that does the work for us。So if you know。

 you can install a date functions library。If I just， for instance。

 if I just go into my terminal here and say， you know what， I want to create， let's let's look it up。



![](img/9b2334de6b7bce29a33363e7b68f3198_23.png)

Date functions， snow gass。 So it's a library that exists。 You can go and Google it。 They'll。

 they'll show you that you can。

![](img/9b2334de6b7bce29a33363e7b68f3198_25.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_26.png)

Where's like a bit of an old school way of doing it。



![](img/9b2334de6b7bce29a33363e7b68f3198_28.png)

Yeah。That's okay。 I'll just show you this really quickly。 So it's like， if you have a。

The way we include stuff nowadays is a little bit different how used to you see these imports are a bit different this is kind of complicated it's to do with like there's an old school way of importing in no JS and there's a new school way of importing the new school way is only now just becoming kind of part of the standard configuration。

But it's not quite standard yet so eventually you'll see this kind of thing disappear right now because we're teaching this in a really introductory way and frankly you won't ever really have to do too much like this for just。

Using the standard way instead of confusing you with all these abstractions but。New way of importing。

 old wave importing。 You'll see lots of both examples over the Internet。 You know。

 sometimes I get students that be like， oh my God， this is so confusing。

 And the answer I usually give is like， the reason Javascript is like an exciting and a terrible。

Ecosystem to work with is because the best and worst thing about it is the exact same thing。

 The sheer pace and volume in which people interact with it。

 It is a language that has so much attention and so much time and energy's been put into it that like it advances and its usage is just like unparalleled to anything else in programming right now。

 but the downside is， is that it moves so fast and people keep changing and improving it so quickly that standards can't keep up。

 So it doesn't have the same。 I'd say it has。 So it's very like kind of。

Cool or how it's very new and fresh all the time， but the downside is that it kind of stumbles forward and it takes a while to kind of catch up after itself。

But the point is that if I try and include a library like date functions there。

 and then I try and run that， you see actually get this error and it says module not found。

 it says cannotnot find module date functions right now if you've seen the NPm lecture。



![](img/9b2334de6b7bce29a33363e7b68f3198_30.png)

You know what this is， it's because if we want to use something like that。

We have to go and run NPm install date functions and that will then go and install it to our package JSson and it will go and add the node modules as we've seen in the other lecture we've now got date functions as part of our dependencies。

 we've got this lock file here which helps manage dependency trees and confusing things above my understanding and then we have our node modules folder where the actual libraries themselves are stored so now when I run this oops sorry now when I run this。

It actually runs now this doesn't actually do anything yet， obviously。



![](img/9b2334de6b7bce29a33363e7b68f3198_32.png)

Which is fine， but let's say in the date functions library。

 I now want to actually look up you know date functions。



![](img/9b2334de6b7bce29a33363e7b68f3198_34.png)

What was the thing I wanted to look at interval to duration？



![](img/9b2334de6b7bce29a33363e7b68f3198_36.png)

Sometimes you find these like if you go to the actual websites here and you go to like documentation。

 some documentations will be really good like this one where you can look up interval to duration where it says convert an interval object into a duration object andre like oh that sounds really interesting and you go look and there's like an example there and then you're like okay that's kind of cool and then you think oh how do I use it well there you go I can actually copy and paste this you can see here this particular library doc actually shows you the old school way of importing it。

 you can use viral cont I just use cons here So you know we've got our interval to duration we require that and then we come down here and we try and use it and it's like okay that looks interesting So there's our interval to duration。

Now let's imagine that we put this inside of our for loop and let's just say interval is that and then we just are going to console log well the console log the date then the interval and you think。

 okay well what are the what's okay well the start date is going to be the date and the end date is going to be now in JavaScriptscript new date gives you a date that's right now I can show you that。

 for instance， if I just go to watch the terminal here if I just open the node interpreter and I write new date it'll give you right now right now。

You know， it's giving you a date the 27th of February 2023， and it gives you 7， 29 a。

This is London time or， you know， UTC time， which makes sense because right now I'm not in Sydney's time zone。

 The time now is like nearly midnight on Sunday。 It's still Sunday here。 It's Monday with you。

 So the time zones the the date it gives us is always in like one time， typically。

 which is the London time。Without daylight saving， basically like plus zero。

 which is really useful because this time is the right time for you and I we don't have to get lost in like 7。

29 a where。But the start date， it wants like a year a month， a day， and then hours， minute seconds。

 Well， hours， minute seconds are going to be 0。 but we have hour month and day， and it's like， okay。

 well， well I don't know how to split that up。 But' if you imagine you're a programme and you're trying to work with this。

 don't get stressed on splitting it up yet。 Focus first and actually just。

Putting in you know hard coding in numbers and seeing if it works so I'm just going to put in。

 you know the numbers that we are passing in， which was， you know。2023 February 23。

 and let's just validate for a second that this actually works。

 You know that's the most important first step。 So now I run this on terminal。

 I'll close that for a second。 I run my command again and I can see here that it says， you know。

 2023， February 23， it's been  zero years，0 months，24 days，0 hours。

 29 minutes and 37 seconds and you think oh 24 days。



![](img/9b2334de6b7bce29a33363e7b68f3198_38.png)

It's a little bit confusing， isn't it？Why is it 24 days。Becauseuse， you know。

 it feels like this is only three days ago， right？So what are we getting wrong here。

 Does anyone want to help out？

![](img/9b2334de6b7bce29a33363e7b68f3198_40.png)

Because what like the point of this is to show you that。

A really common process you will follow is to find libraries like these to help you solve problems。

But then as you work with them， you'll need to understand how to debug them。

 how to read the documentation， things like that。Yeah， so okay， any ideas？

Why are we getting this wrong thing？Okay， how would you debug this Well。

 one here's one thing you could do。 You could go and take this。And you could go and say。

 you know what， at the end， I'm actually just going to go console log these two things out。

So I can see what。See what I'm getting。Okay， so they look pretty， oh， there you go。

 that's quite interesting。😊，The first one thinks the dates actually March。Okay。

 so what's happening here is that clearly zero is January， one is February。

2 as much So as we enter two and then it's like， okay。

 that's problematic because if we think about our dates that we're trying to pass in。

 which is 23022023， it's like， okay， will this cause us problems maybe。And again。

 before you stop before you kind of start going and trying to solve all these problems yourself。

 you've got to remember JavaScript is quite powerful。

 there's maybe lots of ways you can solve the problem a good example is if you went and looked at the date library you might see let's see what happens if we actually just pass the raw date in see how it interprets that。

Look at that。The JavaScript library is actually smart enough。to。Take in。

The date in the string format were given and convert it to the correct date here right now you can obviously see that。

You know， it put in the time as 8 a， which。Is interesting。 I don't know why's specifically 8 AM。

 to be perfectly honest， but。Bigger。So what does this tell us？



![](img/9b2334de6b7bce29a33363e7b68f3198_42.png)

This tells us that the month was the problem and we actually tried to。

Not use the library well enough， so if we actually just put date in here， this should work for us。

 so let's try this now。Okay， zero years， zero months， three days， 23 hours。32 minutes and 54 seconds。

You think， okay， let's go back to the original problem。

 calculates how many days since that data passed。Okay， well， three days。

Right let's just get the days part。 So now you can say date and then we might say and then we'll use the funny little backtics。

 we'll say dollar interval dot days。Have passed。Okay。And you can see this is how we are。

Using strings in jascript， Javascript has this kind。

 this is the equivalent of Python F strings for those who don't know you got the back texts。

 you put the dollar sign and then you got the braces and that's how you inject a variable within a broader string。

 Okay， so this seems to work so far right now we aren't quite reading in 20 dates but that's okay two dates is fine for each date calculate on how many days since the days passed easy Okay now we want to create a list of keys to value pairs that stores the date probably is a string and then days since that date days that are passed since that date。

Okay， oh wait， now we've got a problem， have a look here where're like， okay。

 there's been three days that have passed。Since that date and then here it's like there have been 27 days that have passed since that date and it's like oh why is that that's because we are only looking at the day's interval。

 whereas if we look at this one here this 30th of 2008 it has a years a month and a day's element。So。

 again。Do we want to go sum those up？

![](img/9b2334de6b7bce29a33363e7b68f3198_44.png)

Maybe。Maybe not。What can we look at here Let's try and see what let's try and see what else is in the library and again I run this lecture twice a year。

 so I frankly forget what's in this library half the time。

 even though I do the same lecture I nearly always forget which is fun because it means I get to kind of explore it with you which is like okay。

What are we got each day of interval？Returns the array of dates within the specified time interval that seems interesting。

 that looks like when you find two intervals it shows you all the days。

 but that's not what we're looking for。um。Let's look for like， a days between。

Difference in calendar days。 That's really interesting。

 Get the number of calendar days between the given dates。

 This means that the times are removed from the dates and then the difference in days is calculated C。

 suddenly。We are realizing that like we could have just spent a whole bunch of time solving this problem manually as opposed to using simply a better library function。

 You can see here that it gives us a different line to import So up here。I come up here and I say。

 all right。There you go constant's difference in calendar days。Let's try this now instead。

 so we'll say difference in calendar today as you can see。

 it doesn't really take a start and a finisher just。Takes in two dates。 It's interesting isn't it。

 It's like， why do functions do that some that seems quite inconsistent， doesn't it。

 I'm sure there's a good reason。So there's out two dates。Console。

log date and then we'll just say difference in calendar days and we'll just comment this part out now because we don't really need it。

We run it again， okay， function difference in calendar days。Okay， that's quite interesting。

What are we doing wrong？Oh， this should be interval silly， silly， silly， silly， silly。 Okay。

 negative 3 and 5，1，7。 So you can see the orderings around there is a little bit differentca in that case。

 they're always putting the the high ones。 So now we've got three days in 5171。 Wow。

 how easy was that right， crazy。 So we do Noday between。 Let's name our variable。

 something a little bit cleaner。😊，And there you go。Days in between， really good。



![](img/9b2334de6b7bce29a33363e7b68f3198_46.png)

Next one， create a list of keys and values。 Okay well that's pretty easy。

 I can go and create a object in JavaScriptscript called date days since pairs It's an empty object or an empty dictionary for those of you with a Python background and each time I loop through this I can say date days since pairs and I can use the date which is a string as the key and say that's equal to the number of days between。

So I'm basically building out that object or dictionary and then I can print date days sense pairs like that。

Okay， so 2000， is my first date。 that's three days。

 Then is that now when I go at other dates like say。You know， what's an important date？

I don't know when， when did what was。What was the Trump election everyone remembers that day， right？

So 8th of November or something，4th of November， I can't remember how the US selections work。

 but they go okay， 22305 days that sounds about right。

 you know obviously you should go and check this in more detail naturally but you know that's okay。



![](img/9b2334de6b7bce29a33363e7b68f3198_48.png)

嗯。Just getting started there。

![](img/9b2334de6b7bce29a33363e7b68f3198_50.png)

Create a list of those pairs and then outputs this as JSON to a file on the system。

 so similar thing again， no JS write JSON to file， Google our problems。



![](img/9b2334de6b7bce29a33363e7b68f3198_52.png)

Stack overflow， you know， we know the drill。Blah， blah， blah。

 we can see a couple things happening here。The first thing is that。



![](img/9b2334de6b7bce29a33363e7b68f3198_54.png)

There is a function called JON dot stringify， this is in another lecture too where if you give it a fairly simple either like an object or a based or string。

 like you know J has a fairly strict， simple number of types。

You can see that if we take this object here and actually print it out as JSON。

 it gives us the JSON equivalent of that， but then if we want to write it to a file。

 we need to include yet another library。

![](img/9b2334de6b7bce29a33363e7b68f3198_56.png)

Which is the file system library and then in this case that's when we write that we want to do a right file and。

These all work， but I want to show you the one that's like simpler。

 which is this right file synchronous where we say dates dot JO and then we say we just put our JO dot string of file into it。

So we're using the JO stringing and fire to convert our object。

To Jason and then we're taking that and we're writing it through a file。 and when I run that。

 you'll watch watch the the little editor here。You'll see that this now appears。Dates do Jason there。

I guess one side of this， one downside of this。This approach that I'm doing with the lectures is that you can't see my mouse。

 can you， that's kind of annoying。Because I can't really point to stuff oh well。

So now you can see we wrote that to a file， right， pretty easy， pretty good。Pretty， I don't know。

 Like， it just works。 It just like behaves where like。That was easy。 Like， how long did that take us。

Like 30 minutes， right， well， not even 20 minutes。 we've just mostly been rambling the whole time。

 you know。So it's like。

![](img/9b2334de6b7bce29a33363e7b68f3198_58.png)

So it's like any questions about that particular one？



![](img/9b2334de6b7bce29a33363e7b68f3198_60.png)

Just wait a second for people to talk。Ask questions， we're going to move on to the other example。嗯。

In a second， but I just want to make sure。We're real good。唔 k。All right， super engaged good。

Goodooy goody goody well let's move on to the next question then。This one kind of。

This one is an interesting one and again if if if you've watched， if you've done 153。

 one in the last couple of terms， this is completely pointless for you， but for the majority of you。

 I think more than half。This should be quite interesting now。

The reason I like the first demo question is because it helps us understand the kind of general mechanics。

Of no Js， It helps us understand that like， okay， we can do things like read from R V。

 We can do things like。Ls and dictionaries， JO writing to files。🤢。

Including date libraries and pars stuff。 We kind of get a good little touch on all of it， right。

 gives you a good sense of how you can use it like a language like Python。

 But the second question is honestly not something that you're going to。



![](img/9b2334de6b7bce29a33363e7b68f3198_62.png)

Use any of in the course， you're not going to like you know you look at this write a web server。

 you're not going to be writing a web server in this course。

 it's something that we we do in other courses in CSC but we don't do it in this course。



![](img/9b2334de6b7bce29a33363e7b68f3198_64.png)

The point of this question is kind of just a bit of fun it's just a bit of fun to show you what NoJS can do if you've written something in Flask or Gengo or something in Python before then it's a good way to see how you can do something similar in JavaScript but mostly it's background knowledge because in assignments3 and four you'll be building a front end。

For a server。And that server will be written in no JS just like what we're doing in this lecture here。

It's not something you'll apply， but it's something that will help you understand what is going on under the hood。

Later on， and this question says we want you to start a simple HtTP server that has one get request route called slashSpe。



![](img/9b2334de6b7bce29a33363e7b68f3198_66.png)

All undergrads should have。A good baseline of。Networking and HDP。If you're a postgrad。

 then if you don't know anything about get post request HTTP。

 I'd probably recommend that you go and watch the catch up lecture for Understanding HTTP servers where we cover that a little bit。



![](img/9b2334de6b7bce29a33363e7b68f3198_68.png)

So you can go watch that that should be pretty straightforward， but otherwise let's just get into it。

 I'm going to create myself a new file called server。 Gs。

And what we're going to do in this file is we're going to go and take。

fairlyair simple server library that you can find on Google if you just type in No JSHtTP server。

You Google it。 There's a few different things you'll find。 So again。

 the benefit of something like a jascript or node Js is that， you know。

 it's not like see where you have to go and write your own systems。 You can go and。

Use something that already exists。Now there are kind of two popular servers that you might deal with with node JS。

 one of them is the HTTP server library。

![](img/9b2334de6b7bce29a33363e7b68f3198_70.png)

This one is like a more generic library that lets you kind of do it makes everything with running an HTP server it a little bit easy We're not going to use that one。

 we're going to use one that's a lot more opinionator called Express。

And what express is is it's like a much more narrow focused HTTP server that is easy to use for like a more narrow thing so it's like and you'll see this pattern a lot with these libraries they'll often be big libraries where you can do everything and everything's kind of medium difficulty and then there's libraries like this where it's like really focused on a specific task but doing that task is really zippy。

And you can get started with this just by copying and pasting this particular code here and you can see that the only library it uses。

 you can see that you can look for the libraries it uses is just with this require keyword。

 so all I need to do now is run NPM install Express。

Now naturally I'm in the same folder that we did the other activity and so in terms of our met package management。

The expressed dependency that we're installing was happening in this exact same folder here。

Now this really simple server behaves super simply too all you have to do is run node server and it will actually start the server up in this case it doesn't display anything for us which is kind of annoying but that's okay and all this is saying is that if I go here and I go to local hostst300/ I will get this web page hellello world。

Now this app dot listen tells us what port the server is running on。Actually。

 let me take you through it。You know we have the importing of the server itself。

 we have the creation of it， you know， if if you're familiar with object oriented programming this is like kind of importing the class and this is like creating an object of that class type And then here we're specifying that on that server we have one particular URL which is a slash and what that slash is going to do is its going to。

Return。It's going to send back text and that text is just going to say。Hello， world。

Then we're going to listen on port 3000 so we could change that from port 3000 to 3005 or something and that would change the URL that we're viewing。

 but generally that's a really simple web server and you say how easy that was we're now running a web server super。

 super， super easy。

![](img/9b2334de6b7bce29a33363e7b68f3198_72.png)

嗯。

![](img/9b2334de6b7bce29a33363e7b68f3198_74.png)

What the question asks us to do though is this route we want to create a route called scrappe and they said we want it to be a get about okay so it's a get route called Scpe Easy This route takes in a URL and a particular HTML tag to look for and count okay that sounds interesting So what this is saying is we want to take in a web page URL and a particular HTML tag and then we want to somehow count how many times that HTML tag appears on that web page It's like okay Sure。

And this route should return a simple object with the number of times that a tag appears on the web page。

 so let's break this let's break this problem into a few steps。

 We need to first capture the URL and the tag in the request。Then we need to count it in the URL。

 Then we need to return it。 So one of， you know， I think the best things to do with all these things is to。

 you know， just kind of stub code it。 So first thing is how do we capture things with a get request。

 Well， now I'm just gonna again， Google express get capture variables。



![](img/9b2334de6b7bce29a33363e7b68f3198_76.png)

How to get， get query strings in express to us And okay， well。What do they show us they say that？

There is this magical variable called Re Do query， which makes sense because one of the， you know。

 when we're looking at a particular HTTP request such as s Scpiier。

 we have access to these two giant objects which are request in response。

And these things are massive。 Like if we look at them together here， right， Like， let's say I。

 you know。Restart that server， and then I come up here and I go slash scrape。

Look how big these objects are they're both massive because there's so much stuff in the request and the response because every HTP request has a bunch of data that the server gets and then a bunch of data that the server sends back and what they're seeing here is that there's actually a particular。

Field called request dot query， which will actually store all of the stuff that is sent by the URL。

 Now， granted， because nothing is in the URL right now。

 we get this empty object down here that you can see。But if we go and add things to the URL。

 such as URL equals hello end。tagag equals BR or something like a line break or， you know， like that。

 then that information is now passed through to the server。I'll point out again。

 if you're feeling lost， there is an assumption that you have understood the basics of HtTP servers。

 so if you are lost and you don't know things about gett or requests or responses。

 please go watch that lecture， particularly postgrads， but assuming you're following。



![](img/9b2334de6b7bce29a33363e7b68f3198_78.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_79.png)

We've now captured that data。 If you played around with things like flask。

 you've probably got some familiarity with this concept and you're just seeing it done a different way。

 And now I can capture those variables。 And I can say， well。

 my URL is request dot query dot URL and my tag is request dot query dot tag。

And then I might console log both of those， Con log URL and tag easy， restart the server。

Bun it again。 Hello and VR。 That's good。 And then what am I going to do， I'm going to return。

 What did it tell me a simple object with the number of times that a tag appears on the web page。

 So I'm going to return an object that says count5 or I might say， you know cont count equals 5。



![](img/9b2334de6b7bce29a33363e7b68f3198_81.png)

So you can see now and this is this is I'll say this in every course I。

 This is how I like to break down problems。 You can see here we've gotten the flow and the pipeline of the problem solved。

 even though the generating of that count right now is fake。 It's just kind of made up。

We actually need to account it for real， which is kind of a harder problem， right？

But we've gotten started somewhere。okay， the bottom line of my terminal is out of frame。 Thank you。

There are。 Thanks， everyone。Good point。So。Now。Oh okay， I've got another question。

 NYX says do we need to MPm in it every time we create a new project？I guess so I mean。

 yes is the short answer， the question that's more interesting is what is a project and the answer as well。

Deds generally you'd MPm and knit for each new project and a project would just be。You know， what is。

 what is a sizable piece of software that you want to package up and potentially share with someone。

 So， you know， in this， like look。In this lecture， we're doing two examples that are totally unrelated。

 so yeah， you'd probably NPm and two different folders because you'd be working on two different things and most of it they'd be two different git reos。

 so to speak。I'm just combining them together。It's easier， you know。

 and it gets us through the stuff quicker。So I've got my URL， I've got my tag and then you think。

 oh golly， well what do I need to do now， I need to somehow take a URL and load up an entire web page and that entire web page I want to get all of the HTML code in it。

 Good thing you all understand HTML now， but I still actually have to go and Google No JS read HTML page from URL or something。



![](img/9b2334de6b7bce29a33363e7b68f3198_83.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_84.png)

Okay， and what do we got get URL contents in No GS with Express。 Oh that sounds interesting。

 So what do we got。That's maybe not what we're after。This looks interesting there。



![](img/9b2334de6b7bce29a33363e7b68f3198_86.png)

You see no Js。Think。Read。URL content。It's a sync request。



![](img/9b2334de6b7bce29a33363e7b68f3198_88.png)

There's a library here now。Later on in the course， like there's many libraries you can use to solve this problem after you do the content in week four。

 which is on asynchronous programming。Most of the libraries will make sense to you。Becauseuse you'll。

 you'll have learnt about asynchronous programming For now， I generally would encourage you to。Use。

 well， you're not gonna really again， this is a， this is a fun demo。

 You're not really gonna be doing this。 But for today。

 I'm going to be using a fairly simple library that's not very popular。 It's called sync request and。

It's just， it's just going to allow us to actually make requests。Like this。

 where what we can do inside here is after we import it， right， we'll say， you know。

 constant request equals requires sync request。Is we can come in here and we can say， well。

 my response is a request。To this URL and you know， the URL that I pass in。

 which I actually need to provide a real URL。 But you know what。

 let's just start with Google do co like this。And it's got all these headers and things。

 but I don't need to worry about that for now， and I'm just going to console log the response and see what happens。

 see if we get an error or something。

![](img/9b2334de6b7bce29a33363e7b68f3198_90.png)

So I go and run my server， I go and refresh this page。And we get， oh， look， we get this whole thing。

 Look at the terminal。 It says response to 0， blah， blah， blah， blah， blah。

 And then we have body here。 Now， body is what we're interested in。Okay， so now I try this out。

 and me go body。Run it again。 We can see the bodys this kind of whole buffer thing。 Now。

 normally you'd kind of Google this and you'd be like no Js， no Js buffer to string。

 And you you try and find the problem。 buffers have a two string method。 Okay。

 that sounds interesting。 Dot body dot two string。 See if that works。 Re the server。Oh， cool。

 look at all that。 whole bunch of HTML and JavaScriptscript， a lot of JavaScriptscript， right。

 but some HTML there。So you think， okay， that's really good， cool。Okay， well， there's our string。

 There's our body。 So let's capture that and say all HTMLM L is that it's the， the response。

 And now we've got our tag。 and then you think， okay， wellll now I want to find。You know。

 JavaScriptscript number of time string in string。

![](img/9b2334de6b7bce29a33363e7b68f3198_92.png)

How to count string occurrences in a string， What is JavaScript going to tell us？

I was going to tell us this a few different ways。 This is one's using redjex， which is fine。诶。

So people are sharing you their functions。A lot of stuff is going on here。😔，This one's quite smart。

 This one， this is the funny thing。 Some languages， you know， like， I'm pretty sure Python。Is maybe。

嗯。Interesting， did I move that to the wrong So I。Playing around with the terminal。

Make sure everyone can say everything。嗯。You know， some languages will have easy ways to count strings and strings。

 right， but with。Javascript， like just a quick Google， it doesn't look like it's that easy。

There's no like you know， instance of or you know， number of or something like that。

But you can see here these are lots of different ways people have solved off。

 Some people have solved it with red。 Some people have written their own functions and shared that this other person has been kind of smart said you know what。

 if I actually just use the split function which takes a string and I give it a thing and it splits that up So if I have like you know if I have a string like you know ABC D dot E and I go dot split on a dot。



![](img/9b2334de6b7bce29a33363e7b68f3198_94.png)

That will break that up into an array of A， B， C， D， A。So how many dots exist in that Well。

 one less than the total number of items。 that's kind of interesting。 So we could try that。

 We could say con count equals all HTML dots split on， say， the tag。So if there are5 B tags。

That means it'll break up。When you try and split it， it will break it up into six different pieces。

 so you need to subtract one off that。 We actually need to get the length of that because if you split it。

 that will break it up and do an array of six pieces。

 the length of that array will be6 and then you subtract one to get5， which is the count。

It's a bit ugly isn't it， but it works， right， so we can try that。 we can say let's count that。Oh。

 let's reallystar the serve and try this out， refresh。14， okay， that's interesting。

 Whatever is available H1。0ero， H2。2， H 3。H4， what about a bold tag？1886。 Well， why have I got 1886。

 that seems really high， right， that kind of like too high。

 And the reason for that is because we're just splitting on the letter B， right。

 Whereas what does the tag actually look like well。This is where things get tricky。 for a BR tag。

 you you know that it's probably going to look like that。Or， you know， it could also look like this。

 couldn't it。There's actually a few different instances of how that tag could look。

 but pretty much only4， or like maybe 6。Or you could have more white space， right。Oh。

 it just keeps going， doesn't it。And then you think， oh God。

 And then when you have other things like bold， well， they've got closing tags。

 So now you've got that， and then you've got capital bold and capital closing， you know。

 and then then you've got all mixed in match And you think， well， damn， this is kind of hard， so。嗯。

You know what's maybe the right way to go about this。



![](img/9b2334de6b7bce29a33363e7b68f3198_96.png)

Does anyone have any ideas， How would you， this， this solution clearly has some holes in the approach that makes it imperfect。

 How would you try and。

![](img/9b2334de6b7bce29a33363e7b68f3198_98.png)

Make it more。嗯。Sorry， got an important work message。 UNSW work， don't worry I'm not。

Not cheating when you are with other work。How would you break this up。Some give me some ideas like。

 you know， like I've shown you the limitations of this basic string splitting method。Like， you know。

 the reason this question is fun is because whether or not you're coding a server and node Js。

 we're still exploring what Javascript can do because a large part of this is still like some of this you couldn't do with web Javascript。

 which is what the rest of this weeks on and stuff。 Okay， Vincent， good job， Vincent Vincent said。

 not sure if valid， but you could convert everything to lowercase and then check for B and then divide that number by two。

Okay， so I like where this is going。 So instance， like， well， firstly。

 we should convert everything here to lower case。 That's true。

 We should take the body and we should do two lower case。 I believe that's a function。Javascript。

Do them， okay。Yeah， it is。 So this will convert everything to lower case。 So that's good。

 We can get rid of all the upper case problems we have。And then it says， well。

 instead of looking for tag， why don't we look for？Tag with the braces outside of it。 Okay。

 sure that makes sense。嗯。You could maybe even make this a little bit easier by removing out。🤢。



![](img/9b2334de6b7bce29a33363e7b68f3198_100.png)

You know， if you're worried about say someone having like a B。

 is that's pretty unlikely you don't see much of that。

 but you could actually remove all white space if you wanted to too。Remove all white space。

 That might create some problems， but let's roll with it for now。 So we' lower casing it。

 we're removing all the white space， and then we're counting all the bees。



![](img/9b2334de6b7bce29a33363e7b68f3198_102.png)

Should work。 Try that out。Where's my tab。

![](img/9b2334de6b7bce29a33363e7b68f3198_104.png)

I've lost。Did I close it。Oops。嗯。Oh， I hard code that。That's right。 I should really use URL here。

 and then put。Google up here。Okay， cool。 So now we've got 19 B Rs， and we've got。

Still that many bees， Probably cause I didn't restart the server。0 Bs。 okay， what about a tags，0。

 A tags。 Okay， well， let's try and console log all H T M L。

Let's make sure we didn't totally ruin everything。Okay， that still seems like a lot of H T L。

 I can see a。Oh， and then you're like， oh， no， I see a problem， these divs。🤢。

These divs sometimes don't have closes immediately after them。 So that's not very reliable， is it。

 because if I just do div here。Says we have0。 But if I get rid of that closing brace。

 how many do we have。21， okay， well， this， this starts to make sense。 and it kind of works because。

 you know， we have all those divs， but this this kind of breaks down in the B problem。

 because if we have a bunch of bold tags， how do we separate bold from B R。

Cause if we have five BR tags， that probably means we only have two bold because if B gives a7。

 you know what I mean， that's because there's like a bunch of Bs and then there's a bunch of Bs。

 And every time we do that， it's going to get the BRs too so you think oh。Gosh， well， again。

 what could you do there Well you could， you could count them up again。By saying， well。

 let's get everything where there is a closing tag or where there's a space after it。

 And then you think， oh， we already got rid of all the spaces。That's not good。

 So maybe we do have to go and unreplace all those spaces and just deal with it。

Because we're gonna to add these two together。So it's like， okay。

 we're gonna count all the tags that close immediately and then the tags that have the space after it。

Oops we've got a tyer。 B is not defined。what do we got， B be， be， be， be be。With the B。24 어 없어。

Riding crap everywhere。Count 0。That's not good。What have we done wrong there？Count0。😔。

We've got some parentheesis problems， probably not。

 that's not really the order of operations is not a problem there。Then you think， okay， well。

Space tag。 This is where you have to then go and inspect the H a bit again。

 So let's go and console log out all the H。Let's look for tag， right， So it's a good way to a bug。

 you go and say I'm going to go look for tag。 What tags do we have input， input's a great one， input。

10， okay， so maybe there just wasn't any Bs cause we have some divs。

So maybe we were just false positive in that whole time This is probably an okay starting point for us。

This approach is also good because it works with the void tags like BR2。Sort of。Yeah。

 this works for Br2， obviously it doesn't account for when someone does that but。You know。

 you could always expand this just by adding more and more like by saying， yeah， okay。

 if someone has't open。Clloose things like that， you know， play around with a but。

The point is we've gone and solved this problem and you know what。

 you know what we didn't do here that we should have done。

 we should have gone back at the very start and made sure that libraries like this don't already exist because maybe there's libraries out there。

 no JS count HTML tags。

![](img/9b2334de6b7bce29a33363e7b68f3198_106.png)

Probably exist。Count all A tags on a page。This is all this is all web JavaScriptscript。

 this is not no JS， that's why I searched up no JS。嗯。You know， maybe it's not。

 maybe it's not doesn't exist or something， and that's okay。

Sometimes things don't exist and sometimes you have to do the work yourself。That's okay。Okay。

Any questions because that kind of brings us to the end of the demo today。

 there haven't been too many questions so we kind of jotted through things pretty quickly。

Just a quick recap while we check if there's any questions。Today was about。

Getting you comfortable with Java so that when you go and do so again。

 there's JavaScript the language， it's done on the browser。

 it's done on the terminal Today we played around the terminal because it's easy and it gets you comfortable with the language itself。

 but for the rest of the week you're going to go play around with JavaScript and the web browser。

That's what assignment two is on that's what assignment3 is on that's what we're going to be talking about next week and the week after so lots and lots and lots of web stuff this is the only time for a while we're going to be playing with JavaScript on the terminal。

So go deep into the web stuff。So after today， go ahead and watch all these week three lectures here。

 the Web JS intro， the Dom events， JavaScript closures。

 and remember if you get stuck on any of these or something doesn't make sense。

 you can always go down to the bottom of E and it will show you these are a few good exercises to do。

Right。Cool。Andrew says， will the tutorial questions for the week focus more on Web JSN？嗯。As a rule。

In this course。With the exception of week 1。Every。Wak。U。Oh， sorry。

 I wasn't showing you the dumb stuff， I was on a different screen。

What I was showing you before everyone， sorry， I have a couple of windows open。

 That's one downside of it。 By the way， do you like this， See this little thing up the top here。

 there' little flashing things， There's actually something one of the tutors Jason here made。

 So he actually contributed to the E source code I is something that I encourage you all to do if you're bored。

😊。

![](img/9b2334de6b7bce29a33363e7b68f3198_108.png)

Just trying to find it。Yeah， Jason went and put in this the other day so that when there's a lecture on or a help session。

 you can actually click on this and it takes you straight there。 So that's really cool。

 really good example of just people contributing stuff。 But my point was。

 sorry was that the next thing to do after this lecture is to go watch all of that。 Now。

 there was a good question that was asked， which was。😊。



![](img/9b2334de6b7bce29a33363e7b68f3198_110.png)

嗯。From Andrew。If you exclude week one， every week what we do is we actually。

We do the tutorials the week after the lecture， so all of week two's tutorials focus on Week one lectures。

All of week three's tutorials focus on week two's lectures。

 so this week all the tutorial questions in class are going to be focused on mobile CSS and dev tools and the basics of JavaScript right。

嗯。Because that's what we did last week with the prerecords。

I understand this is slightly awkward for assignment， too。

 I get that because you're kind of sitting there being like assignment， too。

 This is on all the web stuff， but。You're saying that the web stuff we have to learn this week and the tutorial questions aren't on it till next week。

And the answer is that。Assignment 3。Is big。 And it's like。30 times more work than assignment to。

And it's out in week four。 So basically all of the web content is geared towards。



![](img/9b2334de6b7bce29a33363e7b68f3198_112.png)

Assignment three。Right。So next week we demo the web content live。

 next week we do the web JavaScript tutorials。You start assignment 3。

Everything's geared towards that this week is just like a little kind of like self-guided there's a really simple few lectures to watch and a really tiny simple 5% assignment so don't go to the tutorials this week to get comfort for your little assignment to go to the tutorials this week because you're trying to keep building up your knowledge necessary to keep going through the bigger parts of the course。

Yingbaus says， heyden， I got a question about assignment 2 format for street name and Sub Can we assume the user will input the info directly without any starting spaces。

 I think that's fair。 Yeah， that's fine。 When， we're not gonna like assignment 2 is not tested that heavily like。

I'm probably just gonna to get like two tutors to mark it all in like a couple hours like it' it's meant to be like a35%。

 Most people will get four or five out of five on it。

 It's only there to like force you to not force it's a bit dramatic it's there to really just be like go learn the basics of this so that when when assignment3 comes out。

 you've had to learn the basics so you feel confident in starting It's very digestible and we have lots of help sessions too this week。

Cool， any other questions， otherwise we'll wrap up。Cool， we'll wrap up now。

 thank you everyone for your incredible effort at the start of the course。😊。

I know it feels like a lot of things are flying at you at the moment。 But trust me。

 if you just kind of sit in there for one more week， things will start to pick up in difficulty。

 but you'll start to kind of see the picture much clearer too， so。

Keep it up I'll send you a notice on Friday go watch the prerecords， go to tutorials。

 go finish assignment2 and I'll see you all next Monday back in the lecture theatre Oh and last question someone says how do I find my pair I'll be releasing assignment  three formally on Friday Don't you have to start on Friday start it next week after you do assignment2。

But I'll send out the information about pairs。 then I still have to kind of fiddle it together。

 And like 50 people sent me like emails with last minute changes。

 so I have to go and sort all that out in the next couple evenings so。Info on that next Friday。

 this Friday， you'll get the info on it before you can start don't worry。

 you won't be in the dark anyone。Okay。Thank you all， have a great evening and again。

 I'll see you next Monday in person or for those online， I'll see you back here online next week。只啊。


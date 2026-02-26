# UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p11 11 CS169 11.zh_en -BV1UsB7YPEMj_p11-

![](img/ce3ffcd033543aed7b196740c40d342f_0.png)

Sui。Cool， so there is almost no one in lecture today。

So not too surprising considering it's the midterm。

 although it's unfortunate because this lecture is a little bit shorter so the remaining time is going to be questions for the midterm。

 so you guys all get to ask random questions and see how prepared I am for the midterm。

That's mostly a joke。 I do know what's on the midterm。But it won't be。

Midterm honestly won't be too bad。 If you did the practice stuff， it should be。

Very similar in structure， there may even be a couple questions or two that know more similar from there。

And then also we will release the student submitted questions after lecture， we look through them。

 there weren't any that made it today， but they are actually good questions so a couple of those will probably make it on the second midterm and we'll release the form then but there was only like eight or 10 of them so not too many anyway。

 but you just another good set of things to think about they were all relevant to the topic at hand which is nice nobody asked a question saying if they could get 100% which sometimes does happen。

But anyway， so todays this week's lecture， so today is going to continue the topic of BDD and cucumber testing。

 Thursday's lecture will be on our spec。 So the theme this week is really。

 you know building the test cases for applications getting into the meat of rails。

And that's where we'll be for a couple more weeks。We did release homework 5。

 It was a little bit late。 so you have until Sunday as well because of the midterm。

 So it's going to be an intro rails assignment。 and then we will do one or two additional homework assignments after that。

 but they will be all centered around。The tools that you should be using to get you up to speed on your projects。

So， you know， there。This one will be working on some rails applications。 You've seen a little bit。

 So， you know， the stuff that we've covered in lecture， there will be a couple rails。

 questions on the exam， of course， but really。The goal of these next couple homework assignments is to give you the tools that you need to get running on your projects。

 mean， because you have access to your customers， what we're going to start to do is give you resources for contacting your customers so we'll post some starter template emails that you can use to reach out you are free to use them or not。

 but it's always nice to sort of have a starting point。And so for the next couple weeks。

 there'll be some homework assignments and some project work overlapping。 you know。

 We know it's a little bit much at once， especially since we just had a midterm。

 but after after those next couple homework assignments， it'll be full project work all the time。

 and that will be the focus of this class And then you know once you get into project work。

 that's where things get really fun and interesting。 So once you have a foundation for rails。

 we can also talk about all the other interesting things。 So if I can get approval to do it。

 we're gonna to do a lecture later in the semester。

 which is how I develop grade scopepe and show you some stuff from gradecope。

 I desperately want to use that as an example because there's some fun things。

 but I also don't want to just like throw the private repository up on a webcast。

 Since that would not be the best thing。 but I'll see what I can share later on。 and。😊，You know。

 we'll get into what I think is the really fun and interesting portion of this course。

 So throughout the slides， we've given you some general advice。 and I think this one is important。

 you know， knowing what you don't know， especially as it relates to debugging。 This is a reminder。

 especially as you get into haier questions， on your projects。

 especially for those of you with legacy projects where you're going to be debugging code。

 where the person who wrote it is long since gone， not literally， of course，😊，But， you know。

 if you are debugging a problem and you don't understand the problem。

 copying a random stack overflow answer， even if it fixes the problem is not necessarily going to make it go away。

 So I don't have the original source of this quote， but I do like it。

 problems that go away by themselves tend to come back with friends。

 which is a reminder that if you fix a bug by patching it a way。

 you don't understand that bug is likely to rear its head down the road。

 And maybe in a nastier place。 And for the sake of expediency。

 like I will not shame you if you do this because we have all done this。

 I think every member of the Grcope team has done this at one point or another。 Like you know。

 you are solving a task。 But just a reminder that be mindful of that。And this is another great one。

 Week of coding or debugging can save you hours of thinking。That is worded correctly。

This is also true。 we have all been there。 I have certainly been there where you know throwing spaghetti at the wall is comfortable and you know there are times where it's appropriate。

 but taking a step back， thinking through the problem。😊。

I you always likely to get you a little bit further and sometimes faster than you would expect。

 but thinking is definitely hard。 So just you know be aware that the hard stuff actually will save you time along with this sort of the meta point of the course too there's been some really good questions on piazza there's one last night or this morning about like the difference between sessions and cookies those are perfect questions they especially interesting things to think about and a lot of those two this course especially because we're building web applications with you design pattern that exist in industry like when I answer those questions。

 I often do a Google search and check for good blog posts to make sure that I'm not missing anything or that there's some other details or I look up the rails documentation to make sure that I'm not gonna to say something totally off base but with this course。

 especially when you have a question one of the things that's great。We're not telling you。You know。

 just how rails works like yes， learning how rails works is an important sort of practical facet of this course。

 but as a reminder， you have access to sort of everything around the knowledge of software engineering。

 so keep that in mind when you run into questions and things。So to get back to a word。

We're talking about cucumber and cappi Barrow， so cucumber is this nice layer which lets us write tests。

In a way that reads fairly close to English， it reads like computer English。

 because there are lots of things that basically have computer English。

 It sits on top of this tool called Cappibar， which interacts with a web browser and in development。

 you know， all this is connected to a running copy of our application and a database so。You。

 these are steps and step definitions。 This is the part which automates the web browser。

 And beyond that， we have the rest of our rails app。 But for the purposes of writing tests， you know。

 you can mostly assume that the rest of this works。 So Thursday， we'll get into R spec。

 you've seen a little bit of the structure of R spec， perhaps if you've looked at。😊。

Some of the examples， and we'll show you a few there， but our spec is。

A tool for unit testing is a tool that gives you assertions and expectations so you could say expect user session count to be one after you log in for the first time or something like that it gives you a nice again。

 semi-englishlike set of methods but a way of writing test cases that are readable gradecope makes heavy use of R spec like all testing frameworks that has its quirks。

 but I think it is a great tool， and again it's a stack so it goes up and down。So cucumber skills。

 we've talked about these。Step definitions based on regular expressions。

 you should get familiar with them for this course。 You will see them。

 We will not be quizzing you on the aspects of Harry regular expressions for that。

 I recommend you take 60 and B with Hfiner because you get excellent practice depending on the semester。

And they are an incredibly useful skill， but they are a useful skill that you should build up by doing Google searches of the syntax and how to use them。

 do not try to memorize the entire spec of regular expressions at once。

So interacting with components， form fields buttons。 So these are things like fill in， find on page。

 Again， there is a set of APIs for these。 You'll get familiar with them over time。 and so。You know。

 those are really the aspects of things。 We're gonna have a step definition that responds to some essentially variables that you write as a programmer。

 We're going to interact with things of the page。 And then we're gonna check for the output。

 So to continue to continue along with this this is a step definition。We have a scenario。

 we have given and and we can use when and then as well。In our step definition。

 we might make a call in this case to active record。 We might fill in scenarios with。Another thing。

 so first clicker question of the day。What can we expect to find in which file？

 So where in where in our rails app would we find the scenarios and steps。And it's open。

And let's see， so the lecture filled up a little bit more。1，2，34 5，6。Okay， it's leveling off at1， no。

 cool， 30。Can I get to 32？No， we cannot。 but 31 is the largest number that you can represent with 5 bits。

 So that's， that's a good。That's a good scenario So we're gonna go ahead through this that's nicely formatted in general you would expect your feature definitions so the scenarios itself belong in a feature file this question was word it a little bit funny the step definitions belong in a ruby file the way that you can determine this is that your features look like plain text so given when then they are English words they actually do have a syntax to them the language is called Gkin which doest really matter but we just call them dot feature if you have a code highlighter some of them will actually auto detect the structure and give you a little bit of syntax highlighting but your ruby files go in a step definitions folder or file depending on how many you have so those would be a ruby file but the scenario the scenarios themselves should be in a dot feature file and I'll show you a couple。

Examples of course projects， so I have Armando's audienceience first app which will be one group project in this course and I have our app called ESS Engagements。

 which is the application that the course staff uses to manage all the customer projects that will also be a group project but they make good examples of Ruby apps so well poke in some of those tests a little bit later today。

But scenarios in feature files and step definitions in ruby files。

 So another question just checking in with what cucumber is doing。 So in this example。

 what is the step definition trying or what is cucumbers' job trying to do。So remember。

 the question is about cucumber and we have a combination here of cucumber is the thing running our。

Steps。Which kind of hits the answer？27。30。😔，And that's right about where we were before。

 So in this case。Let's so we got an E Qui al right。 let's go through this。 but in this case。

 cucumber is the tool that is going to be the thing that is matching steps to these step definitions。

 So our testing framework so far with BDD is a set of feature files and a set of step definitions。

Cucumber manages the interaction essentially between our feature files and our step definitions。

 so it is a tool that defines things like given scenario and then when is my mouth it does show up they're cool so。

Cucumber gives us this framework。 its job is to then say， well， I have a method and I'm going to。

Well， already already said that that's fine， then I'm going to try and match it with some regular expressions that you have defined as a programmer so cucumber is a thing that's going to be managing that interaction。

Again， these are all technologies that， you'll get familiar with。 The point here， too， is that。嗯。

You know cucumber is the piece that is going to be managing the interaction between features and step definitions。

 Capybarra is the tool that manages interactions with a web browser or a fake web browser depending on your setup。

 but from the point of a test， it works exactly the same。

 The reason it is useful to know this distinction is so that when you run into an error。

 you're able to better you Google something。 Otherwise in practice when your applications are set。

 you usually don't need to worry about what's happening where you get into a nice flow。

And you write some feature steps and maybe you write a step where you're like。

 I don't have a step definition for this， I want to say。You know。

 maybe you don't have a step definition yet that says my birthday is set to or you don't have a step definition。

That says， and the user is an administrator， something like that。

 then you know that you create a new step definition in a step definitions file。

But cucumber is the piece that manages that and we'll get to Cappi Bar in a second。

So we don't need to necessarily go through this will given line match the scenario in this step definition。

 my birthday is set to。It will the reason here is that this would be a pretty poor example to use it for three slides and have the answer be no just as a matter of practicality。

嗯。😊，So you know what we have here is the point is， you know this is really asking can you match a regular expression yourself。

 but given this would match any method here because what we're doing is you know wed said that cucumber matches all the methods are the same alias for in an internal method and the reason for that is just so you could write English like things you might say given my birthday a set to if you want to set that up as a precondition。

But what's going to happen here is， you know we have my birthday， we have some quotes and。You know。

 anything in the wild card here will get matched。 So whatever you put in there you could put in May 12th。

 you could put in， you know，5 slash1，2 slash 1980， whatever you want。

 it would all get matched in this format。嗯。And so why the double quotes。

 this just helps you structure your regular expressions a little bit easier。

 It also helps you separate input as a parameter to your regular expression from the required text so you could actually write a regular expression group here that is you looks for a month type word in some numbers。

 but wrapping it in quotes will make your job as an author of step definitions a lot easier。

 it'll make your specifications and your scenarios much easier to read because it'll be clear which is input and what's not。

 the one caveat being that if you want to use double quotes inside your expression sometimes that makes things complicated。

 but for the most part， you don't really need to write double quotes inside your input and if you run into that and can't work around it just post it out in piazza。

 but you can do。about anything with regular expressions。 So it is a solved problem。

 It just might be heavier than you expect。But quotes quotes are a good starting point for just wrapping your data。

 you could choose to use single quotes， other sorts of things， whatever structure you want but。

Quote to the starting point so for cucumber， the way that you're going to work in your projects is a process where you start by writing failing tests so you will get requirements from the customer。

 you will turn those into scenarios and feature specs so you know you'll say given I am logged in as an administrator。

Then I click update some record and I expect this to see on the screen or something like that。

 if you follow perfect practices， which may be hard and foreign at first and it will feel like a little bit annoying。

 you know you will start off by having a test that when you run will execute but will be failing。

And the goal is to go from failing to passing tests。 So cucumber got the name because。

I don't know why they necessarily picked a vegetable， but the idea was that green tests are good。

 and I guess green vegetables are also good for you。 So cucumber。

 but you go from red to green and yellow is just sort of a step in the middle for not yet implemented which you can mark。

 but for the most part， as your work in your apps， you'll start with something failing。

 then you'll go to green。 if you see blue， blue is a helpful step in cucumber。

 this just means that one of the previous steps failed。

 and I'm not going to repeatedly tell you that these steps failed because you know if step2 out of five fails。

 the app just doesn't go on。 So it makes your failure in numbers and counts a little bit more realistic in terms of what happened in that run so。

These are things that we're not going to go over all of these。

 but I will take a second to show you a couple things in some of the applications that we have。

 but the point being that beyond just given when and then steps。

 there are a lot of features in cucumber itself。And a lot of tools。

Surrounding cucumber that you can make use of to help sort of make your tests go a little bit。

A little bit easier。 So the two things that I'll are actually。

 I'll show you the first two so background steps in dealing with tabular data。

 So let's see if I have。

![](img/ce3ffcd033543aed7b196740c40d342f_2.png)

![](img/ce3ffcd033543aed7b196740c40d342f_3.png)

系。That is the midterm， so we're not going to show you that yet， and you'll get to see it soon enough。

So this one。Has both background steps and tabular data in one file。 This is the Esas engagements app。

 So it's not super exciting。On a development machine。 what it Yeah， Okay， So it's up here。 right now。

 I have no applications。 But essentially， what this does。 actually， So this is。



![](img/ce3ffcd033543aed7b196740c40d342f_5.png)

Let's see if I can float the production one。And it's Heku， so it's gonna to boot up。

 but essentially this tool is a thing that lists a bunch of customer projects。

 It has a bunch of states so that over the many years of this course。

 we can track which customers want to be repeat customers who's working on what projects and so on。

 So if this is your project， you're getting a first look at what we're going to do here。嗯。



![](img/ce3ffcd033543aed7b196740c40d342f_7.png)

But in our cucumber file， so if it boots up in a second， we'll jump back， we have a few things here。

 which is we have a keyword called background， so background is a nice keyword which says for every scenario in this file so we have a feature。

 a user can be created。嗯。And a user can be created， you'll see， has you know。

 about four or five scenarios here， maybe a couple more。

 and all of those scenarios require some shared setup state。

 So a user can be created requires someone to be logged in and so you might want to say， well。

 it's going to be really annoying if I have to repeat the same two or three or four steps before I do all of these features。

 So a background says is if you define a background。It's equivalent to its own sort of mini scenario。

 You can think of it that way。 if I define something that I'm calling background。

 then before each of these scenarios。Cucumber is going to go and run the background steps in R spec。

 when we get to R specEC， there' is going to be a thing called before and after。

 So you'll have similar control there。 But this is a really common pattern in testing。

 which is essentially we have a set of related tasks。 We want to set them up at the beginning。

 and so。That will be run once before each of these individual scenarios。

 So every single scenario cucumber is going to go and run the background stuff。

 So that's the first keyword， which is really useful。 The second thing。😊。

Is that you'll notice there's this structure delimited by pipes。 This is called tabular data。

 and cucumber provides a framework for dealing with this。 It's。

 you get to make use of it in your own step definitions， so。Cucumber will do all the parsing。

 which is nice。So let's see。If I can find。This。Step definition。诶。Let's see where would it be。嗯。So。

What cucumber does， you'll notice that if you， in this case， if you end things with a colon。

 it has stuff that automatically parses things into a table。 and this is。

Not the best example because you don't actually get to see what each hash is。

 but what you do get to see is that cucumber gives you a table of data。

 it turns them into a set of hashes。And then when you have a hash。

 So this is now just a plain ruby hash， you get to do whatever you want to。

 So this is passing a hash into an internal app dot create method。

 So app dot create can do whatever it wants to do In this case。

 I don't even really know what it's doing because I haven't written this application。

 But what I do know is that cucumber has taken。It's taken this table。 It's given me a hash。 So each。

 each item of this hash has three or excuse me， has four values。

 So one of them is a keyword with name， which should be app 1， one is a。Key of description。

 which is the value test or guide D， which is one and status of pending。

 So what cucumber is going to do for you is it's going to par all this。

 Your first row is essentially you can think of it as the header of a CV or the first row of a spreadsheet。

 which tells you， you know， what are these columns。

And cucumber is going to go ahead for you and build a hash out of this table structure。

 So essentially what it's doing is saying I'm going to find a bunch of data。

And in line and then turn it into something that you could work with an array of hashes。

 so if you're taking on a legacy project， most of your applications will have some of this set up already。

 but the great thing here is that as you read through the files。



![](img/ce3ffcd033543aed7b196740c40d342f_9.png)

You get to understand， you know， then you see and I should see new users。

 so these would be probably buttons in the application or features。😡，You know。

 and I fill in new user with these tables。 So this one is just using a field and value。

 So if you remember when we showed you the fill in method from Capbi Barra。

 this works pretty closely， right， field has a name and a value。

 This is those would be Hl form fields。 So this would be a common。

A common step definition that you might write if you want to loop over a bunch of form fields。

 And what this prevents you from doing is saying， and I fill in the name field with user  one。

 and I fill in the email field with some email and， and， you know， and so on。

 So table structure can be really handy here。I can put a link to this on Pi as well。

 all these applications are open source。You may have seen the SaSbook organization on Gitthub。

 which is the organization which eventually owns all the course projects。

 you are more than welcome to peruse that open source code。

 if you're looking for ideas again like professional coders。

 you should not just copy things that you don't understand。

 but if you're looking for design patterns， if you're looking for structure。

 if you're looking for hey， you know this application probably has something similar to what I'm doing。

 I encourage you to go through GitHub and search your patterns and if you do take something。

 credit it with a comment which helps not just you but also in the future when you go back。

And you look at something， you know， a credit will help you figure out where to get more information。

 So those of the power features on this slide are going to be the two most useful things。

 if your application deals with time sensitive data timeco is a very useful gem。

 which allows you to fake the time that your tests are running in so。Graadecope， as you can imagine。

 has a lot of things that deal with due dates and so what we do is we set up a timestamp so before every test we there's a method called timeco do travel and we travel to a specific date and then from there we can say you know one dot week from now。

 one do week ago we have。A series of assignments that are created all based on a similar date。

 So we don't actually have to worry about the current time of running tests。

 And when I created this data， it also lets you do things like time timeco dot travel1 dot week from now。

 And then you can make an assertion that says， you know。

 this assignment could not be submitted or something like that。 So that is its own。A tool。 But。

 you know， if you have anything that deals with timelines， things like that， it can be a very useful。

 useful thing for writing specifications in cucumber or in just R spec。But。These are things that。

 you know， you can go through and do to。To aid in tools and so as you as you get into your applications。

 I encourage you to。You know， to review some of this。 So we're going to post a cappy bar cheat sheet。

 There's a few of these online as well。 We have one that is pretty good， but。

The thing about Kapppi Barra is that it's interacting with the web browser。

So anything that you see on a web page will be available in Kapibarra。

 and it is not exactly necessarily an instance of Chrome。

 So occasionally there will be small differences。 But the idea here is that you always can refer to a page。

And a page in Cappy Bar is like an HTML page。So it has an HTML element， it has a head element。

 a body element， it has whatever your rails app would have rendered。

And the really useful things are find which find is probably your most common cappybar method。

 there are a lot of ways that you can pass data into find you can pass CSS selectors so find you do username will find all the elements that have a username class on them。

 you can find IDs you you can if you're familiar with Xpath which is a way of writing selectors for HTML elements that operate on XML documents。

 they get ridiculously complicated but you can pass those into CApybarra essentially CApybar gives you one method called find which will find all the things on a page however you want to so starting there is a good point there are different submets so if you want to just find links or find buttons。

 those methods will be available as well。To you， let's start with find and。Whatever you pass into it。

 you will be able to use and so a common thing that you'll see。

Is there are methods called have CSS have Pa， have text。

 these methods internally use find and then they return true or false whether or not they find something so a really common thing is expect page to have CSS checking if some CSS selectors rendered you might say expect find some element to also have CSS and that will sort of scope your。

You're searching into a specific element。 So if you have。

 let's say you have a username that might appear on a page multiple times， you might first。

 you find a section of CSS and then expect only a specific section of a page you have some data so you can combine these in an infinite number of ways。

You know， the recommendation here is to make a step definition for these so that it's a little bit more user focused because when your user uses your application。

 they are not going to be expecting a username CSS class to be anywhere on the page ideally they will never know that you have a username CSS class on your page。

 although you know it's a web app so they can expect the source that they want。

 but you write them as close to English as you can。

Another really useful thing that you might find with Cappibarra is you might。

 especially if you're using CSS， want to use CSS selectors that are specifically used for testing and not for styling your application。

 So one common trick that works really well is。So a pattern that gradecope follows we by no means invented this is to use dot JS classes。

 so if we ever have something that interacts with JavaScript。

 we have dot JS and we might have like edit button。

 something like that and what this does is it separates your CSS。From presentation。

 from styling and from using it as a tool to grab a specific element because CSS。

 you know when you use selectors， you're kind of conflating the use of styling and testing and grabbing a specific element So gradescope uses dot Js since if we're testing something。

 we probably have some jascript associated with it， I've seen applications， use dot test star。

 you know， whatever they want to name their their CSsS classes as but you give them a specific name so that when you change the structure of your application from a visual perspective。

 you don't necessarily have to change all your test cases。

 so there's a lot of ways you can structure your CSS but whatever you know whatever you want to do we' go in there。

And so。That is a bit on Cappy Bar and cucumber， any questions so far on those tools？

And if you do have questions， now it'd be a good time because there is a cucumber question on the midterm exam。

 but it's a pretty standard one。 So everything that you've seen through last week should cover it。

 But other questions on cucumber。Yeah， just shout it out。How does okay， so the question。

 how does cucumber simulate the web browser？ So cucumber itself。

 just for clarity is going to call Cappy Brow， which is a tool that's simulating the web browser。

 No worries。 So how does Cappy Bar do it。Let's see if I can jump back really quickly to this slide。



![](img/ce3ffcd033543aed7b196740c40d342f_11.png)

呃。Yes， yes， yes。 build effects are only helpful once。



![](img/ce3ffcd033543aed7b196740c40d342f_13.png)

There's a few different tools that Kapibar can interact with。

One of them that's commonly used is Cappybar Webki。 The other one is a tool called WebDriver。

 and so Cappybar Webkit。Which there's now some better tools， but it's pretty popular still。

 What it's going to do is it actually has a Chrome image。Bilt in sort of into the gem。

And it spins up essentially a headless version of your web browser。 So on。On the command line。

 you could start a headless version of a browser and what it's going to do is it's going to say in this case。

 it works mostly like Chrome， so it'll give sort of you can call it a fake Chrome all the HTML of your page then Chrome is going to render it like it would a normal HTML page and then it's going to act interact with an API that。

Sort of this fake Chrome thing provides another way that it does this is using a product called WebDriver。

 So WebDriver is a standard interface for doing browser automation。And what that does is it spins up。

 in some cases， a live browser on your computer。 So there is a mode in which you could actually watch your feature specs be executed live in a browser that you are seeing as it goes through and automates them which is a little bit disorienting because it is faking。

 clicking as fast as a computer can fake clicking， So you'll see things just scroll around and jump up and down。

 But what it's doing in that case is。😊，Trying to play you a user as directly as closely as possible。

 So it's going to say find。 and then it'll make a call to some whatever browser you're using， Chrome。

 Safari Firefox， I'll support this。 It will say， you know， find that element。

And the browser in that case will be looking through its own HTML and then it will return some data to Cappibarra and so there's basically just a couple defined interfaces polulttergeist and Phantom JS are two other gems that get used。

 both of them are now deprecated but they might be used in projects。

 but they work essentially the same way where they are mimicking a browser environment。



![](img/ce3ffcd033543aed7b196740c40d342f_15.png)

But there's essentially just an API that's defined between the browser and cappy bar that it can call。

And actually， if you want to mess with this。 So this may not be the best demo。



![](img/ce3ffcd033543aed7b196740c40d342f_17.png)

No， but if you have Chrome installed。 So， you know， if I have applications。Google， Chrome。So。

An application on the Mac is just a folder。 It has things called contents and things are in this Mac OS folder。

 So there is this Google Chrome binary inside this folder。 And I believe I can do help。



![](img/ce3ffcd033543aed7b196740c40d342f_19.png)

And it's going to try and boot up Google Chrome， so it does that。

And the help flag does not do what I wanted it to do， which means you'd have to Google for things。

 But you could interact with the Chrome that's installed on your browser in a command line。

 So I believe also， if I just like navigate to a page。



![](img/ce3ffcd033543aed7b196740c40d342f_21.png)

No， it's not going to debug things for me。 that's not effective。



![](img/ce3ffcd033543aed7b196740c40d342f_23.png)

So yes， I don't want to have to hold cu。But what Chrome will do is there's a whole bunch of options here they're like really cryptic and not super well documented。

 but you can， if you have it installed in your Mac， I forget the exact location on Linux or Windows。

 but sort of a similar thing， you could actually just yourself。Google the command line options。

 and you can do really interesting things like writing a command line function to open up a web page or getting some data out and controlling Chrome through the command line。

 So Cappy bar， depending on its setup will use something a little bit lower level。

 but you can also set it up to directly interact with the Chrome that's installed on your computer as well。

 And so there's just like there's 100 and some total command line options that Google Chrome provides most of them are horribly cryptic and meant for debugging。

😊，But they are fun to play with， well， for some definition of fun， I suppose。

Other questions on Capar yeah？Yeah， which one？Sa。Yeah， yes so。Just to clarify。 So you said that。So。

 in the。That definition。expression and that as long as in the feature file。

The regular expressions message will call that function so how come in the set definition use given。

Are there other like。Yeah， so they are given and then and when。And there may be one more。

 but those are the four that get commonly used。They are all aliases for the same method in cappy bar。

 So the reason that you can use any is you， you know， so for this scenario。

 you're going to say given I am on the user page， you might， depending on the structure。

 want to test things in a different order。 And so you might say given。You know。

 I log in as a new user。Then and then you might say then I am on the user page or something like that。

 And so what cucumber is doing for you is it saying that these methods of given and then are really to help structure your scenarios so they read a little bit more like English。

 but in terms of the code that gets executed， they all execute the same set of step definitions Yeah oh no。

 it doesn't matter。 Yeah because they're all aliases for the same method。

 what you usually pick is the one that you think makes the most sense。

 So the lecture on Thursday had a couple recommendations。

 which is stuff that's given will set up some preconditions So this will be things that would in this case add some data to the database。

 maybe create a user。You know， set a birthday in this case。

 things that are then and when would be checking for expecting some data to appear or have a condition that's met and if you follow those recommendations it sort of just helps clarify you know what you should see when you read someone's spec files or step definitions but you can really do anything you know frameworks have recommendations and programmers have the power to do what they want with those recommendations。

 but yeah if you follow the recommendations and you'll typically stick to a few specific words。

But yeah， that's a good question， Other questions， cucumber cappy bar related。Testing scenarios。

 things like that。OhCool。Let's move along for the recommendations of customer meetings。

So these are recommendations from past students， which is when you get into projects having frequent communication is really important。

 so one thing that's worked for some project groups is over Slack or sometimes a few groups would do like a fivemin Google hangangout every day。

 but just sort of daily as you're working on your project， even if you're not meeting as a group。

 have some checkin so that when you and your partner you know are you start working on a feature。

 check in with your group， you know let people know what what you've done。

 what you've been struggling with that way especially if you push some code to GitHub and someone checks it out。

 there are no surprises。Team communication with six people will be a challenge。

 especially since all six of you have probably very different schedules， so keep that in mind。

You knowGroups have said one meeting per week wasn't enough。So that means shorter。

 more frequent meetings that could just be checking in over hangouts over Slack。

But keep that in mind for your team， also keep in mind that you know。

As you have a team of six people。You have eight to10 weeks of working together as a team。

So things can adapt even in that time period， you might say let's start with meeting on X， Y。

 and Z dates， but feel free to change things as well。

 take the time to sort of self-evaluate your team， your communication strategies。

 see what's going on。We will be adding you all to a CS 169 Sla。

 So the channel for your project group will be the default place， to have that communication， but。

You know， however， you are communicating as a team。

 err on the side of more communication than less will be helpful so， you know。Why should you care。

 Pa students have said that this is one of the most important things。

 the more that you communicate as a team， the bigger a chance you have of completing all the features that you have been asked to build。

And in industry， I would also say that communication as a team is probably one of the continually hard problems。

Especially if as engineers， you're the type that are not as comfortable communicating with people。

 you will work with people like that in industry， it is always probably the biggest barrier to success on any project。

 but you know， the more you iterate at that process， the better you become at doing it and so。嗯。

You know keep that in mind， so for customer meetings。Some。Some just general advice。

 so you should all expect if you can try and meet with your customers later this week， if not。

 the goal should be to meet with your customers next week sometime and we'll be handing out again。

 some templates for that。嗯。You know the goal is that this is not always just a checkoff of what's been done。

 but a conversation。You know when you have a meeting。

 you should expect that the customer already has the information that they need so in your first meeting where you're going to get up to speed。

 you won't be demoing an application right In fact， if a customer is a repeat customer。

 they might be demoing something to you but you know they should have a sense of what the meeting is going to be。

 you should have a sense of what you're going to provide in terms of working you know the goal when you deliver a feature is again。

 it works on production not just it works in your computer。嗯。😊，You know。

 it is a professional meeting so。You know， be professional about it and remember that your customers are not necessarily Berkeley people。

 so they expect meetings to start on time， not on Berkeley time。

 if you need to make a meeting start at Berkeley time， that's perfectly okay。

 just tell a customer that you'll be starting at， you know，1210 instead of 12 o'clock。

 and you know that that will usually work。But just be mindful of that as well。 And， you know。

 for your own team meetings， you can start whenever you want， of course。

 but be mindful of that with customers。嗯。And。The biggest thing is in advance of the meeting。

 give the customer everything that you think they will need to be successful in the meeting。

 so if you have a demoable application，Make sure that they have access to that beforehand so that they can go through and test it so that in a meeting the feedback that they provide you is not just。

 oh yeah， I sell you demo away and it looks good's I have played with this。

 I think that this works pretty well here is some feedback about X Y or Z and the more that they have a chance to give you to prepare for their side of the meeting the better feedback that they will give you and that makes your job as implementers much easier。

And again， you know。The goal with this is to get as specific as possible。

 So if they give you specific feedback， note that down and you know， track that， whether that's。

 you know， in pivotal tracker， if it's directly on a story， if it's just Google Docs， Slack notes。

 whatever， you know， whatever methods your team uses to track notes from customer meetings。

 you should use what's comfortable to you， but do make sure that you track。

You know what happens Google Docs are probably the best thing for meeting notes since they're easy to share access。

 you can do all sorts of fun things with them。 But you know。

 however you want to work that is important for you。Again， during the meeting， all the simple stuff。

 you know， you should be present for the meeting。 you should not be multitasking。

One person should be taking notes so that you know， you have a record of that， but otherwise。

 you know keep that in mind， here is a typical agenda， which is revisit the last meeting。

 get feedback on any updates since then。And then the most important thing that you can get from the customer is to prioritize what is important because you're building an application for them。

And this will vary greatly depending on the customer。

 But some of your customers will have dozens of really good ideas and you will not be able to implement all of those ideas。

 And so it is important to say， you know what is the one or two things that are most important for you and ask them a question that way。

 you know， say what are the one or two things that are most important， you know。

 And if they give you five things， say that's awesome， but we don't have time to build five things。

 you know， of those five， what can what should we start doing first。 because。😊。

That will help you come back to the next meeting and you'll say， okay。

 we talked about these two things， here's the two things that we built and you let's go from there but the more you can get clarity on priorities。

The easier your job will be。Again， the reality is that this is one of these things that is always hardest in industry。

 whether you're consulting， whether you're developing， know internal projects。

 prioritization is difficult。 so expect to get it wrong a couple times。

 but definitely the point being that you should try your hardest to iterate on that。嗯。And again。

 after the meeting。 So following up is important。 You know， if you took good notes。

 then it should be easy to enter them into tracker or something like that。 Remember。

 tracker is not necessarily a to do list。 So you may have action items that aren't。

aren't directly user stories that you want to follow up with。 So as soon as you get them done。

 you know just let the customer know， some customers might ask that you just give them updates on some specific frequency。

 if they do that， then work with them a great tool for reminders is since you will all have Slack channels。

 you can just use Slas built in Slackbot to say remind me X date to send an email to the customer about whatever you talked about feel free to use the power that Slack gives you there if you want another project tracking tool you're more than welcome to add one on your own。

😊，But of course。knowThat's things that your team all needs to be comfortable with。

And anything that's code。You should definitely make a story for so even if it's a minor change。

Make a story， put it in tracker if it's an easy thing， you know， assign one point to it。

 just knock it out and you get a couple small things done。

 but make sure that all code changes specifically are tracked in tracker as well and that gives you a good sense of。

Sort of know all the other work that you've been doing。

And remember that remote meetings are a possibility。

 some of you this will be your only option if you have the ability to do face to face meetings。

 that is the strong preference because they are much nicer， just facial expressions， verbal cues。

 anything like that， you will get a much higher fidelity。

If you can use headphones over just your computer mic， it makes a world of difference。

 the other thing for remote meetings is even if your customer is remote。

 I would encourage your whole team that is on campus together to book a room and then have sort of you know just a two way call instead of a six or seven way call because that will dramatically change the ease of a meeting。

And if you can avoid it， prepare everything in advance， so you minimize screen sharing。

 jumping back and forth is always a challenge with meetings。

 but just keep in mind that that is an option。Your first meeting with a customer will be an iteration zero meeting。

 so you're going to start seeing a lot of small assignments on B courses for these things as well and we're going to try and put all the information that you need to know in those assignments。

But you， make sure that your customer knows who all of you are so you know。Names。

 maybe a little bit about background， but don't spend too much time on it。

 but you want to build a rapport with your customer so that they can give you honest feedback and you can be honest with them。

 you know， don't let a customer tell you that you have to build everything all on one go。嗯。

But do make an effort to sort of understand what their needs are。

And your goal for your first meeting is for iteration zero。

 since this is going to be a setup is not necessarily to plan all the work， but to get a high level。

You know， a high level setup。Don't plan your iteration one stories after just the first meeting you will meet again to do that。

And， you know， it's gonna be a point of getting just a rough setup up there。

 So those are the goals for iteration0。 It's a little bit more free form because it's less focused on the code。

 But you should， you know， you should get a sense for how things gonna go。

 This is especially important if you're starting up a new application。 you know。

 you'll want to get a much better sense of the customer' needs than just the one or two paragraphs that you've seen so far。

 So be mindful of that as well。 And because this course likes acronyms。

 this is another good acronym Sammoas。 So it's a little bit long to remember everything。

 but it has all the steps。 this is definitely an aandoism。 although food is always a good acronym。

 So start and stop properlyly。😊，Again， be mindful that your customers like you as well are also busy。

 so that's helpful。Andas so every meeting should have an agenda minutes means after the agenda you are following up with notes of what actually happened during the meeting Minute are especially important if you ever can't make a meeting and then you try and later go back to the meeting notes to see what actually happened you will then realize the importance of good meetings。

So， you know， someone who's taking them， you know， they don't need to be you know。

 verbatim word for word notes， but they should definitely give someone reading them later。

A sense of what is important， what did happen。One speaker at a time， super important there。

 just always be mindful that you are not interrupting people。Since this course is mostly guys。

 Most of your teams will be guys， especially be mindful that you' are not interrupting people because it is super easy to do。

 We all have bad habits， but you know。Try your best not to interrupt either your teammates or the customer。

 again， materials in advance。 So demo applications， screenshots， you know， mockups， lowfi mockups。

 whatever you have in advance， send those to the customer。 You know。

 if you had them two or three days in advance， then that's perfect。 but， you know。

 don't send them something 10 minutes before the meeting that says， hey。

 we're gonna meet in 10 minutes。 Can you review this because that's probably not enough time。

At the end of the meeting， make sure you all agree on the action items。

And then during a meeting is a good reminder to set a date for the next meeting。

 if you can get on a nice schedule with your team especially since you're all on campus。

 with your customers， you'll meet a little bit less frequently。

 but hopefully you can pick sort of a standard time that works for everyone。

 although you use your own judgment with what will be easiest as well there so。



![](img/ce3ffcd033543aed7b196740c40d342f_25.png)

Those are the things on meetings that is。About you know， enough to get started for that。

 So there is 20 minutes left to class， so midterm prep questions。

 anything that we've covered so far in the class is a fair game。 So yeah question。Explain once again。

Webs server。Yeah。This is getting into the weeds。 The difference between a web server and an application server。

 So let me see if I have。

![](img/ce3ffcd033543aed7b196740c40d342f_27.png)

Easy， no， no， no， here's one。Let's see if I have easy access to。One of these slides will have it。你啊。

😔，Where is this diagram？Oh， that's a nice bug。嗯。See if it's。Let's see if we can pull up。

Diagram somewhere。No。诶。I should be in here somewhere。



![](img/ce3ffcd033543aed7b196740c40d342f_29.png)

Okay， that'll work。So。What we have for this diagram just so that we can go through the few steps。



![](img/ce3ffcd033543aed7b196740c40d342f_31.png)

So in this diagram here we have。

![](img/ce3ffcd033543aed7b196740c40d342f_33.png)

Our application server， and then it separates the web server。

The distinction here is pretty minor in some frameworks you。

Will maybe not really notice a difference， But in this course。

 we're never going to be interacting with the actual web server directly。

 The Web server itself is the logic。That handles H P requests。

 So getting a request and setting the response back。

 it will be the thing that's responsible for parsing that piece。

 So Necat would be the example from homework where you more directly interacted with the web server side of things。

 So。Rails is。嗯。Rils is really the application server。

 so it sits on top of a web server that handles those requesting responses。

 and you can interchange the web server layer of your rails application。

 So there's a few different ways that you can。You know that you can actually serve and process HP requests for the most part of this course。

 we're not going to talk about the details of there。

 but in your gem files you might see something called Puma， you might see something called unicorn。

 these are different web servers that handle the raw HGP responses and。

They all work with a common API that rails can sit on top of and uses。

 but you won't need to necessarily know how they work and so the application server is the piece that that will define your MVC logic。

 that will define the routes that you respond to all those kinds of things and so。Yeah。

 there is a boundary there， but for the most part in this course。

 will stick strictly on the side of the application server。Yeah， good question。Other questions？Yeah。

 you resources like that。Like what helpers is it？Yeah， okay， that's a good question。😊。



![](img/ce3ffcd033543aed7b196740c40d342f_35.png)

What helpers does the？

![](img/ce3ffcd033543aed7b196740c40d342f_37.png)

Broouts file create。 So the reason I'm going do this is because I kid you not。

 I have done this a thousand times in my life。Which is why it auto completed。

 and it's why this is purple。 And the top of the list is this guide is the most useful guide when you are getting started on rails。

 It is called Ras routing from the outside end。😊，One bit of caution before I do continue。



![](img/ce3ffcd033543aed7b196740c40d342f_39.png)

Is you want to make sure that you're looking at the right version。

 so if its guides that Ruon railils， this is just the current version and there is some way here to get to past versions so you might want to double check that you have the correct version of rails。

 I forget offhand what the way of switching the version 4 docs is。

 but for the most part it doesn't change too much， but you just want to be aware。



![](img/ce3ffcd033543aed7b196740c40d342f_41.png)

![](img/ce3ffcd033543aed7b196740c40d342f_42.png)

So it depends on how you define your resource， but the rails default will give you a bunch of methods and they are all listed here so you get a few getss。

 some posts， the other tool。Yeah， so this is for photos。

This is what we get just from resource photos。嗯。So you have get so an index page。

 a new creation page， the post route to create things。诶。An individual resource， so that has an ID。

An edit resource， so that is a page with a form。That lets you update。A put or patch method。

 So that is the the request that sends the form data from the from the browser to the server and then a delete route。

 which is the thing that destroys them。 So those are the defaults。

 You can customize these the other way that you can get this。



![](img/ce3ffcd033543aed7b196740c40d342f_44.png)

So let's see。 let's not use that or that。So I am in， actually， let's not use ESS engagements。

This may not work because。Rubs being a pain。Yeah， okay， that's not gonna work。呃。

So bundle exec rake Ros is the task that。AThat's really unfortunate， what are you mad about now？Okay。

Okay， we can fix this really quick。I hope。Yes。Okay。

 so rake routes is the thing for your own application that will also list the exact routes that were generated and they go in order of the file as well。



![](img/ce3ffcd033543aed7b196740c40d342f_46.png)

Those are your two references in terms of what what you should use。

 The other nice thing about ra routes is it gives you the exact controller action name。

 So in a terminal， if I make the font smaller， it should。

Nicely show up as a table so this is something for your project that especially if you are getting up to speed on a new project。

嗯。It be a useful thing as an overview， but it lists。But the。Path helper。

 so those are the methods that you could call in your application， the HP verb。

 the UI with parameters and the controller method in your application。

 So resource will give you the what is that1，2，2，7 specific things and then rake routes will give you what's there for your actual application。

 So the rotten potatoes homework is pretty simple if I had that， I would have used it， but。

Computers are hard。But yeah， so that would be the place to check for that kind of stuff。But yeah。

 definitely review the rails routing guide a few times。It's just always a good source of reference。

Other questions。Sure there are other questions on the midterm。

Anything else not midterm related to projects， software engineering， things like that。Oh， yeah。

 you just go over over time on the differences between like Sinara and rails and。Yeah。

So Sinatra verse rails。 So let's just do， let's see if I can pull up the Stra docs。嗯。

Sinatra is useful as a small。Let's see。So。Soinatra is useful as a framework for getting started。

 building really simple web applications。 It is essentially。诶。It。

 it doesn't have model view controllers。 It is the essentials of a web framework that gives you what you need to define routes。

 including the HP method and the path and write a function that would， you know。

 do something useful with that。 So if you're ever building。A really simple application that。

 you know， is making some API requests， Proing some data。 maybe doesn't necessarily need a database。

 Sattra is a great place for that。 It can interact with a database， but。By default。

 it doesn't give you the tools that support that。Most Sinatra applications are designed to really be a few small files and it's designed as a framework to always be lightweight。

 so that's why you know their are examples the code that we give you really lives in one file。It's。

 you know， a set of。Shorter methods that handle the routing for you。And so， you know。

 Sinatra is a really useful tool， it gives you something to practice Ruby as well。

But it doesn't give you the important stuff that we want for rails。 So the reason that we use rails。

 And let's see if。That's。I can jump。诶。So。Is there a good overview。Yeah。Why。

 why rails then as a framework。 So the reason we also don't start with rails is because when you get a default rails app。

 you get a ton of stuff that comes with it， that if you want to just demo you know。

 creating and responding to web requests， you have a lot of overhead to go through。Now， in practice。

 this is an okay thing because the amount of overhead that you do go through helps you set up doing things like writing a line that says resources。

 photos and you get a bunch of methods， you get a bunch of helper functions that come with that line。

 so rails。Really helps you structure。All the app all the functions that make the rest part of a restful web application sort of nice and useful。

 So it gives you a lot of structure。 So your application folder is where all your code is going to live。

 So you know this is going to be things or I should say most of your code。

 not all of it since there are other folders， but you don't write that much that goes into them。

 So you know you'll have a folder for models， a folder for views， a folder for controllers。

Nicely corresponding to the MVC pattern。And if you have a resource called photos。

It corresponds to a thing called photos controller。 It has a model called photo。

 It has a view folder called photos， which all sort of get set up for you。

 and so rails as a framework gives you that structure。You know。

 it doesn't necessarily enforce that structure， but by convention。

 it's easier if you follow sort of restful design with rails。

 And so it gives you that the other really big component of rails that is。

Super powerful and super helpful is active record and so active record is the thing that maps。

Rails and ruby data to the database that you're using。

 And this abstracts away most of the SQL that you would need to write。 Not all of it。

 You still need to understand what's happening with SQL there。

 but it will give you all the tools that you need to do。 So when you've seen things like you know。

 photos do where maybe created at is greater than one year ago， or users do find by username。

that is active record interacting with your database and giving you all those tools， yeah。ビディービ？体 c。

He would not work with。So。It could work with a NoSQL database。There are。

Different so it is designed to so one， it's not just an in-memory database it will connect to Postgres on a server as well and in production that's what it will be doing there are active record adapters for things like MongoDb which are noSQL databases it does get a little bit hairy because the patterns are assuming a relational database but people do use active record with NoSQL databases we'll talk about that later in the semester as examples but for all your projects I wouldn't like expect that you have a need for another database。

Yeah， but yeah， active record is probably one of the biggest components of rails compared to other even Ruby or JavaScript frameworks that make it a useful tool for building applications。

Yeah， good question though。Other things， Ruby rails， midterm related， not midterm related。

Life questions， yes。Can you explain the。So the stories。嗯。

So imperative meaning like you list the steps out like directly， so user stories。

 how you write them will be a little bit up to you。

I wouldn't worry about the specific vocab differences too much。But。

With imperative user stories where。You write things of， you know， this happens and this happens。

 and then I do things in a set of steps。The goal there is that if you write them with step definitions that then correspond exactly to the actions that a user would take。

 you exercise your application。When it's the tests are automatically run in as close a way as possible to what a user would do。

 So you might have a thing that says， and then I check the field for。Administrator。Then I expect。

 you know， the user to be an administrator or something like that。

 So imperative means that you're going to go through literally action by action in。

A browse equivalent to a browser and do it declarative would be you have the option to just say directly updating the database by making a call to active record and the reason you might do a declarative story or a feature step is it would be sort of one step that sets up a bunch of stuff。

You know， the。Let's see。 Let's see if I have these。 So， you know， this would be。



![](img/ce3ffcd033543aed7b196740c40d342f_48.png)

A bit more on the declarative side because it's going to take a bunch of things and just do it for you。

This is。You know， a bit more， well， these are just I should see， so it's not really doing things。

 but that's。You know the structure more on the imperative side。

 the reason to use declarative structure where you just say the world should be like this and a bunch of things should happen automatically is really for speed。

 it can exercise it can be faster to write that test case too because it's easier in a lot of ways to write you know user update and declare a bunch of state in your step definition than it might be to write a bunch of smaller steps that fill out form fields。

 so it really depends on you know where your where your feature stories are what you're going to be using more and that application that you work on。

 but the imperative stuff really gives you a good exercise of exactly what the user is doing but。

Used appropriately， both give you good test coverage and good confidence in the application that you have。

But yeah， you know， and we're going to do our best to also stay away from specific vocabulary questions。

诶。On exams， but yeah， good， good highlight of different ways of writing things。Other questions？

Other things about building applications in general？Customer side of things。Yeah。

first meeting like this week。Yeah， when should you have your first meeting。

 if possible this week is good that gives you more time I would。

Like what I would encourage people for team meetings。Is the sooner you can meet with the customer。

 the sooner you have a chance of just getting started and getting familiar with things。

 especially since what's probably going to happen for most of your first meetings is you're going to come out of that meeting。

 you're going to think you understand things。And then you're going to look at the code that you've been given from the past project。

Or you're going to think about creating a new rails out from scratch and you're going to be like。

 okay， holy crap， I don't understand like five things that I thought I understood。

It happens all the time。It's normal。 But， you know， the sooner you start that process。

 the sooner you have a chance to go back to the customer and say， hey， we now realize we have these。

 you know， three or four more detailed questions。 So I think sooner is good。 if you want to just do。

 you know， sort of a pre meetinget of like， let's just get to know you。

 be mindful of the customer' time。 you know， so they don't have。You know。

 an infinite time to meet with you， but we you know we have told them that they should probably try to spend you know one to two hours a week depending on their commitment on this class project so one of those hours should be you know meeting with you if possible so if you want to do a short intro meeting that's like a half hour just say let's get to know you let's hear that you know the high level requirements and then we'll come back and do a first more detailed meeting that can be really useful especially if you just have no context for what this project is I would definitely recommend doing that。

Or maybe even just setting up some email conversations。y好。哎呀 yeah good ahead。So。

Also for like the customer meetings， there is like a time conflict with like other members of the group。

They aren' able to show up。How would you resolve that？Yeah， so time conflicts and meetings。

The goal should be to have all of your group members there as possible， it is 11。

 so I'll answer this， but if you need to walk out， go right ahead。If you have time conflicts。

 what I'd say is have as many people there as possible if it makes it easy to schedule a repeated meeting where one person can't be there。

 you just need to make sure that that person is as involved with the project。

 so keep them up to date， have a second meeting with them。

 make sure they're hopefully always pairing with someone who is in the meeting right。

If you really can't make a third of your group there， then。You know。

 you might want to try some like video hangouts or alternating times or something like that。Yeah。

 good luck on the midterm， 7 PMm。 we'll see you there。You'd better see you there。Mmm。Where's TV？



![](img/ce3ffcd033543aed7b196740c40d342f_50.png)
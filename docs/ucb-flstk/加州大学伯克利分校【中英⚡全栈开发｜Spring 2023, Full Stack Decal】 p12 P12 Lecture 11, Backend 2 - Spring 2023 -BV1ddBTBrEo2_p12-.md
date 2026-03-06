# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p12 P12 Lecture 11, Backend 2 - Spring 2023 -BV1ddBTBrEo2_p12-

![](img/18f8b419755349cc15567673482ae2ee_0.png)

哪我。谢。一个。不对。对下。我这个。可以。嗯。Thank。嗯不。哦，证清楚。Hey everybody， it's Berkeley time， so we'll be starting now。

Welcome everybody， this is lesson 11 we're going to be doing Express and MongoDb and I'm never once again。

So just a quick recap on what we covered last time last time we covered HtTP RE and Postman HtTP is a protocol that allows different computers to communicate between each other over the internet so you have client side as well as server side servers are the areas which contain all the information that then sends the information back to the client which is what's making the HtTP requests in the first place then you have RE APIs rest is an architectural structure for APIs and APIs or application programming interfaces which allow two applications to communicate with each other these two applications could be just your backend and your frontend but it could also be two separate applications like LinkedIn and your application communicating with each other and then finally we use Postman to test out API endpoints or to test out sample HtTP requests it just displays it in a really nice way and allows us to know that we're doing stuff properly that's pretty much it for this type of stuff that we covered last time and here's like kind of the structure of exactly what we covered last time we。

Like the web app in your browser so that's your computer。

 you send a request over by putting a website or by call or about making a request of some API that sends some information to an API which processes your request。

 sends that information over to a server which can collect information from a database if necessary and if it is necessary it'll package that data and then send it back to you in the form of a response so that's like a pretty good summation of how HB request work combined with everything else we discussed last time。

😡，The next thing is express you guys may have already seen Express before if you've started on homework 6 or like maybe mentioned in reference in the past couple of lectures but Express is a backend web application framework for note JS so you may use Axios that's more so for frontend Expresses that for backend and it's designed for building web applications and API so it's really useful in that sense and here's like an example of a snippet of code you are first creating an express object and then making the express server on your backend and then you're writing your HP request paths down below so you're writing app get flash you're getting the request and response and then you're sending a response with the following information and then you're also listening on the port provided so that's just like basically starting up your app and that port and then you also creating get request are there any questions regarding express or anything I've just gone over including the recap one last time。

Yeah so whenever you're importing so what you'll have to do is first you'll have to NPm install express and then you'll have to make an express object like this so in back encoding views require instead of import。

Any questions apart from that is a great question， any questions？

CoolSo then we're gonna move on to databases so databases are organized collections of structured information or data typically stored electronically in a computer system and there's two main types of databases you first have SQL databases which are like Postgres and Microsoft SQl server these are like a Google sheets where each line of data corresponds to one database and you have different columns that correspond to different categories that each data has so yeah just think of this like a Google sheets and that's basically what it is and the other type of database is no SQL databases which are not like Google sheets instead you define schemas which are structures in which objects that your when your data is selected that's how it may look like so you may have like a user object with like email username and password that's like the general structure of how a user will look in your database and you'll just store those objects in your database and then your database will collect information whenever your user logs in per se and then store that information like that so instead of you like line by line writing out like。

person you'll create objects for every single different type of data you're storing so and some of those examples include MongoDb and DynamoDb and today we're really going to be mainly using MongoDb and Mongodb is just a no SL database that's pretty easy and the learninging curve isn't too high so that's what we're going to be starting off with and that's what you guys are going to be using on the next homework I believe are there any questions regarding the MongoDb or databases。

Cool then moving， sorry VerQQL SQL is the flexibility for the manual structure。

So I wouldn't say that's like a major difference and just be in the way data is stored so in SQL databases everything is line by line。

 whereas in in these in like no SQL databases it's object based so you if you worked with like objects before in previous programming classes that's how each kind of data each data points is stored it's stored as an object versus being stored as like a line of code or just like a line of text。

So is it a collection of objects yeah？So now we're gonna be moving on to the demo but before we move on to the demo I just kind of wanted to show you guys how Mongodb kind of looks when you make a database on it So Mongodb works by you making like projects and then within those projects you can have databases so right now I have this thing called cluster one that is not the project name that is just the like that is the like upper category in which projects are contained so you can have multiple projects in a cluster my projects's name is web dev demo and then I can have databases within that specific project so in this like in this database within this like project I have sample AirbnD listings which is just the default database they provide you and I'm just going show you guys how the database is kind of structured so if we scroll down we can kind of see not is it like too small or can you guys see。

I'm just gonna to zoom in but if you can kind of see every single like kind of block you have right here。

 this block represents one housing unit on Airbnb so it has like the listing URL somewhere around here the neighborhood overview the description the ID the name these are all characteristics of a house that's up for rent on Airbnb so every single one of these blocks so there's like a bunch of them if you keep scrolling every single one of these blocks they sample house up for rent on Airbnb so that's kind of like how your database will be structured and as you can see they're like objects because they have multiple fields that can be filled in and can be updated and we can also filter for specific values by first doing curly braces then writing the name for the field so let's say I want to get the name of something and then I can get that value so I just want this specific data points I can do that andvoila I've queried results for this specific object so you can find different objects by putting in values or putting in fields and then putting in the respective values。

Last time we went over how to query your results using HP requests。

 this is very similar to that and this should be like pretty simple to understand if you guys were here last time and if you guys understand query which is not too difficult with a concept yeah's up so it's atationary yeah it is pretty much a dictionary yeah。

Any other questions？So cool that's just howgo mongodb databases are structured and now we'll like go into kind of building our own so in order to kind of follow along if you guys do want to get like mongo S install so if you have homer you can just install like the mongo shellll script command which is going to be necessary for making our database on the command line so right now let me just CDd out of this directory and let me make a new directory they only call it like practicing mongo or something let's go it mongo f。

Okay CD Mongo cracked and then once I'm in that directory I want to create a new like kind of project and the way I do this NPm in it this will create a package do lock JSON file which I can use to store dependencies and I can put like known modules into so like right now it's going to give me like a bunch of information that I can potentially put in I don't care about that right now so i'm just going to enter and everything but if you guys are making your own projects from scratch you guys can use NPm in it and then for instance where is it git repository you can put the git repository in some keyword author license you can put that all in for now we don't really care and that's fine me。

So great， let me open this guy up in VS code， fantastic， so I'll full screen this。



![](img/18f8b419755349cc15567673482ae2ee_2.png)

Okay， and the first thing I want to do is I want to make an index Js file that's where like all my backend code is really gonna to go kind of like your HTML files you guys were working with in like the first couple of lectures。

 you had an index by HTML file well for the backend it's the same thing is just index Js so that's the first thing we kind of want to make and the next thing we want to do is we want to install all dependencies and the dependencies you guys will need are the following so NPm install dash save this will save the。

Whatever dependencies you get to your specific package lock JSON file so the dependencies I want to install or express remember that's the backend web application framework for the servers that we're going to need so that is essentially very important then we're also going need to install cores this is for IP routing This tells us which IP addresses can access our specific database and can interact with our API we willt be using that too much in this lecture but it's still very useful to have and you guys might need to use it on your own projects then we'll need to install mongoose mongoose allows us to communicate with Mongodb like our database in Mongodb so allows us to do readwrite operations as well as update or access information from the MongoDb databases so that's also something well need over there and then we'll need something called berypt JS this is really useful for encrypting your passwords so we don't want to store users passwords like just their password in the database we want to encrypt that somehow and we use BCrypt Js to do that and the next thing we'll kind of need is JSON web token。

So when a user signs in they'll be sent a JSO web token which will be stored locally on their device so every other time they log in that JSson web token will just be sent over instead and that'll help them sign it This is just like an added layer security and that's something we like to use and I'll get more into like exactly how we're going to use it and then we're going to use express validator which helps make sure。

Which helps to make sure that our specific routes are correct and it double checks like it allows us to basically do a lot of routing through HTP requests and then the next thing we need is nodemon。

So nodemon is kind of like NPpM start but for backend server。

 So whenever your server's update or whenever you make any changes to any of your files。

 it'll just restart the server for you so you won't have to continuously click over and over again and the last thing we'll need is dot Eb so you guys may have played around a little bit with dot files like the NPpm module just allows you to kind interact with those files we're not using that but this is just useful for your own projects so I'm just gonna NPpm install so you guys know how to like have seen it before at least they'll click enter and then hopefully this will install and then while it's installing I want to go over the JSON web tokens so let's go over here so yeah so tokenbased authentication starts with you sending some login data which is like your username and password and then with the database or with our servers will make a JSON web token with some secret code and that JSON web token will be like an encrypted a long string that your browser can use to continuously access our website and we'll send back the JON web token through an hp response and then we'll also have like authenticated requests with J。



![](img/18f8b419755349cc15567673482ae2ee_4.png)

![](img/18f8b419755349cc15567673482ae2ee_5.png)

T in the header so whenever we're trying to resign into the application we will send an HtP request with the JSsonN web token in the header request and then the web application will look at that JSO web token verify that it works and then say fantastic you're good and then logs in by sending a response back that says you're good and then logging us in giving us all those features like come with logging us in so that's like a good overview of how JSsonN web tokens work and then here is like that much more into depth so you make a post request first with all of that information then you check if it's an existing user and then you save the user to the database and then you return the message register successfully that is how you make a user so if a new user wants to sign up for your service that is an example of user registration then we do user logins which is you post the username and the password then you make awT token you send it back over and then every repeating time they just use the JWT token to make sure that they're good to go with the application So today basically what we're doing is we're just making this。

I think we're making the user authentication service。

 so creating a way for users to sign up and log into this application。

 and that's like the crux of what we're going to do today。

Whats up kind of these three and four are connected I how the1 three that sort but I'd wanted to go a second。

嗯。So when you're initially like logging in， once you've just made your account and you're logging in to the application。

 you'll send the username and the password over and then you'll get the JWT token back and once you get that JWT token that will be stored locally on your device and you'll get that you know all that information over here。

So then every subsequent time you come back to the app。

 you can just use the JWT token and that'll allow you to get it。Yeah。

 so just the first time I use user login and the subsequent times you go through steps four through six。

Yeah， any other questions？

![](img/18f8b419755349cc15567673482ae2ee_7.png)

CoolIf there are no questions I'm just going to continue so as you can see there are a few new files in our like Vs code we have index Js package lock Json and then Packinson Json so all of our new kind of modules have been downloaded into our repository and the first thing we're going to want to do is we're going to want to make an express kind of server So the way we do that is。

Like the following so it requires kind of like import and it does the exact same thing is just we use that on the back end then we're also going to make this thing called a body parser This is useful for like parsing information about JSO so like whenever you're send some JSsonN information body parser is use to kind of take that JON object and then make it readable and then like you can play around with the data that you get from there so we're going to require body parser。

And we're going to start our app。Whathoops。Great， and the next thing we're going to do is we're also going to make our port。

And we can just make it like that so that our port can just be local host colon double slash 4000 so i'm just going to leave it to that you can make it whatever you want is just going to change whenever you're doing like requests or anything like that The next thing we're going to want to do is we're going to make our first path which is going to be app dot use and then we're going to want to use body parser。

And then we're going to add this JSON method， which is just going to parse the JSON whenever the JSON is like pushed into our database。

So that could be like whenever you're sending over a request you'll sign over that data in JSON this like appt use so like the flow of the flow of the request will go from the top of this document all the way to the bottom so this body parsel will just kind of parse through that JSON and then give me and allow me to kind of use this in the next couple of lines so that's going to be really useful whenever i'm writing the next lines of my code then i'm going to do app dot get。

Request or sorry app do gets slash so whenever somebody goes to the slash on my webage they're going to get the following information and I'm going to do request and then response and I'm going to make an arrow function and then over there I'm going to make a response do JO adjust the message。

Message。你 a。Is。Working so this just shows for me at least that like this application is working so far and there are no issues that I can kind of see in that so this is just for me to know that this application is working and these like few couple of first steps are great and then the last thing I want to do is i'm want to do the app dot listen thing so I showed this earlier in the presentation but i'm going to want an app dot listen to start the server up at port 400 so i'm going to want to do it at port and then i'm going to want request。

Response and then another arrow function。And then I'm going to want to console。 log that D server。

Sver has started。Ced。Dollar。This so this will just give me my port number and this should be logged whenever I like make a request to that specific port any questions on any of the code that Ive written so far。



![](img/18f8b419755349cc15567673482ae2ee_9.png)

So so i'm just going to go into postman and just see that it's working so I've like kind of just one playing around with that and we can go local hosthen4000 slash send。

我怎了。

![](img/18f8b419755349cc15567673482ae2ee_11.png)

Yeah。Oh my bad I forgot to start my node backend so the way I do that is NPx nodemen nodemon indexjs so that starts up the index dojs and activates it so that this server should be working out andvoila now if I make the get request hopefully it worksvoila so there we go my backend is working and it's fully functional and it's active at that specific local host and I can check that in the console log server has started at port 4000 so fantastic any questions on what I've done so far is there any confusion is there anything you guys want to ask or anything I should clarify。



![](img/18f8b419755349cc15567673482ae2ee_13.png)

![](img/18f8b419755349cc15567673482ae2ee_14.png)

All right， what is the slash in the get？So yeah that's the file path so whenever a user tries to go to the website's URL and then has this slash right there that is like I should just get that information that that is that is accessible and my like application is access to that area and I can like manipulate some information there so that's so right now like this is this is just for me to understand that my code is working this is not like something you'd have on your website this is just when your're testing stuff yeah。

So just like to clarify I guess like the first part of the part in the string that is like the resource or file path that the user goes to based on your like website so in this case that's just adding a slash after your domain name and when they do that it'll take the request there's obviously a no request here because it's a get request and then it'll send a JSON response saying the API is working so that's pretty much a good question。

So so yeah what's up so is the are you to use that for like data Yeah so the request is whenever like a user goes to a specific page on your application they'll ask hey。

 they'll ask your server can I get some information back and redefine what information we're going to give back to them so whenever they go to the slash slash part we'll give them this information we'll give them this response from the back end。

Yeah。Good question。so what the how is the？For you want to something with the head is。

Yeah the Re so RQ stands for request so whenever anybody goes to like a specific part of your website they'll send over a request and you'll have to give back a response so my computer if I go to YouTube do co it'll send a request to YouTube servers for some information and YouTube servers will send that back in the form of response there are multiple types of like methods you could have here so right now we're using a get method all that does is get some information from the people are from like the servers so in this part like the request isn't super relevant it's just a response so yeah yeah。

That's why it's kind of like faded out。But yeah。Any other questions？

Okay cool and the next thing I'm gonna to want to do is I'm going to want to make a new terminal I'm going to understand it to bash because again I'm getting some weird errors with ZsH so I'm just gonna to work with bash and in bash I'm going to just type Mongo S this is the Mongo shellll script and what it should do for me is create a sample database for me to work with so hopefully it does that beautiful it did very happy with that otherwise I probably would have like did but here is my specific So here's like here's like the URL which i'm connected to and then if I scroll all the way down this is the name of the database So this is just like a sample database and made for me just to play around with this when you guys are making your own apps if you go to like Mongo D there should be like。



![](img/18f8b419755349cc15567673482ae2ee_16.png)

like go out of here there should be some option to kind of connect So if I got a like web dev demo or something yeah。

 there should be this option called connect and you can connect in a variety of ways so you can connect through the Mongodb shell you'll get like a URL so if I click on that I don't really care right now because i'm not going to do this but you can take this line of code down here and you can just plug that in to your terminal and it should automatically connect you to the database so this is something you guys will do when you're making your apps I'm just making like a test database for me to test out a couple of features and show to you how they work。

 but apart from that yeah this is something you guys can use in your projects are there any questions regarding that。



![](img/18f8b419755349cc15567673482ae2ee_18.png)

so Mongo think Mongo maybe be like platform as a service or is it or how does it work exactly because'm a little I'm just a little confused if you cant install it as a。

Like a node package。啊。Yeah I guess we're about the nature of So MongoDb all it does for you is provide like database support and it allows you to kind of connect their database with your application so we didn't really download Mongo as a like a node repository or as a node module what we did is we downloaded a service that allows us to connect our application to Mongo as a node module so we don't download Mongo itself Mongo store is probably our database somewhere in the cloud I think they give you the choice like AW as Google or whatever Microsoft I think Microsoft is your their story of data up there and you just connect it with your web app that's basically what they're doing so they're offering like cloudbased databases and you just connect it with your application and you have flexibility in making those databases whichever way they fit your application。

Yeah， good question， any other questions？If there are none then the next thing we need to kind of do is we need to create our database and kind of format how our app interacts with it so what we'll need to do is we'll need to create a config file and then a database do Js file you can name this whatever you want i'm just aiming a Db dojs so I can keep track of it and then the first thing I'm going want to do is allow us to connect by making a mongoose object with a mongo Db。

Daatase that we just made so cons Mongos equals a require mangos this is just how you import stuff in the backend and the next thing that I'm gonna w to do is I'm going to make a mongo URLri so this allows me to get access to my database at a specific URL so cons Mongo URL and that is equivalent to the following string down here so right over here everything up till there that should be what I copy into that and then I do slash the name of the database so slash test this is going to be slightly different when you guys are connecting your own database from their website and you guys are going to have to figure out how to optimize that so this is just how we're doing it for now but you guys will have to change it whenever you guys are making your own applications and then the next thing we want to do is we want to make and initiate Mongo server function。

Ser。And we're going to want to make it a。They will function生。Great， and within this function。

 what we're going to want to do is we're going to want to put a try cap statement where we await mongos。

To connect to the UI so Mongos allows us to connect to different applications and we're going to allow Mongos to kind of connect to the Mongo UI we specify up there so we're going to want that as our first field and then as our second field we're going to want to have a field called use new URL parsor。

And that should be dot true so this just parss the URL and allows us to get access to that database so this is an await function we're going I want to await for mons to connect to this and then we're going to want to proceed down our code and then once we do that we're going to want to console do log connected to DB just to tell us that hey this has worked we are now connected to the database。

嗯。So that's that part and then we're also going to want to have a catch statement where we catch any errors that happen so in case like for some reason this doesn't work we want to catch that error and then console log that console log that error so that we know what's going on and why that error is happening and then we're going to want to throw the error so that just like stops the app and finishes it off so now we can kind of go ahead and export this function so we'll need it was hover in red。

This should be probably， I think， async。Right， asynnc。Yeah。

 it's going to need to be async and then we're going to do module。

t exports equals initiate Mongo server。So what this basically this last statement what it allows us to do is export any functions we've created in a file and then export it outside so we can use it in different files and the way we can use it in different files is we can just like for instances cont initiate Mongo server equals require so we use the require statement and then we use the relative file that so dot dot slash。

嗯。I don't know why it's going all the way there dot slash my dot slash conflict slash so this will get whatever we exported from that specific file into this initiate Mongo server kind of thing and then over here we can just initiate。

Monggo server boom like that and now it's sure work so if we go to our other terminal yep there we go now it's connected to our database so through that process we've kind of used the database do Js file and the configs to connect our mongo database that we made in the terminal to our application over here are there any questions about what I did in those steps。

哦啊 so。Then I'll just continue。The next thing I want to do is I want to make our user schema。

 so I want to make a models folder， so this is going to contain the models of how my data is going to look so modelss。

Delete。So I'm going to want to make a models folder and within that folder'm i'm going to want to store the different data that I'm going to want to have so for now it's just going to contain user data which is going to be an object that shows how user data should be stored in my database so I'm going to want to make a models folder over here and then within that models folder I'm going to want to make like a user JS。

And then in there some things that I might want is mongoose again。

 so mongoose equals require mongoose。And then other things I may need at the very top of my file is this method called user schema。

 so this is like an object I'm creating which is the which which demonstrates how user data should be stored within my database。

 so constant user schema sh schema equals mongos。Do38 model， I believe。Mgots你 my that？嗯。

And then you do like this， and then you can put different fields in here so you can put username hype。

So you can put different like items you want within your objects within this larger object and what you need to put is the type of the object as well as whether it's required so we can just quickly copy paste this specific line of code down the file。

And then what we need to do is we need to change these specific entries so maybe one we want to have is email the other is password and the last one is created at which tells us the date at which it's created at so over here these types should beul string they should also be required otherwise our object or our code should not be able to make a new user object so we want to make sure we have all these fields and then for this last object we want the type to be a date。

And then we want the default value of this to be date。 now。

So that's just gonna to give us like the current date and make that the created value if no created value is passing so we do need the upper three。

 but for the last one we can just make that on our own so that's pretty much it for this and then we want to make sure that we export it and the way we export this is a little bit kind of interesting and the way we export it as module exports equals mongoose do create or mongoose。

 model and then we put a string name in here and then we export the user schema so user schema so there we that's how you export user schemas out of your thing you need to create a mongoose。

 model object which takes it whatever data you've made up there and then exports it as a model which we can use to kind of model how data should be stored in our database are there any questions regarding the user schema or what I just did right now。

不是不是你的对。So the user string is just a name I gave to it I just made a user because the cell user object should be user objects should look so whenever I import it it has this name I can also change the variable name to store this information。

Any other questions？Okay so so the next thing I'm going to want to do is I'm going to want to go to routes so what a route is is it defines different ways in which my API can work so given a specific file path what should my code do routes can determine what my code should do given a specific file path and we can so previously we were kind of doing this in our index dojs where we have app dot get colon slash this is like the sorry or quote slash this is getting us the file path to like the get request area and we can do and we can like writet like post or appt get for all these different file paths but at the end of the day that's gonna be really tedious and one way to kind of simplify that and make it easier faster process is by using these things called a routes and roots can contain all these file paths within it and what we should do given those file paths so I'll show you and when I'm showing you guys it'll make a little bit more sense but we're just doing like this。

App get thing and just pushing it into roots instead just to make it a little bit more simplified so within roots I want to create a user dojs file and this user i'm calling it user。

js because it's it's file paths for the slash user so whenever whenever anybody in our website type slash user this roots are going to handle all the possible commands you can have there so that's like kind of the point of roots and that's how we're going to use them。

So it'll make more sense as I go， but just for now kind of follow along so we're going to have birth and express object where we're going to require express。

Same way we've been importing Express dot before， and then we're going to have a router which equals express dot router。

So that should be yes， that should be a right syntax and then we're going to want a command and the way we make a command is by writing the name of the object the name of the router object so that's router and then router dot post and we're going to want to make a。

Yeah， so it's going to be， I believe it's going to be like this。

And then within these kind of parentheses we're going to want to write the specific file path we want to go through so for the first one it's going to be through signup so whenever anybody types user slash signup they'll go and this router will be activated whatever code you write before all that code is going to be activated whenever anybody tries to sign up for application so sign up。

嗯嗯。And then when they sign up， what we're going to want to do is we're going to want to make an async function with a request and a response。

And。Like that and then once we get that async function over there we're going to want a little bit of data from the request so whenever anybody is trying to sign up they should send some data in the form of the request so that should be the username。

 the email and the password so I can just make three objects and then make that equal to request do body and then this will get me like whatever information they pass to me so that's going to be like the username email and password and the next thing I'm going to want to do is I'm going to make a try catch block so I'm going to make the try statement and within the try statement what I kind of want to do is I want to I want to make a user variable that stores whether this user exists in my database and the way I'd kind of do that is I do await user do find one and then I put in the email。

So this would check whether a user exists given like there is the email there So remember the user object is the schema we made the dot dot slash model slash user there are predefined functions in Mongodb that allows to query the database and find out whether specific users exist given the data we're sending in So right now we're using dot find one to see if there exists a user that has the specific email that's being passed in and if there does we're going to make an error statement because this is a user signing up for the first time So they're just making account there they shouldn't already have one if they do that's an error so we want to make an if user so if the user exists then we want to do a few things and the first thing might be we want to send a res dot status 400 So if you guys remember from last time we have different statuses under which our responses fall under so 400 is a client side error which means that the request they sent was bad they're sending a requested。

lash signign up or create a new account when they already have an account that is a bad request and part of that bad request。

 we should send them back like some JSON telling them that hey。

 you already have an account or like the user already exists。😡。

So this is just like a JO object that's being sent over that tells the user hey your account already exists。

 why are you signing up， you should do something else right and this is just there and this just like kicks us out early in case they made an error when they're signing up。

So。We error check for the fact that they might already have an attempt。

 that's pretty much what this code block is doing。😡。

And the next thing we want to do is we want to if that is not true。

 so if that is true like if they already have an account。

 the code ticks out here because it'll just return a response do status of 400。

 but if that is not true， we want to make a new user object。Which contains the username。

Email and password so we want to take the values we got from the request do body earlier and then pass them into a new user object so remember we made schemas those are like objects and we can pass in certain values into them and here's an example of us passing the username email and password we got from the from the request and we can put that into a new user schema and we can create a new user object which is going to be the new users kind of login。

Are there any questions about what I've done in this step or anything I've done in the past up。啊，第三系。

Oh， which part are you're looking at the first one and then the。

The user yeah okay so whenever you're passing in like variables we're getting variables from a request body。

 you want to use curly braces that's like one instance where' you use curly braces and another instance where use curly braces is when you're making a JSON object so if you go to the response that status whenever we're making a JSON object we first had the parentheses which calls the JSON method and then you have to have curly braces inside of it just to store all the information within the JSON request and if you want to have multiple fields you can separate them by comments and then for whenever we're making this new user object we need to maintain like the value of these variables and pass them in and the way we do that in JavaScript is by using the curly braces so that's why I've use like the curly braces so much in my code does that make sense。

So so so far we just kind of have a new user object and the next thing we're going to want to do is we're going to want to encrypt their password and the way we do that is kind of interesting so we first make something called a salt and I'm going to need to import to be encryptpt so。

The way I import I've done this a few times， but it's just like this be crypt JS so this import the be crypt kind of module we downloaded earlier and this helps us encrypt our password so I can do be cryrypt dot。

Erypt do gen salt and then I put a number in here and what salt is this is like a little bit more advanced for computer security it just adds random numbers into your password so that whenever it's being encoded it's harder for hackers to guess because now they're just like a bunch of random numbers in there and they're not going to be able to just like kind of guess it and figure it out so that's going make like accessing your password and encrypting your password even better and accessing your password even harder so that's why we use salt and then I'm going to want to hash my password so password I'm going to want to that set that equal to or'm I'm going to want to take the field so I've created this new user object so I can get their password。

😡，And I want to hash their old password， so I do salt and then。Ass rate decrypt dot hash。

So this is going to take the salt and their password and it's going to hash the password based on the salt and based on some like other hashing hash code method decryptas so what this will basically do is just encrypt the password now hackers really won't be able to guess it and I've made it slightly more complicated with salt that's like the generally good way of thinking about it。

And just a error I made here this is supposed be password and this supposed to be solved yeah so youve got the password first and then the salt afterwards but yeah so that's how I've basically encrypted this password and then after I've done this I want to save the user to our database and the way I do that is I use this save method and the save method takes the user object and then pushes it into our database so I've collected all this information I made this user object but I also need to put it in my database。

 this is how I do this I await user that save and that's pretty much it for just making a user object and then in case there's an error somewhere in between this I'm going to want to catch the error and then I'm going to want to maybe send like I want to console the error so I canops。

嗯。I'm to want to console log the error so that helps me figure it out and then I'm also going to want to send this as a response。

 so response do status 500， which means that there's an internal server error。

 which means we made a mistake on our part and it's going to tell the user like maybe like I want to send like a message that just says error in saving so like whenever the user like for some reason can't make their account it's on us we just send this we just send like this message to them and we also need to send a resdot status thing because if you look at the very top we take in a request and then send out a response so we're going to want to not just throw an error we're also going to want to format that error as a response so that's why we do the resdot status 500 send error and。

Are there any questions regarding anything I've asked or？Okay cool， if not。

 what we can do from here is。We're going to want to add a JWT token at the very top so remember when I was showing you guys how users sign in。

 they use something called the JWT token well we're going to have to make that somehow and we use the JWT modeling or the JSON web token module we made so we just import。

Jason， web token？At the very top and the way we do all that information is not too difficult we just do something called constant payload and we make this。

 I believe in arrow function， although like。Yes， constant payload。

And then we make a function like this， and that contains like the user's ID。嗯。

So this should be working with the error。Yeah， I'm not 10 I'm not sure what the error is。

 but this should be fine maybe it's expecting a comma down here。嗯。There we go。

There we go so that stores an ID in this like new user object we've made within payload and that contains a user ID so I didn't mention this earlier。

 but in our Mongo Db server so in the database。

![](img/18f8b419755349cc15567673482ae2ee_20.png)

To to。Browse collections yeah so in each specific object we've made we have an ID and that ID is a specific number that Mongodb creates on its own and it's unique for every single object within the database so we just kind of store that within every single object and then we can kind of use that to our advantage and we can use that to encrypt and make the JwT token in the first place so we're going to we're going to need to make a payload that's how you make a payload is just a user object with its specific ID and we're going to use that later on whenever we are creating the Jwt thing and then the next thing we're going to want to do is we're going to want to use this method called Jwt sign and we're going to want to make the payload。



![](img/18f8b419755349cc15567673482ae2ee_22.png)

Then we're going to want to make a random string so you can put any string in there in here and this is for creating a signature for the JWT token this is a little bit out of scope for whatever we're going to go over but this is just useful for encryption and making sure that we have the correct levels of security which is really important so for now you can just put any string you want just remember this string so let's say I want to put random string it doesn't matter。

And then I'm going to also want to add an expires in field over here。

 which is an allotted amount of time into which this JWT token expires in so after some period of time you guys may notice you need to log back into an account like it doesn't remember you for some reason that's because the JWT token has expired so it has like an expiry date attached to it and companies will often just continuously change the random string they've attached just to make sure that their security is at a very high level so your JWT token might expire often and you might want to attach that quantity over here so for right now we don't want it to expire really fast and we'll make it 10000 seconds。

So it'll expire in 1000 seconds that's a little bit near like a weakish and the last thing we'll want to do is like in case for some reason like this is not working there is some issue going on we'll want an error token so we want to pass in a error and the way we passed in the error is a little bit interesting so the syntax is different from what we've doing we've been doing in the past so if error throw error and if there's not an error what I want to do is I want to send a res dot status 200。

As a JON object and I'm going to want to put the token inside of it so this will just send the token back to the user so they can store it on their side and that is how you make a jwt do sign and it seems like everything is good here and the next thing that I'm going to want to do is I'm going to want to export this router so at the very bottom I can just do module do export equals a router so remember this is my router object I've made a method within there and I've defined that method and now'm is all I'm doing is exporting that router so I can use it in different files so I can come back to index do js and then I can import the router。

Dot slashros slash user so this will be like my router for my user and for now i'm just going to change the name because I don't have a user in here so i'm just going to like make that my thing and then over down here i'm going to make an app dot use slash user slash or and then that's going to be my resource path so whenever I go to the slash user area in my file I'm going to use the router called user。

So this basically makes my code look a little bit nicer and then also kind of abstracts or kind of splits up the tasks separately so it looks nice and easier for me to handle so all i've done is instead of writing the app dot post slash whatever user slash sign up so instead of writing all that stuff here so that would be like app dot post slash user slash sign up。

Instead of writing that here and then writing all that code down below i've just put that in the router file that's all i've done so the routers are just like taking that away and putting that over there and I can just use that router object to make app done use instead so it just makes my life simpler and allows me to error test a little bit more easily that's the only reason we do it are there any questions regarding something i've done or any issues like understanding something。

Okay and if there are any questions just interrupt me at some point and then we can kind of go over it and now we're going to want to test that our methods are actually working so i'm going to want to go to the specific directory and i'm going to want to do a post command so。



![](img/18f8b419755349cc15567673482ae2ee_24.png)

It's glitching， so I'm just going to add a new field。嗯。对。

Why is it not allowing me to do this I'm just going to restart postman real fast because it's acting up but basically what you want to do is you want to check whether that endpoint is working so you'll want to make a post command towards slash user slash sign up and it should work or it should just send the error message back so let's go ahead and do that post slash user slash sign up and then in my body i'm going to want to send a JSO object and the way you do that is scroll up there is JO over here。

Okay。And I believe it's like this user name off my back youve to put it in quotes so user name so Jason has like its own specific synaxia to put the keys in quotes and then you make it equivalent to like some username so let's say it's Bob and for the email。

Let's say that is equal to bo@chmail。com and then finally we have our password。

So we can just put in something random for this and it doesn't really matter， it can be like BobO 1。

 two， three andvoila pencil。This should work now。是。A syntax error。Grees index double quoted。好，麻板。

So let's try that again。Cannot post slash user slash signup。



![](img/18f8b419755349cc15567673482ae2ee_26.png)

Why is that？嗯嗯嗯。

![](img/18f8b419755349cc15567673482ae2ee_28.png)

Should work。Okay。It is a JO。so there seems to be a slight error I'm going to see if I can kind of figure this out and this should give you like a good idea of how to decode whenever you're writing out your database so you'll get issues like this sometimes and we just have to figure out exactly where it's going on coming from so cannot post slash user slash signup so maybe I made the link wrong Yes that was the issue you're supposed to put the path over to there so I forgot to include a s there and now it should work I'm hoping there we go user already exists so in my previous commands I probably already filled that in so instead of doing that let me change the email to like Bob 123。



![](img/18f8b419755349cc15567673482ae2ee_30.png)

![](img/18f8b419755349cc15567673482ae2ee_31.png)

![](img/18f8b419755349cc15567673482ae2ee_32.png)

What is now your issue。App crashed， okay， great。So we're just going to restart。

N thex nodeman index chains。

![](img/18f8b419755349cc15567673482ae2ee_34.png)

Okay， now can you work？E and saving beautiful and now you're failing again Okay so I don't know what's going on and we're going to just try changing this person entirely and maybe if it works so person。

😊，And then we're going to make the password for single 1，2， three， so so my laptop isn't done。Hey。

 what is your you know。I would say okay， so there's some weird thing going on and it's not letting me do anything。

 so let's try this again and I'm going to make a raw JSON object。嗯。遇上你咯。我问你。Hello。喵。HelloGmail。

com and then password。So we can just put a random password in and we want to make sure it's a post request。



![](img/18f8b419755349cc15567673482ae2ee_36.png)

What is your issue？Okay maybe it's giving me okay so it's just crashing every time and there seems to be like some error within the crypt so maybe i'm not importing it properly that's maybe the issue so let's go back to be cryp Js and maybe I haven't installed maybe that's the issue so control C NP pm。

Okay， what is your issue？My badt， it's not supposed to have a dash or not a dot in between it。Okay。

 well let's go back to the DB dojs non DB dojs roots file and let's make sure that E cryptjs is right。

This looks fine， I don't understand what the issue is。

 maybe the issue is in my hashing so let's see if that's the issue。Yes。

 so this could be because i'm not putting the await weight function down here。

 so it's not waiting for the salt to be there and that's why it's giving me the issue so let's put await weights there and hopefully this now works I think it should but。



![](img/18f8b419755349cc15567673482ae2ee_38.png)

You never know。嗯。Oh。

![](img/18f8b419755349cc15567673482ae2ee_40.png)

Okay， let's find out what else， oh， I havenve not started my server， that's why。嗯，麻拜。



![](img/18f8b419755349cc15567673482ae2ee_42.png)

嗯嗯嗯。There we go。Yeah so oftentimes whenever you're writing this you will get like ton of errors and you just have to look through where you're getting the errors and then debug them as we go so this is more authentic than if I had just got it on the first try so yeah you will like suffer a lot when you're writing back in code。

😊。

![](img/18f8b419755349cc15567673482ae2ee_44.png)

![](img/18f8b419755349cc15567673482ae2ee_45.png)

And we're just going continue from there now and like so now we can see like our post request is working whenever we're sending that post request we are getting that JSsonN web token back and we can kind of test and play around with this JSson web token just to see like kind of how it works so we can take that JSsonN web token and there's this pretty cool website called Jwt。

 iO and it allows you to kind of play around with jSsonN web tokens so I want to use this there we go。



![](img/18f8b419755349cc15567673482ae2ee_47.png)

![](img/18f8b419755349cc15567673482ae2ee_48.png)

![](img/18f8b419755349cc15567673482ae2ee_49.png)

![](img/18f8b419755349cc15567673482ae2ee_50.png)

So we can paste in our thing right there and so you want to enter your random string whatever you put there and as you can see like right now the string over there the signature value is invalid it's just this random value and if you replace it with the actual value so for us it was random string it's a signature verified right now but if we rever it to something else。

I should。Should reload and it should tell us so I guess the Wifi is going of slow but earlier it is telling us the signature was not verified and this is what our random string kind of does for us。

 it changes up this last blue parts and that encodes everything and you can kind of see what is encoded into what So in the very first part we're using this algorithm called HS256 which helps like kind of encrypt our passwords which is probably a be cryrypt is doing then we also have this user object in the purple part。

 which is like the I that's our paidload that we made and then that's all like the expiry data and then all the other stuff we put into it So as you can see like this string is just kind of a combination of all the data we gave it and it just hashes that into this string so hackers can't like use it to make new versions of the JsonN web token and gain access to our database so it's all security stuff And if it's going over your head it doesn't really matter too much but this is just kind of like the general idea of how we're using this and why we're using this and then also this thing below is how we encode the signature of the string so it should not say signature verified I'm hoping that。

Slow internet and the signature is just the blue part。

 so that blue part changes whenever I change this part and that blue part has to match up with the JSON web token otherwise the JSON web token will be incorrect。

Are there any questions regarding anything I've done in the post requests。

 the routers or anything else？Okay so so i'm just going to then continue on on to the next part of this and the next part is kind of going to be pretty similar to what we just did so we've made this slash lineup method the next thing I might want to do is maybe make the same thing but what if I want to allow a user to like log in normally so i'm not creating a new user this time i'm just allowing a user to just log into their account and the way I do that is I do router do post。



![](img/18f8b419755349cc15567673482ae2ee_52.png)

And we can just reopen this and it's going to look very similar syntactically to how I made it up here。

 so i'm just going to have like the file or URL path so this would be login and this would then also have like very similar code to this so I make an async request up here。

And then when you're logging in， okay pause over there yeah， so whenever you're logging in。

 you might pass different information， so whenever you're logging in usually usually is's just like your email and your password。

So we're going to want to have that and we're going to set that equal to request。

 body so now we're just getting our email in our password like we did before and then we're going to want this try catch block kind of similar to how we made it last time and we're just going to edit it here and there because that should be pretty equivalent to what we did last time so。

It should be it should be like pretty similar， it's not going to be super different from what we did last time there's just going to be like a few minor quirks here and there that we're going to need to change and that we're going to need to update just to make sure everything is working。

So the first thing we're going to need to change is let user await dot find one email that should be fine。

 but in case the user does not exist so in this case if we actually find like an email that means that the user exists and that means they can log in but if we can't find a user that's a problem they should not be logging in they should be making an account so we're going to want to maybe send a response status 400 with like the JSON message that user does not exist please sign up。

How much battery do I lost 8% okay， me a bit told。Useusr does not exist。Please sign up。

And that should tell like the user to kind of sign up and then I do not to make a new user object this user already exists and it's stored within this user up here so this user found one email that should return me the user object of the person who has already been in there so i'm chill that is good that is exactly what I want and the next thing I want to do is double check and make sure that their password is valid so I want to make this maybe is match and the way I want to use this is I want to await be crypt to compare。

The two values so user dog password and then the password passed in and remember that the passwords are encrypted so whenever I pass them in bec has to do all the comparing for us to make sure that these passwords are the exact same and to make sure that this person is logging in with the correct passwords and this will return me like a Boolean that tells me if these two things are the same or if they're different。

So like the next thing I want to do is I want to have like an if statement over here。

 so if they are not a match， so like if the passwords are long。

 then I I'd want to do like a I'd want to return a response status 400 because this is an incorrect query and I'd want to make a JSON object where I'd have the message maybe like incorrect password or something。

So there we go and that should be good and again I don't need to use consult or hashing the password again password has already been hash so I don't need to take a look at that and make sure that's okay and the next thing I'm kind of going to want to do is very similar to what I did last time so I'm going to want to make sure that I'm going to have the payload again so I don't need to save I don't need to say this user to the database they're already in the database I'm going to have this payload and I'm going to do JWt so I'm going to like double check whether their token is all good when they're logging in I'm going to want to send them another token so I'm going to want to send them another token and that's going to have like this expires in value 3600 it's going to have the same random string as we had before and it's also going to have the payload which we had in the previous JSson web token and it's going to be like pretty much the exact same thing as we did last time and then I'm also going want to have to have a cache error down here so that's pretty much it。

Pret much very similar to what we did last time。We can go ahead and just test to make sure that this guy works and let's go to postman so if we test out slash log in。



![](img/18f8b419755349cc15567673482ae2ee_54.png)

It should work。So the password is incorrect。Let's make sure that first this user is signed up。Yes。

 so they exist， and then I want to go to the slash login。



![](img/18f8b419755349cc15567673482ae2ee_56.png)

And maybe I'm using a wrong URL， so I am using the right URL。

So then I'm probably not making this is match statement correct， so isM is a await so not is Ma。Okay。

 so that's if the is matches false， then this should give me some value and it could be because maybe I flip the values around。

 maybe this is bush be like this。

![](img/18f8b419755349cc15567673482ae2ee_58.png)

Shouldn't really matter too much， but we'll see。There we go Okay for some reason it was that and I got the token back and the token is this value So whenever you're logging in you should also get a token that's because like some users log in after they've signed up for a very long time and they might need a new Jwt token or J token so that's why we get the token back and it works pretty much the exact same way functionally as the previous time and the last thing we're kind of we're going to do in this demo is we're just going to demonstrate how to use middlewares So middleware is anything that takes a request and a response and then does something with it but doesn't send a response back instead it passes it creates like it alters the request in some way and then passes that on to another function that can do all that work for us so normally we just have functions that take a request and a response and then immediately send a response somewhere right we're always sending a response with a token but what we want to do is instead of doing that maybe alter the request and let somebody else do the work and the response and then tell us that that response is good or if that response works。



![](img/18f8b419755349cc15567673482ae2ee_60.png)

So what I'm going to want to do is I'm going to want to first minimize these and then I'm going to want to maybe make some middleware so I'm going to want to make a folder called middleware and these are like kind of like functions or helper functions you guys can use so if you if you ever done like any other coding class use helper functions to help you make other functions you can think of middleware like that that's pretty much like helper they're like the helper functions of backend coding。

So we can make a folder called oth should be oth。js。Okay， and at the very top。

 I want to import some stuff so I want to import JWT。Jason Webb token。

And then if I think I should be good with just that， and then I can just go directly into a function。

Equals function with a request response and next。Here I made a function。

 so it literally is a function and it takes a request response and then next and next is a function that allows you to just pass on that information to a different function rather than returning a response yourself so it just alters the request and then passes on that information and then we're going to start with getting the token value so。

I believe it's like that。And you just query the value of the token from the header so tokens are passed through the header of the request so in the request header you can get the value of the token and then store it in a variable to use it somewhere and then if the token a doesn't exist you want to return some error message。

So if not token maybe just return a res dot status 400 so that means like the request was bad and did not contain the necessary information and you can send like maybe an error message saying error。

Jason by Poken Nobelllen。So yeah， this will just send like or this message to the user if the token is not valid for whatever reason and this could be like their end or R end and the next thing we want to do is we want to have a try catch block where this just tries and if there's an error then it pushes the error out and we want a con decod which equals the function Jwt。

 verify token。And then whatever random string we put earlier。

 so for us that was just literally random string so that verifies that the token has the right signature based on the random string and if it does。

 then we are good so。We do the following and then finally we pass on this information。嗯。

So so this request a user now is equal to decod a user and then we pass that information board and then we just make the catch block are there any questions did it see like a hand up so next all it does is just passes on whatever information i've changed here to any other function that's using this like help or function in a sense so right now as you can see i've changed the request values so i've changed request ID user to decoed a user。

Yeah。Next just send the floor to whatever other function comes after yeah good question are there any more questions？

嗯。嗯。Then I want to catch the error and then I can just like maybe return。

Consult log the error and then。Return or reside status。Yes。

So this is an internal server error if it doesn't work。

So I just want to make sure you do that and then the message can be。啊。There is an error in。

The competition。Thank theJson web。😔，Or yeah， let's go。

So it'll just send that message if like there are any issues and you can you should probably make your messages way less verbose but I'm just doing this for now it doesn't matter too much。

And yeah， so that's pretty much it the final thing we kind of want to do is we want to go back to roots and user dotgs and we want to add a router。

t get method whoops not not with curly braces so you use use parentheses whenever're using router。

t get and there's like a lot of weird syntax when it comes to backend it's like toughft when you're getting when you're just learning it but you'll get used to it hopefully over time and in the router。

t get thing you're going to want to have slash so you're going to want to have the pathway slash me。

And。傻说。嗯。嗯。Of and then async。Requests and response。

And then you're going to want to have an arrow function。

And then you're going to want to put the value of request or off down there。

 So that's pretty much it for this part of the equation so we can just like。嗯。

We can just put that information in here so we can have like。H honest。

We want off and we can import that from。Dot dot slash middleware。Slash。And then。

We want to put the values within the specific block of code。

 we're going to want to have a try statement。And within this price statement。

 we're going to have like something making sure that the user exists。And then request our user。

 ID and then we're going to want to use。Then we're going to want to send the user as a J object back。

 and then we're going to finally catch the error and then if that happens we want to send。

The message like。We're going to want to send like a maybe a Json object， so Res dot status。

Maybe you'd like。500。Dot。Jason。嗯。Message， error， infection。不。

So what this piece of code will do is it's just allowing us to test that if the user is giving like the correct JSON web token whenever they pass that information is it right first of all and it allows us to authenticate that and if there's some error we just send an error in fetching and that's pretty much it so this is just a dot get method and it's like really useful for just understanding if the JSON web token is valid and then if it's not for some reason then we like kick them out or something so if you guys remember like the fourth and fifth step one once a user has like a JSON web token stored in their device locally they'll just send that instead of their username and email so we want some way of just authenticating that the user legit based on that JSON web token and that's what this block of code is doing and yeah that's pretty much it for today's lesson are there any like final questions about middleware about making the roots or about anything we've got。

Okay， so if there are no questions， you guys are free to leave and before I forget the secret word for today is mango so instead of mango mango so just go ahead and put that into the form and that's pretty much it if you guys have any questions you guys are more than welcome to stay and if not you guys can leave。



![](img/18f8b419755349cc15567673482ae2ee_62.png)

![](img/18f8b419755349cc15567673482ae2ee_63.png)

对。
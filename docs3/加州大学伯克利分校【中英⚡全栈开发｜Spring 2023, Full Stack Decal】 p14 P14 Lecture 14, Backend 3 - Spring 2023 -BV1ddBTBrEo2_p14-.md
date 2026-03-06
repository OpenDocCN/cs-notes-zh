# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p14 P14 Lecture 14, Backend 3 - Spring 2023 -BV1ddBTBrEo2_p14-

嗯。

![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_1.png)

对我个。对对。All right， hi everybody， we're going to be starting the lecture now。All right。

I'm never this is the third time you guys have seen me or fourth time and this time I'm teaching like off with MongoDB we did most of this last time my bad we were supposed to actually do something different。

 but we're just gonna to be finishing up the off stuff we did most of the last time I'll just go over it again because it's been a while and then we'll just finish up the last portion which was just testing out our code and that's pretty much what we're gonna to do for today so today is not going to be a super long lecture I'm going to spend a lot of time reviewing MongoDb concept so you guys can definitely know it when you guys are working on your projects。

So just a quick recap I taught this all like a while back but we have like three different protocols that we use we use HP protocols which allow you to communicate with servers on the internet it just basically allows you to get information that displays that information on your screen and HP requests do all that work for you they do all that communication we also have rest which is an architectural style of building APIs As or application programming interfaces and just allow two different applications to talk with each other So rest is just a way it's just a standardized way of making those APIs it's kind of important I guess you guys need to know when you guys are using APIs it's useful to know when you're also building out your APIs and then finally the last thing is Postman Postman is just something we can use test for APIs we can send mock HP requests and see if it works or not yeah so Postman is just really useful cleans up all that stuff and makes it very easy to understand if your As are working so definitely recommend using Postman this is all review so if you have any questions let me know but I'm gonna kind speed through it。

Here's like an example of like an HP request， you have your computer。

 you send it to like some API which communicates with a web server which communicates with like a database or something。

 and then you get some response back so you're sending over a request getting a response back that's like the key stuff you kind of need to know from this。

What are databases databases just help you store data I know that's like pretty self-explanatory and you have two separate types of like databases you have SQL databases like my SQL Microsoft SQL if you guys took CSs62 andA that teach you SQL that's like what SQL databases are built on like backcode and usually data is stored in like Google sheet style where you have like multiple rows for every single line of data like a data frame or something so that's like how SQL databases kind of work the other form of databases is no SQL databases which is literally just no SQL and some examples include like MongoDb which is the one we're using and MongoDB is built on Python so yeah。

So onto Mongodb the way Mongodb works is you build data structures like how the data is stored in your database based on these schemas and schemas are basically blueprint or models for how data is added and stored to your database so you have like objects in your database maybe you have a user object and within that user object you have different fields that each user should include so maybe each user should have a username and password those should be two fields within the user object or user schema you make and that's like how the data is being stored in your database and you define that theyre building schemas that's like the foundational aspect of how data is stored in Mongo and it's pretty easy if you've done object oriented programming before pretty simple but yeah and there's also cru commands which is create read was it update and delete so we'll go over like the syntax of how to make all four of those these are going to be like the four key commands are going to be needing when you're making your own databases so I would just like look at the syntax when I'm going over each one of these operations and then making sure you understand them fully Are there any questions regarding anything I've gone over。

够。So here's like an example of some schema code so first what we do is we kind of initialize a schema object then we make a new schema object by doing glance item equals new schema which is initializing a new schema object and within that schema object we have our four kind of categories which include like a title task date and urgency and we kind of define what each of these what's going to be the type of each of these seals so title going to be a string for example and then finally the last thing we need to make sure we do is we need to convert this into a model so Mongo maybe kind of does that for us and that'll allow us to kind of use the models we've created to actually store data whenever we're building out the other parts of our application。

Any questions on fews？Cool then we have create operations so when we're doing create operations basically we're putting new information into the database so we need to do a post command so as you can see at the very top we have a new post command and that just goes to the slash Db area so it's taking information from thatlash Db area it's getting a request from the user So remember how I talking about Htp request when you're building out your API you get an HtP request and then you have to gain a response back So right now they're just kind of taking that request making a to do object with elements from the request you'll have like the title task date and urgency from the request and you'll fill out the specific fields in the to do object so now you made this like new to do object which is basically the Mongodb schema thing that we made on the previous slide so as you can see we made this new to do object over here that's that thing at the very bottom so we made that new to do object that has V4 fields and over here we're just making a new kind of to do object and within that to do object we'oring all that information we got from。

The users so this is like an example of an application where the user is maybe wanting to create some new tasks that they have to do and within each task it has all these four elements and the user fails that out and wants to create that new task then your database should do all this work it should make a new to do kind of object or task object and then save it to the database and that's good over here in this next line where we save the to do object at the database this part is creating the to do object with all its specific information that we get from the request and this part is taking that todo object and then saving it into our database that's done through the dot save command which Mongodb makes for you and then you do a bunch of error checking in case there are any errors with doing that thing so in this case like maybe for some reason it fails you send an error request just so that the user knows that for some reason it's gone wrong and they should do it again and then otherwise you just send a success message and we went over this like a while back there different types of status requests and different types of success messages it's not super。

I just know like I believe the important ones are like 200 which means it's perfectly good 500 which means it's a serversideder。

 which means your database screwed up somewhere and 400 which means somehow the client screwed up so that means the person who was sending the request made a bad request those are like the three main ones off the top of my head those are the ones you should know and obviously like in the code we did last to last week we already had that kind of planned out so when I'm going over that code i'll just kind of reex that but that's pretty much it for like creating data any questions on this。

What'sOn security I am not at all like somebody who is qualified to talk on that。

 but in the off example we had， we had ways of securitizing it through using salt and other encryption methods。

 so I'm sure in both SQL and manga Db based databases you have ways of encrypting the data and they're probably going to be pretty similar because I think most like computer security methods are pretty similar so。

To answer your question， one， you can add security from your side onto your like application that should pretty much make the security pretty even and then two I'm sure like they're both pretty comparable like I don't know for sure though。

 but from your side there are definitely steps you can take which we did in the off example that will help securitize your database。

Any other questions， that was a great question，'s up。Whiister string argument。

To do oh this bottom line over there that just names the object I mean it isn't like super relevant personally you can name it whatever but we tend to name it the exact same as this to do thing over here so whatever variable name we have we tend to make that spring name the exact same and it's just useful whatever' exporting the object but yeah。

Any other questions？这本。系翻。I believe MongoDV is like the database itself。

 the people who've made it have constructed it in Python。

 you can use it with JavaScript though so like on your side it doesn't matter right you can write it with whatever you want but I think the people who made it wrote it in Python and 100% on that though。

😡，Good question， any other questions？So。All right cool the next kind of thing we want to go over is read and retrieve This is basically just getting information you're not manipulating any information on the database all you're doing is taking existing information and then displaying it for the user so for instance in this application maybe the user has previously stored to dos so they'll already made previous tasks that need to finish this could be like homework assignments or something else and they want to retrieve that data by maybe pulling up previous tasks this is an example of how you do that in your database so you do router do gets and this is like getting all the to do messages a user has made and how you do that is you take the scheba object in to do then you do do find and find takes arguments so you can filter through all the to dos that exists for a certain user and you can filter the ones that you want to select this one if you don't put any arguments in here it won't filter anything so it'll just give you back all the to do objects that exist within the database and then it'll take those to do objects and then it'll display all those to do objects it'll send a response back with all the。

To do objects and you can take those responses and do something with it and that's basically what this code is doing is just taking all the to dos in the database and sending it over find is a method that exists within Mongodb。

 you can look up the documentation if you want to learn more about how it exactly works but when you have no parameters in there then it just returns all the to do objects or all the objects in the database basically based on the specific schema model you use any questions on like what Yeah so within like the find command maybe you put like so we can go back to yeah so maybe we can put like title equals hello or something or we can put task equals homework assignment3 I don't know you can like put specific fields within that to do object and then make it equivalent to some other like value that you're looking for specifically and then it'll filter for that so you can do stuff like that and get the exact to do item you're looking for or a group of to do items you're looking for。

お该あ。I believe it does give you back an array， so like if if you have multiple to do objects it'll just give you so if we go back to that previous line of code as you can see is like kind of returning all of these to dos so I'm pretty sure it is going to be just like an array of objects that you can get and then you can take those array of objects manulator and display on the screen。

😡，Yeah。Any other questions？Cool the next thing is update update is just taking existing information in the database and then changing it to whatever the user wants to be so the first thing you want to do is make sure that the data that the user is requesting to change actually exists so we do a dot get command we just make sure that the data exists we do a little bit of error checking right there just to make sure it exists and if it does that we kick them out right there and if it does and we continue to the next step which is a dot put command dot put is used to update data specifically so on the previous slides we had dot get that's only for getting data you don't update anything with that then you have dot post which is only for creating new data and finally a dot put which is used to update existing data so then we do dot put we get the ID we get the item so let's just like whatever is given in the request we just take those specific things out we check to make sure that the ID is in the database ignore the database name this is like some example the previous people may don't worry about that too much。

Get these specific item by just filtering through the database and then making like finding the ID so it's like an array basically and then once we find it we just kind of send it back and if we don't find it then we send that okay there's an error this object doesn't exist and that could happen like maybe if。

So like one example this could be like maybe the item itself like this this item that is spent in the request。

 maybe that item is not associated with that particular ID and that case you can't update that item anymore so。

That's just something things to look at。Are there any questions based on this？

So you could also just do this in one step realistically you don't really need a dot get。

 you could just go straight as the dot click commit and you could just check if the ID exists within there and if it doesn't then you can kick them out there as well so either way it works。

 but yeah that's pretty much it。The next the last thing you can kind of do in a database。

 the main thing that you guys will be using is the dot delete command and dot delete basically all it does is it just gets rid of an item in the database so the first step again same thing as before we're just checking to see if an item exists in a database and if it doesn't be immediately click about because you can't delete an item that doesn't exist in the database then we do a dot put command that step isn't entirely necessary but this step is another way of deleting an item you can just update the item to be nothing so that's kind of what they're doing right here。

I mean， I just go with the dot delete command it's simple and it already exists like it's pretty much written for you。

 So like the people who made mangadb have a bunch of prewritten methods and this one is just okay given the ID just delete the method for me and it just does that for you so that's a great example of abstraction and it just makes your life a lot easier when you're using mangodb like you don't have to write the delete methods from scratch most of them exist in mangodb and realistically I'm pretty sure you probably don't even need the get method。

 you could probably just go straight to dot delete method and it'll autoche to make sure that that item first exist in the database and then if it does then it'll delete it and if it doesn't it'll send an error message out for you this is just lengthening the code out so it makes a little bit more sense to you guys are there any questions on deleting items from the database。

Yeah， so we don't need to we just did this to kind of give you guys a better idea of different chunks and different steps you need to have when you're checking for items and databases you don't need the dog gap method you can honestly say I don't want this I don't want these two chunks of code and just jump straight to this line of code and that'll probably do all the work for you。

😡，Yeah， it's just to show you like how to break it breaking down the code of parts but it's like easier to understand basically。

If you read every just take one as。Good question， any other questions。SThere's no。Sorry。

 what was your question again？我。So the Mongodb part。If I understand your question correctly。

 the way Mongodb is kind of interacting with our code is twofold。

 the first is through the schema objects， so we have these existing schema objects。

 these data structure models that we' written out， which is the todo object which I introduce a few slides back and then we have these prewritten methods by Mongodb which will search through the database that I made in Mongodb search for those items that I've saved to Mongodbs database that I have and then find them and delete them if they exist。

 So that's like the Mongo Db code if that's what you're asking there is no specific like there there's no Mongo Db language like there's no language that Mongodb works on I'm not writing like some Mongodb language they just have their own methods and I can use them in my like backend code so as you can see I've kind of used them on my backing code and I'm just coding a normal ja pretty pretty much So I'm sure can interact with most languages we're just going to use ja in the backend because it's simple and most people do this but that's pretty much it。

对，该是。Cool， good question， any other questions？

![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_3.png)

Okay cool now its just going to move on to the demo so again we've already pretty much finished this last time I'm just going to quickly go over the code again just so that you guys have a very clear understanding of exactly how Mogad works and then we'll do some postband commands and after that we'll be pretty much done I'll just give you guys a secret right off of that and then we can do some homework questions for like 208 minutes but yeah that's just going to be the general agenda after we're done to this demo。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_5.png)

I'm just going to quickly open up。嗯。The demo on my computer。I believe。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_7.png)

So if you guys were falling along last time you guys should probably have the code somewhere we finished almost all of it I think we we finished this last method so。

There was like one last thing we had to do I think we finished that pretty much at the end of class we just didn't get a chance to test it i'm just gonna go over everything from the jump again so the first thing that we did is we just installed a bunch of dependencies into our code those dependencies include a node mod which is like the kind of NPm start version of like backend code it just automatically refreshes your page every single time you make a change in the backend。

So that was one thing we did another thing we kind of did is that was like the first step the second step was making this index dot Js file so I'm just going to quickly go over this index dot Js file I'll just full screen real fast so。

The first line of code is express hopefully you guys remember what express is Can anybody actually tell me what express is just so I can know that you guys know properly yeah just runs the server Yeah pretty much so Express just helps us set up a server pretty easy definition and the way we import stuff in backend code is using the word require that just helps us import stuff so we're importing express at the very top then we're using something called the body parer that just helps us parse through JSsonN files and get the information that we need and then we do this kind of function called initiate Mongo server which helps us connect to the Mongo server that we've created within our code so way we do that is in this config folder and we were writing this out just so that we can make sure we're connected to a Mongodb server so that we can access that information and then save new information to the Mongodb server so if you go to the very top the first thing we do is we use this thing called Mongos this allows us to connect to Mongo Db servers access information and save information。

All the heavy listing for us mangos is absolutely necessary put it in your convict files the next thing we do is manga uri the manga UI is just the area in which your manga Db server exists you put that there so that you can connect to the mango Db server hence that's why we have like that specific weird code there and I can quickly just show exactly how we did it so。

😡，This is one way to have like a local kind of what do you call a local database on your own laptop just for like testing purposes so that's what we did last time and as you can see it's all I did is I typed Mongo S which is the Mongo She script command and that created this line of code we have this first part about Mongo Db Co and doublelash all the way up to this part that is all the information we need from this area we put that in the Mongo UI and then we put an extra slash plus the name of the database so when you guys are building your own Mongodb databases it'll be on the Mongodb clusters and it'll be slightly different from this but this is a good idea on good general idea on how to test out your databases and how to build like a local database just so that you get familiarity with Mongod commands that's what we did last time and the Mongo UI is just like that first chunk again plus the name of our database which is at the very bottom over here which is just test so we just put slash test there and then we wrote an entire function just to make sure。

We could connect to that specific UI that we listed above。

 which is where the MongoDB server was and then if we could great。

 we just said connect it to database and if we could it we said consoles log error throw like an error right at the very bottom so we're just throwing an error in case there's an error and we can just quickly test that this works。

 we can do NPX。😊，I believe this was it。Yeah。😊，And VX nodemon connect to database so that works so now we know for a fact that the initiate MongoDb server kind of works and you need this function over here just to connect to your database。

 this just helps you connect to your database， that's it。Any questions on this？Yeah。我这边个在提供。

So that cluster thing is something you have to set up in your local Mongo DB so you to like create a MongoDb account you go to their website create MongoDb account and you can build like cluster and then your own personalized database over there。

It's slightly different and it's a little bit like different from what we did over here。

 but if if you can do this part it's not too difficult to find that part out there's like docs online that you guys can use and there's also like a few videos you guys can use yeahs。

当。你点啱试用四好先分有我。Yeah so MongoDB isn't stored in those table like formats it's using objects instead so we have different objects like the to do object I was showing you it stores objects in that format versus like a line by line format so it's just a nicer easier format for people to read it's based on your preference really if you have experience with SQL servers and you prefer them perfectly fine go ahead and use them we're just teaching MongoDb because we view that as' easier。

Yeah so clusters is just MongaDBs like special way of categorizing their projects once you go to like the MongaDb website it'll make a lot more sense but they have like clusters and within each cluster they have like I think a project and then within each project you can make like multiple databases to store any information you might need and then you can also build schema directly on the Mongodb website instead of doing it in your app but it it's really just up to you and you'll kind of see it when you walk them to the website it'll make a lot more sense and if you have any questions obviously drop by office hours I'm sure somebody will able to like walk you through it good question though any other questions。

不则。Yeah， this is all my back end code， none of this code is front end， all of it is straight backend。

Yeah so we have like different folders I think I explained this last time but we have like a contract folder a middleware folder models folder。

 root folder and then obviously the index OGS file normally backends have like a few more extra folders in there with a lot more files but this is a very basic example so we didn't want to go super in depthep but like yeah。

 this is like the standard things and I'll go line by line and kind of explain what each folder is doing。

Yeah， any other questions？Cool， next part is just gonna be going back to the indexjs file and going line by line to kind figure out what's going on。

 The next part is gonna be the user thing。 So we're getting some information from the roots file。

 so let's go ahead and go there and then it'll explain exactly what roots does So what roots does is on a website you'll see often that you can go to different areas of the website so like for instance on Instagram when you go to the profile after after you go to the profile it'll be ww Instagram colash profile so like the then the part after that constantly changes when you go to different pages on a website and that's kind of what the roots is handling when a person goes to different roots on the website different areas when you put alash after the URL on the website this roots file is going to handle all of that it's going to first tell what information to send over the user second what information to get from the user and then do all that in between stuff manipulate that information and do exactly what you wanted to do So roots is like。

your heavy lifting on your websites it's making sure that the correct data is displayed in the correct places and it handles that through different slashes and different areas on your website are there any questions on how roots kind of works and the fundamental idea it's based on。

Cool， I'm just gonna go line by line then the first thing we do is we make we're basically helping users sign up so when they're signing up for our website。

 this is like the first chunk of code we do they'll have to go to the part of our website that has a slash sign up after it and then once they do that they'll send over some request and within that request we'll make sure first if this user already doesn't exist in our database because if you already exist in our database we don't want you signing up again so we'll make sure the email isn't in the database we use like a find command and then we use the filtering thing that somebody asked me that earlier we use like we just put in the email make sure that this doesn't return to value so that this returns the value it will probably return like true or something or or it will return user object that's stored in the database so we want to make sure that this user object is going to remain nu and then if the user does exist in our database like if that email is stored in our database with the user we'll give a status 400 which means a bad request from the user who's trying to sign up on our website and tell them。

Hey this user already exists。 please use a different please do not sign up with a different user or login and then we'll make like so if this if statement doesn't trigger so if statement basically if it does trigger。

 it takes us out of this all this code and if it doesn't trigger we go to the next line and in the next line we just make a new user object So I know we're using like this user variable over and over again。

 don't worry too much about it this user variable just gets updated so in this case like if it doesn't trigger the if statement it's no so it goes down here an updates with a new user schema object。

 we'll discuss the user schema object and a little bit don't worry too much about that but we create basically like a new user with a username email and password that we got from the request then what we do is we just encrypt the password so somebody was asking about security Here's how we do it we just have a a salt basically add a random number to your password So it's harder to decode a hacker somehow data access to the database and we use this library called decCrypt which does all the work for us it kind of encrypts the password based on some。

algorithmgoth that it has in the back and it has like a unique way of hacking different applications so it's hard for people to kind of figure it out and we use this random number I just put 10 in there so this 10 is added onto your password randomly so then it gets hacked and it gets encrypted so even if somehow the hackers are able to decrypt your password there's a random 1 right now that they to figure out is that your password or is that not included in your password so that makes it a lot more confusing for people to get through your password and then finally you set the user's password in the database to that password that you just have the reason why you do this is because when the hackers gain access to the database you want to make sure they have a version of the password that is not the actual password you want to make sure you actually update the password in the database。

And then all you do is this line just saves the user to the database。

 This is very similar to the save command we saw on the post command on the create slide on the presentation。

 This just saves you don't have to do much more than this。

 we use the await command because sometimes this takes a little bit of time so we want to make sure we give the program enough time to do otherwise it might run into some errors The last thing we do is we could JSson web token this allows users to constantly log in without having to constantly put their email and password in over and over again and for us to verify that every single time instead they can just use this existing JSsonN web token thats stored locally on their device and just send that over to us and if that's valid then they just go through instantly so it saves us a little bit of time we don't have to worry so much about them doing all that stuff yeah what's up that payload so the payload is an I it uses an ID and it helps encrypt the JSson web token so that's a lot of words and they break that down first Is are stored within an Mongo Db database every single object because it their own unique I which is generated by。

Monggod so they'll just do all that for you We're just taking that ID that we made we're using the new user object we made all the way up there。

 we're using an ID that's associated with that object and we're taking that ID and we're just making a payload with it this payload is just a new object with only that ID in it so that's literally all the payload is is just something that contains that ID ID and then what we do is we make a JSON web token a JON web token is what I just described within that Json web token we use the ID to kind of encrypt it or we use it as a signature basically so we put a payload first so the Json web token is composed with a few different parts the first is like a payload which is the ID the second is a random string I put random string you can put numbers you can put like a different string it doesn't matter this is just to encrypt the JSON web token so hackers can't get into it just another encryption technique if you want to learn more about it you can look it up we have something about it in our textbook that might go more to depth that I'm just gonna kind of go quickly through it then we have an expires in field which tells us how long this JSON web token's gonna last。

if you don't put anything there， I believe it just lasts forever do you want to maybe have an expiry date just in case and then we have like error handling at the very bottom pretty much but yeah。

 that's pretty much it for JasonO Webp tokens Any questions regarding the first chunk on when we're just helping users sign up？

😡，Cool the second chunk is helping users log in so they already exists within our database and they want to use their email and password to log in they go to the slash login part of our website so they go to the URL slash login and they they can enter this information so they send over a request and that request contains an email and a password because you don't need your username for some reason whatever it doesn't matter it's not super relevant but let's just say they're logging them in their email and password so we get their email and password from the request body So requests the different parts to them in this case we're storing all of that in the body then we do something very similar to the code up top is just slightly different we just find we just assign a user object so this is like a variable we've made forget about the previous user variables we've had we just name them the same thing over and over I know it's a little bit confusing but just hang with me here make a user variable this has no previous values in this case and we find a user within the database that has。

That specific email attached to it if it exists， it'll send over that user object。

 which we will assign to that new user variable we just made if it does not have a user object associated with it it'll send over something that's nu and that'll be assigned to this user variable so it'll it'll either be nu or a user object what's up。

😡，Just to clarify the user with the capital U that is referring to the thechema object right and so that has the bunch inherent I guess methods that we can use。

From Mongo Db， which is like find one Yeah so we can call Mongodb methods on that user object and all that is like important when you do I import Mongos。

Monggos yeah so it allows us to communicate with the it allows us to communicate with the MongoDV servers that we've made or MgoDV databases that we've made what allows us to access or use that specific user schema is this thing up here a con user equals require models user and I'll explain exactly what that means just after I finish this I'll go to that and then I'll explain how that works and how that chunk works but good question。

Any other questions？Cool okay so let's just finish this out then so if the user does not exist So if it is if it is basically a no object。

 this will return true because not no is true and if the user object does exist。

 then it'll be false but if it's no this will return true if statement will trigger your request is bad So about status 400 again means that the request is bad there is an error with a request you are using a user who does not exist who does not have it your email is not found in the database theres no user associated with that email。

 therefore you can't be signing in with this email so just automatically fix you out there and if that user does exist with that email then it goes to the next part。

 it makes sure that your password though the same So we're just comparing the passwords and if it's not a match。

 then again you've made a bad request please fix your password and if it is fine like the match。

 you go to the next step which is just sending them a JSson web token So this is assuming zooming they don't have a JSON web token attached to them and we do the exact same thing we did in the last chunk of code。

We just use a payload， which is the user's ID， attach it to the JSON Web token。

 put a random stringing， and then finally send that back over to the user so they can just use that to constantly sign in rather than using their login ID and password。

😡，So that's pretty much it and then I want to quickly go over the models thing so let's go to this models thing this is like a schema object sample code we have for a user in our database so it has a username email password created that and each has a few fields each of these subfield within the user schema object has a few of its own specifications the username has to be a string and it is required。

The only like different one I guess is it created at created at is like when your account was created that has a date object in it。

 which is something that Mongodb has it's a unique type of data they have and then you can also said default values using this field default as data now and that's kind of Mongodb stuff that does that for you so this is your Mongo Db schema and you can use the schema to kind of access data related to the schema So if you make a new user object like maybe some guy named Michael tries creating a new account on this website it'll be saved under this user kind of tag and if you want to access information about Michael who's just made a new account you use this schema and you use the Mongodb commands that we were showing you in the previous slide like dot find to get Michael like maybe you do user what is it called So I think。

You can export this so over here we kind of export this as a model and now we can kind of use that to do all those Mongad commands so this is like a prerequisite step but once we export that and import that into a different file we can maybe say we can maybe call this like a user schema object and we can do user schema find username equals Michael and that'll get us Michael so yeah that's basically kind of the gist of how you do this what's up。

Yeah。So this is what a team is。 This is what a visual thing think。That's all the time here。Yeah。

 we had always just talk about like Mongodb soaring data。

I that stored like on Mongodbi's cloud or like I know you can use the URI and that can get a stored in cloud in order to do that you need to make an account right yeah and then so if it's stored locally where like exactly is that。

Is that within this folder or。That's a good question I'm not 100% sure I think it's probably stored in their cloud because it's it's not found anywhere locally in my devices I mean a few like usernames and passwords。

 none of that is stored on my devices and if you go to the Mgadb website they have a bunch of different options and how they store your data and one of them is cloud the Atlas one and that's the one I recommend using because it's free for like about like a gigabyte or like 50 microbytes or something like that so I believe they store all the information on the cloud。

It's not stored locally The database I've created is like a local example but it's connected to some cloud options if that kind of makes sense so this this database is not associated with an account like if you go to my Mongodb account you won't see this test database pop up anywheres instead this is just like a local database that Mongodb might create they might make like a little bit of cloud space for me and I can just play around with like a little bit just a test Mongodb out pretty much。

Thank you course，'s it？没没有。That's a good question when you guys are working on your own projects and when you're updating the database like adding your users or something like that。

 you'll be able to see it on the Mongadb website so when you start out on MongoDb。

 it'll give you some sample databases and that'll give you a better idea of exactly how data is stored so you'll have like different files and those different files will be the different schemas and within each schema you'll have maybe like one object about like a specific user so maybe you'll have an object about this guy named Michael and it'll just be like a few lines it'll be like username Michael email of like Michaeljimo etc cea etc etc ce and then you'll go to the next user you'll skip a few lines and then you'll have those same field again that's how information is kind of stored in MongaDb so locally I can't see all the users that are stored in my database but on the Mongodb website once you' connect it to a database on that website you can then see all your users stored there。

Good question， thoughug。Anyone else， any questions？This technical is justprintYeah， 100% yeah。Cool。

 if there are no questions， I'm just going to like finish this out。

The last thing we kind of did last time is we have this last get command so when you go to get slash me so the URL the website slash me you can get you can run a get command so you'll send a request over and that request Yeah so the request contains the user ID and then you try to find user and then you send back user back to the to the user so they're requesting information about themselves by just sending an ID and it'll send them some information back and。

The way we're going to do this is we're going to use a JSON web token and that'll just kind so what this will do is it'll just kind of parse that information for that JSON web token and it'll hopefully work so I'm just going to quickly demonstrate this last part。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_9.png)

嗯。😊，So this is just Postman again， we've used this like a few times before。Yeah呀。

So the first thing I want to do is I want to maybe。

I want to make a new user and the way I do that is first the URL the website so I at the very top of your index director file you define what port it's going to be on and in this case I made a local host 4000 that's the port so you can just set the port to be like 4000 or like 3200 doesn't matter I think the default is like 4000 so I just set it for the default which is port 4000 so right now my note server operating at port 4000 I want to get I' want to maybe create a new user so I can do like sign up。

And I think I had to， yeah， so we'll just go with this。

This should give me probably an error because I've already， I think I've already done that。

Or I think there's a different command， actually。You're right， actually 100%， yeah， not bad。

It's user slash signup because in the and I didn't actually talk about this that much but in the index JS file we actually defined that at this specific path so at the slash user path。

 we want to use the router so the router is all that stuff I was going over thelash signuplash login you first have to dolash user and then you have to put all that information in and then the router would trigger trigger all of its command so good catch whoever said that you're absolutely right you dolash userlash signup and I've already made this user in my database so making it again would just get me an error so I'm just gonna change a few of these fields and another thing I want you guys to notice is I'm sending a JSsonN object I'm not sending like a text so there are a few options when you're making a posting you'll have like text jascript JSson whatever make sure you're using JSson because we're parsing JSson files that are being sent over So just make sure you're using JSson whatever you're testing out of your code otherwise you might get errors that aren't actually like true so we will change up the names here。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_11.png)

![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_12.png)

Change it to like。So I'm lazy， I'm just going to like flip around the names。

 it doesn't matter too much right now。Okay that should not be happening so maybe maybe there's already a user with this specific email associated with them so all I have to do is I just have to change some of the words around。

So for right now， I don't care that much， so I'm just going to put random stuff。Beautiful。

 so back I get a JSson web token when I was showing you guys on the previous couple of slides。

 remember I said that if everything goes correctly you get sent a JSson web token back so as you can see we've created a user we get this JSson web token back and I can also test that the login part but for now I'm just going test that dot getme method because we didn't get a chance to test that out last time and the way we test that out is。

Which is copy paste that information， and we have this like token field。So。

Right now we're running a dot get command。So。This is an example of  queryering in HGTP so you can get specific information out of specific URL by using the question marking and then setting a specific field equal to whatever string you put in。

So that's what we've kind of done over here again like don't worry too much about this。

I'm just going change it because we have a new token and let's send that information over and if it works we should get all this information properly so we get like an ID username and email password to create that field we get all the details about the user basically so by sending over JSsonN web token we've successfully kind of signed in and you can use this to kind of build out your app using JSsonN web tokens if you want to for now you could also keep it simple by just using usernames and passwords what's up。

So for a user accessing this website through like a web browser， let's say when you sign in。

 does the JB web token automatically get placed in the header or how does it like？

How does the database know that we contain a JSON Yeah so what happens is when you guys or when you've already signed up or logged in for an app and when you get that JSON web token back as like a response from the website what happens is you store that information locally on your device when information is stored locally on that device whenever you send another request that information is already always included in the headers because when you're making an HGP request you often include all the details even if they're not needed in the request so the request sometimes that's a lot more useless information than it actually needs and so that token is going kind of be sent every single time and that's handled by the web browser。

Yeah long as we send so okay yeah。Yeah， of course。Any other questions， that was a great question。

Yeah so I mean that's pretty much it this is just like an example of how to use PostB and we worked a lot on the authentication stuff last time。

 so if there's any confusion about that I would recommend going back to the videos we did last time。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_14.png)

I think it was like two weeks ago， it was like just before spring break， maybe a week before。

A week or a week and a half before spring break started I would look over that video if this is confusing at all and of course there are tons of like mongodv videos online if I'm at all confusing for you if I'm going too fast or if like my explanations don't make 100% sense there are people whove worked on Mongodv for far longer than I've been alive not alive but like far longer than I've known about Mongodv So if you prefer their videos that's perfectly fine there are tons of resources you can use use whatever resources you want but yeah that's pretty much it if you have any questions I'm here you can go ahead and ask me but that's it for the lecture before I forget secret word I don't remember the secret words so let me just pull it up and make sure you guys can get it before you guys leave。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_16.png)

The secret word is off AUTH。Yeah， and that's it for the lecture。

 so I'm just going to like end the Zoom recording。And you guys are free to leave whenever you guys have put in that secret word。



![](img/f1a2c5f12ca87d13bcf9a7d48b4dc21b_18.png)

我。
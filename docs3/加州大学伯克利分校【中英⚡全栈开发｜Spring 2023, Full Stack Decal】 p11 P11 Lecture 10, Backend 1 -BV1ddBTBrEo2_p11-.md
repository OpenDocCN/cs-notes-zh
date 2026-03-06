# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p11 P11 Lecture 10, Backend 1 -BV1ddBTBrEo2_p11-

![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_0.png)

不行。Hello everybody， we'll be starting the lecture now since it's a little bit over Berkeley time。

So hi nice to meet you， I'm Nemer I'm back from the HTML lecture and today we're going to be going over HP RE and Postman。

 which are necessary tools when you're building at the back end of your projects。嗯。So to start off。

 you guys have already learned the frontend fundamentals in HTML， CSS and JavaScript。

 that is the front end and that really is like how you display your website whereas now we will be switching over to the backend which is more about like saving and managing your data and that involves using NoJS Express which you guys have already learned as well as a few more helpful tools。

So we'll be talking a little bit about HtTP today HttP is like the language of the Internet and it stands for hyperpertext transfer protocol it allows devices on the internet to communicate with each other to send webpage or something so for instance when you guys are going to like Wikipedia you'll notice that in the front of the URL for Wikipedia there are the four letters HttP that is just telling you like that this protocol called HtP is being run and it allows your browser to access that Wikipedia homepage specifically how HttP works is it sends a request to the Wikipedia servers for the details on how that webage is constructed and then the Wikipedia servers will send back that information and your computer will then display that Wikipedia page usually when you make this request the response you get back from the server will be like some HTML code which then your computer knows how to display on the screen so then you'll just see that on your screen。

And we'll be kind of going over more in this in depth。

So that's pretty much what HGP is it just allows two devices to communicate one of those devices is the client side which is your computer and the other device a server。

 which is all the stuff that contains all the information about like the website and all like the information you need to build that website on your own local device。

Cool so there's a slight difference between httP and htPS the difference is just that httPS is encrypted so all the traffic that happens over htPS is encrypted hackers can't track it versus HttP which is insecure so the default standard right now is HtPS which is encrypted so this difference isn't too big don't worry too much about it you're mainly going to be using htPS。

And some key requests you can make with HP so this is like your computer asking a server for some information Some of these types of requests you can make include the get post put and delete requests the get request is getting some information you guys have probably already worked with this a little bit or seen like how it works but just more formalized it just allows you to get a little bit of information and it happens implicitly when you type in Hps in your browser another type of request you can make is post post allows you to create new information on a web page so for instance when you guys are buying something on Amazon that's basically a post request because when you click post or when you click buy this order Amazon will send that information to its servers showing like how your user profile has bought like some piece of equipment so that's creating like a new piece of information which is that Xperson has bought this piece of has bought those equipment or whatever it is another command is put put takes like an existing piece of information and just replace it so this could be like。

If you want to update your user profile and you want to change your name for instance。

 that would be an example of a put request and the final is delete delete is getting rid of existing information on your on your browser so if you like want to get rid of maybe a previous order you've made on Amazon that would be an example of a delete request and there is one more major form of request which is called patch patch is similar to put in the fact that it's like updating existing information but rather than replacing it it's just changing some small thing about it these are like the main five HP requests and you'll be using them a lot when you're building your backend server。

So here's like kind of like a short demo of exactly how it works so here we have this database called slash books and then when I click next when I get the books。

 it'll show all the books in the database when I get or when I delete a specific book ID that book ID is now gone and then I can also post a new book or a book ID that'll create a new book in my database and then I can take that existing book ID that I just made and I can replace it with something else through the put command and then finally I can get that new replaced a book ID through the get command。

And here are different responses you can get So just a bit of a clarification response is the details of server and back to you when you make a request request is what your computer makes when it's asking for some information So a response is the response back to that request and here are five different categories of responses you can get which is really important when you guys are building your applications out so the first is informational this isn't super important in fact just worry about the ones that have stars next to them the second is success This means that your request went through perfectly and all the information you requested is coming back to you in the format your request the next is redirection so think of this like if you look up http call doublelash Instagram co you would be redirected to the Htps version of the website that's essentially what redirection is and when you get that response it'll just tell you it'll give you like a 300 and it'll tell you that it's redirecting you through this new web page the next one is client error this is when when you're sending a request it's a bad request someone。

Like might look a little bit familiar to you guys include the 404 not found and 400 bad request。

 so when you guys send a malinform request you'll get this message back。

So you want to make sure that when you're using APIs that you want to make the proper request otherwise you'll get stuff like this back and the fifth and final category is five or 500。

 this is when the server has some internal issue so when it's processing your response it is enabled to deliver to you for some reason you'll get a 500 like an internal server error so those are like the main five categories I would really just mainly worry about four which is ones that you'll be mostly dealing with but sometimes when you have like an error when you're building out your backend you'll also need to send a 500 internal server error so that's just like different things you guys need to know in terms of like responses you might get when you're writing out an application。

😡，So now we're going to kind of do like a little bit of a demo where i'm going to show you guys exactly what information comes to you when you're making an hp request so here is this curl command and curl is your machines built in way of kind of demonstrating exactly what h requests do so let me go ahead and just open my terminal Okay for some reason it's not letting me and。

😡，嗯。😊，Share screen desktop。呃。Okay， cool terminal， are you guys able to see the terminal？



![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_2.png)

2。So I'm just going to make it a little bit bigger and then increase the size。

And you're going to want to use bash for this there were some issues when I was using a ZsH during too much about exactly what that means。

 but for now let's just go ahead and make a curl request so in the slides we're making a curl request to this website called Poke API so believe it's pokey APIpi。

co。Okay， so then that's not the right URL， so it's HtPS cool and double s working atpi。com。嗯。



![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_4.png)

嗯。

![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_6.png)

是。So there we go So I made a curl request to this website called PokeyAPpi。

 co and at the bottom you can kind of see it's giving me a bunch of HTML and jascript near the bottom you can see the HTML tag and then right next to it is a script tags so this is kind of what happens when you're making an hp request when you're making an hp request to a website it'll just send you all the h code so your computer can then display on your screen this is why we have like the meta tags and the h doct tags so that when your computer is processing all this information it knows how to display that specific whatever specific website you want so this is an example of like making an Hp request now let's try making like more specified hp request which will be on the slides and it was just like curl hp curl and double Pokey APIpi。

 co API B2。So here's like a curl command to a specific page on this website which contains information about the Pokemon called Didto and as you can see you get like all this JSO data about the Pokemon Didto so specific applications will return you HTML in some instances and then JSON in other instances and you guys when you get JSO back that's what you really want to process and if you guys are using like other websites to get some information this is what you want so then you can get the exact information you want so here's like an example of using NHTP request to get JSON and we'll talk a little bit more about why that's more relevant later on。

Let me just open the slides back up。

![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_8.png)

嗯。So that's just curl request It just shows you exactly what the HB requests are and here's like the anatomy of a request so in the beginning you have your protocol which in this case is HB then right after that you have the domain name so in this case this is an example but it's like ww packetet pubub co this is pretty similar syntax to what you guys have normally seen and then after that you'll have the resource slash file path so that's like the specific content you want like where it is in the web page so like a domain will have a number of pages on it if you want to get information from a specific page you'll have to put the resource slash file path and the most important thing you guys need to know is this part right after called the query string what the query string basically is is it allow you to kind of filter through that web page to get the exact information you want so in this case let's say I want like this I of one and topic of two it'll get me the information only pertaining to that query string Are there any questions about like the HB request or anything I've gone over so far in this lecture。

Cool， then I'm just going to give like a demonstration of how like the query kind of string works。

 so let's go ahead and make a curl request the exact same link。

 but instead of making it to ditto this time let's make it to。



![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_10.png)

Let's make it to so let's make it to let's try to get all the pokeke one so the way we do that is it's kind of if you go to the API website it's in there you go。

And I may see your curl that using Pizer。Using Python， you don't need to use。

Or do I how can I write quote for the batch， but it' the file。

You can just use your terminal so you can just you don't need to code in a specific language curl is inbuil to your terminal。

 so if you just run the curl command and a website on it you'll be able to get that information to on a project。

Yeah so you can write your backend using curl with literally any language you can write it in Gengo which is built on Python or you can build like using JavaScript there's a bunch of applications that do do that as well and in the in all those files it's really just curl but you normally don't use curl to build your backend this is just to kind of give a demonstration of exactly what information you get when you're doing HB request Does that answer your question okay yeah so we'll get more into like how to build that out exactly how what's up。

Which protocols are you thinking of？对对。Not to my knowledge。

 but you can use curl to see like what other protocols are happening when you call like or when you when you have an HP request。

 but it's mainly for my knowledge for HP requests， although I'm not 100% sure on that。就。

Are there any more questions before we continue？Then I'll just like put the query command in so the query command is when when you go to the specific web page and when you put in all these resource paths so right now I've gone onto to thelash APIpi B2 Pokemon page I want to get all the Pokemon and there are specific commands thatll be in the API documentation on how to do that but for now i'll just give you guys the command is just limit equals 100000 and then when I want to have two specific queries at once I just separate them by like an and command and then I put the second query command so let's go ahead and do that and boom so as you can see I got like all the Pokemon it's like super long so I'm not gonna go through all of it but it gives me like JO objects for every single Pokemon and I did that by having a query string to specifically collate all these Pokemon together so that's basically it for like how this stuff this like curl request kind of works and there's like a level above curl requests and the way you do that is you just。

Do curl。And then you can do dash fee， of my that。So there's a version of curl where it's a verpose。

 it'll give you even more information than what you're getting right now， so curl。

b htpss Co and double/cokey APIpi。co/lashkey/2 smon。

And as you can see I got I got more metadata on top of that So at the bottom here is like some little bit of information that I was not getting before and then at the top I get like some metadata about exactly how this application is running so I get its server for instance Cloudflare if that's relevant to me I can get if you go all the way up there express X powered by express which is pretty interesting so it's backend is built using no J and then using express as your client server and then there's like a lot more information up there if you scroll even further up you'll see that we use htP1。

1 somewhere I'm not exactly sure aware yeah HP2 is my bad on the second line HtP2 200 so it gives you like a bunch of really cool information that you can play around with and really the relevance of curl and HtP request is just when you're trying to get information from other websites and then put it on your own website so that's where like curl is really good it helps you exactly see what's happening when you strike that website URL and what information you're getting so it's really good。

Like for instance， I think Vihan or somebody else did did this in the past couple of lectures where they went to LinkedIn and they got their follower account to test is a way to test if you're getting your follower account properly is to just use curl to make sure that the data you're getting is the ones you want and then to figure out how to get your follower account out of the JSON object that's returned to you you need to figure out which queries will get you that so it's really useful for getting external information from different applications and that's what curl is used to kind of see are there any questions about anything I've done in terms of curl forbose curl in general or HP requests。



![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_12.png)

Okay， solid it so that I'm just going to continue。Yeah， so when you make a HtP request。

 this is kind of like what the server sees Oh I can finally do slidehow let's go Okay so when you make an HtP request this is what the server sees So at the very top is your method this is an example of a post method to the server will see like this post method happening and then it'll see the Uri the UI is a file path so like after Poki API co we put slash API slash v2 slash Pokemon that would be our example of a Uri and then the htP version at the very end so this is all information of the server seeing not information that you directly get at the server the server just kind of like when when you''re putting in the htP request it just kind of does this all behind the back and then you also have like the post the connection and the content type content type is super important So in this case it's applicationlash JSson and most of the time the content type is determined to buy the server so it's not you who gets to decide whether the content type is H or JSsonN it is the server。

So you have to play around with whatever data they give you and then finally at the very bottom so this is a post request so we're creating something new on this webp page and to do that we need to provide some information or pass some information that we want to change or create and in this case we're passing like this name of a person and their specific age so that's kind of like what the server see when you're sending an HTB request。

😡，And here's like a JSON object again， I don't know if you guys need a review of this。

 but just quickly it's just like a dictionary and Python or a hashrap or tree map in Java so you have your keys and values and the values can really be anything they can be strings integers I don't know if JavaScript is doubles or floats but it can have like arrays or other JSON objects so it can just be a variety of things goes up。

For curl requests。P chase on on。I don't think so I think。

I think for keys you have to be consistent with what's your keys like you can't if you have strings for the entire object。

 you can't change it to something else like integer midway between but don't quote me on that I'm not 100% sure and I'm kind of like rusty on this a little bit。

 but generally they tend to follow the same format。😡，Cool， thats a good question， anybody else。



![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_14.png)

So then just continuing here's like an example of Axios which you guys might have worked with the previous lectures Axios is like a frontend kind of server to get information and there's an example of a get request using Ht and then you get like a response and then you post that response and then you cache the error and then you log the error so this is like typical stuff that you'll even be doing it's a very similar flow to our back encoding which we're going to get more into next time so you'll be seeing stuff like this and today's lecture is really just to give you an idea of exactly why it's working and how it's working and here's like another example of axios and we have in do post command。

And youre posting some specific information and then you get a response and we logged that response and the status code of that response so that would be like 400200300 whatever whether it's a good request or not we'll get like that information back and then we'll also cache an error and log the error so I'm sure you guys have gone through this stuff but if you guys need go review I'm totally more happy to stay on this page doing the same So curl is just doing a get request so it would just be doing the same thing this guys doing kind of similar not 100% but it is kind of modeled by this curl is doing a few more things in the background this is a little bit more basic example of this where it's like you get the get request and instead of displaying the information which you get you instead of just log out the status code curl will just display everything so curl is a little bit more ver post but this I think models it way better than this post command because post is creating you information get is just getting the information。

Good question， anyone else。

![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_16.png)

And here's like kind of the flow of HP requests so first you have your HP requests which originates from your computer then you move on to the roots these roots are predefined in your computer and they direct where the HP request goes so for instance if you need to have like a specific field for get requests for post requests for all these different types of requests and those are the roots those are like defined in your roots and then it goes to your controllers which dissect your HP request so if it has like queries in it it takes the resource and file paths and then determines exactly where you want to get that data from and then it'll go to the models which are connected to the databases and the databases store all the information and then once it reaches like the models they'll tell the database to get this specific information they'll get that information and then send it back through the controllers to you and in this case it's being sent in the form of HTML but that's not always the case。

And then here's like another diagram to give you an even better example So the first two steps of the same it then moves on to services So for this I'll just kind of give an example so it makes a little bit more sense。

 So let's say you're using Google Maps and you want to find you want to find like the address of a specific restaurant like let's say toss noodles so you go and that'll be like a service of Google So once you like type in toss noodles into the search bar that'll go into the services area and then it'll collect like a bunch of information first it'll send a request to its database for the address of toss noodles to display on the page then it might request a few images related to Toss noodles to display on the page and then it'll also go to like an external API if it wants to get like the stars of toss noodles it'll go to that external API let's say it's Yelp it wants to get some information from Yelp it'll go to Yelp and askper how many stars displays how many reviews are there what do the reviews look like So that's kind of like an example of exactly how an HP request works in like a popular application are there any questions about exactly what's going on here or。

I've sent it the past。Cool。And here's like kind of a file structure you'd have when you're making your backend so as you can see you have like each specific container kind of separated into the different chunk at the very top of your app J I'm sure you guys I've seen this a few times before this is mainly where you're like react stuff goes in and then you have like API roots config loaders models which we just talked about services which we just kind of talked about those are the things that handle where everything's going and where it's going and then if it needs to call anything from outside that's what it's doing then you also have subscribers and scripts the main ones we'll mainly be using next time is like config and loaders so I won't worry too much about the rest of them but they're good to know especially when you're working on bigger backend budget。

And our last kind of part of this lecture is going to be RE API so RE stands for representational state transfer and it's basically just an idea of how APIs should be structured and formatted。

 it's an architectural style and then the second part of this word is API I haven't explained this very well so I just want to make sure I clear to this up right now API stands for application programming interface and when people are building their applications they need a way to connect it to other applications so like let's say like LinkedIn knows that other people might want to use the data that users have in their profiles in some sort of way they might build an API on top of their applications so that external third partiesies can still use LinkedIn to do some cool data manipulation or do something cool so often big applications will build APIs on the side so other applications is going talk to them the API is just meant for two separate applications to talk to them and you can have an API just talking to like your frontend that'd be an example of an API as well that'd be like your frontend talking to a backend so。

You can think of an API kind of like a phone it allows communication between two separate applications to be possible so when you're building your backend that's an API between your front end and your back end and then when you're building an API so that other people can use your application and can use your data that's also another example of an API and an API is also where all your get commands post commands all that stuff is defined so that is where you define what information other people can get from your website。

From like a third party application。That's where all that stuff is defined and you'll if you guys have ever used an API before you guys will maybe get what I'm talking about and then you guys can also like look up exactly what's going on there as well on your own there's like a ton of APIs online the Spotify API is a very popular one if you get the chance I would just like read through the documentation to kind of understand how they work but all they're doing is providing information from one application with the other are there any questions about like rest APIs or APIs or any other questions。

标证对，对。诶现象因为啲。ない。RestT APIs is a type of API， so it's like an idea of how APIs should be made。

Yeah usually API yeah most of them are APIs or sorry most most APIs are rest APIs that is the industry standard but there are like a few more different architectural styles we're just going to be going over rest API for today though。

So there are like six main categories that rest APIs need to meet and it's important you guys know this so that when you guys are working on your project。

 you guys know how to work with APIs in case you're using them at all in your website in some sort of way so the six main categories are the first being client server this basically means that no matter what device you use and no matter what platform you use you should get the exact same information every single time from like a get request or a post request or the API in general。

 that information should be the same regardless of what platform you're on the next is stateless and stateless is basically that every single time you send a request。

 it must contain all the information necessary in order for the request to be executed so even if you're making like the same request 25 times the server is not storing any information about who's making this request and why they're making it or what they're making it they're not going make you provide less information you're going to have to provide that same amount of information every single time so that could be so usually they make the main thing they make you。

Like sendend every single time is something known as an API key an API key is just a form of authentication to show that you're not a robot and you're not just spamming their API so a big like kind of issue that APIs deal with is people just spamm their APIs like a bot can just spam their API over and over and the way they make sure that you're a legitimate human is they make sure you get an API key by connecting it to your email or to your name or to some form of authentication and they also give you like a limit on how many API requests you can make and then there's also ways to set it so that APIs can only be accessed by certain devices and certain API addresses and that'll be something far more relevant in a next week's lecture but just know this just to kind of get a better understanding of APIs。

The next kind of key tenant of rest APIs are that they need to be cashable cashable basically means like storing a little bit of information on your device so for instance。

 if I keep making this request that one plus1 equals2 that get request or that information is never going to change so sometimes servers like cache a little bit of information onto our device so that when we continuously make that request it doesn't have to keep going all the way to the server and back especially if some information will never change this could be like maybe in some applications they don't allow you to change your username so instead of storing instead of storing like a person's username on the server what they can do is when you're making an account for that website they can store that username on your device and it's just like a small smiddgegen of data so it'll be like stored as a cookie or something on your browser and then whenever you open the browser and you log onto the device it'll just automatically display your username so some information that never changes you can just cache it locally onto a person's device and。

APpiIs require that you mark your data as uncaashable or cacheable。😡。

That's pretty much it percaable the fourth part is uniform interfaces and what that basically means is that all structures of API should be relatively similar so that we as people who are using these APIs can understand it and work with them that's pretty much it's not too complicated and the fifth is like a layered systems the way I like to think of this as like abstraction so you have different layers to the API and the user should not be able to see like the bottommost layer they should not be able to look at the code and see oh this is what's going on instead there should be some level of abstractions that when I'm using the application I just get to use the requests and the commands they have without thinking too much about how the code is written so that's another central tenant and then they also want layers to be separated so there's different layers to your API and you don't want like layer number two talking to layer number five you want there to be like some clear structure to your app or your API and that's like another central tenant of your API and the last one is not so relevant anymore but it's more so like about when you're downloading or executing code in the。

like applets or scripts we don't do that at all anymore。

 so is this part is like not super relevant but it used to exist just worry about the first five for now and that should give you like a good enough idea on how to use rest APIsre whenever you're using them。

 whether it be like in this app or future apps。😡，And like the last part of this lecture is just gonna to be Postman and what Postman is it's like an incredibly helpful tool to just see it like for testing and validating different APIs so it's like the curl request except it's a much prettier application so you get to see a lot more information and you also get to like break down exactly what information you're getting back and whether you're like API requests are working at all in the first place so this is just going be like a pretty short demo and that's going be it for the lecture so let me go ahead and open up Postman so Postman is an app on your computer you can download it from the app store or I think we can maybe use it in your web browser but I would recommend downloading it it's gonna to be really helpful when you're testing out your backend or testing out anything related to that so here's like kind of how Postman looks so let me just full screen this so you guys can see it a little bit better。



![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_18.png)

![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_19.png)

Okay， so here is Postman and how Postman works is at the very top。Yeah， at the very top you have。

Why is it okay there at the very top you have the type of request you want to make So it's a dropdown menu with get post put watch delete a bunch of different ones for now we're just gonna to play around with get will work more post and all that stuff later but here is like and then right next you put like a URL So in this case I put the Pokemon URL that we're using before and that has the query string already attached So if I can I can go ahead and test out what happens when I send this request and when I send this request I get a bunch of JON objects But last time you guys remember in the terminal it was like really chunky and there was way too much code and you couldn't really tell different JsonN objects from different JON objects postman separates it out from me and makes it look really nice so I can tell exactly what's going on and to make sure I'm getting the information that I want so it looks like I'm getting the information I want and I can keep scrolling and I'll look through all the Pokemon again that's great and then up here you also have your query parameters So if you want to add you query parameters it's really easy you just check the box and then you。

Whatever you want， I don't know any more query parameters and I don't think this thing has any more query parameters。

 so I'm going to hold off from doing that but whenever you want to make more query parameters if that's allowed you can go ahead and do that and once again query parameters which just like filtering the data you get so I get all this data I can filter it so I only want to have like one Pokemon or something like that then I can just make sure I do that。

But yeah， that's pretty much it for postman。 There's a little bit more of some cool stuff that you can see。

 So if we go to。I forget where but if we go to headers there we go if we go to headers we can see like all like a laundry list of meta information that we're getting whenever we make like get request in this case so I'm getting like the date I'm getting the content type which is really useful so in this case it's applicationlash JSO so whenever I'm processing that data I can just know that it's a JSON object and then process it accordingly and then I'm also getting powered by again I'm getting a lot more information than I was getting with just the curl request so like Postman is the updated version of that and it's a much more powerful version of that and it's also much nicer so I'd recommend just using postman test out whether your backend is working you can make get request to see if your like backend is running your servers are running if your node servers are running whatever it is you can use Postman to do that so yeah it's a pretty cool application and as can see I'm working on another project right now so I'm making like a bunch of request to my own backend so I' made a get request to local hosts Col。

4 a000 and when I do that I made it so that it logs out like adjacent object and as you can see like it's logged out adjacent object so it's really convenient to test on my backend code without having to like open a server and then go into console log and see if that's working so postman very good application use it and that's pretty much it are there any questions regarding what i've got in this lecture or any like questions from earlier on。

So yeah， well if there are no questions i'm just going to put up the secret word and you guys can go ahead and just put it into the attendance form so the secret code for today is midterm because I've ton of them。

So go ahead and just like put that in yeah。And then we're also doing homework five checkoffs。

I'll stick around to like 91591ish yeah but if you guys want to do like a homework checkoff built then we can go ahead and do that yeah so if you want to do homework checkoff go ahead and go your computer and just kind of start up your notes server make sure it's all working so that when you get up to me you can just show me your code is working and do like a few commands so I can check you off。

哎。Yeah。啊，Yeah， but once you guys fill out the secret code and if you guys don't are not checking a homework five right now。

 you guys are more than free to leave。好。

![](img/b6bdfddf5eea15d682fa6c5257b4a1c6_21.png)
# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p15 -15-MIT web.lab (6.962) - Day 4_ Workshop 3 (Backend).zh_en -BV12Ux5zTE9p_p15-

All right， can you guys hear me in the back？Tumbs up， yeah。2。

So now we're gonna go into actually implementing our backend。



![](img/8cf5410479b52f1f6ecd25c125d030b8_1.png)

So our goal for today is have a working feed and profile。 So currently， if we pull up our capbook。

 let me do that right now。 We do。NPM run。You guys don't have to follow along with this。

 But currently， like， if we post something on our catbook or like， we comment something。嗯。

Whenever we refresh。Everything just disappears。 And that's not really good if you want to make like like a social media app。

 so。The problem is。i。把嗯。Yeah， by the end of today， Post will be able to refresh。

 and our comments will also persist。And so currently。

 all our stories and comments are stored in our reaction state。 So like Cordelia said yesterday。

 like it's kind of bad that we store our stories and comments in like like a variable in our friend。

 it's just like really bad practice since like as you guys saw， that whenever we refresh。

 we just get the same stories rendered。😊，And so by the end of today。

 we want other stories and comments to be stored on the backend。And so how does the front end get。

 get the stories in comments if we have the backend， we just send requests to serverver asking。

Please give me the stories， and then I'm sure just sends them back to us。

So let's see this example in action。 If you guys can open up Weblab dot is slash example on your computer。



![](img/8cf5410479b52f1f6ecd25c125d030b8_3.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_4.png)

Do inspect。And then go to network。And then refresh。

You again can see all the requests that we send to our server。 So this is our example server and。

You can go to， I don't know， like stories and see the response， the headers， the request method。

 we got our status code 200， okay。And so if you pull up all of the requests。

 you see that there are different types of requests and。One of them is fetch。

And that basically said is that we're sending H T TP request through JavaScript。

 And so you guys remember how I mentioned yesterday。

 how you can send there are multiple ways to send H TP requests， one of them being the browser。

 another being JavaScript and another being from your terminal using curl。

This is using the jascript method， and we'll be using it a lot whenever we're developing get and post requests from our friend。



![](img/8cf5410479b52f1f6ecd25c125d030b8_6.png)

So。We need a way to oh， I'm not presenting。Okay， yeah。

 we need a way to send our request to our server。 And so we're gonna be sending H TP requests to using jascript。



![](img/8cf5410479b52f1f6ecd25c125d030b8_8.png)

And so in utilities dot Js， you can see that we made some helper functions for you guys get and post。

 and essentially what we're doing here is we're abstracting out the fetch function that is in JavaScript to send request。

 So for get， you can see that。We have like our endpoint and then our parameters。

For get requests and then for fetch request using post， we specify the method， headers and body。

 So this resembles the HTP request structure that we mentioned yesterday。

 and it will be important to remember this， the structure of H TP request whenever we are sending and receiving information through our server。

 and we'll talk about that later whenever we implement our endpoints。



![](img/8cf5410479b52f1f6ecd25c125d030b8_10.png)

Okay， so let's get started guys。Go to your terminal and VS code and run these commands。

I give you guys。coupleuple seconds。O。It like oh。It like， code its gonna be on the。Okay。

I'll just share this one。

![](img/8cf5410479b52f1f6ecd25c125d030b8_12.png)

嗯。Oh yeah， you're right。Okay， so。Get reset hard。Get fetch。Get check out。It3， step  one。All right。So。

嗯。So in this workshop， we're gonna to be using NPM star and NPM Run Dev。

 and as I mentioned in the previous lecture， we run servers on ports on our computers。

 So whenever we run NPM start， we're gonna be running the server folder in our project on port 3000 and those will be handling requests that we send from our friend and then our NPM run Dev server。

 which will be accessible at 51，7，3 localhos well essentially just be sending us the react files that we can render on our browser。

 which we use to actually send requests to our backend。And currently。

 we have one test endpoint that we implemented。Right now， it was like the example API endpoint， yeah。

So here's the agenda for today。We're going be sending a get request to our server。

 and our server is gonna to have an endpoint for that get request。

 and we're gonna be requesting stories。Then we're gonna be sending a post request to our server。

 and we'll handle that logic on the server side with a post API endpoint。

And then we do the same thing for comments。 and then towards the end。

 we'll be implementing root middleware so that we can have very neat code and we can organize our API endpoints。

Alright， so step  one will be moving stories data to the back end and then requesting them and then creating an endpoint。

So currently， we have our stories hard coded in feed dot Jx。

 So if you guys can pull up feed dot Jx and find the stories。And then we'll move on。O。

But we don't want this data to be in the backend。 I mean， we don't want this data to be in the front。

 We want it to be in the backend。And so currently， any modifications to stories on the front will just be local。

 So whenever we refresh， we'll just end up with the same three stories。

 So we're gonna move all this data to the back end。

 and this will be your turn to get your turn to get familiar with where everything is and。

Just to move the data from feed to server。 So I'll give you guys a couple of minutes to do that。

 And if you guys have any questions， please feel free to ask。3。啊Yeah我。

We're moving the data of the stories。 So you see how we have all of the stories defined。あこ 때문에も。

Once to copy and paste all that。The actual story definitions， and then the hard of series everything。

他品配。哦，那那个那奥。Just is the stories that we define this cycle。S hoping。

You just copy and paste stuff up where it is step。How it this。Anytime like。

Anywhere before where we implement our endpoints。Alright， guys， can I get a thumbs up if。

You guys are able to move all that data to server。jS。Te me if you guys need any more time。

 So hold up， hold up how many fingers you guys need。 How many， how many。

 how many minutes do you guys need of time to finish this。😊，2。Alright， I'll do it with you guys。

 And then you guys can。Just。Do the same。 So we go to。Go to。Components， then we go to modules and oh。

 actually， it's pages。And then we go to feed dot JSx。We simply copy and paste stories。copy them。

Oh sure。My V code is bugging。So we copy that and then we go to server do JS。

 So this is where our server code is going to be。And we just copy and paste it right above step  one。

I like changing the name to like stories。2。Are we good at that？2过。

Now that the stories are in the back end， we need the front end to actually request them， so。

We'll be sending a request for stories and then several will send back stories。

 So just so you guys like are able to get familiar with H T TP requests and the structure and what information we're sending to the server imagine that or actually go on Webla dot is slash example。

😊，Again。嗯。And then go to inspect and then network and look at structure of our stories requests。

And try to fill out all the missing information。Sorry。😔，All the missing information。好的。

All the missing information here。And if you guys need any help， please get on the queue。But yeah。

 so go on the network tab and then go to the stories request and see what kind of information we're sending。

So， you're going to refresh。And then all the requests are being sent to the server。

And so you can see all the comments。な want。Here。At the find。

So I forgot to mention that you might want to refresh the page whenever you're on the network tab just so that all the HP requests can be shown。

All right。How much time do you guys do you guys think you guys need？

You guys pull finger put up your fingers。I mean， that's。Allright。

 I'll give you guys one more minute for this。All right， so I'll do it with you guys。

So if we go to Weblab s example。We can go to inspect。And go to network。And then， we can refresh。

fresh。And we can see all these HTP requests that this website sends。And then we go to stories。

We look at。All the information， we see that's a get request。And the server， for the example， server。

 is Kbook。On render dot com。 And the end point that it's using is API slash stories。

So for our own catbook， wed want to use the endpoint API s stories or create an endpoint API stories。

 And the base URL will just be local host  3000。Then if we go to response。

 you can see all the stories。The people posted。Daniel， hi， Maar， hello， and then。来了。

And here it says 304， like on the first render of these stories， it'd actually be a 200。

 But since our computer just like stores it on in the cache， then it's just a 004， 304。So。

And so it would look something like this。So。Now， we're going to want to actually request our stories from the friend。

Should I。G a break for。Lunch， I don't want to do this in four minutes。All right， guys。Break time。

 Zoo people。Alright， so we're going get started now。

 so just a little review to remember what we were doing。

 we moved our stories to the back end and now we want to send get requests to a server to actually retrieve that data。

 And so we have a little diagram right here in the corner just to show whether we're in the front end or the back end front end we're gonna to be making get and post requests and then the back end is going to be making the endpoints that run the functionality for those specific request。

And so right now， we're on the front end and we're gonna be sending a get request。For his stories。

And so we're gonna be using the built in function in utilities do J S， which is the gap function。

 And we want to call this function on the API stories， API slash stories endpoint。

And I want you guys to think for a second， what parameters， if any。

 do we want to pass into this function or the specific endpoint。

 Is there any kind of information that will help us refine what stories we'll be requesting or will we just be sending a request to the endpoint with no parameters。

I remember that get returns a promise。 So you want to use dot then so that we can actually。

Run some logic on the data that we would retrieve from the server。

 So we also want organizing stories from earliest to latest。

 And you want may want to use the reverse that reverse method for a raise。

 So I'll give you guys a second to think about how we would probably structure this get request in the front end。

 So we would probably be in。Eta Jsx。This should be gone。Yeah。

Ill give you guys a minute to think about how we could probably structure this request。

 And then since you guys I have never actually sent a get request， I'll do。

 and you guys can just follow along。嗯。All right， so I'll start implementing it。So in our friend。

 we're in the front end， we're in feeded do JSX。 we want to send a request to the endpoint。

AI slash stories。 So we get our get function。Then we specify our endpoint。

 We're gonna be using API slash。Slash stories。And this is going to return。

 We don't know how long this request is going to take。 So it returns a promise。And so。

 we use that then。And that then takes in a callback function。

And our callback function as input will retrieve the stories。 So our story objects。

We passed into dot then， the dot then callback function。

And so what kind of logic do we want to run after we retrieve this data from our server。Well。

 we just want to set these stories as the current stories。嗯。On our website。So we use set stories。

 story objects。But remember how we mentioned how we want these stories to be rendered from earliest to latest。

 So we'd want to use a dot reverse method。So we initialized a variable called reversed。Stories。

And this is gonna to be equal to story objects。Dot reverse。And then。

We simply passed those reverse stories and two set stories。ゼロ。And we can look at the solution。啊。

So that you guys can parse it。 And if you guys have any questions。Please。

 please feel free to ask or get on the queue so that somebody else can help you。Sorry。Yeah。

 so the thing about this is that we can actually name it whatever end point we want since we're gonna implement this A this。

 this endpoint in our back end next。 So right now， we're just gonna call it API S stories。 And like。

 pretend we're gonna be receiving these stories from the back end。 But after this。

 we're actually gonna create the end point that sends those stories back。😊，嗯。Alright。

 and some questions so that you can speak or you can， one question。

 some question for you guys is what H TP request is being sent here。And why do we use dot then。

 And I'll go over those right now。 So just turn and talk to your neighbor， yeah。

Give you guys like a minute for that。Hey guys， take one minute if you're not sitting near anyone who you can talk to。

 go find someone， at least one person， you can mean in the groups of like 2，3 or more if you want。

 and introduce yourself and sit next to them because I think with some of this like more tough conceptual stuff。

 it's actually really helpful to talk it out with someone， so。😊，One minute to find someone。

 if you don't have anyone， go。 so I hear it's starting to get a little bit quiet。

 So the H TP request that is being sent here is。A G request。

 you can see because we have the the get function。 And then why do we use dot then or like any request to a server。

 It may take an unspecified amount of time。 and we don't want to wait for that request to be fulfilled。

 like we want to be able to render the rest of our website and not worry about whether that data is retrieved or not。

 And so we create a promise and then dot then handles that promise or the contents of that promise after it's resolved。

And so after it's resolved at the retriever stories。

 we reverse them and then we set them as the stories on our website。酷。

So now we're actually gonna send back those stories from the back end。So we're in the back end。哦。

And yeah。So if you guys remember the request in response to objects from the previous lecture。

 we're gonna to be using those objects to send and receive data from the back end。

And so a little bit about Re and res。So ReC stores the incoming request。

 and we use the rec object to access the information in the H TP request the server received。

As I showed you as earlier， inside the H T P request， there's like the target URL parameters。

 the header of the body。 And then like the type of request that it is。 And so for all the queries。

For all of our query parameters， we're going be storing them in Redot query or we'll be able to access them in Redot query and then so this is for a get request。

 this is where we'll be storing our parameters and then for a post request。

 we'll be storing all the information we want to post to our backend inside of rec dot body。

Then for response。So res is your servers response， and we use the res object to send a response from the server back to the friend。

 And so the information that we're sending back is going to be the status code and then whatever information are front and requested。

And so we'd have a res dot status function。 And then we just put in whatever status code we want。

 send back。And then res dot send will send back the data that are front end requested。O。

And so now we want to create the endpoint API slash stories。What does this route needs to do。

 But you just need to send back all the stories to the front end。How can we access all the stories？

 Well， if you guys remember， we move back all the stories information from our front end to our back end and just stored it in a variable called storiesories。

Oh， that solution。And so I'll code that out right now。So we go the server folder， server。 JS。

And then we want to implement our get in point。So we have our server abstracted out as the app variable。

This is our express server。So we do app dot gap， and this sets our endpoint。

And the endpoint that we wantan to use is API slash stories。

And this app dot gap function also takes in a callback callback function。

And this Koback function takes in a wreck。And a response。

And so we simply want to send back the stories to our front end。 And so what we do is res dot send。

All of our stories。And that's pretty much it。I'll keep this up here for a minute if you guys can turn and talk to your neighbor and。

Talk about like what this code is doing。 that would be great。

 And then if you guys have any questions， I'll be here。don like new stories。 How does them。

Like if there are stories。Okay sorry， Can you say that？ You didn't。嗯。Alright。

 can I get a thumbs thumbs up if we're all good。Good， good。Okay， cool。 And so I saw that。

 most of you guys like tried to test it out， test this out already。

 And you guys got like an internal server error or something like that。

 And that's because we're not actually running our back end yet。😊。

I mentioned earlier that in order to get our front end react files， we run NP PMM run dev。

 and we need to do a similar command in order to run our backend。

So open up two terminals and run NPM start in one， and then NPM run dev and the other。

And then check out local host 5，1，7，3。Run MP PMM install。 And I think maybe that will help。

 I' will fix it。

![](img/8cf5410479b52f1f6ecd25c125d030b8_14.png)

Alright， and if you guys have your website out， like you can。哦。We can post stuff。

 and our comments can be posted as well。Or I mess something up。Yeah whatever。 But if we refresh。

 all these posts still disappear。 And that's because whenever we post information， we're。

Updating it on our。Our local state， But we aren't sending it。

 We aren't actually sending it to our backend。 That's why we need to create a post request and then a post end point for our backend so that we can send that post to our back end and our back end just。

Appends it to the list that stories our stories。And so that's what we're going to do next。

Oh before that， does anybody have any questions？哎。

![](img/8cf5410479b52f1f6ecd25c125d030b8_16.png)

So if you guys can run these commands。That'd be good。Okay， so now that we're on the same page。

 we're gonna implement our post endpoint and our post request on the front， so。嗯。For post requests。

 we want to store whatever content we're sending to our backend and Re do body。

And we can actually specify specific attributes for certain information that we're sending to the back end。

Similar to how。How we send down props and those props can be used as attributes whenever we send information using get and post。

 we can specify certain key value pairs so that we have organized data。嗯。And so。

We're gonna implement the get and post。 I mean， rather the， the get。

 the get request or the post request and the post endpoint and the opposite。Order， so。

For our get request， we say get request。 and then we implemented， I mean rather。

 we implemented the get request。 and then we implemented the get endpoint。

 Now we're gonna do the opposite。 We're gonna make the post end point and then create the post request from our front end。

 And so you can do whichever order you guys prefer。 whichever is more intuitive to you。

 we'll just show you that the order doesn't matter。

 just like as long as you have both the get request or the post request and the post end point。

 you'll be good。So example would be like， hello， here's a new story， Miow。

 and then our backend receives that post and adds it to our stories variable。And then we。

 we were usually we like we。We return the post that we made just so that our front end knows that the post was successfully added。

And so if you guys can， so this is why we test it out。 Web labb dot is slash example yesterday。

 Can you guys go to Webla dot s example and then open up the network tab and then try posting something on that website and find your specific。

ATB request and the network tab。哎呀。Oh yeah。 turn and talk to the person next to you so you guys can reach an agreement on what。

They should be building with。

![](img/8cf5410479b52f1f6ecd25c125d030b8_18.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_19.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_20.png)

哎，扣。And so I'll do it with you guys。So， inspect。

![](img/8cf5410479b52f1f6ecd25c125d030b8_22.png)

Open up network。嗯。嗯。I'll post something。Hello， weblab。I get my。

Here's the HTTP request that I sent to the example server。 So it's a post request， it's status 200。

Successfully handled。And then you can see that my response。

 they just send me back the posts that I created。Hello， webla。嗯。Yeah。

 and so if we look at the answer。You see that's post request。

 and our backend server is going to be local host 3000。

 and we're gonna to be using the endpoint API slash story。

 which is the same endpoint that they use on the example server。

We're gonna be sending a post through the request body。

 And then our backend is gonna send us a status code。 and then that same post back to us。



![](img/8cf5410479b52f1f6ecd25c125d030b8_24.png)

2。And so。Whenever we are dealing with requests and responses。

The way that we access information for a post request would be in Re dot body。

 And as I mentioned earlier， we can add our own attributes to Re dot body just by。

Passing in a key value pair as input to our parameters。So here I define a variable。

 which is just a key value pair， which is content and web development class and competition。

And then we pass this in through post， which takes in an endpoint and then parameters。

And then we run some call function that doesn't really matter right here。And then。In our backend。

 this should be app。 Don't worry about Ro。We have our endpoint slash weblab。And it should be API。

 And we take an a re response。And we simply print web development class in a competition by accessing the value Reta body dot content。

So now we're gonna be in the back end， implementing our post endpoint。So。

I'll be doing that with you guys right now。So we are in the backend。

 so we're going to be in server do Js。And so we have our server app。

And endpoint that we want to make is a post endpoint。

And we're going to name the endpoint API slash story since we're posting a story。

And the callback function。We'll take in a wreck。And。

And so what information do we want to get from our rec。Let's suppose that。We pass in。Really。

 we can do whatever we want here。 So let's say our story is gonna be equal to request body since it's a post request。

And let's just say it's the attribute that we make is a story。And so since we're posting this。

 we're going to want to add this to our data structure， which is our array of stories。

And so we simply get stories。And we push our story。Onto our。Stories are rare。And at the end。

 we want to send back this story to our friend to tell them， okay。

 we successfully added your story to our database of stories。We do res do send。Story。New story。So。

 now。嗯。I'll you。 I'll put it up on the screen so that you guys can parse it for a second。

 and like the previous slides， please turn around and talk to a partner and talk about what this code is doing。

Sorry。哦， I see。So it sounds like you guys got it。 So like when， like most of you guys questions like。

They're really like design questions like。It it's a little bit weird to like。

 implement the end the end point first and then send the post request or send the get request first and then implement the end point。

 So hopefully like after all of this， you guys all understand like， oh。

 like whether we send information through dot body dot content or rec do body， it's really up to you。

 and like what you guys want to send through the parameters in a get or post request or。Yeah。

 it's really all up to you guys。And so now we're actually gonna send a post request to our backend。

And so。We want to send a post request to the endpoint that we made and our endpoint is API slash story。

And so we're currently in the front。What do we send as a parameter。Like。

 if we don't send anything else， like， ha， how is our backing gonna know what。

 what posts we want to post， So we're gonna be sending a post through our parameters。And so。

Let's go to feed dotjSX。And we're going to be posting our new story inside of the callback function add news story。

And so just for some context to know what a New storyory is doing。

Let's see where it's being passed into。So。Down here in our like return statement for feed。

We see that we're returning a div with a new story object。

 and then all of our story objects that we want to render。



![](img/8cf5410479b52f1f6ecd25c125d030b8_26.png)

And so this new story object is。

![](img/8cf5410479b52f1f6ecd25c125d030b8_28.png)

Just， let's see。It's just like the， the post， this post。



![](img/8cf5410479b52f1f6ecd25c125d030b8_30.png)

New story object with like the submit button。And so we're passing in our add new story function into that comment。

I mean， sorry， that that component。And so if we want to see where it's actually being called。

 we can open up news story input。New post inputs。Dot Jsx。

And you can see whenever we post a new story。嗯。Or rather。

 we make another Koback function called add story。 And inside of that function。

 we call add new story。And so。We pass this function down as a function handler。For on submit。

So as a callback function add story， whenever we click submit。

 we call that function with our input being whatever text we have in our。Tex box。And so。

 we make our story。We're got started right here。And then we passed it into add new story。

 So as just some context， we're passing in a story object into add new story。

And so let's implement our post request to the back end。So。We know that we're going to be posting。

Sending a post request to the endpoint slash API slash story。And the callback function。呃呃。Or， sorry。

This is the front。 So we're gonna be the post function is gonna be returning a promise。

 And so we're gonna， we're gonna want to actually handle。The promise using dot then。

And remember how we send back the post back to our front end。

 So just to confirm that it was actually added。And so we can have our new story。Object。

And we're going to。Just add this to our state。And so。Instead of value， we're doing new story。Object。

And so， that's pretty much it。And I'll leave the solution up here just so you guys can turn into a neighbor and talk about what it's actually doing。

Oh oh yeah。 No， no， no， no。I think。哦，呀。And so， our。Story is just gonna be value。

 And so we pass in value。As our parameter， the U。So it seems like you guys are pretty much done with this。

 Just like one thing I wanted to quickly mention is that if we do MPM Run start。



![](img/8cf5410479b52f1f6ecd25c125d030b8_32.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_33.png)

Rather， where are you gonna test it now。And so if you guys weren't able to finish it。

 go to go run these commands， and then we'll be able to run our back end and our front end。😊。



![](img/8cf5410479b52f1f6ecd25c125d030b8_35.png)

And we can see that once we post something， post a story， a free refresh。😊，That story persists。

 And that's really good。And one thing I wanted to quickly mention is that， like。

This is rendering our stories。 And whenever we request this website。

 we're just requesting the stories， and then we put them into components and then render them。

 But if we just put in the URL or rather。

![](img/8cf5410479b52f1f6ecd25c125d030b8_37.png)

The endpoint that we created like for getting stories like API slash stories。



![](img/8cf5410479b52f1f6ecd25c125d030b8_39.png)

哦。300， cause the back end。We'll just get all of our story objects that we created。

And so that's pretty neat， except they won't be like rendered correctly。



![](img/8cf5410479b52f1f6ecd25c125d030b8_41.png)

O。And I'll hand it off to a Hong to。In the rest of the workshop。 Thank you guys。哦。Alright。

 real quick。 I'm just going to review everything that we just did in steps 1 and 2 because it was kind of a lot。

 And just show you how the flow goes from beginning to end。😊，In the code and in our ACDP requests。



![](img/8cf5410479b52f1f6ecd25c125d030b8_43.png)

So， if we。Pull up our code。 First， we're going to talk about get stories。

 which we implemented in step 1。And we make the。Get request inside the use effect of our feed。

 That's inside the use effect because we want to know we want to do this as soon as our website loads。

And then in server do Js。Oh gosh。Lucas， why does your computer not drag。Can I， can I。

That's kind of a problem。Can we split oh my god。Okay， fine。 I'， I'll just change tabs。

 That's awkward group， but it's fine。Oh， that one。Oh， thank goodness， okay。Sorry， we're moving along。

So， here。You notice that we have。哎。Here in the front end is when we make the get request。

 and then here in the back end is where we define what the get request does。

And so here what we're doing is we start off by making a get request to slash API slash stories。

 No parameters。 And if you look at the slide here， the content of the HDP request is right there。

 And then you can see that if you open up if you run NPM start NPM Run Dev。

 you open up capbook and then you inspect element and go to the network tab as we saw earlier。

 you can see what the requests actually are。 you'll be able to see the request being sent like at the top of the slide。

😊，And then in our server file， we decide how we're going to handle that request。

 So in the server we say， okay， anytime the app gets a request to API s stories。

 we're going to send back the stories and then the response gets sent that looks like the response on the bottom of this slide。

And then once we receive that on the front end， we're going to take what we received from the back end。

 the story objects， which you can see there。And then we take it and set the react state equal to it。



![](img/8cf5410479b52f1f6ecd25c125d030b8_45.png)

And that renders the front end based on， oh my goodness。

 I hate Max based on what we received from the back end。



![](img/8cf5410479b52f1f6ecd25c125d030b8_47.png)

So that was get stories， that was step one。Step 2， we implemented the functionality to post a new story。

 And so this was also in feeded。And then this is the corresponding back end code。 So here in feed。

We send a story using value。 Now， what is value Well here。

 this add new story function gets called every single time that we hit the submit button。

 like we type something in and hit the submit button to post a new story。😊。

You'll see that value this function gets called using inside the new post input component。

 And so we create a new jascript object with the content， which is what we typed in Right now。

 The creator name is just anonymous user， and then some I D。😊。

And so this is going to be what value the。Parameter here is equal to。

 It's just a jascript object that represents our new story。

 And we send that off in the to the post API slash story endpoint。

 As you can see at the top of the slide。 That's the request being sent。

And then we wrote on the server。What we want to do when we receive a request to the slash API。

 Oh my goodness， slash API slash storyory endpoint here。So when we receive this kind of request， we。

Add the， the story that we just received to the end of our stories array。

 So we distort it in our database or not database， but like in our server。

And then we send that new story back。And so you can see the response here on the bottom of the slide。

 It just responds with the story， the exact same story that got sent to the front end as like a confirmation。

 Here， here's， here's the story that you just added。😊，And then on the front end。

 once we receive this response。We take that response and we add it to our array。

 our list of stories that we're holding on the front end so that we can actually display it。

So that was just a summary of what we did in steps 1 and 2。

 And now we're going to repeat that and do basically the same thing for comments。

 But before we do that， everyone stand up。I'm not going to do anything crazy this time。

 We're just going stretch。rightYou can do a little reach up。Twist to one side。T see the other。

Back to center， lean to one side。Into the other side。Okay， everyone can sit back down。

 Now I'll pass it off to Hong。Hello。呃。Can you guys hear me find in the back？OK， cool。嗯。Yeah， so。我跟他。

Probably speed it up a bit。When we because。Just for the sake of time。But how do。亚的有。嗯。

Our next step is to do the。Slash API comments， get endpoint and make the get request from the front end for the comments。

So before we do that， make sure you're caught up by following the steps up in the top right corner。嗯。

I'll do that here。Allright， so currently， we have our comments hard coded in card do A SX。

 as you can see right here。In our code in Car Jx。And right now。

Because we have our comments hard coded。If we。Try to post a story and refresh。 It'll save there。

 but the comments don't save yet。 So we also want to move this to our backend so we can do the same thing。

Yeah。过。So let's move the data to our server。We've already done this once。 So I'll just do it。Again。嗯。

Yeah，各会。I think filtering through comments is actually like a pretty fast thing。

 especially once we transition to a database， which willll be able to do that operation really quickly。

 like the filtering thing where you filter for comments under a specific story basically。

 So right now we'll code our server so that it just has like a list of all the comments。

 And then whenever you want the comments under a specific one， you just filter for them。

 But databases actually are like really fast at doing this basically。 So once we move to a database。

 the efficiency is less of a concern。😊，Good， so I just。

I just copy pasted from card do J X and dis J S。And。Yeah。Now that the comments are in the back end。

 we need the front end to request them， So we need to set up something pretty similar from or similar to what we just did for stories。

Except there's one catch。Which is that。We。嗯。Which is that we want to filter only the comments that are under a specific story。

 which is what I just talked about。 So here you can see that earlier。

 we were taking all the comments。We were taking all the comments。

 and then we were filtering it for the comments such that the comment parent matched。

The prop star Id， which is basically the story I D that we passed down。

So we want to do the same thing on the server side。

 which means that the client needs to ask the server which story like it wants the comments for。

 basically。And to do that， we're going to need to use Re dot query。哦。

So this kind of three parts to a get request that we've gone over basically。 But for a query。

 I just want to show what that looks like when you pass in like a query into a get， basically。

 So let's say we used get slash API slash web lab as our endpoint。

 and then we pass in this query with some content。First， the query gets transformed into。

Our URL as part of the URL。 So it'll be part of our URL where it sets content as the parameter that we passed in。

And then it'll hit our backend。 So this URL will basically hit the end point in our backend that is labeled slash API slash web lab。

And on， on the back， when we want to retrieve our query content， we can just print out。

 or if we console our log query dot content here， it'll retrieve the content parameter from。

From the URL that we passed in， basically。So if we console that log here， we would get。

Web development class competition， which is what weve fasted。过。So。First step。

 we're going to start by doing the slash API slash comments endpoint。嗯。So， here we're。

Just as a review， we are basically asking for the comments under a specific story。

And then we get back the response from Express。Or from our back end saying。

 here's the comments under that post。 And for now， we're gonna be focusing on the response。

Before that。We're going to。Do one more， one more exercise in Webla do slash example。

 So let's use the network tab and open webla do slash example and then fill in the request method。

 the URL， status code and the response body。 So one more time。 And this time。

 I think what you should focus on is what's going on in the URL and how the query gets transformed into the URL。

Can I get fingers。For how many minutes you need left。我没来。OK过嗯。Yeah， we're just gonna move on。

 basically， what happens。So， again， we're。You'll probably see a different URL when you saw this in K example。

 but。We're using local host 3000 as our server。 So that's gonna be our base URL。

 We're using the slash APII slash comments endpoint， and then。

The important part here is that there's a parent and we feed in the idea of the parent， basically。

Which。Is then met with the response from the server with a status quo 200， and then。

The response body， which is the list of the。Comments that we have。 So we have two comments here。

And yeah。哦。Okay， so let's create a get request。For this story。We're going to be in serverver do J S。

 what。How we。Sorry， I think apparent。 Okay so。Okay， we're doing our gear request first。

Which means that we'll be in car dot J S X。 So we're on our front end right now。 Currently。

 we're coding our frontend react code， which is getting comments for that story。

So we're going to be in Car JSx。And you'll see here we have a two do for step 3。

 fetch the comments from the server。嗯。In order to do that。

 we'll model our code pretty similarly to what we did in feed。嗯。Which pings slash API slash stories。

 Here will'll ping。 Here we'll do a get request from slash API slash comments。

And we're going need it to pass in。A parametermeter， which is our parent， as we just saw。

And what is the parent I D that we have。Well， we actually already have our old code here。

 which uses prop star I D to get the story I D that we pass in or the story I D that we like check for to see if the parent matches。

 basically。So， let's use this。Prop start I D。To represent our parent ID。And then。嗯。

That's it for the get request。 Now， we need to figure out what we would do once we get the response back from the server。

So to do that， we use do then。And for the response。嗯。For the response。

 we need to write a callback function to figure out what logic we do。So that'll look like。

When you get a comments response。为异议。嗯。Second。When we get a comments response。

We take that commentss response and we set comments。嗯，是。好这什么。And then we can delete this line。不嗯。

Yeah。Great， yeah， so that's the solution up there。I'll give you like 30 seconds to like。

Read through that。 make that， make sure that make sense and catch up。呃。

Let me know if you have any questions。Now that we have。而嗯。Our API request written。On the front end。

 we need to actually implement that on the back end。So that's the okay， here you go。

 portion of this step where we are writing whatever is going on in our backend。

 which is in server do J S。So。Currently， we have the list of comments already moved to our backend。

 and now we just need to implement the logic that occurs when we ping this endpoint。过。

So we included the parent stories like underscore I D prop as the parent parameter。

 when we made the guy request from the front end。So how can we access this parent I D from the back end？

 Well， because it's included as the parent， we can just get the parent parameter of something。

 And that something is going to be Re doc query。Because。呃。Like， if you remember， for get requests。

 we're gonna be using get Re doc query to get the parameters that we pass in from the front end。

 basically。Cool， after that， we need to filter out only the comments that are the children of that specific story。

嗯。Ie。 where the parent matches the parent that we actually pass in。Finally。

 we want to send those comments back to the front end。Yeah， so what that's gonna look like。Is。

Defining a get request。After dark yet。And the endpoint is gonna be slash API slash comments。嗯。

And then， our。啊。Input is gonna be a whereas。

![](img/8cf5410479b52f1f6ecd25c125d030b8_49.png)

And then what we want to do。Is。嗯。Find our parents。So。Consparent equals。R die。Qury parent。嗯。

So Reta query represents the query that we got。 and then we take the parent parameter。

 So this should be whatever parent that we passed in from the front end。 Now。

 we want to filter out the comments that our children of that story to do that。

 We can look at what is happening。And never mind， I deleted the line。Okay。Well。

 we can do what was previously in Car dot J S X， which is the dot filter on our comments list so we can take our comments。

And。嗯。Filter them out using the dot filter。Methd。And。We feed in a callback function。Which。

Takes in comment。And for each comment， we check whether or not。

That comments parent is equal to the parent that we have passed in。过。Okay， finally。

 now that we have our filtered comments， we want to send those comments back to the front end， so。

That is just。We can do that， just using Resdo N。Filter comments。And， hopefully。



![](img/8cf5410479b52f1f6ecd25c125d030b8_51.png)

If we go to our front end now。We can see your comments。 Okay， yeah， cool。 Everything's working。

 We can maybe post a comment。

![](img/8cf5410479b52f1f6ecd25c125d030b8_53.png)

呃。So， here's code。Here's the solution code up here。

 which you'll notice looks a little shorter than the code that is here。 They're actually equivalent。

嗯。I just wrote it in more lines over here， but。All we needed to do was filter out。

 And then we used a shorthand。Notation for function。To just map each comment to。True， whether true。

 if。If the parent matched up and then false， if the parent didn't match up。嗯。

So we can kind of shorthand the callback function that we wrote here， basically。

 And then everything kind of fits into a single line。嗯。Yeah。



![](img/8cf5410479b52f1f6ecd25c125d030b8_55.png)

If you put the two， like parts side by side。This is what we have。

So we're making the get request from the。We're making the get request from the client side。

We're processing the get request on the server side， which filters the comments。And then。After that。

 we do the dot then， which is taking whatever response we got from the server and then sending our comments to that comment response。

any questions。Okay， I be。Moving on， we actually just tested it out。 So yeah， it does work。嗯。

In our browser。Now， if we refresh right now。The Miow comment that I made is gone。

 So our next step is to make sure that those comments are persisted on the server by actually posting our comments to the server。

So back on the same page， let's follow these commands。



![](img/8cf5410479b52f1f6ecd25c125d030b8_57.png)

Okay， so we see two two dos first step four。And。We'll be doing those。Which are posting that。

 implementing the post endpoint and then also making the post request from the front end for that endpoint。

Yeah， so as an example。嗯。Maybe we make the。Comment。

 please post this new comment under the story that we give。 And then the response is。Okay， sure。

 you've done it and we'll also send the response back with the comment just to confirm that。

 you know， everything matches up on the server and the client。嗯。I think we will。呃。Skpped this part。

 honestly yeah， Okay，'ll， we'll skip this part because it's like basically the same as posting a comment。

 which we've already done except we're posting a story。

 So the only difference is that the request URL is going be slash API slash comment instead and the request body is going to contain a comment。

Other than that， it's gonna look basically the same as slash API slash story。So。Yeah。

 hopefully this step is actually pretty simple。嗯。In order to post our comments to the back end。

 we're gonna need a post endpoint on the back end and a post request on the front end。

If you remember。For post requests， we are gonna use recordile body to retrieve those。

 retrieve whatever content that we send on the back end。呃，Yeah so。The main difference here。Is that。

When we do our backend code， we're gonna be using rec dot body to retrieve whatever content that we sent through。

 So if our body that we sent through post had one content parameter。

 then we can retrieve that using rec dot body dot content。Yeah， so the first thing。

 the first part of this that we're gonna do is posting the comments。Which is。

The post request to the backend。So。We， what information do we want to send through Reile body。

 We want to send the comment that we plan on posting the common data。

That we want to post is passed in through the add new comment in Car do J S X。

 So let's dig a little deeper into here。Let's add new comment function。

That we have here is's being called。 Or first of all， it's being passed into comments block。

Which then passes it as a prop into new comment。And new comment calls。I do comment with。

This Json object here， which represents a comment。 It has a content， a creator name， an I D。

 and a parent。So our new comment component is going to be calling a new comment with。

 with an object that represents a comment。 So whatever is being passed in。To add new comment here is。

 we can basically think of it as。A comment already。 So we don't have to do anything with it。

 All we need to do is post it to the server。So in order to do that。嗯。Sorry。In order to do that。

We will be。Making a post request。 So post。30。Slash API slash comments is the end point we want to use。

And then。嗯。The body that we want to give is just literally this comment。Object。



![](img/8cf5410479b52f1f6ecd25c125d030b8_59.png)

And now。After we。Received the request from the server。

What we want to do is take the common object that we get back。And set comments。2。嗯。

Our original comments list with this common object added on。 so there's the solution。呃。Yeah。OK嗯。

One question that I'll give you like a minute to discuss is。Why we need to set this comment inside。

Why we need just call set comments inside the dot then。Rather than just outside of。

Why we can't just do the set comments outside the dot then， because even outside the dot then。

 we have this comment like。This comment parameter that were being passed into the function。

 So why do we do this inside the dot then rather than outside。

Maybe turn to talk and discuss for a bit。OK嗯。I'm just going to bring it back because we do need to keep moving forward。

But basically， the reason why we put this said comments inside the dot then， why we call it。

 why we call set comments inside dot N is because if we call that outside。

 then there's a chance that our promise doesn't fulfill， but we still call set comments。

And what was that， What would that mean， Let's say。

 like the server like crashed or aired when we were trying to post this comment。

Then we would still be showing it on our own front end。 But on the back end。

 it would actually like not exist。And this is a problem because generally。

 we want whatever is showing on our website to reflect what's actually like in the server。

 So we don't want like we， we don't want to be showing users， hey， like you actually。

 you posted this post or you posted this comment successfully when， in fact。

 like their comment actually like didn't get posted successfully。 So in general。

 we like do these like logic inside the dot then to make sure that we're reflecting what is like actually on the server basically。

嗯。Okay， so after， so we already done the post request from the front end。 Now we want to do the post。

Now， we want to respond to the post request from the back end。So again。

 that's going be in server do J S。呃。I。Oh， right。过， so嗯。

We need to add an API route basically that correctly respond or yeah。

 correctly responds to post requests to slash API slash comment。 So that is this。Response arrow。Yeah。

 so it's gonna look a lot like post slash API slash story。 Thankly， again， we don't。

 I need to do too much work here because our comment is actually just passed in as the body of our。

Our request。 So all we need to do is basically。Take rec dot body。

 and that will literally be the comment that we want and then add it to the comments list。

So what is that going to look like。Basically。We'll define a post request using opt post。嗯。

And then slash API slash comment is the end point that we wanted to define it on。And then。

Taking in a request and response object。We want to。Simply。嗯。Get our new comment object。

 which is going to just be。到 body利。Then we add the new comment to our comments list。

 which we can do by doing comments stop push。commentment。Finally。We send it back to our client。

 using Reddoend。嗯，你考虑。Cool， here's a solution。I'll leave it up。For just a little bit。So yeah。

 I'll leave the solution up on this screen。If you have any questions about it， please let us know。

 In the meantime， I will test this on my front end to make sure everything is working。



![](img/8cf5410479b52f1f6ecd25c125d030b8_61.png)

If I go here， and I type。I like dogs。Sure， okay， stories still work。And let's say underneath here。

 I type。不。Okay， and then if we refresh， everything is still there。 So yeahy。

 we have made sure that these things made sure that the both the stories and comments have persisted on the back end as well。

 So that when we refresh。We嗯。When we refresh， the things don't go away， basically， yeah。Great。

 any questions。So yeah， hopefully you should be able to also go in check and make sure everything is also working in your own。

 in your own browser。Are we doing another one。呃。Maybe I'll just。Yeah， we might。Alright。

 so now we're going to briefly review everything that we just went over in steps 3 and 4。

 And then after that， we'll take a quick break。 and then we'll move on to something a little less brain intensive。

 more chill， more fun。😊。

![](img/8cf5410479b52f1f6ecd25c125d030b8_63.png)

Al right。So let's look again at the， was' everything in feeded Hong。Oh， right， right， right， okay。

So we have card。And then。Split screen with。Oh， wait， I should suppose screw a server。Can I do this？

 Nope， oh， I can， okay。Okay， so first， if we want to get all of the comments in step 3。

 what we did was we。Send a get request to API slash comments。

 and that included some query parameters here。 So the get request included a query parameter that had the parent。

 which is the story that we were posting that comment under and then。

What that looks like is it sends a request to the URL。

 and then it adds the query parameters to the URL。 So we have local host 3000 slash API。

 and that should be。Slash comments， yes。And then question mark and then the query parameters。

 So all of that information gets sent in the URL because for get requests。

 they cannot have bodies of the request。 A get request will only have parameters inside the query inside the URL itself。

And so after we send that request here， then the server。

 we have this endpoint slash API/ comments that's listening for request to slash APIpi/comments and when it receives one。

 it takes a comments list， filters out all of the ones that have that particular parent that we received from Re doc query so this is pulling out the value associated with the parent in the HtGP gett request。

And so it takes all of those comments and sends them back to the front end。

 and that's the response that you see at the bottom of the slide。And then， on the front end。Once。

As soon as we receive that response back from the server。

Then we take the comments that we received here。And we set the react state with it。

 which allows the front end to render based on what we received back from the server。That was step 3。

 And then finally， in step 4， we implemented the functionality to send a new comment over to the server。

 And so what we did here is。😊。

![](img/8cf5410479b52f1f6ecd25c125d030b8_65.png)

Add new comment gets called anytime you type in a thing into the little comment box and hit the submit button。

 and then that will pass in the information about a comment。

 And so we're gonna take that information about a comment that we have in our front end that was defined a new post input。

 and I won't pull it up， but it's just a jascript object that has the comment information。

 We're gonna take that and send it as the request body to the server。 Now， notice here。

That when we get our request， all of that information of the parent is in the URL。

 But then when we do a post request， the convention is a little bit different when we do a post request。

Then that is sent not in the URL， but inside the body of the request。

 So this is what our H TP request is going to look like to post a new comment。

And then same as before we have this endpoint that's waiting and listening for any request to slash API slash comment。

 This is in our backend on server do Js。And then once we receive that。

 then we're going to take the new comment that we received。

 this is rec out body because it's the body of the request， as you see up there。

And then we're going to add it to our comments listed that's stored in the server and then send back the comment that we just received to the front end。

 And so that's why you see in the response， we're sending back the exact same data that we received from the front end in the first place。

😊，And that's just confirming that it worked。And then in the front end。

 once we receive the response from the server。We take the response that we receive from the server。

And。Set the react date， set comments to。What it was before， plus that additional comment。

 And so we can display the new updated comment list on our front end。Any questions on any of that？

Cool， did you wna take over for the last bit。呃。I'm a be kind of speedy， speedy with the last part。

We wantna。Finish on time， I think。But basically， if we look into our server， dot S。

And we'll only be focusing on our server for server now。We have。

A pretty long server O JS file right now。Let's make sure we're to caught out first， using like。

 get reset hard， and then we'll check out。Next up。Step 5。Yeah， so。

We have a pretty long server O J S file right now。 It's like 120 lines。

 And if we wanted to write more API endpoints， those are all and if we wanted to write those and they all went into server Js。

 then it would get a little crowded。 And this is especially an issue once server R Js starts having to also handle things like。

Like connecting to our database or like making queries to Google calendar or whatever else you want to do。

 if you all put it in one file， like this will kind of be a nightmare。

 So what we want to do now is basically move some stuff away from server Js and I kind of just like want to show how we would do that if you'll notice in our workshop 35 we have made a nice folder here or sorry。

 a nice file here called API do Js And so our next step is basically going to be moving everything from server do Js that is related to our API into this file so that we can implement all our endpoints over here。

Yeah。The syntax for this is going to be app dot use， which is a middleware。 And we pass in a router。

 which is basically a。An app object， just like constant app equals Express。

 except it allows us to import this object from other files and。And use。

 use the endpoints from that file， basically。So let's check out that branch。Which I already did。But。

 yeah。I'll I'll move kind of quickly here， basically， just because I wanted to finish。

How this is going to work。Is we're going to move everything that is currently in app。

 which is serverS into a router。 And the reason why we do this is mainly for organization and modularity。

 So basically if we organize into different files， it'll be a lot more clear where things are and modularity means that we can work within a specific file without worrying about what's in the other files basically。

So currently， just in an example， we have in slash API slash test endpoint right now。

 We want to move it to router do J S。Or sorry， we want to move it to API dot J S。

 and we'll have slash API slash endpoint in API dot J S instead。

So the steps is creating a separate file， which we have already done。嗯。嗯。

Defining a router for s API do JS and API JS。嗯。过。That's all we need to do there。嗯，Next。Next。

 we want to export our router so that our server can see it。

So that's just gonna look like module that exports。

 which is essentially the back end or the backend version of export。Exporting like any function。

 So if you remember like export。Export default。From the front end。

 this is like the version of that that we do in the back end。

So module that exports equals router will export this so that other files can see it。Yeah。

 if you ever are confused about how we know how to do anything。嗯。Feel like generally。

 you get these things by looking up the documentation。 So if you ever don't know how to do something。

 you can look at the documentation for any help。嗯。Cool。

 so the next step is defining the middleware to route any API paths。Over， so to do that。

 we're going to go back into server J S。And we're going to。Deefine。嗯。A router。Which is just。

Requiring。Which we do by just requiring。嗯。API。And then。嗯。The next step is to use the router。In。

In the server， which we do by implementing a middleware。 So what that's going to look like is。

Using an app Ill use。And。You feed in this API path， which means that anything。

 which starts with slash API will be。Using this router for。O。Finally。

We're going to move everything that we've just implemented。哦。Into。API R JS。

What the heck is happening。Okay， so we just literally just copy pasted everything that we had in app dot or in server dot J S。

 into app dot Js。嗯。So嗯。Yeah， let's see what this looks like。

We see that we have this app dot get slash API slash test over here。

What that turns into on the server side。Is。This we instead， use router dockette。

And instead of slash API slash test， we use slash test because when we wrote here。

Cont or app use slash API。 This will route everything that starts with s API over to the router and。

Get rid of that slash API tag or s API part of the URL on it。So。To recap。

App turns into router because we're now using our router instead of our router object instead of our app object。

And then anything that with， anything with this slash API。Tag， we get rid of that slash API tag。不。

So let's do this for all of them。I'm going just replace all instances of app with router。给。

So now we're doing router do yet for everything， and then we'll just delete。Everything。对。嗯。

Every single slash API at the start of each URL。哦O。That was a little fast。对。Again。

 if you have any questions about this， just come to office。Okay。嗯。



![](img/8cf5410479b52f1f6ecd25c125d030b8_67.png)

Let's go to our front end and see if everything is working。Okay， cool。

 So it looks like everything is working。 We can like try to do a few test things。😊，嗯。And then。Yeah。

 okay， cool。 Everything is working over here。 If you check conser dot Js， we it's a lot shorter now。

 now that we've moved stuff to API dot JS。

![](img/8cf5410479b52f1f6ecd25c125d030b8_69.png)

So， in general。This， this kind of syntax is really helpful in case you ever want to move stuff that you have to find in server do J S to like another file。

 basically。嗯So。Now that we have everything in API dot J S， any future endpoints that we write。

 we can just put an API do J S instead。Yeah， okay， you can play around with that a little bit if you like。

 But that's the end of like my lecture in Lucass。 So hopefully you guys enjoyed that。

 please give us feedback at weblo。 slash feedback。Our next lecture will be on databases。

 so see you after a short break and maybe an announcement from。



![](img/8cf5410479b52f1f6ecd25c125d030b8_71.png)
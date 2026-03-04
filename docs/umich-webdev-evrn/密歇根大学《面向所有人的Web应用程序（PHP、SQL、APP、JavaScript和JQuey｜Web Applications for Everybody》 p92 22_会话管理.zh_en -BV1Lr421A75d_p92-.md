# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p92 22_会话管理.zh_en -BV1Lr421A75d_p92-

![](img/259971f8bd24a99cad9787738b209510_0.png)

![](img/259971f8bd24a99cad9787738b209510_1.png)

Okay， so now we're going to talk about PhP sessions。 Now they're related to cookies。

 but you really have to separate them。 So cookies are a browser concept and an H TTP concept。

 So just review， the server sends a cookie。 and then it's like stored in here。



![](img/259971f8bd24a99cad9787738b209510_3.png)

And then then the browser sends it back x equals 4。

 we saw the set cookie request and the cookie header， okay now。

Sessions are data that we store in the server， so you wouldn't store like the current account balance or even the current logged in user。

 at least unencrypted in a cookie， because this is part of the browser and you can change it right you can actually change it。

 You can delete it。 You can throw them away， and I'll show you how that works in some of the demonstration videos where you throw these things away。

But what we can use is this cookie to effectively unlock a session。

 and a session is a little bit of data。Sttored generally the web server。

 although you can store it externally in all kinds of servers， depending for more advanced things。

 and could even be stored in the database， but for now， we'll just take it the simple way。

 It's not in the database。 It's a little tiny file that lives on the server。

And so just like when this request is coming in， we have Gt。Post。

And the get in the posts come from forms and parameters， we have cookie。

Once we figure everything out， this data here is going to be session。

Now what's cool about session is this is a two way connection we can also the cookies are sort of a two way we can use set cookie to send it as well。

But session is data that's really easy and it's another super global。

 So now we're going to talk about given what we know about cookies。

 how we implement and use sessions in PhP。

![](img/259971f8bd24a99cad9787738b209510_5.png)

So。When we meet a new browser， we check to see if there is a session cookie。 It's still a cookie。

 but a session cookie。 And if there is no session cookie， we make up a large random number。

 some unique mark。 And then we send it as a cookie。

 and then we create a session with that same identifier。



![](img/259971f8bd24a99cad9787738b209510_7.png)

And then when we get the next request， we see， oh， there's a session cookie here。

 and then we can reconnect that session in a way we go。

 And so the PhP takes care of a lot of this session stuff for us like a web framework。

 And so the session identifier is subcurity by obscurity。 We pick a large random number。

 We turn it into hex characters and we stick it in the browser and we stick that in a cookie。 now。



![](img/259971f8bd24a99cad9787738b209510_9.png)

![](img/259971f8bd24a99cad9787738b209510_10.png)

If you somehow compromise your session identifier and lose the session identifier， then。

Someone could fake the session identifier because they could change the cookie in their browser and take over your session。

 but because these are such large random numbers， we generally don't worry too much about that and they only live for a little while。

 so when you close your browser that session is gone and it's gone on the server as well。



![](img/259971f8bd24a99cad9787738b209510_12.png)

![](img/259971f8bd24a99cad9787738b209510_13.png)

So we tend to store not too much data in the session。

 but if you take a look and you took a typical application， especially a PhP application。

 and you go to it for the very first time， you'll see this cookie Now you can change the name of this cookie in the configuration of your PhP but by default。

 the cookie is named PhP session ID and that is coming back from the browser on first page long before you've pressed the login on anything and so there's a session and the login is different。

 we'll talk about login later， the session is just a place to store data that is a two-way place to store data。



![](img/259971f8bd24a99cad9787738b209510_15.png)

And so now。This isnt space。 This is not time。 Now， what we end up with is a browser that has a session cookie with some large standardrum number。

 a different browser， dot dot， dot dot， more browsers， different users，  different cookie。

 dot dat do da da， different cookie And inside the server。

 we have a little storage that corresponds to each of those things。

 so that when we see a request coming in， we can reassociate using the cookie。

 we can then look up among all the sessions， and pick the right session and hand that into PhP as dollar underscore session。



![](img/259971f8bd24a99cad9787738b209510_17.png)

So the cookie unlocks the session as it were or chooses the session for us。



![](img/259971f8bd24a99cad9787738b209510_19.png)

So PhHP has good support for sessions built in， we basically establish or create a new PhP session by calling session Start before any output and you'll see a lot of things we'll talk about upcoming that you've got to do them before any output。

 this is another word for in the model。So it's in the model code， not the view code。

If the user has cookies， we can then use the session variable to store from one request to another。

 So this is a two way variable。 You can take stuff out of it， and you can put stuff back in。

 And so now we have a bit of stuff that you probably wish， oh。

 why can't I keep that post data while the post data vanishishism and it's recreated on every request response cycle。

 but the session is not。 It's reassociated， So you have the cookie。

 It reasociates the session and the default place that we store these things is on desk。

 So now we have a time situation where。

![](img/259971f8bd24a99cad9787738b209510_21.png)

Once you've got the session established， the cookie comes in。

 it pulls the session in to the session variable if in your data。You change it。

 Then that data is written back out to the disk。 and then this response comes out。 Now。

 sometime later， we do another thing that it creates a get request with some kept parameters。

 And then we pull the session data in， and then we can make changes to the session data。

 and then we send the response。 Time passes。 another post comes in， it makes post data。

 So the post is created each time。 different post data， we pull the session data out。

 and then if we make changes。 We put the session data back， send the request。 time passes。

 you get the idea comes in， got there's a post request。 We get new post data。

 but then we pull the session data into session， we make changes in here， get sent back。

 and the response happens。 So this is sort of this like。

Global variable across a series of request response cycle and its a cycles。 and it's an array。

 it's a key value array。 you get to pick the keys。 you get to do whatever。

 Now one thing we don't put gigantic stuff in session。

 we use it sort of like a little breadcrumbs for our application like logging in and logging onto is something we're going to store in this session area。



![](img/259971f8bd24a99cad9787738b209510_23.png)

![](img/259971f8bd24a99cad9787738b209510_24.png)

You can find out where your server is configured by PhP info。

 You can find out where it's storing the sessions at and you can even go look at the sessions。

 and there you go， you'll say， oh look here we go。 This is a little file and it's keyed by the session I So when when the request comes in it goes and finds this little file。

 And if you're to look at this not they're not guaranteed to be viewable。

 but this happens to be viewable。 It's kind of a series of key value pairs in here and says it's an integer。

 this is sort of a magic format that we're not supposed to look at。

 but it's the kind of stuff that's being stored into and out of the session variable is' stored on disk。



![](img/259971f8bd24a99cad9787738b209510_26.png)

NowSome people debug their applications by looking at these things。

 and I've done that from time to time， rather than printing it out。

 So the way this works is somewhere very early in your application before anybody。

 any output has come out， you say session start and session start does one of two things。

 If the cookie doesn't exist。 It sets the creates the session in an empty session and sets the cookie。

 If the cookie does exist， it reassociates the old session， whichever the case is once you're done。

 dollar underscore session can be used， so you can't use session。Until you call session start。

 so you can't use this， the get in the post and the cookies are set before the first line executes。

 the session is only set after you call session start。

You can wipe out all the keys with sessionession destroy。

 and then you simply store stuff in session by using assignment statements。



![](img/259971f8bd24a99cad9787738b209510_28.png)

So here's a little bit of code that you can run and play with。 And so here we go， comes in。

And we're going to call session start right， and you can't have any output there。

 but this is kind of in our model view controller， this is sort of the split here where we're doing the sort of the stuff that you can't see is done here。

And so but we're looking at session data， so remember the session data is coming in and going out of this application。

 so if there is a key of pizza in session， we print that session is empty。

 and then we say session subpizza is0， so we're storing it in the session。

And then we fall through and we print out session。And then the next time。It comes in。Session starts。

 Well， pizza is now equals 0。 That's in the session。 It's outside。 And once we say session start。

 this is pulled into a dollar session。 So this becomes false because there is a pizza key in there。

 And so that it says， if the pizza is less than session， pizza is less than 3。

 we're going to take the old value。 The 0， add one to it and store one in it。

 and we're going to put a one in here。 And then it finishes and does the thing。 But now time passes。

 and there is a one sitting in here。Comes back oh。Pizza equals one。 so comes in。 It's set。

 It's less than3。 We add it。 It becomes  two， runs， comes in again。 It's 4， et cetera， ettera。

 et cetera。 And you get the idea。 The point is， is that in this statement right here。

You are reading and writing from the session， which is outside this， and it's not in the browser。

 The session is in the server。 Somehow the server is responsible for it。

 The cookie unlocks the session。 The cookie reassociates the session。

 but the cookie is not the session。 So it's x equals to 4 key value pairs stored in the server。

 and it's a superg named dollar underscore session， It's established。

 So if you were to print session out here， it doesn't exist。 But then once you type this。

 then it does exist。 So the session start。

![](img/259971f8bd24a99cad9787738b209510_30.png)

![](img/259971f8bd24a99cad9787738b209510_31.png)

Reads the stuff off disk because you can have some of your PhP that doesn't use the session all and then you don't have to call session start if you're not going to use the dollar earn score session variable。

 you don't do that so。Here's what happens when you click it， creates the session ID the first time。

 and then sets it to zero。

![](img/259971f8bd24a99cad9787738b209510_33.png)

And then you keep doing it， it goes one， two， three， and then it calls the reset。

 and then it empties it out。

![](img/259971f8bd24a99cad9787738b209510_35.png)

That's this code here is if this gets to be three or larger。

 it calls session destroy and then restarts the session and then runs and does the thing。

 so that all session destroy， it doesn't change the session ID。 I mean， it's the same session ID。

 but it does delete all the keys inside of it and so it empties the session out。



![](img/259971f8bd24a99cad9787738b209510_37.png)

![](img/259971f8bd24a99cad9787738b209510_38.png)

So the next thing I want to talk about is how sessions can work without cookies because this is a really。

 I think， really cool feature of PhP。

![](img/259971f8bd24a99cad9787738b209510_40.png)
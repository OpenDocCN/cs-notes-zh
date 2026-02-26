# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p37 -37-COMP6080 - Javascript AJAX 🦊 Fetch.zh_en -BV17RXGYuEaM_p37-

Promises in and of themselves whilst they're a very interesting type theoretical computer science thing。

😊，To us pragmatic concept pragmatic programmers， it's kind of useless until we introduce the Fech API。

😊，So the first API is meant to be a replacement for XML HTP request。

 and the main thing about it is that it uses promises right out the gate， it is promise based。😊。

And it lets us do all the stuff we did before， but gives us a nice way to do it with promises and in the language of promises。

Before we when the XmL HttP requesting would throw an exception if it was like a network era or something like this。

That will amount to being a rejection in the Pro world it won't reject if the HTTP status is is not 200 though so it's only for network errors。

 which is really useful right because it means that you can catch any unexpected errors in a nice nice way and you can handle expected errors again in a nice way using Dotlands。

嗯。Yeah， so it also takes in this is more of an API thing。

 but it takes in obviously the URL that you own fetch from and then it takes in some。Arguments to。

Like customize how it's going to do the request， the main one。

That you' probably be using is just to change what HTTP message you're going to be using so this defaults to get I've just said your process to show that you can change it。

 but you can add more things you can change the authentication token you can add headers like the accept what was access control all that stuff of course and again HtTP message you can also change but it already looks much nicer right？

不这 out的。So here I have the previous lectures example with fetching from our Chuck Norris API。

 so just to recap it， if I open this up， you can see we're going to get some Chuck Norris memes。

 if I praise Chuck Norris。Nothing happens here。诶。I should do something。Did I open the right？

Think here。Yeah， I should。I'm relatively surprised as by that're not doing anything。😊，Oh。

 because that isn't real thing。 That's why。Yes， there it is。是。Oh my god。

 this is such an remember if you think of pop anyway。

 we're going to convert this into using fetch so let's go ahead and do that。😊。

The first thing is we're just going to get rid of everything。

 well actually let's do this quick a bit。😊，So I said before that would be sort of rarely。

ever creating a raw promise and that's true because if we just call fetch。

 fetch will create our promise for us so we don't have to， which is pretty awesome。😊。

ItAll we need to give that is the URL， and then。This is where we're going to do some chain。😡，Soir。😊。

Let's do the error case first。So if remember， this promise that pet transfer will reject。

In this case where there's an over these cases where there's a networkarrow， So in both of our cases。

 we're just out putting to the console， so let's just。Do the same。Not complete。

 but we don't really care what the argument is。But I will say。That was just an error。Okay。

But how do we do this inside stuff？😊，Well， we do this by。Chaining with up then。Now with FTs。

 you have to be a little bit more， how would you say stringent about what to do。

 so what Fs returns when it fulfills is the response object。

And it's this response object that we can go ahead and check status。And and do stuff。

 So what I'm going to do is similar here so we can say if。

Rs dot now it has this thing called okay and this will be true if it was okay and false it wasn't so we'll fill what happens in the okay case in a second。

 But if there was an error， so it's not okay then we'll just。😊，See what the error message was。

Resdo sense， same thing。Okay。And then what we'll do is we just so anywhere， well， I guess。Wevo。

We'll just throw this as the error， actually。Remember， if we throw this。

 this will count as an implicit rejection for this dot then， which will go inside of here。

 so that's exactly what we want。But if we are okay， then what happens？

Is that to get at the data now that fetch has native JSson support there's actually a method called JO like this and as you can see it actually will return a promise as well so you can't just use the JO directly you have to。

😊，Return。You have to chain with another dot then， so we have the dot then to get out the JSson。

 we need another dot then to actually get out the data like this。Yeah。😊。

So it's two steps first you get the result and then you get the JSO by returning the JSO promise us and chain。

And we're just going to do the same thing。But instead of being called name design。

 it will be called date。Yep， so if I just comment all this stuff out。Yeah。It's a， many less lines。

It just looks nice so at that， so let's go ahead and run this。😊，And it works。 Okay。

 let's go with another one。Cool。So you can see it works and it's much nice。

And just to show off that we go into these dark catches。

 let's go ahead and copy the internet again by throtling。First shock Norris check the console， Oh。

 no， there was a network  error， See we went， we went into that catch。

 Let's turn the internet back on。😊，And go to our fake。Soい。And we' pray our Norris。In our consult。

 there was another network error， right， 404 specifically。😊，Oh， we just don't print out the error。

 but yep， so everything works exactly the same way as XHL， but it's just nicer。😊，It's just nicer。



![](img/a0e9760ed3a992ed0886a5c84a81f0a0_1.png)

Yes。

![](img/a0e9760ed3a992ed0886a5c84a81f0a0_3.png)

Okay。So we have all of this nicety， but。It's not a silver bullet， we shall have some differences。

 so let's go through them。Well， probably the biggest thing that this XML HTtP request has going is that it will work even for In Explorer5 or very old versions of browsers。

 so if that's something that's important to you and fetches and available then youre kind of stuck。😊。

With HB requests， so， but you should always default， of course， to that if you can。

XmL HtTP request to my knowledge is the only thing that lets you like hook into the large download progress and all this stuff。

 like to monitor downloads， you can't do that with promises and fetch that I know of without。

 I think using streams which is like a separate API that is also built on promises。😊。

So it's not as simple as it was with XMl HTTP request also cancelling promises is not easy。

 which is something that's actually important like for time knots right you need to be able to cancel sometimes。

😊，So they each have their benefits and their drawbacks but fetchch I would say has more benefits so you should should be using that yeah and the streams API that you can use with fetch has a nontrivial learning curve so if you're interested then you can go and look that up there's a link to the dos there。

Yeah， but you know， we're moving forward， right？That's just awesome， it's nice， it's flexible。

 uses promises， which is pretty awesome。😊，But you know， like if you look at it。

 run back a little bit。Where's the。If you look at it。Like。Still， we're not。

In our regular function scope， right， we're doing stuff。😊，Inside of these steps。

And like we want this ability， right？So promises don't give that to us。So。Can we do that？Well。

 I think we can and that's what next lecture is going to be about we'll be talking about async kindaway and doing some more fetching stuff。



![](img/a0e9760ed3a992ed0886a5c84a81f0a0_5.png)

So。See you guys now。
# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p93 33_07_01_Django中POST重定向的实现.zh_en -BV1Kt421V7EE_p93-

SoNow we're going to solve the problem of a post followed by a refresh and we're going to use something we've talked about before。

 we're going to use a redirect right so the basic rule is never send HTML as a result at the end of a post request in a sense if you're going to return something at the end of the post method。

 return a redirect， don't return HTML now we've got to eventually get them some HTML so we redirect to a page that we know and then that will cause a get request and then that page is what we will show so the question is handle post。

 send a redirect， and then redirect to where。

![](img/e7c3a03300ff1551556e3fd94065b741_1.png)

![](img/e7c3a03300ff1551556e3fd94065b741_2.png)

Now this is kind of controller right we talk about model view controller right controller is oh。

 something happened and I'm going to move the user's browser from here to here。

 so redirecting when we're redirecting in a sense that's a controller function so we often do our redirects from the views or we're saying here at the end of this view you know what I don't actually want to show you a page right now I'm going to send you to another page so that that page you see with a get request and we often send ourselves back to the exact same page。

 we take a post from on a page and then we redirect right back to the same page。



![](img/e7c3a03300ff1551556e3fd94065b741_4.png)

So to remember。We got 200 OK， which is a nice page， we got 404 not found。

 we saw 403 not authorized before and 302 is found and moved and we're going to reuse this redirect capability。

 but we're not going to do a like wild redirect to a site completely outside of our site。



![](img/e7c3a03300ff1551556e3fd94065b741_6.png)

So this is a diagram from Wikipedia that's talking about the post redirect and on the left side we have the problem where the user fills out some kind of a form does op post。

 changes the data in the server， we send back a 200 request。

 says your order was successful and then the user hits the refresh button Now the key is this only happens if user hits refresh and then the browser asks are you sure you want to do that and if you say yes。

 then it's going to order twice or deduct the database twice So the solution is for us to have the user fill at the form。

 click a submit， send a post request， do the actual transaction。

 insert an order or do whatever and then send a 302 redirect and then the browser instantly goes blink blink blink's the browser instantly turns this into a get。

Postentially。Right back to our same page。And then we send the page back that says your order was successful or whatever。

 and then if the user refreshes that， it just says over and over。

 your order was successful now one of the things we're going to also show you when we do this is that we might actually have some kind of a message in that moment of post because that's where we got the post data and then we've got to pass that to the next request and we're going to use the session to do that and then the message can come out so this whole order was successful often it knows the order was successful in the postcode so we have to send this to the next request and we use the session。

To get it from the post request to the next get request and that's a technique called flashlash messages and I'll show a simple way of doing that and then later we'll show a more complex way to do this Django style。



![](img/e7c3a03300ff1551556e3fd94065b741_8.png)

Okay， so here we go， this is actually the nice way to do this， right？When we first go to the page。

We're going to go to a get request。We're we're going to see if there's a message that's that incoming message。

 but it's the first time so there is no message we'll talk about that in a second。

 If there is a message once we've got it， we're going to delete it from the session and then we're just going to send the guest。

 HTMLm with the message but the first time to message is false so you'll see no message right so the first time through in a get request it runs this template there is no message and then the CSRF token is there and so we get to see that as our get request okay。



![](img/e7c3a03300ff1551556e3fd94065b741_10.png)

![](img/e7c3a03300ff1551556e3fd94065b741_11.png)

![](img/e7c3a03300ff1551556e3fd94065b741_12.png)

So that is the get request， so we then put in our guess and then we press the submit button that gathers all that data up and sends a post to the browser。



![](img/e7c3a03300ff1551556e3fd94065b741_14.png)

![](img/e7c3a03300ff1551556e3fd94065b741_15.png)

And so that post。We'll end up after CSRF checking will come here because it's opposed。

And so what we're going to do is we are going to grab the guess。

 which now is coming from the post data， we're going to check it and message is just a message of too high to low。

 etc ce， and now instead of rendering which is what we did before we rendered right here。

 we're actually just going to set that into the session under message we're going to store it。

And then we're going to send a redirect， and we're going to send a redirect to request。 path。

Which means that we're actually telling the browser to do a get request right back to us。

 which means it's going to come in here， then it's going to read the message。

 and then the messages is going to come out here。Okay。So that's how the post happens。

 let's go through that again。We get the post， we grab the guess， we check the guess。

 and we store our response to the guess in the session， and then we redirect back to ourselves。

 which comes into the get， we pull the message out of the session。

 we delete the message from the session， and then we actually render the page。

 so you get the original get request， we type in your guess。



![](img/e7c3a03300ff1551556e3fd94065b741_17.png)

![](img/e7c3a03300ff1551556e3fd94065b741_18.png)

Here the submit button。Went to the URL awesome， but it came back with a 302， not with a 200。

 and with a location that says go back to get post awesome。 So that's the same URL that we posted to。

 We posted to the URL。 And if we look underneath the response。

We'll find that that's empty okay so on the post request there is nothing in the response。

 there is no page because what we're seeing here is the result of this get request， okay。

 so what happens is is that the browser sees the 302。

 sees the location and immediately turns around and does a get request and then that get request shows has this page。

 and then it's going to get a fakcon which is just another get request。

And so this is the get after the redirect and we can see in the data that's associated with it and it's got this one actually has a real response。

 it's a real 200 and then we have the real page and that renders it and then it grabs the favicon just so that I can put a nice cute little favicon up there。

Now， if we hit refresh， so we sit on this page and we hit the refresh。

Then what'll happen is it it'll rerun the most recent thing and the most recent thing that we got was this get request。

 which means it does another get request， whereas before it was redoing the post request and that's why it was complaining so you get no message。

 you get no problem you get absolutely nothing so it's actually really quite pretty。



![](img/e7c3a03300ff1551556e3fd94065b741_20.png)

![](img/e7c3a03300ff1551556e3fd94065b741_21.png)

So here is the pretty little way of doing it and the simple rule is。

And the first rule is at the bottom of a post method you should be redirecting if you're sending a screen back at the bottom of a post message after the date has been handled。

 then it's a mistake so the steps are we go to the page we do a get request there is no message so we get sort of the page with no message then we do a post request。

 the post request comes in we check the guess， we put the message in the session and then we redirect and then it comes back to a second get。

 pulls the message out of the session， deletes the message from the session and then renders it with the message and everything and it's called flash message flash message pattern in particular because we're deleting it after we've shown it to the user。



![](img/e7c3a03300ff1551556e3fd94065b741_23.png)

![](img/e7c3a03300ff1551556e3fd94065b741_24.png)

So next we're going to switch to how Django actually has forms。

pyY and makes it easy to construct forms， so we're not going to be writing a bunch of input tags or option tags or select tags。

Jengo makes this a lot easier for us。
# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p91 21_Cookie技术.zh_en -BV1Lr421A75d_p91-

![](img/2371360732cd30a82a78008456b5af87_0.png)

![](img/2371360732cd30a82a78008456b5af87_1.png)

So now we're going to talk a little bit about what we call cookies and sessions。

 The idea of cookies and sessions is that。Web servers need to know which of many browsers they are communicating with。

What we've done so far is we really have a web server。

 a database server and a browser all on the same computer， and so it's all you。

 but in reality you have a database server and web server and like  a thousand users and which of those browsers is it talking to？



![](img/2371360732cd30a82a78008456b5af87_3.png)

And we do this so much when we log in and it knows who we are。

 and it knows what our shopping cart is。 We take all this for granted。 But in this lecture。

 we are going to dig in to the mechanisms that make all that possible。 It's just so automatic。

 It's another one of those things that if you don't know what it is。 It's like whoa。

 I didn't realize it was that complex。 And then once you understand， it's like， of course。

 it's no big deal okay。

![](img/2371360732cd30a82a78008456b5af87_5.png)

So the first thing we're going to talk about are what are called cookies。

HtP cookies cookies are part of the HTTP protocol， so they function here。 They don't actually。

 they're very much not stored in the server， they're not stored in a database。

And so the idea of a cookie is it's a bit of data that's stored in your browser。 It's key value pair。

 It's almost like a PhHP key value array that's stored in the browser。

 so you can say x equals 2 except it's the server's data。

 So this is a bit of server data that's stored in the browser。 Those are called cookies。

And so the idea is is that you start with nothing in the cookie and then it comes in and request comes in。

 and then what happens is added on this request is like x equals 3。

 and then it stores that x equals 3 and then that comes out then the next request comes in and then it adds x equals 3 to that request。

Just like get data and post data， cookie data is added to requests， the difference is unlike。

Get data and post data。 Once that request is done， the dollar getting the dollar poster gone。

 the cookie data comes in on every request。 And so you could have like 1 thousand0 requests。

 and they will all have this cookie X set to 3。 And then if later we set that， you know， x equals 4。

It overwrites it， and then the next thousand requests will say x equals4。



![](img/2371360732cd30a82a78008456b5af87_7.png)

So it's just a way to say here's a key value bit of data and please send it back to me on every request。

Okay， so this is a really simple concept， and it solves the problem， as I mentioned。

Of when you have a web server that's talking literally to thousands of different people all with different identities。

 some have credit cards， there might be a shopping cart， we might be ordering stuff。

 and we have to mark the browsers and so that's what we're doing we're our mic in the browsers and we're picking a random number and we're going to give them a mark。



![](img/2371360732cd30a82a78008456b5af87_9.png)

![](img/2371360732cd30a82a78008456b5af87_10.png)

In the earliest of days， you 1990， the Re response cycle had no state and all browsers looked identical。

 but now when we're going to log in and we're going to have identity， so Facebook knows who you are。

 YouTube knows who you are， cookies are the way that we do all that stuff。



![](img/2371360732cd30a82a78008456b5af87_12.png)

So cookies are a piece of data that's chosen by the web server。

 the key and the value are set by the web server sent to the browser。

 stored in the browser and then sent back。Now cookies are not the same as sessions and they're not the same as being logged in。

 you will find that it's quite often that you visit a web page and they're going to set a cookie long before you log in。



![](img/2371360732cd30a82a78008456b5af87_14.png)

It just often on the very first request， it's going to set a cookie。 It's going to say。

 do I have this X cookie set， If not， I'll set it every time。 And so and again。

 I've drawn this picture a couple times。 you go in， it sets a cookie。

 It sends a page back and a cookie X equals2， and that cookie is X stored over here。

And then on all the requests， the cookie comes back in。

 That's what this picture is trying to show you。

![](img/2371360732cd30a82a78008456b5af87_16.png)

So they're marked as to which web addresses they come from。 And so you only get the cookies from。

 If you're a server， you only get the cookies back from the server that came from that server。

 They're kind of stove stovepid and isolated， siloed in the browser。

 so that you can't have one server looking at a different server's cookies。

 They also have an expiration date。 There's also a maximum size of them。

 but usually we don't put very much in and we don't run into the maximum。

 So you can have a cookie that lasts for a couple years。

 or we can have what's called a session cookie， which is a cookie that goes away as soon as the browser is closed。

 We tend to use session cookies for things like logging in and logging out。

 although some systems use long-term cookies to do log in and log out those tend to be like signed in more complex。



![](img/2371360732cd30a82a78008456b5af87_18.png)

So basically， PhP has really excellent support for cookies， just like when we have Dollar_re Get。

And dollar underscore score pose。These are the things where it's coming in。

 you got get data that ends up in dollar get。 you got post data that ends up in dollar post and。

Cookie data ends up in dollar underscore cookie。 And it's a superg， just like all those other things。

 And so that's pretty cool。 We can say what were the cookies that were sent to us。

 And they're all sitting there in dollar cookie。 And it's a key value array。

 Like what could be easier， so。😊。

![](img/2371360732cd30a82a78008456b5af87_20.png)

We can ask that again， we don't have to do any work。

 dollar cookie is defined and dollar cookie is defined if we have previously set a cookie。

And so what we're going to do here in this particular bit of code is we're going to check to see if there is a Zap key inside of cookie。

 We would have had to set it。 so it'll start by being false the first time through。 And if it is。

 we'll set Zap to be 42 with an expiration。 So that's an hour from right now。

 So that's time plus 3600 is an hour from right now。

 And then we'll print the contents of this cookie array。

 And then we'll click this over and over and over again。



![](img/2371360732cd30a82a78008456b5af87_22.png)

And so the first time that this happens is you'll notice that there is no cookie。

 We're going into a fresh browser。 We hit the cookie thing。 There is， oh， no cookie。

 but in the response。We see a set cookie Zap equals 42 with an expiration date and a away we go。

 And so this is coming back from the server to the browser。

 And so now the browser has to set this cookie。 And the browser has to send us back this cookie on every future request。

 So if you go into application cookies and here。 you can see this Zap。

 Now there's other cookies that you're going to find login cookies， et cetera。

 But this is storage in the browser。 This is in the browser's storage。 Basically。

 and the cookie has been set when it receive that it's set this。

 And so there's little database in your browser that is the cookie values。

 Then the next time you hit the statement。 It's going to send the cookie in。

 So the other thing I showed you is response headers。 This is the request header。 So the cookie says。

 oh， hey， I just took those two key value pairs。 I'm going to send them to you on this cookie。

And I got Zap equals 42。 And this could be hours later， Well， not hours later。

 because I only had an hour， but it could be minutes later。 And so it sends it in。

 So then PhP receives this。

![](img/2371360732cd30a82a78008456b5af87_24.png)

And it puts that into the dollar underscore cookie。

 So the first time we do a get request and that get request detects that there is nothing in dollar cookie So and sends back a set cookie。

 Zap equals 42。 So now the browser has Zap equals 42。 Then we do a get request。

 and then that shows up in this one。 and it does another get request and Zap equals 42 keeps coming in。

 So this is time passing。right， time passing。 So whatever we put， it stays there。

 And unlike dollar get and dollar post， dollar get and dollar post only last one thing。

 and they don't come in the next one， right， unless you put them out somehow and cause them to come out。



![](img/2371360732cd30a82a78008456b5af87_26.png)

So up next， we're going to talk about sessions， which is in addition to cookies。

 it's an in server data structure that is driven by cookies。



![](img/2371360732cd30a82a78008456b5af87_28.png)
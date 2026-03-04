# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p94 24_代码详解：Cookie与会话.zh_en -BV1Lr421A75d_p94-

Hello and welcome to Web applications for everybody。 Today。

 we're going through some of the session and cookie examples。

 So this is a very simple example called cookie do Ph。 P。 And basically。

 what it does is cookies are key value pairs that are stored in the browser。

 they're a bit of data that the servers can store on the browser。

 and we store it using the set cookie。 And we can say that what it's almost like a dictionary that or a associative array that lives on this on the。

😊。

![](img/76fe488013308c3fa4386d3837af72ca_1.png)

![](img/76fe488013308c3fa4386d3837af72ca_2.png)

On the browser， we say Zap equals 42， and then we give it an expiration time of now plus 3600 seconds。

 which is an hour from now。 But we're only going to do this if the cookie is not set。 Now。

 this turns into a header on the response。 And the first time we do this。

ll we'll notice that it's not set and then we'll set it。



![](img/76fe488013308c3fa4386d3837af72ca_4.png)

Okay， so you kind of set up。 So I got a fresh brand new browser。

 and I'm going go straight to that bit of。Straight to that bit of code。

 And so we can see on our developer console， hopefully， the cookie is going to be set。

 So here we come。And now I can take a look。 And so I look at the request。The request。

Yourquest is a get to that URL。And so what happens here is now because of this， this is a header。

 This is a response header that set the cookie。 And what that basically says now is that every other request from this point forward。

 That cookie has to come in。 Now， we can actually see these cookies under application cookies。 H TtP。

 Now， these other things have to do with automated things that are gathering data， whatever。

 but this is the Zap cookie。 Now， I can hit delete here and get rid of it。 of fact。

 I can delete all these guys， too。 I just get rid of them。 So I just got rid of those cookies。

 These cookies belong to me。 they're my browser。 In the old days， you could actually change these。

 I don't know how you change these as easily as you but you can change these。

 And so cookies are not something there're something the application sets on the browser。

 but they're not something that you'd think of as reliably owned by the browser。 now。

So theres a cookie sitting here。 and， and it set this cookie on that request response cycle。

 And that's because the current values of the cookies are copied into this very global superg dollar underscore cookie and PP。

 And because I was hitting it for the first time， there was nothing there。 So we said it。

 But from now on， if I ask for this again with a refresh。

 It is not going to give me the cookie because it's going to notice that I've sent it。



![](img/76fe488013308c3fa4386d3837af72ca_6.png)

![](img/76fe488013308c3fa4386d3837af72ca_7.png)

So if I take a look at this， the cookie array has Zap equals 42 and the way that was populated is in the request header。

The request header that the browser sent to the server。

 it sent a cookie header that says Zap equals 42。 And so what P H P does is it parss this Zap equals 42 and puts it in this variable dollar underscore cookie。

 a superglo like post， like get， et cetera。

![](img/76fe488013308c3fa4386d3837af72ca_9.png)

![](img/76fe488013308c3fa4386d3837af72ca_10.png)

And so because it saw that was already set。 It didn't feel the need to set it again， right？

 And so you'll notice there is no set cookie， at least not for zap。

 there's all this other crap that got set again， because I deleted it。

 I don't even know what those things are for， but whatever。 Now， if I go。

 and I take a look at my application。 And I look here。 this one got set again on that request。

 But if you hit refresh over and over and over again Now。

 every time every time there's going to be the cookie's going to be there。

 and it's not going to have to be set again。 Now， if I delete it。I delete it。And then I hit refresh。

And I take a look at the cookies。 It's back because this code detected that it wasn't there。

 but once I deleted， it doesn't get sent on the next request。



![](img/76fe488013308c3fa4386d3837af72ca_12.png)

Okay。😊，So that's cookies。 That's cookies。 Cookies are key value pairs that come in the browser now。



![](img/76fe488013308c3fa4386d3837af72ca_14.png)

![](img/76fe488013308c3fa4386d3837af72ca_15.png)

Let's talk about sessions。So sessions are not the same as cookies， although they make use of cookies。

 And so in PhP， if we want to use sessions， we sayage sessions start。And what happens。

 this is called cefund。phP。

![](img/76fe488013308c3fa4386d3837af72ca_17.png)

![](img/76fe488013308c3fa4386d3837af72ca_18.png)

I won't hit enter yet。Session start basically does a whole bunch of stuff。

Session start If there is no session cookie and there is no session cookie here。

 We'll see one in a second。 It actually picks a large random number for the session。 I D。

 then sends that out as a cookie session cookie， and then creates this superg called dollar underscore session。



![](img/76fe488013308c3fa4386d3837af72ca_20.png)

Now， the data installer underscore session is not stored in the browser。

 it's actually stored in a magic place in the server。



![](img/76fe488013308c3fa4386d3837af72ca_22.png)

In such a way that if you modify session in a request， it actually stores the data in a server。

 So once you've done session start， you have this magic variable that。Doesn't come from the client。

 Doesn't come from the browser。 It comes from the server on every request response cycle。

 so you can put data into it， and then you can take data out of it。

 And so it's pretty cool from one request to the next。



![](img/76fe488013308c3fa4386d3837af72ca_24.png)

Okay。And so let's go here to network to start。 and I I'm still in cookie dot Ph。 P。 Let's clear that。

 Now， when I hit enter here， it's going to retrieve Seshf do PhP。

 And it's going to notice that there is no session cookie and it's going to pick and create a session cookie。



![](img/76fe488013308c3fa4386d3837af72ca_26.png)

![](img/76fe488013308c3fa4386d3837af72ca_27.png)

Okay， so if I look here and I look at the response， you see a set cookie。

 The name of this cookie is PP C ID D。 That's actually something you can change in PhP。

 and this is the large random number that was picked by by it。Okay， and so the session is an array。

 and I set this array to be pizza equals0。 If there。

 so dollar session was created on this first request， but it's empty because it's the first request。

 And so pizza is not set。 And so it says session is empty。 Look at that session is empty。

 And then it sticks a0 in there。 And then down at the bottom， it prints it out。

 So we see the0 is in the session。 Now， this0 and pizza has not come back to the app come back to our browser。

 If we look at the cookies。 We have the session I D。

 which is kind of unlocks the session on the next request， but it doesn't store。



![](img/76fe488013308c3fa4386d3837af72ca_29.png)

![](img/76fe488013308c3fa4386d3837af72ca_30.png)

![](img/76fe488013308c3fa4386d3837af72ca_31.png)

Pizza equals zero， pizza equals zero stored magically in the server somewhere。



![](img/76fe488013308c3fa4386d3837af72ca_33.png)

Now。If I hit refresh， let's move this down a bit and move it down a bit。 if I hit refresh。



![](img/76fe488013308c3fa4386d3837af72ca_35.png)

You will， it'll come back in。 Session start。 We'll see a cookie this time。

 It'll send the cookie this time。 and it'll say， oh， it pizza is set because of this code。

 not because of the cookie， because it will be the same session because it will it will send this back again。

And。Session some pizza equals 0。 And then it's going to say， oh， but it is set。

 So this is going to be false。 So it's going to drop down here。

 and it's going to look at the current value of sessions of pizza， which is 0。 right now。

 if it's less than 3， we're going to retrieve it， add one to it and stick it back in the session and say added one and then print this stuff out。

 so。

![](img/76fe488013308c3fa4386d3837af72ca_37.png)

Pizza is now one。 It's still on the server。 The cookies haven't changed。 If I click it again。

 that code will run， it'll be2， right， and then it'll be3。 So now。



![](img/76fe488013308c3fa4386d3837af72ca_39.png)

Next time I click it S sub pizzaa， a server variable。

 this server variable that's going from request to request to request to request。

 The server variable is going to be greater than3。Oh wait， maybe I got to click it one more time。



![](img/76fe488013308c3fa4386d3837af72ca_41.png)

Click it one more time。 Oh， no。

![](img/76fe488013308c3fa4386d3837af72ca_43.png)

It's oh it it is three because it it's only less than three。 So because it was equal to 3。

 it ran this， which is session destroy， which really takes out all the key value pairs from the session in the server and session start。

 but you'll notice that our session I didn't change。

 But then when we print the dollar session variable it is now empty。

 And so what session destroy really does is empties out the dollar session。 The next time this runs。

 the session I is still not going to change because that's still in the cookie that's still being sent every request。



![](img/76fe488013308c3fa4386d3837af72ca_45.png)

![](img/76fe488013308c3fa4386d3837af72ca_46.png)

![](img/76fe488013308c3fa4386d3837af72ca_47.png)

![](img/76fe488013308c3fa4386d3837af72ca_48.png)

And it unlocks the session。 The session just on the server happens to be empty。

 but the next time we click it， it's going to say， oh， S's empty and set it to0。



![](img/76fe488013308c3fa4386d3837af72ca_50.png)

Sessions empty， set it to zero。So。Now， if you really， really， really want to， you can go to your。

Local host 8080 and go into your map。And go to PhP In and then look for the session。Session。

Save path。So that is the session save path。Now， I'm going to go show you what happens inside the session Sa path。

I'll open up a terminal and I'll change directory into the come back。Session save path。

So in this session there are actual files， let me just do this open dot， so you can see it here。

 but I can actually open these， I'll use old school VI to take a look at one of these things。

🎼And these have what's called a serialized versions of the basic stuff that is in a session Okay and so that is data you're not supposed to mess with that。

 but in just so that you can kind of see that these sessions variables are stored on disk somewhere and I don't particularly know why this one's not storing very well on disk。

 but that's a different problem， so there is sessions。



![](img/76fe488013308c3fa4386d3837af72ca_52.png)

And I hope you found this particular video on cookies and S useful。



![](img/76fe488013308c3fa4386d3837af72ca_54.png)
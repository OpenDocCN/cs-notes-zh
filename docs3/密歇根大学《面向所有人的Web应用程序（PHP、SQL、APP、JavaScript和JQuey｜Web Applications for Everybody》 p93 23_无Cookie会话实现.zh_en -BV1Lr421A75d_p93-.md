# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p93 23_无Cookie会话实现.zh_en -BV1Lr421A75d_p93-

![](img/5a157cb1e9db681f0958a5c7c33331ac_0.png)

![](img/5a157cb1e9db681f0958a5c7c33331ac_1.png)

So I just got done talking with you about how PhP uses cookies and sessions。

 but there's a really cool feature in PhP that has to do with sessions that don't require cookies now it's a kind of a narrow application probably 99% of the applications just use sessions。

 but the applications that I work on personally have to do with teaching and learning。

So you might have the same application in one course。

 you're a teacher in another course you're a student。

 and you might want to have both of those courses open up in two tabs at the same time。

 whereas there's one cookie for both of those tabs for one website。

 so if you want to have a different session in one tab than the other tab you can't use cookies for that and that's why I know and like sessions without cookies。



![](img/5a157cb1e9db681f0958a5c7c33331ac_3.png)

So basically， most applications， like I said，99% of them just use cookies and don't worry about it。

 just don't think about it。 But if you really need to function with an iframe or have one or one session active a away you go。

 And it's really cool for PhP。 So here's a little bit of code。

 and I'll sort of walk you through this。 how we can actually make sessions work without cookies。

 so here's some magic bits and you can go Google how you do this。

 But this basically says we're not going to use cookies for our sessions and we're going to transform the output automatically to make it as easy as possible for doing this。

 We do a session start the same as we ever do。 And there's some screen there。

 And this code is pretty much the same as before。 where we're going to have sessions of value。

 If it's empty。 we're going to set it to 0。 If it's below 3， we're going to add 1 to it。

 And then if it's above 3， we're going to destroy it and restart it。 So it's the same0，1，2，3，0。

1 to empty 0，1，2，3。

![](img/5a157cb1e9db681f0958a5c7c33331ac_5.png)

![](img/5a157cb1e9db681f0958a5c7c33331ac_6.png)

And so that's what it is。 and we got both a form that we're going to submit and aR that we're going to submit to click back and forth。

 So this is how this works。 So if we take a look at this。

 we want to make it so that we're passing this identifier。 we still end up with a session identifier。

 the place that it stored on disk as the exact same thing。

 but we need to pass this from one request to another and so we either have a form right here that we can submit or we can click on anchor tag but we have to somehow pass from this request to the next one。



![](img/5a157cb1e9db681f0958a5c7c33331ac_8.png)

And so if we take a look at the view source of this， we can see the two tricks that are happening。

 So the first thing that happens is we put out Hf equals noc PhP and then PhP addedQu mark session I。

 So if you click on this anchor tag， that's the click it's going to go to。

 And so the session I is being passed as a get parameter。

 So that's how you do it for anchor tags that are going back to the same application for the form。

 So we have a hidden field right here that is added by PhP。

 So if you'll notice we didn't put this out added by PhP which is the session I and it's that same I。

 same identifier that identifier that identifier I don't know why it's it's wrong there。

 but it's okay。That should be the same there。 So there's our session and a away we go。

 So if we hit a form， we send in post data and session start， whether it's a get or a post session。

Start。Looks for those things in a way you go， okay。

So then what happens is if we click the button in this case。

 I click the get request okay and we've added one in the session so it's now one and away you go and you can see the only kind of compromise that you have is on get request you see the session ID on the post request you don't because it's hidden but there's no way to hide it from a get request and so that's basically how you do cookie list。

Sessions and that's just a whosh by you can read up on how that works on the internet。

 There's session ideas and everything it's not automatically added。

 but basically Hres and forms they get added automatically we'll learn sometimes where we're talking to URLs that are not just HRs or forms but basically the URL we've revealed that and if you like copy and paste the URL you got other ways to have to protect the session because it's revealed to the user and they might bookmark and so if you're going to do these cookie list sessions。

 there's a few more things that you have to learn。

![](img/5a157cb1e9db681f0958a5c7c33331ac_10.png)

![](img/5a157cb1e9db681f0958a5c7c33331ac_11.png)

Okay。But for 99% of you we're going to use cookies to do sessions。

 Session and cookies work really well in PhP with a Doll earner score cookie， the set cookie call。

 the Doll earn score session， and the session start and the session destroy。

 make things happen really easily， and so up next we're going to learn a lot more about what we might do with these sessions in PhP。



![](img/5a157cb1e9db681f0958a5c7c33331ac_13.png)

![](img/5a157cb1e9db681f0958a5c7c33331ac_14.png)
# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p57 31_06_06_POST刷新模式.zh_en -BV1Kt421V7EE_p57-

So these forms are kind of complicated， there's a lot of little details， once we get them。

 then we'll be able to knock out forms and just do form after form after form。

So I call this little section post refresh oops， so remember this little page not so long ago where I'm like。

 look it's great， we did CSRF and we checked it and it worked great and we put the CSRF token in and it's all good。

Well， it turns out from the heights of success is the depths of failure。But it's not too bad。

 not too hard to fix it。 So you just got to fix it。

So the problem is if the browser sends a post request and it gets back at 200 in a page of HTML which is exactly what we just did。

 and then you hit the refresh button on your browser。

 the browser is going to resend the post request and if you go back I said post requests are things that change so for example。

 if you are transferring money from your account to someone else's and you hit the transfer button it's a post and a money gets transferred and then transfer successful and then if you hit refresh。



![](img/91a7868b9b453f758504b71c411f7fbd_1.png)

You're going to post it again and so the refresh basically reruns the entire previous transaction。

 It doesn't just grab the page， it sends the post data again。

 so if you transfer to $100 in one post and you hit refresh。

 you're going to transfer $100 again So what happens is is that because the browsers know that posts are potentially dangerous to the server。

The user will get a pop up， not from you， but from the browser to say，Hey。

Yeah this person who built this server application left you sitting on a post and you hit refresh and I'm going about post it again。

 So are you sure you really want to do that， And the problem is the user doesn't even know a post is barely knows what's a refresh。

 and it looks like a mess。 So the way to do this is you go to the page。 You type in 42。

You hit submitmit query and it'll say congratulations。And you look at it。

 and then you press the refresh button， the refresh button。



![](img/91a7868b9b453f758504b71c411f7fbd_3.png)

The reload button。And you press3 load button， and it says， to display this page。

 Firefox must send information that will repeat an action such as a search order confirmation that was performed earlier or a money transfer。

That is not a message from your application。 That is literally because your application was a little sloppy and Firefox is like。

 I'm really not sure if we should do this。 I'm going to ask the user。

 but it doesn't exactly know what to ask the user。 It doesn't know what you just did。 and so。

It's a yucky message。 And what we want to do as programmers is avoid this。

 We want all the message all the user experience coming from us。

 not having the browsers take over some of these things。

 And so it's just bad practice in general to send。

![](img/91a7868b9b453f758504b71c411f7fbd_5.png)

A 200 post to take a post request and then send a 200 with an HTML page back okay and so it's just ugly the browser asks。

 it's out of your control， it's ugly， it's bad usability so we can do a little bit of work to make this never happen so that's what we want to do here。

So the way we do this is through what we call post， redirect， refresh。



![](img/91a7868b9b453f758504b71c411f7fbd_7.png)

So up next， we're going to show how we're going to fix all this using a post， redirect， get， refresh。

 these titles keep getting longer and longer。
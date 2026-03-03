# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p55 29_06_04_表单与跨站请求伪造-CSRF.zh_en -BV1Kt421V7EE_p55-

Now that we've talked about forms a bit， I want to talk a little bit about security in forms。

 I want to talk about a security issue called cross site Re forgery or CSRF。

So the idea of a CSRf attack is that a rogue site。It has do with cookies and how cookies get sent to site so let's say you're logged into my site and a rogue site generates a page that's going to post and on every form you can post to a site other than the one it came from and so if I can get data。

That I want to send to the legitimate server， the O I can set up a post， and then if you。

 if I can convince you to hit the button。Then it will grab the cookie and send it to the legitimate server that you're already logged into and perhaps do something dangerous。

 and so the rogue server doesn't need to know the cookie。

 the rogue server just needs to convince you to click on a rogue form to send to the request server。

So the defense for CSRf is tos don't be confused with session it is going to use session。

 we're going to grab another large random number and we're going to call the CSRf token and we're going to stick that in the session and then what we do is every time we send a format that's coming from our server we add a little input hidden tag that has this CSRF token and then when the post comes in we check the CSRF token that's coming in in the post data and then we check it against the one and that's in the session and then rejects it if it doesn't match so here's a picture of how this works right so we'll have a legitimate server we're going to produce a page by the legitimate server and it's going to post back to this same server the action is the URL to send the post data to and we got some key value pairs in a submit button so you hit this submit button and it's going to come back to the server now one of the things that the browser is supposed to do is pull a cookie。



![](img/7f78ccfdd0e1d9a9ef33ee638e404a4e_1.png)

For that server and send it， so it sends it both a post and the data。

 but it also sends the session ID cookieie。And then what happens is that the Django gets its hands on it。

 it looks up the session ID pulls it in and notices that it's C7 and been logged as an instructor。

 and then I can actually change this grade and set the grade and it works。



![](img/7f78ccfdd0e1d9a9ef33ee638e404a4e_3.png)

Okay。Now here is what happens when you get to a CSRF attack。

 so somehow a page gets sent to the server。Right sent from a rogue server and it just has this form method equals post action equals DJ。

 it's not the action is it coming going to a different place and it puts sort of a new grade and then a submit So what happens is is this submit comes in。

And the browser dutifully appends the cookie to it， and it sends it。

 Now you had to be tricked into getting to this page and sometimes tricked into submitting the page。

 But once the post comes in， it has legit cookie in it。

 The cookie is used to look up the session and reassociiate it and we can check in the session that the user is indeed logged in。

 and we'll let the thing set the grade to 1。0。 So this would be a way if you could convince a logged in instructor to run a post form that you created。

 you could basically change your grades。 So that's how it works。 That's how a CSsrF attack。

 you have to be tricked twice first， but there's ways in jascript to make it So it's hardly noticeable that you get tricked。



![](img/7f78ccfdd0e1d9a9ef33ee638e404a4e_5.png)

So。If you do this with CRRF， the legit server basically adds another value， not the session ID。

 but another value in the session， which is a large randomly chosen number。

 and then when a page comes out， it's a legit page。

 and it uses a type hidden variable and puts the CSRF value in。

 now you hit the submit button and the CSRF is coming in as post data。

 the regular data the grade data is coming in and the browser dutifully appends the session。

And so then using the session cookie， it reassociates the session， says yep， you're C7。

 you're the instructor and the CSRF works， CSRF matches， so let's go ahead and let you set the grade。

 so we let them in。

![](img/7f78ccfdd0e1d9a9ef33ee638e404a4e_7.png)

With the attack blocked because the rogue server can generate a page。

 but it doesn't know what the CSRF is。So it you know could who knows what the CSRF is。

 so it generates it， maybe you can put a CSRF but it doesn't know it。

 so then the post happens and all the data gets gathered up and so it sends the CSRF but it's not the right CSRF。

 the session ID is sent in。And so the session is pulled in。

 we know it's user CSA we know it's instructor， but we're going to check to see if the CSRF matches and then it blows up and so then you just refuse the post probably log the user out and then log some kind of a security error so the idea is is by having this little CSRF number in the session。



![](img/7f78ccfdd0e1d9a9ef33ee638e404a4e_9.png)

We can then take care of that。So like most things， Djago comes out of the box with CSRF protection built in。

 just like the session， we've got CSRF middleware just dropped in and actually it works automatically you don't even have to ask for it to work once you have a session。

 it starts putting out CSRF things。

![](img/7f78ccfdd0e1d9a9ef33ee638e404a4e_11.png)

So up next we'll talk about now that we know the concept of CSRF。

 we'll talk about how we're going to use CSRF inside of forms to implement sort of CSRF protection。


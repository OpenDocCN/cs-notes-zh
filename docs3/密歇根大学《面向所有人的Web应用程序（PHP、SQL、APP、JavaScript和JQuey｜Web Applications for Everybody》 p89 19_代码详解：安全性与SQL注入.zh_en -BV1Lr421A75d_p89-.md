# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p89 19_代码详解：安全性与SQL注入.zh_en -BV1Lr421A75d_p89-

Hello and welcome to web applications for everybody。

 we're working through some of the code that we have， the PD code， and we're in the middle of it。

 and the code that I want to show you right now is code called login。phP。Okay and so here's login。pP。

 so let's walk you through what it's going to do。 Of course let's start with a data model So here's our people。

 we have passwords like Chuck 123， we should of course be hashing these passwords。

 but for now we're just doing plain text passwords and we're going to log people in and so we got so if it works I I can type in c7umish。

edduu and password to 123 perfectly fine password。C 7 at U meed out E to U password of 123。

 And it says， yea， you're logged in。 And if I say C 7 atummeed out e tou and I say password of not 1。

2，3， it says， no， you're not logged in。 Isn't this cool。 So let's see how we do this。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_1.png)

Log in 1。 PhP， so require 1。 this is the postcode and we'll just leave this for the moment we'll come back to that in a second。

And then I put out this form。 that is a just to take the。

It simply gets the email and password and then post it。

 so let's take a look at what we're doing here。We're pulling in the post data。

 We're pulling email and password out of the post data。 And look how fun we've done this。

 We've done this with a double quote， and we're using the variable substitution that double that you can and put email equal single quote E single quote for the email and password and we create the SQL。

 we run the query， we grab to see if there's one row， if there is one row， row is non falsealse。

 if there is a row， if there's no row row is false。

 and basically you're not logged in if the row is false and you are logged in if if you got one row and your login success。

 And so that's how it works。

![](img/ff91d4be316a8fa95b84c13b4ff866f6_3.png)

C7 at U edu and 1，2，3。Runs this select statement， right。

 and I can go run that select statement right here。Run the select statement。And I found a row。

 I got one row。 So that means that I'm logged in。 and that's exactly what we see。

 We see that we've got the row， the record set name maps to the string chuck。

 So we select name from users wear email。 And so log in success。 right。

 And if I do see7 atumish Eduu。 and I put in the wrong password， then it gets no row。

 because there is no record that matches these two things。 Okay， so that seems like a good idea。But。

It's not a good idea at all。And that's because there is this thing called SQL injection。

 And so this is the classic explanation of SQL injection。It's a XKCD。XKCD comic。

And mom is saying hearing the hi， this is your son's school， we're having some computer's trouble。

 and mom says， oh dear， did he break something and school says in a way， And then the school says。

 did you really name your son， Robert， single quote semiical and drop table student。

 dash dash question mark。And mom says， of course， we named him little Bobby Tables as his nickname。

And then the school says， while， we've lost this year's student records， I hope you're happy。

 And then mom says， and I hope you've learned to sanitize your database inputs。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_5.png)

And the problem is， just like with H T M， L， if we are taking data raw from the user and putting it into strings and then sending that to the database。

 a clever user can type an evil thing and take over。

 So let's try to become evil and break in to our thing。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_7.png)

![](img/ff91d4be316a8fa95b84c13b4ff866f6_8.png)

Now， what I need to do is I need to type into the password something that has a single quote in it。

 because then I can convince it that it's a single quote。 So here's。

 here's one that looks pretty good。 So I'll say Cs@umish E to U。

 And I'm going to say that the password is single quote。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_10.png)

Or P single quote or oops， or single quote1， single quote equals single quote 1。 Now， again。

 it's just like when I was doing H amenitiesities， I am going to put this string right there。

 and then SQL is going to interpret the single quotes that I just sent in。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_12.png)

![](img/ff91d4be316a8fa95b84c13b4ff866f6_13.png)

And so this is not the right password， but then when I submit it。Look at the select statement。

 The select statement is this is what I typed。 This is the unescapd data that came from the user， so。

I can。 I mean， I meant for it to be that this was the password， but that's not how S。

 Q L is going to read it。 It's going to say this or an S that's S， Q L 1 equals1。

 which is always true。 So there is a record that's going to come back。

 and we used in the code the existence of one record as login successful。 And so a away we go。

 So I just broke into this system by figuring out a cleverly constructed password。To get in。Okay。

That's bad。That's bad。 Now， I would want， I wish I could show you little drop table students。

 but they made it so that this query right here won't do semicollonons unless you force it to do semicollonons。

 So the more fun thing to do is to add a semicolon in there and do a second S Q L command。

 But they took away all the fun， So I can't even demonstrate that。

 So I can just demonstrate cheating and logging in without actually knowing the password。

 So how do we solve this。 Well， it's so easy。 the way we solve this。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_15.png)

![](img/ff91d4be316a8fa95b84c13b4ff866f6_16.png)

![](img/ff91d4be316a8fa95b84c13b4ff866f6_17.png)

![](img/ff91d4be316a8fa95b84c13b4ff866f6_18.png)

Is we use login 2 dot P， H P instead， and we use PO the way it was meant to be used。

And if I put in the single the P or1 equal oops， P or1 equals 1， it's not going to work。

And that's because the S， Q L it's actually sent has these placeholders in it。

 It doesn't have the actual text。 We actually pass in the text to this execute。

 And this execute carefully escapes as much as necessary。 All of these user entered values。

 It assumes anything that's being mapped in here might be dangerous。 So it's like。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_20.png)

Create a little place。 Don't let this data escape。 Cate a little place。 Don't let this data escape。

 If they put funky characters in there， do whatever。 It's kind of like Hinities。

 And before we had P and prepared statements， there was a series of my SQL escape things that made the code look really nasty。

 Now we just use PO。 And many languages have these things where they parameterize all their SQL。

 And so the the answer to this is just use P prepared statements。Don't use。🎼String concatenation。

 especially when user enter data is present。 Never。

 ever use string concatenation to make SQL when end user data is part of the query and end user data is inevitably going to be part of the query。

 So that's why PO is my best friend。 And I love PO。 And I can't say enough good things about PO。

 And so that is how we do avoid。

![](img/ff91d4be316a8fa95b84c13b4ff866f6_22.png)

SQL injection， okay， so I hope this little code walk through was helpful， cheers。



![](img/ff91d4be316a8fa95b84c13b4ff866f6_24.png)

![](img/ff91d4be316a8fa95b84c13b4ff866f6_25.png)
# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p85 15_安全问题：防范SQL注入.zh_en -BV1Lr421A75d_p85-

![](img/2334fcfc1cb0ce1244a668131d7c1655_0.png)

![](img/2334fcfc1cb0ce1244a668131d7c1655_1.png)

So now I want to talk a little bit about concerns about database compromising using what's called SQL injection。



![](img/2334fcfc1cb0ce1244a668131d7c1655_3.png)

And so let's go back to what we talked about a couple lectures back about how ill intention to people。

 figure out that your code is not protecting itself。

 and they construct something to put into a field。 Okay， And in that。

 if you don't sanitize your HTML， then you can sort of escape out from under things。

 and if you recall we fix that with a thing called HTML entities right， because you know this quote。

 because we didn't sanitize this user input that quote finished that And so we escaped into the background document which then rendered all of that stuff。

 And again， HTML entities is the solution to that。 So that's called HTML injection by using the user input and typing something really nasty。



![](img/2334fcfc1cb0ce1244a668131d7c1655_5.png)

![](img/2334fcfc1cb0ce1244a668131d7c1655_6.png)

![](img/2334fcfc1cb0ce1244a668131d7c1655_7.png)

SQL injection is the same for SQL and it has to do with the user typing something into a field that you just simply take and put into a query and if the user figures out that you've done that。

 then they just start doing things like putting in single quotes and or statements and and statements。

 etca， etca， etc。 and so the danger here is that if you don't sanitize your user input when you use it in SQL queries。

 you are leaving yourself wide open。And so let's say that you were going to make your life really simple and you just wanted to use the query rather than the prepare and the execute。

 So this is another way to say check a password right So we're gonna say if we got a post you know we've making a login form you know I password login right So we pressed it。

 And so we we grab the email out and we grab the password out and we just make some SQl。

 Now remember double quotes in PhP do dollar sign replacement。

 So the email goes in here and the password goes in there and look how simple that is。

 and now we don't have to do prepare execute， we just do a query and we'll just take whatever the email is whatever the password is。

 we put it in the query and then just run the query。 This is。Terrible， this is very。

 very terrible because this allows SQL injection because we didn't process the user data。

 we just concatenated the users typed in data right into an SQL statement and in a way SQL injection is worse than HTML injection。



![](img/2334fcfc1cb0ce1244a668131d7c1655_9.png)

And so。Here we go。 So let's just show how this works。

 So here's here's here's some accounts that we've created。So I'm going to type in， behave this time。

 and I'm going to piped in the wrong password。 And so if you look。

It puts in the email into here and the where clause and the password in there and runs this select。

 and if you run the select against this data， you're going to get back no row。

 and so you're going to correctly detect that login is not correct。Okay。

 so that's when you have a user who is nice。

![](img/2334fcfc1cb0ce1244a668131d7c1655_11.png)

And there is an XKCD comic， I'll let you read this comic for a second。

So the comic starts by a mom picking the phone up and the school says，H。

 this is your son's school we're having some computer's trouble， and then she goes，" oh dear。

 did he break something and the school says in a way。"，And the school says。

 did you really name your son， Robert， single quote， parenthesesis semicolon。

 drop table student semicolon dash dash question mark？And mom says， of course。

 little Bobby tableables is what we call them， and the school says， well。

 we've lost this year's student records and I hope you're happy， and mom says。

 and I hope you've learned to sanitize your database inputs。And of course， the thing is。

 is this is just like HTML injection in that ma carefully named her son to have a single quote。

 and so that's going there's going to be some single quote and then that single quotes ends it and then semicon used to mean well。

 it still does mean go to the next command and then drop table students。

 that's a legit SQL command drop table students and then another semicon and this is a comment。 Okay。

Now it turns out that using PD unless you force it to it doesn't respect the semicolon。

 So that's good because this is so shameful right So we can't quite do this the example I gave you that is doing this concatenation is the best I can do because P doesn't allow the semi I so would like it to be all have this。

 but this is so bad that they change the underlying libraries is not to allow semicolons step through。

 but we can still break in if you do it wrong Okay now this is kind of funny and you think well。

 someone really named that here at the University of Michigan。

 we have a thing called unique name right and my unique name is C。

 and I met a student whose unique name was null。 So null turns out to be an SQL keyword and so it's one of those things where you look in a language null is not a string when it's a keyword and so he would find all kinds of things where he would be registered for classes that he didn't mean so he actually。



![](img/2334fcfc1cb0ce1244a668131d7c1655_13.png)

![](img/2334fcfc1cb0ce1244a668131d7c1655_14.png)

Renamed himself null just out of a。Sick sense of humor knowing that it was going to cause him all kinds of misery。

 but。He was helping the university learn to sanitize their database input。

 So this is not as outrageous as it seems in this cartoon。 Okay， so remember the code， right。



![](img/2334fcfc1cb0ce1244a668131d7c1655_16.png)

The code basically takes the raw。Email and the raw typed in password and puts it in。

 And she'll notice that I've got a single quote。 So now what I do is I type in P or1 equals1 with all these quotes carefully constructed。

 right？ And so when this goes in， it just concatenates this stuff， This is bad。

Concatenateates this stuff。 Select name from users where email equals C sub。

 This is the user entered stuff right here。 That's simple enough。 and password equals。 Now。

 this is the SQL。This is the SQL。But this。Is the stuff I typed。

But once MysQl is executing is doesn't know what came from the user and what came from you as the developer。

 And so it doesn't know how this happened to be correct constructed。 It doesn it like， oh。

 some of that's from the user。 No， no， no， that's the database command that you typed and you sent to the database。

And so what it says is email a c7 atummieddu and password equals p or 1 equals1 well it turns out this is always true。

 so this is always true， so this is always true， so that whole thing is always true and so now you're logged in as C7@ Umiedduu log in success because that gives you back a row。

That's SQL injection。Because this is lazy Z。Lazy。I'll concatenate it all， that'll be great。



![](img/2334fcfc1cb0ce1244a668131d7c1655_18.png)

PPE PhP4 and three， and this was like the biggest problem that PhP had and it really contributed a lot to PhPs being a disrespected language。

And because people who didn't know much how to program would use this。 and they'd use this pattern。

 and then they would leave themselves so wide open。 Erasmus Leor。

 if you'd probably seen a video that I put up for the class。

 He came and he said the first thing he does at any campus。

 He walks in and starts typing these little single quote things at at things and tries to break into every campus server。

 It's like， why don't you guys clean this up。So。The bad news is。Before we had PDO。

 and this is one of the things I love about PDO is before we had PDO。

 there was this thing where you had to do the MySQL escape strings and then they had a version of PhP that oh。

 it was terrible， I anyone talk about it。

![](img/2334fcfc1cb0ce1244a668131d7c1655_20.png)

It was so sad。PDO is so beautiful。 That's why I love PO。

 It turns out as long as you're using prepared statements， SQL injection doesn't happen。

 So any user data has to be put in through these little。😊，Through these little placeholders。And。

The placeholders are careful when the execute runs。

 the placeholder execute is careful to do all necessary escaping。 Okay。

 and so you don't put quotes in。 you don't put anything in。 You just say。

 put this thing that came from the user and protect it。 So it's like having HTML entities。For HTML。

 except it's automatic。 It's all automatic。 And so this is why if you're taking data from the user。

 you want to do a prepare， execute step rather than a query step， as I showed you in that last thing。

 it's automatically escaped， automatically handled， automatically makes it so SQL injection。

 So as long as you're not concatenating it， but using prepared statements in placeholders。

 life is good。 and that's like why I like it。

![](img/2334fcfc1cb0ce1244a668131d7c1655_22.png)

Okay， so up next we're going to talk about like how exceptions get thrown and what kind of things go wrong and what are and what are not errors in database connections from PhP。



![](img/2334fcfc1cb0ce1244a668131d7c1655_24.png)
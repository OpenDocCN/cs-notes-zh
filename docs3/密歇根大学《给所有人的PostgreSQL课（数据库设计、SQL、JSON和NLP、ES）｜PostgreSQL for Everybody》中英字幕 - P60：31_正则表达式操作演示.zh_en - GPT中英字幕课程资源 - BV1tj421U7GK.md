# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P60：31_正则表达式操作演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another walkthrough of S QL。 We're going to play a little bit about with regular expressions。

 So I assume that you've watched the lecture on regular expressions。

 So I'm just going to sort of tell you each what it each one of these does。

 So I'm going to make an email table， which just some text in it。

 going insert some email addresses in it。

![](img/cb2f2797e7920d708b29abc2eb4ab3da_1.png)

![](img/cb2f2797e7920d708b29abc2eb4ab3da_2.png)

![](img/cb2f2797e7920d708b29abc2eb4ab3da_3.png)

Select star。He。Is my table。So there we go， so we have a few things that we can look at。

So let's take a look at some of these queries。So。So this t is a regular expression。

 It's kind of like like， but it's the regular expression one。

 So that the difference is is that this does not need this this basically is going to take this yish and move it across the entire sort of match it。

Moving across。 And so anything that has a Uish in it anywhere is going to match this one。

 you don't have to put wild cards at the beginning and end like you do want a light clause。

 So if I'm that's really saying， select where there is anywhere in the email address。

 there is a Uish email address。The carrot is the start。

 So that basically says select anything that starts with the letter C。So C7 Colleen， of course。

 do then select something the dollar sign is a metacharact that saysShow me the everything that ends with dollar sign。

So that has all the EduU ones， so there's Apple。com and Apple。com。

So the bracket is a single character that's a set。 So what this is saying is I want to see at the beginning of the line。

 some something that starts with G or N or T。 That's what the brackets are。 It's a。

 It's a set of possible characters。So there we go。The G or the N or the T is what we got。So。

Now we can look for。Any digit。 So you can inside brackets， you can have a range。 So 09 is a range。

 And again， it's still going to check every characters like， is this a number， Is this a number。

 Is this a number， And then it finds it， So they'll find the ones that have a number in them anywhere。

And it finds this one。If I have bracket 0 through 9， brackets 0 through 9 is my regular expression。

 that says two digits right next to each other。 but anywhere in the file。

 So that says this is Ted 79。 That was a two digit1。

 Here was before we did a one digit number So one one digit number anywhere in the email。

 So Glenn one matched。 but if I want a two digit number。A way I go Okay。

 so that's just sort of a review of some of the basics that we can do。Now。

 you can also take the email and run it through a regular expression。 So this is just a wear clause。

 right， But what we're doing is we're going to actually， instead of just showing the email address。

 we are going to pull things out of the email address。 And so what we're going I'll show。

 let's just show you this。 It's kind of cool。 And then。It's actually pulling the number out， right。

 Select Sub string email from quote 0 through 9 plus。 So here we go，0 through 9 is any digit。Plus。

 means one or more of them。 Go have one or more of them。

 And what's happening here is email is the whole email address。

 But what we're doing is with this from inside the parentheses。

 it's different than saying which table is。 that's this from from inside the parentheses says， look。

 apply this regular expression and extract from email。That fraction of this。

 that portion that matches 0 through 9 plus， so that gives us the 79 and it gives us the one。

This is an aware clause right where email matches this regular expression。

 and then you can also do it in the results of the select。

Now you can also use parentheses so what this is saying here。Is we are going to take。

The email and we're going to run it through a regular expression。

And now in this regular expression is dot plus。Which means any character one or more times。

 followed by an at sign。And then parentheesis means start extracting。And then。

Dot star means zero or more characters followed by stop extracting。

 followed by the end of the string。 So what that really is saying is that saying。

 go up to and start extracting after the at sign and go all the way to the end of the string。

So that's how we've got， you missed out EU， we just got all the email addresses， right？

The email is everything， but we were able to go up to the at sign， start extracting。

 and then end extracting at the end of the string and so we can get the email address that's pretty cool huh。

You can also just throw a distinct。 This is a perfect， like example of distinct。

 It's really just these rows， exact rows that you get without distinct。

 except that the duplicates are not removed。 So we go from six rows with two duplicates to four rows with no duplicates。

 And that's exactly what the select distinct does。 And thats that's really awesome。

 I just the select distinct is like， yep， just show me the unique ones。😊。



![](img/cb2f2797e7920d708b29abc2eb4ab3da_5.png)

![](img/cb2f2797e7920d708b29abc2eb4ab3da_6.png)

Just like in distinct， we can do a group by now this looks a little bit complex where we're seeing。

 but you'll just notice that the sub string email has to be repeated over and over and over again we're going to pull out the domain name that we're going to compound the domain names and we're going to do a group by the domain name。

 so that I wish there was a way to make that a shortcut。

 but there is not really an easy way to make that a shortcut but you will see here that what we're going to get is we are going to get。

The number of times this is going each of these domains is going to be used。 So remember that。

 you know in order a group by an account is kind of like a distinct except it's keeping track of the ones that it throws away so it threw away one u me。

 but it's like that means the count is two， so that's pretty cool。嗯。Okay。

 and you can put the substring in the wear clauses as well。So we can say， you know。

 select star from Em where the sub string email fromh bh bh blah blah， blah。

 this's a whole email from。Quote dot plus at parentheses dot star。

 that's basically saying in the where clause， we're going to do the substring extraction and then match that to U Mdu。

So there we go， and we can see the ID。Okay， so that is。Playing with。Regular expressions。

An email addresses。 Let's go and put。Put some play with tags a little bit。

 Ts is this notion that you have these pound sign strings。

And we're going to make a little table of tweets。Not too many tweets。

 we've got three little tweets with five little tags， so we can see our our tweets。

There's three little tweets in five tags。

![](img/cb2f2797e7920d708b29abc2eb4ab3da_8.png)

So we can， of course， use regular expressions that says you， find pound sign SQL anywhere in。

Tweet tilled Po sign SQL。So that' you're finding the tweet， that's really just a where clause， right。

 that's nothing different than what we did before。

![](img/cb2f2797e7920d708b29abc2eb4ab3da_10.png)

But then， inside the select。You basically can say， I would like to。S， take this tweet。

Column from the Twitter， to T W table and run this match。 And so it。It's a pound sign。

 this a regularg expression， a pound sign， followed by start of extraction。

Follow by and embraces A through Z， lowercase A through Z。Up 0 through 9 and underscore。 So that's。

 that's our legitimate letters。 Plus means we have to have one or more of those characters。

 And then we stop extracting。 So when we run out of which in in this case， it'll be the blank。

 we'll start here。 We'll go。 Gr Po Esql and the blank will stop us because blank is not in this set of characters that we are doing。

G means do it more than once。 And then you're going to see that this sort of。sortrt of。

Expands because some of these have more than one。 And so this redjex match。

Creates sort of some virtual rows。 So this， even though there's only three tweets。

 we get one sort of virtual row。

![](img/cb2f2797e7920d708b29abc2eb4ab3da_12.png)

Because Reja match sort of expands。

![](img/cb2f2797e7920d708b29abc2eb4ab3da_14.png)

And if we can use select Dis on that one as well， so that sort of takes our six tags and knocks are down to four tags because there are some bluelets。

 but we can also then hook back on here if we don't do the distinct。

 we can hook back on the ID of the row it came in and you can sort of see the mapping of which actual tweet so tweetwe1 has SQL and fun。

 tweetweet  two as SQL and UMSI and tweetwe 3 has UMSI and Python。



![](img/cb2f2797e7920d708b29abc2eb4ab3da_16.png)

So that gives you a little bit of regular expressions， regular expressions are themselves a study。

 and so you know you'll learn regular expressions probably as much from stack overflow as anything else。


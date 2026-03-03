# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P84：20_邮件归档系统演示（第一部分）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another walkthrough of some sample code in our Postgres class。

 So now we are playing with loading a email data。 this is probably the most complex bit of code that I'm going to use in this class it's a bunch of Python code does a lot of cleaning。

 It's dealing with some real data this data is actually from 2005 that I've got captured from mailing list from my open source Sai project and so mail is a weird format。

 that's a format called Mbox that the interest it's a simple format from space is the delimiter literally from the first column space is the delimiter and then there's a series of headers with from Col message ID all colon。

There's continuation lines and then there is a blank line and then there is the body of the message and I can get to these sort of in groups or at one at a time and I'm going to write a bit of code to sort of pull a whole series of these things into a database and then play some full text stuff with it。

So so let's take a look at the code here we are at。Pgfree。com/lectures/06pyython。

sql and we are on this email corpus one and again it's going to pull down from inbox。dorchuck。net。

sai。dl/sai。ve。

![](img/884dafbbae170b473d885c73da857f4b_1.png)

![](img/884dafbbae170b473d885c73da857f4b_2.png)

We're going to grab from Pg3。 co s code Gmaine。 py dateatecompat。 py and hidden。pyy。

 I hope by now you've got hidden。 py。And so the program is pretty self containedtained。

 make sure that when you start it you don't have a table named messages。

 so you shouldn't have a table named messages drop it if you are getting started and so but after that you just say Python G main do PY。

 and I'll go ahead and run it。

![](img/884dafbbae170b473d885c73da857f4b_4.png)

![](img/884dafbbae170b473d885c73da857f4b_5.png)

![](img/884dafbbae170b473d885c73da857f4b_6.png)

And it just asks how many， now this is a spider web crawlwler style thing and so it's asking me how many and I'll just say。

 go get me 100 messages and it just starts retrieving them。

And so it's just doing it it's showing you and it's pretty quick。 you'll notice。 Now。

 if I go in here and I say select count star from messages。There was 100。Let me get another 100。

Fooop， not 1 thousand，100。So you'll see that this count doesn't go up。 And that's because， again。

 I'm not committing。 I I'm pushing rows still 100， still 100。 Now it just went to 150。

 It's committing them 50 at a time， just like I did in similar examples。

 So this is running pretty well。 You're supposed to pull in about 300 messages。

 I' like I'll go to 200。 this is a very fast server。 It's highly cached。

 And so you can beat the heck out of this server。 A lot of Apis have rate limits。

 This particular one inbox Doctor Chuck do net has no rate limit because it uses a really cool technology called CloudClare。

Which is free infinitely scalable caching， so it's super fast and I use this in my Python for everybody class as well。

Okay， so that's running。And let's see we've got 250。 It'll run for a while。

 So let's take a look at the source code。So the main code is in Gma。pyy。

And it is a bit of complexity in here。 the biggest complexity of this is that I'm spending some time trying to make this code。

 clean the data up a little bit so that my work inside the database is less difficult And the problem with all this email stuff is that there's doing different servers are involved in it。

 there are slightly different ways like this from address。 you'll see in a second。

 sometimes the from address has like less than greater than in it sometimes it doesn't the format of the date is weird and the time zone and and all that stuff and sometimes this is connected together and there's different ways that they do dates and it comes through a Linux box or some other box or goes through Google and these headers are different。

 So one of the things I'm trying to do is kind of clean this data up so that when I put it in my database。

 I've got it kind of nice。 The other thing I want to do because I'm gonna to do full text stuff is I'm going to。

I'm going to pull the subject out， I'm going to split the headers and the body into different fields in my database。

 and so the headers are the part from the from up till the first blank line。

 I and if I'm doing like full text searches， I really don't want to be searching the headers。

 although the subject line is particularly interesting we might want to do searches on the subject line。

 so I'm pulling out the date。The scent date， the subject， the headers and the body。

 and that's what I'm pulling out and I'm using the Python program because it just is too hard to write SQL to do all this stuff。

 Some people might tell you to write a story procedure。

 but frankly you might as well just do this in particular because we can connect to the database we use the hidden trick。

 etc ceter。 there's these lines about ignore SSL certificate errors just do them long story that has to do with HDPS and expired certificates。

 you don't care。 you're talking to an API and nothing here is important。 So we're just doing that。



![](img/884dafbbae170b473d885c73da857f4b_8.png)

So if we take a look at what's going on here， this is a little different。

Then a classic crawling and then I know what the order of these things are。

 and I'm actually going to the primary key and the message number from the database is from it so it's like message three to。

Going from three to four， that's just retrieving one message。

That I know it and so I'm just going to just retrieve them in order。

 hopefully they don't blow up on me， but this is this one's more reliable and doesn't have eight limits and so it's a little easier to handle。

嗯。😊，And so what I'm going to do is I'm going to decide where we're going to pick up where we left off and let me show you how this code works。

 It's either going to start at message 0 and actually which is a message1 because I say start equal start plus1。

 but now I'm going to hit enter here in the running g main dot pi and it's going to go back to this shell and I'm going to start it back up again。

 this is a restartable process because the data is all in theres 400 rows sitting in the database。

 data is all there So I run Python G main dot py and it knows that we got start 401 So if I just say give me one message it'll retrieve one message and then I can ask。



![](img/884dafbbae170b473d885c73da857f4b_10.png)

It's 401 and so it doesn't restart now if I wanted to restart then I've got to manually drop the table。

 to drop the table's right here。

![](img/884dafbbae170b473d885c73da857f4b_12.png)

I don't have the drop table oh， you just say drop table messages and it would work， okay。



![](img/884dafbbae170b473d885c73da857f4b_14.png)

So let's go back to taking a look at this code。

![](img/884dafbbae170b473d885c73da857f4b_16.png)

So it's a while loop and it goes kind of it asks how many messages then it retrieves those messages and how many more you want to do and so but it's still working down you know。

 message 401， 402， 403。So as it starts， it skips any of messages that are in there。

 so if there's a message in there， we do a select。And at this point。

 I want to show you this thing called my us。

![](img/884dafbbae170b473d885c73da857f4b_18.png)

Get out of there and do my us。 So take a look at my u stop pi。 I just made some library code。

 And the reason was is that I have a few things like I want to query a row and fetch one。

 fetch the first record。 I it's a query like limit one query or something。 And I'm gonna do that。

 And sometimes I'll do like a count star。 And I actually want the value。

 like not just a row with a single item， a single row with a single item。

 but I'm just the zero with element of that row topple。 and I want it。

 So I'm just like these are common things I do over and over again。 So I put them in this file my us。

 And if I go up to the top of the file， I am port my us。



![](img/884dafbbae170b473d885c73da857f4b_20.png)

![](img/884dafbbae170b473d885c73da857f4b_21.png)

![](img/884dafbbae170b473d885c73da857f4b_22.png)

![](img/884dafbbae170b473d885c73da857f4b_23.png)

And then I can use that so this is just my us do query value is this is what I call when I know that I want a single value。

 this is just going to give me one row select ID for message where ID equals 12 or whatever and away we go and so this is just saves me typing about eight or nine lines of code and it returns none。

If， if it's not none， see that it is not none。 we're going to continue。

 So that as I skipping through rows。And then I create the URL by just concatenating and I get one message at a time。

 I could actually get multiple messages at a time， but then I need a loop inside the loop。

 and so I'm not just going to do that。And then I have the code here。I am going to。

 of course put in track set block， I'm going to use URL Lib giving myself a 30 second timeout。

 this is the comp this context equals CTX is a compensation for bad HTTPS certificates。

 which is some I could just go off on why that got messed up and security people are。

 then I read the document， check to see if I got a 200， which of course is the HP okay。

I specifically catch this with a control C so I can blow it up and get out and clean my mess up。

 So let let me go ahead and do that。 I'll do Python G main dot py and retrieve 1 messages and then hit control C。

 and I actually caught this abort。 And what I want to do when I'm aborting is I want to break out of my loop。

 And then I want to make sure that I commit all the records that I just got done doing and close。

 and you've seen other things where I didn't do this。 and I didn't blow blows up。

 and I wasn't in to try and accept。 and an it messed up。 The other exception。

 who knows what's wrong with this other exception。 I just am going to print the error message out。

 Now one thing I should sort of point out at this point is this G main dot py code。

 This took me probably two weeks to write and get right。

 And so all of this stuff you don't necessarily have to put all this stuff in。

 I kind of added all these things。 some of this tricept stuff。 I added it all。



![](img/884dafbbae170b473d885c73da857f4b_25.png)

As I realized you know， I have this problem and I have that problem and so one of these things is these programs evolve as you run them and you should write them in a way that let you do that so you'll notice that my thing is eminently restarttable you just drop the table and it starts itself back up and so because you're going to be restarting this so many times as you're debugging it and this code is pretty smooth at this point it's been run by probably 20。

000，30，000 students in Python for everybody。But the point is， is when you start。

 it's not necessarily this sophisticated。 And so don't feel like everything that you write has to have a bunch of tries and accepts。

 although when you're writing code， you can come back and take a look at this code and say， oh。

 that's kind of nice because this will always be available on Ppwafree do com slash code。

So even if you're not taking a class， you can see all this okay。

 so I retrieve the data and I print out the length and you'll notice that that's what's coming out here。

 which which URL I'm retrieving and how long it is 3686 characters。



![](img/884dafbbae170b473d885c73da857f4b_27.png)

And then and then I'm going to start parsing it， right， Okay。

 And so because I'm retrieving one line at a time， it's supposed to have a from space at the beginning of it。

 one one mail message at a time。And I have this thing about failing。 and sometimes it just fail。

 fail， fail， fail。 And so I had a little code that's smart about that。

So then what I do is I check to see if I got it from at the beginning。



![](img/884dafbbae170b473d885c73da857f4b_29.png)

And you'll notice that that from at the beginning is not necessarily the person that it's really from。

 there's a from colon header， which is different than from。Then I look for two new lines in a row。

 new line backslash n backslash n， and if I find it， then I break it into header and body。

 and again that's going to then be two columns in my database so that I can separately do stuff to the header and the body。

Else I kind of trigger a failure and print it out to debug it and again， once it works。

 but these little failure things are a good idea and you don't want it to go too far when it's failing。



![](img/884dafbbae170b473d885c73da857f4b_31.png)

And then I got to pull out the email address， and I use a regular expression looking for the from colon at the beginning of the line。

Followed by a list Anne。And then a bracket。And we check something here there。Yeah。

 only that was there。front I just took that space out。

So the from colon with brackets and the from colon without brackets。

 and that's what this code is doing。And if I find one without with brackets， I take the brackets out。

And the next thing that's a little bit difficult is the processing of the date。

So we go find the date header， so I look for a line that has date in it。That's right here。

 And then I pull out。All this stuff Friday， I want to get rid of the Friday。

 So that's what this dot star comma does。 And I want to skip a space。 and then I grab this stuff。

 Now， this is a weirdly formatted date。And so I had to build a separate function， parse mail date。

AndSo if you take a look at parse mail date。Pse mail date is trying to use a thing that's built into Python called parser。

 parse and if it works it's great， otherwise I roll my own date compatibility library。

And I just Googled something about what if the parse mail date doesn't exist。

 and then I could write my own， But I really wanted to use the one that was built in to convert everything to this ISil format and the Iil format is what then my insert statement is capable of doing。

 So so the date part。Is probably the most complex and this is it falls into the category of data cleaning right and so then I get a sent out date。

 then I go find the subject。And I look for a new line followed by the word they're so subject at the beginning of a line。

 and then I do extraction of everything up to the end of that line and I use I pull that out of the header data right so I pull the subject out of the header data and I strip it and I lowercase it。

 etc cea， et cetera， et cea。嗯。And then I just insert it all， insert into messages。

 I set the ID in this one which is kind of weird， and then every 50 messages I do a commit and every 100 messages I sleep so that I can hit control C and when the loop is all done。

 I do con dot commit。And again， I can run this。Over and over and over。And。

Pull messages out and of course I can watch。 So at this point I got 403， 403。 and again。

 it's cruising along。If I get control C now。I think。I think。I might not have got it。

 It might not have been in the right place。 And so let's see if the commit worked。Well。

 I got three of them there， so the commit were okay。



![](img/884dafbbae170b473d885c73da857f4b_33.png)

So that。Let me just pull 10 messages down。So that one worked and so what I'm going to do is I'm going to stop and come back and talk about what we're going to do when we start creating these indexes。



![](img/884dafbbae170b473d885c73da857f4b_35.png)
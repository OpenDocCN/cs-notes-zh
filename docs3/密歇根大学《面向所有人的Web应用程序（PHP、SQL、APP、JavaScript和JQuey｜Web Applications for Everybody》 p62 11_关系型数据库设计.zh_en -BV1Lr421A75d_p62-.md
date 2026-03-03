# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p62 11_关系型数据库设计.zh_en -BV1Lr421A75d_p62-

![](img/18a8ed329f7e1ed033736bd921036e32_0.png)

![](img/18a8ed329f7e1ed033736bd921036e32_1.png)

So welcome to our second major section of databases。

 previous lecture we learned about how to get work done in a single table。

 and now we're going to start connecting and that's where the word relational starts to matter。

And so these are the complex data models and relationships。

 and they're just techniques how we represent these things in a way that allows databases to do that sort of magical。

 high performance， efficient data gathering that we need to do and so this is where we're going to rubber meets the road and really learn how to build。

SoThis is where we switch from how to talk SQL to how to design databases。As I've said before。

 I learned databases kind of late in life and I took databases in grad school and that was in the 1980s and databases。

 relational databases weren't all that good。 And so I'm like databases they're dumb right and I would just write loops that read stuff but now I mean it was about 2000 when I had to work on a web application is my professional job for the first time in my life。

 and then they're like we're gonna to do some database design I'm like I don't know anything about that。

 So I went in a room with a bunch of folks and I picked it up really quick。

 I think it's really a beautiful thing I mean you draw this picture。

 you draw these lines and you're sort of like creating a network of data for your application And so the basics of database design or I think easy to understand and I think you'll have a good sense of them after the course of these next few lectures you can always learn more often people like why don't you teach me advanced databases and it's like。



![](img/18a8ed329f7e1ed033736bd921036e32_3.png)

![](img/18a8ed329f7e1ed033736bd921036e32_4.png)

The basics are easy to understand and the only time you really learn the advanced is if you face a problem and you ask someone or you look on stack Overflow。

 so it's a beautiful art form， you're going to actually be great shape to participate in database designs and you'll be able to design moderately complex databases and not make mistakes。

 but then there's always additional tricks that you can do。



![](img/18a8ed329f7e1ed033736bd921036e32_6.png)

So this is a picture of a data model that I've built。

 It's kind of similar to something we're going to talk about in this lecture。

 it's a learning management system and it's a learning tool that I actually use for the auto graders for this class。

 This is the data model of the software that supports the auto graders of this class and ultimately each of these little boxes is a table each of the little lines is so you know that's a table that's a table that's a table table table and then we've got some keys and we got little data bits in it。

 and then what's cool is we've got these lines and eventually we will understand what these little characters mean this means many this means one et cea。

 et cetera。 This is many the many table， this is the last part of the this is like two hours from now you'll see all this but ultimately what we're doing is we're creating a picture and it's a network and the relational bit and the thing that makes it super scorchingly fast is all the thinking that you do about these things about these lines and they'd seem like they're just nerdy things。

 but this is the magic of relational databases。And actually。

In a couple hours you will understand virtually everything on this table and that means sort of when you go to a job place and you see a picture like this on the wall because they can get kind of complex。

 this is another open source project that I work on called Sai it's an open source learning management system and this is just like about one quarter of its data model but what happens is when you're an application developer。

 you have to know the data model you have to change the data model and understanding the data model is the key to writing performanceant code because anybody can write crappy code。

 but in a web application if it's going to be successful at all。

 it's got to be relatively performant。So basically the idea is as you take a user interface of some application。

 you don't build the application from the data model。

 you build the data model from the application and then you kind of look at the application and say what kind of chunks of data do we have here and we're gonna put it all on one table because that slow So we' got to put it in a few tables So what parts best go into what table et。

 eta， et。 And so the idea of building a data model from a mockup and so let's pretend that we just started a company right and our idea for this company and this is a brilliant idea。

 I mean and we really should actually start a company on this。

 Our idea for this company is that we think that in the future。

 people will buy music based on tracks， not based on albums。

 an album for those of you don't never see an album is a set of musical tracks that you buy all at once for like $9 or we can sell a track for a dollar。

 wouldn't people like that So that's our innovation that we're gonna do So we've hired a graphic artist。



![](img/18a8ed329f7e1ed033736bd921036e32_8.png)

![](img/18a8ed329f7e1ed033736bd921036e32_9.png)

![](img/18a8ed329f7e1ed033736bd921036e32_10.png)

And the graphic artist has come back with this mockA says you know we're going to do really well if we build an application that can do this for people So this is the mockA Now the first thing we got to do as developers is not necessarily argue with the mockA。

 we can't say do you realize that this data model is not normalized properly and so you got to change the application because if you change it。



![](img/18a8ed329f7e1ed033736bd921036e32_12.png)

![](img/18a8ed329f7e1ed033736bd921036e32_13.png)

Assume this is what we want it to look like。 This， this is like。To a data modeling person。

 this is like， oh wow， look at all theooh， it's so scary。

 look at the vertical duplication of strings that that can't happen。

Our job is to build a data model that meets the user' needs。

 not tell the user that just because they have the word paranoid more than one time in a column on this user interface that they have violated the rules of normalization and they should come up with a different user interface。

 So the question is then how to go from this user interface。

 We got tracks length artist album genre rating accounts。 So we sort of have our columns。 Now。

 you could imagine that one way to do this would be make one table called the music table and put all these columns in。

 But what you would find is that。And you might have done this in your own life where you tried to put a spreadsheet of all your music tracks and youd find you' typing this in over and over and your brain is going like something's wrong here。

 And then it turns out you made a typo。 you're cutting and pasting and you made a typo。

 then you' got to fix it a bunch of places。 So the idea is in relational is this shouldn't be in one big table。

 This album information。 It needs to be It own table。 And we're only you put the word paranoid in1。

 cut into the chase。 And then what we're going to do is we're just going to take these tracks and put a mark in。

 So paranoid will be like album number 7 and then P。 And then we put like 7，7，7，7，7，7，7，7。



![](img/18a8ed329f7e1ed033736bd921036e32_15.png)

This will make a lot more sense later， okay， but that's the idea that we look at this as data model people and we don't tell you to change。

 we don't tell the designer to change their look and feel， we are going to compensate on our end。



![](img/18a8ed329f7e1ed033736bd921036e32_17.png)

So we look at all the columns because we do have to represent all the columns。

 we know they're going to be more than one table but we want to group them in a same way right and so we have to sort of figure out how what tables。

 what are the kind of core objects that are being represented here。

 it's not just one object for each column that's not good either and we have to kind of find a balance between the things that belong together and the things that belong separate and need to be linked back and forth and once we found that balance is where we get that sort of maximum efficiency。

So you can pause， you're going to get cup coffee because we are going to sit down in this conference room on a whiteboard and we're going to figure out what the data model of this thing is。

 and we're going to debate。 we're going to figure it out。

 So these are the columns that we've got to make。 So the first。

Conversation that we have to have usually is。What's the first table。

Because we're going to put this in multiple tables。 there's going to be more than one。 We know that。

 So in building a data model， you often ask what is the first table and。



![](img/18a8ed329f7e1ed033736bd921036e32_19.png)

Usually you think about as like what is the core purpose of this application？

You might decide that if we're making Twitter tweets might be the core thing if you're making a learning management system。

 courses might be the core thing。 if you're making a email system users might be the core thing。

 So now we have to debate on our little thing What is the core thing because users is not our core thing because we're building a little tool that everyone has separately and then after we build this we're going to invent a phone that has like you can touch the screen and stuff it's going to be big we're going to do really fine here。

But it's one user， so the users each person has its own phone and we're writing an application。

 so users is not our core thing。 we don't have columnnamed users so don't a column name email so we can argue。

 but if you look at this， I'm just going to say that fundamental thing does what is the aspect of every row and that is I think it's kind of a track that track is the core thing。

 so let's say our first table is track。

![](img/18a8ed329f7e1ed033736bd921036e32_21.png)

Okay。And now what we're going to do is we're going to look at all of these things and we're going to say which of these things are just like an aspect of every track that's different for every track and which of these things are the same across multiple tracks。

 So that's the idea。 and it really comes down to vertical duplication。

So vertical I mean that's the clue， if you see something vertically duplicated， that's a string。

 it's a problem。Vertical duplication with numbers turns out to be okay。 So numbers are easy。

 So here we have the length。 Let's just go with this。 We go with the length。 So we got the track。

 We got to take the title because that's different。 So we'll take the title。Title goes over here。

So we got that figured out。 The length。 The length is just a number。

 The fact that two things are four minutes。 numbersumbers are cheap and easy to store。

 So we don't worry about the fact that something is 300 seconds。

 and another thing is also 30 seconds。 So we're going to put that over here。

 We're going make this be the length is fine。 This， Oh oh， don't do that。 So length is taken care of。

 but this has vertical duplication。 So we're not going to do that。 This has vertical duplication。

 We're going to put that somewhere else。 This has vertical duplication。

 we're going to put that somewhere else。 So this rating this is really like a 0 through 5 number。

 So that's good。 So we're going to put rating over here。

So we've done that and this is the number of times we played and this is the count。

So we've kind of made our first table。 Okay， you've got this taken care of this taken care of。

This taken care of and this taken care of。So we got track。We got the title。We've got the length。

We've got the rating。An account。That's our first table。And we got this checked off。

 we got that checked off， we got that checked off and that checked off。

So then we're not looking at these ones that have vertical duplication and that's where you basically are going to make another table。

 So let's kind of figure out， you know what's going on here and let's make a table for albums。

So they're every album and we're going to have a title for each album。

And then every track is connected to an album。So we're going to put a word belongs to here。

So this is saying that every track belongs to an album。

 so now we've got that taken care of now actually that's not an album， sorry。This is the album。

This is the artist。So now what we're going to say is， well， okay。

 so every track belongs to an album and then every album belongs to an artist。

 so we're going to make up artist table here。Like ACDCs the artist。

And we're going to have the artist name。Like AC DC， And then we're going to say every album belongs。

To an artist。 So albums belong to artists。 tracks belong to albums。 Als belong to artists。 not。

 We can argue you we're probably going like， it's not quite like that。 And you're probably。

 we're gonna have to simplify this。 But so to， to do the data model。 So we've got this taken care of。

 We got that taken care of。 And the only thing we got left to taken care of is the genre。



![](img/18a8ed329f7e1ed033736bd921036e32_23.png)

![](img/18a8ed329f7e1ed033736bd921036e32_24.png)

Now the question is， where do we want to connect the genre， right， do we want to connect the genre。

 does an artist belong to a genre， does an album belong to a genre or does a track belong to a genre？

this is one of the things you do in data modeling。 and of course， this one is pretty simple。

 but this is the idea， but it turns out that wherever we connect genre is going to make a difference in our application。

 Okay， it's going to make a difference in our application because if we connect genre to an artist。

We do it here。Then that means that every ACDC thing has got to be rock。

Is did A DC ever do a Christmas album？ Has D C ever do folk ands like， well， that。

 that might be a little limiting if we do that。 So we're not going to put that there。

 We're not going to do that。 Well， how about an album， right， So you know。

 as who made who we want to do it here？ Is this where we want to put it。

And so that would mean that every track on the who made Who album would have to be rock and were like。

 that's closer。 but what if， you know， ACDC did the greatest hits and some albums were folk and some albums were rock。

And's like， yeah， that's no。 Okay。 so that's a bad idea because we want flexibility。

 We want to make it then。 So the answer is is we're going to put genre right here。

And we're going to make every album has a genre。 Now we got it。Okay。Oh， so there's our picture。

Four tables。1， two， three relationships。Whoa， what a mess。What a mess。Oh， look how beautiful that is。

 See， I have instant beautification right And so this is what we achieve。

 Now we don't worry too much about nerdy terminology。

 we're just trying to break the columns into things that belong together and establish sort of some kind of a meaningful human understandable relationship with them。

 and we're going to quickly turn this into sort of code， but now it's not code。

 This is sort of a philosophical concept and and a way we go。 And so up next。

 we're going to talk about how to map this picture that we just drew into a database conventions on columns and database features that let that all fit together。



![](img/18a8ed329f7e1ed033736bd921036e32_26.png)

![](img/18a8ed329f7e1ed033736bd921036e32_27.png)
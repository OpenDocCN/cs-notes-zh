# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p68 17_多对多关系.zh_en -BV1Lr421A75d_p68-

![](img/5b65dc00c48811de9adb46ebbf2ff89b_0.png)

![](img/5b65dc00c48811de9adb46ebbf2ff89b_1.png)

Okay， so everything we've been talking about up till now is what's a one to many relationship。

 But there's other kinds of shapes of relationships between tables and the biggest new one that we haven't talked about is what we call many to many relationships。

 And so this is my data model for the software that runs the autograder called the Suy software。

 and one of the more common situations is the course to user mapping。

 And so the problem is is that you can have many users and you can have many courses and many users can be a multi member of many courses and many courses can have many users。

 And so the notion of one album belonging to an artist And it turns out that album artists really should be many to many。

 So album and artist really should be many to many。 but。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_3.png)

The idea is， is we have to have a relationship。 And so what we can't do is we can't say there's users。

To courses。We can't have the many on this side and the one on that side。

 and we can't go users to courses and have the。The many on one side。

 the many here and the one on that side。 You can't do that。

 The relationship is truly between users and courses is many to many。

 So what you end up having to do is you actually make a table table in the middle， right？

 And so we'll not talk about this。So everything we've done so far is many to one。

 and that just means that you can have lots of rows。That go that are like 7，7，7，7 in the track。

 and then there's one，7 over here。So 17， so lots of foreign key， lots of rows of the foreign key。

 you can have vertical duplications of foreign key， but you can't also then have this。And also。

 if you really know music， a track can be on more than one album we simplified that for the previous lecture。

So the way we did it was a many to one okay but sometimes there are things that are naturally。

 many to one， but sometimes there are things that are actually many to many， so lots of authors。

 a book can have multiple authors and an author can write multiple books。

 and so we really just have to draw the picture like this。

 This is crowfoot diagram that stands for many， many。 it's many to many。

 and we have to the logical diagram。We'll just say it's many to many。 It just is。 okay。

 Let's not argue about it。 You can't do it any other way。 But then we have to turn it into tables。

 just like we had to add columns for foreign keys。 Well now we， instead of just adding columns。

 we have to add a whole table。 you call a junction table， a many to many table， a connector table。

 a relationship table， all kinds of things。 And so what we do then。

 is we break this many to many relationship into two， one to manys。 So this is many to one。

 This is many to one， one on this end， one on that end， then there's many。

 And then we can put lots of author book combinations inside here。

 And it's almost easier to take a look this in a practical example， right。

 And so if we think of accounts and users， and we have a many demand relationship between people in courses。

 and the courses that they're in， et cetera， which is really a roster is a combination of。You know。

 might call this thing a roster in the middle。And that is the mapping of what people are in what courses。

 So again， we're going to break this in the middle and make a little table in the middle and put the menus back and forth。

 right So this is how you do it。 So what you do is you create a table。 And so this the first table。

 every table we've created till now has a primary key right because we want to get it that row。

 These connector tables or join tables or junction tables， they tend not to have a primary key。

 And we'll see in a second how we create sort of a metaprimary key。

 which is that has a uniqueness constraint on it， that is the combination。

 So you can only have the user， an account course combination once。

 But one account can have many courses。 So the uniqueness is the combination of the two numbers。

 not the number itself。 So the primary key in a sense， is like a meta primarymary key。

 which is those two things connected together。And so we end up with a foreign key。

 a foreign key pointing to a primary key primary key。 These two tables are just totally normal。 Now。

 the interesting thing is you sometimes actually do model some data in here。

 And in a course situation， you can also model the role。

 whether they're a teacher or a student because。They're not。

 it's not like you're a teacher forever or that you know whatever you can't model the fact that you're a teacher and say everything you do because sometimes you're in a class that you're a teacher and sometimes you're a class that's a student。

 And so the fact that your're a teacher student gets modeled at the connection right so we have this connection。

 It's many to many connection but we kind of have this role that's modeled at the connection point between these two things And so that's an aspect。

 you don't always have to have data in the connector table， but it's also okay。

 And sometimes the data in the connector table is the only way to put it。

 So another thing you might put in here is like grade or something。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_5.png)

![](img/5b65dc00c48811de9adb46ebbf2ff89b_6.png)

Because you can't say you get one grade because you're in many classes。

 so you might have a final grade in lots of classes。

 and so it's what grade did you get in the class that you're in？

So there is data to model sort of here in the middle at times in the middle of the connection。

 so in a logical diagram， we don't really draw this picture， but there is data that lives there。

So the tables that we're going to create are pretty straightforward we' start with the outside ones。

 we've got an account table by now this should be familiar we have you know a logical key。

 we're going to put a niness constraint on it， the name and then primary key is a count ID that's just telling inside here the same for courses we've got a primary key auto increment。

 yada yada copy paste， copy paste， do that stuff all over again Okay so those two are those two are just like we've been doing the fun one is this next one。

Okay， and so in this one， we're building this member table， which is the thing。

 And so you'll notice there is no primary key。 There's no auto increment right。

 there's no auto increment here。 We don't have that。 So what we have is we have two foreign keys。

 We have two arrows that start in this table。 So we have two foreign keys。

 So account I and course I and then roll is this little bit of data that we're going model right there。

 There could be a couple of other things here。 If we're going to do this。

 and then we have two constraints。 And what all the constraints really you're doing is capturing these two arrows so that says that this account I inside this thing actually points to a row over here in the account table with a primary key of account ID and this course I that's in my table points to a corresponding row in course indexed by course I and we're going to do an update cascade on delete cascade。

 we talked about that before。 And so that's most of this。 but here is the fun part。

 Look at this primary key right in all the other ones。We had a primary key。

And we indicated that was the primary key。 Now， we don't have a single primary key。

 We have a combination primary key or a concatenated primary key。 And so we just give it two things。

 And what this says is the combination。Is unique。Not account ID is not unique。 Cose I is not unique。

 but the combination of any pair of account ID course ID is unique。

 And so we kind of have a primary key， but it's both these numbers。 Now， the thing is。

 is it sets up an index to look up the combination of the numbers really fast。

 So this actually drives an index。And so looking things up as long as you know both numbers is really fast。

 and it turns out given that you're kind of connecting with joins between all these courses。

 you know what those numbers are， so can look these things up really fast， super， fast， fast， fast。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_8.png)

Numbers， not strings。 sorry， I'm just， there's a little ad that pops up everywhere and I'm one on my head like don't use strings。

 don't use strings， just use numbers。

![](img/5b65dc00c48811de9adb46ebbf2ff89b_10.png)

Okay， the inserts now kind of feel pretty natural because we're used to these are the leaf tables。

 so we're going to put， you know， some folks in， right？Jane。

 Ed and Sue and Jane's email and then we are establishing because of that those have auto increment primary keys。

 so we're establishing the key for the internal key for each account。

 then we're going to do the same thing for courses yada yada yada and then we are going to come up with a primary keys。

 and then we have to write those down on our little piece of paper right because now we have to model at the connection。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_12.png)

Okay， and so now we're going to connect these things in。

 and so we're going to put in little bits of information。

 We're going to insert into the member table。 We got two foreign keys。

 which effectively are the primary key， but they're not auto increment is just the primary key。

 So account I course I enroll。 So that means that account one。Jain。Is in course1。As the instructor。

And account2， Ed is in course one as a student， and Sue is in course one as a student and。

Jane is in course 2 as a student， and Ed is in course，2 as a teacher， and。

Ed is in course three as a teacher， and Sue is in course three as a student。

So what we're doing is we're making。These things are like in here and we are putting connections where appropriate。

You know， and there's there it doesn't have to just be one connection Okay。

 And so we know all we have to know all these numbers by knowing these numbers and then knowing how to connect them。

 But this is really just modeled data。 That's the role that's there。

 So we're going to insert those just that's just drawing little lines。

 That's how we draw lines inside of databases。

![](img/5b65dc00c48811de9adb46ebbf2ff89b_14.png)

![](img/5b65dc00c48811de9adb46ebbf2ff89b_15.png)

And so if we're going to join this back together， we're going to want to produce a bit of output。

 you know that Ed is Ed is in PhP as a teacher。 Sue is in PhP as a student。

 Jane is in Python as a teacher at so how to produce that。

 Well you write a join statement right youd write a join and I think of this as China to joining through right we join through the membership table So we're kind of taking from two sides and we merge all these things together and we pull this。

 we pull this all in Okay so we're going to select the account name。

 the member role and the course title that's going to get us all this stuff and then we're going to join from the account joined with a member join with the course that's creating the super metata row that's kind of this big member here is in there Member is going contribute role basically and the on clauseuse。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_17.png)

Three tables， two relationships， arrow， arrow， on clause， member count ID equals the account。

 I count ID， and the member course ID equals course course ID Again。

 you should be able to write these in your sleep if you've been naming your things correctly Now I got an order by here that' basically says I'd like this to go in ascending order of course title。

Follow by descending order of member role and then followed by within a role the So in this case So this is the most important sort。

 this is the second most important sort。 And then when these two things match。

 then Ed and Sue will sort that way。 And so now we can sort of get a course roster list。

 who's the teacher， who's the student in all of our courses， by joining all those things together。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_19.png)

And again。What I just showed you is pretty much how we do it in real production systems。

 Here's a user table。Here is a course table context table， here is a foreign key。Context ID， user ID。

 Here's some information role that's actually modeled right there and look。

It knows about the fact that this is a many to a one。 And this was in a many to a one。

 which means that we effectively have created a many。To many。

 except that we use this junction table to achieve the many to many between users and courses。

 This is why I say once you kind of know the stuff that's。In here， in this， in this modeling。

 you can kind of build professional grade。To， so the first。100020000 users of an application。

 You can build a professional grade data model。 There will be things you will learn。 I mean。

 this is not the end of your learning。 There will be other things that you will learn。

 but you actually。If you can see this， you actually know a whole lot。

And I just need to emphasize that， yes， you could store this in a spreadsheet。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_21.png)

But speed is the key。 and in an online system， you can't pretend that the date is going to be small。

 You've got to model it right。 It's so much better to just model it right from the beginning。

 get good at what we're learning in these classes。 And then if you happen to scale。

 you're ready for it。It might seem like a tradeoff。 you might like oh boy。

 there's a lot of work there， but the answer is your application simply dies。

 I mean it doesn't just slow down a little bit。 it dies。 it doesn't work at all。

 there comes a point where your demand causes it to just die and you just can't throw more resources at it and so this is where startups you all hear about them oh。

 we wrote this cool thing and oh， we had to throw it all away and rewrite it and that's because they didn't think about their data model early enough。



![](img/5b65dc00c48811de9adb46ebbf2ff89b_23.png)

![](img/5b65dc00c48811de9adb46ebbf2ff89b_24.png)

![](img/5b65dc00c48811de9adb46ebbf2ff89b_25.png)

So that's end of a whole bunch of lectures talking about database databases allow us to scale to large amounts of data and pull those things in very speedy。

 The key is one copy of string data elements don't allow that vertical duplication that's called database normalization。

 it is a science of its own， We know enough of it to be dangerous。

The key is is that storage is smaller and the amount that scanned is smaller。

 and so that's really cool and。

![](img/5b65dc00c48811de9adb46ebbf2ff89b_27.png)

It is an art form， and literally。You can learn the basics， and they're beautiful。

 and you can actually be very competent， but you will learn forever。

 I love sitting down with somebody smarter than me about databases and say， what about this。

 What about that。😊，And even some of the rules。Of database normalization， Sometimes you apply them。

 and then sometimes you got across the streams and like， oh，8 a sec。 So it's。

 it's there's a lot of learning。 The fun thing is to learn the basics。 And then later。

 you can learn the exceptions， cheers。😊。

![](img/5b65dc00c48811de9adb46ebbf2ff89b_29.png)
# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p33 33_06_04_课程与会员的多对多数据模型.zh_en -BV1rNibBuEwD_p33-

So now I want to show you another example of many to many from an application that's near and dear to my heart and that's the autograder that I use for most of my online classes。

 So one of the things the autograder has to know is like who is in what course so that we can track grades based on people in courses。

 and so this is the data model and it's a little bit different syntax you sort of see one to many。

 it's used this what's called crowsfe and you see this little crowfoot and that's like a many when it sort of spreads out and then you sort of have this one and there's various little ways in one or more or zero or more and so there's little that's called a crowsfoot diagram。

 but these diagrams ultimately you're capturing the same thing whether these relationships or many to many or one to many and what the cardinality of each end of the relationship is and this is showing a person table a course table and a membership table and this is a very common thing that we have to solve an educational systems。



![](img/16efea47d2ec2815fcf84bcc32918293_1.png)

![](img/16efea47d2ec2815fcf84bcc32918293_2.png)

![](img/16efea47d2ec2815fcf84bcc32918293_3.png)

And it's a little bit more sophisticated than the previous one。

 which I thought was beautifully elegant and simple， but I want to show you this one as well。

And so what we have here is basically people are in courses。



![](img/16efea47d2ec2815fcf84bcc32918293_5.png)

Right a person can be in many courses and of course can have many people。

 so it's a many to many relationship， we create a through table we'll call it a member table。

 we end up just like before with two one to manys pointing out or many to ones pointing outwards so we have a person ID and a course ID in the member table。

 all three of these tables have primary keys of ID ID and ID and then we put the little tiny sort of virtual set in here so that at a person you can just look at a virtual set of their courses and in of course you can say who are the members of this course。

Now we're going to do one more thing that's a little bit different here。

 and that is often the simplest of through tables is literally an ID。And two foreign keys。

AndAs a matter of fact， some people， Django doesn't like doing this。

 but some people don't even include the ID field and they just make the combination of the two foreign keys as a unique ID and if you're doing databases directly。

 you can actually do that。But here's a thing that you can also do。

 so if you think about in a teaching and learning situation， people aren't just members of courses。

 they are members of courses and they have a role and is that role as a learner。

 a teaching assistant or an instructor or perhaps they're the departmental administrator， right。

 and that that is an attribute of the connection， right。



![](img/16efea47d2ec2815fcf84bcc32918293_7.png)

The connection between a person and a course。Is the membership， and oh， by the way。

 they're not just a member， they're a member with some metadata。

And so sometimes we add data to the through table and it's actually quite useful。

 and it's really the only place to model this kind of data because。

Somebody might be in a course as a teacher and they might be in a different course as a student。

 so you can't just say this person is always a teacher or they're always a student。

 you can't say that it depends on the context and so that's why at the connection between a particular person and a particular course。

 we actually model the role that they have in that course。



![](img/16efea47d2ec2815fcf84bcc32918293_9.png)

So here we go， so we're going to have a person in a course。

And we're going to have a through table of membership。

And so we're going to send these things back and forth to each other。



![](img/16efea47d2ec2815fcf84bcc32918293_11.png)

And this membership is the tricky one。 And so we have a foreign key over to person and a foreign key over to course。

 and we're going to model some information。 We're going to model a created date at and this is a datetime field。

 this is another feature that basically says let's make a created underscore at and De Django。

 I'm not even going to set this value， please， when I create this a new record here。

 populate this the current date and time and if I make a change to it， change the updated at。

 and this's a common pattern in lots of tables to put these two two lines in。

 and and it's so common that we often call them the same field。

 So you you'll look in somebody's django model and you'll see created at and you'll see updated at。

 And so that's another thing we're modeling at the connection。



![](img/16efea47d2ec2815fcf84bcc32918293_13.png)

In the through table。And so。The other thing we're going to do is have the role。Now。

 the example that you use in local library， they make this role， I think， a string。

 which makes me kind of like feel bad because I don't like vertical replication of string。

 even if they're sort of from a fixed vocabulary。

![](img/16efea47d2ec2815fcf84bcc32918293_15.png)

So what we're going to do here is we're going to do something where we're going to create。

A set of integers and associate those integers with meaning and use them in the amin interface。

 et cetera。 And so what I'm going to do here is these learner， IA， GSI。

 instructor and admin are just integer numbers。And then I'm going to say。

 I'm going to make this little couple of tuples。Or a list of tuples as it were and you know the learner integer maps to the string learner so we can show that in the user interface。

 This here is a lot of UI stuff。 So in the admin UI。

This whole member choices thing affects the ad menui。When this is all said and done。

 we basically say the role is an integer field and I like that because it's short and I love integers。

 how many times have you heard me say I love integers， integers are short and efficient。

 and instead of asing any number， it really is the choices are pulled from this thing。

 which is these possible numbers， which is 1，1，000，2000， 5，000 or 10，000。

 and the default value is learner， which means it's a one。So this is a nice， this is basically not。

 you could make an integer field and we could code in our Python code these numbers and these strings。

 but there's a lot of value in using the administrator interface now and having these values known inside the data model rather than just coding them throughout all the Python code that we write。

So when this is all said and done， what we have is two foreign keys。

 you know two outbound foreign keys like you would expect。

 a created and an updated app that's totally maintained by Django for us and then modeled at the connection a role like are you a teacher。

 are you a student okay and so that's a little more sophisticated kind of many to many model and we can talk to this？



![](img/16efea47d2ec2815fcf84bcc32918293_17.png)

In the。Jengo shellll， Python 3， many managed Py shell。

 you know we import the models from the application models that this is really reading the models。

pyy file from the many folder， import the person model the course model and membership。

 those are Python classes， we're going to make a person and save it。

 we're going to make a course and save it， we can check the ID to prove that。

We can look at all of the members values， that's a query set， and then with nothing in it。

And then we can create a membership。And we give membership that instructor。 This is that number。

 right， I think that was like 00 or 5000。 I think what that was。 and then courses C。

it's not there we go courses C in person is P that's taking from the P and C variable that we just created。

 we are basically populating the true table with the two objects from which we'll figure out what that foreign key is and then we save it。

 we can see that it's been saved by looking at ID。And so we can see these things like C members values now。

 we can see that this is the person who is a member of that particular course and we can see what courses TEed is in and TEed's in Woodcraft and so this is just another example using the shell to talk to some many too many relations So up next we're going to show how we do the shelllike operations but we're actually going to just write Python code rather than typing Python code。



![](img/16efea47d2ec2815fcf84bcc32918293_19.png)
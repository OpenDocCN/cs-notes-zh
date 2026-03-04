# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p84 14_使用PDO访问MySQL并插入数据.zh_en -BV1Lr421A75d_p84-

![](img/1e787e4629e2a31a470a1f29b733031b_0.png)

![](img/1e787e4629e2a31a470a1f29b733031b_1.png)

So now we're going to figure out how to actually insert data from a form on a web page into a database。

 We're going to go all the way through。 So here's the code。 It's not all that complex。

 Let's take a look at what it's doing。 And so here we have a form， right， in this form。

 it's down here。 If we take a look at the form。 Again。

 we got a model view controller where we kind of have the code that's doing all the thinking up here。

 This is the model。This is the view。And the controller does kind of its thing， right。

 controller is the thing that decides it。 we'll learn more about controller later。

 but this is the model code。This is the view code。 So we'll start looking at the view code because on the get request when you do a get request。

 it just skips all this because there's no post data。 right， But now I think you should know that。

 So it skips through。 And so it prints this out。 It has a form。

 Remember the name is the key value pairs that are going go into the post array name。

 email password and then a button。 So we've got this。 So we type all this stuff in。 type type type。

 We press the add new button。 and that sends a。Meth equals post once we type that。

Once we click this button， then it runs back in， except now there's post data。 There's the name。

 the email and the password。 So these variables get pulled in。

And now we're going to do is we're going to write some SQL， we're going to say insert into users。

 that's the database name email password， that's the column names。

 values equals and then we have these little things called placeholders。

Now you can name these anything you want， but I name them the same as the post data。

 but which happens to be the same as the column。This needs to be named the right。

 but this placeholder could be X and this placeholder could be X。

 This name here comes from the post form， and this name here comes from the data。

 but these placeholders are arbitrary things that you make up。

 but you keep your life a little sane or if you just name them the same thing。

 So colon name is a placeholder。 Col email is a placeholder Call a passwords placeholder。

 which will be replaced by this actual strings。 So we can print out this SQL。 So that's the SQl。

 and you see that the SQL just has these placeholders sticking in it。

And then we're going to do what's called a prepared statement。 So we're going to prepare it。

 which prepare is kind of looking at it and seeing if you got the syntax right， et cetera， et cetera。

 You know， what's going on。 So prepare can blow up。

 But then we're going to actually execute the statement。 So it sort of pares it and make sense of it。

 You might prepare it once and then in a loop， use it over and over again。 But for now。

 we're just going to prepare it and then execute。 So this is actually sending it to the database server。

 And what we're basically giving it is an array。 execute the parameter。So execute。

 we pass in an array。This is the array。To pass in with the a string with the placeholder。

 call a name map to the actual string we want。 So this is， this here is going to be Fred。

This here is going to be Fred At， and this is going to be you know，1，2，3 or whatever it is。

 So what that says is take these values， stick them in the corresponding place。

In the query and then run the query。Okay， so that's what that's doing the prepare execute。

 so it's what's called a prepared statement and if you're going to use the placeholders。

 you'll notice we didn't do this before we just ran the query and that's because we didn't have placeholders。

 we didn't have values that we wanted to substitute so the prepare。

 execute is the pattern we use when we have values that we want to substitute。



![](img/1e787e4629e2a31a470a1f29b733031b_3.png)

And so we can do that and we can insert a bunch of users over and over and over again。



![](img/1e787e4629e2a31a470a1f29b733031b_5.png)

Okay， so we can combine kind of the last two things by having sort of the add new user form that makes this user and we can have the model up here。

 This is the code from the previous one where we're just check and to see if we're in the middle of a post that comes from the add new and puts those things in。

 And then we can also just put a little y loop。 So we can see this。

 So we don't have to kind of hit the insert button and then go look and PhP my admin to see if it showed up。

 We can actually just have an SQl statement that is going to select。 And this， of course。

 came from like a couple of sample bits of code ago where we do select and we print all this stuff out。

 So you type something submit and then poof it shows up at the bottom。

 And that's quite easy and quite natural。 I'll show you in another video the exact demo of how this works。

 So now let's talk about deleting users。 So that's how you do inserts and select。

 remember doing Crud， create， read， update and delete。 So so we have to do delete。

 So the first thing about delete is you do not want to do a delete on。



![](img/1e787e4629e2a31a470a1f29b733031b_7.png)

![](img/1e787e4629e2a31a470a1f29b733031b_8.png)

You always want to do a delete on a post。 And so this is where you see and from a user experience perspective。

 you see often if you hit a delete button like little trash can or something or little trash can。

 you hit the thing， you hit it， then it goes to a page and says。

 are you sure So often what they're doing is this is a gat request。

That's going to show you a thing and then this is going to make when you hit the hit this button。

 that's going to be a post request。

![](img/1e787e4629e2a31a470a1f29b733031b_10.png)

Because if you remember getting post and the rules of getting post。

 you're not supposed to change anything on a get， you're only supposed to change it on a post because。

Crawlers don't follow posts， et cetera， et cea， et cetera。

 They don't The browsers don't let you double post， et cea， et cetera Okay so。



![](img/1e787e4629e2a31a470a1f29b733031b_12.png)

We're going to put up a screen。That's going give us a key that we want deleted in a field。

 Then we're gonna hit the button。 and it's a post。 So then when we hit this button。

 it comes in and runs this stuff。 And so if it's a get request。

 it just comes through here and and displays the screen if it's a post request。

 It comes in here and runs the stuff。 So it's really simple。 deletete from users where user I equals。

 and then you just have a placeholder。 In this case， I'm using colon zip。

 because you can make the placeholder be anything you want。 Okay， so then I'll print that out。

 I'll prepare the Sql。 And then I say I would like to execute that SQl。

 and I would like the colon zip to be replaced by whatever that user I is in this case the four is going go in there。

 So this runs SQl， delete from users where user I equals for。

 and that actually deletes it and away it goes So you sort to see the pattern。 It's like。



![](img/1e787e4629e2a31a470a1f29b733031b_14.png)

You make a SQL， you put in your placeholders， you do prepare， you do execute and execute。

 you tell what you want to put in each of the placeholders。



![](img/1e787e4629e2a31a470a1f29b733031b_16.png)

So it deletes it and it's gone。

![](img/1e787e4629e2a31a470a1f29b733031b_18.png)

And so I can actually， in this user 3， I sort of combine all this stuff together。

 and I put a little delete button。 And so eventually you'll have prettier user experience。

 but I want to make it so that if I press this delete button， this guy gets wiped out。

 If I press the add button， this guy gets added。 There's a new one。

 So I can have add and delete now combined onto the same screen。

 So let me show you how that ultimately happens。 Everything is the same in this user 3 do PhP。

 I add the the controller code， the view code up here。



![](img/1e787e4629e2a31a470a1f29b733031b_20.png)

The view codes up here and that's the delete code from that other one and then what I do。

 everything else is the same except this little bit right here。



![](img/1e787e4629e2a31a470a1f29b733031b_22.png)

What I have here is I have this is a form。I when to put this submit button， that data gets sent。

 this is a form， this is a form， this is a form， and that's a form。

 so let me show you how I construct that form。

![](img/1e787e4629e2a31a470a1f29b733031b_24.png)

Okay， so if you look， these are the table cells， the name is one cell， the emails another cell。

 the passwords another cell， and then this is that last cell。

 this is kind of like the action column and in that cell。

I print out a little form form method equals post input type equals hidden。

 So an input type equals hidden is like a text， but the user never sees it。

 And I say name equals user I D value equals。 and then the primary key of the row。 So I've added。

That I want to also fetch the primary key of each row。 And I put that in quotes。

 and I got it with arrows and less thans and new lines and all that stuff。

 And I have a little delete button。 which you do see， It has a little value of Dell on it。

 And then I have the end of the form。 And so that's how I end up with。



![](img/1e787e4629e2a31a470a1f29b733031b_26.png)

A form over and over and over again， right？So if you look at the source code of this particular form。

 you know it's going to be like yo， that's there and then this action column is there's a form。

 input type equals hidden name equals user ID， value equals 5 that came from the row user ID right there。

 and then I have a submit button and that shows the submit button and then I have and a form so like I said each one of these things is a form。

 the difference is they have a different primary key， whatever the1，2，3，5， whatever they are。

 that primary key is embedded in a hidden field in each of those forms。

Then when you press this button。It says， oh， the name is delete。 So if I have I set post sub delete。

 then I know that it was the delete form that was pressed， right， And I have is set post user I D。

 So that triggers this model code。This model code to run the delete。

 and that's just the code from from there。 And so that's how I end up with one，2，3，4。

5 little forms on this page。 Now later we'll make the user experience prettier as we go forward。



![](img/1e787e4629e2a31a470a1f29b733031b_28.png)

And so this again， is kind of the model view controller。 the whole model up here。

 we're going to require the P。 We got the add model model。We got the delete model。

 and so this is our magic line between the model and then below that， the view， right。

And so then inside the view， we're going to do a database call and we're going to loop through all this stuff and a away we go。

 that's really from the other thing。 And then we have the bit that has to do with user a form and and a away we go。

 I'll walk through all of this in a text editor in another video。 So up next。

 I want to talk a little bit about some security holes that I may or may not have just introduced into that last bit of code。



![](img/1e787e4629e2a31a470a1f29b733031b_30.png)
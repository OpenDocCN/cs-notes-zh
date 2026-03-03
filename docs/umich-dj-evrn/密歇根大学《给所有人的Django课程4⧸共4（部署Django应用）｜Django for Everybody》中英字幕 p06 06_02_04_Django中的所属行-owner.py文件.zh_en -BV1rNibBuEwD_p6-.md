# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p06 06_02_04_Django中的所属行-owner.py文件.zh_en -BV1rNibBuEwD_p6-

So hello， with all that as lead up， we are going to finally start taking a look at how we actually build this owner list view so let's take a look。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_1.png)

So the basic idea is we're going to make a new class called owner list view， owner update View。

 owner C View， a whole series of classes that sort of mirror the generic ones and we're going to add our own little sauce and we are going to basically make our owner list view which is going to extend generic list view and we're going to extend owner list view to create particle list view。

 so the thing we ultimately end up with as our view is sort of three layers deep where we have our view that extends another one of our views that extends a view that came from。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_3.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_4.png)

呃，jango。And so there we go， and so things like article list。

 HTML as the template and all that convention and the name of the variable article list。

 that's all convention， and we've been doing that quite a bit。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_6.png)

So let's start with the models changes Now in this model。

 everything except one line should be familiar to you and pretty comfortable。

 The only line that's a little bit different is this owner line。

 so it's just another field it turns out to be an integer。

 it's a foreign key like integer all foreign keys or integer and on deletete models cascade you have seen that before that simply means if we have a bunch of articles that are linked to a user and we delete that user。

 it deletes the four articles that were associated with the user in order to keep the internal pointers consistent。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_8.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_9.png)

So that part is is all the same quite comfortable and you've been doing that for a while now。

 Se off user model， we're importing settings from Django and we are making a foreign key to a model that is not ours It is something that Django maintains Djago always has a user model somewhere it may be named one thing or a different thing we just don't know we don't know what the name of the user model is and so we have to ask Django for it and Django conveniently always leaves it in this location Se do offus model and turns out if you want to change it。

 you got to change that variable。

![](img/89c28e67cdf3f58cc5fa0f53318ad234_11.png)

But for us， we're not going to change where it's at。

 Djago is going to set it for us and we're just going to use it。 So there's two tables。

 there's this article table and some user table somewhere。

 and there's a foreign key relationship between them on in a database level。

 And once you make this database you could go see what the name of that table is because it will show you the create statement that it actually use。

 not that that matters。 And so it's pretty much a normal old thing。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_13.png)

Like we've been making except it's got this extra owner column and're going that's the thing we're focusing on right now。

Okay， so the views are going to be pretty straightforward。

 the thing you're going to see about the views is we're not going to use the generic list view the generic detail blah。

 blah， blah， we're going to make our own these are made by us myarts。 owner， so we'll see owner。

pyy in a second。And so article list view， which is the is the you know we got a URLs。

pyy that routes here， is going to extend on our list view and say do this model。

 things like the template name and everything that's all done by convention right。

 so we're going to have a detail view， a create view now the one thing that's different about the create an update is there are two things there's a form。

Which tells what shows up on the screen， and then there is the model back here。

That shows up what's ends up in the database right so the model article model is what's in the database。

 The form is what we show on the screen。 So the model is which model is in the database and fields are which model fields are to be put on the screen。

 We're not going to show all of the fields on the screen in particular we are not putting the owner field in because we're not letting the user say this is owned by number 12 If it's owner 12 great that number 12 is the current logged in user。

 It's not something we let the user see So we don't put owner in here。

 We put the title in the text we don't put updated at or created at all the things from the model。

 we have to tell that we want this to put in the form and that to put in the form this is going to be handled internally and these all these three are going to be handled internally owner created at an updated at or handled internally text and title are to be shown to the user and so here we are an article create view and we're saying this is the model and make a form。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_15.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_16.png)

Based on that model， but only for two of the fields， ignore the other fields。

 the same for an update and then the delete't it doesn't use an actual form。

 so you just tell it which model it's going to use。 So again。

 this is a triumph of don't repeat yourself。 All the brains of this operation are really at an owner column oops。

Add an odor column and then。

![](img/89c28e67cdf3f58cc5fa0f53318ad234_18.png)

Extend these classes that we are about to make， extend the classes that we're about to make now I want to show you how to make the classes so I show you the easy stuff now we talk about the hard stuff okay。

So。This is the owner update view， and so let's take a quick review of the owner update view and。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_20.png)

If we when we first do a get request， if we go look at the documentation， it says， oh。

 I want to show you the old data in a form and I'm going to call a function called getQu set in generic update view okay and if I can't get anything if I don't get anything I'll give you an error so this is like to a URL like slash edit。

Slash2 and if the two is not in the database， then you're going to get a 404， so we call getQu set。

Okay， and and so let's just take a look at GetQu set。

 so the way we're going to do this is because we're in the middle of an update。

 the user is intending to modify it， which means we're not going to let them modify it unless they're the actual owner。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_22.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_23.png)

So what we're going to do is we are going to override the query set。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_25.png)

And I just put Prince Damon in for yucks。And so the first thing we're going to do is get the default query set This is going to pick the model that we're going to query and it's probably going to say something like you know the primary key is whatever that number was2 or 14 and so we're going to actually get a query set back and so that says super go into owner update view owner update go into no not owner update view go into update view and go run its query set and then give me back that query set and then what I'm going to do after I got that query set is add a and clause to filter it that says okay whatever that primary key was fine and the owner column of this model must match the current logged in user。

And so I'm like it's like at addingtting a where clause and an and to the where clauses。

 the other thing that you'll notice here is login required mixing。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_27.png)

I could have put login requiredquired mix on all those in all in the views。 py。

 but Rick I need to have this variable self-request user properly defined。

 which means any owner update view you really can't use it unless you're logged in so it's like I'm going to put the login requiredred mix in here that's like a marker interface that says look if you're not logged in。

 send them to login and then come back here and if they can't log in I'm never going to let them run this code because if you let a non-loggedin user run this code it would blow up right there。

 so in a sense this is like a guardian pattern to say don't even bother coming in here if you're not properly logged in and you don't have a user object properly pop passed in as request user。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_29.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_30.png)

And so that's why I put login required mix in there。

So the key here is we're going to do a where clause that is where ID equals 7 and owner equals 14 whatever the current logged in user is and so that means that when you come in here。

 if you're trying to edit a thing， you're going to get a 404 right if it doesn't exist。

 you're going to get a 404 or if you don't own it， you're going to get a 4040 404 is not found。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_32.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_33.png)

And it it's legit to say it might be there， but you didn't find it because you were trying to read it for updating so by changing goodQu set in a sense。

 to return zero records when you don't own the record because this is an update view if you look at the list view。

 it doesn't do any tricky stuff because you can list them all right and so list view is no big deal。

 a detail view is no big deal， but an update or a delete view。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_35.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_36.png)

Yeah， detailed view unless of you are good， but an update and delete you have an intention of modifying it so we're not even to let you retrieve the record if you don't own it。

 so we do that by overriding query set， calling super and then augmenting the query set when we get it back so that it accomplishes what we want to achieve。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_38.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_39.png)

So the next thing we're going to look at is how we actually store the data and the storing of the data is in form valid。

 we're going to override form valid and what remember when the post data comes in。

 we're going to first calls form valid that's checks to see it if the things are the right length if it's a date it's the right format。

 who knows what it does but we're also going to override it and stick our own code in form valid。

 so yes it's going to do all those checks， but also we're going to do a little sneaky thing to make what we want to do that's going to solve the create and update situation。

 but it's mostly for the create。

![](img/89c28e67cdf3f58cc5fa0f53318ad234_41.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_42.png)

And so in the create view， it sends out a blank form and then in comes the data。

 but we never showed owner， let's go back a little bit right so if we're going a create view create view。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_44.png)

The form that we're going to send out is title。And text。There is no owner field。

Now this owner is required and so we have to get the owner in， so what we do here。

 it's really quite simple。

![](img/89c28e67cdf3f58cc5fa0f53318ad234_46.png)

We're going to- so there's， again， there's a form object which is kind of like the UI side of things。

 and then there's a model object。And so Form do save commit equals false says just copy the data into an object as if we were going to store it。

 but don't actually store commit equals false is make it but don't store it and then we're going to add the owner field which is there to be self-request user now selfrequest use remembers like 16 it some number it's the primary key of the user and so that's going to copy 16 in here。

 and then we're going to save it。But then we're also going to do the validation。

And call the super to do form validation for us， and so we're calling the createate View form validation as well to make sure everything else is done properly。



![](img/89c28e67cdf3f58cc5fa0f53318ad234_48.png)

Okay。Okay，When it's all said and done。All we have to do to make an owner。

Work in this situation is we add an owner column foreign key to the right place。

 we import owner delete view， and then we just extend owner delete view to make article delete view and then tell it which model to work in。

 And then the magic all happen。 So I don't need。 I'm not going to show you owner delete view just。

 you know， that it's going to force log in。

![](img/89c28e67cdf3f58cc5fa0f53318ad234_50.png)

![](img/89c28e67cdf3f58cc5fa0f53318ad234_51.png)

And it's going to only let you delete rows that you own in the system。

And so this is really a neat example of how you can use the object orion pattern to extend these existing things and give features that you want to add to them I'm going to guess the first。

10 of these are going to be just at an owner field because it's such a common thing to have a database rows that have an owner field in them。

 but you know we can do other things beyond just an owner field and it again is a nice review of object orientation I'm just going to hit Os orientation over and over and over and over again because。

It's hard to get it and I want to tell it to you as many times as I can。And again。

 I don't like putting， we don't like putting， don't repeat yourself。

 lots of boilerplate to do this owner， you could do it all in a view， you really could。

 but you really don't want to， you want to basically make an object yourself。

 we've been using other people's objects now we're extending object classes to make our own classes and then using those classes so it's a good example of how we can save a lot of time and energy with object orientation and inheritance。


# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p33 07_02_04_在Shell中使用Django模型演练.zh_en -BV1Kt421V7EE_p33-

Hello and welcome to another walkthrough for Django for everybody right now we're thinking about data models and I'm going to show you how you can walk through and run this particular little example in the Django shell。

So let's go ahead， we're going to Python anywhere。I've already got a bash console。

 I love the idea of this bash console， this is Linux。

 I think that everybody should be learning Linux。

![](img/62ffef858791cf1e23e84bf8f96827a5_1.png)

So if I start my home directory CD dot dot means go up a folder LS minus L I got some folders here I got DJ free samples。

 which I try to convince you to check out so that you can edit your file。Edit my files。

 look at my files， use that as sample code for your own work。

There he is instructions on how to get clone that and so but we're going to we're going to assume it's already there already there and follow the。



![](img/62ffef858791cf1e23e84bf8f96827a5_3.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_4.png)

For the instructions， so we're going to go into that folder C。

And then we're going to type a get poll。And the way this works is this is in GitHub。

 and that way if I've made any changes or fixed any bugs in my sample code。

 you've always got the latest code。

![](img/62ffef858791cf1e23e84bf8f96827a5_6.png)

And I've already done this， but there is a bunch of so oh， by the way， I got to switch into my。



![](img/62ffef858791cf1e23e84bf8f96827a5_8.png)

Jngo3， I got switch into my virtual environment， you'll notice I didn't have virtual environment now I do that's because this next command is Pip command。



![](img/62ffef858791cf1e23e84bf8f96827a5_10.png)

Just notjango 3。This P command is going to change the Python configuration。

 and it's literally best if you do this in a virtual environment。

 So you're not like messing up your overall Python install on your system。

 whether it's your desktop or。

![](img/62ffef858791cf1e23e84bf8f96827a5_12.png)

or Python anywhere with my particular requirements with my this is installing a bunch of utility code。

 et cetera， et cetera， et cetera， and is there some new it looks like I got some new version here and most of it's already there from a previous time that I installed all this stuff。

 but it's good that I ran this。Um， to make sure that I have all of the Python requirements needed for this。

So now it's done and it's installed all of my requirements。

 so I'm going to type the clear command to kind of clear up my screen。Okay， so there we go。

 so then the next thing you run is this command that we run， we're going to run a lot。

 especially in Python anywhere， is this Python 3 managed PY check。

And what this does is it reads through the URLs doi and the applications and a whole bunch of other things。

 And it blows up。 And so if you get no issues， that's good。

 The point is is you do not want to continue down this other path unless check passes because make migration starts to make changes。

 So make migrations is。

![](img/62ffef858791cf1e23e84bf8f96827a5_14.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_15.png)

Jango reading through all of the ModelSt Py files。And and creating migrations。

 So migrations are not SQL， they're actually Python code。

 And because this was checked out from Github， that all of the migrations are actually sitting there。

 right， There's a way if you want to remove the migrations and remake them from scratch So the migrations reads model stop Py files like。

VI users。Model。py。And reads these and then creates migrations。

And then the next thing that happens is we're going to actually I'm I'm going to get rid of my database that SQI3。

 you can that throws away your database， and actually tells you do that right here。

 and then migrate reads the migrations， migrate doesn't read the Model。pyy file。

 it reads the migrations， and then it creates the database and so it's going to create a database and it is going to create a bunch of tables in that database。



![](img/62ffef858791cf1e23e84bf8f96827a5_17.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_18.png)

So you see for each of the applications that I have in this jnangle project。

 it's creating it's creating a bunch of tables。 And so here， for example。

 as users one into initial that is the table that I'm going to mess with up to that point。

 So now I've done all this stuff and it's time to actually。



![](img/62ffef858791cf1e23e84bf8f96827a5_20.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_21.png)

Run Python managed PI shell。So what this is is it's like starting Django and loading all the Django libraries and reading all the Django configuration files so there could be a bunch of errors that happen at this point and if they are。

 go back and fix those errors， okay you can't just like oh I think I'll ignore those。

 this is what the manage PY check did， it sort of did that。

But now it's like your' interview views py file， which we'll see in a bit。

 you can type Python commands that Django inside Django， it's not just Python。

 but Python with Django and all of your Django application preloaded so that's why it takes it takes a of a bit of time to get to this point。



![](img/62ffef858791cf1e23e84bf8f96827a5_23.png)

And now it's pretty easy so we can now we're going to type Python， right？

And we're going to import the user model。And that worked。And now we are going to create。



![](img/62ffef858791cf1e23e84bf8f96827a5_25.png)

A new user object so these next two commands are really important。

So what that user says name equals Kristen email equals that is going to create a new user model object in Djagos Python's memory and give it back to me in the variable U at this point。

 it's not stored in the database。 So if I say where did this store in the database oops， U dot I D。

There is no ID currently because if it was given an ID in the row that gets a serial number basically of the user after it gets saved and you dot save。

Says see this U variable that I've gotten memory full of data， well， store it in the database。

And now I can say u dot ID and I can see that it was stored in the database at position one。

 which is exactly what you would expect that these numbers are pretty simple。

 they start at one and they go up and we'll see as we do a few more folks。



![](img/62ffef858791cf1e23e84bf8f96827a5_27.png)

Let's put a few more folks in。will you reuse the variable you。

I'm just going to copy and paste all these at the same time。



![](img/62ffef858791cf1e23e84bf8f96827a5_29.png)

And now I can say u dot ID for whoever the u do u dot name is Sally， that's the last one I did。

 and then u dot ID。Is five。 it's the fifth one。 So now I have five models that have been persisted。

 stored in my database。

![](img/62ffef858791cf1e23e84bf8f96827a5_31.png)

Now， if I want to retrieve those user objects， so user is the name of a model that's actually a class objects is a。

Attribute in there， which has a method of values。 So I can get back all the values。

 And you see what I get is what's called a query set。

 but all intents and purposes it functions like a list。 And then in that list。

 there is a series of objects。 And it looks exactly like the data that I put in。

 but it pulled that from the database。 And the thing that's in there now is the I is now in there。

 So this this data has a primary key for every other one of the rows that I put in there。

 And so I can say that so。

![](img/62ffef858791cf1e23e84bf8f96827a5_33.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_34.png)

I can add a filter and so you'll see this pattern where user objects and then I sort of throw these things in and then the dot values comes at the end。

 and that's because filter is a method that returns a thing that has a method。

 so this is the values method that the filter returns and you can just keep putting these together so I can say this is like a where clause and SQL so this basically says give me only and it's a query set so it's a list。

 but there's only one object now there could have been more than because we don't have any uniqueness constraints on email there could be more than one record that match email C7@um。

edduu。

![](img/62ffef858791cf1e23e84bf8f96827a5_36.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_37.png)

You can delete， so this is basically， let's go grab that record。

 but then run the delete method on that model object。Model instance， so this will get rid of。

Then then。The TD record， we can go retrieve all of the objects and we can see， oh， there they are。

 but there's no Ted。 There was a Ted before， another is no Ted。



![](img/62ffef858791cf1e23e84bf8f96827a5_39.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_40.png)

We can update so let's check this one again。 let's grab that and pull out so this we're going to change this name here。

 This is in the database。 And so we're doing crud here。 And so we're going to update， create， read。

 update and delete and update the last one we got to do we delete it so again。

 we're going grab all the objects we're going filter them down withware clauseuse to the ones where email C7 image。

 E you。 and then we're going to set new values。 And so if I now。



![](img/62ffef858791cf1e23e84bf8f96827a5_42.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_43.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_44.png)

Say what is this well the name has become Charles so it switched from Chuck to Charles and it's in the database right this is not just in memory。

 this is dnangle writing all this stuff to the database。



![](img/62ffef858791cf1e23e84bf8f96827a5_46.png)

Now just a little bit more and you can go read up on this and we'll have lecture after lecture and all kinds of example codes。

 but you can sort of sort this stuff by email ascending so a。



![](img/62ffef858791cf1e23e84bf8f96827a5_48.png)

四。Collleeen， CVL， and then K comes later， or we can descend。

We can see them descending so did I get that wrong， Oh， that's in descending order by name， so S。

Okay。CCOC， so they're descending by me。So that gives you just some of the kinds of things that you can do in the Python shell。

 let's say quit parenthees here。And there we go， okay。

 so I I hope that you found this thisjango for everybody walk through useful cheers。



![](img/62ffef858791cf1e23e84bf8f96827a5_50.png)
# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p02 02_01_06_DJ4e市场平台初始设置与安装.zh_en -BV1rNibBuEwD_p2-

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_0.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_1.png)

嗯。Hello and welcome to yet another walk through for Django for everybody。

 This is a walk through of the first lesson where we start working on the marketplace assignment。

 So there is the marketplace setup。😊，And so this is something you do before you start working on Marketplace。

 We're going to start this using a Github， which is a little bit different。

 It makes it sort of easier and then a little bit different。

 So we go to the assignment specification and then it says we're going to build the whole Marketplace website is got ads and tags and by the time you're all done you'll have many。

 many features but we're just going to get it started now and there is a Github reppost。

 so instead of having you type a bunch of stuff I've given you kind of an empty application in GiHub and so you are going to follow the instructions。

On Github， which is common， you'll find dgle projects。 there's a read me here。 So this is my market。

 And so this is the starter。 So these instructions are how to do it。

 So we're going to start by going to Python anywhere。Okay so if we look at our files here。

 we havejango projects， which is where we're going to install it Myite。

 that's the thing that you've been using to do all the applications up to this point。

 And so we're going to create a new Django project So the firstjango project is my site and the next Django project is going to be called market。

Okay， so let's go into consoles。And start up let's get rid of that one， start a fresh bash console。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_3.png)

So the instructions here are in this GitthHub repository Okay。

 so the first thing to do is check to see if you already have a Django 5 to virtual environment。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_5.png)

CD tilted。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_7.png)

Now， the fact that it says V E52， that should be a clue right there。 but we'll do it anyways。

 And you'll see that we're going。 this is the folder in your home directory tilt slash dot V E5，2。

 And there's stuff there。 And if you look at the instructions， it says， oh。

 if the output looks like this， which it does， then you've got one。 Okay， great， great。😊。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_9.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_10.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_11.png)

This is you can ignore this now because you don't have to do any of this stuff and then once you're ready to go。

 we're going to do the install so we've got to be in our home directory。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_13.png)

And we need to be in the 5，2 virtual environment。 Okay。

 so then we're going to start running these commands one a time。

 I don't like using this little clock check all thing。 It， It gets kind of。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_15.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_16.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_17.png)

You want to look at the output of every one of these things。 So this is the get command。

 and the gi should be already be installed on。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_19.png)

So we're in Dngo projects。 now if we take a look at our files， hit reload here， you will see now。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_21.png)

That now there's a market and there's a bunch of stuff in market。

 and it's kind of similar to what we had in my site。 you know， it sets up a bunch of stuff。

 there's a managed do Py and a home file config。 Now the key thing here if you take a look。 Well。

 let's just， let's follow it。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_23.png)

CD market。So now we're in that or in home directoryjango projects market。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_25.png)

Then we'll check our Python version。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_27.png)

And the Python version is 313， which is perfectly fine because that's in our virtual environment。

 Now， if you just you these may me not do much if you've already got your latest Pip and a probably say you're already good。

 you got the latest Pip and let's do Pip minus installst our requirements TXt。

 And I I look at that and say you've already got it because you already got a virtual environment。

 This is just adding a bunch of stuff。 So you see it just said it's great。

 you got everything you needed from when you installed the Dj3 samples before。

 And let's just for double checkin， check to see if we got django。

 And here we are on a virtual environment。 we got Tjango 52。 So we are in good shape， right。

 So depending on what you see。 you may need to do more or less of this。😊。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_29.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_30.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_31.png)

So， now。You'll notice， as I said before， there is no market market。 There's a file。

 I changed the name of this to config， and you can file the patterns here。

 So settings that P5 Py is in market config。 A lot of developers don't like the market market pattern and want to change the name of the project folder and the project configuration folder to be two different things。

 So I followed that pattern here just to give you a little different way of thinking about it。

 Okay And so we'll be in our home directory。 I mean。

 our project directory and do Python manage P check。In the market directory， and that's good。

 it's didn't if you have problems， you should something went wrong。And so it worked okay。

 So so we've already installed the application。 And I put everything in there that you need。 Now。

 there's a few things that you're going to have to do。

 So we are going to go in our Python anywhere and go into the database tab because we're going to switch to using my S Q L。

 Now， let me initially set my password to something。That。There we go， I'll set my password to that。

I'll change it later。Okay， initialize myosQL， so now we're setting MyqL as part of all free Python anywhere databases and it's taken a little bit of time。

Okay， so now。We need to make a database， don't use the default one。

 let's create a new database and let's call this one market。So we can have multiple MySQL databases。

 MySqL is way faster than an SQL light。The problem is。

 is that SQLite stores its data on a network drive， which is not the best for SQLite。

 SQLite's a fine database for small things。 So we got a database name market。And so now we're good。

 so let's continue back to our instructions， so we are going to go into our settings。 Py config。

Settings。pyy， and we're going to find our databases。So。So this one here， it's not the default， oh。

 I see。I got both these in here， so let's comment these out。O so。We'm going to comment this one out。

This came out of Gitthub this way already set up。So I'll comment out the。This one。

 and it looks like most of it is already there。And it even has the password。

 it's going to be called market。And this is going to be and this my account here is CSE。

 I'm not Dr Chuck here。I'm C7。And CSE。Okay， so C7 is is my Python anywhere account market is the database I just made C7 and this password which I'll change later。

 but that's the password I used oh I got to change this to be C7 as well okay。Okay。

 so I'm going to save this。And make sure you comment this one out this is this is a Python code and so that。

This database is， if it runs later， it's just a variable， and so you got to be careful。

 it'll go back to SQL light。If you don't comment this out， okay？So。

Now let's go back to our instructions。Says to fix all that stuff up。

And you make the changes and save it， then you run Python manage Py check until there are no errors。

 so hopefully。We'll just do this right away。 Python manage Pyche。 No errorss。 That's good。 And again。

 in all these things， if you get an error， slow down。

 So now we're going we're already in this folder， but we'll type it again。

So we're in our Django projects market。And then。We do make migrations， chances are good。

 this will not give us any output。Oops。Y， no changes。 That's okay because that make migrations。

 as by now， I hope， you know， doesn't really touch the database。

 It just looks at the models do Py files， and now we're going to do a Python managed by migrate。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_33.png)

And so this is actually now that this is really important because now it's doing all this stuff which you've done before with SQL light。

 except now it's doing it with my SQL。 So if you go into your MySQL。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_35.png)

You will see a whole bunch of tables have been created。 And so we can get a console。

 Let's see what happens when we click on the market。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_37.png)

Now this is my SQL console， which is very， very different than a bash console。

And an SQL command in my SQL is called show。Daables， and you end em with。

So this made all these tables in the marketing database in the market database， which is good。Okay。

 so I'm going to close this one。 I don't need it anymore。

 I was just kind of checking to make sure my database is right。

 and then I'm going to create a super user。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_39.png)

Now， you might have created a super user before， but we just changed a database and made it all fresh again。

 so I'm going to call a super user。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_41.png)

And I'm going to call it admin。And I'm not going to give it an email address。Yeah。Yeah。

I got to write that down， so I don't forget it and then have to reset it。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_43.png)

Okay， so we had to create a super user。And again， that's because。

You just needed to create a super user because you didn't have one from when all the stuff you've done before。

 those are all in SQLI。 Now what we're going to do is go to the web tab。And switch。

So remember this is the run server and so you've got a couple things here。

 so we're going to change this， Everything should be the same except we're just going to make this be market。

And you can have many applications in here， but you only to have one active at the same time so you can actually switch back and forth。

So I make that be market。And the virtual environment is right。

 and then if we look at our instructions。Okay， so it said source code and workinging director。

 you fixed that。And then we're going to edit this stuff。This is in the Wsey configuration file。

And again， this goes into my site。 And you can kind of guess what this is。

 It's going to change this word my site to my site and this to config。

 But I'm just going to paste them in。 And it'll do all that， right。

 So we're going in the market folders the market。 But config。

 that's that new merit settings stop P Y is in a folder name config now。 And so that's。

 that's why it says config settings。 You can switch back and forth between market and my site if you want。

Okay， so let's go back to the web tab now， So we got our Wey done。

 we've got our virtual environments correct from before we had that before for the first part of the class。

 So let's take a look at the application。 Well，' got to go to the web tab and let's reload it。

And let's then see if it works。And there you go， so you got some other things that you're going to do you as you do stuff in here。

 but if we go into this these instructions， we'll see that， yeah。

 it's shows so we'll go to home slash home。That's there。We'll go to。/lashfavacon。icco。

And that's the icon that shows up。come that's not showing up。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_45.png)

there oh， I see。 see there you got that icon that shows up and then we'll do one more thing here。

 go back to the instructions and we'll go to admin。



![](img/d3d2d5080524ffb4df2b6b165c3a69b5_47.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_48.png)

And I name my account admin and。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_50.png)

And there we are。 Okay， and so now you have this all set up。

 and so you pretty much have finished the read me at this point。

 read me's done and you have finished this initial setup。 Okay。

 so I hope you found that useful and then you'll go on to the next step and the auto graders。

 etc ceter， after you finish this。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_52.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_53.png)

Cheers。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_55.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_56.png)
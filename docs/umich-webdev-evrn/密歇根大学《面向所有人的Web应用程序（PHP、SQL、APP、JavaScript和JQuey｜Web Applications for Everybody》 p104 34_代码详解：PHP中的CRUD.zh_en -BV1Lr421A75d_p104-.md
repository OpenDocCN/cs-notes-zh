# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p104 34_代码详解：PHP中的CRUD.zh_en -BV1Lr421A75d_p104-

Hello， everybody。 Welcome to Web applications for everything。 Yet another code walk through。

 The code we're walking through right now is Crud， the Cd application。

 Now you'll notice if you click on the crud application。

 it won't let you run it on web applications for everybody。

 And that's because it requires a database connection。

 So you're going to have to download it and run it somehow on your local host to sort of see what's going on。

 And so there we are。 We got a crud running here， make it a little bigger so you can see it。

Because it has to be set up。

![](img/664e0683bfe1607ce851355c9f9c5d96_1.png)

And I have this missed folder， that a little smaller。this missed database。

 and if you're a little concerned or confused about how to get things set up in the CRD folder。

 there is a SQL notes on how to set this database up and then insert some users into it。



![](img/664e0683bfe1607ce851355c9f9c5d96_3.png)

U。And so， so basically the idea of this cru application is it's not really that different than anything else we've done。

 We're really kind of moving code around and cleaning it up and and bringing it to sort of the best practices。

 So before we have done things like。Oh， in the P file， we did things like user 3。php where。

We sort of had a delete and an insert and a table all showing in the same thing。 So in a wake。

 this is the file from several several lectures ago。

 that's the closest to what we're going to do in Crud。

 But what we're going to do is we're going to have a set of all。

 we're going pull some of the functionality out and kind of clean it up out of user3 and move it around and then come up with a pattern where we have a file each for the insert the delete and the update and the list。

 And so this turns out like the index file is the thing that does the list。

 Let's just play with this application for a second。 So here's our index。

 and it shows what's in the table。 We can add a new thing。



![](img/664e0683bfe1607ce851355c9f9c5d96_5.png)

Ros。Caitlin， C， A T Y， L Y， N Umi Edu U。 and then， you know，9，8，7。

 So we have an ad page that does the ad and everything has a cancel to go back。

 and then it it redirects itself back to index PP with a little success message。 and then if。

We got a delete。We can delete this and delete it， now it's gone， and then we have like on edit。

And we can make changes。And then update it and it changed it。

 So we're kind of routing between these four main files。

 There's sometimes a view file like a view dot PhP that we click on。

 but we have so little data that we just kind of do it in the index PhP。

 So this is not that different than anything we've done before。

 So let's go ahead and start with index PhP。 The one thing you'll notice about index PhP is I'm using Hres to go into edit with a get parameters user I equals1。

 And in to delete。 So there's no forms on this。 And so there's no posting going on。

 There are just Hres。 These are ares and this is H。 So if you look at the top。

 the kind of the model part of index， there's nothing there。

 All I do is pull in the P and I start the session。



![](img/664e0683bfe1607ce851355c9f9c5d96_7.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_8.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_9.png)

And then I have flash messages。 and pretty soon this is going， it won't take long。

 I'm to stick these in a utility file and just include them。

 but basically they check to see if there is a kind of a residual from whatever previous thing was executing if there's an error or a success printing it out and then deleting it to implement the flash pattern。

This。Table is pretty much code we've done before， we make a table， we make a row。

 and then we make one， two， three， and then the fourth column。



![](img/664e0683bfe1607ce851355c9f9c5d96_11.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_12.png)

Is this edit s delete。 And all we do is we put an anchor tag in edit dot PhP with with a query parameter user ID equals the primary key of the user ID。

 and that's the edit text and then the delete dot PhP。 and that's the I equals in the delete text。

 So that's how we end up with Hs。 and then we just go to add dot PhP to go to add new。

 So let's take a look at the add code。 This yellow stuff。 This is just my browser。

 I wish I could convince the browser to stop doing that。 That's the browser prefilling stuff in。

 and the add code is kind of like the user 3 do PhP code。



![](img/664e0683bfe1607ce851355c9f9c5d96_14.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_15.png)

TheIt's got some post intelligent post code， you know， it requires P PhP， session start。

 gets things going。And then it has a， it's not doing a very good job。

 but here's the beginning of the view。 it's not got a doc type HTML， sorry about that。

 but it does check to see if there's an add flash and we'll see when well use that in a second and then we just have a simple form。



![](img/664e0683bfe1607ce851355c9f9c5d96_17.png)

And then we have a cancel， I'm just making the cancel be a Hf rather than a fancy button。



![](img/664e0683bfe1607ce851355c9f9c5d96_19.png)

Now， if we take a look at the postcode， this postcode does a bit of data validation。

 now I'm finally doing some data validation and this is the model code that says if there is these three variables that are in the post。

 you know。

![](img/664e0683bfe1607ce851355c9f9c5d96_21.png)

Ai。A at a。com and A is the password， if those are set first we're going to check to see if the name or password is less than one in terms of length。



![](img/664e0683bfe1607ce851355c9f9c5d96_23.png)

And if that's not true， then I'm going to say missing data， oh， so let let's execute。

And then I'm going redirect right， set an error， redirect back to the script and then quit so we don't fall through so we're gonna be doing that all the time so let's let's send bad data and here we go。

 So if I do have you developer console on this and take a look at the network tab and let's make another mistake get rid of that get rid of that you know blah。

 blah， blah， but we'll keep the rest of it blank and we're just going to say add new you'll see that it does a post to add dot phP and then it。



![](img/664e0683bfe1607ce851355c9f9c5d96_25.png)

Seets the error， and then it does a redirect。Back to add dot Php。

 which immediately doesnt get to add dot PhP， which is what then gives us back this page with missing data right so that comes out so that's a post redirect and this is a error checking a data validation error checking post redirect and that's that's exactly what we want we're going to check to see if there is an at sign in the middle of the email and so if we we have nonb stuff here。



![](img/664e0683bfe1607ce851355c9f9c5d96_27.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_28.png)

Right but there's no at sign here it's going to complain， it's going come。

 it'll make it through these stir lens， but it won't make it so this is my pattern， data validation。

 looking good， check this one looking good， anytime you quit。

 just quit right there are other ways to do this， but I try to make my data allocation kind of in a protector pattern where I'm not going to let you go any farther。

 I'm out of here if something's bad。

![](img/664e0683bfe1607ce851355c9f9c5d96_30.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_31.png)

So this one's going to say bad data with a a post redirect。



![](img/664e0683bfe1607ce851355c9f9c5d96_33.png)

And if everything is fine， it does an insert using PO key with the substitution parameters， name。

 email and password。We prepared the statement one of the things is you don't put debug print in here because we're still above the line and so we don't get to print the SQL out I tend to it's a little harder you can print this stuff out。

 but then you don't want to you want to sort of comment out the header because you want to be able to see the output if you're debugging in here but we just do the insert we've done this before and then we put a success message and then we go to index。

 phP so we're doing controller function to go there so X X@ Y do co。



![](img/664e0683bfe1607ce851355c9f9c5d96_35.png)

And some password and we hit new and so it redirects and goes back to index PhP and index do PhP has a success message。

 And because it's been wiped out at the end， we hit refresh or get and that message goes away。

 but the data doesn't go away。 The data is still there。 So that's the flow for insert。

 So let's do delete next。

![](img/664e0683bfe1607ce851355c9f9c5d96_37.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_38.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_39.png)

So delete， remember， it just is a Hf coming out right here。

It does an Hf user ID equals and then the primary key。Let's take a look at the delete code。

So here's our model， so we're going to ignore that。

Now we are going to check to make sure that the user ID we've been given is correct。

 so if I don't if I somehow can find my way to delete that PhP。



![](img/664e0683bfe1607ce851355c9f9c5d96_41.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_42.png)

It says missing user ID。Seets an error and goes right back to index up PhP。

 so somehow that didn't work well， but if it's a URL that we constructed。

 the user ID probably is in there。 so then it's going to demand that。

 then it's going to do a select where the user ID is whatever this number is8 in this case and if we don't get a row。

 then we're going to say bad value for user ID。 So if I do user ID equals。



![](img/664e0683bfe1607ce851355c9f9c5d96_44.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_45.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_46.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_47.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_48.png)

Come on， 800。

![](img/664e0683bfe1607ce851355c9f9c5d96_50.png)

It's going to say bad value for user ID and then redirect index PhP， see how easy this is。

 you just like check a problem， boom， set a flash variable， send it back。Okay， so now finally。

 we're going to get to the point where we're going to put out a confirmation dialogue and we're going to use HTMLities or using the short print this variable out but we call HTMLminities just in case the user has name themselves。

 Mr。 double quote input type equals button or whatever or little Johnny Tables for all we know and so we're just putting that out and that comes up here and so X is the person's name。



![](img/664e0683bfe1607ce851355c9f9c5d96_52.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_53.png)

And we have a little form with a hidden variable， which is the user ID， the primary key of this。

Of this user， and then we have a little a delete button or cancel button that's really kind of routing us back to index。

php。

![](img/664e0683bfe1607ce851355c9f9c5d96_55.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_56.png)

U， but then the post comes in and we post the delete we're checking。

 that's the delete that comes from the submit button。post sub deletelete the name。

So if set post subdlete， that really means that delete button was pressed and there is a user ID。

We want to double check these。 Don't don't skimp on these。

 check for everything you're going to use because the last thing you want is some kind of trace back in here。

 So just double check stuff。 this kind of guardian pattern is what it's called to make sure that we don't run code when we're not sure the post is set So we're not just deciding when to run this code。

 but we're also making sure that all the preconditions necessary to run it are okay So we're going run a delete statement。

 delete from user ID whatever we use a prepared statement and all the P goodness。

 we say record deleted and we redirect indexed P PhP and we return these three lines and these three lines are like yup。

 you better get it because it's what you do I want to go here。

 and I please display a green message record deleted And so when I say delete。



![](img/664e0683bfe1607ce851355c9f9c5d96_58.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_59.png)

It does that right and goes back to index。 PhP and has a nice little success message。

 and I keep saying this if I refresh， the success message goes away。

 but the data doesn't change Okay， so that's a flash。



![](img/664e0683bfe1607ce851355c9f9c5d96_61.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_62.png)

So we're zooming through this。 So the only thing that's a little new。 Actually。

 most of that was code we'd already had is just a lot cleaner now， right， So now let's go into edit。

 Let's take a look at edit。 Edit's a little bit different。's kind of like an ad。



![](img/664e0683bfe1607ce851355c9f9c5d96_64.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_65.png)

Here's here we go again in the model part， we're going to say if these things are set in the post。

 I'll come back to that。Again， we're going to be clever and we're going to check to make sure that we know the data。

 but now we're going to select all of this stuff right so select and we wait if there's no row so if someone had like somehow gone to a user ID number that doesn't exist up here。

 but we won't do that it works just the same as the delete code。

 I probably there's grab this code right here from the delete looks like it's exactly the same as the delete code。



![](img/664e0683bfe1607ce851355c9f9c5d96_67.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_68.png)

And then I'm going to start printing the data out and so I'm going to use a little I'm going to do HTML entities rows sub name。

 email and password and put them in the variables N E and P and pull out the user ID that's just to make this a little more concise here some HTML with some little bits of PhP variables being dropped in for the existing old values Now I've already called HTML entities on these three so they're okay。

 so we're safe And so that's how these old values that were pulled from the database in row number one get there Now I'm sitting here waiting and I'm going to say Chuck。



![](img/664e0683bfe1607ce851355c9f9c5d96_70.png)

Chuck and I'm going to do a post and then the post is going to come in here So this is the first time we've seen an update。

 but it works just the same as anything else。 it's exactly as you would type update users set column equals placeholder comma column equals placeholder column equals placeholder where user ID equals placeholder then we prepare that statement and then we execute with the data from the post and of course this is solving our problem of SQL injection because we're using prepared statements in PO and we should in time we'll put error messages here。

 etc but for now this is mostly going to work unless it blows up because we have a syntax there in the SQL which we don't。



![](img/664e0683bfe1607ce851355c9f9c5d96_72.png)

We set a success message record updated and then we redirect and then we stop you pretty much as soon as you say header location。

 you're going to quit so I've changed this to Chuck I say update and there is my data and of course it's a post redirect I don't have to tell you that by now I think you kind of got it。



![](img/664e0683bfe1607ce851355c9f9c5d96_74.png)

Edit we do do a post to edit， get no response， but then it redirects。

 and then it gets this thing back。

![](img/664e0683bfe1607ce851355c9f9c5d96_76.png)

That's pretty much it right that's pretty much the CRD code it's not that compared to everything else we've done so far。

 it's not all that new， it's just coming up with a nice organization for the code so that we can make sense of it and not make these applications too complex so I hope this was helpful and I hope the rest of the code walkthroughs have been helpful as well。



![](img/664e0683bfe1607ce851355c9f9c5d96_78.png)
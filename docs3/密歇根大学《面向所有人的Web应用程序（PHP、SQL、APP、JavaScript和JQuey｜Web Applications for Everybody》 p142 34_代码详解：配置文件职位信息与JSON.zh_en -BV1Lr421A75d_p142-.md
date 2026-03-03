# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p142 34_代码详解：配置文件职位信息与JSON.zh_en -BV1Lr421A75d_p142-

And welcome to web applications for everybody We are going to go in this bit of a code walkthrough of the autograder I mean know the assignment for profiles。

 positions and education and so there's two real learning objectives for this one is we want to do a little bit of we want to do a little bit of exercising at JSON but we're also going to end up with a many to many relationship and so like always I've got a whole bunch of things that you're supposed to do and how you're supposed to do this and again it builds on the previous ones so if I assume you've watched all the previous ones or you have the previous assignments working。

So。So let's go ahead and just run this code and demonstrate it。HTTPcon slash local hostst。

Web applications for everybody。This is not Re's position。 This is Re's education。

I got stuff in the database， let's see what I got profile。Let's just get rid of all of them。

That didn't work。So let's just go here。Delete from profile。With nowhere claws。

 delete from profile with nowhere claws， sometimes it's nice， nowhere claws。

So now I should have nothing in positions because I could have shown you that but the cascading foreign key got rid of all that stuff。

 so we still have our users and let's check we got the one user with the hash password which we're supposed to have。

Now the first thing we're going to do is we're going to put in some new tables here we go。

 let's just borrow this out of。The assignment and create two new tables with some foreign keys。Go。

Okay， so now we have。The education， and we're going to use this as a。

Look up table and have a and then。I mean， institutions is going to be this lookup table and we're going to have a many to many relationship。

 this is a two way link where we have profile ID link in a profile institution link to institution and so each of the people are going to have when they choose an education and we'll see how that works in a second。

And then I've got a seed。你啊。Institution table with some interesting data so go into the institution table and insert some data。

And so now in our institution table， we've got some institutions， okay？So now that we built this。

Let's log in。I had the cancel。UMS S I。You study to you？I guess that's the right password， no。In I。

PhHP1，2，3。My browsers keeping those passwords， okay， add the new entry。

So a lot of this looks the same。Got first thing。And the position is like from before。

But education is a little different， okay， so this is the one we're going to do differently。

So in education， orient the plus， we're going to say 1990。And then we are going to have this school。

 but what we're going to do is we're implementing a type ahead and that's in the assignment to implement a type ahead and it tells you how to build the type ahead。

So if I type。UN University of I can choose this now the interesting thing is this to use JSO and JQu so。

So if I do a view developer a console。And this is how those things work。

 I don't know if you can see it now， let's do that again， let's empty this out。Basically。

 what happens is you've told Jquery that as people type call server based code for the prefix。

 And so there's a database query that's going into this database table here looking for。Prefix is U。

 so if I type U N。You see that it actually made a query and in that query。

 if you look at the response to that query。That query is a little table right of all the that is select using a light clause。

Select。Using a like clause， like is kind of a wild card you percent is like the wild card character so this is going to be UN percent like university。

 UN percent， and then that matches those prefixes。Now。

When I pick one of these things it really is still all in the browser。

 it's all JQu and this is still just a text field， there's nothing tricky here。

 this is a sort of an intelligent text field。Let's move this over， let's make this wider。

This is an intelligent text field that now has a value of University of Michigan。

When it gets submitted， it just gets submitted as a string and you'll see what we do when we submit it。

Okay， and so so that's the tricky bit is to add this and what we want is we want the users to reuse existing ones or make new ones so you can even add a new one called。

1996。Lansing community College。This doesn't match anyone， but it's going to end up inadvertent。

 it's going to add one and then link it together and so if I hit this add button。And I take a look。

 you'll notice in the institutions by me typing a new one Lanston Community College has been added here。

And so then if we look at the profile。I got a profile， this is me。I got some positions， no。

 just got one position。And then I got education entries， and so if I look at the education entries。

 the education entries are a many to many， pointing at profile ID 10 and Inst ID1。

 which was the Cambridge one， I think。You can find out Cambridge no that was University of Michigan and then 10 is the Lansing Community College one。

 And so we got a lot of stuff that we got to make work。 We can， of course。

 edit these things and we can。Delete a position and then add a different position。嗯。Pizza Hu。

And of course we have some code that shows these things with a little bit some queries that put all this together and print that all out and so that's kind of how it works。

 I'll go ahead and delete it and then log out and so that's pretty much how it works up next we're going to talk a little bit about the code and walk through the code。

Okay， so now we're going to take a look at code。And I think I'm going to focus this time on the edit code in other ones I focused on the a code。

 you know the idea is not to give you all the code but to be able to have you work the pieces out together so let's take a look at edit。

This is quite a bit more complex， it depends heavily on the U code。

 I keep moving more and more of the code that's like between add and edit into U just because it's I don't like repeating myself。

And。The head code's important as well， so we'll take a look at the head code And so really I've got jQury I've got some CSsS in here for bootsottrap and jQury and then jQury UI and jquery U I is where this little autocomple thing comes from and I give you this head guy in the in the。

In in the handout so you can just borrow that so again this looks pretty familiar now we' got some mut stuff we got we got the script protecting itself。

 we got handling the cancel button we're demanding a profile ID get parameter right there if there isn't one it just blows up and gets mad and then it basically makes sure that we do have a profile it's also validity checking this number now by reading this across to doing the select for the profile and this end user ID equals the session this is the way to if you'll notice now you don't't you're supposed to do this where if you look at the profile。

 there's also a foreign key into the user table。And so what I'm looking for is I'm not just letting anybody I'm protecting myself that you can't just put a profile and doesn't belong to you。

 that that has to also match。The user I， right， So that's what I'm saying here。

 If the profile I is the one from the。The one from the request and the session ID is the user ID is the one from the session and I'm only going to let you retrieve profiles that belong to you that's kind of what I'm saying there。

Okay。And so this is at this point， you know we're just that was mostly security and checking and making sure and being safe。

 et cetera， et cetera， et cetera， so then we have our post code and we should look familiar the validate profile code。

 validate position that's all in U。There it is the Valdate profile。

And it's basically returning a true or an air string and if it's a string。

 I do the error and if the positions are wrong， I do an error。

 my whole goal is is to make sure that the profiles are valid。Okay。

And it looks like I did not validate the education， so I should do that and I just I guess I should。

And let's do this。Sure的。Validate education。I put it to do in there and it's actually what coders do because we all kind of。

 even this text editor knows that。Okay。Began to update the data。Okay。

 so this is all pretty straightforward， all we're doing is we're updating the profile。

 which is this table right here with the new stuff and that's pretty much the same as it's been the last couple of assignments。

And then we're going to take the position entries for the profile and this is a many to one relationship。

Let's go ahead and change this， let's get two positions in here。1，980。嗯。Pizza hut， save。

So now we got two， let's go back here， browse， we've got two right。

 two positions for a profile this is a this is a many。Physicitionians to one profile。

 so that's a many to one relationship。Okay， so this is the old trick right in the middle of the edit I don't I might have deleted one of these things and added another one and so what I'm going to do is I'm going to delete all the old ones。

Okay， all the old ones and then add the new one so I'm going to wipe them all out so delete from position where profile E equals now we already know that this is good because we tested it way far above。

And then I've moved the code to insert the positions， it's the same as the previous assignment。

 but I've now inserted it into this U code。Here is insert positions。

And it's going to take the database connection and the profile ID and it's just going to loop through these things。

 do if they're there， do validity checking on them and then insert them and in the edit case not we're not inserting and so it's the old profile ID because we already know what the profile ID is it's coming in on that get request right and so that's coming in。

嗯。And we're going to do the same thing for education。

We're going to clear out the educations that hook up to， so if I go into education。

 is there only one in here？Now let's put it another one end。Let's make another education。1995。

 Duke University。Save。So now we should have。so this is a many to many we could have many profiles going to you know many institutions going to one profile and many profiles going to one institution。

 so if we had a second profile in here， then we could add another profile and there could be so that's a many to many relationship and I'll go through that in some detail once I've taken a look at the code。

And so I've got we're still above the line right， we're still in the model code so I'm going to load all of the positions and all the schools into arrays and that is here here is just a select I'm using this fetchch all that you may not have seen before when you have a select that's going to return multiple rows and you just want an array of the rows and each row of course is an array it's going to be a linear array of rows and a key value array is each row you can use this thing called fetchch all and it really is you've probably seen me do this before where just while my way through it looking to see if the row is while as long as the row is not false just keep adding onto to the end of that array but that's built right into PDO。

And you might think， oh that's going to do a lot of rows。

 well you're supposed to use limits and clauses and things to make sure that in any query you're doing you're not bringing back a billion records。

 so dispatch all turns out to be a really useful thing and it replaces four lines of code with one line of code。

And so， you know I'm going to just do the same thing。

 I've got the pulling the institutions in and you can kind of see this when you're looking at the view。

 the view guy， this is the you know that's going to give you one。

 two educations and one two positions and that's what these give you back is an array or each one of these is a row。

 okay？And so in edit， I load them up， I leave them in positions in schools because the first thing you always have to do in edit。

I you have to read what's in the database and you have to render it in forms right so you've got to make this。

 if you inspect this element， we take a look at it。

 this pattern is kind of the same well EU year one that one we haven't done yet。

 so let's look at the positions。Inspect the positions。 So year one， and then。Desk one。

 remember the pattern year one， desk one and then。Position two is year two and desk two。

 and that of course， correlates with。This where we're pulling the stuff out of the post database on  one。

 two，3，4，5， and that's how we're kind of looping through sort of an array of fields as it were where it's kind of an array we're constructing by Kcaation。

 okay？And so if we take a quick look at this education code。

 there's a plus there and let's just take a look at the JavaScript。

 although this should be familiar with to you because it's not that different。嗯。The add pose。

 remember the add pose， we are going to go there and grab the little plus sign and then every time you click it。

 we're going to add a new thing and then concatenate some strings together and automatically count these things up。

So for education， we're going to do the exact same thing， check count them up。

And we're actually going to grab， we're going to do this one a little bit different。

 we've got this EU template， which is just some text in here。hoops。

So this is a pattern for putting sort of hidden text in。

 we make a script tag and I give it ID and a types set of savings type equals JavaScript。

 and now this is just a little string and I'm going to replace this at count。With the number。

 so you see this at count， I just made this up， so I'm doing a string replace， let's go up here。

And I am doing a。Right here， I'm going to grab the source， that is that text down there。

Then I am going to do a replace of at count at with a little number。

 And so it's kind of doing the same thing as this is。 It's just a little。

ItIt's six and one half a dozen in the other， this is kind of ugly and a little harder to get syntactically correct。

 I'm using kind of a template in this second one okay？Okay， so that's， that's how we do that。

 but we also then have to。I kind of skipped ahead here， we have to when we're showing this page。

We have this array of schools and we have an array of positions。

And if there is more than zero schools， we have to loop through and we're going to start with this variable count E toU now the interesting thing is this is a PhP variable for now。

It's the same name as the one we used in JavaScript， you'll see this in a second。

So what I have to do is I have to construct the markup， so when I just display it。

 these markups are coming from PHP looping through the existing things that it pulled out of the database。

Okay。😊，And so。We make the div。If there's some schools， we put out the div EU1。

That's pretty easiest to show the position because you're kind of familiar with that so we have the plus value for the a pose。

 we have the div， you'll notice that let me go down here a bit if there are nothing here。

 we just have an empty div and that's where we'll put the new ones。So I have compositions here。

 and then we put out the div， we give it an ID based on composition。

 we get input type equals text year one， year two， year three， and then we take the old data。

The old year out of the position， and then we take the old description out of the position。

 making good taking care to call each T entitiesities。

 and we construct the J query to get rid of it so we're constructing this little minus sign。

To say go to pound sign position one and remove it， so if I go like this。Position one。

 it goes away poof right so that's generating this。

 And when you go and we do a similar thing for the educations， We have an educational counter。

 we have a little field， we have a little plus another plus guy and then we have a field and it goes round and round and and constructs all this markup。

 So all this markup is coming from PhP。The one， two， three。Eddu year one。Add you school1。

 the school and that's all just strings at this point Val equals University of Cambridge。

 this of course here has been an HTML escaped with HTML entities the way you go so。

When this code is all done right here in the server in PhHP， we have this variable count pose。

Which is the number of existing positions that have come out from the server。

And then we have our form and then going to JavaScript right so we're now we're in HTML so we've exited PhP。

 we're back in HTML， we're printing out the submit form and the cancel form right here。

 save and cancel。And now what we're doing is we're saying count pose。

 this is a JavaScript variable equals and now we drop into PhP of the value of the PhP。

 so I'm going to just refresh this screen and give you a sense of what's going on there。Vi page。

 so this is a trick， This is in effect， trickly passing the results of a PhP computation into a JavaScript variable because I'm going to need that JavaScript variable。

See this。So count pose equals 2， there's two of them and that's coming from here is's just this little two is the number of things that were generated from the PhP。

 so the PP goes like that， it generates the one and the two。

 this is probably an easier way to look at it， right。And then position one and two。

 and then this way， it means that when we hit the plus button， so I haven't hit the plus button。

So if I hit the plus button， it's going to be number three。

So if I hit plus and inspect this because countpost starts it too and the first thing this JavaScriptscript code does is adds one the countpost。

 Now we're in JavaScript， and then it builds this new div。

 So thats this is the new div and these were the old two divs and they looked the same。

And if I do an inspect element， you will see that this is year three。

And count poses four at this point， so if I hit it again， it's going to be year four。

If this plus again， then this next one down here is going to be year four。

I haven't submitted anything， I'm just kind of playing with a Do object model at this point， okay？

And count Edu a Edu is doing the same thing it's just instead of doing this。

Ugly careful string incatenation， it is making a template。

With this at count that I just made up to be the substitution point for that little number。

 whatever that little number is。Okay。😊，Okay， so that's just that really had nothing to do with JSON。

 which is one of the things and so。The JON part。诶 os。The JSO part。Is kind of simple and boring。

The JO。Is。JaQury。😔，Autocomp。So I'm used to using this J Co autoo complete widget。

And this is how it works。You can have a tag， just an input， and then you basically say， hey。

Let's hook this up and go to this tag and autocomplete with this source of the list now this one is showing a list in a JavaScript variable。

 but you can also make the list come from a PhP file that goes into the server。

And I mentioned this way， way way at the beginning， so let's review this。And so let's take a look at。

Let's go and make it fresh。Let's add an education。2001。So now。View developer console。Network。Okay。

 so。So。And you school。Has class equals school。Okay。Class equals school。 So every one of these。

Text areas that I want to have autocomple working on， I've put a CSS class on them。

And then I can in a single JavaScript line。Well， three JavaScript lines。Say hey， JQuery。

 go find all of the tags with school Class equalal school and make them autocomplete fields。

 and the source of the autocomplete data is this on in serverver PhP script called school。phP。

So here's Schooled dot PhP。It does a select。With a light clause。And it uses a percent。

 so that's like U N percent， and then it sends it back in Json， so it retrieves all these rows。

 pulls out the name of the school。 remember that the institution looks like this。Looks like this。

 here's all the names of the schools right， remember Lansson Community College I added because I put that in because you can cause it to add a new one。

Okay。😊，OhIt's a complex one， isn't it， it's a complex one， that's why we' near the end of the class。

Okay， so。If I type。L。It sends a request， I didn't， I had to build this PhP code。And it says。

 go do a select and give me all all the institutions in the system that have L as the prefix。

And then all this other stuff。That was all done by JQury and JakeQu UI， all that pretty UI。

 I didn't make any of that， and now this is now simply a text field。So if we inspect this。

It is just a text field， the values for some reason not really here， I don't know why that is。

 but that'll get fixed before we hit the submit button。So now what I want to walk you through。Is。

The submit button here。So let's also add another one， no， not a position， I didn't want that one。

Goododbye。Let's add another education。2005。嗯。School of driving。So that doesn't meet any criterion。

 as a matter of fact， if we did a view developer console。I'm I should showed this as it was going。

Let's。Look at the network。School of。So it said， oh what starts with school of and the answer is nothing starts with School of。

 which is okay， we're still allowed， it's just a text field， school of driving。

So the way this works is this is going to be a many to many。 so we know that Lance。

 I'm going to hit the save in a second here and show you what's going to happen。

 University of Cambridge already exists。 Duke University already exists。

 Lansing Community College already exists。 School of Dring does not already exist。

And so let's take a look。So school do PhP was just to get the UI when we hit the submit button。

We're going back to edit。 PhP way at the top， way at the top， way at the top。Insert educations， okay？

So it's like you've got Edu year one， school name one， Eddu year two， school name two。

And this is going to do all that stuff， and again because we're in the middle of an edit。

 we already know at the profile ID it's 11。We're also going to use the trick。

To delete out the old entries， right， we're going to clear out the old position entries and the the the not the position entries。

That's a typo。We're not cleaning out the institutions， we're cleaning out the education entries。

 these institutions are still here， the education entries are the entries that map from a user to a school that indicate that they're at that school。

 by the way and we're modeling the year as data， we'reing the year as data on that many to many link。

Okay， so let's go to In Educations and take a look， this is probably， well。

 this is the most complex thing we're going to do。So we'll make our screen bigger。

And we'll make our text smaller。Because。Okay。Insert positions， not too bad。Right。

So here is the insert educations， it's got a little more to it。

So the first we're going to go through， we got these Ed you got this post date of Eddu year one。

 Eju school one， Edju year two， Edju school one， that is。This data， Edu year one， Edju School one。

 Edu year two， school two， if it's non blank， if it is blank， we're going to sort of。

 I guess we're not even doing validations because we already we should have validated it before but we didn't do it yet that'd be something you can do is add cool validation。

So the key is is we got this variable school， which is the string name school。

 which is like Duke University so what we're going to do is we're going to look up in the institution select。

Institution ID from institution where name equals name， so where name equals Duke University。

 so we're going to go an institution。Were equals Duke University and we're going to find one and so we're going to get a sixth there so we're going to be good so that basically says and we're going to do a fetch now remember if it does not there in SQL that's not a bad thing Ro becomes false。

 but it's not like a failure you said give me the record that where this is true and the answer is there were not that's a valid answer okay。

So if the row is not false， that means we got a row。

 well we know what the primary key of that institution is， which is six。

 so that means that institution ID is going to be six。In the case where I just typed in。

The School of Dr。Institution ID is going to still be false right we set it to false and we didn't set it to a number。

 then I'm going to do an insert into the institution。

And so I'm going to insert the institution table。So I'm going to add one to this。

 I haven't hit the button yet， so it's not going to do it， but there'll be a new one added。

 It'll get the number 11 if all goes well， and Im want to ask PDO because I just did an insert and say。

 layh， what was the institution that you just inserted was the primary key In this case， it'll be 11。

And so at this point， by this line right here。I either have looked up the old institution or inserted it。

 so I don't exactly know nor care which of those two things happen。

 but I do have this variable institution I D that I know is the primary key of either the old institution that was already there or a or one that was。

Just recently inserted。 So that's pretty cool。 remember。

 rank is just my little way of having a sort order。If you go over here。

 I just make those go up by one， two， three， four five。

 so I know which order they are in case the years aren't in order， I don't want to order by year。

 I'm ordering by rank。Okay， so。Profile ID it's a many to many right profile ID institution ID year came from the post data and rank is the little number and we're done because I've got that working so let's go now and see when I hit this button what's going to happen。

You'll also see that well actually these guys are going to get deleted but then they're going to get reed because there's no primary key being built here。

 this is the many to many table that's pointing to two primary keys。

 a primary key in profile and a primary key in institution so I'm going to hit the button I've I've been threatening to hit the button now Im going to hit the button clunk。

Okay， so now what we should see。Is these should be the same。

 We should see one more because we are do we add two more， I don't know， We added two more。 Oh， oh。

 Lensing Community College and then 11， if you look at 11，11 is the School of driving。

 and if we look in the institution table， we see that it inserted an 11 school of driving。

 so it ran this if there was no institution insert it So we ran it， we got back this 11。

 the 11 came back here in P insert last insert I。 So that's really good and then we inserted。

This record， the 1111 profile I 11 institution 11。 and so now there are four。

F education os come back， floor educations， and so we see four educations and it all works。

So that's a bit of a walkthrough of this really complex and important thing where we're starting to show as we go forward。

 there'll be increasing ways to use JSON to backend what we're doing in JavaScriptSt and changing the UI。

 so I hope you found this interesting and I hope you do well on this assignment。



![](img/2dd83b7f3251c2de00df4387ebb9a33f_1.png)

![](img/2dd83b7f3251c2de00df4387ebb9a33f_2.png)
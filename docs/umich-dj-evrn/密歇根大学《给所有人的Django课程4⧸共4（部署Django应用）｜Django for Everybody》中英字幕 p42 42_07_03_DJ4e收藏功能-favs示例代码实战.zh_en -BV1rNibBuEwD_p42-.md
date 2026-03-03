# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p42 42_07_03_DJ4e收藏功能-favs示例代码实战.zh_en -BV1rNibBuEwD_p42-

Hello and welcome to another of the sample code walkthroughs django for everybody。

 This particular sample walkthrough is the favorite things。

 You can see the source code here in favs hopefully you have like I do the whole source code of this entire DJfr samples checked out somewhere。

 maybe on your local computer or maybe on a separate python anywhere website in a way that you can watch it。

 And if you don't have that， you can play with these samples here at samples djfr e do co。

 I'm going run my a local copy。 So let's talk a little bit about what we're doing。

 We're really demonstrating many to many accounts。 but in this case， we're also demonstrating Ajax。

 and I can show you how Ajax works at a high level。

 So normally if I click on know raindrops on roses and all things。

 you see an entire request response cycle you see lots of things going on here。

 and and if I click on this I go up to here this。

![](img/93f7b6f482b038f42d521918ac98ff02_1.png)

![](img/93f7b6f482b038f42d521918ac98ff02_2.png)

![](img/93f7b6f482b038f42d521918ac98ff02_3.png)

The very first page is a bunch of HTML that came out and then the rest of it is like bootsottrap。

 et cetera that was loaded by that page and but so you have to kind of scroll back up。

 but now I'm going to clear this， I'll go back to all things。

So that was one page with lots of sort of derivative stuff。

 But what we're going to do in this is when we hit this favorite button we're not going to see a full screen refresh。

 we've got some JavaScriptscript code in here that's going to make this when I click on it's going to make it filled in。

 but it's also going to have to update something in the database so that it remembers that this is one of my favorite things for the login user so I'm going to hit it。

And you see that I hit this favorite and that called a view inside the server。

 which updated the state。And now if I refresh the whole page， it's going to show it to me。

 and it's remembered this， right， so I refresh the entire favorite list。And if I knew add a new one。

 whiskers。On kittens。This is just a normal bit of code that's not that different sound of music。

So like this one I've got a favorite， this one， I don't have a favorite I don't have that favoriteed。

 And And so but Ajax is the way that we can both。 well。

 it's just jascript and J query that's updating the UI。

 but we can change data on the server by just hitting a URL in this case with a post request。

 So we do if we look at this， it actually sent a post request。 if you recall。

 we're not supposed to change the server state on a get request。 So this is to not be tacky。

 we're going to send a post request And again， if if you see this in the source， which we will。

 you don't want a a。Spider to go down these get requests， they'll see these URLs in the jascript。

 we just hope and they won't do it because they see it's a post request。

 So it's so if I hit refresh now， the data has been updated So if I take a quick look at the admin user interface。



![](img/93f7b6f482b038f42d521918ac98ff02_5.png)

![](img/93f7b6f482b038f42d521918ac98ff02_6.png)

Yish。A min。And I look at faz。 This is my。This is my many Well I'm just gonna stay here， right。

 So this means that the user DJ4E likes raindrops。 And so if I do a refresh here。



![](img/93f7b6f482b038f42d521918ac98ff02_8.png)

So that means that me， the logged in user， DJ free likes this。 Now。

 if I say I would also like whiskard on kittens。

![](img/93f7b6f482b038f42d521918ac98ff02_10.png)

It's going to update the database。 See there。 And then if I come over here， I can hit refresh。

 and you see that Dj48 likes raindrops。 And it's just a many to many table with an outward outward connection to raindrops on roses and another outward connection to the user DJ 4。

 Now I'm going to delete this。I'm going to delete this from within the administration。Now。

 this is exactly。

![](img/93f7b6f482b038f42d521918ac98ff02_12.png)

What the unlete button does Now， the state of the system doesn't know that I deleted this in the background。

 But if I hit refresh。You see， it now knows that it's deleted because it actually went and it queed all those tables。

 And there was really only one favorite。

![](img/93f7b6f482b038f42d521918ac98ff02_14.png)

![](img/93f7b6f482b038f42d521918ac98ff02_15.png)

So let's take a look at the the way this kind of comes together。

 We will eventually get back to all this jascript。 So let's start with。The models。The model。 Yeah。

 so thing， of course， has some title， like a lot of things， some text。

 we have a foreign key into odor owner because we want to be able to mark these things as belonging to somebody。

 This owner right here indicates who owns it。 I。e。 who will get the edit and delete just like everything we've done that does that。

 Fs is the new bit we're adding。

![](img/93f7b6f482b038f42d521918ac98ff02_17.png)

And so we're basically saying， okay， we're going so this foreign key is a one to many right because that's one user to many things。

 but this is the many to many。 And were this is also to off user normally many to many is three tables。

 you know the kind of the left table， the right table and the middle table。 Well， in this case。

 we got the ones table， but the right table as it were， is the user model itself。

 and that's okay because the user model is a table and all we're doing with sets the settings that off user model is knowing what table that is。

And of course， the created ad and updated ad and the title that does。

So this is our through model and of course when you're in the middle of a foreign key。

 you effectively have a foreign key to the left and a foreign key to the right and so this is like we have a foreign key back to thing and that's a one to many relationship and then we have a foreign key to the users and that's a one to many relationship。

In this case， the ondte models equals cascade means if a thing is deleted and theres a favab row that references the thing。

 the fav rows that reference the thing will be deleted。

 And the same is true for if a user gets deleted all the fav rows except So either side。

 either left or the right of this， we could if one of those records goes。

 the corresponding records and fab will be deleted。

 And you can either delete things or you can delete users。

 And the fav rows are sort of automatically maintained。

 Now the one thing we're doing here is a little different than what we did in the comments one is we've added this unique together。

 And that simply means that you can't insert more than one combination of a thing in a user。

 So it's not like you can favor it a lot。 if you keep hitting favorite。

There's only one row if there's a row in here that exists。



![](img/93f7b6f482b038f42d521918ac98ff02_19.png)

I。e。 right here。 If this row exists and it connects the two， then it's favored it。

 So in the other examples， you'll notice that we modeled something at this connection。

 This is really a pure many to many。 And this unique together basically says the only data that matters is the actual connection between thing and user。



![](img/93f7b6f482b038f42d521918ac98ff02_21.png)

![](img/93f7b6f482b038f42d521918ac98ff02_22.png)

And this is just kind of a little fancy way to make it so that the admin user interface looks really cool right。

 DJ4E likes whiskers， that's just that's what you're doing with these string classes。



![](img/93f7b6f482b038f42d521918ac98ff02_24.png)

![](img/93f7b6f482b038f42d521918ac98ff02_25.png)

Okay。So of course， you'll do your migrations when you get that that's already taken care of。



![](img/93f7b6f482b038f42d521918ac98ff02_27.png)

Let's take a look at a couple of things， let's just start with URLs。pyy。

Make it a little smaller so it sort of fits better， a little wider there we go。



![](img/93f7b6f482b038f42d521918ac98ff02_29.png)

So this looks very similar to a lot of things that we've done。 We've got a main view。

 we've got a detail view。 we've got a create view。Delete view。

 So those are all sort of we've talked about those before and we've used those。

 This is the new thing here。 And so this is， this is the URL that we're going to hit。

If we're going to do a favorite or an un favoriteavorite and it is the primary key of the thing。

 and that's why I name this thing slash thing primary key。I'm might want to call that thing Pk。

 and then favorite。 right， And then that's going to call the add favorite view。 And， of course。

 this thing favorite is just a way to reference it in templates and in views。

 And the same thing for unfavorite。 And so we've got a little tiny a favorite view and a delete favorite view。

And in terms of this， the only real code that we're going to change from previous examples is the list view because the list view has to be augmented to actually show the little asterisk。

 and the list template has got to be augmented。 And matter of fact。

 the most complex bit of this is the list view。 And these two have got to be edit as well。

 So let's take a quick look at the views。

![](img/93f7b6f482b038f42d521918ac98ff02_31.png)

![](img/93f7b6f482b038f42d521918ac98ff02_32.png)

I go ahead and CD templates slash favs。 So let's start with our list view。Okay， and。Qhu。😔。

Go a little larger。 There we go。 Here's our list view， And let's take a look at our list view。

 So the first thing is， because of that owner field。

I am going to import the owner detail view owner list view and owner create view。

And so I've got that and actually I'm importing it from a different。

From a different project that's okay。 this owner dot Py is in the My arts。

 but you might have it also locally， it be owner do Py so。So again， the whole I D here is。

 is that the owner field in the models， V I models dot P I， this owner field。Is managed。

Like in many of these， by us creating。My do sMy arts。Owner。

And basically we're creating this owner list view， the owner detail view， owner create view。

 and if you recall from these， these are the places where we've kind of overridden the original automatic create View automatic update view。

 which we've used for lots of things， except when we're creating it。

 we've got to put the request user in right before we split the save into two pieces and then we half save it。

 then we put we set the owner field then we finished the saving。

And then the update view and the delete view is more about the query set， and it basically says。

 I'm not going to let you retrieve this for update。 That's what query set is。

 I'm not going to retrieve， let you retrieve this for update unless you own it。

 And so that's what this is basically saying is I'm going to also filter these based on the owner must be equal to the current logged in user。

And this code right here， this code right here is exactly the same for delete。

 So what we're doing is loading the delete loading the record prior to delete。 and we're saying。

 look， if you don't own it， I'm not going to load it。

 which means you can't delete it because it gets a 404 not found。 And so again。

 thats that's in the delete view and the update view。

RightThat's all here because it's going to do a get or 404 right And so in there it does a get 404。

 again， this particular when we got to do our own get or 404 and inside delete view and update view it's going to do a get get or 404 Git object or 404 and then this code right here if if it's like Id equals primary key and owner equals selfdot request user。

 the answer is no， And so you're this is going to blow up this delete view and update view。

 Now that's just a review of stuff we've been doing for a couple of examples。

 So I'm not going go into super great detail。 So what I want to do。

Because I want to show you a thing list view。Now actually does owner list view。

 but if you go back and look at owner list view， it doesn't really do anything other than the base one。

 but。So its basically looks like most of these， except what we've done is we've overwrittenden the get request。

 so this we're overriding the get request。And some of this is the stuff that's part of the default。

 meaning it always would go get thing list to objects dot all。

And it would always pass into the template thing list and if you take a look at the template right what it does is it checks to see if there's a thing list。

 then it loops through it and then it prints all this stuff out and literally a lot of this is very similar to everything we've done with previous sample code right。

But the problem is， is we need to get the data so that we can know the starting value。

 whether these are supposed to be filled in or not， right。And so what we do is we say， okay。

 and we only going to do that if they're authenticated because this if we're not logged in。I log out。

I don't have any favorites。 I can't un favoriteavor thing。

 I can't favorite things because I'm not logged in。 And so there's I don't do this， right？

 So I if the users authenticated， then I'm going to do this。 And it also means that in the template。

All of this stuff， this is the favorite code only happens and only shows if the users authenticated。

 So I'll log in the J 4 E。

![](img/93f7b6f482b038f42d521918ac98ff02_34.png)

![](img/93f7b6f482b038f42d521918ac98ff02_35.png)

Log in and now it's actually pulling this extra data and so here we are in views if the users authenticated。

 let's go to the current logged in user and get a list of their favorite things。

 but only the ID field。Now this would give you a list of objects and each object would be ID colon 1 ID colon 2 ID colon 3。

 And so we use a bit of list comprehension so that I end up with a favorite that's just a list of the IDs of the things for which I have a favorite So in this case if this is like thing one and this is thing4 And so in this list that list will be just four because four is favoriteed into one is not so I might have 50 of these and you might only have two of them favoriteed And when it's all said and done。

 this favorites list if you printed it out let's print it out。



![](img/93f7b6f482b038f42d521918ac98ff02_37.png)

![](img/93f7b6f482b038f42d521918ac98ff02_38.png)

Print favorites。Brint that out。

![](img/93f7b6f482b038f42d521918ac98ff02_40.png)

And you will see。Let me hit refresh here and then go over to my run server。

 and it's a list with the number 4 in it。 So for。

![](img/93f7b6f482b038f42d521918ac98ff02_42.png)

![](img/93f7b6f482b038f42d521918ac98ff02_43.png)

4 is a favorite and one is not a favorite。 If I hit this and then I hit refresh and I look at this print。

 you'll see that 4 and one are my favorites， right？ And then if I unfavorite4 and I hit refresh。

 you will see that one is the favorite， okay。

![](img/93f7b6f482b038f42d521918ac98ff02_45.png)

![](img/93f7b6f482b038f42d521918ac98ff02_46.png)

![](img/93f7b6f482b038f42d521918ac98ff02_47.png)

Now， that then drives into that and that just is passed right here into the template。



![](img/93f7b6f482b038f42d521918ac98ff02_49.png)

And then we have this new stuff in the template。 Now。

 we're in the middle of looping through all the things， which this is the loop that goes through。

 all those things。 But here we are in the middle， if the user is authenticated。嗯。And so。

 we basically have some。Code anchor tag H F equals pound sign is our key that says don't actually go anywhere。

 And the on click is the method。 And that's going to call some jascript。 and it's going to call。

As a parameter。 So I got a single quote here， the URL for the thing un favoriteav of thing I D。

 And I'm also passing thing I D as a parameter。 So if you do a quick inspect element right here。



![](img/93f7b6f482b038f42d521918ac98ff02_51.png)

Inspect element， you see that on click fav post， This is the a URL to hit。 and that's the I。

 So I'm passing those in as parameters and then return false。

 We'll go through that jascript in a second。 And I also give this on Id so that I can reference it down in that function that I'm going to build in a second so that's here。

 Id equals favorite now。

![](img/93f7b6f482b038f42d521918ac98ff02_53.png)

I need to decide whether or not， to show。Which of these two to show。

 So it turns out that there's actually two stars。 And what I'm really doing is I'm showing one star or the other。

 You don't notice that。 But if you look down here， there are actually two stars。 here's one star。

 and here's the other star。 So there's actually， if you， if you， you know。

 if I can see if I can convince it。Mhhm。If I can convince the。Where is， oh， it's got to be here。

 display none。If I can change this to be display in line。You'll see。That there's really two stars。

And all I'm doing now this is not gonna be much。 this is not going work。

 I don' know how well this is going to work because I'm manually on to hit it。

 but there's actually two stars， right， But what happens is is that I hide the star that's filled and show the star that's filled appropriate。

 So let me refresh to get it so that。 But there's two stars there。1 is hidden and one is not。

 So it turns out that what this is， is this is2 bits of making a star。

 And all I'm doing is I'm stacking two stars。 I'm stacking an orange star on top of a blue outline star and。



![](img/93f7b6f482b038f42d521918ac98ff02_55.png)

But then what I'm doing， I'm doing twice。So that's a link。But。

What I'm doing is if the current thing is in the favorite list， remember I did that。

Then I'm going to add a style equals display none。And if， in this case， that ones。

 if it's not in the favorite list， I'm going to hide this one。Right， this is the unfavor。

 and this is the favorite。 And if it's in favorites。I'm going to hide the favorite。 So I。

 if it's already a favorite， I'm going to show the empty star that's got an unfavorite link。

Show empty star。I mean， show a full star with an unfavorite link underneath it。

 my mind gets all messed up on this。 And then if， if it is in favorites。

 show a filled in star with an un。With an unfavorite。Yeah。Yeah。It was not in favorites。Oh， right。

 I I got， It's almost a double negative， right， If it's not in favorites。Hide it。

 So this kind of flips。 but okay， so this is。This is an empty star that if you click on it favorites it。

 and this is a filled in star that if you click on it unfavorites it。



![](img/93f7b6f482b038f42d521918ac98ff02_57.png)

Okayay。So let's take a look at this now then there's the tricky bit。

The trickyy bit is that when you click on the one that you can see and in this case。

 the 1 I can see is this one right so I'm here， I can see this one。

 so it's going to click on fav post passing in f thing unfavorite where that is the key of the thing Here's the whole thing right and passing in that number We'll see what that's for in a sec。

Okay， so now I'm going to switch to the JavaScript that handles this。Kay。

So now we' got this function fab post and you don't have to modify this。

 so this is the URL that we're going to post to， we're actually going to send no data to it and then T ID is are so we can have a number。

So this fetch is built into the browser， you may have to do what's called a polyfill for fetch if you have a really old browser but。

We don't。 And so those are called polyfills， things to say like， oh。

 this is Internet Explorer10 or whatever， and I mean X。

 So fetchch basically takes the URL and then a object with method post， ya yada。

 you can go look all this up。 You don't have to worry too much about it。 content type。

 And I'm not sending any data。 And so this is a post with zero data。

And then the way this works is is this fetch function starts the fetch。

 but then it delays it because it could take a long time to go across the internet。

 go through the server and come back。 And then what it does is it comes back and then calls this function。

 when the response returns back to the browser。 So this is the browser talking to the server。

 and then you split your code into two parts。 The cart part that gets it started。

 and then the part that， in effect asynchronously reacts to the finished。 So that's why I'm saying。

Log finished。 So you see， oh， it finished。 And then the next thing I do is I'll go grab those two little stars and I flip them。

I hide them。 If they're visible， I hide them。 And if they're hidden， I make them visible。

 So unfavoured star thing I D， which means it comes back to this little guy here。

 And it just toggles them。 So when I do this， it's actually hiding one and showing the other。

 hiding one and showing the other。 I could have done this with differently。

 But that's really what's going on。 And you can see the display none flipping back and forth down here。

 as I flip it。 And， of course， it's also changing it in the server with the post request。

 So if I sit here and I look at the network。And I go。On favoriteavorite， favorite， un favoriteav。

 favorite。 And that's because as I'm showing it and hiding it。

 it's also toggling what happens when I click on it。 If， if this is shown。

 then it's going to call unfavorite。 Oh， this is now shown。 It's going to call favorite。

 So the empty star is going to call favorite。 and the filledin star is going to call unfavorite。

Pretty cool， huh？I mean， you could probably come up with some better HTML and。And so again。

 if you look at the console， this is quite nice。 I got some debugging here， right， favorite。

Favorite finished。 So that's actually going on here after the network shows when they start。

Start now that finish so fast is hardly whatever。 But then this shows when it' finished。 Okay。

 and so that that's how you debug this。 Now， you might have problems on your own code when you're doing stuff like this。

Okay， but in this， you just don't have to change much。So that is probably the hardest part of this。

Then the last thing that we've got to do is we've got to go into the views。

tpyy and handle these posts to Favab's thing favorite finished。Right so we got to hit the posts。

 So if you take a look at。嗯。URLs， Im probably going to need models。Keep models up。URL， dot P Y。

So this is the routes。 So it's really simple。 Remember this thing。Is the primary key of the thing Id。

 not the favorite I D。 F does have an Id， but we're not really using it。

 We're using the combination of the thing I D and user Id， basically as the index in the favorite。

 So we go find favorite view。It's down near the bottom。

And so if recall most forms we require CSRF and there we could have put the CSRf in here。

 but it was a lot simpler to just make it CSRf exempt。 You kind of have to decide on security。

 whether or not it's okay like I could write a code injection that would favor a bunch of books for you。

 Is that really that dangerous。 But you could make this more secure。

 But what I did is I made it CSRF exempt。 Okay， And so if you go read the stack overflow。

 you have to。You have to import these things and then add this little thing that basically says， hey。

AndWe are not going to blow up CSRF。 if you don't， these things， these things will get。403s， I think。

 which is not allowed， but you don't want that。And then after that。

 this looks like pretty much any other thing。It's a login required mix in。

 which basically means a session has to be established。

 We' are not really caring it Well just extending a normal view。 turns out there's no Ui to this。

 If you look at the response， the response is empty， but that's okay。

 because the damage has been done in the server as a result of the post。 So we got a post method。

 We're overriding from view。 And we're taking self in request， which we always get。 And P K。

 of course， which is the second number， right， I guess it's in URLs。 right。

 Pk is whatever this second number is， it's that parameter。

 we get Pk is the parameter comeback views。 There we are。



![](img/93f7b6f482b038f42d521918ac98ff02_59.png)

![](img/93f7b6f482b038f42d521918ac98ff02_60.png)

![](img/93f7b6f482b038f42d521918ac98ff02_61.png)

![](img/93f7b6f482b038f42d521918ac98ff02_62.png)

Print some stuff out。I'm going to load the thing that corresponds to the PK or blow up with a 404。

 right so you can't just guess， I can't just say you know two I can't。

 if I pick a PK that doesn't exist， nothing happens。

And then what I'm going to do is I'm going to load the old favorite。

I I'm going to create a new favorite and I'm going to put to the left and the right the user value of favorite。

 right so we're setting these two parameters right here。



![](img/93f7b6f482b038f42d521918ac98ff02_64.png)

![](img/93f7b6f482b038f42d521918ac98ff02_65.png)

Setting thing and user。So thing is being set to the current thing we just loaded。

 which is got a primary key， and the user is the current logged in user。Now。We're going to save it。

 but we're going to do it in the track set block because what if there's already one there。

 And if you recall， you can't， because of unique together。

 you can't save the same combination of thing and user twice。

 And there's other ways I could have done this that a little more complex， but I kept it simple。

 I just tried to try and and said it's okay if it blows up， that means it's already there。

 that because I don't， I don't let you really hit the favorite twice。

 But if you somehow could like click on this。 If I could do an inspect element。



![](img/93f7b6f482b038f42d521918ac98ff02_67.png)

And。Okay， and like。So that so we're unfavored。 So， but I could unfavor it twice， right。

 All I'd have to do is somehow convince myself to grab this URL。 It's not favoriteed it。

 And you think， oh， don't do that。 Well， the user can always like。

Hand put this URL and I just unfavored it。What I do Ron， Oh， too many favs。咁 back。

That's a second unfavorite， but I don't know why that didn't I that blew up。 Well。

 let's stop playing with that。

![](img/93f7b6f482b038f42d521918ac98ff02_69.png)

Let's see。 Did a complain in my thing。Fang。1， un favoriteav。嗯。F stain。



![](img/93f7b6f482b038f42d521918ac98ff02_71.png)

Oh， oh， I know why。Da。

![](img/93f7b6f482b038f42d521918ac98ff02_73.png)

I'm doing a get request， there is no get request， come back， come back。Yeah。

 you can't always put it in a browser， make it work， teach me a lesson， right， there's no def get。



![](img/93f7b6f482b038f42d521918ac98ff02_75.png)

And I can make it work， but that's a get request and so it's like， sorry。

 there ain't even a get request here。Okay， so high level， we get the things primary key。

 we load the thing， we create a link， we create an object to put it into fab with a two pieces and we try to save it and don't really care if we've inadvertently double saved it because our UI is sort of keeping us from causing that to happen。

 okay。So that's the favorite。The delete favorite is even easier。Right so in deletete favorite。

 we're CSRf exempt， we're doing we have to be logged in because if you're not logged in。

 then request user is going to blow up， this lines going to blow up because request user is not necessarily set if you don't have login required。

 so that's why we drop login required mix in right here。And then we load up the old thing。Wei。

And and that's， that's because we need to put it in this effect filter。

 So this is a like a wear clause in SQL fab objects get user equals the current logged in user and thing equals T T was the primary key of that thing。

 So if we can get it。Then we delete it now。

![](img/93f7b6f482b038f42d521918ac98ff02_77.png)

If again， somebody manually found their way to the unfavorite button。

 even though we've hit it cleverly， they could still find their way or a web browser might find its way。

 We're like， okay， we try to delete it。 It's not there What， there's nothing bad。

 We'll just kind of fave not。 We'll just， it does not exist。 and we're going to pass。

 And then we return an H TV response， which is in effect emptiness。 So when we come here。

 go to the network。

![](img/93f7b6f482b038f42d521918ac98ff02_79.png)

Refresh， clear everything。Unclear it。 right？ There is nothing there。

 So we return an H T T P response， but the most important thing is， is that we sent back at 200。

 So this， you know， implicit when you're doing this is there is a 200 going back。

 And so it is successful。

![](img/93f7b6f482b038f42d521918ac98ff02_81.png)

Okay， and so I think that this is pretty much all I have to cover on this， how to build a favorites。

 the quick way to test this is you know you should be able to turn these things on and off and watch the network tab and then if you hit refresh。

These two things， the state of these should be the same。

 meaning that you've properly recorded them in the database。 So when I had it breaking， you know。

 I would hide it and then I would refresh it and the little little little orange star would come back。

 So I hope this was helpful to you。 a helpful little walk through going through the the favorite sample code。

 cheers。

![](img/93f7b6f482b038f42d521918ac98ff02_83.png)

![](img/93f7b6f482b038f42d521918ac98ff02_84.png)
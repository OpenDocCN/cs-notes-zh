# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p05 -05-MIT web.lab (6.962) - Day 1_ Workshop 0 (HTML_CSS).zh_en -BV12Ux5zTE9p_p5-

Hello again， everyone。 Hope pizza was good。 We're going go ahead and start on our first workshop now。

😊，Yeah。Yeah， so our first workshop is， so as Andy mentioned。

 we're going to be working through building this catbook website。

 and this is gonna to be our first step。And we're going to use some of the HTML CS S ideas that we talked about earlier today。

So for today， we're gonna be using both V， S code and the terminal。

So if you could go ahead and open those up。That would be great。If you haven't set up everything。

You can go to Weblabs do slash homework 0。And get that set up real quick。And as always， if there's。

Questions， then go to the queue。Okay cool， I'll move on then。Okay， so first。

 we're gonna open up our terminal。 I'm just gonna use the terminal on B S code because I think it's nicer。

😊，But yeah， use any terminal that you'd like。 If you're on Windows。

 make sure you're using the Gitbaash terminal。And I think Abby showed you how to change that。Okay。

 first step， we're gonna change directory into whatever folder that we'd like。

 I'm just gonna choose desktop， but you can also make a folder if you'd like， like using M M K D I R。

Call a web labb or something。Yeah。Move into whichever folder that you'd like。At the moment。Alright。

 now we're gonna to clone the repository。嗯。Steps for this are pretty simple。

You'll go to this site right here。I'll open it up。那'次。Its weblab dot is slash catbook。

I'll leave it up for a moment that everyone can get to it。给。Everyone good。过。Alright。

 once we're on the page。And can click code here。Once you're on the page， click the green code button。

And then， we're just gonna。Copy。The command here。Or the link。Iapppy that。😊，是。啊。All right。

 once that's copied。Then or we go back。Or has everyone gone to that page and copied the link？Okay。

 then you're gonna type in this command here into your terminal。

So get clone and then can copy paste the link。And then， you should see。Some messages。Resolving Dltas。

And that should mean it's cloned。I'll wait for a second。Want to get up there。OK。Alright， next。

 we're gonna move into that directory。So once again， use that command。And then in your command line。

 you should see you're in catbook react。Alright， and then we're gonna type in this command。

 get check out。W 0， starter。And it should say that you switch to a new branch。It easier to starter。

All right， does everyone good with that。Okay cool。

![](img/139f1f3dcd8d4d8d767115084154b7c0_1.png)

Then we're going open up that folder。You can do this easily on V S code， go to open。

 It'll be in desktop。Yeah then。

![](img/139f1f3dcd8d4d8d767115084154b7c0_3.png)

And Kappa react。And you can just click open。

![](img/139f1f3dcd8d4d8d767115084154b7c0_5.png)

And then if you want to open up index to HTML T L， drag it out here and then。

That's something that looks like this。Before we dive in。

 we're going to encourage you to do some nice formatting。Foraing is good， obviously。

 because it'll help you read your code better， especially when you're collaborating with other people。

 you want to make pretty code so that other people can like easily understand where your project is at。

😊，Thankfully， we can use an extension that will do most of this for us。

So we'll go ahead and download that。It's called prettier。And I'll show you how to get it。

So once you're at this page in V S code。Go to this icon right here。Extensions。

And you should see something that looks like this。Once you're here。Can just type in prettier。

And there should be an install button here。 I already have it， so。I'll show up。

 but go ahead and install it。Okay， once that's done。

 then we need to change the settings so that it's in use。So。You go down here， click the gear button。

And then there should be a settings。Oion。Quick settings。



![](img/139f1f3dcd8d4d8d767115084154b7c0_7.png)

And then you're gonna want to search for formater。

![](img/139f1f3dcd8d4d8d767115084154b7c0_9.png)

It should have some default option， but you want to change it to prettier。

And you can do that just by searchinging through the。Alright。

 we also need to change it so that it formats on every save。So that means every time you press。

 like control S， then it'll automatically format your code。Which is really nice。

So we'll type in format on save。In here， and then you just need to check this little box。Alright。

 I'll wait for a moment。All right， is everyone good。And again， if you're behind。

 then just feel free to join the queue and we'll be ready to help。Alright。

 here's a little demo of what Perttier does。 Yeah， if you control S。

 then it looks much nicer and much easier to read。Understand what's going on。

So let's go back and look at the code。Should have something similar to。What's on here。And。

If we'd like to look at the actual sites。This might be annoying。Then what you can do is。哦。喂。



![](img/139f1f3dcd8d4d8d767115084154b7c0_11.png)

![](img/139f1f3dcd8d4d8d767115084154b7c0_12.png)

Let move this。呃。啊。

![](img/139f1f3dcd8d4d8d767115084154b7c0_14.png)

Okay， but basically to view the file， all you need to do is navigate to。The folder。

And like finder or whatever， using Windows。You can drag it up。Here。And。It should display。

Whatever the website is rendering。So as you can see。

 we only have hellello worlds and then are titles catbook。It's pretty much what we expect。

And it's up there。I'll let everyone try that out for a moment， before we jump in。So again。

 all you need to do is go to finder。嗯。Navigate to the folder for your Cap react。

 and then just drag in index the H into your browser。 and then it should pop up the web page。哎，啊，录长。

Okay， so looking forward， our goal at the end of this is going to be able to build this profile page in Kabook。

 So this is our goal for the end of this workshop。😊，Okay， before I begin。

 I'll explain like a little bit about our workflow for the workshops。

So the idea is gonna to be that I will explain like something that we want to add to our website。

You guys can talk with your friends for like a minute or like five minutes or so。

 Try to implement it yourself。And then we'll come back。 We'll touch base。

 and then we'll implement it together。嗯。Yeah， and if you get lost or fall behind， don't worry。

 because we have some things thatll help you stay up to speed。But yeah。

 buckle up because we have 11 steps in this workshop。 So it's kind of a long one。But， yeah。

 we'll get through it together。Okay， first it's just gonna be doing some work in the bare bones H T M L。

So。All I'd like you to do is add some more text into your document。And with that。

 we're going to use some of the tags that I talked about before。If you want。

 try to make it look like this。Using the tags that Ive listed up here。

And keep in mind that we could use like things like div that I talked about before。

 but wed like to keep it more semantically nice so we can use things like section。

And this one here will just add a horizontal rule。So let's take up the line。

So take like three minutes， talk to the person next to you。And try to get as close as you can。

 So making your website look like that。And if you want to see the changes on your website。

 if you still have the tab open in your browser， all you need to do is reload。

I haven't made any changes。 So you。Hello， and if you're too shy to add yourself to the queue。

 which you should not be，'cause the queue is very approachable。

 But if you don't wanna add yourself to the queue， we have Lucas and Daniel walking around so you can just flag them down if you need help with anything real quick。

Okay， I'll give you guys like。Three more minutes。To try to get it done。有了。嗯。哦。Yeah， also。

 if you wanted an alternative to opening up the thing without having to go through like finder or anything。

 Another thing you can do。Is right click on the file。You just copy the path here。So copypy the path。

And then， if you go into browser。I think you can just pi it。And then， it'll open up。Same thing。

Alright， we're gonna start working through it together now。So going through what we see up here。

Obviously， we see this big。Header up here， Bucabuca。And for that， I think we're gonna to use。

The header tags， H1。How wait， could you get that。Print。To my back。再跟。One more。喂。Allright， under that。

 we have our line here， and I mentioned that you can use the HR tag。

And it's actually a self closing tag。 Maybe I should have mentioned that。 But of course。

 you could just use the MN Web docs to find that out。

 And it makes sense because you're not going really enclose anything within a line。Next。

 you didn't have to do this， but I'd like for you to do a section tag。

So that we can group up our about me and our favorite type of cat。And within the first section。

 we'll do。A header for about me。And you'll notice that I used H4 here。嗯。

Something about the header tags is that they have， like， different。

Default sizings under them already。And the higher the number， the smaller the text。So， if you want。

 like。Various like subheadings you can use like H 3， H5， H， whatever。But I'll use H4 for this。

And then over here， we're going to use P。And then。I won't talk about the full text。

 but you can do it if you want。And then we'll have the other section。And。好。Yeah。

 let me turn that off。嗯。啊，听得到。So this is about what it should look like。And if we go to。

How a peer and reload。And we should see that it looks closer to what we want。

And feel free to just add whatever text you want。 And I't really care。Alright。

 I'll wait for a moment for everyone to。Get up to speed and make sure that you can see。

This in your browser。O空。Art， we're gonna move on。And before we do that。

 I'd like you to type in these commands into your terminal。Let go back out。First。

 we're going to type in git reset hard。And I'll explain what this does， exactly， in a second。

And then we're gonna type in gett checkouts。0， step 1。Wait for a moment for everyone to do that。OK。

So yeah， what exactly are these commands doing。Okay。

 the first one that I told you to do was get reset dash hard。

 So git reset hard is going reset your local version of the code to be whatever was last committed。

 So， for example， like， let's say。You were working on some code。 it kind of got away from you。

 and you like don't know what's going on anymore。 And you just want to go back to like the last。

 like， like landmark point that you were at。Then you can just type in get recess dash hard。

 and it'll reset your code。Toever you last committed。

You can kind of think of Github as the place where all like the nice code is。 you give it to you。

And then you do your work on it。And maybe you mess up。

And you wish that you could undo all of your work。But not undo everything， right。

Then you can just do git resetes dash hard。And your code will be good as new。

The checkout step we kind of mentioned before in our G basics lecture。

But all it's doing is changing or it's switching your version of the code to a different branch of the repository。

嗯。对二。Theres a slight difference between the one we showed you the first time with dash B。

 So that's gonna make a new branch。 This one is just。

Switching to a branch that we already have created。So in summary， if you ever get lost。

Then don't worry， because you can just type in， get reset hard and then check out whatever step we're on。

And you'll be good as new。 And you can just follow along from there。

A quick note is that you shouldn't abuse， get recessed dashes hard。

For like every project that you do， it works really well for our workshops because we're just trying to like。

啊。Wal work through something together， but。If you're doing your projects and you make a lot of changes and you just get recessed Dutches hard。

 then it'll be lost forever。 So keep that in mind。Okay， so back to where we were。

We'll type in those two commands。And you'll notice that。 it actually has。

The correct solution code to have exactly what is up on the slide。So。Again， if I try to do this。

Then my code matches。Was it shit。Okay， cool。Move on to our first step。

And that's going to be to add an image。And I'll have the commands for to get to whatever step we're on in the corner or on this page here。

And I'll have the progress bar to help you see where we are。So yeah。

 let's try to add an image to our website。 We're gonna put above thebucabuca。

 and it's gonna be an image that's already in our folder。Itll be cat dot P And G。

It's just like a cat。And。I'll give you guys like two minutes to use the image tag that we talked about in the earlier lecture。

And try to get your website to look like that。Once you've got the image showing up。Also。

 remember to add some alt text。You can make whatever you want。And remember。

 if you forget the syntax for anything， it's just a Google searchway。Alright。

 I'll go ahead and work through it with you guys。So if you recall， image is a self closing tag。

And we use this attributes。To get the right picture。

And I'm just using this name because the name of our image is Ka P and G。

And it's in the same directory as our H L document。 So I don't need to do anything fancy。

 And then for alt text， I can just say。cat whatever。And remember it's self closing。

 so we don't need to have opening and closing tags。 We gonna add this forward slash at the end。

It'll render correctly。Its threeload， and there's our image。Alright。

 I'll give everyone a moment to get cut up again。Alright， sounds like people are done。

 So we'll move on。Alright， next， we're going to do some centering。Before we do that。

 remember to type in the commands that you see over there。 So we're gonna get that dash hard。

And check out the next step。O。Okay， for this step， I'd like to do some centering。 So I want to move。

 So you see how all of our text is like on the left side。

 I'd like to change like at least one thing that it can be in the center。

Because that's what our end goal kind of looks like。So。Here's what I'll do。For this。

 we're going to open up our CSS。Documents。And we're going to define a class。Or actually， first。

 how about we just link our style sheet。The way we're going to do that。Is in the header。

Or in the head element。Just add an element。没给。This real thing just tells it to interpret it as a style sheet。

And then。Hf。Tlls it what to look at。And again， this link element is also self closing。Alright。

 I'll let everyone get that linked up。Okay， next， we're gonna try to actually apply some styling onto our elements。

So as I said before， I want to have things centered。So I'll walk you through this one。

 because I haven't。Shown you that much about this stuff yet。But。

What we're going to do is define a class first in our CSS document。And， actually。

Have it split screened。You guys can see both things。But in our CSS document。

We're going to define a class。Or we're going to select a class。Called UT center。

And it's going to have this attributes。Let everyone get that copy down。As a quick aside。

Whenever we have a class that's only really applying like one thing， we call it a utility class。

 And that's denoted by the。You prefx on the thing。And the dot is here because it's a class。

So if there were an I D or something that we use like a hashtag sign。 But because it's a class。

 we're just going to use dot。到。And now， once we have our costs in here。

 we can apply it to whatever we want。So。How about we apply it to the header。The big header， H1。

And the way we're going to do that is by setting the class attributes。Toいう text。Then。

We should see that the text is now centered。Alright， give everyone a moment to do that。那m move on。

Again， all I did was。Create this class here in the style sheet and the C S styles does C S。

And then we apply it to an element by changing the attribute of class。To new tech centers。Okay， cool。

 I'm move。Alright， go ahead and reset that hard and check out step。3e。Alright。

 we're going to do some more styling in this one。And we're just going to use the class that we created earlier to center other parts of our document。

Shows the power of how classes can be used for many different elements， unlike Ids。

Our goal is to make our website look like this。And I'll give you guys like a minute or so， to。

Do that。O。那对。Alright， since this one's not too bad， I'll just go ahead and I've coded with you guys。

So again， we already defined our class。 So all we need to do is apply it to do other things。

And you'll notice that I put this in the section element。

And that means it'll apply to everything within it， as well。

So everything is going to be centered in the about me。And then if I also want to center this。

 I'll do the same thing。O够。And as a review， yeah， like what I just said。

 if you apply the class to these section elements， then it'll apply everything within it。

 So maybe that gives you an idea of why like div or span would be useful。

 You're just trying to select like an entire section。

 It doesn't make sense to do that for like every single element。

 And it makes more sense to do that for like a container on all of it。Okay， step 4。

Is gonna be something pretty common。 That's importing fonts。So first， we're gonna reset thates hard。

And check out the next step。Alright， let's go find a font that's better than the one that we have on default。

Your go to website， in this case， is going be font Google dot com。Ptty easy to remember。嗯。

You can just go to the search bar and search for any font that youd like。

 I'm gonna use open Sans today， but feel free to choose a more interesting one。😊。

So once you're on font Google dot co， you can just look it up and。They have it right here。

Once you're there。Click on the font that you'd like。

And then we're gonna head to this get font button。Should be in the top right corner。

And then you'll get to a page that looks like this。Okay， next， we're gonna click get embed code。

There are some fancy options here that you can play around with later。

But I'm just gonna choose an easy option。 I'll just choose the defaults。呀。Okay， next。

 once you're on this page here and I have the direction。Of here， yeah。Let everyone get to there。

 quick。O。Once you're here， the default option is linked。

 but I'm actually gonna use import because it'll be nicer to just put in our C S S。Document。

And they actually have it so that it'll go in an H here。But。嗯。For our purposes。

 I'm just gonna copy this intersection that's within。The on tags。So， copy that。

And then we're going to move back to our CSS style sheet。And。Real important。So again。

 we're gonna go to here， click on import instead of link。

Go to the first one and bed code in the head。And instead of including these tags。

 which would refer like putting it in the head of our H T L。

We'll just copy paste this inner part here so we can put it in the style sheet。Directly。O， cool。

Once that's done， we can apply it to our elements。In this case。

 I'd like it to be applied to everything， basically on the document。

So instead of defining or like selecting a class or an element and applying it to only those。

 I'll just select the entire body。So to do that， you can just but body the selector。

 And then within it， we're gonna change this attribute to upon family。Because we import it。

 it'll let us directly refer to Opens。Or whatever font that you imported。

And then if we go back to our website。Yeah， the font should be updated to whatever you chose。

Because we like having， like， fallbacks and。Safety for safety reasons。 If we go back to our code。

 we can also add。Like a fallback option in case our。Our statue didn't actually import the right font。

 And it doesn't know what Open sands is。So we can put like sand serif。That's like a built in。

In the case that we don't have open sands than our web Pat just。Default to stand Sarah。

And you can do that by just adding it after some commas。Okay， cool。 I'll move on to the nav bar。And。

As always， we're gonna reset that hard。Check out。Re step 5。So if you remember in our end goal。

 we had like a nice bar at the top that said catbook。And we're gonna do that。

 using the nav bar element。So what I want you to do is add this k nav element to the top of your body。

Give everyone a moment to do that。嗯。Iue I'll do it with you guys。Also。

 add this header elements for your catbook。Once you've done that。

We're going to preemptively add these classes because we know we want to style it later。So。

I'm going to assume that we're going to use this class called nav container。

 which we'll define later in here。And I guess for the header， we can also define something。And again。

 I haven't done any styling to it yet， but I'm just doing this preemptively because we will do it in the future in our St S S document。

Okay， yeah。 So let's go and do that。Before we do that， I'll touch a little bit on CS variables。

So C S S does support like a type of variable。 And this is helpful if you're gonna be using like the same thing over and over again。

 Like， for example， like a color that's in hex， you don't want to keep typing out like the hex。

 And maybe it's nice to just know like what color it is already， so。😊。

synyntax for that is gonna be as follows。So the reason that it uses roots and it'll use colon when you're referring to root is that it'll apply to like the entire web page。

 If you remember at the beginning of the first lecture。

 I saw you guys that the HM L tag that contains like everything。 This refer as the root。

 So this will just make sure that you can use this variable like。Anywhere at all。And then。

 for variables。We're going use these two dashes。And then， the variable name。

And then what it's said to。So if I use exactly what's on there。Ks。This color。

Another nice feature is that you can click on this and then select another color。Okay。

 once we've defined those variables， we can go ahead and use them。In other styling。

So let's go ahead and style that class that we used over here in the nav element。So or。

 let's use the na title 1， I guess。Okay， here。And then if we actually want to extract the value from a variable。

 we'll have to wrap it in this bar。A function thing。And then another attribute will change。Spot size。

We're also gonna undo some of the default formatting that's been applied to H1。

 So C S S alreadyity or H T L alreadyy like interprets some default formats。

 Like you can see like the font family is also chosen for you。 But if we want to undo that。

 then we have to explicitly tell it。In the style sheet。So we're also going to add。

The following attributes， like margin。And on wait。O。And then。Yeah。

 we should see our nav bar up at the top here。And just to make sure that your variables are working。

You can go into here。Change the color。And reload。And yeah， it looks like it changed。

Give everyone a moment。K up。没 cool。Alright， Evan， we'll take you guys on to the next steps。Okay。

 so now we have a nava bar。

![](img/139f1f3dcd8d4d8d767115084154b7c0_16.png)

So。Let's go ahead and try to style the out for it to have a different look。 So first。Just check out。

Step 6。Right， so yeah right now， the NFar is white and。White with blue text。

 but we want to have it now blue with white text。So， using。

So using the C S S variables that we defined earlier， try to style the nav bar。

And I'll give you guys。A couple minutes either。All， so sitting a time。

 I'm gonna start going over how you did for this one。So。Since we have the。

 we add the nav container class that Sova added earlier。And then， just to style it。

You can create the nav container class within the C S S file。

 And we want the background color to be the blue。 So the blue is our primary variable here。呃。



![](img/139f1f3dcd8d4d8d767115084154b7c0_18.png)

Pm variable。 And then we want that。We now want the text color to be white。

 And that's our it's just called white。 So we rename rename that to white。And if we reload。

We now have a blue background。W tax。Alright， so because sitting and coding H TL for a long time is kind of difficult。

 we're going to give you guys a five minute break。 So if you need to use the restroom。

 grab some water， feel free。 But for the rest of us， I wna get us up and moving a little bit。

 So raise your hand if you think you can wash it longer than me。😊，Okay， we got one two， oh。

 thank you， Lucas。Anyone， anyone？Allright， well， y'all are gonna find out because we're all gonna wtz it。

Every find a spot on the wall。Come on， even if you don't think you can out wallt meat。

 you can still come and do a wall sit for as long as you can。let's go guys。 Come on， Come on。

 pick it up， pick it up。 We don't have much time here。😊，Alright。

 I'm gonna start the Wall battle in like 20 seconds。



![](img/139f1f3dcd8d4d8d767115084154b7c0_20.png)

嘿van。Could you turn out some music or something？A secret weapon。 That doesn't sound good for me。Oh。

 is that why you spot right next to me so you can pull some weird？Heck， yeah。

 that's what I like to see。😊，Alright， ready。 We're gonna start in 3，2，1， go。😊。

I'm setting a max cap of four minutes， so that will have time for the actual HML and CS。

S programming of our lecture。😊，So if you can make it to 4 minutes， you've effectively won。Whatちね。But。

What year you。I'm had of。ju。Well， it's so。 I'm so。

![](img/139f1f3dcd8d4d8d767115084154b7c0_22.png)

And， there's no。TheThe only sound options are。But these do't work。我就是。おです。I don't think you。然 the油。

Why are so many of you guys still up， This is scary。Or down。 I mean， okay， fine， fine， fine。

Lucas is yelling at me to get 90 come on。 okay， Im 90 degrees now。Hey， Lucas。

 you're  not 90 degrees either。 What is this。I it's more now。Oh。

I'm regretting my life choices not right now。 I'm not gonna lie。All right， we hit three minutes。Guys。

 I lost sit for longer than Lucas。 Let's go。要是。You're playing geometry dash。That's so funny。

30 seconds left。That's， that's a threat。嗯。10，9，8，7，6，5，4，3，2，1。Everyone down oh。

Add those people who went the full four minutes， Y'all are amazing。 I wish I had a prize for you。

 but I don't。 Alright， back to evidence of it。😊，Every went back two seats。嗯。嗯。Okay。

 we'll move on to step 7， which is removing the margin。So， as always， we hard。And check out step 7。

So， if we look at。If we look at our web page here， we have this slight white space around everything。

 and we can see it here。 too。 We have white space around everything in the document。

Which is not ideal。 We want something to， something that's flushed with the edges of the browser， so。

We need to figure out how to fill this space up and to do this。

 the easiest way to figure out what's going wrong with your website on the front end is to use developer tools。

 So it developer tools。 you can just right click and hit inspect element。

And you have this sort of mouse tool， which lets you hover over elements。

 And it tells you which element you're over， so。If we hover over the nav bar here。

 we can see which we can see the nav title class， and we can see a couple other attributes on it。

 such as the size， the color and things like that。So as for the white space around the whole website。

 if we click on body here， then we see that there's this little box down here。

 And this is what's called the box model。 And this lets you see what the sort of sizing of your H L boxes are。

 So we have what's called the margin the border padding and then content。

 So margin is the space around your content。 it's just。

Used in the typical form of the word padding is spacing that goes into the margin。

 And we'll see that in a sec。 And content is the actual size of the content。嗯。

So we want to get rid of this margin around the outside， which makes this that there's white space。

Yeah。啊。So one thing about the margin C S attribute that we'll talk about briefly is that it actually has something called ordering。

 So you can specify one number or you can specify multiple numbers。

 And depending on what you specify， it changes。Changes the look。Of the margin。So。Right now。

 if you want to get rid of the margin around the outside on the。On the， on the body。

 then we can put in a margin 0。 And if we reload， we see that it applies a zero margin to everything around the box。

 So if we， if you look at the box of the body， everything around it is a dash indicating that there is no margin at all。

But if we put in two numbers， what it does is it fills it it fills it starting from the top and going clockwise and repeats if necessary。

 So if， for example， we wanted it to be flush with the wall on the top， but not on the sides。

 then we could put in like0 and then 0 pixels and then 10 pixels and this would fill it in starting from the topping going around and this places。

A 10 pixel immersion on the side。So can these 10 pixel merges on the sides。

 but 0 on the top and bottom。And again， if you do a third one。

Then it fills it in starting the topic going clockwise。 So actually， you。

 you wouldn't be able to tell what this one because it'll just be white。

 But then if we reload and open up developer tools again。If we open our developerbra toolss。

It's bit hard to see， but you can see the 0，10 and 20。

 And you can play around with this for yourself。 Just adjust the numbers on。

Any of your distance attributes。 So that's things like margin or pixel。

 And it'll fill in from the top going around the clockwise。So we can set that back to 0。

 because that's what we want。嗯。And yeah。So now another piece of styling that we w to do is add padding。

 So if we look at our， if we look at the top here， this not only is the nafar flush with the browser walls。

 but so is， so is the text。 And that looks kind of bad as well。 So we want to add padding。

 And we can do that in a similar manner to our margin。

 And since we want 8 on the top and 60 on the side。If we go into the nav container。

 which is the container where we want to have padding。

 So padding sort of is added to make the elements within a container。

 So it's children spaced off from the wall from the edges。

So if we add padding to our na container and what。8 pixels， and 16 pixels。

It'll do something like this。And get the patterndding that we want。But why do we。

 Why do we choose 8 pixels and 16 pixels？ Well， this is something that's called the 8 point grid system。

 And so this is choosing all your distances to be a multiples of 8 or， or a half multiple of 8。

 And this is just。A standard to make things visually appealing and just have a very consistent format。

So we just hard code it in the the padding here。 But to enforce this a point grid system。

 one thing we can do is use the C S variables again， so。Instead of only having colors。

 we can also add in distances。 So X small is four pixels。 And after that， we have the multiples of 8。

And these sorts of distance metrics are built into C， S S libraries and things like that。

 which we'll talk about more next week in the advanced C S lecture。So now that if we。

 now if we define these variables， then when we set up。

 when we want to set up padding like8 pixels and 16 pixels， we can directly call on the variables。

 So8 pixels corresponds to small。And then 16 pixels corresponds to medium。So。If we。

 if we place this in， we should see that there's no change。

 But now we have a system where we can directly enforce the8 point grid system just by using the C S variables that we defined。



![](img/139f1f3dcd8d4d8d767115084154b7c0_24.png)

One more distance metric that I'll talk about for a second is just within height。

 And that's pretty self explanatory。 It sets the most innermost box。

 But we don't actually need to set it here， because。If we don't set it。

 it implicitly just fills the entire space。嗯。Yeah， and here's a quick exercise。

 which is rounding corners。 So if we have on our image here。On our image here。

 we have very sharp corners。 But if we wanted to style a bit and add rounded corners。

 we can use the border radius attribute。 So go ahead and take a minute or so just to try to round off the corners。

Of。Your。Of your， of your image。Oh， and also， I forgot to。I forgot to reset to step it。



![](img/139f1f3dcd8d4d8d767115084154b7c0_26.png)

![](img/139f1f3dcd8d4d8d767115084154b7c0_27.png)

So。This one is not too complicated。 We， the main thing we just need to do is we need to add a class。

To our image， which is what actually contains our avatar。 And we can just call the class avatar。

And then we can create an avatar class， and we wantan to adjust the border radius attribute。

 and we can set it to maybe like， our medium variable。And that we see we get round quarters。So。

One quick exercise you could do after， after class sometime later today is creating a perfect circle。

 So this would be to， this would be using the border radius attribute and maybe some other attributes we've learned about today to try to make the avatar circle。

 But if take a time we'll skip this and yeah， you can just check out to step 10 if you want to see the result。

😊，Yeah， so。Step 10， we have a circle。Okay， now we're gonna shift gears a little bit。

 So we've been styling a a lot of stuff。 But now we're gonna talk about actually arranging things on our page。

So。Our final result， we want something to look like this。

 We want our about me text and our favorite type of cat text to be next to each other。 But currently。

 we just have them vertically stacked， which is the sort of arrangement that H TM L defaults to。😊。

So there's a couple of different ways to arrange things on a page in C S S。

1 is called flow and one is called flex。 but flow is outdated。 and we use flex now。

 And you'll be using Fl a lot throughout your project at the end。

 And we'll see it a couple more times this week， too。😊，So to do is flex。

 you just set up some display flex。 And then after that， there's a number of。

Other things that you can adjust。 So if flex is actually。Pretty extensive。

 So there's this C S Ts website。 You can visit Web Web do is slash flex to get to it。

 And it sort of discusses all the different settings， Yeah， for flex。😊，So to get flex started。

 the main thing you put in your C S S is display flex。 But then after that， you have to。

 you have all these attributes that you can adjust。 So， for example， one of them is flex direction。

 And this is sort of one that we want to go for。 because this adjusts whether the elements within a parent container are arranged horizontally or vertically There's wrapping。

 there's justified content and align items。 So these two sort of So justified content is how things are arranged on the main axis align items is how they're arranged on the orthogonal axis。

 And these are also very important for stling。 And you can read through the rest of the ones in here。

 on your own。😊，So。Yeah， if you look at this gift here。

 you can see adjusting the flex direction will change it from。

 from being arranged horizontally to vertically。So now we want are currently vertically stacked about me a favorite type of cat boxes to be arranged horizontally。

 so。

![](img/139f1f3dcd8d4d8d767115084154b7c0_29.png)

If we look at our H L code now， if we notice， we sort of just have these sections for favorite type cat。

 And about me， they're just。One after the other within the body。 So the body is the。

 is the smallest enclosing container for these two。

 But if we wantan to arrange just those two horizontally， then we。

 we need to have another div just for these。Just to contain these two。And once we do this。

 we can create maybe another utility container called duleex。And then if we want it to be horizontal。

 we can first set it to display flex。And then we can choose the flex direction to be row。

And if we do this and reload， we see that they're now arranged in a row。

And it turns out that you can actually also just delete this flex direction row attribute because flex defaults to having things in a row。

 So normally， you actually just specified this if it's in a column。And you'll get them in a column。

 And you can also do things like column reverse。And we see if we reload about me in favor type of a cat flip。

So that's the most basic way to use Fls。We just set them up to be in a row。And。

You can see the results if you check out step 11。

![](img/139f1f3dcd8d4d8d767115084154b7c0_31.png)

So I guess just a few。The way we got it to be horizontal is we surround。

 we surrounded our two sections within a larger div and applied the flex utility class。哎，嗯。

I'll move on to some other， the other set of flex， which is within the arrangement。

 You can also control how large your boxes are。So reset hard and check out step 11。So currently。

 we have our website looks like this。 We have the two boxes sort of scruned up on the side。

 and they're not exactly what we want to have because the final， in the final case。

 we wanted both sort of centered on each of their sides。So。Fleex is another。

 you can also control sizing with flex。 And if we look inside the C S S Ts website。We have。

Fleex grow。 and we also have flex spaces。 So if you read through these。

 these are both ways to control how large they grow。

 So flexg sort of changes priority for when things grow。 So if you apply。If you。

 if you set a value of 2， then one of the sub containers will take up twice the size compared to the other ones and。

Fex basis is the default size before the things grow。 the ref flux grow。呃。嗯。With this in mind。

 maybe try to play around with flux basis and flux heroro and see if you can get the two columns to be equally sized。

And the main thing with flux is there are a ton of settings。

 And the best way to learn is just playing around with your different boxes and get trying to get things to look like the way you want them to look。

And also， as a hint， you're gonna want to probably create some new classes because the way flex。

 the way flex basiss and flex scroll work， is there applied to a subcon， so。

If you have the larger blue container， then you would apply flex grow and flex basis to the classes of the subcons within them。

没有。So the way we're gonna do this is we're gonna create a subcon class。And。嗯。

We're gonna to set the flex。What go to one。And we're gonna do this so that both the elements and apply this class to both the elements within the container so that they grow to the same amount。

And then no default size for either of them。And so if we apply these classes now to the two sections。

And then we reload， we see that they grow to the same size because they're given them the same priority within the flex box。

Since we applied the same class to them and we get close to the desired result。

And you can check out step step 12 to get that result。right。

 so that was pretty much it for this workshop。 And there's a lot to it。

 There's a lot of new C S attributes that we learned and combined with doing HTML L for the first time。

 But the main， I， but I hope you learned a lot of the main ideas from this workshop。😊。

Here are a couple of helpful links。 Again， the C S S tricks website is at Webla dot is slash flex and has pretty much everything you need to know about flex。

 I still reference it from time to time when I need to。 And here's some games。 I've。

 I've never played these actually。 But you could check them out and see if they're good。😊。

There's some additional styling that you could do as extra homework afterwards。 And it's in W 0。

 step 13。 And W0 complete has the full， the W0 complete branch has the full cap profile page。😊。

And we'll also do more C S next week in advance C， S S with Stanley。And minute for。



![](img/139f1f3dcd8d4d8d767115084154b7c0_33.png)

Feedback。
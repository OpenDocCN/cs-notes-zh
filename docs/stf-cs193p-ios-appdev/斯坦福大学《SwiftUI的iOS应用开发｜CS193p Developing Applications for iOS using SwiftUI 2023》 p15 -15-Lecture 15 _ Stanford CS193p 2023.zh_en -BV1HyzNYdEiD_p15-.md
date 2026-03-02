# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p15 -15-Lecture 15 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p15-

right， lecture number 15， the end of the quarter here。

 all the topics that I did in the first 14 lectures， they kind of apply to almost any kind of app。

 right gestures and animation and persistence with codeable and all these things those are things you want to do in almost any app。

This is the first time I'm going cover something that really is only in a certain kind of app。

 which is a document oriented app， right we have emoji art。 create these nice Moji art documents。

 They're truly documents。 The user wants to save them and rename them and move them diecloud drive and do all this kind of stuff and that's different than like memorize。

 memorize it plays a little game， but it doesn't save anything as a document or whatever。

 So that's what we're talking about today before I do that。

 I'm going talk to a little tiny bit about app and scene which we've taken for granted right your little@ign main program we have that app thing there。

 we to talk a little bit to tiny bit more about that。

 but usually you don't need to do much with app and see how you've been using it is pretty much how you use it。

And after we talk about the document architecture stuff I'm going to come back and talk about two topics undo and notifications undo you might be surprised to see here but it actually none of that document stuff works without undo you have to do undo to make the document stuff work and then notifications I only am bringing this up notifications really is an old API and we hardly to use it anymore but there's a couple of places where it's useful and one of those places happens to be in our emoji app so I'm going show it to you really briefly at the end of the slides and then rarely at the end of a demo and quickly show it to you it brings up a little bit of a can of worms because it is this older API but I think in the name of completion I should show you this thing。

So let's talk about app and scene。 So app is just a protocol just like view is a protocol。

 It seems very similar actually， when you look at your app sign main program and you have your emoji art app has a var body just like view has a var body but the type of the var body in app is some scene not some view some scene So your app is structured as you've got this app。

 which is this app protocol thing and then you've got multiple scenes and the reason you have multiple scenes is because your app can have multiple windows on iPad and on the Mac on iPad again we've started to see a little bit of the multiple window Ui a lot of people don't even know it's there。

 but it's there it's pretty cool and then on the Mac of course you can imagine having multiple windows with multiple emoji art documents open and each of those windows is a scene capital S scene it is another little protocol here So there's not much to say about app except for that it's the thing that。

decidedes what scenes you're going to have。Now what about scene let's talk about scene scene is a container。

 a window that contains your top level view and we've seen this right because we had our memorized view was the top one and then we have ourOGR document view。

 these are views that are at the top level of a scene， so the scene is where you say what that is。

Now you can create your own scenes like you've create your own views and this is pretty rare I think one example of where you might want to do this is you want to look at this atign environment variable called scene phase scene phase tells you things like this scene has become the foreground scene or now it's in the background and you might care and want to do something when that happens then you might be creating your own scenes but normally you're not creating your own scenes you're using the built-in scene creators of course you know the one that we've been using so far called windowow group but there's a couple other ones I'm going to talk about today。

So these scene building scenes， window group， document group has two versions of it。

 you can kind of think of these things like four inches for scenes。

A windowdow group so far we had one little view in there and it took over the whole screen and we didn't create multiple windows。

 but windowow Group can create multiple windows and I'll show you the UI in emojiART today how you create multiple windows and when you create multiple windows it's just going to create a new container and a new copy of your view。

But if you have the same view model that's shared between them。

 then you're going be seeing the exact same thing in every one right because of course views are just showing what the view model represents in the model。

 so you're going to have that so that may not seem that much。

 but when you have a document group you're much more likely to have every scene have its own view model because each one is representing a document here。

Let's talk here about the green content you see that each of them has this green content in the window group it's just some view and that's going to be what fills the entire scene so it's content view or memorized emoji memorized game view orji or document view in the document room ones you can see that there's an argument there config in you see that config in that config is what tells you which document is going to be opened in that given scene so this closure。

 this green closure for the two document is called with this argument are config and the config simple little obstructive basically has two things I think the URL of the file and a view model to use。

This document group will call that closure every time the user wants a new scene。

So window group is the one you've seen before。As I said before。

 if you have atign state object at your app right there， then yes。

 you can still create multiple windows in the window group thing。

 but they're all going to be showing the same view models that are all going to be exactly the same thing。

 there's nothing that says though you couldn't move that atign state object down into the view and then have every window be its own little game right emoji memorize game you could do that certainly possible and that's why it's important to understand that at sign state object scoping is this that the app shared overall or is it in the view only for this view。

Now most what I'm going to talk about here is the document group。

 so this document group that you see on here， the code。

 this is for an editable document like an emoji art document where we're going to be setting the background and adding emojis and all that stuff。

 so let's look at all the parts of this a color coded these things here。

So the yellow is the actual call to the scene building scene。

 the for each like scene thing called document group and you can see it has two arguments actually let's look at the second argument。

 which is a closure， that's the closure with the config that I told you has all the information you want in there and config document is a view model for a document to open so it handles opening the thing up。

 getting it out of the file， creating a view model， emojiA document。

 which is our view model and handing it to us so that all we need to do is say emoji A document view here's my view model。

 config that document really cool at this level。That's all there is to that what's going on the blue thing is kind of interesting that's a little closure that creates a new document because you're going to see when we look at the UI for this that there is a button that says create me a new untitled document and it's going to create it for you and it's going to call this closure and for us that's easy just create one of our view models。

And they'll automatically handle all the files， you don't do anything with the files here at the app level。

 you do a little bit of reading and writing in your view model of course。

 but at this level this is what the code looks like and this code that you see looks like this for all document apps it's just really simple like this。

Now you put this nice simple code in there， but then you have two things you have to do to make it all work One is your view model emoji document has to conform to this thing called reference file document this protocol and this is the protocol that makes a so the thing can be read and written to the disk and very simple protocol we're going to learn all about that and then the second thing is you have to implement undo this might seem kind of weird its like what does undo have to do with any of this but undo is how the whole document system knows that this document got edited。

If you did something that can be undone， then your document must have changed and so I'm going to write it out to disk and this documentism auto saves your document。

 it is automatically anytime something changes。Maybe not immediately， but very soon。

 it's going to write it out to disk。 So that's why undo is important。

 And I think it's an interesting decision on their part to make undo be required because they could have put some little thing that says。

 oh， just mark this document as edited。 and then not have undo。

 And I think they wanted the experience for their users that apps with documents have undo。

 And so they just made it a requirement。 So I've kind of like it。

 And you're gonna to see it's quite easy to implement undo。 So。

No problems there Now let's talk about getting the view model to put your model on the disk and out and we already saw this right we already saw we auto save our document our one document and we know that we just have a data we turn into a JSO we write it out to disk we read it in and it's very。

 very similar to that but it's a little more formalized。

So here is the reading from disk and this is the init of your view model so if you have a view model that is a reference file document here you're going to have this init and all this init needs to do is take this read configuration and inside the read configuration I think is' only two things in there like the type of this file it is like it was a JPEC file or whatever and then this var called file you see a data equal configuration dot file and the filestruct represents a file in the file system and dot regular file contents means give me the contents of that file as a data which is exactly what we want for us it's going to be a JSON encode code to JSON and then we just initialize our model we're just going to say emoji art equals that thing from the JSON and we're on our way。

Notice that this thing throws and if for some reason we can't get the regular file contents out of there。

 we're just going to throw this coco error Now we could have made our own little enum for throwing their file error or something like that but I'm reusing coco error here just because I think it's an interesting thing to be able to do and if you go look at the documentation for coco error you'll see there's a whole bunch of coco errors that make a lot of sense that you might want to throw it just a convenient way to throw some common errors is to use a coco error Coco by the way is the name of iOS development system it's called coco we don't really call it that anymore now we call it Swt UI but so it's an ancient name Coco it's probably 20 years old。

So that's how you read it in， couldn't be easier right just get the data out of the file there how about writing it out This one's a little bit odd the function to write it out is called file wrapper and the readings called file wrapper and it returns a file wrapper you see this type file wrapper is that some files historically in iOS in Mac they are stored as a directory with a bunch of files in there so you could imagine that you had I'm just making this up this is not the way it's done I don't know but like pages you have a pages document and it's got a lot of images in there maybe those images are stored as JpeEG files in a directory and the pages files one of the files in the directory you see what I'm saying so we're kind of making it out of that so that's what a file wrapper is supporting but in our case with emojiA we don't use any of that we don't store our emojiR document in a directory with a lot of little we just store it as a data blob literally data so if you。

Doing that you can use this file wrapper constructor here。

 regular file with contents and you just give it a data and it makes one。

But if you were doing all that weird directory stuff you would do that in here building your directoring for your files in there。

 but all you have to do is return a file wrapper and it will take that file wrapper and put it on disk for you So this is the essentially the writing and this right configuration here again just a couple of things in there it's got。

Probably the type of file we're writing here。And so very simple。

So that's the basics of reading and writing， reading at the top， writing at the bottom。

Now there's a little more with reference file document though， reference file document。

 that previous one was just the basic reading and writing of file documents。

 This is specific to reference file document here。 the most important difference is that the creation of the data that you're going to do happens in a separate thread in a reference file document in case it's expensive to create takes a long time maybe to create it's some gigantic thing now an emoji art totally not our emoji art documents are so trivial to create we just Json and code them blam but anyway。

 this infrastructure is built just in case you have this funk in the reference file document protocol called snapnapshot and it passes the type of file So like is this an emoji art file that I'm asking you to snapshot or a JpeEg file or what and you give it back a snapshot Now that snapshot the blue up there is a don't care so you can do anything you want to give it back like you could give back an emoji art if you wanted。

But usually we give back a data here because eventually what's going to happen is we're going to be given that snapshot back back on the main actor and asked to go write this snapshot out。

This is where you put the thing that turns your model into a data when you're doing a reference file document。

And then the file wrapper one that we saw on the previous page is a little different because look they give you the snapshot back So they're going to call the snapshot on a different thread when it's done。

 they'll come back and call this file wrapper thing just like we saw on the previous page but with this extra argument snapshot and then you're just going to write it out and that's why it's nice if snapshott is a data because file wrapper regular file contents wants a data as that argument there right so that's why a lot of times we'll make snapshot be of type data but if it wasn't if it was a type of emoji art。

 which would be legal then here we would be。Doing convert right do JSON。

 turning it call the JSON function that throws， we'd be trying it all that stuff。

 we could do that here。And that's all there is to do in reference file document。

 implement this stuff， and these are mostly one liners to implement。

 as you'll see when we do our emoji art。But inside there you saw a lot of reference to types。

 the types of file right an emojiA file or JPEG file， that is this type UT type。

 which is a uniform type identifier and theres some infrastructure in Swt for dealing with these things for standard files like JPEGs and things like that。

 the UT typestruct has some statics do JPEg textexpf and you can use those for standard if you're reading writing standard types and why by the way would you do that。

 what if in emojiA we had a menu item， save as JPEG where it would draw our thing as a JPEG well then we might be writing JPEGs out。

But if you have a custom type， which we do in emoji art， you have to invent your own one。

 and that requires doing some stuff in your project settings of your app to tell the system about this new custom type emoji art type。

That you have and one of the most important pieces of is you have to have a unique identifier for it that no one else would use for their type and so that's why we always use reverse DNS notation here So emoji art is going to be of typeedduu Stanford cs1gp emojiard I don't think anybody else is going to choose that for their type and then we have to say what this means and this is how we do it this little screenshot here is from the project settings the app you'll see we're going to do this in the demo It only wants a few piece of information here。

 first of all there's two different kinds of type identifiers there's exported ones and imported ones exported ones are ones you own like emoji arts it's like this is my type and I defined it my company in charge of it you're exporting it to the world imported type is identifiers that you are willing to read but you don't own so you're willing to read this type somehow displayed your app or something but it's not your so that's going export it and import it So here's。

Export a type identifier it has a named emoji art that's just so the UI user clicks on it'll say。

 oh this is an emoji art file or whatever， here's our identifier I talked about over here is the extension so I'm going to have my files for emoji art to be dot emoji arts just like dot JPEG files say dot JPEg R I'm going to say dot emoji art。

And then finally there's this conforms to down there these uniform type identifiers have kind of an inheritance orientation to them。

 this is not obviously a program or anything like that but they can inherit meaning you can think of them as protocols in a way but they're not protocols from other types so here's two types public datata and public contentent just like eduu。

tanford。cs193。 emojiar is a type so always public datata and public content and those types you would never open a file that's up type public。

data it's more like an abstract superclass for other types and why do we conform to those two abstract types well public data just means it's a regular file on disk that have binary data in it。

It's not a file wrapper some kind of thing like that。

 And then public content means the user perceives it as a document。

 they want to see it in their file system when they browse around。

 they see it there so we obviously conform to both of those if you're doing some of this stuff go look at UT type its documentation。

 there's a whole description there of all the dozens maybe over 100 different types。

 both the abstract ones and concrete ones and you can see how it all works but for us pretty straightforward here So that's how we describe our type identifier but since we're inventing a new type。

 we also have to fill out another part of our project settings which say what is that type that Edu Stanford CSs193P and all we have to do is give the name of it again and here in handler rank we're probably going to say owner。

 we're the owner of this document our app owns this document we should be the first one who gets to open them where we can edit them and this part right here is just how the system knows there's a new thing called emoji artt。

The other one was saying that we can open them and edit them this saying it exists orre just declaring it。

One other thing that you're going to see when you do those previous two pages that I was talking about there。

 you're gonna to get a warning in your app that says whoa。

 you define a document type but you don't say how people find it and interact with it and there's a couple of different options you can do there you'll see them in the warning but usually we're gonna to pick this one supports document browser we're going set it to yes and we're going to do this in our infoP list I don't think we've had a chance to edit the infoP list in this Of course I know some of you are running across that in your final projects but you'll see how it's done it's essentially just this little kind of dictionary of information and we're going add this one supports document browser to it and set it to yes and that's going make it so that。

The system knows that this app has got a document that it can show in the files app， for example。

 an iPad or in the file system on the Mac。So we got the UT types declared in our infoO P list now we need to define this emojiR type in our code and the way we're doing to do this is we're going to add an extension to UT type to give our own little static because I told you there was Ut type。

 Jpeg and Uttype text well now there's gonna be UT type。

 emoji art because I'm going add this little static led emoji art and the way I created is I say UT type that is exported as because it's one of the exported type Ientifiers right and I give it that Eduu。

 Stanford。cs1 P emoji art and by the way if you run your program and this string does not match what's in your infoP list you'll get a runtime error which is cool purple error。

And that's it So now we have invented a new type emoji art and we can use this type in our reference file document。

 all those implementations that we're asking for UT types now we can use this one and one of the things in reference file document we have to put is what types we can read and write it's just an array of UT types and of course an emoji art we only have one so it's an array of one thing in it are emoji art types by the way you don't have to have both of these if you put the readable one and you it's a type you own it's going to assume you can write it as well。

So that is all there is to it， it's surprisingly little code and you're going to see a massive amount of user interface that gets added to your app just because you can read or write documents。

But as I said， if you don't do undo， none of it works， it'll never save your documents。

'll just sit there thinking your document has never been changed and the way we do undo is with this object called a undo manager。

And the undo manager， super simple， it basically just lets you register blocks of code to be able to undo other changes right just give it a closure and say。

 hey， I just did something if you want to undo it， here's the closure that says how to undo it。

This actually making things undoable that code usually lives in your view model and why do you think that is because that's where all your intents are right you got to your intents in your view model and say how the model gets changed。

 adding emoji， setting background so that's where you're going to put the undo。

Unfortunately the undo manager comes to you on the view side in fact。

 the undo manager is just an aign environment variable remember outsideign environment is not in thatign environment object a different thing Asign environment its just looking things up in that environment values place and one of them is undo manager and so you're going to put this at the top of some view or some views and you're going to get the undo manager。

 you really have a choice here， you could get your undo manager and maybe on a peer of your view you could give it to your view model say here's the undo manager to use for all the intents。

Or you can do what I'm going to do in this demo， which is every time you call an intent。

 you pass along the undo manager to use to undo it。I slightly prefer the other way。

 but I have definitely seen it done the first way and the code's a little cleaner the first way。

 because in the second way， now all my calls to my intent functions I have to add this extra argument。

You'll see this in the demo and you can kind of make your own decision which way you want to go there。

You've got this undo manager inside your intent function in your view model。

 how do you use it really easy， you call this function on the undo manager called register undo with Ta the target is the object in this case it's going to be our view model that handles the undo that figures out what to do with undo and then how to undo is just a little closure that takes the handler that with target itself and hands it back to you and says okay you said that this was the thing the handle undo here it is what is the code to undo this and so that's what's in that closure the how to undo it's just a closure got code in it that says how to undo whatever you're registering so that's what register undo does you call register undo every single time you do something that can be undoable。

If you have a view model whose model is just astruct， simplestruct。

 then you can use this nice little code undoably perform that I wrote here to make anything you do。

 any intent function undoable， so let's walk through this。

It's called undoably for form again this is a function in your view model and it has an argument。

 of course with undo manager and then the do it that will closure there is the thing you want to be undoable。

 so set upsetting the background or adding an emoji， whatever it is。

 that's in this closure you're going to pass。Then all you do is you say let old model equals model and remember our model is astruct so when we say let old model equal model。

 what does it do， it copies it right Strs are value types when you assign them。

 they copy it So now old model is a copy of my model then I say do it。

 which is the set background or addoji and then I register the undo with the undo manager if I have one that's what this question mark means could be nil I'm allowing it to be nil up there and inside the register undo the closure I give is just set the model back to that old model that I just made a copy of I clearly is going undo it let me go right back to the way it was。

So this， these four lines of code inside here will make anything you do inside of a view model whose model is astruct。

 undoable。Now all you have to do then is wrap undoably perform with around all the things inside your intent functions。

 so you just go to every one of your intent functions and say undoably perform， wrap that around it。

Undos can also be named and this。A lot of times you just hit undo， you don't think about it。

 but most times in a Mac app if you go up to the edit menu and look at undo。

 it doesn't just say undo， it'll say like undo set background or undo add emoji the undo will kind of tell you what the action that you'll be undoing is you can set that really easily by just saying undo measure set action name to set background or whatever you want and it'll associate that action name with the Reg do that's happening at the same time。

And if you really want to be tricky， you see this myself do model equals old model right here。

 you could wrap that in an undoably perform and then you'll get redo so that's an easy way to get redo one minorr you can get redo just wrap your。

Undo inside that undoably perform。So that's it。 That's all you need to know for the document stuff。

 I'm going to talk about this notifications thing a little bit on the side here。

 The idea of notifications is that you can asynchronously send。

Little notices or notifications to other parts of your code now this is not putting a notification to the user on screen you know meeting at five okay that's a totally different thing that's the UN notification thing totally different nothing to do with this this is more something happens in the system and the system wants to send you a notification this happens。

So what kind of things might that be some database changed like you're looking at the user's contact。

And a contact got added or something changed by the context and it's going to notify you oh go look at those contacts again because something changed or the keyboard comes up。

 you know how when the keyboard comes up it kind of pushes your UI out of the way。

 well you can actually find out where did the keyboard come up what is the actual rectangle they do then when does it go away so you can get notified about that and there's other system settings etc。

Now， this。You can find out all the things that have these notifications from the system by looking at notification。

name。And you can see there's hundreds of them， there's a ton of them in there。

And you can find them other places too， like the one we're going to use actually user defaults。

 did change notification， that's a notification that could sent to you when someone puts anything in user defaults and we need that for our emojiA because we rely on user defaults as our database for the palettes。

 you'll find them in both of these places， but one thing I'm going to caution you is that this whole notification thing is a little bit the old way of doing this。

And really the number one way we do most of these things now is with at sign environment and the environment values so if we want to know we change from light mode to dark mode。

 we don't sign up for the notification that tells us that we just do at sign environment what mode are we in light or dark and it automatically redraws our views when that changes and we want that kind of behavior the automatic redraw and all that so notification is oldworl stuff that's why I'm barely even want to show you if I didn't have to do it for this user defaults thing for palettes I wouldn't even show this to you but go to environment values first to try and find what you want and then if you really feel like you need to you could start looking in notification name see if you can find some other notification that does what you want。

And of course， you can make your own notifications and post your own notification so you can use the notification system to talk to your own code。

 other parts of your own code。But we rarely do that。

 it's really not in Swt UI because of the way it's architect as a reactive UI。

 you don't really need to do this。So how do you sign yourself up to receive these notifications when the system wants to notify you that user defaults changed。

 how do you sign up to find out well in a view it's really easy。

 you use this view modifier on receive you say on receive notification center。

 default the notification center is the thing that sends out these notifications for you it's in charge of notifications and you get a publisher for the。

Notification you're interested in like userdefaults。

 did change notification that's what the blue thing is there and then you just give it a closure and it'll execute that code whenever that notification gets sent so again if we're doing user default one anytime user defaults changes in any way it's going to execute this closure and you'll notice the closure has a little argument notification on it I'm going to talk about what's in there in just a second it's a really small littlestruct。

But what if you're not in a view though， what if your view model wants to find out that user defaults change。

 which is exactly what our case is。 Well it's a little more difficult than you have to ask the notification center to tell you about it and you do it by adding your closure using ad observer right so you say say notification center that default a observer give the name like user defaults did change or whatever。

 there's also these other two arguments object and queue。

 the object is who's sending this notification。 if you say nil。

 then it means anybody who sends it So a lot of times put nil because we don't care who's sending it we just want to find out when user defaults changes and then Q。

This is the old world of multis writing， the queue system， don't worry about it too much。

 we're always going to put main there because we want our code to run on the main actor and it's talking about this closure down here。

 what queue is it going to run on， we want it on the main actor， so just say that main there。

So here is the closure， this is exactly the same as the closure we had up there above you can see it has the argument notification and I told you I was going to tell you what was in it well here's what's in it。

 this user info v and this user info v is very unfortunately a dictionary where the keys are basically hashable things hashable strings usually and the values can be anys they can be in any which means you have to use ads and is what a mess luckily again this stuff is old we don't really do it much。

This notification user info， for example， on the keyboard one。

 it's actually the CG rec is in this dictionary that tells you where the keyboard is now when it came up。

 could be valuable。And notice also that this ad observer returns a little observer thing of typey N object protocol right there。

 that's just a little cookie that you can use to later remove yourself as an observer。

Because let's say your view model， like the user closes the window and the view model goes away。

 you don't want to keep getting notified that the user default is changing。

 so it removes itself when it goes away and you'll see that in the demo as well。

And yeah I put up a slide how you post your own notifications。

 it notification center default up post and this as you imagine there's the name that you made up some notification name and it since its basically when you call this。

 it's going to execute those closures for all those other people who are at observing or on receiving and that's about it。

 it's unfortunate that this user info requires the A or is which we saw before and anytime you see Azure is you're seeing an old API we don't really do Az or is anymore we use protocols and we type things。

But in the old world， we didn't have that， so we're stuck with any。Allright， so that is it。

 Let's do a demo that shows all of this stuff I just showed you。 we're going to do all of it。

I'm going to start actually。you know， I like to do a couple little bonus things at the start that have nothing to do with what I'm talking about that day。

 the two things I'm gonna to do today is I'm gonna to send an app icon for my app which please all of you should do on your final projects I want every single one of you to do it and you're gonna see it's so incredibly easy there's zero excuse not to do okay so please do give your app and app icon so how do we do it well remember this assets down here there was this app icon you see there's this big space it says 1024 by 1024 So you just put a very high resolution version of your application icon and it'll scale it down to all the various sizes it needs you document icons and all these things spotlight results and all that'll do all that for you which is kind of cool in the old days you actually had to provide about 30 different sizes and now it'll do this for you so I have an icon here here it is my paint palette emoji so I'm going bring it over here。

You're upping in here Here it is now this app icon would prevent me from ever shipping this app on the app store okay and that is because I just screen grabbed the emoji for the paint pallet now it's really a good app icon for emoji art because it's an emoji of a paint pallet right get it but this image was designed by some designer at Apple and you're not allowed to use it as your own art so this would immediately cause you to be rejected from the app store they wouldn't even get two minutes into running your app and they would just reject this right away。

What's the other little trick thing I was going to do， I will show you。

 it's here let's go up here in document view， let's run our app we can see our nice。



![](img/39cf309056382b11c93a4e49325ac696_1.png)

![](img/39cf309056382b11c93a4e49325ac696_2.png)

New icon here。There it is， to see it down at the bottom。Whatats this， though， I'm going to bring up。



![](img/39cf309056382b11c93a4e49325ac696_4.png)

My list， this is my list of pallets， I'm going to add another window。

Which is my settings app So here's my settings app and one thing you can do in settings is make your fonts in your app bigger I think I mentioned this earlier in the quarter right I think I said old people like me you know we can't see that too tiny fonts so we want them to be bigger so here is my settings app and if you go where is it in settings now I can't even see this is the problem but I think your accessibility。

Display and text size。Larger font here we go so you can navigate down here and if you move this slider。

 it'll make your fonts bigger so watch our app on the left as I change this in settings。Larger， see。

 smaller。Younger， older， Okay， so that's kind of cool， but do you notice something else。

 Look at our pallets at the bottom。They're not changing， you see the sports down there。

 I'm making it bigger and smaller and it's changing these fonts。

 but it's not changing this down here。Why is that not changing why do these other things change and though that one doesn't Well these other things change because they're using the body font right font dot body or font dot caption or font dot headline。

 all these built in ones， those ones will automatically scale to whatever size this is saying。

 but what font do we use here， let's go look at our code and see what font we use there。

There it is right at the top， pallid emoji size， it dot system 40， so it's fixed at 40。

But there's a really cool little at sign thing we can do at sign。Scaled metric var。

 And if we do that， it takes that 40 and scales it based on the font。

 So this scaled metric is only for things that are linked to font sizes， Okay， content sizes。

Let's run again。To add back our list。And here's our slide， watch this。see。

 it's making it larger and smaller。Okay now again， this is something that in the old world we would have to get a notification and we'd get the notification that things change and then we'd have to redraw to okay。

 so nowadays no， we just add on scale metric all fixed it's a good example of why we don't really use notifications anymore。

Let's do emoji art documents we're going to start by going to our project settings and inventing our new type emmoji art so our project settings are up here。

 I think most of you are starting in your final projects to maybe go in here and have to do things so we're going to do that as well here's our document type we're going to add it。

Give it its name， emoji art。And its type eduu。tampford。cs193p。mogt。And it's rank。Owner。

And then down here in our exported type will say that we can。Read and write this。Mudji art。

You you that stampper that see has1，93 P that would G。Art。😮，Public content and public data。

Emoji artist is extension Notice we can also add icons here if we want to nice icons for our files。

I believe actually what you really want to do for this is put a thumbnail of your document instead。

 and I'm not going to have time to show you how to do that， but there's a mechanism。

You know how you can quick look on files， you know right click on them on the Mac and say quick look and it'll show you a quick look of it that framework also has a mechanism where you can create thumbnails for files so we would have to do a little bit of work in our emoji art。

Both our view model and our view to create a little thumbnail and then we could store that thumbnail in with our document and then when users looked at our document they would actually see a miniature version of it which would be really cool and that seems to be the way to do it that is more helpful to users than just some generic icon that represents a document and if you look at most Apple apps that's what they do they have a little kind of image of what thing would look like。

All right， so when we build now。We'll see this learning。 you see it up there。

 this little one if I click on that says here this application supports opening files。

 but it doesn't declare whether it supports opening them in place or you can edit them in place so you can set this document in in place or you can do supports the document browser which is what we want We want to be able to browse our file system see our documents and so I'm gonna show you how to do that I'm going go back to my infoP list here the same place where I just added this document type and export a type I'm going go up here to the bottom I'm going write I'm gonna select one of them and right click and say add row that's going to add another row of info here So all these this is like a little dictionary。

 this infoP list with a lot of settings about your app you can look at them and see what they are later but we're gonna add a new settings by saying add row and'm going to scroll away down what are you to call it supports document browser or something So it's under S you can see that a lot of things Here it is supports document browser。

And I'm going to click this to be yes， so yes， we do support document browser Nowte command B to build that goes away。

So this is the infofoops setup to make it so we have this emojiA document and as soon we install this on our simulator or on our device now that device or that simulator knows that there's a type called emojiA。

Right now that we have that， we can actually go to our code and open in。Save these things。

Go to let's start in our view model Here's our view model and right now we autos saveve。

 remember we have all this autos saveve， I'm going to take all that out because we're not going to autos save anymore now we have documents。

 I'm not going to do this autos saveve， so let's delete that and delete all this。Delete all this。

 you don't need any of that， it's all gone， you see we're not doing any auto saving anymore。

Another thing I'm going to remove is over here in my Moji art app just to clean things up。

 remember I had this pallet manager code where I was taking over the whole screen to join the pallet manager so you could see the three paned split you let's sit here to all that that was where we could see multiple stores。

So this is more what our app would look like normally right here。All right。

 so where do we go from here Well， to make our app go from being the kind of app it is now。

 which by the way， let's take a look and see what our app can do now。

 we haven't added the document support yet。

![](img/39cf309056382b11c93a4e49325ac696_6.png)

Here's my app and I can say add another window here， get a nice background。



![](img/39cf309056382b11c93a4e49325ac696_8.png)

Is on here， and I can also go up here and say add another window and look what happens if I click on my own icon。

I get a second one， so now I actually have two windows here looking at the same document you see this one and this one over here。

Same thing， and they both have the truck， that's because both of those windows are looking at the same assigned state objects here。

This。Default emojiR document。 since they're seeing the same view model。

 they're showing you the same document。 Now， they each have their own zoom and pan because they are separate views。

 but they're both looking at the exact same document。

So that's kind of neat that you could have multiple windows like the same document。

 but it's not as neat as being able to have multiple documents。

 so the first thing we're going to do is change our window group right here to be a document group。

This is the thing that's the base of all the document behavior and you'll remember that this one had a little argument config。

 which is the configuration of it， and instead of using our default document that we have up here。

 instead we're just going to grab our view model out of that config。

And then the other thing we're going to do is have another argument here， new documents。

 which has a little closure that creates。A new document so that when the user says new document。

 they get it。And when I do this， there's two things。

 one I can get rid of this default document because I'm not using that anymore now my document。

 my view model is coming out of being created from these files， these document files。

 but you also see I got big old error here， a really important error， let's look at it。

Emoji art document needs to conform to reference file documents。

 That's that whole protocol I was telling you about。 And once we do that。

 we're going to have opening and closing documents。 That's all we have to do。

 So let's go over to em MojiR document and make it implement that Here it is。

 MojiR document currently implements observer logic。 So we'll make it do reference。

File document as well and if we click on reference file document actually to get the little documentation for it。

 you'll see that it's a protocol that inherits from observable object， so only observable objects。

 only view models can be reference file documents it also means we really don't need to say both of these things because a reference file document is by definition also an observable object inherits from that。

Now， of course we need to implement this protocol， so let's use our fix， go up here。

 fix now we got some of our reference file document here， not all of it right。

 we got the readable content types， that's nice， that's the thing that we're going to fill out with emojiR。

And we've got our init to open up a document， but we didn't get our saving ones。

 the file wrapper things。 Where are those Well before it can generate those。

 it needs to know the type of your snapshot。 you see the very first line snapshot equals some type And for us。

 I'm gonna have our snapshot be a data again， I could have my snapshot be an emoji art and convert it to a data later。

 but might as well do the JSON encoding in the snapshoting process in this other thread。

 Now as soon as I do this data now I'm going to get this error that I still don't conform。

 let's fix again。Fix。Now I've got all of the functions， all five things here。 you see Sshott。

 file wrapper， the readable content types， the init， and then， of course。

 the little type alias for what type we are， By the way， once it generates this。

With this return value， you actually don't need this type alias anymore because it can infer it from the snapapshott return type。

That your snapshot is a data。What error we got here cannot find type UT type。

 that's this uniform type Iifier and to get that to work。

 we actually have to import our uniform type identifiers module。So don't forget that piece of it。

 you'll be kind of frustrated why it's not working if you don't import that。

 it's a different module there。So let's just go through all our errors here what's this one static bar declaration requires an initializer well of course we have the static bar it doesn't say what it's equal to I'm going to have it be computed right here I'm going to return an array with what I want to say instead of JPEG or PDF or something like that I want to say emoji art。

And that's the content types that I want to be able to read and write， by the way。

 and of course this doesn't work because it says UT type has no member emoji art has Jpeg and PDF no no problem go up here extension。

To UT type， and this is where we have this static let emoji art equal a UT type that is exported。

And uses thatedduu。tford。cs1p。gt so I've just added another static and if we go by the way and look at UT type in the documentation。

We can get a look at all the other。Ones we have here， you can see there's quite a few of them。

Different types。 look at them all G files， gift， G Jpegs。MP3 files， MP4 video。

 so these are all well known UT types and we just added another one emmoji art in our app is now also a well known type。

Look at that no errors， so now all we have to do is fill out these little gray code blocks to implement the actual functions and let's just start at the top and work our way down the snapshot really straightforward we know how to do this we need to return our model as a data so that's just our emoji art as a JSON。

And there has a little error here， call can throw， but is not Mark with try。

 of course we know that turning our emoji art into a JSON can throw。

 that's a throwable little function so we'll just say try by the way we don't need return because this is a one liner that returns this。

That's it What about this one， the file wrapper around here。

 well we have to create a file wrapper and we write a regular file。

 so we're just going to return a file wrapper。And one of the ones down here see it regular file with contents。

 instead of directory with file wrappers， we just want a regular file with contents here and the data that we're going to provide here is our snapshot。

Because our snapshot returns a data and then it gets passed back to us here and we're just going to create a regular file with it as our file wrapper。

 that also is a one liner that can just be returned。Okay， this is pretty easy。 What about this guy。

 So here we are creating a。Emoji art document， or view model from this read configuration。

 Let's take a look at this read configuration that was given to us file document read configuration Look only has two things content type。

 which is UT type so for us that's always going to be emoji art that's the only type we say we know how to open so that's always going be emoji art and then it has this file which is the file wrapper。

 if we look at file wrappper it's got a whole bunch of stuff that has to do with doing the raft thing directory of files。

 but if we look down here at the bottom。It's got the one we want。

 which is give me this file wrappper's regular file contents。That's the bar we want。

I'm going to use that。And here me say。If I can let data equal this configurations files regular file contents。

 then I'm going to create my MojiA document from it and by the way if it's not then I'm going to throw that error and that coco error that we saw on the slides error dot and you can see look at all the different file errors that you could possibly throw with coco errors。

 lots of different things in this case it's basically like a corrupt file if we got this far must be corrupt or something how else would we not be able to get the regular file contents。

The good asking for the data。And if we have that data， it's JSON data for emoji art。

 How do we create it， I'm just going to set my emoji art model equal to an emoji art。

From that JO and of course this can throw as well， so let's try and you can see that these things rethrow so I don't have to do catch or try question mark or anything。

 and'll just rethrow it up out to the document system or whatever。voila， that is it。

 really four lines of code that actually do anything to make our app readable and ridable。

Let's go take a look。Our app is completely different we just run our app no pallet across the bottom what's going on here instead we're getting this nice。

Essentially， document。UI for managing all of our documents and look at that create document I told you we're going have UI for creating document Also look along the left here we can browse documents on my iPad here。

 here's my emoji art document directory go inside here and that's where it's going to put all those but I could also be saving my files on iCloud Drive I don't have my simulator signed the iCloud here so I'm not seeing it。

 but I can save it on iCloud just as easily as I can on the local file system。

So let's go ahead and create a document here。let's add a background to it。Here。

 we've got a nice background， add another truck out here， and then we go back here。

And there it is and oh oh， that's a little scary， it says down there 31 bytes。

 I don't think that's big enough to describe that URL and that little truck and in fact yes。

 if I open it again， I lost everything。Why no one do。

No undo means no document saving right so we got to go back and implement undo to make this all work Now how are we going to do undo here。

 I'm going to do that trick I told you before about the undoably form going to put it down here in my intents because almost always all of your undo code is in your view models intent area。

 That's why we segregated out like this give it a nice space。

 So we always know where we're going where things might be undoable。

 So let's put this little private funk undoably。Perform and it needs an undo manager to do its work。

Do manager， and I'm going to make it default all to nil。

 So if you say undoably perform and you don't provide an undo manager。

 it does it without undo they can't do undo and then we need to do it the actual thing to do。

That right here。In here， we're going to do this trick that I showed you since our。

Model our emoji art is a struck a value type that can do this thing where I say let my old emoji art。

Equal my current emoji art。Then do it to change my model in some way。

 and then have the undo manager if we have one register for undo。And the target here is myself。

And the handler is going to pass myself back to me。

 that's what this argument to the handler is is whatever this target is。

 it gets handled thrown back to you later when you're undoing and we can do trailing。

Cloose your notation here。And inside here， if I'm trying to undo it。

 I'm just going to have myself's emoji art equal the old emoji art。

And hopefully you all are comfortable with this idea of how closures capture the state outside of them。

 right so old emoji art is a local variable and this closure captures it and actually keeps it in that closure in the heap。

 just waiting for some day later when the undo happens and then it can use this local variable inside the closure。

That's kind of why we call these closures， it creates a closure of all of the named things that are around when the closure is declared like this。

And if you don't really understand what I'm saying there。

 you want to go back to your reading and reread the section on closures。If we want to be nice undo。

 we could do a name for this for each of our undo things so maybe we have something here action。

 which is a string and then when we're registering we'll do undo manager set action name to be that action so that we can get undo paste。

 undo copy， undo add emoji undo set background we'll get the actual word for it and heck while we're here let's do redo as well and all we need to do is redo is wrap this in an undoably perform so I'm going to have myself do an undoably perform with that same action。

And with the same undo manager。And all we're going to do for the do it is to do this。

So redo is just undoing and undo， that's what redo means。We have this great undoably perform。

 All we need to do now is go and put it in all of our intent functions。

 So for set background right here， that's a good one。 let's do here undoably。Perform。

And the action here would be set back round。With some undo manager。

And where's this undo manager coming from， Well， like I said， we can pass it as an argument here。

 maybe undo with undo manager。Or we could hand it off from our view to our view model at some point。

 hopefully before any of these undoable things happen， right。

 maybe on a peer of our view or something like that。

 but again I'm going to pass it in separately to all of them。And in fact。

 I did that for all of these other ones just to speed things up。All these other intent functions。

 you see all these， I have a little。Under our undoable， intense。

That are exact same thing I haven't changed anything except I put an undo manager argument and I do undoably perform around each of them and I even kind of put nice names on them like when you add an emoji。

 it'll actually you know if you say add a helicopter it'll have add helicopter so when you say undo it's going to say undo add helicopter。

 which is kind of cool。Now this has made it so that our view model is entirely undoable。

 but our view， of course， has to provide the undo manager so we got to go change all the places we call our intent functions here in in my version of the app here it's only set background and aoji in your apps it's more resize move you have other intent functions that you called because your homework I'm just going to go back to my。

What your our document view。Go down to。Our drag and drop。Here it is。

 This is where we set our background it's going to say。Undo with。

Undo manager and same thing with our aoji。Undo with。Undo manager， and where do we get this？This。

 we get out of that environment， so we go up here。That's an environment。

Back slash dot undo manager bar undo manager。I can't remember what we really showed these ads on environment things。

 but if you。Option click on it you'll see a description of outsideign environment and you see where it says environment values right here。

 let's go ahead and look at that so here's all the many outsideign environment things you can do to find out what's going on in your app。

So there's quite a lot about what's happening within within your display。

 what's happening with scrolling or state， you can find nothing happening with your scenes。

 all kinds of stuff here， and this is really the new way of finding out what's going on in your system。

 as I said， not that notification way。All right， so let's run see if this works。



![](img/39cf309056382b11c93a4e49325ac696_10.png)

All right， bring this guy up。Let's go， add。

![](img/39cf309056382b11c93a4e49325ac696_12.png)

Our windowindow。Let's drag this out。Okay maybe we willll zoom out a little bit， let's get up。

Is that a taxi cow I can hardly even。See it， something like that。And back。

And how many bikes does it say now？Oh， is that three238。 Oh， that looks good。

 It looks like it might have saved that file。 Let's go look。Wila， it saved it。

And we can do another window here。Go add another window and again I'm going to click on my own icon。

To get one here， create a new document。Called it untitle2 in this case。

 let's go get this different background。Zoom out a little bit。

 let's put it maybe good place for helicopter or my favorite emojis。Right here。Of course。

 I have to zoom in and out when I drive and drop them because I don't have resize like you guys have。

We have two documents right here， this one and this one， and we can go back here and for example。

 rename these by pressing and holding， see you press and hold， say rename this one taxi。

And then press and hold on this one。Rename， can you can say how there it is。

 this is we'll say helicopter。Now as one last thing I'm going to do。

 which is to add an undo button because we have this nice undo where we can put things here and undo。

 but I how do I do undo I don't have any U I So let's put a little undo button let me go back to my。

Ting a few here， I'm going to put it right here， I'm going to say toolbar。

 add a little toolbar along the top and I have undo button and I wrote the code for this undo button I'm going to put it in my extensions over here under our undo button it's really quite a simple little button。

 if you tap on it， it does undo if you long press on it then it shows this pop over and this pop over will' show you the undo option if you have it or redo if you have redo so you tap to undo。

 you long press if you want to do redo basically。So let's see this in action。So dot toolbar。

 did we see dot toololbar before， I think we might have dot toolbar。

A toolbar adds these buttons along the top。 I thought， I think we did do it。 Yeah。

 when we did the plus button right in the palette list， we did a toolbar button。

 So there it is up there。 That's the undo button up there。 If I drag something out， like。

 let's put a golf course right here。And hit undo。 who， it went away。 And now if I press and hold。

There's redo， I can put it back。And if I add a couple more golf holes out here。

 actually let's add hockey goals instead。Hockey goal stopping people on the road there now when I press and hold over here。

 I'm going to see undo the hockey goal and if I undo that now I have the choice to undo the golf thing or redo the hockey goal。

So this I'm showing you on iPad， we don't have our Mac version of this。

 but on the Mac version you'd look in the edit menu and it would be showing you undo and redo like this。

And you can see why it says undo the golf course right， because back here in my emoji art document。

 when I did my undoably perform and addd emoji， I said add emoji。

 I put the actual emoji that I added， and that's why I'm seeing it over here。This is almost working。

 We definitely have multiple documents， we can kind of open them in different windows， etc cea。

 but there is one kind of weird thing， watch this， look at my palettes down here。我。Okay。

 I'm sping through my palettes， it's changing it in both windows。

I don't think that's what I want because one document I might be， you know。

 doing some COVID thing or something on the other document I'm doing vehicles like this。

 so I want them to be separate。 So why are they staying the same Well。

 they're staying the same because in our app we made our pallet store be global to our whole app So all the scenes are getting the same pallet store So when you change the cursor index it's changing that in all of them。

So that's not what we want。 How do we fix that easy。

 we're just going to get rid of this here and we're going to put it down into the views so each view here。

Is going to have its own pallet store。 Now， I'm going to rename this shared to make it clear that they're all still sharing the same backing store。

 They're all sharing the same。User default is the user default with the name shared now and so any changes we make to the pallets are going to affect all of them。

 but it's just that cursor index that we're clicking through is going to be different for each of them so this is kind of almost the perfect situation where we're sharing the pallets among all our scenes but each has their own little cursor index so let's see this in action。

Oh got an error here why do we have an error well because I was injecting my pallet store from the app level all the way down。

 so now I want this injection to happen in each view because each view has its own pallet store。

 but it still wants to inject it down into all of the pallet choose and all that。Here we go， ready。

It's separate over here， separate。 What about if I delete one over here。I deleted it here。It's gone。

 is it gone over here？Yeah， no more animal faces， however， we got a little bit of one problem left。

 which is this so you got animals on both sides， watch this。Deleelete。Oh。

 it didn't delete the animals on the other side。You see， they've got animals over here。

W what's going on， we know they're sharing the same backing store and in fact they are because animals is going to be deleted here。

 the next time this P store looks in the user default， in fact， watch， if I start cycling around。

 it's gone。It's just that it didn't instantaneously delete it because it didn't notice the change in user default。

 so that's where this notification thing comes in， we're going to add the notification。

 let's go over to our pallet store and when we initialize it when we first create our pallet store。

 we're going to ask that notification center， please notify me if user default changes。

So we just say notification center default， bad observer。We want this one down here。

This little space in here so you can see these arguments better。So the queue， we want the main queue。

 of course， object， we don't care anybody who sends it to us。

 and the notification we're interested in is userdefaults。d change notification。And then inside here。

 we're going to get this notification passed to us so we can look at its user info， but we don't。

 we don't care what the user info is， and what are we going to do when user default changes？

Our pallet store。Kind of like its underlying backing store changed we want our views to update well how do we make views update object will change that send this is an observable object the object will change that send says go make the views update because I've changed in some way。

Now it's interesting here that we have an error this is something you're not going to see a lot in value programming in fact you'll never see in value programming this only has to do with reference types like classes and what it's saying here is the reference to object will change in this closure requires you to explicitly use self in other words it explicitly wants me to say self dot object will change why is it want me to be explicit there。

Because this closure right here。Is going to capture self。So that closure sits in the heap。

 the notification center is holding onto it， just waiting for the notification to happen so it can call that closure and that closure has a pointer to this pallet store inside of it。

It needs that pointer so that it can stand object will change right well that has got some problems going on because that is going to keep this pallet door in memory forever。

Until we remove observer， right， we never remove ourselves as observer。

 then we are always going to have this p store in memory。

 so that is a problem and we're going to fix that in a second here。

There's a couple of ways to do this， if we took this out， another fix that is offered to us。

 I'll show you。I hit here and sit fix， it says capture self explicitly。

 but we did this one reference self explicitly， but we could capture self explicitly like this。

And it put a little square bracket itself， do you see it right there？And this is a little notation。

 this is not an array or anything， this is just listing things to capture in order to make that closure work。

 so we're explicitly saying I know I'm capturing self there so that when I use self inside when I do optical change。

 we know it's captured and we're going to use this to our advantage in a second here because there's going to be a problem with this。

Now notice I'm also not getting the little cookie and removing this observer， but I want to do that。

 but let's just make sure this works first and then we'll go back and do that。All right。

 here we go again。You get another window。This guy， this one。We go。 now we got vehicles in both。

 ready。And will delete w， it deleted it in both and this object will change do send and it updated the UI。

So that did fix it。But like I said， we have a little bit of a problem and it's this。

 I want to do this thing where I say observer equals this。

 and then I have a little assign state private var， which is of that observer。

 which is this MS object protocol weird thing。Then I want to remove it。So I added it。

 when do I want to remove it， I want to remove it when this pallet store disappears when this window is closed and we're not looking this document anymore。

 I don't want to watch that user default change so there's actually a cool little function only on reference types called D in it it's like the opposite of a knit this gets called when you leave the heap。

When no one else is pointing to you anymore。You get thrown out of the heap。

 this gets called perfect time for me to say if let observer then notification center。Thatt default。

 remove observer， that observer， and I'm going to put a little printing in here so we can see that this is working。

 remove observer。Let's go over here。Ron。And openness。And out a window。This one。Now。

 when I close this window， when I hit close over here， we should get something on our console。

 right that says remove observer。Shouldn't we， because it's going to get denniited， so let's see。

Close。Over here， oh， some things happened， but I don't see a a remove observer here。Never got called。

Why is this？This is because that D in it never gets called because this palace door never leaves the heap because that closure always keeps it in the heap。

That closure up here， this one right here。It captures itself。

 so there's no way for the power store to ever leave the heap as things are currently designed。

And that's not good How do we fix that Well， there's a really cool thing we can do here and say make this a weak self weak self means don't keep this thing in the heap。

And if no one else is interested in it， they just set this self to be nil。

 so it turns self into an optional。An optional that no longer keeps that thing in the heap and now we have to say since it's an optional。

 we have to say self question mark do object will change because it might be set to nil so this weak' self gives the opportunity for the thing to be removed from the heap out from under this closure and we're being safe here in that when the closure does run later if it were ever to be called later after we've left the heap that will be nil and so nothing bad will happen。

Be cool， now we run。Close this。Go back here。Ah，Re observer， it actually did remove the observer。

That's good so that last little piece that I'm telling here about this。

 we used to have to worry about this all the time because we didn't use value types in the old UI kit world so we were constantly having this problem where things were being kept in the heap and we had to weak sell and make sure they now we hardly ever have to do that because almost everything's a value type so you don't have this problem with the value type because the value types aren't in the heap so how could they possibly be kept in the heap this is not even an issue for them。

Okay， perfect timing right on time today。

![](img/39cf309056382b11c93a4e49325ac696_14.png)

And if you have any questions， say and oh， by the way。

 if you haven't hooked up your device to this in preparation for next week to just test it。

 please do that now。
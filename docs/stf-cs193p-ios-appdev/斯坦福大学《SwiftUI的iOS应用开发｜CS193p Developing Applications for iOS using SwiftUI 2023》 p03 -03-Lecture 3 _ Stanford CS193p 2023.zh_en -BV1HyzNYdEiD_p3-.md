# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p03 -03-Lecture 3 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p3-

It's probablyably the most slides you're going to see me do in a row the whole quarter long。

But we do need to cover some basic architecture before we dive into the next part of the demo。

 which be the second half of today， Any questions before we start。Okay good， all right。

 so lecture number three here we got two huge topics to talk about one is MVVM。

 which is the architecture， the design paradigm that you're going to use to build an app and then the Sw type system。

 the different types that are in there likestructs and protocols and all that so those are two major topics and then I'm going dive back in the demo and we're going start building the game logic for our memorize app right we need all the things about what happened when you click on cards and all that we need to build all that。

All right， so this MVVM thing， what's that all about？Well in Swift。

 to say that it's important to separate the logic and data。

 the part of your app from the UI would be a dramatic understatement is really。

 really important Swift UI in a way is all built around this idea that you're gonna have your data and logic what your app does over here and then you're gonna have the UI that chose that to the user and interacts the user is a separate thing that's just really important the logic and data side of it so in our memorized app it's what happens when you click on a card and are the cards face up or face down all that stuff we call that part of our app the model you're going to hear me use that word model hundreds of times all that stuff lives in the model we call the stuff we've been doing so far across the UI or sometimes we'll call it the view because it's our view our portal onto the model。

Now the model， it could be a single struct， it could be a whole SQL database full of stuff。

 maybe it's some machine learning code， maybe it's like a rest API over the internet。

 it could be almost anything， it's conceptual， our model is conceptual。

 it's not just a single struct， although with our memorized app。

 it is going to be a singlestruct because this is super simple， little first starter app。

 but I don't want you to think that your model couldn't be way， way more powerful and complicated。

Now the UI part of our app really is just like a parameterizable shell that the model feeds one of the best phrases I've heard for the UI is it's a visual manifestation of the model because the model is what your app is it's a memorized game that's what it is so all that logic is in the model the UI it's just how you show that to the users it's a visual manifestation of it right and so you really want to think of it that way。

For what we've done so far is face up card count these things that we've been putting in outside signed state。

 they belong in the model， those are all things about the game we're playing right so we don't want those things so we knew why we'll be getting rid of them putting them into our model。

Now one of the things that Swift does super important。

 one of its responsibilities is to take to make sure that anything that changes in the model appears in the UI so it's got an enormous amount of infrastructure to do that for you right that's one thing you have to understand you're not really going to be responsible that much for making whatever's in your model appear in the UI Swift is going to mostly do that for you you just got to give Swift some hints about what in the model affects your UI but once you do that it's going to do it so don't worry too much about that part of it mostly you're going to worry about separating these things out。

If we separate these things out， the UI and the model。

 how do they connect to each other because obviously they need to talk to each other well？

I've boiled it down to three different ways of connecting it here， which's probably some other ways。

 but I think most things would fit in one of these three categories。

So rarely one way we could connect the models to the UI is to have the model be outside state in a view right。

 I mean if you put the entire model all the logic app into an outside state in your view。

 then obviously your view could access it well this is extremely minimal separation。

Probably wouldn't do that。 I'll talk about when we would do that soon。Number two。

Is that the model is only accessible to the UI via a gatekeeper so we're gonna have a gatekeeper and that guy's job is to keep the UI in the model communicating with each other safely coordinating communication。

 This is the main way we're going to do it。 This is this MvVM thing I'm talking about。

 number two here is 99% of the time you build an application。 And then I throw out number three here。

 which is kind of a hybrid of the first two， which is there is this gatekeeper。

 which we call the view model there。 but sometimes it'll allow direct access to the model。

 It'll have a var this public that the UI could look at that bar and actually talk directly to the model directly to the memorized game。

 That's a hybrid。Of the first two essentially so how do we know which of these things to do Well the easy answer is always do number two Okay that's what I'm going advise just always do number two。

 especially when that previous slide when I said the model could be SQL databases and all these things you definitely need number two in that case because this thing in the middle this intermediary it's the thing that knows how to do SQL and all that you don't want your UI to have you make SQL calls your UI is just presenting information on screen it should all be simplified for your UI So that's why you would always do number two。

But a very， very， very simple model， even simpler than our memorize。

 it might want to do this Asign state solution， especially if the view maybe just comes on screen really briefly。

 it has a little bit of data that maybe it's like image data that it's showing or something like that and then it goes away and it's gone forever then maybe you don't need this extra gatekeeper guy and then the third one is maybe you're in between like our memorized game could be that hybrid you're gonna to see when we build our memorized game Yeah。

 we have this intermediary， the gatekeeper but a lot of time the gatekeeper is just forwarding on requests from the UI directly to the model so you could make the argument just let the UI see the model directly and still have the gatekeeper to do some other bookkeeping I don't like number three because as your app grows you start building a tangled mess where your UI is now talking directly to your model through this gatekeeper guy and it just doesn't grow very well。

 It doesn't。It's not a flexible growth system， so even though you might have to do a little bit of work to protect your model from your UI with this gatekeeper that seems a little bit like why are we wasting our time doing that。

 it still can be worth it especially as your app grows and becomes more powerful and you'll see that in the demo because I'm going to show you both number two and number three in our demo。

We're going to talk about number two， this MVVM， the reason it's called MVVM that stands for model view view model。

 that's what the MV and VM are。The model， you know what that is， I told you。

 your view is another word for the UI， and view model is this gatekeeper in the middle that I was telling you about。

It's kind of interesting name view model because his job is to connect the view to the model and be the gatekeeper between the two。

 so I kind of like the name view model， weird word， but that's what we're going to see。

So here's a picture of MVVM， there's my model over there。

 here's my view and we'll get to the thing in the middle in a second so let's talk about the model in this whole architecture。

 The model is UI independent We are not even going to import Swt UI in our model。

It is truly UI independent in our memorized game it's going to play a game of memorize with anything on the cards JpeEG images we're going to use emoji。

 but it can do anything it's a generic UIless memorized gameplay thing UI independent important to understand that part in the model。

 as I said before， it's the data of your app like whether the cards are dropped out or down and the logic like what to do when you choose a card which cards that flip both and stuff。

 it's both of those things combined。It's very important to understand that the model is the truth。

For all of these things so if you want to know the data or you want to perform some logic。

 you have to talk to the model， there's no copying this data somewhere else like into this view model thing I'm going to show you or certainly not into outside state in your UI。

 you would never do that you if you want the information you go back to the model it's the truth。

If you always anything the model knows， you should always be asking the model for at all times。

Now let's talk about the view， what is the view Well， the view， as I said。

 it's a visualization of the model， the view should always look like what the model looks like。

Whatever's happening in the model， you should see that on screen。

The view because of that is stateless you see it doesn't hold any state it's just always showing you what's in the model so it doesn't need any state that's why any state we have in the view we market at sign state so we realize oh we have state in our view that's not good this is supposed to be stateless it's okay to have at sign state in very rare circumstances but it's unusual and it's especially marked like that so that we are aware that we're doing this thing that really is rare the views are mostly stateless they're just showing you constantly what's in the model at all times。

😡，You probably already noticed this， but our view is declared。Okay。

 we don't write the code for our view in an imperative fashion。

 you guys know what the word imperative means that's like。When you're writing code。

 you're calling function， then you call another function to make something happen and then you call another function you're writing imperatively。

In our view， you noticed， we just had our var body and we just listed the views that when our UI。

 we modified them with view modifiers， but we basically just listed them。

 They're just sitting there of Et of。You know， cards and the buttons， we're saying what it is。

 we're declaring this is our UI， and then the model data drives it。

Any part of our UI that can vary is changing because our model is changing and causing it to change so we declare so it's declarative and that results in this word we see a lot which is reactive that's because the UI is reacting to changes in the model model changes UI updates because it has to because it's always showing what's in the model。

So now we can talk about this MVVM thing and it works like this。

We're going to introduce another a into this thing， the view model。

And the view model is going to bind the view to the model。

 It job is to connect these things to each other。 So this line that comes across right here says data flows this way。

 read only right， because this is a stateless and it's being fed by this。

 This guy up here is going to intervene in this line and he's not only binding them。

 he's also interpreting them like this might be sQL。And this doesn't make SQL calls。

 so it's the thing that has to make SQL calls， turn them into normal variables or something so the view can see them right so it's doing interpretation of the model。

😡，It also is a gatekeeper between these two guys， it's protecting the model so that the UI can never do anything bad to the model。

 and I'm going to show you how it does that， the main way it does that in a minute here。

 so it's a gatekeeper and interpreter it's the thing that controls the flow here between these two things。

So basically that line goes up and through there。And the data flows through the view model to the view。

How does this all work？Things happen in the model and it's this view model's job to notice those changes so again。

 SQL database it's got， you know it's signed up with the SQL database to get notified when things changes。

If it's a swiftstruct， fantastic， swift， really good at telling you when something in astruct changes。

 you'll see why that is when we talk about the type system。Whatever it is。

 the view model has to notice the changes now when it notices the changes。

 it then publishes to the whole world something changed。In the model。

So once the view model says something changed， that's when Swift UI kicks in and it looks at its view and says。

 oh， something changed， did anything changed that means I have to redraw and it's super smart about this。

 it's only going to redraw the views that actually were affected by this change and it does that for you so you don't have to worry about it you don't have to do anything to make that happen。

so this is the process notice change， publish it changes happen system Swift automatically figures out which views have to be redrawn and it draws them how does it know this by the way how does it figure this out again it's all about dysfunctional programming about the fact thatstructs in Sw our value types we can see when they change very easily it's built in to know when they've changed that's all because of Swt Swift enables this to happen and we're not going to talk about the mechanism for that right off the bat here but it's pretty cool。

I'm just putting these things here like these view modifiers and these little assigned things with like assign states。

 but they're different I'm just putting them up here for future reference。

 I'm not going to talk about any of them right now。

 but later in the quarter when you see me talk about one of these things you can think back and say oh I'm gonna go look at that MVVM slide and see oh yeah that's right it was an MVVM thing so we'll be talking about like observed object and observable object publish in the next lecture or so but some of the other ones a little later in the quarter。

So that's the basics of MVVM going this way。But there's a big question here。

 what about the other way， Because the view， you can tap on things。

 you can swipe and do things the user can interact here。They could affect the model。

 So how do we go that way Because I told you this arrow only goes this way and it does only go this way。

 Well， that is done。By processing user intent and that's another thing the view model does when someone taps on something in the view they call a function。

 the view model saying the user has the following intent for example in our memorize game the user wants to choose this card you're not going have a method in view model called tapap that would make no sense that's a UI think you would have a method in view model called choose this card you see it's a user intent。

 the user intents something semantically meaningful to the model but then once again the viewmod's job is to turn that into a bunch of SQL calls or something like that whatever makes sense to express that intent in the model。

 so it's very important this idea of intent now sometimes。Intent like choose a card our model。

 or memorized model it's gonna have a choose card method that's just fundamental to it so it's gonna to seem kind of weird like our view model is hardly doing anything it's just forwarding the message on but it's still being a gatekeeper it's still you know binding them together it's just that our first app is really simple but the second app we build you're going to see that there arent intent that can't be mapped directly to a single call in the model but anyway that's what happens here is intent Now what happens when that intent is called in the view model well of course the view model modifies the model whatever the user to express whatever the user's intention is。

Then what happened before happens again， the model changed the view model notices the changes。

 it does all this publishing of something change， the view does its thing and it updates same exact thing as happened before so when it comes to going this way。

 the only thing is the intent once you call the intent view model updates the model and then the normal update happens right our stateless UI which is reflecting the new state of the model after the intent that we expressed。

And that is it， that is the entirety of MVVM， so let's go to the next step in architecture here。

 which is the type system。Every language it's just so important to understand the fundamental types that are involved right because everything that the language can do really flows out of those fundamental types。

 so let's talk about the types here now I don't have time because I want to do some demo today to talk about all the types so I'm going to talk aboutstructs and classes and then these don't care types which are kind of fun and then protocols I'm going to talk half about protocols that's why I say protocol part one I'll talk about more protocols in lecture5 or so I'm going skip enums not because enums arent important they are enums are important type but I just want have time to do everything and I do need to talk about this last type which is functions and yes。

 I'm talking about types here functions are types。So let's talk about these types。Struck in class。

 very similar。 So I'll kind of compare them in these first two slides。

 They have almost exactly the same syntax。 And you've already seen it， right。

 you saystruct content view， colon view class very similar， But inside there。

 they both have vs that can be stored like is face up right， just a stored variable， normal variable。

 they also both have computed vrs like var body right， we compute the value of the var。

They also both can have constant lets， a number of lets versus v。

 lets are constant bars are variable。Both have functions。

 and I just want to remind you here that in functions our parameters here can have names like。

Oper in and buy right there and that they can also have two names。

 an external name and an internal name， the blue is external name and the purple internal name right we use this on the inside callers use the blue name you saw that in the last demo。

And they both have thatstructs and glasses， I have all these things。

They also both have something we haven't talked about， which is initializers。

Now we saw a rounded rectangle when we created it， we created it with a corner radius of 12 or whatever。

 but when we were typing corner， it also was offering us this other one。

 corner size where we could kind of do both the X and y of the corner， not just a radius。

And that's because the ground rectangle has two initializers。

 And you can have any number of initializers you want， and they can all have different arguments。

 You can take whatever arguments you want。 as long as you initialize yourstruct or your class。

 That's fine。 Now we haven't needed any initializer so far because and I'll talk about this in the next slide。

 we've used the free in it。 you get a free in it withstruct and classes。 They're different。

 but you get a free one。 And we' have been using the free one。 Like when we created our card view。

 we use card view open parenthees content。 Remember that。

 we got a free in it there that allowed us to call that。 and I'll talk about that in the next one。😊。

In the demo we're also going to write our own in it because it is flexible and nice to be able to specify your own arguments to create your thing They're really simple it's in it looks just like a funk。

 but you don't say funk in it you just say in it and you can have as many of them as you want。

When we create our memory game over there， memorize game。

 we're going to initialize our game with the number of pairs of cards we want。

Even though number of pairs of cards is not going to be a var。

 we're going to have an array of cards instead。So what's the difference then instructorstruct in class got all these things all exactly the same what's the difference well this is really important to understand and what's good about this is understanding not only from the Sw language perspective but because most of you are coming from objects running your programming and so you're used to classes and Sw task classes and so when I'm comparingstructs or classes it's kind of like comparing what you know to what you're going to be doing because you're going to be doing 99。

9%structs in this class。Okay're the only thing we're going to use a class for， believe it or not。

 is that view model， that gatekeeper thing， that will be a class。

 but everything else will be astruct。All right， so the biggest difference betweenstructs and classes is thatstructs are value types。

 and classes are reference types。Then think raise your hand if you think you know what that means Okay a few of you so a reference type means that when you have a variable that is a class you don't actually have the class stored in that variable you have a pointer to it it lives in the heap somewhere you have a pointer to it you have a reference to it right a reference type and that's what you're used to okay almost all languages Ob languages they have reference to their classes now what's good about that。

Well， I guess what's good is you could have 20 different pieces of code all sharing the same class right。

 they all have a pointer to it， they can all modify it and everything What's bad about that you could have 10 different things all pointing to the same class and they're all modifying and how do you know one one's not screwing it up for everybody else。

So that's the good and the bad of reference types it turns out Swt believes the bad outweighs the good so they don't use reference types for most things in Sw so what's the alternative value types what does that mean Well a value type means that the storage for the variable is actually right there and there's no pointers it's actually stored right there and it also has some things that fall out from that for example。

 when you pass a value type to a function you get a copy of it in fact even when you assign one variable to another you just made a copy of the other one。

Every time the thing gets passed around or signed， it's getting copied， copied， copied copied。

 not pointer， and why is that good because if you give a copy like he passed into a function and then that guy mucks it up。

 he only mucked it up for himself， he didn't muck it up for you because you gave him a copy and he worked on it。

Now the flip side of this is it requires a lot of different thinking okay and when you're writing your code。

 for example， if you have a struct and you want to give it to a function to modify then you would give it to the function they would modify it and they would probably return you the new one right so the return value of the function like here's that new thing you wanted and you saw this actually probably when you looked for array shuffle right there's a shuffle which shuffles the array in place that only worked if you have a v and then there were shuffled。

With a D on the end， which gives you back a new ray shuffled。

You see and that shuff old that's more the kind of swift way to do it now we'll talk about in a couple of bullet here how we do the shuffle in place when we have this going on I'll explain that in a second。

 but that's important to understand and then again at class again you're passing around pointers so everybody's pointing to the same thing they're all sharing it。

Now， another interesting thing is if you have a class and you're handing out all kinds of pointers to it。

 when do you know how to clean up the memory right。

 when do you know I'm done with this object this class well in a lot of languages you do garbage collection right？

You go look in the heap， you do a mark and sweep， nobody's pointing to this I'm going to clean this up whatever your strategy is turns out Sws strategy is a great one it's called automatic reference counting where it keeps track in real time how many pointers it are there to this and when that count goes to zero it immediately cleans out the memory so it's really nice even though we don't use classes it's still really nice that they have this feature in there so what happens on the struck side on the struck side it uses copy on right。

Because when I say that you're passing these things around by copying them， I mean allstruct。

 if you had a of a million items in there， when you pass it to a function， it would copy it。

Now that would be。Impossible if theres really a million items in terms of performance right。

 you can't copy a million item array but arrays are strucks。

 so what happens is when you pass it behind the scenes。

 it's not actually going to copy it until someone writes on it。

And once someone modifies that array now they get their own copy and so's the whole thing is based on copy on right now when you have copy on right。

 guess what？You know when things change。You have to know when that array changed or how do you know when to copy it Well I told you before in the MVVM。

 Swis's really good about knowing whenstructs change。

 it's built into Sw to know this struct was actually changed。

That is just fundamental because it can't do the copy on right otherwise。

 and without the copy on right， constantly passing around arrays of a million is would just not work。

 it just wouldn't work。And this works incredibly well swift incredibly efficient if you build your code。

 even if you're processing large data set， it's really。

 really efficient because it does this copy on right built in to the very language。Now。

 as you're probably getting the message here，structs are the foundation of functional programming。

 they're right at the base of what we're doing， classes are the basis for object orient programming。

Why do we choose one of these styles over another？Well。

 objector of programming came out of this idea I talked about it before。

 data encapsulation right want encapsulate the data of a real world concept or thing and then associate all the functionality with that data by encapsulating it all into one structure with functions about that data right that's what object or program is。

 I think we can all agree and it adds this idea of inheritance because some things are very like other things but with you know some minor modifications and so we can inherit from them and then tweak them to be a specific instance of that or whatever that's great。

But functional programming has a different take on it。

 which is that it's not the data that we wanted to encapsulate it's the functionality so all we're going to really do is describe how things behave I've already said this before right like how a view behaves or whatever we're going to describe that formally in our language and then we're going to be able to know which things can do what and we can ask them to do it and when it comes to the data that's behind the scenes like how an array stores its things who cares okay what we know is that an array has a whole bunch of functions and bars on it that we can call it'll do certain things and we don't really care about the data and we never care about it and if it totally changed its mind about that we wouldn't care too。

So functional programming it's fundamental to functional programming that we have these value types because in functional programming。

 one of the real things we want is provability you all heard about this concept of provability in computer science you want to be able to take a piece of code and prove that it will do what it will do no matter what no matter what environment is in or whatever you can't do that not be programming because you don't know who's gonna to have a pointer to your class who might mess the whole thing up。

 increment some counter or do something like that whereas's here with functional programming you can because you're always passing a copy of the thing in there and it does what it does and it returns the modified thing back so its that's always going to happen nobody can interfere with that from outside that function will always do what it says it's going to do and you can prove it with test cases or whatever can prove what is doing so it's just a different way of thinking about programming much more about provability and functionality based design and this is。

more about data encapsulation and kind of modeling the real world。

 although we can model the world just as well and functional program because in the real world。

 things behave like certain things so we can do it there too， just as much。All right。

 so there's no inheritance at all instructs because inheritance is limiting you know if I had two things that are kind of similar。

 but one's not really a subset to the other， it's like they want to share some functionality but they can't see they can't inheritance is limiting unnecessarily so there's no inheritance。

 there is inheritance of course in this side because Swift is trying to be an object or language and also it has to have backwards compatibility with the old way of programming in iOS which is all classbased so it has single inheritance。

 regular normal inheritance that you're used to。This in knit thing I told you you got a free in knit they both get free in its totally different astruct the free init you get is an in knit that initializes all of the variables is face up and content all of them right and of course if any of them are defaulted then you don't have to put them on there but you get that's what you get if you don't do in your own init you get a free one that has all with a class if you don't do your own init you get one that does none of them。

But it's still required that all of them be initialized。

 so the only way you can use the free inI in a class is essentially is if you put is equal to something for every single variable they have to all have default values because you only get this free one so in classes we almost always have inIs because this is such a weak free init instructs we often don't have inIs because the free one is so powerful。

In object programming， the objects are always mutable， you have a pointer to them。

 you can always go through that pointer and change the object。😡，Dangerous。

 that's why anybody can change your object dangerous。Here instructs mutability is explicit。

If something is in a let， you can't mutate it。 if it's in a var， you can。

 So if I had an array and it's in a var， I can call shuffle on it because shuffle shuffles it in place or I could call aend to add something to it or I could subscript it and assign one of the things to something else because it's a var it's in a var stored in a var if it's in a let。

 things like shuffle don't even exist。Now， if you call shuff fold with a D， that would work， right。

 because that doesn't modify the array， it just shuffles it and returns a new one to you。

So this is explicitly managed， which is really awesome as a programmer to know that you have some piece of state that can be modified or not。

 it just， it's wonderful。法。It wouldSo the question is can I use a let for a class， you can。

 but all you're talking about there is the pointer to thing it points to is always mutable， okay。

 the pointers not mutable who cares right I mean you have the point。Ls are allowed。

 but they don't really mean much over here。So yeah， sostructs are your go to data structure。

 99% of everything you're going to do in this class is astruct we're doing functional programming here。

Sometimes you'll hear me also say because whenever I say functional program I was throw there or protocol oriented programming you could call it that I'm going to talk about protocols in a second you'll see why I keep throwing that in there pure functional programming doesn't have some of the things that Swift does with its protocols。

 so it's a combination a functional programming and protocol orient programming。And here。

 we either use this for backwards cabatibility to the old iOS。

 which none of you are going to be doing， that's six years old by now。Old news。

 or we would use it for our view models。 Now， why do we use a class for our view model。

Here's why our view model is shared， very much shared between maybe lots of different views。

 lots of views want to get at the model。I might have a score view in my memorized game that wants to show the score of the game。

 so it wants to get at it。So you want to have a pointer to the shared view model。

 the shared view model that's looking at the model， but the key here。

 the reason it works here is that the view model is a gatekeeper。

 it has walls up against that are protecting the model。

 right that this whole existence is as a gatekeeper。

 so having a shared pointer to it it's not going to get damaged。Its whole job is to not allow damage。

 it its whole interface， the whole programming interface to it is a protected gatekeeping kind of interface so it's a time where we can take the advantage of the shared nature of having a pointer to it that we can hand out to point at all these views but we're safe because its whole job is to be a gatekeeper。

All right， generic， so I talked about this earlier array right an array of ints array is kind of a generic because you can put anything in there。

 let's talk about how this really works， this stuff。

Sometimes you want to build astruct and it has some data associated with it and you don't care what type it is。

 array， the classic example there， we call that being type agnostic about that type。

 I like to use the phrase it's a don't care because I don't care what it is。Swiss though。

 is strongly tight。Remember I said that that's a problem because you got to know what that type is。

 Swift doesn't Swift does have。A thing that is not typed。

 but it's just for backwards compatibility with that old iOS stuff Okay。

 we never use it when we're actually using Sw so Swift is strongly typed every single thing every variable has to have an actual strong type and then we do that nice type inference to make it so we don't have to type it so much。

 but they all still have a strong type。So if we're doing array and we want to have ints in there。

 we have to have a type for int， so how do we specify this type we don't care about？

Well we use generics and here's what the syntax looks like for generics we're going to imagine array and let's pretend that we're going to write the arraystruct。

 okay we're the authors of it， we're going to need to have variables and functions that are of this don't care type like if I say append to the array and int。

 well that that append methods， its argument has to be a type int。

So I need that type when I'm building my programming interface for array。

 so let's look what it would look like approximately if we were to build our ownstruct array。

 So here it isstruct array it's got its functions and bars in there。

 but it's got angle bracket element。That trirangle bracket element means。I'm array。

 I have a don't care called element。This element can be any type。

Any type in the entire swift type system here， most may be a function， I guess。

 but it could be a certainly a struct or a class or an enum。

And this type is something that array doesn't care what it is。

 but it's going to use it in its programming interface， right， funk append， there's the element。

 it's subtype element。So when does this thing become a real type， of course， when we create it？

When I say var a equals an array of int， now element is an int for me whenever I'm using a。

Element is an int， so a pen takes an int， a subscripting returns an int or sets an ant。

 it's as simple as out。SoYou notice that this angle bracket thing kind of matches what the guy who wrote Struck did。

 angle brackets right after the name， angle brackets right after the name， when you're creating one。

I think the thing that makes this hard to understand is people are like， w。

 I can't really think of an example of when I would use this。It's like array， yeah， I get it。

 of course， but so in our demo we're going to do that， we're going to create our own generics。

 itll make a lot more sense when I do that。Here I just want to emphasize that you could have multiple of these generics。

 so array could have multiple， you can declare as many of these don't cares as you need。

 right to define your class as totally allowed there。All right。

 so this is actually called type parameters because we're kind of parameterizing the array type with that little element thing。

 but I'll call them don't care， I just think don't care is much more visceral like makes much more sense that the don't care。

 I don't care what that type is。Now one thing about swift's don't cares or its generics。

 it really uses them a lot， it's really fundamental to swift and we're going to combine it with protocols and it's really going to be powerful once you throw protocols into the mix of these don't cares。

I'll give you a preview， imagine that you have a don't care that you forced to behave like something。

Now you've major don't care B oh I care a little bit about this and that allows you a lot of flexibility to build programming interfaces。

 we'll see that in our demo we're going to do that in our demo as well and so I won't talk about too much about it but before we can talk about that we need to understand protocols more and again I don't have time to talk all about protocols。

 but let's get a little bit of an understanding what's going on with protocols you already have seen the view protocols so you're probably already getting an idea let me talk a little more formally about it。

Protocol looks like when you see it in code， kind of like a class or a struct that has no implementation。

So here's a protocol called Movable。And it's got a function move by some int。

 It's got a var called has moved and another var distance from start。

But notice no implementation here， the move by has no curly braces after it and the two vs just say get or get set so the curly braces after a var in a protocol just say whether there's a read only var or a var you can get and set that's all it appears in the curly braces there no implementation so a protocol it just a description。

I'm sure you can all make the leap quickly to why do we do this because we're just describing behavior here。

 just functionality， we're not actually providing any functionality。

 we're just saying we want to have things that behave like a movable。

And if you want to behave like a movable， you need to implement movable。

 which means you need to implement move by and has moved and distance from start。

So remember that when we said we behave like a view， we had to implement our body。

 if we wanted to implement movable and behave like a movable。

 we have to implement all three of these things。When you claim to implement a protocol or you claim to behave like a protocol。

 you have to implement all the things in that protocol。Re the way around that。

I use this thing behaves like it's the same way as like I call it don't care， don't care。

 it just more visceral here but conforms to is really the right words when I have astruct that does this colon movable。

 we're saying that portable thing conforms to the movable protocol。

I like say it behaves like a movable， but that's the real words， the real thing would say。

So everyone understand that， that's what a protocol is， just a functions and bars。

 no implementation just so we can say that other things behave that way so we can make contracts between objects basically。

It's also legal to have protocols like protocol vehicle that behave like other protocols it's kind of like we call this protocol inheritance because vehicle has its own var。

 but it's inherited these ones so if I want to have a car which is a vehicle I have to implement all four things。

Because I've inherited both of them， so that's protocol inheritance， that's totally allowed。

You can also of course have your car or whatever implement multiple protocols that just means they have implement all those things I'm just saying here you can have comma。

 another one comma another one and it's actually quite common to do this we'll be doing this in our demo we're going to implement multiple。

We're going to behave like multiple things。So what do we use a protocol for we do this have this thing what do we use it for Well a protocol is a type I'm talking about the type system it's a type and so you can use it as a type a type of a var or as an type just passed to a function var body actually it's return type or it a var but it's type that var byte it's a view something to behaves like a view of course we got the sum in there which makes it automatically calculates it for us from our you know computed property but it is a type view and view as a protocol so you can do that I'm actually not going to talk about that right now even though that seems like wow that's really important it's really it is important but there's other things that are more important so I'm not going to talk about that thatll be in part two of protocols how do we use a protocol as just a type a type of a var or parameter。

So what am I going to talk about？Well， I'm going to talk about the way you've seen it already。

 which is super important， which is to specify the behavior of astruct a class or an enum， right。

 we saystruct content view behaves like a view by doing this。 And we know that when we did this。

 we had some things we were required to do like implement our body and that we got a ton of things。

 a whole bunch of， you know view modifier functions like foreground color and all these things that apply to all views。

I call this。Constraints and gains So this is using protocols for constraintss and gains you're going to constrain somestructs in classes or eums or whatever。

 like constrain them such that they have to implement var body if they want to behave like you。

 but you're going get gains like a whole bunch of functionss or whatever And this constraintsss in gains idea is true for all uses of protocols for protocols are always constraining because they're making you implement certain things。

 but they provide kind of a framework for you then to get a bunch of gains and I'm not going to talk a lot about the gains goes back to this extension thing。

 how we make this happen， but conss and gains is a big part of what protocols are all about right huge gains。

So we're going to see quite a variety of protocols， even in the next couple lecture。

 like identifiable， aable， equitable， custom churn convertible， animatable。

 tons and tons of protocols， pretty much in everything we do。

 we start doing these protocols and we do it so that we can both constrain things and gain things。

Another use of protocols I hinted at before， which is to turn our don't cares into care little bits。

So instruct had been declared as array of element， where element。Behaves like an equtable。

 then you could only put things into a that you could do equals equals on because that's what the equtable protocol is equals equals right when you say that x equals equals y that equals equals is actually part of a protocol Its what called equtable So luckily they didn't define it this way because we can put things into a that aren't equtable and had they done it using this where clause。

 see that magic word where we could constrain that don't care to be a care a little bit。

 and we're going to do that in our demo as well。that makes sense how we could use protocols here？

It's just a way to make our don cares a little more like we care。All right。

 so more about protocols in part two， once we had extensions。

 they're going to be the gains part of constraints is going to go off the charts over there and we're also going to talk more about some and any you know like some view and there's another one called any that are really good for using protocols as types like when you want to put things in array and you want any。

 you want the array to be any kind of a certain thing that behaves like something then you have this nice any。

Keyword that helps you put that in there。 So we'll learn all about that in protocols Part two in a couple of weeks。

There's an overview of protocols just understanding why do we do this protocol stuff？

It's just a way forstruct classes and enums and stuff to say what they're capable of and to demand certain behavior out of otherstruct classes and enums right that's what's fundamentally about but the great thing is that neither side has to reveal anything about what they are they aim to say whether they're a structure or class or an enNM they just have to say yes I implement that protocol so it hides the implementation behind this protocol and hidden implementation is good because you can then change it on you know you can change it without breaking anything because you've hidden the actual structure or class that's implementing something。

It's also a way to add a ton of functionality via this extension thing。

 which I haven't talked about yet。It's really when we say that Swift is all a protocol oriented programming language。

 this is why we're saying this because it's all about the functionality and we describe what the functionality is via these protocols right that's why we say it's a functional programming language protocoliented programming language they go together。

 this is why they go together so much it's how we describe the functionality。All right， function。

 this is the last type in the types this I'm going to talk about。

 the only thing to get from these slides functions are types。They're first class types。

And here's how it works。You can declare any variable or parameter to a function or the return type of a function to be of type function this syntax for the type function includes the arguments and the return type of that function you can do it pretty much anywhere another type is allowed there are some restrictions actually but certainly parameters functions return values to variables they can all be of type function so here's some examples this one here in yellow that is a type called a function that takes two ins and returns a bo。

That's what that type is there's another type， this type is a function that takes a boolean and returns nothing that's what a void means right there This is a function that takes no arguments and returns an array of strings。

And here's one that takes no argument and returns nothing， which is the common type we see。

We can have variables that are of these types， we could have parameters that are of these types that are past to functions。

 they're just types。Here for example， is a variable s。

 its type is a function that takes a double and returns nothing， or here's a function， do something。

 it has an argument what which is of type function that takes no arguments or returns to Its kind of exactly what you expect the only thing maybe you wouldn't expect is notice none of these include parameter names so when you're specifying the type that is a function you don't include the parameter names。

It's just the actual types of their term values and arguments。

So how do we use something like this here's a var operation that's up type function that takes a double and returns a double and here I have a function that I wrote called square and square happens to take a double and it returns a double it returns the opera times the operaran we all agree that that's a function that takes a double and returns a double right well then I can say operation equals square。

Because operation is of type function that takes a double and returns a double and square is a function that takes a double returns to double so I can say operation equal square and I can now call operation。

Just as if were square， I can say let result equal operation of4 and that's going to work because operation is a function that takes a double。

 this is a double and returns one， so result one is going to get it and it's going to be 16 because operation is currently square。

But I could reassign operation and say operation equals square root。

 so square root is a built in function in Sw that takes a double and returns a double square root of it。

 now if I say let resolve equal operation of four， I get two。You see。

 because operation is a different function now。I'm not going to take the slide time here to show this doing the same thing for a function argument because we're going to do that in our demo。

Closures， you've heard me talk about closures， we often call them in line functions。

 we call them closures for a reason， hopefully if you're doing your reading。

 I believe we're covering that in the reading this week。

Closures capture the environment of the variables that exist when the closure is in line。

 right a closure just an in line function， we've seen closures all over the place so far in the code we've done in this class。

There's a lot of built-in support for it I think these view builders were closures when we did the ontaap gesture it had closure when we did buttons action。

 that was the closures， these are all closures I'm not going to talk a lot about closures and how they capture the environment I'm going to leave that to your reading and then you're going to see me doing it in class it'll make sense then its actually turned out have' been on the UI side the capturing nature of closures we don't use it that much。

Mostly if you want to think of closures as just in line functions。You can do that。

But hopefully closures now make more sense how they are arguments to functions， like remember ZStack。

 content， colon， open curly brace， and then we put the viewBuilder stuff in there。

 well content in ZStac is just a parameter to its creation and its type is a function that takes no arguments and returns a view。

That's all it is， nothing special there， that's all it is the only thing that's a little special is that it's a view builder。

 so it has that magic that turns the list of views into one tuple view combined view so it's got that magic。

 but when it's declared it's just a type a function that takes no arguments return to view。

We're doing functional programming here in Swif， these are really really important right closures。

 functions as types， just we're just going to be doing this all the time in this class。

I take some time on this because I know that for some of you it' like whoa， functions as types。

 I can't imagine this but it'll become very natural once we start having some variables and functions that take these as arguments you' be like oh yeah yeah。

 yeah， yeah it's really really cool and it is really cool。All right。

 so that is it for the slides today， like I say that's the longest run slides I'll do all quarter。

 but those are two important things to understand that MVVM thing and all these types and so let's get back to the demo and what we're going to do in our demo is we're going to start building the model for our memorized game。

And then in the next lecture， we'll build our view model and hook it up to our UI。Here we go。

 this is where we left off last time now I'm going to take a little time here to clean out a little bit of the code that we put in there。

 you were allowed to do this in your assignment as well。

I'm just going to go through here and remove these buttons at the bottom。

 I have these buttons down here just to clean up the code because you understand how that works。

 it's not really helping to be in our face。 so we can remove this。

 the spacer in the card count adjusters there。 We don't actually need this to be in a Vt。

 I guess we can just have it be。

![](img/33bed8579d8b25aa750cc2d4267687cd_1.png)

Scroll view。That right， and we don't need the card count adjusters or here by the way。

 one thing I would have done probably， you see how I created a one liner card adder here。

 once I added this I probably would have put this up there in line and and it probably wasn't worth it to have just a one liner there。



![](img/33bed8579d8b25aa750cc2d4267687cd_3.png)

买了。It wouldn't be wrong， but it probably wasn't worth it。

And let's see we don't need card count anymore because we're not adding or're removing。

 so let's have this go back to being the emojis indiceices。Instead。That's everything yeah。

 we're back to working over here。We got our UI， I'm actually not going to touch this UI in this lecture。

 instead we're going to totally do model only and they're totally separated right so I shouldn't have to touch my UI。

 which I'm not going to。And I'm going to create my model in a totally different file。

 so I'm going in Xcode here I'm going to go file new file。

 that's how I add a file to my project a model is going to live in a totally separate file you notice down at the Bible says user interface Swift UI view that's one you might choose if you're creating a view we're not so we're going to choose Swift file you almost never choose these other things unless maybe you're doing unit tests or something like that most of those other things you're not doing C+ plus you're not doing metal probably maybe for your final project you might be。



![](img/33bed8579d8b25aa750cc2d4267687cd_5.png)

But we're going to choose Swift file here。I'm going to call my model memorize game。 memorize game。

 And remember that it is the game。 It is the actual logic and date of the game。

 One thing important to do， see what that group right there is。

Thats speak this is the group that is going to put the file in this is something students really forget to do so I'm can take some time to make sure I make it clear what's happening here is you don't really want to put your files up at the top level where your Xcode Pri is right you know if you look in your directory you've got the Xcode Pro and then you've got something they're called memorize that's this folder that's where you want to put your files。

So one way to kind of make sure you're doing the right thing， so if you click through。

 this is the folder you want to put it in。This one here。If you don't do it。

 it's not the end of the world， but it's just going to start looking a little ugly because you're going to have random files。

 swift files up at the top level instead of putting them down in this nice memorize。



![](img/33bed8579d8b25aa750cc2d4267687cd_7.png)

So we created it here it is， here is our model and our model starts out saying importm foundation。

 not import Swift UI that's because we said create a Swif file instead of a Sw UI view and that's exactly what we want here Foundation。

 that module is just as and ins and ruless dictionaries。

 non UI think nothing in foundation has anything to do with UI and if you myself having to do import Swift UI here in your model。

 you're doing it wrong because models are UI independent they should not have import Swift UI。Now。

 our memory game is just going to be astruct， so I'm going to astruct memory game。

And it's not going to behave like anything for now。

 so I'm just going to put the curly braces after there and when I build my model。

 one of things I almost always do is try to stub out when I'm starting what does this thing do and what data does it have associated with it？

Just to get me started， I might change my mind and use a different data structure or whatever。

 but I want to kind of make that。Cl in my mind， at least as some straw man before I start going。

So our memory game， what the guy I should have left those cards up although they probably wouldn't appreciated that in other classes but and I'm not taking them up and down because they take a lot of hook up there what does it do Well。

 it definitely has a bunch of cards。Can we all agree that we probably need some kind of R cards。

And' the array of something， I'm not sure what， I'll call it the array of card， how about that。

So I definitely want that。 Do we all agree with that。

And what is how do we play our game we basically choose cards right， choose card。

 choose card to matches or not or whatever， so I probably need some function choose a card and it's also of this school type card。

And that's it， that is my entire model because that is all our memory game does。

 it has so bunch of cards， you choose them in a place now in your assignment two you're going to be asked to do some additional things like scoring。

 so you're going to probably add something here the score by an int or something of our int or double if you want double precision scoring you're going to add that。

 but for our basic game that we had so far， this is really all there is。

But what about this card thing， It's saying cannot find type card in scope。

 So we're have to think about what a card looks like in our model。 So let's have a little nested。

Strt called card， you see how I've put this card inside this struct。That's not only allowed。

 it's really good for name spacing。Because the name of thisstruct is actually memoryga。card。

Because I put it on the inside of it。 And that's what I want。

 because I don't want some generically namedstruct card floating around in my app。

 Maybe I'm building， you know， an app that has 20 card games in it。

 I don't want this card to be called card。 I want it to be memory games card， right。

 So this nesting is really nice， but it's almost entirely just a name spacing thing。

 but it's nice for feature other there。So what do we know about a card。

 what kind of information it have well？There's whether it's face up。

 that's a big one we know that is' going to have。What else want I know about a card。

 anybody think of anything？If it's been matched， absolutely， still haven is matched。那是不。

What else do we want to know about card？Yeah， like what's on the card。

You know I know I didn't bring a card today， but remember my cards had Halloween themed things on there。

 witches and spiders and things。 So we got to know what's on there。 So that's interesting。

 We'll call it content。 It's the contents of the card。 What type should this be。A string， a string。

 if it's we're doing emoji right， then string because emojis are strings。

 I guess it could be character， also there's a type in Sw called character。And that'd be maybe okay。

 but I actually have a better idea， let's make this a don't care。Because we're making a card game。

 We don't care what's on the cards put anything you want on there JpeG images， emojis， whatever。

 So let's make this a don't care。 So how do we put a don't care here So first of all。

 let's just make up a name for it， I'll call it card content just type on just making up and I could put it here。

Card content as it don't care。 right， It becomes a note don't care。 But actually。

 that's really not going to work very well because that would mean here I would have to say what the type was。

Because remember， whenever I have a don't care， whenever I use this thing like here。

 I have to then say what it actually is。So that's a little bit of a conundrum。

 but easily fixed because I'm just going to take this and make the don't Care be on the entire memory game。

Now memory game， including its little substructs here。

 all have this don't care that can be used anywhere inside memory game。

That's one thing to understand about don't care is the wider the scope you put it。

 the more it'll apply right to substructs。So we had this look， no errors。

 we had no errors up here and we got this card content， it could be any type。

 it could be a string if we're emojis could be image， JPEg image， it could even be some UI thing。

And I said this was UI independent it can't have anything Yeah。

 but whoever create this memory game is going to be in the UI probably in a view model right the view model is part of the UI by the way the view and a view model both considered parts of the UI they're going create the memory game。

 they could specify a UI I think because their UI that's part of it so here inside here though we are not doing any UI so that's a cool feature too you don't care can make it so that you can use things in the UI kind of through your model but your model is actually still complete UI independent because it doesn't care。

 does not care what you put on these cards。So that truly is just about all there is to do with our model here。

They have five minutes left。Let me think about this。Yeah， let's do it。

 I'm going to create my view model。 we're going to come back to this。

 We obviously haven't implemented our memory games logic， but that's all there is to our memory game。

 It just has the cards。 We choose them， their're face up matched。Content。

 so let's create our view model。 This is the gatekeeper between this。

 our model and that UI that we've built。 Mac looks like this view view file or here do file。



![](img/33bed8579d8b25aa750cc2d4267687cd_9.png)

![](img/33bed8579d8b25aa750cc2d4267687cd_10.png)

Again， it's the Swif file it's not a view view model it's not a view and I'm going to call this emoji memory game because this view model is going to be specific to emoji memory game if I had one that was JPEG image or something maybe I would have a JPEG image memory game。

It is possible I could also build my view model to be generic and it could have a don't care as well。

 but I don't I'm not going to propagate that up， but I could。

 It's totally legal to have don't cares on your view model。

 but I'm not to for mostly for simplicity of the demo I'm not going to kind of go that far with our don't care。

 So this particular view model is going to be specific to emoji memory games。 This the only work。



![](img/33bed8579d8b25aa750cc2d4267687cd_12.png)

For memory games where it's emoji。 So here we go， a create app。

And this one is going to import swiftiftUI because。

Your view model is part of your UI it has to be because remember it's packaging up the model for the UI so it has to know what the UI looks like it has to be part of your UI。

 but I say that but the view model is not going to be creating views or any of that stuff the view is going to be doing that but this will know about the UI and it will know about UI dependent things like colors。

 things like that， images， it knows about that。So this is a class because it's going to be shared amongst everything。

 and I'm going to call it emoji Me game。And a class if it had inheritance would be right here。

 my superclass or whatever we're not going to do inheritance。

 we don't need to inherit from anything to be a view model so we'll leave that off but it could also behave like something so you know something we behave like right some protocol could be here。

 and you could have one without the other， like maybe I don't inherit anything but I do behave like something that's legal too。

The only thing is that if you do have a superclass。

 you want to list it first in that list before you list the things you behave like。

 that's the only restriction there。Now， my view model is the conduit between my model and my UI。

 so it needs connectivity to the model because it needs to talk to the model。For example。

 if the UI the view had an intent like choose a card。

 the view model has to be able to talk to model and express that intent。

 So we almost always need variables here for our model I'm going to call mine model This is a bad name This is a name that you would only use for instructive reasons Okay you would call this something like game because that's what it is you always want to pick names very what they are I'm going to call the model just so you constantly are going to be reminded whats model and what's view model And when we go back to our UI on Monday。

 I'm going to call that variable view model so that you'll be able to see them but which ones which So I have a model and what's its type Anyone want to guess what the type of this model my model is here。

No guess it's a memory game。Of string。Because I said this was an emoji memory game。

And so it's going to create a memory game that model。As a type string。Everybody cool with that。

 I just took that genericotype and specified the don't care， the don't care is a stream right there。

W now let's let's not go over time I'll stop so we have two errors two things to do right off the bat we'll do on Monday one it' saying emoji memory game has no initializers see it has no init and remember I told you that classes only get a free init which initializes nothing and this v has not been initialized so that's why it's making this complaint right here so we'll have to fix that obviously。

And the other thing I'm going to do right off the bat on Monday is talk to a little bit what I was telling you about the partial separation versus the full separation mechanism。

 we're doing full separation here because we're creating a view model in between but I'm going to show you how this model can be protected right now the UI could see this model because it's just a var in my class it can see the view models you see it but I'm going to protect it so they can't see it so the UI cannot see it and then I'm going to。

Be a gatekeeper， so we'll start that off on Monday and then we'll implement the rest of this and then we'll go make our UI use all this。



![](img/33bed8579d8b25aa750cc2d4267687cd_14.png)

And that is it。
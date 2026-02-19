# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P15：-15-15. Functors _ - GPT中英字幕课程资源 - BV12VChY2EF4

But we're gonna go ahead and get started。 Ho functional programmers。 Wow。

 some of you actually showed up on time today。 That's crazy。

 today we're gonna be talking about functors。 we got our house points here。

 Just let me know the word and I will rig it。 Okay， I just， I need I need a little。

 I need a little from you first， All right， so let's see it today。 All right， let's see it。

 but I'm yeah， that's where we are now。 I don't want to buy bober for the same lab twice in a row。

 Don't make me do it。 Don't make me do it。 All right。😊。



![](img/7539e8beb92fd6256a7542b51cbec87b_1.png)

You know， today we're gonna to be talking about puncctors。

 which are a way of modularizing our code in a different way or in the kind of an extension of the way we saw last lecture。

 We had modules。 Now， puncctors are going to show us how we can write code that depends upon modules。

😊，Moddules are themselves not first class in the sense that they aren't values， they aren't types。

 but they kind of live outside of that， but punctors will give us an extension of how to deal with that。

😡，Another note you have an exam next Monday at the normal time during lecture okay the last lecture that you will be quizzed on or tested on is two lectures go as in modules will not appear on next Monday's exam okay because the module's homework is due after after that so we couldn't put it on the midterm but that means you're expected to know polymorphism hops CP exceptions and rex okay so I believe it's going to be a coding heavy exam all right so just letting you know that。

Otherwise with no other administrative stuff， we're going to go ahead and get started today's lecture is going to be interesting because we're going to try and do something called polymorphic dictionaries and we're going to try and do it five times and we're going to fail the first four times and eventually we'll reach how we actually should do it okay so we're going to have our naive implementation up here and over the course of this lecture it's going to evolve into something different okay so just for today sound good to everyone otherwise I can't find my child。

😡，Well， I just had a second here Okay， let's get started so dictionaries， polymorphic dictionaries。

 and then I'll introduce you to some new stuff called T classes and funs， Okay。

 and if you've ever heard of functors in any other context。😡。

Orget about it because it's not what you were talking about today because there' this word is used in a lot of different places。

 that's not what we're talking about all right。😡，Soementtes up there all right so the last time this time is actually in is actually relevant we last time we learned about signatures which are how we can kind of specify the interface of a module it's like the type of a module right it's a description and then we can use modules or structures to instantiate those interfaces by giving the implementation and we saw that we could do in two ways last lecture we could transparently or opaquely ascribe which would either let us have the types be known to the user or not have the types to be known to the user what is the reason why we might not want the types to be known to the user what's a big one shut it out。

😡，Why do we not want that？Safety why。就这样回。So they don't shoot themselves depends against yourself that's actually precisely how you should describe it Yes。

 to have have opaque types is like having a safety on a gun okay。

 but' so we want to have this opaque description stuff。

 but we can choose whether or not we want to do that let's move on okay。

Dicctionaries who's familiar with the idea of a dictionary。

 I think we also use it a little bit maybe in this course So a dictionary also known as a map people use it interchangeably it's confusing is just a data structure that lets us store keys that map to values and I want to play a game with you and the game is let's write a library for dictionaries in SMm and here's gonna to be our signature which you can also see up here and let's run through it a bit but our signature is called stir diic I know I told you that we're going for polymorphic dictionaries right now let's talk about string dictionaries that is dictionaries that map from strings to anything they're singularly polymorphic so the type of our keys is going to be the type string and our type alpha t is abstract I don't know how I'm going to implement dictionaries but we're going to discover that over the course of this lecture and then I've got three operations I want to support on dictionaries I can either have the empty dictionary which is a type alphapha t because it can store anything we don't know yet。

I have the value insert which can give you a key and an alpha value， a key and a value， a pair。

 and I insert it into the dictionary and get a new dictionary okay and then I also have lookup where I give it a key and a dictionary and I get an alpha option I get none if it's not there I get some if it is because this interface makes sense to everyone because this will be very critical that we're using this over the course of this lecture。

😡，This is our type for string dictionaries and one way we can try to implement it is with this structure right here structured dit and we're going to be oply ascribing to St diict in this case we're going to be implementing alphapha T as just a list of pairs。

 a keystar alpha list all right now let's get to it I gave you the empty value which is the empty dictionary is just the empty list but if we wanted to do insert on this list with another key value pairing here's what I'm going to do。

😡，Let's try well okay we know that in a dictionary if I give you a key that's already in it。

 I can choose to do two things， I can overwrite it or I could just not insert I guess we're going to overwrite so if I insert the same key twice I'm going to overwrite what was there previously and in fact I'm going to tell you that there's quite an easy scheme we can use I'm going to just。

😡，Cs cake come a be。On to L。 and then when I look up。I'm going to recurse if I get Neil。

 what do I put？None， right， because I can't possibly find it。Otherwise， if I have x con x's。

Very simply， I'm going to write。If or sorry， actually。Let's see K prime。Coma V cons x's。

Because this is a keystar alpha list， so when I pattern match， I can just destructure that tuple。

Can I here to sees by the way？哎。If k is equal to k prime。😡，Well。

 then I want to just return some beat， right？And then otherwise。If these two keys are not equal。

 well then I didn't find it， I got to keep looking。😡。

Does everyone understand why this like simple insertion scheme should work with this lookup function。

 I say find the first instance of the key yeah。yes， I am。 thank you。

Does everyone see why this should work， I say I want to find it and I find the first instance of something matching the key that's all I do and I otherwise I straightforward relieve recur and that way I don't need to go through and look through all the keys and literally replace them。

 I could I could like go through the list and then replace it but that would be not necessary based on this like I'm still going find the first one with the added caveat that we will keep around all the old entries which could potentially be expensive but I don't actually really care about that at this point in time but this is just the game we're gonna to use all right。

😡，All right， who remembers workspan？Which is a concept that was deep， deep in your prehistoric past。

 so we haven't done work span in a while and we're not going to， but I'm want to ask you。

 what's the complexity of this？There should be an answer that it springs immediately to mind。Oh then。

 right because it's a list and lists are not great for this purpose and let's see I'm also going to give you that。

No， I don't actually。That sum wrong。 Yeah， okay， but yes， so that's not that some right。Oh sorry。

 I put the cases I see my yeah， and also I didn't have an else just ignore what's on there。

 This is the source of truth， all right。Point is oh then which is not great 122 actually last lecture they had something about like does log n really matter I saw in their slides yes it does practically login is basically constant okay so we are going to care about the fact that this is a linear cost。

😊，What's the way that we could do this， Otherwise， How else can we do this。A tree exactly。

 So let's do the first of many iterations we're going to do on this topic and we're going to。

Do it with trees and to do this， I'm actually going to have to use two boards because there's no way I can fit the whole implementation。

Okay， so。First thing I'm going to view。Instead of a keystar alpha list。

 it's going to be a keystar alphapha tree where trees are the classic implementation we've seen over the course of this lecture or the course of this class。

K come a V and then give an empty。All right， so if I want to insert K on the V into the empty tree。

 what do I get？😡，Yes， I get another note where it's just。Empty left and the right subtes。

But I sawre K hum a V。Instead of anything else at my root。

 why because again it's a key star alphapha tree we're not just sooring ins at our nodes。

 we're sooring pairs， right？😡，And then if I wanted to do insert of K comma B。On oh yeah。

 this is the part where I'm going have to erase all of this because there's not going to fit away right and if I wanted an uncertainty to an arbitrary tree。

What do you think is pertinent for me to look， let me have the ups？

H well what do I really want to do here？I want to case， right， yeah？o啊嗯。

I was meeting to say also yes， we want to maintain balance that is for next lecture this lecture selfbalancing trees are kind of a complicated scheme if any of you taken 122 that's going to take a whole lecture to develop today let's focus on just doing the trees and I'll show you how to do it in a balanced way next lecture but today let's assume they're balanced yeah so we if we want to assume we're inserting into a balanced tree and then it'll say balanced magically I might want it yeah。

😊，P song， great request。Yeah， I' give。Yep， sounds good。All right。

 let's case on string that compare both， right？😡，Which is a function that exists that we're allowed to use at our leisure。

 oh yeah， let's make this K prime come up for you。😡，Pay prime， comma V prime。Pma R， right？温调最头。喂。

If I compare K K prime， I have three cases， yeah。And if I get equal。

 I want to just replace it in place， okay， so let's do node of L。😡，And then this one is the new one。

 right， K commma V， so I'll just replace the K commma V。Or。And then if I get less。

 I'm supposed to go。Into the left substrate， right？Someone did you note？

This is again the gross part where now I'm going to have to do of a bunch of word text at you but right but the idea is I want to insert into the left tree right where I'm going to insert with K comm of V again。

😡，And then I'm going to keep everything else。😡，K prime V prime stay R stays。

 so let me actually if I can move。Darn， I usually use some like yellow chalk around here that said okay。

 anyways， the point is that this is the only thing that's changing， right？And then if I do greater。

I want to insert into the right substrate。So I do node， I leave L the same。😡。

I leave K prime comma V prime the same。And then I。Insert。KVR。Any confusion over the insertion case？嗯。

That's okay。And then if I want to look it up， well， I don't have to do much else， right。

 because if I if I'm trying to look up in the empty tree， well。

 I'm not going to find it right so I wasn't in there in the first place so。😡，9。Otherwise。

 and I realize this is kind of a boilerplate and then hopefully if you've been following along in this course like this should kind of feel natural to you and if not that's perfectly fine too it means that me running this out by hand is not wasted。

😡，What is what？boyo little plate， it looks like this。What does Will play mean maybe？

Is that what you're asking yes， okay， I guess I never really am defined that for you。

 But basically yeah， boilerplate is a term where you talk about code that's like dumb and silly。

 And you kind of have to write it。 You have to write it because the computer needs it。

 but like it's very clear what you need to write。 It's boring to write。

 It's like not very interesting。 So I call this boilerplate because。In my mind。

 I know everything I'm doing， but like you know。It's fun。Okay， so if I'm trying to look up and oh。

 sorry。😡，I was too， I was falling too much the mold。

 Remember the part where I said I knowt what to do。

We're actually going to look up just a key right and then if we look at this node we're going to have K prime comma B prime at the root if I want looked that up。

 I got to look at it right I got to see whether they're not there the same key if they're the same key。

 let me go and find let me go take this value out。😡。

So we take that value up to the ball game and then we return some of L be primeed。Otherwise， well。

 okay， if it's less or greater， remember in the binary search tree。

 all I need to do is do one comparison and then go left or right or left or right right so I'm going to go look up。

😡，With cake。But now I'm going to do it in the left substrate。Or otherwise， if it's greater。

 and I could also use a wild card here if I really want。I'm going to go and look up。K二。

This make sense as an implementation of dictionaries on trees。Any questions on this？

Where we're assuming again it's balanced in some way。

 magically there's a fairy out there who's going to just like cast a spell and then make it a balanced tree。

 why not Okay and the next lecture that will actually be true except the fairy will be us。

So these two things are what's changing Okay， keep that in mind so actually let me be clear this。

 this and this， otherwise it's just node of Lr okay otherwise I keep only those subrees are going to be touched。

😡，Okay， well， this is pretty nice。😡，And then oops。There we go。comparison function sorry。

 I actually completely double this and then also I wanted to say again。

 we're opaquely ascribing because we don't want someone to know how we implemented our dictionaries okay。

Okay that's string dictionaries what about polymorphic dictionaries Well I told you we wanted to improve this and make the keys of any arbitrary type because this is actually something you do quite often like maybe you have some kind of more exotic data structure that you want to be able to insert as a key and you want to handle your own comparison function say that you have some kind of like student information that you want to use as a key but only like the student ID like a hash of the student ID and and their name is the comparison like you don't want to necessarily always use just a string you might want more interesting things than that and this happens like all the time。

😡，So that's going to be my motivation for why we want to do that so for instance like one way I wanted to show you this is like if I wanted to make a function that gets your grades it would be kind of silly if like I had to implement like a two string function for every key I wanted to use and then turn it into a key and then try to query the dictionary like that will be kind of nonsensical I would have to do this everywhere I wanted to use my dictionary for instance if I had a dictionary that was only a string dictionary so I want to avoid this kind of code so we're going to hand roll polymorphic dictionaries。

😡，All right， and that's what we's going to be able to look at what it looks like first。

 but first of all， commit this to memory because it's about to go away， all right？

We're going to change it so if I wanted a type of polymorphic dictionaries。

 it's no longer fine for me to say the type of key is string in fact。

 what I'm going to do is I'm going to strike this from the record entirely。😡，Actually， no。

 the first thing we need to do is go back to the safety churchs。

So let's go back to the signature if I have my signature for stir di， I actually don't。

 right because I want to change the my problem so that now and talk to about polymorphic diction。😡。

So let's take this away and let's call it Hol_ di。😡，All right。

 and then I'm going to strike this key type from the record entirely， it's gone， all right。😡，But now。

Instead of having a type alpha T， I'm going to show you that there's something called double polymorphism。

 we can make a type doubly polymorphic and what that means is that instead of being parameterized by one type variable。

😡，Now it's parameterized by two。Okay so this is the difference there。

 and then we're going to have to change this everywhere we use it if only I conspicuously left space。

Oh， actually that's not going to work， sorry， this is actually going to be his officer of data。

But the other places as well okay so instead of accepting a key。

 we're going to accept an alpha to our beta type because alpha is now the type of our keys and beta is the type of our values。

 except now we're using variables for both。😡，Wherever I had an alpha before， I now have。Alpha beta T。

嗯。Yeah， so this is a syntax thing。A do polymorphic type is different so this。😡。

And this are different because。This one looks like a type constructor that has one type variable that we're in saning with the type alpha s beta。

 this one is a type that has two type variables that we're in sanating with alpha and then beta do you see why like like we can't distinguish this between that and then what I just sold you which is a type variable that has just alpha ser beta。

😡，These par is different things like this， it's ambiguous to say this because this looks like you have one type variable as opposed to two。

 So we do this per comma syntax to indicate that there are however many type variables actually in the implementation。

😡，咋没3。Yeah， so basically like like。If I told you this alpha star be， let's make it really concrete。

 let's say alpha star beta list。😡，Is this a type list that takes in two type variables。

 alpha and beta， or is this a list of tus of alpha and beta？Those are two different things。

 the star indicates tuples， so if you say that this should be the syntax for a doubly polymorphic type list。

😡，Well， it doesn't look like that at all， it looks like it's taking in one type component where this。

😡，Is itself the input type？But this is very clear where because it' common。

 because this is not types syn text。 This is the first parameter。And this is the second premise。

We can we can talk about this a little bit more， but I'll basically just tell you your syntax and try to motivate like why the syntaxt was chosen in that LA。

 it's not important that it was it's just important that it happened okay。Well。

 it depends on what T is。Yeah， in practice now。In generalina， but yes。

 so for alpha and beta instead we're going to do Al comma beta t and then here we're going to do beta option。

😡，Because we're returning a value and beta is the type of our values。And then here we take in。

A alpha comm a beta T。And the hearing of taking in the key we taken in alphapha。

Does this look good to everyone so let's read it again Okay I have an alpha comma beta T I have a type that has two type variables。

 The first one is alpha which denotes the type of keys。

 The second one is beta which denotes the type of values all right and an empty is going to be both an alpha beta T because it has any type of key any type of value。

😡，Inserting， I want to insert a pair of a key in a value， I insert it into an alpha beta dictionary。

 and I get back in alpha beta dictionary because it's the same alpha in beta。If I want to look it up。

 I give it an alpha， which is the type of our keys。

 I take in a dictionary which is parameterized by alpha and beta。

 and I return a beta option because beta is the type of our values。😡。

You can replace anywhere you see beta with like like tick V to denote like a type variable that's for variables and anywhere you see alpha you can replace it with like tick K to denote that it's for keys。

 butma basically alpha is keys。😡，And beta variablesvari are values。

Is everyone good with this signature？Yes。Yeah because if I have an empty dictionary it can have any type of key and any type of value right so then that means I'm unconstrained in terms of what my key and value are it's not just like an int inch dictionary that would be a dictionary mapping incidence because an empty dictionary could be anything。

 it could be any type of dictionary so it'll be fully polymorphic in the empty case。😡，嘅。

Any other questions on this before we move on to augmenting the implementation？

Let's put this back up here。And we're going to start down here well all right humble origins we're going to have to make the corresponding changes in the structure that we made in the signature right so a couple things have to change here I'm going to have to first of all。

 it's no longer right to say this is an alpha T that wouldn't satisfy our signature instead it's an alpha beta。

😡，C。And it's going to get a little tight but。And then instead of being a key star alpha tree。

 we're going to make it a alpha star beta tree。 Remember。

 I'm just replacing key by alpha and then alpha by beta， I guess。In the opposite order。Okay。

 but what else needs to change about our code， where else do we make an assumption that is no longer satisfied by this？

😡，Yeah。We need some kind of comparison function right because how else are we possibly going to know where to go because I have to put something here so the next thing I was hiding from you by not looking is what do we do now。

 what do we do in this case basically which is basically the same thing as I have on the board so we're going need to augment our function with the comparison function and if only somebody had left enough room for that unfortunately that person's not me so。

😡，Inert。And then we're going to insert a CMP function here as well。And then everywhere we use insert。

 I'm also going to insert ACMP function。I'm trying to like execute like the very particular edits I'm making okay I'm trying to show you that the implementation stay the same。

 but i'm just looking at and changing certain things okay so make note of where needs to change and why it wouldn't work to change elsewhere so I insert a c everywhere I make a recursive call to insert and also。

When we're doing the strained up compare， no we don't。😡，We do CMP of K comma K prime。

Does this first page make sense， I just augmented it with the CMP function to replace it same thing we did with merge sort all right。

😡，If that's good enough， let's move on to next page。😡，I got to do the same thing here。

Look at this convenient space。And then instead of string that compare。

 I call my real comparison function， and instead of lookup， I call CMK。😡，So the edits look like this。

I insert this， oh yeah， and also I need to change the signature， right？So instead of doing this。

 I'm going to actually have to insert some things， I'm going to write it。😡，嗯。

This is going to be shortlift we're going to get rid of the comparison function really soon。

 so I'm going to tell you is I'm going to put an asterisk here。😡。

Imagine I wrote that on the board remember this is the real signature I'm going to leave this this way for now because I need it for the future。

 but our signature would just change because we've taken an alpha star alpha to order function does that make sense to everyone I'm just inserting the one parameter okay that's the only change。

😡，Otherwise， I'm going to put it back， and then we're going to focus on this。

So that change needs to be made to the signature。😡，And then。

These changes need to be made to the structure along with the one for types here。😡，7 cope of this。

Okay， cool， Z convinced this works like this is working code。

 it'll do the polymorphic comparison thing， polymorphic dictionary thing yeah。That道。唔该我步。Well。

 we're taking as an argument here。😡，I augmented it slightly， you may have missed it。

 I added it as an argument to insert and gel lookup。Yeah， so insert certain lookup。

 always take in the comparison function now。Oh yeah。

 we have to hold yeah if I wanted to use this thing so actually that's a good point so let me let me do the thing I was going to do。

 which is I'm going to say we're done。All right， see you next look， no， this is not it。Why。

 because there's actually a very good observation you， yeah。Yeah。

 pretend I changed the signature to be this one。In which case that now， also let me change up here。

Right。Book。We're now trying to look at for the dictionary or the interface for polymorphic dictionaries。

We ascribe， we type check， but there's something someone said。

 which is that we need to keep around our comparison function if I'm using this library right think about how I use this code well now I need to pass in the comparison function everywhere I use it and that's fine for sorting right because I give it the comparison function one and done it uses it it uses it does merge sort or whatever and then I'm completely done with sorting my list I don't need the comparison function anymore。

😡，But this is an interesting case where it's kind of persistent。

 I need to keep using the same comparison function。😡，This is a real detriment。

 okay and we're going to look at exactly why that is when we look at this。😡。

Consider this code right here。Al I have a string comma int di a dictionary that maps from strings to ins and it's just empty right I can I can do this type annotation and then I want to insert two pairs into it。

 the map from high to zero and the map from the there to one okay。😡。

And you kind of expect what I'm want to get is the root should be high and the one to the right of it should be there right because there is greater than high okay。

 because the cheese compers。Well all right， here's what I'm going to get right that's the picture for you。

 but what happens if I kind of misplace something， I'm always losing things， you know。

 what if I lose my comparison function。😡，I'm going to test your linguistics knowledge here very briefly because I'm going to ask you who heres familiar with an ancient dialect called pigig Latin？

So pig Latin is where you take a word in English。And you move the first letter to the end and even certain A。

 that's literally how it works for every single word。

 And let's say that the end string maps to just a。 Okay， so Latin is going to be At andlay。

 hellello is going to be L O Ha， Okay， and Brandon will be Brandon Day， I guess， but so pig Latin。

If I wanted to implement it an SMML might look like this all right if I wanted to turn a string into pig Latin。

 I'd explode it to get the character list representing it， the empty list maps to a。

 I take the first character off， I append it as a single team to the back which is terrible I turn it back into a string and I can cat with a and this turns the strings into pig Latin right？

😡，And then if I wanted to do a comparison function that instead of comparing strings directly compares them in pig Latin。

 that would be how I implement it， right？😡，Well this is kind of an esoteric funny little comparison function。

 but I'm always losing things so like I open my drawer of comparison functions and I mean to draw a string down compare。

 but really I take the pig Latin comparison function What happens then what happens when I execute this trace Let's see what happens so。

😡，This is a valid comparison function it's total it has the type string star string to order so there's nothing wrong with it there's no basically i'm telling you there's no static way for me to know I picked the wrong comparison function if I try to do this SML andJ will very happily be like yeah sounds good to me。

 let's go ahead and do it。😡，So。If I use it in conjunction with the same dictionary we just constructed。

 the one that had high in there， I want to insert， use this new key value pair called class and then two。

 but I'm going to use the compare Pig Latin comparison function。😡。

So what happens let's do it out loud， okay， so this is our picture。

 what happens is that we have this tree。😡，And I'm comparing class to high。

 so first I take class and I turn it into pig Latin so I get last K。

 I take high and I turn it to pig Latin so I get I ha and this one is greater than that one right so we get greater。

So when I insert this class thing， I'm going to go right， does that make sense for everyone？😡。

The comparison function modular pig Latin is going to be greater。 Okay， so I go right。😊，Now I'm here。

 I'm at a new node there so I compare a class and there in pig Latin so I turn them both into pig Latint I get last k and here ta and you'll note they're of the same length right so what matters is that L is less than H or sorry L is greater than H so they get greater okay is everyone familiar with lexiographic ordering like it's based purely on length and if they're the same length we go character by character until we find the first one that's sum not equal and instead's at a less or greater so L it follows later in the alphabet than H so because they're the same length we get greater okay。

Okay， so if we get grade， that means we go right and we insert it。😡，We get this street。

Does everyone follow my logic？Well， h， what happens if I try to go look for class again。

 but now Ive refound my old comparison function， what's the issue here？😡。

If I try to look up class using the original compare function， class is greater than high。

 so I go right， right？Class is also comparing to bear is less， right， because C is less than T。

 though the same length， but C is less than T。So I'm going to go left。😡，But there's nothing here。

So what is my code gonna return？ It's gonna return none。I'm going to say I can't find the key class。

That doesn't make sense to people， right， like it's there， it's right there。😡。

So the problem I'm trying to get across is we mixed and matched our comparison functions。

 there was nothing that said that we couldn't mess them up and we did， so it takes discipline yeah。😡。

So one thing we could do is we could store the comparison monkey with the tree and then in the empty case we'd only need it once I'm going to call that route B。

 we're going to call that V6 we're going to do things in a slightly different way but that would work albeit it comes with some the costs。

 but it would work。But the basic idea still being that like we don't want to mess this up， right。

 It takes discipline， Okay， and then， and then the kind of like invisible theme I've been talking you this whole course is that discipline is for ws。

 All right， you don't have discipline。 No one has discipline。

 You're going mess up when you're 20 hours overtime working working overtime on yourre beach and in Laguna Bay。

 Okay， my point is like。Discipline never works。 Alright， let's do static guarantees。

 Let's make sure we can never mess up。Enter what I'm going to talk about next， Okay so。

Let's try to make sure we can't mess up our comparison functions。😡，嗯。

And Im want to show you how we do that after the quiz。系。Take a quiz。Like we're good， all right。

Thumbs up， thumbs down， Oh， I do not think it's as hard as when I gave like week two， like lecture4。

 a thumbs up， thumbs， thumbs sideways。Who just like completely doesn't get the idea of representation independence。

 like it's fine if you didn't finish， but did anyone like actually like understand the idea of what that proof means？

Basically， so let me give you a brief description， which is like the things that correspond to three。

 for instance， will be like。有呢。有呢有呢。This would be a valid numeral3 under the unit list interpretation y because the sum of all the length is three。

 right？So the point is that this is equivalent。😡，Under representationpresent In to this list as well。

And it's also equivalent to。This list。Does everyone see that the sum of the lengths of all these inner lists is always three so every single one of these lists is actually fair game and actually you can insert infinitely many arbitrarily many empty lists in there because it won't affect the so all those values are equivalent in the representation way like they represent the same three that's all but yeah you'll do something a little bit more interesting on the homework but that's the idea of representation independence it's just like how can we represent the same things with different values。

Okay， cool， okay， let's move on， I think we actually have a fair amount of time。

 but again knock on wood。😡，That's not made of wood cool so let's augment our signature a bit because what we're going to do is we're to try and fix this problem of maybe not having the same comparison function all the time we want to make sure that we always have a static guarantee that if I insert and I do a success a succession of a sequence of inserts it's going to be okay even if I don't need to pass in the right comparison function okay。

😡，We'll do this by talking about type classes， has anyone heard from someone other than me the language hasskell？

So the language the Hakell language is one where this is a big deal。

 type classes are exactly how how school works and we can emulate it in standard amount。

 okay so here's what we do。😡，Remember that signatures can specify either a concrete type or an abstract type right in the signature that I just wrote for you a little bit ago these types or rather this type is abstract I didn't define it in the signature but if I define it in the signature right remember I had earlier I had type key。

😡，Equals string right if this were still in the signature。

 this would be a concrete type every implementer of this signature must specify that it has a type key where that type key is the same as string okay you have no choice。

 but with abstract types you have all the choice in the world you can implement whatever and your client may or may not see it depending on how it's subscribed to but the point is that the implementer has a choice here the a choice here。

 but the implementer has no choice here。😡，So。We described that opaque description lets us high definitions right I can make sure that no one knows about things but what we want to do is there are other reasons for why we want to transparently describe I gave you all those benefits for opaque description it's not true that it's always the right move sometimes we want people to know a little bit of information and type classes are where this happens。

😡，Okay， so we say that a type class is a signature， okay。

 a particular kind of signature where that signature has a type T。😊。

And operations that can be performed on that type T okay kind of out of out of board space at this point。

 but that it's those two things， okay， a type T and operations on that type T and not to keep you in the dark。

 I'm going to show you a signature right now okay。😡。

So type classes describe structures that can ascribe to it。

 so we say that certain types implement the type class。

 and I'm going to show you that this is a valid instance of a type class。😡。

We call this the ord signature， the ord signature is that of。

Types T that support a compare function on that type T okay any so we can implement this for a lot of different types。

 but the point is that this type T will not be opaque it will be transparent the the person using this type class will know what that type is the point is that we can exhibit this type okay so for instances look let's look at some instances of how we could implement org。

😡。

![](img/7539e8beb92fd6256a7542b51cbec87b_3.png)

So if I were to handily have order written out for you here，notてア么。Which I do。

 And I also have the pig Latin one so let's wait up for that。 but if I wanted to implement or。

 I might do something like let's implement or， but for the string type。So I would ascribe it to org。

And then I would say that the type T must be string right for the string or type class。

And then also this vow compare is equal to string downll compare。

If you're comfortable with partial application， you should be okay with me writing this。

 I'm just saying the compare value is literally the function strain now compare。😡，Oh and also a note。

 I don't think I addressed last lecture， but on syntax， we write Val here。

 even if it's a function for in a signature， we write Val to say that there's a value。

 doesn't matter if it's a function or not， that's dependent on the type。

But it valid for everything Okay， so does everyone see that this is a structure that has a type string and the compare function on that type string。

😡，And this is a valid type class because it ascribes properly I'll also say it's a little bit better because this is a valid total comparison function we could put whatever we wanted here okay but what's important is that like word this is a valid instance but we can also implement other types of let me do it actually let me hand it for you we can also do other type classes for other types if I wanted an ord type class on ins I would write this。

😡，Stt。I would say type T equals int， and I would say Val compare。Equals in compare， oh my goodness。

Okay， so this is also a valid comparison function and a valid type class of ord for in we say that when both of these things a to ord。

 they are instances of the type class or okay so the type class is describing a bunch of structures that might look like this okay。

😡，But the key thing is also that there doesn't need to be one type class or one instance for a given type class。

 right， that would basically be the same as saying there's only one comparison function canonically for a given type。

 which is simply not true。 There are many types out there where like。

 it's not necessarily clear how you should compare them for strings， you might say， okay。

 in compare string I compare。 That's fair dice， right， But like I mix my metaphors that。 but I'm。

What about pig Latin， can't leave out pig Latin， so another valid type class or an instance of a type class will be pig Latin ord。

😡，Which also ascribes to orD。And its contents are that a type T is also equal to string。😡。

But the v compare is equal to a compare pig Latin， which is defined up here， right？

Does everyone see how these structures implement instances of this type class they ascribe okay I'll show you the use for it。

 but if you get the idea which is that a type class is just a type and a operations on that type。

 these are valid instances of the ord type class another further thing I'll tell you I don't remember what further thing I was going to tell you oh yeah the other further thing I'll tell you is we transparently ascribe here why because the structure is literally called string or okay like if I chose to opaquely ascribe this signature thatll mean that people using string or would be forbidden by the compiler to use this comparison function on strings。

😡，But it's called string word the fact that this thing contains strings is not important because this is not like a type that has avariance。

 it's just a type I'm trying to say I have databoard okay。

 so we transparently ascribe in this instance okay。😡，That is type classes， okay。

 and then the Hakell thing wast aside， you really don't need to know anything about that。



![](img/7539e8beb92fd6256a7542b51cbec87b_5.png)

Okay， so we can implement order of several different ways which look like this。😡。

And they are instances of the or type class and then that's why we transparently ascribe Okay。

 so let's change our signature in light of this okay。😡。



![](img/7539e8beb92fd6256a7542b51cbec87b_7.png)

I want to fix my signature， I want to fix my implementation to a particular type class to a particular instance of org。

 okay so to do that， I'm going to change my signature down here。😡。

The first thing I'm going to do is I'm going to。Kill this， which I wrote earlier。

 And then everywhere we see alpha comma beta， I'm going to make next that。

 It's no longer going to be double doubly polymorphic。 Okay。

 we're going to restore just the one type bird。 So anywhere I see this alpha and beta。

 I'm going to just try alpha。😡，Maybe them'm going to do a little better than that。So okay。

 this is actually lot of places， but for instance， first pass。

 let's see everywhere we put alpha beta and we're going to erase it。

And now we're going to just say empty is a type alpha T and this is a type alpha T。

This is a alphapha T， okay， and then also we taken an alpha T hereops。And then now instead of beta。

 we return alpha。And then where we previously had alpha。We're going to have key dot T。

So if you see that there's a structure key， oh I'm sorry。😡，对。

The most important thing is that we're going to put this at the top。😡。

Remember that diatribe earlier about how？Structures can contain structures。

 we're saying that any implementation of polymorphic dictionaries needs to come with a key structure。

 it needs to have a comparison function inside of it okay so basically we're storing the comparison function with the implementation of the dictionary。

😡，So we must have a type class an instance of the or type class with us。

 and then what's the type of our keys is just the type T， key dot T， the type T in the key structure。

😡，So I'm going to do these edits and I'm going to read it out again as soon as I think it's ktic okay yes。

 this is good okay so let's work through it again so if I have a signature polydict I have these things I have an implementation of a type class which has a type T and a comparison function。

😡，I have my type alpha T， which is means alpha is the type of its values and that's abstract。

 I don't know what's inside， okay， I don't know how it's implemented。😡，I have my empty dictionary。

 which is a type alphapha T again， and this actually looks almost identical to what we had at the beginning of lecture。

 it's just that now when I taken a key。😡，I take in a key dot T。

 I take in the same type T that's in here。😡，Does this make sense to everyone？

This insert this look up like the types are good， I'm just like I insert a pair， I get a dictionary。

 I give a dictionary， I get a dictionary， I look up a key， I get out of value potentially。该。

So this is our new signature for polymorphpictic sharingaries。Given that。

 let's go ahead and alter our source。😡，So if I want you to implement this。

 but now I want you to use this。😡，What I would do。Is I'm going to say that instead of having this be doly polymorphic。

 it's going to be you singly again。😡，So alpha T is equal to。And I'm going to have to also。

 because it's in the signature， I have to provide the structure key。

 so I want to say that structure key。😡，And for now， for now。

 let's focus on implementing just one that takes in strings Okay so we're going to say string。😡。

Ord the same string or I just defined for you in that code file Okay。

 I'm going to say that this key is localized to this type class instance。😡，Okay。

 then type alpha T is going to be the type key dot T。😡，Star alpha。Spe。第。Yeah。

Ord is a signature so let's go back to word that's a good question so or is actually a signature so it doesn't know about whether or not people ascribing to it are transparent or opaque the structure acribing to it makes that choice and what I said here is that string word chooses to transparently ascribe to or which means that in this context when we use string word we know very well string word has a string inside。

So in this case， we choose to transparently respect。



![](img/7539e8beb92fd6256a7542b51cbec87b_9.png)

Good question， Yeah， okay。And then for the rest of our implementation， well， what can we change？

We don't need the comparison function anymore。 We don't need a pass1 why because we just care about this one。

 We care about the comparison function inside string word。 So everywhere I had CNP before。

 I'm going to retriike it from the record。😡，What should be here。And then instead of using C there。

 I'm going to use。Tea。Dot compare does that make sense to everyone。

 I have this key structure and it has a comparison function inside。

 so I'm allowed to do key dot compare to get it out。😡，Okay。

 and then I believe that's all the changes that need to be made other than the next page。

So here again， we strike the comparison function from the record。

And localized to the single comparison function now。

 we do key dot compare in the lookup case as well。😡，Is everyone good with this？

We essentially reimplemented dictionaries that take in only a string。

 but we did it using the type class， and I'm going to show you there's a reason why we're doing that okay but does everybody。

 I know this is like a new concept to you like putting the structures in the structure。

 but do you like see why this should like work like intentionally and I'm going to tell you it's valid SML code。

😡，Okay， so we localize everything to the store order and we pretty much restore exactly our previous implementation in the V1 or the V2 this string the tree example。

😡，But that was a lot of effort to go to and I think I have something to say about it here where it's like and these are our changes right I just changed the heat on compare and I removed the CMs but it's hard to highlight the absence。

 So if you get confused go back and look at this this is the difference。



![](img/7539e8beb92fd6256a7542b51cbec87b_11.png)

but there's another issue here， which is what if I try to use it， so let's see this。

So I have indexic3 SL for you here。An implementation which should look exactly the same。

 I've got key do org in my or key acribing a key which sorry， taking in key， which ascribes the or。

 and I have insert and lookup taking in a key dot T or key is the same and Ive stic here where I can choose to ascribe to。

Poolidentt。And this is a valid instance of polyditch just one where the key type is string right that's fine Okay。

 well this should look the same as what's on the board， but what happens if I try to run edge。Okay。

 everything works fine let's go again What if I try to use this I say stir di dot empty is equal to empty and then I say。

 well let me just try to do stir diict dot insert I going to repair like class commude again okay。5。

Bad news bears。It's subtle why this is happening。😡，There is a tight error。 The reason is for this。😡。

Do you agree with me that st diict is opaquely ascribing to Poldict， it's just what it says。

 but Poldict what does Pollydt say Polydict looks like this？😡。

Where in this signature does it say that the type of keys is string？Nowhere。

The fact that we opaquely ascribe is all or nothing when you choose to oply ascribe to a signature you're saying。

😡，None of the types I'm holding you're allowed to know about I'm hiding all of them including the type of keys inside of this subsidiary structure we're too opaque we want to hide the implementation of the trees。

 the implementation of the dictionaries but we don't want to hide the type of the keys because then if I try to insert it'll be like I don't know what type of key that is that's what just happened but I'm telling you that the type error I just got was because SML didn't want me to know about the type of keys。

😡，So how do we fix this？Make key that's a decent idea it will be it wouldn't be that difficult but it's not going to solve our problem which is that we don't know what the type of keys are so in fact we're not really going to be able to solve this without another language feature i'm going to tell you it's called a where type thing so I'm going do this something for you up here but basically if I have a sIG a signature sig I can do this where type T equals T prime。

This itself up this whole line， like everything in pronsia。😡。

This is a valid signature that I can ascribe to， but it's the same as the signature sG only where where where we have that this type T is actually redefined and it's made transparent at type T prime we call I call this selected transparency it's it's called the where type clauses okay so what I'm telling you basically is that。

😡，If I type this， where type key dot T equal string， right。

 because I told you the problem was that we didn't know that type key dot T was string。

 This will publish the fact that。We're asscribing to not Polict。

 we're asscribing to a new signature that looks like polydict。

 but one where this guy is transparent at this type。😡。

Fair enough and if I do ascribe to that now I should know that my type of keys is indeed string okay so again the key phrase to hold in your mind is selective transparency okay opaque makes everything opaque that makes our key type opaque so we make it selectively transparent using this three things remember okay that's it and if I run this code for you。

😡，So I do empty is equal to sugar not empty again， and I try to insert class comm two into it。😡。

It's going to work， it's going to type check because now as the user of this library。

 I know that the type of keys is string。😡，Does that make sense for everyone it's a new language feature it's not super important but like this is like a conceptual I I say this is not super important a lot like I downsco things it's kind of important but the point is that this would not type check without it okay we have to know what the type of key's are if we don't know what the types of keys are we can't use the dictionary we're using a dictionary we're both the type that it is and the type that we can interface with it is unknown we're screwed in that case yeah。

When you yes， well， you mean from the where type I put？Yeah。

 the compiler will look at this and be like， okay， I'm going to ascribe you to a new signature。

 one where key dot T is known to users and where it's string。😡。

So it's made selectively transparent yeah yeah so that's what the compiler will do Okay this is just the minor technical detail we need to get past because I don't want to show you code that doesn't work。



![](img/7539e8beb92fd6256a7542b51cbec87b_13.png)

I try to avoid that where possible。Okay， and then I have this nice little graphic for you here this is exactly what went wrong when I showed you and then what the way that we fix it is that we're just going to。



![](img/7539e8beb92fd6256a7542b51cbec87b_15.png)

Change this swearware type okay， all right， that's the fix。😡，喂嗯。う。We can use it correctly。

Did I just go through all of this effort like an hour of lecture to show you string dictionaries again。

 I promised you polymorphic dictionaries and true you could retype I could literally copy paste all of this code at different types like I can show you if I wanted to reuse this。

 here's what I would do。😡。

![](img/7539e8beb92fd6256a7542b51cbec87b_17.png)

I would copy paste everything here。I would change this from stir to int I would change this from stir to int and I would change this from string to end this is how I reuse it right I showed you I showed you polymorphic dictionaries but only if you copy paste the code entirely I think we can do better all right so after an hour i'm going to tell you this is why we have puncctors this is what we came here for all right so。

😡。

![](img/7539e8beb92fd6256a7542b51cbec87b_19.png)

There's no generality here because we don't have efficient code reuse all right。

 people in like in like job or go or whatever before they had parametric polymorphism you'd ask like okay。

 how can I use like a length function at different types and they' be like oh yeah。

 just so copy paste the source and then change the annotations Yes they didn't have that language feature to like last year or two years ago。

By the way， this hasn't been known for the past 50 years。

 I'm not kidding with you here we've known about polymorphism for 50 years system but yeah that's what they used to do so here I'm not telling you that we're going to do something better。

Let's talk about puncctors， functors， puns， functionss， if you know anything about category theory。

 which I hope none of you do， it's not that okay and if you know anything about math。😡，It's not that。

We have structures and we kind of have signatures as well and by analogy you can think of structures as like big twos of values right not just that。

 but they're akin to values and they have types and those types of signatures right in this kind of analogy we have values and structures and we have types and signatures right they kind of correspond。

😡，But we didn't have functions for modules。Now we do。So if we wanted to draw this analogy。

 functionss are going to be our equivalent of functions for modules， okay functionss are not modules。

 but they are functions that act on modules and we can use this to parameterize our modules by other modules。

ok so。Here's the spin text for puncters， and I I'm not going to write it on the board for you。

 I'm just going to go through it with you。If I want to describe a puncter。

 I give it a name and I give it an orb， it looks the exact same as the structure but I replace this first line。

 so it still equals astruct and I put normal structure things inside of thestruct。

 but the main thing that's changing is that first line。😡。

And then what I'm doing is I'm saying the puncter is named name and it takes in a module called org and that module has to ascribe to this signature sig okay we have a notion of type checking for fe puns as well of course we do so if I if I tried to give this puncter and like a random structure that didn't ascribe to sIG it'd be like I don't know what you're doing like that's not allowed。

😡，嗯。And this is analogous if I did a function declaration where I did fun name taking an ag of type end or something equals something。

 which is declaring a function named name that takes in a value named Arc。

 we're declaring a function named name that takes in a module named ag of signature sake。😡。

Asscribing to say， okay， and the analogy runs deep here， just piggyback off what you already know。

All right， that's how we would do Pcster declarations and then if we wanted to。

 we could create instances of the orb type class out of other instances， the org type class。

 for instance， let me show you。

![](img/7539e8beb92fd6256a7542b51cbec87b_21.png)

Suppose I was interested in implementing。😡，An instance of or， but for twoples of instar string， Okay。

 so I might call this。😡，I might call this in string or。

And what I'm going to say is that it's equal to wherestruct type T is going to be in star string and I'm interested in ordering these things and here's how I would do it。

 I would say compare I1 S1 it's actually a twofold。😡，I2 S2。Equals case int compare I1 i2 of。

 and if it's equal， then we go to string dot compare S1 S2。If it's less， we go to less。

 greater we go to greater。Okay， let me read out what this is doing to you。

If I wanted to compare a tuple of ints and strings， I'm first going to look at the first entry。

 If the ints are the same， then I have to look at the strings。

 and if the strings are equal or less or greater， I just take that so I could case on it。

 but I don't need to。 I just return whatever string that compare returns But if the first int is less or greater。

 well， that means that the tuple is less or greater。 It's kind of the same thing as strings。Okay。

 does everyone understand that this works， like this is how we do it。

But that means that if I wanted to produce an instance of the site class for any type of pairs。

 I would have to write out all of this。😡，For every type， if I wanted to do it for bos and strings。

 okay， I would do this。😡，Os。It's down here。I would do this and I would change this to boo。

 and then I would change this to boo。And then I would do like， I couldn't even do bulldo compare。

 I don't think it exists。 Maybe it does。 But the point is I would do something like this。 right。

 I produce a huge amount of boilerplate code。 Let's not do that。

What we can do is we can define a fun that takes in two ord type classes and then it will put them together okay and here's what we're going to do I'm going to show it to you on the slides。

😡。

![](img/7539e8beb92fd6256a7542b51cbec87b_23.png)

So I would have to do this for every permutation of types and I don't want to do that。

 so let's not do that let's do better， all right。😡。

This is what we're going to do we declare a function called pair or this function is parameterized on two type classes on two structures。

 one of them is an implementation of or， the other one is also an implementation of word it's just like two struck two types and also comparison functions online them。

😡，And then if I wanted to define a type of pairs， it would be the first type star the second type right。

 so this might be inward， this might be a string word， for instance。😡。

And then if I wanted to compare them， I write the same code I did before but instead of using ink compare and string compare。

 I use whatever comparison function was included with both both structures right isn't this fully general。

 I don't make any assumptions on what structure I got I just got two structures that I know can be compared I essentially got two types that I know can be compared。

😡，And if I wanted to use this。I would actually write okay I have an additional comment。

 but basically this is what's happened and if I wanted to use this I would give it into order in string word okay I don't actually have this copy pasted out on my thing。

 but basically if I wanted to do instead of writing in string word out like this I would write this。

😡。

![](img/7539e8beb92fd6256a7542b51cbec87b_25.png)

Structure， because I'm declaring a structure int string or equals pair ord of。

Structure a equals inch ord， and then also to put it here， structure B equals string ord。

The syntax highlighting is kind of being weird， but do you see how this that corresponds like I'm saying in string ord is the funter pair ord applied to both of these type classes I already have in that oh wow。

😡。

![](img/7539e8beb92fd6256a7542b51cbec87b_27.png)

That will work with this。This same declaration， okay？

You can just trust me that it works we'll talk about this syntax a little bit more tomorrow than lab Okay does this make sense to everyone。

 I can write a function that's parameterized on models。😡，系。Yeah。It does， it does。

 but like you you can't really get away from making the initial one because you have to tell it what the comparison function on strings is in the first place because it's not an economical one。

😡，Yeah， good point， though。Okay so pair or we take in two things。

 but something's going on here This is syntactic sugar I'm not going to try and stress it too much for you。

 but basically this is a very historic 150 thing okay this trips people up people are always gonna make a difficulty with this and because there's like a dependency thing or we can only check that this is correct once you submit to the auto if you mess this up it will compile locally but then you submit it and it'll be like error was found and then you'll be like Brandon help me out here like 10 minutes before the deadline and I'll have to help you so pay attention a little bit but we'll stress this more tomorrow lab。

Basically。The thing to know here， okay， the one thing I want you to take away。😡。

there's other things I want you to take away， but one thing I want you to take away Funs taken a single structure。

 Funs only ever taken a single structure at a time。

 same thing with functions actually functions only ever taken one thing is's just that one thing might be a tool。

😡，Or a function。 Or an Indian might return another function。 But the point is that。

This is not taking in two structures， it's syntactic sugar who saying I'm taking in a structure that contains both of these things。

😡，It's not very clear what this is doing but I'm telling you that this is special syntax that has been baked into the SL andj compiler okay what this means is。

😡，If I write something like this， for instance， okay these are not structures， right。

 these are just types and values。😡，What's happening is it's implicitly saying I'm taking in a structure acribing to a signature that contains a type T and a val X of type in this is an invisible signature that some structure is ascribing to I don't know what it's called I don't name it it's anonymous。

 but this is taking in a single structure that contains this。😡。

And another side note which is there's no comma here， there's a semicolon。

 just white space that tripped me up when I was firstist， but I' don't mistake this。

 there's nothing other room spaces。So。We take in a structure ascribing to this。

 that means that if you try to give it like a this is fair enough。

 I think like people don't usually mess up this example。😡。

But something can change if you try to use it like this， so for instance。

 someone might write this and this is correct， but people usually also try to write this。😡。



![](img/7539e8beb92fd6256a7542b51cbec87b_29.png)

People will write， puncter name。Taking an org of type sIig， and this is fine， butll write this。😡。

This will not type check if I try to do like if I did this， for instance。😡，对。

I don't have an example of found my head， but if I tried to do this and I did like。

 let's say structure result equals name of。😡，Ag。This is not going to work on me。

 I have to write this。😡，Because if I use syntactic trigger to define the function。

 I have to use it when I apply it。😡，I can't give too much time for this。

 but basically just be aware of not doing don't don't put structure here if you can avoid it if it takes in just one thing because it's better to do this if it's only taking in one structure okay your tea is will go over this more in depth all right but the point is if it's if it's declared using syntactic sugar you have to apply it using syntactic sugar as well so if I use the structure thing here I have to put the structure thing here okay this is the。

😡，This is the definition， this is the use site。 Okay。

 that's basically what I want you to know right We have to move on them。😡。



![](img/7539e8beb92fd6256a7542b51cbec87b_31.png)

Okay， and so for instance， if I had this thing like this names pun。😊，Whereas type T inalex。

 I would also similarly just write type T inalex here when I use it。If I see it here。

 if I see it back of the declaration， I see it back of the use site， okay monkey see monkey do。

 all right， that's it。Okay。Yeah， I guess we those to move on from that。

 I won't take questions on that I never checked Menty。It's about habit。

Let's see whether or not there's actually a question so always is that， all right。You are pros。

Let's move on。Okay。So here's what we're going to do。

 and we're going to actually go back to our implementation for once， finally。😡，Our signature。

Saays the same the signature is a detail fun is ascribed to signatures。

 but the fact that this signature exists doesn't mean the functer can't ascribe to it okay so to use the punter I don't need to change my type my signature I still have some structure key which is unspecified but。

😡，I'm going to change the implementation because instead of having structured diiced。😡。

What I'm going to write。Is I'm going to write a punter。😡，Instead of being a structure dis。

 I'm going to say I'm going to raise this whole line and I you know you can already see it on the left。

 but I'm a Iright puncter and we're going to call this functer make diict。

 usually we preface puns by Mk it's just convention。😡，And this thing makes dictionaries。

 makes dictionaries out of what， it makes it out of instances of the ord type class。😡，So。

 for instance， I'm going to take in key。Ascribing to or。

And then I'm going to opaquely ascribe to Polydict。😡。

Except I to make I need to also do the war type thing again， because it's still going to be opaque。

Where type P dot T is equal to。She actually sorry， wait， no， sorry， I tested this before class。

 I don't need do that。拜拜。跟。Does everyone see what changed， I now am taking this key as a parameter。

 meaning that now I can change this， I don't rely on just string or。😡。

So I say that structure key is equal to key。😡，The same key structure I got。

And now everywhere else did do I have any remaining references to the string or thing I localized it to earlier。

 I don't， right because I use key dot， whatever， which is that key， which I take as a parameter。😡。

So I' have no more dependencies upon a specific instance of or， I now only care about this guy。

Funter maked okay and now you should believe me that what this is doing is it's saying I can give you a library of dictionaries if you give me a very simple library all you all you need is a type and a comparison function that's it Okay and I can generate essentially I can generate this code for you。

 but at every possible。😡，Intance of a type class doesn't matter which I can still generate this for you。



![](img/7539e8beb92fd6256a7542b51cbec87b_33.png)

So let's see that in action here。And I'm going to have to era all this。

And I might racist this super perspective。Okay， so we're going to go to Dix5。

sml where somebody has happened to have already implemented this for us。嗯。😊。

And the signature should look this same to you， Polly Dickict。But this time。

I have a fun that takes some key ascribing to org okay and here's the syntax for how I would use it。

 I say structure inict。😡，I'll make it a little bigger structure in diict equals the make diict function called on inch ord。

😡，Or if I wanted to string di？I would write string dict is equal to make diict on string or。😡。

Or if I wanted a dictionary of pig Latin， I would say pig Latin dict equals make diict on pig Latin ord。

Okay， very first syntax remember earlier I showed you that to do this wed have to copy paste all this code really now we don't now we just write this down here and it reuse that same code and if I did everything correct this should work。

Wops， oh， I never defined pair word for you， that's right。Yeah， this examples。我 sorry。

And now we have three implementations of dictionaries， okay so I can I can use it for you。

 I can write， for instance， a Val I empty equals in to empty。

I can insert so I can say like v I1 equals indexdt insert。

 let's say one map to two in the empty dictionary。And if I wanted to do int start。

Look up on I1 of or one of I1。So one is in there and maps to two and then two is not in there。

 so I get none Okay， I can also do the same thing with string dictionaries so I can say。😡。

Let me make this a bit bigger， Val SMT is equal to。Sray di dot empty。

 and then I can also do B S1 is equal to Schdt dot insert class goes to two。If I do that on S empty。

 I get an int strain di dot t， right。Oh she and lunch吗。使いたい。Oh， it's because I'm a。

I think I mess something up maybe I shadowed the polydict because there's multiple of them flying around in principle it shouldn't be so actually I'm not sure what' went on there。

I'll get back to you about the after lecture because I'm actually not sure why it's visible either good question Was that the same question you're going to ask？

Yeah， yeah， I'm not sure why， I didn't test this beforehand。

Let's actually it should still maintain thevariant。

 I'll tell you something which is that it' will still maintain the invariant that if I sorry。

 I totally you erased the example I was doing a second ago。

 but if I insert class to2 in the int string not diict， if I try to do pig Latin dit。 inserter。

Of high to one to that same dictionary。Here I still get take it， whoa， okay。

 I definitely mess something up。Yes。Let's get back to one。Yeah， in principle。

 there should be a static of guarantee here， but I think I think I must have messed something up about the syntax。

 it gets picky when you get into functors like functors are like definitely one of the areas where like if you make a small mistake it's going to come back to bite you but in principle there's nothing that stops us from doing this if I got the syntax right I'll post an addendum after this lecture。

 good point。But in principle， pig Latinict and Sdiict have completely different types and they are known to be different to the compiler。

 it's just so this opa description thing is not going on right now。😡。

But that's puns for you any questions on like the syntax of puns are like。

I'll tell you like principally。The reason why we did this is like we built up this idea of polymorphic dictionaries。

 we did it a bunch of times and we saw how it wouldn't work like there were a bunch of tradeoffs basically like either we'd have to monomorphize it or we'd have to write a bunch of code I wanted to show you that like this is the solution that we converge upon with functionss we can do it fairly cleanly and we can restate our modules in terms of other modules this is a general phenomenon if you have code that's predicated on the types of other code you can use this fun idea which is really really strong because it means that for one thing you can predicate your entire implementation on a type that lives somewhere else and you can react to the type and then all of your code gets to rewritten for free it's very very simple to do because again one thing about this is types guide structure right so when I specify。



![](img/7539e8beb92fd6256a7542b51cbec87b_35.png)

This polydt signature it's all I know about the world all I know is just what's behind this interface and then I'm allowed to change this wherever I want I can kind of like build code out of other code such that if I change something downstream or upstream I pay very little price for it ahead of time it's a general principle we're like if you erect these guardrails ahead of time you make your invariance clear you write everything down you specify。

😡，It's very， very simple for you from then on out。Functional programming。

 we push all the work to the first to the first 50% right the thinking about the problem。

 the first 95% of thinking about the problem， writing the code comes pretty simply from that。

 at least， you know sometimes。okay， I will post an addendum about that thing sorry it didn't work but in principle you should have seen oh my god wild type bear pig Latin diict anddict completely incompatible。

 you know， but that is。😡，It for today。And this is the entire implementation。😡，That's it。

 I finished your bit early， but thank you so much。
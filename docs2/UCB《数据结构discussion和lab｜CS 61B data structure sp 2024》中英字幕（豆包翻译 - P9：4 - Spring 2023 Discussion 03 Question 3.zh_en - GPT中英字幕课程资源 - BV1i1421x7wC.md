# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P9：4 - Spring 2023 Discussion 03 Question 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/1c75ad495c066662c77ce0d44922855b_0.png)

![](img/1c75ad495c066662c77ce0d44922855b_1.png)

Okay let's work on question three cardinal directions here we're asked to draw the box and pointer diagram that results from running the following code a DLL string node is similar to a node and a doubly linked list it has three instance variables pre S and next so here I've just put the class definition for DLL string node so you'll see that DLL string node takes in three arguments in the constructor so pre S and next preve and next are both DLL string nodes and S is just a string and then it just kind of sets all the instance variables。

So here we want to draw the box and pointer diagram after we've executed the main method okay。

 and for the purposes of this question， I am going to draw the one DLL string node like this so。

Do like。Kind of a situation like this。 So let's say we have a Dl string node where this string is like high。

 we'll do it like this。 And this is going to be the previous and the next pointers。All right。

 so now that you're acquainted with that。Let's just jump right into this question。So first off。

 we have DLL string node L equals new DLL string node。

Passes in null for previous eatat as the string and null for next。

 so let me draw that really quickly。So I'm going to draw it down here so L。

I's going to point to so notice that I'm not drawing the node directly inside of the box that represents the variable L and the reason for this is because theLL string node is a reference type it's not a primitive right so it shouldn't go directly inside of the box。

嗯。So I'm going to draw and I'm going to make that a little smaller。

I'm going to draw this a DLL string node， this is gonna be PRv。 This is gonna be next。

 we said both of these are null and just to explicitly say that these are null。

 I'm going to draw a slash through them and then S is over here and okay forgive me for this because I know I just said that I'm drawing an arrow to represent reference types right because it's pointing to an object and memory to save space I'm just gonna make the string go directly inside of the box but like for purposes of understanding like reference types pretend like it's not actually going inside the box and I'm just doing this for for like space purposes Okay like so normally this should be like an arrow to eat but because like that gets messy I'm just going put eat directly inside。

Of S， okay， please forgive me。 Okay， as long as you know the difference， that's what's important。

 okay。Cool， so the next line we say L equals new DLL string node null is or we pass in null for pre bananas as the string and L as the next。

 so that means that first of all we need to create a new DLL string node， right？😊。

And the string that's going in is bananas。The previous is null and the next is L so that means the next is going to point to whatever the current L is pointing to right we update L to be equal to this new D string node。

 but at the same time we're pointing this nodes next to whatever L is currently point to so what that's going to result in。

Is something like this I'm actually going to erase these up here because I think you or hopefully you know what these represent。

L is now going to point to this node。Containing the string bananas and this node's next point is going to point to whatever L was previously pointing to which is this each node okay so something really important that I want to point out that was brought up to me by one of my students during discussion that is like honestly really confusing and I fully didn't understand it when I was a student is that L。

Points to this node as a whole。 Okay， it's not pointing to this。

Like preve it's not pointing to this next it's not pointing to the string bananas it is pointing to this DLL string node as a whole okay so the DLL string node is like treated as one unit here that L is pointing to right so I think that's like the main confusion when that happens when i'm talking about these because sometimes when I mean to say like the node with the string eat that's such a mouthful that I just say like the eat which is bad i'll try not to do that but。

Bear with me and I think Josh also like explicitly mentions that when you have reference types it's like pointing to the object as a whole。

 not like any one instance variable of that object， okay？Cool， so moving on to line 13。

 we have L is equal to new DLL string node with null in for pre never as the string and L as the next variable。

 so once again we're going to do something similar where we need to create a new DLL string node。😊。

It's previous as null。The string is never。And it's next is pointing to whatever the current L is and we're going to update L to point to this new node。

 so once again we do something like this。Oh oh， I did not think this through like i'm drawing kind of thick but I will minimize it in a bit so anyway this never node is going to point to bananas because it's next is L or whatever L was pointing to initially right okay and then we have one more of these kinds of lines L equals new DLL string node null goes in for a pre sometimes as a string and once again the current L is going to be this new nodes next so。

😊，We have pre sorry， we have null in forprive， we have sometimes as the string。

And then we need to once again update L to point to this new node whose next pointer is going to point to the never node Okay。

 let me like figure out how to do this。哦。Yeah， so it's going to look something like this after we execute line 14。

Okay， so on to line 15， DLL string node M equals L dot next。

 And I think this is where things start to get a little bit tricky， so。

We're going to have this variable M and M is going to point to L dot next。

 so let's follow our arrows really quickly， so L is pointing to this node over here。

 L dot next is pointing to this never node over here。

 so that means that M is also going to point to the never node so drawn arrow。And then onto line 16。

 DLL string node R equals new DLL string node null in for pre shredded is the string and null in for next。

 So what that's going to look like is let's make R。And R is going to point to。A oops， that's ugly。

I is going to point to a string DLL string node that has null for preve and next and the string is shredded。

😊，Okay， and then we update R to be equal to a new DLL string node that has null in for preve wheat is the string and the current R is going to be this new node's next pointer。

 so we're going to do something similar to what we did with the L's up there where we add oops。

Where we add in。A node。In between。We didn't leave enough space for that one second。

Where we add in a node。In between the current R。And what R is pointing to and that new nodes next is going to point to the previous thing R was pointing to。

So we have null here and the string is wheat。😔，4。Now in line 18。

 we do R dot next dot next equals R once again let's follow those pointers r is pointing to this so R dot next dot next so this means that we're going to set this pointer now is equal to R so it's whatever R is pointing to right so what is R pointing to it's pointing here that means we're going to set this pointer to point back to the wheat。

Noode。Okay， cool and then in line 19， we say m dot next dot next dot next equals r dot next okay。

 let's find m dot next dot next dot next first so we follow the arrows M is point to here dot next。

Dot next， dot next。 So that means we're setting this variable here right， is equal to R dot next。

 R dot next is this。arrow over here and that's pointing over here。

 So R dot next is pointing to this shredded node right。

 so that means we're going to draw an arrow from this next part of eat to the shredded node。Great。😊。

Then on line 20， we see L dot next dot next equals L dot next dot next dot next。 So L。Dot next。

Dot next。Oh let me rettrace actually like even I'm getting confused and like this is like。

I like wrote this question， you know， I just， it's hard to follow along sometimes so L。Dot next。

 dot next。 So we're setting the next pointer of the never node is equal to L dot next dot next dot next。

 So that's going to be the next one over L dot next dot next dot next。

 So that means we're going to draw an arrow from。The never nodedes next over to eat。Okay。

 and now if you were to run this through the Java visualizer。

 you'd notice something really interesting。 So you'd notice that this bananas node disappears from the visualizer Okay and the reason for that is because Java does something called garbage collection where if there's an object in memory and no variable is pointing to it anymore like no variable is referencing it then Java iss like okay。

 we don't need this variable or sorry we don't need this object anymore。

 let's throw it in a trash and free up some space for other variables。

 So I am actually going to erase this from our drawing right like notice how there's nothing pointing to the bananas。

Note anymore， so I'm just going to erase it。And on top of that。

 I'm just going to redraw this arrow so it's a little nicer。Awesome。So on line 21。

 we set L equal to M dot next， so M is pointing over here， M dot next is pointing to the eat node。

 so we're going to draw an arrow from L over to the eat node。

And it happens once again right we notice that the sometimes node doesn't have anything pointing to it。

 so Java is going to be like， okay， time to sleep this into the garbage because we don't need this object in memory anymore。

 so goodbye to the sometimes node。Great in line 22。This is where we start using dot pre。

 and the reason why so initially。When I wrote this question it was originally a singly linkedless question and then I realized that students were not really comfortable with the idea of preve。

 they were only really comfortable with the idea of next but because preve is so important to like project 1 a I just like threw this in there so we can get comfortable with the idea of like using like extra variables that are not necessarily like next right so in line 22 we do m dot next dot next do preve equals R let's follow along。

😊，And。Thoughtton next。Dot next。Dot pre so we're setting this arrow over here with shredded right is equal to whatever r is pointing to so。

We're going to draw an arrow from here over to whatever r is pointing to。

 which happens to be the wheat node Okay， something that I want to point out is that。

This question is very careful to dance around like a null pointer exception and what I mean by that is let's say we did M dotpre。

tpre so we would follow the arrow to M we would say M dotpreve okay that's here dotprive and then Java would throw an exception and be like wait。

M dot preve is null and you're trying to call dot preve on something that is null that's not possible because null isn't like null is like nothing in Java right so you can't really like call an attribute or call a function on something that doesn't even exist。

😡，Which is why like I wrote this question so that it would avoid things like this。

 but that's just something important to keep in mind。

 particularly when you're doing Project 1 a so that you don't accidentally like go too far with like your dot pres or your dot next calls Okay anyways thats like a quick side tangent Okay anyways on line 23 we say L dot pre equals m so we follow over here L dot pre so we're going set this pointer we set L dot pre to be equal to whatever m is pointing to which happens to be the never node so let's draw an arrow。

From the eatve， the eat notes preve to never。Or to the never node， oh， see I just did it。

 I meant the never node， not the never string， it's going to point to the never node。Then in line 24。

 we say L dot next。preve equals L， so we're going to follow along to L dot next。Dot preve。

 so it's this arrow right here。And we're going to point this to whatever L is pointing to。

So L is pointing to the eat node， so we're going to draw an arrow from the shreddeds preve to the eat node。

And then finally， we say r dot pre equals L dot next dot next， so we're going to see R dot pre。

 so we're going to set this variable over here is equal to L dot next dot next so L。😊，Thought next。

Dot next。Is pointing to this wheat node。 So really what we're doing here is we're drawing an arrow from the wheats pre thes the wheat nodes previous variable。

Back to the wheat node itself。Okay kind of weird kind of convoluted hopefully that made sense and you can always put it through the job of visualizer if this was confusing I know I myself got confused when I was doing it and finally now that we're at the end I'd like to reveal the reason that this question is called Carinal directions so if you didn't go if you didn't grow up in the United States like and go to elementary school in the United States this might might not make a whole lot of sense to you but like when you're in elementary school and you're learning like north southea and west the acronym that a lot of teachers use is never eat shredded wheat and if you follow from。

I believe M yeah， if you follow from M and you go through all the next pointers。

 it spells out and never eat shredded wheat and that's like the whole thing with this question。

 I had a lot of fun writing it and I hope you enjoyed doing it。



![](img/1c75ad495c066662c77ce0d44922855b_3.png)
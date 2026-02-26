# 008：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 8.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

![](img/ff42ff085d5a23846742cb907bae8696_0.png)

All right， good morning， good morning。Monday of week three， Monday of week three。U。

So we have the new notes。 If you need a copy， there are some in the front。 normally on Monday。

 I'll put some in the front and also put it in here。So logistically， for this week。

 we have quiz1 redo。So if you didn't do as well for quiz1， you can use this opportunity to make up。

 We don't allow future make up of this quiz anymore。 So todays not today like this week is the。

 the chance to make up quiz 1， okay。And also， we have our P2 due this week， a latest。

 So you should be able to do it ever since Friday。 And today， we'll start with the。

Second data structure for C I C12， which is called linked list， link list， okay。So。

P3 will be about linked list。 P3 is about it。嗯。Number one， link list is not as often used as a read。

That's the first thing。 So when you say I'm， I'm asking a software engineer。

 what are the most commonly used data structures that they use in their everyday life。 Let me say。

 array raise。Stacks and queues。 They rarely say link list。 They rarely say that。

 Im gonna need to use a lot of linked list。Unless you are doing some sort of like database。

 if you are using database a lot， sometimes people use a list more。

 But the idea of link list is they usually provide a supporting role for other data structures。

 For example， if you say I need to have a stack。 and you have a cube。 A lot of time。

 people use a link list to support them。 So linked list is a very powerful data structure。

 They are rarely used independently to say to solve this problem。 I need a list。

 and I will use a link list。 But for all the other data structures。

 people adapt linked list into them。So it's， I would say is， is's a very foundational。

 useful data structure in here。 Okay， so well， we'll talk about the idea of what is an link list。

 and also we'll look at the iters in the link list。嗯。Liinnk list， the ideas is the following。

 So we know about a real list。嗯 so。For a real list。We know a realist is just a。 There's。

 there's nothing special about it。 It's just an array。 And you say array is。

A sequence of bys cut out into different pieces， And each piece is like a variable。

 That's what array rare is。 There are contigs in memory。But for a real。

 it try to solve some of the problems of a race。A raise is， is very nice when you try to say。

 I don't change the data a lot， or I only insert at the end。 I will remove things from the end。

 So a lot of time you say you push to the from the back， you pop from the back of Ray。

 That would work just fine， perfect。But if you say， I need to insert anything into into an array。

 and sometimes you say， I have some data。 I I have to keep this data sorted。

I will keep this data sorted。 And sometimes I， I need to insert new data in there。

 Sometimes need to remove some data。 If your data is dynamic。

 while you have to keep the things sorted， using a array in January is a bad idea。 Okay。

 Its just because when you insert things in the beginning， or in the middle， you have to shift。

 right， So the cost of shifting is the killer for a array。Now。

 the idea of a link list try to solve the problem is like you're gonna break each of the cells apart。

 So now you have individual cells。They are not necessarily next to each other， in memory。

They are linked together。Using references。 So this is a linked list。

SoThis is a rate list or link list that are both lists， except now。

 are these cells next to each other in memory。In linked， you don't have to。Okay， that's it。

 That's it。Now， the。The， the nice thing about Lius is if I need to insert something from the end of the list。

You can have a double link list where you know the end。 So it's very nice。

 If you have to insert something in the beginning or in the middle。

 the insertion part in general is not a cost problem for。Link this has its own problem。

 Thats so in here， this part is shifting。That's the problem。 right。

 I have to shift things around for a race for linked list。 You don't have to shift。

 You't have to shift。If you need to insert anything into a link list。

 you just put that node in here and then just break that chain， make two new connections。

 That's about it。 The problem with link list is seeking。You need to go to the right spot。

To do those operations and going to the right spot is gonna be problematic。So that's the major。

Problem with the linked list。 So a real have its own problem， has its own pro and cons。

 similarly for a linked list。For linked list， normally we say this thing is a node。Right， so。

You have the node， and then you have a reference pointing to the next node。

If you look at this generic node in here。 So we have a node which has a piece of data。

 and then you have this this thing。Notode next。 So inside node， I'm creating another node。

Is this going to be a problem？Can the node hold itself plus something else。Will this be a problem？

It's like you put yourself into yourself， plus something extra。Will this work？

Can someone tell us why this would work？How can I have a node inside a node。有。An objectject， right。

 So this thing is just a reference。How big is the reference 4 byte。 A reference is 4 byte。

It's not like you are stuffing a node object inside another object。

 This thing just serves as a reference that will point to another node object， okay。

And then you can do regular constructors。 And this thing is like the arrow。

So this reference is the arrow in the visualization all there。So if you give me an element。

 I would change it into these things。And then somewhere in this code still inside this node class so we can access next and data directly。

 And we did something like this。In teacher。U a little bit。So。All of these。Two lines。

 N1 equals to this thing。 N 2 equals to that as say N 2 dot next equals to a1。

 Which one of these choices is the correct answer。I think this。That's what we have。

Let's try the vote。 E is none of the above。No， no them is right。Frequencies， A C， O， frequencies A。

Remember starting from this week， I think we're gonna count participation so。

The most important thing is make sure your frequency is correct。 It is AC okay。

What would you vote for for this one， Which one is the correct memory model。冇停。Alright。

 I think we disagree with each other a lot on this one。 There is no majority vote。

 And the most popular vote is the wrong vote。Can you have a discussion， please。

 What did you vote for and why， What did you vote for？Why do the vote for that choice， All。

 I'll stop the vote now。 Okay， so discuss， please。All right。What's the answer in here。

 The most popular choice was a。 The most popular choice was a， right， We have N1。

 N1 is pointing to a node with data 5 by default。 All the next is now to start with。 So we have。

N1 pointing to this node， N2 pointing to this node。 And then this used to be now with this operation。

 N to next equals to N1。 You assign one reference to the other。

 So whatever N1 was pointing to N2 adult next would also point to it。 N1 was pointing to this object。

 N2 was pointing over there。Right，That's how I would visualize it。 So A looks right， right。

 technically。A is incorrect。Technique is is incorrect。B is the correct answer。

 I believe B is the correct answer， because this data is a reference。

 This data is never gonna be in a generic object。 This data is always a reference。

 It will never have the value in there。Okay， so it's not gonna be a， I see A's idea is correct。

 but B is the correct answer in here because data is a reference。So it's next。

 next is also a reference。 M N2 our references。References would never have the value in them。

 They always contain the address of the object，Can we not。Put this into a sa again。

CanCan you use a premium type in the link list not with generics。I mean， if you create any generics。

 it has to be a reference type。 right， If you use the link list from Java。

 that's also a generic class。 So you can't use prim types。You commonly use primitive types on。

At least generic data structures。 But you can say， I just want to create the language with intes。

 That's totally fine。But not with generics。Any other questions？All right。

This is how you connect different things together。 So this is。A key operation in here， okay。嗯。

What we want to do now is we'll look at the implementation of linked list。 That's for P 3。 Okay。

 so here are a few notes。 Here are a few notes。numberer one， linked list。

 they are basically a bunch of nodes linked together using the next in them， okay。

So the node forms the structure of the list in general contains number and the data。 right。

 So you create the link list， not for the sake of creating those nodes。

 You put data inside each of the node。 The data is like each of the data in a array。

 if you think about it。 So instead of putting them into individual indexes。

 Now you're putting them into individual nodes， okay。

And then you should have a reference to go to the next node。 Usually， we call that next。So it goes。

From the beginning to the end。And optionally， there is also a reference that would go to the previous node。

So that's called a Do linked list。In other words， you have a no， you may have a link list like this。

And continue。And the last note in general， has a now， I just use。This symbol in here， this。

 the beginning also has a no。So this is called a doubleub link list。

 Each node would have reference to the next node。 Each node would also have a previous reference to。

 to point to the previous node。Normally， you have this thing called head。

That points to the first note。You also have a tail。Points for the last note。Haad and tail。

 they will be pointing to the beginning and the end of the list， okay。In addition to head and tail。

 you might also say size， how many nodes you have。So。Normally。

 this is a visualization of what a singlely link。 Sly means it only is a one way street。

 W linkless is like a two way straight， okay。So if you look at this part。嗯。Normally。

 this is a link list。 So when you create my linked list class object， you created this thing。

You created this thing。 This thing may have a hat that points to the first node and sides how many things there are。

And this is。Sometimes you put the dummy node in here。 This node doesn't have any legitimate data。

 The data will be no。 And then after this dummy node， you have these real nodes in here。

So this is node number 0。 This is node number one， and the data will be pointing to objects of type E。

That's how it goes。And as well， what is this tummy node， This is the tummy node。

The purpose is this head would never be now。 In other words， it is always pointing to something。

 And having this domin node in here， basically the。

 the first node you have is right after this do node。 This head not being now。

 sometimes can avoid some error checking。 That's about it。

 So you can do exactly the same thing without using a do node。

 But having a do node in there sometimes may simplify your error checking。Okay， but that's about it。

 So in our P3， we will do domins in here。 And the P 3 is a doub linked list。

 So in addition to have a head size， you may also have a tail。

And this tale will be pointing to the last note。In the list。Okay。Any questions？

Does it make sense if I have a singlelyling this， I also have a tail。Doesnt make sense。I said。

 this thing。With the point order。Does that make sense？Does this makes sense。 If you say。

 I have a single list。 I also have a node pointing to the last node。Can you have a discussion。

 Does this make sense。What's the benefit of having a tail。For the list。Anyone have any idea。

Is there any benefit， yeah。啊。So if you want to pan a new node in there it's a little bit easier。

Right， so that's the only benefit。 you say I I want to append something to the end。

 That's the benefit because you're already there。 Otherwise， you have to hop right for linkless。

 you cannot say go to the second element。 You have to hop from the pad hop a certain number of time before you can reach that spot。

 That's why we say seeking is the issue。 You cannot easily just use the index to go to that spot like an array。

 you cant。But normally， for singlely linkedless， people don't care about the tail。 It just ahead。

Keep moving。Any questions。That's a singlely linked list。The question I have in here is， what。

The type of hat in here。Can you vote in。Open it up again。There we go。Can you in。

 what should be the type of this head variable。In the link list class。

 So linked list have two classes in general。 One is the link list class The is a node class。

 Those are two different things。I think we are doing good on this one。

About half of us are getting this one。嗯。What should be the answer for this one？We'll stop the vote。

 We'll stop the vote， okay。A of 94 people who voted in，55 voted for a。So。

It should be a node reference。 It should be a node reference， because if you look at head。

 it's pointing to this object， this object is a node object。 So head has to be a。No， the reference。

As has to be no difference。Are we good。Alright。So。No ver。嗯。No， we're， we're just gonna practice。

 right。So let's， let's look at this thing。Sometimes， we call。A dummy node Sentinel node。

 Sentinel node is just a dummy node。 The question I have is。

 if this is the visualization of a linked list head is point to this node。 This part is data。Right。

And then this is what we have。 The last parts next is now， the question is。

 do we have a dummin node in this implementation？ Did we use a Dmmin node。Can you vote in。

Did we use a tummy note？Did we use a dominote。All right。Or stop the vote。

 A majority of uss voted for a。Yes， can someone tell me why we we use a dummy note。

 What's your reasoning yeah。So head is point to this in where data is now。

 That that means we have a domin node。 Is that the case。 I think probably that's a justification。

 But what if I have a data that is just now。In my link。It's， it's hard for you to tell。

 just by looking at the list。 did I use a a dummy node。 So the first data is now。

 they must be a dummy node。 That's not necessarily the case。 What if my link list allows dummy data。

 like now data in my list。If that's the case。 then this thing is may not be a domino。

 So just by looking at the list is， I would say C， only five of us4 for C。

 I'm not sure more likely than not。 if you， well， you can say this。

 if your list doesn't allow no data， then definitely this is a domino。 we used domino。

 But if I don't know if your list allows you to to do it or not than I'm saying not sure。

So by looking at the list， you， you really cannot now judge。 We need more information。

This makes sense， just be careful in here okay。So it does' mean that if I have now data。

 it must be a domino。 That's not always the case。Are we good？Now。

 this part is the most confusing part， I would say for our students。

 This is when we try to link things together。 This is when we try to link things together。

 and this is a singularly linked list。Okay， this is a singlely linked list。Can I ask。

You to draw the memory model。 So you have the paper。Draw the memory model for this。Note。

 so we have two constructors。But this constructor and this constructor。And then， I'm。In my main。

 I create N1 N to N N0 N1 N2。How are they linked together。

 Can you draw the memory model for this one。You can work with a neighbor to work。

Or you do it this individually， either is fine。Try to come up with the memory model。

 voting in once you' are done drawing。 Okay， I' will keep this clicker on。

 You don't have to worry about it。D it， and then he said， I'm done。Then you come both。

They linked together。Both in once done， drawing。You can definitely look at your neighbor's model and see if it's the same as yours。

The way you realize them might be different， but。Where the reference is puning to should be the same。

Alright， only 28 of us have voted in。If you say， I'm done。The冇天。No need to rush， though。

If you are done， looking at your neighbors。Moern， and this should be。They should be the same。

And try to explain your thoughts to your neighbor。This is what I got。 What did you get。

And then it's okay， if they're different， you figure out who' is right。Alright。

 lets let's look at this one， okay。So N 0 looks like at it is in the beginning。 That's the。Easy one。

 So N 0 is pointing to a node。Where I would say the first cell is data。 The second cell is next。

They're both no， right。 So that's pretty straightforward。

And now we say N1 is pointing to a node where we are passing in data as one。

 and then n 0 as the before node。 So we're using the second constructor。

By using this constructor in here。so data is pretty straightforward。SaN1 is pointing to。A note。

 Now data equals to the data。 So it's  one。 I'm gonna just gonna write it in one here。

 But technically， this one should be pointing to an object。Of one， right。Just write it in there。 Now。

 next equals to before dot next。 So what， what does before4 point to now。Will that be 4。2。

When I'm calling this constructor。Well uss be 4。3。Before he's pointing over here， right？

So we pass n 0。To the constructor before is pointing to this variable， as this object。Say next。

 which means my next equals to before dot next。Before dot next equals with。

What's before thought to next？No。So I'm assigning this while with。哦。

And then the next thing is before dot next， which is this variable equals to this。

 What does this point here。Inside the constructor。Remember。

 inside any Java instance or instance class， there is always this。

 this points with the calling object。This， so this object is triggering the constructor So this points to this one。

 So before do next， which is this variableable equals to this means assign this thing。

With this arrow。No。It's funny you over there。And then the construction caused that。Are we good。

SoN0 is now pointing over here。And similarly for N2。N2 is pointing。To this one with the two in there。

And now， N 0 is passed to before again。 N 0 is past to before again。 So before it's pointing to what。

 what's before pointing to。At this moment， if I'm sitting in this constructor。This object。

So before he' was pulling the oil here。And。This， in fact， also points over here。算了。

Before it's pointing over here。This is plenty over here。Before， which is n0， pointing to this object。

So data equals to data。 that is 2 next equals to before dot next。So next is this horrible。

Equs to B4 dot next， which is this variable。 I'm assigning this value to there。

 This thing is funny0 here。 So what's gonna happen is。It plentyy over here。And then before dot next。

 before dot next equals to this。 This is Poo here。This arrow is broken down。And now。

 the contractor call is done。This is how he goes。So technically。

 what we are doing is we insert our new node right after before。Right now 34。That's the connection。

Are we good？All right， let me。Let me do this。Given this memory model， right， given this memory model。

I want to ask you the following。Is this true or false。A true B false， okay， so。

I'm gonna to ask you a question。嗯。And0 dot next。Is the same as。N two dot next。Is this true of us。

 given this me model， Is this true of false。N0 dot next equals N2 dot next。Alright。

 a majority of us are saying no that different。 I agree， because N， N 0 dot next is this variable。

 The value of this variable is the address of this object。 N 2 dot next is the value of that。

 which is the address of this one。So this is false。Now， let me ask something。

A little bit more crazier。嗯。嗯嗯 one。Is the same as。N 0 dot next， dot next。Is this true of us。

N1 equals n0 dot next dot next。Over the world for A true B false。

Can we have a quick discussion on this one。 please。 It looks like some of us are little bit confused。

Is this correct or no， Can you have a discussion with your neighbor， What do you do vote for。

What do you do before。What do you do with forward here？Did the vote for true or false。Alright。

 so this one is true。 right， This one is true。 Well is true。 N1 is here。 N1 is pointing here。

 N 0 dot next is this variableable。 dot next means。Whatever this n0 next is 22 dot nexts， which is。

This arrow。N1 is pointing here。 N， basically N 0 dot next equals to N 2。Right。

 so you can replace this thing with N2， N2 dot next equals to N N1。 That is true。

But the idea as you can see， you can call dot next， next， next any you want to， right。

 It' just gonna hop forward。Are we good。 So this is how you seek when you。

 when you say I need to go from N 0 to N 1。 You just hop twice。1，2， and you cant go there。

Is there a question in the back no？Any questions in here。Right。So let's write this one， okay。

So we have a single leading list。And you have had， we assume we use the tummy node in here。

And what we are given is， for example， I say， I want to write the add method。

For the single link list， the first one is the index， where you want to add it to。

 And then the second part is the item。If you a at a location 1， this is where you add it。

 So this is location 0， Lo 1， you add it before。This spot。O。So that's how we're gonna insert。

 basically the insert method。嗯。If the index is out of bound， then you throw an exception。

 You can assume we have this construct in here。Okay。So can you write this code by yourself？

The idea you have to hop to the right spot。And then create a new node， break the links。And then。

 insert。That's the idea。 Can you do this yourself。Through exceptions， if index is out of bounds。

Write this code Microsoft。It's important that you can write codes on paper。

Because when you are being interviewed， sometimes they will ask you to write code on a Google Doc or on a whiteboard。

 that is compile ready。In other words， you can't say I need the I D to highlight the syntax。

 They sometimes don't allow it to have it。I wonder to insert this thing。

You can assume you have a hat， you have a size。In the list。If you are done both in okay。

So a lot of times is you practice during lecture and you do something similar。Inindian。And the P。

Vting if you are done， don't forget to do error checking。

Don't forget to update anything you need to update in here。系。Bothing if you are done with this。

You folks， maybe another。Man neither or two。Right，You need hop。

 You need to write a loop to hop the right number of times。And once you gather。

You need to figure out。How to cut the original link。And make the new link。

You can use the constructor。If you want to， that's fine。 Or you can just cut it yourself。

Inith other way is fine。4， once you are done with this code。You have to practice yourself。

That's when you realize what you don't know。Alright， let let's， let's， let's look at this one。 Okay。

 so we have the index in here。嗯，太普。The next page。Index out the bond。

 When do I have index of the bond， If what。When do I have the index out bound？Index as well。

Les than 0。That's one。Anything else。Or what。If you assume you have a size。The index is。

 is it can I say index。Is bigger than equal to size。 Should I have Eco in there。You shouldn't。 right。

 So you in here， what's the size of this list。3， there are three things。

 So this dumy note doesn't count。 Dmmy note doesn't count。So index is bigger than size， you throw。

New。Whatever index， all the bound， the exception。Does this make sense。No， we need to hop。

 We need to hop。 So can I do this。How many times do I have to hop， Where do I want to end up。

 Do I want to land over here over there， Which note should I， do I want to stand on。IThe no zero。

 node one。Which one is better。0ero。Or one。If I stand here， I have no way to access that thing。 right。

 If I stand here， I， I can use next to go there。 So I want to stand at no zero。

 So how many times I have to hop if I start from head。Just once， I just need to hop once。

So can I say this。4 in。I equals to 0， is less than。Index。Plus， plus， I I say。Haad equals to head。

Dot next。Will this work。Ha equals hat dot next。有。Right， so if I change hat。What's going to happen？

Then I， I don't have access to anything all here before， because myself， myself， this head pointer。

 there is no way I know where my list begins anymore。 So you do not want to do this thing。Right。

 so what you want to do is you want to assign， for example， I want to assign head to a current node。

 current。Right， so you， you want to remember where head is without changing head。

 And you say current equals to current dot next。So， you hop。All the way to the right spot。

 this is your current。So if I need to hop once， remember， current you to be here。 H once。

 you are sending all here。Are we good。If index is one， that's where I want to insert。 If index is 0。

I current would be there because this loop would not even run。Right， so I'm not at the right spot。

 What should I do。Can I use the constructor？ How do I use the constructor。I say。Can I just do this？

 This is pretty weird。 There's a new node。嗯。I need the data， new item。And then what。

Or should I pass as the second parameter。Is there current or current data next。

Is it current or current do next？It's current， right？And that's it。

I don't even need to capture the return value。 I think this will just make the link for me。Am I done。

What what is missing。Increase the size。Size plus plus。 So one extra element in there。嗯。Now。

 what if I don't use this， I want to do the connection by myself。 How should I do it。

So we have these three operations， right， this part， this and this。 I would create a new note。So if。

 if Im my new note is listening thing。Note temp。Eales a new node。And I just passing this new item。

 So it's gonna make my， this thing would be now to start with。 So temp is point over here。

What should I do to make the connection， I would leave for you to think about it。

 I think we are running short on time in here。 But if this is temp， right have a new note。

 how do I do this by myself without calling that constructor。Think about this。

 and then we'll review this on Wednesday。I think it's like 9，50 at this moment， okay。

So where don't today， I'll see you on Wednesday。If you didn't get chance to vote in。

 it's time to vote in。 Okay， make sure you are vote in at least once。Before you go。

We job six participantss， so you shouldn't， fact you agree， just don't forget next time。Yeah。

There should be many many。

![](img/ff42ff085d5a23846742cb907bae8696_2.png)

should be there， right week by week。

![](img/ff42ff085d5a23846742cb907bae8696_4.png)
# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P5：-05-5. Trees _ - GPT中英字幕课程资源 - BV12VChY2EF4

Okay let's get started， so we're gonna be talking about trees today。

 trees are a pretty fundamental data structure when it comes to computer science。

 I'd say next lists are the pretty much most important one okay and what we're going find is that a lot of data structures looked like trees so we can generalize this idea of trees in SML to being able to do any kind of data type All right to recap what we did last time last time we learned about structural induction on lists。

 we learned that if we want to prove things about the natural numbers。

 we have to be able to prove things by using the mathematical induction principle the principle of mathematical induction but for lists in SML。

 we can still maintain that ability to do induction by doing a different kind of induction called structural induction and we're going to keep that theme going later on today and we find out that we can do the same thing on trees。

😊，Last lecture we also learned about this idea of tail recursion which lets us make code more efficient at very little cost to the readability because of this idea of using an accumulator and making tail calls which don't have to do any work after the recursive call that won't come into play today but we will talk about that later okay so this is our schedule for today we're talking about trees traversals on those trees we're going to do a proof and then we'll talk about how we can generalize this idea of trees to other data types okay and Ill define for what that means later on okay so。

😊，Talk about trees I already said that trees are pretty much the most fundamental data structure other than lists but you might be familiar with this idea of a binary tree right and a binary tree just looks like this it's a node at the top and a two nodes at the sides and then we store some kind of data at the nodes right if you take it 112 or 122 you should be familiar with this concept but a binary tree might look something like that it might be a little bit more complicated we call it a binary tree because a binary tree has at most two children it doesn't need to have two children always because we see that a three node here has one child。

SNL doesn't have an inbuilt tree type， but that's fine because it turns out that we can just define it for ourselves。

 so to do this we're going to use something called a data type declaration and it looks something like this so we'd write the keyword data type。

😡，This is a key word， so you can't use this as a variable name or anything。

 then we say tree is the name of our type。😡，Equals and now we we're going to say what the constructors are Okay。

 so I'm going to write this and I'll explain to you what it means in a second。

 but we're going to write empty。😡，Or。Notode of。Trees are int。Star tree， all right。

 and the basic idea here is what this means is it is a type that is two things， it is two things。

 one of the things。😡，And actually get a different color here one of the things is empty it's called a constant constructor。

 it's a constructor for the tree data type that takes in no arguments。

 so we might say that empty as is itself a value and it's of type tree。😡。

Okay and then we also have node where node takes in an argument， it is not a constant constructor。

 it has an argument， so it takes in a value of type and these are there's implicit pren here but you don't need to put pre around it it takes in a value of type tree ser star tree okay and then you might be able to guess oops sorry you might be able to guess what it returns because node is a constructor of the tree data type so I told you what it takes in what does it produce well it just produces。

😡，A value of the tree data type。I'm saying data type here and type interchangeably data type is really just declaring a new type there's not really a difference between like a data type and a type okay it's just that how we declare it looks different。

😡，So。This is the type of trees all right it is empty or node and no more and what I mean by that is in the same sense that we had lists and lists were nil。

😡，Or cons and you can also say that Neil was of type， you know， let's say inlist， okay。

 it could be any type of listsp， let's say in list and then cons was of type。Int star。Ent list。

To endless in the same way you might say this right we see the correspondence here between these constructors between。

😡，Nil and empty， which are the base cases， which are the constant constructors and node and cons。

 which are the recursive constructors。😡，We see that actually this is a consequence of the fact that data type is a recursive type。

 we mentioned tree we once here in the base case， but we make trees out of other trees the same way that we make lists out of other lists。

 okay so there shouldn't be necessarily an unfamiliar concept because we're using just a simple recursive definition to be able to declare this type okay？

😡，So moving on， I mentioned about these constructs。

 this no more idea is going to be really important， Okay， we're kind of keeping this going because。😡。

What this declaration says is that。You know， I have these types， but I'm another thing to say。

 Oh actually， I guess I had nothing else to say about that。 But yeah， it is two constructs。

 And in particular， that means that we can case upon a tree using cases， right， So I say case tea of。

Where T is a value done to a tree， and then I would say empty。Let's say goes to zero。Or node。Of LXR。

 which is how we typically milk this。Goes to。X， which is of type int。

 right because it's here actually， it's a type int， so this will type check。😊。

But this whole expression is able to be written because of the fact that。

Our constructors are empty and node and no more。 We get our pattern matching principles still。

 Okay so we get to create trees and we get to destruct trees。 remember what it said about deing data。

 Okay， let's move on。 So let's look at some trees and how we can picture them in our brains。

 but we have the empty tree， which has no picture， because it doesn't exist。

 It's empty we have the singleington tree where the root is just the value 150。

 and that looks like a node that has no children。 Okay。

If you want to so at this point I should say something about how this syntax can start to get pretty verbose。

 especially if you're writing it in line because the fact that these two empties here can be gigantic trees in their own right。

 which means that if you try to do this try to write like a big tree。

 especially on one line it's going to explode and it's going to like have a bunch of parentheses and you might get it wrong so if you're having trouble with that you can use this excellent。

😡，SML tree converter made by a previous T Sue Lee， basically you put the depth of the tree in。

 and then you can specify some values like  one， two， three，4。

You can generate the SML text and this is now the SML text or。😡，The tree that we're describing here。

 the one that looks like this Okay so no that's kind of useful for if you wanted to like did generate for any test cases or anything like that okay。

😊，Maybe that's the side note okay we can move on to more interesting tree examples if I wanted to do the tree that's just one then five and zero I would have to put a node where my left child this thing here is itself a node right it's a node of one thing and we have to kind of put empty like a bunch of times you know that because there's four children that could have existed but didn't we have fourempties as a result and hopefully that makes sense to but you can you can work through like these typing rules this rule right here if it doesn't make sense to you as why this should type check okay。

And then on the other hand， if we wanted to do an unbalanced tree like a non- symmetric tree one in five my right it's the same as the right side tree。

 but now this node on the right is just empty okay it's empty because there's no tree there so now I only have two nodes you note that like the number of times that we write node is equal to the number of nodes that there are that shouldn' make sense to you okay。

😡，But all these are values of type three。and the syntax is important to get used to。

 but it's okay I already mentioned about how node is a recursive constructor or a nonconant constructor and empty is our constant constructor and that they're called a recursive type okay any data type declaration can be a recursive type but it doesn't have to be and I'll show you later that the distinction between those two things。

😊，Okay， and I already wrote this case for you， but also we can write one function on trees so I'm going I'm going to show it to you and then we'll go through the syntax okay so suppose I want to write a function that sums all of the nodes in a tree right I'm going to be able to case on two things right two cases empty and node in the empty case the empty tree has no sum there's no elements in it so we return zero right。

😊，For the node case， tree sum upon that is now a recursive case。

 I have to make a recursive call and in particular I have to make two recursive calls because I have two subtes that I might want to get the sum of so to do trace sum of node of LSR。

😊，You take the recursive lip of thepe if I have the recursive lipa faithpe if I assume that tree sum of L is the sum of all the nodes in my left subt and trace sum of R is the sum of all the nodes on my right subte is not the case that the sum of the whole tree is those two quantities plus my root right so think recursively it should make sense to you that if I just add up everything on my left in my right and then I put them all together with the root I now have everything so that's exactly what this code is doing it says let me some of the amount of cost。

 the amount of nodes in my left add that to X and then add that to my right so it's exactly what I said it would be it reads like math or it reads like almost like English that's the idea there right but note again note that there are two recursive calls and we're gonna see that there's a tight coupling here with how this affects our proof okay。

😊，Okay， and now I will write this one with you， but we're going to write a function to compute the depth of a tree okay and we're going to define the depth as such so if I have a tree and it looks like this so I have like like a note here。

 this is the first depth so like this is a node of depth of one or a tree of depth one now this is a tree of depth。

超。And now this is a tree of depth。3e。😡，Ignore the data I put in the tree but the idea is like it's the maximum depth of what across all paths you could possibly take and in particular the empty tree is actually of a depth of zero I also need to put that okay。

 but that's our specification。😊，Yeah， and the empty tree is like， yeah， it's right up here。

And then zero is above that。 Okay， yeah， cool。 So let's do it so。We're going to define this function。

 but first I'm going to take a little detour and I'm going to give you N。😡，Which is an int。

 actually let's say n1 and then N2， which are ins we're going to define a max function which takes into ins and then it returns to me their max right and we can do this because SL has comparison operators so we say。

😡，If N1 is less than N2。Well， then I probably just want the greater of the two， which is N2。😡。

Else I want N1 right otherwise if n1 is the same as n2 then I don't really care just do whichever okay I'm going to define this for you and then we're going to see what we use it for Okay let's define the depth function now okay so we're going to do fine。

😡，Deepth。And then we're taking in a tree right， so let's begin our pattern matching。

 we're going to say empty is our first case because when we write a recursive function on trees。

 our first move is always to write the empty case okay and then I'm returning an in。😡。

So the depth of the empty tree is， as I said here， zero because it one it doesn't exist it doesn't have any nodes。

 so we'll say zero。😊，And then the depth。Now your next move when you're writing recursive function is to write node of Lxr。

 okay？Now， this case is going to be equal to。Well， I said I wanted the maximum possible depth among all of my children。

 all the paths to the bottom right and it turns out that recursively we only need to think about two paths okay if that makes sense。

😡，Let me put it this way right I define a sandy mass function for you and here's the consequence if I have the maximum depth path on my left substratere。

😊，And the maximum depth path of my red sub or the height of that path。

Then I just need to pick between them， right？😡，So let's just say。Nextax。Of depth L。

Comma depth R right， I'm passing in a twople of both of these things。😡，Does this look right， well。

 actually I'm just taking the math of these two paths。

But if you notice like I've never done any math， I never added one anywhere， I had zero。

 and then this is zero from like recursively you can assume like the next case above the base case must be zero。

 the math of zero and zero is always zero。😡，I didn't do any work here I just straight up like return to the recursive result so if you're not doing anything with your recursive result that's a code smell you should probably think about it because you probably always need to do something with your resive call now if you're doing a tail call you might do work before the recursive call right but here we're doing like almost no useful work we're just taking a max。

😡，So what they'll tell you is what we need to do。😊，Which is to add one to it here Okay。

 we have to add one at our node because when we have this this straight or this pass us is a height like。

😡，Two， and this is a height， well， this is a height one， okay， if I take the mass of these。

The height of my tree is still just one plus that is three， so I add one， okay？😡。

And I won't go into this right now， but I'd like you to check your understanding why did I not write like why did I not compare depth of L and depth of R immediately like I could have written if depth L is less than depth of R。

 okay without without using this max function。😡，Why did I not write this Okay I'm going to。Le。

 this is an exercise， okay？But I want you to think about eager evaluation。

 you answer that question okay。All right， next's move on so we're going talk about tree traerssals。

 which are a way of getting data out of a tree。 So we talked about trees。

 we talked about being able to do stuff on those trees。

 but we don't want to let's say repeat too much work。 And what I mean by that is。

I can define functions of trees and trees are a way of storing data similarly to a list actually trees are like in a sense strictly more powerful than lists so suppose I wanted to write a function suppose I wanted to in particular write a function to count the number of nodes in a tree okay and I'm going to write this with you real fast but I'm going to tell you it's not going to be super exciting okay so count。

😡，Remember， first move， empty， right， that's the first move when we're writing a function on trees。

And then we're going to say in now the number of nodes in an empty tree is zero。 So again。

 base case of zero。 All right， what's my second move node right， So I say node of。LXR。

And what this is going to be is I'm going to count all the nodes my left and my right sum those up and add one okay it's no different than what we saw before it's similar to tree sum except I'm not actually using this x value so let me say count of L。

😡，Plus one。Bus count R。That's the function。But here's the thing I define this function。

 but I wasn't super excited by I've done this a million times maybe you were。

 but the point is that this was not very fun to write like I've already written a length function on lists right I basically wrote another length except for trees where I count up basically every element in it right but why should I have to do this in fact we might duplicate our efforts a lot if we write something like tree sum but we also write like a function to sum up all the elements in a list that's duplication of efforts it's duplication of code so how can we use this idea that trees are themselves data structures that sewar data and kind of use like repeat usage of our previously defined list functions and we can do that because we can try to turn a tree into a list so what we're looking for is we're looking for。

A function F of type 3 to int lens。😡，And it turns out that there's going to be a couple ways that we can achieve that okay。

 and we're going to talk about here Okay， so we rolled that。

 but it's it's boililerplate pretty much okay， so here's the kinds of traversals we're interested in okay。

And there's going to be three ways that we're interested in。They're called in order。

 free order and post order Triveral。Okay， and they're very simply described， okay。

 on this next slide， I'm going to tell you exactly the philosophy that goes with each of these traversals。

😊，For in order toveral， it's for all these traversals， okay， you only have three choices， okay。

 if I'm looking at a node。😡，And here， and I have like a left subt that I don't know about like I'm holding like I haven't looked at maybe and I have a right subt here okay。

 I have three choices I can do my left。😡，I can do my my root and I can do my right sub and when I mean do I mean visit right for births。

 I'm looking for an ordering。And I can really only choose to do this， this。

 this or like like here those three things in some way。

Now if you think about there's actually more than three possibilities。

 but these three possibilities are the only ones we care about okay so these are all characterized by what their philosophy is for what that ordering is okay。

😊，If we start with in order traveral this one's the most natural， I think it is root left right。

 if you could visit left， go left if you and then if you can't go left。

 go to your root and if you can't go to your root。😡，Well， yeah， go right。

 I guess you can always go to your root， but I'm， that's the idea。 Okay， so for instance。

 if I wanted to think about how this thing shapes up， let's say I had the tree above。 Okay。

 so it looks like this， right。😊，I'm gonna omit the吗。In side of it， right。

 but if I wanted to talk about how I traverse this thing， I start here at my root。

And then I want to go left and I can go left， so I do。And then I can go left， so I do。

 and I can't go left anymore， so I stay at my root and I write one。😡，But I can't go right now。

 so I backtrack， I go back up here and now because I've already gone left。

 I visit my root so I go two。And then I go right because I can， so now I'm at three。😡。

And now I can't go left right or root， so now I go all the way up to here。

 so I get four and then five and then six and then seven。😡，Or actually。

 I think that it's actually five% yeah。Basically it reads exactly the same as if you were trying to go left to right right one。

 two， three， four， five， six seven okay that's the idea behind in order traversal and then I won't describe preorder and post order for you。

 but I'll say that they're the result of it if you do root left to right and left right root respectively as your philosophy of tree traversal okay。

😊，Okay， hopefully that makes sense to everyone， I'm going to erase this now and then we're going to implement one of them。

😊，So let's implement a first off， let's implement in order traversal， okay。

 so we're going to write it here。😡，Remember， first move， empty。

And I want to get out of it and in list， so I'm going to write this all right。😡。

Now if this doesn't make sense to you you think like what's the in order traversal of the empty tree。

 what is a list resulting from visiting all the elements in the empty tree and it should be obvious to you that the answer is nil the empty list right there are no elements to visit so I return empty okay fair enough。

 then we go in order of node LFR。😊，As usual， right？

What do I return here all right so my my philosophy was left root right what that means is that I basically want to visit all of the elements of my left subre and then my root and then my right now what does it mean to visit all the elements in my left subt that means。

😡，A recursive call on my left sub right if you recursively assume that in order on L will return to you a traversal of all the elements in L。

 then that just means in order L that's what it is this is an in order traversal of the left sub。😡。

And I want all of these before I put X and R in， okay？😡。

And then I want x and then I want in order R right I said left root right。

 but now how do I put these values together Well， I'm going to have to take an int and two int lists。

😡，So here's what I'm going to do。I'm to actually I'm going to append this， okay？To this。

I'm going to take this endless and append it to this endless so I'm going to have to produce an endless here and what I'm going to do is I'm going to do this。

 let's say this。Does that seem okay to you？This is actually wrong。

 I can't do this because this is the take train。X is an end here。😡，In order or as an intla。

 I can't append an int to an in， but what's the canonical way to prepen an int to an int？😡，It's tons。

Simply enough， right， I con on to the right， and then I append that Okay， it would be。

 you could do this， but please don't， it's a style violation and you shouldn't This is。

Not useful this is going to be this is will actually degenerate directly to X cons in or R okay。

 but this is like wasted effort you should never append a singleton list to the front Okay so I'm showing you what you should not do but I' the cons here and then now we have our in order to brle okay so that's how we do in or。

😡，Right。And you can if it's not obvious to how it works。

 you can try to like kind of work through some small examples to convince yourself。

 but the idea is that there's there's very few moves we could make there's very few possibilities that we had for what we could do here so the fact that we did it left root right and that's the specification of inor means that like this is pretty much the only thing we could have done to make it right okay that's not a super strong justification but we're not going to prove it right now okay。

😊，And I'm going to write。Preord， which is sec tree， returns to in list。I'm running out of room。

 I'm going to put equals here。😊，So we're going to write preord now。

 but now I'm going to tell you that I'm a well we're doing the preorge revversal so now we're going to do root left right okay I'm going to spplay it out along two lines。

 but I'd already did the empty case for you if it's empty then we're just going to have their empty list right because there's nothing in the tree but if I pre-ord of node。

😡，LX R as usual。Well now what do I do， I have to do root， then left， then right。

 so what it looks like is I'm going to do something like this。😡，X。😊。

I'm going to call myself recursively on the left， and I'm going to call myself recursively on the right。

And now how do I stitch this up into a valid in list？😡。

I'm going to take these two endlesslist and append them together。😡。

And now I have an int with an int list， so I'm going to con it on， that's all。😡。

It's all you need to do so with this now we have our implementations for in order traversal and pre-order traveral very short。

 very concise， very simple right its it's very terse how you can define this SML but that's the power of recursion because someone invented a technique for colonizing literally infinitely many facts in your brain and by the way it's called recursion or induction depending on how you look at it okay so this is a demonstration of how we can do recursion on trees and now if I have in order I could do something like this instead of using count I can say length。

😊，Of inor。Of T where some tree t okay， and I'm going to tell you that this should be essentiallyly equivalent I'm going to run out room here a little bit。

 but this should be essentiallyly equivalent to count of T。😡，Okay， that's our idea。

 that's why we defined in order， okay。All right， but we can now we wouldn't have had to right count if we wanted to all right。

😡，Okay， and I already showed you this cool， good time。

 I'm going to drink some water and take a break。😊，Okay let's get back to it so right now we're going to do a structural induction proof on trees and we're going prove an equivalence sort of like the one I was talking about with count length。

 but we're gonna to show that doing that tree some function I was talking about earlier and doing a list sum instead on the in order traversal of that tree end up with the same thing in that sense we're showing that the data is preserved okay we're going to prove that inductively how structural induction so I've already talked a little bit about structural induction。

 but we're going to be able to do it on trees， why because trees are built up from other trees in the same way that lists are built from other lists in the same way that natural numbers are built from natural numbers and anytime you have that kind of hierarchical structure an inductive definition we call it you have induction okay so。

😡，This is the principle of structural induction on trees， and it should be very familiar。

 so if I've got a theorem on values of type tree， I want to show that for' all values that my property holds。

😡，I need to show only two things。😡，I show that P of empty is true。

I show that assuming that I get both p of L and P of R that is that P holds for some arbitrary L into R values okay if I have that。

 then I just need to show that P of node Lr holds for an arbitrary X and this should look familiar but also not because before we just had one induction hypothesis right but now we get two why because I have two trees on my left and right that I need to be able to say the theorem holds for if I don't know that the theorem holds for my left and right subrees。

 I'm up the creek without a paddle I don't know what to do my moves I can make are very limited。😡。

But I need that principle of induction to be able to talk about any of my children okay so for a tree I get two all right for an arbitrary L and R。

 but you have to say for like some L R it's still not proper to say for all。😡，T of type three， okay。

 that would still be assuming the theorem， but you just get two right， not no more no less， right？😡。

Well actually I guess you don't always need both your induction hypotheses。

 but for the vast majority of functions you could write on trees。

 you will need two induction hypotheses Okay okay and I already wrote all of this on the board。

 but you can take a look at it for a second so we have in order traversal that I already wrote for you earlier we have a tree sum function and we have a list sum function and I'm to tell you that we're trying to show they do the same thing even through the conversion of inor Okay that's the theorem in particular right so let's get to the proof。

😊，And I've got two lemmas for you actually I'm going to hide that one because I don't want you to look at it Okay and this is one of our lemmas。

 which is that a list sum of L1 andendel2 is the same as summing the list sum of L1 and L2 separately。

 all。😊，Cool， so let's use proof the first thing I got do is。😊，Right。

 what kind of induction I'm doing。😡，So we proceed by structural induction， right？😡，On what on T。

 which is of type  three， but we can just say on T。😡，All right。

 if I want to prove something about every possible value。

 I can do it by induction or I can do it by letting it be3 here I have to be able to decompose on the structured low so I want to do induction all right。

 so if I if I proceed by structural induction on T the base case  for T。😡。

Is when t is equal to empty。Our technique for how we're going to do these proofs is we're going to try and start at the left hand side okay so like when I say left hand side I mean in an equience proof I have a left hand side here which is trace sum of T and list sum of in or T in fact let me let me write that down Cly this is my LHS and this is my RHS right left hand side and right hand side。

😡，And what I want to do in this proof is I want to take the LHS and I want to like step it to something。

 I want to show that it's essentially equivalent to something。

And then eventually arrive that it's essentially equivalent to like E。

And then I'm going to get stuck， I'm not going to know how to proceed。

 I'm not going to know what move to make that's okay。

 because what I'm going to do is then I'll start from the right hand side。😡。

And then I'm going to simplify it， I'm going to show that it's equivalent to something。

 and eventually I'm going to try and show that it's equivalent to E。😊。

So I'm trying to have the meat in the middle I told you earlier that essential equivalence is an equivalence relation。

 it means it goes both ways， so if I show that LHS is equivalent to something and RHS is equivalent to something。

 I have shown that。😡，LHS and RHS are equivalent Okay。

 the reason why it might seem like it doesn't matter the way we do it and in a sense， you're right。

 this will make citing justifications a little easier for us Okay it'll make it a little easier if we don't do something called backward stepping。

😡，Right。Cool， let's say I don't need this Okay， so let's proceed with the proof well let's start with the LHS。

 which is tree sum of tea so tree sum。Of empty。And we know and remember that the way that we do an induction hypothesis is we have a knowledge bank and this is our knowledge bank。

 this is everything we know about the world， okay plus or minus a few other things we know about okay。

 but basically if you're ever if you're ever looking for something to do，😡，It's up here。😡。

This is the list of possible moves you can make it's like chess I've laid out everything we can possibly say and we have an equation here I'll say equation for like an equivalence right between tree sum of empty and zero So little I say I say equivalent to zero。

😡，And then I give justification， why？By clause one of Tresome。😡，All right。

And now zero is pretty much as simple as it's going to get right so let's say that we're stuck all right。

 let's say we're stuck and let's say that let's call it for the LHS， let's do it from the RHS now。😡。

Well， if I have list sum， remember the RHS is that quantity up there， if I have list sum of inward。😡。

Of empty。I'm going to do two things， first off， I want to be able to set this。😡。

But how do I simplify listum， well， I only have an equation for when list sum is taking in nil or X con Xes。

😡，In order of empty is neither of those things， I don't know what it is necessarily。

 I have to do eager evaluation， I have to swap it for something。

Buy Sml's evaluation rules because I want to use a definition of list sum but I can't yet Okay so I'm trying to get at that by using in order so what is the definition of in order say well I have an equation that says in order of empty is nil So let's use that so this is equivalent to list some。

😡，Of nil， right， and that's why clause one。In orange， okay。

Plususe one of in orderg and then I have listed some of Neil。

 so now I know that that's got to be zero because I look up at my knowledge bank and I find it inside okay。

 very， very procedural， that's zero。So I say clause one of。Lis some。

And now I've set LHS or I haven' a set I've shown as equivalent to zero。

 and I've shown the RHS is equivalent to zero， therefore they're both equivalent。😊。

And that's the base case done okay little check mark。

 but we're not done yet okay we we have more stuff to go so let's see let me think about this。😊。

I'm going to write the induction hypotheses on this board and then hopefully we can just remember it when it comes later okay so this is the base case done remember we get two induction hypotheses so what are they well I'm going to say IH1。

😡，We assume that the number for a specific L， so for sum， I'll say for sum。😡，L of T3。

We get that tree sum of L。Sum capital is essentiallyly equivalent to list sum of inward of L。😡，Okay。

 that's my IH1， personan L， a specific L， a fixed L。What about IH2， well。

 where do you think IH2 is going to look different？

It's going to look different in exactly three places， which are everywhere I mentioned。😡，L。

 so I'm going go， I'm going to do this， okay。I'm just going to write equals equals R equals it's it's going to be exactly the same and I don't want to write it out again。

 so it's the same same sort of deal Okay， that's our IH1 and IH2 Okay， all right。

 I'm going to put this away now and we're going to go work on the inductive set。Alright。嗯。

And we will refer back to this in a second， okay？Alright。Inductive set。

With our L andRR that we received from the induction hypothesis， we want to show。😡，We want to show。

 so WTS want to show。That tracesome。Of node。Of LFR。Is equivalent to。list some。Of inward。

Of note of LXR， and I caution you to please write this out。😡，Specifically。

 write out what you want to show， it will help you okay， because now。😡，This is our new。

LHS and this is our new RHS， okay， and we're trying to show that these two things are equivalent。

 okay？I hope I have enough room for this Let's try it out Okay so let's start from the LHS right it's tree sum of what I just said okay so here we want to be able to apply our definition and in fact do we have an equivalentvalence that says something about this turns out we do why because tree sum of newdevelop R is just tree sum of L plus x plus3 sum of R Okay so by unpacking the definition I'm going to say this is equivalent to I'm going to put it on this new line because I'm going to run on a space I think otherwise。

😊，Is the equivalent to trace sum of L plus x plus tree。Are， okay， and that's why I close to。

Trece some。系。I'm trying to leave like half this board empty， hopefully。

 and I'm also going to notate this is LHS okay。😊，All right， but now what do I want to do。

 I want to be able to say something about tree sum of L and tree sum of R now we do have two induction hypotheses that could help us with that because we know something about tree sum of L and tree sum of R。

😡，So let's actually， let's actually do that。 Let's say it's a。So we're going to call IH。

And say that we're in order of L sorry not in order of L。List some。In order L。Plus， apps。Yeah， okay。

Plus， I'm going to break it apart here and you'll see why this is in a second。

With some in order of R。Okay， so this is what I step two because I applied the induction hypothesis on both of these guys。

And I get these。Okay， so I'm going to say by Ih。Time si。O。😊。

But now I want to say something about n order of L and list some of that。

 but do I have anything that says anything about in order of L like for a specific L that I don't know I don't so what I need to do is give up and go home because I don't know what you do now so I'm going to give up and I'm going to go to the right hand side。

😡，And it's okay to give up， this is a life lesson， right， let's start from the right hand side。

 which is this guy。😊，So if I have lists on。In orange。No develops R。

I want to step this what do I do first thing I do is I look at the definition of listss sum can I apply list sum do I have anything that says what list sum of in order of node is I do not I only know a list sum of Neil x con Xes and in this case aend of two things because of ourlemma so I can't do anything here but I can simplify in order because what do I do I know that in order of node of Lr is this so I'm going to do that。

😡，So let's say equivalent too。I'm trying to walk you through like my whole like proof writing process right this is exactly what I'm thinking when I'm writing the proof。

 it's a very formulaic way of doing it。In order to L append。😡，X cons onto 2 in order of R。

I'm going to write in here like margins in small pause to。In order， okay？That's our justification。O。

But now I'm in a pickle okay， because what do I have。

 I have list sum of n or L append quantity excellence n or R。

 but list sum only applies to these two things， oh wait， we have alemma for that。Except we don't。😡。

This is going to be very subtle， but it will not be correct for you to set this。

 so actually let's write it out so here's what we want we want to be able to say oh， I have。😡。

List sum of L1 append to L2， and I know that's equivalent to list L1 app plus list some L2。

 so this looks like L1。😡，Right。And this looks like L2。So I want to be able to use that to say。😡。

This is equivalent to list sum。Look in or L。Plus list sum of。X con onto inward R。

Why because I'm using L1 and L2 as sandins for these two。They look the same。

And what I want people to do is I want to cite。Lema1。

But I'm going to tell you right now this is wrong， this will get you the points stocked off。

 you can't do this。😡，The reason why you can't do this is because you need more justification here。

 why， because look at our dilemma， it says for all values， L1 and L2 of type int list。😡。

Is in order L and X cons in order to R are those two technically values？

Are they valuable is a bigger question， Okay， I don't really care so much of their values。

 so much as if they are valuable expressions because so long as they're valuable。

 I can swap them for their values， that's what referparential transparency says， right？😊。

But I want to say for all values。So I have to show that in order to L and xs in order are evaluate to values that they are valuable now you might look at the definition of in order and say。

 oh in order is total， right， so it must be valuable。😡，But you need to show that to me。

 I need to I need you to cite that to me so here's what I'm going to do and I'm going to activate my computer again even though I won't need it for right now here's what I'm going to do I'm going to reveal to you what our hidden Lemo was the whole time。

😡，So I need to show the value， okay actually let let me let me hammer this in a bit more。

 I need to show that this is valuable， this yellow thing and this。😡。

Wouldn't it be great if I knew that in orderg was total。

 you can't cite that without proof if you want to prove or cite totality on an assignment。

 either you will have it as alemma or you'll have to prove it on the spot。😡，In this case。

Thelemma I was hiding from you was the fact that we were given while we were doing this proof。

The fact that inor is total。That was the secret。So we can cite it。😡。

But if you don't have that you'll often to prove it okay but note that this is this begins a chapter in your life called totality citations where you have to write that things are total on certain lines to be able to make a step go through okay and what I'm trying to get at is to show you that this step is based on whether or not you need that a particular expression is valuable okay the way it goes and let me let me show you this because I have slides for this explicitly。

I've already already talked through all this， but this is what I call stepping through theorem values。

 if you want to step through a theorem or alemma that has a value in it。

 something quantified over values， you have to show that whatever takes the place of these variables like L1 is you know in order to L。

 you have to show that that thing is valuable。😊，And how do we do that？

We're going to be able to use totality as a tool to get at Val we want totality for the purpose at getting at Val that is the important thing okay so。

😡，Here's the picture， okay， I want to use a theorem which relies on E being valuable。

 so I want v of E。😡，And I want valuable of E so if what do I do。

 I can get it via a totality citation usually if this was like okay， if this was lists sum of nil。

 I would have no problem with you not citing totality here to set or if both of these were nil okay but they're not。

 their expressions in the form F applied to something。

 which means they could loop they could raise an exception。

 which means that they might not be values， which means the theorem might not apply。😡。

If they were nil， that would be okay， but because their function applications。

 we have to be careful okay so to repeat it one more time， we want v， we get it via totality。😊。

So what I'm going to do is I'm going to era that here， and I'm going to say to make this step。

 we have to cite also lemma2。Because we want to show that in order of L and x cons in order R。

Are valuable。Now you might also be wondering like how wait I showed that in order R is valuable。

 how do I show the x cons that is valuable， the reason that's because cons is a constructor。😡。

Constructors are always total okay， you don't have to cite that you don't have to cite that constructors always total。

 but I'm going just know that and that's important okay。

 so because this is valuable and this is a value right because x is a value from the node and this is valuable by the definition by the definition of totality this must also be valuable so we're done so now we can make this step。

😊，And now it almost looks like what we want right we want list sum in order R L plus x plus the sum in order R。

 not list sum in order L plus list sum of x cons in order R。

 but handily we can step through the definition because what do we have。

 we have something which talks about sorry here。😡，List sum of x cones， okay， so let's set it。😡。

So I'm going to leave this left hand side list sum alone， I'm going to just call it or N or L。😡。

I'm leaving this alone， but I'm going to say plus， and I'm going to break apart of this definition to x plus。

😡，List some。Of inward of R。😡，And can I just say clause two？Of list sum here， the answer is no。😡。

When I say stepping through theorem values， I mean also definitions。

 why because definitions only apply to values， remember eager evaluation。

 I only can set this x cons xs if x is a value and x's is also a value so if xs is not a value I can't do that so basically concretely to set x cons in order R I have to know in order of r matches to x's which means I have to know it's a value。

😡，So what do I do， I cite totality again because I need in order of R to be valuable。

 so I do lemma two， and I know this is like getting a little hard to see。😡。

But we're fitting on a board at， okay？So okay， so that's our proof that concludes it because now look at look at my left hand side and look at my right hand side。

 they look the same and if you're confused over the format magnets。知等 that容。Okay。

That's the proof two totality citations， but be aware of where you need to do them all right。

 Val all right， let's stop talking about I just wanted to say this so again because this will be on your homework all right this will this is something you will be tested on。

😡，All right。And then we finish off our proof and we're done actually。

 this one I did the induction hypothesis hypothesis on the right hand side。

 it doesn't actually matter， but yeah， so now by the principle of structural induction on trees。

 we've proven our theorem， that's it We're done Okay， that's the that's the proof al right。😊，O。

We're going to move on， we're going to talk about data types now。😡。

You can look back over the notes to look at this proof。

 but this is one of the most involved proofs we're going to do all year okay so I would just try to be aware of what exactly happened and and would that be aware of the process right I try to be very transparent with my thought process while I was doing that proof okay I'm trying to show you how to think when you do the proof when you're when you're stuck。

😡，Give up and when you don't know what to do， consult your knowledge bank， which I just erased。😡。

Consult your bank with factsTs that you know， there's only a finite amount of them， okay。

 we're not going to give you infinitely money。😡，Okay， I don't think I need too many boards for this。

 I'm going to just move on。We've seen trees， let's go to lists。😡。

Suppose I wanted to write this function here。😡，It's called last。

 I taken an in list and I give you the last element in the list。

 kind of the opposite of the head function I showed you earlier。😡，And we can try to write it。

 but I'm going to tell you that right now。We already get into an issue right off the bat， why。

 because we don't know how to write the base case， and I actually' write this out with you。😡，So last。

 and I want to take in。An int and then give you back an inch， right？

But what do I return in the base case， well， I don't have a last element。Right？

So what we could do is we could raise an exception， okay。

 we could like not handle it and then force handlers of this function to deal with it。

That's kind of gross I said something earlier about how exceptions when you have exceptions it's like they percolate up and then they disrupt your entire execution and now your machine is just crashed your process has crashed you're just like done completely so if I raise an exception with last if I've got someone over here trying to write like you know you know Valal x equals last。

Of Neil。This will raise an exception on them and they have no choice but to deal with it because they don't have a way of handling this at least not yet okay so what we're going to find is that we don't want to be able to raise an exception and in general functions that raise exceptions are really bad okay so here's what we're going to do。

😡，Okay okay， I should also say the alternative here is also we can return like zero。😊。

We could just return like an arbitrary integer， maybe negative one， I don't know。

But now you've made ambiguity because this is ambiguous with the case where let me finish writing last for you。

 actually。So if we wrote that we return negative one。

 well I also want that last of the singleton list。It's going to be that helmet。

And then last of x con x is。Is last two exits， right I'm going to rehearse on the rest of my list because I don't care about the first element。

But now there's ambiguity between if the list is empty and if the list was the singleton of negative one。

 basically I'm showing you that last of nil。Is essentially equivalent to last of。

Singleton lists of negative one。This is ambiguous， a person using this function doesn't know which case they're in。

 so let's not do it okay。😡，We want to distinguish found zero or found negative one and found nothing。

All right so。This happens a lot actually where we write functions where some inputs don't have a good answer for you okay and what we've done so far is in the case of did we raised exceptions in the case of fact we've infinitely looped but neither of those two things are desirable because a person calling that function has no way to deal with either an exception or an infinite loop what are they going to do they have no agency we want to give people using our libraries。

 some agency okay even if they break our preconditions okay because they might make a mistake when we do okay so we're going declare a new data type called option。

😊，And here's how I'm going to define it for you Okay， I'm going to say that data type。Inch。

Underscore option， I'm doing the underscore for。Syntactic reasons don't think too hard about it Okay just think about the content right basically it's because i'm lying to you and there's an extra language feature i'm going to show you in two weeks or one week where this will make sense all right so an into option is as two constructs。

😊，It's either none。Or it's sum of int。😡，Okay an into option is one of two things it is either no data。

 none has no interesting data in it whatsoever， it's just none， it' it's nury。

 it's a nonsense output okay but it's a value at the very least。😡。

Or it's some of an int so either we have an int or we don't is the idea of an in option okay and you don't know which one based on the type if I hand you L of type into option。

 you don't know which one you're holding but you know that it might be a mistake this is the type options or the types of fallible data okay and what we find is actually it's a type constructor which is to say that in options are not the only options that exist we also have we also have string option and we have int list option and we have in option option so on and so forth okay。

😡，Okay so for any type T we have type T option and I already showed you the constructs and yes none as a constant constructor。

 but I want to show you some examples， so if I have sum of five so some applied to five some is a function of type T to T option。

 it's a type int option， if I have sum of a list that could be a type in option。😊，If I've none。

 it could be of type into option and if I've none， it also could be of type pool option。

 none could be of type any T option right because it's ambiguous which one it is。😊。

So these are examples of options。😊，But we can use this option idea to help us rewrite last。

So what if instead of returning negative one as like a dummy value， right because it's ambiguous。

 we separated it by returning int option not an int， but an int option。😡。

And the intoopion is with no underscore， okay， this underscore， don't worry about it， right right？😡。

So into option equals。None。😡，I have no last element， last might return no data。

 so we return none because there is no last element。😡，Otherwise， instead of x， we return sum of x。

And otherwise， our code remains the same。 It looks very much the same， but now a user of laugh。

 this is no longer true， right， because this will now evaluate to。None。

So let me break this equivalence and this will evaluate to sum of negative one this equivalence is no longer true。

And what does this look like for a person calling our function， well。

 I'm going to write this actually， if a person was calling last。😊。

Before they might say something like last of x's。And this will just raise an exception or loop forever。

 but now they have the option to say this。😡，C last of x's of。And there's two cases。

 the none case where they get to do something or the sum of x case where they now have an int called x。

And they do something， but now there are two cases。Two branches for this function， okay？

Now I have agency， now I can use this function however I like。That's the power of options， okay？

So anyway to move on these things are called variant types okay there are constructs that have variants that they can be and this is important to realize because variant types we've already seen actually you can think of lists lists are also a variant type right because lists can be one of two things which are they can be nil or they can be cons tray are variant types they can be either empty or node。

😊，And honestly， you can think of integers also as variant types because they can be one or two or three or negative one。

 it's just that ints are infinite， okay？😡，Okay。But the real power of variant types is that we can case on each of the cases。

 each of the variants it can be， it's also called a sum type， which is a little easier。

 okay let's say。So you can think of the definition of ant this way， okay。

 it's nil or it's cons of blah， blah， blah where cons is also ins okay。

 so that's one way you can think about it。😊，Okay， but this is the definition that I gave on the board earlier。

Okay， we also call these algebraic data types and later on I will try to show you why it is that algebraic data types are very。

 very cool right but let me use context switch entirely we're going to talk about something completely different All right I am interested in this problem。

😊，And， you know， somewhat surprisingly， you're going to find that this problem is actually related to what we're talking about I'm interested in a comparison function。



![](img/09806f8e90db4a7a51e104c18933eb33_1.png)

On integers， that is it's a function that takes into two integers and outputs whether or not they or what their relationship is with each other that is like you CM of x Y。

 x could be less than y， x could be equal to y or x could be greater than y。😡，In most computers。

 or not in most computers， but most programming languages that don't have these algebraic data types。

 here's what they do。They say this is equivalent to they this goes to int。

 why because they say like CP。😡，But one common 2。Goes to a negative one because one is less than two and they say that CMP。

Of two comma 2。Goes to zero because they're equal， and they say that CMP of two comma 1 goes to positive one。

Because two is greater than one。But now what does this look like for a consumer of this data。

 if I want to use CMP， right， I might write this。😡，Case， CP， and I don't know X and Y are。

 so let's say an arbitrary X and Y。Of。Well I know there's a case where it's negative one so I can pattern match on that。

 I know there's a case where there's zero， so I can pattern match on that。

 and I know there's a case for one so we can put whatever here。

But actually you know let's even do it，s let's put this into the into the playground， so VM test SML。

 let's say that we have you know。😊，Actually， yeah， let's just do it okay， so x y。

 if x is less than y， then negative 1 else if x equals y then0。😊。

And then else we're going to return one right those are our three cases'm and I'm also still going to annotate this our and this is a tape。

😊，En and this is a type end， okay？What if I had a function like P。

 which takes an x of type int and the Y of type int and here's what it wants to do。

C CMP X come a y of？Let's say zero goes to or a negative one goes to like like the string L。

 and then like0 goes to the string E for equals and then one goes to the string G for greater。

Let's type this in decimalJ and see what it says。Warning， match non exhaustive。Why。

 because wrote I wrote this comparison， I wrote this pattern matching， but if you see here。

 I didn't handle every possible case， there are more cases than the ones I've written on the board。

 there are more cases than01 and negative one I've lost my child here it is。😡。



![](img/09806f8e90db4a7a51e104c18933eb33_3.png)

There are more cases than these three， I have to add a wild card case or the compiler is going to yell at me and this is a style error。

😡，But this feels really bad because I know if this case is impossible。

 I know by post condition of CMP that it should never return something that's not1。

 zero or negative one。😡，But it does so anyways， I have to explicitly handle it that sucks。

 how can we do better？Allright， I'm going to show you a first cut at this。

 and then we're going to improve log， all right。😊，So。

Let's suppose that we use what's called a type alias all right I'm going to write here so type order equals string okay this is called a type alias I'm saying that the type order is a new type that is literally just the type string by a different name okay so we want to our first cut for the type order will be string so our comparison function will return the string less if it's less it will return the string equal if it's equal and itll return the string greater if it's greater okay that's our that's our first cut all right that's all it does。

😊，Well， what does it look like for a consumer of this data now？It looks like this。

Case compare x comma y of。And now I handled the string last。I handle the string equal。

 and I handle the string greater。But it's still possible for me to mess up because there's another non exhaustive check here。

 I have to add a explicit case for all the strings I didn't handle。

So it's the same I haven't improved my situation， I'm in the same situation。

 but now there's infinitely many strings as opposed to infinitely many inkts that I'm not can， right？

So。This shouldn't be possible。And actually， there's a second issue with what I have here。

 the second issue is that this code plain doesn't work。

I said that compare returns less equal and greater undercase， lower case。

Wwhichch is different than uppercase less equal and greater which I'm casing on here。

 So if this was our code， if this was our comparison function。

 actually every output would go into this wild card case that we said shouldn't be possible and this happens all the time people say oh man this is impossible this shouldn't be possible let me raise an exception okay I reasoned about it and this shouldn't be possible at all but guess what even the most seasoned of engineers make that mistake all the time they say oh this is impossible and they guess what it was possible the whole time it's kind of a motivational story so but in this case not so motivational because we don't want it to happen So let's exclude the possibility of making this mistake let's try to make it so that in a typesafe way this can never happen。

😊，Here's how we're going to do it。We're going to define。So instead of so okay。

 CMP inserting goes through order。😡，All right， and then this is no longer going to be true。

 but we're going to define a new type for order， okay？

And I'm going to keep this around here because we're going to look at how we use the type。

 so I'm going to say data type。Order， I'm going to define a new data type and what it is is it's three things I'm going to put it on a new line。

 but it doesn't matter where you put it。😡，It's less or it's equal。😡，Or it's greater。

The order type has three constant constructors。😡，It is either less equal or greater and nothing else。

 it's just a flag that has three different states it can be in。😡。

And that's going to be what we want to refer here。So to implement it， you know。

' a well I guess I have it on this next slide， but。I actually maybe。

Yeah this is just some kind of like motivational stuff I wanted to talk about I wanted as just to say the big we're trying to find the best solution right like the solution works but it's not the best solution let's find the best one all right。

😊，So with data type order equals less equal or greater。

 this is our new comparison function if x is less than y。

 we return an order which can be only one of three things so we return the constant constructor less which is a value of type order。

 otherwise if it's equal we return the equal constructor。

 otherwise we return the greater constructor okay？😡，And now if I'm using this code。

 what am I going to write this is like。😡，Separate don't worry about it case CMP of what am I going to case of and I realize that's called compare that's called CMP realized I meant the same thing okay。

I only have three cases now。I have the less case。I have the equal case。And I have the greater case。

 and the great thing about this is that the compiler is not going to yell at me。

I have no other cases， this is it， this and nothing else。😡。

That's the idea of sometimes this and nothing else less equal or greater and no no nothing。

 nothing more， no fat， okay。We're going to be able to write really clean code that handles every case and never be assured that we can never reach a case that we thought was impossible。

That's the strength of algebraic data typess okay？Okay， oops。Okay。

 so this is the code that we write and again， if we had misspelled one of the strings that we had back when we returned strings as our order type like that could have gone into production that could have gone anywhere and we wouldn't have known because we need a typo it's impossible to make a typo here because if you if you do if you are like E。

😊。

![](img/09806f8e90db4a7a51e104c18933eb33_5.png)

The compiler will be like I don't know what this is， what is this this is not a value of type order。

 E is not a value of type order， so therefore let me not even accept your program。😡。

One interpretation one canonical way to do it that's the idea all right types guide structure we we structure our types to fit our problem to frame our problem okay our way of thinking is through our types births okay and let me actually just briefly demonstrate to you what it does so if I say data type order equals less or equal or greater。

😡，And thismer function now returns less。Equal and then greater。m，Well， okay。

 I'm just going to show you the like， yeah。I's just say everything was a zero， I don't really care。

Actually， no I'll make it， I'll make it a different greater wait I put in the string sorry sorry sorry。

Yeah， okay， here we go， no no no comments or no quotes all right。

 now we want to do this and then CM returns an order instead of an inch， right？😊。

And this does compile。And better if I I'll show you again if I make a typo， I write equal。😡。

Estma will be like wait， match redundant， I don't know what you're talking about because Iquaa is now a variable name。

 but it will warn you is the idea， okay， you can still pop all pre to this if you ignore the match redundant but be careful about it okay so this is way more resilient。

 it's way more resilient。😡。

![](img/09806f8e90db4a7a51e104c18933eb33_7.png)

Cool， I was a little wrong when I said it wouldn't know what it was。

 itll actually match to a variable case， but that's a different story， okay。All right。

 I have a little bit of time to talk about this last thing with you。whohoa whoa whoa whoa whoa。Okay。

 those were all right。Cool all right， this last thing I want to talk about is called type casting in other programming languages。

 there's an idea of type casting， which means turning like a value of a type into a value of another type for that's not what I'm talking about I'm talking about type casting as in。

Something else I'm making a joke。 It's kind of a pun。

 right I'll reveal to you what I mean at the end of the lecture。 All right。

 But SML does not have type casting in that sense， but it does have type casting in this sense I'm going to talk about today。

 All right， so。😊，The idea is that when we're solving。

There's so many different kinds of problems that have had in common roots， you know。

 there's a lot of problems。No。y啊听期佢。It's just like a。Oh everyone。

I don't know how long it's been there， but， never。Yes。

I said something about how list and trees are the common ways to solve problems。

 but they come in all shapes and sizes at the end of the day。

But the great idea behind algebraic data types is make your types fit your problem make the types serve you okay and here's here's here's our problem Okay。

 we have a class of people all right some people are employed some people are students and some people are unemployed it happens to be that we live in a world where those three things are not disjoint but in this problem let's assume that those all three cases are disjoint Okay you cannot be both a student and employed or a student and unemployed Okay that's the idea all right this is our problem and suppose that we're interested in just a few things right for all these people we interested in their name。



![](img/09806f8e90db4a7a51e104c18933eb33_9.png)

We're interested in their paycheck if they're employed and their tuition if they're a student。

We're interested in the company that they work for。If they're employed。

 we're interested in the number of courses they're taking， if they're a student。

 and if they're unemployed， if they were ever employed， we' interested in two things。

 which are the day since last employment。😡，And the title of their last job。 And again。

 this is only if they were ever employed。 some unemployed people have never been employed， Okay。

 and those are all the things we're interested in。And we can try to represent this in a way using SML okay what we're going to do is we're going to use a big tuple and we're going to use the options that we just learned about because you know if we don't all want to want to store like the name of the paycheck of a person that's unemployed or we don't want to store like the company a person works for if they're a student so we're going have an option so we have the option of having none if that's the case。

And this is the type representation that we have a data type class which is employed or student or unemployed。

 so this is like three things it's kind of like order it's just telling us what we're in。😊。

And this is our type， it's a type alias， and I know it looks it looks scary。

 but this is just a tuple type， ignore ignore the comments， it's a tuple of six things。😊。

One is a string。One is a real one is a string option two of them are into options。

 so on and so forth and what they mean is in the comments here so the string is their name that always exists okay the real is positive if they're employed that's their paycheck and if they're unemployed it's negative and it's their tuition or rather if they're a student if they're unemployed is zero。

This string option is the company name if they're employed， otherwise it'll be none。

And this end option is the number of courses they're taking if they're a student otherwise none okay so like let me let me actually copy this down for you here。

 I don't remember whether or not I have a file with this open， but'm that's fine。😊，Yeah， okay。

 so this is a good enough。Well， okay。Sorry， let me address this right now to make this valid decimal syntax。

 the comments got messed up， but don't worry about it， actually maybe do worry about it。You know。

 let's wrong with it， Okay， so this is the idea and I'm going to make a value。😊。

P of type person info， okay， and it's going to be like their name is Bob。They're employed。

 so the paycheck is 2000， I don't know， like 2000。0。

 maybe they make it look very little and this was supposed to be the company。Company name。

A number of courses。And then days since last employment okay。

 now Bob is employed because they have a positive paycheck right so we're also going to say that Bob's company name is let's say I don't know maybe the work for they work for a Bank of America。

😊，And then the number of courses they're taking is none because they're not a student。

 the day since last employment is none because they're employed and the last job if unemployed is none because they're not unemployed。

 so Bob is employed。We might also have another person。Let's call this person N。And Anne is a student。

 so their tuition is negative。Negative $50，000， okay。

 and it's a real and then their company name is going to be oh so this is somem sorry。😊。

It's some Bank of America because N。Is a student， so she doesn't work for for company。

 and the number of courses she's taking is sum of five。😊。

But she's not unemployed to the last who are none okay， and if we run through this through SML。

 this should type check right， so we're convinced this works。😊，But look at what I had to do。

 look at little hoops I had to jump through to make this work。

 I had to put none in like three different places to make this work。

Like it's disgust and I have a bunch of floating invaris because I have to make sure that if if your real here is positive。

 then these three should be none and if you're a student， then these three should be none。

 if your tuition is negative， but also this should be set there's somebody invariance okay。



![](img/09806f8e90db4a7a51e104c18933eb33_11.png)

Again， remember what I said about invariance， you're going to get it wrong。

 you're going to mess yourself up。So let's try to do an also， oh， sorry， let's say that I'm a。



![](img/09806f8e90db4a7a51e104c18933eb33_13.png)

Also， a person is equal to a tuple。So we also said data type class。

 either employed or unemployed or a student。So a person is going to be a tuple of two things。

 the class and their person info。So if I want to say I had a person。

 I would put it in a tuple where the first thing will be Bob is employed。And then Anne is a student。

And they should type check as a person。Oops。sorry here。That they should now， whoop step put。



![](img/09806f8e90db4a7a51e104c18933eb33_15.png)

All right this should now type check so I have two people but another thing can I can mess up is this tag here this employed needs to make sure that this re is positive there's another area of mismattch via just the type we have so many points of error okay how do we do it better let's try doing it better。

😡，Here's my other motivating thing to you， which is like if I wanted to write a function I took in a person info and raised the tuition by 4%。

😊，If you apply this to an employed person， this will give them a 4% raise。

If you apply to an unemployed person， the real that's sort with them is zero， so won't do anything。

 but the idea is like。We can write code that applies in cases we didn't want it to because it's too general。

 because the types are too general， let's make it specific。😡，系。😊。

So here's what we're going to do better。This will be our new type。Now。

 instead of having employed and the student and unemployed be unaffiliated tags。

 we're going to put the relevant data with。😡，The constructor so employed is a constructor that takes in two things。

 a real and a string， it takes in the paycheck and the company name because those are the only fields that matter to someone that's employed to a student it takes in a real and an in tuupple because the only two things that matter to a student are the real which is their tuition and the number of courses they're taking。

If they're unemployed， there's only two things that matter， but it's an insA string tuple option。

 what this means is that unemployed takes in either none or it takes in sum or that sum is a tuple of insar string basically it means that the int in the string can't both they have to both exist if any of them exist okay and the reason is because if we're talking about the day since last employment and the name of their last employer one of these you shouldn't have days since last employment but not have a name of your last employer okay it's either you were never employed or you were employed and you have both those data okay so this is our new type and I actually misrote this this is supposed to be data type but this is the idea and we also factored out type person equals string star that a tuple of the string because every person has a name okay know also how unemployed people don't have a real because they they don't have an useless zero or real because they don't have a paycheck。



![](img/09806f8e90db4a7a51e104c18933eb33_17.png)

So let's take this and put it into SL andJ。We want to put it directly into the file that we were working。

Okay， let's do it。 And this is going to be indented weirdly， but I'm going to fix it。

 so we don't worry about it。O。😊，And this is actually data type。啊 ok。😊。

And then it should now look familiar to everyone Okay cool so this is what how we use to declare a person。

 let's do it differently let's do Bob again， but now as a person with this new representation。

And essentially I've like shadowed the type here I've yeah， essentially I've shadowed the type。

 so don't worry about it， you can do that。Okay， so if we wanted to define Bob and let's not write P。

 let's write Bob。😡，So let's say Valal Bob is going to be equal to this right it's a string。

 it's a tu of a string cell class， so his name is Bob and his class is employed。😊。

But employee only takes in two pieces of data。His paycheck and his company name。

 what did we say it was， we said that his paycheck was 2000 because he's getting cheated by his boss and his employer is Bank of America。

No no options necessary because we have all the data that we need， no nuns， no options anywhere。

 and now if we wanted to define an， we can say that an is a person whose name is An。😡。

She is a student。😡，And tutuition is negative $70，000 sorry， $50，000。😊。

And then her number of courses she's taking is five， again， real string， real string。

 no options because we isolated it to the case that we care about。😡。

And now if we run this through SL。😊，It works， it compiles。

And it's way better than what we had up here where we had like three different nuns or three different nuns。

 and this is actually what other languages kind of do you might have like a bunch of fields where all of them are called nullable and then you set them to like null or none and you have to just deal with that and you might mess it up you might make it something that's not none。

 not null but that's on you that's now your prerogative。😡。

So don't do that what the what I'm trying to show you here is that the power of types is that we can craft types to fit our problems such that we don't need unnecessary representation。

😡，The the official mantra is make illegal states unrepresentable if a state shouldn't happen。

 make it so that you can't possibly phrase it that the program will complain at you before you even get the chance that's the idea behind types so to finish this off I'm going to talk about this idea I call typecasting so again it doesn't mean turning a value of a type into a different type。

😡。

![](img/09806f8e90db4a7a51e104c18933eb33_19.png)

But it's just like something I made up， so don't say it to anyone else， it'll make sense them。

Similarly to how we have blacksmiths， okay， and you have blacksmith and they have like a mold and they cast metal by the pouring metal into the mold to make like a hammer and depending on what the mold is they get whatever they wanted they cast metal to fit whatever tool they want。

Typecasting is my tongue and cheek way of referring this phenomenon where you fit the type to your problem。

 you cast the type into a mold that fits whatever representation you want because you have that power that's what algebraic data types that you do and that's so different than many other languages honestly some languages don't have this。

😡。

![](img/09806f8e90db4a7a51e104c18933eb33_21.png)

I'll leave you with this final note that an imperative programmer tries to fit square pegs into round holes。

😡，But a functional programmer sees a hole and can make a pe definitive in it。Any hole。Every hole。

Right。Thank you。
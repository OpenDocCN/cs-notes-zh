# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P4：-04-Lecture 4_ Object Oriented Rust - GPT中英字幕课程资源 - BV1D142147he

Hey everybody， welcome， welcome to lecture so today we are going to be implementing a linked list together in rest。

 it's going to be a great adventure and。Yeah this is also my first time live coding so that's going to be interesting too I'm going to try to go slow I'm going to ask I'm going to pause a lot for questions and I want you to please interrupt me if you have any questions as well in order to do the live coding I'm going to share with you all this thing called rest playground which is actually a rest I guess you could sort of like it's a way to like run rest code in your browser。

And it's super helpful because you can share little snippets of code with people。

 I think y'all might have seen it before I've used it in the slacklack。

But then afterwards I can actually share this link with you and you can like play around with it yourself。

 so that's also super convenient。So before we get started， are there any questions？About anything。

So we're gonna to see a lot of ownership and borrowing stuff pop up in like just this example using linked lists and everything。

 So if you feel like you want more practice with that， don't worry。

 we'll definitely get a lot of practice with that。Okay， so I guess without further ado。

 I'm going to share my screen， let's see how do I click this button and I say this one。Great， okay。

Can people see that？Okay， great。Right， so now how do we get started right， so first of all。

 So this is also just going to be our first introduction to object oriented rest。

 And so rest allows you like CNncC plus plus to havestruct。

But the cool thing about rest Strs is that they sort of enforce this idea of type safety。

 I'm not going to go too much into what type safety means for the purposes of this lecture because I'm trying to just introduce these concepts in terms of how you'd use it。

 but like the gist of it is you can't。For instance， like do like an invalid cast or something。

 you can't reinterpret memory in unsafe ways and oftentimes these are common areas that happen in languages that are not type safefe。

 like languages like see for instance， where you can misinterpret a piece of memory and you end up just like sort of populating orstruct with garbage values So this is another nice feature of rust that kind of ties into the memory safety a little bit I'm not going to talk about that too much though So the first step when we're constructing our linked list is we need a definition for for our node right and our nodes are going to be he allocated So I'm going quickly show you how do how do you like allocate things on the heat Does that sound good。

Great okay， so if I want to allocate something on the heat I use this thing called box and rest it's kind of like unique pointer and see it plus plus you might not have seen that before that's okay it just means that I'm going to have a pointer to heat memory and this is the only thing that is going to be pointing to this heat memory so what this means。

So I guess could someone quickly like answer like why why is this useful。

 why do we want to ensure that there's only one pointer to this heat memory， what does that mean？

Like， why is that maybe relevant？Does anyone have any ideas？

Like that might have to do with ownership， right， like how does that interact with with what we've been talking about for ownership。

 feel free to unmute yourself。So if I guarantee that this object contains a point of a heat memory。

 like what happens when the object goes out of scope， for instance， maybe？



![](img/67b74d5773190a9f9823e870d25cb11c_1.png)

![](img/67b74d5773190a9f9823e870d25cb11c_2.png)

Exactly it will autofree because there's this function called drop that gets called when an object goes out of scope right when when it's lifetime ends and then that way we don't have to worry about memory leaks for boxes and it will auto free itself we don't have to worry about double freezeze either because we can't manually free ourselves freeing is fundamentally unsafe thing that rest will prevent us from doing with that so yeah so that's great so an example if I use the syntax is I could say like let X say it's like a U 32 or actually the way I'm gonna to annotate as I'm gonna to say it's a box containing a U32 so this is kind of like the vector syntax we saw before iss going to equal box new of say10 or something like that right？

And then I could do something like printlin。Bing。There a format string X。

 And we're going to see what this does。 So we can run it right in our browser。

 And what is it going to say， It prints out 10。 Another funny thing to notice here is if I do。Star X。

 what do you think is going to print out？Well，'s let's take a look。

It also prints out 10 that's kind of surprising right so this is kind of like one of the quirky things to remember about rust it kind of autodereferences things for you sometimes other times it doesn't Kevin asked a question about this on the slackla which was a great question for the so the internals of how printlin works we're not going to talk about it too much yet because it's a macro it's a little bit more complicated but it kind of knows like auto dereference things like integers in order to display them and later on when we look at actual struct we're going to see how that plays out as well so I guess without further ado let's get started and let's try to define our struct right so。

The syntax for defining a struct and rust looks like this so I'm of astruct node and I first of all。

 okay， y'all have probably made linked lists before what needs to go inside of this struct somebody help me out here。

I' to make this interactive， I'm going to go crazy if I just hear my own voice。



![](img/67b74d5773190a9f9823e870d25cb11c_4.png)

Okay， forward and backward is great for double linked lists Doub linked lists we might talk about a little bit later because they're a little bit fancier in terms of how the pointers work so what if I wanted something simpler。

😊。

![](img/67b74d5773190a9f9823e870d25cb11c_6.png)

![](img/67b74d5773190a9f9823e870d25cb11c_7.png)

![](img/67b74d5773190a9f9823e870d25cb11c_8.png)

Exactly right so we'll have like our value let's say it's just going contain u 32s you might be wondering what if I want a more exciting link list that can contain anything we'll talk about that a little bit later next week when we talk about generics and traits and stuff like that but for now we're dealing with integers we're great with integers right and then you say we should have a phone or like a next what type should this next have。



![](img/67b74d5773190a9f9823e870d25cb11c_10.png)

What do people think？Okay， well， I showed y'all how to make something that's a he allocated pointer or guess a pointer to something on the heap。

 so what might you use there？

![](img/67b74d5773190a9f9823e870d25cb11c_12.png)

![](img/67b74d5773190a9f9823e870d25cb11c_13.png)

![](img/67b74d5773190a9f9823e870d25cb11c_14.png)

That's a great idea right so we do next box containing a node right， so it would be a box of node。

Something like that， does that look good to everybody？



![](img/67b74d5773190a9f9823e870d25cb11c_16.png)

Right， so here's here's a quick question I just thought of so a box is a pointer right but we've been talking about how references are also kind of pointers Why couldn't you have a node ampersand here Does anybody can anyone answer that question。



![](img/67b74d5773190a9f9823e870d25cb11c_18.png)

![](img/67b74d5773190a9f9823e870d25cb11c_19.png)

So yeah， you would be borrowing and more importantly。呃。

Does anybody know what would be wrong with borrowing？Like borrowing works in other parts of rest。

 Why can't we borrow here。

![](img/67b74d5773190a9f9823e870d25cb11c_21.png)

![](img/67b74d5773190a9f9823e870d25cb11c_22.png)

You'd be borrowing like a node， I think the idea would be doing something like this right so without without the box just next colon Ampersand node。



![](img/67b74d5773190a9f9823e870d25cb11c_24.png)

So look at the compiler area， it actually says expected named lifetime parameter。



![](img/67b74d5773190a9f9823e870d25cb11c_26.png)

This might give you a hint of what the issue could be here。



![](img/67b74d5773190a9f9823e870d25cb11c_28.png)

That's exactly right Like if you want to borrow a node here who are you gonna borrow it from you have to ensure that that node survives for the lifetime of this linked list and there's no good way for for rust to guarantee that like that ownership is going survive for as long as you need it and so we actually need to own the node here and that's why we put it inside of a box a box is a pointer it's an owned pointer to somewhere on the heap and it's gonna survive as long as the box survives So like a nuanced thing I want to point out here is like the rest compiler is actually so nice gives you a suggestion for what you should do but sometimes you don't want to follow these suggestions so here the rest compiler is saying oh you need to do a lifetime parameter right so I could write my code like this where I say tick a tick a is essentially a variable saying like this node is going to live as long as a a is like a lifetime right and then I could say tick like ampersand tick a or something like that and if I do that。



![](img/67b74d5773190a9f9823e870d25cb11c_30.png)

It is still angry a note， sorry， it has to be note of。And I guess ampers be。Next。

 So I think it would be something like this， actually。

You have to do something like this actually which is okay we're not going to talk about this syntax for a while I just wanted to show you here that this is an example of how you can communicate to your code i'm going to promise that it's going to live at least this long but this is not what we're doing today。

😊，I understand it like this might have been a little bit confusing to show you。

 but I just wanted to give you an example of you can communicate to the rest compiler how long these things should live and this is something that we'll actually see a little bit later on but that's not what we're doing today so that's why we're gonna have it as a note just like that so forget I even said that that was kind of just more of like a little bit of an advanced point there but this compile is just fine and right this is great so like my linked list how do I know i'm done my next is gonna have a null in it right。

😊，So does that feel wrong to anyone with the current setup we have like what do we just say about null pointers？

Like can my box， can I do a box， can I， can I can I do like box， Col and cold and no？

Does that make sense No right， so what do I have to do。

 what tool do we have to use that we might have seen recently that Ryan introduced last lecture。



![](img/67b74d5773190a9f9823e870d25cb11c_32.png)

![](img/67b74d5773190a9f9823e870d25cb11c_33.png)

Exactly exactly so I'm going to say next is an option of box of node and it looks like that's kind of a mouthful to say option of box of node Ru actually lets you do type declarations and type definitions and stuff like that I'm not going to show that right now maybe I can like provide a link to an explanation of that in Slack I just don't want to like bombard you with too much new information but for now let's and I also just want us to like sort of let that sink in this is an option containing a box of a node Are there any questions so far。

Okay， great。 So then now what do we do right， so now we actually have to implement our linked list right and say our linked list is going to long list Okay。

 linked list， we want it to contain， you know， some sort of head。

And we want it to contain let's say a size we want to keep track of our size so as you see the size should be should be stored as a u size。

 this is the syntax remember it's a colon on the left hand on the left hand side of the colon you have the variable name on the right hand side you have the type。

So what type should the head be？What do y'all think？



![](img/67b74d5773190a9f9823e870d25cb11c_35.png)

![](img/67b74d5773190a9f9823e870d25cb11c_36.png)

Exactly， exactly exactly if we just had a node， we're promising that our link list is at least size one。

 but it's going to start out empty right so it should be an option of a box of a node exactly does that make sense to everybody。

😊。

![](img/67b74d5773190a9f9823e870d25cb11c_38.png)

And now I'm going to show you sort of like the object oriented syntax for。

Implementing like functions on these objects。 So the way you do this is you'll say something like Iple node。

 Let's start with node。And the way I'm going to do this， I'm going to say public function new。

Is going to take in so we're going to create a note what should I pass to my new function What do you all think So this is my constructor I could have named it anything。

 but I'm calling it new because that's just convention and that's good style。

So what should my constructor take？Like if I'm trying to make a new note。



![](img/67b74d5773190a9f9823e870d25cb11c_40.png)

![](img/67b74d5773190a9f9823e870d25cb11c_41.png)

Right， so value is a U32 and okay。What else maybe， I guess we have two things that arestruct to fill in。

 right？What's， what's the other thing we need to specify to have this be like a nice。

 well defined node。Exactly， exactly， thank you。 So well， next， it would be an option Fox node。

And then right so we have that and okay and then let's see and then I'm gonna show you the syntax for constructing a node right so we'll do some the way the syntax looks is it will be node with the brackets So kind of like ourstruct definition except on the left hand side will have again like the variable name on the right hand side will'll just like plug in what value we want there to be so I know this looks a little bit funny because like it's called like value it's like value twice but the value on the left hand side is thestruct member it's important to remember the value on the right hand side is from our actual parameter right so it's like value value and the next next would be correct here。

Does that， does that syntax make sense to people， So this highlighted portion is the name of thestruct。

 Look how it actually highlights in thestruct。 This highlighted portion is the name。

 I guess it's highlighting all the values in the program。 But。

 and this highlighted portion is the actual parameter。 Does that make sense to people。😊。

Another thing I want。

![](img/67b74d5773190a9f9823e870d25cb11c_43.png)

Becauseuse you know like the 106 is is we always say like if you make it the same it's kind of confusing so we prefer that you make it slightly different So I've seen in rest code basiss people doing stuff like this and and like I think it's fine I feel like if you're to call it something like temp value and temp next for me it's like I think it's like a matter of personal taste but I think it's fine because it's like this new function is very simple right it's literally just taking all of our parameters and it's put it's plugging them into into the little members of the Str so I think it's okay to do this but in other cases you do want to like kind of differentiate your variable names that's a good point。



![](img/67b74d5773190a9f9823e870d25cb11c_45.png)

![](img/67b74d5773190a9f9823e870d25cb11c_46.png)

That's a great question that we will answer soon once we start defining methods on our node or on our linked list that can actually modify things so it depends like what kind of a reference do you have to your node if I have a mutable reference to my node then sure I can start changing things around if I have a shared reference like a borrow a shared borrow to my node then I can't do that but that's a great question so you're already thinking one step ahead there。



![](img/67b74d5773190a9f9823e870d25cb11c_48.png)

Another thing I want to like notice here is that we don't have a semicolon here。

 this is because this should actually be returning something。

 so I forgot you need this arrow and you're going to say this is going to be returning what it's going to be returning a no。

RightSo if I had a semicolon here， there's actually going to be a compiler error that you will see compiler error is going to say mismatch types。

 it says expectedstruct node it found this empty parentheses so these like this empty pair of parentheses is something called the unit type。



![](img/67b74d5773190a9f9823e870d25cb11c_50.png)

You don't have to worry too much about what that means but that's basically it just means like nothing kind of it's different from the none of option it just kind of means that like its void you should think of this as a void basically more or less right so this means it's so when you put。

When like in a function like the what the last expression and the function evaluates to is what the function returns so if I put a semicolon that makes that expression evaluate to void it makes it evaluate to the unit type here I remove the semicolon and it's happy with me。

Does that make sense？Okay， great。 So we do the same exact syntax for linked list， right。

 so now that you'all have seen a syntax， can somebody tell me what I need to type here。

Someone's just sort of like narrate when you help me out here。

So to remind you the link list looks like that， maybe I should close this actually great now you can see all of it。



![](img/67b74d5773190a9f9823e870d25cb11c_52.png)

So what do I need to type here？

![](img/67b74d5773190a9f9823e870d25cb11c_54.png)

![](img/67b74d5773190a9f9823e870d25cb11c_55.png)

Exactly right。 So head is going to be of time。 Okay， well actually。

Let's say we want to initialize an empty linked list。What should I do。Let's say actually。

 let's say our new doesn't take in any arguments， it should initialize to an empty linkus。What do I。

 first of all， I'm missing something here， what am I missing？



![](img/67b74d5773190a9f9823e870d25cb11c_57.png)

Exactly， the return type is going to be a linked list。



![](img/67b74d5773190a9f9823e870d25cb11c_59.png)

Okay， and now what am I missing here， what do I need to， what should what should this be。

 what is an empty linked list？

![](img/67b74d5773190a9f9823e870d25cb11c_61.png)

![](img/67b74d5773190a9f9823e870d25cb11c_62.png)

Exactly， so we're going to set， so head is going to be none， right， we don't have a head yet。

 we don't have， we don't have a node yet and the size is going to be0。



![](img/67b74d5773190a9f9823e870d25cb11c_64.png)

Does that make sense to everybody？Any questions about that， so let's just run it to make sure it。

Pileles。Run， okay。

![](img/67b74d5773190a9f9823e870d25cb11c_66.png)

Great， so that that compiles it outputs 10 because we saw this here。

 we're going to get rid of that soon。Great， okay， so now let's let's go forward。

 let's make this a little bit more interesting so we defined our new function。

Let's define is empty and get size， so let's define get size first So this is going to be interesting because this is going to incorporate a little bit about what you know from borrowroom right so I'm going to say there's going to be a public function get size。

And like Python， there's this self keyword， so I'm actually going to say amperserson self。

And then I'm going to say right that's the only parameter it should take right and what do you think should be returned here like if you had to guess what the syntax would be。

 what do you think I would type here？Like what's the most intuitive thing？

Maybe for those of you who know Python。

![](img/67b74d5773190a9f9823e870d25cb11c_68.png)

s。Like if this were Python code， what would I type？



![](img/67b74d5773190a9f9823e870d25cb11c_70.png)

Exactly， thank you， Michael， so it would be soft out size。



![](img/67b74d5773190a9f9823e870d25cb11c_72.png)

Right。

![](img/67b74d5773190a9f9823e870d25cb11c_74.png)

Oh， oh， yes。 okay。 That's all。 Thank you。 You caught that as well。 U size， arrow U size， great。

 But okay， that kind of remind me of something else。 So self is a shared reference。

 A shared reference is kind of like a pointer。 normally we do reference pointers。 So first of all。

 let's see if the compiler is happy with us when we do this。 So if I do Ampersand sell， sorry。😊。



![](img/67b74d5773190a9f9823e870d25cb11c_76.png)

Start yourself。

![](img/67b74d5773190a9f9823e870d25cb11c_78.png)

Thought size。 What does it say， You think it's gonna be happy with me。

It is happy with me it thinks that's great right but it's warning me that get size is never used the funny thing is that if I just take this away it also works just fine this is because rust when you're accessing astruct member it will dereference it as many times as it needs to in order to get to like know the core of thatstruct member which is weird I understand that that might be like nonintuitive this is more of just you can think of it kind of as like syntactic sugar but this is just something to keep in mind like idiomatically it's better to like not explicitly dereference things if you don't need to in certain cases you will like if I it's kind of like a little bit of a tangent so if you have like questions about that maybe save those for after lecture because I want to like make sure we get through all of this but like an example would be like if I'm iterating through a vector of integers my iterator is going be a pointer to each thing in the vector and it's gonna be a pointed to an integer and if I want to like increment that value or something if I had a mutable iterator。

😊。

![](img/67b74d5773190a9f9823e870d25cb11c_80.png)

![](img/67b74d5773190a9f9823e870d25cb11c_81.png)

![](img/67b74d5773190a9f9823e870d25cb11c_82.png)

I would have to do like star and I have to like increment it or something。

 you might have seen that in the previous week's exercises。Any questions so far？

So for now just remember that it will it's smart enough to know how to dereference it right so now if I want to do like public function is empty right first of all。

 what kind of a reference do I need to sell。Like what's the first parameter， what do people think？

Yeah， exactly Amperserson self， great， a lot of people said it and what is this going to return？

Its going to kind like a bully， right？And then I will say。

 so there are multiple things I can say here， someone have a suggestion。



![](img/67b74d5773190a9f9823e870d25cb11c_84.png)

![](img/67b74d5773190a9f9823e870d25cb11c_85.png)

So soft dot size equals equals zero， like let's see， is it happy with that？



![](img/67b74d5773190a9f9823e870d25cb11c_87.png)

Yeah， so it's happy with that another thing I could have done would I could also say， you know。

 we could say head dot is none。That's I'm just showing you different possibilities。

 I want also show you that you can call functions for the class from within the class。

 I can say self。ge size。Is equal to zero right now this might not be the most idiomatic thing because like why do we need a function call if we already have a priority already inside of the class and we already have like size。

 but I just want to show you that this is also possible like you might want to be calling functions from within the class inside of the class does that make sense to everybody。



![](img/67b74d5773190a9f9823e870d25cb11c_89.png)

Great， okay。Okay， great。 So I just want to show you some syntax for how we'd actually like get started with constructing this。

 I could say like let list of linked list。Equals what do you think it should。

 what should I put on the right hand side of the equal sign？

I don't know if you'all y' all remember like if you're defining a new vector。

 if you're defining a new string， like what sort of syntax you use？不。



![](img/67b74d5773190a9f9823e870d25cb11c_91.png)

![](img/67b74d5773190a9f9823e870d25cb11c_92.png)

Exactly， be link was Col calling you。Right。Oh， it was angry it's because I forgot semicov。

There we have classic。 Oh， and it's also because I deleted X， obviously， I'm sorry， great。 Let's see。

 What does this do。Great， so it doesn't output anything so yeah。

 so I could do linkless Col call new and to test my functions。

 I could say something like print Bang and I'll just say。You know。

 we'll try to display what happens when I do list do is empty。Let's see what that outputs。



![](img/67b74d5773190a9f9823e870d25cb11c_94.png)

It outputs true right， you see that down there so it actually knows how to display things like true。

 which is pretty cool to think about。We could also do something I want to show you like in rust when you're trying to desert when you're trying to like assert your code like do assertions for tests you can do something like assert bang list dot is empty This is like a useful thing to know when you're writing unit tests and rust so if we do that。



![](img/67b74d5773190a9f9823e870d25cb11c_96.png)

![](img/67b74d5773190a9f9823e870d25cb11c_97.png)

It's going to be just fine， but if I did not is list that is empty。

 what do you think happens with a failed assertion， it should panic。

 should crash my actually wait a second， it does not that is interesting。



![](img/67b74d5773190a9f9823e870d25cb11c_99.png)

![](img/67b74d5773190a9f9823e870d25cb11c_100.png)

Assert that， wait。Oh， it seemed to be okay Oh， sorry。 No， it does。 It said it did panic。

 So it did fail。 It printed out something then it panicked， right。

 So do you see that it said thread main panic at assertion fail。

 So this is how you would write unit tests and stuff like that。

 If you want to show that your code like， say we want to test get size。 Now， we can say assert bang。

 assert E Q bang。 So this is like asserting equality between list dot get size。And at this point。

 it should be zero， right， so we could say something like that。And that didn't panic。

 so we know that all of our assertions must have evaluated to true just note that I removed that negation there。

 Does that make sense so far。Does this syntax kind of make sense， it's a lot of you syntax。

 totally okay if some of it's confusing， it'll definitely be signals。



![](img/67b74d5773190a9f9823e870d25cb11c_102.png)

![](img/67b74d5773190a9f9823e870d25cb11c_103.png)

So we can identify them as macros So what you do in something like C is kind of like a stylistic thing where you'd make everything in all caps and that was supposed to signal to people that this is a macro because like the way the macros work is they kind of just like find and replace things right like that's what the preprocessor will do for like compilation but rest like this is actually built into the language like I can't I can't define a function that has an exclamation point in it does that make sense So this is like a much safer way of doing macros Ru macros are actually super fancy and interestingly there are lots of cool things you can do with them but we're gonna be talking about that a little bit later on but that's a great question yeah。

Are there any other questions right now？Okay， so I guess before this gets really exciting when we start pushing and popping things to it。

 let's all just take like a quick one minute break， like get up。

 scratch like do whatever you need to do。Sort of like。You know。

 we've all been sitting down like 50 minutes is a short amount of time。

 but it's also a long amount of time to sort of do that。Reset yourself。嗯。Okay。Al right。

 just a really quick it's like reminder to get moving。

 maybe go outside today if you haven't gone outside。 that's really important。 wear a mask。

 obviously be safe， but try to get some fresh air for sure， great。

 So now our link this isn't too exciting。 We just made an empty link list is not much going on there。

 Let's actually start adding things to it right so I'm going define a function called push right and public function push。

 Can somebody tell me what I should write next。😊，And so maybe like using what you might know like about borrowing。

Ownership， stuff like that， What should I write next？



![](img/67b74d5773190a9f9823e870d25cb11c_105.png)

![](img/67b74d5773190a9f9823e870d25cb11c_106.png)

Andmpererson， okay？So push is actually going to be changing our list too， right？



![](img/67b74d5773190a9f9823e870d25cb11c_108.png)

![](img/67b74d5773190a9f9823e870d25cb11c_109.png)

So how do I type that？So 8% mute。the same thing。 Yeah。

 so y'all might have seen this on the assignment even last week you'll definitely see on the assignment this week So it'll be Ampersand mute to self So it's important to realize that like something like C++ lets you do this it's just like you put like cont after I guess like the name of your method and this is like saying like a promise that I'm not gonna change anything about the state of the class right but here in rest you have to be explicit about like is this going be immutable or this going be a mututable function So because push we expect to change things in the link we need an ampersand mute to self we kind of need a little bit more than that So we need the value that we're pushing so we could say something like you know value it'll be restreoring U 32s right so are we storing U 32s weoring U size yeah we are rest storing you 32s great okay what goes next。

What do I need to do so like let's like refresh our linkedless mechanics， what do I need to do？She。

It's like the first step。Like if you're writing this in C or Java， like what would be the next line？



![](img/67b74d5773190a9f9823e870d25cb11c_111.png)

![](img/67b74d5773190a9f9823e870d25cb11c_112.png)

Exactly， so how do I make a new note， do you remember？



![](img/67b74d5773190a9f9823e870d25cb11c_114.png)

First of all， what's the type going to be what' to annotate the type？



![](img/67b74d5773190a9f9823e870d25cb11c_116.png)

Exactly， and how do I make a new box？

![](img/67b74d5773190a9f9823e870d25cb11c_118.png)

![](img/67b74d5773190a9f9823e870d25cb11c_119.png)

Box phone and calling new and what do I put inside of this box？



![](img/67b74d5773190a9f9823e870d25cb11c_121.png)

A note， okay， how do I make a new note？Yeah。Okay。

![](img/67b74d5773190a9f9823e870d25cb11c_123.png)

Right， okay， great。Okay， so it'll be node。New and what's the first parameter？



![](img/67b74d5773190a9f9823e870d25cb11c_125.png)

。

![](img/67b74d5773190a9f9823e870d25cb11c_127.png)

All right， so the value is going to be that value。 What's my next now？

So let's look at this definition right so the next is going to be an option box node let's say I want my linked list to have constant time insertion and deletion constant time push and pop maybe the names push and pop are kind of suggested let's say this is going to be a stack right so。



![](img/67b74d5773190a9f9823e870d25cb11c_129.png)

What does this mean for the next point？

![](img/67b74d5773190a9f9823e870d25cb11c_131.png)

Well， okay， yeah， so it could be none。But if we're just moving this to the front of the list。

 what what do we do？

![](img/67b74d5773190a9f9823e870d25cb11c_133.png)

![](img/67b74d5773190a9f9823e870d25cb11c_134.png)

It'll be a head， right， so how do I refer to that head？



![](img/67b74d5773190a9f9823e870d25cb11c_136.png)

![](img/67b74d5773190a9f9823e870d25cb11c_137.png)

Head， okay， right。 So first of all， let's just make sure that compiles by itself。



![](img/67b74d5773190a9f9823e870d25cb11c_139.png)

So this is actually ending up being a stack instead of a linked list to link I mean。

 a linked list independent by， yeah， yeah。

![](img/67b74d5773190a9f9823e870d25cb11c_141.png)

So it seems to be angry here， right， so it does not implement the copy trade。

So how do you think we could fix something like that？



![](img/67b74d5773190a9f9823e870d25cb11c_143.png)

![](img/67b74d5773190a9f9823e870d25cb11c_144.png)

This is kind of an issue right we wanted we wanted an actual we wanted the head of the linked list。

 but we have a mutable reference to it this is kind of a problem。

So the rest compiler has a little suggestion， but I'm going to say we're going to ignore that suggestion for now。

Yeah。What are the thoughts people have？Does anybody have a sense of why there's an error here？で。



![](img/67b74d5773190a9f9823e870d25cb11c_146.png)

![](img/67b74d5773190a9f9823e870d25cb11c_147.png)

Yeah exactly like that's what the compiler says it says head does not implement the copy trait。

 you can't just copy it and it's also saying you can't like what we'd like to do is you'd like to transfer ownership。

 right？嗯。And that's kind of tricky。Because we have a mutable reference。

 and how do we convert a mutable reference to like an owned version of something。

 This is an unfair question of me to ask， because like you haven't learned it yet and I haven't showed it to you。

 but I'm gonna show it to you right now。 So if I have something like， let's say I'm gonna let。

 you know， I'm gonna have something like let X is gonna be， it's gonna be an option of a U 32。

 And that's gonna equal sum5。

![](img/67b74d5773190a9f9823e870d25cb11c_149.png)

Okay， and I'm going to let， let's be like X ref is going to be Amperserson mute to an option U32。

And that's going to equal ampersand sorry I have to say let mute x right not don't want to make an error there it's going to be ampersand mute of x okay。

 so far so good。

![](img/67b74d5773190a9f9823e870d25cb11c_151.png)

So let's just like convince ourselves that this by itself will compile I'm going to comment this out。



![](img/67b74d5773190a9f9823e870d25cb11c_153.png)

So that this by itself is valid so this by itself is valid right there's this function I'm going to introduce to you called take and what take is going to do is it's going to convert this mutable reference of the option to the value。

So the option itself， it will like return like the option itself。

And or I guess like the value inside of the a and it'll leave none in its place。

Or sorry itll it itll still be the option it will convert basically this am percent mute to an own option I will show you a code example of what this looks like So what I mean here is like if I do something like you know。

Results of take。あ。It will say I'll do extra do take， this is what calling it looks like。

And then if we do printlin B of like what's。Like， left at X。This will be X。

We'll actually see how this works and I'm also going to comment out this true。

 I'll just delete that honestly。

![](img/67b74d5773190a9f9823e870d25cb11c_155.png)

So we're going to run this。And let's be how this works。 Oh， it got angry at me。

 What did I screw up because I put I got a little creative with my exclamation point。

 I put it on the inside of the function。 Sorry about that。 Alright。

 let's take a look now Now it should now it still doesn't comp Okay。

 so it's saying I don't know how to display options。 I'm gonna show y'all a little trick。

 I could do debugging like this。 I can put a colon question mark。

 and that's going to display the option for us as a debugged value。😊。



![](img/67b74d5773190a9f9823e870d25cb11c_157.png)

![](img/67b74d5773190a9f9823e870d25cb11c_158.png)

It's still angry oh it's it's angry over here as well okay， it's angry at both of them， but yeah。

 so this fancy colon question mark syntax will display the option in debugging。And this should work。

 great， it works。

![](img/67b74d5773190a9f9823e870d25cb11c_160.png)

Great， okay so let's take a look at this so I had a mutable so to recap I have a mutable reference called X ref to this option and when I call take on this mutable reference。

 it will convert it to the actual option of ownership over it now and the result of take is sum5 which was what was there and then now x is actually mutated now it contains none。

😊。

![](img/67b74d5773190a9f9823e870d25cb11c_162.png)

So you can sort of see like this is doing some sort of like moving around of memory under the hood if you're wondering how this is implemented under the hood it's doing some unsafe operations and we're not going to like delve too much into like。

How this is implemented it's like a like maybe in like like a couple of weeks we'll talk about like unsafe rest and we'll talk a little bit more about how rest handles like raw memory and stuff like that。

 but do the semantics make sense to people like I can have a mutable reference to an option and when I call take on that mutable reference it returns the option itself not as a reference but as an actual value you can think of it right and。

What's left in the original option is none。Does this make sense to people？是。Any questions。

 this is totally confusing， by the way， I think it's not like super intuitive why this works or how it works。



![](img/67b74d5773190a9f9823e870d25cb11c_164.png)

![](img/67b74d5773190a9f9823e870d25cb11c_165.png)

No so take is defined on options so actually there is a more general that's a great question there's a more general version of take that will essentially give a mutable reference to a particular type it'll give you back that type and it'll leave like a default value in its place but we're not going to talk about that right now if you're interested in learning more about that if you look up like mem colon and colon take that's that's what that will do that's a great question。

😊，Yeah， any other questions about this？So I'm going to comment this out for now。

 I'm going to comment this back in so this is our buggy push， what do I need to do？

In order like given that that's what we just talked about， how do I fix this？

Does anyoneone have any suggestions？

![](img/67b74d5773190a9f9823e870d25cb11c_167.png)

![](img/67b74d5773190a9f9823e870d25cb11c_168.png)

Exactly， so let's see if that makes it happy so if I do if I close this， okay。

 so this is what we have so far self do head dot take， what is that going to do。



![](img/67b74d5773190a9f9823e870d25cb11c_170.png)

So we get a lot of warnings because we never use anything。

 but it compiles so that's wonderful right so this is our solution。

 but are we done yet is this actually pushing it to the list？😊。



![](img/67b74d5773190a9f9823e870d25cb11c_172.png)

So what do I need to do now？

![](img/67b74d5773190a9f9823e870d25cb11c_174.png)

Exactly so I can set self dot head is equal than new node and I think this goes back to your previous question No about like how do I modify things inside of thestruct so you notice here because I have an ampersand mute self I'm actually allowed to do this does that make sense great so I can do like self dot head equals new node and what I need to do one more thing I would argue。



![](img/67b74d5773190a9f9823e870d25cb11c_176.png)

So we're maintaining two pieces of state right， how do I update my other piece of state？



![](img/67b74d5773190a9f9823e870d25cb11c_178.png)

Exactly， so I'll do self that size plus equals one and let's see if it's just happy with this。



![](img/67b74d5773190a9f9823e870d25cb11c_180.png)

Now， mismatched types。Oh， okay。 so what's going on here。 Why is it angry at me， it's because I did。

 So how do I fix this， Can someone tell me how to fix this。



![](img/67b74d5773190a9f9823e870d25cb11c_182.png)

I wrap this one in option right so i'll say option box notes so this is definitely a mouthful right here maybe we'll move this over to the next slide so it doesn't go over but now this should compile another thing I want to say like oh actually oh no expected what does it say you have to wrap in some and。

😊。

![](img/67b74d5773190a9f9823e870d25cb11c_184.png)

Wai Yes， box。 Yes， you are totally right。 Some box you。



![](img/67b74d5773190a9f9823e870d25cb11c_186.png)

Right so it's angry about you have a value and then when you put this inside of an option。

 you have to say， well， hey， this option is not none。

 it's actually like something here is the value that it is Another thing I could have done is I could have said this was the new node I think in my opinion。

 it's like slightly more idmatic to say this I'd say self thoughthead is equal to some new node。



![](img/67b74d5773190a9f9823e870d25cb11c_188.png)

This is what I would say。Personally， but like it's the same thing functionally the same thing right。

 so if we run this。Great， so that works Another thing I want to say is like there's kind of this like fallacy like bubbling around where people are like oh the rest compiler is like so hard to pass like once your code compiles。

 it basically is correct right like that's not necessarily true you should still test your code we're gonna do that right now so I'm going actually I'm going copy and paste the cheat right here I'm going copy and paste the display function that I have already prepared and let's see let's see let's see let's see where is it where are you and this is just gonna print out our linked list So the logic here actually isn't like too interesting So that's why I didn't think we need to like code it up together but。

😊。

![](img/67b74d5773190a9f9823e870d25cb11c_190.png)

Dam right there Okay， so this is just going to display our link this so we can like verify to ourselves that it's doing that's doing this correct right so one way to test this is I can say for I in one dot dot dot10 say I'm going to do's first of all yeah I'll do list dot push I right。

And then now I can do link， I can do list dot display。That makes sense to everybody。



![](img/67b74d5773190a9f9823e870d25cb11c_192.png)

So let's actually run that and let's see what happens。Can borrow list as mutable。

 it is not declared as mutable right， so the way we fix out is you say let mute list great。

And now I use variable x F， right， does that make sense to everybody？



![](img/67b74d5773190a9f9823e870d25cb11c_194.png)

so this is a little stack right， it's a stack and it's going to be 98765 because this is the reverse order in which we put things Another thing to notice about this dot dot dot operator is it's1 dot dot10。

 but that actually goes once it's the first thing inclusive second thing exclusive that's that's the convention that Ru uses。

Does that make sense to everybody？Right， and then now if I also do something like print L。You know。

 list size。Then I could also do like list。 gett size and that should output nine if everything is correct。

Right， and we say that list size is not perfect。 Great。 Alright。

 so might have time for two last things。 I'm gonna see if we give time。 But let's see。

 see public function top is the other。😊，嗯。Thing to implement right here and this is going to return what。

What do you think this should return？Are you 32？E 32， okay， what if my list is empty？



![](img/67b74d5773190a9f9823e870d25cb11c_196.png)

![](img/67b74d5773190a9f9823e870d25cb11c_197.png)

Exactly。Option E 32。Great。Now what does my implementation look like？



![](img/67b74d5773190a9f9823e870d25cb11c_199.png)

![](img/67b74d5773190a9f9823e870d25cb11c_200.png)

Great， I definitely want a mutable reference to solve， that's correct。Now it。



![](img/67b74d5773190a9f9823e870d25cb11c_202.png)

![](img/67b74d5773190a9f9823e870d25cb11c_203.png)

Well， so this is a stack we just want to remove the first element。

 so we want constant time addition and dition， but yeah。

If I was doing like a queue or something or like a， I guess like a backwards queue。

 I what would that be， Yeah， it would be kind of like a backwards queue， but yeah exactly。



![](img/67b74d5773190a9f9823e870d25cb11c_205.png)

Yes。That value， okay？

![](img/67b74d5773190a9f9823e870d25cb11c_207.png)

wouldThat would be fine actually， so this would be fine I'm actually going to suggest that we do something a little bit different。

I'm saying let's say that we should get like the node is like let node equal self。head。ta。

Because we're going to be eventually。Sort of like。We need we need this as like a value。

 we need this as an option。

![](img/67b74d5773190a9f9823e870d25cb11c_209.png)

![](img/67b74d5773190a9f9823e870d25cb11c_210.png)

That's a great question Okay， so if soft head is none take is going to return none that's a great question so i'm going to show you all some cool syntax there's this question mark syntax and rest。

😊，And what it does is if self。head。t take is none， then notice how this function returns in option U32。

 if self。head dot take is none， this will just return out of the function after the first line and it's going to return none。

This is like very slick air handling syntax that you could use， right？Does that make sense？Right。

And if it's not none， then node is actually going to be of type， it's going to be of type。诶。Well。

 it will actually unwrap it right， so it will actually be of type box sorry， yes。

 it would be a box mode。So let's actually just compile that to your so compiles， I'm going to say。



![](img/67b74d5773190a9f9823e870d25cb11c_212.png)

Like this returns none no matter what， but like let's just verify that the compiler is happy with that。



![](img/67b74d5773190a9f9823e870d25cb11c_214.png)

So the compiler is happy with that， right？So self what this question mark syntax will do is it will unwrap if it's some。

If it's none， then it will just return none from the function， does that make sense to everybody？

This is kind of funky syntax， but this is like a nice way to avoid match statements which you know like another way like handle errors and stuff like that。

 but this is considered more idiomatic for something like this。

 but notably this works because we're returning an option E32 and this will return none it will return this type if this is if that doesn't work out does that make sense。

Okay， great， so we have this node， what kind of point rewiring do I need to do you can do this in the last minute。



![](img/67b74d5773190a9f9823e870d25cb11c_216.png)

![](img/67b74d5773190a9f9823e870d25cb11c_217.png)

Exactly， so soft that head is equal to we'd say node dot next actually， right？

Because we have this node from earlier here。But if we do， yeah， does that make sense？

Because if we do self do head dot next， we might， well actually let's see what the compiler tells us。



![](img/67b74d5773190a9f9823e870d25cb11c_219.png)

If it's happy with that。嗯。It's angry because it's， well， it's an option， right？

So you need to take it out of the option and that's what we did up here。

But that's that's like a reasonable thing to' going try out there so no dot next and finally we need to return this value。

 how do I return this value？The value of the thing that we just popped off。



![](img/67b74d5773190a9f9823e870d25cb11c_221.png)

![](img/67b74d5773190a9f9823e870d25cb11c_222.png)

Right， okay， so I would say some of what。Exactly some of no dot value。

 let's just make sure that compiles and before we go， let's just test this out real quick。

 So if I do printland thing of let's say like。

![](img/67b74d5773190a9f9823e870d25cb11c_224.png)

First elements， so be， I guess say I guess top is a better top elements I gonna I say list dot pop。

 I'm going to say unwrap here because we know it's we know it's not empty because it's returning an option then I and then if I do list do display again。

 let's just make sure that this makes sense So I'm going to run this。Great。

 so top element was nine and now the list is87，65，4，321， great。



![](img/67b74d5773190a9f9823e870d25cb11c_226.png)

![](img/67b74d5773190a9f9823e870d25cb11c_227.png)

That's okay， great。 We didn't。 We forgot to。 I will， I will do that。 So let's see。

 So we'll do this one and we'll just say self do size minus equals one。😊。



![](img/67b74d5773190a9f9823e870d25cb11c_229.png)

Great。And I realized I also committed an error in the lecture notes， so I will update that as well。

 but now if we do printlin thing you know， size。

![](img/67b74d5773190a9f9823e870d25cb11c_231.png)

We do list that get size。

![](img/67b74d5773190a9f9823e870d25cb11c_233.png)

Then we should also see that that has decreased to eight。



![](img/67b74d5773190a9f9823e870d25cb11c_235.png)

So if we look down here exactly， so list size was nine。

 the top element was nine we popped it now it's 8765 and the size is now eight great。

Does that make sense to everybody， this is a really involved example。

 it's a lot of new concepts that y'all haven't seen before。

 but you'll definitely see again in this week's exercises。



![](img/67b74d5773190a9f9823e870d25cb11c_237.png)

I will share a link to this so that you can play around with this yourself and you can， you know。

 maybe you wanted to find like a copy function for your linked list。

 maybe you want to you know see if you can like get generics working with it if you want to study up on that。

 but yeah that's all that's all for this week， please stick around if you have any questions。



![](img/67b74d5773190a9f9823e870d25cb11c_239.png)
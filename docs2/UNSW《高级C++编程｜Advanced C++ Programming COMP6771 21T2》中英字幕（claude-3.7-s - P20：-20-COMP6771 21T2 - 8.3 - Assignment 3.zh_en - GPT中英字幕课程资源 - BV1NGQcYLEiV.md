# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P20：-20-COMP6771 21T2 - 8.3 - Assignment 3.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Okay， so assignment 3， it's been out for a week， and it's due in 12。The13，13 days， Monday week。

 little 10。 Yes， assignment 3 is。Assignment runss a very old assignment。

It was written years and years and years ago。 We've just adapted it。

 Assment 2 was written by Brad Heap， and we've adapted that。 and that one was written by another one。

 Assment 3 is another one that was adapted in 2019 I。

Think where we wanted to do something more complicated。Then。You know。

 just like a vector or something。So we made a graph assignment because we wanted to get students comfortable with。

In particular， templates。And。Custom iterators like the week 7 topics。

 that's like the bulk of what this assignments about。

 So it was really about can they get comfortable with templates and custom iterators but it was also designed to be quite just a bit more complicated to actually really hone in some of you'll C+ plus knowledge。

 So the good thing about this assignment is that structurally speaking in assignment too and I know many of you who haven't started this will have started this we like yeah yeah yeah But assignment too we asked you to create a Euclidean vector which was basically an object that could store values as like an array。

 it was like an array wrapper， but for a vector and。Yeah， that was the。

That was the gist of it and we asked you to use operator overloading and some smart point not really much for smart pointers。

 but a little bit with smart pointers to basically define your own library and avoid using SL containers but instead you use primitive style arrays。

We gave you a bunch of member functions and constructors and this and that to implement in assignment 3。

 though， we're expecting you to do a similar thing， except instead of making a。

Euclidean vector were're asking you to create a graph， a generic graph。

So that's a graph whereby the type of the nodes here。

 type T here and the type of the edge weights here you are generic。 they can be any。

Type in particular， ordered type， I think。 But， you know， I mean。

 for we just test this with strings in doubles， like it's not rocket science。

 like we don't test it with crazy things。 It's just strings， ins doubles chas， like stuff like that。

 So you can have a graph of kind of any type you want。Like assignment，2。

The graph is defined in graph at HPP and because it's a going be a templated type。嗯。You have to。

Put all of the definitions inside the HPP file， either inside the class body or underneath the class body。

 depending on your judgment as to whether you think it's sufficient。

 like whether it's the right thing to do。So very similar， it's a class。It。

This one's gonna be templated。 We haven't put the templates here。

 Anyone who started has probably put the templates there themselves。 In fact。

 like it really depends on how you want to go about this。

 Some of you might prefer to go about this making the entire graph work。

 just feel like in and then go back and template everything。

 I don't know if I would necessarily recommend that I know it's something that some people would find easier And if that's really your jam then go for it。

 the main reason I say that is because it's probably very easy to underestimate how painful it would be to make to retroactively put template type name in all the right spots。

 and you'll come across a whole bunch of errors。 So if you do take that approach。

 my only advice is don't think you'll just like in an evening go and make it template it or whatever。

 but I would recommend you start off actually making it templated。

The cool thing about the graph is that it's going to follow a really similar structure to the。



![](img/79aab290c7ce7dc57087c8e777a085cf_1.png)

The books， and。The rope examples from。Lectures， so in my tu today in Tu 8。

 which will get uploaded tonight。We we did an example of this so you can go watch that or go your tutors to。

 go to whatever tutor it doesn't really matter。Maybe it's not here。 Is it here， Class temp Ins stack。

 Oh， yeah， we did the inst example。 So it's like， if you're looking for inspiration。

For the custom iterator part， you can go look at the inst example or you can go look at the28 examples that we went through because your graph will follow the same general pattern of you've got a class and it's got a class iterator inside of it and then you've got some beginss and ends and like you can look at stuff like this or the Tu 8 rope example to really get yourself like a bit of a bedrock in how this works in a general sense。

 there'll be some extra little things you have to consider。



![](img/79aab290c7ce7dc57087c8e777a085cf_3.png)

Probably one of the more interesting。 let's go into it as we go， but。U。This is your templated graph。

generic。Directed weighted graph is the name space it's in。

 You have a graph that takes into templated types because it's directed。

 There is a sense of order with your edges。 So if something has an edge from A to B with weight。E。

 that doesn't mean that there's an edge from beta。B a。So edges。You know。Edges are directed。Sorry。

 I'm just reading some of this again。Dmitri says can we take Instax as an example。

 I think Inst is a great like like I think InsStac is a good example。's it's not perfect。

 Instax is not templated number one， okay， that's a really important thing like your your assignment expects you to do a templated type Instac is bidirectional。

😊，No， it's not。 Sorry。 It's just const。 I it。 No， no， no。So I think the only two things are that。

 One is that Instac as a forward iterator。 The iterator you want for your assignment is bidirectional。

 That's one particular challenge。 The other thing is that Instax is not templated。

 which is kind of relevant。 We've been very kind to you。 And we've actually given you the。

Full like iterator class definition。 So you can actually copy and paste this in。

 You can copy the whole thing in。 Most of it's like all the declarations are done for you。

 which is great。 We've made it clear that you have to define the equals operator。

 the post and pre increment in both directions。😊，The pre increment post increment， pre decreement。

 post decreement。The D reference， the constructor， and then just the iterator traits here。嗯。

Most of these are defined for you。 And， in fact， value type or graph any E value type is already kind of defined for you。

 too， in the dot H in terms of we've actually defined it here。 So as part of the graphs public。

In the public part of the class graph definition。There's actually astruct value type here。

And when we designed this assignment， there was a lot of debate as to like what iterating through it meansca it's like how do you iterate through a graph。

 That's a bit weird， like most data structures you can iterate through pretty intuitively。

 but what we decided was that iterating through a graph is iterating through its edges in sorted order。

 I think it's still sortded order。嗯。in some kind of sort order。

 but that sort order is based on first， the source node， then the destination node。

 then the edge weight。So like if you have a whole bunch of， you know， nodes and stuff， it's like。嗯。

Each time you iterate through the graph， you will get a littlestruct。Of three values， N。

 n and E for the from node， the two node and the weight node。

 And the point is that they should all be sorted in terms of， you know， the from node first。

 So it's like， if you add a graph like this，1，2，3，4。The point is that， you know。Let me just get a。

You just draw something slightly different really quick。 You know。

 if I had a graph like this where I had， you know， one，2，3。There's， there's one。

 I'll draw some arrows。 I'll give these letters。 There's one。 there's2。There's three， this is A。

 this is B， and then this is C。It's like if you were to try and iterate through that。

 you would get one。2。Bei。😊，1，3， a。31 c like that。 So you'd get it in order of like it's always sort of by the from node then it's sort of by the two node then it's sort of by the edge weight。

 if there were multiples。 I think an important note to point out is that up the top of this's it's made clear that edges can be reflexive。

 That is to say the source and destination nodes of an edge could be the same That means that you can have edges point to themselves。

And then also G is a multi edged graph as there may be two edges from the same source node to the same destination node。

 So it's possible that you then have another directed line here of weight D。

 so the source and the end node can be the exact same as well。But that's the graph structure。

 so you have to store that graph structure generically and make it iterable and in fact。

 like half the assignment's just making the graph structure and the operations of it。

 the other half is probably getting the iterator working I don't even want to say that's half because I don't think it's half but as you can see there's constructors there's like a default constructor。

There's an initial list that takes in a bunch of。Nos， as you can see there， initialize a list of n。

 there's a iterator that takes in an iterator of nodes。Move constructor。Apparently。

 there's no copy construct。嗯。Move assignment。 Oh there are sorry。 We just organ them the wrong way。

 copy constructor。Copy assignment。 There are all the kinds of ways of creating it。

 Then we have the modifiers。 you can insert a node， insert an edge， replace a node， merge。

 replace a node。 This was this was a little drawing that a student in 2019 made they were like， hey。

Is this what you mean？😡，And we were like， yes， that's a really nice way of describing it。

 So we just put it in the spec。 So I can't remember who made this。 I wish I had put a credit there。

 That's really lazy of me。 I mean they were happy about it。 and they're like mad。

 It's just I hate forgetting who that was because that was really useful。 So you know。

 merge replace node is quite well specified there。 erasing a node。

 erasing an edge erasing an edge based on an iterator instead of a value。😊。

Pretty standard stuff clearing the the graph removes all the nodes from it。

 We've had questions in the the forum already about， you know， can this be。Can we use STL containers。

 yes you can， we're not expecting you to use primitive arrays。Lots more functions。

 and then you get into the iterator access that begins in the ends。The， you know。

 begins for constant objects， the begins for end objects。I don't know if we made this editable。🤢。

Like， I think。I don't I can't remember， I mean， it'd be written here somewhere so I won't comment on it。

 but you know operator equals output operator blah blahlah。

 there's just stuff to do so and it's a lot like assignment too it's just harder right which is the cool part so like you get it right if you get assignment to you get this assignment then you just have to make sense of templates and custom iterators and you're done you just got to do the work So do the work。

We have another iterator。 well， anotherator。 so I'm really tired。

 This is our iterator definition again， because you can copy and paste this。

 we hope that it takes some of the stress away for you in terms of like worrying about what this is。

I even looked at the spec for a few weekscause I， I kind of polished it up and then。

Just haven't looked at it since we released it because last week it was just a horrible week。

In terms of the iterator there's more specification about how they work。

 we gave examples about what a sorted graph means， so you can actually like look at an example here。

 The only thing missing from this example is two edges that have the same source and destination node。

 but you can make I trust you all to make sense of that blah blah and then we have our compulsory internal representation So this is the only thing worth making node of。

 so we don't tell you how to store your nodes and edges you can use vectors or sets or anything you want。

 The only things we specify that they have to be heap memory stored。

So like how whatever structure you use， the actual nodes and edges themselves are he objects， right。

 And when we， and you can see this here by。So what we expect。Is that if you create a graph。

 I think this fund is important。If you create a graph and then inside a scope。

 you create a string and then you insert that node into the graph while that string is copied into the graph。

 you need to create your own copy of it on the heap such that you know if whoever kind of gave you that value at the start。

 if they disappeared or they went out of scope， you still hold that value validly right like and the resources of your graph should outlive the call as resource。

 So once it gets into your graph， it outlives whoever gave it to you until you're done。

So we do expect you to create memory on the heap You do need to use smart pointers for that to solve that problem So someone gives you a stack string you use a smart pointer and to create like a heap object managed by that smart pointer of that node or whatever the constraints to point out are that for each node in the graph you're only allowed to have one underlying resource stored in your graph for it。

 Now this is I guess， important depending on what your implementation is basically。

In your representation， you might have pointers to nodes。

 you might have multiple pointers to the same node， depending on how you saw things。 for instance。

 for instance， if you， if your graph is just a， here's a simple example， right。

 you could have a standard vector of n。Thoses all your nodes。

 And then you could have a stand vector of。The， the value type， right， something like this。

 So therefore， like， and this is your like array of edges where like each thing is like， you know。

 node 1， node 1， edge A， node 1， node 2， edge A， node 1， node 3， edge B， like whatever it is。

The thing is， though， that in this particular structure。You have。This one used a few times， right？

And the point is that。If you have any kind of data structure that references a node。Multiple times。

 you need to make sure that you're not duplicating that。

 as in these three things should either they should all be pointers to the same kind of like。

One underlying object so。Yeah， you can't create copies of a node like if you have a node in a graph。

 there's only one instance of it being stored in memory in the graph。

 imagine you like think of it like this a node is like a gigabyte。Say。

 and you don't want to have more than one copy of it。 So you need to use pointers。

 You need to use smart pointers。 maybe you use unique pointer with observer raw pointers or maybe you use shared pointers with weak pointers like that's up to you。

 And that depends on your data structure and depends how you're trying to approach it。

 we don't have that constraint with the edges， you can have multiple instances of an edge in memory if you need to。

 though generally we basically are saying that if if if you have multiple instances of edges for no good reason。

 then we won't be happy about it。Fin says so we should only be calling one make Sha or make unique so yeah generally speaking in this assignment you're going to end up using unique pointers or shared pointers you're not really going to end up using both so you kind of just have to make a call based on your data structure I'd probably recommend that you choose your data structure and then you try and make sense of what pointer makes the most senset don't do it the other way around。

Yeah， so that's how you should do it。嗯。Yeah， we use smart pointers because if we didn't use smart pointers。

 there'd be so much copying happening all the time。 Like that's why we like pointers， even though。

 you know， and and the other thing is you can't it's not this there's really long winded reasons why having a vector of references isn't great and stuff so。

Like point we kind of make out like pointers are evil， right，'s it's just that。Poiners aren't always。

 there are sometimes better solutions to pointers。Sometimes they're not。

 and that's really as simple as it is。嗯。The only thing I would say here。 Yeah， I mean。

 all of this makes sense。 we've， it's all pretty similar to the previous assignment。嗯。

I'm sorry this one's wrong。 That's the one thing I did miss。 That's just the wrong。

 But you all know how to clone things by now。 Sorry about that。 I'll fix that up。

 but that's no big deal。 Marketing criteria is exactly the same as the previous one。

 We have clang format things。 We have best practice things， Test correctness。

 your tests are probably going be very similar to assignment 2。 You'll probably have like。30，10，50。

 I don't know。 however many things you want， a bunch of things you want to test like different properties。

 generally speaking， you know， you've got all these different functions and things you can do。

 Test should be the easiest part。My personal recommendation to you as your friend， is probably to。嗯。

To write a little bit of the assignment until you get it。And then go rightdo your tests。

 it'll make your life a lot easier。Y。So I I I wouldn't expect you all to start writing tests for templated types if you you know。

 I mean， you could actually， it's actually not that hard。

 but I get that you want to get your hands dirty sometimes， you know， I get that。

 though make sure you don't write tests till the end。

 you'll just write better tests and you'll get better marks if you write your tests at the start。

 So that's probably one recommendation I have if you do have any other questions about it。

Then the best place to look is。We have a pin post assignment3 spec questions。

 Nathaniel has been on this， like。I don'n know。 Some expression that describes like。

Something that's really intense and good。 Nathanthanya' has just been smashing， getting。

 getting look 21 hours ago，21 hours ago，4 hours ago，4 hours ago。A day ago， I mean， you get the point。

Thenaniel's just been on top of this。 pretty much every single time I've gone to answer one of your questions。

 that Daniel's answered it for you already， so。😊，Big thank you。 big thank you'。

 big thank you to Nathanielll for that。 And yeah， if you do have questions about the spec。

 then just post here。Again， this is not us debugging your code。

 this is you clarifying stuff it's also a great spot if you have questions to kind of skim through this。

 maybe there'll be a little bit of help here in your understanding that you didn't realise you needed。

So yeah， that's where to go for that and。Yeah， I think that's about it。 Honestly， it's like。

I like this assignment because it's in some ways the easiest one to start because of assignment too。

Like you， you kind of get it， you know， you've got a class。 youve got functions。

 You just got to do it。 You can do the iterator later。

 you can finish this whole assignment without the iterator。 Oh， and just just in advance。

 someone's gonna ask this question at some point。 How many marks will I lose if I don't do the iterator。

I don't know。Like we don't really plan for that， but if you want a number。

 like if you iter it just flat out， doesn't work。Maybe。Maybe a quarter。

 maybe a quarter of these performance marks， I would guess。It depends on the tests we write。

 Like that's it。 like so you probably can't get about 15% of the assignment or overall marks if you don't do the iterator。

So， you know， I would say， you know， do that last or just don't stress about that。 There's so many。

 so many easy places to start with this。 Like you can just make a graph and then you can just add the node and remove the node and。

嗯。Yeah， it's just such an easy thing to start， erase it， printed out。 Con it and print it out。

 start with that。 go do those two things， fill in the rest of the gaps。

 You'll get enough confidence to do the iterator。 and you'll just， you know， spend the time on it。

 You'll be okay。 I faith in you all。Insert edge， insert node anyway， it's 759。 so let's stop here。

Thank you again for coming along and listing and all of that。U。

And if you have other stuff post on the forum， otherwise I'll see you all next week and I'll send you an update on Friday。

😊，Thanks for being such a bright， smart bunch of students。 And yeah， I guess that the last point。

 Nathans encouraged me to remind you not to get caught up on complexity。😊，When。When tutors mark this。

 we're not going to like be looking at complexity like really deeply like like we'll probably ask them to have a glance at it。

 but they're not going to be like analyzing in detail。

 So in a lot of ways this is mainly just a guideline for you all I'd say is like。😊。

You don't have to treat it like something terrible will happen if you don't do it。😡。

It's a general guideline。 And if you violate a lot of them， there's probably gonna be some penalty。

 but， but generally don't get too caught up on it。 Just focus on implementing it。 But yeah， anyway。

 have a great night， everyone。 and I'll see you next week， thanks。



![](img/79aab290c7ce7dc57087c8e777a085cf_5.png)
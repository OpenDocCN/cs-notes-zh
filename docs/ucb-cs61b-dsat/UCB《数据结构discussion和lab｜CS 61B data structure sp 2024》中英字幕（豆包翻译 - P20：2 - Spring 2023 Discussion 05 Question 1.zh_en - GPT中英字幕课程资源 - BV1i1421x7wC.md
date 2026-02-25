# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P20：2 - Spring 2023 Discussion 05 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明发明。🎼Ba。

![](img/579631cef9373e3650c18a2aaba760e7_1.png)

🎼And。All right， so for this discussion， I felt like it might be a little bit better for learning purposes if you were to see this done live because in regular discussion5 I wrote this question so that it takes up the entire time of the discussion It's just one question that has many different subparts that build on each other so I think it's like nice when you see it come together so that's why I'm going to be coding this live which I don't necessarily always like because IntelJ gives you a lot of hints when you're writing things so it's like a little harder to build intuition but I think it's still would be cool to see it all come together and then like we can run it at the end So anyways。

 question one for OHQ Mashaan is designing the new 62 to be author hours queue Fun fact this is actually true because this semester Masha and our wonderful wonderful infofra team or wrote 601 B its own Q because in the past we've used 60 and A's style。

Anyways， just a little tidbit for。So the code below for OH request represents a single request。

 it has a reference to the next request， oops。😊，Actually。

 I'll just click over here has a reference in the next request description and name contain the description of the bo and the name of the person on the queue and is set up as a boolean that marks the ticket as being a setup issue or not So you'll see over here that OH request takes in a description a name is set up and the next OH request So basically OH request is set up a lot like an int list right where there's like the head of。

😊，An int list and then the rest of the in list itself is an in list。

 so it's kind of like a link list that just keeps chaining with next， okay？Awesome， so now in part A。

 we're asked to create a class O H iterator that implements an iterator over OH requests and only returns requests with good descriptions using the is good function。

 Our O H iterators constructor takes in an O H request that represents the first O H request on the queue。

 If we run out of office hour request， we should throw a no such element exception when our iterator tries to get another request like so。

😊。

![](img/579631cef9373e3650c18a2aaba760e7_3.png)

Ooh， I don't like how a。well， I'm trying my best throw new no such element exception。 Okay。

 so the first thing that really pops out to me is that we're told that OH iterator should implement an iterator over OH requests All right。

 let's do that so we're going have public class OH iterator implements iterator。😊，Over OH requests。

Yeah， okay there we go， Im going like move my video a little bit so I can see。

And then I'm going to import Java U itator here。Cool， yeah。

 so we want to implement an iterator over OH request， awesome。Oh， now Java's kind of mad at me。

 In is getting mad at me until it give me these red squiggglelies。 I wonder what that's about。

 It says class O H iterator must either be declared abstract or implement abstract method has next in iterator。

 Oh， right， because any class that implements the iterator interface must also。😊。



![](img/579631cef9373e3650c18a2aaba760e7_5.png)

Fill out its has next and next methods， right， we need to override that and implement that in the class。

 So what I'm going to do here is I'm going to make this function up here。Public。Buleian。Oops。

Has next。And we also need to override the next function， right？So this is going to be public。

And then I'm going to question mark this because I want you to think about it before I give the answer away entirely。

😊，Next。Okay， cool， so remember that the next function should return the next element in our iterator right。

 the next element that we want to spit out of our iterator and that needs to correspond to whatever type the iterator is iterating over right and the iterator is iterating over a bunch of office hours request。

 which means that next should return。An OH request。Awesome， so now we have our blinks。

 we're ready to fill those in and the override tag is no longer yelling at us like you are not overriding what you would need to okay。

Cool so up over here in the constructor we're told that we take in Q it's an ohH request that represents the first office hours request on the queue and I think we'd like to hold on to this for when we're inside of our has next and our next functions so I'm going to set K equal to Q so we have access to our instance variable once we finished executing the constructor and we can refer to cur inside of has next and next Okay cool。

😊，I think Has next is a little more intuitive so let's start there the idea behind Has next is because we only want to look at tickets or requests with good descriptions we have to skip over we have to kind of prep our cu so that we skip over tickets that have bad descriptions right so that means that in this while loop we have to find some way to keep iterating through all the OH requests until we find one with a good description so what that's going to look like is。

😊，Well， cur is not equal to null， so I feel like the cur not equal to oops。

Her is not equal to know I feel like this is kind of customary at this point where it's like oh you want to make sure that you don't hit a nullport exception so you're going to stop iteration right before you hit the end。

 but the added part of this is that you want to make sure that you only that or that you skip over tickets with bad descriptions right so the other component to this condition is while current is not equal to know and。

Not is good cur dot description。So that's our loop condition and in the body of our loop we're gonna to say cur equals cur dot next so what this is going to do is we're going to start at the beginning of our Q and while we haven't reached the end of it and we haven't run into an office hours request that has a good description let's keep skipping over that first ticket on the queue so we set cur equal to be cur dot next so let' to illustrate this out let's say we have crystal Jety and Vidia on the Q let's say there are three OH requests in a row and let's say crystalrys has a bad description Jety has a bad description and VDA has a good description and then over here you don't need to worry about it too much right now but a good description is just that the length of the description is greater than equal to five characters。

What this。What this stuff while loop is going to do here is it's going take in crystal as cur right because we're going to pass in the first person on the queue to cur and we're going to look at Cryal's ticket and say while Cur is not equal to no so we haven't hit the end of the OH request queue yet and not is good cur description so here we're saying the current ticket is crystalal's ticket bad if it's bad then we want to advance cur to whatever the next ticket is and the next ticket in this case is jetty's ticket so once again we're gonna to look at this and say how we reach the end of the list yet no we have not yet so we look at this condition is jetty's description good no jetty's description is not good so we're gonna to skip over Jety's ticket and move on to Vthia's ticket and then when we get to VDI's ticket we know we haven't reached the end yet Cur is not equal to no but V's ticket is good so we would break out of this loop。

And Kew would now be pointing to V's ticket， okay？So now we have to do a bit of error not error handling per se。

 but we need to think about like an edge case。 let's say everyone's ticket was bad so we went from crystalsals ticket to Juty's ticket to Vs ticket and then when we came across video's ticket let's say videos description was bad and so that means we would be in this part of the wire loop and we'd say cur equals cur next Cur on next on videos ticket is null so wed set cur equal to nu and at that point we've gone through every possible ticket on the queue and we didn't find a good description So that means that if we made it all the way through the end of our queue and we didn't find a ticket that was acceptable then has next returns false right there's nothing left in the queue that we can iterate over that will give us a good request so that's kind of what I mean by E case handling here so we say if cur is equal to null。

So we went through the entire list without finding a good ticket， we're going to return false。

 and otherwise if K is not equal to null， then we did find a good ticket。

 so we're going to return true。Right？Cool， now next。Next is a little trickier。

 but I think a good guiding point， a good starting point might be this part over here if we run out of office hours request。

 we should throw a no such element exception when our iterator tries to get another request like so throw new no such element exception so basically what this is saying is if we try to call next on our iterator and there's nothing left in it like has next year' false。

 then we should throw that exception so why don't we put that into code。

We'll say if has next is false， like so if not has next。

We want to throw new no such element exception。很快。And then I think something got perplexed by students a little bit in section today was why are there three lines like why can't we just be like。

😊，诶。Whathy are the three lines like why can't we just be like return cur right because we established that cur over here when we go through has next Cur is going to be containing the next good description office hours request on our queue right why can't we just return cur we totally could however the issue is that let's say we only return cur here like we let's ignore these other lines for now。

 let's say rereturn cur going back to like the Crystal Juty vivid example。

 let's revert videos ticket so that she is a good ticket and Crytal and Juty both have bad tickets。😊。

So we're going to call hass next and then we're going to find out that the next good ticket that we want to spit out is VDdia's ticket okay。

 so Cur is pointing to Vdia so let's say we figure out has next and we find out oh yeahy Vdia's ticket is good and K is pointing to Vdia's ticket when we go in next to actually spit out that ticket we're going to return VDdia's ticket great awesome。

And then when we call has next though， this is going to ask us well cur is not equal to null and the description is bad。

 but we never advanced cur right so Cur is still pointing to VDdia's ticket and VdiaA's ticket is good so we're basically just going be stuck in this endless loop of has next being true and every time we call next it's VD's ticket but even though it shouldn't be VDA's ticket right we should be at null now there's no more elements to even go through in our iterator。

So keeping that in mind， we can get around this pretty simply by just saving the current office hours request。

 let's call this like。C request equals cur。And then we can return per request at the end。

And in between these two， we can advance what Cur is pointing to。

To ensure that when we next the next time we call has next。

 we're looking at a new ticket that we haven't already processed， all right。All right。

 that's it for OH iterator， okay？Oops， I just realized I forgot to scroll down on the PDF side of things I'll try to keep。

嗯。Pos your attention to that to make sure that we're all staying on the same page Okay。

 so next part B， define a class OHQ below we want OHQ to be iterable so that we can process OH request objects with good descriptions our constructor takes in the first OH request object on the queue。

All right， so in the first line we're told we want our OHQ to be iterable all right。

 that's a sign to me that we should have OHQ implements iterable。Over OH requests。

We know that it's going to be an iterable containing OH requests and once again IntelJ is giving me all these red squiggly lines is getting mad at me when we hover。

 we see OHQ must be declared abstract or implement abstract method iterator in iterable。😊，Oh yes。

 that's right Any class that implements the iterable interface must define and fill out the iterator method right so that's what's going to go in here。

😊，So。We're going to say public。And we know this is going to return an iterator over OH requests。

 right？And then this function is going to be called iterator。Okay， cool。嗯。

Let's think about how to fill this in in a little bit。

 let's go back to the constructor really quickly forgot I realized I forgot to do that。

 but basically over here we take in this OH request queue which represents the first office hours request on our queue and because we probably want to hold onto this this Q variable outside of the scope of our constructor。

 let's save it into our private variable。😊，This do Q， so we can do this do cube plus Q。😊。

Just to address this syntax over here with this keyword。

 I got a really fantastic question in discussion today。

 which was like a student asked me why do we need to use this keyword。

 why can't we just say something like。Why can't we say likeq equals Q？

So the issue with this is that it's not inherently clear to Java what we're doing and I think Java visualizer and intelligent do this differently。

 I'm not entirely sure， but the point is what we're doing in this line we don't specify this is that we are setting Q this local variable equal to I believe this Q over here。

 which is the private， this private instance variable Q inside of the OHQ class。

 so I believe that at the end of this constructor you call it's going to set this local variable Q to whatever this Q is which is null and that's kind of useless for the purposes of what we're trying to do here because we want to set the instance variable equal to this local variable Q that got passed in so we have access to it in other functions right which is why Q is this dot queue is necessary。

😊，However， if we were trying， if we called this like Q or something like that。

 we could just do Q equals Q the letter because there would be no ambiguity as to which variable're referring to is okay？

😊，Oh， it's strange our back。Okay， cool， and then revisiting the iterator function down here。

We know that this iterator function over our OHQ which is iterable should return an iterator over OH requests how do we do that well lucky for us in part A。

 we literally just implemented and and we literally just implemented OH iterator which is an iterator over office hours requests right so we can return a new instance of the OH iterator object and the OH iterator object takes in the first OH request on the queue。

So we can just pass in queue here。All right， so that's part B pretty short and then I'm really excited for you to see like the rest of the scenario all comes together。

😊，And very quickly， actually I think I'm going to do this out of order because I think part C is relatively disparate from the rest of the from the rest of the question and I mostly put Part C here for reasons of space so that when I was printing the worksheets。

 everything would fit nicely into four pages so don't worry we'll come back to part C but it's not directly relevant to this like overall iterator question or not super relevant to the overall iterator question。

😊，We'll come back al right， so in part D。😊，嗯。We move over here yeah in part D suppose we notice a bug in our office hour system and when I see suppose I mean like really use your imagination here because it doesn't like the current implementation that we have for OH iter and OHQ doesn't actually have this bug anyways but suppose we notice a bug in our office hour system if a ticket description contains the words thank you it is put on the queue twice to combat this we'd like to define a new iterator TY iterator so。

If the current items description contains the words thank you。

 it should skip the next item on the queue because we know the next item is an accidentally is an accidental duplicate from our buggy system so I'm going to keep reading this and then make a couple of corrections because I realized this was worded kind of strangely well as an example if they were four OH request objects on the queue with descriptions thank you thank you on board help me calls to next to return the zero second and third OH request objects on the queue remember we are still enforcing good descriptions on the queue as well。

😊，A quick correction to this line over here。So it should skip the so if a current item description contains the words thank you。

 it should actually skip the current item and move on to the next item because we know we'll have a duplicate。

 so this is just like a matter of like。😊，Implementation。

 but I think personally it's easier if we skip the current item and move on to the next item so we skip the first thank you and move on to the second thank you just in an implementation detail。

 but overall the functionality is going to be the same so based on that this should say first second and third oh request objects on the queue okay。



![](img/579631cef9373e3650c18a2aaba760e7_7.png)

And then click tip to check if a string contains the words thank you。

 you can use string dot contains thank you。And then overall as a hint we've already enforced good descriptions with our regular OH iterator。

 how can we use that we reuse that functionality without repeating ourselves also notice that OH iterator instance variables are private so we can't access them from subclasses of OH iterator Okay so I think this question is quite difficult。

😊，Because it's not very intuitive and it requires a lot of trust in like an inheritance to do its job kind of and a lot of trust in abstraction。

 basically。So the idea here is TI iterator is going to operate a lot like OH iterator。

 the one that we implemented in Part A right however。

 like we don't need to rewrite everything in OH from OH iterator and then add a teeny tiny tweak to it because that would be repeating ourselves which is not good in code right we want to we want to try to not repeat ourselves if we can help it when we're coding right just for cleanliness and just for abstraction purposes so the idea here is that instead of having TI iterator implement iterator over OH requests and then like reoverride all like the has next and the next it would be better if instead we inherited directly from OH iterator with extends right so remember that we can extend one class so here we're going to extend OH iterator。

Okay。😊，And basically， this is going to adopt all of the functionality from OH iterator before we make any other changes。

And also you'll notice that once again In is getting mad at me let's hover over this it's gonna to say there is no default constructor available in OH iterator okay so here we have to think he has to ask ourselves okay in the TI iterator when I'm creating a TRI iterator object for the first time doesn't need to be any different from my parent constructor right does it need to be any different from OH iteratorss constructor let's take a look at OH iterator quick like hack if you didn't know this already if you hover over something like a definition or a class name in In with your mouse and you hit command click on a map。

That's going to take you directly to where that class got implemented and you can see all of its details。

Anyways， so if we look at OH iterator we see it takes in an OH request that is the Q and it sets cur equal to Q it doesn't really seem to me that at this point in time we really need to do anything in our TY iterator other than set this so what we're going to do here is。

😊，Just call the superconor and we're going call the superconor with the super keyword so we can do something like super and pass in Q so basically what this is saying here is that hey Java in the TI iterator constructor when a Ti iterator object gets initialized I want you to call OH iterators constructor and pass in the queue so that's basically the equivalent of setting this equal to a new OH iterator Q except you can't reassign this in Java so I'm just like making this up for clarity purposes for you to see what the super line is doing over here。

So when I showed this to my students， a lot of them were like， wait a second。If T。

 Y iterator extends O H iterator， and O H iterator has this has this。Instance variable curve。

 Why can't I just do something like。Okay can I just do something like this dot curve equals Q。Oh。

 okay， oh so you'll notice that K has private access in OH iterators。 So basically。

 when TI iterator inherits or extends from OH iterator。

 it's not going to get a copy of the private variables I mean。

 technically speaking because TI iterator is an OH iterator， it will have。

It will have a curve variable right but it's just not accessible directly from TI iterator because it's private so we can't do this and the reason why I actually made that variable private in this iteration in this semester for discussion five is because last year when I taught this question I realized that since we didn't make it private students were doing something like this and basically basically they were basically copying over a lot of code from OH iterator which is not what we wanted we wanted them to abstract it away with the super keyword and trust that inheritance from OH iterator would do them right okay so basically that's kind of the the thought process behind this so cur has private access as an OH iterator and even though TI iterator is a kind of OH iterator it doesn't have direct access to cur unfortunately so we'll use super to do our bidding right so we have that。

And at this point in time， if we leave TI iterator as is in the constructor。

 it calls the superconstructor， so this means that TI iterator has the exact same functionality as OH iterator。

But that's not quite what we want right， We want to build on top of the existing functionality from OH iterator。

 We want to use OH iterator as like a starting point， right so。😡，We want to use OH iterator。

 whatever it spits out as the next valid ticket and we kind of want to vet that valid ticket even further and check whether or not it contains thank you right and the easiest way to do that。

Or at least how I wrote down the solution is by overriding OH iterators next function。 Okay。

 so this is where things get interesting because there's now like levels to how we're overriding the next function。

 right in OH iterator we overrote the interfaces next function。 And now it' UI iterator。

 we're overriding OH iterator's next function。 So we know that the next function is going to return and OH request and then it's next。

😊，Okay， cool so remember what we just talked about with like oh。

 we don't have access to cur right so we'll have to entirely rely on the superclass we'll have to entirely rely on what super can give us from the body or from the inside of TY iterator right so if we want to use OH iterator as a starting point and get whatever tickets OH iterator will spit out with it's already good descriptions right we want to vet this tickets further we can use OH iterator's next function to give us a ticket with a good description that we know for sure will come or we can to give us an OH request that we know for sure we'll have a good description because that's our like baseline that's like our starting point right so we can do something like this and this is gonna to look really weird but stay with me here。

 we can do something like super dot next okay and what this is saying here is that hey I'm calling these super classes next。

Method， I'm calling O iterators instance method called the next。

 and I know this by once again I'm going to use the command click and it's going to take me to the definition。

It's going to take me over here to ohH iteratorss next function so basically here inside of TY iterator we called OH iterators next function because we use super to refer to OH iterator all right so this is our starting point we know for sure that result is an OH request with a good description so now。

We want to check if result is not equal to null， right。

 because we know that super actually I think we made it so that。Next， can't return null here。

Maybe you can return no， I can't think about it right now。

 but the point is I want to double check that result is not I to know。But also。

 if the results description。Contains。Thank you。Then I want to skip over that ticket， right。

 because I know that。The bug made it so that tickets that had thank you in the description got put on the queue twice。

 so I know that if I skip over this one will be good and we don't have to worry about running into duplicates because we've already skipped over one of the duplicated tickets so we can say result equals super dot next。

Okay。And finally， we are going to return results。Oops。So just to summarize what we did here。

 we called Super dot next to give us a ticket with a good description and we double check that it's not null and also whether or not its description contains thank you if its description does contain thank you。

 then we are going to bump up result one more time to the next element in the that the iterator is going to spit out in order to get around the fact that we're going to have duplicates of the thank you tickets right so if we have two in a row。

 we ignore the first one and we bump onto the next one and that's the one that we're going to return and that's it for TI iterator。

All right。Okay， and then in part E， I think this is where everything comes together and it's really exciting。

So。In part E we're told to let me scroll out oops scroll out a little bit yeah we're told to change the OHQ so that it uses TY iterator and then fill in the blanks to print only the names of tickets from the queue beginning at S1 with good descriptions skipping over duplicate descriptions that contained thank you assume that we are not using the feature from part C that prioritizes setup tickets and I realize we because I skip part C for now we'll come back to it after we don't need to worry about that for now what won't be printed after we run the main method。

😊，Okay， so over here， in order to get rid of the duplication bug for thank you。

 we would use TY iterator。However， there's a couple of ways to get around this， but currently。

In part D we just made up the fact that there's this bug but there isn't actually a bug so if I run this if I after I fill out the main function and I run it it's gonna run into a nullpointer exception so for now I'm going make it an ohH iterator but I just wanted to get across the idea that like just because you define like one iterator for a particular iterable does not mean that you need to use that one specific iterator for that iterable forever right like we could switch around what kind of iterator what we want that we want to use like TI iterator is going to give us also an equally valid iterator basically okay but for the purpose of this question。

I'm going to change it back to OH reator so we don't run out of null pointer exceptions。

 but I will show at the end a way to deal with the null pointer exception because we have we have this like fake duplication bug anyways。

 just in a a very quick assign。Okay， so。We want to print the names of the tickets on the queue starting。

At S1 so we know from over here that S1 is an OH request and then the next field of S1 is S2 so S1s next is S2 S2 is next is S3 S3 is next is S4 S4 is next is S5 S5s next is null so it's kind of like once again it's like kind of like a linked list of OH requests right so the idea here now。

Is that we want to make an office hours queue， what's call this Q is。

Which takes in S1 as the first OH request on queue。Right， okay。

 and now this is the moment of truth because I think this is like the big gap that my students had trouble making and honestly that I also had trouble making when I was a student this idea of like I'm so used to using four loops to iterate through like lists and a arrays and sets that I forgot that it's applicable to anything that is iterable right I can do like a for loop through anything that is iterable so if I go to OHQ。

You'll realize that we had OHQ implements iterable over here， which means we can use like and。

I don't know， like maybe many drum roll because this was like a huge epiphany for me when I was seeing this for the first time。

 I was like。You can do something like4 OH request O colon Q。

This like this like small line of code like absolutely blew my mind because I was like。

 wait a second that doesn't like how， how does that even work， I don't really understand that。

 but then you remember。That we made OHQ iterable right a list is iterable and a arrayiterable a set is iterable and we're so used to iterating through all of those like really common data types that you kind of forget that oh as long as you make an object implement iterable you can use the syntax right because the syntax really is I think I went over this in content review it's really just shorthand for something like this for iterator OH request let's call this it or something like that。

😊，Let's call sit。Let me interpret that really quickly。And then。

It's effectively calling the iterated method of the iterable， which is Q in this case， right。

 and we want the continuing condition to be iter dot has next。

That's basically the equivalent of doing something like this。Hter dot next。

So what we have in line 18 is just shorthand for this four loop up here because it implicitly calls the iterator method。

 which I just find so cool on it。It like just like all made sense to me now when I saw this for the first time。

 anyways， yeah， so we can do this。And。We're concerned with like oh。

 we want to print only the names of tickets from the queue beginning at S1 with good descriptions skipping over duplicate descriptions that contain thank you so well if in OHQ we already replace our iterator function the one that gets called here to return a TI iterator then that takes care of everything for us right if we iterate through it this is going to implicitly call next on only and only give us tickets that have good descriptions and skip over duplicate descriptions with thank you so we can rest easy and literally just say。

😊，Dot out do print LN o dot name Okay so that means when this runs。

 it's going to start at S1 at the front of the queue and then iterate and print out all the names of the good tickets without getting duplicates so S1 is a good ticket because its description is more than five more than or equal to five characters so we're going to print Ashley and then when we move on from Ashley's ticket to Angels ticket Angel's description is a bit too short so we're going to skip over Angel's ticket and move on to S3 to Omar's ticket then to seller's ticket and then to Elena's ticket and so when we run this it's going to print everybody's name except Angels。

And it's going to take a little moment to build， but we'll see this very quickly。😊，Awesome， cool。

 yeah， and then。Just to go back and address the fact that I know I didn't。

I know I didn't change it to T light iterator。Because we didn't actually have like a duplicate bug on TI iterator。

 But let's say we did。We could do， we could change the iterator method of OHQ to return a TI iterator and then we could force its hand a little bit。

By duplicating Elena's ticket。Sorry， this is like very hacky and if you don't follow along it's like totally fine i'm just doing this for continuity purposes of making sure that。

We can see what happens in In J。Okay， yes， so let's say this was the actual queue where we actually did duplicate Elina's ticket。

When this runs， it's going to print out Ash Omarceella Elena without printing out Elena twice because we're going to skip over one of the duplicate tickets。

So slow。Okay， awesome。 Yeah， it printed Ash Omar Stella Elena， and there was no duplicate of Elena。

 yay， awesome。😊，So as promised， I'm going to go back to question C because it's quite disparate from the rest of the discussion。

I believe it's an OH request， yes， so an OH request。是。嗯。

Mshawn would like to find a way to prioritize setup tickets on the queue so that they appear at the top He wants to implement this based on the I setup field of each OH request。

Then sometimes students forget to set it to true， so he decides to use description as a backup field to break ties。

And we're told we want to fill in the compare method of OH request comparator。Firstly。

 if one but not both of the OH requests have there is set set to true。

 the one with is set up set to true should take priorities so it's early in the queue and if both or neither of the OH requests have there is set up set to true tie break with the description the description has to exactly match setup in order to be counted as a setup issue if both requests have such descriptions then it's a true tie and you just return zero。

Okay over here we have this public class OH request comparator。

 we know that it's going to implement comparator and I want to talk a little bit about the importance of parameterization in this context。

😊，You'll see that I have in comments comparator and there's these angle brackets that represent the parameterization。

If we just did something like OH press Comparator implements comparator。

Let me import that really quickly。😊，If we just do this， Java is going to be like， hey。

 you need to implement the compare method from comparator and I'll be like， okay。

 and I click implement methods。And it's going to give me a method that looks like this。

 It's called compareare it returns an int and it takes in two objects as input。

 like the literal Java object。 And while this is possible to work with。

 it's not an ideal situation because it's kind of like。😡。

I like I know this OH request compator is going to be a comparator over OH request specifically right。

 Like I don't want to have to deal with like this super general。

 this super generic object when I know that it's going to be。A comparator over OH requests。

 So if we parameterize the comparator like this。OH request。Java is now going to be like， hey。

 you need to implement compare。 but this time when it autofis it in for you。

 you'll notice that instead of it being object01 and object02。

 it's going to specifically be OH request01 and OH request O2 So that's really nice for us and a real upside of parameterization that helps be more specific and this is actually like a really interesting thing that you're going to come across in I believe project 1 C when you're implementing equals and this idea of parameterization and casting when you know the object for sure is going to be like a linkless deck or like an array deck this stuff like that Yeah anyways。

 just a very click aside you don't need to like。😊，Noe super about it in depth。

 just know that it's like really helpful when we parameterize our。A types， okay？

So I'm going to come down here and fill in。😊，The compare method。

So now that we've established that OH request comparator is going to be a comparator over OH request。

 we know that S1 can be an OH request and S2 is also an OH request right。

 we know that we're going to be comparing two objects of type OH request。

And just as a quick review over what these numbers mean。

 we return a negative number if S1 is less than S2 AkaA S1 takes priority over S2 and then we return a positive number if S1 is greater than S2 AkaA S2 has greater priority over S1 and then zero is like a tie between them it's like there is no one S2 S1 or S2 that takes priority over the other all right。

So。We know that what takes precedence first is going to be the is setup field of the each OH request so in this first part we're going to return negative one if S1 is less than S2 based on the is setup field so we can say something like if S1。

 setup is equal to true。And S2 dot set is set up is equal to false then we return negative one right because S1 is a setup ticket S2 is not so S1 takes priority it goes lower on the Q in terms of like how in the front it is right and you'll notice here that I explicitly use equal equal true and this is because I want us to really fully and truly recognize the difference between how we compare。

How we compare。Primitive versus reference type so is set up this lowercase boolean is a primitive type so we would use equal equal to compare primitives Okay。

 we cannot use dot equals to compare primitives job was going to make like a weird area like wait primitives don't have methods called dot equals Okay so in in theory you could simplify this to like。

If S1 dot is set up and not S2 dot is set up， but I wanted us to explicitly notice that we're going to use equal equal here。

 okay？So on the other hand， pretty similarly， we're going to return one if the opposite of true is true。

 So let's say S1 is not set up， so S1 dot set up equal's false and。

S2 dot is set up is equal to true in this case we're going to turn return one because S2 takes priority over S1。

And then if we get to this case， that means that either both of them are true or both of the both S1 and S2s is set up are true or both of them are false。

 in which case we need to break ties according to the description and we're told that we break ties based on whether or not the description exactly matches the word setup so I'm going to define some very quick。

😡，Variables， so let's call this S1 desk match description matches setup。

And then let's call this S2 desk notches setup。Okay cool so over here。

 if you remember that we're comparing strings now and strings are reference types in Java right so if we want to make sure that two strings are completely equal to each other because the reference types we're probably going to want to use dot equals and what that's going to look like is S1 description dot equals。

Set up。And S2 dot description dot equals setup up。Right you notice how we didn't do something like S1。

t description equal equals setup。Right because these are reference types so we want to use dot equals just to make extra sure okay。

 so what this's going to look like down here is something similar to what we did in the previous if else cases。

 so we'll say if S1 desk match is set up。And not S2 desk matches setup。

 we return negative one because S1 is going to take precedence。

 otherwise if S1 desk matches setup is false， so S1's description doesn't contain setup。

And S2 description contains setup， then we want to return one because S2 takes precedence over S1。

All right， that's basically the gist of OH request Comparator。

If you're still watching here is a very small caveat that I would like to add that I actually was not aware of when I was writing this question。

 but I decided to keep it in here anyway is that Java has something called a string pool so for string even those strings are reference types and Java for strings specifically sometimes you're able to use equal equal to compare the contents of two strings but I don't know the exact details of when this is always true but the point is to play it safe any reference type you see even if it's a string you'll want to use dot equals that's a very small caveat in case you do try to code this up on your by yourself and you do use like the equal equal for the string here it might actually return true but I don't know the total details of that but the point is。

When in doubt with reference types use dot equals all right， and that's the end of question one。


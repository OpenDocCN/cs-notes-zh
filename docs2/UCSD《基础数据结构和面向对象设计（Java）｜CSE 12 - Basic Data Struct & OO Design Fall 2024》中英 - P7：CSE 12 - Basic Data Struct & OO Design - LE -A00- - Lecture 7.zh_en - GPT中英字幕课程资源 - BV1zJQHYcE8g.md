# UCSD《基础数据结构和面向对象设计（Java）｜CSE 12 - Basic Data Struct & OO Design Fall 2024》中英 - P7：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 7.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

All right。Then we should get started in here。Morning。Our participation would start on Monday。 right。

 So today we're gonna see clickers， but。It's not required。So。嗯。I don't think we。

 did we release P2 already。I can't remember。嗯。So， but P2 will be released today。 Okay。

 so P2 is about reallist。 What I want to do today is I want to explain this exercise。

 We're gonna work on the exercise about reallist。 And also。

 I will talk about P 2 a little bit during the class whenever we have time， okay。嗯。So if you look at。

This。This exercise， this worksheet， we have the array list。 We have the array right。

 the back end of the array list is on。And then now this is the default constructor。

 So the default size is， is 5。But I think in the P， whatever the default capacity is。

 that's the starting size of the array。This size variable of the array just indicate how many things are being used。

 The underlying assumption is those spots that are being used。 we。

 we only use the spots from the beginning of the array， right， So if you use 3 out of 5。

 it means elements 0，1，2 are being used in the array。 that's the underlying assumption。 Okay。

 so there may be some unused things after after size， after size， okay。嗯。

Last time we talk about this append method。So for aend， if we assume that the。

DR still has enough things。 Then we just say if element is now， we don't depend anything otherwise。

 we should use size。As the location to insert this new element。

 because we want to put it at the very end for the C plus plus programmers。In here。

This append method is more like the pushback from C plus plus vectors。So it does the same thing。Okay。

 and don't forget to have size plus， plus， make sure that you update the size。As you can imagine。

When the array is totally full， that's when size is the same as the length of the array。

 When this is the case， you have to resize。In other words。

 you have to kind of relo relocate another bigger array。

 copypy in from the old array into that bigger array。 updatedate your size， updateate your。

The element you want to insert and also update what data is。

 So this resize function is a very costly function call。I think in this P A， we ask folks。

 whenever you resize， you double the size of the array。 That's what we're trying to do。

Are there any questions？All right。Did we do get， I remember in this section， I think we did get。

 Did we do get pass them together。Remember the 10 o'clock was literally behind this one。

 Did we do get last time we did， right， So get is， you just return whatever the element is。So。

 you're gonna return。Data。Index。嗯。If you don't consider any errors。

So this is a pretty straightforward function。 Any questions about these two。Deend and get。Yeah。嗯。

Second。Should we do any air tracking for， We should， We should in general。

 like if index is negative or bigger than this than the size， you should do air tracking。

You should do air checking。嗯。One other thing， Just be careful， I think。Don't forget to type cast。

 right， I think data is。Is the object array。 So don't forget to type class if you return E。

That's about it。Yeah。Right， data dot length is the capacity of the array size is how many things are being used。

Any questions for this。All right。Any other questions， I think our class is relatively small。

 I don't know。 People can't wake up anymore。 But if you have questions。

 we can entertain the questions you all have。One of the luxuries that use these smaller classes。

 You know， that's one of the luxuries， so。Since our class is smarter by， by chance this morning。

 So if you have any questions to ask。All right。哪页。If you have questions， feel free to just ask you。

 then we can take a pause and answer the question。How about this one。This is a very bad function。

 This is a very， very bad function。 Removemo first。Remove first。

I want to remove the first element of the array return。 I think I， I have removed。Can you。

Implement this one by yourself or work with a neighbor collaboratively to solve this one。

 If you're asked to remove the first element of the array。

Based on the analogy of students coming in to grab a chair， this is a very bad thing。Right。

 so can you do it yourself。有。Do I have to shift everything to the left。You have to。 You have to。

 because by default， we assume we only use from 0 to sides-1 elements in the area。

This thing would remove the zero thing。And， and also consider error checking。When I say you。

 you shouldn't remove the zero thing。Think about it。 Okay， so write this code Para。

I don't think we have any of the handouts anymore。 I think it was recycled。诶。

We should have some handouts in here。If any of you need a handout。It's here。If you are done。

 look at your neighbor。 I want you to include error checking。 if you can say。

If something is not good， then I shouldn't remove this zero element。This is the。If you are done。

 look at your neighbor's code and see what they got。I'm gonna open up the clicker。 if you are done。

 give me a vote。So。I know how many people are here。Same frequency， A。Same frequency as。All right。

What I want to do is first thing I want to cut out this zero element， right。So， this is my data。

And this is the thing I want to cut out and remove。嗯。When do I say you can't cut it out。If what is 0。

If it doesn't exist， if what， if。How do I know there's nothing in there。I the datata到栏 equal to 0。

Or should they be。Size， right， if size doesn't include 0。 If size is the same as 0， there's nothing。

You can return now or you can throw an exception， whatever the description ask you to do。 And say。

 okay， something is bad in here。嗯。Now I'm ready to remove。 How do I remove this thing。

I need to do a shift。I need to do a shift。 I would shift everything from the right。To the left。

 by one spot。RightThat's what I need to do。 So I'm gonna write a for loop with this work。Ie close to。

Size。Michael do have a lot box， okay。I'll figure out where the bugs are。I。B it than0。say。Data。i。

Eco是 data艾是吧？And then I will return。Data 0。Can you have a。

I have a quick discussion what is wrong with my code。 Like where， where， where， where are the bugs。

Or other box。Let's do a left shift。Allright， any where are the bugs。Where are the bugs。Yeah。

Did I plus one， so。In here， Okay， so we， we try to copy。The， the。

 the next one to the current location， Okay， anything else。Yeah。We didn't update size。

 so we should do a size minus minus after it。Good。Other things， yeah。Alright。

 so I I'm trying to make the copy of like a copy from here to here here to here。

 Is there gonna to be an issue。If fact。Try to left shift ray。

And I'm going from the back with this work。It won't。 It won't work。 right。

 Here's the because I've seen people trying it and your shifting doesn't work。 Just for example。

 if I'm I array as。7，23。I don't know 40。If I say， let's cut out this thing。嗯。

My array still have these14 things， about 23，40。 And the last one is just empty。

The last spot should be empty。 If I make the copy in here。This item would change to 40。

And then I copy it again。 This thing will change to 40。And if I copy again。

 this thing is changing the 40。 Right， So the idea is if you try to left shift。

 you have to go from the left to the right， not the other way around。 Just be careful。

Does that make sense。Why you should now do this。 So I， I would say。Now， I could 0。As less than。

Size plus plus I。Do I have issues with this。有。I want I plus one to be less than size because size is like the limit that I should not exceed。

Right， so。Because you have several indexes in here， right， You have I I plus  one。

 and you may say I plus whatever it is， the largest index that you use to index into the array should never exceed size。

 So the largest index out of I I plus 1 is I plus 1。 So you just make sure I plus 1。

It's less than size。And then， plus， plus I。And I do the copy， decrease size， return data 0。

Still problems。 What are the other problems。对啊。I need to save the first element before I return it。

 because it's gonna be overwritten。 So I'm gonna save it， I say。二。Reference equals to。Data 0。

And there a written reference。I still have bugs。有。Right， I have to type cost data 0 into a E。Right。

 because data is an object array。 So I have to type cut into E before I can do the assignment。

I think now we are。O诶喂 ok。Does does this make sense。I do have a concern， though。

And I want to ask you all。As you can see about， the zero element was overwritten。

 The zero element was overwritten after we shift。 And we said， okay， we remember it before。

We remember it before。 We this actually kind of remember it。Because hes already overwritten。

We remember this thing。And this thing is already overwritten。

Would this return actually give me the old value or the new value。Does that， does this。

Question makes sense。 Like， we remembered this thing we tried to remember before we overwrite it。

Would this actually。Give me like this 7 instead of the new value 40。Will this work？

If I remember this thing， return it。It will work。Or you won't。Can I。

 can I ask you all to give me a quick vote Will this work。 Actually， like。

 I remembered this thing because I need to return it。A， yes， B， no， A is， it's gonna work。 B is， no。

 it won't work。Can you， can you just。Show me how you feel about this。

 Would this remembered the old thing before。I return it would this work？We， we。

 we did the right thing。 Remember it before we override it。

And then we returned this thing that we just remembered， would this work。Look at this。 Look at this。

We， we have a tie。 We have a tie。 That was a concern that previous student have asked me。

 And I think it's a good question。Can you have a discussion with a neighbor。Would this work， did I。

 What did I remember， In other words， I remember some。 What did I remember。Can you have a discussion？

 What does this reference remember。Because I want to return it。What us reference， or remember。

Will this work？This would work。 This would work， right， Why， why this work。 Just remember。

 whenever we have generics， we are looking at array of references。 We have a array of references。

 So when you say， you have a 7，23，40， what it means is you have this thing，7 is an object。

20 is object。3 is an object。40 is an object。 And this array has a bunch of references。

 has a bunch of references。Right， and then we say reference equals to theta 0。

What does the reference point to， Does the reference point over there。Does reference1 over there。

If I say reference equals to datata 0， does it point to the element in array， location 0。No。

 it doesn't。 right， It doesn't referenceence points over here。 When you assign one reference。

 this is data 0。This data 0 is a reference。 It is pointing to this object。

 So reference is pointing over there。That's what happens。 And then we。

 we do the shifting to the left。What is gonna happen。You're gonna start to let these。

 So data 0 now will be point here。And that's what they are pointing to。And when you return reference。

 you are returning a reference to this 7， which used to be the zeroth。

 What zeroth element is pointing to。That's why it works。 That's why it works， okay。

I think there was a common confusion， and they would say。You remember there。

 but it is already overwritten When we assign data 0 to reference。

 we are letting them pointing to the same object。Reference is not pointing to data 0。

 Reference is pointing to the object。 data 0 was pointing to。So that's why it works。Are we good。

Alright， so that's。Remove。And this is a very bad。Decision， right。

 as you can see is it involves this very expensive loop。

For you to shift everything through the left side。嗯。Now， how about this two string？

 This two string doesn't work。I'm trying to convert this to a string。 And in Java。

 when you print out a release， it print out the data in the release in a very nice way。

And this one doesn't work。 Can you have a discussion。Where is the bug。Where are the bugs。

So what is this。So there are two bugs。 Well， hardly give you a hint fix this line。 I shouldn't。

Could in there。That's gonna。Make it too easy。 What's wrong with this lie， anyone。What's on this line。

Size -1 instead of length， -1， right， so。嗯。Should be。Size。-1。How about this name。

To return plus equals to。So what we are assuming is。Why do I even need this，9。

If the9 is bigger than 0。We add the last part。So the idea is we just don't want to have extra comma in the very end。

Right，We just want to have extra comma。 So this part would just avoid this extra comma。So I've。

 Ive say。This part。Should just be。Size。没有是吧。Does it make sense？You can come combine these two。

 you can combine these two。 Just check if I is the same as size -1。 You don't add that。Common。

 that's about it。Then just just one question， right， one quick question。

 so we can try to combine these two together。Which is better， I say a for loop， the same for loop。

I'll do this four。I equals 0 S less than size。Plus， plus， I。Ill say， return to return。Plus。

 equals to。The start data， I。If。I。Doesn't equal to size，-1。Will say， to return。Plus， equals to a。好吗？

Which approach is better。Are they are the same。I say， a is。Lafe is better。B is right， is better。

She is still the same。What would you say。Let let's do a quick vote on this one。

 which approach do things better。Or they are the same。 There is no difference。Sorry。So again。

 this part you want to call two string。Right， they are object。 If you try to con this to a string。

 it's gonna automatically cost two string on this one。So this one， you can。

 you can definitely do dot to string just to be safer。 But Java by default will call it。Sorry。

 I have close to vote prematurely。 Which one is， which which one is better。 or they are the same。

Or stop the vote。 If you look at it。I don't know。 Does this mean we disagree with each other quite a bit。

In fact， this one is better。 The one on the left side is better。Right。

 why is the one on the upside Pa。对。Right， so this one， only one condition is true。 right。

 when I is the same as size。 So if you put this if inside here。

 you are tracking it redundantly for many， many times， which you don't have to。Right。

 so that's why you can stop。A little bit beforehand and then append the last thing。 So it's faster。

 It's faster。 So just， just because they would produce the same result doesn't mean they are the same thing。

Okay， so technically， this one would probably。Be faster if size is very big。If size is small。

 no one cares。Right， any questions。So I would prefer the one on the left side。 This， this is better。

This is bad。Any questions。Alright， so I think we。And then we have the。Kind of the the main method。

 right， So you just do a bunch of function calls， aend a few things。 And then you can run the code。

 You can run the code。There shouldn't be any issue。

I want to use the remaining 20 minutes also to give you heads up on P2。

 I don't think our our T has released this thing because it looks like it's still private as of now。

 So for this P， you're gonna implement the first data structure， the first data structure。

 which is a rate。 So you're gonna write your own rate， And once you release this P A。

You should see a Piazza announcement and then keep eye on that Piazza announcement where if there's any update on typos in here。

 then you will update on that Piazza announcement， as well as in this Github rippo。So。

The out of 100 points，95 is about the implementation testing。5 point is about styles。

AndThat's what we have in here。嗯。You are given。2 files。So my list is an interface。

 My list is an interface that would describe the functions you should implement。

And then there is a public tester that we give to folks。

 You can use this to test your code a little bit， but you are supposed to write your own hidden test。

 In other words， your own customized test， that what you should do and implement this class。

 which should be a generic class。ok。And this， I think we know how to run it。

 right If you use V S code， you just click on the button。嗯。

Out of the like 95 points for implementation testing，20 points are for testing。

75 points for implementation。 Okay， again， please do not share your test with other people。

 Keep it to yourself。 Okay， you can teach them。 say maybe you can test to remove something if the array empty。

 That's fine。But do not sayy， this is how you query the array and then remove it。

 Just don't go into details。 The rule of thumb is。We encourage students to talk to each other。

 but you should think about if I tell my friend how to do this thing， can。

 can they implement their code very similar to mine。If that's the case， you shouldn't say that。

RightSo if you say I'm talking about a very high level thing， that's fine。

 Okay You use your own judgment， use your own judgment。So we give folks two files。

 This one is to the public tester。 and this is a hidden tester。 We should know it。

And what we have in here is we give folks the。How we can test your code。

This is how we implemented the degree scope tester。 So we tell you how your code will be tested。

 We give folks some public tests。 So， for example， the constructs。That built the array。

 So my objects insiateated with three different constructors should have the correct properties specified。

 if they are embedded through the correct exception。

 So this is kind of how or given tester test them and your tester that you should implement by yourself should number one。

 test embedded input for capacity argument。 now input for a arrayconor， or elementary array is valid。

 even now with the correct sites。 So those are the things that you should test。 In other words。

 write your own tester。 Okay， and then descriptions for all the other methods。

 And I I will explain what these methods will do。 So they are quite a few methods。

 We have to implement for the array。 Some of them are not standard。 like rotate。

 It just we throw it in。So just， so we can implement that， okay。So the implementation in here。

 please be very careful。 Do not import a real list。Do not import reals。 If you do that。

 you may get a zero。 just because you are not supposed to use the reallist。

 And sometimes if you use like intelligent J or V S code。

 they would say you you click on quick fix and they say， oh， here's the import。Just be very careful。

 I've seen students say。This thing is imported by the I D E automatically。 I didn't know it imported。

Please make sure you double check。 Okay， before you submit。 And in fact。

 when you upload your code to graycope， we check that for you， too。 You're gonna see a 0。

 if I have the wrong import。Okay， I， I don't think there is any excuse to say the I D imported。

 I didn't know because when you submit it on Gcope， Gco will also check it for you。

 So when you submit anything to Grcope， please wait a little bit to see the result。 Okay。

 do not just drag it in there。 and then you are done。 Don't do that， okay。So do not import the array。

And then for the array， there are only two instance variables。 First thing is this object array。

The second part is size。 You're gonna see some sort of warning because we do type cast。

Something like this。 This is unsafe in each child's mind。 so you can ignore these warnings。

 You can ignore these warnings。The second parameter is the size。 The second parameter is the size。

So just like what we did in the， in the exercise， let me show you the。Okay。So， my list。

So this is a description of the interface。So whatever we have listed in here。

 you are supposed to implement it。 Okay， so this one is called expand capacity。嗯。

So it's going to increase the capacity of the arrays， like ress。And I think in this one。

 if I remember it correctly， we decided to let folks double the size of the array。Okay。

So this one is supposed to increase the capacity and then copy it in。

So this is the required capacity。Go to the capacity。 What is the capacity of DNA。

Is it size or is it length。Lth， right， the capacity is the length is not to the sides。

This is to insert this element at this location。AndSo you insert a certain element at a certain location。

 Remember， it's gonna push things down the line for you。

 So don't forget to shift everything down the line。 Okay， do I insert first or shift first。

You have to。Shift， right， Reer that spot， Shi everything back。 and then you put something in，嗯。

Upend we， we， we did this。 So it's very similar。Prepen， this is a bad thing。

 right Prepen insert at the very beginning。 So this is a。The move is similar， like remove。0， right。

 So remove the first thing that's similar like this， cat。Set。Remove， given the index。

 you want to remove those things。This one will return the size of the array， rotate。

So rotate this by index number positions to， I think it should be。This to the left， to the right。

 Let me see， I think。Maybe Casey is still working on it。I remember， we changed it。Rotate。

It should be rotate。嗯。Right。So it means you have D R。

 You're gonna shift everything to the right by a certain amount， by a certain amount。

 we need to update the starter code。 The start code sets shift to the left。

That's why it's not released。 I think he's still working on it。 So this one。

 we're gonna rotate DRA to the right side。 So it's a circular rotation， circular rotation。

One thing you can definitely do is， if you say I want to rotate index number of times。It's just。

 if you can implement rotate once， you just run this called index number of times。That's it。

 So focus on rotating once and then call this rotate。Index times。So that's what you can do。

 You can do。 find， look for something in the array。

 So this is more like the contains method in the array list。嗯。What else insert aend， prepen。Rotate。

Find， okay， I think those are all the methods。That we ask folks to implement。As for the tester。

Let me go to the tester in here。嗯。Public tester。So we have given folks quite a few testers， right。

 So we created these examples。This is a list of size 1。 So we have a bunch of。Aray in here。

SoThe setup would create all these things。 and then individual testers。

 So you should run definitely your code against this tester。 It will test the basic stuff。

 but it doesn't mean at this moment that whatever you see on graycope。

 when you are upload to graycope， if you get 100%。 or if you pass everything。

 everything is green in there， it doesn't mean you're gonna get 00%。There， there are hidden tests。

 There are hidden tests。 and those hidden tests are the things that we just described in here。

In the right up， we say how we gonna test our students code hidden test。 That's what we do。 Okay。

 so if you say， I implement these things， I pass off them。Then you should be good。

Then you should be good。Any questions about P。2。In questionsions， yes。Yeah。

 so I think our Ps are due on Thursday。 So we release it and then Thursday night。

And that's a deal time。Let see， what else I want to discuss in here。Constructors。So coding styles， O。

 coding styles。 So we have a style guide。Okay， so。There are certain things that you should。

 you should know。 you should your file should have all these things。 Okay。

 so file header that describe what this file does。 And then class header describe what this class has individual method should have their own headers to describe what this method requires what this method returns。

 inline comments should be few。 In other words， you have to comment for every line。

 you comment for the important part of your code。 that's for the in line comments， indentation。

 I think V S code can do this for you。 That's not the issue。

 make sure you use descriptive variable names， Descriptive variable names。

 for loop counters I J K are fine， but for other things。

 make sure you use descriptive file names sorry， variable names， No magic numbers， please。

 the magic numbers， anything that is not one0 negative one。 They magic numbers。

 So in your implementation。If you need to use any constants， define them as final variabless。

But in the tester， you can use magic numbers。 That's totally fine。 Okay， in testers， you can do it。

 make sure you have reasonably short methods。 I don't think any of the methods。

 West suppose implement is gonna be very long， but you can definitely create hoper method。

 Please be careful， you should only create private ho methods。 If any。

 I want to create a hoper method， make sure it's private。 because if you create any public。

Hopper method， our prototype check would find out that your signature of the class is different from what we are required to do。

And that's gonna be a prototype error。 That means automatic0。

 So please do not create public help method。 Private help methods are encouraged。O。

So use Java do comments。 so there is a full style guide in there。 read it once。 You're， you're good。

 I do see like a lot of our students put in comments like once I finish everything that will put in the comments。

 That's fine。 That's fine。 Personal， I would prefer to put in comments before I even get started。

 the the file header for the class， the method header that help me to understand what am I supposed to do in here。

 If you can write out what this method is supposed to do。

 is can help you to formulate how you want to do it。So I want to comment it out in the beginning。

 And one problem with commenting in the last minute is every quarter for every assignment。

 always have one too soon say， Bob， I submitted 1150 on the due date。 My code worked fine。

 and my commenting， I forgot a asterisk。I forgot to close my comments。 No。

 my code doesn't come I get 0。 What's gonna happen， You're gonna get 0。Okay， so please， that。

 that's a very sad event， right， So I don't want to say you get to0。

 but I I this the only option I have。 So please do not just say I will comment in the last minute and upload it。

And you， if your code doesn't come out， that's a 0。 So please comment as early as possible， right。

 And when you submit me something， don't wait until the last minute。That's all。

I think that's everything I want to talk about P 2。 Okay， I don't。

 I don't foresee people having a lot of issues with P 2。The last part， tester。When you have a tester。

 please make sure in your tester， you test for everything。 not just like， for example。

 let me get something。From the array， you should verify， is the size still good。

 Is the array still the same as before， Are there any changes on the array。

 So you should test on that， Don't forget those things， because if you forget。

 your tester would fail certain tests on Grcope。All right， so if there are no other。

Things folks want ask。 We are done today。 Okay， if you have questions， I'll be happy to answer them。

Enjoy your weekend。 Enjoyy your weekend。Yeah， it's a good question。You should。

 because style is auto graded。So。Starting from P to P1， I think when we try to grade P1。

I think it's also auto graded for P1。 Let me talk to the T A。 You should be able to get right， right。

 You should be able to get something back， yeah。Yeah， sir。AC c。Yeah。

So you should press and hold the button。If you see， I think mark means is connected to the base。

P one。Yes。ピーチィの。But it's not like because， we have hidden tests。



![](img/d124e2c49ba689e252e7005ca918ef87_1.png)

![](img/d124e2c49ba689e252e7005ca918ef87_2.png)
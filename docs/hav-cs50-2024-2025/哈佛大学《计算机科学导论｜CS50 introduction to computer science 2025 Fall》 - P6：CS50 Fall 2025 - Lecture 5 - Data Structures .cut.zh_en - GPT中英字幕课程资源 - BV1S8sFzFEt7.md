# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P6：CS50 Fall 2025 - Lecture 5 - Data Structures .cut.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

All right， this is C S 50 and this is week 5 already wherein we will focus today on data structures。

 which is a topic we've touched on a little bit in simple form。

 but today we'll dive all the more deeply and for better or for worse。

 this is our last week on C next week， of course， we transition to Python。

 which is a so called higher levell programming language， which is really frankly。

 just going make our lives a lot easier， we're gonna to be able to solve a lot of the same problems。

 but so much more quickly as humans， but not necessarily as we'll see as fast when we run the code as the computer might have if we were still using a lower level language like C。

 So indeed thematic over this week and next is going to be the theme we've seen before of tradeoffs。

 but before we get there， why don't we focus on a couple of data structures that you might encounter in the real world namely stacks and Qes。

 let's learn some facts about both of these if we could dim the lights dramatically。

🎼Once upon a time， there was a guy named Jack。 when it came to making friends。

 Jack did not have the knack。 So Jack went to talk to the most popular guy he knew he went up the Lou and asked。

Sorry， can we rewind。 I didn't hit the right button。

Suff is happening on the screen that you are not seeing。All right。

 maybe let's bring the lights back up。But first， let's learn the facts about cues and stacks。😡。

🎼Once upon a time there was a guy named Jack。 when it came to making friends。

 Jack did not have the knack。 So Jack went to talk to the most popular guy he knew he went up to Lou and asked。

 what do I do， Lou saw that his friend was really distressed。 Well， Lou began。

 Just look how you're dressed。 Don't you have any clothes with a different look。 Yes， said Jack。

 I sure do， come to my house and I'll showed them to you。 So they went off the Jacks。

 and Jack showed Lou the box where he kept all his shirts and his pants at his socks。 Lou said。

 I see you of all your clothes in a pile。 Why don't you wear some others once in a while。 Jack said。

 well， what I remove clothes and socks。 I washed them and put them away in the box。

 Then comes the next morning and up I hop。 I go to the box and get my clothes off the top。

 Lou quickly realized the problem with Jack， He kept clothes， Cds and books in a stack。

 When he reached for something to read or to wear， He chose the top book or underwear。

 Then when he was done， He would put it right。😊。

![](img/a13647f57b55a63e0e45544ba0bcb12b_1.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_2.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_3.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_4.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_5.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_6.png)

🎼Back back it would go on top of the stack。 I know a solution， said a triumphant Lou。

 You need to learn to start using a cue。 Lou took Jack's clothes and hung them in a closet。

 And when he had emptied the box。 He just asked it。 Then he said now， Jack， at the end of the day。

 put your clothes in a left when you put them away。 Then to morrow morning when you see the sunshine。

 Get you clothes from the right from the end of the line。 Don't you see， said Lou。

 it will be so nice。 You'll wear everything once before you wear something twice。

 And with everything in cus in his closet and shelf， Jack started to feel quite sure of himself。 Oh。

 thanks to Lou and his wonderful cue。😊。

![](img/a13647f57b55a63e0e45544ba0bcb12b_8.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_9.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_10.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_11.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_12.png)

![](img/a13647f57b55a63e0e45544ba0bcb12b_13.png)

Al right， our thanks to Professor Shannon Devval at Elon University who kindly put together that animation。

 and it's meant to paint a picture of a couple of things that we've all encountered in the real world。

 but more technically what we just saw were what are known as abstract data types。

 whereby their data structures in some sense。 but it's really about the design thereof what characteristics or features or functionality。

 these structures offer irrespective of how they are implemented in terms of lower level implementation details。

 which is to say you can implement， as we'll see queuees and stacks in any number of ways which are're gonna have real worldd implications for how you can actually use them in what kinds of problems you can solved with them。

 So let's consider， for instance， cues in the first place。

 So a queue is something youve sort of experienced all the time。

 anytime you go to a store go to some event for which you have to line up in a socalled queue。

 you'd ideally like there to be some fairness property about that queue such that if you got in line first。

 you get into the store first， you get to check out first or some other such goal。 Meanwhile。

 the person who got their last actually is that the end of the line and stays at the end of the line and therefore get served or enters。

In at the end。 So Qes have what a computer scientist would say is a fiIFO property first in first out。

 that is if you're the first person in line， you're the first person to get out of line and for many problems。

 that is a good solution。 certainly if you're concerned with fairness。

 but more technically a Q has what we'll call two operations N Q。

 which is a fancy way of saying getting in line and Dq。

 a fancy way of saying getting out of the line from the front of it。

 but those two operations if you think about it in code。

 could it be implemented with different actual details And by that。

 I mean this here is one way that we could go about implementing in C code a queue for a bunch of people or persons who want to line up for something So for instance。

 well decree that this queue can hold no more than 50 people like that's the physical capacity And then we define a structure which we've done a couple of times in the past whereby this structure has not only an array of persons that we call people and that will be as big as is the capacity So this is an array of size 50 for50 such person。

And then we're going to propose that we also keep track in this implementation of a queue of the current size of the Q。

 So we're going to make a distinction between the capacity。

 like how many total people can be there and the size。

 like actually how many people are in line at that moment in time so that you know which of the spots in the array are effectively empty and we're going to call that whole structure a queue。

 Now the catch with this particular implementation in code of a queue。😡。

Is what there is inherent in it， a limitation， something you just kind to deal with。

 And I see you nodding， what's your instinct for this。Okay， well。

 I think you hit the nail in the head in that it's only for 50 students or 50 people。

 which means if a 51st person wants to get into line。

 you literally have no means of remembering them in this data structure。

 So how do you solve that Well， we could just recompile our code after changing the 50 to like 51 or maybe 500 or 5000。

 But there there's this tradeoff because you could still be undershooting the total number of people trying to get into maybe a big concert in the case of an extreme。

 But at the same time， if you over allocate memory using 5000 locations in memory。

 What if only a few people show up now you're just wasting memory And certainly at the end of the day。

 you only have a finite amount of memory in the computer。

 So you kind of have to decide a priori like before compiling your code。

 how big is this structure going to be， how much space you're going waste in the end。

 it's all sort of stupid， it would be ideal if instead we could just grow the queue as needed and shrink it essentially asking the operating system is we started doing last week for more memory and then giving it back if we don't actually need that memory。

 which is to say can't really do。Aray in this static sense and by static， I mean。

 we're literally deciding in advance a compilation time how big this thing is going to be。

 As an aside， this is also a bit annoying for implementing a cu because you have to somehow keep track of who is at the head of the queue the front of the queue because as you start plucking people off you need to remember who's the next person effectively But there are ways and code that we could solve this。

 So let's consider an alternative to a queue， which gives us very different properties namely a stack。

 and we saw that in the animation whereby Jack used a stack to put his clothes into a box so that every time he got dressed。

 he sort of took the sweater from the top from the top from the top and might never wear anything other than black as a result。

 if he does a wash before he actually reaches the blue in the red sweater there。

 So a stack as we've just seen， has a lifefo property to it last in first out。

 So if I do a load of laundry and I plop some more sweaters on this stack while I'm presumably going to use the last sweater that went in first as opposed to trying to create a mess and pull the bottommost sweater out。

 which is just going be。Little more effort than than it would be otherwise from just taking it from the top。

 So sometimes last and first out doesn't give you maybe this fairness property you might want for other problems。

 but it does give you inefficiency， a convenience， certainly， So maybe that might be compelling。

 And stacks are actually everywhere too if you've checked your Gmail recently。

 odds are you've opened up Gmail co or outlook co and you've looked at your inbox。

 And where does the new mail by default end up at the top at the top at the top。

 And I dare say all of us are guilty of sort of neglecting emails that fall below the breaker onto the next page and sort of focusing only on the last in and therefore replying to it first out。

 which isn't great maybe for the senders of those emails。

 But it's just how those user interfaces are implemented quite often unless you override those default settings。

 So how might we implement a stack。 Well， we need to implement more technically to fundamental operations。

 The analogs of Nq and DQ in the world of stacks are called push which means push something onto the top of the stack and pop。

 which means remove something from the top of the stack also。

And the team in the cafeterias and dining halls on campus do this all day long。

 any of the cafeterias or dining halls that have stacks of trays。

 of course you put the first tray at the bottom and then the next tray and the next tray in the next tray in which tray do all of you pick up well presumably the one on the very top because it's even harder to grab the bottommost tray than it would be for something like a sweater as a result there's maybe undesirable properties maybe no one ever gets to the nasty tray at the very bottom of the stack because we're constantly rep punishishing the top ones but thanks to gravity like that just happens to be the most appropriate data structure in the real world for distributing things like trays in a cafeteria So how might we implement that idea and code Well funny enough。

 we can pretty much use the exact same structure we could just rename queue to stack because at the end of the day we need to keep track of some number of people and maybe peoples a weird sort of analog log here but we kept everything else the same so why not that but the size is also something we still need to remember and it turns out it's a little easier to implement a stack in this way because you could always remove it from the end of the array。

Aray and the first thing that went into the stack。 the first in can always stay at location 0。

 for instance。 But ultimately， we could implement it in this way。

 but we have the same darn limitation。 You can still only put 50 sweaters，50 trays。

50 people into that stack data structure。 So this is just one implementation approach。

 But that doesn't mean that's necessarily a limitation of stacks and cues theyre abstract in the sense that we could do better。

 we could maybe start to manage our own memory move away from statically defining the total size of this array and just start allocating and delocating that is growing and shrinking the data structure instead。

 which is to say we can make these abstract data types much less abstract with actual implementations。

 So let's consider the first of the data structures Actually。

 let's consider a data structure that we saw an abstract data type that we saw early on that we didn't necessarily give this name。

 a dictionaries is yet another abstract data type that's sort of everywhere in the world。

 literally in the world of dictionaries containing words and their definitions。

You can think of a dictionary really in the abstract if you were to draw this on the chalkboard as really just a two columnn table whereby on the left is the word and on the right is the definition。

 if it's a physical book， it's essentially the same thing with lots of columns of words on the left often bolt-face and then the definitions right next to them you can also see this in the context of like a phone book which is where we began the course in week zero where it's essentially a dictionary of names and numbers instead of words and definitions and a computer scientist would generalize the notion of a dictionary further and just call the thing on the left a key and the thing on the right of value and these things are omnipresent in computing and you're going to start to see them all the more today and next week and beyond in that if you just want to associate some piece of data with another piece of data a so-called key value pair a dictionary is going be your go to data type but even these two we can implement in different ways for reasons that we've already seen maybe there's only a finite size to this dictionary if we're using an array。

 maybe we can do better than that。Maybe a dictionary if implemented one way is going to be fast。

 maybe if' implemented another way is going be slow。

 So we'll consider these other design possibilities today， too。

 in the context of phone books and other data structures as well。 After all。

 if you have an iPhone or an Android phone my Apple or Google only decided that you can have 50 friends because they implemented the contacts app in an array。

 I mean， that would be an annoying limitations So presumably they've done things a little more dynamically as we'll do today。

 So let's focus on the first of the data structures we saw back in week2。 That is an array。

 which recall was just a chunk of memory where you can store values in it back to back to back。

 And that was the fundamental definition， the values are back to back to back or contiguous in memory。

 And as we've seen， we generally have to decide in advance the size of an array。 So for instance。

 if we want to store three values like one2 and3， it might look pictorially like this。 or in code。

 let's go ahead and implement this same idea and take a moment to whip up our very first program here。

 and we'll call it say list do C。

![](img/a13647f57b55a63e0e45544ba0bcb12b_15.png)

This program， let's just do something demonstrative of how you could use arrays to store three things in memory。

 It's quite simply the numbers 1，2，3， but you can imagine it being three people's names。

 three sweaters， three people or any other piece of data as well。

 So I'm gonna go ahead and at the top of list dot C include standard I O dot H。

 I'm gonna then do int main void。 So no command line arguments。

 Then I'm going go ahead and give myself an array of integers of size 3 called list。

 And that's how we've done that from week2 onward。 Then just for the sake of discussion。

 I'm gonna to hard code some representative value。 So the first value will be at location 0 because as or 0 index。

 Then I'm going do the second value， which will be 2。 And then the third value。

 which will be at location 2， but the value will be3。

 Now just to prove that we've stored this correctly in memory。

 let's just do a quick4 loop for int I equals equals0。 I is less than3 I plus plus。

And then inside of this for loop， I'm just gonna do a quick printf of percent I backslash n printing out the value of list at location I。

 So it's not a useful program per se， but it gives us an array to play with。

 It prints out that what's in it。 So we hopefully we will see 1，2 and 3 on the screen。

 So let me make this list program。😊，Dot slash list enter and voilla。 We're on our way going。

 All right， But what if now we actually want to change that design and be like， oh shoot。

 I now have a fourth number that I want to store or just bought a fourth sweater or a fourth person wants to get in line or I wanted add a fourth friend to my context。

 whatever the scenario might be。 it stands for reason that ideally you would plop that fourth value right here in memory so that everything remains contiguous。

 You're still using an array， your code doesn't really have to change except for the length。

 for all intents and purposes， It's the same implementation using just a bit more memory。

 But recall that when you declare an array of a fixed size。

 you only are getting promised that chunk of memory。

 not necessarily more memory to the right to the left above or below conceptually because recall in the context of your whole computer you've got this canvas of memory。

 all of which represent here bytes and there could be a whole bunch of actual values or garbage values in memory。

 So in a more complicated program that one，2，3， sure might end up here。 but if I also create。

A string in this program H E L comm world might have also ended up right next to it in memory。

 which means I can't just plop the for here because then if I'm still using that string elsewhere in my program。

 now it's gonna say Lo world instead of hello world because you're just claiming the H that byte as your own which does not in fact。

 belong to your array。 Of course looks like there's plenty of other memory I could use here because these garbage values represented by Oscar are not being used。

 they've been used in the past but we treat garbage values as memory we could reused certainly So wouldn't it be nice to maybe just plop the1。

2，3 and4 in this chunk of memory over here。 and I can totally do that。

 but of course if I want to do that， I got a copy the first three values over and then put the fourth one there and then presumably give back to the operating system。

 the memory I no longer need So that in fact， when using arrays is a perfectly valid solution。

 And I think we can go ahead and do this in our same program。 So let me go back to VS code here。

 and instead，Of statically allocating memory for this array and by static， I mean。

 literally hard hard codingd the number three here in a way that is permanent effectively。

 Let me go ahead and do this instead at the top of my code。

 let me delete the static allocation of that array before。

 And now let me leverage my understanding if still preliminary of pointers and memory management from this past week 4 to just dynamically allocate a guess at how much memory I need initially。

 So I'm going to go ahead and use malloc and allocate space for three integers。

 But integers take up a few bytes and it's usually is4。

 but just for good measure I'm gonna say times whatever the size of an int is is the total number of bytes I want。

 So presumably it's gonna to be three times 4 equals 12。 but I'm generalizing it。

 But then recall that malloc returns the address of that chunk of memory。

 The address is the first byte。 So if I want to create an array effectively called list。

 I can't just do。List like this yet。 But what I could say is that all right now。

 my list variable is actually going to be the address of an anteger and set malloc's return value equal to that。

 So in code here， what I've done is I'm asking on the right hand side。 the operating system。

 Please give me 12 contiguous bytes in memory。 All of those bytes， of course。

 can be numerically address like Ox 1，2，3，1，2，4，1，2，5。've had that story before。 Maloc。

 by definition returns the address of the first such bytes。

 and it's on me to remember that I allocated 12， if need be。

 So I'm just storing the address of that first byte in a pointer called list。

 So recall from last week， there's this functional equivalentence we saw between treating a pointer as an array and sometimes even treating an array like a pointer。

 the C language sort of lets us do this this conversion， if you will。 So what I could do here now。

 is quite the same syntax as before。 I could say。List bracket0， gets one， list bracket1 gets2。

 list bracket2 gets three， and even though I have this fancy new line inspired by week four。

 the syntax thereafter can be exactly the same。😡，Why we'll recall that these three lines here using square bracket notation is just syntactic sugar for the stuff we learned last week。

 specifically I could instead of doing list bracket 0。

 I could much more arcanely say go to that address in list and put the number one there。

 please I can say go to the address list plus one and put the value2 there。

 I could then say finally go to the address at list plus2 and put the number three there。

 but this looks ridiculous and even sort of an experience programmer might not be inclined to do this if with using fewer keystrokes and more readable code they could just do instead what I did the first time around。

 which is functionally the same and just treat that chunk of memory as though it's an array and the computer will essentially do the requisite pointer arithmetic to figure out where to put one2 and three。

 So even though this is still kind of fresh hot off the press form last week。

 it's exactly the same as we tinkered with last。We。So suppose now that some time passes。

 and I realize for the sake of the story that oh shoot， I need more than three integers。

 I need space for four。 so as to achieve this picture in memory。 Well， I could of course。

 just like delete all that code， change the three to a4， redo the whole thing， recompile the code。

 rerun it。 But let me propose that we write our code in a way that allows us to change our mind while the program is running how much memory we actually need。

 in case in point， if you meet someone new， you want to add them to your phone。 Well。

 you obviously don't want to have to wait for Apple to recompile the contacts app。

 reboot your phone just to add one more person， you want the program just to ask the operating system for more memory for that new person。

 So in this case， let's just pretend that some time passes。

 And now I want to go ahead and actually change my mind and instead allocate space for four integers instead。

 Well I could do something like this。 I could just say literally list equals malloc of four times size of int。

Semi colonlon， I don't need to redeccl list on line 13 because it already exists from line 5。

 but this is bad。Because what have I done wrong here in line 13。I've made a poor decision， yeah。

 in front。Yeah， I'm wasting all of the memory I had from line 5 because I'm essentially forgetting where it is。

 If the list pointer is literally a pointer， like a foam finger pointing somewhere in memory。

 what I'm really doing is saying point it over here now。

 But I've completely lost track of those other three integers in memory。

 And that's what we described last week as a memory leak。 which you could find with Valgri。

 And if you didn't find it or fix it in code eventually the computer in the program would slow down over time。

 So this is probably bad。 It's not good to just unilaterally change your mind and say no no no。

 forget about that memory， give me a new chunk of memory。

 especially if you want to copy the old memory into the new。

 just like I did a bit ago when trying to get the 1。

23 into the bigger chunk of memory that can fit 1，2，3，4。 So how might I do this。 Well。

 a temporary variable is of our go to solution anytime we need to remember something in addition to something we already have in mind。

 So let me just give myself a temporary variable called TM by convention for short and set the return value of this mala call to that。

 And then what I could。Do is something like this。 Much like my print statement earlier。

 I could do another four loop and say4 int I equals 0。 I is less than 3 I plus plus。

 And then in this four loop， I could say treat that new chunk of memory as an array like we can set the Ih location equal to the Ih location in list。

 So these lines here。😊，Copy old list into new list。 It copies those first three values。

 And that what I bet I could do at the bottom here is then just manually。

 I can say go to the fourth location， which when you0 index is technically bracket 3 and set that equal to the number4。

 So these lines here， copypy the one， the two and the three using a loop and then line 20 here at the moment。

 just adds the fourth value。 And again， this is a stupid sort of way to write code and that if you want to put the4 there。

 you should have just done it earlier， I'm just pretending that some time has't indeed passed in the program。

 And I've changed my mind along the way。 And I want to let the user add some value to memory。Okay。

 but before we proceed further， I dare say that there are some。😡，Other mistakes we should clean up。

 One of the lessons I preached last week was that anytime you use malloc。

 what should you do or check for？😡，You should always we， You should always free。

 So here I'm clearly not freeing any memory。 So I should definitely do that。

 And there was one other rule of thumb with memory。 What should you always do。When using mal like。

 yeah。Check to see if null came back， which just means something is wrong。

 Like it's out of memory or something else went wrong。 And if you don't do that。

 your program may very well crash with one of those segmentation faults that we saw briefly in the past。

 So it makes the code a lot more bloated， but it is good practice。

 So let's just check if the list pointer I get back contains null。 There's no point continuing on。

 let's just go ahead and immediately return one because something has indeed gone wrong。

 And then down here under malloc again， let's do the same。

 If the temporary pointer also contains null now， let's go ahead and similarly return one or any other non-zero value。

 But here's the subtlety and let me combine your two ideas。

 If I immediately return one on line 20 after the second malloc call fails。😡。

What should I still go back and do first？Yeah， you want to elaborate on your first instinct？Yeah。

 I want to still free the first chunk of memory because if we execute line 5 and all is well。

 which means that line 6，7，8 and 9 don't apply。 like it's not， in fact null。

 we got back a legitimate value。 That means we have a chunk of memory given to us for three integers which means it still exists down here at line 19 and 20 So if I'm ready now to abort this program and return one to signify error。

 I first want to free that original list and say to the operating system， here's your memory back。

 Now， as an aside， strictly speaking this is not necessary because the moment the program itself quits the computer is just gonna give back the memory to the operating system。

 So when programs quit the memory leak sort of go away。

 but your code is still buggy and generally we're running software that doesn't run for a split second。

 but for minutes， hours， days continually in which case it's best practice to squash these memory related bugs now。

 check for null free any memory so that you never indeed encounter these kinds of leaks。

 Allright so let's forge ahead a little bit more。😊，Let me propose that after we have done the copy。

 we now want to similarly free the original list。 However。

 what I think we're going to want to do first is after freeing the original list is remember that the new list is effectively。

That which we allocated the second time around。 So even though this program' is getting a little long。

 notice that what I've just done is I've said， okay， store in the list variable。

 the address of this new chunk of memory so that list now with a foam finger is effectively pointing here instead of up here。

 But before that， I made sure to free what my finger was pointing at。Originally， the list pointer。

Alright， lastly， let's just scroll down to the bottom of the code here。

 I can manually change the three to a4 just to demonstrate that I've stored all four values in here。

 And then at the very end of the program， I think I have to free the list again because now the list is pointing all out the foam finger to the bigger chunk of memory。

 the 1，2，3，4。 And then I can go ahead and return 0 at the very end。

 because all is hopefully well at this point。 Let me go ahead and open my terminal window again and make this version of list。

 I made a lot of mistakes here。 It seems。 Let's scroll up to the very first。😊。

Call to undeclared library function， malloc， dot， dot， dot。What have I apparently done wrong？

Or forgotten。What if I done't wrong back？Yeahep。Yeah。

 so in standardlib dot h is where malloc is actually declared。 So let's just add that quickly。

 let's go ahead and include standard Lib dot H。 in addition to standard Io dot H。

 let me clear my terminal window， rerun， make list enter Now we're good dot list and few we see 1，2。

3，4。 Okay so at this point in the story， all we've done is write a dopey little program that allocates memory for three integers。

12 and3， then changes our mind and allocates more memory for four integers。

 freeing the original chunk of memory after copying the first three integers into the new memory and adding that fourth value。

 But this is kind of a lot of hoops to jump through and let me propose one refinement here。

 So if back in Vs code， we go back into list do C here。

 It turns out that at least this loop isn't strictly necessary not to mention the fact that we already have another loop for just printing the list。

 If I want to more cleverly relocate memory。 It turns out that there's another function that we didn't talk about last week。

 But is in standard Lib dot H2 called。😊，Realloc， which as the name kind of suggests。

 it reallocs memory， but a little smarter in that it will try to grow your existing chunk of memory if it can。

 which is gonna be super efficient because then you can just plop the for at the very end。

 or if there just isn't room there because maybe someone else put hello world right there in memory elsewhere in your program。

 it's gonna do all of the copying for you。 So what you get back ultimately is a pointer to the new chunk of memory containing all of the original data as well。

 However， we're still going have to check for null。

 we're still going want to free the original list if something goes wrong and then return one。

 we're still going want to add the fourth value because real has no idea what more we want to put in the list。

 but I can， in fact， delete my other for loop whose purpose in life was just to copy all of those integers from old into new。

All right， that was a lot， let me pause for any questions。

Let does really know that it should reallocate the memory in least show you tell。

 like if you have a lot of mal。Very good question。 That's because I wrote a bug that we didn't trip over because I didn't compile this version of the code。

 So the question is， how does realalloc know what to realalloc， Well， according to the documentation。

 which I forgot to read， you need to tell realloc， what the address is of the chunk of memory that you do want to reloc。

 So the first argument to realloc， which I did admittedly forget until a moment ago is to put the address of the chunk of memory that you already mallloced earlier so that it knows to go there。

 see if there's indeed some garbage values it can reclaim at the end of that chunk of memory or if it has to wholesale move things elsewhere and memory to give you four times the size of the in this time instead of just three but still things can go wrong。

 like you still want to check for this null value because realc might not be able to give you enough memory or your memory could just be so fragmented that even though you want four bys。

 maybe there's three bys over here，2 bys over here，1 by over here。

 if there aren't four contiguous bys， realalloc 2 could fail and it will return null to signify as much other questions。

Thisす。Why do we still need the temp variable for the same reasons as before。

 Because if we just say list equals realloc and something does go wrong。

 realoc by definition will return null， but not touch the original memory。

 which case we have now lost track of where that original chunk of memory is。

 so we can never go back to it to print it to change it to free it so we have to use this temporary variable here。

 good question Other questions yeah。😡，Is there a reason that we free list instead of temp。

 So let me down here or further down。Okay， so further down， let me scroll down to where we came from。

 So here， after we've added this fourth value to temp， I've gone ahead and freed list。

 which at this point in the story， is still pointing to the original chunk of memory。 The 1，2，3。

 Then I am updating。List as a variable to point to the new chunk of memory。

 Then I'm doing my thing by printing out all of the integers therein。

 Then I'm freeing what list is then pointing to。 So I'm not technically freeing the same address in memory multiple times because I'm in the intervening time moving what list is pointing to。

Absutely， yes， it would be correct to go ahead down here and just say temp because temp is still in scope。

 It's still pointing at the same thing。 I would just argue that that's semantically wrong。

 because at this point in the code really list is the variable you care about。

 T was really meant to be a throwaway temporary variable and you're asking for trouble。

 if you use a temporary variable later， then you， the programmer intended。

 And if a colleague did that too， who knows what you've done with the temporary in the meantime。😡。



![](img/a13647f57b55a63e0e45544ba0bcb12b_17.png)

Good questions。Yeah， in front。Correct， Rialloc will try to give you more memory in the same location as before。

 if there's room at the end。😡，So realallocable to two potential things for you。

 So if the computer's memory looks like this， you're sort of out of luck because real can't give you this by。

 However， if it finds like 4 B down here， for instance。

 realalloc will not only allocate those4 B for you， it will then copy the data for you over to it。

 which is wonderful because it just means we don't need an extra four loop all the time。 we do this。

Yeah， in front。How does it know how much data to？Because how much， how does the。

 how does realalloc know how much data to copy because the operating system。

 and you can think of it as the standard library， S TD， LI B dot H。

 keeps track of what memory has been allocated。For you in the past。

 So when you pass in that same address， it knows it has essentially a lookup table， a dictionary。

 if you will， that tells it what memory has been allocated already。

 So you don't have to worry about that。Yeah， in front。Good question。 In other programming languages。

 you don't always have to declare the length of an array case in point Python coming next week。

 That is because someone else who invented that programming language wrote all of this kind of code for you。

 And indeed， that's one of the goals with our transition between weeks 5 and6 is to demonstrate that all of these problems are still being solved just not by you and not by me anymore。

 We're standing on the shoulders of other smart people who have invented not just new code。

 but like a new language and a new compiler or as we'll see an interpreter for it so that we can hide all of these lower level details because honestly。

 as you can see already， like this is an annoying number of lines of code just to have a conversation about the numbers 1。

2，3，4 in Python we could reduce this code to like two lines of code  one line of code。



![](img/a13647f57b55a63e0e45544ba0bcb12b_19.png)

It's going to be fun。 All right， So with that said。

among the goals here was to demonstrate that there are a bunch of ways in which we can implement these data types。

 but let's talk more concretely about what we' call data structures。

 which are concrete definitions of how you use the computer's memory to lay stuff out in memory and using data structures。

 you can implement stacks and cues and dictionaries and all of these other things。

 So we're going to put into your toolkit today， a whole bunch of canonical data structures that like every computer's scientist does and should know that you won't necessarily implement all of the time yourself。

 But when you use some feature of Python or Java or C plus plus or some other language you are choosing among typically implementations of these data structures that someone else has written the code for so that you can just benefit from the functionality and the features thereof like that fiIFO property we talked about or LIFO without having to get into the weeds too much yourself。

 So when it comes to data structures let's consider that。

We have at our disposal now a few new pieces of syntax in C and we're gonna to add just one more today。

 We saw last week that we have thestruct keyword and we've seen that for a few weeks now whenever we want to invent our own data structure。

 we can use literally struck we saw in the past that you can use the dot operator to actually go inside of a structure to get at a person's name or their number and we saw last week the star operator for dereferencing a pointer dereferencing an address to actually go somewhere like inside of a structure wonderfully today we're going to see that you can actually in some cases。

 combine the dot and the asterisk into a single operator with two characters that literally looks like an arrow and that will help reflect the yellow and black drawings that we've done over the past couple of weeks where we have an arrow on the screen pointing somewhere This literal arrow in code is going to line up with that same concept So let's introduce the first of our alternatives to arrays an array again is a contiguous chunk of memory where the values are back to back to back among the upsides so fast。

Like all of the data is right there we've seen since week zero you can do binary search and just jump around randomly by just doing simple arithmetic to go to the middle。

 the middle of the middle by just dividing by two a couple of times and rounding as needed。

 but the problem with the array to be clear is that they are statically，😡。

They are statically allocated to be a specific size， maybe three， maybe four。

 but it is a finite value， which is problematic because look at all of the code we had to write just to resize these things again and again。

 Well， what if we sort of try to preempt that kind of pain and try to just build up a list by linking it together。

 no matter where the values actually are in memory and move away from this constraint that everything has to be contiguous。

 after all， as I said a moment ago， if the computer has plenty of memory here， here， here， here。

 that to collectively is more than enough memory， but none of those individual chunks is quite as big as you need for an array。

 Well， heck， let's at least try to leverage all of the available memory and stitch together the data structure as opposed to really holding firm this constraint that the array be back to back to back and contiguous So a linked list is something you can now build using that syntax from last week and a bit more today in your same canvas of memory so that for the sake of discussion。

 suppose that we want to store。First in our list， the number one。

 Well we all know already that it might very well exist at an address like Ox 1，2。

3 for the sake of discussion， but it's somewhere there。

 suppose that you want to store a second value in memory。

 but you didn't think about it initially and so you weren't smart enough to put it like right next to the one and then the next value next to that but you know somehow from malloc or similar functions that you could put the number two over here at address Ox 4。

56 for the sake of discussion。 And similarly， there's room for the number three over here at say address Ox 7。

8，9。 So already we have a list of values in memory but because they're not continuous you can't just do some trivial plus plus trick to go from one to the other because they're differing numbers of bytes apart they're not just back to back one by。

 So what if we try to solve that problem in the following way。

 instead of just using one byte for each of these values。

 let me waste a little bit of memory or spend a little bit of memory and have some metadata associated with our data。

 So data is value。you care about metadata is data that helps you maintain the data you care about。

 So let me propose that we use two chunks of memory for every value。

 such that the top of each of those chunks represents the actual ver。

 we care about 12 and3 respectively。 And you can perhaps see where this is going。

 The second chunk of memory that have allocated to each of these values could perhaps be a pointer to the next one。

 a pointer to the next one。 And if this is the end。

 we can put our old friend O x0 aka null and just treat that as the end of the list implicitly So even though these things could be anywhere in memory by just storing with each value。

 the address of the next value in memory， creating effectively a treasure map or breadcrumbs。

 however， you want to think of it metaphorically， we can get from one node to the other。 And indeed。

 that's gonna to be a term of art。 we start using a node is just a generic structure that contains data and metadata usually like the number you care about and a pointer to the next such node。

 These are not to scale as an aside is。😊，four bytes。

 a pointer as we've discussed is technically8 bytes。

 but it just looks prettier to draw them as simple squares on the screen。

 So what does this really mean， Well， who really cares about Ox1，2，3，4，5，6，7，8，9。

 we can really think of this actually as being more of a picture with arrows。

 but to keep track of this list of three values。 I do propose that we're gonna need one additional value over here。

 and it's deliberately just a single square because to keep track of this list of three values。

 I'm going to use just one variable called say list and store in that variable a pointer as we defined it last week。

 the address of the first node why because the first node can then get me to the second。

 The second node can then get me to the third and so forth。

So what's the upside now if I want a fourth value somewhere on the screen， I could put it here， here。

 here， here， wherever there's enough room and just make sure that I update the arrow to point to that next chunk。

 update the arrow to point to the next chunk， there's no copying of data， one。

 two and three can stay there now forever until the program quits and we do actually free it。

 but we can just keep adding， adding， adding or growing。😡，This data structure in memory。

So that is what the world knows as a linked list in Python to which you were essentially alluding a list in Python is indeed a linked list。

 Other languages called these vectors， but they are essentially as that can be grown and shrunken automatically effectively without you having to worry quite as much about it。

 So how does the code for implementing something like this work。 Well。

 let me propose that we have this familiar friend of a person which we claimed in past weeks has a name and a number associated with them。

 We know from last week that strings are not technically a thing in C as a keyword。

 So that's technically just char star name and number， but same idea otherwise。

 and this is what we defined in the past as a person。 So this is a structure we've seen before。

 I now need to implement the code equivalent of these rectangles。

 each of which has an integer and then a pointer to the next such value。

 So let me propose that we delete what's inside this structure， change the name from person to node。

 which again is the generic term for a container of values and let me。

ose that inside of this new node structure， we put literally an int for the number we care about。

 There's going to be my 1，2，3， or 4。 And then， and this is a little bit。New。

Let's include in this structure， a pointer to the next such node。

 It's a pointer in the sense that it's an arrow。 It's the address of the next node。

 So that's why we say node star， I could call it anything I want。

 but semantically calling it next makes perfect sense because it's the next such node。

 but this isn't quite right for annoying technical reasons， I need to do one other thing here。

 I need to technically， and we've not done this before， put the name。

 give a temporary name to this structure， if you will。 So literally saystruct node here。

 even though I've already said node here。 why because I technically need to change this line to saystruct node star。

 Long story short。 Why is this necessary。 We'll recall in the past C and the compiler reach your code top to bottom left to right。

 Well， if in a previous version of this code， we use the word node here。

 but the compiler never sees the word node until down here。

 Like it's just not gonna compile because the word literally doesn't exist。

 We saw this with functions in the past。 So we have solution to that was to put the prototype higher up in the file and then it would compile okay。

 you can think。This is somewhat analogous。 whereby if I give this structure a name on this first line。

 even if it's redundant to this one， then I can say struck node inside of these curly braces because the compiler has already seen the word node there。

 So you have to do it this way。 So now that we have this in code。

 we can kind of start playing around with actually storing these things in memory。

 So let me propose that we go ahead and do this by transitioning back to V S code here。

 And let's instead of using our arraybased implementation。

 let's implement the first of our length lists。 And I'm gonna be a bit extreme and pretty much everything inside of main。

 I am for convenience now going include the C50 library， not so much for the char star thing。

 but because as we discussed last week， it's still useful for getting in and getting strings and other things which unless you use scanf are much harder and more annoying to get in C。

 So let's go ahead and do this。 outside of main。 let's go ahead and invent。

This node called struck node here。 then inside of my curly braces。

 willll give every such node a number and every such node a pointer to the next such node and we'll call this whole thing node by convention。

 Then inside of mainine， let's go ahead and do this one step at a time。

 Let me propose that to create a linked list initially， it's empty。

 So how do I represent an empty linked list。 Well， I could call the variable list and set it equal to null。

 But what is the data type for a linked list。 Well， per the picture that we had up earlier。

 insofar as all we need is a single pointer at far left here to represent the address of the first node in the list。

 I dare say all we need to say is that our list is of type node star。

 That is to say what is the linked list。 Well， it's by definition。

 the address of the first node in the list。So that's the first subtlety here。

 So that gives me a picture with no other nodes。 It just gives me a single pointer initialized to null。

 Now， let's go ahead。 And for parodity with the previous example， just do something three times。

 So in this for loop structured exactly as before。 Let's go ahead and allocate a new node。

 Ask the user for a number to put inside of it and then start stitching things together So as to achieve a picture in memory quite like this。

 So how am I going to do this。 Well， first， I need to allocate a new node。 How do I do that， Well。

 I can use our new friend Maloc and allocate the size of a node。😊。

I want to store the address of this chunk of memory somewhere。

 And what I'm gonna to propose is that we have a temporary variable。 And I'll call this n。

 which whose type is that of a node star。 So what am I doing here。

 I'm trying to build up this list in memory so that I first have a pointer to the list。

 I first have a pointer that is null pointing nowhere。 No list exists。

 I then want to go ahead and create one new node。Store value in it。

 And then point my list at that node。 Then I want to do it again。 and again， a total of three times。

 So how do we do this， We allocate space for the size of a node。 however many bytes that's gonna be。

 It's probably gonna be 12 because it's 4 for the n and 8 for the pointer。

 But who cares size of will answer that question for me。

 I'm gonna store the address of this chunk of memory inside of a temporary variable called n for node。

 And that's why it has to be node star， because it's going to be pointing to an actual node。

 I'm gonna do my quick sanity check。 So if n equals equals null， we can't proceed further。

 I'm gonna go ahead and just return one right now。 So that's just sort of boilerp code。

 You should be in the habit of doing anytime you're using Maoc。 But if all goes well， let's do this。

 let's go to the address in n。And then go inside of that node and change its number to be whatever the human wants it to be by using get in and just prompt the human for their favorite number。

 Then let's go to that same node and update the next field to equal for now。 null。

 because all I want to do is allocate one new node with that number。 That's it。

Then I'm going need to stitch this together further。So I'll propose that all we need to。

 and let's clean this up first is now make sure that we string these nodes together。

 This syntax isn't quite right because technically， because of precedence， I need to dere os。

 I need to。Dereference n and then go inside of it。 I need to dereence n and then go inside of it。

 However， this syntax。 if it's looking a little overwhelming and you have no idea now what's going on。

 thankfully and C， there's much simpler syntax， which is this go to the node and go inside it to get the number。

 go to the node and go inside it to get next。 So the arrow notation that I promised we would now have is the same thing as using the star operator。

 the dereference operator parentthesizing it， then the dot operator。

 which is a pan in the neck to write out all the time。

 I dare say n arrow number and n arrow next is just much simpler。

 It says go to n and point at the number field or the next field respectively。Alright。

 so the last thing I'm gonna propose we do。 and then we'll make this much more clear in picture form is this。

 Let's go ahead， and prepen。The node to the list。 And by prepen， I mean， insert it at the beginning。

 insert it at the beginning， inserter it at the beginning again and again。

 I'm gonna say n next equals list， then update the list to set equal to n。

 And then after all of this mess， I'm gonna return 0。 Okay， this was a huge amount of code。

 But let me give you a quick recap， then we'll paint a picture。Here is my knit list initially。

 so the foam finger is pointing to null， which means the list is of size 0。 There's nothing there。

 Then I ask the computer to do this three times， give me enough memory for a new node。

 then after checking that it's not null， put the user's favorite number in it and update the next field for the moment to null。

 then lastly， go ahead and prepen this brand new node to the existing list and by prepen I mean put it at the front So n at this moment is pointing to that new node and I'm saying you know what。

 whatever the current list is empty or otherwise set the next pointer equal to the list whatever that list is and then change the list to point at this new node。

😡，So now let's do this more carefully step by step in picture form。

 So I'm gonna propose that we go through some of these representative lines as follows。

 Here is the first line of code， even without the assignment。

 If you just allocate a variable called list that's a pointer to a node what you essentially has is a box of memory that looks like this it's a garbage value though because there's no assignment operator So who knows what's inside of this pointer that is why in my actual code I set it equal to null which effectively creates in memory the same box but gets rid of Oscars gruch and puts the null value there。

 So we know it's not a garbage value， it's a pointer known as null。

 So that's what that very first line of code did in the computer's memory。

 The next thing I wanted to do was allocate enough memory for a node。

 not a node star for a whole node， I want that whole chunk of a rectangle given to me in memory that's going return to me the address of the first byte thereof and I'm going to store that in a temporary variable called n。

 So at this point in the story N is going to be a pointer of its own another box that initially sure。

Going be a garbage value， but because I am using the assignment operator。

 it's going to point to that chunk of memory， which malloc， if successful。

 presumably allocated for me in the computer's memory。

 So n for all intents and purposes points at that same chunk。

 These values are still garbage values because it's just a chunk of memory。

 who knows what it's been used before。 But that's why after this line of code I took care to get an in from the user and then initialize the next pointer to null。

 So for instance， for the sake of discussion， let's get rid of get int for the picture and just say the human typed in the number one initially。

 Well， that's equivalent to putting the one in the number field by first going to the address of in n and then dereferencing it using the star and the dot notation respectively。

 So that means follow the arrow and then change number to the value one then the next line of code or rather or equivalently。

 you can just do the same thing。 And thankfully， now C syntax lines up with what the pictures look like we've been drawing。

 go to。😊，And follow the arrow to the number field。 That's literally what the syntax is telling me。

 Meanwhile， if I use that same syntax again for n arrow next， set in equal to null。

 that's like saying go to n， follow the arrow and change the next field in this case to null or well just blank it out to be clear。

 So at this point in the story， we have allocated the node。 we have stored one and null there。

 list is still null。 n is pointing to this。 But the whole point of this exercise is to add this node to the list。

 So we need to somehow update this value， which is why ultimately I'm going to do something like list equals n。

 Now that seems a little weird semantically， but recall that n is a pointer。 That is the address。

 pointing at Ox 1，2，3 or wherever that is。 So to point list at the same node。

 It's equivalent to setting list equal to n because then we'll effectively have an arrow identical from list pointing at that new node。

 And at this point， I don't even care what n is anymore。 It was always meant to be a temporary value。

 This now is my。istSo even though I did it in code already preemptively in a loop。

 the first iteration for that loop literally created this in memory。

Let me pause before we go through numbers two and three for any questions。

Cause the V S code version looks scary。 This is perhaps a little more bite sized。Okay。

 so how about we do this twice more for two and three respectively。 So again， inside of our loop。

 we're back to this line， which asks the operating system for enough memory for the size of a node stores that address temporarily in a variable called N。

 So here's our friend Oscar brought back onto the screen。

 Maybe the new chunk of memory is over there。 This effectively points n at that chunk of memory。

 The next line of code inside of that loop that's relevant is this and we'll get rid of get in to just pretend that I literally typed in2。

We're gonna go to this version of n， follow the arrow。

 go to the number field and set that equal to 2。 The next line of code。 we start at the n。

 follow the arrow， change the next field to null。 and then same lines as before。

 we now need to update list equaling n， but something's about to go wrong here。

 If I update list to point to the same node that n is pointing at watch what happens。

 I set list equal to that。😡，And because it's temporary， might as well go away at this point。😡。

What have I done wrong logically here？Yeah。Yeah， I lost the arrow to the original node。

 I have orphanned the first node because now nothing in my code is actually pointing at it。

 I've got in duplication， two pointers pointing at this chunk of memory。 So this thing。

 even though we obviously as humans can still see it。 We have lost track and code of where it is。

 which means that is the definition of a memory leak。

 I can never get that back or give it back to the operating system。

 So the program itself finally quits。 So I think I need to be a little smarter and not do this line quite like this yet。

 I think what I want to do and I've rewound。 So list is still pointing to the original list。

 and is pointing to only the new node。 What I think we need to do is something like this。

 And this is why the code was fairly non-obvious in VS code at first。 go to N。Follow the arrow。

 go to the next field and here's the cleverness。 point this pointer to the existing list's value。

 So if the existing list is pointing here， that just means hey。

 point this to the exact same thing because now I can safely update the list to point at the same thing is N So its arrow now points here。

 but even when I get rid of n， I wonderfully have the whole thing stitch together。

 And the metaphor I often think of is like around like Christmas time and olden times when people would like stitch popcorn together。

 That's what you're kind of doing with a thread here。

 you're trying to stitch together these nodes or popcorn kernels， if you will。

 such that one can lead you to the next can lead you to the next can lead you to the next。

 but you can never let go of part of that strand in the process。 So here now we have a list。

 which is great because notice we haven't touched the one， but we've added the two。

 we can go ahead in a moment and add the three， but you can perhaps see where this is going。

 I'm kind of doing backwards by accident。 But we'll get there soon。 So now let's allocate。😊，New node。

 run through in our mind's eye， All of those same steps。

 I'm gonna hopefully end up with a list that now looks like this。

 And even though it's kind of long and stringy， these values could be anywhere in memory。

 But because of these various pointers， I can jump from one location to the other making more efficient use of everything inside of the computer's own memory。

 Allright， But of course， we've got this symptom that didn't really intend whereby the whole darn thing is backwards。

 But I think that's kind of okay for now。 But I'd like to propose that we consider how we can now maybe traverse this thing and actually print out the values in memory。

 So let me go ahead and do this。 Let's go ahead and how about。😊。

Let's say let's go back to VS code here。 So at this point in the story。

 we've got the same code that implements that same idea except I'm using get in just so that I can dynamically type in the one。

 the two and the three without having to hardcode it into the actual code。

 supposeose that after doing this exercise， I actually want to do something interesting like print the numbers。

 Well we don't have that code yet in this version of my program。 So let's bring that back。

 Last time I did this just using a four loop and array notation。 and I think I can do that。

 but let me propose first， that I implement this idea pictorially。 Here's the same diagram。

 This is what exists in the computer's memory。 If I want to go ahead and print out these numbers。

 albeit in reverse order。 let me propose that we can do this by giving ourselves another temporary variable we'll call PTR pointer for short。

 and that's like having another foam finger that points at the start of the list。

 So it's not pointing it list， it points at whatever list is pointing at which means here。

 then I can print out the three pretty easily。As I next update pointer to point to the two。

 print it out， then point it to the one， print it out。 And eventually I'm going realize， oh。

 I'm out of nodes because the end of this list is null。 So that's the idea I want to implement now。

 logically in code， create a temporary variable called pointer。

 set it equal to whatever the list itself is print out the value， update the pointer。

 print out the value， update the pointer， print out the value， update the pointer。

 realize it's null and stop。 So in code， it's a relatively small loop。

 even though the syntax is still pretty new。 Since we've only just started playing with memory since last week。

 But what I'm going to do is exactly what I proposed。

 I'm going create a new pointer called PR and set it equal to the list itself。

 That's like having another phone finger， temporarily pointing at the first element in the list。

 Then what I'm going to do is say while that temporary variable is not null。

 Go ahead and traverse the list。 What do I mean by that。

 let's go ahead and print out the current element in the list by using percent I。

lash n and printing out whatever the pointer is pointing at specifically its number field。

 So that is follow the arrow and print out the number。 Then inside of this loop。

 I'm going to update after doing that。 my temporary variable called pointer to be equal to pointer arrow next and that will have the effect with just those few lines of code of implementing precisely this idea。

 I first set pointer equal to the list which happens to point here first， I then do my printf。

 and then I update the next field， I rather I update pointer to be the value of pointer follow the arrow next。

 So if this is Ox 1，2，3， for instance， that is what is now in sorry if this is Ox4，5，6。

 that is what's now in pointer， So the arrow effectively looks there in my forward loop。

 I print out with percent I this number and then I go to the next field。

 follow the arrow and then set it equal to rather。Whatever this pointer is here， Ox 7，8。

9 set it equal to the pointer there。 So I effectively move the arrow there。 Then lastly。

 I update PTR to point to the value of this next field， which is null。

 which means effectively pointer itself is null， which means the four loop cleverly stops now because I was supposed to do this whole loop while pointer is not null a pointer is now null。

 And just as an aside， if you prefer the semantics of a four loop。 there's nothing new here per se。

 I can do this exact same thing using a four loop simply as follows。

 and it's a little tighter to implement less follows， I can say four。

 instead of in I equals 0 in that old approach， I can actually use pointers in a four loop like this for node star pointer equals the start of the list keep doing something So long as pointer does not equal null。

 and on each iteration of this loop， update the pointer to equal whatever the pointers own next field is and then inside。

This for loop， print out using percent I backslash N， the current pointers number field semicolon。

 So here is where again， we see the equivalentence of four loops and while loops。

 What you can do with one， you can do with the other。

 This is a little more elegant in that you can express a whole lot of logic in one line of the for loop。

 Frank， I do think the first version is nonetheless more readable。 So let me undo， undo， undo， undo。

 Everything I just did on the course's website， you'll see both of these versions。

 This one's a little more pedantic as to what it's doing step by step。😊，Okay， that， too， was a lot。

 Let me pause here to see if there are。Any questions？And if you're feeling like that fire hose。

 like this is why we transitioned to Python where all of this now gets swept under the rug。

 but is still happening just not by us in a week， questions， yeah。Yeah， really good question。

 So here I've been preaching like we don't want to lose memory。

 We don't want to leak memory and here I am fairly extravagantly now spending twice as much memory to maintain this data structure。

 that's going be among the themes with all of the data structures we talk about if we want to gain some benefit like dynamic growth and shrinking of the data structure。

 youve got to give me something。 And what you've got to give me in this case is the ability to use more space。

 in a bit today。 and after break in particular， we're going decide we'd really like these algorithms to be faster。

 Well， that's fine。 but you're gonna have to give me something in return。

 you're gonna have to spend more space to make the code faster。

 And so time and space and financial cost and human time and any number of other resources are all things that you need to evaluate as a programmer or manager and decide which is least and or most important to you。

 And right now， I don't care about space as much as I care about the dynamism that I'm trying to solve first Other questions on here。

 yeah。Yes， why am I using pointer instead of N I， well， yes， I could reuse n at this point。

 I deliberately chose to use pointer for two reasons。1， I'm using it for different reasons here，2。

 it's not necessarily the best idea to use one variable here for a specific purpose。

 and then reuse the name down here。 besides it's out of scope at this point anyway。

 So it just makes me feel better that I have different variables doing different things。

 but it would not break if I did it your way。Other questions。Yeah， and back。Our pointers temporary。

 not necessarily， like the linked list we are building up in memory exists because we are using pointers to build this data structure and to keep it intact for as long as the program is running。

 my temporary variables， N and pointer PTR in this case， those are ephemeral。

 and I'm only using them to kind of stitch things together temporarily。😡，A good question。 All right。

 so let's now motivate why we're spending so much time sort of stitching these things together so carefully。

 Well， here's our little cheat sheet of common， but not exhaustive running times。

 let's consider what the running time is for some fairly basicistic operations like inserting a number into a linked list。

 maybe searching for a number in the linked list or traversing it and also deleting ultimately numbers in a linked list。

 So here is my list initially completely empty。 and suppose I go ahead and insert the one。

 then I insert the two， then I insert the three using code like we just wrote， I love this approach。

 because even though it looks a little scary at first。

 this is probably the simplest way to implement insertion into a linked list。

 why because I'm just constantly preending the next element， preending preending。

 which means all of my hard work is just here at the beginning of the list。

 So even if this thing as 100 elements in it， I'm only manipulating some pointers all the way over here pictorially at the left。

 which means it's pretty darn fast。 So given that definition in this picture。

 what would you say the big O running。😊，Time is of insertion into a linked list when using my current implementation。

😡，Big all of one why well it's not literally one step。

 but it is a constant number of steps because if we literally counted the lines of code I was executing。

 it's a few steps to sort of point one thing up here， point the other thing down here。

 then update the third and boom we' done in particular what my current code does not care about is the whole length of this list Y because I'm never traversing the whole thing for the insertion part I am obviously for the printing part。

 but for the insertion， I'm just prepending again and again。

 The downside though of this approach is that the whole darn thing is coming up backwards。

 I'm not doing anything with regard to the ordering of these elements。

 which means what's the running time of search going to be， for instance。

 if I tell you search for like the number one， find it for me。😡。

What's the running time going to be there in Big O？They go of， yeah。Big O of N。

 because in the worst case， it's gonna to be all the way at the end。

 And we've seen this scenario before。 So it's big O of N for searching。

 It's definitely big O of N for traversing or printing。

 But that goes without saying if you want to print every element， Obviously。

 you have to touch every one of the N element。 But what about deletion。

 Suppose I want to delete an element。 That's gonna be in big O of。Also N why because again。

 in the worst case， it could be all the way at the end。

 So only insertion as currently implemented is big O of one because we are exercising full control over where the new elements go irrespective of what the actual values are。

 So things could escalate quickly here， if we do actually want to start keeping things say in sorted order。

 because we can no longer just naively plop things at the very beginning of the list。

 I think we need to start being a little more careful as to where we put things。 So in fact。

 even though we're doing okay on insert right now， we still have big O event for the searching and for the deletion。

 which we won't do in code as well as of course， for traversal。

 So how else might we go about building this list， let me propose that we could maybe append to the end of the list。

 let's try that and see if it gets us anywhere better。

 So here's my list initially completely empty aka null。

 I go ahead and insert the number one as before。 But now in this algorithm。

 I'm gonna insert the number two。AndThe number three， so this is great because now， by chance。

 it ended up beautifully in order， but that's because I chose the numbers 1，2，3。

 but we'll come back to that detail。😡，Let's consider now what the running time is of this algorithm。

 of insertion using app pending to the list。 What's the big running time of insertion now。😡。

Big O of N。 So it's sort of strictly worse because now it's always going at the end。

 Now I could be a little smart about it。 I could just allocate another pointer and just always have another pointer pointing at the end of the list。

 just as I have a pointer pointing to the start of the list。

 that's totally fine if you're willing to spend one more pointer， which is a drop in the bucket。

 a legitimate solution。 but where I'd like to go with this is let's maintain sorted order。

 no matter the order in which the numbers are inserted， whether it's 1，2，33，2，1，21，33，1，2。

 whatever order， the human types in the numbers， I want to build the structure out such that they always end up insert sorted order。

 just so that my contacts in my iPhone or my Android phone， for instance， are sorted as intended。

 So how do we go about doing that。 Well， here we're still dealing with some big O let's try this。

 here's my list initially empty。 Now the user inserts person number two first So it ends up there。

 Then they insert number one， I'd like it to go there。 person number4， it goes over there。

 And then person number 3， it ends up here。Even though it's sort of obvious with a piece of paper and pencil how to stitch this together。

 this is now an annoying number of logical steps because there are so many opportunities where I could screw up and orphan one or more of these nodes。

 but let's consider the scenarios that we we might encounter。 Maybe we get lucky。

 and it's like an empty list and we just have to insert one new node。 that is trivial。

 We've done that already。 The two was super easy to implement。😡。

The one could be really easy to implement to， because that involves the prepending scenario。

 And we've seen that prepending is super simple。 So there's only two other scenarios to consider app pendingending。

 if it's a really big number and ends up at the end。 and we've talked about。

 but haven't seen code for that。 the annoying 1， I dare say is gonna be when the new number belongs in the middle。

 But I propose to think through it this way。 because now you just have four problems to solve not just one massive illdefined problem。

 You've got scenarios in which you want to insert a new node into an empty list。

 you want to prepen the new node into the beginning of the list。

 append it to the end of the list or somewhere in the middle。

 So that's like four blocks of code in my program， I can now sort of take the proverbial baby steps and implement this bit by bit。

 And to do this let me propose that in a moment， I'll switch over to VS code。

 But sort of Julia Chil style， I'm going to open up a premade version of the program that actually gives us a working solution。

 albeit initially with some bug。 So here we have out of the oven。 This version of。

dot C at the top of the file。 I've got my same includes as before。

 I've got my same structure as before here。 I've again got int main void。

 I've got the beginning of my list here， setting it equal to null。

 And then for the sake of discussion， I'm going insert three values for this example，1。

2 and 3 by allocating enough room for a node setting it equal to N Then I'm gonna make sure a standard and check that n is not null。

 And then I'm going actually populate this with the humans' first choice of values。

 So let me scroll down。 But as such， there's nothing too new just yet。😊。

Here we have the lines of code in which I'm getting an inch from the user setting next equal to null。

 And then I'm prepending， no matter what per our earlier version that we did on the fly。

 This new node to the list and then updating the list to point to it。 And then down here。

 I'm printing the number。 So this is where we left off。

 But this is a premade version that's nicely commented。 It's on the course's website for reference。

 What I'm not doing now is intelligently preending app pending or plopping the code in the middle。

 So how do we do that。 Well， let me go ahead and quickly open up a new version of the program that gives me。

More functionality than that one by opening up now， a premade version。That looks a little something。

Like， give me just a moment。嗯hu。Go sorry。看。Let's take a look at this version of the code。

 So everything thus far is the same。 And if I scroll down besides the new comments。

 you'll see that now I'm starting to make some decisions after I have allocated the new node and populated its number and next field As an aside。

 I don't strictly need to initialize the next field to null， because eventually。

 as we've done in every past example， I've updated that next field anyway。 However。

 because this one might now end up at the end of the list。

 and I just want to program defensively initializing pointers to null before you're ready to assign their value is a good thing in general。

 So heres the first of the questions I'm gonna ask myself if the list into which I am inserting this new node is empty。

 So it's the beginning of the story super easy， just set the list equal to the address of that new node and we done。

 That's what happened when I inserted a bit ago， the number two for the very first time。 So indeed。

 what has just happened here is that now the list previously empty contain。😊。

Only a node containing two。 However， thereafter， there was another scenario。

 So when we moved on in our story and added the number one to the list， well。

 that happened to end up at the beginning， but it could also end up at the end or in the middle。

 So let's break down those scenarios here， too。 So here。

 if it is not the case that the list is empty in that if condition。

 we're going to end up here now in the elset。What do I want to do here， Well。

 let's go ahead and for now， in this simplified version。

 append it to the end of the list so we can see that code。 How do I do this。 Well。

 I'm using a for loop， much like the one I had before。

 which just allows me to traverse the existing list， whether it has one node or many。

 and I'm gonna ask a question。 if following the current nodes， pointer field。

 next field leads me to null。 Aka， the end of the list。 Okay。

 let's go ahead and update the end of the list to actually equal the new node。 So in other words。

 if I'm sort of following， following， following all of the arrows， and I reach a node。

 whose next field is null， no problem， update that next field to point to the new node。

 I want to insert， irrespective of the values。I just want to append this node no matter what。

 And then I want to break out of the code。 Then at the bottom of this version of the program。

 It's all quite the same printinging out the numbers using the for loop version of my code from before instead of the while loop。

 but they're equivalent。 But what I did do in advance in baking this version of the program is also go through the motions of freeing every one of the nodes afterward。

 but we'll come back to that。 So this version of the code just to be clear。

 only appends nodes to the list， it's still not treating things in order。

 but we've now seen two of the scenarios pled off the list is empty。 or it has numbers。

 and we want to put something at the end。 So let me propose now that I take out of our distribution code。

 another version of this program that does that and a bit more。

 I'm gonna go ahead and open up in just a moment a new and improved version of list do C and now it looks almost the same at the top。

 scrolling down， scrolling down， scrolling down here's some now familiar code if the list is。

Do that simple thing as before and just prepen it。 rather just set it equal to the list。

 But here is now where we're adding some inequality。 So if the number in question。

Belongs at the beginning of the list。 So if the number。

In the new node n is less than the number in the current list。

 which is presumed to be the first node at the moment。

 then go ahead and update the new nodes next field to point at the existing list。

 and then update the list to point at this new node。

 thereby giving us from two in the list to one and2 in the list to be clear if I go back to VS code here。

 what's happened here is because one is less than two。😡，Of course， I'm gonna update the new nodes。

 next field to point to the list。 What does this mean， Well。

 the new node at this point in the story is the new node for the number one。

 because that's the second thing we're inserting。 I'm going update its next field to be whatever the list a moment ago was already pointing at。

 So this is the after effect。 But a moment ago， list was pointing at only the two。

 So now the next field of the one points at the two， And then lastly here in this line。

 I update the list pointer to be the address of that new node。

 And here's where I'll wave my hand a little bit today， because it starts to escalate quickly。

 It's useful。 And it might very well be useful for problems set 5 in particular。

 But I think more healthily reviewed step by step at a slower pace。😊，Here is where I'm asking myself。

 all right， If it's not the only element in the list and it doesn't belong at the beginning of the list。

 Well， it belongs somewhere later in the list， which gives me two final scenarios。

 Let's figure out which scenario we're in。 Let's use this for loop to iterate over all of as many of the nodes in the list as we need to。

If we get all the way to the end because our pointer variable now equals null。

 it's like following the arrows following the arrows。 and maybe we're trying to insert the number 5。

 I've already hit the number4。 I've hit null5 belongs at the end So here we have are promised append code。

 which is exactly the same as before， but now I'm doing it conditionally。

 if I've indeed found my way to the end of the list。 And then lastly。

 let me scroll down just a little bit。 if it's not the case that the list is empty。

 and it's not the case that the new node belongs at the beginning。

 and it's not the case that the new node belongs at the end。

 I'm just somewhere in the middle of the list because the new number I'm inserting is less than the one I'm looking at here and it's okay to use two arrows。

 but I'll wave my hands at that for now， these three lines two pointer manipulations in a break is what's going to stitch together that three in between the two and the four。

 And let me propose for lecture sake， take this on faith that this collectively does stitch things together properly but I do。

Think as you'll see in problem set 5， it's a much better exercise to think through a little more carefully step by step because there's just a lot of fine tuning of these pointers together and the order of operations does matter。

 But at the very end of this program， notice this is kind of mind list。

 even though the syntax is undoubtedly less familiar here is how just like traversing the whole list to print it out。

 we can similarly do one more pass over the linked list and free every one of the nodes。

 But notice it's not quite as simple as just saying free the whole list， free is not that smart。

 Maoc is not that smart。 And even though you have called malloc 12， three times。

 you have to really call you have to call free1 to， three times。

 you can't just pass at the beginning of the linked list and say you figure out what to delete because it has no idea what a linked list is or what your data structure actually is。

 So the reason that this loop is a little complicated is that what I'm doing with these three lines is essentially traversing my list。

And making sure that I have a pointer that when I'm ready to delete the three， the one。

 I have a pointer pointing at the two， and then I free the1。

 I update my pointer to point at the three， and then I delete the two。

 I update my pointer to point at the4。 Then I delete the three。 and then I delete the4。

 So there's a bit of trickery involved in making sure you don't orphan things step by step。Okay。

 that was a lot。 Let me pause here。To see。If there are， in fact， any questions。

Even though we're deliberately waving our hands at some of those details。Questions。Now。

 let me add one final flourish。 If we were to really quibble over this。 I mean， my God。

 we're up to 80 lines of code already just to implement the numbers 1，2，3，4。

But there are some subtle bugs in here at the moment。 So for instance。

 suppose that something goes wrong with malloc inside of this for loop here and suppose that it's not your first iteration。

 something goes wrong and maybe the second or the third iteration。

 Why is this error check suddenly bad as I've implemented it。😡，Yeah。

I didn't free the memory from the previous iteration。 So this is where like oh。

 like memory management starts to get really annoying because if you do want to practice what I've been preaching。

 which is free any memory you've allocated， and you've already allocated one， maybe two nodes。

 because Maoc is again failing maybe at the last iteration here。

 you have to somehow go back and free all of that。 And that's fine。

 like we have code at the bottom of my file here， which could traverse through the existing list and just free it all。

 So I could just copy， paste that code， put it into my if condition。

 and then run that code2 to delete the whole list But at this point， if you're copy and pasting。

 you're probably doing something wrong。 And so let me propose as a final version of this just for your reference later in the9 and final in version 9 of this file here。

0 indexed， what we have Give me one second to just make a quick copy and copy it over in list 9 do see our last version of this。

 we have the following whereby now in my function。 in my main function。

 I have the exact same code is before。😊，But I've taken the liberty of implementing an unload function so that I can call it here as well as at the bottom of this main function。

 so I can unload it here or unload the list there， and all I've done now is in good form in terms of design。

 just implement the notion of deleting a linked list in its own function so I can call it any number of times from any number of places。

 but just so you've seen。😡。

![](img/a13647f57b55a63e0e45544ba0bcb12b_21.png)

How I might do that there。Alright， so let's ask the question。 after all this。

 what is the running time of inserting into a linked list。They go of。Say a look big of。And damn it。

 like， that's no better。 All right， What's the running time of searching a linked list。Big O N。

 damn it， What's the running time of deleting from a linked list？😡，Big O of n。

 So like everything is literally big O n。 So there's the price we've suddenly paid。

 We have an hour after we started with arrays gotten to the point where we can dynamically grow in a linked list。

 And I dare say even though we've not done it and won't do it today shrink the linked list by freeing things that we don't need。

 So we have the dynamism and we can make more efficient use of memory even if it's very fragmented and there's a few bytes here or a few bytes there but we've paid this price。

 because with a arrays recall， even our phone book example， we at least had binary search。

 the running time for which was big O of log end。 So my God， not only are we spending more space。

 the darn thing is slower。 Surely， this is not how our phone contacts are implemented。

 Surely this is not how stacks and queuees are always implemented it。 And indeed it's not。

 this is just gonna be a stepping stone to now doing a sort of mashup of data structures whereby we take the best features of a arrays。

 the best features of linked list， mashed them together to get new and improved data structures。

 But for that， we're gonna have to have some cookies first and we'll come back in 10 minutes。

 Cookies are now served。All right， we are back。 So let's recap how we got here and why。

 So we started with our old friends arrays， which we introduced in week2 and recall that the whole peel of arrays was that one。

 as all things go like relatively simple， certainly now in retrospect。 But more importantly。

 they were really darn fast。 like arrays inof far as they are stored back to back contiguous in memory means that we could do very simple arithmetic recall to like figure out the length of it and then divide by two to get the middle。

 divide by two again to get the middle of the middle and so forth。

 And even though we might have to do with a little bit of rounding。

 arrays l themselves to binary search。 And thus logariththmic time。 So big O of login。 But today。

 I claim that the downside of arrays that they have to decide in advance how big you want it to be。

 And if you guess wrong。 And it's too small， how much memory you ask for。

 you then have to reallocate memory。 And that's fine， it's solvable with mallc or realloc。

 But it's gonna take some amount of time to copy all of the old memory into the new memory。

 whether you do it with a for loop or reloc does it for you。😊，Meanwhile。

 we only did it with like three values， maybe four。

 but imagine it being 3 million values that you now need to allocate more space for。

 you're gonna waste a huge amount of time copying 3 million values from the old location to the new。

 And so that's just generally not very appealing。 And so that motivated a whole discussion of linked lists。

 whereby now， we can create a more dynamic data structure。

 whereby we only allocate memory as we need it。 So we don't have to worry about underestimating or overestimating and therefore wasting memory。

 we can just go bit by bit for each new value， we allocate another node。

 another chunk of memory and the thing just grows and grows and grows。

 but as we saw just before break， the downside is even though we're avoiding the inefficiency of having to move stuff around in memory once allocated the nodes can stay where they are and we just update our pointers。

All of our running times for searching， inserting new elements。

 deleting old elements would seem to be big O of n。 But why was that， Well。

 in the context of a link to list， recall that it might look a little something like this whereby we have a pointer called list pointing to maybe four values like this and suppose that we do want to search for a value。

 now it's nice because in our latest version of this linked list。

 it was sorted from smallest to largest and that was always a precondition of doing binary search But even though it's obvious to our human eyes where the middle is It's like roughly over there how is the computer gonna figure that out or how is your code that you write。

 Well， unfortunately， the way we've stitched a linked list together with these pointers is if you want to find the middle。

 you can But you got to start at the beginning， traverse the whole thing to figure out how long it is then do it again and stop halfway through once you know what the halfway point roughly is then if you want to search the middle of the middle。

 you've essentially got to do that whole process again， And so now just to use。Binary search。

 you need to spend big O of n steps just to even find the middle。

 Now if your mind is kind of spinning and you're like， well。

 maybe I could just kind of cheat and use a pointer to always point to the middle of the list。

 totally fine， you can spend in some additional space to remember the the middle of the list。

 the end of the list but where does that stop。 What if with binary search you go not just to the middle but the middle of the middle the middle of the middle of the middle you're gonna keep around a pointer to every element because if you do。

 you're essentially back to an array if you've got one location for every other location So it just kind of devolves into a mess。

 even though there's some minor optimizations we could in fact make in fact we didn't talk about it yet。

 but one common alternative to a singly linked list which ours is it's linked with a single pointer from node to node computer scientists also like to talk about doubly linked list where there'sarrows going both directions which actually would have simplified some of the last code that we looked at because I don't have to look ahead to figure out what I want to free or what and where I want to insert some value but that too。

Doesn't fundamentally change the speed。 It just makes your code a little easier to write。

 So in short， with linked list， we get dynamism， we can now grow and shrink things without wasting time copying。

 but we've lost hold of our binary search。 and that was very appealing as far back as week was zero when we wanted to do something quite quickly。

 So let's see if we can't make some mashups now take some arrays， take some link list。

 literally mash them together into a sort of Frankenstein data structure and see if we can't get some of the speed of arrays。

 but the dynamism of linked list。 And so I give you trees。

 if you think about in your mind's eye what a family tree looks like where you typically have some parents and then some children and some grandchildren and so forth。

 It's this sort of treelike structure。 even though by convention。

 it's drawn top down instead of bottom up like trees in the real world。

 But the top of that family tree we're gonna call the root of the tree just so happens to indeed grow down。

 But a tree is a very common data structure。 and it's interesting Vi arrays and linked list。

 and that it's the first of our two dimension。😊，Da structures。

 an array is effectively just a single dimension along from left to right。

 A linked list is essentially the same， even though in reality might be up down left and right in memory。

 it's still just one thing stitched together in a single dimension。

 a tree adds now a second dimension and specifically useful for us is what we're gonna call binary search trees。

 which is spoiler going to give us back the ability to use binary search。

 But we're gonna store the data， a little more cleverly than in arrays alone。

 instead of storing our data in one dimension in a binary search tree。

 we're gonna store in effect in two different dimensions。 And that's gonna gain us some speed。

 So here， for instance， is an array of seven numbers， as we might have seen it back in week2。

 when we first introduce arrays。 let me draw our attention to the middle element。

 and then to the middle of the middles and then the middles of the middles of the middles。

 just by color coding them slightly differently。 If I were to run binary search on these numbers or the lockers that we had on the stage a few weeks back。

 I would jump to the middle than the middle of the middle and so forth。😊，though。

 is that implemented it as an array。 It's not gonna to be very easy to add new values Y。

 because if I want to add the number 8 or 9 or 10。 I might get lucky and there might be room in memory here。

 but I might get unlucky in which case， then we got to start jumping through those soups of malloc or realaloc and copying all of this memory to a new location。

 which is doable。 We solved it in code， but it's going to be slow for larger data。

 So can we avoid that。 Well， maybe I deliberately color coded things like this。

 because let me propose that instead of storing these seven values in an array。

 Let's store them in a family treelike structure like this。

 where I just kind of exploded them vertically on the y access here。

 So now the middle element the fours at the top of this tree， the two in the6。

 which were the middle elements after the middle are going be to the left and right of the。

 and then these leaf nodes。 so to speak， we borrow a lot of vernacular from the world of actual trees。

 these are leaves in the sense that they themselves have no children。

 they're at the edge of the data structure are going be the middles of the middles of the middles。😊。

All the data is still there。 I've just exploded it from one to two dimensions。

 and let me propose that now that we have this technique of using pointers， which we use with C code。

 but you can depict them pictorially with arrows， let me propose that we stitch together these seven values in memory using a bunch of pointers whereby now each of these nodes drawn as a single square for simplicity is going to have not only an integer associated with it and not just one pointer。

 but per these arrows as many as two arrows associated with it。

 So our nodes are about to go from data structures with two things a number and a pointer to three things a number and two pointers for the left and right child respectively。

 And I dare say now that we have a two dimensional tree data structure consider how you might find a number therein。

 Supp I'm searching for the number5。 Well， I start at the root of the data structure。

 And even though our human eyes obviously know where we're going。

 notice what's important about this binary search tree。 If I go to the root of the。Of the tree。

 I see the4，4 is obviously less than 5。 What does this mean。

 This means I can divide and conquer the problem right off the bat。

 I know that5 is going to be to the right of this node， which means effectively。

 if you think in your mind's eye about sniffing the branch there。

 I have just have the problem essentially， like dividing the phone book in half。 Why。

 because I don't even waste time looking at this subtree， the left child of the four element。

 Meanwhile， if I go from the root to its right child here。 I see the number 6，5， of course。

 is less than 6。 So this is effectively like snpping off that child。

 because I don't need to go further there because I know a smaller element is going be in this direction。

 And that's the key property of a binary search tree。

 It's not just a family tree with numbers all over the place， they follow a certain pattern。

 Every element is going to be greater than its left child and less than its right child。

 assuming you don't have identical values。 And that property is actually a recursive。

To borrow terminology from a couple of weeks back， recall that a recursive function there's one that calls itself a recursive data structure like the pyramid in Mario is a data structure that can be defined in terms of itself。

 Well， binary search tree is a recursive property in so far as if it applies to this node。

 it also applies to this node。 case in point 2 is greater than one。 but it's also less than 3。

 It's true over here，6 is greater than 5， but less than 7。

 And it's technically true of the leaf node because the definition is at least not violated there。

 because they don't even have children themselves。 So this is a binary search tree because of that pattern。

 So this then invites the question， well， how long does it take us to search for a value in a binary search tree。

 Well， if the number is 5， it's gonna to take me 1， two steps。 But if there's n elements here。

 can someone want to generalize that mathematically or just instinctively they go of。Log N。

 and even if you're not quite sure how the math works out any time you take a data set and you have it。

 have it， have it。 We're talking about log base2 of n again。 And indeed。

 that's going to describe the height of this tree。 The height of this tree is essentially log base2 of n。

 because if n is 7， it's going to give me essentially 2 when we round appropriately。

 if we round up if we've got8 elements， log base2 of 82 to the third。 So that means 3， So 123。

 it kind of works out。 even if I'm doing that a bit quickly。

 The height of this tree is log base2 of N Aka big of log n。 How long does it take to insert。

 I think it's gonna take log n because I can insert over here or over here or over here。

 depending on where the number goes， how long does it take to delete I'll claim it's going to take about the same。

 So wow， we're back in business。 I've got now the ability to grow and shrink my data structure。

 because if I want to insert the number 8 iss going go right there。

 if I want to insert the number like 5。5， I can see where I would put it。

 It's going to be easy to add new nodes by just updating the pointers without copying every。

Everything in memory like we had to for arrays。 But there is a downside here。

I got to concede something。 What am I， What price am I paying。

 What's the trade off here to gain that dynamism and that speed。But individual。Yeah。

 I' am literally using three times as much memory now because even though it's not depicted here。

 explicitly， each of these squares represents an integer and a pointer and another pointer。

 So that's like 16， that's like 20 B at this point of memory instead of just four bytes for each of the integers in an array。

 Nowadays， though space is pretty cheap。 we all have very large dropbox folders。

 icloud folders in the like。 So it's not really a big deal to use that many more bys。

 certainly know how a big deal for7 numbers。 but if it's 7 million numbers。

 maybe this isn't the best data structure to use， even if speed is important。

 you got to decide ultimately based on your actual use case， what matters more。 So in short。

 a binary search tree， you can kind of think of as an amalgam of or rather a variant of a linked list。

 except that every node has as many as two pointers instead of one。

 which is what gives us now this second dimension。 And in fact。

 this translates pretty nicely to code。 In fact， if we consider how we implement it in a linked list。

 a node recall that it looked like this where you got a number in each node。😊。

And a pointer to the next element in the linked list。 Well， I think for a binary search tree。

 we can sort of borrow this as inspiration， make a little more room because we need two pointers instead of one。

 and I'm just gonna to call the left child， the left pointer and the right pointer。

 But here is the three times as much space give or take because I now have three elements associated two pieces of metadata and one piece of data that I actually care about to stitch this thing here together。

 All right， well， if this is the data structure there。 how could I implement this in code。 Well。

 here's where recursion again comes into play。 The fact that a binary search tree is recursive in nature in that what you say about this node about it being greater than the left child in less than the right child can be said of this node and this node and this node in this node。

 you can leverage that beautifully in code like this。

 So suppose I'm implementing a search function and see whose purpose in life is just to say yes or no true or false。

 the number you're looking for is in this tree， which might be a useful thing to check in an algorithm。

😊，Search is going take two arguments I propose The number you're searching for and a pointer to the tree。

 That is the root of the tree initially。 So how do you actually traverse this thing in C code。 Well。

 we can pluck off the easy case first， the base case。 if the tree itself is null。

 Like if you hand me nothing， I'll give you your answer right now。

 false like there's no number here if the tree is empty。 So that's easy。 Otherwise。

 if the number you're looking for is less than the number in the current node。

 So tree is what's passed in a pointer to the root。 So if you follow the arrow。

 you can get inside of that value and see its number if the number you're looking for is less than that。

 Okay， you want to what snip off the right tree and dive down the left subtree。

 So you search the trees left child for the same number else。

 if the number you're looking for is greater than that number， you search。For the trees。

 right child for that same number。 And the fourth and final scenario is what？ Well。

 if the number you're looking for equals the number in the current node， you got it return true。

 And if you recall some of our past design discussions。

 This is sort of a waste of everyone's time to ask this question explicitly。

 let me tighten this up design wise because there's only four possible scenarios。

 Either there's nothing there。 It's to the left， it's to the right or you found it。 It's right there。

 So whether or not you agree at this point in your programming career。

 like there is a beauty to this code that most programmers would claim is here and that it's so relatively elegant whereby you've defined what the function is。

 you've got this base case， which is arguably one of the clunkies parts。

 But the fact that you can just check a value here， and then traverse the exact same structure。

 but a subset of it by traversing the left subte or the right subre is like a beautiful application of recursion And it allows you to search for this thing no matter where it is in the computer's memory Que then on this idea of a binary。

😊，Searchry or this actual。Code thereof。But if you don't answer a question， if youre not written。Nope。

 if the number is not there， we recall。 So if we get all the way to the bottom of the tree。

 such that now in that one of those leaf nodes， and that's not the number I'm looking for。

 such that there's no left child left， no right child left， this conditional is gonna kick in。

 and I'm gonna return false。 But if I find it along the way。

 whether it's at the top of the tree or somewhere in the middle or among the leaves。

 I will eventually return true。Good question。 And to be clear， even though I'm calling this a tree。

 that's true， certainly for the first time I call this function because I'm passing a pointer to the whole tree structure。

 But if you think about it， what's the left subree in the right subre， It's just a smaller tree。

 It's like a baby tree that's attached to this parent node。 so to speak。

 So it's perfectly reasonable to just call the search function with that child， because it。

 in turn has a whole subree below it or the right child which has the whole subte。😊，Below it instead。

Allright， so I like this direction。 We've now kind of improved upon the linked list。

 We've gained back some of our performance because we can now find something with big O of log n time。

 I don't love the fact that I'm using three times as much memory roughly。

 That feels like kind of a high price to pay just to speed things back up。

 But let's consider whether or not this thing is actually gonna work as the data structure gets bigger and bigger as well。

 So it looks beautiful here is written。 And that' because I drew the picture like this。

 and it's got seven elements in it。 But how did we get to seven elements。

 Let's start from the beginning。 suppose that the tree is initially empty。

 and suppose that a human using get in or some other technique inserts the first elements into the list like the number two。

 And the goal is to maintain the binary search tree property。

 which means you got to have it greater than left child less than the right child。

 So suppose the human using get or some other technique next gives me the number one。 no big deal。

 I plop it right there is the left child suppose they give me the number three next No big deal It goes right there。

 I have very deliberately manipulated this story to work out beautifully。 such that the。😊，I smaller。

 but it's still a binary search tree and nicely balanced， so to speak。 But what if the user。

 for whatever reason， just gives me a more perverse sequence of inputs。

 like the worst case scenario to give me three elements。 and suppose they give me one first。 Okay。

 that's the root。 Then they give me2。 Okay， that's cool， That's like the right child。

 But what if they then give me three。 Well， to maintain that binary search property。

 the three has to go over here。 supposeose perversely， then they didn't give me4 then 5， then 6。

 imagine in your mind's eye where this story is going。

 What have I accidentally created in memory then。😊，A linked list。

 which is like bad for all the reasons we discussed before the break。

 because even though we're getting the dynamism， it's devolving into big O of n。

 So I've kind of manipulated the situation here with the original example with seven elements and then three elements by making sure that they were inserted in just the right order because unless you are clever about how you build the tree in memory。

 it could very well devolve from a tree in two dimensions into actually a link list in one dimension。

 And now this is just a long and stringy tree that does not violate the binary search tree definition。

 but it is surely not balanced in this case。 Now， as an aside。

 if you take higher level languages and data structures and algorithms。

 there's many different alternatives to binary search trees that actually have it baked into the algorithms a little bit of rejiggering of the structure so that really as soon as you insert this three。

 you spend a little bit more time and clean the situation up。

 and essentially what you do is like pivot the thing around this way so that two becomes the new。

Root and then one hangs off of it and three still hangs off of it。

 So with each insertion or deletion， you rebalance the tree as needed。

 which does cost you a bit more time， but it avoids the thing devolving into big O of n again。

 and we won't do that in code。 So this is recoverable but not if you implement it naively as I did at least verbally in this story。

😡，All right， Well， can we do better than that？ Well， why might we want to。 Well。

 at this point in the story， it certainly could devolve into big O of N， And that's not great。

 Certainly for large data sets， it's nice that we're back to log n。

 at least if you take on faith that we could kind of rebalance this thing as needed and maintain a logarithmic height for it。

 But really the holy grail of data structures is to achieve something that is big O of one。

 like constant time， whereby no matter how many numbers or names or sweaters are in the data structure。

 it will take just one step， or maybe three steps。 even 100 steps。

 but a number of steps that is completely independent of how many actual pieces of data are in the data structure。

 that is to say over time， it doesn't get any slower， even if you've got tens。

 hundred thousands millions of elements in there already。

 So how do we gain something like big O of one， constant time。

 the appeal of which is reminiscent of our early picture from week1。

 like this was our early algorithm for finding someone。phone book or counting students in the room。

 something linear， literally straight lines。 This was the logarithmic curve。

 which especially as you zoom out， starts to get very， very appealing timewise。

 something that's constant time looks even prettier。

 It is a straight line the one step mark or the two step marks。

 whatever the constant number of step marks is And even though logarithmic will still grow in perpetuity。

 constant time by definition never changes。 And this is what we'd really like。

 So when you're searching for someone in your phone， you're searching for something on Google。

 you're asking a question of chatBT， you get an answer like that in constant time In of how much data is actually in there。

 Well， let's see how we can do this to do this。 We're gonna at least need a new building block。

 a term of art known as hashing Hahing formally takes an infinite domain of values and maps it to a finite range of values。

 So from high school math class domain is the input ranges the output So an infinite domain to a finite range is the goal here of hashing。

 and we might see this actually in the real world when you're playing games or runnot or you're cleaning up。

😊，After a game， like here is here are some super jumbo playing cards that we got online。

 and suppose that you want to just get these into sorted order。 You could do this very painstakingly。

 There's 52 cards here。 You can kind of lay them all out and start sifting through them and put the two over here and the four over here in the hearts and the clubs and so forth。

 Or you can start to look at the cards and bucketize them first to take a 52 size problem And maybe shrink it down into 4。

13 B problem。 So here， for instance， is where the first diamond mi the club here， spade over here。

 diamondd over here。 And I can kind of just do this again and again。

Bucketizing literally all of these values so that I've got a very simple heuristic that allows me to move the cards into these buckets。

 each of which is gonna have a subset of the values。

 And then I've got smaller problems I can deal with。

 So dot dot dot assume that I bucketize all 52 of these values。

 Then I've just got four problems remaining。 And I dare say it's a little easier then。

 because they're all of the same suit。 And so I can pretty easily sort it from ace to king or whatnot。

 because those are effectively just numbers at that point。 So hashing refers to again。

 taking values from an infinite range。 in this case， it can be finite。 and it is in this case。

 But if you're doing it more generally with numbers。

 you just have to map it to a finite range like 1，2，3，4 finite number of buckets of values。

 at which point then you can solve the problem a little differently。 or a little more efficiently。

 So why is this germane。 Well， I would propose that if we want to start organizingizing our data in memory toward an idealistic goal of achieving。

😊，In time， hashing might be one ingredient for the solution there， too。 And generally。

 we're gonna to describe the process by which you decide what input goes to what output is namely what's called a hash function。

 It's a mathematical function or a function and code that takes as input a card from a deck or maybe a word from a dictionary and outputs a value that represents the bucket into which it should go。

 So in the case of our contacts app， for instance， of course， in the goi of it。

 you have all of your friends and family top to bottom alphabetically presumably you might want to ideally find someone quite quickly。

 ideally in constant time， the naive implementation that Apple or Google could implement。

 It's just use linear search。 search through all of your contacts， top to bottom。 And eventually。

 you will correctly find the person， but wouldn't it be nice if instead use an array。

 And then they can use binary search and get you the person in logarithmic time， That's great。

 But if you have a lot of friends and family in there or much larger data。

 wouldnn't it be nice to just jump to the answer in one step。 And instead of even log of end step。

 So that's our goal。 Can we get close to or。😊，at constant time。 So with a hash function。

 we essentially have our old friend problem solving here。

 the inside of which the algorithm is known as a hash function。 And for instance。

 if I'm looking at Mario's number， I might now want to look for Mario not top to bottom or not divide and conquer。

 jumping around to the middle of the middle of the middle。

 let me just figure out what bucket Mario is in and in the English alphabet。

 there's 26 letters of the alphabet A through Z eithercase or lowercase。

 and suppose that I want to find what bucket Mario is in。 Well。

 much like these cards and the suits thereof， wouldn't it make sense that anyone whose name with a goes into the first bucket and maybe the B's go into the second bucket and the do dot dot z' go into the last bucket So it stands to reason that if I pass in Mario to a hash function implemented in C or some other language。

 I would like to get back the number 12 because M is the 13th letter of the alphabet。

 But if we start counting it0 with our buckets， which are essentially an array。

 then it's index location 12， instead of 13。 Similarlyly， if Luigi is the input。

 I'd like to get back。The number 11。 So my hash function somehow takes as input in this story。

 a string and gives me an integer。 I claim there's theoretically an infinite number of names in the world in the English language。

But there's only gonna be 26 possible answers from this hash function，0 through 25。

 So that's our infinite domain to our finite range。 instead of 4， it's now 26。 Allright， so what。

Should we do with the computer's memory to leverage the fact that we can very easily bucketize names based on the first letter of someone's name。

 Well， let me propose that the hash function part of this。 ourane as it looks。

 it's actually pretty straightforward。 So if you wanted to translate this idea into C you can include C type H。

 which we've used a few times to get it access to like functions like to upper。

 and this is just to make sure you can be case insensitive。 Here's my hash function。

 it's gonna return an int， which is the goal takes a string as input。

 I will call it name And what is this function do。 Well， it's kind of some clever ASi arithmetic。

 It first converts to uppercase。 The first letter of that person's name。

 So if it's all lowercase forces it to uppercase Y because I want to subtract no matter what 65 the ASi value of capital a from this。

 And I don't want to screw up the math。 if I'm doing like a lowercase letter minus the capital。

 I want capital minus capital is all So this will return to me a number between0 and 25 inclusive because if。

Is a letter a name that starts with a。 I'm only looking at the first letter。

 I'm subtracting off a that gives me 0。 and I'm gonna return0 as a result dot dot dot if it's Z。

 I'm gonna return 25 instead， Now there's no error checking in here。

 if you pipe in nonenglish symbols It's gonna break。 So let's just assume for simplicity。

 This is indeed in English name that's coming in。 I can refine this a little bit。

 I'm going propose moving forward in our final week here of C。

 there is some added defenses you can put in place when writing code。

 Like if you know that you're receiving a name as input that is you're passing something in by reference。

 there's a danger now per last week， because now the call of this function。

 whoever's using this function is telling you where to find Mario when where to find Luigi's name。

 The problem with that is that you could go to that address and actually change their name in memory。

 even if you're not supposed to。 You're supposed to just use the name。

 So you can do something like conantt， which says you should not be able to change this value。

 even though I'm not giving you a copy of it by value。I'm giving you a reference there， too。

 Another refinement here is that a hash function for an array is the goal should return a value that's 0 or one or two on up。

 never negative so we can even more protectively say it's not just an int。 It's an unsigned int。

 And we talked briefly about that last week。 albeit'll be in the context of chas。

 These are just like minor improvements that makes your code arguably better designed because you're opening yourself up to fewer possible mistakes or issues。

Alright， so with that said， let's now assume that we've got this kind of function in implemented。

 and we can now use it to decide what bucket to put these people's names into。 Well。

 let's give you what are called hash tables， which are sort of the Swiss army knives of data structures。

 The kind of thing that some computer scientists have been quoted as saying if they were stuck on a desert island with only one data structure。

 This is probably the one they would want， why it's just really generally useful。

 because it allows you quite powerfully to associate keys with values。

 which is to say to come full circle today， hash tables are often how you would implement at a lower level。

 the thing we began class with talking about dictionaries， collections of key value pairs。

 That after all， is what a phone book is。 if we call it you know names and numbers。

 but it's keys and values。 That's what an actual English dictionaries is the Oxford English dictionary。

 It's a bunch of words and definitions or keys and values so useful in general to be able to associate one piece of data with another Ergo hash tables。

 So here's how you might implement and see a hash table。You want it to be of size 26 for instance。

 so 26 buckets from a to Z， hence the 26， you want this to be an array。 and that's fine。

 This is an array of four buckets。 I'm going to use an array of 26 buckets because a hash table2 is going to be an evolution of our linked list mashed together with an array。

 So a hash table in short is going to be an array with linked list as we'll soon see here's the array。

 26 pointers to nodes So I'm going to give myself an array of pointers that is going to store ultimately a whole bunch of person objects like this。

 So for instance here's a cha star name cha star number as we've discussed in the past representing a person。

 these are the pieces of data I might want to store in this data structure。 However， let's simplify。

 let's not worry about the phone number because we're not going call any one to but for a linked list of persons I'm going to need to store let's say the person's name。

But also a pointer to the next such name to the next such name to the next such name。 So again。

 I'm just the leadinging number is being unnecessary detail。

 But if we're gonna have an array of linked lists， this is our new definition of node for this part of class。

 whereby it's not for a tree。 It's now for a hash table。 And we'll see this in action now。

 Here is my array of size 26。 I drew it vertically。 But who cares。

 These have always been artist renditions thereof， it just fits nicely on the screen this way。

 This is location 0。 This is location 25。 So any a names should end up over here。

 Z name should end up down here and so forth。 Let's just generalize this away as letters of the alphabet for clarity。

 That's where all the names are gonna go。 So hopefully Mario here， Luigi here and everyone else。😊。

So what are each of these squares， They're just pointers to nodes。 initially all know all claim。

 But as soon as I insert Mario into this so-called hash table。

 I'm not gonna to put him literally here。 I'm going to create a new node in memory。

 put Mario there and then stitch it together because if I get another M name。

 I'm gonna stitch it together and together and together again。 So， for instance。

 here comes Mario into this data structure。 So this is a pointer to a person structure。

 Here's Luigi and here's a third character as well， Peach。 That's all working out great。 dot dot dot。

 there's a whole bunch of characters in the Nintendo universe。 Here's a lot of them。 Unfortunately。

 especially if you're a fan。 there's also other names that do start with M and L and other letters of the alphabet。

 So we're poised to have what we're gonna call collisions。

 which is a downside of using a hash function。 If you're going from something infinite to something finite by definition。

 you're going have a heck of a lot of potential collisions somehow， multiple M names。

 multiple L names and so forth。 So we've got to mitigate this。😊，HowWell。

 if you meet someone in the real world whose name happens to start with M and you already are friends with Mario。

 Well， you could delete Mario from your phone and put that new person there。 but that's kind of dumb。

 you could clobber the value that is。 or maybe you put the M friend here。 And when that fills up。

 you put the M friend here。 And then when you meet someone else whose name starts with M。

 you put it here。 But then it justs into this mess at which point now there's no rhyme or reason as to who is where itves back into something linear。

 you have to search the whole darn thing looking for M friends just because you ran out of space where you want it。

 So here's the beauty of mashing together in array with a length list you hash the name to the intended location like box 12 here。

 And then you just start stringing them together in a linked list。

 and hopefully you don't have too many of those collisions。

 but at least now you don't have to delete or make a mess of the data structure。

 So here's another bunch of names3 starting with L Here's a bunch for the others letters of the alphabet and it's just a It's an array now of linked lists。

 This then is a hash table。 So the。To consider now， is this better than an array。

 I this better than a linked list。 Well， I dare say it's better than a linked list。

 because if it were a linked list from a to Z， what would be the running time of searching for anyone spoil a big O of N。

 because even if it's alphabetically sorted， You got to start at the beginning and go all the way through the list。

 potentially define someone like Zelda whose names starts with of course， Z。

 But here we have an array of linked lists。 So what's really the running time here。

 It's not quite as bad as N steps。 Because if you assume a uniform distribution of names such that the world of Nintendo。

 maybe has as many M names as L names as a names as B names。

 you could assume that there's a bunch of chains， a bunch of linked lists here， chain together。

 But they're all roughly the same。 So maybe you have N names in your phone book this way。

 But these lists are only of size， there are only one 26 of that length。

 because you've got that many names there， So what's the。😊，Running time。 Well， ideally。

 we'd move away from linked lists with big O of N and achieve our constant time。

 But we have these collisions to worry about here。 So if we've got multiple M。 So just to be clear。

 whoops just to be clear， we want to get from big O of N to something constant time。

 but we're not gonna get to constant time。 if we've got collisions。

 If we've got three L names and a few B names and a few A names we can't just jump to that location and find the person we're looking for。

 So what's the fundamental goal Well， I think we want to maybe use a smarter hash function And here depicted is an excerpt from a bigger hash table that is a much bigger array that assumes that you're not looking at the first letter of everyone's name。

 but apparently what instead。The first three letters of the person's name。

 which just decreases the probability of collisions， because in this model。

 I dare say there's no one else's name in the Nintendo universe that starts with L I N。

 So now Li has its own location in memory。 and similarly for Luigi L U I。

 I believe is unique in the Nintendo universe So we don't have a collision。 Unfortunately。

 while this does seem to eliminate collisions based on this tiny example。What's the trade off？

Or what's the catch yeah？走啊。This is a lot more memory。 I mean。

 kind of hinted at the fact that I didn't even fit most of it on the screen anymore。 Here's L AA。

 Here's L U G。 But what about all of the other letters of the alphabet and the other combinations oft dot dot dot dot dot all possibilities。

 Moreover， some of these just don't make much sense at least in English or in the Nintendo world。

 I don't think there's anyone whose name is gonna start with AA or AA or AA or A or in so forth。

 We're wasting a huge amount of space to reduce the probability of collisions。 So that's fine。

 we might get constant time now， but at what cost。 Well， a heck of a lot more memory。

 And so this is one of the tensions when using a hash table is you want to come up with a good hash function that's maybe a little more sophisticated than the first letter。

 but not so wasteful that you need a crazy number of buckets and therefore a huge amount more memory。

 So really even with collisions， it's not quite as bad as N steps because technically。

 if you have k buckets or K is like 26 buckets or four in this case， technical。

If you do assume that the names are uniformly distributed over a through Z。 the English alphabet。

 well each of those linked list is gonna be hopefully no bigger than n divided by k。

 So n divided by 26。 But what do we know about higher order terms when doing big O notation。

 big O of n divided by K。 Yes， it's faster。 but asymptically， that is theoretically。

 you're still talking about big O of n。 So here's tension， though。

 like it's absolutely going be faster。 It will be like 26 times faster than a linked list。

 but it's still just big O of n because it's going to take an amount of time that's still linear in the size of the data set。

 So we seem to have strayed yet again away from our constant time search。

 So can we find this holy grail。 Well， we kind of can。

 if you let me spend just like a lot more space。 There are tries in the world。

 which weirdly is short for retrieval， even though we don't say retrival。

 But a try is a tree made out of arrays。 So at some point。

 computer scientists We're just like mashing things together。😊。

stein style like length lists and arrays。 and now we've got trees and arrays。

 You two can mash something together and come up with your own。

 but let's look at what a try actually is because it is going to get us that constant time grail。

 So here is the root of a try。 You can think of each node in a try as really being an array of values A through Z in the case of an English problem like we've been playing with here。

😊，And what you do is you treat this array as being indexed from 0 to 25 or equivalently a through Z。

 And you treat each of those elements as a pointer to another such node in the try。

 And what you do is implicitly store the names that you're storing in this data structure by going to an appropriate location based on the first letter in their name and then adding a pointer that represents the second letter in their name。

 adding a pointer that represents the third letter of their name and so forth。

 So what do I mean by this。 supposeose we want to insert toad。

 one of the characters from the Nintendo universe first。 if we count up where t is in the alphabet。

 this。😊。

![](img/a13647f57b55a63e0e45544ba0bcb12b_23.png)

Pointer here will be changed from null to a pointer to a new node that represents the second letter in toad's name。

 which is gonna be， of course， O。 then to insert T O A， we're gonna need another node。

 A is going lead me to D。 And for depiction sake， I'm gonna draw in green。

 even though this would actually be a boolean or something like that in memory that indicates that toad's name stops here。

 So in other words， this try in memory has four nodes now。

 Each of those nodes is essentially an array of size 26。

 but the word toad is not actually stored in the data structure explicitly， there's no cha star toad。

 but implicitly because the T pointer is non null。 the O pointer is non null。

 The a pointer is non null， and the D pointer is， in fact， null at this point。

 is the common technique here。This allows me to insert other names from Nintendo's universe like Tot。

 because I can continue from here to go to the e node to the t node to the t node again and then e node。

 which all again mark in green。 So you can even have names that are substrs or equivalent superstrs of each other by just having all of these various breadcrumbs along the way。

 where again， a non null pointer here to a non null to a non null to a null pointer here indicates that or it can't be null at this point。

 this is where we have to use a boolean， indicates that there is a name in this data structure that ends here。

 and there's another name that ends here。 Meanwhile。

 if there's a third name from the universe like Tom， same idea。

 But eventually we can start reusing some of these arrays。 whereby non null non null null。

 or there's a boolean flag here that says true。 a name ends here。 Now we're reusing that same array。

 So each of the nodes represents the Ih letter of the word or the name you're trying to store in the data structure and by playing around with null and non null and some boolean。

Can implicitly store names in this structure。 Now， it's way too pictorially difficult to depict lots and lots of names in this form。

 So just imagine your mind's eye that there's dozens， hundreds。

 thousands of names now in this data structure， but just more arrows in more arrays How do you actually look someone up in this data structure。

 Well， if you want to ask a question like is toad in this data structure or is toad it in this data structure or anyone else。

 you can simply start at the root node， as we would do for any tree and you hash on the first letter of toad's name。

 which gives you this location and you check is it null。 if not， T is implicitly there。

 So you follow that pointer here。 and then you hash the second letter of toad's name and O。

 and check this pointer and you follow that arrow。 then you check the third you hash on the third letter of toad's name A。

 and you follow that arrow。 then the fourth letter of toad's name D。

 and you see there's a boolean here， represented in green。

 That means toad is in this data structure and no。Notice what's。Subtttle here。

 It doesn't matter if there's three names in this try or 3 million names in this try。

 How many steps did it take me to confirm or deny that Toad is in this try。😡，1，2，3，4。

 which is arguably constant。 even though the names can vary at some point。

 there's no Nintendo name longer than what like 10 characters，20 characters， maybe 30。 I mean。

 there's some reasonable bound that is finite where there's never going be a name longer than that because Nintendo is never going to come up with a crazy long name for a game。

 And so you effectively have constant time for looking up T O A Tot Tom Mario， Luigi Peach。

 any of the other names we've looked at。 So this is to say a try allows you to ask questions like is toad in this data set or equivalently what is toad's phone number in this data set。

 because if you assume now that each of these pointers ultimately is not just a bull saying yes or no。

 but maybe it's an actual person structure with a name and a number you can store even data like that。

 your key value pairs where your names or your keys and your phone numbers are your values to make this more clear than here is a data structure。

 how we might represent in C each of these notes is not quite technically just an array。

 It's an array。Size 26， we'll call it children because it represents the children of that node of typestr node star。

 And then here， for instance， for simplicity， is that person's number。

 If we reintroduce numbers and want to store in this data structure， someone's phone number as well。

 So using that data structure and that kind of code。

 you can implement a try using something as simple as this initially your try is just a pointer to a node。

 one suchstruct， we can of course， initialize it to null to make clear that there's no names in here。

 But each time we allocate a node， we can then add another node， another node hashing on the first。

 the second， the third， the fourth dot dot dot， the last character in the person's name。

 allocating a node as needed， flipping that bully into true or false or adding their phone number as a cha star to indicate that we have then found them。

 And so of all the data structures we've looked at today。

Big O of one is actually achieved with tries。 And yet， curiously， for problem set 5。

 you're not going to implement tries。 You're going to implement hash tables that sort of Swiss army knife of data structures that like every programmer everywhere knows about。

Why， like why not use tries？Very often in practice， perhaps。Certainly can。But what's the trade off。

 perhaps？Yeah。It's a huge amount of memory。 Things have escalated since the start of class。

 added we started with one int。 Then we added an int and a pointer and int and two pointers。 Now。

 I'm proposing 26 pointers plus a boolean or a data structure called person。 I mean。

 it's escalating significantly and the biggest catch with a try。

 as you might have imagined with Toad and Toed and Tom on the screen。

 there's a huge amount of wasted memory just as we saw with a hash function potentially。

 but that can be reined in， as you'll explore in the problem set with a try。

 most of the pointers in those arrays are just null and unused。

 and it just tends to result and you're using way more memory to solve the problem correctly。

 but in a way that tends to slow the computer down and just waste more memory than is useful。

 That said， just as we started today， there are stacks in the real world。

 There's cues in the real world。 There are even hash tables in the real world。

 which you'll indeed implement in code for problem set 5 has anyone here ever had a salad from a restaurant called Sweet green and Harvard Square。

 Also elsewhere in the US one two of us three of us so not hard。😊，Imagine going to such a store。

 getting in a queue and staring at a shelf like this because what sweetgr and similar restaurants do when you order for pickup is they hash your salad into a shelf like this。

 and so literally in Swereen might you see some wooden shelves like this。

 this is the A through E bucket， the F through J bucket。

 the K through N bucket and the O through Z bucket whereby if your name like Main happens to be in one of those ranges。

 they will hash my salad and put it here but of course， even in the real world。

 there are some constraints and what can go wrong with this here， hash table system。



![](img/a13647f57b55a63e0e45544ba0bcb12b_25.png)

What can go wrong？Someone who's been there， maybe。What can go wrong， Imagine like the extreme。

 lots of values here， yeah。So there's no more space So And this has happened to me in the past。

 especially since sweetgr before adopting this system。 They used to put the A's here， the B's here。

 the C's here， the D's here and so forth。 And then someone at some point realized that they were very frequently overflowing the A's to the B's and the B's to the C's that no one was using Q or Z with any frequency。

 And so they were sort of wasting space and running out of space。

 So at some point that decided to literally remove most of the letters of the alphabet make the buckets bigger and fewer。

 So now it's very unlikely that you're gonna have so many Ks through Ns that you overflow the shelf。

 But this is in the real world， a data structure like we've seen today。 And so therefore。

 among the goals， even as arcane is things seem to be getting with all the pointer notation and de referencing this and that。

 really all we're doing in code is implementing real worldor solutions that other people have already come up with and translating them to a new domain And the very last thing you'll do in C this is indeed implement your very own spell checker whereby we' give you a very large file of all 100000 plus English words you'll have to come up with a clever and efficient way to load it up into memory and we'll give you。

😊，That will actually measure how fast or how slow your code is。

 how much memory or how little memory your code is so as to actually compare it against not just your own。

 but perhaps others as well。 So with that said one a bit early today， we'll see you next time。


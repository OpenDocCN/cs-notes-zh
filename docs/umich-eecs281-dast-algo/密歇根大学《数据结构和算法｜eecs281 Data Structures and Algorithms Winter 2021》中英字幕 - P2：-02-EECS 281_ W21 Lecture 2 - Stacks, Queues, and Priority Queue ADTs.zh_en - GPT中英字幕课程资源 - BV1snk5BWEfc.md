# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P2：-02-EECS 281_ W21 Lecture 2 - Stacks, Queues, and Priority Queue ADTs.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

Hello everyone， I thought I'd start just a minute early today so that I could show cat so this is Spencer who is one of our cats。

 he is a rescue cat， he is big on laps but not big on being held。

 he likes to be in a lap that is not moving。So he usually。

 if you hear me talking to a cat during lecture， he's usually the one he likes to come up and head butt my elbow and ask for attention when it's time to lecture。

So why don't you sit on your own chair and you can hang out with me。Okay。

 so today we're going to go on to lecture two。And I just noticed before I started that the slides are named a little bit differently from what the lecture title is like the PDF file has a slightly different name。

 but it's the right set of slides lecture2， and you can see in slide of the slides stacks and Qes is more in line with the title on the schedule of topics。

So you're going to notice also there's some blank slides in here like between topics。

 Professor Garin put those in when he made the Pewise lectures。

 the ones that if you look at a schedule of topics where it says playlists。

 these are the slides that he made for those with excuse me。

 the break points between each of the separate videos。

 so for the most part we're gonna to skip over those blank slides pretty quickly。

So we're going to talk today first about a little bit more about abstract data types which we mentioned last time also。

 and when we're talking about organizing data， we need to talk about really what are the valid operations that we want to do on this data。

 but we want to add things insert them， we want to often delete things。

 get rid of things that we put in the container and have some way to access what we've put in the container。

 some way to look at。And so an abstract data type is our interface。

 it tells us what this data structure will do。And then when we create a data structure， we implement。

The ADT and we have some we say here concrete implementation meaning there's really code behind it in some language now we're often going to talk about data structures and what they can do but and that's the theoretical side and it's good to memorize the theoretical side。

But we also like to talk about the details of implementing it。

Now once we have a data structure we can look at measuring performance。

 which is going to be our next couple of lectures coming up after this and we've got a little bit of a chicken and egg problem here at the beginning of the class because it's hard to talk about complexity if we don't have a data structure or an algorithm to analyze but we can't talk about data structures or algorithms without without having some knowledge of a bit of complexity so luckily you've gotten an introduction to complexity from 280 so we're we're going to be doing that soon we're going into any detail。

 yes you missed the cat but remember the lectures are recorded so after the lectures done and the recording is posted。

 you can go back and C CAAT。So when we talk about our design choices here。

 we want to look at when we put these things in memory behind the scenes when we make our implementation。

 are we going to use contiguous memory， contiguous meaning one element follows another in adjacent places in memory。

 and that would be something like an array or a vector。

Another different way to do it would be where the data is not necessarily contiguous in memory。

 but has some sort of way to connect it like with pointers。Now。

 when we talk about the runtime we want to look at。

How much time is needed to perform an operation Now， also， besides runtime， we also want to look at。

Space， how much memory is needed to do things， how much memory is involved in keeping this data structure。

 or if I perform this particular algorithm， do I need any extra space and if so， how much？And also。

 how does our size， how does our number of elements or number of inputs affect these？

Measurements of time and memory。And so we're going to look at complexity analysis and more in detail in the next couple slides。

But simple example here， if we had a linked list。And we want to enter excuse me insert a value at the end of the linked list。

 Well， I would have to follow the head pointer。So that would be one operation。

 then I would have to check， is this a null pointer no it's not okay so I can follow it to another one。

And really， that could be a two operations or one operation， I could say， well。

 really there was one to check if it's a null pointer and since it's not a null pointer。

 then I could follow it。And then I look at not at the end yet， so I follow it again。

Check the is a null pointer， follow it to the next one， is this a null pointer， yes it is。

And so then I can create a new node。I can put the value in there。And then I could change。

 I've got to make sure this points to a no pointer and then change that one to point here。

So it looks like it took us on the order of like six operations to get to here。

 so it took about six operations to get to there， follow the head pointer， is it nu。

 follow the pointer， is it nu， follow the pointer， is it no， Okay so that was six operations。

And then once I'm there， it took me another， create something， put the value in it。

 and change the next pointer， so it took me around。2 n plus3。

Operations follow a pointer is it nu follow pointer is it null follow a pointer is it null。

 so for every node I had to do two operations and then I had to do let's say three more operations to add the new node I've got to create a node。

I've got and if we say， hey， my constructor for a node。

 constructing a node always makes the next pointer a null pointer。

 that happens automatically when I create the node， but I've got to create the node。

 copy the value into it and change the pointer that points to that new node so that's where I got my 2 n plus three and we might argue a little bit maybe it's 2 n plus4。

Maybe it's not 2 n plus3， maybe we count the null pointer， maybe it's 2 n plus4。

 but when we look at our big O notation for this， we would say hey， this is big O of M。

 we get rid of the lower order constant term， so it doesn't matter if it's two or three or four。

 we get rid of the constant out front of the largest order term， we end up with our event。

So on our labs and exams we don't tend to ask you for this。

 what we're interested in is that because we don't want you to spend too much time worrying about is it 2N plus3 or 2N plus4。

 we want to get to the Big O event。So it's okay to disagree a little bit about the number of operations as long as we get the right complexity class。

Now， when we want to choose a data structure for our task。What do we want to look at？Well。

 we've got to have the right operations like I need a container that allows not only adding things。

 but I've also got to be able to remove things and you know。

 access them kind of is' an always sort of thing I didn't add it to the list here。

 but we can add access。To the end of it， so we always want to access。

 but for this particular one I might need the ability to remove elements。

I've got to have the right behavior and we're going to look at some examples coming up really soon like with stacks and cues so if I'm。

Creating a certain data structure I might need like if I'm having a stack。

 I've got to be able to actively moving， and if I'm creating a queue。

 I've got to be able to do things at data to take from one end and add to the other end。

And then there is the right trade offs for runtime complexities。Meaning。

What am I going to do most often and do I get a reasonable complexity for the things I'm going to do？

😔，And then the last one is memory overhead。That's not。User data。

So we're going to memory overhead a bit throughout the semester。 So when we say overhead。

 we're talking about the memory， that's not the data。 So if we go back a slide。

 my memory overhead here would be the head pointer。That next pointer。

 that next pointer and that next pointer， I've got a an amount of memory used up in pointers that is not data。

 so that's what we mean by memory overhead。Now， another thing we might have to。Do， hopefully。Okay。

 I'll pause here for a second。I'm like eight seconds behind you。Okay。

 so let's hopefully we're backup up because I'm seeing chats coming through now。

 so hopefully we're caught up。All right， so the other potential concern here at the end is limiting our interface to avoid problems。

 so if I wanted to keep。A container that was always sorted。So if it's always going to be sorted。

 I can't just allow people to insert things wherever they want to when I insert a new element。

 it has to go in a location that would keep it sorted。Okay， so for some examples here。

 if I was making a system to track orders out of fast food drive through where someone in the。

Inside can take an order over the microphone and type it in and then you drive up and you get it。

 well， that sounds like a cue， people get in at the back and they take from the food from the front。

If I was doing， oh， say I wasn't hadn't taken 2 anyone1 yet and I had to be a receptionist for a summer and answering phone calls。

 I might have to say， oh， well， the easiest thing for me is a stack because then I can just go line1。

 line two， line3， line4， line 3， line  two， line1 that's really easy for me but then the first person needs to wait longer。

So that a stack would work easy for me in my head， but maybe a queue would work more fairly for the so that no one waits a lot longer than others。

Oh， but what about if my boss's spouse calls or my boss's child calls。

 maybe I should get them through right away and that would be something like a priority queue。

 which we're going to talk about later on。Your to do list。

 so things you need to do like right now be at lecture。

 start make sure you're working on project zero， ask questions about project zero。

 get your IDE working， things like that。But then when a project comes up。

And you're working on your project and then you go， oh my gosh， my English papers due tomorrow。

 that's more like a priority queue as you remember that things are coming up。

 the closer they are to the due date， the more important they are。

So we're going to talk about that priority Q idea later on today。Okay， so basic idea of a stack。

So a stack supports last in first out， that's what LO means， last in first out order。

 so the last thing in is the first thing out。And we put the methods here。

Are the consistent with the STL。 So if we look at like standard。Cool， coal and stack。Data type。

 which is a templated data type， that's what the angle brackets mean。

 these are consistent with standard stack。So push adds something to the top of the stack。

 pop removes it without looking at it， pop just gets rid of it。

Top allows you to look at something without removing it。

And then size and empty are helpers that let you look at the number of elements or is the stack empty or not and there are other things besides this。

 you know it's got dynamic memory behind the scenes so it's got a constructor destructor copypy constructor overloaded operator equals。

 all kinds of things like that。So， we can。Use a stack to produce useful things like an undo feature。

In an editor or a back feature in a web browser， but that doesn't give us an easy way to have a redo in an editor or a forward feature in a browser。

 so that would take a more complicated day structure。

It's also the way that function calls happen in C++ we talk about the。

Memory stack or the call stack when function calls happen， they go on to a stack。

Now we're going to look at。Implementations here， so one implementation is we could have an array or a vector behind scenes。

And I keep a pointer and that right here， my top pointer is basically a pointer to just past the last element。

So an empty one， an empty one while I might have a base pointer and a top pointer that are both null pointers。

It could also be empty if I've got a block of memory here。I could have my base pointer。

And I could have my top pointer。Point to the same place， that could also be an empty container。

Now when it says push， it says， okay， if needed， allocate a bigger array and copy data。

 we'll get to that in a minute， let's do it， let's assume that there is room and it says okay。

Step two is add a new element at the top pointer and in the top pointer okay。

 so if I push another value， so if I did a push operation。

 I'd put a new value in there and I'd move the top pointer over。And then if I did another push。

 I'd copy that piece of data in there， I move the top point over。

And now I've got to have some way to be able to detect that I am out of memory。

So I've got to have some other piece of data here to tell me。How big is my block of dynamic memory？

How big is that block of memory， So I need something like the。Capacity， which would be five。

Now let's go through the other operations and come back to the push so P says we just decrement the top pointer。

 we don't get rid of data， we don't reallocate the block of memory， we just move the top pointer。

If someone says， I want to look at the top， we say take top point or minus1 and dereference that and let them look at it。

If they want to know the size， I just subtract base pointer from top pointers。

 so I do top pointer minus base pointer， tells me how many elements are in there。

Empty is easy if base pointer equals top pointer then I'm empty。

But the capacity is important to know if I'm full if I need more space or not， so right now。

 if I was to ask it what is the size， it would say five or would do the subtraction of pointers。

 and so when I need to check this if if I need to allocate more space。

 I really am checking is the size equal to the capacity。If the size is equal to the capacity。

 I have to grow it。Okay， so to grow that。What we would have to do。

 it says we would have to allocate a bigger array and copy the data over。

So let's copy a bigger array。Okay， so I copy a bigger array or sorry I create a bigger block of memory。

 then I copy the data over so I copy the blue one， the oh gosh。

 I'm colored blindd Ive forgot check my colors here， I think red one， yellow one。

 the two others I copy those over。 Now this description if needed to allocate a bigger array is not quite complete。

 there's other things that we need to do here in this step one of push。

I've got to do two other things。I've got to delete the old block of memory because if I don't do that。

 I'm going to leak memory。And I've got to change the base pointer and the top pointer。

Base pointer is here， top pointer。Is now over there。

And now I can move on to step two of putting that new element in there。

So now I can put that new element in there and move the top pointer to just past it。Okay。

 so down at the Bobman asks us how many steps for each of these operations。 Okay， let's skip push。

 we'll come back to that in a minute。 So pop decrement a pointer， that's all of one。So O of。

 I'm going to make an O of column here， I don't have a lot of room， so pop is O of one。

Top is a subtraction and de referenceence that's all1。Size is just a subtraction of pointers。

 That's over of1。Empty， I just have to compare some pointers。 That's over one。And now for push。

If it's big enough， so step two， let's do step two first， that's the easier one。 So in step two。

 I copy the new element and I move the pointer that's over of one but。If it's full， step1。

 I've got to。Alloccate a new block of memory。Copy， end things over。

Then I've got to delete a block of memory， move to pointers。 So I've got a constant amount of work。

 I've got a。Create a block， delete a block， moot， change a pointer， change a pointer。

So it's really it's4 plus M。Which is really a of。嗯。So this one's O of N。

 if there isn't room and O of1， if there is room。Now we're going to have to come back to this when we talk about complexity analysis chicken and egg problem here。

 so we're going to have to come back to a better analysis of this and something we call amortized analysis so most of our operations are0 of1 push is sometimes O of n but if you think about it I grow from five to 10 then I can push five more elements before I have to grow again。

If I grow from 10 to 20， I can push 10 more elements before I have to grow again。

So really the growing doesn't happen super often because every time I grow。

 I double the size I make it bigger， means it's going to be even longer。Until I have to grow again。

So most of my operations are basically going to be o of1。

 except on those rare occasions when it's full and we have to grow it。

 so we'll come back to a better analysis of this particular case later on。Okay， what about？

If we did this with a linked list。Now， a singlely linked list would be sufficient to do a stack。

 and it's not just sufficient， it's efficient。Now I'm going to have to keep the size。

 so I'm going to have to keep a head pointer and I'm going to have to keep the size somewhere if I don't want the size operation to take too long。

So we look at our different operations here， push says insert a new node at the head pointer and implement the size So when I want to add a new node to this。

Stack version about using a linked list， what I've got to do is I've got to create a new node。

Copy the value into it， make it point to where head pointss。

 and then change head pointer to point there。So that's what I have to do and I'll always do that I always create a note if I need one and then pop says I've got to delete the node at the head pointer。

 I've got dec the size， and I also have to change。The head pointer。

So I've got to change the head pointer obviously to point to the new head of the linked list after I'd delete a note。

Someone wants to look at the top， I just dereference the head pointer and look at the data there Well really it's not just dereference head。

 it would be more like head。Pointer。Arrow， let's say it's called data。

 weve got to look at the element inside the pointer。

 but still that's basically a dereence of a pointer， so we've got to look at what it points to。Size。

It's easy we just return that size variable。And empty。

 I can check if the size is zero or I can check if the head was a null pointer。

 either one would work。Now like I said， an alternative approach would be to not keep track of the size and let's look at our operations either way。

So push， I got to create a new node， copy the data， change the head pointer， that's all one。So oh。

 I who， that too many parentheses。So O of， so o of one for push， O of one for pop， O of one for top。

 O of one for empty。 If I do the check if the head is a null pointer。

 it's always going to be o of one。Now， the size would be o of1 if I have a size or it would be o of M。

If I don't have a variable for the sides。So having that variable for the size。

 I pay a little bit of overheading memory， a constant amount of overhead。

A piece of memory that is not the user's data。But it makes my size operation all one， which we like。

So we'd probably want to go with that implementation。Well， true。

 someone said in there we could have added at either end。

 I was sort of planning ahead because I wanted it to be efficient。 I said， hey， for a stack。

 let's add at the head， let's delete from the head of the list。When we get to a queue。

 we'll have to do something different， so that's coming up。All right， so actually and it says here。

 which one is more efficient， a linked list， well， here's our number of steps laid out。

And they're pretty。Similar complexities， the only difference is push， it's constant most of the time。

 but it's linear when we have to resize and like I said。

 we're going to talk about amortized analysis coming up soon。So they're pretty consistent on time。

On memory， though。Okay， so I say the constant factor for the complexity is lower for vector。

 so the constant factor something tends to be a little bit lower for this。

Liinked list also or even the linked list is going to have overhead because all of those next pointers are going to take up space。

 so the vector approach for this is pretty good。Now the nice thing about the。Liinnkked list， though。

 is that we never have a node that's not used in the vector， as we grow by doubling。

 I could be at like six out of 10。Or really if we've grown by doubling。

 I could be at five out of8 would be a more reasonable place to get so if I was at five out of8 I might have some wasted space。

 but in the linked list version I've got all those wasted pointers。

So this is why the vector approach is nice if I can preize it if I know exactly how big it's going to need to be。

And that's mentioned in the lab or project zero， sorry that's mentioned in project zero about vectors and sizes。

Okay， now if we look at standard stack。So the standard stack， the STL stack。

 you just include stack to get access to it， you can choose the underlying container。

 but usually we don't， we usually just let it do its thing and。

What happens is behind the scenes by default， there is a deck。

 and we're going to talk about deck in a little bit。 But you can also tell it， hey。

 I want you to make me a stack of integers that behind the scenes is really a vector of integers。

 or is a standard list of integers。 and standard list is doubly linked list， it says， et cetera。

 So that's when we get to when we get to deck， which we're going to look at today。

 we'll learn a little bit more about what a deck is。 But the people who implemented this the SL。

 they chose deck， they said that's the best way to do it。

 Now's more complex data structure we'll talk about in a little bit。Okay， those our stack Q。

So our Q supports PIFO， which is this first in， first out。So we have let's go to the examples first。

If you're waiting in line at the dorm， you know， in normal times when we would be out in person getting food with other people around us。

You know what that's like or hope you can still remember that waiting in line for lunch or another example is like going to a movie theater or waiting to get your tickets。

 get you enter at the back of the line， you buy your ticket at the front of the line。

If we had a playlist and we added songs at the end of the playlist like it's playing right now and I say。

 ohh， I got that reminds me I gotta get another song by that artist and add it to the playlist。

 it might get added to the end of my playlist and I'll get to it as the playlist finishes。Okay。

 so operations and these again， are taken from standard Q。

So standard Q operations are very similar to the standard stack operations except for two things。

Where they go， so push adds it to what it considers the back and pop removes it from what it thinks of as the front。

The instead of a top member function， there is a front member function that lets you look at whoever is at the front of the queue。

 it's got size and empty。And it also has， like I said， other things like。Constructor， destructor。

 copy， constructor， operator equals， etc。So we've got all those operations because it's doing dynamic memory behind the scenes。

So if we want to implement a Q， so here's one way to implement a Q would be with a circular buffer。

 and I'm going to have to do another example。 It's not a good example of the circular buffer isn't in the slides。

 We actually let's let's stop part way through and I'll give you an example of the circular。

 What do we mean by that。 So we start out。 we've got our front and our back index。

These could be indices， they could be pointers。It doesn't matter much。And we've got a size。

 so I've got a block of memory。I start out when it's empty， front and back are the same size is zero。

 and if I push something。I push it at the back and the back moves over。

 that's very similar to how the stack work。So we put it there and then we move the pointer or the index。

Then if we push again。We put it there where back points to or refers to， and then we move it。

 and then we push an element， and we are off of the end， and it's full。

 We're going to have to also remember。The capacity is equal to three also。

 we're going to have to remember that。So that's how I tell that it's full。Is that back index is now。

Three and the capacity is three， oh wait， that's not good。 let's not do that。

 capacityity is three and size is three， it must be full。So here's where circular comes in。

 don't go forward in the slides here， how do we what do we mean by circular Well what if。

 what if I did some new operations here， what if I did a pump？Okay， if I did a pop。

 I would move the front index over and I would set the size to two。And now I say， I want to push。

I want a push， well the size is not equal to the capacity。So I've got somewhere to put it。

So if I've got somewhere to put it， what I've got to do is I've got to say， hey。

 the back index really shouldn't be off of the end， the back index really means it's here。

 let's put a new element over the top of that。Green one。

 and then let's move the back index over and move the size up to three。

Now the back and the front are the same but it's not empty anymore。

 they started out the same because it was empty， but just because they refer to the same index doesn't mean it's empty so that's what it meant by circular。

 if there is room， we will wrap around to the beginning and use those popped locations at the beginning。

Now， if it was full and we wanted to push， then we would have to grow it。Now。How do we grow this？

Well， we could allocate a new block of memory。Let's make it。Twice as big。Now， do I want。The front。

And the back to both be in the middle of this thing， that wouldn't really be good。

 How about if I put the。Blue1 over here at the front。 So there's the blue1。 Here's the red one。

Let's assume we pushed a push yellow。So I pushed the yellow one， the yellow one would go here。

 and then I would have empty spaces after that， and this would be the front。

So front would be here back。woWould be here and then if I wanted to push。A， let's say an orange one。

 then I would put the orange one here and I'd move the back over by one。And also。

 I would have to move the size up to four and the capacity up to 6。

 so the capacity would go up to 6 when I allocated。

 the size would go up to four as I finish adding that new element。And then remember。

 we've also got to delete that old block of memory。Oh it's brown， sorry。That's me。

 I warned you last time I'm colorblind。Sometimes I get them right， sometimes I get them wrong。

And besides Brown wouldn't have worked Ad either because then blue and brown both start with B。

 so that wouldn't have worked well， let's pretend it's red。Okay， now。

 so that was an example that wasn't quite on the slides。Now let's go back to the slides here。

 so the slides say what if it was full and we pushed， hey， heres here's the thing I just did。

 I copy over to the new block of memory。We change the capacity。Capacity is equal to6。

 the size is equal to4， and then we add the new element。And then if I pop。

 I would pop from the beginning， pop from the beginning， and then if I wanted to。

 I could push four more elements。I think I should probably。In the future。

 I think what I'll do is I'll redo these slides and get rid of the。

Just colored dots and just put like letters or numbers there， like 1，2，3，4， ABC D。

 that way the colors wouldn't matter。 And I can just say A， that would be better。Okay。

 so let's look at our complexity of these operations。Okay， so it says in push。

 if the size is equal to the capacity， then I've got to realcate a larger array。

 copy over the elements。 unrolling as I go。 remember， unrolling is what I did with the visual where。

 hey， front used to be at index 1 in the old one but I want front to be at index 0 of the new one。

 So I want to go from the front to the back。In line in the new one。

 So I want front to be at index 0 in the new one。 And then also obviously。

 we've got to delete the old block of memory。Regardless of whether step one happened or not。

 we go on step two。So if size was not equal to capacity， we go on to step two， if it was。

 if size was capacity， we do step one to make the bigger block， copy things over， fix the indices。

And then we move on to step two， which is we increment the size， we increment the back index。

 or sorry， we put the value at max index， we increment theize and increment back index。

And it says wrapping around。Either one as needed。So wrapping around what that means is。Over here。

 when I got to the point where back pointed to the end， let's not do that。

 let's never let that happen if back if incrementing back moves it off the end。

 let's move back back to the beginning and we can do that with。Remainder on division。

So I could just say something like back。Is equal to back plus one。Majulo。The capacity。Actually。

 it's not module， it's remainder of division， so remainder when divided by capacity。

 So if we go zero to 1， one to  two，2 to 3。The modo or remainder arithmetic gets us back to zero。

So that's what it means by wrapping around either as needed。

 we're not going to have a back index that points off the end。

 let's move it with the remainder back into the valid index。

So pop is we increment the front and decment size front is we just return a reference to that element。

Size， we return size empty， we check if the size is zero， so our big O over here。Oh，1，1，1，1。One， if。

1 for step 2。 So step 2 takes one operation， but step 1 could take n in operations。

 So the whole thing here， this is where we get that0 of n sometimes0 of1 most of the time。

 That's what we call the amortized o of one。So we'll get in the future lecture。

 we'll look at how to do that amortized analysis。Okay， linked list。

Now it says here Sly linked is sufficient， we don't need a doubly linked list to make a cu。

 but what we do need， we really do need a tail pointer。Now， with pointers， we don't need capacity。

Because we only create a node when we need it。 So with this one， we're going to need a tail pointer。

 but we don't need a capacity。So it says pushush says append a node after the tail and in at the sides。

And then when we pop， we will delete a node at the head pointer。

 and obviously we've got to move the head pointer and we will decrement the size。

And this is the efficient way to do it。 could we。Push at the head and pop at the tail， yes。

 but it wouldn't be efficient。So we went with the more efficient way of which one and it also sort of makes sense with our idea of the Q。

 you get in line at the back of the queue， you get out of the front of the queue。

So the head and tail here kind of makes sense with not only keeping it straight in our mind。

 but also making it efficient。So then size， we just return the size variable。Empty。

 we just return his head equal to a null pointer。And then our big O complexity for these。

Is going to be 1，1，1，1，1， or n if we don't have a separate size variable。

So we really want to deal with that o of one and having that separate size variable。

It's a little bit of extra memory for that some type of integer variable to maintain size。

 it's a little bit of extra work with every push and pop we've got to increment and decrement the size。

 but we never have that hey， how big is that Oh Oer let me count all million of these nodes for you。

So it does make the size a little more。Attractive to someone using our data structure if the size operation is over1。

So then we've got our comparison again。And this。Complexities。

 the time complexities in this table are exactly the same as our。呃。Stack implementations。

And the same notes below it basically， the linked list has the overhead of the pointers。

 The constant factor is a little bit lower for vectors。

 It turns out vector is a pretty good choice here。 or sorry the。

The global vector here and the wrapping around works okay。

But it is a little bit confusing to look at it。The Q inside of a vector with the circular buffer rotating around is a little bit hard to picture。

So in the STL， when we include Q， we get access to the standard Q， we can make one by default。

 It's based on a deck again， we'll look at that it's coming up really soon。

 We can also tell it to make us one on a standard list。 remember standard list is a doubly linked。

And it's got a ahead。A a tail。Over。Oops over。So it's got O of one head and tail operations。

 so you can do this in a doubly linked list。You can't do it in a vector。Because。

The standard Q has no idea of circular。Standard Q just says， hey。

 I want to push at the back of the underlying container and I want to pop at the front of that underlying container。

 and vector doesn't have a pop front， It's not efficient to do it， so vector doesn't have it。

Vectctor does have a pushback， but it doesn't have a pop front。

 so it won't allow you to say I would like a cu that's based on a vector it won't even compile。Okay。

 that's Q， all right， deck。So DAC DEQUE is pronounced D。Happily， this has nothing to do。

This has nothing to do with a eucur deck， so when that was done， that was 28。

 so in 281 when we say D， we mean this， the double ended Q is what it stands for。Now。

 if you look up these data structures， that's as far as I'm going。

 I promise I won't say I won't mention you here again this semester。

 so when you look up terminology online，You might see things。Called DQ， and。

DQ and NQ are different words for P。And push。We like to stick with the simple ones push and pop。

 it's consistent with the STL， it's less confusing， but if you look it up online。

 you might see those terms DQ and NQ。But we're going to stick with push and pop。

So now the STL includes standard D。Yeah， as I， as I。Type so there a there's an include file for it。

 there's a standard colon colon deck， and it's an implementation of a deck。

And it's generally behind the scenes it's based on a growable collection of fixed size arrays。

 so this is a place where we're going to step off the deep end a little bit into the guts of the STL you do not have to know this for the exam how it works what you do need to know is the operations so you are going to have to know the operations because excuse me。

We are going to have you use a standard deck in Project one。

But you don't have to know how it works behind the scenes。

 you just have to know what you can do with it。So standard D has six major methods。

 all of which are O of1。We have push front， pop front and look at the front so we can add at the beginning。

 remove from the beginning， look at the beginning， we can push and pop at the back and look at the back。

Size and empty， it's got other things like you copy constructor， etc ce。And it's also got O of one。

That's what constant time means，0 of1 the operator square brackets。So， you can。

Add and remove from both ends， and you can do o of1。 you can jump to index I in O of one time。Now。

 if we wanted to implement a deck， the first part up to this line up till there would be pretty easy to do。

If we wanted to implement the deck other than the operator square brackets。

 it would be pretty easy we could do a。Doubly linked list or circular buffer would be pretty easy。

But it wouldn't be super efficient。 The circular buffer would make the growing would kind of inefficient。

 The doubly linked bist would make the square brackets inefficient。

So if we didn't care about being super efficient， we could do it with a DoE length list with a head and tail pointer。

Um， or we could do it with a circular buffer， it wouldn't be as cool as the way the STL does it。

So the way the STL does it， there are two separate pictures here taken from。Two different sources。

 So this one， the top one is the left and the bottom one is the right。

 It's two different views of the same idea。So the big idea is at the top level here。

 I've got something that's like a vector。And the vector contains pointers to fixed size blocks of memory。

Now notice it says here that we've got a shift of three and a chunk size of six and let's look at the second one because it's got a little bit more detail。

So the chunk size of six meanss that， hey， all of these are size six。

The shift equal to three is referring to how many are empty at the beginning。

So how many of them are empty at the beginning？And we're also going to have to keep track of like。

 what is the actual size， like how many elements are in here， So 6， 24， 25， 26 trans08。So this one。

 the size right now is 29。 That's how many values are actually in there。

 So if you count all those little blocks。Graish blue。Blocks， they are the filled ones。

 the colored blocks on the right， there's 29 of them。So the idea here is that。

If I need to grow at the end， well， hey， if this was a vector。

 think of it like if you look at the left one， the left one's a little better this way。

 the left one has the top level has unused at the beginning and it's got unused at the end。

 So if you need to add another chunk at the end， you add a chunk and you allocate and just put it in there。

And then if you need a new chunk at the beginning， you just put it in there。 Now。

 if it gets completely full， then we've got to grow the top level vector。

 We've got to grow the top level vector and leave some blank pointers at the beginning and some blank pointers at the end。

Remember， the blank portions at the beginning and end over here， remember。

 I've got to have o of one push front。And I've got to have o of one。Push back。

I need over one push front， I need over one push back。So that's what this accomplishes now remember。

 this slide is not going to be on the exams at all。

 maybe a little bit on the lab because you'll have time to talk and ask questions and stuff。

 but this internal details will not be on the exam I promise。Okay， so it's， I hate。

 I just hate saying， hey， there's deck and it's magic。How it does things。

 so I'd like to give you somewhat of an overview， but I don't want to get bogged down in the details of this for three hours。

In the code in the STL， remember if you look at my video， even if you have a visual studio。

 look at my video for where I said if you couldn't get the right location。

 go to this the last part of the visual studio， it tells you how to turn on debugging of the STL and an Xcode you can just do it。

 if you really want to look at the guts of the STL。

 you can always just make sure that if you're in visual studio。

 you got to have library debugging turned on， but then you can just step into you can step into things like vector pushback。

And I've done it， I've looked at a lot of the STL code， and none of it scares me like deck does。

I've looked at the vector implementation， linked lists， hash tables。

All kinds of different things and。None of it is as ugly as the decks that I've seen。 So let's。

 let's just call it done here。 If you want to come to office hours with questions。

 I'll talk about this more。 But like I said， since this is not going to be on the exam。

 we don't want spend too much time on it。 There's also。

 I've got links in the slides to two more sources， go read both of those sources before you before you come in with more questions。

 they will answer a lot of them。Okay， so the nice thing about the standard deck。

 this is what you need to know about it。It's got stack and Q like behavior at both ends that's all of one。

It's got accessed with square brackets with0 of1， that's what you really need to know about deck to be able to use it for the project。

Okay， that's done with deck。 Okay， what's a priority cue。

 This is something you haven't heard of before。 So a priority cu。

It's kind of like a cu in that you push things in and you can look at who's at the top。

But the order that they're inserted doesn't matter。

What matters is who's at the top is the highest priority。

 and you get to decide that by your ordering of the priority queue。

So you can look at the highest priority element， you can pop the highest priority element。

Now let's look at a little example before we talk more about it。

 and we're also going to talk more about these when we get to project two。But we needed to do。

 we needed to do the stacks and cues and talk a little bit about the deck before Project one。

 So we've got all these chicken and egg problems。 So we're going to get to complexity in detail next。

 And then when project。One is out， which is next Tuesday it's going to be about。

 I think I've got it set to auto revealal at 1201 a the project spec will become available if I remember to log online on Tuesday。

Monday night， Tuesday morning， as Monday becomes Tuesday， if I remember to log on。

 I'll turn on the autograder right at midnight， although most people probably won't need it much the first day。

 but I'll make sure that we get equal hours no matter what time zone you're in。

So you're going to need D for project one， we're going to need priority cues for project two。

 but since we're already talking about stacks and Qes， let's talk about priority cues。是。

Here's a simple example， we have an emergency call center and there are three levels of priority and zero here zero is the highest。

Sorry， my keyboard opened up on me。 Okay， so my highest priority is zero。

 So there's three priorities of call of calls that come in。

 And what we're doing for this example is we're pretending that one person is in charge of answering phones and another person is in charge of sending people out so that one person doesn't have to do everything at once We want to get the calls into the system。

 we want to get those people logged and we want to go answer the next call and then we want to be able to。

Dispatch people out there。 So a level 2 call comes in。 This is a very low priority call。

 This is something like。My cat's stuck in a tree， so I answer this phone， my cat's stuck in a tree。

 okay， I put that in the system， type it in， here's your address。

 move on to answer the next call Another level two call comes in。

And let's pretend the dispatcher is finishing a previous call。

 so while the dispatcher is getting someone out to the previous call， I answer the phone。

 cats stuck up a tree， cat stuck up a tree and I answer a new call which is a priority one。

 priority one could be something like， you know there's a strange person walking around the backyards in our neighborhood at night。

Okay they're not doing anything yet， but this is definitely a more priority than our cab in the tree。

 so I put that priority one call into the system and still I'm answering phones。But then， hey。

 the dispatcher finishes what they're doing， they look， there's no priority zeros。

 there is a priority one， they dispatch it。And then the phone rings， I answer it。My house is on fire。

 okay， let's put that and that's priority zero and then。

The dispatcher finishes sending out people to the suspicious person walking around the neighborhood and dispatches the fire truck to go to that house that's on fire。

The cats are still tuck in the trees， they're not going anywhere。

 we will get to them soon when when the fire is put out， the fire truck will go get those cats。

So that's an example if， if we had a fixed。Number of priorities。

If we have a fixed number of priorities， a prior queue is pretty easy。

What I really need is what it looks like here is it looks like an array of linked lists。

And so when there's a fixed number of priorities， it's really easy。

It would probably be good to deal with it in the order that they came in， so I think I did what I do。

Yeah， so I added there。 So we would probably want to take off the back there。

 So we'd probably want to have a。Instead of an array of linked list， let's have an array of cues。

So if we had an array of cues， I just wanted to draw this easily， but yeah。

 if we had like an array of cues， then the first cat would get helped first。Okay。

 so now let's look at just our overall things we want to do。So things we want to do， we want to。

 this is not a fixed number of priorities， this is if I don't know the number of priorities。

 what have I got to be able to do， I've got to be able to add someone to the priority queue。

I've got to be able to pops the highest priority element。

I've got to be able to look at the highest priority element。

 one thing you'll notice here that's different from stack and Q。Is this is a cost reference？

You're allowed to look at the top element of a priority queue， but you can't change it。

Because if you looked at it and changed it， if you changed what determined its priority。

Maybe it shouldn't be at the top anymore。So with a stack and a queue。

 you're actually allowed to look at the front of the queue or the top of the stack and change it。

Because it's not moving。But with the priority queue， you're not allowed to change。Who's at the top？

Now there are ways around that， we'll talk about that later with Project two stuff。Size， empty。

 no reveal revealed a number of elements and is the container empty or not？Now。

 some examples on there like hospital cues for arriving patients， you know， okay， you've got a。

pain in your chest， you're pretty close to first there， you've got a gunshot wound。

 you're even faster helped you've got a two degree fever。

 you can wait I'm not sure why you're at the emergency room。

 but we'll get to you after we take care of these more critically injured people。

Now there's lots of ways we could implement a priority queue， All right。

 so one way would be if we had an unordered container。So if we had an unordered container。

 meaning we just throw stuff in there。I just have to get it in， so adding the push operation。

 you just call these push and pop。So push and pop are。Push is really easy for an unordered one。And。

Pop is pretty hard because I've got to look at everyone in there to determine who's the highest priority。

And what if I wanted to look at the top， which add another column for this top would be conceivably O then also because I've got to look at everyone to know who's the highest priority。

What about a sorted sequence container？So it is sorted at all times if I push， it must stay sorted。

Now， how long we're going to break this linear here down， we're going to break this into pieces。

 how long does it take me to find the right place to put someone in a sorted container？

So sorted let's。Sored push。Step one is I've got to find where to put it。

I've got to find where to put it could be what complexity， what can I do here？I can do a。

Binary search， which means it's O of log again。But afterwards， I have to do something like a vector。

Insert。And actually， vectors have a dot insert member function。

Which is O of n because to put it in the middle， other elements have to move over to make room for it。

So finding where to put it is O log again， but putting it there depending on where I am， right？

If I'm adding it at the end， it's O of1。 If I'm adding at the beginning， it's O of N。

 if I'm adding it in the middle。It's all n， so it's over n average。And worst。

So that's why the whole thing is O event。Because and that's our average case and our worst case。

 So it takes O n time to。Get it into that container。Now， the。

 it says the remove is constant if I'm careful， if I'm careful。

 if I keep the highest priority element at the back。The vector pop back is0 of1， that's constant。

Also， if someone wants to look at the top， that's allvo also because I know hey。

 highest priority elements's at the Mac， here， I'll show it to you。Now a heap。

 we haven't looked at heap yet， that's going to be a couple more weeks， this is a heap a binary heap。

A binary heap is a data structure we're going to look at。

 which gives us logarithmic push and logarithmic pop and O of one top。

So thats that one's a lot better than the others。 And if you think about how we use a priority queue。

 right， I'm going to be putting things in and eventually hopefully everything that I put in is going to come out。

So both of these， these top two， have a life cycle that adds up the push and the pop。

 add up to linear。So putting something in and eventually taking it out is a linear operation。

Whereas this one， putting it in and taking it out， adds up to logarithmic。

So that would be a much more efficient data structure。So we're going to look at binary heaps。

 we've got a whole lecture about binary heaps and how to use them and what we can use them for and how to implement them efficiently。

Now， if we had a small fixed number of priorities， like with our call center here， two slides ago。

 if we've got a fixed number of priorities， then everything can be constant。But in general。

 we don't have that。In general， we don't have a fixed number of priorities。

 the number of priorities are very wide open。Let's think about another use we could make of a priority queue What if our。

knowAgain， a normal semester when we're back in the labs。

 what if our printer had a priority queue instead of a queue and we gave higher priority to shorter print jobs？

So， you know， theres， there's a two page job printing and there's a 50 page job waitinging。

 you print one page， you get in as soon as the two page is finished， your one page prints。

Now that means that you don't have to wait for a 50 page job。

 but it also might mean the 50 page job type。Doesn't know how long it's going to take before it's done because people keep printing one and two and three page jobs in front of it。

So， that's。Nice for the short jobs， but not nice to the long jobs。So we could do it。

 but would it be a great way to do it I'm not sure。

 but there we don't know we don't have a fixed number of priorities because you know。

 there could be someone printing their 250 page PhD dissertation。Oh whoops sorry。

 I drew over the top of that drawing， so that's the that's the array of linked lists or array of cues。

That's for this one， if we've got a small fixed number of priorities， we can do that， but in general。

 we've got to do something like this。So those are the general cases。So the standard priority queue。

 by default， it uses standard less to determine priority。So by default， if we just say。

 create me a priority Q of integers， it will be a max P Q。

 meaning the highest value is the highest priority。

 So if I make a priority underscore Q of int and I push like， so I make a priority。Of itt。皮Q。

And then I push， whats speakQ， and then I push。3，1，5。 And then I say who's at the top。

 it would say 5 or and if I pushed if I pushed 3，5，1， then I ask who's at the top。

 it would still say5。 It's the highest priority。 The maximum value is the highest priority。

 If I want a min P Q， I could use a different font or I could use standard greater instead of standard less。

And if I don't have something like integers， I'd have to create a func or a function object to do the comparisons。

 and we'll talk more about how to do this later on when we need to do it。And so if we've got objects。

 we create custom fun doors， etc。Oh whoops， I forgot there is a slide for this。

So there's some slides for standard priority queue， there's how to create one。

 how to create one with a custom funk door。So there's how to create one by default with a type like T like integer。

 so this is a type T like T is something like integer。This is if we have anything else。

 we want any other ordering we have to do it like this。And there's also some standalone functions。

 the algorithm library says basically if you've got a fixed size container full of stuff。

 you can turn it into a binary heap， you can push heap and pop heap on this fixed size container。

So we get the priority Q by including Q seems a little weird， but yeah。

 Q and priority Q are all in the same include file， but then we get access to standard。

Priority underscore Q。 And there's some of the things you can do with it。

 And we'll do more examples of this when we get to project 2。Okay。

 the last thing we've got today is an example of using a couple of containers to。

Complete and a complex task。 sorry， stumble over that。 I need drink。啊。😮，Okay。So we're going to。

The okay， sorry， I saw a question there that I know the answer to right here。

 We need a vector for standard push heap and and or make he and push heap and pop heap。

 We need an underlying fixed size container with Oval on operated square brackets。

 so these could work on an array。They could work out a vector。They could work on a deck。

It's basically it's got to have all of one operator square brackets for that to work。Okay。

 so here we're going to show you something that's kind of complex task， the task is given n elements。

 I want to generate all of the permutations of those n elements。

And because I don't know how big M is。I can't use nested for loops。

Because I would need one nested for loop for every mmp。

 so we're going to have to have recursive function。

And we're going to use a stack and a queue to move elements around between them。

 that's why we' got the juggling graphic here， we're going to jungle elements between the two containers。

So here's our goal， basically， if I gave you the input  one， two，3。

I want to get the output and could we could make this a little easier and get rid of all the curly braces and the commas right so if I get rid of the curly braces and the commas。

And just put spaces between them， this gets a little bit easier。

So I just want to output the permutations so if there's if n equals3。How many permutations are there。

 there's six of them。If there was four of them。How many would there be sounds like how many permutations are there？

And factorial would be 24 if there's five of them， there'd be 120， six of them， 720。10 of them。

 approximately 3。6 million permutations， so this is of n factorial complexity。

It's going to take a few lines of code to get this done。It's not horribly long。

 but it's a little bit cryptic。Let's dive into this。

So the first thing I'm going to need is a helper function。

 the helper function is just for printing the contents。

So what we're going to do is we're going to juggle back and forth between stack and a queue when the stack gets full。

 we're going to print it。Now， printing a stack is a pain because。

If I want to look at anything other than the top， I have to pop the top off。

To look at the thing below it， so I had to make a copy here。

I had to make a copy of it to be able to print it。That's not very nice， let's skip this。

 let's do a better helper function。If， instead of a stack。If I kept a v door。The vector。

 I can iterate over it， I can use my enhanced for loop。Some people call it the range based。

Some people call it the each。So the enhanced for loop of the range based for loop says hey let's look at everything in that container and let's display that thing followed by space。

 so that's what this one does except instead of a stack we'll use a vector。

 we can still treat a stack as if it's a vector right I can push at the back pop at the back instead of the stack growing upward it grows sideways that's okay we can still picture that as a stack。

So we add at one end， we take from the same end。So that's our helper function that we're going to use to print it out when we。

everything is in the stack and here is the cryptic function。

So we're going to look at this one piece at a time。

 so we've got it templated because I don't know what you're going to give me a container of。

It's going to be a container of integers or container of characters， a container of strings。

 I don't care。 You give me a container of stuff。 I will display all the permutations of that stuff。

 which was why we had a template over here。 Also for printing out the elements of the vector。

 we're going to have a。Template and type there also because I don't know what you filled the container with。

All right。I'm going to。Have remember， I said we're going to have a recursive function。

 so here's our recursive call。If we're going to have a recursive call， we've got to have a base case。

So what we're going to do is we're going to start out。 Everything is in unused。 So when we start out。

 I'm going to have like unused。Contains 1，2，3。And perm， the vector。Ex empty。

So every time I make a recursive call， I'm going to move something from。Unused overin perl。

If unused is empty， that must mean that everything is in per。So if unused is empty。

 that's our base case， everything has moved over to perm， I print out this perm permmutation。

 so I print out this permutation and then I return I'm a base case。So there's our base case。

So our base case is print the contents。Okay， if that's not true。

 then we're going to look at this and I promise you this is going to be a little bit crytic。

 we'll go through an example， I think we'll have time to get an example done here。Okay。

 so what it says we've got to do is we've got to take what's at the unused front。

 we're going to put it at the back of the permutation， and then we're going to make a recursive call。

Then were going to after the recursive call is done。

 we're going to take what we put at the back of the permutation and we're going to put it back in the unused and we're going to get rid of it from the permutation。

Now let's not worry about where we put it in the unused app。But think of it this way。

 I started out unused was1，2，3， and perm was empty。That's before the recursive call。

So before the recursive call， that's what it looked like。 then I moved something over， right。

 I moved the unused fronts。 So I moved unused front over to perm， So I had one over here。

 so it wasn't empty anymore I had one over here， and that was gone。

So I used to have three things in unused and nothing in perm。 I put one in perm。

 I make a recursive call。And then after the recursive call is over。

 I take that thing that's at the back of the permutation and I put it into unused。

And I pop it from her。This is where 280 is going to help you a little bit。Precondition。

 post condition。Before this code happened。Unused had everything， and Perm had nothing。

After this code is done executing， I have returned to that state。 Everything is in unused。

 Nothing is in per。Now the order changed， but that's important for getting things in the right。

 getting all the permutations， the order changed， but the our precondition is。

What was in unused is the same before and after the recursive call and the two lines before and the two lines after are the。

Changing what's in there and changing it back to restore the precondition。Okay。

 so let's do oh I thought I had a blank slide in here。 Okay， sorry。

 I thought I had a blank slide in here。 Let me erase this and we'll go through it in here。

 I want to spread it out just a little bit so we can go through it。 Okay， let me oh spacing here。

Okay， so we've got unused。And we've got per。Okay， so we've got one， two， three。

 and there's nothing in part。We go to the for loop， right， So we're not a base case。

 We go to the for loop。Oh wow， there's a weird， I'm seeing a weird character。

 it doesn't look like backslash in， it looks like wide double horizontal bar。

That should be a backslash enter or yeah， that should be a backslash end。

 I don't know how that weird character got in there。I'll fix that later sorry， okay。

 so we are not a base case， so we go to the for loop and we move the unused front over to the back of perm。

And we get rid of it from there。 So we've got two，3， and one。 Okay， we make a recursive call。

 Is this a base case， no。All right， so I enter the for loop。

This four loop has to run two times because that's unus size。

 So I've got to run this four loop two times。 I take the front of the unused。

 and I add it to the back of the perm。And then I pop it from the front of the unused。I've got that。

 all right。Make a recursive call， is this base case， no， because unused is not empty。

Go to the for loop， this for loop is going to run once。I move the unused front over the back of perm。

And I pop it， so now there's nothing in unused。Make a recursive call。In this recursive call。

 am I a base case， yes？So I output one， space two， space three， that's what's in per。All right。

 now base case is done。 I return。 I am at line 12。 And so I have to do what line 12 says。

 I've got to take the back of the permutation and put it at the。Back of the unused。

 so I've got to put three over here。And then I've got to get rid of it from the per。

 and I've got one， too。Now that was a loop that was going to run one time， that loop is done。

If that loop is done， this recursive call is done and I return to line 11。

 I just finished a recursive call。I go to line 12。Okay。

 take what's at the back of the permutation and put it at the back of the unused， Okay。

 so I go to three comma 2， I've got a one over here。Because I pop back of the permutation。

 but now remember， I'm in the middle of a for loop that's running twice。

 so I go back through this for loop。For loop says， okay。

 take the unused front and put it at the back of the permutation one oops。

I don't want to do it there， I want to draw a new line， sorry。

 so I go to one comma  three and there's just a two in there。Think of it this way。1，3。Is fixed。

 two still needs to be permuted， so I make another recursive call。Make first call。

 Is this a base case， No， Okay， I've got a four loop it's going to happen once take the back of or sorry。

 take the front of the unused， put it at the back of the permutation，1，3，2。This is empty。

 make a recursive call， and my base case， yes， I am。Print out 132。Recursive based case is done。

 go back。And I pick up at line 12， and I start restoring things。

 So I'm going to restore things to the point where I've got。Two and three。

 and then one's going to go in。 and then I'm going to start basically， I've finished。

 I have now finished all the permutations that start with one。

 future recursive calls will do all the permutations that start with two。

 then it will finish all the permutations that start with three。Now。

 do you need to know how this works for the exam no？No。

But we're going to need this function again later on in the semester， when we get to project4。

 we're going to need this function again actually， we're going to show you a slightly better version of it in just a minute。

Here's the driver， here's main that sets it up， I've got an integer。

 I get the user to enter an integer。Again， looks like somebody looks like Professor Daren on his Mac messed up our backslash ans so we'll get that fixed So we read an integer as soon as we read an integer it says create me a vector of size teas size T is a tight And if you look at the canvas files。

 resources optimization tips you're going hear me say this I had a student to actually tell me Professor Paloti I was binge watching。

Videos to get ready for the exam and now I hear you say Canvas files。

 resources optimization tips in my sleep。Sorry， but it's important， so look at what a size T is。

So I created a vector of size t， a deck of size T's， and I created a deck of size Ts。

 noticeice here this is how big。How big should that deck be？And then， iota。

Iiota is a function to look at。 It's in the algorithms library。 I think it's an algorithms。

 It could be a numeric。 Look it up。 C P P reference C plus plus dot com。 Look up Iiota。

 What Iioda does is it says， hey， I've got a deck。 Let's say that perm， let's say that size was or M。

 Let's say N was 3。 So my deck right now， unused。Is of size 3， and it's actually filled with 0，0，0。

 What Iiota does is it says， go from unused beginning to unused end， inclusive， exclusive。

And fill it with values starting with one。 So it fills it with one and 2 and 3。You say Iota。

 why do I have to use Iiota， I could just write a for loop。 Yep， Professor Garen tried it。

 He tried Iioda versus a for loop for filling a really big container。

 and Iiota is like three times faster。So Iiota fills it with values and then gem perms prints off all the permutation。

 so you can just retype this code， throw it into a test project， try it out， run it。

 you'll see what happens with it。Now， there's one other side or sorry， two other slide in here。

 Look up， There's also the STL has something called next permutation。 Again。

 not going to be on the exam。 Next permutation is not something you need to know。

 but it's good to look up。 see what it does and what's different about it。

 But the really big important thing is our version allows us to add code to the base case。

 It allows us to have something that we do special with the base case。This， if not promising。

 this is going to be used when we get to backtracking。And branch and bound。

And that's going to be like lecture， I want to say lecture 20 ish。Where is that？Lecture 22 actually。

 so we're going to come back to see this again at lecture 22。

 this version basically has one container instead of shuffling stuff between two containers it leaves it in one container and remembers how much of it is permed and how much is not yet permuted。

And it accomplishes the same thing like if we get rid of those lines and we just do the C out here。

They produce the same output but。This version is faster because it doesn't move stuff between two containers。

 it just rearranges the contents of one container。Okay， so that's it for today。

 sorry we're like two minutes over here， so I'm going to end the video and I'll head over to Prof hoursrs。


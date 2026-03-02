# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P7：-08-EECS 281_ W21 Lecture 8 - Heaps and Heapsort.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

All right， quick sound check for those of you who are。On the stream。嗯。He post a quick chat message。

Acknowledging video and sound， please。According to my tech， everything should be fine。Right。

Things happen。Great， thank you。All right， we're almost ready， let's give a few minutes to folks。

They might be joining a few minutes late。So we'll get started in。We are Lunar New Year。

I have a couple of folks of my company。Took the day off to celebrate。我下一步的单单。In schedule day often。

 plus I still。Have to be here for all of you。All right， so hopefully this gets fixed soon。

 YouTube is not receiving enough video to maintain smooth streaming as such viewers will experience buffering。

All right， so hopefully when I stop my music。We'll get better。It's not choppy for y'all。Let me。

 let me do that actually just to see if things get better， okay， Google stop。Maybe that helps。Right。

3。All right， let's get started this。YouTube is telling me that it's not receiving enough video。

 I'm not sure what that means。Hopefully。The video gets smoother now that my kids will stop。

They're schooling for lunch。嗯。It's actually a good thing that this is scheduled at lunch。Okay。

 so so folks are experiencing buffering， Okay， so hopefully this gets better。

 I'm not sure what else to do here。It's said to， like。Max。Oh， no， I think it's。

 it's on my side because it is that YouTube is telling me that it's。

Not receiving enough video to maintain a smooth streaming， which so it must be。My streaming。

To YouTube。But I don't have anything else to play around with to make it better。嗯。Alright， so。

Let's hope that it gets better again， my kids should be stopping school。

So hopefully that will help with the bandwidth。And things get better。

 but let's get started because is three past noon， welcome back everyone to your live 281 lecture。诶。

My name is Hector Garcia。Mentioned that last time， just in case you didn recall。

 it's also there on the。I guess slide I also found that I had some real estate on my。呃。On my slide。

 so I added like a quote。From Donald Guth with who you might have heard of， if you haven't heard of。

 he's basically one of the grandfathers or grandfatherparents of computing as we know it today。

 it's one of my favorite quotes is beware of bugs in the above code， I have only proved it correct。

 not tried it so he actually wrote this quote and one of his seminal books in computing。嗯。

So it goes to say that sometimes and you probably experienced this in project one。

 you kind of assume that you have everything worked out in your head and then you where you wrote the code that implemented everything that you had in your head and then it doesn't work right because in your head you proved that it was correct but of course it's another thing when you actually have to go ahead and implement things bugs do creep it All right so today's lecture is on。

Heaps and heap sort we'll also talk about priority cues， which as we're going see。

 priority queuees is more of an abstract data type if you haven't heard of that term before we'll talk about it whereas heaps is an actual。

Practical implementation thing that we will write code for right so we'll basically start discussing what heaps are。

 the concepts， then look at code for heaps and then say how heaps correlate with priority cues。嗯。

So basically one potential implementation of a priority queue is using a heAP。

 more specifically a binary heap， which is what we'll discuss today for project two you will be implementing several types of priority queuees or several implement youll have several implementations for priority queue one of them being binary heaps。

 which。We're going to discuss in great detail today and give you code for right。

 So make note for project 2， you after this lecture。

 you'll basically have everything you need to go ahead and implement your。Binary heat in Project two。

So also one of my favorite lectures to teach in 281 because this is likely the first time that you're run into kind of a nontrivial data structure。

 efficient data structure that you you're going to be implementing right so up to now you might have seen some very simple well not necessarily trivial but simple data structures like a list in a binary tree。

And today， this is， you know， going to be a full on implementation of a。

I wouldn't say extremely complex data structure， but more intelligent data structure than the ones that you've probably seen before。

Okay so that's all right， let's get on with it in order to talk about heaps。

 we really have to talk about several concepts related to trees。And so trees。

 you've seen either in 203， depending on where you took 203 and with whom you also have seen some of an intuitivetuity if took 20。

So you know a tree is a graph that consists， well， a tree is a graph。

 more generally a graph consists of nodes and there's edges connecting those nodes。

 and then more specifically a tree is a type of graph， okay。It is a connected graph。诶。

Without cycles right so that's particularly important Okay and you can also say that same definition in a different way。

 which is it is a graph where any two nodes are connected via a unique shortest path Okay those two definitions that are actually equivalent outlet you kind of rummish through your 203 material to。

呃。Check that out。嗯。It is a directed tree where you know we can identify。

 we can identify children nodes and parent nodes。So an example of that is there on the slide right。

 so A would be a parent node to its children， B and C。Okay， and then in a binary tree。

 that is a node a node has at most two children， right， so no more。Has either no children。One child。

Or two children， that's it， those are the three possibilities。For any node in a binary tree。对。

And so additional terminology， you have the root of a tree。

 which is basically the topmost node in the tree， so in the example for that tree。And on the slide。

 it would be A。But note that you do have subtes。Inside of a tree， because。As you're going to see。

 you can have a recursive definition trees are very a minimal to recursive。Just recursion in general。

And so if we consider。This subt right here， that I'm。Second。Then the root is going to be B， right。

 So this is the root of。嗯。Call it subree。Well， I want to use a different letter， so sub3 Z。

parentarent is the immediate predecessor of a node， right？ So like I said。

 A would be the parent to C。 C would be the parent to I so on and so forth。

 childd is a node where the。Where the current node is apparent。Okay， so。I is a child of sea。

B is a child of a， so on and so forth， and as necessary is a parent of a parent okay so。

A is an ancestor of D， right shown here， So this would be an ancestor to D down here。嗯。C。

 for example， would not be an ancestor to D。嗯。Then you have descend sentenceants with a child or a child。

So。嗯。Then an internal node is a node that contains children。Okay， so as long as it has one child。

Or two children。It's an internal note。So technically， the root node is considered an internal node。

Then a leaf node is a node without any children right so you'll find the leaves at the bottom of the tree right so let's see if I can switch colors with me。

Nfety pen， right？All these down here。Are the leaf nodes。啊。The tree， all right。

 so that's mostly review and what you've likely seen before。Is an implementation of。A binary tree。

Using。Binary tree， nodestruct or class okay and。You've probably seen before this kind of。

Class declaration that's on the slide。where you have using pointers right。

 so you have a pointer to the left child， you have a pointer to the right child。

 and then you have some internal value to the node that is maintained。Right。

This is actually using some generic， so we assume there's some other class called item that we're using to declare the item that belongs to the node in line5 right that's the declaration。

That would be like a data。UmOr a key。You could have an additional declaration and separate the data from the key。

O那。But especially for this lecture， we're going to always conflat the key and the actual data that we're trying to hold right so we're basically just going to be using integers and the integers that we're looking at are both going to be the key and the data。

But that in a more generalized implementation need not be so right。

 you can have some key that we're going to look at to organize or structure the nodes and then the data。

 which is just whatever the node is meant to contain。All right， so as I mentioned。

 trees are by definition， recursive structures， so very a minimal to just recursion in general and recursive algorithms。

I mean that is because， you know given any tree， you might you can go ahead and look at a subree within that tree。

 right？So any of the properties that we can describe for trees can be defined using recursion。

 so for example， you have the height。Okay， and and because this is recursion。

 there's going to be the base case and then there's going to be。The recursive calls。

 so if you have a property that's high， okay， which is yeah how high the tree is from the base of the tree to the root。

The base case is that height at empty is going to be zero right， so it means like your tree is empty。

 it has a height zero right so that means that as soon as，The tree has at least one node， right。

 it's going to have a height of at least one。And the recursive definition is height at any no is going to be the max of the height from the left child between the height of the left child and the height of the right child plus one right so this plus one is always going to account。

For that route。So for example。Here， the height of B。Would be three。嗯。That is because it'll be。

The one here accounting for B plus one plus one。Makes sense。Hight。

 so fairly simple that you have size size is， you know， again， size of an empty tree。

It's going to be zero。But then size at any node is going to be the size of the left child plus right。

 so not a max， it's a plus size of the right child plus one， so that's fairly easy。

 I'll let you just work it out。And then death。Of the tree is how far to the null pointer。

 but looking up right it's kind of it's the inverse of the height right so height is kind of looking top to bottom and then depth is looking bottom to top so the depth add the depth of B is going to be2 right because it's going to be the plus one right here。

That counts B， and then it will be the death of the parent， which is a。

 and that's going to be one so it's  one plus one gives you two， right？So those's our quick examples。

 those are fairly easy， I highly encourage you to implement。Like if you haven't done it before， okay？

Fairly easy to just copy paste the code that we give you on this slide。Okay。

 createate a very simple tree and then implement these functions right it's good practice for something like a lab or an exam I think we do have a lab where we have you implement some of those things but。

Just in case you can also do it on your own。All right， so those are。

 that's basically a review of trees。again， you probably。Seen before， but if not。

 it's not terribly complicated。嗯。But we we are going to use a lot of those terms so get familiar with them when we when we talk about heaps all right。

 so I'll pause here to see if there are any questions just to see do I have anyone from staff on the chat' just to。

Okay， so I have streaming is the value low for y'all， Oh not for me。

 it might be the YouTube player volume。Fine for me Okay， so good。

 the volume is good for an integer key， any number for a string， maybe a name or something。 Yeah。

 those so I think Ian posted an example of like if you want it in your treestruct or tree node struck to separate the data from a key so maybe the keys which is something easy to compare that could be an integer and then the data could be something more complicated like a string。

 but again for the rest of lecture this lecture， we're going to assume that the key and the data are the same thing we're basically just doing an integer and we're going to use it as the key as well。

For the tree project for the project in 280， the key was the word from the Piaztoppo with the value there you go。

 what's the difference between a key and a datum then？For。Hopefully I don't add on。

Hopefully I don't put your the name， I apologize if I do。There is for in this lecture。

 we won't see a difference because we're conflating the two okay。

 just to keep things simple and write less code as you're going to see， but in general。

 you would want to separate the key from the datum。嗯。嗯。Maps aren't in trees。

 a map has two keys in the data， so yeah， a map is not a graph data structure。

 so they're definitely not a tree。Oh， well， if you're talking about what's implemented behind the scenes。

 leave let's put off that conversation how an STO map， for example， is implemented behind the scenes。

A little confused on the difference between height and depth， yes， so height， it's look at it。

 let's go back to the example。Height is just for any particular note， let me erase some of this。

Height， if we're talking about B right here。Height is basically measuring this distance。Okay。

And depth is measuring this distance right here。Does that make sense now？Moish。Give it a second。

 I know there's lag in between what I。What I say。But hopefully。

 so let me write it here so this would be height。And this is that。Of B， by the way， of node B。no。

So it's not of the total， so just to so partially correct sub I would correct the fact that you're mentioning total height of a tree。

 you can measure the height of a node inside of the tree like the B example that I just went over right but if。

😡，you measure or compute the height of the root node， which in this case is a。

 then that will give you the total height of the tree。Allright。是。

So heat fundamentals and this is going to be a bit jarring。

Because even though we've kind of described the tree node class， you know。

 and we kind of went over it and the pointers to left child and right child and all that stuff。

 now we're going to tell you to kind of forget it。诶。😊。

Because the way that we're going to implement trees is not going to be with a class like that。

So bear with me， we're going to talk about it in a second。

What we're going to do is implement such trees using an array and you might be like， wait。

 what do you mean an array or how would we use an array？Okay。😊，So again， bear with me。

But in order to be able to use an array to represent a binary tree like this。😡。

We're going to add some particular properties with for the trees that we're going to consider right so they are binary trees。

 but we're also going to consider that they are complete binary trees。😡，Okay。

 so this is a restriction that we're going to add。The trees that we're going to be interested in are binary trees。

And they're also complete binary trees。So completeness means that the way that you fill up the tree。

Is in a specific order。Okay， so if you recall， if you've seen you know， binary search trees before。

 you don't， there there is a constraint that you need to meet， but it's not related to how the nodes。

嗯。😊，Are inserted in the tree in terms of order。喂。😊。

Here we're going to say that if we're going to insert a node into the tree。😡。

Is going to follow specific order。And it's going to be top to bottom， left to right。So。

The way that you fill up every note in the tree is in level order okay if you recall what level order traversal is。

 if we started， say from an empty tree。The order of insertion of these nodes。Are going follow the。

Alpha numeric ordering of of the keys， which in this case are， you know A B C， D， right。

 so this is the or so this this would assume that a was inserted first， followed by B， followed by C。

 so on and so forth。 and that's level， right？And that would be a level order。嗯。For the tree。

So for example， the tree in the middle is not a complete tree because it doesn't satisfy that property right so we we have A。

 B， C， D， E， F。G should be here， right， but instead， right these are reversed。

Notice that the tree in the middle is something that you could get in a binary search tree because if you recall the condition for a binary search tree is just like which which shy should I insert the node depending on。

The comparison to the key of the current node。And so similarly， this is not a complete tree。

Complete binary tree because the insertion order would have been A， B， C， D， E。Oh， I see an I。

 that shouldn't be there because the next no that I would see should be an F， right， which is here。

 So these are this is bad。 It's also bad because G， for example， should be here yeah。Instead of here。

 so that's not a complete tree。Those are binary trees。But they're not complete binary trees。

And we're adding that constraint because that constraint is going to facilitate our representation of a tree。

Using an array。😡，嗯。So all right， yes， so we have someone from staff on the chat great thank you。

 don't know who it is， but thank you。嗯。Helps a lot see does that matter if a node is going to have two children doesn't that rule out the possibility that a leave node。

Would be。To the right。So I'm going to put off that question because I don't quite understand the question。

 So I'll come back to it。 Okay， and then hopefully we'll get an answer。

 Let me go next to representing。A complete binary tree using an array。

 and this is what it would look like。 so you have the same tree that we had before it's on the left there on the slide。

 and then you have the array representation of the same tree。Okay， so notice that we basically have。

The notes in the tree。Sored left to right， okay？In the array， so a goes here。Bi。四。D。

 so on and so forth right all the way to the end。 so it's labeled right there。

 the number that sits below the drawing of the node。Is signifying the index。

That we would use to fetch that node from the array。Notice that we've started our indexing。At one。

Rather than0。Okay， in the array。That has a purpose。Um。

 it's actually going to make some math that we're going to look at next much easier， well。

 not much easier， but just nicer。Okay，And you would say， well， what happens to the you know， zeroeth？

Notode in the array or serieseth element in the array。So youre a slot in the array。

 whatever you want to call it right here。Where that is supposed to be。Mhhm。😊。

Open and closing square brackets， we're just basically just going to ignore it。Okay， so you can。

 let's just do that to signify that。 we're ignoring that know， as it always。

 isn't that wasteful really is's just one slot out of an array that could be， you know。

 sized in the thousands and thousands。 So it really not going to make a difference performance wise if you just ignore。

A single element in the array。Cool， all right， so let's look at why we would want。To index the array。

At one。And by the way， in project two， when you implement it。

You're welcome to use either this one based indexing that we use here in the lecture。

 or if you want to just redo the whole thing using zero based indexing， meaning from the very first。

You don't waste that first element in the array， you're welcome to do it okay。

 it's just basically going to be working out the math that you're going to see next。对。So this math。

 remember， is going to be for the one base indexing of the array。嗯。For any note。

Okay given the current ordering that I have in this array for the nodes of the tree。That means。

That if I pick any index I。I can reach the parent by just doing I divided by two。

 and this is assuming integer division。That's all I need to do。and if you don't believe me。

 go back to this example and like， all right， I don't know。

 I want to find the parent to E right here。 All right。

 we'll find E in the array right here and then you have five divided by2。ok。😊。

That gives me two integer。And lo and behold， right， one and  two。

 it tells me in the array that it's B and yes， true enough。B is the parent。Yeah。😊，Makes sense。

All right， so additionally， if I were to do。From any node trying to find that node's left child。

 all I have to do conversely is I times2。Again， if you don't believe me。

 pick any node in the tree and say C， okay， I want to find the left child of C。

Okay let me pick a different color for my pen。Let's say I want to find the left child of C。 Well。

 that would mean C is indexed at three， so I do three times 2 that gives me 6。

 so I jumped to6 and lo and behold， it tells me that it's I in the array sure enough， there it is I。

Okay， and then。All right， so how do I find a right child Well。

 that's actually fairly simple still I would do i times 2 plus one。Again， you don't believe me。

 check the example if then the question is and I。Oh哎呦。Leave it to you all， give you one minute。

 see if you can figure it out。How do I determine whether a node？Is a leaf node。Okay。

 it's a fairly simple check。See if you can figure it out by inspection and all of this， you know。

I'm sure if I gave you this example and I told you like work out how I can compute the left channel the right。

 you would just spend， I don't know， half an hour， one hour and you know。

Just by trial and error would figure out what the math is， but we're just， you know。

 giving it to you because。It's easier that way。And again， if you were intent on， oh。

 everything's buffering。嗯。Things are buffering， okay， okay。Let me know when we're back。

And then can someone post？Where it might have buffered a bit， I don't know if it just。

Why is it buffering again， I don't know what's going on today。Okay， so we're back now。嗯。

And I have Richard who okay， so I guess everyone heard my question， or at least Richard did。

 which was how would I determine if a node is a leave node and that would be if I just check whether I is greater than however many nodes I have divided by two。

Okay。So。Just make some space there。So whether that index represents a leave node。

 you would check by doing I is greater than whatever the size is divided by two。

Okay so the size here is one to notice that this is size in how many nodes are in the tree right so how many non empty slots or elements I have in my array。

 not the capacity of the array right that's going to be important for project two。

 oftentimes we see that you know。People use the vector。

 which I believe we call data and when do data that size and that's what you use and no。

 don't use that， what you want to use is whatever the number of elements which is usually an integer you keep track of internally in your heap。

Okay， so it'll be whatever the size is divided by two and the size here， I believe is what one，2。

 three， oh， it's nine， so nine divided by two and so。If the index。

Of the node is greater than half of the size then you know it's a leaf。No， fairly easy Okay。

 notice that all of this if we were using。A tree node data structure， like the pointer base one。

It would require traversals in the tree， which is。You know。

 much less efficient than just doing random access on an array right。

 so that's one of the nice benefits。Of a heap， a binary heap implementation， using an array。

Or a vector for that matter。If I haven mentioned this before。

 I use the terms vector and array interchangeably。Okay。😊。

Because they basically are interchangeable data structures。그。All right， so。And reiterating。

 this is for when we're doing the whole bit about just ignoring the very first element of the array。

 okay， if you do that， all this math would work out， it' going to work out。

 and I'll leave you as an exercise to come up with this math that would correspond to actually not wasting that very first element of the。

All right。酷。All right， so that's that array is what we're going to use。

To store our complete binary tree。嗯。And。What we're going to use is。Complete binary trees。

To implement a heap。😡，诶。So， in addition to having。The property of being a binary tree。

 of being a complete binary tree， we're going to add a third property。

 which is known as a heap ordering property。And then we're going to have a full description for a heap implementation。

Now heaps， common two flavors， max and min heap。Okay， for the rest of the lecture。

 we're going to assume that it's a max。Heap。嗯。The difference is going to be apparent once I describe what the heat property is。

Um， so let's assume that we're going for a max heap， that would mean that um。

 for any node in the tree， any of its children。Okay， and descendants。Are going to be less。

Then the current node。诶。And notice that this is very different from the constraint that I have for a binary search tree right。

 remember a binary search street constraint will say like all the nodes on the right subt are going to be greater than the current note will depends which way you decide to go。

 but let's assume。😡，Every node in the right substrates is going to be greater than the current node。

And all the node in the left sub。Are going to be less than the current note。The heat property is。

Every node。Be it on the left sub or the right sub。Is going to be less than the current node。

 and it's less than assuming that it's a max。Jep。Okay。😊，And then if it were a min heap。

 then the constraint reverses， right， it would be every node that sits below the current node。😡。

Would have to be greater then。TheThe current note。系。😊。

And notice that if the current node happens to be the root。Of the tree。

 that would mean by definition that the root will contain。The most extreme value。

For the key in the tree。Okay， so in case of the max。Heap。The root。Is by definition going to be？

The maximum element in the entire tree。Yeah。Makes sense， I'll stop there to see you know。

 look at some questions here。Saw here if either child index references a null pointer。

 so this is an array， so there should not be any null pointers。呃。If that makes sense？

Or both actually。Again， so what would happen in an array implementation is you can try and query a left or a right child for a particular node。

 but you'd want to check whether that query would put you if the math that you worked out to check the left child put you beyond the number of elements in the array or again。

 the size， not of the array again of the number of elements in the array。

 then you'd know that no such left child exists， for example。😡，Okay。

 can we check whether or not the node has a left or a right child yeah。

 John that's what I was just describing you can check by just checking against the size right if you're computing the left child and that value that you come up with is greater than the size then you know that child doesn't exist。

嗯。Okay， I think we're good。 is it， is it complete heap ordered binary tree recursively or？

Can heaps be other trees too， no heaps cannot be any other。

 it has to be a complete binary tree that follows the heap order property。Otherwise。

 your he will not work。There's other types of。Implementations for a priority queue other than a binary heap right in fact your project you going to implement pairing heaps which are conceptually very different from binary heaps okay they achieve the same purpose which is to have a fast access to the most extreme element in the container。

But they do it by very different means。primarilyarily binary heaps are much easier to implement than pairing heaps as you're going to see for project two。

嗯。All right， so let's get going in the interest of time so we went over。嗯。The heap ordering property。

 right？So a heap has these two crucial properties that I just talked about， in fact。

 in response to a question on the chat， completeness， again。

 complete binary tree and follows the heap order。Okay。

 so we leverage these two to have not only an efficient data structure。

But an efficient implementation of that data structure that uses an array rather than a pointer based class or struct。

For the nodes in the tree。Allright， so this is where we put it all together。

 specifically with regards to what we mean by a priority queue。

 So a priority queue is an abstract data type also known just by。80T， right， so if you might have。

Heard of the term ADT that stands for abstract data type。嗯。

Which is also known as an interface right so usually prior cues is is what we call the interface。😡。

For a bunch of operations that we'd like to see in a container。Okay， and so for a priority queue。

 one of the like to see is fast access， specifically constant time access to the most extreme element in the container。

ok嗯。And it just so happens that a binary heap is an implementation that facilitates。

That same want to have in a priority queue， so that's why a binary heap satisfies an implementation for a priority queue abstract data type。

😡，Okay。Now that's not to say that you could write a tree implementation of a binary heap， you could。

 there's nothing preventing you， but it's going to be much。

 much less efficient than if you use an array。Implementation for your heap， right。

 so this can be confusing， but I guess that's how it works。 We use arrays or trees to implement。

A heap。But then we also。Say that we use a heap to implement a priority queue。

So the arrows in these box figures that we have here。😡，Imply。A direction of implementation right。

 so we use erasor trees to implement a heap and then we use heaps to implement a priority queue。

And also， we're going to use heaps later on this lecture to implement the Heap sort algorithm。😡。

All right。😊，So let us get on with heap fundamentals because now that we know。How to represent Ys？Um。

 we now have to discuss the operations that we're going to need to actually make a heap work。Okay。

 because we haven't really spoken about like， oh， what happens if I take one of the notes in the heap and I？

Take it off like what's going to happen， right， what happens if I take the top？The root node。

 if I take it out of the tree， what do I do？Okay conversely， how do I add a node to my heap？😡。

So that's what we're going to talk about。Right now。嗯。But what we're。Going to discuss first。

They're kind of， you'll see how they're specifically related。

Is if I take a tree and I break the heap ordering property， how do I fix it？

So we're going to come up with these functions to fix a heap。

And those are the same functions that we're going to use to actually implement functions for inserting or removing from a heap。

All right， so let's say that I wanted to modify a heap。

 let's say you have that current heap right there again， we're always assuming it's a max heap。Um。

 so let's say that we wanted to increase the priority。诶。😊，And recall that we're conflating。The key。

 which would actually use to compare the nodes with the data itself。诶。

We're just using integers in both， so we might as well use the same integer。

But just to remind you this need not be so right so you might have key which will signify priority and then the data is just something that we manipulate along with the key throughout。

系。😊，So if I wanted to increase key， meaning if I take， say， in this example。

 we're going to take eight。😡，Okay， so if I look in my assuming that this array is called heap。

 so just for so this is called heap。So heap at eight， which would mean this right here element。

In the array。Its current key is two。And I'm going to increase it to 35。

That's how I'm modifying my heap。If I do that， I will potentially。Break the he property。喂。😊，So。

Let's see what would happen， and usually I write this with my pen。

 but I believe we have some very cool animations。Wy there it is， Okay。

 so lets let's go over our new and improved animations here。So。Let's say that we increase key。

At heap8 from2 to 35 oops。That means in the tree picture， hopefully you didn't miss the animation。

 but just in case so you see we had two there right， so this is node8。Right here。

So what we're going to do is change that to 35。If we do that， you clearly see that we have。

Broken the he property。Okay， because we have nine here， which is less than 35。Can't have that。诶。

All right， Well， how do we fix it， Well， it turns out to be fairly easy to do What we can do is basically bubble up the value as much as we can in order to。

Fix the overall heat property of the tree。So what we would do is compare 35 against nine。

 determine that it is larger than nine。And swap。And do that recursively。

So now I would compare 35 against 18 determine that there is still a breakage there。And so swap。Okay。

😊，Niffty， nifty animations。嗯。Now I would compare 35 against 81 and say like， well， oh， this is good。

 This still holds for the heat property。 So no need to swap and I would be done。

 That's all the swapping that I would need to do in the array。

 which is now the animation that's so shown at the bottom of the slide， I would。Take the two。

Make it a 35， that's the update that I'm doing， yeah。And then just as before。

 I would compare against。The parent， which would be nine again， I would do that by。Doing I。

 which in this case would be eight。Divided by two gives me four。

 so that's how I can easily compare against the parent。Determine that I need to swap， so I do。Okay。

 ran this repeat。4 divided by 2 gives me 2， so I compare against 18， make that swap。

 and then2 divided by 2 gives me 1， so I would compare against 81 but determine that there is no need for swap okay。

So fairly straightforward process and this is known as a fix up。Okay。Operation。

OkayBecause what we're doing， if you see in the previous animation， is that we're at the bottom。

And work our way up fixing。The tree。Now you could write a recursive implementation for this。

 but why would you， it is way， way easier and much straightforward and more and easier to test if it's just a while loop。

 okay？😡，So。In this while loop， notice that all we're doing is while。

 so this is line two here on the slide。While。Basically I have not gone out of bounds because remember the left bound in the array in terms of elements is whatever sits in the element index at one。

 right we're ignoring the zeroth element。So while I haven't gone beyond the left bound of the array。

And。I can swap。Which is that condition where I'm checking the parent， right so this。Is basically。

Parent。D K divided by two。While I can swap。I do， I swap。And then I basically move to the parent。

 which is line four， and all I need to do to move to the parent is take the current a next。

 which is K。The divide equals y 2。诶。So fairly， fairly simple or straightforward procedure here。

And I ask you。You know。Take 30 seconds or a minute。See if I see some responses in the chat。

 what is the run time？Of。This function。And maybe there's also lag。Anyone beer？

What is the runtime of this function？Have an answer， log n， yes indeed， okay， oh， how is it log n。

 it's a while loop， well， it's a while loop， but you see that the stoppage of the while loop is going to be driven by k。

And K， I'm decrementing by doing divided by， right？It's not really a decrement， but the jump in K。

Is a factor of two。Okay。So。That's what gives you log end time。Again， log n being the number of。

Elements in your heap。Not the size of the underlying array。

 right at any point you can have the size of the underlying array be much bigger。😡，Then N。

Which is the number of elements in your heap。Right。😊，So always make note of that。

 remember it when you're implementing stuff in Project two。All right， so we have a function。

To fix things when the key is increased， but of course。

 you can also modify a tree by taking one of the nodes。And changing。

The key by so let's look at that key， so let's say that I want to reduce a key。

 so I'm looking at so this is he as an array。Okay， and I'm looking at two right here。

So that's the index。And I say， well， its current value is 18， I'm going to decrease it to three。诶。😊。

Let's see what happens then in our。Nfty。Animations。So we have a change from 18 to3。

And now you see that it's kind of the very similar situation， except you know。

Whereas for increasing the key in that situation， we just needed to look at the parent to see。

Where to swap。It is a little bit more comp when we decrease the key。Because we have。We can pick。

 we could pick between the left or the right out。诶。

So that's the only thing that makes it a little bit more complicated， but it's， you know。

 overall it's kind of the same approach right， given a change in the current node。

 I want to walk down my tree。😡，嗯。Whilst fixing whatever is wrong。Okay。

 it's basically the same approach earlier we were walking our tree up。From the node that we changed。

In this case， we have to walk our tree down。But as we walked down， we could either go left or right。

 so we have to pick which way to go and the way that we pick is whatever child node has the larger key。

Okay， uh， videos choppy again。嗯。So I'll take。One minute， see if it gets better。

But then there's the then there's the lack， but hopefully it gets better soon I honestly I apologize I do not know what's up maybe my kids someone one of my kids is using some nifty thing for their schooling。

I have to figure it out。Right。Alright。😊，So let's continue we so just get our bearings again we had 18 there you know in terms of the tree that's what we're looking at。

 we've changed it to a three so now we need to pick as we walk down to fix the heat property because recall if that is a three then that is smaller than either nine or seven and we can't have that right you know。

What we need is the larger number should be at the current node now， so how do we determine that。

 well we compare against the nine and the7 and determine the nine is larger。😡。

So that's what I pick to swap with。Bom。Okay， and then this is basically a recursive。Function。

Although again， we were obviously not going to implement it as a recursive function。

 but conceptually， it's easier to think of it recursively because what we would do is then move to that node。

And rinse repeat， right， compare against its children and compare three against two and4。

 determine that four is larger， so that's the node that I would pick to swap with。诶。And boom。

 then I'd be done because I'm at a leaf note。So in the array。

 the way that it would look in the array is。This lot right here is where I make my change。

 so turn it 18 to a3， then compare against9 and seven again using my nice i times 2 for left。

And I times2 plus1 for right， and I apologize for my terrible handwriting。

 but it's hard to write out with this pen。And so that I compare against nine。

And determine that that's swappable so I do and then rinse repeat right now I compare the three that now sits at node4 and compare against4 and 2 and determine that four is larger so I make that swap right so this is basically the same thing that we saw in the tree picture but now in the array。

Okay。嗯。All right， so let's look at an implementation for this function and you know。

It's called F Now。Because if the other function was fixed up and again。

 what we were doing was traversing up， then this one should be called fixed down because what's exactly what we're doing。

 we're traversing down the tree。Okay， so you can see how there's similarities except as kind of one is the opposite of the other right so earlier we had divided by two。

When when we were moving up the tree， but now we're going to have times two， right and in fact。

This is saying， well， while I have not hit。The right bound of the array， again。

 determined by he size， not the size of the underlying array， so not data that size。嗯。

I basically check the left child。Okay， and if the left child is smaller than the right child， right。

 so this is。Basically， left。And of course， J plus one would be right。

And all and this if on line four is just。Figuring out which child to swap with， right。

 so if you determine。That the right child is the one to use。

 then all you need to do is take J and do a plus plus right because remember the difference between the left and right child is a plus one in terms of indexing。

Um， given the math that we've been looking at。All right。

 if I'm looking at the largest one of the two， right？Which is now J。嗯。😊。

And I determine that the current node that I'm looking at is indeed the larger or equal for that matter。

 then no breakage， so I'm done， I would break right。

 and I would strongly discourage the usage of break inside a while loop。

But it's easier to read this time around but。嗯。The programming gods will。

Come crashing upon you if you use a break inside a while loop。Anyway， but here it's okay， no worries。

And of course， in projects， we don't really grade that stuff， so you're free to use whatever。

If you want to use。嗯。So otherwise， it means that there is a breakage and what I would do is in line six。

 I would do the actual swap。And then moving down is just， hey。

 whatever I determined I did to swap with， I'm just going to assign a K， comes back Rinse repeat。

OkayAnd that's your fixed down function。W which implements basically the example that we saw earlier in the slides。

With the sample tree。Go。All right， so now that we have fixed up and fixed down。

 meaning we have the means to fix a broken he property。

Now you'll see that it's incredibly easy to implement like a push and a remove。From my。From my heap。

嗯。Up， buffering again， I'll pause， oh man。In the meantime， why not use a break in a while loop。

 it makes things harder to read in terms of code， right？😡。

If it's a Y loop like the one that we have in the slide is yeah， it's very easy to read， that's fine。

 but remember sometimes you're going to have Y loops that are like fairly big that if you break in some middle of the loop。

It it kind of is jarring like if you're trying to understand what's happening in the loop and it's you know。

 you kind of see a break it's like， oh， okay， so now I break out of my loop and I gotta go back and remember what was happening at that point to determine the breakage so。

嗯。If in general， in programming using break or continue， I kind of frowned upon， I mean。

 but you know， to each his own。And my developers and my team， if they use a break， I tell them like。

You need to show your code to make it more readable because you should avoid the usage of a break inside of a Y loop or for loop。

 okay？Of course， sometimes maybe there's a particular situation where you can't help it。

 but I can't think of any， usually you can refactor， you can restructure things。All right。

 so now that we have our functions to fix。呃。Our heap， we can implement。

 push and remove functions or push and pop however you want to call them for a heap。

 which would mean。That having those functions will give us everything that we would need to implement a priority queue using such a heap right so priority queue is abstract data type what it wants。

 remember this is fairly basically just a description of a wish list for our container and so that wish list or or interface is that we want insertion which is push inspection which is top which is just checking fast check of that maximum element or most extreme to accommodate the case where you have min heaps。

 most extreme element in the container。And then removal， which is pop。Okay。

 you will see priority queuees in project two， you will be tired of them by the end of project two。

 you will also use priority cues potentially for other algorithms that we'll discuss later on in the semester。

😡，So that's why we talk about them so much。All right。

 so let's say that we're talking about a priority queue and we want to insert and this is a priority queue that we're implementing using excuse me。

 a binary heap。Okay。😊，So let's say that we have PQ and we're doing push 100。

The way that this would work。Is as follows， we would add what we're looking to push。

 the element that we're looking to push or the key that we're looking to push。😡。

As the last element in the array。Okay。😊，Well， in the animation right now its using the tree。

 so it would be the last node in the tree and remember it's a complete binary tree。

 so the way that we would add that node，Is top to bottom left to right， in other words， level order。

 so it would go as a left child of seven Okay all right so we。A place 100 right there。

And then what we would do is fix up。Right so we inserted there and fixed up and so 100 would be compared against seven determined that 100 is bigger。

 so swap right same thing that we did for fix up。Then do the same thing between 1 and 18 fix up。

We'll continue and compare 181。Which will be our final swap because now we're at the left bound of the array right or the root of the tree。

So you see that I basically was able to explain a away push by just saying， oh， I fix up。Yeah。

 so you're going we're going to look at a code for the push function and it's basically going to be two lines of code。

 one of them is just calling the push function， sorry the push function。

 one of them calling the fix up function。so this is what it would look oh this what it would look like in the array right。

 so it it's not that we would well assuming that our array is at capacity。

 we would have to create a larger array to fit the new element。

 but hopefully we're at a point where we haven't run out of capacity and so。😡。

Putting the new element at the end of the array or at the end of the prefil part of the array。

It's a real easy operation。So we just place it there， 100。And basically compare against 7。

 do the swap， compare against 18， do the swap， compare against 81。

 do the swap right that's what it would look like in the arrays。

 It's fairly nicer to look at in the tree than in the array okay。

But it's useful to see both just so you can get your bearings as to what happens in the array given the tree。

Okay。All right， so that basically covers insertion or push into a paric。Okay so as I told you。

 as I mentioned， it's basically two lines of code。You know。Place the element right end of the array。

Okay， which is， you know。Heap size。Then increment heap size by one， because remember after line two。

 it would mean that now the number of elements in your heap would grow up by one。

And remember if the plus plus operator is to the left of。Excuse me is to the left of a variable。

 it means that that incrementing is going to happen before the execution of the rest of the stuff that happens in that same line right so basically we will increment heap size first and then place that element the new item element there。

Okay。And then again， I I don't know if I mentioned this before。

 but these function implementation assume that there is some item class somewhere defined that we're using to represent。

An element inside of the array。For our heap。And then all we do is call fix up。Given the heap array。

 so this is just the heap array that sits behind the scenes and hip size， which is where heap size。

 not hip size， heap size， which is where the new element sits right and then fix up。

 we'll just take care of the rest。Okay。So fairly， fairly straightforward。Now deletion， all right。

 otherwise known as pop。Okay so if I wanted to pop my priority queue， how would I do that Okay， well。

 the way a priority queue goes what you're popping is always going to be the max or a most extreme element in the。

A prodigue。So that would mean， oh， it says no data， hopefully we can come back。All right。

 I'm giving it a minute。See if it comes back。Okay。I think we should be back。

 you should have seen some buffering according to my stuff。Here， I take here。

 but I think we're back in business。Or maybe not。This was not happening last Tuesday。

 I think I'll need to get in touch with exfinity。All right。

CouldSome in the chat tell me the status of the buffering？To determine whether I should keep。Do。

I think they're drawing the tree just for visual 6， but the implementation is using it。 Yes， William。

 that is correct， all of this， please note the actual implementation that we care about is the array implementation。

 we still represent the tree。Because， you know， it it's easier to conceptualize as a tree than as an array。

 but behind the scenes it's all an array will'll never in project two for the binary heap you will not be using a tree node。

Class or anything like that。All right， let me keep going， I think hopefully we're back in business。

 it says that。Viewers are buffering。 I'm going to keep going。 So we have deletion or pop。

How do we do that， as I mentioned， you would want to just remove the most extreme element。嗯。😊，Oh man。

 let me， all right。Give me one minute， I'm going to see if I can find something that I might cannot quite sure because I should be in class。

I'll be back in a minute。对。I'm back。 I can't find anything that's different from last Tuesday。

So I think our tech issues are more of。Exfinity， which is what I use。Sadly。

 that's what I have to use for Maya。Injure webs。Mish。

 can you go over the difference between heap size and array size， yes I can。

 let's say I'm going to use this drawing right here。If you had。

 if this was an actual array that you were writing in code， right。

 well first it would have like some slot right here。

For the first element that zeroolith element that we don't care about。Okay。

But then behind the scenes， you might have。Another part of the array， a bunch of slots。

That are unfilled， right， they don't contain any elements。

So this right here is an internal variable that you will keep。😡，That you may call heap size。

So it's value right there。Would be nine。Yeah。😊，Whereas the array size would be。Out here。Okay。

 so that's the difference。嗯。Does that make sense？Mish。

 and I hope I'm pronouncing you're incorrect as well。嗯。Yeah呃。Yeah， Xfinity sucks。So yeah。

 array size is really the capacity of the array， whereas heap size is how many elements you really currently care about in the array。

All right。So。Let me just so we can get back to。Deletion here。All right because we still have。

 we have 50 more minutes and we still have heap sort to cover， okay。

 but that's okay don' if we don't get to it today， we can continue Tuesday。I think。

With this deletion， we would cover most everything that you need to know for Project two。All right。

 so back to deletion again， it's a matter of using instead of your fix up using your fixed down function。

Okay， so when we delete or when we pop。What we're looking to remove is basically the root， okay。

 which is the most extreme element。And what we would do right there is take that most extreme element。

Remove it。诶。😊，And。Take whatever is the last element in the array。Okay。😊。

And place it as the root element。Okay， so we swap the four that sits here at the end of the array and swap it with。

The root or right over。Okay。😊，So we just move it there so you can see how this is kind of working things。

 but the other way around right when we insert it。We place the new element at the very end of the array。

And then fixed up。When we're deleting。What we're doing is。Moving。

The last element to the front of the array， and then what we're going to do is fix down。😡。

So it'll be comparing for guess 18 and 14 and determined that 18 is larger。

 so that's what I would swap with。Then take four and determine that I would swap it with nine and then。

And then I would be done。Okay， because at that point， I can just forget about this。

Slot in the array that is represented by this empty。A node in the tree。

When we do heap size minus minus， right because now our heap has gone down by one。One element。

So that's。Represented by the removal。Of that node， oops， excuse me， of that node right there。



![](img/d003a752002ef0918b5ec5ab91bcedf9_1.png)

All right， so let's look at what happens in the array itself。Basically， what we would do is。Well。

 this is the animations representing us as kind of taking out the the what is it 18， sorry？诶。😊。

But sorry， the 81。U， but really， if we just basically take the four and write over the 81。

 it's just just。The same effect， right？So take the four， place it at the first element。

 and then do our fixed down。So on and so forth。All right， so again。

 our deletion pop is just two lines of code， right， so it is placing of。

Line two is placing of the last element as the first element in the array。

 remember first here means index at 1 okay。嗯。And then fix down right here。

we can just pass it as one because that's where we placed the new element。Okay。

 remember if you go back to the fix down。Function declaration， the third parameter。

Is the index of word。嗯。The current element is at okay， in this case。

 the current element is going to be the root。 so it's just one。All right。

 so we basically have everything we need to implement。

A priorate you using a binary heap and I'll you know let you look at that XKCD。Somewhat funny。

So just to summarize what we mean by a priority queue， as I mentioned。

 a priority queue is an abstract data type or ADT。It supports primarily insertion。

 looking at the most extreme item。Indy tree in the binary heap tree。

We use top for that and then it also supports removal。Okay。😊，呃。Now。In fact。

 there are multiple ways that you can implement。A priority cube， as I mentioned earlier。

The one that we're discussing today is the binary Heap implementation。For project two。

 you're going to。Implement an unordered array priority queue。

 so basically you're going to implement the insertion removal and top operations using a vector behind the scenes。

Or again， or an array， note names terms used interchangeably。But it's going to be a plain old vector。

 there's no particular ordering right， so in those under those constraints。😡，How would you find？Top。

 how would you insert and how would you remove？Well， for。Inserting。

 that's fairly easy because we don't care about ordering。

So we just place the element in the first slot that we have available， right？Now。

Top becomes linear time because there's no particular order in the array。

 So therefore in on the worst case， I have to search all the elements in the array to find my most extreme element。

 right， Basically is's a max functionally that finds the max or min， depending on whether it's a。

Min particcu or max particcu。嗯。It has to search the entire array to find it。

And then removal is depending on what happens。Okay，Because there's no specific order。嗯。You will have。

2。D on where the element that you're removing sits right so if it's at the end of the array that's。

Constant time， but if it's in the middle， you're going to have to move things around。Okay so。U。

That can be linear time。And then an assorted array right。

 so it is an array where we're always maintaining the elements in sorted order。

 you have insertion that takes linear time right， compareare that to constant time with an own ordered array right insertion now takes longer because since we want to maintain the sorted。

Elements invariant。Then we need to find the right place where you're going to insert this new item。😡。

For Elvin。So that takes linear time because we would have to find where to place it。

And if it's sorted， you would say like， well， I can use binary search， yes， very good。

 so that gives you log end time but。Once you insert。

You're going to have to shift everything in the array， so that still takes linear time。

 even though finding where to place it might take log in time。😡。

You when you insert is still overall going to take linear time because of the shifting of the rest of the elements when you insert in the middle of array。

But because it's sorted， then it's constant' time to find the most extreme element because it's going to be the first element depending on。

 you know， whether you're sorting increasing or decreasing。

And then removal is also fairly easy because it's just going to be the most extreme element that sits always sits at the end of the array。

So。You， you can just。You don't necessarily have to shift everything。嗯。

You just have to remove the single element now in a heap， everything for the most part。

 is more efficient。It's log in for insertion， as we saw because of the fix up function。

 iss also log in for removal using fix down。Inspection is just constant time because all we need to do is look at the root of the tree。

 which is again， the first element in an array。The caveat is that it's a little bit more complex to implement because you need to write code to maintain the heat property。

 which are the fixed up and fixed down functions okay？그。All right。

 so let's look at some interesting functions for a heap。Binary heap more specifically。

 the first one is hepaify and then we'll talk about he starts。

 so we'll finish today because I'm running out of time with heify heap excuse me。

 the accident is getting the better of me。Heappoify。And then HeapO will do on Tuesday。

Which works out well because next week is when we start discussing sorting algorithms in general。

Okay， so。Heappaify， otherwise known as building a heap。😡。

What we're doing there is taking a random array， how do you take a random array of integers。

 for example， because all that we've been doing all along is dealing with integers。And。

Move things around in the most efficient way such that the output is an array that satisfied that satisfies。

All the constraints for a heap。Meaning it will represent。A complete binary tree。

That where all the elements satisfy the heat porter property。Okay。😊，Now， you could say， well。

 how about if I just， you know， take every element in my random array？

And then just declare an empty heap。And then just use the push function n times。Totally doable。

 the problem is you run into a run time of n log n， right。

 because remember the push operation takes log n time。

And you're going to do it for every element in the random array， so that's N login。

And then the worst。Even worse is the fact that you have to use O of n extra memory because you'll need when you declare the separate heap。

 you're going to be declaring behind the scenes a separate array that you're going to use to hold everything that you're going to push right so is O of n extra memory。

😡，喂。You can also say。Well， it's not hard to see。That an array that is in sorted order。

It's going to satisfy。The he property。诶。😊，I'll let you figure that out。

 you can show that by induction， like you can prove it by induction。嗯。

But if you take an array and you sort it， it's it's it's actually going to be an array that does represent some。

Complete binary tree that follows the heap order property right， so you can do that。

 you can say like， all right and I take my array you know。Throw it to a sort。Function。

 and then that's it。 I'm done。 Allright， so that's better。 It's not using extra space， right。

 because sorting algorithms， as we're going to see in later lectures， you can do in place。

 meaning in the same array that you're given as input。

 you just shift things around so that it comes out in sorted order。But the runtime is still in login。

喂。And what we can we're going to show you is a procedure that actually achieves the same thing in linear time instead of n log n time。

 which is what you would need for either sorting and reverse order or。😡。

Doing end pushes in when you continue。喂。What we're going to do is modify the given array and basically use either our fixed down function or a fixed out function to。

Fix it。😡，So that it represents a complete binary tree。That follows the border property。 Okay。

 now there's four possibilities here， right， because I could iterate my random array left to right。

Okay， which if you think of the tree pictures that we've had。

It's like traversing the tree top to bottom。Okay。😊，Remember。

 the very first element is actually the root right so if you're traversing the array left to right。

 you're basically going again as far as the tree goes top to bottom。So you go either。Top to bottom。

 doing fix ups or fixed nouns。Or you go bottom up， which would be traversing the array from right to left。

Doing fixed ups or fixed downs。 right， So there's four possibilities here right， I go top down。

Do it fix up or top down， doing fixed down。Or I do bottom up doing fix up or bottom up doing fix now。

 So there's four possibilities。😡，To go about this two of them don't work and two of them do work。嗯。

So。If you proceed。Bottom to top， right， so that is again。

Would be traversing your array right to left。Okay， doing repeated fix down。

That is the best and ideal。诶。Way to do it。OkayThis is what we're going to go over。

You can also try to do。啊。Bottom to top， which again would be iterating over the array right to left。

😡，Doing repeated fix up， that is not going to work。That would produce an invalid heap， meaning。

The array would not properly represent。A heap。You can also try top to bottom。

 which is iterating left to right， doing repeated fix down。

And that would also produce an invalid heat， right you just have to try it out。

 I'll let you try it with like these examples right here。

 it's not easy to do after two or three steps you'll be able to see it。It just won't work。

Then the last approach that would work is to proceed top to bottom， so again， left to right。

 do and repeat fix up， that would work， but that would mean that it's no better than actually just sorting。

 right？😡，So it would be and log end time。对。Wwhich is the same as doing a sort。

 so why would why would you do that if you could always throw it to a sort algorithm and it makes no difference in terms of runtime。

 then I would rather do that， right？But let's discuss。

 I guess on Tuesday because I flat out ran out of time。嗯。

This approach in the second bullet on the slide。Which is。What we call hepaphy。In STL。

 this is the make Heap function。😡，Okay and。It's not at all easy to see how this function works in linear time。

Which we're going to go over on Tuesday。So I encourage you to。

 also because you'll need it for project two， hey， just declare an array。

 put in some random like last lecture， we discussed how you can use a random number generator to just create a large array with a bunch of random integer values。

😡，Then pass it to the make Heap function。😡，And then look at the array after。

 and then you'll see that the elements in the array will satisfy the he constraint。Okay。

So that's an exercise and then on Tuesday we'll go over kind of the details of how that can happen and why we arrive at a linear runtime as opposed to N log N okay。

All right， so I ran out of time and I do apologize， I'll try to get in touch with Xfinity。

 see if you know， it seems to be on their end， honestly I can't think of what was the issue here。

 so I apologize for the buffering interruptions。Get started on project two。

 always the earlier that you can start， the better。All right， you all have a great weekend。

 stay safe， let me see if there are some lingering questions that I could answer real quick。I think。

Staff。Answer rate。Answered most of them， I don't know， by the way， who's in staff today？

So I can thank。嗯。Who'ho's on the chat from staff today， sorry， so that I can properly think。嗯。

All right， well whoever it is， thank you for taking care of the chat for the most part。嗯。

I will sign up now。Have a great weekend。嗯 where is my。


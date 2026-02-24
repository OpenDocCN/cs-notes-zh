# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P10：5 - Spring 2023 Discussion 03 Question 4.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/07ab240af576a1b7d72c2d9fee3ef271_0.png)

![](img/07ab240af576a1b7d72c2d9fee3ef271_1.png)

Alright， let's move on to question4 gridtify here we're asked to consider a circular sentinel implementation of a singlely linked list of nodes for the first rows times columns nodes place the item of each node into a 2D rows by calls array in row major order what that means is that elements are sequentially added filling up an entire row before moving on the next row so as an example if the Sly linked list contains the elements five than three than7。

2 and8 and there are two rows in three columns calling gridtify on it should return this grid so note that the Sly linked list may contain more or fewer elements in the capacity of the 2D array。

😊，So what I mean by that is you'll notice here that a two by of three grid gives us six elements to fill right but there's only five elements in the singly link list so you'll notice that the first row is occupied by the first three elements right because there's three columns so each row can only have three elements so the first three elements go into row zero so it's five。

 three and seven and then once we fill up that entire row we move on to two and8 and two and eight go in the first two positions of。

😊，Row index one， it's technically the second row， but because we zero index。

 it would be row index one， right？And one more note is that。

You'll notice there's a zero in this last element over here。

 and the reason for that is in Java when we instantiate。

An array I'm going to do like let's say like a stringing array， for example。

 what I means strategy an array of primitive types sorry each element of the array gets set to a default value。

 so for an integer array， if we say like。Pay Java， I want an in array of length3 and you don't specify what elements are in it already。

 It'll just default fall to a bunch of zero。 So just like。

I like that versus a reference type array if you tell Java hey Java I want to string array of length three it's just going to fill it with a bunch of nulls because they're reference types right and null's a special kind of pointer that represents nothing this in Java all this to say you don't need to worry about how the zero got there the zero will already be there so you don't need to worry about that super tiny edge case okay。

That's it。Okay。Cool so down here we have the Sly linked list class defined and we have access to a Sinel node the node object contains an int item which is what we want to be putting into our grid at the end right and also each node has an attribute next which points to the next node in the Sly linked list so if I were to draw out this list over here with the sententinel with the circular Sinel implementation specifically it would look something like。

😊，Here's our Sentinel。And it has a next pointer， which points to a five。

And the fives next point to your points2。A three。Threes next is a seven node。

Ss next node is a two node and then the two's next node is an eight node and instead of stopping the single list here and being like okay8's next node is null。

 we're not going to do that because it's a circular implementation so8's next node is going to swing right back around to the Sentinel so it's circular okay。

Okay， and then one more thing that I want to say before we jump right into this question is that I think that。

Multidisional arrays can be a bit daunting to students sometimes。

 so if we were to draw this out in like the job of visualizer。

 let's say like two rows and three columns。Java would represent it like， okay。

 you just told me you have an integer array。A 2D integer array with two rows and three columns。

 So that's the equivalent of doing something like this。

 So the first dimension is of length to and the second dimension is of length through this would look something like。

Length2 array and within each of these boxes in our length2 array。

 there are pointers to a length three array。I and then if I were to fill it in， it would be like 5，3。

7，2，8，0， but I'm not like the hugest fan of this representation because it's like ugly and it just doesn't really。

 I think it's not very conducive to our minds when we think about like what a 2D array looks like like a grid looks like so I'm going to probably draw things like this and to put it explicitly。

If we were to。Say this is our 2D array， let's call this like R。切。This whole thing。Would be R 0。

 this whole row right here， the 53 and 7， this length3 array is going to be R 0。And the2。

8 and 0 down here are R1。And if we wanted to get something like the eight over here， that would be。

R1 right because R1 gets us that whole length three array with 2 a and0 at index1， right。

 because8 is at index1 of this array of 2 a and0。All right。

 so hopefully that helps build a little bit of intuition about 2D arrays because we're going to be working with them a lot in this question and yeah let's jump straight into the problem。

😊，So here we have Grtify， it takes in an int rows and it also takes in an int calls。

 and there are literally only two lines that we can fill in。Okay， I don't know about you， but like。

This seems like kind of a complex problem to tackle and we literally have like two length to do it that seems like infeasible。

 which is why we're lucky because we also see a signature over here for something called gridtify helper it doesn't return anything。

 but it takes in a 2D inch array grid a node curve and an inch nufil okay let's maybe maybe let's fill in。

😊，A little bit of gridify and then we'll jump to gridtify helper and then back to gridtify and Ill hopefully you can like catch catch on to what i'm doing but the reason for that is because I think it's just a little more intuitive to tackle the problem like that so up here in 14 we have this variable grid it's a 2D integer rate。

And we need to instantiate it， right。From the example up here， if we had two rows and three columns。

 we would instantiate it with something like this right oh it's got the new。

Where in the first dimension， there's two rows， right， and in the second dimension。

 there's three columns。 So what we're going to do over here in line 14 is much the same thing。

 we're going to say new。2D inter where the first dimension is length rows and the second dimension is length calls。

 so this basically makes a 2D and array where there are rows number of arrays of length calls okay。

Oh。So when we come to our helper， we have access to this grid。

 this curve and this nufield and I don't necessarily like to do this regularly but I think in the context where you're given like skeleton code and like sometimes where you're on an exam and you're like shoot I really have no idea what's going to go into this variable I think it's okay to like cheat a little bit and read the variable name and be like I wonder if the variable name will giveaway like a clue as to like what this is supposed to do for me so the grid is the grid hopefully it's like fairly clear that we're going to be passing in this grid that we just created and gridtify to gridtify helper then we have this curious note curve and this number nufil okay。

We have this big old if statement and then from this if statement we immediately return Okay。

 so that implies to me that we'd probably want to return immediately。

If like we're done going through our single list， like we've put everything into our grid that we possibly can。

 okay？I'm just going to write that here like if finished。Putting。All elements through。

gririd okay and then down here we have row and call as variables and once again I think I hope I'm not making like too much of like a logical leap here and hopefully it's fairly intuitive that row and call are supposed to help us index into this grid and basically help us tell or help tell us what row and column we need to index into the grid in order to put CurRS item into but basically we can figure out like the nitty gritty of this later we just hopefully hopefully you've intuitive that this row in this column are going to help us index into grid so。

😊，Remember that the point of this question is that for each node in the Sly link list。

 we want that to end up somewhere in our grid right or the the item or the number associated with each singlely linkless node is going to end up at someplace in our grid。

 so I'm just going to extrapolate a little and be like。

 okay that means that after we find out what a row and the column mark。We can just do grid。Sub row。

Sub columnn is going to be equal to cur。Dot item right because cur is a node and it contains some kind of item。

So this was just fully me being like， okay， I just。Like I know I haven't filled out lines 24 and 25。

 but I know they have something to do with helping me find out exactly which spot in my grid I'm supposed to put the current nodes item。

 so that's why I'm going to start。😡，Okay。Next， the let's maybe tackle line 20。

Actually maybe let's tackle the last line so gridtify helper is helpful for us because we want to go through every node in the Sly linked list right and hopefully you've intuited this out but when we have like a singlely linked list question or like any kind of like linked list question the gut instinct for us is to make functions recursive because linked list are very recursive in nature right we start at a node and we go on the next node then we go on into the next node and we go on the next node so basically in the final line of gridtify helper。

😊，I have a strong feeling that it's going to be a recursive call to gratify helper and I used to be really scared of recursion like when I came out of 601 a like didn't feel fully prepared and even when I was taking 601 B I was like the recursion is really scary to me because I can't take that recursive leap of faith and I hated that term so so so much so let's do this together。

On this last line， let's make our recursive call。To gratify helper。So at this point， you know。

 barring the fact that we haven't filled out rowow and column or whatever。

We just assume that in line 27， we are correctly setting the current nodes item into the grid at position row index column。

 okay？Or sub row index call that's what I meant so that means in Grtify helper when we recur we need to pass in some updated variables right because we're like okay we just like got through the current nodes item on the next one right so what I like to do when i'm making a recursive call is I look at all my variables and I think。

Does this variable change or does it need to change and how does it need to change。

 So when I look at grid。Do I need to change what grid is equal to？Well。

 we did set like the element of grid at index row and column right。

 but we don't actually need to change what grid is equal to you like we don't need to be like grid itself equals some new thing right so I'm going to say that grid does not change。

What about K Well， K is a node and we already saw this current node right we already put its item into our grid。

 So I would say that yes， curve does need to change and the only way that we can really change curve is by moving on to the next node。

 which is exactly what we want right we want to move on to the next node and put elements into our grid in 2D row major order so we can say curve do next。

Gets passed to gratify helper。And numb filled is more of。Is more of a mystery here。

 We haven't used numb filled yet， so numb filled。Once again。

 like cheating a little bit and going off of the name of the variable nu filled is going to be a variable that helps us keep track of how many elements have already been filled and the intuition behind this is that in line 20 we have this if statement and we already previously established like from intuition that this statement is going to return if we finish putting all elements through the grid right and if numb filled is equivalent or greater than or。

😊，Let's say equivalent for now if nufield is equivalent to like the actual number of slots that we have in the grid then we're done right we can't put anything else into the grid and we noted up here in the problem statement that the SL list may contain more or fewer elements than the capacity of the 2D array that we're trying to fill right so at that point we should just stop。

😊，Trying to iterate through our singlelylingus and put things into the grid because there's nothing not like no empty space left in our grid。

 that's the purpose of the nufil variable。So that means that we need to keep track of how many variables that we've already filled right so when we call gridtify helper we've just put a new element into our grid。

 so that means that nufold should increase by one。Plus。Cool。Okay。

So knowing that we can tackle this statement now， which is if we finish putting all of our elements through the grid。

Okay， so。We can break that down into two cases。 Actually， I'm going to keep that there。

 So the first case is either fewer elements。In。The Sl list。Then。Grid size， right。

 Or there are more elements。In the singlely linked list than the grid size。

 so if there are fewer elements in the singlely linked list than grid size。

 that means that we would run into a case where。We went through every single element in our link list。

 and then we ended back up where。This is like a tricky thing that I think it helps to draw out。

 which is why I did draw it out in the beginning， but a lot of my students in discussion thought that oh。

 if cur is null， then we would stop recursing right because there's nothing else left to recurse on。

 but the issue is that with a circular Sinel implementation。

If you go all the way to the end of your list and you go to the next node again you're going to end up back at the sententinel Okay。

 so this really like the Sinel even though this is the last element in the list the sentinel marks like the true end of the list right so this number one is basically。

😡，If K is equal to Sentinel。Because that means that we went through an entire list and we ended up back at the Cinmon we're like。

 oh， there's no more， we shouldn't like we shouldn't recur anymore more through this list because we've already seen everything。

Okay， on the other hand， if there are more elements in the singlely linguist than the grid size。

 that means that numb filled。😊，Is greater than or equal to so that means the number of elements that have been filled into the grid already is either greater than or equal to。

The grid oops。The grid size。Aka Rose by callss。Okay， cool。 Let's put that into code。

 So the first one is pretty straightforward so we can say if cur。😊，Is equal to Sentinel。

When we have fewer elements in the Sly linked list than the grid size。嗯。😊，Then。

We want to return immediately because we're like， oh， there's no more elements to put into our grid。

 right or。Nun filledled。Is greater than or equal to really it should just be equal to but we're playing it safe here and doing greater than because just like formality's sake。

 greater than or equal to our grid size。Okay， so in gridtify we have access to rows and columns right。

 but like in Grtify helper we don't have access to rows and columns。

 but that's going to tell us exactly how large this grid is， right？

So even though we don't have direct access to the original number of rows and columns that were passed in。

 we do have access to the grid directly and if you'll recall。嗯。

Grid has a couple or an array has a special variable called dot link。

Which tells you exactly how long that array is so like if we have like R dot length and array was like length to there were two elements in this array。

 our dot length would be equal to two Okay， so we can use that same principle to figure out what the rows and columns are so we know that the first dimension of our grid we passed in rows so we know that rows。

Is effectively。Grid dot length。Right。Calls is a little harder to imagine。

Um but we know thatum one row in our 2 d grid is represented byum or like one row in our 2D grid is。

Itself， like kind of like a pointer to another。Aray so in the example that we were talking about oops actually I'll just yeah I'll just point out this one in the example we had earlier with this two rows by three columns example we know that the 2 d array points to this like length to array and each element in that length two array itself points to a length three array because there's three columns in two rows so we can use that same logic and be like okay。

 we know that the row is like the number of rows is the grids length right？

These like two elements up here and we know that each element in that grid。In each row。

Is going to be an array of length columns right， So if we just index into grid like we could do like grid。

Sub0 dot link。 that's going to tell us how many columns we have。

 So we can change this to nu filled is greater than or equal to。Grid dot length。Times。

Grid at index zero。Dot link， okay。I'm just like， can I erase all this because it's like really cluttering up the space。

嗯。Okay， so we have our base case， we have our recursive case。

And now I'd like to hop back into Grtify because I think that these two lines really are challenging。

 especially if you haven't really seen row major order before and it's like。

Like kind of hard to remove， but in Grtify we know that we're going to call Grtify helper。

So Grify helper takes in a grid， a note curve， and an inch numb filled。

So we know that we're going to be passing in the grid。As for what we pass into curve。

This was a little bit trickier， and there are a lot of options that you can do to pass into curve like but typically when we pass in a node to。

Some kind of like linkedist problem or linkedist function in this class we will call it we'll pass it the first element in the list the first node in the list and by first node I don't mean the Sinel I mean like the literal first node in the list that contains some value that is like meaningful to us because the Sentinel is the node that we have access to but it's value is just like a placeholder right it doesn't really mean anything it's Sentinel dot next that we'd like to use。

And in theory， we could do， we could pass in like Sentinel dot next dot next or Sentinel dot next dot next downdex or even Sentinel itself。

 but typically for the purposes of these questions。

 especially when we're concerned with like indexing into something。

 we want to pass in Sentinel dot next because like the first element of the list is going to be in like index zero。

 right？Okay， and finally for numb filled， that's the number of elements that have already been filled and we already established that we're in this recursive call。

 we're going to increment it and that's going to be the determiner for what goes in this if statement right like to determine whether or not we're done filling up our grid so we can just initialize it to be zero。

😊，Okay。Okay， so we've just made our recursive call to gratify and now we're on the final parts。

 which is actually filling in what row and columns should equal I this is honestly the hardest part of the question if you're not super familiar with like。

With like grabbing the elements of a 1 D a one dimensional data structure and putting them into like a 2D data structure。

 But it depends a lot on the dimensions of the 2D data structure。

 So I'm going to give an example up here。 I've erased like the messy like scribbles I had earlier。

 but let's say I'm going to。Number each of the elements in the singlely legalist by index。

 so five is going to be index0， three is index 1， so on， and so forth。And if you notice if。

We draw out where each of the indices ends up。Let get 0，1，2， and then。Excuse me。

 and then index three， four and then this one doesn't really matter。😊。

And we know that this was a two by three。grid。Right so because this is row major order so we have to fill up the first row entirely before we move on to the next row that means that rows come in groups of calls elements right so one row consists of three elements at a time so that means that the number of columns is directly relevant to determining what row we should end up in in our2D array right so if oops。

If we're0， one or two， we should end up in row zero and if we're three。

 four and on for the purposes of this question just three and four， we end up in row one。

So that means that like the first three elements of our singlely link list end up in the very first row and the next three elements end up in the next row but the next three elements end up in the next row。

 so that smells very strongly to me of division and like specifically floor division in the sense of like。

😊，If we do。One floor divided by three， which is the number of columns we have that ends up being zero。

 so we would get here and be like， oh， index one is going to be in row  zero。

 same with two right floor two floor divided by3 is going to give us zero as well。

 And so we know that two is going to end up in row zero。

By the time we get to three though if we do three floor division three。

 we get one so we know that three is going to end up in row1 likewise if we do four four floor divide by three。

 we get one so we know that we're going to end up in row one because we know that each row comes in groups of three okay so that was kind of like the answer to what row is。

So， row is going to be。Like effectively like the index we are in in the Sly linked list。

Divided by the column， the number of columns that we have， which we established up here is grid。

Sub 0。Dotling。ok。Now the question is， well， what is like the index of the element that we're currently at right because we don't have like a running。

Number to account for that right but we actually do because we have numb filled up here and numb filled we started at zero because we wanted nu filled to tell us how many elements we have already filled into our grid right so when we enter this function for the first time nu filled is zero so that's effectively index0 right and we know that with every recursive call we increment numb filled so numb filled is effectively like an index for us it's keeping track of which index of our singlely linked list that we werere in right so we can just do。

Nun filled。Divided by grid sub0 dot length to be our row， okay。

 and that's going to tell us which row we're in。All right。On to call。

 I think call might be a little bit easier to like into it out， but you'll notice here that。

Like the row the column that we end up in for a particular index is also dependent on the columns right because once again each row consists of three elements in this case so it's either only going to take on values of01 or two right in terms of which column the the index ends up in and because we know that and like any index will ultimately get paired down ultimately get shaved down to a number that's either01 or two in this case because there's only three columns that seems a lot to me like a mod So if we do like。

One modular3 which is the number of columns we have。

 we get one so we know that the one is going to end up in column one of a row likewise if we do something like four modular 3 we're also going to get one right the remainderer is one and so we know that the four is going to end up in column one of some row。

And then if we do like three modo3 that gives us zero right the remainder of three divided by 3 is just zero。

 so we know that three is going to end up in position zero of one of the rows。

 So how we put that into code is down here， we're going to say nu filled right because we're still working with the index here。

 mod the percent sign is the mod。Once again we're going to use the column link I mean just the columns number of columns we have to modulate it and that's how we get the column that we're supposed to use based on nu filled which we use as like our index a quick note right here。

So I know in Python， Florida division is something like。

Two slashes but in Java the regular division sign is by default already floor division so you don't need to worry about it okay and we've just finished gridtify okay that was such an or deal。

 This is a really tough question and like to be honest I was I initially wrote this question to be put on the exam and then I was like I think it would be a good discussion question so I just like kept it there instead anyways part B less part of this entire worksheet why do we use a helper method here so why do we use gridtify helper to actually implement gridtify like why can't we just have the signature for gridtify also have a pointer to the current node such that the user of the function passes in the Sal each time。

So basically what this is asking like is like， why don't we just have gratified taken rows and columns and also like a node curve and then also like a nu filled。

Right。And the reason for that is。One of two things so number one it's always good to kind of factor out your code into smaller chunks for modularity purposes so like。

It's like always like really frustrating。 Let's say you're like writing a function。

 and it's supposed to do a lot of things。 and it has a lot of moving parts。 And it's like 100 lines。

 like， it's super frustrating if like even one tiny part of that code goes wrong。

 And then you have to like debug like your entire function。 right。

 It's always great to break down your functions into a smaller chunks to make them more manageable and easier to debug。

 So that's one reason。😊，Another really big reason is。

Let's say you're the programmer and we have some singly linkedist。Like S。

SL list or K or something like that， and then let's say we fill it with a bunch of elements。

It's really nice for us to be able to call S do gridtify like2。

3 right where we're just passing in the rows and columns and we're telling， hey Java。

 like I just want you to gratify this function I mean I want you to gridtify the singlely linked list for me into a two by three grid it's like so clean it's so simple we don't have to worry about like the nitty gritty implementation of it right versus if we have to do something like S do gridtify rows columns and we pass in the node that's going in and we pass in the number filled so far already that's super unintuitive to the programmer or the user who's using gridtified so I have to pass in these like super specific implementationbased details into this function every single time they want to call gridtify right and makes it easier for us to make mistakes Also it's not intuitive for the user and third of all like the user shouldn't really know about how the singlely linked list works under the hood right like let's say you have a client somewhere and they have access to this grid。

I function this gridtify API they shouldn't know under the hood that it's like implemented with a bunch of nodes right so it kind of helps abstract away all this information to a user and give them the simplest interface possible to work with all right。

😊，Cool， and that's it for question four。

![](img/07ab240af576a1b7d72c2d9fee3ef271_3.png)
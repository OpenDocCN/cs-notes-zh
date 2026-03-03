# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p50 29_06_09_代码走查-构建Python-0.0.9字典实现.zh_en -BV1v2421P7pt_p50-

![](img/5410a62ed2645451ea3ea9662e58a072_0.png)

So welcome to another code walkthrough for C programming for everybody。

 This is another in our epilogue code where we're comparing and contrasting the way I taught lists and strings in the Kninggan and Richie chapter 6 with how Gio of Van Rossom actually implemented dictionaries lists and strings。

 and we're going to look at dictionaries here。 So I've got two tabs open in my text editor。

 I've got one that's P1 dit C， which is the Python1 implementation。

 which is my approximation of Gito's approach and my simplification of Gito's approach。

 and then I have the Kr diict， which is the version I wrote。



![](img/5410a62ed2645451ea3ea9662e58a072_2.png)

Kind of cleaned up and adapted for this。The version that I wrote as we covered it in Kne Gurenci chapter 6。

If we look at the very allocation and I mean the structures at the top。

 we have a de node a dictionary node and we have in the dictionary node in my implementation is got a next pointer and so it's got a key in a value。

 we're going to have character we're going to string keys and integer values just to keep our Malex down but the difference between the dictionary node in my code is that I am going to everyone is going to be part of a link list because if you recall in my code in Carnegiegan and Richie as it's described。

It is an array of linked lists。 And so in this case。

 I just have four heads and four tails that point to the head of a linked list。

And so that means that every Dode has got to be either the beginning， middle or end of a linked list。

 and so it's got to have the D nodes have to have a star next in them。

So let's go compare and contrast that with how Gio did it so Gio still has a d node because now we're in dictionaries and so you need a key and a value and so in my KR deck I made the value be integers just to simplify it。

 but I'm going to make the keys be the values be strings in my Python code to be a little closer to you know what Gio did。

But then the change happens when we start allocating the actual dictionary object itself。

If we look at what I allocated， I have a number of buckets， and I have a count for mystruct Kr dit。

 but then I have an array of four heads， an array of four tails。

 which is basically a way to make four linked lists that I will select among the linked lists based on the hash function。

 but that's not what。Gto did in P1 dit， we got allocation in a length。

But then we also just have an array。Seriously， an array of pointers to D nodes that we'll call items。

 Now， the fun thing is。If you look at this。Let me go ahead and show you a little bit different if I looked a P1 list。

And I compare and contrast。A P1 list has an allocation， a length and a pointer to。

I an array of pointers to strings。In my P1 dictionary， it's an array of pointers to key value pairs。

 but the ac length and then an array of pointers to something is a very similar approach and you'll see when we get to the Python 3 stuff。

That the， there's almost a duality in， in Giidto's mind between the dictionary and the list。

 The dictionary is like just a slightly improved list having to do with indexing and， and again。

It was a surprise to me。And。But the similarity， again， when you get to Python， the3 Python。

 Python 37 version of the dictionary is going to be like， oh， I see what here going on here。

 but so just for now， remember the approximate duality between dictionaries and lists in Python 1。0。

Okay。So again， we have our linked list nodes that have a pointer to a key pointer to a value that'll be a dynamically allocated pointer。

 pointer to a dynamically allocated and safe string。

 and then we have a dictionary which is then a one dimensional array of those pointers to those D nodes。

And if we。If we look。So， so the key thing here is。We need to know which entries in。

This array of dinos are。Empty and available in which ones are used。

 So the construct is a little more complex。 if we look at P1 di underscore new。Of course。

 we allocate the kind of object itself， we set the length because there's nothing in it。

And we're going to allocate。Two slots， just like we did in the P1 list。

That that forces us to reallocate so that we don't have to write too big of a code to cause reallocation。

 and we can debug our reallocation， and then we basically create an array of D nodes。

So we're like two times the size of struck Dode。And the size of struck B node is。Two，64 bit pointers。

And then what we're going to do is we're going to mark them as empty。

 We need to know that these items are empty。 And so we're going to set the key。

 which is a pointer in the value for each of them。To null。

 so you've created a two long array of D nodes with keys and values of null。And again。

 we need to remember which ones are empty and are not。And so， so then let's look at the main code。

 So that's the constructor。 That's the data。 that's the。

That's the data structures and the constructor。 So， so what we're going to do is we're。Oh man。

 didn' I thought I'd deleted that line that。Now let's delete this line。Ca we're printing it。

 We've added some stuff in the print。 that makes it a little simpler。Okay， let's hope it still runs。

 That would be cool。 Let's run it。 Ske I change the code。Yay， it works。 Okay， Okay， it's simpler。

 I like simple。 So we create a dictionary calling P1 diict new， we print it。It's going to be empty。

 Then we put under the key of Z， the string catch phrase。And print it。

 then we put the key we put W in。 that should be a replacement。

And then we put the string s in sai equals B， basically。

 Sally equals C basically and then a equals D， and then we say how many things do we have in there。

 and then we do a get。Like a dot get in a Python dictionary。

 and we're looking for the key Z and we' looking for the key X。

 well the key X isn't going to be in there， and then we delete it。

So let's go ahead and run this code， which we just did。And。And so what this print does。

 I've added some stuff to it。 so you see the first print is just curly brake open and close curly brakes empty。

 and it's also printing out the length and ac。 and so basically what it's saying is there is a length of0 and what we have two spaces ac。

So then what we do is we put Z in。And that Z ends up in Z equals catch phrase， and that ends up in。

Position0 in the array。 and then we have a length of two a length of one because we've got one thing in there an ac of two。

Then if you recall， we replace z equals W。Now， because Z hashes to the same spot。

 we'll talk about how that happens in a second。 That hashees to position 0 in the array。

And then it just replaces it， and so it just replace the value in that case。

 and so we still have only one item in there and an allocation of two。Okay。

And so then what we're doing is we're inserting a new。Like sakai equals B。

I should probably put some more print statements in there。嗯。Let's do let's do that。

Let's do the underscore put。And let's put a print statement in here。Print app。Insert。Percent S。

Equals percent S。Back slash n comma key comma value。Oop。It'll be just easier for us to。De bugg this。

第一。😔，Okay。Okay， so。We insert z equals catchph that goes in。Hed slot zero。

 we have one item and a length of two， we insert z equals I want to call that put。

 I want to call that put。Because it's not insert。So then we put z equals W。

 and then it uses the hashing and the lookup and all that stuff to find that that's in position 0。

 And so we simply replace the value。 so we' we didn't extend it at all。

 And now it's trying to put sai equals B in there。And with the hashing。

 hashing of Sakai finds its way to position one in our two item array。And when we're done。

 we've got our two item array happens to be insert order。

 but that doesn't necessarily mean because it's just my hash function in terribleable。

And then we have two items in and and two items out， two items in there and two items allocated。 Now。

 we're trying to insert Sally equal C。 And now the hashing algorithm， which I'll show you in a bit。

 looks through and says wait a sec。 there's no space here。 Usually at that hashing algorithm， says。

 if it's above 60 per cent。Full， then we declare it no space。

 And so we're going to do what's called rehashing。 So we reallocate， and then we re add the thing。

 So we're making the space。 So it doubles it in size。 So when it's all said and done。

 sai ends up in position 1 and Z ends up in position 2 and Sally ends up in position 3。

 and we have three items in any four long array。Now here's an interesting thing you will see here when we go through the rehashing Z in the two two long array。

 Z was in position 0， but in the four long array， z' is in position 2 because this is rehashing Now what happens is is that's because whatever the hash value for z was modo 2 is 0 but。

Moulular 4 is2。 that and so the positions don't change。Right， it wasn't。

 It wasn't going to end up in position 1。But。Modulo2 and Moo4 are multiples of each other。

 but you'll see you see in this case here， Sai Z Sally。The position of Z moved。 And so again。

 if you're writing an iterator that's going through this and you just inserted one and it reallocated in that。

 that's why Python 1 dictionaries and literally any hash based dictionary。 that's truly using hash。

 We'll see how it worked in Python 3 in a second。 but。When we reallocate things。

 stuff gets shuffled around。 So the order is different。 So we made space for Sally。

 and then we put a equals D in。 Now the thing we're triggering is if it's greater than 60% full one。

 when you have one and you got two， that's 50% full。

 And that's why the sai equals B did not trigger a reallocation。

 But if we have three items in a four slots， that's above 60%。

 And so we're going to reallocate And so even though we could a snuck it in that last spot。

 that's not good for hashing。So we're going to say， you know what。

 it's time to make this bigger again。So we're going to make so a equals D。

 we're going to make space for a。And they're going to double the size of the array to be 8。

 And let's see we got sai equals B in position 1。 We got Z equals W in position 2。

 We got Sally equals C in position 3 and a equals D in position 4 and we're half full at this point。

 So we're done now。 we have a length of4 and we say， hey， let's look up Z and yes。

 we get W and let's look up X and the answer is， there is no X。 And so our code is working doing。

 you know， our little unit test。Our little unit test is kind of doing dictionary things。So。

 let's take a look at。Put。Okay let's take a look at print， because prints easier。

 Let's take a look at print。Because print teaches us a little bit about the data structure。Okay， so。

Oh come back， come back， come back。 So in P1 died underscore print。

 the whole little first equals one。 that's just there so that we put the comma out but。

The nice thing is it's a for loop。For I equals 0， I less than self ac。 Now。

 if we look at the P1 list， let's go look at P1 list。The P1 list， the array the its I equals 0。

 I less than self length。 And that's because in the list。

 we just append in the beginning of the array sub 0 sub one sub two sub 3。 That's how this work。

 But because we're using hashing。Our array is like sparse in that it starts out empty and we start using slots。

 but we don't use every slot in order。So weve got to go through all the slots to iterate through a dictionary array。

And if it's null， remember if self items subi dot key equal equal null， continue。

 which means skip empty slots。Skip empty slots。 So this， this array could have 100 things in it。

 And if we only put one。Where the thing is inserted。

 which you're going to see in a second with insert。Is dependent on the hash function。

 because we're not just inserting them linearly。 We're inserting them based on hash function using open hashing。

 And so we have to skip the empty items。 But after that， it's okay。 We just print them。

 And so we're iterating through。This array of pointers。

 skipping empty empty entries and printing out the entries that exist every time we're doing an underscore print。

 and so we're seeing them in the order that they got spread out using the hashing function。Okay。

 and so you can see that it prints the key and it prints the value and then it prints the I。

 the position， and so that leads to you know very， very pretty stuff and then we print the length in the ac and so this is great for debugging。

Great for debugging for us。Okay， so that kind of reviews that the items is a sparse array with nulls being our way of marking emptiness Okay。

 so again， if you go back to the underscore new。We allocated it and we set everything to null。Okay。

 so let's go look at the underscore put because that's where all the good stuff happens。

 it's a bit of work。YeahCan I get it all on one screen， No， I can't get it all on one screen。Okay。

So we'll just work through it。So。The first thing we have to do is we have to figure out。

Which of the slots in this array？The key belongs in。Which of the slots。In the array。

 does the key belong in。So we're going to use a utility thing we write we wrote called P1 di underscore find to say find me the entry in the array。

That。Is the right entry for this particular key。Okay。

 so now we've got to go look at that P1 diict find。Okay。So this is pretty straightforward。And so。

This is open hashing。And so the way open hashing works is it starts by doing a hash computation to figure out a position。

In this array of items。And get Buck。You've seen this in other code that I wrote。

Git bucket is just a crappy little hash function。That does a shift and an exclusive or repeatedly going through the entire string with the idea of creating a pseudoran number that is deterministic based on the string that I can then take the modulo of the number of buckets。

 so this ends up with a relatively large integer that in long strings might even overflow and again。

 hashing computing hash functions is a is a research area unto itself。

 this is a terrible hashsing function。But。I've used it over and over and over again because it's short and gives me some random some pseudo randomness。

 but it's probably a highly collision resistance。 So the whole idea is。If I have。

Two buckets this gives me a deterministic number between zero and2， but not including two Okay。

 so let's go back to the find operation。So。We。We get the bucket。And that bucket might be。Well。

 let's say it's bigger。 Let's say we've got 16 slots and they're all empty。

The way it works is bucket it'll say， okay， hopefully you're slot5。The problem is。

Is then there's what's called collision resolution。And if slot 5 is already filled。Slot。

 youve got to find another slot。And but you got to find another slot in a way that later after it's in there。

 you can find it again， find the key again。And so we do linear hashing。

 we do linear collision resolution。Which means if we find ourselves hashing to position 5 and position 5 is full。

 we say， oh， well， let's just linearly go forward。 Let's look at 6。 Let's look at 7， then 8，9。

 whatever。 And then when we get to the end， we go 0，1，2，3，4，5。

 And if we get to the point where we have checked all the slots。 and they're all full。

 Then we kinda have to blow up。 And that's where it says printf could not find slot for key。

 That would be like throwing an exception。 We'll just print it out here， because But that'd be like。

 something went wrong， because you're never supposed to 100 per cent allocate a hash。

About 60 or 70 per cent is when you're supposed to quit and double it or expend it in some other way。

 So let's look at the code that hunts for a starting at position 5 hunts for a free position。

And so we say offset equals zero， offset less than self alloc offset plus plus。

 so that's going to go if we have like eight entries， that's going to go from zero to seven。

But we really want to start that iterator in five and then wrap around when we get to eight， okay？

And so I just， I call it offset， but then I calculate the position in the in the array as offset plus the number of buckets。

 I mean， offset plus the bucket， which is five。 and then modo self aex。 So if we got8。

Off that's going to go from 0 through 7。 And if and the bucket is 5。

 that's going to go from 5 through 7 and then 0 through 4。 Okay， so I is the circular。Look。

 so we're doing a circular lookup in an array starting at five。 we're going to look through every。

 if necessary， every single position in that array is going to be checked。

So we're starting at like five where the hash function told us to go and if selfite sub5。

 key is null， it's in great spot， that means that the hash function pointed us to a available entry and we're done so we return the address Ampersand selfarrow items subi。

Otherwise。We might have found something that's full。

 and we don't know right now if we're going to replace this value or not。

 But if the key matches what we're looking for， we actually found the right one。

And so we returned self， the address of self items I。And if we didn't find an empty one and。

And we didn't find one that was full with a matching key。

 Then what we've got to do is go back up into the for loop and go down one。 So if we were at 5。

 and we， it was full， but the key didn't match， then we would go to 6。And if6 was full。

 and the key didn't match。We go to 7。 If 7 was empty， then we're done。 So we say， oh。

7's the where we're going to go。 And so you can see if you think about this for a little while。

 and you go read the the lecture slide on open hashing。

You can see that as long as there's space in this array and it's not completely full。

 eventually we're going to find a place。Okay， we're either going to find a place that matches the key of what we're going to find an empty place。

 and that's what Fe's job is to do。And again， as long as resize is working and we never let it get to be above 70%。

We can always find a slot for the key。Okay， so this again。

 when we say printf could not find slot for key， that's really。Traceback time。

 because that means that the thing above us， which we're going to look at now。

 is going to be going to blow up。 Okay， so let's look at underscore put again。是。

C them underscore put。So。A lot of work gets done in underscore find where we hash the key。

 and then we do the linear。 we do the linear look up if it。we do the linear look up。

For cl collision resolution， and we either have an empty entry。Or we have the actual entry。

And so the first if statement we have afterwards is if old is not null and the key is not null。

 that means we just found it。Which means all we got to do is replace the value。

 We don't have to add any entries。 The index is great。 The array is great。

 So we just free the old value， and we allocate the new value。 And then we just string copy it in。

 And away we go。 So that's， that's when we did the。That's when we did the Z equals W。

 That was the code that ran to basically say， oh， well， we found Z。

 So we just to we have to free the original string and the original string is catchphse。

 and the second string is W。 So we're replacing catchphse with W。

 And this little bit of code right after the underscore find is the thing that does here we found it。

Okay。But so that's that's the second one， let's go back to z equals catchphse because z equals catchphse is not found because we're starting with an empty array。

So that means it。Old key， we're going to get an old because the hash will find a slot and that slot will be empty and it'll give us back to us。

But old key is going to be no， which means this one is available， which is cool。Okay。Now。Actually。

This to do is no tu do， not a tudo any more。Right now， it's going to be an ignore。So this is the bit。

 okay， I'll come back to this， okay， this is the tricky bit。

Now I never did this in Carnegan and Richie。I don't think。I have to check。

But this is called rehashing， and this is when。Our length is greater than or equal to 70% of our allocation。

 which means this array is more than 70 per full。That's when we're going to do this reallocation。

 okay？But I'm going to ignore that whole， if statement for now。I'll come back。

So we're processing z equals catchphse here。And Z ends up。

 we can even look ends up in sub0 of the array。And so if it's time to insert。

 this part is really easy。So it's time to insert， We're going to allocate the key。The value， Mal。

 the value and Malic the key。And string， copy them in。The old already exists。

 Old is a pointer into an entry into an array that's got a key in a value。Okay。

 so there's an array of。Key value pairs。 And so we don't have to allocate the old itself because the old is already in the array。

 but we do have to allocate the strings that we've been passed as parameters。

 And then we add one to the length。And so that's basically how it ran when we're doing Z equals catchph。

 At the end， we had Z in position 0。 We had a length of1 and an ac of two。Okay。

So now we're going to look at。Were we've got a。And you'll notice that my 0。7。

 let's go back to that now because we're going to look at that。This is kind a tricky。Okay。

 so this whole self length greater than or equal to aic 。7。I kind of it。

It allowed me because it was only two items。 It allowed me to fill it up completely because one item is only 0。

5。And so when I put s equals B in， I didn't trigger the reallocation。

So it just put it in position one， I don't know if。🤧。Ohsai did go into position one。 so。

 but now we're doing C。 And it's like， I could not find a slot for Key Sally。And so。That means。

Could not find slot for key Sally。 So that means that it's searched。 Let's go back to find。

I guess this is not really a traceback， this is just a fact。

So it went and looked at hashed this the what's the key and that again， Sally， that key is Sally。

 it hashed the Sally found a starting point with bucket that hash just found a bucket。

And where did Sally want to go， Sally ends up well in three， but a pride of been a one。

 Sally would have been bucket one before it got expanded。And then it looked through the whole thing。

 which in this case was only two， and it couldn't find either an empty one or one that matched Sally。

 and so we say， can't find it， return no。Okay。And so now we get back to put。So we're doing Sally now。

And we find old is actually null， so this code doesn't run。So we didn't find an entry。

Old key is not even allowed， we're not even allowed to say old arrow key because old is no。And now。

Fine didn't find it， which could be bad， but we're going to fix it。Come back。

 come back or want to fix it。So we're coming through here and we're saying if self length is too full。

 greater than 70% full。Then we're going to make space。 So you can see here in the output。

 it says we are making space for Sally。 We're still in the middle of the put of Sally equals C。

Right and so。We're going to grab a copy of the old allocation number and the old items。

 Those are just integers。And then what we're going to do is we're going to make a brand new empty。

Items。And so we are going to double the size of our array。And then we are going to set the new items。

 That's why I had this more old items here。 We're going to set the new items to be。f。D nodes。

 it's an array of 4 D nodes。 Now we've got to be really careful。

 This is kind of like a constructor for that items。

 We're going to set the key and the value of the newly allocated four items in that array to null because they start empty。

 You'll see a sec that we got a re atom。 So we're kind of creating an empty array。

 That's twice as big。And now what we got to do， and this is why we call this rehashing。

 is we got to go through the old array。And find all those items。

 and then we got to add them in the right spot。And this is where you'll notice that Z was in position  zero and Z ends up in the reallocated rehash array in position 2。

 so you really have to rehash it because all the rules in the new one have to be followed。

 the initial hash， the linear resolution of conflicts of collisions， et ceter。

So you really think of this items as a brand new one and we've got the old items sitting there not much longer。

 but we're going to go through them all and we're going to just add them again now。哎。Yeah， so。

 so we're going through all of the old items。 If the key is null。

 that's one of the empty slots in old items continue。 Then we're going to call find again。

 And the key thing there is that's why we made self items be the new thing is so we could call find。

 So that's the first time it's being called in this loop。 The the new items is completely empty。

 But old items ice of key is the key。And then。And so。Let's see what we got here。Yeah， so new item。

 if new item is null， that means it didn't find space。 Now。

 we just doubled the space so that shouldn't happen。

And given that the keys in old items are already unique because this is a dictionary。

 we should never find。In the new empty， the key twice。 So that basically， that basically says， oh。

 it's already in there。 And the answer is wait， wait， wait， we started with an empty one。

 So new item key not equals null is a bad thing。But it should never happen because we're going。

 we have a unique。Each key is unique。 There are no duplicates。

 And so as we're inserting them again into a new hash map。Aray。ThatWe should never get it。

 So that's why it's a very bad news。 That means that we either couldn't find space。

 because I don't know why。Or it's already in there。

 which I don't know why either that means that this is like trace back time。

 this is like the runtime library is not well formed and we made a bug in our runtime library。

So then。That means that new items should be non null and it should be empty。

 which means we can just like copy Now this is just a pointer copy。

 it's not actually the stuff because we take the key is the pointer to the key。

 the string array and the value is the pointer to the string array so we say new item key equals old items sub dot key and the same thing for value and so now what we've done is we've copied all of the old items and we've positioned them correctly in the new items。

So at this point， we're done and the free here is simpler because we're not freeing the strings because we just copied those。

We are freeing the array。Okay， so we're freeing the old array。

 free old underscore items freeze the old array。Now what we need to do。

Is we need to search for the position because we're going back to。Put Sally equals C。

And so Sally is the key that we're putting in， so we just made space for Sally。Now again。

 if Sally was already in there， this code would have run and we' be done。

And so we have to relook in the new， the newly expanded array， we got to find the right spot。

And again。If Sally was already in there， this code would have been run and we'd never read down here。

So we have to redo this and say， okay， where is Sally？In this case， we really。

 where should Sally be long because。We just made more space。

And so old equals nu would mean don we still don't have space for Sally。

 even though we doubled the darn thing， or yeah， we doubled it。An old key not equal no。

 that means that we Sally's already in there， wait a second。If Sally was in there。

 we'd not even come down here。 So again， the selling old key， not equal。 again。

 you put out these kind of tracebacky， very， very bad news。 That is like。Somebody our code our code。

 we're the library writer， our code is messing up。So old is really supposed to find， no matter what。

We're adding Sally to the dictionary， old， got to find a slot for us。Or we just our code is broken。

So this is me debugging and leaving this in， you know， just to make sure like， oh man。

 that is impossible， should never happen， but I'm going to say。Very bad news。So it finds a slot。

 and then we just copy the key and the value and increment at length。🤧And so this whole reic thing。

Is kind of new。 I don't think I did this when I did the Carnegan and Richie。

 because the way Keringgan and Ritchie does it， you can just keep extending those link lists。

 like if you look。 So if we look at the underscore put in the Knegiegan and Rie code。

 you'll see I do a get bucket， right。And I find a bucket。And if it matches。

There's always a bucket in this one because it's the buckets are pointers to link list。

 So there's always a bucket。 There's no resolution by linear collision resolution。 So if we find it。

 we just copy the value。 in this I had integer values。And then otherwise you just append。

To the end of the tail of the bucket。Using， you know， self head sub bucketet equal all new。

 and then it's just at that point， this is just cement and P in KR diic。

We don't have to reallocate now you would want to reallocate at some point because then these chains。

Get too long。 And that's。 And so it's not like you don't have to reallocate with these chains。

 I didn't write it。 So the reallocation would be sort of。In the middle of put。

 and it'd be very complex code， and it would be actually probably you about the same complexity。

 maybe a little bit more complex than what the Python 1 implementation was。And so with that。

 I think I pretty much have covered the essential differences between the Carnigan and Richie dictionary code that I wrote and the。

Basic approach。听了。The basic approach using an array of denode items。

 and if we look at find a linear collision resolution and the linear collision resolution。

Let's do this， I'll put a comment in here。Linear and underscore fine。I can't。

I got to figure out how to spell collision。Well， the version you see will have。あ。How many ss， No。

 how many Ls。Okay， I'll fix that for you。 And so this is linear collision resolution。

 And that that's tricky stuff。 And so you want to take a look at that and understand that very carefully so。

🎼I hope that you found this lecture useful， I think the next thing we're going to talk about is how dictionaries changed from Python1 through 3。

6 all the way up through Python 37 because the dictionaries did change and got a lot better so we'll talk about that soon。

 cheers。

![](img/5410a62ed2645451ea3ea9662e58a072_4.png)

![](img/5410a62ed2645451ea3ea9662e58a072_5.png)

🎼Yeah。🎼Yeah。

![](img/5410a62ed2645451ea3ea9662e58a072_7.png)
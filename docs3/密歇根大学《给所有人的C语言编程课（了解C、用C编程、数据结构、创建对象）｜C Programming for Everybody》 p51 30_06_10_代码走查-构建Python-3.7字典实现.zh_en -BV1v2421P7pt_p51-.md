# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p51 30_06_10_代码走查-构建Python-3.7字典实现.zh_en -BV1v2421P7pt_p51-

![](img/adda044b76f4126dbef5c32c077b7d61_0.png)

Hello and welcome to another programming walkthrough for C programming for everybody。

 this is one of the last walkthroughs for the epilogue code and in this walkthrough we are going to look at how dictionary。

 the internal data structures in Python for dictionaries changed between the first version and the 3。

7 version and so we talked previously P1 diicted。c about in effect Python 0。01 through Python 3。6。

And then Python 3。7 and later has a new dictionary that maintains insert order。

 but it also saves a lot in terms of efficiency。 So here is our approximation and simplification of the Python 3。

7 dictionary。嗯。And so let's talk a little bit about the problem that the Python 3。

7 dictionary solved by looking at the Python 0。01 dictionary。 Now。

 if you listen to the E Van Rassom video that I've got。

These key value pairs in the real version of the dictionary。

 it stores a pointer to a key pointer to the value and the hash value。

 So it doesn't have to recompute the hash。 Now， I kept it simple and all my stuff was going to be small。

 So I didnt didn't do this optimization to recompute the hash。 I could have。

 but I just kind of want to keep a coat as small as possible。

 So I just recompute the hash in a few places I need it。But this means that in a 64 bit system。

 this is  three times8 or 24 bytes， and the problem is。

 let me delete this line so I don't break my code。The load factor。

 we never let the load factor get above 0。7， which means that by definition and the larger the structure gets。

 the larger the wastages，30% of the entries have to be empty。In the key value pair array， and again。

 that's 30% of 24 bytes。Wasteted 30% of the size of the array times 24 bytes that's always wasted。

 you cannot not waste it。And so what happened is is that in the Python 37 version， in effect items。

Started was treated more like a simple linear array of pointers to key value pairs。

 So now you've got your key value pair in Python is key value hash and a few other things。

 So this is a larger data structure deode is a larger data structure and then we have a separate simple integer array that is the index because items is an array。

An index is the offset into that array， but that's just one integer。

And so we're going to do all the hash indexing and resolution and conflict resolution and closinging resolution in this index array。

 which itself is a much smaller item。 and I'm going to just make it。

 And I don't know if Python does this， I'm just going to let index be twice as long as items。

 which means from an indexing perspective， we never get a load factor above 50%。

 and we're only going to extend the array when we run out of space in items。

And we're going to store the key value pairs linearly，0，1，2，3，4，5 in items。

 And then we're going to just reallogcate。 So in many ways。All of a sudden kind of realliing。

 let me open a new tab here， P1 list。Got C， the reallican code。If we go back to the P1 list。

 extend if necessary， you're going to see that in P1 list append and P3 list append。

 we're going to see that it looks a lot like the relic pattern in the Python list because it is an array。

the actual key value pairs are stored linearly in an array。

 and that's also how you end up with maintaining insert order。

 wasn't they tried to maintain insert order， but at some point if you're just using a linear list， 0。

1，2，3，4。Insert order is going to be maintained。 And if you delete one， you shift them all up。

 and it just treats。 So I would guess it ultimately inside of。Python itself， after 3。7。

 there might be some overlap in the code between dictionary and list because they pulled out the hashing lookup in this separate data structure。

 which is an array of integers。Okay。So so then if we look at the theette bucket is the same。

 it allowsy hash function， I'd make did it as small as I could just so it didn't take up a lot of screen space。

If we look at the constructor， P3 dit to underscore new。

 we see we're allocating the actual dictionary object， and then we're allocating。2。

Key value pairs two struck D nodes， and then we're allocating four two times。

The aex size of integers。 And so our index is4 and our deode list， our deode array is。

Do you know what to array is two？And we don't have to initialize the key value pair array。

 the items array， because we know with length， which ones are valid and which ones aren't valid。

 But we do have to take this new index and put negative one in there。

 We did this little differently in Python 1 dictionary。 We use nullles。 But right now， I'm just。

 it's an array of integers。 And the negative one is going to be my marker。

That's going to be my market to say this is an available index slot。

Okay so that's what the data structures look like let's go ahead and run the code now you'll note that this code is in effect exactly the same as the P1 dict code that we went through before。

And so we'll run it and it'll look stunningly familiar。

Meaning that putting we're having an empty dictionary。

 we're putting Z equals catchphrase and putting Z equals W， si equals B， Sally equals C， a equals D。

 and we're printing it out。So now we're printing it out。 This is like an iterator。

 So Z catch phrase and then0 is。Is the position in the index， not the position in the items。

 It's the position in the index。 So this is in。Index position0。And when we get。

 and so we see Z maps to W， sai maps to D B， and they're in index position zero and1。

It's kind of hard to hash and we didn't and because we don't have to rehash until it's completely full。

Because then we have two items。The ali is 2。 so we can put z equals W and s equals B。

 Remember that index is 4 when ali is 2。 So index has four integers。

 So we still have a load factor of 50%。 But now what happens， we're going to put Sally equals C in。

And now， we have to extend。The items。And we automatically extend the index。

 so we have a 50% load average before the extend， and then we have a 50% load average after the extend。

Well， actually' a less than 50% load average， but the point is， is because I just， by definition。

 had my hash index be double the length。I never get to a low average of 0。5。Above 0。5。 And again。

 you can make this more complex and let the load average get to 0。7。

 but I'm keeping it really simple。 The other thing that you'll notice is in the rehash， again。

 thinking back to the Python 1。So you'll notice that the hash position of Z。

 just like in the previous one。After it went from 2 to 4， went from position 0 to position 2。

 And I talked about how it's not going to completely move randomly， but it hopped in this case。

 because whatever the hash value， modulo 2 was 0 and modulo 4 was 2。 And that's because 2 you know。

0 is modular 2。 So these things kind of go by powers of two like and so。

 but B equals one state in the same place， et cetera， et cea， et cetera。 And so。

 but here's the thing。 Notice the order of the things printing out。 These zeros and ones， et cetera。

 That's the hash position。 but it's not the position in items。 So Z equals catchph in item sub 0。

 Z equals W is in item sub 0。 Sai is B。 that's in items sub1。Hash position。

 So Z equals W in this output is in hash position 2， but items position 0。

 And so you'll notice that insert order is maintained in this unlike the P1。Again。

 this wasn't to make insert order work。 It was a side effect of changing the data structures to make items be just an indexed array。

 starting at 0。And again， pulling the hash computation， not up， sorry。Yeah。

 items is an array that's linear and index is an array that is looked up by hash。 Okay。

 so let's take a look。So let's take a look at put。And of course， the first thing we see is P3。Find。

And。Just underscore find。 Let's so recall from the previous one that the goal of find。

Is to bind a bucket。Position that's free and available， okay？And so。

Remember that get bucket is just the hash computation for that particular key we're looking for。

And we have the same kind of circular， this will give us a number between， you know， zero and eight。

Like zero through seven， if there's eight entries or zero through three， if there's four。

 zero through zero one if there's two。And then we have to go it with a circular look。 Okay。

 but you'll notice now when I say 4 offset equals 0 offset less than self ac times 2。

 I am now looping through the index array， not the items。Not the items array。

And I do the same little trick to do the modulo so that it goes like 56，7012，34， so I goes 56，7，0123。

4， which is exactly what you need to do to do collision resolution using linear probing。

 which is the way we do it。And it's very simple。 If we find an empty spot in the index。 now。

 the data is not an index， the data is still in items right， So if we find an empty spot in index。

 meaning it's a negative one， that's a free one。 And that's what we're going return。

 Notice that in this one， I'm returning an integer rather than a pointer。

 I probably should go back and change all those others to return integers instead of pointers because it I think makes code easier it looks a little more complex in some places。

 but easier to understand of other places。If it's negative one， we're done。If。We。

 we look at the key and we find in items now。 Now， this one's a little trickier。

 We're comparing the key to。Self items， which is the key value pairs， right， But it self index sub I。

 self index of I is the position。Within items of a particular key value pair。

So we have to look up using self index to find the right spot because self items is like a linear list。

 It's not really di。 It's not really a hash map。 The only thing that's hashing here is the index。

 And then we go grab the key out of the thing。 And if we match it， we're like， oh。

 this is the position。 Oh， by the way， I found it。So in our calling code。

 we'll check to see if it's empty or not。 but right now， if it's empty。

 we turn I and it's if it matches we return I， otherwise we keep。Incrementing。Now。

 the key thing is because。The the load factor is only 05。 This is always going to succeed。

 That's another nice thing about this。 It always is going to succeed because when we increase the size of。

Items， we also increase the size of index so that index is always two times the size of items。

So we never get a load factor above 0。5， which means this feels to me like a lot more reliable code。

And if we get， if we don't find an empty slot， which in the other one。

 that was a trigger for reallocation。 But in this one， we reallocate differently。

 So returning negative one， that's just like not a good sign。 Okay。

 so let's take a look again at at find， I mean， at the put。So this code here。

 when we do the find position equals P3 decked fine of the inserted key。We basically say。

 if the position。Is not equal to negative one。 That means this is a valid entry。

 which means we're replacing the value。 And again， that's the。

 that's the scenario where we have z equals catch phrase。 And then we say z equals W。

 We're just going to replace the value。 We're not going to change the key。

 The key is already in the right position。 The key is already hashed properly。 The index is correct。

 The items is correct。 and all we need to do。Is。Grab the value and get rid of it。

 and then allocate a new value and stir copy it in， and we're done。So we're done， so if you find it。

 that's great。Okay。So we don't find it， we have to insert it。

But we know where to insert it right here， but now what we do。

As we simply say if self length is greater than or equal to self allc。

 that's when we're going to expand it。So here we're saying if self length is greater than or equal to self aEC 0。

7。 Now the ac here is the number of things in the items， which we're using linearly。

 which means we can filled up 100% before we have to extend it。

 so we're looking to see if the length is greater than or equal to self a here we were looking is the length greater than equal to self ac times the load factor 0。

7。 that's only triggered in Python 1 dictionaries， but if we look。This， again。

 this append says if self now we're in P1 list， this is again。

 that duality between Python 1 lists and Python 37 dictionaries。Because in a sense。

 the items is just。A list。RightSo if self length， which means now it's full， weve it's 100% full。

 it's 100% utilized， there are no spaces in items。If self length is great in self aec。

 we're going to extend it。 so that means that this code here， self length， self aec。

It's really quite simple。So we just re the items。And Reelic twice and Reic。

 whatever we're going to do twice as big in this case。

 And so that is like exactly copied from the list。 We just realelic。Okay。

 so but now we got a little bit more work to do in Python 3 because the items was easy。

 We just reed it。 We did exactly what lists would do in this situation， but now。

We got to fix the index， okay？And so so self items at this point is right。Okay。

 so self items is right because reelect did all the work for us。 You know， we doubled the size of it。

But then it copied all that stuff。Okay， and the other thing we don't have to do here。

 which we did have to do in Python1 is we didn't have to set all these new items that have been allocated because。

In items because it's like a list， aEC and length， all that matters。

 and we haven't changed length yet。 we have changed Alec。

 So the fact there might be garbage and all that news data。

 it might be zeros might be garbage is okay。Now what we're going to do is rebuild the index。

Items hasn't moved。 and so we don't need it。 We just free index right now。 Remember。

 index is that in ager arrayrays that's twice ac。Right so now we just allocate another integer array that's twice the size of whatever we've got allocated in items。

An integer array， so selfarrow ac times 2 times size of int boom。

And then we just have a little for loop for I equals less than or equal to self a 2 I plus plus set it to negative of1 because what we're doing is we're creating a new completely empty index。

 The key value pairs are just sitting there happy as a clamp in items。

 But now we got to make a new index。 Okay， so we're going to refill this index。

 but it's really simple。😊，So now we're going not to aEC for I equals0， I less than self length。

 now we're going to go through the items and that's length。

And then we're going to call the find operation。Based on the key of each of the items。

And that's going to give us a position。And it's going to do conflict resolution。

 collision resolution using linear probing。And so at that point。

All the index at that position is the position is where in this array should it go。

And that means that， you know， if it's in the third position in the hash map and we're looking at the zeroth position in items。

 I is 0 and position is 3。And so this code， if you compare this code again。It's better memory wise。

 if you compare this code to the code inside， if you compare this reala code between。

The Python1 code。And the Python three code。Oh， and， oh。

 and I don't even do it in K R because it was going to be so ugly。 I didn't want to show it to you。

 right， So it's ugly in Python 1。 It is pretty in Python 2。 I'm seriously。 this。

 you'd look at this for look at this code in underscore put for a while。 And you were like。🤢。

Why didn't they think of that back in 1989， Why did it take him till whatever 20000。

18 or something to see this。 It's a beautiful data structure， right， It is a。

 it is a beautiful data structure。 Okay， so here we are in this code where we have refilled the index。

😊，And again， self index is changing， right and because that's how the conflict resolution works and positions in the index might be different before and after。

So。After that。We're done extending。 We're going to have to do the actual insert because the reason we extended to do is we were going to insert a new thing in this case。

 if we look at we're trying to put Sally equals C in， then we extend from2 through 4。

 And now we're like done extending。 And so we got to put Sally in， right？ So Sally's going to go in。

 And this is the insert code that we've already looked at。 right？

 But we do have to go find its the position of Sally because we found it before in the。

Pre expanded index slash items。 And now we're finding it in the post expanded index slash items。

 But then we just allocate the key and the value， copy them in and then add。

The key value pair at the end of length， which is。Not aec。

 but length is like the next position in that linear array of items， so we're new items。

We set the new key， the new value， and then we set the index to be pointing at this entry in self items because index is an integer。

 So it's like if we're putting it in， So if we're exp from2 to 4 and we're going to now use3。

Position two， actually， self index， whatever has the position is computed by hashing and linear collision to clean up and then we set it the length and we add one to the length。

So if you watch kind of all this stuff， it， it just。Of of these four lines of code。

Only one of those lines has to do with hashing， and that is the self index position equals self length。

we're recording it's kind of like recording a cookie crumb in the Hansel Gl。

 so so we're just remembering in the index where that is so we can jump to the right position in index quickly using hashing rather than doing a linear scan of the key value pairs but literally if you took this index away。

 you have just a list and so again， let's look at Python list。Yeah， this is simpler because I'm not。

Yeah。But all it does is it extend extends this was a list of strings。

 so it's actually a little simpler， but all it does is it copies the string and then puts it at the end and then adds one to the length and it's done。

 And so the Python 3 dictionary does that。It's kinda cool。So as we put Sally C， it extends it。

It recomputes the index， and that's why the hash position of Z moved， but not the position in items。

 The position in index moved because it sub2。Z maps to W in position2。 That's the index position。

 not the items position。 The items position is just like a link Li Z is in0。

 sai in sub 1 and Sally is in sub2。 and so that's insert order and everything works。🎼Pretty well。

🎼And so， for me。As I think about like the Python III dictionary and compare that to。Classic。

Cernegan and Richitchie Dictionary where I didn't where the classic Carnegan and Richie Dictionary was。

So complex on rehashing。That I didn't even write code for it， I'm like。

 oh let's pretend that's not a problem okay， and now I can tell you in the Python3 code。

I can tell you， I can go all the way through the rehashing and tell you that it's some of the more beautiful code。

🎼That I've seen。So I hope that you found this valuable。Cheers and hope to see you online。



![](img/adda044b76f4126dbef5c32c077b7d61_2.png)

🎼Okay。

![](img/adda044b76f4126dbef5c32c077b7d61_4.png)

🎼Yeah。Yeah。

![](img/adda044b76f4126dbef5c32c077b7d61_6.png)
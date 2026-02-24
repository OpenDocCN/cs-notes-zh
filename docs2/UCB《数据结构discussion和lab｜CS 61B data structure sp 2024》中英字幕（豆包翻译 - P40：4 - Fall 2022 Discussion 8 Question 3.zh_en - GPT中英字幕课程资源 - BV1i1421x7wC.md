# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P40：4 - Fall 2022 Discussion 8 Question 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/d5638bee31cd95dfc3d7909429d620aa_0.png)

不是。Okay， let's move on to question three， a side of hash browns。

 and here we just want to draw the hash map after the following operations that we do on it。

 So just a bunch of puts。We're using a hash map that maps a string to an integer。

 and we for simplicity purposes， we are going to start off our hashmap with only four buckets。

Okay and to make things easy， we're going to pretend like the hash code of a string just takes the first letter of that string and hashes it to whatever integer that corresponds to in the alphabet so that means that as the first inposition zero of the alphabet as these zeroth index of the alphabet A would hash to0 B would hash to1 D would hash to3 Z would hash to 26 so on and so forth。

 hopefully you see how like that hashing scheme works and so for example。

 if we were to look at hash grounds over here it starts with the letter H H corresponds to the integer 7 if we zero index starting from a and so this hash grounds would hash to7 okay。

So one more thing to note is that we want to for this question I know it's not on this slide sorry but we want to resize when our load factor is three4s and just remember that load factor is just the number of elements that are in our hash mapap divided by the number of bucket that we had and here we said that we're starting with four buckets okay so first if we try to put a hash browns and map it to seven in our hash mapap we're going to look at our key which is hash browns take the first letter which is H and hash that according to its position in the alphabet and down here we have this helpful little chart that tells us that H is going to hash to7 so now we know that there's four buckets so we know that the bucket the hash browns is going to end up in is going to be seven mod4 which is three so we're going to put this entry of hash browns comma 7 into bucket number three okay。

And over here， you'll see our load factor calculation where we have one element in our hash mapap and four buckets。

 and so our load factor is only 25% right now， okay？😊，Now if we try to insert dim sum。

 dim sum starts with the letter D D corresponds to the number three in our alphabet。

 so three mod4 is three so dim sum is also that entry is also going to end up in bucket three and since we're using external chaining here。

 we're going to tack it on after a link so it's like a little like a length list okay so dim sum is going to come after hash browns in bucket number three。

Next， when we try to put in S cargo， S cargo's first letter is E that is the number four in our on4 mod4 is0。

 so we know that S cargo， the entry is going to end up in our bucket number zero。

Now we've reached a point where we now need to resize right because our load factor is three forts。

 So what do we mean by resizing this entails two things。 number one。

 we're going double the number of buckets that we have right and number two。

 we now need to rehash the elements in our hashmap why do we need to do this Well before remember that we determine where each entry in our hashmap was going to go based on the length of our buckets are array based on how many buckets we had right we determined that even though hash browns。

 which starts with the letter H and hashes to7， even though it starts it should hash to bucket number 7 before we only had four buckets so we had to do seven mod4 which gave us three And so hash browns ended up in bucket3 So now if we try to like search for hash browns。

 we're going to try to mod 7 we we' try to do seven mod。The number of buckets that we currently have。

 which is eight which would give us seven so we tried to look for hash browns and bucket number seven。

 which isn't going to help us if we don't rehash our keys so that's what we mean by。

Rehashing the elements of our hash map basically after we resize were're not guaranteed that the particular elements that we hash previously should still be in those like buckets and we can see if they need to move around so s cargo was for mod。

😊，Sorry let me face that Scargo started with the letter E so that was four and then we did a four mod for originally which is how it ended up in bucket number 0。

 but now since we have eight buckets we'll do four mod8 and Scargo is going to end up in bucket number four and we just discussed this but hash browns is going to end up in bucket number7 right seven mod8 is7 so hash browns is going to come down here and dim sum starts with the letter D which corresponds to three3 mod8 is still three so dim sum is just going to remain in bucket number three so basically when I click to the next slide you'll see that Scargo is now in bucket4 hash browns is in bucket7 and dim sum is still in bucket3。

Cool， and our load factor is now38。Now， if we try to put in brown bananas。

 brown starts with the letter B， so that's going to correspond to the integer1， one mod is one。

 so ground bananas is going to go in bucket number one。Likewise。

 with burritos when we try to put burritos in， B will hash to1，1 mod8。

 the number of buckets is still one， so we're going to attack on burritos at the end here after brown banana in bucket one。

Buffalo wings also starts with the letter B so we're once again going to hash B to one1 mod8 is one and buffalo wings is going to get tacked on as a link after burritos and now。

😊，We need to resize again because we've now hit the three fourths load load factor limit。

 so we're going to double the size of our buckets okay and I。

There's like not enough space on this slide to show 16 buckets， but we doubled from 8 to 16 buckets。

 right？ And now let's think about rehashing everything。 So these B letters。 they start with letter B。

 that hashes to11 mod 16 is still 1。 So none of these are gonna move dim sum starts with the letter D。

 that corresponds to the integer 3，3 mod 16 is still 3。 So this one isn't gonna move likewise with4。

 right， the E corresponds to 4，4 mod 16， still 4， even hash browns。

 which starts with the letter H which would mod sorry， which would hash to 7，7 mod 16 is still 7。

 So even though we double the size。Of our。Of like our buckets it didn't even do anything right like we didn't have to rehash any of these because they are still in the same buckets regardless of how long our buckets were right so that means that now when we put in Boon me we have our nice resized hash map。

And we're going to put in bottomomy， we're going to see the B that's going to be the integer one that's going to hash to one。

1 mod 16 is one。 So we're going to add that on as a link in bucket number one。And finally。

 if we try to do put burritos 10， we're going to take a look at the burritos it starts with the letter B so we're going to hash that to one1 month 16 is one we're gonna look in bucket number one and as we're traversing through this chain of B words we're going realize that burrito sorry this should say burritos but I don't know why it should say burritos though we're going to notice that burritos is already an entry in our map and since we know that keys in a hash map should be there shouldn't be duplicates of keys and a hash mapap what we're going to do here is we're going to stop here and say okay I see that there's already a burrito's key in here I'm just going to replace the value two with this updated value of 10 because burritos are really yummy we're going to replace this yummyiness value of  two with 10。

And it's just going to look like that and we'll notice that our load factor does not change right our load factor is still7 out of 16 because we didn't add just because we tried to put burritos in doesn't mean it actually added a new entry right because burritos was already a key in our map Okay so this is what the final hashmap is going to look like all right。

So now you might have noticed that I kind of breezed through the last five puts here because all these started with the letter B right so I knew what they were going to hash you but that in and of itself is problematic with the behavior of our hashm so in theory if we put in a ton of words that started with the same letter that gives us like a lot of items in the same bucket right and in theory we resize our hashmap because we want our hashmap to be able to distribute elements evenly right but you'll notice here that because the。

Because we are hashing our keys based on the first letter of our keys。

 there's only 26 letters in the alphabet right which means that the result of our hash is only ever going to take on 26 values so that means that even as our load factor gets really big like we let's say we keep adding elements to our hash map。

 our load factor could get really really big but it won't ever distribute the elements and the first 26 buckets beyond those first 26 buckets right even though we resize and try to keep our load factor load。

 it doesn't change the fact that our operations are going to be slow because all of our elements are effectively going to be clustered in the first 25 buckets。

 even after we keep resizing and keep resizing based on load factor which could take us to like thousands and thousands of buckets so that's really inefficient right？

And so a solution to this would just to be have a better hash function like the hash function that we were using for simplicity where we took the first letter and hash that that was like really like that was very simple right like so that lets you like a ton。

 a ton of collisions and wasn't super helpful in getting us to spread out our elements nicely a cl across our hashmap so I'm not going to go into like depth as like what a better hash function would be specifically but if you're curious you can definitely look up Java is built in hash function for these string the actual string object because it's a lot more complex than what we were doing here and that's it for 3B。

😊。

![](img/d5638bee31cd95dfc3d7909429d620aa_2.png)
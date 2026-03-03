# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p37 16_05_02_理解哈希计算原理.zh_en -BV1v2421P7pt_p37-

![](img/6eb63111da8605488720b8d0efb6d739_0.png)

So now we're going to talk about a hashedbased implementation of our map。

 And this is the answer to the world's most common programming interview question。

 but we're going to do hash maps and then tree maps。 tree maps are harder。

 So hash maps turn out to be beautifully simple。 And that's kind of the reason that everyone likes these as interview questions because the interviewer can remember the answer。

 A treemap， they might have trouble remembering。 And so it's the perfect thing in an interview to say。

 draw me a hash mapap because they know they still remember the answer from when they went to school。

 they'd have to do a little review to get the tree map right。 So here we go。

 So let's talk a little bit about a hashmap implementation。 It's got a weird order。

 And once you see the data structure internally， it'll be clear why there's a weird order。

 It is like a Python2 dictionary and it's like a Java hash map。

 It's very similar to both of these things。 I'm guessing the code we're going to write is very similar to when you know made his first dictionary。

 It's going extremely。Fast insert and looked up。Just like Python 2 dictionaries and Java hash Maps。

 it's going to be iterable like Python2's dictionaries and Java hash Mapss。

 and it builds on linked lists。Surprisingly， it's really easy to build a hash。

L hashmap if you understand， link list。And so it's covered in chapter 6。5。1 and 6。

6 and Carnegie and Richitchie， 6。5。2 is literally the hardest。Part of the book。And。

That's why we kind of start with 6。6 and then kind of go back to 6。5。Okay。

 so let's take a look at our data structures and how we're going to go from the list map to the hash map。

So our list map is pretty simple， we've got the entries in the map。

 which are key value which we've decided are going to stay public。

 we've got to approve in the next for the map entry which is just you know we're going to link these things together and then the list map itself it's got a head and it's got a tail and maybe a count and a few other things and then the methods etc because we've done encapsulation so the hash map entry if you look at it。

 it's pretty much identical and that's because the entries in a hash map are just part of a link list。

 the key to the hashm is there's multiple link list and we see that。



![](img/6eb63111da8605488720b8d0efb6d739_2.png)

Instruct hashmap and underscorecar buckets is how many buckets we have in a more sophisticated hashmap implementation。

 we would have the number of buckets grow as size grew and the list got too long。

 but we're going to keep that so that's called rehashing and we're going to keep that out of our conversation so but we're going to have a number of buckets and in this case it's going to be eight So those are called hash buckets and then we're going to have heads。



![](img/6eb63111da8605488720b8d0efb6d739_4.png)

Plural， organ' going to8 of them， and tails eight of them。But within a particular head and the tail。

 it really is a hash map， so as you're writing the code for the hash mapap。



![](img/6eb63111da8605488720b8d0efb6d739_6.png)

Go back to the list map。 I mean， literally copy the list map code and then change the singular to plural。

 and you'll see some of the things I show you in the actual code。

 So if we look at how a list map looks， it's got a ahead and it's got a bunch of entries that have pres and nexts。

 I'm not even showing the preves in the arrow as I'm just showing the next。

 but assume soon there's always pres there because it's a way for us to link things in。

But if you look at the hash mapap。So you take the actual key， you run it through a hash function。

 which creates some big number no matter how， but it is just a number no matter how long the key is。

 it can be one character or 2000 characters eventually a hash runs a calculation that gives us back a number。

 sort of a pseudorandom number that has you equally likely and there's a whole science of hashing。

 and then we take a modulo and in this case we have but four buckets。

 so we take this hash calculation， modulo4， and that gives us a number from zero through three。



![](img/6eb63111da8605488720b8d0efb6d739_8.png)

And with that number， we picked the linked list， and then we add it to the linked list just as if。

We were doing。This was a linked list， so the once we've done the hash and we picked a bucket。

It really is exactly the same as the linked list。So a hash map with four buckets is the same as four linked lists and you pick the linked list by the hash computation and hash computation is deterministic and predictable so wherever we put D。

 it's going to be in bucket1 and we can look it up in bucket1， we can store it in bucket1， etc。

 and so for inserting M equals 90 of that's going to hash into bucket 2 and we're going to put it in that linked list okay so it is beautifully simple。



![](img/6eb63111da8605488720b8d0efb6d739_10.png)

Now， what is a hash calculation。 This is actually from my Postgres for everybody course。 Basically。

 the hash maps large data items to a single。A single number basically。

 and these are called hash values。 so the whole concept of a hash function。

When used with a modulo in this case， I've got 16， modullo is 16 in this picture。

It maps a big string into some fixed number of buckets and often the buckets are power of two。

 but they don't have to be， it's really a modular operation。

And so there's a whole science of hashing and hash functions。

 and it turns out the hashing and hash functions。Are a big part of security and digital signatures and all that stuff。

 and so there is there are people who spend their whole lives researching how to build good hash functions and so there's this Shah 256 compression function you can go look it up。



![](img/6eb63111da8605488720b8d0efb6d739_12.png)

You can see what's going on here is like the arrows are shifting and the plus with a circle is exclusive ors and they sort of both show you the shifting and the exclusive or and they give you a diagram of how these things and they shift an exclusive or ya and they're taking the pieces of a value。

 it's computed in a loop and updated and what they're showing you is what happens。



![](img/6eb63111da8605488720b8d0efb6d739_14.png)

Each iteration through the loop and so the idea is is we are going to take a string， string array。

 and we're going to take a number of buckets。And the idea of a hash。It is just some integer number。

And we're going to go through each of the items each of the characters in the string。

 that's the four star stir star stir plus plus， and we're going to take the current value of hash in this case we're going to shift it three to the left and then we're going to exclusive order with the character we're looking at so you can say。

Shift 3， exclusive or， shift three， exclusive or， so you can think of it as like an accumulation。

 but the exclusive or is a nice form of accumulation in that it。It。Increases the randomness。

The pseudoranness of this thing and so exclusive order just turns out to be a super valuable calculation and so this loop is going to run so many times and so we're going to print it out you're going to see the hex if we're just taking the letters H。

 you can see kind of the internal hash value。🎼Growing and changing and you can kind of see it going from right to left as it sort of grows。

 and there's new data being put in bit wise。 It's a bit you know bit exclusive or。

 but at the very end， it says return hash percent buckets。

 which takes the modlo operator of the number of buckets。

 And in this case I'm going to be using eight buckets just to run the hash function right give me the bucket for this string So you can see me running different things on the righthand side and getting back the ultimate final buckets。

 So high goes in bucket 1。 hello goes in bucket 7 and world goes into bucket 4。

 this this is really inspired by， you know the shifting in the masking。

 but I've simplify it so you can kind of see what's going on and in our particular hash it's good enough for our purposes。

 but it's probably going to have collisions when treated against a whole series random data It's not going to be as good。

 And that's where a fancy hash like。

![](img/6eb63111da8605488720b8d0efb6d739_16.png)

gott a shot 256。Would be helpful so now that we understand the basic data structures and how hashing functions work。

 let's up next we're going to take a look at actually building a hashmap or at least adapting our list map and turning it into a hashmap。



![](img/6eb63111da8605488720b8d0efb6d739_18.png)

🎼Yeah。

![](img/6eb63111da8605488720b8d0efb6d739_20.png)

Yeah。
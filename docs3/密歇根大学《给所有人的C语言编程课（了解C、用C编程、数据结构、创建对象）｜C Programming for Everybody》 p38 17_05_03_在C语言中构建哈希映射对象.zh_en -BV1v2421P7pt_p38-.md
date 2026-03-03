# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p38 17_05_03_在C语言中构建哈希映射对象.zh_en -BV1v2421P7pt_p38-

![](img/411a95f9b40cfd2bc8391d1c13251770_0.png)

So now that we understand what a hash function is， we're going to actually build our hashmap implementation。

 but what we're really going to do is make a copy of our list map code and change as few things as possible。

 You'll be impressed with how easy this really is if you have a bit of working list map code。

 This is the new constructor and I can call your attention to the changes right remember we have a number of buckets。

 we have however many head however many buckets we have We have eight heads and eight tails。

 So we're going to look at the constructor So we're going to allocate a hashmap。

 It's not that big right You still got it's still got the functions for our encapsulation to put get size dump and it or that's not changed at all。

Except it's called hashm instead of list map， the buckets is set to eight。

 we're going to initialize all eight buckets to add a head of null and a tailed null because remember。

 this is just eight linked lists and the count you set to0。



![](img/411a95f9b40cfd2bc8391d1c13251770_2.png)

Pretty straightforward， especially if you understand the hash list。

 and if you don't go back and watch that lecture， don't just like go， oh。

 I didn't understand what hash list was。 I'll just keep on not understanding and and use Che EptT。

 It's like well。I don't know what to do if that's how you're going to go through this assignment。

If you have an understand a working hash list， this is easy， easy， easy。

 we've been using ListMap Find before， and all it does is it finds a hashmap entry if it's already there。



![](img/411a95f9b40cfd2bc8391d1c13251770_4.png)

And so we sent in the whole hash map self， which is very。

 you know Python object oriented pattern where the first parameter is always self。

 We have a key we're looking up， and then we're telling it to start in a particular bucket。

 and that's the real change。 If you have hashlist find it doesn't have a bucket hashm find has a bucket And so this code is exactly the same as hash list find except instead of starting at head。

 we have an array of heads and we use bucket to figure out the thing and then we loop through it。



![](img/411a95f9b40cfd2bc8391d1c13251770_6.png)

We're in the right bucket， something above us figured out what bucket it go through。

 and so if we look at hashmap get。

![](img/411a95f9b40cfd2bc8391d1c13251770_8.png)

Which is taking a key and having it a and having a self。 we say hey。

 compute the bucket from the key and however many buckets we have， which in this case might be 8。

 and then we do a struck hashm star Retve， go find it passing in the bucket。

 if if the return is null from find。We return the default， Otherwise， return the value。 So again。

 there's one line changed between the code from。

![](img/411a95f9b40cfd2bc8391d1c13251770_10.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_11.png)

List mapap get to hashmap yet。 So let's do a quick review of what we do in map put。

 Now this is not the hashmap put。 This is mapput。 this is our list map put。

 So we call find if we find it， then we're just going update the value and we're done if we don't find it we allocate the new entry。

 we set it next to null and we link it into the list and this is the place where you should be drawing a picture if the head is null that means we have an empty list then selfhead is this new thing if the selftail is not equal to null we've linked it at the end then we're going to update the tail etc。

 So draw these pictures and these are the parts where you'll mess it up you will get these wrong and it's okay to get these wrong。

 put like a print statement in every line here if you're having trouble and you got all the cases in this nice little four lines of code captures the cases so remember we're inserting at the end So what do we do for hashmap put we have a bucket we're going run a hash computation to figure out which bucket it is and we're gonna call hashmap find and we just tell it to find it in the bucket。



![](img/411a95f9b40cfd2bc8391d1c13251770_13.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_14.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_15.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_16.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_17.png)

So in the linked list， sub 3 or sub 4， or whatever。And if we found it。

 we update the value and return。Otherwise it's time to insert so we allocate a new one we set it next to allll and then we know which bucket it is so in this we looked at the previous code it was for one link list and for this current code there's8 link list。

 but we already know which link list we're dealing with and so literally you can take the word head and change it to heads sub bucket everywhere you see head here you can change it to heads sub bucket。

 Tas sub bucket and literally when I wrote this code that is exactly what I did。



![](img/411a95f9b40cfd2bc8391d1c13251770_19.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_20.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_21.png)

I did it slowly not to mess up， and of course the compiler helped me if I forgot something。

But that's as simple as it is to transform the put。From a list map to a hashm， of course the dump。

 we have to do a little bit differently， we want to show all the buckets and so we are showing what bucket it is。

 the key value pair， but other than that it's really pretty straightforward stuff to do the hashm remember I told you that writing a debug tool is essential so you can change your main code a dump because you'll mess it up right you will not write this code perfectly and you need to be able to debug it so now let's take a bit of a review of the list map iterator so recall that the iterator is its own object we've got the entry。

 we've got the iterator and we got the map itself。

![](img/411a95f9b40cfd2bc8391d1c13251770_23.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_24.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_25.png)

And the map iterator is allowed to do all the internal stuff because whoever's writing these things。

 writing them at a group so we can think of it as like a protected value and so really the essence of the map it iterator is a current so we're going to call the public part of it is next and Dell and the private part is what the current thing is because we're we don't get to see the current but we can use next to get the current back and so the idea is as we can call next。

 next， next， next next rather than looking at current recall that the way the iterator works is you ask for the itator and then you hit the itator with the next and you go until you're done and when you find something you print it out and we can do the same thing in and as well as Python if we think about how to do the iterator for a hashmap it's a little different。



![](img/411a95f9b40cfd2bc8391d1c13251770_27.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_28.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_29.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_30.png)

We must move， we must start at， generally we start the first bucket。

And we must move through all the buckets eventually we've got to get to because we got you know eight or four link lists。

 we got to go through all of them and we got to go down each of them but if we're looking for the next item and we got to skip empty bucket so we kind of got a bit of a complex while operation and so one of the things we're going to do is when we create the map iter we are going to store a reference to the hashm so when we construct a map hashmap iter we're going to know which bucket is an internal value current is an internal value and map is an internal value which we're going to use to remember that map that we're an iterator for and we're going to have an next in Adele this is the constructor and we're saying make an iterator given a hashm we make the it structure we remember a pointer to the map in case we're going to need it later。

 the current bucket we're going to look at is zero and the current map entry is the head of the zero bucket and then next。



![](img/411a95f9b40cfd2bc8391d1c13251770_32.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_33.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_34.png)

Dell are just capsulated methods basically and then we return it Now that first bucket may or may not be an empty list right so that first you know there might be just one bucket。

 the third bucket might have a list in it and01 and2 won't have anything in it so remember so we've starting at the top bucket and our current is pointing to the head of the first bucket which may be null the tricky bit is the it next and we remember we've given the map iter we don't get map but we've stashed map in underscore map if selfcurren equals null in the old days in a list map we knew we were done and we could just return null but now we have to go down a bucket so self this is the iterator's bucket goes from like zero to1 so we increment it。



![](img/411a95f9b40cfd2bc8391d1c13251770_36.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_37.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_38.png)

And。If the self， the current bucket we're looking at in the iterator。

 is greater than or equal to the maximum number of buckets we have now got to the last bucket and we return no。

And then what we do is we say okay。That must mean we have more buckets。

 so we say self current as equals self map， that's our little stashed version of the map。

And we're going to go。 We've already incremented self bucket。

 And so we're going to grab the next head， and then we're going to loop up。

To the top now at this point， if that bucket is empty。

 we're going to do it again and we're either going to go through this while loop enough times。

Until we either have exhausted the buckets or we have found a bucket。



![](img/411a95f9b40cfd2bc8391d1c13251770_40.png)

That has an entry in it then we've got to do a little trick grab the current so the only way we're coming out of this loop is if selfcur is not null because if selfcurrent with null we would have wildd our way through and then returned null eventually after we exhausted the buckets in the while loop above so the rat valve is self-curren if selfcurren is not equal to null we're going to go to the next and then return rat valve。



![](img/411a95f9b40cfd2bc8391d1c13251770_42.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_43.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_44.png)

I've given you the code。Go through it carefully。It's tricky to write What I would do is I would like print these this code out and draw the picture draw the picture。

 So let's take a look at a hashmap iterator in action。

 So this is what it looks like when we just got constructed and we're in the first call to next current is pointing at the first item in the first link list the head sub0 we'll fall through。

 we look at this self-current value and it's not equal to null， which is great。

 which means we have something to return。 So so we don't have to go through the sort of scanning across null entries So we skip the while loop and we simply set RE valve to selfcurrent and if it's not equal to null we advanced that and then we return RE Val And so at the end it looks like this the current has been advanced to the to the next thing we're going to return on the second call。

 So the first call returns f equals 19 that's the RE valve。

 and the next thing is going to be H equal 17。 but now we give it back。



![](img/411a95f9b40cfd2bc8391d1c13251770_46.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_47.png)

To the calling code and a away we go。 So now we come in。



![](img/411a95f9b40cfd2bc8391d1c13251770_49.png)

In the second call。It's going to do kind of the same thing current is going to have pointed to8 equal 17。

 it's not null， and so we simply take RE Val and be self。 current， and then we advance it。

As long as self current is not equal to null and because it was pointing to h equals 17。

 we're going to advance， but now as we exit this second call， current is going to be null。

 but we're going to take care of that on the third call， so don't worry about that。

 RE Val is h equals 17 and current equals null。

![](img/411a95f9b40cfd2bc8391d1c13251770_51.png)

So now we're done with a second call， so now we come into the third call， and in this situation。

 we are pointing at the zero bucket and current is null。



![](img/411a95f9b40cfd2bc8391d1c13251770_53.png)

So the while loop is going to take over， so while self current equals null， which is true right now。



![](img/411a95f9b40cfd2bc8391d1c13251770_55.png)

We are going to run the code， say self bucket plus plus which is the bucket number in the iterator and we're going to ask。

 is the bucket number in the iterator greater than or equal to the number of buckets in the map If we are we're done we're at the last one but we're not so we're not going to return null we're going to say self current equals self map head self sub bucket so we're going to go down to bucket sub1 now and we are going to make current point at bucket whatever the head of bucket1 is and that's okay we found an empty bucket because remember I said you got to skip empty buckets。

 but we're inst in the while loop。

![](img/411a95f9b40cfd2bc8391d1c13251770_57.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_58.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_59.png)

So while goes up， says， self current is still null， I mean I just move to the next bucket。

 but self current is still null， so I add one to the bucket， the bucket becomes two。

 we check to see if we're done。

![](img/411a95f9b40cfd2bc8391d1c13251770_61.png)

If it's greater than equal map buckets， return nu which it's not because we're at bucket1 and selfcurrent is equal to self map member map is our remembered version of the whole map so we can see all the heads because we've got to work through the heads so now self-cur points to be equals 14 and now the while loop goes back up and now self-curren is not null because it's pointing to the B equals 14 item。

 so it pops out of that while loop。

![](img/411a95f9b40cfd2bc8391d1c13251770_63.png)

And drops down and says RE Val equals self current， which was b equals 14。

And then it advances self current and self current becomes null again。

 but that's okay because we're going to return B equals 14 on the third call。 So just to review， we。



![](img/411a95f9b40cfd2bc8391d1c13251770_65.png)

We returnedturn f equals 19 on the first call， we returned h equals 17 on the second call and return B equals 14 on the third call。

And now it's going to loop back up。

![](img/411a95f9b40cfd2bc8391d1c13251770_67.png)

And we're going to see the fourth call。And so the fourth call is going to come in and。

Current was d equals 21， and so it's pretty simple， we're not going to run the Y loop at this point。

We're going to return to equals 21， we're advanced current， so current is now pointing to null。

 and now in the fifth call， current is null。But now that's going to trigger us working in the while loop。

 we're going to add one to the bucket。The bucket is going to become four。

And we say if this bucket inside this iterator is greater than the total buckets in the map。

Return null and we're now done。 The fifth call returns null that tells the calling code that we are at the end of the list。

 So if you keep yourself straight and you draw pictures like this and you think it through。

 this is a surprisingly small amount of code。

![](img/411a95f9b40cfd2bc8391d1c13251770_69.png)

To build a complete iterator for a hashmap， I kind of mentioned this in passing。

 but we still have more work to do a thing called rehashing it's not that hard and feel free feel free to try it。



![](img/411a95f9b40cfd2bc8391d1c13251770_71.png)

![](img/411a95f9b40cfd2bc8391d1c13251770_72.png)

At some point if these linked lists get too long our performance starts to suffer and so one of the things that hashes do is in the middle of an insert they'll have something we call a load factor and it's like whoop these buckets we have。

Each bucket would have a length， and we might check all the bucket lengths。

 And if it got to be like over 10 or 15 or something。 we would go from。

 we would have to rehash these things。 You don't have to reallocate。

 you just have to go from four buckets to8 buckets and then you recalculate the hash modo 8 and figure out which bucket it belongs in and reconstruct all these things。

 And so it's not impossible to do a rehash doubling the bucket and reducing the average chain link。

 but we are not going to do that in this particular thing because we're going to keep it simple。

 So the hash map iterator while complex is surprisingly simple。

 It's really very similar to the list iterator。 the key thing is that we've got to have that while loop that's sort of skip if we're at the end of one list。

 it's got to get to the beginning of the next list and it's got to skip empty buckets。

 Now this is why you can see because that the things in the list are in somewhat random order the buckets。

The mapping of any key to any bucket is in random order， and this is why when you think of Python 2。

 we can look in Python 2 and we say， oh。

![](img/411a95f9b40cfd2bc8391d1c13251770_74.png)

If you iterate through a map。They come out in the same order， but there is no predictable order。

 but if you do it twice， you're going to get the same order and the fact that the order might change if you do inserts or deletes。

 that has to do with the rehashing。So we're kind of at the point where we have built the two foundational types of Python 2。

0 we've deal put a list。And we built a dictionary quite than 2。0。

ButNext we're going to move like to Python 3。0 and start creating a linked list that maintains sorted order and can be iterated in key order。

 and so that's going to be our treatment。

![](img/411a95f9b40cfd2bc8391d1c13251770_76.png)

🎼So。🎼Yeah。

![](img/411a95f9b40cfd2bc8391d1c13251770_78.png)

🎼Yeah。

![](img/411a95f9b40cfd2bc8391d1c13251770_80.png)
# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P39：3 - Fall 2022 Discussion 8 Question 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/30324118dd1b21b8dc71632af217cdc9_0.png)

Okay on question two， which is all about hashing So for part A。

 we're given a bunch of potential implementations of the integer hash code function so integer is the actual built in Java object and we want to know if these hashing schemes are valid and if they are what are the advantages and disadvantages of each of these hashing schemes and for the purpose of purposes of this question let's assume that like we have infinite numbers of buckets like which wouldn't happen in the real world but let's just assume that we have an infinite number of buckets so we don't really need to worry about the modular scheme we're just worried as to whether or not they're valid or invalid okay。

So for the first one， we see public hash code it just returns negative1 All right。

 let's go through the properties is this valid。 number one， it's an integer。 Yes， it does the trick。

 number two， the hash code for the same object should always be the same So an integer object if we call hash code on it where returns negative one every single time no matter how many times we call hash code on that integer object is's going to return negative one so it fulfills that the hash code for the same object should always be the same number three。

 if two objects are equal， they have the same hash code so let's say I had an integer5 floating off in space and an integer5 floating off in space when I call the hash code on both of them。

 they're negative one and they're equal because we're assuming here that the integer equals method just returns its integer value which is five so we're gonna say five is five they're equal and they have the same hash code cool this is a valid hash code。

😊，Is it a good hash code though， okay， let's think about that remember that we said that a good hash code is one that distributes elements evenly。

😊，Is this going to distribute elements evenly？No， if the hash code returns negative one every single time。

 that means that all elements are always going to hash the same bucket right like whether it's integer 5 integer 1000 integer 10。

000 and 270， it's always going to hash to negative one which is not great for us。

 which means that every single element every single integer that we hash is going to run into a collision。

 so even though this is a valid hash code it is not a good one at all。Okay。

So moving on to the second one， we have public hash code where it returns in value times in value and just as a reminder in value is just a method of the integer class that just returns the integer value of that integer so if we had like integer 10。

 it would just return 10 so here we have basically invalue squared okay。😊。

It is just a valid hash code， number one， it's an integer cool。

The hash code for the same object should always be the same yeah if we have integer 10 its hash code is going to give us 100 over and over and over again right the in value of that integer is not going to change so it's consistent what about number three if two objects are equal they have the same hash code so if I have an integer 10 floating in space and I have another integer 10 and floating in space they're both going to have hash code of 100 so we're good they do have the same hash code so this is a valid hash code implementation。

😊，Is it a good hash code so here we're going to be a little bit iffy about the definition of good but let's think about it in terms of collisions are collisions possible。

With this hot code。Well， if you remember that when we take a square root of a number this the result can either be positive or negative right so we can kind of think about this in terms of like positive and negative numbers so。

The hash code for integer five is going to be the same as the hash code for integer negative five right because five squared and negative five squared are both 25 so they would both hash to 25 and there's going to be a collision there right we did say that assume that for the purposes of this question there's like a ton of buckets so。

😊，Like it's probably fine if we have like one teeny tiny collision， so it's not a huge deal。

 but it's still good to note that this will have a collision regardless it's valid but there will be a collision for numbers that have the same absolute value okay。

The third part just returns super dot hash code and remember that the integer class just inherits from Java the object and objects hash code is based on memory location。

 so when we call super dot hash code we're really calling objects hash code okay which is based on memory location。

😊，So let's think about whether this is a valid it's an integer。 Yes， that's good。

 the hash code for the same object should always be the same。 Yeah。

 the location in memory for an object should always be the same so it shouldn't ever change so if we hash that element again over and over it should be consistent Now number three if two objects are equal they have the same hash code this is where things get a little bit fishy so going back to the example with the integer5 floating in space and integer 5 floating space let's say I had like two variables I have int a equals integer 5 and int int B equals integer 5 so A and B are both integer objects that have int values of5 right and we said that。

😊，The integer equals method is just its int value right so in theory this five and this five A and B they should be equal to each other because they both have the int value5 for their integers right Okay。

 so these two objects are equal do they have the same hash code。Well。

Objects hash code is based on memory location， which is what we're calling here right A and B are referring to two different integer5 objects in memory。

 which means that these two integer5 objects are in different locations in memory which means that their hash code is not going to be the same right because it's based on two different spots entirely so this hash code is actually going to be invalid because memory address is unique per integer object right。

Okay。The fourth one that we propose is going to return the current time as an int Okay。

 so going back through our three card interval rules of whether or not a hash code is valid number one it's an integer great number two the hash code for the same objectvic should always be the same。

Okay， if we have the integer 10， if we hash it。Ash。12 pm。

 that's going to give us a different hash from if we hash that that same object that same integer 10 at like 1 pm right because time is not going to stop for us。

 which means that every single time we hash a particular object again and again。

 it's not going to give us the same hash code， which means it's not consistent and therefore this hash code implementation is invalid。

Okay。What about our last one for our last one we just say want to return the integer value plus three so this means that if we were hashing integer 1 this would give us1 plus3 is4 if we were hashing integer 6 that would give us6 plus three is9 so on and so forth so we know it's an integer cool the hash code for the same object should always be the same this is just simple addition between two numbers that won't ever change right in value shouldn't ever change for the integer object so we know that it's going to be consistent and then if two objects are equal they have the same hash code is integer 6 and integer 6 are these hash codes we gonna be the same。

😊，Yep， they are because the int value doesn't change and so6 plus three is  nine they're going to hash the same thing Co。

 we figure it out。 so we know this is a valid hash code implementation。😊，Now is it good。

 does this distribute allates evenly， assuming that we have like a gazillion buckets that we don't ever have to worry about？

Are there room sorry， is there room for collision？Let's like revisit what we did here with the positive and negative numbers so we figured that there would be a collision here for numbers same absolute value let's try that down here so if we did integer 5 and integer negative5 integer 5 would hash to8 and integer negative 5 would hash to negative2 okay so there's no collision there。

😊，嗯。Okay， so。I don't think we can have any collisions actually because int value is just going to take on the value of the integer right so so long as you like。

😊，Hash two different numbers。 They're going to give us separate hash code。

 the hash two different integer objects that have different ins。

 They're going to give us different hash codes， right。

 So they will never be a collision with this hashing scheme。 So this is a valid and really good。

Hash could， okay？Now。Moving on to2 be， some quick conceptual questions。

 when we modify a key that has been inserted into a hash map。

 will we be able to retrieve that entry again Okay， so we know that for a hash map。When we are。

Putting an element into the map。 and we are also retrieving an element from the lab。

 When we put the element into a map， we hash the key。

 We put the key into the relevant bucket that it hashees to based on like modular and whatnot。

 And when we do get， we do the same thing。 when we do get。

 we hash the key that we're looking for and traverse through the chain in the bucket that。

The key hash to in search of the element that we're looking for， okay。So can we ever？Alma。

Find the entry again after we modify the key so this is the answer to this is either sometimes always or never。

Okay， so I think as a student I was especially tempted to say never because I thought that like you know。

 you should never like modify thequia hashmap right that's really bad because that means like you're going to like screw up all of these things with hashing and then you'll never be able to find your value again。

But remember that hashing， like， you might just get really， really lucky。

 and the change that you make to your key might actually just hash to the same bucket， right。

 So let's say， like， I put in。Like the key， which was the string the string hellello okay and then I changed my key to high and let's just say that hasing high just coincidentally got us to the same bucket that hellello was in which means that when we're running get and we're searching through our we're searching through our bucket with get we ended up in the same bucket so that means that we were like insanely insanely lucky it's obviously not a guarantee that will happen but that very slim chance that you do luck out and you hash the same bucket means that there is this slight possibility that you'll be able to retrieve the entry again so this is going to be sometimes。

Okay， now for number two， when we modify a value that has been inserted into a hash mapap。

 will we be able to retrieve that entry again， so number one we were asking what happens when we modify a key number two we're asking what happens when we modify a value。

😊，Well， remember that when we're inserting into a hash mapap and when we're searching through a hashmap。

 we're only hashing the key right so the value doesn't play any role into the hash function or I mean it shouldn't play any role into the hash function。

 so that means that if we change the value to something else。

 we'll always be able to get the same entry associated with that key because we didn't change the key we're not hashing the value here。

Okay。😊，And I believe that is it for two question number two。



![](img/30324118dd1b21b8dc71632af217cdc9_2.png)
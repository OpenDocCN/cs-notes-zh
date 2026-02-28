# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P27：26_模块3 2 2 映射.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/661069a5cd10e201637e2ad34d8789c1_1.png)

🎼う。🎼Yeah。So a map is Golan's implementation of a hash table， so a map is exactly a hash table。

 You can use the make function to create a map。So we have an example here。

 so first thing I'm doing is I'm declaring ID map as a variable。

 a map variable right so I say var ID map and it's going to be a map and notice it after the word the keyword map I have in brackets I have the word string that's the type of the key。

And then after that， I have another type， and that's the type of the value。

 right so the key and the value can be different types。

Then line after that so that first I'm declaring ID mapap to be a variable。

 then I'm actually assigning it。😡，Pointing it to a map， making an actual map。

 and I call make for that。 So ID map equals make and then parents map， string。

 int right so it creates a map Now at first this make is going to create an empty map。

 but it creates a map。Now， another way to define a map is you can create the map with a map literal so you can initialize it with values with key value pairs rather so I'm showing that down here I map colon equals map string andt and then in curly Ras I list a bunch of key value pairs and the key and the value is separated by colons So in this case is just one pair。

 but you can have a separated list of key value pairs in this case it Joe 1，2，3 so Joe is the key 1。

2，3 is the value so and you can put any number of those you can initialize it with any number of those key value pairs。

Accessing map。 so how do you access the elements in a map at first。

 actually most of it is the same as the way you would access an array。

 except the index that you use that you put in between the square brackets， that's actually the key。

So if I want to read the value associated with the key Joe， I can say。

 in this case I'm doing a print， format print line， ID map， and then in brackets， I say Joe。

 I give the string Joe， and that will return the value associated with Joe and it'll print that。

I can also。Add a key value pairer into the map。😡，Or change an existing one if it's there。

 So if I want to add some new key value pair， I could say I map Jane， you know。

 maybe there's no key Jane in there right now。 I map Jane and brackets equals 4，5，6。

 So that puts a new key value pair in there。 Now note that that would also change a key value pair。

 So let's say there was already a key value pair in there。 Jane was mapped to 6，7。

8 So I if by saying I map Jane 4，5，6。 I'm getting rid of the old key value pair associated with Jane。

 And I'm putting a new one in there。 So Jane is now associated with 4，5，6。😊。

Also you can delete a key value pair from the map so without overwriting it。

 you can just delete it completely by calling the delete function so you call delete you pass it。

 the first argument is the name of the map， so ID Matt。

Second argument is the key that you want to delete。 so in this case， Joe。

 and it'll eliminate that key value pair， Joe and Joe and whatever's value is it'll eliminate that from the map。

So there are also a few more map functions。One thing that you can do with maps is you can have a two value assignment for a map。

For instance here， Im saying ID comma P colon equals I map Joe。Now。When I do that。

 when I do that assignment， if I had just done a single value assignment。

 say I said ID colon equals ID map Joe， then ID would equal the value associated with Joe In this case I'm doing a two value assignment。

 So the second value ID comma P that P is going to be a Boolean it's going to be true if the key is present in the map。

 So there are cases where you don't you're interested in knowing whether that key is in the map。

 maybe you don't even care what the value is associated with Joe。

 you just want to know if Joe is in your map。 So P will be true if that key Joe in this case is in the map and it' will be false otherwise。

There's also length function， you can apply that to maps and if you do you say like here I'm saying I'm printing a L of ID map。

 it'll tell you how many key value pairs are inside the map。

Another thing which is very common to do is to iterate through an entire map。

 just like iterate through an array， very common thing you want to iterate through every key value pair。

So what you do here is you're using basically a two value assignment with a range keyword。

 so it's a for loop， so if you look at the for loop you got the key and then the value p comma value and then that colon equals range on the ID map so what that does is every pass through the for loop key is going to be equal one key inside the ID map and Valal is going to be equal to the corresponding value in the ID map so in this way every pass。

 every iteration through the for loop we use one key and one value pair so key and value will be bound to a different key value pair for every iteration through the for loop and you'll iterate through the for loop until you've gone through every key value pair inside inside the ID map。



![](img/661069a5cd10e201637e2ad34d8789c1_3.png)
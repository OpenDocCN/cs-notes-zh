# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p29 08_03_02_在C语言中实现Python字典(dict)类.zh_en -BV1v2421P7pt_p29-

![](img/b256fa6f0fef9837b4b46376a8d3c300_0.png)

So now we're going to build a Python dictionary class and here is the code that we would put in our dictionary。

 I kept the strings really short because of all the I want the examples to be pretty short and easy。

So what do we do， we create a dictionary and we use the you know bracket square bracket operator to create a key。

 it's a key value pair， the key Z match it goes to the catch phrase。

 we print it out the dictionary Z goes to W which is replacing catchph with W because if you overwrite the same key。

 you have to put the same you have to replace the value。

And then we're going to throw three more things Y maps to B， C， maps to capital C and a maps to D。

 that's just so that it's not sorted too badly， and then I print it out and then I print the length of it I do a get and with a default value of 404 so sometimes I get for Z I get the W and then for x is not there so I get the 404 again kind of an homage to the H TTP error code 404 not found。

 and then I use it right over our little 4 loop for key and diict， et ceter。

 I can print the key value pairs out。We'll do the same thing and C。 And again。

 this is almost a perfect transformation。 Literally。

 we first create the dictionary with calling a new。Then we put the word catch phrase in the Z key。

 then we print it， then we put a W in the Z key which should overwrite it and we print that。

 and then we set the Y key to BB， the C to be capital C， the A to be capital D。

 and then we print that。And then we ask， how long is it？

And then we do a get to look up under the Z key and the X key， one of which is there。

 one of it is not there。 And I get a null back in that situation。

 I guess I was a little C like in my get code。 And then I dump it out。

 and I dostruct D node loop go from the head until it's null and I print out the key and the value from each of those dictionary nodes。

 And then I delete it at the end。 So this is。

![](img/b256fa6f0fef9837b4b46376a8d3c300_2.png)

The code。 now， again， notice we don't know much about looking things up。

 We don't know how the length is maintained。 We don't know how the static and dynamic allocation is going to happen。

 We now have a contract with a bunch of library code that is going to implement this dictionary object for us and do all of them memory manipulation on our behalf。

 Again， we start with a basic stuff。

![](img/b256fa6f0fef9837b4b46376a8d3c300_4.png)

The big thing we're going to do is we're going to not just have a value。

 It looks like a lot like a link list。 We're going to have a key value pair。

 The pi diict has a head and a tail and account just like the pie list。

 And if you look the constructor， it's pretty much like the constructor for the list。

 we allocate the di pi dit。Structure， and we set the head and tail to null to indicate empty。

 and we set the count to0 and we're done。 And the same with the Dell。

 the Dell is very much like the linked list Dell。 We are have to， because we've allocated the key。

 the key is also going to be a dynamically allocated pointer to a character array。

 So we got a free curve key along with curve value。 But then everything else is the same。

 we pre preload the next value， then we free curve， then we move to the next value。

 And then when it's all said and done， we free self， which is the pi diic value。

 when it's all said and done， we can call the new。 and then we can set a key like catch fze。

 And the key thing there is the key and value are both。



![](img/b256fa6f0fef9837b4b46376a8d3c300_6.png)

Maaled。Bits of memory， just like， you know， before we had the text。

 which was a malic bit of memory and copied， and we had to free it。 But now we just have two things。

 And so the key and the value are two things that are that are going to be malled and then copied into the mallic area。

 So some methods for you to build。 the lens should be pretty easy。Similarly。

 that we have a print that's going to be pretty and I want you to match exactly the output of the Python。

 And so it turns out that we can make a method called find。

 which returns a D node rather than get returns a string and find returns a D node。

 and then we can use find both in get。And in put。 now we use it pretty much in get to go find it and then return the value because we have the key。

 We look up， find it by key and then return the value。

 So that's pretty pretty easy to do the get once you have find。

 So the find is find is a Thor loop where you're going to go and you're going to find it。

 And if you find it， you're going to send it back。 Okay， and if're not。

 you're going to send a null back。Now you better check if it's null right including in the get。

 you got to check if it's null， but then in the put。

 what you do is you look up the old one with Pd underscore find。And if you get one。

 if old is not equal to null， then you're the key updating the value for the key， and if not。

 you're adding it now the thing about the else clause here is it looks a lot like a linked list。



![](img/b256fa6f0fef9837b4b46376a8d3c300_8.png)

Because really if you look at this thing， it is a linked list。

It's just there's two values in each one。 We're not doing anything magical。 Now。

 more advanced dictionary implementations might use hash maps or binary trees or other things like that。

 like that we're in chapterer 6 that we didn't talk too much about。 But for now。

 we're just going to make our dictionary be a linked list。 But instead of just a value。

 it's a key and a value so we can look it up by key。

 And so we're not doing too much tricky stuff to make our dictionary really by just adding a bit to a list。



![](img/b256fa6f0fef9837b4b46376a8d3c300_10.png)

So let's just take a look at how this is going to work。In sort of the real world as it runs。

 So remember， we have kind of the dictionary itself， which is a head and a tail and account。

 And then we have the dictionary nodes， which is our key in value。And the next one。

 now the key and the value are not the actual strings， they're just pointers to strings。

 which means we're going to have to use malloc to when we get a key and we get a value。

 we're going to have to mallick and copy both of those things。



![](img/b256fa6f0fef9837b4b46376a8d3c300_12.png)

So if we start and we see Pi dick_ new， we're going to get a dictionary with head and tail that point to null。

And then if we add catchphse， well， we allocate the Z， we allocate and copy the key Z。

 and we allocate and copy the value。And put those in key。

 And then next is null and head and tail point to this thing。 So we've allocated three things。

 We've allocated a D node， and we've allocated a character two character arrays using Malic。Okay。

 so then let's say we're going to run the next line of code， which is setting the key Z to W。Now。

 when you're in the put code。You go and you call find and you see that there is a thing。

 There is already a Z in there。 So what you've got to do is you've got to replace catchphrase。

 So you actually before you go and make a new。

![](img/b256fa6f0fef9837b4b46376a8d3c300_14.png)

Value。You have't been to copy W into it。 You want to free the old stuff。

 And so you tend to free the catch， free the value that was in there before。

 and then you mallic and copy in for the new value。 So if you're done at the end of this。

 you will have catchph somewhere in magic free space。

 We don't know where how C does magic free space， but it does do it。 So at the end of the second put。

You still have one entry， but the value has been changed from pointing at catchphse to pointing at W。



![](img/b256fa6f0fef9837b4b46376a8d3c300_16.png)

🎼Then we add y equals B。 Well， you do a find and there is no y key。

 So now it's more like a link list。 You create a new D node and you pen it to the end。

 just like in a link list。 And then you save the key and point key at it。

 And then you save the value into new Malic space and then point value at that。

 And then we go to the next one where we point C we don't find C in there。 So we create a new D node。

 and then we do a malik of the the key and a malik of the value and we point to those and then copy the data into those two maled areas。

 and then point key and value at those maled areas。

 And you can kind of see that this is really at this point， unless we find the key in there already。

 it's just a link list that happens to have two character arrays that are dynamically allocated and copied one for key one for value。

 That was a bunch of object orientation。 It was kind of a walk down the path that Nito Van Rossom took probably in the。



![](img/b256fa6f0fef9837b4b46376a8d3c300_18.png)

![](img/b256fa6f0fef9837b4b46376a8d3c300_19.png)

fewew weeks of him building the string class， list class and dictionary class。

 chances are good he built something very， very similar and then he's like。

 okay now I got to make this better but you know if I was just writing this thing he'd probably just type this out。

 it's kind of pretty for a computer scientist who've been doing algorithm data structures their whole lives。

🎼It's like， well， why don't I just make a class that does this， you know。

 now that I now that I've got sort of an object ored universe， let me hide all of the dynamic memory。

 And that's really what we're doing。 We're hiding the dynamic memory and the implementation details and all the for loops and Y loops that are being hidden。

They're important and if you were to look at the source code to stir list and died in Python you'd see they're allocating and reallocating they're doing it a lot more cleverly than what we did you don't want to call reec too many times。

 but for now it works we're doing small stuff there is an infinite number。

There's an infinite array of optimizations to make all of this way faster and more impressive。

But that's really for another time， so we've kind of got the idea of the baby steps from a procedural language with pointers。

 structures and dynamic memory allocation， how you would take the step using those underlying things in a procedural language to build basic objects and support those objects。

 perhaps as you're building a new language like Python。



![](img/b256fa6f0fef9837b4b46376a8d3c300_21.png)

Yeah。
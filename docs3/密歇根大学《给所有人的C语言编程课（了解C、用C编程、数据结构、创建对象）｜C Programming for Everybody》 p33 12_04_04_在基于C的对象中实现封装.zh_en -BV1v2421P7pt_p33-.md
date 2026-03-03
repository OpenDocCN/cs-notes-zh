# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p33 12_04_04_在基于C的对象中实现封装.zh_en -BV1v2421P7pt_p33-

![](img/4384fdb5c426dd9847b6f20605a58cfd_0.png)

So it's time to stop deep diving into object or theory and get to write some code。

 And so we're going to start with something simple。 We're going to do encapsulation。

 The second thing we're going to do is iteration。 But for now。

 we're just going to do encapsulation and then in the next section will do iteration。 And really。

 most of this code you've already done。 we're just kind of refactoring it and moving things around and taking these。

 you know。Functions that we named by convention and we allowed the calling code to use and moving them into the class using some pointers。

So a real accomplishment here is the map arrow put， the map arrow get and the map arrow Dell。

 these things are now named and accessed in such a way that they are attributes。

 the functions we're calling are attributes in the class itself and so other than that。

 it's not that different and so it's not that big of a deal The other thing we're going to do is be a little more explicit about what things in these classes are public and what things in this class that we're building are private。

So we'll start with a map entry， this is the structure that makes up the nodes of the linked lists。

The key as a character string and the actual value is an integer that we're just going to make it simple to we got to dynamically allocate the key like we've been doing。

 and then we have a provenve and a next。The key there is the preve in the next our double underscore。

 So that means they're private， but we are going to decide that key and value are public。

 and we just indicate that much like Python would do by not putting double underscores in front of it and remembering in our mind that they're allowed to be used in calling code。



![](img/4384fdb5c426dd9847b6f20605a58cfd_2.png)

The map structure most of it looks pretty simple， we have a head and we have a tail and we have a count。

 you've been maintaining those for some time now， those are private attributes。

 so we rename them in such a way that they have double underscores in front of them。



![](img/4384fdb5c426dd9847b6f20605a58cfd_4.png)

And then we have a series of public methods， we have five of them。

The key thing is these are pointers to functions。And that's what Boyd star put。

 that's parenthesesis star put。 that means that there is a we're allocating a variable in the structure named put。

And it is a function pointer that will return avoid void。

It's a pointer to a function that returns a void， so not only are we defining the attribute that we're going to use to access the function。

 we're also defining the calling sequence。 it returns a void， and it takes three parameters。

 a struck map pointer to self。

![](img/4384fdb5c426dd9847b6f20605a58cfd_6.png)

![](img/4384fdb5c426dd9847b6f20605a58cfd_7.png)

Char star key and int value。 So when it's all said and done， this is not putting the code in here。

 as it might say， in jascript， for example， what is is is a single 64 bit number。

 which is a pointer to the beginning of a function。 Now the function。



![](img/4384fdb5c426dd9847b6f20605a58cfd_9.png)

Method signature has to match， so we're defining the method signature， but in terms of allocating。

 we're really allocating one pointer for put， one pointer for get， one pointer for size。

 one pointer for dump， and one pointer for dell。And again， you know you look at get， well。

 get takes as its first parameter， a pointer to the map。

 which is self a key that we're going to use to do the lookup and then a default value to return。

 and then get returns an int。

![](img/4384fdb5c426dd9847b6f20605a58cfd_11.png)

And so that that's pretty straightforward， it took me a little while to get the pattern right about because the parentheses here are really。

 really important because we're both defining the attribute name and the rules of its use and the method signature of the function that we're eventually going to point to。

Okay。But that's pretty much it right we're just going to put these things in and so the constructor is pretty straightforward。

 it's not that different than the constructor that you did。



![](img/4384fdb5c426dd9847b6f20605a58cfd_13.png)

Weve got to build these functions， double underscore mapput， doublestrom map gap， map size。

 they're outside of this they're above us in the source code somewhere。

 and we're just saying Parrow put， which is an attribute put。

 public attribute put is equal to Ampersand， the address of the double underscore mapput function。

Super simple Ampersand is address of address of that function， get is address of that function。

 size is address of that function， dump is address of the function and we're done and and this is kind of showing you that this is。

 let's see。Head is a 64 bit pointer Tas a 64 bit pointer count is probably a 64 bit integer or a 32 bit integer put get size dump and Dell are all 64 bit。

 So the size of the map itself， the map structure is about you know。



![](img/4384fdb5c426dd9847b6f20605a58cfd_15.png)

Ten words or less， and that again has to do with efficiency， right？

But you probably have most of the code you need for mapP， mapp yet， map size， mapp dump。

 and Map Dell。So a map dump is pretty simple， you know， if we look at this the you know。

The self is the pointer to the map。 So it has a head and a next。

 And we're going to just go through it until curve is equal to null。 We've got a map entry。

 which is the type。 Now， we don't double underscore the curve because that's really just an automatic variable inside this function。

 That has nothing to do with the outside world。And you'll notice that we're just access double underscore head。

 we're accessing double underscore next because we're in the class right and so that those are private。

 but they're totally legit to access them when we're building a dump tool inside the class so private things are accessed in the methods in the class that's normal right we don't have to hide those。



![](img/4384fdb5c426dd9847b6f20605a58cfd_17.png)

I'll tell you， when I'm building something like this。

 the first thing I want to get to work is some kind of a dumper because how， I mean。

 when I write this code before I hand parts of it over to you， I have like，Map dump， map dump。

 map dump， map dump every line I put a map dump。 And eventually when stuff starts working start taking the map dumps out。

 So just debu， debu， debu tobu。 all is it。 So' that's why I'm just like。

 I couldn't write this code if I didn't have a map dump。

 And so I'm going to make you guys do it as well。 So the de， like most des。

 The key thing is to draw the picture and figure out what parts or dynamically allocated and then call free or which parts came from mallck and then make sure you free them。



![](img/4384fdb5c426dd9847b6f20605a58cfd_19.png)

And so we're just going to loop through， and again we're in the class so we're happily using double underscore attributes。

We're going to loop through， we're going to and the order this is always important。

 but by now it should make sense we're going to free the key because remember that's a string pointer that we malled。

 we do not need to free the value that's just actually part of the map entry struck and when we're going to get rid of that in a second we're going to advance to the next one first。

And then we're going to free the current map entry。

 and then we're say current next and we're going to loop up and so eventually we're just going to go through the linked list。

And free the key and then free the entry itself。 and we've given back all of our data。

 And then we're all done with that。 We actually free the。10 words or so That is the map structure。

 Again， this should start to look familiar to you。So Gt is pretty simple as long as you have some code that like is map Find。

You know， map Find is going to do all the hard work。

 but mapp Find can look at underscore head and all that stuff and next and look at all that write some for loops。

 it should be not too hard。

![](img/4384fdb5c426dd9847b6f20605a58cfd_21.png)

And again， underscore underscore map find is private。

But we're in the class and so just have fun talking to the private stuff。

🎼Mapput is something you're going to have to write， but if you think about it。

 if you get map Findd and it returns you it will return and you've done this before。

 you've used a find like method to find the thing in the link list and you update it if you found it it's really simple you just change the value in return and if not you add it to the end of the you construct a new map entry and you add it to the end of the list。

 and so again， I just hope by now you can knock these things out and so that's basically it I mean if you really think this was a very simple section where all we're doing is changing from globally named functions we're enforcing the rules of private with double underscore and then we're taking those pointers we've declared pointers to functions in our map and then our constructor sets them up and the rest is really just refactoring code that you pretty much already have。



![](img/4384fdb5c426dd9847b6f20605a58cfd_23.png)

![](img/4384fdb5c426dd9847b6f20605a58cfd_24.png)

🎼Yeah。🎼Yeah。

![](img/4384fdb5c426dd9847b6f20605a58cfd_26.png)
# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p42 21_06_01_欢迎来到CC4E结语篇.zh_en -BV1v2421P7pt_p42-

![](img/105f70b7aec4e17e5214b016b5411441_0.png)

Hello， and welcome to the lecture in C programming for everybody that I call the epilogue。

And that's because this lecture happened after the course was completely finished。 I have a saying。

In my life， that basically says that when you think you are finished with a journey， often。

 that's when you finally know where the journey actually begins。

 And that applies in sea programming for everybody。

 because see programming for everybody for me was a four and half year project to create the book。

 create the auto graders， create the lectures， Get it up on courseurra， Get it out on the Internet。

 et cetera。And so I just was going through the class， and at some point I ran into chapter 6。

OfCar of get him Richie and I'm like， what will some good examples to use？

What are some good examples that I can use that will be relevant to the students who perhaps have taken Python for everybody and I'm like。

 well， why don't we just implement some Python classes we'll see how complex they get and if they get if it works out well。

 it talks about the concept of interfaces and implementations。

so I think it worked out really really well and so as we are going through chapter 6 of Carnegan and Richie。

 I built us a Python string class and you can go back and you can watch those other ones。

As an extendable character with some chunking where it would allocate some space and then。

Fuill that space up and as that space filled up， it would extend it。And I made a list class。

 and I used the linked list。From Carnegiegan Richitchie Chapt 6， if you recall。

 I made an extra little bonus section 6。5。1 where I talked about link list explicitly because in the original Carnigan and Richie 1978 book and I believe it's the same in the '84 and but I'm like I'm going to show you link list first and so I added this little piece to the canon that Carnigiegan and Richitchie Cannon and I added that。

I implemented the Python dictionary。Using the technique of Carnegan Rie 6。6。

 pretty much straight on when I built the Python string class。

You'll notice that there's a structure that has a length and an ac and the alic is how many characters we allocated。

 and the length is how many of those we've used， and we're putting automatically a0 byte at the end of it。

 So as you add things together， eventually you get the length to be 9 with a 0 byte and the alic is 10。

 which means we can't add the letter D。 And so we real use realc to extend it。And make it be 20。

 And then we have space to put both the letter D and the end of string。 We built a Python list class。

 It was， it was so natural to just make it be a linked list。 And linked list has twostructs。

 One is the link list itself that has a head pointer and a tail pointer and a number of items that like lets us give back L when we need to give L back。

 But then every node。

![](img/105f70b7aec4e17e5214b016b5411441_2.png)

![](img/105f70b7aec4e17e5214b016b5411441_3.png)

We're going to just have a list of character strings or character arrays。

 and so we have a pointer to a character array， and then we have a pointer to the next。

 and so when we sort of do our constructor， we allocate the object and then we set the head and the tail to null to indicate that the list is currently empty and set the count to0 and we're done。



![](img/105f70b7aec4e17e5214b016b5411441_5.png)

And then as we add things to the list， right， we have these pointers。

 and we point to the head to the beginning of the list， the tail to the the last item that we added。

 and we store using Maloc the string so that we get a pointer to a string that。



![](img/105f70b7aec4e17e5214b016b5411441_7.png)

The list owns rather than the parameter， which doesn't belong to us。 And then we hook the next up。

 and there's a little tricky stuff， right， If the string is empty， which means head is null。

 then we just point head at the newly allocated node。 If the tail's not null。

 we take the last thing and point it to the one we just made and set tail to new and then we allocate the string and then copy the text from the parameter into text and then we store that as a pointer and then we update our count。

 Like if we add another one， you have to kind of graph the new one in beyond the tail。

 So the tail instead of being null null points to the one we just created the fun。

And then we update tail to point to that， and then the next on that one is0 because that's our way of ending the list。

 And if we're going to iterate through this list， we start at the head。Look at the item。

 then we go to next and we'll look at that item we're going go to next and look at that item and go to next and it's not longer we're done Again。

 we were able to build a quite competent Python list object from that。



![](img/105f70b7aec4e17e5214b016b5411441_9.png)

And as you might expect， when we switch to building the dictionary class， we just go into section 6。

6 and go in and make a hash table with buckets， and it's literally theh the bucket based hashm is probably the most common programming interview question。

 perhaps it's less common now because everyone knows that it's a programming interview question。

 right？And so， you know， I just figured， of course。

 a dictionary is going to be a set of buckets that are a set of pointers to list。 you know。

 recall that hashes are some function that takes the key and creates a large pseudorandom number。

 which means it's deterministic， but it's widely distributed it with the idea to limit collisions。

 So John Smith and Joe Smith， hopefully will hash differently。

 even though they're very close right And so the way we did this again。

 following Carnegan and Richie is we use the key computed a hash， which is a large integer generally。

 but then we modo it based on the number of buckets。 And so the buckets are in a sense。

 for linked list。 And if we wanted to write this code in a way。

 we could have kind of use the list object and said here and be a little bit less repetitive but we just implemented the whole thing。



![](img/105f70b7aec4e17e5214b016b5411441_11.png)

So if you look， we start with astruct KR diict， which has a number of buckets。

 it has four heads and four tails in account。And so it's just heads and tails of the way you do link lists and if you look at the node。

 we're going to do key in value and I'm going to make it be a string key and an integer value again to simplify right and the char star key is a pointer to a key that we're going to save。

And if we look at the new operation。We allocate the actual dictionary object。

 We decide how many buckets we're going to have the way I define structure care deck。

 it's just a four element array。 Then we set them all to null so that we know that they're empty because it's important to know if the heads and tails are each of the link lists are empty。

 The one thing is this doesn't have any expansion mechanism。

 And so I just wanted to keep it really simple to show you the data structure。

 So I kind of like punted on rehashing and expansion。And then we set the count to0。

 and then we return it as we're inserting things in， right， we use the hash to figure it out。

 And then we simply have four linked lists。 So if you were to compare the Kr list code to the Kr dic code。

 you would see that a lot of it looks the same， except we're starting with a head that has been chosen by a hash computation along with modo based on the number of buckets。

 As I've finished all that up and I finished a class up。



![](img/105f70b7aec4e17e5214b016b5411441_13.png)

I wondered。 I began to really wonder。 I looked。 I started looking at it less from a C and Can R。

 Carnegan Richitchie perspective， and more from a Python perspective。 And I'm like。

 did I just inadvertently do exactly what Gito Van Rossam did。

Did Gito Van Rossom read this book like most of us did in the 70s and 80s， And did he just say。

 you know what， I'm going to make a list object and it's going to be a linked list and I'm going to make a hash object。

And it's going to be a set of buckets， linked lists in buckets like everybody would do。


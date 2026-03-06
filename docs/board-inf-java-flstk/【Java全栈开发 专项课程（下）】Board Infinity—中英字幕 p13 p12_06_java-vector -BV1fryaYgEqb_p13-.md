# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p13 p12_06_java-vector -BV1fryaYgEqb_p13-

![](img/0e5673b2b31080000b2375900f8a324b_0.png)

Like error list and linked list vectors are also used for dynamic arrays Ve is like the dynamic array which can grow or shrink its size again it extends the abstract list and implements the list interface。

😊。

![](img/0e5673b2b31080000b2375900f8a324b_2.png)

One important thing that you need to understand。 vector is synchronized。

 It means only one thread at a time can access the code。

 This means if one thread is working on vector， no other thread can get a hold of it。

 It means only one operation on vector can be performed at a time。 For example。

 if addition is being performed on one thread， other operation cannot be performed until the first one is over。

 That's how a vector extends the abstract list。Class and implements the list interface。



![](img/0e5673b2b31080000b2375900f8a324b_4.png)

The elements of vector object can be accessed via an index into the vector。😊。

As I said it is similar to the LLS but having a couple of differences， as I said。

 vector is synchronized that contains many legacy methods that are not part of the collection interface。

😊，These are the reasons to use vectors in a real time as I discussed。

 it has a dynamic size that we have in error list or linked list you can just opt it out right way。

 it gives a legacy support and synchronization thats an addon to the vector that you can use it up to restrict your operation or modification on a particular list to be done by the multiple threads。

😊，These are the specific methods like add at all Add element capacity contains equals get an index of。

 which are the methods that you can use from your collection interface and also few of them from the vector methods to itterate your list。

😊，Most of the time we compare the vector with Erlist， As I said。

 Erlist is a part of Java collection framework， but vector is a legacy class of Java。

 Ve grows double its size when capacity is reached。

 but as grows by half the size when the capacity is reached。😊，As I said。

 vector methods are synchronized， thus does not allow your modifications or manipulations to be happen by multiple threats at a given point of time。

 but errorist is not synchronized。 Ve uses enumerator and ittator for traversing the list of elements。

 but errorist uses only itrator。I'll talk about ittated in my upcoming session。

 vector operations are slower as you know， because of the synchronization and the error list is faster。

Vctor has increment size using which vector size can be increased。

 but L does not provide the increment size。😊，And vector is thread safe。

 which means using vector from multiple threat is permitted and is safe。

 Ar list is not a threat safe。 Let's try to implement vector in programming。Here。

 I'm creating a vector of integer。Im creating the vector of string。First of all。

 I'll display the size of the vector。😊，Then I will add the elements into the vector vector dot at。

Programming。Networking。I'm just adding different domains。Database。Deployment。And cloud services。

Then I will display the vector。 I can display with the help of。Normal is out。

Would like to check the size of the vector。Victor dot size。

If in case you wanted to remove any element。Just go for the remove method pass on the index that you wanted to remove。

Again， check the size of the vector。If in case you wanted to remove all the elements。

 just use clear method and just check the size of the vector。Let's try executing this piece of code。

So here I get the error where two brackets are being used。

So here we can see that initially the size of the vector is0。

 five strings added and the size became5。😊，Then vector1 element gets removed。

 the size became4 and then cleared all the elements， the size became 0。😊。

So that is how vectors comes into the picture in real time in one of the example I will also demonstrate you how you can use any of them like alist linked list or vector to store the objects or a class type into this particular list。

See you in the next session until next time， Stay tuned。 Thank you。🎼。



![](img/0e5673b2b31080000b2375900f8a324b_6.png)
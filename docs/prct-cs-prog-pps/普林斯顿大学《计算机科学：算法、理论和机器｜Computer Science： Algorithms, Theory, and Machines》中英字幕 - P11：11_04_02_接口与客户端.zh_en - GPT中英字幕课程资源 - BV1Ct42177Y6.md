# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P11：11_04_02_接口与客户端.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/0229689202a7bf5aaa554130df1e3327_0.png)

Today we're going to talk about symbol tables， a classic data type with numerous applications where a classic data structure and variance to that data structure allow us to achieve performance gains that are extremely important in the performance of our computational infrastructure。

We're going to follow the same basic structure as the last lecture where we give the APIs。

 present a challenge of how to get performance， implementing those APIs。

 and then look at classic data structures that help us address the problem。

Let's go back to Bob and Alice and the idea of using a whitelist filter with merge sortt and binary search to say maintain customer accounts or client accounts and Alice says well it's kind of a pain sometimes really hers company is doing really well Bob maybe not so well hasn't noticed but what Alice says well we have to resort the whole list whenever we add new customers And the other thing is we want to process transactions and associate all sorts of information with our customers the bottom line is that that API。

 we just merge sort and binary search is not quite enough we need a much more flexible API and that's what symbol tables are all about。

to think about it so why are telephone books obsolete now well they don't support some operations so one they don't support is change the number associated with a given name it's already printed but another one even more important is what if you need to add a new name associated with a given number you have to wait for next year's telephone book or what if you want to remove a name and associated number again with modern systems we just do that in our digital devices and it's all fine but the solution we presented with merge sort and binary search and the sort of and searching lecture has that same problem we don't support the operation of adding a name or removing a name and so with symbol tables。

 we get that flexibility in symbol tables by the way are the basis of the systems used in your digital devices to。

phone numbers。The idea is called an associative array of abstract。 It's really a very old idea。

 So what you want to do is imagine using arrays， but rather than forcing the indices to be between zero and the array size minus-1。

 let's imagine that we can use string values。 So then a phone book would be something like this would have an array called phone numbers and then within the brackets we have a string instead of an in that's restricted to a certain range and then the result then we can assign other strings to the array kind of in that way。

And actually， or so in Alice's case， maybe there's transactions。

 it is a string that includes a date and an amount and a vendor and so forth。

It's actually the case in some programming languages， not Java。

 that you can write code like this and underlying this code is the kind of implementation that we're going to talk about today。

 a symbol table。Here's another example that is common in the web today you want to associate string with a URL and vice versa so it's the very fundamental abstraction what we talk about is using keys to access associated values and the keys and values could be any type of data but we have the simplest client code that you could imagine just put the key inside brackets and then assign values that's the associatedsociative array abstraction there's the vice versa where we associate IP addresses with string keys。

 very flexible abstraction so the question is how do we actually implement that as a data type in Java and that's what we're going to consider today。

So let's lay out the abstract data type in the same way that we did for stacks and Qes in the last lecture。

So a symbol table is an abstract data type whose values are sets of key value pairs。

 and we're going to assume that the keys are all different。

 that's not really a restrictive assumption， as we'll see in a minute。

So the basic operations are we want to associate a given key with a given value and that might be might involve two different things if the key is not in the table。

 if there's no value associated with that key anywhere in the table。

 then we'll add the key to the table， the key value paired to the table。If the key is in the table。

 we'll just change its value， just like you would do with an array。Now。

 the other thing that we want to do is return the value associated with the given key。

 so that's using associative array and expression or the right hand side of an assignment statement。

We might want to test if a given key is in the table and then we might want to iterate through the keys in the table and get the key value pairs out。

 those are the basic operations we want to be able to perform。

Now sometimes it's useful to make additional assumptions。

 so one thing that we'll use in this lecture and it's very common and useful in applications is that the keys are comparable so that is they're in a total order if we can compare one to the other we can get a result of less equal or greater and that's true of many common keys like the strings that we used in all examples or integers or doubles and so forth。

 and then in that case when you iterate through the keys， you get sorting for free。

 the iteration comes in order， and that's very useful。As with stacks and Qes。

 we don't want to have within client code any limit on the number of key value pairs。

 that's a fundamental restriction assumption that is going to make the code much more useful just as with stacks and Qes。

And just to simplify the code in several implementations。

 we're going to assume that if a key is not in the table。

 it by default associates with special value null。And again。

 this is just a statement in modern terms of a really old idea。

 so used to have not just telephone books， but dictionaries where the key is a word and the values the definition and again in telephone book key might be the name and the value。

 the phone number used to be people still do by paper documents where the key is the time and the channel and the value the TV show。

 and then encyclopedias where the key is a term and the value is an article。

 nowadays you think of the key as what you put in a search and the value is what you get。

So that's a symbol table， abstract data type。Or in one more point before slide rules even or at the time of slide rules。

 it used to be that people evaluated functions by looking up a number in a book and getting the function value like the sine function or cosine function。

 all of these have been made obsolete by symbol tables。

Okay so let's have a benchmark example that we're going to test our implementations against and here's the one that we're going to use so we have a sequence of strings on standard input could be a very long sequence in billions or longer and what we want to do is count the frequency of occurrence of the strings in standard input and there's lots of reasons to want to do that so our keys are strings and our values are integers so for each string we're going to keep an integer which is the number of times that we've seen that string。

So here's just a simple example where we'll take some keys and so if we get it that we saw it once and so we associate the value one with the key it and then same what it was and the so now we've got four things in now we've got six things there now we get it and that's the second time we've seen it。

 so now we change the value associated with it to be two instead of one and so forth。

So we just go through the strings that we get in standard input， we look up in the symbol table。

 whether we've seen that before， if we have， we increment the frequency of occurrence we just saw another time if we haven't we put it in with a value of one that's going to be our benchmark example and we'll look at client code that does that and then we'll see if we can support that client code in real applications。

So either we change the value or we add a new key with value one。Now before doing the code。

 we have to again look at the parameterized API in we're going to use generics the same way as for stacks and cues。

 it's a little more complicated because we have two things that we want to use placeholder type names。

 both keys and values， and again we'll use those within angle brackets and then substitute real types in client code。

So now inside the angle brackets， we use the generic terms key and value。

 and there's an additional complication that we want for the implementations we're going to consider we're going to assume that the keys are comparable that means the data type that whatever type key is implements the compare to method so that means that we can sort the symbol table by keys and we can do other things that depend on the keys being in order。

 and that allows us to sort support a much broader class of implementations and also guarantee good performance as we'll see。

Okay， so our constructor creates a symbol table， again。

 no reference to the size or the maximum number or the capacity or anything like that。

 the symbol table should be able to hold any number of values in the client coach and be restricted。

So what operations do we do， well， the first is called put where we associate key in value and if there's no value associated with that key in the symbol table。

 we make a new entry with that key value pair， otherwise we change the value associated with that key to the new value。

And then there's get， which takes a key and returns a value。

 now that's the value associated with a key， if the key's not there we just return null。Contains。

 is there a value associated with the key with our convention that's very easy we get it and check if it's null。

 and then there's the idea of iterating through the keys in the table and we'll talk about that in a minute。

So that's the API， let's talk about iteration just for a second。

 and this works it' true for any collection， even a stack in a queue。

 and we can do it in lots of ways， but Java has language support for going through collections called the for each construct。

So if you have a stack， you could just say for string S colon and stack。

 that's a special syntax for the for loop that goes through every item on the stack and print it。

The way that it goes through the stack is code in the implementation。

 but we're interested in it now because of how it simplifies client code。

So it's useful for any kind of collection of data to be able to iterate through each item in the collection。

 the implementation determines which order and we use very we like it because it has a substantially simpler client code and so that's what the implements iterable thing is about in the API so actually our implementation of pushdown stacks in the book and on the book site implements iterable and what that means is that you can use it。

 the client code can use for each concept for that construct for that data type。

And we want to have a performance spec where it takes constant time per item like all the other operations for stacks。

So the question is， what code do you need within the stack implementation to implement this interval idea？

Well， this is about on the border of the kind of code that we'd expect you to write。

 but for now the answer is we did it for stack and Q so you don't have to do it。

You can read in the text about how to implement an iterator that's associated with a collection type。

And our implementation meets that performance spec of constant time per entry and for now what we can do is make use of that one。

 but really what I want to emphasize now is in client code。

 if you're using collections like StaQ or symbol tables，Use iteration。

 it makes the client code much easier to understand。

We'll take a moment to consider the question of why we use ordered keys。

 it seems to add complication Well one reason is it's very natural for many applications。

 the keys that client programs tend to use are things like numbers or strings or date and time。

 even when you have color and length， there's a natural order in the keys。

And given that natural order， that enables extensions to the API。

 we can provide operations that clients might expect。

 like give me the keys in sorted order or even more important。

 something like find the CA's smallest key， there's plenty of applications where having operations like that in the API are important。

 so it makes sense to consider implementations that take advantage of order in the keys。

In the present context， what we're interested in order for is that it enables us to develop implementations with guaranteed efficiency。

Mer sort and binary research are examples of that， and in this lecture。

 we're going to look at a data structure that takes advantage of ordering in the keys to guarantee efficient performance。

All right so let's look at a client example now， so what we want to do is take the lines on standard input。

 the strings and put them out in sorted order with any duplicates removed so the key type is going to be a string we'll just use a line on standard input as the strings in this case we're going to ignore the values we don't need the values we're just sorting the keys。

This is a really simple symbol table client， we call the symbol table BST tomage to the data structure that we're going to use。

 as you'll see。So we build a new symbol table， its keys are strengths and values are integers。

 and we're not going to use the value while there's a another line on standard input。

 all we do is put that line into the Sim table and give it a value of zero because we have to give it some value。

Now we use the for each construct to go through the keys in the symbol table and just print each one out and that's a client。

 very simple client code to get this job done so if we have our tale of two cities text first1 lines or so。

 if we pipe that， take that as input to this program we get those lines sorted in sorting doesn't happen until the fourth word where we have age and best in EpoC and so forth。

So very simple client that gets sorting done need a specialized sort。And that's a warm up。

 here's a more interesting example， which is going to be our benchmark。

 that's the frequency counter example。So now we want to compute the frequencies of occurrence of the words on standard input。

 so our key type is a string again， and now our value type is the integer which is the number of times we've seen that word。

 this is the client that I explained gave an example of at the beginning。

So now we build again a symbol table with string keys and integer values now while standard in is not empty。

 we just read a string， we check if that one is in the symbol table with ST do contains。If it is。

 then we。Put into the symbol table with key with a new value， which is the old value plus one。

So what that does is change the value associated with the key by incrementing it by one。

That's if there was a value associated with that key in the symbol table。

 we'd seen that string before。Otherwise， we put a new entry in the symbol table associating that key with one。

 saying we've seen that the first time。And then at the end we can print out the keys in sorted order with the frequency of occurrence associated with them again。

 that's a very simple client code that's useful in lots of applications and we'll look at some later on。

So in this example， again， we use this code and as standard input we provide that small test file and you see a lot of words are just appear once。

 but it of the in wass appear 10 times in that example。

 so in this case then we pipe it through the other program in order to get things in order of frequency of occurrence。

 which is maybe what we want in an application。That's frequency kind， that's the second example。

Here's a third example that's more complicated， but also not much more complicated but useful。

So one thing that you want to have is maybe an index to the words on standard input。

 So what's that mean well our key is a string， it's a word that appears on standard input。

 but maybe for the value we want to know all the places where that word occurs so。

Maybe in a book you want to know what pages it appears on or in a string。

 in a string from a web page， you want to know the places where the word occurs。

That's an indexing example。This is not much more complicated than the frequency counter。

 given the data structures that we've developed， it's a fine example of the utility of defining appropriate abstractions。

So now our symbol table is going to associate a string with a queue of integers。

So we'll make a new symbol table that associates string keys with cues of integers。Again。

 we're going to go through every string and standard input， but now we'll keep an index eye。

 which is the place that we are in the string when we're reading the I key， then we have the value I。

So we'll read a string again， doesn't contain if the symbol table doesn't contain the key。

 then we'll put it there with a new cu， just make a new cu。

And then after we've done that and if the key was already there。

 what we do is we're going to get the Q that's associated with the keyca now if it wasn't there we made a Q。

 if it was there， there is a Q， so we're going to get that Q and then we're going to call the NQ method and put I at the end of that Q。

That's it。In this case， we changed the entry in the symbol table by getting the queue out and calling the NQ method。

Now when we go through， we can print out each key and then we print out the Q that we get that's associated with that key in the symbol table and that's a cu。

 and so there's a two string method that prints out the whole thing。So now for our sample test fileT。

tech， we get an index which says for every word， the places where that word occurs。

 and you can see the utility of that in all kinds of applications。And again。

 our emphasis is that we have with this API a very flexible data type that gives us simple client code for doing complex tasks。

 you might have imagined that it would take quite a bit of code to do something like solve this indexing problem。

So in the bottom line is that symbol tables are everywhere in the computers and devices that you use from credit card account numbers to web search to cloud storage in all kinds of situations。

 you have a key that indicates what you want and you have a value which is the thing that you want and these things have to perform well they're at the basis of everything that goes on a router in the internet when it has to route something somewhere has to know where and has to look up that value in a table and many。

 many other situations in the computational infrastructure involve symbol tables。

 it's a very fundamental data type。

![](img/0229689202a7bf5aaa554130df1e3327_2.png)

So Bob and Alice or anybody else that wants to make effective use of computers。

 you're going to need a good symbol table implementation。

 and that's what we're going to consider next。

![](img/0229689202a7bf5aaa554130df1e3327_4.png)
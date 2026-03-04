# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P1：01_02_03_典型客户端.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/eaf46f9fbf7326cc8385f8b40bbcdaf2_0.png)

We're going to begin by putting our programming knowledge and our ability to be able to scientifically study programs and operation real applications to good use by studying one of the most important applications of computing。

 sorting and searching。We'll start with a， typical example of a client program。

It's called a white list filter。So this is something that comes up often in applications。

 maybe you're familiar with the idea of a black list。

 so that's a list of things that are going to be rejected for service so for example。

 if your credit card is over overdrawn or if you have spam email you want to reject that。

The opposite of that is called a white list， that's stuff that's going to be accepted for service。

 and it's very similar so that's when your account is in good standing。

 the charge will go through and you want email for your friends and relatives。

 So what we're going to talk about just as an example of a typical client is a white list filter。

So the idea is that you're going to have a file that has a strings of all the things that you want to accept the white list。

And then we're going to read strings from Standard In， say that's a much larger input。

 and we're going to write to standard out only the ones that are in the white list and of course then there might be information attached and we can use this to accept email or to accept an account charge。

Soll in our examples， we'll leave out this associated action or message content。

 say in an email spam， but here's an example， so let's say I want to only accept messages from these email addresses。

 Alice Bob Carl and Dave。So now standard in is the stream of emails that I'm presented with。

 so if I get Bob。office， that's in the white list so I'll check that and write it out to Standard out and that's just a surrogate for processing it further。

Carl， that's in the white list so that gets written out Marvin at spam。

 that's not in the white list so we ignore it at this point that's the purpose of the white list filter is to keep those bad emails off the list that gets processed there's another one from Bob that gets checked you've still another one here's some more spam that doesn't make it there's one from Dave that gets checked and goes to standard out there's our friend Eve that one's not going to make it and there's Alice and so forth so that's the whole idea to filter out the things that we do that we want to reject or to filter through the things that we want to accept for service so we want to write Java program that has this functionality and where both the white list and the list of transactions could potentially be very huge。

So here's what the client code is going to look like。

What we need is a search method and that's going to be our focus for a lot of this lecture and so that's going to be a method that takes an array。

 a string and an array is input， and it's going to let us know whether that string called key is in the array。

So given that we have that method， and remember this is a client and we're going to look at the implementation of that method much later in this lecture。

 here's what the main looks like。So it refers to argument is a file that contains the white list。

 and so we use our read all strings method from our in in our standard IO library to take all the strings on standard input and put it in an array called words that's the white list。

Men from standard input， as long as it's not empty， we're going to read a key。

And then call our search method to see if that key is in the list of words。

The interface for that method is to return minus1 if it's not there， if it is there。

 it returns its index in the array。So in this case， all we need to know is is it not equal to minus1。

 that means it is there， that's when we print it back out to standard output。And that's it。

 that's our client， so these are the examples that I just gave if white4 is our whitelist and test is that list that I gave the example。

 if we call this program white filterter with white4。

tex as its argument then it'll read that whitelist in， and then piped in from test。

tech goes into standard input， all we get printed are the ones that are in the whitelist。

So that's the setup， our goal now is to write this search program that can enable this behavior。

 particularly when both the white list and the list of from standard input is very large。

So here are our friends， Alice and Bob again， so Bob says well， Alice。

 I think I'm going to start an internet company and Alice says， sure， me too。

 I'm going to try to have a thousand customers by next month and may be a million next year。

And Bob says" well we're going to grow even faster than that， Alice says， good luck， by the way。

 you know you're going to need a whitelist filter because you're going to have accounts and clients and you're going to have to accept and reject and he said yes。

 I know I'm going to go to a hackathon to knock it out。And Alice says， well。

 I'm going to take a few CS courses， maybe an online course like this one first。

 so we'll follow Alice and Bob through this process。Okay， so here's our first try。

 which is a simple strawman implementation called sequential search。

And the whole idea is you've got the array that's got the white list。

 and you just go through the array to see if you have a match with the search string。

If the match is found， you return that index， and if it's not， you return minus1。

 that's got the functionality that we need for our white list filter。

And the code for that is pretty simple， go through all the array。

 check if the array elements is equal to the key， if it is， return it， if you don't find it。

 return minus1。So say we have this array of 15 words， the names。

 and we're looking to see if Oscar is in there。So we're just searching through the array looking for Oscar。

 maybe this is the code that Bob came up with in his hackathon。

First thing to notice about this is it didn't stop at Oscar， didn't even find it well。

 so this is just getting our heads back together on our basic parameters for how to do things in Java。

 think about why this didn't work， didn't stop at Oscar。If you think about it for a minute。

 you'll see that what it's doing is with equal equals that doesn't actually compare the strings that compares the references。

 so it's checking to see if those two things refer to precisely the same sequence of characters。

 whereas what we want is to check if the strings that they refer to are equal character by character。

 so what we need is to use compare to。So okay， that's all right。

 so now let's fix it by putting in A of I。comp to which is going to return zero。

 if and only if the strings match character by character and in that case then this works。

 it finds Oscar and returns 10。And Bob says，" okay， this was even easier than I thought。

But as we know， we have the ability to test the performance of this before we try to run it in production on large inputs。

And so we want to do two things， we want to do a rough mathematical analysis。

 and then we want to do some empirical testing and we want to know if those models match and then we can proceed from there。

So let's just think of a simple mathematical model for how this thing performs with sequential search。

 so let's say that we've got our white list length is N， and then for some constant C。

 we have CN transactions， so 10 times or 100 times as many transactions as there are in the white list situation might be different in an application。

 but this will give us an indication。And we'll also assume the string length is not too long compared to N that really the number of names is what's huge。

So here's a quick analysis of that so the first thing is if it's on the white list what's going to happen well if everything's random you're going to go about halfway through the list on the average and so that's an easy thing to analyze even easier is if it misses then it's going to go all the way through the white list on the average so either halfway through or all the way through。

Well， if you've got a constant times n transactions and either you're checking n strings or n over two strings。

 the expected order of the growth of the running time is going to be proportional to n squared。

 it's quadratic。So that's a mathematical analysis we should expect the running time for random strings to be quadratic。

Well， let's check that with empirical tests， so first thing we need is an input generator。

 so this is a short program that we're going to use to generate random strings of a given length from a given alphabet and this will give us the flexibility to test our programs in lots of different situations。

So it's got a method random of string that takes a length as one argument and an alphabet。

 the characters that make up the string as a second argument。

So what we're going to do is make an array of characters that is the length that we want。

 and then we're going to go through that array and what we're going to do for each position in that array is generate a random integer between zero and the length of the alphabet。

And then pick out that character in the alphabet， so that's a random character out of the alphabet。

 and we're going to assign that to A of I。And then when we're done we'll just make a new string from that array of characters。

 so that's a simple method to return random strings。

 then our driver will take the number of strings that we want from the command line and then the length is a second argument and the alphabet as a third argument and then just generate in strings of the given length from the given alphabet。

Pretty simple program once you've seen it and here's the type of things we can do so we can say give me 10 strings of length three from the alphabet ABC and that's what it does and that might be useful in a situation where we have not many customers but lots of transactions from those customers and it turns out that the performance of sorting and searching algorithms can vary depending on how many duplicates there are so that one there's a good chance of duplicates。

Or if we take say， eight digits and we take our alphabet to be from 0 through nine。

 then we're going to have much less of a chance of duplicates。

Or in another application that we're going to look at later we might have a really long string just one from the alphabet ACTG we use that to test algorithms from genomics where it's a long string there might be only one of them and all of those situations are covered by this generator Okay。

 so let's take a look at what the test client for our sequential search program and look like so we'll match what we assume for a mathematical model and say we'll do 10 end searches in a white list of lengthIn。

So。We'll first have our search routine that's the code that we just discussed and then here's what the main routine looks like for this so again we take our white list from standard input and so that's the length of the white list is N and now we'll keep track of the time using system。

 current time and milliseconds divided by 1000 system in seconds we could also use our stopboards class that we developed earlier and now for I from zero to 10 times n so that we're going to do 10 times n in this loop。

And what we'll do is just pick a。A word at random out of the white list。

 so we know that our search will be successful， so there'll be no output。

 so that's good for running a big empirical test like this to have no output。

And so then we're just going to check that it's。Whether or not it's successful。

 we know it's going to be successful so we're not going to print it out but we did the search and then after we've done 10 end searches then we'll check the time again in what we want to print out is the number of seconds that it takes to do this process so with this test client now we can run this for huge files using our generator so for example this generator generates 10。

000 words of length 10 all lowercase characters and I just abbreviated the alphabet with a to Z in so it fit on the slide。

So in this case， if we run this， we're generating 10，000。

10 letter words and we're going to print out the time to do 100，000 searches in that list of 10。

00010 letter words and we get the result three seconds。

So now we can use this test client to go ahead and do doubling tests of the type that we learn when studying performance in the first part of the course。

So again， white list of size and 10 n transactions and all I'm going to change is the size of the file from that last example。

 so we get three seconds for 10，000， if we run it for 20。

000 takes 9 seconds and also keeping track of the transactions per second。

 just as a measure of how well we're doing。Run it for 40，000， it takes 35 seconds。

 now we start to compute the ratio of the time for n over the time for n over two， 80，149 seconds。

 it's taking a fair amount of time for sure and the transactions per second is going way down。

So Bob wants to have his million customers， well it's going to take 38，000 seconds。

 that's 10 hours just to do this whitelist thing and what's worse is it's down to 34 transactions per second and dropping。

So Bob can see that that's maybe not too good and if we go and just look a little more carefully at what the doubling test means。

 remember that this ratio tells us the exponent in the growth if the running time proportional to a constant times n to the B with this doubling test if you take log to the basease2 or this ratio that's going to give the exponent so this says that the order of growth is n squared log base2 of4 is2 so that validates the mathematical model and we have a lot of confidence that the running time of this thing is going to be proportional to the square of the size of the white list and that doesn't scale and that's not going to work too well for Bob's business so we're going to have to look at better methods than sequential search for solving this problem。



![](img/eaf46f9fbf7326cc8385f8b40bbcdaf2_2.png)

![](img/eaf46f9fbf7326cc8385f8b40bbcdaf2_3.png)
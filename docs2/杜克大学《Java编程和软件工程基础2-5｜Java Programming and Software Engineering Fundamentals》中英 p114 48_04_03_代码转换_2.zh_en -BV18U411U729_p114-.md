# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p114 48_04_03_代码转换_2.zh_en -BV18U411U729_p114-

![](img/17aaaa4ff2679c2617def65b029803b8_0.png)

We'd like to find out how many times somebody visits a website。

 So we are going to look at a log file that has I addresses and see， for example， for one I address。

 how many times did that IP address appear in the file。

 That's how many times that person visited the website。 So we have a program here。

 a class called log Anar。And。

![](img/17aaaa4ff2679c2617def65b029803b8_2.png)

We are going to write the method。Count visits per IP。

 So how many times does each I address visit a page。And what we have in here is we have。



![](img/17aaaa4ff2679c2617def65b029803b8_4.png)

We're going to put log entries in an array list， it's called recordss。

So we have a constructor that initializes that array list， we then have read file。

 which is going to have the file name of the log entries。

 and that is going to allow you to select a log entry file and then it just goes through and reads through all the lines and puts them into records。



![](img/17aaaa4ff2679c2617def65b029803b8_6.png)

So we're going to focus on writing count visits for IP， and we're going to use a hash map to do that。

So the first thing we're going to do。Is we need to make an empty hashm and we're going to be mapping a string to an integer。

 so for each IP address， which is a string， we're going to map that to the account。

 which is the number of times that IP address appears in the file。So first， let's make。Let's see。

A hash map。Of type string， which is the type of the key。And of type integer。

 which is a type of the value。For the hash map。We need to give it a name。

 so we're going to call it counts。And then， we have to create。A new one。 So a new。Haash map of type。

String for the key， and。Integer。4。😔，The value。There we go。Nowao。Now that we have it。

We want to iterate over all the records that we have， so we're going to use a for loop。4。😔。

Each log entry。We need a variable name， so I'm just going to call that L E。

We're going to iterate over the records where we've put all the records from the file。



![](img/17aaaa4ff2679c2617def65b029803b8_8.png)

Okay。

![](img/17aaaa4ff2679c2617def65b029803b8_10.png)

AllThere's our for loop， and now we're going to look at each log entry one at a time。

So first what we'll do from the log entry is we'll get the IP address。Okay。

 so we need a variable for that。 And that is going to be of type string。 So we'll call that variable。

 say I， which is of type string。And we will use the log entry to get the I P address。

 So if you remember， we have。Get。Iipi。😔，Address。And that should get us。The I address。

Now that we have the IP address， we have to see if it's already in our hashmap or not。

So we'll have to ask a question about that。So we're going to ask if。Counts。Dot contains。Ki。😔，Okay。

 so again， counts is our hash mapap and we're using the containss key function。

And we will ask if that IP address is in there or not。

And I'm actually going to ask first if it's not in there。 So we'll put the knot there。

And if it's not in there， then that means we want to put it in there for the first time。

 and we put it in there for the first time， its count is going to be one。 so we'll add code for that。

So we get the name of the hash map， which is counts and we'll use the put。

 and we need to put in the IP address， which is the variable IP， and we put in one for the count one。

Now， if it's not in there。Then we'll want to， sorry， if it is in there。

 then we'll know it's already in there。 We need to get the value out。 We need to add one to it。

 and we need to put it back in。 So we'll do that now。So essentially。

 we're going to use count stop put。But what we're going to put in there is we're going to put the IP address in there again or basically replace it。

With we have to get the old value out and add one to it。

 So we'll have to use counts dot get to get the old value of it。

And then we'll have to add one to that。And then what else we have to do。

 we come down here So if we get to the end of that and we've looked at all of that。

 we put all of our log entries into our hash map and essentially they're each in there once with the count of how many times they appear in the file。

 then we can return the answer。Which is just counts。So we'll compile this。And let's see。😔。

We got to spell get IP address correctly， so we'll fix that。

And we've compiled it with no syntax errors now。

![](img/17aaaa4ff2679c2617def65b029803b8_12.png)

Al right， so now we want to test this out again， let's just see count visits per IP is going to return the hash map that is all the mappings of the IP addresses to their counts。

 so you get the whole thing。We need to test it out now。



![](img/17aaaa4ff2679c2617def65b029803b8_14.png)

So in order to test it out， we're going to create another class here， which I've started。



![](img/17aaaa4ff2679c2617def65b029803b8_16.png)

Called count Tester。And what we'll do in here。Is we'll first create a log analyzer。

The class that we just had， so we'll create a log。Analyzer。Object， we'll just call it L。

 and we have to create a new one。Okay so now we have a log analyzer object。

 we'll need to pick a file to read from。So I'm going to use the read file。And we'll put in。

 I happen to have a really small test file to make sure and convinces myself that this actually works。

So， it is called short。Test。😔，Log。And I'll show you that in a minute。

And then I want to now call count visits per IP and remember that's going to return a hash map。

 so I need to have a hash mapap variable to put it in。So I'll do that。Hash map of type。String。😔。

Vniger。I'm going to call it counts。And now that is going to be assigned the value returned by our log analyzer。

 which is called L A。 And that's going to call the method we just wrote， which is count。Visits。

Per I P。And then once we have that， we can just print out the hash map that we created。

 So I'll just have system dot out， print line。Han。😔，Counts。Now let's see if this compiles。

And we're missing something， let's see。We need to use。 We use the wrong kind of quotes。

 So we'll put double quotes here。And we'll try compiling it again。And we forgot the colon at the end。

 So my semicolon at the end。Alright， good， we're good。 So that works。

 And I want to show you over here my simple file and then we'll run it。

 so I have this very short test file and you can see it's got 1，2347 log entries in there。

 You can see the second entry which is 152。3。135。44 is in there three times Now we're going to run it。

 So we'll come over to blue J。 Everything's compiled。 we'll run count Tester。



![](img/17aaaa4ff2679c2617def65b029803b8_18.png)

We've got to create the new object first。And we'll run。And there we go。

 and you can see if I can put both of these up here at the same time。



![](img/17aaaa4ff2679c2617def65b029803b8_20.png)

There we go with one。

![](img/17aaaa4ff2679c2617def65b029803b8_22.png)

So we created a hash map。And you can see that the one that starts with 152。

3 is listed as being there three times。 That is we print out the hash map and it prints out each IP address equals its count that we came up with。

 And so the second entry here is 152。3。135。44 with a three and you can see the 157。

551 is only in there one time and we got one and you can see the 152。3。135 is in there twice。

 and you can see we counted it twice。 So now I'm more convinced that what we wrote is correct。

 All right， happy coding。

![](img/17aaaa4ff2679c2617def65b029803b8_24.png)
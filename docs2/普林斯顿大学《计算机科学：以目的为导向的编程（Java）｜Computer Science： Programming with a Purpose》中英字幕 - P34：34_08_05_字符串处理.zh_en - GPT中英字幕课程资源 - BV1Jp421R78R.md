# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P34：34_08_05_字符串处理.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/1f7f4db03f0b4a7327301a487fd4dabe_0.png)

To finish up our study of the use of abstract data types。

 we're going to take a look at string processing in a bit more detail。So as mentioned。

 we've already been using strings， it's a sequence of UniIcode characters。

 and Javas ADT defines operations on string that allows us to write programs that manipulate them。

We've already been using a few simple ones like the constructor or in Java。

 if you put a sequence of characters inside quotes， it creates a string。

You can get the length of a string or you can get the I character but there's many other operations that are defined。

 for example， you can get a substr between index I and index J minus1 by calling this method。

 you can find out if a given string if our string contains a given string。

You can find out if this string starts with a certain given string or ends with a certain given string。

You can this method index of searches through the string to find the first occurrence of a given pattern。

Or the first appearance of the pattern after a given index concat we've been using with Java built in plus operator。

 but it creates this string with a new string T appended， you can compare strings。

 you can do very powerful things by changing all occurrences of a given string A to another string B within a string。

 replace all。Split， if you give a delimiter， then you can get an array of strings that are in the original string。

 every occurrence of the delimiter defines an substr and you get array of those substrings。

 we use those for examples， to take a text where words are separated by blanks and turn that into an array of words。

And you can check whether a string is equal to another string。

 it actually equals takes an object as its argument， of course。

 if the object is not a string it's not going to be equals if it is a string。

 then that's a check for whether the value is the same and we'll take a look at now some programs that use these methods。

 they are very useful and powerful and string processing is a very important paradigm in modern programming as we'll see。

So here's some typical examples， just a couple of toy examples。

 so is the string of palindrome does it read the same forwards and backwards。

 well we get the length of the string then we go through half of the characters and then we just check that if the character I from the beginning is equal to the character I from the end if it's not you return false。

If you get all the way through， then you return true。So that is the string of palindrome。

Let's find the lines containing a specified string in standard input。

 so we take a query from the command line while standard input is not empty， read a line。

 check if that line contains the query， if it does print it out， and there we go。

 that's a simple way to look in a file for the lines that contains certain words。

 for example in a program， the lines that use a certain variable。

 we'll look at later in the course at expanded version of that operation。

And here's so maybe the text file on Standard In you want to look for the hyperlinks and endin。

edu and again so we can read the strings from standard input and if it's a hyperlink it's going to start with HGTP// and it ends with pointedDU then that's the string that you want so all kinds of things like this。

 all of those methods provide extremely flexible basis for processing strings and we'll see plenty of examples as we move through later in the course。

Here's a very important example from molecular biology for many years， the challenge was to。

Find out the sequence of DNA in， in a human genome。But that happened maybe about a decade ago。

 and now the thing is that we have all this data that it's a huge amount of data that characterizes the genome and what we want to do is try to understand the structure that's what scientists do nowadays in genomics。

And so the idea is to represent the genome as just a string。

 there's four different types of things in the genome， and we call them ACT and G。

And we can think of the thing as just a string of A's， T， Cs， and G's。

And it might be a hugely long string， might be billions of characters depending on the organism and so forth。

 and there's many， many of these out there that scientists have sequenced and discover the actual sequence。

 but now they need to write programs to understand the structure and that's string processing。

So for now we'll talk about the idea of a gene， which is a substring of a genome that represents a functional unit。

And what。Scientists know about genes is that they're made of things called codons。

The ACT and G elements are called nucleotides and if you have three of those in a row。

 you have something called a codon and the codons for a gene just before a gene。

 there's the sequence A T and G， just those three letters。Then。At the end， after the gene。

 there's one of these occurrences of。Three letters of codedon TG， TAA， or TGA。

So we have a start codon， then we have a bunch of codons and then we have a stop codon and if everything in between is a gene as long as that thing is the length of it is a multiple of three。

 that is it has to be a sequence of codons。So in this genome， with that start and that stop。

 we can identify that gene。There's actually another one。A short one。 It might not be a gene。

 but it's a potential gene that worthy of further study。

So our challenge is to write a Java program that can find genes in a given genome。And again。

 you want to think of this genome as being something extremely long。

 maybe millions or billions of ACs and T's and G's。

As a warm up we'll do a little bit of a simpler task is just identifying whether a given string follows these rules and is a potential gene。

 so given that string we want to check does it begin with a start codon does it end with a stop codon and if so then what's in between is a gene？

So let's look at that program。So we're going to use a static method that takes a string as an argument。

 and then it's going to return either true or false depending on whether it's got the proper structure。

So the first thing is。The length of thing has to be a multiple of three。 So divide by three。

 check the remainder， if it's not0， then return false。Can't be good。

Then the other thing is it's going to start with AG。It doesn't start with AG return false。Again。

 each one of these lines is enabled by a method in Java string data type。

 where computing with strings using the set of operations in the data type。

So now we go through the rest of the string。And jump three at a time to check all the codons。

 pick out the given codon， if it's equal to a stop codon， then and we're not at the end。

 then we have to return false。The only time that it's legal to have a stop co on is right at the end if it ends with TA。

 TG or TGA， then return true。And if we don't find the S co on at the end， then we return false。

So now this is a main that just reads a string from command line and calls this function。

 and so if we call it with our example， we get true。If we call it with a slightly longer example。

 not when we get false， in that case it' because the length is not a multiple of three。

 and here's another one where there's a stop codon in the middle that returns false as well。

So that's the kind of processing that we can do with Java string data type that helps us address the scientific problem。

The real problem of interest gene finding， it's a little more complicated but not a lot more complicated。

 we can go and go ahead and scan left to right through the data when we find a start codon we can set a variable to the index where that thing is and then if we find a stop codon and then we're a multiple of three then we found a potential gene we can print that and then reset or are we looking at a gene or not indexed to minus one which indicates that we're not。

And so this is just a trace that you can study for how this method would work every time it finds a start code on。

 it looks， it keeps track of that index until it finds a stop and if it finds a stop and it's on a multiple three。

 it prints out the gene so it finds those two putative genes in this example。

The code for this is a bit more complicated than the one I just showed。

 but not a lot more complicated and we'll leave it as an entertaining programming exercise for you that uses string operations。

 again， it's interesting to think about how Java might represent strings。

 but it's an abstract data type and our program should not be dependent on it。

 but it's so good to have a mental model of what's going on。

 particularly when it comes to performance and we'll come back to that。

So here's a possible way that it might be represented in a Java system。

 so our variable genome maybe will point to an area of memory that has two things in it。

 it's got the length of the string so we can get that quickly。

 and then it's got a memory address in this case， X。

 which is the place where all the characters are laid out of sequence。And with that representation。

 then when the Java has to implement the various methods。

 lots of them it can do very efficiently getting at the I character and so forth with only a few operations。

And then for example， substring， one thing that a way that it could work is it looks just like a string。

 so substring S starts at one and then goes to index 5 so this says that S starts at x plus1 which is the first place and it's of length4 and then it can point to that same area where those letters are and that's a very efficient way to represent substrs and then T starts at9 is of length4 and so forth so that's one way to represent strings and again maybe our programs don't depend on that。

But it does have some implications。 One thing is that S and T are not the same string。

 They're different strings。It might be another memory representation where someone decides it's better to implement substrs such that S&T actually would be the same strings。

If you say S equal equal T， then that's going to be false because those things are different。

 equal equal just would compare the addresses， the references。

But you do have to say if you say S equals t， then that's the whole purpose of the equals method。

 it's going to compare those character sequences and tell you whether or not those strings have the same character sequences。

So the point of this is that the API doesn't always have all the details。

 you need to know a little bit about the context in order to fully understand how all the methods work。

Al right， so here's a summary for object on oriented programming。

 what you're going to be able to do is to create your own data types。

 your own sets of values and operations on them， and then use them in your programs。

Object oriented programming is about manipulating objects。

 which are things that hold a data type value， variable name for refer to objects。

 but really what we're doing is manipulating the objects in the data type values that they hold。

In Java， what programs do is manipulate references to object。

 All of these things that we've talked about are what's called reference types。

 which is different than a primitive type， primitive type。

 like a double the variable refers actually to the value all of these others refers to a reference to the value So bull it and double and so forth。

 their exceptions to this rule， and actually in some object oriented programming languages there's no separate primitive types and some people believe that language shouldn't have them。

 but the great efficiency gains that you get with them has proved very effective for Java so the purist versus the practitioner struggle continues if you're a practical program you want those primitive types。

But the main idea is in this lecture is that you can write programs that can manipulate abstractions like colors。

 sounds， pictures， strings in the next lecture you're going to learn how to define your own abstractions and write programs that manipulate them and that's when you've really brought your ability to program up to a whole new level and we'll see many examples of that。



![](img/1f7f4db03f0b4a7327301a487fd4dabe_2.png)

![](img/1f7f4db03f0b4a7327301a487fd4dabe_3.png)
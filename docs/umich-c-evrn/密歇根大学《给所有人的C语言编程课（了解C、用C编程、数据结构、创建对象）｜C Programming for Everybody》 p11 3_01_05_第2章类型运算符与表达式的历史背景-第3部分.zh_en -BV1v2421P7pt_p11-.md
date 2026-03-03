# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p11 3_01_05_第2章类型运算符与表达式的历史背景-第3部分.zh_en -BV1v2421P7pt_p11-

![](img/8e2f87e888f28bde7dab376ede57a645_0.png)

Now another thing that C really was one of the early innovative language was byte addressable computers right and so we don't think much everything's a string and we can look at the characters in the string。

But in the old days before C and the generation of computers that kind of triggered C。

 we didn't have characters， so you couldn't in the hardware to load a character。

 you could only load a word， and then you had to find the character within the word。

And the language that really was the immediate precursor to C was the B language。

 and the difference was is the B language was a really cool。Low level word oriented language。

 And then the C language came from B and became a byte oriented language。 And so C sort of like said。

 we're going to do bite address。 So if I take a look at the way I had to do character character support in a C D6。

6500， which is the computer I was using in like 1975，1976。



![](img/8e2f87e888f28bde7dab376ede57a645_2.png)

It was a scientific computer。 It， It barely cared about printing characters。

 It didn't even have lower case。 It had 60 bit words and packed 6 bit uppercase characters。

Into those words。And it used a series of zeros to fill it up。

 And so if I put the word wordsHello world into the CDC 6500， it took two words。And hello， space W。

 O， R， L was packed into the first word。 And D was in the second one。

 And then we did what was called0 filling。 The rest of those characters were all zeros to integer 0。

0，0，0，0，0，0，0。And if I wanted to know what the fifth character of this two word string was。

Like the O， for example， you would create a mask。 And in that mask。

 you would have zeros where you wanted to get rid of stuff and ones where you wanted to copy stuff。

 So you would take hello world， and you'd run it through this mask with the bits in the right position。

 and then you would get the O and all zeros in the rest of the word。

 and then you would have to shift it half the way down because there were 10 characters。

 so I had to shift it5 characters to the right。 And then you would have the letter O in the bottom 6 bits of that word。

 And then I could write an if statement。

![](img/8e2f87e888f28bde7dab376ede57a645_4.png)

![](img/8e2f87e888f28bde7dab376ede57a645_5.png)

That's how I would say if the fifth character is the letter O。

 I had to extract the fifth character by hand。

![](img/8e2f87e888f28bde7dab376ede57a645_7.png)

So you can imagine how happy I was when I began to see programming languages that allowed me to use more of an race syntax and say string sub five。

Or even in this case，0，1， to3 for strings of 4， But I could treat characters as an array。

 The notion of a character array for me in in 197 in 1977 was。But why would you， you know。

 you couldn't do that， right and so。We。You know， a whole。

Generation of programmers went go through their entire career without having do any masking and shifting。

 So this chapter is going to talk to you about it。 And you might say， well。

 if C was so good at doing it for you， why did they show it。

 And that is that people like me would not have had respect for this language。

 if it weren't for the fact that they had a good masking and shifting。

 because we were doing that all the time in these word oriented computers and word oriented languages。



![](img/8e2f87e888f28bde7dab376ede57a645_9.png)

![](img/8e2f87e888f28bde7dab376ede57a645_10.png)

And just as C and Eunuchs were making the world safe for characters， then we had this other problem。

And I'm only going to talk a little bit about this。Just don't worry about it。

 the concept of Indianness。If you're loading words。

 do you load them with the least significant digits first or the most significant digits first？And。

Most computers。Were。Big Indian and big Indian to us software developers made the most sense。

 because that's how we thought it would lay out。 But it turns out that。

A few processors wanted to load， if they were going to do an ad。

 they wanted to load the low end of the integer first so they could start the addition while they're adding bring in the high end and they could overlap the load and the ad。

And then Intel， which in those days， wasn't all that popular。

 but they were so interested in the microprocessor performance that they became little Indians so that their loading an addition were fast。

 And so we've been stuck with a lot of little Indian microprocessors since then。

 and big Indian and little Indian。 It's， it's one of the harder things to solve。 really。

 It really is。 And so I'm going to show you some code。 I really。



![](img/8e2f87e888f28bde7dab376ede57a645_12.png)

I really， all I want you to do is feel sorry for those of us who had to figure out little ending and big Indian。

And let me just give you an outline of what this code is doing。

 I'm not going to walk through it in detail。 It just is kind of scary。 So， and。

 and you're not even going to understand most of this code until chapterpter 5。 is's just。

 let's just talk a little bit about the bits and how masking and shifting would have worked。

 If we didn't have character arrays。 So what I'm doing in this program is I'm creating a character array。



![](img/8e2f87e888f28bde7dab376ede57a645_14.png)

The length of this character array is hello world plus1 for the Terinator， H ELLO space WORLD。

 so 11 plus1 should be 12 characters are allocated。



![](img/8e2f87e888f28bde7dab376ede57a645_16.png)

And then what I'm doing in this next line that says int star S I is I am actually saying I want to take the same storage and pretend it's an integer array。

And so that's what that line is， it takes the address of the beginning of the first character。

And convert it from a pointer to a character。Which is cha S is a pointer to a character and have it be a pointer to an integer。

 And again， I'm sort of like jumping ahead in chapter 5。

 So I'm I'm not expecting to understand all this。 I'm just。



![](img/8e2f87e888f28bde7dab376ede57a645_18.png)

Just making you aware of it。

![](img/8e2f87e888f28bde7dab376ede57a645_20.png)

In those first two lines， I've got a character。Aray and an integer array。Okay。

 and this is a this is a 32 bit integer。 and so that means that。

The characters are stuck into 32 bit integers in a little Indianian way。And so if you look。

 that means。That if you just look at memory from left to right， that the。

The lowest of the first four， which is 32 bits， the first character that comes out is the L right and you can see the little Indian which in your mind thinks it should be shifted。

 but that's because this is running on a little Indian computer and different computers will give you different results。

 and this is a little Indian example。And so you can see。With masking and shifting， where。

I'm going to try to get the E out。Which would normally be the second character。

 but it's kind of the second from the bottom of the first integer。And so what I do is I make a mask。



![](img/8e2f87e888f28bde7dab376ede57a645_22.png)

And I'm going to print this out， I take FF， which is。8 bits of ones。

 And then I shifted up eight characters to the left。 and you can see that in the printout。

And then I mask out that character。Which is the E。But then it's in the wrong position。

 and then I have to take thatmaed result， and I have to shift it back down 8 so that it's in the bottom part。

 so now I can check to see what that letter is。 This is how I would pull out the second character of a string so I could check to see if it's an E。



![](img/8e2f87e888f28bde7dab376ede57a645_24.png)

![](img/8e2f87e888f28bde7dab376ede57a645_25.png)

Because I can't compare directly the second character of string， right， And Python， you're like。

 whyhy are we doing this？That's why you build a string class instead of use a character array for this。

 And I made it even worse by like starting with taking a character array and viewing it as an integer array and then playing with the integers。

So。You don't have to understand this。

![](img/8e2f87e888f28bde7dab376ede57a645_27.png)

Just。Be thankful that you use Python and if you don't use Python， you use C。

 and whether it's a big Indian or a little Indian machine。

 you can treat an array of characters as an array of characters and you can get the third one or the fifth one with a square bracket notation。

 okay？🎼Storage allocation storage allocation storage allocation so a summary of this lecture is we talked about number based conversion。

 we talked a little bit about division， why the Python 2 integer division happened I don't really have a really good answer for that concept of integers and words and bytes and masking and shifting and characters just because these topics are covered in this chapter and they will feel very foreign to you and unnatural but just give a shot。

 read through them， understand them and and they'll make sense later later we're going to learn about structures and pointers and addresses advancing and stuff like that it'll all make a lot more sense coming up。



![](img/8e2f87e888f28bde7dab376ede57a645_29.png)

🎼Yeah。

![](img/8e2f87e888f28bde7dab376ede57a645_31.png)

Yeah。
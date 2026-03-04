# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P34：34_08_05_机器操作.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/4b1b7a469220c64f7ea06454c1338878_0.png)

So now that we've seen a program， we can look at how people actually used to operate such machines beginning of the computing。

So this is what the front of the machine looked like。 And again， this is our imaginary machine。

 It doesn't look that different than a real computer。And it might be hard to believe。

 but this is the complete user interface of a lot of early machines we've got switches。

 we've got lights and we've got a few control buttons and they're labeled with pretty much what they do so the first thing that we have to do to use the machine is turn it on and sometimes that would be just plugging it in or sometimes there was a key but for toy you just press the on off button。

And then it lights up it says that it's on， and that's the only way you'd know that。

Then what you need to do next is load your program into memory。

 so this is the little program that we just did that adds two numbers and by the way this was before postits even existed。

 but we'll pretend that there's a post it that's got the program it would be a small scrap of paper with scotch tape on it actually。

So to load an instruction， then what you need to do is you there's a set of eight switchesed labeled address and a set of 16 switches labeled data。

 so you have to set the address in binary so that's flicking up that switch so that represents 10 and hopefully the light lights up。

And then we have to put the data switches to set what the instruction and codingding is。

 so the first one is 8， so that's 1000， next one is a， that's 1010。

You might think of a as 10 in binary， 1010 maybe do the conversion of binary first one digit at a time you get pretty you get to do this pretty quickly after a while next digit is 1 next digit is 50101 flip up those bits so now we've got the switches set to the instruction and we've got the address that we want to put that instruction in so now we hit the load button and that'll load the instruction from the switches into theAdd memory word。

And after it loads， the light goes off。So there we go。

 We've got one instruction in the machine and then flick the switches down。

 Good practice to flick them all down。And you could do that by running your hand across them and that's why those go quickly。

And let's go to the then the next instruction and the next instruction， we do it all over again。

Lo the address in this case， it's 11 key in the instruction， it's 8， and then B， 10，11。

 and then a1 and then 6。 So now we've got that instruction encoded and we can press the load button and now we have the second instruction in。

Flip the switches down， do the third one。Third one is location 1210010010 now you can see why you want to be working in Hex。

 if you're trying to do all this in binary， it would get even more confusing。

And now do the data switches to do the instruction encoding and you can also see how quickly you can convert from Hex to binary。

 so C is 1100 A is 1010 and B is 1011 and now that instructions is encoded in the switches and it's addresses is there so we press the load button and load it in。

And then click the switches down and do the next one。

This is the store instruction and it's in location 13 and then the 9 C， which is 11001 and 70011。

Now that's encoded and we press load and flick the switches down。

And then go to load up the halt instruction and the halt instruction is easy， that's at location 14。

 the data is 0，0000， so we're done with that and then we just press load and it's all loaded。

So at that point， we have our program loaded into the toy memory。

And we have to kind of trust that it's in there but there is a button that helps us at least double check that we got our program right and that's the look button so if you want to double check that you loaded your program properly and didn't have a bug like put in a wrong Hex digit somewhere what you can do is set your memory switches again。

 so 10 and now when you press the look button it'll tell you what is what is in that memory location。

 just press the look button and then in the lights it'll tell you the contents of that memory location in this case as what we wanted8A15。

And typically， if you're a cautious programmer， you'd go through and double check that every memory location has the right instruction and the consequences of a boggger。

 a little harder to deal with in a program like this than in a Java program on your laptop。

So now we've got our program in and then what do we do next well we want to load data in。

 well how do we load data in well exactly the same process。

 no distinction between data and instructions， so we load our address in 15， our data is 80008。

 hit the load button and it's loaded。And then we have one more data thing， and that's in location 16。

 So that's 0，1，1，0，0， binaries 6。And then set the data switches to five and then press our load button。

And now we're set to go， we forgot our program and our data loaded into the memory。

 and now we want to run a program， so what we do to run a program。

 set the address which is to the address of the first instruction in this case it's 10 in press 1 run and what does run do。

 it just starts that fetch increment execute cycle。When you press run。

 the program starts running now the data lights might flash sometimes and but what's going to happen is after a while the run light goes off。

 maybe you noticed it went off， goes off when the halt instruction is reached and that's the only clue that you have that your program executed。

As the run light goes off。So then how do you figure out what it did， well。

 we have the look button to see the output， what we're going to do is set the address switches to the address of the expected result in the memory。

In this case it's 17， notice we don't have any way to look at the registers， they're temporary。

 we just have ways to look at the memory。So we look at 17 and hit the look button。

 and it tells us our result that D。If we want to run the program again and enter different data。

 we can do that， enter different data and press Run again。

 and write down those answers on those postits or in a piece of paper。

That would be the way that we would enter and run a program in an old machine like PDDP8 that we're representing with our imaginary machine toy。

Nowadays， I think many people find it unbelievable that people programd in this way。

 the people really program in this way， and I have to say yes， absolutely， in fact。

 here's a guy programming at PDPA people used to programming white shirt and ties too。

 and I have to say I spent three years of my life programming in this way。

 and we'll talk in more detail about this process later on。



![](img/4b1b7a469220c64f7ea06454c1338878_2.png)

![](img/4b1b7a469220c64f7ea06454c1338878_3.png)
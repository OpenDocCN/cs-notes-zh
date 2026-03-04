# CppCon【中英⚡CppCon 2024】 p10 P11 How to Quickly Convert Floating-Point Numbers in C++ - Cassio Neri - CppCon -BV1NHEEzdE92_p10-

![](img/7fde77efe88ea5fe90557eaddb17b60f_0.png)

Just coming here made me realize how much better an in person conference still is it doesn't even compare so it's been really great being here again。



![](img/7fde77efe88ea5fe90557eaddb17b60f_2.png)

![](img/7fde77efe88ea5fe90557eaddb17b60f_3.png)

Before anything， let me tell a story from ancient Greek mythology。



![](img/7fde77efe88ea5fe90557eaddb17b60f_5.png)

This is the fight between Hercules and the Hydra Wener Hercules committed a very serious thing he was remorseful。

 he fell deepening his heart， so to be forgiven and live in peace he was ordered to complete 12 hard labors of which killing the Hyda was only the second one。

The Hyder had several heads and very strong regenerative power so that every time Hercuku is chopped off one of the hydra's head out of the wound。

 almost immediately one or more heads would fall it was indeed really hard to kill the hydra。

 but he allows Hercu's nephew else in the picture found a workaround。Whenever a head was cut。

 using his st he allows to characterizeize the wounds and that would prevent new herds from forming。

 So eventually Hercules manages at the hiding。I'm telling you that story because that's the origin of the expression Portuguese Bihu Gi Cabeis。

 or seven headed beast， but not to be confused with a story of the seven headed beast that appears in the last book of the Bible。

 the Book of Revelations。L sorry Bruce。 That's another beast。 Okay。

 so I was always saying the expression figure to refer to hard problems with complex solutions。

 but is' most used in negative form。 No on Bi setskaosis is's not a7 handed beast。

To explain that certain things are not as complicated as they might seem。

 But I guess the most common English expression that conveys the exact same messages it's not rocket science。

 So in this talk， I'm going to show you a problem in the solution I came up with。

 And I hope to convince you that it is the problem。 No， only' wish set Ca。

 It's not a7 had a least is not rocket science。 So thanks for coming to attention to my talk or for what the recording for people on YouTube。

 Let me give the context。 it's Friday afternoon。 People are exhaust has been a lot of fun。

 but quite exhausting。 have people here dad。 So you might hear ignoring。 That's not my fault。

 I promise。 So my name is Caari。 I'm a PhD maththe X former professor University in current I work in finance in London。

 But this work here has nothing to do with my。Job， I'm here in a personal capacity and all opinions I'm going to express on my own。

So this is carry out in my spare time。So let me tell you three cool things about myself。

ALong time ago， I published this paper where I derive these integral partial differential equations。

 not now some mathematicians call it Nes equation。Two years ago。

 I published this paper with my friend of Orange neither。

About calendar algorithms that were inventeding， they were very efficient and now they feature in many important pieces of software。

 and they refer to as the Nish Schneid algorithms。And about 10 years ago。

 I he wrote you the archive this paper where I have the several lines of code very obscure。

 but very efficient to resolve to solve a quite interesting problem in combinators。

 and more recently I was informed that Professor Dono Kinu。

 I'm going to cite that in the art of computer programming and he suggests that he might call it Neris Ha。

So I proudly showed that to my boss。And he says， from equation to Albertber to hack。

 men you are going sold downhill。And I believe it has some hidden message about my bonus。

 but that's not your problem。 That's my problem。 Our problem is the conversion from four point numbers to string。

 and here are four ways of doing that in standard C+ plus and notice that the output is not always the same and one reason for that is there is no one size fits all solution for this problem。

 Sometimes we want more customability or times we want more performance or more reliable results。

 And by the way， the same situation happens in other programming language。

 So talking about performance and more reliable result brings our attention to two charts。

Which is supposed to produce the result to be the first of those functions and produce a reliable result in some sense that I will explain later on。

But what's the deal？So we all know computer store numbers in binary。

And we want to see them in decimal， but we all know how to convert。Binary to decimal， right。

 is's just a bunch of divisions and models operations。 Each step we get one digit。

 And here is the code to do that。It's a textbook code okay it's not the best way to do that they are very sophisticated ways of doing this conversion because this is an interesting and important problem。

 but it's not our problem because here is the whole version from integer to a string and we are concerned with converting float point numbers but isn't that the same should be right well think about this number here float me2 to negative 126 its no phone number。

 it has 126 digit after the dots so how do we calculate this number。

Do I have to run the loop that I just saw 126 times， that sounds very weight， very slow。

Besides nobody wants to see this awful number， we prefer to see something like that at the bottom right moreful size。

 but how do we get that number， should we it's more or less in there。

 not quite so but should we run the loop， calculate the 126 digits and then throw away most of them sounds very wasteful。

 So there are better ways of doing that and that's what this talk is about。

So but before I explain you how the algorithm works， I have to explain how float point numbers work。

 but I always start very slowly with a very simple CPU that is capable of restoring and display just with four digits。

 but the first problem we have is I don't want to see only intervals I also want to see fraction numbers So solution that problem we just stick a dot in between dig。

 but the dot is only conceptual is not there for the CPU。

 the CPU doesn't see it just us okay so we solve a problem very cheaply。

 and then with that storage storage and counting， we can go from 0。01 in steps of 0。

01 up to almost10s。 we solve one problem but almost 100 is not enough it's small range I want to in large range this range I can add extra digits but that has extra costs。

 How can we。Large the range without incurring extra costs。

 One way of doing this is repurposing the first dish and look at it as the exponent in that on the expression and the other。

Jsuits make up the myiss。And again， everything that is great is just conceptual。

 is not installed stored in any shape or form by the CPU。 It's just for us to consume that。

 at the bottom， I'm going to show you the result of the expression。 So now let's start our account。

 we can go on steps of 0。01。 let's accelerate that and make a pause here。

If we keep the semiulog as before， the next step would be what would we increment exponent and reset the mon。

 but that brings us back to zero and we do not want to go back to zero， we want to go forward。

 so we have to introduce a rule here。Whenever the exponent is no zero。

 there might the first digit must be no zero， that's what we call scientificnotation right。

 so let's keep going and now look at the bottom。It's the number getting larger and larger and the gap between two consecutive number increase when the exponent is ined and with that logic。

 we go up to almost 1 billion。Before was almost 100， now almost 10 vehicles， so nice。But。

 I still not happy。I'm not happy there is small scale。 We start with steps of10 to the negative two。

Which is not very grular。 what if I want more precision。 So one way of doing that， I again。

 I don't want to incur extra costs， but I'm happy to trade this large range for something smaller。

 So a very easy way to do that。 it to rescale everything by 10 to the negative three。

 but this is also equivalent to biasing the exponent。And the rule is still works。 So again。

 you'll see if you you know where this is going， let's accelerate， okay。

 we go up to almost 10 million not 10 bigger， but 10 million iss okay。

 And we start in steps of 10 to the negative 5。 So this is basically how F point。



![](img/7fde77efe88ea5fe90557eaddb17b60f_7.png)
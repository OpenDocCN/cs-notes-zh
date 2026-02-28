# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P16：15_模块2 2 1 注释和整数打印.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/51d7091b4424526f842d3105e6954b06_1.png)

🎼う。🎼Yeah。So we're going continue talking about the basic data types。

 but a couple of things I want to hit on are comments and print statements。

 So it's interesting when talking when teaching a class about programming language there are some things that you have to teach it linearly one thing at a time but some things are basic concepts that I have to use very early on so I'm going at a sequence a little bit but these are comments and printing print statements I use all the time。

 I've even used them already， so I need to define those then I'll keep going with the variables。Okay。

 so comments， comments this is pretty straightforward。 These are basically C like comments。

 They look like the same as in C。 single line comments are just a double slash so slashlash everything to the right of the s on the line that's a comment which means it's completely ignored by the compiler it's only text for the programmer to look at to understand to help the understandability of the code which is a useful thing comments are excellent things when used appropriately but you can see here you can just say slash this is a comment and then everything to the right of it。

 which is everything on that line is gonna to be a comment。

 stuff I've highlighted and read there then in the next line I declare variable var x int and I say s another comment and that case the slash everything to the right of the s on that line is comment but the stuff on the left is still valid code。

 So the stuff on the left gets compiled。 The stuff on the right is ignored by the compiler。😊。

Now in addition to these single line comments， you got block comments and those are marked off with the slash star and the star s so slash star begins that star slash ends it everything between thelash star and the star slash is comment。

 So in this case it's just two lines， but I could have any number of lines of code if I wanted to have a lines of text whatever I could have any number of lines of text describing a function or something like that Mark that put that as a block before the function if I wanted to。

😊，So those are comments Now， an additional thing that I've already been using are print statements just because they're so useful printing。

It's done using the format package FMT package， so you have to import the format package。

 import format at the top of your program。Then print F is sort of the first standard print print function you use a format。

 print。It prints a string。So you pass a string as an argument to print F。

 so format that print F quote high， a string is delimited by these double quotes。

 and we'll talk more about strings， but the simpleple way is just double quotes。

Or I can say x x colon equals jo and then format print f high plus x so plus a concatenation operator that concatenates the high and the next string x which is the word jo。

 so that would print out high Joe with phase in between。

Now we also we're going to use format strings。😡，Fort strings are strings that are used for formatting the output to make it look nice。

And basically， all format strings are their' strings double quotes。

 But inside the string use what are called conversion characters。 So in this language there and go。

 use a percent percent and then some other character。 So， for instance， if you look at the example。

 format print F says high and then percent S percent S is a conversion character for a string。

 So what's going to happen is wherever you see the conversion character。

 that character will be substituted by by some variable。 in this case， its percent S。

 that means a string。 So it expects a string。 So if we look at the arguments to print F。

 the first argument is is a string high percent S。 That's a format string。

 The next argument is the x that x is going to be some string that is going to be substituted in for the percent S。

 so。😊，If x is the word Joe， then when I do this print statement， it's going to say hi Joe。

 right because Joe will be substituted in for the percent S。 So this is commonly used。

 these format string are commonly used to make the format look nice when you're printing。

So besides the comments and the printing， let's start talking a little bit about integers and the nature of integers。

So first as a generic int declaration， we've already declared some integers of var x int right now there are different varieties of integers generally。

 for the most part， we're not going to care。 we just say var x int and leave it to the compiler to figure out what type of integer。

 what length of integer to use most of the time， but you can have different lengths of integers and so for instance here。

 you got int 8 int 16 and 32 and 64。And that those numbers are the number of bits that are used to represent the integer in memory。

 so 8 bit integers 16 bit 32 bit to 64 bit， then Uent are unsigned integers and also 8 bit 16 bit 3264 the difference between ints and Uents Uents are unsigned so that means that they can get larger。

Meaning there's a normally an we're using twoth complement arithmetic inside our machine。

 so the most significant bit is the sine bit and an unsigned integer that most significant bit is not used for the signine。

 it's used for magnitude representation。 So the magnitude the absolute value of the unsigned integer can get bigger just because you have that extra bit that would have been used for a signine in ir regularular integer。

 you can use it for magnitude。So the difference between these different lengths of integers is just how big do we need the integer to be so an 8 bit integer。

 let's say that can only represent you know X say it's an 8 bit unsign the sound sign for a second that can represent 0 to 255 because that's the biggest number you can represent with 8 bits。

But a 16 B energy can go from0 like an unsign energy can go from 0 to 64 k。

 which is about 65000 and thereabouts。 So it's much bigger。

 So number the more bits you use the bigger the number of representationation can be the safe is the most common thing to do is just to declare it as an int and leave it to the compiler to figure out。

 But if you happen to know the magnitude of the numbers that you want。

 you can control that by specifying what size energy you want。

Now integers also have a set of operators。Binary operators， I'm shown right here。

 They're also unary operators。 but these are the binary ones。 These。

 you seen these in every language， plus minus tons。

 all the arithmetic shift modo comparison operators， So equal equal is a comparison。

 equality comparison。 exclamation equal。 That's not equal greater than less than so forth。

 They're boolean operators。 So and or and then bitwise operators where it does boolean operations per bit inside inside whatever the integer is。

 So you can see those two。 But these are common to basically to all not all。

 but all standard languages have the same set of operators you can operate on integers with。😊。



![](img/51d7091b4424526f842d3105e6954b06_3.png)
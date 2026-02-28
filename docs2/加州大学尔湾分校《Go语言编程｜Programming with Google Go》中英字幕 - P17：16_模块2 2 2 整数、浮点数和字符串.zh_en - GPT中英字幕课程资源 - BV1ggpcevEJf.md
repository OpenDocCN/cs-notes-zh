# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P17：16_模块2 2 2 整数、浮点数和字符串.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/236fb74ec899af852af4f4517e8d47de_1.png)

🎼う。🎼Yeah。So we talk about integers， now let's talk about type conversions a little bit before we go into the next basic types。

There are cases where you need to convert a number or a value from one type to another type。

And for that， you use a type conversion Now these conversions are not always possible， okay。

 you can't necessarily do those conversions， but when they exist when they can do when you can do them。

 here's how you do them。Let's say。Okay， so let's say for instance。

 youve got some integers of different lengths。 So I've got variable X。 It's a 32 bit integer。

And variable Y it's a 16 bit integer。And I want to say x equals y， I want to assign one to the other。

I went to do some operations with them together。That， as shown， would actually fail。

 reason why I would fail is because。These two integers。

 they' are actually two different types of integers so the compileism is two different types。

 and 32 is a different type than in 16， so it'll throw an arrow when you try to set one to the other。

Because when you assign like that， the， the thing on the left hand side and the right hand side。

 they have to be the same type。And it sees them even though they're both integers。

 the fact they're different length means they're different types and you throws an error。

 So in order to do this， you've got to convert one to the other。 So for instance， you might say。

 let me take that y， which is 16 and convert it to an in 32 and then assign X to that。

 and then that would work。 So the way you do type converts like that is you use this t operation where t is the type。

 the name of the type So if I want to convert y in 16 into an n 32。

 I just use this this built in function in 32 and that will take whatever its argument is and try to convert it into it in 32。

So x equals n 32 y。 That's what it would do。 take y， which is n 16， convertver it to n 32。 Now。

 this is a conversion that is possible。 All it has to do is it sign extends the。The y integer。

 So the y value， you don't want to change y is value is equal to2 right So y is a 16 bit version of2。

 and they want to make it into a 32 bit version。 So what's going to do is take the sine bit and just extend it。

 So if the sine bit is 0， meaning it's a positive value。 It just puts 160 bits and the high bits。

 gives you a 32 B number， which is equivalent。 also a 3 32 B representation of2 says S equal to that。

 So this is the type of conversion is possible。 So it's easy to do。

 So you just use this in 32 function to do it。Note that there are other type of versions that you can't do so easily and it will fail on those。

 but some of them are possible like this one。So another type， besides integers are floating points。

So floating points， they're basically real numbers right now depending on how many bits along the floating point is。

 like say you got float 32， that's going to give you approximately six decimal bit digits of precision okay。

Float 64 is going to give you approximately 15 decimal digits of precision。

 so you figure out how many bits you want to use， how big you want to be based on how much precision you need。

And often it tends to be you want to go longer than shorter。

 right because precision errors are a common problem in floating point arithmetic。

 so you want to use more precision the more precision is probably the better。

 of course there's a space issue right use more memory if you make them longer。

And also performance changes right， but still you know you don't want to precision errors are an issue sometimes。

So you can express floating point numbers with decimals or in scientific notation so we can see two our x is float 64 123。

45 right that's a decimal itll make it a floating point representation also you can represent the same thing scientifically with this E as the exponent right for the 10 So this is base 10。

 so E2 means the 10 to the two。Also， you can represent complex numbers if you want to。

 they have complex。Comflplex numbers， so if you remember complex numbers from high school or wherever you learned it。

 you got the real part in the imaginary part so this is how you create a complex number you use this complex function it creates you give two arguments the first number the real the second number is the imaginary so2 plus3I would be that complex number if you're using complex。

😊，Al right， so first， we're going to talk about strings in order to talk about strings。

 we need to talk about ASI code and Unicode。So strings are going to be sequences of byte。

 we'll see that in the next slide， but each individual element， each a byte in a string。

Stings are made to represent different characters that you see。 Okay。

 so often strings are made for printing。 they don't have to be for printing。

 but they're often made to represent printed things。 So for instance， hello world。

 the string hello world， right， that's something that's meant to be printed and seen by a user。

So now each one of these characters that you want to store in a string。

 each character has to be coded according to a standardized code。

AsI was basically the first accepted one。 American Standard code for information exchange。

 and it's just a character coding。 So each character that you that you want to represent is stored with is represented with a an8 bit code。

So for instance， a capital A right a capital A in ASCI is the number 41 in hexadeadecimal。

 okay I just know that off top of my head is's a common code， but it's 41 in hexadecimal。

 so that's an eight bit code so ASCI is an 8 bit long code which means it can maximum represent 256 possible characters really does 128 because one of the bits is used for something else。

So that's not a lot of characters。 So an 8 bit code is sufficient for English because there aren't that many letters in the alphabet。

 But once you start incorporating other characters that that you need to include。 So， for instance。

 Chinese is a good example because there are a lot of characters in Chinese right you can't use an 8 bit code and hope to represent Chinese。

 So once you start trying to look at all these different character sets in different languages and different characters that maybe even aren't part of languages but things that you want to。

That you want to represent anyway that you want to show and have a appear on the screen。

 you need a lot more than8 bits so that's what Unicode is for Unicode is a character code that is a 32 bit long code。

And so you can represent2 to the 32， which is a lot bigger to gig，2 gig， I think。

 So it's a lot bigger。 So that's a lot of characters。 Now， UTF 8。Is sort of a。

Say a subset of Uniicode。It's a variable length code， so it can be 8 bits。

 but it can go up to 32 bits。And the first the first set of codes in UTFA match ASCI right So all the ASCI code values are the same as the their UTFA8 values。

 So for instance， capital A's in hexademo it a 41 in ASCI it's also a 41 in UTF8 Now UTFA also includes a lot of other codes like for instance。

 Chinese characters right and those aren't in the first in the first 128 right there outside of that They require more bytes you can't just use the 38 bit code to represent those。

 So maybe those are 16 bits or 32 bits。 So UTFA is a variable length code。

 but it can carry it represents a lot more characters and you can represent with ASCI。😊，Now。

 the default。In Go is UTF8。And in UTF8 or Unicode code point is a term for a Unicode character so there can be up to two to the 32 code points right and in go。

 they call a code point a runon So runon is just a term for a code point。

 So the character the capital A character it has a run which is represented with Ox41 right in hex deimbel is a 41 that you call that it's run。

Okay， now to strings， now strings are arbitrary sequences of bytes。Represented in UTFA。

 so each byte is a rune represented as a UTFA code point， so these strings they read only。

You can't modify a string， you can make a new string that is a modified version of the existing string。

 but you can't modify an existing string。Often meant to be printed or displayed to a user。

A string literal is just a string that's notated with double quotes， so for instance。

 if I say x colon equals high there， that's a string literal right and that's a sequence of bytes。

 each one of those bytes， each one of those characters H I， space， T， H， E， R E。

 each one of those is going to be represented as a rune， UTFA code point。

And they're put together and an array of those will cover arrays soon。

 but an array of those is going to be a string。

![](img/236fb74ec899af852af4f4517e8d47de_3.png)
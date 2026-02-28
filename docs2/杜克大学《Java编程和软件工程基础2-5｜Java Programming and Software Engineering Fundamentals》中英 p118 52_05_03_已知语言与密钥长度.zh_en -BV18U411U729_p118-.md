# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p118 52_05_03_已知语言与密钥长度.zh_en -BV18U411U729_p118-

![](img/4762cbcbc69f1ceac2974fd819f84b5a_0.png)

Hi， the first step of your visionre breaker is going to be to write code which only handles the case when you know the key length。

And are working with a single language like English。 Whenever you're developing software。

 it's a great idea to implement one feature first， to test it thoroughly before you build more features into your program。

 And that's exactly what we're going to be doing here。😊。

Remember that the Vigenre cipher acts like several Caesar ciphers for different slices of the message here you see a message which was encrypted with a Vire cipher whose key length is4。



![](img/4762cbcbc69f1ceac2974fd819f84b5a_2.png)

We've colored the letters based on the part of the key that was used。

If you take only the blue letters， you could use the Caesar cipher cracker that you wrote previously to find that part of the key。

 these letters are basically just a message encrypted with a Caesar cipher。

 but they're spread out through the total message then you could do the same thing with the red letters to crack that part of the key。

 and similarly for the green and the purple letters。

 this is the conceptual idea of how to break a visionire， if you know the key length。

You slice the string up and you break each slice using a Caesar cipher。



![](img/4762cbcbc69f1ceac2974fd819f84b5a_4.png)

So what should you write to implement this， the first method you'll want to write is slice string。

 which takes three parameters。The message to slice up。Which slice you want？

And the total number of slices。For example， if you call this method with four total slices and which slice equals zero。

 you would get the blue letters put together into a string。Like this。Similarly。

 which slice equals1 would get the red letters as you see here。

 the new line character counts as a string。And which slice equals two。

 you'll get the green letters in the string。And finally。

 which slice equals 3 would give you the purple letters。 Again， you see the new line character。

We have some advice for you to help you write slice string first。

 remember the stringBuilder class you learned about earlier。

 it will be useful as you build up the resulting string to return。

 you will want to append characters to a string builder object。😡，Second。

 you will likely want to make use of counting for loops in ways that are slightly different than you've seen before。

 you've typically had four loops start at zero， but they can start at any number Here you see an example of count for loop that starts at4。

Of course， you could use a variable or a parameter to indicate where you start counting。

 that will prove quite useful in this method。You can also have counting four loops that count by something other than one。

 this loop counts by7， so it would print the values of 4， 11， 18 and 25。

Of course you can count by a variable or a parameter instead of the constant 7 you see here。

 that may be very useful as you write slice string。



![](img/4762cbcbc69f1ceac2974fd819f84b5a_6.png)

Once you've written slicelic string， you'll want to write the method try key length。

This method finds the visionire key for an encrypted message。

 assuming that the key length is k length， the parameter。

It also takes a parameter for the most common character in the language， this parameter is for later。

 for right now you'll just pass it E。When you write this method。

 you want to make use of slice string that we just discussed。

 and you'll want to use the Caesar crackrackcker class。

 We've provided you with a version of Caesar crackracker that's similar to the one you wrote before。

 but with a few changes。 First， we separated out the code that finds the key。



![](img/4762cbcbc69f1ceac2974fd819f84b5a_8.png)

From the code that decrypts the message， and second。

 we've made a constructor which takes the most common letter in the language that you're working with。

In this part of your program， you'll just pass the most common parameter。

This method should return an inray of length， key length。

Which holds each of the shifts that the Caesar cracker found for each slice of the message。

After you've written Tri Key length， you have one more method to write for this part of your program。

 breakak visionionre。😡，This is the method you'll want to call from Blue J。

 It will set everything up and will call the method try key length。

You'll want to use a file resource object to read in the file that you'll want to decrypt。😡。

File resource has a useful method。As string， which reads the entire file into a string for you。

 Once you've read the entire file， you'll want to call try key length。

Passing the message you just read。The key length， which is given to you at this stage and the letter E。

 which is the most common letter。Try key length will return the key as an array of ins。

 You'll simply pass this to the constructor for Vire cipher。

 and you'll make use of its dot decrypt method to decrypt the encrypted message。 Finally。

 you'll print out the result。voila， you are done。

![](img/4762cbcbc69f1ceac2974fd819f84b5a_10.png)
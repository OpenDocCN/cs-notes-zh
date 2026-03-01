# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P38：38_04_02_隐写术第一部分.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/dfc9c6d1e99d5ae69049706f01c49922_0.png)

Hi， in this lesson， you're going to learn how to use functions to implement what is called steganography。

 hiding data in an image or other digital artifact like an audio file。

 a software program or any file of zeros and ones because stganography is a bit larger of a task than previous problems you have solved。

 It's a great idea to break the code down into functions。

 As you progress through this lesson you'll see some examples where pieces of code are abstracted out into separate functions to simplify the entire solution and to avoid repetition of code。

😊，The idea behind stganography is to take an image like this image of Sprinterusssein Bolt and hide data like another image inside it。

 altering the numerical values of the pixels of Useain boltol to encode the hidden image。

 The key to steganography is to hide the data in such a way that nobody can easily tell you have altered the original image。

This image on the right is the result of hiding a secret message in the first image。

 Can you tell that it has been altered。 If you look really closely。

 you can see some differences in the shading of the background。 However。

 if you were to just look at this second image by itself， There is nothing suspicious。

 It just looks like a picture of Hussein bold。This idea has been around for a long time。

 predating computers， sending an undetected message has been important throughout history。

 One important modern use is to avoid censorship imposed by oppressive governments。

You can hide any digital information in an image you could for example hide a text or HTML file in an image。

 however that would take a bit more math and a deeper understanding of how everything is a number to keep things simple at first you'll work with hiding an image in another image of the same size。

When you are finished with this lesson you'll be able to find hidden meaning in the universe。

 That is we're going to walk you through not only the concepts。

 but also the code to do staginographic hiding， then you will write the code to extract the hidden message from an image For example。

 you could take this picture of a galaxy and extract the message that we hi inside of it。Okay。

 so how do you actually do this， you already know that pixels have red。

 green and blue components which numerically represent the color Is there a big difference between a red value of 240 and a red value of 255。

 they are numerically different， but if you look at them， the two of them are pretty similar。

The fact that you can't easily tell the difference when you change the numerical value slightly is the key to hiding data in an image。

 you can store the hidden data in the least significant digits of the color value and not see much change in the resulting color the least significant digits are like the ones and tens places in a three digit number so you could hide a 15 in 240 by changing 240 to 255。

To do this， you're going to need a bit of math。 don't worry， it's just multiplication。

 division and addition， you just have to put them together the right way。

To understand how to do this math， we're going to start with decimal。

 the base 10 number system you use every day， we'll explain the concepts in base 10。

 then learn about binary， the base 2 number system that the computer uses to store numbers。

All the principles will be the same in base 2 as they are in base 10。

 you will just need to use powers of 2 instead of powers of 10。

To see this idea in the familiar base 10， suppose that the values for the red， green。

 and blue went from 0 to 9999 instead of 0 to 255。 This gives each component of the color four decimal digits。

Now suppose you want to hide this red pixel with the RGB values shown， red equals 8274。

 green equals0 and blue equals 1098 in this blue pixel with RGB values of red equals 3568。

 green equals 5686 and blue equals 7450。We'll put the result here on the right。For the red。

 you want to take the most significant two digits of the pixel you want to hide the data in。

 which is the blue pixel and use them as the most significant two digits of the result。

Then you want to take the most significant two digits of the pixel you want to hide the red pixel and use them as the least significant two digits of the result。

Notice that 3582 is pretty similar to 3568， it will look almost the same。

 but youve changed it slightly so that it stores the secret information in its least significant digits。

Now you do the same thing for green， taking the two most significant digits from this blue pixel and combining them with the most significant two digits from this red pixel。

Again， 5600 is pretty similar to 5686。Now you do the same thing for the blue component。

 combining the most significant digits from the two pixel's blue components。

 the resulting number 7410 is again quite similar to the original 7450。

If you look at the resulting color of this pixel， it's pretty hard to tell the difference between it and the original blue pixel。

 but as you'll see， we've hidden a red pixel inside it。Now that the information is hidden。

 how would you extract the secret？You know that you want the least significant two digits of this pixel's red to be the most significant two digits of the hidden and soon to be extracted at pixels red。

 so we want 82 to be the most significant digits of the R or red value。

But what should the least significant digits be。It doesn't really matter too much。

 so we'll just pick zero。Then you do the same thing for green and the same thing for blue。

If you look at the resulting color， it is this shade of red that shade of red is pretty close to the original color that we wanted to hide。

 even though you don't get the exact color back out， the extracted image will look pretty similar。

So now you know the big idea stganography is hiding data in other data in particular。

 you're going to do this with hiding one image in another Now you understand the basic math that is involved in it。

 taking digits from each number and combining them， however to implement this in code。

 you're going to need to learn a little bit about binary， the base2 number system。

 the computer uses which is why the color values go from 0 to 255。

 instead of the0 to 9999 that we just worked with。
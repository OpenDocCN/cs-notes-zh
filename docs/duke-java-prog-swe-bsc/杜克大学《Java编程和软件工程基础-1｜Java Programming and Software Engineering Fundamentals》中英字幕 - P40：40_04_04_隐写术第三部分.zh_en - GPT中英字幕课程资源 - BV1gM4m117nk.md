# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P40：40_04_04_隐写术第三部分.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/a97b4dd933e9dd1807d4a66c5ad0a415_0.png)

Okay， now you know the big picture of steganography， as well as the basics of binary math。

Now it is time to look into putting all of this together。

Let's suppose you wanted to hide this top image， which has a secret message inside of this bottom image。

 which is a picture of the galaxy。You have already seen how to take the eight bit numbers which represent one of the color components。

 red， green or blue， and hide the most significant bits of one in the other。

 You take the most significant bits from the image you want to show up and combine them with the most significant bits of the image you want to hide。

 You have already seen this math to make this work。

 but there is a bit more to this than just doing math on one pair of numbers。

You need to do this math for each pixel。Iterating through each pixel in an image should be quite familiar by now。

 and you need to do that math for the red， green and blue components。

 Since you need to do the same thing three times， you might think about pulling that computation out into a function。

 allowing you to call the function rather than repeating the code for that task。

Speaking of functions， since this task is a bit more complex。

 you might find it useful to break it down into a couple functions。

 we're going to walk you through a couple functions that we broke our implementation down into for hiding。

First， we made a function called Cho to hidede， which is going to take the image we want to show up in the end and produce one that looks quite similar。

 it is going to do the math on each color component of each pixel that keeps the most significant bits and zeros out the least significant bits。

The algorithm for this function would be to iterate over each pixel in the image and do this math to the red。

 green and blue components you want to divide by 16， take the math dot floor of that result。

 then multiply by 16。You might want to extract this repetitive math out into its own separate function。

 then just call it in each place。The resulting image should look pretty much the same as the original as we show here。

If you were implementing testing and debugging this code。

 breaking it into small pieces like this would be helpful。

 you can check the result of this one piece and make sure it works before moving on。

The second function you might write would operate on the image you want to hide。

 We call this shift because it will shift the most significant bits over into the least significant bit positions that is you would take a color value like 10110010 and convert it into 0001011。

The 1011 has been shifted from the most significant bits to the least significant bits。

The algorithm for this would be to iterate over each pixel and set the red， green。

 and blue to the math thoughtt floor of the original value divided by 16。

If you looked at the resulting image here， it would look plain black。

 That is actually a great thing since all the information is in the least significant bits and the most significant bits are supposed to be all zero。

 Again， you could test this separately before you move on。

The final function called Com takes two images and adds red to red。

 green to green and blue to blue to produce the color values of the resulting image。

It should look basically the same as the original image。

 Once you have the ideas for these three functions。

 your high level algorithm to hide one image in another looks like this。You just call the functions。

That we discussed and they do all the work。Having seen the algorithms for each of these functions。

 you could translate them into code。For example， here is the Cho to hide function。

 You can see here where we decided to pull out the actual math into its own helper function and call it for each of the red。

 green， and blue components。The other functions to hide would be similar， as we discussed。

 you iterate over the pixels of the image and do the math we previously described What about extraction？

How do you get the hidden image back out， We're going to leave that to you。

 You have already seen the math required。 So now you can use the seven steps to develop an algorithm and translate it into code。

 Start out with step 1， and work on an image with two pixels。

 Write down numeric values for their red， green and blue， then extract the hidden two pixel image。

 Once you have done that， work through steps 2，3 and 4 to develop your algorithm。

 Then translate it into code， Test it and debug it。 Happy coding。


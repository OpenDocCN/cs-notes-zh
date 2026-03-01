# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P10：10_02_02_2-霍夫曼编码-时长-20-11-可选休息点-06-53.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

We' are now ready to describe each of one of the blocks that build an image compression algorithm and in particular。

 JPEC。 And as we say， we are going to start with a symbol encoder。

 After we have basically done everything we have done the transform and the quantization that we are going explain in detail。

 we want a further compress。 So quantization will provide us some compression。

 but we want a further compress， but we need to save whatever we have produced here。

We need to save with no error， but we're still going to see how we can compress。

 So why can we achieve that？ The basic idea is very simple。



![](img/4f21fc502b10e185a453c3b4cedd23d0_1.png)

And， of course， you cannot teach image processing without showing at first at least once this famous image that is called Lina。

 that it it used to be used a lot in image processing。 But now because of the band of images。

 many other images。 aus， but I want to show it at least once during this， this nine weeks。

 And we might see the same image again a few more times。 So the basic idea is that some pixels。

 some great values in the image appear more than others。 And let's see that here on the right。

 we have what's called the instogram。

![](img/4f21fc502b10e185a453c3b4cedd23d0_3.png)

The intogram basically counts how many times a particular gray value appears in the image。

 For example， the pixel value， the pixel with gray values。

 let's say around 47 appears this amount of time。 So we go around the image we count how many times I see the number 47。

 and this is the amount of times。 Then I can go and see， for example，200。

 And I see this this amount of time about 700 times appears in the image。

So we see that there are some pixels that appear a lot。 There are some pixels。

 let's say 0 or one don't appear at all。 and the basic idea that we are going to exploit is that we are going to try to give to pixels to pixel values that appear a lot。

 very short codes and to pixel values that don't appear so much。

 we are going to try to give very long codes or longer codes。Let's see how we do that。

 Let's see an example of the use of this。

![](img/4f21fc502b10e185a453c3b4cedd23d0_5.png)

So here we have an image， and this is actually the image that we saw in the previous video。

 the geometric image。 This is a particular image that has there is only four different gray values in that image。

 and they appear。 So they pixel with pixels with gray value 87 appearing one quarter around the image。

 So 25%25% or probability of 0。25。And we also have 1。

28 appearing almost half of the timing the damage， and we also have 1，86 and 255 App very。

 very few times。 Everybody else just doesn't appear in the image at all。

So the standard way to represent this image is we have an array and for every pixel we have a binary code with 8 bits。

 So we are going to basically represent 87 with its binary representation。

 We are going to represent 12 a which is its own binary representation and so on。

 So at the end we are basically spending 8 bits。Pair Pix。If we don't compress。

 But let's assume that somehow I manage to basically construct a code that is shown here in a way that 87 is represented by the binary code 0。

1。1，28 is represented by the binary code 1，1，86 by the binary code 0，0，0 and 2。

55 by the binary code 0，0，1。 That means that， for example。

 if I want if I want to store or send the pixels 87，87，2，55。1，28， instead of writing。All this， then。

This again， for 2，55 days and for 1，28 days， which will take me basically  four times 8，32 Bs。

 I'm going to write it in the following way。 I'm going to say okay，870，1。87， again，0，1。2，55。0，0，1，1。

28，1。 So it basically took me 2，4，7，8 beats instead of 32 to represent the same string。

 the same form of gray values。 Now the decoder。Has this table。

 So the decoder will see 01 will go into that pixel position and we'll put an 87。 We'll see 01。

 will'll put again an 87。 We'll see 0，0，1。 We say， oh， I need to put at to 55 and so on。

 And so we have achieve compression。 Let's see exactly how much compression we can achieve。

 So basically， we do a very simple computation。 We say， okay， we probabilityba0 point。Sorry。

With probability，0。25。I'm gonna have length of 0，1。Out length of， of two。

That's my code 01 with probability with probability 。47。 I'm gonna have length of one。Plus，0。

47 times 1。With probability 025。 So for one quarter of the image， I'm going have length 3。

And with very small probability， I'm also gonna have length 3。And this is equal to 1。60。1。81。Okay。

So instead of 8 Bs per pixel， I'm going to have 1。81 on average of my whole image。

 and basically I have saved a lot of pixels。 okay， I have gone from8 to basically 1。

81 and that's a compression of over four times。 and that's what we have done basically what we did is we exploit the fact that some of the pixel values appear more often than others。

 and then I have to give shorter codes。 I can give shorter codes。

 So how we do that we do that use using something which is called halfman coding and I'm going to explain next how to do it。



![](img/4f21fc502b10e185a453c3b4cedd23d0_7.png)

So let's just look once again and this particular example。

 the best way to explain half one coding is just to use an example， and I'm going to do that next。



![](img/4f21fc502b10e185a453c3b4cedd23d0_9.png)

So let's assume that we have five different symbols，6 different symbols。 sorry， and I order them。

 The first thing I have to do is order them。With according to the probability。

 the highest probability first and the lowest probability at the end。

 And if some probabilities are equal， it doesn't matter which one we put first。 So， for example。

 this symbol a2 might be the pixel value 100。 The symbol X。

 a 6 might be the pixel value 77 and so on。 So I'm going to add basically。

 I'm going list the the symbols here and the probabilitybabilities here。 And from the bottom。

 I start to add。 I take the two lowest。And basically， I add their probabilities。 So I go from 0。

04 plus 0。06， and that's probability 10。1。 And then I do the list again。 So none of this has changed。

 The only one that changes the last one。 See what's happening here。

 What's happening here is with probability 。4。 I can get a2 with probability 。3。

 I can get86 with probability 。1。 I can get a1。With probability point1， I can get symbol a 4。

 and with probability point1， I can get either a 3 or a 5。

 I'm going to have to do something to distinguish which one is it， I it a 3 or a 5。

 And that's going to come in the next slide how we distinguish them。Now we do we do this again。

 We take the two lowest。And then we add them。 And now because it became 0。2， remember。

 we have to reorder all the time。 So let me just describe that again with 0。4， we can get a2 with 0。

3， we can get a6。 Now， with 02， we can get either one of these two， which is a4 a3 or85。

 I don't know which one， but I know that with 0。2 probability is one of them。

 And then we have 01 again。 We do that once more once more。

 actually two more times we add the two lowest。 we get this。

And then we once again add the two lowest and we get this。 And once again。

 we every time we add the two lowest and we move into the next column， we reorder everything。

When we end up with only two， we stop。And we're going to see why we stop。



![](img/4f21fc502b10e185a453c3b4cedd23d0_11.png)

Now it's time to give the code。 So basically， what I have done here， I basically。Re。

Through the graph that we have in the previous slide， and so this is the first column。

 this is the second column and the third column， the fourth column and the fifth column and I'm going to go backwards assigning codes。

So basically， 2。6， I assign0。And to 04， I assign1 before we go backwards。

 let me tell you what's happening When the decoder is going to see a 0。

 it's going to know that it' from the group that LED to this 06。

 When it see a 1 is going to know that is from the group that lets to LED to this 0。4。

 Then we're going to have to keep adding bids to say which one in that group。

And that's why we keep going backwards。 So we basically propagate back the0。And we actually， the 0。

6 came from 0。3 plus 0。3， so we add a 0 and a1。So now， and we， of course， propagate a 04 here。

And basically， assign to this that came to this column without adding any numbers。

 So it keeps propagating without adding any bits。 So now all the symbols that LED to this group。

And we are going to see it was actually only one symbol。We have this code， and all the symbols。

That propagated to this。Probability， will have symbols that start。 We have codes that start from 01。

So now we keep propagating。 We propagate the one to the one， the 0，0 to the 0，0，0，1。

We have to split because this 0。3 probability came from the addition of these two。

 and then we have a 01，0，011。And then we keep going that we propagate the one to the one。

 the0 to the 0， this0，1，0， which has a code 0，1，1， propagates here。

And this actually has to split every time we split because when we were computing it， we were adding。

 So when we are going back， we are splitting， every time we are splitting， we have to add 0 and  one。

And so we keep going， we keep going and we get this result。

 that says that the symbol 0 1 is going to have a code one。The symbol 0，6 is gonna have a code 0，0。

And so on。 So this is the code is a variable length code。

 Not every symbol is represented by a code of the same length。 It actually has a different length。

 And the length depends on the probability。 the higher the probability， the shorter the code。

 And that's very easy to see because the lower probabilities were added， added， added， added。

 And then when we are going back， we have to split， split， split， split。And remember。

 every time we split， we have to add a symbol， and we have to add a bit for that symbol。

 so basically the call becomes longer and longer。Andm。We can actually go and compute once again。

 the average length of this。So to repeat the process， we basically。Order the symbols。

 according to their probability。 That's what we did here。 We start adding low probabilities。

 So we add these two。 We got this。 We reorder， and we keep going。 It's a recursive process。

 So if you know how to go from one column to the next， you know how to go all the way。

 and then we come back。There is a couple of things that are very important to observe here。

The code that you get in this way is what's called prefix free， and that's very， very important。

 look at this column。When you see a1， when the decoder sees at 1。

 it knows that it has to go here to a2。When is this a0。It basically says， okay。

 I have to wait for the next symbol， but there is no code here。

 which is a full prefix of any other code。And that's very important。 Otherwise。

 the decoder won't be able to reconstruct。 Let's give an example of something which is not a prefix called。

 Let's say that the symbol a1 is represented by the code  one。

The symbol a 2 is represented by the code 0， and the symbol a 3。Is represented by the code 0，1。ok。😊。

So when the decoder sees 0，1。Basically， there are two possibilities。Is it a 3。

Let's say P value of 100。Or。Yes。😊，A2， followed by a1， let's say P 0 and pixel 255。

So there is a lot of ambiguity in the reconstruction， we don't know which one it is。

And this is because this code is not what's called prefix free。This guy。Is a subset of this guy。

 That doesn't happen here。 Let me just clear these annotations。None of these code。 So， for example。

 the 0，0， you don't find it anywhere here。So when the decor sees a one。nows what to do。

 It puts the pixel value of a2。When it is a0。He said， oh。

 I have to white because there are many coats that start with zero。If it is a zero another0 next。

 oh I'm done， I basically have86。If let's say it so the the color receives a0 and then a one。Says。

 oh， I have to wait。Because there are numerous codes that start with 01。

But then it receives another one， says， oh I'm done。

 I' have to keep waiting because there is nothing。 There is no ambiguity here。

 And that's very important。 I have one code by construction。 Look。

 have we basically split and split and split and by construction， This is a prefix free code。Now。

 how do we know that this is an optimal code， how do we know that with this set of probabilities？

The process， the procedure， I just explained， achieved the lowest possible the lowest possible length。

 the shortest possible length of a code on average。 So that's a theorem。

 We have to prove we are not going to do that in this class。

 but that's a theorem that that shows the halfman coding basically achieves the shortest possible length。



![](img/4f21fc502b10e185a453c3b4cedd23d0_13.png)

Now， you might wonder what length can halfmanco achieve or any basically encoder of this style？

 So the basic idea is if I give you a set of probabilities。How much can I compress， How much I go。

 And before I construct a halfman code， I want to know。

 is is worth the effort of constructing the code， Will I compress a lot。

 And the the way to do that is basically you compute what's called the entropy and the entropy。

Which is written by age， age is entropy。Is the sum。Overall， the symbols。With a minus here。

 I'm going to explain a second of the probability。Of every symbol。Lock。



![](img/4f21fc502b10e185a453c3b4cedd23d0_15.png)

Base 2 of the probability of every symbol。 So basically sum 0。4。Times log base2 of 0。4 plus。3。

Times log base 2 of 03 and so on。 So this is actually at again a positive number。

 because all probabilities are below one， and therefore。

 the log of the probabilities are negative numbers。 And then with the negative， we get a positive。

And Shanon's fair theorem basically says that we can achieve basically asymptotically。

 we can achieve this code length on average。 So this is basically what's achievable with this type of code like halfman code。

 We basically can compute this number and say， oh， that's going to be my average code length。

 my expected average code length。 and it's actually not so hard to understand where this formula comes from。

We use a similar computation with the previous example here。

 The probability is based on the probability of the symbol appearing。

 and this is actually the length。Of the code that is going be used for that symbol。 So basically。

 what this is saying。Is that the expected length of that code is the log of the probability。

 and why is's only the expected is because you cannot have a code which is 3。2 long。

 you have to send entire bits。 Either you send 3 bits or you send 4 Bs。

 And that's why this is on average under the expectation what you expect to be the code length。

But this basically gives you an idea of what encoders a halfmanco can achieve。

So now that we know how to encode the bits that we are producing。

 we are ready to go into the next blocks of image compression。



![](img/4f21fc502b10e185a453c3b4cedd23d0_17.png)
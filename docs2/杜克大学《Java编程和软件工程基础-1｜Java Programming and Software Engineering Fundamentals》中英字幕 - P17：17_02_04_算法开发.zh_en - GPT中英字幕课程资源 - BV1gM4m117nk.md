# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P17：17_02_04_算法开发.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/eba3d50be6f6bbeea3497377e188a242_0.png)

The green screen problem also called a chromroma key problem because it is keyed to the colorss chromroa or hue。

Like removing the red from eyes in a picture taken with a flash is common in videography。

 as it allows actors to be recorded in a studio and placed in front of a background or made from an image or video taken in another setting。

This algorithm is what let Drew and I talk in outer space， with dinosaurs。

Now we are going to walk through solving this problem as an example of how to approach programming problems in general。

The first thing we need to do before we solve a programming problem is to figure out exactly how to solve that problem ourselves。

You cannot write a program， explain to the computer what it needs to do until you completely understand yourself how to do the task。

In a precise step by step fashion。 In fact， this is often the hardest part of programming。Now。

 trying to do this particular example of the green screen problem would be too difficult because these images have2 million pixels each approximately。

Trying to operate on them by hand would take an impossibly long time。Instead。

 it is a good idea to work on a smaller instance of the problem by hand to gain a deep understanding of how to solve the problem。

In this case， we're going to look at a two pixel by two pixel image。



![](img/eba3d50be6f6bbeea3497377e188a242_2.png)

We will start by picking a two by two image to be the foreground， the image that will go on top。

And we'll pick a two by two image to be the background。



![](img/eba3d50be6f6bbeea3497377e188a242_4.png)

Also， we will need an image told the final result or output。 This should also be two by2。

Now that the examples are chosen， let's go through and figure out what color to make each pixel of the output image。

Great， now we have solved an instance of the problem by hand。

 The next step is to write down exactly what we did in a step by step fashion。



![](img/eba3d50be6f6bbeea3497377e188a242_6.png)

I started with the foreground image， I wanted， I'll call this FG image。



![](img/eba3d50be6f6bbeea3497377e188a242_8.png)

And with the background image， I'll call it B， G image。 I then made a blank image of the same size。

 I'll call it output。I looked at the first pixel in F G image， and it was red。

 So I set the outputs corresponding pixel to be red as well。

 I looked at the second pixel in F G image。 It was green。

 So I looked at the same position in B G image and set outputs corresponding pixel to B G image pixel。

I looked at the third pixel in FG image。 It was green。

 so I looked at the corresponding pixel in B G image。It's blue。

 So I set the output to be that same color。I then looked at the fourth pixel in FG image and it's blue。

 So I set the corresponding pixel to be blue in the output。Great。

 now we have a step by step set of instructions to describe exactly how we solved the problem for this particular pair of images。

 But to write a program， we want to be able to solve this problem for any image of any size。😊，Now。

 if you look at these steps closely， you will see that there is a lot of similarity We're doing almost。

 but not quite the same thing for each pixel in the image。When the FG imageages P is green。

 we use the BG imageage P， and when the FG imageages P is not green。

 we use the FG image pixel directly。Going back to our step by step instructions。

 we will rewrite each step to be a little bit more general。

 taking into account this conditional behavior we just observed。

You can do this for each pixel's step， and now each step is more general and more similar。

 they would work for any two by two images， but only for two by two images。

Here we have improved the step by step instructions to express the repetition over each pixel。Now。

 the steps are general enough to work on any sized image。 In fact。

 what we have done is devise an algorithm that we want to that we're going to implement an algorithm is a clear step by step set of instructions to solve any instance of the problem you want to solve。

 You can express an algorithm in English， as we have done here， or in code。

 as we'll need to do to let the computer run it。Everyone makes mistakes When devising an algorithm。

 there are many different ways to make mistakes。 For example。

 you may not have seen the pattern correctly， or you may not generalize each step correctly。

 to try to protect against these types of mistakes。

 let's try our algorithm out on a different example to see if it works as expected。 If it does。

 we'll be more confident that we did it right。 If not。

 we've caught our mistakes early before we went to write code。 Of course， once we write code。

 we will want to test it more thoroughly。 but we'll talk about that later。

As you walk through your algorithm， you will want to keep track of what step you're on For us。

 we're going to draw a green arrow to show where we are in the algorithm。

You then want to go through each step exactly as it is written。

Here I've picked the three by one image to be the foreground。

 and this three by one image to be the background and a three by one image to be the output。

Here I will keep track of which pixel is the current pixel with a blue arrow in the drawing above。

This first pixel is green， so the algorithm says to look at the same pixel in the background image。

 which is yellow。And make the same pixel in the output image， also yellow。

Those are all the steps for that pixel。 So now the algorithm says to go to the next one and repeat the process。

We will continue to follow these steps。As they are written。Exactly as they are written。

Until we finish all of them。At this point， we want to see if the image came out as expected。

In this case， the output was right， since our algorithm appears to work， it's time to write the code。


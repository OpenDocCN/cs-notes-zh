# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p105 21_VR对象选择与操作第二部分.zh_en -BV1jM4m1k73q_p105-

![](img/80104523c87c75bd017ffc3a907a0ec2_0.png)

![](img/80104523c87c75bd017ffc3a907a0ec2_1.png)

So object manipulation is really about modifying objects in the world and so we have a number of options here。

 So super handss， as I just said， implements four of them。 So hover， grab， rotate and stretch。

 So in other words， changing the object's appearance is something that you could do on hover and then change the object position。

 obviously as we grab the object。 you want to drag it and you want to move it around rotation。

 you allow the user to change the orientation of the object and this can be done with one hand。

 or in many applications is actually done with two hands or two controllers。And stretching。

 So the same idea。 in this case， we definitely need two controllers in the super hands case。

 I'm going to show you this。 right here I have an example。Of。Super hands， so。This is an example of。

Far manipulation， so I'm using a laser pointer to go and grab。

 I'm now gripping the object and then I release it so I can lift it and release it again on this platform。

And I can also throw it。And this would be an example of farm manipulation。Okay。

 now let's look at near manipulation。So here I have an example of near manipulation。

 so I'm too far away from the cube pointing it it doesn't do anything。

 so no ray casting no laser controls and so me trying to interact with the object doesn't do anything but then I have teleport so I can teleport over to the object and now you can see as I reach into the object it actually detects this。

And one can do it with either hand。And so this is essentially hovering the object。

 It's collision detection。 And so on now I'm inside the object， and now I'm outside the object。

So I'm entering the object and now I'm going to use the grip to actually lift it so I can lift the object。

 and this is grabbing it。 So reaching in there， grabbing。



![](img/80104523c87c75bd017ffc3a907a0ec2_3.png)

And then I can lift the object。 So with a second controller， also entering。



![](img/80104523c87c75bd017ffc3a907a0ec2_5.png)

I can not only grab and lift。But also stretch。 So here I'm gonna move these controllers together or further away and。

Can just use one hand to lift it or rotate it。 So one hand rotation。Two hand stretching。

And adjusting the size of the object。 And then I can just release it and it reacts to physics。

 and I can also grab it again。And。Do the favorite thing that I always like to do and throw it away。

So that was far and near manipulation using a virtual reality controller。

 What if we want to use our hands， So let's look at hand manipulation。

So this is a demo where I have lots of。Cubes on a virtual table in front of me。

And I have hand tracking。 And so I'm going to show you， this is really like my。My physical hand。

And it's tracked in real time， and I have a hand menu associated with it。

And so this uses essentially an Ochis quest hand tracking。

 And the way I trigger this menu is with a pinch gesture。

When the menu is visible and that's how I've implemented it prototypically。

 and then we have physics enabled， oops， sometimes some funny things happen。



![](img/80104523c87c75bd017ffc3a907a0ec2_7.png)

And you can like grab these things。And。Basically， physics works with both hands。

And can insert new objects。😔，And can like play around。 I mean， you could theoretically， let's say。

 plan a little bit。 The scenario could be like planning。Ciity I how does something with cubes。

 I don't know already what the diary would be。

![](img/80104523c87c75bd017ffc3a907a0ec2_9.png)

So hand manipulation is really one of the latest things you can do in virtual reality。

 It's only available right now on the Archlist quest， at least at the time I was recording。

 this was very experimental， just came out a few weeks ago and just had to implement it and show it to you。

 I think it's pretty cool。 I do think that it will this is based on Webex are。

 so it's going have an impact on how we interact in the future with Web content at least it's what I strongly believe in it what I also focused on a lot of my research some of it was in collaboration with Mozilla when there were still focused on WebEx are。

 It's been a tough week last week where there were a number of layoffs in Mozilla。

And Webex R is not the main focus anymore。 So let's see where that is going。

 but I'm going to show you two more examples。 So here next I'm going to show you manipulation in tiltilbr。

😊，So this is tiltbrush。 I have the menu。 I'm using the left controller。

 already to manipulate this object， this menu attached to the left controller。

 And then I was just picking。A color and Im sketching in mid air。

 and that is a form of manipulation because we are spawning actually new 3D content。

And the way this is done is in a very performant way。

These are not little spheres that are placed in there。

 which might be the first thing that you might be implementing when you want to do your own sketch tool or some kind of lines that you're adding to the scene no that is really manipulating the mesh and that is a more advanced way of implementing this and tiltilbrush is really quite advanced because all this stuff is glowing and being animated so it's one of the most amazing sketching tools when you look at it it's not particularly useful for a lot of the activities that I need to do like planning a VRC and there are better tools for that but there are some really impressive artists out there who use tiltilbrush in a really cool way So so that was a form of manipulation。

 a lot of things coming together obviously selection and manipulation in tiltilbrush let's come back to half life Alex so I have a last example here for you one of the things that I really liked is a whiteboard that it's early on in the game。



![](img/80104523c87c75bd017ffc3a907a0ec2_11.png)

If you play it， it's really quite well done and there have been cases where actually teachers have used this in class as a gameful learning way right。

😊，Now we can sketch。This is Hlife Alex is one of my favorite scenes is right in the beginning。

And we could grab a pen and leg。Sketch out the plan here。And so this is kind of like。

 if you want storyboarding in VR。So this could be my two frames or something oops。

And then you have an eraser here， so make sure that。

This might have been important information from the previous person。

But let's just like leave it there for now。And sketching something cool in yellow。

 and you don't even have to press anything。 I mean。

 because the idea is that you are in virtual reality。And when I picked up this pen。

And control and Phops and just dropping everything。I mean。

 you have to use the controllers to hold things， but otherwise it's definitely。

That pen just it's definitely one of the better sketching interfaces that I have seen you have to obs release and there we go。

And。Could also try to， you know。F tune and some of the things here。

So this was my lecture on object selection and manipulation。 It was very example based。

 we didn't go too deep on the coding part。 That's what we're going to do in the honest track。

 So check that out if you're interested really in how to do these things in more detail。

 I have lots of examples， lots of code to share and so let's look at this together so but we have the basics。

 And if you just want to zoom through and go to the next stage this is more or less the VR portions for us。

 we're going to learn more about AR in the next module。

 but really there's a lot more content in the honest track。 So I would invite you to check it out。😊。



![](img/80104523c87c75bd017ffc3a907a0ec2_13.png)

![](img/80104523c87c75bd017ffc3a907a0ec2_14.png)
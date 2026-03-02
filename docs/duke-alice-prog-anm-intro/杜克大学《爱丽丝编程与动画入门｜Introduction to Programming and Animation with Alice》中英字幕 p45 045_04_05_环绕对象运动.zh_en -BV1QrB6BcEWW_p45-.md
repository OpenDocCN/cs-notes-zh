# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p45 045_04_05_环绕对象运动.zh_en -BV1QrB6BcEWW_p45-

![](img/944fcf049ec0611a0a66ac5f8544225b_0.png)

In this lesson， we explore how one object can circle around another object。

We will start with a world that has a flamingo and an ostrich to its left。

Both birds are facing the camera。 We would like the ostrich to circle around the flamingo。

We will explore how to use the turn instruction to do this。

We already have a few instructions in the world。 The flamingo says， let's explore turning。

Then we have the ostrich turn to its right， one revolution， and then turn to its left。

 one revolution。Let's play the world。We'll see the turn instruction makes the ostrich turn in place。

 either to the right or to the left。We already knew that。

How do we get the ostrich to circle around the flamingo？

We could have it move forward a little and then turn a little and repeat that a lot。

 but that would make a really jagged circle and would be a pain to implement。

It would be nicer to move the ostrich in a smooth circle around the flamingo。

We can try to have the ostrich turn and move forward at the same time。As the ostrich moves forward。

 the turn at the same time makes it continuously turning a little bit。

And it will move in a circular direction。Let's add in a comment。We'll say turning with do together。

Let's add in。A do together。And put in an ostrich。 Let's select ostrich。Turn right。Wen。Why right。

 Because as the ostrich moves around the flamingo， the flamingo will always be to the ostrich's right。

Let's add an ostrich move forward，5 into the do together。So I'll select forward。😔，And。

I'll have to type in the five。5 is the total distance for the ostris to travel。

Let's give both of these a duration of two。Just so it will take a little longer for the。

Ostrich to circle。And let's play the world。After the ostrich turns in place。

 the ostrich will make a complete circle because we told it to turn one complete revolution。

And it moves exactly five units。 That means the circle the ostrich made has a circumference of five。

Their circumference is a distance moved to trace the circle。Now， that circle was really small。

 and the ostrich did not circle around the flamingo。We need the ostrich to move further。

Let's copy the do together。And we'll have the ostrich move further。We copy it to the clipboard。

And then， drag it over。Willll add a comment right above it。That says。Turning in a larger circle。

Then we just need to change the five in the move forward to 12。We'll have to type the 12。

Let's play that。The ostrich turns in place。And then does the little circle。

 and then it does a bigger circle。Now the ostrich moves in a circumfers of 12 and we got lucky it just barely went around the flamingo。

 that's not quite what we want。We want the ostrich to circle the flamingo in a circle whose radius is the distance between the ostrich and the flamingo。

We need to use the distance2 function。We also need to know how far that circumference is。

The formula for the circumference of a circle is2 times pi times the radius of a circle。

Pi is a constant for 3。141592， but we will just shorten that to 3。14。

This formula for the circumference of a circle is the distance the ostrich needs to travel。

Let's add a comment。We'll say turn with math。To get the circumference of the circle。

Let's copy the do together。The last one。We' copy to the clipboard and drag it down。

The only thing we need to change is the distance in the move forward instruction。

To two times pi times the radius。So first， let's change the 12。To a2。

And then click on the down arrow beside the two。And select。Math。Times， so it's two times。

And we want to pick。3。14。We need to use math one more time to multiply times and pick any number。

So the 3。14， the down arrow beside that will pick math。Times， and will'll just pick any number。

 I'm just gonna pick one。Now， remember， to use a function that calculates a number。

 we need a number first as a placeholder， and then we can replace the number with our function。

Now that we have the one， let's find the distance to function， so click on functions。

And if you scroll down。You'll see ostrich get distance to other。

Drag that over and put it over the one。And select the flamingo。

So now the forward direction is 2 times 3。14 times the ostrich gi distance to the flamingo。Now。

 we'll play the world。The ostrich now turns with five， and he turns with 12。

 and now he turns with the exact distance between the ostrich and the flamingo。 That looked great。

Alice has a way to make this easier for you。 There is an as seen by option with the turn instruction。

Let's add a new comment。We'll say turning with as seen by。Thenen。We want to add an ostrich。

In turn instruction， so click on Pro。And turn。We want the ostrich to turn right。Wan。

And then let's add detail and make that duration too。So it takes two seconds。

Then click on add detail again。And this time。Add， as seen by。The Famingo。Let's play the world now。

The ostrich turns with five and then 12， and then the circumference。 and now here comes the Eene by。

It looks exactly the same。That was only one instruction and certainly a lot easier。

So note that we had the ostrich turn right around the flamingo and as seen by the flamingo。

And it was right since the flamingo would be to the ostrichs right as it turns around it。

Let's see what happens if we turn left instead of right。So， copy the instruction。And then。

 change the right。To the left。 So the first time with Es seen by。

 the ostrich will turn right and the second time with E seen by， the ostrich will turn left。

Let's play the world。

![](img/944fcf049ec0611a0a66ac5f8544225b_2.png)

The ostrich turns a circle of five， a circle of 12， and a circle of circumference。

 and now here's the ascene by right and here's the asne by left。Using left instead of right。

 the ostrich turned the opposite way， it went backwards around the circle。

That wraps up exploring turning with do Together and with a scene by。


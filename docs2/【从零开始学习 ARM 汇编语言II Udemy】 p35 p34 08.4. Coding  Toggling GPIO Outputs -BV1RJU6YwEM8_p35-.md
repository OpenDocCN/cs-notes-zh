# 【从零开始学习 ARM 汇编语言II Udemy】 p35 p34 08.4. Coding  Toggling GPIO Outputs -BV1RJU6YwEM8_p35-

Hello welcome back。 So in the last lesson we saw how to develop our GPIU driver。

 we created a GPIU as an output and then were able to turn on the LED。

 Now let's see how to make the LED print blank， I should say。

I am going to create a copy of the last project and rename this。And then we just continue from there。

I'm gonna open it。

![](img/9c6745cdace8cbd3640b44745559b80a_1.png)

Right， it opened。 So we are going to create a delay function to help us do this。

And I should mention this delay that we're going to create is not precise Later on。

 when we get to the section on time as we're going to see how to create precise delays。 But for now。

 I'm going to create delays。 going to create ource pseudo delays。Actually。

I shouldn't say it's not precise。 this delay is precise。

 but it is calibrated for my particular configurations and what I mean by this is it is calibrated for my MCU running at 60 meHs and using the Car U visionion compiler so。

Let's see what I mean。 I'm going to create a symbolic name for one second。 I'll call this one sec。

E Q U。 and I'm going to assign this constant。 So I'm going to pass this to a register。

 and we're going to keep minus in one from this， taking one from this。 And by the time it reaches 0。

1 second would have passed。And then I'm going to create another symbolic name， this is half a second。

And I'm going to use this。I'm going to use half of this value here， which is this。Right。

So then we can go ahead to create our delay。I'll come down here to create a new subroutine calledor delay。

ICom here。And then I'll delay。😔，And太始。This subroutine shall take the content of Reg R3。

 so we are going to pass a delay amount our argument is going to be placed in R3。

So come here and see sub S。R 3。R 3 and then -1， meaning subtract what is in R 3。

Subtract1 from the content of R 3 and put a result back into R 3。

 And then I place the S over here because I want to update the APSR flags。

 When I perform this operation， the subtract operation。

 And the reason I want to update the flags is that I want to be able to check what any of the flags are set。

 the APSR flags for those of you who took the the fundamental cost。

 the arm assembly program from ground up。 We spoke about those flags。 We have the zero flag。

 the curry flag， the overflow flag。So the zero flag is set when the previous instruction or the previous operation。

Return a result of 0。 So that flag is going to be set。Right， so I'm gonna say B and E。

I'm gonna to say B N E。Delay。And this basically means branch if the Z flag is not equal to 0。

Meaning if theziif flag is set， if the result here。If the result here is is 0。

 if we keep subtracting from R 3， if we keep subtracting one from this number and we end at 0。

 the Z flag is going to be set。So we check if the zf like is said。If it's not set。

 then let's keep subtracting。 If it's not set， we keep subtracting。

 That is why we seem branch If the sea flag is no set， meaningan we've not arrived at 0 yet。

And then I'm going to return from the subroutin by doing Bx。LLa like this。Right。

 so I'm going to write a new subbri known as LED blink。

 and then I'm going test out the delay function there。So we start off by accessing our data register。

I'm going to access the data Reg like we did before。

So we have the data register now we've accessed it。We read， we put in ourciro。Nin。We turn the LED on。

This is what we do。We did this already。 This is our LED on。 Once the LED is on。

 we're going to load one second。 I'm going to do load R 3。With the constant one second。

And once we floated R 3， we're going to branch to our delays of routine。

And then were going to turn theity off。I'll just copy this。

And I'm going to create a symbolic name for turning the LED off。I'm gonna have red off here。

Red is bits number one。So red， so red off， I'm gonna do。Redol。Equals。Shift 0 to position 1。Like this。

 I'm going to take this red off。Put it here。 So we're going to turn red off and we're going to delay。

Again， so I'll start by loading R3。Which one second again。And then B。Then we。

 we go to our delay sub routineoutine。😔，And then。This is it。 We can。

We can keep branch to the top so that we create a loop here。LED blank。Over here like this。😔。

So now we can try this out， I'm going to copy this label。And come over here。😔。

And because we already have LED blank as a loop， we can take out this loop。Okay。

 we can test out our code and see what we have。I'm going to click here， to build。Have an arrow here。

😔，It says one sec， not defined。😔，Okay， there's a type of here。Okay， let's build it again。😔。

It's built successfully。I'm gonna click here to download on。

I'm going to download onto my board by clicking here。It's downloaded。 as you can see。

 the LED is blinking。At a rate of one second。Right， this order is for this lesson。 Like I said。

 this delay is not perfectly precise is， is sort of calibrated。 is too。



![](img/9c6745cdace8cbd3640b44745559b80a_3.png)

You can just take it as a pseudo delay。 but this is how we are going to make our LED plan。

 When we get to the timer section， were going to see how to create delays using cyst timers as well as general papers timers。

 But for now， this all there is。 If you have any questions。

 just let me know and I'll see later have it。
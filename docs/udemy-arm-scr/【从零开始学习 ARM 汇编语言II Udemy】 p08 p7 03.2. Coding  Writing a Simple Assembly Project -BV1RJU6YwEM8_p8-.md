# 【从零开始学习 ARM 汇编语言II Udemy】 p08 p7 03.2. Coding  Writing a Simple Assembly Project -BV1RJU6YwEM8_p8-

Hello， welcome back in this lesson we' are going to demonstrate how to write assembly code using the cube IDE。

I'm going to create a new project from over here， new STM32 project。

And my board selector is going to load up。So here we go。

 so I should point out if you load if the project selector or the target selector loads up and it doesn't show this panel over here。

 simply click cancel and start the project creation project and start the project creation process again。

嗯。Because sometimes when you try to create the project and it tries to load the arm。



![](img/34981b8b60c54e6fe170ea48cc2a192e_1.png)

![](img/34981b8b60c54e6fe170ea48cc2a192e_2.png)

The target selector。 It doesn't load everything。 It doesn't load the part that allows you to search for your board。

 if you experience that。Click console。 There is council down here。There is council here。

 If you experience that， just click console over here and start again。Yeah。

 I think cube ID E still has a number of bugs that， you know。

 updated versions would would sort of get rid of。 Yeah， look at what I'm having here。

 So the the panel disappeared just what I was talking about。So in this case。

 what I'll do is simply cancel and then just start again。

 I'll click console over here and then I'll start again。Newu。😔，Look at this。Oh goodness。Okay。

 STM32 cube。STM 32 project， not Q project。So it's going to load up the target selector again and this time I hope you will load it up properly。



![](img/34981b8b60c54e6fe170ea48cc2a192e_4.png)

So I'm going search my board again。 do pardon the the resolution here。 It's from the cube I D E。

 It's not from my side。 STM32。 My board is SDM 32 F411。 Just search your board here。

 and this is the same screen we find on K M X。 So there is nothing strange。 Just search your board。



![](img/34981b8b60c54e6fe170ea48cc2a192e_6.png)

Your microcontroller， if you are using a different microcontroller and then go ahead and select it。

So once your body is selected， you just click next。And then you give your project a name。

I'll call this simple assembly。I'll keep everything the same， or' click next。

 and I'll click finish over here。And it's going to create the project。 it says this。

This kind of project is associated with Kerex。 Do you want to open this perspective now， I'll say no。

 I think it would open it regardless。Right， so the setup is complete， and we have this here。

 I'm going to close this。 We don't need us。 We write in assembly code。

And then this is our project we come to call。 Our source file is here in the source folder。

And then our source， we don't need all of this。We don't even need main。 C。

 I'm simply going to delete the main dot C right click。Click delete over here like this and then O。

We don't need rest， but we can keep them there。 I'm going to create a main dot S file right click。

Newu。😔，Fal。😔，I'll give this a name， Ma dots best。Right， and this is our main S。

 So we write our assembly code in here。Okay， so to write assembly code， we start with the directives。

 the directives are not， they are not instructions。

They they tell the compiler how to compile the code， so in assembly language。

 you could have two different compilers of the same instruction set。

 the difference they would have is in their directives。

What that means is that the code we're going to write here should run exactly the same way on the arm arm compiler or the arm asmbler。

 I should say asemr no compiler because the as code is assembled， it's not compiled。

So the arm asmbler will run this just that the directives would have to change so over here we're using the Gcc asmbler and we start off by using the section direction to say this as a code section。

 we just say a dot section and then we see a dot text。To say this would hold a code and then。We can。

Use the CPU to indicate what CPU we are using， were using the E cortex M4 it to another directive。

That is the CPU we are using， and then we can use the dot Global。

And here global without an A dot GBL and then we say main to make this， this subroutine main。

 this label main to make it accessible from a file outside of this one。

 So I'll say main and then I'll come over here and then I'll create main， So main is a label。

 a create main like this。And then we start off by moving。We're going to say move into register R5。

0 x。Z x0 x64， and I think this is the number100。This is just for testing to show that we can write assembly code here。

 And then we're going say move into。Register r4。We're going to move let say a number。The number0。

 How about that？And then once that is done， we're going to create another label here we call loop so that we can jump to this label and over here。

Were going to say。How about we。We say a。Add the content of R 5， add1。

 at the number one to the content of register R5。And then store the result in RF5。

 We do that by writing this。We take this opera， we add it to this， and then this the destination。

So the content of this register add this to it and then store it here。Right。

 and then we say our for how about add。The content of register R4。I'd want to it。

I'm writing it in this way to let you understand， so first we take the content of r 4， we add one。

 and then we store the results back into R 4。Right。So we call in this loop。And then let's see。

 what else can we add to this experiment？Think we can simply test this out because this is simple assembly just to test that。

 we can create and run assembly code。 So we're going to end。

 but we're going to branch to this label here。 This label is not accessible yet。

 So were going to make sure when we execute this instruction we execute this next one。

 and then we would execute a third one that would bring us to this label。

 So we use the B instruction， which means branch。 and then we pass the name of the label like this。

 and we use the end directive here to indicate this is the end of our assembly assembly program。

 So control S to save。And then yeah， we can build and see what we have。Click over here to build。

It's built in。It's builted in。We have three errors。Lexi。I'm going to open this up， what does it say？

😔，Immediate expression requires， okay， yet I forgot to put this here。Okay， if you are using a number。

 you have to put the number sign， Huush sign like this。So that is one of our arrow。

I'll click toBuild and see whether this is what created the other  errorss build。Okay。

 it's looking good so far。And it's built successfully， no warning。 Okay。

 so now let's go to our debug field to check our registers whether indeed we get these values stored。

In the registers， I'll click over here debug。STM 32。I'll say okay。I'll click OK over here。

It's opening。And it's finished opening。 So we have different views here。

 We have the live expressions。 We have breakpoint。 We have modules。 We have registers。

 If you don't have any of these views here， you can come to window。

 show view and then too any of them on。 So if you didn't have the register's view。

 you can simply click to have it。So click on Regs view。And oh exponus。

And this will give us a view of our general purpose registers。 So this is r 0。

 This is the value of r 0 now。 This is R 1， R 2， R 3， R 4， R 5。

And then the other registers are down there， cause we have we have。We have floating point registers。

 That's why we see the theses。 But we're looking at just the R registers。

 the general purpose registers。 So we use this to execute our instructions line by line。

 This means step into。 This means step over。 This means step return。

 We're going to use the step into。And whenever you see thisarrowru pointing to a line。

 it means this is the next instruction to execute。This is what is going to be executed next。

 So I'm going click on the step into。And it's executed this。 What did this do。

 Did this moved 0 x 64 to register R 5。 Let's see what R 5 has this。 And as you can see。

 R 5 has the number 100。100 in hexodademal form is 0 x 6，4。 The next says。

 the next instruction says move the number 0 to register r 4。

 So let's run this and see whether r 4 will be 0。 Well r4 is currently 0。

 So there'll be no difference， but let's run it regardless。 or click over here。 step in 2。Okay。

 so nothing has changed， we know that。The next instruction says branch to the label loop。

 so if we execute this， we want to jump to this place， branch to this place。

I'll click to execute this。Okay， and now we are here。

 so the next instruction says go to the content of register R 5。AndAdd one。

To it content install store the result back into R5。

 So currently our register R 5 has the number 100 after this instruction。

 we expected to have the number 101 because we are performing 100 plus 1。So click over here。

 step into。😔，And as you can see， our 5 has 101。Right， so next it says go to register R 4。

 take it content， add one to it， do r 4 plus1 and then install the results back into r 4。

I'll click here。To step in two。And we just executed。And then as you can see。

 our 4 has1 and that's the end of our program。So this shows that we can run our assembly code。

With cubebe IDE and that is how we create an assembly project， you simply create your project。

 you delete the main dot S file。The main dot C file creates a main dot S file。

 and it's important that we call this。Whereas it's important we call this main do we call this label main。

Because in the in the system reset handler， it looks for this。

This subrout called mean as its starting point。 So if we give it a different name， it wouldn't work。

 So let's say I give it a different name。 mean 5， for instance， let's say。

The starting label is called mean 5 and I'm making this。Accessible， if you use the global。

 it means you want to make it global so that other files can access it。 So let's say this is it。

 And I click here to build。Okay， what does it say， we have two  errorss。What does it say over here？😔。

Return exit status。 So basically what is happening is our code has no starting point。

So that is why we using the Webmin if we had a main dot C file。

 then we can give our label here any name because the starting point of the program will be in the main dot C。

 but because we do not have main dot C， we use this controlr S or build and then the errors should disappear now。

As you can see， we no longer have any  errors。Right。

 so this all is if you finding in the course useful， just， you know。Leave it the in the review area。

Okay， I just can't help it before you go， I would w to show you why main is the is the word that we need to use to make a work。

 Okay， so we need to go to our system dot S file and take a look at the。

A routine known as the reset handler。 And this is the first portion that is executed whenever your board starts up。

 Okay， after the boot sequence， of course。We come to over this folder here set and then there is this file and dots S file it's called this long name startup underscore STTM32 F4。

And then dot S， I'll double click to open this。And what we're looking for is the reset handler。

So this is the resett handler， right？ This is how it starts。 It loads this to SP mean stock points。

 you need not know that but important thing after it's executed。

 it branches to this other label known as loop copy data in it。

 So let's go to loop copy data in it and see This is loop copy data in it。

 So this is still part of the reset handle the reset handler comes here。

 and then this execute these lines 1 by one。 and this finally branches to loop The 0 Bs。

 So this is our destination。 So let's also branch there。

 let's find this routine loop field0 Bss when we take a look at it。 we see what happens。

 it executes this execute this this and then it branches to system in it to initialize the system。

 and then finally it does B main， it branches to the application's entry point。

So this is why we have to make sure we have the main existing in our application because its going to branch to a label known as main。

 if we have main not C， that label will be created。If we have just assembly language。

 we have to make sure our assembly language has a main in there so that we can branch。

So let me show you something， let's say I change this main here to main 2。Now。

 let's build our assembly language programming C， I'll click over here to build。

And we have two arrows， right， cause we have main two over here。 What does I say。

Undefined reference to main 2。受。We have men two over here。😔。

And then let's go to our assembly dot S over here， and then I'm going to change this to main2 and then this to main2 control S to save and then click over here to build。

And as you can see， because I change it to main 2， now we can use it to main 2。

 We can use main 2 here。So if you want to use a different name。

 you would have to change it from the reset handler。 but yeah， we don't want to do that。

 Now you understand why we use main if you don't， of course。

 you can leave it in the questions and answers area。 Okay， so I'm going to leave this。

 I'm going to change it back to main。 So you can even use the word start or your name。

 but the reset handler has to branch to that label。 Okay， so that's all there is。

 And have a nice day， my friends。

![](img/34981b8b60c54e6fe170ea48cc2a192e_8.png)
# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p171 51_05_07_Eclipse环境下的HelloWorld.zh_en -BV18U411U729_p171-

![](img/1a2a2328b745ddbadead5f3fdf079124_0.png)

Hi。I'm going to go through the process of writing hellello around the world。

 the first Java program we did in which we use the Eduu。

du classes to read a text file or a URL and say hellello world in many languages。

 something like Bgerur Mond。Which is a language I speak a little tiny bit of and then other languages as well。

 You've already seen a walkthrough in a previous lesson of the code here。

 I'm going to show you what happens in eclipse to show a little more deeply how this code works。

 And also， again， to show you the power of eclipse。

 I've taken the code that was part of that previous lesson。

 This is the the function that opens a file。 In this case， the file is hellello Uniode dot text。

Makes a buffered reader from that。File， and then loop through the buffered reader input to print out Hello world。

Eclipse is telling me with these red X's that something's missing。

 It says import path because eclipse doesn't know that path is a class。

 but Eclipse does know that it's in that。Package， so it's imported Javava。 No do file do path。

 I still have a redx because it doesn't know about paths。 So I'm going to say。

 please import that as well。 Now， I've imported two different classes。

 Bed reader is something that Eclipse doesn't know about。 Let's import buffered reader。



![](img/1a2a2328b745ddbadead5f3fdf079124_2.png)

![](img/1a2a2328b745ddbadead5f3fdf079124_3.png)

And it doesn't know about files， so I'm going to input files。And Bed Reader， if I come up here。

 I'll say I've got buffered Reader files， path and paths。One more right click here。

 unhandled exception。

![](img/1a2a2328b745ddbadead5f3fdf079124_5.png)

When you open a file or when you read a file， an exception is going to be thrown。

 you've seen lessons about this。 I need to either rethrow the exception or put a try catch block around this。

 Eclipse gives me the choice。 I can add a throws declaration or surround with a try catch for right now。

 I'm going to add a throws declaration。 That means eclipse came in and added this throws I O exception。

 And now we can see that my function here to read and print is complete。



![](img/1a2a2328b745ddbadead5f3fdf079124_7.png)

![](img/1a2a2328b745ddbadead5f3fdf079124_8.png)

My function down here that read from a URL is not quite ready to go。

 so I'm just going to comment that out because I'm not interested in it。

 I'm toggling the comment and eclips comments out every single line。

Now I can come down here and I can see。That Im want to call this method。

Read and print in my public static void main function。 so I will do that。

I'm going to run this program by clicking the Run button and we can see down here in my console window。

 which I will make a little bit bigger。That it said， hellello world in all the different languages。

 hello， Chao， Mihaba， that's about the most I'm going to do。

That was reading the file that was local on my computer。 Now。

 I'd like to go one more real quickly and read the URL。 So I'm going to uncomment。That。

I've got a couple of red X's because Eclipse doesn't know where the URL is。

 so I'm going to import the URL class from Java。net。I've just added that。

Then I'm coming down here and it doesn't know about input streamream readerer。

 which is in Java do IO。So I'm going to input that。I've got a mouthformed URL exception。

 I must add a throws declaration or catch it。 So you can see I've added malform URL exception。

 And then here I've got。An IO exception。And you can see that replaced malformed URL exception with the more general I O exception。

 There's an inheritance hierarchy for exceptions。 and I O exceptions kind of the parent class of all the possible I O exceptions。

 So now this method is done。 Read and print URL。 I'm going to call that by editing my main。Now。

 when I run my program， it will go to our Dukeletoprogram。com website。

 read the file that we've stored there and run might take a little bit longer。But as you can see。

I've still got hello around the world in all these different languages， as we say where I come from。

 Ola， enjoy your programming。

![](img/1a2a2328b745ddbadead5f3fdf079124_10.png)
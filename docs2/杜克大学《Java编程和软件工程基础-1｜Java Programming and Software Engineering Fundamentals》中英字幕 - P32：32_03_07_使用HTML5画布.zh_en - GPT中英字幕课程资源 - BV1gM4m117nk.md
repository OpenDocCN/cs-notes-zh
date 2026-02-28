# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P32：32_03_07_使用HTML5画布.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/62ceb0681cde594e8d7b5bbf6315ca44_0.png)

Hi， let's see how to create a web page and write code that will move us closer to the green screen page rather than using div elements。

 we'll use a new HTML element named Canvas。 The canvasva HTML element is used to store images in the Duke learn to program or DLTP environment that you've seen before。

 A canvasva has a different functionality than a div。 As you'll see， it's possible to draw shapes。

 lines and more。We'll only explore basic functionality of this HTML element。

 You'll see how it's accessed via JavaScript， and you'll be able to do more if you explore additional resources。

Previously， you have seen the div element used to specify a section of a web page so that the background color or other attributes can be changed programmatically by referring to the element ID。

 in this case， D1。😡，On this page， the make line button changes the background color to lime。

And the make yellowel button changes the background color to yellow。

Let's try using Canvas elementement instead of DF。You'll see that we have to make a few changes to the CSS and to the HTML panels。

When we use Cans， the Ho text disappear。It turns out that special methods are necessary to write text in a canvas。

But as you can see here with the canvas， the background color changes work the same as they did with HTML div elements。

We'll see more closely how to program with a canvas as we explore this functionality。In。More detail。

Let's talk about how a canvas is used。 It's used specifically to draw graphics。

 usually it's used with JavaScript。 You should think of it like a container for graphics。

 where the container needs to be filled in which you do by writing a script。

 There are several methods that you use to create these graphic tasks such as drawing paths， boxes。

 circles， text and adding images。We'll show a simple interactive page using a canvas element。

 We'll create a web page with two buttons using HTML， CSS and JavaScript。

 Each button will change a different feature of the HTML Can element。

 One will make the background line and the other will draw yellow squares and create text in the canvas all with JavaScript。

 Let's program。Let's look at an example of using code pen to combine Hml。

 CSsS and jascript to make an interactive web page using a canvas。 As we saw in the recent lesson。

 I'm going to have a canvas that's going to make both color background changes and draw using the graphics element。

 I'm starting with a canvas。 We see that we've got the canvas element here。 It's I D is D1。

 And we have two buttons。 One that says make limeme， and it calls a doli jascript function。

 One that says。

![](img/62ceb0681cde594e8d7b5bbf6315ca44_2.png)

Make yellow and calls a do yellow JavaScript function。

 The functionality that we have that we start with， which I've already coded is make lime。

 We can come over here and just review a couple of concepts。

 I use the standard document dot get element by I D to grab the element whose I is D1。As a reminder。

 that's this canvas。And then I make the background color line。

That's why the function is called duulon。In the make yellow function， which is。

The button that calls do yellow。I get the element by its I D， and I make the background white。

 So right now， making yellow actually turns it white。

 but I'm going to make it white in preparation for making some yellow rectangles。

 Let's also just review very quickly that there's some CsS for the canvas that styles it to have a specific width。

 a specific height and a border。 That's why when we start with the page blank。

 we see that the canvas is here。

![](img/62ceb0681cde594e8d7b5bbf6315ca44_4.png)

![](img/62ceb0681cde594e8d7b5bbf6315ca44_5.png)

With nothing in it， a little narrow border。 that's one pixel wide as we can see here specified in the CsS。

 and these two buttons。 So let's look at the do yellow jascript function and see how to make yellow rectangles appear by using the canvas。

 The first step is going to be that rather than drawing in the canvas。

 We're going to have to access the context of the canvas。

 That's a new concept for canvases that the graphics are actually displayed in the canvass context。

 The way we do that is create another variable。 I'll call it。



![](img/62ceb0681cde594e8d7b5bbf6315ca44_7.png)

C T X for context， and I'll get the context from the canvas。

 which is stored in variable Dd1 and the name of my method is get context。

 I'm actually going to take off my little bracelet because it's kind of jangly。

 so excuse me while I remove it and put it right there。

 It's kind of hitting the keyboard and it's annoying to me， might be annoying to you。

 So I'm going to call get context。 and I have to specify that I'm getting the 2D context in other examples we might see something beyond two dimensionmensional。

 but all the graphics I've ever done and that we'll ask you to do are the 2D graphics。

Now that I have the context， I have to fill it with yellow squares。

 The first thing I'm going to do is do something similar to what I did by setting the background color。

 I'm going to set the fill style。To yellow。That means anything I draw will be in yellow。

Then I'm going to fill a rectangle。 That's the name of the method there is fill rec。

 and I have to specify。Where it's going to be， I'm going to use this to see what happens。

 I'm going to actually test it。 First， I'm going to save it。

And I'm going to review the code that I wrote and then test it。I got the graphic context。

 then I set the fill style of that context to yellow。And then I created a filled in rectangle。

 and I specified the coordinates of the upper left portion of that rectangle， which are at 10。

10 and the width and height of the rectangle， which are 4040。 Let's see how that works。There's。

 I made it limeme。 Making yellow doesn't do anything。 So right now。

 I have to look because there's a bug in my code。 Luckily， code pen helps me find that bug。

 You can see that this is in yellow， whereas this is in blue。

 I didn't spell the name of the variable right。 Con is C T X。 So now I'll call make yellow。

 and I see up here。 a yellow rectangle。 exactlyactly as I'd expected。

 Just to see I understand the parameters。 Let's make this rectangle bigger，60 by 60。

 I'm hit and save。 make yellow。 that rectangle is definitely bigger。 Just because I can。

 I'm going to make that rectangle 100 by 100。 I want to make sure I understand that that makes the rectangle bigger。

 Sure enough， it's bigger。 I can actually change where it's drawn by changing that 10 to a 50。

 Let's see what happens。The rectangle is lower on the page because these are the X and Y coordinates。

 X goes along the width and y goes along the height with the upper left corner 0，0。

 as you learned in our Duke learned a program when we were talking about images。

 I'm going to set that back to 10，10，40，40。 And then I'm going to draw another rectangle。

 This rectangle is going to be near to the other one， almost adjacent to it。

 I'm going to make it at 60，10， and also make it 40，40。I'm going to not forget my semicolon。

 Let's see what happens when I make that yellow。 I now have two rectangles。

 Notice if I make the background line that draws behind the rectangles because it's the background color。

 Ma yellow changes it to white because as we saw here， the background color was changed to white。

 Remember that when you write code。 The method or function that you call executes from top to bottom。

 Make it white， get the context， make the context yellow， drawaw two rectangles。

 I've got one more thing to do with the graphics。 And that is， I want to create some text。

 I'm going to make the text in a different color。 So I'm going to set the fill style。To black。

And then I'm going to draw some text， and I draw text by saying fill text。

 I specify the text I want to draw when which in this case is hello， and I specify where to draw it。

 which is 1080。 Let's see how that works。

![](img/62ceb0681cde594e8d7b5bbf6315ca44_9.png)

I can't see hello anywhere。 Once again， I've spelled the variable wrong。 Apparently。

 I do that often by mis typing。 there's hello very。

 very small down there below the yellow rectangles。

 I can make the font different by setting the font style of the text just as I set the fill style。

 So I'll set the font to a bigger font。

![](img/62ceb0681cde594e8d7b5bbf6315ca44_11.png)

30 pixels。 And because I'm fond of。Ariel。I'll change the font to Arerial。

 Notice I now have hello in a bigger font。 It's 30 pixels just to make sure let's make it 50 pixels and see if that makes it bigger。

 That's definitely bigger。

![](img/62ceb0681cde594e8d7b5bbf6315ca44_13.png)

Unfortunately， it overwrites the rectangles， so I'm going to set it back to 30。I'm going to save it。

 I'm going to test all my buttons， make lime， make yellow， make lime。 I've got two yellow rectangles。

Done by the context F rec methods。 Notice I've set the style to yellow。

 If I had set the style to purple， for example。And spelled it correctly。 When I call make yellow。

 it makes purple rectangles。 That might be confusing。 so I'll leave it back at yellow。

You can explore more of the graphics context using the resources that we provide。

 have fun writing code with canvases， I do。
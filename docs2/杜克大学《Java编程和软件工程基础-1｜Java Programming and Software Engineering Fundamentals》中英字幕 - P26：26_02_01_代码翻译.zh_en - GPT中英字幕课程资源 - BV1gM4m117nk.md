# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P26：26_02_01_代码翻译.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/ec3808904cf8823e78990f7cd1954a13_0.png)

Okay now it's time to turn our pseudocode into JavaScript code for this video。

 we've already started by filling in some of the code because it is so much like our previous examples and we figured that you've seen it before so we don't need to go over it again。

 so that's creating the FG image， the BG image and the output image that is the same size as the FG image。

So we're going to get down to actually writing the code。

 which says to process each pixel in the FG image， so we've written our standard for loop that goes through each pixel of Fg imageage。

 values。So now we're at the first line of pseudocode that is nonstandard that's specific to this problem that we haven't written before。

 and that is to look at the current pixel and determine if it's green。

It turns out that we didn't really figure out what green is in our planning。

So we have to kind of figure that out now as we're coding。

 we intuitively understood it when we were working out our plan。

But how do we explain it to a computer， how does a computer know what green is？Right now。

 we're not sure。 So we're going to start very simply。 and we're just going to say if。

The green component of the current pixel。Equals 2，55。

That's an example that we've seen before that we understand means that something has a lot of green in it。

 In fact， it means it has all the green in it。 And so that's a simple place to start。

 And we'll see how it works out as we go。 Starting simply is often a good strategy。

For when you're writing code， just to make sure that we have something that works。With that done。

 let's start looking at what we're going to write when that condition is true。

 Then we're going to go inside the conditional and write that code。

 So it says to look at the same position in the B G image， and we recall。

That every pixel has a coordinate location within an image。Given by its X and Y values。

 So we're going to go ahead and get those and store them in。Variables， named。X and Y， reasonably。

So that is the corresponding location in the FG image。 and now we want to get the pixel。Of。

The Bg image at that same spot， So well the we'll call get pixelel。With x and Y to get that value。

So now those three lines。Represent that one line of our pseudocode。

So we needed to do a little bit of work to translate that one line。Into actual code。

Now that we have the corresponding pixel in the B G image。

 we want to set that to the corresponding position in the output image。 So we're going to do that by。

Caing the calling set Pix。With that x and Y and。The B G pixel that we just got。

And that completes the inside of that if statement。Okay， let's look at our last line of pseudocode。

 It starts with the word otherwise。 Well， what does otherwise mean。

 otherwise means only do this last piece if the condition on line 12 was false。Well。

 how do we write that code， well we could write the opposite or the negative of the condition on line 12。

 but that can be hard and so that is error prone that can lead to problems。So。Most languages。

 including JavaScript。Include something called an L statement a shorthand for this situation。

And else just means if the condition above On line 12 was false， then run this code instead。

So what do we do when we say otherwise， we're going to set the output's corresponding pixel to the current pixel。

So we're going to say output dot。Set pixel。X and Y， again。But in this case。

 we want the current pixel， so that's just pixel。Now we wrote X and Y here and。

Those might be and those are things that we want to。Compute， just like we did before。

 And I'm just going to show you a different way to do it than how we did before。

 I'm going to write these。Vues in line。Whereas in the previous version。

I wrote them and stored them in a variable。So from a functionality perspective of the code。

 these work exactly the same， whether I decide to save it into an instance variable or whether I pass it directly into the function doesn't matter from the programming functionality perspective。

So you should use the one that you're Mar comfortable with。

 some people find it more readable to give every value a name and some people find it more readable if the code is a little bit shorter and they can write them in line。

It's entirely up to you what you want to do。But I'm going to review my pseudocode and see that I start out and I've got for each pixel。

 that was my standard loop。I'm checking to see if the current pixel is green。Then， I'm getting the。

Pixel at the corresponding X and Y coordinates in the BG image。

 I'm setting those to the corresponding position in the output image。If that wasn't the case。

 then I'm setting the pixel， the corresponding pixel in the output image to the foreground images or the current pixel。

So I feel pretty confident at this point that my pseudocode is correct or that my code corresponding to my pseudocode is correct。

 so I'm going to run the code。It doesn't work。 Oh， my goodness。 I just double checked it。

 and I have exactly what looks like the foreground image。

 This doesn't look like it applied anything at all from the background image。

 How could that possibly be。Well， if you'll recall， when we were starting this video。

 we sort of felt like our idea of what green was was a little bit hazy。

 And this is a very exact measure for what green is。 This is saying。

The green has to be exactly the maximum value of green， which is 255。So I'm going to try to have a。

More loose definition of what green is， and I'm going to try。Say 2，40 as a value。

 So this now gives me a variety of green values to work with。

 And let's see what happens when I run this code。Ah。

 that looks a whole lot better now I can see dinosaurs， now I can see space。It。

 it seems like it worked a whole lot better to give us this range。 However。

 if you look very closely at the image， you'll see that Drew and I have a halo around us。

 We have a green halo where we weren't quite correct in our range。 So let's try。

 Since that worked so well。 Let's try upping the range a little bit more。And say， making it 200。

So that gives us even more。Green values to work with to try to get that halo to go away。

And I ran the code again。 And now you can see that the。Colors。

 the space colors are bleeding into Drew shirt。And so it looks like Drew is fading into space。

 and that's not what we want either。Now， we could spend some time trying to perfect this range for this particular image so that we get the halo to go away。

 but space doesn't intrude on。On the foreground image。

But that doesn't seem like the best way to go about solving this problem。

 because we're really just going to make it work for these two images for this particular range of colors。

 So let's think about a different way to define green that might be a little bit more general and robust。

So instead， I'm going to define green as a color that has more green in it than both red and blue combined。

 So I'm going to write that as。Green， the value of green is greater than the value of。

The red and the blue added together combined。So now when I run the code。

 I see that the halos went away and the space went back to its proper place。

 so I'm very happy with the results of this code that I've written。

I've gotten my code to work for these two images。And I feel very good about it。

 But to be certain of my code， I would certainly want to try it on a wider variety of images to see if I've really defined green correctly and gotten it to work。

😊，But I'm going to leave that as an exercise for you to encourage you to experiment on your own with your own images。


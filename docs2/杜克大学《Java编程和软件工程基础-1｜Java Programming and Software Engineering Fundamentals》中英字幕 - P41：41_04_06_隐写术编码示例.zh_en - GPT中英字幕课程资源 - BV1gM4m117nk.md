# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P41：41_04_06_隐写术编码示例.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Okay， we've walked through some of the concepts and we told you we would walk you through the code to hide one image in another。

 We've started here with the clear bits function， which we'd seen before in a previous video。

 which just takes the math thought floor of the color value divided by 16 and multiplies it by 16 to clear out the lower bits。

We've previously talked about the Cho to hide function。

 and we've written down here the steps for the algorithm for that。

 and we're just going to turn those into code。So we need four var。PX of image dot values。

 That's how you've seen to iterate over。The pixels in an image before。

 and we want to clear the low bits of the red。 So PX dot set red to clear bits。

 this function we wrote to do the math for us。Of P， X dot get red。

 So we want to take the current red value called clear bits to lower out the0 the。

To zero out the lower bits and then set their edge to that new value。

We can do the same thing for the green。And the blue。And then， when we're finished。

Our image that we've been modifying。Is the answer to our whole function。

 that's what we want to give back to over or called us。Now。

 I've got some placeholders for the other functions we're going to write here in a second。

 And at the bottom here， I've got this algorithm that we saw as our high level algorithm where we combine chomp to hide。

 shift and combined。 So at this point， these two functions don't do anything。

 So printing our overall answer is not going to do as much good。

 I'm going to comment these lines out。And instead， I'm just going to print start so we can make sure that that works pretty well。

Before we do anything else。So if I run this code。I'm working with our picture of Hussein Bolt。

 I get something that looks pretty similar as with the previous videos。

 you can notice that the background colors have changed just a little because I've been modifying these color values。

Great， now let's go work on shift。 So remember， this is where we're going to take those most significant bits and move them over into the least significant bit positions for the image we want to hide。

 So our algorithm is going to call for us to iterate over each pixel in the image。😊。

And what we want to do here。Is to shift over the red bits so we want to do PX dot set red and remember we can do this by dividing by 16 PX do get red divided by 16。

 because 16 is2 to the fourth power that will move everything over four binary digits or bits。

Now we want to P X dot set green to P X dot get green divided by 16。And similarly。P。

 X dot set blue to P X dot get blue。Divided by 16。And again， we've written this little bit of code。

 We'd like to make sure that it works， or at least looks like it works。 Before we move on。

 We're not testing very thoroughly in this video。 We would encourage you to do more extensive testing of your own code。

 So what if we now。Hide。And we print out hide。Oops， we left off， if we go back up here。

 we got sort of a weird error message， cannot read property gistring of undefined。

 What does that mean， Well， something was undefined。 That's generally a bad thing。

If I go back and look at this， I forgot to return my answer。Oops。

And now we get an image that's mostly black。 if you remember from before that's what we want。

 We've hidden all this information in the least significant bits。 we can't really see it。

 even though we just fixed one little compiler error。

 it was really good that we got that fixed before we had a big mess of code where it might have been harder to find that problem。



![](img/e1bc74790d0ae9e9ecf2414a6fdf04cd_1.png)

Finally， we need this combined function。We want。To make a new image， we're going to call it answer。

 It's going to be a new simple image of the same size。 So you want show dot gi width。

And show do get height。 these are show as one of the parameters to combine the image we want to show up and hide is the other image which we want to hide。

 We're going to assume they're the same size right now。 That's not very robust。

 You'll write some code to crop the images to be of the same size。Then you can work with any images。

And for each pixel in answer dot values。We want to get the x and y of that pixel。

 So var x equals px dot git x。 You should be pretty familiar with that by now。

 And var y equals px dot gett y。 Again， a familiar thing。

 We want to get to the same pixel Show pixel。 we'll call it from the show image dot。Get pixel with X。

 Y。And we want。The same。Hide pixel。Hi， did I get pixel。The same pixel from the hide image。

And now we want to set Px's red。To the sum of show pixels red。Plus， hide pixels red。

Remember that's going to combine them the two together。

 one of them is going to have the most significant four bit set and the other0。

 the other is going to have the least significant four bit set and the other zero。

 so when they get added together we'll get a whole eight bit number。

And then we're going to do the same thing for green。And for blue。And after doing that for each pixel。

 our answer is going to be the image answer。So now I'm gonna come down here。 I'm gonna。

Uncomment these last two lines， get rid of the extra one I wrote。

Now we get this image of Uain boltolt that looks like what we expected。 Are we sure it's right。

 Not really， we'd want to investigate a little more。

 We could have just messed up and maybe returned our。

 our start image somewhere or something like that。 We're not going to test terribly rigorously in this video since I would take more time。

 We would leave that up to you。So with that， I leave you with one final important question。

 what would happen if we hid an image of a stosaurus inside of another image？



![](img/e1bc74790d0ae9e9ecf2414a6fdf04cd_3.png)

It would be stosaurus sonography。
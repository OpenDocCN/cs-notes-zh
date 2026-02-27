# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p04 -04-COMP6080 - HTML 🐲 Image Types.zh_en -BV17RXGYuEaM_p4-

Hi everyone， My name is Hayden and I'm here today to talk to you about image types。

 imageage types fall into the HTML category， essentially just the introduction to web category and the point of this lecture is to not only understand what an image is in terms of how it's used on the Internet。

 but the different types of image formats that exist and why we might use different types of image formats。

 Now you're familiar that the Internet has images right。

 you're familiar with this because you go to Google images and you see a whole bunch of images here and they all kind of do the same thing。

 their aim is to convey information to you by you know essentially rendering pixels on the screen。



![](img/ce1a8313b36810156f4a4e9380f09a04_1.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_2.png)

A lot of these have different image types， though。 You can see this one here。

 Google's telling me that one's a JpeEg。 that one's a JpeEg。

 A lot of images like this will be JpeEgs。 But if I type in something different on the internet。

 for instance， like blue circle， we're gonna see that the types of images are different。

 For instance， this one is a P And G， P and G， P and G， P and G， P and G。

These are all PGs And these two are JpeEs。 And it's like what is the difference between these right？

 They all look like blue circles。 And that's really what we're gonna try and you know get into。

 So as we said， all of these images are about rendering a collection of pixels on screen to help provide some kind of visual and you've seen JpeEgs and PGs。

 but there are also these other formats that you' probably familiar with in some ways。

 such as Gif or GIifs as well as SvGs and Bmps， if you you know maybe you've seen those around。

 maybe you did a course where you had to manipulate one or perhaps even you。



![](img/ce1a8313b36810156f4a4e9380f09a04_4.png)

Use Microsoft paint back in the day， right， If you want to learn more about these image types。

 you can go and check out this article。 This is essentially just a quick pro and con of different image types。

 It's a good little reference point。 So you don't have to like come and watch this。

 But there's tons of stuff around Google that you can look at to just explain this because these are fairly introductory concepts。



![](img/ce1a8313b36810156f4a4e9380f09a04_6.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_7.png)

Now， before we dig into more about what these image types are。

 it's important that we understand the two kind of key categories of image types。

 which are vector images and raster images。 Now， there is a great  lecture in this course on SvGs。

 which are vector images， and it's worth going and watching that because I think there's a good comparison and there of the difference between a vector image and a raster image。

 vector images are essentially these。😊，You know， kind of computed images。

 It's like there's just instructions about how to draw something。

 But most of the images that you're probably familiar with that way down here are these raster images because raster images are literally just a collection of pixels in some kind of color space。

 It can vary per image。 But you can really trivially visualize them as a 2D array of colorss right。

 And that's what it looks like here。 It's columns and rows and there's colors in each cell。

 And that's what all of these different types of you know Jpeg P and G gift they're all the same thing。

 They're all collections of just colored pixels in some kind of structure。

 Now Raster images have downsides。 compared to vector images。 But again。

 we're not here to compare them today。 We're just here to learn about what these different types of raster images are。

So。Here is a really simple table kind of comparing。Bit maps， I call them G， JPg PNGs。And， you know。

 essentially how they work。 I think some of the key things to notice here are that。

You've probably mostly seen JPEGs and PNGs， right， and there's a reason for that。

 it's because they don't have any of the kind of base limitations that Bimaps and G have。

A bitmap image is quite literally， quite literally a 2D array of。Coours， right， it's。

 it's what you'd expect if you could go and make a BM yourself。

 It's something we used to get students to do。 you go and open up a text editor and you essentially can like fill in hex codes and you can make your own little BM。

 It doesn't use any compression。 It's， it's not losssy。

 Losssy is when you lose some quality of image。 And I wrote uses no。

 because it's just not really used much。Honestly anymore。 But you'll see it floating around。

 It's kind of like the the literal image。You know， if so you might have heard about a little bit more。

 but we'll come back to those at the end。 Let's focus on the two kind of heavy hitters of images。

 which is Jpegs and PGs。 Now， when we talk about their format is like 24 bit or 16 to 24 B。

 what this is usually referring to is it's kind of like if you understand basic computing theory。

 an 8 bit number is an 8 bit memory address or an 8 bit value you can store a certain number of numbers。

 right， a 24 bit。Set of numbers can store massively more amount a massively larger amount of data。

 So Jpeex and P and Gs can store more data per pixel。 right That's what this is saying。

 This is like a per pixel。 And what is more data per pixel mean， it means more subtlety in color。

 And you could probably find this out if you like look up 8 bit versus 24 B image。

 Because quite often you can see the difference。

![](img/ce1a8313b36810156f4a4e9380f09a04_9.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_10.png)

嗯。You know， like your。He's just like a quick example。 It's like。This is not a great example。

 but it's like 8 bit images。 will only have so many colour compared to 16 bit images。

 which have tons more。 So if you've ever gone and like found like an old school looking image that seems to have。

 you know， not as much kind of colour detail， it looks， you might say， oh。

 it looks a bit low quality。 Sometimes that's actually because they're using less colours。

 This is like a good example here， right， Like this is trying to describe the sky And the sky is a very。



![](img/ce1a8313b36810156f4a4e9380f09a04_12.png)

Nanceance color， right？ This is 24 verse 48。 Now you don't need to worry about the numbers or anything like that。

 but I'm just trying to convey the point that higher bit rates mean higher quality because it's more shades of a color you can put in an image。

 So PGs and JpegGs are pretty good on that in that area。

 they are both compression based image formats， which means that they actually do compression the image。

 so that unlike Bmps， which literally store all of the raw data。

 PGs and Jpegs will actually store like a compressed version of it。 Now。

 this is not a course about compression， compression is essentially just a way of trying to represent the same information in a smaller space。

 but here's where kind of the key differences。 JpeEg is what we call a lossy compression format。

 A lossy compression format means that when it compresses it actually loses some detail in the attempt to make things like very not using up a lot of memory whereas a lossless。

Compression format doesn't lose that。 So the way images work is like if you take a photo right and you compress it when you uncompress it。

 the question is was it the original image quality right like is it indistinguishable from the original If the answer is yes。

 then it's what we call lossless because nothing has been lost in that process of compression and uncompression and if it's lossy it means that something has Now that's really the key difference between JPgs and PGs Now what I'm going to show you is an example of me trying to export a Png in a lossy and lossless format basically via Png and a JpeEg to kind of understand the difference。



![](img/ce1a8313b36810156f4a4e9380f09a04_14.png)

So what I've got up here is I've actually got an image that I want to take you through and compare and contrast the difference between like a PG and a Jpeg。

 This is actually a Jpeg taken off the internet。 Most normal images are And what I'm gonna to do is I'm going to try and save this image and I want to show you the difference with like how a JpeEg gets saved versus a PG So I'm just using Photoshop at the moment and if I open up the save pop up。

 here's what we can see together。 What I have here is I have me trying to export the image a Png 24。

 Now Png 24 is essentially like the normal way to export a Png because it is 24 bits and I can actually show you the difference with like a 24 bit Png and an 8 bit Png because watch what happens when I go to 8 bit。

And I'， I'll go zoom in on a few， like I'll go zoom in really close on a few spots。 Oh。

 that's maybe a bit too。Maybe a bit too close。 You see something like this right。 Now。

 remember how I talked about colour space。 Look at the difference here。

 P N G 24 has a much bigger colour space because of its higher bit rate， and therefore。

 it is able to represent more colours。 But P N G 8， it struggles to do that。

 And that's the same for gifts because they're all 8 bit。

RightSo that's one of the reasons that Jpegs and PGs or P G 24 Bs are quite popular or even 16 bits because they represent more colors。

 Now， have a look at the size of this P G 24。 It is a 2 mebyte image。

 you can see that down on the bottom left here。 It says 2。106 M。

 If you're not watching this video on 1080 p， I would probably recommend you do that。

 And it looks pretty good。 Now， let's look at a Jpeg。 Now， a Jpeg at what we call 100% quality。

 I limited to no compression also looks pretty good。 And in fact。

 if I zoom back in on some of these spots。Like here。

 and maybe I'll zoom in even further so you can really see it。

Let's look at the difference between a very lightly。Compressed Jpeg and a P G 24。

 It's not very different。 In fact， I can see a couple of very tiny details。

 but totally indistinguishable， effectively， that P G is 2 MB。 And that Jpeg is 720 k。 Now。

 there are times when P Gs are better。 particularly for small icons and stuff。

 It's not like JpeEgs are always better because it is still compression。

 You are still losing some data。 But here's the crazy thing about Jpegs。

 If you actually turn the quality of a Jpeg right down， you can get some crazy compression。

 This is now 42 k。 The P G was 2000 kB。 but look at the quality of this image。 It looks。Awful， right？

 Absolutely awful。 And you'll see if I turn the quality up somewhere in between。 it looks like O。

You know， it looks。Bine。That pretty indistinguishable from a P G for like normal consumption。

 So instead of using a 2 MBby Png， we can use a 300 kiloby Jpeg。 Now。

 why would you not always use Jpegs That that would be a reasonable question here。

 And the answer is because Jpegs are always losing some kind of detail。

 The reason you don't notice it in an image like this is because this image is already kind of grainy。

 right， Like its I mean， it's already a Jpeg。 So what that means is that it's already actually lost some detail。

 You can kind of see the remnants of the compression here from the previous Jpeg usage。

 So the P Gs on the Internet， you often will use you'll often use Pngs for things like。



![](img/ce1a8313b36810156f4a4e9380f09a04_16.png)

O， sorry。

![](img/ce1a8313b36810156f4a4e9380f09a04_18.png)

You'll often use PGs for things like a Google nice image， you know， like an icon or something。

 because a lot of icons will have very subtle detail like this。 You know。

 you might want to keep all these little speckles。 if we tried to make that like Jpeg that。

 we lose some detail there that's really critical。 So it's kind of like， you know。

 if it was taken with a camera， often you will。Treat it like a JPg。 If it's not taken by a camera。

 you'll often treat it like a P And G。 That's kind of one of the key differences。

 So that's why these days we tend to use either of those two formats。

 The G format is still sometimes used。 You probably most often seen it as an animation product right。

 where you know， you see a G on the Internet because it's like an image with like frames and it does something。

 Nowadays， Web technology is getting much better。 And you'll see things like dot webm formats。

 which are essentially like mini videos that you can display on the。



![](img/ce1a8313b36810156f4a4e9380f09a04_20.png)

The Internet， which are essentially replacing gifts。

 So for all intents and purposes in terms of basic image formats。 nowadays。

 you're only really concerned with Jpegs and P And Gs。 Now。

 this leads us on to the last part of today， which is probably going to be important for one of your assessments。

 is the idea of base 64 encoding。 Now， here is one of the problems with the modern Internet。

 There's tons of tons and tons and tons of。

![](img/ce1a8313b36810156f4a4e9380f09a04_22.png)

You know， images everywhere， right， on like tons of websites。 I think about Airbnb as an idea。



![](img/ce1a8313b36810156f4a4e9380f09a04_24.png)

Real estate dot com， you know。Lots and lots of other things are just images everywhere and one of the problems is if you follow this link。

Most web browsers are actually limited by how many images they can get from one website one like server at a time。

 So let's just use Chrome as a benchmark。 It can only get6。

 So what that means is that if your computer tries to load6 images。



![](img/ce1a8313b36810156f4a4e9380f09a04_26.png)

From Airb like 12 images from Airbnb， it can only do 6 at a time asynchronously， like concurrently。

 And then it has to like， you know， it's only got like 6。

 like think of it like I've only got six hands。 You know， it's I can only grab 6 things at a time。

 I can keep grabbing more。 but there's any 6 I can grab at the same time。

 So what happened was people started saying， hey， what's the point of like。



![](img/ce1a8313b36810156f4a4e9380f09a04_28.png)

Loading up H pages where we send you an H document。 and in that H document。

 we then give you like an image tag and tell you， can you then go and load this image， right。

 because that's what an H pages。 essentially a page that the server gives you with more instructions about more stuff to get from the server to build a page。

 So that's where the idea of base 64 encoded images came from。 And the idea with these was that。



![](img/ce1a8313b36810156f4a4e9380f09a04_30.png)

For small images， when we give an H TM L page。 and let me just prepare a quick example for you。

 So just made this really quick web page， right， It's super simple。 It's just， it's just B。

 Ho and this image。 And I'm gonna give the image。

![](img/ce1a8313b36810156f4a4e9380f09a04_32.png)

A width of 400 just so it's a bit smaller， you know， when we have an image like this。



![](img/ce1a8313b36810156f4a4e9380f09a04_34.png)

That's actually still very big。 Maybe 200。 You know， we have a page like this。

 That's like hello and then a cat image for small images， which isn't this cat。

 What they figured out was that instead of creating an H page where I send a URL to then go and fetch Let's actually just send all of the pixel data。

 Like just the image in some kind of it's like you ever tried to open a file like a Jpeg and like a notepad or a text editor。

 and it's like a big bunch of goble， obviously every file is just a bunch of you know binary， right。

 So they're like let's just send the actual like code for it。 So you can actually see this。

 and Google started doing this too。 And you've probably come across this problem。

 I have to turn off my large image small。 have you ever gone on Google And have you ever clicked on have you ever like seen an image you like And then you've clicked on it or something and you've gone copy image link。

 and then that one's not a good example。 I'm sure one of these will do it。



![](img/ce1a8313b36810156f4a4e9380f09a04_36.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_37.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_38.png)

Let me just find it really quick。

![](img/ce1a8313b36810156f4a4e9380f09a04_40.png)

You've probably seen this I don't know， draw off。So' for small images of drops on Google。

 if you have a copy image link， you'll arm on being， no wonder。Sorry， I use E for my lecturing。

 and I think Google does this and Bing doesn't。That much。 But if I write， click on an image。

 I was wondering why it wasn't working。 You'll actually see you ever sent this to a friend。

 You've been like， oh， check out this image and you paste it in like Facebook。 And it's like， what。

 what just happened， What actually happened here is that the image that Google was loading on this page。



![](img/ce1a8313b36810156f4a4e9380f09a04_42.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_43.png)

This page loaded on your browser。 And then it's not that your browser went and fetched another image from the Internet。

 Your browser actually was given this whole image as part of the loading process。

 So this image is actually this bunch of code here。 That's actually the giraffe。

 just compress like just encoded in a format that's just made up of ASI characters。 essentially。

 Okay， so now what I can do is instead of putting in the image source on my page。

 another URL I can just put in that actual random text as the giraffe image。😊。



![](img/ce1a8313b36810156f4a4e9380f09a04_45.png)

And then when I go back to my page， I can load that giraffe too。

 And this is really interesting now because my page is only had to load one image。

 Like it's only had to load the HTML file。 Now， obviously。

 the HTML file is bigger It's now bigger because before it was like two lines now it's like a tunnel lines。

 But from a network perspective， I don't have to go and make more requests。 So what does this do。

 It means the initial load of a page is a little slower because the file you're getting as bigger。

 but it means subsequent loads unnecessary because they've been encoded now。

 this doesn't work great for very large images。 You actually see the way Google does this a lot of the time is that all of these images tend to be base 64 encoded like you go and look up most of them and they usually all base 64 encoded。

 But the big ones here when you go and get their image location it tends to be an actual URL。

 So what Google' is doing is they're they're trying to find fast ways to。



![](img/ce1a8313b36810156f4a4e9380f09a04_47.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_48.png)

![](img/ce1a8313b36810156f4a4e9380f09a04_49.png)

Load all of these images because remember how we said you can only load so many concurrently。

 So they're like， okay， they just give you like one page back。

 which has all the images encoded in it and then any bigger images they won't encode because that would be like just very inefficient。

 So they actually give you the real URL。 So there's like a mix of approaches here。

 base 64 great for small because you can just send one request back with like 20 images in it and you're not dealing with any browsers or concurrency or anything like that。

 There is no right or wrong way。 That's just a bit of background information。

 But and you can do this with P andGs and Jpegs they're both work fine。That's really the crux of it。

 hopefully that gives you some background on some of the， I guess。

Slier details about what all these different types of images and things you see are around the internet and how they work with our HTML web pages。



![](img/ce1a8313b36810156f4a4e9380f09a04_51.png)
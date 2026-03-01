# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P6：06_01_06_4-人类视觉系统-时长-17-10.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Without any doubt， one of the main clients of image and video processing is us。

 So let's just learn something about our own visual system。



![](img/2615250ac781e88280ff9a6e4515dbd1_1.png)

Here we have a very simplified cross section of the human eye。We have the cornea。Here。

We have the lenses。And we have the retina。The retina is where the images that we see the images that come to our eyes are projected onto。

 so basically as we see in this figure， we have the sin。

 So this is the actual scene in the real world and is projected into our retina here in the back of our eyes。

The retina basically has sensors， as we're going to talk in a second。

 and the images are projected onto the retina， and then they are sent into the brain。 Okay。

 so the retina is full of sensors。

![](img/2615250ac781e88280ff9a6e4515dbd1_3.png)

All over the retina。And actually， we have two types of sensors。 We have cones。

 The cones are basically marked here by the continuous line。

 That's the density of cones that we have in the retina。 And as we can see， there is a very。

 very high density of cones。 We see a very， very high peak of cones around the phoba。

The phobia is basically where we can see the best Cones are very good at seeing details。

 Cones are very， very good at seeing in bright light。 So we actually， without as noticing， of course。

 in our regular scenario， we are always trying to move our， such that basically the scene。

 is projected as much as possible into the phobia region of our retina。 So those are the cones。😊。

And they actually， their density， the amount of cones。

 the amount of receptors goes down when we get away from the phobia。

There is a different type of receptors， basically of sensors， which I called the roads。And。Those are。

 sorry。The roads are basically marking this picture with these lines。

So the concentration of the roads is actually a bit more uniform across the whole retina。Basically。

 as we can see in this picture， there is， of course， a very low。

 basically nonexist concentration where the cones take over。

 and the roads are actually very good to not to look at details。

 but to get a general idea of what's happening at the scene。

And they are actually very good to see in very dim light。😊。

So between the cones that are very good at seen a bright light and very。

 very concentrated around the fovea and the rows which are spread all around the retina。

And are very good at seeing at very low lights。 We get an extremely large spectrum of light that we can observe with our naked eye。

 Before I detail a bit more about that， I want to tell you that there is a region in the retina。

 There has basically。😊，No cs。And that's that region here。 That's called the blind spot。 Basically。

 there's no receptors there。 And we don't notice that。

 and we're going to discuss that in a few weeks， when we talk about the image processing technique in painting。

 which， as we have seen in the first videos is about making removing objects from the scene。

 we're going to be talking about the blind spot a bit more and why or how its believed that we actually don't notice that there is a region of our visual system that basically there there are no reception of what's happening in the scene。

 but were completely unaware of that。So going back to the point that we have an extremely。

 extremely broad range of intensities that we can see when we combine the cones and the roads。

We should note。That as the in this figure， we are actually， we can actually perceive a very。

 very broad range of intensities。 So this is in logarithmic scale。

 It's really a huge broad of intensities that we are able to perceive。😊。



![](img/2615250ac781e88280ff9a6e4515dbd1_5.png)

And some of it is actually perceived by the roads。Low intensity， some of it is actually perceived。

 but it comes when we start going into high intensities。

One of the issues is that we are able to perceive very， very large range of intensities。

 but not at the same time。 So we cannot see in very dark rooms and very light regions of the room at the same time。

 so we we can see very dark。 we can see in very dark rooms， we can also see in very light rooms。

 we cannot see at the same time。 And what we need is actually to adapt。 So at certain level of。

 at certain level of intensity。 for example， this point， we are actually adapt。

 and we are able to see this range。😊，If we are adapting around here， we are not able to see。

Or at least not see very easily around here or very， very low intensities。 That's what happens。

 We experience this all the time when we go into a dark movie theater at first。

 we don't see very well。 And after a while， we adapt and we actually see where we are going and where do we need to see it。

 And the same when we go into a light room。😊，Now， it's very important that regardless of the background light。

 we're able to distinguish the details and and at different levels。

 So when we go into a movie theater and the lights are off。

 we don't want to see a uniform movie theater we need to find where basically our seats are。

 so we need to be able to discriminate even between very low levels of light and we also need to be able to discriminate between very high levels of light。

 So that's what these adaptation allow us to do。 and there are very。

 very good experiments in the literature to try to understand what kind of discrimination we can obtain a different levels of light。



![](img/2615250ac781e88280ff9a6e4515dbd1_7.png)

And these experiments are， basically。Very simple in its， in its most fundamental form。

 So there is a background light。And we basically draw a circle in the middle。

 and we start changing the light of that circle until the observer says， oh。

 I notice that there is a circle in there。 We can go up， making it lighter。 We can go down。

 making it darker。 and then we measure how much change are we able to perceive。Now。

 the amount of change that we need to perceive depends actually on the background light。

And that's what's called Welo， and this is。Shown in this picture。

 it's a very interesting effect that if we are in very low light conditions。We need the delelta。

 the change to be relatively high。 if we are in very。Hi， background light。

 we don't need so much change。So the basic idea is that if we are in a very dark room。

 very small changes in in light， very， very small changes in in in brightness will not be perceived。

 We actually need。A much wider range of changes， basically a much larger change。 So basically。

 two things that are very that both of them are very dark and very similar。

 We won't be able to distinguish between them。 On the other hand， when the background。

Is already very bright。 We don't need so much difference between the different levels to be able to distinguish between different objects。

 and that， as I say， is called the We law and it's extremely important in the design of images and in the design of cameras and the design of different image acquisition devices because if we want to distinguish between two objects that both of them are very dark we need to be very careful because we know that we need a very large difference between those objects。

 we are actually going to learn in week3， actually how to make。These differences。

Even larger so we can distinguish them。 So if we take a picture of two very dark objects that are different objects。

 but they're basically a brightness is very similar。

 we're going to be able to process that in the computer so we can。

 even with our naked eye distinguish between them。So the conclusion of this part is that we are able to observe and understand and make interpretation of images in a very。

 very。😊，Wide range of brightness， but。We are not able to do all that at the same time we need to adapt and if we are adapting to dark。

 then we are less sensitive that if we are adapted to bright areas to very high levels of light。



![](img/2615250ac781e88280ff9a6e4515dbd1_9.png)

。Another very interesting aspect of our visual system is that our visual perception depends on what's surrounding us。

 One example is already web law。 If we can perceive this circle in the middle。

 depends on actually the。😊，Bness de luinance around it。 The other is what's called Mac bands。

 And it might be a bit difficult to see this through the video。 But let me explain it。

 And in the next slide， we're going to see a even more clearer example。

The basic idea is that while I do present here。I present you here a black region， a bit lighter。

 a bit lighter， a bit lighter and so on。 The actual intensities that I'm painting each one of these is is constant。

 So basically the intensity here is constant， as we can see it here。

 The intensity here is constant is this intensity， and so on。

 So the intensity of every single one of these segments is constant。

Our perception actually doesn't look like this。 It actually doesn't look constant， like in this。

It's actually， like， here。We perceive that when a dark region is closer here。

 So we are at the boundary between here。 we actually perceive that the dark is even darker and the brightest even brighter。

 You might be able to perceive that in these regions， for example， that basically。

 we believe that because we are coming here into a brighter region。 We're coming from this night。

 It actually looks darker。 We perceive it as being darker。 It's not actually。

 but we perceive it as being darker。 I'm going tose my annotation。

 So maybe you can see that a bit better。 Let me just point again to where you should be looking at。

You should be looking at this boundary， for example。

 I'm going to draw on top of it and then erase it。 You should be looking at this boundary that when you're coming from the left。

 it looks actually darker than it actually is。 And when you're coming from the right。

 it looks actually brighter than it is。 So let me just erase this and give you。

Couple of seconds to try to see if you see that。 But if you don't， don't worry。

 we're going to go into the next slide and it's going to be even more clear。



![](img/2615250ac781e88280ff9a6e4515dbd1_11.png)

Here， let me explain what we have。 We have three。Rectangles。They actually have exactly the same。

Briness， so they were painted with exactly the same paint。Now， the background。

Have were painted with three。Different。Levels of gray。 This is dark。 This is light。

 and this is in between。And。I hope you can perceive， even through the video。



![](img/2615250ac781e88280ff9a6e4515dbd1_13.png)

Ded。

![](img/2615250ac781e88280ff9a6e4515dbd1_15.png)

Let me just go back。YouThat this。Looks。Daarker than this one。Because this one。

 I'm going to raise all my annotation in a second。 so you can look at that again。

 This one is surrounded by a brighter background。

![](img/2615250ac781e88280ff9a6e4515dbd1_17.png)

T this one that is actually surrounded by a very， very dark background。

 and then the perception is that this one is actually perceived as being darker than this one。

 Let's see if we can see that once more。

![](img/2615250ac781e88280ff9a6e4515dbd1_19.png)

Okay， I hope you can perceive that。 so there is a lot of visual illusions that and tricks that our visual system plays with us。

 and here is yet one more。

![](img/2615250ac781e88280ff9a6e4515dbd1_21.png)

嗯。The idea here， there are a number of things once again I'm going to use my annotation。

 and then I'm going to erase it， so I hope that all of you can perceive here as square。

It's actually not a square。But you can perceive， you believe that there is a square。

 So you believe that there is a square right there。But you actually， theres not。

 There is actually absolutely no difference between the colors when I go around here。



![](img/2615250ac781e88280ff9a6e4515dbd1_23.png)

Between the level of y， there is actually no difference here。But this gives us the illusion。

That is actually a square。Here。I hope you can see it now， similarly in。This image。We actually have。

Stray lines coming。Nothing in the middle。 but when I'm going to erase that。

 I hope you will be able to perceive that there is kind of a circle form in the middle。

So we perceive it's actually very interesting to see that sometimes the actual responses of our visual system。

 so if we were and measure the actual firing of the neurons in certain regions of our visual system。

 they are identical to those that will happen if I actually drew a circle there。



![](img/2615250ac781e88280ff9a6e4515dbd1_25.png)

![](img/2615250ac781e88280ff9a6e4515dbd1_26.png)

So this is a visual illusion that is as strong as an actual drawing。

here is yet another example that because here we actually make an angle like this and here we make an angle like this。

 most of us will perceive this line as being longer than this line。The same on the figure。

 on the right。Most of us will perceive that these lines are actually not parallel。

But they actually are。And the perception that they are actually meeting each other is a result of basically a visual illusion。

 so it's important when we're doing image processing to understand how our basic understanding of the visual system works once again。

 because the main client of image and video processing is basically us。



![](img/2615250ac781e88280ff9a6e4515dbd1_28.png)

So in the next video， we're going to start seeing formulas。 so far。

 I have shown you basic images and some basic understanding of the human visual system。

 really basic understandings and people spend their whole careers studying the visual system。

 So these are just some very， very basic concept that are important for us to continue and now we are going to start talking about what are pixels and whats quantization and what thisization and what are those megapixel cameras or even gigapixel cameras and what does。



![](img/2615250ac781e88280ff9a6e4515dbd1_30.png)

![](img/2615250ac781e88280ff9a6e4515dbd1_31.png)

All that me。Thank you。

![](img/2615250ac781e88280ff9a6e4515dbd1_33.png)
# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P49：49_05_11_11-Adobe Roto Brush幕后技术-时长-31-29-可选休息点-20.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。In this video， were going to learn about Rotobush。

 Rotobush is the video segmentation algorithm inside After effects。

 After effects is the video processing product from Adobe and Rotobush was released around April 2010 with a new version of after effects that was released at that time。

 and it was considered one of the highlights of that new release。

 So I think it's very cool to learn about the basic concepts behind Rotobush。 So let's dive right in。

😊。

![](img/5642dce5d4ed051be8e2fc8724dc1a1f_1.png)

When we are doing video segmentation and in particular。

 if we're doing video segmentation for products that are going to be used， for example。

 in advertising or the movie industry， we need some very basic characteristics that need to halt。

We need very high accuracy， we need to be able to do segmentation at the P or even sub Pix level。

As we saw， these are very challenging problems， so the user is going to have to be in the loop。

 and we want to make sure that the way the user is involved in the process is a very comfortable way for the user。

And if the user is involved， this has to be done basically and in real time。

 you cannot request from the user to do something， then go home。

 come a few hours later and see what other results。

 you need the user to interact in real time with a computer。

 and those are basic characteristics that any one of these type of systems needs to have and certainly rottobraush has。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_3.png)

Now we need。High quality。 So we will need to be able to segment the videos with very。

 very high quality to get to the set pixel levels， to be able to do that。

 And this is a video that we have seen before。 Now。

 why is this so challenging for a number of reasons。 some of them we have seen and some of them。

 I'm want to go back to them。 So these are some of the challenges that we encounter。

 And we encounter them in video， we encounter them also in images。

 And that's why I basically using stills here as well to illustrate。

 One is overlapping color distribution。 What do I mean by that。 We saw in the previous。

Slide that I want to segment out these two players。 But look。

This player has a white shirt and also people in the audience have a white shirt。

 this player has a blue shirt， there's also blue here， there is blue here， there is blue here。

 so basically there is a lot of overlapping colors we discussed that early Leon it looks like color enough and therefore edges are not going to be sufficient to do an accurate segmentation。

Here is another example where edges are not going to be sufficient。

 there's basically no boundaries here。So how do we know to cement out the car if I don't really see where the car ends？

Additional challenges that appear in particular in video is that there are what's called topological changes。

 So look how the arm here is separated from the body in one of the next frames is actually touching the body。

 and this hole has been created。So the actual shape。

 the global shape of the object of interest is changing and once again is changing here。

 there is a new hole， so there is a lot of variability because of the articulation。

 and that makes the problem really， really challenging。So。

What are the type of features that are in rottobra in the segmentation behind rottobra that basically we need to have。

 but also features that we need to have in many， many of these type of video segmentation approaches so accuracy we already talk about that。

Robustness。Robustness also refers to the fact that not only the image can be changing。

 but we actually might have a very， very rich variety of data。

 and we want this algorithm to work as good as possible for all of them it might work better better for some of them。

 meaning the user might need to be less involved。For some， the user might need to be more involved。

 but we want this to be a really good algorithm for all of them。

So has to be practical and this is related to the user intervention。

 we want to make sure that when the user gets involved。

 things get better because of involvement of the user and don't get worse so we don't want to let the user to basically say。

 oh I'm happy with everything but this and then the user go goes and does something that basically destroys the parts that he or she was already happy with so it has to be a natural workflow and very easy and as we say has to be very computational efficiency so we have about 30 frames a second in the NTSC American system and similar 24 to 30 frames between the NTSC and the pilot systems and we don't want every frame to take hours which is want every frame to be done really kind of in an interactive comfortable time。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_5.png)

So the algorithm I'm going to describe has four major steps that we see them here。 first of all。

 we are going to do segmentation one frame to the next frame。

 then we're going to propagate multiple frames ahead and then we're going to show local correction and I'm going to basically briefly mention about post processing which is a concept that we are segmenting videos and not just still images and we're going to see many。

 many very cool examples， so let's start with the localized classifiers。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_7.png)

So let me explain what do I mean by localized classifiers？

We are going to assume that we start from the segmentation of a given frame。

This segmentation was obtained either manually， remember we are talking about segmenting entire videos。

 so certainly we can ask once in a while the user to manually do a segmentation。

 but we know that we don't actually need that because we have learned many ways to do this type of steel image segmentation so we start from one segmentation。

And we want to propagate this segmentation to the next one。

 that's going to be our first challenge here。Now we're going to have what we call local classifiers。

 so we're going to put windows center around the segmentation around the boundaries that we have just computed。

From each one of these windows。That basically go all around。 So everyone has a window。

 Every pixel has a window， or maybe we do every few pixels going around the curve with some overlapping。

 as we have illustrated here。 from every one of these。 We have very important information。

 So once again， this is just a local window。Is here because we are in a frame that we are giving the segmentation for that frame。

 so we are on frame T。 we have the boundary and we have the inside and the outside of the object。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_9.png)

Now， because we have that， we have two very important characteristics in that window。

We have a shape right。That we say， okay， we believe that the next frame we have a similar shape。

 Remember， frames are very， very fast in time， So things cannot in a normal video。

 change a lot between frames。 So we have a shape prior。 We also have a color model。

 So we know what type of colors to expect in the programeground。

 What type of colors to expect in the background。That's for every one of these windows。

So let's see how we use that。We are now in frame T。

 and we want be able to segment out frame T plus1 this we have， as I say。

 is one of frames that either we mark by hand or is one of the previous frames。

 as we are going to see in the next slides when we progress。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_11.png)

And we have these windows all around， and I want now to segment out the player here。

The first thing we do is we basically move these windows to the new frame。

 Now we can just move them with basically no shifts and that won't be too bad or we can move them following what's called motion estimation。

 You remember when we talk about video compression。

 We talk that we go in a block and look for the most similar block。In the previous frame。

 this is what we are doing now， so。For example， we could go into every region and see either backwards or for or forward。

 we can see what's the closest box， what's the closest local window so we can start for example in this local window。

 look around a regions here and then move it to the place that we believe is the closest one。

 we can do the means square error， the absolute difference。

The same type of approach that we did for prediction when we were talking about video compression。

 So for every window we have a new position again， if you believe that there's no too much motion in the image。

 you can just copy them to the same position so we copy them we use this motion estimation to move them。

 so now we have the windows。In the new frame that we are about to segment。Now， remember。

I'm going to just pick two windows。 I'm going to pick a window in the current frame and one in the future frame。

 This is the segmentation that we know。 This is where we need to put it。 Now。

 we are transferring the red curve。To the blue， because we have moved the， basic， the block here。

 But we don't believe in the blue curve yet。 That's the one that we need to adjust。Now， remember。

That for this， which we call the training because it's something that we already have。

 we have a shape prior and we also have color distributions。 So we have。

 we say more or less this is what we believe should be the curve here。

 And these are the distributions of colors in the foreground and in the background Now why do write here GMM。

 this stands for gaussian mixture models， that's one way to approximate the distribution of foreground and background。

 So think once again about the histogram distributions， now instead of having the histograms。

 we want to approximate approximate them by a parametric function and that's why we are using for rottobrar Gaussian mixture models but it's not critical now Just remember you have a distribution of colors for the foreground a distribution of colors for the background for simplicity。

 just think about。Perhapss。Now， that's what we're going to try to combine to， basically。

Find the exact position of the blue curve。 So once again， the red moves to the blue。

 but we want to be able to shift that around。So this is going to provide us some information of where should it be。

 I'm not going to allow it to change completely because I'm not expecting a complete shape the formation from frame to frame。

 I'm also not expecting complete changes in the color in the pixel values in the image。

 So this provides me a very good prior about the colors。 for every pixel inside here。 I can say。

 are you more probably。Foreground or background， so we can get a picture like this and the idea is to merge。

A shape prior and a color prior。嗯。How to merge them is going to be what we are going to explain next。

 The important part here is。That from what we already know， we can get for every block。

Kind of a distribution of probability， probability of shape and probability of colors merge them。

 And then we get a probability of every pixel being either foreground or background。

 That happens for every single one of these blocks that have moved from the previous frame。

And therefore we put it back， we get that for the entire。Image。And from that， for example。

 using graph cuts， we can get a segmentation and from this frame。

 we will be able to go to the next frame Before that， I have to explain you how we do this merging。

For the merging， we have to remember that we have both colors and shape as indicated here。

 So for every block， color and shape， how we combine them。 the basic idea is what's written here。

 if you have colors that are well separated， trust them， If not trust the shape。

 if you are ambivalent， trust both and merge them So we have the color distributions here from the previous frame。

 we have information from the previous frame， a segmentation that we trust and we got the shape prior。

 the color priors。 if the color distributions are well separated， So you look at the Instagrams。

 for example， of every color or a distribution of all of them together and you see that they are very well separated and there are multiple ways to measure that。

 if they are well separated， trust the colors， trust the probability and use。

The shape prior very limited so the shape prior was somewhere here that was the curve you say I'm going to let you be any place at a relatively large distance from what your shape prior predicted so you basically can go and every pixel that has certain distance from the prior is an allow region for the prior so you get this two type of probabilities you merge them you get your confidence map or the probability that we saw in the previous slide that if you have this confidence。

If you don't trust them too much， basically you have that the distributions are more overlapping。

 then what you do is this band that had a prior。Shape， you make it a bit narrow。 You say basically。

 I don't want to let the boundary in this particular block to go very far from what I predicted has to be more or less where I predicted and the less you trust the color because of overlapping the more narrow you make those bands。

 So this are three examples from the video， and these are real examples。

 So this is the back of the player where the colors were very well separated。

 This is the another region。 there is not such a clear separation。 And look here。

 Even the image tells us the separation between foreground and background is not very good For all the cases we get as we saw in the previous slide Both color and shape。

 The difference is once we're given the shape prior， something like this will be here。

 here will be something like this and here will be this。 how much we let that shape。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_13.png)

To impose the actual position of the new curve。If we trust a lot the color。

 we basically expand that shape prior a lot and we say。

 be anywhere you want because I know colors are going to help me。We thrust it a bit less。

 we see that this is a bit narrow when the color distributions basically don't provide any information。

 the shape prior comes to the rescue and say I'm sorry you cannot change too much。 so it's a very。

 very narrow band。This always comes from the probability comes always from the colors of the previous frame。

 the actual shape of the confidence of the prior depends on the confidence we have here these two we add them。

 we normalize and we get what we saw in the previous example here。

 for example there is no way to use colors they are too similar but the shape prior because the previous frame was so nicely segmented。

 help us to continue with the segmentation for the next frame and so on this is a very important concept where we merge different types of information to obtain the segmentation that we want。

Let's just illustrate how important this is。 We have here one frame。Sigmented。

 we have the horse segmented out， and we're going to want to segment the next frame。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_15.png)

So， first of all。Why this local， remember having this frame， we are having blocks around。

It and we do everything local because they overlap， they share information。

 but everything is local if we were not to do it， so if we were to consider one entire frame as one block。

 there is so much variability in the colors that the distribution basically makes known sense and we won't be able to segment the horse。

If we use the local。This is what we are going to get already much。

 much better using local color models because we only care about what's around。

Each one of the pixels。In the boundary now there are still problems with basically as we see here the horse is white。

 the carriage is also white， so certainly the color there won't help a lot and we see that problem coming here okay but that's where the shape prior this provides both colors and shape for the next frame and that's where it comes to rescue and here we see what we get when we combine both locality and shape and color priors we get very nice prior that as I say before with an algorithm like graph cardss immediately gets the nice segmentation and we propagate the segmentation to the next frame so both local and combining shape and color is very important to get this accurate segmentation we're gonna to see very soon that the locality。

It's important beyond what I just explained， it's also important to help the user have a much more friendly interaction with the images。

So this is how we actually go from one frame right to the next frame。

 but we don't want to do just one frame， we want to do multiple frames， how do we do that？



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_17.png)

So the basic first idea that will come to our mind is okay segment the first frame。

 go to the next frame， then from the segmentation of this frame。

 go to the next one from the segmentation of this one go to the next one and keep going as long as you can as far as you can but this has one fundamental problem the fundamental problem is the following。

This is a frame that we trusted， we trusted it a lot， maybe because we did the hand segmentation。

 maybe because we work very hard on that。Now， this is the result of the algorithm I just described based on this。

This might not be perfect。If I propagate this to the next one。

 then the errors I created here propagate to the next one， which means that my shape prior。

Eor propagate my color distributions。Also the estimations for this frame propagate if there are any errors one way to address that is to say。

 okay， in order to stabilize the system， why don't we let the color priors also to influence here Why don't we let them keep moving and also hear and also here this is the frame that we trusted a lot so let's just have it move forward remember that we're working in blocks so locally we let it move forward and in that way everybody will get also some of the information that we have from the original frame and from the original segmentation that we so much trusted。

And in this way， what we get is that our segmentation has propagated not only one frame but has propagated multiple frames。

 so once again the information that we trust and because we're working locally it doesn't have to be that we trust it globally it only has to be that we trust it locally。

 that information we can propagate multiple frames to help stabilize the system。

 we could actually iterate and use the current segmentation as the initial condition or the prior for the next segmentation and so on that's an option in this type of frameworks。

 but the critical part is to use information that we trust as many frames ahead as possible。

Before I give you some cool examples， there is a couple of additional things that we need to do。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_19.png)

One of them is how are we going to let the user to repair mistakes。

 No matter how great the algorithm that we developed， video segmentation is a very。

 very tough problem。 In particular， if we are going to segment to our movies。

 so we need to let the user do repairs in the algorithm， remember when we trust a frame。

 we really trust it， so we better make sure that all the frames all the way are in very good shape。

So， here is an example。We have this progression， and then we realized that it was good。 It was good。

 But here there is a mistake。So how are we going to let the user repair that mistake？

Here is where once again the work on local blocks helps a lot。So we basically want to do that。

 We want to go。And repair it。 And there is many packages that will help us to repair。 Basically。

 I want to illustrate that again。Here we have it。And now we repair it。

 So we repair it inside many different packages， Photoshop after phase。

 you can just go and move that curve。But of course。

 remember there were propagation before there was propagation before。

 So that mistake that we had before propagated， propagated propagated。

 I want to now the correction I did。 I wanted to propagate as well。

 I don't want to propagate backwards if I'm happy with what happened in the past。

 I don't want my correction here to influence what happened here because I'm happy with that。

 So here we have everything based on local blocks， local patches。 and that's great。

 we go and look at every block or every patch that is affected by my recent repair。

 and because we have this motion estimation that we did。

 we know where are these blocks going in the next frame。😊。

We have their position in the future as well and then we go and do repairs only in those blocks。

 maybe we can expand a couple to decide to just make it more continuous repair but we certainly are not going to let the propagation of the correction go all the way far away here and that's how we get this local control。

So these blocks are helping us to get local features and are also helping us to do the interaction much faster。

 So look what's going to happen now with these repairs。We is do them， and here it is。

 we have repaired them。 Let me show that again to you。We had a mistake。

 but which as a repair a mistake， we let that。Repair。

 propagate to the corresponding blocks in future frames。

And then we get everything repaired and then we can continue with this frame segmenting forward frames。

 So this is very cool。 This is the third step that basically is the local correction The final thing is we have so far that segmentation frame by frame。

 This is a movie we need the segmentation to be coherent， consistent across frames。

 One way of doing that is basically to smoothing out。

 we have this segment per frame we're gonna smooth them out across time regularize them to make them look better。

 and I want to basically show you what happens So you see here you might be able to see that the boundaries are a bit rough here and are much nicer here We basically take the segmentation of multiple frames and we smooth them out together together。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_21.png)

![](img/5642dce5d4ed051be8e2fc8724dc1a1f_22.png)

![](img/5642dce5d4ed051be8e2fc8724dc1a1f_23.png)

![](img/5642dce5d4ed051be8e2fc8724dc1a1f_24.png)

![](img/5642dce5d4ed051be8e2fc8724dc1a1f_25.png)

From this rough segmentation to much nicer， much smooth segmentation that help us either to put this object in other movies or to do different effects。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_27.png)

![](img/5642dce5d4ed051be8e2fc8724dc1a1f_28.png)

So now it's time to show examples of this very cool technique。

This is an example that we have seen a number of times before。 So here we have multiple examples。

 but I'm going to run them now。 we have segmented out。Here， the person， it looks very nice。

 It has all the components。 It has the repair， the smoothing， everything and looks really。

 really nice。😊，Here is the example that we have seen multiple times and we see with a particular case where we blur the background。

 this is a special effect that we have seen in the past in one of the introductory videos before。

We segmented out the players， and then we put them in a blurry background to enhance the players and call the attention of the viewer to the players。

Some additional really nice examples of special effects Here we have the original one。

And there is a special filter。 you can see the lady surfing that has been filter out。

 so we first have to segment this with all the problems of splashes from the water topological changes occurring as we see here。

 once we segment that out， we can make very nice special effects like here here we change the light。

😊，In the person， as you can see， we don't have to affect the background because we have segmented the for out。

 and here is the composite that we have seen before。

 Everything starts from segmenting this very tough image。I wantna keep giving you examples。

 I think this is quite cool。 This is another example where we basically segment out the player from the background。

 look how difficult this problem is the background is all blue and white or blue and gray like the player a lot of confusion but we have shape and that helps a lot and once we segment these player out we can basically modify the background。

 for example， significantly blur it and this is also based on just the concept that I just explain to you of segmenting the foreground out for this particular。

 there is some additions on not only modeling the foreground colors。

 we can also model the background colors。All what I explain now is let's model the foreground color and shape。

 Why not to do also some learning of the background You can do that and then you get improvement in your results but again。

 the concepts are very similar and I want to give you one more example So here is another special effect where we basically take the actor here segment it out and we can repeat it in multiple positions Again。

 the big challenge here is to segment it out here there is very good basic contrast between the actor in particular with the shirt and the background so color will be very important here。

 but also the shape the actor is moving， but it's not completely deforming so the shape prior is critical。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_30.png)

So this gives us an idea of what's behind one of the popular video segmentation techniques。

 in particularly rottobra， which is incorporated inside Adobe after effect and we have seen it has many components it uses shape。

 uses color uses localized structures， localized learning both to be able to do more accurate predictions and also to make it more friendly to the user when the user needs to make corrections。

 All those concepts put together is what leads to these very。

 very high accuracy and very user friendly video segmentation。

 Thank you very much I hope you enjoy this and I will see you in the next video Thank you。



![](img/5642dce5d4ed051be8e2fc8724dc1a1f_32.png)
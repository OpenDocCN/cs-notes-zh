# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p34 P34 OpenGL -Episode 33- Camera -- first-person movement with right vector -BV1pTvFz3Eqh_p34-

Hey， what's going on， folks。 It's Mike Karen and welcome next us in our modern open GL series。

 In this lesson， we're gonna go ahead and really finish off our camera and be able to move left and right。

 Now this lesson is kind of fun because we'll actually be able to use again a little bit of the math things we've talked about like the cross product to actually implement a working camera。

 and some of these ideas of building a new matrix such as the matrix that we're building for our camera through the look at function are actually gonna to be useful in other parts of computer graphics。

 Now you'll just have to subscribe and check out the series to make sure that you see why or when。

 but this is a common idea of things that we're gonna want to do again。

 using our tool to cross product to take two vectors and get a third Perpenico vector anyways with that said。

 let's go ahead and dive in here So let's just go ahead and recompile this code again。

 just so you can see I'm just using our standard compile here of where we left off last time and I'll go ahead and give this a run here。

😊，So we can see our program from the previous lesson if you haven't seen already。

 make sure you check it out， but basically I'm moving my mouse to the left and to the right to do a mouse look and then the forward in the back keys will move me appropriately so I can effectively circle around this object and again as a brief code review。

😊，And I've got an alt tab to get out of this because I've got my mouse locked to the window。

So just a little reminder if you're following along there， but if we go into our source code。

 let's just dive into our main loop here， this was sort of to lock our mouse to the screen so we worked on that last time and then from our input again we kept track of the current mouse position so that in our camera function here in mouse look if we go ahead and check it out here let's see if I can go ahead and go to the definition nope and tell us since doesn't want to work so I'll do it。

manuallyanally here， let's go ahead and edit。Our camera。But basically this mouse function。

 our mouse look function took the current position that was coming in and as long as it wasn't the first look at our mouse because we need to store something in the previous position in order to get a delta between the previous and the current mouse and then we rotate about vector which is our up if we're going left or right now again。

 that could change if you went ahead in the previous lesson and implemented a way to tilt the camera upwards effectively that's why use the up vector here because your up isn't necessarily always your y axis again。

 think about it like on an airplane or something where you want to be able to your view direction sort of changing。

😊，But anyways， that was the main idea and then the trick was to make sure that we moved forward here。

By updating our eye position along the view direction right So if we're turn to left a little bit forward is going to be。

 you know some direction in the Z and the X plane。 Okay， so x and z need to be updated。

 Y doesn't really change here for where up is unless we're tilting up or down again。

 depends on your camera。 But that's the idea here。 So we did the same thing for moving forward and backward and critically the little mistake that I made last time。

 but corrected right， our look at or the center where we're looking at is the I plus our view direction forward。

 Okay， so that was the basic idea。 and now we want to go ahead and implement the left and the right movements here。

Now， again， if I just implement these as say updating the initial like x position by you know minus equal speed or something。

 let's just go ahead and illustrate what happens and again， why is it positive？For the。

Moving right and negative for left well ahead use right hand rule right my thumb is the X axis of positives in that direction。

 So let's just go ahead and see what happens if I do this again it's it's valid and I'll go ahead and bring in my window here。

 I'll go ahead and press the right key。😊，And it does move me right and the left key moves me。 Well。

 till the left here。 But okay， now I'm going like some weird direction。 I don't even know。

 I it is updating my X and my y。 but oh my goodness。

 I'm going forward and backward in all sorts of weird directions。

 So needless to say we can't just update the eye position here， okay。

So what we're actually going to have to do here。Is in order to figure out where we're moving is again。

 to think about our right hand rule。 And I'm going to keep doing this。 but take an axis。

 place it right in front of your head here with your thumb index finger and middle finger forming a right triangle here or coordinate system。

 place it in front of your head。 And then as you turn， keep it， you know， perfectly in front of you。

 And as you do that， which direction or which of these axis thumb index finger or your third finger are telling you which ways to the right or to left。

 Well， it's your thumb right， that's the right vector is what we call it here。 Okay。

 so you might read about this on various tutorials。 but that's the idea。

 So if I update my position based off of this vector that's going to the right。

 then I should be able to slide to the right and slides to the left。 Okay。

 just like a good dance move or something。 but that's the idea。😊，So my question to you。

 and this is something where you can pause the video and think about it。

 is how do I get that right vector？If you thought about it for a little bit。

 maybe you pause the video， maybe you didn't， but you just want to try it out。 Well。

 I know where up is in my world。 right， that's not going to change if I'm moving left or right。

 I know where my view direction is。 I've got two vectors right somewhere forward， somewhere up。 Well。

 then I can get that perpendicular vector right because forward。

 I know is sort of falling my eyes up is， you know， wherever my head is oriented。

 and then I can compute that cross product。So let's go ahead and do it， let's use GLM。

 nice library for us to compute this right vector here。

I'm going to call it that exactly the right vector because that's what we're computing I don't necessarily need to save it here because I'm computing it every frame here。

 I've got a view direction so forward and up here。😊，Okay， so and again。

 you might you' kind of have to think about this。With your right hand rule。

 as far as what order do I？Multiply the vectors in this is one of those things where we kind of want to draw it right this is what we we're working on here from the last time。

 but again， I'm building this sort of coordinate system here。

 So let's just draw a little coordinate system and let me draw it relatively straight heres or X y and Z you know。

 something like that Z positive X positive y positive and of course these all go。😊，To infinity。

 there we are and let's go ahead and。Draw our little camera here or a coordinate system right and I've got another camera。

 let's say I've turned a little bit have to think about how to So here's our camera you know somewhere in the world。

😊，Here's y here is well let me just actually draw the little camera。

 I'm going to sort of tilt it downwards or something。 Let's say we've done that。

 and you can kind of draw the axis through it。 camera right here's the X。 here's like up。

 maybe here's forward， and I know it's hard to visualize a little bit。 but you know。

 somewhere there is， you know， this right vector coming down here somewhere。 Okay。

 so that's what I'm actually computing。 So I've got up here， okay along this axis。

 I'll go ahead and highlight it。😊，Forward here， and I want to get this， you know。

 third axis that's perpendicular。 Sorry， it's a little bit messy there here。

 I'll just fill in the lines。 Actually， let's just fill in a different color。 Here we go。

This is the important thing out student read， it's that important， there we go。So here's our up。😊。

Here's our forward。 And then you have to use your imagination again。

 But these are in 3D and here's right。 Okay， so that's what I'm trying to compute。 So I'm taking up。

Or forward here。Our view。And then I want to cross it with up here。 Okay， now why that order。

 it's because we want to get the vector that's， you know， coming out this way。 Okay。

 so that's the idea。 I mean you could， you could try it experimentally。

 I suppose both ways and see if it works。 But anyways。

 let's go ahead and just take the view direction and are up vector。😊。

that gives us our right vector and then that's how we're going to update our I position okay。

 the right vector times whatever our speed is， and we said left as a negative okay。And the positive。

Is going to be when we are moving right here。 Okay， because of our right hand rule， right。

 where x positive is。 So let's go ahead and compile this。And give it a run。

And let's bring our camera in。 Okay， and first and foremost。

 let's just kind of line it up with our scene here。 If I go left， Okay。

 that's looking pretty good And right， Okay， so now I'm just using the right key。

 And I should just be able to， you know， spin around here。 I' forward and back to move along here。

 But again left， right， left， right， forward， left， right。

 doesn't matter what orientation we get in left， right， forward， back It's working there。 Okay。

 so that's it。 That's all there really is。 This is a， you know， shorter lesson in way。

 for getting our camera working。 This idea that。😊，We can just compute this right vector to move along。

 And again， this is really nice or interesting idea for us in computer graphics。

 this idea that we can recompute different coordinate systems。 In fact。

 we're gonna need this again is alluded to when we get into advanced shading techniques to compute new spaces and perpendicular vectors。

 for instance。 All right So with that said folks a couple things here as we wrap up here。

 I want to go ahead and announce that I'll eventually be putting on my course here。

 The open GL series， so it can fall along for free with my other courses and other resources up here。

 and it'll be a nice way to track your progress along this open GL series。 So again。

 I think that's something optional that you can use。

 but free for the open GL for this particular series of open GL introduction that we're doing and with that said folks。

 otherwise， hope you enjoyed this。 hope you learned some stuff here。 again， this is quite a。😊。



![](img/f6516db6bdf5fa6c9c74b81bbb4999f6_1.png)

![](img/f6516db6bdf5fa6c9c74b81bbb4999f6_2.png)

You know， a satisfying achievement， I think to get this camera working and then to be able to move forward。

 left right and back and so on。 And again， as mentioned。

 you can try to translate these to WA and D Now if you want to move up maybe the space key or something that is literally just moving the well it depends how you want to handle it。

 but you know updating the sort of why position。 You could think about that and also think about if you want your camera to tilt up and down So you have a full sort of 360 degrees look capability I suppose。

 but again， I'll leave that challenge to you folks again go ahead and have some fun with it and in the meantime。

 I'll look forward to seeing you in the next videos All right take care of folks。😊。



![](img/f6516db6bdf5fa6c9c74b81bbb4999f6_4.png)
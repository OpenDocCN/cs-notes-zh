# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p40 3_XR开发要素解析第二部分.zh_en -BV1jM4m1k73q_p40-

![](img/838279d352670ece1122d42a7a64bf35_0.png)

![](img/838279d352670ece1122d42a7a64bf35_1.png)

So in the following， I'd like to share an example our example of the Lion King 2019 remake we were studying basically we were working on a research project in my lab at the same time as the Lion King was about to come out the 2019 remake and it was so interesting to us。

 I mean we also I was just awarded a faculty award from Disney and I promised I'll do something with that research funding and I was working on this project where the idea was to really allow multiple designers to collaborate。

 be it an AR or N VR and collaboratively author actually using immersive authoring XR experiences and so we looked at a couple of examples and one of the most complex examples that we looked at was the Lion King。

And so it was very interesting for us to look at the teaser。

 the teaser had just come out and so we analyzed the teaser and we were basically using that lion king example as a case study to really learn more about tool support and what is involved in doing XR and why did we choose the lionking well the lionking don't know if you knew that but that remake was actually directed and shot in virtual reality so basically the camera man was like in there in the headset and chasing down the animals and things like that and that was how it was recorded and so it was a very interesting case study I'll share it with you because I do think it's good with keeping with this lecture we want to understand what doing XR actually involves。

So this is the Laning case study and it's from our paper， which I invite you to read on Ex director。

And I to want you to pay attention to a few things， I'll actually start at the end。

 not the beginning of this project， and I'll show you an example of a scene that we shot we were still experimenting with Rafii climbing up Pride rock。

And it was a really a vast virtual environment that we were trying to prototype， obviously。

 with limited means， we didn't have a $250 million budget。And we had two actors here。

 so we're going to do this scene where Rafii climb up Prirock and the actor or actors in this case will be Jane and the VR headset and then Katie will be our director of photography operating the camera and this is an AR capable phone and I'm going to be the director and I'm going to show you one of the many takes that we did so that you get a sense for how we worked on this little project and again I mean we are not Disney and we had a much smaller budget but I think it still serves the purpose of this lecture action。

Actually。Okay， then go back I idea。So why did I share this with you Well this is my example of creating an XR experience and using techniques more or less from filmmaking so if you think about filmmaking one more time so we have all these various roles that I talked about earlier and then how do they actually translate to XR designers and developers where the director that is usually the person in charge and if it's one man project then would be just the XR designer or the X developer in a larger more professional XR experience you might have a project lead so that might not be the same kind of designer or developer but many XR experiences are really just created by almost a single person and that person would then function in all these different kinds of designer or developer roles that I'll spell out here a little bit now the most interesting part when it comes to differences between filmmaking。

And Xr is that the director of photography。 So the person in charge of the camera is actually the user。

 And now that introduces a lot of interesting challenges， design challenges。

 It gives a lot of agency to the users and autonomy。 And that's really what we want。

 That's like one of the main affordances of of VR and A。

 This idea of being able to explore virtual content in 6 degrees of freedom and really go。

 go about and choose your own perspective and all that。😊，But from a design perspective。

 you really have to make sure that you draw the attention of the user accordingly the correct visual and maybe audio cues and all these kinds of things。

 So that's interesting challenges there。And then when it comes to the actors， well， on the Xr side。

 often it is just a designer who composes scenes of 3D models and if there are no  freed available 3D models or the designers feel like they really need more basically custom 3D models then usually you can do so and so much without 3D modeling。

 but then usually you would have to work with a 3D artist who really can create 3D models and rig them and then animate them and as I said。

 this is really a set of skills that not necessarily every Xr designer has to have another way to actually bring characters life would be through motion capture and that's actually a profession so you could do this basically these actors in a body track suit that's how most of the marvel movies out there。

 for example are being made that would be not the most costeff but very realistic animations that you would actually get out that way。

And then thinking about the remaining roles and their responsibilities so the gafferers are responsible for light。

 somebody responsible for the audio mixing sound and then the special effect designer on the XR side that would be mostly probably the X designer choosing appropriate lighting and materials so really making sure that the 3D models have the right materials and settings and textures and that's something we'll explore a little further and then also incorporating sound and again we're working with spatial sound here。

 so placing sound sources in 3D and making sure that the audio is according to the physical and the virtual environment the geometry of those which is a very interesting task to do this well so that audio would also be like occluded in some sense if there is an obstacle in between that really adds to a more realistic experience。

And then finally， especially effects， that's something that the Zonny is zone so much can do as a designer and the have particle effects and maybe shaders if you understand that a little bit。

 but most of the time you'll probably have to do scripting and so this is more the role of a technically inclined person so I say X development here。



![](img/838279d352670ece1122d42a7a64bf35_3.png)

So now I'm going to walk you through the steps of basically going to the beginning of this project and just this case study on focused on li and how did we actually work。

 So first we started with storyboarding and wire framing and this is something that I think is inherent to any exc project that I do I usually start on paper and I plan things out。

 I have an idea and I sketch those out。 So brainstorming for me doesn't happen in thin air。

 it actually happens on paper in this case we obviously we were picking scenes from the teaser。

 the teaser was available to us So that would normally just be in your head and you would try to express it on paper。

 So the way we use storyboarding and wire framing here is still relatively close to the traditional sense but we like we really figured out like what are the camera movements。

 what kinds of characters are involved and how do they move and how do they relate to each other。

What's the story and then which sequences are we going to pick。

 So that's how we use storyboarding and bio fming here。

And I'll show you a little bit of what my students and I came up with。

So here's our example where we my students and I worked on this liing remake。

 essentially the remake of the remake， if you will。

 and we had a $25 budget So we basically bought lots of physical prototyping materials， Plato。

 we did have paper and transparency and a lot of the tools and we repurposed cardboard that became then our stage and what is really cool in this way it's basically a physical storyboarding activity So it goes beyond paper it's actually very close to physical prototyping。

 in fact， you may look at this as a physical prototype rather than a storyboard but I do think when it comes to AR and VR things。

 this idea of prototyping and storyboarding physically like in 3D physical space is very。

 very important。So we had a lot of iterations here and you can see how my students。

 Jane and Amy were filming and testing and there's another person filming Neil filming them and then Katie was also in the background。

 so a cool set of students， a little bit of a film crew。

 they had to make sure that the background is kind of right。

 this was one of the harderest scenes to film where a lot of character。

 tiny little character movements and。Pretty cool。 And so。Yeah， that was that。



![](img/838279d352670ece1122d42a7a64bf35_5.png)

As we were storyboarding， you could already see more or less the physical prototyping activity。

 but I showed you the making of the physical prototypes。

 and now I want to share with you the physical prototypes。

 So this is really how a user would experience them。

 And one thing I would invite you to do if if you feel like it。

 due to copyright reasons we cannot play anything at Disney here， but I would like you to。

 if you can access YouTube and could get access to the teaser that was basically the inspiration for our work。

 and then you're going to the part where James Earl Jones says。😊。

Everything the light touches is our kingdom。 And so when you go there， then after that。

 it really starts with this really cool soundtrack。 and that's how I have experienced this prototype。

 and I usually play it to my students in my class so。😊。

I'm going to play the resulting physical prototype。 And this is now， in some sense。

 you're experiencing it was created with physical only。 So reality only， no A R V I yet， but。

It gives you a first sense of what it might feel like to be in this virtual world that we are prototyping here。

All right， and here we go。 This is the opening scene。Are we looking at pride rock。

And then rafis coming up。 This was the thing we had previously done with VR。

 and we're going to go there again， Simba moving the ahead。And。

We fy breaking that thing was one of the hardest scenes。 We had to shoot this in slow motion。

 You can see this flickering， which is just a light。And then replacing that on Zimba's head。

Walking to the top。En showing baby symbolimba。And then we have this really cool scene behind where you can see all the animals。

 I mean， a little bit abstract here， but all the animals down there。 Alright。

 so this is that example。 And these were just the physical prototypes。

 And then we were also doing the digital prototypes So we took each of the scenes。

 and we prototyped in digitally with a number of tools some of which Ill also cover in and some of the courses here。

 So we did involve unity， we used aframe and Webex are， we did some modeling and blender。

 but mostly correctionction。 Several of our models actually came from Google Poly and were done with either Google blocks or tiltbrush。

😊，And so these are all kinds of immersive modeling and immersive authoring tools。

 so 3D modeling and immersive authoring tools， and so there are actually quite a range of little technologies involved it does not look as polished somebody in our reviews called this crude programmer art and that's probably what it is compared to Disney but even this was quite a lot of effort so let let's take a look。



![](img/838279d352670ece1122d42a7a64bf35_7.png)

So here I'll show our digital prototype with scripted animations。

So it's based on the teaser and rafii is going up。 and we see Simba。 and we see some reflections。

 and you can see some differences in the quality of the models。 This was， again。

 one of the hardest things to do in 9 hour。

![](img/838279d352670ece1122d42a7a64bf35_9.png)

![](img/838279d352670ece1122d42a7a64bf35_10.png)

诶。Animation and scene。Te by one of my students。And then we're going in on the final look at the scene here。

And a little bit static。 this shot。And this 1 I really like， because you can see。

A few other animals down there。 There was a weird transition just now。 but that is the the。

Digital prototype that we created。And you can see how the camera spins a little bit。

 That's kind of nice。Yeah， it is a prototype first， it allows you to envision the final experience。



![](img/838279d352670ece1122d42a7a64bf35_12.png)
# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p12 2024-10-02 - CIS 5650 GPU Programming Fall 2024 Lecture 8.zh_en -BV1sRtresE67_p12-

来一些。All right， let's get started， I've added the slides to the schedule。

 let me know if you can't access them。So today in today's class you're going to deviate a little bit you're going to learn about the graphics pipeline as well as some forward class and deferred trade rendering options this is。

Completely separate from Kuda but there'll also be components where you'll be like hey。

 that makes sense in Kuda I can see why they did that so let's get started。

Some of you may have already learned this in other classes。

 so this might be basic but it's important that we level set everybody and today's lecture will essentially be project4 and you'll do that using web GPU so。

So feel free to ask any questions。纯粹。

![](img/429b5b49ef5202f28a4ab42b4f92c2da_1.png)

All right， so we are going to learn about how the graphics pipeline maps to hardware and to start with that graphics is a really big area。

 right。Eric Keyinenes on Monday kind of highlighted that in graphics you have modeling where you're actually building the 3D models。

 you have animation where you're animating those models and then there's rendering where you're converting what is virtually bits and bys into pictures on a screen right into pixels and lights and if you want to print it into ink。

And even within that， there is photore rendering， non photoreal rendering。😊。

Real time rendering and not real time rendering today well focus on the real time rendering part about how how do you take triangles and essentially put them on the screen。

So。From a rendering perspective， the goal is how do you you have pixels on a screen。

 how do you assign these pixels some color， how do you know what should show up where？

And that's the main goal of rendering to do that。You essentially have to compute two parts one would be。

Which sorry？Just trying to get mine。Slis up one would be。First what is visible。

 so I'm standing here in this classroom right I can see all of you， I can see the walls。

 but I can't see what's behind that wall。So we have to figure out what can I see I can see the tree through the window because it is transparent if it were opaque I wouldn't be able to see it so first is figure out what you can see and then second figure out okay what is the color how is it affected how what material is it how does light affect and so on。

So those are the two key parts of rendering。So we are going to walk through how the real hand rendering pipeline。

 the traditional one， the standard forward rendering pipeline is going to do that。そ。こ。

So here are the stages。of a very traditional old school forward rendering pipeline this is kind of the simplest form of it right and we will start with the step called vertex assembly。

So in vertex assembly， what's happening is you have certain geometry right and you have to arrange it in a way that the computer can understand and process。

So what you are essentially doing is taking a vertex one or more ver， I suppose。

And converting them into buffers that are neatly arranged。So this is the vertex assembly part。

 this is essentially kind of what you are doing in a lot of ways where you arerranging for each pixel。

Its position X， Y， Z， a normal because you need that。

And then you also have additional values such as texture coordinates， bump coordinates， etc。

 if needed。But all of that together is the data you need for any single vertex we are not even talking triangles yet。

 you are just talking about vertex which is a point。

 so what are the properties of a point that you need to send to the GPU。嗯。あ的。不知道。

So this essentially taking this pipeline will essentially take what is points in space ver disease in space。

 remember even triangles are like a human made concept in a way I guess so points in space。

And then the output has to be an image on screen or printed。

 so how do we get that so we start with the vertices。

And then we' are arranging them into OpGL as position texture coordinate binomial by tangents。

 etctera， so what are the properties of a point first？

So that's how you want to arrange it each of these are。

A vertex will have at least one of each of these right so that's what you' are arranging and that's assuming no indices of course if you do indices and stuff it gets a little bit more data but essentially bottom line is that you take the properties of a vertex and you're arranging them so that the GPU can read it。

こ？So I spoke about that anybody know the difference between a binmal and a byte tangent？喂。

Very really。Basically the same thing， but they're four thousand each other。

Yeah so by tangent is a tangent by tangent is tangential to the surface okay so it and then by normal is a normal that is normal to both the tangent and the normal so if you think about your x y z coordinates on one axis you will have normal one axis you will have by tangent and the other axis you will have by normal。

是法。And。Is bi normalmal called no， there are three different things， there are three different axes。

So。I think by tangent， so tangent， let me see if I can draw it。And again， I maybe。

So if you have a circle， there's your tanggent， right？I think what normal would be。

 let's say this way。Okay。The by tangent would be like that。So normal is coming out。My tangent。

And then your bi normalist like that， so it's like。Paled to the surface， in a way。

If you want to think of this as 2D。And then you have the normal coming out of here。

 so that's one way to think about it。是个。什是。叶酸呃。Yeah， so this first tang that I drew is in 2D space。

This could be， I could draw it here as well if if so that I'm not confusing with parallel lines。The。

You can put a three dimensional axis at any point right so if you are putting a three dimensional axis at the center and assuming the circle is flat or let's say a triangle then what are the three axisxes so normal by tangent and by normal would form those axisxes。

Okay。Anybody know what these access can be used for？Or when you might use them。Nick。

 and I'll come you guys as well。s normalormal mapping， anything else。Yes。好。Yep。

Yeah exactly they use for normal and pump mapping most of the time。

 so any anything that needs work in the tangent space would you ever want to store all three？喂，呃就。

Yeah。倒し。was fine but like for space efficiency exactly So remember these these kind of concepts apply from code as well。

 right computer is free。 If you store two axes， you can always compute the third pretty much for free。

😊，Okay， all right， so any questions on vertex assemblies？

So you kind of have vertex 0 and then vertex 1 will be offset and so on。

So no other questions on wordex assembly。Okay。So now from vertex assembly what we do is the vertex shader now most of you have probably written a vertex trader in 460 at some point or a previous graphics class and what we are doing here is essentially。

Transforming a vertex position。Into from model two clip coordinates essentially so you're going from a local coordinate system to a global coordinate system and that's what a vertex shader does。

 the reason it's a shader， aK a Kuda kernel you know they derive from the same ideas right lots of data running in parallel。

 the reason it's a shader is because。You can compute all of these in parallel。

 every vertex is kind of independent of every other vertex。

 so they can all run in parallel and that's why GPU is great for that。嗯。

It used to be called transform and lighting stage， anybody know why？

So the transform part is probably obvious。Because it's transforming the vertex。

 why do you think the lighting was in there？有。这个对。Sorry， you could do。like you do lighting。对。

Potentially， yeah， I think that could be one of the applications。No。Yeah。

 so but deriving from that idea， the reason it was called lighting as well because in double sided rendering。

 you could figure out which direction of a triangle is pointing towards the light。So but yes。

 apply that drives to the idea that you said。嗯。Okay， so， so input to the vertex shader is。You know。

 get you get the vertex and you get the modern matrix。

And then you convert that into a modified version。any questions on this。

 anybody not seen this in 460 or haven't written quote about this in Open GL？

I'm happy to go to Eba okay you， but ask questions here if it doesn't make sense。

The it why is it cold？Because you are going to put it on in the normalized coordinates。

So and then you'll be clipping them so this first going into normalized coordinates and then we'll figure out what what's actually visible。

 what's within the screen， what's not。嗯。Any questions from you guys， Dominique？No， okay。All right。

To come back to the next question。So wordtices， let's say you have a cube， you know that's one unit。

 you're usually going from zero to one on each of the three axises， right？

So that's a model coordinate but that cube could be placed anywhere in the world right and I mean in the virtual world here it doesn't have to be on the origin of the virtual world even though the vertices might say 000111 it can be placed at 50500 if you want to so thats why you need to convert what a vertex is in local coordinate space into global coordinate space and then from global coordinate space you need to figure out okay where is my camera if my camera is the origin where is the cube in that scene so that's why you have。

Model to world， so you're converting the model matrix into the world matrix into the world coordinate system。

Then from the world coordinate system， youre converting it into the eye。

 which is the camera kind of like what you're doing with Pa tracer now。😊。

And then once you have the view at the。Camera position。

 then you have to clip it into normalized coordinates， which is0 to 1。

 so kind of like your screen and you get the projection matrix from that。

So there are three matrices that you use for this， theyre called model view projection MVP essentially and you can combine because it's all4 by4 matrix math。

 you can compress these into a single4 by4 matrix and just send that to the GPU so that's why we have the three matrices broken out here but if I go back to the previous slide you just see one getting input here so you have just the model view projection matrix here。

Questions about this。Okay。The other thing that youll put in here is also any uniforms and matrices。

 so of course the model view projection matrix would come in as。A uniform as well。

Uniforms in shaders are constant memory so you remember kuda kernels having constant memory uniforms use constant memory in shaders because they are constant they read only and theyre the same for all the shader threads so that's why you can use uniforms here。

I'm sure you're starting to see a lot of parallelddles between QudDa and something like OpGL now。

Questions on this。어때？All right。So once weve this is kind of the view sorry I sure haveve moved to the slide right so to first convert let me just cover it virtually as well。

 so you want to cover convert，The view matrix into the world matrix， right。

 so that's where you take the。Cler position。And you make。Everything oriented to the camera position。

 so now camera becomes your origin， so you're taking a look at it from from the camera's perspective。

 so that's first step。And then you do model to world。

 which is kind of like where I describe the cube can be anywhere and you can take the local vertex coordinate into the world vertex coordinate。

And then finally you do the clip projection where you're taking what is the camera seeing versus what is going to be on the screen so you can have an orthogonal projection where everything is parallel。

 youll get something like this， but if you do perspective projection which is what our eyess and cameras do you're going to have more of a thrust right so it converts it into that thrust。

 things that are further away in the distance will appear smaller。

 things that are closer to the camera will appear bigger。So those are the three main steps。

And here you have in combining them into one。Questions on this。能呢？こ会こめ。

So the  four by four matrices because you need three by three for rotation。

You need three elements for translation。And then you need three elements for scaling along each axis。

So this is called homogeneous matrix and computer graphics， so if I kind of draw it and。Again。

 students in 46 please correct me if I'm wrong because I don't always remember this or I don't do this every day。

So that's rotation。So this。This scale， right？And no。The thing that rotationSo this this scale， yeah。

 rotation and scale， you're right， and then column translation one bottom。

 and sw zero you could use this for Skew， yeah。So yeah， basically this is。

Like when I learned this for the first time in 460， Nomala was teaching this I know， yeah。

 Nomale and Steve Lane were kind of teaching in parallel。

This kind of like a bit of magic path about how beautifully it works because you can divide it up in all different ways。

 and that's why GLM， the library that you're using works so beautifully with through， you know。

 three by three， four by four matrices as well。😊，And when you do matrix multiplication like that。

 all of these properties do get preserved， so if you have no translation that'll be preserved if you have no rotation but only translation that will be preserved as well so it works really really well。

Other questions on this？Okay， I have a quick demo to show you from our friend Anna Keynes from back in the day。

 hopefully it still works。All right， it does。So this is a very simple demo that shows。😊。

This kind of translation rotation scale。We we have a world space point so this blue point is what we are counting and it is in some world space and we can move it around and as we are moving the camera you can see that the view stuff is moving。

 not the original points， the view is moving。But if I。Let's see how， how do I track this。

So here I'm just translating right I'm not rotating so you can you can see only specific things changing。

But if I were to rotate， then you see the whole 3 by 3 matrix rotating from there。Why is to s Mo。

Watch matrix。Go to do on， Oh yeah。Good call so I can move the x and y here。So。

 you are seeing how if Im translating how only this value is changing so this is x y z of translation。

 so pay attention to the top right this border matrix here。

Only x is changing only y is changing only z is changing now if I rotate you will see these values rotate。

This for why。This foruzz the。And then if I change the scale。

 all of those will rotate so let me turn the rotation back to zero。

And the diagonal will change for scale。So yeah， player under this demo if you want to understand this model view projection matrix mode。

 it's linked in the slides， so this transform demo is linked here。Okay。All right。

You can use the model to clip coordinates for transformations like bump mapping and stuff。

 but you can also use it in a time dynamic way， how would you implement something like pulsing like this？

Like you have a model and you want to make a pulse， how would you do that？

So you don't just think you have to think about shader at one point in time。

 you can think of shaders in time。Good ahead Nick， just do this place as a function of time maybe some。

Yeah exactly so so this is some like again you don't just have to transform the transform the vertex along those along what was the input。

 but you can tweet the input as well So like Nick said you want to take。What is the vertex？

And actually move it along some function， right， the pulse is the function。

So what kind of function would be helpful to do a pulsing operation？

And compute sorry sign is pretty good， so something like this right where you want to have a displacement along each vertex so you're going to add in a direction。

And here is a simple equation that is 0。5 time sign of a timed uniform。

 again time can be uniform because it's same for all war disease right and then you add one so what is the shortcoming of this equation？

What's like the limiting factor here？What if you have a really big model？Yeah。

Have you have a realistic model。It's not going to be very noticeable with history。

So think about the amplitude for this display function， 0。5 times sine goes from negative 11。

Today is not a great thing so basically the displacement will be between0 and  one for this function。

😊，Which is not a lot you are going to have if you have a model that's hundreds of meters you know one centimeter or one whatever unit you choose is going to be really really small so let's add some scaling factors to that so we can have a uniform scale that scales for all。

All of the word sees but。What's the impact here， what's the shortcoming？

So we said one might not be too big and Nick，'s you ideally want your skill factor to be like some kind of function of the size of your model at the first。

Potentially yes， so here if you have a uniform scale for a lot of different types of models。

 it could either be too much or too little。So what we want to do is get like a varying bge right so to do that we can have a function like this which is scale factor and then we consider the y position in x and y and multiply that with some kind of frequency to get a bulging operation so we dont don't just want it to bulge in one direction we actually want to change over time right so we can add a frequency to that signine function as well so just just an example of。

How you can do these basic things with a vertex shadowr。All right。So in this。

 anybody tell me what changes per vertex and what doesn't？So only position changes per vertex。

 everything else is essentially a uniform。So again everything goes into constant memory。

 so a lot of things can be pre computeuted here like for example。

 the scale factor can be multiplied by half before the frequency and new time can be premipplied so you can save a lot of compute that way。

So。The other thing a vertex shader can do is read from textures。

Right so now if you have been adding textures to your path tracer。

 how do you think textures are useful for vertex shade verex vertices are 3D points。

 textures are 2 d images but。If they're available， they can be used for something right so any ideas on what they can be used for？

好。Yeah。Right， yeah， normal map， bunks map， other ideas。那就是。Yeah。

 you could use it for animation as well。人呢？This短。Yeah good all good ideas so so he here's like an image of things you can do so you can have displace map for water and stuff like that so it becomes really really powerful a few more demos here from back in the day that you guys can check out all done using vertex shaders there's everything' is happening at the vertex level。

So that's all for what actually does， let me pause and take any questions。YeahM。

Rand monkey random monkey used to be like。

![](img/429b5b49ef5202f28a4ab42b4f92c2da_3.png)

A demo tool is like shader toy or something like that， yeah it AMD doesn't host it anymore。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_5.png)

So it used to be kind of like a shader toy， 3Js kind of thing for the desktop here。

Basically these demos were a ball bouncing， the morph was kind of like a screen saveer type thing where the balloons would become smaller。

 bigger， negative， positive， that kind of thing particle system was like fire coming out of the Utah depot。

Okay， all right， any other questions on whatex shadeder？All right。

So let's talk about primitive assembly then。So remember， I said vertices are points in space。

 they have no concept of O and part of a triangle。Or I'm part of a sphere or anything else。

 so primitive assembly is the operation。Where you take。Three points。

 essentially because you want to work with triangles and one by one。You。

Transform them using vertex shader， but now you convert them into a primitive assembly。

A primitive is。We don't say a triangle assembly because there can be other types of primitives。

 lines for example， or fans and others， but the most common one of course is a triangle。

 so we essentially take all of these points and convert them into primitives in parallella。

And that's when you get an association of， okay， this is now a triangle， or this is a line。

 and that's the main function of the primitive assembly。嗯。Questions on this。

So one thing you guys haven't asked is。Where does primitive assembly happen because you've never just in a primitive assembly shader？

Right？So these kind of functions are all called fix function。

 theyre happening on the GPU itself using the pipeline。

 the graphics pipeline has these steps built in and will'll run them for you。Other questions？Okay。So。

Then we kind of get into what needs to be clipped and stuff so remember when we said we go from model to world to view and clip now we need to actually figure out whats on the screen or not right our screen could be infinitely big our screen could be very very small so what is actually being seen in the screen so that that's kind of where we get here。

So here's an example of clipping， you know you can have triangles all over the place。But。

When you actually are drawing。The real time renders on the screen。

 you want to do the minimum amount of work。In the fastest way possible。

So to do that you want to figure out what is visible versus what is not。

 which is again one of the you know conditions we wanted for rendering so clipping does that for you。

So in this case we have these three triangles。The red one is completely out of the screen。

 so that's going to be ignored。The orange one is partially in the screen。

 so here the GPU is going to clip it essentially and then create two new vertices and it may teslate them which is to say create new triangles from there as well to do the computation。

Tppping can sometimes happen sooner at the time pipeline。

 but it really depends on the GP and the hardware。Questions on clipping。

The other thing that happens here is also determining what pixels overlap and this is really the rasterization part。

 which is fixed function again。In drasticization， what you're trying to do is from when you have many。

 many objects in a scene， some objects are going to cover others。Sometimes partially。

 sometimes entirely and again， when you want to think about doing the minimum amount of work。

 this is again an area where you can discard certain objects。So in this example。😊。

You want we have two triangles， one is blue and one is red。

 and the right side of the image is kind of showing what that might look like in pixels。

So anybody want to guess or think about how this would actually be implemented if we were to do this as a software render？

Yeah。每天是10。Yeah you could you definitely need the z value to do the comparison of course one thing you have to think about is these images are in 2D what happens if the triangle is like crossing like that right so in some cases parts of one triangle might be ahead in other cases the other parts of the triangle might be head so if you have like if I'm。

Using my hands。You know， the the overlap can differ based on what。

3D representation of what looks like。嗯。Anybody think about aing？

All of you are doing anti heliasing in your pathway raised so how can aliasing happen in a ra riseor？

Ohello。さ考か。Yeah。我可以刷一，其下我可以再。嗯哼。😊，嗯。그냐 근데。Yeah thats that's absolutely a key point there if you want to antiallias real time rendering you then you have different techniques where you can increase the number ofs pixels on your screen or other concepts where so that's called。

That's called multisle and haing right where you're kind of fake digitally creating the screen bigger and then you're going to compress and take averages so that's one technique there's also FxAA which is much more rasterizer friendly where you're not scaling up the amount of work you're doing but you're doing it using other techniques。

嗯。So yeah， here's an interesting question here。哦。These two。

 what happens to non position vertex attributes during rasterization？

Which is to say if you have normals， what happens to the normals？And what happens to by tangents。

 for example， we were talking about before。Any thoughts on that？哦。Yes。Yeah， exactly。In vertices。

 the vertex is here here and here and here and here and there， right there is no vertex here。

 but if we are clipping。😊，Now we kind of have to do a fake vertex in the middle。

So how do we compute that， how do we compute the color of that if our triangle。

 let's say it wasn't already， it was red， green， blue， and it was rainbow in the middle。

How could we compute that and that's using some form of interpolation which can be defined by the user and that's going to be used for the coloring there。

The last question， what is the triangle to fragment ratio is a very interesting question and I think some of you are going through that now with your path tracers。

So let's say we have a cube， just a cube that we are rendering。

 what do you think of the triangled fragment ratio there？And on how big your view is。No， does it？

Does it depend on how big the cube is？So。The number of triangles in a cube。Constant。

 right let's let's say it's 12 tris。That's constant。How many fragments do we have？

Let's say we have standard 1920 by 1080 screen。That's like about 2 million， right？

So the number of fragments remains constant and if you have let's say just a cube。

 then thats constant as well， so it doesn't matter what size you scale it up to。

I think Nick what you may have been thinking about was。

The the pixels to triangle ratio of coverage on the screen and thinking I'm asking the question more from a compute standpoint。

How does the compute for the triangles required compared to the compute for the fragments right so what do you think in the example of a cube？

Small， right， like it's very fragment shader heavy。

You have a lot more fragments than you have triangles。Now let's flip that， let's say you have a very。

 very complicated scene， you know， like the manite ones or others where you have billions of triangles。

But again your screen size is just 1920 by 1080 about 2 million pixels now thats a very different compute paradigm where your vertex shaders。

I have to do a lot more work。And your fragment shaders are going to do the same amount of work。

The reason I bring this up。😮，Is because that。😮，That kind of compute disparity。

Was the reason Hua was formed？Because pre coa。😮，Every GPU had dedicated vex shaders and dedicated fragment shadeds。

 and well see this in some of the future slides to come about how offset that weight could be and could be optimized for different kinds of purposes。

嗯So。In the general kuda sense。All the kuda cores that we use for compute now and have been using so far can be used as both vertex and fragment shaders as well as compute shaders and others。

 and that's why it's called the unified device architecture。

 compute unified device architecture that way they don't have to select or do we dedicate 50% of the transistors to vertex shaders and 30% to fragment shaders or the other way around they don't have to think about that anymore。

O。Any other questions on raization？How many of you have written a software Raizer， I'm curious？

All right， O。Or is that now in  force60？😊，K。Back when I was a student we did a Kuda Ra。

 that was one of the coolest projects， not as fast as Open G， but it was really good to implement。

In GPU class。 Yeah， so we did， we did scanline and stuff on the GPU。 So if I remember correctly。

 we paralyzed。Per ro， I think， so so was we are very very fast， but of course， not as fast as OpenG。

So if you guys are interested， that could be a really good Houda port in your own free time。咩。

So compared to Kuda， like let's say you did a rasterize and Kuda。

 you're writing all of the software yourself。The reason openGL becomes fast is the rasterized on openGL is going to use fixed function hardware。

 there's hardware dedicated for that， whereas youre writing coulda code with ifs and for loops and whatnot branching essentially whereas on the hardware。

It's optimized using transistors， so that that's why open if you write the software anything。

 it's never going to be as fast as dedicated hardware。好。没。

They're olderer companies sharing the same like they know they all share the same hardware or is the Harvard specific to？

Yeah， that's a really good question， so I would say it used to be。😊，Now if you think about it。

What does a normal KudDa GPU have， it has Kuda cores。Does tensor course？

And it has great chasing cores， so now we went from again I'll have slides later。

 but I think it's worth talking about you go from in the 90s where you have nonprod with GPUs。

 everything is hardware。😊，To。some things are programmable， like the vertex and fragment shaders。

To Quda where everything is programmable。But now you're going back to saying hey I need faster matrix multiplication。

 I need faster reinterction tests so I'm going to create dedicated hardware for that。

 so it's all a tradeoff between how many transistors can you fit on a GPU or CPU any chip。

 what can they be used for what's the best bang for your buck there in addition to other things like energy efficiency cost and things like that？

Yeah。は。Other questions on drasticization。어때？All right， so then once we know， again。

 about think about the original problem。For real time rendering。

 you need to know what you can see and then you need to know what to color it。

Once the rasterization step is done you know what you can see right you have what's on your screen you know the exact pounds of it so now you start to think about okay how do I color this so the reason it's called fragment is instead of pixel is because that's how the GPU is going to think about it。

So the most common thing to do in fragment shader is。

To compute the material and the light and what effect that has。

So here in the simple diagram you have。A fragment coming in， which basically is a pixel。

That comes in you also get uniforms and textures for the materials and other information and what you get out is a color of that pixel。

So。Fragment shaders can be computationally more expensive because they are doing a lot more compute。

 whereas in vertex shader， the most common thing you are doing is transforming the vertex using 4x4 matrix math。

 which can be really fast on the GPU。Here you're going to do a lot more texture lookups。

 lighting math， checking if some if you can see the light or not。

 so that way tri and shade is a lot more heavier。Question here。I'm saying the fragment is the input。

 but what does that mean comparing to the ver x shader position is input so you have position X Y， z。

 you have a normal， you have other things， what does the fragment input mean？你这不。然后。

Whateverever they。So。Yes。But what is purely the fragment part of it？

Right exactly so the fragment is represented by the window coordinate so you get an xy as well as a depth of your normalized screen coordinates。

 that is your fragment and then you get the output of the ra riseizer and the vertex shader where you have what interpolated coordinates and which pixel they are going to be seen on。

The other questions here， what are some examples of useful uniforms in a fragment shader？

What are like some of the most common ones？嗯。Screen dimensions， yeah， what else？嗯。嗯。

So that would go into textures， right， what are common uniforms？Tex sampler can be uniform you。

Time can be a uniform if you're doing any time based thing。Naniel light direction， yes。

 absolutely light light is a big one Okay， what example of textures。😊。

Useful textures in the fragment shader。Next Aldo，Otherre those？Then。Roughness。

 potentially some materials， yeah。So other examples would be。Along with Albedo。

 you can have a diffuse map， a bump map， you can a specula。

 you can even have like transparency maps and other things there to help with that。Okay， so look。

A simple lighting equation， the most common one of course is blank Fong where you are going to use an equation like this。

 basically what you're saying is。If any point on the screen can see a light。

 then shade it based on its dot product， so that's what you're doing here。

If you want to do specular and again you guys are doing path races so you're doing real specular right but in rasterization everything is kind of fake so to do a fake operation like that what you are essentially doing is taking that and multiplying it by the power。

😊，Off。😮，How。Closely does the normal and the shine align to the light。

And then the power that by the shiness so it's a very shiny object it is going to look more white if it's not a very shiny object then it's going to use the normal color。

Qu that's written there， why is it not evaluated per vertex and interpolated during rasterization？

Any thoughts on that？They said， you have an idea？If you you have some kind of like fall out。おなな。

exactlyactly， so just like we saw with the pulsing example in vertex shader。

 you could do other things in the fragment shader where you're applying a bump map or you're changing the normal to compute a different light color so that's why it's not done in the vertex shader。

So here's an example。Which is per fragment lighting and which is per vertex lighting。So。我意的。

The one on the right per vertex， yeah， this one。Yeah。

 this is per vertex the reason you can tell is the amount of spread。😊，is much more in a vertex。

 especially on a curved surface， that's where you notice it。

 you also notice that the lines are pretty much aligned to where the light is whereas in a fragment you are going to get a much smoother operation because you are going to get that interpolation to get you better lighting。

Here's an example of texture mapping， which I think some of you are doing in your path tracer as well right。

 really simple take an image， use that image to color your 3D model。

You can also do other things like lighting and mapping there combining those two。

 so we have a lighting model。Or lighting image， if you want to call it that。

 you have a 3D model and then you can use that for lighting globe in this case。

Here's an example of bump mapping so let's say you have a map of the world and then you have an elevation map of the world that's just how high is something on the world so you can take that and this is flat shading essentially and then you can apply the bump map so I'll go back and forth especially look at this top corner here you'll notice it become dark so this is bump map。

This is not bump map。So you can clearly see the difference about how it makes a change。

 you' are not moving any vertices here， right？In bump mapping， we are not changing any vertex。

 we are not adding more computation on the vertex side。 all we're saying is。

Use a different normal as of the point were moved， and that's where you get this lighting。

You can also do specular maps， so specative you know adding shininess。

 you can add that to the fragment shader so areas like this up here。

 this elbow that you're adding more specular lighting you're faking it。

 but it looks reasonable enough or has looked reasonable enough until recently until ray tracing came around。

You can also do you like to helmet with lights and realistic things。

 I want to do photo non photorealistic rendering so you can do that as well in fragment shaders。

You can do reflection mapping and environment mapping so the environment here of course is a texture so you're going to think of the world being got inside a box and then anything that's not the object you're going to query the color from that texture and put it around that but also。

Use it for reflections so here you can see in the in this teapot how the reflections of what might be the other side of the world are getting reflected。

Okay， so more examples， you can do fog。So fogk would be done by the Z distance and you can do that per fragment。

 so essentially youre adding some gray touch to it if that point is really far away in the distance。

 but if some point is close to you in the fragment shaded depth。

 then you're not going to add that much Z to it。So here's a question for you guys。

A fragment shader will output the color right， but what else can that be actually used for？咩。こ the。

Yeahep， you can have depth， yeah。The color can like also have the al value over。Okay， so colors。

 depth， what else？I guess if you're doing some kind of。might want to have。

yeah so I'll just put normals under more colors because youre outputting colors to a texture and stuff like that and the other thing you can also do is discard a fragment you can just be like no I don't care about this fragment I'm going to ignore it。

嗯。So the reason you may want to discard is because you may have some form of color key。

 so let's say you want to see only object the colors that are red。

And you want to ignore everything else， you can ignore it based on that you can potentially do cross sections。

 so especially in like scientific rendering， you want to render a brain right and you want to。

Chop off the brain in half virtually and see it and see the cross section you're just going to you're not going to discard the triangles you can discard the fragments in that case。

You can do holes， perforations， et cea。That buffers for Z buffer shadow deferred rendering and multiple colors。

 of course， for textures and multiple render targets。Here are some fragment shader examples。

 let's see if this link still works。走。Let me copy that link correctly。

It's not copyIt's not letting me copy this link correctly。

 but you guys can look at the slides and run it if it works。

But it's just a demo of how the fragment shader works just like we had for the vertex shader。Okay。

So once you output all of the colors， so we went from vertices， project them。

 see what we can see through the camera。Figure out what the colors to put on the screen are。

 but then you have some per fragment tests that you can also run what are some of these tests and what are they useful for。

용환。You have a depth stress， of course。Anyone else？So in the traditional pipeline we had three types of tests。

 scissors test， stencil test and the test test， anybody want to say what these might be useful for。

Look。I mean， sometimes there's just。Good reasons to mask out like some particular area where you don't want to put something in what's an example classic is the outline shader where like you know this me call your geometry slightly bigger with with a vertex shader sorry slightly smaller with the vertex shader and then use that to generate like a sc。

Yeah， soll let's go to stencil and then come back so the stencil shader is literally you know。

 all of you have probably use stencils at some point it is。Getting an arbitrary shape。

And only rendering or not rendering those fragments。 So that way you can control。

Not always having to render the entire screen at the same time。

 you can use a stencil for an arbitrary shape。So here in this example so we have。

 let's say a color buffer and then we have a stencil buffer that only has ones in a certain area including a hole and then the rendering for that would only be in that area all other fragments would get discarded。

So coming back to the scissor test， scissor test is similar。

 but its more like you can do it more on a rectangle。

Rather than have these kind of holes and stuff a stenr test is more powerful and more arbitrary。

 a scissor test is much more rectangle and oriented to the screen so you are going to either say hey I want to render only one quadrant for example。

 let's say you want to have the albedo， the depth texture。

 the normal texture or render on the scene at the same time and you can use the scissor test to do that in four different quadrants without having to create four separate screens for that essentially。

嗯。The reason we have this result as being special is because it's much faster right instead of having to do a general purpose tenscil。

 it's much faster to do it for multipass rendering， post processingces effects and stuff like that。

Sttencil test we already covered and then for depth test。

 we can figure out visible surfaces from this。It was once upon a time， a long time ago。

 it was called ridiculously expensive。That's because。It needed a lot of memory， essentially。

But what happened was。Whether you call it Moores law or anything else。Compute became cheaper。

 bandwidth became cheaper and now nobody even thinks about it being expensive right so essentially it's allowing you to figure out what is which object should be ahead of the other。

Here's some examples of depth testing， so we have the shading being done using depth。

And this can be applied to something like a fog where in the fragment shader。

 things that are further in the back are more foggy or more white。

 whereas things near the screen are more gray。The one thing to remember about depth stress for those of you who may not have written the rasterizer is that depth  zero is basically the screen。

 depth infinity or if you normalize the depth1 will or minus1 depending on your axis will be the far plane as we call it so you have a near plane and a far plane。

O。Finally。You have blending。So blending is essentially how do you combine？

Different fragment colors within。Within the or after the fragment shader。

 but before the frame buffer gets executed。What is the main reason to have blending？嗯。

Absolutely transparent materials so basically you can do either additive blending or Alflow blending using this and again you know modern day GPUs you can do this programmable but again back in the day of the traditional openGL pipeline all of this would have been states and you would be passing this using APIs to something like openGL。

Here's another example of alpha blending where you have to sort which object is ahead of width。

 so here again you know comparing the previous example。The red is behind the yellow。😮。

But the fragment shader doesnt know that without knowing that the z value of each of those fragments。

So you need those to be able to sort the alpha blending out。Any questions on this？Okay。

So after all of that。😮，We end up with an image。So we've gone from verex assembly where we had just points and we arranged those points into memory。

Use the vertex shader to transform them into world space and then Can space。

Primitive assembly tell the GPU which vertic make up the points because you don't have to have consecutive vertices to make up a point those vertices can be randomly placed in memory and you have to say which vertic make up any triangle so thats primitive assembly in the rasterizer your computing your clips about which triangles are visible and which are not and then finding which pixels from those triangles are available fragment shader your computing。

The lighting and the materials for those visible fragments。

Then you do per fragment tests where you' are either checking or discarding different parts of the fragment and then blending for any alpha blending such as transparency to finally get the output image。

Of all of these steps， which is the most expensive one。😊。

Or which is most commonly the most expensive one， Let me put it that right。开始。

Yeah most most commonly it the fragment shader that is the most heavy so here we have this was from this leg down here。

 this was a comparison of the different shader times for these games of fear year of4 and half life2。

Again， this is from an old paper， but I think it represents the material really well。

So you can see how。In these here's the average time breakdown and that chart shows the average time spent in the rendering stages for 25 frames。

嗯。So you can see that fear。Was a lot more pixel shader light in a way， at least relatively。

 but pixel shading was still the biggest part of it。And Fo also used the rasterizer a lot more。

 so it had a lot of competing triangles per se， whereas of life years of war and half life too were very。

 very pixel shader heavy， almost like if you just ball pocket it you're probably talking 70% of or more。

 right？嗯。If you look at the right side。Which is。嗯。The percentage breakdowns across frames。

Then you're still seeing how pixel shaders are the most heaviest in fear。

And the rasterization can vary depending on which scene you're in。

 depending on how much geometry there is。Any questions on this？Okay。

So let's talk about the evolution of the graphics pipeline and this was kind of where I was hinting before。

 right？

![](img/429b5b49ef5202f28a4ab42b4f92c2da_7.png)

So early 90s， this is the error of。Wolf 3D its software and all of those where they are taking PC games and building software raization engines on that。

 so all of these are like interactive software rendering that no such thing as the GP at that time even the CPUs were barely powerful enough。

So you have this kind of。If you notice these while they're amazing games， there's no ceiling。

 there's no floor。There's no height changes， it's all flat， there's barely any walls。😮。

And there's no lighting， if you look at wolf， there's no lighting。😊。

Its all it's all fake textures look at the two pillars on the right they have the exact same thing going on they also have pre computer texture coordinates and things like that。

😊，A year later and this is how quickly graphics was changing at that time right。

 Doom had BSP3 so it added texture mapping for all of the surfaces， added some lighting。

 also added some floorral altitudes and stuff like that。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_9.png)

So why do we want GPUs right this was this kind of came about you know later in the 90s。

 early 2000s and the reason is to exploit that parallelism。There's parallelism in the pipeline。

 there's data parallelism in things like pixel shaders and fragment shaders and you can also potentially do CPU GP parallelism where the CPU does something while the GP is doing other things and you can use that the other reason GPU came about was for the fixed function hardware like texture filtering rasterization alpha blending and even of the compute site multiply an ad mad essentially is one of the most common operations you do right like think about all of the block IDX times block 10 plus thread IDX you're doing that's a multiply and ad operation so to be able to do this on the GPU using fixed function hardware is really really fast。

So， on。In general。Something like the Labi， how many of you know what the Laray project is？Or was。

So the Lay project。This is how far weve come when MDD and NVD were really I mean they are still in the hes of the GPU。

 but when GPUs were big and Intel was trying to compete，😊，They had this， let's just say。

 wonderful idea。To say， hey， I'm going to shove。A very very large number of X86 cores to make my GPU right whereas if you think about KUuda and even AMD。

 the cores as they call it are very very small their lightweight。

 they do compute really fast whereas X86 is more general purpose and they try to put that onto a GPU chip and call it project lay so it was much more general purpose but also 12 to 40 times slower on most of these common operations。

So in 1996， you start going from software render。Which is what Wolf and doom and other games use。

To the first what could be called video cards essentially right where this was a 3D Fx voooo and it kind of divided the pipeline up into youed all of the vertex stuff。

But this video card or the GPU took care of the rasterization and putting all the pixels onto the screen。

 and that was all fixed function hardware。嗯。And then。You have something like this Mayo card example。

The question I want to ask you。Or maybe more suggest is what do you think of the fragment versus word explode here if you see a screen like this？

Wch one do you think is higher？설。Yeah so this has way more fragments and less vertices。

 lots of colors， lots going on but all of these are probably very very small objects so all of these boxes can be like a sprite or two triangles the walls are flat so the vertex load is a lot less and the fragment is load is more。

What about something like this on the V， so we come from Mariioar 64 to Mariioar on the V。

 what do you think of something like this？On the fragment invert X here。

It's probably still like higher。Yeah， exactly still still very much high fragment load。

 but now you're seeing the vertex carboning trees to get more realistic objects in there。

So I show these two images to motivate that。Over the years， has computers become available？😮。

GraicGraphics developers， modelers， animators have always put more and more information on the GPU and tried to push the boundaries。

So then in 1996。The G4 256 came out Nvidia's first major card along this line and what it did was it made everything in hardware so we went from Doom where everything was software。

Two 3D effects where it was split， and now we have everything in hardware。

So it had fixed function verex shading， it had bump maps and like maps but it was all in hardware so you just told it what to do and it did it for you that it wasn't programmable very much and for that time it was really really fast like 10 million polygons in that age was like crazy。

And those of you who are your own computer builders and stuff。

 you probably don't even recognize what the sport is。

 this is called an AGP it was pre PCIE so not all of the computers but I remember I used to have a computer that didn't have a PCIE and my neighbor or cousin or somebody got a graphics card。

And then we would buy games that required a graphic card and I couldn't play it on my PC and that was like those were some of the most frustrating years of my life。

All right， so we go from G4 256 to G43 in the early 2000s。

 which is where the traditional openGL pipeline came about where most of it was hardware。

But then you got these programmable stages。So you could essentially program the vertex and fragment shaders in there。

 and that way you added many more options。The other thing， and then in G46 in 2004。

You added textures into wordex shader again you have to remember that all of these features that we take for granted on a GP weren't a thing back then everything had to be added one by one so。

If you think of this。Textures in what shade is less than 20 years old。

So that's like those kind of things blow your mind about how far the graphics industry has come recently。

SoYou could say that yeah。You most of you are probably not as old as doom， but yeah。

 texture is in vertex shaders yeah。嗯。So so this was when you know NviDdia started really pushing the boundaries of the GPUs and putting out images like this in their marketing material。

 so you could havetex vertex shaders that could read texture so you'd do displacement mapping。

 you had dynamic branches again， if statements weren't a thing。In shaders before 2004。

Right so you can have branches， you can have multiple stages and so on。

I think I covered this all right， that's an interesting question then how does this relate to war partitioning in Kuda？

So for best performance。Your fragment shaders。Should have been coherent in screen space。

RightSo that's the statement。How does it relate to war partitioning in Kuda？Yeah。那就说一。

Maybe each fragment like gets one。This one break。Yeah so so that that is kind of the motivation so you have to think about Kuda coming after all of this right so Kuda was inspired from this and before Kuda was around that's exactly what they were doing one thread。

😊，was doing one fragment and then neighboring fragments。

 you wanted them to have the same branching conditions。

 you didn't want them to diverge and that's where the concept of warp partitioning and one warp comes together。

So now you start to see the parallels as we get closer to20 as we get closer to 2007， 2008。

 you start seeing how。Graphics of that time。Inspired kuda。So here's the graphics chip on a G46。

And remember how I was saying you had to choose between where you dedicated your transistors。

So you had some up there for vertex processing。You had all the green stuff kind of being more fixed function。

 you had some memory for your textures， you had a bunch for texture and fragment processing。

 and then you had a bunch for Z compare and blending。And then you had memory。Right。

And this is literally how many verortex shader processes there were there were six， right。

 and there were 16 fragment shaders。Like your GP probably have 2000 now， at least。

 whereas back in the day you had 6 and 14。Then in 2008 youve got geometry shaders。

 so these were you know starting to get a groundup GPU redesign。

 you added things like transform feedback where you could get the data from the output of the vertex shader back onto the CPU and do other things with it and then openGL3 came out。

 created more unified shader processes。And pay attention to the word unified shader processor。

Because that's where it started to be like， hey if we don't need different transistors of vertex shaders and fragment shaders。

 we'll use a unified shader processor。

![](img/429b5b49ef5202f28a4ab42b4f92c2da_11.png)

嗯。So these were kind of the examples that came out。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_13.png)

嗯。And then in 2008， that's where the G8D architecture comes into play and this is where you start seeing the unified shaders。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_15.png)

So from a graphics perspective。The reason to have unified shaders is something like this。

In the top image， you have very， very complex geometry。😊。

But you're not doing much in terms of lighting or anything。

 right you're mostly drawing lines and stuff so those transistors would essentially not be used。

Whereas in the bottom image， you probably have like some simple geometry to represent the ocean surface。

 but then you're using bump map during lighting， all of those things in the pixel shader to do the lighting really well。

So。If you could unify them and essentially combine the amount of transistors that could do both now you can use that workload as it best optimal right so in the top image you can use the vertex load a lot more and give a small number of transistors to the pixel and vice versa for the bottom image。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_17.png)

So this， how many of you watched the graphics， no， not graphics。

 the GPU architectureecture recorded lecture？Now， so I would say this is a good time to watch it if you want because it will really show how from a pipeline perspective。

 so I'm showing the graphics pipeline perspective here right that would be much more from a compute perspective how the GPU architecture evolved to what it is today。

搜。In this image， what we are essentially showing is these。

Each of these here kind of represents an SM， so you have an SM， you have yellows as cores。

 you have blues as context so context is memory then。

You can use these as you please for different stages in the pipeline right and you can have multiple frames in progress so they are going to be used for different things and potentially even for compute operations。

But不。嗯。Then you add tesslation shade is around 2010。

So tesslation shaders are really good for things like grass which is not going to be a project this year。

 it's also great for ocean surfaces and things like that where you're taking a certain amount of geometry but then really exploding it on the GPU because you have basically a lot of compute available to you to do really advanced them another use of tesslation shaders is hair and clothing but you can add more detail it's kind of like anti think but on geometry think of it that way for teslation。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_19.png)

![](img/429b5b49ef5202f28a4ab42b4f92c2da_20.png)

And then 2012， you add compute shaders。Which。Prior to kuda you were essentially hacking up vertex shade and fragment shader to do things like matrix multiplication you may be like what how did that even work yeah but they were doing that so come then you get。

Kuda， which is like a pure compute solution， but then GP GPU kind of combines the graphics pipeline and compute shaders together。

And that's why you can do things like， you know。

![](img/429b5b49ef5202f28a4ab42b4f92c2da_22.png)

🎼我的是。you get like water shades and things like that where you can do compute based operations within a graphics pipeline。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_24.png)

So here's where compute shaders got added into open GL4。3。

 so you can also see tesslation shaders and other things on the screen there。Mesh shading of course。

 hasn't taken off as much， but in 2018 andvidia added mesh shading to。

To the GPUs it was meant to replace the traditional geometry pipeline so go away from vertex and fragment shaders and stuff to in a completely different way of thinking about it called meshlets so this is kind of the meshlet processing pipeline I'm no expert in this we did have a guest lecture from Manuel Kramer who was one of the key people on vertex shaders back I think it was in 2020 and if you're interested in mesh shaders I thought it was a great guest lecture back then very very complex not easy to understand but something if you're interested in doing mesh shaders again。

Meshades didn't create a different pipeline， meshhas would use the GPU pipeline to do mesh shading based things for their use。

And here's a couple of demos， of course， Naite more recently is also using a similar pipeline for that。

2019， oh sorry， didn not go ahead。那是哎。那个男。Represent us geometry in different ways。Yeah嗯。

Is there a chance that in the future there'll be like hardware created that are optimized specifically for mesh shadeators as opposed to the traditional baization bycycl？

It's a good question。 And I don't know the answer to that。

 The reason I don't know the answer is because the again， the the translation of。

Do do we now start creating mesh core if I can call it that as opposed to putting more intensor code or RT core or traditional compute core like what's the calculation。

 what's the cost benefit， how many people are going to use it， I don't know。

It may be more like NVDdia at least， decides to say， hey。

 we are going to optimize our course or our fixed function hardware to do more mesh shading。

 that could be something that might happen。Other questions？Okay。

Then in 2019 of course ratio came about， I'm not going to touch too much on this because Eric Kanes told us everything we needed to know on this。

嗯。Some images， so here's kind of the conclusion of this。

39096 we had input data software entering frame buffer right that's kind of what all of you did in 460 as well。

Then 2001， everything became fixed function hardware with limited to no programmable things there。

Then in when direct X10 came out and some more modern GPus came out， you started getting。

Vertex shading， geometry shading， fragment shading as programmable。

 and everything else was fixed function。

![](img/429b5b49ef5202f28a4ab42b4f92c2da_26.png)

Then with Kuda and stuff， you kind of go into no fixed function where everything is as you wanted。

 you can define if you were to write a kuda asterizer， that's essentially what you're doing。

But now we could potentially be going back into software render if the hardware is fast enough。

Right if we'd say which we not？Happened really， but it's an idea you can think about just like。

In the 70s， we had mainframe computers。And nobody had a computer on the desktop。90s， 200s。

 everybody has a PC， right everybody has a computer on their home and that's what they're using。

And now everybody's using the cloud where you have this either phone or tablet or small。

 very lightweight PC， but you're connecting to this giant mainframe in AWS or somewhere else。

So just in that concept， you can think about how we are going back into software rendering if there's infinite amounts of compute available。

 including things like pixel。Not iss pixel feeding。嗯。

Anybody know what Unals remote render thing is called？I thought it's called pixel sha。

 but I may be Yeah no。Sorry， let me， that， that's gonna bother me。 So let me look it up。 Un remote。😔。

认真。Second。I'm not unable to find this anyway， I forget I don't want to digress too much。

How many of you have played one of those cloud gaming platforms NviDdia Gforce now Microsoft textexbox。

 whatever they call it I'm sure there's an AWS version I'm sure there's a PlayStation version most of you have played this at some point right yeah so again this is basically that where you're rendering somewhere else and all you're getting is a stream of pixel bytes into into your computer so that's kind of how。

The pipeline has evolved， that's how it inspired Kuda。

 and that's where essentially we might go in the future as well。

So that's the end of this part of the lecture。Let's stick。A five。

 six minute break and come back and we do forward plus and differ just so that we are setting you up really nicely for project four。



![](img/429b5b49ef5202f28a4ab42b4f92c2da_28.png)
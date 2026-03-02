# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p21 -21-Guest  Lecture  - Kimera_ From Classical SLAM to 3D Spatial Perception.zh_en -BV1UfAmeUE3e_p21-

![](img/ccd447fa75f181625bab62026a7e7d44_0.png)

Yeah。Good， I think it's recording them right right I think。

Pleasure having you Tony and you don't need introduction you're doing great work robot mapping Tony from MIT it's a pleasure having him here the stage is yours I will monitor questions in chat and let you know when it's possible。

Yes feel free to ask any question during the presentation so well thank you very much for having me it's a pleasure to be here I will be presenting today mostly what has been all my work during my PhD so I'm a fourd PhD student at MIT working with Professor Lucca Caronone and my work has been always about bringing the gap between classical slam and 3Dpat perception and I will define what these terms are in a moment but the idea is to improve upon classical slam to leverage the most out of the sensory input that we get in order to understand the scene as better as we can so the motivation of this work basically is about allowing robots to navigate fully autonoously indoors given natural language commands such as a command like bring me a cup of coffee that might be in a kitchen。

This is in contrast to the typical queries that we have in robotics， that is okay。

 go to X Y z location in a given frame of reference。

So in order to have a robot to understand such queries， such natural language queries。

 we have to decompose the problem into three levels and many more eventually but like the main levels are first it needs to understand where it is in space and the problem known as localization then it also needs to understand what is the world surrounding it。

 the problem known as mapping and a combination of both is like a simultaneous localization a mapping problem also known as lamp and then on top of it it needs to understand not only what the geometry around it。

 but also what does this geometry represent like you don't want to have the geometry of a mug of coffee but you also want to understand that that's。

So the combination of all these three problems I will refer to it as metric semantic s metric for the geometric or potentially photometric reconstruction and semantic meaning the semantic understanding this problem we solve it in our first approach with our first work called Kimmera and eventually I will just name everything kmerra as in chimerra keeps growing in this sense so hopefully you don't get too confused but at the core kmerra is a metric semantic s approach。

So the input to Kimmer is basically an RGBD camera with in and inertial measurement unit that gives you linear acceleration and gyrososcopicpe information and with this information the idea is to go from images to a dense 3D metric semantic map of the world so let me go back because I think I went too fast so images like this one。



![](img/ccd447fa75f181625bab62026a7e7d44_2.png)

To a metric semantic reconstruction of the world， and in this case I'm showing a 3D mesh。

Where we have the objects， theman objects in the scene， color coded with solid color， so for example。

 the chairs are here in green， laptops also in red， etcter。

and you also have the floor and the walls and here i'm showing like M that is also very sparse as in there's huge triangles for the floor。

 there's not like millions of points for the floor and stuff like that so this is the most idealized result that we would love to have in a metric semantic slam that goes from images to this。

So okaymerra is our first attempt to this and we actually got fairly close to the ground truth and I will get into the details of how these words and how do you put pieces together to arrive to this level but notice that there's also like a lot of words to do still for example you will see that here on the left the reconstructed chair is not totally well reconstructed there's this missing connections right you will maybe also notice that if you look at the bin the purple bin it's kind of like connected to the closet and that something that you don't want you want to have entities separated right and it's very difficult to see here but this is a 3Dmas that is very dense there's lots of vertices per object and for example the floor is represented by millions of points instead of like just one triangle and that。

All right， so it's a first good attempt， let's say。

 but let's get into how do we get to this level of results。



![](img/ccd447fa75f181625bab62026a7e7d44_4.png)

So at the core of camera we have like a classical sparse visual inertial autoometry pipeline。

 unfortunately classical s typically uses sparse landmarks so that it does the inference much faster and so our first problem that we have to solve is how do we enable dense 3D reconstructions and here I'm showing you a drone navigating indoors you have the camera input on the left side on the bottom left。

And what we do at the first approximation is estimate the 3D scene。

 the depth by simply triangulating the feature tracks that we tracking the RGB image and projecting this in 3D given that we have triangulated Islamlammark。

 this gives you a very rough estimate of what's the depth of the map。

 but this is not sufficient for a global 3D metric reconstruction that we mentioned before。

 this is mostly to avoid the drone to collide against things right？



![](img/ccd447fa75f181625bab62026a7e7d44_6.png)

So once we have the pole and these 3D landmarks that are fairly accurate， but not super dense。

 we then fuse dense maps by using steer reconstruction or RGBD cameras into a volumetric 3D representation and the volumetric 3D representation is very similar to what you've seen in lecture to help I believe in a Comp mapping and it basically uses a Bay Asianian fusion to update at its voxel what is the probability of having an occupied voxel。



![](img/ccd447fa75f181625bab62026a7e7d44_8.png)

![](img/ccd447fa75f181625bab62026a7e7d44_9.png)

On top of these we augment the volumeot representation with semantic labels I believe you've also seen similar approaches by using categorical probabilistic distributions and so what we do timera is simply we take the left camera image we run it through a conventional neural network to get the semantic labels and then we project this three point cloud in space andfuse it in this volumeot representation our implementation is such that it runss really fast it's about 10 hertz on a CPU it doesn't even use a GP because a drone is typically very constrained in terms of computational power。



![](img/ccd447fa75f181625bab62026a7e7d44_11.png)

![](img/ccd447fa75f181625bab62026a7e7d44_12.png)

![](img/ccd447fa75f181625bab62026a7e7d44_13.png)

And so we get this 3D reconstruction that I'm showing of an office space where the drone is navigating indoors。



![](img/ccd447fa75f181625bab62026a7e7d44_15.png)

And on the right， I'm showing a top down view where you see the reconstruction being progressively updated。

Notice that here I'm using ground truth semantics because I didn't want to bias this reconstruction into a given semantic network and I assume that in the future semantic semanation will improve over and over so given these assumptions that's one of the reasons we get a fairly consistent reconstructions here so here I'm showing a basic overview of the ground truth on the right and our reconstruction on the left。



![](img/ccd447fa75f181625bab62026a7e7d44_17.png)

![](img/ccd447fa75f181625bab62026a7e7d44_18.png)

![](img/ccd447fa75f181625bab62026a7e7d44_19.png)

So you may see that there's there's a bunch of errors as well like there's like noise。

 there's like places where it's empty， but overall it has a nice 3 degree reconstruction of the scene。



![](img/ccd447fa75f181625bab62026a7e7d44_21.png)

So the organization of Commers a bit complex， I will not get into details of every model here unless we have a lot of time in the end which I have sites for that or if you are really curious about it。

 but at its bare bones like we have as input as I was saying the stereo and IMU we pass this to Kmer viao which has a state of the a visualal N hellmetry pipeline that gets just the 3D poses and the 3D landmarks。

 the 3D landmarks I then sent to the multi I think Ive frozen over there。

I think I approachedze for a second then the 3D lamb。😊。

Mars when go to the camera measure that reconstructs a fast local per frame 3D image and then fuses it into a multi frame 3D image。

And in parallel we send the three post to our camera RPG module which does post graph optimization which I believe you are familiar with now and this allows you to reduce the drift when you do local visual in geometry all of these is then all this information to 3D poses and depth and semantics is also sent in parallel to the kmer semantics module which is the one that provides this slow semilow it's actually real time global metric semantic then reconstruction。

So actually let me show you how fast this is so here I'm showing on the left the fast approach which is the defaulting k seman and the mergeRS approach which is a little bit slower but improves the quality and you can see that it's fairly fast I mean this is actually running three times faster than the drone was moving around so the reconstruction is almost immediate。

ok 嗯。嗯先 so。Then once we had Kima and we provided these dense 3 d metric semantic mash。

We realized that it's not that useful for a drone like or a robot like we had before。

 the one that wants to bring us a cup of coffee to understand how to do that。Why。

 because our query of bringing us a cup of coffee that's in the kitchen has high level concepts of the scene that the 3D metric semantic me does not have。

 like for example， the concept of rooms like what's a kitchen， what's a corridor。

 what's a bedroom etc， also does not have like the concept of whether the most common traverible paths like Hythropological map of where you can go from A to B。

It also likes the concept of object instances like each chair here just colored as chair like you have to imagine that these are vertices at the end of the day they have the label of the object and that's it there's no concept of object or even instance like this chair is chair number one and this chair is chair number two etc and also it didn't have like dynamic objects so in an office you would imagine to see lots of humans moving around but Kmerra was not built to handle these dynamic elements。

So with this in mind we developed a well let me first let me first motivate why do we want to do these highle attractionions with an example that is very common to you so here I'm showing a 3D mesh that is that I took from Google Earth and that's like from satellite imagery of the MIT campus and you can see that I mean you can recognize buildings roads and so on but it's fairly difficult if I tell you okay bring me to the MIT dome main dome it' like you have not probably not unless you didn't hear for a while you have no idea where it is。

It's actually here and if you haven't taken yourself a picture here when you come to the MIT you should but like。

It's fairly difficult for you to recognize that and the same happens for a robot what you would like to have is like something like more semantic right like an annotation that tells okay there is the great dome。

 you have the roads that are traverseible around here， you have like the auditorium here， et cea。

 like parts， all the meta information that you can extract from the scene。Actually。

 you want both because for a robot you also want to avoid colliding against building in other things or trees and so on that are static and so for that you will have like these merged representation。

 semantic and geometric。So the combination of both of these worlds led us to develop the concept of a 3D dynamic S graph and a 3D dynamic S graph basically extracts all these high level abstractions of the base metric semantic mesh so at the first layer I'm showing here the measure reconstruction from Kimmera。

The second layer represents what are objects and agents in this scene。

 so objects are considered like static objects like sofa chairs etc ceter and agents can be the robots or humans moving in the office which is a bit difficult to see it here but they are moving around I'll show it in the next light how it looks like in 3D。

Then in the third layer we have the concept of places。

 places are spaces in 3D space where the robot can be without colliding against the structure around and structure is basically like ceilings。

 floor， walls， etc。These places are connecting topologically so that you know how to go from one place to another。

And by using this topological graph we further segment it into the concept of rooms right pretty useful for navigation and these rooms are further more connected and then we have the last layer which is the concept of buildings of course you can concateate buildings together and have a topological map between buildings you can also generalize these with different floors etc。

Now let me go， well let me show you first like a 3D visualization of this in and this graph。

 by the way this is a tree like representation so every node has one single parent。

 it's not completely three because it's like theseions at the same layers and each node has also children。

It allows you to do very fast inference as well。But let me get into layer by layer how do we build these reconstruction so at the base layer we have the metric semantic 3DS。

And as I was telling you， this is Mokimera。嗯。The second layer is about the objects and agents。

 so we divide first the objects as static elements and in this case we have like our cup of coffee。

 table， etc ceter。What is their shape or other meta parameters like the bounding box etc。

 and also we assign ideas per object if the bounding boxes are not connected。

 they have a different ID with further distinguish between known objects for which we have a CA model and in this case we would resist that can model to the vertices of the mesh so for example。

 if you have a sofa like this that is not fully reconstructed but you know what IT a sofa is then you would fit a shape on it and there are known objects which do not have prior3 model。

And there's of course， a lot of work that can be done here， like for example。

 if you have two reconstructions from different sides of the same sofa。

 you could merge them in some sense and then agglomerate all your information about an object。

But we didn't delve deeper into that side of things despite the fact that it's super interesting。

Then we have in the same layer， our agents which are dynamic objects in this case。

 it can be vehicles， human robots， et， and since we are in an office space we show how do we integrate。

 for example humans in the space。So for humans， we basically analyze every image and for every image separately。

 we extract the detection of a SL mesh or simple mesh。

 which parameters the pose and shape of humans fairly accurately and by moving these parameters。

 you can fit the human shape into the image。And we use the approach from professional analytics and colleagues to regress is what are these shape parametersters and then we use our own approach for tracking detections on a frame basis to discard outliers and to track detection from frame to frame which is shown here so let me show you how this tracking works so here we have the drone or robot moving around it's kind of like a pill here but like it moves around and it see this image with a human in it。

And can well we can show here that we can fairly well track the human around and we also show it with several humans and there you have to do some data association to these ambiguated detections but overall it looks like a consistent tracking of the human this is then embedded into the layer two of the syn graph so that we have all the trialss of the human moving around Of course as soon as you deal with dynamic elements you have to be extremely careful because if you try to do this dynamic sorry these volumet syn reconstruction with humans moving around you will have the classical ghosting effect where you see the human reconstructed several times despite despite it being the same one right so theres two approaches to deal with this one is to use what it's known as voxel carving and voxel carving what it does is basically it updates as soon as you see that the human is not there anymore it will continuously update the information that it's not there until the human disappears but that。

to weird artifacts where you see half of a human there because the other voxels that saw the human have not been updated with the information that the human is not there anymore。

So instead of using that， well in parallel of using that。

 we used what we known what we named as dynamic masking。

 and that's basically masking the image using the semantic label where if we have like a semantic label of a dynamic entity。

 we will not integrate the depth from that pixel into the volume reconstruction。

That allows us to get like。To avoid integrating the depth information from a human into the static through the reconstruction。

 So you see on the top not using this dynamic mask in on the bottom using it and how reconstruction。

 By the way， we also use the IMU information。We also use the IM information to understand what is dynamic versus what is static so that the human does not generate feature tracks that could spoil the pose estimate so probably you've seen the concepts of rannack to avoid to remove these outliers and here we use like the IMU as well。

All right， so then in the next layer we have places and structures so I ask a question。

The previous results， did you only use monocular camera or stereo cameras？For the depth integration。

 we use RGBD， so with the depth in the simulation side of things in the real life side of things we use either stereo or also RGBD。

 but like for example， in Europe I used stereo because there's no RGBD。

And you can run all of this in CPU in the Kmera platform， yes。

 everything is running CPU so far except like if you want to run new run networks that you' belong in the。

嗯。But yeah I have to say that that's a very good question because I have to mention as well that these the chimera semantics so Kimmera the basesymmetric semantic mesh is built online okay incrementally but the 3D dynamic S is built after the fact so like a batch and offline it's not built incrementally although we have recent work that manages to build everything real time and incrementally I'll get into that later on but yeah that's a great that's a great point。

So yeah， then we have like the third layer places and structures， so as I was saying。

 places are free space locations where the robot can fit without colliding against anything in its environment and I just represent typical traverseability so this is a classical topological map。

We extract this topological map by inF by using an approach from Helen orlen Icova and colleagues that allows you to extract this map from the volumetric representation and it's a bit slow but sufficiently efficient the whole3D dynamic syn reconstruction takes about 20 minutes for this office space which is not real time but like very efficient doesn't take forever and I'm talking about the whole segment like the tree light representations one everything was coded in C+ so that also helps and we are working on doing some Python binding eventually。

So structures are mostly walls， floor， and sym， which are extracted by the semantic labels here。

 I'm showing an explosion of the sin using these labels。

And then I get into the layer4 about segmenting this topological map into rooms because as you can see here。

 all the places are have the same label and the same color right so you would further want to distinguish it in room segmentation room segmentation is particularly difficult I mean if you want to do it in the last the most oncon to up it's pretty difficult although it sounds super trivial it's not it's not it's not that easy but we managed to get something very relevant because most of the room segmentation work tried to do it like on upper image basis and things like that which is not you don't have too much information to do that but with the full volumetric3 image that we have and the concept of structure and the concept of the topological map and things like that we are able to do something fairly simple that is really accurate so let me introduce first what clean and sign distance function is so remember that we were using a volumetric map and that means that there's about。

SoFor every three position that's a small cube and in every vertex of this cube we store not only the truncated sign of distance function。

 but we also compute whats the clian sign of distance function meaning at every point in 3D space it tells you what is the distance to the nearest obstacle so for example here i'm showing a 2D slice of this function。

And for example， when you are near a wall， you have a red label meaning that it's like zero。

 meaning that the distance to the closest obstacle is zero because you are in the obstacle in this case a wall and it's green in the middle because it's further away from any obstacle so if you cut this to these slices and you truncate this field you get something that is very close to a floor map that I'm showing here and with this floor map we dilate it a little bit and then we got the topological map we got it with this floor map we got all the connections that are between places and that gives you a very rough segmentation of the topological map into rooms。

from this， we then reuse the topological map to label all the nodes that were like left over by using majority voting so if you take a place node that didn't have any neighbor and you look at its neighbors you compute its label by getting how many other neighbors considered that they are in the same room okay with that you get a fairly consistent semantic segmentation of the rooms and then we just connect the rooms together if there's a single place that is connected between that has different labels that is connected right？

That gives you this room top at the room level， we have a topological map as well。

 which we connect from places to rooms and then rooms to buildings， by the way。

 each object is also has also as a parent a place so that if you tell the drone okay go to sofa number four。

 it knows to which place it has to go。And that gets Ju is a nice tree like representation。All right。

 finally we have the building node， which en calculates of all these rooms and places together。Great。

 okay， so that was our concept of three dynamic S graphs and I'll get into a little bit more details of what things you have to be aware of and what applications this representation has。

So we extended this work into while showing applications。

 one is the jical semantic but planning application。

 we also open some simulated these assets that were bigger and more diverse than just the office space so we have like outdoors indoors。

 we have an apartment， we have an office etc。Neighborhood， we also run these in real life datasets。

 which I show later， and we also implemented the concept of simultaneous pose graph and mesh optimization because Kmerra viao as any VIO pipeline out there it will have drift after some time and then we close we use loop closures to limit this drift but once you optimize these pose graph you also have to optimize the three mesh somehow otherwise you will have deform the poses but not the three mesh and how we deal to this in the first paper was simply to do the loop closure optimization first and then reconstruct the whole thing。

So we had to come up with a way to do this optimization with the mesh in the loop so that's what Kimmerra PGmoO does instance post postgraph M mesh optimization and so as a quick reminder you have like four poses here connected together with autoary links for example and then you have a loop closure here represented in blue and typically you would optimize this using postgraph optimization and so the question is how do you do that taking into account that you have a 3D me attached to those poses。

So what we did is like we formulated the whole problem as opposed of optimization problem where our variables now are not only the pulses of the robot。

 but also the vertices of the mesh。Now we subsample the ma a little bit so that we reduced the computational burden。

 but you can see here like in these triangles， there are subsampled vertices of the ma that summarize the 3D ma。

You have to remember that the three images is fairly dense。

So this allows us to get us links within all our variables。

The green ones correspond to links coming from the original 3D。

 the yellow ones or orange ones correspond to the visibility ones and then you have in red the autometric links then when you get a blue loop closure you have like a you can formulate all of this as a loop closure sorry a post optimization optimization problem and you solve for the whole optimization problem and that leads you to a deform 3DM on top of the deform postures which is very useful for building incrementally the 3DM and then updating the whole reconstruction together。

All right， so then we get into our extensions into more simulated data sets and more real data sets and this is also a pretty cool result here but let me summarize which data sets we have here so office data is basically the one I've been showing you so far which is this nice office building but we also have like an apartment building a subway and a neighborhood which is outdoors these are fairly large scale reconstructions then they are open source so you can also have a look at them。

And on top of that， we evaluated our methods in Real life dataset， we have the Euro one。

 which is the classical visual inert helldoometry data set， the white old。

 which is basically my apartment， it's a three room kind of apartment and it's very interesting because we will compare both apartments reconstructions to see how different it gets and then two others。

 one is my office and then school。And to do that we mostly had to build our own hardware。

 which I'm showing here， it consists of two D435I cameras which provide you the stereo and IMU data and we had two also because one we had it with format mapping with the RGBD enabled and the other just for post estimation。

Of course， this has to be calibrated and so on before running。Okay。

 so here I'm showing one simulated data and one real life data set。

 and I'll give you two seconds to try to guess which one is which。Let me see if you can see there。

 yeah。Okay， Joe， can I asked question before you move on what a previous camera set up。

 do they have overlap in their field of view？In this one I believe there was not much overlap there was like a 90 degree or something like that intention by design you decided that's intentional because otherwise。

 so theres is more problem that shouldn't be there but there is there because again we're talking about hardware here and it's hard but like the RGBD of the default55 if you enable the infrared sensor。

 that infrared will get seen in the RGB images of the other camera。

 so that will be tracked as feature tracks in by the VIO。

So you will see like you know like the infarite pattern you will see it in the RGB image and it will be static all the time so we will think that you are constantly static because every red dot point gets at the same pixel location and that will spoil the post estimates so yes it's intentional that they look far apart and this also allows you to have denser reconstructions because you can use sting one and RGBD in the other and you have like two sources of depth of different field of use so that's also useful that makes sense the previous slide I wonder。

If you， because you're not showing it visually， is there any mesh vertex to mesh？Edges。

 factors in the backend to enforce。Some sort of a mesh consistency in a graph。

Because the image implies that they only me structure that is captured through correlation with poses with the trajectory。

Intrior C and B。Yes， no no you're right so these are it's very simple the model at the end of the day this is just like we have the autometric constraints which is ST3 constraints including the loop closure and the others these have the level of translations。

As in， it's like kind of like just springs kind of thing， a matter of。

Computationally manageable approach right because yes it's to make it all the mesh constraints it wont be tractable Yes。

 by the way these are really really subsample3D so its not like not near as as dense as here the way it's a problem we've been thinking about how to build the dense map while we're solving this graph is s problem yeah so we we got inspiration also from from elastic fusion we use like a deformable graph that they call and for its deformable8 the vertices of these deformable graph were not actual entities in the geometry they were like the skeleton of the geometry in some。

Well definedfin way but I don't remember what was the definition of it and then they would attach the surfaceles that were in the neighborhood of that node so that once you deform this graph you would also deform the surfaceles but the surfaceles themselves were not part of the graph so it was a very subsled graph kind of like if you have a corridor you would take like the skeleton of the corridor right and you would deform only the skeleton and the other vertices are attached together。

But here we are going a step further， right， because we are encoding correlations between the geometry。

嗯。Yeah， that makes sense， Thank you。对。All right so where was I okay so here okay so all right so the left one is the real live apartment this is my apartment with my room kitchen and living room I didn't get into my roommates rooms for privacy but it's fairly fairly close to the simulated reconstruction they are both have similar kind of noise and 3D reconstruction problems in terms of completeness but like the 3D dynamic symbol that you couldn build on top of it it's fairly robots right it has like the right number of rooms connected as they should and they have all like the nice infer bounding boxes of the objects。

Okay， so that show mostly that you can close the gap now in some sense。

 between real life and simulated data and was pretty cool to see。

And then I'll show like a quick demonstration of what this enables us so once we have like these three dynamic syn we finally can do this kind of queries okay robot go to this room and fetch me whatever no in this case what I have is like let me show you so what they have is like a drone in this room okay flying around static and then I tell it okay go to room number seven close to bin number three in this room。

And then what I'm able to do is like at the level of the year of the S graph。

 I can plan first at the level of the rooms to which groups you have to travelverse instead of looking at other rooms。

 then go to the topological map and the level of places where the path planning is also efficient by using H star or something like that。

 and then eventually I get into the volumet level where you have to look at every position in this space whether I will be in collision or not。

And that basically shown here like the pink is like the map at the topological level and then the black one is the locally free trajectory。

So yeah that showed mostly like what was the end application。

 although there's millions of other applications for the three dynamic syns that we can get a little bit deeper later。

 by yeah let me summarize basically what we have here let me see so first of all we open source all these data sets so feel free to use them I think theres everything that you need to build your own reconstructions improve on these methods perhaps the completeness like that we have like photorealistic RGV images depth images。

 semantic images， IM information the ground truth for almost everything including pose estimates human poses。

 object poses etc。We have two data sets the first one is the one that we use for the original three dynamic Sgra paper。

 the youth humans U stands for Unity because everything was built with a Unity simulator。

 the simulator itself is open source so that's pretty cool and then we have the humans too which is our IJRR paper the journal paper that worked on top of the previous one and mostly extends the office space to a neighborhood subway and apartment spaces and it also includes humans so there's moving around。

诶。Okay， so yeah， you have the website here if you want to check the data set。

And okay so what was one of the problems that we just mentioned like many just asked the question about okay how fast is this is this incremental right the thing is that DGs are all built in batch and so that's a fundamental limitation so the natural step was to build a real-time incremental through the DG of the scene and this is work from my colleagues Nathan Ju and of course LucA and they just publish this paper called Ira a real-time spatial perception engine for three syn graph construction or optimization I really recommend to you to read it。

 mostly things that I really like are the look closures using your article descriptors so that instead of using the typical back of words approach you also look okay where am am I in a building that is having a room that has certain objects in the space and then you extend these descriptor having this information and then you can do this。

Top down text of where you are and then you also have like the concept of continuous segmentation of places into rooms。

 which is very interesting to look at。AndThere's also other works that are going into that direction。

 for example， S refusion， which also does some kind of incremental graph prediction from these LGBD sequences that they also recommend you to read。

Um so that that basically rubs up what has been gone so far in terms of like going from classical s to densesymmetric and semantic s to high levels in understanding of the world。

And now I'll get a little bit into what I believe are the next frontiers for La and current limitations of Kmerran3 dynamic syndrome that would be very interesting to explore and maybe you will have the chance to explore。

so first I would like to touch into how do we tightlyco learning and inference by inference。

 I mean s inference， and then I will touch briefly on differentiable rendering。

 which is a very exciting topic also。And then I'll leave some time for questions and I think we still have plenty of time。

 so that's great。So okay so the metric semantic La I mean I have to say this is a fairly new concept right but like there's still a lot that has to be done and there's some limitations that are intrinsic to the way people are doing things currently that I believe we should we should tackle all so first of all Kimra only uses deep learning as a black box and I never told you that we were training neural networks in the loop with La right like semantic seation was taken out of the box depth estimation can be taken also from a neural network there's also many other things that you can estimate know optical flow traveribility you name it。

Furthermore， we do not reuse the dense 3D image once we build this dense 3D metric semantic image the VIO has never never back projects these into a depth image that compares with the RGBT image and then takes errors or a feedback group from that information and improves its position and potentially the map as well so how do we merge these you know how do we how do we solve these intrinsic problems in in the s pipeline that we have right now well first I argue that we should couple deep learning and to train dim networks in tandem with them and what I mean by that is that。

These weight of the neuraln network should be aware of what influence they have in the s pipeline。

 and then I'll touch into the differentiable rendering that has the potential ability to simultaneously optimize both the pose and the map。

So okay so let's start with telecoing DeepS so neural networks as you probably know。

 they are state of the art for many many applications including depth estimation。

 optical flow semantic segmentation， but like all those land pipelines that you will see around they barely get using learned front ends。

 they barely get to the level of model baselinelam。😊，And that sounds weird。

 right because they are in principle better fronts that what we currently use。

 but yet they do not achieve very good performance and the hypothesis here is that these neural networks have never been able to tell。

If getting an overconfident estimate of a depth estimate improves or not the s pipeline right so what we would love to do is train our neural networks with s in the loop and by Islam in the loop。

 let me formulate it here very in a very simple way。

You remember that well probably from the previous lecture actually here in the I'm showing a double optimization problem where the inner optimization problem is simply the one problem I kind of linearize it here already but you have to imagine that this could be a nonlinear let me youC marker this should be like a nonlinear function of your state and your input where the parameters theta are you can kind of can imagine that they are like the neural network parameters like say that you have a optical flow or depth estimation network and the depth estimation network has some parameters theta plus this theta parameters they can kind of parameterized other things like the robust cost function that you use or other I parameters in the optimization problem the thing is that you want to optimize you want to optimize these problem and then you get x being x would be like the trajectory estimate for example。

The post estimates of the VO and you want this post estimates of the VO being as close as possible。

To the ground truth trajectory okay and now you want to optimize the network parameters so that this loss this outer loss is minimized right so again we solve the some problem in the inner loop and then for its solution of these inner problem s we want to minimize the end tracking error and find the parameters that do so。

So the hypothesis is that if we train our neural networks using that。

Using this kind of approach we will be able to improve the sM estimate and the fundamental problem that you have to deal here is that well first you have to know how to differentiate through such an optimization problem and there are techniques to that one is on rolling which is kind of it's kind of like the most used right now which simply。

Unrolls the optimization problem like every delta step that you take you take it into your computational graph and you back propagate through that and the other one that is more recent is to use implicit differentiation where once you get to the optimal you can。

I will not get into details， but you can basically differentiate the KKT conditions and then with that you come back propagate in one step。

And so the idea here is mostly to be able to optimize through these problem， the network parameters。

 it will also be computationally more expensive， of course。

But you don't really my argument here is that you don't really care because this is an offline approach right the training of the neural network it can be done in weeks。

 you don't really care the important is that once you deploy it it's real time right。

All right so why is this not commonplace I would argue that I mean the tools are there it's kind of like we know how to enroll。

 we know how to do factor graph optimization， we know how to train neural networks。

 but the problem is that we still lacking like some large photorealistic s data sets with potentially inertial measurement units and so on and we now have data sets such as Ttan Air although it doesn't have IUS from the last time I checked which is a pity or simulators like Earth steam carla etc that we can leverage to learn these networks and to improve our sM estimates。

Furthermore， we lack the differenti factor graph optimization frameworks。

 that's just super important like GTM unfortunately you've already played with it。

 it does not support out differentiation as far as I remember。

 or at least it does not support it in the context of dim neural network training。

CRS has some support has a strong support for forward model to differentiation。

 but I still haven't figured out how to connect that with Pytors or JAs or this network so you'll have to help me with that but I think it can be done and then we have other new tools very recent like Ja's factor graph which seem to go towards this direction but they still have't improved like how to fuse not how to fuse but they haven't improved yet like state of the RV yours or autoometry pipeline and I believe it's in part because it's very recent but it would be awesome to have some pipelines develop on top of these tools or develop our own tools in that sense。

So yeah much has to be done still into this direction。

 but I believe it's like the right way to go and hopefully we can finally type a couple deep learning and slam。

Okay， so let me get into the next one， which is very interesting and it's differentiable rendering for Islam。

So you probably are already familiar with concepts such as differentiable rendering nerve and all these things because they have like a lot of。

Let's say publicity nowadays， but let me summarize it very quickly the idea of differentiable rendering is mostly that you the classical differentiable sorry the classical rendering pipelines can now back propagate gradient so that you can optimize your neural network given the difference between the rendered image and the observed image okay and for the case of I nerve what they do is that they have an MLP that does some kind of positional encoding meaning that for each 3D coordinateor in space and view direction they would encode they would have the MLP infer de occupancy and the color and then you would integrate all of these informations through array that gets to the pixel of the camera and that will give you a color and then you compare all these pixels of all these colors and I know it sounds computationally expensive because it is and with the actually observed image and take。

Gs with respect to the parameters of the neuraln network so that it understands the scene as it should。

This approach seems to work really well and everyone is fairly impressed by what's the performance of this。

 given the simplicity also of the pipeline and novel work has tried to leverage this new results for pose estimates a simultaneous mapping and localization right so on the right I'm showing INve which was one of the first two estimate poses to infer poses given an already built nerve of in this case an object in the scene and they seem to perform fairly well although the optimization path seems a little bit noisy。

 it doesn't seem like it would be really robust。And then IMap， which is very interesting。

 takes similar ideas from IE， which basically propagates errors from the loss to the estimate post。

 but they do that in a simultaneous localization mapping framework where they do in a joint optimization。

 the optimization of the map and then optimization of the post and vice versa and they alternate。

We still have to see an approach that does that simultaneously， right in a joint combined way。

But okay， so what does this enable us well first the nerve results are fairly impressive like you can see in imM that despite the fact that it's fairly smooth is really complete this you remember my reconstructions that were very incomplete well here the beauty of the neural networks is that you can query it anywhere you want continuously in3D space and it will retrieve you a value it might guess it in some weird way sometimes but at least it gives you some prior information on what is in there。

And so the idea is that this is very flexible and very simple。

 so you can integrate it as well in neural syngraphs right which is this paper that was presented in CBPR 2021 and this paper basically shows that 3D S graph like the one we were using in Kimmera can be at at its lymph node can use neural rendering differentable rendering to actually be able to simulate very interesting effects when you decomposes in so for example something that it's impossible to do with the mehe that we have in Kmera is simulating like theity specities of the 3D image that moves in the scene so for example here I'm showing here they show like a car that move from right to left and you can see like the sun spot on the car moving as well consistently with the translation of the car and that's something that。

ul not be able to model in the original camera paper so that's a very interesting new ways of merging these differentiable rendering and three dynamic syns and I believe it will be like the future mostly because of its versatility right now you can not only move the objects around which you could do with three dynamic syns but you can also optimize these models over and over by using differentiable rendering so that's a very interesting novel ways of doing these and I expect that this is very much in the context of computer graphics and novel view synthesises and so on but like I expect a lot of work going into robotics to implement this kind of approaches right。

So that's mostly it for this presentation and I would love to delve deeper into whatever subject and topic you want to。

 but overall， well I presented the three metric semantic pipeline that was Kimmera。

 which allowed us to go beyond the classical sparse point clubs which at this point it should be fairly simplistic for you and you should strive to go into denseZ geometrically and semantically aware maps。

Then we built on top of it with the 3D dynamic scene graphs and we're constructstructing these high level representations of the scene。

 which are critical for robot navigation。And then I touch a little bit on what are the different frontiers that I am really excited about and if I had to do a PhD again。

 I would probably jump into one of these。So with that。

 I conclude the presentation and I hope that we'll get closer to having robots navigate fully autonomously in our home or offices or everywhere。

All right， yeahep， fascinating talk。I love the ideas that you shared with us， thank you so much。

I think we can open to， maybe。Some hard questions for you and I can start and a lot of these ideas that you shared。

 we talk about them in the lab。In different contexts and setups。

 not necessarily in specific wordss that you said。Especially hyperparameteral learning that is such a big deal。

 still tuning conveyvariances in the factory graph。Everybody complains about that yeah。

It would be nicely outsource it to a learning module so one one question that I cannot ignore is。

I don't have an answer for it， but this how。Do。So we can aim for some models that are really huge and it'll solve the problem probably。

 but we still have the problem of generalization and answering what is the minimal。Set up or model。

That provides that。Generalizability and performance at the same time。

And the answer is seems to be that we keep coming back to this problem of structure。

 not giving up everything to the black box model， which is maybe that's why you talked about the delay and why you're not adopting all this back propagation idea。

So I wonder if you have any insight to share in this regard。Yeah。

 so we always have to keep in mind the generaliz problem always like when designing these modules so what I've seen from the literature so far is that there is a lot of value in bringing your。

Not prior information per sample like your insights about how things work。

 not like the principles and that seems to be that the more principles you put into the optimization problem。

 the more grounded mathematics you bring the optimization problem the more generalizable it becomes right so for example there's work from David Kaamousa Profes Kaamma that shows that by fusing by learning not directly from the images but from the extracted feature tracks and or IMU perineg factors by learning from these abstractions of the real world。

You can achieve much better general eibility than if you were like directly inferring from sensor measurements right which are conditional into where you are sensing these thing so I believe that again like I do not want to throw away all we know about factor graph optimization and all the people are constraints and all these things it is to leverage that as much as possible in in in an interesting way and unfortunately I've seen like a lot of work into abstracting the raw sensor input into concepts that we know and master and then learning on top of this but I haven't seen a lot of learning on the fusion side connected with that meaning that the pipelines that strive to do general e by abstracting the input into other concepts that are more amenable to deep learning theyve typically  fu this information by concatenating。

The hidden learned parameters， which is like， I mean， okay。

 but like you throw away like all the factor graph optimization literature that's exactly I felt when I saw the concateation。

😊，Exact feels like a bit a little bit too fast though。

 so I still have to see someone connecting both in a meaningful way， right？😊，um。But yeah， I think we。

 we are， I mean， probably there's someone。I mean， I wouldn't be surprised if someone publishes this in one month or two。

Yeah， I mean， there's a lot of work to do in that area how to we don't have sense of fusion in late in the space。

 so to speak， that's。And it's the generalizability of this。Model based matters of。Amazing。

 we can just the filter anywhere。But anyway， yeah， these are great ideas that we struggle with let's see if anybody from the audience have any questions。

Yeah， I got a question if you don't mind。So in the concept of like safety。

 do you worry that like your work， especially making use of neural nets。

 which for miners saying don't have a whole lot of guarantees that are mathematically based。

 like if your work ever goes to like try and push it into industry or farther where you want some sort of like guarantee that when the robot goes to pick up a coffee cup it doesn't pick up a knife like is there work or do you see interesting work that's going to go on beyond what you're currently working on to try and set up some sort of constraints or mathematical guarantees that like the output that you're producing is close enough to ground truth it'll be able to safely interact with people in the real world in an industry？

Yeah， so me personally haven't I haven't looked too much into into this field mostly because I don't have time。

 but like most of many of my colleagues in my lab with Professor Luc at Caron have looked into this kind of guarantees and I would really suggest like looking at the world of Pascal Antonante for example who is actually looking to how we can provide this kind of guarantees in a mathematically sound way I'm more in the camp of okay well we haven't even solve the inference problem like let's not even look at the guarantees so far right but it's definitely super important and I can be blamed that I haven't looked that much into it。

Thank you so much， fantastic talk。没有。And now I'm saying that there's something in that chat。 Okay。

 there's no question there。发生。Do you have any questions？

Feel free to type in chat or open your microphone。Okay。Hi I'm Bruce so I have a quick question。

 I saw you have a hierarchy for your planning for your mapping。

 could you go back to that slide real quick？So that you have a building and rooms and then。

At the end。Is one。Yeah， could you go to like next two pages。

 I think there's a larger hierarchical graph there， yes this one。Yeah。

 so I have a quick question that how how did you formulate the so like you have a you have the object and agents。

 the purple lines， so that's the topological。Wable region， how do you formulate that？

So the purple line here， I believe it's the trajectory of the robot。

 it's not the topological map is on top of it。I see。

 so different colors there stands for different rooms that。And how do you classify so first。

 how do you classify if the area is if the the sensor the sensor measurement you have is optical or free reach or optical free like。

First， how do you determine obstacles and how do you formulate into different roots？😡。

Yeah yeah so let me perhaps show you more like these to these lies so that you see so remember that this is not visible in the reconstruction but remember that this is a volumemetric map so you actually have information at every vox cell in space meaning almost every 3D position what is the distance to the nearest obstacle so this gives you all the information you need to understand if something is free or not。

Right， and what what the topological map does is mostly like。

It extracts every point in this space that doesn't collide against something。

In a more sum I mean this is a very oversimplification because a bit more complicated than that。

 but it basically extracts these diagram of poses that do not collide against an obstacle and again I have to emphasize that the way of extracting a topological map from a ESDF comes from the world from Helen or Lecova which I have here sparse three topological graphs for myarial vehicle planning so I really suggest you to look into that paper you are interested and it's mostly about extracting these G which stands for I don't remember what was the G it wasvolnoy diagrams and the idea that。

Is that you want to strike the skeleton， the skeleton of these reconstruction and you want to strike every point that is connected to at least。

It's a bit difficult to explain in hand waving， but every point that is connected to two different obstacles。

In a minimum way so if you have something in the middle for example。

 in the or something very close to this wall I hope you see my pointer。

 this will not be included in in the G because it only is close to of them it's only close to this wall right but instead if you take something that is in this diagonal this will be extracted as a place and connected between places because this guy is is at the same minimal distance between the wall on the left and the wall on the downwards right so you would have extracted like the skeleton and this skeleton is usually if you have perfect if you have perfect reconstructions this skeleton is super sparse but as soon as you have like noise and obstacles and lives and stuff it gets very dense because many of this point are the minimal distance between two。

Different obstacles y yep yeah。Yeah so I'm working on something similar to this so yeah'm so if you use that work then I think I think that's pretty clear and but I have a yeah another question like how do you specify different rooms right so like now you have a grown autograph now you know the。

Like you used like a distance to assign obstacles， I assume the obstacle here is some threshold that or if the height is hide in something。

 it becomes an occupied cell and then then you have this graph and you run for anothergraph to build this topological information then how do you assign different rooms？

Okay， so once we have the truncated， as you were saying， there's threshold there。

 that will give you like kind of like the floor plan， right？Okay。

 now if you project the topological map in this 2D slide， the topological map is in 3D。

 so everything place is connected together and so on。

 you project all the nodes into d in this 2D floor map okay。And now and now you disconnect。

 you use the floor to disconnect all the edges to remove all the edges that are intersected by this floor okay。

 okay right， that will give you a fairly fairly compact clusters all right。

Got it and okay okay you simply you simply label them like room1，23，4 five。

67 all right and then you have have the leftover nodes that do not know where they fit and they are the ones that are close to doors close to walls close to obstacle they do not know where they are but then you use like a flufully sorry a Euclidean region growing clustering technique or you can use like the one that we use that is basically vote maximum vote kind of approach where it's node groups at its neighbors and if they are not label they will not changes its label for anything。

 but if they are connected to three room seven and one room one then they will consider themselves to be in room seven and so on。

Got it， thank you I think that's really helpful， yeah， thank you。Thank you， Bruce Tripy。

 you have questions， I think Tony， do you have time？

Of course of course no no you have plenty of time but Bruce I just wanted to tell you that you should also look at the extra paper because they show how to do this incrementally as well by using by using the concept of modularity and then they try to minimize modularity some algorithms doing that that is really cool as well so you should look into that definitely yeah thank you appreciate it yeah。

Great talk， by the way， thank you and the order of raised hands we have ppy and then Lou。😊，Hi。

 my question maybe。It's mostly like I wanted to understand what is the value of getting this semantic representation of your objects。

 like where do you actually end up using it and how do you do it in real world where you don't have like CAD models or if you can't infer CAD models。

 how do you see that happening and if that's even important for your pipeline。

Yeah so it's very important for us to understand what's the semantic label because at the end of the day we want to do these queries now these queries of where do we want to go and if you only have vertices with annotation without annotations of what is what that becomes impossible right well like there's still like lots of applications where so we are not extracting all the value of these semantic labels for example one could argue that you could use these labels to improve the localization performance by for example comparing the labels that you rendered like the differential rendering that I talked about before you could use it at the level of semantics as well you render the semantics you compare with the semantics that you pair and you improve your neural network to get better at inferring semantic labels so although I do not extract too much value from the semantic labels there is a lot of value that can be extracted andm sorry what was the other question。

Then how do you do that in the real world So in the real world well first we use mas CNN。

 which is like kind of like the classical one which I believe we should improve on and there's a lot of work on it actually there's one word that I really love that you should check out it's a eye labelbel and it's built on top of imMap and it's from professor professor Davidson that shows that by only having the user click on certain entities and assigning labels only by a few clicks no more than that they are able to extrapolate all the semantic labels to the whole scene which is super impressive and they also use differential render for that by the way really worth looking at it in our case it was as simple as using mas CNN and propagating non propagating these labels we fusing these labels in the volumeot representation and for the cases where we have CAD models versus the cases we now have unfortunately we could only test。

And the cases where we have CAD models in simulated data sets in the real life data sets we didn't have any CAD model of anything really。

 so so we couldn't we couldn't。Take that。that's what I was wondering like what like I understand the semantics are important。

 but yeah。Yeah。No， that's a。 thank you。Lud， do you want to ask your questions？Yeah， yeah。

 it's very nice talk。 So I'm interested in the。Is a loop closure part。

 So I'm wondering what kind of method are you using for loop closure Do you like leverage the thin graph structure for loop closure like you match some local thin graphs。

Also， do you think？If you do this will be better than like the image based loop closure。

All right well for that I have to refer you to the words from my colleagues because they are the ones they are the ones that develop that so I well first I cannot take credit about it and second I'm not super familiar about the tiny little des but overall it looks like this like if you know how back of words word devout to at the first paper we use that and that's it for look closures like you only look at appearance pictures and images you take the back of words of it and you computer descriptors and then you compare these descriptors with the query image that you have for this case what they have is like they extend these descriptors instead of just having lowle RGB kind of like information that you use for the descriptors you also have the concept of okay I mean this place in this room which is kind of like a kitchen because you have all these objects right and then what you can do is like。

Bottom bottom down approach sorry top down approach first where you compare like okay I' mean the same building or not like the descriptors of the buildings is the same or not theres meaning in the descriptor of the building you can compute it as you want right how big it is what does it have inside does it have kitchens offices etc it's up to you right you compare these and then with these you are able to say in which building you are right then you go to the next level one you figure it out the building you have the rooms okay in the rooms we have a descriptor for room kind of thing like it has to know like okay is it a kitchen is it a bedroom is it you compare these guys you have pruned all the ones that were not kind of like kitchen if you're in a kitchen for example。

Okay once you get into this， you get into the places right and so on and you keep doing that until you get to the to the well。

 you have three levels here， so you get into the point where you have like the images and then you do a deba2 kind of approach so that you pull many images by then。

 right you compare this and then you do the the classical relative pose estimation and that gives you the loop closure between the images。

Yeah， so I'm thinking like in the lowest level， are you still match image， right。

So like I think one limitation is it it can only work when there's the not much change for the perspectives right。

 So do you think you can maybe match the local syn graphs like they have the。嗯。

They have the objects and the topology of the objects。

 Do you think that quick will be better than matching the image。

Very good point I think they delved a little bit deeper into that but you're right like you could do ICP kind of matching between the geometries right and with that they also provide you like a good yes of whether it's mergeable or not whether it's a closure or not you're right you're totally right and now I'm not sure if they do it already actually but that's totally totally reasonable to do like instead of estimating the relative pose using only images which could you use also ICP registration right。

Okay， yeah。Yes， thank you。 Another question is will you do the。啊对。Like the you。

optimizeptimize the pulse of the8 of the vertices of the mesh。

 You only optimize that for some sample。Vortices， right， So after you have the optimize my suppose。

 How do you deal with the the other measures。Yeah how do you。

Deal with the other ages and the thetices。Oh good question yeah no these ones are kind of fixed like the gray ones。

 so once you optimize these they are just connected together let's say。嗯。Yes， for example。

 you have the the post changed for M1 and M2。 What about like the other you other poses other verses you didn't sample in in this graph。

Yeah， so imagine that I move this M2 to the right， okay？AndThis。These one。

 So there is two approaches to this。 the one is like the。I mean。

 the naive one would be to keep the relative distant to keep。

While the relative distance between both， yeah， you're right。Yeah。

I'm not sure how we deal with the ones in the inner inner me。

 but you could imagine that you could trace them proportionally。

Like imagine these are all triangles so they all have bar centers so if you keep the barrier centers the same they will remain the same right if you've m to a little bit to the right and this is a triangle right so this guy has barrry centers I don't know one half one half one half then it will start one third one third one third it will stay in the middle of the triangle no matter how you move the triangle you see what I mean。

So you can you can either hacode that right you put them like that or if you have like some concept of weight or something like that you can do another optimization problem per big triangle kind of thing。

 but that won't be super useful so I believe we just keep the very centric coordinates the same for its point and that's it inside this triangle。

Okay， okay， thank you， Thank you so much。Okay， only if we could back properly it。That error。

Maybe we could render it I have the closure questions actually it's something that。Keeps me awake。

 I want to do this hierarchical。😊，L closure detection and registration using semantic knowledge。

Seems to be very difficult because we want to move beyond appearance based。The closure。

But it still there's no direct s method that can。You tech loop closures， you can in treat you。

 but it's not as powerful because。At the end， he's still rely on geometry。 and that's。

Limited as opposed to appearance or semantics。I want to connect it to one of the future directions that you talked about that now we can use neural networks to manipulate symbolic。

Structures like semantics。Where do you see these two can go can we。A float。

The problem of hierarchical semantic matching for recognition and registration to that symbolic。

Neer manipulation。Yeah no， I think we have to go that way eventually right because its I don't know who told me that they would call it the warmhole problem as in typically offices right they have the same layout kind of thing and if you're in the kitchen of floor one and the kitchen of floor two。

Visually， they appear very similar， right， but they will have some。

Either some things that are slightly different in terms of geometry or they will be in different floors。

 the fact that they are in different floors and you know that you are in the second floor already prunes you a lot of things know so in one sense the hierarchical descriptors that are implant in itra are the natural next step of loop closing。

But if you want to do this。Much more robust right and just using photometric information you definitely have to get into the semantics and whats the layout even the 3D you know even the 3D concept of things I haven't looked too much into wow okay look closing with using these the MLP itself right the fact that it knows the occupancy and the semantics and the color per per position or something like that right if you know we I mean we haven't solved it but if you know we did that visual we work with hierarchical semantic features one problem is that we are assuming it。

Point。comeses with a hierarchy of labels and these labels are dense。

Whereas when you go to higher level of abstraction in the semantic hierarchy。

 the concept becomes a sparser and。In some makes it easier to narrow down where you should look into and matching these concepts is not trivial because we don't also detect them necessarily。

Yeah， you're not detecting Okay， I'm not building that that seems to be。

That seems to be necessary to user memory and the way we can bring in memory is offline training。

In your network。Because we don't have any problem in our everyday tasks of， you know。

 mistakns two rooms in the building if we live there or we work there。It doesn't matter the lighting。

 what's the lighting or appearance， you can detect it easily。But yeah no， you' you're right。

 you're right and I haven't I haven't thought enough about this to have a better answer than than these guesses but like。

We have to explore it because the thing the reason why we haven't explored that much that is because we didn't have it right so that's great in the sense that well now it's the time to think about this thing yeah now I don't expect an answer just part of some of the feature research directions and questions point out to this direction but I think we need to explore and yeah it's not a simple to answer。

😊，嗯。Right， lots of feature work ideas for。People who will watch this talk。

 is there any other questions while you have access to Tony？😊，And his great mind。Okay。不是。Yes。

Well maybe I can close with the fact that almost everything I've talked about in this is open source so feel free to try it as well you have the data sets you have some of the algorithms it's still unclear if we are when we are going to publish the DHG side of things but most likely it would be eventually open source so。

I'm happy to see what you guys build eventually。And行。Thank you， Tony， thank you so much。

 it was pleasure again having you。Thank you for having me we look forward to hearing about your future work in this area。

Thank you so much。By拜。

![](img/ccd447fa75f181625bab62026a7e7d44_23.png)

Yeah。对。
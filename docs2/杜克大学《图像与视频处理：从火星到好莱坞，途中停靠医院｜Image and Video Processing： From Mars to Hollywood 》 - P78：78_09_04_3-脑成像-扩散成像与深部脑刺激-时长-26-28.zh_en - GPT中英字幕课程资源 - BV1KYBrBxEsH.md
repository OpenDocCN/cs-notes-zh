# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P78：78_09_04_3-脑成像-扩散成像与深部脑刺激-时长-26-28.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back to our image and video processing class。

 This video we're going to be talking about brain imaging。

Brain imaging is an extremely exciting area with applications in basic science。

 try to understand our brain， how we develop and also applications in medicine。

 as we are going to see in this video， we are going to start with a bit of a discussion on a relatively new modality which is called defffusient weighted MRI defffusion weighted magnetic resonance imaging。



![](img/f45add048210d4c2e8e9099ac04a35ed_1.png)

MRI is very old， and it has been a tremendous contribution to medicine。 diffusion weighted MRI is。

 as I say， a relatively new technique。 The reason I'm going to talk about it is because we're going to see a very surprising application of one of the tools that we have learned actually in the segmentation week。

 applying now to diffusion imaging in a very， very different scenario。😊。

Like most of our weeks during this class， we could just speak this topic of medical imaging。

 even the topic of medical imaging for MRI and basically talk for months about it。

 so as before I' give you a few examples to provide you some motivation and some excitement about this area。

So what is diffusion weighted imaging， The basic idea is relatively simple， the basic concept。

So you have a brain actually， we're talking about brain imaging。

 but you can do diffusion imaging for other organs。 You go into a magnet。 an MRI machine。

 Sam type of machine， So this comes of the same classical hardware。

 we're going to just use it differently and what we're going to get out is measurements about the brain connectivity。

 How is a given region in the brain connected to a different region in the brain。

 Something very cool， How is this connected to this， Is it connected at all， For example。

 That's what we are trying to do with efficient weighted imaging。

 And it has been used for neurological disorders， You know if the connections are not what we expect that might actually mean something。

 It has been used for study， as I say， normal brain development。And in general。

 it's used to study the structure of fiber bundles， basically connections in the brain。

 What is the underlying concept in diffusion weighted imaging？

The underlying concept is the following。 Let me just run this。

Let's assume I'm going to make a drawing here。 Let's assume they have a region in the brain。

That is connected to a different region in the brain。

 so gray matter basically and another region of gray matter in the brain。

 and we assume that they're connected。By brain fiber bundles， imagine just cables， Okay。

 so you have two regions in the brain and you have a cable connecting between them。Now。

 we have water and what diffusion weighted imaging is trying to measure the water diffusion in the brain。

Now， assume soon that I tried to。Make water go through the bundle in this direction。

 because the bundle is there。 water。 we have a challenge to go and to move in that direction。Now。

 if I tried to make it go in this direction， then it would actually move in a much easier fashion。

 So if there is a presence of a connectivity in a given direction。

We can actually try to push the water。In different directions。

 and according to how successful we are in pushing that water。

 we can infer the direction of these bundles and then basically the connectivity of different regions in the brain。

 So， for example， if we try to diffuse the water and it goes in every direction。

There's basically no cable。If we try to diffuse the water and it goes in every direction， but one。

 basically there is a cable in kind of the orthogonal direction in the perpendicular direction。

 so if it goes every place but it just has really difficulties going in this direction then something is stopping it in this direction so it comes of the perpendicular direction now you can always you can also find crossings basically find that more than one direction is difficult to make the water go through and in general you can find basically the probability of diffusion in every direction and that gives you the probability of having connections。

Cables in the brain， this cable this bundles in the brain between different directions。

 How is that done The person goes into the magnet， and basically， there are gradients。

 create that in different directions。 So it's kind of you're creating magnetic fields in different direction。

 So you go around， let's say， a circle and you try to create a field in this direction to push water in that direction。

 Then you try to create a field in this direction， to push water in that direction。

 So you basically do that for multiple directions。 and you measure。If you can move those。



![](img/f45add048210d4c2e8e9099ac04a35ed_3.png)

Water molecules in that direction。 Then what you get at the end is something that looks like this。

 you get multiple directions。And basically people take 32 or 64， sometimes 128 of these directions。

 depending how much time can you spend inside the magnet and what's the accuracy that you want your result so basically the person is sitting in the magnet and you creating this gradient in multiple directions from that you can infer the probability of having a connection in a given direction because you infer the probability of moving basically the water in a given direction。

 so you get all these multiple directions and from that， as we I said。

 you get at every single box cell。In the image so we are in 3D， our brain is 3D。

 So instead of pixels， we have voxels。 basically it's kind of threedimensal pixels。

 this is just a slice of a brain。 and we have here at zoom in version of one of the regions。

 and then at every voxel you get kind of a probability of diffusion in a given direction or a probability of having this cables in the brain。

 this bundles in the brain in a given direction。 and then you can consider the whole。

 So this I'm drawing here， the more round it is the more kind of isotropic uniform the probabilities。

 the more stretch it is the more anisotropic in that direction。

 And if you see that there is kind of a cross， then there is anisotropy in more than one direction。

 you can consider it completely or as we see here with this red。😊。

just can pick the maxa where it's actually very strong and that means that probably there are fibers。

 there's cables， I keep using the word cables so because it's kind of that connection or basically give the connectivityivity or the conductivity between regions so you can only pick the maxima of those and say。

 hey， I believe there is a connection in this directions and maybe also in this direction going through this ves so in this ver we might have connections going in two directions。

 basically strong connections going in two different directions。Now， that's per voxer。

What happened if I want to say。Which regions are connected to this region of the brain？

Or is this region of the brain connected to this region of the brain。

 So that's basically I want to go from these local measurements that I get from the machine。

 There is some。Image processing to actually get this， thenoing and other things。 But basically。

 most of the work basically is done by this very smart acquisition。 So you're here， and you say。

I want to know the probability of connection between now far away regions。

Is this region of my brain connected to this region， How can I measure this from this。

Data that I have just obtained。And look what we can do。 There are many things that we can do。

 but here is one of them。 We can do a half transfer。Now we use。

 we learn about the half transform to detect straight lines or curves。

 Now we are actually going to do a half transform for something slightly different。

 but these are still curves。 We want to find basically cables in three dimensions。

 So this is how we do it。We basically stars， let's say， from a point。And we say， let us find。

The strong curves going through this particular point。So you can throw。

 You can just start with a few samples。You just是。Put many curves。 You can parameterize this。

 You can parameterize almost any fashion that you desire。

One of the ways to parameter is just to write polynomial functions and say I。

 I want to just use a function that is of the style。 let me just write down。A1。Plus， a2 x。Plus， a 3。

X squared and so on。 Maybe you go up to 6 exponential seventh。

 And then the half is going to vote for these coefficients。 Remember。

 the half transform is great when we have parametermeized curves。 And here。

 I'm going to just parametermeize a curve by a poly by basically this。😊。

Function and x is just coordinates in X， Y， Z in three dimensions。 So these are kind of vectors。 Now。

 how do you do the votinging Very simple。Remember， at every voxel。

 we have the probability of going in every direction， so I take this curve。

And I say is this a good curve and I go through the voxel and I say what's the probability of going that voxel in this direction。

 so basically the tangent to the curve， and then you go to the next voxel you know go to the next voxel and you keep going so you add the probabilities that you got from the data of the diffusion MRI。

When we talk about the half transform， we were kind of adding the edge content。 If there is an edge。

 we were voting for it， if there wasn't we weren't voting for it here。

 we actually do a weighted voting。 We vote by the probability of going in that direction。

 but it's the half transform。 This is， I think is very beautiful that we can use a very standard theory for a very cool application in a modern image acquisition technology。

 So you go and vote and vote and vote， and then you take another one and you vote and you pick the curve that has the maximum vote。

 So you say this is the one that most of it or at least the majority or in a very strong case the tensions go in the direction that the boxeses tell me there is a lot of probability。

 a high probability of going in that direction， a fiber or a cable， as we have been saying。

Then you pick another point。And you do the same。 You pick anarrow point and you do the same。

 And in that way， you get these tracks。 you get from every point， basically。

You get this probability of having these cables and connections。 And then you say。

Is this point connected to a point， let's say here if there is not a strong cable， a strong curve。

 then sayter connected， you can actually make a binaryization Yes or no。

 or you can make a probability decision。 Oh this is the probability that they are connected at the probability is。

 as in half transform the addition of the local probabilities at each voxel in the same way that when we were detecting circles or straight lines。

 we were saying what basically the chances that these straight line had many local edge detectors along its way。

 And what you get at the end is a beautiful image like this that gives you a lot of tracks。

 It basically gives you a lot of connections between different regions in the brain。

 and that you can use for many， many problems in basic。😊。



![](img/f45add048210d4c2e8e9099ac04a35ed_5.png)

Science in for disease， for development or for other areas。 So to recap。You go into the magnet。

 you get these magnetic fields in different directions。

 you compute the probability of having a cable or a fiber in a given direction。

 And when you want to get information about two points use it has transformed to do a voting process。

 And you can get that connection。 and this is not the only way to do that， it' just one way。

 and I think its a nice way to illustrate how and tools that were developed for image segmentation basically are also applicable in these new modality。

 Now， this has many， many uses。 and for example， you can use diffusion imaging for the very exciting area of deep brain stimulation。

 And I want to discuss what is deep brain stimulation and some of the image processing challenges there。

 So let's do that now。😊，What is deep brain stimulation， Deep brain stimulation， first of all。

 is used for things like Parkinson， essential tremor。

 and at a more experimental level for clinical depression and for OCD and other neurological problems。

 The basic idea is that as we see in this image， an electrode is inserted in the brain。

And pulses are sent， so the electrode is inserted and there's also a generator that is normally put in the chest with a battery。

 and that generator sends electric pulses and basically stimulate a given region in the brain。

 So it's brain surgery， the patient for most of the cases is actually awake and we're going to see the reason for that。

 So there' is only local anesthesia， but the person is actually awake during the surgery where this electrode is inserted in the brain and we see kind of a schematic drawing here。

 and I strongly recommend you to go， for example， in YouTube and do a search on deep brain stimulation and you're going to see the fantastic results of this surgery and some of the symptoms of。

 for example， Parkinson。Or essential tremor basically stop immediately when surgery is finished。

 It's a fascinating area。 Now， the big challenge here is to find the target。

 to find where do you want to put that electrode。 That's the big challenge here。

 And that is normally done with the help of。A number of components， two of them being a model。

 basically brain neurosurgence know about the brain， they know the literature。

 and they have kind of a model of the different regions in the brain and some are basically expressed here in a schematic way and then they use an Atlas。

 they basically have an atlas of brains and they say they know where those different regions are in the Atlas。

 and then they get some imaging for that particular patient and then they try to locate those regions。

In the images of that particular patient using this Atlas now one of the challenges with the help of new acquisition techniques and new image processing techniques is not to use the Atlas anymore and to basically do everything with images from that subject。

 The reason that the Atlas is sometimes used as well as， of course。

 the models is because the images and image processing is not great and then you need to use an Atlas to kind of help you navigate inside the brain Now if we have better images and if we have better image processing。

 we might be able and is going to show you in a second we are able to basically localize the target per subject and then do a better job。



![](img/f45add048210d4c2e8e9099ac04a35ed_7.png)

Now。The way that people are looking into advancing deep brain stimulation is fascinating for image processing because it uses everything that you can get from an MR machine and of course this is not a class on magnetic resonance imaging So I'm just going name a few which just saw a few minutes ago diffusion imaging and we're going to see its role in a second。

 but people use different basically modalities inside the MR So the subject is in the magnetic resonance machine。

 It's like the same hardware but you change the software a bit and you can get different things like T1 T2 susceptibility weighted imaging and of course diffusion imaging as we just saw and you try to combine all of this What do I mean by that you basically register them you align that basically we saw we talk about。

Registration when we were talking about HIV and image processing for viruses so you put all of them in a coordinate system in the same coordinate system you might be able to bring the Atlas as well if you wish to do so and then when you have all that you basically which is already one of the image processing challenges you start doing other image processing things like for example。

 image segmentation you might be able to automatically or semiau for example。

 using active contours segment and mark the regions that the neurosgeon nodes are the target regions so you put you develop active contours that are specialized to these type of challenges and the beauty of that is that when we talk about active contours normally we talk about gradients of one image now you can。

Take gradients of multiple images because you have multiple modalities together so you can we talk about T1 T2。

 the susceptibility weighted image， you can actually compute gradients with all of them together remember we talk about vectorial gradients。

 so now that every voxel and have one scalar number and have multiple numbers， the T1， the T2。

 the SWi， the susceptibility weighted imaging and then I compute vector gradients。

 and I do this vector active conours to segment the regions you can of course。

 and you get segments like this here are different regions of interest。

 the neurosurgeon knows more or less the regions where they are。

 but this gives a very precise segmentation of the different regions of interest to help the neurosurgeon targeting the one that he or she。



![](img/f45add048210d4c2e8e9099ac04a35ed_9.png)

Noose that should be target。 and that's where the electrode should basically be touching。

 so you can give kind of a virtual reality of the brain。

It's superimposing these segments that you get with active contours。

 basically inside a three dimensional visualization of the brain。 you can， of course。

 add the diffusion weighted imaging that we saw earlier in this video。

 and this is represented here with gray。 these are the fibers that we computed。

 So the neurosgeon can start thinking， okay， if I touch this region because it's connected to this。

 then when I put。Basically electric pulses there because I inserted my basically my electrode there。

 then that will also affect this region because they're actually connected so it's not only that you're giving a good target localization you're also telling if you touch here what's going to be affected by you touching there and that's the beauty of putting all this image processing altogether together and then at the end the neurose engine did a lot of planning and basically say okay this is my target because you help me localize it。

 you help me figure out the connections。After surgery。

 the subject goes into a CT and basically we take a picture of this is actually the cable that is going to be basically going to the chest for the battery and this is the electrode that was inserted。

 we have segmentations of the regions and then the neurosurgeon can basically after surgery See wasai in the right place As I say the subject is awake and the subject is giving feedback to the neurosurgeon for example。

 if it's a surgery for Parkson then you can basically experiment different behaviors to see if they improve with the position of the electrode and for example。

 one is the tremor if the tremor stops when you localize the electrode in a certain place and start sending certain electrode pulse。

 then you say it looks like I'm in a good region。

![](img/f45add048210d4c2e8e9099ac04a35ed_11.png)

ThereBut to work even further， you can after surgery visualize everything that happened and here is actually real data。

 These are segmentations that were obtained by type of active contours type of techniques with all these modalities these are the electrodes so you go and register one more modality which is the city from after surgery and then the neurosurgeon can say looks like I was where I wanted to be that's great I actually saw that during surgery because the subject was getting better and then electrodes actually have multiple contacts。

Some have four， some new ones coming to the market have 16。

 and then these post up images can help the programmer to say which one of the contacts will be more effective according to the position that I have localize them。

 So a lot of image processing we do registration from the different modalities we do segmentation。

 and that helps the neurosgeon to localize himself or herself inside the brain of the subject to better do the surgery。

Of course， doing it safer as well。 And in the same fashion that' maybe after surgery to do a better programming and understanding what was the actual outcome of the surgery。

Once again， deep brain stimulation is extremely exciting， and I strongly recommend you。

 if you just search， for example， on YouTube， you're going to see actual patients that talk about how the life became much better after deep brain stimulation from our perspective of image processing。

 tremendous challenges。 and as I said earlier。Basically， the contributions to humanity are great。

 So you're doing very， very challenging image processing， and the outcome is absolutely outstanding。

 and it's hard to ask for something better than that。

 I hope you enjoy this shorter video that shows you a few of the challenges in brain imaging。

 which is， as I say， one of the very active areas in medical imaging。

 and looking forward to seeing you in the next video。 Thank you very much。😊。



![](img/f45add048210d4c2e8e9099ac04a35ed_13.png)
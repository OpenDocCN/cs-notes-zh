# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P73：73_08_07_7-高斯混合模型与结构化稀疏性-时长-15-40.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。This video， I want to talk about Gaussian mixture models and its connection to sparse modeling。

 and in particular， this is going to be useful for us to introduce the concept of structure sparse models。

 Let's get into that。

![](img/b27693ea5808619c56ec4935fbee5ff0_1.png)

As examples， we are going to use the same type of image processing tasks that we have been using for regular sparse modeling in the previous videos。

 What we have is that from an observation Y， we want to recover the image F。 Now。

 the image F has been deteriorated by this operator。

 U and has additive gaussian noise as we have seen before。

 What type of operators are we going to consider， are we going to have in mind。

 the same type that we have seen before， For example， U can be the masking。 Basically。

 we let some pixels go through some pixels we block。 This is why， basically our observation。

 and we want to go back to F via in painting。 U can be a convolution。

 So were going to blur the image。 Once again， this is our Y。This is the observation。

 and we want to go back to F do deep layerlaring， or we can do subsampling Basically。

 we want to go from a small image to a larger image， and that's zooming。

 So these are the type of operations that we are going think and have in mind。 Now。

 let us describe the type of models that we are going to have in mind。

 And the basic idea is that for the moment， we are not thinking about sparse modeling for F。

 we actually are going to be thinking about Gaussian mixture models for F。 Now。

 as we have been doing for sparse modeling。 We don't work with the whole image， we work with patches。

Once again， we work with all the overlapping patches， all possible patches in the image。

And the idea is that we are going to model each one of these patches F sub I again that has been the form。

 Sometimes the operator is the same operator all across the image。

 sometimes it's not and that's why I market U sub I and this is our observation。

 the noise is as before Gaussian。Now we're going to model these signalss with K different Gaussians。

So basically， we have if the patch is 8 by 8。We we again have a 64 dimensional vector as before。

 and we are going to model with k Gaussians， K64 dimensional Gaussians for a Gaussian。

 we actually need to compute the average for each one of the K just to have a number in our head。

 We are going to make k equal 10。 we are going to see that we only need a few Gaussians。

 So we need to compute the average of these 64 dimensional vector and the covariance of these 64 dimensional vector。

Each one of the Gaussians， we need to do that。Now， a Gaussian。

 having a model as a Gaussian is equivalent to having a model as a PCA or principal component analysis。

 the basic idea is that these covariance matrix， we can compute the eigen vectors and the eigenvalue and the eigen vectors give us a dictionary。

64 atoms in that dictionary。 if we are on this dimension。 So each one of the Gaussians。

 let's say 10 gives us 64 atoms。 we end up with the dictionary of 640 atoms in this case。

 that in a very particular form， because each block of 64 atoms are the eigenvectors that correspond to this basically this covariance matrix。

 So that's our structure right now。 and the basic idea is that each one of the patches is modeled by one and only one of these。

 And what we have to do is from the noisy image we are going to have to estimate the noisy or the blurir or the subsample image。

 if we are talking about in painting we are going to have to estimate the Gaussians。10 Gaussians。

 meaning we are going to have to estimate their average。

 we are going to have to estimate their covariance。That's one thing that we have to estimate。

We also are going to have to estimate for each patch which one of these K or 10 Gaussians。

Fits that patch。 The best。And then once we do that。

 we're going to have to obtain from the observation， reconstruct the actual image。

So a lot of things that we need to do estimate the K Gausss。

Estimate the identity of every patch and also then estimate the reconstruction。It turns out。

 although this looks as a very complicated problem， it turns out it is not。

 it's a very simple problem， and it can be efficiently solved with what's called the maximum a posterior expectation maximization。

 the basic idea is that if we know the Gaussian。 So if we know every patch， the best Gaussian for it。

 we have to do nothing else but linear operations with this type of filters to do the reconstruction。

 So it's piecewise linear。For every Gaussian， for every Gaussian that we used to fit the particular patch。

 we just need a linear operator。And this is a very， very simple algorithm。 Once again。

 we are approximating basically every one of the patches。 But by one Gaussian。

 and its kind of selecting。

![](img/b27693ea5808619c56ec4935fbee5ff0_3.png)

From this very large dictionary， one block of 64 atoms。

 which corresponds to the Gaussian that we are selecting。Now。

 the map E alternates between the estimation of the Gaussian and estimation of the basically the appropriate Gaussian for a given signal or for a given patch。

 So we are doing again， we are doing this maximum posteriory。Expectation， maximization。

 and that does more or less the following estimates all the Gaussians， then basically says， okay。

 which patches like Gaussian number one more than any other Gaussian。

 and then with all those patches reestimates the Gaussian number one。

 and it's very similar to what we talk about the KsVd。

 But instead of estimating the dictionary atoms we basically estimate a whole Gausian。

 meaning an average avariance matrix or a PCca basiss。 And then we keep itating。

 normally we do that for three，4 iterations until we converge。

 what we observe here is we have color coded this image according to the Gaussian that a given pixel is selecting a pixel meaning the patch around it is selecting This is the initialization。

or after one or two iterations and this is after that and what we see is that similar regions of the image end up selecting the same Gaussian once again we only allow in this type of approach to select a single Gaussian for every patch meaning for every pixel and again we are going to do the recovery by averaging all the patches that touch the pixel as we have been doing for sparse modeling so now looks like we are not doing sparse modeling looks like what we are doing is representing every patch as one out of Gaussians but let's see that what we are actually doing is a very particular case of sparse modeling。

Why is that。In ordinary sparse modeling， we have a large dictionary normally overcomplete。

 and we are allowed to select L atoms。 So we have K here， a large K。

 and we are allowed to select L atoms in this case。3， and remember， how many options do we have。

 We have。L。To choose from K and that is normally a very large number。

 If we take the regular sizes that we are using for image processing patches。

 which are5 by5 or8 by8 and then a dictionary， which is 256 or 5 to 12 or 1000 and then parsity in the order of 5 to5 to 10。

 this number is about this order， it's a huge number。

 a very large number of subspaces that we can pick from that has the advantage。

 the advantage of being a very rich model but on the other hand makes the model very unstable。

 there is so much to choose from then basically if we make a small change in the image or in the patch。

 we might end up selecting something completely different。InOn the other hand。

 when we are talking about the Gaussian mixture model。Which， as we say。

 is equivalent equivalent to a principled component analysis。

 So we take the covariance matrix and we decompose it to get the principled component analysis。

From the eigenvectors of the covariance matrix， and then we concatennate them。

 So this is one Gaussian， another Gaussian， another Gaussian， another Gaussian and so on。

 and we have K Gaussian， let's say 10 here are the eigenvectors corresponding to the covariance for the first Gaussian。

 the second， the third， the fourth and so on here I show that for five。 Now。

 when you pick a Gaussian， you pick the entire block。

And then you fit the best you can at Gaussian or you use the PCA basis as the atoms of your dictionary。

 But look what happened， we went from this huge number to only about 10 or 20 options because once you pick the Gaussian I mentioned is a linear operation。

 you just project into it and you already have the atoms you already have everything So in both cases。

 you learn the dictionary that here you learn a dictionary where every atom is independent and basically the coding with the atoms is independent here we learn a dictionary that has a block structure and also when you're representing when you are projecting you pick entire blocks and this is a concept that is called structure sparssity where basically the atoms have correlations and they're either pick together or they're not。

At all。 This is a very particular case of what's called block structure。

 There is no overlapping because you are only allowed to pick one of the Gaussians。

 and there is no basically in principle， there is no atom that belongs to more than one of the Gaussians。

 if the Gaussians are different。 So you only pick one block。

 which is a particular case of structure sparsity。 The overall concept of structure parrssity being again。

 the fact that atoms come and go together， they are learned together。

 theyre used to encode the signals together。 and that stabilizes your system much more because the number of options is much lower。

 you either pick one and none the others or you pick the other。

 but you're not allowed to pick an atom from here another from here and another from here。

 you pick in blocks。 Now， of course， as before， there is a lot of very interesting theory here。

It's also very important to know if this is actually useful if I need 10 million Gaussians。

 I'm not gaining much， but actually it turns out that with 10 or 20 Gaussians you can get basically some of the same results that we saw for ordinary sparse coding but with a much simpler algorithm and a much more stable one so again it's sparse coding sparse modeling but in a structure fashion let me show you a few examples of this。

This is one of the examples that we have seen before。

 But now if with this Gaussian mixture model or with this structure sparsity or basically piecewise linear。

 because once we pick the Gaussian， we are in the linear area。 Again， we have the original here。

It's a zoom in to the original， only 20% available。 And here is the reconstruction。

 We have seen a similar example with sparse coding。

 Now we are seeing it with the Gaussian mixture models。Another example is zooming。

 we start from a very small image and we basically zoom in， we want to make it larger。

 and we get really， really nice results with this technique， very sharp edges。

So this is another type of structure， another type of sparsity with structure incorporated。

 and also we get a very strong connection with a classical model with which is these Gaussian mixture models。



![](img/b27693ea5808619c56ec4935fbee5ff0_5.png)

With this， we are actually concluding the week on sparse models。

 We could spend a whole year teaching about sparse models， but we have provided the key concepts。

 what these sparse coding， we have provided the concept of how to learn the dictionaries。

 We have provided some of the theory， we have talked about some of the theory we have talked about some of the computational techniques。

 and we talk about the relationship between sparse modeling and more classical techniques like Gaussian mixture models。

 And from that， the new concept of structure sparsity。 This， as I say。

 is a topic which is very active research。😊，Currently in the image and signal processing community。

 and I hope you have enjoyed this week， and I'm looking forward to seeing you next week once again。

 Thank you very much。😊。

![](img/b27693ea5808619c56ec4935fbee5ff0_7.png)
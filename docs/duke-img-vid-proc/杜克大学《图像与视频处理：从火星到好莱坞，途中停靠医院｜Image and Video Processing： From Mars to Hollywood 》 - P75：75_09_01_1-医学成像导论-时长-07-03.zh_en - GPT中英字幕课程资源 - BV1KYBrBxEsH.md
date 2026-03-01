# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P75：75_09_01_1-医学成像导论-时长-07-03.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back to a new week on image and video processing。

 The topic of this week is medical imaging。 Medical imaging is a fascinating area。

 The challenges are incredible and so are the rewards。When we solve problems in medical imaging。

 we are basically helping humanity and that's a great reward Now medical imaging is very。

 very different than many other areas of image processing One of the differences is that very often we start the investigation we start a work in medical imaging with a problem presented to us let's see a couple of examples of that。



![](img/4e10e720ed44e2102ff3a8769dc1d8da_1.png)

Here we see images of skin basically just regular pictures of the skin with potential lesions。

 potential cancel lesions， so maybe a doctor knocks the door in our office and says。

 could you please help me what I need to do is I need to automatically segment out the lesion。

 I want to measure it， I want to measure its area， I want to measure some of its characteristics inside and sometimes I even want to track it。

 I want the patient to come again， let's say after a year or after a few months or after a certain period and control how that lesion。

 how that region is changing。But the problem is very specific。

So you think and you say I know I have learned how to do image segmentation。

 one of those techniques is active contours， so you can start with a contour。

And you can let that curve deform towards the boundary of the object。

 This yellow curve and all these three images were actually segmented out with active contours。

You might think oh but this image is actually extremely noisy， these are hers。

 but these hers are from the point of view of image processing noise。

 but you also now know how to do image denoicing so maybe before you apply active cons you basically do image denoicing so this is a very important application and a particular example where we are applying our knowledge in image processing to a particular problem let's see another example。

Here is another example in the area of cystic fibrosis and without going into too many details。

 this is a patch that is basically put on the skin and it basically measures the amount of sweat and the concentration of chloride in the sweat。

And the basic idea， the challenge here is to detect this curve。

And detect this curve and compute the ratio of the areas that are inside this curve and inside this curve。

 So once again， the scenario is that a doctor knocks your door and asks you explains you the problem and asks you a particular question and says。

You need to detect this curve and you need to detect this curve for me once we detect the curves。

 we can compute the area and that area gives us information about the concentration of chloride in the sweat。

So you think for a while， and you say。This curve looks very elliptical to me。

Can I assume that that's an ellipse or a circle， You ask a doctor。

 this is a process of communication between two different disciplines。If the answer is yes。

 you say I know how to detect those type of curves， they have transform。

 the half transform is great to detect parametric curves。

 so you apply a half transform not to the image but to the edges of the image。

 and you get this curve perfect。Now this is nonparmetric so you can either apply active contours or you can try autos threshold algorithm to see if you can get this region once you get this region。

 you compute the ratio of areas and you have solved an extremely important problem。Now。

 often in medical imaging， we don't really attack。Problems like these ones that I just mentioned that we basically address basic research issues with data that comes from medical data or biological data。

 An example of that is here， these are basically surfaces that represent the gray matter in our brain in the brain of the subject that went into an MRI scanner。

 And here we see what are called the suulci。 So basically our brain， our gray matter is folded。

 And these are the basically the bottom of the faults。 And from for many reasons in neuroscience。

 these curves are extremely important。 So here is a challenge for image processing in three dimensions。

 how to automatically compute this sucal curves， not for a particular medical problem or medical application。

 but for。Basic research， basic science， basic neuroscience question， once you compute this。

 you can create very interesting networks。Of this sulai， which again。

 have a very important neuroscience。Problem is a very important information for many neuroscience applications。

 some of them actually related to particular problems。

 but some of them related to basic research So these are just some examples of medical imaging。

 we're gonna to see much more in the next videos。 but one of the fascinating areas of medical imaging is that it's a constant learning experience。

 This is not then just by people that are expert in image processing you have to work very close with doctors with people in biology。

 with neuroscientists with people that basically have the medical imaging challenges and that basically forces you to learn new problems all the time and forces them to learn new techniques and basically forces both groups to work close with each other which actually is a lot of fun because as I say。

 it a constant learning。

![](img/4e10e720ed44e2102ff3a8769dc1d8da_3.png)

Experience I'm going to try to teach you some of the challenges in medical imaging It's a huge area。

 so I'm going to pick a few examples in the next videos to illustrate some of the problems。

 some of the challenges and some of the rewards when you work in medical imaging See you in the next videos。

 Thank you very much。

![](img/4e10e720ed44e2102ff3a8769dc1d8da_5.png)
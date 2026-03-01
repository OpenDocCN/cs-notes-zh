# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P74：74_08_08_8-附加内容：稀疏建模与分类-活动识别-时长-15-10.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

![](img/60ab5afc80d3f078a8f017874cbf013b_0.png)

Hello and welcome back I want to illustrate now how we can use spa modeling for problems in image and video classification In particular。

 I want address the very challenging problem of classifying or recognizing activity in video for example。

 if we look at this video we want to be able to say there is a person carrying an object if we look at this video we want to be able to say there is a person jumping if we look at this video。

We want to be able to say there is a person running and if we look at this one we want to be able to say there is a person jogging here。

 Of course we want to be able to say all the activities and to recognize all the activities in any video for example。

 here we have a movie of basically a clip of the movie Forest Gump。

 and we want to be able hopefully to say everything that is happening in the movie。

 basically every single activity in that movie。How can we do that with sparse modeling。

 Let's see that。We are going to start from what's called supervised classification The basic idea is that we are going to have a collection of data for training and that data comes with labels so somebody is going to basically tell us this video has this type of activity this video has this type of activity for example we can have this video。

And it comes with its own activity and its own label And what we're going do is we're going learn a dictionary for this type of activity。

 one dictionary per activity or per class Now we can just go and look at all the patches in the video and trying to learn for those patches as we have done in some of the previous lectures but not every patch in this video is actually interesting we need to find and we want to use only the patches that have some information about the activity one way of doing that it's just to take frame differences。

 if we take frame differences when there is no activity that difference will basically be very small and when there is activity when there is a person moving we will have a big difference So we just take consecutive frames and we sub one from the other So one frame minus the previous one and so on to try to see。

Which regions in the video， in the image in each frame do have some activity， let me show you that。

So here we have basically a video of frame differences。

 nothing else than every frame minus the previous one。

 and you see immediately that we can basically take apart those regions that have activity from the regions that do not have activity then what we do is we only look at patches。

Basically regions， let's say eight by8 by5， so we take eight by8 in the frame and five consecutive frames and we look at which of those have high energy。

 basically have more non-zero coefficients or enough high coefficients that we define they go above certain threshold and they have some energy we pick only those patches and with those patches we learn a dictionary for that class so this is the dictionary that we learn is of course dictionary in time because we have used patches that are let's say eight by8 in space and five in time Now this dictionary is for this class Now we take a different class we take basically videos from a different example and we go and do basically the same we learn activities for this one we take the video it's just a different activity。

So we take frame differences。 We take all the patches that have sufficient energy。

 and we go and learn a dictionary for them。And it is。

Way we have now a dictionary for class two and another dictionary for class one these dictionaries are adapted to the class and we continue doing that for every single class that we have in our database for training we basically are going to have another class here。

Of a different activity， and we are going to have another dictionary here for that activity。

And we do that for as many classes as we have。 Now， what we end up having at the end。

I's basically a large dictionary that is the concatenation of all the previous dictionaries。

 so we put every dictionary one after the other and like a block and then we have a large dictionary now we actually know that every block belongs or represents a different activity and that has been the training supervised because we have labels for every single one of the classes we created one dictionary they came with labels we're going to talk about unsupervised in a little way。

Now when a new video comes in we want to classify it。

 that's actually the goal of this learning how do we do the classification almost identical to the way we did the training but now we have the dictionary ready so basically a new video comes in。



![](img/60ab5afc80d3f078a8f017874cbf013b_2.png)

a new video comes， for example， any of these type of videos。We do the feature extraction。

 in this case， very， very simple， just frame difference。Then we go again to every patch。

 three dimensional patch in space and time， and we encode every single patch that has sufficient energy as we did in training when coded with this dictionary。

But now we remember that every block in the dictionary represents something different。

 so we're in coding with that dictionary and then we look。

Actually which regions of the dictionary were actually active Let's say that when I encode this video。

 most of the energy of the code that I produce is in the second block that means that the video is from the second class if most of the energy is in the seventh block then basically this is from the seventh class so basically we look at for example the L1 in every single wall in every single block and we pick the one that has basically the maximal energy there are many ways to pick the right block but the basic idea is that we although we are encoding with a large dictionary this dictionary is the concatenation of multiple dictionaries and then we need to observe which one of the blocks of this large dictionary is the one that is most active and that basically tells me。

Which one is the class for that video， Very， very simple。

 We are basically doing dial learning at training stage。

One dictionary for each one of the classes and then we're doing just encoding。

 sparse encoding and then we say which one was the one that you like the most that's your class。

 very， very simple algorithm that basically achieves some of the best results that has been have been published for this type of activity recognition challenges。

 let's see some examples。The examples I'm going to show you are from a database of videos collected from YouTube Every area of classification has standard databases that the community uses to test their own algorithms and this is one of the most popular ones。

 It has a lot of variability are just videos downloaded from YouTube So here are some examples。

 for example of basically two different videos of a person playing with a ball just soccer playing and of course we want to be able to say this belongs to the same class。

 Some of the videos are used for training。 Some are used for testing。 we also have people jumping。

Just kids jumping here， and we will call these basically the same class。

 although the videos are completely different， we know that it basically is the same activity。

 We also have basically bike riding。And we have just examples of horse riding and examples of basically。

Diving in a swimming pool， so different type of activities， we basically train dictionaries。

 one dictionary per activity， and then we have a new video and we say which dictionary you like the most。

 the one you like the most that's your class Let me show you some results。

And the way I'm going to present you the result is what's normally called a Conci matrix。

 so here we have all the different activities and here we have the activities in the same order。

And in every row we basically see the percentage or the probability of doing a correct classification and what you want is to be as close as possible to one in the diagonal so 91 here means that basically 91% of the videos of basketball were correctly classified Now there was about 2% that of the basketball that were classified as class2 class2 is biking and then you can have here basically 1% were classified as class 1。

2，3，4，5，6，7，8 as class8 so you look for class8 so that's a confusion matrix it tells you both how many times you have done right。

 but it also tells you what type of mistakes you have done and as you can see most of the numbers are very。

 very close to one this actually some of the best results with this very。

A very simple technique we learn a dictionary per class and then we do sparse coding for the new dictionaries and we get the result and the results are really really good in spite of the variability in activities。

 videota with different cameras， different resolutions。

 different qualities but have common activities and we can actually detect them now this is supervise what happens when we don't have supervised data to do the learning let's talk a bit about that。

Lets us observe this video first and let us concentrate on what's happening on the right which is the ground truth and we're going to see two people here that are running and then jumping lets just look at that I'm going to probably run this video a number of times while I'm going to explain what's happening so the people are running。

And they're jumping。And if you see， basically， there was a box that was green and now became yellow。

 Let's just run it again。It's green that means one activity， yellow， that means a different activity。

 so this is the ground truth we basically when and mark it by hand。

 so how can I use sparse modeling to detect this change in activity very simple and very similar to what we have just done。

We basically start and we take， let's say， a time period of one second and we learn a dictionary for that in the same way that we have just done for the supervised case then we take the next second and we try to encode this new one second of video using the dictionary that we just learned if we can do a good encoding meaning I encode it and basically my encoding vector is various spase that means that that dictionary is a very good dictionary for this new time period of one second That means I probably have not changed activity Now I keep going and then I encounter one second where I try to encode with the previous dictionaries。

And I get a very bad encoding either I cannot reconstruct the video or I need to use many。

 many atoms in the dictionary， meaning my encoding vector is very nonparrse that means that that dictionary that was trained to encode a video with a given activity in a very sparse fashion is not working for this segment of the video that means you have changed activities and what you can do is first of all call this a new activity and then you can actually train a new dictionary and now you're gonna to have one dictionary per activity that you have seen so far and you can keep going and that's basically what we are doing here and on the left is the result the grand truth was on the right again this is unsupervised this is just marked so we can verify if we are doing correct or not and let's see the performance of sparse modeling and as you're going to see。

Left is basically identical to the right， so we automatically were able to detect the change in activity by observing that the dictionary that we learned in the past is' not good anymore for the new activity and therefore we probably have change activity and we can detect this change in a completely unsupervised fashion。

 you can take multiple people and do the same exercise， you can ask are these two persons。

 these two groups of people maybe even doing the same activities， you do a dictionary for one。

 you do a dictionary for the other and you see if you can interchange the dictionaries if you can those dictionaries are good for both activities means both activities are probably the same if you cannot interchange dictionaries the dictionaries don't work for both activities。

 those activities are different so this is one way basically of using sparse model。

For classification very simple learn dictionaries per class and then use them to encode the new data and see how good is that dictionary and according to that you can do the classification so a very powerful and very simple technique for image and video classification Thank you very much looking forward to seeing you in one of the future videos thank you。



![](img/60ab5afc80d3f078a8f017874cbf013b_4.png)
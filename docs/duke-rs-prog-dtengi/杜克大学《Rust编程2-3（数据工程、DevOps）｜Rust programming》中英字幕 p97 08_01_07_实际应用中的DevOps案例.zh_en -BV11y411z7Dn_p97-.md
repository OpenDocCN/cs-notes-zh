# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p97 08_01_07_实际应用中的DevOps案例.zh_en -BV11y411z7Dn_p97-

![](img/77a38b3be86eb0be14d6db6c38ff98ba_0.png)

I want to show you two projects of real world applied DevOs concepts。

 one is from the Cy project in this case the C dash Python project is the Cy SDK for Python now the implementation is not the actual inner workings so this is not interesting。

 but I want to show you a little bit about what happens in the actions portion of it。

 which is the CICD part。So similar to other projects that we've seen。

You can see here that there's a lot of things going on。 There's code QL C and several more workflows。

 Some of these are tests， but several others are not necessarily tests and you can see there is a lot of combinatorial tests going in tests and validation。

 So you have things like testing these Python version with these projects。

 So you can see theres there's Bodo 3 and p27 as well as salary and p27。

 but if can I can keep going you can see the breadth you know the amount of different checks and validations that it's going on here with all of these projects。

 let's take a look at SQL alchemy。 So anything and this will happen9 hours ago Anything that is going on there。

 We'll see five jobs completed。 Let's take a look at of some of these as checking for failures。

 things are getting。

![](img/77a38b3be86eb0be14d6db6c38ff98ba_2.png)

![](img/77a38b3be86eb0be14d6db6c38ff98ba_3.png)

It seems there's different python version， so you can see that this is exploding in a matrix of different case scenarios and you can go in and dive in and exactly see what is going on now I don't have exact dis as to what's going on because I need to sign in Of course I have not sign in so I don't have access to to this but if I was signed in。

 I could probably take a look at some of these things that are happening there。

 So that is a good example of one of the many different things。

 and let's just very quickly take a look at Github and the workflows。

 we haven't seen what those are yet。 but let's take a look at the release one which is a good one because it will list the steps that need to happen。

 So let's see we're going to release it requires it requires to have like some version there and then it goes through the steps of setting up the environment cloning the code using a special token here。



![](img/77a38b3be86eb0be14d6db6c38ff98ba_5.png)

![](img/77a38b3be86eb0be14d6db6c38ff98ba_6.png)

And doing a specific action here that is called the action Prely。

 so this thing right here will take care of everything needed in order to get these properly released。

So all in all like several different things that need to happen here to cut a release and then several different things that can get validated with a matrix。

 different options， different branches， different types of versions now the R one I want to show you is this one from the SeF project again which is the Jenkins instance Jenkins is a CICD platform it is the most popular CICD platform in the world so if we see the amount of tests and validations that these have its it's pretty's pretty compelling we can see here that there's not only ceF builds but there's all kinds of things here that are happening here's a SeF volume and look at the amount of testing that is going on now right here on the left you will see that there's build exeer status。

 what is going on here well these are notes that are waiting to get to build。

These idle notices that you're seeing there are notes are this is a distributed system so all of these are waiting for jobs so imagine if you have a team of 100 developers pushing code all at once well this would get routed one job at a time to do some build and validation some of them have names some others don't but most of them right now they are idle now if I scroll here you'll see that there's a couple that are running this one seems stuck that's why this is red let's take a look at what's going on so usually takes it takes about an hour I would say on average and and you can see here some some are passing some are failing so similar to Github actions isn't it we're seeing some things that are good some things that are not quite good and it gives you a good perspective on things that are happening Now this is why real applied Devs practices are all surround。

Aomation and a continuous delivery， continuous integration platform in this cases。

 Jenkins before it was Github， but it gives you an idea of what are some of the other things some of the capacity that you need to have in order to take care of all of the things and all of these all of these pieces like you can see here there's documentation build all of these things are added bit by bit this project when I actually was contributing to it didn't start like having all of these。

 you could say like probably like 50 notes or maybe a little more like 60 notes all building at the same time we started with one let's do maybe like a couple more then let's add 10 let's try to figure out what is to happen So these are two very good projects One is Jenkins with Se and then the other one is the C Python SD decay for the C projects all implementing checks and validations that are very good examples of。



![](img/77a38b3be86eb0be14d6db6c38ff98ba_8.png)

IDevelops in real world projects。
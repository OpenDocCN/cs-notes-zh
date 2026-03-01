# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p148 59_04_04_Jenkins平台概览.zh_en -BV11y411z7Dn_p148-

One of the most popular CicCD systems or platforms in the world is Jenkins and what we're going to do today is going to run Docker and port 8080 to port 8080 so like it's going to buy the voltage expose port 880 I'm going to use Jenkins and the LtS。

 there's many different ways of installing Jenenkins we're not going to go through the process of installing it。

 but certainly I'll show you how I tend to run it I've already run that before so you won't see that I'm pulling the images this has initialized this is key and this is why I'm showing you the logs because the first time you started up you will have this little token that you need to actually proceed for the installation so I'm going copy that and then head over to my browser which I already have running on port 8080 I will have to reload this and once I read。



![](img/1ac6c1ded9d4dd7b4e787f8b59b5d48d_1.png)

![](img/1ac6c1ded9d4dd7b4e787f8b59b5d48d_2.png)

You will see that Jenkins is locked down so let's just make sure that I have these good zoom there and I'm gonna put that special token that I just based and I will say no。

 I don't actually want to do that I don't want to select many different plugins。

 but I think those those are fine and this will go well these will still go and install several different plugins by default fold Now let's let's take a look at what's going on here。

 we have Github pipelines pipeline support we have SS we have Github branch source so there's deep integration with Github as well if you want to have something that is external that is not running at all on Github perhaps you're doing some private projects or you want to have some specialized things that depend on a local bill server Well Jenkins is a good option Now let's just wait a second until all these complete。

And the dashboard ends uploading Okay， things have completed。

 I'm just going to go very quickly here and put some bogus things and so that I can go very quickly just for admin I'm going to skip the email address。

And I'm going to say， save and continue。I'll probably want an email address。

 So let me give you some something bogus here， sample that org and save and continue and then be on my way。

 This instance configuration step right here is useful if you're behind a web server， we are not。

 we're just running it directly。And yes， I want to start using Jenkins。

 Everything's good and this is what you're greeted with。 We'll have some security。

 perhaps some certain things that we need to set up an agent。 I'm going to dismiss these for now。

 but this is going to be very very similar to what we've seen before。

 So what we're gonna have here is going to have a build queue So if you have many different servers and many different tasks of doing those will start appearing right here。

 right now we have to build executors and this means to notes that are actually doing work。

 So Jenkins has a way of distributing the work in this case this is a sole standalone server which by default comes with these two executor。

 So if we wanted to have a new item and we have like a freestyle project we'm going to say test。

When I say okay and then we're going to be greeted with this informational screen。

 we're going to say this is okay for now no code managing build triggers。

 we've talked about build triggers before it can actually pull yoursource repository you can have a GiHub hook so if you Github makes a change。

 then this will take a look at that or wise you can build periodically or trigger builds either from scripts or at a certain timest。

 but you can actually add your steps here so say for example when I execute a shell we can say echo success and we can say save and then that's our job we can actually build right now and the bill will start showing up right here so it took almost no time because I mean I didn't do much and you can see here the output so very quick very easy to set up to work with you can see now our test job appears right here。

And the components are really similar， it's just once the CICD system。

 in this case Jenkins is up and running， you need to find where do I define my jobs。

 how do I configure them where they're going to run and if I have many things running what's the Bill queue so there you go that is a very easy and straightforward way to start and playing with Jenkins and understand what are some of the components that Jenkins has。



![](img/1ac6c1ded9d4dd7b4e787f8b59b5d48d_4.png)
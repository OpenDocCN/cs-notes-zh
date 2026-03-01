# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P67：67_05_11_AWS Cloud9中Hugo自动更新.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/03a3fb64026ed1736fea3f6b05520f42_0.png)

Hi， my name is Noah Gift， and I'm an adjunct professor at Duke。

 I'm also an executive in residence there， and I specialize in data science and cloud computing。

 and today I'm going to be giving a talk on Hugo helping humans at scale through continuous delivery on AWS。

 One of the topics I'm extremely passionate about is relooking at technology and taking a different lens where we look at the stakeholders。

 I think the last 1020 years。 we've seen that there has been really this idea that startups are only good technology is only good。

 But then we look at the effects on society。 people believing things that aren'true that are clearly easy to debunk problems with getting people vaccines。

 there's been this proliferation of misinformation and disinformation and there's been this metric of user growth and engagement as in and revenue is evaluation as the things that we value in society。

 But I think it's time that other。😊，Parts of our society fight back。 and we。

 and we use our own resources to spread actual true information， true facts。

 And one of the ways you can do this is by using a technology like Hugo。 Hugo is open source。

 It's easy to deploy。 You don't have to pay anything to a hosting provider。 If you don't want to。

 You can do it all yourself with your own two hands。 and you can actually spread accurate。

 meaningful information at a global scale。 So you can build a website as big as the Wall Street Journal or the New York Times yourself and actually have a bunch of facts that continuously get deployed into a production based environment。

 So that's really my。My challenge for people that are listening to this are that you can actually create a difference in the world by spreading information。

 And Hugo could be one of the vehicles that you use。

 So I'm going to go through and walk step by step through some of the processes that I've used personally for websites with Hugo。

 And I challenge you to try to make the world a better place by spreading true and and facts throughout the the world and making humanity better。

 All right， Let's go ahead and get started。Let's take a look at this Hugot site process here of continuous delivery on AWS。

 And really， let's start at the beginning here。 First on the source code section。

 what we could do is develop a local server workflow。

 and this could be in an environment like either AWS cloud 9 or potentially Github codespaces or some other cloud based environment。

 maybe the Google Cloud， Azure cloud， it could be your desktop as well。

 I personally prefer to use cloud based development environments。

 and I would go through and get this running locally。 first。

 making sure that I've got everything set up。That I've actually got everything that would be deployed in the cloudbased environment running in my my environment that's a mimic of this。

 And this is really what the cloud 9 environment does。

 it's an exact replica of the kind of environment that I would run later Now once I've gone through and I've pushed my code into Github I can actually listen via the build server and the build server would go through here and actually trigger a new deployed process every time it changes is made in Gitthub。

 Now the great thing about this process is that with the 80bu cloud9 environment obviously I can push the code in。

 test the changes locally with a local Hugo server here and make sure everything looks right or if their small contentbased changes。

 I can just edit directly from Github。 and those changes can automatically be deployed。

And here's what we get into the AWs code build process。 and the AWs code build process。

 What it will do is it could create an item potent infrastructure command。 Now。

 it could be in C sharpharp， which is a language I like， it could also be in Python。

 which another language I like。 It could be in Typescript。

 you could basically programmatically control the deployment in an item potentent way。

 And what this means is that every time you make a change， it'll always be the exact same change。

 no matter how many times you deploy。 So you know that your website is in a solid condition potentially read only so that no one could ever break into it。

 you would then go through and build your Hugo site sync those files directly into。

This S3 environment。 and then this would be really the basis of your website。

 The only thing left to do would be to have route 53 lock in the bucket and then also talk to the 80buush cloud front。

 which is the CDN。 and the beautiful thing about this workflow is you can deploy everything within just a few seconds。

 Okay， let's go ahead and take a look at how we would do this。 Okay。

 let's take a look here at my personal website， Noagi com。 I can move this down a little bit。

 And in general， the idea here is that whatever I want to continuously deploy this website。

 all I need to do is go over to my Github repo here， look at the repo that has my code in it。

 knowagi website。 and I can just if I want edit directly inside of this website。Add content， courses。

 whatever it is， I'm building it out and automatically will' deploy this into the website up here。

 So this is really the beauty of how this works。 In fact。

 just to let you know how simple it is to make a change。

 I can actually even edit potentially the readme itself and just say， you know bump deploy。

And if we go through here and we bump the deploy， I didn't make any content changes。

 but it'll trigger the build。Could build。You can see that it's the point successfully and that if I select this。

 this process is going through and building out in real time exactly what's happening inside of my。

 my project。 So this is one of the really nice things about。Using this continuous deployment process。

 and I type in gift。 Here we go。 We can see this was just deployed recently latest build。

 and I can even start it again manually if I wanted to and I can even look at the logs in detail。

 which is， which is kind of neat。 And and this is gonna show a step by step what to do。

 So how do I do this on my own if if somebody else wanted to reproduce what I did。 Well。

 to start off with， I would recommend going into AWs here and creating a new environment。

 So let's go ahead and do that， We'll call this Hugo。



![](img/03a3fb64026ed1736fea3f6b05520f42_2.png)

![](img/03a3fb64026ed1736fea3f6b05520f42_3.png)

And then inside of here， I like fast machines， so I'm going to select a slightly bigger machine here。

 so it'll be a little bit responsive， so 16 gigs of Ram。

8 CPU that looks good will use Amazon Linux because that's what the AWs code build will use and notice that it'll time out after 30 minutes for me。



![](img/03a3fb64026ed1736fea3f6b05520f42_5.png)

And go ahead and create this and now what's great is that I can start developing in identically the same environment that the build system that will push the code to S3 will actually use and this is a huge advantage of the AWS Cloud 9 environment and it's actually a very good environment to build in。

😊。

![](img/03a3fb64026ed1736fea3f6b05520f42_7.png)

All right， so we've got this thing set up here。And a few different things to point out is that I have a shell right and this is a bashbased shell and it can do really anything that a regular AWs environment can do because I have the credentials set up here automatically in a role based privileges so I can actually interact with the AWs ecosystem and even sync my Hugo site directly there。

 So all right， let's go over here to Hugo to the latest release go down and grab a 64 bit tar file。

 let's go ahead and say copy link address。

![](img/03a3fb64026ed1736fea3f6b05520f42_9.png)

![](img/03a3fb64026ed1736fea3f6b05520f42_10.png)

And then go back to this environment。Go ahead and say W get， pull it down locally。

 Now I just need to uncompress this thing。There we go。 And now it's really just a one liner。

 I can just say pseudo， C P， Hugo。Let's go ahead and put Hugo into user。路过。Been perfect。

 Now that it's inside of there。 if I， if I go ahead and I remove the rest of this stuff inside of my environment。

 I'll remove Hugo。Or remove Hugo。The tar file， and I type in which you go。



![](img/03a3fb64026ed1736fea3f6b05520f42_12.png)

We can see the user local band Hugo type in Hugo version， here we go。

 and we got the latest version of Hugo。 Now what the next thing that I would recommend to do is actually go to the quick start here and let's follow the quick start guide。

 So pretty easy to get started with it。 we can say this Hugo new site。



![](img/03a3fb64026ed1736fea3f6b05520f42_14.png)

There we go。That worked out pretty well。 Make this a little bit bigger。

So we've got this new site here， notice the structure， we have a content。

 we have the themes that canfi file all that stuff Now we'll want to go ahead and follow exactly what they say。

 which is let's go ahead and CDd into that quick start directory and let's go ahead and say get a knit。



![](img/03a3fb64026ed1736fea3f6b05520f42_16.png)

![](img/03a3fb64026ed1736fea3f6b05520f42_17.png)

As well。 And then finally， let's go ahead and add a theme so we can copy this part。



![](img/03a3fb64026ed1736fea3f6b05520f42_19.png)

There we go。 Now that we've added the theme， we can actually echo it into the config into the config file。

 which will allow us to run it。 And now we can just type in。



![](img/03a3fb64026ed1736fea3f6b05520f42_21.png)

![](img/03a3fb64026ed1736fea3f6b05520f42_22.png)

嗯。Really， the last step， which is to add a new post。 Let's go ahead and do that。



![](img/03a3fb64026ed1736fea3f6b05520f42_24.png)

Let's type in new post。Perfect now if I go to content。

 I go to post the big thing to do as a takeaway。Is that we want to make it not a draft because those won't publish。

 well say false。And then we'll also say here， Holello world。Hello world。

 And then're we're pretty close to being able to run。 We just type in Hugo Ser。I believe D D。

 and this will serve it out。 Now to test it out。There's a couple of different ways to approach this。

 I would just open up a new shell first， so say new terminal and just curl。The address that shows up。

 which is local hosts 1313。And we can see that it's， in fact， running in Hugo is， is still running。

 building。 Everything's working properly。 Now， one of the things that we can do， though。

 to fully view everything that's happening is to go into。Our other environment here。

 let's go ahead and go to AWS。

![](img/03a3fb64026ed1736fea3f6b05520f42_26.png)

And let's go ahead and go to E2。 And let's actually open it up so that we can see what's happening。

 And so in this case， if I look at the Hugo deploy here， this is the website。

Hosting environment that I'm working in currently。 And we can see this is the public IP address。

 but we can't access it because EWS is secured by default。

 So what we'll need to do is go to security。Go into the security details here。

Go into the group and scroll down to edit inbound rules， and we'll add a rule that says custom。0，0。

 and for port 1313。And this will allow anybody to go through and view our website remote。

 which is what we want。

![](img/03a3fb64026ed1736fea3f6b05520f42_28.png)

And the only other thing we'll need to do is make sure that we have the right IP address。

 that's one thing。And I can go ahead and replace this right here and put in 1313。

 but it won't run yet。Because of the fact that we need to tell Hugo itself to bind。To that port。

 So we'll have to do dashache bind equals， and we'll have to go ahead and say0 dot 0 dot 0 do0。



![](img/03a3fb64026ed1736fea3f6b05520f42_30.png)

And if we run that and we go back， we should have our Hugoat running and notice here's the hello world latest post here。

 Now， if we want to change it in real time， very straightforward to do because I'm inside of cloud 9。

 we can say this is from。

![](img/03a3fb64026ed1736fea3f6b05520f42_32.png)

![](img/03a3fb64026ed1736fea3f6b05520f42_33.png)

![](img/03a3fb64026ed1736fea3f6b05520f42_34.png)

Cloud 9。Save it。 Notice it automatically builds it。 We go back here。 look。

 automatically updates our website。 So this is an amazing workflow that is is really easy to get started with and to develop your code locally。

 Now， if you wanted to then go to the next step。 like I did。

 All you need to do is push it to a Github repository， like I'm doing right here。

 let's go ahead and walk through some of the things that I did。 So I have my content。

 Everything's the same over here。 I have my theme。 all this。 And really the secret sauce here。😊。

Is this build spec do yaml file。 This does the majority of the work。

 And let's go ahead and see what are the things that I do。

 So I copy the latest Hugo release or the one that I was using at the time I built this。

 I do similar things to what I did in this environment。 I then go ahead and say Hugo。

 which builds the website and then I sync the code by using AWS S 3 syncnc command。To my bucket。

 which is the same as my name。 This is really a key here to get route 53 working。

 I then do a replace of all my content。 I do a cache invalid for a cloud front， which is the CDdN。

 And it's really just those three steps， AWS S3 syncnc。

 and go through and do the cache control replace and then go through here and do a cache invalid。

 Now， how would we actually go through and take a look at this in the real world if we go through here and we look at Amazon S3 here。

Let's look at the website that I've got set up。 It says publicly available or accessible。

 We have properties。 And if we scroll down， what are the things that make it happen。

 One is that I've enabled。This feature of AWS static website hosting very easy to do。

 you just say edit Once you've done this， you can take this bucket website endpoint and you go to routeute 53 and you just add that into your route 53 address。

 which it is actually inside of here if you wanted to play around with it and look at it You can look at the service。

Route 53 and actually configure that yourself。 The only other thing that is。

 is probably important to be aware of is that you have to create a bucket policy。

 And so in this particular environment here。The other thing to be aware of that I did was under the permissions。

 I have actually a policy that's a read only policy this lets people read the access to my website once I've got these two things set up the policy and the static website hosting that's linked to RAph 53。

 the only other thing that we would need to do is go over to cloud 9 and and I'm sorry into code build and make sure that code build is actually building out our project so you'd say go ahead and create a new build project。

And a few things to point out in this build project would be that you would want to point it to where your code lives。

 it could live in any of these locations， S3 code commit， I would probably recommend GitHub。

Go ahead and select a managed image， I would say use Amazon Linux 2 because that's the same as the environment that we're building in。

 go ahead and select the latest runtime and we're not using Docker so you don't need to do this。

 but you would need to select a new service role in IAM that has the ability to copy data into S3 as well as communicate with Cloudfront。

 So this is something to be aware of in order to do that you would need to go over to the IAM system。



![](img/03a3fb64026ed1736fea3f6b05520f42_36.png)

And we go down here， and we go to。

![](img/03a3fb64026ed1736fea3f6b05520f42_38.png)

Theam。The I am system here。Step at I。Let's go to all services。And go to IM。

The IEM system is where you can actually go ahead and create a role that would actually allow you to do that build process。

Finally， you would use the build specaml file and this would actually allow you to push the configuration change to production and continuously deploy your code。

 One last thing I'll point out is once you go down here to whatever repo notice that you should select Gi submods。

 All right， that's it。 Also all we have to do to get Hugo working in your AWs continuous delivery environment。

 let's go ahead and recap the steps。 So step1 would be make sure you have an AWS account launch a cloud9 environment。

 Step two is I would set up your Github communication， So create some keys。 we didn't go over that。

 but it's pretty straightforward to do once you've done that go ahead and download the latest Hugo file In this case。

 I downloaded the latest version and uncompressed it and copyied it into user local bin。

 Once you've done that， go ahead and create a new site with the quickstar guide。

 add the submods that will give you the Hugo。

![](img/03a3fb64026ed1736fea3f6b05520f42_40.png)

ThemeAnd then go ahead and run it locally and do a curl to make sure it's working。

 then go over to the security groups， make sure that you open up the port 1313 so that you can actually expose it to 000。

 then go back， make sure that you can do that workflow Once you've got that working that could be your development environmentnament and you can go back and forth and get it get it running locally and get the site exactly the way you'd like。

 then simultaneously I would go over to AWSS3 create a static hosting scenario there so you can go ahead and follow the official documentation for AWS。

There's a very good how to guide on how to set up the permissions correctly。

 And then actually from cloud 9， you could even just copy those files over there if you wanted to to just test it out before you set up the continuous delivery process。

 Once you've got the manual copying of the data in there。

 then I would go through and do the AWs code build process to do the continuous delivery。

 So really a very straightforward process to set up a global scale website that is on par with something like Wall Street Journal or New York Times。

 Okay， good luck。

![](img/03a3fb64026ed1736fea3f6b05520f42_42.png)
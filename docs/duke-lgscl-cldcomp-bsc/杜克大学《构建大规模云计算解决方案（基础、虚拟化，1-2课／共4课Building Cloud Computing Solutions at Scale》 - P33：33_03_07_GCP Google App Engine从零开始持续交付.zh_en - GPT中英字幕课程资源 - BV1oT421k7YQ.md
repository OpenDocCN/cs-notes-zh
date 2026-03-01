# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P33：33_03_07_GCP Google App Engine从零开始持续交付.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's dive into a project that will allow us to really kick the tires on doing continuous delivery。

 So what are the core components for GCP continuous delivery First。

 there's a app yal file and what this does is it tells us what runtime we want to use Next up there'll be a cloud build yal file and this will tell the cloudbased build server how to deploy in this case it'll be very simple。

 It'll be basically G cloudud app deploy。Next up we can look at a couple other things we have the actually application source control so there's a really simple application here that has a route that just returns hellello world and then this route if we pass in a name it just returns it back so really simple application here and then there's some requirements file that has the actual packages is going to need so that's really all you need to do to set this up and so what I'm going to do next here。



![](img/1257d08258d80e0c6053322c44afb583_1.png)

Is I'm going to actually deploy this application into Google Cloud。

 so let's go to Google Cloud here and let's go ahead and create a new project。

 we'll do this from scratch and we'll call this cloud data。Continuous delivery。There we go。

 and let's go ahead and create that。Great， now that did that。

 I'm going to go ahead and close this terminal to tell it to use this project here。

 and then I'll open up a new cloud shellll。 And this should activate that project So you can see here that now that's activated great。

 So really the next step here would be for me to clone that repo if I didn't have it already cloned so I could actually go through here and potentially maybe even make a directory called you know my。

😊。

![](img/1257d08258d80e0c6053322c44afb583_3.png)

![](img/1257d08258d80e0c6053322c44afb583_4.png)

My delivery， something like this， will change into here and we'll get clone this。Perfect。

 and then I will see the into this。And again， we should see that same structure here right we've got everything ready to go so really the next step here would be to do a initial app engine deploy and what I would typically do is first create a virtual environment so let's go ahead and do that go here and say virtual environment。

And we'll say Tilda， we'll call this dot CDd。Great， let's go ahead and source that。Been activate。

And then I'll do a make install。And this will go through and install my packages。

 And then the next thing that I'll do is I'll say Python main。

 And this allows me to run this locally。 and this is really the power of using this cloudbased development environment notice it's running on porch 8080 I'll go ahead and select this icon web preview and it'll let me preview this application。

 There we go。 So we got hello world working。 that's great。

 So next step would be to configure Google App Engine。 Great now that we've got this setup locally。

 I can run the native cloud commands， I can run G cloudud。😊，App deploy。

 and this should go through here and allow me to select an environment that I'd like to deploy this to and let's go through here and say US Central。

 so we'll select 14。

![](img/1257d08258d80e0c6053322c44afb583_6.png)

And then it's going to go through here and automatically deploy this project for me so really as long as I have that initial structure it'll go through here and automatically look at the YamL file。

 which is my runtime and then set this up and deploy it。Great， now that it's deployed。

 I can check it out by just going to this URL and it's already in production。

 ready for me to test it out。

![](img/1257d08258d80e0c6053322c44afb583_8.png)

![](img/1257d08258d80e0c6053322c44afb583_9.png)

Perfect， and I can go to that route here。 if we look at the source code。

 let's see how the source code is。 it says there's a route called echocho name。 Okay， great。

 let's try that out。 let's go through here and say echo Fo there we go， new name Fo great。

 we got a working application， but you know it would make it even better is if I could actually edit this code and it would automatically deploy the changes using continuous delivery。

 Well， fortunately， we can do this using the Google Cloud platform。 Well。

 what we'll do is we'll go to a service called code build or cloud build。



![](img/1257d08258d80e0c6053322c44afb583_11.png)

![](img/1257d08258d80e0c6053322c44afb583_12.png)

There we go， CloudBuild。And what we'll need to do is hook this trigger up。

 and so we'll select trigger。And we'll say。We'll scroll this down a little bit here and go to createre a trigger。

And we'll say cloud delivery。Say this。This will auto deploy。All right。

 and then we will need to decide how to actually do the deploy automatically。

 I'll say every time I push a new change， automatically trigger this。

 and then we're going to select where this is from notice。

I talked about this earlier but the master branch here would be this particular deploy if I wanted to do a different environment。

 I could do a staging environment， I could do a production environment and the branch itself could have a different build job and that's how you would do many different kinds of deployments Great so that looks good I'm going to go ahead and connect a new repository and I'll tell it I want to talk to my Gitthub account。

Once I authorize it， I'll just need to make sure that I've selected the right account， there we go。

 GCP flask email deploy， perfect， let's go ahead and connect that。And we'll go ahead and say。

 create push trigger。There we go， it's ready to go so the only thing I'm going to need to do here is I'm going to need to go to settings。

And I'm going to need to enable a couple things。 One， I'll need to enable app engine admin。

 So this allows the build server to， to actually， on my behalf， do the deploy for me。 and I'm also。😊。

Is currently disabled， so let's go ahead and do that， let's go ahead and enable that API。

There we go so this basically me tells app Engine that I can make API calls in this project。

And in addition that the cloud build service itself can make those API calls right so I can tell it that。

 yeah， you can do deploys for me and I also want a service account as well so that it can actually do this on my behalf。

 So those are the two settings， App Engine and then service account and also the app engine API has to be enabled。

 Great， once that's done， it's as simple as me going back over here and actually changing this source control So if I go to the main file I can go ahead and say edit this。

 And let's just try something else we'll say hello world。CD like that。

 we'll just change it a little bit。And I'll go ahead and say testing continuous delivery。There we go。

 and this should trigger build。Let's go back to this， let's look at the history。And。Here we go。

 this one is running。And you can see what it's doing。

 So it's initializing the code it's redeploying the changes and it's doing this automatically。

 So if I was working with a team of developers， I could also add in a L step。

 I could maybe do a little bit of cleanup or add maybe some kind of a unit test。 but in general。

 this is a fully automated continuous delivery pipeline that really took just a few minutes to set up。

 So let's go ahead and watch this， make sure it looks like it's done looks like it's working here。

 and when it's complete， what'll happen is I can go back to this target URL and if I refresh once this is done。

 it should show us that it has a new hello world message。

 which has the words continuous delivery inside of it。 So looks like it's working successfully here。

 great。😊，This looks like it's good。And again， I'll just go in and grab this URL here so we can test this out。

Put this in。So it's not refreshed yet， but let's refresh it again， maybe it's complete now。

There we go。 So we've got a full working continuous delivery。 So in a nutshell。

 setting up continuous delivery is fairly straightforward in a cloud based environment。

 And really it's a best practice for projects。 And if you use something like flask and you fork this project that I set up your GCP flask and I' deploy it's pretty straightforward to test out。

😊。

![](img/1257d08258d80e0c6053322c44afb583_14.png)

![](img/1257d08258d80e0c6053322c44afb583_15.png)
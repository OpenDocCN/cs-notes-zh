# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p116 27_02_02_安装ELK技术栈.zh_en -BV11y411z7Dn_p116-

![](img/438a69299c7389f9e03d0e78b007c9f1_0.png)

Let's see how we can install the ek stack in a Dviian based machine。

 This is a Linux based machine and we' gonna install like an all in one and before we start we're gonna take a look at what do we have here and it's a to 2004 longter support version and that is what we're going to be using so lets let's very quickly go through the steps and these are all coming from the documentation that we'll go through in a second All right so first let's get let's set up all of the keys and dependencies we'll start by getting the GPG key from elastic search。

And then we need to install or ensure that app transport H TtPS is installed。

 So this is a dependency for getting everything in orders。 I'm going to type in transport。HCTPS。

And then that will take a second and let's just wait until that complete。

 All right that completed and the next step is adding adding or creating a list So the list and I're going to paste this here。

 which is a very long command allows to put everything together the keying like where where the package is coming from in this case it's coming from artifacts that El that CO and when hit return that's almost immediate and now the first thing we're going to do is we're going to install no longer app transportationtps we're going to install elastic elastic search so we're going to do that and you might get in travel here because you might see that it's unable to locate the package Now when that happens it means that the repositories in the list that we just add those need to be updated so we need to run pseudo update and update everything。

Well see that elastic is now getting pulled in and now we can actually go ahead and run elastic search and that will take a quick second and we'll pull everything and build and install the package and then we'll continue on the other packages for the El stack Okay that has finished and there are a couple of things that you need to take into account First is the generator password for the elastic built in super user。

 you can change these later but it's useful to capture that like this is a secret token you can't or you should not。

Share it out。 you have to keep it in in a very secure place。

 perhaps a password manager for sure you can if it's going to join a cluster we're not in this case then you can follow the instructions right there you can reset the password again and then you can do an enrollment for Kivaana which we'll see later al right。

 so we've installed log stash next is we need to install。Kvaana Kivaana is the front end。

 the dashboard and that's going to pull the packages for Kivaana and we'll wait until that completes。

 All right Kivaana completed now let's install logtsh and logtash is going to also take a second so let's install that as well and wait until ecomple All right so that complete it install and so now let's go ahead install file bit。

 which is the last piece that we need here。 Allright so that will be usually faster than everything is we've install and we'll have to wait until that completes as well。

 Okay so now we need to start enabling and activating some of these services and we're going to do this with system D So let's start with let's see if system CTL is available in our on our path it is perfect so we can do pseudo system CTL and demon reload So that command will ensure that everything is red。

And now we can start enabling these services， so let's start with Elastic search and that is Elastic search that service。

And that will create a link perfect now we need to enable file beat。File it is there perfect。

 And next up is locktash that service。 you might see that some of these are that service and some of some others are not。

 And then we have also Kivaana that service perfect。 So we have。Logt Kivaana service。

 So now I'm going to start the Elastic search service and I believe I've already done that。

 So if I do P and check if elasticastic search is there。

 you will see that elasticastic search is already running。

 So that's very good next up I need to make sure that Kivaana is running。

 So let's do start and then Kivaana that service。And then do P S and Gr for Kivaana。

 I'm making sure that this is already started。 So perfect you can see it's right there。

 and Im going to do the same with the lock stash service。 So log stash。That service。

 And make sure that。That is also running。And that is running perfectly。 So no， no problem there。

 And finally， we are going to do the same for。For file beat。 But let's， let's make sure。

Let's make sure if file bit is not already running and file bit is not running。 So allright。

 so let's just get get that started。 Allright， I'm gonna clear my terminal here。

 I'm gonna make sure that I can start file bit。 F bit has started。 Let's grab for it again。

 and now it is it is there perfect。 So we have configuration。

 Well we we don't have configuration yet。 and we have everything we need。

 So now what we're gonna do is we're going to install how about we install the Nng X servers。

 We're going to do solu cache。Search engine X to make sure that we have the actual engineng X server and that it is。

 So we're going to do so app gate install engineng X full。

 and we're going to pull those and get N X up and running。

 And the reason I'm doing this is to make sure that we have something that will produce some logs and that we can parse them and look how they are being processed by the whole system。

 Alright， so En X is done and we should now have bar log， Enng X there。

 and we have access log and we can take a look at what it's in access log it should be empty。

 how about error log it should be empty as well。 perfect。 so that is all there are no problem。

 So now what we need to do is actually we can start checking if Enng X is running。It is running。

 we can try doing a curl local host which will get an access there to En next and now we can take a look at access log and now we have an entry there。

 okay perfect。

![](img/438a69299c7389f9e03d0e78b007c9f1_2.png)
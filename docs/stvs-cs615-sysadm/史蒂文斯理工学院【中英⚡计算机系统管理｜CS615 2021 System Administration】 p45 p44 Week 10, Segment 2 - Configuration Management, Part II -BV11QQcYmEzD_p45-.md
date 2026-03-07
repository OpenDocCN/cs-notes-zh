# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p45 p44 Week 10, Segment 2 - Configuration Management, Part II -BV11QQcYmEzD_p45-

Hello and welcome back to C 615 System Administration。This is week 10 segment 2。

 and we're going to continue our discussion of the underlying concepts of configuration management systems。

As we hinted at in our last video where we talked about the abstraction of service definitions。

 we now want to go even further to better understand just how these critical infrastructure services impact the operations of our systems and what important considerations we have to keep in mind in installing。

 running and managing that。Let's look again at our service definitions from the last time。

We had done a decent job of defining with some level of abstraction what needs to happen on a given system that filled a specific role and had noted the concept of inclusion of other modules to build extensible systems too。

 well to do what exactly。To configure our services， you might say。

And when we perform these configurations manually， what do we do？We added configuration files。

 We install packages。And we start services， for example。

But its critical to understand that for a configuration management system。

 the main task is not to make changes。 Instead， it is the job of a C M system to assert state。



![](img/83255cb47d201cbcaeeca78590647429_1.png)

And there is a significant and notable difference that influences how these systems work。

It may initially seem counterintuitive， but when you think about it。

 you really do not want to have specific changes be made on a system。

 but you want to ensure that the host is configured correctly and then apply only those changes necessary to get it to that state。

We know that the entropy of an enclosed system increases with time， so our systems deteriorate。

 and it is the job of the Cm system to bring order to chaos， to get us back on track。



![](img/83255cb47d201cbcaeeca78590647429_3.png)

Here， let us illustrate the states we might care about。

 We start with a system in an unconfigured state， meaning the system does not meet the requirements we have。

 does not have the right packages installed or the right configuration files present。

This might be a brand new system with just the B S installed。 for example。

 our C M system then performs whatever changes we have to find to bring the system into the configured state。

After the C system has run， all required packages are installed， configured properly。

 and all services on the host are running。The system is ready for production。Now。

 throughout the lifetime of the system， we may periodically apply certain changes such as upgrading a package or changing the way a specific service runs and then restoring it。

But with time， things change。Entropy or perhaps users cause our system to deviate from the desired state into a deviant state。

Perhaps somebody made some manual changes on their system or added some packages that now conflict with a service。

Now， our CM system runs regularly and detects this deviation。

 reverse or overrdes such changes and brings back our system into the known good state。

But entropy can be clever and lead us to yet another state。 The unknown state。 That is。

 we are now in a state that is not well defined， perhaps because the C M may have stopped running on the host or may erronely be applying the wrong configuration。

The host may have been shut down。 The network is connected， and intruula may have taken over control。

 or rats may havened through the power cable。 We simply don't know What's worse。

 We may not even know that this host is an unknown state。 Not all failures are immediately obvious。

In some cases， if the C system is still running or if the host is booted up again after having been shut down。

 it may recover by itself， meaning a properly running C system possesses at least some self feeling properties。

But it's also possible for us to determine the status of such work systems in an unknown state by a monitoring and thereby bring those systems effectively into the known bad or tian state。

Now， in some cases， a system may have reached a state where the C M system cannot recover by itself。

So we may rebuild it， thereby bringing it back into the unconfigured state， which of course。

 may also happen to bring back a system from an unknown state。

 either intentionally or automatically via say periodic and automatic rebuilds。

But now note that we have two additional states beyond just configured and the different states of not being correctly configured。

Specifically， a host may be marked as being in service。

 meaning it is ready to accept production traffic for whatever functionality it may offer。

 or it may be marked as being out of service。These states are slightly different from the other ones in that they may be influenced by the C M system。

 but it's also possible that the C M system does not care about this aspect。

 It merely ensures the system is configured appropriately。And so if you have a devviian system。

Your monitoring solution may trigger a change to take the service out of rotation， although。

 of course， that can also be accomplished from the configured state。

This aspect is sometimes managed through a separate supervising service called service orchestration。

Which may bring individual systems into and out of service from the configured state。

And flip them from one to the other based on specific， externally defined properties。

We show these actions as dot lines to illustrate that they may be performed by the configuration management system or by any other means。

Now， this data diagram here may give you an idea of the transitions the system may undergo， but。

 of course， any single host does not operate in a vacuum and C M systems running on each individual host and themselves often orchestrated from a central service。



![](img/83255cb47d201cbcaeeca78590647429_5.png)

Are， of course， distributed systems， Me they consist of components that may be located on different networks all across your infrastructure and which require communications between them to coordinate their actions。

As such， CMm systems are subject to the CA theorem， like any other distributed system。

 meaning we have to consider three distinct and important properties。First。There' is consistency。

 That is， we want to ensure that all systems are consistent amongst each other。

 with each receiving the same updates consistently。Secondly。There's availability。

 The system can receive updates and ensures that the services managed by it remain available throughout the operation。

Finally， there is partition tolerance， meaning the C M system doesn't break down when it can't receive updates and is able to recover gracefully from any such partition。

The dilemma here is that due to the distributed nature of the system。

 we can only always guarantee two of these three required properties at a time。

Welcome to the wonderful world of distributed systems。



![](img/83255cb47d201cbcaeeca78590647429_7.png)

The other important aspect of C systems is that in their effort to assert state。

 it's critical that the operations performed by the C are idotent。

In importantency is the property whereby a function can be applied repeatedly with its own result as input and yield the same outcome。

So mathematically speaking， this means that F of F of x is the same as F of x。

One example of this is the absolute function。If you take the absolute of negative 1， you get one。

 If you then take the absolute of one， you get one， which is the same as the absolute of negative1。



![](img/83255cb47d201cbcaeeca78590647429_9.png)

Now， in our context， this means that you can perform the same operation multiple times in succession and always have the same outcome。

 which is notably different from it doing the same thing。Here， let's look at some examples。

Removing a file has the outcome that after the command completes the file is no longer there。

What if you then run the command again？Well， the command may complain saying something like no such file。

 but the outcome remains the same。 The file resolved at conf is not present。

So this operation is inimant。Likewise， if we write some data to a config file and the manner are shown here。

 then the outcome is the same， no matter how often we repeat the command。

 Each time the file will be truncated and the contents written。

So this is an inimportant change as well。Now， if we change the command to append data。

 then obviously， if we run this command twice， we get a different outcome。

 The file now contains two lines for this name server。 So this command then is not itim。

Changing the owner of a file。Is it important。S is changing permissions。

But what about a command like this。Installing a package should yield the same result if it runs the same command again。

 shouldn't it？ I mean， if the package is already installed。

 then it would say so and the command would be a no op， right。Alas。

 this is decidedly not an inim command。 When you specify to install a package。

 most package managers will go and and the latest package。

 which then may install a different version of the package on each in vocation。

 thus yielding a different outcome。What if we specify the exact package version？In that case。

 we should be guaranteed that either the same package is installed or nothing happens。But in reality。

 we have to admit that we don't know for sure for some packages， execute script at startup。

 some expand configuration files， based system parameters and so on。

So we are unable to make a blank statement here and instead have to investigate in more detail。

 which gives us an idea of the complexity of writing truly in importantant C M recipes or workflows。



![](img/83255cb47d201cbcaeeca78590647429_11.png)

And inotency is， but one important requirement。 It enables some form of self feeling。

 as it causes no harm to execute the same steps over and over in order to bring us into the desired state。

 But do note that this does not mean it is necessarily efficient。

A C system would be considered entirely inimportant if at each invocation。

 it deleted all packages and then reinstalled everything from scratch。

But that would incur a high cost， both in time wasted， as well as in service availability。

So a good C system that needs to try to be a bit smarter。Sure， the changes need to be inimportant。

 but that's really on you。 The system doesn't know what's inimportant， what's not。

 You are the one defining what steps it should take。

But the Cm system should be able to determine whether any of the steps are necessary to be executed。

And then it also needs to ensure that as it performs the changes。

 it will reach a final state that's desired across multiple systems。

That is we require eventual consistency across multiple hosts。

Suppose you want to roll out a package update across all HTTP servers。

What if one out of 10 systems can't apply the update for whatever reason？

Do you then leave that host as is， Then you have9 host that are identical and one that's not。

Or do you roll back the changes on the nine hosts to ensure consistency across all systems？

Or perhaps you apply the change on the nine， but mark the  tenth0th one as being deviant and take it out of rotation。



![](img/83255cb47d201cbcaeeca78590647429_13.png)

Different systems solve this in different ways。 And as you can tell。

 you acquire some notable communications and awareness of the other systems。

 which is why we often integrate with monitoring systems that help us manage the service status。

 such as EG service orchestration。

![](img/83255cb47d201cbcaeeca78590647429_15.png)

So we need to keep in mind that configuration management systems oftentimes not only configure and manage complex systems。

But that they are themselves complex systems that may fail in complex ways。

C M systems are inherently trusted in order to be able to make changes on the host。

 It needs to have the privileges to do so， meaning that， of course。

 C M systems have the potential to really ruin your day to break things to the point where they can't recover by themselves and require manual intervention。

For this reason， it's important to have a carefully planned stage rollout plan for any changes you are pushing out。

 going slowly to incremental sets of systems。With appropriate monitoring and checking and perhaps an automated approach to rollback a failure as detecteds。

This is one of the self feeling properties of many such systems。

 They analyze a success rate of the changes they are rolling out and automatically rollback of convergence cannot be accomplished。

 for example。And of course， you need to keep in mind that whoever has access to the configuration management system has effectively full route access to all systems managed by the system。

So appropriate audits and checks are mandatory here。



![](img/83255cb47d201cbcaeeca78590647429_17.png)

But what functionalityly does a C system really require if we are looking to a certain state。 now。

 obviously， as weve used in know our examples， the system needs to be able to install software。

 So it probably needs to integrate with the package manager and use。

It needs to be able to ensure that a specific service is started。

 restarted and kept running as needed。 This requires an integration with the unit or R C or system D components on your hosts。

It obviously needs to be able to apply file permissions and ownerships。

 as well as be able to install static files to add content to existing files or to generate host specific configuration files from properties of the system or network location。

 etc cetera。But in addition to these requirements， C M systems also often need to have the ability to execute specified commands that go beyond permissions。

 packages or fire management。As well as to be able to collect data from the host and to be able to report its status。

 or just collect the data back to a central service。



![](img/83255cb47d201cbcaeeca78590647429_19.png)

And if you look at this list of functionality。You will notice that your C M system overlaps with a bunch of other important systems and services you utilize。

You oftentimes require generic remote command execution mechanism。A data collection agent。

 as well as reporting infrastructure that allows you to perform actions or collect data based on system properties。

All of this directly intersects with a lot of security， relevant tasks。

Identifying the deviation from a known good state is obviously a critical piece of information in this context。

And you often run regular integrity checks， which really are just one form of one commands and collecting information。

But you also regularly have to roll out software updates and vulnerability patches。

 which really is just one form of applying software updates。And then again。

 you need to be able to move a host into a quarantine or well defined devvit state。



![](img/83255cb47d201cbcaeeca78590647429_21.png)

So we see that configuration management as a system overlaps with and enables a large number of other systems in areas that recorded to the system administrator as routine。

Software deployment， both the initial installation of the O， either onto bare metal or into a VM。

 the building of machine images or containers， as well as the regular updates of software installation of packages as needed for a given service。

The overlap here is directly with your deployment engine or your continuous deployment pipeline。

Your monitoring solution， both for general reporting as well as the frequent but unpredictable data collection needs you might have。

For example， you often never need to run a check across all your systems that say collects the contents of a specific file or checks for the existence of a specific configuration parameter。

Your Cm system may already have this information or can be used to collect it。

 even though its primary purpose is not providing logging and monitoring。

Revision control and Aring changes is another area you intersect with。

 because once you've abstracted the configurations sufficiently。

 any and all changes become code changes， and then revision control benefits applied to software engineering also become mandatory and welcome in this context。

Compliance enforcement becomes possible thanks to configuration management。

 If you have a regulatory requirement to deploy certain changes across all your systems。

 then the C system is how you guarantee such a change。And so on and so on。

So you see the configuration management often provides a foundation for many additional infrastructure tasks。



![](img/83255cb47d201cbcaeeca78590647429_23.png)

Let's visualize these codependencies and intersections because， hey， Venn diagrams are awesome。

We've already mentioned the intersection of configuration management and service orchestration。

But in order to use either one， you first need to know what systems you have。

 It may seem trivial and obvious， but an accurate asset inventory database is a core critical infrastructure component that lists and keeps up to date your comprehensive inventory。

But， of course， not all systems are the same。 So we also need a central place to define the role a given system may play。

 such as H TP server or mail server。But further final grade down to different deployment tracks such as production。

 development， QA or cannerary to test out certain changes。From these defined roles。

 you can then define which configurations are applied and what systems are put into rotation。

Likewise， from here you are creating new instances。

 building new hardware and are installing or deploying software。

Just like your monitoring may differ based on the raw definitions of your assets or instances。

The intersections of these circles here then include specialized topics that may be accomplished by one or the other systems。

For example， the initial software installation and network configuration is likely to be applied by your deployment engine。

 but then asserted as a continued state via your configuration management system。

 while the CM system might collect specific metrics that are then exported to or via other monitoring agents to give just one more example here。

Now， all of this is part of the related topics of configuration management。

 but perhaps you notice that we've kind of neglected one major trend in the industry。

What about containers。Do we really use configuration management in the same manner when we use static。

 small， well defined containers？And the answer here is yes。 and no， or maybe kind of。It depends。

Because you see， containers are different。

![](img/83255cb47d201cbcaeeca78590647429_25.png)

On the one hand， but on the other， they're really not。

 They're just the evolution of the same concepts。Just like with CMm systems。

 where we assert the state of our systems。 So in a way， our containers a state assertion。

Just like before， we need an inventory of resources， of instances， of destinations。

And even though perhaps we no longer manage individual hosts and use one more layer of interaction to manage our containers using specialized software and complex systems upon other complex systems。

 we are back to a certain state。This is because our containers。Really。Ot to be immutable。That is。

 they should not see runtime changes thereby guaranteeing the correct state。

And we determine our state deviation instead of trying to update the configuration on the running system。

 we instead integrate our code changes and deploy an updated container image。

Although it's worth noting that even though Docker and Kubernetes and all those things are quite nice。

 much of the heavy lifting， even in the brave new container world。

 is still done by all the same tools as before。But yes， a mature organization。

 the configuration of runtime systems has moved away from individual mutual systems to generic。

 well defined， immutable components that can be structured and deployed in an automated fashion。 I。e。

 infrastructure as a service。But as much as we've talked about configuration management in the context of service。

It's also important to keep in mind that we have the same need for state assertion and all the other benefits of C M on desktops and mobile clients。

 where we oftentimes use enterprise tools to manage some of the same aspects， but， of course。

 in a different context。As well as in network equipment like routers and switches or in storage devices or load balancers or caching systems。

That is。Everything we learned here can and should be applied there as well。 although admittedly。

 the industry is a fair bit behind in this area and centralized configuration management for these devices is not always as easy as it should be。



![](img/83255cb47d201cbcaeeca78590647429_27.png)

Okay， I think we're coming to the end of this topic。 I now there was quite a bit we covered here。

 So let's make sure we recap the most important aspects for you to retain and perhaps research on your own in more detail。

First， let's keep in mind that we want to move away from individual systems towards clear definitions of the services we deploy。



![](img/83255cb47d201cbcaeeca78590647429_29.png)

That is， we no longer trial to nurse and nurture fragile individual systems that only a handful of people may remember how exactly theyre configured。

 and instead want to move to completely replaceable and exchangeable systems that can be recreated。

 instantiateated on a moment's notice。

![](img/83255cb47d201cbcaeeca78590647429_31.png)

To do that， we focus not on making specific changes， but rather on asserting state。

 defining outcomes rather than how we configure a system。Given the nature of configuration systems。

 we need to remain aware of the limitations and build protections for the different ways distributed systems may fail。

We built state definitions such that they can be reached by applying it important change sets with reliable assurance and yielding a final convergence on a known state。

All of this include significant overlap with other components services and systems use in system administration。

 And you'll probably want to research the topics shown here to take your understanding of the next level。

 as we， as an industry are moving away from specialized services towards a more descriptive way capable of being automated with integrated tests。

 code review and continuous integration and deployment， like any other large scale product。

 In as a service。😊，As you can tell， this larger topic has become one of the most important fields in large scale system administration and has opened up room for a lot of interesting research。

Make sure to check out the links I've included at the end of the slides for this video for additional resources。

In our next videos， we try to cover a number of important aspects relevant to system security。

 Good thing。 that's an easy topic and can trivially be covered in just a few minutes time。

What's that， The can't。 Well， we'll still try to do our best。Until then， thanks for watching。😊，Jes。



![](img/83255cb47d201cbcaeeca78590647429_33.png)
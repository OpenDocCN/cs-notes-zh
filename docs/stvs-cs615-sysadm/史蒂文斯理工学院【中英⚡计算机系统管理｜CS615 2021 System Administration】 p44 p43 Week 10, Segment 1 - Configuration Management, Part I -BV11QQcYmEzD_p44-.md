# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p44 p43 Week 10, Segment 1 - Configuration Management, Part I -BV11QQcYmEzD_p44-

Hello and welcome back to CS615 System Administration。😊，We are now in week 10。

 and this first segment of the week， we're starting our discussion of the topic of configuration management。

This is one of those really interesting topics in system administration that combines all the practices and experiences from managing hundreds or thousands of systems。

 their individual services and everything in between with the broad concepts of distributed computing。

It covers directly or indirectly almost all of the topics we've discussed so far。

 but takes us into a perhaps more academic area of the field。

But let's first see what exactly configuration management is and why we might need it。

As much as system administrators like to joke that the users are the cause of all the problems with the system。

 and that things would be just so wonderful and easy if only we didn't have to deal with those pesky requests with users causing trouble。

 It's important to remember that the system we manage are intended to  fulfill a specific purpose to be useful。

 That is， in order to be useful。 they must be used。Which， in turns， means that they are not static。

Fileites are created， modified or removed， you as log in and run commands。

 services are started or terminated。In addition， the requirements of the systems dictated at least in part by evolving business needs or emerging technologies are changing all too frequently as well。

This leads to new software being added， patched or upgraded。 Use accounts are added or removed。

 Jos are scheduled， or their frequency changed。 Interactions with other systems are enabled to prevent it。

 In other words， our systems do continuously undergo change。On a single host。

 such changes are made by local modification of system configuration files in vocation of specific commands and the installation or tuning of different applications。

And these changes then need to be replicated across large numbers of systems。 Nowadays。

 frequently even make more dynamics through the use of short lived containers and the like。

But as we build these servers， even if we meticulously document every step。

 we need to be careful to not rely on fragile individual systems。

In our discussion about automation of jobs and system centric software development。

 we are seeking increased reliability and resilience through automation。

 which in turn requires us to inventory and document our needs。For example。

 in order to apply a security update to our web servers。

 we need to first know exactly which of our menu hosts are running the vulnerable version and then perform the same steps of upgrading the service on that。

Since we cannot possibly keep track of hundreds of changes across thousands of systems ourselves。

 we delegate the task of applying well defined sets of changes to possibly very large numbers of systems to a class of software known as software configuration management systems。

 simply referred to as Cs。We offend hinted at the capabilities of such solutions before。In week 4。

 we explained that by the time the Os is installed on a host。

 we already have to perform at least a minimal amount of custom configuration。

We also noted that in order to be able to add software on a host。

 configuration management requires a tight integration with a systems package manager。

Another ever changing aspect of our systems was touched upon。 and we talked about user management。

 And in just the last few videos， we've repeatedly stressed the importance of automated systems set up for backup。

 which obviously requires a central configuration that is distributed across multiple hosts with some changes made to account for local differences。

So how did configuration management systems evolve， They all developed to solve this generic problem。

 You have figured out how to correct the configure one server for the intended use case。

 and now you want to replicate the setup to others。And， yes。

 just about every single system administrator I know has undergone the evolution of the systems。

 as I'm showing here， It appears to be one of those lessons that everybody has to learn for themselves。

But anyway， how would we go about this？Well。We might start by copying all the necessary bits from one system to the other。

 and then copying over some of the config files。And then restart the service on the newly set up system。

Cool， we're done。But then you realize that copying all this data around is not very efficient。

Remember what we use in now our backup videos to copy data more efficiently to only sync the delta between two sets of data。

That's right， we used our sync。And so we go ahead and do just that。Except， of course。

 that is a bit dangerous because， hey， your machine may be similar， but they're not identical。

There are some bits that are unique to your system that you can't blindly copy over。

We already knew that， though， didn't we。

![](img/7a20602f63ad64a1d1ca08a90edc7f02_1.png)

That's right。 Remember this slide from week 3， when we talked about the file system hierarchy。

Using this matrix， we get a pretty good idea of which data we can sync easily。

But we also face a distinct problem of having to somehow manage data that we marked as non shareable。

 meaningan we have some files here that are not shareable in that they are identical。

 but they are predictable in their contents and oftentimes can be derived from certain system properties。

So we're talking about doing what computer scientists do best。

 adding layers of indirection or abstraction。

![](img/7a20602f63ad64a1d1ca08a90edc7f02_3.png)

But okay， back to our initial problem。Once we've realized that we can blindly copy things from one server to another。

 we then began to think about pre populating the correct configuration for each destination server in a central place。

And then we start to build a so called golden imageage from which we can deploy all the shareable data。

But where we also keep host specific bits such that only those fight that are relevant to this systems are copied over。

Before we then start the remote service and call it a day。Which works fine。

If you have only a handful of hosts as is sequentially looping over them。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_5.png)

But clearly， we have a scalability issue here。So then we turn the whole thing around。

 instead of pushing data from a single server to thousands of machines， we instead。

Have each server pull the data。Which really is just the same approach， but in reverse， more or less。

And once you've deployed that， you notice that this， too can suffer scalability issues since now。

All of these machines。😔，We'll try to connect at the same time to this little server over here。

So to try to prevent that。😮，You then add a random sleep over here to spread out the load of bit。

 and perhaps you stage out the changes across multiple servers。Or instead。

 you try to switch to more of a Ps up model whereby the server periodically checks if any changes are even needed Instead of thrashing the disc and calculating the checks them for all these files。

Eventually， though， you've had enough and you switched to using an actual configuration management system。

 such as， for example， puppet。But， of course， then you have to spend a fair bit of time actually understanding how to set up your servers。

Before you then install the service， although not after having cursed Java once more with all your heart and configuring the client side as well。

And now everything is pey and all your files are synced until you inevitably run into some edge condition that the Cm system you pick doesn't solve。

 and you go back to step1 where you begin copying files around。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_7.png)

But okay， so regardless of which approach we're using。

 we've already identified a difference in how some of the data is to be handled。

We have the shareable data consisting of， say， some software packages or fixed data files。

And we have system specific but predictably configured files。

 such as many of those we find under the Etsy directory。What does that look like in practice？



![](img/7a20602f63ad64a1d1ca08a90edc7f02_9.png)

Suppose you have your systems distributed across multiple geographical regions or data centers。

 as we discussed previously in the context of business continuity or to minimize distance to your end users。

So， let's say， we have our。US West， US East， Eu North and APpeEC regions or data centers。

 with each hosting the same identical HTP service。Now， each of these systems will of course。

 require its own default route。As but one example of a network configuration。

 but you also most likely want to ensure that each one uses their respective local DNS resolver or Cislog serverver。

 which then means that you have to ensure that E seriesoft。com and etsysslog。

com get configured correctly。For each of the regions。In addition。

 you'll probably have a few things that are common to all of the systems。For example。

 youll probably have to grant access to all of the systems here。

To the developers in charge of the application， but wouldn't want those users to have access to the DNS and Cislog servers。

 meaning you could then enable different accounts based on the server's role。 While furthermore。

 you also have at least some configurations that are the same for all of the systems in your fleet。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_11.png)

In other words， the configuration of your systems can be divided into two broad categories。

 Those aspects that vary based on the system specific placement。

 such as by geographical region or perhaps by network zone。

 and those that are specific to the given task of the service。

Amongst the unique yet predictable properties are then the network configuration oftentimes derived at runtime from。

 for example， DHCP。The various critical infrastructure services we mentioned， including。

 but not limited to DNS， NTP and C log。But also the minimum version of the operating system you are using。

 the user management and things like the configuration of SSH， although， of course。

 there are countless other examples。On the other hand， we also have service specific properties。

 For example， to provide the HP service， you'd have to define and configure across all systems。

 the correct software package， the correct configuration for the Web server， including， for example。

 the Tl S configuration。Which， of course， in turn， requires you distribute the correct deal as certificate and keys。

 or perhaps your database configuration， as well as whatever content your server is hosting。

And of course， just like before， there are a few limits what else might fall into this category。Now。

 having understood what we might want to configure differently here。

 let's see how we can go about defining this in a scalable manner。So here's how says looks over。

 and we might try to describe it in somewhat abstract terms like so。We require log rotation， SSH。

 the admin accounts we mentioned previously， and then the actual configuration of Cis log itself。

Different CMm systems use different syntax and languages to represent such concepts。

 but to give you an idea。

![](img/7a20602f63ad64a1d1ca08a90edc7f02_13.png)

Here is an example of how such a puppet resource might be defined。 As you can tell。

 the system uses a domain specific language that's reasonably self explanatory， defining。

 for example， that a given software packet should be installed and be kept up to date。

That a specific service should be kept running。And what the various permissions and ownerships are to be on the relevant configuration files。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_15.png)

Now to enable admin account on these systems， we would have to provide another definition as this is a separate from the Cilog specific tasks。

And the example shown here is using a chef cookbook， which uses a ruby like language。

 allowing you to define resource parameters in a dynamic fashion。

Then to round up our quick demonstration of a different configuration management system examples。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_17.png)

Let's use Cf Engine to illustrate how you might define the SSH relevant bits。

As I'm sure you'll have noticed， these different systems are rather similar in how they structure their data and definitions。

 making it reasonably painless to move between them once you've internalized the general concepts。

Now obviously you'd not be using three different CM systems here and instead to everything using the system it chose。

 but I wanted to provide you with a simple and quick look at the commonalities here。

So now that we've defined our S log service， we can then repeat the same thing for our DNS service as well as our HTTP service。

But of course， you will have noticed that each of these does not define the log rotate in SSH services itself。

 but instead uses an include directive。That is， with a proper CM system。

 we can abstract specific components and reuse them。

So that we then might have the log rotate functionality specified separately。

 just like the SSH service。But just like when we're writing software。

 we want to avoid duplication of code， right？ So when we notice that we're using the same thing across the board。

 then we can， of course， group these two things together as a separate resource。

 thereby minimising the places where we might need to make changes that we wish to add something to the common service here。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_19.png)

And， of course， we can then iterate on this approach and realize that。 nay， wait a second。 Over here。

 we're doing the same thing as over here。So why not put that into its own definition and reuse this？

Which then lets us replace the repeated inclusion here with a shortened form shown here。

So as you see， we are building up much more programcentric automation focused approach here。

 going well beyond the concept of simply copying files around to focusing on really defining our services。

 identifying reusable building blocks and combining those to derive service specifications。

 which is precisely one of the strengths of using a cable configuration management system。

So good bye， Manuel Arrsic， you didn't scale well at all。

 even if we may do with you for much longer than we should have。



![](img/7a20602f63ad64a1d1ca08a90edc7f02_21.png)

Okay。I think it's time to take a break。 We're not done with a topic of configuration management。

 And our next video will go into more details of the C system's required capabilities。

 the concept of state assertion。 And yes， a bit of alllusion to distributed systems at the cap theorem。

To keep your mind focused on this topic， I'd recommend that you review some of the discussions from earlier videos。

 in particular， understanding of five system hierarchy is important here。

 and itll be a good exercise for you to classify different parts of your systems。

You also should try to follow the example we showed here in attempt to clearly define a particular service。

For example， in order to configure， say， an SMTP serverver。

 what are the different components and services you would need。

Do some research of the different config management systems out there and see how they differ and what they have in common。

Some are easier to set up than others， so maybe give it a go。And finally。

 read up on infrastructure as code and service orchestration。

 two areas that overlap and intersect with configuration management significantly。

 but they are not entirely identical。We'll revisit these relationships in our next videos。

 but I hope these example exercises will help you deepen your understanding and better internalize what we've covered here so far。

Until the next time， thanks for watching， cheers。

![](img/7a20602f63ad64a1d1ca08a90edc7f02_23.png)
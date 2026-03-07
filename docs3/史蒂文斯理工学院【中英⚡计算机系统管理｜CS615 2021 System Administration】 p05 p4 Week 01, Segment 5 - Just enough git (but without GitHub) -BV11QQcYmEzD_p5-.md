# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p05 p4 Week 01, Segment 5 - Just enough git (but without GitHub) -BV11QQcYmEzD_p5-

Hello and welcome back to CS 615 System Administration。

Since we'll be using Git for a number of our assignments and projects。

 since it's commonly accepted that nobody really knows how Git workss。

 I thought it might be useful to do a quick run through how to set up Git for our class。And by Git。

 I mean， Git， not Gitthub。 No seriously， it's possible to use Git without Gitthub。 I know， right。

Git is a distributed version control system。 GitHub is a company owned by Microsoft that basically provides Git as a service。

Now， obviously， Gitthub is hugely popular， both as a hosted platform for proprietary software development。

 as well as a public platform for open source development。

 and many of the workflows enabled and promoted by Gitthub are indeed quite useful。

 But at the end of the day， the co functionality is available for you via Git。

 The tool developed by none other other new Stvats。In this short video。

 we're not going to get into the details of how Git works。 As I said。

 I don't think anybody really knows。 And， of course。

 you are encouraged to read up on your own on the common Gi workflows。

 But I do want to quickly show you how to get set up for this class to ensure you hit the ground running。



![](img/8e9c71b662cfc585e62d2f8d007d5131_1.png)

Since we're going to be using the Linux La systems here at Stevens。

 we'll start by setting up our S S H config for this first。 And as you know。

 when you connect to a host for the first time， you will be asked whether you can confirm the authenticity of the host key。

 And virtually every single person on the Internet doesn't even blink once and says， oh， sure。

 when they actually mean how the hell would I know， go away， Let me log in。

But we'd like to find a better way and actually know that we're connecting to the host we think we're connecting to。

There are some ways to solve this chicken egg， such as using DNS SSHFP records。

 we'll mention those again in future class， or to use SSH certificates instead of host keys。

The simplest way， though， is for you to retrieve the host fingerprint to put into an un hostst file via some other means。

I thought Steve's ID had put the SSH host key fingerprint somewhere， but since I couldn't find it。

 I put the relevant key on the course website。The Linux lab name actually points to a load balance rotation of hosts each reachable via the same IP address。

It used to be a DNS round Robbin， which made us a little bit less convenient。

 So now we only need a single line that we need to append to a non host file。

Which we can do like this。Okay， so next， SS administrators we quite lazy and hate to type more than absolutely necessary and typing s hlinlab。

 cs。tevenstch。edu is a bit annoying， so we're going to add a little snippper to a SSH config to let us just type SS H Stevens instead。



![](img/8e9c71b662cfc585e62d2f8d007d5131_3.png)

So here you can add other short names， if you like， you're going to use just Stevens。

We enable strict hostkey checking since we have the correct known hosts entry。

My username at Stevens is different from the local username on my laptop。

 so I'll also specify that here。Next， I provide the path to the correct SSH key to connect to Stevens。

Specify that we only want to forward the correct amenities。And silence some debugging information。

You can look at the S Config menu page for more information about the various options available。Okay。

 these options now in place， we can now simply type SSH Stevens to log in on the remote system。

There we are。Now， we can go ahead and configure good on these systems。Let's start。

By setting our email address。As well as the default push model。Now we create our raw git repository。

For that， we need a new directory that will contain all the Gi metadata。Once we create the directory。

 we can then initialize the directory via a gi in it there。Now， and this is important。

 this will not be the directory where we create files or work from。 instead。

 this will be where Gis draws all its information。So now we change out of this directory and clone the repository。

 we just created。You may be used to cloning directories using either an HTTPS or an SSH prefix to specify your remote repository in another system。

 perhaps Github。But a remote repository can also be specified as a directory on the local system。

 which is what we're doing here。Alright， we appear to have clothed an empty repository。 Well。

 that's not surprising。 So let's add read me。This repository will contain all coursework for the class 6 CS 615 System administration。

Next， we get add the file and commit it。Now， if we want to make changes。

 we follow the normal good flow。We edit the file。We create a new subdirecty。

And we create our first nodes for a week one。Again， gi add。And get commit。

And then gi push our changes to the upstream repository。



![](img/8e9c71b662cfc585e62d2f8d007d5131_5.png)

As you see， this all behaves just like any other gi repository。

 even though it's in a local directory。But the nice thing is that with that repository initialized on Linux La。

 we can now also use that as a remote repository from our laptop。For that。

 we simply clone it by specifying the host name and get well with the help of our SSH config。

 sort things out for us。

![](img/8e9c71b662cfc585e62d2f8d007d5131_7.png)

Let's give that a try。Notice that here we're specifying the raw git repository to clone on the remote site。

We can now edit files in our local copy。

![](img/8e9c71b662cfc585e62d2f8d007d5131_9.png)

Say add a sentence about our glorious good success to a weak one notes。We get commit or changes。

And then push them back upstream。If we're back on the next slide。😊。

We simply change into the check that repository and issue a good pull。



![](img/8e9c71b662cfc585e62d2f8d007d5131_11.png)

Good log shows all commit history， as we'd expect， and all changes are now present here。



![](img/8e9c71b662cfc585e62d2f8d007d5131_13.png)

And we're done。 We've set up good for use with this class and all without using Gitthub at all。

Please make sure that you follow the setup and begin using Git for your course notes as well as your homework assignments going forward。

The links here and the slides should help you further if you're not familiar with it already。

If you are unable mental problems， please rejo on the class's mailing list or slackck。



![](img/8e9c71b662cfc585e62d2f8d007d5131_15.png)

Until next time， thanks for watching， G。
# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p23 p22 Week 04, Segment 3 - Package Management -BV11QQcYmEzD_p23-

Hello and welcome back to CS S 615 System Administration。 This is week 4， segment 3。

 and after we just finished up installing an operating system on our discs。

 we realize that there' is more to that than just extracting a few turbultts into a file system。😊。

In particular， we noted that for our system to come up and be useful。

 we need to oftentimes install additional software。

 bringing us back to the earlier discussion of what types of software they are。

 and whether or not we can easily say， yes， this belongs to the operating system and nope that's an add on。

And as we install such software， we may end up with our attempt of the manual dot s configure make make install in vocation being foiled by an unmet dependency。

 sending us in a wide goose chase of downloading dependencies of dependencies in order to finally get our headon software installed。

The conclusion， there has to be a better way。Inter package management。

 which we'll discuss in this video。 But before we get to that。

 let's first take a look at the few pieces of software and attempted to find their place within the software stack。

Here I've listed a few examples with a table to let you fill in whether you think that each entry belongs into the category of system software or otherwise inherently being part of the operating system。

 or whether we consider the entry more of an addon provided by some third party。

Why don't you try to pencil in what you think fits where？Now， as you do that。

 you will probably need to take a step back and ask yourself， wait a second。

 just what exactly is the operating system。We had earlier said that clearly。

 the kernel itself is not equivalent to an operating system， but that， yes。

 you do kinda need one of those。 An o without a kernel is not really useful。Okay。

 so kernel is not a on software。 After all， this is how Gnu Linux came to be a useful operating system。

 All the other bits were already available， but a kernel was missing until Lino Salitz released his Linux kernel under the Gnew Public license or G。

But then if we do need a kernel， what else do we need to have an operating system？

In a modized system， you can extend the functionality of the kernel via loadable kernel modules。

 and for certain pieces of hardware， you do need those special drivers。

 So those ought to be part of the OS S as well。But you also sometimes need drivers that are supplied to you by the Hary manufacturer。

 Of course， the company that makes say your rate controller needs to make sure that their driver works with your specific kernel version。

 So there is still a tight integration。But as it may be proprietary or in either case separate from the OS。

 we have to put a check mark over here under the third party。Now， what about firmware， Well。

 perhaps we should specify what we mean by firmware。 The bio is sure。

 but also the actual firmware running on the rate controller or unique。Now。

 those don't need to be integrated with the Os and why there may be tools provided by the OS to manipulate different types of firmware that would generally be considered to be an addon。

Next up， Lipsy， the Sened Sea Library。Now， that is something that really needs to be quite well integrated with a kernel and all the other applications and services offered by O S Without this library。

 a lot of things will not work。 And upgrading this library has the potential to break just out everything on your system。

 So clearly， you check in the O S column。Now， while it's conceivable to install a separate C library implementation as an adddon。

 I think that would be rare。 So we put an xe into the addon column here。What about the shell？

HaT question。 Now， of course， just about any Uni operating system comes with a shell。

 But you also might be aware that there are all sorts of different shells you could install on top if you liked。

So this one's a bit weird。 The po extend that requires a shell to be present。

 a born compatible shell no less， but you could conceivably also build noise without a shell。 But O。

 let's put a check mark in both columns here。How would S S H， both the client and the server。

In a way that's similar to this shell， just about every unique version around ships with S S H。

 and basically all ship the same version of S S H， open S S H。

But it's also possible to install it as an addon or to use a different implementation。It's rare。

 but hey。Okay， next， mail server。Again， most unit systemss come with a mail server out of the box。

 which is a bit weird because nowadays， there really is no obvious reason why a stalone system or server should come with a full SP server。

But this is an example of the legacy of the Uni system being primarily a very generic server OS for multiple users。

And of course， you can have multiple implementations so it's also Aon software。

How ordinary she T piece are over then。Well you'd think that'd be the same as the mail server。

 but traditionally an HTP server has not been included in the UniX OS。However， increasingly。

 more and more versions have added an HTP server to the bay system simply because it's become such a common use case。

Now the HtTP service included in many base operating systems might be good enough for low performance。

 low traffic sites， but if you want to serve some serious traffic。

 you'd likely install another version。Databases then， unfortunately。

 not yet included in every OS that you installed and remain a primarily standalone erroron application。

And finally， I listed Python here as is stand for just about any programming language interpreter。

 compiler or environment。And it's another funny one because obviously， it's an addon。

 You can download an installed Python on any system and even have multiple versions installed。

 Although the resulting dependencies for your software can get really annoying here。

But also many operating systems do ship with it out of the basezo S。

This goes back to the standard Uni versions， too， which shipped with a C compiler。

 even though nowadays， it really is not needed for most systems。

But the Python interpreter may also be required component of the OS。

 if some of the tools the OS provides are written in Python。 So again。

 it illustrates just how difficult it is to draw the distinctions here。But。

Seeing how most things are third party or ats anyway， why do we even care？

One of the reasons is that we want to understand the dependencies between components。

 a coherent operating system that comprises specific core components and ships them as one coherent unit is easier to manage。

 to use or to upgrade than a large po of independent packages just that just happens to be deployed on the same system。

And to resolve these dependencies， we oftentimes use a so called package manager。

So which of these components here would come and who you manage by our package manager。

Welcome to the wonderful world of system administration with the correct answer。

 as so often is it depends。😊，It depends on the operating system in question。

 as well as on the flavor of the operating system。Some operating systems do not use a package manager for the core OS and only use a package manager for addon software。

 but other systems use the same package manager for all components of the system。

 including the individual kernel modules or the kernel itself。



![](img/954beb6d0e34e06eb61cf3e5600409a2_1.png)

But so let's look at how we manage software from a different perspective here at the bottom of the stack we're about to build sits the hardware。

On top of that sits the firmware， managing and interacting with a hardware andom capacity。

Next is the kernel managing the hardware。We then have some system software sitting on top of the kernel or otherwise being tightly coupled with it。

 device drivers， kernel modules， core libraries， et cetera。

But we also have a bunch of utilities and applications sitting here， such as the shell。

 or the common Uni tools we used to， set， or Gr， etc cetera。These interact with each other。

 but also may be used to control some of the firmware and a lower layer。Finally。

 on top of all that sits what we called addon software， things like a web browser。

 a web server or a database or a different programming language environment。

 the AW S utilities and so on and so on。Now， at some point， that point is a bit arbitrary。

 as we have seen。We declare that some of these components are part of the operating systems。

 and others are not。 It really depends on the operating system provided to define what they believe is part of the O S and what is not。

But even for those components that are not part of the US。

 we are still looking for a same way of managing it and all the dependencies between them。

So we find that package management spends all of these layers。

So we see that even if our operating system uses a package manager。

 it may want to use that to manage and on software。

But as you soon enough find out once you've been running a system for longer than a week。

 there is always some software that is not available via your preferred package manager and that youll have to be careful how to manage that software and so again the distinction between what is part of the OS and what is addon becomes more meaningful。



![](img/954beb6d0e34e06eb61cf3e5600409a2_3.png)

For example， when you upgrade your OSs， will that lead to a system that's incompatible with your Aon software？

The addon software might install its configuration to files in a location that you consider static when you designed your partition schema。

Or the software you're adding may conflict with some of the Qs components。

 or you end up with multiple versions of the same software。

You may have to adjust your system startup scripts to launch the third party's service at that system boot。

But generally keep track of where the software is located。

What dependency said Ha and how you tell it that you meet the requirements。

 meaningan whether you can install the software by your package manager or by hand。

And it's oftentimes easy to say， well， I always and only install all my software by a package manager。

 but sometimes you don't have a choice because the software is available to you only as an op b that you don't have much control over。

So as a general recommendation， it's usually the case that you simply don't have a choice。



![](img/954beb6d0e34e06eb61cf3e5600409a2_5.png)

Software provided to you in source form needs to be packaged up and installed to ensure you can express dependencies correctly。

 and even proprietary software can and should be turned into a package for your environment。

After all， package management is really just a way of delivering files to a system while expressing requirements and dependencies to yield the final state。

We'll get back to this concept of asserting state of defining the outcome package X is installed。

 rather than focusing on how to do that later in the semester， though。Anyway。

 since package managers are a critical tool in any assessment Edmins tool chest。

 let's look at a few examples of the functionality they provide。



![](img/954beb6d0e34e06eb61cf3e5600409a2_7.png)

Here we are on the Stevens Linux Lab， which happens to be a Debian based Linux variant。

 so it can use the D packaged tools to manage our software。By running Dpackd de。

 we can see all the software that is installed on this system。Which turns out to be quite a bit。

1319 packages in total。But this is quite useful now， isn't it。

 Being able to list all the software that's installed together with a version of the package is rather important。

So the first excellent thing a package manager provides is thus。A software inventory， hooray。Okay。

 next for any given package that we have here。We can list the contents of the package。 For example。

 the TCP done package contains all of these files。Not only that。

 we can also go the other way around and ask the package manager， hey， I've got this file here。

 What package does this belong to。So we get here a rather convenient method of looking up which files belongs to what package forward and reverse。

So this is the second excellent thing our a package manager provides。

A file listing and look up to yay。But， unfortunately。

This only works if the software in question was installed using the package manager。

So for consistency， you really want to make sure you go to the trouble of packaging up the software you add here。



![](img/954beb6d0e34e06eb61cf3e5600409a2_9.png)

Just think， suppose you want to upgrade Python on this host。

 but let's say the AWS tools require a different version and will break。

Since the AWS toolss were installed outside the package manager。

 the package can't know this and will happily let you upgrade Python and break AWS for all of us。

So that's really no Bueno。So take note。When you use a package manager。

 use it consistently or you lose many of its benefits。And there are several。

 besides just having a convenient inventory。To illustrate another advantage of having such an inventory。



![](img/954beb6d0e34e06eb61cf3e5600409a2_11.png)

Let's take a look at a different system。Here we have a feddoa instance which uses the rathead package manager or RPM tool。

Like before， you can get the listing of all installed packages。



![](img/954beb6d0e34e06eb61cf3e5600409a2_13.png)

344， in this case。

![](img/954beb6d0e34e06eb61cf3e5600409a2_15.png)

And cut the contents of a package， like so。

![](img/954beb6d0e34e06eb61cf3e5600409a2_17.png)

Now， suppose we change one of the files in this package。



![](img/954beb6d0e34e06eb61cf3e5600409a2_19.png)

Let's say， Etsie Pada di Sudo。

![](img/954beb6d0e34e06eb61cf3e5600409a2_21.png)

To simulate a system compromise， That is， if an attacker gained right access to this fire。

 they could change how authentication for pseudo is done。Not something we want。

So now the file looks like this。Let's also change the owner and group here。Now。

 how would we go about finding out whether or not a file like this has been manipulated？

Remember that our package manager provides a full inventory of all files。

 but it has even more information than that， doesn't it。In order to install all the files。

 the package manager also must know the ownership and permissions， right？

And probably also knows what the file size is and even what the content should be。

 So if we have all this information in the package manager's database。

 then we should be able to look this up and verify the integrity of a given package。And indeed。

 the RPM command offers an option for this。If you run RPM D V， you get output like this。This means。

That the RPM command detected that the size， the M5 checks sum， the user， the owner。

 and the last modified time of the file differs from what it was recorded at installation time。

How cool is that。We get an implicit intrusion detection kit here via the package manager。Nice。Now。

 let's change back everything to normal。There。Well， okay， the last modified times stamp still shows。

 but we know that everything else is in order。We can of course。

 also run the validation check across all packages。And you will find。

That there are some changes here。This may be entirely normal since you may change the configuration files for several packages。

 log files will necessarily changed during normal operation， etc。

This hints at the fact that in order to properly monitor a system。

 you need to actually understand the context and know what the normal status is so that you can identify whether any reporting and changes are expected or not。

 we get back to that discussion later in the semester and we talk more generally about system monitoring。

But all right， we get an intrusion detection mechanism， which is quite neat。

 But let's see what else we can do。 And we have a proper inventory of all packages in our system。

In this example， we get back to a NePSSD system where we use the package tools to manage addon software from the package source system。

As before， we get the listing of the packages。177。In this case。

But what I want to do now is figure out whether or not any of these packages have any known vulnerabilities。

 After all， if I have an inventory of the packages on my system。

 then I should be able to automatically compare it to a list of known vulnerabilities and see what things I have to patch。

So that's the next really neat feature provided via a good package manager。

Implicit analysis of which packages need to be patched by analysis of known vulnerabilities。

All right， for that， we need to get the list of known vulnerabilities。And in this case。

 it is provided by the NePSSD project and can be retrieved via the package admin utility。Okay。

 so let's take a look at what type of file that is。Jesep compressed text， it seems。

Let's have a look at the data。Looks like a plain text file， easyy to read and parse。

It contains a listing of package name and version， mapping that to the type of vulnerability and the URL with more information about the specific issue。

As you can tell， theres quite a few of these entries here。So let's try to run an audit。

We used the package admin tool for this。 And， wait， what's this。

It tells us something about not being able to verify a signature。

Let's look at the fire one more time。We note that right here at the top。

 it tells us that this information is cryptographically signed using PGP。

Which is rather useful when you want to be assured that the data is authentic and unmodified。

But we can't verify the signature because we're missing the key with which this file was signed。

 So let's fetch the key from the package clause website。And import it。There。

 now we can see if we can verify the data。Okay， we got a valid signature now。 that is。

 we can verify that the file we have was the one that the packageaw security team published。

But we haven't verified this key， meaning the GPG tool does not know whether this key with which the file was indeed signed is trustworthy。

Let's change that。Since we fetch the key from the website via HtTPS。

 and we know that the location is indeed that which the package hosting publishes its key。

 we can sign it。All right。 There we go。Let's try again。啊哈。Now we have a good signature that we trust。

 great。So now we can run the package audit。And。Here we go。Oof。

 that's quite a few issues the two identified。 welcome to System Administration where just about any package or than a few weeks is likely to have a security vulnerability。

Which is why it is so useful to have a tool that can tell us what they are so that we can then decide whether we need to address them。

 Okay， so let's see。Bash over here appears to have a privilege escalation vulnerability。

 so we probably want to fix that。So we can use our package tools to pull in an updated version。

The tool calculates what， if any depend it needs。And then downloads the updated package。

Removes the old version and installs the new version。So， now。When me run the package audit again。



![](img/954beb6d0e34e06eb61cf3e5600409a2_23.png)

We know that the vulnerability for bash no longer shows up here。



![](img/954beb6d0e34e06eb61cf3e5600409a2_25.png)

Hooray。Okay， so let's break here before we move on to further discussions involving package management and some of the more area security aspects involved therein。

What have we covered in this video。We've seen that what comprises noise。

 What is system versus add is not an obvious distinction。

We've seen that some dependencies are more tightly coupled， The kernel and Liy， for example。

 than others， meaning updating them requires coordination and compatibility。For others， however。

 there are multiple options。 and what is grouped together as the operating system really largely depends on the provider。

But either way， we've illustrated that all of this software could and should be managed in some coherent fashion。

And the good package manager provides a list of excellent features。

 as we illustrated by example of the WbN D package， Reta， Fidoa or Ascentto S RPms。

 or via NPSSD's package source tools。Those features include the ability to easily install software and have the package manager automatically resolve the various dependencies amongst the packages。

After installation and through consistent use of the package manager。

 we thus gain a complete package and file inventory。

 which we can then use to build package and file integrity checks。

 as well as a comprehensive mechanism to check your software for non vulnerabilities。Now。

All of these features apply to OS， as well as add on software。 So long that is packaged consistently。

So you probably want to make sure that you have integrated your package manager with the Os。

 meaning the package manager itself， another piece of soften our stack really becomes part of the O。

Now， we aren't quite done yet with a topic of package management。 And then our next video。

 we'll continue with a closer look at language specific packages。

 as well as a range of security related concepts in this area。

 But before we move on to that discussion， let me leave you with a few exercises to consider。



![](img/954beb6d0e34e06eb61cf3e5600409a2_27.png)

To begin with is' useful to get some practice in building packages。 since as I mentioned earlier。

 as a Ssadmin， you oftentimes have to do just that for the various software components that are not already packaged。

So why don't you go and find one of your favorite tools。

 check if it's available as a package for your preferred Unix version。 and if not， change that。

 I'm sure the upstream project will be happy to accept your contribution。😊。

Another useful exercise is to compare the different package managers。

 similar to what we've run through some of the examples on different platforms in this video。

Identify the basic commands to perform the most important task and package management。

Compiling a clear cheat sheet like this can be invaluable for your future efforts when you switch from one Uni version to another。

Next， think about how we can manage firmware。 How does your prefer OS handle this。

Research the concept of reproducible builds。 And think about how that relates to our discussion here。

 That is， if you run the same package manager command on different systems。

 will you always necessarily get the same result， What differences might occur。

And think about how the management of packages overlaps or intersects with the configuration of the software。

Can you use a package manager to assert the desired state of a system down to a specific configuration。

Well get back to this discussion towards the end of the semester。

 but it's still a good exercise for you to think about this already。



![](img/954beb6d0e34e06eb61cf3e5600409a2_29.png)

And finally， here has a more detailed exercise you may want to run through。

 It includes the comparison of installing software by hand and via package manager and would like to give you a number of important insights into what we have discussed here in this video。

 as well as in the next。😊，I know this looks like a lot of work， but as I keep saying。

 it's up to you how much you get out of this class and if you're interested in system administration。

 these exercises can really deepen your understanding and in addition be practically useful to you。😊。

With that in mind， thanks for watching and I'll see you next time， cheers。


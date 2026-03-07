# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p24 p23 Week 04, Segment 4 - Package Manager Pitfalls -BV11QQcYmEzD_p24-

Hello and welcome back to CS 615 System Administration。This is week 4， segment 4。

 And after in our last video， we sang the high praises of package managers and illustrated their various useful features。

 It's now time to shine and light on some of the problems we regularly encounter when dealing with package management。

Now， to be fair， many of the problems noted here are not so much inherent to package managers than to the larger conceptual issue of installing software。

But it is worth keeping in mind just how fragile the systems we routinely build really are。

Remember how we tried to classify software by type and group it into categories like the operating system and add on software。

We quickly realize that it's not straightforward。 but O。

 let's assume that we're using an O S that uses a package manager for our components， the Os and Els。

This should let us easily manage all the software we need in a consistent manner。But unfortunately。

 that doesn't always work out。 If you're writing a lot of Python code， for example。

 you'll probably know that one of its strengths is that there are many open source modules and all sorts of cool packages let you simply import anti gravity without having to worry about implementing this yourself。



![](img/5d3b15c011f640c1d450f5587c87479d_1.png)

But all these modules cannot possibly be shipped with the O。

 and as the language environment oftentimes moves significantly faster than， for example。

 an operating system release cycle could keep up with。

 you generally won't find your anti gravity RPM and now you have to figure out how to install such modules。

Most programming languages encounter this problem sooner or later and end up building a native language package management systems of sorts。

 complete with remote repositories and all that。So now。

 instead of looking for an R PMM for your Python anti gravity module， you might use Pip。

 which will go and fetch your module and install it in the right path and。Wait， what's that？

 You're on half Pip。 Oh， no problem。 You installed it using E install。

 which is a Python package manager that you can use to have it automatically fetch modules and install them in the right path and。

Well， you see where this is going sillyly， Python， you should be using nodj as anywhere， right。Right。

But the point here is not to make fun of different languages。

 but to point out that there is an apparent need to rapidly and easily install packages for a given language and that these solutions do not integrate with your O S provided package manager。

And it really is just about every language that has this concept。 For example， long。

 long before node Js， Pearlhead C pen。And P P had Per and Pele。

 which had a repository compromise in 2019。Ruby has gems。

 as well as a public repository that has frequently seen compromised individual gems。

Gofe' code more or less， directly from Gitthub。And Rut uses the cargo native language package manager to build packages and upload them to the public community。

 Cate registry， Cates。 Io using the country code top level domain for the British Indian Ocean territoryri because that's what you use these days when you want to show that your H。

We'll talk more about domain names and top level domain in a future lecture。



![](img/5d3b15c011f640c1d450f5587c87479d_3.png)

But okay， so keep in mind that we have these different language specific package managers。

Let's talk a bit about dependencies， integrity and trust。We have seen the OS package Manager。

And we've seen the various native language package managers。Seems like we've lick the problem。 No。

 each one can install software。 So what's the issue。



![](img/5d3b15c011f640c1d450f5587c87479d_5.png)

Well， let's have a look。Here has a system that has a bunch of Python related Rms installed。

So far so good。 we know we can identify which modules belong to which package and can express dependencies amongst them。

 such as， for example， that Python URL Li 3 requires the Python IP address and Python 6 packages and is of version 1。

10。0。But now this host also has a bunch of Python modules installed by a Pip。This， too。

 is convenient， as Pip shows us which versions of the modules are installed and also sorts out the dependencies between them。

But now notice that we have URL Li 3 installed twice once by an R PMM。And once， by a pip。

And they're different versions， too。So now things are getting interesting。

Imagine that you have a tool written in Python that needs U El 3。 Which version will it pull in。

And what if there's a vulnerability in your L Lib 3 version 1。9 that was fixed in version 1。15。

Is this system affected， Which Python  tool using your aib 3 on this host need attention。

Does your host inventory correctly identify both versions。

And how do we even get to have two versions of the same package installed。Our Python version here。

Is 3。6。But。We don't even have a Python 3 RPM installed。



![](img/5d3b15c011f640c1d450f5587c87479d_7.png)

The RP PMM version is 2。7。So now where do we find a Python that is not listed in the RP PMM database。

And also then identified by a pip。Now， here it is， under up Python。Which package provides this file。

H， no package。Nice mess。 We got here。And this is not even a very rare setup。

 You will find similar configurations on most production systems。

And this doesn't even get us to the question of which version of which package is running in every single container you have。

So we see that dependencies cannot be expressed， relied on or tracked once you break out of the package manager。

 By the very nature， each package manager assumes that it is in charge of all of the packages and doesn't cannot know about similar software added in another way。



![](img/5d3b15c011f640c1d450f5587c87479d_9.png)

But okay， so dependencies can become a problem。 What about integrity。

How do we know that the software we are installing doesn't contain a back door。

You all have probably seen install directions like this。 And oftentimes。

 people criticize this approach because obviously pulling random code off the internet and running that as rude is not a very good idea。

But consider the alternative。The traditional method of installing software looked like this。

You down the tuble of source， extract it， build it， and then install it。Sure。

 you could inspect the source code and the configure script and the make file to verify it doesn't do anything nefarious。

 But honestly， nobody does that。 And it simply wouldn't be a scalable approach。

So this really isn't that much different。Similarly。

 the various native language package managers do something similar in the background。

 They download some files and execute some scripts。Likewise。

 for a desktop of targeted package management solution tojore。Now。

 one thing that you can do to make things a bit better would be to ensure that you use H T TPS S instead of H T TP so that you get at least some authenticity assurance。

We'll get back to that discussion in a future lecture， though。

But let's think about what we're really concerned about here。 But the given examples。

 we fetch some software from the Internet and install it without having any assurance that the software is what we think it is。

How can we improve on that？

![](img/5d3b15c011f640c1d450f5587c87479d_11.png)

Now， your package manager may include support for signed packages。That is。

 the package contains some metadata that includes a digital signature so that we can verify that the data we downloaded was indeed the one that was uploaded to the repository by an entity we trust。

So for that， we need to again deal with asymmetric cryptographic keys frequently using PGP。So here。

 this RM Bay system includes a handful of PGP keys from different entities from which we may want to install software。

This key over here， for example， is the feddoa E P E L repository key that the feddoa produces to sign the extra packages for enterprise Linux。



![](img/5d3b15c011f640c1d450f5587c87479d_13.png)

![](img/5d3b15c011f640c1d450f5587c87479d_14.png)

The R PMM command can be used to verify the information embedded in the package。Whidge。

Includes a check some of the data itself， as well as a signature created using this key here。

When we install this package， the signature is automatically verified。

 meaning we get assurance that what we are installing is what the Fidoa project uploaded。

That's great and strong assurance。 It means we at least know that the repository itself was not compromised。

 nor that anybody in the middle was able to manipulate the data in transit。

So this topic of trusting quickly becomes interesting， by which I mean complicated。

We trust the Fiora project and thus anybody able to sign packages using that key。

 which may be an automated release system。 but our trust also goes into a few other directions。

 which I was taking a quick look at。I don't know if you remember the left pad incident from a few years ago。

 In that case， there was a widely used and surprisingly tiny node Jaz module called left pad。

 There could be used to。 Well， my name suggests pad text blocks on the left with the appropriate amount of white space。

The entire module is shown here，12 lines of code。Turns out this was a surprisingly popular module。

 many other libraries included this module。But for various reasons。

 the author one day decided to remove the module to unpublish it。Now。

 as the author that entirely is prerogative。 But， of course。

 that means that every single package that either directly or indirectly depends on this module is not broken。

And so it turned out that apparently a third of the Internet did depend eventually on this tiny little nojis module。

 and various large Internet companies encountered serious problems when the internal trialss could no longer be built。

Now， aside from wreaking havoc on the internet， this provides an excellent illustration of the fact that if you depend on another module。

 you literally depend on it， meaning you break if it breaks or goes away。

The NPp N P put in some restrictions since then， surrounding what happens when a module gets unpublished。

 But by and large， there is a problem that's inherent in package management and requires you to understand the impact of your dependencies。



![](img/5d3b15c011f640c1d450f5587c87479d_16.png)

But with a large number of public repositories used by the different native language package managers。

 repositories to which you just about anybody can upload anything， mind you。

 there are other concerns。Earlier this month， the blogpo went around and described an interesting attack method called dependency confusion。

In which the author was able to compromise a number of large companies by way of the logic employed by these package managers。

The way this work was really quite simple。

![](img/5d3b15c011f640c1d450f5587c87479d_18.png)

And step 1， you find out what types of modules your target organization might be using。

 a simple way of doing that is looking at the website sources or sifting through public github repositories。

 which oftentimes include built information， such as what package a given module depends on。

Turns out there's a lot of results if you know what to search for。Now。

 many companies have internal repositories that they use for their internal only proprietary modules。

 but they also pull in code from public repositories。

So once you know the name of a package that your target uses。

 but that's not been published to a public repository。

 you create your own malicious module and publish it to a public repository。When you do that。

 you use a large version number so that it may seem that your module would be newer than the version found in an internal repository。

Step 3 is the easiest， and perhaps the hardest。 You wait。You wait， hoping that at some point。

 somebody will find and use your package。And what do you know at some point。

 somebody is going to run NP in。Now， NP PMM install is noted here has the default behavior to always look for the latest version of a package。

 That is， if you find two versions， the one with a larger version number is picked。Which， of course。

 is exactly why you picked a large version for your malicious payload package。Furthermore。

 by default， the commanders configured to look at the public NPM repository in addition to any internal repositories。

So if you know the name of a package， create your copy and give it a large number at some point。

 something is going to pull it in。Congratulations， were now on the hosting question。Just like before。

 there are ways to address this， not allowing pulling code from public repositories， for example。

 but it's not always easy。The main lesson remains that you do trust upstream repositories。

 whether you like it or not， and verify the integrity of a repository or a package。

 something that requires more care or attention than most organizations pay it。

So let's review some of the pitfalls we discussed in this video。First of all。

 it's important to remember that you indeed depend on your dependencies。 That is， if they go away。

 you break。If they introduce an incompatible change， you break。 And if you don't control them。

 then you are relying on others， possibly outside of your organization。Now。

 to ensure that you don't put an untrusted code from the internet or that you don't break if some random person on the internet gets into a beef with the repository maintainers and takes their modules offline。

 you might decide to mirror an upstream repository internally。

But that really doesn't solve that problem at all。 If you are mirroring a repository。

 you are mirroring all its changes。Now， mirroring can help you in some of the circumstances。

 but it does not address all of them and not completely。As so often， there is no silver bullet。Next。

 we've seen the use of signed packages in R Pms containing checkups， which is all nice and well。

 but unfortunately， only solve one part of the problem unless you have established the trust relationship with the provider。

 they mentioned this concept in an earlier video。Finally， this reflects our first point。

 You need to remember that all trust chains down to the weakest link。

 the integrity of your software built is gated by that of your dependencies。Now。

 we'll get back into the discussion around trust， integrity and what to do about the various threats in the more abstract context later in the semester。

But for now， perhaps try to think a bit about the incidents alluded to in this video and research what similar issues may have occurred before。

Put some thought into how you might want to protect your environment against these problems。

Take a look at the various OS and linger specific package managers and find out where they pull their packages from。

What transport mechanisms do they use and how do they assert integrity and authenticity。

How do you know that you can trust them。And think about the problem we illustrate earlier。

 installing language specific modules in an environment that uses an OS S native package manager。

How do you record or resolve dependencies。As I illustrated， this is far from a solved problem。

 so there are no right answers to these questions， but they are all well worth your time to research。

And with that， we're coming to the end of our discussion on package managers for the time being。

In our next videos， we will move on to discuss multi user fundamentals。

 what it means for a system to support multiple users and how that effectss design decision system administrators have to make。

As well as the first discussion of certain authentication basics。Until the next time。

 thanks for watching。

![](img/5d3b15c011f640c1d450f5587c87479d_20.png)

Jest。
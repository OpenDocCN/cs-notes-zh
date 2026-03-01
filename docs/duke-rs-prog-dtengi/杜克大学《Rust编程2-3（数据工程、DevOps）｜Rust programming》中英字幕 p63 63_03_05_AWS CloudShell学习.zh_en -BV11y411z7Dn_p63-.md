# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p63 63_03_05_AWS CloudShell学习.zh_en -BV11y411z7Dn_p63-

![](img/84b7999a7bd5f3c62a978f0eac362292_0.png)

Here we are with AWs Cloudhell。 you can see here from the documentation that it's a command line access to AWs resources and tools in the browser。

 which is really a critical aspect of it。 So this means if you're at the library or if you're at a coffee shop you can shell into here and start doing work and it's gonna be very fast because you're inside of the AWS ecosystem。

 So if we scroll down here and we take a look。 One of the things that's kind of cool about this is that you can see here the benefits。

 there's no extra credentials to manage because it's roll-based privileges Also it's automatically updated with the latest operating system from Amazon。

 The tools are installed。 there's no cost。 you also get a gig of storage and you can customize it。

 So really in a nutshell here Here's like the visual view is that it's one of the interfaces that you can use to programmatically control the AWs platform。

 So let's go ahead and get started here， I'm going go to my Cloudhell environment。



![](img/84b7999a7bd5f3c62a978f0eac362292_2.png)

And let's just take a look at this， how do I launch this。

 So I go over here and it's just on any environment here in any region you can launch this and you get this message here from my previous work in the Cloud shell。

 So before we even get started， I'm going show you a little trick here。

 which is I can delete my current work。 So this is really handy because if you're doing a bunch of fancy stuff inside of your Cloud shell and you were experimenting and you screw everything up well。

 it's good to know that you can actually delete the entire thing and I'll just restart。😊。



![](img/84b7999a7bd5f3c62a978f0eac362292_4.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_5.png)

Okay， we're back here。 AWS has reset the Cloud shellll environment。

 and let's take a look at a few other other things here in this actions menu。

 So a few things that I think are really helpful is if you want to open up a new shell you can go here and now we've got a new shell so you can open up as many of these as you want Also if you want to split into rows。

 you can have a top and bottom this can really be handy if you're working with。

 let's say some kind of a foreground mode microservice like flask or fast API and then you want to invoke it right below this really。

 really handy interface， you can also go through here and split into columns so you can you can build out this really like a dashboard for doing things inside of your terminal。

Now， if we scroll down here as well， we can see that you can download files so that's pretty handy。

 if I go in here and I look at for example， the PwD command。

 which shows me where my path is and I do an LS there's nothing in here。

 So we'll come back to that but I could download a file if I wanted to now also we can upload file So maybe we'll start with this you can upload one file at a time from your computer to the home directory。

 your home directory is limited to one gig， So here we go。

 This seems like a good idea is I can upload one file very。

 very common for people working with data to upload let's say a CSV file or some other artifact that you're gonna do machine learning on。

 So what I'm going do。

![](img/84b7999a7bd5f3c62a978f0eac362292_7.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_8.png)

As I'm gonna go to my desktop and I have a zipped file here on my desktop that I'm going to upload called Cats Dog Small。

 so let's go here and let let's upload this file we'll go ahead and select it here we go Cats dog small perfect and then I'll click upload and what's really handy about this is now I'm inside of the AWS ecosystem and and this is really handy because I can actually move it around places so if I go through here and I say unzip cats and dogs there we go we've got this whole thing inside which is pretty handy。



![](img/84b7999a7bd5f3c62a978f0eac362292_10.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_11.png)

If I want to， I can look inside of the directory there we go and we can see these different files。

 So let let's go ahead and test out the download here since we're already here。

 So what I would do is I would just need to know the name of a path so let's go ahead and download this file and let's just put in that path here So we've got slash home。



![](img/84b7999a7bd5f3c62a978f0eac362292_13.png)

And Cloud Shell。User。Cats， dogs。Small。cat。Zero dot。JPg。Okay， that looks perfect。 Download it。

 There we go。 So there is actually a great feedback loop where you can go up and down into these different directories and I'll probably just remove this file as well。

 which is always a good idea once you've uploaded it if you don't want it anymore because there's a limited amount of space we can see this by running the Df dash H command。

 This shows us the file system and notice here that in our home directory。😊。



![](img/84b7999a7bd5f3c62a978f0eac362292_15.png)

This is where we would actually be working with storage and there's only 10 mebytes that are currently used。

 but I have another 899 mebytes available。 So that's plenty to do many things that you'd want to do inside of the AWS cloud shell。

 So another thing that we can talk about here that's pretty nifty is that notice if I type in E Do sign bash sorry shell。

It'll say Bbash， that's the default environment。Now what's nice about this is you can obviously edit your shell。

 let's go ahead and edit our ba shell real quick。And let's just put something kind of fun in there and let's just say。

OnBe here that echo， this is bash。Here we go， and now I'll go through here and close。

This environment by opening up a new tab。And it'll say this is bash right and I can close that other one so that's pretty handy。

 but we don't have to just use bash we can also use other shells。

 we can also use the ZSH shell which many developers like because it has a few extra commands here similarly notice how the bash command didn't run because it's a different shell environment we can edit this and we can go through here and we can go to our ZSHRC file。

And notice here that there's some really cool commands that we could play around with and we could actually tweak these like one of my favorite ones in the ZSH configuration file is to do autoC so it doesn't need to type in the CD command。

 but we'll just keep things simple here and I'll just type in echo， this is ZSH。And again。

 if we go through here and we go to that same thing I did before， we'll open up a new tab。

There we go。 This one is bash because the default shell that opens is bash。

 but what happens if I type in ZshH This is ZshH right so we have two environments here that we could play around with。

 but we're not done if you're a dotnet developer you may want to use the Powerhell prompts here we go if we go to Powerhell prompt you also could go through here and build out things using C sharpharp and play around inside of this interactive environments。

 so really pretty pretty awesome that you can actually play around with all these different environments here whether you'renet donet developer you like bash or you like Zhell。

 So。Let's go ahead and move on a little bit here and actually play around a little bit with using this environment to actually do some work so what I'm going to do here as I'm going to exit again and we can see here that if I type in echo dollar sign shell we can double check what shell we're in okay good we're in the ba shell so the first thing that I would say that we can do here is that we can copy some files to an S3 bucket so I'm going to go through and I'm going to look at the official documentation here and let's go ahead and pull this up。



![](img/84b7999a7bd5f3c62a978f0eac362292_17.png)

And this is a great place to get ideas about what you can do。

 So look copy multiple files between your local machine and Cloudhell。 So this looks pretty cool。

 What we can do is we can actually upload multiple files to a bucket。

 So let's do this let's go ahead and create a bucket from the command line So first up here I'll go through here and I'll type in this command And so this command here says AWS use the S3 API。

 create a bucket and we're gonna actually put the bucket name right here。

 So we'll go ahead and call this something unique we'll call this cats。



![](img/84b7999a7bd5f3c62a978f0eac362292_19.png)

Dogs。11，21，2021， there we go， that looks pretty good and let's go ahead and push return。

What's nice about this is that I don't necessarily need to use the console itself to do things now let's go ahead and double check to make sure that this exists so if we go through here and I look for cats and dogs。



![](img/84b7999a7bd5f3c62a978f0eac362292_21.png)

We should see， if I refresh。There we go cats dogs right so we're able to programmatically create buckets and control them。

 which is really really handy another thing you can do as well if I type in AWSS3LS。

 I can pipe out the output of this to count the number of buckets。



![](img/84b7999a7bd5f3c62a978f0eac362292_23.png)

Here you can see that I have 99 buckets。 So what I did is I ran the AWs S3 command to list the number of buckets。

 pipe that into the word count L command and now I can see that there's 99 buckets。

 So okay what else can we do what we can synchronize these files here and in fact if I look in this directory these are these files that I uploaded earlier So what I can do is I can type in a synchronization command to put these inside of this bucket cats and dogs here So the first thing that I'll do is I'll take this name which is a neat little trick that I like to do and I will put in the hashtag。



![](img/84b7999a7bd5f3c62a978f0eac362292_25.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_26.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_27.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_28.png)

Right there and that way I can refer to this command without it blowing up and all I need to do here is just type in AWS S3。

Sync dot， which would put everything in this directory into。This destination。

 and so this is the trick here is I want everything that's in this directory to be synchronized to the remote S3 directory。

You can see here every single one of those files is synchronized very， very quickly。

 that's the other advantage of using this Cloud channel environment and once all these files are uploaded。

Or synchronize into this environment what I can do as well is I can actually go through here and verify that that bucket is actually ready to go。

 So let's go ahead and watch this thing go here。 you can see here tons of files or synchronizing And if I wanted to make small changes。

 the synchronization command will actually keep them up to date。

 So really you can see how the cloud shellll if you're working with any kind of a data pipeline。

 data engineering machine learning engineering is really invaluable。

 So let's go back to the Aws cloud shell here go ahead and click refresh。 there we go。

 and we can see here that all those files are inside of my bucket。 So all right。

 so let's go through here and download something as well， that's a zipped file。

 which is a common way to synchronize things。 how would we do this Well I would just go through here and type in zip are cat cat like that。



![](img/84b7999a7bd5f3c62a978f0eac362292_30.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_31.png)

There we go。 we added a zip file here there you see this now all I only need to do is just type in PWD and actually put in this path here。

And we can actually just do this as a neat little trick。As I can do cat。

 zipip that way I can verify that the path exists， this is a great idea so that you don't get yourself into trouble so I can copy this。

Right here， copy this path and then go here and then go to download file。



![](img/84b7999a7bd5f3c62a978f0eac362292_33.png)
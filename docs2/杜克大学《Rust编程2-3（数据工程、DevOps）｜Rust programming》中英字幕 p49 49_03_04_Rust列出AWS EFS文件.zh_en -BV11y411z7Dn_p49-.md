# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p49 49_03_04_Rust列出AWS EFS文件.zh_en -BV11y411z7Dn_p49-

![](img/11757f937684d9213b253850050f6278_0.png)

Cargo Lambda is a great way to deploy rust functions to Aws Lambda。

 and it really simplifies some emerging workflows that a modern compiled language like rust can do in this demo。

 I'm going show how cargo Lambda combines with EFS。

 which is a mounted managed file system from AWs to let you do really new things that potentially wouldn't be available without the serverless plus the managed file service plus rust right it's the combination of all three。

 First， let's take a look here at EFS。 So we see the elastic file system。

 It's a thing of beauty because in this case， look。

 I'm only using know17 megabytes and it can grow to terabytes。

 it can grow the discao automatically but it's also this resource where I don't have to use it all or nothing I don't have to pay for terabytes at a time。

 I can pay for what I need when I'm actually using it。 So it's a great ephemeral type resource to。😊。



![](img/11757f937684d9213b253850050f6278_2.png)

Use in serverless workflows Next up here， I'm going to use the Lada and this Lada here。

 which I've already deployed， is an EFs lister here。 And what's great about this is that。

I've gone through and configured so that the file system is actually melted directly inside of this Lambda。

 So when it launches and it does whatever it needs to do。

 I've already got the ability to actually access it from the Lambda。

 So this is a very interesting pattern here where I'm not paying for anything I'm not paying for the file system not paying for the Lambda Intel。

 I actually need to use it。 And because I'm using rust， it's going to be incredibly efficient。

 So the question is， though how do I actually develop against this。 Well。

 one of the ways to do this is to use cloud 9。 So with cloud 9 here， you can see here。

 I've got some rust stuff already set up And if I go to rust see dash version。

 we can see that rust is already installed here and what's really great about this as well is that I can also look at my history and and figure out how to mount the file system that I've melted before。

 So if I go back here。

![](img/11757f937684d9213b253850050f6278_4.png)

We can see， oh， look， all I have to do is follow these directions。 So I'm gonna。

 I'm going to make a directory here。 So， in fact， if I want to be lazy。

 what I can do is I can actually grab these make a new file here and just throw these commands inside and then I can just follow them。

 So let's go back to。Here and just run these commands。 So first step， we've got make a directory。

Which will be the MT EFS。Oh， it already exists。 So that's good。 So in fact。

 if I've already done that， then what's great is we can see does the mount directory already exist。

 So looks like it exists， but nothing's mounted。 So let's go ahead and mounted。

 Let's go ahead and go up a couple levels here。 In fact， we can just go here。😊。

And go back into our environments and now I can just run this mount command， perfect。

 and we can also run this command if it wasn't already run。

 I'm pretty sure already already ran this and this will just double check that we've got the package looks like it was already done。

And then from here， we can actually， if I needed to it， mount it again。

 or we can actually see what's inside that directory。 There we go。

 So we see that there's stuff inside of here。 So I've got， you know， large language models。

 pretrain models， you know， whatever it is you want to put inside of here。

 And this is a great way to develop as well， right， because I can just say， you know， I don't know。

 I want to put a file inside of here， a new one， and we'll just say， mounts。EF。

 and we'll call this demo video。呃。I was here。DotTXt。And now， if I do L S， here we go。 demo video。

 I was here。 So that's all working。 Now， let's look at the code here and see it actually in action。

 So I'm gonna go to the check out of here that I have the。The code that will talk to this。

And this is going to be an EFS lister。 And now let's go ahead and take a look at what that code actually does。

 So here we have the cargo file。 first， let's pull that up。

And the dependency here is that we're using the Lambda runtime and we're using the recommended libraries like Tokyo and Tracing that they recommend with Lambda。

 and also that again， I'm using the cargo Lambda system to deploy it。Next up。

 we also have the source。 and if we go through here and we look at the main here。

 I have some code that decsializes and serializes the data。

 I also have the ability to do the helper function that lists the files in the EFS volume。

 And you can see here it's pretty straightforward。 I just asynchronously read this inside my lambmbda and I run it and then finally over here is where I pull together in my Lambda function。

 So it's in many ways， pretty similar to let's say AWs Python with Lada except for it's extremely efficient and is if very easy deployed process。

 So now that of all that all that stuff cooking here， I then pull together in the main function。

 Now how do we run this。 Well， I could run it from the terminal here。 that's one way to do it。

 Or I also could just run it from the EFS that's already deployed So let's go ahead and test this thing。



![](img/11757f937684d9213b253850050f6278_6.png)

And I believe that just a hello world test should probably be fine。

 We could just leave those values in， or I could even do an empty payload doesn't matter either way。

 Let's just do an empty payload。And let's save this what was called this test。And here we go。 And oh。

 it says that there's a problem。 It's saying， oh， a missing field name at line 1。 Okay。

 so to test it， it's going to need a name field。 So let's just go ahead and say name。

 and we'll just say， you know， test。 All right， let's go ahead and save it， Test it again。

And there we go。 We're able to to actually get it， get it cooking here， which is great。 And now。

 look， it gives us what's inside， and we should see。😊，Exactly the file that I created。

 which is demo video I was here。 Now a couple other things to point out here is look at this。

 the build duration 14 milliseconds， right I mean， this is just amazingly efficient。

 also the memory is extremely efficient as well。 So this is something that is not really in the realm of what a scripting language can do。

 it just can't do the things that a rustbased efficiency can do in the deployment as well as trivial because the binary that gets pushed over here。

 So in a nutshell to summarize what we're doing that EFs is an emerging standard that mixes with rust and also the Aws Lambda ecosystem for large language models for dataan engineering and really it should be something that your organization investigates again。

 if you take a look at this code here。 is this is pretty straightforward。

 there's not even 50 liness of code to get this Lambda cooking。

 and we know that it's going to be very secure。 rust is one of the most secure languages。



![](img/11757f937684d9213b253850050f6278_8.png)

It's going to have performance that's similar to C， so check it out。

 see if you can mix together in your organization， EFS， Lambda and Ru。



![](img/11757f937684d9213b253850050f6278_10.png)
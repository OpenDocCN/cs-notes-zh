# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p80 80_04_05_基于EFS挂载的AWS Lambda无服务器MLOps.zh_en -BV1Hy411q7Zm_p80-

![](img/b30c7bddd90c5fd11bc7040151d0f5c1_0.png)

Let's take a look at this project， which is MLOs inference using the Onyx model format mounted via EFS and also invoked via AWS Lambda。

 So the reason for doing this is so that you can use serverless technology like in this case it would be AWS Lambda to serve out inference。

 and this is an emerging standard here where the advantages of serverless is you don't have to manage it。

 It's easy to deploy especially if you're using a high performance language that supports binary deployment like rust。

 all you need to do is go through here and deploy a binary that has the ability to mount the model via EFS。

 so let's go ahead and walk through exactly how this would work。 So first up。

 you're going to need to have access to EFS， you're going to need to create an EFS Mapoint will cover that in a second and your development environment at least。

In terms of putting the files there probably should be something like AWS Cloud 9。

 and so what you need to do is follow the instructions for EFS on how to mount the EFS volume on the cloud 9 environment。

Put whatever you need on there， for example， you could put 1 to 10，20 onx models， mount them in EFS。

 but you also need to make sure that you're able to expose port 5049 so that it is able to actually talk to that cloud9 environment。

 similarly with AWs Lada， there's a couple things that you have to do that are nonintuitive again through a VPC。

You'll need to actually have access to port 50，4，9 so that those two services can communicate with each other and you'll also need to set up a file system。

 And this is actually a component that is available with Aw Lada you can set up a file system and one of the things that you have to do is actually set up an access point via EFS in order to do this And again。

 we'll walk through this in a second。 Finally， once you've got all that set up。

 you can then go to a different development environment if you want。

 I prefer Github codespaces and you can use the cargo Lambda package to go back and forth and test out your deployment and actually get things cooking。

 So let's go ahead and walk through how we would do that。 So again。

 the goal here is to use this Onx runtime here because it is the ability to really refine the way you invoke models you have the ability to use just this runtime for multiple formats It actually has better。



![](img/b30c7bddd90c5fd11bc7040151d0f5c1_2.png)

Forments and smaller size as well。 So that's really the goal here with that。 So first step here。

Let's go over to the file system， EFS。 So if we look at Amazon EFS here。

 you can see it's an elastic file system to create one。 It's pretty simple。 know。

 you just go through， you just create a default file system here and that's it。 Now。

 once you've created it。 if we go through here， let's take a look at some of the things that are important to be aware of。

 So one of them is the attachment。 So in order to put the files onto EFS。

 you're gonna have to attach it。 And so this is a really good way to start is click on attach。



![](img/b30c7bddd90c5fd11bc7040151d0f5c1_4.png)

![](img/b30c7bddd90c5fd11bc7040151d0f5c1_5.png)

And notice that it will give you the ability to mount V and D S， which is a good idea。

 And all you need to do if you use the EF S Mount Telper is just run this command。

 and then EF S will be available on， for example， Cloud 9。 Now， the one thing to be aware of here。

Is that you do have to set up the security group。 So let's go ahead and look at this and we go over here and we look at the instructions here。

 You can see that this is really a how to guide on step by step on how to set it up。

 So I would recommend use the mount helper here。 go ahead and do that Once you've got that set up。

 Let's go over to EC2 here， you're going to need to make sure that your security groups have the ability to communicate via 5049。

 So anything that communicate whether it's cloud 9， a virtual machine Lambda。

 it must have the ability to talk to that 50，49。 So now again， if we look at the the source here。

 the important thing is to look back。If we go back to this file system and we look at the network here and we look at the security group。

 if we see this， these are the security group here。

 that is going to have to be hooked up again into into here so that you're able to actually communicate via 5049 so this is probably one of the trickiest things to remember initially once you've got that setup then the other thing that is a little bit tricky is we have to go back over to this onyx Lambda that we've set up here。

 you can just set up you a Lambda function is that under configuration you do have to have a VPC so notice here we've got this VPC so that we've been able to communicate with the security group that we care about here and also the other thing that we have to set up here is we have to set up the file system so this is probably the trickier part here is if we go to file system notice here that we have file system ID。

We have access point。In order to set up the file system and notice， we also have the mountpoint。

 which I say Mountpoint EFS in order to set that up， if we go back to EFS here。

And we go to access points。 That's all you need to do is you just say create access point。

 Once you've created the access point here， you can actually then mount it into the Aws Lada。

 Now there is actually a nice article that I would recommend looking at that will expose a little bit information if we go through here and you go using Amazon EFs for Lambda in your serverless application。

 It'll walk you through all the steps that you can go through how to create the file system。

 etc cetera， etc cea。 So that's really it is just to have those things hooked up here now finally。

 once you want to start developing once you've copied the Onx file over there。

 the only thing you need to do is again go into whatever it is that you've got in this case I have Onyx EFS Lambda。

 let's go ahead and seed into this directory。

![](img/b30c7bddd90c5fd11bc7040151d0f5c1_7.png)

Let's take a look at the code。In this code here。First。

 I have a library and this library code allows us to basically do an OnyX inference Now notice this is important here is that I'm saying with the model from the file。

 use the model that I put onto the EFS file system in this case it would be M and T EFS squeezequenet and then once I do that I do my invocation in the code and it returns back the score in terms of the main right here。

 the other thing to be aware of is that I have a little helper method that I like to put here that look what it does。

 it actually reads the mountpoint and list the files just so I can verify that I know what's inside of this mountpoint。

 I think that's a typically a good idea and then finally inside of here。

 I just do the invocation which again does the scores and gives us the results of the inference from the OnX runtime。

Now the only other thing that we need to do to kind of play around with this is I like to put a make file here together so that I make it really easy to test it。

 so in this case。I would just need to source my virtual environment because it does actually use Python。

 believe it or not to use the deployment。At least in order to install the extension for cargo。

 and then in order to test it， I can just type in make andvoke。

And this will actually send a payload over to the Lambda and notice what it does。 It says， oh， look。

 I'm mounting this runtime。 So I think this is really a good idea for debugging is to have that list type method available。

 And then again， you can just invoke it and you can see that， in fact， it is running。

 So there are quite a few moving pieces when you're building this。

 you can actually go through and look at this repo here。

 this rust Iovs template go to Onyx EFs Lambda。 And this will be able to walk you through。

 But I think that the big thing as well is just to from architectural standpoint。

 remember what the key pieces are。 This is the center that everything needs to talk to。

 you must always have access to 50，4，9。

![](img/b30c7bddd90c5fd11bc7040151d0f5c1_9.png)

Follow the EFS mount instructions that are available on the console for EFS to mount this。

 copy the model onto from this location to EFS on Lambda， you've got to again。

 make sure that the VPC is set up and it has access to 50，49。

 make sure you set up the file system access point and this is actually what's going to invoke it so you can even evoke it by just selecting it in terms of development。

 I do believe Github codespaces is an ideal environment to developing because you get access to Coil it。

 you can actually go through and test back and forth。 So that's it And nutshell。

 I think this is going to be an emerging way that MLOs is going to be used in many organizations as they leverage rust plus Onyx plus EFS plus AWS Lambda。



![](img/b30c7bddd90c5fd11bc7040151d0f5c1_11.png)
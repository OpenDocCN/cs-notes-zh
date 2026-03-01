# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p88 88_04_06_构建并部署支持函数URL的Polars Rust AWS Lambda.zh_en -BV1Hy411q7Zm_p88-

![](img/dcb71d4e2a5109fd9896b847b0c40182_0.png)

Okay， what's better than rust with Pols and AW Lada。

 a URL that we can call to filter queries into the data frame。 Okay。

 let's go ahead and take a look at how that would work。



![](img/dcb71d4e2a5109fd9896b847b0c40182_2.png)

First up here， we have our code， and you can see there's a general tree structure here。

 So if I say tree。Dash I。 and I filter by the target。You can see the structure。

 which is Lib main right here。 So now that we've got that structure。

 What do we need to do to get this thing working。 Well。

 let's go ahead and seed into polars Lambda axon There we go and inside of this particular project Not here I'm using a web framework to do the routing for me。

 but I'm still doing this inside of Lada。 I have a hello world route and then I have a simple route here that is able to look at the irris data set that I've got included I filter and I pass in this five value and then I calculate that from this data frame。

 So it's using the lib here， which has all of the fancy polars code here and then I'm going to pass that in and then convert it to adjacent payload。

 Now I just call it inside of my aync function here。

 So pretty straightforward to test this out locally。 What do we do Well。

 we can just type in make watch here， which runs the cargo Lambda watch command。Thats simple。 Now。

 all we need to do is curl it to test it out。 So we know there's two routes。

 Let's go ahead and do curl first local host 9000。Awesome， that works。 Hello Pols。

 And then if we want to pass in some parameters， we can do filter 5。 There we go。 Awesome。

 So it's working。 now， what do I do， Well， let's go ahead and kill。😊，There's terminal here。

And then let's push this out to production。 So let's go ahead and do a make。Build and deploy。

 So let's do this command first， make build。And make deploy。All right。

 this is going to do a very efficient arm 64 release because I love saving money。

And while this is deploying， once it's successful， what we'll be able to do is actually。

Turn on the URL function feature inside of Ews Lambda and then remotely invoke it。

 which is pretty fun。 Okay， our Lada was deployed successfully。 Let's go ahead and take a look at it。

 Next， if we go over to our Lambda functions here。 Let's look at last modified。

 and let's refresh it 15 seconds ago。 That's the one we want。 perfectfect。

 let's go to configuration here and let's go to function URLs。 There we go。 Let's do it。

 No authentication for demos。😊。

![](img/dcb71d4e2a5109fd9896b847b0c40182_4.png)

All right， and we can just copy this function URL， and then we can go back to Vi Studio code and we can actually trigger this thing。

 So let's go ahead and do that next。 So we'll just type in curl。



![](img/dcb71d4e2a5109fd9896b847b0c40182_6.png)

Awesome， and then we type in filter。We type in。When we do iris？Filter 5。Beautiful。

 so we have a full web service that's using polars and we're using the AWS Lambda function URLs。

 I call this victory。

![](img/dcb71d4e2a5109fd9896b847b0c40182_8.png)
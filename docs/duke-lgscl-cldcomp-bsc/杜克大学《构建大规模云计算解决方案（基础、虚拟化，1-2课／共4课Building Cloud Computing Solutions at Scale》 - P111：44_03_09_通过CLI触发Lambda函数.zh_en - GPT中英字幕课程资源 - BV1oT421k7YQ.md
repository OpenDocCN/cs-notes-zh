# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P111：44_03_09_通过CLI触发Lambda函数.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's take a look at how you can also invoke a Lambda function using the command line interface。

Oftentimes it's easy to use the Lambda function in the console and test out。

 but there are a lot of use cases where invoking it from the command line can give you incredible power and automation power for let's say scripts that you're going write let's go ahead and take a look at how we do that so first up let's take a look at this Lambda function again you can see here that this is the event that goes in and I'm going to look for the word name Marco and if I find it it'll return back polo so to test it out。

 I can go here really quick test this thing out call this Marco put in name Marco。So， name。Marco。

 great。 so once I invoke this next step， what I'm going to do is I'm going to return back the word polo。

 So here we see that there's a polo that shows up Now I also can do the exact same thing by using the commandlan interface。

 So let's go ahead and take a look at that。 if I go over to a terminal here。

 and I run this particular command and notice that in the cloud 9 environment。

 this is installed automatically the AWS commandlan tools and this is one of the key advantages to using cloud 9 for AWs development I type in AWS Lambda invoke function name and I put in the name of the Lambda function that I want to invoke and then I give it a payload in this case。

 the payload is the same thing。 It's name Marco， I then give it a file to put the output。

 So the way this commandlan tool works is you have to give it a file that it'll put the output in and then I just run this pipe command。

Will print out what happens so there we go， you can see that it returns back polo and if I run it again with a different name。

 we'll call this maybe。Out two， we can see that there'll be a different outcome from a different payload。

 so instead of having Marco here， what I will do is I will put in Bob， there we go。

And if we run this out， you can see that it didn't work because I needed to。Put the。

The name here a little bit differently。There we go， no， so in a nutshell。

 this is a great way to invoke command line tool is to use it from the command line and you could see how maybe even doing a highly distributed operation where you are going to process a lot of things by invoking it in a command line tool。

 you can get a lot of power。

![](img/929e3abe540d528fbc7954aefc99b831_1.png)

![](img/929e3abe540d528fbc7954aefc99b831_2.png)
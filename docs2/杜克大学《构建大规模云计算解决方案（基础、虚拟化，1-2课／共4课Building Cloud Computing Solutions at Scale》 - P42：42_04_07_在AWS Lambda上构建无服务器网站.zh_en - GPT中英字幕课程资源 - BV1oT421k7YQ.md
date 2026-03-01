# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P42：42_04_07_在AWS Lambda上构建无服务器网站.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

In this lesson we're going to build an AWS Lambda website。

 let's talk a little bit about AWS Lambda in a nutshell， it's a Python function。

 it could be function in another language， but in this case we're going to do Python and this Python function is hooked up to a trigger。

And it could be any trigger that you could hook up to build something out in this case we're going to build a trigger around the web so we're going to hook up an HttP trigger to it so what this means is that if I click on a URL it'll map down to this function and it'll actually call it and that's all it is when you're building a AWS Lambda function and later if I wanted to hook this up into other kinds of events maybe I could hook up into maybe an S3 file that's event a file placed on S3 or if I wanted to listen to SQS which is a queue I could hook that up but in general it's just a piece of logic。

 I hook it up to an event and then I can serve out a website so let's go ahead and build this。

Once again with AWS Cloud9， what we can do is build out a solution inside of this cloud9 environment for Lambda to do that。

 I'm going to select this tab AWS Resources。And from here。

 I'm going to move this over a little bit and there's an icon for create a new Lambda function。

 I'm going to go ahead and click on that。And if you notice。

 it says build out a function name and an application name。

 so I'll go through here and just say hello， cloud。Lambda。

And it'll automatically fill out the application name。And then it'll ask me for a runtime。

 so Lambda does support multiple runtimes and cloud 9 supports both node and Python。

 I'm going to select Python 36， and then I'll go ahead and say an empty Python function。

Next up here's where the trigger comes in， I am going to build a website so I will take this trigger which is API gateateway and select it and that's going to ask me where is the location I want to map this to so what is the URL path to start with I will go ahead and say the slash path so the root path and then for security。

I'm going say none， I just want to serve out a very basic web request okay and then from here I don't need to do any special privileges。

 it's just going serve out HTML and I can go ahead and say finish great now that I've got that set up it'll build out a scaffolding for me inside of here so you see that it it goes through and it creates this whole structure for this project including a file here。

 a virtual environment and some other things well all I need to change is this lambda function itself as a handler In fact。

 in this case we're not going to even capture the event we're just going to build out something that returns back raw HTML so anytime you get a scaffolding like this can you can go through and put your logic inside of here so I'm going to just paste some code I have prepared earlier and notice that I say content is a variable and I put some HTML in there so I put an HTML。

Tag and I say you know here's my hello website Lambda paragraph and then notice I return a response here and the response in the body is this content so this HTML it returns back a status code of 200 this means that a web service is successfully retrieving a code and then for the headers I say look to the web browser I say I'm going give you HTML that's it so once I do this I also could build out a website the difference between this and a static one is that it's called every single time someone makes a request so。

Now that we've got this set up， I'm going to run it locally to do that。

 I'll go over to this Ho cloud Lambda directory and right click on it and say run run API gateway local what this will do is it allow me to test it out in this local environment So this is one of the key advantages of AWS cloud 9 notice that it fills in a get request which is a way of saying I want to grab some information from this application when I run it it comes back and it gives me the results that I expect perfect Now the next step after I've tested this is I could go here。

 right click on it and then do a deploy and this will deploy it into the AWS console we'll go ahead and do that Now once it's been deployed I can go back to AWS and you can see that it's now been in this location and the key things to point out here are that notice that its sets。

This API gateway trigger。I also can look at my source code if I want to by selecting this icon and I could edit it and change it if I needed to。

 but in general the main thing to look at is this API gateway and if I scroll down and if I select this API endpoint。

 it'll serve out my HTML request so let's go ahead and try it out。There we go， hello website Lambda。

 so in a nutshell the key component of building this is this Lambda interface and the fact that I can hook it up into an API gateway。

 I could later add different triggers as well or leave this trigger alone。

 but this is a key capability of modern cloud computing。



![](img/112d2595ed2c79a082bb39ef13b84528_1.png)

![](img/112d2595ed2c79a082bb39ef13b84528_2.png)
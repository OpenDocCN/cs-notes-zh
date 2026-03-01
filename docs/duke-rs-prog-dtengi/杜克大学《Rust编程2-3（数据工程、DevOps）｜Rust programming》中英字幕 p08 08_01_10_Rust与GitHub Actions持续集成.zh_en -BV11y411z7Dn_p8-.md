# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p08 08_01_10_Rust与GitHub Actions持续集成.zh_en -BV11y411z7Dn_p8-

![](img/2fc5fbde4de0e19b2b000631673653f9_0.png)

Here we have a new project template that I'm going to use to set up a continuous integration for Github actions。

 Github actions is a way of testing your code and even deploying your code automatically。

 So I'm going to go ahead and say use this template to create a new repository。

 Let's go ahead and do this。 and I can put it into a place here where I say。Gitthub。Actions， rest。

 example。And for the description， we'll just say build and test a rust。Project。

And the goal here with setting up a new project is that it allows us to from the very beginning。

 set it up for continuous integration， which is a Devouts best practice and really does help you build out microservices in a faster way because you have a quality control process that improves your code over time。

 So I'm going to go ahead and create a new code space here。

 let's go ahead and say new with options rust does benefit from powerful machines and I'm going to use a 16 core machine so that the compilation will go very quickly。

 So what will happen is this will set up a rust-based environment for me to allow me to build code inside of here and as it's building out this project the other thing thatll allow me to do is push changes so that I can test out a Github actions workflow。



![](img/2fc5fbde4de0e19b2b000631673653f9_2.png)

Here we're inside of GitHub code spaces， and you can see here if I type in which cargo cargo is already ready for us so we can go ahead and start a new project。

 I'm going to go ahead and say cargo and we'll call this test rest here， and that will be the name。

 We' use the knit command。And we'll， we'll go ahead and do this。 Na is equal to testing rust。

 and we'll go ahead and。Create a structure here， as well。

So we'll go ahead and say touch source Lib do S。 We'll also say maketer。嗯。Dash P test。

 I'll go ahead and touch inside of test a test underscore。Live Rs， perfect。

And we've got all that set up here。 So really the only thing I need to do is put in some code。

 already have some code from another project。 I'm just gonna to paste this inside。 So for the main。

 we'll go ahead and paste this inside and I'll also paste in the Lib file。

 which I had already previously built Let's go ahead and paste that in here。And then we also。

Could go to the test file and just copy and paste the test file as well。And paste that in here。

 So now that we've got all that set up。It's going to be pretty easy to change it a little bit。

 So we just have to say instead of unit test， we'll call this。Tea rest here。Great。😔，Here。

 that looks good。One of the nice things about rest is how good it is at understanding we can do the same thing here。

 We can， in fact， just do a search or in place。And we can just replace that with T。

And we just go ahead and do that。Perfect， and because we have a make file here。

 we can actually go through and do different commands， like we can say， make formats。

And we see all the code is well formatted if we want to type in make Lint。

This will tell us if things are working properly。It looks like they are。

 and then if we want to do make test。The test will go through and run our tests， and we can， in fact。

 see four of them ran successfully。 We can even take out the quiet here。To， to double check that。

We see everything that's happening perfect。 Now， the real thing that is going to be important is to verify that our Github actions workflow is successful。

 So if we go through here， we can see how inside of this environment it's going to run on a bountu。😊。

It's going to pull in the rust tool chain here， and it's going to say make Lint。

 and we can even see what it does。 So since we've tested all those things locally。We are able to。

Fully verify that these steps should work。 Now， there is something called make format check。

Which we don't have here， so instead we can just tweak this a little bit and we can just say make format。

Perfect。And now that that's all set up， I should be able to say get status。

Add in the things that I've changed。 so we'll say gi add dot Github。Get。Add star。

 Add everything else。Also， add the。Get ignore。And if we say get status。

 they should all be ready for commit， we'll go ahead and commit them。Ready。For C。

Continuous integration。And that should trigger it。 So if we want to go ahead and check this out。

 we would just go over to this repo right here。

![](img/2fc5fbde4de0e19b2b000631673653f9_4.png)

And we can go over to actions， and actions is triggered based on。The operation that we just did。



![](img/2fc5fbde4de0e19b2b000631673653f9_6.png)

Which is we hooked up the build system into this process and it's going to go through and it's going to verify all of the different steps。

 What's also nice about this is that each of the steps has been broken out So we see that there's a build binary release step。

 there's a linting step， there's a rust formatting step and look we can see that the formatting appears to have been successful and we also have the test step and the test appears to be successful。



![](img/2fc5fbde4de0e19b2b000631673653f9_8.png)

And the Lntes appears to be successful so for all of these。

 if we go to all workflows and we build by our release， we don't really care about that one for now。

 but basically thelyntting formatting tests are all successful and we could go over here and we could say create status badge copy the status badge and then put this into this example。

 and this is a good practice when you're building things for continuous integration is you want to let everybody know and we can even call this。



![](img/2fc5fbde4de0e19b2b000631673653f9_10.png)

![](img/2fc5fbde4de0e19b2b000631673653f9_11.png)

A example。Of。Rest， CI pipeline。So， tests。Our rest code。With Github。Actions， right。

 so this is the the heart and soul of continuous integration is that you have something you're able to work on locally。



![](img/2fc5fbde4de0e19b2b000631673653f9_13.png)

You verify that those steps inside of I， I would recommend a make file here are all able to be run successfully。

In fact， you could even run them all together if you go here and you say make all。

And then those same steps are able to be replicated through your build system。

 it could be Github actions， It could be some other build system like GCP Cloud Run， whatever it is。

 and then you have a badge share that shows everybody else that your code is actually high quality and it's ready to go and then you can build upon this to do continuous delivery。

 so this is the foundational component of DevOs is continuous integration and it's pretty straightforward to set up。



![](img/2fc5fbde4de0e19b2b000631673653f9_15.png)

![](img/2fc5fbde4de0e19b2b000631673653f9_16.png)
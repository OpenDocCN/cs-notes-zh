# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P40：40_04_05_在AWS上构建静态S3网站.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

In this lesson we'll dive into Amazon S3 and build a static website to do that we'll put a index。

ht file in an S3 bucket， you can think of S3 as a folder and this is an object that will be served out。

V the S3 bucket。And this object will then turn into a website by enabling static hosting。

So this is really the trick that we're going to do to serve out a website that will be available all over the world and globally distributed。

 so if you look at this and we look at the uptime here。

 those will be 11 nines of reliability so that means that it's 99。

999 etc up and the reason why is that behind the scenes here。

 you've got many of these replicas of this object stored。

And you can be assured that when someone goes to your website it'll always be available and another key aspect of this is that you don't have to manage any servers。

 so this is actually a serverless technology so let's go ahead and get started and build this ourselves and we'll start with the cloud9 environment。

In order to create a statically hosted website， we only need a couple things。

 we just need an index HTML file and we also need to create a bucket and enable it to have the correct permission。

 so first up， what I'll do here is I'll make an empty file called index do HM。

And I'll go ahead and edit this， so I'll go ahead and double click this and put some tags inside。

 so I'll say for here maybe HTML will be the top tag。And then inside of here。

 we can do a title that can say。You know what the name of the page is？Let's say this is a website。

And then maybe I can also put in some kind of a paragraph。Inside that says you know this。Is。

My new website。It will make it big。There you go。Great。

 so I've got a very basic HTML document here and and it's pretty much ready to go when I'm available to host it。

 So next up， what I can do here is maybe just keep this laying around and then I'll go over to S3 and create a new bucket So let's go ahead and create a new bucket in this case I'll call this hello cloud for data。

 these have to be unique name So this is a really important thing to be aware of so you would have to have a unique name for your bucket。

 Next up I'll actually enable all public access。 So you only want to do this when you're creating a public website。

 but I'm going to go ahead and do this。😊，And then I'm going to acknowledge this is the change。

 and then I'll go ahead and create this bucket。Next up what I will do is find that bucket。

 so we'll say you know hello cloud for data and I will need to give it a couple things so first I'll need to go to properties here and scroll down to find the static website hosting option right so this says use this website hosting option and we're going to go ahead and do this and I'm going to say enable。

And once I do this， it'll ask me to tell it what is the main page and this will be the index file that I created and then what is the error page。

 error do HTML， this would be if， for example， someone doesn't get a response。

 what page would be shown。And we'll go ahead and say save。

Now really the only thing left to do is to add a bucket policy and this bucket policy will allow me to correctly serve out traffic and so in order to do that I'll go to permissions。

And I'll scroll down here where it says bucket policy。

 and this provides access to the objects stored in the bucket， so the file。

 so go here and paste this in。And all that says is that every file inside you have the ability to read it。

 I'm going to change this to this location right here。And we'll past this。

And you can see that it's going to now let anyone in the world have access to this data。

 so we'll go ahead and say save Now the only other thing I need to do is go to this cloud9 environment。

 download this file and then upload it to that bucket， I also could copy it from the command line。

 but just for ease of use here， I'm going to say download and I'm going to download it to my desktop and then I'm going to go back here and go to objects and then I'm going to upload it so go through here and we'll say add files there we go。

 there's this index study HTML file great， and then if I go ahead and say upload。

How do we now know whether this works Well， if I go back to the main section here and I go again to properties。

If you scroll down。It'll have a static website hosting URL that'll now be available。

And all I need to do is click on this little link here and this will open up the view and there we go we've got a new website working so it's very straightforward to create a statically hosted website that has incredibly high availability and you can do it with just a couple steps。



![](img/45171fde71372d406e014b702336d621_1.png)

![](img/45171fde71372d406e014b702336d621_2.png)
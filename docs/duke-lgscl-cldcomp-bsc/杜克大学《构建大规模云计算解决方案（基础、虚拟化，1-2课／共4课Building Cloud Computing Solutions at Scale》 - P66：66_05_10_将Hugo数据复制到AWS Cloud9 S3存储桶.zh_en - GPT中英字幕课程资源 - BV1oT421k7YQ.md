# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P66：66_05_10_将Hugo数据复制到AWS Cloud9 S3存储桶.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

So what I'm going to do next here。

![](img/a56f17f6842925881af7e76506402948_1.png)

Is I'm just going to copy it over。 I'm going to create a new bucket。 and I'm。

 and I'm going to literally just copy the data over。Myself manually by just doing a copy in S3 here。



![](img/a56f17f6842925881af7e76506402948_3.png)

I'm going to go over to S3 real quick and go to this thing。And make a new bucket。

 we'll call this bucket。You know， Hugo Duke or something。You go Duke。

 unless it's I already used that earlier， okay， that looks good， we'll just say next， next， next， oh。

 you have more buckets than allowed。But I have a constant problem with that。

 I'm going to delete this。And it says， deletete the buckets。Oh， the name of the bucket， okay。

 there we go。This is what happens when you're working on AWS for years is you have too many buckets。

Huggo Duke。Here's our bucket。And well go ahead and create this。



![](img/a56f17f6842925881af7e76506402948_5.png)

And I think that the main gist of this is that I'm going to go to this bucket。And I'm going to。

Go to properties if I remember， and click on static website hosting。

And so this is literally a serverless technology and all you need to do is just click this button and then now you've got the ability to run websites that have again。

 119s reliability it gives you a couple things to put in here you know for options I'll type in HTML Sure we can say error。

 HTML these would be the root file。And then I can say save and once I do that the only other thing I need to do is I want to create a bucket policy that will allow anybody to actually read readate out of this and so I'll need to go to I believe it's under permissions under bucket policy and you just go in here and just say what you want it to do this is actually pretty intuitive it says every single thing inside。

 let people like look at it essentially so I'm going to go ahead and save this。Oh。

 because I need to put the actual name， I need to type in the word。Her Duke， There you go。

So this would have to be the name of your actual bucket。There we go， access denied。

Bucket air to add a new。Hugo Duke， that's definitely interesting why it's asking me to。嗯。

The block public access setting internal for this bucket prevents generating public access。

Maybe they change something。They might have。They might have。

Donone something differently than the way I did it last year。

 they're always making things a little bit more secure。

 but it looks like you have to edit public access to say yes。Then do this， then then paste this in。

 and then I can type in Hugo Duke。So this is the part that's kind of irritating about cloud computing is this kind of tweaking things。

Like this， there you go， okay， save looks like it's good。So in theory， I could actually just。

I believe even go to this Hugo section， this public directory。And literally just， in fact。

 let me just try this， I'll just download it。

![](img/a56f17f6842925881af7e76506402948_7.png)

I'll just download this whole directory。To to my desktop。



![](img/a56f17f6842925881af7e76506402948_9.png)

Just to show you in theory how simple this is， and then I'm going to go back to this bucket。

And just dump the files in there so you can see it's kind of a simple process to to create a website so we go here and I just throw this in there。

 I just dump it in there sure I'll dump it in。

![](img/a56f17f6842925881af7e76506402948_11.png)

And just say next， next， next。

![](img/a56f17f6842925881af7e76506402948_13.png)

And now that looks like it was pretty quick。 if I go to properties， I think it has the link here。



![](img/a56f17f6842925881af7e76506402948_15.png)

There you go， right？Pretty prettyty awesome how I mean， I made a couple mistakes typing in commands。

 whatever， but the gist of this is that。This is actually a professional scale website， it's up。

 it's running， it'll essentially it's a battle tank， it'll never go down。



![](img/a56f17f6842925881af7e76506402948_17.png)

![](img/a56f17f6842925881af7e76506402948_18.png)
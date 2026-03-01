# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P7：07_02_03_使用Markdown、GitHub和Jupyter Colab进行技术讨论.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

There are a few ways that you can quickly get into effective technical discussions。

 and we're going to go over four of those techniques。 The first one is GiHub in Markdown。

 so we'll go through here and mark this off。And what I'm going to cover is how to use GiHub and markdown to create an effective repeatable technical discussion。

 So first up here， if you're not familiar with GitHub。

 it's a place to create source control code and also share the code with other people so it has a lot of collaboration features so I'm going to go through here and create a new repo and a repo is where you would store your work。

 so we'll go here and say technical discussion。And it's always a good idea to put a description so this is。

A demo。Repo for sharing ideas。Around communication。

And I would recommend adding a read me file so that。

We can actually do markdown based documentation and then I'm going to add a gi ignore file here for Python so I'll go ahead and type Python here and what this does is makes it so that I don't check in garbage files that like a dot PyC file or some other file that will add noise to my repo Once I do this。

 I'm ready to do my first bit of technical discussion and to do that I can actually select this pencil icon on here and put some documentation in and I would say something like this I would go through and add these markdown based tags and you can see how the markdown language works。

 It's fairly intuitive if I go and I put in to it'll be a smaller heading so this is a second heading。

And then if I wanted to do， let's say， a bulleted list， I could put an asterisk ear and say one。

Make another one and do two and then do another one and do three。

 and I can preview those changes on the fly。And so this is a great way to build out technical repeatable discussions because not only do I give people the preview here and they can see actually the markdown inside my repo。

 but I can use this raw markdown and put it into another source like a book or a website。

 There's lots of ways to format markdown code。 So it's probably the ideal technical discussion format。

 So I'm going to go ahead and save this and then move on to step two。

 So we are able to create a readme file Ive got some technical discussion。

 So let's move on to step two here and step two will be to explore something called a gist and a gist is a way of sharing a small code snippet。

😊，And I'm going to go through here and go to Gist and it's part of Github。

 And what's nice about it is I can put in a very small piece of code， let's say， for example。

 hello do Py， and then write it up into Python， so say you know death， hello。

And then I could say return you know， x plus y or whatever it is that I wanted to put inside of here。

There we go and then create this either public gist or a secret gist in this case。

 a public one is just fine。And what happens is that it automatically figures out the syntax highlighting and what's nice about this is if I go through here and I take this particular code sample。

 I can either embed it or I can share it or I can actually have people clone it as well so if I go ahead and say share I can take this URL and then I could go back to my technical discussion and I can put let's say this is my gist。

 you know let's a gist example， this is a good example of my code。

And what's nice about this is that it's a isolated piece of code that I can share with other people and many communication tools like for example。

 Slack will auto render out what's in this gist so if you are going to share a code with somebody it's a lot better to use something like a gist because then they get the exact syntax highlighting they get the exact format and you don't have to worry about introducing weird characters that could cause problems so this is a reproducible code sample plus people can comment on your code as well so that's the next section。

Let's go into Collab and Jupiter， let's dive into this one next。

And what's great about coab and Jupiter is that it's really easy to create very complex and reproducible code so you can take a look here at coLab。

 it's a hosted version of Jupyter notebook that's available from Google and when if you want to create a new notebook。

 you can just say new notebook here and it's actually free。

 anybody can sign up using the Google tools。And I could go through here and put some documentation together。

 so I'll say technical docs。And what's nice about this is that I can run code so I can just go through here and say。

 you know， hello and put in a function， you， return high， something like this。

 and then run that cell like this。Right so is a great way to actually put exact pieces of code into a notebook and I can build very complex things here and additionally。

 I can also get access to a GPU。 so if I wanted to go here and say change runtime。

 I could pick a GPU or a specialized chip like a TPU So there's some really cool features that are available in the hosted version of Jupiter called coab Now to build out a more complex example here for documentation。

 what I would say is to do something like this， let's say I was going to build a data science project。

 I typically like to do this， I'll do you know a couple hashtags here and say ingest。😊。



![](img/046bf9eaa3b401db8fe976d10b7308fb_1.png)

And then that would be my first part of my project and then maybe build another example here and' say。

 you know EDA for exploratory data analysis and then build maybe a couple more here and say。

 for example， this would be the modeling phase。And then maybe make another cell that says the conclusion。

So the core idea here is that I can actually build out these examples that are collapsible， you know。

 build out some code， write whatever it is I want to write here。

 even put pictures and other items inside of here。And it uses markdown as well。

 so if I'm using the techniques that I covered earlier you know in the GitHub Readby。

 I could do the same techniques here， I could say， you know this is a markdown。

You know heading and then I could go through your input like one， you know two。

 etc So it's got a lot of powerful features that are embedded inside of this Now it gets even better because if I wanted to share it with someone I could click on this icon here and just create a link and then share it with anybody right I could do like a you know treat it as a Google Doc or the feature that we're going to use is I'm going to go and I'm going to say file and I'm going to save this inside of Gitthub itself。

And so what's nice about this is that it will connect automatically to my GitHub account。

 I can authenticate against it and then check this into my repo。

 so I'm going to go through here and say you know find this documentation。

That I just created called technicalical docs。

![](img/046bf9eaa3b401db8fe976d10b7308fb_3.png)

Here we go technical discussion and I'll go ahead and say okay。

 this will do a commit and then now it's actually available inside of my GitHub repo and what's great about this is that not only can people look at the code and reproduce exactly but because they can see it。

If they click on this link it'll open up their own version of it as well so this is probably one of the most effective ways to do a technical discussion is to create a coLab notebook and check it into Gitthub likewise if I want to go through here and I want to put a reference to it I could just say you know right here I could say you know coLab example right？

And now I've got this in。And say this is the notebook and notice how when I put this link in。

 I used this。Markdown formatting to reference links right so it's just the square brackets and then the link itself is with the parentheses。

 Okay great， I got this cooking so the last step here that I'm going to show you is a neat little trick where we can embed images in markdown it works with coabab notebook markdown or it also works with Jupiter markdown or it also works with Gitthub So what I'm going to do is I'm going go back to my repo which is here technical discussion and I'm going go to issues in Github and I'll say new issue and what this will do will allow me to create this ticket and what's neat about creating a ticket is that I can later put an image inside of here so let's say I want to I don't know take this notebook and I wanted to take a picture of it I can use the a screenshot here and just grab a little piece of this and this will show up。

My desktop now what I'll do is I'll drag that icon of the image directly into this location。

 so if I go here and what it does is it actually creates a URL for me and if I say submit this issue。

 notice that now appears inside of a GiHub issue。To reference this in my technical documentation now。

 I go here and edit the Readme file and then put in an image。

And this is a neat little trick that is a great way to host images in your notebook and notice when we put this in。

 you'll see that I have an image that appears as well。

 so we've covered several different forms of technical communication in this brief overview including how to use GiHub。

 how to use just how to use collab notebooks and then how to paste images。

 so all of these are effective ways to create reproducible technical communication。



![](img/046bf9eaa3b401db8fe976d10b7308fb_5.png)

![](img/046bf9eaa3b401db8fe976d10b7308fb_6.png)
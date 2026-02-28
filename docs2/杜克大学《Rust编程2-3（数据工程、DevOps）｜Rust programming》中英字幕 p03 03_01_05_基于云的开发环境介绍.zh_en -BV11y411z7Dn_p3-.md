# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p03 03_01_05_基于云的开发环境介绍.zh_en -BV11y411z7Dn_p3-

![](img/9df7b47ae5867e5d643e05a5c32bae1b_0.png)

Let's dive into using Github codespaces along with all of the common features that make it so powerful。

 First up， I'm going to go into this organization。 I'm going to select repositories。

 I'm going to create a new repo。 When you first get into Github codespaces and Github configurations。

 the first thing to be aware of is a new repo。 And you have a few options here that are important to consider one is private public。

 Let's go ahead and say public。 Also， do you want to start from a template。

 This can be a great way to save a ton of time。 You could create template for different languages。

 And then everything's already set up for you。 So let's go ahead and say template here。

 And let's see if we can find one for rusts。 If I go through here， we say rust， new project template。

 great， If you wanted to create your own dot files repo。

 All you need to do is let's go ahead and do that again。 So we'll go back here。😊，We'll go new。

And this will just see， you know， these。These are the dot files。

It should give me the ability to open this up in codespaces and codespaces are a cloud based environment that allows me to edit things inside of here。

 we'll go ahead and do that， make this a little bit bigger as well。So we'll say touch。Dot bashhar C。

And then we'll make this bigger。How about there， perfect。

 And now that I've got that bashar sea in inside of here。

All I need to do is just put something inside。E B equals vim。And we could say， you know， Tilda。

Dot BshRC， right， So basically edit the bashRC file， and then we can do another one。

 which is reload it。 and we can say R L equals， and we could just say source。The BshRC。

 So this is just a nice little shortcut here that allow me to you know。

 basically edit and reload a ba or C file。 So if I source this ba C here， you can see if I say EB。

 this would edit up。The the Vm file。 And then if I wanted to reload it。

 I could just do this and reload it， right， so now I could just check this in， just get add dot。嗯。

Bashhar sea。And we can go over to codespaces。 And under codespaces， look。

 automatically install dot files。 There we go。 No give dot files。 So so perfect。

 we've got to set up where we're all ready to go， and that'll install it inside of any repo that I need to。

 the next step that we're going to do is is actually launch this with a code space。

 So if you select code here。 noticeice it says your workspace in the cloud。😊。



![](img/9df7b47ae5867e5d643e05a5c32bae1b_2.png)

![](img/9df7b47ae5867e5d643e05a5c32bae1b_3.png)

You can pick a default one， or we can go here and say new with options。

And we can select different configurations。 So in this case。

 this is using this configuration for rust， which is what I'll take a look at in a second。

 But we also can toggle the machine types in this case。We can see there's two core，4 core，8 core。

16 core， whatever kind of machine I need for my particular problem or even a GPU as well。

 I'm going to go ahead and pick a big one，16 core。 Great， let's go ahead and launch this。

And initially， it'll take just a second to build the container because I don't have code space pre build set up。

 Let's go ahead and do that next。Let's let's go here， go to Ses。And if we go down to codespaces。

 you can use this option called pre build and what pre build will do。

Is it'll automatically install all the software that I've got configured and make this so that it runs automatically when I'm building my my repo。

 So this means that the next time I launch it， it'll launch very， very quickly。 All right。

 so we're inside of here。 we've got it all set up。 We've got this new template。

And then it's up to us at this point to decide what kind of user experience we want for this particular repo。

 So what I'm going to do next here is I'm going to go in and change the background。

 So I'm going to go ahead and say。

![](img/9df7b47ae5867e5d643e05a5c32bae1b_5.png)

Go to themes here and we'll go to color theme， dark color blind beta， there we go。

 perfect And I like this one because it has nice contrast and it's a nice dark screen here。

 And then if we want to do a G poll， we can take a look at what we've got left to demo。



![](img/9df7b47ae5867e5d643e05a5c32bae1b_7.png)

All right， so what I've already done is I've shown that you can create a repo with a template。 Now。

 let me do one thing though real quick， which is show you that if I wanted in the future to make this a template。

 I could go to settings。

![](img/9df7b47ae5867e5d643e05a5c32bae1b_9.png)

And I would select this option like this。And what this would do would mean that other people in my organization or even if it's public。

 other people on Gitthub could use this template to build off of。

 this is a really good idea for your own personal uses to leverage templates that you save a lot of time when you're creating new repo。

 So that's just something to be aware of。 And if we go back here。

 we can take a look at the key files。 There's a Docker file。



![](img/9df7b47ae5867e5d643e05a5c32bae1b_11.png)

And the Docker file is actually pretty straightforward in that we inherit from the dev containers Docker file。

 and this Docker file here is using rust。 So Ru is already set up for us from Microsoft there's not much we need to do。

 we can put a little bit more if we want to inside the command and we can say let's say update it go ahead and install maybe clang LLD。

 whatever it else I need to do and I can do that every time the machine launches again。

 because we're using codespace the pre buildds， it can actually do this automatically。

 The only other thing to configure would be if I wanted to go inside of here and tweak things a little bit and I can really do things like install certain extensions。

 etc ce， etc ceter， and put these in。 Now one thing I will change here that will get us to the next lesson is I'm going get rid of this because I need to actually tweak things a little bit。

 So let's go ahead and get rid of that。And in order to persist extensions here。

 you could just save them inside of here， but what I'm going to do。

As I'm going to go over to extensions here。 I'm going to find that Github Copit chat is something that I actually want to install。

 So let's go ahead and select that。 Now that we've switched gears here。

 what we can do is start to play around with something called Github Copit chat or coppit X and it's a very powerful feature because it allows us to act like we have a pair programming friend here。

 So here we go， We NoA gift， I'm your coppit。 and I'm here to help you get things done。

 generate Uni test， Explain the code， propose fixes。 Well， say I want to create a new rest project。

All right， let's see what it says thinking。Okay， all we have to do is say cargo new new project。

 Okay， great， let's go ahead and do that。 Let's just say cargo。New， and will say。

 instead of my project， we'll just call this hellello world。Youre， great。And then it says。

 how do I run my project？Oh， you just say cargo run。

 So let's go ahead and take a look at the code here。And we see that inside of hollowello world。

 we have a main， and we， we see that that's the actual code。 Again， if I toggle back here。

 it's going to tell me。That I would need to see the into Hello world。 And this type B cargo run。

And we've got this cooking。 Now， let's ask it to change things a little bit。 Now。

 notice that it says here that it will compile run the project。 if your project has a main。

 it will be compiled as binary run。 If your project has a lived out rest。

 it will be compiled as a library and not run。 So let's do that， right。

 So let's go ahead and create if we type in tree here。We see that in fact。

 there is only the main inside of this location。 What we can do is we can just say， you know。

 create an add function。And guess what it goes through and it creates it。 Not how this says public。

 So it's going to be exposed publicly。 Now， in order to use this， I would just go back。Here。

 and we could just go ahead and say。You know， result。Equals。Hello world add。

 So it's going to use the cargo name right here。Inside the package to actually use the library code。

 Let's go ahead and try this out。 Let's see if it works。Let's go ahead and change it。Like that。

And we can just say cargo run。And oh， we have a small ear here。

 So this is one of the nice things about using a very powerful language like rust is it tells you very verbosely what mistakes you've made in this case。

 that's all we got to do。

![](img/9df7b47ae5867e5d643e05a5c32bae1b_13.png)

We run it。 Hello world 1，2，3， perfect。 All right， let's take a look here at this Github Copit Ci。

 This is one of the other features I wanted to show you that's really amazing。

 This is a technical preview， you can see that it's not perfect。

 but we can do some amazing things here by just typing in the two question marks and asking it to actually help us out with command。

 So if I go over here and I go and I say， you know， show me the directory structure。😊。



![](img/9df7b47ae5867e5d643e05a5c32bae1b_15.png)

![](img/9df7b47ae5867e5d643e05a5c32bae1b_16.png)

Let's go and see what it tells us。 Oh， you just run tree。 Now， what I can do is I can revise it。

 I can cancel or I can run the command。 Let's go ahead and run it， perfect。Got it。 Now。

 this is kind of annoying is that it has got all these artifact files that I don't really care about。

 So what if I wanted to actually get rid of that， So I could say。You know， run the tree command。

For a rest project。But only show。The source files。And not the artifacts。

Let's see if it knows how to figure this out。There we go。

 So we just say tree and it's gonna to ignore the target where the builds are actually run so we can actually go through and run this command。

 let's go ahead and run it。 I' sure you want to execute it。 There we go。

 Now this is a lot better because this particular project which is a little bit of a complex project is showing us that it's just the rust code。

 just some C+ plus code and some header files here that I've got set up so it's a lot cleaner to actually take a look at so this is yet another tool that's important to be aware of is this Github copilt Ci and really we've been able to cover quite a bit of stuff inside of our demo here everywhere from know creating a repo enabling dot files installing and configuring codespaces and dev container configuring and running copiled X and also configuring and running a copilt Ci。



![](img/9df7b47ae5867e5d643e05a5c32bae1b_18.png)

![](img/9df7b47ae5867e5d643e05a5c32bae1b_19.png)

![](img/9df7b47ae5867e5d643e05a5c32bae1b_20.png)
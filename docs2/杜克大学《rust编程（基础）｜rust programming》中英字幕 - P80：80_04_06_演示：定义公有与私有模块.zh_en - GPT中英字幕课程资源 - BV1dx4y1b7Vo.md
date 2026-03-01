# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P80：80_04_06_演示：定义公有与私有模块.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/7b7026e6aa4f6afac8fd73aa1b1c2a33_0.png)

Because now we know how to verify that we can actually use and import some of these modules and make use of them outside of Lib that ares outside of our crate。

The next thing that I want to show you is how to。Essentially ensure that some of these functions will be publicly available like this one and some of them might not be publicly available so what does that mean and how we can verify that well when I sayP for public is actually a keyword for rust makes a module function or data structure publicly available it can be used somewhere else besides the module where it is defined so。

Let's do this bit by bid。And in this， it means that read standarding is publicly available。

 so if I remove that， if I save that。Then if I run the do test it will fail。

 so let let's scroll back very quickly here and let's see what it actually says。

 it says that this is a private function now I didn't explicitly say this is a private function。

 however because I removed the pub keyword for public， it made a private。

Now that's tricky to kind of get used to it， but that's the default so it is defaulting to private if I don't explicitly say pub the same thing happens with module so if I go and say mod colors and save that and run the doctors we're going to get a few a few that are going to fail and let's scroll up born to previous private module。

 we can't use colors anymore now。That fails there， but if we go to colors。

 it means that we can't use CLI u because of colors right so it is kind of tricky。And we could。

 we could do something like let's try what happens if I remove that line and then I run the do test。

 so we also get to see that because redina found in in this scope so even if we say use red。

And then run the do test。 you can see that we we will still get into into trouble here。

 So that means that we don't have access to these private functions。 we're getting into trouble here。

 even though red is actually。R is actually a publicly available function。

 so we're going to need to travel， we don't have access to that where we would have access to red if is if we had some something else。

 so see for example， if I have like a private function over here， so we say example。

And then we use how about， yeah， how about both， both red and blue with example， right？

 So this is a private function。 It's not used anywhere else。 How about we remove pub。

From these functions。 And now red is available to be used。 and that's not a problem。

 So both red and blue will get used because they are right here。 So they are within scope。

That means that within this module， which is the colors module right there。

We have access two private functions in this case， red and blue from here。

 so all of these will have the ability to be exposed within the module this has repercussions for later when we start seeing a little bit of when we want to test and we want to run some tests so how would you go around testing like say for example this example function where we want to verify some of these functionality outside of the colors module if we don't have access to this because it's not publicly available well that becomes a problem so there are a couple of ways we can do we can work around that but for now let's just go back and say these are publicly available I'm going save those I'm going back to Libs I'm going save mock colors is publicly available if I run do tests we are going to get our two tests or two do tests past。

Seen back again so。Those are the things those are some of the differences when we're saying pub here and pub right there so if we want these things exposed。

 then that's going to that's the way to do it if we want to use colors only for say for example。

 functions and and other code that lives in Lib that R S。

 we could and not expose it to outside so anyone that installs our CI U library and we want to do that we can still say mod colors and that brings colors into scope that means I could do something like say for example let red string would be equals to colors red this is a red string and that would be fine because colors is coming from here but not not from CI Us because this is not publicly available not available outside of the lip。

That are as module。 So I'm going to go back and make this stay as it was before and make sure that this is publicly available。

 So those are some of the considerations that you need to have with public and private functions and modules when you're building your library。



![](img/7b7026e6aa4f6afac8fd73aa1b1c2a33_2.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p20 20_01_05_使用二叉堆创建无花果优先水果沙拉.zh_en -BV11y411z7Dn_p20-

![](img/215ccc3d1a809b15ac1e7e89ef4d89b9_0.png)

All right， in this video， I'm going to make a rust program that creates a fruit salad。

 but it has a twist here in that I'm going to assign the fruit fig。

 which is one of my favorite fruits。 The priority。 And this program uses the binary heap to accomplish this。

 And the rust standard library is able to actually build this for us。

 which is nice binary heap comes from standard library collections。

 And the first thing that we're going to take a look at， is there's an enum here。

 which is a fig and other， And then。😊。

![](img/215ccc3d1a809b15ac1e7e89ef4d89b9_2.png)

In this particular scenario here， I'm going to define figs as the highest priority by implementing OD。

 So I say implement OD。 So basically make the order here。

 and I'm going to say that basically figs here are going to be at the top and then other fruits are going to be at the bottom here。

 and then I also have partial order as well。 and then finally I get into the generation of the fruit salad。

 So what I do is I then use that data structure。 I use some randomness as well。 And I say， look。

 here's my fruits。 apple orange pear， peach， Ban fig fig fig fig fig So I just added a few figs here to kind of make the stack a little bit more oriented to figs。

 And then what I say is here's the fruit salad。 Let's go ahead and say that I'm going start with a fig count。

 and I'm going to say well figs are under two。 go ahead and keep selecting fruit。

 So I'm going prioritized for figs， but I'm。Also going to stack the deck in the favor of the figs as well。

And what's going to happen is it's going to push things down here until I've got a couple figs。

 And then it's going to generate the rest of our fruit salad here。

 So let's go ahead and run this and take a look at how it works。We go ahead and say cargo run。

We can see that the random fruit salad with two servings of figs。 we have peach， peach， orange。

 apple， orange fig fig。 You run it again。 You'll see there's always going to be a couple figs here。

Which is pretty neat and it allows us to create this really kind of customized metric。

 which again is really useful for people that are doing data engineering and the main thing to be considered about a binary heap is that it's a priority queuee and rust and it's a very handy data structure when you need to constantly pull out the highest or the lowest value from a set。

 and that's it for this particular demo go ahead and try it out yourself。



![](img/215ccc3d1a809b15ac1e7e89ef4d89b9_4.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p143 54_03_06_改进报告逻辑.zh_en -BV11y411z7Dn_p143-

![](img/f1542e82cb535a927c749ec645bdcefb_0.png)

We have some issues here with our tool that is actually trying to enforce some compliance based on some rules so what we need to do here is essentially go and deal with this loop over here so to recap if we go back to rules adjacent what we want is to check every single directory and make sure that these files are present these are required files so these ones should be present inside in this case of the Etsy directory right now what's happening is that for every single rule for every single file because of this start expanding on thatlo pattern it's looking for password and group and of course that's not there and if it's not there it will report failure on each one actually if I toggle my terminal and I do cargo run you will see this in action。

So let's take a look here。 We will see password and groupno found password and groupno found and you'll see that pattern repeat over and over like actually everywhere。

 So that's not what we want right like if you're gonna report these don't report for every single file because these are the Esy files you will see that group is reported over and over and over al right so let's let's fix this let's improve or two and you know having tools and developing these tools as you are making progress。

 it is very common to find into situations where the output is not exactly what you want or what you need So even though this is a demo and I'm trying to explain how to actually put these things into practice you shouldn't feel overwhelmed or frustrated when things are not quite right actually this is an important way of learning and in this case rust and handling the logic because it will allow you to。

Get a better understanding。 So we know for a fact that is this loop here that is within this match that is causing the problem。

 So the， the， the main thing here is that because we're dealing with a G pattern。

 we need to understand what。What is this， what is the root right if we're doing Esy slash star that will definitely expand。

So one of the ways that you can you can make these you can fix these。

 you can get a little bit better here is by capturing every single file that you've seen and the way you do that is by creating a vector So let's let's go to for every single rule we want to capture all of the files right because that will give us the ability to see everything that we've captured and check later if that file that we wanted to do is there or not。

 so let's do let's create a mutable vector here so。



![](img/f1542e82cb535a927c749ec645bdcefb_2.png)
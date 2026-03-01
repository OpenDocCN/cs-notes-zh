# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p14 14_01_07_水果沙拉命令行工具演示.zh_en -BV11y411z7Dn_p14-

![](img/e139a8491316ee084928480fe2d33c4c_0.png)

Al right， here we have a rust command line interface。

 It's very similar to let's say Python's arc parse module。

 The idea here is to use a command line interface to give us a little bit more flexibility when we're building things。

 Now let's go ahead and take a look first at the structure。

 So here you see that there's a source in a lib and a main。 So by default in rust。

 if you wanted to put some library code together。 you don't need to do anything other than inside of source。

 create a lib do Rs file。 In this case， this is the Lib do Rs。

 And I would go through and I would put in my logic。 So in this case， I expose the function。

 So I type in PB。 And this makes an item visible to others。 And then I create a V here。

 So this is pretty simple， I create a vector that includes strings inside。 So I say vex string。

 And now you just go through here and you say to string to string to string right to all of the fruits that I。

AddAnd， then what I do is I do a shuffle right here。

 So I kind of move them around to make them unique on each iteration。

And then I put them back inside of here。 So once I've got this ready to go。

 then I can go to the main。 And in the main here at the very beginning。

 we have the clapped parser here。 This is， again， similar to Python's or parse。

 And then all I need to do is say use Ci salad， Cate fruit salad。 Now。

 where did this create fruit salad come from。 Well， it's right here。

 I publicly exposed this function。 And now how do I know about the namespace， though， Well。

 all we have to do is go over to cargo tul and notice here。

The name of this package is called Ci salad。 It's going put the hyphen here and make it into an underscore。

 If I go back here。 So here， what we can do is we can see that。 In fact。

 you do have this ability right here to use the first namespace， which is the name of the project。

 And then that publicly exposed function， which is implicitly inside of live do R S。

 So this is a nice pattern that saves you a lot of time。

 I go in and I put some default things in here， like a version author， et cetera。

 I use the options to give me something that I can pass in。 And then from here。

 I can get the number of fruits that a user requested。 And then I go through here。

 and I basically tie it all together。 So pretty easy to use。

 So let's go ahead and C D up a directory here， go into C I salad。 And now， if I type in cargo。😊，Run。

 dash， dash。That will actually pass what I'm going to do into the command line framework。

 So this is really important。 This can be very confusing is when you're using a command line tool library is to use this double hyphen here。

 then passing in the argument。 So there we go。 we can see that it gives me back help the help message。

 which then lets me do other things like use the number option here。 So let's go ahead and do that。

Let's type in cargo run。And then I'll type in number， and we'll say 5。 Here we go。

 Create a fruit salad with5 fruits。 If I want to go ahead and I want to add 10 fruits。There we go。

It's going to go ahead and add 10 fruits inside of there。

 So this is a great way to really extend what you're doing once you get used to writing scripts inside of rust。

 use clap here to extend it。 It's pretty straightforward to do。

 And then also one of the great advantages is you now can do binary based deploy and give someone your command line tool。

😊。

![](img/e139a8491316ee084928480fe2d33c4c_2.png)
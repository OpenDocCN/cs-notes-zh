# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p11 11_01_04_向量水果沙拉演示.zh_en -BV11y411z7Dn_p11-

![](img/945d022ab88b88fcfc39c572b71c89f1_0.png)

Here we have a demo of how to use Ru vector data structure。

 This is very similar to Python's list data type。 We're going to go ahead and dynamically add。

 remove and access elements from the vector and we're going to demonstrate the features and advantages of this particular data structure。

 so you can see here that at the very beginning， this program creates a fruit salad by scrambling。

 shuffling a list of fruit。You can see I put in the comments a vector is a growable array here。

 so it can grow shrink in size， and it's one of the most useful data structures in rust。

 So this is really a go to data structure。 you're going to use all the time to solve simple problems。

 And in this particular example here， I use RA here。 So this will do the random number generation。

 I'm going to also use the R thread RG。 We can go ahead and take a look at cargo。

 And you can see here that I actually pull in that dependency。

 So when you're pulling things in to a rust project that's using something outside of the standard library。

 You would put this in as a dependency。Next up here， if we go back to the code。

 you can see it's very straightforward inside of a main function to define a vector。 In fact。

 here I say orange fig， pomegranate， cherry， apple pear and peach right here。

 you can see it looks very similar to a Python list。

 The only difference is I have the VEC and the exclamation point right in front of it。

 So that's a very similar component to Python。 We also see that I declare to be mutable。

 So I can make changes to it while I'm doing other coding tasks in the script。

 if I didn't want to change it。 I would just say let fruit。 and it would be an immutable vector。

And now if we go down here first up， I scramble it， so I say fruit dot shuffle。

 then I go ahead and I say print out the fruit salad。 In this case。

 I say for I U size item in fruit dot iter。 So it's in iterable。

 This again is very similar to Python and I enumerate it。

 which means that it's going to print out both the number as well as the item inside of the vector and I print those out。

Finally， at the very end， I'm able to print out this fruit salad。

 So let's go ahead and do this If I go through here and I seed into this vector fruit salad。

 All I need to do is type in cargo run。😊，It's going to build it。

 and it's going to print out this fruit salad no。Some of the things that we also may want to take a look at is going through and formatting the code。

 so if I want to go ahead and format it， I can type in make format。And in this case。

 nothing is necessary to be formatted because it was already formatted。

 but I like to keep those things inside of a make file。

 And you can see here's the command if I wanted to run it myself， cargo， FM T。Also。

 if I wanted to do a Li， we could also do the same thing， I could type in cargo clippy。

 you can see there's no problems with this particular code。

 So those are some of the main takeaways when you're building out a simple data structure with rust。

 pretty intuitive as well if you're using tools like GitHub Copit。

 which can help you do code completion。

![](img/945d022ab88b88fcfc39c572b71c89f1_2.png)

![](img/945d022ab88b88fcfc39c572b71c89f1_3.png)
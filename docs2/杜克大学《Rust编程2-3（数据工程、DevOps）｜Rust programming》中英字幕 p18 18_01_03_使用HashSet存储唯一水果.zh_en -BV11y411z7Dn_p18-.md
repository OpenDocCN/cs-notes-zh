# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p18 18_01_03_使用HashSet存储唯一水果.zh_en -BV11y411z7Dn_p18-

![](img/e950d94ddc1ded89371cbd3b8dcc97b0_0.png)

All right， in this video， I have a simple rust program that generates a list of 100 random fruits and calculates the number of unique fruits we end up with。

 So let's go ahead and take a look at the very beginning here。

 one of the key takeaways as well as I'm using the ran external crate here to help me out。

 and in particular， the sequence slice random and thread Rng here are doing a lot of the heavy lifting because they'll generate a random choice from a list of fruits。

 And a lot of times this is a great way to generate random choices is in this case。

 this is a vector and I'm going to feed it into the random selections from the random crate。

 Now we're going to use a hashet from the standard library collection as well。

 So that's another thing to pay attention to and one of the key properties of a hashet is that it will only store unique elements。

 So this is perfect for this kind of use case and then if we scroll down here a little bit again。

 this is the random。😊。

![](img/e950d94ddc1ded89371cbd3b8dcc97b0_2.png)

Stuff that we actually have some code here that allows us to you know generate a fruit。

 So in this case， we go through here and we have a fruit set and we say for you know。

 basically 100 fruits here。 let's go ahead and generate the fruit Now again。

 this is the function that does all of the heavy lifting here。 Now let's go ahead and run the code。

 I'm going to type in cargo run。And you'll see here it compiles。

 And then I've been able to generate 100 random fruits。

 And the number of unique fruits generated is 8。 Now， just because we generated 100 fruits。

 the number of unique fruits is fewer because it's possible to select the same fruit more than once。

 that's really the key takeaway here， even though this is 8。 Now， if I changed it， for example， to。

 let's say， 10， this could be kind of interesting， because the fact of randomness here。

 it would potentially change things a little bit and allow us to maybe see what would happen where many scenarios。

 there won't be 8 random fruits。 let's go ahead and run it。There we go。 Look， in this case，6。

 even though I generated 10， I run it again4 right， So because of randomness here。

 it's not always going to get to 10。 In fact， it would be not that common to get to to 10 random fruits。

's it's possible that each one could be uniquely selected。

 but then you're getting into a mathematical combination。 and you'd have to figure that out。

 But in this particular scenario here again， if I go back to。100100， we can actually see it again。

 and we're able to see this random fruit generator。

 So really the randomness plus the hashet in general are really good skills to know。

 and it's pretty straightforward to do this with rust。 And again。

 one of the nice things about rust is that it's a compiled language and has lots of safety features。

 And I could generate something like this。 for example， find all the unique customers。

 and this could be a dashboard or some kind of utility for a data engineer。😊。



![](img/e950d94ddc1ded89371cbd3b8dcc97b0_4.png)
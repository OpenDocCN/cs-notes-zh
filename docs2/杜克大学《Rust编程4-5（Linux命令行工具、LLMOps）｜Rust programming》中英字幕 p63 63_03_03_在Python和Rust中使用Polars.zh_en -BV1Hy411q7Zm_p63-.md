# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p63 63_03_03_在Python和Rust中使用Polars.zh_en -BV1Hy411q7Zm_p63-

![](img/6331b61162506a6f54a408f4e25f4e61_0.png)

Here's an example of how the rust data frame library polars could be used in a realistic project。

 First step， we have the rust project ecosystem， which includes the cargo package management system。

 which would install polars and any other libraries， for example。

 clap or criterion if you need to do benchmarking。 Once you've got all this setup up。

 The next step would be to add some integration tests， add some unit tests， add your benchmarks。

 put it all together so that you're able to verify the performance。

 the business logic as well as the contract for let's say the binary tool that you're delivering。

 So that's kind of the high levell overview。 But let's go ahead and look at polars real quick and see at some of the things that you could do So first step。

 in terms of the API here， you can see it's very straightforward in a function you would build out let's say importing a CSV file processing it。

 doing some group by。

![](img/6331b61162506a6f54a408f4e25f4e61_2.png)

And in terms of the performance， you can see that really polars is as fast as it gets。

 There isn't a data frame library that's faster than Pols。

 And you can see here that in the case of you know Polers here it's so so fast that it's almost you can't see the performance it has in doing things like reading let's say a park A file。

 So let's go ahead and dive into the code here next。

 So if we go into our project we see there's a Pol Python Ru project let's go ahead and look at the cargo file here first。

 so I used the Pols library next up。

![](img/6331b61162506a6f54a408f4e25f4e61_4.png)

Inside of the source directory here， I have a data file。

 and this is just the iris data set in terms of the main file here。

 what this is going to do is it's going to do some filtering。

 So it's going to say the rows where the column sple length is greater than five。

 it's also going to do some grouping so it's going to look at the data from the species column It's also going to do some aggregation and it's going to calculate the sum of other columns And so in a nutshell we're going to get some kind of basic operations that you would typically do with data frames。

 Now first step， what do we do， we import the necessary modules from the polar's crate。

 Now we build a main function。 So in rust if you want to build a very simple project you just need a main function。

 and that's what we're going to do here。 So I import the iris cv file。

 I then go through and I do my filter operation then I do my group by operation and then I aggregate the results by summing the specific columns for each group。

 So the sepple length。The sple width， the pedal length， the pedal width。 Finally。

 once I've got all those done， then I trigger the computation and collect results into the data frame。

 Finally， we go through here and we put it out。 So pretty straightforward project that kind of kicks the tires on what you can actually do。

😊，I actually like to use the make file here。 And in this particular make file， you know。

 if I wanted to build things， run them， test them， et cetera。

 this is where I would actually trigger things。 All right， so all I need to do now is do cargo run。

 So let's go ahead and go into this project structure here。Perfect。

 and then I'm going to go ahead and type in。The cargo run command。All right， here we go。

 We're able to actually put this into a three by5 shape and you can see here that this column is a string。

 So this shows the Sitoa， Viica versa color we have the sepple length， the sepple width。

 the pedal length， the pedal width， and it's all pulled into a nice compact structure like we were trying to do when we aggregated everything together。

 and those groups give us the results of our query。

 So in a nutshell the rustbased pullers library is a great high performance library that allows you to do things in a very fast manner。

 and if we run it again， you can see it's just lightning fast。😊。



![](img/6331b61162506a6f54a408f4e25f4e61_6.png)

In order to do the query。
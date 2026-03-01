# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p41 41_02_04_使用Rayon并行爬取维基百科.zh_en -BV11y411z7Dn_p41-

![](img/1a3fbac1ec1318af8187e51a4bc27783_0.png)

Here we have a great example of how to use threads to speed up a parallel fetch on the web。 First up。

 we use Wikipedia here to fetch pages。 And then I process each of the pages content。

 So the text inside of the Wikipedia page。 I also collect timing metrics to ensure that I'm actually doing things that I expect to be doing。

 And then over here， I have concurrent page processing。 and this is where all the work happens。

 And then finally， we're able to show how you can use a external tool。 In this case。

 this is rayon and Wikipedia to do a lot of the heavy lifting for us。

 So let's go ahead and take a look at this cargo file here。 you can see Wikipedia。

 You can see rayon here。😊，And if we pull into this particular example， you can see rayon， Wikipedia。

 Wikipedia page， etc ce， this is where I've been able to leverage the libraries that do all the heavy lifting for me in the case of Rayon。

 what's nice about it is it intelligently will launch threads in a way that allows me to leverage it to do the parallelization for me。

Here I have a process page。And then I also have a con here， which includes several NBA players。

 and in fact， nine NBA players。And in this particular example here， I have the process page。

 so I have a function here that's able to get the page and the content。 Now that I've got all that。

 all we have to do to leverage the concurrency of rayon is to use par dot it。

 So in the case of regular concurrency you would do dot iter which is just be without threads in this case。

 though I'm launching a thread per operation here to fetch those pages。 Also I go through here。

 then I process the page as well。 So I can do the same thing as well。 I can actually go through here。

 and I can say look again par iter。 and we can actually see this when I have rovert。

 it says convert self into a parallel iterator uses rayon prelude So what's nice about this is it's able to process in a thread everything that's happening in the page as well as give me some descriptive statistics。

 Finally at the very end here， I'm able to print a bunch of different metrics so。😊。

How long did it take to process a page， Also， what is the average time per page， And then finally。

 what are the total number of pages that were processed。

 And then this is also a nice metric to verify that you are in fact。

 using concurrency is what were the number of threads that were actually used。

 So now that we've got all that going， let's go ahead and run it and you can see here extremely quick it was able to process nine different Wikipedia pages and almost like it was instantaneous and we can see here that。

 in fact， we're able to grab a sentence from the first Michael Jordan page able to grab a sentence from this other page and we can see that。

 in fact， the page time， the total time， the average time， total number of pages。

 all of these give us great descriptive statistics on how to benchmark whether this is a good formula for us to use or not。

 And again， this is one of the most important parts of multithreaded programming is to。



![](img/1a3fbac1ec1318af8187e51a4bc27783_2.png)

benchmark so you know that you're improving things。

 not slowing things down or causing unneeded complexity。


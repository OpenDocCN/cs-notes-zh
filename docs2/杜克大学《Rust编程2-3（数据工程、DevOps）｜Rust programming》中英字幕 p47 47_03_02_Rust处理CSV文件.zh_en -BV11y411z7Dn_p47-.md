# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p47 47_03_02_Rust处理CSV文件.zh_en -BV11y411z7Dn_p47-

![](img/567d77c843c4fac516b8f513330b210d_0.png)

Okay， I'm inside of AW S cloud 9 here， and I want to work with some CSV files。 Fortunately。

 it's very straightforward And Ru。 So what I'm going to do is I'm going to first create a new project。

 So let's go ahead and say cargo new CSV demo。 Great。 Now that I got that。

 I'll go ahead and get into this project。😊，And let's go ahead and check it out。

 so we've got CSV demo here and we have a cargo file that we're going to need to add a library to。

 So in order to do that， what I'll need to do is toggle to a library that we can use。

 so let's go ahead and use CSV itself appropriately named。Let's go ahead and put that in。

CSP now one of the nice things about the rest language is I can also look at the CSV documentation here and just see what's going on and we can see here okay。

 it looks like there's a 1，22。 So maybe maybe that's the version we actually want to to play around with okay。

 perfect。 Now the next thing that we can do is go to the main function here。

 and we have a hello world。 So I first can just make sure everything runs。

 looks like it was able to pull in that package but I actually am going to look at the official docs here and copy what is actually running in the official doc。

 so。

![](img/567d77c843c4fac516b8f513330b210d_2.png)

![](img/567d77c843c4fac516b8f513330b210d_3.png)

I'm going to go ahead and make a data directory， which is a nice way to structure a project。

And then I'm going to copy this data right here that is from the sample and put this into my project。

 and let's go ahead and just take a look real quick what this does。

 so we say example CSV reader from Read IO， etctera， etc。And then we have a main here。

 So really the heavy lifting is this mutable variable RDR， which is a CSV reader。

 and it's going to essentially prono outout the records in the CSV file。

 So what do we need to do next is inside that data directory。

 I'm going to go ahead and create a file that has some some data inside。

 And so I can do that by looking at。A file here that I've got prepared。

 and we can just say touch data and just call this text do TX T。

And then I'm going to paste in some sample data。And let's go out and do that。Perfect。

 now all I need to do to get this thing cooking is actually to run it with cargo。

 And so that should be also pretty straightforward because Rus has such great support for running utilities so let's go ahead and do cargo run and I can just say。

Here data， and we can say text。t TXD。What happens， There we go。

 We're able to actually read in those records So really， really straightforward in rust in fact。

 maybe you could say it's more straightforward than many scripting languages because of the fact that I can bundle all this up。

 put into a binary and then give it to somebody else so check it out if you want to play around with CSV files and rust the CSV library is quite simple and straightforward to use。



![](img/567d77c843c4fac516b8f513330b210d_5.png)
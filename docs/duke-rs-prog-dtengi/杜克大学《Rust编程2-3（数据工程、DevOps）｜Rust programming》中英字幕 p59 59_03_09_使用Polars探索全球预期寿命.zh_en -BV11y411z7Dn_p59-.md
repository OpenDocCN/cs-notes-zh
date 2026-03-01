# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p59 59_03_09_使用Polars探索全球预期寿命.zh_en -BV11y411z7Dn_p59-

![](img/3af1663208700e7d7e4e29d27b7e37b6_0.png)

All right， let's take a look here at this Pols project。

 What's really great about it is that I have some CSv data。

 which is really common for data engineer and it is going to explore life expectancy。

 you can see the different columns here， country name， life expectancy at birth， total etc。

 Now once I've got all this data together again with a really common data frame type workflow from many organizations。

 you'd love to give a commandlan tool to somebody that they can explore the data more at their leisure and you know do common operations in a very uniform way。

 So what I do here is I first build out this lib do Rs。

 It's a very common place for you to put utilities and inside of here， take a look I do this import。

 I say use polars and then I build a bunch of helper functions and use pub to publicly expose them so we can see here that PB shows that the read CSV is。

I also have another function that I build which is going to print the rows of the database and then I print the schema and I also print the shape of the data frame so you could see here how you could put lots of different other helper functions here for other people to use in your organization and there could be even a common pattern that you use I also in the cargo do2ml all I need are two libraries right first polars and I've actually hardcoded to this specific version。

 this is another great feature of rest and also with clap。

 which is the commandlan parsing library Now if we look at the main dos I use inside of here the whole tool together and I have a con here that is going to look at that particular data directory。

Once I've got all this stuff set up， I'm pretty much ready to go， I can just go into the parsing。

 put some information about the version， the author， you know what the tool does。

 even put a little example here of how to run it I think is a nice touch for people that are going to use the tool and then inside I put in the different operations that I want so I have a print I have a describe。

 I have a schema， a shape， a sort， all the stuff really is able to be captured together。

 and I even have some default values Once I've got all that setup up right the lib。

 the main everything， the command parser， I put it into the main function here which then just does matching right it says。

If this particular option is put in， run this command， if this other option is come in。

 let's do this command and then at the very end here I have some logic here that just really cleans things up and lets me use data frames in a very pleasant way and then that's it at the very end I'm able to actually take this and make a high performance pure rust-based data frame tool that I can give the binary to and I'm not going to have to worry about weird installation problems and this is really the advantage of rust over Python for data engineering。

Here we go， Let's go ahead and run it nice。 I've got the data frames all printed out here。

 and in this particular example， it shows what the shape is 3 by 66。And I have the country name。

 country code indicator， right， so I have a really good overview of what's happening because I was able to write that helper code that does all the hard work。

But we can actually make a little bit more sophisticated because I did that work and I can sort things。

 right This is a really common operation you'd want to do as a data engineer or data scientist。

 Let's go ahead and sort the top 10 countries for life expectancy and again you can see as lightning fast we go through here。

 we see that countries in Asia have amazing life expectancy， also Australia。

 Europe there's some amazing life expectancies here。

 and I can see this very clearly because the tool was well architectected。 So in a nutshell。

 I think it is important to consider for data frames that pure rust solutions have many advantages。

 including security， portability， performance over traditional scripting languages like Python。

 for example or R。 and highper data engineering tools should look at using pure rustbased solutions。



![](img/3af1663208700e7d7e4e29d27b7e37b6_2.png)
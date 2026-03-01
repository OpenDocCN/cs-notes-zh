# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p51 51_03_06_Rust调用AWS S3存储.zh_en -BV11y411z7Dn_p51-

![](img/2e0ea2c22042911ff0f24fcba0949722_0.png)

Here we have the AWS SDK for rust， which is a great way to develop for AWS because the rust language is a modern compiled language that has many solutions solve that other scripting languages or older compiled languages wish they had solutions for。

 So， for example， threads asynchronous programming， security deployment。

 all these things are natively great with rust。 So it's really an ideal tool for dealing with a cloud provider like AWS。

 So let's go ahead and take a look at a example of this SDK。

 all I need to do is say cargo new SDK example， and put this in to your dependencies。

 and then when you build out some code pretty straightforward you would have to use Tokyo to do the asnc version of the API call but then it looks very。

 very straightforward。 So let's go ahead and do this。 let's copy our command here。

 which is cargo new SDK example。😊。

![](img/2e0ea2c22042911ff0f24fcba0949722_2.png)

For。And I'm going go into the environment here environment for cloud 9。

 Now I could just go ahead and build this， create a new rust project。

 but I've already done this and I don't need to actually do a new cargo project。

 So what I'm going do instead is I'm going to go inside of a directory here and look at a project that I've already got built。

 So let's go ahead and go into this project which is AWS meta S3。 Now look at my cargo file here。

 you can see here that I've been able to put the name of the package。 I have AwS config Aws SDK S3。

 I use Tokyo as well。 and now I also use kmelan tool library clap so that I can orchestrate things。

 Finally inside of the lib here。 we can see all the heavy lifting so we've got the AWS config data。

 I have a new client that I create。 so this is a public function that's async again。

 so I have this great async performance。Also have an async list buckets function。

 So it's nice about this is it will go through and again。

 make these calls in a way that's extremely efficient over the network。

 And then what I do is I get the size of an AWs S3 bucket by summing all of the objects in the bucket。

 So you could see this could be a very expensive operation if you have lots of files in the case of of my particular buckets。

 I actually do have quite a few files inside of here。

 And so it's gonna to be a very expensive operation if I'm using a slow language。

 but because I'm using rust。 I'm pretty confident that this will work pretty well。

 And I also have a command line tool here that's wrapped in front。

 So this is the part that goes through， gives me some information about the tool and then I have a buckets and I have an account size section here。

 That's it。 And then in order to call it and put it all together I do the command line put it into a parser here。

 And then I'm。On whatever it is that I'm doing。 And then you can see here that this does the whole command。

 So really pretty straightforward process here。 if you're running in cloud 9。

 because it already handled the security token for me because it has privileges to make those API calls。

 So all I'm going to do here is type in cargo run。And this will compile the project and get us started。

And because I'm using a very powerful cloud9 instance， the compilation will go very quickly as well。

 and that's one thing that's probably approach it is why not use a nice powerful instance in Cloud 9 because rust。

 the compiler can take advantage of multiple cores and when it's compiling the code。

 it's a great way to speed things up。So here we go。

 we're now putting the AWS SDK for S3 together in the project， and once that's complete。

 I should be able to test out this tool。Al right， looks like it's going to the final process of creating a bin here executable。

 And there we go。 So I'm going to go ahead and do dash， dash help。To invoke it。

 And you can see here that this particular command has buckets and account size， right。

 So let's go ahead and try the first one out here。 Let's do AWS。 and we'll just call this。Buckets。

 dash help。 And how does that work。 So it looks like you just do buckets。

And we can go ahead and run this there we go。 We've got a list of all the buckets in my account。

 And now if I want to go back to the help， we can look at the other one。

 which is the one that's going to total every single object in every single bucket in my account again。

 a little bit scary if you're using a solar language。

 but because we have this powerful rust ecosystem with acing calls and it's tuned with AWS pretty confident it's going to go very。

 very fast。 Look at that。 It's amazing that was able to figure out that there's 114 gigs in my AWS account here。

 So really in a nutshell the AWS rust SDK is an emerging tool for people that are doing data engineering。

 And this is a great way to get started。😊。

![](img/2e0ea2c22042911ff0f24fcba0949722_4.png)
# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p84 84_04_02_构建并部署Polars Rust AWS Lambda.zh_en -BV1Hy411q7Zm_p84-

![](img/0e52b81a1ad6e30e5430f90d750f2513_0.png)

Okay。Here we have an AWS Lambda that is going to be invoked via cargo Lambda。

 and I'm going to integrate the Pols data frame library。

 a high performance data frame library alongside AWS Lambda， which is a great combo。 Okay。

 let's go ahead and dive right in here。 We're going to go into a project called Pollar's Lambda。

 Let's go ahead and walk through the basic structure。 actually。

 a great way to walk through the structure is to run tree。😊。



![](img/0e52b81a1ad6e30e5430f90d750f2513_2.png)

Dash I target。 What this does is it eliminates artifacts and just shows me the rust code。There we go。

 So we see there's a cargo file， make file and a couple of rust files inside of source。

 So not a lot of code， let's go ahead and look at each of these。

 So first up here inside of the cargo do2l file。 What do we got。

 We have the deialilization serialization libraries， we also have Pols， and we also have Tokyo。

 which allows us to do a syncnc。The reason I get a lot of this is including the Lambda runtime is I'm using the cargo Lambda tool。

 and if we go ahead and look at that。You can see some of the things that you can do with it。

 So typically what I would do is I would run cargo Lambda watch to interactively play around with it。

 just like many other common web frameworks。 And then when I want to invoke it。

 I just say make invoke and this runs cargo Lambda invoke and we pass in a key value pair And then when I want to build and deploy pretty simple as well。

 we can just do the build and deploy， in fact， I can target arm 64 because I love saving money and then finally when it's deployed。

 there we go， I can invoke it。 So really the whole feedback loop is handled by cargo Lambda。

 so let's go ahead and dive into the code here next， underlib。

 let's take a look at what I'm doing here。 So I'm filtering， I'm grouping， I'm aggregating。

 So really kind of simple things that you would normally do with a data frame and I'm using the Iis data。

 Now one trick that I did that may be appropriate for demos or kind of small projects is I actually hard coded the iris data into my rust file。

Now if there's a big file， it's easy to put it into S3。

 but in this case it would be kind of fun to just put it in there so that I don't have to do that much work and then I have some calculation code here so how do I calculate the CSV file here I just use cursor which is from the standard library and then I treat it like a file and then I do all of my aggregations and sums and things like that and return back the data frame now to use that inside of the lambda all I need to do is go ahead and say polars Lada。

 which is the name of the project calculate so import that and then I use the Lada runtime and I use the serialization deilization now take a look here what I did is for the request I'm assuming someone's going to pass in a filter and if we go back to this code here notice that I do a filter here so this could be anything really depends on what kind of operations you want to do with polars but in this case I'm going to build an。

I filter and then again， if I go back here， I can use that for the request that goes into the lambda Now the response is just gonna be a payload and I do something kind of trivial in that I just take the whole data frame response and I turn into a string I mean probably not appropriate for any scenarios other than a demo but for now just to make things simple and the code simple I'm going to do it that way So first up here I have my async function that takes in the request and this request then gets put into a payload which I filter and that's the value earlier。

And now I go through and I pass that into the data frame， which again， remember it accepts one value。

 Then I just simply pass in the response here into the response object and then return that back and this will automatically convert it to Jason。

 All they have to do now。Is take the async main here， which is done from Tokyo。

 and I add some Tracing and et cetera。 and I run it。 So pretty simple， actually。

 to get this thing running。 So let's go ahead and test it out。

 What I would recommend when you're using cargo Lambda is to split the screen here。

 let's go ahead and do that。 So I'll type in make watch。 get it cooking。

 Then all I need to do is go ahead and say， make andvoke。And this will actually just test it out。

 And what it's going to do is it's going to compile it if it needs to compile。

 in this case it's already compiled， I don't have to do anything。 There we go。

 We see the results of that actually API call so。Really， there's not much more to do now。

 All I need to do now that I've tested it locally is I can actually kill this terminal。

Stop this and then go back to my make file， which does all the heavy lifting for me。

 So I can just say make build and and make deploy。 Let's go ahead and do it。 So I'll say make build。

And make deploy。 So it's kind of ridiculous how simple it is to deploy a lambda rust function。

 you can see it's trivial。 And now in order to test it out， I just run AWS invoke here。

 which is going to say cargo Lambda invoke remote。 So it's going to call into the AWS ecosystem and pass this value in。

 So let's type in make AWS invoke。Perfect， so trivial to make millisecond type responses to Lambda。

 This code runs extremely fast on AWs Lambda。 I think it took under two milliseconds to run this data frame operation。

 So I think this is a great showcase of why you should consider using cargo Lambda and rust and polars altogether。

😊。

![](img/0e52b81a1ad6e30e5430f90d750f2513_4.png)
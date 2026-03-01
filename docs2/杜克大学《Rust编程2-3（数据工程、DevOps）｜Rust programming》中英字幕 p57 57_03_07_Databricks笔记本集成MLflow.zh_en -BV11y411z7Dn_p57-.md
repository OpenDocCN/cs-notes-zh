# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p57 57_03_07_Databricks笔记本集成MLflow.zh_en -BV11y411z7Dn_p57-

Let's talk about getting started with ML flow and ML flow tracking To start with。

 we need to dive into what is Databricks machine learning。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_1.png)

Well， Data B's machine learning is a complete solution or a platform that allows you to train models。

 track your training runs。Create feature tables and share models。

 You can see a diagram here from the official documentation where the data prep is in this data sources and Dlta tables phase。

 It then goes into creating polished features that get put into the feature store。

 which makes it easier to do things like Automl work with those models and features inside of notebooks and then perform multiple experiments like automated hyperparameter tuning jobs。

 Once you've gone through and selected the right model。

 you can then deploy it in a batch based mode or an online serving mode。

 So it's really this comprehensive solution from data to production。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_3.png)

Now let's talk about ingesting tables。 There are a bunch of different ways that you can adjust tables。

 one of the ways is you can just upload a file that's an easy way to get started。

 you can also use the DBFS or the Databrick file system One of the unique things about the Azure integration is that you can also hook into Azure storage like the Azure blob storage system or you can also hook into a third-party integration and use those thirdpart tools。

 there's many different thirdpart integrations。

![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_5.png)

![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_6.png)

Let's go ahead and talk about this concept of a quick start ML。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_8.png)

Really to get started， the first thing you would do is create， let's say。

 a one to two node ML worker cluster。 So if you're in the machine learning tab inside of Databricks and you go ahead and you select cluster。

 One of the things you'll want to do is make sure that the Databricks runtime version is using an ML version。

 There is a standard runtime and there's the ML runtime。 the ML runtime includes ML flow。

 and it allows you to integrate with the rest of the experiment tracking and things that you would expect from a machine learning workflow。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_10.png)

One of the things that you'll want to do after that is attach a notebook。

 If you go through and you import， let's say， the ML Quickstar notebook。

 which is included in the default console， and you right click attached to it。

 you can then get started on working on that notebook。 And really。

 that's probably the best way to get started， Cri a cluster go through。 and then once a clusters up。

 go through the Quickstar model training notebook。Now。

 if you've gone through and trained a classification model。

 one of the things you'll see is this concept of a bunch of different experiments and you can select which of the hyperparameters or which of the models you want to select to deploy to production。

Inside of the experiments UI is really the heart and soul of a lot of the model tracking because it allows you to go from the notebook directly to an experiments tab and actually take a look at what it is you actually did。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_12.png)

When you go into the experiments tab here， one of the powerful things about it is that you can actually go through writing your sidebar and toggle through and look at the different experiments and look at the model that was created。

 including the accuracy using the metrics that show up in those experiments tab。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_14.png)

Now， let's go ahead and dive into hyperparameter tuning。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_16.png)

How would we actually get that working with Databricks to start with one of the things you can do is you can have many different experiments with one API call。

 and that's the power of the experiments tracking interface and really this is something you'll see in many different tools you want everything in one interface so you can actually query through。

 look at the different experiments you've run and figure out what is the best metric for that experiment。

Now， if you go into a hyperparameter compare functionality。

 one of the other things you can do as well is do a scatter plot and take a look at the different runs and even dive into details like the learning rate versus the loss。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_18.png)

Also， it's important to know that you can do parallel hyperparameter tuning， which allows you to。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_20.png)

Really optimize how quickly you get to the in solution。

One of the ways you can do this is by using the hyper optt。

 which has distributed asynchronous hyperparameter optimization。

 and there's three different algorithms you can use。 There's random search。

 There's tree of Parison estimation or TpeE， and there's adaptive Tpa E。

 and you can parallellyze this with Apache Sp or Mongo Db。

 So really there's a lot of ways to get started with parallel hyperparameter tuning。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_22.png)

And if you take a look at the code here， you can see on smaller clusters or the Databricks Community edition。

 it's a good idea to do parallelism too， but if you have a big cluster。

 you can make it whatever number you'd like。

![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_24.png)

Now， if you go through and do a search run， what you can also do at the very end is look at the metric that you care about。

 maybe it's areay under the curve， you can say I want to see the last 10 results and then it'll go through and give you the best run for that particular search query that you did and you can do it all in code。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_26.png)

Finally， when you're done comparing the runs， you can look at them all inside of UI here and then expand and compare depending on what it is you want to do with those hyperparameters and experiments。



![](img/e0b206d3a8d1f5c98d6fc5e6d66a17a9_28.png)
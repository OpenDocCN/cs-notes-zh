# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 -BV11y411z7Dn_p69-

![](img/649d5215dbb6526b833f45177c2e502a_0.png)

Let's take a look at the common data engineering tools that are used in industry with a focus on open source here。

 to start off with we have the Hadoop Spark Hve ecosystem。

 and first let's look at some of the pros here of these particular tools here， scalability。

 you can use these to handle large data， also flexibility。

 you can process a wide variety of data types and structures。

 including semistructured or unstructured data。Cost effectiveness。

 you can use commodity hardware and also integration。

 so you can use things like SQL to get things done in terms of the cons here。

 there is a little bit of complexity that you have to deal with。

 That's one of the issues with these tools， latency as well as another issue here。

In terms of not knowing how to deal with realtime processing data。

 this is something that you have to actually work around and then resource management。

 it can be very difficult to get everything working exactly the way you want it and then maintenance if you're dealing with these systems they require a lot of handholding and maintenance and the ability to make them run at a scale that you actually are able to keep it in operations Now in terms of beam here as well one of the things that's important about the pros is that it is a unified model right so what this means is that you can use pipeline for bad streaming and also combine a different workloads。

 it's also portable so you can use it on lots of different runtime like Flink or Google Cloud dataflow or Sp etc and also have support for multiple languages meaning that。

You can use go， Python， Java， etc now in terms of complexity though。

 this is one of the downsides of beam also limited adoption， there's not as widely used runners。

 for example， with beam and then the performance can also be an issue because it's not as optimized as a dedicated batch or stream processing system for certain use cases。

Now what else do we have here， we also have airflow。

 which is also a very common tool that we can learn about and in terms of airflow。

One of the things that you can be aware of is that they have workflow management in terms of a pro。

 it's got powerful tools for defining and executing and monitoring complex data pipelines。

 scalability as well， so it has great scalability characteristics and then in terms of the community and ecosystem there's a ton of things around the airflow ecosystem。

 but the cons would be that the learning curve is very steep for this particular system。

 that deployment and maintenance can also be an issue in terms of a distributed environment and then the UI may not actually be exactly what you're looking for in terms of a managed workflow orchestration。

So next up here we can also talk about the pros and cons of both Kafka and RaitMQ and in particular here a few of the things that we can care about would be that in terms of highput。

 scalability， fault tolerance， they have the ability to really handle tremendous amounts of data。

 these are some of the strengths with these particular systems for real-time message exchange in terms of the cons though。

 maybe one of the things that could be an issue is the message handling right。

 you know can you actually figure out how to process orders efficiently and in particular delivery systems you could have some issues there with things being out of order and also delayed message handling as well could be an issue and then as usual resource management could also。

Be a con to be aware of Now， what else do we have here， We also have Cassandra。

And one of the things that's important about Cassandra as a pro is that it is actually very scalable right so it's designed to do distributed NosQL in terms of the flexibility data structure as well。

 we can see that it has the ability to do semistructure data， structured data， etc。

But also in terms of the cons is's extremely complex to use and also if you have a right heavy workload that's great。

 but if you don't then you could run into issues with let's say a read heavy workload and this could be something that could be a problem and also the lack of aggregation could also be an issue for this so you know just again in terms of looking at the pros and cons of these approaches。

 it's important to know that there is no one perfect solution for everything you're doing with data engineering。

 although these are very common tools that you will see in industry。



![](img/649d5215dbb6526b833f45177c2e502a_2.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p70 70_04_04_数据工程管道核心组件.zh_en -BV11y411z7Dn_p70-

![](img/e598088fca7673f9bd1777f23c1c69b0_0.png)

Here we have a data engineering pipelines diagram where I've been able to whittle things down to really three different components of a data engineering pipeline。

 First up we have data ingestion， second up data processing， third data storage。

 so these are really the uniform aspects of a data engineering pipeline that are always present。



![](img/e598088fca7673f9bd1777f23c1c69b0_2.png)

The orange items here， resilience， scalability monitoring。

 these are components that are really persistent and that they're going to be a part of any data engineering pipeline that goes into production。

 So let's go ahead and talk through each of these components。 So first up， in terms of the ingestion。

 This is the most important part of a data pipeline。 really。

 it's can I get anything to work And the data can come from multiple sources。

 It could be a data a data lake or even realtime data streams。

 And it's going to be able to process that data from a collection standpoint。Next up。

 we have processing， and this is about transforming the data into a more usable form。

This could be cleaning or validating or formatting the data。

 And it makes sure that you can actually build aggregation， summars， et cetera。

 So this is where we see a lot of。Tools like Sp， for example。

 that can go through and do processing and other E TL type operations。

 Now in terms of the final step here， which is the data storage and output。

This is where the pipeline would facilitate storing the process data in a suitable manner for further analysis so it could be。

 for example， a data warehouse or it could be a dashboard， etc ce。

 This is the final endpoint Now along the way though we have these other components here and so scalability is something that's really critical because in terms of building something that's able to run in production you have to be able to run it at a vertical or horizontal scalability and this means that you can add nodes to it or increase the size of the system。

And then in terms of the resilience here， this means that they're able to run。

 even if there's an error。 So， for example， if it's an event that triggers it and there's some problem with the event。

 it could still alert you and tell you what the issue is or it could maybe have different nodes that are running and some of the system can run even though one of the nodes has actually failed also in terms of monitoring and maintenance here。

 we have the ability to look at the data flow， look at the system performance。

 maybe send out and alert when there's some kind of an issue with the pipeline。

 So really holistically， when you're thinking about data engineering pipelines。

 these are going to be the key components， step 1 data instion， step 2 data processing， step 3。

 data storage and then these these really these inherent principles。

 resilience scalability of monitoring are always present。

 not only just in data engineering pipelines， but also in。Production software engineering systems。



![](img/e598088fca7673f9bd1777f23c1c69b0_4.png)
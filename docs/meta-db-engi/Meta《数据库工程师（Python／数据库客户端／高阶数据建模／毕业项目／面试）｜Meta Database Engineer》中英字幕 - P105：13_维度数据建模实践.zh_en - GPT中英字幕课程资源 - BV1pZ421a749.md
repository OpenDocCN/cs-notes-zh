# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P105：13_维度数据建模实践.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

At this stage of the course you should be familiar with the dimensional data model and many of the key concepts related to it。

 but how do you build a dimensional data model， the process for building a dimensional data model revolves around four key steps known as Kimball's dimensional data modeling。

In this video， you'll explore the approach and review each of these four steps in detail Let's begin with a look at global superstore and their use of the dimensional data model。



![](img/041690abe38a55de7ef37b81ebb495de_1.png)

Global superstore wants to perform data analytics to understand their recent sales figures。

 This requires building a dimensional data model that will help them understand their business and the factors that impact on their sales and profits。

 before you explore global superstore's process， let's quickly recap the purpose of a dimensional data model and take a high level look at the four key steps。

 A dimensional data model must focus on particular aspects of a business or organization in order to address specific problems。



![](img/041690abe38a55de7ef37b81ebb495de_3.png)

![](img/041690abe38a55de7ef37b81ebb495de_4.png)

![](img/041690abe38a55de7ef37b81ebb495de_5.png)

![](img/041690abe38a55de7ef37b81ebb495de_6.png)

The model is created using a systematic approach that revolves around four key steps。

 These steps include。The business processes， the grain， the dimensions and the facts。

 Each of these steps is a choice。 You need to choose a business process that your dimensional model must investigate。

 You then need to choose the facts and dimensions that can provide the answers you need。



![](img/041690abe38a55de7ef37b81ebb495de_8.png)

![](img/041690abe38a55de7ef37b81ebb495de_9.png)

![](img/041690abe38a55de7ef37b81ebb495de_10.png)

Let's work through each of these four steps or choices and understand how they contribute to the process of building a dimensional data model。

When building a dimensional data model， the first step is to identify or choose the specific business process to be addressed。

Once you've identified the process， you can then determine the grain of data in the data model。



![](img/041690abe38a55de7ef37b81ebb495de_12.png)

Global superstore have decided that the business process to be addressed is their sales activity。

 Once you've decided on the process， you then need to choose the level of detail required。

 This is referred to as the grain。 What granularity or level of detail is required for the data warehouse to address your process problem。



![](img/041690abe38a55de7ef37b81ebb495de_14.png)

![](img/041690abe38a55de7ef37b81ebb495de_15.png)

And what's the lowest level of detail required to address the issue？For example。

 global superstore need to analyze their sales data at both a yearly and daily level。

 they also need to investigate this data at the global and local level The next step in the process is to choose the dimensions In this step you need to choose the relevant dimensions In other words。

 in what context do you need to explore your business activity。 As you already know。

 global superstore need to analyze their sales data。

 and they need to analyze this data in the context of products， customers， time and locations。



![](img/041690abe38a55de7ef37b81ebb495de_17.png)

![](img/041690abe38a55de7ef37b81ebb495de_18.png)

![](img/041690abe38a55de7ef37b81ebb495de_19.png)

![](img/041690abe38a55de7ef37b81ebb495de_20.png)

![](img/041690abe38a55de7ef37b81ebb495de_21.png)

![](img/041690abe38a55de7ef37b81ebb495de_22.png)

So now that you've identified the business process， the grain and the dimensions。

 it's time to establish the facts， this is basically answering the question of what do you want to measure？



![](img/041690abe38a55de7ef37b81ebb495de_24.png)

You need to select the measures that contain numeric data and populate your fact table with these attributes。

 for example， global superstore need to explore their facts using the dimensions tables， location。

 product and time they can demonstrate how each of these dimensions impacts the sales。



![](img/041690abe38a55de7ef37b81ebb495de_26.png)

And they can also include relevant attributes that provide useful information about each dimension once you've decided what aspect of your business process you need to investigate and chosen the grain related facts and dimensions。

 you can then create your schema。

![](img/041690abe38a55de7ef37b81ebb495de_28.png)

![](img/041690abe38a55de7ef37b81ebb495de_29.png)

Arrange your dimensions and dimensions tables。Global superstore can arrange their dimensions and measures in a star schema。

 Their schema examines the performance of their sales activity in the context of four different dimensions。

 Custom， products， locations and time and within each dimension is a set of relevant attributes that target the required data Once you've decided what aspect of your business process you need to investigate and chosen the related data and dimensions。

 You can create your schema。 Global superstore have identified their dimensions and measures step by step based on their business requirements。

 They can now perform different forms of data analysis to achieve their goals。

 You should now be familiar with using a systematic approach to build a dimensional data model。

 and you should also be able to identify and explain each of the four steps in which you must make your decisions around data。



![](img/041690abe38a55de7ef37b81ebb495de_31.png)

![](img/041690abe38a55de7ef37b81ebb495de_32.png)

![](img/041690abe38a55de7ef37b81ebb495de_33.png)

![](img/041690abe38a55de7ef37b81ebb495de_34.png)

![](img/041690abe38a55de7ef37b81ebb495de_35.png)

You've made great progress on your advanced data modeling journey。


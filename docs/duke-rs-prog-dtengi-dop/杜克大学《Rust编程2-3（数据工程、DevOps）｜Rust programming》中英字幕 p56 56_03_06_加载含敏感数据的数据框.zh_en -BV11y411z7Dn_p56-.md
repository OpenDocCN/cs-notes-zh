# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p56 56_03_06_加载含敏感数据的数据框.zh_en -BV11y411z7Dn_p56-

![](img/335cf243c2e3added873a8e75b9df807_0.png)

Loaded data frame with sensitive information。There are a few things to pay attention to。



![](img/335cf243c2e3added873a8e75b9df807_2.png)

First， what is the data classification methodology used？

One of the most common ways to do this is to have different labels， for example。

 a sensitivity label that would apply to certain information。

 a retention label that would basically say how long this data should be around Also labeling it sensitive information in general。

 and then there's different types as well， such as trainable classifier。

 so could you actually go through and actually detect certain types of data and automatically protect it and classify it。



![](img/335cf243c2e3added873a8e75b9df807_4.png)

Once you have these controls set up， then you can go into different aspects like the storage type。

 the encryption， access controls， data destruction， data loss， logging， who's been accessing things。

 tracking where those resources have moved。

![](img/335cf243c2e3added873a8e75b9df807_6.png)

Finally， once you've done all that， you're ready to securely load your information from a data frame because it's been classified properly。

 The redacted information， either will be nulled out or it won't show up when the data frame is actually loaded。

 So this is really a key aspect of securely loading data frames is the back in work of classifying things。

 training things successfully。 And then there isn't upfront work that's necessary。😊。

When you're loading a data frame， it's already been done and preloaded。



![](img/335cf243c2e3added873a8e75b9df807_8.png)
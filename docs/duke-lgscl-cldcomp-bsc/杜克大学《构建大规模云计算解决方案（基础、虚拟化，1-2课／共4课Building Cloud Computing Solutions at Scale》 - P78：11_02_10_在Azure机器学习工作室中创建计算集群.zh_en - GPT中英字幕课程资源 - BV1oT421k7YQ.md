# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P78：11_02_10_在Azure机器学习工作室中创建计算集群.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's dive into the Azure compute options。If we look at this interface here。

 we have compute instances。 We have compute clusters， and we also have inference clusters。

 So what's the difference？ Well， the compute cluster here is where you would spin up something to provision a Jupyter notebook。

 we can go ahead and do that。 So if I go ahead and select new。And the options of selecting the name。

 let's just say this is a Jupiter demo。You can see here that I can select between a CPU or a GPU depending on what problem I'm solving。

 and I also can toggle between the different machine sizes。And additionally。

 I'm able to SSAT into it if I need to， so I'm going to go ahead and say create。

This usually takes a few minutes to create now let's also look at compute clusters。

 if we look at compute clusters， if I go through here， I can say new same thing I can say。

Compute cluster would be demo cluster 2。And as well， I can toggle between a GP or a CPU。

If I am going to be doing AutoML for example， and I'm going to be doing deep learning。

 then a GPU could really make sense for that particular workload。

 this is also important to be aware of is the virtual machine priority if I click on this you can see that dedicated means it's always there。

 but a lot of times for experiments I think the low priority is the way to go because it will actually lower the cost as well I can toggle between the sizes here。

And then I can select the minimum and maximum number of nodes。 Now。

 this is important to call out here is that。If you don't want to be paying something when you at night。

 for example， when you you don't have a job running。

 you should leave this at zero and then you can tell it to burst up to a certain number like let's say I want to burst up to four and then I can go through and create that So what's nice about this is that it will be idle until I need it and then when I provision it it'll be ready to go now let's take a look at the third type the third type is a Kubernetes scale inferenceferencing cluster type and if I go through here and I create this you can see that it uses Kubernetes to do inference or prediction at scale So when you're creating an inference cluster it's very similar to the other types compute instance compute cluster you would type in a name we'll call this cube cluster and we'll select a region as well central US same thing I can select different virtual machine types we can leave a default number of nodes here and I can go ahead and say create。

Finally， the last type of compute instance would be a specialized cluster。

 let's say you're using databricks， for example， which is a managed spark environment。

 I could hook that up into this attached cluster so in general there's compute instance which is for Jupyter notebooks。

 there's compute clusters which is for bursting and doing training and then there's inference clusters which is an optimal environment for doing predictions at scale not using hosted Kubernetes。



![](img/8bb3939d970e530dd480ae24548b0bec_1.png)

![](img/8bb3939d970e530dd480ae24548b0bec_2.png)
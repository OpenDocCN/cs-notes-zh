# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P72：05_01_02_课程二项目概述.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/8de687e27b86793602b8d29e3f18adc5_0.png)

Let's walk through the project that you'll build as the final project in this course。

 What you'll do is create a containerized flask microservice and deploy it。



![](img/8de687e27b86793602b8d29e3f18adc5_2.png)

In a managed container service。 So these are some big buzzwords。 And let me break each of these down。

 So first， a container is a distinct unit of work that is typically a Docker format style container that contains all of the runtime as well as the source code necessary to deploy。

 So really， it's the runtime。And it's the source code。

 That's really the big key difference with a container versus a regular application。

 And in terms of a microservice， we'll get into those details later。

 but really it's a single purpose application。 So it does one thing and does it really well。

 Like let's say a small kitchen knife or a blender， right， they do one thing and they do it well。

 Also， this managed container service， there are several different options in the cloud。

 Every major cloud provider has a managed service offering。

 a few of the examples that I'll talk about， one of them is called cloud run。

And Cloud Run is a fully managed container service on the GCP platform where you can effectively give it a Docker format file。

 check it into a container registry So a place where you put these containers and then it'll turn it into a web service for you so there are lots of these really highlevel managed container services there's another one on the AWS platform called EKS on AWS and that's a way of managing a container in a Kubernetes environment so there are lots of interesting ways that you can deploy this container and you'll have the flexibility to choose which of the managed service offerings work best for your workflow。



![](img/8de687e27b86793602b8d29e3f18adc5_4.png)
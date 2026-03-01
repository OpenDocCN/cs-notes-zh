# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P93：26_02_05_Kubernetes Pod与Node.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/da0dafd38ee0236bcdae4bb01a82667b_0.png)

Kubernetes pods and nodes are important concepts。 You can see in this diagram that the node can contain multiple pods。

 and we know that nodes can run on a virtual machine， they can run in a data center。

 they can run in a cloud but inside of this node you could have many different pods which in turn could have many different containerized applications volumes IP addresses and it's typical to have multiple pods inside of one node a few things to consider here is that a pod is an applicationspec logical host and it can contain different application containers that are very tightly coupled。

 for example， a frontend and a backend could be included in this particular configuration a few other things to consider is that a pod will always run on a node and that node worker machine in Kubernetes。

Can either be a physical machine or it could be a virtual machine depending on what kind of cluster you've configured。



![](img/da0dafd38ee0236bcdae4bb01a82667b_2.png)
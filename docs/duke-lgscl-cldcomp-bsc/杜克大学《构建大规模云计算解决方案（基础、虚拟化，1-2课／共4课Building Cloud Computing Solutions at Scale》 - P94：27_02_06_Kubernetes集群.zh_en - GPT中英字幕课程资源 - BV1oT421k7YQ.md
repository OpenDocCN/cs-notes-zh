# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P94：27_02_06_Kubernetes集群.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/db52e8e34fadf96324240b9195bbc457_0.png)

And。Kubernetes， cluster architecture。A Kubernetes cluster contains a couple different types of resources。

 First， there's the control plane that coordinates the entire cluster。

 And this is the purple dot right here。And the nodes are the workers that run inside。

 so you've got several workers inside and they're communicating via this' Kubernetes API。

You can see here that the nodes are all basically inside of this control plane controlled in a cluster diagram。

 and they're processing different types of work， depending on what kind of Kubernetes architecture that you're building a node can also run on a physical computer it could run on a virtual machine it could run in a cluster。

 so it's important to know that this cluster is a conceptual cluster but the physical nodes could be living in multiple different types of locations。



![](img/db52e8e34fadf96324240b9195bbc457_2.png)
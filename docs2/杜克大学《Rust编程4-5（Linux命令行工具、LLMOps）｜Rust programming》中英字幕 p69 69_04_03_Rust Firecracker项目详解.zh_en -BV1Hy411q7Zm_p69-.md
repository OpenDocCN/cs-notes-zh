# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p69 69_04_03_Rust Firecracker项目详解.zh_en -BV1Hy411q7Zm_p69-

![](img/941a3c4287c34bcea6eee0c0a550eb90_0.png)

Yeah。Here we have firecracker， which is a virtual machine that is specialized for running multitenant container and functionbased services and also optimizing performance and security and this is actually building rust and rust is an excellent choice for this kind of a problem because of its safety and performance characteristics。

 the architecture is microvms here， and this means that their lightweight， their faststar nature。

 and it makes firecracker suitable for serverless。 So this is really the engine that powers AWs Lada and there's minimal overhead because only the essentials are included and as well in terms of security。

 rust safety features help minimize the risk and also reduce the surface area that is attackable some other things to include here about firecracker are that it can launch thousands of microvms at a fraction of a second enabling the rapid。

Scaling of applications。 there's low memory head as well。

 and it has integration with container runtimes。 And this is why it works well with things like AWS Fargate and Kubernetes and other types of containers。

 So this is really the engine that's being powered underneath the hood of Lambda and Fargate and it's also an open source project。

 So a few different takeaways here are that you know really in terms of a showcase for the power of rust。

 it's hard to find a more successful open source project。

 and it kind of goes to show you if you want to do computation at scale that's extremely lightweight。

 something like rust is really your best bet。 And that's why in the domain of data engineering and MLOs and cloud computing really rust in a sense。

 is a secret weapon because of how efficient it is at building secure yeah performance code。



![](img/941a3c4287c34bcea6eee0c0a550eb90_2.png)
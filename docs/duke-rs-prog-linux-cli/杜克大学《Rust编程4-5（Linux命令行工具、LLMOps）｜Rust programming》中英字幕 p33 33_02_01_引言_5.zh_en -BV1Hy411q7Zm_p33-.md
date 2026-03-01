# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p33 33_02_01_引言_5.zh_en -BV1Hy411q7Zm_p33-

Packaging and distributing your tool is essential once you are ready。

 you've built something that is useful that is automating some task and it's allowing you to be more efficient。



![](img/320791f83101b0744a52f7d5fdbd7ed0_1.png)

Well you might want to distribute that like it might be a situation where you want to share with other folks in your team or other teams。

 or perhaps you want to install these tool in some systems。

 it could be some continuous integration system or some other servers that might benefit from these automation that you built from the ground up Now the first step is to understand a little bit how packaging works in both either Python or rust the packaging will be slightly different。

 but they accomplish the same goal， which is how can we put all of these things together。

 especially if we're dealing with。Depenencies， if we're relying on on perhaps a framework or some other library that is helping us helping our command tool to achieve some objective some goal and allowing us to automate some tasks。

 how can we put all of those things together if you're no longer building a simple scrape like say for example in Python where you can actually use a single file and distribute that and copying that file everywhere。

How can you ensure that all of the dependencies and everything is put together in a single package that can be distributed and shared across either team members or other systems that might benefit from that so the first step is packaging and we're gonna to see how we can put all of that together with packaging and then the next step from there is to try to make an actual release and how can you make a release and how you can put it in a registry or in a place in a package index in the case of Python where you can not only put it there。

 but allows other tools to install from there as well for in the case of rust is create StaIo and all of these indexes or registries will allow you to more easily share your package that you've been able to properly put together using the proper packaging tools that will go and see next。


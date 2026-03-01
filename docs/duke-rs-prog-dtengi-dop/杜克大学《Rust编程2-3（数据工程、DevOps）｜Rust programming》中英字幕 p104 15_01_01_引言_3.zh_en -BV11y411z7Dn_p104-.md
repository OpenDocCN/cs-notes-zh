# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p104 15_01_01_引言_3.zh_en -BV11y411z7Dn_p104-

Understanding containerization and containers and the runtime and everything that revolves around Docker and container images is very important。

 All cloud providers have immense flexibility for containers and for good reason because they lightweightway theyre fast is easier to scale as compared to regular servers and definitely compared to virtual machines as well now virtual machines have their own place in in production with different types of services and different types of workloads。

 but containers are crucial and they're so crucial in fact that I think it is one of the core pieces for the foundational knowledge on applying Dev principles and we'll see what are some of those concepts that you will need to understand for containerization as you move forward and we'll see how that applies to applications in general but also specific to rust as well when we'll want to see how we can put together a rust application。



![](img/5514a9b7b392e3a5330df7046fb75028_1.png)

And what are some of the considerations and now is where you will start seeing some of the core differences between rust and some other languages。

 you'll see the possibility of creating a container， a rust container that has minimal weight。

 less than 100 megabytes， in fact even less than 50 megabytes total in total storage you will be able to deploy you can actually get that container and employee to the cloud。

 and what that translates into well it translates into savings。

 it translates into much faster rollouts easier to develop faster to collaborate and while you're pushing and pulling those images back and forth。

 everything is faster。And everything's cheaper， why wouldn't you want to use something like that and we'll see how that works。

 but also covering some of the general or the generic concepts of container extension that are so crucial in basically everything that we do with technology these days。


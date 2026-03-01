# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p99 11_01_03_审计网络安全.zh_en -BV1Hy411q7Zm_p99-

![](img/3cd2965ee6d2b33033014ddb85e7d606_0.png)

One critical thing to figure out in your organization is how to audit the network traffic that's happening are there malicious attacks are there internal behaviors that are miscongured so one of the ways you can do this is by using something called VPC flow logs you can log and view the network traffic and so this allows you to collect store analyze network flow logs and then troubleshoot things including security issues and make sure that the network is acting as expected up until now you would have to do this with for example an agent on AWS but now you can use VPC flow logs so let's go ahead and take a look at that in this example here I go to my VPC I go ahead and I create a VPC flow log it in turn shows all the different connections in my network and I can watch in realtime as I'm streaming connectivity and I can see if things are rejected or accepted and then this is a。



![](img/3cd2965ee6d2b33033014ddb85e7d606_2.png)

Good interface for me to then later create alerts with， for example。

 CloudWatch or third party systems。

![](img/3cd2965ee6d2b33033014ddb85e7d606_4.png)
# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p95 07_01_08_改善方法论.zh_en -BV1Hy411q7Zm_p95-

![](img/4a397f5cef31f1306131a6664fc74af6_0.png)

Plan， do check and act。It's a implementation of the scientific method。

 but applied to a manufacturing or software engineering context。 First， in the planning phase。

 you need to identify the problem。 So we need to build an automation tool that looks at inventory。

Next， you go ahead and try that solution out。Once you've done the initial prototype。

 you want to check to make sure it actually accomplishes the business goal， right。

 So if you had some automation around inventory， it should have an accurate count of inventory So you'd go through and analyze the results。

If， in fact， it does work， then you would act by putting this into a production component of your facility。

 If it doesn't work， you would need to go through。Go back again to the planning phase。

 identify what the problems are， and then go back and repeat this process。

 So really the plan do check act is an iterative process that constantly improves things。

 And this is a key component of the Kaszen methodology。

This is an example from my career in a real scenario that was very serious。

 We had servers that were randomly crashing。 And so the first question is， why do they crash。

The answer is not sure there are no log files so we can't investigate why there's a crash。

 The next question to ask is， why are there no log files。Once that question had been posed。

 we were able to discover that the systems were using ephemeral storage。

 which is a storage that will go away if it reboots。 And there was no swap partition。

 This is the partition that's used when memory is basically consumed on a machine。

And so then the next question we had was， why are there systems that are using ephemeral storage without swap？

Next， the question was resolved with the answer of Devops specialist used to work at a top tech company。

 and they said they don't use swap there。And the second answer was that ephemeral storage is cheaper。

So then the natural follow up is what would happen if we enable swap and then use EBS storage？

EB S storage is block storage that is persistent across reboots。The final root cause analysis was。

That we were able to show that there was a kernel panic and an out of memory error in the crash logs。

 This is the last step here to debug the problem。And then we asked the question。

 what is causing that error。 And now we can see that the root causes that the Java application server configuration file allocates more memory than the machine has available。

 So it was causing an issue where the application software itself consumed all the memory and because there is no swap to right to。

Then the kernel itself would have to actually come into play and this is where part B says the Java kernel consume since Java consumes all the memory。

 the Linux kernel kills the Java process， finally a supervisor。

 which is managing processes and restarting them automatically then created a race condition that crashed the machines。

 so by asking these five questions， it was a very， very difficult problem to solve。

 but it did get us to the root cause and not every problem can be solved by fiveY's。

 but many problems can be solved by five y's， and this is really the principle of the heart of Kaiszen。

 which is go to the root cause and continuously find out what that cause is and fix it。



![](img/4a397f5cef31f1306131a6664fc74af6_2.png)
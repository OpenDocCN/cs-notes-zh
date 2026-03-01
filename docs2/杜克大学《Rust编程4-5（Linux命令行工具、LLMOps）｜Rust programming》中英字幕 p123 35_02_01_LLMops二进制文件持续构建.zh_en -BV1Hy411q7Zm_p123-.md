# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p123 35_02_01_LLMops二进制文件持续构建.zh_en -BV1Hy411q7Zm_p123-

![](img/c971797747550e5a974e963548644971_0.png)

Continuous build is a very good concept to dive into for LLm ops because you need to figure out how to have a binary that's going target the right architecture and also how to create an artifact that you can use later So first up here we have a source repo and this could be where your framework lives and maybe it's a framework like rust candle and as you're making changes to it。

 it would trigger the build system。 Now in the case of LLm ops。

 where would you actually take this build system towards well first what you would do is you would trigger a cloud host because the cloud hosts would have a GPU that could have the correct drivers installed for example。

 the couda drivers and this would be a build host that would be remotely connected to the build system the build system could be a system like Github actions or it could be let's say AWS code build or some other cloudbased build system it really doesn't matter but。

Once you go through and you compile the software for that particular GPU architecture。

 you would then register that binary artifact。 So really this is a necessary step because you're going to need to target a particular hardware architecture Next step when you're ready to use this registered binary。

 What you would do is pull down that artifact and put it onto a GPU host at that point。

 you're ready to go。 What you could do is build， let's say， a chat loop or build maybe a endpoint。

 whatever it is you're going to do with that particular binary。

 but it's ready to go for you to actually utilize it。

 So this is a very different way to think about what's happening。

With LLMOs is that you really need to have the right hardware， you want to have automation set up。

 and you also want to have the ability to easily pull the built binary that targets a particular GPU type so that you can use it and let's say your own chat loop。



![](img/c971797747550e5a974e963548644971_2.png)
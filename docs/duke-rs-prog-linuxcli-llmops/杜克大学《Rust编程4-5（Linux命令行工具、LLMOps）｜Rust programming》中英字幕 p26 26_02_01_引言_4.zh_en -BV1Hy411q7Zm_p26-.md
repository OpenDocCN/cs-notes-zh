# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p26 26_02_01_引言_4.zh_en -BV1Hy411q7Zm_p26-

![](img/70ca34ba562945dabb67537b658df4db_0.png)

Let's go through all of the basics， all of the fundamentals that you will need in order to build command line tools in both Python and rust。

 we'll see how we can add options and flags， perhaps even some boolean flags that are turning on or off certain behavior and we'll see how we can integrate those into the tools that we are going to be building then we'll move on to slightly more complex handling of arguments and flags。

 but we'll add subcommand， subcoms is a nice way of separating the concerns se the work that these tools are going to be doing and it will allow you to have a cleaner separation when you're writing the code on what are the responsibilities and what are the actions that you want to take in each of these segments and then we will add a little bit of extra flexibility by。

Taking a look at environment variables， we will be able to modify these command line tools that we're going to be working with so that they can accept options and flags well not flags but values so that we can alter。

 we can tweak the behavior of the command line tools by reading these environment variables that are going to be specific to the task that we're going to be working with all of these will give you great flexibility in order to choose to pick and choose exactly what is the best strategy for the command line tools that you want to build as you move forward。


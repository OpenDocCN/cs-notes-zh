# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p133 44_03_01_引言_8.zh_en -BV11y411z7Dn_p133-

![](img/04f4d8dab74c473c27dd1821b8f1be17_0.png)

Although you can use rust and many other programming languages directly to perform tasks。

 like say for example， send a network request an HTTP request or connect to an external API。

 sometimes we don't have an option other than wrap around an existing tool and these are called like these existing tools could be external programs like Uni or Linux utilities。

 command line utilities， CLs that are performing a very specific tasks that it would be either hard or very cumbersome to do within not only in rust but any programming language really。

 so I want to show you explore some strategy， some techniques that you can apply when you have when your objective is to actually wrap around an external tool not only just wrapping up。

And calling now to that external tool， but also trying to consume the output from that external tool what are some of the considerations。

 what are some of the potential pitfalls that you may find when you go down that road I done these many different times and of course I want to show you what are some of the things that you should look out for but also try to try to focus on so at the end of the day you have a reliable tool it could be a library or a command tool that wraps a system utility that you can rely on and and implement and use everywhere where you have such an need。


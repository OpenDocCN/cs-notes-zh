# IBM网络安全分析师专业证书课程4：《网络安全与数据库漏洞》｜network-security-database-vulnerabilities｜ - P54：53_OS命令注入 第2部分.zh - GPT中英字幕课程资源 - BV1RN411q7PY

![](img/d368de23353deb603b5a8ddd1313caab_0.png)

Yes。In this video， you will learn to describe additional OS command injection attacks。

Explain why commands should not be run through the shell interpreters。

Explain why it is important to use explicit paths when running executables。



![](img/d368de23353deb603b5a8ddd1313caab_2.png)

The next recommendation is to not run commands through She interpreters。

 you may be familiar with She interpreters like SH Bsh， that's on UniX。

 CMD and PowerShell on Windows。When you supply your command。

 let's say your business logic requires you to run NOS command so you have no choice you have to do it。

😡，If you run it and supply it as a。Pameter to the shell interpreter then that also gives attacker extra power because for example。

 they could chain command they could as the syntax I showed earlier with the semiconlon you could chain a number of commands in there and attacker could download malicious code could delete files could create web shells do all kinds of damage but if you run the command directly without passing into the shell interpreter then a whole set of shell syntax such as semicolon pipe andpers back quote dollar sign all that syntax that's introduced and understood by the shell interpreter is no longer valid because you are just running a single command in this case remove command and you're passing in a file to remove so this command that you see here the second command on the slide will actually fail it will not work because the semicolon will have no meaning to the RM command note that even。

If you do that， there is still danger of doing additional damage。

 you could not only manipulate the single parameter。

 but you could add additional parameters to a command that you're running so here in this example we're running an endmap application to scan a particular IP address however。

 if attacker has control of the input they could specify additional endmap parameters and in this particular case it would cause endmap to write a log file to a particular file that you specify however if it's running as a root command there's a possibility that this would actually overwrite an importance the library so bad things still could happen is just the attack surface is reduced you're no longer dealing with a full set of syntax that shell interpreter supports but rather concentrate on a single command。

Also something to keep in mind is that another example that we often see is that you may execute a single command particular。

 let's say a shell script， but inside that shell script there could be something in those commands that could trigger OS command execution on the parameters that are passed in so even though you're running something directly。

 not involving shell interpreter，There's still a chance that something could happen inside the script that you need to watch out for。

 and you have to scrutinize how you operate on the input that user supplies so that a malicious command is not executed inverly。



![](img/d368de23353deb603b5a8ddd1313caab_4.png)

The next recommendation is to use explicit paths and applications are found by the operating system and executed based on system path settings and there is a type of attack where if there is a folder on the system that's ridriable to a general user and have multiple users using the machine and that folder also。

Exist referenced in the path before the folder containing the executable you're trying to run。

What the attacker could do is if they have a low privilege account on the system。

 they could log in and they could drop a malicious version of the application in this case。

 in EndMap in the folder that's under their control and that appears in the path before the regularular folder where endMap lives。

And when we execute command without the full path， just say endmap and then the IP address。

 that malicious executable will be run instead of the one that we intended。

 so to protect against that it's best to reference all the executables that you run by their full path that way there is no ambiguity and the right executable will be loaded and by the way。

 the same recommendation applies to another type of attack called DL Hajikin because the same thing applies to DLLs and shared libraries attacker could drop a malicious version of a shared library or DLL。

Into the folder that they control， it appears in the path。

 and that would be loaded before the valid version of that same binary file。



![](img/d368de23353deb603b5a8ddd1313caab_6.png)
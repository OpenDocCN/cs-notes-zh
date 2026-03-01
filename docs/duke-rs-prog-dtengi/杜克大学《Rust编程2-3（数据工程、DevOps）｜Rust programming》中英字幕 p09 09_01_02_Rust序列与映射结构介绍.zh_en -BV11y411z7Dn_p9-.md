# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p09 09_01_02_Rust序列与映射结构介绍.zh_en -BV11y411z7Dn_p9-

![](img/c78d68dc7830ed0ff3e619953fd2a679_0.png)

Here we have rust collections and a few important things about rust collections is there are some similarities to Python。

 For example， with a sequence。 It's just like a python list。

 more or less and with a map it's just like a python dictionary。

 But one of the key differences is that they're immutable by default。

 So let's go ahead and take a look at this sequence here。 at the very beginning。

 notice that the let fruits equals apple banana cherry。 this creates an immutable list。

 So you can't change it in the future， and this is a safety future of rust。

 the output if you printed it would be apple banana cherry。 Likewise， with maps。

 if you go ahead and you try to insert something into a default hash map and you don't create a mututable value it won't work because rust is going to protect you from creating a mutable structure unless you explicitly say mute。

 Now， if we go ahead and take a look at what the output of something would be。

You can see it's going to be a key value pair， Apple 10 banana 8 oranges 15， so in a nutshell here。

 similar to rust， Python also uses lists as sequences and dictionaries and Python lists are dynamic arrays and they're similar to a rust vector。

And with a Python dictionary like maps and rust， they're key value stores in terms of access patterns in both Python and rust。

 the elements in a list， Python or sequence and rust are accessed by their position。

 duplicate values， a Python list does allow duplicate values， just like a rust sequence。

 but a dictionary， both in Python or rust map don't allow you to have duplicate keys。Likewise。

 one of the key differences is iteration order as well is going to be different because in Python by default。

 a dictionary does actually in the new versions maintain the order。

 but it wouldn't in rust finally one major difference here is type safety and this is a key reason for using rust is that Python's list dictionaries are dynamically typed。

 meaning you can put anything aside but rust will have static typing which means that it only can contain things that explicitly are typed and this is a great security feature of rust。



![](img/c78d68dc7830ed0ff3e619953fd2a679_2.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p27 27_02_04_最小权限访问.zh_en -BV11y411z7Dn_p27-

![](img/c3c57489fbd1ec48926f62cbe32d6973_0.png)

Let's take a look at least privileged access as a security context inside of a castle in the computer world。

 obviously， we know about you want to limit the amount of privileges you give a user until they ask for them。

 that's really the same concept in terms of a castle here。

 So within a castle the access is strategically restricted。 The count， for example。

 could enter any area of the castle but a servant could only go where they are needed for their duties and the least privileged model enhances this security level。



![](img/c3c57489fbd1ec48926f62cbe32d6973_2.png)

In a similar way， there are users and programs that should only get the necessary permissions in a computer system。

If you give excess access， it's going to increase the risk that there could be some kind of an abuse。

 For example， if a Ca guard doesn't need access to the Treasury or a kitchen cook doesn't need to enter the barracks。

 Their jobs are limited to those authorized areas。 In a similar way with computing authorization is controlled through access policies。

 This means that a database application will get read and write privileges to a certain table。

 but it shouldn't be able to delete let's say files on a server。

 there are effective security grants that have only the minimum amount of access required。

 the additional permissions can be added if the responsibilities grow。

 but there's a strict baseline to start with。 Unfortunately。

 many organizations start with an overly permissive access model。

 Then what happens is you try to later lock down security and there's problems。 This is like。

Everybody into the castle before you restrict certain areas。

 it's better to adopt a least privileged mindset from the very beginning。

 although it does take a little bit more work up front。

 but it does greatly reduce the potential for damage from mistakes。

 bugs or bad actors and this limit to permission is going to lock down in this particular example。

 a castle， but in your case， a digital castle or your computer system。



![](img/c3c57489fbd1ec48926f62cbe32d6973_4.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p13 13_01_06_链表水果沙拉演示.zh_en -BV11y411z7Dn_p13-

![](img/d4e3d57b30290123f97a6ef17f04e0fc_0.png)

Here we have a linked list example here。 and one of the nice things about a linked list is that it has some really key elements of efficiency with things like insertion or deletion from a list if you don't care about accessing the elements。

 or in this particular example here， if you want to insert or remove elements from the middle of the list。

 But it's actually a much more rare data structure to use and it has a higher memory overhead and worse cache locality than either Vc or V deck。

 let's go ahead and take a look at how we would use it， though。 So again。

 I make this very similar to a previous V deck example here。

 except for a linked list at the very beginning here。

 I go ahead and I push these elements into the back of the linked list。 Now。

 here I do something a little bit unusual is that I convert it back to a Vec here。

 just to keep it similar to the previous V deck example here。

 probably wouldn't do this in the real world。And then after I shuffle it。

 I move it back into the linked list， and then I push the fruits to both the end of the list after shuffling。

 and then I go through， and I print it out。 So really。

 the idea here is that it's a specialized data structure that has a few unique properties。

 But most of the time you're better off using either Vc or V deck。 Let's go ahead and do cargo run。

There we go。 We see that we're able to actually do a very similar operation to Vec。



![](img/d4e3d57b30290123f97a6ef17f04e0fc_2.png)

![](img/d4e3d57b30290123f97a6ef17f04e0fc_3.png)
# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P56：-056-Functional Data Structures Chap5 Video 4.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The kind of stack we just implemented is a functional data structure。

A functional data structure is one in which there are no mutable updates。

Every operation takes a kind of old value， if you will。

 of the data structure and returns a new value。But it leaves the old one unchanged。



![](img/fb20f39e7eeb67a896adf88ba5e14e48_1.png)

You can see that in our stack implementations when you look at the types of the operations。



![](img/fb20f39e7eeb67a896adf88ba5e14e48_3.png)

Push takes in a value and a stack that is here， an alpha and an alpha list and gives us back an alpha list。

It actually does not change the underlying stack that old stack is immutable， as always， instead。

 push gives us back a new stack。

![](img/fb20f39e7eeb67a896adf88ba5e14e48_5.png)

Same thing with pump。It takes in an alpha list and returns an alpha list。



![](img/fb20f39e7eeb67a896adf88ba5e14e48_7.png)

We say that functional data structures are persistent rather than ephemeral。

That means all the values of the data structure still persist throughout time。



![](img/fb20f39e7eeb67a896adf88ba5e14e48_9.png)

We saw that with our stacks S and S prime。S was unchanged by pushing one on it。

And S prime was unchanged by popping one from it。Those old values are still around and still available for use。

 They persist。 they have not disappeared。 Now you might ask。

 is a persistent data structure as efficient？

![](img/fb20f39e7eeb67a896adf88ba5e14e48_11.png)

As an ephemeral data structure， is it going to be harder to write， is it going to be more complex？

Maybe so。It turns out the OcaMml compiler is very good at efficiency at making sure that representations of the data structures share the same space and memory so that you don't waste memory by having all of the different versions of it still around。

And of course， there's garbage collection in Ocal， just like there is in Java and other OO languages。

 and the garbage collector can reclaim memory that's no longer in use。As for time efficiency。

It is a phenomenon that sometimes functional data structures or persistent data structures rather。

 do require a little bit more time complexity to implement。

It's not uncommon as a rule of thumb for it to say maybe take logarithmic more time to get a functional data structure than an imperative one。

That's not a huge amount of overhead to pay。And you get a lot of benefits along with it。

 both the benefits of persistence and the benefits of being able to reason more easily about what is happening in the code because of the absence of imperative features and mutable updates。



![](img/fb20f39e7eeb67a896adf88ba5e14e48_13.png)
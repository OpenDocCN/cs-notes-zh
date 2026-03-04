# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P154：-154-Compilers and Interpreters Chap9 Video 1.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/61b35276bfbe3c55637a544b354cf75d_0.png)

A compiler is a program that operates on programs。So we're treating code as data when we talk about compilers。



![](img/61b35276bfbe3c55637a544b354cf75d_2.png)

The data itself is code。

![](img/61b35276bfbe3c55637a544b354cf75d_4.png)

A compiler takes in as input a source program。

![](img/61b35276bfbe3c55637a544b354cf75d_6.png)

And produces as output， a target program。

![](img/61b35276bfbe3c55637a544b354cf75d_8.png)

Then the compiler goes away。It's not needed to run the target program。😡。



![](img/61b35276bfbe3c55637a544b354cf75d_10.png)

The OS helps load and launch the program but the compiler is no longer needed to be around。

 you could completely delete it from the system if you wanted， when the target program runs。

 it itself accepts inputs and outputs， for example。

 maybe the target program is an enigma simulator and it takes as input strings and keys and produces as output encryptions or decryptions。

😡。

![](img/61b35276bfbe3c55637a544b354cf75d_12.png)

![](img/61b35276bfbe3c55637a544b354cf75d_13.png)

![](img/61b35276bfbe3c55637a544b354cf75d_14.png)

![](img/61b35276bfbe3c55637a544b354cf75d_15.png)

![](img/61b35276bfbe3c55637a544b354cf75d_16.png)

An interpreter， on the other hand， takes as input a source program。



![](img/61b35276bfbe3c55637a544b354cf75d_18.png)

But it doesn't produce a target program as output。

![](img/61b35276bfbe3c55637a544b354cf75d_20.png)

Instead， the interpreter stays around。And takes in whatever inputs the program was supposed to take itself and produces that output。



![](img/61b35276bfbe3c55637a544b354cf75d_22.png)

So it's like cooperating with the source program in order to transform inputs into outputs。😡。



![](img/61b35276bfbe3c55637a544b354cf75d_24.png)

![](img/61b35276bfbe3c55637a544b354cf75d_25.png)

The primary job then of a compiler is to do translation。

Translation typically means from a high level language like Java or Ocal。

 down to a low level language， maybe even a machine language like X86。



![](img/61b35276bfbe3c55637a544b354cf75d_27.png)

![](img/61b35276bfbe3c55637a544b354cf75d_28.png)

![](img/61b35276bfbe3c55637a544b354cf75d_29.png)

Compilrs typically therefore can offer better performance because they optimize to improve the code so that it runs very quickly on the machine。

😡。

![](img/61b35276bfbe3c55637a544b354cf75d_31.png)

![](img/61b35276bfbe3c55637a544b354cf75d_32.png)

Interpreters， on the other hand， their primary job is execution。 they just want to run the program。😡。



![](img/61b35276bfbe3c55637a544b354cf75d_34.png)

Typically， they're easier to implement than compilers are。



![](img/61b35276bfbe3c55637a544b354cf75d_36.png)

And sometimes you can do a little bit better of error messages or debugging with an interpreter as well。



![](img/61b35276bfbe3c55637a544b354cf75d_38.png)

Here's a very common implementation technique these days。



![](img/61b35276bfbe3c55637a544b354cf75d_40.png)

You take a source program， you run it through a compiler to get an intermediate program which is usually in some Bte code language。

 for example I'm sure you've heard of Java Bte code and you've seen the dot Bte extension for our OcaMl programs which is actually OcaMl Bte code。

😡。

![](img/61b35276bfbe3c55637a544b354cf75d_42.png)

![](img/61b35276bfbe3c55637a544b354cf75d_43.png)

![](img/61b35276bfbe3c55637a544b354cf75d_44.png)

That byte code is executed by a virtual machine， and you can think of the VM here as being a kind of interpreter。

 it takes in the program， it takes in the actual input that program is supposed to operate on。

 and it produces the output in cooperation with the program。😡。



![](img/61b35276bfbe3c55637a544b354cf75d_46.png)

![](img/61b35276bfbe3c55637a544b354cf75d_47.png)

![](img/61b35276bfbe3c55637a544b354cf75d_48.png)

It can get even more nested than this， in fact， inside of the Java virtual machine。

 they've actually stuck a compiler， if there's some code that's getting executed a whole lot。

 it can go ahead and compile that piece of the code down to the machine language for better performance。

😊。

![](img/61b35276bfbe3c55637a544b354cf75d_50.png)

![](img/61b35276bfbe3c55637a544b354cf75d_51.png)

So there is a broad spectrum of techniques that can be used to implement a programming language。



![](img/61b35276bfbe3c55637a544b354cf75d_53.png)

![](img/61b35276bfbe3c55637a544b354cf75d_54.png)
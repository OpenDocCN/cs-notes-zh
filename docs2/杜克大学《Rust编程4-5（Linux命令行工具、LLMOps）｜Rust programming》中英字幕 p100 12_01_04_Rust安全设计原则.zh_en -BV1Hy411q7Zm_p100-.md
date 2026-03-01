# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p100 12_01_04_Rust安全设计原则.zh_en -BV1Hy411q7Zm_p100-

![](img/42af0fa3171081c6c866db0f86416590_0.png)

![](img/42af0fa3171081c6c866db0f86416590_1.png)

The rust language is a modern compiled language that's secured by design。

 And we're going to talk about this using a concept of a mythical magical kingdom called rustland First。

 Let's define the core characteristics of rust。 We have memory safety without garbage collection First here。

 Ru provides memory safety without the need for garbage collector。

 That means theres no null or dangling pointers。 No data races。

 and the safety is actually enforced at compile time。

 This prevents a wide class of common errors and vulnerabilities。 Next up。

 we have ownership and borrowing rust， unique features of ownership and borrowing help manage memory safety。

 and in rust， each value has a variable that's called its owner。

 There can only be one owner at a time。 This prevents multiple threads from modifying data concurrently。

 This is a common source of bugs and crashes and other languages。 It's also immutable by default。

 And rust。 All variables are immutable by default。This means that once a variable is a of value。

 it can't be changed unless explicitly marked as mutable。

 This design choice prevents accidental modification of variables and data races。 Next up。

 we have zero cost abstractions，0 cost abstractions mean that it provides high levell syntax without sacrificing performance。

 and these high level abstractions， make the code a lot easier to understand。 and right。

 reducing the likelihood of bugs and security vulnerabilities。

 We also have the concept of built in testing and documentation next year。

 which means that the documentation is present throughout the code。 you can have more clear code。

 understandable documentation and it's all built into the rust installation。 Finally。

 we have concurrency without data races。 This means that it's designed to prevent data races at compile time。

 and the rust ownership system allows fine grained control over。😊。

Where that state change would happen and the type system is enforced for any given piece of data。

And it can be either mutated by a single thread or read from multiple threads at the same time。

 But not both。 This design choice helps prevent complex， hard to detect concurrency errors。

 which can lead to security vulnerabilities in typical multithreaded application。

 So let's go into a fairy tale here。 And let's talk about the magical kingdom of Ruland。 In Ruland。

 there's a special rule about toys represented by memory in our story。

 Every toy or piece of memory has only one owner at a time。

 This prevents confusion and fights over who gets to play with what toy Imagine if two children wanted to play with the same toy at the same time。

 It could lead to a conflict or the toy getting broken。

 This is a lot like memory safety and ownership and rust。

 It prevents conflicts between different parts of the code trying to use the same piece of memory。

 Now， sometimes the owner could lend a toy to another person under the strict rule that the owner couldn't play with it until。

It was returned。 This is a lot like rusts's borrowing feature， ensuring safety。

 even when the memory is shared。 the Rulands toys are also magical。 Once they're made。

 they can't be changed unless they had a special mutable sticker。

 This stopped anyone from accidentally breaking or changing a toy。

 This is also similar to how variables in rust are immable by default， preventing accidental changes。

 The kingdom also is known for magical builders who can make complicated toys using simple blocks。

 All without slowing down the toy production。 This is similar to rust zero cost abstractions。

 which allows developers to write complex code without sacrificing performance。😊，Finally。

 Rust has a great library filled with instructions on how to use each toy properly。

 This is similar to Rus built in documentation， making sure that developers know how to use each part of the code properly。

 And this would reduce the chance of a mistake or a security problem。

 And at the very end here with Rusland。 we have a unique method of organizing play dates。

 So instead of the children playing together in a chaotic manner。

 Each child would have some time with each toy in a controlled environment。

 preventing the chance of a toy getting lost or broken。

 This is a lot like the rust concurrency model， which prevents data races by ensuring the data can either be modified by one thread or read by multiple threads。

 but not by both at the same time。 So the fairy tale ends with Rusland becoming a happy and safe kingdom for everybody inside just like Rust is a reliable and efficient language for all of the users。

😊。

![](img/42af0fa3171081c6c866db0f86416590_3.png)
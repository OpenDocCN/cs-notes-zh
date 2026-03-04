# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p28 27_17_pieces-of-a-language -BV1bw4m1D7MM_p28-

I thought I would finish up this section by taking a huge step back and as we've learned a bunch of ML already。

 think about is this the important stuff， is this how you learn a programming language。

 and so I want to focus for just a minute on what does it take to learn a programming language and which part of that are we focusing on in this course？



![](img/6f4daa6247a31d13b28256617939c366_1.png)

So I like to think of it in terms of five different things。

 If you want to learn a programming language and make yourself a better programmer。

 you need to know the syntax。 How do you write the language constructs， If you don't know the syntax。

 you're not going to be able to write down programs。 I understand that。

 but you also need to know the semantics， What are the type checking rules and evaluation rules。

 If you don't know what programs mean， you're just trying to write down different things and hope to get the right answer。

 that's why we keep focusing on what do these constructs mean。

 what are the actual rules so that we can reason about our programs correctly。

Something we haven't emphasized quite as much is that you need so far at least。

 is you need programming idioms， it's not enough to know that there's an if then else expression that works in a certain way。

 you need to recognize when and if then else expression is the right thing to use。

We talked a little bit about the idiom of using nested function bindings in order to have private helper functions that couldn't be used somewhere else。

 That's different than just the semantics of lead expressions and function bindings。

 It's about representing recognizing typical patterns of use for certain features。

And then there's these other two libraries and tools。

 So what facilities does the language provide to you that let you do things you either couldn't do on your own or would have to reimplement a lot of code that somebody else has already provided for you。

 So an example of a library that usually has to be provided for you is some way to read and write files。

 If a language doesn't give you that on some level。

 you're not going be able to implement it yourself because you need some way to access the file system。

On the other hand， libraries for things like data structures like trees or hash tables or lists are things that you actually could define on your own。

 So far in M， we've used lists that have been provided to us。

 but we're going to learn enough features of M to know that we didn't need that。

 that we could have defined our own。And then finally， tools。

 these are things that language implementations give you to make your job easier。

 maybe it's a repple， maybe it's something that helps you format your code well。

 maybe some of you have used debuggs in other languages。

I like to emphasize that tools are not actually part of the language。

 there's something provided by an implementation of the language or just as a separate tool。

 and as valuable as they are， they are separate from the language itself。

So these are five separate issues and in practice， if you want to be an effective programmer。

 you need to get good at all five of these things， learning syntax， semantics， idioms。

 new libraries and tools， and I would like you to be good about keeping these ideas separate People often confuse them。

 Oh man， it's like a pet peeve of mind when someone says oh I like the ML language because it has a rple。

Theres nothing to do with the ML language that has a repple that's a tool that's provided by a particular implementation of the language。

 and it's good to keep those ideas separate in your head。



![](img/6f4daa6247a31d13b28256617939c366_3.png)

Okay， so bring it back to this course， this course focuses a lot on two and three on the semantics and the idioms and I want to justify that for you so that you'll continue in the course and understand why we're focusing on that。

I tend to not focus on syntax a lot because as much as you have to know it。

 It's usually not particularly interesting。 If you want to study American history。

 you really need to know the American Civil War ended in 1865， but that is not the interesting part。

 That's the basic stuff that get you to actually reason about theories and ideas。 And in our case。

 semantics。 The other reason I usually am dismissive towards syntax。

 I that people obsess over subjective preferences。 And I am not going to sit here and tell you that this syntax is good。

 And that syntax is bad。 I'm not an expert on syntax any more than you are。

 I do understand semantics。 And I want to teach that to you using syntax only is necessary。

AndAs far as libraries and tools， they're really crucial。

 but you're always going to have to learn new ones I'd rather teach you how to think about every programming language and the fact that we happen to have a repel for M or some other language has a debugger or there's good libraries for writing web programs is really not our focus and I truly believe that if you get good at learning semantics and idioms of programming languages。

 it actually makes you better at learning libraries and tools because it helps you say。

 oh how does this library work， what these these methods or functions that are being provided to me what is their semantics and how are they typically used the same mental skills。

 intellectual tools you use for learning a language become incredibly valuable for learning libraries we're not going to learn libraries we're going to focus on the languages themselves and this has the unfortunate effect that it makes the programming languages and the programs we write。

 sometimes seem a little silly right here we are， we've watch all these videos and we know how to append to list。

Or take the max number from a list of numbers。 I know that real programming doesn't look like that。

 but I like to use the simple examples so that I can focus on the semantics and so I ask you not to judge the languages we use by the approach we're taking in the course if I taught all these same ideas in Java or Python or ja which I could do those languages would look silly too。

 Instead I want to use these languages because they're the best vehicles for focusing on semantics and idioms and I assure you that there are ways to take say Ruby and use it for web programs or racket and use it for real desktop software and so on。

 and that's just not our focus， learn the semantics and the idioms in this course and become a better software person and a better computer scientist as a result。



![](img/6f4daa6247a31d13b28256617939c366_5.png)
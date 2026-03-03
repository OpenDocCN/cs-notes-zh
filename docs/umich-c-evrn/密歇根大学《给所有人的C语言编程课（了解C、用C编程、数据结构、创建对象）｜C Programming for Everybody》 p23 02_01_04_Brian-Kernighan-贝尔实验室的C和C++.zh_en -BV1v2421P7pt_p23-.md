# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p23 02_01_04_Brian-Kernighan-贝尔实验室的C和C++.zh_en -BV1v2421P7pt_p23-

![](img/bc8a19f0a9892080601725f6c03fc5b2_0.png)

![](img/bc8a19f0a9892080601725f6c03fc5b2_1.png)

![](img/bc8a19f0a9892080601725f6c03fc5b2_2.png)

It was highly collaborative in the sense that this was a group of make up a number of 30 is people who were all interested in much of the same kinds of things。

 although with tentacles off。you know， theoreticalore computer science。

 math and so on physical sciences kind of thing， but mostly a lot of us at least were basically software people Garner came to Bell Ebbbs。

 I think in 1979 after getting his PhD at Cambridge，And he was interested in simulation。

 you know he'd known Sim in particular， which was object probably one of the very first object oriented languages。

 and he wanted to do simulation， but C was kind of the language that people used at Bell Labs and so what he did was to try and take some of the good ideas from Simul in particular class ideas and。

P that on top of C and for a long time， the implementation of C++ was basically translate C++ into C。

 and then you could run it anywhere， so it's one of many pragmatic engineering decisions that Brna made。

That if you want， it's hard to get people to buy into a new language if they have to carry an enormous amount of infrastructure and support and another baggage with it。

 whereas if it's one more program that then fits perfectly into your existing environment as a language as libraries and all the rest of it。

 much easier。And so C went through a period of evolution， while， it's still evolving。But。

Starting there in the very early 1980，81， something like that。

 the two languages were very much together because we're all in this one group at Bell Labs that would fit comfortably in this corridor。

 this building and，Brnaitzitz certainly knew C inside out and then was developing this new language that ran on top of it that stressed C compilers。

 so that was useful because the code that his preprocessor generatedative was astonishing。

And I think some of the ideas in C++ then retrofitted back into C。

 in particular the obvious one of how you declare the arguments for a function。

 I mean just that was better。and a handful of other things。

 so for a while the two languages you could say that C was a pretty close to perfect subset of C++ I think that's evolved in both directions and so it's less true now than it was。

 but for a long time you could take a C program and just run it through C++ compiler and it would work。

There's a general observation that。People write code differently than computers write code。

 and so machine generated code tends to stress。In particular。

 the compiler or the language for which you're generating and so in the C++ the C example。

 they would incredibly deeply nest its constructs of one sort or another。

Prenheses that made Lisp look tame。And then very convoluted pointer kinds of computations as well。

 function pointers， all kinds of， and so it was definitely a stress test and also generating things that had odd sizes and so on that were not expected or at least。

Pass that had maybe not been thoroughly tested in a given compiler。

I think a lot of people did not think that C++ was right in some sense it had various warts。

 blemishes and so on， many of those were again direct result of Brna's engineering judgment。

 if you want this thing to take off the more culturally compatible it is。

 the more likely it will do that if you make something that's wildly different people are going to kind of ignore you。

And so。And so some of the syntactic problems of C++ that are still with us are you know。

 the same syntactic problems that you can see for quite a while when I was trying to teach C++ to people。

 I would show them the translation that goes from a C++ object into C and you know it's basically just pointers into structures with the compiler kind of keeping the names apart so you don't have to think about them。



![](img/bc8a19f0a9892080601725f6c03fc5b2_4.png)

And seeing that translation， you could see how object oriented programming could be done at essentially no overhead because it's just structure pointers。

And funny function names and you can pass function pointers around and so it was all pretty well behaved and I think that understand I mean to help me understand what was going on and。

C++ in object oriented programming and so on。I think in modern languages and Python I'll fine example of that。

 there's an incredible amount of magic going on there and I don't quite know how it's done as well as it is。

 I mean， I can sort of imagine， but the mechanisms to make some of those things list comprehensions with lambmbdas in them and so on as how the heck does that work？



![](img/bc8a19f0a9892080601725f6c03fc5b2_6.png)
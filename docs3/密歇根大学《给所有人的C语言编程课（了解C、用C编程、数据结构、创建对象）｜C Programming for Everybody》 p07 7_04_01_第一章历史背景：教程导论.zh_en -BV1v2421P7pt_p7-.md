# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p07 7_04_01_第一章历史背景：教程导论.zh_en -BV1v2421P7pt_p7-

![](img/79864a30d4d4a8f9dd3761241420f8c9_0.png)

Hello and welcome to chapter 1 of Carnegie and Richitchie。 My name is Charles Severence。

 and of course I'm your professor for this course that's about history。Welcome to this course。

 it's really part of a learning path。I don't think that C should be your first programming language and I don't think it should be your last programming language I have a whole series of courses that are all free and available online。

 both just on the web， places like freecodec and Coursera andedX and the place that you're at in my learning path is that you're at right now as C programming and we're not learning C programming to learn C programming。

 we're learning C programming to take a historical look at how computers work and lead into computer architecture I'm not trying to teach a coding in C but I am going to explain how computers work and things like how Java works using C as kind of like the。

It just gives me a way to explain Java to you。The outline of the textbook is a kind of pretty typical computer science textbook where it it starts off easy and then whoa。

 everything goes pretty crazy。 So chapters 1 through four。

And we're on chapter1 right now is mostly syntax and it's just in the programming language and especially if you know a little bit of Java or a little bit of PP or a little bit of JavaScript。

 some of that syntax is going to be like， whoa， of course this is familiar and the answer is well that's because all those languages came from C So it kind of feels like just another programming language。

Except that arrays are not lists and character arrays are not strings and character arrays kind of look like strings。

 but they don't work leg strings。 And you can get in all kinds of trouble。 But other than that。

 once you sort of stop worrying about how long things are。Pretend it's okay， which is dangerous。

 of course， when you write code。Chapters 1 through four feel a lot like you're just any other programming language。

 but then chapters 5 and6 are the valuable chapters of this book。

 but they also become a lot more difficult， so don't give chapters1 through four short shrift because5 and6 are going to just go。

 and then7 and8 is just sort of filling in detail and78 are not so critical。

 you know it just kind of fills in all the gaps。So that's the outline of the book。

Just expect that one through four is going to be smooth and then five and six are going to be like。

 now we're really getting somewhere， okay。So looking at chapter 1， again。

 chapters sections 1 through 15 looks not that different than any other programming language that you've learned。

Chapter section 1。6 is a。Ees staticatic allocation arrays。

 you have to know how big they are when you declare them and you can't resize them until chapter 5 at which point we will start talking about dynamic memory and pointers and resizing。

Chapter 1。71。8 functions in parameters， and it's all called by value in this early phase called by reference is in chapter 5 because we need to know about pointers before that we talked about chapter5。

 even though they use a little pointer syntax here and there in chapterpt 1。In section 1。

9 is character Rays， read this one closely because there is no string object in C。

 there's no objects at all in C。And in section 1。10。

 they talk about variable scoping between functions and that feels kind of similar to other languages and part of it is because other languages took their inspiration from C。



![](img/79864a30d4d4a8f9dd3761241420f8c9_2.png)

🎼So if we just take a quick look at C character arrays。

 we must understand that the size of the character array is at allocation time and there is nothing auto extended。

 And if you write a for loop that goes off the end of the loop like I've got where you know I have a character array that's 10 long and I write a loop that goes up to1 thousand0 storing data in it eventually the program will blow up and you can see like I mean。

 in Python you make you just add characters， whereas in C。

 if you add characters beyond what was allocated， the system blows up and。



![](img/79864a30d4d4a8f9dd3761241420f8c9_4.png)

You probably heard me say more than once that the C language is probably responsible for 90% of the security。

 significant security holes in all of computing， and this kind of code where you allocate an array and then you wildly go beyond it。

Ends up making it so that people can inject things into operating systems and routers and all kinds of things is。



![](img/79864a30d4d4a8f9dd3761241420f8c9_6.png)

Why we don't use C to write programs I mean here we are in the first page。

 the example one of chapter one is why we don't write C very often。

 or if we do we have to be really careful of reviewing it。right it's really fast。

 but it's also dangerous。

![](img/79864a30d4d4a8f9dd3761241420f8c9_8.png)

![](img/79864a30d4d4a8f9dd3761241420f8c9_9.png)
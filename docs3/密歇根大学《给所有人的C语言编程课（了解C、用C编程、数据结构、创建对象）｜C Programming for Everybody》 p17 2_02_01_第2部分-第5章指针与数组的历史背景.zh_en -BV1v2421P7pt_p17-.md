# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p17 2_02_01_第2部分-第5章指针与数组的历史背景.zh_en -BV1v2421P7pt_p17-

![](img/2e7bb090d5bee3d37172c797eb7d4991_0.png)

Pointers are not integers， so if you go back to chapter 2， there was from the book。

 a table of the sizes of things。And so if you look in the PDP 11 integers are 16 bits in the honeywell。

6000， there are 36 bits in IBM 370， there are 32 bits in Inter data 832， there's 32 bits。

 Now I've added a line to this that tells the number of bits in addresses in these systems and you can see if you compare the int numbers to the address numbers that in all the cases except the PDp 11 the integer is larger than the address。

 which means that there is extra space in the address and we can almost treat addresses as unsigned integers Now the PDP 11 is a little weird in that that 16 to 32 is a range of delivered computers over the years and not all computers had full memory and not all applications use the entire memory of the entire computers。

 So most of the time you can conveniently put an address into an integer and then get that address back out and not have。



![](img/2e7bb090d5bee3d37172c797eb7d4991_2.png)

Tncated that address or messed up。So treating pointers as integers almost works。

And the longer ago in history it was， the more likely it did work。

Addresses are generally positive numbers that often start from zero。

 sometimes heap numbers come down and sometimes stack numbers go up or whatever。

But most computers did not come with a maximum memory installed。 And。

 and if you're a multius computer， you didn't give all the systems memory to every application。

 And we tended to use very little memory and applications。 We were very careful about it。

 So it just never ran into the problem of our memory addresses， not fitting into integers。 So in the。

Early 70s， applications could get away with having a function that returned an address。

 returned it as an integer， and then copy it into a pointer without conversion。And so。

By like the early 80s， the notion of a void pointer gave us a way to have a generic address that is a pointer to something we don't know what type it is。

 because all addresses are addresses， but what they point to is different。

And so if you take a look at the AlLEC function， which will play a lot more in the next chapter。

 the Al says， oh， give me 42 bytes and give it back to me as a pointer。

 give me a pointer to 42 new bytes that you just allocated。So if you go in the early 70s。

 Alec returned an end。But then we would cast it to whatever type we wanted。

 So we would say Alec 42 would give us an address that'd be an integer。

 but then we'd cast it to an integer star， which is a。No loss cast。

 And then we would store it by the time in the 1978 CN book。

 we tended to call it a cha star because of the 42 is how many characters we're going to allocate。

 And then you would take the pointer to a character and cast it to a pointer to an integer。

 And so aec of 42 would give us 14 integers。 Actually， I think if I got my multiplicationcation。

 right。

![](img/2e7bb090d5bee3d37172c797eb7d4991_4.png)

But in modern sea， we have thiser void pointer which basically says， look。

 Alec is going to return an address and you have to cast it to something。

So AlEC 42 returns a void star， which is casted to an intstar。

 which is a lossless cast and not something that's going to confuse the compiler。

 and then we store it in our int star variable and so void you'll。



![](img/2e7bb090d5bee3d37172c797eb7d4991_6.png)

Everything you'll ever touch will be using void， but I just wanted to give you a little bit of the history of it and why void's kind of not mentioned in this 1978 book Every time in the class I'm like。

 hey， it's time to learn about security never got kind of groans like oh no back when I taught HTML injection and SQL injection and cross ice scripting in all my previous classes and here's the classic XKCD where。



![](img/2e7bb090d5bee3d37172c797eb7d4991_8.png)

The mom has named their child with a bit of SQL and some single quotes and some comments。

 and that's all fun。It's important that we as software developers are aware of how the things that we build could be corrupted by those with evil intent。

 right？So it has come time to talk about that。4 C。Probably the single worst security hole。

In all of computing history。From 1950 to today， even before C was a thing is what's called buffer overflow。

And it has to do with the fact that。There is no sense。That a string of characters has a length。

It has an allocated length， but it doesn't have a runtime length。

 and so when we put more data into a string than can hold the string。

 it just keeps on storing beyond the end of the string， it doesn't like push。

 make a little more space。

![](img/2e7bb090d5bee3d37172c797eb7d4991_10.png)

And so this is from the Wikipedia page where you have an eight character。嗯。String， followed by。

2 character integer or something。 And we copy the string excessive， which is a 9 character。

 which includes 9 characters and the slash 0， the 0。

 And that completely overrites by just trying to write into the A string。

 It overrites the B variable as well。 And so。

![](img/2e7bb090d5bee3d37172c797eb7d4991_12.png)

That's buffer overflow。 It's sort of like somehow we are going to push too much into this variable so that it extends where it's been allocated and that never is detected。

 And then it keeps going on。 And it means that you can do all kinds of things with buffer overflow。

 You can change variables。 You can like turn on super user permission。 Who knows。

 you got to look at the source code。 You got to carefully construct a sort of nasty attack， but。

The attack vector is the fact that。String arrays bounds are not checked when we're copying stuff in。

 And if you write bad code， or if the system writes bad code。

 it's just going to go wipeing out memory。 So it turns out that the probably the worst offender of this is the getas function。

And this was part of standard C for a long time。And so here what I'm doing is I'm creating a 15 character string array。

 character array。Which is 15 elements。And I'm calling get S and the problem with getS is like。

Somebody's going to give us that data and it's not us， and then I print it out。

So the first thing you see is when I compile a。Pit a code that has gets。 The compiler is upset。

 I have greatly。

![](img/2e7bb090d5bee3d37172c797eb7d4991_14.png)

Simplified the errors， it just it comes up with three errors and this is a subset of one of the errors。

 the compiler is telling you don't use GS if you didn't hear what I said the first time。

 don't use GS。And so， so the compiler is not happy， but it it's like， you know， people write that。

 so we're going to run it。 Okay， a do out， which starts the code。



![](img/2e7bb090d5bee3d37172c797eb7d4991_16.png)

As soon as that line getS runs。😀哈哈。😊，The runtime of the C standard SDIio。

 H says before it prompts us for the data， it actually adds a print statement。

 not our print statement， it's the library saying。

![](img/2e7bb090d5bee3d37172c797eb7d4991_18.png)

You really， really should not be using GS。 And if you think this program is trustworthy。

 you're probably wrong。 So I type hellello world， which is 11 characters。 hellello space world。 Yeah。

 it's 11 characters。 Hello worlds 11 characters。 I type 11 characters in。

 that includes the 12 character， which is the back slash 0。

 And that fits into S S 15 of 1 15 element string character array in the variable S。

 So the program works just fine。 Then I type 8 do out again。 and it once again tells me。

 please don't use getS。 You're going to be in so much trouble。



![](img/2e7bb090d5bee3d37172c797eb7d4991_20.png)

![](img/2e7bb090d5bee3d37172c797eb7d4991_21.png)

![](img/2e7bb090d5bee3d37172c797eb7d4991_22.png)

And now I type instead a bunch of。A hello and a bunch of spaces in the world。

 and it prints out hello a bunch of spaces in world， but has overwritten all kinds of unknown data。



![](img/2e7bb090d5bee3d37172c797eb7d4991_24.png)

After。The S15， so that's， you know， that's like 30 or 25 or 30 characters and the first 15 are in S。

 but then the next 15 are somewhere else。And S is on stack because it's an automatic variable in mainine。



![](img/2e7bb090d5bee3d37172c797eb7d4991_26.png)

And it goes wiping out the rest of the stack。 Now， it turns out that the C runtime puts things on the stack to kind of mark or to catch this overflow。

 And so what happens is as soon as that code finishes， it says abort trap 6， which is basically。

The see runtime saying， you know what， I'm not going to let this program proceed any further because there has been an array that got messed up。

 and it's not that it。Caught， it's not that it caught the array messing up。

 It didn't know how long it was。 It just put characters in。

 But what it did is I put something after the array， and then it checked for it later。

 And that got wiped out。 And it's like， okay， you wiped out my magic little secret。

 And so I'm going not let you continue。🎼And so we don't want you to use getS。

 And this is a buffer overflow。 And I can give you it eventually。

 maybe we will look at some much more complex examples of this where we try to like use something like getS to manipulate what the program does rather than just blow the program up。

 But this is a very simple example of buffer overflow。 So in summary， pointers are。



![](img/2e7bb090d5bee3d37172c797eb7d4991_28.png)

🎼，🎼Beautiful， most beautiful part of sea。They're complex。

🎼But basically pointers make it so that a high level language can function like a low level language if we don't have pointers and I mean not even kind of crappy Python ones。

 I mean pointers that we can。🎼Look up and then dereence officially and formally and not have it be a sneaky way that we're doing it。

 That means that you can do the things that operating systems need to do。

 the kinds of things that we used to write assembly language for， meaning we're going。

 here's a buffer of memory。 We're going to copy this buffer。 We're going to do another thing。

 And there's another buffer。 And there's a link list of all the different buffers。



![](img/2e7bb090d5bee3d37172c797eb7d4991_30.png)

🎼到了的 da。So understanding pointers leads you to the path of assembly language， machine language。

 and any ultimately hardware。So you should not rush through this material， pointers are really。

 really important。Everything we're going to do from now on pointer is just。

 I'm just going to say pointer pointer pointer， just like I say， I'm just trying over all the time。

 I'm going to say pointer all the time。Sections 57 and 51035212 are a little dense。

 so what I really want to do is understand the stuff I just talked about and the corresponding sections。

And chapter six will be more fun because we'll be doing much more with the pointers rather than just what is a pointer。



![](img/2e7bb090d5bee3d37172c797eb7d4991_32.png)

🎼Yeah。

![](img/2e7bb090d5bee3d37172c797eb7d4991_34.png)

![](img/2e7bb090d5bee3d37172c797eb7d4991_35.png)
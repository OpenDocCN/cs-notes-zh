# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P66：1 - Spring 2023 Exam-Level 12 Problem 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/1a40dc39ca96508fe943043f533e5a54_0.png)

Everyone again， one real quick thing that I forgot to go over is the runtime for this problem。

 not bad end the recording a little bit too early。Okay。

 so the runtime for this problem as we know it's supposed to be O of N cubed right。

 and so let's just kind of prove it a little bit down here。Let's just say。

 let me pull this entire algorithm。Is there algorithm？And basically it just go over the runtime。Okay。

 so we know that we're doing for each letter in grid right and so this is this immediately says。

We're doing basically for earth， we'll say。For n squared characters。

I was basically translate this code up here， the pseudo code up here into a little bit of runtime code。

 I guess。So for n squared characters。We know that what we're doing is we're checking eight different directions。

 right， so check。Eight directions。Section we can even do， we can even model it as for。Each。

Of eight directions。So for each of the eight directions。

 what we want to do is we basically want to get that string。Get string。S。And then run Lps on S。

 that's the main work that's being done， right？And then also， you know， remove。From try。

So these are basically the main runtime things that are happening right so here we're doing n squared work。

Here we're doing eight or， let's say。And squared iterations。8 iterations。

And so now we need to figure out how much work all of this takes right to figure out our total runtime。

So getting the string S is a pretty straightforward operation。

 we basically just go back we track back through the grid and get those letters right and so that should take in the worst case it should take end time right the reason being we know that our grid is n by N。

Right so the maximum length of a string of characters in one direction is n right we can start here and this is going to be n characters。

Right， and so basically what that means is that the most characters we can have in our our string S is going to be。

This is basically going to be an O of N operation。Okay。

LPS of S is actually very similar right because now once we get the string S。

 we know that it's at most of length n and checking for a string in our try。

He's also like a constant time operation with respect to his length of the string。

And so the length of the string is n， that means that this is also an O of n operation right because basically we we need to you know trace through the try a letter by letter checking for the longest prefix and so in the worst case。

 the longest prefix is the entire word itself， which means that we would do you know n separate comparisons to figure out LPS of S。

So what that means that this is also an O ofN operation and then finally removing from tryI is the exact same as LPS of tryR because basically we're just tracing through our try again and removing letters this time instead of just searching for them。

So these are all O of time operations meaning this entire block。Is an O of N， right？So now we see。

 okay， we have n squared iterations on the outside。Times a iterations inside that。Times and work。

 total。So we tightenly have， you know。8 and cubed。Which simplifies to O and could we don't care about concepts。

And yeah that's the total runtime so as you can see it follows our runtime constraint and you know that's kind of what I did right here in the beginning is that we can do n work per letter。

 which is what we ended up doing in the worst case。😊，Yeah， okay， this time for real， goodbye。

 see you guys next time。

![](img/1a40dc39ca96508fe943043f533e5a54_2.png)
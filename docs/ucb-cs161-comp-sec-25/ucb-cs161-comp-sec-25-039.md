# 039：-MemSafety3, Bonus Video- Off-by-One Q&A.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Question。That's a great question， Are there some conditions where this doesn't work， for example。

 if this C bites somehow over over rolled over I guess into CE and you're right。

 there's actually some cases where this is not going to work on the project if you get unlucky you might run into one of those cases and we'll talk about how you can fix it on the project so I'll leave that an exercise to you or you can ask later but。

It's possible that some configurations of addresses will not work。 That's a good question。

Any other ones？Okay。Oh yeah， go for it， sorry。Oh， I add 16 at ESP。

 so it's really not the most important thing here， but if you go back to the steps of the function call。

 this is step 11， it's the step where I removed the arguments from the stack。

 so here this dot dot dot I pushed four arguments onto the stack and to delete them。

 I add 16 to remove four arguments off the stack。So it's just finishing calling E。

Really not that important， but something that we added for completeness。 One more question。

That's a great question。 Why does the position of EBP not matter once you open a shell。 I mean。

 it depends on what your shell code is doing， But if your shell code never references this value。

 then it doesn't really matter what you put in there because if you think about it。

 EBP is just a register。 It's just some register， it holds a value。 And if you need it。

 you ask EBP for its value。 But at this point， because you're executing code that you wrote yourself。

 if the code that you wrote yourself， never asks EBP for its opinions。

 then it doesn't really matter what goes in EBP。 And really， if you care about what's an EBP。

 you could even have your own shell code， inject some value that you care about back into EBP。

 if you really care。 But it's just a register， it holds a value。

 And if your shell code doesn't use it。 then nothing bad happens。That's a good question。Okay。

 one more。Yeah， there was a question of does it matter where you put the fake RIP in Maine。

 also a good question， you're stumping me with all these good questions today， So you're right。

 there's actually other ways to make this exploit work too。

 just like how in the original buffer overflow the very first one that we showed you。

 you could put shell code and the address of shell code kind in all sorts of different locations below the RIP above the RIP。

 you could put this pair of values， the fake SFP and the fake RIP， you could put it down here。

 you could put it like up here， you could put it up here。

 as long as it's somewhere you can overwrite， it's totally fine。Any other ones？

Are you just stalling so that we don't get to the next topic？Okay。

 it is a tricky exploit and we'll take a little bit of looking at。

 so don't worry if it doesn't make all the sense right away。Did you have one more question？



![](img/97c5213c872df8788eb33fdfcea9b452_1.png)

でた memory。でもみ。経在。Yeah， that's a great question about why these addresses don't change if you stick around for like。

One more week， you'll get the answer to that。 so stay tuned。It's a good question though For now。

 we're assuming they're the same。 If you stick around for a week， we'll switch them up。


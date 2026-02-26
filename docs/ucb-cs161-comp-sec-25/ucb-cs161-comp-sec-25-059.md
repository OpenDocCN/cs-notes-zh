# 059：-MemSafety3, Video 20- Summary.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/3e21ebb7fa197dc8e8f29b1bee3ba134_0.png)

Okay so to summarize all we've seen about memory safety vulnerabilities in this set of videos。

 we showed you format string vulnerabilities and the idea there was that if you pass a mismatched number of arguments to printf。

 printf goes on the stack anyway to look for arguments and that can be dangerous it can cause things to get leaked on the stack that should not have been printed out and if you use that clever little percent and formatter which goes on the stack takes the next value。

 read it like an address goes to that address and writes the number of bytes printed so far you can actually get any value and memory that you want and that's very dangerous so we have to be really careful about format string vulnerabilities。

 make sure that the user doesn't control that all important zeroth argument to print。

And we also saw the off by one vulnerability which I guess is not on the slide oops。

 but pretend like the off by one vulnerability is here and that was a case where if you overwrite just one single byte of the SFP you can trick the program into thinking that the RIP of not the current function but the previous function is in a different place and when you trick the program into thinking the RIP of the previous function is in a different place。

 you can write your own RIP value at that place and that will cause the program to execute shellcut and we also saw that you can make robust exploits robust by adding little tricks like nooplets that increase the probability of success even if you don't have perfect information about the system that you're trying to exploit so these are really dangerous sets of vulnerabilities if your code has a memory safety vulnerability you really just have to assume that it's toast and the attacker can do whatever they want because they're so powerful even if the attacker only overwrites a single byte they could take。

Con of your system。 So these are very dangerous， and we have to watch out for them。


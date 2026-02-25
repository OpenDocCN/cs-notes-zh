# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P100：-Cryptography2, Video 9- Summary.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

But before I talk about Block Saford chaining modes。

 let me quickly summarize Block Saers and how they work。A block cipher is a function。

 It's a piece of code， but it's good to think about it as a bunch of permutations mapping nbit plain texts to embit cipher texts。

 There's a lot of these mappings。 there's one table for every possible key and once you pick a K bit key you are locking in and committing to using one of those tables that maps each input to a unique output in order for this scheme to be correct the mapping must be bijective every input must map to exactly one output if you have two inputs mapping to the same output。

 you can't decrypt it uniquely for security。 we said that block cpher should be computationally indistinguishable from random and what that means is an attacker with two boxes one with arrows generated from a block cipher with unknown key K and one with totally randomly drawn arrows is indistinguishable。

 The attacker does not know which boxes which and that's what makes a block cipher secure and we saw that brute force attacks take astronomically long。

 Don't even try them。😊，They're efficient because they use a bunch of xOs and bit shifting which computers like to do。

 and we implement them using AES， which is the modern standard algorithm。

 But the reason why we can't stop here is because even though they have this security property indistinguishable from random permutation。

 they don't have the security property we want， which is in CPA security so we have to fix that and we have to fix the fact that it encrypts only endbit messages。

 so now that you have block ciphers down， it's time to use them to build something even better。


# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P115：-Cryptography4, Video 2- Hash Security - One-way-ness.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， here are the security properties of a hash function more formally。

 So this is a little math ape， but I'll tell you all about it in English too。

 So one of the properties you want is something called one wayness or sometimes people say the hash is one way。

 So this is what it read like it says if I give you an output why it is hard for you to find an input X such that the input hashes to the given output。

 That's a little wordy。 So maybe another way of thinking of it is like this。

 It's kind of like a challenge。 So I take any input that I want。 I don't tell you what it is。

 So I turn around。 I pick some random input word。 I put it into the hash， and I get an output。

 And then I send the output to you。 the audience。 And I ask you， here's an output。

 I'm not telling you what input I use to get the output。 It doesn't matter。

 Can you tell me any input that hashes to the output that I gave you。

 So your challenge is to find any input such that if I pass it through the hash function。

It results in the output that I gave to you You could pick the same input that I chose where I turned around and I picked a word。

 If you pick the same word as me， that's great。 If you pick a different word from me and it hashees to the same output。

 that's okay too。 So the reason why the definition is a little bit complicated because you don't have to just use my input if you choose some other input that generates the same hash you also win So sometimes people think about this like the hash can't be reversed。

 So if I give you the output it's hard to find the input but we have to be a little bit careful because multiple inputs might work。

 So it's not enough just to say I can't reverse the hash and get the original input more formally it's that if I give you an output。

 you win if you tell me the input that I use to get the hash but you also win if you pick a different input any input that produces the same output is a winner for the attacker So that's the intuition I think about it's a challenge where you get a value and you have to pick an input that produces that。

Value more formally， you can define it like this in math， but I'm not going to read it out loud。

 I think this intuition gives you what you need。So here's an example of a hash function that is not one way this hash function says whatever input you provide just output 42。

 it's a constant number， whatever document you feed in as the input， the output is always 42。

So to play the challenge， what I would do is I would turn around without telling you and I would pick a random word。

 so I've picked some random word for X， you don't know what I've chosen， I have hashed it。

 I did the math， I turn around and I tell you whatever mystery input I chose， the output is 42。Now。

 you know。So now the question for you and the challenge for you is。

 can you find any input X that hashees to the same output that I provided， which is 42？

So what input could you provide that outputs 42？It could be the one that I chose。

 or it could be the one that you choose that doesn't match mine。

Literally anything would work right because everything hashees to 42 so you could choose potato or any other word you feel like it could match the one that I used。

 it doesn't have to match the one that I used as because you were able to choose an input X that mapped to the same output that I provided you win this game and because the attacker is winning that means that the scheme is not one way So if the attacker is able to solve this challenge the scheme is not one way and if the attacker is unable to solve this challenge then we say that the scheme is one way so to make a long story short。

 people sometimes think about this like the hash can't be reversed given an output it's hard to find the corresponding input but more formally because multiple inputs might work。

 you just have to pick any of the inputs for the attacker to win as long as it matches the chosen output。


# 090：-Cryptography1, Video 13- History - Enigma Machine.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay fast forwarding a little bit。 So we went from 2000 years ago to the 1940s。

 This was used in World War I。 It's called the Enigma machine。

 It's a very interesting story if I had time I would tell it to you。

 but the short version of it is the Germans created this machine and they wanted it to be an unbreakable code。

 So now we've gone from substitution ciphers and things that you can solve by hand to cryptography that uses actual machines and in this case it's an actual physical machine that they built to try and build an unbreakable code and what you would do is you'd like press one of these buttons corresponding to the letter you want to encrypt and then one of the lights would light up telling you what the corresponding ciphertext letter is so you might press a and then C lights up and that tells you that a maps to C and what's really interesting is that there's these little rotor city here and every time you press a button the rotor turns a little bit。

 And so what that means is that if you press the button the same time over and over again it doesn't always map to the same letter。

It's not like this algorithm， where if you encrypt DDD， you get ZZZ。On this machine。

 if you press D 10 times， you might get all sorts of different letters because the setting is changing every single time。

Also， that later in the war， they actually upgraded it and they have this big old plug board where you have to plug in letters。

 mapping to other letters。 So what this would do is it would， for example。

 swap the A and the C or something。 not the most important thing here。

 Just know that this is a machine that is trying to implement cryptography and。That's what I did。

So how do you generate a key， you have to set these rotors to the right setting。

 you have to say where they start， you have to plug in all of these wires on the plugboard。

 and it turns out if you do that， you get a really big number in terms of possible keys。

 so anyone trying to bru this is not going to finish it before the world explodes。

And how do you encrypt， you press buttons on the key and the lights light up the corresponding Cyphertex letter。

 and if you decrypt， you actually do the same thing。

 you just press a key and the corresponding letter lights up。So this is what they designed。

 it was a machine version of our code， and we can still use our encryption and decryption schemes to describe it。

But what's really interesting is how they broke it。

 So turns out Ser alert this thing was broken despite Germans thinking it was unbreakable。

 and here are some of the strategies that they used。

 and some of them are relevant to the definitions that we talked about So one thing that the Germans relied on to try and make this thing unbreakable was the fact that the allies don't even know what this machine looks like。

 They don't know that there are rotors and a plugboard。

 So if they don't even know what the machine looks like。

 how are they going to even start breaking this algorithm。

 that was a critical mistake because they broke Krkov's principle。

 The only thing that should be secret is the key， not the algorithm itself。

 and why is that principle there， Because guess what happened。

 Some people left the machines lying around the allies pick them up Now they have a copy of the machine and they know how it works。

 They could disassemble it and learn how it works。 So they relied on security through obscurity。

 They tried to hide the algorithm and that was a mistake。

should have only relied on the key to be secure。 That was mistake number one。

 A second mistake is there were some known plain text attacks。

 So what this means is sometimes the messages were predictable。 So for example。

 every morning they sent like the weather report and we all knew that they were sending the weather report so we could take the cipher text and map it to a weather report for the day even though we didn't know how to decrypt it。

 but even more interesting and this is a definition that we care about is you can actually do chosen plain text attacks on the Germans。

 So what you could do， for example， is you could go to one of their spies you could tell them hey。

 there's a minefield right here。And then what would they do， They would go into a nima。

 They would type the location of the minefield and send the message。 So basically。

 what you have done is you've tricked them into sending a message of your choice。

 So if you think that chosen plaint attack isn't a realistic threat model。

 it turns out it kind of is。 Here's an example where you can trick someone else into encrypting a message of your choice。

And the final tool that they used to break this thing and there were others too。

 but the final one that we're talking about here is just brutefor。

 something that they weren't expecting is that the Allies would build these enormous machines and these are actually the rotors。

 remember the rotors on these machines。 they basically built that。

 but they built a lot of them to try all these different combinations at the same time。

 and with enough work they were able to start breaking down this algorithm and decpt messages。

 So the moral of the story beyond the definitions is that this is an example of cryptography having real worldor impact。

 Some people believe that breaking enigma actually shortened the war and saved a lot of lives。

 And one of the people who built it is Alan Turing who is a big name in computer science。

 and this is one of the things that he made his name on so。

Don't really care if you know the exact Enigma story， although it's kind of fascinating。

 but it is kind of interesting that some of the things that made it vulnerable are things that we care about defending against。

 such as Krkoff principle and the chosen Pla text attack。


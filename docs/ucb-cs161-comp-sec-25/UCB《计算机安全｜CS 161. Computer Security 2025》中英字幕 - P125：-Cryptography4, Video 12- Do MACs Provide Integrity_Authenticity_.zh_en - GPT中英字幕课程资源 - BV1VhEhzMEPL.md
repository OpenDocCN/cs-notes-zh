# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P125：-Cryptography4, Video 12- Do MACs Provide Integrity_Authenticity_.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

O。Now we can finally answer the million dollar question from before， which is。

 did we do the thing we wanted to， did we provide integrity。

 So under the model that we've been talking about， where Alice and Bob exchange messages and Mallory taamppers with them。

 we can finally say yes， Max do provide integrity， if Mallory tries to tamper with the message。

 Bob is not going to verify successfully， and he will know that the message is taampered。

 So if Maory taamppers with the message， Bob will not successfully verify if mallllory taamppers with the tag。

 Bob will also not successfully verify， So that's great。

 We' have provided integrity in the threat model that we talked about。😊，What about authenticity？😡。

And remember， authenticity means you know that the message came from the original sender。 Well。

 it kind of depends on your model and who's talking。

 So if you receive a message and a tag and you check the message with the tag and it's valid。

 What can you conclude。 Well remember， the Mac is a function on the key and the message and it outputs a tag。

 So if I get the same tag and it checks out， that tells me that someone with K must have run the Mac algorithm to output the tag。

 So I know that someone with K must have generated this tag。

 But I can't really narrow it down to one specific person。 So， for example。

 if 10 different people all share the same secret key K and I receive a message with a Mac using that key K。

 I know that one of those 10 people sent it。 But I don't really know which of those 10 sent it。

 So depending on your definition in your model， you might say。

Max don't provide authenticity in that case because you don't know which of those 10 people sent it。

By contrast， in the model where only Alice and Bob have the secret key。

 you could argue that Maxs provide authenticity。You receive the message and you check the Mac and it's valid。

 so it must be from someone with the secret key。 Well there's only two people with the secret key and the message isn't from me。

 so it must be from that other person like Alice So that's a case where Mac do provide authenticity if there's only two people with the secret key and you receive a message Well I didn't write this message So Alice must have written it and that's authenticity。

 It guarantees that the original sender was Alice and I can prove that the person who sent it must be Alice So whether Max provide authenticity is kind of a fuzzy question and it depends on things like how many people have the secret key and whether you want to know if the message came from a specific person or a group there are all these different questions but ultimately it's a little bit fuzzy but it definitely provides integrity。

 Aters can't tamper without knowing the key。And one final point is whether Max provide confidentiality。

 Well remember in our crypttography roadmap where we have that two by two table。

 we set that max are built to provide integrity。 In fact。

 we didn't build them for confidentiality at all。 Some ways you can show that Max don't provide confidentiality。

 One thing is we use no randomness at all。 So we've already said if something is deterministic。

 there is no ID CPPA security。 If you send a message twice and it has the same tag。

 people can deduce that you're sending two messages with the same tag。

 and therefore you must be sending the same message。 So Max don't provide inD CPPA security。

 And in fact， it's not really even clear how you'd use max in the IDCPA game。

 there is no decryption function you can use to undo a Mac。 So the definitions kind of fall apart。

 Max were not designed for confidentiality。 We were never thinking about the IND CPPA game or trying to conceal messages from the attacker at all。

😊，Provide integrity。 They might provide authenticity， depending on your definition。

 and they definitely don't provide confidentiality。 That was never one of our goals。

 So this also means that in general， any Mac that you use。

 whether it's H Mac or some other type of Mac that you design。

 It's okay if they leak information about the message。

 because at no point did we require that Macs don't leak information about the message。

So that's something to be careful about if you use a Mac。

 you don't get confidentiality because that's not what it was designed for， and in general。

 when you compute the Mac on a message， that resulting tag could have information about the message that an attacker can learn。

 so you have to be careful。
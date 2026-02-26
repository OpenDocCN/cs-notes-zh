# 127：-Cryptography4, Video 14- Encrypt-then-MAC is Better.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

So these schemes actually have names and the names are kind of what you'd expect one of them is called encrypt then Mac because you encrypt and then you Mac and you send both the encryption and the Mac of the cipher textex that was the first idea that we saw The second idea is called Mac then encrypt because we first compute the Mac and then we shove both the Mac and the message into the encryption so one of them is Mac then encrypt one of them is encrypt the Mac I always forget which is which but thinking about the steps that is telling you can be helpful。

😊，So one question you might have now is which one is better we've already shown that if you use them correctly。

 both of them give you IND CPPA confidentiality and EUuc CPPA integrity but there is one very subtle flaw in Mac then encrypt and the very subtle flaw is that you first have to decrypt before you can detect tampering so if we look at the way that you would process the message if you're bo and you receive it in the encrypt and Mac case you first check the Mac so if something is taampered you check the Mac。

 it's no good and you stop right away by contrast in the Mac then encrypt scheme。

Everything you get is encrypted so the very first thing you have to do is decrypt this message to get the original message and the Mac and only after decrypting can you then compute if the Mac is correct So when encrypt and Mac you check integrity first in Mac then encryptpt you have to decrypt before you can check integrity and there are very subtle flaws associated with the fact that you have to decrypt first in particular the attacker can give any arbitrary value to Bob and Bob is forced to decrypt it。

Because he doesn't know if this is correct until he has done the decryption。

 So if you use Mac that encryptpt， you're basically creating a character Bob who will decrypt anything you give to him。

 So if I give Bob some garbage value， Bob is forced to first decrypt it and only then can youche the Mac and realize oh。

 this is invalid I'll throw it away。 So you've basically created someone in one of our threat models。

 this is Bob and you can trick him into decrypting any value of your choice。

 Now it's true that in general， Bob is not going to decrypt it and then give the value back to you。

 but maybe there are some leaks， maybe somehow Bob is leaking information about the decryption or the time that it takes him to decrypt leak some information about the message So we have to be really careful because creating this decryption oracle and that's what you call Bob who's decrypting anything you provide。

 you call him a decryption oracle because you can pass him whatever you want and he will decrypt it。

Providing this decryption oracle is dangerous because Bob could potentially leak information about the decryption or the key that you're using to decrypt so we don't like Mac that encrypt because it creates a character Bob who will decrypt anything you give to him and only after he decrypts can he detect that something has been tampered with。

 So in summary， we always prefer encrypt then Mac， because this doesn't open us up to the same problem。

 Bob immediately checks the Mac and if it's wrong， he doesn't do any decryption at all。

 so we don't have a decryption oracle who is potentially leaking data and decrypting anything that the attacker provides to him。

So at least for our purposes， we're always going to suggest encrypt than Mac because it's more robust to mistakes if you mess up and Bob is leaking information。

 you would much prefer this first case than the second case。

 because in the second case Bob is becoming a decryption oracle and leaking information about decryption。

 so that's our argument about why encrypted Mac is the better approach。


# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p119 53_05_05_未知密钥长度.zh_en -BV18U411U729_p119-

Now， you've written the code to break visionire if you know the key length。

 But what do you do if you don't know the key length， Well。

 you could just try some different key length。 You could use the code you just wrote and pass it a key length。

 then see what the result is。 Maybe the key length is one。HThat output is incomprehensible。

 One is probably not the correct key length。What if you try to？H。

 that doesn't seem to be right either。 How about 3。Oh， hey。

 this output looks like it could be English。 It has readable words。

It would seem this message was encrypted with a key length of three。

You could write a loop to try many different key length， Start at one and count up from there。

 The computer can try one particular key length in a fraction of a second。

 So even if a message which is thousands of lines long， is encrypted with a key length of 92。

 the program can do it in no time。But how do you tell if the key length is right。

 Do you really want to look at the output for each iteration to say。That's what we did a moment ago。

 looked at the output to see if it was meaningful text。

But maybe if we think carefully about what we just did， we can find a way to automate it。

As you look at the incorrect decryption here， think about how you knew it was not right。

 This group of three letters forms a word， but J。 O。 W is not a real word。 Likewise。

 Y T isn't a real word， nor is Y， O B， None of the words in this message are actual English words。

Contrast that with the correct decryption。 H O W is the word how D O is do， and Y O U is you。

 All of the words in the correct decryption are actual words。

This observation leads to the idea of how to figure out which key length is right。

 Count the number of real words in the output。 You would start by reading a list of English words from a file。

 You could store the list of words in an array list。

 but we are going to recommend that you use a hashet， which will give you the same functionality。

 but work much faster。Then you try the decryption for various key length。 Start at one and count up。

 Where do you end， Well， you could just count up to the message length。

 Although if the key is close to the length of the message。

 you won't be able to break it because there won't be enough letters to meaningfully frequency count for this mini project。

 just count up to 100。Then for each key length you try。

 see how many of the words in the decrypted text are actual words from the file you read in。

Once you have done that， choose the key length， key and decrypted text。

 which give you the most real words。As we just mentioned， using an array list would work just fine。

 As you read in the file， you would use the dot add method to put each word in the list。

 When you want to see if a potential word is actually a real word from the list。

 You would use the dot contains method。 A better option is to use the hashet class。

 like array list and hashmap， you can use a hashet containing different types of data。

 so you need to put string in angle brackets after hashet。 you want a hashet of strings。

For this problem， you will use the hashet in much the same way as you would an array list。

 You can call dot add and dot contains on it。 You cannot index into a hashet like you can an array list。

 but if you wanted to iterate over one， you could do that with a for each loop。

 That is what has been happening behind the scenes when you iterate over a hash maps dot keyset。

The main advantage is that dot contains will be much faster instead of searching through every word in the hashet。

It can look at only a few words to figure out if it contains the requested information or not。

 The last thing that we will mention before you start coding is how to split a string up into individual words。

 You have already seen that string has a dot split method。 You can use that。

 passing in backlash back slash capital W。 This asks the split method to divide the string up at every character that is not part of a word。

 spaces punctuation or numbers。 Once you have done that。

 you can iterate over those words with a for each loop like this one。



![](img/f1c9381cecec2ea16453817bd6208b46_1.png)

![](img/f1c9381cecec2ea16453817bd6208b46_2.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p34 34_02_04_凯撒密码解密技术揭秘.zh_en -BV11y411z7Dn_p34-

![](img/e2370a251ff4d426a5ac2cdaaee36d9d_0.png)

Alright， join me on a journey here to the clandestine world of secret messages。

 I'm going to be your guide as we encrypt a plain text message and then render it unreadable to people that want to intercept it。

 But don't worry the secret shift value is very clear here and I can reverse the cipher and reveal the original text again。

 So what we're going to do is look at the encrypt function because it's what performs the mysterious art of substitution and it's going to shift each letter to hide the content and the result is going to be incomprehensible without knowledge of cipher。

 So let's go ahead and take a look at how this works。

 So first up here we have the use Caesar cipher decrypt。

 use Caesar cipher encryptrypt let's go to the lib directory。

 which is a commonplace in rust for you to build out your law。Mic。

And this thing here has an encrypt and it's pretty simple。

 It takes some text and it takes a shift value。 So all the shift is is what is going to be the letter substitute right So if you started with A and you shifted to two letters。

 you would be C。 and if it would be3 would be D。 So in this case what we're going to do is we're going to take in the string。

 we're going to say for all of the characters in the text， you do a little bit of pre-processing。

 lowercase it， but basically shift it according to whatever shift value is here。Likewise， to decrypt。

 you just shift it back into the other direction。 Now， if we go to the main function here。

 we can see how it works。 in action is there is a plain text value that's hard coded in here。

 There's a shift value that's hard coded， and then you are able to both encryptpt it and decrypt it。

 according to this Caesar cipher。 So let's go ahead and Cd into this directory first。

 Im to go into the Caesar cipher directory type in cargo run。Now。

 we can see here that the quick brown fox jumps over the lazy dog。 It has been shifted， right。

 So if we know that there's three different。Letters difference is going to be T U。VW， right。

 And so we can see here that you could， in theory， do this by hand if you knew what the shift value was and fairly quickly。

 you know， undecipher， or remove the complexity of what's happening inside of the original Caesar cipher。

 But in this case， if we decrypt it again， you can see what the value is。

 So this is a great proof of concept to start to dive into ciphers。 And， of course， with rust。

 it's pretty straightforward to build these things here， just a little bit of code。

 And this is a good example that I would recommend to play around with。



![](img/e2370a251ff4d426a5ac2cdaaee36d9d_2.png)
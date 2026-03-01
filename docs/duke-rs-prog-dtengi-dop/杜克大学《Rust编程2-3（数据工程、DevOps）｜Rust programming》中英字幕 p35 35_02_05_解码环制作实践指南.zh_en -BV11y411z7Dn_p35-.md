# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p35 35_02_05_解码环制作实践指南.zh_en -BV11y411z7Dn_p35-

![](img/813d363b8042060c933a2f2c90b55f8e_0.png)

Here we have a Caesar cipher， which is one of the simplest encryption techniques that you can use because it only shifts the alphabet letters by a set number to encode a message。

 So in this particular scenario， what I've done is I built this all into a tool that allows you to not only create the cipher and encrypt the cipher。

 but also to use statistical analysis to detect what the cipher probably is。

 So if you can figure out what the shift most likely is。 and you can come up with。

 let's say some kind of a metric that looks at the highest probability for what the shift is then you could actually detect what the message is。

 and you could even think of this as a technique you could use if it was a big data problem。

 For example， and a lot of the data was using this Caesar cipher before you tried every single approach with a brute force。

 you could actually sample it like I'm doing in this particular example。

 So if we take a look at this， we can see。Here that there's a shift here of 10 in this particular example and I can go through and try to guess exactly what's happening and it'll give me different scores。

 So in this one it'll say shift 0， shift1， shift etc cetera， etctera。

 and you can see here that there's two that are are pretty close here and there's another one。

 shift 11。And if we keep going down， though， even further， shift 16 has got a tremendous score。

 which is a score of 40。 so most likely based on this statistical guess of the frequency of the letters。

 that shift 16 is going to be the one that's used and if we go back up here。

 you can see here that you can actually try that out so。

Here we're going to tie it all together first I use Camilan tool library which is the parser and then I go through and I print the analysis and then I pull together different items like the message right is a key component。

 the stats here， statistical information about the message and then guessing the shift and then you at the very end here。

 pull this all together into some code now if we look at the lib。

 this is where a lot of the magic happens here is that I have a hashmap。

And I store the initial frequencies of letters。If you look at 80% of the letters in English。

 they're going to have。You know， this particular makeup so E would be 12。7 T would be 9。

1 A would be 8。2， et cetera， et cetera。 And then if we go down here。

 we could actually come up with a statistical analysis so we could look through what's going on in the code。

And essentially map out the probabilities。 And then finally。

 we could print out the statistical analysis inside。 and that's what this function actually does。

 Finally， if we want to decrypt it， we would just then pass it in to this particular function here。

 So really， that's the genesis of everything that's happening and then if we want to guess the the shift here。

 What we would do is we would use a statistical analysis to determine the likely shift and then we would actually return back what most likely is the decrypted message because it would pick the highest score。

 So here we can see how all that works and then we return back a guess shift。

 So this is like a secret decoder ring that is going to do its best to guess what's happening。

 So in order to use it。All I need to do here is go ahead and do cargo run。

 and then if I do dash and then dash help， I can get some feedback of exactly what's happening。

When we first start off here， it's going to say， okay， CLI tool to reverse engineer a Caesar cipher。

 okay， great， so let's go ahead and do a message。And we can say， you know， for example。

The message would be hello。And then we would put in in this particular example here。

What some kind of statistic if we wanted to， we could do， you know， dash stats。And it would say。

 you know， the frequency。 Now， because I want to work on something that's already encrypted。

 let's go ahead and go back to， you know， here and let's figure out a message like this。

And let's just put this message in into our our tool so we can actually even put it all together and make it easier。

And， and go to a guess。And we can see here that。It's going to run through the tool and it's going to look through every one of the different scores that's generated and it found that the highest score is 16 so it's going to try to do 16 and it's going to say decrypted message which is off to the bunker every person for themselves。

 So really this is a great way to trout different ideas with cipher's encryption is to put it into command tool and also we know that one of the weaknesses of a cipher is the fact that it's vulnerable to this frequency attack right so we know that if you analyze the letters in a cipher for frequency that one of the giveaways is that the letter E is used 12% of the time。

 12。7% of time。 So you know that you can start to do these guesses and then actually calculate what the score is and then that's really the way to essentially decode the message using statistics。

 So kind of a fun exercise to play。Around with， and it was all made possible by the elegance of the Ru language。



![](img/813d363b8042060c933a2f2c90b55f8e_2.png)
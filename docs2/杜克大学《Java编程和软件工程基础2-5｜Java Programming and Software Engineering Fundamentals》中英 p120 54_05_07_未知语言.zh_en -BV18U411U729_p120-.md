# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p120 54_05_07_未知语言.zh_en -BV18U411U729_p120-

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_0.png)

O， great。 Now you have cracked visionre for English messages of unknown key length。

 But what if the messages were in other languages， What if you did not know the language， Well。

 you can use the same techniques and just try each language for each potential language。

 you would need a list of words in that language and to know the most common character。

 which is not E for all languages。😊。

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_2.png)

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_3.png)

Then you can try breaking the cipher for each language。

 You would use the same code you already wrote to find the key length that gives you the most real words in each language。

This gives you the best choice for that particular language。

 then you just see which language results in the most real words。

 that is which languages best decryption is best overall。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_5.png)

To do this， you're going to read the words in for each language。

 You can make use of the read dictionary method that you already wrote。As you read each dictionary。

 you will want to put it into a hashm whose keys are strings and whose values are hashets of strings。

 in particular， the key is the name of the language and the value is the dictionary that you read in with Read dictionary。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_7.png)

Such a hash mapap would conceptually look like this here。

Here you have a table where the keys are the names of languages。

 The values are then the sets of words in each language。

You might think that this type looks a little complex。

 You have multiple sets of angle brackets nested together。 However。

 it is a great example of an important programming principle。

 Do you remember the idea of composition。If you took our course programming in the Web for beginners。

 you learned about it in the context of HTML。 the idea that programming languages allow you to put small pieces together to make larger pieces and that they obey the same rules when you put them together。

This principle lets you make and understand large and complex things。 In this case。

 you can understand this complicated looking type by understanding the pieces。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_9.png)

So what exactly do you need to make your visionre breaker work for unknown languages？

You need to write two new methods， one that counts the most common character and hash set of strings。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_11.png)

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_12.png)

And one that tries the different languages。You also need to modify two old methods。

The B visionre method， which is what you run from Blue Jay。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_14.png)

And the break for language method。You need to write the most common car in method to account for the fact that E is not the most common letter in all languages。

So you will count the frequency of each letter in the hash set of strings。

 which is the list of words for that language。

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_16.png)

You have seen and done many problems with counting how often you find something。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_18.png)

And figuring out which of something occurs most often。

 So hopefully you are getting proficient in these skills by now。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_20.png)

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_21.png)

The other new method will try each language in the keyet of the hashmap language。

You will want to use breakak for language to do the work of trying to break that one particular language。

You will want to use dot get to get the word list out of the hash map to pass into breakak for language。

 You will then want to see how many words you ended up with in the string that break for language returns。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_23.png)

Fortunately， you already wrote a method that does that。You will then want to pick the best language。

 the one with the most words and its decryption。Print them out so that you know what your program found。

You will want to make a few changes to break visionre， the method that you call from Blue Jay。

Instead of just reading one language's word list， you'll want to read many of them。

The other change is that you will want this method to call break for all Ls instead of break for language so that it tries all the language all of the languages that you read in。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_25.png)

You will also want to make one small change to break for language。

Up to now you have just passed in E as the most common letter。 However。

 now you will want to use the most common carin method that you just wrote to find the most common letter in the word list and pass that into try key length。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_27.png)

![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_28.png)

So now that you know the plan， it's time for you to devise your algorithms and write your code。



![](img/55e66fb5c0d9077f03c8cfcb3dbc9381_30.png)
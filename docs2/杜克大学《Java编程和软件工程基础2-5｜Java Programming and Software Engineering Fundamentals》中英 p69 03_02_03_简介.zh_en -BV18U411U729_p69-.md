# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p69 03_02_03_简介.zh_en -BV18U411U729_p69-

![](img/db71ead024e75e7e1adf0489ca3a8da8_0.png)

Welcome back。 Now that you know a bit about the importance of cryptography。

 it is time for you to learn a bit more about the concepts of the Caesar cipher。

 which you will implement in this lesson。Suppose you were in a battle and you wanted to send a message to your sub commanders to tell the first legion to attack the East flank。

You don't want your enemies to know your plan， even if they intercept this message。

 So you encrypt it with your cipher， as shown on the second line。

The Caesar cipher algorithm is named for Jous Caesar， the famous Roman emperor who used it。



![](img/db71ead024e75e7e1adf0489ca3a8da8_2.png)

The basic idea of this algorithm is to substitute each letter with the letter obtained by shifting the alphabet by a fixed amount。

That is a specific number of letters later in the alphabet。

The amount you shift the alphabet by is the key for this cipher。

Julia Caesar used a shift of three letters prior。Which if you think of the algorithm in terms of shifting to a later letter would be the same as 23 letters later。

To see how this algorithm works， we'll walk through an example of encrypting this message。

 We'll use the alphabet to show how letters are encrypted。The first letter of the message is F。

We find the letter F in the alphabet here， and then we go backwards  three letters， E D C。

 So you would write down a C as the first letter of your message。The next letter is I。

 We find the letter I in the alphabet here， and then we go backwards。3 letters， H G， F。

 writing down F as the next letter of the message。The next letter is R。

 We find the letter R in the alphabet here again， go backwards3 letters。 Q， P， O。

 writingt down O is the next letter of the message。

 You would continue the same way through the first word。 And then you would get to a space。

 doing this by hand as Caesar would have done。 The easiest thing to do is leave the space unchanged and write down a space in your message。

The next word in space proceed in the same way。 However， what happens when you get to a。

 we find a here。 It is the first letter in the alphabet。 But how do you go three letters backwards。

You have to wrap around to the end of the alphabet。 from there， you go three letters backwards to Z。

 Y X， writing down X as the next letter。You continue through the rest of the message in the same way and end up with something that is unintelligible under casual scrutiny。

However。If you know or or can figure out the key， you can decrypt the message。

 The process is the same as encrypting with a key of 26 minus n。

So how do you actually do this One way is to do math on the numbers If you took our Coursera course。

 programming and the web for beginners， you should remember that everything is a number。

If you're not familiar with this concept， it is very important in computer science。

 as computers can only work with numbers。 In this case。

 that principle says that these letters are actually represented as numbers。

 so you can do math on them。In particular， you could tell Java to subtract 3 from the letter F。

 and it would compute the letter C。 However， what if you subtracted 3 from the letter A。



![](img/db71ead024e75e7e1adf0489ca3a8da8_4.png)

Java would not know that you want to wrap around and stay only within the alphabet。

 so you would have to include some more mathematical operations or a conditional statement to wrap around and get X。

Another way you could do this， which makes the wraparound case a bit cleaner。

 is to preshift the entire alphabet。That is， compute the shift of each letter at the start before you try to encrypt anything in the message。

 For example， you could take the alphabet And for a shift of three to the left。

 compute a string like this one。We will see the details of how to do this in a future video。However。

 once you have computed these strings， you can use them to look up the encryption of each letter。

For the F at the start of the message， you want to find F in the original alphabet。

 Think for a moment about what you have learned about strings in the past。

 What method might you use to find F。Once you have found F。

 you look at the letter in the same position in the shifted alphabet， which is C。

Then you write down that letter in your encrypted message。For a， which wraps around the X。

 you do not have any special case。 Again， you just find a the original alphabet。

 Look at the letter in the same position in the shifted alphabet。 In this case， that letter X。

 So you write down X in your encrypted message。Great， now。

 you know the basic ideas behind a Caesar cipher。 However， before you implement this algorithm。

 you will need to learn a few new Java concepts。You're going to learn some new ways to manipulate strings。

 as well as for loops， which count over a range of numbers。

Four loops which count over ranges of numbers are particularly important。

 as you will use the numbers you count to to index into data。

Manipulating particular locations in a sequence。 You are familiar with strings。

 which are sequences of characters， but willll learn about the new types of sequences in the rest of this course。

 So you will use four loops a lot。

![](img/db71ead024e75e7e1adf0489ca3a8da8_6.png)

Thank you。😊。
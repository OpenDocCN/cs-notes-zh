# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p73 07_02_07_算法开发.zh_en -BV18U411U729_p73-

Welcome back。 Now， you have all the concepts required to implement a Caesar cipher。

 So let's get started developing the algorithm。 As always， you should start with step 1。

 working an instance of the problem yourself。Even though we have seen some instances worked。

 it is good to work a small instance so you can write everything down and think it through。

Let's encrypt the message I am， which is really I space A M with a key of 17。

 meaning you will shift each letter 17 positions through the alphabet。

You might want to start by writing down the alphabet。

And then running down the alphabet shifted by 17 characters underneath it。 For example。

 a has R beneath it， where R is 17 characters to the right of a in the original alphabet。Next。

 she would go through and replace each character in the message with the appropriate letter from the shifted alphabet。

When you are done， you have the encrypted message， Z space RD。Great， you have finished step one。

Now it is time to do step two and write down exactly what you just did。

The first thing you did was write down the alphabet。 Then you computed the shifted alphabet。

The third thing you did was to look at the zeroth letter of the message。 Don't forget。

 when you index into sequences such as strings and string builders， the first element is at index 0。

That letter was I。 So you looked in the alphabet to find I。

 Then you found the letter in the shifted alphabet at the same position， which was Z。

So you replace the zeroth character of the message with C。Next。

 you looked at the first letter of the message， which is a space。

If you looked for space in the outfit， you would not find it。

 so you would not change the character to index one of the message。Next。

 the second character is an A for which you perform a very similar process。

 as you did for the zeroth character and end up changing it to R。Finally。

 you do the same thing for the third character， which is an M that you turned into a deep。

Now that you have thought through all of that， you have a list of the 17 things you did for this particular message and this particular key。

 However， there is one more thing that is good to note here before you proceed。

Notice that your algorithm calls for replacing characters in the message。If your message is a string。

 you cannot do that。 As you recently learned， strings are immutable， meaning you cannot change them。

If you recognize this issue now， you can adjust your algorithm to reflect the fact that you want to work with a string builder here。

 we've added a step at the start to create a string builder from the string message。

And then we updated the algorithm to work on the strain builder。

If you do not realize you need to do this now， you would figure it out at a later step。

But the earlier you can figure it out everything you need to do， the better。

Looking at this algorithm， you can see that the first few steps are an initial setup before you begin performing repetitive steps for each letter in the message。

If you focus on the steps after the initial setup， you can see that you are doing almost but not quite the same thing for each character in the message。

One significant difference is what you decide to do based on whether or not you find the letter in the alphabet。

Replacing the current character if you find it。Or doing nothing if you do not。

If you look at the steps for one particular character where the letter is in the alphabet。

 you will notice that the character you looked for in the alphabet is the current character in the string and that the letter you use to replace the current character is what you found in the same position in the shifted alphabet。



![](img/1ca813dc9caac4b6c74f060fcd62d942_1.png)

Now that you have thought this all through， you can write down。A much more general algorithm。

Notice that the step number two here requires a little thought and a couple of statements。

But you have already seen how to do it。When you are looking for patterns。

 you should examine any constants， such as zero here and ask if you always use that constant。

 or if you need to look for a more general pattern。Here you always want to start from zero。

What about three， do you always want to count or do you always want to stop counting at three？No。

 how high you count depends on the length of the message Here we've written that you want to count to the length of encrypted。

 but noted that you want to count to less than it， not less than or equal to it。 In our example。

 encrypted was 4， and you only want to count to 3。Now is time to test out the steps。

 pause the video now and try to encrypt the message a space bat with the key of 19。

Did you catch the subtle problem with this algorithm， Even though it computed everything you wanted。

 we never said what the final answer is。You want to be sure to explicitly say this so that you know what to return from your method when you translate to code。

Your answer is the string inside of the string builder you called encryptrypted。

Now that you fix this detail of your algorithm， you are ready to turn it into Java code， Thank you。



![](img/1ca813dc9caac4b6c74f060fcd62d942_3.png)
# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P15：-16-random - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/d599875aee7f49738a513fca7cd6b5ba_0.png)

Well hello one and all and welcome to our short on the random module Now the random module is a module you can use at an element of randomness or chance to your programs and we'll see here I have a program called cards。

 Pi which I've created much I think code cards。 pi and adding in these lines of code on lines 1，3。

4 and7 down here so the goal of cards。 pi is to simulate kind of dealing from this deck of cards that I have here in the form of this list one called cards with three cards。

 Jack Queen and King。

![](img/d599875aee7f49738a513fca7cd6b5ba_2.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_3.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_4.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_5.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_6.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_7.png)

But if I want to deal cards， I think of this element of randomness。

 shuffling the cards and dealing them and seeing what cards I get and to get someone randomness whileing to use the random module so I can import it up top using import。

😊。

![](img/d599875aee7f49738a513fca7cd6b5ba_9.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_10.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_11.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_12.png)

Import random just like this。 And then down below， I can see a few ways to use the random module with a few functions that are built into it。

 Now one we've seen is the choice function， which I can get access to by calling random dot choice。



![](img/d599875aee7f49738a513fca7cd6b5ba_14.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_15.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_16.png)

And dot choice here， this function takes as input some list and returns to me some random element from that list so I think I could give as input here cards。

 my list， my deck of cards here and have it choose for me one card randomly from this deck of three I could then print the result just like this if I go down below and type Python of cards do pi but we'll see I got back queen from random dot choice just to prove this is a bit random here。

 I'll do Python of cards do pi and I get queen again by chance。

 but let's keep trying I'll get queen again， I'll do Python of cards do pi and there we go now we have a new card again。

 each one being chosen randomly by chance。

![](img/d599875aee7f49738a513fca7cd6b5ba_18.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_19.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_20.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_21.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_22.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_23.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_24.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_25.png)

So what else is built into the random module well one that can be useful to you one function is not just choice but choice plural and choices is true to its name。

 let's you choose not just one item from a list but multiple if you want of two so let's try that out I'll get down below and I'll type random dot choices and it turns out if I read documentation。

 I'll find out that choices this function takes as input it first argument。

 the same list of options to choose from and the second argument is one called K which stands in for number of items I want to randomly choose from this list so here let's try choosing two cards instead of just one。

 I'll set K equal to two and now if I go down below and run Python of cards do pi let's see what we get。

 I'll get queen and king so it seems like I randomly chose two cards from this deck and got back queen。



![](img/d599875aee7f49738a513fca7cd6b5ba_27.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_28.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_29.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_30.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_31.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_32.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_33.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_34.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_35.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_36.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_37.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_38.png)

And king let's keep trying this again。 I'll do Python of cards。 pi。 I'll get queen and Jack。

 Python of cards。 pi King and Jack， and we can keep going here but。



![](img/d599875aee7f49738a513fca7cd6b5ba_40.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_41.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_42.png)

Hm。So here I seem to have gotten queen and queen， which might not be what you'd expect Now it turns out that random dot choices is doing what's called sampling with replacement。

 it's akin to me having a deck of three shuffling it， taking one card out。

 writing down that card putting it back in shuffling again and choosing another random card from that same deck of three so every time I choose a new card in this case。

 I'm choosing from this set of three when I choose a card that doesn't eliminate it from future choosings of my random choosing in this particular case。

 so this is sampling without sampling with replacement， add in the card。

 let's say back into the deck Now if we don't want that we want to sample let's say without replacement。

 I could use a different function， one called random dot sample random dot sample。

 and this one has the same arguments。

![](img/d599875aee7f49738a513fca7cd6b5ba_44.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_45.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_46.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_47.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_48.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_49.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_50.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_51.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_52.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_53.png)

The first one being the list of cards to choose from or really any list to choose anything from。

 and then K being the number of items we hope to select from this list。



![](img/d599875aee7f49738a513fca7cd6b5ba_55.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_56.png)

Now like I said， random dot sample will select with replacement without replacement。

 it will be akin to me having a deck of three， shuffling it， taking one card out。

 shuffling the remaining two and choosing one more cards so let's see what happens here I'll run Python of cards pi and I'll get back queen and king two distinct cards。

 I'll again do Python of cards pi， Jack and King and again queen and King so you can see here I'm getting a random set of choices from this deck but because I only have one card for each in this case。

 you know Jack， Queen and King， I'll always get at the end。

 unique choices from my deck I'm here sampling without replacement。



![](img/d599875aee7f49738a513fca7cd6b5ba_58.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_59.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_60.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_61.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_62.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_63.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_64.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_65.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_66.png)

Now what if I wanted to maybe weight the odds a little more in my favor and make some things more likely to happen than others well I can actually use if we go back to random dot choices。

 another argument to this choices function， one called weights， weights and weights takes his input。

 this argument here， a list of values， numbers to be sure。

 the same length as the list that I'm selecting elements from。



![](img/d599875aee7f49738a513fca7cd6b5ba_68.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_69.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_70.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_71.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_72.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_73.png)

So let's say I wanted to you know currently make it more likely a user will choose the jack card Well I could do that by adjusting the weights here currently if I didn't set weights at all。

 it will be equally likely that a user would choose Jack queen or King， but I could wait things more。

 let's say in my favor and maybe make it so that the user 100% of the time will choose jack and I can do so like this here 100。

 and I'm getting 100% means that the user will always choose the jack card and0 here。

 meaning kind of0% will be they'll never choose in this case queen or King So that's one this I'll do Python of cards pi and here well unsurprisingly we get jack and jack and or one this again。



![](img/d599875aee7f49738a513fca7cd6b5ba_75.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_76.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_77.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_78.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_79.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_80.png)

Get Jack and Jack。 And again。Get Jack and Jack。 So it seems like I've weighted things more towards this jack card。

 But what else could I try， Maybe I could make it only a little bit more likely that user chooses the jack card。

 and I'll then make it a little more likely they choose the queen card and king。

 let's put it about 5%。 So to be sure these weights add up to 100%。 Of course。

 we're always going select at least one card from the options here。

 But it seems like 75% of the time we'll get back a jack 20% of time we'll get back a queen and 5% of time willll get back a king。

 So let's try this out。 I'll run Python of Car pi。 again get jack and jack Python a Car pi again。

 get jack and jack。 And if we keep going。

![](img/d599875aee7f49738a513fca7cd6b5ba_82.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_83.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_84.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_85.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_86.png)

Ods are， will eventually， as we have down below， end up with a queen， but again。

 this is much less likely than it was before without having applied these weights。😊。



![](img/d599875aee7f49738a513fca7cd6b5ba_88.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_89.png)

Now randomness is really fun， really cool， but it's not so fun and not so cool when you're trying to debug your programs。

 in fact， randomness can get in the way of debugging because really you want to think of debugging as thinking of defined inputs and defined outputs and if everything happens randomly it's hard to debug your program so thankfully there are ways to have your programs work with randomness but to guarantee certain outcomes when you want to do something like debugging。



![](img/d599875aee7f49738a513fca7cd6b5ba_91.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_92.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_93.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_94.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_95.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_96.png)

Now in the random module， there is， in this case a function called seed and a seed is something that goes into this thing called a pseudoran number generator。

 actually underlies the random choices that go into functions like choices and sample and choice that we've seen here。



![](img/d599875aee7f49738a513fca7cd6b5ba_98.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_99.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_100.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_101.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_102.png)

Now it turns out that when you initialize a Python program like this one or call a function like random dot choices。

 you are using that pseudoran number generator and it takes as input something like a seed that might change on different runs of your program like your system time but if we give a seed that a specific number that always stays the same well we'll always get the same choices from let's say a function like random dot choices or sample or choice let's take a look at it here I'll go down and I will say random do seed random dot seed and I'll give it here。

 some number let's just say zero for simplicity now normally the seed would be set by something like my system time it changes on each run of the program but here I want to define it explicitly as zero every time I run this program Well I could go ahead and run Python of car。



![](img/d599875aee7f49738a513fca7cd6b5ba_104.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_105.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_106.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_107.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_108.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_109.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_110.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_111.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_112.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_113.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_114.png)

pi and we'll see we get back king and king by chance， but now if I run Python of cards。 pi。



![](img/d599875aee7f49738a513fca7cd6b5ba_116.png)

I'll get back king and king again and maybe again here I'll get back King and King。

 so it seems like setting the seed has given me a random choice， certainly from this deck。

 but one that will always stay consistent and I could try this again。

 I could do maybe a seed of one and see if that might change anything here。



![](img/d599875aee7f49738a513fca7cd6b5ba_118.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_119.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_120.png)

Python of cards。 pi， I'll get Jack and King here， and I claim that as long as my seat is one。

 I'll get back Jack and King。

![](img/d599875aee7f49738a513fca7cd6b5ba_122.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_123.png)

So these setting the seed here is a really good way to help you debug your programs。

 your programs can involve randomness， but you can actually be sure of the outcome when you set something like a random seed。



![](img/d599875aee7f49738a513fca7cd6b5ba_125.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_126.png)

So this was our short on random， if you' free to use it at element of Chance or randomness to your programs or whenever everyone's set the odds in your favor。

 this was our short on random， we'll see you next time。



![](img/d599875aee7f49738a513fca7cd6b5ba_128.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_129.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_130.png)
# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P11：-12-Lists - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

Well， hello in and all and welcome to our short on lists now we'll be exploring how we can store information in certain orders within Python and I have here a game called Super Mariio Car which not familiar as a racing game for the Nintendo entertainmenttertainment system way back in the I don't know the 90s or so and the idea is you would play as Mario。

 Luigi Princess Pe and race to get a certain place in the race whether it was first， second， third。

 first or fourth whatever it was we're gonna make a list here to represent the racers in their place when they cross the finish line here so I'll come to my terminal here and I'll go ahead and code results do pi and to make a list in Python well I can think about how I want to store these racers maybe Mario came first followed by Luigi so Mario in first place Luigi in second place I could make a list in Python by first giving it some kind of name so here I'll give this list the name results just like this。

Reult and I'll say results equals in this case， while a list and a list in Python is denoted by these brackets here。

 these square brackets， opening and closing。Now within these two brackets I can actually place this information in the order I want it to be。

 so first I could place Mario saying Mario came first in this particular race。

 followed by in this case Luigi just like this， and notice how each of these elements is separated by a comma。

 so Mario came first， followed by Luigi。So here I've created a list just explicitly on my own I a list。

 add the elements and so on， but often in Python you might have a list you want to dynamically add to as your program runs here I've initialized the list but how could I keep adding more racers in this case Well let's say after Mario and Luigi comes Princess Peach so I could if I wanted to add on to this list。

 use a method called append append， add a new element to the end of this list here so I could try results do append I take my name of my list。

 use dot and then append to add on some new element at the end of this list and back in the superintendo entertainmentter system era Princess Peach is actually just called Princess so I'll use that name here and I'll add the princess to our list here saying that she came in third Now let's see where we're going here so if I were to print the results I can use print here。

I can then run Python of results and down below， I'll see Mario， Luigi and Princess。

 So Mario in first place， Luigi in second place and Princess in third place so far。Well。

 maybe as the race goes on， we have more racers who finish so I could keep app if I wanted to I could say results do aend and maybe after Princess comes。

 let's say Yoshi， another player you can play in this game after Yoshi comes Coupa troopa and then after Cooperupa Troupa comes let's say Toad so these are our results I'll go ahead and run Pythonresult。

 pi and now we'll see our results for the first six finishers again Mario in first place Luigi in second Princess in third and the rest following thereafter。

Now we could， if we wanted to try to add more than one racer at a time。

 maybe we get the results for Bowser and Donkey Kong Jr。 at a pretty similar time。

 so we could try to add both them at once to our list。

 one way to do this would be as follows I could go ahead and say results。

 append and add on maybe a list to my list， I could try adding on in this case， Bowser。

Followed by Donkey Kong Jr。 and hopefully what we'll see is that these two elements。

 these two racers， Bowser and Donkey Kong get added at the end of our list all at once。

 but let's see。If I were to run Python of results do pi。Well we'll see here。

 we'll see here that we still have our first six or so finishers， but then at the end。

 I'm noticing that Bowser and Doetkong Jr。 well they're added into our list。

 but they seem to be inside of a list themselves notice the curly curly brackets around their names there So how could we fix this if we want to add onto our list using a list itself。

 we can't use a pen， aend actually goes ahead and add the list itself to our list So why don't go ahead and remove this。

 I'll say results dot remove which is another method I can use to remove items and I can give as input to remove the list itself and why don't we do this instead I'll say results dot extend。

Results extend， and I can give extend now a list， but it will really take each element of that list and append it to。

 in this case， my original list called results。 So to be clear。

We're starting now with a list of two racers who finished Mario and Luigi。

 we're adding in Princess Yoshi， guparupa and Toad each individually。

 We try to add the list of Bowser and Donkey Kongong Jr。

 but we realized we can't use a pen for that so we remove them instead and now we'll try extending our list which will take each of Bowser and Donkik Jr and add them individually to our results list here So let's try this I'll run Python of results do pi and hopefully I'll see down below we can in fact see all eight now of our finishers each on our list with no sublists if you will inside of our one larger list So here is an example of our list Now we've added racers to it What more can we do with list。

 let's go ahead and try to maybe take our list as it exists down here。

 I can really just copy and paste this。 actually let me not copy and paste。

 I'll come back up here and I will do results equals and I'll type in。Mario， Luigi， Oh， Princess。

 Yoshi， Coupa Troupa。Toad。Bowser and Donkey Kong Jr。 so a bit of a long list we have up here。

 but this will enable us to see a few more features of lists as well。

So one other one we could want to be familiar with is just getting a sense of what remove might actually do here。

 so here I have a list where Bowser is clearly part of this list。

 Bowser looks like is in seventh place in this race。

 but I could remove Bowser entirely like I could say results do remove and then give us input Bowser and this remove method will' actually search to my list and find the first instance of Bowser and remove that element as well。

 so I'll run Python of results。 pi and we'll see down below that Bowser is no longer in our race。

Let's say Bowser tries to cheat the system a little bit and we remove Bowser。

 what we later go on and try to add Bowser back in。

 what we saw with results do append power to append Bowser Bowser would show up at the end of our list in this case in eighth place。

 but we don't really want that for Bser Bowser of course prefer to be in first place。

 So I could try this I could try a new method， one called insert an insert takes as its first argument。

 the index at which I want to insert some given element So recall how our lists are actually index from zero0 is the first element。

 one is a second element and so on and so forth。 So for instance。

 Mario here is at the zero with index Luigi at the first index Princess at the second index So if I want a Bser to kind of sneakily move up to first place。

 I could try to insert Bser of course at the zero with index and say is the second argument the actual element I want to introduce。

Bowser in this case So what have we done We've had our list of results up here with Bowser in 7。

 We've removed Bowser， but then later on we go back and insert Bser in first or the zero with index as well。

 let's try printing our results down below and we'll see that Bowser appears now to be in first place at the zero with index of our list。

Now one more thing we can do with list， one more method to consider here is one called reverse。

 in fact I can call results doreverse， I wanted to flip the standings a little bit。

 turn whoever is in eighth into first， whoever is in first， into eighth。

 and I could actually run this now and see the result。And we'll see our list has been reversed。

 we have Donkey Kongong Jr。 now in first who is previously in last place and Bowser who is previously in first place is now here and first So these are a few methods we' familiar with as you go off and do work with lists we've seen here append。

 we've seen extend， we've seen remove and we've seen insert and of course at the end here we've seen reverse that's it for this short on lists。

 we'll see you next time。

![](img/98003cc8d548ad85267880e4e815f1c4_1.png)

![](img/98003cc8d548ad85267880e4e815f1c4_2.png)
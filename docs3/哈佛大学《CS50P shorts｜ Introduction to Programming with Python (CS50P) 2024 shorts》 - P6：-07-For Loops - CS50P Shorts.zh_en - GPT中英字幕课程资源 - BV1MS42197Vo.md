# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P6：-07-For Loops - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/27e27eaa3403abf6d4c673e299ac34d9_0.png)

Well， hello on and all and welcome to our short on four loops。

 If you're familiar with the Mario videoideo game series。

 you might be familiar with Pi Princess Peach and her castle a Peache's Cat and we'll imagine together that Princess Peach is inviting some guests to join her at a ball at Peach's Cast at 7 pm this evening Now thankfully Peach has auto the process of writing letters to her guests。

 In fact， we have here a function called write letter which takes in to arguments one called receiver and one called sender and notice how the purpose of right letter is to return to us a fully written and formatted letter to a receiver from the sender in particular。

 we're using Python F strings here to interpolate the values of receiver and sender。😊，For instance。

 if our receiver were to be Mario as it is online too here， and our sender were to be Princess Peach。

 well we should see at the end of this a letter that says dearar Mario。

 and then some text down below， sincerely Princess Peach。

 and then we'll take that letter and print out to our terminal to make sure everything is all correct。

So let's see what happens if we were run this program。

 I'll go ahead and open up my terminal here and I'll run Python of letters。 pi。

 I'll give us a bit more space so we can see all the letters fly by here if I hit enter。

We'll see some letters being printed out to each of our guests here， we see we invited。

Invited Mario first that seems good invited Luigi next Daisy as well。

 and finally Yoshi so this program seems to work， but there's a question of how well it's designed if I were to show you again what this program looks like let's think of some scenarios where this might get a little tedious let's say we're only inviting four guests now but we also want to invite other folks too。

 in which case our guest list get pretty long and to do that I need to kind of copy and paste。

 copy and paste to add new letters to new characters as well。Now。

 if you find yourself in this kind of situation where you're repeating something for each maybe guest you have。

 you might think to use something like a for loop， a for loop fact is great when you know how many times you want to iterate or you want to do something like write a letter for each person or each thing you have in some list like a guest list in this case。

So let's actually make ourselves a guest list and write a for loop to write a letter for each person on that guest list well in Maine here。

 why don't I go ahead and update this program to instead keep track of a list keep track of a list that we're going to call names and this names list will be our guest list for the ball I'll go ahead and maybe add a few names the guest list I'll go ahead and add Mario here and Lubi G as well Daisy to Daisy and Yoshi just like this and now I have a guest list of names I'm hoping to invite Well now what should we do。

 we know we want to write a letter for each person that is going to be in this list so I think I can actually get rid of this code down below here and instead think about how I could use a for loop。

WellOne way to use a for loop as we saw in lecture is to use numbers and iterate over every number in some range of numbers。

 so I could write some code like this for I， which is usually the name we give to some variables iterating changing on each iteration。

For i in and then the Python range function， and range will give us a list of numbers from zero up to。

 but not including the value we pass in as input to range。So in effect。

 maybe I want I here to iterate， let's say from zero， maybe the zero with index of this list， to one。

 the first index of this list to two， the second index of this list， and then to three。

 the third index of this list。Again， indexing from zero with Mario here。So to do that。

 I can actually pass into range here the length of our list here I'm sayingL of names。

 which in this case is four， but range will give us0，1，2。

 and3 let's try this out though I'll go ahead and print I down below and ideally I'll see012 and3 each of the indexes indices in this list here。

I'll go ahead and run Python of lettersters。pi。And we'll in fact， see0，1，2 and3。

 that seems to work just as well。 but of course we don't want to invite these numbers to our part。

 You want to invite Mario， Luigi， Daisy and Yoshi so one way to approach this is to use I to index into our list I could do something like this I could say names bracket I and on each iteration again I will change first it will be0 then one then two then three giving us different names in our list here want to go ahead and run letter pi again and we'll see now the names we're hoping to invite and this is promising because I think I could actually use these as input to the right letter function let's try this if I were to go ahead and print not just name bracket I but the result of right letter given names bracket I as the receiver and Princess peach as the sender I think we start。

To get the same letters we saw last time。Notice a few things first here though， again。

 I will update on each iteration of our loop that is from oneteral or time going from top to bottom in this invented code here。

 but well will'll actually stay the same is Princess Peach here。

 the name that will be the sender that will not change on each iteration because it doesn't depend on anything in our loop itself。

So let's go ahead and run this， I'll run Python of lettersters。

 pi and we'll see the same letters down below here as well。So same result。

 but what have we given ourselves here， not able to make this program much more flexible。

 much more adaptable， how would should invite additional guests。

 we could very quickly let's say add a guest like Bowser。

 everyone is invited here and we could print out a letter for Bowser just like that。

 no copying and pasting， just adding Bowser's name to our guest list。

Now let's uninvite Bowser actually and think through some ways to improve the design of even this little segment of code here Now this works。

 it's actually pretty well designed， but I think we could make it a little more readable。

 maybe stylistically better too and we could do that using a feature of Python which is we can actually iterate over any kind of list directly。

 this is a list here， names is a list of in this case names so we can actually use it as the second part of our for loop。

 could say4 I in names。😊，And in this case， I will actually temporarily refer to each of the items in our list or the names in our names list。

 I will first be Mario， then Luigi， then Daisy， then Yosi updating on each iteration。

But I don't need to use I， in fact I can give it any name I like as long as I am consistent with that name。

 I could say something more Englishlike like for name in name because we have a list of names plural。

 but each item is a single name singular so now on the inside of my for loop well there's no longer an I variable to use to index into names but I've conveniently given myself now this variable called name that I can just use again first name will be Mario then Luigi then Daisy then Yoshi updating on each iteration as we loop through our for loop and once we get to the end。

 once there are no more names will simply stop looping and exit our program。😊，Let's try it here。

 I'll go ahead and run Python oflet。pi and we'll see the same results but now with a bit better English syntax and probably better styllististically as a writing programs like these so four loops again are powerful when you know how many times you want to loop or when you want to do something for each item you have in some list or more generally some iterable something can be iterated over this was our short on four loops。

 we'll see you next time。

![](img/27e27eaa3403abf6d4c673e299ac34d9_2.png)

![](img/27e27eaa3403abf6d4c673e299ac34d9_3.png)
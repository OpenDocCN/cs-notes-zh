# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P2：-02-Capture Groups - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

Well hello Ar in all and welcome to our short on capture groups Now those of you who have made international calls might be familiar with what's called a country calling code and I have here three of them up above in the dictionary called locations I have one plus one which often involves numbers from the United States in Canada I have one plus62 which often involves numbers from Indonesia and one plus 505 that involves numbers from Nicaragua and I have down below here in Maine a program that in this case validates phone numbers internationally so I have here a pattern that I'm going to look for within each of these phone numbers I might enter into my program down below online 7 in this case notice what I'm expecting I'm expecting the literal actual character plus here I've escaped it with this backlash because plus has other meetings within regular expressions。

I'm now expecting any kind of number in this case know0 through9 between one and three times so notice here the country code for the US and Canada that's plus one so only one number here for Indonesia it's 262 and for Nicaraagua it's 3505 so between in this case oneN3 numbers following some plus thereafter there will hopefully be a space for this a valid number and then there will be exactly three numbers a dash again exactly the numbers followed by a dash again and then exactly four numbers so this is the pattern we are looking for and down below ons9 through 13 or this is the code doing that work for us we've stored within number the user's phone number that they have entered and we're going to check using re do search if we found a match for our pattern within the number string if we do have a match is returned。

U will print valid if we don't， we'll print invalid。

Let me go ahead down below here and let me type main to ensure I call Ma when I run this program and I'll go ahead and run Python ofgroup。

pi and if I hit enter now I should be able to enter a number I'll test one here plus1 and I'll type in 6174951000 I'll hit enter here and we'll see that that is valid maybe I'll try it to for Indonesia I'll do plus 62 and I'll enter in my phone number again and I'll hit enter and I'll see that's valid as well and just for the measure I'll test Nicaragua I'll do plus 505 and I'll type in this number and we'll see that is valid as well。

So it seems like our pattern is working， but there's more we could do with this program， I think。

 thanks to this feature called a capture group。Well。

 maybe what I want to do is not just share if this number is valid or invalid。

 but maybe tell somebody from what country in this case this number is calling from。

 you can think of your phone when receive some call from an unknown number it might at least tell you the location or the area that number is calling from。

 what if we write the same thing here where people call us internationally and we show the user in this case what country they are calling from in this case we don't want to just test to see if we find the pattern within our phone numbers here。

 we also want to extract some portion of it in this case the very first portion。

 the country calling code plus 505 for Nicaragua plus6 to for Indonesia or plus one for the U。

 and Canada。We run into a problem here if we were to use maybe simple a string manipulation。

 if I entered in some number and was trying to extract in this case the country calling code。

 well I wouldn't immediately know whether I should extract in this case the first two characters plus one。

 the first three characters plus62 or in this case the first four characters plus 505。But thankfully。

 I'd actually use regular expressions and capture groups to dynamically capture the portion of the content I'm looking for。

Now the way I can make a capture group is by using parentheses inside of a regular expression。

 so really I want to capture or extract in this case the country calling code。

 which we said the pattern exists for right here， a literal plus sign followed by one to three numbers。

Now I can encase this inside of parentheses and this becomes my own capture group。

 but how could I maybe find the information I capture well if I find a match here turns out that this match object in Python comes with another one called group group if I were to do let me do a match dot group。

 well this would help me find all of the capture groups。

 I've actually implemented in my regular expression and extract them from this match。

Because let's say this is the first capture group we have， I could go ahead and type one here。

 capture groups， at least in Python in this particular case are one index。

 so I'm saying here if there is a match， go ahead and give me in this case the result that I found within the first capture group I'll go ahead and store this in one a variable called country code and I could instead of printing valid here。

 maybe I'll go ahead and print something like country code and see what we can find I'll go ahead and run Python of groups。

 pi and I'll go ahead and do plus one fog on my phone number hit enter。And now we'll see plus one。

 so it seems like we extracted in this case， the portion of our content that matched the pattern within these pregthees。

I'll try it with another one here， I'll do Python ofgroups。py plus62。

And we'll see plus62 so it is dynamic， I'm just not looking for the first two characters all the time or the first three characters all the time。

 it's looking for this pattern and when it finds it is returning it to us as appropriate。

Now what else could we do with this well country code literally is a string here so if I wanted to in this case find the country somebody is calling from based on their country calling code well I could perhaps use country code is the key for this dictionary here I could type locations bracket locations bracket country code and because each of these country calling code is a key in my dictionary I should hopefully find in this case the actual location they are calling from let's try this out。

 I'll run Python of groups。 pi and I'll now type oops I'll now type let's do plus one again。

 by the number hit enter。And now we'll see United States and Canada， I could do this again。

 I could try let's say a plus 62 and number again， Indonesia。

 I'll now try plus 505 and I'll see Nicaragua， so the capture group here is doing the work of finding the portion of our content that matches some pattern we were looking for。

我。I think we've really seen a lot of what this can do for us。

 but there is one more feature to take a look at here notice how on line 11 I am really using indices indexes to find the capture group I'm looking for but a more complex regular expression might involve more than one capture group could involve up to I don't know more than more than one two。

 three，4 could it up to 10， however many it is it can be helpful to have a better way to refer to these capture groups so if this capture group has some particular meaning to it。

 I could actually give it a name to refer to later on within the regular expression and the way I do this is with the following syntax within my capture group after the first preesis I can type question mark P and then open bracket。

 closed bracket or in this case less than signine greater than sign and then some name for this capture group I could call。

Cory code， just like this。So now this pattern here and the capture group has a name I can refer to later to extract it with。

Down here on line 11， I could in this case use one。

 but now I could actually make use of country code。

 the name I gave for this particular capture group and I could type in country code just like this which will say find for me in this case the capture group that I named country code and use that instead I'll type Python of groups。

 pi I'll go ahead and type plus one same number here and now we'll see United States and Canada seems to work but is now a little more readable even some name something I might later hope to capture in our programs。



![](img/6037d7f7088881629d75b3be83216cf6_1.png)

So this was our brief foray into capture groups and this was our short， we'll see you next time。



![](img/6037d7f7088881629d75b3be83216cf6_3.png)
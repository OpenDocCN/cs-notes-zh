# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P5：-06-Dictionaries - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/2b66443907fb946a813965bfda7ab8c3_0.png)

Well hello in all and welcome to our short on dictionaries Now dictionaries are useful well you want just to explore similar kinds of information in terms of these key value pairs。

 so more on that in a moment but let's first dive into our scenario here I have here a program called report do pi where the goal is to write a report on some given spacecrafts out there in the universe and notice how here I have a function called create report that takes as input。

 something called spacecraft an argument here called spacecraft and my goal is to well one hopefully make sure this report actually has the information I'm looking for and then return that report for printing perhaps up in mainine over here。

Now we said that dictionaries are good for toing collections of related information and I think a spacecraft kind of qualifies in this sense as spacecraft has something like a name。

 maybe like a distance from Earth， let's say， so I think a spacecraft could be good to represent with a dictionary well let's try this out here I'll go ahead up to main here and I will create our very first spacecraft that I'll call in this case just spacecraft and all'll set spacecraft equal to well a dictionary and so we've seen a dictionary begins with these curly braces。

 whereas a list begins with square brackets， a dictionary is loaded with these curly braces here。

Now a dictionary， of course， comes with these keys and values， now a key is simply some name。

 so of accessing some particular value inside of this dictionary。😊。

And maybe the first key we should have here is some attribute of our spacecraft， maybe its name。

 for instance， so I'll say here one of our keys is name and syntax wise what I have to do when I specify a key is this I give the name of the key in this case the name of the key literally is name I can then type colon followed by the value I hope for this key to represent。

 so in this case maybe let's talk about let's talk about Voyager1 which is the furthest manmade spacecraft really any kind of object away from Earth。

 Voyager 1 here。So here our spacecraft is a dictionary and we have one key name that is assigned the value Voyager1。

 but of course there are more really properties of Voyager  one。

 we can actually put inside of this dictionary， one of them is distance distance and we said Voyager one is the furthest manmade object from Earth。

 so we'll go ahead and say that this is 163 astronomical units away。

 which is on the order of let's say billions of miles away。

 go ahead and look up what that conversion is on your own。So here we have Voyager one。

 and we also have a distance of 163 AU， and this together forms our spacecraft。

So if I want to create a report on this spacecraft I could， as we said before。

 maybe print the result of create report， but then give us input our spacecraft down below and hopefully if we run。

Python report dot pi。嗯。Well， we see a report， like I argue that。

Create report is returninging us some text and we're printing it in main。

 but we haven't fixed these to dos So we have here our own dictionary with keys and values that we have specified but if we want to access those values given some key well we can do that perhaps in great report Now in general we could assume let's say that create report is given some spacecraft that is a dictionary with these two keys name and distance and the goal here is really to just access the values at those keys so I could use here are python F string and use curly braces of my own these are not curly braces for a dictionary。

 these are curly braces for interpolating some value。

 I can put in python code here to get some value and actually incorporate it into this text called report here。

So for the name of our spacecraft， we know we have a dictionary that's called spacecraft being passed as input to create report。

 and we also know we can assume in this case that this dictionary will have a key called name all lower case。

 so to access the value at this key， we can use brackets followed by the actual key of our actual name of our key。

 in this case the name of our key literally is name。

So here to be clear we'll do is go ahead and interpolate some value inside of this F string and this value will be the value we access by accessing the name the key name as it's part of our spacecraft dictionary here。

 which do the same thing now for distance， we can assume that our spacecraft dictionary also has a key called distance just like this and now if we were to rerun this report。

 I think we'd see that we got a report back with our name being Voyager 1 and our distance being 163。

 but there are no units here， so we ahead actually add this in 163 AU or astronomical units。

All right。So this is our report and you can kind of get a sense for how handy these things like dictionaries can be。

 we are able here to combine various pieces of information， the name of our spacecraft， the distance。

 and then access it very easily using these keys that we have down below。

Now what might go wrong with dictionaries well let's say we're not using Voyager1 anymore。

 we're using a new spacecraft or more specifically a kind of telescope called the James Webb Space Telescope one of the most recent space telescopes created that can help us see far beyond and reaches of space so here I'll make a new dictionary。

 and I'll set the name to James Webb Space Telescope。

 but I'm actually not quite sure how far away this telescope is from Earths all leave that key empty here。

Well， I can go ahead and try to run Python of report。

py but before I do maybe think about what might go wrong when I call create report， let's see here。

 I'll hit enter。And I'll actually get what's called a key error down below I see key error colon distance and it seems to me that we tried to access this key named distance in great report。

 but our assumption was not quite correct spacecraft does not have a key called distance so let's go ahead and add that key here well it turns out that to add a new key to a dictionary。

 I don't need to just simply create it as a dictionary is being built， I could also do this。

 I could go ahead and try to tried to do spacecraft。Brackt distance。

 much like the syntax down below to access this key。

 but then supply some value in this case I could say that it is， I think let me just check here。

 it is a 0。01 AU away from Earth so actually interestingly。

 the James Webbs Space Telecoe kind of orbits the sun in a kind of constant distance around from Earth about 0。

01 A here Let's go ahead and run the report again， I'll say Python of report do pi and now we'll see that our report has been fixed rest down below。

Okay， so we've seen here various ways to add keys to dictionaries。

 various ways to access those keys and to create our own dictionary let's consider more ways to actually access these values for a given key let's go back a little bit and when we actually don't have this value 001 we have just here the key name what could we do perhaps maybe anticipate this error and make great report a little more flexible with the kinds of input it might get Well it turns out that access some key we don't need to always use this bracket notation In fact there is some other method one called get we can use to try to access some key In that key doesn't exist we'll actually get some other value we specify instead so here perhaps in distance I could instead of using bracket distance here I could use dot get so the neo my dictionary spacecraft dot get followed by。

The key I hope to access in my dictionary， in this case， distance。

I could if I wanted to supply another value that will actually be returned if this distance key is not part of my dictionary。

We saw earlier that distance is not part of this dictionary。

 so what we should hopefully see instead is unknown。

 I I to go ahead and try Python of report dot pi hit enter and now we'll actually see that get return to us unknown instead of the actual value for this non-existent key let' avoids the key error we saw earlier as well so let's try this here I'll do spacecraft dot get and I'll try to get the name of the spacecraft otherwise we can go ahead and return unknown as well。

So in general， you will find that most of the time you can use that same braRA annotation we saw earlier。

 but if you aren't sure if some key will exist， you could use get to try to get that key but return some other value if that key in fact does not exist inside of your particular dictionary in this case。

So I believe this gives us an example of how we can go ahead and get our keys。

 let's now explore other ways to add keys beyond just the same syntax we saw earlier as well。

So recall， we could go ahead and add in a key by creating a dictionary up here， I could say distance。

 distance colon， et cea here， I could even do some syntax like this， spacecraft distance equals。

 let's say 0。01 these are two ways to add keys to dictionary。

 turns out there's also one more to be familiar with as well。

If I wanted to add not just one key at a time to my dictionary， but maybe multiple at once。

 I could use a method called updateate so I could type theI dictionary followed by a dot and then update just like this and update takes as an argument as an input here another dictionary。

 but it really take that dictionary's keys and values and just add them to the dictionary I started with here。

 in this case spacecraft， so we'll update spacecraft with all of the keys and values that I provide as input to update。

Now I could go ahead and specify here in another dictionary。

 maybe the distance which we said before was 0。01 A， and then we maybe specify another attribute。

 maybe the orbit here as I said before， the James Baab's telecope telescope orbits the sun in this case。

 so here I'm trying to add now two new keys， one called distance and one called orbit each with their own values。

I could also go down below here and I could add in some new line of my report， maybe I'll say orbit。

 and that is equal to maybe spacecraft。ge， the key called orbit。

 otherwise will return unknown if that key perhaps doesn't exist down below。Alright。

 so here we've tried to add here two new keys at once to our dictionary above。

 let's go ahead and run Python ofre。pi， and now we'll see that those keys are in fact part of our dictionary。

 thanks to update as well。So now we've seen how to add keys in various ways。

 how to access keys in various ways， but let's see some other utility features of dictionaries as well actually go ahead and remove what I have here and why don't we try to make a new program one called distances do pi Now in distances dot pi。

 we're going to treat dictionaries a little bit differently I'm going make a dictionary where I have the names of my spacecraft in one column if you will。

 and the distances of those spacecraft in another column if you will my dictionary so for instance I can make a dictionary called distances and open up some curly braces here and as the keys in this dictionary I'll go ahead and have the names of spacecraft like Voyager1 for instance。

 Now the value of this particular key will be the distance that Voyager1 is away from Earth which happens to be 163 AU as we saw。

Or。Now I can go ahead and add other keys to my dictionary， other spacecraft and their distances。

 I can also go ahead and add Voyager2， which happens to be 136 AU away from Earth。

 I could go ahead and add Pioneer pioneer 10， which is about 80 AU away， new Horizons， another probe。

 which is about 58 AU away， and finally Pioneer 11， which is about 44 AU away。

So notice how here my dictionary is representing multiple spacecraft。

 but I'm really definingfin the relationship between my spacecraft names and their distances as well。

So with my information presented like this， I could try to maybe print out each of their names and their distances using some key functionalities of dictionaries here I'll go ahead and define myself a function called Ma and I'll leave that empty for now。

 I'll go down below and make sure I call Ma and now within Maine my goal is to for each spacecraft I have inside of the dictionary print out its name and distance away from Earth。

So if I want to do something for each let's say anything I have a good idea is to use a for loop in this case I want to do something for each key I have in my dictionary what turns out that dictionaries come with a method called keys that returns to me all the keys in my dictionary so I could type 4 name in distances dots and again dot keys。

 this method here that will return to me all of the keys in my dictionary， so first Voyager1。

 then Voyager 2 then pioneer 10 new horizonors， pioneer 11。

 these will all a part of the return value of dot keys when called on the distances dictionary and now I'm saying for name in that list of keys。

 so first name will be equal to Voyager 1， then Voyager 2， then pioneer 10。

 as my for loop continues in the code indented here on line 12。

So now that I have name which will first be Voyager 1， Voyager2。

 I might also want to access in this case， the distances of those probes from Earth。

 so to do that I could actually maybe plug in my key to my dictionary and get back the value I'm looking for let's demonstrate this here I'll type print and I'll use an F string and I'll then say name referring to the name of my spacecraft is and then some distance away from Earth。

But again， we have here name， which is in fact a key of our dictionary。

 so I could type distances bracket name to access the value for each of these various keys I'm getting for instance。

 when name is equal to Voyager 1 I'll get back 163 right here when name is equal to Voyager2 well I'll get back 136 right down here so I could complete the sentence by saying name is some distance in AU from。

Just like that， let's go ahead and try running this， I'll say Python。Of distanceists dot pi。

And we'll see here some other reports on our spacecraft， Voyager 1 is 163 AU from Earth。

Voyager 2 is 136 AU from her。So when you want to do some kind of code like this On 12 for each key in your dictionary。

 you could use dot keys to access each of those keys and loop over them perhaps with something like a for loop。

One more be familiar with here， we can also loop over， let's say the values in our dictionaries。

 so just like we have keys， we also have values as well dot values and let's try maybe converting these AU to meters instead a much more friendly a measurement so I'll go ahead and replace this code down below here and why dont actually delete this for loop here and first give myself a function to convert AU。

To convert AU into in this case， meters， it turns out that the number of meters corresponding to one AU is this big number here。

 I'm not even sure how to pronounce it， but I will make sure type it incorrectly。

59787-0700 and I believe this is correct， 870597。1，4，9， yes。

 this really big number that I don't know how to pronounce is the number of meters in one given A U。

 so if we wanted to perhaps loop over all of our values in the dictionary， so first 163， then 136。

 then 80 and so on， we could use a4 loop。I could say four perhaps distance in distances dot values。

 and then I could perhaps print using an F string。The distance。An AU is the converted。Distance。

In meters。So to be clear here。A function called convert that takes single amount of AU and converts it to meters。

 then in mainine we go through each value in our dictionaryaries values。

 and then we'll go ahead and convert that distance to meters and also print out the distance in AU。

So I'll go ahead here and I'll run Python of distanceists。pi。

 and now we'll hopefully see down below all of these distances in AU now in meters。

So we've seen a lot about dictionaries， we've seen back in report。pi， how to create them。

 how to supply keys and values。We've seen how to update our dictionaries。

 whether using the update method or by using BC notation we saw earlier too。

We've seen how to access those values， given some key， we've seen the get method down below。

 as well as the more simple bracket notation too。And over in distances of dot pi。

 we've seen how to loop over the keys and the values in our dictionaries that's set here for our shortened dictionaries。

 we'll see you next time。

![](img/2b66443907fb946a813965bfda7ab8c3_2.png)

![](img/2b66443907fb946a813965bfda7ab8c3_3.png)
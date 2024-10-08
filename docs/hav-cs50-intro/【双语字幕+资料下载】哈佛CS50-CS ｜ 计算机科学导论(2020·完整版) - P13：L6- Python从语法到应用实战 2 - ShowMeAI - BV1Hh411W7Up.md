# 【双语字幕+资料下载】哈佛CS50-CS ｜ 计算机科学导论(2020·完整版) - P13：L6- Python从语法到应用实战 2 - ShowMeAI - BV1Hh411W7Up

right thing instead well let me go ah**d，and open up another program here。

also from week one this one was called，conditions。c，and this one give me one moment to open。

this up on the left，this one here was a program whose，purpose in life was to get an in from。

the user called x，get another called y and then it just，did this if。

x less than y print out as much else if，x greater than y，print out as much and so forth let's go。

ahead and translate this program into，the corresponding python code。

using some of the syntax we've seen，already i'm going to go ah**d and save，this as conditions。pi。

and i think i'm going to go ah**d and，keep using the library the cs50 library。

so i don't have to worry about，those kinds of errors when casting bad。

input to another so from cs50 import，getint and let me go ah**d and now get，an in from the user。

in from the user，calling it y and i won't bother typing，comments this time just for time's sake。

and now let me ask the question in c i，would have done if x less than y。

python is a little more terse if x less，than y suffices but with a colon。

under that i'm going to go ah**d and say，print x is less than y，than y，y，out，x is equal to y。

and i think that's just about it i'm，going to go ah**d down here and run，python of conditions，indeed。

time with 2，it again with 1，have worked，and let me point out one other thing i。

mentioned earlier that you have this，just say，import the cs50 library if you don't，function names。

that's totally fine but notice that the，ide is yelling at me at lines three and。

four that getint is no longer recognized，that's because python supports this。

feature when using other people's，libraries，is to say，you can't refer to getint anymore。

directly you have to more explicitly say，of，familiar dot，library just like a c。

struct and call the function called，getint therein，so i can now go ah**d and rerun this。

python of conditions。pi，is now working，again so which is better it depends i。

mean if it's sort of more readable to，that's going to save you a lot of。

keystrokes because you don't have to，keep typing cs50 dot cs50 dot。

if though you're writing a pretty big，program and maybe you're using。

two different libraries that both，implement a function called getint。

you want to be able to distinguish one，from the other so you might want to just。

import the libraries by their name，i've done here，which is known as name spacing name。

spacing means that you can have two，identically named variables or functions。

existing in two different name spaces，they don't collide，library。

or some other library's name instead let，here，let me go ah**d and open up another file。

uh from week one this one was，agree。c and this program，prompted the user uh to input whether or。

not they agree，and we checked a little curiously that，first week。

using equals equals uh quote unquote y，or lowercase y，n，well how do we go about converting this。

one let me go ah**d and give myself a，new file over here，i'll call it agree。pi in this case and。

it turns out we can solve this one in a，few different ways let me go ah**d and。

start off by importing from cs50，uh gets int just because it's oh no get。

string rather because it's convenient，let me go ah**d and get the user's input，via getstring。

and ask them the same question do you，agree question mark with a space。

then let me check if s equals equals，quote unquote y，or s equals equals lowercase y。

then i'm going to go ah**d and print out，agreed，else oh no l if，s equals equals uh capital n or。

s equals equals lowercase n let me go，ahead and print out here，not quote unquote not agreed。

and i think that should do it but，something's weird here，there's a few differences what strikes。

you as，different from c what muscle memory，might you have to break now。

when using conditions with multiple，boolean expressions，combined in this way and there's another。

subtlety there's at least，two salient differences between c and，any thoughts in the chat or an air。

i was going to say for this one instead，of using the symbols for the logical，directly。

yeah we can literally just type the，english word or if we want to express a。

logical or so in c recall on the left we，would have done this vertical bar thing。

which is fine you get used to it but，english sense，python took the approach of using more。

frequently actual，english or english-like words that，actually do read left to right and。

indeed a theme is emerging here when you，read python code，it is closer to english than c is。

because you don't trip over as much，punctuation each line of python code。

tends to read a little more like an，english phrase or an english。

sentence and there's one other subtlety，here on the left back in week one，the y's。

and the ends this week i'm using double，quotes but to be honest，it actually doesn't matter i can。

alternatively use single quotes anywhere，everywhere so long as i'm consistent。

but in python there is no fundamental，difference between double quotes and，consistent。

the reason being when we looked at the，data types that existed between。

c and now python absent from the list of，python data types，was char in python there is no such。

thing as an individual char，string，even if it's just one character long，everything is a string。

downside is we don't have it quite as，fine grain control upside is we get a，lot more features。

with those string structures，as we've already seen with for instance，those。

as well well let me go ah**d and i think，i can simplify this for instance suppose。

i wanted to tolerate something like，not just y or y in uppercase or，tolerate。

yes in uppercase or lowercase as well，well you could imagine just starting to，add to the code or s。

equals equals yes or s，equals equals yes but wait a minute what。

if the user is being a little sloppy and，what if i want to actually say like well。

what if they're yelling or s equals，equals yes in all caps and there's a few。

other permutations as well like，this is quickly devolving into quite the。

mess but if at the end of the day you，really just want to detect，why or the word yes irrespective of。

capitalization，i bet we can be pretty clever in python，here what if i，go ah**d and say if s is in。

quote unquote y or yes，in fact i can borrow an idea from，earlier whereby i can use the squ*re。

bracket notation to give me a list which，automatically，grow or shrink as you need it you don't。

have to decide in advance how big it is，this preposition here in is a new，keyword in python。

that will literally answer that question，for me and we've used it before earlier。

when i implemented speller，i said if the word is in my set of words。

return true so if s in this list i'll，get back yeah uh，true or false based on the answer to。

that question but again it's not，tolerating case but no big deal。

dot lower now i can say is the lower，case version of s no matter what the，human typed in。

in this list of two values that means，now the user can type in，all caps in alternating caps in one's。

capitalized letter or any other，permutation。

![](img/ba5c84256d1c630ab124e64119667f77_1.png)

whatsoever all right so that then is our，conditions let me pause here to see if。

there's any questions any questions or，confusion that we can clear up with。

syntax with conditions boolean variables，of boolean values so a question came up。

so in python we are allowed to use the，equals equal syntax to compare two，strings。

yes so another really good catch in，python，there are no pointers underneath the。

hood they're still addresses like your，memory hasn't gone anywhere but。



![](img/ba5c84256d1c630ab124e64119667f77_3.png)

underneath the hood all of that is now，managed for you，by the language itself so if you want to。

conceptually compare，one string against another just as i did，here now on line seven。

python will do the，quote unquote right thing for you you，don't need to regress。

into using stir comp instead now just，this if，s dot lower in quote unquote n。

or comma no we can achieve the same，result there，by doing the same technique other，questions or。

all good here no all right well let me，go ah**d and open up another example。

that you might recall we did a，it，uh good better and then best this one。

involving just a cat meowing in some，form so let me go ah**d and open up。

from week one an example that was called，meow zero relatively straightforward，that simply did this。

it simply meowed three times so suffice。

![](img/ba5c84256d1c630ab124e64119667f77_5.png)

it to say now in python，it's pretty trivial to do something，three times like this i'm gonna go ah**d。



![](img/ba5c84256d1c630ab124e64119667f77_7.png)

and call this meow，dot pi and of course i can just do，something like print。

meow and i can just copy paste that but，of course the whole point of this，example back in week one。

was not to devolve and to just copy，paste surely there's a better way。

and we've seen a better way this time if，in c，int，i get zero i less than three i plus plus。

then in some curly braces we could have，done printf of meow，new line semicolon so that was the next。

version of our meow code in c，but in python of course it's a little，more succinct i can just do four。

i in range three print，quote-unquote meow so very similar in，spirit to our hello world of before。

but again we don't have to include any，a main function，or we don't need any of those curly。

braces or semicolons if you like we can，just dive in and focus on，last time。

evolved the meow program into having our，own helper function，our own function that actually uh。

allowed us to create an abstraction on，top of meowing and that was in our third，version aka meow2。

let me go ah**d and open up this version，in a tab and notice that this version。

started to get a little involved because，one we needed a prototype at the top。

because i now had a meow function at the，print meow，but to abstract that away as a new。

helper function，and then i had this code here with a for，loop inside。

well in python it's going to work out to，be a little simpler here too if i want。

to do something three times for i，meow，now of course meow doesn't yet exist so。

i can solve that problem we've seen，earlier albeit quickly in speller that i。

can define my own functions like meow，there's no more void because if you。

don't want to have arguments in a，function just don't put them there。

there's no return values specified in，python they're implicit instead so it's，suffices to do this。

here now，i have a program that iterates three，times calling meow each time and meow is。

defined down below，let me go ah**d and run this python of，traceback most recent call last there's。

a problem on line two，of meow。pie because a name error name，meow is not defined。

now the language being used there by，python is a little different。

from c's it's frankly a little more，human friendly but what just happened。

what problem has arisen that i yet，haven't tripped over，until now，even if you've never programmed in。

run help，50 yet what might be the uh the issue，there，uh if that function is not found when we。

are trying to call it because it's，described below when we are calling it。

yeah so this is no prototype yeah，there's no prototype and it turns out in。

python there isn't a notion of prototype，so unfortunately the solution we saw。

in week one is not to just copy and，paste the first line up above and end it，with a semicolon。

that's just not a thing i could do this，i could just move my meow function to，the top of the file。

thereby defining the function first and，then using it last and that would，actually solve the problem。

really help us，long term because you could probably，imagine a situation where this function。

wants to call this function but this，function calls this one，and you just can't really neatly order。

and it's just not going to be as，maintainable right recall that one of。

the values of putting main at the top of，rc programs was that，any reasonable person who wants to。

understand your code is probably going，they're not going to want to have to，looking for the。

actual main code so it turns out in，python even though you don't need a main。

function it's actually common to define，one nonetheless，it's going to be implemented with。

something like this，and i'm just going to indent my code，below that there。

so now i've defined main but i haven't，executed any code yet，on line 6 i've now defined meow but i。

haven't executed any code yet，and i mean that literally if i run，python of meow now and hit enter。

i would hope to see meow meow meow，weird，but python is doing literally what i。

told it to do i told it to define a，function called main and i told it to，define a function。

called meow what i never told it to do，is to call either of those functions so，the simplest fix here。

it's a little different from c and a，little weird is just call main is your，very last thought。

in the file so define main up at the top，it to be，but call it all the way at the bottom。

and let me go ah**d and now and run my，program and now voila，meow meow meow is back because i've。

defined main i've defined mao，and now i am calling main now as an，aside you will very often see in。

various documentation and tutorials，online a much，will have，you typing out this this achieves the。

same goal but it's not strictly，necessary for our purposes this line of。

code if you see it in any online，references or examples or books or，sections or the like。

it is necessary only when you're，libraries，like your own cs50 library or your own。

image blurring library or the like，it's not necessary when we're just。

writing individual programs of our own，so i'm going to go ah**d and keep mine。

simple and literally just call main，and let me just wave my hand at why you。

need that syntax otherwise，in this context but let me go ah**d and，modify this one last time。

because recall that in c the last，version of my program，had me running meow and passing an input。

because i defined meow was taking an，input like n，and then doing something like for int i。

gets 0 i less than，n i plus plus and then inside of my，curly braces did i print meow。

so that now i have a helper function，that i've invented，that takes one input in int called n and。

it loops that many times and prints out，real nice，abstraction and that now my program is。

distilled it's just meow three times，and it doesn't matter how i implemented。

meow i can do the same thing in python，an argument called，n i don't have to bother specifying its。

type i can now say for i，in range of n and i can print meow that。

many times and now i can get rid of my，loop in main and just say，meow three times and so same。

functionality if i run this a final time，meow meow meow，a，more sophisticated way by actually。

giving myself now，some of my own actual uh helper，functions all right any questions then。

on this progression，now we're not really seeing new python，syntax we're now just seeing a。

translation of some actual past，c programs into python to show really。

anything on your end brian nothing here，all right well let's go ah**d and open，another version。

from week one of a program called，positive。c，which was an opportunity back then not，function。

called getpositiveint but it also，introduced us to the familiar do while。



![](img/ba5c84256d1c630ab124e64119667f77_9.png)

loop and unfortunately，we're going to take that away from you。

now python does not have a do while loop。

![](img/ba5c84256d1c630ab124e64119667f77_11.png)

but it's of course a very useful thing，to be able to，do something while a condition is true。

after all pretty much any time we've，gotten user input in the class。

we've used do while so that we prompt，them at least once and then optionally。

again and again and again，until they cooperate so let me go ah**d，and implement this in python now。

in a file called positive。pi，and go ah**d here in positive。pi and，translate this thing。

as follows let me go ah**d and uh from，cs50 import，getint let me go ah**d and define a。

function called main so now i'm just，going to start to get into this habit。

i'm going to go ah**d and give myself a，variable called i and call。

get positive int and then i'm just going，to go ah**d and print out i。

keeping it nice and simple now i have to，implement，get positive int it doesn't need to take。

any input so i'm not going to give it，any arguments，and now i have to do the do while thing。

so the pythonic，way to do this in python is almost，always to deliberately induce。

an infinite loop and the idea being if，you want to do something again and again。

just start doing it forever and then，break out of the loop，when you are ready to so what do i want。

to do forever in this function well i，want to go ah**d and get，positive。

integer and then i want to go ah**d on，the next line，than，0 thereby making it positive break。

and the last line of code here is going，to be to return，n so notice in c on the left。

i did this do while thing i had to，declare n outside of the do while loop。

because it had to be outside the curly，braces to be in scope，here，is actually a little bit different。

oh yes i did screw up okay if，asked the actual question if n greater。

than zero so what did i do actually，differently here on the right hand side。

well notice i deliberately induce this，infinite loop on line 10 which just。

means do the following forever，get int，if so，break out of the loop how do i break out。

of the loop well notice that the，consistent，puts me back，in line with the original indentation。

return，lines up with the while loop which means，it's the first line of code that's。

outside of that loop，in the past we would have had very，explicit curly braces now we rely only。

on indentation，that then lets me return n so what are，some of the differences here one the do。

while loop is completely gone but two，in python，that the moment you declare a variable。

it exists until the end，of that function you don't have to worry。

about the nuance of declaring a variable，first like we did in c。

up here and then returning it down below，the moment we execute this line of code，11 here。

n suddenly exists for the entirety of，the remainder of that function。

so even though we declared inside of the，loop so to speak as per the indentation，statement。



![](img/ba5c84256d1c630ab124e64119667f77_13.png)

here at the end of the program all right，let me pause there，and see if there's any questions or。

confusion on，getting user input doing the equivalent，logically of do while。

but doing it now in this more pythonic，way peter，in python are variables accessible。

across functions or no，good question no so if you declare a，scoped。

so to speak to that function it is not，return it，and pass it as output to input or you。

would have to define it for instance as，a a global variable，instead all right。

well what else then might we translate，well recall from uh，recall from our earlier endeavors in。

week one we played around with these。

![](img/ba5c84256d1c630ab124e64119667f77_15.png)

examples from mario and for instance we，wanted to print something out，of these。

pyramids or these uh coins or these，little bricks on the screen。

well here let me go ah**d and open up a，new file called mario。pi and i'm going。

to transition away from always showing，the before and after and now just start。

to focus more on the python code that，you can always look back if you want at。

the corresponding c versions，how do i go about printing out three，bricks like this vertically。

well in python i might say something，like for i in，range of three quite simply。

as we've done a few times already and，just go ah**d and print out a hash。

i don't need to worry about the new line，because you get it for free so to speak。

but i'm going to go ah**d now and run，python of mario。pi，version。

of this mario structure but what if i。

![](img/ba5c84256d1c630ab124e64119667f77_17.png)

want to do the coins instead，what if i want to do this horizontal。



![](img/ba5c84256d1c630ab124e64119667f77_19.png)

coins that appear in these four bricks，and print out an，uh version of that well how might i do。

that well let me go ah**d and change，this to be，instead in my code for i in range of。

four so i can print four of these things，let me go ah**d and print out a question。

mark and then run this，so let me run mario。pie and voila，damn like not what i wanted and so。

here's that trade-off right you might，have been kind of excited。

so far as it's possible to be excited，about code uh that like oh my god you。

don't need to do the stupid new line，characters anymore，but what if you don't want it now we've。

kind of，found a downside of getting those new，lines automatically，well it turns out if we read the。

python，what's，powerful about python 2 is that it，supports not just positional arguments。

where you just do a comma，separated list of multiple arguments to，called。

named arguments whereby if a function，like print，takes multiple inputs like uh this one。

this other one and this other thing，each of those inputs can have names and。

you the user of that function，that，print in python supports an argument。

called end and you can explicitly say，what value you want to give to that。

parameter by mentioning its name，and here i'm going to literally do this。

i'm going to tell the print function，an argument to it，to be quote unquote the reason for that。

is that if i read the documentation，the default is actually this if you read。

the documentation it will tell you，print default value for its end argument。

is backslash n this two is a feature，that c did not have，c did not have optional arguments。

they're either there or they're not，uh rather they either have to be there，or they cannot be there。

python supports optional arguments that，even have default values。

and so in this case the default value of，this per the documentation is that end，why。

every line ends with that value if you，want to change that to be nothing the，so-called empty string。

you change it to quote unquote so let me，go ah**d and run this now and voila。

closer it's a little stupid looking，because now my cursor ended up my。

my prompt ended up on the same line so，maybe after this line let me just go。

ahead and print nothing that is，a new line and now if i run mario。pi，voila。

now i get the effect i want and if you，want to see what's really going on here。

i can do something stupid like hello，and now i can end every print。

with hello hello hello hello right not，means，that expression，but the correct version of course is。

just to blank it out。

![](img/ba5c84256d1c630ab124e64119667f77_21.png)

in this way but here's something that's，kind of cool and this is where if you're，kind of a geek like。

life starts to get really interesting，fast i can actually change my python。



![](img/ba5c84256d1c630ab124e64119667f77_23.png)

code to print out these four question，marks in the sky，to be quite simply print quote unquote。



![](img/ba5c84256d1c630ab124e64119667f77_25.png)

this program，boom done and here's where again you're，getting a lot of。

features in the language where you don't，to think about，a lot of syntax if you want to take a。

question mark and do it four times，you can literally use the star operator，which has been overloaded。

numbers，but also automatic concatenation if you，will，with strings in this way so let me go。

ahead and do one final version from，mario recall that the last thing we，something like this。

let me go ah**d and change my mario code，now to be for i in range of three。

because this is a three by three grid of。

![](img/ba5c84256d1c630ab124e64119667f77_27.png)

bricks let's say，and let's go ah**d now and inside of，this loop do another。

nested loop where i do three，columns as well and in here i want to，print out a single hash at a time。

but i don't want to print out a new line，i only want to print out a new line。

here so it turns out that essentially，because python gives you the backslash，ends for automatically。

essentially any logic you wrote in the，past now needs to be reversed if you。

ever printed a new line now you，don't want to print a new line and if，you ever didn't print a。

new line now you do in some sense so let，me go ah**d and uh，not make wrong language python of mario。

dot pi and voila，my three by three grid so this is to say，that in python。

we can nest loops just like we did in c，i can use multiple variable names like i。

and j being conventional there's no。

![](img/ba5c84256d1c630ab124e64119667f77_29.png)

again the logic，the ideas are still the same it just，to，for instance uh some of the new syntax。

all right questions on，mario or on loops or on recreating these，programs as well。

any questions or confusion that we can，now well let me go ah**d and do，recall that in。

c we ran into a problem pretty early on，with integers and let me create a。

program here called int dot pi，and let me initialize a variable called，i to one。

and let me go ah**d and do this forever，let me do this forever inside of a while。

true block let me print out whatever i，one，to i on each iteration let me go ah**d。

and run this program，and let me increase the size of my，window for now and just run this thing。

whoops that was mario，let me run this thing python，counting up。

to infinity and honestly this is gonna，take a while you know what's faster than，counting by one。

maybe multiplying by two so let me go，ahead and multiply by two instead。

to kill the program just like in c i，used control c and that's why i see，keyboard interrupt。



![](img/ba5c84256d1c630ab124e64119667f77_31.png)

it respected my wanting to cancel the，program let me rerun this now and just，count really big。

and even though the internet's being a，little slow which is why it's a little，shaky。

that's a really big number already if i，keep doubling i，what would have happened already at this。

point if i were using c，to implement this program if in c i，declared a variable。

called i and it was an int and i kept，and again，any thoughts yeah what would have。

yeah i think it would have crashed，be taking，much memory good thought so it wouldn't，crash per se。

something would go wrong it wouldn't，crash because it's still an ant and in c。

at least it would still be taking up on，a typical computer 32 bits or four bytes。

have started printing，zero by now or even negative numbers，c，is that integers are a finite size only。

32 bits or four bytes which means if you，keep going from 1，2 4 8 16 a million uh 2 million。

4 million 8 million and so forth，billions，and as soon as you cross the 2 billion。

threshold or maybe the 4 billion，threshold if using，assigned or unsigned numbers it's going。

to get too big you're going to have，integer overflow，overflow，not a thing anymore in the world of。

python your numbers will get as big as，you need them to get they will，you。

unfortunately floating point imprecision，still a thing so i only divided one by。

two earlier but if i continue to divide，other values and i looked at enough。

decimal points we would still suffer，unfortunately from floating point and。

precision however in the world of python。

![](img/ba5c84256d1c630ab124e64119667f77_33.png)

like in java and other languages there，are libraries scientific libraries that。

allow you to use as much precision，as you need or at least as much memory，as your computer has。

so those problems too have been better，solved in more modern languages than in。

something out of the box，like c code but just by multiplying that，number again and again。

larger numbers，than we ever saw in weeks past well let，me go ah**d and do another。

program here this one called scores。pi，that's going to be an example of really。

keeping track of scores which was an，the class，and in python i'm going to go ah**d and。

give myself a list of scores like this，72 73 and 33，again sort of a playful reference to our。

ascii numbers but in this context，they're quiz score so two ok quiz scores。

and one kind of low quiz score，assuming these things are out of like a。

hundred but notice the syntax i'm using，squ*re brackets in python give me a list。

i don't have to decide in advance how，big it is it's not an array per se but。

it's similar in spirit but it will，automatically grow or shrink。

and the syntax is even simpler suppose i，want to average these scores in python i。

could do something like this，i could print out that the average of，these scores is for instance。

and then i could do something like this，i could do the sum，of scores divided by the length of，of new。

already it turns out in python that，there is a sum，function that will take a list as input。

and return to you，the sum of those items and we've seen，already there's a length function。

l-e-n that tells you the length of a，list so if i add up all my scores。

and then divide by the total number of，scores that should give me by definition。

my average so python of，scores dot pi voila oops uh what did i，do here，ah i screwed up so。

unintended admittedly but let me try to，well this，error message is a little cryptic says。

type error can only concatenate，stir not float to stir so long story，short python in this case。

does not like the fact that i'm trying，to take a string，it，a float on the right so there's a couple。

of ways i can solve this and we saw the，fundamental solution earlier if this。

expression here that i've highlighted，is by definition mathematically a float。

but i want it to become a string，i can just tell python convert that，float to a string。

so much like there's the i2a function，that some of you discovered，which is the opposite of the a2i。

function i can take in python，in this case a float and convert it to a。

string equivalent so now if i run python，of scores。i，voila my average is 59。3333 and you。

already see a bit of imprecision，there's some rounding error at the end，there that is not a perfect。

one-third but there's another way i，could do this and it's a little uglier。

but i could use one of those，f strings i could say go ah**d and plug，in a value here。

and just print out the user's average so，it turns out that inside of these curly。

braces you don't have to print，entire，coding expressions and i would encourage。

you not to paste crazy long lines of，code because it's going to very quickly，get unreadable。

at that point you probably should use a，variable but here i can go ah**d and run，python of scores。

pi and voila，i screwed up again also not intentional，but i can fix this。

yeah i'm missing the uh the f at the，string，answer，so again i have multiple approaches。

there's a third one here i could do，stir，in that context because now if it's。

inside of a format string，python will presume that i want to，that's nice。

or i can just factor this out and i can，say something like this give me a。

variable called average assign it equal，average，so again just like in c so many。

different ways to solve the problem and，which one is best，depends really on what might be most。

readable most maintainable，or easiest to do let me go ah**d and add，some scores dynamically now。

instead of hard coding my three scores，let me ask myself for my scores over the，course of a semester。

from cs50 let me import get int just so，i can get some numbers easily。

let me give myself an empty list of，scores the syntax for which is just open。

bracket close bracket so，nothing inside of it initially and now。

let me go ah**d and do this let me get，of the term now，for i in range of three let me go ah**d。

and append，value，of getint is like this now this too i，could do in a bunch of ways let me get。

rid of this here，um whoops no we'll leave that there this，what i'm doing。

i'm getting int and i'm passing the，return value of int，to a new function called append it turns。

out that lists the squ*re brackets，once you've defined them in a variable。

like scores they too have functions，append，in order to add a number to the list so。

now let me go ah**d and run this python，of scores dot pi，let me manually type in my 72 my 73 and。

my 33 and voila。

![](img/ba5c84256d1c630ab124e64119667f77_35.png)

say make the exact answer but think，about how much of a pain this would have，been in c。

if you had to either decide and advance，the size of the array or not decided in。

advance and use malloc，and re-alloc to keep growing and，function。

which comes inside of that list variable，handles all of this automatically for us，of features。

any questions though that i can answer，um yeah i had a question about um。

so even a pen even if a pen like，to write，does it underneath the hood just do，like。

malloc and reallock or something like，that like is that all is that happening。

inside python yeah that's exactly what，the language，all of that malloc stuff reallock stuff。

maybe it's implemented with an，array underneath the hood like in the，linked list。

like we saw last week but all of that is，happening for you but that again is one。

of the reasons why the code。

![](img/ba5c84256d1c630ab124e64119667f77_37.png)

ultimately runs a little slower because，you have someone else's code in between。



![](img/ba5c84256d1c630ab124e64119667f77_39.png)

bit of that work，are there efficiency differences in，between like the ways that we print。

of like utilizing the f um like，formatting or，don't have to be。

if i'm understanding correctly it's uh，there are some fancy features of it for。

instance there is syntax you can use to，specify how many decimal points you want。

to print after a floating point value，i percent，s percent f and so forth there's，fortunately。

less of it since you don't have to worry，no all right well let me go ah**d and do。

one other example that might be familiar，from some weeks past，let me go ah**d and whip up a quick。



![](img/ba5c84256d1c630ab124e64119667f77_41.png)

example of uppercasing just to tie，together one of our earlier examples。



![](img/ba5c84256d1c630ab124e64119667f77_43.png)

casing，in this case a file called uppercase。pi，let me go ah**d and from the cs50。

library let me go ah**d and import，getstring，and then once i have this let me go。

ahead and get a string from the user and，ask them for，ahead and，do the following let me go ah**d and。

print out after the goal being i want to，uppercase this whole string for the user。

and i'm going to keep this all on the，that's going to print before。

ask the human for some input and then，after show the capitalized version of，the whole string。

so how can i do this well we've seen one，way already i can do literally。

for instance s dot upper and let me go，ahead and save this and now run python，of uppercase。pi。

let me type in high and lowercase and，version，but if you want you can actually。

manipulate individual characters as well，let me go ah**d and a little more，pedantically do this。

for cns print c，now this isn't quite what i want yet but，it's a stepping stone notice now if i。

type in high and，case i see h i exclamation point，all still lowercase so i haven't done。

let me get rid of the，new line just so it all stays on the，same line because that was kind of ugly。

let me do it again okay a little better，let me actually add a new line at the。

very end of the program to move my，more，hi okay i'm not uppercasing anything。

but if i change c to c dot upper，it again hi，and boom now i have another working。

program but the new feature now，is notice this coolness on line five。

if you want to iterate over a strings，initialize i，to zero and then use squ*re bracket。

notation like you did，in c you just say for c and s or for，x in y whatever it is four can also be。

used to iterate over the individual，to do when doing something，like cryptography or the like so we。

string all at once，we can still gain access to our，individual values。

and there's other things you can do in，python as well that we could do in c。

let me go ah**d and create a program，here called argv，was uh，the name of the input to main that。

allows you to access command line，arguments now today we have seen that，don't need to。

but it's conventional it's not required，anymore and so we don't we haven't seen。

argc or rv yet but that's because，they're elsewhere in python，if you want to access command line。

arguments in python，it turns out that you can import a，module called argv。

and this is a little new but it follows，the same pattern as cs50s library。

i'm going to import from the system，library a feature called，with python。

but to use it you have to import it，explicitly and now i'm going to do this，if the length of arg v。

equals 2 then i'm going to go ah**d and，print out just like we did a few weeks，ago。

hello and then argv bracket，1。 somewhat cryptic but i'll come back，to this in a moment。

uh else i'm gonna go ah**d and print out，a default of hello world so we did this。

some weeks ago in week two，whereby we ran a program that if the。

user typed their name at the prompt it，would say hello david or hello brian。

if they didn't it would just say hello，world so to be clear if i run this thing。

and run it without any command line，arguments i just see hello world。

if i run it again though and type my，name in and hit enter now i see hello。

david so how is that working，well this first line of code gives me，access to argv，library。

if you will the sys package so to speak，but it works the same way。

there's no arg c but no problem if v，is a list of command line arguments，which it is length len。

will tell me the length of that list，which is equivalent to argc so i can，reconstruct the same idea。

from my version in c，and here then i have a format string，that prints out hello。

comma and then whatever's in curly，braces and rgb is a list，and just like in c which had arrays a。

list is just an array that can，dynamically grow and shrink for you you。

can still use squ*re bracket notation，the human typed，so let me change this just for clarity。

to be zero and if i rerun this now and，type in david，it says weirdly hello rgb。pi so what you。

don't see is the word python python is，the interpreter but that's not part of。

your program's execution per se，argv 0 is going to be the，name of the python program you're。

running and arg v1 is going to be the，first word thereafter and so forth。

so we still have access to that feature，but now we can，convert it now to python and in fact if。

i want to print out all the command line，arguments i can just more simply do this。

for arg in argv go ah**d and print arg，glance，now let me go ah**d and type in。

something like david malin two words，enter you now see everything printed，forth so。

here too notice how neatly we can，iterate over a list in python there's no。

i there's no squ*re brackets necessarily，you can just say for arg and argv just。

like a moment ago i said for c，in s pretty much the python for loop。

is smart enough to figure out what it is，you want it to iterate over whether it's。

a string or a list and my god，it's just so much more fun or pleasant。

to program now when you don't have to，like，incrementing and plus plus and，semicolons and all of that。

here，examples quickly，but they're really just translations，again and for coming upcoming problems。

more，methodically compare before and after as，well，anything at all on your end brian，nothing here。

all right so let's look at some of our，final past examples and then we'll，look at some。

even more powerful things that we can do，because now of languages like python。

let me go ah**d and create a program，this time called exit。pi，exit。i and this program's purpose and。

life is just going to demonstrate exit，statuses recall that eventually in c。

we introduce the notion of returning 0，main，we do have that ability now in python 2。

that you'll start to see in more，larger programs here too i'm going to go，ahead and import cis。

the whole thing this time just to show a，different way of doing this i'm going to。

say if the length of sys。org v，does not equal 2 let me go ah**d and，yell at the user。

missing command line argument and then，after this i'm going to go ah**d and do，sys。exit。

of 1 otherwise i'm going to go ah**d and，print out，a formatted string that says hello comma，r v。

bracket 1 with cisnow in front of it for，reasons i'll explain in a moment。

and then at the end i'm going to go，ahead and by default print sys。exit。

zero all right so what is going on here，different things，i decided not to import rv specifically。

but just to import the whole library，but because i did that i can't just。

write the word argv anywhere，i now have to prefix it with the name of。

the package or library that it's in，so that's why i started doing sys。rv，sys。rgv，the sis。

library which gives me access to an exit，function which is the equivalent to。

returning from main so this is a bit of，a dichotomy in c，you had a return zero or one or some。

other integer from main，in python you instead call sis。exit，with the same kinds of numbers so a。

little bit different syntactically but，it's the same fundamental idea。

what's the purpose of this program well，if i run this thing its purpose is just，word。

after my program's name so notice if i，just run python of exit dot pi。

it's yelling at me missing command line，argument if i run it instead with my，name after that。

now it says hello david so stupid，program it's only meant to demonstrate。

how you can now return different values，program，because you're no longer in maine you。

can't return per se but you can now in，python exit，as needed so that's the comparable line，there。

all right any questions then on exit，statuses again we're just kind of。

churning through the list of features we，saw and see even if they don't come to，you supernaturally。

there is，uh there are analogs here in the python，world，no all right well recall that after that。

we started focusing really in the class，on algorithms and that's when like the。

size of our data sets and our，the efficiency of our our code started。

to really matter let me go ah**d and，write a program called numbers。pi。

that for instance contains an import at，in a moment，and then it gives me uh let me give。

myself an array of numbers like 4682750，and you might recall that those were the。

numbers behind the doors in week three，and suppose that i want to search for。

the number zero well in c，to implement linear search you would use，a for loop and a variable like i。

and check all of the locations python's，way simpler，if zero in numbers go ah**d。

and print out found and then i'll go，ahead and，else print out not found。

and that's it so let me go ah**d now and，do python of numbers。pi。

hopefully i will see indeed sheet found，because it's in fact there so that's it，phrase，true。

or false that you want so there is our。

![](img/ba5c84256d1c630ab124e64119667f77_45.png)

linear search what if i want to do it，for names well let me go ah**d and give。

myself a second file similar in spirit。

![](img/ba5c84256d1c630ab124e64119667f77_47.png)

actually，if i really want to be identical to our，c version let me go ah**d and exit。

with zero here and let me exit with，one here but strictly speaking that's，what i did。

when we did this in c instead in names，let me go ah**d and do something similar。

let me give myself a names，list with a whole bunch of names bill，and charlie。

and fred and george and ginny，and percy and lastly ron，all the way at the end and then let me。

linear search，if ron in names go ah**d and print out，found else go ah**d and print out not。

found and i won't bother printing out，or exiting with 0 or 1 this time but let。

me go ah**d and run python of names，whoops python of names and voila。

we found ron and notice i'm not cheating，i don't think i've screwed up。

uh if i go ah**d and say ron old if that，was in fact his formal name。

now i search for ron not found it's，looking indeed for an exact match。

so that's pretty cool that we can，readily，but recall that a little bit ago i。

proposed that python has other data，types as well，among which are these things called。

dictionaries or dicks，d-i-c-t which represent a collection of。



![](img/ba5c84256d1c630ab124e64119667f77_49.png)

key value pairs similar in spirit to a，has，spanish keys and english values。

converting one to the other，this english dictionary has english，words and english。

definitions but the same idea a，collection of keys and values，using one you can find the other well。

let's go ah**d and translate this into。

![](img/ba5c84256d1c630ab124e64119667f77_51.png)

python in a program called，phonebook。pi and implement something，recall。

in pi in c we used a couple of arrays，initially then we scratched that and we。

used an array of structs，is a more，follows，let me go ah**d here and uh from cs50。

import get string then let me go ah**d，and give myself a dictionary of people，different。

but i'm going to go ah**d and，preemptively use curly braces，they are back for the purposes of。

dictionaries and then here's how you，define key value pairs，is gonna be，*****。

thousand that's his number，and then i'll be one of the other keys。

for now we'll keep it a very small phone，book or dictionary，*****，oh and that's it。

so the curly braces can technically be，on different lines i could move this up。

here i could get rid of this，but there are certain style conventions。

in python the point though here is that，a dictionary is defined with curly。

braces at the beginning and end，the keys and values are separated by，colons。

and the key value pairs are separated by，commas so that's why it's conventional。

to write it the way i did，it's just a little more obvious that。



![](img/ba5c84256d1c630ab124e64119667f77_53.png)

this is a dictionary with two keys each，of which has，a value it's just associating left with。

right so to speak，now what does this mean suppose i want，to search for someone's name well let me。

go ah**d and give myself a name variable，call getstring askingthehuman for a name。

and let me implement my own virtual，phone book much like the contacts app in。

your phone let me go ah**d and then say，once i have the name if name in people。

that's great if i found the name in，people let me go ah**d and print out，people。

bracket name and this is where，dictionaries are gonna get really，explain，python of phonebook。

pi enter whoops，python of phonebook。pi let me search for，brian's number。

boom there's brian's number let me go，ahead and run it with david's name，and run it with。

phone number，just yet he's unlisted as would be。

![](img/ba5c84256d1c630ab124e64119667f77_55.png)

anyone else that i type in，so what has gone on here well at the top，people。

and it's a dictionary a set of key value，pairs left and right。



![](img/ba5c84256d1c630ab124e64119667f77_57.png)

then i'm just getting a string from the，user using get string as before。

and then this is powerful too this is。

![](img/ba5c84256d1c630ab124e64119667f77_59.png)

essentially on line，9 searching the whole dictionary，me，down here the name associated with that。

sorry the number associated with that，person's name and let me make this more。

clear by factoring this out，let me give myself a variable called。

number and then more explicitly print，out that variable's name，here's what's different today if name。



![](img/ba5c84256d1c630ab124e64119667f77_61.png)

and people，is written here what this does is it，python searches。

all of the keys for that name it doesn't，search values when you say。

if name in a given dictionary like，people is it searches only the keys。

if you then found the key i know，definitively that david or brian。

are in the dictionary and notice this，it's just like in c's array syntax。

you can now use squ*re bracket notation，to index into a dictionary，using a word like david or brian。

and get back a value like our phone，number in c，and thus far even in python whenever。

we've seen squ*re bracket notation，it would only be typically for numbers。

because arrays or lists have indices，numbers that address the first location。

middle and last and so forth everything，dictionaries，is that they're otherwise known as。

associative arrays a dictionary is a，collection of key value pairs and if you，want to look up a key。

you simply use squ*re bracket notation，just like we used to use squ*re brackets，for numbers。

and because python is a pretty fancy，language，it handles the searching for you and，search。

to give you，constant time by using what we called，last week a hash table。

dictionaries are typically implemented，a hash table，and recall that even though it was，really a a。

goal of achieving constant time if you，choose a really good hash function，hash into。

you can come close to constant time so，again among the features，gives you。

very high performance it's not linear，search and in fact，set recall that when we began playing。

speller，using what like 10 or 20 lines of code，max instead of the many more that you。

might have written for pset five，speller used a set and a set is just a，collection of values。

long story short it's similar in spirit，to a dictionary in that it too。

underneath the hood uses a hash table to，get you answers quickly，so if you think back to what that。

speller example was，of code，line of code，was implementing pretty much the，entirety of。

your spell checker all of those pointers，linked lists，you get that。

with the language itself all right any，questions then，on dictionaries they will recur and they。

structures，because this ability to just associate，something with something else，organize。

your data any questions，here yeah sophia，is there only a set hash function that，dictionaries。

or can we change that hash function in，any way good question um。

the it comes with a hash function for，for you，so you that's the kind of detail that。

you should leave to the library，because someone else has spent all of，the time thinking about how to。

dynamically adapt the data structure，move things around as needed。

so that you no longer need to stress to，implementing，speller yourself and turns out other。

things get easy too this is not a，commonly needed feature necessarily but。

it is something we can do let me go，ahead and write a quick program called，swap。pi，ago we gave，of 2。

and then i printed out something like x，is x，y is y but this week i'm using format。

strings just to print that out，then i did something like swap x y and i。

just kind of hoped for the best，and then i printed out those values。

again well it turns out in python，because you don't have pointers and you。

don't have addresses per se，that you have access to you can't resort。

to the solution like last week and pass，these variables around by reference so。

to speak by their address，that's just not possible why is that a。

thing well it would seem to be taking a，feature away from you but honestly if。

this past week was any indication，including the week prior，pointers are hard and like segmentation。

of that stuff right，is difficult and at worst your programs，can be compromised because someone can。

access memory that they shouldn't，so python takes that feature away java。

also takes that feature away from，programmers to sort of protect you，against yourself。

from screwing up like you may have and，past week，but it turns out in python there are，want to swap。

x and y that's fine swap x and y，and so now if i run python of swap on，this program。

voila boom it's distilled into one other，line so even though they take something。

away from us that you can do a lot of，with，we can nonetheless hand you back a more，powerful feature。

with this one liner for swap and notice，that it's x comma y on the left。

but y comma x on the right and that has，the effect of doing what brian did with。

the glasses of liquid，of doing the switcheroo even without a，temporary variable，happening。



![](img/ba5c84256d1c630ab124e64119667f77_63.png)

underneath the hood well let's go ah**d，from week。

![](img/ba5c84256d1c630ab124e64119667f77_65.png)

four and then introduce a few of our own，here in week six，let me go ah**d and implement another。

persistent。

![](img/ba5c84256d1c630ab124e64119667f77_67.png)

let me go ah**d here and open create a，file here called。



![](img/ba5c84256d1c630ab124e64119667f77_69.png)

name this，name comma number so csv file recall is。

![](img/ba5c84256d1c630ab124e64119667f77_71.png)

like a very simple spreadsheet，i'm going to go ah**d and just create。

that so i have it nearby and then i'm，going to create a new file called。



![](img/ba5c84256d1c630ab124e64119667f77_73.png)

phonebook。pi，going to do this，i'm going to import from cs50 the，getstring function as before。

but i'm also going to import a library，called the csv library it turns out。

python comes with a whole lot of，functionality，related to csv files to make your life。

easier and make it easier to do things，with csvs，among the things i might want to do is。

this let me go ah**d and open up that，file phonebook。csv，in append mode similar to f open two。

weeks ago，and let me go ah**d and assign that to a，variable called file。

then let me go ah**d and just get a name，from the user so let me use getstring to，get someone's name。

name here then let me go ah**d and get，number here，so using number and then lastly and this。

is the new code，let me save that name and number to a，file and recall from pset 4。

that saving files and writing bytes out，to files is pretty involved like it，recover。

or blur any of those filters that，involved creating new files，turns out the csv library makes this。

pretty easy let me go ah**d and give，myself what's called a writer。

and i'm going to give myself the return，value of calling csv。writer a file。

so what is this doing file again，represents the file i'm trying to open。

csv writer is some function that comes，input，a file that you've already opened and it。

kind of wraps that file，with some fancier functionality that's，programmer。

to write to that file what am i going to，do i'm going to use that writer variable。

to write a row that specifically，contains a name and a number，and i'm using a list because if you。

rows，a list is kind of the right idea each of，the cells from left to right is kind of。

like a list a row is like a list so i'm，going to deliberately use a list here。

and then lastly i'm going to close the，file just as i've done in the past。

so it's a little cryptic here but again，getstring getstring isn't uh is。

is is old now this is old now so，the only things that are new are。

importing the csv i'm opening this file，in append mode，similar to what i did in c and then。

these lines here involve，wrapping the file with the csv，functionality。

writing a row to this file with right，row and then closing it。

so let me go ah**d and try this now let，me open up phonebook。csv，which for now only contains these。

moment ago，and let me go ah**d and run this python，of phonebook。pi。

let me go ah**d and add brian and brian，will be plus one，*****，thousand enter。

and now let me go to my csv file over，here，ah damn it i screwed up uh pretend i。

didn't hit enter there now it works，let me go ah**d now and do this again by。

inputting i should have hit enter when i，created the file manually but i screwed。

up when creating it so let me wave my，hand at that and convince you。

that i did this correctly in code by，adding myself david，uh，2750 enter let me go back to my csv file。

and voila now it's formatting correctly，line for me。



![](img/ba5c84256d1c630ab124e64119667f77_75.png)

and notice too if i download this file，let me download phonebook。csv。

like i did in a past week let me，download this to my own mac，let me open this csv file and whether。

you have apple numbers installed or，microsoft excel，you'll open something that looks like。

this and voila i've dynamically created，using python code now。

my own sort of csv file and it turns out。

![](img/ba5c84256d1c630ab124e64119667f77_77.png)

there's a way to tighten this up just a，way i did，but it turns out that you can also open。

and close files a little differently，you can do this with file with rather，with open as file。

then i can indent all of this here and i，can get rid of my close。

line so not a big deal to do it the way，i did with open and close。

but the way i've done this here is a，little more pythonic，this with keyword which is not something。

analogous to anything we've seen in c，the with keyword when you open a file it。

will automatically close it for you，eventually so you might see that in some。

online references or other materials，but again it just does that for you，automatically。

well let's go ah**d and do this i like。

![](img/ba5c84256d1c630ab124e64119667f77_79.png)

the fact that we can now manipulate csvs，and it turns out that if you've ever。

used google forms that's a very popular。

![](img/ba5c84256d1c630ab124e64119667f77_81.png)

way of like collecting data from users，in fact let me go ah**d and go to a url，cs cs50。ly hogwarts。

which is going to show you a form like，this here if brian you wouldn't mind。

typing that into the chat，go to that url cs50。ly，hogwarts and if everyone wouldn't mind，your。

what house you wish you were assigned to，by the sorting hat，would you be in。

now if you've used google forms before，results，certainly in the google form itself and。

already 122 of you have buzzed in，and we can see a distribution in a graph。

and so forth but what i want，is not the distribution pictorially。

there i'm going to go ah**d and open up，a spreadsheet and so if you've never。

used google forms before，you can click a button and then you can。

get a list of all of the responses that，are coming in live right now。

and by default google keeps track of the，time st*mp when the form was submitted。

and what house was actually used so i'm，going to go ah**d now and do this。

let me go ah**d and download that in，another tab give me just a moment to。

do it on this screen here i'm going to，go ah**d and，download that csv file。

onto my mac locally by going to，file download csv，that's going to put it into my downloads。



![](img/ba5c84256d1c630ab124e64119667f77_83.png)

and upload this，into my ide by just dragging and，browser，i'm going to do this by dragging and。

dropping the file，all right now i have that file there and，let me go ah**d now。

and make sure the file's there i have，this file called sorting hat responses。

form responses one and so forth，well let me go ah**d and write a program。

now that manipulates this data much like，you might if running a student group。

that's collecting data in a google form，or you're just collecting information in。

general and have it in csv format，how might you now tally up all of the。



![](img/ba5c84256d1c630ab124e64119667f77_85.png)

results especially if google weren't，results were，well let me go ah**d and write a program。



![](img/ba5c84256d1c630ab124e64119667f77_87.png)

called hogwarts which is not something，that we've seen ever before in c let me。

go ah**d and import this csv library，let me give myself initially a。

dictionary called houses that contains a，whole bunch of keys，like gryffindor with initial count of。

zero，huffle puff with an initial count of，zero，raven claw with an initial count of zero。

and also also slither in with an initial，count of zero so notice in a dictionary，or dict in python。



![](img/ba5c84256d1c630ab124e64119667f77_89.png)

the keys and values don't need to be，strings and strings it can certainly be。

strings and numbers because i'm going to，count of，all of the votes for one house or。

another so let me go ah**d and do this，let me go ah**d and open up，with open the sorting hat file。

inform responses 1 dot csv，long file name but that's the default，from google as。



![](img/ba5c84256d1c630ab124e64119667f77_91.png)

file so i'm going to use my one liner，instead of having to open and close。

i'm going to give myself this time a，reader which we did not see before。

a csv library has a reader function，that allows me to read a csv file，automatically。

i'm going to go ah**d and skip the first，the first row，timest*mp。

and house which i do want to ignore i，want the real data from you all。

and here's what's cool about csvs and，python i can if i want to iterate over，all of the rows。

that are in that spreadsheet i can do，for row in reader，and now let me go ah**d and get at for。

instance，the uh house in question so the house in，a given row，is going to be the rows first。



![](img/ba5c84256d1c630ab124e64119667f77_93.png)

entry zero indexed so what is going on，here well let me go back to the google。

spreadsheet a moment ago and in the，google spreadsheet，there's two columns and the way the csv。

reader works，is it returns to one row at a time and，that's conceptually pretty。

straightforward it maps perfectly to the，idea of a spreadsheet，but each row is returned to you as a。

list a list，in this case of size 2 so row bracket 0，would give me a given time st*mp。



![](img/ba5c84256d1c630ab124e64119667f77_95.png)

row bracket 1 would give me a given，house name。

![](img/ba5c84256d1c630ab124e64119667f77_97.png)

so that's why here in the ide i'm going，ahead and declaring a variable called，bracket one。

because i don't care about the time，st*mp we all just did this roughly at，the same time，index。

into the dictionary just like in c you，could index into an，i can use。

strings so i'm going to go ah**d and say，go into the houses dictionary which i，defined up above。

increment，it by one and that's it，at this point i have opened the csv file。

and read it using the library in this，loop i'm iterating over every row in the。

spreadsheet that you all，created by filling out that form again。

and again i'm just using a variable to，get at whatever is in。

the second column otherwise known as row，bracket one because row record zero，would be the time st*mp。

and then i'm going into the dictionary，called houses which we defined up here。

i'm indexing into it just like an array，but it's a list in this case。

using its house name which looks up the，appropriate key，of，incrementing its value so it's a nice。



![](img/ba5c84256d1c630ab124e64119667f77_99.png)

way of going into the dictionary，and incrementing go in and increment so。

now let's go ah**d at the very end here，and just print out the result。

for house in houses is the fancy way to，iterate over all of the keys。

in a dictionary go ah**d and print out a，formatted string as follows。

let me print out the house name followed，by a colon，followed by a the house's uh dictionary。

indexing into it with house so again，second，python of hogwarts let me cross my。

fingers that i didn't screw，this up and i did，the ide knew before i did all right now，and。

damn it all right the file is called，something slightly different，versus when i。

practiced uh let me copy this，so close sorting hat responses ah。

it has parentheses which i forgot all，the program，damn it okay no such file or direct oh i。

forgot the csv，dot csv okay now cross fingers and，oh thank god okay so gryffindor，uh，oh。



![](img/ba5c84256d1c630ab124e64119667f77_101.png)

beat out hufflepuff very interesting for，whatever sociological reason。

but here we have a program now that，with silly，harry potter data but again imagine。

collecting any data you want from users，downloading it as a csv to your mac or，pc or your ide。

then writing code that analyzes that，data however you want i did a very，simple summation。

but you could certainly imagine doing，something fancier than that，like doing summations or averages。

standard deviations all of that，functionality could we get，as well are any questions on，dictionaries。

powerful，features we've yet seen in a programming，anything at all on your end brian。

no hands raised here all right well let，me go ah**d now，and i'm going to transition actually to。

my mac where i have in advance，pre-installed python，just so that i can do things locally。

it'll make things a little faster i，don't have to worry about internet。

speeds and the like and this is indeed，pc，interpreter，run it on your own mac and pc however i。

would recommend you continue using this，ide certainly for problem sets sake。

until the end of the semester maybe，transitioning to your mac or pc。

for final projects only only because，what i did this weekend was spent waste。

a huge amount of time just getting，stupid libraries to work on my own mac。

which is often easier said than done，just because when programmers are。

writing code that's supposed to work on，every possible mac and pc in the world。

you and i and everyone else have，slightly different version numbers。

different software installed different，incompatibilities，so those kinds of headaches very quickly。

arise when you're doing things locally，um so let me encourage you to wait until。

terms end with final projects perhaps to，sort of move off of the ide。

and do what i'm about to now do just，because you'll be able to，see these demos more clearly here i'm。

going to go ah**d and on my own mac i'm，called，a library，that supports speech synthesis and if i。

want access to that functionality it，suffices to import，pi ttsx3 which is the name of that。

person's open source free library，that i downloaded and installed on my，i。

literally never used this before this，past week and i，found that i can declare a variable。

called engine for instance，i can then call pyttsx3 dot，init to initialize the library why。

that's just because of how the，programmer designed it you have to，initialize it first。

i then can use that engine to say things，like say，should run，the engine and wait for it to finish。

before my own program quits，all right let me go ah**d now and close，that and run python，of speech。

pi on my own mac，here hello world，and indeed，i can probably make this even more。

interesting let me go ah**d and say，something like this let me open up，speech。pi again。

and add some functionality i won't use，the cs50 library but i will use maybe，the input function。

let me go ah**d and say name gets input，what's your name question mark and then。

let me go ah**d and say not hello world，but let me use an f，string which doesn't have to be used in。

print you can use it in，any function that takes a string let me，go ah**d and say hello。

to that name all right let me go ah**d，and run python speech。pi again。

whoops let me go ah**d and run python of，speech。pi，again what's my name david hello。

david we're in choice of inflection but，indeed it synthesized it let's try brian，hello brian。

okay so we could probably tinker with，the settings to make the voice sound a，little more natural。

but that's pretty cool well let me go，into some code i wrote in advance this。

time using a different library this one，related to，faces and facial detection certainly uh。

very much invoked when it comes to，and other，websites automatically tagging you very，governments。

federal governments and law enforcement，a crowd，and let me go ah**d and open up a file。

here for instance a little more benignly。

![](img/ba5c84256d1c630ab124e64119667f77_103.png)

office，so here's a photograph of some people in，an office and there's a lot of faces。

there but there's a lot of boxes of，those faces，but let me go ah**d and look at quickly。

a program called the tech dot pi，most of this file is comments just so。

that if you want at home you can follow，along and see what it does。

but let me just highlight a few salient，lines here's that pillow library again。

where i'm accessing image related，functionality from a pre-installed，python function。

and this one's just kind of amazing if，technology，just import face recognition that is a，you access。

to that kind of power down here now i，only knew how to figure this out by，reading some documentation。

but you access the library called face，recognition dot load image file which is。

a function that does what it means i'm，opening up office。jpg，and then scrolling down here to the。

of the，blue is comments recall this line of，code here，is all that's required in python to use。

the face recognition library find all of，the face locations in a given image and。

store them in a list，called face locations this line of code。

here is just a python loop that iterates，over every face。



![](img/ba5c84256d1c630ab124e64119667f77_105.png)

in the faces that were detected and then，these several lines of code here。

long story short just crop out，individual faces and create a new image，with the found faces。



![](img/ba5c84256d1c630ab124e64119667f77_107.png)

so without getting too much in the，details of the library which are not。

that intellectually interesting the。

![](img/ba5c84256d1c630ab124e64119667f77_109.png)

features are interesting to us for now，let me run python of detect。pi let me。



![](img/ba5c84256d1c630ab124e64119667f77_111.png)

thing，and voila if i zoom in here we see，every other，photograph。

cropped out as indeed an individual face。

![](img/ba5c84256d1c630ab124e64119667f77_113.png)

so if you've ever noticed a little，squ*re on yourself and facebook when，uploading a photo。

this is exactly the kind of code that，facebook and others，execute that。

well you know what how about this in the，same office photo，um you know there's one person that。

always seems to stand out no one really，likes him and that's toby。



![](img/ba5c84256d1c630ab124e64119667f77_115.png)

what if we had sort of a mug shot of，toby in a separate file like this。



![](img/ba5c84256d1c630ab124e64119667f77_117.png)

can we find toby in a crowd among these，people in the office well we can let me。

go ah**d now and run a program called，recognize。pie，which you're welcome to look at online。

it's similar lines of code it's not，terribly many。

![](img/ba5c84256d1c630ab124e64119667f77_119.png)

that is going to do some thinking，it's opening up both the office jpeg and。

this one and notice what just happened，if i zoom in，great big，green box around his face have indeed。

been recognized，so again i'll just glance at the code，this time if i open up recognize。pi。

it's a few more lines of code but again，other things。



![](img/ba5c84256d1c630ab124e64119667f77_121.png)

i'm loading toby。jpg and i'm loading，office。jpg，and then there's some more code here。

that's looking for toby looking for toby，and then drawing a big green box around。

the face that is ultimately found，so again at the end of the day it's just。

loops it's just functions it's just，variables but now the functions are。

pretty darn fancy and powerful，because again they're taking advantage，of all of these other features。

that we ourselves have implemented in a，language like c，uh or have um now seen glimpses of。

within the world of python，well let's do another one let me go，ahead and open up real quickly。

one of these，2d barcodes a so-called qr code let me，go ah**d and create a file called，qr。

pi and in this file let me go ah**d，and do this，import the operating system library for。

reasons we'll soon see，and let me import the qr code library，which will do。

all of the hard work for me let me go，ahead and create an image called，making。

and let me paste in this url of one of，the course's lecture videos for instance。

and then let me go ah**d and save this，image as qr。png，portable network graphic as indeed a png。

other things，and then let me actually open this thing，up open up system。

actually nope that's fine let me keep it，simple we don't need the os library。

no we do let's go ah**d and open it up，with openqr。png，so three lines of code make a qr code。

with that url。

![](img/ba5c84256d1c630ab124e64119667f77_123.png)

save it as qr。ping and open the file，three lines of code let me go ah**d and，run python of qr dot pi。



![](img/ba5c84256d1c630ab124e64119667f77_125.png)

voila it was pretty fast if you would，like to take out your own，iphone or android phone turn on the。

camera if your phone supports this，and scan this 3d barcode by awkwardly，just pointing your phone。



![](img/ba5c84256d1c630ab124e64119667f77_127.png)

at the lecture as we speak it should，open up youtube for you，hopefully and with such ease。

i apologize for to those yes thank you，for showing me what you're now seeing i。

apologize for doing that yet again，never gets old but all we've done is，embed in a two-dimensional。

format details of which we won't go into，in class a url，which suggests that you can store。

anything inside of these 2d barcodes and，your camera，can the software running on your phones。

these days decode these things，for you well let me do something else，this time involving。

another sense this one listening let me，go into a file called，listen。pi and let me go ah**d and do。

and get，by using，then，let me just send it all to lowercase，just to keep things simple。

and now let me do this once i get the，user's words let me go ah**d and say if，the word hello。

is in their words go ah**d and，print out hello to you too so if they。

say hello i want to say hello back，l if how are you in words，something like。

i am well thanks as the computer uh，l if goodbye in words，then let me go ah**d and say something。

reasonable like，goodbye to you two，and then lastly else let me go ah**d and。

print out just something like huh，unrecognized so if you will here's the。



![](img/ba5c84256d1c630ab124e64119667f77_129.png)

an ai，right a program that's gonna somehow，interact with me the human。

typing in phrases to this thing so if i，did it correctly let me go ah**d and run，python of listen。pi。



![](img/ba5c84256d1c630ab124e64119667f77_131.png)

i did not do something correctly uh，oh not is in okay sorry，let me go ah**d and run python of，listen。

pi say something i'll say hello，oh hello to you too what a nice friendly。

program uh let me ask it how it is，how are you question mark it just seems，to detect that。

let me go ah**d and say okay goodbye for，now and it detects that too。

because goodbye is in the phrase that，the user typed in but if i say something，like hey there。

it's not recognized so pretty cool we，can use very simple，string comparisons using the in。

preposition to detect things，but i bet you know i bet if we use the。

right library we can really make this，more powerful too let me go ah**d and，just like i imported。

facial recognition let me import speech，recognition in python which is yet。

another library that i pre-installed，let me go ah**d and now do this，recognizer equals speech。

recognition dot recognizer，and this is just creating a variable，literally。

the documentation for using this library，then let me go ah**d and do this。

also from the documentation with speech，recognition，dot mic micro phone。

as source so this is opening up my，microphone in some sense，again just following the documentation。

let me go ah**d and say，say something to the user and then after，that let me go ah**d and。

equal to the，recognizers listen function，passing in my microphone as the source，and now down here。

let me go ah**d and say print out you，said，and below that i will print out，recognizer。

dot recognize that's the hardest part，today so far for some reason google。

audio all right so what's going on，this line of code these lines of code。

here are opening up a connection to my，microphone on my mac，it's then using the speech recognition。

library to listen to my microphone，and storing the audio from my microphone，in a variable called。



![](img/ba5c84256d1c630ab124e64119667f77_133.png)

audio these lines of code down here are，literally printing you said，and then it's passing to google。

thegoogle。com。

![](img/ba5c84256d1c630ab124e64119667f77_135.png)

the file of audio that i just recorded，on my microphone，and it's printing out whatever comes。

back from google so let's see what comes，out again crossing my fingers that i，didn't mess up。

it's pretty good speech recognition it's，up to google，but now let's make things a little。

fancier and actually respond to the，add back，some of the previous logic and say。

something like this if hello，in words then go ah**d and print out，like before。

uh hello to you too l if，uh how are you in the words that have，out，i am well thanks and down here。

if i said goodbye in words then go ah**d，goodbye to you too，recognize，this right。

let's now go ah**d and do python of，listen。pie，hello there oh damn it，okay stand by uh oh。

sorry uh let me do a find and replace，i called the variable words instead of。

audio and i just executed a fancy，command to replace it everywhere so。

audio is what i meant to say this time，now let's go ah**d and run this python，of listen。pi。

hello world damn it，audio data is not interval this is a bug，notes，her，first time。

but the wrong way let me change my，variable back to words，okay what i forgot to do was call one。

line of code here that's literally，sitting in front of me，i need to convert the recognizer's。

return value，recognize google audio i need to store，the return value。

of passing the audio to google and，storing the resulting text here。

and so i have restored using the words，variable here，all right now let me go ah**d and run，python。

very nice how are you today。

![](img/ba5c84256d1c630ab124e64119667f77_137.png)

all right so there we have an even more，compelling artificial intelligence。

granted it's not that intelligent it's，just looking for pre-ordained strings。

but i bet we can do something even more，and in fact let me go ah**d and step，can't help。

do something in real time on a big fancy，pc here in the theater。

we are running some other python program。

![](img/ba5c84256d1c630ab124e64119667f77_139.png)

on a cpu that's fast enough to do this，in real time and we've connected one of。

our cameras to that pc，so that what you're about to see is the，result of one of our cameras。

being wired into this pc running that，camera's input into python software，running on that pc。

and we have trained the pc using this，python software，to recognize certain images in the past。

and let's see if we can't do this，me on，go ah**d and，all right i think we are live。

so again you see my mouth moving in，lockstep with，uh einstein here his lips are matching。

mine his head movements are moving，matching mind we can even be inquisitive，if my eyebrows go up。

my mouth go through this way this way，and you can see that the python program，in real time。

is mapping my facial movements onto，known as a，deep fake rung wrong could we try out。

who similarly is matching a big smile，gets a little fake at some point but。

again if we pre-rendered all of this，instead of doing it live the pc could。

probably do an even better job，uh how about could we uh invite harvard，president larry bakau。

this is cs50 harvard university's，introduction to the intellectual，enterprises of computer science。

and the art of programming how about，this is cs50 yale university's，introduction to the intellectual。

enterprises of computer science，and the art of programming now at this。

point the real world implications of，this should be getting increasingly，this on。

instagram and tick tock and the like，days，which are essentially doing the same。

thing and you can see the image doesn't，quite keep up with me if i start moving。

a little too quickly right now，this has very real world implications in。

the world of politics government，business and really just the real world。

more generally because i'm essentially，putting in someone else's mouth。

my own words and while it's clear that，these examples thus far。

aren't really that compelling if i start，to move too much you see that things。

start to get out of sync，just imagine that if we wait one year。

our computers are going to be twice as。

![](img/ba5c84256d1c630ab124e64119667f77_141.png)

fast with even more memory and the like，software is only getting better and more。

powerful the libraries and the，trained，and so among the themes for the coming。

weeks of the class is not just，how to do some things with technology，and how to write code。

but frankly asking the much bigger more，important picture question of。

should you do certain things with，technology and should you，actually write such code we did ask。

for their permission，in advance to spoof them in this way but，we thought we would more playfully end。

with just a couple of other examples，uh that you perhaps see on instagram，tick tock and the like。

wrong shin could we invite pam to join，today。

![](img/ba5c84256d1c630ab124e64119667f77_143.png)
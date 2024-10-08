# 【双语字幕+资料下载】哈佛CS50-CS ｜ 计算机科学导论(2020·完整版) - P17：【CS50网络安全讲座】如何保证电脑和手机的安全 - ShowMeAI - BV1Hh411W7Up

![](img/1640fde899975b31be8bfdc31ceb2f81_0.png)

![](img/1640fde899975b31be8bfdc31ceb2f81_1.png)

all right，this is cs50 and this is not a typical，week of cs50 indeed we're midweek here。

uh in the fall of 2020 here on campus，which would normally be。

first year family weekend an opportunity，for the parents and family members of。

the undergraduates here at harvard to，classes，attend talks and get to know their，course。

this uh this particular year all of us，are staying afar，digitally except those of us who are，already。

and so what we thought we would do this，year is hold a virtual talk of sorts a，virtual discussion。

focused on one topic that doesn't，computer science，does not require that you be in or have。

taken cs50 itself，because it's about a topic that's at，least in part familiar to all of us。

technically，it's certainly familiar to all of us as，security，or cyber security and what we propose。

today is that we have a discussion，about how you might go about keeping。

your own computer be it a laptop or，desktop or your own phone which is also，a form of computer。

secure and i dare say that this topic，even though we'll get into some of the，secure。

is familiar in the sense that all of us，think about or encounter。

good security and bad security in the，real world every day，think about the home that you live in be。



![](img/1640fde899975b31be8bfdc31ceb2f81_3.png)

it a house or an apartment or a，dormitory or somewhere else，typically you'll have things like locks。

on the doors and you might even，depending on where you live，have bars on the windows and the like。

but typically，there are manifestations of security at，different levels and i mean that。

there might be，bars on the first floor windows but not，on the second floor or the third floor。

and that is to say that someone could。

![](img/1640fde899975b31be8bfdc31ceb2f81_5.png)

technically make their way，into your home by way of the second。

floor or the third floor but it's going，to be more difficult of course because。

they need a ladder they need some other，form of physical access to a height like。

that at which point they're probably，going to attract more attention。

and so the probability that an adversary，is going to break into your home given。

that they have to actually rise to that。

![](img/1640fde899975b31be8bfdc31ceb2f81_7.png)

level and get above the first floor，is probably relatively low it's not zero。

there's nothing stopping someone，technically from pulling up a ladder and。

going into that open window or the like，that has no bars，but it's less likely and that's actually。

a good way to think about security，in the digital world as well that，there's really no such thing as。

secure like your phone is not secure。

![](img/1640fde899975b31be8bfdc31ceb2f81_9.png)

fundamentally your，fundamentally，it's secure to some extent it might be，secure against certain。

attacks or certain types of adversaries，resources。

![](img/1640fde899975b31be8bfdc31ceb2f81_11.png)

and those resources might be time might，be money might be technical savvy。

but it really is going to be a trade-off，and so while a bit unfortunate。

one way of thinking about security is，that you don't want to be a secure。

in an absolute sense in the real world，you want to be more secure。

than your neighbor's house for instance，you want to somehow raise the bar either，physically or。

metaphorically to the adversary so that，too much time。



![](img/1640fde899975b31be8bfdc31ceb2f81_13.png)

too much money too much effort to break，into your home，that they might as well just go next，true。

in the world of computers but we're，going to measure the security。

of systems more computationally not so，much physically。



![](img/1640fde899975b31be8bfdc31ceb2f81_15.png)

so with that said let me invite you to，open up this url，here on your screen if you're using a。

laptop or desktop go ahead and just open，it up in a separate tab in another。

browser if you're on your phone you can，go back and forth between two windows，system。

but go ahead when you have a moment and，open up this url and we'll use this url。



![](img/1640fde899975b31be8bfdc31ceb2f81_17.png)

to ask a few interactive questions that，you can respond to，digitally and will also take questions。

and comments throughout，today as well so with that said what，does it mean to be secure then let's。

take a couple of thoughts on this，what do you think of the word secure as。

meaning in the context of your，phone of your computer of your home，interpret as you will。

what does it mean to be secure would you。

![](img/1640fde899975b31be8bfdc31ceb2f81_19.png)

say，any digital hands in zoom，feel free to if you're feeling shy feel。

free to chime in via the chat and brian，can proxy，but otherwise do feel free to raise your。

hand virtually，definition，yeah how about over to pranav if i'm，pronouncing it right，mean。

to protect all the data，that's stored on a particular system if，we're talking about technology。

and at least make it hard，and buy yourself enough time，that a certain person。

may not hack into your system at the，current moment，be able to。

protect your system for uh your entire，lifetime but，i would say at least buy yourself uh。

you know continue continuously buy，yourself time，okay i like that so security is all。

about keeping someone out，of your resources but as i myself have，claimed thus far that's。

hard to argue in the absolute really you，want to。

![](img/1640fde899975b31be8bfdc31ceb2f81_21.png)

your system to just take too much time，to compromise for your phone or your。

laptop to take too much time to，compromise at which point，you're sort of probabilistically。



![](img/1640fde899975b31be8bfdc31ceb2f81_23.png)

statistically，safe against adversaries because again，they're not going to want to waste that。



![](img/1640fde899975b31be8bfdc31ceb2f81_25.png)

much time or effort or money，hacking into your particular system，versus someone else now there are。

different ways that you and i，in the real world try to keep our，laptops and our phones secure。

and one of those most popular web，mechanisms is of course passwords，passwords being。

some kind of phrase some kind of number，device with，so that ideally only you know that。

into the device，by using that password and so by a show，of physical hands。

how many of you have passwords on your。

![](img/1640fde899975b31be8bfdc31ceb2f81_27.png)

laptops or desktops，if you use one of those devices so，almost all of the hands are going up。

those of you who don't have your hand，going up you've probably made i presume。

a conscious choice to not use a password，maybe it's annoying to type in maybe you。

don't really worry about anyone around。

![](img/1640fde899975b31be8bfdc31ceb2f81_29.png)

you getting into the device but，you should concede or recognize that，there is therefore a threat。



![](img/1640fde899975b31be8bfdc31ceb2f81_31.png)

it's much easier for someone to get into，your laptop or desktop。

than into that of anyone else who raised，of you who，have a phone a mobile device those of。

you with that device，how many of you have a password or。



![](img/1640fde899975b31be8bfdc31ceb2f81_33.png)

passcode on that device，on your phone so somewhat fewer hands，i'm seeing so it's good that so many。

hands are going up but there too，it seems that some of you don't have and。

hopefully you've thought about the，implications of that，which means that your parents your。

siblings a stranger，if they just physically pick up your，phone whether it's in your home or in a。

cafe or an airport has immediate access。

![](img/1640fde899975b31be8bfdc31ceb2f81_35.png)

to all of your data so arguably much，less secure certainly than someone。

that requires a password but let's，consider，how we can measure the security of your，computer。

just by using this simple familiar，mechanism like a password so。

it turns out that you and i frankly as，humans aren't very good at picking these。

passwords in the first place as of 2019，just some months ago at year's end this，to be，world。

literally one two three four five six，that was the most common password，year。

uh among those uh passwords that were，known number two on the list was。

slightly better one two three four five，six seven eight nine after that was。

qwerty if that one looks a little weird，you look at the top，left row of your keys q-w-e-r-t-y is。

what they would spell on a u。s keyboard，people are really not trying very hard。

to come up with their password，even though it's not technically an。

english word per se password was the，number four most popular password，p-a-s-s-w-o-r-d。

which is a little too tongue-in-cheek to，be at all secure，after that was slightly worse one two。

three four five six seven，after that one two three four five six，seven eight after that。

one two three four five you can perhaps，adorably，i love you but if you think you're being，password。

well there's a lot of other humans in，too，one one one one one one was also popular。

and then lastly one two three one two，three so now why these passwords you can。

perhaps infer from this list why some of，are，odds are these people were using these，passwords on。

phones or on websites or on other，systems that probably had like a minimum，password length。

these people probably needed a password，that was six，characters long these people probably。

needed one that was nine characters long，and so forth so you can perhaps see some。

manifestations of policies that，companies and universities and and。

uh software manufacturers might have in，place but suffice it to say if your，password is on this list。

your first takeaway from today's，discussion should be，change that password at least if you。

care about the account and i would argue，tune will come back to this。

it really probably should figure into，your decision making what type of。

account it is if it's for some，silly website or game that you're never，deal。

if it's your bank account your student，record something medical related。

probably you really don't want your，password on this list so there。

too consider the context in which we，make all of today's decisions。

now why are these passwords bad and why，risk，so a term of art in computer science is。

that of brute force attacks，and this kind of is what it says this。



![](img/1640fde899975b31be8bfdc31ceb2f81_37.png)

refers to an adversary，someone who's out to get you or get，someone has，uh a device or writes。

uh software that tries to just guess，that，if they don't know your password they're。

not just gonna try random numbers，necessarily they're gonna try one one，one one one one。

and then they're gonna try one one one，one one，one one either manually by typing it。

into the phone that they might have，stolen off of you，or maybe by writing software and then。

connecting that software，via usb，cable or lightning connector or the like。

a brute force attack pretty much just，means that the adversary。

doesn't necessarily know anything about，you your name your birthday your。

children's names nothing like that but，they do have a lot of time。

or a lot of skill and so they're just，going to try all possible passwords。

and what's eye-opening i think about，this type of attack，is that it already gives us an。

opportunity to start thinking about how。

![](img/1640fde899975b31be8bfdc31ceb2f81_39.png)

can we protect ourselves against an，attack and just right now，how secure are your accounts on your。

phones and computers，against brute force attacks well let's，consider how an adversary might do this。

here，but let me go ahead and play this，animation really which shows a。

small robot of sorts that is typing，using this little robotic arm onto an，android phone down there。

there's a zoomed in version of it and，by a robot，a physical device that an adversary has。

designed to just type in all possible，itself is short，you could imagine the adversary going。

about their day going to sleep and this，thing just keeps brute forcing its way，through your password。

so eventually it might get lucky and，stumble upon whatever code，you were indeed using but of course。

there's probably other，threats too there's other threats in，fact anyone who's taken cs50 or cs50x or。

even just the first few weeks of it，both of which are，common programming languages anyone who。

certainly write，software that simulates what that robot，was physically doing and the thing about。

software is as soon as you don't have，any moving parts you can do things。

much much faster because it's all，electronic it's not at all mechanical，and so in this case。

what if i were to steal your phone off，of you for instance，then plug。

my mac or pc into your phone with again，a usb cable or a lightning connector。

such that i could write code that tries，all possible passcodes again and again。

for instance suppose that your phone is，using and this is not an。

uncommon default on on iphones or on，android phones at least in the past。

four digits suppose that you're required，password，synonymous here that are four digits。

long and we're talking decimal digits so，zero through nine so zero one two three。

four five six seven eight nine，you need to choose four of those digits，in some pattern，there。

that are four digits long if your，passcode is four digits long，you can begin to think about the。

security of your passcode，in terms of well how long would it take。

an adversary to brute force their way，to my actual password starting at 0 0 0。

going all the way up to for instance，9999 well let me go ahead and open up，from before。

you'll see in just a moment a poll，that'll ask you this very same question。

that being how many four-digit passcodes，are possible in just a moment you'll see。

this on your screen let me go ahead and，full screen it on my end as well。

go again to the url that's atop my，screen here if you，missed the url earlier or happened to。

close the tab，how many four digit passcodes are，possible，how many four digit passcodes are。

possible among the answers here are 4，or 40 or 9999 or maybe 10 000，and buzz。

in with one of those responses if you，could，all right looks like we've got a few。

hundred responses thus far we'll give，you a few more seconds to buzz in。

a few more seconds to buzz in，and let me go ahead and begin to reveal。

the results here so it looks like。

![](img/1640fde899975b31be8bfdc31ceb2f81_41.png)

uh quite a few of you 60 plus percent，think it's 10 000 possibilities 27。

of you think it's 999 possibilities and，then a few others think it's 40 or 4。

and a bunch of you are unsure so let's，consider then how we would answer this，for answering this。

on our own let me go ahead and propose，that to answer this question we just do。

some very simple arithmetic it doesn't，need to get very complicated。

but the math could be thought of in the，following way，if we've got a four digit passcode。

that's four digits，each of which can be zero through nine，and there's ten total digits there for。

zero through nine zero one two three，four five six seven eight。

nine so ten possible values for each of，those four digits，so if that's the case i think it's fair。

the first digit，times 10 possibilities for the second，times 10。

times 10 and of course if you multiply，this all out the answer was indeed。

10 000 possibilities so if you have an，iphone or an android phone right now and。

you've got a four digit passcode，that you think no one knows that may，very well be the case。

but you should worry about or consider，well what happens if a friend with a，fancy robot。

connects your phone to that and just，zero，to zero to nine nine nine nine or。

smarter still connects your phone via a，cable to their laptop。



![](img/1640fde899975b31be8bfdc31ceb2f81_43.png)

writes software to generate all of those，possibilities，well a little worrisomely it's not all。

that hard to do the latter and to，actually write code so in fact let me go。

ahead here and on my own mac，let me go ahead and open up a program，in a file。

called crack dot pi so crack is a term，of art and programming which means to，brute force your way。

what it is，algorithmically those of you，particularly parents and family members。

who have never seen any of this before，totally fine that's new to you。

your sons and daughters and others here，have in the room，have seen a little bit of this code but。

we'll keep it short which is to say that，effort，to write code that brute force is an。

attack on your own phone，and the code i'm going to write here is。

in a language called python which is，quite popular these days。

and i'm going to say a command like this，from string import，digits which is just a clever way in。

python this programming language just，give me access to all the possible，digits in decimal。

zero through nine and then i'm going to，import so to speak，from a library some software that some。

other smart people wrote，something called product so it turns out，of。

functions or functionality much like in。

![](img/1640fde899975b31be8bfdc31ceb2f81_45.png)

like addition，subtraction multiplication and division，of those，the。

functions i'm importing here is this，notion of a product which really just，means a permutation。

of all possible uh digits and now i'm，going to use what's called a loop。

in programming a loop in a program is，and again，and i'm going to go ahead and say this。

for passcode in，the product of all of those digits and，repeat the digits four times total。

go ahead and print out each passcode let。

![](img/1640fde899975b31be8bfdc31ceb2f81_47.png)

me go ahead and print it out using，somewhat cryptic syntax，but that's only because i'm going to。

print out a list as an actual string，parents and family members don't worry。

for now what that means um cs50 and。

![](img/1640fde899975b31be8bfdc31ceb2f81_49.png)

cs50x students，this is just a clever way with a couple，of lines of code to iterate。

over all of the digits 0 through 9，combine them，four at a time and print out all。

possible permutations，of those four digits so if i didn't，screw up here i'm gonna go ahead and。

save my file，and run a command called python on，crack。pi。



![](img/1640fde899975b31be8bfdc31ceb2f81_51.png)

and hit enter boom that was so fast in，fact let me do it again let me clear my。

screen and rerun this crack。pi。

![](img/1640fde899975b31be8bfdc31ceb2f81_53.png)

program boom that's how fast a computer，my little mac here，zero。

zero and nine nine nine nine and it's so，fast because it did them all in the，blink of an eye。

so if you're thinking that your four，secure，it probably really isn't because it。

wouldn't take that much effort for maybe，someone in your household to write code。

like this connect your phone secretly at，night when you're not paying attention。

and figure out potentially，what your code actually is so what would，be better than。

than using just digits what would be，better well why don't we use letters of。

the alphabet english alphabet for，today's purposes，and in the english alphabet we have more。

letters than we have，numbers so how might we think about this，let's go ahead and ask a question here。

if you change your phone after today to，use four letters of the english alphabet。

instead of using numbers alone，how many possibilities are there then。

well let me go ahead and open up a，different poll question here，which asks this time how many。

four-letter passcodes are possible and，in just a moment you'll see in that same，window as before。

this question being asked how many four，letter passcodes，are possible and we'll see what folks。

think in answer to this as the answers，to be fair i have not qualified one。

thing so you might have to be making。

![](img/1640fde899975b31be8bfdc31ceb2f81_55.png)

letters，of the english alphabet however there's，uppercase and lowercase。

so if you allow the user to type in，something case sensitively so to speak。

where case matters it's not 26，possibilities for each of those four，so it looks like。

an overwhelming number of you 78 percent，think there's some seven。

million possibilities when using four，letter passcodes，about 11 of you think that 52 000。

are all of the passcodes so let's go，ahead and do the quick math。

again it doesn't need to be particularly，sophisticated the math let me go ahead。

and open up this time，a similar approach to this problem，whereby if we have four letters of the。

alphabet and let's assume case，sensitivity which to be fair you might，not have assumed。

well then i think we have 52。

![](img/1640fde899975b31be8bfdc31ceb2f81_57.png)

possibilities times 52，times 52 times 52 for each of，the four letters in your passcode and if。

you multiply that out boom，you indeed get seven million plus，possibilities。

so consider the takeaway here if you are，currently using a passcode that's four。

digits purely numeric you have only ten，thousand digits between you and some，potentially。

if you change your four-digit passcode，to be a four-letter passcode。

then you've got seven million possible，passcodes between you and the adversary。

now why is this better，well again whether they're using a robot，or using code。



![](img/1640fde899975b31be8bfdc31ceb2f81_59.png)

it's just going to take them more time，to hack into your device。

and again at that point if it's going to，take them that much time that much。

effort maybe even that much money，other people，might indeed be more secure because it's。

probably going to be easier for that，phone，and try to get into that one instead。

well let's consider what this does，in actual code let me go back to my。

mac here and let me go ahead and open up，that same file as before。

and let me go ahead and change something，as follows instead of using。

digits let me use what i'm going to call，ascii letters，families who are not familiar with cs。

ascii just refers to essentially，all of the printable letters of the。

alphabet that you would typically see，in english so a through z capital and，lowercase here。

and i'm going to go ahead and change my，mention of digits here to be ascii。

letters as well so again the program is，almost identical，but it's going to use all 52 uppercase。

and lowercase english letters，this file。

![](img/1640fde899975b31be8bfdc31ceb2f81_61.png)

let me rerun python of crack。hi and this，time i actually have a moment to walk，over to the screen。

and point out now that we're just now，through the lowercase z's。

now we're going through all the possible，letters，it's still pretty fast this is maybe。

what 10 seconds later done，we went from aaa a to z zzz，so we've raised the bar and again the。

security of our，because now it's going to take the，adversary more time or more effort。

to actually hack into our device well，let's consider perhaps another question。

then what if we generalize it further，to be characters and those of you among。

families perhaps might not know the，distinction between characters and，floor here。

when you register for a website these，days it's somewhat annoying。

because those websites typically force，you to choose a good，password and what do they typically mean。

by good password，what does your password these days often，have to contain before the website even。

lets you proceed。

![](img/1640fde899975b31be8bfdc31ceb2f81_63.png)

yeah feel free to raise your your，virtual hands，and let's see brian who do we have how。



![](img/1640fde899975b31be8bfdc31ceb2f81_65.png)

about uh dax，what are your thoughts eight characters，at the very least。

number and capital so at least a number，and character so combine the two。

i like that so instead of 26 or 52 or 10，we instead have maybe 62 if we combine，letters and numbers。

other thoughts on what websites，typically，okay so special characters or，hash symbol。

maybe it's an exclamation point a，else，yeah so these symbols and frankly i get。

as annoyed as you probably do when these，websites sort of annoy you and say no。

that you can't use that password no you，can't use that password you need to，guess。

but indeed if we add punctuation to the，mix i think we can do，even better in fact a character。

therefore is any type of character，maybe it's punctuation maybe it's a。

letter maybe it's a digit unlike just，characters，it turns out that typically at least in。

ascii the system that cs50 students will，know computers typically use。

there's 94 possibilities for each symbol，because you've got，10 letter 10 digits 0 through 9 you've。

got 26 lowercase letters，26 uppercase letters and then if you，count them up on an english keyboard。

32 characters more that represent，punctuation like hashes and exclamation。

points and commas and periods，so if you have 94 possibilities for each，of those symbols it turns out。

that you then have a total of 78 million，good now，we're really raising the bar to the。

adversary because now they have to waste，even more time，trying to hack into your passcode and in。

fact let me go ahead and simulate that，with some actual code let me go ahead。

and open up my same program as before，and this time let me go ahead and import。

not just ascii letters，but also digits and also literally，punctuation。

the code i'm writing in this language，called python literally gives me access。

to all printable punctuation，by just importing it with this first。

line of code and i just need to change，one line of code down here。

i need to actually say ascii letters，plus，python，lists，those cs50 students among you will know。

that you can join two lists perhaps in，this way using what looks like，them all together。

but i'm still going to do of length four。

![](img/1640fde899975b31be8bfdc31ceb2f81_67.png)

here now let me go ahead and save this，program and rerun it as python of，crack。pi。

and now i can frankly take my time，walking over to the screen，because now what you're seeing on the。

screen is four possible symbols，but it's including 32 possible，list。

is much longer right at this point in，the story we were already through。

all of the lowercase letters up through，z a moment ago，now we're only at the m's n's。

o's p's which is to say，that if my mac weren't just printing，this on the screen but were instead。

connected to your phone that i stole，and somehow sending all of these。

possible passcodes into your phone，it would be taking this much time to。

actually solve now to be fair we're，almost at the lowercase z's。

so you know if we kind of stall for like，a minute or two longer，million。

possibilities is not all that impressive，and so i dare say that。

we should do even better than this so，what might be better than four，characters for a password。

any thoughts or volunteers what would be，a better password than，four characters where again each。

character is a letter，a number or a punctuation symbol，the list is pretty good but i think we，done。

in under a minute yeah thoughts leo，i'm still muted i think we need to，unmute leo。

hello yes okay success right um uh，have a longer password to use like at，least eight characters。

perfect so have a longer password use at，least eight and notice here。

we're even now going through the numbers，but we're almost done it seems with the，punctuation。

but again if i give this a little more，time and i think i was a little over。

zealous under a minute probably isn't，class，that will have been done but what if we，characters。

well eight characters is gonna take even，all，how much longer this might take let me。

go ahead and open up a somewhat，different question but similar in spirit。

in just a moment that will appear on，your screen and the question，here is going to be how many eight。

character passcodes are possible，give me just a moment to open up that。

screen you should see it momentarily，and indeed on your screens now you，should see this question。

how many eight character passcodes are，possible and this time i'm kind of。

waving my hand at it i didn't even，bother doing the math，precisely yet but i'm proposing that。

it's roughly a million。

![](img/1640fde899975b31be8bfdc31ceb2f81_69.png)

a billion a trillion a quadrillion a，quintillion，some of you are perhaps noticing a。

pattern here and you went straight for，quintillion that bar，right。

good instincts perhaps looks like we're，getting equilibrium about 60 percent of。

you think it's one quintillion，25 percent of you think it's a，quadrillion and then fewer and fewer。

for the others well let's take a look at，what the actual answer is。

give me just a moment to actually do out，the math here on my screen。

and if we do out the math on my screen，here we'll see of course that we need to，do some more math。

times，instead of just four to leo's suggestion，of using eight possible symbols。



![](img/1640fde899975b31be8bfdc31ceb2f81_71.png)

and if you do this out i had to think，about this this in fact。

is let's see we've got millions billions，trillions quadrillion so gotcha so it。

wasn't the biggest option on the list，the answer is indeed quadrillion so six。

quadrillion if you will，but but but those of you who are fans of。

having quintillion possibilities which，is pretty pretty，secure because it's just going to take。

the adversary way longer to hack into，your password，well all it takes to go from six，quadrillion。

to some number of quintillion is just，had proposed，not an eight character passcode but a 10。

character passcode，we actually would have hit quintillions，secure，the longer and longer and more。

complicated these passcodes get，all right so by logic then you should，eight not ten。

maybe they're 20 characters long maybe，they're a hundred characters long。

but here we see another theme in，security that of trade-offs，like the end-all is probably not to be。

as secure as，conditional，on some other goals you might have so，let me ask this。

what's the trade-off here in making your，password longer and longer，do you。

pay as the human what's the downside in，computer science as in life there's，always a catch。

there's always a cost so what's the cost，when you make your passcode more and。

let's see who do we have brian over to，uh ginny，yeah i feel that it is very difficult。

for a human being to remember such a，long password and due to that we even。

store those long passwords somewhere in，the system itself，so that we can use that whenever we have。

to log into the system，yeah there's this trade-off of just，remembering the darn things and you make。

a perfect point，if uh if i can get on my soapbox again，if you are the among those people who。

have pretty good passwords and by good，passwords i mean some numbers some，letters some punctuation。

but it's written on a post-it note on，your monitor at work，or maybe it's slightly more cleverly。

written in a microsoft word。

![](img/1640fde899975b31be8bfdc31ceb2f81_73.png)

file in your hard drive or maybe it's in，a google doc or maybe it's even on a。

piece of paper in your drawer，you're just exposing yourself to other，threats of course but here too。

is sort of a sociological consideration，or just a policy consideration whether，university。

or just a household with multiple family，members what should your own policies be。

because arguably it's not jenny's fault，it's not our fault，if we are resorting to writing things。

down on paper if our passwords，are so darn hard to remember and，moreover i haven't even made the。

suggestion yet，but if you are one of those people in，life who is using the same password，websites。

are，also doing something bad why because if，any one of those apps or websites is。

compromised and your password gets out，whether it's i love you，quote unquote or something much more。

complicated all an adversary has to do，now is try that same password。

on your other accounts and so you're，just exposing yourself to more risk by。

reusing passwords but to jenny's point，here my god where does it end now i need，a really long。



![](img/1640fde899975b31be8bfdc31ceb2f81_75.png)

random password on this website this one，and this one and this app。

all over the place i mean honestly i as，a human certainly can't。

remember all of those passwords and even，if i could i feel like there's better。

things in life to be remembering，than passwords for accounts like this so。

there's surely a trade-off here，but again the goal is to keep the。

adversary out with some probability，not necessarily out in the absolute so。

what else can we do to prevent the，adversary from hacking into our system，so that i can have in。

somewhat easier more memorable passcode，but at least keep them out well here's a。

screenshot of something you might have，done by accident，uh perhaps late at night when a little。

groggy or a little blurry eye，trying to type in your password，incorrectly too many。

times in fact by a show of physical，yourself，out of your phone before by typing in。

the wrong password too many times i did，it like literally just the other day。

and so on iphone for instance it looks a，zoom in，minute so，you don't have to get rid of the phone。

and start over but the iphone is telling。

![](img/1640fde899975b31be8bfdc31ceb2f81_77.png)

you to come back in a minute and if we，look at for instance android。

something similar your android wallpaper，will differ certainly。

but down here here for instance it says，too many attempts，try again later i mean that's a little。

infuriating because if i pick up my，phone now i want to get in now。

when the heck is later so putting that，aside，what's the takeaway here why are apple。



![](img/1640fde899975b31be8bfdc31ceb2f81_79.png)

and why are google doing，this because i bet all of you if you've。

ever locked yourself out of your phone，are super annoyed at that moment in time，google。

but what's the upside of what they've，just done when they lock you。

out of your phone for having guessed，your password incorrectly。

why is this arguably a feature and not a。

![](img/1640fde899975b31be8bfdc31ceb2f81_81.png)

sam，uh yeah it's used to uh decrease the，chances of like a successful brute force，to suck。

and how does it decrease the chance of，that would you say uh，because it makes the attacker um。

i have to commit more tries before they，can successfully get into the phone so。

it decreases the chances，exactly so this is a very common，principle in security。

and it was pointed out earlier too just，slow the adversary down like we don't。

have to rethink the problem of security，we don't have to redesign passwords。

necessarily but we should make it harder，for the adversary to log in。

ideally without making it harder for you，consider，the simplest passcode that had four，digits a four。

digit passcode there were ten thousand，possibilities a computer a robot could。

guess all of those pretty quickly，but what if after typing in the wrong。

passcode three times or maybe ten times，some small number of times what if the。

iphone or android phone，locks you out for a minute just like，iphone did a moment ago。

well that might mean even though there's，only ten thousand possibilities。

maybe it will take the adversary ten，thousand minutes to crack。

in track your password because they keep，getting slowed down every time they type。

in an incorrect one and maybe it's not，quite ten thousand it's some，down in that way。

maybe you have a 10 character passcode，with 78 quadrillion possibilities。

and imagine the uh the phone just slows，you down one second maybe you can only。

type in one passcode per second，quadrillion。

![](img/1640fde899975b31be8bfdc31ceb2f81_83.png)

kind of，slow down might very well be enough to，keep the adversary。

out and so if you don't have features，like this enabled，on really any device you should look for。

them nowadays thankfully they tend to，come pre-configured for this。

but there is a downside there is a，downside you shouldn't just turn on，these kinds of defenses。

blindly because what's the downside of，it，enabled those are the same things or。

enabling it if it's not already enabled，what's the downside here to be clear。

because none of our advice today will be，100，uh well uh if you forget your password。

that means it's going to take longer for，you to access your phone again。

yeah it's going to take you the user the，in and i'll，admit too i have on multiple occasions。

not locked myself out once i then got，stubborn and i think my anger level just。

rose so i started typing in more angrily，and therefore making more mistakes。

and what apple and google do is they，have what you might describe as，way of saying。

the first time you get penalized you，know one minute now you have to wait one。

minute if you screw up again，then you have to wait two minutes if you。

screw up again maybe it's five minutes，maybe it's 10 minutes maybe it's an hour。

and i swear at that point i wanted to，throw my phone across the room because i。

couldn't get into my own device，and there you start to sacrifice of，course usability。

right if my device is so secure that，even i can't get into it，then is it really worth having it all。

and so finding that inflection point，systems，because you have to find that inflection。

point so that your users are using good，passwords and passcodes。

but they're not just taping them onto，the monitor on a post-it note，or disabling them all together。

all right let me pause here to see are，there any questions about，passwords passcodes brute forcing。

or these kinds of defenses given that，defense，against adversaries accessing hardware。

and software that we don't want them to。

![](img/1640fde899975b31be8bfdc31ceb2f81_85.png)

now so there is a definite number which，we can calculate that for four digit，numbers this is the。

most possible number of outcomes but uh，what from our matrix。



![](img/1640fde899975b31be8bfdc31ceb2f81_87.png)

fingerprints space scanning yeah really，good question so what about biometrics。

using face scanning like，apple has face id these days which also。



![](img/1640fde899975b31be8bfdc31ceb2f81_89.png)

annoys me sometimes if it doesn't quite，get my face right or these days if we're。

wearing masks it's infuriating to use，that kind of feature but。

maybe probabilistically there are fewer。

![](img/1640fde899975b31be8bfdc31ceb2f81_91.png)

people with exactly your facial features，more secure，than picking some passcode sometimes you。

use fingerprints or retinal scans or，like the distance between your fingers。

all of these different measures that，statistically tend to ident not so much，uniquely identify us。



![](img/1640fde899975b31be8bfdc31ceb2f81_93.png)

but uniquely identify us all enough and，there's threats there too a former，twin brother。

who because of apple's face id was now，able to get into his phone by just。

picking it up off of the table，because as twins they both looked all。

too similar so there's downsides and。

![](img/1640fde899975b31be8bfdc31ceb2f81_95.png)

upsides there too，but biometrics can also help things so，always。

and not something for instance that you，just only have to remember。

and in fact that's a perfect segue to，what uh computer scientists call。

two-factor authentication in the，security world security people would，call。

the passwords we're using one factor and，factor。

![](img/1640fde899975b31be8bfdc31ceb2f81_97.png)

and indeed two-factor authentication，adversaries，that doesn't rely just on something you。

know like a password，it also relies on something typically。



![](img/1640fde899975b31be8bfdc31ceb2f81_99.png)

that you have，or the like，password and，downloads it somewhere from a database。

where you've used it before，they don't necessarily have access to。



![](img/1640fde899975b31be8bfdc31ceb2f81_101.png)

and the like，unless they have physical access to you，threats，but there's other forms of two-factor。

authentication for instance if，if this sounds familiar now and maybe。

you don't even call it two-factor，two-step，authentication uh by a show of physical。

hands who has one or more accounts that，uses two factors，instead of just one yeah so here too。

it's good to see so many hands going up，but if you do not use two-factor。

authentication for things like，your email account or your bank accounts。

or your brokerage accounts or your，health medical accounts you really。

should start considering doing so and，what form does this typically take well。

let me show a screenshot here for，gmail account，that you use for work or for personal。



![](img/1640fde899975b31be8bfdc31ceb2f81_103.png)

use you can enable what google calls，two-factor，authentication and what you'll be。

prompted for when logging into your，gmail account if you，uh if you enable this is not only your。

username and your password，but also a six digit code and six digits，doesn't sound terribly long。

but in this case the way these，are sent，via text，message or via special app that you，device。

have that，device and therefore only you know that，code and better yet。

these codes expire so even if some，adversary intercepts it or sees you。

typing it in over your shoulder，you can only use these codes once which，alone，use。

and so consider now again and i can't，emphasize this enough if you。

are of the age where you have your own，bank accounts again brokerage accounts。

anything medically related anything that，you find especially important or。

personal like your own email，password，you now as of today already have the。

mathematical tools and the mental model，i dare say to figure out just how easily，someone could。

your information。

![](img/1640fde899975b31be8bfdc31ceb2f81_105.png)

and take your money or read your emails，or the like so you can improve that，better。

longer more random password that you，remember or memorize in some way。

or additionally by enabling the second，factor so that you，narrow the number of threats that are。

dangerous to you as a result so，with that said too with two-factor。

authentication there's another thing you，can bring into play when it comes to。

managing all your passwords i alluded to，using microsoft word before or。

post-it note there are software，solutions to this too，so another defense we would like to。

offer up for your consideration today，is what's generally called a password。

manager this is a piece of software。

![](img/1640fde899975b31be8bfdc31ceb2f81_107.png)

either for free or that you pay for for，your phone your laptop or desktop。

that literally manages your passwords in，its simplest form，think of it like a spreadsheet but。

that's secure，quote-unquote on your own computer that，is these password managers and here's。

two popular ones onepassword。com is one，popular tool，lastpass。com is another one and there's。

others if you google around but i would，as always read up on reviews or get。

second opinions don't just take at face，value what we propose，that you type，then you。

save them all behind one master password，one password that's really long。

hopefully really random with lots of，numbers and letters and symbols。



![](img/1640fde899975b31be8bfdc31ceb2f81_109.png)

main，password and by entering that password，into your mac or pc or phone。

you then unlock all of your other，paste，your actual accounts usernames and。

passwords or these programs also give，keyboard，command and voila you're automatically。

logged into websites you don't have to。

![](img/1640fde899975b31be8bfdc31ceb2f81_111.png)

copy paste or manually transcribe them，so to this day what does this mean for。

me i use one of these password managers，and most of my colleagues do as well。

many of us most of us don't even know，the passwords we use for various，websites or。

apps or the like why because we now，trust that the password manager can with，a click of a button。

generate a really long random password，with lots of numbers digits and，punctuation。

and then it will remember it for me and，i just have to remember that one。

main password that's protecting all of，those others，so that's kind of good in that now i can。

practice what i've been preaching，but i'm there is a downside，i'm exposing myself to a new risk or。

vulnerability that is to say what's the，trade-off here，why should you not necessarily just run。

off after today's class，download and install a password manager。

and start using it without a little bit，of thought first，what's the downside of this probably。

sounds pretty good，yeah over to uh。

![](img/1640fde899975b31be8bfdc31ceb2f81_113.png)

uh like lex lean if i'm saying it right，um yeah if someone cracks like your。

password manager password，then they have like access to all your，passwords yeah。

so you really depends on what the threat，here is or what you're most worried。

about if someone compromises guesses，figure out your main password。

that protects all the others now you've，just handed them all of your accounts at。

once and that's a massive trade-off，however if you again consider the。

alternative coming up with big random，passwords and then memorizing them all。

or somewhat foolishly writing them down，monitor，the question shouldn't be is this uh the。

uh isn't is this the right way to do，things but really relatively speaking。

is this a better way to do things you're，risk，which of those risks do you worry about，that concern。

but maybe you could write down your main，password for your password manager。

and maybe put it in a physical vault or，a fire a fire locker or the like。

that with very low probability someone，else would get access to unless they。

physically attack that device or hide it，like，so that yes it's vulnerable but the odds。

that someone finds it might just be，relatively low but again this is the，theme figuring out。

what the right balance is for your，accounts and the type of security。

that you want to aspire to achieve well，let's consider a few other defenses and。

we'll leave time at the very end for，techniques，what's another building block that we。

can bring to bear when it comes to，protecting ourselves online，so encryption cs50 students will know。

that encryption refers again to the，scrambling of information looking making。

data look like it's random data，but by encrypting it with what's called，the key typically a key that。

only you and the recipient somehow know，encryption tends to be the solution。

to a lot of our problems and indeed，these password managers，typically additionally encrypt your data。

so that even someone who steals your mac，and pc can't just open up the program。

and see it all of the data 2 is，similarly encrypted，many of you have already been trained or。

conditioned by society to at least，look for or hope for or recognize https。

colon slash slash the s means secure，that just tends to be a good thing。

because it means a website you're。

![](img/1640fde899975b31be8bfdc31ceb2f81_115.png)

visiting is secure it's encrypted，as opposed to just http which was much。

more common just a few years ago，and is completely unencrypted so that is。

to say if you visit a website that says，just http in the url，anyone between you and that website。

theoretically can be listening in，so to speak on your your traffic the。

zeros and ones going back and forth，visiting，if you're in some foreign country。

visiting sensitive materials the，government could know what websites。

you're visiting and what content，that much，harder it's not a hundred percent there。

are attacks still that are possible but，again it just raises the bar。

but there's a another technique that's，increasingly being discussed in the。

media and with which you should be，familiar known as end-to-end。



![](img/1640fde899975b31be8bfdc31ceb2f81_117.png)

encryption end-to-end encryption means，that when you're using a third-party。

service typically whether it's a chat，the like，you're not just encrypting your traffic。

the zeros and ones，you and，amazon or some other third party you are，encrypting your data between you。

and the person you're talking to so，what's app for instance the popular，messaging tool。

early on had this feature and many other，chat programs nowadays have it as well，including imessage。

uh and signal and telegram and the like。

![](img/1640fde899975b31be8bfdc31ceb2f81_119.png)

end-to-end encryption means that even，though you're using a third-party。

service a company that you may or may，not trust，your communications are communicated，between you。

and the person with whom you're seeing，uh speaking the，company in between their servers even，servers。

cannot decrypt that information they，cannot see the information in its，does。

this at least only recently does this so，zoom for instance the technology that we。

are all using right now，actually took some flack rightly so some，months back when in their marketing。

literature on their website as a recall，encryption，which was false because what end-to-end。



![](img/1640fde899975b31be8bfdc31ceb2f81_121.png)

between you，and the person with whom you're，communicating but the marketing，literature at the time。

between，you and zoom which is not what security，researchers or computer scientists or。

technologists in general，would define end-to-end encryption as，rightly so。

they've begun though in recent weeks，rolling out actual end-to-end。

encryption we are not using it right now。

![](img/1640fde899975b31be8bfdc31ceb2f81_123.png)

it actually makes certain features，trade-off，but generally speaking if you're having。

the most intimate or private or。

![](img/1640fde899975b31be8bfdc31ceb2f81_125.png)

personal or financial or medical of，communications with people。

this is another feature you should start，to look for and listen for，using。

and especially when it comes to，communities，this is the kind of software that's。

increasingly under attack by governments，because they often want，backdoors so that the uh usa's nsa。

or fbi or some other entity can get into，these communications，that's made much more difficult in a。

good way by using end-to-end，encryption so that your communications，are indeed secure。

well in our final moments together let's，let's focus ultimately on zoom the very。

technology we're using because they've，taken some flax certainly。

beyond end-to-end encryption which you，being，lot of users，decided some months ago to stop using。

zoom for this reason even though their，business is still booming。

so is zoom secure let's ask one final，question of the group here，keeping in mind that we've now just。

security，let me go ahead and ask this final，question here which will appear on your。

screen in just a moment，it is quite simply is zoom secure，and we'll offer you answers of yes no。

all right let's see how the responses，are coming in i'm seeing 55 percent。



![](img/1640fde899975b31be8bfdc31ceb2f81_127.png)

no 16 yes 28 percent，let's take，a couple of comments here among those of，you who think zoom。

is secure why do you think it's secure，would anyone be comfortable raising a。

virtual hand so we can call on you，or maybe commenting in the chat as to，any volunteers here。

let's see over to how about uh sam what，uh two days ago zun zoom offered a。

end-to-end encryption to all the，users yeah so it was in fact that timely。

zoom began rolling out on a trial basis，essentially end-to-end encryption with，all users so，key2。

and zoom has implemented that concept，correctly，then yes maybe zoom is secure in the。

sense that your video conversation with，someone else，is in fact private between you and them。

with that said，if you're in a coffee shop or in a，library at least in healthier times and。

someone's looking。

![](img/1640fde899975b31be8bfdc31ceb2f81_129.png)

over or listening in on your，conversation arguably even that，technology is not secure。

you can imagine there being other，threats maybe you have accidentally。

been vulnerable to a virus some kind of，threat on your own computer and even，between you。

and that other person that doesn't mean，there's not malicious software running。

on your own personal mac or pc or the，other person's，recording everything you say and。



![](img/1640fde899975b31be8bfdc31ceb2f81_131.png)

adversary so，there too whenever you ask or answer，questions about security。

take into account those kinds of，qualifications those conditionals，because it's security is never uh。

should never be discussed really in a，vacuum so those of you who said no。

i think we could come up with even more，reasons but at least let me dispel。

just a few because i do think some of，the flak zoom took was overstated。

because those criticizing didn't really，understand some of the issues that were，instance。

all of you today to log into this，meeting，for instance followed a url most likely。

that you had been emailed or that you，saw on your screen and that url。

probably looked a little something like，this https which is good，zoom dot us or something like that。

followed by a number the meeting id，for instance five five five one one one，a different number。

this url，after registering is it secure well even，though all of you here right now have。

presumably registered，technically there is nothing stopping，any of you from。

texting or emailing or dming，this same url to anyone else on the。

internet and they could therefore join，perhaps without registering so maybe，that's a threat though。

zoom typically sends you not a url，that's as simple as this when you，register but a longer one。

indeed and there's another detail that，some urls have too，which might look like this a question。

mark at the end and pwd for password，and then some kind of password and。

indeed the urls you clicked today looked，a little more like that still different。

because they were special registration。

![](img/1640fde899975b31be8bfdc31ceb2f81_133.png)

password，now you need to know both the meeting id，and the password in order to join。

that particular zoom meeting and if，you're not running big classes like we。

are today with this meeting，but rather you're having one-on-one or，smaller scale meetings。

typically you are receiving or，generating a url that looks like this。

or better yet that looks like this so，that it doesn't suffice for an adversary。

to just guess the meeting id，and that's what was happening early on。

zoom typically did not require that，meetings，which meant the only thing between you，to speak。

hacking into your meeting was they just，had to guess the meeting id。

and we've seen already it took me what，like one minute 30 seconds。

to write a python program that just，generated all possible numbers of length，4 or 8 or whatever。

so you know people with too much free，time are writing code，that just tries all possible urls and so。

if you've ever been zoom bombed，maybe that's because someone shared the。

url with someone they shouldn't have，or maybe someone with a bit of。

programming experience or just luck，feature，in the sense that honestly having to。

type in a meeting id and a password，is just annoying it starts to hurt the，usability of the system。

and a lot of people in the corporate，world like they don't they're going to，choose another product。

if another product is easier to start，the video conference with。

so arguably it was a conscious decision，on zoom's part now universities and。

companies have started requiring this or，another feature called a waiting room，today。

but that just again raises the bar to，someone attacking these systems so is，zoom secure。

yes and no like it really should be，considered not in a vacuum，but in the context of what kinds of。

threats are you worried about，and what kinds of defenses are you，willing to put up。

so just like in the real world you might，have your own，uh home or apartment or the like on。

which you might have locks，and bolts and bars on the window you。

know at some point if it takes you five，door。

![](img/1640fde899975b31be8bfdc31ceb2f81_135.png)

just to get into your home it might be，going to enjoy，going home because it takes that long to。

get in and you might put bars on the，window to keep that person physically。

out but it's not going to look。

![](img/1640fde899975b31be8bfdc31ceb2f81_137.png)

particularly nice and there's nothing，there too，there's this sort of trade-off and so。

among the takeaways we hope from today，are one just better thought processes，your phone。

or your computer or your homes for that，matter to be secure and to recognize，trade-off and。

we would encourage you ultimately to ask，these kinds of questions if any company。

if any app if any website just says on。

![](img/1640fde899975b31be8bfdc31ceb2f81_139.png)

their website we are secure，like that's nonsense like that means。

nothing in and of itself until you start，asking questions like，what are you secure against and how。

well thank you so much for joining us，here let's officially wrap here but。

folks are welcome to stick around for，uh some more time if you'd like to ask，to take off。



![](img/1640fde899975b31be8bfdc31ceb2f81_141.png)

questions，brian if you'd like to call on anyone，oh yeah so i had a question uh remember。

how you said that for iphone，10 or，some x number of wrong tries but when。

you write a code is that the same case，because then even affordable passcode is。

really saved because there's only one，person probably，of someone hacking in yeah really good。

question it depends on the device so，if you read months years ago now like，the fbi has been in the u。

s the federal，bureau of investigation has been in this，like apple。

because they want it to be easier for，them to get into，um suspects devices like their phones or。

their ipads or the like，and they typically do this by connecting。

a computer similar in spirit to what i，to hack in，but apple um to their credit has been。

making it more difficult for people to，automate，attacks on these devices and so even，lockouts。

typically do apply even if you're using，a physical cable，that would be a good thing otherwise。

it's not really doing anything except，keeping the non-programmers out。

when the programmers are really the，threat，so those same defenses do tend to apply。

apple has also made it harder for，instance to install，different software on a phone unless you。

have the passcode already，there was an attack vector years ago，whereby you could actually install。

special software onto the iphone that，did not require a passcode that，therefore made it easier。

to get at the data but that has been，fixed i believe since，other questions about security or。

passwords or encryption，or the like maybe no questions on，quantum computing though since。



![](img/1640fde899975b31be8bfdc31ceb2f81_143.png)

we sort of fielded all those looks like，we have a question from steve。



![](img/1640fde899975b31be8bfdc31ceb2f81_145.png)

yes this is this is steve can you hear，me yes steve over to you。

so here's my question what do you think，about the uh，little，usb looking uh devices。

do you think they're a good idea a short，answer yes and this was more common a，corporate world。

companies like rsa and others would，literally have what are typically called，with a battery。

and also a tiny little screen that，displays that，good，in the sense that it is literally。

something that you must physically have，so it's a good second factor。

downsides include it's something you，must physically have and i've had those。

in the past and if i misplace it or，don't keep it on me，i might now be locked out of an account。

just because i don't have the stupid，key fob with me increasingly companies。

have started using software，fobs instead which means you install。

special software onto your iphone or，your android phone，which is a little better in the sense。

that i know i'm pretty uptight such that，my phone，whereas i might not notice my keychain。

or my key fob missing as quickly，so there tends to be downsides with the，about。

usability so not bad but increasingly，too，i would beware using text messages so，sms。

or text messages that you get in green，on like an iphone，those tend to be very uh forgeable and。

distrust uh distrustworthy uh，untrustworthy and so i would beware，using anything that is。

text message based but good question，other questions from the group there's a。

question in the chat about，cookies so are there security issues。

that are related to cookies should we，clear cookies off of our devices。

what should we do about cookies yeah so，for those unfamiliar，tune in this coming monday to cs50s。

lecture on cookies and other such web，programming topics，in the meantime a cookie is just a small。

file or piece of data。

![](img/1640fde899975b31be8bfdc31ceb2f81_147.png)

browser，the first time you visit it typically so。

![](img/1640fde899975b31be8bfdc31ceb2f81_149.png)

if you visit facebook or gmail or really，any website on the internet including。



![](img/1640fde899975b31be8bfdc31ceb2f81_151.png)

cs50 zone you will have a cookie planted，on your computer，that again is just some uh little value。



![](img/1640fde899975b31be8bfdc31ceb2f81_153.png)

that helps the website remember，that you have been there before。



![](img/1640fde899975b31be8bfdc31ceb2f81_155.png)

a lot of the，a lot of，tracking which means that if you have，cookies on your computer。

they are designed to be sent back to，you have。

![](img/1640fde899975b31be8bfdc31ceb2f81_157.png)

websites like the facebooks and googles，them。

![](img/1640fde899975b31be8bfdc31ceb2f81_159.png)

those advertisements also often come，websites，which means those different companies，computer。

and these advertising companies are。

![](img/1640fde899975b31be8bfdc31ceb2f81_161.png)

different customers，facebook and google and thousands of，other companies and unfortunately that。

means as the middleman so to speak，they these advertising networks which。

unfortunately are often owned by google，and facebook。



![](img/1640fde899975b31be8bfdc31ceb2f81_163.png)

visiting，because these cookies are kind of like，virtual hand stamps as i describe them。

whereby much like you might get your，hand stamped at an amusement park or a。



![](img/1640fde899975b31be8bfdc31ceb2f81_165.png)

bar or a club or the like to just attest，that you've been there before。

your computer is designed to show these。

![](img/1640fde899975b31be8bfdc31ceb2f81_167.png)

back，so pretty much all of us are spending a，telling，many websites who we are effectively or。

that we're the same person，thereby leaking information about where。

else we've been it's incredibly creepy，and only in recent months frankly in the，past couple of years。



![](img/1640fde899975b31be8bfdc31ceb2f81_169.png)

have companies like apple and even，google to some extent。



![](img/1640fde899975b31be8bfdc31ceb2f81_171.png)

are browsers，disabling what are called third-party，parties，it's not going to eliminate the problem。

but it will make it much harder，but there's a trade-off there too。

whereby it might get more expensive to，use certain websites if they can no。

longer make money off of you as the，product but need to charge you as。



![](img/1640fde899975b31be8bfdc31ceb2f81_173.png)

the user let's see over to phillip or，oh brian there we go what if someone。

gets a picture of you and shows it to，your phone，oh a good question what if someone gets。

a picture of you and shows it to your，phone and you're referring to like the。



![](img/1640fde899975b31be8bfdc31ceb2f81_175.png)

phone being able to unlock itself，yeah so typically phones are resilient，infrared。

uh which is a spectrum of light that we，humans can't easily see。

and that means that it isn't necessarily，as，easily in the movies this is very often。

the case you hold up a picture of，works，it doesn't work as well with physical。

hardware however if you had enough time，and talent you quite possibly could，create like a dummy。

a puppet of some sort that looks and，feels and is the right temperature 98。6，fahrenheit for instance。



![](img/1640fde899975b31be8bfdc31ceb2f81_177.png)

that resembles that person closely，enough that，absolutely you could pretend to be that。



![](img/1640fde899975b31be8bfdc31ceb2f81_179.png)

person now if you have people trying to，hack into your phone by creating puppets。

out of you that are that accurate you've。

![](img/1640fde899975b31be8bfdc31ceb2f81_181.png)

about，but um it's indeed possible less so with。

![](img/1640fde899975b31be8bfdc31ceb2f81_183.png)

other questions or comments on security，or passwords cookies or the like and。

again feel free to drop off if you have，to it's just open q a now。

yeah there's a question from esther，esther，esther um thank you。



![](img/1640fde899975b31be8bfdc31ceb2f81_185.png)

if we've just been clicking and，accepting cookies，is there a way to go back and。

like clean that up so that you're，you're not continuously being tracked。



![](img/1640fde899975b31be8bfdc31ceb2f81_187.png)

yes so and i should have addressed that，earlier um，short answer yes most browsers today。



![](img/1640fde899975b31be8bfdc31ceb2f81_189.png)

instance or，private browsing mode which actually。

![](img/1640fde899975b31be8bfdc31ceb2f81_191.png)

private，in chrome，essentially that clears your cookies，that window，configure。

most browsers if you poke around the，appropriate settings，to delete your cookies after a day or。

after a week or after every session，but here too there's going to be a。

downside cookies are a wonderful thing，technologically，because they enable websites to remember。

that you and i have been there before，and that you and i have logged in before。

and indeed it's for login purposes that，on amazon，and every time you clicked a new product。

you had to log back in again to add it，to your shopping cart，unusable。

you would probably go shop somewhere，else and so there's this trade-off where。

you probably do want cookies to work，but you don't want them to work or stick。

around forever and thankfully again，up to this，whereby it is all too often uh computer。

programmers instincts to keep data，around in perpetuity maybe it'll be，useful eventually。

nowadays companies are getting better at，getting rid of data and some of this is。

coming from political pressure，especially in the eu for instance。

but it's changing slowly but thankfully，it's changing。



![](img/1640fde899975b31be8bfdc31ceb2f81_193.png)

but in short if you poke around your，browser settings yes you can clear them。

manually or on a schedule which might。

![](img/1640fde899975b31be8bfdc31ceb2f81_195.png)

not be such a bad thing，other questions on security another，question from steve。



![](img/1640fde899975b31be8bfdc31ceb2f81_197.png)

steve back to you okay um。

![](img/1640fde899975b31be8bfdc31ceb2f81_199.png)

frequently you'll see websites or or，you know other areas on the web that ask。

if you want to use your，email credentials let's say you have a，gmail account。

and they want to use those credentials，to log into their，to their site now that seems like a。

really bad idea，what do you what do you think about that，it's that's a good question so。

it probably is not a bad idea if the，website has implemented it properly。

if you are being asked on a website for，password，that is a very bad thing and this used。

to happen often and some websites still，do this even gmail and yahoo。

in order to link accounts will sometimes，ask you to type in your username and。

password for another email account，the reason being they need that account。

in order to fetch your emails，but what i think you're describing is。

actually more commonly used on the web，more generally these days where you can。

log into a lot of websites，using an existing gmail account or，microsoft account。

or apple account or bunches of others，and thankfully that is typically，as。

oauth a-o-a-u-t-h version two，and this is actually a pretty fancy。

technology and cs50 uses this for all of，its websites whereby，you are redirected from a website to。

google you will then do log into google，and google essentially sends back a，mathematically，website。

that tells them what your name and your，email address are but does not tell the。

website what your password is，and so long as google has approved this，website for using this feature。

of authenticating them via oauth they，are allowed to authenticate you in this。

way and the idea here is really，transitivity in the mathematical sense，will and。

rather if this website trusts google and，google trusts you，then the website can trust that you are。

in fact steve，but you should always make sure that，when you're typing in your。

gmail username and password that the url。

![](img/1640fde899975b31be8bfdc31ceb2f81_201.png)

is literally google。com and not，randomwebsite。com。

![](img/1640fde899975b31be8bfdc31ceb2f81_203.png)

other questions about 15 minutes left，for open q a if folks have questions，are they and。

do they help us be more secure on the，web yeah vpns or do they help us be more。

secure so a vpn is a virtual，private network if you work for a，company or go to a university you。

quite likely have access to a vpn at，university，anywhere in the world。

typically to your campus or to your，company's network，in a secure way what does that mean in。

an encrypted way，so you run special software on your mac，or pc or phone。

that software connects back to your，campus or back to your company，using encryption so scrambled。

information so that all of your internet，traffic now goes from your laptop or，desktop or phone。

encrypted to your company or to your，campus and from there，it goes to the actual websites that。

you're visiting a vpn tends to be，you and，only you and other employees or students。

with access to like，websites，on campus or at that company or。

as many students in today's meeting will，likely know it often helps you。

access netflix and hulu and other，websites from countries that don't。

support them or where content is，effect，coming from an，ip address that is an internet address。

at your company or at your campus so if，i'm traveling abroad。

internationally somewhere outside of the，visit，gmail will，think that i dave and malin am in the。

united states，even if i'm in a completely different，country and so for better or for worse。

it can be used both for secure purposes，and also，circumvention purposes but it also is a。

good thing too especially in do，uh if illegal sometimes um in，geographies where there might be。

government censorship vpns also allow，people to essentially，teleport in some sense to a different。

country so that they appear to be coming，secure，that government that company that big。

brother so to speak，least without，always the downside，they will tend to slow things down so if。

you are in some other continent of the，the world trying to vpn into harvard to。

watch netflix now all of your traffic is，going back and forth and back and forth。

and you're probably not going to get as，good of an experience even though you，might have an actual。

other questions brian yeah over to uh，let's see over to uh，hello can you hear me yes we can what's。

your question，uh yeah so my question is that how，do you connect the laptop from which。

you're hacking for example，that time，the，cracking the codes for pin codes and all。

how do you connect it，to a mobile phone or another laptop，which you're hacking。

it's a good question i don't know，offhand i've not actually done it myself。

it should is typically possible，with uh the right type of hardware so。

the right type of cable which tends to，be pretty straightforward。

but you sometimes actually need special，software running on the device which is。

easier on some devices or，others i suspect this is not very easily。

done just by plugging into an iphone，read up on it，um so i would refer to google for。

resources on this if curious to see just，how possible，it is but much like you can connect。

itunes and other software to the iphone，there's definitely a way for these tools。

to communicate but it's getting，increasingly difficult by design which，is probably a good thing。

araceli if i'm saying your name right um，to meet，you yes we can what's on your mind my。

professor my name is araselli i，do have a question what about the，safe。

what did what what did you say the lock，patterns for the phones you know where，you connect the。

dock yeah the lock pattern so where you，move your finger up down left and right。

so those are it's a good question um，those it depends on how complicated they，are and how long。

your path is if it's just up down left，right which is the equivalent probably。

of just four characters，the idea of these patterns if you've。

never seen is you can essentially draw a，polygon a picture on the screen。

and if it matches closely enough what，your pattern is it lets you in。

i think the answer there is going to be，the same it depends on，what how long or how complicated that。

pattern actually is，how forgiving the software is to you，being slightly off。

the path that you followed previously，and also it depends on。

who else is looking over your shoulder i，will admit that i very often see my，thing on their phones。

because by design it also tends to leave，a trail so that you as the human can，help you draw it。

but that's who is going to be a，trade-off so i i don't know，um in the security research world where。

they're regarded it's probably meant to。

![](img/1640fde899975b31be8bfdc31ceb2f81_205.png)

secure，i can probably type something more，random and also cover things up with my，drawing。

on the screen there but i'll read up on，the，mathematics of it depending on the，length before。



![](img/1640fde899975b31be8bfdc31ceb2f81_207.png)

other questions a few people are asking，for software recommendations that if i。

want to have a secure text message，conversation with someone or a secure，video call with someone。

without the company being able to，intercept the conversation，uh what tools should we use yeah so to。

their credit apple is actually，done really well i think in sort of。

building their business in part not just，around hardware but around privacy。



![](img/1640fde899975b31be8bfdc31ceb2f81_209.png)

principles far more so than like the，you。

![](img/1640fde899975b31be8bfdc31ceb2f81_211.png)

are the the the product so to speak uh，because they're using advertising and。

other mechanisms to monetize。

![](img/1640fde899975b31be8bfdc31ceb2f81_213.png)

your usage of the services um so，imessage for instance is probably a good。

place to start of course you have to，have a mac or an iphone for that to work，so it's more exclusive。



![](img/1640fde899975b31be8bfdc31ceb2f81_215.png)

um in the android or pc or computer，world more generally，whatsapp is quite popular you might have。



![](img/1640fde899975b31be8bfdc31ceb2f81_217.png)

owned by。

![](img/1640fde899975b31be8bfdc31ceb2f81_219.png)

and has been，to，take at face value that these，products claim to be using end-to-end。

encryption but at the end of the day if，code，the code in which those programs are。



![](img/1640fde899975b31be8bfdc31ceb2f81_221.png)

written it is certainly theoretically，possible that one or more governments be，it ours or another。

has somehow inserted themselves into，that process so that it's not as end to，end as you might think。

therefore there are also open source，initiatives which means code written by。

people in the community where the source，code is published for all to see。

which doesn't uh eliminate the，possibility that there are back doors so，code。

but at least if a lot of smart people。

![](img/1640fde899975b31be8bfdc31ceb2f81_223.png)

and can vet it，the probability that those things are，hidden in there is probably lower so。

their software like signal，uh which i believe is open source，telegram which i think。

might be i would have to google to，double check and a few others，as well other questions over to max。

types of，attacks that you could do other than，brute force attacks，to access a password yeah。

really good question other types of，like the，most simplistic attacks which are brute。

force start at the beginning and go all，the way to the end，but there's something to be said for。

what you might see in tv and movies，where you guess someone's birthdate。

or maybe you guess their their um you，know husband or wife's birthdate or。

someone in their family or maybe their，mother's maiden name or the name of。

their first dog or any of those security，questions that websites often ask。

frankly you might think are good because，only you know what the name of your dog，was growing up。

but no if you posted that answer on，social media no，dogs names tend to be fairly common and。

so it's probably not that hard to guess，all possible dog names，you can also do what's called a。

dictionary attack and in fact instead of，from zero。



![](img/1640fde899975b31be8bfdc31ceb2f81_225.png)

zero zero zero on up to 9999 i could use，letters of the alphabet and start with。



![](img/1640fde899975b31be8bfdc31ceb2f81_227.png)

the b，words c words d's and so forth and just，dictionary，which might still have thousands or。

hundreds of thousands of words，but that's going to be far fewer than。

the quadrillion possibilities that i，started alluding to earlier。

so again a piece of advice today might，be if your password is。

someone's birthdate or a pet you grew up，with or the name of the town you were，born in or the like。

those are not hard pieces of information，to guess to look up in a dictionary to，often。

so yes there's unfortunately more，sophisticated attacks by using those，kinds of heuristics。



![](img/1640fde899975b31be8bfdc31ceb2f81_229.png)

tricks to start with the obvious and，else。

![](img/1640fde899975b31be8bfdc31ceb2f81_231.png)

seems to be working other questions on，yeah over to uh let's，is，how safe is saving your passwords on。

chrome edge，etc like their browsers ask you to，remember us right sometimes yeah so。

built into a lot of browsers today，essentially our password managers i。

would have to read up on the particulars，to know what kind of，like to。

think that if you're using them properly，they are encrypting things somewhere on，your hard drive。

or somewhere in the cloud using your，the like，brian do you happen to know if the。

browser's built-in password managers，i'm not sure offhand i would have to。

look into it a little more yeah if you，don't mind if you want to email me i can。

try to look that up later i don't know，and i'm hesitant，to answer only because i don't want to。

recommend the wrong thing i use a，third-party password manager that。

works outside of browsers as well like。

![](img/1640fde899975b31be8bfdc31ceb2f81_233.png)

lastpass or one password the types of，things i mentioned earlier。

i don't know offhand um but i would do，your due diligence first and i would，google something like。



![](img/1640fde899975b31be8bfdc31ceb2f81_235.png)

does safari encrypt passwords or does，edge encrypt passwords，and then think to yourself well how is。



![](img/1640fde899975b31be8bfdc31ceb2f81_237.png)

it encrypting it is it using my username，and password and if so is it doing it on，my mac or pc。



![](img/1640fde899975b31be8bfdc31ceb2f81_239.png)

is it doing it in the cloud and try to，take those ingredients as。



![](img/1640fde899975b31be8bfdc31ceb2f81_241.png)

um factoring into your own decision，time for one or two more questions i。

and do use your zoom virtual hand just。

![](img/1640fde899975b31be8bfdc31ceb2f81_243.png)

![](img/1640fde899975b31be8bfdc31ceb2f81_244.png)

yeah can you hear me we can yes okay so，um i'd like to ask that you know。

these days uh especially in android，phones we're actually seeing a lot of。

optical um in display fingerprint，scanners and face scanners uh where you。

can just you know touch the display，separate，hardware visible fingerprint scanners。

and you know we all know that apple did，a very good job with，touch id and even face id these days so。

i'd like to ask um are these optical，in-display，solutions secure if not actually even，more secure。

than the capacitive um，you know touch id or the capacitive，fingerprint solutions we got to see。

earlier on，that's because yeah those were very，secure in fact um。

reports were saying that you know they，could easily determine if the。

hand was uh dead because you know there，was no electricity passed through it。

so yeah it's a good question i don't，know i would have to read up on the。

state of the art there i'm not sure just，how much the academic community has。

uh vetted those kinds of devices yet，where you you're actually touching the。

glass and doing the protection，underneath it。

![](img/1640fde899975b31be8bfdc31ceb2f81_246.png)

i'm guessing there's some amount of，tolerance that is documented there or。

maybe it's not even publicly documented，by the various private companies。

whereby with some probability。

![](img/1640fde899975b31be8bfdc31ceb2f81_248.png)

only you will actually be able to unlock。

![](img/1640fde899975b31be8bfdc31ceb2f81_250.png)

relatively，uh small number of other people，probabilistically who have similar，enough fingerprints。

it's i would have to read up on the due，diligence there as an aside。



![](img/1640fde899975b31be8bfdc31ceb2f81_252.png)

as we focus on these biometrics consider，actually have been doing something。



![](img/1640fde899975b31be8bfdc31ceb2f81_254.png)

clickers，that use a little small battery and use。

![](img/1640fde899975b31be8bfdc31ceb2f81_256.png)

your car，and unlock the doors or even start the，engine even those historically have not。

been terribly secure there might be，only several thousand or tens of，thousands possibilities。



![](img/1640fde899975b31be8bfdc31ceb2f81_258.png)

but it has been documented that you，could take some of those cars clickers，mall。



![](img/1640fde899975b31be8bfdc31ceb2f81_260.png)

or a department store and the like and，if you click it enough you may very well。

unlock someone else's car because the。

![](img/1640fde899975b31be8bfdc31ceb2f81_262.png)

company manufacturing that clicker just，hasn't used enough，possible codes to keep the devices。

secure and this is true with physical，keys too if you think your physical key。



![](img/1640fde899975b31be8bfdc31ceb2f81_264.png)

is secure that's probably not the case，especially if it's a locksmith a local。

human who has actually decided。

![](img/1640fde899975b31be8bfdc31ceb2f81_266.png)

what level of permutations to use on，your metal key，quite possibly your metal key could。



![](img/1640fde899975b31be8bfdc31ceb2f81_268.png)

unlock your house and someone else's so，different，in software is pranav's alluding to is。

really just the，complexity of or the space of possible，values or permutations。

and for that again on things like the，glass-based technology i would have to。



![](img/1640fde899975b31be8bfdc31ceb2f81_270.png)

read up，oh hi hello can you hear me we can yes，hi um i had a question does harvard。

teach an online cyber security class or，is the one you recommend，good question brian i don't know if。

there's one online they certainly are on，campus，brian do you mind a quick google yeah i。

definitely has，other cyber security classes by other，universities it looks like mit has one。

and a couple of others too，so definitely options that are out there，indeed well thank you for that。

and all of the questions i want to be uh，respectful of everyone's time so whether。

you are a cs50 student or，family member or cs50x student or friend。

thank you so much for joining us today，uh we look forward to seeing you in。

future class and all the best with。

![](img/1640fde899975b31be8bfdc31ceb2f81_272.png)
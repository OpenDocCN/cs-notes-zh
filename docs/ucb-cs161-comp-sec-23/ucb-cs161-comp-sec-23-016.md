# 016：UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p16 -16--CS161 FA23- Lecture 16 - SQL Injection and CAPTCHAs.zh_en -BV1YGbceREDs_p16-

![](img/1993cff87a35f6dd2f2eff4cf6cdfeb8_0.png)

Okay， sorry for not being here on Monday， we had a midterm for 18 the other class so wait to go take care of that but hopefully an site so could care of you and told you all about SQL injection or not SQL injection I'm telling you about SQL injection they told you about excessS or crossside scripting so。

The key vulnerability that makes Prostate scripting tick just to quickly review is that。

The server provides or I guess。The server stores data or provides data to the user and if that data is supplied by an attacker then it looks like it's coming from the server even though the attacker supplied it so that's kind of the rough idea of why excess is a problem the problem is that the attacker can provide data to the server and then the server can serve that data to other people and it looks like that data is coming from the server even though its really supplied by the attacker so there are two classes of excessS that you learned about and。

When I think about these two classes I always think of them using an example like the canonical example is how I remember which one is which so for stored accessS I could define it。

 but to me I think of the canonical example being like Facebook or Twitter or whatever they call Twitter nowadays like one of those websites that social media website with a bunch of posts and so the way I think of it is imagine if someone makes a post and inside the post they have some jascript that gets stored on the servers of Facebook and then when you go load Facebook and you load that post what happens the server takes that ja post and serve it to you and you see that post and it looks like it's coming from Facebook or that Facebook served it to you so that jascript runs with the origin of Facebookcom it looks like it's being served by Facebook has access to any like cookies or secret values that the jascript from Facebook would't be able to access however that was actually code written and injected by the attack so。

To me that's the canonical example of Sex success， what makes it stored is the fact that the attackers chosen in JavaScript gets stored on the server like permanently stored in their database and then when you load that website that JavaScript gets loaded to you by the server so as the victim when I see that JavaScript I'm seeing it loaded through Facebook。

 that JavaScript has all the privileges that Facebook's JavaScript would have but it was injected there by the attacker。

Okay and then the second class of attacks is a little bit weirder。

 but it's called reflected XS and here the canonical example that I always think of is like Google or a search engine and so why do I think of search engines because I think about well if I go on a search engine and I click search like what does the URL look like so if I click on Google I type in like potato and I click search the URL that I get redirected to or the URL whose data gets loaded back to me it probably looks something like this right so it's like Googlecom and this is still mostly review and it's like something like I don't know search and it takes into URL parameter and kind of the key is that if you look at the URL parameter。

Part of the URL parameter includes the string that I searched for so I searched for potato。

 this URL contains potato and then the thing returned by this URL will say something like you know 10 results for。

O都 okay。So the key idea here is that if I click on this URL。

 I get a page back with the exact same text and it tells me 10 results for whatever it is user search for or user for this string and if I replace this string with anything else。

The return page will also have that same string。And in particular。

 if I replace this string with some piece of JavaScript script alert One script and someone clicks on that link well then they get redirected to a patient that looks like this that says 10 results for script alert one script and so that script alert One script again it looks like it's coming from the Google server but it was really injected there might be attack was able to injected because Google gave you this place where you can type in any arbitrary string you want in the request and that arbitrary string gets reflected back to you in the response so now anybody who clicks on this malicious link they will go to that link and when they go to that link。

The string in the link gets reflected back at them， and it looks like it's coming from the server。

 but it really came from the attacker。 So that's the canonical example that I used to remember what reflected excess is and so。

Those are the two categories of XS reflect that XS has one extra requirement to make it happen。

 which is that you have to make the victim click on a link so in XS。

 if the victim just loads the Facebook website with a post。

 they get hit with the jascript and now their browser executes the ja and reflect that XS there's a little extra challenge which is that the attacker has to make the victim somehow click on this special link and only when the victim clicks on this special link do they get redirected to this special page or directed to this special page where that input in the URL gets redirected back at them so somehow the user has to click on that link and they can use any of the strategies that we've talked about so far for tricking user into clicking on a link so we can send the user an email that's like free iPhone to click on this link we could use It know go on some like website that the user visits a lot and like drop the link there and hopefully they click on it we can use like pay for an advertisement that like loads this page lots of different ways to get the user to click on this link。

Okay final note I'll make before I move on again， I'll review from last time is that even though reflected XS and CSRf。

 which is the attack from two lectures ago， they both require you to click on jascript the reason why they' attacks or they're vulnerable is quite different right so even though they share in common this feature that the attacker has to make the victim click on the link。

 they are really quite different attacks， if you drill down and think about like what fundamentally is causing them to be vulnerable so reflect that XsS。

 the reason why it's vulnerable is because of the jascript so when you click on the link the thing that gets returned contains the same ja and the ja runs that's why clicking on the link is dangerous by contrast in CSRf there is no jascript at play at all you can execute a CSRf attack with no jascript at all in CSRf the reason why clicking on a link is so dangerous is because when you click on the link that causes cookies to automatically get sent and when the cookies automatically get sent the server thinks。

The request is coming from you， even if you didn't mean to send it so even though both attacks required the victims to click on a link。

 the reason why they're clicking on a link is really quite different CSRF clicking on the link is vulnerable because of the cookies being attached nothing to do with JavaScript and and reflect that excess the reason why clicking on a link is so dangerous is because the value return from that link contains JavaScript that are gets executed nothing said about cookies so they share a step but just because they share a step doesn't mean they're the same attack it's a common thing to get those two mixed up at this point now that you've seen them both but like in essence they're quite different things。

Okay and all of it goes back to the key vulnerability。

 which is that the server is accepting any arbitrary input and giving it back to users so the server accepts any string。

 you put in like ebot valid string you put in script alert at one script valid string and so the server is accepting any old string and then giving it back to the user so this is a server side problem。

 the server should not be accepting all of these strings and returning them directly back to the user as HTML because otherwise now the user could interpret this stuff as JavaScript or HTML so there are some defenses one defense is that you allow the user to type in the weird things like script alert at one script but you escape those characters and if you escape those characters now they're not treated as script script tags or now they're not treated as JavaScript syntax now they're treated as like a literal lesson than sign and a literal or greater than sign and a literal so if those get loaded into the victim's browser they're not executed as JavaScript。

You just see the raw text of the script text okay so that's one possible way to sanitize things we saw that sanitizing things is really tricky and you shouldn't try to write your own sanitizer in the same way that you shouldn't try to write your own cryptography there's too many different edge cases it's much better to use some library that's already done it for you there are also more fancy defenses like templates where it's kind of like a parameterized sQL which we'll see today and the idea here is that。

Again， it's some library out there that generates the HTML and then plugs in the user input including the script tags for you and does so in a very careful way to make sure that the user supplied input。

 even if the user supplied input contains script tags never gets executed as JavaScripts and again this is something that you wouldn't write yourself in real life。

 you would certainly outsource it to some other library that does it for you。

And then the final defense is a browser side defense， which says。

First remember all of excessS as a server side vulnerability so both of these defenses come from the server who needs to be careful of how or like what HTML they serve back to the user and what inputs they accept from the user so both of these are defenses from the server but there's also one way for the browser to be more careful about excessS attacks it's called the content security policy and so here the browser enforces a set of rules that says I am only going to execute the jascript that gets loaded from an HPP response if it satisfies this sequence of rules and there are certain rules that you can use to make XSS attacks harder so for example you can say I only trust jascript if it was loaded from one of these websites that I trust if I just see some random jascript floating around and I cannot verify that this jascript came from a trusted source I'm going to refuse to run it this is only the browser would enforce because the browsers the one running jascript but you can tell the browser hey please be really careful and if you just see some jascript coming back in the response like maybe。

Directly inside the HTML that could be really suspicious and it might be the sign of a I attack so please don't run that。

 but if you get some response back in the loads JavaScriptscript from a trusted source like maybe you trust all the JavaScriptscript with domain Google。

com or something then we can allow those to run so you can tell the browser what types of JavaScript you want to run which ones you don't what do you trust what do you not trust that's a browser site defense against excess。

O。Any questions about XS and stuff from last time？Okay。Cool and then the second part of last time。

 I hope if any of this seems like brand new to you， by the way。

 like let me know because then we're gonna have to do some catching up okay so hopefully last time you also learned about clickjacking and user interface attacks so clickjaing it's a really fancy name but all that it really is is the user when you click on something the browser is forced to assume that you actually meant to do it So if somehow you can consider human factors and trick the user into clicking as something that they did not mean to click on then now you stolen the user to click and the browser is forced to assume that the click is valid if I like click on a download button the browser has to assume that I intended to click on it the browser can't be like oh but maybe the user got tricked the browser's not that smart the browser says if the user clicks on something I assume the click was intended and I will do whatever that click results so as the attacker if you can display something to the user that tricks them into clicking as something that didn't mean on clicking so for example you put up like a bunch of shiny download。

Buttons around the real download button or you make some frames invisible so that the user thinks that they're clicking on something。

 but they're really clicking on something different。

 you can convince the user to click on something that they didn't mean to click on and the browser is forced to accept it the browser is not that smart doesn't know whether or not you meant to click on it so the ways that to defend against this are to be careful with the way that you present your websites so these are mostly I don't know。

 the browser or server side defenses I'd say it's a bit of both but the browser and the server can work together to make it harder for the user to get tricked so for example I can force the user to see if the users clicking on this download button I can like focus the users attention on like here's where you're clicking so please be really careful make sure you really mean to click on this and don't get distracted by this fake mouse that someone is drawn for you for something or we can be really careful with the time at which the user click something so they maybe click trackingracking attacks where as soon as my mouse hovers over something like the instant before I click the attacker makes a button appear and suddenly。

When I click I didn't mean to click on the button but it suddenly appeared or now I clicked on the button that just appeared。

 I can also enforce you know try to defend against those by giving the user time to understand when I click on something like pause for a second did you really mean to click that Yes you did okay then I'll take your word for it you can also ask the user like hey you have clicked on something really weird are you sure you want to click on that thing and the user can say yes or no so those are all different ways to enforce or to stop clickjaing and one possible way to stop is also to say if I'm a website I'm not going to allow other websites to embed me so。

I'm not going to allow other websites to use the iframe to put the contents of my website inside their website because they might do funny things and try to steal clicks on my website。

😡，Okay， so that would be server side defense。Okay that's clickjacking and the final thing we talked about is another human factor based thing from last time called phishing and here the idea is that here the attacker is going to impersonate someone legitimate so the attacker they're probably not someone legitimate but they could pretend to be someone legitimate so out what the exact example is but maybe the attacker comes up to you and says I am the real Paypal please give me your password or like I am Google please give me your password so that I can show you some emails or whatever so here the attacker is pretending to be the server going up to the victim and trying to trick the victim into providing the attacker with some secret information like their password or some like verification code we talked about how it's really tempting when you're trying to defend it against fishing to be like how could users possibly be this dumb just don't get fished but remember it's really tricky because attackers are really good at pretending to be the server and attacking this is really hard。

if users aren't trained to defend against fishingishing so we really can't blame the users for being in a scenario where they haven't been trained to detect this。

 even if you are trained to detect it， detecting fishingishing can be really hard because attackers can do really clever things like they can write Google co but instead instead oh they use a zero and maybe a lot of people will't notice that so you have to be really careful okay and then we talked about the defense against phishing which is that the user needs to prove their identity with two different methods so this way even if the attacker fishes you out of one of the two factors the second factor still protects you so if you accidentally get fish like the attacker comes up to you and says I am Google co and I'm requesting your password so I can give you this super important email like please give me your password and you mess up and you give this attacker your password well normally you'd be in trouble but if you have two factor authentication and enabled the idea is that there's two different ways you need to prove your identity。

So even if the attacker steals your password， they probably don't have a second way to prove that they're you and the three different categories of ways that you can prove your identity are something you know that's like your password or some secret pin code that you have so even if the attacker steals that they might not have these other two things so second way of verify who you are like something you own so why do those websites always text codes to your phone because your phone is something that you own and so that's the second factor they want something you know which is your password they also want something you own and to verify that you are the person owning your phone and you're trying to log in they'll like text you your code or something and then more exotic ones exist as well like something you are so like your fingerprint or like your face something to identifies you physically。

And so this depends against attacks where attacker has one of your factors。

 but if they don't have both of your factors， then they can't log in as you so the attacker now has to steal two of your factors somehow。

 there are different ways to do this。 So one way to do it is the attacker could fish you into both factors is they could say I'm Google please give me your password okay thanks and please also give me that verification code that you just got from the real Google give me that too so somehow the attacker could fish you into giving up both of your factors you have to be careful the attacker could also use social engineering where they like call up the bank or something and say oh I'm the user and I got locked out of my account please like please I'm begging you like reset my password and maybe some humans will get convinced by that so that's like social engineering it's a huge topic it's also something we're gonna to talk about a lot but involves like psychology and like economics it's really interesting okay and there were other ways to stop twofactor authentication like security keys is a way to stop them so。

Really deep topic we kind of skimmed the surface of it。

 but this is like cutting edge if you're curious about like users。

 how do we make sure that the tools that we give to users are foolproof so even if a user isn't totally security aware we're giving them the strongest tools that we can so that even if the users mess up hopefully they don't mess in a way that's devastating。

Okay， cool， that's all stuff from last time I figured I'd just give you a quick summary if you wanted to hear from me。

 but sure， Anna and Sa Ts did a great job explaining it too， Okay， but I had a extra of time to do。

 so figured I would。😊，Okay。Here's all the new stuff so sorry to bore you with all the review here's all the new stuff for today so today's another twopart lecture like last time last time the first part was all about XS which is more of a technical topic we had to understand the attack and the steps of it and understand why it's subverted the same origin policy so today our first topic is also more technical it SQL injection so we have to understand how SQL works and what this attack looks like and all of its different steps and then in the last like 1020 minutes just like how we talked the phishing last time and it was kind of a lighter topic more high level we'll talk about captures at a very high level you can just sit back watch the pictures look at the examples and then we'll be done with all of web so two more topics to go。

Okay， so I'll start with the technical topic SQL injection and then when we're all tired around like 620。

 I'll tell you all about the lighter topic which has kept us okay so you've seen this chart over and over again in fact like I didn't get a teach to you this semester unfortunately but you saw the number one most common one as of 2020 which was XSS I think it was still number one like at least a year ago I don't know about 2023 but like it's always up there it's so common even though we know how to fix it and today we have another one that is so common like top six even though as we're about to see there are always the defendant tested okay。

So。To understand this， I have to present a model of how the web works and how web servers work and again this is kind of a rough model it's enough to tell us about SQL injection but in general this is not how a website has to be designed but it's a strong enough model to motivate why SQL injection is a thing so you can imagine that like any web server out there is's probably gonna to have data to store and they could have a lot of data like imagine I don't know like Netflix okay well Netflixs going to have tons of data to store they have to store user information they have to store like all of our watch history to spy on us or whatever they have to store all those gigantic movies and TVs and videos that they're going to serve to us so this is a website whose backing server has to be massive to store all this data or you can imagine like Google must have some sort of massive data of like all of the files that I upload to their servers or all the search results that they're going to give to me that are cache or whatever so somehow all these websites are going have massive backing data arrayse store。

All this data and usually the way that these servers are built is that they're gonna have some coding logic that handles my request so like when I say please retrieve a file。

 there's some code that process of which file you want but then there's also going somehow be some sort of database that actually stores that massive amount of data so there's a like cartoon picture of what it might look like so this part you've seen before the client and the server talk to each other using HtTP we've seen this before a web server is some piece of code that like handles the request and says for every incoming HttP request how do I think about this request and what response do I give back to the client all of that lives here in the web server the client that's us that's our browser sending the requests and receiving the responses and running the ja so we've seen these to interact before but the web server itself it has a lot of data to store like it has a ton of data that users uploaded where it has all these posts that it has to store where it has all these movies that it has to serve。

Client well sometimes the web server will have a backing database to keep track of that So instead of the web server scoring it themselves。

 maybe the web server has some backing database and the web server can talk to the database and say well the user just sent me this HttP request and this HttP request requests requires fetching this really specific file inside my like terabytes of storage so instead of the web server trying to figure out how to find that file themselves the web server might say that's too hard for me I'm just gonna go to my database make the database find whatever it is i'm looking for in this gigantic file system and then the database will return the request to file to me so I'm going say hey I really want to watch X movievie okay I shouldn't say X movie but I I meant that as like arbitrary movie not X rated movie but if you really want to watch an X- rated movie like your free time so we make a request say I want to watch G rated movie great。

Family friendly web server says okay here's the movie I want to watch but like I'm not the one responsible for destroy sting these really big files so I'm going to go back to the database server and say can you find the movie the user is looking for and like give me back that data the database server says sure I'll do that and I'll give you the data you're looking for and then the web server will format the response all nice and HtTP and then give it back to the client now the client can watch their really safe family friendly children's movie or whatever it is they want to watch okay。

Great， and so how do the client and web server talk the language that they use to talk is HtTP we've talked about this HttP is the language that allows the client and the web server to communicate in a way that makes sense to both of them So this way when you send an HtTP request or you receive an HttP response you both know exactly how to read it because you're speaking the same language you're both following the same rules that's great So how do the web server in the database server talk again。

 these two have to have some language that they both speak so that the web server can ask questions and the database server understands those questions and the database server can send responses and the web server can understand and parse those responses they have to be speaking the same language otherwise if the web server send some request and just writes likeD database server。

 please give me something database server is going be like I don't know what this says so somehow they have to both understand the same language and there are lots of different language is out there but kind of the standard that you'll see and the one that well see in this class is SQL okay so。

😊，Before I can tell you all about the attacks， we have to do a quick speed run of how SQL works and how databases store all this data and the language that they use to communicate to each other。

 So I actually don't know how true this is anymore。 61。

 which is intro CS separately for those of you who are in other schools。

 they sometimes teach SQL and they sometimes don't and it costs a lot of trouble for us because I can never tell when you all like SQL experts or when this is just like completely foreign into you So I guess I'll hold the audience and is probably not a representative sample whatever have people seen SQL before in 61 or other context。

 Okay have people have people not seen SQL I mean it's totally fine like it's on 61 it's not on us okay that's okay it's totally fair okay so if you've seen SQL this will probably be mostly review and maybe kind of boring if you've seen SQL but like mostly forgotten it this might be a good refresher if you like use SQL every day in your life。

 this is definitely gonna be very boring and if you want to like take a nap but like go outside and take a walk enjoy the date I understand and we'll be back。

20 minutes to talk about the actual attack okay but for the people in here are on Zoom are outside watching the recording who haven't seen SQL totally okay like I don't understand how prerequiites work anymore。

 but okay so we're going talk about SQL and you can think of SQL for the purposes of this class as like a way to read these tables of value so our databases are going be stored as these really big tables and you can possibly have multiple tables in a database if you want to but the table itself is going have this really specific structure where there's going have it's going have all these different columns and each column represents some sort of field and then each row represents an entry of the table so I realize that all sounds pretty vague so maybe here's an example that makes it clear so in this table I'm organizing data in a very structured regimented way which is to say that each of these rows like this row this row this row they all represent a unique record and each record has a certain number of fields in this case I've chosen to say that every record has。

ID field and every record has a name field which is a string， every record has a likes field。

 which is a string， and every record has an age field which is a number and you can define the types of fields that you want in your table。

 okay？😊，And so the database server's job and what we're gonna to write SQL4 is to come up with a language to tell us if I want to request stuff from this table。

 how do I do so in a way that we understand and the database understands so I can ask the database please go into this table and give me all of the rows that have age greater than three or age greater than two does how do we write that how does the server know how to parse that that's what SQL is going to be for okay it stands for something I don't really care what it stands for personally。

 but there it is sometimes people call it SQL there are some properties that are important if you're interested in this stuff you're like。

 I find this interesting， CSs186 is the class that you're that's supposed to follow up I don't know if it's offered though but sometimes it is so that's the database class we're interested they'll talk about SQL in a lot more in a lot more detail but for this fast you just have to know the basics I'd say the only key thing that I want you to take away from this slide is that the SQL language is declarative which means that we don't actually have to。

how we want things done so if I want if I'm like hey I really want the row that has ages greater than two I don't have to specify how I just have to write a SQL query that says please give me all the rows that have age greater than two I don't have to specify how the SQL database will do that for me which is nice so it's not like I have to say oh please iterate through all the rows and if you see an age greater than two please return I don't have to deal with that the database will deal with all of the work of how to do things I just have to deal with what I want to happen in my SQL statement okay。

So what are all the building blocks of SQL and again if it's your first time we'll give you some practice throughout the class you just have to know the basics for this class so the first piece of syntax you'll see all the time is the select keyword what does the select keyword do the select keyword is useful if you ever want to go into a table and pick out certain columns that you care about so the select keyword is used if you want to narrow down the column for example perhaps I don't want all of these columns maybe I just want to list the names and if that's the case that I'll say something like select name from this table bots or maybe I don't want the name I want the name and I want the age but I don't want the other two columns that I'll say select name comma age so here the thing that comes after the select keyword that's a list of columns and it tells me exactly which columns I care about it doesn't help me narrow down the rows that's gonna to come later right now it just helps me narrow down maybe I only want some of the columns and not all of them so here I select two columns but the result is still gonna have all the rows inside so when I ask SQL for this query。

The results's gonna have all of the rows， but just two of the columns sliced out okay if you want all the columns。

 there's a star operator which basically says keep everything that way you don't have to list out every single column but it's just a shortcut okay there's also a really funky thing you can do and probably even if you've seen C you probably haven't seen this weird syntax before but there's a really weird thing you can do just you can select the constant which is kind of weird so maybe instead of selecting a row you can select the constant word C and what that does is it will simply give you a table of the row CS repeated over or the string CS repeated over and over again and likewise with the string 161 here and you you might be like why the heck what I ever want to do this but who knows maybe you for an attack this kind of exotic syntax might be useful okay。

That's how you narrow down columns How do you narrow down rows the way that you narrow down rows is you use the where clauses and the where clause gives you the ability to write conditions and what SQL will do is it will only give you the rows that satisfy those conditions so here's an example or eventually therell be an example you can use all sorts of these operators they're pretty familiar from other languages hopefully so here's an example of a condition I might want I might want only the only the rows where if you go to the likes column you find the screen pancakes okay and what SQL will do is it'll go to every single row1 by one and say is your likes column equal to pancakes yes。

 I'll keep you is your likes column equal go to pancakes no so delete I don't want to in this query your likes column equal to pancakes no so you don't belong in this query okay so this will filter out some of the rows so here I'm narrowing down the scope of the rows that I want I'm not narrowing down the scope of the columns because I chose to select everything at the start but I've narrowed down the rows to just the ones that I care about okay。

I can be more exotic so here I'm narrowing down the columns I only want the name column I don't want the others and what rows do I want to filter out I only want the rows where the age is less than two or the ID is equal to one so I can have more complicated combinations of conditions as well and now I'm only going to get the rows where this condition is true so either age has to be less than true or two or ID has to be equal to one so ID is equal to one keep age is not less than two ID is not equal to one delete ID or here the is less than two so keep so I have two rows to keep and I only want the name columns so hopefully I get something like that。

Great so those are the two rows that got selected that's how you fetch things from the table so if someone hands you a big table and asks you to select things out of it。

 these are the ways in which you have to know for this class how to select things there are more exotic ways to select things as well。

 but these are the ones you have to know if there's any more strange syntax we're gonna tell you ahead。

Okay。How do you modify a table Well the keyword for modifying is insert into and here's the syntax where it it's a little bit strange。

 but here's what you might want to do if you want to insert items into the array or into the table okay so here I'm going to create again I want to insert into the bots table so its essentially it might be a type of I think this is supposed to say bots because that's the name of the table that I want to insert into so all'll write insert into the name of the table that I want to insert into and then i'll use the keyword values to say here are some hardcoded things that I want into the table so here's a hard coded tuple of four values please put it into this table here's another hard coded tuple of four values please insert it into the table and they'll show up the table。

O。Great。😊，There's also something called update so insert is if you ever want to like sho extra rows in there and the only syntax you need to know for insert is the values keyword followed by a bunch of constant tuples showing what ends up being added to the table you can also update things and the update keyword is gonna be used to change what's in the table so you're not adding new stuff but you're changing stuff in the table and usually the update syntax is also follow with the where clause so use the where class to say which rows you want update so I'm going to say update here's the things I want to update and here's what I want to set so I'm going to say please change this column set are equal to this value but don't change every single row just change the rows that satisfied this condition so just like the select statements I can select out columns that I want to update if I don't want to update all the columns I can also select out conditions that help me narrow down the number of rows but ultimately I want to set some column equal to some value so here's an example and again most SQL syntax it's like kind of。

Readable if you just read it from top to bottom constructing it can be a little bit more tricky。

 but again we'll try to give you a hints whenever the syntax isn't super obvious but everything in this lecture is just the base simple stuff that you're supposed to know okay so there's an example of updating again I say update here's the table I want to update and well what rows or what columns do I want to update not all of them I just want to set the age row so there it is I said the age row or sorry the age column and I want to set the age column equal to6 but I don't want to change all the numbers to six I just want to change some of the rows to six which rows specifically only the rows where name is equal to willow so I go through the table find only the row where name is equal to willow of which there's only one and update its age column to six okay if you didn't have the wear clause like this I guess it didn't have that but if I didn't have the wear clause and I delete it then what's gonna happen every single age is gonna get set to six which is probably not what you want okay。

Finally there's a delete thing and just like before there's a where clause that tells you which rows to delete so if I want to delete a row I can say please delete all the rows where age is greater than six so those two get deleted and its mostly yet okay and the final thing that you might see now and then is create which is the keyword for creating new tables so if I want a brand new table I can create a new table here it's called cats I specify ahead of time which or sorry which columns I wanted the table so I want a table that has these four columns and I haven't inserted anything yet so it has zero rows。

That's what creating looks like and finally the last operation you might want to see or you might see sometimes is drop drop is kind of like delete but in delete you were deleting specific rows in drop you're dropping an entire table or deleting an entire table so I could say something like drop table bots and what's that're going to do it's going nuke that entire bots table completely gone so drop is the keyword for deleting things and you can imagine as an attacker we like deleting things sometimes okay。

Cool so those are that's like a theater of all the keywords you might encounter again。

 they're not something for you to memorize but to get familiar with your practice on by your cheat sheet if you want to want to memorize them。

 but we have to be able to understand what this language is like to do a text on it okay so that's it for all the SQL syntax anything you want to know about it。

Does anyone know who these two are？You know who the bots are， where're the last two？No。

 they're not  going of8。So Nick Weaver used to teach this class。

 those are his two cats so now you know， okay。If you look at some of the past exams。

 I think one of them has a photo full of the cats，Great， you don't have to know them for the exam。

 but those are next two cats and they have a place in the lecture forever Okay here' are some final little pieces of SQL syntax that you might see sometimes so it' just like in any other programming language SQL has comments。

😊，Except in SQL， if you want to start a comment， you don't use the hash sign in Python。

 you don't use the double slashes X C or Java， you use two dashes。 Why do you use two dashes。

 I don't know， but it is what you do So if I have some query and I want to add a comment at the very end saying what the query does or just leaving some note for myself the dash is what starts a comment So everything after the dash dash is treated like a comment and is not interpreted as SQL code and that's gonna to be super useful for attacks So it's easy to lose sight of like what the heck is this dash it's like a magical attack operator it's not nothing magical it is literally just the comment operator just like the double slashes inQ it just starts to comment okay。

Sometimes you'll see semicolon separate different statements this one is honestly implementation dependent so some SQL interpreters will allow you to write two queries in one if you separate them with the semicolon some SQL interpreters will force you to put a semicolon at the very end some will not force you to put a semicolon at the end and make it optional it really depends on the specific SQL interpreter that you're using so there's no hard and fast rule here。

So it's kind of like depending on what SQL interpreter back in you're using the semicolonons might make a difference。

 if it really makes a difference for our questions willll usually specify， but like in this case。

 we're going to assume that obviously on this slide the semicolon separates the two statements so lets us write an update statement which changes some rows followed by a select statement which pulls out some rows and returns it to the user all at once。

Okay， we've barely scratched the surface of SQL， so like don't go out and think you're suddenly a SQL expert from scratch。

 but for this class， this is kind of the baseline of what you need and anything else we' provide as we go。

Okay everyone mostly happy with SQL okay if you like fell asleep because the SQL review was too boring you can come back now because we're gonna to talk about real stuff or real attack content Okay not that SQL ist real content but wasn't a text okay so what is the SQL query look like so there's a bunch of fancy code I don't need you to read any of this code really but the key here is that think about what happens if I go on a website and I say something like I don't know。

 I go on a website and I really want to know about like paper clips I'm intensely curious about paper clips so I'm going to go on the website and submit a post request or a get request and it's all about paper clips so think about what the server now has to do the server now has to go to the database and request all the irrelevant information about paper clips that the user was so intensely curious about So what is the server going to do the server is going have to go to the database and request something about paper clips so what's it going to do server might do something like well I'll do a select。

I'm going to select all the items and their prices from this table of all the items I wish it could be like millions and specifically since the user cared so much about paper clips please give me only the ones where names is equal to paper clips So what has happened here well the user made this request so who supplied the string paper clips the one in red that's the user the user supplied the string paper clips and then what did the server have to do the server had to run the SQL query with the user's input plugged in wherever the name equals blank came in so if the user said I want paper clips and we have to put paper clips here if the user instead says something like oh I'm intensely curious about pencils and we have to put pencils has the string here or if the user says oh I'm really intensely curious about I can't I'm out of like office supplies I don't know why the user wants office supplies so badly but if the user wants I don't know staplers okay then we put the word staplers over here。

Okay， this is SQL query， it's run by the server， but we have to plug in some user input， okay。

So now let's think about what if the user puts in something really strange like instead of putting stapler or paper clip。

 what if the user puts a singular quote mark now why would the user do something so weird well I guess we'll find out because if we take a singular quote mark and we put it into this query now let's read this query what do we do the server takes the same query and after the name equals blank we fill in the blank with whatever the user supplied which in this case is just a single solitary quote and then what do we do we pass this to the database and the database does all the hunting through the items table and gives back all the items so we're gonna to pass this query to the SQL interpreter。

 what is the SQL interpreter going read like let's now act as the database and read this so I read select item price from items okay this all seems reasonable but like hang on a minute here because I see an opening quote and ending quote and a third quote。

I don't know about you the SQL interpreters don't like this right I should not have a mismatch number of quotes here I have three quotes the SQL interpreter reads this and says what the heck is this。

 this is not valid syntax， I expected an opening quote and a string and a closing quote you gave me three quotes that's not the right number of quotes so the SQL interpreter panics and says no I'm not executing this query you're not speaking my language so server error and then the server is just forced to return an error to the user and say I don't know what you requested but it didn't work database wasn't happy with what youre requesting。

Okay。So this seems pretty innocuous right okay the user type something and the server crashed Okay big deal But what if the user is a little bit more clever and writes something like this is this a valid string to pass in Sure the user could pass in anything paper staplr quote or one equals one Sure they can pass that in and what do we do we faithfully take whatever the user writes in red and plug it into the name blank and our query so our query has a blank and the blank is going to be substituted in with whatever the user gives to me so that I can run a query relevant to what the user wants and if the user decides to give me this extremely strange string in red well if I don't know any better。

 I'll just take that string in red plug it right into the SQL query and pass this off to the SQL interpreter now the SQL interpreter is going read this and the SQL interpreter doesn't know what part the user provided right the SQL interpreter is not like oh that part's red the SQL interpreter just reads this as plain no SQL so we can read this as the SQL。

terAs the database and we see okay select item price from items Okay pretty normal and the where tells me how to filter so as the SQL interpreter I read this and I say which rows does the server or the user want A the user wants all of the rows where the name field is blank so please give me those and also please give me any rows where this condition is true。

Okay are there a lot of rows where name equals blank I don't know how many rows are there where one equals one it's kind of a degenerate question but the answer is like all of them right if I go to any row and I ask K is one equals one true for this row who cares what the row contains and I go to another row and I say hey is one equals one for this row like yes right doesn't matter what the row contains one equals one is simply always true so this where class where does it evaluate the true on every single row so what is this going to return it's going to return every single item in the table okay。

So by providing this very strange input， somehow we were able to trick the SQL query and the SQL interpreter into returning the millions of items that are on sale。

 including like just everything right as opposed to just some specific item and that could be bad because maybe some of your items are a top seeker。

 you don't want to sell them or you don't want to show them to users yet。

 but here we're allowing the user to see all of the items by passing in this very strange input。

Okay let's do another strange one was this one'm gonna do again it's just some innocuous string the user could put anything here。

 they could put stable， they could put one equals one。

 they could put drop table items and what do we do we take this and we faithfully put it into the query where we plug it into the blank next to the name and we pass this over to the SQL interpreter and say here's here's my SQL query with the user's request plugged in please execute this as SQL the SQL interpreter reads and it reads okay well the user wants everything where name is equal to blank semicolon and the statement Sure I go through my table search for all the rows where name is equal to blank maybe I get some stuff maybe I don't who cares okay and then the SQL interpreter keeps reading because there's more statements to come and it see oh you want me to delete the entire item table okay very strange request but I'll delete the entire items table and now the entire items table is gone okay。

So that would be bad， so here's an case where the user has applied some input and suddenly caused the server to just delete an entire table。

 even though you weren't intended to do so。Okay。So that is the high level idea now let's think about what actually happens so maybe you follow this idea of like oh well。

 if the user types in some very strange input， they can cause the output or they can cause the resulting SQL query to do strange stuff let's like take a step back and think about what actually happened to this example so what actually happened is something called SQL injection and specifically what is happening is that the server has some query and the query has a bunch of blanks that the server expects to be filled in by the user so the user can fill in anything they want into the blanks and then the resulting query with the blanks filled in get sent over to this database and the database executes the whole thing as SQL so if the user is really careful they could inject their own SQL code into those blanks and then when the server sends that query to the database database is going to interpret the user's input as more SQL so now the attacker is able to execute any SQL that they want on the server。

As we saw， you can leak data like you can leak information about all the items in the table。

 you can add your own records or insert statements。

 you can update records like oh I really want the stapler be to cost like one sense so I can modify the record I can delete entire tables so anything that SQL the SQL query you can do the attacker can force that to happen and the reason why the attacker is making this happen is because those blanks that the server is expecting the user to fill it with like just regular old strings like stapler or paper clip the attacker can also fill those in with arbitrary SQL and if the attacker formats they're exploit correctly then now that entire string gets executed as SQL by the server or by the database and the database has no idea which parts were prevent by the server and which parts were injected by the user so that's why it's called injection because this query is sitting right there it's got a blank the user can put whatever they want in the blank normally we just expect normal old strings。

But if the user injects SQL， then that entire string。

 when concatenated with the user's input or like when the user's input is substituted into the blank。

 it reads as SQL that does other stuff that the attacker wants， okay？

Thats SQL injection so like I'm normally not someone who's like oh there's an XC you wear everything。

 whatever so like there are certainly lots of like security related comics from this guy and we try not to like go overboard showing you all of them you can go on and like read them if you're interested but this is one that's like so famous that I think we just have to it's like we're obligated to so if you haven't seen it before it the like the legendary like Bobby tables one so somehow the school is having trouble because this person name their son Robert like quote semicollon drop table students dash dash and apparently this persons gave his Bobby tables and so now when they enter this student's name into the server like everything gets messed up okay so that's the joke it's called like the Bobby Ts comic and I guess it resonates the fact that if the user puts in some really strange data it can cause the server to interpret that data as okay so yes schools。

Please sanitize your input or else you fall in for the Bobby table screen okay that's the comic it's like too famous not to show so there it is okay there's like other more exotic ones I assume the goal here is that if the cop like pulls you over I don't know I assume the intent here is that if the cop like pulls you over and tries to like enter your license plate and they enter this entire license plate and I guess you might get away so maybe we should also go like lead all my traffic tickets or something I don't know。

Is a speed trap maybe yeah so if I like drive past the speed trap and it tries to like OCR or like automatically read my plates it'll read this and maybe I'll go in and like delete my traffic tickets and like give extra traffic tickets to all my enemies or something I don't know okay。

That's SQL injection in real life。 Like I don't recommend it。 but I don't know。

 we'll try and see what happens。 Okay great that's SQL injection。

 That's the thing that makes it work is the fact that the user input is treated possibly as SQL。

 it really shouldn't be treated as SQL but if we plug it in and that we run the result in SQL query and the user input is valid SQL syntax it could also be executed okay so there is one problem in real life。

 which is that well， and this is something that people asked way back in the memory safety unit as well。

 And so they said， okay I believe you that like yes。

 if you input this special shell code or whatever you can cause shell code to execute So if you input the X in this particular way。

 okay you can get exploit to execute， I believe you but like how would you know that the stack is set up in this really specific way。

 or how do you know that the server is running this particular piece of C code and so in the first unit we kind of ask you to suspend your disbelief and assume that this can happen and here I'll give you maybe a more satisfactory。

😊，Answer for a similar injection attack and。Yeah you might say okay like I believe you if you insert some really strange stuff like this you can get the tables to get deleted but like how do you know that the query is actually getting executed like this。

 how do you know that there is a SQL query and furthermore。

 how do you know that the SQL query looks exactly like this so that I can construct my magic string so that my magic string combined with the table itself or the query itself results in some valid SQL syntax like how does the attacker know this string so one possible answer to say assume the attacker knows the system in the worst case if your code gets leaks on how you should still be defended against SQL injection attacks but maybe another more satisfactory answer is to say SQL injection is still possible even if you don't know what the underlying query is and so even if you don't know what the underlying query is you don't know exactly what SQL syntax is being used in the backend you don't know exactly what the format of the tables are you don't know exactly what the names of all the different columns are or how。

Rs are structured， you could still maybe do some sQL injection and if you do then you're doing something called blind sQL injection。

 so here you're still doing SQL injection， but you're given very little information about what the queries actually look like。

 right？And furthermore， you might not even get a response if your attack works or not。

 so for example， in I don't know， this attack from before。😡，Where we were like。

Executing this somehow like online store SQL query right if you make a bug somewhere in this query like somehow you constructing your expert incorrectly what would you get would the server be so nice to tell you like oh hi so you just tried to inject into my query and this is what the query looks like but you made a little mistake you forgot a quote so like if back and fix that no the server is not gonna tell you that right instead the server is not gonna like reveal to you what the query is and where you made your mistake the server is probably going say what're gonna say like error syntax error I don't know what you said try again right and so。

Sometimes you don't get feedback as to whether or not your exploit worked or even something like this if you successfully drop the items table is the server going to come to you and say like oh man you got me like my items table is all gone probably not right the server might just say like error or couldn't find item and so。

😡，In general， it's often the case that when you run SQL injection， you don't have a lot of feedback。

 you don't know what the query says because the server is not going to be so nice as to tell you。

 here's the query here's the blank， but something in there and the server is also not going be so nice to tell you that if your expert is incorrect like oh you just tried to attack me but you made a mistake please fix this so you can attack me properly like no server is not going to do that and if the attack exceeds the server is not going to say you got me the server is probably just going to error somehow and so blind SQL injection is the practice of still doing these injection attacks but without the knowledge of what the query is and without the knowledge of whether or not your expert is working you only get very limited information like error messages you might get those or like success messages you might get those but you're not going to get very specific information about what the injection was and you'll get to do some blind SQL injection in Project3 which is the last project of this class so we're gonna to give you a web server that's vulnerable we're not going to give you the source code so you don't get to know。

My internal table look like you don't know how does my table structure you don't know when you insert something and it doesn't work am I going tell you exactly what the query was Nope you have to take educated guesses and your educated guesses are going to help you run SQL injection even though you might not know exactly every last detail about what the injection is so there are lots of different examples of cases where you might not be able to get the responses so maybe like in the shopping car example from before if you inject something you might get a bunch of rows back but like think about something like password verification what signal do you get back if you try to sQL inject into a passwords database you might only get the answer of like password is correct password was incorrect that's it you get a true false value you don't get anything else you don't get like rows of passwords for your perusal you just get a true false value and somehow you have to leverage that in order to make your injection work so blind SQL injection is the practice of even if you don't have complete information about the system you still might be able to take educated guesses。

You might be able to take brute forest attacks， make guesses about what the column names are or what the table structure is。

And somehow use these little clues that people give to you in order to make the injection work it's like a bit more of an art science and there's no one true strategy as to how to do this but get some you'll get a chance to try it yourself on the third project and it turns out that in real life there are a lot of automatic tools that do this for you so there are automatic tools that try to like learn about what the internal SQL tables look like and like help you out and give you common approaches for how to do blind SQL injection so even if the attacker doesn't know your system does that stop SQL injection not really it just makes the attack a little bit harder for the attacker and arguably it doesn't even make the attack harder if these automated tools exist。

So that's hopefully a more satisfactory answer as to if the attacker doesn't see my system。

 how can they attack it well one we should assume they they're able to take see your system because of the security principle。

 but two， even if they cannot fully see your system。

 they can often take educated guesses or brute force and do what's called blind injection。

And that's still going to cause bad。O。Onwards so let's talk about the different ways in which we can defend against sQL injection So remember the defend against it we have to think about like what is the root cause yet So whose fault is this is it the server's fault or the client or the browser's fault and how do we defend against it what's the core vulnerability the core vulnerability the whole reason why SQL injection is a thing。

It's because we have these statements select something on something。Where is。

We have this big select statement or whatever followed by a blink and the user can put whatever they want into the blink and anything you put into the blank。

 the resulting string where some of the string was provided by the server and the rest of the string was supplied by the user this entire string is treated as SQL that is the key fls and the key flow is something on the server side the server is baking in the state because the server is taking this arbitrary string。

 plugging in the user input and then reading the entire string isQL that's the main problem so how do we stop this well long way to stop it it's kind of similar to XSS So if you really squint a little bit SQL injection and XSS are very close cousins and that in both cases we're taking user input as the server and we're not checking is the user input being treated as SQL when we return it when we run it or is the user input being treated as JavaScript and I serve it to another user who request it so。

One way we can stop that is we can check the user input more carefully and say actually you should not be able to enter this really specific screen that causes all my tables to be dropped。

 you can sanitize the input so only way to do that is to say hey you should not be inserting quotes because quotes are special characters I get interpreted differently in SQL syntax so don't enter quotes and don't notice any colons and don't enter any of the dash dash or any other special characters in SQL so as the server you could receive the input and say if this input involves like dashes and quotes I'm going to reject and say I'm not going run a SQL query。

 this input is too strange another option is to escape those characters so instead of saying oh you've got a dash dash I reject you could take the dash dash and replace it with escape versions of dash now the SQL interpreter is not going read the dash as a comment operator it's gonna to read the dash dash as a literal character dash and another literal character dash because I escape them or if I insert a quote the SQL interpreter is not。

read the quote as begin a new string or end a new string instead the SQL interpreter is going read it as like this is a literal quote character so I could also be careful with escaping and just like in XS we have to be really careful with escaping and there's lots of different ways to escape the escaper or to subvert the escaper and so it's really careful or's really difficult to think about what are all the special characters if I sit has in this very specific way can the attacker attack my sanitization code what are all the different edge cases so there are libraries out there to do this for you you don't have to write it yourself so maybe there's like some SQL escape function out there that does it for you。

Okay。That's our first defense， pretty similar to XSS and both these have the same underlying vulnerability。

 which is that user input is being treated like code in order to make user input not treated like code。

 the main fix or one of the main fixes is to sanitize the user input and make sure that the user input cannot be interpreted as code。

 either by rejecting user input that looks like code or by sanitizing and escaping all of those special code characters so that it doesn't actually get Red as code。

Okay。So that's one possible defense， but for SQL injection there's actually an even stronger defense and this one's called prepared statements or parameterized SQL and this one sorry it requires a little bit of knowledge as to how SQL the interpreters work and it's not something that we can cover in full detail in this class。

 but if you think about what the SQL interpreter does。

 one way you can think of it as well the SQL interpreter takes this statement， right？😊。

With the user input plugged in and it has to interpret it a SQL so at some level it needs to take this statement and like compile it into some lower language that it can use to run on the database like SQL interpreters。

 they don't just read English and then like oh， the English statement has to do this that's what I'll do somehow the SQL interpreter must be taking this English statement and compiling it down into more fundamental code like ones and zeros than an actual machine can execute and how does the interpreter do that beats me take 1 and6 to be sure but somehow the SQL interpreter is taking this English statement and translating it into a bunch of ones and zeros that machines can understand better So the idea behind the prepared statement is at some point you are going to have to take that blank that question mark and substitute in whatever the user intended to write。

If the very first thing that I do is take this question mark and replace it with what the user intends to write and then I pass this entire query to the SQL interpreter and the SQL interpreter starts to like break it down。

 turn it into ones and zeros and execute it， that anything that the user writes has an opportunity to be read by the SQL interpreter interpreted and converted down into ones and zeros as a SQL code that's a problem so the fix here。

Is at a database level or at a SQL interpreter level， what I can do is I can say， you know what？

That question mark， it's gonna represent something the user is gonna plug in。

 but actually I can actually start reading this query before the user plugs it input。

 so I'm gonna leave that question mark there， I'm gonna plug it in for later it's like a variable I'll plug it in later it's something that the user provides but I don't know what that is yet I can still start interpreting this query and say oh I have to go to the items table I need to pick out these two columns I need to do some filtering and I don't know what filtering I'm doing yet because the user hasn't provided me their input yet but maybe I can take this input and parse it into a bunch of ones and zeros first。

And then only once this input is completely interpreted and there is no more English to SQL translation needed。

 only at that point later down the line do I take the user input and plug it in so by the time the user input is plugged in I've already taken the step of taking this English and converting it to a lower level and so by the time the user plugs in their string。

 the user doesn't have a chance to have their string interpret it as SQL that's what the prepared statement says so it just changes the order in which I plug in the user input instead of plugging the user input first and I'm saying SQL interpreter。

 please read this entire statement as SQL I instead say SQL interpreter。

 please read this statement as SQL， even though there's a blank inside and then once you're satisfied with how the SQL should be interpreted then plug in the blank from the user so that by the time the user blank is plugged in。

 everything is already parsed and the user input will never get parsed as SQL syntax so even if your query has a bunch of quotes。

and dash dashes and special syntax statements， by the time your input is plugged in。

 all of the conversion of quotes and dashes and select statements into special keywords has already been done so by the time your input appears none of your input is going to be treated as SQL。

Okay。It's called prepare statements， sometimes it's called parameter SQL。What's good about it。

 what's bad about it Well， one thing that's bad about it is this is a defense at the SQL database level right so whoever is implemented SQL and there's lots of different SQL implementations out there。

 whatever implementation of SQL that you choose to use like whatever SQL software you are using you would have to make sure that the SQL standard or the SQL implementation that you use supports this weird prepared statement syntax because not all SQL。

 like there's no rule that says all SQL statements have to allow you to leave a blank so that I compile this entire statement with a blank and then fill in the blank later that's not standard SQL is not built into a regular SQL so you need to pick a SQL implementation that allows you to do this that says actually I understand how to take the statement with some blanks inside compile them down and then substitute in the blank later but not everyone knows how to do that it is not a requirement that all SQL implementations have to do this most SQL interpret。

These days I think do support prepared statements， but you have to pick the right libraries if you pick one that doesn't support prepared statements then you can't take advantage of this vertical or this feature okay so again this depends on whoever it is implementing SQL you need to pick someone that does support this。

And because this is so implementation specific， different implementations have different syntaxes for it。

 so that's why we didn't teach you a specific syntax because maybe here this particular SQL library that I've chosen to use uses a question mark as a placeholder but maybe some other implementation chooses to use some different syntax so now it's your job to look up the documentation for MySQL or Postgre SQL or like the Python SQL library or whatever and it's your job to look up exactly for your particular language and your particular SQL interpretation。

 what is the correct syntax for prepared statements because it's different for everyone so that's just how it is in the real world a human factor I guess you have to be careful and make sure that this defense while excellent you have to understand like how the different implementations actually allow you to use it that question last that item。

Like the par version of your Yeah it's a good question which is what happens if you take the parsed version of something and like pass it in here So I believe what happens is like by the time everything is parsed this thing is only being used as a raw string is no longer getting parsed at all it's just some placeholder string so by the time you're ready to put something in there the parsel has already done all of its job and is no longer going to interpret anything as code anything else that goes there is simply a raw string that gets compared against yeah it's a good pointm very thinking outside the box I like it okay so that's a downside is that it's not built into SQL but an upside of prepared statements which I don't know where it went but。

An upside of prepared statement is that this actually stops and I guess it's not， where did it go。

 I don't know， okay。But it turns out that prepare statements or parameterized SQL。

 it is actually one of the few defenses you'll see in this class that I would say is more or less 100% because if you implement this correctly and you use the right libraries there will never be a case where user input can be treated as code user input is locked in to be treated as raw data only it will never be par code so if you implement this defense properly you too can stop 100% of SQL injection attacks so this defense exists it is one of the rare defenses that we will see in this class that defend against 100% of attacks like most defenses are like oh it works but there's these like work around and it just makes the attackers life harder but not that much harder but this is one of those few defenses where I can confidently say if you implement this correctly 100% of SQL injection attacks gets stopped。

Which of course raises the question of why is this still number six if there's a 100% defense well human factors right so I guess not everyone knows about this attack or knows about its defenses or how to use them people might use the libraries incorrectly they might use older versions of SQL of like SQL and the SQL library so yeah it's 100% defense and it exists so please use it but I guess not everyone uses it so that's why it's a whole topic in this class that's why it's still number six on the leaderboard oh well。

Okay。Great so turns out SQL injection iss not specific to the SQL language you could have used any database language and gotten the same injection vulnerability so we can actually generalize this and we can generalize this a whole category of a text called command injection So what the heck is command injection so command injection is a fancy name of saying there are a lot of different cases where I take the user input。

 plug it into a piece of code and then run the code and if there's ever a case where I take the user input plug it into some piece of code like some string and then interpret that screen with the user input substituted as a line of code regardless of what language that code is in SQL C Python and that's something that we call command injection okay so command injection is just I have a string the string has a blank inside the user substitutes in whatever blank they want and then I read the entire blank as a piece of code and if the user input something that's like that looks like code it could be interpreted as code that's command injection thats a question。

I。🤧I guess the compiler a string that's a string Yeah。

 there's a question of can the compiler tell the difference between like a string and a piece of code Id say it depends on the compiler also depends on the setting right so maybe this example will illustrate I'm not sure because you're definitely right that not all cases of just user input are command injection cases。

 but here's a case that might be the case or where that might be the case so here I have a piece of like dash syntax so this is something that I want to go into my terminal I want to go into my terminal and run this command and I'm going to use that system function call to do it so I'm going to go into my terminal and I'm going to run this command where I want to like look through phonebook do Txt with a string that the user provides so I'm in my terminal and I have this string prepared and I'm going to substitute into users chose an input and then run this command with the user's input substituted。

In my terminal using the bash scripting language， which is what our terminals use。

 and then I'm going to take the result and then return it to the user or something okay。

And yet again， we have the same problem as before， which is that if I put in something like a name like weaver。

 that's the last name， then what we' this do， it will take this string， plug it into that command。

 and then run this command in my terminal。But if the user chooses something really weird like this。

 then again we plug this really weird string into my command wherever the blank was and this resulting thing have interpreted as bash。

 you don't have to know exactly what it says but it basically says read the passwords file and email it mal that would be bad so that's an example of command injection and notice that this is nothing to do with SQL so I don't need you to be a bash expert but the key takeaway here is that this has nothing to do with SQL and yet it is still another similar case where there's a string。

 the user input something into the string and the resulting string is parsed as input and if that' pars as code and if that ever is the case then you might find yourself vulnerable to command injection and the defenses are kind of the same as before so use input sanitization or use safe system libraries that stop you from doing this so as we saw from before there are safe system libraries like the parameter SQL library or the prepared statement。

Library in C， there are some different ways to be careful with like oh。

 instead of just substituting in the user string and then calling system on the whole string。

 which treats the entire string as a bash line， you could use one of these safer libraries which allows you to have passing command line arguments without parsing them as SQL or like as batchsh syntax and so that's something you can do in C Python go and so forth。

O。So instead of saying here's a blank， let's input the blank and then read the whole thing as a piece of code。

 we can instead say here's a command with the argument missing and plug in the user's input as the argument。

 but don't read this code that's what the exact B function would do in C okay great and if you're wondering about like human factors well a lot of older languages like C。

 they give you both the unsafe and the safe version。

 some more modern languages like go simply skip the unsafe version and just give you the safe one so there's no way for you to shoot yourself in the foot which is nice okay that's the end of SQL injection do you have any questions we probably in the last like nine minutes talking about caps。

Okay。Anything on chat， I guess I should have been checking， is not okay。

I guess final final thing I'll say about SQL injection before we move on forever is that those magical syntax or those magical queries So for example。

 I don't know， see if I can find one Okay maybe okay so these queries like how did I come up with this magic string how does the attacker or the user come up with this this is something that kind of comes with practice I'd say it's kind of hard to explain it in words but and if you go to like discussion or do some of the homeworks so I get some practice with this but it turns out these are not immediately obvious So for example here I have to be really careful with things like I need a quote here。

 why do I need a quote here because the name input it starts a quote so that everything afterwards is inside quotes so I have to add a second quote that like closes and matches the first quote right or for example here I need a semicolon to end the first select statement so I can start a gra new drop statement and also I know that at the very end of my input there's gonna to be another ending quote added by the SQL query itself。

Because it says name equals quote blank quote so that quote at the end。

 I don't want it to mess up my  query so I need to comment it out with this common syntax so。

Designing these queries can be a little bit tricky if you go to like discussion or you think about this in like homeworks。

 you'll get a chance query even even in the third project。

 you'll get a chance to practice with these queries and think about how to actually construct them。

 but it turns out getting those quotes exactly lined up they can be kind of tricky sometimes okay that was the last thing I wanted to say about the query itself。

 I think if you go back to last semester SQL or two semesters ago SQL lecture。

 we also talked about how to design SQL syntax queries in more detail。

 I do have some bonus slides at the very end if you want them but I'm gonna to talk about capture。

There are no objections。Okay， you've seen caps before。

 so I'll just tell you about them in like a security relevant context， okay so。

Most websites they're for humans， they're not for robots。 This is not always true。

 but it is generally true， for example， if I have a login page。

 was it for it's for humans to type in a password and see if their password is correct and login it is not for an attacker to brute force lots of different passwords that website is for humans to use not for attackers to automate a brutefor attack we'll even talk about cases later and when we talk about denial NA service in the last unit about how if robots visit websites they can possibly take my website down by overwhelming resources they could send spam they could like scalp tickets if that's a thing that we still care about I don't know so those are all different ways in which robots using websites can be a bad thing so what's the definition then of capchas so a Captcha is a challenge that is easy for humans to solve but hard for computers to solve so this is a way for us to tell computers and humans apart theres what it stands for I don't care if you know what it stands for but if you're curious it's there and so。

I is that I want this capturecha to help me determine if the person making a request is a human or a robot okay so how do I tell I give you a capcha and if I get a valid solution then the person making the request is probably a human and if the capturecha fails then the person making this request might be a robot so I don't allow the access okay there's lots of different examples of these maybe you've seen them before so like please read that text and type what it says and we assume it's hard for computers to do that or please select all the images that show cats and we assume the computers have a hard time doing these or please listen to this audio and tell me what it says we assume computers have a hard time doing that。

And so that's what capturechas are for turns out， and this is kind of a side note and not security relevant specifically。

 but like if you're ever wondering why like the Google capchas which are really common on the internet are so obsessed with asking about like traffic lights and stop signs and motorcycles like why does Google care so much about traffic well maybe it's because they want a lot of handlabeled data for their machine learning algorithms perhaps and so I don't know。

 I'm not accusing Google of anything here， but machine learning requires a lot of human labelbeled data and so one possibility of these capchas is there a way to cheaply get a lot of human answers to these queries so that they can use them for their machine learning data and like back in the date why were these like reading distorted text ones so common or maybe because back in the date they were really trying to use machine learning to learn how to like read images of text and the needy human examples for that too or they need human examples to label this training data and tell you like which of these are cats so they could plug those？

into their big machine learning algorithms， I'm not saying that's what happens。

 but it's a pretty common alternate use case for Capchas okay。

 so there's your Capcha if you select all the stop signs maybe like automated kernel stop okay。Yeah。

Okay what's wrong with CAtchas or like what are some modern issues with them well that's a problem nowadays which is that as neuralists have exploded and made AI like really really powerful。

 then capchas are now having a harder time separating out humans and robots because robots have gotten really smart and so。

That's a problem which is that as captures get as robots get smarter。

 catches have to be a lot harder to make the robots go away and only keep the humans and there's also a problem which is that as these capchas get harder。

 even humans that have a hard time solving them it's an interesting problem the robots are so smart that they simply might be able to outsmart us there's also a problem of ambiguity where the catchcha is simply so hard that like even the person serving the capturecha doesn't know the answer and so that one's pretty tricky sometimes they might just have to like take a majority vote and see what the humans are saying I hope that it's correct but that's a challenging problem I don't know the answer like I don't design catchs so that might be a problem and the final thing。

the final don't thing if I don't dive halfway through this lecture is that not all robots are bad so sometimes there are robots out there that do good things like they archive the internet for us and they take snapshots of websites in the past those might be cases where robots are doing good things but caps can't do that caps can't tell between a good robot who's helping archive the internet or like performing some service that's relevant or robots that are doing bad things like sending spam or bruteforcing passwords captors can only distinguish between humans and robots they can't distinguish between bad robots and good robots okay。

So yes， they've gone'm like incomprely hard and now they're like， oh， to prove you're a human。

 please solve this like derivative， okay。我问不清。Great。

 so what are the attacks on captures and this is kind of interesting this is where the security relevant aspect comes in。

 which is that。Sorry， okay， if you don't like the coffee on the recording。

 you can watch me say this when I was in sick a year ago， okay。

So what are some attacks on captchas well it turns out that captchas。

 they don't really stop attackers who have robots because if you're an attacker and you see this capturetcha in front of you。

 what are you going to do， you might just pay someone to solve the Capcha for you and so it turns out nowadays you know thanks to like global capitalism and like the inequalities in the world solving captchas is pretty cheap like a couple cents per captcha so you can simply outsource this ask someone else to solve the Capcha for you and so now you've really not distinguish between humans and robots but you've distinguished between humans and attackers who are willing for attackers can to spend like 10 cents per capcha and robots and attackers who are not willing to spend 10 cents per captcha okay。

So yeah， this is a possible attack。It's a security is economics attack so we raise the bar。

 we don't make it impossible for robots to attack us。

 but we make it expensive for robots to attack us because the robots have to be assisted by humans who are paid 10 cents to solve a bunch to capture us okay so yes there are services online that are super shady that help you selfcap us okay。

😡，So we're nearing the end you're gonna go I'm gonna go drink some water and before you go I'll give you a quick summary of SQL injection。

 which is the key problem was that there was this string。

 the user was able to substitute anything they wanted into the string and the resulting string was interpreted a SQL code so if you can come up with a carefully constructed string that causes the resulting overall string substitute it in with your code to execute SQL that does something malicious that's called SQL injection and it generalizes to command injection because SQL is not the only language in which this can happen we talked about the two defenses which were input sanitization just like an XSS and prepared statements where we。

Free compileile the statement down so that at the very end when the user string gets substituted in all the parsing is already done。

 we talked about how even if you don't have a perfect picture of what the query looks like。

 you can still do blindsQL injection you're just gonna have less feedback and you're going have to take educated guesses that took what the query looks like and finally I gave you like a 1 minute rundown of CAchas they are supposed to distinguish between humans and machines what do they actually do they actually train some machine learning algorithms and provide human label data and they also distinguish between humans and attackers who are willing to spend a little bit of money versus robots and attackers who are not willing to spend that money so doesn't stop attackers where user robots which makes their life a little bit more expensive and we talked about some of thes with catchs okay so at' 630 so I'm going to let you go and try not to get sick like I did and if you would like there are some bonus slides here on SQL injection that walk you through an old discussion question if you're curious but they are optional and they're just。

For your reference if you like， okay， and if you want a video on these video slides go back to like a year ago fallal 22。

 I talked about these a year ago， okay， but there's no way I could talk about it this time without like coughing your ears to death okay see you next time。



![](img/1993cff87a35f6dd2f2eff4cf6cdfeb8_2.png)
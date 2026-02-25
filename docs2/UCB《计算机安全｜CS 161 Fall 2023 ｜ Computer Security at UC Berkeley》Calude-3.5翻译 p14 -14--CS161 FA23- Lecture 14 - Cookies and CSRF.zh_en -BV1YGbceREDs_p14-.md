# UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p14 -14--CS161 FA23- Lecture 14 - Cookies and CSRF.zh_en -BV1YGbceREDs_p14-

Okay。

![](img/3d6d31b1db9e129f95909bb119cc6a8e_1.png)

Okay hi everyone， so we're going to continue our exploration of We and hopefully I'm not so sick that I like become unintelligible halfway through okay。

So last time we gave you a quick whirlwind tour of web， I'm not going to。咁啊。Okay。

 everyone can see this。As you can tell， I'm sick， I forget anything left and right， okay。

So last time we told you about different parts of the web， so we talked about the URL。

 how it breaks that into different paths， like different parts， the protocol path， location。

 the domain。Now we talked about how when you get served the webp page you get the way that the webp page looks nice is that you're provided with HTML which is a language that lets you do things like bold textex。

 Telet and so forth， and then links forms the images the CSS makes the website look nice so it lets you define styles like what colors you want to use or font you want to use and then JavaScript is browser side code right key part of JavaScript is that it is not the server executing JavaScript in most cases the server sends the JavaScript over and then it is the browser's job to execute the JavaScript on your computer so when you're playing that little game in your browser or something very likely the JavaScript is executing on your computer and it was sent to you by someone who you might not know or recognized okay。

And finally， we talked about different threats on the internet and the main way that we thought about was how do we protect two websites that are unrelated from accessing each other's resources。

 like if I am attacker。com， how am I going to stop。Attackcker。com from accessing resources on sayBa。

com or some legitimate website and so the browser enforces a rule which is that if two websites have different origins。

 they cannot read data from each other， send data to each other and the way that we defined origins we just did plain old string matching on protocol domainat import and that's the best we can do because sameor policy it was not designed when the web first came about is something we added on at the very okay。

So that's all from the last time， so this time we're finally going to start okay one more so last time we talked about HtTP that was instead set of rules that we used to send messages back and forth。

 we talked about how it is one request to one response always one to one and how the request and the responses have to be formatted in a very specific way so that both sides understand the semantics of all the ones and zeros that get sent over the channel okay。

So yeah finally we can talk about a tax for today so we're going to spend the first half talking about a critical feature that keeps the web running so the first app is not going to be necessarily attached tax we're just going to talk about what are cookies。

 why are they necessary to keep the web running and then we'll talk about session authentication which is going to look really similar to cookies but it's really a specific application of cookies so you can use cookies for all sorts of things session authentication is a very common one。

And then finally we'll talk about a attack that you can do on cookies called CSRF and then we'll talk about defenses。

 so that's our plan for today we'll talk about cookies and then we'll talk about an attack we can do on them okay。

So first， I'll tell you all about cookies。One thing you might have noticed with this HTTP protocol is that it's one request for every response so you can almost think of it as like every request and response is independent of each other so if I send a request I have no idea what the contents of the previous requests were and I have no idea what the content of the future requests are so you can think of it as every single request to the surfer is processed independently of all the others and so maybe this is okay maybe viggilanna fetch a PDF it doesn't matter if you fetch it now or fetch it 10 days from now maybe the request in the response is independent after all but。

Maybe that's not what you want on your website， so here's some examples of。

Places where if I enable some setting or I want the HtTP response to be different depending on what the past HtTP request and response said。

 so for example， if I go to a website like I go to our course website ES161。

org and I turn on dark mode。Well I would like it so that if I send any future HTTP request to the server。

 I want to give my websites that a nice and dark black background right where if I turn off dark mode that I want all my future requests to have light mode enabled so somehow I have to remember this state across different requests so it's no longer the case that every single request and responses independent because if I choose to enable dark mode I want all my future requests to come back with that beautiful black background in white text。

Or another example is if I type in my username and password to log into the bank website。

 I would like all my future HTTP requests and responses to know that I am the one I'm the user making those requests I don't want to have to log in again and again every single time it's just kind of annoying so I want my requests to remember something from the past namely like I login information or whether I selected dark mode or light mode like I want some of those things to be remembered。

😡，So the way that we're going to unlock that HttP by itself can't do that HttP treats every request and response separately。

 so the way that we're going to unlock the ability to link together HtTP request and responses is something called cookies and so。

😡，It's a fancy way of saying a piece of data that's going to be maintained across multiple requests。

 So here's how you might use it。 So one way that you might get a new cookie creative。

 So I guess the first question is where do these cookies come from So one way that you can create a cookie is the server can send one back to you So when you send a request to the server the server has to send back exactly one response and that response might say something like here's the response in HTML or whatever And by the way。

 here's an extra cookie that you should store and keep track of So the server can create a brand new cookie and send it to you and the HtP protocol specifies where the cookie would be said so that both sides understand okay this is a brand new cookie that the server has created out of nowhere and is providing to the browser。

There are also other ways to do it so if you run JavaScript JavaScript could create a brand new cookie sometimes depending on the settings of the cookie you can also go into your browsers settings and create your own cookies like that's probably pretty unusual for most people using the web but if you really wanted to or you wanted to execute some attack you could certainly go into your browser and create all the cookies that you possibly want so that's totally okay。

In general， cookies are stored on the web browser so just like how JavaScript is totally browser site is the browser executing all the code cookies are totally stored by the browser so the server。

 yeah the server might keep some information about the cookie but usually we assume that this browser is the one responsible for keeping all the cookies so if the server creates a brand new cookie sends it into HTTP response and says here's a new cookie for you the browser is responsible for keeping track of it and something called a cookie jar which kind of makes sense or if some piece of JavaScript creates a brand new cookie we would like it so that the browser keeps track of that newly create a cookie also in the cookie jar okay。

So well， what good are these things after you create them and restore them。

 well the nice thing about them is that now anytime you make a request like an HtTP request from your。

😡，Okay， we're all the way back， okay。I think we're back okay， so before I really interrupted。

 I was telling you about how cookies are automatically sent by the browser so the browser digs through the cookie jar finds all the relevant cookies and it attaches them and sends them as part of the HTP request。

Sorry， I'm sick and the Wi is broken， okay， bad thing， okay。

So now let's peek inside a cookie and see what exactly is the data and how do we store it So just like how HtTP had all those rules about like you gotta check getter set for every single getter post for every single request and your responses have to have an error code inside the cookie also has some semantics that tell me when I build a new cookie this is how I organize so I'm not just writing like an essay'm not the data inside for cookie I need to format it in this very specific format so this way whenever cookies get sent back and forth everyone knows exactly what I'm talking about them so these are all the fields that you have to know there are other ones out there you can set some of them are optional some of them are mandatory but these are the ones that you have to know for this class for the attacks that we're gonna see so the first thing that we're gonna see is that the actual data of the cookie is stored in a name value pair so think like Python dictionary or think a hash mapap if you're more familiar with like Java or data structures So think about mappings of names to values so in this cookie the actual data that is being stored like what's the information。

あ。The website that's being stored， the name is theme and the value is dark。

 so maybe I wanted to keep track if someone shows dark theme or light theme。

 I could make a new cookie with the name theme and then map that name to the value of dark。😡。

Or you can do something else iss up to you right but this is what at least we've chosen on this example as the data of the cookie and these can just be any arbitrary strings there are some restrictions of special characters you can't use that you'll encounter on your projects。

 but for the most part strings okay。Then we need to say something about what websites is this cookie associated with because if I just say theme equals dark。

 does that refer to like every website in the world does it just refer to the 161 class website。

 does it refer to you on Google and Dark mode too like who does this cookie belong to or who is it relevant for So the way that we're going to do that is we're going write a domain for the cookie and a path with the cookie and these might look kind of familiar they look kind of similar to the domain and the path of a URL but ultimately these are I guess they kind of do look similar right but their fields of the cookie so when you build a new cookie you need to fill in a new domain of your own and you need to fill in a new path of URL and you can choose the values that you put here and these values somehow scope the cookie and tell me about which websites is this cookie relevant to and which websites is this cookie not relevant to and it should remind you a little bit of URLs although it is not an actual URL when you put these together like you're not a real URL it is just telling me that this is relevant to this。

I made him this path。Okay。And we'll see later rules for how you might be able to send this or what you might be able to set them two okay then there's two security fields that we care about so I'll go through them one by one so one of them is called the secure attribute and it's kind of I don't know not the greatest name but basically the idea is if the secure attribute is true then this cookie will only be sent if the request is made over HtTPS so do you remember how there were a lot of different protocols。

 the ones that we care about are HtTP and HtTPS the secure version so if you set the secure attribute to true as the browser digs through and looks for all the relevant cookies。

 the browser is going to say okay this cookie is tagged secure so I'm only going to send it if the request in question is an HtTPS request encryptto with cryptography over the network somehow and if it is HtTP I will refuse to send this cookie。

And there's another attribute for security， which again。

 I don't really like the name it's a little bit confusing。

 but it's called I didn't invent it so I can't name it so it's called HtTP only and this attribute says if you said it equal to true。

 then JavaScriptscript does not allow allowed to see this cookie so we know the JavaScript runs in the browser and since JavaScript runs in the browser it can look through the browser for stuff like hey。

 what are all the cookies being stored which cookies do I have which cookies do I not have can I create some new ones。

 but the browser will add an extra rule which is that if the HtTP only is set to true then we're not going to allow JavaScript to see this cookie so JavaScript when it asks the browser hey what are all the cookies in the jar the browser will not return a cookie or HttP only is true because we're not allowing JavaScriptscript to read it or modify it。

So yeah， I don't really like the name HttP only， but remember what is it actually about it's not about like HtTP versus HttPS。

 it's specifically about whether JavaScript allows you to access the cookie。Okay。

So those are the fields again you said either true or false and then there's an expiration field which is kind of what you'd expect which is as soon as that date arrives。

 this cookie is expired and you can no longer eat it or send it to the websites or whatever so there's a timestamp tells me when the cookie expires and again there's more fields but those are the ones that you have to know for this class okay。

Questions。I should probably blow my nose Zoom as't 60 and be lectured two and everyone's like。

I don't know， everyone was amused by， okay， here go。Okay。I hope you enjoyed okay。And系m大讲 ok。

So let's talk about rules for setting and sending cookies so this is definitely going to get a little bit into the weeds of rules and like trivia。

 but still it's important to know as we design attacks text about cookies so first we should remember that。

😡，Who is allowed to create new cookies Well the server can create a new cookie fill it in with as of now whatever they want and then send it to you and then the browser is going automatically attach any relevant cookies and we haven't formally defined what it means for a cookie to be relevant and we also haven't formally defined rules for what kind of cookies you can set and we're going to see you now why we would need those rules in the first place So for example。

It would be kind of annoying if say like I made a request to evil。com and then evil。

com sent me back like， hey， here's a brand new cookie for you。

 please store it and that cookie is marked as relevant for like CS161。 Darkmouth。

So somehow I've talked to evil。com and they've sent me a cookie that forces my CSm61 website to be dark mood like that's kind of weird right I don't want websites to send me cookies that get。

used on unrelated websites so somehow that feels like a risk it feels like somehow I'm subverting the same origin policy and allowing two websites to communicate when they shouldn't be able to so we're gonna have to add rules to prevent this case because anybody can set a cookie but I don't want the evil。

com website to send me back a cookie that ends up affecting future request to CS161。

org because if they send me a cookie and it says like theme equals dark cs161。

org in the future anytime I make a request to CS161。

org I might end up sending this evil cookie and suddenly my website's in dark building I'm like what the heck is going on so。

I don't like this it's a security risk we have to take care of it and a second problem is that cookies can often contain sensitive information as we're about to see so。

Suppposed a cookie contains some like top secret information well it would be really bad if you know I had a cookie with top secret information about my bank account login or something really sensitive like I don't know password to like the exam solutions and when I made a request to evil。

com it would be pretty bad if my browser presented to take that cookie attach it and send it evil。

com again it feels like somehow i'm breaking the same origin policy and allowing two web to communicate when they shouldn't so somehow I need to prevent cookies being sent to the wrong places because the browsers automatically attaching relevant cookies I need to define this word relevant in a way that。

Cookies don't get sent to the wrong place I have a cookie that has a secret from my bank account it should really only be sent and attached to my bank account requests not to any other requests and also if evil。

com sends me a cookie they should not be able to send me a cookie that affects other websites they should only be able to send me your cookies that affect their own website evil。

com the website setting the cookie okay。So now we have to come up with rules to do all this and it's called cookie policy and just like the same origin policy these are enforced by the browser and why does it make sense for the browser to enforce these because where are the cookies stored they're stored into the browser so when the browser gets a new cookie and someone says hey here's a new cookie for you please throw it in the jar the browsers gonna to check is this cookie okay or is it disallowed and I shouldn't accept it and likewise when the browser is automatically attaching cookies in every single request it's the browser stopped to check is this cookie relevant to the request being made or is this cookie totally unrelated and I probably shouldn't sent it so the browsers the one who has to decide all of this stuff。

And one thing I'll notice that the rules that you're about to see。

 these are specific to cookies and how they get set。

 they are not the same thing as the same origin policy。

 even though both of them serve kind of the same purpose。

 which is to stop websites that are unrelated from interacting or affecting each other。

 but this one is specifically a set of rules on cookies and same origin policy specifically a set of rules on like HTML。

Okay。So before I can tell you about all the cookie rules。

 we need to take all these domains and somehow organize them because if I have a bunch of domains like I don't know I have Berkeleyedduucs161 or Google co I would like to be able to organize them in some sort of way so that I can define very specifically what does it mean for domains to be related what does it mean for a domain to be more specific less specific so the way that I'm gonna to do it is kind of what you'd expect。

 which is you look for all the dots in the domain and you split the domain on all the dots and you create a kind of natural looking tree like this like honestly I don't know how to explain this without just showing it to you so it seems pretty natural to say berkeley。

edu and mitedu they both belong to the family ofedduu domains seems pretty natural and you know piazza co not that we use piazza anymore but remember when we did and Google co those seem to belong to the family of co and every single domain belongs to。

Family root so that's the set of all possible domains so we'll see this again also in a lot more detail when we talk about DNS but for now you can think of the domains as somehow forming a tree and this tree can allow me to specify things like which domains are more specific which domains are less specific which domains belong to a family which domains don't so that's why the hierarchy exists and so we can use this to start building up all of our cookies okay。

ACouple more just like vocabulary terms that you'll see now and then sometimes when the domain is directly below root。

 so it's got a single dot followed by something at the very end。

 sometimes people call that a topleve domain so anything the whole family ofedu that's theedduu top levelvel domain or the family of all domains ending the docom all the servers whose name's ending docom that's the docom tlD there's one for I don't know co。

 UK for all the British ones I don't know lots of different ones。

And sometimes we' use the word subdomain to say when something is more specific， so etopberrkeley。

edu， it seems pretty natural to hang it underneath Berly。edu in the screen。

 so we can say something like etopberkeley。edu is a subdomain。So just vocabulary on this slide。

 nothing like super fancy。Okay。So finally we can get to the rules so first thing to remember when you see these rules is like what are they even good for like the browsers the one checking them we should remember that and we should also remember the reason why these rules exist is to stop those attacks from earlier so if the evil。

com website sends me a cookie I need to decide do I accept this cookie and add it to my cookie jar or do I deny this cookie and throw it in the trash and the reason why this matters is because I don't want evil。

com to send me a cookie that can affect other website。😡，I don't want evil。

com to send me a cookie that like changes my bank login or I don't know。

 changes my one things to do one to dark。So somehow might have to come up with some rules and so。

This is kind of an annoying way of writing it， but all of these mean the same thing。

 so I'll first say it in like。Wors I guess and then i'll show some examples。

 which might be more helpful So one way of saying is that there are two domains that need to be compared here so remember when you get a brand new cookie it's got a domain inside like do you remember when we went Ta showed what was this。

The parts of a cookie domain right there right so there's a domain inside the cookie that's one of the values that we have to compare and the second value that we have to compare and that was this。

 the value in red that's the domain inside the cookie but there's actually a second domain that we care about which is the domain of the website sending me the response So if I send an http request to say like www。

gocom when I receive a response who is the response coming from it's coming from www。gogle co。

So these two values， even though they are bought both called domains， the one in blue。

 that refers to who is sending me the response in the first place。

 and domain attribute Y refers to what did that person fill in when they created a brandenn new cookie with a domain？

😡，So what I have to do to determine whether I accept this cookie or not is I have to check these two values and I accept the cookie if and again the wording is kind of funky。

 but one way of saying it formally is that the domain attribute。

 this is the thing inside the cookie that the server wrote down is a domain s of the server's domain。

 which is the website sending the cookie back to。😡。

So a couple ways of saying this in maybe more pallatable terms are you could say that value in blue。

 which is the server sending like the identity of the server sending me the response that string has to end in y the domain atrophy another way of saying it is that the domain has to be below or equal to has to be more specific than y or you could say x is more specific or equal to y all of those actually are exactly the same and if those still sound confusing honestly you're not alone I think examples make this a lot clear so here's an example。

I sent an http request to mail。go。com This is the value in blue Why is it in blue Because this is the person I'm talking to I made an http request to mail。

google。com and they're sending a response back to me so this is the domain of the website sending the response back to me and when they sent a response back to me they could invent a brandnew cookie you know like they baked a brand new cookie and it's got a domain value and a path value and the server mail。

googlecom decided to write in Googlecom for the domain field they chose this value it's baked inside the cookie and so I'm going to label that red this is not who I'm talking to I'm talking to mail。

googlecom but when they cooked up that brand new cookie they decided to write Google co as the domain field。

So I check and I can check there's all sorts of different ways I could check。

 Does mail do go do com end in Google do com。 but sure does。 mail go com ends in Google do com。

 So that's okay。 We accept this cookie。 We could also say is mail Google do com gonna be below Google com if I drew the hierarchy tree。

 It would in the same way that etopbrokeleyedduu was underneath Brkeley do Edu。

 mail do go do co will also be below Google。So I accept this cookie we could also say mail。google。

com is more specific than Googleogle。com also a way to accept this cookie so in other words。

 if I receive a cookie and the value has domain go。

com I will only accept if the person setting the cookie is Google。

com or someone below or more specific than Google。com。😊，Okay。And as another example， if mail。google。

com or if I made a request to say like evil。com so now the blue value is evil。

com and they sent me back something with domaingoo。com now evil。com is not more specific than Google。

com they're not below each other on the hierarchy or one's not below the other on the hierarchy so I don't accept if evil。

com for to set a cookie thats scope to Google。com I don't accept right this stops unrelated cookies from being accepted if they come from someone unrelated okay。

And just like we said from before， if you make a request to Google。

com and you get an answer from or you get a cookie withd Google。com also accepted because Google。

com it ends in Googleo。com yes is Google。com below or equal to Google。

com of the hierarchy yeah they're the same thing on the hierarchy is it more specific or equal to Google。

com yes， so ultimately once you get the hang of it。

 it is a little bit mechanical but the important thing of why it's set up the way that it is is because I don't want evil。

com to be able to set a cookie that messes with bank。com or messes with CS161。

 org that's the reason why this whole policy exists。

But ultimately the policy is a little bit like trivia。

 you just kind of write it down somewhere and keep track of it， okay？

A couple more just side notes and I know we're getting into the weeds of these policies a little bit so one thing you cannot do is you cannot have the domain attribute be a top levelvel domain so for example you would not be allowed to set domain equals co and if you think about again the reason for doing all this it feels pretty reasonable that I don't want to set a cookie for domain co because if I set a cookie for domaincom I'm saying like this cookie is relevant to every single docom in the world and it's like。

Well， that's kind of weird How is evil dot com able to set a cookie that's relevant for all the dot coms in the world like evil dot com should not be able to speak for all the dot coms in the world and Google do com should not be able to speak for all the dot coms in the world so somehow。

This dotcom domain if I fill in my cookie feels and I write docom is the domain then I'm somehow claiming to speak for all the docoms and that's just too general so we added another extra little side rule that says if the domain attribute is a do co you can just stop right there and say no I don't accept because do co it was too general I don't want to set cookies that affect everybody in the do co subte or I don't want to say a cookie that affects everyone in theorg subte it's way too general and opens up to many attacks so we add this extra rule which is that the domain attribute the thing you fill in the cookie it better not be a docom or a org or one of these toplevel domains。

Okay。A final little ni that I have to mention is that we actually don't check the path for setting cookies so you can set any path you like。

That's just the rule okay。Maybe it'll make more sense once we see the policy for sending cookies。

 but it turns out when you're setting cookies you just check the domains against each other and the server sending you the cookie。

 they have to fill in a value for the path and when the cookie had all those fields the server had to fill in something for the path turns out they could but whatever the heck they want for any string goes the browsers not going check that and reject。

Yes， I know it's a little bit tedious， but that's the policy and the important thing to remember is like why the policy is the way that it is right the goal is to prevent。

Someone like evill。com for setting a cookie from setting a cookie that would affect other websites as well。

There's a question of where are the cookies stored。

 they're stored in the browser right so the browser is the one responsible for keeping track of all the cookies because it's the one collecting all the cookies from websites and then attaching all the relevant ones as they get some。

Yeah， great question， anything else？Do we have to satisfy the three conditions？有。Yeah， so。

Okay so the question was these three conditions do I have to satisfy all of them。

 they're all equivalent so these are just three different ways of writing the exact same condition。

 so if you satisfy one you satisfy。Yeah， great question， okay。

So that's setting cookies so I have to go through the other half of cookie policy and again I know it can be a little bit boring at this point and we're really getting into the weeds of this stuff but remember like the big pictures that I want to be able to attach cookies that are relevant so when I make a request to Google co I'm gonna dig through all my cookies I might have a cookies saying like CS161。

g dark I might have a cookie saying here's your bank co login and I might have a cookie saying evilcom something so somehow the browser needs to be able to dig through the entire cookies chart and extract all the cookies that are relevant to the Google request that I am about to make and then automatically attach those in the HttP request that I fire off the wwwgo co。

So how do I determine whether a cookie is relevant or not that word relevant was just too big like what does it actually mean So here's where we're finally going to define what it means for a cookie to be relevant so again。

There's two domains and there's two paths and I feel like it's kind of confusing at first oh well how there two domains to remember the thing in red。

 these are the values inside the cookie when I create a brand new cookie I have to fill in all those feels I got to fill out the whole form and two of the feels that I have to fill out are the domain in the path So that thing in red that's the thing I fill inside the cookie and then this stuff in blue these are the domain in the path of the person I'm talking to just like before so when I make a brand new request in http to www。

google。com then the domain in the path are www。gogle。com okay。

And the domain and the path attribute those are buried inside whatever cookies I'm taking through so this is what it looks like in words and again you can think of it as the domain attribute has to be a suffix has to be more specific than the server's domain the path attribute has to be a prefix has to be less specific than the server's path but like I look at these and honestly I'm not a huge fan of this so here's my little trick for doing sending cookie comparisons it does not have to be your trick and you really like thinking about suffixes and prefixes you totally can but here's what I do so。

I write the two values side by side and I guess the colors are a little bit funky but this thing on the top。

 this is the person I'm talking to I made a brand new HtTP request to this thing of top so that corresponds to these values the ones in blue so that's the person I'm talking to I make a brand new HtTP request to this URL。

And now this browser needs to go through every cookie one by one and design are you relevant should I send you or should I not send you so consider a cookie whose domain is this and whose value is this or path is this like where do these values come from they're inside the cookie they're baked inside the cookie when I make a brand new cookie these two values are baked inside。

😡，So what I can do is I can just line them up really carefully like this so I can take my cookie domain。

 my cookie path and then put them together and。Line them up at the right place so like wherever that single slash is after the first domain I line them right up and then all I have to do to check is I check the domain starting at the slash and going backwards and it seems like I found a total match the 161。

org matches tune。161。org and I go to the right and I check does that match that yes the paths match all the way to the end of the cookie right？

And so if I started thislash and I moved to the left and I moved to the right and everything matches with the cookie domain in the cookie path against the URL that I'm sending to that I consider this cookie relevant whatever name and value pair is associated with this particular cookie I will attach this cookie and send it to this URL however if I get something like this where the path just doesn't match then I check to the left is okay。

 but I check to the right and I see a mismatch and I don't send this cookie so this is just exactly the same as the definitions from before where like this word is simply not a prefix of this word that's okay or you can just put them side by side and do a comparison again it's kind of mechanical but the important thing is I care about cookies that are relevant and this is how we're defining a cookie that's relevant。

Okay。So those are the policies we talked about setting cookie policies。

 those tell me when I get a brand new cookie do I accept or do I reject and I need to make sure I only accept cookies that are I only accept cookies so that I avoid that are relevant so I avoid the attacks like evil。

com sends me a cookie that's relevant for like bank。

com that would be bad and when I send cookies I use this rule to check whether or not the cookies is relevant it is relevant I send it is not relevant like goat send。

I think again， I know it's not the most interesting thing in the world。

 but it's important to remember what these policies are and be able to like check because when we start doing a tax。

 it's important to know which cookies are relevant and which ones are。

Okay great so hopefully some more interesting stuff coming up this one is kind of interesting unfortunately is's just a of a lot of slides and a lot of words。

 but if you're interested it's here I think we all have a video from past talking about it it's called the Spec attack and this is one of those attacks where the people writing the operating system messed up so when the people writing the operating system messed up a lot of bad things happen and we actually want you through the details it's actually something you know how to do given your knowledge of memory safety and how the browser was memory unsafe and also now giving your knowledge of cookies but I'm not going say it all right now but it is pretty cool so。

😊，There if you want it， it is very long and complicated， but if you're interested。

 know check out the video on it from the past semester of okay but I guess one thing I'll note about the legacy of this attack is like if you ever wonder why your browser eats up so much memory it because of this attack we have to somehow keep all the tab separate and to do that we have to run different processes for every tab and that's what makes web browser so like memory consuming your intensive okay so now you know there's this vector attack。

It's not something we would test you on， but turns out just given all the first principles you know now about cookie policy and about memory safety vulnerabilities。

 you can reconstruct this， which I think is really cool okay unfortunately we won't because I don't have time but pretty cool okay。

Anything else you want to know about cookies before I tell you about an application of them？

We talked about what they are， the policies of when you set them， the policies of when you send them。

 and now we can finally talk about the rules or not the rules but like the applications of what cookies are good for。

Okay so we already saw a couple of lossess like one of them was the dark mode thing so somehow when I send a request to the server and I say I would like dark mode from now on。

 the server can reply to me with the cookie and saying sure you want dark mode from now on keep this cookie in your pocket and every single time you make a request please attach that cookie and I will remember to send you the dark mode website every single time you ask so that way I've made my HTP request and responses not independent they can now rely on each other which is pretty cool。

So that's one possible use of cookies but another one that's really common and security sensitive is staying logged in so for example。

 if I walk up to you know Gmail and I log in a single time well that loin is a single HTTP request and my response might be like the list of all my unread emails well that's great but later if I make another request how does Google still know that I'm logged in like it doesn't know right and so without the power of cookies every single one of these requests would be independent and I would not be able to stay logged in as a user if I wanted to say like check my email all day long so。

That's why we need the power of cookies to help us unlock something called the session and what's the session it's a fancy way of saying when I log in。

 I usually stay logged in for a certain amount of time and how is it even possible to stay logged in like how does the server know all those future requests are coming from you that's because there's some cookie being said that reminds the server oh hey。

 here's the person who's currently logged in making all the requests okay。

So if it were not for cookies and session authentication， how would you deal with the internet。

 you would have to type in your username and password literally every time you open your email client every single HtTP request would have to have the username and the password attach because they're all independent they cannot rely on each other and then every response would be separate so kind of annoying like I don't want to have to type in my username and password every single time I want to check my email so instead。

😡，I want to be able to associate a bunch of requests and responses with the same logged in user so I log in a single time。

 provide my username and password and then for like the next 15 minutes or one hour or one day。

 all the requests with the same somehow like cookie attached or somehow the same something and we'll have to figure out what that something is are associated with the same logged in user。

So how do we unlock this， we unlock this using cookies， so this is an application of cookies。

 that' not the only thing。It's not the only thing you can use cookies for you can also use cookies for dark mode or something else。

 but this is a very common security sensitive application of cookies， okay？😡，啊，走。

Anything else you want to know about this stuff？Pd to like stay alive up here？啊， ok 啊。

Okay don't come up here later else you're going to like get germs all for yourself Okay so here's the intuition for maybe what session authentication is going to look like and so。

Maybe it helps maybe it dozen't， but it something we thought of so I don't know if anyone's ever been to concerts before or still goes but if you ever go to a concert maybe what's happened is like the first time you walk in like you're waiting in line and you go in and the security guard asks for your ticket and ask for your ID so you present here's my ID here's my ticket they scan the ticket scan the ID check that you are who you say you are and then has anyone ever gone like a wristband they give you a wristband on your way in right and so what is the point of the wristband well the point of the wristband is say you forgot something you're like shoot left something in the car So what would you do you would leave the venue wherever the concerts taking place and if you want to come back in later do you have to wait in line and show your ID all over again well no you just show the wristband and tell them you've already checked me here's the wristband and then they let you back in。

So somehow this is what we want， because if all of the incoming people into the concert were I treat it independently。

 when I leave and re-enter， I would have to present my ticket over and over and over and over again。

 the security would have to check my identity over and over and over again。

But instead if I walk in a single time， I get a wristband the wristband basically says yes。

 this person is already authenticated so the next time they walk in you don't have to go through that costly check of like here's my ticket here's my idea again you just show them the wristband is automatically attached and then they let you write it so this analogy like it works for the most part I guess the one place where it breaks is that the wristband would have to be unique for every single person when we talking about session authentication because everyone's logged in separately but like modlo that one little nitpick this I think is a pretty natural analogy for session authentication okay。

So what does this thing look like in actual cookies so the thing that I want is I want that wristband but I want it in cookie terms or I want it in session terms I don't want like you know physical wristband so how do I take this idea of a wristband and turn it into something that I can actually implement so i'm going to implement it。

😡，Using a value called the session token and this is a very fancy way of saying this is a random long secret value that is associated with the currently logged in user So if I am logged in right now。

 I have a session token it's a long random string that identifies who I am and the fact that I'm currently logged in This is the wristband sitting in your browser So how do you get one of these wristbands while I have to wait in line show my ticket and ID and get a brand new wristband so in that same vein the first time I log into the website I present my ticket my username。

 my I and my password， they check if I am who I say I am and if they're satisfied then they provide me with a wristband so how does the server provide me with a wristband they send me the brand new session program that I've just created。

😊，Now I have a wristband on me so in the future， if I ever want to make another request like I want to check my email again or I want to go back into the concert I don't have to wait in line and show my username and password all over again。

 I don't have to type my username and password again and again and again instead I can just take that wristband the session token that I've already received attach it to my request and say hey remember this value that you gave to me earlier remember this wristband I still have it so you know who I am it's me and so the server looks at that value and says oh yeah that's you and so they accept that response as being from you and you no longer have to enter your username and password which is really nice。

So that's the wristband as it would be implemented in code it's this random value。

 you receive it the first time you log in and in the future you send it to the server every single time so who has to remember the session token well we have to remember it the person using the website we have to keep it in our browsers because in the future if I ever want to check my email I need to resend that session token over and over and over again and also this time the server also has to remember that session token so it might have some sort of a database that says like this user is currently being issued this token this user is being issued this token so that way when I send that token over and say hey it's me remember me the server can look in their database and say oh yeah I remember you I gave you this token 10 minutes ago that's who you are so I'm going to associate this request as being from you。

Okay。So this idea of session tokens is really great。

 but as at this point it really tempting me to think session tokens or cookies are they the same thing are they related somehow they are and the way that they're related is that the session token is just some high level idea it's like。

This wristband idea I didn't say anything about cookies on this slide is just some arbitrary idea you can implement it however you want。

 but it turns out the most natural way to implement it is to use cookies so session tokens are the idea cookies are how I implement them and as we said from before this is not the only use of cookies you want to go use dark mode go use cookies you want to go I don't know。

Whatever you want right I can't think of any right now but there are all sorts of different ways to use cookies that do not involve session tokens。

 but session tokens are one common application of cookies they're a highlel idea that I'm going to implement using cookies so I'm going to rewrite the same steps from before but this time I'm going use cookies to actually store that value and we'll see it's actually pretty natural so first time I log in I send my username and my password like I always do security guard checks my ID yes you are who you say you are and this time instead of just sending you the session token they're going to send you a new cookie and the cookies is going have the session token inside。

And just like before the server is going to keep a map saying this new value that I generated is associated with this current person logged in right now。

And in the future， if I ever make a request well， the nice thing about cookies is they're automatically attached。

 I don't have to manually dig through and find the right session token if I set the session token up correctly。

 the browser will just automatically attach the session token every single time and make a request to the same website and then the server can check the token and say。

 oh yeah I remember this token I know who you are and so they can send you data that's customized to your loggedin session so if I send a token or I send request and the cookie has my token attached automatically the server knowss from me they will serve me my unread email but you might have a different session token and if you ask for your unread email youll send your session token the server will check that and say oh I know who this is and they'll give you your unready so we can make the same requests with different cookies and different session tokens and the server can customize our responses。

 which is great。Okay。Such tokens and cookies， very， very similar things。

 but the important thing is that session tokens are implemented with cookies。😊，Okay。

And finally how do you log out so there's a couple ways to do it so one way is if you explicitly click log out then both sites destroy the token so when you click log out maybe like a little piece of JavaScriptscript runs or something deletes your token and then。

The server will also delete it from their database and say， nope。

 this person is no longer logged in Another way to log out is if the session finds out so maybe the session was only valid for know 15 minutes or something and after 15 minutes expired the session to cookie might just expire so the server might delete it say they's no longer active it's been too long and maybe the cookie itself expires so lots of different ways to destroy a session tokyo once you're done。

😊，O。Questions， okay。So session tokens， they are very secret values and if you think about it。

 imagine if someone comes along and steals your session token what happens if they steal your session token well now they can take that same secret value attached to their own requests and when the server sees those requests what will the server think they're like oh I know this value I know who this is but it's not actually you someone else who's stole a value and it's pretending to be you so session tokens are really sensitive because they are how the server know who you knows who you are so if someone else steals that value they can present the same value to the server and the server will see that value and be like it's you I remember you but is not actually you someone else who's stole your access token they're stealing your identity and now they can do anything they want inside your email account or your bank account or whatever it is you're logged into so you have to be really careful about session tokens。

They are like as good as your password， someone steals your session token。

 it's like they stole your password they can now log in as you， which is bad okay。

So how do we stop this the server has to be careful here because the server needs to generate these tokens very securely and very randomly because if the server generates the tokens like0。

1，2，3，4 well now the attacker has a very easy time guessing what the token is and if they guess the token right they can pretend to be you so the server has to be really careful it has to generate the session tokens randomly so one way to do this is maybe pick a really long value like 256 bits and make them all random bits and usually a secure random number generator and now if an attacker wants to guess the session token what are their odds of succeeding like one in two to the 256 right like size of the universe unlikely so we have to be careful make sure the session tokens are not guessable and not compromising okay。

That's the server making sure that the session tokens they create are not guessable the browser itself also has to make sure that other people can't steal the session token。

 for example， if I log on to evil。com， it would be really bad if evil。

com could just go into the cookie jar uses of JavaScript and pull out all the cookies including session token values and just read them that would be really bad because now the attacker is JavaScriptscript and like maybe take those values send them back to the attacker or something now the attacker knows all your session tokens。

So the browser itself has to make sure that if you go to evil。

com for who knows why the JavaScriptscript or any code on evil。

com executing in your browser is not able to see these session tokens and steal and how do we enforce stuff like this。

 we need to make sure that unrelated websites don't interact with each other so we saw how cookie policy would stop you maybe evil。

com from receiving the cookie we don't want to send this sensitive session tokens to evil。

com because that would be bad and also say same emerge policy where I'm not able to access the data in some other website so this is where we need to enforce that like separation of different websites okay。

AndFinally， like we said， it'd be really bad if you had a cookie that logged you into Google。

com and when you made a request to evil。com your browser was like oops。

 I automatically attached the Google。com cookie into my request of the attacker now the attacker receive the request knows your session token value can log in as you so that's where the cookie policy comes in we only attach relevant cookies and we need to carefully set these cookies such that the Google。

com session token is not sent to an irrelevant website like the attacker's website or anyone else's website for that matter okay。

So how do we build one of these session token cookies we know these are the fields of the cookie value they can be filled in with basically anything you want subject to the cookie rules so here's an example of what you might want to set so name and value seems reasonable maybe call a token you can call a session token we call it whatever you want the value it's got to be long and random we talked about this the value cannot be something predictable it can't be like a counter or the current date then an attacker could guess it and that would be bad so this needs to be long random value256 bit size of the universe unlike guess。

What about domain and path these I need to be really careful when I set them because I need to set them so that the browser only attaches these cookies to the relevant requests。

 so if I mess up and I set these domains and paths to be too general or too specific I could mess up and cause this cookie to be sent to the wrong place so maybe if this is a cookie for my email I'm going to specifically say domain is mail。

google。com so that this cookie is only a sensory requests。😡，That ended mail。google。com， so mail。

google。com would received this， but maps。google。com would not or evil。

com would not receive this cookie because it's not relevant to those domains。

So I need to set these specifically and that depends on like how neural website is organized。

 you need to carefully set these so that this cookie is only sent when it's needed。

 you should never be sending this cookie unnecessarily because it's got top secret login data。

And the way that you control that is you set the domain and the path to limit this cookie。

 so it's only sent in the relevant cases， okay？Should I set the secure flag to true probably right seems like a nice idea if this is a secret value to take that secure flag flip it on even if I didn't know anything about what that was。

 but what it actually does is it would say that this cookie is only sent over HtTPS connection so if you make a insecure connection where an attacker can eavesdrop on a channel then this cookie would not be sent only sent if the channel over the network that you're using as encrypted which is a nice property。

HtTP only again，'s kind of on you and what settings you're using。

 but one possibility or one argument for setting it equal to true is because you don't want JavaScript to be able to dig and access those tokens like I would not want the JavaScript on some other website to be able to dig through all my cookies and find this session token and now they know my random value so one way to stop that is to just say no JavaScript can ever touch this cookie if JavaScript asks for a list of all cookies Word is going to pretend this doesn't exist and not give it back to the JavaScript。

So you can do something like that and then finally expiration date again it's up to you。

 but if you think that a user can only be logged in for 15 minutes at a time and after that they should log in again。

 then you might set the expiry date to something like that if you feel differently you're like user can log in stay logged in for like a day a year then you can change this expiry date as you feel a。

Okay but the downside is you know someone sets an expiry date of like a year in the future now this cookie is good for a year so now that user is going to stay logged in for a year even if say someone else steal the computer or something so it gets's up to you right there's a tradeoff between usability and security that we see over and over again。

Okay questions when you log in again is the session token different if you're asking about two separate logins I think it's generally true that the session token is different so once I log out the session again is destroyed if I make another login request with my username and password all over again I should get a different token yeah free question others。

If we set the agency only we to choose， then how the server verify messages。

The question was if HTTP only is true how does the server know whether or not the JavaScript is correct。

 well when I send the cookie over the server receives the cookie as part of the HTTP request right they don't need JavaScript to be able to access this cookie。

 it send as part of the HTTP request data。两对不し。嗯嗯，O。

I'm not getting through like the rest of the weekend， I okay？

So that's it for cookies that's it for session authentication which is a particular application of cookies。

 so the final thing we have to talk to you about is the attack on cookies and then after that we can go home and I can get a good night's rest hopefully okay。

So we've already talked about cookies and session tokens we know how the session token is implemented using cookies and it's a value that associates a request with the current person who is logged in and the browser automatically attaches the stuff so the attack here is called crossite request forgery it's kind of a fancy name but basically the idea is that well what if the attacker tricks you into clicking something you are not intending to click so for example。

I lot of examples later， but basically the idea is if an attacker tricks you into clicking something you did not mean to click and we'll see lots of different ways to do this when I click on something what's going happen the server is not the server the browser is going to automatically attach all the relevant cookies and then the request is gonna be made so if the attacker tricks me into making a request that I did not intend to make like I was not actually trying to do it but the attacker trick me into doing it the cookies will be attached because that's what the browser does it automatically attaches cookies and then the server will have no idea that I got tricked the server will think yeah this person probably really wants to send$100 to mal and bankss going to make that happen because they have no idea that I've been tricked they see the request they see the cookies are valid they see the session token matches my previous logged in token and they give it they give me the request or they execute my request。

So CSRf is an exploit on the fact that the browser attaches cookies automatically to allow an attacker to perform an action as me。

 they're going to trick me into doing something， I'm going to potentially believe the attacker and make that request and because when I make the request I automatically attach the cookies。

 the server will think that I actually meant to do that even though the attacker trigger me。Okay。

Here's what it looks like in a diagram so the first thing that happens is we actually log in so we send the username and password and then we receive a valid session token so now in our browser we've got the valid session token the server's database also says that token refer first to this person who's currently logged in so the server knows who I am I have the session token that I can present so that the server knows who I am。

And now somehow the attacker might trick me and click this link or make this post request and if I accidentally make that request and I listen to the attacker。

 then I'm going to send a request to the server and what will the browser do。

 the browser will automatically attach that cookie and the server will have no idea whether or not I actually meant to do that or whether or not I was tricked by the attacker so the server is going to see the request is going to have my name on it。

 my cookie on and my session token and the server is going think it came from me。

So that's basically it it's got a fancy name it's got all these different steps。

 but ultimately all you're doing is you're abusing this fact that because of the cookies being automatically attached any new request from the user will look like it's coming from them because of those cookies so if you can trick the user into making a request then the server will have no idea that the user was tricked the server will think the user actually meant to do so all of it kind of boils down to making the user make that request while they're logged in and automatically sending cookies okay。

So feels like easier said than done right like how am I going get the victim into making a malicious request I guess everyone you know that goalable that they will just click on whatever link So here are lots of different ways to do it So I'm gonna split into two different categories suppose I want the victim to make a get request that they did not mean to make how would I do that there's actually lots of different ways So one way is maybe I'll trick the victim into clicking a link I'll send the victim an email being like you've just won 10 dollars and a new iPhone click on this link to claim and if the user clicks on it now their browser is gonna open that link and what does the browser do when it opens a link makes a get request to that link to see what that link contains and fetch the information from there So if you can somehow trick the victim into clicking a link that they were not intending to click then that's one way to trick them into making a request and if。

That requests to some authenticated server like the bank。

 then the cookies will be automatically attached， right？And how much you do this， yes。

 you can send an email that's like youve one， you know a new iPhone。

 you can also do other things and we'll see those when we talk about like clickjaing and phish， okay。

So example， maybe that link that I send in the email goes to something like this and maybe the bank has this transfer function that is opening up to everyone and if you send a get request to the transfer endpoint with these arguments maybe the bank will process your transfer and when the user clicks on this the user is gonna send the request with these arguments and the banks going process it why is the bank going to accept this request because the user automatically attaches cookies so the bank will say I remember you you're the person that's just logged in and you want to transfer 100 bucks to mallllory like okay I'll do it and so now all your moneys going okay。

Other ways to do it maybe you just accidentally go on evil。com for some reason and if you go to evil。

com maybe their website has some JavaScriptscript then we know JavaScript can also make requests that's an option here's a pretty cool option which is do you remember。

That image source thing from last time where we said if I embed this HTML on a website that someone loads and the website or the browser is trying its best to make the website look nice。

 how is the browser going to make the image appear the browser is going go to that link get the image and display it for me that's what the image source tag does I go to this link make a get request to fetch the image and display it to the user so whatever link I put here the only way for the browser to make this image appear nicely is to make a get request and fetch the image except that's not actually an image link right like there's probably not an image sitting over there so。

Even though this doesn't have an image， what the browser going do it's going say I see an image tag。

 I think I need to make the image appear for the user， so I'm gonna make a get request。

 receive an image and show it to the user so I make the get request I receive back not an image and I display an error I'm like that wasn't an image but it's way too late because by the time I've made that get request and received back like error not an image I've already sent this get request over and the money is already gone so the image first tag is one way to trick people into making a get request。

😡，Because the only way to render this image tag correctly is to make a get request to whatever the source attribute is and try to get the image back and maybe you don't get an image。

 maybe you just went to some endpoint that causes some transfer to happen okay？😡。

Yeah HTML will probably return an error but by that time it's too late your get request was already sent and as we know cookies are automatically attached and no one asks you if you want to send the cookie they're automatically attached so by the time this request gets sent is too late Valer's got the money and you get an error on your web page okay。

Great so those are ways to trick the user into making a get request Those were simpler because all I have to do is get the user to click on a link or make a get request What about post post is a little bit trickier because if I just go into my browser and type a link that's not a post request that's a get request and we talked about that last time。

😊，So how am I going to make a post request happen well as we said。

 if you just click on a link that triggers a get request it doesn't trigger a post， however。

 maybe when you send the user an email like you've just won the lottery， click to claim your prize。

 maybe you make the user open the attacker's website and maybe the attacker's website has JavaScript that makes a post request JavaScript is able to make a post request so that might be an option。

Other options are if you know the victim is going to visit some website。

 I could put JavaScript on that website I'm like I know the user logs on Facebook a lot and so I'm just going go on Facebook write some JavaScript and then maybe the user will run that and that's an attack that we'll see a couple lectures from now。

Other ways to do it are you can just pay for an advertisement and the advertisement has the JavaScript so if you ever open a page and the advertisement loads well now the JavaScript is going to run and is' going to cause you to make a post request so ultimately if you want a post request usually involves some level of executing JavaScript on the victim's side but still possible right so just because I want to make a post request instead instead of a get request that doesn't mean CSRF is completely defeated it is still possible just a little bit harder。

Well， any other questions？Okay almost done okay great so this is you've seen this over and over again once we talked about web attacks we're going check off a bunch more of these。

 but here's CSRF sitting in the top 10 and all you had to know was know web 1。

0 basics and how cookies work and yet like there it is is a top 10 so still really common these days even if it's been around for it。

😊，Okay， and as we go through what we'll check off even more of these so come back next time we'll check off another one。

Okay。You're a bunch of example I'm not going to go through all of them turns out the like internet of things you know like the smart toasters and stuff tend to not be very securely built so there's actually ways to do CSR on those you can read about it all you want there This one is like a really old slide that I've kept around because I find it pretty funny because I remember when YouTube had a friend and family list because I certainly don't but apparently back in 2008 there was a CSR vulnerability on YouTube where you could add people to your family list。

Okay， fun， I would imagine this no longer exists， but it does hit major websites too， okay。

That's fun， but yeah this happens all the time here's the one from like Facebook in 2009 it's been around forever。

 but all of them have the same origin which is I shouldn't have said same more of all of them have the same cause。

 which is that I am tricking the user into making a request that they did not intend to make。

Like if you read this article， what does it say the attack involved the HTML image tag residing on the site。

 so they were using that image source trick to make people make get requests。Okay， and even。

 you know， when you make that get request it's even returning an image so you can't even tell that something has gone wrong。

 so they were really tricky about it。Okay。So that's ESR that's the attack all of it really boils down to you if you trick the user into clicking a link or making your request and the cookies get automatically attached。

 the server has no idea of telling whether or not the user was strict or whether or not the user really meant to send $900 to melody because how could the server know that the request has been made the cookies are attached so from the server's perspective it's totally good totally legal okay。

Questions about CS或 talking about defense。O。I amAl there。

So there are three defenses that we're going to talk about and these defenses are all servers so interestingly。

 the CSR of defense actually has to happen on the server's behalf。 and so here。

The server' is going to try and add an extra piece of authentication so like what was the main flaw that made CSRf a problem Well the problem was that if you sent a request and the request had the right cookie then the server just had to accept it if if the session token was correct the server would say hey I know you you're the person who just logged in and I want to accept your request and so that was not enough so in these defenses we're going try to add extra security extra information so that now it's not enough just to send a session token。

For the server to know who you are， you need to set an extra second secret value for the server to know who you are。

 and that second extra secret value is called a CSRF token。

So now there are two secret values the session token is still there I'm not getting rid of it however this time I'm going to add a second secret value so how is this going to work I'm going to request the secret value as the user I'm going to request the secret value from the server the server is going to give me a bonus secret values was not just the session token but also a bonus secret value that only I know and my request is going to have to manually attach that bonus secret value in order to be accepted as value so the cookie itself it was too automatic attaching that cookie automatically was not good because now the attacker can trick anyone。

to making a request that automatically attaching the cookies。

 but the CSRF token is going to be a little bit more difficult so it's not going to be bundled in a cookie because cookies were automatically attached we're going put it somewhere else。

 it's a little bit more difficult。 So maybe like the header。

 the get parameter one of the arguments in the get URL the content。

 the data and the post request so here。This extra secret value is not automatically attached Someone needs to do a little bit of extra work in order to send this value to the server and this second value which is not automatically attached is what's going to stop a bunch of CS or Fs so here's an example that I like which is say you want to fill out a form so。

😡，If we had no defenses a form is vulnerable to CSRF why is that because if I well suppose first we should say that forms usually our post request right when we submit a form we click the submit button the data gets sent over as a post request so what can the attacker do the attacker can make you visit their website and have some JavaScript on their website and what will the JavaScript do the JavaScript will create a brand new form JavaScript can do that the JavaScript will fill in the form with all sorts of malicious fields like two Maory $100 and so forth。

And JavaScriptscript can fill in the form and then JavaScript can make you submit that and all of this is running where the user's browser。

 the victim's browser so the attacker's JavaScript is running in the victim's browser it's creating a brand new form on the victim's browser it' filling it in with all the right field mallory 100 and then it's submitting a post request with the user's cookie attached automatically so that's how a form might be vulnerable to CSRF so how to CSRF tool can stop this。

Now I'm going to add an extra value that's an notword of the cookie so now when I request a form the form' is going to have all the usual fields name。

 amount of money you want to send who you want to send it to。

 it's going to have all those same fields except it's going to have an extra field where it's going to say hey in that H response for HttP response I gave you another secret value wasn't just the cookie but I gave you a secret value specific to this form so when you submit this form please also attach that secret value for me and only if you give me the right secret value will I be convinced that you are who you say you。

So now was the attacker going to have to do well the attacker is going to have to make a brand new form just like they did before。

 they're going to have to fill in all the fields and then make the post request except how is the attacker going to know what to put in that CSRF token do？

They don't， the attacker doesn't know what to put there。

 so now the attacker is no longer able to fill in all the fields of that form in a way that the server accepts。

😡，Server could try to or the attacker could try to put in their own CSRF token。

 but it doesn't match right each token is unique to a user。

So the difference between the CSRF token and the cookie。

 the session token is that the CSRF token is something that's embedded somewhere else For field HtTP header。

 it is somewhere different so that the attacker has a harder time getting it to be automatically sent it takes more work to send now usually this is still automated to some extent right like I've never had the type of a CSRF token but adding this extra secret field that's not automatically sent the way that a cookie is automatically sent is going to help me stop CSRF attack。

That's the hazard I。O。So that's one attack or one defense， okay？The user logs in， gets a token。

And when the attacker says make the request we make the request so this is regular CS or this is regular CSRF。

 however， if I add in this extra step where I get the CSRF token in step two。

 now when the attacker tells the user hey make this request fill out the form with these fields andend it。

 the attacker is not going know what to put in all the fields because there's that extra secret field the CSRF token field which we can make hidden so the user doesn't have to see it and now the attacker doesn't know how to fill in the entire form so they cannot trick the user into making a legitimate request because that CSRF token is not automatically attach the burden is on the user or the user's browser or the attacker to manually attach that token so it's a little bit of extra work。

 the user almost always never notices the browser tends to do it but now the attacker's life is a lot harder。

O。Great so that's maybe the most common and strongest CSRF token or sorry CSRF defense the CSRF token so the second defense that we're going to talk about it works but it's definitely not as bulletproof or as strong as the CSRF token so here we're going to take advantage of the fact that the HTTP request that gets sent often contains a lot of information about the request。

So we know that the HtTP request that has what has like the get impose post parameters。

 it has the URL path that i'm sending the request to so that's all these different parameters。😡。

including lots that we didn't talk about and here's one that's pretty useful so the httB request usually involves a lot of information about like the metadata I guess i'll sit down so I don't like collapse okay。

It's pretty cool， maybe I'll just sit down for the rest of the semester Reg chill Okay so the refer header is one of the many metadata fields in the HttP request so the HttP request might say things like this request was made using a Fireboxox browser or this request was made using HtTP version 1。

0 but specifically one little piece of metadata that the HtTP request tend to attach is。😊。

Where did this request come from like what webage was I sitting on when this request was made so for example if I am on Facebook。

com and I click a link then the refer header will say this HtP request was generated by somebody who was sitting on Facebook。

 co on their browser and click the link there so sometimes the HtP request will automatically bundle this information it could be for tracking purposes it could just be to keep track of where the requests are coming from do analytics but sometimes people will attach this or say I don't know。

I go to the Facebook homepage and I type in my username and password and I send it。

 the refer header will say this person， the way that they made this request or the way that the request was triggered was that they were on www。

facebook。com， they typed in their username and password and then they sent it off。

 click the submit button。And this works for malicious things too so for example。

 if you're on say like a forum and someone makes a post with a malicious IMG tag and you make the get request。

 then the refer header will say the reason why this get request was triggered in the first place was because the user was on that form saw the IMG tag made the get request so the refer header roughly speaking tells you where the Rick has came from or say you're on an attacker's website and the attacker's website runs some JavaScript that triggers a request the refer header would say something like this request is made。

When the user was on the attacker's website and made a request。So that the refer header。

 it gives you some clue as to where the request came from and if you're wondering why it's spelled wrong should have two R's not one。

 apparently someone  typed it and no one has fixed it so refer header with one R okay doesn't really matter though。

 but it is kind of funny okay。So what is this thing good for well the refer header can give the server and again the server is the one doing all this defense stuff it was the one that implemented the tokens server is also the one that implements the refer header so the server can now use the refer header to get a clue as to whether or not this was something the user actually meant to do or whether or not the user just got tricked so this might offer the server a little bit of an insight into what the user was thinking for example。

If I receive a request a login request say and it comes from bank。

com/ login in other words the referer header says the user was on bank。com/ login fill out the form。

 click submit and the refer is bank。com/ login then as the bank server when I see this request and I see that the refer is bank。

com/ login I am I think to myself you know what this user made the request from my website the bank。

com website so I feel pretty good about so I think the user was really on my website made the login request so I think this is legitimate I don't think this user was tricked。

However。If I receive a login request with a username and a password and it's。😡，Refer as like evil。

com well then now the bank is looking at this and being like wait a minute why did the user go to evil。

com and then try to send a login request to me the bank I don't like so I don't think this refer makes sense so I'm going to reject this login request I'm not going to accept it or I'm going to reject this money transfer request or whatever so。

😡，One possible policy is that when you check the refer header。

 you allow the request if the refer is from the same website， so if your're bank。com。

 you only accept the requests that were made as a result of someone sitting on bank。

com and making a request and you do not allow crossite request。

 so you do not allow someone to be on a different website like evil。

com and sending a request to bank。com as a result of sitting on evil。com。And this is all servers。

 the servers job to use the refer and clue themselves into whether or not the user meant to make the request or if they possibly got tricked。

😡，So ver add seems great， seems like I have a way to distinguish whether or not the user was being tricked or whether or not they really meant to log in or transfer money but。

There's a problem and the biggest problem is that the referer header is options。

 there's no requirement that the refer header is correct or filled in。

 it could be blank and so one reason why the refer header might be blank。😊。

It's because the refer header might leave private information。 So， for example。

 say you're on like Apple's internal website。 I don't actually know if this is their internal website。

 but say this is and。If you were on this website and you submitted I don't know a form or something。

 then the refer header would say hey that user was sitting on this top secretet Apple URL before they made the request suddenly you've leaked information about like Apple's top secrets probably bad so sometimes people will strip the refer header and delete it before sending the request on so some browsers have security settings and privacy settings where you can actually strip away the refer header and leave a blank。

So that when I make the HtP request instead of honestly feeling in the refer like everyone was hoping I can just leave it blank。

 the HtP request is still valid， it doesn't require the refer header to be filled in。

 still a valid request but now the server is now in a bit of a pickle because the server gets a blank refer header so what does it do was this really an intentional request on the user's behalf was this the user being tricked I don't know because the header is blank it doesn't tell me any information because whoever made the request strip the header away so now I have to figure out do I deny things that have a blank header do I accept things that have a blank header is a tradeoff if I accept everything then maybe it's less secure but more usable if I deny everything maybe it's more secure but it's less usable so now I have a bit of a struggle to decide when the header is blank what has to happen？

Okay。That's refer header the final defense is a little bit more modern and I guess we don't have too many slides on it just one and so this one's called the same site cookie attribute this is another attribute inside of cookies so remember how cookies had like they have domains they have paths they have secure they HtTP only they have one more it's called same site and it functions kind of similarly to the refer header but the refer header was for HtTP requests same site as for cookies。

And so the same site says。When I dig through the cookie jar to decide what gets sent or what doesn't get sent。

 don't just check for the domains and the paths being valid。

 make an additional check and make sure that if。I'm sending a cookie to evil。

 co or yeah when I'm sending a cookie to evil。 co the domain of the cookie needs to also match evil。

 co or when I'm sending a cookie to I don't know bank co the domain of the cookie needs to exactly match bank So this is a stricter check between the cookie domain and the domain of the origin you're on so sorry I may have messed that up a little bit so one more time same site doesn't check it not only checks who you're sending it to so that's what all cookies check all cookies check you're sending to bank co or Google co or mailgoo co as we saw but the same site additionally checks what website you're currently on as you make the request So if I'm sitting on evil co and I make a request to bank co the same site cookie attribute will say well in general I would send the bank cookie because I make them a request to bank co。

But because you have specifically told me that you should only send cookies conservatively and only send if I was sitting on bank。

com and made a request bank。com， I'm actually not going to send the cookie and the reason why I'm not going send it is because I was sitting on evil。

com when the request to bank。com was made if same side is set strict the only way in which the cookie will be sent is if I was sitting on bank。

com and I made a request to bank。com then the cookie would be。So。

That's the same sign cookie attribute， I believe most modern browsers have it。

Probably just like Microsoft Edge or internet Explorer if it doesn't have it。

 but it's kind of like coming down the pipeline， it's another way to defend against CSRF attacks。

Okay， awesome， I'm almost done。So。Quick summary on cookies and then I'm gonna to go take a long nap so cookies were a piece of data it's just a name value paired with a lot of different attributes and the reason why cookies exist is because we want to be able to maintain state across multiple requests if I would like the website to be dark mode I order the website please be dark mode for the rest of time The server is gonna send me a cookie I'm going to store the cookie in the browsers cookie jar and on all future requests this browser will automatically attach the cookie and that way the server can customize this response and make the background look dark or whatever it is I request。

So it allows independent HtTP requests to stop being independent and we talked about these rules and the important thing is really not the specific rules to be honest but the important thing here is why these rules exist so anyone can just tell you these rules and you just write them down on your cheat sheet and memorize them the important thing about these rules is that they are trying to stop attacks where cookies are allowed to affect unrelated domains so I don't want evil docom to be able to set a cookie that affects Google co I don't want evil。

com to be able to change my dark mode settings everywhere or like logging in on all sorts of different places that would be bad。

And similarly， I only want to attach relevant cookies， I don't want to send my Google。

com session token top secret evil。com so the cookie policy restricts what cookies do I accept。

 I don't want to accept evil。com sending me unrelated crap and I don't want to send unrelated stuff if I'm making a request to Google。

com I'd better only send the cookies that are relevant to my current request。

Talked about session authentication， a particular implementation or like a particular idea that's implemented by cookies。

 so session authentication could be implemented all sorts of different ways。

 but cookies are the most natural way and again cookies are not the only thing you can session authentication is not the only thing you can do with cookies you can do all sorts of different things session authentication is one of them they can think of it as the first time you log in you send a username password receive a session token as a cookie and then in the future you automatically attach that cookie however we have to be careful because that session token is you it's you being logged in if someone steals it they can now log in as you so you have to be really careful about keeping them secure and not sending them to the wrong place talked about CSRf it's a fancy attack a fancy name but all that it is is you're tricking the victim into making a request the request automatically attaches cookies and the server has no idea whether or not you really meant to send it or whether or not you got tricked into sending it and this could be a get request could be a post request as long as the attacker。

See into making the request and we talked about the three defenses token is an extra secret value that the attacker does not know but needs to fill in themselves so no longer automatically attached has to be filled in by the user of the attacker now the attacker doesn't know the secret value cannot fill it in when they're tricking you into making a request talked about the reverse header and sames cookie which gives you a rough clue as to where the request came okay。

That's it thanks for stick with me as I like sniffled the whole time， so I'll see you on Monday。

 maybe。

![](img/3d6d31b1db9e129f95909bb119cc6a8e_3.png)

Okay。
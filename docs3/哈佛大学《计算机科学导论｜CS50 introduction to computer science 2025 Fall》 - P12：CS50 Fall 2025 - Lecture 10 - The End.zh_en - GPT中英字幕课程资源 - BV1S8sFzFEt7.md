# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P12：CS50 Fall 2025 - Lecture 10 - The End.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

Alright， this is C S 50， week 10， the very end， and we will end today's class just as we ended week 0。

 which is a little bit of cake outside in the transcept。 But over these past 10 plus weeks。

 if you've been feeling like it was that proverbial fire hose hitting you in the face with so much new content。

 so many new skills， so many new challenges， realize that you're in very good company and we can officially declare nonetheless。

 that if you started the class among those less comfortable。

 you are officially after today no longer less comfortable。

 you're at least somewhere in between and if you were in between。

 you're more comfortable and if you were more comfortable。

 you're perhaps now most comfortable among those here。

 But keep in mind as per CS50 syllabus what does ultimately matter in this course is not so much where you end up relative to your classmates。

 but where you end up relative where to where you yourself began and that's taken into account come final projects come final grades。

 but most importantly， that's really what's most important educationally in general is that Delta from week 0 to in our case here now。

 week 10。 So if it's any reassurance， something I like to bring up around this。😊。

Is just how badly I did in CS 50。 and like the very first problem set Like I didn't even get hello world right somehow in the fall of 1996。

 So here's a photograph of my homework assignment for assignment1。

 It was a program to print hello world on the screen， I was incredibly detailed with my comments。

 even commenting that mainine is main， which is not the way you're supposed to program even telling the Tf where my file ended。

 which is not really necessary。 And I got minus-2 for not even following directions correctly。

 So take some comfort in that even if by problem set none。

 you're still getting points're hopefully at least in my case in some very good company。

 It only gets better and easier and faster in time。

 But the whole course ultimately has really been about this picture。

 problem solving is computer science and you have inputs， which is the problem to be solved。

 You have the outputs that you want to get to which is presumably the solutions there too and inside of that proverbial black box are these algorithm。

 step bystep instructions for solving some problem。

 And I pulled up my own notes from C 50's first lecture。

 some 25 plus years ago too where I wrote down。This in my horrible writing handwriting to this day。

 but I noted that what an algorithm is is a precise sequence of steps for getting something done。

 which is pretty much what we now say。 I noted that programming itself。

 as we have for weeks now is the process of taking an algorithm and putting it into a language that computer can process。

 And that's what you've done in scratch and C in Python in SQL in Java and anything in between and most important。

 at least my takeaway that day when it comes to algorithms is precision and correctness and indeed those are points we've made perhaps not as emphatically over the past several weeks as well。

 but we thought we'd see just how much those two lessons in particular have sunk in by doing a bit of an exercise。

 some CS50 pictionary in this our last lecture altogether this term for which to begin we need one brave volunteer to come on up stage。

Who would like to volunteer， Who how about， okay， over here。

 We never call from the middle of the section， Come on up。

 come on up a round of applause for being so brave， nice。😊，All right， come on over。And。

In just a moment， let's go ahead and do introductions first you want to come up over to the middle of the stage and introduce yourself to the world。

Hi， I'm Gia。 I'm a freshman。 All right， nice， nice to meet you。 Thank you for joining us。

 So what we're about to do is G is gonna look at my screen where there's going to be a picture on a white screen。

 All of you， presumably have a white sheet of paper in front of you that you grabbed on the way in。

 if you don't just grab one from a friend or your binder or the like。 And if you really don't。

 that's okay， too。 But hopefully everyone has a pen or pencil or someone near you does。 And what Ge。

 we're gonna ask you to do is program the audience to draw what it is you see on the screen。

 you can say anything you want， but you may not use any physical gestures or the like verbal programming only Okay all right。

 come on over to the lectern。😊，And in just a moment。

 GN only GA will see what is actually here on the screen。Step one for your audience。Okay。

 so the first thing that you need to do is draw two lines right next to each other。

 two vertical lines。Okay， okay。Step  two， step two， once you have done that。

 you need to draw three dots， one on above those two vertical lines。

 one right in the middle between those two vertical lines and one at on the bottom of these three vertical lines beneath。

Those two vertical lives。 Yeah， so three dots。Okay， step three。

 step three is on the top of the left vertical line。

 you're going to connect a line from that position to the top dot that you drew。

 and then on the top of the right vertical line， you're going to connect that position to the top dot that you drew。

All right， step four。Is。Remember that top left position。

 you're going to connect that to the middle dot that you drew。

And then the top right of the vertical line。yes， you're going to connect that to the middle dot of the line that you drew。

And then step five。On the bottom left of your left vertical line。

 you're going to connect that position to the bottom dot that you drew。

And then on the bottom right of the right vertical line。

 you're gonna connect that position to the bottom dot that you drew。And now。

 from the middle dot to the bottom dot， you should have no line in between that。

 And you can now draw a line between those two dots。Step 6 and the last。 I think you should be done。

 All right， a round of applause then for our programmer。 Let me give you a little something。

If you want to take a seat， now what Kelly and I are going to do is very quickly collect your execution of this program。

 and we'll see just how it went with Gia as the programmer。

 If you want to just reach out and hand me or Kelly over there。 Any of your handwritings。

 We don't need all of them， just a representative sample will suffice。If you're proud of your work。

 extend your hand quite a bit， okay， very proud， okay， okay。Okay， okay， one more， one more， okay。

 all I'm going to run back to the stage， okay， it's okay if we didn't grab yours。All right。All right。

 so thank you to Kelly for grabbing these as well， so without having seen any of these here is how you all interpreted Gia's instructions。

 so here's one。😡，Interpretation。Perhaps similar or different from your own， here's another several。

A time。erVertical line question mark， okay？Here is。Very narrow one。All right。And。

And let's see if we got any other variants thereof。 Actually， the rest of them are pretty consistent。

 So G， if， it's any reassurance， I'm seeing a lot of ones that look like this。

 Here's another that looks like。this， and here's yet another that looks like this。

 So if you're wondering where we're going with this。

 if I go ahead and reveal what it was Gia was looking at on the screen， she was， in fact。

 having you draw this here。😡，Cube so some of the takeaways here。

 Souffice to say not all of that went well。 But why was that。 Well。

 I dare say it was very easy to get confused。 I think Ge in some of your words。

 because you had in your mind's eye， exactly what it was you were drawing。 And of course。

 it was right there on the screen， but we didn't leverage at least in G's instructionsions any abstractions。

 I dare it might have been a little bit easier for all of us。

 if maybe she had just teed things up by saying， all right， everyone。

 we're going to draw a cube for instance， which is indeed an abstraction over these lower level details that she was focusing on。

 but perhaps there could have been another approach altogether， which is even more pedantic。

 for instance， a lot of the earliest drawing programs and even worlds like scratch sort of take for granted that you have a coordinate system like X's and y's and even up down left and right。

 So one alternative to just saying， hey， I'll draw a cube。

 which could be subject to interpretation because the cube like this， I it like this rotated。

 So we still would have needed more information than just a cube from Gia， but here。

 maybe an alternative approach would have been to really get into the weeds and say。

Put your pen at the top of the page and then draw a straight line to the southwest， for instance。

 and then draw another line of the same distance to the south and then to the southeast or so forth。

 And it could have been in terms of degrees， It could be directionally in that way。

 but it might not have been clear to anyone。 What it was we were drawing until enough of the line suddenly peer on the screen and then voila。

 you see that we've been drawing a cube this whole time。

 So the degree to which we're precise And the layer of the level of abstraction that we operate in is incredibly important。

 whether it's for another human to understand us for an AI to understand us nowadays or anything in between。

 All right， why don't we go ahead and flip things around a bit for this。

 Why don't we go ahead and get one more volunteer to do something a little different here on stage one more。

 how about here on the aisle come on down round of applause for this spray volunteer Come on down。

All right， so in this exercise we're going to flip things around so you all will be giving the instructions verbally by just shouting them out and our volunteer whose name is Preston。

😡，Presley， Presley， Presley want to say a quick introduction。 Yeah， my name is Presley。

 I'm a freshman living in Stoughton House。 Nice， Well， welcome， come on over to the the easel here。

 And we have a black marker for Presley here。 And the only thing that we ask is that you not look up or behind you。

 because the answer is gonna be right there on the screen。

 But everyone else is welcome to look up or over to the TV screen。

 And if you want to go ahead and face the easel here。

 And as you draw just make sure to kind of open up after each stroke of the pen so that everyone can see what you have done。

 Allright， so no looking up as of now， because what the audience is about to do is to program you to draw this on the screen。

😊，Oh， way to encourage him。 Okay， so step1， feel free to just raise your hand and we'll shout him out。

Oh I heard draw circle over here。😡，But not too big， I heard over here。😡，Good abstraction。

 you're going to end up drawing a stick figure。But we should probably be a little more helpful than that。

 So let's do the hand thing just so we can be more precise and not over Presley。

 there Ru a hand over here。 Yeah， and back。Draw a line down from the circle， Presley。

From the bottom of the circle。😡，Okay， someone else？Actually， let me rewind， so say it again。😡，agon。

Draw two diagonal lines from the line you just drew。😡，Well， I don't think the audience likes this。

 Wait， let's。Okay。Okay， that's what we were told， next step， someone else。😡，さ。Good one。 Okay。

 extends the original vertical line to be about the same height as the circle。Okay， yeah。

 that's good， Good feedback。 Alright， someone else， next step。Next step。Yes。抓清。Nice。

Draw two diagonal lines from the bottom of that line that look like legs， good use of。

Detail and abstraction。Okay， nice， next step。Anyone we' close， yeah， over here。😡，台。On the left。

 so you're going to draw a speech bubble to the left of the head with the wordh capital H with a short line。

😡，No bubble all just high。嗯。And you wanted to clarify one other detail。😡。

A line from high to the face。With space in between， okay， no， you're doing great， it's okay。

 pressley， hang in there， okay， final step or two。Next step。Anyone at all。Feel free to shout it out。

Adjust the arms to make them look like they're running。😡，Good luck。Oh。

 I like that draw perpendicular line from the left arm。To the bottom。😡，and lastly， one final step。

Same side。Yeah， it's permanent。I think we need a final touch on the other arm。 Maybe yes。

 one final step。Anyone？不。Draw a perpendicular line diagonally to the left。😡，Of the right arm。嗯。

Just a little bit。All right， I think we've withheld our applause long enough Presley。

 if you want to take a step back and look at what they were trying to get you to draw。

A round of applause。So here too， let me here you go。 Be your dorm room， if you would like。 Okay。

 and a little super Mario as well。 All right， so here， too， I think you were the problem this time。

 round of applause for pressly。😊，And of course， since it's permanent in。

 it's easy to sort of go off the rails early on and make a mistake。

 But I think was actually a nice mix of lowlevel details。

 like the directions of the lines and the lengths thereof and also some abstractions。

 because I do dare say someone shouting out that it is to be a stick figure gave him a much more helpful mental model。

 So that might be sort the comments on top of the function。

 but when we really got into the weeds of implementing that function。

 it was more akin tostep by step instructionsions for solving this here， particular problem。

 So my thanks to Presley for bearing with us with that one as well。 So beyond this。

 where have we been up until now。 So if we look back at the pastover weeks。

 this is sort of the trajectory on which we've been， So we started with scratch from scratch。

 literally in the very first week， the goal of which which introduce you to some of those procedural fundamentals。

 like what a loop is and a conditional and Boolean expressions and variables。

 which have pretty much recurred in different forms and different languages over the week since。

Thereafter we transition to a more traditional language C。

 which many of you will never use again and admittedly even I only use it for like a month or two of the year during CS 50 itself。

 But the intent was to be this incredibly foundational language that so many other languages today are built on top of case and point the interpreter that you might use for Python itself can be written in C。

 And that speaks to how we sort of talked about bootstrapping from one language to another from low level to high level and beyond arrays in algorithms。

 all of memory and data structures like all of that is sort of omnipresent and computing in programming and the like。

 even though you might not need to in modern languages like Python worry as much about managing your own memory because good programmers。

 better programmers have figured out how to solve those problems for you in the language itself or in the libraries that you're using。

 you can take for granted now that you at least know what a hash table is， what a linked list is。

 what the tradeoffs are among those what the running times are。

 and that's what computer scientists and software engineers think about and talk about and whiteboard about in the real。

World when trying to implement algorithms of their own to real world problems or implementing realw products。

 And then， of course， of the past few weeks， we've sort of used that as a stepping stone to talk about very modern programming paradigms。

 most recently web programming。 And even though we didn't use it explicitly in the class mobile programming is increasingly based on Htl and CsS and jascript。

 which might be something some of you will tackle for your own final projects and you can escape now using or seeing or leveraging somehow artificial intelligence and among the goals for today is to at least point you in the direction of tools that now having finished problems set 9。

 you are welcome and encouraged to use for your final project so that you can build all the more and all the more successfully than even some of your predecessors just a few years ago could have now that your own work and your own know how can be amplified by the impact of AI itself。

 This， of course， now brings us to today。 The end， but wanted to give you a sense of where you can go here on out。

 So with your final project。 This really is the intent of the final project is to be the very first。

😊，Of hopefully many projects that you decide to spec out for yourself like every problem set thus far has been written by me and the team and you've been following our instruction step by step。

 The frontnal project takes all of those training wheels off and even though you are welcome and encourage to borrow code from say problem set nine if you want to do something webbased or even earlier if you want to do something that's more similar to past PSetsets is to make it ultimately your own and even if you want start with a completely empty window and just a blinking prompt and build something of your own setting out for yourself as you've seen in the specification a good goal which you intend to meet no matter what a better goal which is a bit more of a stretch and a best goal。

 which in practice， rarely ever happens with software to this day 25 years since taking CS50 myself or plus now even I consistently underapp just how long it takes sometimes to solve problems but that's beginning to go away at least to some extent thanks to AI where at least now you essentially have a junior colleague next to you who can help solve bugs for you。

😡。

![](img/a745728fbc4038620ad10ac9483d4ef2_1.png)

In the right direction， even tackle features as well all that we ask for this final project is that you build something of interest to you。

 that you solve an actual problem that you input campus or that you as we say in the spec change the world and try to achieve something try to create something that outlives the course itself over these final few weeks of the class and even continue on with it if you'd like in January and beyond So what are the support structures in place and how met you go about this so a longstanding tradition of CS50 is this epic late nighter the CS50 hackathon whereby around 7 pm will serve some pizza around 9 pm will serve some ice cream and if you're still awake come midnight when the event will start to wrap we'll get in a whole bunch of CS50 shuttles drive down the road to the international house of pancakes which is open 247 and have some breakfast together if you choose with some pancakes together at this local ihop here are just a few visuals from the past year's hackathon of students gathering in the engineering building across campus here having some of that same pizza and here still being awake at early。

Morning hours as well to paint a picture of this too。

 the team few years back kindly put together a video。

 a sort of sizzle video that paints a picture of what it might be like if you at least were a Mppet attending this year。

 CS50 hackathon， we could go ahead and dim the lights。

 I think we can go ahead and play this teaser of what awaits later this week。😊。



![](img/a745728fbc4038620ad10ac9483d4ef2_3.png)

![](img/a745728fbc4038620ad10ac9483d4ef2_4.png)

Just one night all we got。Just one night all forgot。就是这什ね。🎼little。🎼So we got。🎼直接围传。いわな。Sキバ up。🎼直间为装。

🎼巴黎。🎼因为装。Al right so what then is the CS50 hackck of on itself what really is a late night opportunity to dive into to start to make progress on your final project the teaching staff and I will be there on hand。

 not so much to answer any and all questions for you but to help you help yourselves point you at resources point you at the requisite websites。

 the documentation so as to empower you ultimately to solve this here problem for yourself without some of those same prior training wheels that we've had on the goal ultimately is to prepare you for the end of semester exhibition。

 the so-called CS50 fair， which will be an opportunity to present your final projects on your phones or laptops to passers by from the faculty from students from staff from visitors all across campus here some emoji balloons will await you hear a photo booth if you'd like to immortalize the memory and the goal of the hack of the fair will be really just to present your projects to others that come by delighting in what it is you have achieved over these past few months alone and of course by the end of it you'll pick up。

Your very own CS50 tshirt， which says hopefully proudly that you have now indeed taken CS 50。

 but let's just see in preparation for that how much has indeed sunk in。

 we did have that test a couple of weeks back which went great。

 But we thought we'd pluck some of these same review questions that you prepared over the past couple of weeks to challenge at least six of your classmates to come up for now this socalled CS 50 charas for which we need two teams of three So if you're sitting there in a group of three of friends total or we'll form one up here live So come on up as our first volunteer need five more volunteers feel free to volunteer。

 the persons next to you three in a row， about two more over here one and about two on the end。

 come on up。 All right a round of applause for these six year volunteers。😊，All right。

 so let me give you one microphone。Let me give you second microphone and Kelly if you want to come on up as well。

 I think these three seem to know each other already。

 so we'll have them be one team if you guys want to be another team as well， come on up。

 let me take one microphone actually for the other team。All right。

 and have about quick introductions to this team here， and first we need a team name from you all。

 you haven't had time to think about this。😡，Team A， okay， so team A is who I'm Leah。

 I'm a first year， and I'm in wholeworthy。Welcome， my name is Steven。 I'm a freshman in Canada F。 We。

 I'm Charlotte。 I'm a freshman， and I'm also in Canada out。 Allright。

 so let's do introductions on the other team as well。 You are going to be team。😊。

Awesome Awesome sauce。 Okay， versus team A。 If you want to go ahead and introduce yourselves here。

 Hi， my name is Jenny Pan。 I'm a freshman in Holliis。 Hi， my name is Noah， I'm a freshman in abo。

 And hi， my name is Marie and I'm a freshman。 Sorry， I'm a freshman in candidate All right。

 We to both of our teams here。 And among the goals now。

 let's leave one microphone with each team is to play a bit of charades whereby one of you in a moment is going to be responsible for acting out a word that you see on the screen。

 So we're gonna put on this screen in the screen over here。 Some term that relates to C 50 somehow。

 And that person's goal over the course of 60 seconds is going to be to act that out in such a way that their teammates can hopefully guess what the word is。

 We'll give you 60 seconds at a time。 Kelly is kind offered to keep score。

 And if you solve it in fewer than 60 seconds， we got another word for you in another word And we'll see how many points you can accrue over the course of those 60 seconds。

 And depending on how this goes we'll do maybe one or two rounds in total。

 S do we get how many skips you get。 I guess you can skip。😊。

As many as you want until we run out of questions。But try not to run through all of our questions。

 All right， any questions they'll be on that。 All right。

 so if you guys want to step off stage over there， why don't we have team A begin。 So one of you。

 Leah， you're holding the mic if you want to be the char。

 let's go ahead and have you stand here So you can see the screen And we only ask that YouTube not look up because the answer is gonna be right there。

 All right， and you should just shout out the word that Leah is acting out question Act onlyras speaking Yeah。

 yeah， I can't speak because that would kind of defeat the point。

 So yes just acting out physically All right， I'm gonna go over here。

 give me just a moment to get the slides ready with your questions。😊，And Leah， the first clue， oh。

 and Kelly's going to be timing you 60 seconds to accrue as many points as you can。 All right。

 here we go。Go。A that out。好。Oh， that was weird。 Thank you， sorry。Yes， act out this is CS50。

 all right， no， act this out， please go。😡，Calling a recursion， yes， one point。Going an array。

 linkedless。Abstraction。Snake。Python， Python， Yes， Python。Duck， the duck， nice。Binary。呃。

 one zero binary digit对。第。1，0。Simply binary。As you。Want to pass。Theyten。Lless array， yes， array。Loop。

 yes， loop。Time， all right， very nicely done。All right， five is the score to be。

 So if you guys want to step over here， if one of you has the mic。

 go ahead and assume the same roles。5 is the score to beat。😡，All right，5 is the score to beat。

All right， here we go， final round。First word， and you guys just make sure you don't look up。Go。

Haad node。Input。Algorithm。谢。No。ISure， you have to act it out， act it out。Oh， they go。Run time。

Runtime。Three， yes， three。Next one。Next one。My search。Binary bullolean， no。Aerge sort， call。

 phone call function。It was binary search wasn't it Well that binary and it's time all right。

 but a round of applause for our team awesome sauce。Okay， we have some parting prizes for you。

 your very own Super Mario Pez is for you guys as well。

 I'm glad we squared away the ability to pass though on the question so thank you for that All right so admittedly pretty hard our thanks to all of these volunteers for playing that out。

 allow me to turn our attention back to here in just a moment where else。We can go from here。

 So up until now， up until now。We've been using visual studio code for CS 50 at the URL CS50 recall that this is just an adaptation of a commercial tool called Github code spaces。

 which is like a cloudbased version of visual studio code itself or VS code which is an largely open source tool for Microsoft that's incredibly popular in industry。

 which is to say， even though we have the C50 library in there。

 and we turned off by default some of the menu options and we disabled AI。

 It is the tool that so many programs around the world do use every day to write code。

 So you have been learning all this time sort of industry standards in that sense。 It is now time。

 if you so choose， but you are welcome to keep using this for your final project of feeling more comfortable with it to drop the4 CS50 and actually install on your own Mac or PC if you so choose visual studio code itself。

 you can go to this URL here， it's fairly straightforward to install it。

 but invariably you'll run into probably some technical support headaches。

 depending on the language that you're trying to use with it， for instance。

 if you're trying to use it with Python， you'll probably also have to download and install Python onto your computer。

 at least if you want the latest version。😊，And just know a priori that sometimes just stuff happens and it just doesn't work。

 and you have to Google or ask chat Ept。 and that's fine。 And honestly， that's kind of normal。

 But this is also why we don't do any of this in week 0 of the cloud so that we can focus on hello world and Mario and cash and credit and get into the interesting parts of computing and programming and not not frustrating you so with technical support challenges。

 but now given that all of you are somewhere in between or among those more comfortable you're now ready to sort deal with those same technical challenge yourself。

 But who knows， maybe it will go perfectly smoothly。

 you can go to CS50's own documentation because if you want to be able to use all of the same software that CS50 has pre-installed。

 you can use a technology known as containerization with a tool called Docker and actually run a CS50 environment on your Mac or PC or even in the cloud。

 but still run VS code on your own Mac and PC among the upsides of which are that you're not dependent necessarily on the cloud。

 you can do everything offline， which is useful in general， you can do things。

More quickly sometimes if you're using the full capabilities of your own computer and not just a browser。

 So this is generally how programmers approach their code using something like VS code or alternative products。

 And in fact， there's a bunch of others out there， but perhaps the trendiest right now are these three here。

 not just visual studio code itself。 but a tool called cursor。

 another one called Winsurf and there's dozens of other text editors often known as integrated development environments。

 which tend to have even more features that you can download for free or commercially on your own Mac PCs and the like but you can't go wrong transitioning from CSs50 to VS code on your own Mac or PC if only because you're already familiar with it。

 As for the command line。 So those of you with Mac might have found somewhere in your utilities folder。

 a program called terminal， if not poke around there later today and you'll see that all this time you've had a command line interface available to you on Mac Windows has something similar as well。

 they don't necessarily come with all of the same tools that we've been using within C5 But if you're a Mac user and you go to this URL。

Here or you're a Windows user and you go to this URL here or if you're a Linux user。

 you probably know all of this already。 so there's no URL for you there。

 you can install some of those same tools on your Mac and PC and feel all the more at home doing things in a command line as well Git this is something that we actually in CS50 abstract on top of this is essentially the def facto standard nowadays for collaborating with other people using a central cloud server in order to share your code with it and in turn other people for versioning your code so that you keep track of multiple versions thereof and changes that you've made go to this URL here if you would like and you'll see a tutorial by CS50s own Brian you introducing you to actual Git because we've been sort of abstracting away this particular tool by just doing it all automatically for you if you've ever gone through your timeline in CS50 dev being able to roll back to previous versions of your code we're just using Git but we're automatically running this command for you if you want to collaborate with partners for your final project you can use Git however I will encourage you to alternatively use。

Visual studio code's live share feature， which allows one of you to log into your codespace。

 click some buttons and then share access to your codespace with your friend or your partner with whom you're working on the project and you can both in real time like Google Docs edit the code or different files therein using that one code space a little easier than getting onboarded at least with Git hosting a website if this proves of interest for your final project or even after the course。

 if it's a static website to popular places to go if only because they offer free tiers is what's called Github pages which you can use or just host Htl Cs and jascript with no Python。

 no flash， no backend or netlify is a popular company nowadays that has an entry levell account for which you can sign up for free。

 if you just want to have like a portfolio website if you're an artist or a program or you just want to have static content that you write once and deploy these are good starting points。

 but not all of them Hoing a web app。 So this list gets even longer in all of these recommendations are essentially curated by the teaching staff。

 Sore。Opinionated， but these are perhaps the most common places you can go Amazon， Microsoft， Google。

 Cloudflare， they all have student type accounts。 So if you use your edu email address， for instance。

 or some other form of proving your status as a current student。

 you can generally sign up for discounts and free access to a lot of these same services as well without having to pay while you're just learning along the way Gi has something similar called the student developer pack and then a couple of other companies for hosting web apps that have been popular or heroroku orsell and bunches of others。

 So by web app， we mean not just HTMLtss and jascript， but maybe some Python。

 maybe some javascript on the server， maybe Ruby yet another language or any number of others when you actually need a backend。

 in addition to the frontend， maybe you need a database as well。

 this would be the place to start whether it's at the C50 hackathon or beyond And nowadays。

 this is a slide that didn't even need to exist a couple of years ago asking AI again。

 for your final projects， you are welcome and encouraged to amplifying your own productivity with AI not by having it do it。

For you， but moving away from the duck， which by design has been fairly limited and meant to be a good teacher。

 but not necessarily one that's going to be a good partner when it comes to building your final project。

 So ChatBt Cla Gemini Githubcopilot， openaiI codeex V0 are all popular tools right now that you might want to play around with the easiest of these to use perhaps if not familiar which say chattBt already would be Github copilot only because you can enable it within your cs50 code space by following our own documentation at c5 read the docs we'll tell you the sequence of steps via which you can re enableable AI now that you're allowed to for your final project and turn on all of those features that were disabled by default。

 and then there's still humans out there like remains to be seen just how popular these websites are in the years to come for better or for worse。

 But among the places that programmers and technoophiles have gone for years are Reddit stack overflow。

 server fault where there's a rich history of questions and answers that ironically all of those AIs have been trained。

Whi unfortunately means some of these might be driven out of business eventually in some sense if we're all just turning only to AI。

 but when you actually want that human component， these are still good places to go and then news。

 two of the many places you can go for news and technology， computing。

 computer science more broadly would be techcrunch is still a good one hacker news so to speak and then you might have some of your own popular choices as well and then with some bias take other classes like CS50 besides this undergraduate class has a rich history now over the past decade of creating all the more opencourseware So courses in more Python moresQL。

 a language called R cybersecurity game development and more all of those are linked at this URL here。

edxg c50 where you need not pay or sign up beyond auditing the course and all of the content is freely available。

 something for winter break for instance， if you want to dive a little more deeply into some subject for the sake of your final project。

 your professional aspirations or even just prepare for spring term and then over the coming weeks too will CS50 itself be soliciting interest and applications。

For becoming a teaching fellow or TF， a course assistant or C。

 if you would like to get all the more involved as a teacher of CS 50 next fall。

 do follow the application link that we will soon circulate via email and do stay in touch too if you just enjoy answering other people's questions or seeing what the pulse of sort of computing is this URL here is a whole bunch of C50s own communities in social media largely via which you can follow along at home in the months and years to come So a few thanks before we do one final game all together to all of the people who have been making this course possible our friends at Memorial Hall who bring us into this beautiful space and make it possible for us to have of all things a class in such a space。

 our friends at ESS who help with the audio each and every week in CS50 The restaurant Changz down the road。

 we hope you'll continue to visit our friends there Wesley Chen is a good friend of ours and the manager please tellre from C50。

 and I'm sure he'll be delighted to see you and then CS50's own team most of whom were in back there sitting next to you with cameras without whom the course。

😊，Wouldn't possible。 And， of course， the has 50 zone teaching fellows in Cas。

 just a few of whom posed here for this photo。 If I could invite you to all give everyone here a round of applause。

 My thanks to all of them。So。And then， of course， the CS50 duck should be thanked as well。

Thanks to CS50 zoneng Shiin Lu and some of our own former teaching fellows and students who have been behind the development of that their duck that you've gotten to know over these past several months。

 Allright， if Kelly could join me again on screen， the only thing between us and cake is a final game。

 namely a quiz show in which all of you can partake。

 So if you have a phone with you go ahead and take that out if not already and points your camera at this URL。

 which will open up an interface much like the one we use during our artificial intelligence lecture。

 we have prepared a sequence of 15 challenges， all of them related to Cs50 content。

 the goal here is to get as many points as you can based on correctness。

 but also just add a fun flourish speed as well。 So each question is worth 1000 points。

 But as soon as Kelly shows it on the screen， a timer will start ticking And the longer you take to buzz in with the right answer。

 the fewer points that you will garner。 So just for fun at the end of the day。

 but see if you can't challenge yourself or maybe。😊。



![](img/a745728fbc4038620ad10ac9483d4ef2_6.png)

![](img/a745728fbc4038620ad10ac9483d4ef2_7.png)

The friend next to you to see who wins next。 So here's the URL。 If you still need a scan。

Give folks a couple final seconds to scan。If you haven't quite gotten to working， that's fine。

 just play along with say the person next to you。 And if Kelly。

 we want to switch over now to the first question， here we go， Question1。

 what is the largest number in8 B unsigned binary digit can represent 256，128，255， or one。😡。

Starting strong， and keep in mind， all of these questions came from you all because we asked you recently for review questions that are now on the screen。

😡，Again， the timer is clicking and most popular answer was 255。

 which I think if we click once more will confirm， was in fact， the correct answer。

 So why is that and why is it not 256， Well， if we start counting from zero as we always have that's consuming one of the 256 possibility So the largest number that we can represent with that 8 bit and unsigned。

 which means no negative numbers involved is indeed going to be 255 T that information now always all right。

 next question from Kelly， which issue is at the center of the year 2038 problem。

 which hopefully you added to your Google calendars a few weeks back， entered your overflow。

 malicious inputs， SQL injection attacks or memory leak。😡。

Which of those is at the core of the year 2038 problem？All right。

Let's go ahead and reveal the number one answer with 92% of you saying integer overflow is， in fact。

 correct， because we're still in the habit of using 32 B integers to keep track of time from the so-called epoch。

 which was January 1，1970 on unfortunately， we humans aren't great at sort of planning ahead。

 And so we're going to run out of permutations of 32 B by a certain date in the year 2038。

 unless everyone upgrades their computers to 64 B counters， which thankfully。

 most every piece of modern hardware nowadays is using already your max your PCs in your phones。

 So hopefully this will be really a nonevent。 but hopefully you'll think of us in Cs 50 in you know。

10 plus years when your Google calendar reminder goes off。 Question3。

 which of the following is not a step of compiling。 Liing preprocessing， assembling or interpreting。

A bit more of a challenge， which is these is not a step of compiling。All right。

 almost 200 responses coming in。All right， why don't we go ahead and reveal？

The most popular answer with 54% of you saying interpreting is in fact correct。

 recall that we talked about compiling， compiling itself is just one of several steps。

 there is in fact the preprocessing step which takes care of any of the hash symbols in C that start with hash and hash to and the like that's preprocessing。

 there was then assembly or that was then compileiling。

 which actually compiled your code into assembly code。

 there was then the assemblymbler which would actually take it down further to machine code。

 and then linking。😡，29， this is for 29% of you， the linking step recall was taking your zeros and ones and combining them with say。

 C S 50s libraries， zeros and ones and maybe the standard I O libraries。

 zeros and ones linking them all together to give you one executable program like hello itself。

 Allright， next question。What does a pointer store， the name of a variable。

 the memory addresses of a value， the size of a value or the value of a variable。Think for a moment。

What does a pointer store？All right， about 200 responses in。 and yes。

 the memory address of a variable with 96% of you confirming as much， that is correct， question5。😊。

What is the running time of what is the running time of linear search， Big O of1， Big O of n。

 Big O of n squared or big O of n log n。Linear search， running time。

And recallca that with something like search， you could get lucky。😡。

But if big O is the upper bound on our running time， you might not。

 You might hit the end of the list that you're searching。

 And so the running time of linear search is， of course。Big O of。And it might be omega of one。

 but not big O of one， at least if we're considering what the worst case scenarios might be。

 All right， on to question 6， what data structure follows the first in， first out principle， A queue。

 a linked list， a stack or a hash table。First in， first out， Aka FiIFO。😡，Which of these is FiIFO？

Alright， first in， first out， is， in fact， a queue， as you would hope。

 if you're getting in line for a restaurant， for a store。

 you'd hope that if you're the first one in line， you're gonna be the first one out equitably speaking。

 And so it is， in fact， a queue， the opposite of that， in some sense。

 then would have been a stack whereby when you think about the cafeteria trays。

 the sort of first one in is actually the last one out。 So LiFO instead for a stack。 Allright， Que 7。

 which operator returns the memory address of a variable。 an asterisk， a dollar sign。

 an ampersand or a hyphen and a greater than sign。😊，Presumably in sea。

Which returns the memory address？😡，Of a variable。All right， let's see what everyone thinks。

So the most popular and correct answer is the ampersand。 This is the address of operator。

 The asterisk recall in most contexts is the opposite of that。

 that's the dereference operators actually go to an address。 This is not a thing in C， this though。

 is similar in spirit to a combination of the star operator and the dot operator。

 which means to dereference and follow a pointer to something inside of a struct typically。

 All right， question 8， which SQL command is used to remove duplicate rows from a result set。

 remove unique distinct or clean。😡，We didn't spend a huge amount of time on these keywords。

But only one of them applies here。 A result set is just the answers that you get back when doing your select。

And if you want to filter out duplicates， you can in fact， say。😡，Distinct is correct。

 Uni is also a keyword in SQL， but that is when you want to define in your schema that a columns values are going to be unique like an email address column。

 instead， distinct is how you filter out duplicates in your select。 All right， Question 9。

 We' past the halfway mark。 What does an H TTP code of 4，18 signify not found。

 I'm a teapot forbidden， unauthorized。😡，418。This too， if you know this one moving forward。

 you'll be considered among the。CS。Elite。Answers are coming in a little slower。

 but I'm a teapot is correct， which is not actually a thing or useful technology。 It was， in fact。

 in April Fo's joke years ago， where a bunch of computer scientists got together in a room and wrote out an entire specification for what it means for a server to return4。

18， I'm a teapot。 Allright， number 10。😊，Yeah。这。Where does Maoc dynamically allocate memory from。

 the heap， the stack， global variables， or assembly？😡，All right。The correct answer here is， in fact。

 heap。 These are interesting because we accidentally showed the correct answer a moment ago。

 So heap is， in fact， correct。 That's the sort of top part of the memory。 Even though top and bottom。

 make no actual technical sense， it's just our artist rendition thereof the stack recall is what is used when functions are being called every time a function is called。

 it gets a socalled frame on the stack。 That's where your local variables and your arguments get put。

 But if in C， you use malloc， it does， in fact， end up on the heap。

 I'm gonna stand here just in case the next answer is get revealed。Okay， go ahead， okay。In C。

 if you allocate memory with malloc， but forget to call free， what problem can occur， a memory leak。

 segmentation fault， stack overflow or all of the above。😡，If you allocate memory with malloc。

 but forget to call free， what problem can occur。Alright， most popular answer is， in fact。

 memory leak， which is correct。 You could imagine scenarios in which you also get a segmentation fault and or a stack overflow。

 But those aren't direct consequences of not calling free。

 that's generally the consequence of using too much memory， for instance， or in this case。

 doing something wrong with your memory。 So interrelated。 Yes。

 but in terms of not calling free for each malloc， this is what's going to happen by definition。

 Al right， well done there。 Next question， which is 12。😊。

What does this domain name give the webage of safetychool。org， is it Harvard Universityrs。

 is it Princeton University， is it Yale University or Columbia University？😡，Alright。

 recall that this was in the context of our H TP redirections。 Yes， interesting。 Yes， in fact。

 Yale University， some alum has been paying like $10 a year for like 20 years for this joke。

 Sa school do org。 if you visit it returns an H TP 3，0，1， H TP header。

 which says the location of it is， in fact， Yale dot E D U。 Alright，s13，3 to go。

 What is the purpose of DN S  to encrypt data sent over the dark web。😊。

To find the nearest coffee shop for you to protect your location against hackers or to translate domain names into I P addresses。

Whathi is the purpose of DNS？😡，If helpful， domain， name， system。Al right， abouted at the 200 mark。

 And the correct answer is indeed， domain names into I addresses。

 That is a server that is on your home network， on your ISP's network， on your campuses network。

 your corporate network that just answers questions like that for you。 Allright。

 second to last question。 Which of the following is not a built in SQL feature to tackle race conditions。

 begin transaction， commit， rollback or enroll。We talked ever so briefly about this in the context of ending up with too much milk。

 recall。😡，And the correct answer is。Indeed， enroll， all three of those。

 even though you didn't have to use them for problem sets 7 or 9 are indeed features of SQL。

 but enroll is not a thing。 Alright， and the very last question。

 Try to answer this as quickly as you can。 What does Professor Maland say at the beginning of every C S 50 lecture。

 Welcome to Car's computer science class。 Hello， everyone， ready to code。 Alright， this is CS S 50。😊。

Or let's get started with some programming。All of these questions were in fact， written by you all。😡。

All right， and the correct answer I'm pretty sure with 98% of you saying so is all right。

 this is CS50 and all right， this was CS50， cake is now served。



![](img/a745728fbc4038620ad10ac9483d4ef2_9.png)

![](img/a745728fbc4038620ad10ac9483d4ef2_10.png)
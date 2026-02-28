# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P3：-03-.Lecture 3_ Editors (vim) (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

啊，O。Cool so welcome to the third lecture of the missing semester of your CS education today we're going to be talking about text editors this is a topic that I really like。

 I think it's one of the most valuable topics that we're teaching in this class because as programmers you spend so much of your time editing text editing programs that if you invest time into making yourself more efficient at doing this you'll save a ton of time probably hundreds of hours over the course of your undergrad or over the course of your career。

😊，So。Text editors are a little bit different than other programs you might use to edit。

 say things like English prose， because programming is different than writing English prose when you're programming。

 you spend a lot of time reading what you've written。

 you spend a lot of time navigating around a buffer and you spend a lot of time making little edits to code all over the place rather than just writing in a long stream like you do when you're writing an essay or something。

 And so it makes sense that they're different programs for these different purposes right So you have things like Microsoft Word for writing essays and things like Vim and Emax and VS code and sublime for writing code。

嗯。So the way you learn a text editor and become really good at it is you start with a tutorial。

 and so that's basically going to be the function of today's lecture plus the exercises we've given you。

And then after the tutorial you need to stick with the editor for all your editing tasks and when you're learning a sophisticated tool。

 so today we're going to teach you VIm which is one powerful editor that a lot of programmers use when you're learning sets a sophisticated tool it may be the case that initially switching to this tool slows you down a little bit when you're programming but stick with it because I'd say that in about 20 hours of programming using a new editor you'll be back to the same speed at which you programmed using your old tool and then after that the benefits will start and you'll get faster and faster as you learn more。

With these sophisticated programs like ViIM， it takes not way too long to learn the basics。

 but a lifetime to master。Throughout the time you're using this tool。

 make sure you look things up as you go if you ever get to a point where you're like。

 oh this is a really inefficient way of doing things， I there a better way。

 The answer is almost always yes because these text editors were written by programmers for programmers and so of course like the people who wrote these tools ran into the same kinds of issues and fix them so that you don't need to deal with these anymore and so yeah。

 as you're learning， make sure you look things up as you go either use Google or feel free to send us emails if you have questions or come to office hours and we'll help you figure out how to do things really fast。

😊，So as far as which editor to learn in previous iterations of this class。

 we actually avoided teaching a specific editor because we didn't want to enforce our opinions on you guys。

 but we actually think that it's really useful to teach you how to use one particular tool and use it well and so people have really strong opinions about editors and you can see the course notes for more links on this topic。

Looking at which editors have been popular over the years， Stack Overflow。

 I'm sure you've all heard of that， does a survey every year asking developers various questions and one thing they ask is which text editor do you use and it seems to be that currently the most popular kind of graphical editor is VS code and the most popular editor that is based in a command line interface is VIM and so we're going to be teaching you VIm。

And there are a couple reasons for this。 One is that all the instructors， so me。

 John and Jose use ViIm as our primary editor， and we've been doing this for many years。

 and we've been very happy with it。 And we think that there are a lot of interesting ideas behind ViIm。

 So even if you don't end up using this particular tool in the long term。

 I think it's valuable to learn these ideas。 And also a lot of tools have actually been really excited about the ideas in Vm。

 And so they support a vim emulation mode。😊，For example， VS code。

 what's apparently the most popular editor in use today， supports Vm bindings。

 and this Vm emulation mode as of now has like 1。4 million downloads。

And as you'll see over the course of this lecture， a lot of different tools like including your shell。

 including things like the Python， Repple and like Jupiter notebook and all sorts of other things。

 even your web browser can support the emulation mode and so yeah we're going to be teaching you this really neat tool today。

And in this lecture we can't really cover all of them right it's a very powerful tool but our goal is to teach you the core philosophy of them like the really neat ideas behind it and then in addition to that some of the basics like how do you open a file close a file。

 navigate around a file make edits and things like that and you may not remember every single little detail from this lecture because we're going to go pretty fast through some of the material but it's all in the lecture notes and then the exercises actually give you links to some tutorials and things so I highly recommend that you actually go through all the exercises at least the non-advanced exercises。

😊，Any questions so far？Great。Okay， so one of the really cool ideas behind Vim is that VIm is a modal editor。

 What does this mean modal comes from the word mode。

 and this means that ViIm has multiple operating modes。

 And this is kind of developed from the idea that when you're programming。

 they're oftentime're doing different types of things like sometimes you're reading code。

 sometimes you're making small edits to code like you're finding a particular point like changing a little thing somewhere。

 Sometimes you're just writing a lot of code in one go like suppose you're just writing a function from scratch。

 And so VIm has different operating modes for doing these different types of things。😊。

And so I'm actually going to write this down on the blackboard。

 So we'll have a useful thing to refer to later。 So when you start Vm up。

It starts up in what's called normal mode。 And in this mode。

 all the different key combinations behave in one way。

 And then there are different key combinations that switch you between normal mode and other modes。

 which change the meaning of different keys， so。For the most part。

 you'll be spending most of your time in Vm in normal mode or what is called insert mode。

And to go to insert mode， you press the key I for normal mode and to go from insert mode back to normal mode。

 you press the escape key。A little note on notation because we'll need this later in the notation I'm going to be using in this lecture and what's also in the lecture notes and what Vim uses to give you feedback。

 they have a couple different ways of talking about different keys。

 So when they're talking about bare keys like just the I key on your keyboard。

 they'll just say I but for a different key combinations like when you press control and something like say control V it's notated in one of like approximately three ways。

 one way that can be notated， it's a carrot and then the control character。 So this is control V。

 another way this might be written， I think we've written it this way in part of our lecture notes it' control V this is probably the one you're more used to seeing and then in some parts of vim this is written as angle bracket C dash V closed angle bracket So there's a little bit of notation that will be useful later。

So， yeah， Vim has a couple different modes where normal mode is designed for navigating around a file。

 reading things， going from file to file， things like that。

 And then insert mode is where you type in text。 So most keys that you press here will just go into your text buffer。

 whereas keys that you press here are not being put into the buffer and instead of use for things like navigation or making edits。

嗯。And actually， the picture is a little bit more complicated than this。

 There are a whole bunch of other modes。 And I'm just going to write them down here because we'll have them here to refer to later。

 And so Vim also has a replace mode。For rather than inserting text and kind of pushing what's ahead of it forward。

 it'll overwrite text， and then it has a bunch of different modes for selection。

So it has a mode called visual mode， and then it has visual line and visual block。

This one is entered via the R key。 This one was entered via the V key。

 This one is entered via shift V， and this one is entered via control V。

And then there's the command line mode。Which is entered via the colon key。Okay。

 so now that we have that on the board to refer to later。嗯。好。We can actually try some of this out。

Alright， so one thing we noticed looking at that picture is that to go from normal mode to any of the other modes。

 we press some key， but to go from any of the other modes back to normal mode where we spend a lot of our time。

 we use the escape key on our keyboard。 So for this reason。

 since you end up pressing the escape key a lot when using ViIm。

 a lot of programmers rebind one of the keys on their keyboard to be escape because it's really inconvenient to reach out with your left pink key to press that tiny little escape key in the corner of your keyboard And so a lot of people use the caps lock key instead。

 So it's right there in the home row。😊，And we have some links in the lecture notes for how you can do this key rebinding。

Okay， so now that we've talked about kind one of the core ideas of Vim， the idea of modal editing。

 we can talk about some of the basics like how do you open up this text editor。

 how do you open files， save files， and things like that。And so this is a command line based program。

 although there are some graphical variants。 And the way you start this program is by running Vm。

One thing you might notice is that in the bottom left corner of my screen。

 you actually saw what I just typed。 This will be useful later in this lecture where I'm actually typing in commands for ViIm and I'll be saying what I'm ping。

 but you'll also see it on the screen。 So if I press control C， see， it says control C over there。

Is that text big enough for everybody to read？Great。Okay。

 so the way we open VIm is just by running the program VIm on our command line。

 and this comes pre-installed on most systems。 and if you don't have it。

 you can install it using your package manager。VIm can also take an argument if we want to use it to edit a particular file instead of just opening up the program and then later opening a file。

 so for example， I have a file in this directory， this is actually the lecture notes for this lecture so I can do vim editoritors。

 MD and pressent and then boom， Vm is started。And then in this lecture。

 I'm not running Vim in the completely stock configuration。

 I've configured a couple of things that make it behave a little bit nicer by default。

 little things like having line numbers on the left or having some more status information on the bottom。

 And if you want to start with this default configuration。

 we have a link to this in the lecture notes。 so you can get a slightly more sane configurationfid by default。

嗯。So once you've opened Vim， what do you do。 Well， as I said earlier， Vim starts in normal mode。

 So if I just start typing letters like say I type X， it didn't insert X into the buffer。

 You can see the cursor up in the top left。 It actually deleted one of the characters。

 That's because I'm in normal mode， not insert mode， so。

Insert mode is basically what you're used to with all the other text editors you've used in the past where there's a cursor somewhere and you press the character。

 and it just goes into your buffer。Instead in vim， you start a normal mode and you can press I to go into insert mode。

 So see if I've pressed I。 And then in the bottom left， notice that it says dash， dash insert。

The bottom left always tells you what mode you're in unless it's normal mode。

 in which case it's blank。 And now that I'm in insert mode， if I press the X character， for example。

 see， it just gets inserted into my text buffer。 and I can backspace over and type other stuff。

 And now my text editor kind of behaves like you'd expect any other program to behave。

So from this point， how do I go back to normal mode if I want to stop inserting characters。Yes。

 exactly。 I press escape， and that's the symbol my key visualizer uses for escape。

 so just be aware of that。嗯。And then Vim has this idea that using the mouse is inefficient。

 Like your hands are on the keyboard， moving your hand over to the mouse takes a lot of time， right。

 Like， you don't want to waste those。ACoup of milliseconds while you're programming。

 like in the middle of things。 So instead。All vim functionality can be accessed just through the keyboard。

 And so all sorts of things you might be used to doing like opening files by going like file。

 open or file save or things like that are instead of access through the keyboard。

 And how is that done， That's done through one of the other vim modes that are on the board over there。

 in particular， through command line mode。So if you're in normal mode and you press the colon key。

 you'll notice that the cursor， I guess my visualizer is covering the thing right now。

 but it's gone the cursor jumps to the bottom， the bottom left。 And it shows that colon I just typed。

 And now I can type in a command。 So you can think of this almost like the command shell that we've been talking about over the last few days。

 except this is Vims command shell。 So you give vim commands here instead of shell commands。

And there are a bunch of built in commands that do all the things that you're used to。 Like。

 for example， one command that you might want to know is how to quit this editor。

 You might notice that if you're normal mode， I can press escape to go back command line mode to normal mode。

 And I press C C。Unlike what happens with a lot of programs， this doesn't quit BM。

 so how do I quit Vim， I can press colon and then go into command line mode。

 and then I can type in the command quit Q U IT。You'll see that me should move this over to the middle or something。

Ces says colon and quit， and I press enter， and it quits spin。



![](img/ddd580325caf3a55db2aa1961bd00860_1.png)

And I can open Vm up again， there's actually a short form for this command， just Col and Q。

And that'll do the same thing。And there are a bunch of other useful commands like this。

 So some other handy wants to know are how do you save a file。

 so suppose I make some edits here like hello world。 So I pressed I to go into insert mode。

Or let let me redo that。 I press I to go into insert mode right now。 I can use the down arrow tip。

Yeah。I think I have slightly， I should fix the。 Can you fix the convey， actually， John。Oh。

Never mind that。I suppose I go down to this line。And I press I to go into insert mode and type in some text and then press escape to go back to normal mode。

 Now， how do I actually save this file， Well， there's another command for that。

 So colon to go into command mode。 And then I can type W。And press enter， W stands for right。

 and it says in the bottom， editors， do MD， whatever， blah， blah， written。

 And so this means it saved the file。 And so now if I call in queue to quit and open the same file again。

 you'll see that the changes have been persisted。

![](img/ddd580325caf3a55db2aa1961bd00860_3.png)

There are a couple other so there's a ton of different viIM commands that are useful for different reasons。

 but I'll just explain a couple more to you now。 One command that's really useful is help Col help and you can do colon help and then type in a particular key or a particular command and get help for that keystroke or that command。

 So if I want to know what colon if I want to know what colon W does， I can do colon colon W。

And that'll give me the documentation。On Col W or Col Wright。If I do Col in Q。

 it'll close this window and bring me back to where I was before。

And notice that colon W is different from colon help W。Because the W key is。

The W that like when you're normal mode and press W。

 what happens is just the W key here without the colon。 And if I look for help for colon W。

 that's the help for the W command。嗯。So。Now， you basically have。

The bare fundamentals needed to use Vim， right， You can open the editor。

Use it to edit a particular file。 press I to go into insert mode and type in some text。

 press escape to go back to normal mode， and then colon W to save your changes。 Col and W to quit。

 So like already， you have the bare fundamentals necessary to edit files using them albeit somewhat inefficiently。

 So any questions so far。这样的吧。こく大夫。Yeah， so the question is。

 what's the benefit of the of the normal mode。 And we'll talk about that in more detail in like  five minutes。

 but in short。Insert mode is just for typing in text。 So I'm in insert mode I can type in text。

 But when I'm programming， I actually spend a lot of time moving around my file making small little changes。

 So I go here and like， oh maybe， I want to change this H TP link to an H H T，P， S to H TP。😊。

I can make like small point edits， things like that in normal mode。

 And we'll see a whole lot more of that in about 5 minutes。 Good question。 Any other questions。Okay。

 cool， so moving along。嗯。One other thing that's kind of useful to know， I think。Is。At a high level。

 ViIm's model of buffers versus Windows versus tabs。

 So it's probably the case that whatever program you were using before。

 like sublime text or VS code or whatever， you could open multiple files in it right and you could probably have multiple tabs open and have multiple windows open of your editor。

 So Vim also has a notion of those different things。

 but its models a little bit different than most other programs。

So Vim maintains a set of open buffers。 That's the word it uses for open files。

 And so it has a set of open files。 and then kind of separately from that。

 you can have a number of tabs and tabs can have windows。

 the kind of weird thing which makes vi a little bit different than the program you probably use in the past is that there isn't necessarily a one to one correspondence between buffers and windows。

 So one thing I can do， for example here， and we'll show you the key combinations and stuff for this later。

 but one thing you can do is create two different window。

 So I have one window up here and then one window down here and notice that the same files open in both windows。

 So if I make some edits over here， they actually happen in the bottom window as well because it's the same buffer that's open in both windows。

 And this is kind of useful for say looking at two different parts of a single file at the same time。

 like they want to be able to look at the top of a file。

 say add an import to your program while you're down below working somewhere else。



![](img/ddd580325caf3a55db2aa1961bd00860_5.png)

![](img/ddd580325caf3a55db2aa1961bd00860_6.png)

So this is just one helpful thing to keep in mind that Vi has this idea of。

There are a number of tabs。And each tab has some number of windows。 and then each window has。

A correspondorreponds to some buffer， but a particular buffer can be open in zero or more windows at a time。

Just one thing that confused me when I was initially learning them。

 So I want to explain that early on。And then。The colon Q command， which we talked about earlier。

 is not exactly quit。 It's kind of close the current window。

 And then when there are no more open windows， V will quit。 So here， if I do colon Q。

 it'll only close the window， I think， on the top here， because that's the  one I was in。

 And now the remaining window becomes full screen。 I can do colon Q again to close this。

 now I'm in the second tab that I'd open。 And if I do colon Q a final time。 Okay， now Vim exits。



![](img/ddd580325caf3a55db2aa1961bd00860_8.png)

And if you don't want to press colon Q way too many times。 Okay， so here I have three split windows。

 If I do colon Q A for quit all， it closes all the open windows。



![](img/ddd580325caf3a55db2aa1961bd00860_10.png)

![](img/ddd580325caf3a55db2aa1961bd00860_11.png)

All right， so now to answer your question of what is normal mode actually for。

 this is another really cool idea in VIM， and I think this is actually the most fundamentally interesting idea of this program。

It's that like you're all programmers。 you like programming。

VIm has this idea that ViIm's normal mode， like Vim's interface itself， is a programming language。

And let me repeat that。 That's like a kind of fundamentally interesting idea。

 The interface is a programming language。What does that mean。

 It means that different key combinations have different effects。

 And once you learn the different effects， you can actually combine them together。

 just like in a programming language， you can learn different functions and stuff and then glue them all together to make an interesting program in the same way。

 Once you learn Vims different movement and editing commands and things like that。

 you can talk to Vim by programming vim through its interface。😊，And once this becomes muscle memory。

 you can basically edit files at the speed at which you think。 Like， at least for me。

 I don't think I've been able to do this with any other text editor that I've used in the past。

 But this one gets pretty close。So let's dig into how exactly normal mode works。

 So you can try to follow along with this， like open up some random file in Vm and follow some of the key combinations I type in。

 So one basic thing that you might want to do is just navigate around a buffer。

 like move your cursor up down left right。 And so the way you do that in Vm is using the H JK L keys。

 not the arrow keys。 though they do work by default。

 try to avoid them because you don't want to have to move your hand all the way over to the arrow keys。

 like there's a ton of time you're wasting right， H JK's right on the home row。 And so J moves down。

 K moves up H moves left and L moves right。And this may seem a little unintuitive now there was some historical reason for it。

 like the keyboard， the original VI developer used had the HJKL keys like labeled and arranged in a way that made this more reasonable。

 but this will very soon become muscle memory。 So this is the basic way you can move your cursor around while in normal mode。

Now， what else can you do， Well， if we had to move around files like this， it'll be really slow。

 We don't have to want to have to hold down these keys and like。

 wait for a long time for them to do its thing。 And so there are all these other different key combinations for doing different movements。

Also， by the way， this is all in the lecture notes。

 So you don't need to memorize every single key in its meeting right now。

YouJust try to understand the overall idea that ViImMSs interfaces a programming language。

So another thing you can do is press the W key。 This moves the cursor forward by one word。

 and then similarly， the B key moves the cursor backward by one word。

So this allows slightly more efficient movement within the line。

There's also the E key for moving to the end of a word。 I'm going to move this over a little bit。

So if I'm here， for example， when I press the E key， it'll go to the end of this word。

 end of this word， end of the next word， and so on。You can also move by whole line。

 So0 moves to the beginning of a line， dollar sign moves to the end of a line。

 and the carrot key moves to the first non empty character on the line。 So let me find one of those。

 for example。So here， if I'm on my cursors right here， if I press zero。

 my cursor goess to the beginning of the line， dollar sign， end of the current line。

 and if I press carrot， where like on what character will the cursor end up， can anybody guess us？

So carrot goes to the first non empty character on a line。Kind of like Reg X carrot。第。Yeah， exactly。

 It goes to this dash。Let's talk about some more movement commands。

 There's ways to scroll up and down in a buffer， so control you。Goes up。And control D scroll down。

So this is better than holding down the K or J keys， for example。

 this is a lot slower than moving by entire pages， C D and control U。

There's also ways to move by the entire buffer。 So capital G moves all the way down。

 G G moves all the way up。Some of these movement keys are mnemonic。

 So they're like a little bit easier to remember for that reason， right。

 like W is word B is beginning of word E is end of word。 those all seem pretty logical。

0 carroat and dollar are kind of inspired from rex。 So those make a little bit of sense。

 There's some other ones that like don't necessarily make way too much sense。

 but there are only so many keys on your keyboard。 So what are you going to do。 For example。

 the L key moves your cursor to the lowest line that's shown on the screen。L for lowest makes sense。

 M for middle， and then H for highest， I guess。嗯。And there are a whole bunch of other interesting movements like this。

 So we're obviously not going to be able to cover all of them right now。

 but you'll be able to go through them in the vim tutor exercise。

 which is exercise number one for this lecture。嗯。Some other ones I want to talk about now。

Maybe I'll talk about one more。 There's another movement called find。 This is also kind of useful。

 Suppose I'm on this line。 And I want to jump to the first character that's equal to something like I want to jump to the first O。

 I can press F O， and my cursor moves to the first O。 I've like found O， I can do F W。

 and it'll move to the first W， which I think is right here。 F C find the first C。😊。

I can also do the same thing。 but backwards。 if I do capital F W， I can find the W that's before it。

 capital F S， find the S that's before that。 And then there's a variant of F for find T for2。

 So I can jump2 O。 And it jumps like until it's found O， but not on top of it right before it。

 And capital T， say T jumps backwards to the T， except not all the way on top of it one character before。

And so you can already see that idea I talked about of Vim is a programming language。

 you can compose these commands。 F and T are fine in two。

 and you can say find a particular character or jump to a particular character。

So those are a couple of movement commands。 So any questions about those so far。So this is yeah。

 question or no， okay。Cool， so those are big movement commands。

 This is how you can navigate around a file quickly in normal mode。Now。

 another category of useful commands are editing commands。 So one we kind of already talked about。

 which is the I command for moving from normal mode to insert mode where you can start just writing text。

 So suppose I go up here。 and I press I now I can type in whatever text I want。 Hello world enter。

 move this back。😊，And then press escape to go back to normal mode。

 and I've made a change to my buffer。 But there are a whole bunch of other commands for making efficient edits that make sense for when you're dealing with programming languages。

 So one useful command that I accidentally used earlier before teaching you about it is the O command。

 So suppose my cursorors like over here。 And if I press O from normal mode。

 What it does is it opens a new line below where my cursor is。That's what O stands for。

 And so it creates a new line and puts me into insert mode。 And I can start typing in some text。

Press escape and go back to normal mode。And then just like the O command。

 there's a capital O command。 So if I'm here and I do capital O。

It puts me into an insert mode above where I currently am。

There's another VIm command for deleting things， so suppose my cursor is like on top of this word right here。

And I press the D key D for delete。 Oh， nothing happens。

 Turns out that the D key needs to be combined with a movement command。 So remember。

 we just talked about different movement commands like H JKL and like word and backward word and things like that。

 So I press D。ops I press D。 and I can press W。 And it's deleted a word。So let me undo that。

 undo and Vm is just you for undo。So notice my cursors right here。 If I do D W， it's deleted a word。

 I can move around and then delete another word。 Supp I'm。Keeps getting in the way。

 Suppose I'm like somewhere in the middle of a word， and I want to delete to the end of a word。

 Any guesses for what combination of keys I'd use for that。D and what？D E， exactly。

 delete to the end of the word。Another useful editing command is the C command。 C stands for change。

 So change is really similar to delete， except change puts you in insert mode because like。

 I want to delete a thing， but change it to something else。 So if I'm here and I do C， E。

 it's like change to the end of the word。 and it。Get rid of the contents until the end of the word and notice it put me in insert mode to now whatever characters I type go into the buffer。

If I press escape， I go back into normal mode。And so C And D are analogs。

 they both take motions as arguments， and they will either delete that motion or change that motion。

So， for example， if you press the。See there's also this pattern that if you press a particular editing key twice。

 it'll have that effect on the given line。 So if I press D D that deletes the line。 If I press C。

 that deletes the given line， but puts me in insert mode so I can replace it with some other line。

I'll cover a couple other editing commands because then later we'll see how all of these things interact together。

 So another useful one is the X command。 So suppose my cursorors over some particular character。

 If I press X， it just deletes that character。There's another command called R。

 If I'm over a particular character and I press R， it takes another character as an argument。

 and it replaces that particular character with some other character。嗯。

And I'll cover cover a couple more editing commands。 So I think one I talked about a moment ago。

 but of course， you can undo changes you've made in Vm。

 and the way you do that is by pressing you while youre normal mode。

 So you for undo is pretty easy to remember。 So I press you a whole bunch of times is undone all the changes I've made。

And then the opposite of undo is， of course， redo， and the binding for that in Vm is control R。嗯。

Alright， one other editing command I'm going to talk about is copy and paste because oh。

 yes question。Unduelay。Everything had done。Or is it done the last。That's that's a great question。

 So the question is， does undo undo everything you've done since you've gone into insert mode or just the last character。

 It's it's actually a little bit more complicated than that。

 undo does like undoes the last change you've made。

 So if you went into insert mode and typed in some stuff and went back into normal mode and then press U for undo。

 it'll undo all you've done in insert mode。 But if you'd done some other type of editing command。

 like say I press X to delete a character， if I do U for undo。

 it'll just undo that change that that editing command made。😊，Does that answer the question。

Any other questions？Cool， so I'll talk about copy and paste as well because that's a popular one。

 The Y command stands for copying and the P command stands for pasting。 Y for copy because yank。

 like that's the word that's theology terminology that BiIm uses for copying。

And these commands are y also takes motion as an argument。 So if I do like why。

 why it copies the current line and an the effect press P for paste。

 notice that now these two lines are identical because I've just pasted a line below U for undo。

But if I do something like YW， it's copied the word and then I can do P。

 and it just pasted that word again right where my cursor was。One useful thing。

 especially in the context of copy and paste， is to be able to select a block of stuff and copy it。

 right， Like this is probably how you used copy and paste in whatever editor you were using before。

And so that's where we get into the visual modes。 So these are another set of modes that are all related to each other。

 and that can be reached from normal mode， and they're used for selecting chunks of text。

 So one mode is just regular visual mode。 You can enter that by pressing V。

 And then once you're in this mode， you can use most of the regular normal mode commands to move your point around。

 And select everything in between。 So I can use like HJKL just to move the cursor or I can use W to move by words or different things like that。

 And it will select a block of text。😊，And once I've selected this block of text。

 there are a whole bunch of different types of useful things you could do with it。

 One of the most popular things to do is copying this。 So once I've selected， I can do why to copy。

 and it puts me back into normal mode。 And now it's copied this to the past buffer。

 And then if I go somewhere else and press P， it pasts in that whole chunk of text I copied。

And then similar to visual mode， which selects kind of a contiguous stream of text。

 there's visual line mode so that can be reached by pressing capital V。

 and that selects whole lines at a time。 And then there's visual block mode。

 which can be selected by pressing control V And that can select rectangular blocks of text。

 So this is something your old editor couldn't do。Alright。

 so there's a lot more vim editing commands to learn。

 There's lots of like really weird and fancy things。 Like， for example。

 the Tilde command changes the case of the character or the selection that you've currently selected。

 So， for example， I can take this like visual studio code and flip the case on the whole thing by selecting it and pressing Tilda。

😊，And there's a whole bunch of other things like that。 They get more and more esoteric as you go。

 So we're not going to cover all of those， but you'll get to those in the exercises。

So those are vim editing commands， and a lot of them can be composed with movement commands。

 So any questions about either of those so far。Cool。

 so moving along another category of things of commands that are mostly relevant to normal mode are counts。

 so you can give them a number to do a particular thing some number of times。

 So suppose my cursor is here and I want to move down like one，2，3， four lines。

One way I can do that is by pressing J four times， go down four times， KK K K goes up four times。

But rather than pressing a particular key again and again， I can use account。 So if I press 4 J。

 it does J  four times。 Bms interfaces a programming language。 If I do 4K， it moves up four times。

 If I'm here and I press V to go into visual mode。 Okay。

 so I can move my cursor around and select blocks of text。

 I can do like E E E to select a couple of words。 but I could also go back here。

V for visual mode and press 3E to select like three ends of words forward。And then， of course。

 these can also be combined with editing commands。 So like， suppose I want to delete7 words。

 I can do that by moving my cursor somewhere and doing 7 D W，7 delete words。

And so this is particularly useful for things like suppose my cursor somewhere on the screen and I'm looking somewhere else on the screen and I want my cursor to go to that particular line。

 Notice that I've set up relative line numbering on the left。

 So wherever my cursor is it shows the current line number。

 but everywhere else is's just the offset from where I am。 Now suppose my cursor is here。

 But I want to move down to the like Microsoft word down here。 So that's eight lines down。

 So what combination of keys what I press to do that。 Like what's the most efficient way Yeah。

 exactly， let's try that out 8 J and my cursor move down to this line。Okay。

 and then one final category of key meanings in Vm is something called modifiers。

 So we have so far movement edits counts。 and then finally we have modifiers。

 So modifiers kind of change the meaning of a movement command a little bit and a couple modifiers that are especially useful are the A and I modifiers。

 So A stands for like around and I stands for inside。And to see where this is really useful。

 I can move my cursor to somewhere like here， for example。

 So hopefully most of you are familiar with markdown syntax。 And if not， it doesn't matter too much。

 This is a link in markdown。 It's a text surrounded in square brackets。

 and then the link in parentheses。 Suppose my cursors inside here。

 And I want to change the text corresponding to this link。Well。

 one way I could do that is like move back here with B and like 2 DW and then I to go into insert mode。

 that's one of the many ways I can make this change。

 And now I can type in whatever other thing I want。You to undo， you to undo。

Another way I could have done that is change two words， C to W， and then type in some other text。

But one final way I could do the same change is using these modifier commands to talk about how I want to interact with these different types of grouping things like parentheses and square brackets。

 So one final way of doing this is change inside square brackets， C I bracket。

 and that puts me into insert mode after deleting the contents that are inside the brackets。

So do you see how we can take all these different ingredients。

 Like we talked about change and we could combine that with different movement commands。

 We talked about inside how it's a modifier。 and then we talked about。

 we didn't talk about parentheses。 But if your cursor is hovering over a different different types of grouping things like parentheses or square brackets。

 you can press the percent movement key to jump back and forth between matching parentheses。

If I go over here and I do DI。Prenheses， I can delete the contents inside these parentheses。

And so those are vim modifiers。 I guess talked about I， but we didn't talk about a。 If I do D。

 A parentheses that deletes a whole like parentthesized group， including the parentheses。

 So I is inside。 A is around or including。Alright， so those are basically the different categories of things you can combine together when interacting with Vim's interface。

 So any questions about that or the overall idea of this interface being a programming language。Cool。

 so。Let's do a quick demo to kind of demonstrate the power of this editor。

 and it will kind of help us see how。This tool can work really fast and kind of match the speed at which we think。

So over here is a very broken FizzBuzz implementation that doesn't actually print anything。

 Hopefully most of you have heard of FizzBuzz If not I'll explain it super briefly。

 FizBuzz is a programming exercise where you print the numbers one through n。

 but when the number is divisible by three you print Fiz when it's divisible by5 you print Buzz and when it's divisible by both three and5。

 you print fizzBuzz and if none of those apply you just print the number so you should print like1。

2 fiz4 buzzuzz and so on。 but if I run this program。



![](img/ddd580325caf3a55db2aa1961bd00860_13.png)

It doesn't print anything。

![](img/ddd580325caf3a55db2aa1961bd00860_15.png)

Here I have them on the left and just a terminal on the right。Okay。

 so there's a bunch of issues with this。 One is that main is never called。

 So let's start off with fixing that so。Here's how I would make this change and notice how few keystrokes this requires。

Capital G means go to the bottom of the file。O opens a new line below。

 and now I can just type in stuff。 So I'm in insert mode。



![](img/ddd580325caf3a55db2aa1961bd00860_17.png)

Okay， so I've typed in whatever change I want to make， escape to go back to normal mode。

 if I do colon W， so command mode right。And I go back here， okay。

 now at least my program prints something when I run it。

Another issue with this program is that it starts at zero instead of one。 So let's go fix that。

So I want to go over to this range， whoops， this range thing。

 and it shouldn't be going from0 to limit。 It should be going from one to limit plus one。One command。

 which I didn't show you about is how you search and Bm。 So you've press forward slash。



![](img/ddd580325caf3a55db2aa1961bd00860_19.png)

BI need to close this and restart it。 If you press forward slash， it starts search。

 So if I type in range enter， my cursor goes from wherever it was before to the first instance of range it found。

 So it's a really efficient way of moving where I want to move。 I can press W。

 W to move forward two words。 I to go into insert mode， add the one comma space escape。

 I'm back in normal mode。

![](img/ddd580325caf3a55db2aa1961bd00860_21.png)

![](img/ddd580325caf3a55db2aa1961bd00860_22.png)

This is a very common pattern in BIM， you stay in normal mode， you go somewhere。

 you go into insert mode， you make a tiny change， and you jump right back to normal mode。

 like normal mode is home， and that's where you should be most of the time。

I also want to add a plus one。 So E to go to the end of this word， a for aend plus one escape。

Alright， fix that problem。 Another issue is that this program prints fiz for both divisible by3 and 5。

 So let's fix that slash fiz searches for fizz I press and it goes to the next match。

 C I C I quote changes what's inside the quote。 So its deleted the fiz and put me an insert mode right in between those two quotes。

 and I can type in whatever I want。 escape to go back to normal mode。呃。So great。

 I've fixed that particular problem。 Another problem with this program is that it prints fizz and buzz on separate lines。

For multiples of 15， so。Let's go and fix that。呃。Let me go down to this line here。

 One way I don't actually worry about like the actual contents of this program。

 like this is some stupid program that doesn't matter。

 Pay attention to what keys I'm pressing in Vm that allow me to make changes to this program really efficiently。

So my cursors on this line， I press dollar to go to the end of this line， I for insert mode， Okay。

 now I'm typing some stuff， escape to go back to normal mode。

Now I want to make the same change to the print below。Look at this， J， J dot。

So what dot does in Vim is it repeats the previous editing command that was made。

 And so this is a really nice way of doing repetitive tasks without typing the same thing over and over again。

 So in that particular case， I inserted comma and， And so it applied the same thing on this line when I press dot。

😊，And then I guess one final part of this demo is。We will fix the issue that this program maybe should take a command line argument instead of having this hard coded 10 down here。

So how do we do that， I'll press G G to go to the top capital O。 So now I've opened a line above。

 and I'm going to type in some text， like import cis， enter， escape to go back to normal mode。



![](img/ddd580325caf3a55db2aa1961bd00860_24.png)

![](img/ddd580325caf3a55db2aa1961bd00860_25.png)

And then I want to go down to where this 10 is， so slash 10 makes me jump straight down there。

C Ipre to edit what's inside the parentheses。 And now I can type in like whatever thing I need to type in here。



![](img/ddd580325caf3a55db2aa1961bd00860_27.png)

And then once I've done this， my。Program does FISBs correctly。

 I think I missed one change I wanted to make， but it doesn't matter。

 This demonstrates that you can make lots of changes really fast。

So any questions about this demo or the overall idea we've been talking about？

I didn't catch how you changed clean the window。 Okay， so this will be covered。Tuesday。

 so the kind of outside environment， I'm running vi on the left and Michelle on the right。

 And then this is T Mus on the outside。One variant of that question might be like。

 how do you switch between different Vm windows， and you can see the lecture notes for that。

 but there's a key binding for that。 So if you have the same window open or multiple things open。

 there's a way of doing that。Question what's the difference between change。Good question。

 So delete takes motion and then removes those contents。

 but keeps you in normal mode so you can keep just moving around a file。

 What change does is very similar to delete。 It takes motions and treats them in the same way。

 deletes those contents， but then puts you in insert mode。

 And so it saves you from typing one extra keystroke。😊，So if I'm here， for example。

 I want to delete main， DW deletes a word。But now， if I press whatever key like， I press J。

 it just moved me down。If I undo that， do C， W for change a word。

 Now it's actually put me into insert mode， and I can type in whatever I wanted to insert。 So D W I。

Is the same thing as C W。 But it saves a keystroke。

 one thing we've linked in the resources is something called Vim golflf。 Basically。

 people have set up a game online where you can get an editing task and try to figure out the minimal number of keystrokes necessary to complete that editing task。

 It's actually really addictive。 So I'd only suggest going on their shift some spare time。😊，不。

I think I saw a hand for another question， yeah。And we repeat the last。U， period。Yeah。

One of the most useful impmans。 Good question。 Any other questions。课嗯。

So I think we have about five minutes left， and I'm going to briefly talk about a thing that's also covered in detail in the notes。

 so make sure you look at the notes for this。So Vim is a programmer's text editor。 And so， of course。

 it's highly programmable， not only through its interface。 that's a programming language。

 but also a couple of different ways， there's lots of settings that you can tweak to match your preferences and you can also install plugins for vim that do all sorts of useful stuff。

 So the way vim is configured is through a file on disk called VmRC。

 and you'll see this is a common pattern in a lot of shell-based tools。

 there'll be a plain text file that configures how the tool works。

 And so if I edit this file and it may or may not exist on your machine yet。

 but I've downloaded the we've created a kind of default VmRC for you and linked it on the course website So you can start with that one。

 if I do vim tilda s VmRC。

![](img/ddd580325caf3a55db2aa1961bd00860_29.png)

I can see here a bunch of comments and then particular commands， like by default。

 we want syntax highlighting on and we want line numbers。 if we didn't do some of these things。

 like let me remove the stuff that sets line numbers if I remove those configurations and relaunch Vim notice that I no longer have line numbers on the left。



![](img/ddd580325caf3a55db2aa1961bd00860_31.png)

But yeah， so in short， there's a lot of stuff you can configure with Vim。

 We've given you a very basic configuration that tries to like remove some of the kind of weird behavior that's on by default in Vm。

 But we don't really try to enforce too many of our other opinions on you。 But， of course。

 like the three of us use Vm a lot。 and we have heavily customized VRCs。

 So we've linked to our personal configurations too。 if you want to take anything from that。

 And also like thousands or like millions of people share their VRCs on Github。

 So there's lots of places to look for inspiration。 There's also cool blog posts on this topic。

Another thing you can do in Vim is you can extend it with plugins that do all sorts of useful things。

 This lets you do things like fuzzy file finding， which a lot of text editor come with by default。

 So you can get like a pop up window。 You can type in the name of a file or approximately the name of a file and find it very quickly。

 Or there are things that show you like visualizations of undo history。

 They are things that show you。😊，Like file explorers， things like that。

 So we've linked to a couple of our favorite plugins on the course website。

 and so I highly recommend becoming familiar with how to install a plugin because it takes like three seconds and some of them are really cool。

And then finally， the last topic I'll briefly mention before we finish today's lecture is vim mode and other programs。

 So it turns out that a lot of programmers were really excited about vim's interface。

 And so they've implemented similar functionality in other tools。 For example， like。

 I've configured my Python Reple to run in vim mode。 So I can like type in stuff here。

 And if I press escape。 Now I'm in normal mode in my Python Reel。

 And I can like move back and forth and like press X here， delete a thing like C W change a word。😊。

And do all those good things。And it's not just the Python Re。

 Like I have my terminal behaving this way too。 so like I can type in whatever I want here and like escape now I'm in normal mode。

 I can go here and like go into visual mode inside my terminal and like select blocks of text。

 press tiltda to change the case， whatever So we've linked to like how exactly you can enable vim mode for like bash Zhell fish。

 a lot of readlinebased programs like Jupiter notebook， a whole bunch of other things。

 And if it's not another， you can probably find it by googling it because a lot of people like to have this sort of functionality。

 And if you're really gonna like commit to learning vim。

 I think it's valuable to enable this sort of like vim emulation mode and every tool you use is like wanted to like make you learn the tool a lot better。

 And too， once you become good at vim， like those skills will now transfer to all your other tools you use。

Okay， so I think that's it for our rapid introduction to Vim。

 There's some other neat material that we weren't able to fit in today's lecture。

 but it's in the lecture notes， and then finally I highly recommend going through the exercises for today。

 like at least for me personally， I think spending time learning my text editor has been like the most beneficial thing out of like the kinds of things we're teaching in this class。

So yeah， that's it for today's lecture and we'll see you tomorrow。

Note that we've changed tomorrow's lecture to data wrangling。 Thursday and Tuesday。

 lecturecs are now switched。 So this is reflected on the course website in case anybody was going to come to one。

 but not the other。
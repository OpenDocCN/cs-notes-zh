# P7：Lecture 7 Signals - ___main___ - BV1ED4y1R7RJ

 Welcome to Wednesday。 Hope the assignment's going well。 I will go back to my office。

 right after class today。 I guess you get the benefit of coming to class and， under hearing this。

 I'll go back to my office today and then stay there for about。

 45 minutes to an hour for anybody who has questions on homework。 I also have。

 off-sours tomorrow morning from 10 until noon。 So feel free to stop by Gates。

 201 if you want to go to my office hours。 And then of course there's regular。

 off-sours with the TAs this evening and tomorrow as well。 The assignment is due， tomorrow。

 Hopefully it's going all right。 Remember this is a real file system you。

 guys are actually looking at。 So all the little nuance parts to it。 Well that's， real life。

 That happens in in real programs。 So you're getting a little bit， of a taste of that。

 Let's see I put a joke up here。 The barman asks what the first。

 one wants to race and she's walking to a bar。 So I know it's hilarious isn't it？

 The so the joke is you always have to explain your jokes if they're not that， hilarious right。

 So the joke is that this is a race condition。 We haven't really。

 talked too much about race conditions yet but we will start to see many many， race conditions。

 We've seen a few here and there。 A race condition is simply when。

 two things are happening simultaneously and you don't know and you can't predict。

 which one will actually get to where it's trying to go first。 That becomes an。

 issue if you're doing things like trying to wait for something to happen or。

 rather not wait for something if you forget to wait for something to happen。

 and it may be out of order from what you kind of expected。 So you have to think， about that。

 It makes programming concurrently tricky because you have to， think about that。

 So today we're going to do a few examples where we're going to。

 see race conditions and we're going to see one way of handling them。

 Okay so this is what I introduced on Monday。 We're talking about signals now。

 Okay and signals are a way to send a message basically not even a message。

 basically a way to say to another process something has happened。 You don't。

 even get to say like any message itself。 The best you can do is you can actually。

 pass a signal number which is the actual signal that gets sent but you。

 don't get any other information。 If you want to pass other information to the other。

 signal you have to do it in such a way that both processes have access to it。

 which generally would mean shared memory or a file or something like that and。

 that becomes a little bit trickier to do too。 So it's not like you have this。

 situation where you're just signaling another process and then being able to， tell it lots of stuff。

 It's got to be a logic sort of thing like when this。

 signal happens you're going to do this because the signal happened。 That's what。

 that's what we're going to do。 We're going to see examples as we go through， this。

 Okay a signal handler is a it's a function that you write that goes into a。

 process and when that signal arrives or the process the signal handler gets， called。

 Okay and the ones that we're going to focus on are when a child has。

 some change of state when it ends when it stops when it's continued and we haven't。

 even talked about how you continue a child that stopped will get there and。

 that's that's a function that you write and it gets called when that happens。

 Okay all right the there are lots of different types of signals as we said。

 there's signals that happen because something bad goes wrong like there you。

 divide by zero that sends a signal or if you try it if you do control C well。

 your program gets a signal that it actually can't block it actually is going。

 to kill your program generally there's some limited ways around that but that's。

 generally what's going to happen and there are other types of signals that you。

 can send that are user signals there's a couple separate ones that are specifically。

 for you to use for whatever purpose you want that's another type of signal。

 Okay all right so as I said sick child is the one we're going to care the most。

 about at least for this class and it happens whenever a child process of a。

 particular parent changes state and so we're going to be able to capture that。

 that is generally when we're going to want to do our weight PID for the child。

 to actually find out what happened to the child what did it just do did it and did。

 it diad normally what happened to it so we're gonna generally see weight PIDs。

 inside of the sick child handler。 Okay the first one that we talked about is。

 this program that I'm going to just retype so that you kind of get the feeling or。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_1.png)

 you actually kind of see what it is kind of in more a little bit slower so you。

 can kind of process what's going on I know a lot of times I've run through code。

 really fast and you go I've never seen that before how can I even process it so。

 I'll try to like slow down a little bit in that sense more often and actually。

 type things out explain as I'm typing give you a second to process it and so。

 forth okay so let's start out we will write a main function this is the example。

 I talked about on Monday where you have this model of dad taking his five。

 children to Disneyland and he lets them all go off and play they each play for。

 a certain amount of time and then they come back in the meantime dad sleeps。

 okay and I actually said something on Monday that I was very confused about。

 and I figured out why it was because I hadn't typed the program in I'll when I。

 get there I'll show you what what I'm talking about but in this case what we're。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_3.png)

 gonna do is we're gonna start out so let me a little higher on the screen here。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_5.png)

 there we go we're gonna do is we're going to start out here and we're just。

 gonna say print F let my five children play while I take a nap look if I was a。

 dad going to Disneyland I'd be on all the rides too so I don't know what he's。

 doing to take them in that but anyway that's what this dad is doing okay and。

 then we're gonna set up the signal handler by saying signal SIGCHLD by the。

 reason they left out all those like what they left out letters and things is。

 because it used to be that you had to have a certain file length or your。

 certain name length limitation and so a lot of these names are really short and。

 kind of leaving out letters just because that's historical in this case so we are。

 going to tell it what function we need to set as the signal handler in this case。

 is going to be reap child okay and then we're going to start up all these。

 children processes okay so we're just gonna go for size TI equals zero I or。

 actually we'll start with one so we just get one two three four five I is less。

 than or equal to five I plus plus and then we are just gonna fork so we're。

 gonna have this kind of we're not gonna actually capture the PID from the child。

 but in this case we're just gonna say if fork equals zero that means we are the。

 child that we're in this block we're going to sleep for three times the I guess I。

 said kid before didn't I do it kid like this， yeah there we go sleep for three times whatever the kid index is index starting。

 at one right sleep in this case is gonna emulate playing or whatever playing it。

 is new and okay and then after the child wakes up from the sleep or finishes。

 playing we're just gonna say print F we're gonna say child and then because we。

 used size T we have to use like ZU or something like that is tired returns to。

 dad not data to dad there we go I guess it makes sense in computer science okay。

 so there we go and I might need a press it quote on there all right and then we。

 are going to just returns here from the child okay so that's what's gonna happen。

 in the child we're gonna do that five times boom and they're gonna sleep for。

 three seconds six seconds nine seconds etc yeah probably thank you very much。

 how about kid thank you very much that would be a bad mistake probably would have。

 gotten a warning I hope we'll see good catch all right so anyway that's gonna。

 be the five children starting up and just sleeping for a while okay and then。

 we're gonna have the parents in this case like the dad okay while numb children。

 done playing is less than K numb children whoops。

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_7.png)

 hang on oh no I knew I'd do something like this I tried to do a special like。

 special command and of course it's not working no oh no hang on match one of 76。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_9.png)

 how about we know one oh oh no what have I done let's sit right again I wonder if any。

 of that got saved let's see we'll find out I don't think I saved it anyway spring。

 and let's see it's live lecture processing let's see it did get a swap file。

 let's see if we can recover it five children see and looks like it doesn't。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_11.png)

 want to play there goes okay what does it say it says file swap owned by that。

 another program edit in the file I want to recover it enter okay so I got saved。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_13.png)

 anyway it looks like most of it did okay well anyway all right let's try this。

 again I won't try to be fancy on this so in this so we got the everything in。

 there for the parent or for the child and then the parents going to do while。

 num children what's the name of the variable there it was num children done。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_15.png)

 playing children done playing is less than okay num children all right so what are。

 we going to do we are going to print F at least one child is still laying so dad。

 nods off okay and then the other day we use when in fact in earlier in this。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_17.png)

 program we used sleep I don't know if you remember that when I said that hey it。

 looks like the dad is waking up or is not waking up when he should be and I。

 thought that was because sleep should sleep normally stop sleeping at the。

 point where a signal is handled actually or I guess is not handled but anyway it。

 does if a signal happens sleep will generally return what we want to do is。

 we want to actually have the dad not wake up so we're gonna say snooze which is a。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_19.png)

 little function we wrote that just basically does this and says don't wake。

 up if you get a signal okay so that's what we wanted to snooze for five。

 seconds and then print F dad wakes up that and there we go and then when you get。

 all the children back we're just gonna say print F all children。

 accounted for good job dad nothing like that and then we're gonna return to。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_21.png)

 her okay so that's our function let's just run it okay make five children okay and。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_23.png)

 when we run this right what it does is it does all those that forking and then。

 dad nods off child one returns after three seconds dad wakes up child's two and。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_25.png)

 and then goes back to sleep child two and three wake up while dad sleeping in。

 that next five seconds and then dad goes back to sleep again and then child four。

 and five also wake up a return rather and then that's it so what did I forget to。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_27.png)

 do I forgot to write the function that actually does anything right so let's。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_29.png)

 see you know this one I want to delete it there we go okay so in this case let's。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_31.png)

 see actually hang on one side jump yes no it doesn't say it's in there anyway。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_33.png)

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_34.png)

 okay so we have to actually write reap child well this is gonna be a really。

 simple reap child in this case okay all it's gonna do it's going to clean up。

 after the children so it's gonna be wait PID all right and then negative one says。

 wait for any child okay no because we don't care about capturing the return。

 values at this point or not you would if you were doing this for a little more。

 robust program and then zero which we'll get to changing that today actually just。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_36.png)

 basically says just block until that child returned but it's going to have。

 just ended because that's why the signal handler got called okay and then at。

 this point we need to update the num was it again num children done playing okay。

 and then that should do that now this signal handler is in the parent and it's。

 getting called when the child ends okay that's how this is getting called question。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_38.png)

 if you didn't write the wait PID there that's a good question all that would。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_40.png)

 really happen is it would it would be as if you were leaking the memory I mean you。

 wouldn't clean up after the child nothing else would actually happen in that case。

 and it would still actually work we can test if you want that's it any other。

 questions on that let's see if this one works now I just made it five children。

 there we go okay so same thing again waiting for three seconds and then returns。

 to dad that wakes up two more children are going to end in the next five。

 seconds and then finally the last two children and and then dad wakes up and。

 then we can say that all children are accounted for okay so that's what's。

 happening the the main parent or the parent function is in that while loop but。

 just sleeping for five seconds and the signal handler is happening and when the。

 gets when the dad gets done sleeping because hey all my children back I'm。

 relieving question so if you didn't write the rep child function dad。

 just keep waking up yes that's exactly what we did when I didn't write that the。

 question was wait if you didn't write the rep child or function what would it what。

 would happen the dad would keep waking up and then that global variable wouldn't be。

 updated so it would just stay at zero as it turns out yeah yeah。

 yeah good very good question when you call us when you when you call the。

 signal function you are passing in a function pointer to reap child good。

 correct well you don't you generally don't need to give it arguments it's a。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_42.png)

 good question but you don't need to when you say signal all it needs to know is。

 reap child there there's only one argument that reap child must take and。

 it happened to be an integer for the signal number cleaning up after the。

 children does not do that and the good question like you're saying why why does。

 cleaning up after the children make it happen it's this that makes the dad。

 because that's a global variable that is being updated by the signal handler。

 all right now if you're thinking wait a minute I thought children and parents。

 have different memories and so if I update the global variable here it's not。

 gonna update the parent remember it's not had none of these this function is。

 not happening in the child this function is happening in the parent when the。

 child ends so it in fact is the same global variable okay all right so that's。

 what happens here what if we so just change it here what if we change。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_44.png)

 something and say let's let all the children sleep for the same amount of。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_46.png)

 time okay so in other words they're all gonna go out and play they're all gonna。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_48.png)

 come back the exact same amount of time let's find out what happens if we do。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_50.png)

 this five children okay so now same thing's gonna happen they all come back at the。

 same time maybe in some other different order right dad wakes up and then five。

 seconds later dad wakes up again and we got all the children back but somehow。

 numb children done must not have been updated correctly okay let's actually。

 see what happens let's look at this again like this let's do this in the。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_52.png)

 SIGCHI in the handler let's just do this print F numb children done playing like。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_54.png)

 that and see that should do it and it is going to be numb I'm gonna try this。

 again up that time work okay all right and then that should do it okay so new。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_56.png)

 children there we go all right and so let's see what happens oh well it looks。

 like four of them seem to have come back all at once and called that signal。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_58.png)

 handler once it turns out that if children end at roughly the same time。

 this is by the way out this is a kernel race condition and this is how the。

 kernel handles it if a bunch of children end at the same time the kernel。

 will take well we'll just say fine I am going to call one instance of the。

 child handler function you get to deal with whether or not like how what what。

 that the ramifications of that is okay so it's kind of a race condition in the。

 sense that in this case four of them were handled by only one child handler。

 process like happening at the same time the the nice thing about it is that if。

 you are already in the child the signal handler and another child ends it will。

 call the signal handler again so it's not that it you lose any children it's。

 just that you have to deal with all the ones that have ended already immediately。

 okay and you have to do that inside the child handler we'll see how that goes。

 yeah question exactly so that so the question the comment is a。

 perfect comment the comment was it's not that the children are ending and not。

 being processed and not hand like the signal handler is not getting called。

 them it's that they're all coming in at the same time the function is only getting。

 called once and therefore when when and they've already ended and that function。

 only ends up incrementing non children done once what we can do is we can。

 modify our program to actually say all right well maybe if all those children。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_60.png)

 are if all those children have ended when the signal handler just happens let's。

 do this while true inside our signal handler okay I'm gonna get rid of this。

 for now just so we don't because we don't need that right now okay when the。

 while true okay what we're gonna do is we're gonna wait for all of the children。

 okay and if the return value for wait PID which normally is the child that was。

 just waited for if it returns negative or if it returns negative one there or I。

 guess a negative number it means that there are no more children waiting in。

 that one like thing now if another one happens to end it will call the signal。

 handler again okay so it's not like you have to kind of keep waiting and maybe。

 it's happened there's no more rates conditions in that case okay so what you。

 need to do in this case is you need to say well our better capture the PID for。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_62.png)

 this right and if PID is less than zero we're just gonna return okay so we're。

 basically gonna break out of the while loop after we've now handled all over。

 the potential children that may have ended in that case okay question it's not。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_64.png)

 less than one for the last child it's that we're recalling we're gonna call。

 wait PID again there are no more children that have to end therefore wait PID。

 says there's no more children that have that have ended now therefore we're。

 going to we are going to return this will well this will every for every child。

 that's ended in this little loop here right it's going to stay in that loop。

 until until it says no more children are left that's what's happening here you。

 not get that if they finish at the same time that's okay but we've got a while。

 loop that's gonna get the first one then the second one then the third one then。

 the fourth one is keep gonna keep going in the while loop and just keep asking and。

 one of them will end up being the one that the wait PID captures we don't know。

 which one one of them will then we'll go through the while loop again and it will。

 return a PID so we'll go oh we're not gonna break we're then gonna go do it。

 again and do it again and do it again until all the children are captured okay。

 still don't get it you have a question about go ahead think of a question yeah。

 so read child is getting called， that doesn't necessary so but wait PID is getting called multiple times until all。

 the child children have been fixed yes wait PID is getting called well wait。

 PID is getting called once when one when any child ends and then we're going into。

 this while it's going oh let's keep waiting for children until there are no。

 more left okay and then we're gonna end question about yeah that is a good。

 question it in this case the way we were running it right now it blocks while。

 there are still children not done so it will wait yeah it'll actually wait for。

 all them to be done now they're all gonna come back in roughly the same amount of。

 time in this case but that's a good point and we'll see how to handle that in a。

 second if you want to deal differently husband okay all right okay if you're。

 still well well let's see what happens when we when we run this and okay five。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_66.png)

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_67.png)

 children okay now it's going to go into that while loop they're gonna return to。

 dad all five of them end up getting captured it in the in that while loop and。

 then dad wakes up and it did increment all got five of their。

 incremented numb children done each time yeah yeah very good question in this。

 case the signal handler it turns out that the signal handler is called once as。

 it turns out it may get called again although it doesn't matter it doesn't。

 actually matter because we're calling wait PID remember what wait PID does and。

 this is a very good point in this form when we say wait PID like this when we say。

 wait PID like that what it says is okay wait for any child to finish if there are。

 outstanding children to finish like if there's any children out there wait for。

 any one of them to finish okay and it will actually block until a child finishes。

 if there are no more children because they're all already finished it will。

 return negative one immediately and that's when we'll break out of that loop。

 yeah let's do that this old college says whoa wait a minute what if we made the。

 following change and just said oh let's see if our new method which we proved。

 works for the other the one where they're all ending at the same time what if we。

 did this now what's gonna happen and the his comment was oh is it gonna mean that。

 we're never going to like it's and we're not gonna see all that dad wakes up。

 business until way at the end let's find out all right now the child's playing。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_69.png)

 remember now they're doing three seconds each right okay child one returned after。

 three seconds child two returned after three seconds dad still hasn't woken up。

 yet child three return child for return dad still hasn't woken up in fact dad's。

 trying to wake up but guess what the signal handler is the part of the。

 program that's running it will not also it's only one process now even though。

 there's two functions that could happen the signal handler is the one that's in。

 this while loop and the dad never has a chance to actually wake up and see if。

 the children have ended yet so yes we broke this one by doing that fancy。

 while we got to do something else yeah， yeah the question is is the signal handler running on the call of when the。

 first child ends it could be the first or it's in this case it is the first。

 because they are ending at different times it could be many ending at the same。

 time calling it once but in this case yes the signal handler starts when the。

 first child finishes and then it doesn't know it never leaves the signal handler。

 until all of them finish this is actually not good programming you want。

 your signal handler to be fast if you did one oh seven e you know that's true。

 about interrupts this is basically the same sort of thing you want your signal。

 handler in and out as fast as you can so you don't want to wait for all those。

 other children remember the dad had job to do the dad was supposed to wake up。

 and say oh I'm gonna see if all my children are back but he couldn't until。

 all the children got back right so that's the big that's a big problem， yeah。

 no no good quite good question has it does the is the weight PID called before or。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_71.png)

 after the child ends it is called because the child has ended okay so。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_73.png)

 in other words reap child gets called when the child has ended and it has not。

 been cleaned up yet there's no way so the operating system is basically saying。

 oh this child has ended well I'm gonna wait around until somebody cleans it up。

 until the parent cleans it up and so it's it's in the process of being finished。

 but the child hasn't been cleaned up yet that's why it gets the PID returned at。

 that point yeah question if we print it out here。

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_75.png)

 yeah let's see what happens when we do that all right what it's gonna do it's。

 going to when each child gets back it's going to just do that right because it。

 by the way it's still inside the loop right it's still inside that while loop。

 not leaving that while I'll show it to you again and then then we'll see let it。

 finish here and then let's see there we go okay so it's still in this while loop。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_77.png)

 remember forever true while true it's in that while loop until weight PID returns a。

 negative number saying there are no more children left and in this case that's。

 really not what we'd like to do it's not the best coding style because we're。

 staying in that child that signal handler until they all finish what if。

 one was supposed to go on for days well the rest of the program wouldn't be able。

 to do anything so you shouldn't stay in the signal handle that long yeah。

 when the other children that is waiting for it to return when they do return。

 is they call the child again yeah this is a good question when I believe it。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_79.png)

 does as it turns out call reap child again yeah I mean let let's do that let's。

 let's let's find out let's see if we can test this I'm not 100% sure this is gonna。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_81.png)

 do anything but let's test this reap child just called okay I think the question。

 was what happens if they've been cleaned up in here does another signal get。

 generated I believe it will I'm not a hundred percent sure once it's cleaned up。

 it might be removed from the it probably is it's probably once it's cleaned up it。

 goes oh I don't need to send another signal because it's been cleaned up I'm。

 guessing that's the case well let's just let's just find out okay let's see how。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_83.png)

 many times is so we actually need to do here is we also need to let's say all。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_85.png)

 children are counted for let's just see if there's any other issues maybe down。

 here later so let's do another let's do another shoes for like three more。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_87.png)

 seconds or something like that okay make five children children okay so boom。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_89.png)

 reap child just got called now it's gonna be in reap child not calling it。

 again until all five get done we know because it's in that while loop and it's。

 just gonna sit there and do that okay and it can't and it doesn't you can't call。

 the same signal from inside this there it goes again it did get called again so。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_91.png)

 yeah it looks like it got called for once more because every all those children。

 that triggered it so I was wrong it does get called at least one more time now it。

 didn't matter because that what would go into that while loop and it would。

 immediately say there's no more children goodbye and that's it so there's some。

 logic there you have to handle yeah good question the SIG the signal parameter。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_93.png)

 I'm gonna get rid of some of these things because we're gonna change it again in a。

 second the signal here over here that parameter all it says in this case is。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_95.png)

 that it's a SIG child that's the only thing gives you doesn't give you any。

 other information just says which signal you could ask which signal that。

 called I mean you basically look at that go is it the SIG job yes that's it maybe。

 we maybe we want this to be an encompassing function to capture many。

 signals and maybe you want to know which signal actually triggered it so that's。

 how you do that yeah， be careful do you mean reap child's called right here it is not called there。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_97.png)

 this is just simply calling signal with a function pointer to reap child saying。

 when a child ends that's when reap child gets called that's a good question。

 it may be the case that the rest of them haven't been created yet by the time。

 you're right in this for loop here if we had made it sleep zero or no sleep at。

 all then it might have jumped into the loop and then it would have done but it。

 still would have worked okay because let's say it didn't have any children at。

 that point it would have exited the reap child but then the next child would。

 have gotten created and it would have gone back and called so I mean it's not。

 like anything would have broken in that case but you're right it could have been。

 that we ended up in reap child before any of the other children were created but。

 it's still going to get called later when they do get created and then eventually。

 finish good lots of good questions here glad I'm going over this again or at least。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_99.png)

 this part of here okay so what do we want to do in this case so now we've got。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_101.png)

 this problem here remember we've got that we've changed the behavior by adding。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_103.png)

 this this while loop up here okay we've said wait block until all the children。

 are done and if we've got five children outstanding then it's going to sit there。

 and block until all the children are done and that's not what we want we want。

 the signal handle will be in and out really quickly that's the basic idea so。

 it turns out that we will finally get a chance to use this final parameter for。

 wait PID okay this parameter there's a bunch of flags you can put in there you。

 just order them together one of the flags that we care about and in fact。

 specifically for this is called double you no hang and double you no hang is a。

 flag that says wait for any child except if there are none that are finished just。

 return immediately with a return value of zero so it said that means a return。

 value of zero means that there are children remaining but have not ended。

 yet but I'm gonna return now because you don't I don't want to block on this I。

 don't want to stick around waiting for those in this while the only other thing。

 we have to change here is we have to say oh fine if PID is less than or equal to。

 zero because if the zero case there are still children but they're still going。

 so I'm not gonna stick in or stick around and try to wait for them I'm gonna come。

 back later when they finish and and call this function that's what's going on here。

 let's try this and see if it works five children okay five children so remember。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_105.png)

 now we've got this idea where we want the dad to wake back up after the first。

 two children okay we have to wait read children I'll take that out so you can。

 see what's going on in a second here but you can see that dad's waking up now。

 which is exactly what we wanted exactly what we had the very first one but now。

 we're doing it in a way that we can capture in case all the some children end。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_107.png)

 exactly the same time or roughly the same time okay let me just run it again。

 without this line in there anymore and we'll just see it work in general。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_109.png)

 what questions do you have about this the purpose of W know hang we will use that。

 very often okay and we'll use that because specifically because we want to。

 keep our program going we don't want to sit there and go oh let's wait for the。

 child let's wait around for the child let's do something else let the signal。

 handler get called when the child ends and deal with it that question。

 basically the flag just says don't like stop the program anymore just deal with。

 them already ended whereas we did not like it was created。

 yeah so the question is this flag or a comment is this flag W know hang it says。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_111.png)

 to the weight PID function if there is a child that's ended return that PID and。

 clean it up if any of the children have ended return pick one of them clean it up。

 and give me that PID back so I can do whatever else I want with it if there are。

 no children that have ended but there are still children out there don't wait for。

 one like we've always done in the past just return zero and say look they're。

 still there but I'm not gonna wait you asked me not to wait for that's what。

 it's doing is well so the question is is there a queue of processes needs to be。

 clean up yes I mean it's it's operating system specific and I don't know exactly。

 how Linux does it but the operating system is part of this whole game when。

 the child ends the operating system says okay I I owe the parent a signal and it。

 sends the signal whenever that child ends now if the parent has already ended。

 well then you know you don't want that but the in this case the parent we've。

 made it so the parent will not end until all the children end but yeah that's。

 that's kind of what's happening the operating system saying I'm gonna build。

 up a little queue of ended children and then I'll call wait PID when I need to。

 lots of other questions yeah good question we don't know how many times。

 reap child is called in general in this case because they're staggered three。

 seconds three seconds three seconds three seconds it's called five times。

 because there aren't two that end at the same time anytime two or more will end at。

 the same time it could only get called once and that's why you have to handle。

 them all inside that because you may not get another call later and it's just a。

 it's a race condition that's kind of built into the operating system and this is。

 the the way they they said look you have to plan for if reap child gets called。

 maybe more than one child has ended you better deal that because we're not。

 gonna call it again in that case yeah so if we do go back to when multiple。

 well too convinced at the same time yeah， correct you would you would go through that so yes if two ended at the same。

 time you would end up getting the called once probably and then it would go then。

 this while loop here would go through the both of them and clean both of them up。

 and then find out that none have let know none of the others have finished。

 return zero and then you return from the function yeah no in this case remember。

 this was the status so we could have done in fact you normally should do。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_113.png)

 something like this status and then you paste in status like that and it gives。

 you more information what was the return value of the child did it end up normally。

 was there some other there's lots of information that you've some of the more。

 information you get from that what status did it what how did it end did it was it。

 stopped or rather did it end or was it stopped or was it continued that gives。

 you more information about that good questions yeah。

 could I run it without which oh yeah you want me to run without the so they all。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_115.png)

 end at the same time sure let's see so if they all at the same time do that and。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_117.png)

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_118.png)

 see okay so remember they're all gonna go boom and after three seconds or。

 whatever right boom they all ended dad finally wakes up and says oh they've。

 all ended we're done and they got handled inside that good question right。

 that's a lot of that's a lot of like stuff packed into one program a lot of。

 different things going on but what we've learned now is well these signal。

 handlers have some nuance to them they have some they have this ability to get。

 called but sometimes it's a little bit like odd because two things could kind。

 of call it at the same time so that's nuanced we've got wait PID which will。

 wait for any children and you can use negative one for the first parameter to。

 wait for any of the children and now we've said yeah but what if we don't want。

 you to block and wait for that child we only just return immediately and we。

 capture the information about that saying oh there's no if it's zero there are。

 children still remaining that have not been captured yet okay now we didn't care。

 if it was children still remaining or all the children are done because we just。

 know that we're counting correctly so reap child will get called again if we。

 haven't counted or if all the children are still remaining just because the。

 main the parent program or the parent part of the process is do kind of doing。

 its own thing okay all right I know this I know there's a lot going on there but。

 do ask more questions and feel free to go run the code yourself if you want to。

 you can download it I didn't put it in the slideshow today I'm not sure if that。

 screwed up my tablet or not but the other day but I'll try it again in the。

 future so anyway we went through all these different cases so I don't I don't。

 think we need to redo these because we did them kind of as we go along but feel。

 free to read the slides about that it's just basically going through exactly。

 what we did live and you saw that we had some various cases where we needed to。

 do more logic and different type of logic okay all right so let's see that I think。

 it's that for there there are other flags besides W no hang there's also W。

 untraced which is a weird name but basically what it means is block until a。

 child process has either ended or been stopped and stopped is paused not ended。

 and we'll see lots of cases where they get paused if you use W untraced with W。

 no hang it removes that weight that blocking part it doesn't actually block。

 in that case W no hang always says well I'm not gonna block but the other ones。

 W untraced is if it stops and then you also have W continued for the situation。

 where the child process has been stopped and then gets started back up again。

 your parent will also get a notice about that get a signal about that okay so。

 often we will see three of them together W untraced or W continued or W no hang。

 and that just says look I want you to wait and return information about a。

 child process that has changed any kind of its state not just ended not just。

 continue not just stop not just continued and by the way don't actually block when。

 you're doing that okay all right so that's the basic idea of signal。

 handlers so far we have some more nuance and race conditions that we have to deal。

 with going forward okay so we have to talk about some more synchronization。

 issues okay when you talk about signal handlers okay。

 remember that the signal handler gets called when the whatever thing happens。

 happens okay so the question came up earlier and said and somebody said what if。

 what if the child process ends before the parent actually gets to something or。

 whatever that could happen all right and you because of the way you write your。

 code that might actually happen and it might not be what you want at least what。

 happens might not be what you want so we have to actually deal with this here's。

 what we're gonna do I'm gonna write another program and it's going to be。

 basically a job list toward a program in other words we're gonna start up a。

 bunch of programs using fork exec cvp like we've done before we'll start them。

 up and we're gonna add them to a job list now in fact you're gonna do this for。

 assignment for coming up not this week but next week you're gonna start you're。

 gonna do this coming up for that assignment and you're gonna have to do。

 this because your shell does that whenever you type a command guess what the。

 shell takes that command and puts it into some list that it's keeping track of to。

 know which programs are running that's what it's doing so that's what we're gonna。

 do we're gonna run these programs three of them as it turns out and then we are。

 going to every second by right we're gonna do it one second after the other。

 after the other and then we're gonna have a signal handler that gets that gets。

 called when the child state changes remember it always gets called in the。

 child state changes and we are going to add it to this job list through the signal。

 handling okay all right and then the parent is also going to maintain well it's。

 kind of the parent is maintaining this job list is really what it is okay in fact。

 we're not really maintaining it always printing it up okay let me show you the。

 program and then we will see it in action okay this is gonna be called job list。

 synchronization doc see and it's gonna be the fun again we'll write the main main。

 part first just to kind of show you what it's actually doing here okay I have I'm。

 gonna call by the way the date function you haven't seen the date function before。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_120.png)

 it just does the date prints out the date okay so I'm gonna call the date。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_122.png)

 function and it's going to run that and then print it off the screen okay that's。

 all the date function is actually going to do okay and so what we're going to do。

 is we're going to set up a signal handler signal SIG child and it's going to be。

 in this case reap processes all right that's setting it setting up the setting up。

 the signal handler okay and then we are going to do what we call we are going to。

 we are going to just actually we're not we're not we're gonna do this in a。

 minute right now we're just going to start the actual for loop to start the。

 process so for size TI equals zero I is less than three in this case I plus plus。

 okay PID T PID equals fork okay if no why this is not okay there anyway all right。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_124.png)

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_125.png)

 fork did I have I might have had a mistake in there so anyway if the PID is。

 zero means we're in the child okay what are we gonna do in there in this case。

 we are actually going to just call exes cvp okay and that's k arguments zero and。

 k arguments remember this is how X that VP works okay and that's that okay。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_127.png)

 remember that will not return if it works and we're gonna assume the date function。

 is gonna work in this case we're not doing any error checking in that case okay。

 and then we're going to sleep for one second okay which basically forces the。

 CPU or forces the parent off the CPU what do I mean by that I mean that it's。

 gonna tell the parent go to sleep and then the child is actually gonna get to do。

 its thing if you have multiple processors this will probably happen。

 anyway but in this case we're just forcing it to make the parent wait for a。

 second why well who knows maybe this is a system where you know you're typing。

 commands in and it's waiting for commands to go whatever we're just we're。

 for now we're just forcing it off the CPU and then we're going to print job。

 percent d added to the job list and we're going to print the actual PID of the。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_129.png)

 child okay and then we're going to return zero and that's okay so everybody gets。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_131.png)

 what's going on here we're gonna start a process three processes the date command。

 it's going to we're gonna print out hey I've started these processes after one。

 second okay that's happening there in reap chai reap processes in this case。

 okay what we're gonna do is we're still gonna do this while true because we don't。

 know we're almost always gonna do this from now on because we don't know how。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_133.png)

 many children have ended or have changed state okay and we're going to say。

 PID equals wait PID negative one no and W no hang because we don't want to wait。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_135.png)

 we don't want to block on these okay and then we're gonna say if PID is less。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_137.png)

 or equal to zero we're simply gonna break same exact things we did before okay。

 and then now we're going to if we were keeping track of this which you'll do for。

 assignment for we're gonna print job percent we're just gonna print it in this。

 case percent D removed from the job list okay so in this case what it's going to。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_139.png)

 do is when the job ends remember no hang actually in this case it's just just。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_141.png)

 when the job actually finishes okay it will say it's removed from the job list。

 when the child ends well why are we keeping in the job list let's remove it。

 from the job list okay so again the parent is creating all these processes。

 and putting it into the job list we're just putting it out but it's like putting。

 it into a job list when the child handle when the signal handler gets called for。

 the child process it says oh the job is now removed from the from the job list。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_143.png)

 okay let's run this and see what happens。

![](img/5307d4923970aa2b8e91ebe06d2ca1fa_145.png)

 okay jobless synchronization all right it says job two three seven three five， which the P。I。D。

 of the child removed from the job list and then it says job two。

 three seven three five added to the job list and then it says the date great。

 actually said the date first in fact because it had to end it said the date。

 and then ended and then it did the same thing and then it says the next job was。

 removed and then added and then removed and then added now you're probably saying。

 yourself well that's kind of dumb the jobless here are they're being at they're。

 being removed before they're being added right and you've got to say to yourself。

 well why is that happening right well what did we do to make it happen that's。

 the bigger question yeah comment or question yeah we did this little sleep。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_147.png)

 for one second right well well when by the time it gets to that sleep the child。

 is already on its way and the date does not take more than one second to happen。

 it happens like instantly right when the date function is done command is done。

 it calls the signal handler all of that happens before one second is done now。

 you'll notice when I run it that one second actually doesn't happen by the。

 time it says it's because sleep does not wait that one second if I change the。

 snooze it would actually wait one second but in this case it just it just。

 wakes up immediately in that case yeah very good question very good comment the。

 question and comment was wait wait if we remove sleep one wouldn't it still have。

 this potential problem because you don't know if the date command is going to run。

 faster faster than this command is going to get to absolutely like you don't know。

 that and then we're purposely putting in this this sleep in here to say hey。

 this is something that could happen even though we're forcing it to so we know。

 what's gonna happen gets me forcing it to but yeah these are race conditions you。

 can't predict them very good good point yeah if you had this right here before。

 you checked if it was the child it would all well remember that it would get。

 printed twice in that case because there's because the child and the parent would。

 do it so that's not really that's not really what we wanted to do in this case。

 but you see the issue here we've got this race condition and really what we want。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_149.png)

 to do is we want the child not to send that signal until after this command。

 that's what we want okay we want the child to maybe it ends we don't care if。

 the child ends we just don't want that signal to be sent until after or until。

 we're ready for that signal to be sent okay and in this case it's going to be。

 after we've added the job to the list because that would be kind of hard in。

 this is especially true if you literally were keeping some list that you needed。

 to like if it was a if it was a queue or something or some or some set or。

 something of like the list and you tried to remove it before you added it well。

 you're gonna crash right or there's some other like oh I can't remove that job。

 even though it ended that's weird right so you need to need to somehow be able。

 to say don't call that signal until after this printout in this case all right so。

 how are we going to do that okay there's the thing we just did what we need to。

 do okay well this is we actually kind of went through all this all this detail。

 here what we need to do is we need to use a different type of system call here。

 okay we need to use have this idea of a signal set and this signal set is。

 going to be a data structure that says when you call the this function called。

 SIGPROC mask it says don't let a particular signal get called until we。

 unblock it okay so we're going to block a bunch some signal in fact sometimes you。

 can block many blocks many signals as you want but we're gonna in particular block。

 the SIG child until we're ready for that SIG child to be okay to be fired that's。

 all we're doing okay there's three different type like functions we have to。

 deal with in this case the one is called SIG empty set let me make this a little。

 bigger one it's called SIG empty set and SIG empty set basically takes this。

 SIG set T type that we have and it kind of initialized it says there are no。

 signals in that set okay it's just an initialization and by the way this signal。

 sets basically an integer that's got a bunch of bits it's that's obviously it's。

 got a bunch of bits and it's got the bits are set depending on the signal and so。

 32 bit integer turns out there's less than 32 signals so we can do we can get。

 away with that then if you want to add a particular signal to a set you can you。

 say okay I'm going to pass in the set that I'm going to add and then I'm going to。

 tell it which signal I want to actually add to that set okay you can also remove。

 them the three that we're gonna care about right now are these three and then。

 if you want to say go block this signal you call SIG proc mask with a with a value。

 called SIG block then then you pass in the SIG set that you care about you can。

 also you can also get back the signal that you that have already been set like。

 it's kind of one of those weird things really like well we're not gonna tell。

 you remember like from day one where we talked about we talked about you mask and。

 there was that weird thing where you the only way to check you mask was to。

 actually change it and you get back what you check it's the same sort of thing。

 here why they did this is just historical I'm guessing but anyway most of the。

 time we're not gonna care about the existing set we're just gonna say look。

 here's our new set I don't care what signals are already done let's just go。

 with it if you're writing a more robust program you might care about that okay。

 all right so let's see how this actually works in practice so let's go modify our。

 our let's go modify our main function here we're not gonna have to do anything by。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_151.png)

 the way to the reprocesses we're just gonna have to change main here to have。

 this signal set that we're gonna block and you'll see how that happens okay all。

 right so what we're gonna do is we're going to the same thing we're gonna set。

 up this signal and then we are going to say okay fine I'm going to get a SIG。

 set underscore T and I'm just gonna call it my set I'm going to initialize it by。

 calling SIG empty set SIG empty set and then we pass in a pointer to the set and。

 then we say let's add the SIG child that SIG add set SIG or sorry set and SIG CHLD。

 okay all right so at this point now we've got our set that we're going to be able。

 to say hey wait for this signal like block this signal until we're ready for。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_153.png)

 okay we don't need to quite block it yet right we want to block it before we。

 actually have the chance to call it like before we actually do for it because。

 at that point we need it to be we need it to be kept blocked okay so at this。

 point we're gonna say SIG PROC MASK okay SIG BLOCK and then we are going to。

 pass in our set and we're not gonna care about the other set so at this point。

 right before fork we have blocked the signals it turns out and this is a good。

 thing as it turns out blocked signals are passed along to your children。

 whatever signals are blocked in the parent are also blocked in the children。

 and the reason for that is so that we can do this I mean that's really the basic。

 the main reason that that we did this is so that we can do that so by the time。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_155.png)

 you get to this child part the the by the time we actually run the date command。

 we are not allowed in fact the program is not allowed to call the SIG child。

 signal now it doesn't mean that it gets like ignored forever if once we unblock。

 the signals that cue of signals that need to be sent will go oh okay the。

 operating system will go oh great I've got this this child has ended I better。

 call it but it's only after we unblock it okay all right so what do we have to。

 do at this point we now need to in the child this is gonna seem a little strange。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_157.png)

 but in the child we're gonna do SIG PROC MASK okay actually I kind of lied to。

 you a little bit earlier the reason the signals get the reason the signals get。

 blocked in the children is not because of this actually it's because you may want。

 the children to also be able to block on their signal and it might be because。

 you're running the same sort of program we will see why that's actually not。

 important because of what I'm exactly gonna do right now we're going to unblock。

 for the child only right there so in other words what if date call the child。

 process if we didn't unblock at that point the date function would start out。

 with its child process blocked and date doesn't do that so it doesn't actually。

 matter that much but if date had its own child because the signal sets are passed。

 along to their children date would also have that issue it might not be able to。

 handle that okay so who knows that might be it might be an issue but for now what。

 we're doing is we're saying in the child go ahead and unblock because it。

 doesn't matter the child we don't care if the child gets a child handler called。

 we care about the parent's child handler getting called and we don't want it to。

 unblock until right here after the printf okay so after the printf SIG PROC。

 MASK SIG UNBLOCK IN THE PARENT SET we don't care about what the previous one was。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_159.png)

 no like that after this now when the child signal or the parent's signal。

 handler can get called when the child ends it probably already will have ended。

 because we just waited for a whole second and in this case so really fast。

 function question yes good very good question question where go back a second。

 explain why unblocking the child unblocking the signal in the child doesn't have。

 anything to do with a parent okay the parent forget about the child for a。

 second the parent has a main function and it has a child hand a signal handling。

 for the SIG child the parents SIG child handler gets called when the child ends。

 unless we have told the parent we're not going to let you send we're not going to。

 let you accept that signal really what it is or you can't send that signal to。

 the parent okay so it doesn't matter if the child signal is blocked or not that's。

 dealing with its own children if it had some so it doesn't matter so when you say。

 SIG PROC MAS SIG UNBLOCK INSIDE THE CHILD it's just saying I'm making sure。

 that child doesn't have any signals of its own blocked right now okay and then。

 and that might because that might be important to the child right in the。

 parent though even here we are still blocking that signal for the parent。

 because the last thing the parents saw was this block right here before before。

 so the parents child handler is not going to get called until line 45 down。

 here when we call unblock we'd say SIG PROC MAS UNBLOCK SIG UNBLOCK on that set。

 at that point now the parents signal handler can get called and it will get。

 called because the operating system goes oh now you're accepting signals I've got。

 one for you and it calls it them hopefully this will actually see how this。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_161.png)

 work jobless synchronization and hopefully there we go now we actually are。

 waiting for one second and now the jobs are added and then removed in the proper。

 order why because we wouldn't we didn't allow them to be removed until they've。

 been added and in this case that just took it took us a little time to edit。

 that's the way that's okay question yeah the date gets printed before we have。

 the job we don't really care about that because we said to the that's a good good。

 point though we said hey go run right we're trying to do our own like adding in。

 we're trying to do our own bookkeeping but yeah you're often running right now。

 if you want to do that yeah there's you wouldn't if you needed to do that we。

 would have done we would have done something like this if you said wait I。

 didn't want date to run before we did the exact V is CVP right like we would。

 have to before even forked we would have to then figure out like how to do you know。

 do that now this might actually this also might be like an issue can't in this。

 case we would have to do something else to try to figure out like how to do how。

 to wait to print until the parent has did done it but once you've got a child。

 in the parent they're kind of independent anyway so you're not really。

 gonna want to you're not gonna be able to wait for the parent on the children the。

 child is not really gonna be a way for the parent itself so you got to be able。

 to figure some other logic out to do that yeah yeah。

 very good question the question was wait is reprocesses also passed down to the。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_163.png)

 child it certainly is because it's part of the program right so the child has。

 access to all its own functions now the child's reprocess won't get called when。

 the child ends because it's not it doesn't have a child that's ended。

 as a bit inception like earlier yeah yeah the right the date might have a。

 child process in which case then it would get called correct yeah yeah so the。

 question was we if the date did have a child then this signal might get called。

 now likely the child would set up its own well actually that's good point in。

 this case the this one would it sure it might have gotten called if the child。

 process had a child process yeah if the child process had a child process yeah。

 the child's one would get called wouldn't get added to our the parents job list。

 we get out of a child's job list or I guess we would get it would get removed。

 from the child job list so you would have to put more logic in there if you。

 cared about that yeah yeah good point yeah what you could also do is you could。

 you can basically say you can set up the signal you can say signal with a no value。

 well basically it's saying don't handle it anymore you could do that in the child。

 if you cared about that we have to not care about that for this part good very。

 good good point there are lots of things think about with these things when you're。

 building these real programs yep so a sig block does that not allow the program。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_165.png)

 to receive signal or sentencing it is not a lot good question if the question was。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_167.png)

 does it does sig block not allow the program to receive signals or send it it。

 doesn't allow the parent in this case to receive that signal that its signal。

 handler will not get called it may be queued up to get called later but it。

 will not get called good question there are limits how many signals the。

 operating system will like block and store oh good question is there some some list。

 or some queue limit on the number of signals I don't know of any it's probably。

 big enough that it's not going to matter like it's probably thousands and you。

 probably likely won't be able to even create thousands of children anyway or。

 whatever so it's probably some limit that we aren't going to worry about yeah good。

 question if we come if we write if we commented this out it's going to run。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_169.png)

 exactly the same because the child isn't going to get any children and it's not。

 going to ever it's not going to matter anyway although if we if we if we ran。

 another program that had children yet probably would print that some job has。

 been added that's weird that why would that happen right but no in this case。

 not gonna matter did I delete the wrong one oh no thank you for oh you want to do。

 this one that one would just make your behaviors of did before that one thank。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_171.png)

 you all this synchronization yeah same sort of thing right no children for。

 the children are getting calling that function if you had one that did right if。

 date had its own shy-up process yeah we probably would have gotten a weird。

 print up in there that said some other process and added a job list and they。

 know well so again when you're trying to do these things you have to kind of。

 keep track of some of the details of these because it's because it's tricky。

 yeah good question yeah good question if you want to say stops calling my。

 function or signal handler you I forget exactly what it is but it's another you。

 basically do signal and then instead of SIG child it's like no signal or it's。

 not that but it's something like that I don't remember exactly what it is but。

 that's what it that's what it is in fact we can look it up if we do man signal。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_173.png)

 let's see here we go let's see here we go SIG IGN means the signal is gonna get。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_175.png)

 ignored or SIG DFL means that the default action will happen so you've got。

 you've got you just passed that into signal and it goes all right no more。

 SIG child is gonna be called into my in my process good question all right kind of。

 nice when you have the manual right there your fingertips okay all right so。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_177.png)

 that's some those are signals there we have gone through the different types of。

 signals we can actually write a little function to kind of capture this instead。

 of writing each little part out individually in this case we can write。

 impose SIG child block which does sets up a set and then calls SIG proc master。

 block and then we could do the exact lift one which does the same sort of thing。

 except unblocks it you could also have one that toggles it if you want to and。

 you'll see those functions we've written some of those functions for you there。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_179.png)

 okay right we already did this the improved job list and what else can we say。



![](img/5307d4923970aa2b8e91ebe06d2ca1fa_181.png)

 for it yeah as I said for process and hair it's the block signal sets so it。

 should it should lift that signal just in case the child cares about it and as。

 as people have already mentioned it probably should also un like it should。

 get rid of that signal handler too so it doesn't get called when the child ends。

 because that's not part of our program again things you have to think about。

 when you're building these for real you have to do lots and lots of testing on。

 this sort of stuff okay two more quick signals or two more quick system calls。

 here processes can send messages to other processes without something。

 happening you are allowed to send a signal to another process you do it using。

 a slightly ill-defined command called kill now kill was named because the only。

 signal that they originally sent was one to terminate a process basically said。

 kill this process and it means not make it stop running right says the original。

 and then they said well what if we want to send other signals let's just keep。

 kill why didn't you call it send signal or something I don't know but they kept。

 it is called it called kill okay so it doesn't actually kill if you send a。

 sick kill yes it will make the terminate the process but otherwise you are allowed。

 to give an AP ID send a particular signal okay so if you want to send the。

 SIG child signal to a particular process you can send it you can also send I。

 think there's two other ones called like it's SIG I think it's SIG USR1 which is。

 like a generic one that you're allowed to send just because hey maybe you want to。

 send one that's not a special one that says killer that says term you know that。

 says stop or it says continue or whatever we will see lots of use of these as we。

 go you can also send a signal to yourself which is you do by the raised。

 system call which basically just takes the signal number you're trying and it。

 sends it to your own process it is exactly like saying kill with get PID for。

 your own PID signal number it's you could use either and they're interchangeable。

 okay you can also get the value of that you can change PID to not be the actual。

 PID you can make it affect other processes that are tangentially related to a。

 particular process and you handle that with a thing called groups I'm not going。

 to go into right now but if you send a negative number less than one to kill it。

 actually goes and finds the group that's associated with that process what you。

 can do with processes you can set them up such that they're in same group so if。

 you want to send a signal to one process it can then or it can if you want to send。

 one kill signal it can it can go to a whole bunch of different processes so。

 it's nice to have these groups we'll get into groups when you get to assignment。

 assignment four and then you can also be zero or negative one we're not going to。

 worry about that for right now okay that was a lot of stuff you have assignment。

 to do tomorrow assignment three will come out tomorrow morning I'll do it。

 release it first thing in the morning for anybody wants to get going on it and I。

 will explain a little bit about assignment three on Monday so if you want to get。

 started on it you well maybe I'll do a little video I don't know when I'm gonna。

 do a video but anyway I will do some explaining about assignment three on。

 Monday all right last minute questions on this stuff or otherwise yeah。

 assignment three is actually gonna be due a week from Sunday so it's a little。

 longer amount of time and then the next one's gonna be out that day and then then。

 the midterm happens so you've got an extra time for the next one as well so。

 it's a little stretched out because midterms and so forth all right so you。

 guys Monday or in lab oh that reminds me I totally forgot sorry one last thing。

 there we so there are a lot of people who wanted to do the Thursday I forget， which one three p。m。

 lab we are adding another Thursday lab so we're changing。

 like one of the Thursday morning labs which not many people are in we're。

 changing or adding a Thursday afternoon lab we're gonna combine the two Thursday。

 morning ones and it's only like four or five extra people so it's not a big deal。

 I will put that up later today so if you want to add the Thursday section if you。

 don't like the section you're in an afternoon one you'll be able to do that。

 all right see you guys later。
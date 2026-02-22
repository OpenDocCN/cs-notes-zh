# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P19：-19-19. Imperative Programming _ - GPT中英字幕课程资源 - BV12VChY2EF4

Dange woman by Ariana Grande because we're talking about some real dangerous shit today。

 which is imperative programming。So， all right。Today we'll be talking about imperative programming。

 which I know you all signed up to take and signed up to be in this last four。 But you know。

 I think this one's kind of an interesting class because people are like oh。

 imperative programming like you're betraying your course。

 But here's the thing we're not because they actually named their course after our mascot。

 you see I programming。 So thing on that for a second All right we're a super set anyways。

 one other thing， let's see so。😊，Is that mean， Okay， all right， okay， well just making sure。Right。

 okay。This is the first of the lectures before the special topics lectures and the final lecture but today is definitely still fair game and I definitely think that next week's lectures are gonna be even cooler compilers and program analysis are my specialties and I'm really excited to kind of talk to you about them if you've heard me ha on about the compiler the compiler compiler hopefully next week I will make some of those things clear to you what I was talking about okay and program analysis is another cool thing and then I am going to send a piazza post about this soon but I'm requiring everyone come to the final lecture okay let's get on with it because I'm already three minutes behind。

😊，So we're talking about imperative programming today which is kind of interesting but also kind of not we'll talk about this idea of mutability that I alleged to in the first lecture we'll talk about reference cells which are a particular kind of type that we can use a kind of data structure for mutability we'll look at some uses for reps look at the example and then I'll tell you some special like applications of mutability that I use as someone who works in a functional language。

 some little tips and tricks I do as a result of this thing okay but let's get into it。😡，Okay。

 so first off mutability。 Alright， Oop see， that's not right。 Allright。

 I'm gonna have to do this thing again where I go here and then I go all the way to the top。

 and then I delete this handy little。😊，Annotation here lets us hand out because it means that my presentation was not compiled with pauses in it。

 but mutability is the thing that exists， and I've kind of harped on at you all the time about how it's really a bad thing and I stand by that we want to make sure we don't have unsafe behavior and mutability kind of if you remember what I said during the per lecture means that if you ever do anything you have to be aware of everything that's happened in the entire program's history。

 which is no bueno as far as software engineering goes or as far as writing programs goes。

Because it's going to make things just really hard to reason about， okay？Boom， so。

The idea is just that we want to avoid foot gunns that will make us write incorrect code and write unsafe code and mutability is one of those foot gunns right so let's try to avoid that。

 but we've been doing that up until this whole point we've been working with purely pure code。

 which is code that always returns the same output given the same inputs because we got predictable behavior but you know we've been talking about purely functional stuff for the whole semester while we've been lying to you because mutable features do exist in standard Ml and that's what we'll be talking about today。

😡，And this kind of makes sense because it's really hard actually to get away from effects as a whole。

 for instance， like in an earlier lecture we saw with exceptions we can now have addition where addition is now no longer commutative does everyone remember that example if I have raised div。

😡，Plus raise bind right if I invert the order of these arguments， if I swap raised v for raised divb。

 raised bind will happen first， which means bind will be raised。

 but in this permutation div is raised first two different exceptions。

 different extensionional behavior so addition in the presence of exceptions is not communutative so we've already seen the like f x can kind of ruin our day when it comes to when it comes to our code so we haven't even gotten away from it purely or for instance in this function here fo I have val x binding this loop function which you know I never defined for you but you can assume is the looping computation and then y which raises div。

😡，Now is it safe for me to permute these， can I switch doors to this， what do you think yes or no？No。

 why What happen。If。Ex loops forever Y raises it， but if I put one versus before the other I get different behavior。

 but I shouldn't be the case， I should be able to be like these are independent。

 I don't need to think about it， I don't care， let me just do it in whatever order。

 but not the case when it comes to things that loop forever and things that raise exceptions so we already lose some of these nice properties。

😡，And extension cos becomes weird reason about when you're kind of in the presence of the outside world when any about is you know I've tried steadfastly to avoid talking about this。

 maybe you'd come across it， but there is indeed a print function in standard amount it's not very convenient to use。

😡，But it has this type signature。And printing is kind of cool because what it does is I can give it's a normal function。

 I give printer a string and returns to me a unit and then all it does is it prints out to my terminal to my console right but this is kind of interesting because what it does is that when print gets a string it always returns to me a unit right this guy。

😡，And that means that for any choice of S， I should have that unit is extensionally equivalent to print of S。

 yeah， because this is going to。😡，Evaluate to that。

Except like what do I mean by extension equis because remember one of the big features of extension equis I talked about in like the first week is I should be able to swap equals for equals if I have two EEQ things。

 I should be able to replace one with the other wherever I see it。😡，Now。

 if I replace every unit everywhere in my program with print of high。😡。

Do you think my program is going to display exactly the same behavior observationally？😡，Indeed。

 it will not， okay， I don't need your sas， it will not because I'm going to get a metric butload of prints of high everywhere when I should have gotten unit okay so。

😡，Printing also kind of makes this idea wrong。 So mutability just makes us have to reconsider our our lives and reconsider our definition of extensional equivalence。

 All right， so we we're kind of we're kind of working working from behind here， all right。

So life is cruel， we live in the physical world all right this is I give you two reasons why why effectss ruin our day here's number three。

 we live in the physical world， we can't get away from that。

 I try not to live in the physical world as much as I can。

 but unfortunately our computers are made of silicon so at some point we have to be able to interface with the real world we have Unix we have we have positive libraries we have a bunch of like machine code running beneath everything so we have to think about that sometimes all right。

😊，So what I'm trying to get at here is like what can we do to make sure that we still have safe code。

 but we have the ability to do this kind of stuff when we need。

 how can we avoid book gunns but still be able to dip a toe in， okay。

 make it a toe gun if we so wish。😡，So the idea here is just that we want to avoid Fo guns We don't necessarily need to prohibit them entirely our approach up until this up until today has been that we want to prohibit Fo gunns。

 we have no mutability anywhere you know I try steadfastly not to tell you that print exists I try to tell you that what I'm telling you about today doesn't exist but all we need to do is be wary and cognizant because as long as we do our best not to dip the toe in we'll be fine All that matters is that we have that caution we don't do it by default okay so。

😡，Another way to put this is like immutability and purity these are concepts that we invented for our purposes。

 but we don't serve them like they're not they're not in charge of us I can have a relatively immutable and pure code but I don't need to bend over backwards to try and make it happen some languages will try to make that happen but in SMLre we're going to say it's okay sometimes to be a little mutable as long as it's a little bit okay。

😡，嗯。But to make sure that we don't have mutable code all over the place， like with C or anything。

 we make it opt in。 And this is a big idea in programming languages。 Okay。

 we want mutability to be opt in。 If I'm writing C code， Okay。

 and I don't forgive me if you don't know C， But like the syntax will look something like this。

 right， I could say index X equals 2。😡，And at any point down here in the program。

 I might say x equals three， and this is an assignment， it's saying， hey。

 this X thing that you were dependent on it is now three， it now contains three。

 that's mutable and I and every single assignment ever in C exhibits this behavior it might mutate something I don't know for sure。

😡，That's the opposite of optin that's by default mutability by default what we're going to do is take this track where if you want to use mutable features。

 you've got to work for it， you've got to tell me explicitly I want this to be mutable if you've worked in other languages like I think JavaScript has this now and Russ they also have this kind of idea sort of。

😡，Okay。And in a different context sort of you know this thing about null pointers which is I can I can have a pointer to some memory location and it can be this thing called null。

 which is really zero and that means nobueno， it means don't go there it means giant you know yellow fence because if you try to go to null you're going to crash a program okay this is commonly known as Tony Hre's billion dollar mistake his wordss not mine because he actually said this and it's pretty accurate okay so。

The way that we solve this problem in SMmL， right is instead of having everything be know by default。

 instead of having everything be possibly know， what did we invent， we inventedvent this idea of。😡。

Some and none， some of V and none。But this showed up in the type This was of type T option We had a specific type that we invented for the purpose of if we wanted to dip a toe into possibly not having a value。

 but not on by default， so that's the thing I'm trying to trying to show you here with what we're doing Okay I need to hear okay so you all are the future of computer science so I need to hear you say something for my peace of mind。

 everyone raised their hands okay everyone raised your hand， I need to hear you say。😡。

Repeat after me， if I invent a programming language。😡。

I will not put no pointers in that programming language。That was wrong， That was wrong。 Don't listen。

 don't listen to him。 Okay， now I can sleep a little bit better at night。 Thank you。 Al right。

 that was for my benefit， not yours。 Alright， so let's take a similar approach with mutability contact switch。

 reset that next slide。😊，Reef cells are going to be our solution for this problem What we're going to do is introduce。

😡，Well， we're going to introduce just like how T option is the type of optional values of type T that is we may or may not have a value of type T。

 we're going to have a new type that indicates mutable storage storing a value of type T and that type is going to be T ref okay so in fact you can say that alpha ref is a type。

😡，And this has concrete instances as inre。And string ref and so on and so forth， right。

 And the idea behind a type。Of T ref is that it is a box that contains a value of type T。 All right。

 So when you ask me what is a what is a T ref？That's what it is It is a box that contains something of type B。

 but beware because I'm lying to you right now because I said the box contains that。

 I mean the box contains that at this point in time because。😡，Somebody might come in。

And sneakly erase it and then put two in it or something。 I don't know。 Okay。

 so everything I'm telling you is very transient。 I can tell you something about refs。

 but I can only tell to you for now。 Okay， because it might change on you。😊。

So the type of boxes is what I want to get across to you okay。

 and the box is allowed to change what's inside， but the box stays right the box stays the same。

 but the thing inside the box might change okay that's the idea。😡。

For anyone who knows imperative programming， I'm telling you that this is a pointer to some kind of like mutable state right but the difference here is that we're making it fully opt in as in there is a type level distinction between immutability andmutability if I have something of type int I know this is immutable I know this will never change on me but only if I explicitly am holding and I'll show you how we create this value in a second if I'm explicitly holding something of type inch ref。

😡，I'm saying， okay， I know this will change on me possibly at some point in the future it's like I'm signing the youlo okay I'm wivaving away my rights to have safe code when I when I see this okay like that's on you right I'm signing this agreement but I don't opt in okay or I don't opt in by default have to explicitly opt in and we can make it very easy to see where these things can go wrong now okay。

😡，呃。So tight guide structure， nobody would he guessed， and that's the idea behind wraps。

So there are a few primitives that are going to be useful for doing this。😡。

There are a few primitives that are going to be useful for doing this ref thing and they are as follows。

😡，The first one is actually a constructor called ref， takes in a value of some type alpha。😡。

And I remember that polymorphphy it means this doesn't need to be alpha could be interesting or whatever。

 And then it promotes it to。A value of type alpha F， okay？is it puts。

 it puts the value that it gets in a box。 I also have this one， which is pronounced Bang。

 the bang operator and B has the type that it has the inverse。 If you give me a ref。

It's going to take whatever is inside that wreck， it's going to derered it to use a certain terminology。

 okay？😡，And then finally this one is contentious， it's colon equals， okay。

 you can pronounce it walrus， you can pronounce it assignment， you can pronounce it colon equals。

 I usually say colon equals。😡，I think my teas are a fan of Walrus。

 but I'm this thing is how I change what's inside of a box， so I say that I take in an alphapha F。Oh。

 this is an inex operator， by the way。Let me write that。It's in fix。

And it takes it into alphapha rep， star and alpha value。

 and what it's going to do is it's going to change whatever' is inside this box to be。

 whatever I gave it。😡，But the thing is that once it does that。

 it doesn't really do anything interesting， it just does that as a side effect。

 so what I'm going to do is I'm going to have it return this。😡。

It returns a unit as in it returns nothing interesting to me because there's nothing that it computes。

 It doesn't compute to me a meaningful value， but it executes a side effect。

 So whenever you see a function that returns unit， you should immediately think side effects are going on Okay。

 like maybe it's a printing function or maybe it's yeah。Not a pure function。

 I would say so because if you give it the same functional value。

 you might get different results out yes， so it is not a not a pure function。Okay。Boom。

 that's exactly what I just said。 All right， and this will be for creation modification。

 well creation。😊，Access and modification of ref boxes or reference cells。 Okay。

 and I will go deep into what each of these do。 All right， if everyone's cool with that setup。

 we'll move on。Okay， so what does ref do， Well， I told you that ref just taste something and puts that into a box right。

 and I guess I can just show you this。 So I have ref of V if I have actually。

 let me be more specific， I usually don't think I need。😡，stressressses point to you but。You know。

 if I have R of E where E is not a value right ref is just a function， Okay。

 so this has no special behavior so what happens first。

 what happens if I have R of B or rep is a function。😡，What's the first thing， y' all know this？

E steps to B or E you know， evaluates to B， hopefully all right， and then if that happens。

 then what happens is。😡，Ba happens。All right， we get a box and one thing to note is that the value that we get here。

 like this value here， this， you know， let's say it's an in， okay？😡。

The value of this interact is the box it's not the context of the box it's the box I'm binding a variable to the box when I say something like you know v x equals ref of E okay。

 the box is ultimately what I'm holding what that variable is associated to。😡。

And it's also worth noting and this will be important for you to recognize on your homework。

 Every time I call ref， I get a new reference cell。 Okay a unique reference cell。

 different calls to ref give me two completely unrelated reference cells think not of memory adies and like positions in the system there just exist They float in the ether okay that's all that matters but every time I call ref。

 I get a reference cell now I have to stress this to you because this is a mistake students make every semester。

 but on your homework， if you call ref too often， you will mess up if you call ref too little。

 you will mess up okay you need you need the Goldilocks ref Okay call it the right amount but understanding this will help you one ref one box。

😊，And read this thing I was talking about which was the null pointer thing this actually is still fine because a ref box can never be empty because in my constructor well I put it away but in my constructor which is ref I can never not have my alpha value so I must put something in the box and I have to have something to replace it with if I change what's inside so my box can never be empty so there are there's no such thing as a null pointer still unless I put like an option in there very intentionally right but I can't get like a siteych bolt still I can't get like unsafe memory access yeah。

Yeah， let me give you a very concrete example。 So if I did something like this。

 I said Val and I been pretty diagnosed for later， but I said Val R is equal to rep of one。

The contents of the box I want to put in are the arguments to ref so it's one。

 so what this will happen is that R is now bound to a box。

 so this box is R because it's the ref where the box contains one。😡，Does that make sense， Yeah， okay。

 yeah， I have plenty more examples to show you， but yeah， good question。😊，Cool， okay。

 any questions on that？😊，Yeah。Okay。Sounds good。😊，Sounds good， you know。

 in terms of like your tuition costs， like that probably cost you like dollars of just that second that you lost。

 And actually， I'm losing more by me speaking about you losing， Yeah， okay， let's move on。

 So ref creation once per call the ref， that's what I want you to know。 Okay， No sharing。 No nothing。

 All right， And so let's look at this code here。 Oh yeah， I say R1 is equal to ref of one。

 R2 is rep of string 5 and R3 is rep of0。 Okay， and I think I'm going to actually not draw this for you because I have very pretty pictures for you。

😊，Okay so one ref1 box over here on the right I have something I call the store。

 It's kind of like I think it's a programming language theory kind of term。

 but the store basically meaning where we keep all of our mutable data okay so right now it's empty assuming that this is the beginning of the program but let's go to the first line so if I try to evaluate ref of one boom I get a box and this box is what's bound to to r1 and it contains one and I call it again new box the box contains this string of five and then I call ref of zero boom new box and now contains zero this should be fairly straightforward right I'm binding each of these boxes to R1 through R3。

And that's fine， but I just want to illustrate to you how these boxes sort of evolve over time。

 but what happens next is what if I want to change what's in the box right I want if I didn't change what was in the box there would be no difference between this and actually immutable things right so。

😡，I'll use my Walalrus operator right here and suppose I did this which is I say V1 is colon equal to one and the V2 is colon equal to a string of one all right and if we go back to our picture that we had a second ago which was this one right this is what I got from the previous one I'm going to execute each line in tandem or in order so the first one I say V1 is now two all right so I update what's in the box and now if I were to do a bang on R one I would get two as opposed to before here I would have gotten one right yeah。

😡，Yeah， it should be。 Thank you。R1， yeah。R1， but this now it goes to two when I say colon equals two and then for r2。

 if I colon equals string one boom now string one's in there two right pretty straightforward。

 I think okay we're just changing what's inside of the box okay。😡。

So seems like we should be able to do anything once we have boxes we just like put stuff in the boxes right。

 well there's a lot of subtle things I'm glossing over with respect to how this is implemented。

 but one such thing is actually if we had this line here， So I say R2 colone equals one。😊，Well。

 first of all， more fundamentally， we believe've gotten the type error， right， which is that R1。

 if you remember。😡，This thing is going to be up type string rep， right， so ref containing a string。

 and I give it I give colon equals a string rep and an endt。😡，Well。

 can you find me a substitution of alpha for which that works？Indeed。

 you cannot okay string and inch are just different， all right， so this will not type check。

 but another another fundamental reason for this is just the fact that when you have a box like you are only capable of storing values of a certain type Okay so this restriction actually helps us in that respect right has to do with。

Compilation so， but yes， so we can only store values of a certain type。 So let's not。

 let's not think of it as a complete wild West。 All right， we only have。

Control up to a certain granularity， all right。Okay。All right， so I showed you walrus。

 I showed you ref， let's talk about how we can take things out of the box。

 that's gonna to be our bang operator， I don't really need to say much about this。

 but if I have bang of R1 and R1 is this ref containing to then boom I put them together and I get to right but you know caution because B is definitely very impure right because we can get whatever out from dereferencing the same ref it depends on where we're at in the currency of the program it depends on everything that's happened up until this point all right so be wary of this because the contents of this box lie to you it won't be the same necessarily。

😡，Okay。And then I should also tell you that we can do this via pattern matching。

 so let me make this link let me keep this， but let me try to make this explicit。So。In general。

 it's nice to have these keywords or not keywords， but these special functions I just showed you that are behind the board because it means that when you're using reps it's very explicit right if I want to know where mutability happens control F ref right fair enough but something else that can happen here is you can also look for bangs I'll also say this okay if I have v R1 equals ref2。

😡，Val R two equals string one， which is what we had earlier， not exactly the declaration。

 but this was the Si of our store I can both do。I can both do B of R1 at some point and also bang of R2 at some point。

But I could also case， and RE is actually going to be a constructor。😡，That means I can case。

The tuple of。The tuple of R1， comma R2。Of。And I'm taking a tripleal pattern。

 so my first thing is going to be a triple。And actually。

 what I'm going to put in is this ref of whatever value I expect to see inside of whatever value wanted to pattern match against。

 So in this case， it'd be2。 and then ref of。String 1。Goes to。True。And if it's not that。

 let's say it goes to faults okay and what I'm going to tell you is that this code right here that I have written on the board verbatim。

 this will always go to the true case because I'm implicitly dereencing R1 and R2 via pattern matching that's all that's happening but it's worth noting that there are two ways to access what's inside of a ref we can pattern match or we can do the bang operator okay so equivalently we could have cased on bang of R1 comma bang of R2 and then remove these refs if you can see that but just something worth noting。

Alright。Cool， so ref is a construct。Okay， let's see。

So we've been using Val bindings thus far of this semester which let us sort of do things or rather we've been using Val bindings in general throughout this lecture to kind of do the side effect things that we want to and what I mean by that is like if I had if I needed to write an expression where I executed some kind of side effect I would write this right I would say let's。

😡，Now on a unit really equals R cone equals 150， let's say， okay。

 so this is me saying let me assign it and then let me like buy the resulting unit value。

 I don't really care about it。😡，And then I do something， let's say the sum expression E。😊。

And this just represents， oh， I wanted to return E， but I also wanted to do some side effect thing。

Now this is grosss Okay， this is pretty disgust。 So what we're going to do is we're going to have a different way to write this。

 Okay， I shouldn't have to spawn a let and in and an end just because I want to do something side effectsable and the syntax for this is going to look like this。

😊，And this is the new synt actually。E1， semicolon， E2， all in Perez。What this means is this。

 the semantics of the service is follows， okay？😡，One， I do E1 reduced to V1。Two。

 I do E2 reduced to B2， so I go from left to right。And then three。I evaluate to V2。 Okay。

 so I'm saying do the stuff on the left， but also what I really want is this。 Al right。

 so instead of this， we could write。R colone equals 150。Semicolon。And then whatever this E thing is。

 I'm， I'm not gonna bother to come up with an example for you。え。Much more terse。

 much nicer all right and one thing worth noting is actually I can iterate this process。

 I don't need to do strictly two semicoons or two things in the semicolon chain so I could do like R colone equals zero R cone equals one。

哦， what。Wait， no， I like the example R colone equals one R colone equals5 semico R colon equals zero。

 Who would have guessed and then I do bang of R Okay。

 so this flip I realized it's a little hard to see， but this represents like。Three things I'm doing。

 I do that assignment， I do that， I do that and I do Bang of R， but I fully resolve to this value。

 whatever it is， yeah。You mean like， does this happen prior to these？Yes， yes。

 these all happen in sequence before we get to this stage yes sure， yeah， yeah。

 it should have exactly the same semantics as if you did it with aette actually yeah。go， okay。

 good question okay。And the reason why I'm kiding a highes today is I' am out。 I need to go jiggle。

 Okay， all right， so we can do this。 and this is just a nicer syntax for doing this sequential operation stuff。

 This is the sequencing operator。 All right， and I just told you about that so we don't need to look at this。

 Okay， cool。😊，All right， well， that's unfortunate quiz time。

 let me think for a second to remember what the password was， Oh， I remember what the password was。

 I remember what the password was， let's go。😊，No， wait， wait， I want to put okay。

 just get in your positions and I'm going to write on the board。Proms behind you， yeah， okay。

All right， let's talk about how we can use some reps。 All right， there are uses。 All right。

 the ones Im want to show you right now are pretty convoluted。 Okay but okay。

 so we have three fundamental operations for working with reps。

 So now we can actually use refs to program things。

 Okay and one of the classic ways we do this is we ask you to implement a function you've seen before。

 but now we're going to do with reps disclaimer， there's no reason for you to ever do this in your life。

 You should never introduce mutability for the sake of it Okay only do it if it actually has a purpose and this does not have a purpose so。

😊，Let's talk about this function All right's let's run it through okay maybe I should have written this with you。

 but the point is I have my store， which is an inch ref and I store one in it okay and then at my base case for fact I at zero I return what's in the store so I would return one here。

😡，And then in the recursive case， I say update my store to be n times whatever is in the store。

 and then I recurarse， right， So if you think about this， if I called fact of like two。

 I would first multiply what's in the store by two， then I'd recurarse。

 I'd multiply what's in the store by one，la， blah blah， blah right。😡，嗯。Yeah actually。

 and this is pretty cool so this is yeah， this is the fact with with refs， anyone cool with that？

Yeah。Yes， they do。Don won't say where you're going to say next。

 so point is as is typical with any kind of imperative programming。

 I've lied to you because I very easily made a mistake and this is just straight up wrong okay and I'm going to show you why this is straight up wrong。

So you know entirely unpredictable we write imperative code and there's a bug who would to guess。

 but here we are right so here's what's happening what happens when I call factive2 well let's see all rightm I'm going to set this through with you and I have a really nice graphic and I'm not going to use because I hate myself I guess but we't going gonna to draw this out so I've gotten my store。

😡，And my store at the very beginning， I'm at here， I'm going to make a box and put one in it cool。

And then I'm going to call factorive  two， okay， that's where we're at right now。😡。

The first thing to happen right is I enter my recursive case and then I say update the store to be two times whatever is in the store。

 so I take this and I multiply by  two yeah。😡，And then I' recursed， so I'm now I'm at active of one。

And now I'm here again， so I multiply what's in the store by one， so I get。😡，Two， again。

And then I rehearse and I go to fact of zero， and then at the fact of zero time， I just say， okay。

 let me return whatever's in the store so。😡，Goes to two okay， what is factorial of2，2？Yeah。

 so what's the problem。 Well， okay， you're right， started to set my bed。

 I lapse in judgment on my bed。 Let me ask you again， what is， what is fact2。Let's do it again。

 hold onm sorry in my bag factor of two， I go to my recursive case and I multiply whatever's in the store by two。

 so I get。😡，Or。And then I recurse and I go here and I'm you know what happens x is nothing okay。

 what happens x is nothing， I multiply by one， and then eventually I return what's in the box so I get。

😡，Or factor 2 is4， right guys。 Yeah， Okay， cool。 Okay， classes is over。 No， it is not in fact。

 it's a really bad sound bite。 No， it's not for。 And in fact， what was our issue here。

 What did I say to you， if you make too many refs。 You're gonna get wrong。

 If you make too little refs。 you're gonna get wrong。 we are straight up in the Papa bear case。

 This is， wait， no， we are not in the Papa bear case， We are in the mom bear case。 This is not， no。

 this is， this is too little ref， We're using the same ref for the same thing over and over again。

 Now， that's not necessarily bad， but we're doing the wrong thing here。 Okay， yeah。😊。

Why don't I just put in a LED decoration， Excel idea。 So let's actually， let's actually try that。

 Let's actually try that。 I don't even have that written now。 Let's try that， so。

I've already illustrated you why this is bad， but let's try it a differently way， right。

 let's put it inside。😡，Let's move fact n equals let。Bel store。Equals ref1。

In case n of0 goes to what's in the store。Or else we're going to update the store。😡。

To be equal to n times what's in the store。And then return effect。Of n -1。

Let's let's put it in the function。No， it's like this should have been into my slides in the first place actually。

 so we got the momber case， this is the Papa Bear case， all right， why is this wrong？

Why is this wrong other than the fact I'm very gleeful about it yeah？

Each call a fact makes a new store。 We make a brand new ref for every single， not just called a fact。

 Every inner call effect also makes a new ref。 What the heck is going on here。 Well。

 it means that we're gonna make basically， if I call fact of2。

I'm going to immediately have a box of one in it and then that calls factive one， which then is like。

 oh cool boss you told me to make a sort， let me do it and then I make a box of one again and I never update this the end of the day yeah if you use it。

😡，A rapper， a raper exactly。 We could exactly do that。 like chance。 we could make a rapper indeed。

 That will be the right way to do it。 So what we're going to do。Is instead of this nonsense。Actually。

 let me see if I can do a slick move on you。Fun。F prime。Of n equals。Yeah， that actually works。Um。

You know。In fact prime。And end， okay， sorry， I know this is hard to read。

 but the point is that this guy。Is a separate thing。Thank you。 Okay。

 So well this is going to be the correct implementation because why when I call fact I make a singular rep cell。

 I allocate my rep cell that has one in it then my recursive function。

 fact prime actually goes and does the recursing and notably when I call fact prime fact prime doesn't allocate another store basically this is exactly the same thing as that right I mean this is exactly the same thing as that it's just that I put it inside of a function such that every time I call fact I do this instead of every call to fact being subserving it to the same ref yeah。

😡，Ref refs give me like 15 minutes， yeah。Cool， okay so if you want to look at my very hard hard drawn drawings I never used I'm really sad about boom。

 we go here and then oh my God， it's updated and then we go there and then oh my God it's updated and then oh my God we get four okay that was the TlDR all right bad。

 bad things happened， but we know how to solve it， which is this guy。

Okay notably this would actually be fine to do if right before you return to Bang of store or well what you do is you would bind the result of bang of store and then you'd reset the sort of one and then you'd return that that would actually be fine I'm going to say that'd be a bad style thing to do though like if you're going to allocate like are you afraid of allocating a singular ref cell every call of fact like。

😡，The the rec doesn't need to exist for every single call right unless you're doing some hardcore performance optimizing。

 Okay， like fact is a pretty trivial case。 So it's possible for this to be correct。

 but this is not okay， try to do this instead， make your reps local to your function All right to your to this first indication of your function。

😡，Okay， and I told you about all this stuff and that's the correct one， so let's go， all right。Cool。

And actually。And actually， we're going to get back to something that was mentioned in the very first lecture and it was mentioned by I'm not to ep your name by Arav。

 I remember I'm not to ep your name up because I want to post these videos but for， you know。

 but observational purity is when something uses side effects on the inside。😊。

But it doesn't seem that way to a color if I handed you as fact function and it had this implementation。

 you would have no way actually of knowing that it was this versus fact， good old fact， Homebo fact。

 the original fact that be defined on the first state class right or the second day。😡。

And that means it's observationally pure， so we also call such things a benign effect。😡。

A benign effect， basically like having this ref cell is okay， it's benign。 You can't tell， Okay。

 and at the end of the day， like computers are kind of like observationally pure things in some sense。

 at least in this class， right we're all running on bare metal。

 But the point is that like this is okay to do。For this particular example。

 there't a reason why you should， but sometimes it's okay to do as long as it's observationally still computing a pure function。

ok。😊，U。In 15451 which is an algorithms class， you race against other people by submitting a solution to some algorithms problem and you can choose whatever language and naturally you can imagine I did double them in SNL okay and by the way。

 I got like number 10 on a leader War I I beat C++ I beat Russ like I'm proud of that。

But I will not lie you that like I have done this thing where I allocated a private ref so I could read from standard input faster because I wanted the speed so like I will not lie you I have done this。

 but for this particular one there's no reason to okay no reason it's a fun class。Cool， okay。

 let's move on from observational purity。😡，We're going to talk about aliasing， all right。

 aliasing is going to be a good friend of ours where it's actually not and it's pointer chasing all the way down。

 but we decided to make our beds so we have to lie in it。😡，Crazy。It was all there？O。

And actually let me see if I anything else so one thing to note here is that we haven't dealt with the case where we actually。

B a variable to a preexisting ref。 we haven't really done that。

 but that is what we are going to do right now， okay。😡，And this will make up aliasing， okay。

 we can alias a point where we can alias a box。And I want you to be careful about this because I want you to make sure your mental pictures are good enough for this for the record of this is like easily testable content okay so this is our example and if I did it correctly it should exactly match what's on the board。

😊，So let's go through it。 Okay， let's start from the beginning。 and what I'm going to do is。

As always。Draw my store。Okay， first line， I say r1 is equal to the rep of zero。

 so one called a ref one box， right， so I get a box。😡。

And we're going to say this one is bound to r1 and it contains what0， it contains zero。ok。

Second line I say that r2 is now equal to r1 What does that mean remember I said the r1 is bound r1 is still down to a value right ref cells are values but their boxes so。

😡，We're just saying the R2 is also this box， not the contents of the box， but the box， okay？😡，呃，那可。

And then if I wanted you to the third line， I'm going to say， oh。

 this is kind of an interesting concept， I've got an inch ref ref。

 I have a ref that is referencing an inch ref itself。

 I'm referencing a reference cell okay which means that I'm saying the R3 is going to be a oh what's this。

 I have another called a ref so I get a new ref cell。😡，This one。😊，We're going to call the Sp three。

But this one is referencing this。😡，あ。YeahYes。No it's that'll get confusing fast contains is an imperfect analogy for what this means but the arrow is what's going to be better to say okay we call this we call this we call this a finger we call this a finger because it's it's referencing that yeah no it's called a pointer okay anyways so we have this box referencing this box right here and that's we're done with this right we're referencing whatever box was R1 down to at the time which is this box right okay。

😊，And then next， I say， oh， do I mess up。 I did。I don't want to take this board down， that R4 is R1。

 I'm sorry。I'm re I'm shadowing R1 with a ref of one， okay。So what do I get， Well， new cold ref。

 new box again so。New box， and this time I put one in it。Okay， and then R1 is nontt。

 so I'm going to take away。This binding。R 2 is still bound to it， that's fine， doesn't change R 2。

 but now R1 is this guy。😡，And now what happens if I do R2 colon equals three， well。

 I just go to whatever box r2 is holding and I change what's inside， so I go here。😡。

Take away the zero， put in a three。Notably， this indirectly changes， I say indirectly changes R3。

 It doesn't change R3 is value。 R3 is value is the same， but if I were to do。😡，bing。

Bang into the room on R three， I would get three， yeah。Yes。Yes， we'll see this in a second。

 We're also going to need recursive types do we need recursor types， roing use recursive types。

There's a review lab problem on this also。Okay， is everybody clear on this example here。

 just follow the diagrams， follow the the arrows， okay？😡，ok。Let's move on。Blah， blah， blah。

 nice pictures I'm not going to have time to show you， blah yeah， okay。ok。

This kind of stuff is pretty typical， okay， pointer chasing， I don't really enjoy it。

 but you know it makes for a fun classroom exercise。

It's easier to understand if you if you realize three calls to Ref， three brand new ref cells， okay。

 that's the important thing I want you to realize and I'm going to go and change this for posterity so somebody jumping in on the recording doesn't。

😡，Cruucify me at a later point。ok嗯。And also note that like we can't change the contents of the box without a call to colon equals so while we put stuff in the boxes the only time the contents of a box actually changed was when I did R2 colon equals 3 okay and if I wanted for instance。

 this pointer to go here， I would say what what would I say？😡。

What expression would I write if I wanted this to go here and set？What do you think。

Or I have this setup。Is equal to assign to。Yeah。R one。Just our one。Ooh， yes。

 this is a difficult thing to get across。 So the contents of the box are changed to what。 Well。

 I wanted to reference this box。 So I need to give it the box R1 is the box。 If I did this， remember。

 Okay， here's another easy way to remember this。 Okay， suppose I did this。😡，Well。

 what's going to happen here is。New box per called or F， so I put in this or this guy。Actually。

 this one in type check first of all， but for a second a bit bigger with me， if I did ref of R1。

 right， I get this guy， which is the new box they just made and then I actually couldn't do this as that would be unsafe。

😡，But like you can imagine， okay， yeah。What do you mean by non local？

If your intuition foreclosures should still apply in that if a closure captures a box。

 that the contents of the box can change at a later point on you。😡。

If I call a function where like that function F contains this box and I can change that box later。

 that box will still be changed when I go back to that function right okay。

 I don't have an example handy for this， but you'll plenty of practice on this on the homework。诶。

有 good question。Okay， well， all right， remember， okay， nothing special about boxes。

 they're just values boxes are values， pointers are value or pointers are boxes。

 let transitivity guide you from there Okay but that's the point right we can pass around boxes like values they are they are values Okay。

 a pointer is just an integer okay。😊，So。Allright and now reps within reps I kind of just want to show you that we can have reps I point to other reps so let's use this list type and I wanted to call alpha L list for a linked list except I realize I used L list in the last lecture for lazy list so we're going to call it a mute list but if you look at this type it should look very familiar to you it looks very similar to what we had last lecture I say that an alpha mute list a polymorphic type mute list can be either the empty list or its cons where the tail is a reference to another mute list。

😊，ok。It is a reference to another meatwi。And you can imagine the sort of zany hynkants we can get into with this sort of thing。

 but you don't have to imagine actually， because I will show you。I'm like'm like， what's it。

 I'm like Karon guiding you to the underworld。Okay， so here's my example for you。



![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_1.png)

I've got this code right here。😡，R is going to be an inch mutless ref， so I put it as ref nail。

 let's step through this code。😡，What am I going to say， what am I going to say about this？

What's the first hand I want going to say if you con into my patterns as lecture at all？4our。New box。

 one call a ref new box。 Okay， so what do I get， I get， I eraed my store。

 but this still is the store。 Okay， I get R is。Oh I okay， yeah R is going to be rep containing nil。

 which is a functional value that just fits inside of this box， yeah。

And then I say that L is cons of Os， I wanted to do this in a different way actually， sorry。

I'm going to put it here conspicuously。😊，And it contains nil， and this is R。😡，This is R okay。😡。

For this one， no box， right， no box。 I'm just going to say I now have a value， which is。

Good to look like this。Cons of one comma this box。And this is just like a value。

 It doesn't like really exist in the store。 So I guess like it would be inaccurate to put store。

 but this is how you can conceptualize it， right， I'm making a value where this R is a box that contains no cool and then this whole thing is going to be L。

😊，All right， and then what if I do， I say let me reassign the contents of R to be L。

 What am I really saying with that， This is why the box containing thing is imperfect because I would have to put this inside of this Like that's kind of weird right so here's what I'm actually going to do。

😡，Contains this an imperfect analogy。The box contains a reference to this cons cell。

 which exists in memory somewhere， okay， but it contains a reference to this cons thing all right。

 and if everyone's cool with this， I'm going to show you that actually，😡，啊爸爸爸爸。

Ive actually I've reproduced this exact example here okay and let me write a fun little function for you so if you believe me that this is the same as that I'm going to write a function called Traverse so I'm to take in an alpha mute list and then we're going to say if I get Neil I'm going to raise div otherwise if I traverse on cons of something and then R what I'm going to do is I'm going to first print I am going somewhere。

😡，And then do a sequencing thing， and this is how I prefer to indent these。

And then I'm going to traverse on。Bang of R。If you believe me， this should type check， okay？

And then that。It， let me do Traverse on L， yeah。Internet loop。Inthfinite loop because I。

Because I go here。you don't want to ask that this is like there's something like this on your over there。

Not like this exactly but you know what I'm doing is I'm unpacking this value and I go to it and I call traverse on this and then I unpack this and I call traverse on this and then I you know I'm looping forever all right I don't mind wasting computer cycles okay people who study machine learning waste like infinite like infinitely more cycles than I do on this all right。

😡，I could be doing worse。 I could be I could be training a neural network that then runs into a typo 5000 compute hours in and then crashes。

 Okay， I could be doing that。 People do do。😊，What is it what？Oh no， I don't care。

 doesn't matter all bets are off when you control de of the program。Yeah， it doesn't matter。 Okay， w。

 we're actually like still pretty good on time All right， cool。

 is everyone cool with this example and note that like we can make cooler stuff than this。

 I wanted to show you the cycle， but we can make a legit linked list。

 We can make a circular linked list like all bets are off right now one kind of cool thing to note about like SmL values right and recursive。

😊。

![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_3.png)

Data types in general that we've seen right is I can't really so far that we've seen in this course。

 I can't really have this case where I do node where you know node is the original tree we saw a long time ago where I say it's empty。

😡，2， and then like。And then like itself like I just can't do that right it's not really possible because how would I make this thing without being able to refer to this I could dynamically make like a new node in an infinitely loop。

 but I can't make it the same node yeah。😡，好。No val recursive only lets you buy into lambdas yes so even then yeah。

 yeah， and more likely than not what you're thinking of you'll get to an infinite loop it doesn't exactly matter。

 but the point is just how like SNL values like when we don't deal with this weird reference nonsense they they're very well behave because they look like this they all you can always draw that。

Unless you're talking about functions， you can always draw them。😡，You can always be like， hey。

 this is empty and you know。😡，Oh， this is node and then it contains two and then。

 you know there's something here， but it can't do this kind of nonsense。

 you can always draw on the board without cycles。😡。

Okay that's the nice thing about SmL values is they're always like some kind of trade， okay？

You can't have an infinitely long value basically because you can also imagine like if I did this。

 I'd have to use infinitely much memory to store it。

 but with reps like I can use indirect to reuse this memory。😡，ItDoesn't really matter。

 I was kind of like thought commenting。Okay， is everyone cool with this example。

 which is nicely illustrated as such， yes， cool。Okay， honestly， I have you for a bit longer。

 but I'm just going to talk about some cool applications of mutability if any of you end up working。

😡，In a language that strongly prefers to be immutable by default。

 which is pretty much every modern language， by the way， like when I'm talking to you about refs。

 like this is present in Ru， it's present in swiftift。

 it's present in JavaScript like this is generally how things trend like the fact that C doesn't have this is because C is a dinosaur okay I wasn't I didn't sign up to teach you dinosaurs but this so when I'm trying to justify you here is that what I'm going to say next is applicable All right。

Notability is generally a big deal， it's generally not a good thing。

 but we can we don't have to avoid at all costs。 there are some real things I use this for in my work and I just want to tell you a few like cool techniques Okay but before I say that actually I had a note which was。

😊，On the very first day I gave you this analogy and this analogy was like an imperative kitchen okay if we were talking about a kitchen is that all all the chefs are sharing the same ingredients in the same dining area does anyone remember this analogyy let's go they have the same dining area and you put down your complete pasta or macaroni and you come back to it and then someone's put marinara sauce in it right because they can mess with each other and I hope now you realize that this was this was a analogy for parallelism and mutability right and a functional kitchen。

 everyone has their own dining area or their own preparation area and their own ingredients so no one can mess with each other mutability is a really bad thing when you come into parallel programs as long as you have imutability sequential or parallel doesn't matter in parallel programs。

 I can't mess with other threads or processes or things I literally cannot immutability means it's impossible。

😊，In the sequential case， mutability can be fine， it can be fine， but。Parael， no man's land。

 no man's land， You all bets are off。 like if you， if you come to me。 Okay。

 and you you write me an email years later， you brandnda， you said mutability was okay。

 I was writing this multithreaded program and it crashed on me。 I will be like， nope， no。

 just don't don't contact me again。 You learned nothing。 All right， This is all bets are off。

 I can't help you。 All right， God can't help you when you're here。

 All right Muability and parallelism。 you're cooked。 You're done。 All right， so。😡。

For stuff like this， it's okay right， but suppose that someone had been running all these declarations at the same time。

 right， What is the what does the diagram become， It doesn't become a diagram。

 It becomes a probability space of diagrams。 It becomes a certain all of the permutations of these declarations possibly of diagrams。

 okay。No one can cze that in their brain okay exponential state space blow up so you're you're just you're done all right that's why I wanted to get across you and if you take 15 to 10。

 they will drive this into your brain more。Okay， and I'm going to show you some。

 but as an aside that was inside， I will show you some cool techniques with mutability okay all right。

 and also like yeah， purities of trap， remember， we make immutability work for us。😊，Alright。

One technique I like to use a lot is fresh identifiers this is maybe more useful in like a programming languages context。

 but actually I think it's pretty pretty universal so basically the idea is suppose I have like nodes in a graph or people in a database or variables in a program or transactions in my bank system and I want to make sure that each of those has a unique identifier why because I want to keep track of it and I want to be able to uniquely reference it and make sure that I know when these transactions are the same。

😊，You might think in a functional setting， that's kind of hard to do because like isn't the point I need to generate like new things。

 well ref cellss are a very easy way to do it。😡，So the simple way to do this is I keep a store at zero and I have a fresh function which is a type unit to in and all that happens is every time I call freshresh I increment this store that exists somewhere in the void and then I give back whatever it's at so you know the first time I call this I get one next time I get two。

 three， four but I guarantee that over a program's lifetime I always get unique identifiers okay。😡。

Does anyone see how this works？😊，Yeah， I personally really like this because this is very handy for my line of work okay but like transactions in a system people in a database like this is generally applicable this is a good like disciplined use of of imutability you know if you're calling dot fresh which takess in a unit and gives back an int。

😊，Usually it's also clear from the type like yeah， there's some mutability going on here， okay？😡。

But another thing that's cool about this is。😊，Or not cool about this is this thing gives me back ins。

 but all I wanted the ins for was to be able to guarantee they were unique What if I take that int and I subtract three from it？

😡，Accidentally， I didn't mean to， but I subtract from it and now I'm holding an int that's the same as another int in my database and then I compare them and I'm like looks good。

 they're the same， but I missed the part where I did some arithmetic to make this not safe You get what I'm saying like the fact that it's an int means I can mess with this invariant I sort of have that unique int should be unique well。

 is what is an invariant soundm like well it sounds like a puncter to me or it sounds like a structure。

😡，So what I can do instead， this technique is fine， but to make it even safer。

 that should be signature， sorry， I can make it a signature which has an abstract type T where freshresh gives me back a brand new tea。

😡，And then I also need an equality function that tells me if two T's。

 two unique identifiers are the same， right because otherwise I can't use them。

 I'm just holding the Ts and I can't do anything of them。And if I have this signature。

 I can make a structure that ascribes to it opaquely where I do the same thing， the code is the same。

😡，But now I hide the fact that it's an int and I can guarantee that if I'm holding an abstract unique identifier。

 I can never change that identifier， I can only pass it around and if you make a mistake at that point that's on you all。

 but note that I need this equality function because otherwise I would not be able to compare two unique identifiers。

 which is the whole point。😡，Okay all right， so fresh Is that's one mutability technique。

 another one's called hooks and this mostly comes up in the context of like compilation troubles which you know I'm not necessarily sure you're familiar with。

 but let me paint a picture， which is that。😡，Like， I've got code， right。

 And this code exists in like different files and the code is dependencies， right。

 Like suppose that I have。I suppose we're working in SNL， right？And I have a file Ada SML。😡。

And this AA SL file is actually used by another file called B do SL。😡。

And this beta S is used by another function called or another file called Cla SML。😡，So it goes here。

This is generally like a bird's eye view of how。Deencyencies in a project work right you can imagine the situation Well this means that C can use a function that's in a but it doesn't go the other way I can't freely use necessarily something from C in all cases the compiler is going to yell at you and itll be like oh dependency alert and this is really freaking annoying by the way。

 but this happens for like pretty much everything so I can't go this way this is impossible。😡。

But suppose that there's like some logic that lives in C that I really want at the time of a okay like maybe C is like computing some like hard to do function or has types or it has data that I'm not privy to when I'm living here in a okay could we factor the code but sometimes that's really hard to do My point is that this technique will mean that we can freely do this kind of thing via a trick。

😡，嗯。And there's lots of reasons why this might happen。

 but what we going do is we're to call it back patching， basically a is going to set up a box。😡。

And in the box is going to be none。😡，But at compilation time， before any code really runs。

 we run all the top level declarations， which means that before A do SML or B to S or c to SL really runs。

 I can have some code from here injected in there， so I'm going to turn this。😊。

I'm just going to leave it here for a second， but I'm going to turn it into。Some of F。

So that by the time that a is ready to use it， this thing contains some code from C and what you'll find is actually this is a perfectly valid thing right because if a to SMML is like。

 hey， I'm giving you this Ref called R。😡，C that SmL can then later say r colon equals 2。😡，Some。Of F。

 right， that makes sense， right， because remember， C can use stuff from A。

Does this make sense to everyone， or is this like too abstract too pest？Okay。

Like that point is like if I， if I give you a ref cell。

 that means I can now change data temporarily in the other direction。

 irrespective of of dependencies， because I can just put something in the box at a later point。

 That's pretty much exactly what this is。 Okay， a hook is a is a ref of type T option ref so we'll say I have a function I need。

 but I don't have it at this point。 And this is in ada SML。

 say it's sub type into inch ref into inch option ref。 I put none in it。 So I put none in the box。

And then like later on in C， I say， hey， I have this a cool function F and I I know you need it。

 so I'm going to set the contents of this box to be sum of F。😡。

This function F that I have that you need and then now when a runs it has access to the box it has access to the function we call this like hooks this is useful if you want to like dynamically change the behavior of a function but you want like a user to be able to do it actually the SML andJ compiler behaves in this way in a certain sense there are some reps that exist in the SML top level and you can like change them and it'll change how the compiler behaves so this is like the same technique applied for instance theres there's a rep I use when I was debugging the NJ bug where like you could do debugging and it was a blue ref。

😊，But what I did is at the NJ top level， I kind of just said colon equals true and then the NJ compiler changed its behavior because now it is reading from the same place。

 so the dependency goes backwards kind of in aence okay my my behavior now can be dependent on stuff later which was just kind of the whole point I' me to build it right。

😡，Okay， that's hooks， sorry if I was a little abstract， but I't know。

 I think this is a really useful technique genuinely and then I have one final example for you。😡。

Global settings suppose I'm writing some kind of function， some kind of code， some project。

 and I have some debug flag someone needs to and if you think about right like if you ever use like a。

😊。

![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_5.png)

Like some kind of command line program， I might say like Snl dash a debug。

 and that doesn't actually exist as a。As a thing， unfortunately。But I'm not going to find one。Yeah。

 I'm not going to find one but the point is like I can usually set some kind of like setting equals to like false right and I want that setting to persist over the course of this program's runtime。

 the whole time that this program's running， I want this setting to be false。Well。

 suppose that it's actually a different one， suppose it's a verbose。Like have you ever。

 has anyone ever like worked with like a command line program where you set for both to true and now like print out love stuff？



![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_7.png)

In SMmL， you could conceive of writing this code as such， I have like some function， initialize API。

 and it takes in an explicit parameter is verbose， and I case on it and then I print it out。😡。

It's not so bad， but you have to think about the fact that like now on every call to this function。

 I have to pass in my I werebo value right that's painful。

 supposeuppose I had like 20 different settings that could change then I got to pass all of them into this function。

😡，If I pass it functionally， that kind of sucks okay because it's not going to change over the course of the program。

 so to show you what I could do differently。😡，I could do this。

I kill the Iverbo I set up a blue ref called I verboose somewhere like at the top level like up here upstream at Ada estimatet at the very first entry point to my function。

 and then I just like bang it I like do referenceence it and I get whatever's inside and now I don't need to pass around Iverbose all the time This makes my code a lot cleaner at really no cost because I don't expect the contents of this rep to change over the course of my program gives me sensibility too because I can change it dynamically now。

😡，Mutability but in moderation， it's helpful， it saves me some code。

 but like for these cases it's like very much clear that like I probably what's the worst case that could happen。

 like very little precious little， it's very hard to make a mistake with this。😡。

Does anyone to Alex example？😊，I don't know， this is something I think about at my job， but like。

Your mouth may vary， but I think this is a genuinely useful technique you could use in any sort of context。

O。

![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_9.png)

All right， and then something I didn't do earlier。All right。

 well actually this this is lazy programming so I don't why I have that open。

 I'm not answering that one。😊。

![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_11.png)

All right cool nothing nothing okay， that's actually the end of the lecture but yeah I'll take questions now Thank you so much welcomelcom to imperative programming your life is ruin。

😊。

![](img/cfad9e592e2bf0e487bb2cd10fcb91ad_13.png)
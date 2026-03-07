# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p06 P7 -BV1qBqPBYEy1_p6-

Oh that you。Okay， so this week a little bit of a change of pace and we're going to be doing a little bit of。

Review of the structure of the Sia。So you heard from Dave Vga last week about a lot of the motivation behind the we。

And the language， what we're going to do this week is take a look at some of the internal structure so you know what we did a while ago was look at the specification of the Java VM but we didn't look kind of inside to see how it's implemented the specification just goes on and on and on and on and on and on。

But for the self， you'll find the specifications， you really sure we'll be able to review the whole thing really quickly。

 give you a feel for what it does。And then then we'll actually start looking at some of the internals and even though this is pretty old stuff now it's kind of 20 years since it was last under really active development。

 it's still worth， I think studying， you know there's the sort of selfish spec region reason that I'm just familiar with this coding even though it's been 20 years they're still recognizing。

 but you'll see that if you look at the Haspot JVM or the V8VM that was written by La back who did both of those systems。

 started both of those systems。Or I imagine any of the other VMs right。

 you'll probably see a lot of familiarity in structure because so many of the ideas were pretty influential and have've been carried along。

The only real difference， some of the biggest difference is that this is a unit process of EMM。

 it was built in the days way。You bought a computer。

 there was one CPU in that period unless you bought something big in a machine room or if it was on your desk。

CP。And it didn't look like that was going to change for a while and 32 bitts was where it's at got sort of 32 bitness and unit processing stuff to sort of really deeply back in。

To how it's done and the big deal in developing something like hotspot was figuring out how to make it truly multi threaded and scale。

So that will be the subject。Withcoming material。So I'm going to talk mainly to the sources as they currently stand。

 which is not exactly what I remember from 20 years ago， there've been a little bit of work。

 but I've been looking at them and there's not that much difference。

There are also publications that span a period of about 87 to 95 when it was under very active development the papers。

And the material we're looking at today is mostly about the storage organization。

 which didn't change that much and was was described in an early engineers thesis by Al Jim Lee。

Which is a pretty good reference for it， but there are some differences between the thesis and what's currently that。

So I'll try and keep it on the current version so if you want to go and look at the source you can go and check the source out。

 in fact I'll be having putting up quite a few fragments of source and I'll put the names。

 the files and stuff that you could go look at it if you start at selflanguage。

org there's a point to the GitHub repository。And it's all written in C++。

And you'll see that' sort of important。Okay， so first thing is。

 I'm just going to do a very quick recap。Of the language itself to give you some to give you the context Now hopefully you've had a look at the self of the original one and got some understanding of the language。

 but it's a pretty small。Self contained language so first thing is you have objects。

 three is an object， 4。2 is an object。If you want to make an object with two slots。

 you just name them X Y， if you want to initialize them， you can initialize them。

 you can initialize using equals， which means it's a constant slot and can't be altered。

If you initialize using an arrow， then it's an assignable slot。

 once you've got one of these objects that's like this you can access the X field by sending X。

 you can sign the Y field by sending Y and you can set the Y field by sending Y column with the argument so this is an example of assignment。

Makes this object assigns five to the wife。And you can this is the textual form rather than the graphical form。

 we could do the same thing on the screen using the graphical form。

 but this is a little bit more concise。So this is a textual form of two of nested objects。

 I'm making a rectangle with two subobjects with a origin or a corner。I can show you that。嗯。はい？一吧。

So there's an evaluator I if I' just。P said。Put the thing in my hand。And one can look through。

Some on civil objects。么给。And it's all， as I described。I just question。

 honest does work if theyre cycle。呃。Let's just draw arrows and stuff， what's the issue。😀呵呵呵。😊。

Whi just connects。The do with the thing it's pointing to。

Do you mean if you have something self referential？这I don't know不。

So that should be initializedop to know。什 now。pointiner。Drop down there self ref。Yeah。I say。皮衣。

IShould。Just wait all and says I' man。O。Allright， so methods are just coded that's put in slots。

 so here's an object with an X and a y and I'm giving it a row slot which contains this method。

Wwhich just sends square root x， square of y adds them together。

 sends square root to the result and so if I get that objective， I've put this in a variable。

 there must be a P declaration somewhere up there， so three and four to x x and y to 3 and4 and call row。

 I'll get 5。0 of the result。Do square with sum of the squares。And once I've got an object。

 I can clone it freely and there's a primitive in。Self a clonening it's a shallow clone。

 all the primitives in begin with an underscore， you can't write methods with underscores at the beginning。

 there are the things provided by the VM。And clone will just shallow copy an object。我 know。Okay。

 so I can also make slots that are parent slots for inheritance。 So in this example。

 I had that one before with an X and a Y in a row I'm making this object cu with a parent slot。

 and it's not apparent because it's called parent。 It's apparent because it's a star at the end。

So the parent law is P， so this object cu is going to inherit from the previous one。

It has its own X slope。Which is distinct from the in the parent object。

And I'm giving it a row method which just invokes the inherited row method and converts that to a string。

So if I send x to this guy， the x will set this X and not the other x。Why will set the other why。

 he inhered why。And if I send row， it will invoke the other row。

 which will do x squared plus y squared square root， but when it sends x to itself。

Because of the resend， you get this X， not the inheritance。

As you would in any objectorious languages right， pick up the bottom definition unless you're doing sort of deco equivalent super。

So this one would take the 10。That's in here and the ten that's in the upper object。

And do the calculation。Control structures are expressed using blocks and block is just small talk speed for closure。

So anything going beclo in square brackets is a closure。And if I want to。Do a conventional。

 if then else， what I do is I have an expression that evaluates to a booion， and I send it。

If true falses， this is a compound selector。This is one message with two parts to the name。

And passing two closures。And if you send that to the true object， it evaluates the first closure。

 if you send it to the false object， it evaluates the second closure， so that's how。

Its analysis done。Oh， that's implemented。In the language using the conditional behavior of dispatch to give you the yes but priority to P and4 to Q and there's a symbolic I'll do Yeah。

 so the way it works is the urary messages the ones with arguments bind most tightly So if you want to parentthesize this。

 you parentthesize first P sending row to P in Q row sending row to Q。And then binary messages。

 which are only symbolic ones bind to the next most tightly， so then we're doing the comparison。

And then the keyword messages are the least bindingy， and so if true false。

 this is you can tell if this is the same。Thing that they're part of the same message because this begins with an upper case letter。

If this began with a lower careler， it would be another message。

 so every message begins with a lower care sliceler。

And continuation keywords all begin with upper case letters。

So this is a single message with two parameters， and these are square brackets。

 they're not parentheses， so that's just an object。Constaining some code。

 why was the decision made to have closures in spite of it and rather just having lazy setics for the impulse？

Because it we sure have dare that not make sort of。Projecting。Basically。

 it's the same message sending semantics for everything and the laziness is in the objects。

 so in this case。Objects that contain code。Can be evaluated later than when it created。

 let's say what was done in small talk。So this is actually， if you're a small do programmer。

 the only thing that would be different here is it didn't use the Ca convention for continued names and so that would be an if false with a small eye。

 but otherwise it would look just the same。Okay， and then you can also use closures to build other control structures so the standard。

Conventional loops are built the same way， so this is a message to a closure that passes another closure。

 you evaluate this one， if this is true， you evaluate that one and it recurs。

And I'll show you how that's implemented on the next slide。

And then the only other thing is in a closure， you can return by aar before the last expression in a closure and what that does。

 it doesn't return to the thing that invokeked the closure it returns to the method。

Which invokeked the method to bend the closure， so it returns from this code to its callline。

They're aligning all of the stack frames in between， they'll just sort of disappear。

So that's a way of breaking out of the loop here， this return here would break out of this loop and return from this method to its enclosing method and that also is a small talkism。

It's kind of almost like a continuation， but not quite。You can only return from Mc block Walalcom。

Return multiply doesn't keep copies of all the stacked frames from example。O。And then so the methods。

 the only ways of building control flow， and this will become relevant when we talk about compilation and inlining because you have to sort of make everything out of this。

I you get to invoke a method which is use sort of standard method in location semantics you can invoke a block so basically when you write this it's a shorthand for making an object with a value slot and the value slot returns a method whose code is this so if you send it value you'll run the code。

You can also have parameterss at the beginning and have a value with parameterss。

And then there's a primitive that just restarts a method from the beginning。

 and that's the only looping construct that actually built in just。Other than recursion。

So that just restarts the things so the implementation of loop on blocks is exactly this。

You send a loop to a block， it evaluates the block and restarts this method。

And it would just be an infinite loop。But if the block contains a non local return or another enclosed internal block contains a non local return。

 then that will break。So normals were returning this deal the trial and that's it。

 that's the entire language more or less I might have missed one or two tiny things。

 but that's pretty much it。The only other primacy how I'm going to mention。

 primitive behavior is that you have vectors。Which unlike the standard objects which have name slots。

 have indexable slots， so you access a slot by number rather than by name。

So that's a sort of a primitive。Capability that's built in。

 There are vectors of object references and bike vectors which can contain bike values， you know。

 not to 255 in each slot。And they are prototypesite by vector by vector that people can copy to make nuance。

 So this says take。Copy is the prototypical vector giving you a new empty one。

 this copy is now adding one element into the vectors and then we have an vector of one element containing seven。

And this pulls out that element。And passes that number seven as a parameter to this guide。

 which copies the process by vector making a seven element by vector with zeros in。Okay。

 might's so build up to。How the actual system sort of works。

So one clever trick here is the way in which methods。Are activated or a model for method activation。

 So the model for method activation is when you invoke a method on an object so but you send a message to an object。

 you look up the slot corresponding to the name of the thing you send， if that contains a non method。

 you just return that non method。But if it contains a method。

 you invoke the method and the way you invoke is by taking the method as a prototype for the activation frame。

 so the method has slots for the arguments and the locals。

He basically copied the method as an activation frame。It happens to， of course。

 have code that already comes with its code。 and you bind in the in the。

Creation of the activation record， you make the add slot called self as a parent which points to the self of this message。

So now the context of the method has the slots of the activation record as the things that are closest in scope。

 and then the slots of self are the next things in scope quite apparently。

So it's kind of a nice unification of objects and cloning to explain how methods run。

And then methods themselves， when you compile a method， if the structure looks like this。

 it has a protoypical slot for the self field and any arguments that might be in here as well。

A reference to another object which is a code object。

 and then that has subreferences one of the bycodes of the actual method that are going to be running and then to another thing which is a vector of the literals that appear in that method and mostly the literals are either things like numbers that you happen to mention。

 but mostly the strings that represent the names of the messages you're going to send。

So if you look at this example， this is going to do that is printing a point so it's going to send print to X。

 print to Y， send comma。To concatenate them。And that's the result and sos the first thing is aend of self of the zeroeth n。

 which is x， then the next one sense print the result of that stack machine as usual。

And then a comma。Its pushed onto the stat。And then we do the sample Y and we send。We send。もてかもといがしや。

Since they saying。M and seems to be as sending。这你在起说这会好吧。

But it's fairly standard kind of you know bikecode。

 stack machine and stuff now that here's the difference with the Java of this is the entire bikecode stack。

我们。This is it， there are only eight， at least in the original version。

 the latest version I know just to added a few because it was used as a way of implementing some other languages on top of self and there was some branching and bodycodes added on lot others the original had conveniently eight。

 which is which there was only three bit out there。

And the bike codes push cellphones the stack or push a literal onto the stack with an index that tells you in that literal vector。

 which one you're going to push。end。The message is named at a certain in text to the thing that's on the top of the stack and if it has arguments。

 then pass the arguments to and pop the receiver and the arguments off。

 put the result back in it in their place。A self send is the same the self is implicit and that's used a lot because the name of the language is kind of a pun here。

 a lot of the code is sending messages to self and so this aligns the one push itself。In that case。

A superend is the same thing except when you're invoking an inherited method by directly looking at a parent rather than sending to cell and there's this twist which is because you can have multiple parent slot。

 you can choose which one of them to sort of do the delegation down so that's this bikecode here almost never used in practice so there's really only seven that is actually commonly used。

The nonlical return bikecode which exits blocks with non-l returns and then you know you've got these single bikecodes with indices。

 five bit indices， well five bits is not very much so there's a single bikecode that says is another five bits found onto the index of the instruction that follows and you can have as many of those as you need to build up the index that you want put to the system limits of the machine which is basically 32 bits stuff。

So it's really very， very simple and clean。Not designed with performance in mind at all right it's a very clean unoptimised kind of thing the compiler is very dumb。

 it's basically just sort of matching up brackets and emitting。

Vcodes a very simple kind of AST walk you thing and the magic is all in the ViM that has to take this and generate really good code when you write。

 say a loop。We see messages in it。 So if performance is not of concern。

 what is the purpose of the self center？嗯。就是第。I don't think so， I guess you could do it。

Just by pushing yourself and doing the other one， I don't know why I guess that had a space for an help code or about three beds。

Why not fill the all A out don't know I think minimally you could do it but get by with just。This。

 this is a short hand for this one。Yeah， yeah， so I think and it may be that in the very first one。

 they had only the minimum five。But sir。This is the again， this is just copied up。忘记。Okay。

 so that's sort of， you know， that's what the VM is meant to do。

 it runs these bikecodes in a system that looks with objects structured as it was before and it has to try and get some decent performance out。

So we'll start looking at how it accomplishes that。嗯。

Let's start with a heap structure because kind of follows on from last week when we talking about generation scavenging and this is a generational。

System it has a generational heap structure and a collector。

 so it organizes that he it two generations are young and old and the youngest sp to eat and from and to in the sort of a classical way in the paper that you've hopefully read。

And when I have this courier， this is the names of the file so you can find that。The source code。

So I showed you the system running last week with a spy， which is this graphical view onto the heap。

 and this is just a snapshot。Of one of those。 So over here are the tiny little。

 this is the Eden and the frorog and the two。 and then each of these is a segment in old space。

 so old space is segmented。You can add more segments。As you're running and in fact。

 the system can give segments back to the O if it doesn't need them and each space is filled in from the ends inward。

 so this is sort of the diagram rotated 90 degrees。 This is just paste from our paper。

So when you have one of these segments or one of the new spaces。

 you allocate objects from the left in increasing address dress order。

 but objects that contain indexable bite slots。Those bike parts are allocated from the right going down。

And the point of that is that when you have a bunch of bytes in memory， when you look at them。

 there's no tagging， there's no indication of what the content is right。

 if you look at one of those words。It could be anything if you put a taggged interpretation on it。

 but it certainly isn't going to be a reference， it's just a bunch of numbers so you don't really want the garbage collector to be looking at those words it's pointless。

 there's nothing there that's going to be an object reference and so by segregating those by exam。

Into the upper part of the space， it means that the scavenger doesn't even have to look up here。

 It just scans this lower palm and this stuff gets copied， but it doesn't have to be scanned。

 so it's automatically segregating that stuff out。 It also means that everything at the bottom is tankgged uniformly。

Which gives us the ability to pass that area in either direction。

 we'll get to that and when I show you the mark of the tagging scheme that's adopted。

So we've got this split thing and they just grow towards each other and so the allocator has to check whether you know there's basically two allocators。

 one for when you allocate an object without bites and one when you allocate on with bys and the one without says I'm going to bump this is it going to bump into that guy？

And the other one has to say， I'm going to move these towards each other with the two parts。

 the two fingers meet。Does the bias area also get compact？Yeah。😊，Yeah。

 so both regions are compacted as they're copied。So you always end up but the pictures always look like this。

 a black thing to the left。A black thing at the eye。

 optionally this one can be empty if you have no bite objects here。

 but you can't have bikes up here where objects stand there。

 so if there's this there has to be there and then a light free region so bomb allocation of both ends going towards each other。

Okay。And that's the same for all of the segments。Spaces and this。

 so each of these blocks in this picture is an instantiation of a class。

In the source called called Space， so and there are some classes for old space and new spaces because the behaviors are a little bit different。

 but they basically behave the same。Okay， so the tagging structure。

Every object reference is 32 bits in the system。And those words are called oops。

 the word oop comes from long longer ago in the dim recesses of small talkque historyster。

And it stood originally for ordinary object pointer。

 so if you look back in the early small talk implementations。

 there were 16 bit systems and it was fit a 16 bit word with a one bit tag to distinguish a 15 bit end from a 15 bit object table index。

But the word UPA stuck in a lot of VM implementation stuff。

 and so you'll see the word a lot and in fact you'll see in the code it's all over the place so every 32 bit object references a new。

And those things also exist， so those things exist in the He， they're in registers。

 they're on the stack and they're in VM data structures and they're always intact Tgged form when they're called oops and they have two low order tagbits。

And the tagging scheme is this， you have a 00 represent an integer。

 which means when you wanted to add two integers， you don't have to do any tag extraction。

 you just do the addition and check for overflow。Similarly， for sometract。

A lower w represents an object。And because this is odd。

 if you inadvertently forget to strip off the tank bit when you do the dereence。

 you'll get a sec fall because it's not aligned。Then lower 10 is a flow with two exponent bits missing in the most recent system I noticed there are if deaths for either removing the exponent bits or the an bits。

 which is kind of weird。Don't know why。They chose to have。Both of those there。

 but there's some stuff in the comments about that。

 I didn't have time to really get to the bottom on it。

And then the interesting choice here is one one。Which tags only the header word of an object。

So the header word contains a bunch of ancillary information， there's an area for a hash code。

 a similar to Java you you can ask for the hash code of an object which is some stable number based on the object's identity and there are some age bits for the generational collection and random other bits。

But the important thing is that these are the only words in that left segment of a heap that tagged11。

 and so you can go from object to object up and down just by looking at the tag bits。

 you don't have to understand the structure in any fine detail on that。

You can scan only for the markets and that's used the lot in the system you see as we get towards it the scanning the heat is an important property of the system。

And that enables the construction of a really fast scan。嗯，什么事的。So because of the float tagging。

 was there a bunch of a arithmetic to do with actual flow point， yeah？

I think it may be that the representation is such that for some operations。You can do。呃。

Floating point number and only do some bitwidtling on the result to compensate for this bias because I think this is in the exponent field。

嗯。Well I'd have to check that to。That's dredged from the back of。嗯。Okay。

 so perhaps the most important。thinging in the heEAP organization is the use of maps to optimize the representation of objects。

Centralize the object behavior and metadata so that you're not wasting space。 So if you。

 if you think about。What a prototype would look like a prototype based system compared to a class based system。

 if you did implementing things naively so in the class based system。

Objects have class pointers that point off to classes and classes contain the metadata and so when you make an object you it just contains the variables that were specified in the class plus the header information。

 If you implemented a prototype based system naively。

 you'd have to list all the slots app with all of their names and values in the system。

And you could maybe abstract have the methods， but this big space penalty for doing that。

 so instead of doing that and paying for all the spaces。

 we use a different scheme which is called a map in some of the Ms' called a hidden class。

And the idea there is that you abstract how all of the metaada are describing the slots into this object called a map。

So this is not a user visible entity right you can't get a reference to a map ass a cell program and they're all hidden in the system。

But there is one for every object that you manipulate and what the map does。

Is it contains a summary of all of the immutable parts of the object which could be shared when you clone the object with another one so if you have methods those are immutable and when you clone the object you would share the methods if you have slots which are constant slots those are immutable and they can go in the map as well。

 they don't have to belong in the individual object。So the map。

 the object now contains the data for the mutable slots and the point it to the map。

 and when we clone it， all we have to do is clone the body and we're good to go。

And in this kind of system， object creation is always by cloning。

 you can't just sort of synthesize something out of thin air you always have to make。

A copy of an existing thing， when you start the system up the keep is populated with a bunch of prototypetos for the objects that the VM knows about。

 the language level primitive object。Yes， just to be clear。

 the superclass pointers are pointing to other class based things。

 parent pointers pointing to more map things Yes， exactly。 So in this one。

 the super class would point to another class in here， parent and map points to another map Okay。

 so what is an instance format。So the instance format here describes how this guy is laid out。

It would have things like the length of the instances if they're fixed object length objects here there's the same kind of thing it has to describe the length and the layout information。

We'll get the names in more detail。Also the name can be required in the map so so the names of the slots have to been here in similarly in the class the names of the inconspirables are in the class too it may not be there right I mean if you're using glass space systems。

If it's dynamic， it has to be， yeah， I mean， you can throw that way of stuff away if it's a static thing and you're never going to need it for reflection or anything。

But even in Java， it maintains all of that stuff in the event that you reflect on the plan。Okay。

 so each map then contains。A list of things called s descriptives。

And a slot descriptor names and categorizes the corresponding slot in the object。

 so the slot descriptor has， the categories are basically， first of all。

 is it assignable or constant？If it's assignable， there has to be a word reserved in the objects to contain the assigned value。

And it contains in the s descriptionscript or the offset of that word in every corresponding object。

 if it's a constant data slot， then it just contains the value of the field。

Methods have argument slot。hich have to be distinguished from the other kind and so there's a tag that says this is an argument slot in method。

And then it also needs a separate bit to say whether the slot is apparent or not and lookup has to proceed through that slot or not。

 and you can look up through constant slots and you can look up through assignable slots。

 parents can be assignable or constant either way。I don't think you can have。Parent arguments。很清楚。

At least I've never written a line of code that did that， but I'm not sure whether it's。我た明白系。

It's an interesting data。あ。Okay， so these slot descripts then sit in the map。

And describe basically all of the behavior and the layout for every object in what's called a cloned family so when you start。

 as I said， you get a prototypical set of objects that the VM says oh here's the prototypical vector。

 is a prototypical bi vector， here's a prototypical this and that。

And then you clone things from there。And whenever you clone， by definition。

 it will be in the same cloned family and can share the map。

Now we get to the point where you can start actually altering the structure of objects and what effect that has on mapped later because those are what are called programming parameters Yes so you said there's a bit is it a parent slot。

 does that mean that it has an entry for for example。

 there's X defined in the parent of that object the instance of the object also say that yes。

 I have an X which is in the pair or does it just point in the pair so in the slot itself has to have a name in the map。

 it has to indicate whether it's a parent or not。If it's a constant slot。

 then the per is in the value of the constant slot field。And most parents are constant loss。Okay。

 if it isn't a constant parent， then you just have an en tray。

 an offset that says where in the object the parent is kept， the reference。

Assignable parents are very rarely used， very rarely used， they're almost invariably constant。O。

So when you clone an object you， the clone shares the map。With the original。

And that means the clone premiseitive is really quick this basically it's just a me copy of the bits。

嗯，知大群里看。When you alter of the structure of an object。

 and you can do that using a variety of what are called programming primitives。

Then you have to start doing stuff to the maps and mute in them， so for example。

 one of the primitives you can invoke says here's an object containing some slots。

Here's another object contending some slots， build a new one that's like the union of the two of them。

 add all of the slots from this guy into' to that guy and make me a new guy that has。

 so if this guy has an X and a Y and this one has a P and a Q you got a new object with an X and a Y and a P and a Q。

And so when one of those premises is run， it obviously has to compute a new map。

For for the merged object or a mutated object。 But once it's done that。

 it then goes and looks in a map table that has a canonical version for every different structure so that if it happens to land on a structure that already exists it throws away the new map and just references the old one so you don't get you never get two maps that describe the identical structure。

 they're all different in somewhere。 they're all canonicalized and that saves a lot of space while while you're programming because it means that you're not you know duplicating methods and stuff。

Whyever you to alter the structure。So the layouts of objects then look something like this。

So I've e listed just three kinds here here's your standard kind of name slot object and then this is an object with index slots。

 but the indexes are the index elements are references to other objects and then the other kind of object is the one that contains just raw bike fields that are indexable。

So in the named case you have a header， a header word， and this is the guy。

 this is the marked word with a one one in the lower door bits。

 there's a map pointeder to the map and then the slots are just contiguously listed after the map。

 and so the map has to describe what each of these guys is in the slot description。

The indexable this is a vector has the same header and map pointer layout。

 but then it has a field which contains the length of the array of things that follows and then there's the actual indexable slots that follow that so this is used for bank checking whenever you access。

And obviously， you can have multiple vectors of all different length。

 so each has to have its own copy of them。And then the bite guys look kind of like that except the bites aren't listed directly there。

 we put the bites off in the upper part of the space and we have a pointer here so we're paying the price of an indirect to get at the bites but we've segregated it on the muff into this other space so we don't have to。

That was a good trade off way back when memory resume only 10 cycles away 20 cycles away。

 you know for modern programming language is how they do the method the name look up。

 do they just do a hash table then it varies by do they just do a stream of care and all so I well so there' you know there's two parts to that the answer that one is you know what does the language mandate in terms of？

Thelookup algorithm， and then the other is how is it implemented？

Most do sort of strengthen pair logically。 And this logically does strengthen pair too， but it。

Avoids those string compares like the plague， so there's all sorts of lengths gone to to avoid having to do lookup by string comparison。

Instead， they're always cashing sating。And I don't know the scheme to avoid them。

 but the simple implementations of things tend to just do the string of dias。Okay。

 so one thing that this doesn't address some languages like JavaScript have the ability to have。

 you know the objects sort of add slots as if the program is running and that's assumed to be a common operation this doesn't this assumes the structure of an object in a running program。

You know， but speed is constant and we're not going to add fields to it dynamically while it's running there's a fairly big performance hit when you do that those things are assumed to be invoked either by the programmer or tools running on behalf of the programmer to do mutation but there's no assumption that running programme will do that regularly all that they have to be optimized so in a later lecture we'll look at how we do variable structures and try and get those efficient but this system didn't。

He tries to address that。so even using the program impitives。

 you cannot change the structure of the existing。Well， so yes you can。

 I have an explanation that in detail， it's basically the programming premisemissives are written in a functional way in that they always make new objects。

But then when you're done there's a way of taking a new object and saying this new object now is going to stand in place with this on one。

 then that's the way that sort of loop closes。I'll show you that。 I'll try at the end of this slide。

Okay， so we'll take a little bit of a digression now into the implementation。

So you've been you writing VMs now in C and you've probably discovered。

For yourselves now it's kind of tedious doing this in sea you know you end up with an awful lot of unions andstructs and tags and macros and you know am I one of these and am I one of those and you have to come up with all these functions which either dispatch based on the type of the thing that you're doing inside the function or you have multiple functions with slight variances on the names that you have to do your own and it's just like a massive pin。

So。It would be much nicer if we could program our objects in an object oriented style in the V。

And self。Manas to do this。And sort of alias is that a clever way。

 C++ objects onto self objects such that you can do object oriented programming at the VM level to implement the object oriented programming at the self level and there are a couple of tricks which are fairly subtle that I think are worth explaining。

On how it does that。So you start with an observation that simple classes andstructs。

 simple classes in sequence plus and seatstructs are basically the same kind of thing。

 they just sort of template overlays on a piece of memory that give you a description of how fields are laid down and you can point to anything in memory。

Do a cast and say， okay， I'm going to pretend that this chunk of memory now looks like this object。

So it gives you a way of looking at chunks of memory as objects in C++。

So that's the first part and then the second part is if you add a method to a class in C++ and you don't make it virtual。

 it's a statically bound method。嗯。The actual value of the。Poiner to that thing。

 is it relevant when you involve the method， it's statically bound。

 so if I write if I call method f on P。And F is a statically bound method。

 the value of P is not used in looking up that method right that the call to P is bound at compile time。

And this is irrelevant， this can be nu， In fact， I've seen programs written。

 the test for this equals nu in such methods， it can be anything。

You're just going to call this thing and all it's giving you is a namespace。

 so you end up with a you know class name call on Co F and it's just going to call that so you have a way of invoking methods in objects which are just these overlays on memory。

Which costs you nothing or the you know and gives you this nice sort of namespace organization。

 So that's sort of the basis of this。 But then the thing is you want to do some number of virtual dispatches on objects because otherwise you just end up with building the dispatches by hand in all of your code。

 which is the thing we're trying to avoid and we can't do that by putting virtuals。

In all our objects， because as soon as you add a virtual method to an object。

 then the C++ compiler sneaks in a special slot， a hidden slot that you don't get to see。

Called the V table pointer， we did V table pointers a few weeks ago。And now when you write P。

It looks up this V table pointer。In your object and that's a pointer to a table that has all the function entry points and one of the offsets in there will be the F method and it looks that guy up you know using a fixed offset compile time offset and calls it。

Now that's great， that's the virtual dispatch we want。

 but we can't we don't in this system want to pay the price of having an extra hidden slot in every self object because self objects are only a few words at a time if we add another word it's going to pull up the memory so but back then they made the decision。

 we're not'm going to use this on objects， but we will use this on maps。

And so the virtuals only exist in the maps。Objects are all statically typed。

 and we use the tagbits to determine。What past were going to apply？

To look at the memory region of an object， and then we use an extradirect to do the dispatch for the dynamic behavior on maps。

So virtual is onlyoning maps and we go from an oop， which is one of these tagged。オ。To its map。

 and there we can invoke a virtual method。And so we can have say， a scavengnge method。

That knows about the different layouts of different kinds of objects。

 you know I showed you three layouts earlier for indexed things and slot things and bite things。

And you have three different scavnge methods that each of which knows the layout of the corresponding thing and they're virtually dispatched。

 so you don't have to do that in when you write the scavenger to build another dispatcher。

The dispatch is done by see what's possible for you。

But you have this extra pricing in that you only can do that on the maps。

 and so you can wrap this in a static method。That just calls that one。So， this trick is a。

It's took me ages to understand this the first time I saw it so I've saved you a lot of time believe me。

But when you see it， this is such a clever trick and it makes the VM code so much cleaner that it's been adopted almost everywhere since so in all。

 you' find the exact same structure。For how it does it dispatches maps so are called classes with a K in hotspot because it's a class based language。

 but you can't call them as class with a C because class with a C is a keyword in C++ and the words are not taed because it's statically typed language。

 but it still has this trick of dispatching through maps。

VA has interestingly gone a different way using visitors and templates。Rather than this。Right。

 so in order to do this trick， you have to ensure that your VM does dispatch the same way。おます。

It's going to do the C+ plus dispatch using some bits in the heap。

That it is going to assume the layout of。 So the V table pointer， this is the。Next couple slides。

Okay， so we start with an new。We want to go from the oop to the map， that's straightforward。

 that's what this code looks like。So that says， okay。

 I'm going been given a group classes Star rootot classes of Santaop。🤧So this is a method。

 which is going to give us the corresponding map pointer。

Back and so what this does is it pulls out the tank。

It looks at whether it's one of the immediate tags， int， floatloat， or malm。If it's an end。

 then it does the static cold。On this， which basically will find a point。

 this is the map of N is a VM thing， it's just built in and the VM knows exactly where that is。

So that just alias is off to a variable that points to the hint map， similarly for the float map。

The mark one says， oops， you probably shouldn't be doing this。But if it sorry， if it's not a mark。

 then some other bug， but if it's a mark， then you get the map of marks。

 which is a funny thing that's used in GC。And then for the memoir。

 you cast it to a thing called a memo。Whi is the flavor of oop that knows there is some memory at the far end it。

 So it's the variant of the tagging that has memory underlying it rather than the in the floats which don't and then you call this other static function and the way that static function works is。

It takes the tag pointer and extracts the address。Casting that to a pointer to a stroke。

It pulls out the Mac point not from thatstruct。Trussts that back。Do a memo and then retag that。Sorry。

 that retags it and that gives you the final point of back。So is this is going from。The soup。

Strippping off the tag， finding the field。And going back to the address of the corresponding map。

So you end up with a pointer， a naked pointer to them。

To the the map in the end and all of this stuff， the only test that gets left in all of this is basically the tank test and the tank extraction and all the rest is just cat。

And the compiler relied all of that stuff。It's just finessing。The time system。

So this does add an extra layer of interactiondirect at run time right because instead of looking if you were to use virtual methods in and represent objects with C plus+ objects with virtual methods。

 you would just have a look up the V if yeah， so if you put the V table in the object。

That would save you in a level of indirect， but the problem there is the V table at the end of that point is constructed by C++ at compile time。

 so how do you add self methods or methods from other some of the language into that V table？

Right you can't， so you can't use it for the language level dispatch。

 only the VM level dispatch and the price is you'll pay off for a word in every object and plus GC has to know that that thing is there and to do nothing with it because you can't move the things around that it points to you just have to skip over those words。

So all of this is to align that word， basically yes。

If you were willing to pay for the price of the virtual。The V table in every object。

 you could just write virtual on the under。Okay。So what do maps themselves look like， well。

 unsurprisingly， they also look like he objects。So they have a header and a match field。

And the map has a map map。Which is the map of all maps and in fact is the map of itself。Basically。

 it just closes off the loop。And then after that， here's where the retail table pointer lives。

In this field， so there's this interesting distinction that when you convert a mapup to a map style。

 you have to add two words of offset to get to this guy so that you can now do your virtual dispatch or the table pointer because the C++ system is going to assume that the pointer is here so there's an offset price to be paid when you do its conversion in either direction。

And after that you have the fields in your C+ so the way this is structured is there are two C++ classes。

 this guy has these two fields and then this guy adds virtuals and the V table pointer always gets added in when the class goes virtual so that's why it's。

Then after that， we have a field that says， how long the objects are that we're going to instant here from this map？

How many slots are in the object description， which is not the same as the number that are in the body right because you can have methods and you can have constant slots here there's an annotation field which contains a methodada from programming system and then there's a bunch of slot descriptionscripts these are structures these are multiword structures and the number here corresponds to the number of slots so this length is defined by this field。

So if the VW pointer is created by the C++ compiler。

 it wouldn't have a tag that the GC would understand right because when the GC would be scanning over map objects in the heap。

 youll get confused with whatever the two bits of the VW pointer would be right and how is that finished？

It's。Imiss always zero zero and it's introverted and I think that's the solution。

 but they're always word aligned and so they look like intertes。40%。

So there are all these images wve and little decisions， right there。Yes。

 this doesn't make like non assumptionss。Is highly non portable mean generally speaking。

 when you're writing a VM， you're relying on a whole bunch of undefined behaviors in C or C++ which just happened to be all implemented the same way bystander compilers about you know casting inte just pointers and addressing things that are outsides of arrays and assuming that you could start with this point or and do some arithmetic can get to some other pointer validly and all of that stuff。

At least in K and L， which I'm much more familiar with， says。

It doesn't have to work right can it can you know the behavior can be I delete all your files in your own directory it can do whatever it likes。

 but compilers tend to all have the same kind of behavior because they all more or less run on the same kind of architecture these days where back when things were different when I did my small talk the M。

The first version of that ran on a word addressed machine where bike pointers were word pointers shifted with an extra bit to distinguish the load bike。

 and so if you didn't get your casts right， you know。

I you set faulted and there was certain kinds of arithmetic you couldn't do。 But generally speaking。

 these days we're all run on by addressed machines， you know。

 and all you have to deal with is endianiness maybe and this stuff just sort of seems to work。

But I'm， I'm。When Lars comes in a few weeks to talk about VA， I think a good question would be。

 you know， was the move away from this trick to templates and visitors in VA to avoid the non-portability or was there some other reason？

Be an interesting question。是。So you're main table pointers。

 so this map just the objects that you're creating in the language， right？So yes。

 this is the metadata this is like the class for those you replic a v table point thats probably the same in a lot of places right Yeah there's most maps are going to be slot maps describing slot objects and they'll vary here。

 but they won't vary in this field Okay so then then do you have like four or five like。

Heat basically there's more I'll show you the hierarchy actually on this slide so these are the heap times so there's actually two hierarchies here。

 this is the hierarchy of oops which are the objects themselves and this is a representation hierarchy so each one of these is you know a class or you can think of it as a stroke and each is the prefixx of the guy below it So when you look at memory。

 if you see one of this one of these guys you can always do a cast somewhere up the hierarchy and just look at the prefix So each one just adds more fields that are known about by the VM。

The map hierarchy， however is a behavioral hierarchy using V tables and kind of is a description。

 so this doesn't describe a layout， but it describes a behavior so you can call a behavior in here it might be implemented in terms of the inherited behavior or it might augment in some way。

But this these are the types， there's actually more than you would think。

 but that's because there's a bunch of weird。Stuff that got added for programming language support like profile or objects and stuff like that。

 but the language objects are more or less the first。我 two分。

So you would end up with a whole bunch of V table pointers that point to one of these guys。

 actually mostly， as I said， it's going to be up。you know， almost all of them are going to be this。

 and then there's going to be a few of these others， but because in a running system。

Every map has many instances， the actual overhead of the V pointers is it's not super high。

 there's not like thousands and thousands and thousands of maps in this。It's kind of one per。

You know， language level type you know constructed if you think of a particular object construct as a type。

 there's one map per each of those so yeah we're talking about you know， sort of kilobytes。

 tens of kilobytes of wastage and those duplicated point not megabytes。Okay， so this is the。

 as I said， the structure so you see the top oop divides into the immediately tagged things SMI is small integer flow mark and me a mem is a thing with memory for no reason that I can understand there's this single subclassus that's a mem thing that's full of oops I think those could be merged。

 but I don't know why they're separate and then it divides into the different kinds of behaviors of the things that have memory。

 sort maps， they distinct from objects with slots and then the slots things divide into things that have。

You know， indexable and by indexable things， strings are special because they're needed by the VM for doing a lookup and then you have a bunch of other stuff that's in support of various other。

Some of more obscure features。And then the maps sort of look similar， there are some correspondence。

 but it's not a structural correspondence， you can usually for one of these you can usually find the corresponding guy over here。

But then not in the same entire rock。And。Yeah呀，那。Any questions on that。So。

 let's have a look at an example。Of doing allocation now in the system。

 We want to do fast bump allocation， but we want to be able to do it in our C plus。Style。

 and so the main entry point of the allocator is in this class old universe。

 which has is a single term， it's the universe， it's sort of the entire system。And say。

 you can call this。Passing in the size， which is the number of words you want to allocate and then there's some of these have these booles that basically describe fairly semantics but will ignore those from them。

This guy passes wraps the call。Onto the new generation it says， he， make me an object。

And that guy hands off to Eden as he admitted me an object。 And that guy looks internally。

Using analog ofs just local。And tries to make an object， but if that fails。

 then he calls the more general thing， which is you know， give me some more。

But the fast path thing is this code here， which as I said。

 is a bump allocateator so ups top is the field inside a space that says how far we've allocated it from the left。

We increase it， see whether it's going to bump into the bottom of the bites and if it isn't。

 we just return the new pointer otherwise we say， sorry， I can't do it and then。If we can't do it。

 then this guy will fall back to specific of case。😔。

All of these are in line C+ plus things in the class files。

 so all this code disappears and you end up basically just stuff。That increment in the test。

And all of the extra is just like they have the benefit of the。The program。In the slow path。

 if we fall through that。Okay， we don't get her。Path back then we have the slower allator which is in our space。

 it now records a care， maybe it's time to do a scavveengnge and sets a bit。

 we can't just trigger a scavvenge at arbitrary points。

Because this is a compiled system and the compiled code only registers the locations of pointers on the stack at certain places in the compiled code。

 So you can't interrupt an arbitrary PC and trigger a collection because you won't find all the pointers。

 you just don't know where they are on the stack you have to be what's called a GC safe point where there's a record of where all the pointers are。

 And so what you have to do is you have to set a bit that says I would like to garbage collect the next opportunity。

 please and there's there's a little poll behavior that says， okay， now we can garbage。

So that just registers the request for scavenging。嗯。

If we have so all the spaces in each generation are chained in a threat。

 each points to the next one in turn， so we just say if we have a next one。

 then we're going to try that。If we run out of those then we're going to start in the old generation and you notice this is the allocator in a new space in the old space that will be a some of the fallback behavior which is different from this and so this is old structured to basically try and make the fast path as minimal as possible。

And then the secondary path， know reasonable。In cost。

 but not super cheap these we're now in the room doing function calls。These are GC safe points。

So between two save points。系要 what happens。Need to create an object。And you happen to be out。

You better have some space and this is why there's a fallback into the other spaces。

You're going to look in the other places。And then youd better have some space there because otherwise you die。

And you I'll show you what the compensating mechanism for that is。きまし。Okay。

 so how do we actually do the scaavvenge when the scavenge comes。

 I'm going to all the part about doing the roots for now。

So assume we've scenged all of the roots and we're now going to go through each of the spaces。

And do the scavenging。 So the first thing we do is for each space in the old generation。

 we're going to scavenge the old to new pointers。That are there and we're going to use a card table to do that so there's this thing called scaavengnge recorded stores。

 which uses a card table you remember I talked last week about a card table is a bike vector。

Each bite summarizes some amount of the heap as to whether it may contain an old to new pointer。

 In this case， it's hardwired in that each bite summarizes 32 words of the heap。

And so when you call scaavengnge recorded to us， there's the sort of obvious loop that walks down the byer array looking for a zero。

 remember the zero is the one that indicates a marked card because it's quicker to set a zero than to set a nonze。

When it finds a zero， it applies this macro。To each word in that 32 word region in turn。

 so it's unrolled the loop explicitly to make this as fast as it possibly could be。

 so we to visit a word， we pull out the contents of the word。

 we check if it's tagged as a pointer to an object you know memory pointer if it is and it's in the pointer is pointing to new space which is simply a bound check on the address range of new space。

Then we call the scaavnge virtual。And the scavenge virtual directs through to the map。

 and the map knows the structure of the underlying object。

And then can do the the appropriate thing without that。 that does the copying and the forwarding or。

Returns the forwarding pointer it's already been copied and gives us that back。

 which we can put back into that word。And we summarize whether any of the so newbyte is a global first macro。

 newbyte is updated to see whether we've actually found something to point to new space and we have to set the card back to zero when we're done。

Because we have to maintain that。And if we go through the thing and it was a marked card。

 but there are no longer any new pointers， then we can set it to non zero。

So that we don't have to look。This macro has then applied。To every word in a car。Then this loop。

 after we've done that， we've got this loop here， which is a two part loop。

Each of these parts returns a Boolean and we're basically going to iterate。

Until either of those boooles。Sorry， we're going to iterate while either of them returns true。

So we're going to scavenge anything that we promoted into old space。

 which means going through that newly promoted region looking for pointers to new space。

If we found something， then we may have moved more stuff into the two space and so we have to continue scavenging the two spaces if we found something in there。

 we have to go back and look at。The old space again。

 you keep going around that until the pointers eventually hit the ends and there's no further progress and both of these return fall in the low ends。

If you look at the code for these。So scavvenge promotions on all space starts from a recorded point that we reached。

Last time that's just the field and the class of old space。

Object scengnge point we're just walking through memory one word at a time。

Looking to see whether we have a new pointer。If we have， we scavenge。

 we set our field in the car table accordingly。And an update at the end and then in the new space we're doing similar kind of thing we have a scavnge point that records how file we got to。

And we walk through。Applying scavengnge to every word in turn， which will do all of the following。

 et cetera， and again this is a static which wraps a virtual。Very simple。Pair of loops。Okay。

 so the only other thing now I'm want to talk about in this process is the finding the VM roots。

So every part of the VM that contains a reference to an object。

At the point at which you're on the collector， you know that reference has to be included in the GC and it has to be updated for when the object moves。

So these are variables in the VM， these are data structures in the VM that are not part of the heap all over the stacks。

 all that stuff has to be dealt with the way this system deals with the VM is that there's a macro。

callled apply to VMOops， which enumerous every single variable gives you the address of every variable in the virtual machine that can contain a loop。

And it just says， okay， give me another macro and I'll apply this macro to every location in the virtual machine。

 and then one of the macros are actually many of them， one of them is the scavenger macro。

Which just says， okay， given a pointer to a word that we know as be anop we can scavenge that thing and stick the new value back。

In its plays， and then in the scavenger code itself。

 it just applies the list macro to the scavvenge macro and get all of these scavengnge callss。

 all of the VM variables。拿才拿知道。Is there any mechanism to regist that allocated？Okay。Yes， yes。

 there is， there is another well one of these， so there's another set of calls which call scavvenge on VM data structures。

One of the VM data structures is basically a list of registered locations。

On this deck that you can wrap in a C++ class and say， okay。

 I know where I am and have to scavvenge myself and you build a link less of those。And after this。

 when it calls scavvenge on each of the data structures， that's one of the ones that gets involved。

So there's also scavengnge routines on all the ancillary data structures like the Mac table。

Has to be scaenged right because that point to the maps and the maps can move。Okay， so they。

The old space allocator keeps track of how much free space there is。

 and if you look back at the screenshot。IHere。You see in the visualization。Below， there is a。

Like a ruler。And a red line on a yellow line， so the red line always starts from the right and then turns into yellow。

And these tick marks are1 megabyte tick marks in the heap。USo you see it's， you know。

 it's the same as this except for the this this sticks out further because it has gaps between the each segment。

So asking allocation proceeds， this line will grow from the left。When it crosses the yellow line。

This system is unusual in that。别会。It will wake up a self level thread and say the yellow line is crossed。

You know and the self systemstem could set where that yellow line is willll see I crossed the yellow line you said earlier。

 do whatever you think is the appropriate thing at this point and it can choose to either call a prim safety in v GC it can allocate another segment in the heap it can do both of those。

 it can do neither of those it can delete all the files in your home direction whatever it chooses to do is it's policy it does。

 it's all selfcode and it can do anything it like and the idea is the yellow line should be set far enough back there has enough working space to be able to complete whatever it's going to do before it runs out of space。

So it tries to adapt to the default implementation， tries to adapt to changing behavior。

 so if it sees rapid growth at the line barrier of the he， it'll say， oh。

 better make the heat bigger。If it sees that it runs a GC and a lot gets given back。

 it might give some segments back to the O。If it sees that a GC takes a long time relative to the amount it' collected。

 then probably you need more heap space because you're running out and so it gives more so it tries to do it best there's an adaptive little algorithm。

That tries to do the right thing， but this is all self code。

The red line is for when that cell code hasn't done the right thing and that's the VM like Ive got a GC now because I can't guarantee that I will finish the G if I have much less than this amount of space so when the red line is crossed the next opportunity the next point the VM kicks in and just forces a GC evolve system。

How carefully they have to write the south price so that it doesn't run out of memory Wall。

T if yellow line is any reasonable amount over the red line， not all， it's easy。I mean。

 unless you're going to allocate some huge amount。Stuff in there。

 you don't really have to worry about it because things like the closures and the control structures will all be scavengged。

 you know those I'm going to make into whole space as long as you don't do something you know。

 remarkably space， hungry okay that causes those things to be tenure years， you're fine。

I never had to worry about knowing when I was join that。But okay。

 so if you happen to trigger a full garbage sh， it won't break you。No， no。

 you'll just get a long pause and the goal here is to try and optimize the space usage so that the disruptiveness on the user is minimized right you're making the best use of the resources you've got and you're not giving them long pauses in which you accomplish nothing because you didn't proclaim anything。

But， you know， if you drive it。Into extremes， you'll get extreme behavior anyway。

 it really works hard， for example， to not make a heap that's bigger than physical memory。

Because if you。If you run a garbage collector。On a heap that's bigger than physical memory， you know。

 those machine sites sort walking across the table as the desk。Fangs back and forth。

 so it tries to avoid that case， but if you really need that much memory it okay？

On your head be it and give you more memory， it won't just arbitrarily quit when there isn't space。

 it will only quit when it's really， really run out with virtual memory space。嗯。But you know。

 it might be painful before that point。The whole goal of this is really to avoid having the programmers to think about a he outlook。

 you know MX。What's the Mx value of this application？So you don't have a setback here。

It's just managed adaptly。Okay， so I was going to say I was going to speak a little bit about programming primitives。

 so the programming primitives are the things that are invoked to modify the structure and or behavior of objects。

So the idea is you're in the environment， you see stuff， you want to add new slots。

 you want to change methods， you want to join things， you want to split them apart。

 but programs when they're running，Applications when they're running aren't expected to do that these things are。

 it's okay if they have you know， like user level response times rather than like microsecond。

responsepon？The most common use of this is when the PAser is pasing source and it's constructing the corresponding objects so it says know it reads a description of a slot。

 it says， I've got this object， oh， I'm going to add a slot to。

 I'm going add another slot I'm going to add another。

So those happen in quick succession during pausing and you want to make pausing of source reasonably fast。

嗯。So the way this is done in the VM generally speaking is it adopts this functional approach whereas it always makes new copies of things。

 it doesn't mutate maps in place， it sort of copies by adding or copies by removing or copies by joining things together or whatever because it's just clean as the programs and there are a lot of tricky cases to deal with so it makes new maps on roots on the root and it makes a new object that's an instance of that map to represent the new thing。

 but then if the idea was to have some old object have some new behavior or state。

 then you can invoke this primitive defining which is used to substitute the original one with a clone of the new one and so the idea is。

Here's our original object which has an X and a Y， and the programmer has decided I don't like X and Y。

 I want P and Q now。So I'm going to give you a P and a queue and I want you to make this object look like that one。

And the way it does it is it first clones that。And the reason it clones it is because the clone by definition has no other references to it other than the reference that's held by the VM so we don't have to go off and find references when we do that so you clone that and then you make。

All the pointers point to the other guy。So that's the sort of the basis of the programming prim。

 you know， and now everything that talks to this thing talks to that thing。

 and as far as they're concerned， it's just changed。

It's shape or behavior or whatever it is the program wants to do。

There are one or two interesting tricks in the implementation of this， as I said。

 most of the implications of this are during passing where we're repeatedly are just mutating something to get to a description that's represented by the source file and so most of the things being mutated I were just created an answer in the young generation so when it comes time to search for all the pointers and update the references we can use the same remembrance set implementation to avoid scanning the wholely if the thing we're pointing to。

We're going to switch， sorry pointing from is in new space。

 then we can just invoke the same routine that scans through the card table to find all pointers to that guy and update those without having to do a scanner of the whole heap and that means that we're doing an operation that's proportional to new space plus card set size rather than proportional to heap space size which makes it a little bit faster。

So that's a。A nice trick And then I mentioned also that it's important to be able to scan the entire heap and find references to objects so if that trick fails。

 for example， we're mutating an object that's been sitting on the screen for minutes and it's now in old spaces。

We need to scan the entire heap looking for references to that thing to update them。

 so we want scan to be fast and this is where the marks come in。So it scans through the heap。

 not looking at the object structure at all， looking for the word。

The words that contain the reference that we're about to change。

And then we need to go and find the object that those are in and to do that。

 we can scan backwards to the header。So this is a fast scan and you can find the objects containing objects。

 if you like。If they need some kind of notification or whatever or you need to do stuff on the screen to update them。

 that's another way of doing it and then your final twist is the naive implementation of that would have two tests。

 you know have I found the thing I'm looking for and have I reached the end of the space and this loop is so tight withcycls that it just puts a copy of the thing you're looking for at the end of the space has a sententinel beyond the end of the heap so that you don't have to do two tests。

 you don't have one in a loop and so on the machines that this was built on it it could basically consume the memory bandwidth while was the scan。

Okay， so I'm not sure we'll be doing this or exactly what this will look like。

 but it' be interesting to add cloning。And maps， Stehanni and Patrick and I are discussing what that might look like as an exercise or a twist。

 but that's not formally assigned yet。Quion about the period like， yes。

 So the reason the scan is to be of bad。Looking for corners to the young generation。

 but most of them are not going to be Well it might not yeah。

 so the object that you're mutating might be an old object and so it might not be in the young generation it could be anywhere in the heap and you have to find all the references to it and update them。

And so you want a fast scan through that can update the points。

There are also scanning things that are used in the programming environment。

 so for example you can say please give me all of the references in the heap to this object I would like to see where it's used and the same scanned thing is used to aggregate all of those things and give you a vector back。

嗯。Okay， so I think we should take a break。Don。And for。Great， okay， not so much to talk about today。

Because。Sorry， my。是这。嗯，好。然 of the。The general。Yeah。Right。

 so todays how we talked about the bycode interpreter and filer system。呃。As far as the code goes。

There's not too much I want to say， I think I personally made a mistake designed the assignment when I gave you the instructions for the bikecon interpretpreer。

The semantics were defined way too abstractly。So I got a bunch of working implementations that all do the correct thing。

 but they're all implemented quite differently from each other。But for the garbage collector。

 I gave you some specific layout I wanted you to use。

 so if you follow that I think you'll be okay for the rest the course。Okay。

 so going over to law answer questions。This question is about verification。

 if we want to write a verifier four hour bycode interpretpy or。

 what are the sort of things we want to look out for？So。There's broken the category。

 there's a general category just relating to， is the bycode well formed？

And there's also sort some little things you can check。

Whenever I say this must be referred to a string constant in a constant pool。

 is it actually a string constant？嗯。Does your entry functions have proper number argument。

 namely zero？诶。When you refer to local， is it within the number of locals that you told to function？

You refer to labels outside of the local function， so there's just a big list that you can list。

And then， there's。Some additional things that simply enforce speedies。

Pie says functions can only return a single value， even though the BCO interpreter is free to do whatever。

 which is， so if you place these additional checks，对啊。And unfortunately， you can only run female it。

Sometimes that's desirable。 Sometimes that's not。The most important one that I really want everyone everyone to get is this top one。

So。Basically， at the end of the day， if we want to write a fastcon compiler。

 we want to get a static data flow graph。that's only possible if we have this property。

The stock layout out。On the entry for every basic block。Is the same。

So it means you can't do stuff like you declare an if statement and on one branch of the statement。

 you push two raeys to the sack and then the other branch you push one valley to the sack。

If you do stuff like that。It's very hard to reconstruct this data data flow。

So that is the biggest thing you want to verify for optimization。

One thing to point out is that some people。Got the phasing a little bit confused。

 they said you can do type checking and the implementation already does type checking because you know if it's the wrong type。

 you just fail。So it's important to note div verification happens before you actually run the program。

And because spin is dynamically typed。You cannot in general， look at a variable and know that。

Only integers will be stored on。That's a very difficult analysis。It's impossible。阵容。

So the best you can possibly do if you want to do something like this is sort of a best guess。

And that's generally。Not a great idea to put into the semantics of your wireifier。

 because it means that。As your guesses get more and more sophisticated。

 there will be programs that run our some systems that don't run another。

So that's generally what I do。Okay， so that's what I want to say onification。The next question was。

There's a lot of less time spent on environment looking at now， why is that？

So the biggest reasons is just。In our naive AST interpreter。

 we use this environment object to look up everything。Right， you looked at。Slots。

 we looked at methods， but we also looked at local variables in local variables。🤧。

With a very simple analysis， you can determine。Am I loading logo variable 17？我嗰嗰边好。7。

And this is like a very big。2呃。Any compiler， really just replacing names with Up。

So the only parts left where we actually do need to do is look up by any。

There's like the slot and cost slot。Here I have a little blurb that says。

This ability to look up by name gives you some power， gives you some。

Expressive power for the language， right， so it's useful to have this。If， for example。

 our language had the ability to。You can calculate some string。

And then look up the variable by that string， right。

 so like dynamically calculate the name of the variable to look up。Then you would not be able to。By。

Do this analysis。More statically， you assign each local an index。So。

 I have this little blur that says， you want to give the user useful expressive power？

If you give them too much of expensiveifier， then。You kind of design yourself。

So I don't know what I might say about that because I think self is viewing on well it sort of really pushes the envelope。

 but they step back from the brink of doing things which got very， very expensive。

 there was sort of no known efficient implementation。Like adding in fields too so。

That's regularly done and encouraged by the language is expressed efficiently。

T anything that could be expressing。6。Can you look up slot names in， can you compute them？人 sir。嗯。

There is a primitive that takes。诶。A name is。A variable about expression and does the look up。

 but there's no assumption that that would be。You can do that look。It isn't going to be。

What comes in time。Fast。It's used by the programming environment。Soing for things maybe。

But even you would be strongly discouraged from doing that in an application。So。

Pearl is one of the language I have in mind allow you to calculate the name the variable to look at。

So。AndI think the catch parse pel。pers humans can't persevere。😊，Okay， so that's that's the main。

The next question was， I asked you。A bunch of additional control operators great continue return。

How easy is it to implement using the bikecode interpreter？And everyone has served it very easy。

The BM itself doesn't need to change， really the only thing that changes。And this is great。Okay， so。

ASD interpreters are particularly easy to write。If your host language matches your target language more or less。

And if they don't， if you wanted to write a prolo ASD interpreter， it would be very difficult。

 in fact probably much more difficult than designing a bikecode machine。

So I would say a Ico machine is like a general technique that you should know。

And they is the interpreters you should make them convenient。で。

So some of you may be taking the programming languageage prelen。嗯。

This inherent difficulty between expressing control phone an ASD interpreter and a bicon interpreter。

Is related to something called big stepsmatics and small steps。So。

Those of you taking free might one to read up。O， this was a fun question。 I asked you。

If you want to reverse engineer if you need BIO program， how much information can you get out of it？

And the surprising thing is that it can get a lot out of it。So slot names， method names。

 global variable names， they are all preserved。呃。No in learningning happens。

 so the encapsulation is all preserved。So what is lost？Local variable names I lost have one。

And the high level control flow constructs are sort of lost。They replace them labels and go tos。

Same with any constant scoping。So。But if you always go back from how little the control。

 So we can always go back from labels and go tos and interpret walk w。

If know if you know the exact implementation of the compiler and it uses the reversal algorithm well。

 you can always generate some exactly except they kind of made an exponential disclosure what if they want to get so you can make it very hard to get。

And then the scoping is， you know， when you write your program。

 you can declare your variable eye in like the cost if state。

But the compiler lists all that up to the function level。

 so you kind of have to recate where you think the programmer。Deine this variable。Good。

And this isn't just a hypothetical question if you run any of the myriad of Java people。

I have a question about that just that one because initial values。すごい。The first assignment。嗯。

That's true， except that the compiler shares the same slot。So that makes a bit here。Right。

 so if you run a job with decocompr， what you'll often see is you see a bunch of local variables with garbage names declared at the front of the function。

Followed by a bunch of not very aiomatic look at controls instructors。

That results from the Dikafa Tris best。To infer the control of electron structuress from these labels and gos。

And you don't necessarily lose kinds of scoping becauselafini。The first time it has to be said， yeah。

 that's but but the compiler often shares slots for variables right。

 you end up with the same name oftentimes and same right， so these if you called it level three。

 that's a slot three， then you end up loop level three when there。

But they may be declared in different scopes in the source。right， no， that's certainly possible。

So basically you do your best， this is the information that's lost that you can put in a lot of work。

But everything else is kept。So the programs are actually surprisingly readable even after。Rebu。Okay。

 this was a trickier question than I thought it would be。

 The question is the is T interpreter semantics that are just slightly different from the bi interpret semantics。

So here's an example。What is this program supposed to do， this is a complete program。

So if you running your AST interpreter， well， it sees a function。And going see is print Hello Road。

 so print Hello Road。Then I finish it。So the program prints hello world。

If you running in a micro compiler。Well， it would say， all right， let's compile this function。

It has two variables named I that is obviously wrong， It doesn't satisfy semans。

 so it won't even pass them five。So if you and your friend are running different media implementations。

 someone sends you a bunch of code。one of them will run and print hell world。

 and the other one might not even。嗰得发。Here's another example， what does this program do， you call F。

怎样一个发展。So according to the AST interpreter。When you call F looks up a global variable called F and there's no global variable called F。

 so you quit with。That has not been defined。But if you run in the micro compile there。If you notice。

 all the global functions has been pulled out and then your entry function just calls up。

 so this runs perfectly fine the bico compiler。So these are other differences。

So I don't want to sound like a conmudgen， and this seems like nitpicking。

But this is actually what causes real affordability issues in fact。And as a language designer。

 you try your best to cover all these current cases， but it's often not trivial。

So Matthew flat is that。Sing guy。 he made this comment。放出来我操作。

Just coveringing how intrinsically difficult， covering all these。呃。If you know。

Any program that runs on the Bcode interpreter will also run on the AST interpreter。跟到别的问题。

So this suggests that。Probably if you wanted to define an airtight spec。Language。

 you should think of it from the point of view。Have welcome either， whether they're interested。

对个他们就说那个人。Scratch up，s wrong。But actually you can detect that duringpoli time this hour。Yeah， okay。

 so not trivial not trivial right。Okay。Daphine bycode IR for that particular assignment。

I gave you the source text， you compiled it， then you ran it。

So the user doesn't have to be aware that there's a Bcode interpreter at all。

But if you wanted to expose this to the user， if you wanted to distribute programs in by code form。

And here are some other the things you have to。Bye。For example。

 how do you actually store this bycode on disk， how do you load it。

 so you just have to define a file form method。That's pretty trivial。

 the only minor things are you do have to be aware of Indianness。So that's why when you read it。

The Java spec， they were very careful about the fine and the endinginess of everything。

And then also because now they're given this arbitrary piece of binary。From your users， now。

 I actually do have to。Verify it because you can no longer assume it come from this compiler that you wrote yourself。

So now you actually have to。Be very， very careful about writing this spec so verify。Okay。

 and then last little question was if Fi bycode IR。

 the control flow operators are specified using labels。Go to with names the labels。

This is on contrast to Java， which gives you an integer offset and this integer offset will jump to you somewhere in the Bcode stream。

 and they interpret the Bcode stream from there。So what are the advantages of his event？Well。

This is the extra stage in the Java Bco Hifier， right。

 am I jumping into the middle of a Bcode street？I jumping into the middle of a bike of instruction。

So。Because he used labels。You are syntactically。It's syntactically not possible。

So now that's something you don't have to check for。So， that's very。

It also makes the compiler easier to rent。So basically， most compilers that I know of。

Always have this password where they have labeled internally。

And then there's a separate path to convert these labels into substance。So that save you that。啊。

When you do your Jit， you'll see that these offsets are fairly nameless anyway because the offsets change when you change representation。

Okay， so the takeaway is that。You have your disk format for your IR。

And then you have whatever format you like when you're interpreting it。

And these don't have to have anything to do with these。诶。

So the semantics of the bycode is arefal to how the bicode is surround on disk。

Don't make life hard for yourself by prioritizing the this format over your semantics。そスマします。啊，没。

So I said synactically。It's just impossible to jump to the middle of my if you use labels。

So this is just my personal event， I think if you can do it syntactically。

 you should try and do it syn。So the Holy grail of languages is something where。

Any intachably credit program。It's both correct。Andです。We haven't gone there yet。

And your bottle left to have the empty set。s not consider the。Well， that' sounds useful， though。

 is it。Well， they're all useful and they're find useful in the Amac South book。そな。

's a Uni program that's zero by long， right， I think。It's mostly copyright notes。🤧Oh。你しもけ了。

vol of the zero binary units。More than。你条だけ。Okay， so that's all I want to say。

 So who have started their garbage collector。O。Wow，s actually like who doesn' a running R sold me。

Okay， and you guys have all done the stress test。Wow， okay， that's very。嗯。Okay。

 so basically from this point forward。Whenever you see a segmentation fault。

 you will just quiver in fear that it might be a gu。You never have finished a garbage explain。

This is the。The motivation the first。Of some tips。没有没。Okay。Okay。

 so getting to the point where you can run your garbage collector for the first time。Is easy。

Having it run the second time？あですか。The problem is。If you have a subtle bug in your collector。

After it's run， it's going to make your eat bad in some way that's not easy to discover and in fact。

 the chances are the only thing that will uncover the badness is the second time it runs and it gets sent down a blind alley by something that was there in the first time so this is horrible because by the time you get there right so much has happened。

You know you've got no real sense of what the state was at the end of the first GC and so how do you deal with this this is really an important thing to try and get a handle on。

There's no great solutions， but I'll give you the best I know so far。

So the trick is you just have to do a bunch of extra work as you go along。

 you're going to do this eventually to debug this collector。

 so you might as well just put the effort in up front。What you want to do is write。

For every structure， particularly the heat in the garbage collector。

 but for any other structure that might contain references。An invariant checker。

That checks the sanity of the entire heap in every single detail， every bit， every by， every word。

 everything。And so for example， you want to check that all references in the heap point to the stars of a valid object。

You know that's nontrivial because you have to know where the objects begin to check that right this is why having all of this redundancy in the where the thing is laid out and the structures is important because it gives you a way of checking and cross checking that things are correct so you want to be able to know that every new tool space pointer has a corresponding entry in the robot set and this list is long。

If you think about all of the things that are expected of a correct heap。This is a longer list。

 but what you want to do is codify all this stuff up。

In a bunch of functions or a top level function that captures all of the invariance and provides some way of calling that thing so for example in these are all called verify functions if you look through the source codes you'll find in every class。

There's at least one and sometimes many verify functions and they're all tied together in a hierarchy so that at the top level I can say verify and it will check the code cache and the heap and the remembermbr set and the structure of the stack and everything it takes a long time to do that because it's like a full G is worse than。

A full G， but at the end of it， if it says everything's good， then chances are。

 everything really is good right unless you're making mistakes at the level of you know the answer should have been two and instead you returned three。

嗯。You know， then then this is going to find problems in particular。

What you want to do is make this stuff invocable。Before and ever。

 after every major state change relative to the verifier， so if you have a verifier for the heEap。

 invoking before you do a GC and invoking after you do the GC， if it falls over before you do the G。

 the GC isn't going to make it better。It's only going to get worse So the thing is then you have to back up and find out where did the badness come Was it there the previous GC and you end up doing kind of this binary chop on the world you know you run a program it crashes or it's dead All right so let's run a verify before the last GC before the crash assuming it's all deterministic and replayable or just turn it on for every GC and watch it go and see if at some point it it goes bad。

 whether it dies between GCs or during the GC and similarly for all the other structures you want to be able to turn this on on and off and so command line flags as where of turning things off a configuration file that turns things on and off have it invocable from Fie there's an idea where all the self phones can be invoked from selflevel。

You knowAll of these options are good options。Also， you know， sometimes you want to be able to。

 you know， in the middle of your debugger just say， oh I'm in the middle of the debugger， you know。

 let's just verify that things are okay， but obviously when you do that you have to think about whether the invariant really just hold right if you're in the middle of a GC。

 you probably can't call a GC you know the heat verifier because you probably you know in the middle of some weird state only gets picked up at the end of the GC。

So this is a useful thing to do the one thing I followed up to bottom on the slide is have some way of invoking them that turns them on a lot。

 so if you look in like the hotspot code， there are flags that say scavveengnge a lot and GC a lot and you know various things like that and they force certain operations to happen on a regular basis so for example。

 if you want to really test your GC GC have every single opportunity。If there is a bug in it。

 it will go bad real quick， you won't have to wait for a lot of code to run。It will go off very。

 very quickly。So you can force things that are you know nominally identical kind of operations to just happen a lot and see whether you can force an error because if you can force an error。

 the sooner you can get to the point where the errorero stay happens。

 the easier it is to do both if you don't have to run for five minutes and then figure out what's going on。

 if you can run for a second and figure out what's going on， life is。这样。

That's the first bit of advice。 And actually that's the end of today's。Wcairs。

 so we go a bit early today and you can all go off and them。Do people like us。对。

And next week we'll start looking at compilition I'll send out the reading。

It's probably going to be the polylymorphic inline cache paper。

 which will be something useful to stop it。
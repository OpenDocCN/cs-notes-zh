# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p36 CMU 15-213⧸513 final review： I⧸O, Processes.zh_en -BV17jcReyETC_p36-

So processes in IO。

![](img/ef0d2049bfa99a96bdad97ec26ca657b_1.png)

Yeah， so a typical IO question usually you'll have like。

 hey we're giving you this text file has some text， we're going to open a bunch of files descriptors。

 going to read and print and then dope sometimes and you know for a process and then do and things like that so main idea what you want to know for these kinds of questions is。

😊，How does weed offset？And then how does do 2 work so one the thing that's confusing for me is like the order of arguments so you might want to remember that have it on your cheat sheet or whatever。

 so which way does it go？And then how does the file offset work when you do things？Right。

 so for this question， right， we have food。t tax that just has all the alphabet from a to Z。

And then you're opening three files descriptors to the same file。And you read。

 so first you read from FD1。And put it into character C size of C which is going to be just one byte right。

 characters are one byte， so what if we were to print C， what would be the value？Yes， a。All right。

 okay， so what about if I read from FD2 now？Does the value change does what do I get and see？Still a。

 right， because I'm reading from a different file group。So now we dip to F2 and F3。

And I try to read from F3， what's C going to read？Yeah。

 so your file offset goes after still exists after you do， right and then。

So the last thing should be F2， actually on the slides， I'll change that later。

 but let's pretend it was read F2。That would still read what？Yeah， so there we go。Read offset， you。

 incremented by the number of vites you read， and then do to any read or write you do。

 your file offset still changes。All right， so now comes a slightly tricky part when you fork right so I did all of this stuff and this is the code from before in italics and now you decide I'm going to fork a process。

😊，And then do a bunch of reads in there and then read in the parent afterwards too。

So like things you want to watch for is like how file descriptors are shared within processes。

 so like if the parent opens， is it still open in the child， if the child opens。

 is it still open in the parent， things like that？And then if you dope in the child versus the parent。

 how does that changed anything， how are your file offsets cheered right so that's most of what IO and processes questions to be will test so for example。

 this time I did put in statements，For。This program。What would be the output？So first of all。

 is there one single output that's going to be there？see one shake， two shakes， okay？Yeah。

 so I'm forking right so remember with processes， they can be interleaved however they want unless I have some kind of a reing condition so unless I wait they can be all over the place right？

So let's pretend okay let's do the easy case first and let's pretend that the parent is the only process that does it first right so I'm the parent I'm going to skip over the child part and then exactly perform these two reads。

 so what is this line'm going to print？If I'm just doing the parent。A little bit louder。So。He right。

 I read from F2 and I read a C。And then I'm reading again from FD2， so what am I going to？Friend。D。

 okay， and then what if I read from F1？Okay， cool， so to the parent and now I'm going to do the child。

So we said that FD1 over here is going to print us a B。

What happens when I do this read inside of the child？What would I print？I'm hearing1 C， I think。

People agree， someone disagree？Okay。What do you think it should print？B， okay， why do you think B？

It被か。When你说。It does make a copy。But the file offsets still increment。

So the file offset is still shared between the parent process and the child process。

So it's still going to print C in this case because we increased our offset in this week。

Does everyone get that？Okay， so yeah， within processes。

 your file offsetce is still going to increment。So yeah， okay， I print C here。

And then I decide in the child that I'm going to do。And I'm going to do F2 to be F1。

So what is FD3 going to print？So there are like two dupes you need to consider in this case， right。

 once in the parent I've already duped F3 to the F2。And now in the child。

 I decide FD2 is also going to be due。So what is F3 going to print？对。So。

It's going to you think it's going to print E？Why is that Because I think when F2 changes。

 F2 will stay when you the？Object or remember， right？So FD2 previously was like its own thing， right？

FD3 was pointing to F2。Now I pointed FD2 to point to F1。So what is FD3 eventually pointing to？

So like so you can think of like a chain here right， so FD3 pointed to F2。And F2 points to F1。

So technically， FDs3 now points to F1。Is that confusing do you kind of see that right like it's you can like when you when you when you do these kinds of problems。

 what helps is like just write down F1， F2， F3， and then half the whole sequence that they might be pointing to in the file offset and then just like whenever you see a Duke call replace the entire thing。

With。With the FD。I don't think have to change the price speed。

Because it just changes the entry in the table right， but it just changes which one is。

Becauseuse we don't actually point each other point about yeah。And two them was to one。

 but then three still points to。To what to have pointed exactly。

Right because it's like they're not actually point at each other， right they're pointing at。TheYeah。

 so， so if。So if three pointed to the object that two was pointing to。

 and now two points to a different object， three still points out what two。Yeah， yeah， sorry， okay。

 bye back， by， bye by， yeah， bye back。😊，So three is still pointing to what two was pointing at before。

 sorry， I would change the slides， but yes， that's a good catch。Okay。

 that was not the point of this question， though。Regardless of what it seems like。😊，Okay。

 so three is still pointing to what two used to point to and two we established printed。

D says it's going to print E， yeah okay。But afterwards， when I'm done with this part。

 I still have to execute this， and so what's this going to print？Now。有点皮子。Yeah。

 so after so in the parent， right， we had FD2 print D。

And so when we go in the child and we change FD2 to point to FD1。

It doesn't change what FD3 points to because FD3 still points to the instance of the previous FD2。

Is that kind of clear now， okay， yeah， so F3 in this case would still print what FD2 previously had。

And that would be E because we had D over here。Okay， so now we come out of this and we print。

Itま good。We prayed this part。So。If we printed， so remember we duped here。

 so now FD2 is going to point to whatever FD1 was printing。

And that was going to print whatever is after this call。So that's going to be。

I lost the alphabet but you can write this down and then I think it prints F in this case yeah。表不。个。

你个嗯哼啊。来分析那个龙鸟的三小帝王的。ざ。Yes and over here also， right？So if we executed the parent first。

So this is the output when the parent was done first。Yeah。

 this is only the case when the parent is happening first。Yeah。这第嗯。

Both processes share the same open file table， is that correct？So when the child process is created。

 it creates its own copy of the parent's file table。

So any changes that the child makes in terms of like duping or opening or closing doesn't impact the parent。

 but if the parent made any changes prior to forking the child。

 those would be reflected in the child。Chil or whatever changes like the file position so like it continues to read Yeah。

 so so remember that they're pointing to the same file object， right？So。

 so any changes that you make in the parent from reading is going to increment your file offset。

 right？And so the child is still going to see the updated offset。

So it has its own copy in that it's pointing to so you can think of it like the pointers the pointers are copied。

But it's still reading from the same place。So the file table is then tabled by the。Yeah。

 so it's creating a copy of the file table that's yeah， that's handled by the kernel。

 but it's still reading from the same file if the child makes a change。

 will the parents see the change？Yes， so it's it's updating the same file right so any changes made by any process is going to be the same for all the other processes what you mean is that the file is the same but the child needs a copy of like the pointers to Yeah so like the file object is the same。

 but the challenge has a different pointer to it。Yeah。

 so does that mean like the file offset is stored within the file itself without the file？

So it stored within the file object and the file object has a pointer to the file itself under this now you can have more than one file object for a file。

 which makes it even more confusing。One file object is created every time you open。

And then if you create more pointers like more references to that file object。

 they still all manipulate that one object， if you call another open call。

 then it creates another object object。And so yeah。

 you can open the same file more than once basically， but they will have different offsets。

So if I called do two in the child， will that that be parent as well？

Because whatever you do in the child in terms of duping， opening or closing。

 it's just the pointer to the file object right so the child has its own pointer to this so okay so when we do let's go back right when I do open F1 open F2 and open F3 I'm creating three different objects called F1 F2 F3 right and when I fork。

So in my main process FD1 points to this FD1 object right。

 when I go into the child after forking then the child has another pointer to FD1。So。

If I move around the child's pointer from F1 to F2 or whatever other thing。

 or if I close that pointer， it's only affecting the child's pointer， right。

 my parent is still pointing to the same thing。So it doesn't actually do anything with the parent。

 but because you're modifying the same file， the file offsets are going to be modified。

Other questions？So it all open on a file。Let's say before that。

 that files office was like the second。By or whatever， if we called open on that file again。

 would that new open file scriptor be reset back to cross zero or would it have to？

So like you mean over here， if I had a read in between F1 and F2。

 would that change the offset for F2， no， it wouldn't。Because you're creating a fresh object， right。

 every time you create a fresh object， you start with a zero lesson。嗯。Other questions， yeah。So。

 you said。Thank。Depends on what you say by things， right？For if I'm reading the file offset。

 if I change it in the child it's going to change in the parent， but if I do any open calls。

 close calls， or Duke calls， because those are related to what's pointing to what the changes in the child will not be reflected in the parent。

And vice versa and yeah and vice versa So essentially comes down to are you manipulating the pointer or what the pointer is pointing to let's take a real world example let's say both Stephen and I are pointing to this chair。

If Steven changes the chair that he's pointing to。That doesn't really affect me right I'm still pointing to this chair。

 but now let's say Steven's pointing to that chair and then Stan goes and assist in that chair and I tell him to send that chair。

 Steven sees that update right And so now it's the same for both of us。It affects both of those。

Just by me changing around my pointer， nothing hurts Steven or changed what Steven sees。

So you're saying like working doesn't create like a new diser table or like new object。

 it just like just points another thing。Yes， it just has another pointer pointing to the same object。

😡，It's not going to create a copy of the object itself。Only open can create a new object， that's。

 I think the main takeaway here。Okay， so。Now we're actually going to put a weight cage here。And so。

Once we put that weight PID，Here's about the。So the other case is when the child executes first。Yeah。

 what have been instructions for the child of parent over？In terms。Yeah。

 so that's another possibility right yeah， I didn't list out all of them。

 but like because we don't have this weight PID， it can happen literally in any order。

Can print like one here and then go to the parent imprint and then vice versa。

So that's on the exam we usually don't leave this open ended and say， okay。

 list all the output we say we give you a specific output and ask you is this possible yes or no it just makes it easier for us to regrade or But like for each whenever you have like the question whether this is possible or not the way you want to go about it is like go through and see is this where is this going be printed and then what can I do next So create the graph and then see like where can you go next。

Yeah。You are not。But like reading and writing。Yes， because open close and Duke2 are manipulating the pointers and reading and writing manipulates the file。

Yeah， well， also like if the parent is accessing file descriptors versus like the parent and the child take turns to accessing the same file descriptors。

Does that have different behavior like if the parent and the child are like two separate processes are trying to access the same file descriptor I feel like I remember or something that。

So if so if so that's kind of the same， excuse me， the point is。If the child or parent。

 any of them read or write to the file， the other process is going to see the change。😡。

If they open or close a file or if the child opens a file。

 then the parent process is not going to see any change because the child is manipulating its own pointer。

😡，Not doing anything with the parents' point it's important to note that the contents will still be visible but things like the opposite which are specific to that file object that we keep talking about like that comes back and that gets created everything you open it that's like something that's within that object right so you create a new instance of that object then the opposite not sure the contents live all the way on disk and that's like something that you can have like the object is the chair that stand with sitting in so that that like it。

Yeah， we got考 here我。Sameme so right same？是做一个。Do we？

So like copyright is generally reserved for like things related to actual memory。

 if you map the file into memory， which is something we don't really talk about in the course。

 so you don't really worry about it。Or also the table itself。

 so let's say Stephen and I were all point reporting point to that chair at the same time。

 the moment he changes that point or something else， he gets his own comment。Yeah。人間スプなですたが。あ。デスかす。

So clear I think I want this to go on the record so I'll stand here and say it so there is a table for every single process the table contains pointers in it。

 the pointers are pointing to file objects all right。😊。

The file objects themselves contain a reference to the file， which lives actually on disk。

Two levels here， right， there's actually one more level， which is the file descriptor。

 which is an index into that table。All right， so the table is like an array right。

 and it has indices。 So file descriptor one is the first。

 I guess you know the entry number one inside that table。So when you read from file descriptor one。

 like number one， it looks at the first thing in the table， sees what it's pointing at。

 looks at that file object， sees the offset that it has right there， looks inside the file itself。

 sees what's actually in the file at that offset， then it comes all the way back to the character that you just read。

Lots of indirect here right draw a diagram if you want to convince yourself of this and try and convince yourself what each of these operations do at various points inside that diagram。

 I think that's the best way to get an understanding of what IO is really doing because without this diagram in place it's really easy to confuse like file descriptor with the file object with the file itself so。



![](img/ef0d2049bfa99a96bdad97ec26ca657b_3.png)

I think we're going to move on because we want to leave。


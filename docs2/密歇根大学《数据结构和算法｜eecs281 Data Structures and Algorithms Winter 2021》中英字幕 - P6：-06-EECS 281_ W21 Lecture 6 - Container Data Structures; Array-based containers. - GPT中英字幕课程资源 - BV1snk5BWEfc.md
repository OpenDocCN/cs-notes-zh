# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P6：-06-EECS 281_ W21 Lecture 6 - Container Data Structures; Array-based containers. - GPT中英字幕课程资源 - BV1snk5BWEfc

Okay， hi everyone， I'm having some trouble here， at least it looks terrible on my end。

So what I'm seeing is that in my preview window， all I can see is like Es 281。

 the half of the top of the word lecture6， and then arrays。

 and I can't see the whole slide at least in my preview。So can anyone tell me in the chat window。

 does it look okay to you or are you only seeing like the upper left corner？Okay。

 so everything looks normal to you， okay， I'm sorry for the huge delay， it looks terrible to me。Okay。

 so sorry for the huge delay， I don't know why my preview looks terrible。

 but if it looks good to you， then we can make some progress today。Okay。

 I've been panicking like for 15 minutes。 Okay， let's see what we can get through today。

 We'll try not to go too far over if you have to leave to go to another class and we're not done。

I'm sorry， but， you know， I'll try to get this done。

 So we're going to be talking about array today and the underlying data structures and things that are relevant with this are。

When we're working with a program， we do need to understand how arrays work。

 both built in arrays and dynamic arrays， because we need to know dynamic arrays and how pointers work。

And we need to know how strings work， C strings and string objects now。

Part of the reason for doing these。Data structures like arrays and dynamic arrays when we have things like vectors is one that there is a lot of legacy code out there。

Now granted， they make good code examples， they make good questions for homework and lab and stuff like that。

 but legacy code， what that means is，It's very rare that you go to work for a company and they hire you and they say。

 oh good now that we hired a programmer， we can get started and do some coding Usually you get there and there's like half a million lines of code already and if it's been there a while。

 maybe it was originally written using arrays and Cstrs and didn't use vectors and string objects and stuff like that。

So when we're working on projects， we want to stick to， we want to avoid things like seat rays。

 we want to stick to things like vector。There's also a thing called array that's a template in C+ plus。

 but it's not as useful as a vector because it can't grow。

 you must declare an array object with the size up front and you must pass it with the size known to a function and so I've found array objects aren't as useful as a vector。

 I'd rather just use a built-in array or use a vector。We want to avoid pointers whenever possible。

 Hopefully， you listen to the Project 1 tutorial video， and you're not using pointers in Project 1。

 But I've seen so many people that have watched the video。

 or at least they've claim to have watched the video。

 And I see they've got a structure that has a character， a bo， a character， an int。

 an int an int and another character， which I don't even know what that's for。

 And they put that huge structure in the 3D vector and the deck。 Remember。

 two different data structures。 What goes in the 3D vector is different from what goes in the deck。

 The deck needs the three integers or unsigned integers， Room row column。 but what goes in the。

3D vector needs to be smaller than that。Char and a char is sufficient char bo char is still fine。

 but anything beyond two chas and a bo is going to be too much。

So that's my minor rant for today so make sure that you're doing your data structures properly for Project1 So what we'd like to do if we're avoiding pointers we want to use STL containers like vector and deck and string and use things like integer indices so when I put in the deck when I put a room row column those are indices into the 3D vector when I've got a location like room1 row 2 column 3 I don't need the character in the deck I can look in the 3D vector at room1 row2 column 3 and there's the character there's whether it's been discovered or not so I want to avoid duplicating information if I've got an index I can go look in the 3D vector find everything else I need。

Use the string object。So for things like my output mode。

I could have a string object for that I can when I've got a comment， I can see and ignore or getline。

Like I said， don't use pointers on Project one when you get to project two， part B， pairing heap。

Pointers are going to be unavoidable and you're going to get more pointers than you ever wanted in that one piece of project too。

So there's a little sample of code here asks what it does。

I've got an array of doubles with three double values。 I've got an integer I。

 and I use I as an index， So I say a at index I。I also tried I at index A， and I'll grant you。

 there is another slide that has the answer on it。 But if you didn't do what we said and didn't read the slides first。

 or hopefully if you read it， when you did read it the first time， what did you think of this。

 Did you think， oh， wait， there's no way that's going to even compile。 or did you think， oh。

 sure it's going to compile， but it's going to sag fault at runtime or is it going to be legal。

 legal， meaning， like if you ran it through valgrind。

 it wouldn't say you've accessed a bad area of memory。So it turns out in this。

Those two lines give the same output。And the reason is that。

A square brackets I and I square brackets A， the compiler converts it to pointer notation。

So that's when we say that arrays are pointers and pointers are arrays， that's almost true。

 there's a minor case where there's one thing you can do with one that you can't do with the other。

 but for the most part arrays or pointers， pointers are arrays。

So i suba converts to D reference i plus a， an integer plus a pointer is the same as a pointer plus an integer plus is commutative。

 even when you're adding pointers and integers。Okay， did I expect you to know that， no。

 did I expect you to know that for the exam no， but it's just a point at how how things work is things that look like arrays are really treated like pointers。

Here I've got an array。 I put AECS in it， and you can see the the change in here。 so like I。AECS。

 and then out in line two， I change the A in here to an E。So we've got EECS and the。呃。

Characters I can assign， I can look at something in a character array and pull out the character。

 I can take a pointer to point to the same place that a does。

And I can move that point or I can say P points to something else。

And that line 10 is demonstrating the one way that pointers are different from a array。

 When I've got P and P points to the same place that A does， I'm allowed to move P to to say， hey。

 you point somewhere else。But I'm not allowed to move A。A， I sort of drew it here next to the array。

 but really， a is a pointer。To the first letter of that array， and I'm not allowed to move a。

That's the big difference between arrays and pointers is that pointers can move to point to something else。

 arrays cannot not， they must stay pointing where they were。

And there's the nice things about square brackets here is we can get to index I in0 of one time。

 we have to remember indexing starts at zero， and if we wanted to remember that there were four elements in here。

 we would have to have like maybe another variable to remember how many things are in ourRA because。

Arays don't have any bound check。 If you go off the end， it lets you。And maybe at runtime。

 bad things happen， maybe at runtime， random things happen。Now I've got here an array。

 so on the left is a1 D。 on the right is A2 D。 So A1 D is declared to be an array of size 9。

 A2 D is declared to be an array of size 3 rows， three columnves。 So this is the number of rows。

And this is the number of columns。And square was what fit on here。 I couldn't fit 12。

 I suppose I could do three by two and do a six。 but anyway， so we've got a three by three。

The interesting thing is。In memory。They both look like that one。

Because memory chips aren't two dimensional， I mean， in the physical world。

 they're three dimensional， but logically inside， they are one dimensional。

 you have a memory address。 you look in that memory address。

 And so since the memory chip is addressed linearly。

 the two dimensional array gets laid out linearly in memory。And。This is why。

Localality of reference makes an important what order you do you're looping in。

 See if I loop over the columns and then I loop over the rows。 I would say， hey。

 let's go change this one and then that one and then。This one。And if I change them in that order。

 then I'm not necessarily taking good advantage of locality of reference with a size of nine。

 it may not matter。But with a， with a bigger one， if it was like 1 thousand00 by1 thousand0。

 it would really matter which。Index， you loop to the fastest and the slowest in this one。

 If I was looping through this， you'll see on the next slide。

 I want to go through rows as the outer loop columns as the inner loop， I want。

The column to change quickly， so I stay within that locality of reference if you don't know what that is。

 look previous video near the end， it's not going to be on the exam， but it's good to know。

So I've got this array laid out and you can。Choose to make a one dimensional array and treat it as if it's two dimensional。

 you can do these formulas yourself to change back and forth from a row column into a single dimensional index and vice versa using division and。

Remainder upon division， we can turn a single index into a row and column number and with multiplication and addition。

 we can turn a row column number into a 1D index。Now， could you do this on Project one？Sure。

 you could extend this up to three dimensions and say， hey I don't want a 3D vector。

 I want a 1D vector that's rooms time size time size and one dimensional and then I'm going to do all the translation from room row column to a single index myself because you know hey it's how do I go one row upward or one room down in。

A one dimensional vector， so you'd have to do all the math yourself。 I it faster， Yeah， a little bit。

Is it more confusing to write and to read and harder to get correct， yes。And is it worth it， no。

 because our solution that the timing is based on uses a 3D vector and you're allowed up to 50% more time than us。

And still get full points。So I wouldn't bother with this in Project one。

 it just makes the code harder to read， harder to write， harder to debug if you get it wrong。

So in the example here， if I had a fixed size 2D array and this one where I had a little more room。

 I created named constants for my rows and columns for the size of that。2D array。

 So I created the array， and then I wrote a loop with。Rrows on the outer loop。

 columns on the inner loop， and I go and put a value in every one of those locations。

 so I go through row0， put zero， Val gets inement1， Val gets inement， etc。

So the nice thing about this version is that。Because there's no pointers， it's a little bit safer。

 I don't have to worry about D detail。It's not safer in terms of， hey。

 can you say less than or equals here and have bad things happen， sure。

 it won't stop you from doing that， but it will make it so that you don't have to do a new and a delete。

It uses a little less memory than the pointer version we'll come back to that one in just a minute。

 The downside is this size is fixed at compile time。These must be constants。

 the size must be fixed at compile time and that's a downside in if I had to read in the number of rows and columns from the user。

 this code doesn't work now there's a note here G++ does allow you to do this if rows and columns are not known until runtime but do not use that。

If you get used to using it and you pull it out in a job interview， someone might be like。

 that's not standard C++ and you're showing a lack of knowledge。

 so we don't want to ever depend upon that。So a better way if we needed to know the number of rows and columns at runtime would be to use dynamic memory。

So I create here， I've got row columns， R and C R my indices。

 I just may as well declare them all at once because I was running out of room in line  seven and 12 and 13 to put a size T in there。

So I declare all my variables up front just R andC or just declare up front to make this slide a little narrower。

 I get the number of rows and columns from the user。 Let's pretend that they typed three space3。

3 rows， three columns consistent with the other one。

So I've got line4 is int pointer pointer A equals new int pointer square brackets row okay。

 let's take a step back。 let's do a 1 D。So if I had a 1D and I wanted to do something like this。

 I'd have like int。Pointer。Let's just call it rope。Is equal to new。Int。Square bracket count。Okay。

 so if I wanted to do a 1 d row vector， a single row， this is how I do it， I'd say， hey。

 I have an integer pointer， I set it equal to the result of new int， this many columns。

New ant returns a pointer to an integer， row must be a pointer to an integer。Well， here。

 let's look at the drawing over on the right in the drawing on the right。

 eventually what I want to have is I want to have three blocks of dynamic memory， one for each row。

 but I'm going to need another block of dynamic memory that points to each of those rows。

 So I need a to be a pointer。To a thing that contains pointers。

So that's why it's int star star and saying， I've got a pointer to a thing that contains pointers。

What do I set it equal to a new block of dynamic memory containing integer pointers？

So that's these things。 So it's going to contain these integer pointers and rows is how many there will be。

 So that let me undraw a bunch of this。So。Lime。4our， line four has gotten us to that point。

 that was line  four， we got us to that array， it's not initialized yet， but the array A exists。Okay。

 then in line 7， it says， hey， we're going to loop through for every row。

 let's set a sub R equal to a new point or to a block of integers so we get。

A sub zero points2 three columns worth of data， a1 points to three columns。

 a2 points to three columns worth of data。And then if you look at like lines 10 through 15。

 it's exactly the same as the previous slide。I loop through the rows， I loop through the columns。

 I set a sub R sub C equal to a value， I inputit the value， and we get the same values。

 Now if you look in the inset window over here， each row， the little green numbers are the index。

So the black number is the value that we end up putting in there。

 so this is the picture sort of when it's all done so line8 got us the blocks that are the rows and then lines a 12 through 15 filled in the black values gray the green values are just there to remind us these are the column numbers。

Okay， so we fill that up and we could do more stuff with it， we could put different values in。

 we could print it out， we could sum them up， we could change them around whatever we want to do with it。

 but when we're done，We've got to go clean up after ourselves。

 weve got to go delete that data Now we don't， we don't want to do line 20 first， that would be bad。

Because if I delete the array A first， then I'm not allowed to loop through it because I don't own that memory anymore。

 If I don't own it， it's not safe for me to loop through it。 So that's why we've got to go and。

Get rid of each row， think of it like。I'm building up some blocks， I put the bottom row in。

 I put the top things on top of it， I've got to take the top things off before I take the bottom out。

So I get rid of each row and the order of getting rid of the rows doesn't matter。

 I deleted them in the same order that I created them。

Doesn't matter I could delete them in the opposite order。

 but I've got to delete each row worth of data before I delete a。

So that makes sure I don't have any memory leaks。No。When we look at the pros and cons here。

 so this is fixed size， so this was the fixed at compile time。

So the fixed at compile time pros and cons。 the nice thing about it is that it's delocated。

 We don't have to do a delete。 We never had to do it do a new。

 And it says the a sub I sub J uses one memory operation。 So that's going back to。This slide here。

See when I have a two dimensional array， the compiler generates the code to do these conversions for me。

The compiler generates that code for me， and I only have to go out to memory once。

When I have the pointer version。I have to go out to memory twice。 and rid of all my marks on here。

 I have to go out to memory twice， because when I say something like。A sub1， sub 2。

 I have to go out to memory twice。 I have to go out to memory and find a sub 1。

 follow its pointer and then go to column2 of that block of memory。So there's less arithmetic。

 but there's more memory access。So with the fixed size arrays， there's one memory access。

But there's a little bit more arithmetic going on。 The downside of this is that。Remember。

 it's on the stack。 If it's on the stack， then。Its size。

Not only is it fixed at compile time because we have to declare it with a fixed size。

 but because it's on the stack。The stack has a limited size and if I say oh。

 create me an array of like 5000 by 5，000 at compile time。

 it will crash as soon as you run the program because you can't allocate 25 megabytes of times4 byte pointers。

 which would be 100 megabytes of memory on the stack。Whereas we could on the heap。

The other downside is when we pass two dimensional arrays to functions。

 there pain because you leave you have to declare the fixed size for everything but the first one。

 so it's kind of a pain。Other thing that's important about fixed size arrays to remember is that if you have a fixed size array and you accept input from somebody else。

 you've got to be really careful because if you overfill that buffer， then。

You might have a sg fault or it might be a security hole。

 some of the most common security holes and in fact。

 the biggest first one which was created by a guy named Morris back when I was a student just dependented on something that just assumed everybody that wanted to use this UniX program was going to pass you a unique name。

 a username and a username was always eight characters less。

 they just assumed if someone gave you a name it would be eight characters less so they had a field of size 8 and if you put more date and put more than8 bytes in there then。

Someone discovered that the extra bytes would eventually go into where the program was in memory。

 so if you gave it like a thousand character name， it would start looking at the name and then it would do whatever it had to do and then it would move on to other stuff and the other code would be the data that you wrote in。

So we have to be really careful with those， so what about the dynamic memory？

So the dynamic memory version is allocated on the heap。

So the nice thing about this is that the size can be changed at runtime， obviously。

We can support triangular arrays。 If you've done linear algebra。 You know what that means。

 If you don't， that's okay。 We're just saying all the rows don't have to be the same size。

 I could have rows that were sized like this，1，2，3，4，5。 I could have every row be a different size。

 or I could have larger， smaller， larger， smaller， whatever I want。 It works。

 It also allows me to swap around rows very quickly。So if I had this one that had bigger， bigger。

 bigger， bigger， bigger， and I want to reverse it， and I want to go bigger， smaller， smaller。

 smaller， smaller， it's easy because I just have to swap pointers。 I swap。This pointer with that one。

 I swap to this pointer with that one， I leave the middle one alone because it's the middle。

 I'm not I swapped two pairs of pointers and I reverse the whole array from top to bottom。Now。

 the downside is one， we've got to have a matching delete。 If we double delete， we can crash。

 if we don't delete， we can leak memory， So we've got to make sure we do a delete and the square brackets is a little bit slower because it's got two memory accesses。

 Now， I said I was going to come back to something why the。Pointer version uses more memory。

The pointer version still has。9。Integers worth of memory。 It still got nine times integer。

And it still got a pointer to the whole thing。But it's also got。Rose。Or actually。

 it's the lowercase in this one。Rose times the size of。And thenpointer。Which is generally 8 bys。

 So this one's got 24 extra bys of memory due to those row pointers。

 The version over here doesn't have row pointers。 It just uses 9 by 9 integers worth of memory， and。

ARR。Has to be a fixed pointer that points to the beginning。

 so both of them have a pointer to the beginning， this one's got three extra or rows extra integer pointers of datas of memory that's not the user's data。

Okay， there's a bunch of off by one airs here that you can remind yourself of。

 I've already seen someone in Project one made this mistake。Although it wasn't capital size。

 it was like lowercase size， but I was like， oh， wait wait hold on。

 you're going to have Seg fault there eventually。So remember， we need this one to be less than。

If we're doing indexing， so you got to be careful with those。

So you can look at some of those off by one errors， the range based for loop。

Not super useful in Project one， but it's a good thing to know the range based for loop。

 which started in C plus plus 11， it has a couple of different names。

 Some people call it the range based for loop， some people that call it the for each。Wep。

Other people call it the enhanced。The enhanced for loop。

So it's a range based for loop now one thing you may not realize about the range based for loop is you're allowed to use references with it。

Now， if I wanted to just print out what's in that array， I could say something like that four。It。

X colon myre。And I could see out。Less than less than x， less than less than a space。

 and that would be fine。I don't need a reference there， but if what I want to do is change them。

 I want to double all of the values。If I get rid of the ampersand， what happens is。

I get a copy of the value1， I double the copy。And it leaves the original alone。 So this one。

 if I get rid of the reference， this loop wastes time doing nothing。 It makes a copy。

 doubles the copy and throws the copy away and gets a new copy。But if I leave the ampersand in there。

Then， it。Has a reference to the first value。 it doubles it to2。

 And then as the for loop goes back through the for loop， it says， okay， I have a new reference。

 I now have a reference to that one， which we can double to be 4。

 and then I have a new reference to that one， which we can double to 6， etc cetera。So。

If you need to modify things with an enhanced for loop or range based for loop。

 you need the ampersant， if it's a container of something like strings。

 then we could do a con ref to say， hey， I'm going to look at these strings。

 I'm not going to change them， but I also don't want to copy every string just to print it out。

I want to look at a reference to the string， I will print out the original string and I'll move through so you can do you could add con。

In here， if were going to print large object。So same rules， basically， and this is in the Can files。

 resources， optimization tips。If you have to modify it， you need a reference。

If it's a something else， I should say else， if it's a small type of variable。

 like an entert or a bo or a double， pass it by value else。Else， meaning if it's big。

 but you're not going to modify it， conre。Okay， here's another one。

An example of things that can go wrong with command line processing。

 and we're not doing the command line processing ourselves anymore。 we're learning to use GitO long。

 Why do you use to learn to use GitO long， Let me give you an example。

You're allowed to say you could say dot slash supermarco。Dash。S O space capital L， whoops。

 that's terrible M。You're allowed to put a single dash followed by multiple single options。

 and you don't want to have to write the code to deal with things like that。

So especially if there were more options What if we had like four or five command line options and I did like dash ABC D。

 space capital X， you don't want to have to deal with。ABC， all are no argument， D has an argument。

 but there's only one dash for all of them in a grouping。

 you don't want to write code to deal with all those different cases， so get uplong does it for you。

Now， if we do process the command line ourselvesse， we've got to be careful。Arg V of0 always exists。

 so Arg C is always greater than or equal to1， because Arg v of0 is always the name of the running program like du slash supermarketco would be Rrg V 0。

But Arg v of1 isn't guaranteed to exist。So maybe that's one error。

 A R of one might not exist if I didn't put anything on the command line。 Also。

 there's no guarantee that what I put for that first R option or that first argument is。A。

Length that will fit in name oh， there's typo in this slide This slide should not put the word cs there。

 we want to get rid of that it's important to not have the word cs there when we're using get off long at least if we're doing it ourselves who cares。

 but with get up long it's got to not be casts。So whatever I put on the command line might not fit in name if it was 20 characters long。

 it would not fit in name。Because there's got to be a back slash zero at the end。

So this has got problems if av of one doesn't exist。

 it's got problems if Rv of one is greater than 19 characters in length。

And so we could make it safer by using a string。Copying into the string object。

 but only if the argument exists， and obviously you know we'd put more code in here。

 do things with name， etc。O。Job interview question here， this is a good one。To think about here。

 So I tell you， I've got an array and I claim there might be a majority element。

And I'm not guaranteeing that there's a majority element， there might be a majority element。

 and the majority means it's got to occur more than 50% of the time and you want to find it now let's ignore the constraints for a minute。

 ignore the constraints。How could we do this？We could， hey， I could look at every value。

 I could look at the 11 and then loop through everything else and count up the 11s。

 and then I could look at 13， loop through all the others and count up the 13s。 look at the 99。

 loop through all the others， count up the 99s。 So that would be big O ofs。Big of n squared okay。

 so if I loop through O out that just that was my pen was not working very well there and I know I charged it Okay。

 so this would be O of n squared。All right， that would work， but it would be really slow。

 Okay what if？We sorted it。If I sorted it， then what I would do is I would say， hey， I've got a 10。

 let's go until the end of the 10。 Oh， I'm done。 Okay， I've got an 11。

 Let's go to the end of the 11s。 I'm done。 I got 12。 Let's go to the， Oh， I'm at the end of the 12。

13。 Oh， I'm at the end of the 13s，99。 There's one of them， two of them， three of them，4 of them。

5 of them， aha， There's 5，99s in here。 And that would take。O of。The time to sort。Plus， or event。Well。

 the time to sort this， we can't do better than N log in。

So this end up being this would end up being O of and log in。Better than n squared， certainly， but。

What we really wanted to do was we wanted to do this with OM time。

 so we wanted in linear time and a fixed amount of memory。

 so if we had more advanced data structures and we didn't have that restriction on memory。

 we could do it if we used like a hash table or an unordered map。

 but with these restrictions we got to be trickier。

Now the key here I'm not going to give you the answer today。

 what I'm going to do is I'm going to give you a hint。And say。

Constant time does not mean you only look through at once。

You could look through it two times or three times。

That would be fine as long as you look through it a constant number of times。

 so if there's n elements， n is arbitrarily large， if I look through it two times that's still o of two times n is O n。

 so that's the key to solving this。If you want to look this one up， it's referred to as mos。O。

We're voting algorithm。Now there's other names to it than that。

 but it's also called the Boyer More majority vote algorithm is I think the real formal name。

 but if you look up Moore's voting algorithm， you'll find it。The second one here。

 what if I relax the restriction and I say what if there was a majority element it might be there might be。

 there might not be， what if there might be a majority element that occurs more than n over three times or more than n over four times or more than n over。

K times where K is some constant。Okay， this one， we've got to restrict the。Constraints a little bit。

We still get O of M。And over then average time。But we need O of K memory。And this one is。Called Mira。

Breeze algorithm。So good things to be able to pull out in an interview if you run into a question related to this。

So Mres is just an expansion on the Moore's voting algorithm and it uses a hash table and an unordered map to do its work。

All right， so what I would do is think about that a little bit， try to see a way to do it。

If you can't， that's okay， it's a tough one， go look it up after you try to think about it。Okay。

 what if we had a container， all right， things like vector？Dack。Stack queue list map， etca， eta。

 et cetera， so if we're talking about containers， that's what we mean is it's an object that allows you to hold multiple copies of generally the same type of item。

So if we want a container that holds different types of items。

 that's where we makestructs and classes， and if we want to make a really complex container。

 we put containers inside of containers。I say， hey， you know。

 I need a container that's got a char and a bo and a char。

 but then I can put it inside of a vector that contains lots of copies of that。Next type。

So these containers are really useful， they allow us to have some sort of protection over the data like stack and Q。

 only let us operate on the top of the stack or add to the back of the queue take from the front so they might have some protection over the data they might。

Keep the data sorted， they might keep the data in a certain order。

 they might allow us to like copy the whole object at once or edit。

 like change all of the values at once， lots of different things that we could do with a container。

 but generally they allow us to put things in， take things out。

 look at what's in there in some way or another and maybe a few other features like you know copy constructor operator equals。

 etc。So we've got a bunch that we've started talking about like vector and deck from the standard template library。

So what we're going to look at in this class we're going to look at in a few lectures we're going to look at ordered and sorted ranges after the midterm。

 we're going to look at heaps and hash tables and actually heaps will come before the midterm hash tables and trees and graphs will come after the midterm today we're going to be looking at array based containers as an example of containers and things that we can do with containers。

So。Since this container is going to be holding a variable amount of data。

 they generally work with behind the scenes， they have pointers。So if we've got a pointer。

 then we are going to have a constructor， a destructor， we should have an operator equals。

Just have an operator equals， I got to learn to write a little bit better。

So we've got a constructor destructor operator equals， we want to have a way to add something to it。

 usually we want to be able to get something out， we want to look at an element。

 either look at a particular one like I want to look at index I or I want to look at who's at the back。

Or oh， there is copies just further down。 We want to be able to get the size of the container。

 so it's nice to know， hey， how big is this container， how many elements are in this vector？

Assign an element， so besides adding a new element。

 I might want to overwrite of one value with a new value。

 that's something I might want to do and I might want to do other things also。

Like one thing that I always find is I'm like， gosh， why can't I just say something like， hey。

 I've got a vector event。Oopps。Dctor of int to V， and I do a bunch of pushes。

 why can't I just say C out less than less than V？Why can't I do that？ Well。

 partly because they didn't know how you wanted it to look。

 Do you want em all on one line of spaces in between。

 Do you want them each on a separate line with a back slash and after it， I mean。

 that would be something that would kind of be useful if we make our own container。 We can add。

An output operator or printme member function or whatever you want to call it so we could do things like that and anything else we can think of。

 we might want to be able to have a container that says， hey， container， sort yourself。Actually。

 there's already one like that， the where slide number link lists。

 linked lists have a member function called sort。Vectctorors don't， vectors。

 we got to do differently。O。So when we start making container。Sit code we're writing on ourselves。

 we need to know what kind of access are we going to use。

 are we going to have sequential access where you start at the beginning， you go to the next。

 you go to the next， you go to the next， which is like a linked list would be an example of a sequential container。

Are we going to allow a random access to our container？ Like。

 can someone put data inside of my container and then say， hey。

 I want to look at index I and do that in O of one time。 So if I can go directly to the item。

 this is O of one time here， if I have to skip over n items to get to the n item。

 this one would be O of M to do a square brackets。So the random access is used by things like arrays vectors。

 in fact， DX， we talked about how decks have an01 operator square brackets。And we can still。

 even if we have random access， we can still allow sequential access。So if I have behind the scenes。

 I've got a block of dynamic memory， I can allow random access and I can allow sequential access one at a time。

But if I have a linked list。Then I'm forced to so if behind the scenes， internally。

 I have a linked list， then I can only give you an efficient way to sequentially access things。

Now if we wanted to copy an array， so I've got here， I've got a size。

 I've got a source array which happens to be that size and it's initialized to 3561。

 there's picks and values， and then I've got a destination array。

So I want a copy from the source to the destination。 Now I could do that with a。Simple for loop。

For loop， index， square brackets， square brackets assignment。Simple works。

I could also do it with pointers and incrementing。Now， this version takes。

More lines of code it takes four lines instead of two。

 and I suppose if I could combine eight and9 into one line。

 I could really just change that semi column into a comma， get rid of the word double there。

 and it's effectively one line of code if it was a little bit wider。

So I could do that in three lines of code， but it's a little harder to read。

So I've got this wild loop while the source pointer is not equal to the source array plus the size。

 Okay， let's take a look here。 So I've got source array。So source array points here。

 source array has in it。3，5， six， long， and I start out with SPR。Points there。So SPTR points there。

 and then in the。Destination array。Which is a pointer to a block of memory of size4。

And I've got a D pointer， I've got a destination pointer points to there， I copy the three over。

 I increment the pointer， I increment the pointer， and then I put a five and a6 and1。

 So when SPR moves off the end this loop is saying while source pointer is a valid pointer。

 So if sort of source arrays here， then where is source of source array。Where is？SRC array plus size。

Where is that a point or two， Well， size is 4， So array plus 0 would be the beginning of source array。

 So array plus size is。Just past the last one。So I say， wow the。

Source pointer is not equal to the one that's just off the end。

So while it's not equal to the one that's just off the end， the syntax here。I showed you what it did。

 but we didn't break it down， so this says noticeice that they are both post increments。

So what has to happen is we've got to figure out where does the source pointer point to。

Then we figure out where the destination pointer points to， Then we can do the assignment。

And then the plus pluses happen in some order， it's not well defined。

 but they both happen after the assignment happened。Now， you might say， wow， that's hard to read。

 Why don't I put some parentheses in there。 That'll make it better。No。

WeBecause the dereence has to happen first。So if I put a D reference around SPTR。

Then what happens is。I never move the pointer。 I de reference the source pointer。

 and I change the three to a4， and the pointer never moves。 It still points here。

And I change a4 to a5， a 5 to a 6， a 6 to a 7。 And it happens forever because the source pointer never moves。

 And I just change 3，4，5 up to the maximum for what's whatever's in there。 that double okay，10 times。

1。8 times 10 to 3008 power， I think， is like the maximum double。So that's going to take a long time。

So that's basically almost an infinite loop， so we can't put in parentheses to make it clearer because they make it wrong。

We can't put the prehees around the plus plus because that would mean it's supposed to happen before the D reference。

 So then we would plus， plus before we de reference， and we。

 we would never look at the first element。So we can't change that。

 We just have to get used to seeing this syntax of dereference。

Pointer plus plus equals de reference pointer plus plus this thing is， this loop is so common。

 it's on the cover of one of my operating systems textbooks， that loop。

So why would we use the pointer version if we've got the array version？Well， one。

The pointer version is demonstrably faster。Second， the pointer version。

Allows us to expand up to iterators。While maintaining the same syntax。Now。

 does this mean you should do everything with iterators。 No， For the most part， our projects。

 we write a solution the way we think you would write it。Or at least should write。

 like we use a 3D vector， we use indices， we don't use iterators。Now。

There's one other thing key about line 11， but not equals here。

The not equals is the right way to do it With this example。

 it would compile and it would run with less than。But if I change this to link lists。

And I use linked list iterators and I use lessM。It won't even compile because linked list iters you're not allowed to do less than。

But every iterator works with not equal。So array or I should say vector iterators。

 linked list iterators， deck iterators， they all work with not equal to some of them work we work with less than others won't。

 so we just stick to not equal。And it gives us this sense that we've got this。Begin。

Is inclusive and our ending is exclusive。So。Source array， the starting point is inclusive。

 sourceurce array plus size is exclusive。 And when we look at vectors and vectors have iterator functions like dot begin and dot end。

 they return iterators in this sense of inclusive， exclusive。O。What do I put in a container？

So what would I like to put inside of my container and remember I'm putting really inside of my container we're talking like what if I was making container and what am I going to do behind the scenes like you say I want there to be。

Chars in that container。Okay， we can do that。 We can we can keep a container of chas。

 like a vector of chas or a deck of chas。 So I'm the container you say put characters inside of that container。

Okay， that's your choice。Now， the nice thing about that is the data is all owned by the container。

The container does the the container does the news， the container does the deletes and。

It takes care of it full you。 The drawback is if it wasn't a character。

 if it was like a vector of student objects， it could take time to copy those。

 like when the vector grows， it takes time to copy all those student objects from the smaller array to the new bigger one。

But it's very common。This is a very common way to do things to say，Make me a vector containing chas。

Okay， what about if I tell you make me a vector containing char pointers？

So you've got to maintain behind the scenes char pointers。So then the question is。

 who owns which part of the data， Like， if you create a vector of char pointers。

 the vector owns the block of memory that contains pointers。

 but the vector isn't responsible for who it points to。 That's really your job。 You said make。

You said hey， vector， I want to store cha pointers well the vector is going to maintain the dynamic block of memory of pointers to characters。

 but it's up to you to maintain the pointers to the actual blocks of character data。

It's a little bit unsafe because I can once I've got a pointer。

 so like someone using this vector can get pointers to your data and can modify your data just by having access to the vector。

It is though useful sometimes if I have things like char pointers， so if you've got char pointers。

 you might want to put char pointers in your vector because you've got these character arrays that end with a backslash zero。

OkayThe other nice thing is shared data like if I have to have a master copy of the data。

 but I need it to be in several different containers like in different orders of different ways to access it。

 but I don't want to copy all these big student objects。

 I might just want different ways to access that big container of student objects。

 I might have like big container of student objects and have like maybe a priority queue of pointers to the actual data。

And a vector， so I might have a vector of the data。

 and I might have a priority queue of pointers that point to the vector。

So that's called shared data where the data really is being used in two containers at once。

The last one here in the top table is references。 Like I say， make me a vector of references， well。

It won't even comply。You can have a container that holds a single reference。

Like I can have a container that has inside of a reference to an integer。

 but I can't have a vector of integer pointers。Or sorry， I can't have vector into your references。

 So containers of references are。Painful to try to use with the STL。

 they won't even compile if you try to make it on your own， it's。Painful even to get to compile。

 let alone work。Because you can't change references when you create a reference。

 it must refer to a real object that already exists。

 and that's hard to do with a large collection of them。Okay， so let's say I've got my container。

 so I've written a container， you give me a type and I store that type。

 so let's say we've gone with the most common， so we've gone with the most common so I have got。

Chars inside of my container。 And you say I would like to look at one of the elements。 You give me。

 Here's an index。 Let me see that character。 Well， I could give you。Value， I can say， okay， here。

 at the look at the character。That works， but it's costly if it's not integers。 What if it's a。

Container of student objects， then giving you a copy of a student object can be costly， can be slow。

All right， I could store your type， whatever you said the type was。

 you give me an index and I give you a pointer to my internal secret data area。

That's kind of unsafe because now you've got a pointer to my private data。

You can move that pointer to look at something else。

 You could move off the end of my private memory without me knowing it。

 You could change the data inside of my container。 What if my container was supposed to。

 whatever you put inside of me， I keep it sorted。 But if I give you a point or two。The middle of it。

 you could change that to make the whole thing unsorted now。

And now it looks like it's my fault that it's not sorted， but it's your fault。

So giving pointers to your secret internal data can be dangerous。

It can be done and it is done vectors have a member function that will let you look at their private data。

Now what about a reference， what if I say okay， you start a bunch of characters。

 I hold them in my secret internal memory space and when you give me an integer。

 I give you a reference to the data that you stored there。And you can change it if you want to。

 That's up to you。 I could also make another version of this。 I could have a version that has。

Cost in there， constant reference to a character。I could have both。

I could have a cont version that says， look， but don't touch。

 and I could have a pure reference version that lets you change it。

 And this is actually a pretty good choice。 This is what most SL containers do。

 Most of them implement both the con version and the non cons version， some of them。

Only have a con version， some of them only have an not con version， and some of them have both。

 So things like vector and Li list and D have both。Unordered maps only have the non cons version。

 they have no look but don't touch version and priority cues have only the cons version。

 you can look at the top of a priority queue but you can't modify it because if you modified it。

 maybe it doesn't belong at the top anymore。So these are the choices that like the STL chooses to do。

 so when you tell the STL make me a container characters。

 it stores what you said and when you say show it to me， it does this。

 it generally either gives you a ref or a congraph， maybe one exists， maybe both exist。Okay。

 so when we're talking about I'm making my own container type。

 I'm going to be the new container type and I'm going to call it array with capital A and I'm going to store stuff inside of it。

Well， I've got to be careful of my internal data。This is20 sorry 80 stuff right。

 we don't want to have two array objects that point to the same block of memory。So if this。

 if I accidentally allow this to happen when I modify a。

B looks like it magically changed when you know， you didn't change B。What happens when I delete a。

 when I delete object A， I'm assuming I wrote the destructor properly。

This memory gets mixed out and someone referring to object B is really being playing dangerously because it's referring to memory that has been given back and might be currently used by somebody else。

 And then if I later delete B， that's definitely an error， I get a double delete error。

Because I'm deleting something that is not currently owned。

So lots of problems happen occur if we allow this to happen。So the idea of memory ownership。

 there's two big。Different ways to approach it one is。If basically if you knew it。

 it's your responsibility， if you do the new， you're responsible for the delete。

 you're responsible for the copy constructor， you're responsible for the operator equals。

 it's your job。And then the second。Approach is。嗯。There's no ownership。There's no one ship at all。

 You do news。 There's no such thing as a delete。 And when things are not being used anymore。

 somebody， we call it the garbage collector。 The garbage collector is eventually going to discover that。

 hey， this thing， nobody's using going anymore。 Let's let's。

Unallocate that block of memory and this is what Java does if you're used Java it does this in C+ plus smart pointers do this。

 you should not do this。Also， oh， this reminds me。Look at your compiler feedback， look at the build。

Output。On the when you click on the timestamp， if you look at the wow I really cannot type today that's supposed to be V U ILD okay。

 look at the build output on the autograr， I've seen people who are including usually it's IOmanip is the problem if you include a Iomanip in Project one you will lose 90% of your points because it it has the ability to allocate smart pointers and you're not allowed to use smart pointers so if you see wow I've got lots of yellow and blue but I only got five points what happened。

Look in the build output， it'll tell you why you're losing those points。Okay， so when we're doing。

Our own memory allocation， when we new memory， we've got delete it。

 One safety tip is instead of just deleting it， set delete it and set it to a null pointer because if if in the future。

 so if I do this one and then Is delete。PTR again， after that， deleting a null pointer does nothing。

Whereas if I get rid of this line and I accidentally delete twice， that's a runtime error。

So doing the equals null pointer can be a little bit safer。So if we're going to。呃。

Do a new then we should be responsible for the delete， the copy constructor， the operator equals。

So we don't want to leak memory。Why don't we want to leak memory？You might say， well， wait a minute。

 when that program ends， the operating system is just going to go take that memory back。Well。

 that's true now， it didn't use to be true。In older versions of Windows。

 I had a game than I was playing that if I played for too many hours。

 the game would just crash because it leak too much memory and I had to remember to play for like an hour or to save it。

 quit， reload， and I'd be fine。But you say， well， modern operating systems aren't like that， okay。

 true。But what if you take your code and you're not stopping your code。

 what if your code goes into a car？Should the car say car out of memory air please pull over and restart the car？

Or your refrigerator software。 Oh sorry， all the food in the refrigerator boiled because you forgot to reboot it it once per a day。

Okay， so embedded systems that are not in a small program。Are dangerous What if okay so you say well。

 I know it's not gonna be running in a car or refrigerator or anything like that。

 I know it's going to run on a computer， I wrote this little sample program that proves that this works and I didn't bother to clean up my memory well maybe your boss had you write that little sample program to prove that it could be done and then someone else takes that code throws it into your big system and now the big system doesn't get stopped every time your code is run your code gets run10 times maybe before the program stops and your code runs it out of memory。

So。Even if you think， oh， I know it's going to be run on an operating system。

 maybe it'll get used in a bigger system and now it's leaking memory。

So we can use Valalgriin to help find those memory leaks。

 and I demonstrated how to do that last time。O。News and deletes。News and deletete。

 so remember if we do a new we have to do a delete。

But there's two different versions of each of them。So there's new。And there's new square brackets。

If there are objects， the constructor gets called， if they are basic types like Inter double。

 there's no constructor， there's no initialization， there's no anything。

 you just give a block of integers that is uninitialized。Or a single integer that's uninitialized。

For delete。Delete if it is a class， it will invoke the destruct a if it's delete square brackets and it's a whole array of。

Objects they get all get their deors called， but if they're basic types， they have no deor。

Now one thing we have to remember is if we do a new， we have to do a delete。

 if we do a new square bracket， we have to do a delete square bracket。Now。Why are there two versions？

Why don't we just have one version？Well。It's how things happen。 Remember。

 one nice thing about delete is。We never have to tell it how many bytes to get rid of。I say new int。

 when I delete that int pointer， it knows to get rid of four bytes。

When I do a new square brackets and I say， hey， I want new int 10， it knows there are 10 integers。

And a pointer to them。 So when I give it the pointer， it knows exactly how much memory to get rid of。

You say， okay， well， fine， make two versions a new， but one version of delete。

And then we just delete memory。 We don't care how it got nude。 Well， the problem is。

 somebody's got to remember with new square brackets。 You've got to remember the size。

 The size has to be stored somewhere with new。 When you do new int， there's one integer。

 When I do new。Ut。Square brackets  one。 There's one integer and one size。

 So this is actually a new int。This is four bytes because that's how big an integer is。

 This is4 plus。Eight， which is the size， so if I did like 10 in drews。

 it would be four times 10 plus 8， it's got to store the size in memory somewhere。

So that's why there's two versions of deletete and two versions of new new allocates exactly what you asked for。

 new square brackets allocates what you asked for plus a size is stored somewhere so that when you say delete square brackets。

 it knows to look up the size to know how many bytes to get rid of。Okay。

 we've got an example here which I know we're going to go over time today。

 but if you have to leave that's fine， we'll get this on the video， sorry， I started late。

So we've got an array class here we're saying， hey， let's make our own array class。

Inside I'm going to have a length which starts out as zero and a data pointer which starts as null pointer and I did double here I could have made this different。

 I could have made it templated but that would have been more work I just wanted to get at least some basic stuff here so I've got a constructor and I wrote the constructor I wrote everything in here inside the header file I'm going write everything inside the header filephat this great if it's templated required if it's templated on this one it's not required since it's not templated but it's simpler to fit it in here and then in subsequent side slides。

 I don't have to say a ray colon and colon so if we the other methods that follow。

 we're going to assume they're all before the closing curly brace。Okay， so I've got a constructor。

 I use the initializer syntax now you're going to say why are there curly braces here。

 aren't those supposed to be parentheses？Well， curly braces is considered what's called the uniform initialization syntax。

This is the I really know C++ way to do it parentheses work。

 parentheses compile parentheses run just fine curly braces say I'm really a C++ person。

I really know my stuff。So that's the uniform initialization syntax。

If we're going to initialize things， it is required。

 we must initialize them in the order they were declared if I declare length and then data。

 I must initialize length and then data in that order。And then this right here。

 this is the body of the constructor。 The body does nothing。

 I've initialized all my member variables。 I'm a good constructor。All right， destructor。

 got to have a destructor if I to have a new， I got to have a delete。

 write those right away when I write code， when I'm doing news and deletes。

 I never write a new and then say， oh I'll get back to that delete later。

I go and write the delete right away to make sure I don't forget about it。

 so we do the delete square brackets on that data and I did the safety here set it equal to null pointer Now granted I know it's a destructor I know that this object is dying。

 but I still it anyway。I've got a simple function here called size。That returns length。

Now it's not a reference， but it says con here。What does that count mean？

Canst is always a promise that something won't change。

This is a promise that this member function size。Promises not to change any member variable。

And it means that if。I'm writing some other code I ordered you to say， I wrote the array class。

 you wrote some other code， you accept an array object by cons reference。

If I get rid of the word con here， you can't look at the size because you said I've got it。

 I accept a con reference to an array object and as soon as you try to look at the size function。

Compilr says no because size。Did not promise not to change anything。

 You accepted a reference that you promised not to change the object。

 but this function didn't necessarily keep your promise。

 So this is what I talked about in a previous lecture about， hey， more constant is better than less。

I say this function makes a promise this function changes no memory。If you try to do that。

 if you try to say in here， like length equals one。Semicollon。

 the compiler will reject this line because the function said。

 I promise not to change member variables。Okay， so there's our basics。

 we've got a constructor and a destructor。We got a size function。

 and we'd like to have other functions， too。 Oh， why， why a class or astruct here。 Well。

 I'm going to have private data。 I'm going to have public functions。 That sounds like a class。

 But there's really no reason it couldn't be astruct。 I could still call this。

 I can replace the word class with struct。The only thing I'd have to do is that I'd have to add the word private。

Colon before line2。 So if I make it astruct with private data and public member functions。

 it's basically a class。So I choose when I'm writing something that has private data and public member functions。

 I create a class， when I'm just writing public stuff， I make it astruct。

Just because it makes sense when you see it。Okay， so I've got here some code for。A copy constructor。

How do I know it's a copy constructor， Well， the title of slide said so。Also。

It's a constructor because it has no return type and the name is the same as the class。

And I know it's a copy constructor because it receives an object of the same type by。

Cost reference now。Is the contra required？Well， the con isn't required。

 but it's polite when you accept by reference and you're not going to change the original。

 It's polite to make a promise。 I promise not to change the original。Reference is mandatory here。

If I didn't pass it by reference， if I passed it by value。

Who's responsible when things are passed by value。 Oh， the copy constructor。

 let's call a copy construct， Oh wait， the copy construct wants a copy。

 so it should copy construct call itself so it can pass itself a copy so it can call itself to make the copy。

 so it can pass copy。Infinite， the compiler will not accept it if you don't say reference。

Saying cons reference is polite because you're promising， hey， to make a copy of that other object。

 I promise not to change it。So we initialize again。

 we initialize the length and the data to a new block of memory。

 and then I run a loop to copy the elements over in the block of memory one at a time。

So I would add this copy constructor inside of my class。

 like before the closing curly brace in the previous slide。Now I've got a couple of things down here。

 I've got a copy construct sorry I've got I created array A of length 10， array B of length 20。

 I created array C is a copy of B。I created array D is also a copy of B。

 even though there's an equal sign there， line 9 and 10 do the same thing。

 because the array D did not exist yet for array D to exist。

 it must be constructed and it is being constructed from B， it is copy constructed。Now， in line 11。

That's assignment。 I've got an object that already exists。

 and I set it equal to an object that exists。 That's assignment。

 If I don't implement operator equals， we get a shallow copy， and bad things happen。

So we need to do a deep copy。Now， the complexity of copying。Is over。We've got to loop through。

 we always have to loop through all of the n items best worst average， it's always ON。

 so when we copy construct， it takes ON time to copy。Now there's a slide here that says。

Better copying， so I've got a copy from I've got a copy constructor， I've got an operator equals。

 don't look at this。 This slide is terrible。 This is the wrong way to do it。

 There's a better way to do it on the next slide。The next slide it says best copying。

 this is the right way to do it。So the copy constructor here。

 this is just the same copy constructor we already wrote we're not changing。

So that topic constructor is done， and then the key is how we write the operator equals。

And it's in the comment here， this is called the copypy dashash swap method。

So the copy swap method is what we are implementing here。

So let's look at what happens and we're going to draw down on the next slide。So it says。

When we're going to copy。With operator equals， what I'm going to do first is I'm going to invoke。

The copy constructor， I'm going to make a copy of the other object first。Now。

 after I've got that copy made， temp is the name of the copy， so after I've got that copy made。

 then I'm going to do some swapping。So what does the swapping do here？Well。

 it says I'm going to swap my length with temp length。 I'm going to swap my data with temp data。 Now。

 I only have one screen to show to you。 So you've got to somewhere have your code handy to look at the code and we're going to draw this out。

 what happened。 Sopper， I dude something like this。 I said like array。A as of size 5。Okay。

 and I said array。B。Is of size 10。And I did some stuff to put some stuff in a array A。

 So I end up when I'm， when I'm done with doing stuff， I've got A， A is the name of an object。

 Remember， a has inside of it， a size 5 and a block of memory of size 5。And let's say it has one。

 two， three， four， five， so that's object A。Then I've got object B， let's draw that below it。

 so object B has a size of 10， and it's got a block of memory。Of size 10。

 let's pretend there's 10 in there， so there's object B。Okay。

 then I add a line of code after filling up array， object A and using a object B， et cetera。

 and I say。B。Is equal to a semicolon。So now you can see the code for the operator equals。

 let's see what happens。When I start the function， so now I'm going to draw over here on the right。

 this is what happens inside of operator equals。And the parameter name is other。那。

Where is the object other？😡，The object other doesn't exist。When I say other。

I am referring to the right hand side of the equal sign。What is so okay， so when I say other。

 other is synonymous with a right now。So other synonymous if with a。

 what is so if I'm a member function， right， all the operator equals I'm a member function。

 who is this？Oh， this is the current object。 That's the left hand side of the equals。

 So this is a pointer。That points to object B。Okay。

 so that's the state of things right now Now we're at line 11。

 it says create me an array object temp。Using other， okay， so array object temp gets created。And。

How does it do that？ Well， it says in the comment， use the copy constructor。

So in line 11 I'm calling the copy constructor so the copy constructor says make a copy of the other object。

 well that's object a， so tempemp basically gets made a copy of a， so Temp gets a copy of the value。

5， which is the size。 It gets a new block of memory of size 5。

And then the four loop runs and it fills it with the values，  one，2，3，4，5。

So now the temp object has been constructed。We're done with line 1 now we get to line 14。

It says swap， swap length， length must be the current object's length。

 It says swap the current objects length with temps length。 Okay， current object remember is B。

 So this says swap that 10 over here。With the value5。So temp gets a 10 and B gets a5 as it size。Okay。

 now it says。Swap。The data， well I've been drawing this wrong。

Object B doesn't really contain that array。 I made I goofed here。What object B really contains is。

A1 and a pointer to that block of memory temp contains a five and a pointer to that block of memory。

 that's what's in objectject temp is a five and a pointer。And object B had a 10 and a pointer。

 so I swap the value， so now temp has a 10， B has a 5， and now I swap the pointers。

So now B has a pointer to the new block of memory of size 5。

 and temp has a pointer to that old block of memory of size 10。Now， when the return happens。

 we'll worry about the this pointer and stuff in a sec when the return happens。

The temp object is destroyed。 When temp object is destroyed， the10 goes away。 But remember。

 the pointer to the block of memory of size 10 goes away。And I am left with object B。 Ob B says my。

 my size is 5。 and I've got a pointer to this。Copy of A's data。So that's the copy swap method。

 I make a copy and then I swap。I want when temp is destroyed， I want。As， sorry。

 when temp is destroyed， I want B's old data to go with。So I swap them。

 So I know temp is going to get destroyed， I'd let it happen。Now， when I say return， dereence this。

 that's saying return the current object， but how am I returning it？I'm returning it。

 I go to the next slide。 I'm returning it by reference。

 I'm returning a reference to the current object。 While the current object still exists。

 It's okay to have a reference to the current object。

 I don't want to pass it by array value that would make another copy of the current object。

I want to pass a reference back to whoever called this operated equal。

Notice the cool thing about this is in the better copying， which is really the bad copying。

In the bad copying， we had to have an idiot check。The idiot check is in there to prevent us from accidentally destroying things。

 Notice in our best copying， there's no idiot check。Good coders don't pay the cost of an idiot check。

What happens to bad coders， bad coders who say x equals x？That costs O of M to copy。😡。

They make a copy of the current object， they assign it to itself， they destroy the old copy。

Bad code pays a bigger cost of O of M， but good code does not have to pay the cost。

Of the O1 idiot check。I call that a winner。Bad code gets more expensive。

 good code gets cheaper and code gets simpler。 The reason that this best copying is also really。

 really cool is。😊，You never have to write another operator equals in your life。

You write the copy constructor。And then you use this as a template for how to create your new operator equals what do you change Well。

 you change the let me get rid of the marks here， so if I'm going to turn this into a new class like oh。

 I don't know project 2 part B pairing PQ operator equals。

 I change the return type I change the parameter type I change the type of the temporary object and I might have to change the list of what variables get swapped and I'm done。

It's literally just copy and paste and。Modify now， promise， though。

 promise me you won't copy from Pdf。 Youve got to retype from PDFdf the first time。 But after that。

 once you've got one of these， you can just。Copy the one of these that you have and make it a new one。

Okay， big three is really a big five if when they told you big3 they're a little bit lying to you。

 there's really a big five the other two you don't need to know they are advanced C+ plus stuff they do good things for you like if I have a function that says。

I'm a vector of int function F。And I make a vector。Of ant。Inside of me。Result。

 and I fill that up and I return。Result。C+ plus 11 makes sure that result doesn't get copied。

 it steals its data and returns it and then doesn't actually copy that vector to get it out of the function So things that you think might be slow are actually pretty fast if you're using a C+ plus 11 or beyond compiler。

Okay， we're really， really running out of time today。

 I know we're a bit over the operator square brackets。We implemented two versions of it。

A cons version， a non con version。We throw an exception if we don't like the index。

And then we otherwise we let them look at the data and we need two versions because， hey。

 what if sometimes I just want to look at it and other times I want to assign to it that's why I need two versions。

 Here's another example of why I need two versions。I accepted a constant array reference。

 I said I promise not to change it， but I looked at the size。 size has to be cons。

 I looked at the overloaded object square brackets。 Object square brackets has to be constant also。

So we've got to have a con version of size， we've got to have a con version of square brackets。Okay。

 inserting an element， you can look at this， this is pretty easy。Complexity insertion is all down。

 and that's it。Okay， so sorry we went to over here because of my late start and my。

 I'm going to have to figure out why my thing does not look right to me but looks right to you。

 so we'll see you off ours。
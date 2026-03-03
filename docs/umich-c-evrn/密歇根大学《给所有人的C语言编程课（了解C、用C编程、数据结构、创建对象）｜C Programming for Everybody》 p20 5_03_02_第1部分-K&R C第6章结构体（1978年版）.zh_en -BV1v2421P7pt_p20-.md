# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p20 5_03_02_第1部分-K&R C第6章结构体（1978年版）.zh_en -BV1v2421P7pt_p20-

![](img/31bfcd4c175bf603475ce9fd0a836013_0.png)

Structures structures is。One of the most beautiful parts of sea， like pointers。

It's a user defined type that contains sort of one or more types within it。

 we call things like X and Y， in this case， members of the structure。

 X is a member of thestruct point and Y is a member of thestruct point。

The dot operator allows us to take a variable that is a structure variable that has all these members within it and then access the members of the structure。

 So an example， K R 0601 dot C， we have struck to point open curly brace double x sumcolon。

 double Y semie， closed curly brace semie， and this defines a new type。 It doesn't allocate any data。

And then we saystruct point P1 comma P2 semicolon， and that actually allocates two points。Which is。

Four doubles。Named P1 and two of each point is P1 and P2， then I say p1。x。Equals 3。

0 and I say p1 y equals 4。0 and then I say p2 equals p1。

 which copies all the fields into the corresponding locations in P2。

 and then I print them out and I get3 and4， and so that's basic structures。



![](img/31bfcd4c175bf603475ce9fd0a836013_2.png)

Simple， clean， elegant， understand every line of this。 memorize it when you do a， in a sense。

 call by value with a structure。

![](img/31bfcd4c175bf603475ce9fd0a836013_4.png)

The entire structure is placed on the stack。 And so you don't want to make structures too gigantically big。

 You know， if they're like 10 to 40 Bs of characters， they're not all that bad。

 But when we makestruct point PMm and set X and y to 3 and 4。

 And then we call funk with funk open print PM close print PM is a structure that is in the scope of the main program and then we're calling funk and passing it in。

 And then we're accepting it as a structure inside of funk。 And the key thing there is at this point。

 it's a sort of copy call by value where the entire structure is allocated on the stack and then passed into funk。

 So if we change it inside funk PF dot x equals 9。0 and PF dot y equals 8。0。



![](img/31bfcd4c175bf603475ce9fd0a836013_6.png)

It changes locally。And we can print it out。 And then when it returns。

 the PM that's in the main program is unchanged。 And that's because the entire structure。

 PM is duplicated into the stack frame for function funk operating a site function fun。

 we're only messing with the copy that's in our stack frame。 And then when we sort of undo that。

 it restores PM back to the way it was。 So those are just plain structures。

 but pointers to structures are where we get a lot more powerful。

 So here we have another same struct with a double x and a double Y。 And now we saystruct point P。

 which is a regular old variable。 and then star Pp， which is a pointer。



![](img/31bfcd4c175bf603475ce9fd0a836013_8.png)

![](img/31bfcd4c175bf603475ce9fd0a836013_9.png)

![](img/31bfcd4c175bf603475ce9fd0a836013_10.png)

To a structure， an address of a structure。And you can take the address of a structure just like you can take the address of an integer。

 a structure is a very fundamental type， so P equals ampersand P copies the address of the actual structure P into the variable P P do x equals 3。

0 or openP star P closed print dot y。Equals 4。0。 So if we have a pointer to a structure。

 we have to use the asterisk to sort of look up the actual structure。

 and then we can do structure things with it like set the dot y value。 There's a shortcut。

 Take an address， dereference it with the asterisk and then use the dot。

 They're combined into kind of what we call the arrow operator， which is P dash greater than Y。

 which is the same as openpren star P close pern dot X。 And so this we call it the arrow operator。

 And so it's kind of a shorthand。 and it's used all the time。

 and you'll see when we look later at things like PhP。 They adopted this arrow operator。

 Most other object oriented languages tend to use the dot operator。

 but others use the arrow operator。

![](img/31bfcd4c175bf603475ce9fd0a836013_12.png)

![](img/31bfcd4c175bf603475ce9fd0a836013_13.png)

![](img/31bfcd4c175bf603475ce9fd0a836013_14.png)

So if we're going to pass。A structure by reference。

 you use the ampersand in the call and the asterisk inside the function。

 so we create struck point Pm， set X and Y within that to 3 and 4 respectively。



![](img/31bfcd4c175bf603475ce9fd0a836013_16.png)

Then we print it out and then we call funk， but now we call it with Ampersand PMm。

 which saysPas in the address of PM。And then in the function。

 we take in PP and we declare its type isstruct point star P。

 which means we are getting as a parameter on address， not the value。

And then we use the arrow operator， PP arrow x equals 9， PParrow y equals 8。

We print that in the function， but because P just points to P。

 it's also changed in the copy that's in the main。 So P is being changed at the moment that P is being changed。

 And so when it comes back， you see that the value is 9 and8 outside of the function So this is simply passing by reference。

 almost we better call it pass by address。 So if you take a look at the stack frame。

 what you see is when we're calling funk openpre ampersand Pm closed print。

 we are making a copy of the address and putting that into the stack frame and then passing that stack frame into funk。

 and so now funk has an address of something， it happens to not be in its domain。

 meaning that PM is still in main， but we can work with the arrow operator and actually make changes in the underlying object。



![](img/31bfcd4c175bf603475ce9fd0a836013_18.png)

![](img/31bfcd4c175bf603475ce9fd0a836013_19.png)

And so the key there is that you could change P P， but P Parrow X。

 you're actually changing the single copy that is in PM at that point。 St allocation。 Now。

 pretty soon we're going to be dynamically allocating things。 We've always said that， oh。

 you create a char array of char with open bracket 10， There's 10 things in that。

 What if we want more。 And we've said you can't reallocate this stuff。 But now we have this thing。

 we're going to start allocating。 So it turns out when you're allocating things。

 you have to know how big they are。 Okay， and so there' is this size of operator。 So size of。

 so if we takestruct point P and star P P， which means we have a structure with two doubles in it。



![](img/31bfcd4c175bf603475ce9fd0a836013_21.png)

And then a pointer to a structure with two doubles of it。 And we simply say。

 what is the size of the structure， And it's 16 because each double is 8。

 And then what is the size of a pointer to a structure。And that is 8。

 because 8 is how big addresses are。 The fact that doubles and addresses happen to both be the same thing is not relevant here。

 addresseses are on most see systems，8 characters。You can also， because it's an operator。

 not just give it a variable， but also give it a type so we can say size of open printstruct point。

 close pern， and that also will be 16 because the size of a struct。

 if we were going to allocate it is 16 characters， so size of returns the size of something in characters。

And so we have this function called MalEC， and Malick， you have to include STDlib。 H to do it。

And so now what we're going to do is create up the structure point again。

 and we're going to create a pointer and we're going to not actually allocate it so thatstruct point star PP allocates an eight character address。

 not the actual double2 doubles。

![](img/31bfcd4c175bf603475ce9fd0a836013_23.png)

Now what we do is we say PP equals first and we're casting this。

 we're casting the returned address from MalEC。Prien struck point star preen， close print。

 That is casting it to a。Pointer to astruct， a pointer to a point。

And then we say Malik open print size of struck point， close print， close print。

 And so that says Malik 16 because a struck point is a 16 characters。

 So Malik goes and finds some free memory for us in its pool of free memory and gives us back an address。

 which we then convert to a pointer to a point。

![](img/31bfcd4c175bf603475ce9fd0a836013_25.png)

And then we store that in PP， and at that point we have data。

 we have a working structure and we can set the x and the y value just as the normal way。

 whether we use the arrow operator or the star and dot operators， we can access that information。



![](img/31bfcd4c175bf603475ce9fd0a836013_27.png)

The next thing we're going to talk about is combining all these things。

 dynamic memory and structures to create lists。And this is a simple Python program Line equals list hand equals open openP Romeo。

 Txt， then loop through and then append each line after stripping the new lines。

 and then printing them out so lines is a list object now underneath it there is a data structure which by the end of this course you're going to get to know really well。

 but this will print out the four lines from Romeo。 Txt and this is Kr0607。 py。



![](img/31bfcd4c175bf603475ce9fd0a836013_29.png)

Now we're going to build this list structure。And then we can store some data in it。

The entries of the list are going to be stored in dynamically allocated memory。

 and each list contains some data and then links to other members。

And so we're going to create a thing calledstruct L node。



![](img/31bfcd4c175bf603475ce9fd0a836013_31.png)

Open print char star text， which is a pointer to a list an array of characters of unknown length。

 struck L node star next semicolon cos curly Bra semilon。

 And so if you construct a real live link list you need also to have two variables。

 struck L node star head andstruct L node star tail。

 And if we end up with a linked list of three things。 head points to the first item in the list。

 And then within that there is the text， the text points to some string。 in this case。

 it's the letter C。 And then the next is an address of the second thing in the list in that second thing。

 text points to is and next points to the third thing in the list。

 And then next and the third thing in list points to a value called null。

 which is our indication that it's an address to nowhere。 null and0 are pretty much the same thing。

 all address are non-zero。 So we look for an address of0。

 and that tells us that we've got to the end。 And then in order to append to this list。



![](img/31bfcd4c175bf603475ce9fd0a836013_33.png)

![](img/31bfcd4c175bf603475ce9fd0a836013_34.png)

We have another value， which is a pointer called tail， which points to the last element in the list。

 When we start the list， head and tail， both point to null。 And so ultimately。

 what we have done is we've created a dynamically allocable structure。



![](img/31bfcd4c175bf603475ce9fd0a836013_36.png)

where we can put sort of any number of lines in it and so it's kind of like a Python list so the first line of this。

 the while statement reads a value into line， a string value into line。

 the next line from the file right and so we have a pointer to a character that we pre allocatelocated above this and that points to the variable font。

Three characters plus an end of string。And then the next thing we're going to do is allocate a new string that is the same length plus one。

 so we're going to allocate four characters using Malec。Stterlin line plus1。

 which is going to give us four。Then we're going to get that address back and we're going to cast that to a char star。

And then we are going to assign that to save。So that's the place we're going to save this new item。

The next thing we're going to do is allocate a brand new L node， a brand new node in our list。

And we're going to mallic size ofstruct L node， and then we're going to cast it to a struct L node star。

 and then we're going to assign that into a struct L node star variable named new。

 we saved our string and we've got a pointer to that save string and a pointer to a empty at this point L node。



![](img/31bfcd4c175bf603475ce9fd0a836013_38.png)

Then what we do is we connect with if tail is not equal to null， tail next equals new so we take the。



![](img/31bfcd4c175bf603475ce9fd0a836013_40.png)

Not the about to be second to last item， and we connect it to the last item。



![](img/31bfcd4c175bf603475ce9fd0a836013_42.png)

And then what we do is we take the text pointer inside of our newly allocated list node and point it at the saved copy of our string in dynamic memory。

And then we point the next to be null。 And then we simply advance tail so that next time we do this。

 tail is pointing to the new end of the string。Now we've got one more thing that we've got to do and that is if head is null。

We have to set head to new that's only going to happen on the very first one。



![](img/31bfcd4c175bf603475ce9fd0a836013_44.png)

And so at this point， our list has three entries。 It went from two entries to three entries。

 And so we can go back up and read the next line and this sequence of。Statements will figured out。

 So I would just say take your time on this。 one thing that we learn when we're working on linked data structures inside of C as you got to draw a picture。

 I I literally can't do this from memory。 I just draw the picture and then it's really easy to do。

 So sometimes you want to walk through a link list。



![](img/31bfcd4c175bf603475ce9fd0a836013_46.png)

So we tend to call this， we make a variable called cur current， which is astruct L node star。

 a pointer to an L node。And so this is the same as looping through a Python list。

 we set current to head because that's where we're going to start going through the list。

And then we print out current text which print C out。

And then we go to the bottom of the loop and then we advance current to current next。

It's kind of like adding plus one， but we just went from the first item in the list to the second item in the list。

And then we do it again。we are printing out the third item of the list。

 and then we current equals current next gets to null and so then the list is over and we have printed all of them out。



![](img/31bfcd4c175bf603475ce9fd0a836013_48.png)

🎼Yeah。

![](img/31bfcd4c175bf603475ce9fd0a836013_50.png)

🎼Yeah。
# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p30 29_PHP数组.zh_en -BV1Lr421A75d_p30-

![](img/41a2676f0b0cc45efa4271621e59e17c_0.png)

![](img/41a2676f0b0cc45efa4271621e59e17c_1.png)

So now let's talk about one of the most popular features of PhHP arrays。



![](img/41a2676f0b0cc45efa4271621e59e17c_3.png)

PP arrays are just plain。 awesome。 They are inspired by pearl。 They're called associative arrays。

 Pearl had associative arrays。 And what happens is。😊。



![](img/41a2676f0b0cc45efa4271621e59e17c_5.png)

Part of what。Programmers have to do is you have to write algorithms。

 which is code and steps that you write through。 and then the data。

 And so you solve problems with a combination of the logic that you use and the data that you create。

 Data structures are how you shape the data。And in a language like C。

 they had this thing called they hadstructs， which are shaped data items in C+ plus you have objects which are shaped data items。

 Java has an object which is a shaped data items and a data has a shape。

 Those are all really complex ways to lots of syntax to say， oh。

 this person has a first name and a last name and a phone number。

And arrays Associative arrays are key value pairs。 So you say you know。

 this person has a first name and a last name and a phone number and you're done。

 And so they are just a way for programmers without learning a bunch of extra syntax to create data structures where they hardly even know it。

 And so that's what Python dictionaries are very popular。 One of the most popular features in Python。

 Jo has things like hash maps。 Windows has things called property bags。

 They're all a version of an Associative array or a key value pair。

 PhP arrays are probably my absolute favorite when I move from PhP to Python。 I'm like dang it。

 I want these things to stay in order。 So PhP arrays are just my favorite associated arrays。 in PhP。

 they can either be like a list。 a linear list index by numbers。

 or they can be key value pairs like first name Chuck last name severance phone number bh。

 and they have two dimensionionalal arrays， but they really just arrays with an arrays of arrays。

 Basically we'll talk a little bit about that， but not too much。



![](img/41a2676f0b0cc45efa4271621e59e17c_7.png)

So you can make an array that is a linear list of things。 so here we're going to make an array。

 so this is sort of a constructor that says make me an array that has two things in it and。

Like most civilized languages， the first element is in sub0。

 so we use the sub operator or index operator。Or item operator， so we say give me the sub1。

 which is actually the second one， and so we print out there。

 so we make an array and then we reference an item within that array unless we tell it otherwise it just puts these things in it0 and one。

The thing that people really love though， is when you do key value， and so this is the syntax。

 let's make an array， and I read this as maps too。So this key of name maps to the value of Chuck。

 So this is the key and the value。 The key， of course， maps to web applications for everybody。

 And then you can use the index operator again to go look up the piece under the key course and out comes web applications for everybody。

 I love this。 I love it。 I love it。 Sorry， I'm like a fan of key value arrays because， like I said。

 it allows us to build data structures without thinking too much about it。 Although later。

 when do objects or anything like， see， you don't want to get so complex or your data structures is using arrays。

 but that's okay。

![](img/41a2676f0b0cc45efa4271621e59e17c_9.png)

![](img/41a2676f0b0cc45efa4271621e59e17c_10.png)

So there's a couple of ways to print these things out because we start building shapes。 So I mean。

 shapes of data and conventions。 You're the one that's a programmer。

 You decide to call it name or course or whatever。 But after a while， you make these shapes。

 And this is a super simple one。 So you want a way to print this stuff out。 print R。

 And I'm going to put a pret out so that the new lines don't get all messed up because that's how that's HTML for a pret。

 So that I see that actually the way it prints out。 So it doesn't do line wrapping on all this stuff。

 So print R goes through this array and print the key and the value key value key value and goes through it。

 you'll notice that the order is the same both when I put it in and when I take it out。

 That's one thing that I like The R and print R， I think， stands for recursive。

 which means you have an array within an array within an array。

 it'll kind of go through that and theyll in den even further and further and further。

 This is very simple。But you can print out much more complex structures and you do end up with very complex structures。

 Sometimes you have a linear array with integer keys inside of a key value array。



![](img/41a2676f0b0cc45efa4271621e59e17c_12.png)

Especially when you start talking with As and JSson and stuff like that。 So you want to print it R。

 Another thing that is even more verbose and detailed because it talks more about the type is a thing called var dumpump。

 Var dumpump I think of it as lower level。 It's less pretty。

 but it's more explicit And what this says is this dollar stuff is a two item array。

 and the first item is name maps to a five character string of the value of chuck course map is a first key that maps to a five character string S I 664。

 So it's just a little more verbose。 and I tend to use Vardump。

 when I'm really digging through something because printr makes it prettier。

 but sometimes you lose some detail。 The one thing I love about Var dumpump is that you can actually print false。

 You can actually print false because Var dumpump is printing that both the type and the value right。

 So here I have false is in thing。 I print out one。 I use print R and it's absolutely nothing。



![](img/41a2676f0b0cc45efa4271621e59e17c_14.png)

And this is like， ah。C。I'm so mad because I look at this and I say the code didn't run。But it did。

 This code did run。 So when you print false， it doesn't show up。 Have I told you that before， again。

 that's cause I am really usually angry after like 20 minutes。

I've wasted time because I keep printing stuff out， and I can't see it。

 But then I realize I should have watched my own lecture and use Var Dump because Vardump says it's a false and its's boolean。

There's a reason it does it this way。I'm sure， but it's not very convenient for debug printing。

Now you can construct and array a couple different ways。

You can start with an empty array and a pen stuff to the end。 So this is make me an array。

And then this is go to the end and add one an item， and then it just adds these in integer positions。

 so it's0 and one， so it's a linear list。You can do the same thing with key values。

 you just put the index operator on the left hand side of the assignment statement， make an array。

 stick Chuck under the key name， stick AWA for E under the course。Ororder。Smiy face。Stays in order。

Okay， looping。This is looping through a key value array。

 and so it's a looping this looping construct that has two iteration variables for each syntactically different。

 the array is the first parameter and then as as a keyword。

 and then you can have two iteration variables， one for the key and one for the value。

 and so I read this as for each stuff as key maps to value。That's what you put right there。

 It's not a less than or a greater than or equal。 It's a map to。 That's like。

 I think of that as an arrow， right， And I think that's exactly what the design of the language was。

 So this loop is going to run and。K is going to go through the keys。

 V is going to go through the value。 and then the next time through the loop。

 they're going to both simultaneously advance。 And so it's a really， I think this is really。

 really pretty syntax。I think that's really nice syntax。 and I like it。

 I like being able to loop through arrays。 If you have a linear array。

 you can get at the key and the value。 In this case， the key is 0 and one。

 because that's how this works。 This is the0 position。 That's the one position。

You can also on a linear array。 You got to be careful that it's a wellform linear array。

 You can use a counted loop right， So count is a function that tells you how many things there are。

 So in this case， that's going be two because there's two things in there。

 So I'm going to have an iteration variable for I equals 0 I less than count。

 So that means it's going to be 0 and 1。 sub2 wouldn't work because this is an array sub0 and array of one there。

 So then I'm going to add one。 So this is there's a counted loop that's going to run twice。

 It's a little uglier syntaxwise。 I for this particular thing。 I want to use the for each instead。

 but you can do counted loop。 Sometimes you actually need a counted loop because you need the variable I for some reason or another。

 And so then you just gonna dereference stuff sub I， which is the0 and the1。

 and then the loop prints all the stuff out。 So that's a counted loop that's going to iterate through an array。

Just talk briefly about two dimensional arrays。 They're not really two dimensional arrays。

 They are nested arrays。 They are reccursively nested arrays。

 So you can put an array within an array， right？ And so， so this is outer array。

 So this is the outer array。 And this outer array has。Three things。The first one， the second one。

 and the third one， and this paper maps to an array。See the comma。

 the comma is part of the outer array， so there are three things in the outer array。

So you can think of this as product subends。Products ofs。

Is going into this outer array and grabbing this thing。And then sub marker is within this array。

 grabbing sub marker and looking up markers。 So that pulls out。Markers。

So so it's not really two dimensionsionalal arrays。

 it's a within as and you won't build the structure often if you're going to get data from a database maybe or you're going to get data off the web or something。

 read some JSON and parsit or something， you'll get this。

 and then you'll just have to figure out how to dig into it， how to go in and dig it。



![](img/41a2676f0b0cc45efa4271621e59e17c_16.png)

Dig through this whole thing。 And so that's as within arrays that it's kind of like two dimensional arrays。

So up next， we're going to talk about how there is a set of functions that help us build arrays and search them and do various things。



![](img/41a2676f0b0cc45efa4271621e59e17c_18.png)

![](img/41a2676f0b0cc45efa4271621e59e17c_19.png)
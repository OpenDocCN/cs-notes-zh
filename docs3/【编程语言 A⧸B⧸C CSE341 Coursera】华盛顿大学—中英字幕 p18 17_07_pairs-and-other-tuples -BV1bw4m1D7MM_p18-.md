# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p18 17_07_pairs-and-other-tuples -BV1bw4m1D7MM_p18-

Okay， in this segment， we're going to start studying data and ML that's built out of smaller pieces of data。

 and we're going to start with pairs。So we've seen numbers。 we've seen Booleanions。

 Those are basic data values， and we've seen various ways to program with them like conditionals or variables or functions。

 but we need some way to build up things that have fields， multiple parts of them。

 This is essential in any programming language。 If you've programmed in a language like Java。

 you've probably programmed with arrays that contain multiple pieces or you've programmed with classes that have multiple fields。

 that sort of thing。 in Ml， we're going to take a very sort of fundamental approach to it。

 we're going to start with tuples which are a very direct way to have a fixed number of different data items。

 each of which can have different types， And then in later segments。

 we'll start programming with lists that can have any length at runtime。

 but all the pieces have to have the same type。 These are not the only forms of compound data we'll study。

 but they'll be enough for the first homework assignment， and they'll get us started。

So we'll start with pairs。 And the way I want you to think about pairs is that they're just things with two parts。

 And so in terms of new language constructs， we need a way to build pairs and we need a way to access the pieces of pairs。

 So here on this slide I have the pair building expression。

 And I have the answers to our three questions about them。 In terms of syntax。

 We're going to write two expressions。 We're going to separate them by a comma。

 put them in parentheses。 and that's the syntax for building a pair。What are the evaluation rules。

 Well what we're going to do is evaluate E1 to some value call it v1 E2 to a value call it V2。

 and then that pair of values will be a value。 So one new kind of value。

 something that's done evaluating is a pair that holds itself values。

We also have a new kind of type for these pairs。 so if E1 has some type。

 say T A and E2 has some type， say TB， then the pair expression will have T star TB。

 so it just has the two parts of the pair， the types of those parts separated by a star。

So that's how we build pair expressions。 Now， how do we access the pieces。

 Well I'll show you a different way in the future。 But for now， let's use these two constructs。

 hash1 of an expression and hash2 of an expression。

 The evaluation rules are that we're going to evaluate that expression E to some value。

 it's going to be a pair。 and then hash1 will return the first part of that pair。

 And then hash2 would return the second part of the pair。 So if x is say the pair of 4 and 17。

 And we said hash1 of x， we'd get back4。Type checking works similarly that E in there better have a pair type。

 so better be some T star TB， otherwise this access expression doesn't type check。

 and then hash1 of E would have type TA and hash2 of E would have type TB。

So those really are the rules， but like anything， you tend to really understand how they work by writing some programs and trying them out。

 So let's just write a few functions that take or return pairs。

 So how about I start with a swap function， maybe it takes one argument I'll call it PR for pair。

 maybe it has type instar bull。 so it takes something whose first part is an int and second part is a bull and maybe what I want to return is a new pair where I build the first piece out of hash2 of pair and the second piece out of hash1 of pair。



![](img/bde06e66f70da79275e99966610c5611_1.png)

Alright， so I'll show you in a second an example of how that works。 In the meantime。

 how about I just write some other functions here， How about I take write a function that takes two pairs。

 both of which have type instar int。And just adds up those four pieces that are in there。

 So what I want to return is hash one of pair1 plus hash2 of pair 1。

 I can grab these four pieces in any order I want hash one of pair 2 plus hash2 of pair 2。

 It's a perfectly reasonable function。 It takes as arguments， to int star int and returns an int。

 So the type of this whole thing would be int star int。Star into star int， and it returns an int。

 and let's put that in a comment。Allright。Let's do a couple more。

 Oh here's one that I really like because this is something that's just completely natural to do and a pain to do in many programming languages。

 Let's take in a numerator and a denominator， X and Y。

 So just two arguments of type in and let's return X divided by y and the remainder of X and Y。

 Now these operators have strange names in M， div and mod， but I can still write this。

 All I'm doing here is returning a pair。😊，Of two expressions。

 the result of x div y and the result of x mod y。 and so this function is going to take in two ints and star int。

 and it's going to return a pair of ints。 The readtaval print loop when we actually print this out won't write those parentheses。

 but it's just that simple。All， how about one more。

 how about we take in a pair of integers and we sort that pair。

 So we're going to return a pair of instar int。And if the first part of the pair is less than the second part of the pair。

Then we'll just return the pair we started with because it's already sorted。

 otherwise let's swap it around and return hash2 of pair， hash1 of pair。Allright。

 so that seems like a good set of example functions。 Let's real quickly go over here。

 make sure that I actually wrote those correctly， and they。Load up here。 Good。

 We see that swap is has type instar Bo， arrow Bo star int。 So how about I try that out。

 How about I try calling it with 7 and true。And I get true 7。 if I call it with。

 let's say-4 and false should get false and -4。 Now you might be thinking。

 how does Ml know that I'm calling it with a pair and not calling it with two arguments。 Well。

 in a future lecture， I will show you that Ml。 that's actually exactly the same thing。 But for now。

 we'll keep them as separate concepts。 And let me try one more here。

 How about sort pair of three comma 4。 I just get back the pair 3 comma 4 of type instar int。

 If instead I had maybe had a value that was four comma 3， and then I had said sort pair of X。

 it would come back three comma 4。 Of course， I could have just directly asked sort pair 4 comma 3。

 I would get the same answer， Of course。 Okay， so that's programming with pairs。

 let's go back to the slides here。 and show you that while that's really all there is to pairs。



![](img/bde06e66f70da79275e99966610c5611_3.png)

We can in fact， generalize this idea to tus。 So a pair is just a two tuple。 in general。

 you can have any number of pieces。 So to build a tuple with n pieces。

 you just have n expression separated by commas。 The type of that thing will be all the types of the expressions separated by stars。

 So something like int star int star int would be a triple where each piece was an int and you access the pieces with hash1 of E hash2 of E hash3 of E and so forth。

 So you'll get a lot of experience on this because intstar int star int is in fact common type for a lot of the problems on the first homework assignment。

I also want to emphasize that without adding anything new to our language。

 the rules I already showed you， you can nest tuples and other kinds of expressions as deep as you like。

 So I have a few examples here on the slide we could type these into the readdevelopval print loop or into an ML file as well。

 But for example， if you write seven comma and then in its own pair true comma 9 Well that's going to be a pair where the first part has type int and the second part is also a pair of type bo star int。

 So the overall type is int star parenthesis。Bol star end。Therefore。

 if you took that x1 and you applied the hash2 operation to it。

 hash2 of x1 is going to give back a bo star int。 so if we then did hash1 of that。

 so hash1 of hash2 of x1， that would give you back something of T bo and in fact x2 would evaluate to true。

Similarly， x3， which is just hash2 of x1， makes perfect sense。

 The result we look up x1 in our environment， we get 7 comma true comma 9。 we do hash2 of that。

 We're going to get true comma 9， and that's a perfectly reasonable value of type Bo star ant that we can then bind to x3。

And of course， these things can nest however deep you want。 So on this last line here。

 maybe it's hard to follow all the parentheses or whatever。

 but we just have a pair whose first part is a pair of ints and whose second part is two pairs of pairs of ints。

 sorry， it's a pair of a pair of ints， Hard to talk about easy to program with。

 and you can see the type written here。So that's tuples。



![](img/bde06e66f70da79275e99966610c5611_5.png)
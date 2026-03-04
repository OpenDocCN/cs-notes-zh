# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p125 27_02_datatype-programming-in-racket-with-structs -BV1bw4m1D7MM_p125-

In this segment， we're going to introduce thestruct construct in racket， show you how it works。

 use it to come up with a better implementation of our little arithmetic expression language。

 and then in the next segment will discuss why it's a better approach。



![](img/fddf8323d917c3a73853a1daaa62b74c_1.png)

So here's the new feature and how we're going to use it。

 you can have a special form that you writestruct。Then the name of your struct。

 then the names of the fields it's going to have。 So here I'm defining a fostruct that's going to have fields。

 bar， Bas and quacks。 We'll see how to use this in just a second It willll be obvious once I show you what functions are defined as a byproduct of creating this declaration and I'll explain at the end of the segment what this transparent attribute is and why I encourage using it。

So when you have thisstruct declaration， a bunch of functions are added to the environment once you evaluate thisstruct。

The first thing you get is you do get a function called fo that takes three arguments because this struct has three fields。

 evaluates those three arguments and returns some new thing。 It's a foo that has a bar field。

 a Ba field and a quax field holding the results of E1 and E2 and E3。 So in that sense。

 a struct is like a record because it has these fields named bar bas and quas。

 but it's more than that。Because we also get a function food question mark。

That evaluates any expression at all in racket and returns true if and only if the result is something that was made from the foo function。

 So this is how we can take something and find out if it's a foo or not。

And then we get three functions for evaluating the fields， foo bar， fo Bas and F quas。

 So what fo dash bar is is it's just a function， just the name of the struck dash。

 the name of the field。 evaluates something if that something that result was made with the foo function。

 the first thing I showed you， then you get the contents of the bar field。 Otherwise it's an error。

 if you call fo dash bar on something that is not a foo， it's a runtime error。

 Similarlyly fo dash Baaz returns the Bas field， fo dash quas returns the quax field。Okay。

 so it turns out these things can be used for idioms like our expression example。

 So what I'm going to show you in a minute when I show you the interpreter， the new Eval X function。

Is fourstruct definitions for cons negate add and multiply the cons needs one field， I'll call int。

 negate needs one field， which I'll call E for the subexpression。

 add needs two fields E1 and E to and multiply similarly for the subexpressions。

 So what we're doing with this collection of fourstruct definitions is a lot like our M data type binding becausestruct definitions are most like M constructors。

 not a data type binding， there is none of that we're in a dynamically typed language。

 but each of these is a lot like in M constructor definition。

 which an M was part of a data type definition。Because what you get when you define astruct is you get a constructor。

 a function for making the thing， you get a tester。

 a function for finding out if you have one of the things， and you get extractor functions。

 data accessing functions for getting the various fields。So Kt would be a constructor。

 Kants question mark， a tester， cons dashash int one of these extractor functions。

So it's not pattern matching。 This is a different approach。

 it's an approach I have to like a little bit less， but it works fine。 It's sufficient。

And because we're in a dynamically typed language， two things are not in this code that you see above first of all。

 we never say anywhere in the language these are all the kinds of expressions there are that's for us to keep track of and secondly we don't say what the types of the fields are there are ways to do that in racket but this more dynamically typed approach just says that any of the contents can hold anything will be up to us to make sure that multiply only holds expressions and constant its field only holds a number。



![](img/fddf8323d917c3a73853a1daaa62b74c_3.png)

So with that， let's look at the code， I have thestruct definitions right here that I showed you on the slide。

 and now we can just write our Eval X function。 It's the same logic as we've seen now in our previous implementation with lists and with N ML。

 and that is if you have a cont using that cont function that is part of thestruct definition。

 just return the entirestruct， the entire con thing。If you have a negate。

 then use the negate E function that was created because we have a struct name negate with a field E on this argument。

 the argument to eval X， so that's going to give back something when we call eval X with it。

 hopefully it will be a cont because when I call contt int that will get the underlying number if the thing was made from the cont constructor。

 otherwise it's an error。I'll negate it。And then I'll call the cons constructor to make a new thing。

Similarly with add， take in the argument to Eval X， if it is made from add。

 then we'll do this branch of the con。We will use the add dash E1 function to get it。

 We'll call eval X with it。 We'll convert it to an int。

 store that in V1 do similarly for the second expression。 So if you call add dot E2 on E。

 Add dash E2 is just a procedure that's built in。 and we get the second thing out。

 Now we have call constant to get the number out， let that be V2。 Add V1 and V2。

 put it back together by calling the constant constructor， multiply is the same as add。

 multiplying instead of adding。So what we have when we run this is we can really think of add as a procedure。

 add question mark as a procedure， add E1 is a procedure。

 so if you said something like define x to be add of cont of3 and cont of4。

That will print as this tree we've built， it's the result of the ad constructor with the cons with the three constructor cons of four。

 if I call eval X on that。I get back the Con7 because remember we return an expression now and this all works great。

 so it's a lot like our version with lists， much more convenient to just havestruct definitions without having to define everything。

 and it is actually different， as we'll emphasize in the next segment。

 the things made from these constructors are not lists， there's something different。

So this is the sort of approach we will take throughout the rest of this section。

 we'll usestruct definitions， and then in our Eval X functions。

 we will use all the functions that get automatically defined as soon as you have a struct。Okay。

 so let's just go back to the slides to finish up here。

I just want to mention this attribute because I didn't explain this hash colon transparent。

 This is not a big deal。 You could leave it off。 and everything I've told you aboutstructs is still true。

 But for us， if you don't have this attribute， the Reple will not printstruct contents very nicely。

 So why don't I show that to you very quickly in the Reple， you'll see here that if I run the file。

And say cont 17， that prince is cont 17。 And， you know， if I had said cons plus 3，4。

 that prince is cont 7， that makes sense。 If I had some other struck definition， fo。

 where I leave off the transparent attribute， Then if I say fo plus 3，4。

It just prints as it's some foo。 It's more abstract。 The repple doesn't want to show it to us。

 I assure you that the bar field of such a thing。 If I said， define y to be Fo plus 3，4。

 that even though。And I am missing parentheses here？That the Y just Princess foo。

 But if I said fo bar of Y， the contents are indeed 7。

 So that's what the transparent is attribute is about。

 does some other things for us that we won't get into here。 There's also， by the way。

 a mutable attribute。 So hash colon and mutable that you can put on astruct definition， if you do so。

 you get more functions for each field。 you now get a mutator function as well。 So for example。

 for astruct card that has a suit in a rank like we saw in an earlier homework in the course。

 This would define a function， set card suit bang that would take two arguments。

 a card and a value and would update the card suit field to be the new value。



![](img/fddf8323d917c3a73853a1daaa62b74c_5.png)

So whether you want mutation for your struct or not is a decision for you to make。

 we've discussed in this course， the advantages and disadvantages of having mutable data。

 there are a lot of disadvantages， but if mutable data is what you want。

 we use mutable data for things like promises， then the struct construct gives you that ability as probably will not surprise you in this course。

 all of the struct definitions we need in this section can be done better without mutation。

 and so we won't use this attribute， but it just shows you that these attributes affect in some way。

 how the struct primitive and racket behaves。
# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P122：-122-Association Lists_ Improving Tests, and TDD Chap8 Video 6.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Are we done testing yet， Let's look back at our test suite。

Thinking about this in terms of black box tests， we now have a test for zero bindings and one binding。

It might make sense to also have a test for two bindings， because that gives us three simple。

 small values for the length of the list that is passed in。Also， N CSS， as one of my colleagues。

 Professor White likes to joke， there are only three numbers，0，1 and many， we have a test for zero。

 we have a test for one， let's have a test for many。

I'm getting a syntax error here as I try to put a second test in。

This expression should have type unit。It's not immediately obvious， perhaps。

 but what's going on is that when Ocamel parsees this。

 it's really understanding this entire expression as being nested in the body of the upper let expression。

 So one way to solve that would be to put some parentheses in。

And then I would need to continue doing that for the rest of my test cases in this style。

Another possibility is to hoist the definition of those lists outside of where I'm doing it right now。

And now I have yet a little bit more compact of code that's hopefully a little easier to read。

Let's run that test case and see what happened。Oh， no， it failed。What's going on？Well。

 it's hard to tell because it just says not equal。I really should add a printer to these test cases to make it easy to see what the outputs are okay Ive grabbed two of the helper functions that were provided in the A2 release code to help us out with this one for pretty printing a list and the other for pretty printing a string Of course when I get here I need to figure out how to pretty print a pair。

 not just a string and not just an integer so I'm going to need to write another helper function to help with that。

There now I have a printer for association lists。Using it。

 I'll be able to figure out what's going on with the output of my test。😡。

Well it's clear I didn't get super great output from that because I'm not really seeing the bindings printed with the tus correctly there。

 let's go back and fix that。That's better。Now I see that I was expecting to get one list but another and the only difference between those two lists is the order that they are in。

 Now， if I think about what happened with my bindings function。

 I know what's going on When I called list dot sort unique。

 it changed the order of the bindings in the list while it was getting rid of duplicates。So。

One possibility here is to use the helper function that I remember being in A2。

 which can compare set like lists where order doesn't matter。

I've grabbed that function from the A2 releasease code compare set like lists。

It's going to check to make sure that the list don't contain duplicates and that they contain the same elements。

 though not necessarily in the same order。The latter is what I'm really interested in here。

 Is that issue with duplicates going to be a problem？Well， maybe， maybe not。

 I'll have to keep an eye on that going forward， but what I'm thinking is in my specification for bindings。

 it says there are no duplicate keys in the list。 so if I'm using that function along with Comp set like lists。

 I shouldn't run into trouble。Let's put that in as the comparator。

And now try running the test case again。Yea， it succeeded。

Hopefully this has given you a little bit deeper insight into the process of test driven development。

We keep writing tests and we keep improving the tests as we go and improving the code as we go。

 but we don't force ourselves to get everything 100% right off the bat。

 It's okay for exceptions to be raised。 It's okay for us to discover new things as we go along。

We write the test。 It fails。 We improve the code to pass the test。

 Then we get rid of any evil things in the code， like duplication or bad style。


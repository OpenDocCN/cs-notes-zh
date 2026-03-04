# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P86：-086-Black Box Testing Chap6 Video 16.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

With black box testing， tests are written based on the specification of a function。

There are a bunch of advantages to writing tests in this way。By looking only at the specification。

 not the implementation， the tester is not going to be biased about any assumptions they might make based on reading that implementation。

😡，Since it's unknown to them， they can't let themselves be influenced。

It also means that the tests that are created are going to be robust with respect to changes in the implementation。

 because those tests were not based on any knowledge of the implementation。

And the tests can be read and evaluated by any reviewers。

 any other people on the quality assurance team say。

 who just want to see whether those are good tests for that specification。

 They don't additionally have to look at the implementation because the tests weren't based on。

There are four main kinds of black box tests。Example inputs provided by a specification。

 we talked about how to document those earlier， those should always become black box tests。

The other three， and we're going to talk about each of these in more detail now， are typical inputs。

 boundary cases， and paths through a specification。Typical inputs are common。

 simple values of a type。If you're testing a function that takes in an int as input。

T a small integer somewhere in the range of say1 through 10。If you're testing characters。

 use simple alphabetical letters or digits。Strings。

 a typical value might be a string that has a length that is a small integer， so it's a short string。

 and whose characters are all themselves typical。An alpha list。Well， similar to strings， really。

 you could test a list that has a small number of elements。

 each of which is a typical value of its type。For records and tus， you get the idea here。

 each field or component should have a typical value。For variants。

 test any typical constructors if that makes sense for the variant that we're talking。

So all of these are common simple values of a type that you could test if you're doing black box testing of a specification of a function。

Boundary cases refer to values like you see here in this tweet which is one of my favorites a quality engineer walks into a bar。

 orders a beer， orders zero beers， orders 9999 beers， orders a lizard orders negative one beers。

 orders a dishes。This is what good boundary value testing looks like。

 Test things that look maybe a little ridiculous。Boundary cases are those inputs that are atypical or extremeal values of a type and values nearby as well。

 so sometimes these are called corner cases or edge cases as well。For an int。

 some good boundary cases would be zero and then some values next to it， one and negative one。

Min ends and Mac ends are also good boundary use。

![](img/87c133d2000b0f53a6feca89b6791098_1.png)

Now， right away， you'll notice。One's a small integer， too。

 So isn't this both a boundary case and a typical case， Yes。

 I'm not trying to say that these three different kinds of black box tests are orthogonal。

 They're not。

![](img/87c133d2000b0f53a6feca89b6791098_3.png)

These are just good ways of generating good black box tests。

 and you may end up with some that throw out of multiple categories， that's fine。

An atypical character might be the zero byte character or the character that's all ones。

 maybe the space character or the delete character that can really mess up some systems。A string。

 you could test the empty string， a string with a single character。

 or maybe an unreasonably long string。For testing alpha lists。

 some boundary values might be the empty list， the list with a single element。

Or a list with enough elements to trigger a stack overflow on non tail recursive functions。

 And by the way， that holds whether this is Ocal or an object oriented language。 Both of them。

 programmers can write functions that could stack overflow。For records and tus。

 you could look at combinations of atypical values and for variant。

 you could look at all of the constructors of it to see if there's one that would qualify as a boundary。

The third kind of black box test is a path through a specification。

This is maybe a little less familiar。What I mean by this can actually have a few different forms one of those forms is representative inputs for classes of outputs。

Here's a specification for a function is prime。Is prime N is true， if and only if n is prime。Now。

 there are all kinds of values you might think of to throw into this function to test。

But there's only two classes of output from this function。True and false。

So a representative input to trigger the output of true would be a prime number， like 13。

A representative input to trigger the output of false would be a non prime number， say 42。

So these are two good black box tests that you could use because they are both designed to produce a different class of output。

Some other examples here， the compare function that the list standard library takes that has three classes of output。

 so if you're testing a compare function， invent three different black box tests to test the path through that specification。

Any function that returns a value of a variant type is going to have several classes of output。

 so produce black box tests that trigger each of those possible constructors。

Another kind of path through a specification that we can test in a black box way is all the different ways of satisfying the precondition。

Now， of course， there might be many different inputs that satisfy a precondition。

Let's look at this specification。 It's for a square root function。

 It computes the square root of x to an accuracy of n significant digits。

The precondition here is that x is greater than or equal to 0。And n is greater than or equal to1。

Once more， a lot of different inputs we could pass to this。

But there are really four representative ways of satisfying the precondition。

And it has to do with the greater than or equal there。😡，Either x is equal to0 or is greater than it。

Either n is equal to1 or is greater than。So we could write four different test cases。

For each of those ways of satisfying the precondition。

That gives us a set of black box tests through that precondition and all the ways of satisfying。

Another way of testing paths through a specification has to do with exceptions。

You could create black box tests of representative inputs for each way of raising or not raising an exception。

Here's a specification for a function pause， This is the zero based position of the first element of a list that equals x。

 and it raises not found if x is not in the list。Once more。

 many different inputs you could imagine testing here。But。

For representative ways of raising or not raising that exception not found。

We could create just two black box tests。1 for when X is going to be found in the list and one for when it's not。

 Remember， by stating a raise's clause here。The specifier is making a promise about how this function is supposed to behave。

 it must raise an exception。s part of the post condition if x is not in the list。Finally。

 testing data abstractions leads to another way of inventing black box tests。

If you think about the operations in a data abstraction。

 there are some functions that produce the value of it。Think back to our set abstraction。

 empty produces a set value。Some other functions consume a value of the abstraction。 size and mem。

 for example， take in inputs that are sets， but they don't produce outputs that are sets。

And then there are some functions that do both。 They both produce and consume a value of the abstraction。

So the add function is an example of this， it takes in a set and gives us back a set。

If we were to add a remove function， that would do the same。

So when inventing black box tests for data abstraction。

 test all the possible interactions of producers and consumers。

 sort of take the Cartesian product of them together and create a black box test for each element in that product。

You could test， for example， that the size of the empty set is zero and that the size of inserting into empty is one。

😡，That tests the application of that consumer size to two different producers， empty and insert。



![](img/87c133d2000b0f53a6feca89b6791098_5.png)
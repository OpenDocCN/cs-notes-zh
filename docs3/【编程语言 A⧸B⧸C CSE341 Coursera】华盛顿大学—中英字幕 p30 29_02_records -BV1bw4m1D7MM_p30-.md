# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p30 29_02_records -BV1bw4m1D7MM_p30-

All right， let's talk about records。 These are a new kind of each of type。

 They're not particularly complicated， but then they'll let us have a really interesting conversation where we can start comparing and contrasting them with tus。

 which are the other way we know to build each of types。

 So I think it'll be easiest to just jump over to the readtaval print loop and start showing you records。

 So how about I just bind a variable X to a record。

 This is a new kind of expression we haven't seen before。 in the syntax is。

 we're going to put something in between curly braces。 We haven't used those before an Ml。

 And what we're going to do is we're gonna have field names which are not variables。

 but can be any sequences of letters we want。 So maybe I want a record to have a field bar and a field fo and a field baths。

 I need to separate these by commas and I need to have an expression to evaluate to create the contents for each field。

 So maybe for bar。 I want to evaluate this expression can be any expression。



![](img/4bf56ce616f411d773d1f7ff1877aa8d_1.png)

In the entire language， as usual， how about true and also true。

 which is a really dumb and fancy way of writing true。 Allright， And then maybe for fo。

 I want to have the expression 3 comma 4 and for Bas， I want to have false comm 9。

 And this should be a perfectly legal expression that we will evaluate and bind the result to X。

 And sure enough， the readdevelopval print loop comes back and says。

 you now have a record value bound to X。Where bar holds three comma true。

 Bas holds false comma 9 and fool equals 7。 So we see two things here。

 One is it evaluated each of our expressions to a value。 And then that was the result。

 Sam thing happened when we did tus。 when we built a tuple。 we evaluated all the pieces。

 and that was the result。 The second is the Ritaval print loop seems to have reordered our fields。

 What it actually did was alphabetized them。 The order of fields and records doesn't matter。

 And so the repel chooses to present them in a uniform or canonical order。

 and it just chooses alphabetization。 It doesn't matter。 All right， And then as always。

 we have the type and records have a different type than anything we've seen in the language before。

 So this is a new kind of type， a new compound type。 And these types are written with curly braces。

 The field names。 a colon instead of equals。 because that's Ml's way。

 And then the type of each field。 and those are separated by commas。 So indeed。

 we see we just built a record where bars is type in star bo。

Baz has type bull star ant and F as type in。 We could nest records。

 We could pass records to functions。 We can do all the normal things。

 Perhaps the only thing that seems strange if you try to compare them to Java classes or Cstructs or Python classes is that we didn't have to declare our record type the same way we could just anywhere write an instar bull without having to say anything ahead of time。

 we can write this record， which has a bar field， a Ba field in a fo field of particular types。

 and the type checker using type inference just figures out the type of the record we have。

 And we can say what is the type of X。 It says it has the type that it had back when we created it。

 So let me show you a couple other examples of records just to make sure we have the hang of it。

 Here's one that kind of represents my niece。 She has a name。 that name is Amelia。

 and she has a birthday。 She doesn't actually have an Id。

 which maybe is the result of this calculation。And sure enough， I get a record where the ID is 4，1，1。

11 and the name is Amelia and that has type Id colon int and name colon string。 And again。

 you can just create any record with any field names you want And the way I haven't shown you how to get the pieces yet back。

 you do that with hash Id and then something like my niece So the same way we had hash1 and hash2 for tus for now we have hash field name to get the corresponding piece of a record and there's no rule that you have to use different field names for different things。

 So here is something that also has a field name that as far as Ml is the same can be concerned is the same as one of the field names in Amelia and my niece。

 but this usually pronounced id， but it's the same as I。 It's spelled the same way。

 And sure enough this creates a perfectly good record holding three bos two of which are false one of which are true in the field names are ego I and super ego so that's your。



![](img/4bf56ce616f411d773d1f7ff1877aa8d_3.png)

Little demo of records。 Now， let's talk about them from a more interesting perspective。

Take a step back to come up with the rules for how you create them and use them。

 So we have a new kind of value in our language。 These are record values。

 These are things where you have field names and each thing is a value。

 That's the result of evaluating something that builds a record The types are these record types where you have the names of the fields and the type that each field has。

As I've emphasized in the examples we went through。

 the order of fields in a record or value or record type never matters。

 so the repple prints them out alphabetically， but something with a fo holding2 and a bar holding for is exactly the same as a bar holding for and a Fo holding2 because we access the pieces by name with the hash my field name。

 the order of the fields is not part of a record definition。Okay。So we've seen this example。

 and I emphasize as we went through it that we didn't have to declare any record types that we just create a record with expressions that have certain types。

 and then we have a record of the corresponding type。

The thing I want to emphasize is that these are a lot like tus so we now have two ways to do each of types。

 if we wanted something that had in it a4 a 7 and a9。

 we could write the triple4 comma 7 comma 9 or we could write a record using three different field names maybe F equals4 G equals7 H equals9 So which should we prefer which is better and you know like all things in language design and software design it depends so the tuple version is certainly a little bit shorter fewer characters to type but the records are a little easier to remember which part is which I don't have to remember that oh my niece's name came first and then her birthday came second I had a useful field names to remind me of that using a name and ID so generally the choice here is a bit of a matter of taste the one thing I would emphasize is if you have a lot of fields like say8 or 10 or 12 or6。

 usually a record is a better choice I know I can't keep track of。Wait， which thing came fifth。

 is that hash5， or am I supposed to use hash7？Okay。

But even more generally what I find fascinating about tuples and records。

 this is just one example of a standard choice when you're designing a language construct。

 which is if you have multiple things do you want to indicate which is which by position。

 the second place， the fourth place， the fifth place， or by some sort of name， the F field。

 the bar field， the name field and each construct that has multiple things。

 you can kind of see which way it's doing it and to point out a common kind of hybrid where it's a little bit of each。

 look at function arguments as we've been using them in ML or even Java method arguments and similar in Python for the call to a method or function。

 it's always by position， the first argument， the second argument。

 the third argument that's how you write down the method call function call， but then in the callee。

 we don't access them by position， we access them by name using the variables or formal parameters we use when defining。

The function or the method。 So it's kind of a strange hybrid。

 And there are other programming languages out there where the caller specifies the arguments sort of by name。

 I want the full argument to be 7 and the bar argument to be 9。 And there are probably languages。

 although I can't think of any off the top of my head。

 where the collea accesses argument by position。 The second argument， the fourth argument。

 the fifth argument。 So whenever learning a concept， we now another design choice to think about。

 which is how you access the pieces， by name or by position。

 There isn't a huge difference between those。 And that's why in the next segment。

 I'll actually show you that twos and records are even more similar than they appear。



![](img/4bf56ce616f411d773d1f7ff1877aa8d_5.png)
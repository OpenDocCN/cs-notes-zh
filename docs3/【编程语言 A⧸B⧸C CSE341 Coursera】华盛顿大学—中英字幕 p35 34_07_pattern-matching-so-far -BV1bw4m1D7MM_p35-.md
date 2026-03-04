# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p35 34_07_pattern-matching-so-far -BV1bw4m1D7MM_p35-

![](img/9951672ea3aed06a0e91d5211214e2df_0.png)

One of the things I've been emphasizing is that when you learn a new language construct。

 you should understand precisely its syntax， its type checking rules and its evaluation rules。

 and since data type bindings and case expressions are the most sophisticated language constructs we've learned in ML so far I thought it would be worth a short segment to just review what we've already seen and know from a precise standpoint for each of those constructs Now what we'll do a little later in this section。

 not in this segment is expand the notion of pattern matching to make it more general and more powerful。

 but nothing I'm about to review with you will become untrue。

 we'll just get some additional things that will also be true。



![](img/9951672ea3aed06a0e91d5211214e2df_2.png)

Okay， so let's start with data type binding。 We know the syntax。

 We have an example here of data type T equals a bunch of constructors that types those things carry and they're separated by pipes。

 This introduces a new type T that was not in our program before。

It also adds constructors and these constructors in part serve as functions where constructor 1 has type T1arrowOT and constructor 2 has type T2arrowOT。

And then in terms of using these constructors， when you have a constructor applied to a value that is itself a value。

 in other words， values of type T both have the tag that corresponds to the constructor as well as the value that's sort of underneath that tag。

Now that doesn't cover the case where you have a constructor that doesn't carry any data。

 in that case you just leave off the of and the type。

 and in that case the constructor is not a function， it's just already a value that has type T。

Alright， so now we know how to make expressions of type T to access them to use their pieces。

 we use case expressions and as I've emphasized these case expressions。

 both test which variant some value of the data type type of type T you have。

 as well as give you a way to extract out the underlying data。



![](img/9951672ea3aed06a0e91d5211214e2df_4.png)

So let's go over a case expression again。 The syntax is here at the top of the slide。

 We see that we put any expression we want between the case and the of。

 And then we have a bunch of branches。 Each one， which is a pattern and then an arrow and then another expression。

 Now， this entire case expression is itself just an expression。

 So we can use it anywhere we can use an expression。

 I admit that it's common for a case expression to be the entire body of a function。

 and I think it has been in the examples I've shown you so far。 but that's not necessary。

 A case expression can appear anywhere。 And here is its evaluation rules。 You evaluate E to a value。

 All right， That thing between the case and the of。 that's going to give you some value V。

Now what we're going to do is we're going to match。

 we're going to pattern match V against each of the patterns in order until we find one that matches。

 so we'll check P1 if that matches we'll evaluate E1 and that would be the answer to the whole thing。

 otherwise we try P2 and so on。 so we're only going to evaluate one of E1 through EN and which one will depend on the pattern that we find that matches。

So what that means is we have to define what it means for a pattern to match。And so far。

 our patterns look like constructor name， and then one variable for each part of the thing under the constructor。

 And so that would match a value that was made out of the same constructor。

And then what you do when you evaluate the corresponding expression， like if P2 matches。

 you evaluate E2 is you evaluate E2 in an environment that is extended so that those variables map to the corresponding pieces。

 x1 to v1， x2 to V2 and so on， and that's how we get the underlying pieces out using the notion of variables and extending our dynamic environment。

Once again， the case where the constructor carries no data is a little bit different。

 you don't have the parentheses， you don't have the variables because there is no underlying data。

 so in that case if it matches， then there' is nothing new to add to your environment。

 but you still go to the corresponding branch， execute， evaluate that expression。

 and that's the result for the entire case expression。So that's our precise definition so far。

 we're going to learn a couple other things that will help us that are related to pattern matching and data types。

 although they're a little bit different， see another example and then make pattern matching more powerful。



![](img/9951672ea3aed06a0e91d5211214e2df_6.png)
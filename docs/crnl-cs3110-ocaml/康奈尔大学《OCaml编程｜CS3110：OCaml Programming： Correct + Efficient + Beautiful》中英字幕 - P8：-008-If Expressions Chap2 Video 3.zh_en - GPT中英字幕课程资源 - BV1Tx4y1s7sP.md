# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P8：-008-If Expressions Chap2 Video 3.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

If expressions conditionally allow one expression versus another to be evaluated by Ocal。

We can write an if expression with the key words if then else。

 so this will be familiar from many other languages。For example。

 we could say if Batman is greater than Superman。Then， we could say。Yay， else， boo。

 So what's this going to evaluate to， Well， maybe you have some personal opinions of your own about that。

 But O Camel says this is going to evaluate to boo。

And the reason for that is that strings in Ocael are ordered lexiographically。

 just a fancy way of basically saying dictionary order。Okay， so Batman is not greater than Superman。

 this evaluated tab boo， in fact， Batman would be less than Superman in dictionary order。Okay。

 so we have a couple interesting things going on here。

 We've got a part of the if expression that's called the guard that occurs between the if and the Zen keywords。

That's got to be a bo， a boolean。It evaluates to either true or false。If the guard evaluates to true。

 the then branch is evaluated， but not the else branch。The guard evaluates to false。

 and we skip the then branch and evaluate the else branch。And notice that those two branches。

 in this case， were both strings。Okay， so all of the things I said about types are actually very relevant here。

 we would not be able to compare， you know， just stick in maybe an integer here if zero then yay L boo。

 some languages let you do that O Cambell's going to be strict though about type checking here and it's going to require that guard to have type bo you can't treat an int as a bo。

Another。Requirement here in terms of fairly strict type checking is that both the then and the else branches have to have expressions that are the same type。

 so I couldn't say if true then yea else1 because yaea and one have different types and so I get an error message this expression has type in but an expression was expected of type string the string expectation was set up just because okay we'll happen to look at the then branch first there and so it thought。

 hey， I'm going to get a string in both branches。Okay， you could also， if you wanted。

Try to leave out the El branch， but you're going to get a rather confusing error message at this point。

This expression has type string， but an expression was expected of type unit because it is in the result of a conditional with no else branch。

For now， for the most part， I just want you to avoid ever leaving out the El branch。

We will see later on why it can be useful and， in fact， might be a desirable thing to do Right now。

 we don't desire to do it。You'll see here that if expressions are a lot like the Ternary operator that can be found in many languages。

The turnernary operator， usually written with a question mark and a colon， you'll find in， say。

 Java languages in the sea family and so forth。And that turnernary operator is usually used to evaluate a guard and then continue by evaluating one of two expressions。

 That's what the Ocal， if expression is doing with the syntax， if。Then。Else。

Now that we've taken a look at if expressions at a more intuitive level， let's go back。

And pick apart their syntax and semantics a little more carefully。The syntax of an if expression。

 as we've learned， is if then else。And it has three sub expressions as part of it。I've written as E1。

 E2 and E3， the E to indicate that they are expressions themselves and the1。

2 and 3 just to help us disambiguate as we read it。Next。

 let's state the evaluation rules or the dynamic semantics。

The definition of how to evaluate an if expression in Ocal is。If E1 evaluates the true。

And if E2 evaluates to evaluate V。Then the entire if expression， if E1， then E2， L， E3。

 evaluates to V。But that's not all that there is to the evaluation rules， actually。

 there are two evaluation rules for the if expression。The second rule is the complement of the first。

 If E1 evaluates to false。And if E3 evaluates to V， then if E1， then E2， L3， the whole if expression。

Evaluates to the。So it takes two evaluation rules to express the meaning of if expressions。

As for type checking of expressions。If E1 has tight bo。And E2 has type T。And E3 has that same type T。

Then the entire if expression has type T。It will get a bit verbose if we have to keep writing out these evaluation rules and type checking rules in the way that we are doing right now。

It would service well to introduce a little notation to shorten them。

Just a little bit of mathematical notation。For Es2， we're going to write a double right arrow。😡。

And pronounce it as evaluates to。 and for type checking， instead of has type。

 we're going to write colon。And still pronounce it has type。



![](img/94c13c67fb90c1f231ba8619f75fa976_1.png)

With those two pieces of notation， I can simplify the rules that I've written here。

Still mean the same thing， just a little bit quicker to write them and hopefully to read them once you get used to the notation。

If you're finding a little bit difficult to parse that notation。

 let me put some parentheses in here for you。 So I'll flip back and forth。

 Here is it without parentheses。 Here it is with parentheses。

When I'm writing that evaluation or type checking relation there。

 I'm really sort of letting it extend as far to the left as possible。

 So it's the entire if expression evaluates to the。 The entire if expression has type T。



![](img/94c13c67fb90c1f231ba8619f75fa976_3.png)

![](img/94c13c67fb90c1f231ba8619f75fa976_4.png)
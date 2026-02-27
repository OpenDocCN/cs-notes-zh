# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p57 -58-COMP6080 - Javascript NodeJS 🐸 Linting.zh_en -BV17RXGYuEaM_p57-

Hi there。Welcome to a lecture on LinkIn in JavaScript。Today， we'll discuss Linting generally。

 how it applies to JavaScript and go through some examples。Let's get started。So what is linting？

Putting it simply， Ling is a method for finding errors in your code。

It's a variant of something we call static code analysis。

 which means that it takes the code you write as an input and analyzes it in place。

 it doesn't attempt to compile your code or run it。

 it just looks at the text of your code to find common mistakes。

Lining is useful because it allows you to avoid common mistakes or deviations from best practice。

 It's often used as a guardrail to protect you from the sort of small mistakes that might often slip your mind。

It can do this effectively because it's fast， Liters run very quickly and can be integrated into your editor so that errors are reported as soon as they're made。

The combination of detecting common mistakes and being fast means that Lnting is a big productivity booster Lntters hold your hand effectively while you code。

 letting you focus more on functionality and less on the quirks of whatever programming language you happen to be writing in。

That said， Lnting is not a substitute for a good testing framework。

 it can only pick up on errors related to the language。

 it can't tell what you're trying to achieve and it can't detect runtime errors。

Lining isn't a way to enforce good system design or architecture。

 and it's not a magic bullet that makes your code work。On its own。

 it can't even detect errors where you're providing incorrect types， for example。

 a number instead of a string to a function。It's also not the only method of statically analyzingnaly code。

 although it is the most common。Before we move on though， let's dig into some JavaScript history。

Javascript has a bit of a reputation as being a rough language with some odd behaviours that makes sense when you consider its history。

 the first version of JavaScript was written in about 10 days by Brednda Iyck who initially wanted to take it in a completely different direction and over the years JavaScript has accumulated a lot of features and quirks that people probably shouldn't touch and early JavaScript code was often buggy and hard to maintain as a result。

So for many years we languished in a time where JavaScript just sort of sucked。

 but it was our only option， then in 2008 JavaScript the Good Part was released。

Javascriptri the good parts detailed the parts of JavaScript that we should be using。

 and the parts we should probably hide under the rug and forget about。

While you may encounter some disagreement on the street。

 it's fair to say that a lot of modern idiomatic JavaScript code is built on the foundations of this book。

So why is this relevant to Ling Well， six years before the release of this book， the author。

 Douglas Crckford， released JS。 Lnt， the first JavaScript Li。

You'll find in JavaScript that Lnting is used a lot。

 you'll generally find this to be the case in languages like JavaScript， Python。

 Ruby and others where the languages are dynamic and lac type systems and the reason for this is really that there's no compiler and there's no type system。

 the language isn't very strict about what you can and can't write and tries to get out of your way but that means you have a lot of room to shoot yourself in the foot。

It's especially common in JavaScript because the language has a lot of bad parts Linting helps us ensure we only use the good parts。

And while JS L was the first Lter to be released in 2002。

 E Linn is now the JavaScript industry standard for Ling。So how does Linting work。

Lining takes your code as an input。 It's configured to have a set of rules。

 if an area of code breaks these rules， the Ler will detect this and report these occurrences。

Lining rules generally fall into two categories。 you have possible errors and simple best practices。

 style and so on。They can be configured with parameters and can be set to either warn you or report it as an error。

When you run a L， you can either run it as a command or you can set it to watch changes in your code。

 This means that when a change is made on the file system。

 it will automatically l and report the results to you。Sounds simple enough， if a little vague。

 So how does linting actually work firstly。The L has provided the code as a raw string。

 It passes the string and generates a tree like structure， which we call an abstract syntax tree。

 This represents the program' structure。It's like a binary search tree， but with more than two nodes。

Each node in the tree represents a block of code， the node also contains information about the line and column number。

 where the code starts and ends。Now the Linting configuration has a list of rules called a rule set。

 each rule is a function that takes in the AST， the tree like structure。

 and inspects it for patent that break the rule。If it finds any。

 it reports them plus where they started and ended。Fair enough， but how does it really work。

 This is an architectural diagram of EL， which is the most common JavaScript Lnting tool in here。

 you can see modules like a L， a source code， rules， a CI engine and so on。

So the CLI module is our user interface， it reads our user input to decide what to do。

We have a rules module and that defines our rules set。

Our source code module is the module responsible for passing the code and generating the syntax tree。

And the L takes in the source code module and the rules module。

 executing the rules against the tree and reporting any errors that it finds。

There are a whole host of rules available in ESLN， but let's take a look at some small examples。

The no unreachable rule stops you from writing code that can't be reached， for example。

 if you have code that appears after a return statement， it will flag it as a warning or an error。

No unused variable stops you from defining a variable and then not using it anywhere。

And no use before defined stops you from referencing a variable before it's been defined in the code。

The last three rules were about detecting possible errors。

 The next three is more about best practices。The indent rule enforces consistent indentation in your code The Novar rule stops you from using the Var keyword。

 enforcing the use of let and const， which were introduced with ES6。

No console stops you from using methods on console。

So how do we get started with LntingLuckiily you already have create reactact outcomes bundled with a preconfigured installation of E Lent。



![](img/c384a8ba6397267daf91913ef3348eb6_1.png)

So， let's take a look。Okay， you can see here that I've got a react application on the left hand side is my file at。

js and on the right hand side is a file called ELrc。json。This is the configuration file for the L。

 and it sits the root level of your project。You can see here that I'm extending reactactor。

React up is a leenting configuration that comes bundled with Cate Reactup。On the left hand side。

 I've commented E S Lient Disable， which disables the Liter。I'll remove it now。And suddenly。

 a bunch of errors are reported。The first error is a warning that the function is defined。

 but never used。 We also have some errors saying that some of our variable references are not defined。

Additionally， we also have a return statement that doesn't reference the right variable and some unreachable code that occurs after it。

First things first。Let's。Reference our function by storing it in a result in our app and rendering it。

This should remove the error on our function， and you can see that on line 5， it's gone。

It's important to note that the Li can pick up errors， but some errors it won't notice。For example。

 I haven't referenced the correct variables here， and the Li won't be able to know which variable I was trying to reference。

 so it's up to me to fix this manually。I can fix the unreachable code error。

 but I just simply moving the force statement before I return。

And you can see here that number multiplier is defined after its reference。

 so all they need to do is move it upwards。Great， so we've fixed ournyting errors。

 but our function still looks a little janky， and there's still a few problems with it。😊。

What I can do。Is I can extend on our lendingnting configuration by adding my own rules。

The indentation here is a little weird， so first things first I'll add an indent rule。

The In rule says that report Indent as an error and look for an andentnotation of two。

 and you can see when I autoave it automatically fixes the indentation for me now that I've added that rule。

I can also see some usage of Var when I'd rather there be let or cons。

 so I'll add an error configuration to our rules and when I order saveve。

 you can see that my VAar reference at the top has been defined to let。

This is looking a little better， but some of my variables are using underscores instead of Caml case。

 which isn't best style。So I'll add a camel case error to my rule set。

Sometimes a Li won't report the error until I've reloaded the file， so I'll reload it now。

There we go。You can see here。That all of its instances in which I'm referencing or defining a variable that uses an underscore have never been reported as errors unfortunately。

 the L can't fix this for us because it doesn't know what the variable name should be。

So I need to go in and fix this manually。Okay， so the naming is looking a little better。

 but there is actually a possible error in this function to do with the for loop。😊。

The fall loopbe continues in the wrong direction。But luckily。

 there's a lintching rule that can protect me against thisarrow。By setting the four direction rule。

a reporter's error and then reloading， you can see that my full loop now reports that the update clause in the loop moves the variable in the wrong direction。

Simply changing this to an increment fixes that。In production applications as well。

 it's not really kosher to use the console statement， so I'm going to remove it。😊。

I can enforce the removal by adding a no console rule to mylining configuration。

I'll need to reload the file again。And you can see here now。

That there's some errors to do with unexpected console statement。

 so I'll just remove anything that uses the console。And now I have a nice function。

So you can see here that by adding a few rules to our Lta we were able to enforce best practices。

 good style and guard against possible errors This was an arbitrary example。

 but the difference that this makes in a large codeb cannot be overstated。As a final note。

 the reason that we need to reload the file is because the L is integrated into our editor in this case。

If we change the Lnting configuration， the editor won't necessarily know until we have to reload the file which loads the Liter again。



![](img/c384a8ba6397267daf91913ef3348eb6_3.png)

Great work In this lecture， you've learned how Lis work generally。

 how they can be applied to JavaScript， and you've seen a demo of how ESL integrates into your editor to provide you a better coding experience until next time。

 all the best。

![](img/c384a8ba6397267daf91913ef3348eb6_5.png)
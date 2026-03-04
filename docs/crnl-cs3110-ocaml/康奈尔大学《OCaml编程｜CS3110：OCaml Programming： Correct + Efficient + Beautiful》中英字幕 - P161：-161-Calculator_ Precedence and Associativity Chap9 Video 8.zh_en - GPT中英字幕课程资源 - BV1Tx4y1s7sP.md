# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P161：-161-Calculator_ Precedence and Associativity Chap9 Video 8.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

For my next test case， I'd like to have two multiplication operators in the same expression。

 So here I have two times 2 times 10。 Right now， that passes just fine。 It automatically worked。 Yea。

 that's fantastic。 What about。😊，Having a multiplication mixed together with an addition to plus 2 times 10。

 That works just fine， too， fantastic。😊，What about having two times  two plus 10？得有。That failed。

What's going on here？So I've got two times 2 plus 10， and I think that should evaluate to 14。Well。

 I didn't get a good result here， it just got not equal because I didn't have a printer。

So I could add a printer in here or I'm going to cheat a little bit right now and I'm just going to do this in you talk to see what happens What happens if I try to interpret two times 2 plus 10。

I got 24。 Why in the world would I get 24？Well， if you think about it， you might begin to suspect。

That my interpreter doesn't yet know order of evaluation。

Because if it looked at that as2 times 2 plus 10， well， that would be 2 times 12， which is 24。

That's exactly what's going on as it turns out。Now， I had been skipping over it thus far。

 but if we clean this up。And then， make build。You're going to see an error here。

When OAml goes to try to create the parser for this。

 it's detecting something that it calls a conflict。

I'm not going to talk right now about what these conflicts are。

 but this is actually what's going on is it's warning me it doesn't know what to do in order to resolve the conflict between parsing the plus first versus parsing the times first。

 which is to say order of evaluation， so to fix this I need to go back to my parser。😡。

And put in it some additional information about the precedence of operations。

You learned in elementary school math that times has higher precedentnce than plus you're going to do the multiplication operator before you do the addition operator。

So I need to tell the parser that as well。😡，So I do this year with some declarations for not just the precedentnce of operations。

 but also their issociivity， I have to do both at the same time。

We could put in some declarations to say that an operator is left or right or even non associative。

 so I'll say here that plus is left associative， and I could also say that times is left associative as well。

The associivity is not really what I'm interested in here though。

 it's the order I put these declarations in， because the order that you put them in establishes their precedentnce。



![](img/3dd09455bc6a4d9fb79a27b14a4e9ac1_1.png)

The lower in the list here of sosociivities， the higher the precedence of the operator。

 That's just how it works。 So times， because I put it below plus has higher precedence than plus。Now。

 I can go back。Make build。 I don't get any warnings about conflicts any more。

 The parser knows how to parse the relative precedentnce of them now， and I can run make test。

 and my test case passes。 It's now correctly interpreting 2 times 2 plus 10 to be 14 instead of 24。😡。

We could go back now and look at that associativity。When I parse  one plus2 plus 3。

 you'll notice the tree that gets created groups the one and two together。

 so this is causing associativity to the left。If I went back and played with those precedents and associivity declarations。

 I could force different results。For example， suppose I made plus right Associative。

Then two and three would get grouped together instead of one and 2。Likewise。

 I could reverse the precedence of plus and times from what everyone knows they should be。



![](img/3dd09455bc6a4d9fb79a27b14a4e9ac1_3.png)

Now， when I interpret 2 plus 2 times 10， my interpreter groups together the  two plus 2 to create 4 and multiplies that by 10 to create 40。

Of course， that's not how we expect these arithmetic operations to work。

 so I should fix that and switch it back。

![](img/3dd09455bc6a4d9fb79a27b14a4e9ac1_5.png)
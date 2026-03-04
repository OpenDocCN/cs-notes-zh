# CppCon【中英⚡CppCon 2024】 p15 P16 Back to Basics： Rvalues and Move Semantics in C++ - Amir Kirsh - CppCon 2024 -BV1NHEEzdE92_p15-

Something really valuable about actually attending and being here in person is having the opportunity to。



![](img/bff0efffefa4dfb53a3aaadf9657dcb8_1.png)

🎼Actually， we ask the speakers while they're there， go up to the microphone。

 ask a question that you have or meet them after the talk。

 chat them out in the hall there's just a lot of。Opportunities if， you know。

 something isn' it really clear to you to kind of just get in there and get a much clearer answer if you need。



![](img/bff0efffefa4dfb53a3aaadf9657dcb8_3.png)

![](img/bff0efffefa4dfb53a3aaadf9657dcb8_4.png)

Hello， everybody， and thank you for joining me for our values and move semantics。



![](img/bff0efffefa4dfb53a3aaadf9657dcb8_6.png)

This talk is part of the back to basic track， even though I believe that it serves for， I would say。

 any level of。

![](img/bff0efffefa4dfb53a3aaadf9657dcb8_8.png)

C plus plus programmes。 It's， it's an important topic， and it's good that you are here。

A few words about myself。 I'm a lecturer at the Academic College of Teleia and Televiv University。

 a member of the Israeli Iso C plus plus National body。

 organizer of the Co C plus plus conference and meetup group and a train and advisor for C plus plus。

 but not only。Let's start with motivation for move semantics。 Mo semantics was added。In C plus 11。

 it was a very important addition。 And let's understand the reasons why it is there。

So let's take the example of a Godzilla， Usually I'm using a Godzilla as an example of a big object that is。

Expensive to copy。 Okay， so let's assume that we have a factory that can create goodzals from the code here。

We can assume that the factory is creating a local Godzilla internally。

 and then returning that by value。 And then when we get the Godzilla created by the factory back to G1。

Most probably， it might be that it would be copied using the copyconor。

 while it might be that we would。 maybe we can do it a bit more efficiently。

How can we make it a bit more efficiently， Well， the gutilla that was created inside the factory。

 the local one is going to meet the distractor very quickly at the end of the statement。

 it's a temporary object， it was created inside the function。 So instead of copying it。😊。

Maybe we could take its assets and tell it not to distract what it created。

 It would be more efficient。 But， but can we do that， Let's continue with G 2。

 G 2 is created with the empty constructor。 Then we use the assignment operator。 And here， again。

 the factory is creating a spooky Godzilla。 Again， a local one。😊，Returning it by value。

 And then again， we use the assignment。 And before C clusterus 11， we just copy。

Can we do it more efficiently， Well， maybe。We can steal the assets of this temporary Godzilla that was created in the factory。

😊，A third。Examp， a third case。Let's assume that we are using standard library list。

 The standard library containers， all of them take arguments when we want to push something into the container and copy the argument。

So when we push back a goodzilla， this 3y1 into the list。Before C 11。

 probably we are copying the Godzilla that was created on the collie side。We。

 without any actual need， because we don't need this temporary object anymore。 Now。

 we couldn't take the actual object into the list because the object was created here unless。

 of course， maybe there is some optimization， but let's assume that the compile was not able to perform any optimization。

 Then there is an object being created on one side。 And then the object is passed。To another side。

 But then the other one， which needs the values， maybe it can。Move， still。

 take the values instead of copy them。 So this is the motivation。

 The idea is to avoid redundant copying when we can steal from a dead object。 Now。

 maybe still doesn't。Sounds so nice。 And it is not a dead object because we cannot steal from a dead object。

 So it's more a move instead of steel， sounds better， I would say， and an almost dead object。

An object that that is about to be distracted。In some cases。

 I would say that the compiler is able to perform some optimization called return value optimization。

 copy lesion or named return value optimization。 I will ignore them。

 Maybe I will discuss them shortly， but not in all cases。

 So the idea that we can save the need for copying in cases where the compiler was not able to perform any other optimization。

 because if the compiler was able to do optimization。

 then the need for avoid copying is not there anyhow。 but that's not the case always。😊。

And we may discuss it later。If you regard questions to see that you are with me。

 should we still a sorry move in this case， I mean， still a move is the same。What do you say？

I hear no。 And the reason is。S TR 1 might still be in use。 I mean， the next line may use S T1。 So no。

 don't， do not move here。 What about this one。So when we concatenate two strings。

 we get back a new string， which is。Just created for us， which is local。

 which is going to die in a moment。 It's a temporary。 Can we steal it。Yes， we can。 Should we， Yes。

 we should， okay。So the question is， how can we distinguish between the two， I mean。

In the first case， we do not want to move in the second case we do want。 What is the difference。

 How can we tell， oh， this one is that and the other one。

 So let's start with the compiler is able to distinguish it between the two。

 So if you get the help from the compiler saying， oh， I'm the compiler。

 one of the things that the compiler is do that is following lifetime。 And the compiler can say， oh。

 I see that this object， Life is。😊，Ended by the end of the statement。 And the other one is not。Okay。

 so we need some kind of from the compileella but but let's start with， with terms。

 Let's have different terms for each of these。 So let， let's both are。

 let's see the differences and and the similarities。 both assigned expressions are references。

 I mean， the second one is the local reference to a temporal。

 But there is an object lived living there for a moment。

 So both are both are references to an expression， currently。

 both lines would call the coppi constructor。 when I say currently， I mean， before C plus plus 11。

 or if we do not implement the pop operation to allow the second one to be more efficient。

And there are kind of different references。 The first one would still be alive after the end of the statement and the other one would not。

By the way， temporary object was a term being used before C plus 11。

 So was 98 already used the term temporary object。So let's name them。

 Let's call the one that would still be alive in L value reference。 Now。

 the name L value reference comes because。It may sit on the left value of an expression。

 It might be assigned to。 I mean， you are still alive。You have an address。

 I can assign something to you。So you are a valid L value。 So let's call you L value Ref。

 Does't mean that you will be always on the left value and of an expression of a statement。 No。

 you can be on the right side of a statement。 instead you are an L value Ref。

 Can you give you an example of an L value， which sits on the right side of a statement。This one。

 S A1 is an L value。 It is on the right side。 It is still an L value because it would still be alive after this statement。

 So the name L value doesn't mean that you should always be on the left side。

 It means that you can be on the left side。 which means that you would be still alive， Okay。

 so this is the nickname for these kind of references。

 how can what should be the name for the other one。 I mean， what is the opposite of left。

Value reference。I think we can go with there。 The， the opposite left is right。

 So let's call it our value reference。Which means that it doesn't mean that you necessarily have to be on the right side of an expression。

 I mean， I mean， you can be sent to a function。 Would we consider it as a value reference。 Yeah。

 if you are temporary a question， can an our value I something which is a temporary seat on the left value of a statement。

Because if the answer is yes， then we can， you know， wrap up and and go。 I mean。

 so what do these names say。And the answer is。Yes， it can。And I believe reference Ken sit。



![](img/bff0efffefa4dfb53a3aaadf9657dcb8_10.png)
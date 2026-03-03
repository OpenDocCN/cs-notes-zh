# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P39：Chapter 3 12.Factored FSMs.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/c3e63c5e0907e525d2c21ceac892460c_0.png)

Facted finite state machines break complex finite state machines into smaller interacting FSMs。

 So this allows us to reduce the complexity of the FSM。 And when we can reduce complexity。

 we can simplify the design， the testing， the debugging。😊，And so a lot of advantages there。

So example is， let's suppose we want to modify the traffic light controller that we built earlier to have a parade mode。

 So we're going to have two more inputs， P and R。When P equals one。

 it enters paradede mode and bravada Boulevard stays green。

 there's going to be a parade going down bravada Boulevard。And when r equals one。

It's going to leave parade mode and go back into its regular operating mode。

So we could have an unfactored FSM where we just include all of those features now in an updated。

 you know FSM that includes all of that complexity， or we could basically use our original FSM。

 the mode， the lights FSM。And add a second FSM called the mode FSM that determines when the light FSM stays with bravada boulevard being green。

And so in that way， we need an internal signal here， the M。

 the mode signal to tell the lights FSM which mode it's in。

And so we still have essentially our lights FSM will be very close to the same with an added input。

 and now we have this mode FSM that takes in these two new inputs and determines which mode it should be in。

So here's an unfed version of the FSM where we include all of the features in the finite state machine。

😊，But our factor at FSM is much cleaner。 So here we have our mode FSM。

And as long as parade mode is low， it stays in the S 0 state with mode， this M output being 0。

But when the parade input asserts。Then we go to S1。Or the FSM goes to S1 and mode。Becomes one。

And so now when。When the lights FSM is in the S2 state， if mode is true or TB is true， right。

 it used to just be。When t is true。Stay in S 2。 When TV is false， go to S 3。

But now it says when TB is true or if。We get this M output from the mode， FSM。So when M equals one。

 that stays in that state。In the S2 state and keeps LB green and LA stays red。

 so let's the paradede go down bravada Boulevard。And then now we need to have the other case include the mode case。

😊，As well。 So remember， we want the opposite of M or T B。 So M or T B。

 all that bar is the same as M bar and T B bar。 So we could have written this， know。

 maybe more clearly to say。That these are， disjoined。Cases， and they cover all the cases。

That's the other case one。M or T B。When they're both zero， in other words， MR or T B。That is0。

 that that expression， that or expression is0。 Then we want to go here or in other words。

 when M is 0 and T B is 0。Then we want to leave that state and start to。Make L A green。

And so in this case， much simpler， right， much simpler FSNs and much simpler to design。

 test and debug。

![](img/c3e63c5e0907e525d2c21ceac892460c_2.png)
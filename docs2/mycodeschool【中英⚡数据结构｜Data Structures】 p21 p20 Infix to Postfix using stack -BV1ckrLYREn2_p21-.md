# mycodeschool【中英⚡数据结构｜Data Structures】 p21 p20 Infix to Postfix using stack -BV1ckrLYREn2_p21-

![](img/73e261f84b5ef117ec43852bf008e5d4_0.png)

In our previous lesson we saw how we can evaluate prefix and postFx expressions now in this lesson we will see an efficient algorithm to convert infi to postfix we already know of one way of doing this。

 we have seen how we can do this manually to convert an infi expression to postfix we apply operator precedence and associivity rules。



![](img/73e261f84b5ef117ec43852bf008e5d4_2.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_3.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_4.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_5.png)

Let's do the conversion for this expression that I have written here。

 The precedence of multiplication operator is higher。So we will first convert this part B asterisk C。

B asterisk C will become B asterisk， the operator will come in front of the opera。

Now we can do the conversion for this edition for addition。

 the opera are a and this post fixed expression。In the final step we can get rid of all the parentheses。

 so finally this is my post fixed expression。We can use this logic in a program also but it will not be very efficient and implementation will also be somewhat complex I am going to talk about one algorithm which is really simple and efficient and in this algorithm we need to passse the infi expression only once from left to right and we can create the postfi expression if you can see in infi to postfi conversion the positions of operations and operators may change but the order in which operations occur from left to right will not change the order of operators may change。



![](img/73e261f84b5ef117ec43852bf008e5d4_7.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_8.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_9.png)

This is an important observation in both in fixed and post fixed forms here。

 the order of opera as we go from left to right is first we have a。

 then we have P and then we have C。

![](img/73e261f84b5ef117ec43852bf008e5d4_11.png)

But the order of operators is different。In infi first we have plus and then we have multiplication in post fix first we have multiplication and then addition。



![](img/73e261f84b5ef117ec43852bf008e5d4_13.png)

In postfi form we will always have the operators in the same order in which they should be executed I am going to perform this conversion once again but this time I am going to use a different logic what I'll do is Ill parse the infi expression from left to right so Ill go from left to right looking at each token that will either be an opera or an operator。



![](img/73e261f84b5ef117ec43852bf008e5d4_15.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_16.png)

In this expression we will start at a a is an opera end， if it's an opera。

 we can simply append it in the post fixed string or expression that we are trying to create。



![](img/73e261f84b5ef117ec43852bf008e5d4_18.png)

At least for a， it should be very clear that there is nothing that can come before a。

Okay so the first rule is that if it is an opera we can simply put it in the postF expression moving on next we have an operator。

 we cannot put the operator in the postF expression because we have not seen its right opera yet while passing we have seen only its left opera we can place it only after its right opera is also placed。

So what I' am going to do is I am going to keep this operator in a separate list or collection and place it later in the postF expression when it can be placed and the structure that I am going to use for storage is stack a stack is only a special kind of list in which whatever comes in last goes out first insertion and deletion happen from the same end I have pushed plus operator onto the stack here。

Moving on next we have B， which is an opera， as we had said， opera can simply be appended。

There is nothing that can come before this opera the operator in the stack is anyway waiting for the opera to come。



![](img/73e261f84b5ef117ec43852bf008e5d4_20.png)

Now at this stage， can we place the addition operator in the post fix string？



![](img/73e261f84b5ef117ec43852bf008e5d4_22.png)

Well actually whats after B also matters in this case we have this multiplication operator after B which has higher precedence and so the actual operator for addition is this whole expression B asterisk C we cannot perform the addition until。



![](img/73e261f84b5ef117ec43852bf008e5d4_24.png)

Mulipplication is finished。So while passing when I'm at B and I have not seen whats ahead of B。

 I cannot decide the fate of the operator in the stack。

 so lets just move on now we have this multiplication operator I want to make this expression further complex to explain things better so I' am adding something at tail here in this expression。

Now I want to convert this expression to postfi form， Im not having any parenthesis here。

 we will see how we can deal with parenthsesis later。

 let's look at an expression where parenthesis does not override operator precedence。Okay。

 so right now in this expression， while parsing from left to right。

 we are at this multiplication operator。The multiplication operator itself cannot go into the postF expression because we have not seen its right opera yet and until its right opera is placed in the postF expression。

 we cannot place it the operator that we would be looking at while parsing that operator itself cannot be placed right away。



![](img/73e261f84b5ef117ec43852bf008e5d4_26.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_27.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_28.png)

But looking at that operator， we can decide whether something from the collection。

 something from the stack can be placed into the post fixed expression that we are constructing or not。



![](img/73e261f84b5ef117ec43852bf008e5d4_30.png)

Any operator in the stack having higher precedentnce than the operator that we are looking at can be popped and placed into the postF expression。

 lets just follow this as rule for now and Ill explain it later there is only one operator in the stack and it is not having higher precedence than multiplication so we will not pop it and place it in the postF expression。

Mulipplication itself will be pushed。If an element in this stack has something on top of it。

 that something will always be of higher precedence。

So let's move on in this expression now now we are at C， which is an operant， so it can simply go。

Next we have an operator subtraction。Subtraction itself cannot go， but as we had said。

 if there is anything on this stack having higher precedence than the operator that we are looking at。

 it should be popped out and should go and the question is why we are putting these operators in the stack we are not placing them in the post fixed expression because we are not sure whether we are done with their right operator or not but after that operator as soon as I am getting an operator of lower precedence that marks the boundary of the right operator for this multiplication operator see。



![](img/73e261f84b5ef117ec43852bf008e5d4_32.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_33.png)

Is my right opera it is this simple variable for addition B asterisk C is my right opera because subtraction has lower precedence anything on or after that cannot be part of my right opera。



![](img/73e261f84b5ef117ec43852bf008e5d4_35.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_36.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_37.png)

Subtraction I should say， has lower priority because of the associivity rule if you remember the order of operation addition and subtraction have same precedentnce but the one that would occur in left would be given preference so the idea is any time for an operator if I am getting an operator of lower priority we can pop it from the stack and place it in the expression here we will first pop multiplication and。



![](img/73e261f84b5ef117ec43852bf008e5d4_39.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_40.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_41.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_42.png)

Place it。And then we can pop addition。

![](img/73e261f84b5ef117ec43852bf008e5d4_44.png)

And now we will push subtraction onto the stack。Let's move on now D is an opera。

 so it will simply go。Next we have multiplication， there is nothing in this stack having higher precedentnce than multiplication。

We will pop nothing。Mulplication will go onto this stack。



![](img/73e261f84b5ef117ec43852bf008e5d4_46.png)

Next we have an opera it will simply go now there are two ways in which we can find the end of right operator for an operator A is if we get an operator of lesser precedence B。

 if we reach the end of the expression now that we have reached end of expression we can simply pop and place these operators so first multiplication will go。



![](img/73e261f84b5ef117ec43852bf008e5d4_48.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_49.png)

And then subtraction will go。

![](img/73e261f84b5ef117ec43852bf008e5d4_51.png)

Lets quickly write pseudocode for whatever I have said so far and then you can sit with some examples and analyze the logic I am going to write a function named infi to post fix that will take a string EXP for expression as argument。



![](img/73e261f84b5ef117ec43852bf008e5d4_53.png)

For the sake of simplicity， let's assume that each operator or operator will be of one character only。

In an actual implementation， you can assume them to be tokens of multiple characters。

So in my pseudocode here， the first thing that I'll do is I'll create a stack of characters named S。



![](img/73e261f84b5ef117ec43852bf008e5d4_55.png)

Now I'll run a loop starting zero till length of expression minus1。



![](img/73e261f84b5ef117ec43852bf008e5d4_57.png)

So I'm looking at each character that can either be an operator or operator。



![](img/73e261f84b5ef117ec43852bf008e5d4_59.png)

If the character is an operant， we can append it to the post fixed string。

 well actually I should have declared and initialized a string before this loop。



![](img/73e261f84b5ef117ec43852bf008e5d4_61.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_62.png)

This is the results string in which I'll be app。

![](img/73e261f84b5ef117ec43852bf008e5d4_64.png)

Else if expression I is operator。

![](img/73e261f84b5ef117ec43852bf008e5d4_66.png)

We need to look for operators in the stack having higher precedentnce。

 so I'll say while stack is not empty and the top of stack has higher precedentnce。



![](img/73e261f84b5ef117ec43852bf008e5d4_68.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_69.png)

And let's say this function has higher precedentnce will take two arguments， two operators。

 so if the top of stack has higher precedentnce than the operator that we are looking at。



![](img/73e261f84b5ef117ec43852bf008e5d4_71.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_72.png)

We can append the top of stack to the result， which is the variable that will store the post fix string。

And then we can pop that operator。I'm assuming that this S is some class that has these functions top and pop。



![](img/73e261f84b5ef117ec43852bf008e5d4_74.png)

And empty to check whether it's empty or not， Finally。

 once Im done with the popping outside this while loop， I need to push the current operator。



![](img/73e261f84b5ef117ec43852bf008e5d4_76.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_77.png)

S is an object of some class that will have these functions stop up and empty okay so this is the end of my fall loop at the end of it I may have some operators left in the stack I'll pop these operators and upend them to the post fixes string I'll use this while loop I' will say that while the stack is not empty。



![](img/73e261f84b5ef117ec43852bf008e5d4_79.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_80.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_81.png)

Upend the operator at top and pop it and finally after this wide loop I can return the results string that will contain my post fix expression。



![](img/73e261f84b5ef117ec43852bf008e5d4_83.png)

So， this is my pseudocode for whatever logic Ive explained so far in my logic I' have not taken care of parenthesis。

 what if my infi expression would have parenthsesis like this？



![](img/73e261f84b5ef117ec43852bf008e5d4_85.png)

There will be slight change from what we were doing previously。With parenthesis。

 any part of the expression within parenthesis should be treated as independent。

 complete expression in itself and no element outside the parenthesis will influence its execution。

In this expression， this part， a plus B is within one parenthesis。

Its execution will not be influenced by this multiplication or this subtraction， which is outside it。

Similarly， this whole thing is within the outer parenthesis。

So this multiplication operator outside will not have any influence on execution of this part。

As a whole， if parenthsesis are nested， inner parenthesis is sorted out or resolved first and then only outer parenthesis can be resolved。

With parenthesis we will have some extra rules， we will still go from left to right and we will still use stack and let's say I'm going to write the post fixed part in right here as I create it。



![](img/73e261f84b5ef117ec43852bf008e5d4_87.png)

Now while parsing， a token can be an opera an operator or an opening or closing of parenthesis。

 we will have some extra rules I'll first tell them and then I'll explain if it' is an opening parenthesis we can push it onto the stack。

The first token here in this example is an opening parenthesis。

 so it will be pushed onto this stack and then we will move on we have an opening parenthesis once again。

 so once again we will push it。

![](img/73e261f84b5ef117ec43852bf008e5d4_89.png)

Now we have an opera。😊，There is no change in rule for opera。

 it will simply be appended to the post fixed part Next we have an operator。

Remember what we were doing for operator earlier we were looking at top of stack and popping as long as we were getting operator of higher precedence earlier when we were not using parenthesis。

 we could go on popping and empty the stack but now we need to look at top of stack and pop only till we get an opening parenthesis because if we are getting an opening parenthesis then it is the boundary of the last open parenthesis and this operator。

😊。

![](img/73e261f84b5ef117ec43852bf008e5d4_91.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_92.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_93.png)

Does not have any influence after that outside that。

 so this plus operator does not have any influence。Outside this opening parenthsesis。

I'll explain this scenario with some more examples later let's first understand the rule so the rule is if I'm seeing an operator I need to look at the top of stack。

 if it's an operator of higher precedence I can pop and then I should look at the next stop if it's once again an operator of higher precedence I should pop again。

 but I should stop when I see an opening parenthesis。



![](img/73e261f84b5ef117ec43852bf008e5d4_95.png)

At this stage we have an opening parenthesis at top so we do not need to look below it。

 nothing will be popped anyway addition however will go onto this stack remember after the whole popping game we push the operator itself next we have an opera it will go and we will move on next we have a closing of parenthsesis when I am getting a closing of parenthsesis I am getting a logical end of the last opened parenthsesis。



![](img/73e261f84b5ef117ec43852bf008e5d4_97.png)

For part of the expression within that parenthesis it is coming to the end and remember what we were doing earlier when we were reaching the end of infi expression we were popping all the operators out and placing them so this time also we need to pop all the operators out。



![](img/73e261f84b5ef117ec43852bf008e5d4_99.png)

But only those operators that are part of this parenthsesis that we are closing so we need to pop all the operators until we get an opening parenthsesis Im popping this plus and up it next we have an opening of parenthsesis so I will stop but as last step I will pop this opening also because we are done for this parenthsesis okay so the rule for closing of parenthesis isp until you are getting an opening parenthesis and then finally pop that particular opening parenthsesis also。



![](img/73e261f84b5ef117ec43852bf008e5d4_101.png)

Let's move on now next we have an operator we need to look at top of stack it is an opening of parenthesis。

 this operator will simply be pushed next we have an opera end next we have an operator once again we will look at the top we have multiplication which is higher precedence。

So this should be popped and appended we will look at the top again it's an opening of parenthsesis so we should stop looking now minus will be pushed now next we have an next we have closing of parenthsesis so we need to pop until we get an opening minus will be appended finally the opening will also be popped next we have an operator and this will simply go。

Next we have an opera end and now we have reached the end of expression。

 so everything in the stack will be popped and appended， so this finally is my post fixed expression。

I'll take one more example and convert it to make things further clear。

 I want to convert this expression。 I'll start at the beginning first we have an opera end。



![](img/73e261f84b5ef117ec43852bf008e5d4_103.png)

Then this multiplication operator， which will simply go onto the stack， the stack right now is empty。

 there is nothing on the top to compare it with。Next we have an opening parenthesis which will simply go next we have an opera it will be appended and now we move on to this edition operator if this opening parenthsesis was not there the top of stack would have been the multiplication operator which has higher precedentnce so it would have been popped but now we will look at the top and it is an opening parenthesis so we cannot look below and we will simply have to move on next we have C。



![](img/73e261f84b5ef117ec43852bf008e5d4_105.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_106.png)

I missed pushing the addition operator last time。Okay after C we have this closure。

 so we need to pop until we get an opening and then we need to pop one opening also finally we have reached the end of expression so everything in the stack will be popped and appended so this finally is my post fixed part post fixed form。

In my pseudocode that I had written earlier。

![](img/73e261f84b5ef117ec43852bf008e5d4_108.png)

Only the part within this。F loop will change。

![](img/73e261f84b5ef117ec43852bf008e5d4_110.png)

To take care of parenthesis。In case we have an operator。

 we need to look at top of the stack and pop but only till we are getting an opening parenthsesis so I have put this extra condition in the while loop。

 this condition will make sure that we stop once we get an opening parenthesis right now in the fall loop we are dealing with operating and operators we will have two more conditions if it is an opening of parenthsesis we should push else if its a closer。



![](img/73e261f84b5ef117ec43852bf008e5d4_112.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_113.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_114.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_115.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_116.png)

We can go on popping and pending， let's say this function is opening parenthesis we'll check whether a character is opening of parenthsesis or not。

 in fact we should use this function here also when I' am checking whether current token is opening or not。

 because it could be an opening curly brace or opening bracket also。



![](img/73e261f84b5ef117ec43852bf008e5d4_118.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_119.png)

This function will then take here， let's say this function will take here and similarly for this last teleelE we should use this function is closing parenthesis。



![](img/73e261f84b5ef117ec43852bf008e5d4_121.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_122.png)

Okay， things are consistent now after this while loop in the last Elelsif we should do one。



![](img/73e261f84b5ef117ec43852bf008e5d4_124.png)

Extra pop。And this extra pop will pop the opening parenthsesis。

And now we are done with this Elsif and this is closer of my for loop。



![](img/73e261f84b5ef117ec43852bf008e5d4_126.png)

rest of the stuff will remain same。After the fall loop we can pop the leftovers and pen to the string and finally we can return so this is my final pseudocode you can check the description of this video for a link to real implementation actual actual source code okay so Ill stop here now this is it for this lesson thanks for watching。



![](img/73e261f84b5ef117ec43852bf008e5d4_128.png)

![](img/73e261f84b5ef117ec43852bf008e5d4_129.png)
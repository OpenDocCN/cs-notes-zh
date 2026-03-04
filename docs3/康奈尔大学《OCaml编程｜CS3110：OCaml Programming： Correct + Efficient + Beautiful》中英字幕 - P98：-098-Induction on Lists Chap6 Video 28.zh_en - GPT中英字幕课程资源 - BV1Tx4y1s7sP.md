# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P98：-098-Induction on Lists Chap6 Video 28.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we've seen how to do induction on our variant type for NAP， let's do it on lists。

The structure of an inductive proof on lists is going to be very familiar from what we just did。😡。

The base case is the empty list， just like for Nat， it was the zero， the Z constructor。

 and like for natural numbers in mathematics， it was the number zero。

 and we just need to show that the property P holds when instantiated on that base case。

 in this case， the empty list。The inductive case， well let's think about how that was always formed in the past。

 it was always a value that was one bigger than another value so it was one bigger as a natural number。

 whether it was the mathematical natural numbers or the variant type that we'd code it up for。😡。

In the case of a list， how do you get one bigger， you cons on to the beginning of a list。

 another element。So here， in the inductive case， the list is actually going to be some head consdon to some tail T。

The tail T is the smaller element of the type。So the inductive hypothesis is the property P and staiated on that smaller value。

 the tail。And we want to show that the property holds of the entire list， HCOs T。

Let's put that to work。Let's prove。That if you append the empty list。



![](img/8712fca364343e3e3ee3fefc4a62d417_1.png)

You get the original list back。To get us started， I've put that source code for append in here as an operator and I've also stated the claim that we want to prove。

We're going to do this by induction。Okay， I've set up the base case here。

 the base case of course is for the empty list， so I've instantiated my property P on the empty list。

 which means I need to show that nil append nil is equal to nil。Easy to do。

That's just one step of evaluation because the append operator is going to pattern match against its left hand argument。

 see that it's the empty list and just returning it。Let's pause here。 I've set up the inductive case。

 The list is now going to be a head element con on to some smaller list T。

And I want to show that when I append nil to that， it leaves me with the original list H cons T。

So to do this， I can take a first step of evaluation of the append operator because I know that the left hand side here is a cons。

 So I know that when I match against that， I'm going to be in this case of the pattern match and therefore。

I'm going to return H cons of pen T list 2。 She had just realized I have a little error here as I turn that into an operator。

 I should have written it over here like this。Okay。So that makes it a little better。Down here。

 that means I have H cons， T append nil。Well， I can't take another step of evaluation of a pen there because I don't know what t is。

 It could be nil。 It could be a cons， but my inductive hypothesis would now apply。 Now， silly me。

 I forgot to set up my inductive hypothesis up here。Okay， now that I've done that。

 I know that T append niil is， in fact， T so I can replace that down here。

And that's what I wanted to show for this inductive case。 I am done。Now。

 one really interesting thing to do next is to compare this proof。

To the one we just did with the proof for natural numbers and adding zero。



![](img/8712fca364343e3e3ee3fefc4a62d417_3.png)

Here are those two proofs on the screen at the same time so we can kind of compare them line by line。

We had an operator that kind of added together two things， whether it was a natural number or a list。

 both of those pattern matched on their first argument in the case of a base case。

 either zero or the empty list returned the second argument。

 otherwise did a recursive call involving the first piece of data and the second piece of data。

 whether that was the smaller natural number or the smaller list。😡，And then for both of these。

 we were trying to prove that if you use that operator， either plus or append。

 and the right hand side of that operator was the base value。

 which was either zero or the empty listt， then you got back whatever you passed in as the other opera end。

😡，We did both of them by induction， and the whole thing ended up being the same in terms of a proof。

 Actually， I just noticed that I left off what I wanted to show here。 That was bad of me as well。

 So let me add that in too。Now we've recovered the similarity between those two。

And you can see that the proof structure ends up being exactly the same and that even the proof justification steps end up being exactly the same here in the inductive case。

 you see that as well， just evaluation and the inductive hypothesis。Okay。

 so those really were doing the same proof in some sense。

 just on two different data types once on Na the other time on list。



![](img/8712fca364343e3e3ee3fefc4a62d417_5.png)
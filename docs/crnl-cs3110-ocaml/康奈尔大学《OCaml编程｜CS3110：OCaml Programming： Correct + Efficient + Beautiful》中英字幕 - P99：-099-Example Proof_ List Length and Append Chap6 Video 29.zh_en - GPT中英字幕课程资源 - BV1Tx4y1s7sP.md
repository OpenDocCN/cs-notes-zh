# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P99：-099-Example Proof_ List Length and Append Chap6 Video 29.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/a59570e3007af58ddf5d19ca3bd3f41b_0.png)

Let's try another inductive proof about lists。This time， we'll look at the length of a list。

 You know how that function is defined。 What I want to prove is that if I append list two lists。

 x's and y's， then I get back a list that its length is the sum of the info lists。

 So length of x's append Ys is equal to length x's plus length y。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_2.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_3.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_4.png)

Another way of thinking about that is that the length operation distributes over append in a particular way。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_6.png)

Okay， so to do this I'm going to do a proof by induction。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_8.png)

But what am I going to induct on。I've got two choices， x's or Y's。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_10.png)

One clue to a better choice here is to look at how the pattern matching works and the functions that I'm going to be using。

😡，The append operator pattern matches against its left hand argument。

That generally means that when I do and induct a proof about append。

 I'm going to want to be inducting on whatever is used as a left hand argument to that operator。😡。

So you can see here that the left hand operaand is x's。

 so that's a good clue that that's going to be the thing that I want to induct R。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_12.png)

So here it's becoming increasingly more important to be careful about stating what we want to show and what the property P is。

So since we're doing induction on x's here， that particular variable。

 the property P we want to show is a property of that of x's。

 and it's the rest of the claim that we had before， which is that for all Y's。

 the length of x' is append y's equals the length of x's plus the length of y's。

So now we can set up the base case。Here we can take a first step of evaluation by reducing the empty list append wise。

 We know what append does when it's past the empty list as its left hand argument。

 It just returns the right hand。Now that doesn't quite look like the right hand side yet。😡。

So let's work the right hand side a little。So we can easily take one step of evaluation there because we know what length is going to do when it's past the empty list。

 we see that up here， we know it's going to return zero。So now we've got zero plus the length of Y's。

 and of course it's very quick to get rid of that zero。

And now we have an equality between the left and right hand side of what we wanted to show。

 so we're done with the base case。Now， let's do the inductive。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_14.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_15.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_16.png)

Okay， we'll pause here， I've set up all of the structure I need for my inductive proof。

 and now I'm ready to take a first step of evaluation。

 I know what aend is going to do when it's past a list that has a cons on the front of it as opposed to a non- emptyty list。

 so let's take that step first。

![](img/a59570e3007af58ddf5d19ca3bd3f41b_18.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_19.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_20.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_21.png)

Okay， now I can't evaluate the append anymore because I have no idea whether the tail T is nil or cons。

 so I don't know what that pattern match is going to do。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_23.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_24.png)

But I do know what length is going to do because it pattern matches and if it has a cons there。

 it's going to return one plus the length of the smaller list。

So I can go ahead and take that step of evaluation。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_26.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_27.png)

Now I can't evaluate any further， but the inductive hypothesis applies at this point because I have this length T at Y and that's what shows up in the inductive hypothesis up there as well。

 so I can rewrite that。

![](img/a59570e3007af58ddf5d19ca3bd3f41b_29.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_30.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_31.png)

Okay， I'm stuck there， I can't take any further steps of anything。

 but now I can start working on the right hand side。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_33.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_34.png)

So with just one step of evaluation， which is evaluating length here。

 which is being applied to a cons so that reduces to one plus the length of the smaller list。

 I now have an expression that is in fact the same as the expression from up here in that proof block。

 so I've shown the equality of those， and that finishes off that。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_36.png)

![](img/a59570e3007af58ddf5d19ca3bd3f41b_37.png)

QED， I'm done proving that length distributes over a pen。



![](img/a59570e3007af58ddf5d19ca3bd3f41b_39.png)
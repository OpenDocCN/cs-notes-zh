# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p174 33_03_depth-subtyping -BV1bw4m1D7MM_p174-

In the previous segment we saw four rules for our subtyping relation which are all allowed in this segment I want to investigate a fifth rule and see why it might not be such a good idea。



![](img/8dbc85ed640d4678626f88856cfe83f2_1.png)

So so far， our subtyping rules let us take a record type， forget some of the fields。

 and reorder the remaining fields。 that's all it lets us do。

So here's an example that it's not quite able to handle it。So in this example。

 I'm going to have some records that represent circles。

 a circle can be represented by its center and its radius。Now， what if for the center。

 I used a nested record that had a point in X coordinate in a Y coordinate。

 Well then a record type might look like this argument C to the circle Y function。

 C has type record with two fields， center and R R has type real center is another record type that makes perfect sense that a field of a record could refer to another record and that inner record has an X field in a Y field。

So this function very simple， just takes a circle and returns its y coordinate。

 So how high is it in the plane， Okay， so all I need to do is return C dot center dot Y。

 take the record C， access its center field with C dot center that gives me back a record。

 say dot Y on that， get back a real， and given the type of C， this will never fail。Now。

 what I cannot seem to do， I can't with my current rules is call circle Y with this sphere value。

 What's a sphere。 It's something that also has a center and a radius。

 but it lives in a three dimensionmensional environment。 So that inner thing， the center。

 It has an x coordinate a Y coordinate as Z coordinate。 So same sort of nested record。

 except the thing in the center field itself has an x field a y field and a Z field。

 So I could make such an object like this， this is the sphere centered at x is 3， Y is 4 z0。

 it has a radius of1。 And if I call circle Y with this。 If I didn't have a type system。

 this would work just fine。 I would get out the y coordinate， I would get 4。0 back。

 But in my type system， this only works。 if the type of sphere is a subtype of the type of C。

 So what we would need is that this type。😊。

![](img/8dbc85ed640d4678626f88856cfe83f2_3.png)

Where we have an x A Y and a Z inside of the record in the center field is a subtype of center of X Y。

 And you see there。 So I have the same question here， and you might be thinking， this is fine。

 I have with subtyping， I can do this。 It turns out you can't。

What we have to ask is this type on the top line， a subtype of this type on the bottom line？

All width lets you do is drop fields of the record so we could drop the R field or we could drop the center field。

 but our width rule does not let us go into a field and use subtyping there。

So what we see is we just forgot a rule， right， So let's just add a fifth subtyping rule。

 This rule has a name it's called depth subtyping， and it's a little more sophisticated because it has an if then。

It says if T is a subtype of TB， then you can replace T with TBB in a record type。

 as you see here after the then it says you can go into some record type。

 find some field that has type TA and replace it with TB you can do that as long as T as a subtype of TBB and so if we had this rule along with width subtyping now we can get the sub typing relationship we need for our sphere records and our circle records because we'd be able to use this rule to kind of go into the type of the center field and then the width rule to drop the Z out of that inner record type。

So depth subtyping makes our other rules more powerful by letting them be used on record fields。

 and that is enough going back to the example here to pass sphere to circle Y。

 So it sounds great and we should add it to our language， right。😊。



![](img/8dbc85ed640d4678626f88856cfe83f2_5.png)

![](img/8dbc85ed640d4678626f88856cfe83f2_6.png)

![](img/8dbc85ed640d4678626f88856cfe83f2_7.png)

Wrong。So。It's all nice that our new subtyping rule let's our example type check。

 but when you're evaluating whether a rule is a good idea and by evaluating， I mean， judging。

 not evaluation like we've meant in this course， when you're judging a rule。

You don't just get to try it on the examples where you want it to work。

You also have to make sure that all the programs you do not want are still forbidden。See。

 it's not worth making a type system more flexible if it breaks soundness if it allows programs that in our case。

 let you access missing record fields to try to read out a fo field from a record that doesn't have a fo or a Z field from a record that doesn't have a Z and unfortunately。

 the rule I just showed you that depth subtyping rule is unsound and all I have to do to prove that to you is show one example where with the rule。

 the program would type check and when you run that program。

 the bad thing we're trying to prevent would happen。



![](img/8dbc85ed640d4678626f88856cfe83f2_9.png)

So， here's an example。And it involves mutation。 I love to pick on mutation。

 This is another opportunity where mutation messes us up。😊，So instead of circle Y。

 here's a function set to origin， it takes in a C of the exact same type as circle Y。

 a record with a center field in an R field where the center field itself is a record with an X field of type real and a y field of type real。

😡，And what it does is it moves the circle to the origin， so it leaves the radius alone。

 but it updates C dot center to B x equals 0。0 y equals 0。0。 This is fine。

 I told you records had mutable fields。 We love to mutate things right So this function is perfectly reasonable and it updates the the circle。

So what would happen if I call this function set to origin with my sphere？Well。

 it's going to mutate that sphere。 In fact， it's going to mutate in a way such that it's not a sphere anymore。

 It's going to change the center field to hold a record that does not have a Z field。

This is a very bad idea。After I call set to origin of sphere。

 the type I gave to sphere is fundamentally wrong。The type I gave to sphere claims that in the center field is a record with a Z field and there isn't anymore。

 So on this next line， when I say sphere do center do Z。

This will type check because sphere has the type I gave it。 So it has a center field。

 that center field has a Z field。 And if you actually try to run this program in its entirety。

 you'll get stuck right here because there there is no Z field in the record that you get back from sphere center because of the earlier call to set to origin。

And the only typing rule we added， the one that's to blame is this subtyping rule here。

 depth subtyping， you just can't do this， you can't let a record type field change to a supertype turning TA into TB because that lets functions like set to origin turn spheres into circles。



![](img/8dbc85ed640d4678626f88856cfe83f2_11.png)

So to repeat the moral of the story， if you have a language with records or objects because objects are things that have a bunch of fields in them。

 like instance variables with getters and setters。Depth subtyping。

 allowing subtyping on record fields， is unsound。A lot of people forget this。

 A lot of people don't never learn this， never realize this。

 They think languages should support this， and they don't。If you have getters and setters。

 you cannot allow the type of a field and a record to change to a supertype or to a subtype for that matter。

But here's the neat thing。 If fields are immutable。

 If you take a more functional approach and don't allow setters on your records。

 then depth subtyping is actually sound。 I haven't shown it through your here。

 but I promise I'm not lyingwing this time。 So this is yet another benefit of outlaawwing mutation that it turns out that when it comes to records。

 you can choose any two of the following three， you can allow setters。

 you can allow depth subtyping and you can have a sound type system。 you can have two of those three。

 but as we saw in the example on the previous slide， you can't have all three。

 So if you want soundness and depth subtyping， why not get rid of the setters。

 But if you wish to choose a different two out of that list。

 I suppose that's a matter of personal preference。 In any case， subtyping is not a matter of opinion。

 if you do have setters and you do want soundness， then you cannot have our depth subtyping rule that we showed in this section。

😊。

![](img/8dbc85ed640d4678626f88856cfe83f2_13.png)
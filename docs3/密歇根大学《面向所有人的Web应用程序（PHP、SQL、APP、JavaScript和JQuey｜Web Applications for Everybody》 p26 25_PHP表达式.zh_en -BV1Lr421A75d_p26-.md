# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p26 25_PHP表达式.zh_en -BV1Lr421A75d_p26-

![](img/1088af125e4434179802b6135f9e8637_0.png)

![](img/1088af125e4434179802b6135f9e8637_1.png)

So an important part of any programming language is how it handles expressions。

 those are things that are kind of on the right hand side of an assignment statement or all over the place。

 right， you know if you have pluses and minuses， it works very much the same as all other the languages using plus minus slash asterisk。

 actually this whole convention， this thing came from Fortranran。



![](img/1088af125e4434179802b6135f9e8637_3.png)

That's how old that is。 That's from 1955， right， That's 1955 is when we had these。

 when they decided multiplication was asterisk probably even before that。

 And we still use it to this day。 so that when every time you type an asterisk when you want to do multiplication。

 think that's from 1955。And so the expressions are on the simplest expression sort of here we have on the right hand side。

 the interesting thing about PhP is that has something that's actually rather rare。

 Although javascript is kind of another language that has very aggressive type conversion。

 and that it doesn't want to blow up。 It wants to convert it。

 And so if it looks at this string 15 plus 27。 like what is going on here。 Now。

 one of two things could happen。 It could treat that as a string and end up with 1527 and concatenate those two things together。

 That's not what it does。 It actually converts this to an integer and then adds them together and gives us 42。

 And so there's a lot of implicit type conversion。 This plus is a numeric。

And so it's going to try to convert its operaans to B numbers， and so that's how we end up with 42。

So the values can be strings and numbers， we can use function calls and there's this order of evaluation that is the same for all programming languages and they can also produce operations So some operators of note if you're coming from Python。

 some of these have Python equivalent， some of them don't we'll talk about some of these there is a increment operator that just says add one to this variable subtract one to the variable concatenation that's quite special equality and not equal these are both common across all C languages this also came from C。

The identity， this is equal in value with type conversion。

And this is equal in without type conversion， so the triple equals and the triple not equals no type conversion。

So in you know， false。Is equal to zero but false。Is not triple equal0。

Because these are different types， false and0 or different types here it's going to convert that to a0。

 Then that's what're going to become true here it's not going to convert that to0。

 The Turner app will'll talk about that。 This is also kind of a classic 1972 C idea。

 And then the side effect。 And then there's other things that come from。

 these are also come from C that are very bit oriented operators， and that's the zeros in the ones。

And they're ending and oing and shifting these things around。

 these usually have no no use unless you're doing something like a compression or encryption or something like that。

 so if you see these you're not going to tend to use these operators。Okay， so let's look at them。

 so increment and decrement， this plus plus is a side effect。 So if we have dollar X。

And it has a 12 in it， so we come in here and again， like any right hand side。

 it's evaluating this right hand side， so it has to first resolve this x。

 so it has to go retrieve the x， so pulls the x the 12 out and makes it part of this expression。

 but then as a side effect and the plus plus is after the x。It turns this to 13。 Now。

 the 12 still exists since 15 plus 12。 and so we end up with 27。

But x has become 13 in this next statement， because as a side effect of reading and adding one。

 that's what we got。You can also say plus plus dollar x。

And the only thing that does is it adds the one before it copies the versions of it copies the value into the expression。

 so in that case this would be 28， x would still be 13。

Now most civilized people tend not to use that unless there will be places I'll tell you to use it and in general I tend not to use it at all。

 and so we tend to do things like add one to it explicitly。

 so we say x equals 12 so we have these x there's a 12 in here we copy the 12 into this 15 plus x so y is 27 and then in this next statement we then add 1 to x and so we add a statement here but we're making it a little clear as to what's going on some people like to show off and write as dense a code as possible。

 I tend to avoid that。The period character， like I said。Is a string operator。

 So it it's not just the fact that it concatenate strings。

 It will also convert its opera ends to strings。 Now， it does not add a space。

 It's just a pure concatetnation。 So if I want hello space world， then I have to add that hello。

 And so I can echo hello world with no new line。 but then I cancatenate that's that variable with concatenated with a new line。

 So I get my new line here with hello world。 So。

![](img/1088af125e4434179802b6135f9e8637_5.png)

One of the things about PhP is the operators have attitude in that they are expecting and are converting based on the type。

 so strings are dot is a string operator plus is a mathematical operator。

 so that actually is in some ways a little more predictable than some languages like JavaScript has this kind of stuff but you can't always predict what it's doing because the operators are more object oriented。



![](img/1088af125e4434179802b6135f9e8637_7.png)

Okay， so this is the turnernary operator。The ternary operator comes from the C programming language。

 and it comes from a time when we wanted to make things very succinct。

 and so the terary operator is basically an if then else in a single line。

So we have an assignment statement here， and there are three parts。

 It's called Turnney because there's three parts。 The first part is a question。

That revvalus the true or falses。 The second part is the result of the expression。

 because this is kind of an expression。 You could put parentheses around it right there。

 This is the value of the expression。 If this is true， and this is the value of the expression。

 as if it's false。 So the way I think about this is I think about this as you got these two values kind of in flight。

That are going to go into this variable message。 And then we pick the one。 So in this case。

 w w W is greater than 100。 So it's a true。 So we pick the one that's true。

 And then that one goes in。 Okay， so they kind of both end up in flight， basically。

It's like this is an assignment statement and one of these two things is going to get in。

 and it turns out this is the one that gets in。OkayAnd so that's why large comes out。

And so we can do things like take the divide by two， take the remainder and ask if it's zero。

 that would mean that it's even either an even number or an odd number and in this case this turns out to be false because it's 123 and so odd gets put over here and so away we go。

This is sort of an example of type conversion。 We take w， w， get the remainder after dividing by 2。

 And in this case， that's going to be one because it's 123。 And that's going to turn into true。

 So one becomes true。And so odd， it copied into message。

 I flip the order of the even and the odd because if it's the result is a one， that's true。

 which is odd。 And if the result is 0， then that's false。 And then you get even。

 So that's kind of a turnernary operator。

![](img/1088af125e4434179802b6135f9e8637_9.png)

I wish I didn't have to teach that to you， but we tend to use it a lot for certain things like checking to see if a key is in an array。

And。So there's a bunch of syntax that we do and so we use it over and over and over again。

 so I have to teach it to you I'd rather not teach it to you， but we just kind of。

If we didn't do that， we'd have way too many if elses in certain very specific situations。

 these are like idiomatic situations where oh you look at it go like that's what he's doing It understand what that is it's really an idiom and he used the ternary operator so I'll forgive him。

 but you don't want to overuse any of these fancy operators side effect operators。



![](img/1088af125e4434179802b6135f9e8637_11.png)

You can use these things， so count plus equals1 is the same as saying dollar count。Equals。

Dollar count。Plus one， this is just a contraction of this expression。And it's it's this。

 I would never use this。 I would not use that code right there。 I would use。

 but I do use it here in constructing strings because you tend to's there's code places where you start a string add something to it。

 add something to it， add something to it。 So one way to do is here you start a string and they want to add a blank to it。

 So you say out equals out dot at that's adding a space to the end。

And you're going to do this over and over。 You're going to say that over and over and over。

 so we can track this to be out dot equals world， and that concatenateates world to the end of it。

 and that concatenateates a new line。 And so that prints out this including a new line to go down there。

 So this is a way， usually this is a silly example。 But we use this to grow strings。

 know start a string， add a little bit more to it， add a little bit more to it。

 add a little bit more to it， add a bit and we use dot equals to kind of add to the end of the string。

And that I tend to use， I tend to like that， I tend to use that。Conversion and casting。

There's a lot of aggressive type conversion that happens， as I mentioned。

 you can also explicitly force it when you want to。

 it's actually something used more rarely in PhP than other programming languages。

 so let's take a look at some of the crazy things that are going to happen here。

 so we have some numbers division this division even though these two things are integers。

 the division produces。A floating point number， which is actually a sane idea。

Divisions that of integers that produce non floating point numbers like Python 2， for example。

 are not so logical。 This one's kind of weird。 This a plus operator is a numeric operator。36。

25 is a floating point number。 Tru is true， but then it gets converted to one to be numeric。

 and 100 is a 100 string， and that becomes。A number 100， so this is going to be 137。

25 and indeed it is， and that is not a syntax error。And you're going to look at Php and you like。

 that's bad。But you get used to it and you say，m。I guess I don't mind that that's a powerful capability as long as you use it wisely。

 this of course， is not wise。I'm just showing you what's possible right。

 so that's a bad line of code， but there you go。So here we're going to do concatenation with D。

Concatennate it。 That's a string operation。 So this is a number。

 but that it forces it to string automatically。 You could put parenthees string。

 That's a type that says convert that nonstr variable into a string。 And away you go。

 that's not too useful because the dots would have converted it to a string anyways。

 but you can take something like 9。9 and convert it to an integer。

 So that turns this to 9-1 and gives us 8。 So that's really a truncating conversion to integer。

And again， here we have a string added to a number。 But remember that this is a numeric operator。

 which means that it's going to force its operations to become numeric。

 So it turns out that what it does is it doesn't blow up Again， you might like it。

 You might not like it， but it turns that to 0。 And so Sam plus 25 is the number 25。

Sam concaten it with 25， that's a string operator， so that says， oh。

 I can convert this 25 to a string and so you end up with Sam 25 and it works out。Plus is a number。

Dot are strings。And so that part is pre consistent。If there's pluses。

 we're going to force them to numbers one way or another， including craziness。

 like the string Sam turning into a zero and so but the dot is for strings and so I actually wish more programming languages thought that way。

Programing language like Python tends to want to blow up， right？And so in PhP。

 we can add the string 100 plus 25 numerics， so that's 125。

 we can concatenate 125 and that gets 100 concatenated with 25。

And we can add Sam to 25 and we get 25 because Sam becomes zero。So in Python。

 we have to be explicit about this。 We have to say int 100 and then this converts it and then adds it and we get our 125。

 or if we want to convert if we want to concate and we want to concatenate。

 so we're using the same operator in Python to do the concatenation。

 but we do have to convert the 25 to a string so we cancatenate that and if we foolishly try to convert Sam into an inger we get a traceback and so。

This kind of tells you the philosophy of PhP in that it lets you do things in PhP that in Python are going to blow up。

 And in a way， this is one of the reasons that I like Python。

As a beginning language because it sort of keeps you on a very tight leash。

 you have to be very precise in what you're trying to do if you try to do something silly。

 it's going to stop you so you can say wait a sec， what did I do， why did I do that Oh。

 maybe I did you know this is silly， but what if that was a variable and you're like  oh that was a string I forgot。

 I forgot that they put sal in there sometimes。And so so it's helpful because this。

 while it can be frustrating to get a trace back， this can also inform you on what you've done wrong。

 whereas PP。Right again， responsible。It'll do what you say。

 even if what you say isn't the most logical thing， it'll do something。Casting， so true becomes one。

 I mentioned that。One of the most frustrating things that happens to be as a programmer is false becomes nothing。

 So if I take this dot again as a string operation。 So it's converting。

 forcing false to become a string。 When it force is true to become a string。 Tru becomes1。 So x1 Y。

 false is nothing。 So if you try to print false out with an echo statement。

 it's going to not print anything。 and that has driven me crazy on more than one occasion。

 because I'm like， echo this variable X and there's nothing。 Unlike it didn't get to that line。 Oh。

 wait a sec。 after 20 minutes， that was a false。 And that's why I'm not seeing anything。

 So you got a false doesn't print out well。So the equality operator as I mentioned earlier is aggressive type conversion operator where it triess to match the type conversions。

 so here' are some silly things that in many languages would blow up but in PhHP are totally cool so 123 is equal to the string 123 well that's because it's trying convert them and so it does and it finds that they're equal。

Here we've seen this， that just turns into 123， so that's going to work。Here this a little trickier。

 it's like， oh， false can become an integer zero and this becomes an integer zero， so yeah。

 they're completely cool。And this one here is really crazy。Five less than six is true。

Which becomes a one。And then the string2 minus the string  one。

 that turns into an integer 2 because minus isn't an arithmetic operator。 So that's 2 -1。

 which becomes 1。 And look at that。1 in one are equal。 So that is like。

That' is like literally the craziest line of code。To not， not the crazy line of code。

 but it's a very crazy line of code to not make a syntax error。 I'm not saying you should do that。

 I'm just saying that's the aggression that all these operators in PhP tend to have。

 Sometimes this equal sign aggression， we want to stop it。 And so we just say。Triple equals。

 and so this basically becomes true with no conversion and it's the same is true。

 and so they're still equal， but if this was like a one。

 that would be false because there the triple equal suppresses type conversion triple equals compared to Python is like is and is not。

Triple equals。Pretty much identical concepts。

![](img/1088af125e4434179802b6135f9e8637_13.png)

Okay， so。One of the things that happens is that the thing that gets you in trouble is anything that's numeric。

 false becomes zero。So anything in numeric false becomes  zero， and there's also null becomes zero。

Okay automatically， if it's in a numeric calculation。

 And so there are times where a function in particular， the string position。

 So the way string position works is it's looking for like one string。 So if I'm looking for ABC。

 And then I have this needle and it's a A it returns the position， which is position 0。 If it's a B。

 it would return1。 the problem is if it returns0， that means that it found it。

 And when it returns is it returns false if it didn't find it。

 So you have to be careful to know whether you found it at the beginning or you didn't find it at all。

 And so you read the documentation。 and it's warning you to use even in the documentation。

 it's warning you to use the triple equals operator。

 So that's how important the triple equals operator is in PP。



![](img/1088af125e4434179802b6135f9e8637_15.png)

And here's some simple examples of the stir post function。So here's this hello world。

 we're looking for the position of the at WO， which is 0，1，2，3，4，5，6， so that'll give us a6。

 we're looking for the string H E and that will be right there in position zero and then we ask where the position ZZ is。

And this is going to give us back a false。And we're concatenating that and you'll notice nothing prints out again。

 this is where I go crazy when I try to print falses out and they don't show up。

And this this is the mistake that you can make。 You can say if if the position of the H is false。

 Well this is going to find it， you think you're asking whether you found it or not。

 and this is going to be converted it to zero because the aggressive conversion of the equal sign and so this is going to print incorrectly Now if we're looking for Zz。

 this one's going to work okay because this is going to give us a false and a false and there's when you do type conversion。

 they still match， which is what you would expect。 but this is where you untpo。

 you have to use triple equals because if this returns a0 and it is not equal to false。

0 is not equal to false because triple equals suppresses type conversion and the same is true here。

 So all that says is read the documentation print doesn't show the false print R。

 which allows you to print even more detail， they never show up。 there don't show up at all。

 So there's lots of ways to try to print false and there's only one way that you can actually show them and that's the vardom。



![](img/1088af125e4434179802b6135f9e8637_17.png)

So up next， we're going to talk a little bit about control structures， if then else。

 and things like that。

![](img/1088af125e4434179802b6135f9e8637_19.png)
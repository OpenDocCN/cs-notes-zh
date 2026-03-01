# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P64：64_03_05_演示：Option枚举.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/aa5b1fba1b7e7b99cc3c4db69df502c0_0.png)

We have been working with inums and numerators to have their variants in rust。

 but we haven't dealt directly or intentionally so with option。

 so in this case we are going to be exploring a little bit more about what option is what can we do about it and why is such an important part of dealing with not only possible failures or possible problems and errors but also match and also the very important sum。

And some is also the the ability of creating an instance of an option。

 And we'll take a look at what that means in a second。

 Some is a also an en numerator that has a variant that wraps a value of some type D that sounds。

Pretty dense， but essentially what it means is that it can take any value。

 So actually let's if we take a look at option here and we go to where it's defined。

 we can take a look at what it actually means so it can return either a none or some value that will have T T is kind of like the basis of all the types in this case。

 it means it can return something。And I think that's a very good name now these might be very feel very disruptive if you were coming from a language like JavaScript or Python that doesn't have something that feels so generic and abstract like some。

All it is， this is an enumerator， an inum， it's an option and you are going to get a nonvalue or sum value。

 So now let's take a good look and go back to our main thats that is going to work with us so we have these function right here let's take a look at what we have what we're dealing with。

 we're going to take two arguments X and y they're both going to be integers of 32 bits and this function is going to actually be returning an option of I32s let's talk a second about what this actually means Yes。

 as you will see as you already seen and we've already covered we're going to return a type we' are going to say this function returns an option for sure but what we're actually saying in addition to that is that we're going to return an integer of 32 bits now because this is an option。

It is entirely valid to return a none， so this means that we're either going to return a none or a value that is actually going to be an integer of 32 bits。

This is very powerful because it abstracts away how we're dealing with errors and options and different situations that we might be in。

 So let's explore those situations in this block of code， we're looking at y and if y is0。

 we are going to say we are going to return a non now that might be weird because if you are thinking about an option in I32。

Integer， then this doesn't look like a none except because option implements none as one of its variances。

 This is entirely valid。 So this is a valid， this is valid because it is the other variant of option。

 So that's why I comment that added that comment here because it is important to understand that because none is part of an option part of like one of the variance of option。

 then it entirely okay to return none， even though none itself is not an option。 Allright。

 and otherwise， if y is not a0 is going to try to do a division。 So the division itself。

 it's being wrapped in sum。 So sum will take the result of x divided by y。

 And that is what increase the option I 32 value。 Now。You might also say well。

 but some is an instant is an instance of an nuator is going to return an instance of a numerator that doesn't look at like an option Well some the call will return will create actually an option itself and if we use the rust and Ler and Vicious Studio code kind of like facilities that we get with extensions and we to look at what we're getting here。

 the result of that operation is always going to be option I32 so behind the scenes。

 some is always going to return an option as well and we'll have to deal with and wrap in that option and trying to get that actual value so that is what this means and we're getting a lot of it is rather involved it can be a little bit dense but we went through what option is how can non be a possible。

And how come some provide an actual option Well， it will produce an option with I32 with an integer of 32 bits in length in size actually B return Allright so the implementation looks pretty straightforward if a is 10 and b is2 and then we call divide。

 which is our small function over here and we're passing both a and B。

 we're going to get a result and that result we can play with match If we get some value of x we're going to say well that's the value that's pretty good if we're going to get a none because we're saying hey y is it0。

 like we're going to get a none。 if we get a none， we're going say error division by 0 right so let's just run it out and we're going to get a5 that's great because we have 10 and2 so now we can actually say。

We can actually try this with0 and say let's look at what we have like oh perfect we are going to get error division by0 that is expected and that is the other the other situation where we might not get what we want so that is option and that is I32 and all of these all of these possibilities returning with sum or none because how they're related to the option a numerator one last thing I want to show you is that you are able you might see a dot nrap on something like result on anything that returns on option。

 you might see the unrap so let's take a look at how that would look it we say print line and we say result that unrap we are going to be looking at the actual value this is actually kind of dangerous because if we're going to get the nonvalue this will panic so use it with caution so if we run。

えっ？You'll see that we'll get a5 right here and the result of 5 is actually the match operation。

 So this is definitely possible and you can actually call unrap But if this becomes a zero。

 then we're going to panic right away so I'm going to run it and you can see there's the panic panic called option that unwrap on a nonvalue understanding these error messages and making sure that you feel comfortable looking at these。

Trace pack it's a very solid way of understanding the problems and trying to deal with them。

 especially if you are familiar with the types in this case we're dealing with option which is an numerator and we're going unwrap now a unvalue made it explode into into a panic so there you go that's a very solid way of diving into option and how it's an enummerator and what are the things that we can do about it。



![](img/aa5b1fba1b7e7b99cc3c4db69df502c0_2.png)
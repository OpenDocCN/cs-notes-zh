# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P34：34_02_04_演示：Rust条件语句.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/12351019f146fececa989102359f1d2c_0.png)

So lets let's start with here with maybe number， so maybe number is the result of Psalm 42。

 so this maybe number is going to be actually going right there。

 so it's then going to say if if it's not a none if it's a number。

 now number is a variable that is a on the fly like I'm naming that。It will will say well。

 the number is the number is this one and you can see here number is used right there。

 So if I use something else and I know like this might be slightly confusing if I say numbers and I save it immediately like this rush will not know what is going on like the local variable is not used so it is assign it on the fly and and then these executes because maybe number is going to be a 42 so let's just run these very quickly and see what we get so number is 42 that's perfect that's what we want and I'm going to close that and and that's a conditional that you're able to do so let's quickly change these and I have that commented out so if I say remove that and save it then we can try to run it again we don't actually need to to make it immutable and we're going to get a non here So that's good but we're getting an error So what's the error let me hover over the number。

And I get a fairly thorough error message let's see doesn't implement standard format display。

 the trade is not implemented for option In strings you may be able to use we are getting column and then the question mark so we can so what's going on here the problem is that if this is a none then we're not gonna be able to display like this and print lines so let's make use of the recommendation there and get it get it like that so we still have a problem here and maybe number is now with a under so typenotations needed for for what we have here so what is a typenotation is something that we haven't seen and I know I'm using a lot of syntax and a lot of terminology but let's just try to comply with what we are getting here from the compiler and what we're gonna do that is by passing that we're not passing that but like define that this column right here is going to。

Ensure that we're saying by the way， maybe number is of this type because behind the scenes。

 rust is not aware on how to do this with a sum none so here was easy because it was an integer and that's very straightforward with a compiler here we need to tell the compiler explicitly by the way we're gonna get an option and that's how this works so there you go like if we run this I think it's now going to be able to run and we're gonna to say the number is none well there's actually no number at all al right so pretty new concept you know being able to do an if condition by assigning also the result of maybe number that might be having this condition associated with it so it's just a different way of doing things you can certainly trying to do it differently but this is certainly。

Text that you should get used to in brass because it's not that uncommon to use it in situations where you want to assign it given an expression。



![](img/12351019f146fececa989102359f1d2c_2.png)
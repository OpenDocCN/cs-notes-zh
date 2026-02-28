# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P10：9_模块1 3 2 变量初始化.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/eacf0552c988fe344d6f106ca5dfe0be_1.png)

🎼う。🎼Yeah。So we're talking about variables and we're going to talk about how you initialize them。

 but first， let's finish up the types， so every variable has to have a type。

And you can make type declarations where you actually define an alias an alternate name for a type。

 so sometimes this is useful for clarity inside a particular application。For instance， here。

 where it could help you say you got some kind of application。And it's working on temperatures。

 temperatures are something that's manipulating， right。

 and every temperature you want it to be a floating point value，64 B floating point value。

 So you can define a new type or an alias for a new type type Celsius float 64。In that case。

 Celsius is exactly the same as F 64。You can always declare your variables to be float 64。

 but Celsius might make sense in the context of the application right maybe application is about temperatures。

 So maybe you want to rename it just to make it clearer for you as a programmer Also like the next one type ID number int maybe I want to maybe I'm making some code that implements a database of users or something and every user has an ID number So I know this this concept ID number。

 I'd like to I know it's an integer， but I want to name it。

 I want to give it that name ID number so that I know every variable that I declare as an ID number。

 it is an ID number。 I know something about it just based on the name of the type。

So once you declare a type like this type Celsius float 64， type IDdenum int。

 you can now declare variables using that alias so I can say var temp Celsius and now temp is going to be a flow 64 because 64 is just flow 64 is alias by Celsius Also var PD IDum PID is actually an integer but we call it an IDum and it makes sense more clear。

So initializing variable values， every variable has to be initialized somehow before you use it。

One way to initialize it is in the declaration itself。 so you can say var x int equals 100。

 and that will make x an integer。 It'll declare it as an integer。

 but it'll also set it equal to 100 or you can just say var x equal 100。 Now if you do that。

 you're not saying you want it as an integer So it will infer the type compilable infer the type based on the type of the righthand side value So the number 100 is an integer so it says。

 oh x must be an integer makes it an integer。Now， remember， sometimes。

This is an issue because maybe it infers something that you don't want， right。

 I like to specify myself， but maybe so for instance， say I say x equals 100。

 but I really want it to be a floating point， I mean 100 point。Something right。

 but I call it 100 because that's my initial temperature that I want。

 but I want to be a floating point value。 This will， if I don't specify， it'll say， well。

100 could be an integer， it'll infer as an integer。 And then if I try to set x to 100。1。

 I'll have a problem。 Now， so I'd like to specify the type。 But， you know， you don't have to。Next up。

 initializing after the declaration， so you can just say var x int。

 and then afterward you can say x equals 100 on a following line， and that's another way。Now。

 if you don't explicitly initialize a value， a variable， it will still get a value。

 It'll get the zero value for its type。 So， for instance， say I say var x int。

 the0 value for its type is0， right So x will be automatically assigned to a 0， initialized to a 0。

 if I don't say anything else。 if I say var x string。

 the zero value for a string is just the empty string。

 So x would be initialized to the empty string in that case。

Now another way to initialize variables is using a short variable declaration。Now in this case。

 you're performing the declaration and the initialization initialization together using the colon equals operator。

 so like there I up on the slide x equal x colon equals 100 okay。😊。

When you say that this is a case where x has not been declared yet。

 right so this statement actually declares X and assigns it， initializes it。Now the declaration。

 what happens is when you use that colon equal， the type that it sets it to be is whatever is on the right hand side。

 so 100 in this case。It says it looks at 100， says， oh， that's an int。

 and it infers x to be an integer。 and then it assigns it to the value 100。

 So variable is is declared as a type of expression， the type that's on the right hand side。

 So it does this type of short variable declaration。

 It does the declaration and the assignment together in one line with this special operator。

 You can only do this inside a function。 So you can't do a short variable declaration outside of function。

😊，That's not legal， so just know that。

![](img/eacf0552c988fe344d6f106ca5dfe0be_3.png)
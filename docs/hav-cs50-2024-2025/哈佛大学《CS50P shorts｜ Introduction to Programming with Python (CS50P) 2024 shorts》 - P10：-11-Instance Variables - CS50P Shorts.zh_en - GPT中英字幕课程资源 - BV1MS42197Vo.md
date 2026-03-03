# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P10：-11-Instance Variables - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/7b25470d5570a713bd45dd40288765bd_0.png)

Well hello Well and welcome to our short on Inst variables in a prior short on defining classes。

 we saw a way to create a class or a template for a package， one what we called in fact， package。

 and down below we created several instances of that class of that template to represent individual packages here。



![](img/7b25470d5570a713bd45dd40288765bd_2.png)

![](img/7b25470d5570a713bd45dd40288765bd_3.png)

![](img/7b25470d5570a713bd45dd40288765bd_4.png)

![](img/7b25470d5570a713bd45dd40288765bd_5.png)

So notice on 11 and 12 I have here some code that defines me two instances of this class that we called package It's be like me creating a template for something called a package and down below creating two particular packages Now I did so as follows I said down below that this first package has a number one the sender was Alice。

 the recipient was Bob and the weight here was 10 but what actually happens as we call like some code on my 11 well we said we come back to these lines3 through6 here so let's take a look at exactly what's happening。



![](img/7b25470d5570a713bd45dd40288765bd_7.png)

![](img/7b25470d5570a713bd45dd40288765bd_8.png)

![](img/7b25470d5570a713bd45dd40288765bd_9.png)

![](img/7b25470d5570a713bd45dd40288765bd_10.png)

![](img/7b25470d5570a713bd45dd40288765bd_11.png)

![](img/7b25470d5570a713bd45dd40288765bd_12.png)

![](img/7b25470d5570a713bd45dd40288765bd_13.png)

Well， when I will run some line of code like on line 11。

 I again am creating some new instance of this class I've defined called package and along the way。

 thanks to Python， this method called Dunder in it is called。



![](img/7b25470d5570a713bd45dd40288765bd_15.png)

![](img/7b25470d5570a713bd45dd40288765bd_16.png)

![](img/7b25470d5570a713bd45dd40288765bd_17.png)

Now we said here that it takes input self， which refers to the new instance of the class that we are creating。

 and it seems like what I'm doing here is taking in various inputs like number， sender。

 recipient and weight and assigning them to various attributes or properties of this class。

 of this instance of the class here。

![](img/7b25470d5570a713bd45dd40288765bd_19.png)

![](img/7b25470d5570a713bd45dd40288765bd_20.png)

![](img/7b25470d5570a713bd45dd40288765bd_21.png)

![](img/7b25470d5570a713bd45dd40288765bd_22.png)

So it turns out that each of these things， self number。

 self sender and so on are called instance variables。

 they're variables that belong to some instance of this class and they are defined for me whenever I call package down below So let's look at number for instance。

 number equals one Well I'm now passing in to D in it。

 this argument number with the value1 and what happens to that number one Well it actually gets assigned as an instance variable within this instance of the class so this instance here has a variable called number and so on for sender recipient and weight。



![](img/7b25470d5570a713bd45dd40288765bd_24.png)

![](img/7b25470d5570a713bd45dd40288765bd_25.png)

![](img/7b25470d5570a713bd45dd40288765bd_26.png)

![](img/7b25470d5570a713bd45dd40288765bd_27.png)

![](img/7b25470d5570a713bd45dd40288765bd_28.png)

![](img/7b25470d5570a713bd45dd40288765bd_29.png)

![](img/7b25470d5570a713bd45dd40288765bd_30.png)

![](img/7b25470d5570a713bd45dd40288765bd_31.png)

![](img/7b25470d5570a713bd45dd40288765bd_32.png)

Let's see this in action here， I'll come down below。

And let me try to actually access these instance variables that I claim I set up upon lines3 through6 Well I could imagine。

 let's say looping through every package that I have inside of this list of packages maybe printing them out along the way Well to do so I could use a for loop I want to print for each package I have so I'll say for package in the list of packages and then I'll throw this in a little later。



![](img/7b25470d5570a713bd45dd40288765bd_34.png)

![](img/7b25470d5570a713bd45dd40288765bd_35.png)

![](img/7b25470d5570a713bd45dd40288765bd_36.png)

![](img/7b25470d5570a713bd45dd40288765bd_37.png)

![](img/7b25470d5570a713bd45dd40288765bd_38.png)

![](img/7b25470d5570a713bd45dd40288765bd_39.png)

Notice first that package will first refer to the package on line 11 and then on the next iteration。

 the package on line 12。

![](img/7b25470d5570a713bd45dd40288765bd_41.png)

![](img/7b25470d5570a713bd45dd40288765bd_42.png)

So very simple here， let's start off by printing something， we could print the package as a whole。

 but I don't think we get a very good output， what I could do instead is try printing in this case。

 something like the instance variable that we called number just to start with package dot number。



![](img/7b25470d5570a713bd45dd40288765bd_44.png)

![](img/7b25470d5570a713bd45dd40288765bd_45.png)

![](img/7b25470d5570a713bd45dd40288765bd_46.png)

![](img/7b25470d5570a713bd45dd40288765bd_47.png)

So if I want to access an instance variable I can in this case refer to the individual instance of the class package here。

 followed by dot， followed by the instance variables is name just like we set up above in this case number so if I try this I'll try Python of packages dot pi hit enter we'll see one and two but just to hammer this home let me try and set one and three and now hopefully see one and three so it does seem as I defined in D in it。

 that the input to these various parameters of package these arguments here。

 they actually get assigned as instance variables of each instance of my class。



![](img/7b25470d5570a713bd45dd40288765bd_49.png)

![](img/7b25470d5570a713bd45dd40288765bd_50.png)

![](img/7b25470d5570a713bd45dd40288765bd_51.png)

![](img/7b25470d5570a713bd45dd40288765bd_52.png)

![](img/7b25470d5570a713bd45dd40288765bd_53.png)

![](img/7b25470d5570a713bd45dd40288765bd_54.png)

![](img/7b25470d5570a713bd45dd40288765bd_55.png)

![](img/7b25470d5570a713bd45dd40288765bd_56.png)

![](img/7b25470d5570a713bd45dd40288765bd_57.png)

Now let's try accessing more and maybe printing these packages in a more in a pretier way。

 so here I can do this， I go back to the format I had before。

 but now use a Python F string and the packages instance variables。

 I could say package and then package dot number just like this I were to run this。

 I could see package one and package2 pretty good what if I tried maybe the same format from before I could try colon and then I could enter in。

 let's say the packages sender two package dot recipient。



![](img/7b25470d5570a713bd45dd40288765bd_59.png)

![](img/7b25470d5570a713bd45dd40288765bd_60.png)

![](img/7b25470d5570a713bd45dd40288765bd_61.png)

![](img/7b25470d5570a713bd45dd40288765bd_62.png)

![](img/7b25470d5570a713bd45dd40288765bd_63.png)

![](img/7b25470d5570a713bd45dd40288765bd_64.png)

![](img/7b25470d5570a713bd45dd40288765bd_65.png)

![](img/7b25470d5570a713bd45dd40288765bd_66.png)

And let's see what we see here， Python packageages。pi， package1， Alice to Bob， packageage2。

 Bob and Charlie， and this is all happening by accessing these instance variables that I set up in Dunder in it as well。



![](img/7b25470d5570a713bd45dd40288765bd_68.png)

![](img/7b25470d5570a713bd45dd40288765bd_69.png)

![](img/7b25470d5570a713bd45dd40288765bd_70.png)

![](img/7b25470d5570a713bd45dd40288765bd_71.png)

Let's now add in the weight， I'll say comma package do weight and we said the weight was in this case in kilograms I'll go ahead and now try to run this again I'll go ahead and go back to my terminal pi than our packages do pi and we'll see a much prettier way of formatting these individual packages In fact we get the benefits of the strings we saw let's say in the short on defining classes which allows them to be more prettily printed。

 but we also get the benefits of this class here， so we have encapsulating information now using these things called instance variables。



![](img/7b25470d5570a713bd45dd40288765bd_73.png)

![](img/7b25470d5570a713bd45dd40288765bd_74.png)

![](img/7b25470d5570a713bd45dd40288765bd_75.png)

![](img/7b25470d5570a713bd45dd40288765bd_76.png)

This then was our short on instance variables and we'll see you next time。



![](img/7b25470d5570a713bd45dd40288765bd_78.png)
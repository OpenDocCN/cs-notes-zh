# 哈佛大学《R语言编程入门2024｜CS50R Introduction to Programming with R》中英字幕（豆包翻译 - P3：-3-CS50R - Lecture 2 - Transforming Data.zh_en - GPT中英字幕课程资源 - BV1Vw4m1e75r

嗯。

![](img/5fbdff023c27189e23ec53d7f4eda959_1.png)

![](img/5fbdff023c27189e23ec53d7f4eda959_2.png)

Well， hello one and all and welcome back to CSF's introduction to programming with R。

 My name is Carterzenki and in this lecture， we'll learn all about transforming data。

 we'll see how to remove unwanted pieces of data how to subsetter data and find certain pieces that we want to take a look at and ultimately how to take different data from different sources and combine it into one single data set。

 So let's go ahead and jump right on in Now why aren' you familiar with statistics or data science。

 you might have heard of this idea of an outlier or an outlier。

 some piece of data that falls outside some standard range Now here， for instance。

 a graph of average temperatures in January up here in the northeast United States。

 notice first on the y axis， I have the temperature in degrees Fahrenheit that's what we use up here in the US and then down below I have the day of the month。

1 through 31 and it seems to me like these bars represent individual days of the month and how high or low they go represents the average temperature on that day Now in the Northeast US it can get pretty cold。

😊，By default， kind of all the way down towards  zero degrees。

 but it could also get as warm as let's say 50 degrees or so it's kind of shown by most of these bars。

 but in this data it seemed like there are a few days that fell outside of that range like if I look down here on day two that seemed like a really cold day somewhere like negative 10 negative 15 degrees day4 seemed even colder like negative 20 or so and then day 7。

 that was really warm for January up here。 it was like 60 degrees or higher So it seems like these would be the outliers in this data set of temperatures and for one reason or another you might hope as a scientist did a scientist or a statistician to remove these outliers altogether and conduct some analysis without them involved So let's see if we can solve this problem of outliers now using R。

 well come back over here to our studio。 our old friend are ID or integrated environment that allowed us to write our code and to write our programs So we saw this function。

Last time called file。Create that allowed me to create a new file which I could write some R code so I'll go ahead and type that same thing here。

 file。create and in this case I'll call this one Ts tempemps。

 R for temperatures here and I'll hit enter and now I see true again which means this file was in fact created and if we saw last time I can go to my file Exper over here。

 which shows my working directory， the place I'm going to store these R files by default and I can click on tempemps。

 R now open it in what's called my file editor where I can write more than one line of R code。



![](img/5fbdff023c27189e23ec53d7f4eda959_4.png)

Now， as we saw last time， one thing you'll often want to do in R is read some data from some file and we saw these CSV files。

 comma separated value files that could store tables of data Well it turns out that R can also work with all kinds of other file formats。

 one of which is particular to R this is called a R data file and it turns out that using an R data file。

 you can store R's data structures like vector's data frames like we saw last time in a file itself such that when I load them。

 I just see exactly what was in the environment in terms of that same vector or that same data frame So let me try doing that and to load an R data file I can use this function conveniently called load。

So I'll type load here followed by some parentheses and now I could type the name of the R data file I want to open now my colleague。

 let's say it's given me a file called tempemps do r data。

 so I could open it using load tempemps do R data just like this and now let me run this line of R code I can do so if I type command enter on a Mac or control enter on Windows I could also click this run button here let me hit command enter and I'll see well nothing really。

 but if I look in my environment now if I open this other pane over here called environment I should actually see that I now have a vector called temps that seems to have 31 numbers as part of it here so why don't I try to find first off the average temperature in all of January and if I want to find an average I could use this other function called mean or often call an average a mean well I could type mean here。

And then give it the same vector temperatures。 If I run this line of our code。

 I'll hit enter and see the mean the average of the temperatures was 22。

74 roughly degrees Fahrenheit。 Now if you're not familiar with averages or means All I've done here is I've summed up all the values in this vector。

 and I have divided by the number of values that I have producing some kind of typical value of the data also called the average。

 So this then tells us that in January， it seems like our average temperature is somewhere around 22 degrees Fahrenheit。

 but that's not why we're here。 we're here because some of these data points seem to be a little anomalous。

 We had some really cold days and some really hot days and maybe we want to remove those days altogether before we run this temperature analysis。

 So let me actually take a peek at this entire vector I can do so by simply typing the name of the vector and hitting command enter to see it down in my console。

 and here are each of those 31。Values。So one thing you might notice is that I can see these outliers now in the data below。

 it seems like that second day that seems really cold。

 well that day actually had an average temperature of negative 15 degrees Fahrenheit and that fourth day that was about negative 20 degrees and same thing here looks like the seventh day was all the way up at 65。

 which is pretty warm over here。So one thing I want to do is actually pull out these outliers to use them in my code and we saw last time I could use this method of indexing into this particular vector that is trying to find particular values and pull them out to use in my code using their positions in this vector。

 Now it seemed like that second day was particularly cold so I could find that temperature by using temps bracket 2 where two represents that second element in our vector if I want to find it I could use bracket 2 and I'll see in fact I get back negative 15。

 same thing for the other one， I could use Ts bracket 4 and that shows me negative 20 that other outlier in our data set I could also use Temps bracket 7 and that would show me this really warm temperature overall in this same vector。

But this is where we left off last time and what I want to do now ideally is not have these outliers represented individually。

 but really have a vector or a list of those outliers to work with。

 and I'd argue that I don't quite know how to do that just yet。

 but I can show you one trick we can use an R to get back a vector from a current vector。



![](img/5fbdff023c27189e23ec53d7f4eda959_6.png)

So let's think through what we've already done。 We saw last time。

 If you wanted to get some element from a vector， we could use this same bracket notation that we even just now used。

 I could use bracket notation and say give me the second element inside of this temps vector。

 And this is known as indexing into this vector。 I take the position of the element I want to find put it in brackets。

 and I get back that very same element。 So again， temps bracket 4 negative 20 temp bracket 7 is now 65。

 but it turns out that cleverly in R， we don't always have to write a single index。

 if we want instead a vector from this current vector， maybe vectors includes only some values。

 I could actually give as the index， not a single index。

 but a vector of indexes and I could actually index into this vector using a vector of indexes。

 So let's take a look at that。 I could instead type something like this。 give me to4 and。

Those elements at these positions 2，4 and 7 and notice here I'm using this C function we saw earlier which stands for combine this mix for me a vector that includes2。

4 and 7 and now I'm indexing into temps using not a single value but a vector of indexes and what I'll get back is as follows I'll kind of mark these as the ones I want to grab and I will grab them out and turn them into their own vector for me to work with in R。

😊。

![](img/5fbdff023c27189e23ec53d7f4eda959_8.png)

So let's go ahead and try this transformation of this vector in R and see what we get back。

 I'll come back to my computer and I'll go back to our studio where we have our same temps vector。

 but now I don't want these individual values I want a vector of the outliers so I could modify how I'm indexing into this temps vector and I could use instead a vector to index into it。

 I want to get back those values at locations to4 and 7， and if I hit command enter here。

 I'll see I now have vector of those outliers。And that's pretty cool。 He me do a lot with this。

 But one thing I haven't done yet is remove them。 Like if I still look at temps now。

 I'll see that those vectors or those elements are still part of my vector I haven't kind of taken them out to remove them altogether together If I wanted to do that Well I need to take a different approach and one thing I can do in R is use a simple minus sign or a dash and prefix my C function here。

 my vector of indexes and what this will tell R is I don't want you to grab these I actually want you to remove them this minus sign says take the elements at these indexes and drop them。

 remove them from this vector。 So now if I run this line of code on line3 what do I see well all of my temperatures but you'll notice that I'm now missing some I'm missing those elements that were previously at positions to4 and 7 or those outliers So let's visualize this two one thing。

That I've done over here is I've said， I actually want you to remove these values。

 and I've done so by putting this dash in front of this particular index。

 this vector of indexes here。 And what R will now do is highlight these essentially and say， okay。

 I know you want to remove these particular elements。 And it will then return to me。

 give me back a vector that includes not those elements anymore。 It becomes shorter。

 so to speak just like this。😊，So now back in arm， I'm able to remove those elements from my vector。

Now let's come back over here and let's see what more we could do with this。

 Well one thing I wouldn't want to be in this scenario is the person who has to go through and find all of these particular outliers and tell me what their indexes are Like if I had to go through thousands of pieces of data and figure out which ones were the outliers and which ones weren't Well I'd kind of be wasting my time。

 What I'd love to do instead is really ask a question is this piece of data an outlier or is it not ask this yes or no question and it turns out that an R we can actually express those kinds of questions using a tool called a logical expression a logical expression Now。

 logical expression allows us to as programmers to express these yes or no questions and get back a yes or no answer in particular logical expressions often use what we're going to call comparison operators And here are a few of them here notice this one this double equal sign stands for equality allows to compare。



![](img/5fbdff023c27189e23ec53d7f4eda959_10.png)

Two values， a left one and a right one and ask， are they equal or are they not Now this next operator。

 this exclamation point equals that stands for not equals It will take a value on the left and a value on the right and say are these two values not equal and similarly if you the other one down here you might have seen this greater than sign and grade school。

 This one stands for greater than this one stands for greater than or equal to This one less than this one less than or equal to but this comparison operators allow us to compare different values and get back a yes or no response and actually true to their name。

 these logical expressions return to us what's called in R a logical where a logical is simply this value that is either true or false yes or no and so you'll see these values occur throughout your time in using R capital T R U E and capital F A LSE these represent yes or no true or false is this comparison true or not。

 Now you might also see them in。Of just T and F， This is like shorthand for these same logicals。

 But in general， you might often see true or false here。

So let's see if I could use these logical expressions to make my job a whole lot easier now as a programme I don't have to find these actual indexes going through data one by one by one。

 I'll come back to my code over here and why to go back to our studio。

 So here I have these indexes that I found by kind of combing through my data。

 but it would be nice if I could have R tell me whether some piece of data is outlier or not。 Well。

 one thing I could do is maybe try to find those temperatures that are lower than we'd usually see like less than zero degrees。

 below zero degrees is kind of this common benchmark ver it was really cold。

 So let's look maybe first at the first element in。



![](img/5fbdff023c27189e23ec53d7f4eda959_12.png)

This temp vector and asked the question， was that temperature lower than or less than zero degrees。

 and this is my first logical expression。Now if I were to run this line of code。

 hit command enter here， what do I get back well false。

 so it seems like Ts bracket 1 if I were to run this and show you what that actually is equal to， 15。

 15 of course is not less than zero。Now， what if I did it for the second one。

 I could ask that same question， Temps bracket 2， and then I could say one over here。

 and now I have true。 So it seems like temps bracket 2 is negative 15。 So in that case。

 actually let me change this this is not one。 it should be less than 0。

 So Temps bracket 2 less than0。 Ne 15 is certainly less than 0。

 I could keep going and ask the same question for Ts bracket 3 is temp bracket 3 less than0。 Well。

 it turns out it's not if I see tempemps bracket 3 down here。 looks like that value is 20。

So I've gotten some other way there， I'm able to ask these questions of individual pieces of data。

But I'd argue my job， my life isn't that much easier right now。

 I still have to go through all of these indices， Ts， bracket 4， Ts bracket5， and so on。

 and my job is still too right， lots and lots of our code to ask these questions。😡，Now thankfully。

 these comparison or these operators here， they allow me to actually give an entire vector as input。

 they're what we would call vectorized so I could on line 3 instead of giving a single value from this vector I could give it the entire vector and get back a vector in response I could run line3 command enter here and now I have a whole vector of true or false values these logical values。

 this is what's called a logical vector and notice here that for every element inside temps I actually asked this same question is this element less than zero is this element less than  zero and I see it seems like the second and the fourth R less than zero just like we saw in our data。

😊。

![](img/5fbdff023c27189e23ec53d7f4eda959_14.png)

So let me pause here and ask what questions do we have on these logical expressions and these logical comparison operators Can a list so a question about tuples in lists which are other structures we have in R tuples are similar to vectors but they actually store more than one storage mode。

 for instance， both numeric and character types， we'll focus more on tuples and lists a little later on。

 but not particularly right now though any other questions。

When you used the deletion operator with the minus sign is that modifying a resource data Good question So when I used that negative and I got back a vector that excluded some values。

 the question is did that kind of save as a new vector to change our environment at all and the answer is I get to decide that myself I go back to my code over here let me go back to what we did before where I had temps here as a vector and I decided to in this case access individual elements of it like to4 and7 I instead wanted to remove those if I wanted to actually update temps to remove those in future lines of code as well。

 I would need to reassign this vector I would say temps is reassigned in this case the exclusion of these particular indexes here so I'm first going to remove these elements to4 and7 and reassign it back to temps and now below this line of code temps will always exclude those values for me。



![](img/5fbdff023c27189e23ec53d7f4eda959_16.png)

A good question。Okay so we've seen how we can ask these questions in our code to determine which of these values are outliers。

 and in fact， we can use these logical vectors， these logical expressions。

 to actually figure out automatically at which indexes we had these particular values being true or false。

 we can use a function called which where which takes as input。

 this vector of logical values and tells me which ones are true or more particularly it tells me the indices of which ones are true。

Here I'll run line three， and I get back both two and4。

 so it seems like if I look at the logical vector itself， which was temps less than zero。

Notice how the second element of this vector is true， and so is the fourth。

 so if I were to use which， which would tell me at which indices is this logical vector true。

So pretty helpful。But I'd argue that I'm not really asking the question I wanted to ask like I wanted to ask is this piece of data an outlier and an outlier can be both low or high So here I've been focusing on outliers that are low。

 but I also want to find outliers that are high like let's say greater than 60 degrees。

 So for that I could use another logical expression like temps greater than let's say 60 And if I run or evaluate this logical expression。

 what will I see well I'll see false， false， false， false。

 but I will see true for that seventh day because that was a pretty high temperature there。

So there has to be a for me to combine， let's say， these logical expressions and ask the question I want to ask。

 and it turns out we can do so in our using what we'll call logical operators。

 logical operators let us combine two or more logical expressions to ask a more complex question in code。



![](img/5fbdff023c27189e23ec53d7f4eda959_18.png)

Now you might notice that I asked the question is this value less than zero or is it greater than 60 you often want to combine logical expressions with this idea of and or or and in fact R gives you a way to do just that here I have two symbols。

 one is the ampersand and one is this vertical pipe。

 the ampersand represents and I can combine two logical expressions and use an and between them with this ampersand。

 if I want to use or for instance I could use this bar here this represents or for me。

So for instance， let's say I wanted to ask a question。

 is this temperature below zero or greater than 60。

 I would put those two logical expressions on either side of this vertical pipe and the pipe would symbolize that if either of those expressions is true then the entire thing is true for and by contrast。

 both expressions on either side have to be true for the entire expression now to be true。

 and you can think of this a bit like English， something is only true if this and that are true as well。

😊，Now unlike our comparison operators that we saw earlier。

 these logical operators actually work differently for vectors of logicals and single logical values。

 so these single symbols， ampersand and the vertical bar， those work for vectors of logicals。

 if you have a single logical value that you want to combine between you need to use this double character set here。

 ampersand ampersand or vertical bar， vertical bar， these work for the single value， true or false。

 whereas these work for vectors of true or false。😊。

So let's try actually inventing now this encode to see if I can get at my question now。

 how can I find the outliers in this data set Well here I have my two logical expressions and I want to combine them to represent one larger logical expression Well as I said before I'm interested in whether temperature is below zero or or if it's above 60 just like this so this now is my full logical expression and I can evaluate it or run it if I do command enter on line3。

😊。

![](img/5fbdff023c27189e23ec53d7f4eda959_20.png)

And now I'll see， I've kind of combined my different expressions。

 I still see that these second and fourth values。 This expression is true for those。

 They are less than0， but I also see that on the element 7 here， that value is greater than 60。

 And so now that is true as well。 If either of these expressions is true。

 less than0 or greater than 60， I'll then see a true in this logical vector。

 And now I can go back to using which I could use which to figure out at which indexes。

 which indices these particular values are stored。So it seems like two， four， and seven。Okay。

 so I think we're making some pretty good progress here where we've gone from using individual indices to now using entire logical vectors to automatically find for us at which places we have this condition being true。

Some other functions to be aware of are these， one you'll to be curious about is this one called any。

Any any takes his input a logical vector and returns true if any of these values in that logical vector are true。

 so here I'm effectively asking not which values are outliers， but are any of them outliers。

 a yes or no question and I'll get back in this case， Yes， that some of these values are outliers。

 there are in other words， some values true inside of this logical vector。

I could also ask this question， are all of these values outliers kind of a nonsensical question at this point。

 but you might use it in other cases， are all of these？valuealues， outliers。

 I can give this function， that same logical vector as input， run this， and I'll see false。

 no not all of them are outliers， if any of them are false， I'll get back false。

I need instead for all of the values in this logical vector to be true。

 for all to return true as well。All right。So one thing we might be wanting to do now is kind of tie this up a bit and so I could try to find those values in my temps vector by now using these logical expressions。

 and I could write this followstemps bracket and then in this case let me go ahead and say which and then let me type in logical expression we decide on earlier。

 I'll say temps less than zero or temps greater than 60 and now will happen is first I'll evaluate this logical expression。

 finding all the values for which this expression is true。

Which will convert that into some set of indices， at which point I'll pass those into temps and now if I run line3。

I see my outliers without me going through the data myself。😡。

I could also decide to remove these values if I tried to use a minus sign here is try this out。

 and I should see that same result， but now just dropping or removing those outliers altogether。

But it turns out that which here is actually kind of redundant that R allows me to do the following。

 I could actually index into my temps vector using nothing other than a logical vector。

 and what R will do is give me back all of the elements for which this logical expression。

 evaluates to true。 I think it's worth visualizing this and we'll call this taking a subset with a logical vector。

 So let's imagine for instance， we have are vector called temps and our logical vector now called filter。

 for instance， and notice how the values both false and true and filter align with those values how they want to keep or remove in temps。

 the values want to remove well those align with false the values want to keep those align with true。

 So now instead of finding to temp some numbers， some inner to subset this vector。

 I could provide this logical vector instead filter just like this。

 and I'll mark those values by they're kept or remove aligning now with that true or。



![](img/5fbdff023c27189e23ec53d7f4eda959_22.png)

False value we saw in filter and once I complete this subset。

 I'll be left only with those values that aligned with true or those values I wanted to keep negative 15。

 negative 20 and 65 now I come back to our studio I will go over to my console and why don't I try just running this line of code as it is I know that this logical expression evaluates to a logical vector if I wanted to。

 I can make this more explicit， like me on the slides I could say my filter my filter here as if I'm trying to remove some values but keep others is this evaluation here and now inside of temps。

 I can put filter just like this and now if I run line3。



![](img/5fbdff023c27189e23ec53d7f4eda959_24.png)

Inside a filter is this logical vector， I can then use this logical vector to subset to access some elements of temp but not others。

 run line4， and now I get back to those particular outliers。Okay。Now。

 what questions do we have on these logical vectors and using them in this case as a way to index into or take a subset of our vector here？

Alright， so seeing none， let's go ahead and keep going and let's introduce one more thing here。

 So I promised that we would try to actually remove these outliers altogether。

 And one thing I've done so far is I've found the outliers and put them in their own separate vector。

 I haven't actually remove them。 Now， one thing that's helpful when you work with these logical expressions is the idea of kind of inverting the result you've gotten。

 if I get a true value， maybe actually want to get the opposite like a false value。😊。

Here I could do the following let's say I want to filter to only those temperatures that are actually not outliers this logical fashion here represents a element being an outlier I could though negate this and say I want to find a value that actually is not an outlier by putting in front of this。

 this exclamation point here this exclamation point means not it takes a true value and converts it to false or a false value and converts it to true so let's try this I'll run line3。

Just like this， and I'll update my logical vector now I'll run line4 and I'll see that now I'm actually getting access to only those elements that are in this case。

 not outliers so again this value， this exclamation point。

 this symbol allows us to take a logical expression that evaluates either true or false and neggate it。

 get the opposite of that， in this case true or in other case false。All right。

 let's see what else we can do， I'll come back to my R studio over here and one thing we also did is we kind of wrapped this logical expression in this case in parentheses。

 this allows me to treat the entire thing as one， notice how I had two here。

 one temps less than zero and one greater than 60 in this case though I wanted to negate the entire thing so I wrapped that in this case in parentheses。

And now I think we've kind of solved our problem we've gone from in this case using these individual indexes to creating in this case a vector that excludes those outliers altogether。

Now let's complete our analysis， I'll go ahead and try to save at this point a vector that doesn't include outliers。

 and I'll call it no outliers， so I'll go ahead and take my vector temps just like this。

 and I'll try to find again those values that were not outliers。

 I'll index into it using my logical vector。Temps less than zero or temps in this case greater than 60 and negating that that means that this logical vector is taking the opposite now and I could if I wanted to then find a vector of outliers just like this。

 temps and then bracket and then saying temps less than zero or temps greater than 60 now not negated and now I have two vectors。

 one that excludes the outliers and one that includes the outliers and now finally if I wanted to save these vectors here。

 I could use this function called save that similar to load allows me to create an R data file instead of loading it into my environment here。

If I type save。I can also then give save the actual vector I want to save to this R data file。

 I'll save， let's say no outliers， and then the next argument is one called file I could say file equals and then say no underscore outliers R data and if I run this line of code line6 I'll now have my file Expr this data our data file it says no outliers I' able to now save exactly as vector to my computer and same thing now for outliers I could save that one to a file called outliers R data as well and I would argue this is our entire program to open and load some vector to find those outliers and to remove them and now finally to save them to their own separate files。

 I could run this entire file with source up here and get all these results saved to my computer。



![](img/5fbdff023c27189e23ec53d7f4eda959_26.png)

Now before we move on， what questions do we have on these logical vectors or on this saving and loading of our data files we have if in the Yeah good questions so may have heard in other languages of these things called if statements so let you ask questions in other ways。

 we'll actually see those in a little bit as well。Let's take one more question here what kind of data files is the type R data is it like a CSV file or yeah a great question so a difference between a CSV file and an R data file is that a CSV file at the end of the day is just plain text you can open it and see the text you have in your data file separated by commas and R data file though lets us save an actual R data structure like a vector or data frame to a file and load it and put it back into our environment so an R data file is not plain text but it does allow us to save an actual vector of data a data frame and make it easy to load that data later on so R data files are particular to R and its own data structures if were organizing data like these vectors and data frames unlike a CSV which can be used across many different languages altogether。



![](img/5fbdff023c27189e23ec53d7f4eda959_28.png)

A good question。Okay， so we've seen here how to remove unwanted pieces of data and how to do so using these things called logical expressions up next we'll see how to take subsets of data and find pieces of data we're actually interested in and ask questions of that piece of data instead。

 see you all in five。Well， we're back and so we previously saw how to remove unwanted pieces of data like these outliers using these things called logical expressions up next we'll see how to apply those very same tools now entire tables of data defined some subset of that data we're actually interested in Now to do that when you need introduce this next data set which is a data set involving these very cute baby chickens and in particular we have a table of data here where each row represents an individual baby chick and how they grew up over two weeks of the very beginning of their lives。

Here notice how in every row represents a single chick and every column has some piece of data about that chick。

 so here line on column1， this chick column represents a number for each chick or identifying each chick uniquely。

Now this feed column tells us what kind of food that baby chick ate over the course of two weeks and then this weight column tells us how much they weighed in grams at the end of the first two weeks of their life。

 Not here how the feed column has food like casine。

 which is kind of like a protein fva which is like a fva bean if you're familiar and then the weight column has their weight in this case in grams。

 So in this case， chick1 seem to have eaten casine and weighed 368 grams at the end of the first two weeks of their life。

Now， one thing we'd be interested is figure out， well。

 what is the average weight of any given chick in this data， we could certainly do that。

 we could look at all of the values in the weight column and average those and comes the conclusion that the average chick weighed some amount But I'd argue it's more interesting to find how much each chick weighed depending on what they ate like how much。

 for instance， did the chicks weight casing way and how much did the chicks weight fva away and what does that tell us about which food is more nutritious for these baby chicks。

 So let's see how we can use these same tools of logical expressions now subset a data table like this and ultimately figure out these different averages across these individual different food groups。

 Let's come back to our studio here and I'll aim to create now a program that can subset this data and find for me the average weight of these chicks based on the kinds of food they ate over time。

 So why don't I create a new file here， I'll do so using。



![](img/5fbdff023c27189e23ec53d7f4eda959_30.png)

File do createate and I'll call this file chicks R for to be chicks that we're going to grow up and see how they do So now'll open my file Exper and I'll see I have this chi do R file along with a new file called chis do csv So my data in this table is stored inside of this file called chicks do csv why don't I go ahead and open this and I can do so in the same way we saw last time using this function called read do csv So I'll type read csv and the name of the file I want to open in this case chicks do csv and of course read csv will return to me a data frame that is a table of data that is now represented in R's own format I'll say that this data frame is called chicks and if I run line1 I'll now have that data frame stored in my environment pane。

If I want to view this， I could use that same function we saw earlier view and I could then give chicks as input and now I see I have my table of chicks and the various foods they ate So true to this slides here。

 we have individual chicks numbered to represent that individual particular chick we have different kinds of feed or food chicks were given I see cane。

 fva， linsed， which is like flaxsed if you're familiar。

 meat meal which involves various kinds of meat， soybean， the actual plant bean and sunflower seeds。

 and here we have our weight column Now I'll notice that unlike on the slides like below fva here。

 I do seem to have some NA values like the linsed values seems to be NA same with this one here。

 for chick 9 same for 11 and 12 Now these nas could mean a variety of things they might mean we didn't measure this chick。

 they might mean we measured it incorrectly it didn't want to include that data but regardless NA as we learned last time stands。

ForNot available， there could be some data point here， but there isn't。

 Soll probably need to handle that as we go through and do this analysis here。

Now I'll go back to my chicks。 our file and one thing I could do just off the bat is figure out how much to the chick's way on average across all different kinds of feed if I wanted to find that out。

 I could use the mean function as we saw just a little bit ago and then give it as input the vector representing the weight column in chicks and so here all I'm doing again is accessing the weight column of chicks which as we learned last time is a vector mean will take that vector and hopefully produce for me the average weight of these chicks。

I'll run line two， and I'll see。H or'll see N A。Well， let me go back to my data table again， I mean。

 I see NA values。But why do you think I would get an NA now。

 if I try to find the average of the values in the weight column。

 let me turn it over to our audience here， why do you think I would get N？



![](img/5fbdff023c27189e23ec53d7f4eda959_32.png)

If I have Ns in the vector of weights， I'm trying to find the average of。

 I think because it's eing the other values。

![](img/5fbdff023c27189e23ec53d7f4eda959_34.png)

Yeah， so it's kind of you might you'd say corrupting other values in some way or it's trying to maybe modify them in some way。

 Now， one thing in particular about these NA values is that they mean something special。

 there should be data here。 but there isn't。 And if you're doing statistics or data science。

 That's actually a really good indicator that you should make a deliberate choice about what you want to do about those values。

 you could remove them。 you could substitute some new value for it。

 But what you shouldn't do is just ignore them and treat them like they don't even exist。

 And so R has a way of telling me now， look， you have NA values here。

 you need to make a decision of what you want to do in order to actually compute what you're trying to compute。

So one thing I could do which shows most natural， I think for this case is simply remove those NA values and if I wanted to do that。

 I could actually use one of mean's other parameters which I learned documentation called NA。

 RM so recall from last time if I want this function have more than one argument I separate each with a comma I'll say comma here and then NA Rm equals it turns out from documentation。

 NA do RM is either going to be equal to true or false NA RM stands for whether I should remove Rm these NA values before I compute the average by default NA do RM is false I won't remove them but if I don't remove them mean won't know how to handle them and so can't compute the mean but if I were to remove them instead that is to make this parameter this argument true well then I would be able to compute the average because I will。

Have dropped or removed those NA values and then computed the average from the rest of those values that are in my weight column so let me run line2 here now that the NA。

 M parameter is set to true and I'll see that the average weight across all the chicks seems to be 28。

77 grams or so， so a healthy weight for these chicks。

Now what I argue was more interesting was the idea of trying to find how much the chicks weighed depending on what they ate。

 and we could use that to figure out what is the healthiest kind of meal for these chicks Well one thing I might be interested in first is how much on average the chicks who ate caing way。

But for that I'm going to need to only deal with the chicks who ate casing。

 so one way to do that would be to subset my data frame。

 only find the rows for which the feed column is equal to casing。

As we saw last time there is a way to do this based on the indices of this particular data of the rows here。

 notice how on the left hand side I have individual numbers for each of these rows。

 these are the indices of these rows if I wanted row1 I could use bracket notation and ask for row1 if I wanted row2 I could do the same thing so I'll go back to my chicks。

 R code and I'll try that as like a first step towards this I'll say chicks as my data frame and we saw last time that we can use a bracket notation to access individual values or elements of this data frame。

Now because the data frame is 2D， it took two values， one for the row and one for the column。

 two indices represent the position of the row we want and the position of the column we want。

 turns out that by convention， the row number comes first， followed by the column number separated。

 of course， by this comma。 So if I wanted the first row， I could do this。One here， that first row。

 and I want all the columns， so I'll leave this part blank。If I run line 3 now， what will I see。

 we'll I'll see just in this case， row 1。Now， like our vectors that we saw earlier。

 these data frames can take more than just individual indices as input。

 they can also take a vector of indices so let's try that I'll give in this case chicks。

 a vector of indices that will then return to me all the rows for which the feed column equals casine that seems to me just based on eyeballing here that it's these rows。

1，2 and3 so I could use the one，2 and3 here， create a vector of those values and then get back in this case。

 all three of those rows。 So now I have indexed into my data frames rows now using a vector and I've gotten back all the rows that I care about So why don't we call this one at least for now caing chicks why don't actually try to save this particular smaller subset of my data frame in this object called casne chis and now if I wanted to find the mean or the average weight for those chicks。

I could use mean， but then I could ask for the weight column from the Casne chick data frame。

 this subset of our previous data frame。So now I'll run line four。

 and I'll see that the casesne chicks seemed weigh significantly more than other chicks。

 379 grams on average。Now， what might we want to use now that we've seen how inefficient this might be。

 Well， as we saw before， I often don't want to use individual indices。

 You could imagine me that the programmer going through and trying to find， okay， well。

 one through three years caing，4 through six is Fva，7 through9 is  Lyseed。

 That's not how I want to spend my time。 There is a very minor movement I could make to this。

 which is as follows， I could actually。Represent this same vector with the following syntax。

 I could use one， colon 3。I've saved myself a few keystrokes and I've gotten in return the very same vector this colon here when it's between two individual numbers gives us a sequential vector。

 all numbers between one through three inclusive and I can prove it to you in the console if I ran this line of code down below one colon3 hit enter I'll see I get a vector。

 one through three inclusive maybe I could do the same for let's say the chicks that are eating Fva。

 well I could go four through6 and get back those particular row indices but。At the end of the day。

 I'm still actually defining the indices at which this particular condition is true。

 I could rely on something better。 I could probably rely on these logical expressions and use those instead。

So what kind of logical expression could help us out here？Well。

 we might notice that we really care about those chicks for which the feed column is equal to casing。

 so I could try to make a logical expression that involves this feed column of chicks。

 when don I try that， I'll go back to chicks。 R and now I'll try this logical expression here。

 chicks and the feed column therein。When is that equal to casing？

So recall that this is my logical expression and because one part of it includes a vector。

 I'll get back a vector of logicals of true or false values。

 let me evaluate this expression by hitting command enter。

 and now I'll see I get back this vector of true or false and it seems to me if I look at this vector over here that these first three values in the feed column are equal to true。

 true， true， true are equal to casing it's set in fact so true。

 true and true these are equal to casing， the rest though are not， they're false。Now。

 one thing to notice when you're working with data frames is that really these elements of this particular column called feed。

These kind of correspond to the rows of the data frame and if I go back to my visualization of my data frame。

 I might notice that the first three values in the feed column。

 well those correspond to the first three rows in my data frame and similar to vectors data frames can actually be subset with logical vectors so let's see how that could work here。

 and to keep in mind this relationship between the first elements of my column and the actual rows of my data frame。

 but I think we'll see how we could use these questions to help us subset this data frame。

Why don't we visualize it a bit like this where before we had seen that we had a data frame called chicks and we could access it using bracket notation entering in the indices for the rows or for the columns but if I had some separate logical vector like the one I just created and I called it let's say filter just for simplicity I might notice that all of those same truths and falses the way they align now with the rows of my data frame So here for instance this logical vector was created by comparing the values of feed with casing。

 those first three values were in fact equal to casing。

But the kind of revelation here is that these same elements now correspond to rows of my data frame。

 I could take this very same logical vector and put it into the place where I would actually ask for very the different rows of my data frame and I would get back the following something like this。

 I would mark so to speak certain rows to be kept at the end of this execution here and certain rows to be removed and I would ultimately end up with only those rows for which the logical vector evaluated to true。

 I would have， in fact， a subset of my data without touching any of the actual individual indices。

So let's try it and R I'll come back to our studio here， and I will do as follows。

 I will try to kind of prevent myself from using individual indices and I will instead use this logical expression similar to the slides。

 why don't I just call this logical vector filter just like this？And why don't I run line three？

Now I have in the case of filter。What do I have， I have a logical vector。

Now I could use this logical vector to index into to find a subset of my actual data frame here。

 if I use it instead of some individual indices to index into this data frame。Now if I run line5。

I'll have subset my data frame and if I run line6 now I'll see exactly the same result。

 and I can even show you what Casing and chicks looks like， let me show you it in the console here。😊。

OCI， in fact have the chicks that ate， in this case， Casing。I could change this filter， though。

 let's say I want the chicks to ate something like a linseed。

 I could use linseed here And now let me rename casene chicks to linseed chicks and find out how much they weighed。

 those chicks to eatte linseed。 I'll rerun my code top to bottom。 On line3， I'll change my filter。

 I'll get back a logical expression representinging those elements of feed that were equal to linseed and then on line 5。

 I'll go ahead and subset my data frame again。 and now I'll have only those chicks。

Only the chicks to ate linsed， and now could I find the mean if I run line six？

So it seems like the NAs are still involved here， I need to now do the NA。 Rm here。😊，Equal to true。

 I want to remove Z a values， and I could find on average how much the chickswelinsed weighed seems like it was 229。

Gms that is So let's go ahead and think through other improvements we could make to this program。

 Now， as I just saw， like I don't want to have to write NA do Rm equals true。

 every time I encounter these NA values， what I would love to do instead is actually just filter out these na values to begin with maybe load my data set but then as soon as I do remove all the rows that have an NA value for the weight column So for that I could probably still use a logical expression。

 and one that comes to mind might be something like as follows， let's say I want to figure out first。

 which elements of the weight column or really which rows in my data frame are equal to NA or let's say maybe not equal to So I'll do chicks here and I'll find the weight column of chicks and I'll ask the question which ones in this case are equal to NA so I can maybe remove them later on and you might notice that I get this little yellow。

quiggly sign and R and this little warning that says use is dona to check whether expression evaluates to NA。

 I'm going to ignore that for now， I'm just going to run line3 here and see what we get。I。

 I get a vector of NA values and this has to do with the fact that R really wants you to know that NA values exist if you have an NA value in your logical expression。

 it's going to make everything else NA because R wants you to decide what are you going to do with this NA value？

So it seems like this approach won't work， but thankfully。

 R does have other functions that we can use to be more deliberate about checking for in a values in some given vector or in some given data frame Now in R。

 these are known as logical functions function that can return to us a logical value and there are a lot of logical functions that are based on these special values we saw in last time you could imagine the is dot infinite function we saw last time was special value called infinite or in that allowed us represent a very。

 very large number you could use is infinite to test if some value is infinite。😊。



![](img/5fbdff023c27189e23ec53d7f4eda959_36.png)

You could also use as we just saw is dot NA is dot NA looked at some given value and returns true if that value literally is NA。

 if it's not， it returns false， same for is do NAN or is dot not a number， special value called NAN。

 well this test for that value and same for null， a special value called null we saw last time that will return true if we have the null value or false if we don't。

But I think the one we're going care about here is is dot NA so let's try that one out。

 I'll come back to my code over here and why don't I try to use is dot NA on this weight column in checks I can pass as input is do NA this particular vector。

 this column called weight and now if I run line 3 well I'll get back a vector of logical a logical vector and I should actually see which in this case elements of the weight column are equal to NA so it seems like mean I might want to use which here but it seems like one。

2，3，4，5，6，7， the seventh value seems to be NA maybe the later one two let's actually use which for this I'll come back to our studio and why don't I use which let's say which values which which elements of the weight column are equal to NA and I'll see that is fact seems to be the seventh9。



![](img/5fbdff023c27189e23ec53d7f4eda959_38.png)

![](img/5fbdff023c27189e23ec53d7f4eda959_39.png)

11th and 1， 12th and 18th rose in chicks。Now that seems helpful。

 but ideally like to find those values that aren't equal to NA and keep those instead。

 so if for wanted or to negate this expression here， as we saw before。

 I could use the exclamation point， this not operator that says if you gave me a false。

 give me instead a true， if you gave me a true， give me instead a false。

 so this will test which values are now not NA in that weight column。I'll run line3。

 and now we'll see we have more truths than falses representing all those values in our weight column that are not in this case。

 NA。😊，So if I wanted to subset this data frame， I could use the same kind of trick we saw earlier of realizing that these individual elements of this vector correspond to the rows of my data frame。

 and I could subset in this case chicks as follows。

 it'd say chicks and give it this logical expression which in fact returns to me a logical vector。

 and then use that logical vector to subset the chicks data frame to now only include those rows。

That in this case， have a weight that is not equal to NA。

Now it would be good for me to maybe save this as the most recent version of chicks now on lines  one and 2。

 I'm loading the chick data frame and I'm now saying immediately I'm going to remove any NA values in the weight column just like this。

 so now when I use mean later on I won't need to use NA。

M because I'll know that all those NA values in the weight column are gone for good。

Now there is one more way to subset these data frames as opposed to using this logical expression that is kind of serving as like an index into this data frame。

 there is actually a function called subset that works on data frames and takes both a data frame and a logical vector as input returning for us all the rows for which that logical expression is true。

 that logical vector evaluates to true。So let's try this， why don't I instead use subset here。

 I want to subset my data frame to only find those rows where weight is not equal to NA。

I could still use subset， I could use subset here， which means the subset function。

 and I could pass as the first input to subset the chicks data frame， and now as the second input。

 the second argument， I now need to give it a logical expression to evaluate to see which rows to keep and which rows to exclude。

Now one thing is I could say is not not is dona， so this means any row that is not equal to NA。

 and I could then give the weight column of chicks as input。

Notice here the syntax is a little bit different， I no longer need to use the dollar sign notation to actually access row the column of chicks。

 I instead to type in the column itself and this works because subset takes as input the data frame。

 it will assume if I say wait I'm talking about in this case the column in chicks。

So this should have the same result。 If I run line 1 and then line 2， if I view now chicks。

 I should see that all of those weights that were previously N are gone from my set。

 I could even use this， let's say later on to figure out how much， on average， the chicks who ate。

 Let's say， soybean way。 Why don't I use subset again。

 I'll make an object called soybean chicks just like this。

 And I will then subset the chicks data frame， the latest version of it。

 And I'll try to make sure that in this case， the feed column equals what we say soybean equals soybean。

Again， because I'm now using the subset function， I don't need to tell R that the feed column belongs to chicks。

 subset will do that work for me， I can just give the column name and ask where is it equal to soybean and now subset will return to me all the rows in chicks where this expression is true。

Let me run line four then and let's see what's inside of soybean chicks。

We'll see that now I have that subset of my data frame。

 and I could now run analyses like mean to determine how much on average did those particular chicks weigh。

All right， now one more thing to keep in mind is that if I were to view this chicks data frame just like this。



![](img/5fbdff023c27189e23ec53d7f4eda959_41.png)

If I'm being very astute， I might notice something a little bit off about it。

 so I have the individual numbers are presenting each chick here。

 but data frames in R also have what's called row names， individual indices for R rows。

 and if I wanted to find those row names， I could use this row names as a function。

 and I could run row names online for and these are the row names of this data frame。



![](img/5fbdff023c27189e23ec53d7f4eda959_43.png)

Now， if you're being a little observant， what do you notice now that we've run line two？

What might be missing from these？Indices of our data frame。One， two， three， four。



![](img/5fbdff023c27189e23ec53d7f4eda959_45.png)

Five， what are we missing in the end？I think it's NA or not available variables Yeah。

 so we're missing in this case all of those row names that previously corresponded to those rows that had an NA value in the weight column so we have one。

2，3，4，5，6 and where'  seven well  seven we saw earlier actually had an NA value in the weight column so we removed it。

😊。

![](img/5fbdff023c27189e23ec53d7f4eda959_47.png)

But it's really not good practice for me to actually have these row names。

 not now ascend one after the other in sequential order to have these missing values here。

So I need to reset them， and I can do that using a pet value that we saw earlier called null。

ll come back to our studio here。And if I want to reset the row names for this chick dataset set I could do as follows。

 I could not just print row names or see what they are。

 I could assign them some value and R has a handy trick where if I assign the row names of some data frame to be null capital N ULL that will reset them to count sequentially one up through number of rows we have Now null remember meant literally nothing there's intentionally no value at all here。

 it means nothing at all but when I assign this value to be the data frames row names。

 it kind of gets rid of them and r decides to build them back in so let's try this I'll run line4 and now I'll check on the row names again and I'll see that we're backed now being in sequential order So whenever you take a subset of your data consider updating the row names to make sure that things are standing just as they should and you have the actual row names。

Ascending order to index your data in this case properly。



![](img/5fbdff023c27189e23ec53d7f4eda959_49.png)

Now。What final questions do we have on subsetting these data frames？

What questions do we have So when you introduce the ECA function of course。

7 and in in conjunction with the witch function， we had the indices that had NA on them on the ways vector would we have an easy way to to count how many NAs we had in the vector because maybe if we had a bigger data frame。

 we would have like a hard time counting the number of indices that it returned No a really good question Bruno and so one thing wed be asking yourself is how do I figure out exactly how many NAs I had in the first place Well we can use a little handy trick of these logical values the true or false values which is that at the end of the day a true corresponds to a1 and a false corresponds to a zero so let's actually see this in action say we can actually count up our number of these true or false values I'll come back to our studio here and our question was。



![](img/5fbdff023c27189e23ec53d7f4eda959_51.png)

How many NA values did we have in the weight column of chicks Well we used remember is dot NA to test and see which elements of the weight column were equal to NA if I use is NA here I get back this logical vector and actually right now all of them are false because I actually I still working with the updated version of chicks that remove as NA values let me run line 1 which will reload the CSv and now let me run line 3 which now has those any values added back in now I'll see that some of these values are true that is there are some places in the weight column of chicks that are equal to NA。

Now a useful trick when you're trying to count up these kinds of values is to keep in mind that true underneath the hood corresponds to the number one and false underneath the hood corresponds to the number0 and I think if I were to do this if I were to do in the R console as dot integer this value true this would take the value true and show me it's true integer representation。

 let me run enter here， I see1 let me do as dot integer for false to see what it really is underneath the hood。

 that seems like it's a0 so I could take this vector of trues and falses。

And I could sumit just like this where sum will allow me to count up all the possible values in here and because true is always equal to1 and false is always equal to0。

 what I'll really get back is the number of trues that are inside this vector or the number of values in the weight column of chicks that were equal to NA so I'll run line3 and I'll see that there were five values。

5 values in chicks， they were equal to NA if I view chicks now I think we should see that we count for ourselves。

1，2，3，4 and then down below5， is actually five values of NA so you can keep in mind this when you're trying to count up your number of NA values that you might have。



![](img/5fbdff023c27189e23ec53d7f4eda959_53.png)

Okay， we'll take a quick break here and come back to talk more about how we can not just choose the subset of data ourselves。

 as programmers， but give the user more control over using which subset of data they want to see we'll be back in five。

Well， we're back and so we've seen so far how to take subsets of our data。

 but what we'll do now is turn more control over to the user and let them to the subset of data that they want to see Now R in general has this idea of a menu wherere present the user with some options they could choose from first if we show them our feed data we could ask them which subset of data they want to see Is it the casing subset。

 the Fva subset， the Lsed subset and so on and user could type in down below which number subset they want to see whether it's one for casing two for Fva or3 for Lsed So let's go ahead and input something like this in R now and show the user the subset of data that they want to see I'll come back over to our studio here。

 and I actually already have a program typed up here one that will implement a bit of this idea already So notice here how I have still reading in my chick do csv file and now we're moving any weights that are and just like we saw before。

 I'm now going to determine which options I should show to the user and I could do that using this function called uniqueique。



![](img/5fbdff023c27189e23ec53d7f4eda959_55.png)

Where I'll pass in the feed column of chicks and get back all the possible options that are inside of that feed column and then down below what what I do well I'll prompt the user with options using this new function we haven't seen yet called cat Cat actually concateate character strings and print them out all at the same time So here I'll cat or print the one dot followed by the first feed options probably caseing in this case then on the next line I will cat two followed by the second feed options which will be something likelinsed。

 let's say and I'll go through all of my possible feed options and at the very end I will ask the user to enter some feed type some number of the subset that they want to see so let's see this in action here I'll go ahead and go the top and click source now and。



![](img/5fbdff023c27189e23ec53d7f4eda959_57.png)

So some things seem to be working here I have actually the feed options being shown as I want them to be shown。

 but what I don't see are these options on new lines like I would rather have one dot space casing followed by two dot space fva not all of these on the same line So think we'll need some new character here to solve this problem in fact R does have a special character they can actually use to solve this problem in general。

 these kinds of characters are called escape characters and one escape character is this one here。

 backslash n which if I were to use it， it won't print out a backlash n to my console it will instead print out a new line and this backslash t well this is actually a special one too if I type backlash t I won't see backslash t I'll instead see a tab So these are helpful for us and in general these escape characters don't actually print out the way you type them they print out something special like a new line or a tab or something else。

Entirely for other escape characters too。

![](img/5fbdff023c27189e23ec53d7f4eda959_59.png)

So let's use now backslash n and see if that can help solve our problem I'll come back over to our studio and let me now add in this backslash n to each of my cat functions here I will also concatenate on each line this backslash n just like this and hopefully when I finish typing all this in I'll be able to see each of these feed options on some new line of my console here backslash n and backslash n and all I'm doing here essentially adding in some new lines to concatenate to each of my options so let me clear my terminal down below and I'll click source now and now I'll see that all of these options are on their own new line because what I'm doing is first printing out one dot then I'm going to print out the first feed option thenm going to cat or print out this backslash n to move to that next line here ultimately allowing me to see all of these options top to bottom。



![](img/5fbdff023c27189e23ec53d7f4eda959_61.png)

Now let's pause here and ask what questions do we have on either escape characters or this program so far as we concluded from the first two lectures。

 I think the programming with R is not safe enough because it saves arguments or variables then after it you can't it change it or you can't access the first element so how how we can program defensively。



![](img/5fbdff023c27189e23ec53d7f4eda959_63.png)

Was this available features Yeah， a good question。 And I like the way you're thinking。

 Like we need to think of how we can program defensively。

 And so one way to think defensively here is to think through what possible input the user could give us。

 if I look at this particular prompt I offer the user that they could type in one through 6 here But what if they typed in like a0 or a 7。

 like they could very well do that。 And so we'll see how we can actually handle those kinds of cases in a little bit。

 But first， I would argue that this， although it works isn't exactly the best design program we could write。

 I do have the right kind of menu for the user to see。

 But I could probably improve the design of my code2。

 So let's come back to our studio and think through how we could improve the design of this code using our's vectorized features So here if you notice on line9 through 14 like。

😊，There's no reason for to type all these lines of code。

 And if you find yourself ever accessing one element of a vector after another just to print something out to the screen。

 you could probably think to yourself there has to be a better way to do this。

 And in fact there is one thing that you might often think about is transforming your output to the user and turning it into a vector itself So here I have all of my formatted options in terms of individual lines of code。

 but it would be really， really nice。 if I had a vector of these formatted options and I could then pass that vector to cat for instance。

 Now cat can take a full vector as input and separate those character separate those elements with some character I tell it too Now for instance。

 I could if I had this vector called let's say why don't we call it formatted options。

And that is a vector itself， I could pass that vector to cat and tell it in this case to separate every element with a backslash n。

 and so long as this vector of formatted options included one for casing， two forlinse and so on。

 it would then be able to print all of out at once， separated by a new line。

 exactly what we just did， but now using only one line of code。Now the challenge is， though。

 how do I get these formatted options in terms of their own vector and how can I pass them in this case to CA Well I think we need another part of our program now。

 I'll say let's make a section to format， to format our options and to do so a little better than we did before。



![](img/5fbdff023c27189e23ec53d7f4eda959_65.png)

So I claim that ideally we want to create an object called formatted options that looks a bit like this。

 this object is a vector and it includes for the user all of their menu options。

 so this is six total options， each one here， one for casing two for Fva， three for  Lysed。

 and notice how I've kind of appended these numbers in each case， one dot space， the food option。

 two dot space， the food option， three dot space and the food option。

Now I'm kind of noticing a pattern in this vector here， which is that for the most part。

 every option I have begins with a number， one to six down here。

Then we have a period followed by a space in every element of this vector。

And then the next thing I see is we have whatever food option corresponds to this particular option。

 like casing， Fva， Lindsse or meat meal。Now when you're using R and you're using vectors。

 it really pays to think in a vectorized way， so I could actually think about this single vector as the combination of three different ones。

 these right here， maybe I have one vector of numbers， one through6。

 one vector of just that dot space， which I quoted here to show the space， in fact。

 one vector just those dot spaces and one vector which you already have of those feed options to show to the user。



![](img/5fbdff023c27189e23ec53d7f4eda959_67.png)

And it would be really nice if I had to function to basically combine these various vectors into a single one。

 take these three and concatenate them into one single list of formatted options。

Now you actually already know what that vector is， in fact vector not that vector that function。

 you know what that function is， that function is paste and its sibling paste zero paste can still work with these vectors but concatenate them now element wise。

 so let's try using paste to vectorize our formatting here and improve design of this code in R We'll come back to our studio here。

😊，And again， our goal is to create this vector called formatted options that has the number prefix2 each of our options to show to the user。

 Now， if I wanted to do that， I claimed we could use paste 0， but instead of giving paste 0。

 several individual options。 I could give it a few different vectors。

 So maybe the first vector to give to it is the number vector I want to first begin my input with those numbers。

 and so I could do as follows I could say one colon 6 that represents the number of the the vector。

 the number vector that I have if I go down the console here， I can prove to you that one colon 6。

 that is in fact a vector of1 through 6。OkayNow the next part was to incorporate that dot space in the middle。

 and I claim before I show you this that I can actually get away with not putting this in its own vector。

 but instead of putting it as a single value and R will repeat that value for me or recycle it for me as we'll see。

Then the third input in this case is the actual option that the user should see in terms of the feed options。

 So I'll type feed options here， which as we saw we down our console here is just a vector of the options we want to show the user。

 So visually what I've done here looks a bit as follows。 I've given input to paste0。

 these three vectors here。 one of numbers， one through6， one of this single element， dot space。

 and one of our feed options， Casing fva，linseed and so on。

 And when I concatenate all these together， I'll get back a vector of six elements element wise concatenating these here。

 So the first one seems pretty straightforward。 I'll take one concatenate with dot space。

 concatenate that with casing and I'll get back one dot space casing。

But the problem becomes what do I do on this next element well two concatenates with what turns out that R actually recycles this single value to the next element to a bit like this。

 so I now concatenate to dot space fva and I'll get to dot space fva I'll recycle this value again for Lsed getting three dot space linsed and recycle it again and again and again until I reach the end of the full length of these vectors here getting in the end my full list of formatted options so let'm going come back now to our studio and let me try to see what's inside of formatted options let me go over here。

And let me first run， let's say， line9。

![](img/5fbdff023c27189e23ec53d7f4eda959_69.png)

Let me now see what's inside of formatted options。

![](img/5fbdff023c27189e23ec53d7f4eda959_71.png)

And here we actually see our formatted vector of options to print to the user。



![](img/5fbdff023c27189e23ec53d7f4eda959_73.png)

Now， what questions do we have， if any， on how pace has now handled these vectors as input？

Our concatenation a little bit more flexible， maybe using the length of our feed options vector because maybe if we added another。

Chicks that ate additional foods。 maybe we could make it a little bit more adaptable so that is my question Yeah a good question I'm making our program more adaptable and flexible here。

 let's go ahead and try and implement that and see what it could do for us I'll come back to our studio here and let's go back to our program and I think you've rightly notice that if we ever had more then for instance。

 six feed options this would no longer work what's more flexible would be to actually dynamically fine the length of the feed options we have or how many we have in total and I could do that using this function called length just like this and as input to length I'll give this feed options vector and length were returned me now how many elements are inside of that vector For instance。

 if I go down to the console and show you what this evaluates2 I can clear my console here and type this in one colon length of feed options and I'll see one through6 but if the length of every7。



![](img/5fbdff023c27189e23ec53d7f4eda959_75.png)

8 or9 or 10。 I would get back one through7，89 or 10 making this more dynamic overall。

 So a great improvement to make here。 I think there's still other improvements we can make though。

 So if I were to run this program as a user and I were to enter the feed type I wanted to view like Casing well I don't actually see anything so I'll need to now figure out how to find the subset of data the user has asked for well if I go down to the bottom my program now I could write that write that piece of code and make a part here that says print selected option and I'll go ahead and try to find the subset of data。

 the user asked for Now they've given me a number like one，2，3。

4 however6 I'll probably need to convert that to the feed option they hope to see so why don't I make a new object。

 one called selected feed like this that will really take the user's number and convert it to the actual character representation。

 whether it's Cane orlinseed or so on to do that I could still use。😊，The feed options vector。

 which has of course our feed options prints as characters inside of them and maybe I could use as the index。

 the users number they selected because if they asked for number one。

 they want the first feed option or number two the second feed option and so on So here I'll index in using the user's feed choice and get back now they selected feed as a character and finally I could print out the subset of data they had asked for so I'll print the subsetd version of chicks where the feed columns equal to the user' selected feed just like this。

 So now my program hopefully work a little bit better if I were to save it and click source I'll now be able to type in let's say one and I'll see that subset that corresponds the casing chicks let me go ahead and clear my terminal again and click source and what if I did two well I'll see the Fva chicks that seems to be going pretty well for me。

But as we've talked about， I think it's worth thinking defensively here still。

 So if I click on source， what if I were being malicious as a user and I typed in something like this。

0。 What do we get。 I'll hit enter。So I won't see really a friendly output at all。

 I'll see this empty data frame and I'll also see zero rows or zero lengthth row names ideally I would show the user something different。

 something like invalid choice for instance， but to do this I think we'll need more tools in our toolkit I'll need to be able to respond to what the user has entered and take some other path in my program now thankfully in R we have access to what are called conditionals where conditionals let us run some piece of code conditionally depending on whether's a logical expression is true or false we have in particular。

 a keyword called if that will run some block of code if some condition or logical expression is true so let's try out this if keyword here and see if it could help us out in our program I'll come back to our studio and maybe before we decide to show the user。

 they selected subset What if I were to handle this invalid case I might do something like this。



![](img/5fbdff023c27189e23ec53d7f4eda959_77.png)

![](img/5fbdff023c27189e23ec53d7f4eda959_78.png)

Saay handle maybe invalid input and why don't I use this if keyword I'll say if。

 and then in parentthees I'll supply some logical expression， some condition that if it is true。

 I'll do some code that will indent and put inside these curly braces here。

 this body of our if statement。So what should my condition be maybe if the feed choice is less than1。

 so it's zero， negative 1， negative2 or so on， or let's say or the feed choice is greater than six just like this I think that should handle things for us and notice here we're actually seeing now this double bar for the or。

 because we're comparing now two single true or false values， not a vector of values here。

So what do I want to do if this condition is true， I want to tell the user that they entered an invalid choice just like this。

😡，Let's try it， I'll go ahead and click source now and notice how if I do enter a valid choice like one。

I don't see that line of code that says cat invalid choice because this condition was not true。

 if it's not true， I won't do the codes inside of these braces here。

But what if this condition is to I enter some number like0， when we try this。

 I'll click source and now I'll type0 and I'll see。WellI'll see invalid choice。

 but I still see that output I didn't want to see Now why is that Well if I go back to my program here and I read it top to bottom Well。

 it seems like if I enter zero I will print out invalid choice but then I'll still go on and show the subset that I didn't want to show in the first place so thankfully we do have other keywords that can make these conditions kind of mutually exclusive either do this or do that and these keywords look a bit like this we have one called else if and one called else So let's use these here as well。

 I'll come back to my program and what if I wanted to consider what I should do when the user enters a valid choice I don't want to print out invalid choice and I do want to print out the right subset So let's say in the case that the user has entered an invalid choice I only want to print out invalid choice and not these subset that they want to see。

 I'll type else here and I'll make this kind of mutually exclusive I'll take this code and。



![](img/5fbdff023c27189e23ec53d7f4eda959_80.png)

![](img/5fbdff023c27189e23ec53d7f4eda959_81.png)

Here and now what will happen is if the user enters an invalid choice like0。

 I will print out invalid choice， but I will not do the code that is now inside of this else block let me try it I'll click source and I will then type zero and now I'll only see invalid choice What if I did something else What if I did source and I did let's say one well now I see exactly the right input so these conditions here are kind of mutually exclusive。

Now we could use the else if keyword which lets us say else and then ask if some condition is true again。

 else if let's say maybe the feed choice is valid， I'll say feed choice is maybe greater than or feed choices is between let's say one so greater than equal to one and let's say the feed choice is less than or equal to six so between one and six inclusive this I would argue would still work we're going to first check if input is invalid and if it's not we're going to check if it is valid so I'll click source here and now I'll run top to bottom I'll type maybe0 and I'll see invalid choice if I do here maybe a1 I'll see the casesne checks as well。

But I think this is a little less efficient than simply having just an else here why well kind of logically if the input is not invalid。

 kind of has to be valid so why should I ask this question again if it is valid or not I could remove this if here and simply use an else but an else if is good if you still have one more question you want to ask if some other condition is not true let me go ahead and clear this here and go back to what we had before I'll click source and now I'll clear my terminal and actually let me get out of this program I' have a controltr C let me click source now I'll type1 for casing。

 see those chis and I'll type source click source again and I'll see zero and I'll see invalid choice So I think this is really the best designed version of our program yet we can handle these various cases of user input and show the user the input they want to see and now make use of these conditionals and so when we come back we'll see how to combine data from different sources way back in five。

We're back。 and so we've seen so far how to remove unwanted pieces of data from our data frames from our vectors。

 and we've also seen how to subset our data as well。

 Now we'll take a look at how it can combine data from different sources into one big data set。

 Now for this， we'll introduce the idea of an e-commerce kind of data where here let's say some giant like Amazon is trying to keep track of customers and the purchases that they made。

 So here in this table， every row corresponds to some purchase made on something like Amazon co。

 notice how every customer here has their own unique I。

 and one identifies me and one might ident you but at the end of the day。

 every customer has their own unique I。Now for every transaction， every checkout on Amazon。

 for instance， we might keep track of the sale amount， how much this user spent on Amazon。com。

 so it seems like user 9971， they spent $2 when they checked out。User 7，9，3，4。

 they spent $71 and so on。 Now， when you have lots and lots of this kind of data。

 it might actually not be stored all in one table。 might be partitioned across several different tables a bit like this。

 and it will be your job as the programmer to combine data from these different sources into one data set so you can answer and ask the questions you have about this data。

Let's come back to our studio and actually show an example of combining data from these different sources。

 So here in our studio I will create a program called sales I'm trying to combine sales data from different parts of the year I'll name this file sales R and I'll create it Now if I go to my file Explorer over here I'll notice that I have that program sales R。

 but I also have these four CSv files。 It seems like one is called Q1 the other is called Q2 and Q3 and Q4。

😊，Now we saw last time this idea of Q。Representing a question like in a poll given to some potential voters here。

 though， Q means something different if you're familiar with business。

 you might have heard of the fiscal year， kind of like similar to the calendar year。

 but the year in which they actually keep track of accounting and so on turns out that that year is broken down into four different parts called quarters。

 three months at a time。 So Q1 stands for the first quarter in the fiscal year， Q2。

 the second quarter， Q3， Q4 and so on。 So these are the four parts of the year of sales that this company had。

Now we were given this data in terms of each of those quarters。

 why maybe a colleague just gave it to us like that。

 we need to figure out how to piece this data together now， so let's open up sales。

 R and see how we could accomplish that task come back to my computer here and let me open up sales R and now let me see if I can first read in each of these individual data files maybe I'll call the first one simply Q1 for the first quarter the first three months of this fiscal year。

 I'll read the csv called Q1 csv and I'll do the same for Q2 Q2 csv the same for Q3 csv and now the same four Q4 csv just like this and now if I were to run all four of these lines of code top to bottom I could do so with source and I would see in my environment now I would see that I in fact have four data frames。

One for each CSV。Let's take a look at one of them， so I'll view Q1， view Q1。

 and I'll see the very same table we saw a little bit earlier。

 I'll see customer IDs in one column and sale amounts in the other remember every row here represents some purchase that was made from this commerce company。

OkaySo it seems like Q1 and even Q2 and even if we look at Q3 now。

 they all seem to have the same structure， the same number of columns。

 but perhaps different numbers of rows and this is helpful for us if we ever have data frames that have the same number of rows and the same names same number of columns and the same names of columns as these have we can combine them using a function called R bind R bind is typed like this。

 it's literally the character R and then bind and R does not stand for R the language it stands for row。

 row bind we're going to bind the rows of these very data frames into one big data frame。

So our bind takes as input several data frames to combine via their rows， I could first give it Q1。

 and then Q2 and Q3 and Q4， and now if I save this result in terms of its own object called let's say just total sales for the year。

 if I run this line of code on line 6 and I view let's say sales。

 I should now see that I have a really big data frame and prove it to you。

 let me go look at my environment over here。Let me make this a little bigger over here。

 so you might notice that on the right hand side I have Q1 and Q2 and Q3 and Q4 each one has about 2500 observations and now sales at the end has about 10。

000 observations or 10，000 rows， really it's the combination of each of these rows stacked on top of each other。

But I think it's worth visualizing to exactly what we're doing with ourbines let me show you some slides to depict just what we did here。

 I'll come back to our slides and show you let's take two example data frames。

 one called Q1 and one called Q2 that we want to combine by their rows using here Rb。

what happens when Rbin runs and takes in as input Q1 and then Q2 Well effectively it takes that first data frame it has and it keeps those rows at the top of this new data frame。

 but then it takes the new data frames like Q2 here and adds those rows at the bottom of this top data frame for instance。

 a bit like this notice how I took Q2 over here and kind of added it bound it by the rows at the bottom of Q1 making this one longer data frame I've done this here for Q1 and Q2 and Q3 and Q4 I can give as many data frames input to Rbine as I want all I'm doing here is adding row after row after row to make this data frame even longer so let's go back into our studio and let's see what is inside of my sales table here the entire thing I've lost a bit of information namely in which quarter each of these sales occurred like do they occur in quarter1 or quarter2 or quarter3。

Qu4 I don't know anymore， so we should probably be a bit careful about combining these and instead first maybe add a column to each of these data frames。

 maybe one called quarter that tells us exactly what quarter this sale was recorded in。

So in the Q1 table， maybe I'll add this column called quarter and recall from last time。

 if you want to add a column， we kind of wish it to quote unquote， into existence。

 I simply type the data frames name， followed by a dollar sign， followed by the call I want to exist。

 and then I assign it some value。Now， in this case。

 I would love for the quarter column to just sew Q1 for every single row。

 and if I want that to be the case， I need only type Q1 in quotes。

AndNow if I reread Q1 and run line 2 and now if I let's say view Q1， this data frame here。

 well I'll see I have a new column called quarter and throughout all the rows。

 I've set that column equal to Q1， so pretty helpful。

 but now if I go back to trying to combine these data frames。

 what might happen if I go down of line 8 now， I'll run line 8， and oops。

 I see an error in Rb which tells me the number of columns of arguments do not match。

And I think it's a little obvious what's happened here。 So Q1 now has three columns， but Q2， Q3， Q4。

 these other arguments to Arbin， those in this case only have two。

 so we need to make sure we're combining data frames that have the same number of columns we want to join them at least by row。

 So let's fix thiss go back to our studio and let's go ahead and just make sure that every table has its own column called quarter and that that column is equal to whatever quarter the sales appear in So Q2 for Q2 and then Q3。

Q3。For Q3。And then Q4。4 Q4 just like this Now I can rerun this code top to bottom using source。

 I see everything work just as well， and now when I view sales。

 I now have that other column called quarter that can only differentiate between individual quarters now of sales so helpful and when I combine these data frame to keep track of where each piece of data came from。

Now one kind of last flourish here if we can actually show us another new feature of R is going to be trying to categorize this data。

 so we combined it， but one thing I wanted to do is figure out which rows were particularly high value sales maybe my boss wants me to figure out which customers were spending the most money。

 well I ideally would want to create a new column and how it be based on the values of some other column。

For instance， let's say this is our table again， this one called sales。

 I still have the same customer ID and the same sale amount。

 but now I want to categorize this data to add another column that tells me whether a sale amount was a high value transaction or if it was just a regular one。

So this could look a bit like this， maybe I add this column called value for the value of this sale。

 and if it's over 100， I'll mark it， I'll flag it as high value， but if it's not， well。

 I'll just make it a regular old sale， and this could help me later on find a subset of my data that includes only those high value transactions and those customers who spent more money than usual。

So let's try to actually add in this value column and it turns out that to do so。

 let to make use of those same conditionals we just saw。 come back to our studio here。

 and why don't we try this ideally I might create some kind of logical expression on sales。

 I would say if the sales， the sail and out column is that greater than in this case。

100 And if it is well I want to create a column that has high value for those particular rows。

 otherwise just regular。 let me run this particular logical expression， line 15。

 and I'll get back this really long logical vector， I see a few trues in there。

 So it seems like there are a few rows where you just spent over 100。

But now my job is to create a vector that if this sale amount was greater than 100 shows high value。

 and if it wasn't， shows just regular。Well， I could use a conditional。

 but I could use special kind of conditional that R has one that works really well with vectors and producing vectors as well。

 this is called if else as a function now， if else can be a function and its first argument is going to be the logical expression to actually evaluate for every row。

 so here I have sales sail out greater than 100 and if this is true。

 my second argument to if else will be the value I want to see in the resulting vector。

So I want to see high value here， and the third argument will be what is the case that's not true else in this case。

 I want to see regular。And now， with these three arguments， if else will return to me。

 a vector where if this condition is true， I'll see high value。 If it's not true， I'll see regular。

 Let's try it。 I'll run line 15。 and now I'll see。A similar vector。

 but now all of those trues are replaced by high value and all of those falses are replaced by regular。

So it seems to me like this allows me to create some new column for my data frame。

 I could then assign this vector as a column in my data frame， I could say sales dollar sign。

 and then maybe I'll make a new column called we call it value before。

 I'll assign that vector produced by if else now to the value column in sales and if I run this line and now view sales just like this。

 I should see that I have this new column called value and if I were to sort visually by sale amount to those high value transactions I would see all of those now are marked as high value。



![](img/5fbdff023c27189e23ec53d7f4eda959_83.png)

![](img/5fbdff023c27189e23ec53d7f4eda959_84.png)

So we've seen here how to do a lot of things in this lecture， how to subset our data。

 how to use conditional take multiple paths in our programs。

 and finally how to combine data from different sources Next time we'll dive even deeper into functions。

 running some of our very own， we'll see you next time。😊。


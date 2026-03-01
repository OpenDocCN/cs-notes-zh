# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p47 47_04_05_哪些国家出口：代码翻译.zh_en -BV18U411U729_p47-

![](img/e3ce87b5a12624fdaf881db3d81aa52a_0.png)

Okay， now that we've developed our algorithm to figure out which countries export a particular item。

 it's time to turn that algorithm into code I'm here in Blue Jay where we've created a class and importededduu。

duke。star， which you've used for many things， an org。apache。coms。csv。star。

 which you've learned recently is what you need for the csvparser class。I've written a method here。

 list exporters， which takes in a CSV parser， so that's going to be the CSV parser that's already open for the file you want and a string for the export of interest。

 and I've written down comments here for the algorithm we just devised。

So the first step in our algorithm。Cha has a S typo in it said， for each row in the CSV file。

 you've already learned that that for CSV record is the type of item that you iterate over in the CSV file and we'll call it record。

From the parser。And I'm going to put curly braces around all of the。Steps that go inside of there。

And then we said， look at the exports column you learned before。I'm just going to call that exports。

 This is record do get and the name of the column you want in this case， exports。

Check if it contains export of interest。 So now we need to check and see if this this string export contains export of interest。

 One way we could do that， which you've seen before is export dot index of。Export of interest。

It's not equal to negative one。Now， if you were to look in the JavaScript String API。

 you could see that there's a little bit more readable and convenient way to do this。

With a method that just is called contains， these two will do the same thing。

 It's just a little more clear to someone reading the code。

 What you're trying to do if you write contains instead of index of equals negative one。

I' going to put that back where it goes。And then we said if so， write down the country from that row。

 so I need to first get the country string country equals and again I'm going to use record。 get。

Country。To get the country column from that row， and then if I want to write something down。

I would print it out。Okay， and then。My curly braces all match up。I'm just going to hit compile。

 It says it compiled with no syntax errors。 Now， as with other things。

 making a CSV parser in the blue Jay object workbench is a little complicated。

 So we're just going to make a method here to help us test this， which is going to be。Who exports。

Coffee。It's going to take no parameters， and it's going to tell us which countries export coffee from a particular data set。

 So I'm going to make a file resource。Which you've seen many times before。And as you may recall。

 if I create a file resource without passing in any parameters。

 it will pop up a dialogue to let me pick what I want to choose it from。

And then I'm going to want to get the CSV parser out of that。

That file resource has a way to give me a CSV parser， which will parse that file data。

 and then I want to list exporters from that parser。4。Coffee。And I'm going to compile this again。

It tells me invalid method declaration， return type required。

 I forgot to tell it what type it returns。 In this case。

 I don't want to return anything since I'm just printing things out。

 So I'm just going to write void there。And then I'm going to try to compile again。



![](img/e3ce87b5a12624fdaf881db3d81aa52a_2.png)

That compiled just fine。We're going to come over here。And I'm going to make a new one of my objects。

And I'm going to say who exports coffee？And then I have this export data。csv file。

Which is going to list a whole bunch of countries。Now we're trying to test out our code。

 we don't know if this is correct how would we know this。

 Well we'd have to go through that entire CSV file and check did we get everything that exports coffee that would be really tedious and is the whole point of writing the program in the first place so what we should and can do instead is write a much smaller file here's the one that we used in the slides and we can test our code on that instead。

 so if I come back here。

![](img/e3ce87b5a12624fdaf881db3d81aa52a_4.png)

![](img/e3ce87b5a12624fdaf881db3d81aa52a_5.png)

And I do Who exports。On this is export， small dot CSV。It says Madagascar and Malawi。

 which we know is the right answer， so that gives us more confidence in our code and we can be more certain that we got the correct answer on the larger file。



![](img/e3ce87b5a12624fdaf881db3d81aa52a_7.png)

So there's the code for that， and now you can do similar things yourself。


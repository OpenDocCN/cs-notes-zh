# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P40：39_map filter.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Let's say I want to generate a list using an existing list。

 The general process would involve applying some sort of operation to each element of the existing list and using those outputs to generate the new list。

 There are many ways you could do this in Python。 In this video。

 you will learn how to process a list with a map and filter functions。

 My file contains a list called menu， and it contains a list of various coffees。

 I want to filter this list for specific coffees。 Say。

 I want to print all coffees that start with the letter C。

 I will do this by creating a function through which I will pass the list to compare it to the letter C。



![](img/fb89cf3f0443695fe70a7221ffbbf194_1.png)

Then I will demonstrate how to get the output first as a map and then as a filter。Before I start。

 let me talk you through the format of a map function， but keep in mind。

 the filter function follows the same format to create a map。

 I type map and then need to define its arguments。The map function accepts two arguments。

 The first argument is an actual function。 In this case。

 it will be the function that I will use to match values based on a condition。

The second argument is the articles that will be passed through that function。In this case。

 the coffees from my menu list。Now， let's create the function with the condition。

I press enterter twice to move the map function down。I typeDeaf and the name of the function。

 which is Find Coffee。I then add a single parameter coffee between the parentheses and a colon after the closed parenthsesis。

The coffee parameter I added will be the coffee from my list。

I now need to check if the first character of the items in the list matches the letter C。To do this。

 I'll create an if statement by typing if C and passing zero to set the action on the first letter of the coffee variable。

I then typed the equal sign twice， followed by the letter C and a colon。I press En。

 and on the next line I typeReturn coffeeee if this statement is true。To use the map function。

 I'm going to assign it to a variable called Maap Coffee。

I follow that by entering an equal sign and the map。

Now I can pass in the arguments for the map function。 Remember。

 the first argument is the function itself。 I enter the function name find C。

It is important to note that I am not calling the function。 I am just passing it in like an argument。

 I add a comma after find coffee， and then the second argument， the article， in this case， menu。

Finally， I want to print out the value of map coffee so you can focus on the results in the terminal。

 I click on run and in the terminal， I receive a map object as output。😊。

The next step is to iterate through the map object。I type for X in Ma C， print out the value of X。

I click on Run again， and now I get the output as a map。😊，In the terminal。

 OIS appears with a lot of values that say none， except cappuccino and Cortado。

And that is because cappuccino and Corrtado are the two matches for the letter C in the function。

 The great thing about the map function is that I did not have to create a four loop to go through the list。

 The map function takes the function as an argument and passes the menu list values into the function one by one。

😊，So that handles the iteration for me， which makes it quite useful。Next。

 I'm going to demonstrate how to get the output with the filter function。To start。

 I'll comment out the section of the code related to the map function and clear my terminal。

The filter function works much the same as the map function。

I declare a variable called filter Cee and assign the filter function to it again。

 I add the two arguments， namely the Find coffeeoff function and menu。

Then I print out the variable filter coffee。I click on Run and receive a filter object as output。Now。

 I will iterate through the filter object， just like I did with the map object。

 I type for X in filter coffee， print out the value of x。I'll clear the terminal now and click Run。

This time， only cappuccino and Cortado are returned， Why is that？

Let me explain the difference between a map and a filter function。



![](img/fb89cf3f0443695fe70a7221ffbbf194_3.png)

A map takes all objects in the list and allows you to apply a function to it。

A filter also allows you to take in all objects in the list and runs through a function。

 but it creates a new list and only returns values where the evaluated function returns true。

 That is why there are no none values displayed in the output for the filter function。

 You now know how map and filter work in Python and should be able to also explain the difference between the two functions。



![](img/fb89cf3f0443695fe70a7221ffbbf194_5.png)

![](img/fb89cf3f0443695fe70a7221ffbbf194_6.png)

![](img/fb89cf3f0443695fe70a7221ffbbf194_7.png)
# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p26 P26 03_为参数指定默认值 -BV1QuJVzpEKE_p26-

![](img/70d50a46bbeeb985494885fab5202603_0.png)

When we call functions print and range， the number of arguments that we pass can vary。

If we don't pass an argument for every parameter， then the default parameter values will be used。

In this lecture， you'll learn how to define your own functions that use default parameter values。



![](img/70d50a46bbeeb985494885fab5202603_2.png)

Let's start by exploring health for function prints。Print has several parameters。 First。

 we pass the values that we'd like to print。Next， we pass the separator， which， by default。

 will be a space。 In other words， if we print multiple values。

 this character would be put between them。After that， we specify end。

 which is the string to be displayed at the end after all of the values have been printed。

And finally， optionally， we can specify the file， which is where the data will be printed and the default is to print a standard out。

Let's call print。If we don't pass anything， then a new line is printed， that's the end value。

Every print is a single value。Then that value is printed， followed by the new line。

If we print multiple values， then they're printed with the space between them and a new one at the end。

Let's print  one， two， three again。This time， we'll have Sap referred to two periods。

And end we'll refer to string， which is the exclamation mark。

Those strings are used instead of the default parameter values。Now。

 let's define a function that has a parameter with a default parameter value。

Willll define a function called every ink。The first argument will be a list。

 and the second will be an int。The job of the function is to create a new list with every8th item from the original。

Let's implement the body of the function。We haven't introduced default parameter values yet。

 so both of these function calls require passing two arguments。Now。

 we'll give parameter N a default value of one， and we'll add a third example to our dock string。

 which calls every n with only one argument， the list。Notice that the doctor has passed。

 We called it twice with two arguments and once with just one。When passing the second argument。

 we can also specify which parameter it being associated with。

For functions that have multiple default parameter values。

 using this notation is necessary in order to associate the argument with the correct parameter。

Let's look get a second example where the default parameter value is mutable。In this case。

 there's one parameter， and it has a default value of the empty list。

This function just dependss the string hello to the list， and then prints the list。

The first time that the function is called， the list contains one string， Hello。

 that's what we would expect。However， the second time the function is called。

 the list contains two hells。The third time it contains three hills。



![](img/70d50a46bbeeb985494885fab5202603_4.png)

As you've learned in previous lectures， the add greeting variable contains the memory address of a function object。

This function object has a parameter L。

![](img/70d50a46bbeeb985494885fab5202603_6.png)

And when the function definition is executed， L refers to the empty list。



![](img/70d50a46bbeeb985494885fab5202603_8.png)

The first time that addd greeting is executed， I refers to the empty list。

 But by the end of the function call， the list that I'll refers to is changed to a list with the string。

 Ho。

![](img/70d50a46bbeeb985494885fab5202603_10.png)

![](img/70d50a46bbeeb985494885fab5202603_11.png)

The next time that ad greeting is called， El refers to a single item list with hello。



![](img/70d50a46bbeeb985494885fab5202603_13.png)

![](img/70d50a46bbeeb985494885fab5202603_14.png)

And then Ho is appended to that list。 So the resulting list is a two item list。 Ho， hello。



![](img/70d50a46bbeeb985494885fab5202603_16.png)

The lesson to be learned here is that default parameter values are assigned at the time of function definition。

When the function is called， any changes that the function call makes to the mutable objects persist from one function called to the next。



![](img/70d50a46bbeeb985494885fab5202603_18.png)
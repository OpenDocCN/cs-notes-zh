# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p146 26_04_03_零阶与一阶模型.zh_en -BV18U411U729_p146-

![](img/4817d9bd627f3edbd4c072067e1aca41_0.png)

Hi， in this lesson， we're going to walk through creating the class that generates text at random。

 using an order 0 Markov algorithm。 We'll also describe what changes you'll need to make to create an order 1 or more Markov class。

 Order 0 is straightforward to program and will be a model for other Markov classes。😊。



![](img/4817d9bd627f3edbd4c072067e1aca41_2.png)

![](img/4817d9bd627f3edbd4c072067e1aca41_3.png)

![](img/4817d9bd627f3edbd4c072067e1aca41_4.png)

All Markov models will use a training text as the basis for generating text at random。



![](img/4817d9bd627f3edbd4c072067e1aca41_6.png)

In an order 0 model， we don't use any characters to predict the next character。

 We choose every character at random from the entire training text。 You can see an order 0 text here。

 Words are long and letter combinations don't always make sense。

 It's hard to pronounce words like tima， for example。Or Dmo。In an order 1 Markov model。

 we choose a character based on one previous character。

 This makes letter combinations more common than an order 0 model， as you may see here。

 where words like best are created randomly and words are easier to pronounce。

 even where they are words like Stard。😊，Anco。We'll provide a quick overview of developing the Markov Zero class and you'll be able to use it to generate text randomly。

We'll think about methods first。 Sometimes this is called the class's behavior。

Thinking about methods will help as we think about what state or instance variables are needed。

We'll need to be able to set the training text for the Markov0 class。

 and we'll need to be able to generate text randomly。



![](img/4817d9bd627f3edbd4c072067e1aca41_8.png)

That's two different methods。We could combine these into one method， but in general。

 keeping methods single purpose is a good idea。In this case。

 we might want to create several texts at random from the same training text。

 So keeping the methods separate makes lots of sense。First。

 we'll look at setting the training text in Markov zero。



![](img/4817d9bd627f3edbd4c072067e1aca41_10.png)

The training text is used when generating random text。 As we mentioned earlier。

 we might want to create several texts at random from the same training text。

 This means we'll need to store the training text in an instance variable。



![](img/4817d9bd627f3edbd4c072067e1aca41_12.png)

The instance variable is assigned a value when the set training method is called and then accessed when text is generated at random。

The other method we'll design and implement generates text at random。



![](img/4817d9bd627f3edbd4c072067e1aca41_14.png)

The get random text method will choose a character at random from the training text。

We'll use the next int method from the class Javautil。 random to create a random index。

And we'll use this index to access the training tax for a random character。

We'll create a string builder object to store the random text since adding or concatenating to a string builder is efficient。

We'll append to the string builder object and we'll use the two string method to return a string when we're done。

We'll also need a constructor and perhaps other methods in the Markov zero class。



![](img/4817d9bd627f3edbd4c072067e1aca41_16.png)

Constructors typically initialize fields or instance variables。In the Marco Zero class。

 we have an instance field that stores a random object from the Java U package。

We create a new random object in the constructor。It's also useful。

 often useful to generate a reproducible sequence of random numbers to help with debugging。

 We can do that by setting what's called the seed of the random number generator。

Which we do here in creating a new random object。 This may help as you debug the Markov classes。

There's also an instance field， my text that's not initialized in the constructor。

But is by the set training text method we discussed earlier。

This is enough background to write and test the Markov0 class。

 but we'll provide some guidance for Markov1 as well。

We have a test program named Markoff Runner to test the Markov Ze class。

The user selects a file to use as the training text。

The code in Markov runner replaces each new line character with a space。 This preserves words。

 which might be separated by spaces， but doesn't treat new lines asspec。😊。

The Markov Runner class creates several examples of random text from the same training text。

What will change when you develop and use Markov one？You'll use the same method。

 names and the same state by using the same method names that the Markov runner test class can be used to test Markov1。

 as well as Markov0。You'll need to change the gett random text method。

Since one character is used to predict the next character in order one markov text generation。

We'll provide a quick overview of the concepts in Markov1。

 You'll see more of the algorithmic development in a later lesson。In an Order one Markov model。

 one character is used to predict the next character at random。In this diagram。

 we see that the letter A follows the letter T 12% of the time。

But the letter Y follows 7% of the time。This means if we generate a T。

 then we' more likely to pick an E than an R next。 And both of those are more likely than picking an A。

 according to the probabilities shown in the diagram。



![](img/4817d9bd627f3edbd4c072067e1aca41_18.png)

The training data is used to create these probabilities。

But we don't actually create the probabilities， which would be possible。

 but more difficult and unnecessary compared to the method you'll use。

You'll write code to every T in the training text。Each time， a tear is found。

The next character is added to a list that represents the characters that follow T。For example。

 we might find the letters A， E， A， R， A， E， and Y after the first seven teeths in the training text。

Choosing from this list will be the same as using the probabilities。

 since there will be more ease in the list than wise。

We'll develop this algorithm using our seven step process， happy programming。


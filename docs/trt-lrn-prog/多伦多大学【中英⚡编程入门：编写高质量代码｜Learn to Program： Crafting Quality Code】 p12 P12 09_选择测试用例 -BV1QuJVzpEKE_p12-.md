# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p12 P12 09_选择测试用例 -BV1QuJVzpEKE_p12-

![](img/47dccc4bf75c0da3335c186817b6983c_0.png)

In earlier lectures， you learned how to execute test cases using Doc test and unit Test。Thirdly。

 test your function， how many test cases are needed？And which test cases should you choose？

The answers to those questions depend on the function being tested。In this lecture。

 you'll learn how to choose test cases。

![](img/47dccc4bf75c0da3335c186817b6983c_2.png)

The first function that we'll test is called count lowercase vowels。

It's similar to the count vowels function that you've seen before。

 except it only counts lowercase vowels as opposed to both lowercase and uppercase。



![](img/47dccc4bf75c0da3335c186817b6983c_4.png)

This function takes one argument， a string， and it returns an int。



![](img/47dccc4bf75c0da3335c186817b6983c_6.png)

To test the function， we need to pick values for the string argument and then call the function to make sure that it returns what we expect in each case。

It's not realistic to test this function with every possible string argument。Instead。

 we group the strings into relevant categories and then choose one representative string from each category and test with that argument。

When choosing the string argument， we need to consider the length of the string and the characters that make up the string。

There are many， many options for string lengths。 For this problem， We'll use three lengths，0，1 and 6。

 And these will represent the empty string， single character strings and strings with more than one character。

Now， which character should we use for this problem， We are counting vowels。

 So we're going to pick the characters that we include in the string based on whether they are vowels or non vowels。

The actual character doesn't matter If we want a non vowel， we could use B， N。

 the question mark or any other character that is not a vowel。Let's make a table of the test cases。

We are going to have three columns， the value of the argument to the function。

The expected return value of the function， given that argument and a description of the test case。

The first test case will use the empty string as the argument to the function。 In this case。

 we'd expect the function to return 0。 since the string doesn't contain any vowels。Next。

 we'll consider strings of length1。For the first string， it will contain a vowel。

 and the second one won't。In the first case， we expect the function to return  one。

 and in the second case， we expect the function to return 0。Next。

 we need to choose test cases for longer strings。Like before。

 we pick the characters to include based on whether they are vowels or not。

We're going to use three longer strings， a string containing no vowels。

 a string containing a mix of vowels and non vowels。And a string containing all vowels。Also。

 for the string containing all vowels， we're going to include all five to make sure that each vowel is counted。

Now that we've chosen the test cases， you can implement them using unit Test。Next。

 we'll choose test cases for the I palindrome function。



![](img/47dccc4bf75c0da3335c186817b6983c_8.png)

This function takes a string and returns a booleion。



![](img/47dccc4bf75c0da3335c186817b6983c_10.png)

Because the function returns a boolean， we need at least two test cases。

 one that causes the function to return true and another that causes it to return false。

 But it turns out that we need quite a few more than two。Once again。

 we need to choose different values for the string argument that represent different categories of strings。

The categories are going to be a bit different for this problem。For the length。

 we still consider length of 0，1 and longer。In， when we developed our algorithms for iselindrome。

 we found that whether the length was even or odd， impacted our program。

 So we'll consider even an odd length as well。Here are the lengths that we'll consider。

We're going to consider strings of length zero and strings of length1。

Both of these are considered palindromes because theyre read the same from front to back as from back to front。

Stngths of length do are interesting because that is the length of the smallest possible non empty。

 even length palanddrome。And of the smallest possible， non palindrome。

Strings of length three are also interesting because that is the smallest possible。

 multiple character， odd length palindrome。We'll also use a string of length six to represent longer strings of even length。

And a string of flank 7 to represent longerger strings that have odd flanks。

Now let's pick the actual strings to use。We'll use the empty string and the string with lowercase A to represent the strings of length 0 and those of length 1。

 And both of those are palindromes。For strengths of length two。

 we'll consider one that's a palindrome and one that's not。Next， we'll consider strings of length 3。

Again， we will use a string that is a palindrome。And this is the shortest multiple character string that is a palindrome。

We'll use A BA。And then we'll use ABC as a three character string that is a non palindrome。Next。

 it's time to pick longer strings with even length。Will use redder to represent longer。

 even length strings that are palindromes and renter to represent those that are not。

And last but not least， we need to pick longer， odd length strings。

 one that is a palindrome and one that is not。Here are some general tips for choosing test cases。

We should consider size， dichotomies， boundaries and order。

There is overlap between these different considerations。

 so that test cases you develop are not necessarily going to fit into just one of these categories。

Let's consider size。For collections such as strings， lists， tuples and dictionaries。

 Test with the empty collection， a collection with one item。

 the smallest interesting case and a collection with several items。Consider dichotomies。For example。

 vowels and non vowels， even and odd。Positive and negative。Empty and full， and so on。Also。

 consider boundaries。If the function behaves differently for values near a particular threshold。

 test at that threshold。Also， consider order。If a function behaves differently when the values are in different orders。

 identify and test each of those orders。

![](img/47dccc4bf75c0da3335c186817b6983c_12.png)
# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p95 29_03_01_简介_3.zh_en -BV18U411U729_p95-

![](img/8d3411bb7cebbb18b0b370f873d23ee2_0.png)

Now that you've learned about array lists， it is time to work with the Gladlib Java program。

 You'll learn how it works and how to modify it to create stories with new kinds of data。

 you'll need to understand the program so that you can modify it as a programmer or software engineer。

 sometimes you'll be creating programme from scratch。 and sometimes you'll be modifying program。

 enhancing them， making them more robust and more in this program， there are many pieces。

 Many methods， each of which you could write yourself。

 This means you'll be able to understand each method and be able to modify the program in different ways。

 Since you'll start with a working program， you'll be able to make improvements and additions while testing your program to see that it continues to work correctly you'll be able to understand class design。

 method design and the limitations of the Gladlib Java program you start with as you make improvements to the code。

😊。

![](img/8d3411bb7cebbb18b0b370f873d23ee2_2.png)

![](img/8d3411bb7cebbb18b0b370f873d23ee2_3.png)

![](img/8d3411bb7cebbb18b0b370f873d23ee2_4.png)

As you work to understand these aspects of software design and engineering。

 you can tell stories about it。As you modify the program。

 you'll be creating reusable program components and reusable ideas that you'll be able to use as you develop software experience and expertise。

😊，We'll take a tour of the program before you begin to make enhancements and improvements。

As with all Java classes， a constructor will initialize a GlaAlib object。

 the constructor will create the array list instance variables that hold replacements for nouns。

 colors and more， it will also create the Java。util。

 random object used for choosing a replacement at random。

The general control flow of the program after initialization will be to read a story template and process each word if the word is a label like country or time frame indicated by angle brackets。

 the code will find a replacement at random。After the story is created， the program will print it。

 Let's look at these pieces in more detail。First， let's take a quick look at creating stories from the template you just saw。

There is one public method in the class make story。

 calling this method will use a template to generate a story。

 as we'll see when we look more closely at the code。In Kenya， a long time ago。

 nearly 245 decades ago， there lived a pink， funny tiger。 It's so love to sing and dance。

 But there was an angry， gigantic lion named Lance that scared it so much。😊，In Ecuador。

 a long time ago， nearly 105 months ago， there lived a jovial， yellow polar bear。

 It's so loved to sing and dance， but there was a furious。

 angry rabbit named Albert that scared it so much。😡。

Reading words from the template and printing the story will be code you likely won't need to modify Call make storyory will read a template from a file or URL and loop over each word in the template。

 If the word is a label with anglegle brackets， it will be replaced。

Finding labels is a straightforward use of dot index of and dot substring in the private method process word we use these methods to ensure that punctuation or letters before and after the angle brackets are preserved。

Printing the story will display the final result in the console window of Blue Jay or a different programming environment。

The private method print out has a parameter to specify the line width so you can create a story and use 80 or 40 characters or any other number。

You could modify the printout method to write the story to a file too using theedduu。duke。

 file resource class。Changing the GlaDlibb。 Java program requires understanding how the array list instance variables are used。

 there is one array list for each possible label in a story template like noun or color。



![](img/8d3411bb7cebbb18b0b370f873d23ee2_6.png)

These instance variables should be named appropriately so that programmers will be able to easily understand their use in reading and modifying code as with all instance variables or fields。

 they'll be created and initialized when the GladLb constructor is called either using new or from within BlueJ when you create an object。

The program could use all the fields when replacing words as part of telling a story。

The field adjective list will hold replacements for the label adjective。

 the field noun list will be for nouns， and the instance variable color list will hold colors to be chosen at random。

Each field holds replacements for the label that's part of its name。

 This is a convention in the program not required by Java。

 but following the convention will make it simpler to create a new instance variable like verb list for a new label。

We'll look at each use of these fields， one is finding a substitute for a label like color。

Based on the word that's part of a label like color or noun。

 the private method git substitute will access the appropriate instance variable to find a random replacement。

 For example， if the label is color， then a replacement will be chosen from the field color list if the label is noun。

 then noun list is used。You can see in the method Gi substitute that adding a new label will require adding a new if statement to access the appropriate array list。

A value is chosen at random using a private method random from。

 both random from and gi substitute a private。 They're called as a result of calling the public make story method。

When Git substitute calls random from， Git substitute will always pass one of the instance variables you made。

 such as adjective list， noun list， etc cetera， as the value for the parameter source。

 Iizing the array list is straightforward， but you'll need to understand it to create a new field for a new label。

 All the array list must be created and initialized when the constructor is called the constructor will call a private helper method initialized from the source for the data for colors。

 nouns and so on could be a URL or a file calling initialize from will result in reading files or URLs to store strings in each array list。

 If the parameter to initialized from begins with H TTP。

 Then eventually a URL resource object will be used to read data。 Otherwise。

 a file resource object will be used。 You can't see that in the code here because the parameter source is simply passed to the helper method read it。

The reading code is located。Let's summarize how the instance variables for replacing labels are used。

 You'll need to understand this to enhance the program by adding a new label， for example。

 to create a label like verb， you'll need a new instance variable you'll name it appropriately like verb list you'll need to modify code in two methods with the addition of verb list。

 you'll modify the method initialized from a private method called from the constructor。

You'll modify the code in the method git Sub， also a private method called by the publicMake Story via the private methods from template and process Word。



![](img/8d3411bb7cebbb18b0b370f873d23ee2_8.png)

The program documentation should include information like this to help you。

 the software engineer make modifications and enhancements。

 have fun telling stories and writing code。
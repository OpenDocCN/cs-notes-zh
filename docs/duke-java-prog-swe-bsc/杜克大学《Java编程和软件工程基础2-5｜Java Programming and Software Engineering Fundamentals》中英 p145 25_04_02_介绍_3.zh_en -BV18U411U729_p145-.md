# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p145 25_04_02_介绍_3.zh_en -BV18U411U729_p145-

![](img/c8e59016ee810de273552169b8937232_0.png)

Hello， in this module， you're going to learn about designing practical Java programs and software design and engineering skills in the context of a useful and amusing program。



![](img/c8e59016ee810de273552169b8937232_2.png)

![](img/c8e59016ee810de273552169b8937232_3.png)

You'll develop and extend programs that use Markov text generation to train on text and then develop random text based on that training data。



![](img/c8e59016ee810de273552169b8937232_5.png)

![](img/c8e59016ee810de273552169b8937232_6.png)

Although recognizing text using Markov techniques uses statistical and probabilistic methods。

 generating text can be done simply using the process and design will explain Many of these ideas were made clear by a mathematician and computer scientist named Claude Shannon。

 who is often recognized as one of the principal thinkers behind what's called information theory。



![](img/c8e59016ee810de273552169b8937232_8.png)

![](img/c8e59016ee810de273552169b8937232_9.png)

![](img/c8e59016ee810de273552169b8937232_10.png)

![](img/c8e59016ee810de273552169b8937232_11.png)

![](img/c8e59016ee810de273552169b8937232_12.png)

This will allow you to practice Java programming and design concepts in the context of a program with very practical applications。

For example， both Google's payD algorithm and many artificial intelligence machine learning algorithms rely on the same Markov concepts we'll explore。

The ideas we'll use have a simple model， suppose you or a monkey。

Pressed keys at random on a typewriter or keyboard。 What text would be generated， Like。

 it would be nonsense。However， what if that keyboard had keys based on a training text。

 So there were more ease if the training text was English。 for example。

 the text might not be so random if there were 20 E keys for every Z key on the keyboard。

We could extend this model so that if the a key was pressed， a new keyboard would be used。

 one that had more T's than B's， because there are many more words that start with the two letters A T than the two letters A B。

 The second letter pressed would be based on probabilities。

 as obtained from the training text and the first letter。

We could bring in a third keyboard based on pressing two letters。 for example。

 if we press T followed by H， then E would be very likely。 R would be somewhat likely。

 and Z would be extremely unlikely。We'll use these ideas in the Markov text generating programs you'll learn about。

Let's look at the output of the early programs you'll develop。



![](img/c8e59016ee810de273552169b8937232_14.png)

Generating text based on training data。

![](img/c8e59016ee810de273552169b8937232_16.png)

In this case， the training data is a speech the German Chancellor Angela Merkel delivered to the European Parliament on October 7。

 2015。An order0 text is based solely on the distribution of characters in the original text。

 There are lots of ease， for example， because that's a very common character。

 The space character is common， too， but the text doesn't look like real text。

And order one text uses one letter to predict the next so that the letter N is likely to follow an A。

 for example， but less likely to follow a P。The words you see are sometimes pronounceable。

 but they're not really words， words like pen， Wpplets and brunt。

An order2 text uses two characters to predict the third。

 This means that an E would be very likely to follow T H。

 and A would be somewhat less likely to follow T H。

 and a G would be very unlikely because the sequence T H G doesn't occur often in text。

You can see lots of words and sequences that are wordlike such as red， wordy， hand， and muitions。

Although we're generating text， you might be able to recognize text and discover the training data。

 this is how Markov text recognition works。

![](img/c8e59016ee810de273552169b8937232_18.png)

![](img/c8e59016ee810de273552169b8937232_19.png)

For example， current spam algorithms often rely on Bayesian probability and Markov processes as part of recognizing spam based on training data。

Here's an order zero text。 Can you recognize that perhaps the text isn't English based simply on the characters that appear。

The accents on some of the letters make it possibly French。



![](img/c8e59016ee810de273552169b8937232_21.png)

In the order one text， where one character is used to predict or generate the next character。

 it seems as though the text really might be French。In the order to text。

 it seems very likely French Here。 two characters predict the third。In the Order  three text。

 you may even recognize La Marses， the French National anthem。

You'll see in the programs you write that generating order 3 and generally order n text is something that you can do。

Here's an overview of what you'll learn in this module。

You'll generalize a concept and an algorithm for generating random text using a Markov process。

You'll see code for zero order and one order text generation。

 and you'll generalize that to any or n order。You'll develop a Java interface that allows the different concepts to be captured practically in code。



![](img/c8e59016ee810de273552169b8937232_23.png)

You'll capture these abstractions in Java by developing and using interfaces。



![](img/c8e59016ee810de273552169b8937232_25.png)

That will help you design and test your program， an important part of building experience as a programmer and software engineer。



![](img/c8e59016ee810de273552169b8937232_27.png)

![](img/c8e59016ee810de273552169b8937232_28.png)

You'll also see that interfaces allow you to make programs efficient without changing too many things at once。

 but separating design and implementation to facilitate efficiency。



![](img/c8e59016ee810de273552169b8937232_30.png)

You'll practice both software design and engineering skills while you develop these programs。

 This will give you practical and transferable experience to other domains of programming。


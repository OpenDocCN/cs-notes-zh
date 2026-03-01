# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P19：19_02_01_变量.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Okay， now that you have the algorithm for green screening at an image。

 you want to translate it into code。But you have a lot of different pieces of code that you need to learn。

 We're going to learn these in Javascript now， but the same basic concepts exist in pretty much any programming language。

 We'll switch to Java in the next course， and you'll see that much of this looks the same。

One thing you need is a way to give names to the values your algorithm comes up with in the English description。

 we refer to them as FG image， BG image， output， and current pixel。

These are going to turn into variables in your code， which you will learn about momentarily。

You also need a way to make images， whether reading in an existing image or creating a blank image。

You need a way to operate on these images and their pixels， looking at particular pixels。

 seeing what color they are and setting the pixels in an image。 you'll learn about these soon。

Your algorithm calls for you to repeat some steps for each pixel in an image。

 You're going to need to learn how to write code that repeats steps， which will be a for loop。

 which you will learn about later。And finally， your algorithm looks at a condition in this particular case。

 whether a pixel is green or not and makes a decision about what to do next based on that condition。

 This is going to turn into an if else statement， which you will also learn about soon。

Here is an example of a JavaScript statement which declares a variable called X and initializes it to3。

 dececlaring a variable means telling JavaScript that you want it to make a new variable。

 initializing a variable means giving it the first value that it should hold when you create it。

Some languages do not require you to initialize variables， but is a good idea to always do so。

Let us take a minute to break down the syntax of this statement。First is the keyword var。

 This keyword is what tells jascript that you are declaring a new variable with this statement。

 Javascript is case sensitive， so you have to write var in all lower case。 Otherwise。

 it does not recognize it as this keyword。Next is the name of the variable。 In this case。

 we picked X for the variables's name。 You can name variables pretty much anything you want。

 There are some rules， but they're somewhat complicated。 If you stick to letters。

 you'll be in great shape。While we can name your variable anything。

 it's good to name it descriptively here， we are not using the variable as part of a real algorithm。

 so we can't give it a really meaningful name。 However。

 remember that we called the variables in our green screen algorithm， things like FG image。

 B G image and output， which indicated what they were for。😊。

Next is an equal sign This equal sign indicates that we're going to assign a value to the variable。

After the equal sign is the value that we want to assign in this case，3。Finally。

 theres a semicolon at the end of the statement in Java and many other programming languages。

 semicollonons are used at the end of statements， much like periods are used at the end of a sentence in English。

 You might wonder why programming languages don't end statements with a period since that seems more natural。

 However， periods get used for a lot of other purposes， such as decimal points and numbers。

 which would make it hard for the computer to figure out if a period ends a statement or serve some other purpose。

Now that you have seen the syntax， let us take a look at the semantics。

 recall that semantics are the meaning of something in the case of a programming language。

 the semantics are the meaning of what the code does， what you're telling the computer to do。

We're going to keep track of where we are with the green arrow shown here。

Just before the start of the code。This arrow will typically point between statements。

 indicating that we have finished the previous statement， but not yet started the next statement。

 We will move it across a statement as we do the effect of that statement Here。

 we are declaring a variable called X and initializing it to 3。 So the effect of that statement。

 its semantics are to create a box labeled X and put three in as its value。

Here is a slightly larger example with three variables。 The first you just saw。

 we create a box labeled X and put3 in it。 The next statement is pretty similar。

 except the variable is named Y and is initialized to 4。So to execute this statement。

 we would create a box called Y and put4 in it。The final statement is a bit more complex。

 It declares a variable called Z， but the right hand side of the equal sign has a more complex expression to compute the initial value。

 X plus2 times y expression is the technical term for a combination of values and operations to compute a value from them。

Here we have a mathematical expression involving the variables we previously declared。

 so we just do the math to get the value for x， we look in its box and find that x is 3。

 Likewise to get the value for y， we look in its box and find that y is 4。

 Now we just have to compute 3 plus 2 times 4， which is 11。

 so we will create a box named Z and initialize it with the value 11。

You can also update the value of an existing variable with an assignment statement。

 noticeice that the syntax is fairly similar to declaring a variable。

 except that you do not write var since you are changing an existing variable rather than making a new one。

Instead of creating a new box， you will update the value in an existing box， in particular。

 the box named on the left side of the equal sign。Here we are going to do x equals z minus1。

 so we would compute z minus1， which is 10 and update x's box to be 10。

The next statement says y equals y times 2。 This looks like an equation from algebra class。

 and sometimes novice programmers think that this statement would solve an algebraic equation。

 However， that is not the case。 This statement follows the same rules as any other assignment statement。

 the current value for y is 4， so we compute four times 2， which is 8， and update Y box to be 8。Okay。

 great， now you have seen the basics of variables with some numeric values。

But what if you want variables that hold things that are not numbers， How could you do that？ Well。

 remember everything is a number， So under the hood， every variable is actually a number。

 but you can use other data types like images and strings where the numbers are interpreted in other ways。

Let us look at this example。 We have two statements here。

 each of which declares and initializes a variable。

The first declares FG image and initializes it to a new simple image。

 which would have the effect of creating a box named FG image whose value is this image of me and Robert。

You may notice that the image is not directly inside of the FG image box。

 but rather off to the side with an arrow pointing at it。 When you do new。

 you end up with an arrow pointing at the thing that new made。

 Why does it matter that new makes a thing and that the box has an arrow pointing at it as you will see soon。

 you can have multiple arrows pointing at the same thing from different boxes。

The second statement behaves similarly， except that the image which BG image is initialized to is Dynos dot P and G。

The expression that we are using to initialize these variables。

Is a bit more complex than the mathematical expressions we saw earlier。

 So let us delve into them for a second。First， we have the keyword new。

 This tells JavaScript to go create a new object。 What is an object。

 It is a piece of data which also has methods that can operate on it。In the case of an image。

 you'll be able to examine and modify its pixels with these methods， which you will learn about soon。

Next is the name of the type to create here you want to make a simple image。

 which is part of the Duke Learn to program libraries and gives you a simple way of working with images to get started。

Finally， there are parameters in parentheses。 These parameters specify more information about how we want the object created。

 In the case of simple image， we can pass in a string which names the image file that we want it to load。

😊，This parameter is what tells the first line to load Drewro。pNG and the second line to load Dynos。

 PNG。There's a lot more to learn about objects in constructing them。

 You'll learn a little bit more about using objects shortly。 However。

 we won't go into too much detail about how to define your own types or objects called classes until later courses。

 We'll talk a bit more about construction in later courses， too。

 although if you want much more detail on that topic。

 you would also want to take the follow on specialization from our friends at UCSD。Okay， great。

 So now you know about variables which are boxes that hold values and how to declare and initialize them。

 as well as how to update them with assignment statements。

 You've learned that expressions are combinations of values such as variables and constants。

 as well as operations such as plus minus and times。 And you learned about new simple image。

 which lets you create a new image by loading the contents of an existing image file。😊。

These are the first pieces you need to understand to be ready to turn the green screen algorithm into code。


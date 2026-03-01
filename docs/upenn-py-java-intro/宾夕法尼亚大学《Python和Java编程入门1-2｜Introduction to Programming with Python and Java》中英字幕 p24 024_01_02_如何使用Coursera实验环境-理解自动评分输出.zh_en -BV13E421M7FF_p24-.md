# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p24 024_01_02_如何使用Coursera实验环境-理解自动评分输出.zh_en -BV13E421M7FF_p24-

![](img/13c3708a4fc8e2d9b1cfc18691899d9f_0.png)

Hello， my name's Pat I do a lot of the setup for our MOC assessments and I'm also a student in the University of Pennsylvania's online MCIT program today I'm going to show you a little bit about how to work with the assignments in this course and what the different outputs will tell you and how to get past some of the more common problems that you might encounter so I'm going to start by opening up this first assignment which is homework 1A。

When I open this up you'll notice that it pops open what we call a Jupiter notebook and that's this interface that we're looking at here it's a really nice way for us to give you some instructions and an environment in which you can run your code。

 meaning that you don't need to install anything or worry about any sort of dependencies on your computer。

 whether you're on Mac Windows Linux it won't impact your coding so this gives us a nice way to get an introduction to writing and running Python code。

In this assignment， we have a note near the top about variable initialization。

 and I would strongly encourage you to read through this and make sure that you understand exactly what's going on here because it's going to be really important to being successful。

 not only in this homework but in future homeworks。So the first thing we need to do。

Is execute this top cell and a cell is just these gray boxes that you'll see within the notebook there are runnable code blocks that you can write and modify code inside of and some of them may be read only like in the case of our test cells or other things that are required for the assignment to work properly。

The easiest way to run a cell is to click the run button near the top。However。

 it's often more convenient to simply use the keyboard and you can hold either shift or control and hit enter and depending on which you held。

You will either stay within the cell， you're running as shown here with this highlighted box being the cell that's selected。

Or you'll move on to the next cell。So if I hold control and hit enter。

The cell executes and I remain in that cell if I hold shift and hit enter。

 the cell executes and I end up on the next cell。Similarly。

 you can begin navigating cells with your arrow keys and you can edit a cell by clicking enter to click into it。

 Now this is a read only cell， so I can't actually modify it。

 but I am able to get into the cell and move my cursor。When a cell executes。

 you'll see a little spinning asterisk， it moves pretty fast inside of this square bracket。

 but on some complex code blocks that you may execute later in the course。

 this might take a few seconds to finish executing。If we look at the first question。

 we're being asked to。Calculate the result of 3。93 multiplied by 4901 and save it in a variable named Q1。

If we look into the actual code。We see that the print statement that's present is already referencing Q1。

 and we know exactly what we need to do here， so let's create a variable named Q1 and assign the value。

3。93 multiplied by 4901。And if I hold control and hit enter here。

I can run that code block while staying in this cell。

Now I'm going to move on to the test here and we'll see that。When I run this cell。

It prints out the word success because we've correctly done the calculation。

 but for the sake of this example， let's make a mistake in this cell so I navigate back to this cell by clicking the up arrow。

And I click enter to begin typing in it。We'll multiply this by four instead of 3。93。

You'll notice the output changes slightly， but the thing that we're more interested in is this test。

When we run this test， we get an error message and this error message is quite large and can be a bit intimidating。

 but once you see a few of these you get the hang of them pretty quickly。

The most important part is what's shown at the bottom， the assertion error。

 and this assertion error is basically saying that these two numbers don't match。

 they expected the numbers to be equal and they're not。So when we look。At the actual test case here。

 we can see this assert equal and we recognize Q1 as we just created that variable。

AndS dot Q1 is the notation we use to access our solution version of that。

 The way these tests work is we have a solution version of the assignment。

 and we store that elsewhere。And then we pull in the values as needed to confirm that the values you calculate match up with what we expect from the solution。

So if we want to correct this， we can go right back to where we made the mistake。

And just change this to 3。93。We hold shift and hit enter to move on to the next cell and then hold control and hit enter to execute this cell。

 and now we get that success message。So now that we are successfully passing the test on Q1。

 we move on to Q2 using our arrow keys， we can simply move down。And in this case。

 it's going to be a similar mathematical operation that we are calculating and using as the value for a variable called Q2。

Again， we can execute this cell and see the print statement return the value that we expect。

 But again， it's more interesting to work through one of the errors。

 So let's just change this calculation slightly。When we execute the test。

We're again going to jump down here and look at the assertion error because this is going to give us the most important information and from here we can tell that these numbers don't align。

And if we look into this bigger message here。We can actually start to understand what's going on so at the very top with this green arrow we see and this is pointing to the assert statement which is basically comparing our variable that we created to the solution variable。

Yes。This is familiar to us because it's actually contained in this cell right here。

 and we know that 43。0 is also familiar as we just printed out in this cell。

 So if we correct that to get to the value。35。83。We can then pass this test and see that success message。

Let's do one more example。 Q3 is a similar question where we are assigning the value of Q3 to。

3 divided by 0。3。Again， we print out the value afterwards and then we go on to our test case。

 and in this case we're passing。Now， let's try checking our test cases using a slightly different approach。

 The validate button at the top is a nice way to verify that you're passing all tests in the notebook。

 not just this test cell that you are actually on。 So when I click this。Yeah。

It's going to calculate every test and you'll notice that many of them are failing。

 but this makes sense because we haven't actually completed the full assignment yet。

If we look at the very top， we see the first failing test is around Q4。

And that again makes sense because we've not completed Q4 yet。Now， if we change Q3。

Such that it fails。And then we go back and validate again。We should now see Q3。At the top。

So this validate button is a nice way to quickly make sure that you're passing all tests。

If we correct this again。And run our cell。 Now we're passing the first three。

So once you've validated your work and you're confident that you are passing as many tests as you're comfortable with。

 you can go ahead and submit this assignment。

![](img/13c3708a4fc8e2d9b1cfc18691899d9f_2.png)

Yes。Now， once submitted， you can always come back in here and resubmit。

You should see a grade appear shortly after submission on the assignment page。

But if you don't get the grade that you hoped for， you can always come back in and attempt this again。

I hope this has been helpful and please post on the forums if you have any follow up questions and good luck in the course。



![](img/13c3708a4fc8e2d9b1cfc18691899d9f_4.png)

그。
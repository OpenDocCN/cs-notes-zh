# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P18：18_02_05_解决编程问题的七步法.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Now， we're going to talk a little bit more about solving programming problems。 In the last lesson。

 we worked through the example of doing the green screen problem。



![](img/0387732bc38753254297dd67b00a931f_1.png)

We took a specific problem we wanted to solve， taking images and applying the green screen tech connect to them and worked through step by step how to go from that problem statement to a working piece of code。

Now， what we're going to do in this lesson is we're going to take a closer look at solving programming problems。

 we're going to teach you the seven step approach that you're going to use to solve programming problems through the rest of this course and the rest of this specialization as well as as a tool that you can use to solve programming problems in general。

 whenever they come up in the rest of your life。In general。

 solving a programming problem starts with a problem statement。

 I want to be able to take a foreground image and a background image and combine them using the green screen technique or anything else you might want to do。

And ends when you have working code that solves your problem。Now， doing this is a big leap。

 It takes a lot of work to go from a problem statement to a working piece of code。

 And you may not be able to just do this in your head all at once。

 Sometimes when a problem becomes easy for you as you become more skilled。

 you'll be able to just do this。 and it will happen naturally and you won't need to worry about it。

 However， the seven step approach we're going to teach you is always going to be a good way to approach any problem where you can't just see the answer right away。

So these are the seven steps that you're going to use to solve programming problems。

 and we're going to look at each of them and see how they work。

 You've seen this already with the green screen example。

 We just didn't talk about the details of each step。 We just did the process。

The first thing to do is to solve a small instance by hand。

 If you remember from the green screen lesson that we just did， we took a four pixel image。

 We didn't want to start with the millions of pixels that are in a real image。

 We just worked through for a very small instance， something manageable。

If you have trouble with this step， maybe the problem is unclear。

 The problem statement doesn't actually tell you how to do things。

 in which case you need to find out what youre supposed to do before you can proceed in a classroom situation。

 this it may involve asking your teacher or teaching assistant for clarification。 in the real world。

 this may involve talking to your technical lead， your customer or refining the problem yourself to figure out exactly what it is you need to do。

The other possibility if step1 is difficult， is that you might need domain knowledge if you're trying to solve a programming problem related to physics。

 but you don't know the physics equations involved。

 then no amount of programming expertise will help you you need to consult a physics textbook。

 a Wikipedia article on physics or a physics professor to understand the physics before you can try to solve your programming problem。

Once you've completed step1， you're ready to proceed to step 2 in step 2。

 you're going to write down the exact steps of what you did in step 1。That is。

 you're going to give directions to someone to solve just that instance of the problem。

 not to solve the more general case， not to do it for any image。

 but just how you came up with your answer for that particular four pixelel image or whatever your problem might be。

The tricky part here is that there are a lot of things that we as humans do without consciously thinking about them。

 We just kind of naturally do them， and we have to think really carefully because the computer doesn't have common sense。

 We need to be very precise。 If we're a little sloppy with our steps here。

 it's going to make things more difficult for us later on because we're going to be missing crucial parts of our algorithm。

In step three， we need to find patterns， we want to write an algorithm for any instance of the problem。

 not just the particular instance that we worked。And so what we're going to do is look at the steps that we wrote down in step 2。

 and we're going to find patterns。 We're going to think about repetition。

 What things are we doing over and over again， How many times are we doing them。

 These will lead to looping constructs， Conition sometimes we do something。

 Sometimes we don't do it under what conditions does this happen。

 This will lead us to conditional constructs like if else， and we'll have values。

 Maybe we used a particular number， because it was part of our input or related to our input。

 We need to think about why we use that particular number。If we have difficulties in this step。

 we need to go back to steps1 and2 and do them again for different inputs。

 if we do these over and over again， we'll come up with more information to look for patterns from。

 we'll have different sets of steps that we come up with for step two that tell us how we worked multiple instances of the problem and be able to find patterns more easily。

Once we finish step 3， we want to check our algorithm by hand。

 We just came up with what we think is a general algorithm， but we may have made a mistake。

 We may not have realized that something happened under particular case。

 or we may have left a value that was particular to the parameters that we chose。

 If we did one of these mistakes。 we'd like to find this now before we translate our algorithm into code。

 So we're going to check this with one or more different inputs， which are again。

 going to be of sizes that are manageable to do by hand。

 We're not going to try it on a million pixels， but we might try it on a very small other image or some other small input。

Once we're confident in our algorithm， we're ready to translate it to code。

 This is where the particular programming language that we're working in is going to come into play。

 so far， we've been looking at JavaScript so we would take our algorithm and express it in the syntax of JavaScript。

Once we've written this down， we want to run test cases。That is。

 we want to execute our program and see， did we get the right answer with our program based on what we expect the right answer to be knowing what problem we're trying to solve。

Every time we run a test case， if it passes， that is we get the right answer。

 we're more confident in our program。 If it fails， we know something is wrong with our program。

 and we move on to step 7， debugging failed test cases。For this。

 we're going to use the scientific method， which we're going to talk about a lot in the next lesson。

And this is going to help us understand what the problem is and give us guidance on what we need to do to fix the problem。

Ultimately， what's going to happen is if we have an algorithmic problem。

 we're going to return to step 3 and fix our algorithm， and if we have an implementation problem。

 we're going to return to step 5 and correct our translation of our algorithm to code。

So these are the seven steps that you can use to solve any programming problem。

 and we're going to use them throughout our examples in the rest of this course and specialization。


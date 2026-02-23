# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P77：35_为表单编写第一个测试.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Imagine that the little lemon restaurant started receiving a few bad reviews from its customers。

 The problem is that they could not figure out what was wrong and act accordingly。

 since users only provided a low numerical score， Skiping the part of providing additional feedback and passing that information to the chefs。

 in order to solve that， they've decided to make the common text box mandatory。

 as long as this score provided by their users is lower than 5 in a scale to 10。



![](img/c484cdee693ed85763c5b39a8afdd358_1.png)

Additionally， they would like to shield this new logic with automated tests so whenever any changes are performed。

 the test suite would run and be able to catch any potential errors incurred by a faulty update。



![](img/c484cdee693ed85763c5b39a8afdd358_3.png)

So the application consists of a feedback form that contains a range input for a numerical score ranging from 0 to 10 and a text box to incorporate additional comments。

To satisfy the requirements desired by little Le， the submit button will be disabled if this score is lower than 5。

 forcing users to add a comment of at least 10 characters。 Now， let's examine the code。



![](img/c484cdee693ed85763c5b39a8afdd358_5.png)

The entry point is the app dojS component where I'm rendering a feedback form component。

 this component receives a prop on Subm， which is a function that contains the values of the form as parameters so that the parent app component can perform the submission。

The feedback form represents an HTML form and includes two controlled components via local state。

 a range input and the text area。There are two pieces to highlight in this component。

 The first is the button disabledable logic is disabled is the variable that controls that state and is set to true if the score is lower than 5。

 and the comment has less than 10 characters。

![](img/c484cdee693ed85763c5b39a8afdd358_7.png)

The other important piece is the handle Submit function。

 which is hooked into the form on Sububit attribute When the submit button is clicked。

 the handle Subm function will be called This function itself calls the prop function provided by the parent with the corresponding form values。

Well， it's clear that the feedback form component contains all the business logic of interest。

 so let's go ahead and write a test for the submission logic。

 The convention for test is to create them inside a file that has the dot test extension that way Jests the test runner is able to pick them up automatically when you run the test command in your terminal。

As I have already written a test scenario， I will now walk you through each line of code so that you understand how the test is structured step by step。

 The test scenario is checking that users are prevented from submitting the form right away if the score is lower than5 and there is either no additional feedback or too short。

First， I create a new mock function with jest。 recall that a mock function is a special function that allows you to track how a particular function is called by external code。

 When the feedback form calls the function you provide as the on submitubmit prop。

 you will be able to explore the argument passed in the call。

Then I render the feedback form and pass the mock function as the on submitubmit Pro。

The following steps are needed to locate the range input and fill it with a value。

 Not that to find the input， I'm using this screen dot get by label text and passing a regular expression to match against。

Screen is a utility object from React testing library that represents the whole page which basically translates to asking the root document to find a label tag whose text contains the word score。

 and then return the input element associated with that label。To fill the input with a value。

 you have to use the fire event utility from react testing library and call the change function。

 While react control components update their state via the onchan prop。

 react testing library follows a slightly different convention。

 removing the on part and having the update method as lowercase to simulate the form submission。

 I have to locate the button element。 observeer how I'm using a different query method。 get by role。

 which looks at elements with a specific role attribute。

 This will work well since the HTML button already has the button roll internally set to simulate the event。

 I need to provide two arguments。 First， the input element in question and second。

 the browser event object， which holds the new value as target dot value to perform a button click。

 I have to use fire event dot click。 It follows the same convention as before。

 removing the on side of the prop and having everything in lowercase。 Great。

 the final two statements are the assertions of the test。

The first one illustrates an example of an expect match that wants to check the opposite by preending the knot before calling the final matter。

What it's asserting is that the function that handles the submission of the form has not been called。

 which is what I'm expecting when an additional comment has been omitted。 Furthermore。

 I have added a second assertion to make sure the submit button is indeed disabled by using the to have attribute matter。

 And that's it Well done for reaching the end of this demonstration。 And this video。

 you learn how you can shield your business logic with a few lines of powerful code。

 thanks to the react testing library。 And what's more important。

 it has enabled the chef at Little lemon to finally receive the necessary feedback and make sure all the new pizzas have a bit more extra cheese on top。



![](img/c484cdee693ed85763c5b39a8afdd358_9.png)
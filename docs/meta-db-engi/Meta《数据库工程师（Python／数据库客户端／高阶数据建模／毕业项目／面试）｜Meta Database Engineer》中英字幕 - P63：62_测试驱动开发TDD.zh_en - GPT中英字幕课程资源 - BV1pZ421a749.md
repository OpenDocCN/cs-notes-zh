# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P63：62_测试驱动开发TDD.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Testing has been a relatively recent entry in the software development lifecycle。

 but its importance has been growing as time passes。😊。

Software development is time sensitive and in the process developers often find testing gets squeezed into the time remaining after the code is written This doesn't leave enough time to test and can lead to the software containing bugs that need to be dealt with over time Test drivenriven development or TDD is an alternative programming practice in which the tests are written first and the code is written so that the tests will pass This differs from the convention of first writing the code and testing the application progressively。



![](img/a95f5c43ed05c9daef36467846f17bcd_1.png)

TDD follows an iterative approach beginning with writing the test cases。

The initial work requires feature and test planning by the team with slight variations。

 let's explore the standard steps。Step one， you write a test for a feature that fails。

In step 2 you write code in accordance with the tests step 3 requires that you run the test expecting them to fail in step 4。

 you evaluate the error and refactor the code as needed and finally in step 5 you rerun the process。



![](img/a95f5c43ed05c9daef36467846f17bcd_3.png)

This process is also called the red green refactor cycle red implies the failed tests and green shows the passing tests after refactoring the whole point of following this cycle is to fail the tests and rewrite until you don't have to a feature is complete when everything is green and you no longer need to rerun。

You can use a package library such as P test when automation becomes a priority P test only requires writing functions while UniTest requires classes This means that PT has the advantage of being easier because it requires less effort。



![](img/a95f5c43ed05c9daef36467846f17bcd_5.png)

Okay， now let's explore some of the advantages you gain from TDD。



![](img/a95f5c43ed05c9daef36467846f17bcd_7.png)

Writing tests first and refactoruring code based on it ensures the tests cover the code。

You can now write test with a specific feature and outcome in mind。

The need for such forecasting provides clarity from the beginning。😊。

The forecasting also plays a role in integrating different components where you add new features and interfaces in accordance with the components that are already there。

Working in cycles over the code gives the developer confidence to easily refactor in terms of additional changes。



![](img/a95f5c43ed05c9daef36467846f17bcd_9.png)

Overall， smaller code with early bug fixes， code extensibility。

 and eventual ease of debugging are the primary reasons TDD is growing in acceptance。😡，Finally。

 let's briefly explore some of the differences between TDD and traditional testing。😊。

The main difference is that with TDD， the requirements and standards are highlighted from the beginning。

 making it purposeful。😊。

![](img/a95f5c43ed05c9daef36467846f17bcd_11.png)

Modern day development often employs a combination of both these forms of testing。

 depending on the different parts and stages of the software development cycle。

There are several subtypes and variations of test driven development these include behavior driven。

 acceptance test driven， scaling and developer test driven development these are all options that can be used in the software development process。

😊。

![](img/a95f5c43ed05c9daef36467846f17bcd_13.png)

Congratulations in this video you learned about the process of test driven development。😊。


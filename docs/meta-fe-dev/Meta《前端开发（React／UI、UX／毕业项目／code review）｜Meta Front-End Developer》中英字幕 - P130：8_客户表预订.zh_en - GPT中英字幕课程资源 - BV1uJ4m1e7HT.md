# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P130：8_客户表预订.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In this lesson， you'll work on the reserve a table functionality for the little Le website。

 In order to do this properly， you'll need to revisit three major react concepts。

 Working with state in react。 Work with forms and writing unit tests。

 Being able to work with state is one of the foundations of react。

 Imagine for a moment that there was no state in react。 by very definition without state。

 All you would end up with is a number of static components and react would simply be a way to divide a large piece of H into smaller sections that are easier to reason about。

😊。

![](img/092b87eb9240f9acae0f20956977ac01_1.png)

![](img/092b87eb9240f9acae0f20956977ac01_2.png)

In other words， you would still end up with components。

 but these components would not allow for any interactivity。 In this case。

 the only benefit to components would be how they allow you to split long code。

 depicting an entire web page with smaller chunks。 Other than that。

 there'd be no real advantage to using them。 This illustrates that in react components and state are inextricably linked。

 One of the simplest examples that is given to beginners when learning about state and react。

 is the example of a counter app or counter componentonent。 a counter would consist of， for example。

 a paragraph that starts off with a certain number value under that paragraph would be buttons。

 which， when clicked， would update the number value shown in the paragraph。😊。

To be able to code a simple example like this on your own， you need to know about rendering in react。

 In addition to being able to use the use state hook and event handling code。 Of course。

 this is a very basic example， but it is often used because it nicely demonstrates different things you need to know of and be able to use in order to deal with state in react。

 State and react also ties in with forms specifically Under controlled and uncontrolled components。

 with controlled components， you control a given form using react state。

 with uncontrolled components， you control a given form using the underlying dom。 This， of course。

 requires the use of another hook， namely the use ref hook with these two concepts in mind。

 you'll need to define the new booking page so that little Les customers can submit new bookings。

 Once you've created an app。 How do you know that it works well。

 How do you know that previous requirements。😊。

![](img/092b87eb9240f9acae0f20956977ac01_4.png)

![](img/092b87eb9240f9acae0f20956977ac01_5.png)

![](img/092b87eb9240f9acae0f20956977ac01_6.png)

The quality assurance or Q A department， client or customer have all been met。

 How do you know that new additions to your app's functionality haven't broken previous functionality。

 These are all tough challenges to tackle。 But thankfully， we have testing。

 That's why in this lesson， you'll also need to write unit tests for your code。 In closing。

 please be aware that combining the concepts mentioned briefly in this video is not a trivial matter。

 Work with all these concepts and techniques takes some time to master。

 That's why you should set aside enough time when working on this functionality。 And if needed。

 referenceence other materials in this program。 too。 Let's begin。😊。



![](img/092b87eb9240f9acae0f20956977ac01_8.png)

![](img/092b87eb9240f9acae0f20956977ac01_9.png)

![](img/092b87eb9240f9acae0f20956977ac01_10.png)
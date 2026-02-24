# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P55：13_组件模块总结.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Well done。 You've reached the end of this module on react components。

Let's take a few minutes to review what you have learned so far。😊。

You began the module with a comprehensive lesson on how to render lists with React you were introduced to the map method in JavaScript。

 which can be used with a to perform transformation operations and is a useful tool when dealing with data from an external provider that you'd like to display differently in your app。

You also learned how to transform any list of items in Javascript using the map method first hand。

 Next， you discovered how to use that map method function。

 along with JSX to render a list of components and transform a collection of elements with react。

 Finally， you gained an understanding of the concept of keys。

 followed by a practical set of guidelines that help you choose the right key。

 depending on your use case。You learned that keys are identifiers that help react。

 determine which items have changed， are added or are removed， as well as instruct。

 React how to treat a specific element when an update occurs and whether its internal state should be preserved or not。

You also discovered that keys can be used when you need to provide explicit information that tells React how to behave when your UI changes when dealing with a list of items。

You've learned that the general rule with keys is to use a stable identifier that is unique among its siblings。

 which is why the key used most often is a unique I from your data。

 You then learned that it is possible to use indexes as keys as a last resort。

 but that this can negatively impact performance if the order of your list items is likely to change。



![](img/c1687f4eb31194577b294c80fde19aa0_1.png)

Next， you moved on to a lesson on forms and how Re treats them differently compared to traditional HTML versions。

You were first introduced to controlled components。

 which are a set of components that offer a declarative API to enable full control of the state of form elements at any point in time using React state。



![](img/c1687f4eb31194577b294c80fde19aa0_3.png)

You learned how to convert any traditional HTML form into a react form using a set of controlled components。

In other words， you learned how to transform an uncontrolled form into a controlled version using local state and the onchan event as well as the on submitubmit Pro。

You also discovered some of the advantages of controlled components compared to uncontrolled components。

 For example， it makes it possible for you to have more control over form submission such as disabling the submit button when the form is invalid。

Last， you were taught how to implement a feedback form。 And in relation to this。

 how to perform any custom validation logic before the submission of the form occurs。

 The final lesson began with a recap of props and state。

 You learn to clearly differentiate between props and state and when to use one or another。

Recall that although props in state have similarities， for example。

 they are both plain JavaScript objects the react uses to hold information。

 props get passed to the component， where state is managed within the component。

Key takeaways included that if a component needs to alter one of its attributes at some point。

 then that attribute should be part of its state； otherwise it should just be a prop for that component and that a component without state is preferable。

You also learned about stateless components which have props but no state and stateful components which have both。



![](img/c1687f4eb31194577b294c80fde19aa0_5.png)

After that， you covered the problem of props drilling and how it affects your components's modularity。

 as parent components have to drill down props all the way to the children that need to consume them。

You were introduced to context API as a solution to this problem and discovered how to use it to encapsulate any piece of global state and avoid manually passing props down between components。

The power of react context was illustrated as a viable alternative to local state。Well。

 I think that's a fantastic start on your journey to mastering Re。

 looking forward to working with you in the next module。


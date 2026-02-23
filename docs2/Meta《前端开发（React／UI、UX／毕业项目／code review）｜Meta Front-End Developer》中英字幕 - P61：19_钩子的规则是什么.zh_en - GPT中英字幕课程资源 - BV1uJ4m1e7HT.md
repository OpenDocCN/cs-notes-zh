# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P61：19_钩子的规则是什么.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By now， you should have a fairly good idea about the purpose and functionality of hooks in react。

 and you may have even started using hooks in some of your solutions。If so。

 you may have encountered some cases where hooks might have made your code invalid。 Well。

 that's because there are a few basic rules to hooks that you need to be aware of and follow in your react apps。

 In this video， you will learn all about the rules of hooks and react and why they are so important and why you would only call hooks at the top level and from react functions。

 The four main rules of hooks are as follows。 First。

 you should only call hooks from a react component function。 Second。

 you should only call hooks at the top level of a react component function。



![](img/1b6178e84164dc75b1c4f08ba49b9b8f_1.png)

![](img/1b6178e84164dc75b1c4f08ba49b9b8f_2.png)

Third， you are allowed to call multiple state hooks or effect hooks inside a component， and finally。

 always make these multiple hook calls in the same sequence。

Now let's unpack each of these roles in a little more detail。

The first rule means that you should not be calling hooks from regular JavaScript functions。

 instead you should only call them from inside a react component function。From a built in hook call。

 for example， from the Use effect hook or from a custom hook。In this example。

 the code describes a button that can be clicked to pick up a new name for a pet。

The name Looper function is used to limit the pet name choices to only fluffy， Rexxi or gizmo。

 noticeice that the U state hook is accessed to the outermost scope of the app function。

 It has not been used anywhere other than this， for example， inside the name Looper function scope。

However， you may have observed that this rule does not prevent you from using the state setting function。

 which is named set Pat name here。State setting calls can be used wherever required。

 The second rule means you must call your hooks before a return statement outside of loops。

 conditions or nested functions。 If you use a hook in a condition， your breaking rules。 For example。

 here， the use effect hook has been used inside the if conditional statement that makes the use of the hook in this code invalid。

The third rule is straightforward。 There can be multiple hook calls as long as they are always in the same order。

 What that means is that you cannot place hook calls inside conditionals because that might result in an invocation of a hook being skipped when compared with a previous render。

In this example， with the same code that describes a button that can be clicked to pick up a new name for a pet。

 the use state hook has been used incorrectly。 rather than using the state setting function set pet name inside the name looper function。

 the use state hook has been used here instead， If you were to compile the code and run the app。

 you may find that the expected output is returned。 For example。

 I'd like to name my pet fluffy with a pick a new name button rendered beneath。 However。

 as soon as you click the pick a new name button， you would receive an invalid hook call error。

 That would violate the fourth rule。 In other words。

 it might disrupt the sequence of invocation from one render to the next。

 Such a violation would result in errors。 If you want to call an effect conditionally。

 you can still do so， but make sure to place the condition inside the hook。Here。

 the use effect hook is invoked initially， followed by the if conditional statement。

So now you're not breaking the rules and the code is valid。



![](img/1b6178e84164dc75b1c4f08ba49b9b8f_4.png)

So let's recap on the four main rules of hooks。 You should only call hooks from a react component function。

 You should only call hooks at the top level of a react component function。

 You are allowed to call multiple state hooks or effect hooks inside a component and finally always make these multiple hook calls in the same sequence。

And that's it In this video， you learn the main rules of using hooks and react and why you would only call hooks at the top level of and from react functions as long as you stick to these few simple rules。

 you can enjoy using hooks in your react solution successfully。


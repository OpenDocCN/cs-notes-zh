# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P131：9_查询预订表 API.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In this lesson， you'll need to use an API to send the reservation data when your app's user makes a table reservation on the little Lemon website to be able to do that properly。

 you'll need to revisit some foundational concepts。 to begin with。

 you'll need to revisit the topic of asynchronous operations in jascript。 Obviously。

 this is a topic outside of react itself， because react was built to work with jascript。

 This means that you must at least be familiar with the essential jascript concepts of synchronicity and asynchronicity。

 For example， you need to understand the general principle of how jascript。

 which is synchronous and single threaded deals with asynchronous operations。

 The shortest answer is that it doesn't really deal with it at all。

 It just uses other built in browser functionalities to delegate work to them。

 and then accepts the results of that work。 Those functionalities are known as browser apis。

 There also sometimes referred to as。😊。

![](img/f15d121dade1f3a2fe53e7f65adf2126_1.png)

![](img/f15d121dade1f3a2fe53e7f65adf2126_2.png)

![](img/f15d121dade1f3a2fe53e7f65adf2126_3.png)

Web APIs， these are， of course， not to be confused with third party APIs that you can connect to to fetch some data from the web。

 but differently， to be able to successfully complete this lesson's tasks。

 you need to know how to deal with requests for thirdpart data in plain jascript before you can implement this functionality in react。

 Luckily， it's mostly the same mechanism with the addition of reacts insisting on dealing with side effects using a dedicated hook。

 namely the use effect hook。 There are several ways to make requests for thirdpart Json data in jascript。

 but one of the more popular ones is using the fetch method。

 which is a built in jascript facade function。 The fetch method uses the X HR API or X M L H T TP request API。

 It's a piece of functionality that comes built into the browser。

 but it's not a part of the browser's jascript engine。 That's why we say that the fetch method。😊。



![](img/f15d121dade1f3a2fe53e7f65adf2126_5.png)

![](img/f15d121dade1f3a2fe53e7f65adf2126_6.png)

A facade function。 When you invoke the fetch method， it returns a promise。

 This means that you also need to understand， at least at a surface level how promises work in jascript and by extension。

 react as well。 A promise is an object that might get fulfilled at a later time。 Actually。

 every promise in jascript can exist in three states。 P， fulfilled and rejected。



![](img/f15d121dade1f3a2fe53e7f65adf2126_8.png)

![](img/f15d121dade1f3a2fe53e7f65adf2126_9.png)

If a promise is fulfilled， then the jascript engine is free to execute all the methods that were given to it as than function calls。

 which are chained to the original fetch call。 Once the Json data has been thus received。

 you can update the local component state with that Json data。😊。

Because invoking the fetch method constitutes a side effect， meaning something outside of react。

 Feing this data requires the use of the use effect hook to update the state。

 you can use either the use state hook or the use reducer hook。

 So why does react insist on using the use effect hook in the case of fetching some third party Json data。



![](img/f15d121dade1f3a2fe53e7f65adf2126_11.png)

![](img/f15d121dade1f3a2fe53e7f65adf2126_12.png)

![](img/f15d121dade1f3a2fe53e7f65adf2126_13.png)

You'll also need to be able to submit your data to the API。

 Just like you did in the previous lessons of this course。

 you'll be given exercises where the objective will be to complete API unit tests。 Finally， as usual。

 you'll also need to track your newest updates using Gi。

 There are quite a few tasks to complete in this lesson。 So let's get started。😊。



![](img/f15d121dade1f3a2fe53e7f65adf2126_15.png)
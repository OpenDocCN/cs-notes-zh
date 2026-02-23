# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P63：21_获取数据并汇总.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

The little Le restaurant wants to rent a competition for its customers。

 where a lucky customer will receive a free meal at the restaurant。

 All customers that are signed up to the little Lemon app will be entered into the competition。

 and a random customer will be selected as the winner。 In this video。

 I will show you how to get some random user data from a website。

 I will be using the random dot me website to access random user data for this demonstration。



![](img/80940bad0a0e7a0cf298b6869aec9298_1.png)

I have prepared some code for this app to fetch the user data from the website。

 If I execute this code， it will initially output the data pending text in the H1 heading At the same time in the background。

 it will be carrying out the fetch data function to retrieve the user information from the random user website。

 noticeice that I have the dev tools open and the network tab active。

 I will click on the no rattling dropdown to artificially slow down my connection。 and the dropdown。

 I will choose the slow 3G preset。 This is so that I can observe the data pending text and the heading before the data gets fetch from the web。



![](img/80940bad0a0e7a0cf298b6869aec9298_3.png)

Once the data has been successfully fetched， it updates the view with the data returned H1 heading and the user information that has been retrieved。

In this example， the data that was requested was the first name and the last name of this random user。

 let's step through this code in more detail。

![](img/80940bad0a0e7a0cf298b6869aec9298_5.png)

So first I have the app function and inside of it following the rules of hook。

 I'm invoking the use state hook at the top level of the component。

 The initial value of the state variable is an empty array。Next。

 I have defined the fetch data function， which is fetching data from the random user。 me API。

 then it retrieves a response from the API in JSON format。

 it then updates the state variable with this JSON data。

You may notice that I'm not using a hook inside the fetch data function because that's against the rules of hooks。

After that， I'm calling the use effect hook and from inside they use effectect hook。

 I'm calling the fetch data function， which I've defined previously。Finally。

 I'm using conditional logic to decide what to return First。

 I'm using the object dot keys code snippet to put all the keys of the user object into an array。

Since object dot keys returns an array， I can access the length property on this array and check if the length of this array is greater than 0。

 If it is， it means that the contents of the state array has changed because as you may remember。

 the state variabless array was empty。So if the array is no longer empty。

 then the diff section will be returned with the H1 tag and a couple of H2 tags。

 otherwise the H1 tag below is returned that reads data pending。

Sometimes it can take a little bit of time for the fetch data function to retrieve the data requested。

 Therefore， the data pending message would be displayed initially after the code is executed。

 Once the data has arrived from the fetch data call。

 this change in state causes a render of my component。

 So the return statement Turnernary operator is reevaluated and that returns all the data from my call to the fetch API。

 and this is essentially how you get data from the web using React。

 So the little Lemon restaurant would be able to apply the same logic to their customer list API to select a random winner for their competition。

 in this video you have learned how to fetch data using the state and effect hook。



![](img/80940bad0a0e7a0cf298b6869aec9298_7.png)

![](img/80940bad0a0e7a0cf298b6869aec9298_8.png)
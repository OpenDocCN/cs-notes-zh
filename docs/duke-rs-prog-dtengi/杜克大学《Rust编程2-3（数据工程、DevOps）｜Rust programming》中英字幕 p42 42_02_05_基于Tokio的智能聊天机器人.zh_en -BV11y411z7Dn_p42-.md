# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p42 42_02_05_基于Tokio的智能聊天机器人.zh_en -BV11y411z7Dn_p42-

![](img/1e05a5451e2f23fcd2c47448b86e219b_0.png)

Here we have a chat bot that is built using some of the nice libraries that you can use with the rest language。

 This code implements a conversational chat loop with an AI assistant and this particular example uses the open AI API。

 but really the code can be used with any large language model。

 if we take a look at what it's going to do。 it's going to enter a loop asking for user input first and then it's going to send it to the API。

 it's going to print out the response， and then it's going to append both to the conversation。

 So the key functions here are a run chat loop。 So main loop is going to handle the conversation。

 which is right here。

![](img/1e05a5451e2f23fcd2c47448b86e219b_2.png)

The next part is it's going to go ahead and call that API and this is where the API call is taking place。

 Now again， it could be done with any API for example。

 a cloud vendor a locally sourced large language model and open source large language model and then finally we get into here and we push out the response and then finally here in terms of the call API。

 you can see that it's a async call right so the reason this is important is it makes it very fast inefficient and scalable because I can use the Tokyo library to handle that now in terms of the last things here we also have get AI response so I parse that and then we also go into the read user input here。

 grab a string and then put that inside so the only other things to be aware of in this example would be to look。

Cargo dot。2 Ml file and look at the different libraries。

Notice here that I was able to use R EQ W ES T， the request， Tokyo。

 also the Sur library here and this one is actually helping with serialerilization。

And I also have the name of the structure Now to pull it all together。

 I have a couple of the files here， so Lib， I expose the chatbot。 Rs。

 and this is one style if you wanted to build out a larger project。

 you could use the lib to just expose another rust script here and then in this particular main do Rs I pull it all together and you can see that I say use chatbot run loop and then use that request and the code in the main is extremely small because all it's going to do is asynchly call into what I built later。

And then I can use the API key， use the URL， and then run on this chat loop。

 So that's what it looks like in a nutshell。 Let's go ahead and get this thing working。 So first up。

 I go to cargo run。And then I ask for human input here。 and so we can ask it a question。

 So you know who。1。The Olympics。For the men's。100 m sprints。In the year 2000。

And it says in the summer 2000 Olympics， the gold medalal for the 100 M sprint was won by Moores Green with a time of 9 do8。

7 seconds。 We could ask a little bit more， you know， who is。More Morey screen。For example。

Could say who is， Maurice。Greened。😔，And it says a former track and field sprinter who competed in hundred and 200 m。

 He won the gold medal and the 10 seconds at。At the 2000 Summer Olympics also twotime World Champ in the hundreds right so anyway I've been able to very easily build out a pretty sophisticated tool just with a little bit of code in rustt here because I can leverage the capabilities of the rust language in terms of being able to build safe asynchronous code Ru is a great choice for building chatbots。

 it's very performant， there's not much to do after you've built your initial structure and once you've got a proof of concept you can easily scale this out to a production environment。



![](img/1e05a5451e2f23fcd2c47448b86e219b_4.png)
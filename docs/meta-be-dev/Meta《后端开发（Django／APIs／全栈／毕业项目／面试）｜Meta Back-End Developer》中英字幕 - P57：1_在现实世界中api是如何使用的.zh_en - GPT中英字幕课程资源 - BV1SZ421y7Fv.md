# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P57：1_在现实世界中api是如何使用的.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Designing an API is pretty much an art form in itself。

 there's a lot of craft and thoughtfulness in how we design things that we present to an end user。

I'm Selena， a software engineer at Meta working on Instagram reels。

I first got into software engineering， I think around the time when I was in middle school。

 I really fell in love with a process of web development and web design。

 which I actually learned just by myself out of curiosity。

 and so I would dissect websites and see how they were functioning under the hood。

 I would follow tutorials by myself， and I really fell in love with this process of creating something tangible out of something seemingly like abstract like an idea or you like blobs and lines of code in this case。



![](img/70ec9f9f842d3e44daa753c5456e3c58_1.png)

So APIs are essentially the bread and butter of endto end full stack developments and I say bread and butter just because they're so crucial in terms of describing how software components interact with each other。

 So whenever you pull up your Instagram app， you are interacting with APIs all over the place。

 So there's a specific set of APIs that renders things like stories and photos and videos in your home feed。

 there's another API that does the same thing but on your Exper page and there's another API that registers things like double taps on a post as likes on the backend and that tells your device to render that little heart icon in the red color you can think of APIs as essentially an intermediary between an end user and a backend service So say you you can describe an API as a bank teller and the data that backend services host as the money in the bank when you are a customer wanting to withdraw or deposit money from the bank you're not necessarily interacting with the money directly。



![](img/70ec9f9f842d3e44daa753c5456e3c58_3.png)

![](img/70ec9f9f842d3e44daa753c5456e3c58_4.png)

Instead， you go to a bank teller， in this case， an API。

 which handles things like communications between the end user and the backend services and also tells you how much money or like data you're able to access。

So APIs at metata are designed with specific purpose in mind。

 so say the goal is to design API for a user- facing product or feature。

 typically we have a designer that kind of creates the mocks and we work with a product designer that essentially provides information on here are the highle objectives of what this end product or service could look like。

 and then typically the actual API design is a handshake agreement between several engineers typically backend and front engineers agree on the API structure。

 and they also agree on things like what the request structure could look like and what the response could look like as well。



![](img/70ec9f9f842d3e44daa753c5456e3c58_6.png)

![](img/70ec9f9f842d3e44daa753c5456e3c58_7.png)

So in thinking about designing an API， I think it's really important to consider who your end user is Another thing to consider is also who are the people who are going to be accessing the data and also your API and services。

 so you want to make sure that you add a layer of security in the form of credentials to your request in order to preserve that integrity as well。



![](img/70ec9f9f842d3e44daa753c5456e3c58_9.png)

My advice for aspiring developers is come at API design with an open mind。

 remember that it's going to be a collaborative process between several engineers and potentially also product managers and designers。

 folks who are going to be really invested in the outcome of the API in the form of a product or an app or a service even when you're building an API you really have to think about components as part of a larger piece and there is kind of like beauty and you know like having an output that is reflective of things that you see in an application in the real world and so just hop fun with it brainstorm with engineers and get a sense of like what the target architecture for an API could be。



![](img/70ec9f9f842d3e44daa753c5456e3c58_11.png)

So I hope that you have a better sense of what APIs are and how they fit in this software development lifecycle。

 I know that you have a lot of work ahead of you but keep checking at it just because it's so worth it to know how all these different components interact with each other。


# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P58：2_你对http有什么了解.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now， you know that HTTP stands for Hypertext transferfer protocolcol。

 and that it's one of the most widely used communication protocols for transferring data across the internet。

Let's briefly refresh your memory of H T T P and H T T P S before diving into more complex topics In this video。

 you will learn about how H T T P and H T TPS S work。 H T TP methods， H T TP requests and responses。

 and finally， H T TP status codes。When you browse web pages， view images or submit a form。

 your data is transmitted using HttP or a secured version of it， which is called Https。

 But how does that transmission work for H TTP and H TTPS respectively Com over H TTP requires at least two parts。

 The client who requests some information and the server who responds to this request and serves the content。

 HtTps is the secured version of HtTP， which makes it better suited to instances where security is a concern。

 But let's find out how this works。 with HtTps， the client's computer encrypts data before it starts its journey to the server。

 The server then decryptps this client side data and processes it。

 But the web server also encrypts the response data and sends the encrypted content back to your browser。

 Your browser then decryptps the response and displays it。



![](img/26b118028d75473615fb4bb7fd1120d8_1.png)

Since the content is encrypted， it is more secure and very difficult to steal or retrieve information from it。

For submitting sensitive data like credit card information。

 it is always preferable to use H TTPS to make sure the data is secure。Now。

 let's move on to some common HTTP methods。

![](img/26b118028d75473615fb4bb7fd1120d8_3.png)

HTTP methods are also called HTTP verbs。 There are five methods commonly used when accessing content over HtTP。

 They are get， which retrieves a resource post used to send data to the server and then create a record put which updates the whole resource patch。

 which you used to partially update a resource and delete。

 which deletes a resource Next are H TTP requests， which contain different types of information that a user's browser sends as encoded data。



![](img/26b118028d75473615fb4bb7fd1120d8_5.png)

![](img/26b118028d75473615fb4bb7fd1120d8_6.png)

![](img/26b118028d75473615fb4bb7fd1120d8_7.png)

A typical H TTP request includes the following。

![](img/26b118028d75473615fb4bb7fd1120d8_9.png)

H TTP version type， for example，1。1 or 2。0 URL or path， H TTP method。

 H TTP request headers and an optional H TTP body。 But what are the H TTP request headers and body again。

 Well， when you submit a form like your username and password to sign into a website。

That data is passed to the web server as the HTTP body as either a raw JSON string or a form URL encoded string。

HTTP headers， on the other hand， are a core part of every HTTP request and may contain extra information that helps the server make some decisions on how to present the content。



![](img/26b118028d75473615fb4bb7fd1120d8_11.png)

Examples of H TTP request headers are cookies， user agents and refers。



![](img/26b118028d75473615fb4bb7fd1120d8_13.png)

After an HTTP request comes the HTTP response， which consists of information that the browser uses to properly display the content in the response body。



![](img/26b118028d75473615fb4bb7fd1120d8_15.png)

The response contains the resource that was requested。

 and it also contains information like the length of the content。

 the content type and headers like cookies。 It also contains E tags。

 The time when the content was last modified。 And finally。

 the response also contains some special numerical codes called H T T P status codes。

 you've surely seen these H T TP status codes， but you might not have known what they are for。 Well。

 they are not really messages addressed to you， the user。

 they actually provide extra information to your browser about the resource。 For example。

 if everything is O， the server sends 200。 you will not be aware of this because it doesn't even display in your browser。



![](img/26b118028d75473615fb4bb7fd1120d8_17.png)

Or if the requested content can't be found， the server responds with the 404 error code。

 which usually displays in the browser because there is nothing else to show。



![](img/26b118028d75473615fb4bb7fd1120d8_19.png)

Here is a range of error codes， and their meanings。100 to 199 are used for informational messages。

 The codes from 200 to 299 are successful responses，300 to 399 provides redirection information。

400 to 499 are client error responses， and 500 to 599 are server error codes。

 server errors are usually raised when the server side code lacks proper error checks in the code configurationration mismatch。

 incorrect package dependencies and so on。

![](img/26b118028d75473615fb4bb7fd1120d8_21.png)

The client side errors usually occur when the client makes a bad API request with insufficient information in the request body。

 or when the client requests a resource that is not present on the server。

 but take note that sometimes the same status codes can convey different messages in different contexts。

 For example， a 200 status code for a get request means the content was found。

 The same 200 code for a put request means that the data transmission and update process was successful。

 Similarlyly， for a delete request。 This 200 status code means that the resource was successfully deleted。

 Some of the most used status codes are 200 and 201，303 and 304。400，401，403 and 404， as well as 500。



![](img/26b118028d75473615fb4bb7fd1120d8_23.png)

![](img/26b118028d75473615fb4bb7fd1120d8_24.png)

You will learn more about what these status codes mean as you move through the course。

 And that brings you to the end of this H T T P recap video that refreshed your memory about H T T P。

 H T T P methods， requests， responses and status codes。



![](img/26b118028d75473615fb4bb7fd1120d8_26.png)

These are the fundamental concepts that you will use to develop sustainable and manageable APIs。


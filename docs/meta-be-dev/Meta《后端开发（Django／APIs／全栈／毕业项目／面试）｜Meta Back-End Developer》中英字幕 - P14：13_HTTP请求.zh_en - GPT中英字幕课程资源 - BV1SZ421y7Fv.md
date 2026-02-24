# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P14：13_HTTP请求.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Have you ever noticed the lock icon beside the URL in your web browser， this means that HTTPS。

 the secure version of HTTP， is being used。HTTP is a core operational protocol of the World Wide Web。

It is what enables your web browser to communicate with the web server that hosts a website。

Most of the time， HTTP is the communication protocol you use to browse the web。



![](img/942faa323d3b16491f4380067d384d75_1.png)

HTTP stands for Hypertext Transfer Protocol。

![](img/942faa323d3b16491f4380067d384d75_3.png)

It is a protocol used while transferring web resources such as HTML documents， images， styles。

 and other files。

![](img/942faa323d3b16491f4380067d384d75_5.png)

HTTP is a request response based protocol。A web browser or client sends a HTTP request to a server。

 and the web server sends the HTTP response back to the browser。



![](img/942faa323d3b16491f4380067d384d75_7.png)

Next， let's explore the makeup of a HTTP request。A HTTP request consists of a method path。Version。

And headers。The HTTP method describes the type of action that the client wants to perform。

 and it communicates it to the server。The primary or the most commonly used HTTP methods are get。

 post， put， and deletete。

![](img/942faa323d3b16491f4380067d384d75_9.png)

The get method is used to retrieve information from the given server。

 the post request is used to send data to the server。

The put method updates whatever currently exists on the web server with something else。

And the delete method removes the resource。

![](img/942faa323d3b16491f4380067d384d75_11.png)

The path is the representation of where the resource is stored on the web server。



![](img/942faa323d3b16491f4380067d384d75_13.png)

For example， if you wanted to request an image from a page in a website。

 then the URL in the address bar would need to contain the full path to that particular file on the web server。



![](img/942faa323d3b16491f4380067d384d75_15.png)

There are multiple versions of the HTTP protocol you won to explore these right now。

 but be aware that versions 1。1 and 2。0 are the most used Finally there are the headers。

Headers contain additional information about the request and the client that is making the request。



![](img/942faa323d3b16491f4380067d384d75_17.png)

Headers can contain information such as the server name， the server port， the request method type。

 and the content type。The contents of the header can depend on the specific client and server。

 but these are some of the most common。

![](img/942faa323d3b16491f4380067d384d75_19.png)

And for certain request methods， the request will also contain a body of content that the client is sending。

Now， let's cover some details about the makeup of a HTTP response。

HTTP responses follow a format similar to the request format。Following the header。

 the response will optionally contain a message body consisting of the response content。

 such as the HTML document， the image file and so forth。

 HTTP status codes contained within the header indicate if the HTTP request successfully completed。



![](img/942faa323d3b16491f4380067d384d75_21.png)

The code values are in the range of 100s to 599， and are grouped by purpose。

The status message is a text representation of the status code。



![](img/942faa323d3b16491f4380067d384d75_23.png)

During your web browsing， have you ever encountered pages that display 404 error not found。

 or 500 errors server is not responding？Let's explore these HTTP status codes briefly and explain about their grouping。



![](img/942faa323d3b16491f4380067d384d75_25.png)

There are five groups of status codes。They are grouped by the first stages of the U number。

Informational is grouped from 100s to 199。Successful responses are from 200s to 299。

Redirection messages are from 300 to 399。Client error responses range from 400 to 499。

 and server error responses are from 500 to 599。

![](img/942faa323d3b16491f4380067d384d75_27.png)

Information responses are provisional responses sent by the server。

These responses are interim before the actual response。

The most common information response is 100 Con which indicates that the web client should continue the request or ignore the response if the request is already finished。



![](img/942faa323d3b16491f4380067d384d75_29.png)

Successful responses indicate that the request was successfully processed by the web server。

 with the most common success response being 200 OK。

You're receiving these responses every day when you receive content successfully from a website。



![](img/942faa323d3b16491f4380067d384d75_31.png)

The meaning of okay depends on the HTTP method。

![](img/942faa323d3b16491f4380067d384d75_33.png)

If the method is get， it means that the resource was found and is included in the body of the HTTP response if it's post。

 it means the resource was successfully transmitted to the web server， and if it's put。

 the resource was successfully transmitted to the web server Finally if the method is delete。

 it means the resource was deleted。

![](img/942faa323d3b16491f4380067d384d75_35.png)

![](img/942faa323d3b16491f4380067d384d75_36.png)

Redirection responses indicate to the web client that the requested resource has been moved to a different path。

The most common response codes used are 301 moved permanently and 302 found。



![](img/942faa323d3b16491f4380067d384d75_38.png)

The difference between the redirection messages 301 and 302 is that 302 indicates a temporary redirection the resource has been temporarily moved。

When web browsers receive these responses， they will automatically submit the request for the resource at the new path。



![](img/942faa323d3b16491f4380067d384d75_40.png)

Client error responses indicate that the request contained bad syntax or content。

 or cannot be processed by the web server。Let's explore some of the most common response codes。

400 is used when the web browser or client submitted bad data to the web server。

401 is used to indicate that the user must log into an account before the request can be processed。

403 is used to indicate that the request was valid。

 but that the web server is refusing to process it。

This is often used to indicate that a user does not have sufficient permissions to execute an action in a web application。

404 is used to indicate that the request resource was not found on the web server。

Server error responses indicate that a failure occurred on the web server while trying to process the request。

The most common code used is 500 internal Ser U。Which is a generic error status indicating that the server failed to process the request。



![](img/942faa323d3b16491f4380067d384d75_42.png)

Have you ever bought something online and needed to enter your credit card information？

You wouldn't want someone else to get this information from the HTTP request， right？

This is where HTTPS must be used。HTTPS is the secure version of HTTP。



![](img/942faa323d3b16491f4380067d384d75_44.png)

It is used for secure communication between two computers so that nobody else can see the information being sent and received。

It does this by using something called encryption。You won't cover encryption right now。



![](img/942faa323d3b16491f4380067d384d75_46.png)

Like in HTTP， the requests and responses still behave the same way and have the same content。



![](img/942faa323d3b16491f4380067d384d75_48.png)

The big difference is that before the content is sent， it is turned into a secret code。



![](img/942faa323d3b16491f4380067d384d75_50.png)

Only the other computer can turn the secret code back into its original content。

If someone else was to look at the code， it wouldn't be understandable。



![](img/942faa323d3b16491f4380067d384d75_52.png)

You use HTTPS every day。This is the lock icon that you see beside the URL in your web browser。



![](img/942faa323d3b16491f4380067d384d75_54.png)

Okay， before I finish， I want to leave you with a brief summary of HTTP。Firstly。

 it is a protocol used by web clients and web servers。

It works to transfer web resources such as HTML files and is the foundation of any data exchanges on the web。

Also， remember that by using HTTPS， we send the information securely。Requests are sent by the client。

 usually a web browser， and the server replies with responses。

 which may be the return of an image our H page HTTP requests have syntax that includes method， path。

 version and headers。

![](img/942faa323d3b16491f4380067d384d75_56.png)

![](img/942faa323d3b16491f4380067d384d75_57.png)

HTTP responses follow a similar format to the request。

 and HTTP's status codes indicate whether the HTTP request successfully completed。



![](img/942faa323d3b16491f4380067d384d75_59.png)

The status code is a three digit number that corresponds with groups representing different types of results。



![](img/942faa323d3b16491f4380067d384d75_61.png)

![](img/942faa323d3b16491f4380067d384d75_62.png)

Well， now you know how the HTTP protocol request and response cycle works。

 you know about its methods and the elements that make up a HTTP request good job。


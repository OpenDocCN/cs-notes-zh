# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p120 31_02_08_暴露自定义监控端点.zh_en -BV11y411z7Dn_p120-

This rust HtTP API has several route several endpoints exposed， one is the root。

 the other one is Redact which is the API endpoint and it has a custom slash health so similar to Prometheus that exposes metrics。

 you can definitely add a custom one now adding a custom one is something that is interesting you might want to run。

 for example dis applicationplication behind a web server， something like NX for example。

 and you can set loadbal strategies I've been in environments before where we had different services running behind an NX web server and we would expose like a specific endpoint to make sure that that that host was able to receive request and produce actual good solid responses and behave correctly now when we wanted to take something not a rotation。

 we wanted to have two behaviors。

![](img/f7449310752a3f55b265b0b0d81eec64_1.png)

wa automatic like if something if there was no space in the disk， for example。

 that weve had that problem before， then NngX wouldn't be routing it wouldn't be routing requests to that endpoint server。

 So if the hell failed then that wouldn't that wouldn't proceed that request wouldn't proceed and we go to another node and we could scale horizontally no problem Now what are things。

 well， that's the automatic behavior， but we also wanted to have manual behavior。

 we could place a file thats say error and then it would take it would be an immediate 500。

 I'm going to scroll the way all the way to so you can see the actual endpoint and the endpoint is this one。

 this is the function。 It's a hell function and implements a responder which is something for Actx web which allows us to respond with an HCP response。

 All right， so let's take a look at what we have here。

Create some checks and we produce some system up time so if we start the service and we say if we say toggle the terminal and we do cargo run that is going to run on local host。

 So I'm going to do curl and I'm going run curl and'm going to do a get request to local host I'm going to type in0 that0 that1 and I know this is running on board 8080 and the endpoint is health。

 So if I do that you will see that there's up time and memory usage and like I'm getting some information so that's fine and that is all coming from not the test if I scroll all the way that all the way up to the function that implements the health status I'm going to close these panel so you can see here memory usage。

 this usage and you know it' producing some useful stuff。

 So now what I want to add is that custom file implementation。

 So if a file exists in the file system it will immediately。Be a 500。

 And then we're going to produce produce an error。 All right， so I'm going to say。

Implement a file based health check。 So I'm going to do I'm going to do that and I'm going to explain in a second what that means。

 allright， so that's what I have。 So return now 500 file exists in the health directory actually this is not going to be in the health directory is going to be in the same place where this web server is running。

 So if， I mean， in production， you probably want to have like an absolute path in this case。

 this is hard coded to just error text it means。Wherever I'm doing cargo run。

 it will require to have this file in there。 So if that exists， I'll get an internal server error。

 So perfect， if I save these and then go back to the terminal。I'm going to say toggle terminal。

 and then I'm going to control C out of this， I'm going to do cargo run。

So I'm going to build this thing again if I do。If I do curl again。

 I still get everything that I need， but if I touch error that text and I do my curl request again。

 I am going to get I'm going to get a 500 if I do a vervo highly ver curl request you will see that I'm getting the internal server error if I remove the error file I am going to get my 200 back again again say error that text again curl I'm going to get internal server error so again this is a good strategy if you want to implement or roll your own kind of like health endpoint that you can use with。

 for example， load balancers。

![](img/f7449310752a3f55b265b0b0d81eec64_3.png)
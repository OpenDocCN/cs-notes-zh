# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p118 29_02_06_在Rust中添加Prometheus端点.zh_en -BV11y411z7Dn_p118-

![](img/541f64ebca3375a4a2aeded698d2db00_0.png)

I have here a web application and HttP API using rust and I'm going to add Prometheus and I'm going to start by showing you cargotel so that you can check the dependencies。

 I am going to add the Acts web prom pro standing for Prometheus and this is Acts web the framework for sure like I'm using 4。

0 here and how we're going to do this is with this crate Now the interesting part about Acts web prom is that it is a middleware by using a middleware we can do lots of different things。

 This is going to take care of all of the formatting and all of the expossing of the endpoint for me instead of having to configure that by myself now remember Prometheus requires to have like a specific endpoint in the application that's what I're going to see next and。

We're going to start all the way to the top and we're going to get what we need right here at the top and I'm going to use Acts where prom and from there the only thing that we need is the Prometheus metrics builder so that's what we need to get started and as you can see is going to be gray because I haven't used it yet no problem I'm going to save that and then I'm going to scroll all the way to the bottom where the sync function main is defined so ignore all the clutter that is going on and these application has already a few endpoints right there like the root of the page or the HTP API has an endpoint here and another one that saysHe no problem and let's see how we can get Prometheus on these applications。

So the first thing is we need to instantiate this variable。

 we need to call the Prometheus metrics builder， so I'm going to say we're going to call this Prometheus。

And this variable is going to come from the Prometheus metrics builder。

 Now compile is already suggesting some things there， but we don't want to call it this way。

 We have a particular way that we're going to use。 and yes。

 we're going to say Prometheus matrix builder new。And we're going to call this redactor。

 which is the name， the actual name of the project。

And then we're going to add the endpoint is going to be slash metrics I'm going I build it and then unwrap and then that is going to define how this is going to be constructed。

 the endpoint is going to be slash metrics， which is essentially kind of like the default for Prometheus。

 Prometheus is going to go to these endpoint and fetch fetch that information remember Prometheus is a system it's a pull system。

 So our little application here can live in a container and just by exposing these will be fine because Prometheus will be pulling from that metric all right。

So we have that。😊，The next thing that we need to do we need because it's a middle where we need to put it inside here where we're creating our HtTP server。

 So our HttP server will need to have here a move， and then we will wrap we' wrap around what we have here。

 our applications we have app double call new and when I say when I wrap these Prometheus clones we're going I clone that and then we're going to save it。

And and then let's say thats that is effectively how this is going to work。

 This is going to run on port 8080。 All right， so now let's toggle the terminal。

And let's see how we're doing we're gonna clear there and go all the way to the tops。

 I'm gonna to say cargo run and this is going to build everything and going to run our application on port 8080 All right so we don't have login we don't have anything this is actually running so let me bring a web browser So I'm bring in my web browser here and you can see that that's running on a local host port 8080 and this is the service and it has a redact here post and that is a 404 because it's only accepts a post and there's a health and then that's fine it has certain things。

 it doesn't have anything for metrics。 Let's actually see what happens if I go to metrics。

 and if I click metrics you will see that well there's some things going on。

 This is the standard format for Prometheus is。Pretty common all of these things I'm getting by default fault。

 I didn't configure anything。 This is all that you get with the middleware by just adding it。

 so you're gonna to get Htp request duration seconds bucket you can see that everything is prefixed by redactor。

 which is the name of the project which I added you can see request duration in seconds So kind lots of different things and then we can we can even look at what's the endpoint what's the method and what's the status so we should probably be getting 405s here perhaps even some some 404 if I start requesting this' actually request something that doesn't exist So if I say metrics like that that doesn't exist that should be a 404 So now if I reload these we'll start seeing the 404 see that 404 right there well that we're making progress and we can actually get that all set up for。

For us so if I go back to the code， the terminal doesn't tell us much so if I minimize this and actually I can even close that pane。

 we didn't add much right we started here sorry for the scrolling we started here by defining Prometheus we wrapped our application because it's a middleware we cloned it so that we don't have ownership problems we use move and if we are scroll all the way to the top then the only thing that we added was the Prometheus matrix builder so that's it in a nutshell how you can expose a metrics endpoint for Prometheus。



![](img/541f64ebca3375a4a2aeded698d2db00_2.png)

![](img/541f64ebca3375a4a2aeded698d2db00_3.png)
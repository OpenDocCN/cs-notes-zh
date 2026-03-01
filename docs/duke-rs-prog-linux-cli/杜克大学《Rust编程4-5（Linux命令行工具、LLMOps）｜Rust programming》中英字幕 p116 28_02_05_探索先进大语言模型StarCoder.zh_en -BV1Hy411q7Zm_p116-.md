# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p116 28_02_05_探索先进大语言模型StarCoder.zh_en -BV1Hy411q7Zm_p116-

![](img/2f480172e9c8603c8ff604482fc3e654_0.png)

Here we have Hugingface star codeder， which is surprisingly more interesting than I even originally thought and I was very interested in it。

 What I'm going to do is walk you through first what it does。

 So it's a model that is similar to other generative AI models for coding like copit for example。

 but it's completely open source and you can see here it has 15。

5 billion parameters and was trained on 80 programming languages from the stack here。

 So pretty exciting。 And if you look at the mission here as well。

 it's an open scientific collaboration for code LLms and you can work on it as an AI researcher。

 let's say you're working in the university system this would be an interesting thing to do so the goal here is that they're going to release datas models experiments so that it's democratizing the generative AI revolution not just putting it in the hands of venture capitalists So if we go ahead and look at this star coder base here1b。

This is a smaller version of it， but it worked very well with hugging face candles。

 Here you can see that Huging face candle， a rust based minimalist MLl inference project can run star coder。

 So you can see here， this is a specialized LLM for code generation。

 and it's pretty straightforward to authenticate with once you've got the initial hugging face tool installed。

 So again， if we go over to。😊，One of the demo projects I have， I have the information right here。

 Pip install Hu face hub， and then you a log in。 So if I go over to my codespaces environment。

 I can actually see this in action Huging face。

![](img/2f480172e9c8603c8ff604482fc3e654_2.png)

See a lie， and I said， who am I。It shows that I'm actually authenticated and I can actually use this project。

 but because I'm going to do something on a very intensive GPU。

 it's going to require something a little bit B here。

 I'm going to move over to a remote visual studio code environment that's running a G5。

 which is a new generation GPU from AWS。 So if we go over to this environment you can see here I'm doing a remote session here and then we can again verify what's happening so I can type in hugging face CI。

 who am I。

![](img/2f480172e9c8603c8ff604482fc3e654_4.png)

There we go。 We see that I'm logged in。 Now， in order to run this thing。

 what's kind of nice about this is that if I wanted to， I can open up a second window。

And paste it above。 and I could see how much GPU is actually being saturated。 In fact。

 I can even open up another shell here and do H top。And you can see here a woo， look at this。

 We have， you know，64 cores。 This is a， this is a big machine。 And then if I wanted to。

 I could also do Nvidia， S M I。Dash L 1 to loop and check out the GPU。 Now that I got that cooking。

 I can just run the command that will actually allow me to to basically test this out。

 So let's go ahead and walk through step by step。 What's actually happening。 So I do cargo run。

 And this is a typical command that you would do to execute something in a project。 Now。

 notice I'm saying features Kuda。 and I'll get back to this in a second。

 So what this means is that I'm using the couda drivers that are already installed on this Aws deep learning base Ami。

 I'm passing it in the big code example。 So this was the Hugingface project earlier。

 I'm then also passing in the prompts。 In this case。

 this would be a rust function that adds two numbers now。One thing I'm going to show you is that。

 in fact， if we want to get optimized performance。Because the couda in in drivers are installed。

 it it's a version of couda that's optimized for working with neural networks。

 So we actually want to use that to speed it up even further。

 So if I'm going to be using this all the time as a coding assistant Why not's go ahead and use the most optimized approach possible So I'm going to say。

 look， I need to find a rust function that adds two numbers。 Okay。

 let's go ahead and do it and you can see this thing in action and watch this。

 you'll see the GPU getting triggered right here and then we'll get a result that tells us a rust hint on how to build a function and rust that adds two numbers。

 There we go， we see saturating the GPU here。 Now let's go ahead and and switch it and let's say Python function that adds two numbers。

 and you can see here that。It's going to go through again。Give us another suggestion here。

 and we could say Ruby function that adds two numbers。If we wanted to even time this。

 you can see that it retrieved the files in microseconds here， I think。

 and then loaded the model in about two seconds and then it started the inference loop。Really， the。

 the amount of time that it took to load the model seems like it's the the bottleneck here。

 which is still not that bad to， to pull in that model。

 but it's able to give us pretty reasonable suggestions here based on this。 And， and we could， again。

 keep going through here and doing ja， for example。So this has a lot of promise， I think。

 for people that are interested in you know really doing their own open source。Coding assistance。

 and you can see here pretty straightforward actually because of the power of rust and also the hugging face ecosystem。



![](img/2f480172e9c8603c8ff604482fc3e654_6.png)
# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p122 34_02_04_Rust聊天推理.zh_en -BV1Hy411q7Zm_p122-

![](img/0c6675accec12f12a870121a010e2345_0.png)

Let's take a look at how you could build a rust chatbot for large language model inference using some of the plug and play components in the rust ecosystem。

 First up， you could look at using the Falcon model which is a great place to start with。

 and this could excel that natural language conversation and then you could load that model into a rust program using something like candle。

 a rust bird， etc cea， which has access to the huggingface models。

 Then you could integrate that conversational model into a rust chatbot。 So how would you do this。

 Well， we could build a chatbot UI with a crate like cursive。

 which is a terminalbased interface in rust， and this could take user input and print bot responses。

 that core chatbot logic loop within continuously prompt the user for input that could take their input text。

 pass it to the huggingface model loaded earlier， and then print the model's response。

 and this huggingface model would handle all。The natural language processing。

 analyzing the user input， generating a coherent response and even accounting for conversational context and the Ru code is a facilitation of this interaction the additional logic could be added for things like sentiment analysis to make the responses more natural and the interface could be adapted even into a web application later after you first had this prototype。

 So in a nutshell here what you want to do is select the appropriate model from hugging face in this case maybe youd choose the latest Falcon model。

Loaded into rust， build that chat by UI， then implement the chat logic with the hugging face model and then continuously prompt and generate responses。

 So it's an exciting time to be a developer because we can plug all these tools right into a command line friendly language like rust。

 which is really unique and that it has so much power for building binaries。



![](img/0c6675accec12f12a870121a010e2345_2.png)
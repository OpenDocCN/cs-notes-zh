# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p87 87_04_05_AWS Lambda函数URL详解.zh_en -BV1Hy411q7Zm_p87-

![](img/d0cbc0fdecbc7c34f042932fa627a055_0.png)

Here we have an example of how to use function URLls。

 which is a great feature of Aws Lada with the high performanceform rust data frame library polars inside of Aws Lada here。

 you can see there's a convenient URL scheme and you can invoke this once you've deployed your code。

 So a few things to be aware of is that the structure is httbs URL hyphen ID Lada URLl region do on Aws。

 really， that's the idea here。 and there's a couple different forms of authentication。

 One is Aws I am。 and the other is just nothing and you can test a request with your browser or even using a tool like curl you also can do a request payload format so you can actually send a request in a detailed Json object and you can put different properties。

 etc ce。 Now the response that comes back is a specific format and it's going to have status code head。

😊，Bod cookies and also an indicator for base 64 encoding and Lada can interpret the different types of function output like a string response or Json and map them to the appropriate response Now in terms of security and authorization again。

 depending on what kind of authentication type you want， let's say AWS I or none。

 you may need to sign the request with Sigv4 and you can use tools like AWs curl or Postman。

 Now in terms of region and IPV4 or IPV6 support。 these are also enabled as well depending on what region you're in。

 So in a nutshell， this is a great way to expose high performance data frame libraries using rust inside of AWs Lada。



![](img/d0cbc0fdecbc7c34f042932fa627a055_2.png)
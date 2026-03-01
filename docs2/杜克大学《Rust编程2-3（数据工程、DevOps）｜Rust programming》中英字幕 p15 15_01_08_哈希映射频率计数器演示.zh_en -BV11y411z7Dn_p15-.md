# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p15 15_01_08_哈希映射频率计数器演示.zh_en -BV11y411z7Dn_p15-

![](img/15ecf944ada76c916683b11833151277_0.png)

Yeah。All right， in this demo， I'm going to show a hashmap frequency counter demo。

One thing to consider about hashmap is it's very similar to a Python dictionary and a good use case for it is to have a frequency counter or to count things in general。

 and it has O to the one time complexity for insertion， deletion and access。 So it's a great。

Really multipurpose data structure in rust that you'll use quite frequently。

 And they're great for tasks that require a quick look up， like counting occurrences of items。

 So it's go ahead and walk through this code here inside of the main。 We've got a hash map inside。

 And then I have a function here called logic。 And inside it takes numbers， which is a vector。

And I say let mute frequencies。 and then I go ahead and create a new hash mapap。 Now， inside of here。

 what I do is I count the frequencies here by doing an incrementer And then when I go ahead and I look at the results。

 I return back a vector to make it a little bit easier to push out the results。 And finally。

 here is the main invocation here in the main function I say let numbers and I create a list of numbers so notice here I say 1。

2， 3，4，5，6，7，8，9。 and then I include a couple of duplicates so that I am able to verify that is going to count the frequency correctly。

Now， this could obviously be a huge string of numbers， but just for a demo。

 I'm going to make it pretty simple。 And then I go ahead and I call that other function above。

 So this is a great way to organize your code in rust is to have a little bit of logic somewhere if it's a simple script。

 if you're not going make a Lib Rs and then call it from the main function that way。

 the main function isn't this huge mass and it's hard to read and then I go through here。

 and I print out that frequency of each number so that I can explain what it is I'm doing because if you just print out a vector。

 for example， it would be a little bit difficult to understand what does it do So it's great to put a message here that says exactly what I'm doing。

 So I'm going to go ahead and type in cargo run。😊，And you can see here it says the frequency of each number in the vector is。

 And then we can see one occurs two times right here， right because we know one is here。1 is here。

 and we can say five occurs once，7。 So everything occurs once except for one and3。

 which should have two。 And of course， that's exactly what happened。

 So a very useful general purpose data structure pretty simple to use as well。

 is a hash mapap it has great performance。 So between a hash mapap and a vector you can really do you know a wide variety of things in rust。

 And these are probably the two data structures to focus on the most。

 And they have a lot of similarity to how you would do things in Python。😊。



![](img/15ecf944ada76c916683b11833151277_2.png)
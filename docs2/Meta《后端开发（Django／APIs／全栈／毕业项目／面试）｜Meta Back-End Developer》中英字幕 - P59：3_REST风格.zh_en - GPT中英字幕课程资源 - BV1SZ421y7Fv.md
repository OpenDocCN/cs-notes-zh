# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P59：3_REST风格.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Now that you've had a refresher on H T TP and H T TPS。 you are ready to learn about RE As。 But first。

 you need to know what is rest。 In other words， what makes the Apis restful。

 an API or application programming interface is a gateway to back end data。

 It allows you to easily access and modify this data。

 And rest is an architectural style for designing Apis for your project。

 It is hugely popular among developers because it's much easier to develop and implement than other architectural styles。

 What works in your favor is that the learning curve isn't steep。

 and you can create production ready Apis in a short time。 but let's not jump too far ahead。

 Youre not quite creating Apis yet。 Rather， you are first learning about the basics of rest As。😊。

Rest APIs provide an easy way for you to communicate with the server and access the data that powers your application。

 But an API is only restful if it complies with certain constraints。 Let's examine them。

 It must have client server architecture。 A rest API is always stateless， and it should be cashable。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_1.png)

![](img/622cc7ff37e532cad6bc0b3d6235b45f_2.png)

It should be layered， have a uniform interface， and it might also include code on demand。

 but this is optional。Let's explore each in more detail。

The API should use client server architecture。 There should be a server that is serving the resources。

 and there should be a client who consumes them。 A rest API is stateless。

 This means that the server does not contain any state of the API client who is making the call。

 So it cannot identify who is making the request or what their previously requested data was without proper user information。

 In fact， the state is only saved on the client machine， not on the server。

 and this influences what you should include in your API's endpoints or URL paths。

 but more on this later。

![](img/622cc7ff37e532cad6bc0b3d6235b45f_4.png)

The API should also be cashable。 This means that responses can be saved by a web browser or a server or any system。

 This caching process can help to reduce the server load by using the API result from the cache instead of making an actual request to the server every time。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_6.png)

![](img/622cc7ff37e532cad6bc0b3d6235b45f_7.png)

Layed means that the entire system architecture can be split or decoupled into multiple layers。

 and you should be able to add or remove a layer at any time。

 The following diagram will make this layering more understandable。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_9.png)

Layers of a restful API system could include a firewall， load balancer， a web server and a database。

 Let's move on to the constraint of having a uniform interface。

 This may sound a little confusing at this point， but it means that the system should offer a uniform communication system to access the resources。

 For example， there should be unique URLs for each resource。

 There should also be a unified way to modify or proceed further with a resource from the API result or representation in a standard X。

 M L or Json format。

![](img/622cc7ff37e532cad6bc0b3d6235b45f_11.png)

Lastly， code on demandd means that the API may deliver some business logic or code that the client can run to further improve the response result。

To understand this code on demand feature， consider the following script tag that loads some jascript code from an API endpoint of the little Le restaurant。

 Once loaded， this script can display any special menu items for that day。 For now。

 these six constraints are just theoretical。 Do not let them confuse you。

 Once you start developing your APIs。 These terms will become clear to you。 Next。

 let's focus on resources。 Res are a core part of every rest A。

 So it's important for you to become familiar with how As present resources。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_13.png)

![](img/622cc7ff37e532cad6bc0b3d6235b45f_14.png)

![](img/622cc7ff37e532cad6bc0b3d6235b45f_15.png)

Say the little Le restaurant has a mobile app， which can be used by customers and managers。

Managers can use the app to get information about orders and customers while the customers use this app to browse the menu and place orders to support this。

 the app uses different APIs to fetch data from the server。

 and in each case the resource type will be different。 Let's explore a few examples。😊。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_17.png)

If a manager wants to see all orders， the app makes a call to the API little dot lemon forward slash orders and displays the result。

 The resource type in this case is a list of order objects。

 If a manager wants to view more specific information about a particular order。

 say the order with the I D 16。 The app makes a call to the API。

 little dot lemonmon forward slash orders forward slash 16。 The resource type is the order object。

 to see who placed the order。 The app makes an API call with an extra filter， forward slash customer。

😊，This retrieves all the details about the customer of that order。

 The resource type in this case is the customer object。

Say the manager wants to look at what the menu items of order number 16 were。

 The app makes an API call that replaces forward slash customer with forward slash menu items。

Only the menu items of order 16 will show in the result。 And this time。

 the resource type is the menu item object。 Now， on the other hand。

 if the customer wants to browse the menu， the app uses another API little dot lemon forward slash menu items。

 And although the resource type will also be the menu items object。

 the return will be all available menu items of the restaurant。

 but sometimes the resource type is the same， although the result can be filtered to be more specific。

Let's explore a final API to unpack this。 This time。

 the customer wants to browse food items from a specific category， say appetizers。😊。

The app will add question mark category， equal sign appetizers。

Notice that the end point is the same as the previous API。

 but it filters the output to only appets for both cases。 However， the resource is still menu item。

 object。 Now that you've explored a few examples of API resources。

 let's revisit the rest API constraint of statelessness。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_19.png)

You need to keep in mind that the server always represents only what you ask for。

It does not remember anything of what happened before。 For instance。

 if the manager retrieves the information about order 16 and then wants to look at the menu items of order 16。

 you cannot just send a follow up H T T P request to the endpoint forward slash menu items。

 because this API will return all menu items and not just the menu items of order 16。

 The server does not remember that your earlier call was for a specific order。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_21.png)

If you want to get the menu items for a specific order number。

 you need to explicitly supply that order number to the server as orders forward slash 16 forward slash menu items。

 in simple terms。 This is what stateless means。 The server cannot recognize the client automatically。

 A calls must include more information about the user。

 but you will learn more about this later in the course。 In this video。

 you have learned how to create rest Apis by following some key constraints。

 you also learned about the core parts of rest Apis like the resource types。😊。



![](img/622cc7ff37e532cad6bc0b3d6235b45f_23.png)

These conventions will help you build APIs that are easy to use and maintain。

 but there is a lot more to learn on how to optimize your As， for instance。

 using the correct naming convention， but more on this in an upcoming video。


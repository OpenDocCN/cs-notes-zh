# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p54 p53_04_implementing-the-post-method-to-create-user-resource -BV1fryaYgEqb_p54-

Hi there。 today in this session， I will tell you how to implement the post method to create a new student as a resource。

😊，And I will also tell you how to pass the query parameter as well。 So let's get started。

First of all， I am going to my student controller and the same implementation I have told you to return the student first name and last name with the help of path variable getting returned with the help of query parameter that's a get mapping。

Here， I would like to get the student。There I need to pass the query。

And depends what you would like to pass in that particular query。

I would be passing first name and last name so that's public that will return the student object and the student with the query parameter needs to be returned。

Here two objects Im returning。 Thats request par。That will take the parameter name， as first name。

Will be stored up into the string force name。Videable。Same thing I need to do for last name。

 That's add request。Badom。The name of the parameter would be last name。Variable could be string。

 last name。And whatever values I will get from the query parameter I need to return as in student object with the help of the parameterized container。

 course name and last name。Let me tell you， how can you pass these iterations so as I have told you earlier。

You need to open up your Chrome browser。Going for a request。 But before that。

 I need to run my application， So just。Let me open up the terminal， terminate my request。

So I can see that there is no request getting executed for the time being going back to the application and running the application。



![](img/2ec51d8e90d92f35326f4f61b66708a7_1.png)

So here， if I will make a request for local host 8080 list of students that will return the list of all the students。



![](img/2ec51d8e90d92f35326f4f61b66708a7_3.png)

I can make the comments for your student controller by the method request URL。Next。

 if you would like to pass the path variable， you can pass the path variable like this， Babna Grani。

So you can see that it's not working because it's Babna Gvani is a student， not a list。

So I can just make a comment to this URL as well。Next is a query parameter。

 How you need to pass the query。 First of all， let's understand that。So before passing up the query。

 you need to say student。And then the query variable that you have written。

 then question mark what query parameter。You are exposing into your parameter list。 That is。

 let's say， John。And if you have multiple parameters， append them with the help of the and operator。

 and there is a Smith。So you can see that the John Smith is Englishtan。

So that's the way you can pass your query parameter to your get request as well。

In case you wanted to add a new student as well。 So in that case， you can just use the add method。

 whatever details coming up right here。For example。I'm creating a post mapping。

Making the same URL for the post mapping that's a student。Public void。A student。Here。

 rather than query parameter or the path variable。Waiting for the request body that will be sending the objects of student。

From the request body of any of your client site， I will be using post man。

And here I would like to say， I only have a list of students in which I would like to add the student。

So first of all， I will terminate my application this way。

Then I will go to the application and run the application once again。

I need a postman to test my post request because by default。

 when you make any request from the browser， it goes to the get request for post port delete you always need a client。

So here is something what I can do is let me just close all of them。

Creating this request where the URL I can copyright from here。Student。

I need to tell that the header of the request， it means in which particular content type I will send the data content type is application slash GSson。

And the request body that you need to pass would be in the Jsson format only。

 So here I'm writing the first name。Let's see， Rogerger。And the last name。That's Lee。

 It's a roger Lee。Now， let me send a request。So you can see that it is saying 405 method not allowed because it is a post request I also need to change the method。

And here you can see that I'm getting the status 200， I'm returning nothing。

 so it's not printing anything in the response body。

 but I can verify over the browser by putting up the student list request whether my student gets added or not so you can see that the roly is successfully added。

 so that's how your post API work that that I have created in the string。Stay tuned to learn more。

See you in the next session。

![](img/2ec51d8e90d92f35326f4f61b66708a7_5.png)
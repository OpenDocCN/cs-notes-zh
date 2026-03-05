# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p53 p52_03_implementing-a-get-service-to-retrieve-user-resource -BV1fryaYgEqb_p53-

![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_0.png)

Hi there today in this session I will tell you how to implement a get service to retrieve the student wean or a student receivers。

 so lets get started。

![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_2.png)

Here I simply right click on my application and I will create the class。That is the student class。🤧嗯。

Under Comd Pavna Gvani。Dot beans or model， whatever you create。

Under the student class I am creating two properties， one is first name of string type。

And another is string last knee。Here， I'm going to。Generate the constructor。Using both the fields。

Gter and setter。Using both the fields。2 string method。

So that you can print the object whenever needed。Although not required， but Im also generating。

The default constructor， too。So， here is my full。Poc class gets ready。

Now I will go to the controller package and create a student controller。Student controller。Again。

 I will make this as a rest controller。You should not have this controller with a default request。

 because if the two controllers will have a default request your。Thebugger will get confused。

 So here Im directly creating a get request for the student to get the student。But before that。

 I'm creating a list of students。Public static。List of。Student。

Then I am creating a method that will return a list of student。That is， get students。

Making this method with， as in get mapping。When you will request for students。

 it will return all the students that you' are going to add into this method。

If you would not like to initialize your methods， students right here。

 what you can do is you can create the student controller constructor。And inside this。

 you can add the students， students start add new student。

Calling a parameterized constructor that is king coachcher。Sya Sharma。And Sarah Bowling。John Smith。

And gotemella。Would like to return this list of students from this particular API that will return the list of students right here。

We can now make a test of this API。First of all， you need to go to your console， terminate。

Your port because otherwise it will give you the error that 8080 port is in use so you could not test your API。



![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_4.png)

So now here I'm making a request to get a list of students。



![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_6.png)

Now what next I can do is I can make another request that will return a particular student。

Based upon a particular I D。So I can go to the student， I can use a path variable or request Par。

 so let me first tell you with the help of path variable。Making a gap mapping request。

Where I say that if someone will look it up for student。And would like to pass the first name。

 and the last name。Boot。This way。Then， the public。This will return one student object student with path variable。

Will be returned here Pa variable will be2。Path variable 1 will take。The path variable with the name。

 first name that is inside the variable string， first name。

Second path variable would be the second last name。 That's a path variable。Last name。

That would be string last name。So， this will return。The student。

 based upon this first name and last name， first of all。So I can say new student。Whatever first name。

Our last name you get in the parameter， you just need to return those details。Let us check this API。

Going back to my application and running my application， as I said。

 I should terminate it before running it up。

![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_8.png)

Calling right here， student。Let's say first name is Goham， and last name is Bla。 So as of now。

 I'm not checking with any of the user， whether with the help of the get request or the filter methods。

 you can pass anything， even though you can pass Pabna Gvani， It will print you these details。

 So that's how your path variable works。

![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_10.png)

You can do the same with the help of the request Par， which I will tell you in the next session。

 so stay tuned。See you in the next session。

![](img/e5d4ccd3b93a9075ab1d4dc17d1c77fd_12.png)
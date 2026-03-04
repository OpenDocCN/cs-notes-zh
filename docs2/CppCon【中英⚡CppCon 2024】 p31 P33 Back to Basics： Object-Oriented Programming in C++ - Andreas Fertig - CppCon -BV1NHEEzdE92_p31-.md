# CppCon【中英⚡CppCon 2024】 p31 P33 Back to Basics： Object-Oriented Programming in C++ - Andreas Fertig - CppCon -BV1NHEEzdE92_p31-

I think it's great， I think it's definitely like a good idea if you're like looking to get involved in the C++ industry to come talk to the people。

 to meet everybody， you never know what can happen。



![](img/24202a9b611b0b57bc02087dc23ae391_1.png)

![](img/24202a9b611b0b57bc02087dc23ae391_2.png)

![](img/24202a9b611b0b57bc02087dc23ae391_3.png)

All right， hello， everyone， Wele to my back to basics talk about object orient programming。



![](img/24202a9b611b0b57bc02087dc23ae391_5.png)

I'm Andreas Perik。The one who created a tool called C++ Inights。

 We will see that during this talk a few times to peek behind the scenes。

 I've also written a couple of books about C++。 I think they are out of them here to cash。

 but we can still fetch them online or on Amazon。

![](img/24202a9b611b0b57bc02087dc23ae391_7.png)

My day job is providing training services， so I'm available for inhouse classes onsite or remote。

 whatever you prefer， I also work together with the CPP Khan Academy here which hosts P and post conference workshops it's a very short notice but you can technically still book my post conference workshop happening。

Tomorrow and on Sunday about more than efficient C plus plus you still have a chance to book Nikolaai you sits class。

 It happens， I think only on Monday， so it gives you more time and it's online。 So more feasible。

 If you want to prefer to learn more at your own pace。 I have a cell study course。

 It's practically a recording of my classes it's about C plus plus 20。

 So you might want to check that one also as well。 I'm German。

 I now met a lot of people during this conference in and other conferences who either speak German are German or at least understand a little German。

 So you might be able to tell from my last name。If you're not。

 you can translate it to English as finish， already， complete or complete it。

 So I think it's a very nice， positive name， right， It's an adjective in German。Of course。

 frequently， in the language。 and when I was younger。

 I made jokes with my friends how rich I would be or the rest of my family if you would get a cent every time when somebody uses our last name。

 Right， so trademarked。 It's not happening luckily。 But whenever I give these talks。

 now I'm looking a bit more into my last name。 And I recently discovered a following。

 we had the Summer Olympics in Paris， which wasn't what I discovered already knew that。 But it was。

 I would say the first time that I realized that the sequence they showed when they start a race or swimming。

 is ready steady go。And I just taught you the translation of my last name。

 you can translate it too ready， so whenever they start a race， not only at the Olympics。

They start a sequence with my last name。Quite interesting。So before we dive into C++。

 let's continue with this other language lesson， I just taught you how to translate my name to English。

 right， How about translating that sequence to German。Are you ready。Steay。Go。

 this is how it looks in German。You would have failed translating that， right？So ironically。

 we start a three sequence part with three words， so you have to listen them very careful in German。

 otherwise you would start to race too early and then my last name goes second it makes sense if you look deeper into the language but。

It only shows me that languages are an interesting thing and can be complicated。

 it doesn't matter whether it's the spoken ones or the ones we just use on our computers， right？

So let's dive into what you are here for potentially not the best German trainer。

 I guess I suck better at C++ Chma wise than in my own language。

So it's about object oriented programming so let's start with the basics a class I assume you already a familiar with that you saw that so we start object oriented programming in C+ class usually it was a class because it's about encapsulation we want to model objects so we start by using the keyboard class given the class a name in my case here Apple and next we have the decision to make in which access regions do we want to put things we have practically three different choices there we can say。

Something is in the public scope that means visible and reachable by everybody。

 you can also put it in the private scope to say it's only reachable and visible to this class。

Wwhich is the main thing about object and programming。

 we want to live in a world where we have this encapsulation we can have private data to the class and can control the access to these individual members。

 which is a different thing， for example， compared to Cstructs where everything is accessible。

We have technically a c kind of specifier that's protected that comes into play when we derive from a base class。

 then protect it means that whatever in that scope is not reachable by。

Anybody else other than the class declared it and all its derived classes。

 so this is how you can give your relatives more access to your private data than anybody else。

Assuming you don't share everything on Facebook you do， that might be something you want to go for。

Now since class about having private data in it， we can also see at the bottom of this class in Q here we have a private data member right。

 you should always have a good reason to declare data members public because one thing about the class is having the things private and having access。

Conunctions chew down。Since that we require a constructor which you see at the top in D here。

 since this is a one argument constructor and marked it explicit because one argument constructors are also referred to as converting constructors and the compilea is allowed to use them whenever it's looking for a conversion sequence and to not make that happen。

 well， unwanted or unintentionally， we tend to say best practices to make our single argument constructors explicit unless we really want this conversion to happen。

Now， once we reach that point， it's about initializing the data members。

 and I show you that in C here， I start a sequence with a column。

 this is the socal constructor initialize a list。Please， please。

 please initialize your data members there。Always。This is the place to do that。

This is the place where it will all happen if you have an object in your class that's default constructible and you move your initialization into the constructor's body。

 it will still be initialized in the construct's initializer list， you cannot prevent that。

You will fail if your type in the class is not default constructable。

 then you will look at a compiler error message because the compiler always tries to initialize the objects there。

 So this is where you should put them。 Otherwise you simply risk and then the initialization happens two times。

So this means indeed D here we have the constructor's body and the constructor's body's purpose is to be there to ensure imvariance。

 we will see an example about this in a few slides。

Then I have the two member functions here set and get to one， as the name says。

 is to set the data member， the only one I have in this class， the other one is to fetch its value。

The one difference between the two you can see is set here is just written out like a normal function。

 while get comes with a constant at the end of the function declaration。

And that signals to your fellow developers to yourselves and to the compiler that when we call this function。

 the state of this object does not change。 This is the promise you're getting。 Okay。

 so this is something valuable， you might hear something like terms like con correctness。

 where we can build chain un constants objects。 So whenever you have a getter that does not modify the state of your class。

Be kind， make it constant， it's the correct sick to do。

Down there in mainine then you can see I'm using this Apple object。

 I use Alice here as one sort of apples and I call sat and get respectively on this Alice object。Now。

 let's use C++ insights for the first time here to pe a little behind the scenes。

For those who haven't seen C++ insides， this is how it looks。

 you can also use the command line version， its main purpose is you put in C++ source code on the left。

You get C plus plus source code out on the right。 it's brilliant， right， million dollar idea。

 Nobody paid for that so far。 The The real thing that C+ plus Ins does is it annotates。

What it sps out on the ride with the things you compiled us to you in this specific case。

 you pluspo insides， looks on everything with the eyes of clan。

You have a default mode where you can translate that。

 I have also a special mode enabled which says shows C++ to C transformation。

 I apologize that in front of a C++ crowd I will show you more C code but the purpose here is to help you understand how classes internally really work and you can see a couple of comments here for the。



![](img/24202a9b611b0b57bc02087dc23ae391_9.png)
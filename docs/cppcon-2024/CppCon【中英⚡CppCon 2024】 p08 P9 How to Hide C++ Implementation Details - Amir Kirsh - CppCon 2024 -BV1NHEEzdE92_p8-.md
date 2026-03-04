# CppCon【中英⚡CppCon 2024】 p08 P9 How to Hide C++ Implementation Details - Amir Kirsh - CppCon 2024 -BV1NHEEzdE92_p8-

This one in particular， it's at a beautiful venue， pretty much everybody staying in the hotel here。

And so that means， you know， after the sessions， people are going out and getting a beer。

And continuing the conversation。And it's just a great way to experience。



![](img/0c8687e8e3dbf7d1536533d7fbfd336c_1.png)

![](img/0c8687e8e3dbf7d1536533d7fbfd336c_2.png)

Good afternoon。 and thank you for coming。 We are going to speak about hiding your implementation details。

 A few words about myself。 I'm a lecturer at the academic College of Telvivia and Telvivia University。

 a member of the Israeli Io C plus plus National bodydy。

 I'm also the organizer of the core CPP conference。 This is a Thir from the previous year conference。

 and a meet up group of the same name。 I'm also a trainer and advisor， mainly C plus plus。

 but not only。😊。

![](img/0c8687e8e3dbf7d1536533d7fbfd336c_4.png)

So I your implementation details。 I think that we understand that。 yeah。

 it sounds important this is why you are watching。 This is why you are here， but why。

Why is it important。Well， I think that we know in a way that it relates to the principles of encapsulation。

That。Bringrink value by hiding things that the user of your code should not be exposed to。And。

This gives you， for example， the ability to protect object integrity。

 You know that nothing will happen for your object， which is not exposed。To the public。

It is easier to use。 You are not exposing things that should not be used。

 And then there would not be any accidents of， oh， you called the function that I didn't want you to call or you accessed a member that you shouldnt access。

 it， it improves maintainability because internal changes do not affect any external code。

 and it is easier to dobu because you can easily add break points and see what actually happens。

And things happen and inside your functions and not by changing data members， for example。

 So encapsulation is a principle that is behind or is leading to hiding your implementation details。

 it also goes with decoupling because once you hide things。

 And you expose only the actual things that the other side needs。

Then you decouple the color from the usage from the implement implementation。

 all the unnecessary details are not exposed and thus cannot be used。

 and thus are decoupled from the actual use。 So it reduces dependencies。

 I'm no dependent on something that I do not expose。And again。

 it facilitate changes because it is easier to change things that are not known to the other size to the outside side。

 and answer reusability once I do not bring with myself too much noise。

 only the necessary things that then the the thing can be easily used and can be reimplemented for other usage without any additional noise that I want to avoid。

 and it improves the stability because I need to test only the actual things that I expose。

 I don't need to test things that are hidden。Because they are hidden。 So I。

 I isolate the actual things that I wanted to use from things that should be hidden。So， so why is it。

 is it not so simple， I mean， we understand that the importance。 and we usually， by the way。

 try to do that。 I， I mean， we put things in the private。Is this enough。 Do we always do that。

 It's not only me saying that it is important and it is not so easy。

 The person who first came with hiding your implementation details is important is David Poas is known about。

Introducing the idea of modules， modularity in software development and the idea of adding your implementation details。

 This is from one of these talks。 And he says that it is other than it looks。 Now。

 there are some reasons here。 I will take my reasons in the following slides。 But in a way。

 it was hard back in the 70s。 It is out Also today。 if you want to follow talks by David Poasi。

 you can find some links。 this is from 2018。 quite a good one。

 So the ideas that came in the 70s are still relevant。😊。

And we still need to make sure that we follow them。 And it is still a bit complicated。

So what makes it not so simple。So first， because in some cases， we are a bit lazy。 lazy。

 not not in the bed manner， lazy we have other important things to do。 I mean， okay。

 let's keep that because we need to do we priorities。 And in some cases。

 we are not sure that something is really important。

 So due to temperature we just keep the fancy design。 No need for a fancy design for this one。

 Just you Ill put use a fact， put all in the public。

 and we don't think that it is important because in some cases， we think， okay。

 we can change it later if there would be a real reason。Would it be easy to change it later。Not so。

I'll give you an example of something that I would say that was a bit lazy。

 And then I will discuss later why I think it was a mistake to begin with。 stood Pe。

Stup pair exposes。 first and second。 First and second are data members that are exposed in the public。

 There aren't any ghettos， so you can actually。Access first and second。 someone was a bit lazy there。

 I mean， does it really matter， I mean， yeah， it just first and second， with just， you know access。

 I would argue that， yeah， it should have been in the。Private with a purple gethetter。

 And I will explain why。 But let's remember that one。

 Someone was a bit lazy because maybe someone thought it is not so important。 In some cases。

 we do not realize that we actually expose private details。 Like， for example， this function。

 What is exposed。Something is being exposed outside。I mean， it's， it's a function。

 I do not expose the member。 My members are in the private， but。

The fact that this class most probably holds。A map of strengths to ends。Is exposed by this API。

 I mean， if later on why the class most probably need to hold this map or all someone。

 someone who can provide this map， because the map is。Returned as a eence。So most probably。

 I don't want to maintain a value。That I create inside the function， a local。 And in a way。

 I'm saying this is a map。 You will get a map。 And if later on。

 I want to return some kind of another associative container， or it would be quite hard to change it。

😊，If I want to change the key， it would be quite hard to。 I mean。

 maybe a key that behaves like a string， but not a string。 Oh， it would be quite hard to change it。

 So I expose something on the API。 And the question is， can we not expose that。 And in many cases。

 we just， you know， write the function。 think that that's fine。

 And then it hits us when there is an need for a change。

 And the change is either impossible or very costly。Because of technical constraints in some cases。

 In some cases， we do not hide implementation details because， well， it could， we couldn't do that。

 I mean， maybe we can， but it was a bit complicated。 like for in this example。

 I want a factory method called create to create a fo object。

 the best thing would be if I do not want you to create fo on your own。

 you should go through the factory。I would have preferred to put the constructum in the private。

 but I can't。Why can't I。Because the factory calls make unique and make unique needs to call the constructor。

 and you cannot friend make unique。 It is problematic。 So if you try to say。

 let's put full constructor in the private， you will not be able to do that easily or in a。

Proper manner。 And then in some cases， you just， you know， leave it in the public section。

 And then the， the， the result is that even though you want the usage of this class。

To go through the factory in order to create a full instance。

 you want the user to go through the factory。 users could still use the constructor。

 that's implementation detail that they have a constructor。 I would want to hide that。In some cases。

 the reason that we do not hide documentation details is because they are trade offs and we don't want。

 we， we do want to expose some information。 Like， for example。

 we want to allow the user to know that we would provide back a vector。 Why。

 Because then you can use it as a vector。 if I would just say。



![](img/0c8687e8e3dbf7d1536533d7fbfd336c_6.png)
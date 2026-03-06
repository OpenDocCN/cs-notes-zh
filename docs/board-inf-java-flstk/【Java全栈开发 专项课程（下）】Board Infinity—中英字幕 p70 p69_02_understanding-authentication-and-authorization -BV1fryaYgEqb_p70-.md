# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p70 p69_02_understanding-authentication-and-authorization -BV1fryaYgEqb_p70-

![](img/74aa827a000f8e76cd95227586369042_0.png)

Whenever it comes to spring security after the spring configuration。

 spring embassy or spring Bo training or introduction。

 very important to understand how and why authentication and authorization is important and how it works because spring security is all about authenticating authenticating and authorizing your content or your request。



![](img/74aa827a000f8e76cd95227586369042_2.png)

So basically before， as I discussed you become a string security guru。

 you need to understand three important concepts。 One is authentication and authorization and the third most important is survey filters I will talk all about them one by one in this session string security works on the following core concepts and these concepts plays an important role authenticating the right user authorizing them to allow to work onto the content and then filter what kind of request is coming and that has to be passed from the dispatcher survey One of the fundamental ways to secure a resource is to make sure that the color is who they claim to be First of you are running a typical application you need your user to authenticate that means your application needs to verify if the user is who he claims to be Ty done with the username。

And password user can say that I am a user King， your web application which I wanted to access by this name or password。

 if the password and the name is correct， then you can allow that person to be accessible otherwise not。

To use the authentication filter， we have authentication provider that processes the specific types of authentication where authentication performs authentication with the request supports check if this provider supports the indicated authentication type or not。

 generally whenever we talk about this larger applications or full flged application we use the repository design pattern where the dark data access object authentication filter or provider which retrieves the user details from the user detail service and the user detailed service is a core interface that loads the user specific data in the spring documentation that spring documentationation authenticate with the specific validated filters and makes up whether your request comes for the right user or not。

 But third second most important is in a simple applications or authentication might not be enough as soon as the user authenticates she can。

Thiss every part of an application。But most applications have the concept of permission or ruless。

Where the authorization comes， authorization refers to the process of understanding or determining if a user has proper permission to perform a particular action or not。

For example， being the administrator， I can see how many users enrolled or registered onto my Ecommer website。

 but you being a customer cannot see that data。So that depends what kind of permissions you have。

 but as I discussed， thanks comes forward as in permissions or ruless， you can take one more example。

 customers who have access to the public facing front end of your web shop and administrators who have access to separate admin area。

 both types of user needs to login， but we need to allow that what are the activities can be done by the authenticated a or the normal user。

So there are different kind of authorization that we can perform URL based configuration or annotation based configuration Authorizationche an application can be complex so we need to define all the rules in a single place so it will become very complex and hard to read that is the reason annotation based configuration is more prefer。

All these are the annotations that you can use that is pre authorize what actions needs to be done before authorizing or after authorizing pre filter post filter secure and ruless allowed to that particular user。

That's how authorization and authentication works in the upcoming session I will talk about filter chain。

🎼Until next time， stay tuned， Thank you。

![](img/74aa827a000f8e76cd95227586369042_4.png)
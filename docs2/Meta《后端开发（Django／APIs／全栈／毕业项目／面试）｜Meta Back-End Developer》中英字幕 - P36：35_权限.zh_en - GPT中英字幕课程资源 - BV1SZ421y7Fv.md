# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P36：35_权限.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

In most apps， users are allocated different rules that allow them to perform certain actions。

 to enable these actions they need to have the relevant permission granted to them。

Think about the following scenario when you visit a restaurant。

 you're not allowed to go into the kitchen。However， if you are a member of staff。

 you are allowed to go into the kitchen。Web applications have a similar concept for controlling which users are allowed to do which action。

This is called Permissions， and in this video you will learn all about user and model permissions in Django。

The Dngle framework has an inbuilt system for handling permissions。

This authentication system has features for both authentication and authorization。

 coupled for ease of use， for a user to perform a certain action。

 they need to have the relevant permission granted to them。Before you explore permissions。

 it is important to note that a user in Django can be one of three classifications。

 namely a super user， a staff user， or a user。Much like other components of Django。

 users in Django are Python objects。The specific type of user is characterized by special attributes that are set inside the user object。

Let me tell you more about the classifications。A superus is a top level user。

 or administrator of the system， this type of user possesses permission to add。

 change or delete other users as well as perform operations on all the data in the project。

A staff type user is allowed to access Django admin interface， however。

 a staff user doesn't automatically get the permission to create， read， update。

 and delete data in the Django admin。It must be given explicitly。

Note that a super user is a staff user by default。Everyone else is a regular user by default。

A user is not authorized to use the admin site。Users are marked as active by default。

A user may be marked as inactive if its authentication fails or has been banned for some reason。

While you can create the user through the admin interface。

 it can also be done through the Django shell。The permission mechanism is handled by the Django。tcon。

aut app。You can use the Cs Use function to create a new user object。Once the user is created。

 you can grant a certain status to a user to become a staff member， to grant the staff status。

 set the user is staff property to true。So how do you create a super user？

Use a command directly inside the Django shell when prompted a password is assigned to this super user。

 followed by an authentication。Go to the admin interface and view the list of users。

The new user appears in the list。Remember that the super user has every permission in the system。

 whether it is custom permissions or jjangle created permissions。

There are several places where specific permission settings can be enabled， for example。

 to a specific model or object。So how do you set permissions in a model？

As you create models in your Django application， Django automatically creates add， change。

 delete and view permissions Permissions are named using the app action model pattern。

App is the name of the Jngle app。Action is add， change， delete， or view。

 and model is the name of the model in lowercase。Assume that a Django app called My app is created in the current project。

 and it has a model with the name my model declared in it。

You can now apply your newly acquired knowledge。What will the permissions be？

The permissions on this model will be as follows My app。ad underscore my model。My app。

chan underscore my model， my app。 deletete， underscore my model， and lastly， my app。

 view underscore my model。

![](img/4517493be5bde69089a93ab4c1c8d42c_1.png)

In Python code， it is possible to check if a user has a certain type of permission enabled on it。



![](img/4517493be5bde69089a93ab4c1c8d42c_3.png)

To do this， you can use the has perm function， which returns true or false。For example。

 if the requesting user doesn't have the appropriate permissions。

 you can raise a permission denied error instead of returning the normal HTTP response。

Assigning permissions to each user individually is a tedious task。

 especially if you have large numbers of users。Fortunately， Django has a solution。

You can manage permissions to sets of users in jnangle groups。That proves to be very useful。Now。

 what is a group？In Django， a group is a list of permissions that can be assigned to one or more users。

A user can belong to any number of groups to go back to the restaurant example。

 you might have a group for kitchen staff and another group for waiters。

When you create or modify a user， simply choose the desired group。

 all the permissions listed in the group will be automatically assigned to the user。

It is important to note that you can still manually add permissions to users。

 even if they belong to a group。

![](img/4517493be5bde69089a93ab4c1c8d42c_5.png)

In this video， you learned about the user permissions and model permissions in djangle。

 you can give permissions to a user while creating it in the admin panel or from the Shell interface。

Using groups is a convenient way of enabling similar sets or permissions to multiple users。

To enforce a permission while executing a view function。

 you can use the app permissionmission requiredqui Decator。


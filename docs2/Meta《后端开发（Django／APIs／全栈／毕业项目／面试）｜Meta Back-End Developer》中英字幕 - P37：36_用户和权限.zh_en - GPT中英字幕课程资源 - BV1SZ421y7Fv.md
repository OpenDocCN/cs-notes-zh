# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P37：36_用户和权限.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

You may remember that you can create different types of users in Django。Now。

 you will explore how to add and remove permissions for these users。

The Jnangle framework has a built in mechanism that manages permissions quite efficiently。😊。

The Django admin Web interfaceface makes it easier for you to create and modify users or user groups。

You can also grant or revoke permissions for individuals and user groups。



![](img/f1cfeb534ffa9f70b5ef633be011e758_1.png)

While Django admin has a user friendly interface， which makes handling permissions quite easy。

 it is also possible to handle permissions through the Django shell。To demonstrate this。

 let's first create a user and then locate the required user by its username。To do this。

 you must first open the interactive Django shell that has Django settings already imported。

It allows you to directly work with the root project folder。Next。

 import the user module from the specific Django。con package。

Then define a variable and assign it the Cate user method and pass the arguments for username。

 email and password in that order。Once the user is created。

 define another variable and assign it the get method of the user object。

Then pass the user name as the argument。Once the user is created。

 the next step is to assign permissions。

![](img/f1cfeb534ffa9f70b5ef633be011e758_3.png)

Jngo comes with a built in permission system， it provides a way to assign permissions to specific users and groups of users。



![](img/f1cfeb534ffa9f70b5ef633be011e758_5.png)

When Djangocon。Oth is listed in your installed app setting。

 it will ensure that four default permissions are available。



![](img/f1cfeb534ffa9f70b5ef633be011e758_7.png)

This functionality allows you to add， change， delete， and view permissions。

 and are created for each junangle model defined in one of your installed applications。



![](img/f1cfeb534ffa9f70b5ef633be011e758_9.png)

Permissions can be set not only per type of object， but also per specific object instance。

By using the methods provided by the model admin class。

 it is possible to customize permissions for different object instances of the same type。



![](img/f1cfeb534ffa9f70b5ef633be011e758_11.png)

Similar to the admin permissions you learned about。

 permission specific to models can also be managed using the model admin class。

The model admin class methods include view， add， change， and deletete。

 and are used to customize the permissions。Now that you have learned about the concept of permission using the Jngle shell。

 next， let's explore user objects。User objects have two main fields known as groups and user permissions。

User permissions， store and reference a single or multiple permission objects。

Permissions can be granted or removed by calling the methods set， add。

 remove and clear on the user object。Let's explore an example using the add method to grant permissions to the user Mario。

😊，In this scenario， let's provide one or more permission objects。

You use the add method to add a permission to change the menu model inside the app， My app。

It's important to know that once you add django。contri。aut to the installed apps list。

 you must run the migrate command to implement the change。Note that when you run manage。t pi migrate。

 each Jnangle model is assigned the default permissions。For example。

Suppose you have a Jngo app called My app in which there is a model named My model。

If you run Boolean expression to verify the permissions to add， change， delete， and view。

 they will return true。

![](img/f1cfeb534ffa9f70b5ef633be011e758_13.png)

In addition to the default permissions， custom permissions can be declared in the Model's Me class。

 which can be declared inside the model。So far， you have covered how you can modify permissions on the Dngo shell。

 however， in practice it is much easier to deal with them using the Dngo admin interface in the browser。

Let's explore how you can add and remove permissions using the Django admin interface。

Building on the earlier example of adding groups and users。

 let's explore how to assign permissions to different users using the Django admin panel。

In the browser at the admin login page， let's enter the credentials for the existing super user。



![](img/f1cfeb534ffa9f70b5ef633be011e758_15.png)

Once you log into the admin panel， notice that you have choices for groups and users。

In the authenticentation and authorization section， click on the link for groups。

 the first thing to know is that you can create groups in addition to the existing staff group。



![](img/f1cfeb534ffa9f70b5ef633be011e758_17.png)

For example。Let's say you want to add some more groups。The first is for the reservation desk staff。

And the second is for the Little Lemon website administrators。

Click on the Add group button and a new page with a form to add a group loads。

You must give the group a name in this example， the name will be reservation De。

Inside the permission section， notice that you have several options in the available permissions table。

Let's say you want to assign this group permissions for the reservations model。

You can select the reservation permissions to add， change， delete our view reservations。

Then click the chooseose button to add the permissions to the Cho permissions table。Once transferred。

 click the Save and add another button to create the group for the website administrators。

Notice that the Add group form resets， allowing you to add another group。

Create a new group called admin users， but this time assign all the permissions by clicking the choose All button。



![](img/f1cfeb534ffa9f70b5ef633be011e758_19.png)

![](img/f1cfeb534ffa9f70b5ef633be011e758_20.png)

As all the groups are created， you can click the saveve button。😊。



![](img/f1cfeb534ffa9f70b5ef633be011e758_22.png)

Okay， so now that the groups are created， the next step is to add the users。

In the Aentation and authorization section， click the Uses link to open the users's page。

Suppose you want to create a user called Mario inside this section remember。

 Mariio is the owner of little Le。Click the Add user button to load a new webpage that displays an add user form。

To add a new user， you must enter the login credentials。

 so enter Mario as the username and then set a password。

Click the saveve and add another button to add a new user。The second user is Meher。

 a staff member at Little Le。Assign a password and click the Save button。

Notice that when you click the saveve button， Django administration immediately takes you to the page where you can assign additional information to the user you just created。



![](img/f1cfeb534ffa9f70b5ef633be011e758_24.png)

There is a personal info section where you can add the user's first name， last name。

 and email address。In the permission section， you can change the permission level and assign the user to a group。



![](img/f1cfeb534ffa9f70b5ef633be011e758_26.png)

In this example， the user Meher is a staff member， so let's keep the permission as active and also assign the permission of staff status。



![](img/f1cfeb534ffa9f70b5ef633be011e758_28.png)

Next， assign Meher to be part of the reservation desk group。

It's important to know that once you assign a user to a specific group。

 all the permissions that are entitled to the group get automatically assigned to the user。

And it's also possible to assign additional user permissions。



![](img/f1cfeb534ffa9f70b5ef633be011e758_30.png)

When you finish assigning a group and permissions to a user， press the Save button。



![](img/f1cfeb534ffa9f70b5ef633be011e758_32.png)

Next， it's time to add a group and permissions to the user Mario by clicking on the user's name in the user's table。



![](img/f1cfeb534ffa9f70b5ef633be011e758_34.png)

First， enter the personal info for the user Mario。

![](img/f1cfeb534ffa9f70b5ef633be011e758_36.png)

Next， assign him the status of Superuser。

![](img/f1cfeb534ffa9f70b5ef633be011e758_38.png)

Make him a part of the admin group and save the changes to return to the user's page。



![](img/f1cfeb534ffa9f70b5ef633be011e758_40.png)

It's also possible to filter the users by different categories。

It's also possible to filter the users by different categories。



![](img/f1cfeb534ffa9f70b5ef633be011e758_42.png)

In the filter panel， you can filter by the staff' status， super user status。

 or the status of the groups in which they are assigned， such as admin users。



![](img/f1cfeb534ffa9f70b5ef633be011e758_44.png)

Finally， on the main homepage， notice your recent actions display in the recent A section。

This feature allows you to configure different users quickly and set their permission levels。



![](img/f1cfeb534ffa9f70b5ef633be011e758_46.png)

In this video， you had an introduction of how to handle user permissions from the Django shell。

You also covered a demonstration of how to add groups， users。

 and modify permissions using the Django admin interface， Good work。


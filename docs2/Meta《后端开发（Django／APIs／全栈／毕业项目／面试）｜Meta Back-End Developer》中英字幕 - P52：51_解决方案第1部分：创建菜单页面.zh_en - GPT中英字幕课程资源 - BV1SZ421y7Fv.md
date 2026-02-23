# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P52：51_解决方案第1部分：创建菜单页面.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Congratulations on completing the graded assessment。

 one of your final steps to test your skills and understanding of the Jngle framework。

Let's walk through the solution。The first part is to create the menu page， open the filemodels。

pi and create a model classes for the menu。Make sure to define a Dunder method inside the model class。

 so the name will be visible in Django admin。The next step is to open the admin。

tpi file and register both models。It's important to ensure that both models are imported from the models。

pi file。Now that the models are in place， run the commands， make and perform migrations。

Once the migrations are completed， open the project level and app level URLs。

pi files to ensure the URL path configurations are in place。Okay。

The next step is to add content inside the models you created using the Django admin panel。First。

 create a super user by running the command in the command prompt with the following details username。

Bisttro admin email， admin@littlelemon。com and password Lemon@ 786 exclamation mark。

Once the super user is created， add the command to run the development server。

Open the browser with the browser Preview button。

![](img/75df9cbcbde4f3ca602dfefb63acb9c9_1.png)

And paste the local hostst URL generated in the terminal。

Add the admin path to the URL to access the admin login page。

Enter the credentials for the super user you created。And log in to the Django admin panel。

Inside the Django admin panel， locate the menu model under restaurantaurant， which is the app's name。

Next， open the menu， click on the add menu button。A new page will display and enter the details provided inside the zip file containing the text for the menu items。

Staying inside the Django admin panel， click the menu under restaurantestaurant and notice that a page displays the list of menu items。



![](img/75df9cbcbde4f3ca602dfefb63acb9c9_3.png)

Once the menu items have been added， open the views。pi file。



![](img/75df9cbcbde4f3ca602dfefb63acb9c9_5.png)

Notice that the code for the view functions for home， about and booking are already in place。

Now create a view function for the menu page called menu and pass the request object as an argument。

Inside the function body， create a variable called menu data and assign it the value of objects。 all。

 which is called over the menu model class， create a variable called main data。

 and assign a dictionary that contains the following key value pairs。

 a key of menu as a string and the value of the menu underscore data as the variable。

The final part of the view function is to return the render function from the view making sure to pass the following arguments to it。

The request object， the template name menu。ht passed as a string。

And the dictionary object with a string value menu as the key and a variable main data as its value。

 open the app level URLs。 pi and add the path function for the menu view。Okay。

 so that should be all the code required to complete the model and view function for the menu items。

The next step is to add the code for the template， expand the app levell directory templates and create a file called Minu。

htm and add the starter code to it。After you insert the starter code。

 replace the Commons with the appropriate Dngo template language code。First。

 create a far loop that will iterate over the menu object。

Use a temporary variable called itemem as an iterator。

Remember that menu is the key of the dictionary object you passed to the template from inside the menu view function。

So you must use the dot operators inside the template while accessing any objects and variables from the object past to the template from the view function。

Between the enclosing paragraph tags， print the menu name from the item variable。Next。

 between the enclosing HTML span tags， print the price from the item variable。

To add the currency symbol and the price formatting。

 prefix the opening curly bracket with the dollar symbol and to fixix the closing curly brackets of the DTL variable with dot00。

Finally， insert the template tag to end the for loop。Okay。

So the first part of the project is complete， let's run the development server to test it。

Open the terminal and add the command to run the server。

 copy the URL generated and click the browser Preview button。



![](img/75df9cbcbde4f3ca602dfefb63acb9c9_7.png)

Then paste the URL into the browser address bar and press enterter。



![](img/75df9cbcbde4f3ca602dfefb63acb9c9_9.png)

Notice that the homepage of the Little Lemon website loads。

Now it's time to move to the second part of the project。And creates the menu item page。


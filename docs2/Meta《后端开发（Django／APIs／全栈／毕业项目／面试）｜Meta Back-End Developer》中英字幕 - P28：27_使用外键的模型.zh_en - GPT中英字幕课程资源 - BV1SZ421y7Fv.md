# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P28：27_使用外键的模型.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now you are familiar with the basics of creating a model and performing migrations。

 let's build upon your understanding of models by connecting to another model using a one to Man relationship。

In this video you will explore an example of using foreign keys as a field inside the model in Django。

 Far key is an ORM field representing a database table column。

You use it to create the relationships between tables in your database。

Imagine the scenario of building an online menu for the little lemonmon restaurant。

The solution begins with creating a table to add the menu items for the webage。Now。

 Little Le is a restaurant that offers many cuisines and placing each cuisine item in its correct category requires some skill。

To do this successfully， start by creating another model for categories and assign the different categories to each of the menu items。



![](img/4b5c9982f132d28ff9a6923a3bc5b17d_1.png)

Now， let's explore how to do this by using a one to many relationship through foreign Keys in Django。

Let's begin by selecting the modelss。 Pi file。Here， you need to create two models。

 The first model is for the menu category， and the second model is for the menu。Later。

 you will add subcategories in the menu category and use the foreign key to reference these categories。

It's important to know that adding both models is done the same way as adding models independently。

Now， for the first model， add an attribute called menu category name and save the file。Next。

 create a second model called menu。Within this model， add the menu item name， price， and category ID。

The next step is to assign a car field to the menu item and an integer field to the price。

Let's explore where to add the foreign key。Write the Model。F and key command in the category ID。

Inside the foreign key are two required fields。The first field is the class for the model to connect to。

 and the second field is the settings that enables on deletelete。

 so it's defined as on deletelete equal to models。protect。Additionally。

 add another argument called default equals none。The next step includes updating the Addmin D Pi file by actioning the required imports。

Next， it's time to register the models。Note that the utility becomes more evident later in the Django admin lesson。

For now， ensure that the Settingspi file in the app configuration is updated。

Go ahead and run the server， followed by performing the migrations。

Notice that the output includes two models that are migrated。Finally， run the command Python 3。

 manage。 pi migrates。The next step is to check the database。 so go to Db。 sQLite3。

Right click and select Open database。Scroll down to SQL Light Explorer and select my app menu。

For this example， assume that there are entries added to the database。Now。

 open the database again under my app menu categories， the ID lists 1，2， and three as Italian。

 Greek and Turkish。Now visit my app underscore menu。

And notice that there is a fourth field called category ID underscore ID。

This field has ID numbers that match the respective categories in the My app underscore menu table。

For example， Greek Sal is listed as ID2， and in the Myapp underscore menu category。

 the category name is Greek。The ID of the menu is referenced and corresponds with the ID listed in the menu category。

Nowo。

![](img/4b5c9982f132d28ff9a6923a3bc5b17d_3.png)

Let's make this more intuitive by adding another attribute called related underscore name equals。

 and assign it， the valued labeled category underscore name。

This means that the My app underscore menu now lists the category name instead of category underscore ID underscore ID。

This is noticeable when running migrations again。The fields category on the menu is altered。

Notice that with delete。t=s models。protect selected。

 no menu items will be removed with any category that is deleted in the category table。In this video。

 you learned how to implement a one to many relationship using firing keys in Django models。


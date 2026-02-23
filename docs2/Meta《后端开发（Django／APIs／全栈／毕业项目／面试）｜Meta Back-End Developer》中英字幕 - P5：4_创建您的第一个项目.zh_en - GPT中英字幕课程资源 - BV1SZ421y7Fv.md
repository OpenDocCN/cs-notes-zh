# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P5：4_创建您的第一个项目.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now， you should be familiar with the concept of projects and apps in Django。

You also explored the core files that make up a Dngle project。In this video。

 you will learn how to create your first Django project using the terminal and the VS code Ed you will also learn how to set up the development environment by installing a virtual environment。



![](img/7de6469007a65e2f5a14f7cde8527319_1.png)

And you will explore some common CLI commands， used to create Dngo projects and launch the development server。

If you are a Python developer working on multiple projects。

 it's best practice to keep your projects isolated in a virtual environment。

But you may be wondering why you need to do this Well。

 dnangle projects can often be quite large and involve specific dependencies for things like packages。

For example， you could have a package that has a dependency on a specific version。

You do not want this conflicting with your other Python or jnangle projects。

 so it's best to keep your projects isolated using a virtual development environment。

Virtual environments are isolated spaces you create to manage dependencies and the overall project。

This allows you to keep features such as the interpreter， libraries。

 and scripts isolated and installed for a specific project。

In addition to the functionalities provided， Django also comes with an integrated development server。

This means that the application has a Re response relationship with a client okay so now that you are familiar with the concept of the virtual development environment and development server。

 let's explore the steps involved in creating a Jnangle project。First。

 you create a project directory。Next， you create a virtual environment for your jujangle application。

Then you create a Django project and finally run the Django development server。



![](img/7de6469007a65e2f5a14f7cde8527319_3.png)

Let's explore each of these steps now in a little more detail using some examples in VS code。



![](img/7de6469007a65e2f5a14f7cde8527319_5.png)

Your project is an organizational unit that consists of settings and database information。

It can be stored anywhere on your development computer， but as a best practice。

 it's best to keep it in a subfold with all your other django applications。

First open a new terminal by choosing terminal new terminal from the top menu Next。

 create a new directory by using that make directory command and then give your directory a name likeBuild Django。

Then， enter inside this directory using the Change directory command。Next。

 you need to set up the virtual environment to do this， type Python 3 M， and then V E in V。

Then give the virtual environment a name such as tutorial E& V。Once you are finished， press enterter。

If you open the directory structure in VS code， notice that some new files have been generated。

Now you need to activate the virtual environment。😊。

Type source and the path from where you can activate it， which is tutorial E and V， bin。

 activate and press enter。 notice that the virtual environment is activated by the round bracket suffix in the terminal。

Once the virtual environment package is installed， you are ready to install Django。

And you do this by using the command Pip3 install jngle。To make sure that Django is installed。

 you can run the command Python 3 M Djangle version。Notice that the current version is 4。1。

Once this is set up， you are ready to create a project。

And you do this by running Django's built in command line tools， type Django admin， start project。

 and then give the project a name。In this example， it's Che's table。Finally。

 press enter to run the command。If you expand the directory structure again。

 notice that the Che's table is created with supportive Django specific files Once your Django project is created。

 you need to launch the development server。Before you do this。

 it's important to be aware of the manage。pyY file that is automatically created with the project。

Recall that managed。PY is a command line utility that works like the Django admin command。

So you can replace the Dngo admin command with manage dot Py as it uses the project settings。

To launch the development server， you can run the run server command using the manage。pyy command。

You will learn more about how to work with Django admin and manage。

pyy commands later notice that a URL is generated。If you are on Mac。

 you can click on this URL to open it in a browser window。



![](img/7de6469007a65e2f5a14f7cde8527319_7.png)

If you are on Windows， you will need to copy and paste it to your browser。



![](img/7de6469007a65e2f5a14f7cde8527319_9.png)

Notice that the terminal gives us an option to press Ctl C to stop our server。



![](img/7de6469007a65e2f5a14f7cde8527319_11.png)

It's important to note that virtual environments and development servers are extensive topics by themselves。

And you will learn more about them later in this course。

You can even omit the use of a virtual environment if you wish。But this is not recommended。

In this video， you learned how to create your first project in Django， using the terminal， VS code。

 and Djangos built in command line tools。
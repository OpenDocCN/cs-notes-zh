# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P6：5_Django admin manage.py命令.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now， you should be familiar with the core structure of the Django framework。

You know that to create a Django application， you need to create a virtual environment for the project。

 create the project， and then run the development server。



![](img/0ff460100a423bfef83c201df0b5b1b9_1.png)

![](img/0ff460100a423bfef83c201df0b5b1b9_2.png)

And you do this by running specific commands such as Start project and Run Ser using the Django admin command line utility。

Jengo provides a set of commands that also generates a project structure that contains the configuration and settings related to the entire web application when working on Django projects。

 developers have two choices for command line utility to perform tasks。



![](img/0ff460100a423bfef83c201df0b5b1b9_4.png)

They can use either Django admin or manage。 PY。While both can be used to perform the same tasks。

 there are some subtle differences and your choice of usage will depend on how you want to work on your project。

In this video， you will learn about the Django admin and manage。

 Py commands and how developers use them to perform administrative tasks。

One of the powerful features of Django is that it provides a ready to use admin interface in the form of a command line utility named as Django admin。

Jianango admin is Djago's command line utility for administrative tasks；

 this utility is present in the Scripps folder of the Django's Environment Directory。



![](img/0ff460100a423bfef83c201df0b5b1b9_6.png)

The Django admin utility is executed from inside the terminal。

Managed dot Py is a script that is a local version of Django admin and is located inside the project folder。

 It sets the Django settingstting module environment variable so that it points to your project settings do Py file。

Jengo admin is a file that is created when you install Django。

 The Django admin utility should be on your system path if you installed Django via PIP。

 if you do not find it on your system path， make sure you have your virtual environment activated and install Django inside it using a command such as PIipP3 install Django。

Manaageged。 PY is a file that is automatically created each time you create a Django project。

 this file is specific to the virtual environment of the project。

 it does the same thing as Django admin but also sets the Django settingstting module En variable to point to your projects settings。

 PY file。Generally， when working on a single Django project。

 developers tend to use manage dot PY as the administrative tasks of Django admin can also be performed with Man do PY however。

 if you need to switch between multiple Django Setting files。

 use the Django admin command with the Django settings module or the Setting command line option。



![](img/0ff460100a423bfef83c201df0b5b1b9_8.png)

The command line examples throughout this video use Django admin to be consistent。

 but any example can use manage。tPY just as well。You may recall that you use the start project command to create a Jngle project。

 This creates a jjangle project directory structure for the given project name in the current directory or the given destination。

By default， the new directory contains the manage。 Py file and a project package。

This project package contains a Setting。pyy file and other files。



![](img/0ff460100a423bfef83c201df0b5b1b9_10.png)

It's important to note that if only the project name is given。

 both the project directory and the project package will use the same name as the project name Also。

 the project directory will be created in the current working directory。

If an optional destination is provided， Dngle will use that existing directory as the project directory and create the managed。

Pwi file and the project package within it。

![](img/0ff460100a423bfef83c201df0b5b1b9_12.png)

A common developer workflow is to use the period symbol to denote the current working directory。

 this avoids having subdirecties with the same name。

 recall that you use that run server command to run a project。



![](img/0ff460100a423bfef83c201df0b5b1b9_14.png)

This command starts a lightweight development web server on your local machine by default。

 the server runs on port 8000 on the IP address 127。0。0。1。However。

 it is possible to change this as you can pass in an IP address and port number explicitly。😊。

It is important to note that if you run this script as a user with normal privileges。

 which are recommended， you might not have access to start a port on a low port number。

 This is because low port numbers are reserved for the super user or root user。

The development server works great for application development and testing。 however。

 Django recommends that you should never use this server in production as it has not gone through security audits or performance tests。

The development server automatically reloads Python code for each request as needed。

You don't need to restart the server for code changes to take effect； however。

 some actions like adding files don't trigger a restart。

 so you'll have to restart the server in these cases。



![](img/0ff460100a423bfef83c201df0b5b1b9_16.png)

In this video， you learned about the Django admin and managed。

 PY commands and how developers use them to perform administrative tasks。


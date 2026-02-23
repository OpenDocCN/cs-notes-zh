# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P7：6_React 项目结构.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

As you might already be aware， it's important to organizeise or structure your react components so that they're easy to access。

 but what does a structure look like， what files and folders are found within a typical react application？

The react project structure is the focus of this video。By the time you reach the end of this video。

 youll have learned how to explain the default folder structure of a react project。

 outlying the benefits of the folder structure。Customize the folder structure to hold components and assets and explain the benefits of planning folder use for app development。



![](img/d70272be59ad595ddfb5418ae733aa5a_1.png)

Let's begin by examining how the default files and folders are laid out in a reactact app project。

When you build a react app using the command NPM in its react app。

 your project is comprised of a specific file and folder structure。

Notice that there are three folders named node moduleles， public and SRC or source。

Let's explore each of these folders briefly now first let's begin with a node modules folder。

You can think of this folder as a repository for all the modules in your react app The node modules folder is automatically added when you install a specific NPM package。

You might recall that packages are groupings of files and or node dot JS modules。

Developers use packages when they want to add a piece of functionality that someone else coded and made available to other developers via the NPM ecosystem。

Don't worry too much about the node modules folder。For now。

 just be aware of it and that it's needed for your react app to work Next is the public folder and it contains the assets that will be displayed to the user in your app。

For example， image files for logos， the Ficcon which displays an icon in the browser tab and the robot。

 Txt file， which is used for search engine optimization。Also， there is a manifestif。

t JSong file which is used to provide some metadata to a device when your react powered web app is installed on it。

While all these files are necessary， the most important one to know about for now is index。ht。

A react app gets injected into the specific element inside the body of the index HTML file。

Based on changes happening inside a react app， it injects those updates in that same div of index HTML。

You'll find out more about how this works later on in the course。Finally。

 let's explore the contents of the SRC or source folder。

This folder contains all the essential component files required to ensure that to react app functions。

And notice that there are some files already in this folder。

These were automatically created when I used the NPM command C React app to build a starter React app。

As a react developer， you'll probably spend most of your time within this folder。

 so let's get a little more familiar with some of these files now。😊。

You may be familiar with some of them already， such as index dotjS and app。jS。

 which are used to render the root component of the app。Let's briefly explore the others。

App dotcsS contains the styles for the app。jS component and the index dot CSS file contains the styles that are use in the entire app。

App。test。js set test。js and the report web vitalitals。

js are files related to the app's performance and testing。

The logo dot SvG file is displayed on the starts page of the default app when the app is displayed in the browser on the local host。

While these can be useful and their functionality is important。

 I can still safely delete them without affecting react abilities to create a very basic application。

😊，I just need to also remove the code that references them。

This is because reactact doesn't have opinions on how you organize your files and folders in the source folder。

 however， there are a few common approaches popular in the ecosystem and you'll learn about them soon。

Its at this point it's also worth remembering that the most important file in the entire source folder is the index dot JS file。

This file imports everything that this react app needs to render a working react app。Okay。

 so now you have explored the main folders， let's explore the files in the root of the default app。

Root files are additional files that are found in the roots of the project folder itself and include a gitign file。

 two JSON files， and a readme file。The dot giig nor file is used in version control and it's used to specify what files and folders must be excluded from a project。

It's important to know that this file is not specific to react。

 this means that other systems use this file too。

![](img/d70272be59ad595ddfb5418ae733aa5a_3.png)

The Readme do M file is a markdown file that gives some basic information on this project  developers use this when they want to share the project's code on a site like GitHub。

The package dot JSON file lists information pertaining to my app。

 which allows NPM to run several scripts and perform various tasks in the app itself。

Finally the packagelock。 JON file holds the list of all dependencies with their specific versions。

 the package。 JSON file helps NPM rebuild the app on another machine or if we delete the node modules folder with all the files that our project needs to run the package lock。

 JSON fileile has all the information for NPM to be able to rebuild those files reliably。

This file is there to ensure that NPM tracks all the module's installationss properly。

As a general rule， it's better to leave these files where they are for the moment as they are required for the app to function。

You should now be able to explain the default folder structure of a react project and outline the benefits of the folder structure。

In addition， you should know how to customize the folder structure to hold components and assets。

And be able to explain the benefits of planning folder use for app development。Good job。


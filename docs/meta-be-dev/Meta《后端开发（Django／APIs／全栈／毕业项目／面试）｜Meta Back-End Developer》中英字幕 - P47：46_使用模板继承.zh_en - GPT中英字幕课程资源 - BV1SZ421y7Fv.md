# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P47：46_使用模板继承.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Up until now， you've discovered what template inheritance is and explored the includelude and Xends tags in Django。

Remember， the Exs tag allows you to replace blocks or content from a parenting template。

It creates a parent child relationship where the child can overrite the parent's functionality。

Likewise， the includelude tag adds parts and includes the rendering of a template in the current content。

It is easy to get confused between extends and include。

 but there are differences that would become clearer with practice Let's begin with a demonstration。

Suppose that you must design the little Le website that contains three pages called Home。

 menu and About。While the contents of each of these pages will differ。

 there are a few basic styling components that need to be uniform across the website。Additionally。

 you may want the menu bar as part of the header so that it can be present on all pages。😊。



![](img/815c075750ee524d69191286f19421a9_1.png)

Let's explore how to use the Exs and include tags to implement Theritance in Django。

Let's begin with the views。pi file。You need to set up three views， namely home， about and menu。

These are the three pages you are creating for the Little Lin website。😊。

Ensure that you update your URL configuration file both at the project and app levels。

 also map the respective URLs to the views。Next， update the settingsttings。

pi file by adding the app inside installed apps。Then create a template folder as part of DIRS ints。

To work with templates， you need to create a folder called templatelates by right clicking on the My project folder and selecting new folder。

When working with template inheritance， you need to create another folder in my project called partials。

😊，This is where you will include the header information。Now let's continue by creating a base。

 HTML file inside the templatelates folder， which will contain the code for the base HTML that you want inside all other pages of the website。

Still inside the partials folder， create the three pages for the little Li website about index and menu。

Also， create a file called underscore header。ht in the partials folder。

 This is the file that you will use inside the includelude tag in the base HTML file。

Now that you have the file structure set up， let's begin by adding some code to the base HTML file。

Remember that you can just type exclamation mark and press enterter to add the basic HTML Stub。Next。

 update the title tag to little Le， also add a main tag inside the body tag。

Here you need to add the tags for the block content， this allows you to use it with the Extends tag。

So type block content inside the first set of curly braces and close it off by typing In Block in the second set of curly braces。

Make this block content stand out by adding some styling with a background color inside the body tag。

😊，Now save the file。The next step is to edit one of the pages， let's edit index。htm。

Add block content and add two paragraph tags inside the block content tags。

Now to utilize template inheritance， add the extendt tag at the top of the index。

htm file by typing Exs open quotation mark base。html Close quotation mark。For this example。

 go ahead and apply the same steps to add content to the other web pages。

 remember to save the file and run the development server by typing Python3 manageage。

P run server in the terminal。

![](img/815c075750ee524d69191286f19421a9_3.png)

Type home in the URL and press Enter。Success it is clear that the template has rendered to the homepage。

Why。😡，Remember you did not add any specifications for a background color in the index file What happens here is that the background that you specified in your base HTML file is extended from the base do HTML file。



![](img/815c075750ee524d69191286f19421a9_5.png)

![](img/815c075750ee524d69191286f19421a9_6.png)

Well done， you just use template inheritance。Similarly， if you go to the About page。

 notice how the details have changed according to the information present on this page。



![](img/815c075750ee524d69191286f19421a9_8.png)

In summary， the base dot HTML template renders on each of the pages。

 but the unique content of each page displays in the block content。Now。

 let's add header information using theInlude tag。You need to add content to the header file and save it。

To carry this through consistently to all the web pages。

 go to that base dohtml file and add an includelude tag that contains the header file reference。



![](img/815c075750ee524d69191286f19421a9_10.png)

Save the file again and return to the server。Once the web page is refreshed。

 notice the header information at the top of the page。

This would be displayed across each web page without affecting the rest of the page information。

This is much more effective than adding the header file inside a specific page。

 which will render the header information only on that single page。😊。



![](img/815c075750ee524d69191286f19421a9_12.png)

![](img/815c075750ee524d69191286f19421a9_13.png)

In this video， you learned how to use theInlude and extend tags to utilize template inheritance jngle。

This skill will save you a lot of time in your future web development projects。


# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P46：45_模板继承.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

When developing web applications in Django， recall the key principle of don't repeat yourself are dry。

"，Dupplication， whether inadvertently are purposeful。

 can lead to maintenance issues and logical contradictions。

Every distinct concept or piece of data should live in one and only one place。

The framework within reason should deuse as much as possible from as little as possible。For example。

 to create the same header and footer sections across multiple pages for the little Le website。

 you can make a copy of the markup and save it multiple times。

 then only change the corresponding title for each web page。



![](img/befc4029c23cc1d6fb68553682a46999_1.png)

But a more efficient method is to build a base template containing all the common elements of the website and assign them to a block。

😊。

![](img/befc4029c23cc1d6fb68553682a46999_3.png)

This block can then be repeated on every webpage。In this video。

 you will learn about template inheritance in Django and how developers use it to speed up user interface development。



![](img/befc4029c23cc1d6fb68553682a46999_5.png)

Suppose you have the task of creating a prototype for the new Little Le website。

The website has four pages for home about menu and book。So far， only one prototype page exists。

And this is for the About U page。In order to work with templates efficiently。

 it helps to break the page up into sections。And in Django。

 these sections are referred to as blockss。For example， at the very top of most websites。

 you find what is called the header， and this is the first section or block。

The header often contains the company name and logo。

It also usually has links to the different pages of the website。

 which is known as the navigation menu。😊，Additionally。

 the header might contain a section where users can log in。

This usually includes a user icon along with a drop down menu with a link to the user profile。



![](img/befc4029c23cc1d6fb68553682a46999_7.png)

When working with a page layout， it's best practice to keep the look of the header consistent and in the same position across all the pages of a website。



![](img/befc4029c23cc1d6fb68553682a46999_9.png)

This consistency is essential for a good user interface and contributes to a positive user experience。



![](img/befc4029c23cc1d6fb68553682a46999_11.png)

Because if the header is visible on all pages of your website。

 it makes it faster and easier for the user to navigate。The same can be said for the Fer。

The foototer is a section at the bottom of a webpage that contains essential company or contact details。

 navigation links and copyright information。😊。

![](img/befc4029c23cc1d6fb68553682a46999_13.png)

At this point， you may be wondering， how do I incorporate the header and footer across the four pages for the little Le website？

That's where you use template inheritance。

![](img/befc4029c23cc1d6fb68553682a46999_15.png)

Template inheritance allows you to split out content by breaking it down into individual components。

😊。

![](img/befc4029c23cc1d6fb68553682a46999_17.png)

You can then insert and reuse these components without dlicating work。



![](img/befc4029c23cc1d6fb68553682a46999_19.png)

And this saves you a lot of time remember， dry is a key principle in django and Tulating inheritance is a great example of this。



![](img/befc4029c23cc1d6fb68553682a46999_21.png)

Okay。So now you are familiar with the concept of template inheritance。

Let's explore the two tag options needed to apply it。😊，They are theInlude and the Exs tag。

Let's begin with the includelude tag。The HTML markup on the base page now references the files containing the code for the header and footer sections using the includelude tag。

If you need to make an update to either of these files。

 you'll only need to do it once and not on every page。

The includelude tag lets you either specify a template strain or a variable to allow conditions for different rendering。

For example。Say you want to pass an object which contains information such as the page name。

To do this， you can pass a dictionary as an argument inside the render function to pass variables or objects to the template。

To gain access to specific data from the header file， such as the page object。

 you need to add additional attributes inside the includelude tag。Once added。

 you can access the page object anywhere on the page。For example。

 to display the page name as a heading element。It's important to remember that this object is part of the dictionary that was passed inside the render function。

 inside the view。Let's recap when using the Inlude tag。

 you instruct the page to render this sub templatelate and include the HTML。

This means that there is no shared state between included templates。

Each include is an independent rendering process。

![](img/befc4029c23cc1d6fb68553682a46999_23.png)

Okay， let's move on to the second tag， which is the extendends tag。

This is similar to the includelude tag with syntax and usage， however。

 its purpose and functionality differ。Extend allows you to replace blocks or content from a pairing template。

 as opposed to include that will include parts。

![](img/befc4029c23cc1d6fb68553682a46999_25.png)

Extend creates a parent child relationship where parent' functionality can be overwritten。Include。

 on the other hand， simply includes rendering a template in the current context。

There are two ways to use the extendends tag， the first is that it can use the string literal as the name of the parent template to be extended。

The second is it can make use of the value of a variable。Once the variable evaluates to a string。

 Django will use that string as the name of the parent template。For example。

Say you have a file called header。ht that contains code for a navigation menu represented as an unordered list。

You can extend the file contents of header。htm to a file called About。thtm。

The code will effectively add the contents of header。htm to the content inside about。htm。



![](img/befc4029c23cc1d6fb68553682a46999_27.png)

In this video， you learned about how template inheritance can save you time by reusing blocks of content such as headers and foottterers Well done you should have the four little lemon pages developed in no time。


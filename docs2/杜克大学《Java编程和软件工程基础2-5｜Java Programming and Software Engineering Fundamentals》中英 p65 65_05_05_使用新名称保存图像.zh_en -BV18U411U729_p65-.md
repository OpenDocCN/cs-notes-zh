# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p65 65_05_05_使用新名称保存图像.zh_en -BV18U411U729_p65-

![](img/83954554ee09432a43c0bf7fa5aa3f32_0.png)

Welcome。Today， what we're going to do is I'm going to show you how to make copies of images by writing a program to do so。

 I've got a file of images on my computer， and I'd like to actually read some of those images in and make copies of those files。

 So we're going to do that with a program。So， I'm going to create。A new class。

And we'll call it image saver。And we'll go ahead and open the editor。



![](img/83954554ee09432a43c0bf7fa5aa3f32_2.png)

And let's make it bigger。And what we'll do is we'll create a method in here called do save。So。😔。

And what we're going to do is we're going to use our directory resource that we learned about。

So I'm going to create。If I can spell it， right。I'll create a variable called DR of type directory resource。

And I'll have to create a new。Diirectctory resource。And then。

We will like to loop over and pick select files from there， so we'll create for loop。

And a variable F， which is of type file。And we'll use the selected files method from the directory resource。

And let's see what we're going to do with our files。

So now what we're going to do is create an image resource。

I'm going to create a variable type image resource called image。

And that we will have to do create a new image resource。And we'll use the variable F that we read in。

In our for loop。And I want to just make sure this works。

 So what I'm going to do now is just go ahead and have the image， just draw。

 and so we'll just draw it on the screen and see if this works。Alright， so let's see if this works。

 I'm going to try and compile it。And nope， I've got an error。 So let's see what it is。

So I forgot to put another curly brace whenever you get this reached into file while parsing and it's got this highlighted。

 So I'm going to try and add another curly brace。 I need one for my method to save。

 So let's put that in there。That looks better。 And you can also tell the way the colors are lined up that I was missing that。

So we'll compile it。 Okay， so it's still not compiling because it doesn't know what directory resources。

 So I have to import。Eduu。duke library， so I'll add that right here。Import Eduu do Dukeke。t star。

And that will。Should fix that error。 So let's compile again。Now it can't find file。

 so I'm also going to have to import from the Java IO library。

And I'll just go ahead and specify that I want to import the file class。

And let's see if that compiles。Yay， no syntax ears。Okay。

 so now we can come over here and we can actually run this and just see all all this is going to do hopefully。

 if it works is it will just display some images that I'm going to select。

 so we will go ahead and create a new image saver。

![](img/83954554ee09432a43c0bf7fa5aa3f32_4.png)

And then we will go ahead and run our do saveve method。

Now I have to find on my computer where I've got some images， so I'm going to navigate。To hear。

And in my I've got it on my desktop， I've got a folder of images， there it is。

And now I can select several images。 I'll just go ahead and select the Dynos。

And I'll select another one。 Easter eggs。 I could select as many as I wanted to。

 and I'll go ahead and open。 and our program should just draw these images。



![](img/83954554ee09432a43c0bf7fa5aa3f32_6.png)

And it did。 We saw the two images。 So that's great。 That seemed to work。I'll just get rid of those。

And let's go back to our program now and now what we would like to do。

 we know that we can get the images and we can display them。

 and so now what we'd like to do is we'd like to make a copy of them。

So we're going to add some more code in here。It。Okay。

 so now what we're going to do is first what we're have to do is we're going to get a file name from the image file that we have just grabbed。

 so I'm going to create a string for that file name。And we'll just call that F name。So the image。

We can use the image resource method that is called get file name。And if you didn't know about that。

 you can look in the documentation and you'll see all kinds of methods that you can use with the image class。

Iage resource class。So just gi file name should get me a string。

And then what we want to do is we want to create a new name。

 which is going to be like copy of the with the old name。 So let's create another string variable。

 This will be called the new name。And it's going to be， let's put make the string copy， dash。

And then we'll add that to the front of the file name and the rest of the file name will be the old file name。

So let's see we will call this。F name is the old name。So we've created all we've done so far。 well。

 let's try and run this。 Let's see if this works。 So if I will just compile this。

It compiled with no errors， so let's just run it。We'll come back over here。



![](img/83954554ee09432a43c0bf7fa5aa3f32_8.png)

We will create a new image saver。And we'll come over here and run our do save method。

We can now go pick some files。We have to navigate over to the desktop where my images are in the images folder。

And I can grab。Let's see Dynos and Easter eggs again。There we go， and we open them。



![](img/83954554ee09432a43c0bf7fa5aa3f32_10.png)

And we got them。 And now I also have the images folder right here so we can just look and see。

 we created a new name that was copy of。 And if we look in the folder。

I don't see any image that's called copy Dynos， so we created a string。

 but we didn't actually use the string to create a new file yet。 so let's do that。



![](img/83954554ee09432a43c0bf7fa5aa3f32_12.png)

So we have the name， but now we need to use it。 So we're going to actually， we。

 there's a another method called set file name。 So let's use that。 So we'll say image。

Dot set file name。 And what we want to set it to is this new string that we created。

 So let's do that is called new name。So that should do it。 And now we also。

 what we didn't do is we need to save the file。 So we have drawn the file。

 but there's also a method in the image resource class called save。 So let's do that too。

 We'll draw it and we'll save it。And that should save the new file。

 So let's run this and see if this works。We'll compile it。

And then we will come over here and run the program， so we'll create a new image saver。



![](img/83954554ee09432a43c0bf7fa5aa3f32_14.png)

And then we'll run our do save method。We have to find some images。Okay， and so again。

 I'll just pick dnos and Easter eggs and let's open them。



![](img/83954554ee09432a43c0bf7fa5aa3f32_16.png)

Okay， so they're displaying again。 But how do we know if it worked。

 Let's go look in the images folder， which is right here。And if you look in there。

 you'll see there are two new files in there。 One is called copy Dnos and the others is called copy Easter eggs。

 So it looks like they copied them。 Now let's see what happens if we run our program again and we select one of those or both of those even。

 So let me get rid of these old images。

![](img/83954554ee09432a43c0bf7fa5aa3f32_18.png)

And let's just run our program again。So I'm running the do save method。



![](img/83954554ee09432a43c0bf7fa5aa3f32_20.png)

I'm going to the desktop， picking some images to make copies of。

 And I'm just going make a copy of copy Dnos。 And let's make a copy of。Copy Easter eggs。

 And we'll make also make a copy of。Let's see， Roger。Alright。

 so we're going to make a copy of those three files。 and let's see what happens。Okay。

 so we had all those pictures pop up。And we'll just get rid of them。

 And if we look over here in the images folder， let's see what we have。 We have。Copy copy Dnos。

 and we have copy copy Easter eggs because we made copies of copies。 Thats what we did。

 And then we also made a copy of Roger。 So we also see a copy Roger。 So anyway。

 that's how you make a copy of an image where we grab the file。 We have to create a new file name。

 And then we save a copy of it with the new file name。

 but we have to give it a new name because there's already a file with that name。

 So we added copy dash onto the front of it。 Hope you enjoyed that。 Thanks。😊。



![](img/83954554ee09432a43c0bf7fa5aa3f32_22.png)
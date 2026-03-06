# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p55 p54_05_implementing-put-method-to-updaate-a-user-resource -BV1fryaYgEqb_p55-

![](img/62cad514bc55721e430593a8d55b1aa0_0.png)

Hi there。 Today In this session， I will tell you how to update。

The student receives with the help of this rest API， so let's get started。



![](img/62cad514bc55721e430593a8d55b1aa0_2.png)

And I'm going back to the student controller。So first of all， let me just add this get mapping。

Not get mapping， I should say the URL that would be required for this post request。

 which I forget the last session。Here I will go for the put mapping。

Where the student request needs to be added。Public。Vvoid， update， student。

Where I will take the request Paraor Park variable， whichever you opted out。Butt variable。

That's your first name。Stringful name。That you need to pass into this path variable。

What you can do is you can execute a for each loop。Student， start。From the student' list。

If any of the start dot first name。Is equals true。The first name that I have。

 Im sending in the path variableable。Then， Studdot set first name。

I also need to pass the student object right here。And that student object。

 I need to pass from the request body。So here I need to set this student first name as student dot。

Get first name。And same thing I need to do for the set last name。That's it。Otherwise。

 if this condition does not matches， does not do any operation。

So let's get run the application maker test。

![](img/62cad514bc55721e430593a8d55b1aa0_4.png)

I just go right here in the post， man。

![](img/62cad514bc55721e430593a8d55b1aa0_6.png)

First of all， I will get all the students right here。Let's say I'm working on the king1。

 So here where the name is king， I want to。Update that object。 And in the place of king。

 I wanted to update， let's say。ha水。Good morning。And I just want to make us request。 It saying that 4。

0，4， not found。Because it should be student， not students。So you can see that the status is 200。

 it means the update is done。And just right here， I can make a check with the help of the get request。

So we can see that King Kocher is no more because that has been updated with Kashmi Gman。So。

 that's how you。

![](img/62cad514bc55721e430593a8d55b1aa0_8.png)

Update request works。
# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p121 121_07_05_躲避障碍物碰撞兔子演示.zh_en -BV1QrB6BcEWW_p121-

![](img/ad2c53e9de03d7788e16616e2dc3983f_0.png)

Let's modify our project to handle obstacles。The ghosts will need to try to avoid the white rabbits as it tries to collide with the bunnies。

We have made several changes to the scene setup。If we click on the setup scene。

We're going to see that five white rabbits have been added to the scene。

We can also note that an object marker has been added over here。There it is。

 It's called ghost starting position。If and when the ghost collides with one of the white rabbits。

 it will get moved back to the starting position。If we click back on the editit code button。

 we can see two other changes。 The first can be seen if we click on the scene tab。

If we scroll to the bottom of the page。We can see that there is a new scene property added。

 it is an array containing each of the five white rabbits， and it's named obstacles。

The second change can be seen if we click on white rabbit。

There's a new procedure written for white rabbits called Wonder。Let's look at that。

We see that the white rabbit will move forward a little bit as it turns a little to its right or left。

The moving forward amount and the turning amount are both random numbers。

Let's create the event to cause all of the white rabbits to start wandering at the start of the running of the project。

Let's go to the initialize event Listeners tab and add a Sc activation listener。We'll need to go。

Down here。Let's add event listener called Sc Actation listener。For this event。

 we want to have all of the white rabbits wander while the time left is greater than zero。

Let's drag in a while loop。And we'll just pick true。We change the true。To relational whole number。

We'll select greater then， and then we'll select one as a placeholder。And zero。

 we click on this dot timer。And then the functions。And we're going to drag the get time left。

Over top of。Thewa。I'm going to drag up the scene activation listener up above the add time listener。

Just so I can see it better。Now inside the while loop。

 we will iterate through all of the white rabbits simultaneously。

We drag in a each in together loop into the。Inside of the wild loop。

We're going to specify the type as gallery。And white rabbit。Then we'll have the item name be white。

Rabbit。Itterator。And for the array， we'll just use the obstacles array。Click， O。

We now click on this white rabbit。And the Proc tab。

 and now we can drag in the white rabbit W procedure inside the body of that loop。

We need to change white rabbit to white rabbit iterator。

The second event we need is for a collision between the ghost and one of the white rabbits。

 we click on the Add event listener at the bottom。And we select position orientationation。

And then add Col， start listener。Now the first set will be a custom set。

 which will just contain the ghost。So we'll selectCustom Ar。

 and then the second set will be the array of obstacles so we can just select that array。

Now we have to add the ghost。There it is， that's the only thing in the first array so we can click OK。

And there's our event， I'm just going to move it up above the Add time listener。

So we can see it better。Now we click on this。 ghostt， then it's already there。Then inside the event。

 we want to drag in a ghost move。And Orient2， so we're going to drag that。

And we want it to move an orient to the ghost starting position。That's it。 You can now play the game。

 but try to avoid the obstacles as you click on white and blue bunnies I'm going to click run。

I'm going to use the arrow keys。We have to watch out for these white rabbits。 Oh。

 I had a white rabbit。 I bounced back。 I've also got -1 already。Let's try to get some points。嗯。

About to zero。Let's see。 We've got one。We've got two points。

We've got four points now we need to go find some more bunnies ah we lost， all right。

 let's try it again。We'll have to click restart。Okay， we need to try and win this time。Let's see。

Okay， we got a blue bununny。We got another blue bunny， we need one more。We got six points。

 I think we're going to win。We gotta stay away from that red bunny that's hopping around。

We can even try and get one more。Oh， we got seven points， we're doing great。



![](img/ad2c53e9de03d7788e16616e2dc3983f_2.png)

Yes， great job。A， we won。Well， we hope you enjoyed watching us play this game。


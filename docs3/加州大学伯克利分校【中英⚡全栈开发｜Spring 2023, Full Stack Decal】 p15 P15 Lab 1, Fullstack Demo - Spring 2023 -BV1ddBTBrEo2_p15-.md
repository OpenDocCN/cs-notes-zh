# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p15 P15 Lab 1, Fullstack Demo - Spring 2023 -BV1ddBTBrEo2_p15-

Through this labs more of like a walkthrough kind of demo kind of format and then the rest of the time I want to give back to you guys and your mentor to do a check in and have some work time to grind the final project out so if you guys saw on the weekly post you know he linked to this lab spec which is pretty sure it just kind of talks about what the lab is about and we actually have files that you can download and kind of follow along if that helps this lab actually is a final project from around like two three years ago so it was actually one of the final projects from some of our core staff last semester and actually our VP education president's last semester as well so this is their very own project and because it is from kind of like just even a couple years ago some of the code is a bit old so Ri kind of works a little bit differently but your all your assignments like this past semester should be like。

Accurate on that， at least。So again， if you guys want to like look at the code there' over here is just under。

 you can navigate to assignments， labs， and then full stack La， which is our only way。😊，So yeah。

 it goes a little bit on how to like kind of download it onto your own machine。

And how to basically set it up and start everything up but I can I will also just start off this lab showing you through the website and basically what it is so it is called up and coming and it's basically a website to host events and organize volunteers for events so like you can add people to an event they can like sign up for different ones。

And。Yeah， so if you see like I've made some events already。And yeah。

 here's the team that designed it last or a few years ago。

So yeah i'll just basically kind of walk through it real quick。

 so we have this is like basically the landing page homep page and you can sign in you have that's a feature like making a user don't have an account。

 it'll take you to a register page。😊，And we can just。Sign up。嗯。Let's put in some fake data here。

And then it'll take me back to a assignment page。All right so once you sign in it'll take you to a browsing page and it'll basically show you some events that are coming up I actually inputed these a bit earlier so originally it'll be like a blank page and I think would be here but yeah we have an ongoing event and then we have an upcoming event。

😊，And one of the features also is to filter so if you see they kind of have like little tags right here。

And let's see when I do。Educational。It would filter out just for the educational ones。

And now let me show you how to create a event， so basically takes you to this。

Big form page and you just put in a bunch of this data so what's upcoming。😊，Steve dead week。Yeah。

See perfectly。And you can choose from a different some other like drop down little drop down menu with different tags。

You can do some start dates， I'll keep that。amam。Put in some fake data here。U see Berkeley。Eley。而且但是。

It has a little confirm button， submit and it takes you back to this homeage。

 but if you go to browse you should be able to see。

All your events so that's the one I just made and it's the past event because I was who leaving I didn't want to put in a fake date so it did the default 1970s but yeah and then they also have a profile page which shows if you remember the data that I put in so ask for my name asked for a username that's right there。

😊，And then I believe I can actually like click on events and sort of like sign up for them to volunteer so let's click on like Cal day I can like join it and there you go。

So that's basically a super quick rundown of their project and you can literally play around with this website all you want it's also again it's on that spec。

The the front end and the back end files and just to clarify。

 they did actually split up the front end and the back end。Fileles into two different readbos。

But actually， I'll show you my VS code right now。

![](img/96dd103c7730e404265dde0882337964_1.png)

I just separated them into folders， which is like kind of the organization that we would like we would want you guys to do and we would like to have both your backend and your frontend file in one GiHub repo so that's just like a note even though like they split it up this is kind of how we would want that format。



![](img/96dd103c7730e404265dde0882337964_3.png)

All right， so that will get out a really quick website demo Oh I also want to show that。😊。

Even if I sign out。And sign back in， the data should still persist and like kind of show my own profile again。

So yeah。😊，And now we'll just go through the code and I'll go through the back and first and then the front end。

 but actually you guys have seen very similar kind of formats before。



![](img/96dd103c7730e404265dde0882337964_5.png)

And routes you've dealt with in the most recent homeworks so like user off you've seen backend with like the different items item lists or something like that and then front end you've interacted with homework four and homework five and actually homework five did deal a little bit with like that interaction between the front end and the back end。

So don't worry， even if this is like big code bases are always scary。

 you guys have definitely seen some of this at least a little bit before。

So starting off with backend， again， you kind of have this。

General format of keeping your route somewhere and your your model somewhere， this is no case size。

 by the way， or should I like zoom in a little bit？I'll zoom in just a little bit。

Just to show like the different older names stuff， but yeah， let me open up routes。And again。

 these should or that some of these naming should have some familiarities， so like off。

 which is homework nine， which I really recommend if you want to implement something like user accounts because homework9 is also kind of like a demoly homework where you kind of just follow a lesson that kind of has answers already so you can see and。

Like。Kind of do it on your own and see like what works and what doesn't work。

So you kind of split up your routes into I kind of like to think about it as like different pages。

 so like off dojs I maybe want to have all like the the endpoints that I want to use on like the sign in page or the login page so here you see like this route represents like the register page。

Um， which would probably， you know， like take in a new user do all that data。A login page。Again。

 like you probably expect like a username a password and you kind of work with the data to check if。

 you know， is that a user in your database， do they put in the right password。

 that kind of data checking。Which again， you can definitely find on homework nine and I don't remember the corresponding lesson number。

 but the corresponding lesson also has all the code there。

And then just to go through another kind of backend file。

 so we have an event so here we have we see we have a link that's to create events。😊，And you'll see。

Get events。And just like keep these kind of routes in mind when you are working maybe you're working specifically on the back end。

 what kind of links and what kind of like data end points do you think like the front will need so you won't just need like a link just to create an event but maybe the front end will also want to load all your events for you so like maybe creating a get link like that would be very useful。

And then models again。You guys have seen this different schemas。

 maybe like what kind of data do you want to save in your user schema。

 if you guys are creating like a new kind of object like events here， you know。

 again just keeping in mind what kind of data you want to save in there。

See that was very quick rundown of the back for this website by the way yall like this is all straight running like from my or this website is like。

Just running from these two two terminals open this one to the back end in terms of front end。

 so like it's all running right now live。Any questions for the back end yeah？

So this is all on like momma TV， yeah yeah。So you'll see like， yeah， like this uses mon goose。诶。

我有俾啊啲。嗯。Oh here， so this is like where they kind of set up their Mongo Db server。佢是我爸。嗯。哎呀。So。

Any backend questions？Okay。I'll now move on to Fnon let me pull up my notes。Yeah。

 so let's move on to the front end files I'm just going to close this。Yes。Okay。

So for front end I just kind of wanted to show like some bits of the code that kind of interact with those back end routes that you know maybe the back end team created so here's one example of in the sign in dot js file where this is。

A react file that kind of represents the sign in page。

 so let me just pull that up so it's like you can see it visually。

So you'll see it has this function called like login attempt again like expect this kind of format to look a little different because I believe this is like some。

Like a lot older react code， but this is a function that basically represents a login attempt。

And you'll see that， you know， like the user will pass in some username some password。

 and then they use Axios to kind of interact with that backend and they basically you know pass in the username and password that the user would give them。

You see this promise that if like the correct result comes back they'll say success logged in they'll have a data to it。

 this is all kind of again refresh from homework nine。

 but I just want to point out one specific line that kind of shows an example of redirecting your user if like something successful happens like if they did successfully log in then this redirects to the browse page which maybe is something you want to know for your project。

嗯。诶。Yeah， so that's like kind of a quick sign in。I guess that kind of like is an example of the front end component to like homework nine。

 you saying。And then here is profile。js， which represents。系。I just want to make sure it was still。

Recording。Okay yeah so profile dot js is oh again I also wanted to show the format of this front end kind of folder so you'll see they kind of broke it up into pages which i've been those are those are like the files i've been showing you recently they might you know split up like their assets into different folder that hold like you know all these different pictures maybe of like。

I don't know， like little logos。嗯。Broke up their styling and then to smaller components。

 so this is a very like typical kind of front end layout that you might see。😊，Okay。

 so back to pages and again， I'm in profile。js。And you'll see that if you kind of just like skimmp through this a little bit。

 it kind of， if you read like some of the functions that say like my profile area profile format or kind of looks like react code to render like someone's profile like if they logged in they want to go click on it。

 you'll see that this would be the code to do that so。Again。

 I just wanted to show profile and show like the。An example of getting data and like loading it so how I said earlier like oh maybe you want to make a endpoint to like just get data so you can maybe like render it on a page and show someone like all the events they signed up for all the upcoming events for them。

U so yeah， I just kind of kind of want to reiterated that。You'll see like my events。

 it'll take in the data and then maybe some condition that you'll use to like filter out just their events。

And they'll basically reuse。嗯。There are components to load that。

 so actually I wanted to pull up a component oh here， event card。Will you see that。

I'm pretty sure all the functions like before this is just like formatting stuff but。

This is an example of。Making like a smaller component。

 so here they have just what called event card which they'll just use to like show one singular event and they'll basically like reuse this for all the different ones that like all their users would use if that makes sense。

Like they broke up a smaller problem into this smaller component and they're just like reusing it throughout their website。

And you'll see that actually the event card file isn't making any of those calls to the database it's all from either like their main page or their profile calling those and then passing in that data as a prop to smaller components like the event card。

 which kind of makes it nicer to just like，Wellch I guess is like a good representation of like this flow of data throughout a full stack。

cha， does that make sense？嗯。But yeah， I guess any questions at this point in the front end， yeah。一起。

I believe yeah， I believe so so that I can show you like an example of。One of those， I believe。

Maybe create page。嗯嗯。Actually， I think it was in registered。Yeah。

 so here's like an example of like axiosose。I found this in the register file so like this you can imagine like a user wanteding to make a new account so yeah you can see that like that would be a post present because now you you're making like this new entry into the database。

No。Anything else yeah definitely feel free to like play out of all these files I literally just。

Downed them and then I put each， I guess， like repo that they made into their own folders。

Andto their own folders opened up a terminal for each folder and then just did NPpm in it and NPpm start just have both serververs running and。



![](img/96dd103c7730e404265dde0882337964_7.png)

Like I have this website up like just rolling and you can try it out。

 put in your new put in your own events， put in your own users， and see how it all works。Um yeah。

 any exam or any questions on like the overall process or like the overall relationship between like front end back end。

 full stack， anything， even any like project specific questions。



![](img/96dd103c7730e404265dde0882337964_9.png)

诶个。Okay， so I'll leave this up I guess， but if you stayed for the full stack lab。

 I'll give you guys the attendance to full stack and actually this code is a little different than。😊。



![](img/96dd103c7730e404265dde0882337964_11.png)

The last few months。Can you please put in this attendance code into an attendance assignment on gradecope so there should be one now let me know if it's not showing up。

 but if you go to your gradecope there should be an assignment called attendance and there should be two for your response boxes one that asked for attendance code and one asked for Berkeley email and then just put in this for the attendance code and then put in the Berkeley your Berkeley email address。

And then submit that。And then I'll actually also use that mean if you'll use that assignment to post your attendance grades。

Yeah。So you do that， don't use the form， just do it on your grade scope。

And then after you guys are done with that， we will use the rest of the time to do some mentor check ins if your mentor is not here and they didn't reach out。

 come to me， tell me if they did reach out and maybe like our。

Meeting up for another time to do a check in then that's perfectly fine but I would definitely you know utilize this time to work on project because I know how hard it is to kind of meet up with like your entire group and find a time that all works for you I was hoping that lecture time would be the perfect time for that so yeah let me give this time back to you also open08 you can come ask me anything but yeah thanks for listening to the full stack lab。

嗯。Yeah。

![](img/96dd103c7730e404265dde0882337964_13.png)

嗯。怎么。
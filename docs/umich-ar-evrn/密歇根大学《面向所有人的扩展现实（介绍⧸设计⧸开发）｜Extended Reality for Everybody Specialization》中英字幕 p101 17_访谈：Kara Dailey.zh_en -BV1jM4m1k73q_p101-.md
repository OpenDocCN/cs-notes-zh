# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p101 17_访谈：Kara Dailey.zh_en -BV1jM4m1k73q_p101-

![](img/e8acbe57d14520d74ff932fbb01bf287_0.png)

![](img/e8acbe57d14520d74ff932fbb01bf287_1.png)

So in this video we're going to have well we are going to have a conversation with Kara Da。

 Kara worked with me on several projects and also supported this MOOC and actually taking some of my AIVR courses as well and the most significant contribution she made to this MOoc is actually helping us develop a VR project that we can use in the course to learn about how to design a virtual reality。

 how to navigate in virtual reality so locomotion and then also doing object selection and object manipulation in virtual reality and all this will be based on our Detroit zoo in virtual reality and so I've invited Kara to talk to us about the project and review it a little bit and well so let's get started。

😊，Hello Kara， how's it going？😊，Hi， Michael， I'm good。 how's it going？ Yeah， doing fine。 So you know。

 doing Zoom recordings all the time。's that's how we have to do it。

 So it's good to see you So we're going to talk about the Detroit Zoo VR project。 And so well。

 I thought maybe you could introduce yourself quickly So we learn a little bit where you are just a bit about yourself to have a little bit of opportunity。

😊，Yeah， sure。So， so I'm a。Recent graduate from the University of Michigan School of Information。

 I just received my master's in May and I'm currently looking for a job right now。

That's good to know。Me in a nutshell Okay， that's cool and you've done a lot of user experience design and research projects and you have also worked on XR。

 you've taken both my courses and as I said， helped a lot with this MOO and one of the projects。😊。

Well， the one project we're going to talk about today is the zoo you created。

 and so let's look at this together。So this VR project actually started out in an office hour。

 I felt like I wanted to tell my students a little bit about geometry and kind of like recreating real world elements in virtual reality So I created this rough layout of the Detroit zoo and I started collect some animals。

 animal3D models And I think that was the starting point for you and then you took it over and you turn it into this beautiful project So first question。

 like what do you think to which extent is it still or has it ever been kind of like the real Detroit zoo and which parts are unique to our virtual reality version。

😊，Yeah， so you know when you handed me this project you kind of had this skeleton version of all the different areas of the zoo and I wanted to keep it consistent with what the Detroit zoo looks like right now so I did a little bit of research into what those areas look like what they're titles I know that there were some differences between what you had and what the actual Detroit zoo is currently so。

That was something that I wanted to keep consistent with how it is presently and then also I'll talk a little bit more about the models that I needed to use and the different types of animals but I wanted to keep those animals consistent with what animals are at the Detroit zoo today so you know you'd see giraffes and you'd see gorillas and you'd see bisons in the American grasslands area and I wanted to keep that true to the experiences if you were to walk through the gates of the Detroit zoo but there are also some exciting aspects that we were able to incorporate like the night zoo that doesn't exist at the Detroit zoo today。

 but if it did I would definitely buy a ticket it's really fun and exciting and that's you know the opportunity that VR provides and therere also like you know the petting zoo and the feeding area that you don't have。

Currently at the Detroit zoo， but the feeding area was inspired by。When I was younger。

 I went to the San Diego Zoo and I was able to feed a giraffe which was a really cool experience as a kid and you know you can't do that in every zoo in every city。

 but if you create a zoo in VR you can make that possible that's and I've actually I've actually tried it out and you know you put a really big gorilla there in the betting area so this kind looks really b so I was a bit scared。

 but then I started feeding some of the bananas I mean that part that part shows basically what what we' teach our learners in this course would teach it last so the object manipulation stuff and there are some action challenges I think this is some of the hard parts to do in VR unless you use like a library which we used there but so I want to unpack a little bit that designing the virtual reality part you've already told us about the animals and。

And then， you know， making it consistent and then some unique aspects。 So then， you know。

 when you normally go to the zoo， there's a lot of walking。 So then in virtual reality， how do we。

 what are the ways in which we can navigate your zoo， your virtual reality zoo。Yeah。

 so you can offer the opportunity to teleport around if somebody's using a headset with controllers and you kind of skip walking down long roads to get from one end of the zoo to the next you can kind of hop along your way and you're there much faster and then the other way of navigation that I wanted to include was the menu buttons that you see。

 I was you know coming back and forth from Boston， I had my headset didn't have my headset so debugging was difficult for me so I needed to create something that I could。

Debug with within the web browser。Yeah。And the other way that I wanted to offer a way to move around the zoo was through the menu that you see when you first open up the application and you can see the different areas that you can navigate to and for me it was really something that I needed to do because I didn't have a headset to debug with so I needed something I could use within my web browser or with my Google cardboard where I could click and I could migrate across different areas really quickly。

 so I think in thinking about also the people who would be you maybe seeing this example who might not have access to a headset or don't own a headset being able to offer this same kind of experience of moving along the zoo was important I think Yeah I agree and it actually charges also on some of the more advanced topics like how do you really。

Design across a variety of headsets and support like 3 degrees of freedom。

6 degrees of freedom with controller without controller mouse interaction。

 if it's just 3D on a desktop。 And in fact， your project can actually do all of this。

 maybe except for the feeding bananas part， which I think for that。

 you actually need a headset because you need a controller and you even though that we could also with summer refinements。

 we might actually also get it to work with the mouse。

 but it's just such a lot more fun with with the controller。😊，Sure， and I think when I was designing。

That portion specifically， I was thinking about ways that you know how could I incorporate this feeding aspect for people who might be viewing it through a cardboard and I remember working and trying to you tap on the banana and have it shoot across。

 but that's you know not really true to a real experience of feeding an animal。

 it doesn't really work like that so it felt kind of weird for me and I think the way that we did it was truest to how it would be in real life。

Yeah， now that's cool。 Alright。 right。 So actually， I think， I mean， if I remember correctly。

 there was a lot of converting of the models and all that。

 So I'm gonna ask you this question around what are what。

 what were some aspects that you thought were difficult to， to design and to implement。

 So we can also talk about development。 So this is a portion in in the M mooc we are now really even more focused on some of the development challenges and working with a frame So you can talk about a frame issues and all that。

 So I'm gonna。😊，So we're going to make a transition。

So that's a cool overview of the project and and a lot of the design work。

 And so I actually wanted to ask you like， so which parts do you think were actually difficult to design and then also to develop and implement with with a frame and for the VR that you did。

😊，Yeah， so I think it was challenging working with the Google Polymods because you know when they're built。

 they're not always built in the most consistent way on Google blocks sometimes they're gigantic and you know when you placed them in your scene。

 you might actually be inside the model and you don't think that it's functioning properly。

 but you know once you kind of play with that and the way that I set up my models was I had a code pen scene and I made sure that they were all zeroed out on a flat level and all of the sizes or the same and that allowed me to kind of copy and paste into the scene I was working with so that I could keep everything really consistent and I didn't have to go back and forth and try to figure out what the sizing was or try to locate an object you know maybe it might have been placed inside of a tree so far away that I couldn't see it。

うん。So that was something that I think was unique to this project where a lot of planning actually went into developing and getting the models into the scene that you see in the video。

 Yeah， so we in this project we didn't want to create our own models we actually wanted to work with available free open source models and we used a lot from well created in Google blockss as you said。

 and I think you're giving a really important tip that are also stress in in the MOC which is like developing a complex scene like this in stages and maybe in even separate scenes and then even changing the layout。

 like what you describe， this is like a really cool prototype or lab scene that helps you develop and get the dimensions right。

 And I think you did a really good job like the giraffes have have a really good scale。

 there's still this one monkey that I'm scared of I wish the best more， but you know that's cool。

 You're also showing a variety in terms of like models with animations and some。

And some have really good material and look very interesting in some of the light。

 you know we have the torch light and all that， so when there are some issues there as well when you work with these models or was the material wise was that relatively straightforward？

So a lot of the Google polymods were kind of inconsistent but I ended up using the aframe inspector to see if I could you know change the lighting on them and I also when I was bringing in the forest environment that you see I didn't want it to be fully wooded because you know a zoo is kind of sparsely lined with trees and things like that so I use the inspector to kind of edit those variables and the more advanced animated models that you see are all from SketchFab for free so it was。

Not something that I had done before was include the animated models into any of my projects。🤢。

That somebody else had created so that was a different experience for me typically I have just used Google Poly modelss where there's no animation involved。

 so that was that was a good learning piece I think that's cool so I show the collibri And there are some other models as well it's really nice and actually you know the other thing you paid attention to and seems like when you look at it。

 you just take it for granted， but like you placed all these animals you rotated them a little bit。

 you chose some interesting compositions you basically copy pasted the same models multiple at times but it doesn't always feel like that So would you say was would you say it was easy to create the VR version or was it very tedious how do you characterize the project I think it was definitely more difficult than。

Other projects that I've worked on in your courses。

 but I was able to organize things and set myself up for success before I had actually started to build the scene and that made it feel more approachable Yeah that's cool I mean the strategies that you shared with the prototype scenes and you know breaking the project down into aspects So when we look at the menu we have like these maybe nine or something different places we can go to did you create each of these separately or like how did you how did you plan out the project Did you always work in across the entire map or did you focus on like scenes by scene I mean I mean these locations or how did you how did you do that part of the project Yeah so I kind of sketched everything out in you know like a physical sketchbook before I started and I I kind of。

Put the camera in a place and organize the animals in kind of a really rough sketch just to kind of get an idea of what my goal was and。

What you see in the final result wasn't necessarily the same as the sketch like I was able to find the really cool conservatory model that I didn't think I was going to be able to find and so there were those really cool。

Times where you know something exciting like that happened and I kind of switched my focus and I was kind of able to adapt there。

Yeah， that's cool。 Well when we look at it， do you， I mean， I don't remember whether you。

 we paid a lot of attention to time。 But what do you think， How many hours of work are we looking at。

Wow。I mean， I think we spent like probably a month or so on this project and you and I kind of going back and forth。

But the planning and then the implementation probably totaled like 20，30。To 40 hours。 I would say。

 yeah， yeah， So it's important that learners don't just think go cool。 I just gonna do a zoo。 Well。

 you really have to plan your time carefully。 So and some things。

 I think some things look decisively well simple。 And then they're actually quite hard。 Do you。

 do you remember any kind of specific instances where some things turned out to be more difficult than you had anticipated。

Yeah the object manipulation was definitely tough for me I'm not somebody who comes from a technical background so you know writing HTML CSS using libraries has been something I've had to learn within the past two years in the program myself so I know that you and I had you know gone back and forth about the object manipulation and how I might get that to happen and so it was really。

A trial and error process with that， but it was definitely the most difficult part I think of the whole project for me。

Okay， so well then speaking about this， really one。

 which was also one of my favorite aspects of the VR zoo the you know。

 the pettingoo and then the feeding area as well。 So do you remember which were there any things that were particularly hard can you give some examples。

 I know the overall things is difficult， but what were some of the challenges you faced there and how did you solve it。

Yeah， so I think the object manipulation aspect was pretty difficult for me。Initially。

 I wanted to start off with kind of the point and click and having the banana shoot across the scene so that you know。

 people who were。viewing from maybe a Google cardboard or just through their web browser would be able to feed the animals just like somebody might be able to if they were using you know an Oculus or another headset but。

I found it difficult to incorporate physics with that and there was a lot of， you know。

 going between different libraries， I know that。I tried to incorporate different Don Mccururty libraries and pick aspects of other ones and it wasn't necessarily working out the way that I hoped so that's when I kind of switched the experience to just a headset and controller guided animation。

Yeah， so in the end， we did end up using this super hands library， I feel， I feel。

 So that basically supports a little bit of controllerbased interaction。

 And so then you can reach into the objects and you can pick them up and then you can move the banana to the monkey。

 But then when you release， you also have to maintain velocity。

 And this is where the physics kicks in。 and so like from a technical standpoint。

 definitely one of the more challenging interactions that you implement it nicely。

 I do like that the bananas are a little bit bigger than normal bananas。

 where there's some reasons why you made these objects a little bigger。Yeah。

 I think that if you have like a larger object， it's you know easier to grasp and once you throw it。

 you can also see it move further out too。 So that was just my reason for making them a little bit larger and plus the monkeys were big to So you needed larger bananas for larger monkeys Yeah it is a virtual reality after all So why do we have to copy paste all that one to one。

 So I actually think you made really good decisions there so that's cool So there is actually a lot of interactivity already in the zoo。

 we can navigate， we can walk around we could do the feeding So we have all these things but you know we were also working on a time limit here but I was wondering what kinds of if you had to extend this project where would you spend your time what do you think would be the most important things that would maybe help immersion or make it feel like an even better virtual reality What do you think。

Yeah， so in terms of immersion， I think altering the birds to kind of animate on a track within that conservatory would make the experience more realistic of being in you know this conservatory with birds flying all around you so that was something that I would have liked to do if I had more time on the project and I also didn't play around with。

Sounds at all either。you know， maybe adding cows moowing within the American grasslands would have been cool and added to the immersion aspect。

 or you know when you pat a monkey and'd scratch it behind its ears in the petting zoo， you know。

 having that monkey make a noise would be something that would add to the experience。



![](img/e8acbe57d14520d74ff932fbb01bf287_3.png)

I agree these are cool examples but I think like you know every project is time limited。

 I think you spent your time very wisely you put together a nice scene for us to learn about and now we also know which things we could expand on So I think this is really helpful Yeah so these were really great insights Kara So you know with the one thing I'm doing with everybody I'll bring in here is going ask whether you have some like last minute advice and some kind of piece of information for our learners when it comes to developing with aframe that's something in for virtual reality that could be a specific advice or also something more general。

 what would you tell our learners who want to learn more about doing XR projects。😊，I think。

I've had the most difficulty in Michael's courses when I don't plan things out for myself where I don't really set myself up for success and in doing this project。

 you know doing all of the legwork in the beginning。

 like setting up the models and making sure they're all consistent sizes really helped me be successful in this project。

 and I think that's just a note of advice that I would give to new learners is do the hard work first and then you can play around with changing you know the environments or moving around the models but do all of that difficult legwork first。

Cool， alright。Well that's cool well thanks Kara for sharing this with us we're going to use your zoo to learn more about each of these aspects in the course。

 so I'm going to share a lot of these examples in a little bit more detail but I also will include this interview with you because I think this is really cool to learn from the designer and the developer herself。

 so thanks Kara。

![](img/e8acbe57d14520d74ff932fbb01bf287_5.png)

![](img/e8acbe57d14520d74ff932fbb01bf287_6.png)
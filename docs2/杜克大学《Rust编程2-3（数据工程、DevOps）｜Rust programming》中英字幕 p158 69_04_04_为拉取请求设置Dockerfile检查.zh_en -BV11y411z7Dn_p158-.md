# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p158 69_04_04_为拉取请求设置Dockerfile检查.zh_en -BV11y411z7Dn_p158-

![](img/d8e11bac604c1d2e3c3958077be2026c_0.png)

Now we want to add another another check here now that we have a Docker file， which is this one。

 Let's take a look at what we have， it's screening our redactor。

 That's the name of our application here， we have these we want to link Why do we want to link well we actually want to do two things。

 we want to Li and we want to make sure that we're not breaking this。 So let's do let's do both。

 we're going to add right here when I add a separate one when I say Docker Docker check and when I click that Yamel So what we're going to do there。

 we're going to actually open the clippy so that we have I usually like to like because Yammal can be kind of tricky and complicated。

 I usually like to do this copy that。And then go back to our new file and paste that。 And well。

 this is no longer called clippy。 We can say Docker check。 Yes， thank you so much。 Coil it。

 and I can save that。 And then I'm going to run this on a push and on pull requests as well。

 Allright， so this is good。 and we to have the steps。

 and we're going to want to have all the way here to line number 10。

 So all of these all of these right here。 Well， the formatting is all messed up。

 As you can see that's one of the problems that runs on needs to be right here and the steps。

 let's take a look。 Yeah， that's perfectly indented。 So that's that is very good。 Alright。

 so what do we want to do。 Well， we want to。😊，We want to say a name， and we're going to say run。

Docker， Docker file LinkedIn。 and we're going use a special。

 we're going to use a special thing that we can do here。 And that is called Hadalin。

 And I really like Hadlein。 I'm going to say。😊，Right there uses Hadlein。

 and that brings in a helper that will allow me to do。Allow me to do the Linting。

 So I'm going to say with Docker file。 and I need to specify the what what Docker file I have。

 So that would be my Docker file right there。 So this。

 this setup right here will allow me to do will allow me to do the the LiIn。

 Now this wouldnt wouldn't be called the build job would be called the Liing。

And then we can actually add on our step， which is actually going to be。

We can say uses well we can actually start adding adding the Docker the Docker building so to build Docker and this is an interesting approach。

 by the way， you can you can actually say name build Docker but don't don't push right so we're going just build and make sure that like even if the LinkedIn is okay or not okay。

 it doesn't matter， this project will actually build so we're going to say Docker build push action version2 and we are going to accept everything that coppit added except we're going to remove this tag so what is going on here like let's just go step by step here we're using a helper called build push action that means that this will set up everything that we need in order in order so that we can use Docker。

And build everything that we need the context is going to be dot。

 we need the root of the repository and the Docker file that we want to use is the Docker file at the very at the very top at the very root and we're not going to push anywhere So we don't care about pushing and if we save these and we commit and push then we will have these available right away so we can actually try that when I go here and'm going to add absolutely everything that I have make fileile clippy and Docker check and I'm going to say at CICD checks for project andm I commit and commit and push。

And once those are there， I can go to the website so let's actually go to the project and see how that behaves。

 Okay so here we are and we already have failures。 Do you see that because I pushed one minute ago if I click that this is the beautiful thing about everything that we've added So if I click that it'll say hey what did Alfredo pushed right here we start with a LinkedIn this Github action is already explicitly adding those inline comments and saying hey warning using latest this pro to errors if the image will ever update pin the version explicitly to release tag very good suggestion I am not using a pin version So this good at some point break and that opens up the problem from from having code that is incompatible this is right here core Dev automation useful positive outcome from adding all of these things that we've been。

Because so far we've had in all of these files all these checks。

 make fileile LinkIn clippy installing what's the benefit right here。

 This is absolutely cold and this is so easy to miss but right now we're getting we're getting that right there we're no longer getting anything else annotated it if I go to actions you will see that we have Cpy and Docker check and Cpy will say we probably fail because as you know we had some warnings there and you can say you know I wasn't using this one so it definitely complain there and not only that but we also we had the annotations there for clippy which is great。

 we also had a Docker check so let's take a look at the Docker check perfect we have LinkIn and we also call the LinkIn because it that's not a very good thing but that's definitely using latest these prone to errors now however we weren't able to build Docker but dump push because the LinkedIn。



![](img/d8e11bac604c1d2e3c3958077be2026c_2.png)

![](img/d8e11bac604c1d2e3c3958077be2026c_3.png)

![](img/d8e11bac604c1d2e3c3958077be2026c_4.png)

Definitely fail。 so we were not able to do that。 So definitely that is very good。

 Now we have a solid strategy here to prevent things from coming in。

 even though that I pushed right away， you can see now that I have that red X that signifies that I'm messing up the project and the state of the project is far from ideal。



![](img/d8e11bac604c1d2e3c3958077be2026c_6.png)

![](img/d8e11bac604c1d2e3c3958077be2026c_7.png)
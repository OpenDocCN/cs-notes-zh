# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p10 P10 Lecture 9, Node - Spring 2023 -BV1ddBTBrEo2_p10-

Yeah。

![](img/7d6c21f07be064be8e2b53d1455dcb32_1.png)

嗯。没有。

![](img/7d6c21f07be064be8e2b53d1455dcb32_3.png)

All right， there's age 15 so we going get started。嗯嗯。All right， today's lecture7。

 no this but NPM sent note package manager。I'm interested in a new infrastructure on going a little bit slower and also I'm going to allow you guys to type out handtyping that way you consider type it yeah so if you have a computer pick it out you make sure you can follow on everything handtyping。

Yeah， I should be able to run get your computer and we won't sort via a demo right away， but yes。

So what is noG so you're going to now already JavaScript that is about can only run on the web other languages you make familiar like Pth or Java they can run on the can programs so node GS essentially allows to use this is JavaScript。

 that's pretty cool that wasn't originally in case of JavaScript， but they added it。

 so that's why it's called node GS not J。So you can download it。

 I'll show you already I havent you can do。You've been running react。And that comes with no JS。

 so you don't need to install noGS apart from that。嗯。

You can check if you have it by just opening your terminal and running node。

That has to tell you whether or not you have it。N PMM。Stands for node package Manager。

 I'm sure you used it as well。And it basically allows you to install packages。

 so it's kind of like if you use P PIP for Python it installs packages for you it's great and also a couple P doesn't do this but NPM does it kind of sets up a whole product environment which is pretty cool。

 you'll see that in a second。Yeah， like that， so you said things since become come online line like MPM23。

 and there's a bunch of cool stuff and you'll be using it。呃，BSO。

What's cool about nodeTS is that a lot value in a powerful context。

So when you run any browser can your really access to stream。

 you can maybe do some pop ups and download files about the about it。

 you don't have access to the file system， you don't have unfiled access to the internet。

 you don't have access to for starting a web there are a lot of things you can't do that you will want to do that you can do for someone with Python。

 right because you want just in your computer。With no J， you can do that。嗯。

But there's things you can't do anymore so with no jazz you're just running anything mindline imagine a bunch of text right so you don't have the website anymore it's just JavaScriptscript so you can't do stuff like document Doug Allen by anymore't it doesn't make sense anymore。

Because。It there's nothing in need to document it or something there's nothing to change sense。

 I'll show you in a second。So if the first examples of something。

 then I'm going to show you how to build nodeGs。Is a web server。

 so you've be making a lot of websites and you can help us in posting employee your chart very nice however。

 it is important to learn how to make your own website。

And what's actually going on when GiHub sort of whenever you ask GitHub for your website it sends it back to your client and it shows it for you what is going on that well this is what's going on there's a computer told server over here which is on this computer somewhere in GiHub service is permanently on I have your files I'm waiting forever until suddenly one of us comes to integrate your project over and we send the request GiHub GiHub service sends back your website you about HTML。

my browser course's going on， but note that it's a computer that's always on in order to website to build other a server。

嗯。What's cool about this is once you have a server that's giving someone your website and the website is running on your computer。

 you can use the server for more so。So hypothetically， imagine I give the user browser a coin， okay。

 which I instruct to make another request for myself， of course not a original one you get website。

 for example， imagine you give the user a login form。And that login form when user click submit。

 it sends another request to that server which already gave the website。

 it sends another request that server。Asking hey look is this username password valid user and the server on yes it is server that bunch of stuff right fit with any database it's like oh is it here or not and test plan yes it is and they kind out says okay perfect I loggged in so servers both give you the website with your coding and they can also do other stuff if you just。

😊，Ask them to other stuff and I'll show you this is we feel complete in a second。

 but the main point is the server is always is on basic server all is on route it and on when you are accessing new website。

Cool， so now is a moment well I will ask you everyone to grab their computers and open them。

This will be a short lecture in total because we're doing checkoffs at the end， I。



![](img/7d6c21f07be064be8e2b53d1455dcb32_5.png)

四啊嘅系苦啦。So yeah just make， so I'm going to ask you to make a new VS code whatever you're using project and in the project I'm going to ask you to make a just a JavaScript file。

So。I believe you are a Ja。I've made here a Java file， which is called Sjs。

 you can call heres whatever you want dojs， and I'm also going to ask you to open the terminal down here。

AndIf you don't have a laptop， you can follow along with your mind。

You can just run this in your head and it should be hard。Thank you。对。我我讲。

Anyone just done leave your hand。嗯， thanks。Is anyone just not doing if you don't feel like it those your hand？

Oh。Oh yeah， so good point， so make a new file called something Dos。

I called my startup Js and then open the terminal。然。I think everyone is done。

So now what I'm going to ask to do is just typeping some Joshsa code in here so I put console log 42 of course you've done this already and you browse away and log 42 you might have even done this already with note probably we have。

And I'm going to ask you to open the terminal and type in node so save the file， make sure it's safe。

 it'll tell you if it's not saved up here。And then type in node and then just type in the name of that file。

And it should do exactly retail， so I did print 42， you can do print whatever you want L printed。

 so cancel print。By think the sponsor that。我富要文。5ive more things。

Change the print image to whatever you want you got some F statements。

 normal document whatever you want it。就是说winwinder is just你 out over there。然后 three这是这样。All right。

 looking good， so that is note well you've JavaScript relatively new compared to the lifetime of JavaScript and it's really useful。



![](img/7d6c21f07be064be8e2b53d1455dcb32_7.png)

I will show you why its for now。So what we're going to do is we're actually going to build one of these servers。

 so we're going to build the server literally is basically what we' just serving your website whenever anyone asks right so let's do that I'm going to put my mic just down in one second and type this except I'm going to type it so it's a little bit less humtimidating so。



![](img/7d6c21f07be064be8e2b53d1455dcb32_9.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_10.png)

Yes。That's how you import things import something something is this is when you're making any variable in polymer function called required with imports。

It's kind of weird way to how it is。I'm going to put two things。Yeah， there you go， I the other one。

I'm going to Express， I'm going to input a course。UAnd if you want that you really should be looking at here。

 if any of you are familiar with the jungle or with wow。

 with that I think basically it's just a package library you can create servers。

And I'll explain to you what a server is in this case。嗯。I a wait and。YeahAny want copy either。

The next what I'm going to do is I'm going to copy this one。So here we're making new express up。

 but we' actually got a few more。You go， so I'm going to make a new express app。Bla。

 this is just where to quote you can sign down line I it and I'll not know this by heart。

 I'm going to keep copying。And'm going copy this。I'm just going to me one second。没有一个。So。

We import Express， we tell Express to this some boiler price stuff。

 I don't know how this works via app。And then we do app。 gett slash the basically app。

 gett is saying whenever anyone makes a request to are service。

What we should do is handle a request and handle a request and handle a request that function I define before。

 which basically describes that response object。It sends back hello， Lo。

You'll see what it does in just a second， it's pretty cool。呃我。I我 need here for。差多。我唔到先生意。诶。Yeah。

 so what a server is。It's just the program learning。Which is listening or connections。

Making connection is no easy， anyone can do it， anyone can try make a connection to your computer。

Thats why we have firewalls to block those connections。

 but we remove firewalls and you start up this filter right here。

Anyone can make a request and whenever anyone does， you will respond hell。That is what a server is。

Respon to connections， connections is like anal thing you can just do that yeah。好。对。Yeah。

 so I did not explain Ti as good catch， I will explain it in a second for now just type it out。

没有还奥特曼。I'm going do one more thing。I'm going to put this one。So。This was weird。

 we're going to have to listen at the random number minus that 2042。诶我个平审。-242。

The reason we need this is because。' people who made this realize there's a possibility that you might want to have multiple servers on one machine。

Multiple things waiting for connection to washing machine so they created ports。This is port 3042。

 so I'm saying hey look， I'm going to listen not just for anything that comes to this machine or anything that comes to this machine on the port 3042 and when it comes I'm going to handle it and I'm going to send back helloo。

行。Ohll， share with slide on。Yes， answer yes， so when you're done with this。

Or while you're doing it do mM so okay yeah， this is a good point so before you make a file you're supposed to do it's matter the order。

 it's okay is you're supposed to do MPM in it。What MPM in it will do is it will create a project for you doesn it yourself you MPM in it and when you do that my name will probably say it already exists it's done so it'll ask you something like this like package name。

 blah， blah， just keep blessing and enter it doesn't matter everything is irrelevant。

And then it'll make it and it'll make a couple of things it might it'll make like this thing patent on based I like this kind of application I'll just make a couple things maybe like maybe not。

But now what you can do is you can run a different commander I said， let's all dompm in it。嗰杯又系你度。嗯。

这是。啊用过已经 check过你。系啊。Is anyone lost or should I scroll up or anything？我行。你说。So。就是想写的。Yeahやす。一。Yeah。

 so this first enter A A default folks。诶已经公司问比。You going to kind of skip it。对。All right。

 I'm going to continue， so after you done MPm minute。

You can do MPM install or just I for short and then there's one thing you need to install you may have noticed yes have install all throw two thingss express and course you can you can do one by one you can do it both at the same time so for the first one express you're going to that like this MPm install。

Yes friends。嗯，在 do that。Is it similar to tape install？I don't keep it here。

 though I already ran it down here minem really like yours will not be that because I already had done。

They still kind of install and when you're done， you sell a course， start like GRS。

a certainly might give an error and it does give an error。Forly， time。

Because this will take five minutes and 10 minutes of about1 at。

And then courses the same the MPM install package， but the MPient package is kind of buggyies like a few other installation images now like you aren'n Y on play alter toia。

嗯。It's not bug in economic status， you can get a lot of practice dependency errors with one package or what you have depends on how like it just takes a while to figure it out。

But that doesn't happen and you should now have express N courses， so I express。

 I don't know if you don't have express just one MPMI course。我知道。你事到。All right。

 raise your hand if everything I've done we've done。Yes是。So。No。

They should run how do you run something so NPM remember is a package manager node is the node JS is。

Execution runtime run does get completely different things NP the fast utility no what actually it does the magic。

So you do node， and then you type in whatever your Joshua file is called。

 minus called started as the when you run it， hopefully it doesn't even an error。

 I going to your mile a little bit。你个资叫你好快啊。So it should say whatever you pointed down here。

 so I did several moving for 2042。Make sure you I think you should just use to down42 if your port is lower than a in my given area right so there's a bunch of stuff so just use the down 42。

 but now I'll come back this in a second here I' not quite here。



![](img/7d6c21f07be064be8e2b53d1455dcb32_12.png)

If you do local hosts。3042。You should get an website。upay says howo world。That's right。

It's local your own machine if someone else wanted to access the server on your machine depending the areas of your machine。

You can find your appears your machine， sadly， your machine will likely block incomingage connections because of your firewall because most machines as they are sold to consumers are not meant to be serverd so they don't enable these kind of connections。

 but if you hypothetically enabled it， you could turn your machine into a server and anyone could make connections for your machine and get the website。

From inside your machine， you can obviously make the website there are holes and this this is probably familiar to like when you're running the react project and that pops up for you。

 it's local whole something kind something same thing you just did there because we just actually get it。



![](img/7d6c21f07be064be8e2b53d1455dcb32_14.png)

This is real HTML， by the way。No。Yeah， you have to restart a file if you change ship。

 like can restart this server。

![](img/7d6c21f07be064be8e2b53d1455dcb32_16.png)

There， so not an H one。

![](img/7d6c21f07be064be8e2b53d1455dcb32_18.png)

ButMy point being that this rest are sand over here。This is the entire。

HtL out so you actually feel that。This I wanted to make it a real server in here you would put your whole channel on that right。

By had links to other things， something like that。The whole thing will be in just this string。

So that's how it looks。This slash going back to the slash。

This is where you are so right now we are in the slash so slash that you can imagine you're in this slash but if you you go just like hello。



![](img/7d6c21f07be064be8e2b53d1455dcb32_20.png)

This won't work anymore It'll be like， I I'll get hello。饿什么。



![](img/7d6c21f07be064be8e2b53d1455dcb32_22.png)

I be like， can Iga hello？It has to like you have to say hello here and then it'll work。



![](img/7d6c21f07be064be8e2b53d1455dcb32_24.png)

So I changed that to hello and this will work because of course the normal one won't work anymore。

 you don't need to copy all that but that's just the point。



![](img/7d6c21f07be064be8e2b53d1455dcb32_26.png)

So。This is the path if you want to handle multiple paths so you want to have different paths in your website。

 you can just have different handlers， you can call this line multiple times and have different handlers。

Any sense， any questions？N事。嗯。One more thing， of course， the course it's not that relevant right now。

Ba， there's a bunch of wait， actually， wait， does this work problem， raise your hand if your website。



![](img/7d6c21f07be064be8e2b53d1455dcb32_28.png)

ok我上系。That actually reference that。

![](img/7d6c21f07be064be8e2b53d1455dcb32_30.png)

嗯。Co， and I'm just going to do one last thing。I'm going to add something interesting。

Just to emphasize the power of servers as not just like the thing that gives you the website。

 I'm going to do something。So I'm going to make my bar here and I'm going to set it to like something。

 I don't know one。And then when I do rest that send， let put this stuff moment。I'm going to be like。

呃。Incremental yeah， nice to hurt。Okay， so all I did is whenever I did rest on send I now send incremental value and I can patentnate the inger and then increment the inger what does this mean every time I handle a request I'm going to an incremental value one and I'm going to increase it the next one I want to request I'm going to be a incremental value two。

So I'm going to give a second to copy that。I I didn't might it change just this way。嗯。

If anyone have any questions or questions going on here， let me know。你般。



![](img/7d6c21f07be064be8e2b53d1455dcb32_32.png)

So this is what it does。

![](img/7d6c21f07be064be8e2b53d1455dcb32_34.png)

そされる。

![](img/7d6c21f07be064be8e2b53d1455dcb32_36.png)

Wun it again。Incremental volume want all right makes sense so it wouldn't want to begin with I made a connection so it should have implemented it so now when we load it again it's two and next time three and if I close this and I open it again it keeps it like it no like it remembers。

Inviuably， he doesn't get a loss when I closed your website because the server is always running and never stop run here in the government。



![](img/7d6c21f07be064be8e2b53d1455dcb32_38.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_39.png)

The client can go away and I can come back30 years later。

 the server has been running the whole time waiting for another connection with incremental value state S7 ready to give it when the client comes back that is the key difference between the server and the client server is running so I can group those things。



![](img/7d6c21f07be064be8e2b53d1455dcb32_41.png)

Now， just to drive this point home。

![](img/7d6c21f07be064be8e2b53d1455dcb32_43.png)

This right now we have a set out， looks like a server was supposed to a or center a question whenever you want website that the industry that will get。

 it compromise value。嗯。ButIt's like a server like you put in here and you got Chrome make because it's really going on here is you're putting this address here and Chrome is making that request for you。



![](img/7d6c21f07be064be8e2b53d1455dcb32_45.png)

We can make this request ourselves。And this part is going to be welcome。

 but if you have not probably have semester。Oh， we still have much time。So。

I'm going to do something relatively quick you can totally do want I a new product you don't have to I a new product drive the point the client is we will accept any server。

You can just make this HTML file wherever you want next to the HS file。And just go ahead and open it。

So I'm just going to put a 42 in here， I'm not going to put anything as HTML mouth file。



![](img/7d6c21f07be064be8e2b53d1455dcb32_47.png)

I want to open it。

![](img/7d6c21f07be064be8e2b53d1455dcb32_49.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_50.png)

系有。And so just go ahead and make something that HTML。

 I made a new HTML and I put a 42 in it and I opened it and it's here。



![](img/7d6c21f07be064be8e2b53d1455dcb32_52.png)

喂 where your hand那 done that。One person is done。One person has done it。Congratulationsgratulations。喂。

😊，これ？Yeah。嗯。All right， I'm going this quickly I I repair。嗯。

So anyways what is your point here so you have a button or notice I didn't add any boil that you because actually nothing that we thought you actually matters you can take know all of it and just start putting pretty neat so you have the button over here you have on click get stuff and you have a guess that theres a normal button that was run function doesn't yet exist when I click it and H1 with an ID and now I'm going to add all this script stuff。

And so what is this doing get stuff we define find it down here。

 so what it's going to do is whenever I click this button it's going to run this bullet what I so I on copy which makes a request to if you know it the same address we're putting in our full address bar and then it's going to do some stuff and it's going to do handle on stuff which up here that's going to run when your request comes stack with stuff stuff is going to do whatever。

Server response， whatever the server dis address and this port response。

 obviously my computer port 3042 and we have have a server running listening on that port。

Amlig and stuff is's going to get that stuff and it's connected to do with my H1 di and equal stuff。

hopefullype what that means but essentially what's going to do is going to grab this H1 and it's going to change what's inside of it to whatever they saw the server respond to。

So it's try。welcomelcome back for。

![](img/7d6c21f07be064be8e2b53d1455dcb32_54.png)

So this will so you click Hescar。And it makes a request to the server。

 which is somewhere else notice this is not the server like the server which is ping it right now。

 it just it justt turns its incremental value， this is not the server。

 this is a different file which when I click getSt makes a request the server。

 get whatever response and puts it in an H1 tag so it's big completely different file。

 in fact it didn't even need to display but we chose to display。😡。

So with schools every time I go test stuff。up and if I close this tab and I open it again。

 I clip got tough， get stuff， it remembers the value。ok so。

The point being that in order to remember anything for a user， you need a server。

 when Facebook remembers QR is because they have a server running all the time with your information stores that whenever you ping them。

 they can say not implemented value 21 what your name there。不两 sense。That what's going on。

They do it by very similar mechanisms， we just did it in't except they do more stuff。



![](img/7d6c21f07be064be8e2b53d1455dcb32_56.png)

So that's the idea。Ftch server。Put it。In file。Yeah， yes。

Leave this here for a second in case anyone wants to try all you need to do to make this HTML followwork is open it。

 however you want to open it at this double click in my Explorer。嗯。Yeah。你你个。这样怎么他负责那个。哦。嗯。你叫我。这不高不高。

Oh， this part over here， I'll just copy this off the internet。

Part of the code is required to fetch things。Specifically the point is like what's really going on here is you're making the request and then result is not action text it's like it's the result love what does that mean that means result doesn't come back all at once it's coming back over time from the server so what we're seeing is hey look give me that result and just。

Wait until the entire text has arrived and return back instead because we don't really don't we don't really care about speed that much。

 we don't want to get each of the individual characters comes in。

 we're just going to wait until it both thing comes in that's what we're saying then。

and then when we're done with that that's why there's two dot ends so the first do then is like all right every time everyone comes in just。

Cumulate into pest and then。Put on the screen。一一个一。然后呢。哦，行。呃，照片。好，好。嗯嗯嗯。

It's a very good question so when HTMLL was was designed 50 years ago they hadn't thought that far yet。

 so what they did is they just made every element with an ID automatically defined in JavaScript as a variable with its ID。

Canorran them， can necessarily territory， you can think about as being something like this。

Like that that's what's going on behind the scene right for every alone ID it's creating a variable off that ID so you have to be careful sometimes you'll think a variable is not defined and then it is because some random thing in your HTML a ID go to that。

So I got to be good hotels because there's a lot of weird things behind these scenes。

 but this one's pretty useful because it allows me to reach lessco which intimidating。yes。But yeah。

 you can put get a。不道。我咩。Yeah。We all right， what you get？没有。P off。

 so you're saying something like this， right？我想。那个。Yeah然。So it remains a turn up。

 so this is think about it business I。So in a short path。

What this is a function that will take pain and lot of function with pass interest。

 but this function of insect pass interest so we're just passing function without following it into then by me combination estimation。

Then。When it gets solve and will' get called rest just like our function of getting forward folks。

 but the point is you can to think about like that， this makes motion sense to you。Yeah。

 these two questions to with pretty familiar with the arrow functions。Wch why kind of。喂喂。

Any final or any questions？就只都清门使用。Ftch question so fetch comes with Josh。

Essentially what it does is it makes a request to a server and a port anywhere in the world。

 we' saying make a request to local host， which is me my computer for 2042。

 usually this will error because nothing is running on your computer。

 listening for requests on port 2042 but probably politically for us。

 we have this running here which we ran and it's still running I can stop it it's still running and it's listening on port the 42 on my computer I run on my computer。

If you typed Facebook's address into here。Then you could get all of Facebook source feedback。

I will try it。

![](img/7d6c21f07be064be8e2b53d1455dcb32_58.png)

呵。Yeah， okay， so there's this like a security thing， which doesn't let you do that。



![](img/7d6c21f07be064be8e2b53d1455dcb32_60.png)

Sair enough。Let me check my own website， I think I put that anything that I did。Alright。

 let me see what looks I wouldn't have this。嗯。It is bigger。因为。And we need so yeah， this is this is。

 by the way right here it's just course CORS， this is why we are over here。

We had to have this first thing and this is basically saying， hey， look。

I'm making a web server and I want anyone to be able to make requests to me。

That's what we did that's why our website works and Facebook doesn't because Facebook doesn't have this line。

We're just smart because I mean。

![](img/7d6c21f07be064be8e2b53d1455dcb32_62.png)

A there where anyone in the world can be us through Facebook， no， unfortunately， we cannot or Google。

闭开华。

![](img/7d6c21f07be064be8e2b53d1455dcb32_64.png)

你死咩。

![](img/7d6c21f07be064be8e2b53d1455dcb32_66.png)

Yeah， what。Yeah。我不。

![](img/7d6c21f07be064be8e2b53d1455dcb32_68.png)

系那。

![](img/7d6c21f07be064be8e2b53d1455dcb32_70.png)

So I honestly doubt it because feel like all these companies configured。Oh。H， hello。我出边水。



![](img/7d6c21f07be064be8e2b53d1455dcb32_72.png)

Theres问。But I just not working。诶。Yes， and here it is。

 it we go So you would first be go through just let me log it。There is so there's all our code。

 it doesn't show up because it literally put it in the screen。This renders to nothing。

Like this is literally like if I just show you， it's here。See it's all here。

 this is all web dev website put it all inside the H1 there's nothing here because of how web dev renders and works。

 it realize it's not in the right place， it just wasn't render itself。Unfortunately。But the three。嗯。

I call is my age one， he's no longer in age one， it's not text area。



![](img/7d6c21f07be064be8e2b53d1455dcb32_74.png)

Okay。

![](img/7d6c21f07be064be8e2b53d1455dcb32_76.png)

No，对。

![](img/7d6c21f07be064be8e2b53d1455dcb32_78.png)

There it is， so now we put all the web apps for store。On this thing。Pretty cool。



![](img/7d6c21f07be064be8e2b53d1455dcb32_80.png)

Of course。That's just because of a web app here， web dev is not an API it's not something you're supposed to make a request from programmatically you're supposed to put it in your browser。

 so it looks like jbberish from here ours。

![](img/7d6c21f07be064be8e2b53d1455dcb32_82.png)

Hows you are supposed to make a request we give sensibleens data back。Oh， because about ACPS。那个。

Ptty cool， so our website like web depth except's only access our computer and also running on port 3042。

 web dev is running on anywhere is no port because we didn't add your port but it's port A by default。



![](img/7d6c21f07be064be8e2b53d1455dcb32_84.png)

The来。Any other questions？Yes。嗯，对原。开嗯。是。Yeah， okay， good point so for you that are thinking about this from the promise perspective the only perspective so financial returns a promise。

Wwhich we then say， all right， when that's resolved on this function and what this function is limits it taking to result from this promise fetch and it's running a text function on it。

 what that tells the result wrong if wait until the whole thinking back and only then the whole thing comes back。

 but it immediately returns to promise。And because of the fact that this immediately returns a promise。

 this immediately returns a promise so we can do ban on that too。

 because there's a promise change and then。This rest is longer a it's no longer an object is straight up just a string。

 so we can't do any more in training here， we just pass it out to our function。Yeah。

 it will make more sense if you do awake with it will。Yeah， no this sounds。嗯Yeah。

So that's just how that is built we have no choice。

 they they' built through the promises in mind you can't really like the only。

I guess just through two ways asking discussion， first point is there has some promises here because requests take time。

 like you send a request Facebook。

![](img/7d6c21f07be064be8e2b53d1455dcb32_86.png)

As you may have noticed this on loading something in fact Facebook's pretty problem slow side so it takes a while that takes a while right so you need to use promises you couldn't just get the value from fetch and then keep running over because it just has a no idea so the promises are built such that would be like one Facebook eventually in referring。



![](img/7d6c21f07be064be8e2b53d1455dcb32_88.png)

An alternative to promises for that use is callbacks。

 and callbacks will require you to pass function type another parameter。

 not a thing that's not how veterans built。嗯。Yeah， that's about it。嗯拜啦喂。



![](img/7d6c21f07be064be8e2b53d1455dcb32_90.png)

All right，我 class this machine coming。And。I'll see you guys never remember heard introduction。

But see you guys all right wait hold on we'll check on。Check off， Steve， please， I have yet to check。

 check off。刘先好的。Sfer， take up。我哋精。Butect two， if you have finished by two， please take。Or flag one。

 wait okay， just let me check the website。

![](img/7d6c21f07be064be8e2b53d1455dcb32_92.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_93.png)

嗯。嗯一不行。嗯。为什么唔负得啊？话俾上东。我钟。It。All right， cool， so I know some people have already checked this off。

 I think， so even already is this what we're checking out now？ so if you check this off。

 feel free to leave and I'll check as we before in my discussion section office hours。

You haven't checked it off， you'll could just stay and check it off now。

 is it the way I do right now as this is the last chance now so we want to check it off stay。哎，人经收到了。

对。They扣。

![](img/7d6c21f07be064be8e2b53d1455dcb32_95.png)

No this part。😀Oh呵呵。😊。

![](img/7d6c21f07be064be8e2b53d1455dcb32_97.png)

嗯。我我 shall I shut a word啊。有的。我啊。Okay。42 is what。我什么是图。So little at four， just FOUR。All right。

 thank you for coming。诶，你系好啊。No。You can come to any officers't to any officers any time。对。



![](img/7d6c21f07be064be8e2b53d1455dcb32_99.png)
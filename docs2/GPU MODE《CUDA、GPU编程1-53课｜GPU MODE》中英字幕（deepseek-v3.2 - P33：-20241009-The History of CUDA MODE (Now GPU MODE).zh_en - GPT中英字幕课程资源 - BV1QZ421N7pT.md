# GPU MODE《CUDA、GPU编程1-53课｜GPU MODE》中英字幕（deepseek-v3.2 - P33：-20241009-The History of CUDA MODE (Now GPU MODE).zh_en - GPT中英字幕课程资源 - BV1QZ421N7pT

There are a lot of incredibly talented people here today， Il。

 And I think one of the most special things about these events is just getting to know the people around you and spending time building together。

 And so when a group like this is all in person。 I think super super magical things can happen。

 So again， thank you， everybody for showing up early， I consider it early on a Saturday。

 And we're super excited to have you here。 And with that， I'm going call it my friends。

 Mark and Andreas， who are gonna to share a bit more about the Kuta mode community。😊，Hey， everyone。

Welcome to the first Kuda mode in real life hackathon。👏Be in San Francisco。

 it's like an absolute honor for me to be here。 Incredible。

 It's like feet like 100 people with all the 10 X engineers here。😊，诶。Yeah。

 for those who don't know me or see me for the first time， I'm Andreas。

 basically a co-founder together with Mark of the Kudamo community。

I am super excited to be here with all of you， the best hackers， the best kuda hackers on the planet。

 And it will be like an awesome day today。 We have， we have fantastic speakers。

 We have wonderful location here from Excel， and。😊，Yeah， we have an abundance of compute。

 So you really， please， please stay after the keynotote。

 get your hands on the on the keyboards and and hackck。😊，So let's meet new friends here。

 Let's learn together。 Let's build together。 And most importantly， let's have fun。

 and let's make the GPus go yeah。😊，So Mark。You start the show now with our open talk and the Kuda Mo backtory。

 So ladies and gentlemen， here is my fantastic buddy and Mr。 Kuda Mo， Mark Serraine。😊，All right。

Oh my God。 Okay， there's a lot of people here。 Welcome to Kunummo I R。 Thank you for coming。

 everyone。😊，O， I think this room has the highest like flops density I've ever seen could be higher than GTC per capita。

😊，So really， our goal with this community is to be a place where people can learn and create like their own open source performance projects。

 And we've had like an abundance of those like created。

 So even though we're now in this like beautiful Excel office。

 we actually had like very humble beginnings initially。

 So Kudum mode started in Europe Europe's in 02023。

 I just like finished another community project called the Europes L M efficiency competition where the goal was to fine tune a single alum on a single GPU in a single day。

😊，And 90% of those submissions used Q Laurara。And so it was very natural for us to invite like Tim Mers as a speaker。

 And Tim had just gave like his very dense technical talk as part of like his like job interview process。

 And so he gave us a non-technical talk about how he writes his kuda kernels。

 And the way he describes it is he goes into kuda mode where what kuta mode means he turns off the light。

 like no internet like dark room。 does the blue light from his screen。

 And he apparently wrote the Kra kernels in a single night。😊，So。

 and this turned out to be kind of like a battle cry。 Like， it became a meme on the Internet a bit。

 like thanks to like typed female and Jeremy Howard。But essentially， like。

 I think larger companies like where a lot of y'all work have a tendency of turning our most talented engineers into like Google Doc engineers with Google Docs that no one reads。

 And you all know who you are。 I see some of them right here。😊，So。So I remember like， at the time。

 feeling a bit bitterweet at the competition because it was a packed room， and it was very popular。

 but it was a competition。 Like people didn't really come together to create something like greater than them。

😊，And so I was watching this like talk very randomly， like feeling kind of like moy at Europes。

 And it was like about the open assistant data set。

And it was like this community project that created like an open chat data set for alums that became insanely popular。

 Im like， wow， like， if only we could do something similar。I looked up the first author。

 and it turns out it was like Andreas right here。You know， meeting And was interesting。

 like because it was sort of like， you know， I met like my other half in some sort like someone。

 you know， like， who like really， really like deeply understood like how communities like， worked。

And I also had like recognize him because he was also one of the original O G Ptorch authors。

 So this is like someone who's been like an open source like for like， you know。

 like most of my career。So I DMmed them on Twitter， and we got to talking about open assistant。

 And like very quickly， we realized， like， hey， we both needed to get better at Kuta and Triton because we had peers who were very good at it。

 and we didn't feel like we were like all that good。😊，Separately， you know。

 like one of my hobbies is hoarding books I'll never read。

 And one of the books I had gotten was like an orange book called programming massively parallel processorcessors。

 So I was like going on Christmas break。 and I took the book with me because the one of the main authors is went to the same undergrad as me。

 which like my wife pointed out to me。😊，And I'm like happily reading this book over Christmas break。

 And I get a message from Andreas on Christmas Eve。 It's like， hey。

 like when are we starting like this reading group， And I'm like， its， you know。

 I was like having Turkey， I was like very sleepy on wine already。 But yeah。

 So the server started like very quickly after like on December 27。

 And it was like meant to be this like cute small server。 That's like invite only。 But， you know。

 that was like not realistic。 And after about like two hours， I had a few hundred people deming me。

 And that that was kind of like the birth of the server。😊。

So our lectures like really always like aim to be like practical。

 like valuing sort of like profiling over theory。 You know， I can seede that I'm very gr brained。

 Like I， I don't understand things very quickly。 And this is also true for the majority of people on the server。

 We， we understand things like via profiling。And this is also why the server has always been culturally opposed to offloading how to do performance to other people that are smarter than us。

 Like basically， we love reinventing the wheels。 We love getting 80% of say of soda performance because we really like to understand how to build wheels。

 So at the time， like， you know， we still had some people explain theory。 Like we had Thomas Vienman。

 who was like another Pytor O G who gave us like sort of like a solid like foundation to Ka programming that we could like lean on。

😊，And we also like managed to attract like one of the best like educators of our time。

 like Jeremy Howard， to give a lecture。And his sort of like controversial take was， hey。

 don't write Kuta， like write like Pythor or Python code and then ask like chat GPT to translate it for you。

 You get like a bunch of code。 You run it through N T U and you keep going。 And initially。

 this sounded like a meme。 But it worked。 And this is how I learned Kuta as well。 And you know。

 it sort of like， you know， took me took me ways。 So initially， like I said。

 we were really a reading group for the programming massively parallel processors book。

 But it wasn't a very good reading group because we sort of gave up on the book after the scan algorithm。

😊，And so， if like， so We May， who's coming here later would， you know。

 probably fail me if I was one of his students。 But， you know， it's okay。Initially， like， right。

 like people were just like learning。 But eventually， Andreas was the first person a pioneer。

 the concept of a working group， which is people coming together to build something hard。

 And at the time， the first working group was like a working group on rig intention。

 So to do like large like context like inference。😊，But like since then。

 we've had like tons and tons of working groups， like many of these people are here today arranging Fac Torceo。

 where it's like Supriya is going be talking about the Trident Prs by Sasha Rush and Karen Zhu。

 H Q Q bysm Bury， whos like here to talk about quantization。

 the Lger team by like by Byron Su Al and Th the Thunder compiler by Thomas。And， of course， like。

 basically， our most popular working group and the most active one that seems to be going from 7 AM till midnight pretty much every day is the L LMC group by like Carpathy and sort of the power Rers team that he assembled between Alexa Aron and Eric。

 Like these guys are nuts。 and they're here。😊，So， you know， you can like， learn from them。So really。

 like Kamo I R L is trying to bring the best elements of the server I R L。

 So we have two sets of talks like in the morning and the evening because we're here to learn。

 But like， hopefully， you'll spend like most of this day like actually hacking。😊。

And it's kind of hard to finish a systems project in a few hours。 That's why like。

 there is no constraint that your projects need to be complete As long as they're sort of like interesting and compelling and they help you kickstart a new performance project。

 like， that's fine。 And you can still be eligible to win。

So I didn't see anyone roll in with their gaming GPUs。

 So it sounds like there's not much like local alum crowd here。So just for today， it's okay。

 You know， you can be GPU rich and you're gonna have like 300 K。

 like worth of like compute credits that you can use。

 They'll be available for like months after today。 But you should， you know。

 see if you can use it all today。呃。Why not？ We also have like some fairly large clusters。

 like sponsored by Lamb and Oracle。 I'll talk about those in a second。 So， yeah， I mean， this year。

 like， honestly， I， I spent like the majority of my free time and work time like lurking and like talking to people on the server。

 It really means a lot to Andreas and I that you're all here to share this moment with us。😊。

And frankly， one of the things that brings me the most joy is when I get a very jaded senior engineer。

 like look at me， like， I'm done with these like fucking meetings。 like。

 I sneak to go into kuda mode。😊，So， hopefully， you know， you do exactly this today。All right。

 that was a long speech， but who's ready for speakers。没有。



![](img/003f7f525b578714c304c1ed47401ab0_1.png)
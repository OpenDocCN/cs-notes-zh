# 【从零开始学习 ARM 汇编语言II Udemy】 p11 p10 03.5. Coding  Converting Keil uVision Assembly to CubeIDE GCC Assembler Proj -BV1RJU6YwEM8_p11-

Hello， welcome back。Yes， you may be wondering why the window looks different。 Okay， so this is。

A project built in K MK MDK5。Ku visionion 5。 and this follows the arm。

 the the directive format for the arm asemmbler。 You would see that the arm。

 the symbolic names are assigned differently， and the directives we have here are different as well。

 And over here， the main， we use underscore underscore main。 We don't use simply made。

 and we know why that is is because when we go to the reset handler。If we come over here。😔。

And with search reset handler。 I'll just give a quick overview。 I'm not here to talk about M K。

 I cannot help it。 I have to explain every single thing。 control F or search for reset handler。Okay。

 and then I'll hit。 okay。 So there's the reset handler。 you hit enter twice。 It will bring you here。

 you see。Its loads underscore underscore main。 So the starting point is underscore underscore main。

 That is why in columnm decay， when we export。We start which underscore this called mean okay in SDM 32 cube I D E。

The application starting point is simply mean without underscore underscore。Okay。

 so what we're going to do in this project is just copy everything。

And the column decay and paste it into our SDTM 32。

Cube Ide E project and start changing it live into the cube Ide E format so that now。

 when you have a project created in Km decay， you can do the change yourself。

 and it's as safe you've got。Two items for the price of one， you know， so let's go ahead and do that。

 I'm going to create a new project。How manys。I'll come over here， Paul。You。A ST The2 project。

And it's going to load up the arm。The target selector。



![](img/ee345a13a9fae01ad3b77181ccec903a_1.png)

It's loaded in。

![](img/ee345a13a9fae01ad3b77181ccec903a_3.png)

Okay， I'm going to set my microcontroller， I'm going to search it SDM 32 F411。And I'll get it。😔。

I'll click next。To grab it。Next over here。And I'll give the project a name。GPIO。Assembly。A call this。

MDK versus GCC。Calim decay。😔，Vus G C。 Okay， there's a descriptive name。

 You can name it whatever you want。 I should point that out。

 and then I'll see next and then finish and。I've actually see， remember my decision。

 Don't ask me this again so click that， okay。So it would open in a number of seconds。Right。

 it's done opening， we close this。And this is from the previous project who close this。

 Do you want to save changes， I think yes， And so thiss the previous project， this the new one。

Carl Liki versus GCC。And then in the previous one， we said we were going to delete everything in this folder and see what we get so we can do that in this project。

 Well delete everything here because we don't need these files。I'm going to。Delete them。

 Let's see whether I can use shift to select all of them。

And then I'm simply going to delete everything from the source folder。 I'm in core source。

 and then I'm deleting everything because we write an assembly code。Right， the only thing we need is。

 is over here is this dots S file from the startup folder。 So now our core source folder is empty。

 I'm going to right click。N file， and then I'll call this main dot S。Main。Do。S， like this。 finish。

Okay。So I'm going to go to our Kau vision and then control A and then control C to copy。

 I've copied everything。

![](img/ee345a13a9fae01ad3b77181ccec903a_5.png)

![](img/ee345a13a9fae01ad3b77181ccec903a_6.png)

O paste over here。 and this is what we have。Okay。Okay， there's a lot of work here。😔，So this project。

 this project， I've not spoken about this project。 This project is input and output， this project。

Is is just like the one we did。Turning the LED on， except that this one allows you to press the push button。

 And when you press the push button， you get to turn on the LED and turn it off。

 So we're gonna start off。

![](img/ee345a13a9fae01ad3b77181ccec903a_8.png)

I'll comment everything out。

![](img/ee345a13a9fae01ad3b77181ccec903a_10.png)

Ill start over here。😔，And then。Sorry bother。Concrl V to paste。😔，And then I'll come over here。😔。

Or C a， there should be a way to command the block right click。



![](img/ee345a13a9fae01ad3b77181ccec903a_12.png)

And then。1。😔，I'll come to edit to see if I can find comment block over here。



![](img/ee345a13a9fae01ad3b77181ccec903a_14.png)

![](img/ee345a13a9fae01ad3b77181ccec903a_15.png)

So there's an option here。And the source， that should be toggle comment， but it's deactivated。

 I don't know whether is's because it cannot identify this for assembly。 In， okay。

 we're going to comment them one by one。 So when we write the Gcc version of a particular line。

 then we comment it out。 So we're gonna take this this first one， ourcc base。



![](img/ee345a13a9fae01ad3b77181ccec903a_17.png)

Could you try to change this into the GCC format？By yourself and let。Okay， so to change this。

 we know what to do。I'm going to copy the same name here。And then we said we use dot EQ U here。

 The format is dot EQ U。 and then this is the name， and then comma。

This is the value we want to give to this name。Okay。Right， so this becomes the new value。

So then this also， we know what to do。Do EQU。And then we fetch this name。And then comma。

 is the value we want to give it。Okay， this， we know what to do， I'll comment it out。And then we see。

Dot E Q U。This is the name。Commer， doess the value we w to give it。Okay， so。

I'm gonna pause the video and complete the rest cause this is repetitive and you can do it。 You know。

 you can try to do it yourself and compare to compare it with the outcome I get。So right。

 I've changed the format of all the symbolic names。Yeah， it took me about three to four minutes。😔。

Okay， so this is it。 We have all of them。 I've kept the original。Kawu Viion code in comment form。

 And when I attach the project to the to the video lesson。

 I'm going to attach the original ku a Ku Viion project as well so that。

If you have car your vision installed， you can try both。So it's all been commented out。Right。

And then we use the format next thing we have to do is our directive。 So over here。

 there are two extra directives we have to include the dot CPU directive。

I'll come to the top of the file here do CPUp。And then I'll give the name of our CPU the cortex M4。

And then the syntax。We're using syntax， we're using the unified。Okay， so once that is done。

We come down here。And this is where we continue over here。 The directive here。

 All of this has to change。 This is the call you vision directive。

We can indicate thumb if we want to indicate that we're using thumb。This。We simply do dot thumb。

And we don't have to indicate an entry point here。 The word export becomes。Global， without。

An a dot globalbo in this area here。Is what we would call section dot section。Dot section like this。

And then the section is taught text to indicators for。Is for。Is for good。 and this thumb。

It's not even composory， so we can take it out。So after we've done this， everything looks good。

And then there is one last directive over here。We can align if we want， but we will skip that。

 and the end directive becomes thought the end like this。Okay， so after we've done this。

 let's build and see what errors we have or click over here to build。It's builted in。

We have 12 arrows。O， so the reason we would have the arrows。Is even I forgot。 So， O。

 this man has to change。 Remember， we pointed out that the reset handler looks for main。

 and the main doesn't include underscore。 So main has to be written like this。

A man has to be written like this。 And another difference is that in K you vision。

 when we write labels。We don't。Let's see。 Should I。Wait。

 the reason I'm holding back is I just deleted the stuff。

 I said I was going to keep it without deleting it。Hm。Okay。

 I'm going to controlt Z and just not delete and keep。 just bear with me。

 I think this will make your revision easier。So。We said this。Comment this out。 This。

 we don't need us well。 And this part thus says。This path says export， This becomes。Dotg。😔，ど。

Global without an A do global。 and the name should be main。Ca the reset handler looks for main。

 And this Pada says area， we said。We call this dot section in our asmbler over here dot section。

 and then the section this dot text remains the same。So we see a dotted text over here。Okay。

So this is what we end up with from this site。Or just align the old guys together。 O。

 this is what he came with。This is our new stuff。Okay， so because this is the global。

 our label here has to be made。 And one other thing over here， over here in in the G C asmbler。

 When you write a label， you've got to put a call on there。 So everywhere we see a label。

 we've got to put a colon on。I'll put a code on here。And then a call on here。😔。

And then a call on here。😔，Ca on here。😔，And then this a， we said， we can keep it out。

 or we can use that a。I think there's a directive dot a line。

And this end is Dot's end in our Gcc like this。And one last thing over here。In our assembler。We use。

Slulash ssh for comment。 We don't use semicolonons in carl asmbler。

 We use semicolonons to indicate comment over here。 we don't。So the comments。

 I don't need to keep them the same。 So I'll just fix the comment without preserving its initial。

Format。Right， do we have any more comment。We do not。 Okay， we have some over here。

Do we have any more， We do not。 Do we， We do not。 Okay， so now let's be able and see what we've got。

 I'll click over here。It's building。 We've got two arrows。 Okay， sounds safe。Let she。Wal from Hu。

Of00 B， S S。 O， it's in this function。 Okay， this will have to do with。Our starting point。

 So let's go and look at our starting point。It's global mainine。😔，And then section is。Dot text。

And then we have our main over here。😔，And then we have our branch over here。😔，And then what do we？😔。

Not have。 We have everything we need。To end。 then let's see。Do CPUU。😔，Cortex M 4 should be fine。Okay。

 okay。I know what is happening。 So you remember the E files we deleted when we started。

 our main had a lot of filess。 One of such filess or one of those files is the arm is the system in it file。

 and this subrout loops to that。 There's a system in it。

 So I'm just going copy that from a previous project。If we go to this over here。

If we go and find our loop fills you BSS。It should be down here。 This is resett Hanla。

 It brings us here， and then it jumps over here， and then it goes to loop  fill 0 B， S S。

 Lo fill 0 B， S S requires system in it system in it existed in one of the files we deleted。

 So I'm going go to our old GI assembly project。 Go to call。

And then copy the arm the system in its there。I'm going to copy these three files system SDM32 xx。

t C。I think its counterpart is the arm。I's this one here。

I think it would have been better if the guys at S T put these files in the set so that we wouldn't need to find it in our application source files。

 Anyway， I'm going to start off by copying these three。 I think these three。Should be required。

 So I'll right click copy， and then I'll come to our new project。 This is our new project。

 GI Asly call M K versus Gcc in our source folder。 or'll right click， and then I'll paste。

Only the exist here， let's go and see， click over here。Okay， the error disappeared。Now。

 we've got no warning。I'm sure we just need one of the three， but we have the three。

 we can keep the three if you are more curious， you can go deletelet in the attitude。

 deletelet in2 at random and see who has the system in it。Right， but we're moving on。Okay。

 so now that we've downloaded。On now that we've built， let's go to the debugger or click over here。

Select this and then O。And then I'll say， okay， from here。Okay。It's done。So we can run our code。

Said Dun。Okay case， they're working， O。So click here to run。And。😔，It's running。

But when I press my board， nothing happens。No， I was pressing the wrong key when I press the。

 I was pressing the the black button。 Sorry， bother， when I press。

 as you can see when my hand is on it， the LED is on， when I lift my honey goes off。

 when my hand is on it， it's on。 when I lift my honey goes off。

So this is how we can convert Ku Vision assembly project to our cube IDdeE assembly project。

 and this same project should work in any form of arm Gcc assembler project。

 So if you have eclipse arm Gcc assembler， they should be able to work。 They use the same syntax。

 So there are the rest。 if you have any questions or just live in the questions and answers area。

 If you're finding the course useful， take some time off to leave a review and have a beautiful day。

 I shall see you later。

![](img/ee345a13a9fae01ad3b77181ccec903a_19.png)
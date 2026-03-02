# 哈佛大学《CS50 Scratch 编程｜CS50’s Introduction to Programming with Scratch 2024》中英字幕 - P1：Sprites - Lecture 1 - CS50s Introduction to Programming with Scratch.zh_en - GPT中英字幕课程资源 - BV1nx4y1s77C

![](img/eb49455774b4527ba20ff4463b78023d_0.png)

Welcome everyone to an introduction to programming with Scch。 My name is Brian Yu。

 And in this course， we're going to be exploring Sc。

 which is a visual blockbased programming language developed by the team over at Mit's media lab。

 using scratch by putting together little scratch puzzle pieces that we'll see shortly。

 you'll be able to build visual stories and animations and games and other programs that you'll be able to share with others。

 And along the way， as we're exploring scratch， you'll be introduced to the fundamentals of programming。

 We'll take a look at concepts like functions and loops and conditions and variables and other types of ideas that you'll see in programming。

 And even though the scratch programming language looks a little bit different。

 it uses blocks instead of the more traditional textbased programming that you might see in other programming languages later。

 really scratch is based on the same fundamental ideas and it's going to use the same principles of computational thinking。

 So with that， let's go ahead and take a look at scratch and dive in to our very first scratch project。

😊，So once you go to Scratch's website， when you click on the create button to create a new project。

 you'll end up seeing an interface that looks like this。

 and we'll be exploring this interface during this course。

 But it's broken down into a couple of parts over here on the lefthand side is our block library。

 You're going to build scratch projects ultimately by putting together blocks in some sequence in order to get the project to do something that you would like for it to do。

 and you can assemble those blocks together from the block library。

 bringing them into this middle part of the scratch window。

 which is the block editor where you're going to put these blocks together to decide how it is that your project should work。

 But before we even get to those blocks and how they work and how to put them together。 Today。

 we're going to be mostly focusing on this part of the scratch window。

 This rectangle you see here is what scratch calls the stage。

 and it's inside of the stage that our scratch projects will live and ultimately run。

 And this is when someone runs your scratch project what that person is ultimately going to see。

 We see that right now。😊，In the scratch stage， we just have one character。

 this default scratch cat here。 and each of these characters， Scch calls a sprite。

 a sprite in the world of scratch is just some object。

 It could be a character like an animal or could be some other object that live somewhere on the stage。

 and ultimately， we're going to learn to have the ability to program these sprites to do what we would like for it to do。

 down below。 we see a listing of all of the sprites that are currently in our project。 right now。

 it's just this default cat。 which is called sprite  one。

 And we'll start to see other parts of this interface as well。

 But let's start today by exploring this stage。 and the sprites that live on that stage and how we can manipulate them。

😊，So what we'll see right now is that our default scratchca is currently just in the center of this stage here。

 but I can move it around， and I can move it around just by clicking and holding on the cat and then I can drag it around。

 I can move it to one corner of the screen or I could click and drag and move it to the other corner of the screen for example。

 And what you'll notice as I start to move the scratch cat around on the stage is the down below a couple of values are changing。

 the x value and the y value right now， for example， the x value is 177 and the y value is 42。

 But if I move the scratch cat a little bit move it somewhere else。

 now the x value is negative 156 and the y value is negative 77。

 So sprites in scratch exists on the stage and in particular。

 they exist at a particular location on that stage which is organized into an Xy coordinate grid。

 And so if you imagine that this rectangle here is the stage this looks similar to an Xy coordinate grid。

 you might have seen in a G。ometry class， for example， where we have the x value。

 which just represents how far to the left or to the right is our character on the stage。

 and we have the y value， which represents how far up or down the sprite is on the stage as well。

 The perfect center of the stage is point00。 if x is equal to0， and y is equal to 0。

 then our sprites going to be exactly at the middle of the stage。 But if we increase the x value。

 make it a positive value， it'll move further towards the right part of the stage。

 And if we decrease the x value， make it more negative。

 then the sprite's going to be further to the left side of the stage。 And likewise。

 the same thing goes for y， but in the up and down direction。

 If I have a sprite where y is equal to 0。 it's going to be perfectly level at the middle vertically。

 But if I increase the y value， then our sprite is going to move up along the stage and if I decrease the y value。

 then our sprite is going to move down along that stage as well。

 So we'll see those x and y value come up， not only in this interface here where we see where the sprite is on the stage。

 but also a little bit later。😊，Once we start putting blocks together to program where our sprites are going to be on the stage at any given time。

 so right now if I wanted to take my sprite and move it back to the perfect center of the stage。

 I could take it and drag it to about where I think the center is and I might be pretty close。

 but if I want to be even more precise I can go down to the X field here and change what's right now 10 to0 and I can do the same thing for y changing what's currently negative8 to0 as well。

 and that will perfectly center the cat in the middle of the stage here。😡。

In addition to being able to change the position of the sprite。

 we also have a few other controls that are in this part of the scratch interface over here。

 I have the ability to give my sprite a name right now， my sprite is just called sprite1。

 which is the default name that scratch gives to a sprite that I create。 But I could rename this。

 I could call this the cat， for example， And what you'll notice is that when I rename the sprite call it my cat。

 then down below in this bottom portion of the scratch interface。

 this is where I see all of the sprites in my project right now， there's just one。

 but each one is labeled by its name， which right now is the cat。

 And as we start to get more and more sprites that will be added to our projects。

 it's going to be helpful to keep track of which sprite is which by knowing what the name of any given sprite is。

😡，Underneath the place where I can name any individual sprite。

 I also have a toggle where I can decide whether or not that sprite should be shown on the stage right now。

 we are showing the cat， but I could click this button over here to hide the cat from the stage And if I want to bring it back。

 I can show it again。 so I can show and hide the cat to decide whether for any particular sprite。

 that sprite appears on the stage or not。I also have these other two controls。

 This control here controls the size of the sprite right now， the size is 100。

 meaning it is at 100% size， which is the normal size for any sprite。

 but I can change that if I want the sprite to be half as big I can change the size to be 50 for example。

 and now the sprite is much smaller if I want to make my sprite cat larger。 I would change it to。

 let's say 200 for example， and now the sprite is going to be larger。

 but for now I'll go ahead and keep it at 100。 and over time we'll start to see that we can change the size as well by way of the blocks that will be introduced a little bit later。

😡，And then finally， in these controls， I have a direction control and the direction control controls which way that my cat in this case happens to be facing right now。

 it's at 90， meaning 90 degrees， in other words， the cat is facing to the right。

 but I could rotate the cat， spin it around and watch as I turn this dial。I can rotate。

 spin the cat around and have it face a different direction if I want to。 And when I do。

 you'll notice that this direction value changes into some number of degrees。

 So right now it's pointing at a 39 degree angle。 but I could change that back to 90。

 And when I do that， now the cat is facing to the right as well。

So I have this ability using this editor here to control a lot about this sprite。

 I can change its name。 I can change its position， its size， what direction it's facing。

 whether or not it shows up on the stage or not。 But really， to make our programs more interesting。

 we don't just want to have a cat that lives in this environment。

 I'd like to add some other sprites to my stage as well。

 So let's go ahead now and try and create a new sprite。😊，Down here at the bottom。

 you'll notice that inside of this region of the scratch editor where all of my sprites live right now is' just the cat。

 There's a little plus button。 And this is the createate a new sprite button。

 And I have a couple options for how to do so。 But if I just click on this main circular button that says choose a sprite。

 I'll end up getting a whole list of different kinds of sprites that I can create their animals。

 there are people。 theres different types of sports related sprites or food related sprites。

 and more than that。 And I can look through this。 and try and find whatever I'd like。

 And let's say I want to add an animal， for example。

 Another animal other than the cat to my scratch program。 Well， up here at the top。

 I can filter down what I'm looking for by a particular category。

 Or if I knew exactly what I was looking for， I could search for a sprite as well。

 But let me go to animals for now， just to see the various different kinds of animals that can exist here。

😊，And I think I like the fish。 So we' go ahead and take the fish and add that to my stage。

 And so once I do that， you'll notice a couple of things happen。

 One down below in this region where I'm keeping track of all of the sprites that are a part of my project。

 I now have two。 I have the cat。 and I have the fish。

 and you'll notice that both now appear in the main stage area of my scratch program。

 And I can move them around so that they're not overlapping with each other。

 So I now have one cat and one fish， whichever one is selected highlighted in blue down here at the bottom。

 that's the one I'm currently working with， where I'll currently be able to add code to it or manipulate its position or size or any of the other attributes we've seen that these sprites happen to have。

 So this fish， for example， is currently located at x equals 73 and y equals 70。

 But if I switch to the cat by clicking on the cat down at the bottom。😊，Now I'm selecting the cat。

 and now I see the cat's position and the cat's name and the cat's size and the cat's direction as well。

So using that ability， we can add new characters， we can add new objects to our scratch project。

 And if we wanted multiple of a given character， we can even duplicate a particular sprite。

 So let's imagine that I want two fish。 for example， inside of this environment。

 I'm going to click on the fish。 And then I can either right click， or I can control。

 click on the fish。 And when I do that， a little menu will pop up where I can here say。

 let me duplicate the fish。 Let's get a second fish。

 And you'll notice that it's called fish2 by default。 I could change that if I wanted to。

 but fish2 is okay。😊，And I'll take the two fish and separate them a little bit on the stage just by moving them around。

 And so now I'm starting to construct this scene。 And this is why。

 why you can use scratch to tell stories or create animations or create pieces of art just by deciding what it is that you want to exist on this stage and then add them to the stage as well。

Now， one thing you might notice is that right now， because I duplicated the fish。

 both of the fish look identical。 They're exactly the same。

 They're both pointed in the same direction。 and I could change the direction or change the size of one of the fish to make it a little bit smaller to make it look a little bit different from the other fish。

 If want a variety of different types of fish in my scene。

 But what I'd really like to do is change its entire overall appearance。

 So I have two different fish that exist on the stage instead of just two copies of what looks like the same。

 And so here's where we're going to introduce another concept in scratch， which is that of costumes。

 Every sprite can take on different costumes。 And a costume is just what that sprite happens to look like。

 And so let's explore now how we can change the costume for one of these fish， for example。

 up at the top of the scratch window， you'll notice a couple of tabs。

 The tab that's selected by default is called the code tab。

 And while we haven't added any code to our projects just yet， ultimately。

 as you start to build more complex projects， you'll be using the。😊。

Tab to take blocks of code and drag them into this code editor in order to decide what it is that your scratch sprites are going to do。

😡，But the tab that we're interested now is this second tab， which is called the costumes tab。

 which is going to allow us to see and edit and modify the costumes that belong to any given sprite。

😡，So let's go ahead and take one of our fish。 We'll go ahead and take fish2 and head over to the costumes tab by clicking on the costumes tab。

 which is next to the code tab up at the top of the window。And when I do that。

 you'll see that by default， the fish has four different costumes， F A and F B， F C and fish D。

 right now， fish A is selected， but I could change the costume。

Just by clicking on a different costume。 If I click on fish B， for example。

 now I've got a different costume that's selected。 and now you immediately see in the stage that the fish looks different。

 It's taken on a different costume even though it's the same fish。

 it appears visually to look different because we've changed what costume it has。

 And I can try changing it again。 Here's fish C。 And then I can try looking at fish D as well。

 So you can experiment and take a look at what costumes happen to be built in by default into any given sprite and change them if you'd like to。

 The cat too also has different costumes。 They don't look nearly as different。

 But what you'll notice is that the cat can be in two different costumes that are just in different leg positions。

 So in costume 1， the legs are straight in costume 2， the legs are bent。

 And if you watch this sprite carefully as I switch between the costumes。

 It almost looks like the cat is walking。 which is why we've got those two different costumes to sort of give the appearance of walking if we would like to。

😊，But let's go back to the fish， which has four different costumes that I can choose from each of which looks very different。

 And I'm not limited to just those four。 If I wanted to create additional costumes。

 I have the ability to create additional costumes too。 How could I do that。 Well。

 here in the costume editor down at the bottom underneath where all of these costumes are。

 There is another plus button that looks very much like that button for creating a new sprite that we saw a moment ago。

 But this time， this is the button for creating a new costume。 And here I have a couple of choices。

 I could search inside of Scratch's own library of costumes to find a costume that I might want。😊。

I could also paint a new costume。 So if you're feeling artistic。

 you'd like to create a costume of your own。 We could try painting our own。

 so I could paint my own fish， for example， And here I have a bunch of different tools that I can use to paint the costume。

 So I'll go ahead and use the paintbrush tool that will just let me draw a new costume for my fish。

 and I can choose what color I'd like the costume to be too。

 So I'll go ahead and choose maybe this color。😊，And I can start to draw。Something like。

A fish will draw a fish will give the fish an eye。 So if you are feeling a little more creative。

 a little artistic， you can try and draw a fish for yourself。

 I can use the fill tool if I want to to pick a different color。

 maybe and fill in the fish with a particular color。 So you can be creative about this， too。😊，Now。

 of course， I do think that the fish that scratch provided for me look a little bit nicer than the fish that I was able to draw on my own just now。

 but I can modify the existing costumes too， using this same costume editor if I wanted to fill in part of the fish with different color。

 Maybe I want a little bit of green in this fish。 I could take a green that I happen to like by just adjusting these dials to specify what color I want and still using the fill tool。

 I could fill in parts of the fish with a little bit of green， for example。

 just to make the fish look exactly how I wanted to look。

 So you have a lot of creative freedom in this costume editor。

 You have the ability to create an entirely new costume just by drawing it and painting it yourself or you have the ability to take a costume that already exists and add to it by painting over it or filling it in with different colors if you'd like to。

😊，And you even have the ability if you want to to upload a costume。

 If you have a photo or an image on your computer that you'd like to use as a costume in your scratch program。

 you can upload it there， or you can even take a photo with your computer's camera if it has one in order to add that photo as a costume as well。

In addition to changing what these sprites look like。

 we also have the ability to give these sprites sounds that they can play。 And so up at the top。

 you've noticed that we have a code tab and a costume tab。

 There is also a sounds tab for the sounds that are associated with each of these different sprites。

 And later on， we'll see ways that we can include those sounds as part of our project。 So right now。

 the fish by default in scratch。 has two different sounds that it has。 one is called bubbles。

 and I can play that if I'd like to。And one is called ocean waveve。

So those are the sounds that are built in as just part of the fish。

 and later on as we're building stories with it， maybe at some point we'll want to play those sounds。

 and later in the course， we'll see ways that we can do just that and different sprites have different sounds built in by default。

 The cat， for example， if I click on the cat， has one sound by default， which is just the meow sound。

 which I can play。But if I wanted to， I could add more sounds as by recording something myself。

 if I wanted to record a sound to give to a sprite， and you can also upload a sound。

 if you have a sound file on your computer that you'd like to include maybe some music you want to go along with your project or a sound effect。

 you have the ability to upload those sounds too。But let's go back to the code tab。

 which we'll look at a little bit later。 and now we've got our stage。

 we've got our stage with the cat and two fish。 But right now what's a little bit boring about my project is the background right now。

 I'm just dealing with a plain white background with nothing else on it。

 And I'd like to make that background a little more creative as well。

 And so this background we've been calling the stage。

 the stage is this rectangle where our sprites live and each stage is allowed to have backdrops。

 the backdrop just decides what image appears behind all of the sprites and by default。

 when you create a scratch project for the first time， the backdrop is just going to be solid white。

 but we can change that。😊，Down at the bottom right here we see the stage。

 and I have the ability by clicking on this button in the bottom right to choose a backdrop for my project too。

😡，And so if I click choose a backdrop， you'll see that I have a whole variety of different backdrops that I can choose from in different environments。

 I see I have a wintry scene。 If I want to create a wintry scene， we have some indoor scenes。

 if I want to some outside like city scenes。 And this one looks nice。 It's an underwater scene。

 maybe。 And I'll use that because I've got a bunch of fish on my stage。

 And so maybe it'll make sense to put my fish in an underwater scene， for example。

 So I'll choose that backdrop。 It's called underwater 1 by default。 And let's use that one。

 So I'll click underwater  one。😊，And you'll see immediately， the backdrop now changes。

 and I can now have my two fish that are living inside of this underwater scene。

 And much as was the case with costumes or with sounds。

 if I had my own image or I wanted to draw my own image to use as the backdrop for my scratch project。

 I could certainly do that as well。At this point now， the cat， though。

 is starting to feel a little out of place。 I'm designing an underwater scene。

 I've got two different fish here。 The cat maybe doesn't belong here。

 And so if ever I want to remove a sprite， here's how you could do that。

 I'm going to click on the cat， because that's the one that I'm currently editing。

 And if I don't want the cat， there is a little trash icon that appears next to whichever sprite happens to currently be selected。

 And if I don't want the cat to be there， I can just press that trash icon and that's going to remove the cat。

😡，And so now I have this scene with these two fish that happened to be swimming around in the water。

 and I could change the scene if I wanted to。 maybe I want to take fish to this yellow and green fish and flip it around so that it's facing the other direction so that one fish is swimming to the right and one fish is swimming to the left。

 for example。 So how could I do that Well， next every fish。

 remember we've got a direction control for any given sprite。

 the controls what direction that fish happens to be facing So if I want to take a fish and have it face to the left。

 for example， I could rotate rotate， rotate， have it faced towards the left like negative 88 or negative 90 degrees or so。

 but this isn't quite perfect， because as you're probably noticing the fish is upside down now。

 So normally with this direction control。 when I'm trying to control the direction。

 it's just rotateating whatever the sprite is in whatever direction I tell it to rotate。

 But what that means is that if it starts facing the right and I rotate it 180 degrees。😊。

All the way to face the other direction。 Now， suddenly it's going to be upside down。

 And that's maybe not what I want for it to do。But it turns out scratcht has a fix for this。

 And every sprite can be in a number of different rotation styles。

 What style it's going to use when rotating by default。

 it uses this all around style where it can be facing any direction that we want rotating all around。

 But there's also this second one that's just called left and right。

 And that will just let the sprite face in one of two directions。

 either it's looking to the right or it's looking to the left。

 And so if I change the rotation style to left， right by clicking on this middle button here。

 that's got like one arrow facing the right and one arrow facing the left。 Now。

 when I rotate a little bit， nothing happens because it's only ever going to face to the right or face to the left。

 But if I rotate it all the way around to the other side。 Now。

 I have the sprite that's facing the other direction。😊。

And that's how I can get one sprite that's looking over to the right。

 and there's one sprite that's looking over to the left。And I happened to like this scene。

 if I wanted to see it in full screen， there's a full screen icon in the upper right where if I click on that button。

 I now see my stage or in full screen， I can see exactly what it's going to look like。

 which is quite nice。 And I now have my first scratch project。 I haven't added any code just yet。

 but I've added some sprites， some characters that are part of my scene。

 I've added a different backdrop that I can use to my scene as well。

 And if I wanted to save this because I want to make sure I can keep this and use it a little bit later。

 I have a few options。 one option in the file menu。

 I can save a project to my computer and that will download the project to my computer such that later if I want to open it up again。

 I can click load from your computer and load that file that I've just saved。

 But also if you create a scratch account by clicking on this join Sc button if you don't already have it and then sign in your account。

 you'll have the ability to save projects to scratch's own website。 And once you do that。

 if you'd like to， you could share your project with the world to send it to friends and family and to let other people that are using scratch。

😊。

![](img/eb49455774b4527ba20ff4463b78023d_2.png)

Have an opportunity to see your project and try it out as well。

So now that we have the ability to create these sprites and to put them onto the stage。

 we can create whatever environment we want for the story or for the animation or for the game or for the other program that we might be trying to create in scratch。

 But right now， these sprites aren't really doing anything。 The stage is always staying the same。

 The fish are always the same。 And ultimately what we're going to look at next is about programming。

 how it is that we can write code， And in particular。

 by using these blocks and assembling them together into stacks of blocks that perform various different activities and tasks。

 We're going to be programming these sprites and the backdrop in the stage to do what we want them to do to create all the more interactive stories and games and animations that we can create all through the use of scratch。

 But we'll explore that next time， that's it for an introduction to scratch for today。

 And next time we'll take a look at how we can take that stage and begin programming with it as well。

😊。
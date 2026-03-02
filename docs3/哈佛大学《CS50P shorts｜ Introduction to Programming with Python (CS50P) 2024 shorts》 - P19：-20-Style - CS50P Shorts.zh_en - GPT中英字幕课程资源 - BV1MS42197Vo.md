# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P19：-20-Style - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/680f0bd4ea96d880701695b318563b6a_0.png)

![](img/680f0bd4ea96d880701695b318563b6a_1.png)

![](img/680f0bd4ea96d880701695b318563b6a_2.png)

Alright， this is CS S 50's introduction to programming with Python。 My name is David Main。

 and this is our look at style。 Now， up until now， we've been writing code。

 That's hopefully at least correct。 That is the code does what you intended to do。

 and hopefully it's also well designed。 That is you're using relatively few lines of code to achieve some goal while still ensuring that it's readable。

 you're perhaps using functions that save you the trouble of reinventing wheels， so to speak。

 but it's possible that your code isn't necessarily manifesting the best style as well。

 which is another form of quality that you can ascribe to some code。 Now。

 style or the right type of style to use is rather subjective and it depends typically on the programmer on the company on the course or on the language that you're actually using。

 but within the Python community， it turns out that there's some pretty regimented standards that most all Python programmers adhere to or rather expected to adhere to because this particular language and community has tried to codify some of their preferences。

For how your code should look in the form of something called PEP8 so a PEP or PEP Python enhancement proposal is a set of proposals that the community within the world of Python typically generate to not only propose new ideas but also to codify ultimately certain standards and PEP8 happens to be such a proposal that's standardized or rather tried to standardize what our code should look like that is to say it's quite possible to write code that's not only correct。

 it might even be well designed， but it's just really a mess and it just doesn't look very good。

 it's not very pretty， it's therefore harder to read it's harder for others to read and therefore it's just not as maintainable and anytime you make something harder to read or less maintainable。

 you're just increasing the probability， dareay down the line of introducing bugs so it's a good thing for your code to be properly format it just like in the world of writing emails or essays or books or documents or beyond it tends to be good practice to capitalize certain words at least in English use good。

😡，Punctuation， use paragraph breaks and the like。 So even if you're relatively new to programming。

 at least in English or your own human language odds are you've had quite a bit of practice with writing language in the human world that also just looks good as well what does it mean to look good in the world of programming code well let me propose that if you look at Pep8 itself which is available on the internet address it turns out that it tries to standardize a number of details that would be manifest in your own code once you've written a number of lines and the overarching premise of Pepe and really the notion of style in the python community especially thatqu readability counts and typically languages python among them come with what's generally known as a style not unlikep8 some kind of a document either printed or perhaps internet based that just tries to standardize what everyone's code should look like So a course that you're taking might have its own style guide a company you're working have its own style you down the road as a professional。

Programr might have your own style guide for your own code， but within the Python community。

 they've tried generally to standardize for the most part a lot of these details。

 and ultimately quote unquote2 a style guide is about consistency consistency with this style guide and the context of Python is important consistency within a project is more important and consistency within one module or function is the most important So that is to say these aren't necessarily hard and fast rules。

 but rather guidelines that should guide the design of your own code Now how do you go about designing or how do you go about styling your code well well it boils down to things like this and many more indentation using consistent indentation now in some languages it doesn't strictly have to be there when you indent one line of code under another or it could be one space or two spaces。

 three spaces or four maybe even eight or an actual tab in the world of Python they tried to put an end to this debate and they prescribe that we all just agree to use four spaces consistently tabs。

😡，Sps no tabs， spaces instead。 and indeed typically in something like VS code when you hit tab on your keyboard。

 depending on how the program is configured， it should generally convert even things like tabs to individual spaces like for What about maximum line length your code tends to get less and less readable the longer and longer your lines of code get。

 especially if they start to scroll over the screen So Python2 tries to standardize what the maximum line length is you just shouldn't go past a certain number of characters to the right of your screen blank lines using some number of blank lines。

 for instance between blocks of code， perhaps among commentss also just lends itself to making your code more readable why because it's not just a wall of text。

 a wall of code that you or other programmers have to see by adding in blank lines and white space more generally can make it a little easier to wrap your mind around what's going on and then imports even something like this when you're importing this library or that or this module or package Python 2 prescribes just how and where you should generally put those lines of code that say。

😡，Import or from and Python via Pe8 also prescribes any number of details as well。

 and these aren't details that we necessarily preach along the way。

 but rather practice as we write each of these examples in class。

 and it turns out too that is you see more and more code well you just get accustomed to the certain rules of proposals like these So how do you go about checking if your code is in a conformance with something like Pepe or style guide more generally。

 well， you can certainly read the style guide itself and then look at your own code and compare the two left and right and decide oh。

 I need to fix this and this other thing in my own code But there's also tools being programmers that can help us solve these problems as well and one of the most popular in the world of Python is a program called Pyant。

 which is an example of what's generally known as a Li。

 which is a program that rather statically analyzes that is reads your code top to bottom left or right and tries to figure out if there are potentially mistakes therein or at least inconsistencies with something like a prescribed style guide。

😡，This is something that you can install via the usual ways using something like PP and its documentation is here。

 but it turns out there's other tools out there as well that are perhaps a little less noisy than pilott。

 It turns out if you run pilot on most of the programs you've written thus far odds are you're gonna be overwhelmed with just how many things you apparently did wrong styllistically even though your code may very well be both correct and well designed So a little less noisy at least initially might be this program here that's the de facto standard within the Python community for formatting your code for you P code style。

 formerly known as PP 8， a program as well is a program that you can not only run on your computer documented at this URL here it will actually take care of the process of reformatting your code for you if it's a bit messy That is if the style of your code your indentation in blank lines and other details as well are not in accordance with the style guide something like Py code style will just fix it for you。

 but another one an alternative nowadays that's actually gaining steam。

perhaps even more popular nowadays， quite simply called black and Black is a program that you too can install with Pip here and it's documented at this URL。

 and the etymology of the name Black is actually an allusion to Henry Ford who invented cars way back when and only sold quite a few black models of the same and indeed he's generally known as saying a along these lines。

 any customer can have a car painted any color that he wants so long that it is black。😡。

So if you think about that for a moment， it's not quite a choice and indeed that's the spirit of this particular formater called black。

 which is that it's opinionated more so than others with a lot of these formatters that exist out there。

 you tend to or your company tends to or your course tends to configure them with certain rules so there might be different ways to do indentation。

 there might be different ways to do imports or blank lines and different companies in different people might reasonably disagree and therefore have their own style guide here。

 their own style guide there and it just tends to waste a lot of time is the thinking if all of us don't even agree on some of these basics So this particular format are called black is an opinionated in the sense that it just makes a lot of these decisions for you。

 and if you don't like the way black is formatting your code tough it that's the way it's going to do it and this is a trend perhaps now at least within the Python community of quibbing a little less over these stylistic details so that you and I can ultimately focus all the more on writing good code and solving。

😡，Problem and let's go ahead and do just this。 Let me go ahead and open up VS code here where in advance I've created a program called students Pi。

 whose purpose in life is just to create at the top of this program。

 a dictionary containing key value pairs， the keys of which are the names of some students the values of which are the houses at hogwarts in which they live。

 And then I've just got a four loop here that iterates over each of those students printing out for now。

 each of their names。 you could imagine certainly doing more with the values as well。

 but for now this is a simple program。 but it's already manifesting poor style arguably certainly inconsistent with Pep8 itself。

 And I know this from just experience eyeballing and realizing wow。

 this is not a good thing that this first line of code goes completely off my own screen feels like it's probably a little long and I'm gonna have to scroll to even see what's going on and this one's more subtle but if you look at line3 here even though I've indented technically sufficiently so long as my code is indented underneath the for loop and any subsequent indentation if I had more lines of code were similarly indented。

would work， and it would be correct， but it just does not accord with Pp 8。

 which prescribes again four spaces of indentation at each level。 So how can I go about fixing this。

 Well， if I've already installed one of these formatters， for instance， something like black。

 I could literally just do this with my terminal window。 I'm gonna run the command black space。

 students do pi and hit enter andvoila you'll see that the students do pi file has been automatically reformat and at top of my file。

 I have now a dictionary， same dictionaries before， but just so much more readable。

 not only does it not wrap around to the edge of the screen。

 you can also see each of the key values pairs one line at a time。

 and you can see that it lends itself to even adding more down the road。

 it turns out it's not incorrect to have a final trailing comma like this。

 even though it's not strictly necessary here on the new line 6。

 Why Well Pama in ravencl is the very last student in this particular in this particular dictionary。

😡，But just in case， as is often the case， I might go in and start adding more key value pairs later。

 a common source of mistake is to accidentally forget that， oh。

 I didn't have a comma there previously。 And here I am adding more key value pairs。

 So that is the kind of detail that black not only fixes for you， but again。

 has an opinion on as well。 So moving forward as you write code of your own。

 It's good to get ingrained into some of the lessons of and some of the guidelines in a style guide like Pe8。

 but know that there's tools be itcode style or black or something else altogether that you can use as a programmer to help you focus more on correctness more on design more on solving actual problems while still ensuring that your code is now automatically formatted as well。

😡。

![](img/680f0bd4ea96d880701695b318563b6a_4.png)
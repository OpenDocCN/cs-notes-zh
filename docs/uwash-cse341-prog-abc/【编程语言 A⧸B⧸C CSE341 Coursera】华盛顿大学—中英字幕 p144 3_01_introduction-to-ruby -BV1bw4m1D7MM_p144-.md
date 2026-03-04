# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p144 3_01_introduction-to-ruby -BV1bw4m1D7MM_p144-

In this section of the course we'll start using the Ruby programming language to study programming languages。

 so in this first segment I want to do a mix of discussing various Ruby logistics and also giving you some background on why we're using Ruby and why it's a good choice for this portion of the course。

So to start with logistics， the main website for Ruby， you can see here is at RuyLang。org。

 the installation instructions for what you need to do to get Ruby running on your computer are available on the course website。

 we suggest different things for different operating systems and so on in the lectures you'll see that I like to use the EMX editor for writing Ruby programs and I encourage you to do the same。

 but you're welcome to use any editor and indeed many editors have plenty of support for Ruby that will be more than enough for our purposes。

There are several different versions of Ruby available and so let me say a little bit about versions and in fact。

 if you' are watching carefully， you' probably noticed that this portion of the video was spliced in because I made the mistake in the past of mentioning specific versions by name that are now no longer widely available and pre-installed and different operating systems and whatnot。

 So none of the intellectual concepts we're going to consider depend on an exact version of Ruby the language is fairly stable。

 but nonetheless， we want to support a range of versions in particular because there are oftentimes where certain versions are easy to install on a particular operating system and others are not So you'll see in the software installation information sort of what versions we're currently supporting and instructions that should be easy for you to get one of those supported versions installed。

 I just want to emphasize that the exact version really doesn't matter。 In fact。

 all of the code we're providing is unlikely to depend。On。

 your code for the programming assignments will probably work fine for any recent version of Ruby。

 but just in case you accidentally rely on some slight change between versions。

 we want to be very clear about what version we're supporting。Now。

 because we're already in part C of the course and we've gotten more savvy at picking up our own languages。

 we may be a little less careful in this portion of the course of explaining every last detail of the language features that we're considering。

 but we do intend for everything to be self-contained and provide everything that you need for the homework。

Now there's wonderful free documentation for Ruby available defining the language。

 particularly giving information about the very large standard libraries and you may need to consult that a little bit。

 but again， we're not going to send you on a lot of hunting for library methods that you may not know about if you do want a book that provides more information about Ruby and how people program in Ruby I've made a recommendation here on the slide that I've found particularly helpful but this should not be necessary。

 This is an additional resource if you'd like to learn more or would like that sort of book format the materials for the course as we have all along should provide you what you need So let me focus a little bit on why we're studying Ruby what's different about this language and why it fits with what I want to cover in the rest of the course the biggest thing is that it is a pure objectoriented language What I mean is that all the values in the language are objects there is nothing but objects even numbers。

Ojects so that will help us to study object oriented programming。

 It's also classbased But what I mean by that。 and we'll explain this in subsequent segments is that we define classes。

 and then every object has one particular class that says how that object behaves。

 So if you've seen Java or C sharp or a very O take to C plus plus this is similar。

 There are object oriented programming languages that are not classbased the best known today is jascript。

 And I wanted to stick with a classbased language and explain things in those terms。

 We'll also see that Ruby has a very nice feature called mixins。

 which are a little bit like Java interfaces and a little bit like c plus plus multiple inheritance。

 but they overcome some of the limitations of each。

 And thatll be a nice thing to study Ruby is a dynamically type language。

 just like we saw racket was dynamically typed。 I want to show you another one。

 And I also feel that willll help us study O object oriented programming。 not to have the。

Types in our way， right from the beginning。There are some other things about Ruby will study It's convenient support for reflection。

 finding things out about objects at runtime。 The fact that it's very dynamic。

 the fact that it has closures， just like we've grown to love in Ml and racket， And lastly。

 that it's a scripting language。 Now， there is no exact definition of what makes a language a scripting language。

 but we'll see various things that are unusual when you've seen other languages。

 things like when you need a new local variable， you can just assign to it anywhere in your method。

 which is like a function without having to say first that you want to have something in that scope that has that variable name。

So there's a lot more to Ruby that we are not going to focus on and I'll be honest that some of these things are what makes Ruby such a popular language。

 but they're less germane to our study of the concepts of programming languages Ruby has lots of support for manipulating strings and we will not study much of that support Ruby is very popular for writing certain aspects of server-side web applications using the Ruby on railils framework which we will not discuss and in general Ruby has an attitude of why not support a big language with lots of different ways to do things very conveniently and we will by no search of the imagination cover the entire language will'll just focus on a subset of the features that will let us study object oriented programming and then a few other things as they become relevant along the way。

So this will complete for us our third position in this little chart you see at the top that after we've studied Ruby well have seen a dynamically typed functional language and a dynamically typed objectoriented language we've also seen a statically typed functional language and many of you will have already seen a staticallytyped objectoriented programming language such as Java or C sharpp so it's nice to fill in that table and I should be clear that we didn't have to use Ruby for this it turns out that rackcet also has classes and objects should you want to do object oriented programming in a racket for example。

 but Ruby makes a more complete commitment to them in Ruby everything as an object and so it's nice to switch to such a language it's certainly not the only language where everything is an object the language small talk actually has a lot in common with Ruby it's just a much older language it's actually a much smaller language so from a teaching standpoint it's nice to use because I could teach you the entire language of small talk。

On the other hand， it's less modern and less practical for modern applications。

 and so I'm happy to use Ruby。So a final logistical note before I show you a simple program and move on to the core material in this section。

 which is the homework for this section of the course is actually a little bit different what we decided to do is instead of like the other homeworks where you pretty much wrote all of the code and maybe we give you a little bit of code to get you started the way this homework works is we're actually going to give you something in Ruby that's a few hundred lines and completely works already and you just need to make various extensions without modifying the code that's already there So this is actually a good way to learn a language which is just to read some code already written in it。

 the challenge of this homework assignment is actually mostly not on writing your code but on reading the code that's already provided to you I think this is a very common skill and software development we're often modifying programs or enhancing programs that have already been written and it's a great way to learn a new language so we're going to try that it's a different approach and I think you'll enjoy it。

The program is actually graphical， so part of the installation instructions is making sure that you can use the TK Graphics library with Ruby。

 you don't need to understand TK very much at all， but you will need to have it on your system and that'll get us set up for the homework。

So with that as background， let me just finish up by showing you a small rubby program as I mentioned。

 I'll use Emax， but you can use another editor if you like Emax should be already configured to handle Ruby quite well by default if you just open any file with a dot RB extension hopefully you will see Ruby down here in the bottom line suggesting that we'll get all the indentation and syntax color highlighting that we want for the rubby language and then this is the code which will understand more after another video or two comments start with the hash character and go until the end of the line things are generally organized into classes so I've defined a class hello here It has a method called my first method Me are a lot like functions in ML or racket but will understand their differences soon enough and then the body of this method is just put S hellello world put S is a builtin method that takes a string and print it out for you when you run the program。



![](img/7e5c5bf955ab21f7a69e0879703a340c_1.png)

Out here at the top level， I've defined a variable X that creates an instance of the Ho object。

 and then I call its my first method method。 and none of that needs to make any sense to you yet。

 I'm just showing you here a program so that you can see me using the tools。

 And for those of you who do know a little Ruby or all of you will soon。

 there are much shorter ways to write a program that prints Hello world。

 but I wanted to show you some of the key pieces。😊，Now we do have a reple for Ruby。

 but I'm not going to show you using it inside of EmX instead I'm going to use it over here in a terminal to open this on Windows I just ran the CMD program the command prompt and that got me here I changed into the directory where my Ruby files were and if I just wanted to run this program and just take the Ruby program which I've already installed and pass it the name of my file and you'll notice that it prints out hellello world and then gives me my prompt back。

Now， I did promise you a Reple。 There's a program called IRB for interactive Ruby hit return。

 and I get a readtaval print loop prompt， just like you expect，3 plus4 evaluates the7。 By the way。

 don't say semicolon at the end。 If you do that， it'll be waiting for another expression。

 And so I have to say something like5。 And then I'll get5 back as my answer。

 If I want to load the contents of a file。 That's load。

 And then in a quotation marks Ruby Intro do Rb。 This is like use when we use Ml or the run button when we use racket。

 hit return。 We'll see it printed hello world。 And then the result I got back was true。

 because that was the result return by the put S method。 So here I am at my prompt。

 I could continue to program in Ruby for as long as I wanted。 and then I was done， I could hit quit。

 and that would leave the Reple。 And that's our introduction to Ruby。

 will' jump into the details of the language in the next segment。😊。



![](img/7e5c5bf955ab21f7a69e0879703a340c_3.png)
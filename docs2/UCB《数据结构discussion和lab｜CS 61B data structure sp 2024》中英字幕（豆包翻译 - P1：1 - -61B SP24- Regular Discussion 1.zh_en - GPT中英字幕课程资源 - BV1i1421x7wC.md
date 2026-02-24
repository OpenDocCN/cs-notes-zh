# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P1：1 - -61B SP24- Regular Discussion 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/48e8bfad2d9e52f17b281ccff1fb66c7_0.png)

Hello， my name is Elena and I'll be doing the walkthrough video for week2 discussion。

 which is about In to Java。So first we're given this class， CS61B student。

 which represents a student in CS61B。Each student has an ID number， grade。

 and all students have the same instructor。Also， we have the construct for the student and two methods。

 watch lecture and get instructor。Given this class， we then want to fill in this new class CS6 UMB。

 which represents the course CS6 UMB。So let's start with Part A。

 so we want to fill in the CS61b class and we need to declare and possibly instant and assign variables。

And there are three variables that we want to have first is the university which is the name of the university。

 which should be UC Berkeley for all semesters of CS61B next is the semester。

 which is the semester that the course is being taught。And we also have students。

 which is the CS6 UMB students enrolled in the semester CS6 UMB。

 and we have to remember that the course has a fixed capacity。So。

When we want to create these variables， we first have to think about like whether we want them to be public or private。

And we also have to think about the type of the variable。

And we also have to think about whether it should be static or instance。

 so I'll first write down the three variables that we want。So university。Semester。And students。

To keep this simple， let's just make all of the public variables。So， public。Public。And public。And。

Now let's think about whether these variables should be static or instance。嗯。So first is university。

 this is UC Berkeley for all semesters of CS6U1B and we also have the semester and the students。

 so because semester and students change for from one semester to the other。

 those should be particular to a certain instance of CS6U1B， so those should be instance variables。

For university， on the other hand， this is the same for all semesters of CS61B。

 so this should be a static variable。So we have to label this variable aesthetic static。

 if it's an instance variable， then we don't have to write anything to indicate that。Okay。

 now let's think about what type these variables should be。

So university is the name of the university， which is UC Berkeley。

 so that's a string and semester is the semester the course is being taught， for example， fall 2023。

 so that should also be a string。So you have to write string。And string。For students。

 this is a bit more complicated， so students is the CS601B students androll in the semester's CS601B。

So students should be a data structure that stores all the CS61B students who are in the course。嗯。

It should be a data structure and we also have to keep in mind that the course has a fixed capacity。

Because the capacity is fixed， that means the data structure。It just has like the size is fixed。

 so in order to store the students， we can use an array because the size is fixed for an array。

And the type of this array should be CS61B student。Let me make more space here。ok。

So these are our three variables。Now， moving on to part B。

It says each CS6 U1B instance represents one semester of the course。

 so we want to create a constructor that takes in a capacity。嗯。

So it takes in capacity for the maximum number of students enrollable and array signups consisting of the students who signed up for the course and the semester。

In the Conor， we want to enroll capacity students from signups and initialize the semester instance variable。

Okay， so let's first write the first line of this constructor。Which is public。C， S 61 B。

And we also have to write the parameters of the constructor。So it says a capacity。

Which is the number of students enrollable， so that is an integer。We also have the array signups。

And these store the students who signed up for the course。So this is also a CS61B。CS61 B students。

Aray。Signups。And we also have the semester， so this is a stream。

I'm going to move this all over a little bit。Semester。ok。Now。

 we have to fill in the body of our contractor。So let's just start by。

Initializing the semester instance variable。So we want to assign the semester of this instance of CS61b to the semester that was passed in。

So to do this， we have to do this dot semester。Is equal to semester。Next。

 we have to enroll capacity students from signups。And we want to put the student that was in signups into our course。

 so in the student's array， which stores everyone who's in our course。

So we first have to actually initialize our students array， so this would be students。Is equal to。

New CS， S 61 B student。And we have to pass in the size of our rate， which is capacity。Alright。

 now for each student in signups， we want to put them in our students array。

 but we only want to put capacity number of students in the course so to do this we can have a for loop。

So we can do for an I equals 0 until I is。Less than capacity。And then I plus plus。

Inside the for loop， we want to take the student。In。Signups。

 so sign ups at index Oh I got the switch。 My bad。 Okay， so students， we want to put。

Assigned students at index I。To be equal to the student in the signups， all right。

So that way we can take all the students in sign ups and put them in the course。

 but we only want capacity number of students。There is like a small issue with this constructor。

 which is that we're always assuming that signups has at least capacity number of students。

 so if signups has less than capacity number of students there would be an index out of bound error so for questions on exams。

 if we have something like this will try to like make it really clear if you can like what you can assume the size to be if that's necessary。

All right， so that's it for Part B。Next is Part C， which is implementing methods。

So we want to consider what the method should return， its argument types。

 and whether it should be static or instance。So。嗯。For Make students watch lecturecture。

 this makes every student enrolled in the semester of the course watch lecturecture。

And the other method we have to do is change university， so this takes in a new university name。

 new university， and this changes the university for all semesters of CS61B to that new university。

So。嗯。For make students watch lecture， let's think about what it should return。

 so this just makes all the students watch lecture and there' is nothing that really should be outputted here so we can just make this return void。

And the argument types， we don't really need to take in anything here。

 so we don't really need anything as input or as an argument in this method。So yeah。

 and then last thing。Whether this method should be static or instance。

Because we have to make all the students watch lecture。

 students are particular to a certain instance of CS61b since this is an instance variable。

Because we need。That information， which is particular to each instance of CS61b。

 this should be an instance method。Okay， with that information， let's try to write this method。

So this should be public。Vid。Make students watch lecture。

And what we want to do in this method is make every student watch lecture so every student who's enrolled in this course。

 so let's think about like what this means in code so thinking back to the CS61B student class each student has two methods watch lecture and get instructor so we can use the watch lecture method to make this student watch lecture。

And we have to do that for all students who are in the CS61B course。

 so what we can do is we can use this studentss array， which we already have。

 which already stores all the students in the course。So。

Whenever we want to like process information that's like or process all the data that's stored in。

An array or a data structure in general we can use a loop so we can use a for loop for this and in the solution it uses a for each loop。

 so what this is saying is basically for each C 61 B student。Which we call student。

So for each CS61b student in students。The array。We want to make that student watch lecture。

We can call the watch lecture method on this student， so student dot watch lecture。So yeah。

 to summarize， this basically goes through each student in the student's array and makes them watch lecture。

 so that's it for this method。The next method that we need is the change university method。

 so this takes in a new university name， which is new university。

And we have to change the name to that。So the return type of this。

 we're not really having any output here， so we can just a return void for this one。

And it has the argument， new university。And。We also。

Need to decide whether whether this method should be static or instance。

 so because we want to change the university name for all semesters of CSX1b。This should be static。

And yeah， also the university is static here。So yeah， it makes sense。Okay。

 so let's given this information， let's work this method so public。会。Change university。

And then we have to specify the parameters so string。New university。

And what we need to do here is basically reassign。This variable university to be new university。

All right， that's it for this matter。The last thing we need to do is Part D。

 which is modify your existing implementation to support expand。

 which allows our infrastructure to handle course expansions， whether the course expands。

 students that were originally waitlisted should be enrolled up until the new capacity。

So there are multiple ways that we can do this。So。One way to do this is。

We're already given the so we already have the students。Aray。

 which has all the students who are enrolled for this course and also in the。

And the constructor were given signups， which are all the students who signed up for the course。So。

One way to do this is。Resize。Students。So。Later in this course， we need do project one。嗯。

Which is like making a deck。Basically， like this is pretty similar to what you'll be doing there and。

So what we can do is whenever we want to expand the course。

 we can resize students and take in more students from the signups array。

 so we have this signups array。And we have。The students array。And whenever we want to expand。

 we can like have a helper method called resize。And what we want this to do is make the students array bigger。

So， yeah， then。After we have a bigger array， we can transfer everything。

 all the students who already were in students， and we can put them in the new students array and we can also take in more students from the signups。

So that's one way we can do this。Another option。Is to。Just keep track of。嗯。

We can just have like the sign ups array and we have another variable。嗯。

To keep track of the capacity， so we currently have three variables university semester and students。

 but we can have a new integer variable， which is capacity。And we also have a signups array。

So let's say signups is like this。But we have a capacity。

 let's say that's less than the size of signups， so we can say like these students can all fit in capacity so they can all be enrolled in the course。

So this will be the actual students。Actually。Enroll。And。Let's just say that， like。

Indices0 through I represent all the students who were actually enrolled who in the CSX1 B course。

 So in this example capacity。Will then be equal to I plus1。Because in total。

 that would be i+1 students that we can fit in CS system B so。Yeah。

 those are just some ideas that we can use to expand the capacity of the course。So yeah。

 that is everything for this discussion we basically just。Completed， filling out this CS6Mv class。嗯。

So that was pretty long， but good job if you made it through。

Thank you for watching this video and good luck for the rest of the course， bye。



![](img/48e8bfad2d9e52f17b281ccff1fb66c7_2.png)
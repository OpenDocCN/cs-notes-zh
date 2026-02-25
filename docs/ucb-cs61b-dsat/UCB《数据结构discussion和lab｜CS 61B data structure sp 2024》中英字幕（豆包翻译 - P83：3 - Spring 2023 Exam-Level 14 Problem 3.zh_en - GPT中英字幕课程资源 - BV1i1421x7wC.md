# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P83：3 - Spring 2023 Exam-Level 14 Problem 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/49bc931c79616fdca0986745fec150d7_0.png)

Hi， I'm Angel and welcome to CS 61 B exam level discussion 14 problemble three shuffled exams so let's go ahead and jump into the premise of this problem for this problem we will be working with exam and student objects both of which have only one attribute to SID which is an integer like any other student ID。

😊，Pairry learned thought it was ready for the final。 However， we will find that it was not。

 It had meticulously created two arrays， one of exams and the other students and ordered both on S I D。

😊，Such that the I exam in the exams array has the same SID and as the I student in the student's array note that the arrays are not necessarily sorted by SD we'll see what that looks like visually in the next slide。

 but this means that the arrays are not ascending or descending based on student ID just that at the I index。

Both the exam SID will match the student SID。However， prairie learning crash。

And the students array was shuffled， but the exams array somehow remained untouched Now with the exam coming up。

 time is precious， so you must design a big O of N time algorithm to reorder the students's array appropriately without changing the exams array note that without its underline so we really should avoid changing the exams array at all and we have that big O of N time constraints Now a hint is to begin by reordering both students。

And exams arrays such that the Ith exam in the exams array has the same SID as the I student in the student's array。

All right， let's go ahead and see what that looks like visually。😊。

So here we have the exams and the students where they're not matching SIDs at the indices so at the zero index we have 499 as the SID for the exam but at the zero index we have 409 for the students so these don't match we have 37 for the exams and 351 for the students and these don't match either and we have 351 for the exams but that doesn't match 317 Now our goal is to get it to match where we're not affecting the exams array at all but the students will go ahead and match the exams so now we have 499 and that matches the new students of 499 we have 317 and that matches the 37 in the students and we have 351 which matches the 351 in the students。

😊，All right， so I'll leave the hint here and we'll go ahead and take a look at the solution and oh feel free to pause and work on it by yourself before coming to the solution。

I'll resume going over the solution in five，4，3，2， one and zero。

 let's go ahead and go over the solution。 Hopefully we've gotten a decent start to this problem。

So we're going to go ahead and begin with creating an exam wrappper class now what will this class have it will have an exam instance and an index of corresponding exam of the corresponding exam in the exams array so what does that mean so let's take a look at this first exam that has the SD of 499。

😊，The corresponding wrappper will have 499 as the exam SIT and zero because it's at the zeroth index。

Now， going on to the next one， we have 317 as the S ID so the exam wrapper will go ahead and have 3。

17 as the exam S I and one as the index。 And we're going to go ahead and continue this process for all the exams Note that students is still。

😊，It's still shuffled。We're not changing students at this point quite yet。

 but the exams rappers are going to go ahead and go in this exam rappers ID array and they'll go ahead and match the exams array。



![](img/49bc931c79616fdca0986745fec150d7_2.png)

Yeah so let's go ahead and solve that shuffled problem though what we're gonna to go ahead and do is we're going to run Radex sorts on the student SDs so now the student SDs are going to be arranged from a sending order based on the SDs so let's look at the students array after this we have 150317351409 and 499 and this is basically increasing with each entry。

😊，Now we are also going to run this on the SIDs of the exam wrappers so now we have 150317351 and it's now increasing based on the exam SID of the exam wrappers and wait a minute that was number sequences kind of sounded familiar in that I actually mentioned them earlier and that's because the SID in the exam wrappers matches the SID in the students so we have 150 matching 150 we have 317 matches 317 we have 351 matching 351 etc cetera。

 etc ce Co so now we were able to get these exam wrappers to match the students objects。😊。

And that kind of completes the hints now the big question is did we break any rules and what by breaking any rules。

 did we accidentally go over our runtime？And we actually find that we did not because RaX sort will go ahead and take a linear amount of time since the SID is a fixed length and of base 10。

 so we still have that big ofath and satisfied with this step。😊，All right。

Now that we're done with the hints， we still need to move the Ith students to the proper place in the original exam array。

 so to achieve this， we're going to go ahead and use the Ith students for the I student we will access the I exam wrappers since they're now matching at index。

And set the index of the I student as the exam wrappers index attributes so let's go ahead and compare so for this first one we have for the zeroth one sorry forgot about zero indexing we're going to go ahead and have students with the SID of 150 and we're going move it to the index that's stored in the corresponding exam wrapper and that'll be four so we're going to go ahead and move this to the fourth index and what that looks like in code is we're going to go ahead and say students copy4 which is a copy of the students will equal students zero because we got this four from that corresponding exam wrapper。

😊，Now moving on， we'll do the same thing with first index where we find that students copy one。

 we'll go ahead and equal students one because we took the corresponding exam wrappper and we found that we should put it at index one from here。

 we can do the same thing with second one because this is the corresponding exam wrapper。

 we get the index from that and put the corresponding students in there so we're going to have students copy two equals students two we're going to do the same with three。

And then finally with four， we're going to go ahead and complete it where the corresponding exam wrapper is going to be 4990。

 so we're going to put this one at the zeroth index with student copy zero equals students four so the idea here was behind the exam wrapper is that we somehow want to find where the exam originally was。

sortrted so that we have some way of matching the exam ID to the student ID and then moving that student ID slash student object to that proper order。

 and that's why we needed to store both the exam SID and the index for reing。こ。

So now student copy will go ahead and just match exams and we have our answer that was able to be solved in Big O in a time。

Of a big O of end time。 So luckily， those students were able to take test Hopefully they had a good time。

 Alright， yeah， sounds super good。 Hopefully that was helpful and yeah。😊。



![](img/49bc931c79616fdca0986745fec150d7_4.png)

![](img/49bc931c79616fdca0986745fec150d7_5.png)

![](img/49bc931c79616fdca0986745fec150d7_6.png)
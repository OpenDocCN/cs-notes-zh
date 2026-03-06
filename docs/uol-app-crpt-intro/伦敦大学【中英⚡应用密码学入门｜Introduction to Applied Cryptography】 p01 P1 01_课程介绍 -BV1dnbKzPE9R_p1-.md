# 伦敦大学【中英⚡应用密码学入门｜Introduction to Applied Cryptography】 p01 P1 01_课程介绍 -BV1dnbKzPE9R_p1-

![](img/1b7ae01c38115f93c9fc08db94137f81_0.png)

Welcome to the course an introduction to Applied cryptography。

 my name is Professor Kate Martin from Royal Holloway University of London and I'm absolutely delighted you've decided to come and check this course out。

And I guess my objective in this short video is to tell you a little bit about what to expect in this course。

And I think to persuade you to continue， which I very much hope you will do。

So I've worked in the area of cryptography for most of my professional life。

 I started life as a mathematician， this is not a math course。

 I moved into cryptographic research and for the last 20 years I've been working here at Ra Holloway as a researcher and teacher on our programs。

 particularly our master's program in information security where we really have been trying to explain to all sorts of people who wish to go into the cybersecurity profession more generally。

The role of cryptography， why it is so important in the subject area that they wish to sort of follow a career in。

So that really is my objective in this short course as well is to try and persuade you that cryptography is very important that it's an applied subject and also give you an indication of the role that it plays in broader cybersecurity。

So why are we giving a short course here on applied cryptography the reason is really fundamental that cryptography lies at the heart of so much of what we do in cybersecurity there's very few technical cybersecurity processes or solutions that don't rely on cryptography rely on using cryptography and so that's why we have put together this course on applied cryptography this is not a course about mathematics。

 this is not a course about detailed cryptographic algorithms if you're hoping to learn that sort of stuff you'll have to look elsewhere。

This course is about what cryptography is。But how it's used to support wider cybersecurity。

 that's absolutely our goal over the next four weeks。

And four weeks is simply not a long time to go into cryptography。

 so we have to be very selective about what we're going to present。

So here's the basic idea I'm going to be explaining to you。What cryptography is。

 what services it provides。We're then going to look at applications of cryptography。

 show you how cryptography is used to support wider cybersecurity。

We're going to also look at a little bit at some of the core ideas。

 things like algorithms and keys and how these come together in cryptographic systems and introduce some basic terminology so you have the central language of cryptography。

But then we're also going to look at what cryptography does not do by looking at how crypto systems can be attacked or can fail。

 so we're going to basically look at the wider crypto system and look at the points of weakness in that system。

So by the end of the course， you'll have a very clear idea of what cryptography is。

 how cryptography can be used。You'll have the core terminology and terms that will allow you to talk about cryptography。

 but also you'll have an understanding of cryptography's vulnerabilities what it doesn't do so so I want to really show you what it does but also make you very aware of what it doesn't do so by the end of the course I think you should feel very comfortable that you understand what cryptography is and what its role is in supporting wider cybersecur。

So。Who might find that useful， why might you want to continue。

 does this fit your interests and needs？Well， I am imagining that you are either a complete beginner to cryptography。

 in which case this is an excellent course， because it's without going into the technical details of this subject and this is a subject which can be very technical if you go quite deep into it。

I just want to show you what it is and give you a feeling for what it does and so if you're a newcomer to cryptography。

 I think this course will serve you very well because by the end you will go， aha。

 I do understand cryptography's sort of modern use and application。On the other hand。

 I'm also imagining that some of you may be sort of aware of that already。

 but what you're actually trying to work out is， you know， what's your next steps， you know。

 might cryptography be something that forms part of your professional career。

Or maybe you're looking at doing a university course， for example。

 maybe you're a computer scientist and you're just trying to figure out， you know。

A I interested enough in cryptography and cybersecurity to make that my area of specialism？

And maybe even you're someone who's working in cybersecurity and you've come across cryptography and you just want to know a little bit more about it。

So that's three types of person I imagine this course could work very well for and also that just includes anyone who's just curious。

 so if you're here because you're just curious you've always wondered what cryptography is but you're not planning to work in the area。

 you're just curious， I think this course will serve you well as well。

Now what will you need to know before you embark on this well not very much really I'm not assuming you know very much I'm not going to give you a basic introduction to how computers work and the internet works and stuff like that。

 we're not going to do that so I'm going to assume that you at least have a familiarity with sort of a computers and networks and understand the kinds of things we do with them and have'm a vague notion of what security might be there but I'm not assuming you're an expert on any of this stuff。

😊，I would like to feel this course is pretty much as self contained as possible。

 and I'm certainly not assuming you're a mathematician we're not going to go to any mathematics I'm not expecting you to have any understanding of math。

 that's not what this course is about okay。So what is the course itself made up of。

 so let me just explain that the raw ingredients， there's going to be things for you to read。

 I'm assuming you can read。There are going to be some short videos for you to watch。

 so they'll be made available， but there's also some things where there's a chance for you to do things so for instance I have prepared some questions。

And written some answers， I've also prepared some discussion items， which I've called activities。Now。

 in both of these two cases。These are things that I'm hoping you will engage with。

 so if you're asked a question where there is an answer。

I would like you to think very carefully about that question and come up with your own answer before you reveal the answer。

 for example。And if there's a discussion item where you're encouraged to go and post your thoughts。

 please do that， okay， so these activities which are designed to get you communicating with fellow students on the course。

 please engage with them。I'm sort of imagining that you have something I'm loosely calling a study journal now by that I don't imagine you have this big leather book called Stud journal what I really mean is that you're going to take some notes and you've got a space where you can gather your thoughts and as we go through the course whenever you want to take notes anyway but I'm imagining you have such a thing so have a space where you can note take or write down thoughts or write drafts of a solutions you're going to post that kind of thing I'm loosely calling that study journal。

And right at the end of the course， we'll have something we call a peer review。

 which is something that I'm going to really encourage you all to respond to and then comment on the solutions other people have put out there。

 thus's a little activity for the end and there'll be explanations about that when we get there。

Okay so that's the main ingredients of the course it's only four weeks we don't have too long and so we're not going to cover that much ground but on the other hand to get through all that you are going to have to engage and I want to sort of tell you a little bit about my own experience of doing a MOOC a course of this type which was on a subject nothing to do with cryptography that I embarked on and I thought oh I really want to know about this and I started doing it and I fully intended to commit the time and then were questions which needed a bit of research and a bit of thought and the answers were there and I started finding myself shortcutting and just revealing the answers and then there was stuff you were supposed to read and post and I thought I don't really have time I'm going to skip that part。

And actually very quickly I realized I was wasting my time because I wasn't learning very much。

 I thought I wanted to know but I wasn't putting the time in and in the end I didn't achieve very much and so the lesson I learned doing that is that on a course like this regardless of how short it is。

You only really get a value if you properly engage。

There's a few things I really would request of you if you want to follow this course and get from it what I have designed you to get from it。

First get to know each other so please get on and introduce yourself if prompted to do that just so that people know who you are and what your interests are。

But if there are things you are asked to do， like a question that you're expected to think about and then。

You can reveal an answer， please take the time to think about it。Please invest sometime。

 don't just quickly reveal the answer otherwise there's almost no value from that process and if there's an activity where you're asked to do something and probably you're expected maybe to do a little bit of research and a little bit of thinking and then post some responses。

Please do that so so please invest that time because you will get something from the process and please post up your activity solutions don't just look at the posts of others take part because that is really where you're going to get value so I know this is a short course it's got limited expectations in one sense but what I do know from my own experience is that that old age what you put in is what you get out is definitely true and I've designed this that so that there are all sorts of points where I'm hoping you will invest some time and take part and I know for sure you will get maximum benefit from this course if you engage with that so that's my request please give that some serious thought and then you will get I hope you are hoping to get from this course。

Okay， so I think it's pretty much time to get started， I'm really delighted you're here。

 I hope I've persuaded you to stay。😊，🎼AndI hope I persuaded you to take art and if you do all these things。

 I also hope you're going to enjoy learning about applied cryptography。



![](img/1b7ae01c38115f93c9fc08db94137f81_2.png)

![](img/1b7ae01c38115f93c9fc08db94137f81_3.png)
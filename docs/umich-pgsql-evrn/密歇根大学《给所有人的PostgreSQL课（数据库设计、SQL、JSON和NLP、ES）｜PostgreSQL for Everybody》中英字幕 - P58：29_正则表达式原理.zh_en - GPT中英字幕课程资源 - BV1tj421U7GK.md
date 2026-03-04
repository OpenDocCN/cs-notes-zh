# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P58：29_正则表达式原理.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/4dee257e2639045fd12af3a18ac286a7_0.png)

![](img/4dee257e2639045fd12af3a18ac286a7_1.png)

Regular expressions are a powerful part of data analysis。

 and they're sort of a little weird at the same time。

 but they're also mysterious and magical and mystical and so there's something that you can kind of impress your friends with。

 and once you know regular expressions， you can use them in lots of places and so what regular expressions are is they came out of some stuff in the 60s and the 70s having to do with programming languages that were all about strings。

And analysis of strings and languages and formal languages and these kinds of things。

 the kind of thing you study like when you build a compiler in computer science。

And regular expressions are one form of languages that can be specified。All that hardly matters。

 but what matters is that it's a text based programming language that you use little characters instead of the word if。

You can have loops， you can have if statements， you can have all kinds of stuff and pull stuff out。

 and it's for working with strings。And it's basically wild cards， but it's also just matching。

 but also parsing。And it's used lots of places like if you use like Linux。

 you can use commands like GP， which stands for generalized regular expression parsing or regular expression or the RNAE。

Every programming language， ja， PhP job they all have it and there are some subtle differences across implementations just you know one language would pick a thing and then they would add a cool couple couple cool features another language would sort of start doing and they would add different cool features so there's kind of this core of regular expressions that are common and then there are sort of extra features that are are differently implemented differently not not all things implement them the same so Postgress uses one particular regular expression I think Postgres in a sense came to regular expressions late and so they're just like picked a very conservative set of regular expressions。

So if at first you don't understand regular expressions， they seem to make no sense。It's okay。

 that's normal。 They're actually kind of fun。And it's like learning a new programming language。

 So just if you learn Python， and then you learn SQL。

 there's like a whole different way of looking at the world when you learn SQL。

 they're both programming languages， in a sense， regular expressions are yet another programming language and the implicit thing that regular expressions are doing is looking through a string and doing things。

 searching for things， pulling things out， searching for one thing then search another thing after that。

 and it's a very compact language and it's fun on stack overflow to say find me a regular expression that pulls out email addresses。

 that one of course， is pretty easy， but there's lot， there's a lot to learn。 so。

So there is a XKD XKCD comic for everything This one is talking about regular expressions kind of in Pearl a little bit and basically the storyline is is there is a whole bunch of data that has to be searched for email addresses and someone types Pearl and a couple characters of regular expressions and then searches all the data and a way it goes so you can go see that on XKCD one thing I like about XKCD is that it's accessible and so you can read the accessible version of it and I believe in this slide if you grab the slides I've got the accessible version of the narrative。

There。 so heres a little regular expression， what I call a quick guide。

 And this is like the keyword of a programming language。 So carrot is not just a carrot。

It matches the beginning of the line。 Doar sign matches the end of the line。

 Tot is a wild card character， which some wild card systems like Linux or doaws use asterisk as a wild card character。

In this language， asterisk means we're going to repeat a character， there is greedy and non greedy。

 which we won't cover too much here。 There's plus， which is one or more characters。

 There is a series of bracket expressions， which are single characters that's a set。

 so bracket AE IOU is either an A or an E or an I or O or U。

And then if you put a carroat at the beginning of the bracket expression。

 you see how this is a programming language。If you put a character that's any character other than capital X。

 capital Y or capital Z。And then you can even have ranges so you can have bracket A dash Z，09。

 that's lowercase letters and numbers。 Then parenthesesis。

 which we'll talk about in a bit when you have this big search thing and you want you don't want to pull it all out if you're extracting from a string。

 use the parenthees to kind of mark the parts of that the matching expression that you want to actually extract。

 you'll see when we get to an example。So come back to this。

So the documentation in Postgres is really good， I'm not going to repeat it here。

 I just encourage you to go take a look， they've got all of the sort of regular expression things and really simple regular expression examples and I'm not going to go through them again I just I really like what how Postgres documents it。

 they document it without going overboard and without going sort of not enough。

So here are the basic wear claws operators， which is what we're going to use， there's the Tilde。

And there's so till is matches， which again， does this string match this regular expression。

 so regular expression either matches yes or no。You can say you want your matches to be case in sensitiveitive。

Exclamation Tilde says anything but this， the match and then exclamation tilled asterisk says does not match case insensitive。

Okay， so。When I first started looking at this， I'm like， well。

 I didn't use the word ragx or something， but you know。

 hey regular expressions are cryptic and so these little operators are cryptic too。

Now it's a little bit different than the light that we've talked about before。

 So if we say tweet tilled UMSI， the key to a regular expression is if it has a string。

 it's going to sort of run that expression along the string check for a match， check for a match。

 check for a match， it's more of a for loop， whereas and you're not matching the whole string you're matching a substr。

 that's the Ted operator， the regular expression match operator。If you're using the like operator。

 which is actually part of standard SQL， you have to put character a wildcard character at the beginning in the end。

 so percent UsI percent says， I want to match UsI anywhere in the line。

 whereas in regular expression， when you say find me UMSsI。

 it implies that it's going to kind of work it across the whole all the characters of the column before it decides if it matches or not so。

There's an implicit loop in these things。So here's a bit of data that I put in just sort of so that we can play with it。

 And we start we start out by building the simplest regular expression。 It functions like like。

 right， And so it functions like like， we use the tilled operator。

 And so this basically takes the email。 And in a sense。

 it slides the U across each of those columns and sometimes it matches and finds a match here。

 sometimes sometimes get the end， there's no match。

 So that basically says I would like to see the ones where if I slide Uish along this line。

 I want those， and I don't want the ones that don't have umi in them。

 And so it's kind of like a wear clause， it's like a like but with percents at the beginning in the end。

 again， implicitly in regular expressions。 there is a loop， It's moving it along the way。

 So here is the first。 And I won't go into too much detail in all these because， again。

 there's a lot of good documentation。 But just to give you a sense of how these。

Programming language work。 So this U me basically says， I'm going to slide youish along each thing。

 But here I add a special character。 So in this case， I'm adding the carrot。

 So what that says is I am looking for situations where the email address starts with the letter C。

 meaning this matches the beginning of the carrot of the column， and that means C。

 And so now we have grounded the match to be at the beginning。Of it。 And you could。Right。

 and so curt C basically is going to say this one， this one， C 7。

 Colleen and the other one don't match。 I could do something like， say。嗯。

dollarll sign as the ma my match。 And then that would hook this instead of going across the whole line。

 It connects it to the end of the line。 And so now the ones at end and M are those Apple dot com ones。

 and the other ones don't match。 And so all I'm trying to point out is these things here are functioning as like。

Callling。Ends with or starts with or something。 And so。

 so you basically are writing code by controlling the regular expression。

 It can't do everything in regular expression， but you can do a lot of stuff with the regular expression。

So here's a thing where I do the dollar sign， I basically say select where they end in dollar sign。

 so it's EDU， that regular expression that's going to slide but then because the dollar sign it's locked to the end of the string。

And then we're looking here for。This is， this is matching the first character。

 If it was inside thes brackets， the carrot matches the first character。 If it' inside the brackets。

 It would mean not， but it's outside so what it means first character。 It's a programming language。

 right， And then we have a bracket pair。 And this is the letter G or the letter N or the letter T。

 So what this is saying carrot， bracket G， N， T bracket is I am looking for email addresses that start with G or N or T。

 lower case。 I could have had that ignore case。 And so G N or T， Where's G N or T， N G N T。

 So that's going to match these three。All right， oh， and there we are。 It matches those three。Right。

 here's the ones that match with dollar Edu， EduU with the end。 so you get the idea again。

 I'm not going to go in super great detail。This shows a range。And so I'm saying I would like。

In time you see bracket， you got to remember。 that's one character。 That's 0 through，9，0，1，2，3，4，5，6。

7，8，9。 And remember that this regular expression is slid across the whole thing。

 So what this is really looking for。Is a having a single digit anywhere in the email。

 And so then we go Ted 79 and Glen1 match because both of them have a digit。

Then I can tweak it a little more and I say， you know what， I want， I want a two digit sequence。

 So now we have bracket 0 through 9， bracket 0 through 9。

 That says one digit immediately followed by another digit。 I could put something in here like。

Dot star。 And that would say one digit followed by any number of characters。

 followed by another digit。 right， So there's all kind of fun things that you could do here。

 And so what this does is this finds me in this case。Two digits again。

 it's searching it's moving that two digits match down the string and it finds two digits next to each other in TEed 79 atumuc。

ed。

![](img/4dee257e2639045fd12af3a18ac286a7_3.png)

Again， these are super simple regular expressions that are very basic and you will have a lot of fun as you learn more about regular expressions。

 So up next， we're going to talk about how we then that was where clause， how you pick things。

 Now we're going to take and pull stuff out of columns using regular expressions。😊。



![](img/4dee257e2639045fd12af3a18ac286a7_5.png)
# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p88 18_代码详解：数据插入与删除.zh_en -BV1Lr421A75d_p88-

Hello and welcome to Web applications for everybody right now。

 we're working through some of the code for the P portable data objects。

 Now you have to run this on your own local host and you have to file the notes to get things set up。

 we did that in a previous video。 So what I'm going to play with now is a little more useful code user1 do PhP And so if I take a look at user1。

 PhP。 file the pattern of requiring P PhP。 and of course。

 P PhP has my database connection information with Id and password。



![](img/9c63b18d293474067bd766f7ff20ea68_1.png)

And I'm going to use sort of my model view controller pattern where I'm processing the data at the top。

 And then I have my template at the bottom。 So this is all the silent processing code。

And then here is the logic。 And so on a get request。

 it just is going to fall straight through here because there's no post data。

 and it paints this post form， which is exactly this。 And it gives me a name。

 a password and an email。 And so I can say， Sally。

![](img/9c63b18d293474067bd766f7ff20ea68_3.png)

Sally。At U IU dot Eu and Sally's password is 9，9，9。



![](img/9c63b18d293474067bd766f7ff20ea68_5.png)

And then I hit post。 And then that's going to come back in the top of this script again。

 And this time these three variables wells are going to be are going to be set。 Okay。

 so when I hit add new here， it's going to add another value。 And so it runs through here。

 and here's the SQL。 And this is PO P basically has placeholders for colon name。

 colon name colon password。 and we'll talk about why this is later。 I just print out the SQL。

 And that shows this insert。 And then it runs that statement taking the name。

 email and password from the post data。 Now I didn't have to name name， email and password the same。

 but sometimes you do that just to keep yourself。Keep yourself sane。 And so that did the insert。

 So I did an insert as a result of a post。 So if I go take a look at my new rows。

 you see that now I have a stallally row。 Pretty cool hu。



![](img/9c63b18d293474067bd766f7ff20ea68_7.png)

![](img/9c63b18d293474067bd766f7ff20ea68_8.png)

Okay， so that's user1。Let's take a look at user 2。 So user 2 basically is going to， in addition。

 this code here is the same。 It's the code to do the insert。 And is H is the same。

 But the only thing I've done different is Im printing out a table。



![](img/9c63b18d293474067bd766f7ff20ea68_10.png)

And then printing out all the data。 So if I go to user 2 instead of user 1。

 it looks exactly the same。 This form is going to be at the bottom。And so but we see the old ones。

 And so now I can say something like Fred。Fred@um。edduu。And a password of some random set of numbers。

 And this form here is the same。 The difference is now， when I do the post。

 it's going to come in here， it's going to do another insert， and that's going to fall through。

 And then it's going to show me all the new ones。 And so now we have this thing where there you go。

 and Caitlin。

![](img/9c63b18d293474067bd766f7ff20ea68_12.png)

![](img/9c63b18d293474067bd766f7ff20ea68_13.png)

So we'll put Caitlin in。 so we now have this thing that's both showing us each time we， oh。

 I kind of mess that up。 but to fix that later。

![](img/9c63b18d293474067bd766f7ff20ea68_15.png)

Her emails wrong。 I didn't do any data validation， but you can see this one here where we're sort of also we're querying。

 we're reading and constructing the table。 So we've kind of communicated a few of these things。

 And so if we look， let's take a look at our database， browse。 and there's Kate， okay。



![](img/9c63b18d293474067bd766f7ff20ea68_17.png)

![](img/9c63b18d293474067bd766f7ff20ea68_18.png)

So now what I'm going to do is I'm going to show you how we might delete。Now。

 the key thing to deleting is you're not supposed to delete on a get request。

 And so I'm going to write this thing called userr Dell and pass in the user ID that I want to delete as a as a。



![](img/9c63b18d293474067bd766f7ff20ea68_20.png)

As a post parameter。 So let's go into user to Dell。

And so now I've just past just painted a form right here。 Use ID is a field。

 and I am going to delete the Kate1 that I just made a mistake typing in。

 So I'll put5 in and send a post in。 So now I'm when I hit this delete button。

 it's going run here again。 And this time post will be set because it'll be set from that5 and I'll delete from users where user ID equals Col and zip That is a placeholderer。

 I'll print out the SQL and a pre。 I'll prepare it。

 and then I'll run it mapping zip to the data that came in from this field over here。

 So this code's going run when I click this button。



![](img/9c63b18d293474067bd766f7ff20ea68_22.png)

![](img/9c63b18d293474067bd766f7ff20ea68_23.png)

ルルルルルル。So we'll go hide that。so it ran and the user's gone。 oop， that didn't look very。

 So when I go over here and I browse it， Kate's gone， and I can get rid of four。 I can say4 delete。

And let me take a look。And it's gone。 Now， here's the thing just to remind you about SQ L。

 if I delete 42。There's no 42 here。 That's not an error because I said delete from users where user I equals 42。

 Well， there was no user I D 42。 So it did exactly what I asked。 That's not a syntax error。

 It's a syntax error。 If I don't spell the word delete right or the word from right。

 But having no records that get deleted is not itself。 an error。 So that's how we do a delete。



![](img/9c63b18d293474067bd766f7ff20ea68_25.png)

![](img/9c63b18d293474067bd766f7ff20ea68_26.png)

So the next thing I want to talk about is use a 3 dot PhP。

 and that is really just combining all these things together， so I have the add code here right？

And then I have the delete handling， the delete handling。And then， I have。The HTML。

 so let's just bring user 3 up。It's like doing all of it together。So it shows everything。

 But the interesting thing is this little tiny delete button here。 So most of it we've seen before。

 we read and we put all the stuff out。 And then in this last field。

 right here in this last field right there。

![](img/9c63b18d293474067bd766f7ff20ea68_28.png)

![](img/9c63b18d293474067bd766f7ff20ea68_29.png)

Pry easier if I just in view source and show you what it looks like。In this last field。I put a form。

Let's make this a little bigger。Make it bigger。The last， So TD is the last column。

 and then slash TD ends that。 And in that table is a little miniature form。

 It's a method equals post。 input type equals hidden。

 hiddend input fields don't show userite equals 3。 And then I have a submit button that has a string Dell with a name equals delete。

So。This form has actually  four， four forms on it。 There's。

 I mean this this page has four forms on it。 There's a form。 There's a form。 There's a form。

 and this is a form as well。 And I can tell which of these buttons was Pat was pushed。

 And that's why I named。I named this one deletete。 So I know that that's a delete。

 And then I have add new。And I can also tell up in this code whether or not it was a delete that I opposed or it was an ad post so that ad post code is right here。

 And it looks， if it is a delete， none of these things will be set。 E password won't be set。

 if it's if it's a delete， then an name password email will won't be set。 but user I D will be set。

 And remember， I'm putting user I D in here。As a hidden value。

 which is the primary key of the user I D。 So how do I construct that text。 Well， it's pretty simple。

 I have the table TD， and then I print out the form。 This is just text。

 hidden user I D name equal name equals user I D value equals。

 And then I concatenate the actual row user I D。 I don't need to use H millinities here because I know it's a number because it's an internal thing that I invented。

 And then input type and new line in form。 I'm just kinda constructing a form from echo statements。

 That's exactly what I do。Okay， so。If I click on Dell here。Glen is gone。

 and it came back up to the top。 So it ran here。 It came down。 It ran this bit to delete。

 Ca that's the button I hit。 And then it fell through and produced the table。 So for us。

 it looked like this just vanished。 So we'll make a new one， Rohita。嗯。You missed that E to you。

Pass her to some stuff and we'll add and poof。 it shows up。

 So that time I pushed this and this post code。🎼Triggered instead。

 And so I can have different forms doing every different thing here。 And it all just kind of works。

 And so that is user 1， user 2 and user 3， walking through。 Hope this helps chairs。



![](img/9c63b18d293474067bd766f7ff20ea68_31.png)

![](img/9c63b18d293474067bd766f7ff20ea68_32.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p154 65_04_05_在工作流中处理逻辑.zh_en -BV11y411z7Dn_p154-

![](img/d6efec3709d028649ba350d10d764029_0.png)

Handling logic in Github actions is kind of tricky。

 The Yamal configuration formatting doesn't allow you to try to condition certain things。

 So say for example， you want one step and say well if certain condition over here is correct then go to the R01 or just failed the job So that's problematic in because like it doesn't allow you that flexibility right it's inflexible there an important constraint but sometimes you have to and the strategy that I want to show you today is by running an external script。

 so you can actually run an external scripting include in your repository So I have a very simple brand new Yamal workflow here or Github workflow a Github action workflow here I've called it bash script I'm going just trigger it manually and the jobs are going to run on to latest I'm going to clone the contents of the。

itory and then run a batchsh script I'm going to pass in a secret token。

 this C or GiHub that token that is in curly brackets that comes from the setup from Github actions itself that is a special token that Github will inject always and by using the dollar sign and the double curly brackets that means is a variable So behind the scenes Github is interpoolating that and producing the actual token。

 the secret。 So then what I'm going to do is I'm going to run this that Github workflow test that S I haven't created that and we'll see how that looks in a second。

 Allright so I'm going to commit this changes and I am going to say create script yao that looks okay and then I'm going to create a na file So I'm going to say I'm create a new file I'm going to say test that S。

put user。呃。We can say bean bash here。 and hopefully that works。 And we can actually say。

 echo working from。A Github action right so just just to test it out if it works when I commit the changes。

 I'm not checking anything and now I'm going to go to actions and I'm going to see now my batchsh script is right there I'm going to click it and I'm going to be able to run this workflow manual because of the workflow dispatch I'm going to click that and wait until this appears right here。

Okay， so that's running。 The bash script is running。 This should be pretty fast。

 The batchsh script was able to complete。 And if I click that I will say working from a Github action。

 perfect， So but you might say well that's really not doing anything。

 It's not checking anything It's not checking if the script is there how can we make this actually check that there's something going on。

 So yes， we can we can definitely go ahead and do that。

 and the way we're gonna do that is by going and making that check by writing some some bash。

 So I'm going to go back here and I'm going to go to the that Github workflows。

 so far it basically it basically works。 right so it basically works we know we know that we know that that works。

 So let's go ahead and edit this and let's try to do some bash here and we'm going say if the condition is the condition。



![](img/d6efec3709d028649ba350d10d764029_2.png)

![](img/d6efec3709d028649ba350d10d764029_3.png)

The variable is C token。 it's actually C secret token。

 So let's let's better get this better get this correct。

 So I'm going to say I'm going to say that this should be actually。With。With quotes。

 double quotes there， so I'm going to say e。If that's correct， bash is very tricky to get right。

 if that's correct， when I say then we're going to echo。We were good to go with the secret token。

 and then。And then otherwise， we are going to say we're going to say， well。

 we don't have that secret token， so we're going to say we don't have the secret token。

Can't continue。And then we can do an actual exit exit one and we're gonna force an error there right so I'm going commit the changes I'm going commit the changes again and I'm going go to actions and I'm going trigger the batchsh script again and'm going to run the workflow click the run the workflow and wait until that that appears that should work。

 we'll see what's the output So why do we have why do we don't have the secret token well。

 because once again I got the bash slightly incorrectly so let's fix that one time once more and that dashes z means like if it doesn't exist So we have the logic here backwards So let's actually put this right here and say if it's not if it's not said then we have a problem otherwise we're good to go So I think dash should do it we's going to go back and the beautiful thing about this is that we can go back to our action。



![](img/d6efec3709d028649ba350d10d764029_5.png)

![](img/d6efec3709d028649ba350d10d764029_6.png)

We're going to bash the batchsh script to run the workflow again and this time we should be good to go。

 This is taking a little bit longer than expected， but this is the normal way that you can set up automation。

 It is actually pretty uncommon to get everything absolutely right the first time and in this case you can see that we have a green a green thing like green button right there。

 no problem we're good to go with the secret token we do have that I just had implement that kind of incorrectly with bash my bash skills are not super good so I had to do some verification there So there you go that is how you could actually implement these not only with bash。

 but with other programming languages as well including Python and why not certainly rust if you have some sort of a binary。



![](img/d6efec3709d028649ba350d10d764029_8.png)

![](img/d6efec3709d028649ba350d10d764029_9.png)
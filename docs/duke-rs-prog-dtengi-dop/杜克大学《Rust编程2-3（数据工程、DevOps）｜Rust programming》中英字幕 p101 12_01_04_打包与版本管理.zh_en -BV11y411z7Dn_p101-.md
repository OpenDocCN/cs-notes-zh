# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p101 12_01_04_打包与版本管理.zh_en -BV11y411z7Dn_p101-

Packaging and versioning are also parts that are important for any project。

 especially if you're dealing with software， when you are in a situation where there's no packaging involved or when there's no versioning involved。



![](img/4e2cb0fac3a62b80f08c4c2434394e97_1.png)

And add that or sprinkle that with the lack of source or version control。

 then things can get quite complicated so lets let's take a look here I'm on the crates that IO website which is where all of the rust packages tend to go the community packages and I' going to look for one that is pretty popular which is third which is the one that helps serialize Jason。

Now this is third and there first off like we have the version in right here。

 so why is the version important because it allows us to understand components at a kind of like version control or source control allows us to pinpoint an exact release that we can work with。

And this is important because we have three pieces right here that are following， we have one。

 we have0 and 183。These pieces right here are following semantic versioning and this is not only important for creating a version but also for installers to understand well how is this going to work what if someone says I just want version 1 like what is that0 and 83 well means that if you like version 1 and you don't care about these other pieces then this 183 could be 254 and you would be happy with that as well so it allows you to define your requirements。

 your dependencies in a flexible in a flexible way？

Now you can see that the most recent analog is has like。2026 million。

 That's that's pretty impressive and 196 million downloads all time。

 So let's take a quick look at Cer。And once you get here， well， that's fine。

 but let's go ahead and look at the repository because I want to show you next what the repository is with the release is。

So inside the repository which is actually happens to be in GitHub。

 we have the tags and with version control tagging is one of those things that allows you to aside from commits to also mark or flag or label something a point in time with a commits with something that has more meaning than checkum so if we take a look at tags。

 you can see that two weeks ago version 1。0。183 was tagged and why is this important again because it points to a specific checksum now those are the tags we also have this thing called releases and the release is actually a tag I mean you can tag pretty much anything and everything and that doesn't really mean anything other than a point in time or a label a linear label in specifically the version that commits that has happened。

But now that can also generate a release and in this case， 1。0。

183 you can see that there's something that tells us what are the things that are happened there and that was released two weeks ago so this is actually the release so it is the label that actually points to a Sha to a a check some actually these ones the label the tag。

 this is the the tag is the same as these right here so this two are exactly the same and that points to a specific point in time。

 So if I click here you'll be able to see that there are several changes Now this is important again because it allows us to pinpoint exactly when it' happening when was it published when was it released and so that others can accurately try to。

What type of version they want to use with a given type of project。 Now。

 I mentioned semantic versioning， which is crucial because it allows us to have a way to describe our dependencies and what these numbers mean semantic versioning means that this is the major version this is the minor version and this is the patch version。

 So let's take a look at sver。 org， which is actually the spec。

 the specification on what what does semantic version in actually mean。

 but instead of going through all of it here I want to go and give you like the summary。

 which is this one I talked about major minor and patch。

Major means that you make incompatible changes。 so you can see here that the actual spec has had some incompatible changes。

 They went from 1。0。0 to 2。0。0。 So if we go back to third you can see that there's V1 So if there was ever a v0。

 that means that from B0 to v1， there were some incomp backwards incompatible changes。

 That means that if you're reducing version 0。0。1 your application is probably not going to work now that v1 is out continuing on the minor。

 the minor right here means that when you add adding functionality in a backward compatibleible manner。

 okay so that's good you're adding more you're adding extra stuff with minor but that's also backwards compatible that means that 2。

0。0 will be compatible with 2。1。0。 So that's not breaking because the major still2 and the mine is increasingly you know it's increasing。

 but in a compact compatible manner， things are not going to break if you continue to use two。

 So now you can see why this is important because you can start declaring your dependencies in a way that is understandable。

 And finally， the patch version when you make backward compatible bug fix it。 So if you're making。

 oh， like there's something that was not quite right。

 we need to make a quick change because this thing is broken。 Well， let's fix it and bump this to 2。

0。1。 if we go back to third， you will see the 183， had to change here。

 support decizing with an equivalent representation。 So it seems like there was something there。

 let's take a look at 182 render field analysis in a sort in error messages。

 So there was a fix actually， and they decided to bump that。 Now this semantic version in。

mber is not always follow to the T and developers might choose to you know keep implementinging the major one in an indiscriminate manner。

 but best to follow semantic versioning adhere to these type of kind of like rules so when you're releasing and making changes and again。

 why is that important because it allows you to roll back to see when when these things happen and to publish them in a way that your users can make sense out of what is exactly the meaning between one release and the other。



![](img/4e2cb0fac3a62b80f08c4c2434394e97_3.png)
# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p23 23_01_08_Rust高级模块使用.zh_en -BV1Hy411q7Zm_p23-

![](img/d97a4500e25c7100906348c56c3bd284_0.png)

One last thing that I want to cover with modules that we haven't done yet is that so far everything has been in Lib Rs。

 but what if you wanted to put things on uT that Rs like I'm doing here you can definitely do that so let's take a quick look at what's going on here and you see here that I have like one function and module definition so that' that's good before releasing in module definitions and how those work but so far those were in Libs Libs is a special it's a special file in rust。

 So anything that declared there is automatically part of the package but what about uT well if we go and say use block rs utL then that's not going work because we're in Lib thats it says unresolved import so that's not quite good if we go to main thats and we say。

Use block R u that will also now work and will' get unresolved import。 So why is that， Well。

 unlike Python， you can in have many different files。

 but those are not going to be pulled in unless you explicitly pull them in。

 So let's let's do this is one way which I think is pretty straightforward go to Lib that R。And say。

 ma， you till。 So if I say these， that means that rust will pull everything in。

 So if I go to back to main Dar Ar， I can actually say， use blockl a rest。Uil。

 and I will get this curly underlined because U is private。 so I can really use it this way。

 I would have to make some changes to make that publicly available。 However。

 we can fix this if we say mod u。 So I mean， that's fine， can you can do that。

 if you want to make it publicly available。 But if you don't you put it like these main that would still complain。

 So we wouldn't be able to use it like that。 However。

 as I was saying if I go back to Lib that R and I wanted to use some of the u stuff I can being private means that I can still use it within my library。

 but not externally is not exposed。 Like I don't want anyone to use it， that's certainly fine。

 So if I go and put it inside one of these functions。 So say for example， this one。

 I can say u and I have the example call there and that will certainly work no problem。

 Now if I go back to u。That's that example， but what if I want to use system and then call now this is unused and I'm making these publicly available。

 so I do have publicly available this module called system So how does that work if I go to LibarRS that means。

That I'll go and say system and then call like that。 So now that system right here。

 it's coming from u thatRS。 So if I go to u thatRS， it is right here。

 So those are two things that I wanted to cover。 I know it can be a little bit confusing。

 just remember that just by defining things in a different file does not mean that it will automatically work。

 if you put them in the Lib thatRS， it's a special file， yes。

 it will work and and then you can you can use it that way。



![](img/d97a4500e25c7100906348c56c3bd284_2.png)
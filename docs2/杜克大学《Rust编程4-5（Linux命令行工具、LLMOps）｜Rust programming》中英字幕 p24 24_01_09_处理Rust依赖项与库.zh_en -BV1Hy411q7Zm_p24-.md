# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p24 24_01_09_处理Rust依赖项与库.zh_en -BV1Hy411q7Zm_p24-

![](img/13020f4b5a2399ca8f27401fe0309d37_0.png)

So far we've seen how we can use cargo to create binary packages。

 but there's also the possibility that you may want to create a library。

 a library that you can actually publish and make it shareable across other binaries as well so avoiding repeating some codes so let's try let's see what are the differences and I'm going to move here the Exper and let's try it so by default if we say new CLI。

And then you can see create binary application C I package， but we can do Cargo new。Library。

 but we can say dash， dash lib。Let's see the difference。 So main difference。 this kind so far。

 it changes the the output from binary to library。 But what does that look like。

 So if we say poke around the source， we'll see that the CI will have main that S。

 but the library will have。Only lid that R and you can see here that we have different code。

 So that is something to keep in mind when you are trying to define exactly what you're trying to do with cargo or you're going to use an executable so libraries don't have a main that R a main function and entry point because you're going to reuse some of its components Now aside from that we're going to be talking a little bit about dependencies as well we've seen。

 for example that you can do dependencies list like that with the name of the dependency first and then the equal sign and then the version but there's definitely more more to it that you can do here it's worth noting that this addition here。

 it's about the rust code that you're going to be using the rust version。

 the addition of the version so you could very well put 2008。

In here and use that now the the latest or one of the latest one is 2021。

 so we're going to keep that now for the definition you can have even authors here which we haven't tried before so you can say something like these and then。

And then， and then an email over here， which would work perfectly for the authors。

 And you have many different ones。 This is important。

 especially when you are going to publish your project。 Now。

 beyond going back to the dependencies beyond doing that。

 you can definitely have ranges and define them as。You can say greater than or equal than0 that8。

 So this is you're going to start seeing some similarities with other their package managers。

 especially if you're coming from Python， this might be a little bit easier to graph。

 So so here we're saying hey， anything be from。From0 to a0。

 but lesser than 0 than  so it allows you to constrain more what you are going to be working with。

 but there's a couple more options that I think are interesting。

One is that you can definitely have depend penencies installed from Git。 So in this case。

 we have clap in search Jason and what happens if for example。

 I wanted to get search Jason from its Github repository in this published version is not what I want so I can I could do something like let's get rid of that one and say Jason and I could say Git and for that I would say httPS Github do co I don't I'm not exactly sure if Rs is the actual repository for for search Jason。

 but that's fine。 let's just assume that it is so I can autocomplete that and that definitely is how you would do that。

 So that that is definitely something that you can try and beyond beyond Git you could even have certain a。

Like adding the actual branch if you if you were to say， for example。

 use a different branch you would add that there as well。

 Now I'm not gonna go into those details yet。 but there's one more one more way of doing this that you might want to be interested in and it's useful to know So let's just say for example that you're the author of search Jason or or that your contributor and you're fixing a bug in your code and it's not published yet。

 I mean you could you could use definitely GithHub or the Git URL and get that from there。

 let's just assume that you have it locally So instead of using Gid you could do something like the find a path。

 So let's just say for example， search Jason has has been on your。

On your path its been cloned locally and you're making the changes。

 you can see these obviously fail because I don't have these working right now like I didn't clone search Jason。

 but if I was this would go one directory up and install search Jason so I think those are very good very good ways on how to deal with dependencies in a more involved way and has different extra things that you can try。



![](img/13020f4b5a2399ca8f27401fe0309d37_2.png)
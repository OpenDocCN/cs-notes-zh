# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p52 52_03_06_PyO3项目架构图解.zh_en -BV1Hy411q7Zm_p52-

![](img/1a48efcc31a4bd90888af307e66ab5a3_0.png)

Yeah。

![](img/1a48efcc31a4bd90888af307e66ab5a3_2.png)

Here we have the diagram of a pi 03 rust Python CI project。

 So this is more of a realistic style of a project that someone would implement the heavy logic and rust。

 So this could be the computationally complex things like numerical operations or maybe some hardcore data frame type operations or even using some MLlops capabilities。

 whatever it is， you're doing that is going to require the core features of rust。

 which is extremely good performance。 one of the best performing languages in the world。 Now。

 if we look at the rust code here， you have to build up the logic。

 And then when you expose the logic， you can see here that it's only a few lines of code to actually create a Python module。

 So this is the key component in your rust code is you build a function。 In this case。

 we have Lib pcalc Ci。 And then what we do is we return back this p result right here。 Now。

 the case of each。Of these functions。 It's pretty straightforward to understand what they're doing。

 We're building a calculator here。 So you sum numbers， you add a string。

 you subtract a string and you divide a string。 So once these are all populated。

 what I like to do is create a make file to make things much easier。

 So I think many Python projects that are pure Python would benefit from a make file。

 but also the integration of both rust and python is， in my opinion， a no brainer for a make file。

 because it includes many of the complex things like copying a shared object file to a location。

 etc ceter that are annoying to have to type manual。 So in this case。

 once we've got a rust code set up， I would run the make file command。 So it'd say make build。

 this would then copy the artifact of the build from rust， which is lib pcal underscore Ci do So。

 So once we have this S we're ready to go。 All we have to do now is figure out how to integrate it into some。

hon Now one of the better ways that I would recommend integrating Ru code is Python Fire。 Now。

 Python Fire is a library from Google that is very interesting because it takes the core nature of Python So classes and functions and lets you actually ingest those without having to write any boilerplate command link tool code。

 So in this case， we would actually build out a class called calculator。😊。

One of the methods in the class would be divide。 And I just call that Ru code that I created earlier。

 in this case， divide as string， nu1， nu 2。 And then at the very bottom here under this section of the Python code if under under name under under equals main。

 you would say fire dot fire calculator。 At that point。

 I have access to every single one of these methods in the rust module。

 And then from the terminal here， look at this， I just say dot slash cc dot Py add 2 and 2 dot slash cc Py subtract 5 and 2。

 So I think this formula。Is in my opinion， probably the most effective way to get started with integrating rustt in Python is to let all of the heavy lifting be done by the part that rust is good at and then let the heavy lifting be done by the stuff that Python' is good at。

 which is there's many of these really fancy libraries that allow you to write almost no code。

 And so by wrapping Python fire with rustt， I think it's an amazing combination for Python projects and I would recommend this workflow。



![](img/1a48efcc31a4bd90888af307e66ab5a3_4.png)

![](img/1a48efcc31a4bd90888af307e66ab5a3_5.png)
# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p135 46_03_03_解析系统命令输出的策略.zh_en -BV11y411z7Dn_p135-

![](img/63ac50af776cc95e17218b2caa5ef4e1_0.png)

We've talked a little bit about the complexities of parsing an external command。

 in this case it was DF with this wrapper， this rust application that wraps the DF command。

But what so those are the complexities but what are some of the strategies so let me give you a couple of things that I think are useful to know when you're dealing with wrapping an external command So first off again it depends in this case we have a command line tool we are parsing and'm going to scroll here all the way to the top where parsing options and arguments and you can see those are right here。

 I haven't gone into detail as to how this is working but in essence it is a command line tool it is a command line tool it has circle like has like a subcom it has like flags here like path is a flag actually like defaults to empty string。

And then the approach with that might be slightly different than when you are actually wanting to create a library。

 if you're doing a library which will provide information output that other tools can use then you might consider both approaches of trying to provide more flexibility and both approaches。

 I mean， either break immediately or provide a useful weight for the handler。

 the consumer of your call to deal with。The problem so if I scroll way to the top here。

 we've talked before about the running the command in this case。

 I am returning a string and I'm not letting the consumer of this function。

 decide what to do about it so I'm oversimplifying here， because I know that's what I want。

 but if this was a library returning a string wouldn't be a good strategy because I'm handling what I'm handling the error here and always regardless of what happens even if its if it's a successful output or not I'm going to always return a string。

That is fine for this use case， but is not always the case。 So if you were building a library。

 then returning a string would be kind of annoying for others that want to actually handle an error。

 they might want to say hey， if there's an error， I I want to deal with the error in a specific way。

 I don't want to print I don't want to print to to the terminal this line right here is actually printing to the terminal is doing a print line call and this command fail will show up you know and then it's calling a macro here。

 which is an error that you comes from the log cr right here so you know the consumer of this might not want it like I know how I want it so because this is living in my same application then that choice is fine。

So the choices you make depend on are you making things for a library are you doing an all in one application that is has its components in this case this is Lib atRS。

 but it has its components for the same application well your decisions are going to change so that's one consideration to have one strategy that you can implement there and not necessarily do this handling right here。

We will talk about errors later how to handle them nicely， but that is it for the run command。

There's other things that are useful here， you can see that I'm splitting naively on white space。

That might cause problems。What happens if you have something that has white space in it then you might get into trouble so you might want to have something more more robust here I'm splitting and tag consideration needs to be in place when you're trying to define what types of commands are going to go inside into this run command function in this case I know it's like a single argument actually a single executable I'm not passing anything else so this would be these arguments are going to be pretty straightforward。

 One of the things that I want to mention is that I have run Df which is the command and in here I have I need to script scrolling a little bit more I have a parse thef so splitting out the parsing from the actual the actual run command is a good idea because then you can deal with not only the logic of parsing all。

This output， but you can only you can get to concentrate only in the input that might be a buffer and that might put you in a good place。

 this is also way， way easier to test because your input can be you can be anything in this case is a string and you can accept the string and no problem and do their testing and not worry about calling a system system command So that is something that is useful in this case you can see that I'm parsing these type of output now if you wanted to and I mentioned this before。

 but if you wanted to parse the output from different systems that slightly vary then you might want to have like a separate parsing for for OS10 so say for example。

 an Apple computer which is kind of like what I'm using right now in one that is Linux so you might want to even split this one into other implementations that will allow you to。

Do all that processing with different systems in the back end so those are also other considerations that you may want to have and also you want to consider the how naive you want your system like the pars here is like very very naive I'm saying I'm blindly trusting that this is never going to fail。

And I'm blindly trusting that there's always going to be a file system here and that file system is checked here。

 so if the line starts with file system Im par I'm not going to parse any of these right so what I'm going to do is I'm going to concentrate in these ones because these ones are known then what I can do is make sure that these are my keys when I'm building that JON output that JON blob。

If the line， this is a good one if the line is the length is0。

 then I'm continue because that means that if there's anything below that or previously like won I won't parse that and I won't break my parsing。

Now， parsing。Can be very brittle like you're consuming output from an external source。 Now。

 one way to do it is well do it like I did， where I'm just splitting on white space。

 So I'm splitting on every single one of these partss。And that might be fine again for my use case。

 but if any of these had white space then I would be in trouble and I would no longer be able to split on white space and would be this would break all of the parsing So imagine if the path here had like a space in it that would be that would get me into a problem where I would be broken I would produce a broken parsing so one of the things that you want to do is analyze the type of output that you have and sure if you want to be naive like I'm doing right here with file system and spliting everything into white space like I'm doing right there sorry about that like right here and then consuming each portion like that then sure yeah you know like that's acceptable but if you want to have something more robust well you need to make sure that your assumptions are right in this case none of these can have white space within。

So those are some of the things that you need to consider， some of the strategies that you can apply。

 splitting parsing into two if you have to support more systems。

 have a separate function that will run that command。



![](img/63ac50af776cc95e17218b2caa5ef4e1_2.png)
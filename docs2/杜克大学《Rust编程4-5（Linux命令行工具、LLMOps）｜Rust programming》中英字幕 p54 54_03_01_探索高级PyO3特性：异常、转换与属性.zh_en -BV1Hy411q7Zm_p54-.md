# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p54 54_03_01_探索高级PyO3特性：异常、转换与属性.zh_en -BV1Hy411q7Zm_p54-

![](img/62633a2777beb85042a5e87475e96844_0.png)

Yeah。Here are some key features of po3， which allows you to use rust and Python together。

 First up here， we have rust extensions in Python。 Some of the things that you can do include allowing developers to write a Python extension in the rust programming language。

 So this means that you can do a high performance save code。

 and you also can use it seamlessly in the Python environment， and the packaging is always excellent。

 when you work with rust。 We also have rust calling Python。

 So in the case of the reason for this is that there are many readability issues with Python where it's really simple to look at the code。

 There's also lots of legacy code in Python。 you may want to interact with and the libraries are extensive because the languages around for 30 plus years。

 it's a very popular language as well。 So the idea here is that by。

Allowing rust code to call Python directly， it allows you to do things like call scripts， functions。

 manipulate Python objects。 We also have the ability to work with native types here as well。

 And in the case of native types， you can use a Py di py list py string right So it's really just a wrapper around exactly what you're comfortable with already in Python and you can use them as native rust types。

 And this is a way to provide a seamless way of converting the data between rust and Python。

 So really you're going to be right at home。And last year we also have the ability to work with exceptions。

 so for example， Python exception handling would be a great thing to you know first build out in rust depending on what it is you're doing So Py3 provides tools for working with these python exceptions from rust This could mean let's say propagating Python exceptions to rust and then raising that python exception from the rust code So you know few things you could do with that。

 for example， as you could create a scenario where rust function calls a Python function that raises an exception and you could handle that in rust So there's lots of integration features here by using rust and Python together and in fact。

 it could be a legitimate replacement of a lot of the Python C interaction that has been historically done。

Rus is a modern compile language， and it works very well with generative AI coding tools。



![](img/62633a2777beb85042a5e87475e96844_2.png)
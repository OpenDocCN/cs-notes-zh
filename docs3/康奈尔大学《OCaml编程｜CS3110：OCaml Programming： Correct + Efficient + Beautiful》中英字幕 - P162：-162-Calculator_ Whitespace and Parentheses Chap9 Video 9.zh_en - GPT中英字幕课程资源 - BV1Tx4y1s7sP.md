# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P162：-162-Calculator_ Whitespace and Parentheses Chap9 Video 9.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

As a final test case here， suppose I wanted to allow white space in between the tokens of my language。

 so I can say 10 space plus space one， and suppose I wanted to allow parentheses to force the grouping of operations as well。

Let's add both of those into our Lexer and parser。 There's nothing to be done for evaluation of。

So I've added two more productions here to my Leer for left parenthesis and right parenthesis。

 which will create tokens L Parin and RPin。And to my parser。

 I've declared those tokens and added one more form for expressions here。

 which when it sees a left parenthesis， followed by an expression， followed by a right parenthesis。

 just returns whatever the result of parsing that expression is。

 it's throwing away those parentheses and representing them implicitly in the shape of the AST。

 Finally， to skip over white space， I'll add in one more production here to my Leer。

So I've defined what white space is， I've chosen here for it to be any space character or any tab character and any mix of those that's one or more。

 that's what the plus means here， one or more of those。😡，And when my Leer sees white space。

 what I want it to do is to not return anything， but to recursively call itself so that's the same read showing up here as it is in the rule up here。

😡，On the Lexing buffer， which just means basically skip over the white space that you've seen and then return the next token that you can find。

Now I can check to see whether my test case passes。And indeed， it does。



![](img/4d6ce272081e136322554ef15f9ba4b1_1.png)

So now I've implemented my entire interpreter for this little calculator language。😡。



![](img/4d6ce272081e136322554ef15f9ba4b1_3.png)
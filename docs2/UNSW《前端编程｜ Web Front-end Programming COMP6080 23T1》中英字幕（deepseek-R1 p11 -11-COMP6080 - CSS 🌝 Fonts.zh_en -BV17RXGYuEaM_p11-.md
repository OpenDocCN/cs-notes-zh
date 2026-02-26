# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p11 -11-COMP6080 - CSS 🌝 Fonts.zh_en -BV17RXGYuEaM_p11-

Hi， my name's Hayden， and today we're gonna be talking about C S S fonts。

 You probably haven't thought a lot about CsS fonts。 And in particular。 so far。

 the most we've covered is that if you have a particular span。

 you can come along and change its font family。 We've also played around with a few other things like font size。

 font way， text decoration， things like that。 But today。

 we're gonna focus on just extending our knowledge slightly in two particular areas。

 which is the font family and the font size。 So firstly， on the font family。

 we mentioned earlier that the font family comes from the operating system。

 And no matter what your computer you're on， you should be able to look up the fonts on that computer。

 So I'm on a Windows machine right now。 And I can actually see just by opening up my settings。

 all the different fonts that are on that Windows machine。 And if I go and find aerel， for instance。

 you'll see that。😊。

![](img/09ab62113b9f57ce43670c0ec5b96b28_1.png)

![](img/09ab62113b9f57ce43670c0ec5b96b28_2.png)

Ariel has a whole bunch of different font weights。 Yeah。

 like bold and bold italic and bold and narrow bold italic and black and a whole bunch of other things。

 It also has a very different font sizes。 And it gives you samples of all of these things。

 So it's actually the operating system providing this information。

 And that's why when the Web browser loads a page with a font。

 such as let's look at agency FB and see how this looks。 Usually。

 you want to use quotes when there's a。

![](img/09ab62113b9f57ce43670c0ec5b96b28_4.png)

A space in the name， so you know agency FB is there and it's like， hey， I am Re font。Now。

 one thing you have to be really careful with is when you select a font。

 you either need to make sure that that font is nearly certainly installed on everyone's computer or alternatively you need to have the font installed yourself。

 and this is another kind of last decade tech that's existed where you can simply go to Google fonts。

 which is just a website with a bunch of free fonts and you can find a font you like and you can actually kind of package it up in your web page so that it's not relying on the person who's using your website's computer so let's have a look at this font baby baby Loica interesting So watch what happens when I type in baby Loica here。

The web page doesn't really do anything with it， in fact， it kind of ignores it。

 which is why it defaults back to Time new Roman。So you think okay well Id really I really like that font。

 I'd really like people to use it， So what you can actually do is you can actually download that font right which will give you a zip file and you can open up that zip file and extract it into your folder and I'll just do that now。

😊。

![](img/09ab62113b9f57ce43670c0ec5b96b28_6.png)

So you can see here this is the zip file I downloaded and it's got this font called Babylonica regular do Ttf。

 And I can just go and drag that into my folder here。 So now my folder will have that font。

 Now I'm just gonna restart my city little editor here because it doesn't like to work And you can see my font is right there And then you think okay well how do I integrate that So now I do maybe and let's imagine you've forgotten。

 you think I remember hateden talking about this So you say like custom font or like import font family or something like this and we'll write Css so that we don't get too confused how to import fonts in Css and we find a really simple stack overflow article and you'll see that it approaches it in a very interesting way。

 you actually have to define the font separately by going at font face and then you say font family and then I can call this anything I want like Babylonica and then I need to tell it where the font comes from and in this particular case because my font is in the same folder if it was in a subfold。

 maybe I'd need。

![](img/09ab62113b9f57ce43670c0ec5b96b28_8.png)

To ride it out like this dotttf。But in this case， it's just in the main folder so I can just write Babylona regular。

 So this section here defines what Babylona is by sourcing it from that file。

 And then when I come to use it like that。 it knows to look look that font face up。

 So now when I refresh the page， I get this beautiful font here。

 And the cool thing about this is because this font is packaged with the page。

 it means that anyone on any browser can get this really exciting font。

 So you know if you want to build a website and you want this beautiful welcome message like this。

 You can just do that， you don't need to save it as an image， that was kind of the classic way。

 things used to be done in the past was that you would you would literally have to like convert this to a PG and then like paste it on the page。

 and that was bad for a bunch of reasons it made the page slower，😊。

It's bad for Se because Google couldn't scrape what that image was， et cetera。 So that's font family。

 and that's custom font faces。 The last thing to quickly touch on with fonts is on。Font sizes。

 Now there's a whole bunch of different ways to declare font sizes。We talked a little bit about EM。

 but let's have a look at the different methods。So。😊，嗯。It's's a very， this page is quite long。

But essentially， they show that there's a few ways you can。You can do it by Pel。

 you can do it by Ams。You can do it by probably RMs， Rs。

 you can do it by EX there's like a whole bunch， you can do it by percentages。

 There's lots and lots of different ways。 And if you Google it。

 you'll see lots and lots of information aren't lots and lots of articles but there's usually a fairly simple one that is best and it's not pixels pixels is one way to do things。

 you pick you know 20 pixels，40 pixels oops that's in the wrong spot。

 you pick you20 pixels 40 pixels and that kind of scales it up。

 The problem with pixels though is you're explicitly defining you know pixels are kind of really useful for layout because pixels literally mean a pixel on the screen。

 and this can be really challenging for devices that maybe have you know higher Dpis or accessibility options to increase the size of the text。

 you don't want your kind of pixel definition to like screw things around。

So we try and steer away from pixels because it takes the power away from the web browser to solve the problem。

What we prefer to use instead is usually EM we talked about this before。

 or even better RM so EM is these are relative measurements and these are really important because what one EM says if we go look at the docks right。

 let's go back up the top and look at EM。😊，A is defined as。

A multiplier of the font size property of the element in which it's used so when we say 2am we're kind of saying two times the default font size it's not only kind of easy to read and understand because you can be fractions as well but it adds relativity to everything which is really important because if you kind of have outer elements with you know bigger font sizes then things just kind of trickle down and because you're kind of saying this is two times the normal size you're giving the kind of browser a chance to define what the normal size is though a much more common one that's being used more and more these days is reM and REM is designed to。

To kind of circumvent the compounding problem。 And what that means is that let's have a look here。

 right， Let's wrap this span inside a div。And I'll call this Gib say body。

And everything inside that div， if I go， you know， the body's a terrible class name。

 but if I say here， font size is 2 AM。What happens now is that these things basically compound off one another。

We like。You know so the 3am is like three times bigger than what I should be and what I should be is defined by the parent and the parent is already two times bigger。

 so you get this multiplying effect or what they call a compounding effect whereas RE is like relative and it is a little it behaves a little bit better on pages in the sense that1 means one times the relative size like globally So what this means is that you can kind of just say that the entire page has a default font size for these elements and RM is relative to that whereas EM is relative to that times whatever is happening with the parents。

 So REM is probably the best attribute to use generally there's probably not a large reason you'd ever want to use anything else so stick to that but if you you can just Google PT versus pixels versus Em versus R you'll see a whole bunch of you know blogs。

 articles descriptions that like to take you through it and explain it in much much more detail they'll often。

Saay that most are bad， some are good and they'll generally push you towards some of these relative relative ones like EM or REEM。

 but short story is check out REEM it's probably the way to go hopefully that was a nice subtle intro into font and gives you just that little bit more background so that you can use it more confidently。



![](img/09ab62113b9f57ce43670c0ec5b96b28_10.png)
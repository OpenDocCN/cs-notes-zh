# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P13：-14-Pillow - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

Well hello one and all and welcome to our short on pillow which is a library for manipulating images within Python So I have here a file of an image called in dot JpeEg and this is the great wave of Kanagawa by the artist Hokuai Now if you're familiar with this image it should not be upside down like this and I really want to flip it over so I can see exactly what this image holds Well thankfully I can use something like Python with the pillow library to do just that to manipulate this image and rotate it so it's going to be right side up instead so let's go ahead and write a programmer do just that I will type down my terminal code image do Pi。

😊，And here I want to give myself likely a main function to write my program in and I'll call main down below Now if I want to use the pillow library for manipulating images in Python。

 I can access it by doing import PIL。Now really， I want access to some particular class inside of this pillow library。

 one called image， more on classes in a future week on object oriented programming。

 but for now think of a class as a bit like a template something of' representing information in this case image。

 so I could access some class that pillow providesdes me by typing from PIL， import image capital I。

So the pillow library gives me access to something called an image that I can use to represent and manipulate images that I might have on my own file system on my computer。

😊，So using this image of class， I can actually go ahead and try to open up an image and I can do so using a method of the image class at one called open。

 I can access it using image。 open and I'll give us input to open in this case the name of the file I'm hoping to open now in Python very similar in spirit to me clicking on this file on lefthand side in Jpeg and seeing what's inside of it。

 open goes ahead and opens that image for use within my Python program here。Now open。

 this method here returns to me an image object， so I'll go ahead and use this IMG variable to refer to my image that I have now opened using the pillow library。

And similar to other files， we open in Python， it's good practice to close them。

 when we're done with them， so as a test here， I've opened up my image， but I should now close it。

 so I'll type img。 close this method goes ahead and closes my image after I have opened it。

Now while we're here， we might have seen before that it's maybe not best practice to get in the habit of defining explicitly and we're going to open and close our images in part because we'll often forget to close things later on so why don't I do this instead I'll go ahead and use with with image do open as imG and as long as I'm indented within this with block。

 I'm now able in this case to see my image being opened and I can run all kinds of functions on it as well So as long as we're indented。

 we have access to this variable called IMG， which is in this case the image I've opened called in do JpeG so what could we do with it well one thing we could do is get a sense for the size and the format of this image thanks to various attributes of this image object so I could for instance。

 try printing IG dot size and this actually gives me access to the size of the image in。

I could also print img。 format， and this for me will show me the format of the image like what file type it is that I'm not sure initially。

So I'll go ahead and run Python of image。py and hopefully fingers crossed we'll see。

Some information down below， so it seems like this image in dot JPEG its size is 1052 by 720。

 so maybe 1052 pixels across and 720 pixels up or vertical and this image's format seems to be a JPEG which makes sense because it has the dot JPEG file extension here。

So we can have access to various properties of this image。

 but we can also manipulate it using a pillow as well one thing we could do is very simply rotate it so here if we look back at our image in dotchepeg we'll see it as upside down so we maybe want to rotate it another 108 degrees to put it right side up。



![](img/0510ec3decf8ba05dee13a20e3dc5550_1.png)

![](img/0510ec3decf8ba05dee13a20e3dc5550_2.png)

Well， in image dot pi， I can do just that， I could say something something like img。

roate and I'll add in the degrees I want to rotate this image in this case 180 to put it back right side up。

 I'll then store this updated image in the imG variable and now if I want to let's say save this updated image I can do so by calling img。

 save and giving some particular file name like out dojpeg just like this。So to be clear。

 I'm opening in do JPg rotating it thanks to pillow with this rotate method and then saving it again。

 thanks to pillow with this save method， I'll go ahead and run Python of image dot pi。

And we'll see nothing in the terminal， but you might have seen over here。

 I now have a file out dot JpeEg， I'll open it up， and we'll see this is that image。

 but now right side up。Oh what else can we do One thing we could do is apply filters to images have a bit of fun here。

 we could rotate it certainly to fix the image， but along the way maybe apply a fun filter to learn more about the image well one filter we can apply is a blur filter make a look a little bit more blurry and to access image filters in the pillow library I can do this from PL import image filter so image filter here is a class that I can then use to apply various image filters and I can actually apply them to my image by using a method filter so I can type IG do filter and then give as input the filter I want to apply and by convention here if I want to get the blur filter I can type image filter do blur in all caps。

I'll now save this image， really well I will update， let's say。

 my image in the IMG variable and save that updated image using the save method later on。

 I'll type Python of image。 pi。

![](img/0510ec3decf8ba05dee13a20e3dc5550_4.png)

And let's see the updated version of out dot jpeg seems a little bit more blurry。

 when compared to in dot jpeg。 So that filter has been applied here。 What else could we do， Well。

 one other fun filter is one called find edges that quickly finds the edges of the image and highlights them for us。

 I can access that by using image filter dot find edges And now if I run Python of image dot pi or what should I see。



![](img/0510ec3decf8ba05dee13a20e3dc5550_6.png)

![](img/0510ec3decf8ba05dee13a20e3dc5550_7.png)

But again， that image rotated 180 degrees and now a filter that finds the edges of the image for me。

So much more you can do with pillowlow， but we've seen here how to open images， how to save them。

 how to rotate them， and how to apply filters， we're excited to see what you'll create with Pilow。



![](img/0510ec3decf8ba05dee13a20e3dc5550_9.png)
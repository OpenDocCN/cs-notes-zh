# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p68 08_02_04_网络套接字与连接.zh_en -BV1Kt421V7EE_p68-

So network sockets are like phone calls for computers and literally in the 1960s when they were designing the concept for network software。

 that is the concept that they came up with and that is that in a sense。

 we make a call we talk on the call and we paint the phone up and as computers were going to share data and some computers were going to have data and other computers are going to want data。



![](img/823ce2c3f85a68d2929d9fd01c35f410_1.png)

![](img/823ce2c3f85a68d2929d9fd01c35f410_2.png)

They thought oh， the way to do this is not necessarily have a permanent connection to that data because there's going be so many computers and so so many sources of data and so many computers that want to consume those data and of course in 1960 they had no imagination that there would be billions they just thought there would be 10。

000 and they thought that was a lot but they came up with a protocol that basically said when you don't have continuous permanent access to data。

 you actually make a phone call， you know where the datas at， you kind of say you dial up。

 you grab this stuff， you get it back and then you let the connection go and so it means that with billions of computers each talking to each other。

 the network isn't so complex and so there's this connect。ReTalk， disconnect， connect， talk。

 disconnect， and it's the way the phone system in our world。



![](img/823ce2c3f85a68d2929d9fd01c35f410_4.png)

Scals to all the people， and it's the way the internet scales to all the people that want to use that internet。

So this is。Made inside of software using an abstraction are library called Sockets。

And sockets really are computer phone calls， you know where you're going to call。

You can start the call， wait for them to answer once they answer， there is a twoway communication。

 it's kind of like a file except that you can simultaneously read from the file and write from the file。

 although it's important for the two cooperating pieces of software to know who's going to read first and who's going to write first because it's like if you know when you pick the phone up after it rings。

 we all know to say， you know hello and that's kind of a protocol who talks first as a protocol like and then the person goes like who is this and then eventually conversations happen pretty naturally you know somebody talks。

 listens， someone else talks listens and that works。

 but there's complicated protocols and you can think of this not necessarily as the browser on on your laptop or phone as talking to data on the server。

 it actually talking to another program so even when it's just retrieving a file it's talking to an application on that server and that application is reading。

File and sending it out。 and we'll see that eventually how we have to do that when we're doing things like uploading pictures。

 we upload pictures， and then we have to actually serve them back out。 We can't just say， oh。

 the pictures are there。 you can grab them sometimes not everyone can see every picture and so part of the software application decides if you are allowed to see this picture I will send it if you're not allowed to see the picture I will not send it。

 And so that's where it's a piece of software that you're talking。

 even if you're looking at a picture sometimes that software is really simple and you barely notice it but there is software in the loop。

 It's not like you just go straight to data。 it is really two pieces of computer software talking to each other and we use the Internet as that intermediary to allow that conversation to happen。



![](img/823ce2c3f85a68d2929d9fd01c35f410_6.png)

So if you read my book about the TCP IP， you'll learn this in super great detail。

Every computer has an IP address， it is a number， there are two kinds of addresses。

 there's IPV4 and IPV6， IPV4 version 4 is the one that's got four dotted numbers like you know 142。

16。42。114， but within each of those they have what's called a TCP port number。

And because this whole internet thing is applications talking to applications。

 we need to have a good way to know which application we're talking to and that's where TCP port numbers come in。

 and you can think of this as like a phone extension you know so you have a phone number and then you have you know extension 1436 and so TCP port numbers are like that so we can not have a specific address for every application but an application as an address and a port within that address or a phone number and an extension within that phone number。



![](img/823ce2c3f85a68d2929d9fd01c35f410_8.png)

And so you can look these things up Port 25 is used for email server to server communication in the old days we use this thing called Tnet。

 we'll talk about that on port 23 and so the client is on the righthand side and it might be a computer where you've got a keyboard and it's you or it might be a server that's got some mail that's being forwarded from somewhere and they all talk and they connect to an IP address in this case。

 7420828177 is the IP address of this computer and then port 25 is the extension where one computer sends email to another computer and each of the arrows in between them is a separate protocol So if you're talking to an email server you expect to talk an email protocol and if you're talking a login server or login protocol that's kind of the simplest one or a web server web server can be on port 80 if it's unseecure。

Preferred of course is HtTPS， which is on port 443 if you have a mail application like say Thunderbird that's reading Gmail it talks to ports 109 or 110 or a couple of other ones that are ways for a mailbox application to talk a protocol to a server- based mailbox to retrieve the new message or delete a message or view a message or whatever so there are these ports on servers that have protocols and then we can build software on our clients that talk these protocols the one we're going to be playing with the most in development mode is port 80 and in production mode port 443 for the HTTP for know web documents basically in web application documents。



![](img/823ce2c3f85a68d2929d9fd01c35f410_10.png)

So up next， we're going to take a quick look at the Hypertext transfer protocol。

 I also want to call it hyperpertext transport protocol HTTP。

 and that is the protocol that we talked to port 80 or port 443。



![](img/823ce2c3f85a68d2929d9fd01c35f410_12.png)
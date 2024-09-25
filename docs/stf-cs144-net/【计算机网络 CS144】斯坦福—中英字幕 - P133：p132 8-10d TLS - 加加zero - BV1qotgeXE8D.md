# 【计算机网络 CS144】斯坦福—中英字幕 - P133：p132 8-10d TLS - 加加zero - BV1qotgeXE8D

 So let's switch gears a little bit and actually let's take a look at layering and how it's。



![](img/627cbfc716011dd75ff6c27291d5a87d_1.png)

![](img/627cbfc716011dd75ff6c27291d5a87d_2.png)

![](img/627cbfc716011dd75ff6c27291d5a87d_3.png)

 implications of security。 So you've seen layering many times。

 It's a general important principle in the design of computer networks。



![](img/627cbfc716011dd75ff6c27291d5a87d_5.png)

 You've seen its benefits， separation of concerns， independent evolution， ease of adaptivity。



![](img/627cbfc716011dd75ff6c27291d5a87d_7.png)

 of adaptability to future technologies。 But it sometimes does get in the way。

 So TLS is used today for secure web transactions over HTTPS。



![](img/627cbfc716011dd75ff6c27291d5a87d_9.png)

 But it's often the case that a web server actually runs multiple websites through something。



![](img/627cbfc716011dd75ff6c27291d5a87d_11.png)

 called virtual hosts。 The domain names of all the websites map the same IP address of the server。



![](img/627cbfc716011dd75ff6c27291d5a87d_13.png)

 Clients connect to all of them with report 80。

![](img/627cbfc716011dd75ff6c27291d5a87d_15.png)

 It's not until the HTTP request comes in that the web server process knows which site the。



![](img/627cbfc716011dd75ff6c27291d5a87d_17.png)

 request is for。 The host header field of the HTTP request tells it。



![](img/627cbfc716011dd75ff6c27291d5a87d_19.png)

 For example， if you go to sing。stanford。edu and tiny。



![](img/627cbfc716011dd75ff6c27291d5a87d_21.png)

 U。S。stanford。edu， the same server。 I can configure a patch as they look up different web pages。



![](img/627cbfc716011dd75ff6c27291d5a87d_23.png)

 A patch would look inside the request， see the host header， and choose which web pages。



![](img/627cbfc716011dd75ff6c27291d5a87d_25.png)

 to serve based on that。 This can break TLS such that it can't fully work properly。 Why？

 Is it because it breaks server authentication？ Does it break the key exchange？

 Does it break randomness generation？ Does it break routing the handshake messages？

 Or does it break pre-master secret generation？

![](img/627cbfc716011dd75ff6c27291d5a87d_27.png)

 The answer is that it breaks server authentication。



![](img/627cbfc716011dd75ff6c27291d5a87d_29.png)

 The TLS handshake and secure session setup occur before there is any application data。



![](img/627cbfc716011dd75ff6c27291d5a87d_31.png)

 As a part of this exchange， the server needs to provide a certificate that binds a public。



![](img/627cbfc716011dd75ff6c27291d5a87d_33.png)

 key to a name。

![](img/627cbfc716011dd75ff6c27291d5a87d_35.png)

 But it doesn't know what name to use。 For example。

 my server can't tell whether a connection is coming in for tiny。us。stanford。edu。



![](img/627cbfc716011dd75ff6c27291d5a87d_37.png)

 or sing。stanford。edu。 So it doesn't know whether to provide a certificate for tiny。us or sing。



![](img/627cbfc716011dd75ff6c27291d5a87d_39.png)

 In my case， I have a certificate that says both。 But if I wanted to add a new host named to the server。

 say a website named www。networkingclass。com。

![](img/627cbfc716011dd75ff6c27291d5a87d_41.png)

![](img/627cbfc716011dd75ff6c27291d5a87d_42.png)

 then TLS would throw an error。 The problem here is that the session layer， layer 5。

 needs to know the host named that。

![](img/627cbfc716011dd75ff6c27291d5a87d_44.png)

 the client is trying to contact。 But that name is only available in the application layer， layer 7。



![](img/627cbfc716011dd75ff6c27291d5a87d_46.png)

 The client is translated the name to an IP address， so layer 3 name。 So here's an example of layers。

 How layer， the encapsulation functionality can cause a conflict and actually get in a。



![](img/627cbfc716011dd75ff6c27291d5a87d_48.png)

 way。
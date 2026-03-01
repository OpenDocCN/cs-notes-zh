# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p104 16_01_01_讲解如何通过双因素认证保护账户.zh_en -BV1Hy411q7Zm_p104-

![](img/011b68d96ac16fb10cd868621c989098_0.png)

Securing GitHub accounts with two factor authentication is a critical workflow for the enterprise because you can ensure that you're going to have the security best practices enabled。

Why would you want to do two factor authentication？ Well， first up。

 it's the most secure way to authenticate。 And if you use one time password applications to configure to factor off or T O TP。

 which is a timebased version， you're going to have the most secure method。 So first up。

 let's see in the UI how you do this on the right here。

 we can see there's a settings picture When you open up the settings。

 you go under password and authentication and it has a section called enable two factor authentication。

Next up， you would set up the authenticator app so you would go through here and scan their QR code。

 set that up， and then you now have time based one time password。

 which is the most secure form of two factor off。Once you've got that set up。

 then the final step in step 4 would be to set up backup security keys。

 These backup security keys would be much more secure than Sm。

 and it's a recommended best practice to set up those backup security keys。

 So once you've got it set up， let's go ahead and walk through the flow here of how it would work。

 So we see here in this blue icon user interface， the user would log in。

 and this would begin the login request。 This login request here would involve the username in the password。

 So this is the first factor in the two factor authentication。 Next step。

 after receiving the login request。 The server would check the password against the stored credentials。

 So if you can't get past this， you're not going to be able to go to the next phase。

 And that's why there's two factors to the authentication。After you've been able to be verified。

 the next step here in step C would be the two factor token generation。

 So once the password is verified， the server would initiate the2FA process。

 this would involve sending a unique token to the user via either SMS or the generation through the one time password。

And at this point， you've now got this generated in real time。

 So there's a timebased component as well， which makes it much more secure。

 Once you've got the token， the next step here would be to take that and go to the Github UI and put in that token and this would be the final layer of security once you've been able to get that verified the server would validate the submitted two factor token against the one it generated and sent and there would be a brief validation period where the token would be available during this enhanced security measure。

 So this is a very secure method for Github。Soon it will be the recommended method and required for all accounts。

 and this is the workflow in order to get started。

![](img/011b68d96ac16fb10cd868621c989098_2.png)
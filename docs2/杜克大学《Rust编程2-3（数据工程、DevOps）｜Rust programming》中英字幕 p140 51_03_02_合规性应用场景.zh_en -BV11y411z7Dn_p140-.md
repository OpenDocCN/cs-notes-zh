# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p140 51_03_02_合规性应用场景.zh_en -BV11y411z7Dn_p140-

![](img/dcd0a836332a4518499f9eec86296e44_0.png)

Compliance and Devopps operations sounds like might not sound like something that you may want to be doing。

 but in fact it is actually very useful under many use case and I'll show you one here I mean my home directory here and I am under my dot SSH subdirecty。

 this is a hidden directory in my home directory and that holds configuration for all of my SSH configuration as a configuration and this is my private key。

 my public key and some information about hosts that I contain when I'm using SSH SSH is a tool allows you to have remote logging capabilities to other systems so say for example if I want to I have a server that I call my Mac mini server。

And I can do SS and then I can be in that that other server you can see that that last logging was there a while ago and I' no longer my prompt has changed。

 so this is no longer the same as my main computer right there So that is essentially what SSH is but when or where does compliance come into play well if I exited here。

If I show you the permissions， you know these permissions have are very particular。

 You see that my private key has read right only for the owner， who's the owner。

 well that's just me and the group that I am in doesn't have either read or write or execute permissions。

 So if I change that if I if I say change the permissions and I'm going make everyone else have read permissions to my。

P key I'm going say ID RSA and I do LS ALH， you will see that now the permissions for for my private key have three permissionmissions for everyone else。

 anyone else can read it including members of my group which is staff。

 so not only myself but everyone else on the system。So now if I want to SSH to Magmini。

Look will happen。 I will get a warning saying hey， warning you have an unprotected private key file。

 the permissions0 that064，4 for users are way to open this means that others can read that and again and it tells you like it is required that your private key files are not accessible by others。

 the private key， this private key will be ignored。

 So right away it tells you tells us like this is not gonna work by the way。

 this has bad permissions and this has happened to to me multiple times when I'm creating moving。

 modifying keys or making some changes and then I get into these situation。

 So compliance in this case could be make sure that certain files are at a specific certain permissions when I control C out of here。

 let's see we had change we change the permissions on ID R to for everyone else so we can say。

Change mod， let no one else have permissions to read it。

And now let's add permissions for me to read ID RSA。 So if I clear these and I do Ls dashel。

 we should be good to go for ID RSA So if I try to assage with Mac mini server。

 everything works then again， so this is one compliance aspect。

 I can check and try to enforce that certain files are at certain permissions usually for scripts。

 you might want to have something you might want to read to create something that make sure that these things are at the right permissions otherwise。

It can advertise， hey， you know these things are not in compliance。

 there are certain problems that need to be fixed， fixing them automatically is a completely different level of automation and tooling。

 but this one right here is good enough to have some sort of understanding。

This is one aspect of configuration or compliance， the other one would be you know checking for files that should exist and by checking for files you can also check if certain things are installed so if I go to Esy and I type a S you can see there's tos of different configuration files right here and all of these files are fine but if you say hey you know like there should be always an nfs。

com file in there and if it's not there， then we're going get into trouble you could effectively write a tool that does that for you that ensure certain things are there in the past to avoid dealing with package managers and to lose some system checks actually I would go into the Esy directory and look for a configuration file for a system that had to be installed and if the file was not there it meant that the system that the software would not work so that is another thing that compliance checks。

Can do for you and are interesting and that's the reason why they're interested interesting in building them。

 implementing them， and adding those rules to systems that you may be managing。



![](img/dcd0a836332a4518499f9eec86296e44_2.png)
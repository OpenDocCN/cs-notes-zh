# 【双语字幕+资料下载】哈佛 CS50-WEB ｜ 基于Python ／ JavaScript的Web编程(2020·完整版) - P6：L1- github操作 2 (github冲突处理与分支) - ShowMeAI - BV1gL411x7NY

to the code what happens if we both make，changes to the same part of the code and。

then try to sync up our work together，what's going to happen well we're gonna。

run into some sort of conflict because，I've made changes to the same line that。

my colleague has been making changes to。

![](img/2a88354eae8a6e05db15c15713ce6e45_1.png)

and that type of conflict is called a，merge conflict that when trying to merge。

my changes with the changes that someone。

![](img/2a88354eae8a6e05db15c15713ce6e45_3.png)

else has made we run into a situation，where suddenly git doesn't know what to。

do there are two different sets of，changes and we need to figure out how to。

resolve them and what to do when we run，into this sort of conflict so here's。

what's gonna happen if ever we run into，this sort of merge conflict it just。

generally gonna happen if I try and hole，in or merge in some changes from。

elsewhere so let's say I run git PO but，there's some conflicting commits。



![](img/2a88354eae8a6e05db15c15713ce6e45_5.png)

something that is online that conflicts，with my current version of the。

repository what I'll get is a message，like this some conflict saying merge。

conflicts in some file have failed you，need to fix the conflicts and then。

commit the results so what might those，conflicts look like well generally the，like this。

git is automatically going to add some，metadata to the file to describe the。

things that it can't quite figure out，and it's a lot of cryptic looking。

information but we can distill it down，into a couple of key parts everything in。



![](img/2a88354eae8a6e05db15c15713ce6e45_7.png)

between these arrows at the top and the，equal signs here are your changes the。



![](img/2a88354eae8a6e05db15c15713ce6e45_9.png)

changes I have made on my version of the，repository that are somehow conflicting。

with some other changes everything，between these equal signs and these。

arrows down here are the remote changes，the changes from github that I'm trying。

to pull in that somehow are conflicting。

![](img/2a88354eae8a6e05db15c15713ce6e45_11.png)

with what I've currently been working on，and then this sequence of numbers and。



![](img/2a88354eae8a6e05db15c15713ce6e45_13.png)

characters here is the hash of the，conflicting commits so every commit gets。

a hash just some sequence of numbers and，characters that is likely to be unique。

that helps to identify any particular，commit and yet will automatically。

generate a hash every time you make a。

![](img/2a88354eae8a6e05db15c15713ce6e45_15.png)

commit and we'll see in a moment how you，can look at all of those possible。

commits but here get is just helpfully，telling us this is the commit that is。

causing the conflict just for our own，reference in order to address this merge。

conflict the way we do it is we first，need to remove all of these merge，file。

and decide what we want what we want as，the resolution of the conflict so maybe。

I want to keep my version of the changes，maybe I want to keep the remote version。

of the changes the changes that were，already on github for example or maybe I。

want to combine them in some intelligent，way I the programmer get to make that。

decision I get to look at my version and，the conflicting version and decide how I。



![](img/2a88354eae8a6e05db15c15713ce6e45_17.png)

want to resolve that conflict I'll，remove any of the blank lines and then。

commit the changes to say this is what I。

![](img/2a88354eae8a6e05db15c15713ce6e45_19.png)

want the merged version of this program，to look like so let's now take a look at。

an example of a merged conflict in，action to see how one might arise and。

how we might actually go on going about，dealing with a merge conflict should it。

happen so I on my computer now I'm going，to make a change to this page I'm going。

to say add a second exclamation point，one exclamation point wasn't enough I'll。



![](img/2a88354eae8a6e05db15c15713ce6e45_21.png)

add in a second exclamation point to，this h1 and I'll go ahead and commit。

those changes I'll say git commit - am，add exclamation point and I'll go ahead。

and commit those changes I saved this，new version of the program but I'm not。



![](img/2a88354eae8a6e05db15c15713ce6e45_23.png)

going to push the code yet instead what，I'm going to do is simulating someone。

else working on the same file maybe，someone else on github has decided you。

know what for this h1 what we'd really，like to do is add some style to it with。

some inline style by saying let's give，it a color of blue for example so。

they've added some CSS we'll go ahead，and write a commit message what do they。

do they've added some style and we'll，commit those changes and now what we've。

created is what is going to be a merge，conflict that someone else on github has。



![](img/2a88354eae8a6e05db15c15713ce6e45_25.png)

made a change to this line changing the，color to blue of this particular h1 tag。

for example and I meanwhile have also，made a change to this same line adding。

an exclamation point and get entirely，operates in terms of like adding lines。

and removing lines given that we both。

![](img/2a88354eae8a6e05db15c15713ce6e45_27.png)

made changes to the same line get is，gonna have a very hard time figuring out。

what to do in this scenario so here in，my terminal I'll go ahead and run git。

pull because I want to pull in those way，to change this and when I do I'll see。

that all right I get this message，conflict there was a merge conflict in，hello dot HTML。

the automatic merge failed because，normally get will try to merge files。

automatically if it can but sometimes it。

![](img/2a88354eae8a6e05db15c15713ce6e45_29.png)

can't so now I need to fix the conflicts，and then commit the results so let's go。

ahead and look at what's inside of hello，dot HTML and what you'll notice is a。

whole bunch of these markers and my text，editor just so happens to highlight them。

for me so that I can see them a little，more clearly but this is just。

highlighting provided by the text editor，it's not actually part of the text。

itself but you'll notice all of these，arrows and then all of these equal signs。

and in between here's my version of this，line of code the line of code with the。

extra exclamation point at the end of it，down below here is the remote。

conflicting version of the same code the，version that was modified on github that。

I am now trying to pull in this is the，version that says we want style color。

blue inside of the inline style，for this particular h1 element and now。

what I need to do is somehow figure out，how to merge these two together how do I。

want to resolve this conflict well in，this particular case I might like to。

resolve this conflict by just taking the，best of both worlds if the person on。

github wanted to add a style attribute，to this h1 element and I wanted the，extra exclamation point。

I can do both I can go ahead and just，add an extra exclamation point and then。

get rid of my version and then also get，rid of these commit markers so go ahead。

and remove those I basically modify the，file until I'm satisfied with it until I。

think that all right this is the way I，wanted to resolve the conflict one。

person added color one person added，punctuation the way to resolve it in。

this case is just use both of them but，here is where some human intuition comes。

in the human programmer doesn't mean to，look at this file and figure out how。

exactly do we want to resolve this，conflict how do we want to figure out。

how to take these different changes and，merge them all together but once we're。



![](img/2a88354eae8a6e05db15c15713ce6e45_31.png)

satisfied with it we can go ahead and，commit the results I can say git commit。

dash and fix merge conflict and all，right we fixed the merge conflict and。

now if I push those results back up to。

![](img/2a88354eae8a6e05db15c15713ce6e45_33.png)

github when that is done，refresh the page I now see the updated。

line of code on github with the h1 that，has both the inline styling and the。



![](img/2a88354eae8a6e05db15c15713ce6e45_35.png)

extra punctuation because I've resolved，the merge conflict and then I've pushed。

that information back up to github as，well there are a couple of other git。

commands that are just useful to know，about I mean there are many but we'll。

talk about a couple right now the first，of which is get log get log is useful if。

you ever need to keep track of all of，the changes that you've made to your。

code you want to keep track of all of，the commits that have been made in this。

particular repository all you need to do。

![](img/2a88354eae8a6e05db15c15713ce6e45_37.png)

is run the command git log and get will，spit out a bunch of messages that look。



![](img/2a88354eae8a6e05db15c15713ce6e45_39.png)

like this describing each of your，commits for each commit it'll tell you。

what the commit hash is such that you，can reference it more easily it'll tell。

you who made the commit it will tell you，the date on which that commit was made。

and it will also tell you the commit，message so if you need to very quickly。

look back and see you know on what day，was this feature added or who added this。

part to the webpage you can just look，through the git log，find the commit in question and then。

you'll know which commit it happened to，be also helpful is if you realize that。

you've made a change that you didn't，mean to and you want to go back to a。

previous commit then in that case you，can use a command called git reset which。

has a number of different possible ways，to use it but get reset in effect we'll。



![](img/2a88354eae8a6e05db15c15713ce6e45_41.png)

take the current state of the repository，and revert it back to an older state of。



![](img/2a88354eae8a6e05db15c15713ce6e45_43.png)

the repository for example so a couple，of ways you can use it or like this you。

can do git reset - - hard meaning hard，reset reset everything back - and then。

you can plug in a commit hash so get log，as you might recall from before gave you。

the commit hashes for each of the，various different commits if I want to。

go back to one particular commit I can，say git reset - - hard and then the。

commit message I want - or the commit，hash that I want to go back to and I'll。

go back to that commit alternatively I，could say something like git reset - -。

hard Origin slash master and recall that，origin slash master is the version of my。

repository that's currently on github so，if I want to take my current version of。

the repository and reset it back to，whatever is on github then I can use a。

command like this in order to do so so，you run git reset followed by a commit。

hash and that will reset the current，state of your repository，back to whatever state it was in。

previously and there are a number of，other git commands as well that can be。

quite helpful as you begin working with，larger and larger project projects but。

these are some of the most helpful and，some of the ones you'll use the most。

often are just adding files that you，want to keep track of get commit to say。

I would like to make a save I would like，to save the current state of all of。

these files push and pull to be able to，upload changes and download changes that。

have made you've been made to your，repository and then some helpful。

commands like reset and log and status，just to give you information about your。

repository and get you back to an older，State of the repository if you need to。

but as we begin to work on more and more，projects and especially as we begin work。

on more sophisticated projects you may，find the just keeping track of one。

change after another is it nearly as，powerful as you might like it to be and。

so we can explore what might happen in a，hypothetical situation where you begin。

making some changes to we get repository，for example so let's imagine you make。

your first commit you make some changes，you make some additional changes and。

maybe you realize you want to start，working on a new feature to this web。

application that you've been working on，so you start working on a new feature。

then you continue working on that new，feature but then you realize suddenly。

you know what there was a bug in the，original code that I made way back here。

and you want to go back and fix that bug，but now we're sort of in a tricky spot。

that we want to fix the bug but we're in，the middle of working on a new feature。

so what do we do we could go back to，this and try and fix the bug but then。

what happens to the new feature the，problem is that this structure just。

changed after change after change is，very linear it only goes one after。

another after another and oftentimes，when you're working on a project it's。

not going to operate in a very linear，fashion you're not always working on one。

thing that immediately follows the thing，before it you might be fixing multiple。

bugs while working on multiple new，features and you want some way of being。

able to work on all of those things。

![](img/2a88354eae8a6e05db15c15713ce6e45_45.png)

simultaneously and to easily be able to，switch between them and so that is where。

branching comes into handy branches are，gets way of working on different parts。

of the repository at the same time and。

![](img/2a88354eae8a6e05db15c15713ce6e45_47.png)

so you might imagine a situation，unfolding more along these lines you。



![](img/2a88354eae8a6e05db15c15713ce6e45_49.png)

make your first commit you start to make，changes you make more changes and when。

you decide that you'd like to start。

![](img/2a88354eae8a6e05db15c15713ce6e45_51.png)

working on a new feature for example，rather than keep making changes in one。

after another after another on this same，branch so to speak I can create a new。



![](img/2a88354eae8a6e05db15c15713ce6e45_53.png)

branch I can branch off and say you know，what let's create a new branch and start。

working on our new feature there and。

![](img/2a88354eae8a6e05db15c15713ce6e45_55.png)

then keep working on that new feature，there and if I realize later on down the。



![](img/2a88354eae8a6e05db15c15713ce6e45_57.png)

road that you know what there was a bug，way back at this commit then I can go。

back to this commit and create a new，branch where I go ahead and fix that bug。

and now I have two different branches。

![](img/2a88354eae8a6e05db15c15713ce6e45_59.png)

each of which might have different code，on it one of which I've been fixing a。

bug one of which I've been working on a。

![](img/2a88354eae8a6e05db15c15713ce6e45_61.png)

new feature on for example generally，each of those branches is going to have。

a name so the master branch is your，default branch which is generally going。

to contain the up-to-date stable version，of your code and as you're working on。

newer things newer additional features，you might have some feature branch where。

you're working on some other feature for，example and at any given time though。

your focus is only on one of these two，branches and where your focus is what。

the current state of your repository is。

![](img/2a88354eae8a6e05db15c15713ce6e45_63.png)

is designated by something we call the，head so if head is pointing to master。

that means your repository right now is，working on this branch where you fix the。

bug but you can change the head you can。

![](img/2a88354eae8a6e05db15c15713ce6e45_65.png)

switch what branch you want to look at，and you can check out the feature branch。

and say let's look at that branch and，begin working on that as well and you。

can begin working on these different，branches by switching where your head is。

switching from one branch to another and，then back again and only when you're。



![](img/2a88354eae8a6e05db15c15713ce6e45_67.png)

satisfied that you know what this bug is，fixed and this feature is in a。

satisfactory place then after all of。

![](img/2a88354eae8a6e05db15c15713ce6e45_69.png)

that we can merge those changes back，together so that everything comes back。



![](img/2a88354eae8a6e05db15c15713ce6e45_71.png)

on to this unified master branch that，now has all of the latest code and。

that's the real power of git branching，this ability to say that I would like to。

be working on multiple things，simultaneously and be working on a。

feature without disrupting the master。

![](img/2a88354eae8a6e05db15c15713ce6e45_73.png)

version of the code so let's now take a，look at an example of how we might go。

about doing that so here in my hello dot，HTML file，I've been adding some style to this h1 I。

added a color of blue and let's say that，I would like to make some changes I，would like to。

move the styling outside of inline，styling and I did instead like to move，webpage。

because we decided earlier that was，slightly better design for a webpage。

like this I could make this changes，immediately but I can instead it if I。

expect I might be working on multiple，changes I could move on to a different。

branch and branch off into something。

![](img/2a88354eae8a6e05db15c15713ce6e45_75.png)

else in order to work on these new，changes and so here are some of the key。

commands to know about this if I type，git branch that will tell me what branch。

I'm currently on and what branch has，exist in my repository so here for。

example I type git branch and I see that，I just have a single branch called。

master and the star on the left hand，side tells me that this is the branch。

that I am currently on the only branch，that there is if I want to check out a。

new branch I can type git checkout and，if it's a new branch I'll type git。

checkout dash B and then the name of the，new branch and I'll call the new branch。

style because I'm gonna be making some，style changes to the web page for。

example so I typed get check out - B，style and get gives me a message I have。

switched to a new branch called style，and now if I type git branch again and。

you'll see that now I have two branches，I have the master branch which is the。

branch I was originally on and now I，have the style branch which is this new。

branch which I am on now as indicated by，the star on the left hand side so now。

that I'm on this new branch I can feel，free to make any changes that I want and。

nothing I do is going to mess up what is。

![](img/2a88354eae8a6e05db15c15713ce6e45_77.png)

on the master branch so long as I stay，on this branch so I can say alright。

let's experiment with removing this，style and let's add a style tag at the。

top where I can say that I would like my，h1 to have a color of blue for example。

so I've made a whole bunch of changes。

![](img/2a88354eae8a6e05db15c15713ce6e45_79.png)

and I would like to now commit those，changes I'll say git commit move style。

properties that's the change that I've，made but I've only made those changes to。

the style branch again if I run git。

![](img/2a88354eae8a6e05db15c15713ce6e45_81.png)

branch you'll see that I'm currently on，the style branch where I've moved the。



![](img/2a88354eae8a6e05db15c15713ce6e45_83.png)

style information up here to the top of，my page but I can switch branches by，using git checkout。

get checkout allows me to switch between，branches we used get checkout - be to。

create a new branch but if you're，switching to a branch that already。

exists I can just say get checkout，master for example to switch my current。

branch from the style branch to the。

![](img/2a88354eae8a6e05db15c15713ce6e45_85.png)

master branch so I run git checkout，master now I'm on the master branch and。

now you'll see if I go back to the file，now I'm back to the inline styling。



![](img/2a88354eae8a6e05db15c15713ce6e45_87.png)

without the styling up here in the head，section of the page if I check out the。



![](img/2a88354eae8a6e05db15c15713ce6e45_89.png)

Style branch again then the file，immediately goes back now I have the。

style code up here in the Style section，of the page and not in line so these。

changes have only been made to one part。

![](img/2a88354eae8a6e05db15c15713ce6e45_91.png)

of the page so now I'll check out master。

![](img/2a88354eae8a6e05db15c15713ce6e45_93.png)

again and maybe I want to make some，other changes on my master branch maybe。

I realized that I want to remove this。

![](img/2a88354eae8a6e05db15c15713ce6e45_95.png)

extra punctuation you know what two，exclamation points was too many will。

remove now we just have one and now I'll，commit these changes I'll say git commit。

and remove punctuation and now I've。

![](img/2a88354eae8a6e05db15c15713ce6e45_97.png)

removed the punctuation only from the，master branch so this master branch now。

has just a single exclamation point here，but it still does have the inline。

styling so now what I'd like to do is，merge in those changes that I made from。

the other branch I'd like to take what I，was working on in the style branch and。

merge it into this current version of。

![](img/2a88354eae8a6e05db15c15713ce6e45_99.png)

the repository on my master branch and，in order to do that the command we'll。

use is called git merge so git merge，notice that I'm currently on the master。

branch but if I run git merge and then，style that is going to take whatever's。

on the style branch and attempt to merge，it into my current branch and what we'll。

find is we're able to get most of the，way there but there's a merge conflict。

now this won't happen all the time when，you merge sometimes get will be smart。

enough to know that if one change has，been made to one part of a file and one。

change has been made to another part of，a file when you merge those changes back。

together git will resolve those merge，conflicts automatically but in this case。

that wasn't the case because both my，style branch and my master branch made。



![](img/2a88354eae8a6e05db15c15713ce6e45_101.png)

changes to the same line of code，and we'll see why if I go back here。

you'll notice that in the merged version，we do see this style tag at the head of。

the page no problems no conflict there，because that was just lines that have。

been added to this page so there was no，conflict the conflict comes up here。

which is where in my version on the，master branch I removed this punctuation。

mark whereas in the version on the style，branch we could we can see here by the，word style。

we removed the inline styling so we need，to resolve the somehow and what I。

ultimately do is just get rid of these，style markers or the conflict markers。

and say you know what I would like for，the updated version not to have either。



![](img/2a88354eae8a6e05db15c15713ce6e45_103.png)

not to have the inline styling and not，to have the additional punctuation so I。

have now made those changes I have，resolved the merge conflict and now I。



![](img/2a88354eae8a6e05db15c15713ce6e45_105.png)

can commit I fix the merge conflicts and，that's the general workflow now of how。

branching in git ultimately works when，you're working on something new。

you might branch off in order to say you，would like to work on a different part。

of this web application you'll make，changes make commits add changes to that。

new branch and when you're satisfied，with those changes when they're in the。

state that you want them to be you can，then say merge them back in to the。

original version of the repository，sometimes you'll have to deal with merge。

conflicts so certainly not always and if，you're careful about where you make。

changes and trying to be careful not to，make modifications to the same line of。

code in two different places you can，reduce the likelihood of actually。

getting a merge conflict because get，ultimately is quite smart about how it。

tries to deal with these sorts of issues，and finally we'll take a look at a。

couple of features of github，specifically that can be quite helpful。

if you begin to work on larger projects，that have many different moving pieces。

the first of which is forking a github，repository so let's go to a github。

repository and look at the github，repository for bootstrap for example so。

bootstrap which is the CSS library that，we took a look at last time is a library。

that gives us the easy access to a whole，bunch of different CSS features and the。



![](img/2a88354eae8a6e05db15c15713ce6e45_107.png)

entire thing is open source meaning all，of the code for bootstrap is publicly。

available for anyone to look up and，more importantly for anyone to。

contribute to that it's not just one，person that's been working on all of。

bootstrap but it's a community driven，repository that many people can be。

working on adding new features and，making fixes to bootstraps code and。

collaborating on them by taking，advantage of the features of git and so。

if you find a git repository that you，would like to contribute to or if you。

want other people to be able to，contribute to your repository one thing。

you can do is fork that repository and，by forking we mean making your own copy。

of the original repository and so up，here in the upper right hand corner of。

github page is a button called fork and，we can see that right now about 68，000。

people have already forked bootstraps，repository made a copy of the repository。

into their own github account and so we，could fork it ourselves just by clicking。

on this button called fork and then，getting our own version of the，repository。



![](img/2a88354eae8a6e05db15c15713ce6e45_109.png)

that we can then clone and push and pull，from as well the reason we might do that。

is that bootstraps repository while it，is public doesn't allow anyone to just。

push to it that would be probably unsafe，if anyone in the world could just update。

bootstraps master code but what you can，do is copy the code make a fork of it。

make changes to it on your own push and，pull to it and then when you feel like。

you've made a contribution that you，would like to send back to bootstrap you。

can open what's called a pull request，that you are requesting that your code。

be pulled in to bootstraps code and we，can look for example at bootstraps pull。



![](img/2a88354eae8a6e05db15c15713ce6e45_111.png)

request tab it looks like right now，there are 71 open pull requests there。

are 71 people that have made some fixes，or made some changes to bootstraps code。

and you can submit a pull request to say，that you would like to take those。

changes and merge them back in with，bootstraps actual code and the people。

that maintain bootstraps code in this，particular repository can review those。

pull requests provide feedback ask for，additional changes and then when。

everyone's satisfied they can merge，those changes into bootstraps actual。

code and this is one of the key benefits，of open source software the ability for。

multiple people to be working on the，same piece of code and for a community。

to be able to collaborate on finding，bugs on figuring out what changes to。

make on figuring out how to improve，upon an existing repository and make it。

better moving forward and one final，thing worth noting about github is an。

additional feature known as github pages，github pages is a free way the github。

provides to be able to quickly take a，website with HTML and CSS and maybe even。

a little bit of JavaScript and deploy it，to the internet for anyone to look at in。



![](img/2a88354eae8a6e05db15c15713ce6e45_113.png)

anyone with a github account is allowed，to create a github pages website for。

free and in order to do so we can，demonstrate it now all you need to do in。

github is let's create a new repository，that will call it should generally be。

your user name dot github dot，is the conventional name for your github。

pages site though it can have other，names you'll just have to manually turn。

on github pages and we'll go ahead and，create this repository now if you create。

a github repository called your username，github io it will automatically be。

supporting github pages and what that。

![](img/2a88354eae8a6e05db15c15713ce6e45_115.png)

means is that I can take this URL and I，can clone it so I can say git clone。

followed by this URL I've cloned an。

![](img/2a88354eae8a6e05db15c15713ce6e45_117.png)

empty repository but I can go into this，repository and add some files to it I。

can say let's add by default it's called，an index。html file and I'll create an。

HTML file that is my site and the body，that will just say this is my github。

pages website so something like this。

![](img/2a88354eae8a6e05db15c15713ce6e45_119.png)

something simple but it can certainly be，more complex if you want it to be inside。

my terminal I will get add this index，study HTML file and I'll make a commit。

and off in a first commit you'll just in，the commit message right first commit so。

but we know it was the first commit and，then I'll push those changes to github。



![](img/2a88354eae8a6e05db15c15713ce6e45_121.png)

now so if you put，your changes to repository called your，username github do and then if you take。

a look at the settings and scroll down，you'll see that github pages is by。

default ready to be published and now if，i click on this URL，my username github do you'll see。



![](img/2a88354eae8a6e05db15c15713ce6e45_123.png)

deployed to the internet such that，anyone can go to this URL and see it。

they'll see a big heading that says this，is my github pages website because this。

is the way the browser is rendering the，HTML that i pushed to my github pages。

repository and the advantage of doing，this is that it's very easy now to be。

able to quickly update my website all i，need to do is if i make a new change i。

can commit that change push that change，to github and when github detects that。

i've made a push to my github pages，repository then it will update my。

website that anyone in the world can，access by going to my username github。

dot and this allows you to leverage all，of these features of get the ability to。

branch the ability to work on different，features of your webpage at different。

times and revert back to different，versions of the code as well so all in。

all git has given us a number of very，powerful tools it's given us the ability。

now to be able to very quickly and very，easily keep track of any changes we make。

to code keep track of when a piece of，code is updated and to quickly revert。

back and look at old versions of that，code if need be and in particular it's。

given us the ability to take our code，and work together with other people on。

it such that we can be working on，multiple parts of the same project and。

someone else working on the same project，can also be working on multiple parts of。

the same project on different branches，and it's very easy then to synched up。

our changes in order to work together，and so get is a very popular tool used。

not only in the world of web programming，but especially whenever dealing with any。

kind of larger project where multiple，people might be working on the same。

thing simultaneously git will enable us。

![](img/2a88354eae8a6e05db15c15713ce6e45_125.png)

to more easily develop our web，applications over the course of this。

term next time we'll take a look at，python which is one of the first。

programming languages that we'll use as，we continue on our journey towards。

building more sophisticated web。

![](img/2a88354eae8a6e05db15c15713ce6e45_127.png)
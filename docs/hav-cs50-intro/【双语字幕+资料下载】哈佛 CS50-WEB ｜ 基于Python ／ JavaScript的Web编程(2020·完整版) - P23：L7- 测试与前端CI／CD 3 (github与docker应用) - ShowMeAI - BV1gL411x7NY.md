# 【双语字幕+资料下载】哈佛 CS50-WEB ｜ 基于Python ／ JavaScript的Web编程(2020·完整版) - P23：L7- 测试与前端CI／CD 3 (github与docker应用) - ShowMeAI - BV1gL411x7NY

little bit easier what techniques can we，use in order to do so and there are a。

number of different continuous，integration tools but one of them，produced by github more recently is。

known as github actions and what github，actions allows us to do is to create。

these workflows where we can say that，anytime for example someone pushes to a。

git repository I would like for certain，steps to take place certain steps that。

might be like checking to make sure the，code is styled well but if a company has。

some style guide that it expects all of，its programmers to adhere to when。

working on a particular product you，could have a github action such that。

anytime someone pushes to a repository，you have an action that automatically。

checks that code against the style guide，to make sure that it is well styled well。

commented documented and so forth you，might also for instance have a github。

action that tests our code to make sure，that any time any one pushes code to a。

github repository we automatically run，whatever tests we would like to。

on that particular codebase and github，actions can allow us to do that as well。

by defining some workflow to be able to，do so and so that's what we'll take a。

look at in just a moment using github，actions to automate the process of。

running tests so that the human though，it would be a good thing for the。

programmer when they're done writing，their code to test their code and make。

sure it works we can enforce that by，making sure that every time anyone。

pushes to a github repository will，automatically run some github action。

that is going to take care of the，process of running tests on that program。

and we'll know immediately as via an，email that github might send to you to。

say that this particular test failed and，you'll know every time you push to that。

repository so how do these workflows get，structured what is the syntax of them。

will they use a particular type of，syntax known as llamo which is some。

language a configuration language that，can be used in order to describe often。

describe for configuration in various，different tools and software github。

actions happens to use that other，technologies use it as well and yeah。

Mille is a file format that structures，its data sort of like this in terms of。

key value pairs much in the same way，that a JSON object or a Python。

dictionary might where we'll have the，name of a key followed by a colon。

followed by its value name of a key，followed by a colon followed by a value。

and the value doesn't necessarily need，to be just a single value it could be a。

sequence of value it's like a list of，values for example and those are denoted。

this way by like a - indicating a list，item 1 item 2 item 3 and in addition to。

just having single values and lists of，items these ideas these lists these。

sequences these values can be nested，within one another that you might have。

one key that leads to another set of，keys that are associated with values。

that leads to other sets of keys，associated with values as well much in。

the same way that a JSON object like a，representation of keys and values can。

also have nested JSON objects within a，JSON object likewise too we can have。

nested key value pairs and as the value，for a particular key - so we'll take a。

look at an example of what that actually，looks like in the context of creating。

some github workflow that will run some，github actions so what will that look。

like let's go back into airline zero，we're here I've defined inside of a dot，github directory。

a directory called workflows inside of，which I have a CI dot yml file it can be。

any name llamo yml or dot YAML are the，conventional file extensions for a yamo。

file and here I'll open up CI yml and，this now is the configuration for how。

this workflow ought to behave I give the，workflow a name it's called testing。

because what I want the workflow to do，is like test my airline application then。

I specify an on key to mean when should，this workflow run and here I've said on。

push meaning anytime someone pushes，their code to github we would like to。

run this workflow every workflow，consists of some jobs and so what are。

the jobs what tasks should happen any，time that I try and push to this，repository。

well I've defined a job called test，project and this is a name that I chose。

for myself you can choose any name for a，job that you would like and now I need。

to specify two things for what happens，on a job one thing I need to specify is。

what sort of machine is it going to run，on that github has its own virtual。

machines of the wise known as VMs and I，would like to run this job on one of。

those virtual machines and their virtual，machines for various different operating。

systems and here I'm just saying go，ahead and run on the latest version of。

Ubuntu which is a later version of Linux，that I would like for this test to run。

on and then for the job I specify what，steps should happen where I can now。

specify like what actions should happen，when someone tries to test the project。

when I try and run this job and here I'm，using a particular github action and。

this is a github action written by，github called actions a slash check out。

and what this is going to do is it's，going to check out my code in the get。

repository and allow me to like run，programs that operate on that code and。

you can write your own github actions if，you would like but here all we really。

need to do is go ahead and check out the，code as by looking at what's on the。

branch that I just pushed to and then，I'm going to run Django unit tests this。

is just a description for me to know，what's going on in this particular step。

and here is what I would like to run I'm，going to first go ahead and install。

Django because I'm going to need to，install Django to be able to run all。

these tests but after and if there are，other requirements I might need to。

install those requirements as well but，the airline program is fairly simple all。

we really need in order to run the test，is just Django so I'll go ahead and。

install Django and then I'll run Python，3 Manish PI test I would like to test。

run all of the tests and the way I can，do that is just by providing this。

managed up high command to say that I，would like to run all of the tests on。



![](img/80e431d7e9ec5e03b4e38d52dddd2733_1.png)

this particular application so this，configuration file altogether now is。

going to specify a particular workflow，the workflow that says that every time I。

push to the github repository what I，would like to happen is I would like to。

check out my code inside of the get，repository so on some bun to VM github。

is going to check out my code and it's，going to run these commands it's going。

to install Django and then it's going to，test my code and it will then give back。

to me what the response is after I do，that so let's go ahead and test this and。

in particular let's run it on a program，where the tests are going to fail so I。

might say for example let's go into，flights and model stop pie and let's go。

to my is valid flight function from，before and change it back to that。

version that didn't work but before it，was something and something I'll change。

it to something or something that as，long as the origin is not the。

destination or the duration is greater，than zero we'll count them as valid but。

we know that that's wrong that should，not work see here's what I'll do I'll go。

ahead and first say get status see all，right what's changed and it seems that。

all right I've changed i've modified，models pi which makes sense i'll go。

ahead and get added i'll add dot we'll，just add all the files that I might have。

modified I'll commit my changes so I go，ahead and use wrong valid flight。

function that's what I'm gonna do and，now I'm going to push my code to github。

I added it I committed it I pushed it，that now then pushes my code to github。

into a repository called。

![](img/80e431d7e9ec5e03b4e38d52dddd2733_3.png)

Airlines that I already have and now if，I go ahead and go to github and I go to。

my airline compositor II what you'll，notice is that we've mostly been dealing。

with this code tab but github gives us，other tabs as well，quite useful as you begin to think about。

working on a project in larger teams so，in addition to looking at the code we。

have issues issues are ways for people，to just report that something is not。

quite right or there is a feature，request that we have for this particular。

code base so the issues might maintain a，list of all of the pending action items。

for a particular repository things that，we still need to deal with and once。

those issues are dealt with the issues，can be closed so I have no issues here，as well。

poll requests are people that are trying，to merge some part of the code from one。

branch into another branch so you might，imagine on a larger project you don't。

want everyone merging things into master，all at the same time you might have。

people working on their own separate，branches and then when they feel。

confident and happy with their code then，they can propose a pull request to merge。

their code into the master branch and，that allows for various other features。

like the ability for someone to offer a，code review to be able to review the。

code write comments and propose，suggestions for what changes should be。

made to a particular part of the code，before it gets merged into the master。

branch and that's another common，practice with regards to working on a。

github repository or any other larger，project that you're controlling using。

source control is this idea of code，reviews that oftentimes you don't want。

just one person making the changes，without anyone's eyes on that code but。

you want a second pair of eyes to be，able to look things over make sure the，code is correct。

make sure it's efficient make sure it's，in line with the practices of the。

application is using and so pull，requests can be quite helpful for that。

and then this fourth tab over here，represents github actions these are the。

various different actions or workflows，that I might want to run on this。

particular repository and what we'll see，here is that if I go to the actions tab。

now what I'll see is here is my most，recent testing action so anytime I push。

I get a new testing action this one was，from 29 seconds ago，I'll go ahead and click on it and see。

what's within it all right here was the，job that I ran test project I see that。

on the left-hand side you'll notice this，big red X on the left-hand side of this。

workflow means something went wrong so，I'd like to know what it is that went。

wrong I'll go ahead and click on test，project and here within it these are all。

of the steps the things that happened，when we actually ran this particular job。

first the job sets up then the checkout，action goes ahead，checks out my code because we need。

access to my code to be able to run it，here was the step I defined run Django。

unit tests which was going to install，Django and run those tests it has an X。

next to it indicating something went，wrong and I see down below annotations。

one failure so all over the place，github is trying to tell me that。

something went wrong it failed two，minutes ago here I'll go ahead and open。

this up and what I'll see is the first，thing that happened is we install Django。

and that seems to have worked okay but，down below what you'll see is the output。

of running these unit tests that we see，failed failures too and now I can see。

here are the unit tests that failed we，failed the invalid flight destination。

test we failed the invalid flight，duration test and as before I can see in。

github user interface what those，assertion errors are I can see it true。

is known false true is not false those，were the problems that happened when I。

tried to run this particular test suite，and now others who are also working on。

this repository can see as well what the，results of these tests are and can offer。

suggestions can offer ways that I might，be able to fix the code in order to deal。

with that problem but now I know that，this particular test failed and if I go。

back to the main code page for this，github repository I'll see that next to。



![](img/80e431d7e9ec5e03b4e38d52dddd2733_5.png)

this commit there's a little X symbol，and that little X symbol next to the。

commit just tells me that the most，recent time I tried to commit something。

went wrong they ran the workflow when，there was an error and so I'll。

immediately see for this commit and I，can go back and look at the history of。

commits and see which ones were okay and，which ones had a tendency to cause a。

some sort of problem so this one it，appears caused a problem and we know why。

it caused a problem because of this，condition something or something else so，I can fix it。

I'll change the order to an end I'll go，ahead and get add dot get commit say I。

will fix a valid flight check if I do，get status just to check out like what's。

going on right now I'm ahead of the，master branch by one commit that's。

exactly what I would expect and now I'll，go ahead and push my code to github by。

running git push saying alright let's。

![](img/80e431d7e9ec5e03b4e38d52dddd2733_7.png)

push this update and now hopefully we're，going to pass the workflow now now I go，back to the report。

i refresh the page here is my latest，commit fix valid flightcheck you'll。

notice here there's an orange dot，instead of the red X as before this dot。

just means the tests are currently，pending the workflow is in progress。

because it takes some time for github to，be able to start up the VM to be able to。

initialize the job to check out my code，to run all those tests it does take some。

time but if I go back to the actions tab，I'll see that all right this time for。

testing we get a green checkmark，everything seems to be okay I go to test。

project just to see it and now I notice，the green checkmark next to run Django。

unit test means that the unit test has，passed as well if I open those up now I。

see at the bottom the same output that I，saw before when I was running those unit。

tests on my own machine，we ran ten tests and everything was okay，and that tells me these tests have。

passed so github actions have the，ability to allow for certain jobs to。

happen certain work to happen anytime，you push code anytime you submit a pull。

request or on various different actions，that might happen on a github repository。

and they're very helpful for being able，to implement this idea of continuous。

integration because it means you can，make sure that when you're merging code。

from some developers branch into the，main branch that everyone's merging。

their code into you can verify that，those tests can pass and you can add。

rules to say that you don't want to，allow anyone to merge code into the。

branch if the tests don't pass to，guarantee that any code that does get。

merged is going to pass all of those，tests as well and so that can definitely。

help the development cycle make it，easier to ensure the changes could be。

made quickly but as we make those，changes quickly we're not going to lose。

accuracy and validity within our code，that we can make sure that our code。

still passes those tests by automating，the process of running those tests all。

together so other than continuous，integration then we now talked about。

this idea of continuous delivery these，short application cycles where we would。

like to very quickly be able to deploy，our application onto some sort of web。

server and when we're deploying，applications to a web server there are。

things that we need to think about we，need to think about getting our program。

that was running fine on our computer，working on a web server as well and this。

can just be fraught with headaches and，all sorts of configuration problems。

because you might imagine that the，computer that you，using is not necessarily going to be the。

same as the computer that on the cloud，the computer in the server where your。

web application is actually running it，might be running a different operating。

system it might have a different version，of Python installed if you have certain。

packages working on your own computer，those same packages might not be。

installed on the server so we've run，into all sorts of various different。

configuration problems where you can be，developing deploy your code and realize。

that it doesn't work on the server，because of some sort of difference。

between what's happening on your，computer and what's happening on the。

server and this becomes even more，problematic if you're working on a。

larger team you and multiple other，people working on a software project but。

you each have different versions of，various different packages or libraries。

installed and those different word，versions have different features and。

might not all work and cooperate with，one another and so we need some way in。

order to be able to deploy applications，efficiently and effectively to be able。

to standardize on just you know one，version of the environment one version。

of all these packages to make sure that，every developer is working on the。

project in the same environment and once，we deploy the application it's going to。

be working in the same environment as，well and the solution to this comes in a。

number of possible options but one，option is to take advantage of a tool。

like docker which is some sort of，containerization software and by。

containerization software what we're，talking about is the idea that when。

we're running an application instead of，just running it on your computer we're。

going to run it inside of a container on，your computer and each container is。

going to contain its own configuration，it's going to have certain packages。

installed it's going to have certain，versions of certain pieces of software。

it's going to be configured in exactly，the same way and by leveraging a tool。

like docker you can make sure that so，long as you provide the right。

instructions for how to start up and set，up these containers then if you are。

working on the application and someone，you're working with some colleague is。

also working on the same project so long，as you're using the same instructions。

for how to set up a docker container，you're going to be working in the。

identical environments that if a package，is installed on your computer in your。

container it's going to be installed in，your colleagues container as well and。

the advantage of this to works with this，idea of continuous delivery when you。

want to deliver and deploy your，application to the Internet you can run，your application。

and inside of that exact same container，setup using the exact same set of。

instructions so that you don't have to，worry about the nightmare headaches of。

trying to make sure that all the right，packages and all the right versions are。

in fact installed on the server dock oh，right might remind you of the idea of a。

virtual machine or a VM if you're，familiar with that concept github uses。

VMs for instance when running its github，actions they are in fact different a VM。

is effectively running an entire virtual，computer with its own virtual operating。

system in libraries and application，running on top of that all inside of。

your own computer so a virtual machine，ends up taking up a lot of memory taking。

up a lot of space docker containers，meanwhile are a bit lighter weight they。

don't have their own operating system，they're all running still on top of the。

host operating system but there's this，docker layer in between that keeps track。

of all these various different，containers and keeps track of for each。

container such that every container can，have its own separate set of libraries。

that put a set of binaries and an，application running on top of that so。

the advantage event of containerization，is that these containers are lighter。

weight than having an entire virtual，machine but they can still keep their。

own environment consistent such that you，can feel confident that if the。

application is working in a docker，container you can have that docker。

container running on your computer，on someone else's computer on the server。

to guarantee that the application is，going to work the way that you would。

actually expect it to and so how exactly，do we configure these various different。

docker containers well in order to do so，we're going to write what's called a。

docker file so to do this I'll go ahead，and go into airline 1 and I'll open up。

this docker file and the docker file，describes the instructions for creating。

a docker image where the docker image，represents all of the libraries and。

other installed items we might want to，have inside of the container and Sanon。

based on that image we're able to create，a whole bunch of different containers。

that are all based on that same image，where each container has its own files。

and can run the web application inside，of it so this docker file for example。

describes how I might create a container，that is going to run my Django web。

application so first I say from Python ：three this happens to be another docker。

image on which I'm going to base these，instructions that this is going to be a。

docker image that already contains，instructions for installing Python 3。

installing other related packages it，might be helpful oftentimes when you're。

writing a docker file you'll base it on，some existing docker file that already。

exists so here I'm saying go ahead and，use Python 3 and now what do I want to。

do in order to set up this container，well I want to copy anything in dot in。

my current directory into the container，and I have to decide where in the。

container am I going to store it well，there I could choose to store it。

anywhere but I'll just store it in slash，user slash source slash app just some。

you are some particular path that will，take me to a directory where I am going。

to store the application but you could，choose something else entirely。

so I copy all of the current files in my，current directory，so that'll include things like my。

requirements file my manage type I file，my applications files all my settings。

files everything inside of the directory，I would like to copy into the container。

then I'm saying work der meaning changed，my working directory effectively the。

same thing as something like CD on your，terminal to move into some directory I。

would like to set my working directory，equal to that same application directory。

the application directory inside of the，container that now contains all of the。

files for my application because I，copied all of those files into the。

container now once I'm inside of this，directory I need to install all of my。

requirements so assuming I've put all my，requirements like Django and any other。

packages that I need inside of a file，called requirements text I can just run。

the command pip install requirement text，and then finally inside the docker file。

I specify a command and this is the，command that should run when I start up。

the container everything else is gonna，happen initially when we're just setting。

up this docker image but when I start up，the container and actually want to run。

my web application here is the command，that should run and I provided。

effectively is like a Python list where，each word in the command is separated by。

a comma we're here I'm saying the，command that I would like to run when。

you start up this container is Python，managed up I run server and here I'm，port。

like it to run running it on port 8000，for example but I could choose another。

port that I would like to run instead so，what's going to happen that is that when。

I start up this docker container it's，going to if it needs to go through these。

instructions and make sure that it sets，up the container according to these。

instructions make sure that we've，installed all of the necessary。

requirements make sure that we're using，Python 3 and anyone using the same。

docker file can generate a container，that has all the same configuration on。

it we don't have to worry about，configuration differences between me and。

someone else who might not have the，exact same computer setup that I do and。

the nice thing about this is that it can，run on Mac and Windows and Linux so even。

people running on different operating，systems can still have containers that。

all have the same configuration that all，work in the same way just to speed up。

that process now so far when we've been，building django applications we've been。

using a sequel Lite database sequel Lite，database just being a file that is。

stored inside of our application and，this file based database allows us to。

create tables insert rows into it delete，rows from it in most production。

environments and most real web，applications and working with many many。

users sequel Lite is not actually the，database that is used it doesn't scale。

nearly as well when there are many users，all trying to access it concurrently。

oftentimes in those sorts of situations，you want your database hosted elsewhere。

on some separate server to be able to，handle its own incoming requests and。

connections and we talked about a couple，of possible databases we could use。

instead of sequel Lite things like my C，group MySQL things like Postgres are。

various different sequel based databases，so imagine now I want to deploy my。

application but instead of using sequel，Lite I would like to use Postgres for。

example as the database server that I，would like to run well that would seem。

to be pretty complicated for me to test，on my own because now in addition to。

running my web application in one server，effectively I also need like another。

server that's running Postgres for，example such that I can communicate with。

that Postgres database instead and，that's going to be even harder for like。

other people to be able to work on as，well potentially it might be difficult。

to get the server to work in that way，too but the nice thing about docker is。

that I can run each of these processes，and in a different container effective。

I can have one container that's running，my web application using this docker。

file right here and I can have another，container that's just going to run。

Postgres and as long as other people，also have access to that same container。

for running Postgres they can be working，in an identical environment to the one。

that i am working in as well and so，there's also a feature of docker known。

as docker compose and what docker，compose lets us do is allow us to。

compose multiple different services，together that i would like to run my web。

application in one container and i would，like to run a Postgres database in。

another container but I would like for，those containers to be able to talk to。

each other to be able to work together，whenever I start up the application so。

if I'd like to do that in order to run，this application on my computer and have。

both the web application and Postgres，installed I can create a docker compose。

file which looks like this，here I'm specifying using version 3 of。

docker compose here I specify again，using a yamo file，much as in my github workflows were。

formatted in Yeman just as a，configuration file docker compose dot。

yml is a yamo file that describes all of，the various different services that I。

want to be part of my application where，each service is going to be its own。

container that could be based on a，different docker image here I'm saying。

that I have two services one called DB，for database one called web for my web。

application the database is going to be，based on the Postgres docker image image。

the Postgres wrote that I don't have to，worry about someone else has written the。

docker file for how to start up a，Postgres container here though for the。

web application that's gonna be built，based on the docker file in my current。

directory the docker file that I have，written and then down below I've just。

specified that my current directory，should correspond to the app directory。

and then I've specified when I'm running，this on my own computer I would like。

port 8000 on the container to correspond，to port 8000 on my own computer just so。

that I can access port 8000 or my，browser and access port 8000 inside the。

container it just lets my computer，actually talk to the container so I can。

open up the web application in my web，browser for example and actually see the。

results of all of this so here then I've，created two services a database and web。



![](img/80e431d7e9ec5e03b4e38d52dddd2733_9.png)

so now let's actually try starting up，these containers I'm going to first go。

into my airline one directory and I'm，going to say docker compose up to mean。

go ahead and start up these services，I'll press return and what you'll see is。

we're going ahead and starting up to，services I'm starting up the database。

service and I'm starting up the web。

![](img/80e431d7e9ec5e03b4e38d52dddd2733_11.png)

service and now as a result of all of，this I've started up the application and。

I started it on port 8000 so if I go to，0 dot 0 dot 0 dot 0 / 8000 or colon 8000。

flash flights that's going to take me to，the flights page and now this is running。

not just on my own computer but inside，of a docker container now of course。

right now there are no flights inside of，this page because I haven't actually。

added anything to the database yet so I，could do that if I wanted to but how do。

I do that well I needed to like go into，slash admin to say like let me login and。

go ahead and create some sample flights。

![](img/80e431d7e9ec5e03b4e38d52dddd2733_13.png)

but I don't have a login yet because I，need to like create a super user account。

and I can't just like inside of my，airline one directory say Python managed。

PI create super user the way that I used，to because this is running in my，terminal on my computer。

whereas what I really want to do is go，into the docker container and run this。

command there inside of the container so，how can I do that well there are various。

different docker commands that I can use，docker PS will show me all of the docker。

containers that are currently running so，go ahead and shrink this down a little。

bit I see two rows one for each，container one for my Postgres container。

that's running the database one for just，my web application that's running as。

well each one has a container ID so I，want to go into my web application。

container in order to run some commands，inside of that container so I'm going to。

copy its container ID and say docker，exact meaning go ahead and execute a。

command on the container - IT will make，this interactive here is the container。

idea that I would like to execute a，command on and the command I want to。

execute is - passing the - L flag but，bash to say I want to run a bash prompt。

I want to be able to interact with a，shell so that I can run commands inside，of this container。

so I press return and now what you'll，notice is that I am inside of my。

container in the user source app，directory that directory that contained。

all the information about this web，application I type LS and what I'll see。

is here all the files inside of this，container now and now I can say。

something like Python managed up I，create super user and now it's going to。

let me create a super user so I'll，create a user inside of my web，application called Brian。

I'll give it my email address I'll type，in a password and now we've created a。

super user and you can run other，commands here if you wanted to migrate。

all of your migrations I could say，Python managed up PI migrate it turns。

out I've already done that so I didn't，actually have to do it again but you can。

run any commands that you could run them，on your computer but now you can run。

them inside of the docker container，instead I'm going to press control D。



![](img/80e431d7e9ec5e03b4e38d52dddd2733_15.png)

just to log out get out of the container，and get back to my computer but now I've。

created a super user so I could go ahead，and sign in to Django's admin and now I。

can begin to manipulate this database，which is a Postgres database running in。

a separate container but the nice thing，about it is that I can start them both。

up together just by running something，like docker compose up for example so。

docker can be quite a powerful tool for，allowing us to very quickly ensure that。

an application is running in the，environment that we expect it to be。

running to make sure that all the right，libraries are installed make sure that。

all the right packages are installed as，well that the configuration between my。

development environment and the，environment that's running on the server。

are the same as well so those then were，just some of the best practices for how。

you can go about developing a program，now that we have the tools to do so we。

have a lot of tools for being able to，develop these web applications。

but as our program start to get more，complex it'll be increasingly important。

to test them make sure that each various，different component of our web。

application behaves the way that it is，expected to behave and then taking。

advantage especially in bigger teams of，CI CD continuous integration continuous。

delivery to make incremental changes and，make sure each of those incremental。

changes in fact works on the web，application and then CD continuous。

delivery to say that rather than wait，and then deploy everything all at once。

let's deploy things in Chrome，as well let users more quickly get。

access to the latest features and more，quickly find out if something went wrong。

we can better identify what it is that，went wrong if we've deployed things。

incrementally rather than waiting a long，time in order to do so as well so these。

are some of the best practices in modern，software application development not。

only for web applications but for，software more generally next time we'll。

consider other challenges that might，arise as we go about trying to make web。

applications that are used by more and，more users in particular taking a look。

at challenges that all arise in terms of，scalability as the programs get bigger。

and also security of what security，vulnerabilities open themselves up as we。

begin to design our web applications，using Python and JavaScript so more on。



![](img/80e431d7e9ec5e03b4e38d52dddd2733_17.png)
# 【双语字幕+资料下载】哈佛 CS50-WEB ｜ 基于Python ／ JavaScript的Web编程(2020·完整版) - P24：L8- 拓展性与安全 1 (可扩展性，负载均衡，自动伸缩) - ShowMeAI - BV1gL411x7NY

![](img/9e1a5fe55e2bc95a425be60a3f404bd4_0.png)

[Music]，all right welcome back everyone to web，programming with Python and JavaScript。

and for our final topic we're going to，explore scalability and security so so。

far in the class we've been building web，applications and we've been building web。

applications that work on our own，computer but if we want to take those。

web applications and deploy them to the，world so people all across the internet。

can begin to use them then we're going，to need to host our web application on。

some sort of web server some dedicated，piece of hardware that is listening for。

web requests and responding to them with，the response that we would like for our。

web application to deliver and when we，do so this introduces a whole bunch of。

interesting issues surrounding，scalability and security so we'll take a。

look at these issues today beginning，with problems concerning scalability。

what those problems are and how we might，go about addressing them so when we。

deploy our web applications we deploy，them by putting them onto a web server。

that I'm here just representing with，this rectangle but all the server is is。

some dedicated computer some piece of，hardware that is listening for incoming。

requests so we'll draw this line to，represent an incoming web request from a。

user the server takes that request and，responds to it but ultimately our web。

application isn't just going to be，servicing one user if it becomes popular。

it might have many users that are all。

![](img/9e1a5fe55e2bc95a425be60a3f404bd4_2.png)

trying to connect to that server at the，same time and as multiple people start。

to connect to that server at the same，time here's where we start to deal with。

issues of scalability a single computer，a single server can only service so many。

users at any given time and so therefore，we need to think in advance about how。

we're going to deal with those issues of，scale but the first question before we。

even get there is where these servers，actually exist and nowadays there are。

two main options for where these servers。

![](img/9e1a5fe55e2bc95a425be60a3f404bd4_4.png)

can exist these services can be on the，cloud or they can be on-premise and。

on-premise servers you might imagine as，if a company is running their own web。

application on-premise servers or，servers that are inside of the company's。

walls the company owns the physical，servers maybe on some server racks。

inside of a room and therefore they have，very direct control over all of the。

servers exactly what kind of servers，they are exactly what software is。

running on them they can go and，physically look at the servers and debug。

them if need be in order to make sure，that any issues are dealt with but。

increasingly we're starting to move into，a world where cloud computing is。

becoming increasingly popular，we're in cloud computing rather than，have dedicated servers that are。

on-premise we have servers that are，somewhere in the cloud where cloud。

computing companies like Amazon or，Google or Microsoft are able to run。

their own servers and we simply use，those servers that are provided by those。

third-party smooth let's Amazon or，Google or Microsoft or someone else and。

there are trade-offs here with cloud，computing we no longer have an as direct。

control over the machines themselves，because they're not on premise we can't。

physically manipulate those computers，but we have the advantage of not having。

to worry about dealing with physical，objects that are inside of the premise。

of the company whose servers we'd like，to run code for the when it's on the。

cloud everything is managed externally，by some other company and we can simply。

use the servers that we need to and，we'll see that this lends itself to。

other benefits as well as we might need，more servers as we start to get more。

sophisticated web applications that need，more users these cloud computing。

companies can allow us to create web，applications that are able to scale。

across multiple different servers as we，start to get more and more users but。

we'll discuss those issues of scale as。

![](img/9e1a5fe55e2bc95a425be60a3f404bd4_6.png)

we get to them the question we need to，ask after we have these servers whether。

they're servers that are on-premise or，servers that are operating somewhere in。

the cloud is how many can those use，users，can the server actually service at any。

given time and that's going to vary it's，going to vary based on the size of the。

server the computing power of the server，and it's going to be dependent upon how。

different how long it takes to process，any particular users request if user。

requests are quite expensive it might，mean that there are fewer users that can。

be serviced at any given time and it's，for that reason that a helpful tool is。

to do some kind of benchmarking some，process of trying to do some analysis on。

how many users a server can actually be，handling at any particular time and。

there are numerous different tools that，allow us to do this kind of benchmarking。

appache by bench or otherwise known as，a/b is a popular tool for doing this。

kind of thing but benchmarking is going，to be useful so that we know how many。

users one particular server can handle，maybe it can handle 50 users maybe a can。

handle 100 users maybe it can handle，more at any given time but ultimately。

it's going to be some finite limit every，computer just has some finite amount of。

resources and servers are no exception，there's going to be some number of users，after。

which the server's not going to be able，to handle it so what do we do in that。

situation what do we do if our server，can only handle 100 users at any given。

time but 101 users are trying to use our，web application at the same time。

something needs to change we need to，deal with some sort of scaling to make。

sure that our web application can scale，and there are a couple of different。

types of scaling that we can try one，approach is to do what's called vertical。

scaling which might be the simplest way，you could imagine scaling if this server。

is not good enough for handling the，number of users that we needed to handle。

we'll then just get a bigger serve in，vertical scaling we just take the server。

and get a bigger server a more powerful，server a server that can handle more。

users than any given time it's going to，cost more but if we need it to handle。

more users we can just get a bigger，problem，this approach is fairly simple it just。

involves swapping out one server for，another one that can handle more users。

concurrently but it also has drawbacks，right there's some limit to how big the。

server can be to how many users any，physical one server is going to be able。

to handle because there's a physical，limitation and on what is the biggest。

fastest most powerful server we could，possibly get so when vertical scaling。

ends up not being enough an alternative，as you might imagine is what's known as。

horizontal scaling and the idea behind，horizontal scaling is that when one。

server isn't enough to be able to，service all of the users that might be。

trying to use a web application at the，same time well then we can take the。

approach of saying well rather than just，using one server let's go ahead and。

split it up into two different servers，we now have two servers that are both。

running the web application and now，effectively we've been able to double。

the number of users that this web，application can handle rather than just。

a single server that can serve us 100，users if we have two of them now we can。

service 200 users at any given time if，you imagine 100 of them using server a。

over here and 100 of them using server B，over there but this then lends itself to。

some other questions that we have to，answer which is how do these servers get。

their users in the first place like when，a user requests a webpage how does that。

user get directed either to server a or，to server B it seems that they need some，decide。

whether to go one direction or another，and it's for that reason that we might。

introduce another piece of hardware into，this picture and that additional piece。

of hardware is what we might call a load，balancer and a load balancer is just。

another piece of hardware that is going，to sit in front of these servers so to。

speak in other words when a user makes a，request to a web page rather than。

immediately getting that request to one，of these web servers the request is。

first going to go through this load，balancer where the request first comes。

into the load balancer and the load，balancer then decides whether to send。

that request to server a or to send that，request to server B and this process is。

likely less expensive than actually，dealing with and processing that request。

so the load balancer is effectively just，acting as a dispatcher it waits for。

those requests to come in and when the，requests do come in the load balancer。

directs those requests either to go to，one server or to another and you might。

imagine the story where we have more，than just two servers maybe we have many。

servers and the load balancer is just，going to balance between all of those。

different servers and this process of，deciding which server to send a request。

to is known as load balancing which is，what the load balancer is ultimately。

doing and there are various different，methods that you might use in order to。

perform this load balancing so you might，imagine thinking about this intuitively。

how would the load balancer decide given，some request should we send the request。

to this router to the server or should，we send the request to some other server。

instead and there are many different，approaches that our load balancer might。

take and here are just a couple random，choice might be the simplest of options。

given a user that shows up and tries to，make a request to our web server the。

load balancer first takes a look at the，user and just randomly assigns them to。

one of the various different servers，that might be processing that request if。

they're 10 different servers it randomly，chooses among those 10 servers to decide。

which of them is going to be servicing，that request this has the advantage of。

being very simple it's just a quick，calculation the computers can pretty。

readily generate random numbers and，based on that random number the computer。

can dispatch the user to one server or，to another server but it might not be。

the best option because if we happen to，get unlucky we might end up with many。

more users on one server than another or，in such，might end up with servers that are。

entirely unused if it just so happens，that we don't end up randomly selecting。

that server now in practice with many，users that are all using this load。

balance that are all being dispatched，odds are high that eventually all of。

them will be used but it might not be a，totally even distribution and so for。

that reason another approach you might，take is a round-robin approach where the。

approach is instead for the very first，user go ahead and assign that user to。

server number one for the next user to，assign them the server number two and。

maybe if there are five servers you say，the third user goes to server three user。

four goes to server for user five goes，to server five and then user six goes。

back to server number one you basically，rotate going one through five and then。

once you've assigned some one to each of，the servers you go back to the beginning。

and this is also a relatively easy thing，to implement because you can simply just。

keep count some were in the load，balancer saying what was the most recent。

server that I assigned a user to and the，next time a request comes in go ahead。

and assign it to the next server and the，next server after that effectively is。

doing a round-robin style approach where，you go through all the servers once。

before going through those servers again，now this might seem better than random。

choice in the sense that it's going to，more equitably decide whether to assign。

any particular request to any particular，server but it also suffers from certain。

problems that round-robin might be great，but if some requests take longer than。

other requests we might also get unlucky，and the requests that are taking longer。

might end up all going to one of the，servers as opposed to another server so。

there are other approaches that we might，want to go to as well for example。

something like fewest connections where，the approach there is to say go ahead。

and when a user makes a request the load，balancer should pick which of the。

servers currently has the fewest，connections the fewest active。

connections from other users and other，requests that are currently connected to。

those servers instead and by choosing，the server that happens to have the。

fewest connections you're probably going，to do a better job of trying to balance。

out between all of the various different，requests that might be happening inside。

of your web application and while this，might do a better job there are。

trade-offs here as well but it might be，more expensive for example to compute。

which of the servers happens to have the，fewest number of connections whereas。

it's much easier just to say choose a，server at random，or to do the round-robin style approach。

of just one two three four five one two，three four five again and again and。

again but all of these approaches，naively have yet another problem which。

has to do with sessions and you'll，recall that sessions we used whenever we。

wanted to store information about the，users current interaction with the web。

application when you log into a website，like you log into your email or you log。

into Amazon for example and then you，come back to that website or visit。

another page on that website making，another request for example it's not the。

case that you have to sign in yet again，that the web browser is totally。

forgotten who you are when I go back to，my mail account or when I go back to。

Amazon for a second time my mail account，or Amazon remembers me from the last。

time that I visited I have some sort of，session where it's keeping track of who。

is logged in maybe information about，what I've been doing on the page and。

allows me to continue interacting with，the web application even if I'm making。

multiple requests and this you might，imagine could be a problem for this type。

of load balancing but if I have multiple，different servers imagine if I try to。

log in to a website and the first time I，make a request，I'm directed to server number one and。

I'm now logged in on server number one，but then I make another request。

I'm directed back to the load balancer，and maybe the load balancer this time。

decides to send me to server number two，but if the session is stored in server。

number one somewhere server number one，remembers Who I am and what I'm doing。

then server number two is not going to，Know Who I am，and therefore it's not going to remember。

that I've already logged into this web，application and as a result I might be。

prompted to log in again and if I we go，make another request and I end up on yet。

another server I might be logged out，again and have to login for a third time。

so the problem comes about when our load，balancing happens but we're not doing so。

in a session aware way that our load，balancer isn't caring about when a user。

visits a page and then visits another，page on the same web application again。

because we want to remember information，from the previous time that the user was。

here so how can we solve this problem，how can we make sure that when we do。

this load balancing across multiple，different servers that we do so in a。

session and we're way well there are，multiple different approaches to session，aware。

load-balancing one approach is this，general idea known as sticky sessions。

where the idea is that when I come back，to the load balancer the load balancer。

will remember what server I was sent to，last time and send me there yet again so。

for example if I log into a website once，and I'm directed to server number two。

for example then the next time I visit，this web application even if I should be。

directed to server 3 or 4 according to，random choice or according to fewest。

connections or any of these other load，balancing methods the load balancer。

should remember that last time I came to，this site I got directed to server。

number 2 and so this time the load，balancer is going to direct me to server。

number 2 yet again that way server，number 2 which contains information，again。

and remember who it is that I am and，it's not gonna make me log in again into。

the exact same website for a second time，for example and so sticky sessions are。

one way of dealing with this problem but，again with all of these approaches and。

this will be a recurring theme as we，talk about scalability and security and。

there are trade-offs here that are，trade-off to the sticky sessions is that。

it's possible that one of these servers，is going to end up getting far more load。

than another if one server happens to，have a lot of users that keep coming。

back to the website and keep requesting，additional pages but other pages other。

servers might have had users that，decided not to come back for example and。

so there's a difference in utilization，where some of our servers might be more。

heavily utilized than other servers and，we're not doing a very good job of。

balancing between them and so one，approach is to store sessions inside of。

the database rather than store，information about sessions inside of the。

server themselves so that if I get，directed to another server that other。

server doesn't remember Who I am doesn't，remember information about my。

interaction with this website if we，instead choose to store sessions inside。

of a database in a particular inside of，a database that all of the servers have。

the ability to access well then it，doesn't matter which of the servers I。

get directed to and which server the，load balancer decides to send me to。

because regardless of which server I end，up getting sent to the session。

information is in the database and each，of the servers can connect to the。

database to find out who I am to find，out whether I've logged into the site，recognize。

and so that might be one approach as，well another approach is to store，sessions on the client side。

we've talked a little bit about this，idea of cookies which can be stored。

where the web browser can set a cookie，so that your web browser is able to。

present that cookie the next time that，makes a request to the same web。

application and inside this cookie you，can store a whole bunch of information。

including information about the session，you might inside of a cookie store。

information about what user is currently，logged in for example or other session。

related information but here to their，drawbacks if you're not careful。

someone could manipulate that cookie and，maybe pretend to be something else and。

so for that reason you might want to do，some encryption or some kind of sign-in。

to make sure that you can't fake a，you're not，but another concern is that as you start。

to store more and more information，inside of these cookies these cookies。

keep get sending back and forth between，the server and the client every time a。

request is made that can start to get，expensive to more and more information。

passing back and forth between the，client and between the server so lots of。

possible approaches no one approach that，is necessarily the right approach or the。

best approach to use in any cases but，things to be aware of things to think。

about as we begin to deal with these，issues of scale of making sure we have。

multiple servers that are available for，usage in case we do need it but also。

making sure that when we do so we don't，break the user experience we don't。

result in a situation where a user is，logged in but then suddenly isn't logged。

in at all and so horizontal scaling，gives us this kind of capacity the。

ability to have multiple different，servers all of which can be dealing with。

user requests and responding to those，user requests as well but a reasonable。

question asked is how many of those，servers do we need now we can use。

benchmarking to try to estimate this if，we have an estimate of how many users。

are going to be on our website at any，given time we can benchmark and see how。

many users there can be handled by a，single server and extrapolate based on。

that information to infer how many，servers we might need in our web。

application to be able to service all of，these different users but it might be。

the case that our web application，doesn't always have the same number of。

users maybe sometimes they're going to，be far more users than another time you。

might imagine for example that in a news，organizations web site like the。

application for a newspaper when there's，breaking news some big story there's。

going to be a lot more people that are，all trying to access the website at the。

same time than in other times so one，approach might be like consider the。

maximum what is the most number of users，that ever might be trying to use our web。

application at any given time and choose，a number of servers based on that。

maximum so that no matter how high the，number of users get we will have enough。

servers to be able to service all of，those users but that's probably not a。

great economical choice if in the vast，majority of cases there will be far。

fewer users in that case you're gonna，have a lot of suberin servers that are。

underutilized where you don't need that，many servers but you're still paying for。

the electricity for keeping all of them，running which might not be an ideal。

choice either so one solution to this，quite popular especially in this world。

of cloud computing is the idea of auto，scaling or you can have an auto scaler。

to say that you know what let's start，with for example two servers but if。

there's enough traffic to the website if，enough people are making requests to the。

website maybe it's a peak time where，people are using the website go ahead。

and scale up go ahead and add a third，server where now our load balancer can。

balance between all three of those，servers and if even more traffic ends up。

coming to the website more users are，trying to use this application all at。

the same time well then we can go ahead，and add a fourth server as well and we。

can continue to do that most Auto，scalars will let you configure for。

example a minimum number of servers and，a maximum number of servers and。

dependent on how many users happen to be，using your web application at any given。

time the autoscaler can scale up or，scale down adding new servers as more。

users come to the website removing，servers as fewer users or using the。

website as well and so this can be a，nice solution to this problem of scale。

where you don't have to worry about how，many servers there are it just Auto。

scales entirely on its own now there are，trade-offs here to that this auto。

scaling process might take time and if a，lot of users all come into your website。

all of the exact same time well it's，gonna take some time to be able to add。

all these additional servers to start，them up and so there might be some。

trade-offs there to where you might not，be able to service all of those users。

immediately and another problem we're，thinking about，as you add more and more of these。

servers you introduce opportunities for，failure now it's better than having a。

single server where if that single，server fails now suddenly the entire web。

application doesn't work at all that's，what we generally call a single point of。

failure a single place where if it fails，the entire system is going to be broken。

one advantage of having multiple servers，is that we no longer have a single。

server that acts as a point of failure，if one of the servers goes down then。

ideally our load balancer should be able，to know based on that information to no。

longer send requests to that particular，server to instead balance the load。

across the remaining three servers，instead now if there's an interesting。

question there as well which is how does，the load balancer know that this server。

is no longer responding that for some，reasons have some sort of error that。

it's not able to process requests，appropriately well there are multiple。

ways you can do this but one of the most，common is what simply known as a。

heartbeat where effectively every so，often every some number of seconds the。

load balancer pings all the server's，just sends a quick request to all the。

servers and all the servers are supposed，to respond back and using that。

information the load balancer knows a，little bit about the latency of each of。

the servers how long it took for the，server to respond to the request but。

also it can get information about，whether or not the server is functioning。

properly that if one of the server's，doesn't respond to the ping well then。

the load balancer knows that there's，probably something wrong with the server。

that we probably shouldn't be directing，more users to that server at all and so。

this can solve for the problem of a，single point of failure by allowing。

ourselves multiple servers where if any，one of the server's fails the load。

balancer learns about that via heartbeat，and then based on that information can。

begin to redirect traffic to the other，servers instead now one thing you might。

notice is that even in this picture now，the load balancer appears to be like a。

single point of failure where if the，load balancer happens to fail well now。

nothing is going to work because a load，balancer is the one responsible for。

directing traffic to all of these，various different servers and so even。

there there's no single server that has，a point of failure this load balancer。

also appears to be a single point of，failure and that's definitely true and。

you might imagine instead of having，multiple load balancers where if one，load balancer goes down。

another load balancer can swoop in，acting as a hot spare where it picks up。

all the traffic that was originally，going to the first load balancer and if。

it ever goes down a second one is ready，to take its place and it might also be。

doing this kind of heartbeat process，checking up on the first load balancer。

and if all as well the second load，balancer doesn't have to do anything but。

if the first load balancer ever were to，fail will then the second load balancer。

can step in and begin servicing those，requests directing them to all of these。

individual servers as well and so there，- another opportunity to think about。

where the single points of failure are，and thinking about how we might address。

those single points of failure in order，to make sure that our web applications。

are scalable so that then deals with，issues about how we might go about。

scaling up these servers but ultimately，the servers are not the entirety of the。

story that inside of our applications we，mostly been have writing web。

applications that interact and deal with，data in some way and there are multiple。

different databases that we've talked，about sequel light has been the default。

one that Django provides to us which，just stores data inside of a file but as。

we begin to grow our applications as we，want to begin to scale them it's quite。

popular in quite common to put databases，entirely some more separate have a。

separate database server running，somewhere else where the servers are all。

communicating with that database whether，it's running my sequel or Postgres of。

some other database system instead and，all of the servers that have access to。

that database and so they're - are our，considerations that we need to take into。

account issues of how it is that we go，about scaling up these databases that in。

this picture for example you might，imagine a load balancer that is。

communicating with two servers but both，of those servers for example need to be。

communicating with this database and，much like any server can only handle。

some number of requests some number of，users at any given time databases - can。

only handle some number of requests some，concurrent number of connections at any。

given time and so we need to begin to，think about issues of how it is that we。

scale these databases as well in order，to be able to handle more and more users。

now one approach the first thing we，might try to do is something called。

database partitioning effectively，splitting up what is a big data set into。

multiple different parts to that data，set and we've already seen some examples。

of database partitioning，we've seen one example where for example。

when we talked about sequel we looked at，a table of flights where each flight had。

an Origin City the Origin city's airport，code the destination city the。

destination Cities Airport code and some。

![](img/9e1a5fe55e2bc95a425be60a3f404bd4_8.png)

number of minutes the duration for that，particular flight and we decided that。

storing all of this data in a single，table probably wasn't the best idea and。

instead we wanted to split that data up，in a type of partitioning where instead。

we said alright let's just have one，table that will have all of the airports。

and so each Airport gets its own row，inside of this airport's table and we。

also had another table which was just，the flights table which rather than。

storing all of those columns just mapped，two airports to each other that with any。

given flight it has an Origin ID meaning，which object which row in the origin of。

airports table is represented by the，flight and then which row in the。

airport's table is going to represent，the destination for that flight so we。

took one table and effectively split it，up into multiple tables each of which。

ultimately had fewer columns and this，might be something we call it the。

vertical partitioning of a database，where instead of just having single big。

long tables we split them up into，multiple tables each of which have fewer。

columns that are able to represent data，in a more relational way and that's。

something we've seen before too but in，addition to vertical partitioning we can。

also do horizontal partitioning where，the idea there is that we take a table。

and just split it up into multiple，tables that are all storing effectively。

the same data but split up into，different data sets so the same type of。

data but just in different tables where，we might have originally had a flights。

table and instead we split it up into a，domestic flights table and an。

international flights table each of，these tables still has the exact same。

columns they still have a destination，column they still have an Origin column。

they still have a duration column for，example but we've just now taken the。

data that used to be in one table and，split up that data into two or more。

multiple different tables instead one，for all the domestic flights one for all。

the international flights and the，advantage there is that we no longer。

need to search through the entirety of，the data set if we're just looking for。

one domestic flight for example if you，know the flight you're looking for is a，domestic flight。

well then it can be more efficient to，just search the flights domestic table。

and not bother searching through the，flights international table and so for。

intelligent about how we choose to take，a table and split it up into multiple。

different tables the effect of that is，that we can often improve the efficiency。

of our searches the efficiency of our，operations because we're dealing with。

multiple smaller tables where these，operations can come faster one drawback。

though is that as we begin to split data，across multiple different tables it。

becomes more expensive if ever we need，to join this data back together and。

connect all the domestic and，international flights running separate。

queries on each and so in that case，we'll want to think about trying to。

separate our data in such a way that，generally we're only going to need to。

deal with one table or the other at any，given time and so domestic and。

international might be a reasonable way，to split up our flights table。

because maybe most of the time our，Airport just cares about searching。

domestic flights if we're know we're，looking for one kind of flight or just。

cares about searching for international，flights if there are different people or。

different computers that are gonna，handle each of those different types of。

systems and so partitioning our database，can sometimes help with issues of scale。

by making it faster to search through，large amounts of data and being able to。

represent data a little bit more cleanly，but it still seems to represent a single。

point of failure that we have multiple，servers now that are all connected to。

the same database and there again is a，single point of failure if the database。

fails for some reason well now suddenly，none of our web application is going to。

work because all of those servers are，all connected to that exact same。

database and so it's for that reason，that we might just as we tried to add。

more servers in order to solve the，problem of a single point of failure。

with our servers we might also try，database replication that rather than。

just have a single database in our web，application in order to guard against。

potential failure we might replicate our，database has multiple different。

databases and therefore reduce the，likelihood that our application entirely。

fails and there are a couple of，approaches we can use for database。

replication two of the most common are，what are known as single primary。

replication and multi primary，replication and in single primary。

database replication we have multiple，different databases but。

one of those databases is considered to，be the primary database and what we mean。

by a primary database is a database to，which we can both read data meaning like。

select rows from the table but also，write data meaning insert rows or update。

rows or delete rows to any of those，tables so in single primary replication。

we have a single database where we can，both read and write and we have some。

number of other databases in this case，two other databases from which we can。

only read data so we can get data from，those databases but we can't update or。

insert or delete from those databases，and now we need some mechanism to make。

sure that all of these databases are，kept in sync and ultimately what that。

means is that anytime the database，changes all of the databases are。

informed now the only database that can，change is our primary one this is the。

only one that can be written to the only，one that allows for the data to change。

the others are read-only so anytime this，primary database updates or changes in。

some way it needs to inform the other，databases of that update and so it。

informs the other databases of that，update and now all of the databases are。

kept in sync where if you try and run a，query on any of these databases to。

select and get some information you'll，get the same results from all of these。

various different databases now the，single primary approach has some。

drawbacks it has the drawback of only，one of these databases can be written to。

so if you have a lot of users that are，all trying to write data to the database。

at the exact same time well there might，be some issues here where this one。

database is going to be carrying all of，that load for all of the people that。

might be trying to update and change，that database and it also has a slightly。

smaller version of the same problem of a，single point of failure there's no。

longer a single point of failure for，reading from that data that if you want。

to read from the data and one of the，databases goes out you can read data。

from any of the other databases and，they'll work just fine but it does have。

the drawback that if this database fails，if our primary database fails well then。

we're no longer able to write data that，if we want to update data inside of our。

database this one database is no longer，going to be operational and none of the。

other databases are going to allow us to，write new changes so there are a couple。

of approaches we can use to try to solve，this problem，one approach though is instead of having。

a single primary database a single，database to which we can read and write。

to use a multi primary approach and in，the multi primary approach we have。

multiple databases all of which we can，read and write to we can select rows。

from all the databases and we can insert，an update and delete rows to all of。

these databases as well but now the，synchronization process becomes a little。

bit trickier and here now is the trade，off and now we've replicated the number。

of reads and writes we can do by having，many databases to which we can read data。

and write data but anytime any of these，databases changes every database needs。

to inform all of the other databases of，those updates and that's certainly going。

to take some amount of time it，introduces some complexity into our，system as well。

and it also introduces the possibility，for conflicts that you might imagine。

situations where if two people are，editing similar data at the same time。

that you might run into a number of，different types of conflicts so one type。

of conflict for example would be an，update conflict if I try to edit one row。

in one database and someone else tries，to edit the same row in another database。

when they sync up with each other via，this update process our database system。

needs some way to decide how it's going，to resolve those various different。

updates another conflict might be a，uniqueness conflict we've seen in the。

case of databases in sequel that when，we're designing our tables I can specify。

that this particular field should be a，unique field common one being the ID。

field for example where every single Row，is going to have its own unique ID well。

what happens if two people try to insert，data at the same time into two different。

databases they're each given a unique ID，but it's the same ID on both of the。

databases because neither database knows，that the other database is added a new。

row yet so when they sync back up we，might run into uniqueness conflict where。

two different databases have assigned，the same exact ID to multiple different。

entries and so we need some way to be，able to resolve those conflicts as well。

and there are many other conflicts you，might imagine trying to deal with one。

example being for instance delete，conflicts where one person tries to。

delete a row and another person tries to，update that row well which should take。

precedence should we update the rows，should we delete the row we need some。

way to be able to make those decisions，because，there is some latency between when a。

change is made to a database and when，that database is able to communicate。

with another database so these issues of，scale these issues of the。

synchronization are always going to come，up as we start to deal with programs。

that are interacting with more and more，of this kind of data and as a result we。

need to design more and more，sophisticated systems that are able to。

deal with those issues of scale now，ultimately we'd ideally like to reduce。

the number of different of these，database servers that we have that every。

additional database server is going to，cost time it's gonna cost resources that。

cost money in terms of keeping all of，these servers running and so ideally。

we'd like not to have to talk to this，database if we don't need to so you。

might imagine for example a news，organizations website something like the。

front page of the New York Times if you，go to the home page of the New York。

Times website it displays all of the，day's headlines with images and with。

information about what each of the，stories are about for example and you。

might imagine that the way they're doing，something like this is that they have。

some kind of database that's storing all，of these news articles and when you。

visit the front page of the New York，Times it's going to do some kind of。

database query selecting all of the，recent top headlines for example and。

rendering all of that information in an，HTML page that you can see and that。

would certainly work but if a lot of，people are all requesting the front page。

at the same time well it probably，doesn't make all that much sense if the。

web application every time is making a，database query getting the latest。

article ISM and then displaying that，information to all the users because the。


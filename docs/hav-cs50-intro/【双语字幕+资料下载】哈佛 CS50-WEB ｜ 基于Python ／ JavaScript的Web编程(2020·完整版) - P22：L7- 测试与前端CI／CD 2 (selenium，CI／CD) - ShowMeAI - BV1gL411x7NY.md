# 【双语字幕+资料下载】哈佛 CS50-WEB ｜ 基于Python ／ JavaScript的Web编程(2020·完整版) - P22：L7- 测试与前端CI／CD 2 (selenium，CI／CD) - ShowMeAI - BV1gL411x7NY

can you actually feel confident in those，changes themselves so now let's take。

this idea of using unit tests to be able，to write these tests that verify that a。

function works and apply it to something，like a web application like a web。

application written in Jango that we，would like to now use in order to be。

able to test to make sure that various，different functions inside of our Jango。

web application work as well so what I'm，gonna do is actually take a look at the。

airline program that we wrote back when，we were first talking about Jango and。

force talking about storing data inside，of databases and I'm going to open up。

models pi where you see that I've made，one addition to our definition of a。

flight and recall from before when we，first introduced this idea of defining a。

model inside of our application for a，flight inside of an airline we gave that。

model three properties it had an origin，and a destination where both origin and。

destination referenced an airport object，where an airport object was an object we。

defined separately but a flight has an，origin Airport and a destination Airport。

and in addition to that every flight has，a duration some number of minutes long。

that that flight is going to last and I，might like to have some way to validate。

to verify that a flight is a valid，flight that there isn't some error。

somewhere in how the data was entered，into the database I would like to just。

generally make sure that given a flight，I can check to make sure。

it's a valid flight and what does it，mean for a flight to be valid well in。

general given these particular fields，I'll say there are two things that need。

to be true for a flight to be valid the，different，that's condition number one it wouldn't。

make sense to have a flight whose origin，and destination are the same Airport and。

condition number two the duration of the，flight needs to be greater than zero。

minutes if ever the duration is zero or，the duration is negative that probably。

indicates to me that there was some sort，of mistake in data entry or some problem。

that happened with how it is that these，flights were configured so I want to。

make sure that the duration is greater，than zero and those then are my two。

conditions for what makes a valid flight，and I've in fact written a function here。

called is valid flight that just works，on this flight class that simply checks。

given a flight make sure that it is in，fact valid and the way it's doing that。

is by checking for these two conditions，that I've just described it's checking。

to make sure that the origin is not，equal to the destination it's checking。

to make sure that the duration of the，flight is greater than or equal to zero。

and maybe I should change that to，greater then to make sure it's entirely。

positive but this then is my definition，for what it means for something to be a。

valid flight and what I'd like to do now，is test these various different parts of。

my application I have this is valid，flight function inside a flight that I。

might like to test as well but we also，have all of these other properties that。

I would like to test these relationships，that a flight has an origin and a。

destination we have passengers that can，be associated with flights so there's。

lots of relationships between my data，that I would like to test and verify to。

make sure they work the way we would，expect it to so to do that whenever we。

create an application in Django like，this flights application here we were。

also given this test dot PI file and we，haven't yet used the test pilot v phone。

file for anything but what it's supposed，to be used for is for writing these。

sorts of tests testing that verifies，that our application behaves the way。

that we want it to behave so let's go，ahead now and open up test stop by and。

see what happens to be in here what we，can do is we can define a subclass of。

test case which behaves very similar to，unit test ins based on that same idea。

I'll define a new class called flight，the，tests that I would like to run on my。

flight's application it's the things to，know about this is that first I might。

need to do some initial setup in order，to make sure that there's some data that。

I can actually work with and test with，and what Jango will do when I go ahead。

and run these unit tests is that it will，create an entirely separate database for。

me just for testing purposes that we，have one database that contains all the。

information that actually pertains to，the flights that are actually there on。

my web server but we might also like to，just test things with some dummy flights。

and some dummy airports just to make，sure that things are working and then。

once we're confident things are working，then we can deploy our web application。

to let actual users begin to use，whatever new features we've added to the。

web application for example so inside of，this database I might need to do some。

initial setup and I can do so by，defining a setup function inside of my。

test case class this is a special，function and Jango knows that when it's。

running these tests it should first do，any of the setup steps that we need to。

do and so how are we doing this well，what we're doing is inside of the setup。

we're going to just add some sample data，into the test database again this won't。

touch the database that users actually，see and actually interact with this is。

just our test one for testing purposes，and we'll start by going ahead and。

creating some airports so Airport，objects create and then specifying what。

the values for these fields should be，AAA，for city a and an airport whose code is。

BBB for city be just dummy airport names，they're not real airports but just use。

for testing purposes and I'll save those，Airport objects inside of these values。

a1 and a2 and beneath that what I'm，gonna do next is go ahead and create。

some flights where I create using flight，objects don't create three different。

flights one that goes from a1 to a2 with，the duration of 100 minutes one from a 1。

to a 1 with the duration of 200 minutes，one from a1 to a2 with the duration of。

negative 100 minutes so I have a whole，bunch of these flights now that I would。

like to test that I would like to make，sure work in some predetermined or。

expected way and so now if I scroll down，we can see that I have a whole bunch of。

these various different tests here is，one test that just tests，the departures count so every airport。

has access to a field called departures，which ideally should be like how many。

flights are departing from that Airport，and I'd like to make sure that。

departures count works the way I，expected to so here I go ahead and get。

the airport whose code is AAA and now，using unit tests like syntax I would。

like to say self dot assert equal so，assert true verifies that something is。

true assert false verifies that，something is false assert equal verifies。

that two numbers are equal to each other，and here I'd like to verify that a。

departure is dot count if I take airport，a and count how many flights are。

departing from that Airport that that，should be three so just verifying that。

that works and then after that if this，test passes then I can be confident that。

elsewhere in my program if I take an，airport and call that Airport dot。

departures dot count I can feel pretty，confident that that is going to work the。

way I would expect it to I can do the，same thing for arrivals get the airport。

and assert that a done arrivals count，that that is going to be equal to the。

number one if there's only one flight，that arrives at airport a one for，example so that tests these。

relationships and I can also now test，the is valid flight function as well。

that here I get my two airports a one，and A two this is the one who was code。

is a a a this is someone whose code is，BBB I'll go ahead and get the flight。

whose origin is a one whose destination，is a two whose duration is one hundred。

and let me just assert true that this，flight is going to be a valid flight。

because this flight is valid the origin，is different from the destination its。

duration is some positive number of，minutes and so I should feel pretty。

confident that this is going to be a，valid flight that I can verify by。

calling self dot a third true I can do，the same thing for testing for an。

invalid flight testing for an invalid，flight because the destination is bad I。

can get the flight Airport a one and get，the flight whose origin and destination。

are both a one and now let me self dot，assert false say that this should not be。

a valid flight because the origin in the，destination are the same what's the。

other way a flight can be invalid well，if I can be invalid because of its。



![](img/dfea2e7985faaf65128c8f32e58edce0_1.png)

duration so I could say something like，eight，and get me the flight whose origin is a。

a one destination is a tomb but the，duration is negative 100 minutes that。

was one of the flights as well and well，that should not be a valid flight so。

I'll say self-doubt assert false is，valid flight because when I call it is。

valid flight on that flight it shouldn't，be valid because the duration makes it。

an invalid flight so here now I've，defined a whole bunch of tests and。

they're more down below that we'll take，a look at in a moment as well but I've。

defined a whole bunch of these flights，now or a bunch of these tests and now。

I'd like to run them and the way that I，can run tests in Gengo is via a managed。

by command management Piatt has a whole，bunch of different commands that we can。

run we've seen like make migrations and，migrate and run server but one of them。

as well is if I go into airline zero I，can say Python managed PI test that's。

just going to run all of my tests and，alright it seems that we ran ten tests。

but two of them failed so let's go ahead，and see why do those two tests fail well。

the way to read this is that we get this，heading any time a test failed and so we。

failed the test invalid flight，destination function and we failed the。

test invalid flight duration function，and docstrings could have helped me to。

know what it is that these tests are，exactly doing but it seems that true is。

not false I want to do assert that this，should not be a valid flight that it。

should be false but for some reason，these appear to be valid flights so。

something seems wrong with is valid，flight where it's returning true when it。

should be returning false and so this，then gives me a place to start looking I。

can say all right let me go to is valid。

![](img/dfea2e7985faaf65128c8f32e58edce0_3.png)

flight and make sure that function is，correct so I go back into models dot PI。

I'll take another look at is valid，flight maybe I'll think through the。

logic again all right I wanted to check，that self that origin is not self that。

destination I wanted to check that the，duration is greater than or equal to。

zero I could change this to greater them，but I don't think that's the issue。

because my a duration was negative and，so that already should have been invalid。

but the other thing I might realize，looking at this now is that okay the。

logical connectives that I have used was，not the right one I want to check that。

for it to be a valid flight it needs to，satisfy both of the conditions the。

origin and the destination need to be，different and the duration of the flight。

needs to be greater than，zero for example and here I've used or。

instead of and so I can just change it，alright and hopefully that will fix。



![](img/dfea2e7985faaf65128c8f32e58edce0_5.png)

things and to verify as much I can rerun，Python managed PI test go ahead and。

press return it's going to check things，that ran ten tests everything is OK and。

alright it seems that now I have passed，all of these tests and notice here at。

the top it created a test database so it，just created a test database for me in。

order to do all this testing work and，then it destroyed that test database at。

the end as well so none of my tests of，I'm adding data removing data it's not。

going to touch any of the actual data，inside of my database for the web。

application Jango will take care of the，process of keeping all of that separate。

for me by first calling that setup，function to make sure that my new test。



![](img/dfea2e7985faaf65128c8f32e58edce0_7.png)

database has everything that it needs to，so all right we now have the ability by。

using unit tests to be able to test，various different functions inside of。

our web application we first saw that we，could test a function like the is prime。

function just a Python function that we，wrote but we can also test things like。

functions on our models like checking to，make sure that a flight is valid。

checking to make sure that we can take a，flight and access all of the or take an。

airport and access all of its arrivals，and all of its departures but I'd like。

to do more than that especially for a，web application I'd like to check that。

like particular web pages work the way，that I want them to work and so to do。

that Gengo lets us simulate trying to，make requests and risk get responses to。

a web application and so let's go ahead，and look at some of these other tests as。

well here what we have is a function，called test index and what test index is。

going to do is it's just going to test，my default flights page to make sure。

that it works correctly so we start by，creating a client some client that's。

going to be interacting request and，response style then I'm going to call。

client get slash flights that is the，route that gets me the index page for。

all the flights and I'm saving that，inside of a variable called response。

whatever response I get back from trying，to get that page I would like to save。

inside of this variable called response，and now I can have multiple assert。

statements inside of the same test if I，would like to sometimes you might want。

to separate them but here I want，fact that the index page works and what。

that means is a couple of things it，means that response dot status code well。

that should be equal to two hundred two，hundred again meaning okay I want to。

make sure that whatever response I get，back that that is going to be a two。

hundred and if there was some sort of，error like a 404 because the page wasn't。

found or a five hundred because of some，internal server error I would like to。

know about that so let me first just，assert that the status code should be。

equal to two hundred but then Django，also lets me access the context for a。

response and what is the context will，recall again in Django when we rendered。

a template for example we called like，return render then provided the request。

and what page we were going to render，but we could also provide some context。

some Python dictionary describing all of，the values that we wanted to pass in to。

that template and Django's testing，framework gives us access to that。

context so that we can test to make sure，that it contains what we would expect it。

to contain and on the index page for all，my flights I would expect that to。

contain a listing of all of the flights，and we created three sample flights。

inside of this test database so I should。

![](img/dfea2e7985faaf65128c8f32e58edce0_9.png)

be able to assert that these two things，are equal response not context flights。

that gets me whatever was passed in as，flights in the context dot count。

well that better be three because I want，to make sure that they're exactly three。

results that come back when I look at，the context and access whatever happens。

to be inside of that flights key there，are other tests I can run as well so in。

this case I've gone ahead and gotten a，particular flight the flight who in this。

case had an origin of a1 and destination，of a1 and that was not a valid flight。

we'll go ahead and get it anyway because，it exists in the database and now I can。

get slash flights slash that flights ID，right because on my flights page I would。

like to be able to go to slash flights，slash one to get at flight number one。

and go to slash flight slash to to get，at flight number two so if I take some。

valid ID some ID of an actual flight F，and go to slash flights slash that ID。

well that should work it should have a，status code of 200，meanwhile though if I test an invalid。

flight page this is a Django command，that will get me the maximum value for。

the ID this ID underscore underscore max，gets me the biggest possible ID out of。

all of the flights that happen to exist，inside of my database if I go ahead and。

try and get slash flights slash max ID，plus one so a number that is one greater。

than any of the flights that were，already inside of my database well that。

shouldn't work there shouldn't be a page，for a flight that doesn't exist so here。

then I can assert equal that the status，code of what comes back that that is。

equal to 404 because I would expect that，page to return a 404 and finally I can。

also check various different contexts，for things about the passenger page so。

in this case I've added some sample，passengers to the database so inside of。

my test I can manipulate the database as，well adding data into the database and。

checking to make sure that when you，count up the number of passengers on a。

flight page that that is going to be，like the number 1 for example so a。

number of different tests that we can，then write in order to verify various。

different parts of our web application I，would like to verify not only that our。

database works the way we would expect，the database to work in terms of how。

functions on our models work in terms of，relationships between those models like。

the relationship between a flight and an，airport but we can also simulate a get。

request simulating the request to a page，and verify that the status code that。

comes back is what we would expect it to，be verify that the contents of the page。

contain the right contents verify that，the context that was passed into that。

template is correct as well and then all，of that can then be verified by saying。

something like Python managed PI test，then go ahead and running that and we。

see that in this case all the tests，happened to pass which means that。



![](img/dfea2e7985faaf65128c8f32e58edce0_11.png)

everything seems to be ok at least for，now so this then again very helpful as。

our web program start to get more，complex as we have multiple different。

models multiple different routes the，ability to test to make sure that if we。

change things in one part of the program，that it doesn't break things in another。

part that can be quite helpful too but，we haven't yet been able to test though。

is any interaction that's happening，exclusively in the browser that I've，been able to test a lot of。

things that are happening server-side，and recall that Django is all about。

working on writing this web server a，Python application that acts as a web。

server that listens for requests that，come in from users processes those using。

these various different views and models，and then provides them some sort of。

response back and we can test the，contents of that response things like。

does the status code match what we would，expect it to does the context match what。

we would expect it to but there's some，times where we would like to really。

simulate like a user clicking on buttons，and trying things on a page and making。

sure that page behaves we would like it，how we would like it to as well even if。

we're not using Django or even if we're，just dealing with the front-end so let's。

create like a sample JavaScript web page，that we might like to test now by using。

these sorts of ideas the ability to，automate the process of testing various。

different parts of our application to，verify that they do in fact work。

correctly what I'm going to do now is，we'll get out of the airline directory。

and I'm going to create a new file that，I'll call counter HTML and recall before。

we created a counter application using，just JavaScript or what the counter。

application did is it let me click a，button like an increase or a count。

button that just increment to the number，1 from 0 to 1 to 2 to 3 to 4 and so。

forth I'm gonna do the same thing here，we'll add a little more complexity。

though and give myself both an increase，button to add a number and a decrease。

button to decrease the number by one as，well so I'll go ahead and start with our。

usual doctype HTML and our HTML tag I'll，give this page a title of counter and。

now inside of the body of this page I，will go ahead and start with a big。

heading that just says 0 and then，beneath that I'll create two buttons。

I'll have one button which will be the，plus symbol and one button which will be。



![](img/dfea2e7985faaf65128c8f32e58edce0_13.png)

the minus symbol so now no JavaScript，yet this won't actually work but I can。



![](img/dfea2e7985faaf65128c8f32e58edce0_15.png)

go ahead and go into open counter HTML。

![](img/dfea2e7985faaf65128c8f32e58edce0_17.png)

and I can see that I now have 0 and I，have a plus and a minus button although。

those plus and minus buttons don't，actually do anything right now，so let's go ahead and make them do。

something let's give this button an ID，called increase，so that I can reference it later and。

give this button an ID called decrease，again so that I can reference it inside。

of my JavaScript and now in the head，section of my web page I'll add a script。

tag where I want to start running some，JavaScript once the page is done loading。

and to do that you'll recall I can say，document add eventlistener Dom content。

loaded to say go ahead and run this，function once the Dom is loaded once all。

the contents of this page have loaded，the way I would expect it to and what am。

I going to do well I first need a，variable something like let counter。

equals zero and then I can say all right，document query selector increase get me。

the element whose ID is increased，that's that plus button and when you are。

clicked let's go ahead and add an event，handler in the form of this callback。

function this function that will be，called when the increased button is。

clicked and what would I like to do well，I'd like to increase the counter go。

ahead and say counter plus plus and then，I'm going to update this h1 that。

currently contains zero document query，selector h1 that gets me the h1 element。

I'll go ahead and update its inner HTML，and go ahead and set that to whatever。

the value of counter happens to be and，then I'll do the same thing for the。

decrease button document query selector，get me the element whose ID is decreased。

that's the button that will be the minus，button and when you are clicked go ahead。

and run this callback function which，will do the same thing except well first。

do counter minus minus decrease the，value of the counter by one and then get。

me the h1 element set its inner HTML，equal to the counter I think this should。

work and I could verify that by opening，up counter dot HTML I'll refresh the。

page and I can test these buttons test，the plus button all right that seems to。

work increases the value by one I can，test the minus button make sure that。

that decreases the value by one that all，seems to work just fine but of course。

this requires me having to interact with，this page I have to open up the page I。

have to click on these buttons and it's，not the type of thing where I'm。

simulating like a get request or a post，request，there's no server that I'm sending a。

request to in getting back a response of，one-two-three-four from this is all。

happening in the browser and so what I，might like to have the ability to do is。

some sort of browser testing and there，are a number of different frameworks for。

doing this one of the most popular is，selenium and what this is going to allow。

me to do is I can define a test file，that using unit tests or a similar。

library can effectively simulate a web，browser can simulate a web browser and。

simulate a user interacting with that，web browser using something that we call。

a webdriver that's going to allow me to，using code control what it is that the。

browser is doing and how it is that the。

![](img/dfea2e7985faaf65128c8f32e58edce0_19.png)

user is interacting with this program so，how is this going to work well I'm going。

to go ahead and just as a test let me，open up the Python interpreter and let。



![](img/dfea2e7985faaf65128c8f32e58edce0_21.png)

me import from tests import star and，that's going to give me access to a。

couple of different things but the first，thing you'll notice that it's doing is。

because I'm using this webdriver it's，going to give me a web browser and here。

I'm using Chrome but you could use，another browser but notice that here。

chrome is telling me Chrome is being，controlled by automated test software。

the Chrome has the ability to allow me，using automated test software using like。

Python code control what it is the web，browser is doing and so what I can do。

here is the first thing I need to do is，like tell Chrome to open up my web page。

and it turns out that in order to do so，I need to get that Pages URI or Uniform。

Resource identifier just some string，that will identify that page and I've。

defined a function called file URI that，gets me the URI of a particular file in。

this directory so I'm gonna say I want，to open up counter dot HTML and I need。

to get its URI but now what I can say is，driver dot get URI meaning like tell。

this web driver this Python part of the，part of the Python program that is。

controlling the web browser that I would，like to get this web page as if the user。

had gone to the web page and like press，return after typing in the URL so I say。

driver Doug get URI I go ahead and press，that and what you'll notice on the。

right-hand side here is that，chrome has loaded this page I am。

effectively controlling this web browser，window using my Python program I said。

driver Doug get URI meaning go ahead and，open up the counter to the HTML page and。

then inside of this test window chrome，is opened that up and inside my Python。

program now using this web driver I have，the ability to like see the same things。

that the user sees when they open the，page so what does the user see when they。

open the page will they see for example，the title of the page so I could say。

like driver dot title and see that all，right the title of this page is。

countered that was in fact the title of，the page but I could verify that inside。

my Python program that by checking that，driver title by taking my web driver。

getting the title of the current page，that it's looking at making sure that。

that is counter and likewise if I looked，at driver dot page source press return。

what I see there in string format so，it's a little bit messy is the content。

the HTML content of this page and you'll，notice things like you know Dom content。

loaded here my own click handlers here's，my h1 that says 0 it's very messy。

because it's being represented as a，Python string and these backslash ends。

refer to like new lines where there's a，line break but this is the content and。

this is really all the browser gets the，browser takes this information and just。

knows how to render it in some nice more，graphical representation that's easier。

for a user to look at and therefore be，able to understand but this is。

fundamentally all that my web browser is，actually getting back when it tries to。

load a web page so what can I do from，here well I would like to simulate a。

user's behavior on this page that a sure，I can get a page and see the title but I。

want to simulate like clicking on the，plus button for example so in order to。

do that first thing I need to do is like，actually get the plus button and to do。

that I could say something like driver，dot get or find element by ID there are。

a number of ways that I could try and，find an HTML element but I would like to。

find an HTML element by its ID and I，know that the plus button the increase。

button has an ID of increase for example，and so if I find element by ID let me。

find the element whose ID is increase，and all right it seems here that I've。

gotten some web element object back for，my web driver and I'll go ahead and save。

that inside of a variable called，increase so what I now have is a。

variable called increase that represents，the increase button that my web driver。

has found on the web page it's the，effectively effectively the same thing。

as you the human going through the page，looking for the increase button the web。

drivers doing the same thing except，instead of looking for the button based。

on what it looks like it looks for the，button based on its ID and so this again。

another reason why it's helpful to give，your HTML elements IDs in case you ever。

need to be able to find that element，it's very useful to be able to reference。

that element by its name but now that I，have a button I can simulate user。

interaction with that button I can say，something like increase dot click to say。

I would like to take the increase button，and simulate a user clicking on that。

button in order to see whatever it is，that the user would get back when they。

click on that button so increased click，I press return and what you'll notice。

happens is that the number increases，increases from 0 to 1 it's as if I the，button。

except all I did was say like increased，click to say go ahead and press the。

increase button and let the browser do，what it would normally do in response。

and what we do in response is get that，JavaScript event handler that on click。

Handler and run that callback function，that increases the value of counter and。

updates the h1 so I can say increase dot，click to simulate increasing the value。

of that variable but this is just a，function call which means I can include。

it in any other Python constructs that I，want that if I want to repeat something。

like 25 times for example and press the，button 25 times I can say like for I in。

range 25 go ahead and like click the，increase button and now very quickly 25。

times it's going to click the increase，button and I'm going to see the result。

of all of that interaction so I can，simulate user interaction just by using，the Python interpreter。

likewise if instead of increasing one or，two decrease well then I'm going to do。

the same thing I'm gonna say decrease，equals driver dot fine element by ID let，me get the decrease。

element the element whose ID is decrease，and now say decrease dot click and that。

will simulate me pressing the decrease，button press it again and the more I。

press it every time it's good it's going，to decrease by one and if I want to。

decrease it all the way back to zero，we'll then I'll just do it 20 times for。

I in range 20 go ahead and decrease dot，click and that's going to go ahead and。

reduce this account all the way back to，zero by simulating the user pressing a。

button 20 times and what you'll notice，is that it happened remarkably fast like。

I can simulate 100 presses of the，increase button by saying for I in range。

100 increased click and very quickly，you'll see that number a hundred times。



![](img/dfea2e7985faaf65128c8f32e58edce0_23.png)

go ahead and go up to 100 faster than a，human could ever have clicked that plus。

button over and over again and so these，tests can not only be automated but they。

can be much faster than any human could，ever be in order to test this behavior。

so how then can we incorporate this idea，into actual tests that we write into。

like a unit testing framework that，allows me to define all these various。

different functions that test different，parts of my web applications behavior。

well to do that let's go ahead and take，another look at tests PI inside of tests。

up I here again is that file URI，function where that function has the。

sole purpose of like taking the file and，getting its URI and we need the URI to。

be able to open it up then we go ahead，and get the Chrome web driver which is。

going to be what's going to allow us to，run the in simulate interaction with。

Chrome and in order to get Chrome's web，driver you do have to get chrome driver。

separately it is separate from google，chrome itself but Google does make it。

available and other web browsers make，equivalent web drivers available as well。

if you'd like to test how things would，work in other browsers because different。

browsers might behave differently and it，might be useful to be able to test to。

make sure that not only does everything，work in Google Chrome but it's also。

going to work in other browsers that you，might expect users to be working with as。

well here then I've defined a class that，again inherits from unit test a test。

case that is going to define all of the，tests that I would like to run on this。

web page that here I have a function，called test title that's going to go。

ahead and first get countered on HTML，it's going to open up that page and then，just assert equal。

let's make sure the title of the page is，actually countered that's what I would。

expect it to be so I can write a test in，order to test for that case as well here。

I test the increase button by finding，the element whose ID is increase and。

clicking on that button to simulate a，user pressing the plus button in order。

to increase the value of the counter and，then what do I want to check well I want。

to check that when you find element by，tag name h1 and so find element by tag。

name similar to find element by ID，except instead of finding something by。

its ID it's going to look at what's the，tag and only is one element that isn't。

h1 and so here I'm saying go ahead and，get me the h1 element and access its。

text property meaning whatever it is，that is contained inside of those two h1。

tags I would expect that to be the，number 1 and so I would assert that this。

is equal to 1 and likewise I can do the，same thing for the decrease button。

finding the element whose ID is decrease，clicking on that button and then。

asserting equal find me the h1 element，and make sure that the contents of it。

are equal to the number negative 1 for。

![](img/dfea2e7985faaf65128c8f32e58edce0_25.png)

instance and this final test just，testings multiple times that three times。

I'm going to press the increase button，and make sure that after I press the。

increase button three times when I check，the h1 check what's inside of its text。

that the answer should in fact be three。

![](img/dfea2e7985faaf65128c8f32e58edce0_27.png)

so now I should be able to go ahead and，test this code by running Python tests。

pi and what that is going to do is it's，going to open up a web browser and what。

you're gonna see very quickly flashed，across my screen were all of those tests。

we test the increase by 1 we test，decrease by 1 and then we test like。

increase three times after we had，checked to make sure the title was。

correct and then we can see here is the，output we ran four tests in this amount。

of time and everything turned out to be，ok none of the tests failed but if one。

of the tests had failed well then we，would see a different output so let's。

imagine for example that I had had a bug，in my decrease function for example。

where the decrease function wasn't，actually working what would that bug。

look like maybe I forgot to say counter，- - or maybe perhaps，more likely what might have happened is。

I wanted to I already had written the，increased function and I decided to very。

quickly add the decrease function and I，thought I'd just you know what copy。

paste like copy the increase event，handler the decrease event handler is。

basically the same thing except I need，to query for decrease instead and maybe。

I just did that and forgot to change a，plus plus to minus minus a bug that。

might happen if you're not too careful，about how you copy and paste code from。

one place to another now when I run，these tests Python tests up I will see。

the simulation a whole bunch get，simulated and when I go back and check。

the output of my test see what actually，happened I see that we do seem to have。

an assertion error here，the assertion fail was on the test，decrease function and it happened when I。

tried to assert that with inside of the，h1 element was negative 1 because 1 is。

not equal to negative 1 so this is the，value of this assertion error as well。

and this is helpful an advantage over，just assert assert just tells you you。

know there's an assertion error but here，in unit test we actually get to see if I。

asserted that two things are equal it，tells me what both of those things are。

it tells me the actual output of H one's，text it was one but what I expected it。

to be was negative one so it tells me，exactly what the discrepancy is I know。

that for some reason it was one instead，of negative one and that can be a clue。

to me a hint to me as to how I can go，about trying to solve this problem and I。

can solve the problem by going into my，decrease event handler seeing that all。

right this was increasing the counter，instead of decreasing it change plus。

plus to minus - and now rerun my tests，and see all the testing，inside of my chromedriver and we ran。

four tests and this time everything was，okay so all of my tests appear to have。

passed this time so those then are some，possibilities for being able to test our。

code especially taking advantage of unit，tests this library that we can use in。

Python in order to make various types of，assertions about what we would like to。

be true or false about our code and unit，test contains a number of helpful。

methods for being able to perform these，sorts of assertions some of them are。

here so we can say things like I would，like to assert that two things are equal。

to each other which we've seen there's a，counterpart to that a certain not equal。

for making sure that two things are not，equal to one another。

assert true and false we've seen as well，there are others as well though things。

like assert in or assert not in if I，would like to assert for example that。

some element is in some list for example，or that some element is not in some list。

there are other assert methods as well，that we can use in order to verify that。

a part of our program or a part of our，web application does in fact behave the。

way we would want to behave and we can，integrate this type of idea into a。

number of different types of testing we，saw integrating it into Django itself。

using Django's unit testing in order to，verify that our database works the way。

we expected it to and that our views，works the way that we expected them to。

and provided the right context back to，the user after the user makes a request。

to our web application and there are，also applications of unit testing。

whether using the framework or not -，browser based testing when I want to。

test like inside of the users web，browser does it actually work when a。

user clicks on this button that the，JavaScript behaves the way that I would。

expect it to and I don't need to，especially use JavaScript in order to do。

those tests I didn't write those tests，using Python using unit tests to be able。

to say click on the button that has this，idea and verify that the result that we。

get back is what we would expect it to，be so that then was testing and now。

we'll go ahead and take a look at CI CD，continuous integration and continuous。

delivery which refer to two best，practices in the software development。

world that has to do with how it is that，code is written especially by groups or。

teams of people how it all works，together and how that code is eventually。

delivered and deployed to users who are，using those applications so CI which。

refers to continuous integration in，frequent merges to a main branch of some。

repository like a git repository and。

![](img/dfea2e7985faaf65128c8f32e58edce0_29.png)

then automatically running unit tests，when that code is pushed so what does。

that generally mean well in the past you，might imagine that if multiple people。

are working on some project at the same，time and multiple people are each。

working on different features or，different parts of that project then。

after everyone's done working on those，features and we're ready to like ship。

some new version of a web application or，ship some new version of a software。

product well then everyone's gonna have，to take all these various different。

features and combine them all together，at the end and figure out how to then。

try and deliver that program to users，and this has a tendency to cause。

problems especially if people have been，working on different big changes all。

simultaneously they might not all be，compatible with one another there might。

be conflicts between the various，different changes that have been made so。

waiting until everyone's done working on，a feature to merge them all back。

together and then deliver it is not，necessarily the best practice which is。

why increasingly many more teams are，beginning to adopt a system of。

continuous integration that there's one，repository somewhere online that's。

keeping the official version of the code，everyone works on their own version of。

the code may be on their own branch for，example but very frequently all of these。

changes are merged back together into，the same branch to make sure that these。

incremental changes can be happening，such that it's less likely that there's。

two really divergent paths that the，program has gone under and as a result。

it's much more difficult to merge those，two paths back together in addition to。

frequently merging to a some main branch，another key idea of continuous。

integration is this idea of automated，unit testing where unit testing again。

refers to this idea of on our program we，run a big series of tests that verify。

each little part of our program to make，sure that the web application behaves。

the way it is supposed to and unit tests，generally refer to testing particulars。

of our program making sure that each，component works as expected there are。

also bigger scale test tests like，integration tests that make sure that。

the entire pathway from like user，request and response that everything。

along a certain pipeline works as well，but there are various different types of。

testing and the important thing is，making sure that anytime some new change。

is merged into the main branch or，someone wants to merge，changes into the main branch that these。

tests are run to make sure that nobody，ever makes a change to one part of a。

program that breaks some other part of，the program and in a large enough。

codebase it's going to be impossible for，any one person to know exactly what the。

effect of one particular change is going，to be on every other part of the program。

they're going to be unforeseen，consequences that the one programmer may。

or may not know about and so the，advantage of unit testing assuming their。

comprehensive and cover all of these，various different components of the。

program is that anytime someone makes a，change and attempts to merge that change。

into the main branch according to the，practice of continuous integration the。

fact that it doesn't pass a test we'll，know about that immediately and as a。

result that programmer can go back and，try to fix it as opposed to waiting。

until everything is done merging，everything together and then running the。

tests realizing something doesn't work，and then being unsure of where to begin。

we don't know where the bug is which，change happened to cause the bug if。

everything is merged more incrementally，it's easier to spot those bugs assuming。

there's good coverage of test to make，sure that we're counting for these。

various different possibilities some，continuous integration refers to that。

idea frequently and more incrementally，updating the main branch and making sure。

that the tests are in fact passing and，it's closely tied to a related idea of。

continuous delivery which is about the，process of how it is that the software。

is actually released to users how the，web application actually gets deployed。

and there are a couple of models you，might go about thinking with regards to。

how it is that some program or web，application gets deployed you might。

imagine the release cycle might be quite，long that people spend months working on。

various different features on some，software development team and after。

they're happy with all the new changes，they've released some new version of the。

web application but especially with web，applications that are undergoing。

constant change that have lots of users，that are moving very quickly one thing。

that's quite popular is this notion of，continuous delivery which refers to。

having shorter release schedules instead，of immediately releasing something at。

the end of some long cycle you can in，shorter cycles make releases every day。

every week or so in order to say that，let's just go ahead and incrementally。

make those changes whatever new changes，happen to have merge to the main branch。

let's go ahead and release those as，opposed to waiting much longer。

in order to perform those releases and，that again lends itself to certain。

benefits the benefit of being able to，just incrementally make changes such as。

something goes wrong you know more，immediately what went wrong as opposed。

to making a lot of changes at once where，if something goes wrong it's not。

necessarily clear what went wrong and it，also allows new features to get out to。

users much more quickly so especially in，a competitive market where many。

different web applications are competing，with one another being able to take a。

new feature and release it very quickly，can be quite helpful so continuous。

delivery is all about that idea of short，release cycles rather than wait a long。

time for a new version to be released，release versions incremental e as new。

features begin to come in it's closely，related to the idea of continuous。

deployment which CD will sometimes also，represent continuous deployment is。

similar in spirit to continuous delivery，but the deployments happen automatically。

that rather than a human having to say，all right we've made a couple of changes。

let's go ahead and deploy those changes，in continuous deployment anytime these。

changes are made the pipeline of，deploying the application to users will。

automatically take place as well just，removing one thing for humans to have to。

think about and allowing for these，deployments to happen even more quickly。

as well so the question then is what，tools can allow us to make continuous。

integration and continuous delivery a。
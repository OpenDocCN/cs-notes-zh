# 【双语字幕+资料下载】哈佛 CS50-WEB ｜ 基于Python ／ JavaScript的Web编程(2020·完整版) - P3：L0- HTML与CSS语法 2 (CSS语法) - ShowMeAI - BV1gL411x7NY

elements inside of other relevance but，right now so far all of our web pages，have been rather simple。

they've just been we've described the，structure of the page and we've。

described we want to list here we want，to form there what we might really like。

is some way of specifying that we want，to style our web page in some way we。

want to add color we want to add spacing，we want to add some sort of other layout。

to our page as well and in order to do，that we're going to use a second。

language that we're going to call CSS，short for cascading style sheets in。

particular we'll use the latest version。

![](img/5b25f9189e795f9881b6a35947d0e23f_1.png)

of CSS CSS 3 which gives us the ability，to take an HTML page and tell the web。

browser how we would like it to be，styled instead of just black text in the。

same font on a white background we can，begin to specify particular CSS。

properties of how we would like this，page to look to make sure that the page。

looks the way we want it to so let's，take a look at a simple example now of，some。

CSS code to our page so I'll go ahead，and create a new file that I'll call。

style dot HTML just to demonstrate some，basic ideas of adding some style to our。

page and we'll go ahead and copy the，same hello to the HTML from before and。

maybe in addition to hello world I，display in h1 some big heading at the。



![](img/5b25f9189e795f9881b6a35947d0e23f_3.png)

top that says like welcome to my web，page for example so now if I open up。

style dot HTML this is what I see I see，a big heading at the top that says。

welcome to my web page beneath which is，just the text hello world and now。

imagine that I want to add some style to，this heading at the top of the page。

maybe instead of being left aligned I。

![](img/5b25f9189e795f9881b6a35947d0e23f_5.png)

want it to be centered maybe instead of，just being black text I'd like to change。

the color in order to do that just as，we've used attributes in the past to add。

additional information to this，particular HTML page we can do a very。

similar thing with CSS we can specify，that we're going to give this h1 element。

a style attribute and that is going to，be equal to and then in quotation marks。

we're going to provide all of these CSS，properties that we would like to add to。

this particular element so the way that，CSS styling works is that we can give。

elements individual CSS properties where，a property is something like the color。

of the element or the alignment of the，element and each of those properties has。

a default value but we can change its，value to something else so if for。

example I wanted to change the color of，this heading so that instead of a black。

heading it displayed as a blue heading I，could say for this h1 I would like to。

give it a color property and then to，give the color property of value I say。

color Cohen and then the value that I，would like to give to it so color colon。

blue for example followed by a semicolon，will change the color of this h1 element。

to blue and my text editor is，automatically showing me a little squ*re。

that shows me what this color blue is，actually going to look like this isn't。

part of the text it's just my text，editor being helpful so that I can see。



![](img/5b25f9189e795f9881b6a35947d0e23f_7.png)

in advance as I'm writing this code what，the color is actually going to look like。



![](img/5b25f9189e795f9881b6a35947d0e23f_9.png)

so now if I open up style dot HTML，here's what I see in，stead of a black heading at the top。

we've changed the color to blue and，there are many other built-in colors。



![](img/5b25f9189e795f9881b6a35947d0e23f_11.png)

that exist within HTML that we can use，in order to change the color to whatever。



![](img/5b25f9189e795f9881b6a35947d0e23f_13.png)

we want if instead of blue I said I want，the color to be red for instance I can。

refresh the page and now the heading is，red and there are many other colors I。

can change the color to like spring，green for instance and that's going to。

be a particular shade of green that，displays just like this and so now we。



![](img/5b25f9189e795f9881b6a35947d0e23f_15.png)

have the ability to add various，different style properties to individual。

elements I can say take this heading and，change its style so that the color。

instead of being black is going to show，up as blue instead and if I want to add。

multiple CSS properties to the same HTML，element I can do that as well here in。

the style attribute I can say that in，addition to saying that the color is。

blue I'd like to give a second CSS，property to this element I'd like to say。

that the text aligned property should be，Center for example the text aligned。

property controls as you might imagine，how a particular HTML element has its。

text aligned is it all the way on the，Left all the way on the right or。

centered and if I change the text，aligned property to have a value of。



![](img/5b25f9189e795f9881b6a35947d0e23f_17.png)

center well then now when i refresh this，page I see that welcome to my web page。

is now both blue and it's centered I've，changed the color and I've changed the。

alignment of this particular element and。

![](img/5b25f9189e795f9881b6a35947d0e23f_19.png)

HTML elements don't need to just be，styled directly they can also get their。

style information from parent elements，so if you recall again that Dom。

structure where we have an HTML element，inside of which is this body element and。

inside of the body element is this h1，element and this text you can imagine if。

we wanted this styling to apply not just，to this heading but also to the hello。

world text I could move the styling，information move this style attribute。

change it from the h1 and escalating it，to this body and if I move the style to。

the body then everything inside of the，body is going to be styled in that way。

so let's now take a look at an example，of that to see how that works if I take。

the style information and I move it so，that instead of associating it with the，h1。



![](img/5b25f9189e795f9881b6a35947d0e23f_21.png)

i instead associate it with the body，then now when i refresh the page i see。

that both parts of the body both the big，heading at the top that says welcome to。

my web page as well as the text hello，world both have those CSS properties。

applied i've changed their color to blue。

![](img/5b25f9189e795f9881b6a35947d0e23f_23.png)

and have also changed their text，alignment to be centered instead of just。

left aligned but if i do want it to just，be that heading then i can move it out。

and say that i just want to apply the，style to that one individual heading now。

one thing that we might imagine might，become a problem over time is that。

imagine if i had multiple headings that，i wanted to style in the same way for。

example let's say I have a second，heading that this is a second heading。



![](img/5b25f9189e795f9881b6a35947d0e23f_25.png)

but I also want to be styled as blue and，centered as well I can refresh this page。

and see that right now that is not the。

![](img/5b25f9189e795f9881b6a35947d0e23f_27.png)

case and I don't want to make the entire，page blue and centered I only want these。

Q headings to be blue and centered so，what I could do is I could just take the。

style code from the h1 and apply it to，this h1 as well so that both of my h1。



![](img/5b25f9189e795f9881b6a35947d0e23f_29.png)

elements now have the exact same style，code and I'll go ahead and refresh this。

and now we see this is the intended，behavior I have two headings both of。

which are centered and both of which are。

![](img/5b25f9189e795f9881b6a35947d0e23f_31.png)

blue but what we want to start to think，about as we start to build web。

applications and especially as our web，applications start to get a little bit。

more sophisticated is to think about the，design of how we're building our web。

pages and how we're building our web，applications and in particular anytime。

we find ourselves copying a lot of the，same information from one place to。

another that's probably not the best，design and you should start to think。

about how might you design this a little，bit better it's not great design 1 just。

because there's some redundancy that，probably doesn't need to be there but。

also because it makes the page a little，bit more difficult to change and a。

little more difficult to update if I，instead want to change both of these。

headings to be red instead of blue then，all the sudden I need to change my code。

in two places I need to change the style，attribute on this first heading up here。

and I also need to change the style，attribute on the second heading down。

there what I'd like to do is to somehow，just be able to write the style code，once and。

then have it applied to both of these，heads and in fact there is a way to do。

that what we can do is instead of doing，what we might call inline styling where。

we take the CSS code and place it，directly as an attribute of an HTML。

element we can move our style code to an，entirely different part of the webpage。

recall again that at the top of our HTML，page we have this head section that just。

includes information that's useful to，know about the web page but isn't。

actually part of the body of the web，page the content that the user sees this。

head section is a great place where we，can begin to put some style information。

information about how we would like for，this web page to be styled so what I can。

do here is instead of putting these，style attributes inside in line with。

these HTML elements I can inside of the，head section of my web page add a style。

element where in between these the，opening style tag and the closing style。

tag I can add any of the style，information that I want and here's the。

way that syntax is going to look I first，need to specify what types of elements。

am I going to style and in this case I，want to style all of the H ones so I can。



![](img/5b25f9189e795f9881b6a35947d0e23f_33.png)

just say h1 and then all of the style，code is going to go inside of a pair of。

curly braces where I can say I would，like the color to be blue and I would。

like the text aligned property to be，centered so now here's what I've done。

I've taken the CSS code that used to be，down here inside the body of the page。

actually as an attribute of these h1，elements and I've moved the style。

related code to a different part of my，page altogether now the style。

information is inside the header of my，page inside of the style element where。

I've said for every h1 element here is，how you should style it the styling is。

in between the opening and curly closing，braces here and I've said that every h1。

should have a color of blue and every h1，should have a text aligned property of。

center and that is then going to apply，to all of the h1 elements that my。

webpage happens to find inside the body，advantage，here advantage number one is what we。

talked about a moment ago I don't need，to duplicate the same code in both of。

these h1 elements I can write at once，and say apply this styling to all of the。

H ones that show up in the page an，advantage number two is we've been able。

to factor out the style code to，somewhere else just to make it a little。

bit cleaner so that instead of having a，really long line you might imagine if we。

had not just two but maybe five or six，or seven different CSS property isn't。

that would have taken up a lot of space，on one line I can instead in a more。

readable more organized way move that，style related code to the style element。

at the beginning of the page just to，make it easier to read it easier to。

visually understand and just to clean up，the body of the web page as well and。

that's going to be another of the key，themes that's going to come up again and。

again in this class this idea of，separating things out so that every。

piece can sort of be independent of one，another our structure of the web page。

inside the body is separate from the，style and we'll see the same sort of。

idea appear again and again as we begin，to try to design web applications well。

so now if I take this exact same page，and go ahead and refresh style dot HTML。

we'll see that we see the exact same，thing both of the headings still show up。

a centered both of them still show up as，blue but now we have the advantage of。

having only written the style code once。

![](img/5b25f9189e795f9881b6a35947d0e23f_35.png)

instead of needing to write the exact，same style code multiple times in the。

same way but it turns out that we can，even do a little bit better than this。

because one thing you might imagine is，that if I have a web application or a。

website that has multiple different web，pages it's probably going to be likely。

that each of those web pages might need，to be styled in similar ways if I have a。

big banner at the top of one web page，then in other pages related to that page。

I might want the same banner styled in，the same way using similar style。

information and right now our CSS code，is specific to one particular page and。

it's not going to be easy to then take，that same styling and apply it to。

another page if I wanted to I need to，copy the exact same CSS code put it。

inside of another page but then we run，into the same problem of duplication。

where I've now had to repeat myself，across multiple different pages putting，the exact same。

CSS code across all those different，pages so there is an improvement we can。

make and the improvement we can make is，to take that CSS code and just move it。

to an entirely different file so instead，of putting this style code inside of a。

style element inside of this HTML page，I'll just create a new file that I'll。

call styles CSS inside of which is going，to be all of the CSS that I care about I。

want to take every h1 I want to change，its color to blue and now I want to。

change its text aligned property to，Center and now inside of my HTML page I。

no longer need to include any CSS at all，instead of this style element altogether。

I can just link my CSS code in that CSS，file called styles。css to this。

particular HTML page and how do I link，the Styles dot CSS file，well I can do so again in the head。

section of my web page using a link tag，where I can say I'd like this link to be。

the relationship is it's going to be a，style sheet meaning what I'm about to。

link is going to be a style sheet for，this page it's going to describe how I。

want for the elements on this page to be。

![](img/5b25f9189e795f9881b6a35947d0e23f_37.png)

styled and then just as in the case of a，link to another page I used href to。

specify a hyperlink reference what I，want to link to I'm now going to specify。

using an href attribute what CSS file I，would like to now link and in this case。

the CSS file that I'm going to link is，Styles dot CSS that is the file that。

just so happens to contain all of the，CSS that I would like to apply to this。

particular file now if i refresh the，page I see again nothing has changed in。

the last two revisions the page just，stayed exactly the same as far as the。



![](img/5b25f9189e795f9881b6a35947d0e23f_39.png)

user is concerned they still see two，headings both of them are centered both。

of them are blue but now the advantage，is that here is my HTML it's shorter。

than it was before and in particular，there's no CSS that's baked in to this。

HTML file at all i factored it all out，into this separate styles CSS file and。

now if I have multiple HTML files that，are all using the same styling I can。

just link them all to the same Styles，dot CSS file，such that they're all using the same。

style information I don't need to repeat，myself and if ever I need to make a。

change across all of those pages I just，changed the styling once I changed this。

style of CSS file and then all of the，web pages that are linked to that style。

sheet will update as well in order to，reflect those changes so again we've。

been able to factor out some of this，style information to a separate file。

just to make our lives a little bit，easier all right so so far we've now。

seen how we can use CSS in a number of，different ways to add some basic style。

store page we've seen that we can take，an element and change its color we've。

seen how we can take an element and，change its alignment move it from left。

align to right align to centered for，example as it turns out there are a lot。

of different CSS properties that we can，add to our HTML elements in order to。

style them in various different ways，more than we'll have time to talk about。

in this lecture but now let's just take，a look at a couple of the most popular。

most common CSS properties that we can，add in order to make our webpages look。

the way we wanted to and one of the most，powerful tools for CSS is controlling。

the size of various different elements，by default HTML just use a default size。

for everything on the page but if I want，to more precisely control how big any。

particular element is I can use CSS in，order to do so so let me now create a。

new file that I will call size dot HTML，we'll start with the same HTML code and。

call the page size and now inside the，body of my page let me just have a。

vertical section of my page just some，section of my page that's going to have。

some content and I'm gonna put this，inside of a div tag now this is the。

first time that we've seen a div in HTML，you can think of a div as just a。

division of the page some section of the，page that's going to have some content。

inside of it and we used is because it，makes it easy to reference a particular。

div or nest information inside of other，pieces of information or just to divide。

and break up our page into multiple，different sections here inside of the。

body I'm just going to have a single div，that is going to say something like。

hello world and now I'm going to add，some style to this page in order to。

control the size of this div to control，the size of this section。

of my webpage I could use inline styling，I could factor things out into another。

file but since I'm only dealing with one，file for now I'm just going to add a。

style section to the top of my webpage，just so you can more clearly see how the。

style of this page is going to map on to，the way that we're modifying these HTML。

elements and I would like to style this，daven in a couple of ways one thing I，color。

let me change its background color to，blue for example and then I can say all。

right I'd like to give this Dave，a width and a height some size。

information I can say go ahead and give，this div a width of 100 pixels and maybe。



![](img/5b25f9189e795f9881b6a35947d0e23f_41.png)

a height of 400 pixels so now when I go。

![](img/5b25f9189e795f9881b6a35947d0e23f_43.png)

ahead and open up size HTML this is what，I see I see in a 100 by 400 pixel wide。

vertical or rectangular section of my，page I see the words hello world and so。

you might imagine if you have multiple，different elements on your page as your。

web pages start to get a little bit more，complex you probably want to have some。



![](img/5b25f9189e795f9881b6a35947d0e23f_45.png)

more precise control over how wide or，how tall any particular element is and。

these width and height attributes can be。

![](img/5b25f9189e795f9881b6a35947d0e23f_47.png)

very helpful because I can very easily，change the width to say like 500 pixels。

for example and now when i refresh the，page now I see that the width of this。

page of this div this section of the，page has actually now gotten a lot wider。

and so we have the ability to control。

![](img/5b25f9189e795f9881b6a35947d0e23f_49.png)

size using CSS go ahead and can close，some of these pages that I no longer。

need and now take a look at some other，things that we can do in addition to。

controlling the size and let me change。

![](img/5b25f9189e795f9881b6a35947d0e23f_51.png)

this color to something a little bit，lighter something like orange such that。



![](img/5b25f9189e795f9881b6a35947d0e23f_53.png)

now if I open up size it looks like this，I'll make this a little bit smaller。



![](img/5b25f9189e795f9881b6a35947d0e23f_55.png)

let's try 200 by 200 pixels it looks now，like this you might imagine there are。

some other changes that I might like to，make like this hello world for example。

is very close to the edge of this，particular day of it's right up against。

the upper left corner of that daiva I，might want to change that by adding what。

we might call some padding to this，particular HTML of it some space just so。

that the content of the element isn't so，close to the border of the element。



![](img/5b25f9189e795f9881b6a35947d0e23f_57.png)

itself so for example one thing I can do，is inside this div add。



![](img/5b25f9189e795f9881b6a35947d0e23f_59.png)

some padding say maybe I want 20 pixels，worth of padding on the inside of the。

element such that now when i refresh the，page we see that we have some padding。

along the outside of the element so that，HelloWorld now shows up not right up。

against the edge of the element but，inside a little bit as well and if we。

have a particular HTML element that，maybe is too close to the edge of the。

screen maybe it's too close to the top，of the screen we can also add space。



![](img/5b25f9189e795f9881b6a35947d0e23f_61.png)

around outside of the element by adding，what we call margin to the element as。



![](img/5b25f9189e795f9881b6a35947d0e23f_63.png)

well so I can say let's give it 20，pixels of margin inside of this div and。

then refresh and now we see that whereas，before this div was very close to the。

upper left edge of the screen now we've，moved it 20 pixels away from everything。



![](img/5b25f9189e795f9881b6a35947d0e23f_65.png)

so it's got some space on all four sides，of it so that's how we can now use。

margin and padding just to make the page，look a little bit nicer to the user so。

objects are not too close together or，too far apart padding again is on the。

inside of the border of the element I，can add 20 pixels of padding for example。

to make sure that the content inside of，the element in this case the words hello。

world just have a little bit of space，from the border and that's padding on。

the inside of the element margin，meanwhile is on the outside of the。

element we add some margin along the，outside of the border to space the。

element out from other elements that，might be nearby to make sure that。

there's enough space between the border，of the element from the top of the。

screen and also from the left and also，the bottom and the right though there's。

no objects there that we're currently，creating space from so by combining。

width and height and margin and padding，we now have the ability using CSS to。

make sure that we're able to layout our，page the way we want to layout the page。

that elements have the right amount of，spacing from each other and are the。

correct size so now let's take a look at，some other features that CSS is going to。

give us in addition to just changing，where particular elements are like。

centering text or adding size and margin，and padding we can also use CSS to。

change how elements actually look we've，seen it to change the color of text。

changing it from one color like black to，another color like blue but we can also。

use CSS to be able to change something，like the font that we use in order to。

display text modern webpages don't show，everything in the exact。

font usually some designer is choosing，what font they want for any particular。

webpage so let's experiment with those，possibilities，I'll now create a new file that I'll。

call font dot HTML inside of which will，be an HTML page called font and inside。

the body I'll again just have a div that，says hello world same as before but now。

inside of the style tag here up in the，head section of my web page I would like。

to add some font information to this div，and in particular there are a number of。

different font related CSS properties，that I can add to control the font of。

any particular HTML element one thing I，can specify is the font family。

specifying what font would I like to use。

![](img/5b25f9189e795f9881b6a35947d0e23f_67.png)

in order to display this text and maybe，I want to display it in Arial for。

example which is a common font used on，the internet such that now if I open up，font dot HTML。

I now see in Arial the words hello world。

![](img/5b25f9189e795f9881b6a35947d0e23f_69.png)

different from the text that I was using，before you can also specify multiple。



![](img/5b25f9189e795f9881b6a35947d0e23f_71.png)

different fonts not all computers，support all fonts so I could specify。

that just in case Arial isn't supported，fallback to any sans-serif font any of。

the fonts that don't have the little，glyphs at the edge of each of the。

characters so now if i refresh the page，because my web browser supports Arial I。

don't notice anything different but you，might imagine if you're using more。

complex fonts that not all web browsers，have or support you might add some。

backups just in case the font you want，isn't actually available in addition to。

a font family I might also specify a，font size how big I want the font to be。

inside of this div so I can specify that，I'd like the font size of this div to be。

you know 28 pixels for example such that。

![](img/5b25f9189e795f9881b6a35947d0e23f_73.png)

now i refresh it and now this div，appears using larger text and I can also。

just as like text editors let you，specify whether you want it to be normal。

text or bold text I can specify a font，weight for this div and say that in，addition to being in font：

arial in size。

![](img/5b25f9189e795f9881b6a35947d0e23f_75.png)

28 I would also like for the font to be，bold such that now i refresh it and now。

the phone shows up as bold and using，these CSS style sheets were able to。



![](img/5b25f9189e795f9881b6a35947d0e23f_77.png)

selectively apply the styling，to only particular parts of the webpage。

if I have another underneath this div，some more text down here for example。



![](img/5b25f9189e795f9881b6a35947d0e23f_79.png)

that additional text that outside of the，div isn't going to be affected by the。

CSS styling such that now if i refresh，this page some more text shows up in。

that same standard default font provided，by web my web browser and not the custom。

font that I have specified to apply to，only this particular part of the HTML。

page so that now is the ability to add，fonts to our page - another thing that。

we might want to do is to be able to add，some sort of border around our HTML。

elements so maybe I want a line to be，able to separate this entire part of the。



![](img/5b25f9189e795f9881b6a35947d0e23f_81.png)

page from another part of the page so I，could add a border by going to this div。

and saying let me give this div a border，and maybe I want the border to be like a。

3 pixel solid black border for instance，I can specify how big I want the border。



![](img/5b25f9189e795f9881b6a35947d0e23f_83.png)

to be I can specify whether I want the，border to be a solid line or a dashed or。

dotted line and I can specify what color，I would like that border to be as well。

so now when i refresh this I now see I，have a border around this entire section。

around this entire div inside of my web，page and you can imagine these borders。

being helpful for styling various，different parts of my page so for。

example if we go back to that table that，we were looking at a moment ago when we。

were dealing with oceans where I had a，ocean and Pacific Ocean and Atlantic。

Ocean this is structured in the format，of a table we have rows and columns but。

it doesn't look great right now I might，like to add some styling in order to。

improve the way that this table looks。

![](img/5b25f9189e795f9881b6a35947d0e23f_85.png)

for example so let's give that a try，I'll go ahead and go back into table dot。

HTML that HTML file I was using before，where I had this table and let me now。

add some style information to this table。

![](img/5b25f9189e795f9881b6a35947d0e23f_87.png)

I might say that for this table I would，like to give it a border that is maybe a。

1 pixel solid black border such that now，when i refresh the page I have a 1 pixel。

solid black border around the entirety，of the table all right that's great but。

I also really wanted a border in between，the rows and the columns as well in。



![](img/5b25f9189e795f9881b6a35947d0e23f_89.png)

particular every table data item，I might like to have some additional CSS。

applied to those two so I might say for，every table data sell again。

TD stood for table data and those were，the individual cells within my table I。



![](img/5b25f9189e795f9881b6a35947d0e23f_91.png)

might specify that I would like those to，also have a border that is one pixel。

solid black such that now i refresh the，page and now each of my table data cells。

also has a border around it now this，applied to the table data cells in the。



![](img/5b25f9189e795f9881b6a35947d0e23f_93.png)

body of my page but it didn't yet，applied to these cells up in the heading。

and that's because those were th，elements table headers and so here we。

have a couple of options I could specify，once more table headers I would like to。



![](img/5b25f9189e795f9881b6a35947d0e23f_95.png)

give a border of one pixel solid black。

![](img/5b25f9189e795f9881b6a35947d0e23f_97.png)

but when I do so you'll see that it does，create a border around those table。

headers but again one thing that should，be crossing your mind now is that。

there's a fair amount of redundancy here，some repeated style code that shows up。

in multiple different places table data，cells in the body of my page I really。

want to be styled in a very similar way，to table header cells and so it would be。

nice if I could somehow consolidate，these two different CSS selectors these。

ways of me saying style table data style，table headers I'd like to combine them。

into one and you can in fact do this in，CSS there are a number of different CSS。

selectors ways of choosing elements and，one of them is just called the multiple。

element selector that if I want to，select both table data cells and table。

headers then I can do so by saying TD，comma th and delete these three lines。

down there what these three lines are，now saying are that I would like to。

style all table data cells and table，headers in the same way and I could even。

combine table if I wanted to for good，measure but I'd like to give all of them。



![](img/5b25f9189e795f9881b6a35947d0e23f_99.png)

a border of one pixel solid block such，that now i refresh it and now I see that。

they all have this border around them，now，most tables you see on the internet。

don't have both a table or a border，around everything in the table and also。

a border around each of the individual。

![](img/5b25f9189e795f9881b6a35947d0e23f_101.png)

cells usually those are collapsed just，into a single line and it turns out that。

CSS has an easy way for you to do this，well I can add a CSS property to the。



![](img/5b25f9189e795f9881b6a35947d0e23f_103.png)

table called border collapse and just，say I would like to collapse all of the。

borders in the table just going to show，you there are many many different CSS。

properties far more than we'll be，looking at today but they're easy things。

to reference so you can easily look up，how to collapse borders in a table and。

then find a CSS property like this that，you can then use and apply to your。

webpage so now I refresh that and now I，see that I have a border just a single。

border around all of the cells in this，particular page next what I might like。

to do though is like add some space，around here like it seems like these。

these text is very tight against the，border of this table so in order to do。

so I want to add some spacing and recall，again do I want margin or padding margin。

is spacing around outside of the border，of a particular HTML element whereas。

padding is inside of the border so if I，want some space inside of the border。

just to space out the text from the，border itself then what I want is。



![](img/5b25f9189e795f9881b6a35947d0e23f_105.png)

padding inside of all of my table cells。

![](img/5b25f9189e795f9881b6a35947d0e23f_107.png)

so I can say let me add five pixels，worth of padding inside of all of my。

table data cells and table header cells。

![](img/5b25f9189e795f9881b6a35947d0e23f_109.png)

refresh the page and now here's what the，resulting table looks like just by。

adding a little bit of CSS specifying，what border I want around the edge of。

the page of specifying a little bit of，padding inside of each of the cell ISM。

my table now looks a whole lot nicer，than it did just a few lines of code ago。

when I just had the HTML structure of，the page and not the CSS to describe how。

I actually want that page to be styled，and notice again that in doing so we。

were able to use one of these CSS，selectors I was able to say that I。

wanted to use the multiple element，selector which is just this comma here。

to specify that I would like to apply，this styling not just to TDs。

but also to th's as well we'll take a，look at some additional examples of CSS。

selectors in just a moment but next，let's turn our attention to some more。

tricky instances where we might want to，apply styling to multiple elements at。

the same time let's imagine and let's go，back to style dot HTML。

where we had some style code where I had，one heading I'll call this heading one。

and let's give myself two other headings，heading 2 and heading 3 all of these now。

our h1 elements that are going to show，up the same way such that now if I style。

and say I would like all each one's to，show up with a color of blue then when I。

open this page where I have three h1。

![](img/5b25f9189e795f9881b6a35947d0e23f_111.png)

tags each of which has a color of blue，when I open up style HTML what I'm going。

to see is something like this three，headings each of which happens to have a。

color of blue but what would happen now，if I wanted to style only the first。

heading I want heading 1 to be blue but，I don't want to style heading 2 and。



![](img/5b25f9189e795f9881b6a35947d0e23f_113.png)

heading 3 how do I do that，well one thing we could do is go back to。

the inline styling we did a moment ago，where inside of each one I said style。

color is blue and that would say for，just this very first heading I would。

like that to be blue but not the other，elements at all but this again we。

decided was not the best design this，inline styling commingling of HTML and。

CSS just gets a little bit messy and it，would be nice to be able to factor all。

of our style code to a separate part of，the page altogether so how do we do this。

well we need some way to uniquely，reference this particular HTML element。

and in order to do so we can give an，HTML element an ID an ID is just some。

unique name we give to an HTML element，so that we can reference it more easily。

later on let me just go ahead and give，this an ID of foo it could be any idea。

you want but foo is just a generic name，here and now we've given this heading a。

name such that in other parts of our，page or an other code we can reference。

and find this particular HTML element，and in particular now in the style。

section of my web page instead of，styling all h1 elements I only want to。

style the element that has an ID of foo，IDs are by definition unique there can。

only be one element in this page that，has an ID of foo otherwise it's not。

valid HTML and so in order to do so，we're going to use hashtag soo the hash。

mark symbol is just CSS way of selecting，just something with a particular ID so。

instead of just each one for selecting，all of the h1 tags if I want to select。

something by its ID I say hash foo to。

![](img/5b25f9189e795f9881b6a35947d0e23f_115.png)

say only style the element that has an，ID of foo and give it a color of blue。

for example so this style code now will，find something with a particular ID and。

give it a style to correspond with it，such that now if I reload this page only。

heading 1 is styled heading 2 and，heading 3 or not I've been able to name。

heading 1 give it a name of foo and ID，of foo and then in my style code just。

style that particular part of my HTML。

![](img/5b25f9189e795f9881b6a35947d0e23f_117.png)

page of course what if I wanted to style，multiple but not all of the headings。

like maybe I want to style both heading，1 and heading 2，now I could use a second ID maybe give。

this an ID of bar for example and then，style both the element with ID foo and。

the element with ID bar but now we're，starting to add IDs unnecessarily I have。

too many different names things could，start to get messy especially as my。

webpages start to get bigger，so while IDs are a way of giving a name。

to an HTML element that is unique，sometimes I want to give a name to an。

HTML element that is not unique some，name that can apply to multiple。

different HTML elements and when we do，that we call that a class an ID is a way。

of giving a unique name to an HTML，element while a class is a way of giving。

a name to an HTML element that might not，be unique it might apply to 0 or 1 or 2。

or more different HTML elements so，here's what that might look like instead。

of giving each of these h one's an ID，that's different I can give each one a。

class we'll give this a class of Baz，again just another arbitrary name that。

we've chosen and I'll give this h1 a，class of Baz as well they both belong to。

this same class called Baz in this case，and now inside of my style code I would。

like to say just style the elements that，are of class Baz and just as we had a。

special symbol the hash tag for styling，only something with a particular ID you。

to style everything with a particular，class I can use a dot so dot Baz。

in this case is going to style only the，elements that have a class of Baz so。

here I can now say take all of the，elements with the class of Baz and go。



![](img/5b25f9189e795f9881b6a35947d0e23f_119.png)

ahead and give those a color of blue so，now I have two H ones that belong to。

class bass each the other h1 does not，and I've styled only the things that are。

of clasp as such that now when I go back。

![](img/5b25f9189e795f9881b6a35947d0e23f_121.png)

to the page and refresh the page，my first two headings those do get。

styled as blue but the third heading，does not because it applied a class to。

these two elements that does not get，applied to this third element there so。

oftentimes it can be very helpful if you，have to start to design larger web pages。

where you have multiple different，elements some of which might be styled。

in some ways and and other elements that，might be styled similarly to one another。

you can add IDs and classes to your HTML，elements just to clean up the way that。

you write your CSS to be able to very，specifically pinpoint one element that。

you want to apply style to or to apply，styling to entire class of elements as，well。

now one tricky thing you might imagine，now is that now we have multiple ways of。

referencing the exact same element so，for example if you imagine that I just。

had a single h1 which had an ID of foo，for example that I've named foo what。

would happen if for instance I said all，of the H ones I were like those to be。

colored red and all of the elements with，an ID of foo or the only element with an。

ID of foo I would like that to be，colored blue what might happen then。

these would seem to be conflicting we're，now suddenly we have in h1。

style tag that is saying I should style，each one's in this way but I should。

style element foo in another way so what，happens if I have an h1 whose ID is foo。



![](img/5b25f9189e795f9881b6a35947d0e23f_123.png)

how do I choose to style that and in，order to deal with that we have to start。

to deal with the CSS problem of，specificity of what happens when I have。

multiple different CSS selectors that，could apply to the。



![](img/5b25f9189e795f9881b6a35947d0e23f_125.png)

same HTML element and this often happens，when we start to add IDs and classes to。

our elements as well so when we deal，with specificity specificity goes in a。

particular order there's an order of，precedence that we can follow for。

determining what style should ultimately，be applied to any particular element the。

first most powerful most specific way of，referencing an element is inline styling。

literally adding a style equals，attribute to our c HTML elements the way。

we did way at the beginning when we were，first taking a look at CSS if we。

associate inline styling with an HTML，element that's going to take precedence。

over any styling that's inside the style，section of our head of the webpage or。

inside of a separate dot CSS file，because the reason and go is if you are。

literally putting the style code，attached to the element itself then we。

probably want to apply it to that，element after that specificity goes in。

order of how precisely we are，identifying an element an ID is a unique。

way to identify an element there is only，one element with that particular ID so。

if I've added style to a particular ID，that is going to be pretty highly valued。

in terms of how specific it is next we，look at classes so if there's no ID。

selector we look for did we reference，the element by its class and if so then。

that takes next precedence and otherwise，then we fall back to what type of HTML。

element it is is it an h1 is it an，ordered list is it a table so in short。

the type is the least specific class is，slightly more specific ID is more than。

that and the most specificity we can，provide is by literally putting the CSS。

inline with the HTML element itself so，let's take a look at an example of this。



![](img/5b25f9189e795f9881b6a35947d0e23f_127.png)

let's look at this code for example，where for instance I have a div and。

whose ID is foo inside of which I'm just，saying the word hello and the CSS code。

that I've included here is I've said for，all divs I would like to give those a。

color of blue obviously in that case，there's nothing conflicting what we're。

going to see is we're gonna see the word，hello and we're going to see the word。

hello in blue but what happens now if we，add anything with ID，you should be colored red well because。

ID has higher specificity than just an，individual tag well then next what we're。

going to say is that this hello is going，to show up as red the ID is more。

specific and so this element is going to，show up red instead and it doesn't。

matter what order these are in it's not，that the later one takes precedence if I。

were to flip these around where idea foo，color red div color blue is in that。

order it's still going to show up as red，because this ID selector is more。

specific than just the name div which is，the name of the HTML element that。

happens to be there and so as you start，to develop more sophisticated style。

sheets you might find that some of your，CSS code is going to conflict with each。

other and that's where it's important to，bear in mind how these specificity rules。

work to know as you add style to your，elements how are they actually going to。

end up showing up now we've seen a，couple of CSS selectors now in terms of。

selecting a single element selecting an，ID selecting a class selecting multiple。

elements as well it turns out there are，a number of other CSS selectors that we。

can use too so we saw for example the，multiple element selector like TD comma。

th for selecting table data but also，table headers but there's a number of。

other selectors here's just a sampling，of ones you can specify like descendants。

or children so if I only want to style，divs that are inside of tables or I only。

want the style lists that are inside of。

![](img/5b25f9189e795f9881b6a35947d0e23f_129.png)

certain classes I can use these，descendant and child selectors to add。

styling in those particular ways and，there are a number of other CSS。

selectors we can add as well and we'll，go ahead and explore a couple of these。

just to give you a sample of how some of，these CSS selectors can actually work。

and we'll start by taking a look at the，descendant selector which is used to。

select all the elements that are，descendants of some other element for。

example so let's go ahead and create a，new file that I'll call descendant dot。

HTML and then again we'll start with the，same code and inside the body of this。

page I want an ordered list that maybe，item，and it turns out with lists in HTML you。

can nest lists inside of other lists，maybe you've seen bullet points where。

there's like nested bullets inside of，other bullet points I can do that here I。

can add an unordered list and create a，sub list like sub list item 1 and sub。

list item 2 and maybe down here。

![](img/5b25f9189e795f9881b6a35947d0e23f_131.png)

here's another list item such that now I，have a couple of items but some that are。

inside of an unordered sub list let's go，ahead and open up descendant HTML and。

see what that looks like so here's what，we have we have list item 1 list item to。

another list item that is probably，actually list item 3 so we have three。

items but inside of list item two I have，an unordered list let's imagine for。

example that I wanted to only style。

![](img/5b25f9189e795f9881b6a35947d0e23f_133.png)

these sub list items as a particular，color and maybe I want those to be blue。

for example if in the Style section of，my webpage I say that I would like for。



![](img/5b25f9189e795f9881b6a35947d0e23f_135.png)

all list items to be styled blue well，then not styled colored blue rather then。

what I'm going to see when i refresh the。

![](img/5b25f9189e795f9881b6a35947d0e23f_137.png)

page is that all of the items are going，to be blue instead of just the two sub。

list items but I could instead say that，you know what I only want list items。

that are children of unordered lists and，I can do direct children using this。

greater than symbol to say that only if，there is a ul that immediately contains。



![](img/5b25f9189e795f9881b6a35947d0e23f_139.png)

an Li within it then I would like for，that to be colored blue and now if i。

refresh that now you'll see that the，ordered items list item 1 2 3 those do。

not get colored but only the list items，that are inside of the unordered list。



![](img/5b25f9189e795f9881b6a35947d0e23f_141.png)

that are directly children of that，unordered list actually get the CSS。

styling applied this greater than symbol，here is specifying immediate children I。

could get rid of it ul Li like this and，this would also work you still see sub。

list item 1 and 2 but this is a more，general selector called the descendant。

selector that selects all descendant，elements so they might not be the。

children elements they might be，grandchildren elements so，speak if those children elements have。

other children that are attached to them，as well again for all of this is helpful。

to begin to think about things in terms，of that document object model that Dom。

structure that tree that represented how，all of our various different HTML。

elements are related to one another so，next up we can begin to take a look at。

some of the other selectors that we have，access to so one of those selectors。

might be something like modifying and，went only on a specific attribute of a。

particular HTML element so we can use，the attribute selector for that I'll。

create a new file called attribute HTML，we're here let's go ahead and create a。

unordered list that's going to have a，number of different links to various。

different websites so here's a list item，that is going to be a link to Google so。

I'll link to Google comm and say Google，and I'll go ahead and add a link to，facebook。

com call that Facebook and I'll，go ahead and add a link to amazon。com。

and call that Amazon and let's imagine，for a moment that I only wanted to style。

the Facebook link like I want to really，highlight the Facebook link tell people。

to click on that one as by coloring it，an entirely different color well to cut。

to style links normally I would say，something like links should be colored。

you know blue for example their color，blue by default but I could be explicit。

about it and say links should be color，blue like that。



![](img/5b25f9189e795f9881b6a35947d0e23f_143.png)

such that now when I open up attribute。

![](img/5b25f9189e795f9881b6a35947d0e23f_145.png)

HTML all of the links are colored blue，but I could also say I would like links。

that have an href attribute of，facebook。com I would like those links to。

be colored red instead so this squ*re，bracket notation I can use to specify a。

particular attribute of an HTML element，only anchor tags a tags whose href is。



![](img/5b25f9189e795f9881b6a35947d0e23f_147.png)

equal to facebook。com those should be，the only ones colored red so now when i。

refresh this I now see that Facebook is，a link that is now colored red instead。

of colored blue because I've been very，specific about picking an attribute that，I would like to use。

in order to reference that particular。

![](img/5b25f9189e795f9881b6a35947d0e23f_149.png)

HTML element and we can use CSS，selectors in more powerful ways to maybe。

not just to style a particular element，always but to style an element only。

under certain conditions or only when an，element is in a particular state and。

this is very often done for something，like when you hover over something when。

you hover over some button and something，pops out or you hover over something and。

it changes color slightly we can begin，to do this by adding what we call a。

pseudo class to a CSS selector so let's，take a look at an example of that to see。

how we can modify an element when a user，hovers their cursor over that element。

for example so I'll go ahead and open up，a new file hover HTML we're here I'll go。

ahead and inside the body of the page，just give myself a button this button is。



![](img/5b25f9189e795f9881b6a35947d0e23f_151.png)

going to say click me and let's add some，style to the button by default buttons。



![](img/5b25f9189e795f9881b6a35947d0e23f_153.png)

show up as fairly simple buttons that，just look something like this I might。

like to add a little bit more to this，button and say you know what let's add。

some style to the button and give it a，width of 200 pixels a height of 50。

pixels and a font size of 24 pixels and，maybe a background color of green for。



![](img/5b25f9189e795f9881b6a35947d0e23f_155.png)

example so I specified some size，information how big I'd like the font to。

be and also a background color for the，button such that now here's what that。

button looks like shrink it down a，little bit it says click me but many。

buttons especially nowadays are a little，bit of they give you a little bit of。



![](img/5b25f9189e795f9881b6a35947d0e23f_157.png)

feedback you hover over them and they，change their color slightly how do they。

do that well often it's using a CSS，pseudo class where I can say button ：

hover meaning when I am hovering over a，button then I'd like you to change the。

background color to orange for example，some other color so now I specified that。

by default normally for a button your，background color should be green but。

when the button is being hovered over。

![](img/5b25f9189e795f9881b6a35947d0e23f_159.png)

instead now change the background color，to orange such that now when I open up。

this page and go to click me if I hover，over the button the color of the button。

changes normally Green changes to orange，it's，that is a very powerful feature that we。



![](img/5b25f9189e795f9881b6a35947d0e23f_161.png)

have access to as well alright so now，we've seen how we can use various。

different CSS selectors to very。
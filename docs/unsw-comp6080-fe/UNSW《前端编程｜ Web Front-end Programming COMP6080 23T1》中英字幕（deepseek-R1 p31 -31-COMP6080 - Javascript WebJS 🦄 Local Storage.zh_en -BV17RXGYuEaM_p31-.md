# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p31 -31-COMP6080 - Javascript WebJS 🦄 Local Storage.zh_en -BV17RXGYuEaM_p31-

Hey everyone in this lecture we're going to learn about a way of saving data across different browser sessions and this method is called local storage so let's dive in。



![](img/78ac387a051afbb2adae255be751dbf9_1.png)

So so far， when we've had data and state in our memory in our JavaScript and react projects。

 this data is transient， which means that when we refresh the page。

 it disappears and it also means that it can't be accessed between different browser sessions。

But often we want our data to be persistent between sessions for example a user might have some settings and we want to save those settings for the next time they visit the site when we want to store data we can store it server side in a database or we can store a client side for example in local storage。



![](img/78ac387a051afbb2adae255be751dbf9_3.png)

So like I mentioned on the previous slide， assistance can be done in two ways。So most traditionally。

 when we want to store data we do so on the server in a database。

 so this involves making requests to the back end server when we want to retrieve and modify data and then the back end endpoints will do something with that data and save or retrieve it to and from the database。

Now we also have the option of storing things client side。

 which means storing info on the user's machine in their browser。

 so this can be done using local storage。NowCl side persistence is not a replacement for serverside persistence。

 it has a few pros and cons which we'll dive into later but its main limitation is that the data stored client side is only accessible for that specific client。

 it can't be accessed by any other devices or users since it's not in the Surs only on the client。

However， clientside persistence is still a really quick and easy way of adding persistence to your site。

 so we're going to focus on that in this video and we're going to dive in how to do this using local storage。

😊，So what is local storage？Local storage is an API which exists in the browser。

 which allows you to read and write to a storage object in the document。

 and this data which you write to the storage object is persisted between sessions。

 which means it stays if the user refreshes or closes their tab or browser。

Let's take a look at some of the pros and cons of using local storage。

 and then in a moment we'll dive into how to use the local storage API in JavaScript。

So let's look at some of the limitations of local storage first in some situations where you wouldn't want to use local storage。

So the first point is that local storage is not secure， local storage is accessible by any webp page。

 so if any webp page knows the key which you used to store the data。

 then it can access and change the data you've stored so in any situation where security of data is important。

 for example， things like passwords or personal information， local storage shouldn't be used。

Secondly， there's storage limitations to local storage。

 so there's a limit to the amount of data you can put in local storage and this just depends on which browser is being used。

So even if you're not personally storing a lot of data in local storage。

 if other websites that the user is using have stored a lot of data in local storage。

 the user's browser might already be at its storage limit from another website and you might hit quota limits when you try to use local storage so yeah when you hit a quota limit you won't actually successfully be able to save data so for any crucial information or for large amounts of data local storage is not a great solution。

The third limitation is local storage only supports storing strings so it accepts key value pairs and the values are only strings so it's not good for storing complex data so this isn't a very hard or serious limitation as you can always serialize a JSO object into a string but it's just worth noting that if you use local storage for storing complex data then you'll need some extra work to serialize and decsialize the data Finally local storage is not suitable for data which is needed on multiple devices so like I mentioned earlier。

Since it's stored client side， it's only accessible on that specific client。

 so yeah it's not useful for data which is needed by multiple users and it's not suitable in cases where the user needs that data if they go onto your site on a different device。

Alright， so now let's look at the use cases for local storage so local storage is great for a few reasons firstly it's very useful for when you have a front end only site with no server。

😊，Yeah， it's just a very quick and easy way to add some persistence。😊，Secondly。

 it's good for storing information which is not crucial if it's lost。

 so being stored on the client means if the user clears their local storage or clears their browser storage。

 they'll lose what you've stored。On top of that， if they want to access your site from another device。

 they won't be able to access the data stored in local storage。

 so I'd recommend using Gi for noncr data。And finally， we've already briefly touched on this。

 but the data being stored on client side means it's available to a specific user friendly。

So some examples of things you should use for are things like personal site preferences。

 for example it uses custom color scheme or persisting their previous activity， for example。

 on a shopping website， you might want to store the contents of their shopping cart and not lose that when they leave the page。



![](img/78ac387a051afbb2adae255be751dbf9_5.png)

Alright， now let's take a look at how we can actually use the local storage API in JavaScriptscript。

So the browser's local storage is a big object consisting of key value pairs。

So we can read and write to it， similar to it a map in JavaScript。

So you can see on the first line here。To add a key value pair to the local storage object。

 we can use set item， so that's just local storage dot set item and accepts the key and the value。

If you've if an item already exists in local storage with that kit， that item will overwride it。

Next we can use G item with a given key to retrieve data from local storage， so local storage。

gt item if you pass in a key that will return a value if it exists if it doesn't exist it'll just give you undefined。

To remove an item from local storage with a Gu key， we can do local storageage。remove item。

And finally， if we want to clear all the items in local storage， we can do local storage。clear。

Allright， let's do an example。

![](img/78ac387a051afbb2adae255be751dbf9_7.png)

All right， so you may remember from last week's lectures on forms that we created this example of a form for a user to create an account。

 so it's just a he T which has a username， date of birth， password。

 state and a file handler and we've also got some JavaScript over here which handles submitting the form。

Now we're going to add some local storage to this to persist the data which the user has entered into the form。

 so just to quickly demonstrate the issue here， if I type in some data and I start entering in some data like my data birth。

 if I refresh the page。I've lost all the data that I've typed in。

 which can be pretty frustrating for a user， so often what websites will too is they'll keep the data in the form using local storage。

Now I mentioned earlier in the lecture that storing secure data in local storage is not necessarily a good idea because local storage does have some security issues。

 but just for the sake of this example to demonstrate how to use local storage。

 we're going to store all the createate account info in local storage。So let's get started。

So what I want to do is I want to add an event listener for when a user changes what they've entered into one of these fields。

 so to do this on each element in the form I'm going to listen to the change event。

What I'm doing is I'm calling array from sign up form。

 which gives me an array of all the elements in our C account form。And I'm going to loop over this。

Now in my4 each， I'm going to add a change listener to every element in the form。

I'm going to do element do add about this all。The change。And before I start using local storage。

 I'm just going to console log the value to show you how we can get the value from this change event listener。



![](img/78ac387a051afbb2adae255be751dbf9_9.png)

Al right so if I start typing in the form， I type Anna。

 you'll notice when I change the value of one of these elements。

 I'm con logging the elementss name and its value so here's company we named Anna。

Same thing happens the date of birth。And you can see it's working for all my fields。

Now inside this event listener instead of just console logging what I want to do is I want to save whatever I've typed in into local storage and for the key I'm going to use the elements name for the value I'm going to use the elements value。

 so let's do that now。I'll bring first to page。Cool。

 so when I've entered in Anna I've now set this item in local storage now just in the browsers console I'm going to try and get this value just to see if it works properly。

CoSo you can see when I call local storage。 get item name it's console logging Anna。

 so I've correctly saved the value in local storage when I've changed the value if I try typing in something else like Anna2。

I've typed in Ana2 if I call get item again， now it's updated so our on change listener is working and we're correctly setting the item in local storage。

The last thing I want to do is when the page loadbes。

 I want to populate this form with all the fields which were previously entered into local storage。

So to do this， I'm going to set element dot value to the item which I retrieve from log storage。

So here I'm just doing element dot value equals local storage doget item and using the key element dot name。

Now just quickly， I'm going to add a check to make sure that the current element is not the file input element because this needs to be a file name and we don't want to be able to programmatically set it to a string that's not a file name。

 so let's just quickly add in a check。And we also don't want to change the value of the submit button。

Sinceensus is also one of the form fields， so I'm just going to check that type does not submit。

 let's try and run this， so I'll fill in the form。

![](img/78ac387a051afbb2adae255be751dbf9_11.png)

Okay， and I'll choose the image and then when I refresh the page。



![](img/78ac387a051afbb2adae255be751dbf9_13.png)

You'll see that all these fields are already filled in with the data that I entered before I refresh the page。

Alright so that's it for this example on local storage and that's it for this video so thanks so much for listening I hope you learned something。



![](img/78ac387a051afbb2adae255be751dbf9_15.png)
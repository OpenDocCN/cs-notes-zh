# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P60：4_命名约定.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now， you know the importance of API endpoints and how they determine precisely what data the server will send to your app。

But a well designed end point also conveys valuable information about its purpose。

 which is helpful for developers and the project itself in the long run。 Your rest A's。

 uniform resource identifier or U R I is one of the first things that users will notice when a page loads。

 It is also called an end point or U R path。 First impressions always make a big difference。

 And that is why naming conventions for As are important。

This video will help you name your API endpoints for maximum clarity and impact。 Let's get started。

Say the little Le restaurant menu app needs As to display all their orders。

 A suitable API end point is forward slash orders spelled with a lowercase O and not orders spelled with an uppercase O。

So your API endpoint should always use lower case letters and hyphens to separate multiple words。

Using underscores or snake case， title case or camel case to separate words is not optimal because it makes the names difficult to read and understand。

 There is an exception to the camel case rule， though。 if your API accepts a variable， for example。

 a user I D or order I D， you should always represent them in camel case and wrap them in curly braces。

For example， if you want to create an API for a specific order， it should be forward slash orders。

 forward slash open curly brace order I D with a capital I close curly brace by adding forward slash menu hyphen items to the API endpoint。

 you can fetch the menu items for a specific order or you can fetch orders of a specific customer by changing the I D to customer I D wrapped in curly braces and adding forward slash orders。

Notice that the API end pointss contain two different variables， order I and customer I。

 and they are both denoted by wrapping them in curly braces and writing I D with a capital I Also always try to use clear。

 concise and meaningful words in your API names to make them easy to read right away。Next up。

 the use of forward slashes。If your project has related objects。

 you should use forward slashes in your API URIs to indicate their hierarchical relationship。

An example of such a hierarchy is a customer can have orders with order items in a restaurant API project。

 Another example is a library can have books with authors， so to get the author of a particular book。

 you can use the API endpoint library forward slash books forward slash and then book I wrapped in curly braces and finally forward slash author。

Or to get all books written by a particular author。

 you can use an I D for the author instead and add forward slash books。

 Not how the relationships between the customers and orders。

 the books and the author are all indicated with the forward slash in these API U Rs。

 Another naming convention is that your API should always use a noun to indicate the resources it is dealing with。

An API that returns a collection of books or a book should use the nouns， books， or books。

 and book I wrapped in curly braces。Similarly， to get the price of a book， you should use the nouns。

 books， book ID， price。A PI endpoints with verbs like get all books or get user user I D are examples of bad API names。

 That's because the resources and arrest API endpoint should be always represented with a noun and never with a verb。

APpiI endpoints such as users， user ID， De， or orders， order ID save。

 are also wrong because they use HTTP requests as verbs to indicate the action the API performs。

Remember， you should send an HTTP delete request to Use user ID to delete a user。

And you should send an HTTP put or Pat request to orders Order I D to update the order。

Endpoints that use standard CrD operation names such as create， read， update or delete。

 should be avoided for two reasons。The resources these endpoints represent should be nouns。

 and the appropriate HTTP requests like get， post， put or delete should be used with those endpoints to perform the necessary manipulations。

Something else to consider is whether file names should be used in APIs。

 The restaurant API project can return API results as XmL and JSsonN data。 So the question is。

 can you design your endpoints as orders order I do Json to get the JSsonN data or perhaps orders order I do Xml for Xml data。

 No， you should never use a file name extension in your API。To solve this problem。

 you should accept the expected data format as a query string parameter。

 So if you want the output in a Json format， you can add question mark format equal sign Json to the API endpoint。

And for XML， you can use question mark format equal sign XML at the end。Similarly。

 to deliver a minified version or source version of a jascript file。

 you use API end pointss like forward slash assets， forward slash JS forward slash J query。

 forward slash 3。6。0 forward slash min or forward slash assets。

 forward slash Js forward slash moment， forward slash 2。29。4 forward slash original。

 But what if you need to filter a collection or perform a search。 For instance。

 the little lemon restaurant has many items on its menu。

 But you are only interested in appetizers to filter the results。

 you should always accept the data as a query string parameter。In a URL。

 everything you send after a question mark is a query string。 Remember。

 the API end point menu items returns all menu items， but to only get the appetizers。

 you should pass the category name to the end point as question mark category equal sign appetizer。

Consequently， if you design APIs that can be filtered this way。

 other developers on your team will derive that to get a list of mains or desserts。

 they can change the end point to question mark category， equal sign， main。

 or question mark category， equal sign dessert。

![](img/3d236c991e8f0f4207112da358c13672_1.png)

This is the beauty of a good and consistent API naming strategy。

Another best practice is that when you share your API endpoints with your team or the public。

 you should never add a trailing slash to the end of the API endpoint。

 What this means is that API names that end with a forward slash like orders。

 order I D and curly braces followed by a forward slash is bad practice。



![](img/3d236c991e8f0f4207112da358c13672_3.png)

So is sports， basketball teams， followed by another forward slash at the end。

Simply end the API without the forward slash at the end。

So if you want to become a fluent back end developer。

 you need to pay attention to your endpoints and make sure you use well designed and user friendly APIs。

Let's recap the best practices discussed in this video。Use lowercase U or I formatting。

Indicate hierarchical relationships with a forward slash。 Use nouns for resource names。

 Avo file name extensions。Furthermore， use query parameters for data types and don't use a trailing slash。

Finally， always follow a consistent naming strategy and standard API naming conventions。



![](img/3d236c991e8f0f4207112da358c13672_5.png)

Well chosen names for API endpoints can significantly improve an entire project by making it easier for other developers to use your APIs。

 and now you are well on your way to creating good API endpoint names。


# IBM网络安全分析师专业证书课程4：《网络安全与数据库漏洞》｜network-security-database-vulnerabilities｜ - P114：55_01_sql-injection-part-1.en_subtitled - GPT中英字幕课程资源 - BV1RN411q7PY

![](img/70a56d316649db7858280604efdeedff_0.png)

Yes。In this video， you will learn to describe SQL injection and what makes an attack possible。

Describe common types of SQL injection， including error based， union based， blind injection。

 and out of band。

![](img/70a56d316649db7858280604efdeedff_2.png)

So let's go to SQL injection。So just as Oman injection。

 this is abuse of vulnerable application functionality that causes execution of SQL queries。

 so it queries executed by database systems。

![](img/70a56d316649db7858280604efdeedff_4.png)

Possible in pretty much any SQL database。 and the main mitigation。Is also input sanitization。

So let's look at an example， let's say we have a login dial。

 you probably have something like that in the application you are developing。And very often。

 what we've often see in the code is that there's， in this particular case， a Java statement to。

App piece together a sequel command。And just directly embed username and password in that SQL statement。

 So when user is found in the database that matches that username and password will let the user in and when the input is benign。

 then everything works fine。 However， let's see what happens if an attacker inject something malicious。

 So at the very bottom there is a statement here that。Actually does not specify any passwords。

 password is left blank， but the username is kind of interesting。 it starts with a single quote。

Then there is an or statement。Or one equals  one。 Then there's a semicolon。 And there's a dash dash。

 So let me， let me go through that to explain what's what's going on。

 So as you can see in the sQL syntax， the value is often。

Surrounded by single quote so what the first single quote here does it actually closes the value for the username and what happens next is attacker adds a boolean clauses or clause and then an expression one equals one one equals one will always be true right and if you're familiar with boolean logic if if there is something or truth then the result of that expression is always true and the rest of the syntax is the semicollon just separates different sQL ques you you could change them using semicons and dash dash in many sQL flavors is a comment So basically comments out the rest of the line So the quote and pass equal equals quote quote is actually ignored so essentially an attacker has turned our SQL query in into the one that。

Finds any user。In the user's table。Does not check the username， does not check the password。

 and just blindly lets people in。So you could， with this very simple piece of text。

 bypass your logging and dialogue on a vulnerable system， and we have seen examples of that。

So what are the dangers of that well as first of all。

 the first of one that comes to mind bypassive authentication mechanisms， then data exfiltration。

 exfiltration is a kind of a I guess military term it comes from you know ability to extract something。

So。Attackers can steal data。 that's you know， in a lot of hacks that you read about in the news。

 they steal customer data。 That's how it's done by using SQL SQL injection。 pretty often。

 you could even execute OS commands in some variance of SQL， you could specify an O command to run。

 So if youre able to somehow inject this SQL statement here and copy select one to program and then B O command。

 you could get。That OS command executed。And also there's always vandalism or denial of service attacks you could。

 for example， tell the SQL server to delete the table and your system is dead after that pretty much so with one simple request that contains the SQL injection command you could bring the whole system down to in sneeze and there is an example down there for that that shows the use of semicolon to separate statements so you could。

Do not assume that if they can inject something malicious in your  query。

 that they could not execute other queries as well。

 there are ways to chain queries together and execute nested queries as well。

 there are many variants of SQL injection there is error based so attack attacker may look at how your system behaves based on the error messages that it gives back So giving back you know private information in the database error directly to your application user tells them a lot about what's going on on the backend and allows them to tailor their commands。

There is union based circle injection， so for example， this is an interesting case。

 this is how data actually could get exfiltrated from the system。

 we have a query here that gets the name and some text from the log file where there is a particular date that's used as the filter and that date in this case is under the control of the application user。

If there is no input sanitization in place， they could specify more than just the date。

 they could add a union clause to that query。Select， let's say。

 username and passwords from a completely different table from a user' table。

 and that would be added。To the output so this way when they abuse the functionality that loads data from the log。

 this functionality will return names and text from the log for a particular date and appended to that will return username and passwords which is something you don't want to happen there is also blind injection this is an interesting one because sometimes people say。

 well you know yes I run SQL quez， but no data is returned to the user what's the big deal in this case there are actually many ways to do injection blindly and guess what data is just by the behavior of the system there are two main types which willbased which is you run a query and as you tweak the parameters there could be one or two possible responses and because of how the system response you could little by little guess what the data is or there could be time-based for example。

 you could sneak in at delay。Into your query execution so that if data is of certain type。

 it does not delay。 and if there is something else in the content， it does delay。

 So it's probably easier to explain using an example in red here。

 we have SQL expression that says that if password starts with the letter a then slip for 10 seconds otherwise return false。

 So when the attacker executes this expression。 if they guessed correctly。

 the response will come back 10 seconds， 10 seconds or 10 millisecond。

 I'm not quite sure but will come back delayed whereas for all other characters they try。

 they will be no delay。 So by being able to execute let's say 26 queries to account for all the letters in English alphabet they would be able at the end of that they will be able to know the first letter in the password So if there are no restrictions on the number of queries you could execute。

 you could write a script that tries。Lettter in the password one by one for each letter。

 you know go through all whole range of possible values and that way you could discover the password without ever getting data output to the screen from the database so you have to be careful about that。

 even if your application does not return data by attackers if they can sneak in SQL injection。

 they could get to the contents。It is also out of band SQL injection where they could trigger requests to other sites and exfiltrate data through some other ways。

 not even through your application， but through other channels。



![](img/70a56d316649db7858280604efdeedff_6.png)

![](img/70a56d316649db7858280604efdeedff_7.png)
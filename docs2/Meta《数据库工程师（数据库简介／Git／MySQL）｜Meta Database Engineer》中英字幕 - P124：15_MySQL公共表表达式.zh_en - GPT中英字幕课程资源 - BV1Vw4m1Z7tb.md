# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P124：15_MySQL公共表表达式.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When working with databases， you'll often need to write complex SQL queries。

 These can be difficult to manage。 However， you can optimize these queries by compiling them into simple blocks using a common table expression or CTteE。

 In this video， you'll learn how to make use of CTtes to optimize your database queries。

 Over at Luc shhrub， the finance department must calculate the average sale for each customer over the last three financial years。

 to carry out this task。 Luc shrub need to create one select statement that contains several complicated SQL queries that include functions。

 strings， operators and clauses。 Fortunately， you can help Luc shrub to minimize the complex of these queries using a CTteE。

 Before you help them out。 let's explore the basics of a CTteE。

 A CTteE is a method of optimizing complex database queries by compiling them into simple blocks of code。

 These blocks can then be used to rewrite the  query by calling the CTteE。😊，required。

 this simplifies the query and makes it much easier to read and maintain。

 A common table expression can be created for one or multiple queries。

 It all depends on the requirements of your database。

 Let's begin with an exp of the syntax for a single C T E。

 The syntax for a single C T E query uses the with clause to start the common table expression。

 This is then followed by the name of the C TE。 This can be a custom name。

 The as keyword is then used to associate the query within parentheses with the C T E name。 Finally。

 create a select statement to query the name of the common table expression。😊。

The syntax for creating multiple queries is a bit more complex。

 Start your code block using the width clause， then list the queries underneath the width clause。

 make sure that each query has a unique name and is separated by a comma。 finally。

 type your select statement。😊，To execute a CTE， type its name after the select statement。

 or you can execute multiple CTE at once to execute more than one CTE at a select statement for each CTE。

 place a union operator in between your statements to return data for all statements in the output result。

For example， Luckyy Shrub can use multiple queries to calculate their average sale Let's explore Lucky Shrbb's use of CTEs in more detail。

 see if you can help them out using your new skills。😊。



![](img/4b5e4f1c13ec49162cb8e04d9db5052c_1.png)

As you discovered earlier， lucky shrub need to calculate the average sale over the last three financial years。

 Their current approach is to create three separate select statements，1 for each year。

 The statements are combined using a union operator。

 Each statement calculates the average cost by using aggregate and string concatenation functions。

 The data is extracted from the orders table， and the conditions are specified using a wear clause。

 You can click enter to execute these statements and return the average sale for each year。

 Although they work as intended， these queries are quite complex and difficult to manage。

 but you can use a common table expression or C T E to improve their readability。😊。

Start by using the width clause。 then rewrite the first expression as average sales 2020。

 followed by the required logic。 You can use an as keyword to return it as average sale for improved readability。

 Then create the second and third expressions。 Use the as keyword to associate the expression with the query and make sure that each expression is separated by a comma。

 Now， you just need to type three select statements。

 Each statement uses an asterisk symbol to extract all data from each of the three expressions。

 Place union operators between the queries to combine the results。 Finally。

 press enter to execute the code。 The output is the same as the last query you execute it。 However。

 this time， you've created a query that is more optimal。

 All expressions are now contained within a simple block of code that is easy to read and maintain。

 You should now be familiar with how to use a C T E to optimize your database。 Nice work。😊。



![](img/4b5e4f1c13ec49162cb8e04d9db5052c_3.png)
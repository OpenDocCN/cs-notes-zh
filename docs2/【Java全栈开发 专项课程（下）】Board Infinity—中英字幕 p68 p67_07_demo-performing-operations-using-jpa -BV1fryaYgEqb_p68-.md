# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p68 p67_07_demo-performing-operations-using-jpa -BV1fryaYgEqb_p68-

![](img/59155540da3b9a2b3af60d31ad6b214f_0.png)

Hi there Today in this session， I will be performing the operations using JA， so let's get started。



![](img/59155540da3b9a2b3af60d31ad6b214f_2.png)

So here I already discussed I' am creatingEmploy repository where the employer repository is extending the JPA repository。

 JPA repository will take to entities the entity by which you wanted to do the operations and the unique key column type in my case the employee ID is long by which the operations will be handled。

So if you will go to the Jpa repository。It will just open up the declaration。

So you can see that the type hierarchy says that its being implemented by all the methods that we have inside it。

 whatever ID type you are passing， you can see that it's a generic type so ID is being taken by the type that you are passing along with that if you wanted to add the operation such as search filter in all the methods or find by methods you can just be adding it here。

Firstce that I have created a service what all service methods I wanted to implement and I wanted to create create contract of it。

My entity is employ， so I will be creating five common methods here saveEmploy get all employ get employ by ID。

 which is taking up the ID as a parameter update employee on the basis of ID and delete employee by ID。

This service class needs to be implemented I will be you can see that employer repository class is being injected here。

 converting that into the service so that it will be injectable to my controller as well。

 employer repository object can access all the methods that by default available to me under the GPA。

So we can see that you you are going to inject this dependency into the constructor。

 I have already demonstrated you multiple times how to do that。

SaveEmploy is the Manve method that we have created in passing the object and you can see that I' am not writing any grid operations or queriesEmploy repository is extending the JPA JP has a method called save will pass on the object and will save。

Now the question is on the which basis of which operations or its the data would be saved。

 so here is the application do properties where all the configurations are returned。In my case。

 this is integrated for my SQL， my data source is my SQL database name is training DB。

Here the data source name is rude， username is rude and the password is route at date rate。1，2。

 three， four，56 hash has here the dialect is my SQl5 dialect， you can use dialect or five。

Here we have hibernet DDL auto I have just taken create because for the first time I wanted to create a schema into the database。

 once your first execution is done successfully I will suggest you to keep it changed to the update。

 otherwise it will every time it will create a new database for you。Here。

 what if methods you can see that get all employees get employed by I D。

Update employ and delete employee just you need to call a specific repository method。

You can see that I'm attaching the receiver's not found exception because I wanted to handle the receiver's not found exception as my own custom exception。

Where I say that if an exception is their a record I wanted to print the Se name field name on which exception has occurred and the field value。

 so I have all these class level variables extended which I wanted to initialize into the constructor and print with the help of their getters only which is I am not there is no point of setting the values at this stage as well。

Further we have employee controller where the rest controller is annotated。

 so any API URL that starts from APIEmploy will be taken it up as an employees request employee services there injected the employee service as a constructor。

And here we have get mapping that will return all the employees by I D。

 It will return the employee by the I D。 put mapping will take a I D if the object is found。

 It will update otherwise say receiver is not found。

And delete will actually delete the object on the basis of ID and will print a message employer delete successfully。

That's how the Ced operation works with the help of Jpa。

 the beauty of JpaA you might have seen in the repository that you do not need to write down any cred operations or query。

 The queries are handled implicitly with the help of the OM and the J persistence API integration。

See you in the next session until next time stay tuned， Thank you。



![](img/59155540da3b9a2b3af60d31ad6b214f_4.png)
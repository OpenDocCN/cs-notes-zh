# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p66 p65_05_hibernate-jpa-annotations -BV1fryaYgEqb_p66-

![](img/4ea0f49761a87dfe16a7164cbaa6dafc_0.png)

Hey guys， today in this session I will talk about tabnet JpaA annotations that you can use while working with Jpa in a larger application you can see that the first is the entity the JpaA entity don't need to implement any interface or extend a super class This entity annotation to be used along with the class that needs to be communicate with the relational mapping tool next is the table by default each entity class maps a database table with the same name in the table before default schema of your database you can customize this mapping with using name schema and catalog。



![](img/4ea0f49761a87dfe16a7164cbaa6dafc_2.png)

Next step， we have is I D。ID， JP and hibernet requires you to specify at least one primary key attribute for each entity。

 and you can do that by annotating an attribute with ID annotation。Then we have generated value。

 generated value is to be taught when your ID needs to be generated as a sequence or auto inement database column。

If you annotate your primary key attribute with a generated value annotation。

 you can use a database sequence by setting the strategy attribute to generation type sequence。

 or if you want to use autoincremented database column， then you can go for identity。

Then we have one2 one， one too many， many to one and many too many relationships these basically helps in associating the mappings you can also map associates in the table model there are modeled as foreign key columns and that needs to be decided what type of association you wanted to create。

 such as mention one2，1，1 to many， many to one and many too many。

So these annotations helps in creating your GPA more elaborate。

You can also use some more annotations， just like join column， transient， temporal and lo。

Loob is basically when there is all almost no limit in the size as string or white。

 and that's not the case of relational database you can define with the help of。

Law law and there are many law itrations that converts into the database such as B or G。

Temporal is basically if you are still using Java dot u dot date or calendar as your attribute types。

 you need to annotate the attribute with temporal。Using this。

 you can define if the attribute shall be mapped to the SQL date time at stamp or not。

Then we have a transient transient is something called specific that an attribute should be persisted into the database or it should remain only at the object level or the GPA level join column basically helps in creating the association when the foreign key column is automatically created。

 but you don't want that automatic column to get created you can manually create your join column that will be considered as a foreign key column as well。

I hope basic idea will be clear to all of you， as I said。

 more will be clear to you when the things comes into the picture。Until next time， stay tuned。

 thank you。 See you in the next session。

![](img/4ea0f49761a87dfe16a7164cbaa6dafc_4.png)
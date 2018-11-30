#__Boyce-Codd Normal Form (BCNF)__

The reason for Boyce Codd Normal Form is to separate entities where a non-prime attribute cannot identify a prime attribute or has multiple candidate keys. Breaking down these entities and creating new entities in their place helps strengthen data quality and reduce redundancy as well as reducing update, insert, and delete anomalies.

Example: Non-BCNF table

	Here we have dependencies:
		(Employee ID, Project) ----> Project_MGR
			    Project_MGR ----> Project
 
 
    The problem for this table is that the project_MGR can identify the project. Which does not meet the condition 
    for BCNF
    
**Prior knowledge for this tutorial**

[Normalization](https://www.techopedia.com/definition/1221/normalization)

[Relational Schema](https://medium.com/@kimtnguyen/relational-database-schema-design-overview-70e447ff66f9)

[1st Normal Form](https://www.essentialsql.com/get-ready-to-learn-sql-8-database-first-normal-form-explained-in-simple-english/)

[2nd Normal Form](https://www.essentialsql.com/get-ready-to-learn-sql-10-database-second-normal-form-explained-in-simple-english/)

[3rd Normal Form](https://www.essentialsql.com/get-ready-to-learn-sql-11-database-third-normal-form-explained-in-simple-english/)    

##__Definitions__

*BCNF*: A stronger type of database normalization than 3rd normal form. The reson you want to use BCNF is because it insures that you do not have multiple overlapping candidate keys. Scroll down to see an example of converting from 3rd normal form to BCNF.

*Candidate Key*: A collection of attributes which act as unique identifiers for an entity

*Non-Prime Attribute*: Any attribute not in the candidate key

*Normalization*: A method of reducing dependency and redundancy of data, making the database more efficient and, in some cases, easier to read.

*Prime Attribute*: Attributes that form the candidate key i.e. the attributes that the entity can be found by. Marked by an underline

*Primary Key*: An attribute within the candidate key which is used as the primary identifier for the entity. Ex: Social Security Number for a person.

A *relation schema* R is in BCNF if whenever a nontrivial functional dependency X → A holds in R, then X is a superkey of R.

##__The Process of Converting From 3rd Normal form to BCNF__

Below is a table in 3rd normal form but not BCNF because employee id and project are both prime attributes but PROJECT_MGR is not a super key, however project manager can lead to project.

![](./images/firstTable.png)

To change from 3rd normal form to BCNF is to separate the table into two entities. In this case we can split EMPLOYEE ID into its own entity, which we will call EMPLOYEE. The remaining attributes, PROJECT_NAME and PROJECT_MGR, can be its own entity, which we will call PROJECT. We then add a new attribute to each of these entities so that we can get from one to another. We’ll call this new attribute PROJECT_ID.


You fix this by splitting this into two table the EMPLOYEE entity would be:

**EMPLOYEE**

![](./images/secondTable.png)

The PROJECT entity would would be:

**PROJECT**

![](./images/thirdTable.png)

This is now in BCNF form because PROJECT ID is not a primary attribute in the PROJECT table. Thank you for following this tutorial!




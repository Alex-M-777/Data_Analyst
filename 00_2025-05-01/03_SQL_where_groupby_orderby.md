# WHERE and GROUP BY & ORDER BY

## where im watching

⭐️ Chapters ⭐️

00:30:57 SQL Basics Tutorial | Where Statement
00:38:54 SQL Basics Tutorial | Group By + Order By Statements

## Where Statement

- =
- <>
- <
- >
- And
- Or
- Like
- Null
- Not Null
- In

I've touched on this before, but it basically specifies stuff.

```
SELECT * 
FROM EmployeeDemographics
WHERE FirstName <> 'Jim'
```

outputs all first name except jim

```
SELECT * 
FROM EmployeeDemographics
WHERE Age <= 32 AND Gender = Male
```

Returns age less than equal to 32 and male.
- and contional BOTH
- or contional EITHER

### Wildcards

```
SELECT * 
FROM EmployeeDemographics
WHERE LastName LIKE 'S%' 
```
Outputs last names starting with S

```
SELECT * 
FROM EmployeeDemographics
WHERE LastName LIKE '%S%' 
```
Outputs names that has S anywhere 

```
SELECT * 
FROM EmployeeDemographics
WHERE LastName LIKE 'S%o%' 
```
Outputs names that starts with S and has an o

Assuming Scott last name:
```
SELECT * 
FROM EmployeeDemographics
WHERE LastName LIKE 'S%ott%c%' 
```
Does not output scott
```
SELECT * 
FROM EmployeeDemographics
WHERE LastName LIKE 'S%c%ott%' 
```
Does output scott

### Null

```
WHERE FirstName is NOT NULL
```

This would return everything when all things are filled out and vv for null

### In 

It's like equals, but better:
```
SELECT *
FROM EmployeeDemographics
WHERE FirstName = 'Jim' AND FirstName = 'Michael'
```
In makes it easier so you don't need to keep doing AND (wish I'd studied more because I def could have saved some time with this command)
```
SELECT *
FROM EmployeeDemographics
WHERE FirstName IN ('Jim', 'Michael')
```

## Group By, Order By

```
SELECT DISTINCT(Gender)
FROM EmployeeDemographics
```

Returns the very first distinct values of male and female, 

|Gender|
|----|
|Male|
|Female|


GROUP BY rolls up all the values in each row
```
SELECT Gender
FROM EmployeeDemographics
GROUP BY Gender
```
|Gender|
|----|
|Male|
|Female|

By adding count:

```
SELECT Gender COUNT(Gender)
FROM EmployeeDemographics
GROUP BY Gender
```
|Gender||
|----|---|
|Male|6|
|Female|3|

```
SELECT Gender, Age COUNT(Gender)
FROM EmployeeDemographics
GROUP BY Gender, Age
```
|Gender|||
|----|---|---|
|Male|29|1|
|Female|30|1|
|...|...|...|
|Female|31|1|

Age and Gender are fields, Count is derived and not a column.
 
```
SELECT Gender, Age COUNT(Gender)
FROM EmployeeDemographics
WHERE Age > 31
GROUP BY Gender
```

|Gender||
|----|---|
|Female|1|

```
SELECT Gender, COUNT(Gender) AS CountGender
FROM EmployeeDemographics
WHERE Age > 31
GROUP BY Gender
ORDER BY CountGender
```

Default is ascension small to big 

```
SELECT Gender, COUNT(Gender) AS CountGender
FROM EmployeeDemographics
WHERE Age > 31
GROUP BY Gender
ORDER BY CountGender DESC
```
desc is big to small

so basically im not going to type out the whole thing so ill word it out here

- Group By aggregates the data into the query which makes it easy to use count or something
- Order By sorts the output, which makes sense
- We used AS to rename the output column
- desc is big to small
- asc is small to big

You can sort many cols and prioritize based on which comes first in the statement

``` 
SELECT *
FROM EmployeeDemographics
ORDER BY Age DESC, Gender DESC
```
you can use col number instead of Age or Gender, like 4 or 5 to order

also, you can asign desc or asc in secondary order by 

This seems to conclude the basics.
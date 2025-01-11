# Select & From Statements

## where im watching

⭐️ Chapters ⭐️

00:24:44 SQL Basics Tutorial | Select + From Statements

## Select Statments 

- Top
- Distinct
- Count
- As
- Max
- Min
- Avg

## Notes

### Select

```
SELECT FirstName, LastName
FROM EmployeeDemographics
```

Grab fn ln col

### * all cols

```
SELECT *
FROM EmployeeDemographics
```

grab all row and cal

### top

```
SELECT TOP 5 * 
FROM EmployeeDemographics
```

select top 5 rows

### distinct

```
SELECT DISTINCT(Gender)
FROM EmployeeDemographics
```

Will return two results from the table, only male and female are found in the table

### count

```
SELECT COUNT(LastName)
FROM EmployeeDemographics
```

Outputs number of last names

derived info base of last name, doesnt return col name

### as (col name)

```
SELECT COUNT(LastName) AS LastNameCount
FROM EmployeeDemographics
```

returns last name count as col name

### min max avg

```
SELECT AVG(Salary)
FROM EmployeeSalary 
```

obv returns min max avg of salary


## available databases ctrl + u 

### specify the database

we are working in a tutorial database, picking from tables that exist inside the database.

> while in master database not tutorial

```
SELECT * 
FROM SQLTutorial.dbo.EmployeeSalary
```

outputs the tutorial database employee salary table


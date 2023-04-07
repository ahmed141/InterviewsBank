The following skillsets of a Python Developer that are useful for the team.

General (Basic OOP & Python concepts, Flask, Django, etc.)

Following are the areas that should be covered in an interview

## General

  * OOP
    * Class
    * Object
    * Inheritance and Composition
    * Polymorphism
    * Coupling vs. Cohesion

  * Data Structures & Algorithms
    * Pointers*
    * LinkedLists
    * Stack and Queue
    * Sorting Algos: Bubble, Insertion, Merge, Shell, Quick, etc.
    * Breath First Search and Depth First Search
    * Hash tables

  * Design Patterns
    * Creational
      * Abstract Factory
      * Builder
      * Prototype
      * Singleton
    * Structural
      * Composition
      * Decorator
      * Flyweight
      * Dependency Injection*
    * Behavioral
      * Iterator
  * Python “Advanced” Concepts
    * Dunder methods
    * Iterator and Generators
    * Closures (function inside a function)
    * Decorators
    * `@property`
    * Metaclasses
    * Global Interpreter Lock (GIL)
    * Threading and Multiprocessing (Bonus: Asyncio)
  * Coding Practices
    * PEP-8
    * Code formatting (autopep8, black, etc.)
    * Code linting (flake8, etc.)
  * Miscellaneous
    * Optimizations
      * Greedy Algorithms
      * Dynamic Programming
    * Cloud (AWS, Azure)
      * Ask general questions based on the resume.
    * Practicals
      * Print the nth number in Fibonacci Series.
      * Convert time (e.g. 5:45 PM) to string (e.g. Quarter to six in the evening).
      * Reverse an integer (e.g. 12345 → 54321).

## Data Engineering
  * Core
    * Data Pipeline
    * Data Modeling
    * Batch vs. Stream
    * Indexing
    * OLTP vs OLAP
    * Pub-Sub
  * Database
    * CAP Theorem
    * Types of Databases (Columnar, Document, Graph, In-memory, Key-Value)
    * Relational vs. Non-relational
    * ACID Properties
    * Normalization / Denormalization
    * Slowly Changing Dimensions (SCD)
    * Lag / Lead
    * Curveballs:
      * Functions
      * Stored Procedures
      * Window Functions
      * Create Table As Select (CTAS)
      * With Table As Select (WTAS)
  * Data Pipeline
    * ETL vs ELT
    * Full Load vs. Incremental Load (Delta Load)
    * Batch Processing vs Stream Processing
    * Idempotence
    * Pipeline (Workflow) Orchestration
  * Data Architecture
    * Data Lake (Bonus: Delta Lake)
    * Data Mart / Data Mesh 
    * Data Warehouse
    * Vertical vs. Horizontal Scaling
    * Master / Worker
    * Star / Galaxy Schema
    * Facts / Dimensions
    * Medallion Architecture (Bronze → Silver → Gold)
  * Tools
    * Hadoop (HDFS)
    * Apache Spark (Delta Table) [Databricks]
    * Airflow / AWS Step Functions / Azure Data Factory
    * AWS Glue, EC2, EMR, Lambda Functions / Azure Virtual Machines, Functions

### Coding Practicals

#### Databases

* Write a query to get the top 3 years of every product by sales.
```
product,year,sales
egg,2021,3432
egg,2020,134
egg,2019,53243
egg,2018,5425
egg,2017,134
egg,2016,314
bread,2021,6762545
bread,2020,2656546
bread,2019,24662426
bread,2018,2466
bread,2017,24625
bread,2016,767535
cookies,2021,3465638
cookies,2020,4565473
cookies,2019,46565
cookies,2018,3647
cookies,2017,436
cookies,2016,45653
```

* Write a query to find services that currently have the deleted status.
```
service,date,status
ec2,2021-11-25,created
ec2,2021-11-24,deleted
ec2,2021-11-23,created
ec2,2021-11-22,running
ec2,2021-11-21,running
ec2,2021-11-20,running
emr,2021-11-25,deleted
emr,2021-11-24,running
emr,2021-11-23,running
emr,2021-11-22,running
emr,2021-11-21,running
emr,2021-11-20,created
lambda,2021-11-25,running
lambda,2021-11-24,running
lambda,2021-11-23,created
lambda,2021-11-22,deleted
lambda,2021-11-21,running
lambda,2021-11-20,created
```

* What does the following do?

```
INSERT INTO SECOND_TABLE (primary_key1, order_number, transaction_number, transaction_time	)
	SELECT COALESCE((SELECT MAX(primary_key1) FROM SECOND_TABLE WHERE order_number>=0), 0) 
			+ RANK() OVER (ORDER BY transaction_time),
		order_number,
		transaction_number,
		transaction_time
	FROM FIRST_TABLE  FST
	WHERE NOT EXISTS
		(SELECT 1 FROM SECOND_TABLE SCD WHERE SCD.primary_key1=FST.primary_key1) 
```

#### Python

* What is the output of the following?

```
def test():
    output = []
    for i in range(10):
        output.append(i)
        if i == 2:
            pass
            output.append(i)
        if i == 3:
            output.append(i)
            continue
        if i == 5:
            break
            output.append(i)
    return output
print(test())
```

* What is the output of the following?

```
a = [1, 2, 3]
b = [4, 5, 6]
c = [7, 8, 9]
d = [10, 11]
x = a.append(b)
y = c.extend(d)

print(a)
print(b)
print(c)
print(d)
print(x)
print(y)
```

---
layout:       post
title:        "Database Normalization"
subtitle:     "Normal Form Types"
date:         2021-06-08 9:00:00
author:       "PC"
header-img:   "img/photo-with-title.png"
header-mask:  0.3
catalog:      true
tags:
    - Database Design
    - Normal Form
    - Reference
---

### Normalization

Normalization of Database Design is created to solve two major issues of the database structure by breaking down large tables into smaller ones.
1. Eliminate Redundant Data
2. Eliminate Anomaly Data, ensuring data quality (especially from CRUD action)

Some other things to keep in mind:
- Normal Form is dependent on its previous form (e.g. 2NF is a dependent of 1NF).
![Normal Form Train](../../../../img/nf_train.PNG)
- Some Databases, especially OLAP may intentionally violate the normal form to help boost their performance, which is called **denormalization**.

### Normal Form Types
1. [First Normal Form (1NF)](#first-normal-form)
2. [Second Normal Form (2NF)](#second-normal-form)
3. [Third Normal Form (3NF)](#third-normal-form)
4. [BCNF (Boyce-Code Normal Form/3.5NF)](#bcnf)

#### First Normal Form

By meeting the following 4 rules, the table will be in the 1NF:
- Only Atomic values are stored. It should not contain merged columns or attributes.
- Columns should be with unique names.
- Every row should be a unique identifier (the best way will be adding a Primary Key).

Let's start with a quick falsity example of NF1. The following example consists of multiple values on the name column and having different domains (`major`) included in the same table.
![Falsety NF1](../../../../img/NF1_falsety.PNG)

By separating the name column into first and last name, it has ensured the data will be able to retrieve or stored atomically, which will fit well for NF1.
![NF1 1 example](../../../../img/NF1_1.PNG)

#### Second Normal Form

As mentioned above, there are dependencies between the higher form of normalization. Therefore, NF2 will be adding on top of the NF1 with new rules:
- Table must be already in NF1.
- Domain-Specific in each table, (e.g. `major` should be separated from personal information).
- All columns are dependent on the primary key column of the table (, in this case, it is `student_id`).

By separating the `major` columns from the `Student` table, it will meet the rules of NF2.
![NF2 1 example](../../../../img/NF2_1.PNG)
![NF2 2 example](../../../../img/NF2_2.PNG)

#### Third Normal Form

In the image above, the `department_head` is depending on the `major`, which is very odd, as it is relating to a non-prime attribute. This is called a **transitive dependency**, which may lead to the issue of data duplication. Therefore, the Third Normal Form will be adding new rules:
- Table must be already in NF2
- No Transitive Dependency
    - , which means should not be having a non-prime attribute depending on another non-prime attribute this is **transitive dependent**.

By separating the `department_head` into its own table `department`, it will meet the rules of NF3.
![NF3 2 example](../../../../img/NF3_3.PNG)

#### BCNF

BCNF is also part of the NF3. As you can see, it is quite weird that why `major` is attached with the `student_id`. When we only want to check for the `major` it will not work very well. That's why we need NF3.5 which also dependent on NF3:
- Table must be already in NF3.
- For a dependency of A -> B, A cannot be a non-prime attribute when B is a prime attribute.

Therefore, in the last image of NF2, having the `major` depending on `student_id` is violating the rule of NF3.5, by adding a new `Major` table, and having another new table to show the relationship of the two tables, which usually are called a **mapping table**.
![NF3 1 example](../../../../img/NF3_1.PNG)
![NF3 2 example](../../../../img/NF3_2.PNG)

Most of the time, the basic Normal Form ends here. Fourth and Fifth Normal Form are not always covered from the textbook, but I think it is good to cover here to help understand the best practice of this art piece. I do think they are widely used, but not said as often as the other 3+BCNF. For more info please see [ Advanced database normalization](/2021/06/10/advanced-normalization/)

### Word List

 * NF n. 數據庫範式
 * Normalization n. 資料庫正規化

### Reference

[GURU99](https://www.guru99.com/database-normalization.html#10)<br />
[Studytonight](https://www.studytonight.com/dbms/fifth-normal-form.php)<br />
[geeksforgeeks](https://www.geeksforgeeks.org/normal-forms-in-dbms/)<br />
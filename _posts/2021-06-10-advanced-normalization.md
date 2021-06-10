---
layout:       post
title:        "Advanced Database Normalization"
subtitle:     "Normal Form Types"
date:         2021-06-10 9:00:00
author:       "PC"
header-img:   "img/photo-with-title.png"
header-mask:  0.3
catalog:      true
tags:
    - Database Design
    - Normal Form
    - Reference
---

### Advanced Normalization

Normalization of Database Design is created to solve two major issues of the database structure by breaking down large tables into smaller ones.
1. Eliminate Redundant Data
2. Eliminate Anomaly Data, ensuring data quality (especially from CRUD action)

Some other things to keep in mind:
- Normal Form is dependent to their previous Form (e.g. 2NF is a dependent of 1NF).
![Normal Form Train](/img/nf_train.PNG)
- Some Database, especially OLAP may intentionally violate the normal form to help boost their performance, which is called **denormalization**.

### Normal Form Types
1. [Fourth Normal Form (4NF)](#fourth-normal-form)
2. [Fifth Normal Form (5NF)](#fifth-normal-form)
3. [Sixth Normal Form (6NF)](#sixth-normal-form)

#### Fourth Normal Form

Let's start with the rule:
- Table must be already in NF3.5
- Table should not have any **mutli-valued dependency**
    - Multi-valued dependency is an issue that faced all the time in a OLTP system, issue usually leads to duplicate of records.

Example:
    /*--TODO--*/

#### Fifth Normal Form

Fifth Normal Form is also called Project Join Normal Form (PJNF), as it is quite complex I recommand watching the video explanation from [studytonight](https://youtu.be/mbj3HSK28Kk)
Rules of NF5 as follow:
- Table must be already in NF4.
- If JOIN Dependency exists, decompose the table and only without loss of data.

#### Sixth Normal Form

6th Normal Form is not standardized, yet however, it is being discussed by database experts for some time. Hopefully, we would have a clear & standardized definition for 6th Normal Form in the near future...

### Word List

 * Mutli-valued dependency n. 
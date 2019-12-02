---
name: "Row Level Security"
author: "Nik"
version: "v1.0.0-initial"
date-authored: "2019-12-02"
theme : "night"
highlightTheme: "darkula"
slideNumber: false
separator: '^\r?\n---\r?\n$'
verticalSeparator: '^\r?\n--\r?\n$'
---

## Row Level Security

<img src="https://media.giphy.com/media/Bc3SkXz1M9mjS/giphy.gif" alt="v2Cat" height="300" loop=""/>

A quick exploration of how to hack

---

## What is it?

- Security against the data itself
- As it's held in the database layer itself, the security can apply at all levels of the application
- Records locked out based on login data

--

<img src="/RowSecurityModel.png" alt="Row Security Model Flow Diagram" width="800" />

---

## Role Based

Role based security assigns a role/user group to each user and the security is modeled against this record. 

This is done by using the TSQL command...

```SQL
CREATE SECURITY POLICY
```

--

### ... Unfortunately ...

<span class="fragment">• This command is only available for SQL Server 2016 & up </span>

<span class="fragment">• This is **obviously** for role based security model _(not what we're looking at)_ </span>

---

## The more hack-y way

<img src="https://media.giphy.com/media/ZHlGzvZb130nm/giphy.gif" alt="v2Cat" height="300" loop="" />


--

## Hierarchies

<span class="fragment">• We store the Staff Hierarchy in the Data Warehouse</span>

<span class="fragment">• We can flag the 'children' of a logged in user</span>

<span class="fragment">• We can filter on activities on the 'child' records</span>

--

<img src="https://media.giphy.com/media/UrEQirmnMPxBwToULv/giphy.gif" alt="Ramsey How it's Done" height="400" loop="" />

--


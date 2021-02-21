---
layout: default
title: Notes - The design of Go from a software engineering perspective
parent: golang
nav_order: 2
last_modified_date: Feb 20 2021 at 07:33 PM
---

The original article: [Go at Google: Language Design in the Service of Software Engineering
](https://talks.golang.org/2012/splash.article).

## 1. Why Google Develop Go Project
Go is designed to address the problem that developing on large software system today is **slow** and **clumsy**, make the dev process more <span style="color:red">**productive**</span> and <span style="color:red">**scalable**</span>.   
Go is more about software engineering. It addressed following difficulties in large-scale software development:
- slow build
- uncontrolled dependencies
- each programmer using a different subset of the language
- poor program understanding (code hard to read, poorly documented, and so on)
- duplication of effort
- cost of updates
- version skew
- difficulty of writing automatic tools
- cross-language builds  

For example: Go uses brace-bounded blocks rather than indentation since indentation is more dangerous in large-scale software system. 

## 2. Understand Go's Dependency
### 2.1 The problem with C/C++ dependency management
==> C/C++ use header file with #ifndef "guards", so each header file can safely #include all its dependencies, even if other header files will also include them.   
==> <span style="color: red">**BAD SCALABILITY** </span>: one header file that is depend by other files might be read multiple times (multiple I/Os) since each one can safely includes its all dependencies. So the larger a software is, the slower the complier time will be.   
==> C++, usually structured with one header file per class, exacerbates the problem by using the same approach at finer granularity.   
==> The engineering effort required to scale up the distributed build system has <span style="color: red"> barely been able to stay ahead</span> of the growth of the software it is constructing.






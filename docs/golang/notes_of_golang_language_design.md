---
layout: default
title: Notes - Language Design of Golang
parent: golang
nav_order: 2
last_modified_date: Feb 20 2021 at 07:33 PM
---

The original article: [Go at Google: Language Design in the Service of Software Engineering
](https://talks.golang.org/2012/splash.article).

### 1. Why Google Develop Go Project
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

### 2. Understand Go's Dependency




---
layout: default
title: Interface
parent: golang
nav_order: 2
last_modified_date: Feb 21 2021 at 09:30 PM
---
## A good article for reference [here](https://medium.com/golangspec/interfaces-in-go-part-i-4ae53a97479c)
## Some takeaways:
### 1. Define A Interface.
- An Interface is basically **a set of methods** required to implement this interface.   
- An Interface can embed other interfaces, either defined in the same package or imported from other packages.  (Using qualified name (packagename.interfacename))   
- Circular embedding of interfaces is disallowed and will be detected while compilation.
- Interface methods must have unique names, no matter where they comes from.   

### 2. Values of An Interface Type  
- Variable of interface type I can hold any value implementing I.   
- Interface itself is a **static** type (Specified when declaration && no change). 
- The assigned value of an interface is a **dynamic** type.   
- Zero value of an interface is nil.  
- Get dynamic type of the value of an interface type: 
	```golang
	fmt.Println(reflect.TypeOf(i).PkgPath(), reflect.TypeOf(i).Name())
	fmt.Println(reflect.TypeOf(i).String())
	```
	or
	```golang
	fmt.Printf("%T\n", i)
	```
	Note: Under the hood it uses reflect package though but this method works even when i is nil.  

### 3. More About Interface Type Value  
Interface type value consists of two components:  
- dynamic type
- dynamic value  
>Interface type value is nil iff **both** dynamic value and dynamic type are nil.

### 4. Empty Interface  
A prominent use of empty interface exists in variadic function fmt.Println.   
```golang 
func Println(a ...interface{}) (n int, err error)
```
```golang
package main

import (
	"fmt"
)

func main() {
	const name, age = "Kim", 22
	fmt.Println(name, "is", age, "years old.")

	// It is conventional not to worry about any
	// error returned by Println.

}
```

### 5. Finally  
1. Every type which implements <span style="color:red">**all**</span> interface’s method <span style="color:red">**automatically**</span> satisfies such interface.  ==> This is more flexible, since we can create interface that was implemented by exist types without change these types.    
2. A type satisfied an interface can have other methods which are not required by the interface. And interface type value gives access **ONLY** to methods of its interface type.  

---
layout: default
title: Interface
parent: golang
nav_order: 2
---
A good article for reference [here](https://medium.com/golangspec/interfaces-in-go-part-i-4ae53a97479c)
### 1. 接口的定义和实现
接口由<span style="color:red">**使用者**</span>定义。
例如：
```golang
package main

import (
	"fmt"
	"go-app/retriever/mock"
)

type Retriever interface {
	Get(url string) string
}

// 使用者定义Retriever
func download(r Retriver) string {
	return r.Get("httpL://www.google.com")
}
```

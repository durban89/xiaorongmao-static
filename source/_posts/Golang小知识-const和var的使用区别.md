---
date: '2025-08-05 09:48:06'
title: 'Golang小知识 - const和var的使用区别'
image: 'https://res.cloudinary.com/dy5dvcuc1/image/upload/v1595385476/xiaorongmao/golang.jpg'
categories:
    - "技术"

tags:
    - "Golang"

---

Golang小知识 - const和var的使用区别

第一个举例

const和var声明的变量值为整型

```go
package main

import "fmt"

func main() {
	const (
		a = 1
		b = 2
		c = 3
	)

	fmt.Println(a+b == c)

	var (
		m = 1
		n = 2
		o = 3
	)

	fmt.Println(m+n == o)
}
```

运行结果如下

```bash
$ go build -o ./build/app
$ ./build/app
true
true
```

第二个举例

const和var声明的变量值为浮点型

```go
package main

import "fmt"

func main() {
	const (
		a = 0.1
		b = 0.2
		c = 0.3
	)

	fmt.Println(a+b == c)

	var (
		m = 0.1
		n = 0.2
		o = 0.3
	)

	fmt.Println(m+n == o)
}
```

运行结果如下

```bash
$ go build -o ./build/app
$ ./build/app
true
false
```

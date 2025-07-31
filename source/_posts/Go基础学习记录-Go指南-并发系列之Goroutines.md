---
date: '2025-07-31 10:26:39'
title: 'Go基础学习记录 - Go指南 - 并发系列之Goroutines'
image: 'https://res.cloudinary.com/dy5dvcuc1/image/upload/v1595385476/xiaorongmao/golang.jpg'
categories:
    - "技术"

tags:
    - "Golang"

---

### **环境**

> go version go1.10.1 darwin/amd64

### **Goroutines**

一个 ```goroutine``` 由 Go 运行时管理的轻量级线程.

```go
go f(x, y, z)
```

启动一个新的goroutine并运行

```go
f(x, y, z)
```

f，x，y和z的求值发生在当前的goroutine中，f的执行发生在新的goroutine中。

```go
package main

import (
    "fmt"
    "time"
)

func say(s string) {
    for i := 0; i < 5; i++ {
        time.Sleep(100 * time.Millisecond)
        fmt.Println(s)
    }
}

func main() {
    go say("world")
    say("hello")
}
```

运行结果如下

```bash
world
hello
world
hello
world
hello
world
hello
world
hello
```

Goroutines在相同的地址空间中运行，因此在访问共享的内存时必须进行同步。sync 包提供了这种能力，不过在 Go 中并不经常用到，因为还有其它的办法。

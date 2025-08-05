---
date: '2025-08-05 09:48:52'
title: 'golang 字符串替换 使用strings.replacer 替换为 strings.replace '
image: 'https://res.cloudinary.com/dy5dvcuc1/image/upload/v1595385476/xiaorongmao/golang.jpg'
categories:
    - "技术"

tags:
    - "Golang"

---

golang 字符串替换 使用strings.replacer 替换为 strings.replace

strings.replace的使用方式

```go
package main

import (
	"fmt"
	"strings"
)

func main() {
	str := "aaa bbb ddd fff aaa"
	keyword := "aaa"
	str = strings.ReplaceAll(str, keyword, "**")

	fmt.Println(str)
}
```

strings.replacer的使用方式

```go
package main

import (
	"fmt"
	"strings"
)

func main() {
	str := "aaa bbb ddd fff aaa"
	keyword := "aaa"
	replacer := strings.NewReplacer(keyword, "**")
	str = replacer.Replace(str)

	fmt.Println(str)
}
```

为什么要替换

“we see that **Replace**creates **more** runtime **memory allocations** than **New Replacer**.”

参考：

---

https://medium.com/@vikram.ingawale91/golang-strings-replace-vs-strings-replacer-a7b2d2b71593

https://levelup.gitconnected.com/multi-string-replace-in-golang-with-replacer-148d4173f439

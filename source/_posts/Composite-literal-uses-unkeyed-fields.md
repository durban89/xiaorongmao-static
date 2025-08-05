---
date: '2025-08-05 09:48:24'
title: 'Composite literal uses unkeyed fields'
image: 'https://res.cloudinary.com/dy5dvcuc1/image/upload/v1754360763/2dbc8a6b73284e49b99f10ca82e90f58_rma9xf.png'
categories:
    - "技术"

tags:
    - "Golang"
    - "Mongodb"

---

错误提示：Composite literal uses unkeyed fields

---

最近遇到这个错误提示

原因是用了Mongodb的一个语法

```bash
mongodb.D{{"key", 1}}
```

于是在用golint做语法检查的时候，给了一个警告

```bash
go.mongodb.org/mongo-driver/bson/primitive.E composite literal uses unkeyed fieldsgo-vet
```

其实是用法有问题，但是代码也能正常运行

但是看着警告也是很不舒服的

修改如下

```bash
mongodb.D{primitive.E{Key: "key", Value: 1}}
```

警告的错误提示就没有了

具体解释可以参考这里[composite literal uses unkeyed fields](https://stackoverflow.com/questions/54548441/composite-literal-uses-unkeyed-fields)

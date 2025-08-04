---
date: '2025-08-04 18:07:46'
title: 'Golang网站开发之模版的if操作'
image: 'https://res.cloudinary.com/dy5dvcuc1/image/upload/v1595385476/xiaorongmao/golang.jpg'
categories:
    - "技术"

tags:
    - "Golang"

---

在网页开发中避免不了会使用到模板，那么在使用模板的时候肯定会遇到条件的判断逻辑

在php的laravel中，在模板中，if条件判断使用如下

```go
@if(条件)
// ... 需要实现的代码逻辑
@else if(条件)
// ... 需要实现的代码逻辑
@else
// ... 需要实现的代码逻辑
@endif
```

在python的flask中，在模板中，if条件判断使用如下

```go
{@ if(条件) @}
# ... 需要实现的代码逻辑
{@ elif (条件)@}
# ... 需要实现的代码逻辑
{@ else @}
# ... 需要实现的代码逻辑
{@ endif @}
```

在golang中，if条件判断使用如下

```go
{{if .C}}
// ... 需要实现的代码逻辑
{{else if}}
// ... 需要实现的代码逻辑
{{else}}
// ... 需要实现的代码逻辑
{{end}}
```

比如我这里在创建的时候问了现实msg错误信息，简单的使用如下

```html
{{ if .Msg }}
<div class="row">
  <div class="col-md-12">
    <div class="alert alert-danger">
    {{ .Msg }}
    </div>
  </div>
</div>
{{ end }}
```

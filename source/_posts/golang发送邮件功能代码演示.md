---
date: '2025-08-05 09:48:55'
title: 'golang发送邮件功能代码演示'
image: 'https://res.cloudinary.com/dy5dvcuc1/image/upload/v1595385476/xiaorongmao/golang.jpg'
categories:
    - "技术"

tags:
    - "Golang"

---

```go
import (
	"xxxx/config"
	"github.com/jordan-wright/email"
	"log"
	"net/smtp"
)

// Send smtp send
func Send(senderTitle, mailTo, mailToSubj string, text, html []byte) error {

	emailHost := config.EmailSmtpHost
	emailPort := config.EmailSmtpPort
	emailUser := config.EmailSmtpUsername
	emailAuthPassword := config.EmailSmtpPassword

	//fmt.Printf("emailHost = %s emailPort = %s emailUser = %s emailAuthPassword = %s", emailHost, emailPort, emailUser, emailAuthPassword)

	e := email.NewEmail()
	e.From = senderTitle + " <" + emailUser + ">"
	e.To = []string{mailTo}
	e.Bcc = []string{mailTo}
	e.Cc = []string{mailTo}
	e.Subject = mailToSubj
	e.Text = text //[]byte("Text Body is, of course, supported!")
	e.HTML = html // []byte("<h1>Fancy HTML is supported, too!</h1>")
	err := e.Send(emailHost+":"+emailPort, smtp.PlainAuth("", emailUser, emailAuthPassword, emailHost))

	if err != nil {
		log.Panic(err)

		return err
	}

	return nil
}
```

使用的是github.com/jordan-wright/email

这个比较好用，效果见效快

A SMTP Server Package [![](https://img.shields.io/badge/godoc-reference-5272B4.svg?style=flat-square)](https://godoc.org/github.com/alash3al/go-smtpsrv)
=============================
a simple smtp server library for writing email servers like a boss.

Quick Start
===========
> `go get github.com/alash3al/go-smtpsrv`

```go
package main

import (
	"fmt"

	"github.com/alash3al/go-smtpsrv/v3"
)

func main() {
	handler := func(c smtpsrv.Context) error {
		// ...
		return nil
	}

	cfg := smtpsrv.ServerConfig{
		BannerDomain:  "mail.my.server",
		ListenAddr: ":25025",
		MaxMessageBytes: 5 * 1024,
		Handler:     handler,
	}

	fmt.Println(smtpsrv.ListenAndServe(&cfg))
}

```

Thanks
=======
- [alash3al/go-smtpsrv](https://github.com/alash3al/go-smtpsrv)
- [parsemail](https://github.com/DusanKasan/parsemail)
- [go-smtp](https://github.com/emersion/go-smtp)

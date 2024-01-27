# 修改
[`quotedprintable: dont returns invalid unescaped byte 0x in body error`](https://github.com/onsole/go-message/commit/6e4cd92753102f04bc94b1cc5dbb79eac4123dff)  
原生的 `mime/quotedprintable` 会返回这个错误，但是实际场景使用下来，是没有太大必要的，反而容易引起无法解析的问题。  
所以将原生的 `mime/quotedprintable` 代码复制到本仓库，修改后并且改变 `encoding.go` 的对应 `import` 即可。  
目前 `mime/quotedprintable` 对应的是 `go1.17.6`

# go-message

[![Go Reference](https://pkg.go.dev/badge/github.com/emersion/go-message.svg)](https://pkg.go.dev/github.com/emersion/go-message)
[![builds.sr.ht status](https://builds.sr.ht/~emersion/go-message/commits/master.svg)](https://builds.sr.ht/~emersion/go-message/commits/master?)

A Go library for the Internet Message Format. It implements:

* [RFC 5322]: Internet Message Format
* [RFC 2045], [RFC 2046] and [RFC 2047]: Multipurpose Internet Mail Extensions
* [RFC 2183]: Content-Disposition Header Field

## Features

* Streaming API
* Automatic encoding and charset handling (to decode all charsets, add
  `import _ "github.com/emersion/go-message/charset"` to your application)
* A [`mail`](https://godocs.io/github.com/emersion/go-message/mail) subpackage
  to read and write mail messages
* DKIM-friendly
* A [`textproto`](https://godocs.io/github.com/emersion/go-message/textproto)
  subpackage that just implements the wire format

## License

MIT

[RFC 5322]: https://tools.ietf.org/html/rfc5322
[RFC 2045]: https://tools.ietf.org/html/rfc2045
[RFC 2046]: https://tools.ietf.org/html/rfc2046
[RFC 2047]: https://tools.ietf.org/html/rfc2047
[RFC 2183]: https://tools.ietf.org/html/rfc2183

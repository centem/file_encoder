## A Python File Encoder / Decoder

### String Encoders and Decoders

Python strings have encode and decode methods. You pass a "codec" to the encode or decode method, and that code will be applied to the string. In most cases, the decode() method is used to undo the encoding performed by the encode() method. ROT-13 is one exception to this because, like XOR encryption, ROT-13 reverses itself when encoded twice.

Please note that in Python 3 the string encode and decode methods have been repurposed to create a Python 2.7 compatible string. 

```markdown
>>> "ENCODE ME".encode("ROT-13")
>>> 'RAPBQR ZR'

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

### Suportedd Encoders
Please note that in Python 3 the string encode and decode methods have been repurposed to create a Python 2.7 compatible string.
So, "ENCODE ME".encode("base64" and other similar codecs will not work in Python 3. In Python 3 the encoding functionality has been moved to the codecs module. The codecs module is also available in Python 2.7 so you can build Python 3 compatible syntax using that module today.
In versions earlier than 2.7 the following encoders are supported.
- Base64
- bz2
- hex
- rot13
- uu
- zip
- string_escape

```markdown
>>> import codecs
>>> codecs.encode("encode me", "rot13")
'rapbqr zr'
>>> codecs.encode(b"encode me", "base64")
b'ZW5jb2R1IG11\n'
```
In versions earlier than 2.7 the following encoders are supported.
Base64
bz2
hex
rot13
uu
zip
string_escape
### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

## A Python File Encoder/Decoder

### String Encoders and Decoders

Python strings have encode and decode methods. You pass a "codec" to the encode or decode method, and that code will be applied to the string. In most cases, the decode() method is used to undo the encoding performed by the encode() method. ROT-13 is one exception to this because, like XOR encryption, ROT-13 reverses itself when encoded twice.

Please note that in Python 3 the string encode and decode methods have been repurposed to create a Python 2.7 compatible string. 

```markdown
>>> "ENCODE ME".encode("ROT-13")
>>> 'RAPBQR ZR'
```

### Supported Encoders

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

### Using Codecs to Encode/Decode

The codecs module can be used to encode data in a way that is forward compatible with Python 3. The encode and decode functions are used to change the representation or the encoding of data from one format to another. Here are some examples of putting these codecs to use with the encode and decode methods. 

```markdown
>>> import codecs
>>> codecs.encode("Hello World", "rot13")
'Uryyb Jbeyq'
>>> codecs.encode(b"Hello World", "HEX")
'48656c6c6f20576f726c64'
>>> codecs.encode("Hello World", "utf-16le")
'H\x00e\x00l\x00l\x00o\x00 \x00W\x00o\x00r\x00l\x00d\x00'
>>> codecs.encode("Hello World", "utf-16be")
'\x00H\x00e\x00l\x00l\x00o\x00 \x00W\x00o\x00r\x00l\x00d'
>>> codecs.encode(b"Hello World", "zip")
'x\x9c\xf3H\xcd\xc9\xc9W\x08\xcf/\xcaI\x01\x00\x18\x0b\x04\x1d'
>>> codecs.encode(b"Hello World", "base64")
'SGVsbG8gV29ybGQ=\n'
>>> codecs.encode("Hello World.encode("rot13"), "rot13")
'Hello World'
>>>
```
Notice that some of these require Python 2 compatible byte string rather than Python 3 compatible Unicode string. Placing the little b outside of the quotes accomplishes this. You can find a complete list of available encoders here: https://docs.python.org/release/2.5.2/lib/standard-encodings.html

### Encoding an Entire File
Now we are ready to encode a file with what we just learned. Here is the algorithm we will employ. The test file (testfile.txt) contains the following data which will be based64 encoded and written to encoded_file.txt. 
```markdown
8.8.8.8
johndoe@mail.com
127.0.0.1
johndoe@gmail.com
http://www.example.com
```
Import codecs
```markdown
import codecs
```
Create a empty list to hold the encoded strings

```markdown
encoded_data = []
```
Open a file that contains the strings we want to encode. Loop through the file line by line and encode the line, add the line to the encoded_data list.

```markdown
with open('testfile.txt','r') as fh:
        for line in fh:
                line = line.rstrip()
                encoded_string = codecs.encode(line,"base64")
                encoded_data.append(encoded_string)
```
Open a new file and iterate over the encoded_data list and write each item to the file

```markdown
with open('encoded_file.txt','a+') as fh:
    for item in encoded_data:
        fh.write(item+'\n')
```
And...voila! The new encoded_file.txt should have the following data.
```markdown
OC44LjguOA==
am9obmRvZUBtYWlsLmNvbQ==
MTI3LjAuMC4x
am9obmRvZUBnbWFpbC5jb20=
aHR0cDovL3d3dy5leGFtcGxlLmNvbQ==
```

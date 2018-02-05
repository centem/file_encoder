## A Python File Encoder / Decoder

You can use the [editor on GitHub](https://github.com/centem/file_encoder/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

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

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/centem/file_encoder/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

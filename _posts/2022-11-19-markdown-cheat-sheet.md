---
title: Markdown Cheat Sheet
author: andrew
date: 2022-11-19 03:42:00 -0500
categories: [Documentation, Markdown]
tags: [markdown, code, markup, syntax, language]
---

# Markdown Cheat Sheet

This Markdown cheat sheet provides a quick overview of all the Markdown syntax elements. It can’t cover every edge case, so if you need more information about any of these elements, refer to the reference guides for [basic syntax](https://www.markdownguide.org/basic-syntax) and [extended syntax](https://www.markdownguide.org/extended-syntax).

---
## Basic Syntax

###### These are the elements outlined in John Gruber’s original design document. All Markdown applications support these elements.

---
### Headings 

# Heading 1
`# Heading 1`

## Heading 2
`## Heading 2`

### Heading 3
`### Heading 3`

#### Heading 4
`#### Heading 4`

##### Heading 5
`##### Heading 5`

###### Heading 6
`###### Heading 6`

---
### Bold
**some bold text**
`**some bold text**`

---
### Italics
*other italicized text*
`*other italicized text*`

---
### Blockquotes
> this is a blockquote
`> this is a blockquote`

---
### Ordered Lists
1. First ordered item
2. Second ordered item
3. Third ordered item

```
1. First ordered item
2. Second ordered item
3. Third ordered item
```

---
### Unordered Lists
- First unordered item
- Second unordered item
- Third unordered item

```
- First unordered item
- Second unordered item
- Third unordered item
```

---
### Code
#### Example 1 (Single Line):
`code`
```
`code`
```
#### Example 2 (Fenced Code Block):
``` 
multiple
lines of
code
```
Use three ticks (no spaces) on the lines before and after multiple lines of code
````md
```
multiple
lines of
code
```
````
#### Example 3 (Syntax Highlighting):
```javascript
// the hello world program
console.log('Hello World');
```
You can add the name of the language at the end of the first set of three ticks (no spaces) for syntax highlighting
````md
``` javascript
// the hello world program
console.log('Hello World');
```
````
**Note that not all markdown applications support examples 2 and 3*

---
### Horizontal Rule
---
Use three dashes or three underscores on their own line
```
---
___
```

---
### Link
[Markdown Guide Website](https://www.markdownguide.org)
`[Markdown Guide Website](https://www.markdownguide.org)`

---
### Image
![alt text](https://www.markdownguide.org/assets/images/tux.png)
`![alt text](https://www.markdownguide.org/assets/images/tux.png)`

---
## Extended Syntax

###### These elements extend the basic syntax by adding additional features. Not all Markdown applications support these elements.

---
### Table
| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |
```
| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |
```

---
### Footnote
Here's a sentence with a footnote. [^1]
[^1]: This is the footnote.
```
Here's a sentence with a footnote. [^1]
[^1]: This is the footnote.
```

---
### Heading ID
##### My Great Heading {#custom-id}
`##### My Great Heading {#custom-id}`

---
### Definition List
term
: definition
```
term
: definition
```

---
### Strikethrough

~~The world is flat.~~
`~~The world is flat.~~`

---
### Task List
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```

---
### Emoji
That is so funny! :joy:
`That is so funny! :joy:`

(See also [Copying and Pasting Emoji](https://www.markdownguide.org/extended-syntax/#copying-and-pasting-emoji))


---
### Highlight
I need to highlight these ==very important words==.
`I need to highlight these ==very important words==.`

---
### Subscript
H~2~O
`H~2~O`

---
### Superscript
X^2^
`X^2^`

---
###### *This guide was adapted from the Markdown Cheat Sheet found at the [Markdown Guide website](https://www.markdownguide.org/cheat-sheet/).*
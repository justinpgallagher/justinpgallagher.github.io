# mariaines.github.io

- [How to update site data](#how-to-update-site-data)
  - [Research](#research)
  - [Teaching](#teaching)

## How to update site data

Most of the site content is defined in markdown files (`*.md`). [Markdown](https://www.markdownguide.org/getting-started)
is a lightweight markup language with pretty simple syntax, that then gets generated into html.

It looks like this:
```
# This is a title

## This is a subtitle

Here is a paragraph. **Here is some bold text.** _Underlined text._

[Here is a link](http://www.google.com)

- Here is a list
  - With a nested list
  - We can also have ordered lists
    1. One
    2. Two
    3. Three
```
which gets generated to display this:

---
#### This is a title

##### This is a subtitle

Here is a paragraph. **Here is some bold text.** _Underlined text._

[Here is a link](www.google.com)

- Here is a list
  - With a nested list
  - We can also have ordered lists
    1. One
    2. Two
    3. Three
---


### Research

The research page is just a single markdown file: [research.md](https://github.com/mariaines/mariaines.github.io/blob/master/_includes/research.md).

To update it, go to the file in github, click the pencil icon in the top-right to edit, and type in the editor.

You can preview your changes by toggling the "Preview changes" tab.

### Teaching

The teaching page is generated from a collection of markdown files defined under [/_teaching_current](https://github.com/mariaines/mariaines.github.io/blob/master/_teaching_current).

These markdown files include a special section at the top that defines some key-value pairs, which are used by the [teaching.html](https://github.com/mariaines/mariaines.github.io/blob/master/teaching.html) page. They look like this:
```
---
name: "ECON 326: Econometrics"
link: http://weatherhead.case.edu/academics/courses/ECON326
syllabus: pdfs/ECON326-syllabus-spring-2017.pdf
---
Econometrics is...
```

To add a new course, go to the `_teaching` directory and click "Create new file" to create a new file with the same structure. Make sure to give it a name that ends in `.md`.

To remove a course, you can just delete the file or move it to a different directory, like `/_archived_teaching`. If you want, we could add a page that includes archived courses.


### Contact info



## Troubleshooting

https://help.github.com/articles/troubleshooting-github-pages-builds/

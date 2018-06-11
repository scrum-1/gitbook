# 協同著作規劃

將各組組長設為 scrum-1/gitbook 倉儲的協同者, 各組組員 Fork scrum-1/gitbook 後更改內容後, 以 pull request 由組長合併至 scrum-1/gitbook, 各組組長則可以直接在 web 上修改 scrum-1/gitbook 的內容

# Chapters and Subchapters

GitBook uses a `SUMMARY.md` file to define the structure of chapters and subchapters of the book. The `SUMMARY.md` file is  used to generate the book's table of contents.

The `SUMMARY.md`'s format is simply a list of links, the name of the link is used as the chapter's name, and the target is a path to that chapter's file.

Subchapters are defined simply by adding a nested list to a parent chapter.

### Simple example

```
# Summary

* [Chapter 1](chapter1.md)
* [Chapter 2](chapter2.md)
* [Chapter 3](chapter3.md)
```

### Example with subchapters split into *parts*

```
# Summary

* [Part I](part1/README.md)
    * [Writing is nice](part1/writing.md)
    * [GitBook is nice](part1/gitbook.md)
* [Part II](part2/README.md)
    * [We love feedback](part2/feedback_please.md)
    * [Better tools for authors](part2/better_tools.md)
```

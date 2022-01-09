---
banner: Library Banner 1.png
banner_x: 0.3941
banner_y: 0.5
---
# Library
This is the sample vault that I use in the [How to Create a Bookshelf tutorial](https://thebuccaneersbounty.wordpress.com/2021/08/21/tutorial-how-to-create-a-bookshelf-in-obsidian/). This vault has the Dataview, QuickAdd, Banners plugins installed.

This is the Library note, where you can find all the book notes displayed using the Dataview plugin. Press **Ctrl+E** (or **Command+E** on a Mac) to switch to Edit mode to see the Dataview codes.

## All Books
---
This code displays all books from the Books folder.
```dataview
table Author, ("![coverimg|95](" + Cover +")") as Cover
from "Books"
sort file.name asc
```

### Books About Fitness
This code displays all books that contain the Type "Fitness" on the YAML frontmatter.
```dataview
table Author, ("![coverimg|95](" + Cover +")") as Cover
from "Books"
where contains(Type, "Fitness")
sort file.name asc
```

## Book Tracker
---
This code displays and groups all books based on their Status.
```dataview
table rows.file.link as Book
from "Books"
group by Status
sort Status
```

## List of Read Books
---
### 2022
This code displays all books with the "Read" status and with the year 2022 on the Date-Read field.

```dataview
table rows.file.link as Book
from "Books"
where Status = "Read" and Date-Read >= date(2022-01-01) AND Date-Read <=date(2022-12-31)
group by Date-Read
sort Date-Read asc
```

### 2021
This code displays all books with the "Read" status and with the year 2021 on the Date-Read field.

```dataview
table rows.file.link as Book
from "Books"
where Status = "Read" and Date-Read >= date(2021-01-01) AND Date-Read <=date(2021-12-31)
group by Date-Read
sort Date-Read asc
```
---
layout: post
title: Getting everything together in the theme
date: 2022-04-07 17:39:00
description: The process for getting the site running
---

I wanted to do some modifications to the theme:

#### Add my CV:
- [X] After trying and failing with [pre-made options](https://github.com/elipapa/markdown-cv), I simply created the file in markdown. It has less formatting but it looks alright and I could add the liquid tag to pull my publications from the main .bib file at the bottom. Also figured out that md doesn't need the closing break tag but `<br>` can be stacked.

----
#### Rename the drop down:
 - [X] Just changed the title of the dropdown.md in the front matter. When adding the permalinks to each page, use underscores and make sure the permalinks for each page match the permalink in the front matter of the corresponding .md file.

----
#### Set the pages and the order of the nav bar:
- [X] The default process is to add `nav:true` in the front matter for each page you want in the nav. I didn't figure this out until I looked at [someone else's repo](https://github.com/rohandebsarkar/rohandebsarkar.github.io). I then added an additional tag in the front matter for `nav_index:` followed by a number which gave the order from left to right. So when using `nav: true`, add  `nav_index: 1` to get the page to be the first and increase the number by 1 for the rest. I also had to add this to the header.html file so that it wouldn't do the default behavior of doing it by alphabetical order. This is in line 48 in the header.html file where `title` is changed to `nav_index`:
`assign sorted_pages = site.pages | sort: "title"`
`assign sorted_pages = site.pages | sort: "nav_index"` 

----
#### Add additional .bib files that would show up depending on the page I wanted them in:
- [X] Export the bibliography from Zotero in bibtex format. Name it something meaningful and then drop it in the "bibliography" folder in the repo. Then, when editing a page in which you want that bib in particular. Use the block that is in publications.md but replace what goes after the -f option in the tag with `bibliography -f ` with the name of the bib you created. For example, `bibliography -f new_bib`. I haven't been able to figure out how to make the items show up without adding the years: [] in the front matter for each year of each item in the bibliography. If you don't add the years in the front matter they don't show up. If you add a list of years separated by space and comma, then all of those years show up as sections in the page with blank rows for years that don't have a publication. <br>

----
### To do:
<br>
- [] <b> Add publications by using categories or tags so I can use the tags from Zotero to pull a selection of items without having to make multiple .bib files. </b>
<br> <br>
- [] <b> Link to particular bibs in separate pages in the drop down (only one partially done) <b>

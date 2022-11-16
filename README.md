# Quarto-links

### Bug description

I see some unexpected behavior when it comes to cross-referencing and linking to chapters and sections in book parts.

- When I have a cross-reference to a chapter / level 1 header in a book part, it does not work for html or pdf.
- When I have a level 2 header in a book part, it does not appear to work at all for pdf output, but a cross-reference to a level 2 header works for html output.
- When I have a hyperlink to a chapter / level 1 header in a book part, the link appears in the pdf output but it does not link anywhere. In html it works fine. 
- When I have a hyperlink to a level 2 header in a book part, it works in html and pdf.

part_x.qmd:
````
# Part X {#sec-part-x}

## section x.1 {#sec-part-x-section-1}
```` 

chapter_y.qmd:
```` 
# Chapter y

Cross-ref to a level 1 header in a part: @sec-part-x

Cross-ref to a level 2 header in a part: @sec-part-x-section-1

Hyperlink to a level 1 header in a part: [part x](part_x.qmd) (The link appears in pdf, but does not work. in html it works)

Hyperlink to a level 2 header in a part: [part x section x.1](part_x.qmd#sec-part-x-section-1)
```` 

html output for chapter y:
![image](https://user-images.githubusercontent.com/30228864/191918595-ef8d9ab3-e877-4d93-96d2-e0cbffd7255c.png)

pdf output for chapter y:
![image](https://user-images.githubusercontent.com/30228864/191918464-c8ab1c97-a2e8-41de-bf74-0a0526cabdaf.png)

quarto_1.2
Rstudio daily: 2022.11.0 Build 202 (also used build 83)
R version 4.0.5 (2021-03-31)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 10 x64 (build 19044)

https://github.com/quarto-dev/quarto-cli/issues/2571

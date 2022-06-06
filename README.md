## Template Tsumego eBook

A lab for learning how to write a Go, mainly tsumegos, EPUB ebook.

EPUBs are basically HTML files. For instance, if you open any of [GoBooks](https://gobooks.com/) books with a text editor, besides some many unicode errors, you will note that it is composed of 90% HTML and 10% embedded ~~Chinese~~ JavaScript for the diagrams.

Useful resources for studying EPUBs:

- [*EPUB 3 Best Practices*, by Matt Garrish and Markus Gylling](https://www.goodreads.com/book/show/13593753-epub-3-best-practices) &mdash; Anders Kierulf, author of the SGF standard, GoBooks, and SmartGo, recommends it
- [*What is EPUB 3?*, by Matt Garrish](https://www.goodreads.com/book/show/18881975-what-is-epub-3)
- [*Zen of eBook Formatting: A Step-by-step Guide To Format eBooks for Kindle and EPUB*, by Guido Henkel](https://www.goodreads.com/book/show/22381850-zen-of-ebook-formatting)
- [*Epub Straight to the Point: Creating eBooks for the Apple iPad and Other Ereaders*, by Elizabeth Castro](https://www.goodreads.com/book/show/8477489-epub-straight-to-the-point)
- [A Kiseido book I translated into Portuguese using LaTeX and GoWrite2](https://github.com/FanaroEngineering/traducao_como_jogar_go)

## Pandoc

So far, the most practical way of creating an EPUB book seems to be [Pandoc](https://pandoc.org/). Adobe InDesign &mdash; or Word, or Google Docs? &mdash; is also able to do it.

Here are some useful resources:

- [Pandoc EPUB](https://pandoc.org/epub.html)
- [Scott Chacon's *Pro Git* book](https://git-scm.com/book/en/v2) was written using Pandoc, if you wish to know how far it can go, or have a reference example.

The essential workflow of developing an EPUB (or PDF) tsumego book in this manner is:

1. Create the problem inside GoWrite, with likely at least 3 diagrams, problem, solution, mistake.
1. Export the diagrams to vector images.
1. Mention the diagrams inside the markdown file.
1. Add the necessary text to make it more understandable.

### Compiling to EPUB

```bash
pandoc <file.md> -o <file.epub>
```

You can also add custom CSS to it.

### Compiling to PDF

Note that using HTML inside Markdown doesn't seem to work when compiling to PDF with Pandoc, unlike EPUB.

```bash
pandoc <file.md> -o <file.pdf>
```

## GoWrite

For Go diagrams, I highly recommend [GoWrite2](http://gowrite.net/GOWrite2_download.html), it won't be as slick as [GoBooks](https://gobooks.com/) interactive diagrams, but it's enough.

GoWrite2 can be a bit tricky to use, depending on what you want. Here are some tips and best practices:

- In general, do use vector images for diagrams, this way there won't be any pixelation on them. The main two vector formats in GoWrite2 are:
    - SVG
    - EPS
- When showing only part of the board in a diagram, crop it in the editing tab, not on the board, otherwise there will be a bunch of empty space in the resulting image.
- SVG is basically text, so you can inspect it and change it through an editor. If you dislike anything about GoWrite's results, do change it.
    - For example, I think it would look better to have black thicker lines around the White stones. So I simply would change White stones to have `.35` thickness: `stroke="black" stroke-width="0.35px"`.
- If you want to open or convert the diagrams other formats, I recommend either using [GIMP](https://www.gimp.org/) or [Inkscape](https://inkscape.org/), which are both free.

## EPUB Readers

Most EPUB readers are incredibly unpleasant or ugly. The only ones I've found so far which are good enough:

- [Thorium](https://github.com/edrlab/thorium-reader/releases)
- [Lithium](https://play.google.com/store/apps/details?id=com.faultexception.reader&hl=en&gl=US)
- [iBooks](https://www.apple.com/apple-books/)

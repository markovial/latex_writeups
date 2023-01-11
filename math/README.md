# Latex
---

This is basically a repository of my base latex structure for a new document.

It contains all of the preamble items , packages and includes that I usually
use in my writeups, so I can just clone and get started fast and easy.

I use vim + pdflatex on Linux to edit my docs with latexlivepreview to do live
previews when editing.

Oh and a huge majority of the typing is actually done by ultisnips. So check
out my dotfiles folder :  dotfiles/.config/nvim/UltiSnips/tex.snippets for the
ultisnips snippets that I wrote and use.

## Required packages :

```
pacman -S texlive-most
pacman -S texlive-lang
```

## File Structure

The file structure is thought out as follows :

 * 0_includes : Preamble file(s). I usually symlink to this file , so that All
 the preamble edits only need to happen in 1 file.

 * 1_bibliography : bib file(s)

 * 2_images : contains all images / graphs /tikz exported diagrams that will be
 used in the compilation of the doc.

 * 3_content : This is where all the main content .tex files are supposed to
 live. I usually divided them up by section / chapter , i.e., only 1 section
 per .tex file , and then they are all combined into one file by including them
 in the main document.tex file which lives in the root folder. Makes the entire
 document structure granular , and more importantly you usually only work on 1
 section at time. So when latexlivepreview renders the doc , I am not
 interested in scrolling through all the pages I already know are done. I just
 want to see current working page(s). This becomes easier if I can just comment
 out the individual lines that include other sections.

 * 4_research : This is where other papers , images , docs , etc ... live.
 Basically everything that I am using to help understand and write about
 whatever I am writing about.


## Creating a new latex doc

1. Copy the git folder.
1. Run the symlink command for the preamble.
1. Clear out boilerplate / tutorial content
	1. Delete everything inside the 3_content folder.
	1. Delete / Rename all the input 3_content lines in document.tex
1. Run make
1. Run make again
1. ... ?
1. Profit

## Symlink command

I do this for some projects so that I only have to edit one preamble file. And
all the others just inherit the changes automagically. Sometimes you want to
adjust the inter-column width and things like that so for those I don't symlink
and just go a project by project basis.

This is obviously an example , you'll have to change the line to point it to
your own git and latex folders :

```
ln -s /$HOME/Git/latex/0_includes/0_preamble.tex /$HOME/Documents/latex/1_Computer_Science/0_Machine_Learning/0_includes/0_preamble.tex
```

# LaTeX Makefile v0.33 -- LaTeX only
# original : https://scaron.info/blog/makefiles-for-latex.html

DOCUMENT=document.tex  # set the path to your TeX file here
#SHELL=/bin/bash   # for the while loop below


all:
	pdflatex $(DOCUMENT)
	bibtex $(DOCUMENT:.tex=)            # bibliography
	pdflatex $(DOCUMENT)
	pdflatex $(DOCUMENT)

clean:
	rm *.aux
	rm *.bbl
	rm *.blg
	rm *.lof
	rm *.log
	rm *.lot
	rm *.out
	rm *.pdf
	rm *.toc


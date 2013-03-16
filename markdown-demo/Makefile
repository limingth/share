SRC=demo.md
PREFIX=$(patsubst %.md,%,$(SRC))

all:
	make html
	make doc
	make pdf
	make ppt
	-rm *.aux *.nav *.snm *.vrb *.log *.out *.toc
	-rm demo2*

html:
	pandoc $(SRC) --ascii -f markdown -t html -o $(PREFIX).html 

doc:
	pandoc $(SRC) -o $(PREFIX).doc
	unoconv -f pdf $(PREFIX).doc 

pdf:
	pandoc $(SRC) -o $(PREFIX)2doc.tex
	xelatex demo.doc.tex
# must run xelatex twice to make tableofcontents
	xelatex demo.doc.tex
#	evince demo.doc.pdf

ppt:
	pandoc -t beamer --slide-level 2 $(SRC) -o $(PREFIX)2ppt.tex
	xelatex demo.ppt.tex
#	evince demo.ppt.pdf

clean:
	-rm *.html *.doc *.pdf 
	-rm *.aux *.nav *.snm *.vrb *.log *.out *.toc
	-rm $(PREFIX).tex
	-rm $(PREFIX)2*.*

open:
	gnome-open $(PREFIX).html &
	gnome-open $(PREFIX).doc &
	gnome-open $(PREFIX).pdf &
	gnome-open $(PREFIX).doc.pdf
	gnome-open $(PREFIX).ppt.pdf

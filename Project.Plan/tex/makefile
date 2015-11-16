.DEFAULT_GOAL := all
texfile := plan

compile: $(texfile).tex
	pdflatex -halt-on-error $(texfile).tex
	pdflatex -halt-on-error $(texfile).tex

clean:
	rm -f *.aux
	rm -f *.log
	rm -f *.out
	rm -f *.toc

purge: clean
	rm -f *.pdf

showpdf: $(texfile).pdf
	evince $(texfile).pdf

all: compile showpdf purge

pdf: compile clean
	mv $(texfile).pdf ../

texfile := CR
ifeq ($(shell which evince >/dev/null 2>&1; echo $$?), 0)
	VIEWER := evince
else
	# Oh I must be on a mac
	VIEWER := open
endif

.PHONY: all compile clean purge showpdf pdf

all: compile showpdf purge

compile: $(texfile).tex
	pdflatex -halt-on-error $(texfile).tex

clean:
	rm -f *.aux
	rm -f *.log
	rm -f *.out

purge: clean
	rm -f $(texfile).pdf

showpdf: compile
	$(VIEWER) $(texfile).pdf

pdf: compile clean
	mv $(texfile).pdf ../

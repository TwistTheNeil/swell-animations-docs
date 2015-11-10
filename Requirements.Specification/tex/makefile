texfile := requirements
ifeq ($(shell which evince >/dev/null 2>&1; echo $$?), 0)
	VIEWER := evince
else
	# Oh I must be on a mac
	VIEWER := open
endif

.DEFAULT_GOAL := all

all: compile showpdf purge

compile: $(texfile).tex
	pdflatex -halt-on-error $(texfile).tex
	pdflatex -halt-on-error $(texfile).tex

clean:
	-$(RM) *.aux
	-$(RM) *.log
	-$(RM) *.out

purge: clean
	$(RM) $(texfile).pdf

showpdf: compile
	$(VIEWER) $(texfile).pdf

pdf: compile clean
	mv $(texfile).pdf ../

pretty-compile: pretty-$(texfile).tex
    texfile := pretty-$(texfile)

pretty: pretty-compile compile showpdf purge

.PHONY: all clean

all: day-1.pdf day-2.pdf day-3.pdf instanton.pdf
	cp day-?.pdf instanton.pdf ../

clean:
	rm -f *.aux *.bbl *.log *.blg

%.aux : %.tex 
	pdflatex $*

%.pdf : %.tex %.bbl
	while (pdflatex $* ; \
	grep -q "Rerun to get cross" $*.log ) do true ; \
	done

%.bbl : %.aux biblio.bib
	bibtex $*



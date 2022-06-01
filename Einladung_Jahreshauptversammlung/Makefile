TEX := pdflatex -halt-on-error
PD := pandoc

TEXDEPS := $(wildcard *.tex) $(wildcard *.bib)
MDDEPS := $(wildcard *.md)

all: $(TEXDEPS:.tex=.pdf) $(MDDEPS:.md=.pdf) $(MDDEPS:.md=.txt)

%.pdf: %.tex Makefile
	$(TEX) $< && $(TEX) $<

%.txt: %.md Makefile
	$(PD) $< -o $@

%.pdf: %.md Makefile
	$(PD) $< -o $@

clean:
	rm -f *.aux *.log *.out *.bbl *.blg $(TEXDEPS:.tex=.pdf) $(MDDEPS:.md=.pdf) $(MDDEPS:.md=.txt)

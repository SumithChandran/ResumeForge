TEX = xelatex
SRC ?= resume.tex
PDF ?= resume.pdf

.PHONY: all clean distclean watch

all: $(PDF)

$(PDF): $(SRC)
	$(TEX) -interaction=nonstopmode -halt-on-error $(SRC)
	$(TEX) -interaction=nonstopmode -halt-on-error $(SRC)

clean:
	rm -f *.aux *.bbl *.bcf *.blg *.fdb_latexmk *.fls *.log *.out *.run.xml *.synctex.gz *.toc *.xdv

distclean: clean
	rm -f *.pdf

watch:
	@command -v latexmk >/dev/null 2>&1 || { echo "latexmk is required for watch mode. Install with: sudo apt-get install -y latexmk"; exit 1; }
	latexmk -pvc -view=none -xelatex -interaction=nonstopmode -halt-on-error $(SRC)
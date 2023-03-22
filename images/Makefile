ALL = benchmark_cheby_dense_10.pdf benchmark_cheby_dense_1000.pdf benchmark_cheby_sparse_1000.pdf
PDFLATEXOPTS = -file-line-error -interaction=nonstopmode -halt-on-error
PYTHON = ../.venv/bin/python

all: $(ALL)

%.pdf: %.tex
	@echo "\n** generate figure: $< -> $@"
	pdflatex $(PDFLATEXOPTS) $<

%.pdf: %.py matplotlibrc
	@echo "\n** generate figure: $< -> $@"
	$(PYTHON) $<

%.png: %.py matplotlibrc
	@echo "\n** generate figure: $< -> $@"
	$(PYTHON) $<

%.tex: %.py
	$(PYTHON) $<

clean:
	@rm -f *.aux
	@rm -f *.log
	@rm -f *.toc
	@rm -f *.blg
	@rm -rf *.out
	@rm -f *.bak
	@rm -f *.ilg
	@rm -f *.snm
	@rm -f *.nav
	@rm -f *.table
	@rm -f *.dvi
	@rm -f *.fls
	@rm -f *.bbl
	@rm -f *~
	@rm -f *Notes.bib
	@rm -f *-eps-converted-to.pdf
	@rm -f *.fdb_latexmk
	@rm -f *.synctex.gz*
	@rm -f ./latexrun
	@rm -rf __pycache__

distclean: clean
	@rm -f benchmark_cheby*.pdf
	@rm -f $(ALL)

.PHONY: all clean distclean

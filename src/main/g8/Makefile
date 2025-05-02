SHELL=/bin/bash
OUTDIR=out
LATEX=pdflatex -shell-escape -halt-on-error -file-line-error -synctex=1 -output-directory=$(OUTDIR)
.SUFFIXES: .tex .bib .aux .bbl .dvi .ps .pdf .thy
.PRECIOUS: %.aux

all:	 $(OUTDIR) dist-sys-notes.pdf dist-sys-slides.pdf solutions.pdf examples1.pdf

$(OUTDIR):
	mkdir -p $(OUTDIR)

%.pdf: %.tex $(OUTDIR)/%.aux | $(OUTDIR)
	$(LATEX) $<
	while grep 'Rerun to get ' $*.log; do $(LATEX) $<; done

$(OUTDIR)/%.aux:	%.tex | $(OUTDIR)
	$(LATEX) $<

%.bbl:	references.bib $(OUTDIR)/%.aux | $(OUTDIR)
	bibtex $(OUTDIR)/$*

# Actually depends on exercises.tex, which is generated as a side-effect of building dist-sys-notes.pdf
solutions.pdf: dist-sys-notes.pdf

# Slides from dist-sys-handout.pdf are embedded in the notes
dist-sys-notes.pdf:	dist-sys-handout.pdf dist-sys-notes.bbl

dist-sys-handout.pdf:	dist-sys.tex

dist-sys-slides.pdf:	dist-sys.tex

clean:
	rm -f {dist-sys-{slides,handout,notes},solutions,examples1}.{log,aux,out,bbl,blg,nav,snm,toc,dvi,ps,pdf}
	rm -rf out
	rm -rf *.synctex.gz
	rm -rf _minted*




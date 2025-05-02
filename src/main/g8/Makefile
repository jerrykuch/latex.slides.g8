SHELL=/bin/bash
OUTDIR=out
LATEX=pdflatex -shell-escape -halt-on-error -file-line-error -synctex=1 -output-directory=\$(OUTDIR)
.SUFFIXES: .tex .bib .aux .bbl .dvi .ps .pdf .thy
.PRECIOUS: %.aux

all:	 \$(OUTDIR) $filename$-notes.pdf $filename$-slides.pdf solutions.pdf examples1.pdf

\$(OUTDIR):
	mkdir -p \$(OUTDIR)

%.pdf: %.tex \$(OUTDIR)/%.aux | \$(OUTDIR)
	\$(LATEX) \$<
	while grep 'Rerun to get ' \$*.log; do \$(LATEX) \$<; done

\$(OUTDIR)/%.aux:	%.tex | \$(OUTDIR)
	\$(LATEX) \$<

%.bbl:	references.bib \$(OUTDIR)/%.aux | \$(OUTDIR)
	bibtex \$(OUTDIR)/\$*

# Actually depends on exercises.tex, which is generated as a side-effect of building $filename$-notes.pdf
solutions.pdf: $filename$-notes.pdf

# Slides from $filename$-handout.pdf are embedded in the notes
$filename$-notes.pdf:	$filename$-handout.pdf $filename$-notes.bbl

$filename$-handout.pdf:	$filename$.tex

$filename$-slides.pdf:	$filename$.tex

clean:
	rm -f {$filename$-{slides,handout,notes},solutions,examples1}.{log,aux,out,bbl,blg,nav,snm,toc,dvi,ps,pdf}
	rm -rf out
	rm -rf *.synctex.gz
	rm -rf _minted*




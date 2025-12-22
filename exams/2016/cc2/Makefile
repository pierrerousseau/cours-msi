MAIN       = main
MATIERE    = cc2
ANNEE      = 16
AUTEUR     = pr

NOM_PROJET = $(MATIERE)$(ANNEE)$(AUTEUR)

all:
	latex $(MAIN).tex
	dvips -o $(NOM_PROJET).ps $(MAIN).dvi
	ps2pdf $(NOM_PROJET).ps

clean:
	rm *.bak *~ *.log *.aux *.out *.pdf *.ps *.dvi

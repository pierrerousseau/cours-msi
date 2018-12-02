MAIN       = main
MATIERE    = cc1
ANNEE      = 18
AUTEUR     = pr

NOM_PROJET = $(MATIERE)$(ANNEE)$(AUTEUR)

all:
	latex $(MAIN).tex
	dvips -o $(NOM_PROJET).ps $(MAIN).dvi
	ps2pdf $(NOM_PROJET).ps

clean:
	rm *.bak *~ *.log *.aux *.out *.pdf *.ps *.dvi

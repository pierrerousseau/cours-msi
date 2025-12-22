MAIN       = main
MATIERE    = msi_cc1
ANNEE      = 15
AUTEUR     = pr

NOM_PROJET = $(MATIERE)$(ANNEE)$(AUTEUR)

all:
	latex $(MAIN).tex
	dvips -o $(NOM_PROJET).ps $(MAIN).dvi
	ps2pdf $(NOM_PROJET).ps

clean:
	rm *.bak *~ *.log *.aux *.out *.pdf *.ps *.dvi

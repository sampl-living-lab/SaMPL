#
# $Id: Makefile 49 2014-02-16 10:42:33Z nicb $
#
# You should set the INCLUDED_MAKE_PATH variable to wherever you have
# downloaded the templates module.
# You may find the template module cvs repository at the following CVSROOT:
# 
# :<mode>:<name>@cvs.miu-ft.org:/cvsroot/ec-stuff
#
# and the module name is 'templates'
#
SCELSI_ROOT=$(HOME)/me/svn/nicb/projects/music/Scelsi/doc/presentazioni
INCLUDED_MAKE_PATH=$(SCELSI_ROOT)/materiali
#
# there should be nothing to be changed below here
#

#
# $Id: Makefile 49 2014-02-16 10:42:33Z nicb $
#
TARGET=slides.pdf 


DVI=$(TARGET:.pdf=.dvi)
SRC=$(TARGET):.pdf=.dvi)
AUX=$(TARGET):.pdf=.aux)

TEMPLATEDIR=$(HOME)/me/txt/seminars/latex-templates/beamer/sme-ccppd/
IMAGEDIR=$(SCELSI_ROOT)/materiali
TEXINPUTS=".:$(IMAGEDIR):$(TEMPLATEDIR):"
PDFLATEX=TEXINPUTS=$(TEXINPUTS) pdflatex

BIBTEX=bibtex
all: $(TARGET)

$(TARGET):	images

%.pdf:	%.tex
	$(PDFLATEX) $<
	$(RM) $@
#	$(BIBTEX) $* 
	$(PDFLATEX) $<
	$(RM) $@
	$(PDFLATEX) $<

images:
	$(MAKE) -$(MAKEFLAGS) -C $(IMAGEDIR)

distclean:
	$(RM) *~ *.aux *.dvi *.out *.log *.bbl *.blg *.toc *.nav *.snm

clean: distclean
	$(RM) $(TARGET)




.PHONY:	clean images

.SUFFIXES:	.pdf .ps .dvi .aux .tex

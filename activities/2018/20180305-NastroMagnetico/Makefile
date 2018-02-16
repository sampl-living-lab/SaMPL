SRC=notes.md
TARGETS=$(SRC:.md=.txt) $(SRC:.md=.pdf)
TOTXT=pandoc -t plain
TOPDF=pandoc -t context

all: $(TARGETS)

clean:
	$(RM) $(TARGETS)

.SUFFIXES: .pdf .txt .md

%.txt: %.md
	$(TOTXT) -o $@ $<

%.pdf: %.md
	$(TOPDF) -o $@ $<

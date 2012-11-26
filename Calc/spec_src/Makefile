DOCUMENT=layout.tex
PDF=$(DOCUMENT:.tex=.pdf)
TEST=

all: clean $(DOCUMENT) $(PDF)

%.pdf: %.tex $(SOURCES)
	@echo 'Compiling to pdf'
ifeq ($(TEST),TRUE)
	@pdflatex -halt-on-error $<
	@mupdf $@ &
else
	@pdflatex -halt-on-error $< > /dev/null
endif

install: all
	@cp layout.pdf ../Specifications.pdf

clean:
	@echo 'Cleaning'
	@find . -type f -name "*.aux" -delete
	@find . -type f -name "*.toc" -delete
	@find . -type f -name "*.out" -delete
	@find . -type f -name "*.log" -delete
	@find . -type f -name "*.pdf" -delete

default : cfp2020.html

all : cfp2020.txt cfp2020.pdf cfp2020.html

# plain is not very impressive: headings are not underlined
%.txt : %.md
	pandoc --from=markdown --to=plain $< -o $@

%.html : %.md cfp2020.yaml pandoc.css caption.css Makefile
	pandoc --from=markdown --to=html5 -s --shift-heading-level-by=-1 --css=pandoc.css --css=caption.css $<  -o $@
# cfp2020.yaml

%.pdf : %.md
	pandoc --from=markdown $< -o $@

%.tex : %.md
	pandoc --from=markdown --to=latex $< -o $@

%.pdf : %.tex
	pdflatex $<

# --from= : markdown markdown_github markdown_mmd markdown_strict
# -f markdown-auto_identifiers
# --to=

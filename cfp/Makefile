default : ppdp2020cfp.html

all : ppdp2020cfp.txt ppdp2020cfp.pdf ppdp2020cfp.html

# plain is not very impressive: headings are not underlined
%.txt : %.md
	pandoc --from=markdown --to=plain $< -o $@

%.html : %.md ppdp2020cfp.yaml pandoc.css caption.css Makefile
	pandoc --from=markdown --to=html5 -s --shift-heading-level-by=-1 --css=pandoc.css --css=caption.css $<  -o $@
# ppdp2020cfp.yaml

%.pdf : %.md
	pandoc --from=markdown $< -o $@

%.tex : %.md
	pandoc --from=markdown --to=latex $< -o $@

%.pdf : %.tex
	pdflatex $<

# --from= : markdown markdown_github markdown_mmd markdown_strict
# -f markdown-auto_identifiers
# --to=

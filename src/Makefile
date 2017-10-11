# Igal Tabachnik, 2007.
# Based on work by Andres Raba et al., 2013-2015.

FIG := $(patsubst %.svg,%.pdf,$(wildcard fig/*/*.svg))
DIR := $(shell pwd)

all: ctfp.pdf

ctfp.pdf: ctfp.tex coverpage.pdf ${FIG}
	latexmk -shell-escape -pdflatex="xelatex %O %S" -pdf -dvi- -ps- $<; \
	mv ctfp.pdf ../category-theory-for-programmers.pdf

epub:
	mkdir images 
	cp content/0.0/images/* \
	content/1.1/images/* \
	content/1.10/images/* \
	content/1.2/images/* \
	content/1.3/images/* \
	content/1.4/images/* \
	content/1.5/images/* \
	content/1.6/images/* \
	content/1.7/images/* \
	content/1.8/images/* \
	content/1.9/images/* \
	content/2.1/images/* \
	content/2.2/images/* \
	content/2.3/images/* \
	content/2.4/images/* \
	content/2.5/images/* \
	content/2.6/images/* \
	content/3.1/images/* \
	content/3.10/images/* \
	content/3.11/images/* \
	content/3.12/images/* \
	content/3.13/images/* \
	content/3.14/images/* \
	content/3.15/images/* \
	content/3.2/images/* \
	content/3.3/images/* \
	content/3.6/images/* \
	content/3.8/images/* \
	content/3.9/images/* \
	images/
	pandoc -S -M title="Category Theory for Programmers" -t epub3 -o milewski-ctfp.epub \
                    content/0.0/Preface.tex content/1.1/Category\ -\ The\ Essence\ of\ Composition.tex content/1.2/Types\ and\ Functions.tex content/1.3/Categories\ Great\ and\ Small.tex content/1.4/Kleisli\ Categories.tex content/1.5/Products\ and\ Coproducts.tex content/1.6/Simple\ Algebraic\ Data\ Types.tex content/1.7/Functors.tex \
                    content/1.8/Functoriality.tex content/1.9/Function\ Types.tex content/1.9/Function\ Types.tex content/1.10/Natural\ Transformations.tex \
                    content/2.1/Declarative\ Programming.tex content/2.2/Limits\ and\ Colimits.tex content/2.3/Free\ Monoids.tex content/2.4/Representable\ Functors.tex content/2.5/The\ Yoneda\ Lemma.tex content/2.6/Yoneda\ Embedding.tex content/3.1/It\'s\ All\ About\ Morphisms.tex content/3.2/Adjunctions.tex \
                    content/3.3/Free-Forgetful\ Adjunctions.tex content/3.4/Monads\ -\ Programmer\'s\ Definition.tex content/3.5/Monads\ and\ Effects.tex content/3.6/Monads\ Categorically.tex content/3.7/Comonads.tex content/3.8/F-Algebras.tex content/3.9/Algebras\ for\ Monads.tex \
                    content/3.10/Ends\ and\ Coends.tex content/3.11/Kan\ Extensions.tex content/3.12/Enriched\ Categories.tex content/3.13/Topoi.tex content/3.14/Lawvere\ Theories.tex content/3.15/Monads,\ Monoids,\ and\ Categories.tex
	rm -fr images/


%.pdf: %.svg
	inkscape -f ${DIR}/$< -C -A ${DIR}/$@

clean:
	latexmk -CA

clean-all: clean
	${RM} ${FIG} coverpage.pdf ctfp.fls

.PHONY: all clean clean-all

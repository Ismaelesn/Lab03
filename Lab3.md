
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4

This text is **bold**
this text is *italic*
This text is both ***bold and italic***
>The drought had lasted now for ten million years, and the reign
of the terrible lizards had long since ended. Here on the
Equator, in the continent which would one day be known as
Africa, the battle for existence had reached a new climax of
ferocity, and the victor was not yet in sight. In this barren
and desiccated land, only the small or the swift or the
fierce could flourish, or even hope to survive.

List item 1
List item 2
List item 3

List item 1
	List item A
	List item B
List item 2

1. Frist instruction
2. Second instruction
3. Third instruction

1. First instruction
	1. Sub-instruction
	1. Sub-instruction
1. Second instruction
[link text](https://yandex.ru/)
``` language
your code goes in here
```
H~2~O
2^10^
$\sin^2 (x) + \cos^2 (x) = 1$
pandoc README.md -o README.pdf
pandoc README.md -o README.docx

FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
LATEX_FORMAT =
FILTER = --filter pandoc-crossref
%.docx: %.md
-pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
-pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
@echo $(FILES)
clean:
-rm $(FILES) *
# Conversion

## Docx to Markdown 

Docx to Markdown with images

``` python 
pandoc -o SalaryRegister.md --extract-media=./ SalaryRegister.docx
```

## Markdown to Docx
``` python 
pandoc --reference-doc twocolumns.docx -o UsersGuide18.docx example122.text
```

## HTML to Docx
``` python 
pandoc --reference-doc pandocTheme.docx -f html -t docx -o output.docx input.html
```

**Syntax Higlight**

1. Run the following command. Use any of the available themes such as `espresso`, `haddock`, `kate`, `monochrome`, `pygments`, `tango`	 and `zenburn`
``` python 
pandoc --print-highlight-style pygments > my_style.theme
```
2. Make changes to the generated `my_style.theme` file if required.

2. Then run the conversion command
``` python 
pandoc --reference-doc=custom-reference.docx -f html -t docx -s --highlight-style my_style.theme -o output.docx input.html
```
## HTML to Markdown
``` script 
pandoc -s -r --extract-media html pmm.html -o output.md
```

``` script 
pandoc -s -r --extract-media html input.html -o output.text
```

## HTML to ASCIIDOC

``` python 
pandoc -f html -t asciidoctor -o outpot.adoc input.html 
```

``` python 
pandoc -f html -t asciidoc -o output.asc input.html
```

## ASCIIDOC to HTML

https://rmoff.net/2020/04/16/converting-from-asciidoc-to-google-docs-and-ms-word/

``` python 
asciidoctor --backend html5 -a data-uri input.adoc
```

## ASCIIDOC to Docx
``` python 
INPUT_ADOC=my_input_file.adoc
asciidoctor --backend docbook --out-file - $INPUT_ADOC| \
pandoc --from docbook --to docx --output $INPUT_ADOC.docx

# On the Mac, this will open the generated file in MS Word
open $INPUT_ADOC.docx
```
``` python 
asciidoctor --backend docbook --out-file - $INPUT_ADOC| \
pandoc --from docbook --to docx --output $INPUT_ADOC.docx \
       --highlight-style espresso
```

``` python 	   
asciidoctor --backend docbook --out-file - $INPUT_ADOC| \
pandoc --from docbook --to docx --output $INPUT_ADOC.docx \
       --highlight-style my.theme
```

## ASCII to Docbook
``` python
asciidoctor -a data-uri -a icons -b docbook wagetype_dev.adoc
```
## wkhtmltopdf
``` python
wkhtmltopdf http://127.0.0.1:4000/docs/CSharpCodingStandards.html google.pdf
```

## Weasyprint

``` python 
python -m weasyprint http://weasyprint.org weasyprint.pdf
```

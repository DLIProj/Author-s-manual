# Conversion

## Docx to Markdown 

Docx to Markdown with images

``` python 
pandoc -o SalaryRegister.md --extract-media=./ SalaryRegister.docx
```

## HTML to Docx
``` python 
pandoc --reference-doc pandocTheme.docx -f html -t docx -o DailyTS.docx https://site/wagetype-based-timesheet/
```

## HTML to Markdown
``` script 
pandoc -s -r html pmm.html -o pmm.md
```

## HTML to ASCIIDOC

``` python 
pandoc -f html -t asciidoctor -o PRL_PayrollSheet00.adoc PRL_PayrollSheet00.html 
```

## ASCIIDOC to HTML

https://rmoff.net/2020/04/16/converting-from-asciidoc-to-google-docs-and-ms-word/

``` python 
asciidoctor --backend html5 -a data-uri my_input_file.adoc
```
``` python 
ASCIIDOC to Docx
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

## wkhtmltopdf
``` python
wkhtmltopdf http://127.0.0.1:4000/docs/CSharpCodingStandards.html google.pdf
```

## Weasyprint

``` python 
python -m weasyprint http://weasyprint.org weasyprint.pdf
```

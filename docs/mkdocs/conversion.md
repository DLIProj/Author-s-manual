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

## wkhtmltopdf
``` python
wkhtmltopdf http://127.0.0.1:4000/docs/CSharpCodingStandards.html google.pdf
```

## Weasyprint

``` python 
python -m weasyprint http://weasyprint.org weasyprint.pdf
```

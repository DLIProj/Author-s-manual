# Authoring

Antora authring guidelines


## Antora process
1. Do conversion (HTML/DocX/Markdown)
2. Clean html
3. Convert html to md
4. Convert md to ascii


## Antora commands

### Antora fetch
``` python 
antora antora-playbook.yml
antora --fetch antora-playbook.yml
antora --fetch author-mode.yml 
```

### Antora fetch local lunr

#### aantora-playbook.yml
``` python 
set "DOCSEARCH_ENABLED=true" && set "DOCSEARCH_ENGINE=lunr" && antora --generator antora-site-generator-lunr antora-playbook.yml
```
#### author-mode.yml
``` python 
set "DOCSEARCH_ENABLED=true" && set "DOCSEARCH_ENGINE=lunr" && antora --generator antora-site-generator-lunr author-mode.yml
```

#### local-playbook.yml
``` python
set "DOCSEARCH_ENABLED=true" && set "DOCSEARCH_ENGINE=lunr" && antora --generator antora-site-generator-lunr local-playbook.yml
``` 

### Install local serve
1. Install server

``` python linenums="1"
npm i -g http-server

OR 

yarn global add http-server
``` 

### Serve

``` python linenums="1"
http-server build/site -c-1
http-server build/site -c-1 -p 5000
-c-1 flag to disable caching
``` 

``` python 
http-server build/site -c-1 -p 5000 DDOCSEARCH_ENABLED=true DOCSEARCH_ENGINE=lunr antora site.yml
```

## Formatting

``` python
[%autowidth]
|===
| A
| B
| C
|===
``` 

### Include
https://gitlab.com/antora/antora/-/issues/596

### Mindfulness
https://www.youtube.com/watch?v=7-bPYMAdnnM
https://www.youtube.com/watch?v=h-CYAQqpvcw



## Doctype book level 0 error
``` python
= Book Title
:chapter: 12
:sectnums: 
:sectnumoffset: 11  (chapter minus 1)
:leveloffset: 1
``` 

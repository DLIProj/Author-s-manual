# Authoring


## Antora commands

### Antora fetch
``` java 
antora antora-playbook.yml
antora --fetch antora-playbook.yml
antora --fetch local-playbook.yml 
antora local-playbook.yml 
```

### Antora fetch local lunr


``` java linenums="1"
antora-playbook.yml
set "DOCSEARCH_ENABLED=true" && set "DOCSEARCH_ENGINE=lunr" && antora --generator antora-site-generator-lunr antora-playbook.yml

local-playbook.yml
set "DOCSEARCH_ENABLED=true" && set "DOCSEARCH_ENGINE=lunr" && antora --generator antora-site-generator-lunr local-playbook.yml
```

### Serve

``` asciidoc linenums="1"
http-server build/site -c-1
http-server build/site -c-1 -p 5000
-c-1 flag to disable caching
``` 

``` asciidoc 
http-server build/site -c-1 -p 5000 DDOCSEARCH_ENABLED=true DOCSEARCH_ENGINE=lunr antora site.yml
```

## Formatting

``` asciidoc
[%autowidth]
|===
| A
| B
| C
|===
``` 

### Include

**Include partials**
``` java
include::version@component:module:partial$name-of-file.adoc[optional attributes]
``` 

**Include from examples folder**
``` java
++++
include::example$process-overview-table.html[]
++++ 
``` 
``` java
include::version@component:module:example$name-of-file.ext[optional attributes]
``` 
[Support non-AsciiDoc content pages (such as HTML)](https://gitlab.com/antora/antora/-/issues/596) 

## Doctype book level 0 error
```java
= Book Title
:chapter: 12
:sectnums: 
:sectnumoffset: 11  (chapter minus 1)
:leveloffset: 1
``` 

## Source code 

```java
[source,java]
----
include::example$HelloWorld.java[]
----
``` 

```java
[source,java]
----
include::ROOT:example$output/query-max.json[]
----
``` 

```java
[source]
----
# Insert logic here
----
``` 

## Admonitions

```java
[IMPORTANT]
.Optional Title
====
Use an example block to create an admonition that contains complex content, such as (but not limited to):

* Lists
* Multiple paragraphs
* Source code
* Images
====
``` 

```java
[NOTE.think,caption=RESULTS]
====
* The following validation messages appear if any of the corresponding validation issues exist.
** Please Add Employees
====
``` 

## Tables with headers

```java
[width="90%",cols="30,60",options="header"]
|===
|Countries
|Capital

|India
|New Delhi

|USA
|Washington, D.C.
|===
```

```java
[width="90%",cols="30,60"]
|===

|Countries |Capital

|India
|New Delhi

|USA
|Washington, D.C.
|===
```


## Links

```java
https://asciidoctor.org[Asciidoctor,window=_blank]
```

```java
https://asciidoctor.org[Asciidoctor]
```

## List continuation
```java
. Step 1.
+
* Bullet list Item 1
* Bullet list Item 1

+
This is Step 2.
+
image:ess-install-image3.png[]
+
This is Line 2 of Step 2.

.  This is Step 3.
```

```java
## Glossary
[glossary]
mud:: wet, cold dirt
rain::
	water falling from the sky
```
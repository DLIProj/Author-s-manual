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

### Tables - Span/ Merge Cell over Rows and Columns
```java
== Table cell span
 
.Cell spans columns
|===
| Name | Description
 
| Asciidoctor
| Awesome way to write documentation
 
// This cell spans 2 columns, indicated
// by the number before the + sign.
// The + sign
// tells Asciidoctor to span this
// cell over multiple columns.
2+| The statements above say it all
 
|===
```

```java
.Cell spans rows
|===
| Name | Description
 
// This cell spans 2 rows,
// because the number after
// the dot (.) specifies the number
// of rows to span. The + sign
// tells Asciidoctor to span this
// cell over multiple rows.
.2+| Asciidoctor
| Awesome way to write documentation
 
| Works on the JVM
 
|===
```

```java
.Cell spans both rows and columns
|===
| Col1 | Col2 | Col 3
 
// We can combine the numbers for
// row and column span within one
// cell specifier.
// The number before the dot (.)
// is the number of columns to span,
// the number after the dot (.)
// is the number of rows to span.
2.2+| Cell spans 2 cols, 2 rows
| Row 1, Col 3
 
| Row 2, Col 3
 
|===
```

Refer to [Span/ Merge Cell over Rows and Columns](https://blog.mrhaki.com/2014/12/awesome-asciidoctor-span-cell-over-rows.html) for more details


## Links

```java
https://asciidoctor.org[Asciidoctor,window=_blank]
```

```java
https://asciidoctor.org[Asciidoctor]
```

## List continuation
```java
. Step1.
+
* Bullet list Item 1
* Bullet list Item 1

+
This is Step2.
+
image:ess-install-image3.png[]
+
This is Line2 of Step2.

.  This is Step3.
```

```java
## Glossary
[glossary]
mud:: wet, cold dirt
rain::
	water falling from the sky
```
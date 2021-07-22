# Authoring


## Antora commands

### Antora fetch
``` python 
antora antora-playbook.yml
antora --fetch antora-playbook.yml
antora --fetch local-playbook.yml 
antora local-playbook.yml 
```

### Antora fetch local lunr


``` python linenums="1"
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
``` asciidoc
include::version@component:module:partial$name-of-file.adoc[optional attributes]
``` 

**Include from examples folder**
``` asciidoc
++++
include::example$process-overview-table.html[]
++++ 
``` 
``` asciidoc
include::version@component:module:example$name-of-file.ext[optional attributes]
``` 
[Support non-AsciiDoc content pages (such as HTML)](https://gitlab.com/antora/antora/-/issues/596) 

## Doctype book level 0 error
``` asciidoc
= Book Title
:chapter: 12
:sectnums: 
:sectnumoffset: 11  (chapter minus 1)
:leveloffset: 1
``` 

## Source code 

``` asciidoc
[source,java]
----
include::example$HelloWorld.java[]
----
``` 

``` asciidoc
[source,java]
----
include::ROOT:example$output/query-max.json[]
----
``` 

``` asciidoc
[source]
----
# Insert logic here
----
``` 

## Admonitions

``` asciidoc
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

``` asciidoc
[NOTE.think,caption=RESULTS]
====
* The following validation messages appear if any of the corresponding validation issues exist.
** Please Add Employees
====
``` 

## Tables

```asciidoc
[width="75%",cols="1,1"]
|===
|Cell in column 1 Row 1
|Cell in column 2 Row 1

|Cell in column 1 Row 2
|Cell in column 2 Row 2

|Cell in column 1 Row 3
|Cell in column 2 Row 3
|===
```

## Links

```asciidoc
https://asciidoctor.org[Asciidoctor,window=_blank]
```

```asciidoc
https://asciidoctor.org[Asciidoctor]
```

## List continuation
```asciidoc
. Step 1.
+
* Bullet list Item 1
* Bullet list Item 1

+
To set permission, select the *Allow* check box next to the user/ groups.
+
image:ess-install-image3.png[]
+
To add any user accounts or groups that are missing from the **Security** tab >> **Group or usernames** list, refer to the link:#_grant_permission_for_the_users_not_listed_in_the_security_tab[Grant permission for the users not listed in the Security tab] section.

.  Click the **Apply** button and then close the dialog box.
```

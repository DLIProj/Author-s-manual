# Reuse content

Excrept from the discussion thread:
https://antora.zulipchat.com/#narrow/stream/282400-users/topic/.E2.9C.94.20Content.20reusabilty.2F.20Conditional.20logic

Use conditionals (i.e., preprocessor conditionals) as a potential approach. See https://docs.asciidoctor.org/asciidoc/latest/directives/conditionals/

For your usecase, you might have an attribute called `myClient`. You could use a conditional within your markup like:
``` python 
ifeval::["{myClient}" == "someBigCustomer"]
This feature is particularly useful for {myClient} users...
endif::[]
``` 
When you generate your documentation with Antora, you can set the `--attribute myClient=someBigCustomer` to create HTML suitable for that client.

**Attribute names should always be lowercase**

Recently, I was working on a conditional flow, and I dearly wished for an `ifelse::[]` macro. It's easy to use `ifeval` for additional case-specific content, but it is notably harder to manage alternative content. Especially when you have several exceptions and a default to express. I didn't find an `ifelse` issue... is this something you've seen requested previously?


**`Re`**: I'm pretty sure there is an open issue about it. I tried to implemented it once, but it turned out to be more complicated than anticipated. By I was a younger lad then ;)

https://github.com/asciidoctor/asciidoctor/issues/514

I also have an idea that could cover the most common use case for ifeval. Something like: ifdef:attribute-name[expected-value]

## Example

``` asciidoc 
ifeval::["{myclient}" == ""]
*Step 1*: User logs into ESS and #opens *DLI account*#.
endif::[]

ifeval::["{myclient}" == "HLB"]
*Step 1*: User logs into ESS and #opens *DLI account* and clicks *Go*#.
endif::[]

ifeval::["{myclient}" == "DAS"]
*Step 1*: User logs into ESS and #opens *{myclient} account*#.
endif::[]

*Step 2*: User goes to *Time Management* Module.

*Step 3*: User selects *Employee Timesheet*, make changes if required and then saves the changes.

*Step 4*: User logs out from ESS.
```  


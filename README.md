# CG-RDF

## Forked Use Case 

The following repository has been modified from its original source material, applied as an use case for the published paper

```
Zamborlini, V., van der Heijden, R., ten Teije, A. (2018). Filtering clinical guideline interactions with pre-conditions: A case study on diabetes guideline. CEUR Workshop Proceedings, 2237.

## Schema Folder

This folder contains the extended TMR modelling schema. The extension allows to represent `subguidelines`, that is, sets of recommendations from the same computer-interpretable guideline that must be suggested together for a particular clinical case.

## Instance Folder

This folder contains the  machine-interpretable clinical guidelines excerpts taken from the original use case -diabetes (DB)- along with the merging of them as generated by the CIG processing tool embedded with an extended version of TMR model found in:
```
https://github.kcl.ac.uk/k1214757/TMRWebX

```
Additionally, the folder also holds data sets for care actions, causation beliefs and transitions/situations/properties. All of them have also been reintroduced using the CIG processing tool.



## cds_hooks Folder
This folder contains a pair of definitions of the expected contextual information, following CDS Hook specifications, with respect to the DB. 
In file `DB-HT-OA-merge_1.md`, the hook defines one FHIR resource for each condition (i.e., DB, HT and OA conditions) whereas in file `DB-HT-OA-merge_2.md` there is an array. labelled as `multimorbidities` of FHIR Condition resources. For each hook we have defined a specific Fetch document.
Additionally, each hook comes with an example of an instantiation of the hook-pattern as a JSON document. FInally there is also a CDS Card response to ANY of the instantiation examples (file `FHIR_response.json`) where all three CIGs have ben triggered, and thus combined, and converted into one CarePlan FHIR resource containing all recommendations from the three CIGs and the interactions identified among them.

## database form Folder
This folder contains MongoDb documents related to each of the 2 hook patterns described in `cds_hooks folder`. The documents, known here as `Fetch Documents`, are used as input by the CDS Hooks Manager microservice (link below) to find and possibly transform data from the hook context into new data. This pre-cooking of data has as objective the activation of relevant parts of Computer-interpretable Guidelines for HT, DB and/or OA at a later stage, by the CDS Service Manager.

CDS Hooks Manager microservice:
`
enter here git page
`
CDS Service Manager microservice:
`
enter here git page
`

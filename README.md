# Project overview

## Objective and Method of Delivery

What?

> __providing a single 
> comprehensive security- enabled read/write data model for all VA VISTA data__ 
> across all VA VISTA operational systems, establishing a common technical foundation
> for master data management and computable data representation and __exchange between 
> VA and DoD clinical information systems__. --- PWS 1.1

For a better VISTA ...

> this project will not build a new health-care application. It is creating a __data-centric, node.js based framework__ for __efficiently using the powerful, multi-faceted, widely-deployed VISTA system__. Without VISTA, the framework would be useless. With the framework, VISTA will be a lot easier to integrate and extend.

Where?

> __all artifacts and deliverables__ shall be developed, version-controlled, stored, and delivered on an industry-standard __public Github__ repository (“Project Repository”). ... The Project Repository shall contain the one and only authoritative version of all artifacts produced under this contract. The government, all necessary stakeholders, and the __public__ shall have full read and download access of all artifacts on the Project Repository at all times --- PWS 1.6.15.1

## Deliverables and Estimated Schedule

In addition to Project Management (PM), the work breaks into __four main tracks__ (A-D) each managed and performed in one or more gits under the _vistadataproject_ organization.

Track | Name | Description | GIT
:---: | :---: | :--- | :---
A | Infrastructure | Project infrastructure including Test VISTA (“nodeVISTA”), gits, tooling, website | [nodeVISTA](https://github.com/vistadataproject/nodeVISTA), [Website](https://github.com/vistadataproject/vistadataproject.github.io), [documents](https://github.com/vistadataproject/documents) 
B | VDM | VISTA Data Model (VDM) - native model exposure and package implementation | [VDM](https://github.com/vistadataproject/VDM) 
C | MVDM | Master VISTA Data Model (MVDM) - definition and implementation of master data model for VISTA | [MVDM](https://github.com/vistadataproject/MVDM)
D | MVDMmap | Mapping MVDM to other models such as FHIR | [MVDMmap](https://github.com/vistadataproject/MVDMmap) 
PM | Project Management | Business/Project Management  | [documents](https://github.com/vistadataproject/documents)

__For current work plans, see the [VDM Track](https://github.com/vistadataproject/VDM), [MVDM Track](https://github.com/vistadataproject/MVDM) and [nodeVISTA](https://github.com/vistadataproject/nodeVISTA/tree/master/Commands) gits.__ The order of work emphasizes assembling and demonstrating all the pieces needed for the MVDM Module (definitions and testing code paths) before implementing it.

The following deliverables are called for in the Project Work Statement (PWS).

\# | Track | Name | Schedule | Git | Content(s) | Format(s) | PWS Section | 
:---: | :---: | :---: | :---: | :---: | :--- | :---: | :--- 
1AA | A |Artifact Repository | Q1 | &nbsp; | Project Gits | &nbsp; | 8.2
13 | A |  Website | Q1 &#8594; Q4 | [Website](https://github.com/vistadataproject/vistadataproject.github.io) | website, infographics to showcase the contents of the VDM and MVDM Subset | HTML, Javascript (d3.js) | 5.3.2
E3 | A | FileMan TEST VISTA ["nodeVISTA"] | Q1 &#8594; Q4 | [nodeVISTA](https://github.com/vistadataproject/nodeVISTA) | a test VISTA ("nodeVISTA") that hosts many test datasets | VISTA System, Vagrant | &nbsp;
E4 | A | Document Generator | Q1 &#8594; Q4 | [documents](https://github.com/vistadataproject/documents) | Programmer documentation will be generated using tools such as Sphinx (http://sphinx-doc.org/) and JSDoc (http://usejsdoc.org/). | Python, Javascript | &nbsp;
&nbsp; ||||||
&nbsp; ||||||
7.1 | B |  Machine Processable VISTA Data Model (VDM) "Read Only" | Q1 | [VDM](https://github.com/vistadataproject/VDM)  | _vdm.jsonld_, the native VISTA data model in JSON-LD based on one or more dd.jsonld's.<br><br>_VDM Maker_, a program that creates vdm.jsonld from dd.jsonld's.<br><br>This version will support query/read ("VDM (read)"). | JSON-LD, Python, Javascript | 5.3.1
7.2 | B |  Machine Processable VISTA Data Model (VDM) | Q2 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM)  | _vdm.jsonld_, enhanced by write-data in dd.jsonlds and rpc.jsonld.<br><br>_VDM Maker_ must process more information from dd.jsonld's and process rpc.jsonld. | JSON-LD, Python, Javascript | 5.3.1
8 | B |  Date-stamped FileMan Data Model Implementations (Definitions) (cross refs, triggers ...) | Q1 | [VDM](https://github.com/vistadataproject/VDM) | _dd.jsonld_, a data dictionary captured in JSON-LD<br><br>_DD Cacher_, a program that caches the dictionaries from VISTAs in JSON-LD form | JSON-LD, Python, Javascript | 5.3.1
E1 | B | RPC Model | Q1 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM), [nodeVISTA](https://github.com/vistadataproject/nodeVISTA) | formal definition of the model implicit in "write-back RPCs" (rpc.jsonld) for write support in vdm.jsonld (#7.2/#E2.2) | JSON-LD, Python | &nbsp;
E2.1 | B | VDM Package "Read-only" | Q1 | [VDM](https://github.com/vistadataproject/VDM) | a package that implements the VDM inside a VISTA. It will allow any FileMan data to be queried according to the VDM. | Javascript (node.js), MUMPS (KIDS) | &nbsp;
E2.2 | B | VDM Package | Q1 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM), [nodeVISTA](https://github.com/vistadataproject/nodeVISTA) | Will add support for creating, updating and deleting (full CRUD) VISTA Data according to a write-back supporting VDM (#7.2). | Javascript (node.js), MUMPS (KIDS) | &nbsp;
9 | B |  (Document) Approach to “Live VDM” Maintenance of Current State | Q4 | [VDM](https://github.com/vistadataproject/VDM) (Wiki) | In a wiki page, describe ways in which _dd.jsonld_ definitions and hence vdm.jsonld could keep pace with changes in VISTAs | Markdown | 5.3.1
15 | B |  Date Stamped (Application) Meta Data for lab, surgery and other applications | Q2 | [VDM](https://github.com/vistadataproject/VDM) | _Metadata Cacher_ that queries meta-data using _VDM package (Read)_. The results will be hosted on the project’s github. | Python, JSON-LD | 5.3.3
18 | B |  Machine-processable [PIKS] Annotations | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Distinguish patient data from other types of VISTA data. VDM PIKS enables MVDM PIKS which enables patient-centric security (#28) | JSON-LD | 5.3.4
19 | B |  Software code [for PIKS] | Q2 | [VDM](https://github.com/vistadataproject/VDM) | _PIKS Annotation Generator_. Relies on _VDM Package (Read)_ | Python | 5.3.4
25 | B |  Prototype query access to VISTA Data against VDM ["FQS"] | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Example clients that query (read-only) nodeVISTA using a REST-based FileMan Query Service (FQS) implemented over _VDM Package (Read)_ | Javascript, Python, JSON-LD | 5.4.1
33 | B |  Prototype Web-Based Query Interface to FileMan [VDM] Data | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Simple Web Client for using _VDM Package (Read)_ | Javascript | 5.4.1
&nbsp; ||||||
&nbsp; ||||||
10.1 | C |  Master VISTA Data Model (MVDM) "Read-only" | Q2 | [MVDM](https://github.com/vistadataproject/MVDM) | _mvdm.jsonld_, a formal “MVDM Subset” definition with much of the scope of the VPR RPC. Read-only support built on top of _VDM "Read-only"_ | JSON-LD | 5.3.2
10.2 | C |  Master VISTA Data Model (MVDM) | Q2 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | full CRUD support rounded out for _mvdm.jsonld_. | JSON-LD | 5.3.2
11.1 | C |  [MVDM over VDM] Heuristic (mapping) code "Read-only" [_MVDM Module_] | Q2 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | mapping tables and rules implemented in a _MVDM module_ that delivers a read-only version of MVDM over the VDM Package "Read-only". | Javascript (node.js), JSON | 5.3.2
11.2 | C |  [MVDM over VDM] Heuristic (mapping) code [_MVDM Module_] | Q2 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | full CRUD support added to "Read-only" base. | Javascript (node.js), JSON | 5.3.2
12 | C |  [MVDM] Normalization Reports | Q2 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) (Wiki) | Documents VDM to MVDM mapping as implemented in Deliverable #11. | Markdown | 5.3.2
14 | C |  Report on [MVDM] Exposure of older models | Q4 | [MVDM](https://github.com/vistadataproject/MVDM) (Wiki) | Describe how older, cruder models could be handled in the MVDM | Markdown | 5.3.2
28 | C |  Prototype Patient-centric Data Security | Q3 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | First document and then provide a self- contained prototype that shows how PIKS- enabled annotations enable patient-centric secure queries | Javascript, Markdown | 5.4.1
35 | C |  VISTA Application model(s)/Prototype(s) [Tests] | Q3 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | MVDM write back tests (tier 1 through 3), enabled by vdmn.js configurations. Test scenarios for Deliverable #11. | Javascript, Python | 5.4.2
36 | C |  Meta-model(s) [VPR] Prototype(s) | Q2 &#8594; Q3 | [MVDM](https://github.com/vistadataproject/MVDM) | Test code that shows how well the MVDM supports VPR (Read-only) convenience methods - read-only side of #35 | Javascript, Python | 5.4.2
&nbsp; ||||||
&nbsp; ||||||
32 | D |  Prototype Web-based Rules Hub | Q3 | [MVDMmap](https://github.com/vistadataproject/MVDMmap) | Prototype a sharable, crowd source-able mechanism to exchange and grow a library of open, standards-based, validated, and exchangeable transformation rules | Web-based interface | 5.4.1
39 | D |  Reference model(s)/Prototype(s) | Q3 &#8594; Q4 | [MVDMmap](https://github.com/vistadataproject/MVDMmap) | Prototype that demonstrates a mapping from MVDM to FHIR | Javascript and/or other translation rules languages | 5.4.2
40 | D |  Document VISTA-ese vs. FHIR | Q3 &#8594; Q4 | [MVDMmap](https://github.com/vistadataproject/MVDMmap) | Human-readable mapping descriptions | Markdown | 5.4.2
&nbsp; ||||||
&nbsp; ||||||
1A | PM | Non-disclosure/Non-Use Agreement	| Q1 | &nbsp; | &nbsp; | &nbsp; | 6.1
1B | PM |  Quality Control Plan [QCP] | Q1 | documents | an effective quality control program |  &nbsp; | 1.6.1
1C | PM |  Phase-out Migration Plan | Q4 | documents | elaborates the artifacts to be transitioned on the Project Repository, and a schedule for transition completion |  &nbsp; | 1.6.17
2	| PM |  Program Management Plan (PMP)	| Q1 | documents | strategy to accomplish the tasks and include the risk, quality and technical management approach, work breakdown structure (WBS), schedule management approach, schedule, cost requirements, and proposed staffing  | &nbsp; | 5.2
3	| PM |  Program Schedule and Monthly Updates | Monthly | documents | schedule, updated monthly | &nbsp; | 5.2
4	| PM |  Monthly Progress Report | Monthly | &nbsp; | includes project status and financial management reporting | &nbsp; | 5.2
5	| PM |  Quarterly Strategic Communications Message | Quarterly | documents | project progress and feasibility of transition to production | &nbsp; | 5.2

Notes: 
  * 25 technical deliverables (in _VDM_, _MVDM_, _MVDMmap_ aswell as _nodeVISTA_) are enumerated above.
  * E1-4 are deliverables required but not explicitly enumerated in the PWS.
  * Deliverable #’s have gaps. The following PWS deliverables were removed as redundant or out of scope per government determination: 6, 16, 17, 20-24, 26, 27, 29-31, 34, 37, 38
  * There is a substantial difference in complexity between read-only and read-write models and implementations. To write anything demands knowledge of rules that go beyond the demands of reading. As a result, both VDM and MVDM models and packages will be delivered in two phases, with read coming first. 
    * VDM "Read" and its package (#7.1 and #E1.1) are due in Q1; Deliverables #8, #15, #18, #19, #25, #33 only require such read-only functionality and are due in Q2
    * MVDM "Read" and its module (#10.1 and #11.1) are due in Q2: Deliverables #28, #36 and all of track D rely only on MVDM ("Read").
    * Read-only VDM and by extension MVDM will expand on open source [FMQL](https://github.com/caregraf/FMQL)

### Formats and Licenses of deliverable artifacts (PWS 8.2) 

Artifact | Format(s) | License
:---: | --- | ---
Data | CSV if tabular structure; JSON-LD for all other structures. | Creative Commons CC0.
Metadata | JSON-LD. | Creative Commons CC0.
Documents | Markdown (git Markdown or Docbook). From this HTML and PDF shall be auto-generated | Creative Commons CC0.
Code (Software) | Source code, and all dependent code, with full version control history. | Apache 2.0.

## System Access 

From PWS 3.1 - within 30 days of contract award the Government will provide contractor access to:

  1. Data Dictionary (^DD) extract from at least five current operational VISTAs. These data dictionaries contain no patient data, PHI, or PII (i.e. no sensitive information).
  2. Current authoritative Master ("Platinum") version of VISTA as maintained internally by the VA. Metadata from this must be complete and without any alterations or redactions.13 The metadata does not contain any patient data, PHI, or PII (i.e. no sensitive information).
  3. Copy of a VISTA with test patients used by VA for internal projects
  4. Copy of at least one real operational VISTA ("Prod Clone" or “Test VISTA”) which would be kept
within the NIPRed network, as it will have non de-identified patient data. 
  5. A VISTA with real but de-identified patient data

In addition, the Project requested that within 30 days of contract award the Government will provide the Project access to:

  1. A copy of the latest version of the VPR RPC software and documentation.
  2. The latest copy of the FileMan namespace spreadsheet.
  3. A FileMan namespace exclusively for the Project to allow for the creation of Project files and fields in FileMan.
  4. Access to the most up-to-date VISTA Integrations Agreements (sometimes called IAs), or Database Administrator Integration Agreements (DBIAs).
  5. Sufficient InterSystems Cache licenses to host FileMan Test VISTA systems.
  6. VA VISTA Sandbox Account with full Linux VM.
  
## Credits

This project builds on the work of many.

Who | Work | In Project Track | Comment
:--- | --- | :---: | ---
George Timson<br>Tom Munnecke | FileMan | VDM | The pair who made VISTA
Nancy Anthracite | Opening up VISTA | &nbsp; | Advocated tirelessly for in-the-open VISTA development
Rob Tweed | Node/M | Infrastructure | Integrated node.js with VISTA and MUMPS ("nodeVISTA")
Manu Sporny | JSON-LD | MVDM | Created and promoted the JSON-LD standard
Kevin Meldrum | VPR RPC | MVDM | Created a JSON-based mechanism for accessing VISTA's patient data 
Chris Edwards | Vagrant Installer for VISTA | Infrastructure | Packaged VISTA for today 


## Diagrams / Images

* VISTA DD -> [DD Cacher] -> dd.jsonld -> [VDM Maker] -> vdm.jsonld   (read-only)
* VISTA RPCs ->[?RPC Cacher ] -> rpc.jsonld -> [VDM Maker] -> vdm.jsonld  (writeback)
* mvdm.jsonld =  vdm.jsonld (embedded dd.jsonld + embedded rpc.jsonld)
* Markdown -> [Doc Gen] -> HTML, Word, PDF


## Deliverables by Type

### Metadata
Name | format | functon
:--- | --- | :---:
dd.jsonld 	| JSON-LD | 	native VISTA data dictionary, captured in JSON-LD
rpc.jsonld | JSON-LD |		formal definition of the model implicit in RPCs, captured in JSON-LD
vdm.jsonld | JSON-LD |		native VISTA data model based on one or more dd.jsonld's and/or rpc.jsonld's
mvdm.jsonld | JSON-LD | 	MVDM subset of VDM that supports full CRUD
PIKS | JSON-LD | 			annotations to VDM


### Software
Name | language | function
:--- | --- | :---:
DD Cacher | |	?? needs definition
RPC Cacher | | ?? Does this exist?
VDM Maker | | creates vdm.jsonld from dd.jsonld's
VDM Package | | implements VDM inside Fileman - "embedded, explicit data model"
MVDM Package | |implements MVDM inside Fileman - "embedded, explicit data and transactional model"
vdmn.js | |		?? mentioned but no definition
Doc Gen	| |		Sphinx, JSDoc,...


## DEFINITIONS
* Metadata Cacher	- queries (VISTA Application) metadata using VDM Package
* PIKS Gen		- PIKS annnotation generator
* FQS				- Fileman Query Service (RESTful) based on embedded VDM model (read only)
* Mapping code	- mapping tables/rules in MVDM Package


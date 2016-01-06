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
7 | B |  Machine Processable VISTA Data Model (VDM) | Q1 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM)  | _vdm.jsonld_, the native VISTA data model in JSON-LD based on one or more dd.jsonld's and rpc.jsonld.<br><br>_VDM Maker_, a program that creates vdm.jsonld from dd.jsonld's and rpc.jsonld.<br><br>The first version will support query/read ("VDM (read)") and depend only on _dd.jsonld_; full CRUD support will follow and draw on the nuance added by _rpc.jsonld_. | JSON-LD, Python, Javascript | 5.3.1
8 | B |  Date-stamped FileMan Data Model Implementations (Definitions) (cross refs, triggers ...) | Q1 | [VDM](https://github.com/vistadataproject/VDM) | _dd.jsonld_, a data dictionary captured in JSON-LD<br><br>_DD Cacher_, a program that caches the dictionaries from VISTAs in JSON-LD form | JSON-LD, Python, Javascript | 5.3.1
E1 | B | RPC Model | Q1 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM), [nodeVISTA](https://github.com/vistadataproject/nodeVISTA) | formal definition of the model implicit in "write-back RPCs" (rpc.jsonld) for write support in vdm.jsonld (#7) | JSON-LD, Python | &nbsp;
E2 | B | VDM Package | Q1 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM), [nodeVISTA](https://github.com/vistadataproject/nodeVISTA) | a package that implements the VDM inside a VISTA. Such a package is needed for the MVDM Module of deliverable 11 and for the prototypes of 5.4. It would provide a Javascript service for creating, reading, updating and deleting (CRUD) VISTA Data according to the VDM.<br><br>The first version will support query/read ("VDM Package (read)"); full CRUD support will follow. | Javascript (node.js), MUMPS (KIDS) | &nbsp;
9 | B |  (Document) Approach to “Live VDM” Maintenance of Current State | Q4 | [VDM](https://github.com/vistadataproject/VDM) (Wiki) | In a wiki page, describe ways in which _dd.jsonld_ definitions and hence vdm.jsonld could keep pace with changes in VISTAs | Markdown | 5.3.1
15 | B |  Date Stamped (Application) Meta Data for lab, surgery and other applications | Q2 | [VDM](https://github.com/vistadataproject/VDM) | _Metadata Cacher_ that queries meta-data using the (read-only) _VDM package_. The results will be hosted on the project’s github. | Python, JSON-LD | 5.3.3
18 | B |  Machine-processable [PIKS] Annotations | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Distinguish patient data from other types of VISTA data. VDM PIKS enables MVDM PIKS which enables patient-centric security (#28) | JSON-LD | 5.3.4
19 | B |  Software code [for PIKS] | Q2 | [VDM](https://github.com/vistadataproject/VDM) | _PIKS Annotation Generator_ | Python | 5.3.4
25 | B |  Prototype query access to VISTA Data against VDM ["FQS"] | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Example clients that query (read-only) nodeVISTA using a REST-based FileMan Query Service (FQS) implemented over a read-only version of the VDM Package | Javascript, Python, JSON-LD | 5.4.1
33 | B |  Prototype Web-Based Query Interface to FileMan [VDM] Data | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Simple Web Client for using a read-only version of the VDM Package | Javascript | 5.4.1
&nbsp; ||||||
&nbsp; ||||||
10 | C |  Master VISTA Data Model (MVDM) | Q1 &#8594; Q3 | [MVDM](https://github.com/vistadataproject/MVDM) | _mvdm.jsonld_, a formal “MVDM Subset” definition with much of the scope of the VPR RPC.<br><br>The first version will support query/read ("MVDM (read)"); full CRUD support will follow. | JSON-LD | 5.3.2
11 | C |  [MVDM over VDM] Heuristic (mapping) code [_MVDM Module_] | Q2 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | mapping tables and rules implemented in a _MVDM module_ to enable expanding MVDM to VDM mapping.<br><br>Builds on the _VDM Package_ (#E1).<br><br>The first version will support query/read ("MVDM Module (read)"); full CRUD support will follow. | Javascript (node.js), JSON | 5.3.2
12 | C |  [MVDM] Normalization Reports | Q1 &#8594; Q3 | [MVDM](https://github.com/vistadataproject/MVDM) (Wiki) | Documents VDM to MVDM mapping as implemented in Deliverable #11. Like 10 and 11, these report first capture read-only behavior before going on to cover all of CRUD. | Markdown | 5.3.2
14 | C |  Report on [MVDM] Exposure of older models | Q4 | [MVDM](https://github.com/vistadataproject/MVDM) (Wiki) | Describe how older, cruder models could be handled in the MVDM | Markdown | 5.3.2
28 | C |  Prototype Patient-centric Data Security | Q3 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | First document and then provide a self- contained prototype that shows how PIKS- enabled annotations enable patient-centric secure queries | Javascript, Markdown | 5.4.1
35 | C |  VISTA Application model(s)/Prototype(s) [Tests] | Q2 &#8594; Q4 | [MVDM](https://github.com/vistadataproject/MVDM) | MVDM write back tests (tier 1 through 3), enabled by vdmn.js configurations. Test scenarios for Deliverable #11. | Javascript, Python | 5.4.2
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
  * E1-4 are deliverables required but not explicitly enumerated in the PWS.
  * Deliverable #’s have gaps. The following PWS deliverables were removed as redundant or out of scope per government determination: 6, 16, 17, 20-24, 26, 27, 29-31, 34, 37, 38
  * There is a substantial difference in complexity between read-only (_VDM Read_, _MVDM Read_) and read-write (_VDM Full_, MVDM Full_) models and implementations. To write anything demands knowledge of rules that go beyond the demands of reading. As a result, both VDM and MVDM models and packages will be delivered in two phases, with read coming first. Deliverables #15, #18, #19, #25, #33 only require _VDM Read_; deliverables #28 and #36 and all of track D need only rely on _MVDM Read_ - they will be implemented once basic Read access is available.
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

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

## Credits

This project builds on the work of many.

Who | Work | In Project Track | Comment
:--- | --- | :---: | ---
George Timson<br>Tom Munnecke | FileMan | VDM | The pair who made VistA
Nancy Anthracite | Opening up VistA | &nbsp; | Advocated tirelessly for in-the-open VISTA development
Rob Tweed | Node/M | Infrastructure | Integrated node.js with VistA and MUMPS ("nodeVISTA")
Manu Sporny | JSON-LD | VDMN | Created and promoted the JSON-LD standard
Kevin Meldrum | VPR RPC | VDMN | Created a JSON-based mechanism for accessing VISTA's patient data 
Chris Edwards | Vagrant Installer for VISTA | Infrastructure | Packaged VistA for today 

## Deliverables and Estimated Schedule

Work breaks into __5 tracks__, each managed and performed in one or more gits under the _vistadataproject_ organization.

Track | Name | Description | GIT
:---: | :---: | :--- | :---
A | Infrastructure | Test VISTA ("nodeVISTA"), gits, tooling, website | [nodeVISTA](https://github.com/vistadataproject/nodeVistA), [Website](https://github.com/vistadataproject/vistadataproject.github.io), [documents](https://github.com/vistadataproject/documents) 
B | VDM | VistA Native Data model (VDM) - exposure and package implementation | [VDM](https://github.com/vistadataproject/VDM) 
C | VDMN | VistA Normalized Data model (VDMN) - definition and module implementation | [VDMN](https://github.com/vistadataproject/VDMN)
D | VDMNmap | Mapping VDMN to other models such as FHIR | [VDMNmap](https://github.com/vistadataproject/VDMNmap) 
E | Project Management | Business/Project Management (Deliverables 1A &#8594; 5) | [documents](https://github.com/vistadataproject/documents)

__For current work plans, see the [VDM Track](https://github.com/vistadataproject/VDM), [VDMN Track](https://github.com/vistadataproject/VDMN) and [nodeVistA](https://github.com/vistadataproject/nodeVistA/tree/master/Commands) gits.__ The order of work emphasizes assembling and demonstrating all the pieces needed for the VDMN Module (definitions and testing code paths) before implementing it.

The following deliverables are called for in the Project Work Statement (PWS).

\# | Track | Name | Schedule | Git | Content(s) | Format(s) | PWS Section | 
:---: | :---: | :---: | :---: | :---: | :--- | :---: | :--- 
1AA |	ALL |Artifact Repository |	Q1 | &nbsp; | Vista Data Project Organization and Gits | &nbsp; | 8.2
&nbsp; ||||||
7 | B |  Machine Processable VISTA Data Model (VDM) | Q1 | [VDM](https://github.com/vistadataproject/VDM)  | _vdm.jsonld_, the native VISTA data model in JSON-LD based on one or more dd.jsonld's<br><br>_VDM Maker_, a program that creates vdm.jsonld from dd.jsonld's. | JSON-LD, Python, Javascript | 5.3.1
8 | B |  Date-stamped FileMan Data Model Implementations (Definitions) (cross refs, triggers ...) | Q1 | [VDM](https://github.com/vistadataproject/VDM) | _dd.jsonld_, a data dictionary captured in JSON-LD<br><br>_DD Cacher_, a program that caches the dictionaries from VISTAs | JSON-LD, Python, Javascript | 5.3.1
9 | B |  (Document) Approach to “Live VDM” Maintenance of Current State | Q4 | [VDM](https://github.com/vistadataproject/VDM) (Wiki) | In a wiki page, describe ways in which _dd.jsonld_ definitions and hence vdm.jsonld could keep pace with changes in VISTAs | Markdown | 5.3.1
&nbsp; ||||||
10 | C |  Normalized VISTA Data Model (VDMN) | Q1 &#8594; Q3 | [VDMN](https://github.com/vistadataproject/VDMN) | _vdmn.jsonld_, a formal “VDMN Subset” definition with much of the scope of the VPR RPC | JSON-LD | 5.3.2
11 | C |  [VDMN over VDM] Heuristic (mapping) code [_VDMN Module_] | Q1 &#8594; Q3 | [VDMN](https://github.com/vistadataproject/VDMN) | mapping tables and rules built over the course of the project in a _VDMN module_ to enable expanding VDMN to VDM mapping | Javascript (node.js), JSON | 5.3.2
12 | C |  [VDMN] Normalization Reports | Q1 &#8594; Q3 | [VDMN](https://github.com/vistadataproject/VDMN) (Wiki) | Documents VDM to VDMN mapping as implemented in Deliverable 11 in a git wiki | Markdown | 5.3.2
13 | B, C|  Website | Q1 &#8594; Q4 | [Website](https://github.com/vistadataproject/vistadataproject.github.io) | website, infographics to showcase the contents of the VDM and VDMN Subset | HTML, Javascript (d3.js) | 5.3.2
14 | C |  Report on [VDMN] Exposure of older models | Q3 | [VDMN](https://github.com/vistadataproject/VDMN) (Wiki) | Describe how older, cruder models could be handled in the VDMN | Markdown | 5.3.2
&nbsp; ||||||
15 | C |  Date Stamped (Application) Meta Data for lab, surgery and other applications | Q2 | [VDM](https://github.com/vistadataproject/VDM) | _Metadata Cacher_ that queries meta-data using the _VDM package_. The results will be hosted on the project’s github. | Python, JSON-LD | 5.3.3
&nbsp; ||||||
18 | C |  Machine-processable [PIKS] Annotations | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Enables Patient-centric security (Deliverable 28), distinguishing patient data from other types of VISTA data | JSON-LD | 5.3.4
19 | C |  Software code [for PIKS] | Q2 | [VDM](https://github.com/vistadataproject/VDM) | _PIKS Annotation Generator_ | Python | 5.3.4
&nbsp; ||||||
25 | B |  Prototype query access to VISTA Data against VDM ["FQS"] | Q1 &#8594; Q2 | [VDM](https://github.com/vistadataproject/VDM) | Example clients that query the FileMan Test VISTA using a REST-based FileMan Query Service (FQS) implemented over the VDM Package | Javascript, Python, JSON-LD | 5.4.1
28 | C |  Prototype Patient-centric Data Security | Q3 | [VDM](https://github.com/vistadataproject/VDM) | Document and provide a self- contained prototype that shows how PIKS- enabled annotations enable patient-centric secure queries | Javascript, Markdown | 5.4.1
32 | D |  Prototype Web-based Rules Hub | Q4 | [VDMNmap](https://github.com/vistadataproject/VDMNmap) | Prototype a sharable, crowd source-able mechanism to exchange and grow a library of open, standards-based, validated, and exchangeable transformation rules | Web-based interface | 5.4.1
33 | B |  Prototype Web-Based Query Interface to FileMan [VDM] Data | Q2 | [VDM](https://github.com/vistadataproject/VDM) | Simple GUI (VDM UI) for VDM Package | Javascript | 5.4.1
&nbsp; ||||||
35 | C |  VISTA Application model(s)/Prototype(s) [Tests] | Q1 &#8594; Q4 | [VDMN](https://github.com/vistadataproject/VDMN) | VDMN write back tests (tier 1 through 3), enabled by vdmn.js configurations. Test scenarios for Deliverable 11. | Javascript, [Python] | 5.4.2
&nbsp; ||||||
36 | C |  Meta-model(s) [VPR] Prototype(s) | Q1 &#8594; Q3 | [VDMN](https://github.com/vistadataproject/VDMN) | Test code that shows how well the VDMN supports VPR convenience methods | Javascript, Python | 5.4.2
&nbsp; ||||||
39 | D |  Reference model(s)/Prototype(s) | Q3 &#8594; Q4 | [VDMNmap](https://github.com/vistadataproject/VDMNmap) | Prototype that demonstrates a mapping from VDMN to FHIR | Javascript and/or other translation rules languages | 5.4.2
40 | D |  Document VISTA-ese vs. FHIR | Q4 | [VDMNmap](https://github.com/vistadataproject/VDMNmap) | Human-readable mapping descriptions | Markdown | 5.4.2
&nbsp; ||||||
1A | E | Non-disclosure/Non-Use Agreement	| Q1 | &nbsp; | &nbsp; | &nbsp; | 6.1
1B | E |  Quality Control Plan [QCP] | Q1 | documents | an effective quality control program |  &nbsp; | 1.6.1
1C | E |  Phase-out Migration Plan | Q4 | documents | elaborates the artifacts to be transitioned on the Project Repository, and a schedule for transition completion |  &nbsp; | 1.6.17
2	| E |  Program Management Plan (PMP)	| Q1 | documents | strategy to accomplish the tasks and include the risk, quality and technical management approach, work breakdown structure (WBS), schedule management approach, schedule, cost requirements, and proposed staffing  | &nbsp; | 5.2
3	| E |  Program Schedule and Monthly Updates | Monthly | documents | schedule, updated monthly | &nbsp; | 5.2
4	| E |  Monthly Progress Report | Monthly | &nbsp; | includes project status and financial management reporting | &nbsp; | 5.2
5	| E |  Quarterly Strategic Communications Message | Quarterly | documents | project progress and feasibility of transition to production | &nbsp; | 5.2

Deleted deliverables (redundant or out of scope): 6, 16, 17, 20-24, 26, 27, 29-31, 34, 37, 38

Extra deliverables not explicitly numbered in the PWS ...

\# | Name | Schedule | Git | Content(s) | Format(s)
:---: | :---: | :---: | :---: | :--- | :---: 
E1 | VDM Package | Q1 &#8594; Q3 | [VDM](https://github.com/vistadataproject/VDM) | a package that implements the VDM inside a VISTA. Such a package is needed for the VDMN Module of deliverable 11 and for the prototypes of 5.4. It would provide a Javascript service for creating, reading, updating and deleting (CRUD) VISTA Data according to the VDM. | Javascript (node.js), MUMPS (KIDS) 
E2 | FileMan TEST VistA | Q1 &#8594; Q4 | [nodeVISTA](https://github.com/vistadataproject/nodeVistA) | a test VistA that can host many different test datasets | VistA System, Vagrant
E3 | Document Generator | Q1 &#8594; Q4 | [documents](https://github.com/vistadataproject/documents) | Programmer documentation will be generated for all applications using tools such as Sphinx (http://sphinx-doc.org/) and JSDoc (http://usejsdoc.org/). | Python, Javascript

__TODO__: order by quarter using a dynamic table.

Formats and Licenses of deliverable artifacts (PWS 8.2) 

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

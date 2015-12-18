# documents

Cross Project Documentation not hosted on the website

Programmer documentation will be generated for all applications using tools such as Sphinx (http://sphinx-doc.org/) and JSDoc (http://usejsdoc.org/).

# Project Objective and Method of Delivery

> The objective of this performance work statement (PWS) is to prototype and demonstrate 
> the __exposure, analytics, and automation of VA VISTA metadata__ using modern, 
> machine- processable, web-centric metadata standards, __providing a single 
> comprehensive security- enabled read/write data model for all VA VISTA data__ 
> across all VA VISTA operational systems, establishing a common technical foundation
> for master data management and computable data representation and __exchange between 
> VA and DoD clinical information systems__.

--- 1.1

> __all artifacts and deliverables__ shall be developed, version-controlled, stored, and delivered on an industry-standard public __Github__ repository (“Project Repository”). ... The Project Repository shall contain the one and only authoritative version of all artifacts produced under this contract. The government, all necessary stakeholders, and the __public__ shall have full read and download access of all artifacts on the Project Repository at all times

--- 1.6.15.1

\# | Name | Schedule | Git | Content(s) | Format(s) | PWS Section | 
:---: | :---: | :---: | :---: | :--- | :---: | :--- 
7 | Machine Processable VISTA Data Model (VDM) | Q1 | VDM  | _vdm.jsonld_, the native VISTA data model in JSON-LD based on one or more dd.jsonld's<br><br>_VDM Maker_, a program that creates vdm.jsonld from dd.jsonld's. | JSONLD, Python, Javascript | 5.3.1
8 | Date-stamped FileMan Data Model Implementations (Definitions) (cross refs, triggers ...) | Q1 | VDM | _dd.jsonld_, a data dictionary captured in JSON-LD<br><br>_DD Cacher_, a program that caches the dictionaries from VISTAs | JSONLD, Python, Javascript | 5.3.1
9 | (Document) Approach to “Live VDM” Maintenance of Current State | Q4 | VDM (Wiki) | In a wiki page, describe ways in which _dd.jsonld_ definitions and hence vdm.jsonld could keep pace with changes in VISTAs | Markdown | 5.3.1
&nbsp; ||||||
10 | Normalized VISTA Data Model (VDMN) | Q1 -> Q3 | VDMN | _vdmn.jsonld_, a formal “VDMN Subset” definition with much of the scope of the VPR RPC | JSON-LD | 5.3.2
11 | (VDMN over VDM) Heuristic (mapping) code | Q1 &#8594; Q3 | VDMN | mapping tables and rules built over the course of the project in the _VDMN module_ to enable expanding VDMN to VDM mapping | Javascript, JSON | 5.3.2
12 | (VDMN) Normalization Reports | Q1 &#8594; Q3 | VDMN (Wiki) | Documents VDM to VDMN mapping as implemented in Deliverable 11 in a git wiki | Markdown | 5.3.2
13 | Website | Q1 &#8594; Q4 | Website | website, infographics to showcase the contents of the VDM and VDMN Subset | HTML, Javascript (d3.js) | 5.3.2
14 | Document (VDMN ) exposure of older models (schedule, lab ...) report | Q3 | VDMN (Wiki) | describe how older, cruder models could be handled in the VDMN | Markdown | 5.3.2
&nbsp; ||||||
15 | Date Stamped (Application) Meta Data for lab, surgery and other applications | Q2 | VDM | _Meta Data Cacher_ that queries meta-data using the _VDM package_. The results will be hosted on the project’s github. | Python, JSON-LD | 5.3.3
&nbsp; ||||||
18 | Machine-processable (PIKS) Annotations | Q2 | VDM | Enables Patient-centric security (#28), distinguished patient from other types of data | JSON-LD | 5.3.4
19 | Software code (for PIKS) | Q2 | VDM | _PIKS Annotation Generator_ | Python | 5.3.4
&nbsp; ||||||
25 | VDM Query Prototype that uses a FileMan Query Service ("FQS") | Q1 &#8594; Q2 | VDM | Example clients that query the FileMan Test VISTA using a REST-based FQS implemented over the VDM Package | Javascript, Python, JSON-LD | 5.4.1
28 | Prototype Patient-centric Data Security | Q3 | VDM | document and provide a self-contained prototype that shows how PIKS-enabled annotations enable patient-centric secure queries | Javascript, Markdown | 5.4.1
32 | Prototype Web-based Rules Hub | Q4 | VDMNmap | prototype a sharable, crowdsource-able mechanism to exchange and grow a library of open, standards-based, validated, and exchangeable transformation rules | Web-based interface | 5.4.1
33 | Prototype Web-Based Query Interface to FileMan (VDM) Data | Q2 | VDM | Simple GUI (VDM UI) for VDM Package | Javascript | 5.4.1
&nbsp; ||||||
35 | VISTA Application model(s)/Prototype(s) (Testing) | Q1 &#8594; Q4 | VDMN | VDMN write back tests (tier 1 through 3), enabled by vdmn.js configurations | Javascript | 5.4.2
&nbsp; ||||||
36A | Meta-model(s) - VPR Prototype(s)5 | Q1 &#8594; Q3 | VDMN | Test code that shows how well the VDMN supports VPR convenience methods
Javascript, Python | 5.4.2
&nbsp; ||||||
39 | Reference model(s)/Prototype(s) | Q3 &#8594; Q4 | VDMNmap | Prototype that demonstrates a mapping from VDMN to FHIR | Javascript and/or other translation rules languages | 5.4.2
40 | Document VISTA-ese vs. FHIR | Q4 | VDMN | Human-readable mapping descriptions | Markdown | 5.4.2
&nbsp; ||||||

Extra deliverables not explicitly numbered in the PWS ...

\# | Name | Schedule | Git | Content(s) | Format(s)
:---: | :---: | :---: | :---: | :--- | :---: 
E1 | VDM Package | Q1 &#8594; Q3 | VDM | a package that implements the VDM inside a VISTA. Such a package is needed for the VDM Module of deliverable 11 and for the prototypes of 5.4. It would provide a Javascript service for creating, reading, updating and deleting (CRUD) VISTA Data according to the VDM. | Javascript (node.js), MUMPS (KIDS) 
E2 | VMDN Module | Q1 &#8594; Q4 | VDMN | a module that will run inside a VISTA process and map to and from the VDM Package using a set of heuristics | 




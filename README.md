# documents

Cross Project Documentation not hosted on the website

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

# 19 Technical Deliverables

 # | Name | GIT | Schedule
:---: | :---: | :---: | :---
7 | Machine Processable VISTA Data Model (VDM) | VDM | Q1
8 | Date-stamped FileMan Data Model Definitions (cross refs, triggers ...)<sup>2</sup> | VDM | Q1
9 | Approach to “Live VDM” Maintenance of Current State | VDM (wiki) | Q4
&nbsp; |||
10 | Normalized VISTA Data Model (VDMN) | VDMN | 30 days/Continuous - start with VPR domains
11 | (VDMN) Heuristic code | VDMN | 60 days/Continuous
12 | (VDMN) Normalization Reports | VDMN (wiki) | 30 days/Continuous
13 | Website | website, infographics | Q1-Q4
14 | (VDMN) Exposure of older models (schedule, lab ...) report | VDMN (wiki) | 2nd Quarter
&nbsp; |||
15 | Date Stamped (Application) Meta Data | VDM | 3rd Quarter 
&nbsp; |||
18 | Machine-processable (PIKS) Annotations | VDM | 1st Quarter
19 | Software code (for PIKS) | VDM | 1st Quarter
&nbsp; |||
25 | Prototype query access to VISTA Data Against VDM | VDM | 30 days, Continuous 
28 | Prototype Patient-centric Data Security | VDMN | 2nd Quarter
32 | Prototype Web-based Rules Hub | VDMNmap | 2nd Quarter, Continuous
33 | Prototype Web-Based Query Interface to FileMan Data | VDM | 2nd Quarter
&nbsp; |||
35 | VISTA Application model(s)/Prototype(s) | VDMN | 2nd Quarter, Continuous
36A | Meta-model(s) - VPR<sup>1</sup> Test | VDMN | 1st Quarter, Continuous (VPR), 4th Quarter MDWS
39 | Reference model(s)/Prototype(s) | VDMNmap | 3rd Quarter
40 | Document VISTA-ese vs. FHIR | VDMNmap | 3rd Quarter

\# | Name | Schedule/Git | Content(s) | Format(s) | PWS Section | 
:---: | :---: | :---: | :---: | :---: | :--- 
7 | Machine Processable VISTA Data Model (VDM) | Q1 <br><br>VDM  | vdm.jsonld, the native VISTA data model in JSON-LD based on one or more dd.jsonld's<br><br>VDM Maker, a program that creates vdm.jsonld from dd.jsonld's. | JSONLD, Python, Javascript | 5.3.1
8 | Date-stamped FileMan Data Model Implementations (Definitions) (cross refs, triggers ...) | Q1 | dd.jsonld, a data dictionary captured in JSON-LD<br><br>DD Cacher, a program that caches the dictionaries from VISTAs | JSONLD, Python, Javascript | 5.3.1
9 | (Document) Approach to “Live VDM” Maintenance of Current State | Q4 | In a wiki page, describe ways in which dd.jsonld definitions and hence vdm.jsonld could keep pace with changes in VISTAs | Markdown | 5.3.1
&nbsp; |||||
10 | Normalized VISTA Data Model (VDMN) | Q1 -> Q3 | vdmn.jsonld, a formal “VDMN Subset” definition with much of the scope of the VPR RPC | JSON-LD | 5.3.2
11 | (VDMN over VDM) Heuristic (mapping) code | Q1 -> Q3 | mapping tables and rules built over the course of the project in the VDMN module to enable expanding VDMN to VDM mapping | Javascript, JSON | 5.3.2
12 | (VDMN) Normalization Reports | Q1 -> Q3 | Documents VDM to VDMN mapping as implemented in Deliverable 11 in a git wiki | Markdown | 5.3.2
13 | Website | Q1 -> Q4 | website, infographics to showcase the contents of the VDM and VDMN Subset | HTML, Javascript (d3.js) | 5.3.2
14 | Document (VDMN ) exposure of older models (schedule, lab ...) report | Q3 | describe how older, cruder models could be handled in the VDMN | Markdown | 5.3.2
&nbsp; |||||
15 | Date Stamped (Application) Meta Data for lab, surgery and other applications | Q2 | Meta Data Cacher that queries meta-data using the VDM package. The results will be hosted on the project’s github. | Python, JSON-LD | 5.3.3
&nbsp; |||||
18 | Machine-processable (PIKS) Annotations | Q2 | Enables Patient-centric security (#28), distinguished patient from other types of data | JSON-LD | 5.3.4
19 | Software code (for PIKS) | Q2 | Generate the annotations | Python | 5.3.4
&nbsp; |||||






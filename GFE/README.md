## Government Furnished Equipment and Information

As presently stated in the PWS, within 30 days of contract award the Government will provide access to:

#### VISTA Versions / Components

VISTA | PHI | PJITC<br>Security<br>Level | Notes
--- |--- | --- | ---
VISTA: <br>DD Extracts  | NO | .COM | Data Dictionary (DD) extracts from at least five current operational VISTA systems. These data dictionaries contain no patient data, PHI, or PII (i.e., no sensitive information).  These DD are automatically extracted from any VISTA instance and converted to the JSON-LD form using the "DDJLD Maker" routine, seen on the architectural diagram [here](https://github.com/vistadataproject/documents/blob/master/README.md)
VISTA: <br>Master | NO | .COM | Current authoritative Master ("Platinum") version of VISTA as maintained internally by the VA. Metadata from this must be complete and without any alterations or redactions. The metadata does not contain any patient data, PHI, or PII (i.e., no sensitive information).
VISTA: <br>Test Patients | NO | .COM | Copy of a VISTA with test patients used by VA for internal projects.
VISTA:<br> De-identified | NO | .COM | A VISTA with real but de-identified patient data. 
VISTA: <br>Production | YES | NIPRNET |Copy of at least one real operational VISTA ("Production Clone" or “Test VISTA”). This will be kept within the NIPR network, as it will have non de-identified patient data.


In addition, the Project requests the additional GFE and GFI be provided within 30 days of contract award to successfully execute the Project:

#### VISTA Dependencies

Item | Notes
---- | ----
VPR RPC | A copy of the latest version of the VPR RPC software and documentation.
Fileman Namespaces Listing | The latest copy of the FileMan namespace spreadsheet.
New Fileman Namespace | A FileMan namespace exclusively for the Team to allow for the creation of Project files and fields in FileMan.
Integration Agreements | Access to the most up-to-date VISTA Integrations Agreements (sometimes called IAs), or Database Administrator Integration Agreements (DBIAs).
Cache Licenses | Sufficient InterSystems Cache licenses to host FileMan Test VISTA systems.
Sandbox account | VA VISTA Sandbox Account with full Linux VM.

In the absence of Government written disagreement as to the provision of the above stated GFE/GFI, the Team will understand that such GFE/GFI will be delivered within 30 days of contract award.

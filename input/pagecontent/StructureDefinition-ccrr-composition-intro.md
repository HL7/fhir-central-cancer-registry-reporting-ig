### Introduction

This profile is used to represent the Central Cancer Registry Report Composition resource. The Composition resource is used as part of the Central Cancer Registry Reporting Content Bundle. The Composition resource is used to organize the information into different sections so that the receiver of the data can consume the data easily.

#### Profiles from Other IGs used as part of the Composition

The content is made up data elements from the following profiles from the other IGs as direct references or as base profiles.

From the Cancer Pathology Data Sharing IG:
* [US Pathology Diagnostic Report]({{site.data.fhir.ver.cancerpathIg}}/StructureDefinition-us-pathology-diagnostic-report.html)
* [US Pathology Related PractitionerRoles]({{site.data.fhir.ver.cancerpathIg}}/StructureDefinition-us-pathology-related-practitioner-role.html)

From the mCODE IG:

* [mCODE Secondary Cancer Condition Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-secondary-cancer-condition.html)
* [mCODE Cancer Stage Group Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-stage-group.html)
* [mCODE TNM Distant Metastases Category Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-distant-metastases-category.html)
* [mCODE TNM Primary Tumor Category Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-primary-tumor-category.html)
* [mCODE TNM Regional Nodes Category Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-regional-nodes-category.html)
* [mCODE Cancer-Related Medication Request Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-cancer-related-medication-request.html)
* [mCODE Cancer-Related Administration Request Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-cancer-related-medication-administration.html)
* [mCODE Radiotherapy Course Summary Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-radiotherapy-course-summary.html)

From ODH IG:

* [Occupation Data for Health Usual Work Profile]({{site.data.fhir.ver.odhIg}}/StructureDefinition-odh-UsualWork.html)

From US Core IG:

* [US Core AllergyIntolerance Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-allergyintolerance.html)
* [US Core CarePlan Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-careplan.html)
* [US Core Condition Encounter Diagnosis Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-condition-encounter-diagnosis.html)
* [US Core Condition Problems and Health Concerns Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-condition-problems-health-concerns.html)
* [US Core DiagnosticReport Profile for Laboratory Results Reporting]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-diagnosticreport-lab.html)
* [US Core DiagnosticReport Profile for Report and Note Exchange]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-diagnosticreport-note.html)
* [US Core DocumentReference Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-documentreference.html)
* [US Core Encounter Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-encounter.html)
* [US Core Laboratory Result Observation Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-observation-lab.html)
* [US Core Medication Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-medication.html)
* [US Core Patient Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-patient.html)
* [US Core Practitioner Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-practitioner.html)
* [US Core PractitionerRole Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-practitionerrole.html)
* [US Core Procedure Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-procedure.html)
* [US Core ServiceRequest Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-servicerequest.html)
* [US Core Smoking Status Observation Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-smokingstatus.html)
* [US Core Vital Signs Profile]({{site.data.fhir.ver.uscoreR4}}/StructureDefinition-us-core-vital-signs.html)

#### Guidance on populating the data for each section:

The following guidance is provided to the implementers to identify the data of interest which needs to be extracted and populated in the various sections.

* Patient: The Patient who is the subject of the closed encounter.
* Encounter: The Encounter that triggered the report (i.e., closed encounter).
* Primary Cancer Condition Section: Condition with a category of "encounter-diagnosis" for the closed encounter with a Condition.code value that is on the reportability list. All Conditions that do not have a clinicalStatus of inactive can be considered to determine the primary cancer condition along with a verificationStatus of confirmed.
* Secondary Cancer Condition Section: Condition with a category of "encounter-diagnosis" for the closed encounter with a Condition.code that is present in the Secondary Cancer Disorder Value Set. All Conditions that do not have a clinicalStatus of inactive can be considered to determine the secondary cancer condition along with a verificationStatus of confirmed.
* Cancer Stage Group Section: Observation with the Cancer Stage Group information and a status of final, amended, or corrected.
* TNM Primary Tumor Category: Observation with TNM tumor information having a status of final, amended, or corrected.
* TNM Regional Nodes Category: Observation with TNM Regional Nodes information having a status of final, amended, or corrected.
* TNM Distant Metastases Category: Observation with TNM Metastases information having a status of final, amended, or corrected.
* Radiotherapy Course Summary Section: Procedures with the radiotherapy course summary information having a status of completed, not-done, stopped, entered-in-error, unknown and a category of 108290001-Radiation Oncology and/or Radiotherapy (Procedure).
* Problems Section: Underlying medical conditions and active problems. All Conditions that do not have a clinicalStatus of inactive and verificationStatus of confirmed.
* Allergies Section: Allergies associated with the patient with status of active and verification status of confirmed.
* Medications Administered Section: Cancer-related medications administered during the closed encounter with a status of completed, in-progress, entered-in-error, stopped or unknown.
* Medications Section: Medications referenced by MedicationRequest and MedicationAdministration.
* ODH Section: Usual Work information for the patient with a status of final.
* Results Section: Results linked to the encounter or ordered during the encounter or results received during the encounter with a status of final.
* Notes Section: DiagnosticReports and Documents created during the encounter with a status of current or final.
* Procedures Section: Procedures performed during the closed encounter limited to status of completed or unknown.
* Plan of Treatment Section: Cancer-related medications requested during the closed encounter with a status of active, completed, cancelled, entered-in-error, stopped, unknown and an intent of order. Service requests and care plan...
* Vital Signs: All vital signs for the encounter with status of final, corrected, unknown or amended.
* Social History Section: Smoking status associated with the patient with status of final.
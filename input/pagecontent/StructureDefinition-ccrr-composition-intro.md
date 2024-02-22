### Introduction

This profile is used to represent the Central Cancer Registry Report Composition resource. The Composition resource is used as part of the Central Cancer Registry Reporting Content Bundle. The Composition resource is used to organize the information into different sections so that the receiver of the data can consume the data easily.

#### Profiles from Other IGs used as part of the Composition

The content is made up data elements from the following profiles from the other IGs as direct references or as base profiles.

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

[Occupation Data for Health Usual Work Profile]({{site.data.fhir.ver.odhIg}}/StructureDefinition-odh-UsualWork.html)

From US Core IG:

[US Core profiles]({{site.data.fhir.ver.uscoreR4}}/profiles-and-extensions.html)

#### Guidance on populating the data for each section:

The following guidance is provided to the implementers to identify the data of interest which needs to be extracted and populated in the various sections.

* Patient: The Patient who is the subject of the closed encounter
* Encounter: The encounter that triggered the HDEA (i.e., closed encounter)
* Primary Cancer Condition: Condition with a category of "encounter-diagnosis" for the closed encounter with a Condition.code value that is on the reportability list.All Conditions with do not have a clinicalStatuses of inactive can be considered to determine the primary cancer condition along with a verificationStatus of confirmed.
* Secondary Cancer Condition: Condition with a category of "encounter-diagnosis" for the closed encounter with a Condition.code that is present in the Secondary Cancer Disorder Value Set.All Conditions with do not have a clinicalStatuses of inactive can be considered to determine the primary cancer condition along with a verificationStatus of Confirmed.
* Cancer Stage Group: All Observations with the Cancer Stage Group information and a status of final, amended, or corrected
* TNM Primary Tumor Category: All Observation with TNM tumor information having a status of final, amended, or corrected
* TNM Regional Nodes Category: All Observation with TNM Regional Nodes information having a status of final, amended, or corrected
* TNM Distant Metastases Category: All Observation with TNM Metastases information having a status of final, amended, or corrected
* Radiotherapy Course Summary: All Procedures with the Radiotherapy course summary information having a status of completed, not-done, stopped, entered-in-error, unknown and a category of 108290001-Radiation Oncology and/or Radiotherapy (Procedure).
* Cancer-Related Medication Request: Medications requested during the closed encounter with a status of active, completed, cancelled, entered-in-error, stopped, unknown and an intent of order.
* Cancer-Related Medication Administration: Medications administered during the closed encounter with a status of completed, in-progress, entered-in-error, stopped or unknown.
* Usual Work: Usual Work information for the patient with a status of final.
* Laboratory Resul : Results linked to the encounter or ordered during the encounter or results received during the Encounter with a status of final
* Vital Signs: All vital signs for the encounter with status of final, corrected, unknown or amended
* Procedure: Procedures performed during the closed encounter limited to status of completed or unknown.
* DiagnosticReport Profile for Laboratory Results Reporting: Results linked to the encounter or ordered during the encounter or results received during the Encounter and Status of final
* DiagnosticReport Profile for Report and Note exchange: Results linked to the encounter or ordered during the encounter or results received during the Encounter and Status of final
* DocumentReference: All notes created during the encounter with a status of current
* Smoking Status: Smoking Status associated with the patient with status of final.


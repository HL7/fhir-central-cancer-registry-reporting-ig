### Background to Cancer Reporting in the USA

Population-based cancer surveillance is critical in North America for cancer control activities aimed at reducing the morbidity and mortality of cancer, the second leading cause of death in the United States (U.S.).  Population-based public health central cancer registries across the U.S. are mandated to collect complete and timely cancer diagnostic, treatment, and outcome data from hospitals, physician offices, treatment centers, clinics, laboratories, and other sources. Recent shifts in cancer treatment from hospital settings towards ambulatory healthcare settings are increasing the importance of ambulatory (non-hospital) healthcare providers (e.g., non-hospital, non-laboratory health care practitioner, physician or dental office, ambulatory surgery center, cancer treatment center, etc.) authorized/required to report a cancer case to the public health central cancer registry for cancer surveillance.

Regional, state and territorial public health central cancer registries collect, manage, and analyze data about cancer cases and cancer deaths. Cancer surveillance is a complex system that captures longitudinal data from multiple data sources using a variety of methods. In addition to recording the occurrence of each reportable cancer (or tumor), the reporters provide information to public health central cancer registries on the diagnosis, treatment and vital status. Reporting requirements may vary by hospital, state, district, territory, or province. Please note for the purposes of this implementation guide the term, “reportable cancer” is inclusive of all tumors reportable to a public health central cancer registry. The [North American Association of Central Cancer Registries (NAACCR) Standards for Cancer Registries, Data Standards and Data Dictionary](https://apps.naaccr.org/data-dictionary/data-dictionary), describes the standards of tumor reportability for national standard-setting organizations in North America.

Public health central cancer registry data are used for surveillance, development of comprehensive cancer control programs, and healthcare planning and interventions. Improved accuracy and completeness of cancer surveillance data impacts all areas of public health interventions. Data also provides baseline and performance measures for cancer-related interventions designed to reduce cancer incidence or improve early detection. Identification of disparities among various population subgroups in stage at diagnosis or in treatment received can inform interventions to reduce these disparities and reduce the cancer morbidity and mortality in minority or disadvantaged populations.

The National Program of Cancer Registries (NPCR), established in 1992 by the U.S. Congress with enactment of the Cancer Registries Amendment Act (Public Law 202-515), is funded and managed by the Centers for Disease Control and Prevention’s (CDC) Cancer Surveillance Branch (CSB) in the Division of Cancer Prevention and Control (DCPC). The Surveillance Epidemiology and End Results (SEER) Program of the National Cancer Institute (NCI), initiated by the National Cancer Act of 1971 (PL 92-218), began collecting population-based cancer incidence data in 1973. Together, NPCR and SEER programs collect data for the entire U.S. population and produce the annual United States Cancer Statistics (USCS). CDC and NCI monitor the burden of cancer, including disparities among various population subgroups and provide data for research, evaluation of cancer control activities, and planning for future healthcare needs at both the state and national levels. Complete and high-quality cancer reporting traditionally relies primarily on data from acute care hospitals and, more recently, pathology laboratories.  

Advances in medicine and changes in the healthcare delivery system now allow patients to obtain their care outside the acute care hospital setting. Data collection systems from ambulatory healthcare providers such as physician offices and radiation therapy centers are not as standardized or complete with respect to reporting of cancer occurrences and treatment. When reporting does occur, it may be through a manual process of identifying reportable cases and submitting paper copies of the medical record, or the central registry may send certified tumor registrars (CTRs) to ambulatory healthcare provider offices to abstract the information manually or electronically from the paper-based medical records. The [Health Level 7 (HL7) Clinical Document Architecture (CDA®) Release 2 Implementation Guide (IG): Reporting to Public Health Cancer Registries from Ambulatory Healthcare Providers, Release 1, DSTU Release 1.1 – US Realm](https://www.hl7.org/implement/standards/product_brief.cfm?product_id=398) is the first standard for ambulatory care to use when electronically transmitting cancer cases to the central cancer registry. The CDA IG is part of the Office of the National Coordinator (ONC) Meaningful Use and identifies the content and structure for reporting from physician electronic health records (EHRs) to central cancer registries (CCRs), but it does not use HL7 Fast Healthcare Interoperability Resources (FHIR®). These processes are very resource intensive, time-consuming, prone to errors in transcription, and inherently less secure. This leads to under-reporting of certain types of cancers, especially those now diagnosed and treated primarily outside of hospitals, such as in dermatology, urology, and hematology, as well as under-reporting of treatment information across most types of cancer.

Standards specifications provided in this document are designed to facilitate the implementation of an automated electronic process for the identification and reporting of cancer cases, treatment, and outcomes using ambulatory healthcare provider EHR systems to create a cancer event report and submit it to public health central cancer registries. Automated electronic reporting is expected to reduce labor (for the ambulatory healthcare providers and public health central cancer registries), and increase the security, completeness, timeliness and accuracy of cancer surveillance data.


### Legal Mandate for Cancer Reporting 

Cancer reporting from all healthcare providers (e.g., hospital, laboratory and ambulatory) for public health surveillance is mandated at the state and territory level. Legislation requiring cancer reporting by healthcare providers exists in all states with some variation in specific requirements. United States federal law Public Health Service Act (42 USC 280e-280e-4; Public Law 102-515), as amended, authorizing the National Program of Cancer Registries, specifies that each federally-funded registry must have a legislative "means for the statewide cancer registry to access all records of physicians and surgeons, hospitals, outpatient clinics, nursing homes, and all other facilities…”. The [National Cancer Act of 1971 (Public Law 92-218)](https://www.congress.gov/92/statute/STATUTE-85/STATUTE-85-Pg778-3.pdf) gives the Director of NCI the authority to “collect, analyze, and disseminate all data useful in the prevention, diagnosis and treatment of cancer.”

#### HIPAA Regulation
The Health Insurance Portability and Accountability Act (HIPAA, or the Act), P.L. 104-191, enacted on August 21, 1996, includes provisions related to insurance coverage and a section that is relevant to electronic reporting of healthcare information. The regulation implementing the HIPAA privacy provisions allows public health exemptions for disclosure without patient consent of individually identifiable health information.
A [discussion of HIPAA as it relates to reporting to Cancer Registries](https://www.naaccr.org/?s=HIPAA) outlines details relating to HIPAA and cancer reporting.


### Use Case
The section identifies the need and specific details of central cancer registry reporting.

Cancer is a mandatory reportable disease; every state has public health law/regulation requiring information to be reported to a central cancer registry about all cancers diagnosed or treated within that state. Central cancer registries are population-based cancer registries that collect data on all cancer diagnosed in residents in a defined geographic area.  The main sources of information include information from treatment facilities (e.g., hospitals, clinics/physician offices), diagnostic services (e.g., pathology laboratories) and vital statistics (e.g., death certificates). Central cancer registries have an emphasis on epidemiology and public health to determine patterns among various populations, monitor cancer trends over time, guide planning and evaluation of cancer control efforts, help prioritize health resource allocations and to advance clinical, epidemiologic and health services research <sup>1</sup>. 

#### Problem Statement
Although cancer reporting for public health surveillance is mandatory, certain types of cancers, treatments, and biomarkers are currently underreported to central cancer registries. This underreporting is because more patients are being diagnosed or treated outside of a hospital setting, such as in ambulatory clinical practices (dermatology, gastroenterology, urology, hematology, etc.). Due to lack of interoperability, these disparate systems are challenged with reporting complete and timely data in a standardized format to cancer registries, and subsequently manual processes are necessary to obtain and process often incomplete data to meet surveillance reporting requirements. Even with reporting requirements, cancer surveillance is complex given the heterogeneous nature of the disease, numerous diagnostic and prognostic factors, and multiple medical encounters that produce data from a variety of non-harmonized data sources.

Challenges include:
* Inability to identify which patient diagnoses and encounters require reporting
* A lack of data in discrete fields (e.g., narrative blob text fields, PDF documents)
* Issues with data flow 
* Delays in data availability 
* Managing proper timing of creating and transmitting reports
* A lack of standardized systems for cancer data collection and reporting (in some cases)


These challenges make it difficult for registries to synthesize information in a timely and actionable way. Automation of cancer case registry reporting will reduce the burden of manual or other non-standardized data collection processes that currently exist.

#### Use Case Goals
The goal of the Central Cancer Registry Reporting Content IG is to automate the capture of cancer cases and cancer treatment information and provide incidence data faster for research and public health. The Central Cancer Registry Reporting Content IG will leverage existing FHIR® infrastructure to transmit cancer case information primarily from ambulatory care practices to central cancer registries. Additionally, this use case aims to identify data standards that allow for the collection and transmission of these data electronically from EHRs automatically rather than relying on labor-intensive manual processes and duplications of effort.


#### Scope of the Use Case

**In-Scope**

* Collect standardized data on all types of reportable cancers diagnosed and/or treated
* Define under what circumstances an EHR system must create and transmit a cancer report to the central cancer registry
* Identify the data elements to be retrieved from the EHR to produce the cancer report


**Out-of-Scope**

* Validation of the EHR data
* Data captured outside the EHR and communicated directly to registries
* Changes to existing provider workflow or existing data entry
* Policies of the clinical care setting to collect consent for data sharing
* Integrating claims data into the trigger event to send a report to the cancer registries

 
#### Use Case Triggers and Reporting
To limit the number of reports sent to registries, this IG contains specific reporting intervals and criteria for both encounter-based and content-based triggering of when a report is sent to a Central Cancer Registry (CCR).

For the **initial report (T0)**, when a qualifying encounter occurs, the patient record will be queried at 15 days post-encounter and (if necessary) 30 days post encounter for the presence of the following content:

* Patient Last Name
* Patient First Name
* Patient Address State
* Primary Laterality
* Primary Cancer Condition: Condition with a category of “encounter-diagnosis” for the closed encounter with a Condition.code value that is on the reportability list. All Conditions that have a clinicalStatus of active can be considered to determine the primary cancer condition along with a verificationStatus of confirmed.
* Date of Diagnosis
* Diagnostic Confirmation
* Behavior
* Primary Site
* Histology
* Clinical Status
* Date of birth 
* Facility Identifier or Facility Name

If all content is present at the 15 day check, then a full report (i.e., all profiles) will be sent to the registry. If any of the content is missing, a full report will be sent at T0+30 days regardless of content status.

The intent of this report is to initiate an incidence case.

**Between T0 and T0+12 months**, incremental reports containing patient information and new information will be sent based on availability of specific content. The following additions to the patient record will trigger an incremental report:
* Non-encounter based triggers: If any information is added or updated for the following resources, then a report will be sent regardless of if the information is tied to an encounter.
	* Primary Cancer Condition
	* Cancer Stage Group: All Observations with the Cancer Stage Group information and having a status of final, amended, or corrected.
	* TNM Primary Tumor Category: All Observations with TNM tumor information having a status of final, amended, or corrected.
	* TNM Regional Nodes Category: All Observations with TNM regional nodes information having a status of final, amended, or corrected.
	* TNM Distant Metastases Category: All Observations with TNM metastases information having a status of final, amended, or corrected.
	* Radiotherapy Course Summary: All Procedures with the radiotherapy course summary information having a status of completed, not-done, stopped, entered-in-error, unknown and a category of 108290001-Radiation Oncology and/or Radiotherapy (Procedure).
* Encounter-based triggers: For any encounter that meets the reportability criteria AND contains new information for the following data elements:
	* Procedure: Procedures performed during the closed encounter with a status of completed or unknown.
	* DiagnosticReport Profile for Laboratory Results Reporting: Results linked to the encounter or results received during the encounter with a status of final.
	* DiagnosticReport Profile for Report and Note exchange: Results linked to the encounter or results received during the encounter with a status of final.

A full report, containing multiple encounter information/any non-encounter-based information, will be sent at **T0+12 months**, **T0+24 months**, **T0+36 months**, and **T0+48 months** if there has been at least one encounter or content trigger criteria met during this time. If no trigger criteria have been met, then no report will be sent. After 12 consecutive months of no trigger criteria or upon patient death, reporting will stop.

**NOTE:** Central Cancer Registry Reporting is tumor-based, not patient-based. Every tumor will have its own triggering and reporting timeline.

Figure 2.1 below illustrates a sample central cancer registry reporting timeline.

{% include img.html img="ccrr-bundle-sending-timeline.png" caption="Figure 2.1 - Central Cancer Registry Reporting Timeline" %}

#### Use Case Actors and Interactions

##### Central Cancer Registry Reporting Actors and Definitions 

* Provider: A person who delivers health care to a patient. In addition to delivering care, the provider also updates patient data and signs off on the content added, deleted, or modified in the patient record once it is updated. The provider can be the individual doctor, nurse, or a combination of different people that are part of the care team.
* Data Source (e.g., Electronic Health Record (EHR), Health Information Exchange (HIE)): A system that is used in a health care organization to capture, store patient data and make the data available securely with authorized users. The most widely used Data Source is the EHR system, however other systems such as an HIE can serve as a Data Source. FHIR APIs can be used to extract data from the data source, process, package the data as needed, and then submit the data to the Data Receiver (e.g., Central Cancer Registry (CCR)).
* Data Submitter (e.g., eCR Now App): A system responsible for extracting the data and submitting that data to the Data Receiver.
* Data Receiver (e.g., Central Cancer Registry): A system that receives and stores the data. 

##### Interactions between Actors and Systems for Central Cancer Registry Reporting 
This section outlines the high-level interactions between the various actors and systems listed above. 

Figure 2.2 below depicts the interactions between actors and systems when the Data Submitter is part of the Data Source Organization. 

{% include img.html img="ccrr-ig-actors-systems.png" caption="Figure 2.2 - Central Cancer Registry Reporting Actors and Systems" %}

The descriptions for each step in the above diagram include:
* Step 1: The Data Submitter creates a notification (e.g., subscription, CDS hook, v2 message) in the Data Source’s FHIR server so that it can be notified when specific events occur in the clinical workflow. 
* Step 2: The Provider, as part of its clinical workflow, update the patient’s data in the Data Source.
* Step 3: The Data Source notifies the Data Submitter based on notifications created in Step 1.
* Step 4: The Data Submitter queries the Data Source for the patient’s data.
* Step 4a: The Data Submitter receives the response from the Data Source with the patient’s data.
* Step 5: The Data Submitter evaluates the data and creates the report if criteria are met.
* Step 6: When a report is generated, the Data Submitter submits the created report to the Data Receiver.

Figure 2.3 below depicts the interactions between actors and systems when the Data Submitter is integrated with the Data Source. 

{% include img.html img="ccrr-ig-actors-systems-2.png" caption="Figure 2.3 - Central Cancer Registry Reporting Actors and Systems when the Data Submitter is integrated with the Data Source" %}

The descriptions for each step in the above diagram include:
* Step 1: A Provider as part of their clinical workflow updates the data in the Data Source’s patient chart.
* Step 2: The Data Submitter which is part of the Data Source evaluates the data and creates the report if criteria is met.
* Step 3: When a report is generated, the Data Submitter submits the created report to the Data Receiver.


#### Central Cancer Registry Reporting ValueSets

The CDC Central Cancer Registry Program has identified the list of conditions against which the patient's data is evaluated for reporting purposes. If a patient has any of the conditions listed in any of the value sets identified below, the patient's data qualifies for reporting to the central cancer registry. These are not explicitly included in the IG as they will be maintained externally.

{% include CancerReportingValueSetList.html %}
 
 
- - - -


<sup>1</sup>  Menck, H., Gress, D. and Griffin, A., 2011. Cancer Registry Management Principles and Practices for Hospitals and Central Registries. 3rd ed. Dubuque, IA: Kendall Hunt.  ISBN: 978-0-7575-6900-5.

### Background to Cancer Reporting in the USA

Population-based cancer surveillance is critical in North America for cancer control activities aimed at reducing the morbidity and mortality of cancer, the second leading cause of death in the United States (U.S.).  Population-based public health central cancer registries across the U.S. are mandated to collect complete and timely cancer diagnostic, treatment, and outcome data from hospitals, physician offices, treatment centers, clinics, laboratories, and other sources. Recent shifts in cancer treatment away from hospital settings and towards ambulatory healthcare settings are increasing the importance of ambulatory (non-hospital) healthcare providers **(NOTE 1)**  data for cancer surveillance.

Regional, state and territorial public health central cancer registries collect, manage, and analyze data about cancer cases and cancer deaths. Cancer surveillance is a complex system that captures longitudinal data from multiple data sources using a variety of methods. In addition to recording the occurrence of each reportable cancer (or tumor), the reporters provide information to public health central cancer registries on the diagnosis, treatment and vital status. Reporting requirements may vary by hospital, state, district, territory, or province. Please note for the purposes of this implementation guide the term, “reportable cancer” is inclusive of all tumors reportable to a public health central cancer registry. The [North American Association of Central Cancer Registries (NAACCR) Standards for Cancer Registries, Volume II, Data Standards and Data Dictionary](http://www.naaccr.org/StandardsandRegistryOperations/VolumeII.aspx), describes the standards of tumor reportability for national standard-setting organizations in North America.

Public health central cancer registry data are used for surveillance, development of comprehensive cancer control programs, and healthcare planning and interventions. Improved accuracy and completeness of cancer surveillance data impacts all areas of public health interventions. Data also provide baseline measures and performance measures for cancer-related interventions designed to reduce cancer incidence or improve early detection. Identification of disparities among various population subgroups in stage at diagnosis or in treatment received can inform interventions to reduce these disparities and reduce the cancer morbidity and mortality in minority or disadvantaged populations.
The National Program of Cancer Registries (NPCR), established in 1992 by the U.S. Congress with enactment of the Cancer Registries Amendment Act (Public Law 202-515), is funded and managed by the Centers for Disease Control and Prevention’s (CDC) Cancer Surveillance Branch (CSB) in the Division of Cancer Prevention and Control (DCPC). The Surveillance Epidemiology and End Results (SEER) Program of the National Cancer Institute (NCI), initiated by the National Cancer Act of 1971 (PL 92-218), began collecting population-based cancer incidence data in 1973. Together, NPCR and SEER programs collect data for the entire U.S. population and produce the annual United States Cancer Statistics (USCS). CDC and NCI build state and national capacity to monitor the burden of cancer, including disparities among various population subgroups, and provide data for research, evaluation of cancer control activities, and planning for future healthcare needs. Complete and high-quality cancer reporting has traditionally relied primarily on data from acute care hospitals and, more recently, pathology laboratories.  

Advances in medicine and changes in the healthcare delivery system now allow patients to obtain their care outside the acute care hospital setting. Data collection systems from ambulatory healthcare providers such as physician offices and radiation therapy centers are not as standardized or complete with reporting of cancer occurrences and treatment. When reporting does occur, it may be through a manual process of identifying reportable cases and submitting paper copies of the medical record, or the central registry may send certified tumor registrars (CTRs) to ambulatory healthcare provider offices to manually or electronically abstract the information from the paper-based medical records. 
These processes are very resource intensive, time-consuming, prone to errors in transcription, and inherently less secure. This leads to under-reporting of certain types of cancers, especially those now diagnosed and treated primarily outside of hospitals, such as in dermatology, urology, and hematology, as well as under-reporting of treatment information across most types of cancer.

Standards specifications provided in this document are designed to facilitate the implementation of an automated electronic process for the identification and reporting of cancer cases, treatment, and outcomes using ambulatory healthcare provider EHR systems to create a cancer event report and submit it to public health central cancer registries. Automated electronic reporting is expected to reduce labor (for the ambulatory healthcare providers and public health central cancer registries), and increase the security, completeness, timeliness and accuracy of cancer surveillance data.

**NOTE 1** 
For purposes of this document, ambulatory healthcare provider has been defined as any non-hospital, non-laboratory health care practitioner, e.g., physician or dental office, ambulatory surgery center, cancer treatment center, etc. that would be authorized to report a cancer case to the central cancer registry.


### Legal Mandate for Cancer Reporting 

Cancer reporting from all healthcare providers (e.g., hospital, laboratory and ambulatory) for public health surveillance is mandated at the state and territory level. Legislation requiring cancer reporting by healthcare providers exists in all states with some variation in specific requirements. United States federal law Public Health Service Act (42 USC 280e-280e-4; Public Law 102-515), as amended.), authorizing the National Program of Cancer Registries, specifies that each federally-funded registry must have a legislative "means for the statewide cancer registry to access all records of physicians and surgeons, hospitals, outpatient clinics, nursing homes, and all other facilities…”.The [National Cancer Act of 1971 (Public Law 92-218)](http://legislative.cancer.gov/history/phsa/1971) gives the Director of NCI the authority to “collect, analyze, and disseminate all data useful in the prevention, diagnosis and treatment of cancer.”

#### HIPAA:
The Health Insurance Portability and Accountability Act (HIPAA, or the Act), P.L. 104-191, enacted on August 21, 1996, includes provisions related to insurance coverage and a section that is relevant to electronic reporting of healthcare information. The regulation implementing the HIPAA privacy provisions allows public health exemptions for disclosure without patient consent of individually identifiable health information.
A [discussion of HIPAA as it relates to reporting to Cancer Registries](http://www.naaccr.org/Research/HIPAA.aspx) outlines details relating to HIPAA and cancer reporting.


### Business Need and User Stories
The section identifies the business needs and specific user stories outlining the central cancer registry reporting data exchange needs.

#### Use Case Goals
The purpose of the use case is to transmit cancer case information to state Central Cancer Registries. The intent is to provide access to data not currently available, or available through non-standard and/or manual methods; it will not replace hospital registry reporting methods that are working well. The cancer use case will help assess how to address the gaps in workflow and triggers, and the ability to leverage MedMorph RA IG along with other existing HL7 FHIR Implementation Guides to address the public health information needs.

#### Problem Statement
Cancer is a mandatory reportable disease; every state has public health law/regulation requiring information to be reported to a central cancer registry about all cancers diagnosed or treated within that state. Central cancer registries are population-based cancer registries that collect data on all cancer cases in a defined population.  The main sources of information include information from treatment facilities (e.g., hospitals, clinics/physician offices), diagnostic services (e.g., pathology laboratories) and vital statistics (e.g., death certificates). Central cancer registries have an emphasis on epidemiology and public health to determine patterns among various populations, monitor cancer trends over time, guide planning and evaluation of cancer control efforts, help prioritize health resource allocations and to advance clinical, epidemiologic and health services research.[1]  Even with reporting requirements, cancer surveillance is complex given the heterogeneous nature of the disease, numerous diagnostic and prognostic factors, and multiple medical encounters that produce data from a variety of non-harmonized data sources.

Challenges include:
* Issues with data flow 
* Delays in data availability 
* A lack of standardized systems for cancer data collection and reporting (in some cases)


These challenges make it difficult for registries to synthesize information in a timely and actionable way. Automation of cancer case registry reporting will reduce the burden of manual or other non-standardized data collection processes that currently exist.


#### Goals of the Use Case

The goal of the Central Cancer Registry Reporting Content IG is to automate capture cases of cancer and cancer treatment information not reported by other sources and provide incidence data faster for research and public health. It will leverage MedMorph RA IG and other existing FHIR infrastructure to transmit cancer case information primarily from ambulatory care practices to central cancer registries. This Use case will not replace hospital registry reporting methods which are working well.  Additionally, this use case aims to identify data standards that allow for the collection and transmission of these data electronically from EHRs automatically rather than relying on labor-intensive manual processes and duplications of effort.

##### Scope of the Use Case

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

 
#### **User Story #1: Cancer Diagnosis and Treatment Reporting based on Specific Criteria** 
A patient visits her primary care provider (PCP) because of a lump in her breast. The provider orders a mammogram and then a biopsy that is sent to the pathology laboratory for testing. The laboratory analyzes the biopsy specimen which indicates the patient has breast cancer. The pathology report is sent to the provider who ordered the biopsy. The provider confirms the diagnosis of breast cancer. This information is integrated into the patient's clinical record. The patient is informed of her test results. The PCP’s clinic EHR system determines that the patient has been diagnosed with a cancer that meets the criteria for reporting to the central cancer registry, as defined by the national standard Cancer Reportability List. On January 12, 2022, a standard report with the required data elements is sent to the central cancer registry where the patient resides, as required by state law. On February 2, 2022, the PCP orders a further workup and clinically stages the patient’s cancer. While the EHR system determines that staging information has not been previously submitted to the central cancer registry, it does not meet the  criteria for reporting because it has been staged within six (6) months of the initial report transmitted to the central cancer registry.

The patient has surgery on February 9, 2022, and then PCP refers her to a medical oncologist in the same clinic for further treatment. The medical oncologist sends the patient to the radiation therapy department to initiate radiation therapy as part of the first course of treatment for her breast cancer. Radiation therapy is given through September 29, 2022 and is documented in the EHR as the reason for the encounter/visit. The EHR system determines that the patient was seen for treatment of a cancer that meets the criteria for reporting to the central cancer registry and is more than six (6) months after the initial diagnosis was transmitted to the central cancer registry.. A standard report with the required data elements is sent to the central cancer registry where the patient resides, as required by state law.

After radiation was completed on September 29, 2022, the medical oncologist initiates the chemotherapy regimen on October 10, 2022, as part of the first course of treatment for her breast cancer. The chemotherapy drugs are infused, and the chemotherapy treatment is documented in the EHR as the reason for the encounter/visit. The EHR system determines that the patient was seen for treatment of a cancer that meets the criteria for reporting to the central cancer registry, however, it does not meet the criteria for transmitting to the central registry because it has been added to the EHR between 6 months and 12 months of the initial diagnosis and transmission of a cancer report. 
 
After 12 months from the initial diagnosis and transmission of a cancer report to the central cancer registry, the EHR generates and sends a standard report with data elements to the central cancer registry where the patient resides.
At every subsequent 12 months after the initial diagnosis and transmission of a cancer report to the central cancer registry, the EHR generates and sends a standard report with data elements to the central cancer registry where the patient resides, until the patient is recorded as deceased or there have been no updates to the patient’s EHR record.


#### Central Cancer Registry Reporting Workflow 

The following is a diagram of the workflow based on the above user story used for Central Cancer Registry Reporting


{% include img.html img="central-cancer-registry-reporting-workflow.png" caption="Figure 2.1 - Central Cancer Registry Reporting Workflow" %}

<br/>


<br/>


#### Central Cancer Registry Reporting Actors and Definitions

The following actors and definitions from the [MedMorph RA IG]({{site.data.fhir.ver.medmorphIg}}/usecases.html#medmorph-actors-and-definitions) are used by the Central Cancer Registry Reporting use cases. 

* EHR 
* Backend Service App (BSA)
* Central Cancer Registry (PHA)
* Knowledge Artifact Repository (KAR)
* Trusted Third Party (TTP)

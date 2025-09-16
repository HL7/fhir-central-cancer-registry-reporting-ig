This section defines the specific requirements for systems wishing to conform to actors specified in this Central Cancer Registry Reporting Content IG.  The specification focuses on using the eCR Now App (or a vendor developed solutaion) to report cancer data to central cancer registries.

### Context

#### Pre-reading
Before reading this formal specification, implementers should first be familiar with these sections of the specification:

* The [Use Cases](usecases.html) page provides the business context and general process flow enabled by the formal specification.


#### Conventions
This implementation guide uses RFC-2119 terminology to flag statements that have relevance for the evaluation of conformance with the guide:

* **SHALL** indicates requirements that must be met to be conformant with the specification.

* **SHOULD** indicates behaviors that are strongly recommended (and which may result in interoperability issues or sub-optimal behavior if not adhered to), but which do not, for this version of the specification, affect the determination of specification conformance.

* **MAY** describes optional behaviors that are free to consider but where there is no recommendation for or against adoption.


#### Claiming Conformance 

Actors and Systems asserting conformance to this implementation guide have to implement the requirements outlined in the corresponding capability statements. The following definition of MUST SUPPORT is to be used in the implementation of the requirements.

##### MUST SUPPORT Definition

* Systems **SHALL** be capable of populating data elements as specified by the profiles and data elements are returned using the specified APIs in the capability statement.
* Systems **SHALL** be capable of processing resource instances containing the MUST SUPPORT data elements without generating an error or causing the application to fail. In other words, Systems SHOULD be capable of displaying the data elements for human use or storing it for other purposes.
* In situations where information on a particular data element is not present and the reason for absence is unknown, Systems **SHALL NOT** include the data elements in the resource instance returned from executing the API requests.
* When accessing Central Cancer Registry Reporting data, Systems **SHALL** interpret missing data elements within resource instances returned from API requests as data not present.
* When data is not available for any of the mandatory elements specified in the IG, a data absent reason extension should be added to satisfy the requirement along with an appropriate value from the [data-absent-reason value set](http://hl7.org/fhir/ValueSet/data-absent-reason).


#### Profiles and Other IGs Usage
This specification makes significant use of [FHIR profiles]({{site.data.fhir.path}}profiling.html), search parameter definitions, and terminology artifacts to describe the content to be shared as part of Central Cancer Registry Reporting Content IG workflows. The implementation guide is based on [FHIR R4]({{site.data.fhir.path}}) and profiles are listed for each interaction.

The full set of profiles defined in this implementation guide can be found by following the links on the [FHIR Artifacts](artifacts.html) page.

##### US Core Usage

This IG leverages the following [US Core]({{site.data.fhir.ver.uscoreR4}}) profiles defined by HL7 for sharing non-veterinary EMR individual health data in the U.S.  Where US Core profiles exist, this IG either leverages them directly or uses them as a base for any additional constraints needed to support the research use cases.  

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


##### mCode FHIR IG Usage

This IG leverages the [mCode FHIR IG]({{site.data.fhir.ver.mcodeIg}}/index.html) for exchanging cancer specific information which includes the following profiles: 

* [mCODE Primary Cancer Condition Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-primary-cancer-condition.html)
* [mCODE Secondary Cancer Condition Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-secondary-cancer-condition.html)
* [mCODE TNM Stage Group Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-stage-group.html)
* [mCODE TNM Distant Metastases Category Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-distant-metastases-category.html)
* [mCODE TNM Primary Tumor Category Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-primary-tumor-category.html)
* [mCODE TNM Regional Nodes Category Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-tnm-regional-nodes-category.html)
* [mCODE Cancer-Related Medication Request Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-cancer-related-medication-request.html)
* [mCODE Cancer-Related Administration Request Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-cancer-related-medication-administration.html)
* [mCODE Radiotherapy Course Summary Profile]({{site.data.fhir.ver.mcodeIg}}/StructureDefinition-mcode-radiotherapy-course-summary.html)

	
Implementers **SHOULD** use the [mCode Disease characterization guidance]({{site.data.fhir.ver.mcodeIg}}/group-disease.html) and [mCode Treatment guidance]({{site.data.fhir.ver.mcodeIg}}/group-treatment.html) when using the above profiles.

##### Cancer Pathology Data Sharing IG Usage 

This IG leverages the following profiles from the [Cancer Pathology Data Sharing IG]({{site.data.fhir.ver.cancerpathIG}}/index.html) for the extraction of Cancer Pathology Reports from the EHR and include them in the Central Cancer Registry Content Bundle.

* [US Pathology Diagnostic Report Profile]({{site.data.fhir.ver.cancerpathIG}}/StructureDefinition/us-pathology-diagnostic-report.html)

##### Occupational Data for Health (ODH) IG Usage 

This IG leverages the [ODH FHIR IG]({{site.data.fhir.ver.odhIg}}/index.html) for exchanging occupational data for health which includes the following profile:

* [Occupation Data for Health Usual Work Profile]({{site.data.fhir.ver.odhig}}/StructureDefinition/odh-UsualWork.html)

##### Subscriptions Backport IG Usage

This IG leverages the [Subscriptions Backport IG]({{site.data.fhir.ver.subscriptionsIg}}/index.html) defined by HL7 Infrastructure WG for automating reporting workflows using subscriptions when desired in implementations.


#### Implementation Requirements

##### SMART App Launch IG Usage

When utilizing the eCR Now App approach for this use case - this IG leverages the [SMART App Launch IG]({{site.data.fhir.ver.smartapplaunch}}/index.html) defined by HL7 Infrastructure WG for enabling authentication and authorization between various actors involved in the workflows. 
This IG leverages Substitutable Medical Applications, Reusable Technologies (SMART) on FHIR Backend Services Authorization requirements.

##### SMART on FHIR Backend Services Requirements

This section outlines how the SMART on FHIR Backend Services Authorization will be used by this IG.

* The system actors namely Data Source, Data Submitter, and the Data Receiver are required to use the SMART on FHIR Backend Services Authorization mechanisms as outlined below for the following interactions:


    * When the Data Submitter is not packaged within the Data Source, the Data Submitter **SHALL** use the SMART on FHIR Backend Service Authorization to access data from the Data Source  
    * Data Submitter posting data to the Data Receiver **SHALL** use the SMART on FHIR Backend Services Authorization to submit the data.
    

* System actors acting as servers (i.e, Data Source and Data Receiver) **SHALL** advertise conformance to SMART on FHIR Backend Services by hosting Well-Known Uniform Resource Identifiers (URIs) as defined in the [SMART App Launch IG Backend Services]({{site.data.fhir.ver.smartapplaunch}}/backend-services.html) specification.

* System actors acting as servers (i.e, Data Source and Data Receiver) **SHALL** include token_endpoint, scopes_supported, token_endpoint_auth_methods_supported and token_endpoint_auth_signing_alg_values_supported as defined in the [SMART App Launch IG Backend Services]({{site.data.fhir.ver.smartapplaunch}}/backend-services.html) specification.

* When System actors act as clients (i.e, Data Submitter), they **SHALL** share their JSON Web Key Set (JWKS) with the server System actors (i.e, Data Source and Data Receiver) using Uniform Resource Locators (URLs) as defined in the [SMART App Launch IG Backend Services]({{site.data.fhir.ver.smartapplaunch}}/backend-services.html) specification.

* System actors acting as clients **SHALL** obtain the access token as defined in the [SMART App Launch IG Backend Services]({{site.data.fhir.ver.smartapplaunch}}/backend-services.html) specification.

* For the Central Cancer Registry Reporting (CCRR) use case, Data Sources **SHALL** support the system/*.read scopes. 

* The Data Receiver **SHALL** support the system/*.read and system/*.write scopes. 

* The health care organization's existing processes along with the Data Source's authorization server **SHALL** verify any organizational policy requirements (for example, registration of the Data Submitter, authorizing requested scopes, testing and verification of Data Submitter implementation in sandbox environment prior to production) before allowing the Data Submitter to access the data to be included in the CCRR report. 

<!--##### Overall Security Requirements 

Implementations must meet the general security requirements documented in [FHIR Security guidance](http://hl7.org/fhir/security.html). In addition the EHR needs to meet the security requirements as outlined in the [Authentication and Authorization Requirements](spec.html#authentication-and-authorization-requirements) section below.
Implementers of this IG **SHOULD** follow the [HIPPA guidance](https://www.naaccr.org/hippa) to ensure applicable security and privacy laws are implemented.


##### Authentication and Authorization Requirements

This section outlines how the SMART on FHIR Backend Services Authorization will be used by the Central Cancer Registry (CCR) Reporting Content implementation guide. 

* The system actors namely EHR, Health Data Exchange App (backend services app), Trusted Third Party and the Central Cancer Registry are required to conform to the [MedMorph Authentication and Authorization Requirements]({{site.data.fhir.ver.medmorphIg}}/spec.html#authentication-and-authorization-requirements) for the following interactions: 

   * HDEA accessing data from the EHR.
   * HDEA posting data to the Central Cancer Registry data store via the TTP or directly to the Central Cancer Registry.
    
* For the Central Cancer Registry Reporting use cases, EHRs **SHALL** support the system/*.read scopes. 

* The Central Cancer Registry **SHALL** support the system/*.read and system/*.write scopes. 

* The healthcare organization's existing processes along with the EHRs authorization server **SHALL** verify consent and other policy requirements before allowing the HDEA to access the data to be included in the central cancer registry report. 
 

##### Knowledge Artifact and Knowledge Artifact Repository Requirements 

* The Central Cancer Registry **SHALL** create a Knowledge Artifact following the constraints identified by the [MedMorph Provisioning Requirements]({{site.data.fhir.ver.medmorphIg}}/provisioning.html#creating-knowledge-artifacts).

* The Central Cancer Registry **SHALL** publish the value sets required to trigger a cancer report for a patient with an encounter diagnosis of cancer. This can be published in the Central Cancer Registry FHIR Server or a separate Knowledge Artifact Repository.

* The Central Cancer Registry **SHALL** republish the value sets when the list of concepts comprising the value sets change. 

* The Central Cancer Registry **SHALL** create the Knowledge Artifact following the constraints identified in [ccrr-plandefinition](StructureDefinition-ccrr-plandefinition.html).

* The Central Cancer Registry **SHALL** implement the Knowledge Artifact Repository requirements as outlined in the [MedMorph RA Knowledge Artifact Repository Requirements]({{site.data.fhir.ver.medmorphIg}}/CapabilityStatement-medmorph-knowledge-artifact-repository.html).
-->
#### Data Source Requirements

* The Data Source **SHALL** support the requirements as outlined in the [Central Cancer Registry Reporting Data Source Capability Statement](CapabilityStatement-central-cancer-registry-reporting-ehr.html).

##### Authorization Requirements 

* The Data Source **SHALL** support the [SMART on FHIR Backend Services Authorization](spec.html#smart-on-fhir-backend-services-requirements) outlined above as a Server.
 

##### Subscription requirements
The requirements in this sub-section are only applicable if when the Data Submitter is not packaged as part of the Data Source.

* The Data Source **SHALL** support the creation of Subscriptions for the following named events described at [US Public Health Profiles Library IG Trigger Events]({{site.data.fhir.ver.uspublichealthprofileslibraryIg}}/us-ph-valueset-triggerdefinition-namedevent.html).
	
	* Start of an Encounter
	* Close of an Encounter
	

* The Data Source **SHALL** support [``rest-hook``]({{site.data.fhir.path}}subscription.html#2.46.7.1) Subscription channel to notify the Data Submitter.

* The Data Source **SHALL** support Notification Bundles with [``full resource payload``]({{site.data.fhir.ver.subscriptionsIg}}/payloads.html#full-resource) as outlined in the Backport Subscriptions IG. 

* For the CCRR IG, the Data Source **SHALL** include the Encounter resource which was started or closed as part of the Notification Bundle.

* The Data Source **SHALL** support operations and APIs for Subscription, Notification Bundle, Subscription status resources as outlined in the [Central Cancer Registry Reporting Data Source Capability Statement](CapabilityStatement-central-cancer-registry-reporting-ehr.html).

##### Data API requirements

* The Data Source **SHALL** support the [US Core Server APIs]({{site.data.fhir.ver.uscoreR4}}/CapabilityStatement-us-core-server.html) and APIs as outlined in the [Central Cancer Registry Reporting Data Source Capability Statement](CapabilityStatement-central-cancer-registry-reporting-ehr.html) for the Data Submitter to access patient data.

 
#### Data Submitter Requirements 


##### Authorization Requirements

* The Data Submitter **SHALL** support the [SMART on FHIR Backend Services Authorization](spec.html#smart-on-fhir-backend-services-requirements) outlined above as a client. 


##### Subscription Requirements
The requirements in this sub-section are only applicable if the Data Submitter is not packaged, as part of the Data Source.

* The Data Submitter **SHALL** be capable of creating Subscriptions for the [encounter-close and encounter-start trigger events]({{site.data.fhir.ver.uspublichealthprofileslibraryIg}}/us-ph-valueset-triggerdefinition-namedevent.html).

* The Data Submitter **SHALL** support [``rest-hook``]({{site.data.fhir.path}}subscription.html#2.46.7.1) Subscription channel to receive notifications from the Data Source.


##### Subscription Notification API 

* The Data Submitter **SHALL** support a POST API <Data Submitter Base URL>/receive-notification with a payload of the Subscription Notification Bundle to receive the notifications from the Data Source. 

* The Data Submitter **SHALL** ensure no duplicate reports are submitted for the same patient and encounter occurring within a health care organization.

##### Data API Requirements
* The Data Submitter acting as a client **SHALL** use the [US Core Server APIs]({{site.data.fhir.ver.uscoreR4}}/CapabilityStatement-us-core-server.html) and [Central Cancer Registry Reporting Data Source Capability Statement](CapabilityStatement-central-cancer-registry-reporting-ehr.html) to access patient data from the Data Source.


##### Report Generation Requirements 
* The Data Submitter **SHALL** be capable of interpreting [Central Cancer Registry Reporting PlanDefinition](StructureDefinition-ccrr-plandefinition.html) to process the encounter-start and encounter-close trigger events and determine if a CCRR report needs to be generated and submitted.

* The Data Submitter **SHALL** create a CCRR Report following the constraints identified in [Central Cancer Registry Reporting Content Bundle](StructureDefinition-ccrr-content-bundle.html).

* The Data Submitter **SHALL** package the CCRR report following the constraints identified in [Central Cancer Registry Reporting Bundle](StructureDefinition-ccrr-reporting-bundle.html).

* The Data Submitter **SHALL** submit the message containing the CCRR Report to the identified endpoint using either FHIR Messaging (<Data Receiver Base URL>/$process-message) endpoint or POST a Bundle using the <Data Receiver Base URL>/Bundle endpoint. 

<!--* The Data Submitter **SHALL** create a central cancer registry report following the constraints identified in [Central Cancer Registry Content Bundle](StructureDefinition-ccrr-content-bundle.html).

* The Data Submitter **SHALL** package the central cancer registry report following the constraints identified in [Central Cancer Registry Reporting Bundle](StructureDefinition-ccrr-reporting-bundle.html).

* The Data Submitter **SHALL** submit the message containing the central cancer registry report to the endpoint identified in the MedMorph Central Cancer Registry Reporting Knowledge Artifact unless overridden by the healthcare organization.

###### MedMorph RA Requirements 

* The HDEA **SHALL** implement the MedMorph HDEA requirements as outlined in the [MedMorph HDEA requirements]({{site.data.fhir.ver.medmorphIg}}/CapabilityStatement-medmorph-healthdata-exchange-app-client.html).
-->
#### Data Receiver Requirements 

##### Message Receiving and Processing Requirements

* The Data Receiver **SHALL** support multiple methods to receive data from the Data Submitter as follows
	
	* POST a Bundle using the <Data Receiver Base URL>/Bundle endpoint
	* POST a Bundle using the FHIR Messaging <Data Receiver base URL>/$process-message endpoint
		 

* The Data Receiver **SHALL** implement the $process-message operation on the ROOT URL of the FHIR Server to receive reports from the Data Submitter using the POST operation.

* The Data Receiver **SHALL** implement the /Bundle endpoint to receive [Central Cancer Registry Reporting Content Bundle](StructureDefinition-ccrr-content-bundle.html) from a Data Submitter.

* Upon receipt of the message, the Data Receiver **SHALL** validate the data before accepting the data for downstream processing.

* When there are validation failures, the Data Receiver **SHALL** return an Operation Outcome response with the details of the validations as part of the POST response.

<!--##### Trusted Third Party Requirements


###### Message Receiving and Processing requirements

* Trusted Third Parties **SHALL** implement the $process-message operation on the ROOT URL of the FHIR Server to receive reports from the HDEA using the POST operation.

* Upon receipt of the message, the Trusted Third Parties **MAY** validate the message before accepting the message.

* When the message is validated and there are validation failures, Trusted Third Parties **SHALL** return an Operation Outcome response with the details of the validations as part of the POST response.

* Once a message is accepted by a Trusted Third Party without errors, the Trusted Third Party will have to route the message to the Central Cancer Registry.

* The TTP **SHALL** implement the Trusted Third Party requirements as outlined in the [MedMorph RA TTP requirements]({{site.data.fhir.ver.medmorphIg}}/CapabilityStatement-medmorph-trusted-third-party.html).
-->


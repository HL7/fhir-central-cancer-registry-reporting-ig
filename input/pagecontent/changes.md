### Change History

The following is a list of all the changes based on versions.

### Changes made from STU 1 to STU 2 (Ballot)

#### Addressed the following Jira Tickets:

|JIRA Ticket|Ticket Description|
|---------|----------|
|[FHIR-42967](https://jira.hl7.org/browse/FHIR-42967) | Leverage mCODE STU3 |
|[FHIR-35768](https://jira.hl7.org/browse/FHIR-35768) | Might want to collaborate and note any overlap or reference with CODEX work, V2 |
|[FHIR-35165](https://jira.hl7.org/browse/FHIR-35165) | PlanDefinition seems to fetch based on Condition |
|[FHIR-35037](https://jira.hl7.org/browse/FHIR-35037) | USCDI Version 2.0 |
|[FHIR-51621](https://jira.hl7.org/browse/FHIR-51621) | CI build link  |


#### Detailed Description of Changes:

<table border="1">
    <thead>
       <tr style="background-color:#DCDCDC">
            <th style="text-align: center; vertical-align: middle;">Artifact</th>
            <th style="text-align: center; vertical-align: middle;">Change Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>All</td>
            <td>Aligned with <a href="https://hl7.org/fhir/us/core/STU6.1/index.html">US Core FHIR IG 6.1.0</a></td>
        </tr>
        <tr>
            <td>All</td>
            <td>Aligned with <a href="http://hl7.org/fhir/us/mcode/STU4/index.html">mCODE FHIR IG STU4</a></td>
        </tr>
        <tr>
            <td>All</td>
            <td>Aligned with <a href="http://hl7.org/fhir/us/cancer-reporting/STU2/index.html">Cancer Pathology Data Sharing FHIR IG STU2</a></td>
        </tr>
        <tr>
            <td>All (where applicable)</td>
            <td>
                <ul>Removed references to MedMorph Reference Architecture IG</ul>
                <ul>Added references to US PH Library profiles</ul>
                <ul>Align with <a href="https://uscdiplus.healthit.gov/uscdiplus?id=uscdi_record&table=x_g_sshh_uscdi_sub_domain&sys_id=05a081bc1baf861049edc957624bcb6c&view=sp">USCDI+ Cancer - Cancer Registry Use Case</a></ul>
                <ul>Fixed typos and broken links</ul>
            </td>
        </tr>
		<tr>
			<td>Change Log</td>
			<td>Added and updated the Change Log</td>
		</tr>
        <tr>
            <td><a href="StructureDefinition-central-cancer-registry-reporting-organization.html">Central Cancer Registry Reporting Organization</a></td>
            <td>New Profile to support the USCDI+ Cancer - Cancer Registry Use Case</td>
        </tr>		
        <tr>
            <td><a href="StructureDefinition-central-cancer-registry-reporting-patient.html">Central Cancer Registry Reporting Patient</a></td>
            <td>Renamed from Cancer Patient to be consistent with profile naming conventions</td>
        </tr>
        <tr>
            <td><a href="StructureDefinition-central-cancer-registry-reporting-encounter.html">Central Cancer Registry Reporting Encounter</a></td>
            <td>Renamed from Cancer Encounter to be consistent with profile naming conventions</td>
        </tr>
        <tr>
            <td><a href="StructureDefinition-ccrr-composition.html">Central Cancer Registry Reporting Composition</a></td>
            <td>
                <ul>Renamed from Central Cancer Registry Report Composition to be consistent with profile naming conventions</ul>
                <ul>Removed the Allergies Section - This section was included in error. This information is not collected by registries or NAACCR and should not be included in a CCR report.</ul>
                <ul>Modified the sections and entries to align with the Use Case Triggers and Reporting section of the Use Case page</ul>
            </td>
        </tr>
        <tr>
            <td><a href="StructureDefinition-central-cancer-registry-primary-cancer-condition.html">Central Cancer Registry Reporting Primary Cancer Condition</a></td>
            <td>Changed base definition from us-core-condition-problems-health-concerns to us-core-condition-encounter-diagnosis to allow for category.code of encounter-diagnosis</td>
        </tr> 
        <tr>
			<td>Use Cases</td>
			<td>
                <ul>Updated text and links as appropriate</ul>
                <ul>Added the Use Case Triggers and Reporting Section</ul>
                <ul>Added the Patient Journey, accompanying Examples, and the Reporting Timeline diagram</ul>
                <ul>Updated the Actors and Systems Diagrams and Use Case Actors definitions</ul>
            </td>
		</tr>       
    </tbody>
</table>

### Changes made from STU 1 (Ballot) to STU 1

#### Addressed the following Jira Tickets:

|JIRA Ticket|Ticket Description|
|---------|----------|
|[FHIR-36230](https://jira.hl7.org/browse/FHIR-36230) | CLONE - Terminology Value Sets Comments |
|[FHIR-35880](https://jira.hl7.org/browse/FHIR-35880) | Add T N M Profiles to Section 6.2.1.2 Text Summary |
|[FHIR-35760](https://jira.hl7.org/browse/FHIR-35760) | Clarify how the data of interest is specified |
|[FHIR-35714](https://jira.hl7.org/browse/FHIR-35714) | Ensure you coordinate the lab result sections with the Cancer Pathology reporting |
|[FHIR-35702](https://jira.hl7.org/browse/FHIR-35702) | Clarify policy references and fix links |
|[FHIR-35315](https://jira.hl7.org/browse/FHIR-35315) | Please confirm that Vendor Software Name and Version number are included in the IG. |
|[FHIR-35314](https://jira.hl7.org/browse/FHIR-35314) | Modifications to Cancer Condition Profile |
|[FHIR-35310](https://jira.hl7.org/browse/FHIR-35310) | Defining URL (Canonical URL) should be anchored in THO not hl7.org/fhir. Only those with required binding to a 'code' data type should be anchored in hl7.fhir.org |
|[FHIR-35220](https://jira.hl7.org/browse/FHIR-35220) | Content Bundle example incorrectly represents primary-cancer-condition |
|[FHIR-35135](https://jira.hl7.org/browse/FHIR-35135) | Endnote citation missing |
|[FHIR-35134](https://jira.hl7.org/browse/FHIR-35134) | Fix broken link |
|[FHIR-35133](https://jira.hl7.org/browse/FHIR-35133) | Why are there 2 Patient Profiles? |
|[FHIR-35131](https://jira.hl7.org/browse/FHIR-35131) | Tighten the cardinality and add dataAbsentReason on elements |
|[FHIR-35129](https://jira.hl7.org/browse/FHIR-35129) | Profile link is not a link |
|[FHIR-35127](https://jira.hl7.org/browse/FHIR-35127) | Typo in section title |
|[FHIR-35023](https://jira.hl7.org/browse/FHIR-35023) | Resource / Specification bundle names unclear  |
|[FHIR-35021](https://jira.hl7.org/browse/FHIR-35021) | Example Bundle Name |
|[FHIR-35019](https://jira.hl7.org/browse/FHIR-35019) | Example instances resource names  |
|[FHIR-35017](https://jira.hl7.org/browse/FHIR-35017) | Table clarification |
|[FHIR-35003](https://jira.hl7.org/browse/FHIR-35003) | Table Correction |
|[FHIR-35002](https://jira.hl7.org/browse/FHIR-35002) | ODH IG Link|
|[FHIR-35001](https://jira.hl7.org/browse/FHIR-35001) | Confusing language in Problem Statement |
|[FHIR-35000](https://jira.hl7.org/browse/FHIR-35000) | Link in Section 2.2|
|[FHIR-34699](https://jira.hl7.org/browse/FHIR-34699) | Link to newest version of UsualWork profile |
|[FHIR-34662](https://jira.hl7.org/browse/FHIR-34662) | CCRR typos |
|[FHIR-34658](https://jira.hl7.org/browse/FHIR-34658) | Missing Must Support for identifier dataAbsentReason |
|[FHIR-34656](https://jira.hl7.org/browse/FHIR-34656) | Patient reference in Encounter profile may be too specific |
|[FHIR-34655](https://jira.hl7.org/browse/FHIR-34655) | Clarify the role of the Knowledge Artifact in defining the use of the content Bundle sections |
|[FHIR-34654](https://jira.hl7.org/browse/FHIR-34654) | Should Primary Cancer Condition be allowed to repeat?  |
|[FHIR-34653](https://jira.hl7.org/browse/FHIR-34653) | Is SmokingStatus repeatable? |
|[FHIR-34652](https://jira.hl7.org/browse/FHIR-34652) | Is UsualWork repeatable |
|[FHIR-34651](https://jira.hl7.org/browse/FHIR-34651) | Use Case description doesn't distinguish between EHR and the MedMorph RA |
|[FHIR-34579](https://jira.hl7.org/browse/FHIR-34579) | Subscription resource bundle |
|[FHIR-34578](https://jira.hl7.org/browse/FHIR-34578) | Subscription Requirements too broad |
|[FHIR-34577](https://jira.hl7.org/browse/FHIR-34577) | MedMorph Link |
|[FHIR-34576](https://jira.hl7.org/browse/FHIR-34576) | Bulk Data Version |
|[FHIR-34575](https://jira.hl7.org/browse/FHIR-34575) | Bulk Data Cohort |
|[FHIR-34574](https://jira.hl7.org/browse/FHIR-34574) | ODH Specification |
|[FHIR-34572](https://jira.hl7.org/browse/FHIR-34572) | PH Profiles Link |
|[FHIR-34571](https://jira.hl7.org/browse/FHIR-34571) | Use of proper conformance words|
|[FHIR-34570](https://jira.hl7.org/browse/FHIR-43461) | Diagram Reportability Identification |
|[FHIR-34569](https://jira.hl7.org/browse/FHIR-34569) | Audit Trail Documentation |
|[FHIR-34568](https://jira.hl7.org/browse/FHIR-34568) | Follow up activities |
|[FHIR-34567](https://jira.hl7.org/browse/FHIR-34567) | Extended Duration 6mo |
|[FHIR-34566](https://jira.hl7.org/browse/FHIR-34566) | Timing Description |
|[FHIR-34565](https://jira.hl7.org/browse/FHIR-34565) | Challenges Include |
|[FHIR-34564](https://jira.hl7.org/browse/FHIR-34564) | Scope Definition |
|[FHIR-34563](https://jira.hl7.org/browse/FHIR-34563) | Other Standards |
|[FHIR-34539](https://jira.hl7.org/browse/FHIR-34539) | Examples not linked to profile page |
|[FHIR-34441](https://jira.hl7.org/browse/FHIR-34441) | Determine how to capture Cancer Disease Status Evidence type using value set |
|[FHIR-34440](https://jira.hl7.org/browse/FHIR-34440) | Add Asserted Date to Primary Cancer Condition |

### Changes for STU 1 (Ballot)

#### Detailed Description of Changes:
Initial version of the IG.

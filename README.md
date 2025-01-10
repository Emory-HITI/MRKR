# Emory Knee Radiograph (MRKR) Dataset
<br>
Data description of the Emory Knee Radiograph (MRKR) Dataset hosted by Open Data on AWS.
<br><br>
An example notebook is included.
<br><br>

### Summary

The Emory Knee Radiograph (MRKR) dataset is a large, demographically diverse collection of
503,261 knee radiographs from 83,011 patients, 40% of which are African American. This dataset
provides imaging data in DICOM format along with detailed clinical information, including patient-
reported pain scores, diagnostic codes, and procedural codes, which are not commonly available in
similar datasets. The MRKR dataset also features imaging metadata such as image laterality, view type,
and presence of hardware, enhancing its value for research and model development. MRKR addresses
significant gaps in existing datasets by offering a more representative sample for studying osteoarthritis
and related outcomes, particularly among minority populations, thereby providing a valuable resource
for clinicians and researchers.<br><br>

### Dataset Size

The total dataset is 2.3 TB and includes DICOMs (2.3 TB) and seven CSV files (2.7 GB)
each containing clinical and metadata.

The dataset will be hosted with Open Data on AWS.<br><br>

### Publication
Pre-print: https://arxiv.org/abs/2411.00866.<br><br>

### License

<a href="https://creativecommons.org/licenses/by-sa/4.0/">CC-BY-SA</a><br><br>

### MRKR Dataset Patient Summary Statistics
<table border="1">
  <tr>
    <td><strong>Total Patients</strong></td>
    <td>83,011 (100%)</td>
  </tr>
  <tr>
  <td colspan="2"><strong>Gender</strong></td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Female</strong></td>
    <td>51,175 (61.6%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Male</strong></td>
    <td>31,836 (38.4%)</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Age, years</strong></td>    
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Mean</strong></td>
    <td>56.6 (std. +/- 16.6)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Median</strong></td>
    <td>58</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Race demographics</strong></td>
  </tr>
  <tr></tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;White</strong></td>
    <td>36,927 (44.5%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Black</strong></td>
    <td>33,503 (40.4%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Asian</strong></td>
    <td>2,893 (3.5%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Unknown/Unreported</strong></td>
    <td>8,751 (10.5%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Other</strong></td>
    <td>937 (1.1%)</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Ethnicity</strong></td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Hispanic</strong></td>
    <td>2,501 (3.0%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Non-Hispanic</strong></td>
    <td>66,378 (80.0%)</td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Unknown/Unreported</strong></td>
    <td>14,132 (17.0%)</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Clinical outcomes</strong></td>
  </tr>
  <tr>
    <td><strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Arthroplasty</strong></td>
    <td>14,843 (17.9%)</td>
  </tr>
</table>

<br><br>

### Dataset Structure


<table>
<tr>
  <td colspan="3">
    Filename: MRKR_CPT.csv<br>
    File size: 178 MB<br>
    Total rows: 6,216,190<br>
    Description: This table contains information regarding all CPT codes for a patient and corresponding dates.
    </td>
</tr>
    <tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>empi_anon</td>
        <td>Integer (8 digits)</td>
        <td>Unique patient identification number (83,011 patients)</td>
    </tr>
    <tr>
        <td>cpt_code</td>
        <td>String (5 characters)</td>
        <td>Current Procedural Terminology code used in coding of medical services and procedures for billing (7,166 CPT codes)</td>
    </tr>
    <tr>
        <td>cpt_group_modifier</td>
        <td>String</td>
        <td>Used to provide further information regarding service or procedure. Most CPT codes do not include modifier data. If there is modifier data, it is often used to indicate the laterality of a procedure (left or right). There can be multiple modifiers for a single CPT code entry.</td>
    </tr>
    <tr>
        <td>date_anon</td>
        <td>Date</td>
        <td>Date of when the associated procedure or service occurred.</td>
    </tr>
    <tr>
        <td>age_at_procedure</td>
        <td>Integer</td>
        <td>Age when the procedure was performed.</td>
    </tr>
</table>
<br>
<table>
  <tr>
    <td colspan="3">
      Filename: MRKR_CPT_dictionary.csv<br>
      File size: 754 KB<br>
      Total rows: 7,166<br>
      Description: A lookup table between CPT codes and corresponding descriptions.
    </td>
    
  </tr>
    <tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>cpt_code</td>
        <td>String (5 characters)</td>
        <td>Current Procedural Terminology code used in the coding of medical services and procedures for billing.</td>
    </tr>
    <tr>
        <td>cpt_description</td>
        <td>String</td>
        <td>Description of the procedure. There are some unique CPT codes that share the same description.</td>
    </tr>
</table>
<br>
<table>
      <tr>
      <td colspan="3">
        Filename: MRKR_ICD.csv<br>
        File size: 1.7 GB<br>
        Total rows: 21,956,056<br>
        Description: ICD9 and ICD10 diagnoses for patients with corresponding dates. Certain diseases of interest are indicated by binary flags to ease data cleaning.     
      </td>
    </tr>
<tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>empi_anon</td>
        <td>Integer (8 digits)</td>
        <td>Unique patient identification number (83,011 unique patients)</td>
    </tr>
    <tr>
        <td>ICD9</td>
        <td>String</td>
        <td>International Classification of Diseases - 9 (12,418 unique codes)</td>
    </tr>
    <tr>
        <td>ICD10</td>
        <td>String</td>
        <td>International Classification of Diseases - 10 (26,963 unique codes)</td>
    </tr>
    <tr>
        <td>date_anon</td>
        <td>Date</td>
        <td>Date of when the diagnosis code was entered.</td>
    </tr>
    <tr>
        <td>age_at_dx</td>
        <td>Integer</td>
        <td>Age when the diagnosis was recorded.</td>
    </tr>
    <tr>
        <td>DX_LINE</td>
        <td>String</td>
        <td>Primary, Secondary, Active, Not Recorded, Resolved, Canceled, Inactive.</td>
    </tr>
    <tr>
        <td>DX_ICD_SCOPE</td>
        <td>String</td>
        <td>Billing Diagnosis, Discharge Diagnosis, Admitting Diagnosis, Referring Diagnosis, Not Recorded, Reason For Visit, Problem List, Working Diagnosis, Other Diagnosis, Final, Pre-Op Diagnosis, Post-Op Diagnosis, Principal Diagnosis, Suggested Billing.</td>
    </tr>
    <tr>
        <td>autoimmune</td>
        <td>Binary</td>
        <td>If ICD code corresponds to auto-immune disease such as rheumatoid arthritis, juvenile arthritis, gout, etc.</td>
    </tr>
    <tr>
        <td>diabetes</td>
        <td>Binary</td>
        <td>If ICD code corresponds to type I or type II diabetes.</td>
    </tr>
    <tr>
        <td>hypertension</td>
        <td>Binary</td>
        <td>If ICD code corresponds to hypertension.</td>
    </tr>
    <tr>
        <td>joint_infection</td>
        <td>Binary</td>
        <td>If ICD code corresponds to a knee joint infection.</td>
    </tr>
    <tr>
        <td>knee_osteoarthritis</td>
        <td>Binary</td>
        <td>If ICD code corresponds to knee osteoarthritis.</td>
    </tr>
    <tr>
        <td>knee_osteomyelitis</td>
        <td>Binary</td>
        <td>If ICD code corresponds to knee osteomyelitis.</td>
    </tr>
    <tr>
        <td>obesity</td>
        <td>Binary</td>
        <td>If ICD code corresponds to obesity.</td>
    </tr>
    <tr>
        <td>nicotine_use</td>
        <td>Binary</td>
        <td>If ICD code corresponds to nicotine dependence.</td>
    </tr>
    <tr>
        <td>trauma_lower_extremity</td>
        <td>Binary</td>
        <td>If ICD code corresponds to lower extremity trauma.</td>
    </tr>
</table>
<br>
<table>
<tr>
  <td colspan="3">
    Filename: MRKR_ICD_dictionary.csv<br>
    File size: 1.9 MB<br>
    Total rows: 25,209<br>
    Description: Lookup table for ICD9 (International Classification of Diseases) and ICD10 codes and corresponding descriptions.<br>    
  </td>
</tr>
    <tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>ICD9</td>
        <td>String</td>
        <td>ICD9 code.</td>
    </tr>
    <tr>
        <td>ICD10</td>
        <td>String</td>
        <td>ICD10 code.</td>
    </tr>
    <tr>
        <td>DX_NAME</td>
        <td>String</td>
        <td>Diagnosis name or description. </td>
    </tr>
</table>
<br>
<table width="100%">
<tr>
  <td colspan="3">
    Filename: MRKR_pain.csv<br>
    File size: 137 MB<br>
    Total rows: 4,975,933<br>
    Description: Contains information on self-reported pain scores by patients during any encounter, including outpatient, emergency, and perioperative. Pain scores related to knees are curated.
  </td>
</tr>
    <tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>empi_anon</td>
        <td>Integer (8 digits)</td>
        <td>Unique patient identification number (83,011 unique patients)</td>
    </tr>
    <tr>
        <td>pain_location</td>
        <td>String</td>
        <td>Raw, uncurated strings of pain locations entered by staff. Approximately 75% of entries are blank.</td>
    </tr>
    <tr>
        <td>knee_pain</td>
        <td>Binary</td>
        <td>Curated using regular expressions to identify if the pain_location is definitely knee related.</td>
    </tr>
    <tr>
        <td>pain_score</td>
        <td>Integer</td>
        <td>0 - 10 pain score.</td>
    </tr>
</table>
<br>
<table>
  <tr>
    <td colspan="3">
      Filename: MRKR_demographics.csv<br>
      File size: 4.5 MB<br>
      Total rows: 83,011<br>
      Description: Patient demographics, indexed at the patient level.
    </td>
  </tr>
    <tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>empi_anon</td>
        <td>Integer (8 digits)</td>
        <td>Unique patient identification number.</td>
    </tr>
    <tr>
        <td>sex</td>
        <td>Nominal string</td>
        <td>[male, female] - Patient sex.</td>
    </tr>
    <tr>
        <td>race</td>
        <td>Nominal string</td>
        <td>[African American or Black, American Indian or Alaskan Native, Asian, Caucasian or White, Multiple, Native Hawaiian or Other Pacific Islander, Unknown] - Patient self-reported race.</td>
    </tr>
    <tr>
        <td>ethnicity</td>
        <td>Nominal string</td>
        <td>[Hispanic patients, Non-Hispanic patients, Unknown, Unreported] - Patient reported ethnicity.</td>
    </tr>
</table>
<br>
<table>
  <tr>
    <td colspan="3">
        Filename: MRKR_image_metadata.csv<br>
        File size: 210 MB<br>
        Total rows: 503,261<br>
        Description: Contains relevant public DICOM metadata tags that may be helpful for identifying images. Patient and exam identifiers are replaced with de-identified versions in this table and within DICOM files. Other Non-PHI containing metadata tags that are not in this table are left intact within DICOM files. Fields containing PHI such as patient name, addresses, or referring physician are removed from this table and DICOM files. For data curation, the below fields were modified or added.
    </td>
  </tr>
    <tr>
        <th width="20%">Field Name</th>
        <th width="20%">Data Type</th>
        <th width="60%">Description</th>
    </tr>
    <tr>
        <td>empi_anon</td>
        <td>Integer (8 digits)</td>
        <td>De-identified patient identification number.</td>
    </tr>
    <tr>
        <td>StudyInstanceUID_anon</td>
        <td>String</td>
        <td>De-identified Study UID, shared between all images in the same study.</td>
    </tr>
    <tr>
        <td>SeriesInstanceUID_anon</td>
        <td>String</td>
        <td>De-identified Series UID, shared between all images in the same series.</td>
    </tr>
    <tr>
        <td>SOPInstanceUID_anon</td>
        <td>String</td>
        <td>De-identified SOP Instance UID which corresponds to a single DICOM image.</td>
    </tr>
    <tr>
        <td>img_height</td>
        <td>Integer</td>
        <td>Image pixel height.</td>
    </tr>
    <tr>
        <td>img_width</td>
        <td>Integer</td>
        <td>Image pixel width.</td>
    </tr>
    <tr>
        <td>laterality</td>
        <td>Nominal string</td>
        <td>[R: Right, L: Left, B: Bilateral, -1: Unknown or not present] - Laterality of the image, as inferred by DL model.</td>
    </tr>
    <tr>
        <td>view_position</td>
        <td>Nominal string</td>
        <td>[F: Frontal, L: Lateral, S: Sunrise, I: Internal Oblique, E: External Oblique] - Anatomical projection of radiograph, as inferred by DL model.</td>
    </tr>
    <tr>
        <td>horizontal_flip</td>
        <td>Binary</td>
        <td>Indicates if the patient’s left side was oriented to the left side of the image, which is opposite of typical radiographic orientation, as inferred by DL model.</td>
    </tr>
    <tr>
        <td>weight_bearing</td>
        <td>Binary</td>
        <td>Indicates if the radiograph was weight-bearing as indicated by a marker and derived by DL model. Not all images in a given exam will be weight-bearing or non-weightbearing.</td>
    </tr>
    <tr>
        <td>inverted</td>
        <td>Binary</td>
        <td>Indicates whether pixel intensity values are inverted from typical radiographic convention, as inferred by DL model.</td>
    </tr>
    <tr>
        <td>arthroplasty</td>
        <td>Nominal string</td>
        <td>[R: right, L: left, B: bilateral, NL: unknown (no laterality marker), NaN: no arthroplasty] - Indicates if image contains a knee arthroplasty and its laterality, as derived by DL model.</td>
    </tr>
    <tr>
        <td>L_KLG_inference</td>
        <td>Integer<br>[0,1,2,3,4,NaN]</td>
        <td>KLG score of left knee in a bilateral knee radiograph, inferred by DL model.</td>
    </tr>
    <tr>
        <td>R_KLG_inference</td>
        <td>Integer<br>[0,1,2,3,4,NaN]</td>
        <td>KLG score of right knee in a bilateral knee radiograph, inferred by DL model.</td>
    </tr>
    <tr>
        <td>SeriesDescription</td>
        <td>String</td>
        <td>DICOM Metadata describing the series.</td>
    </tr>
    <tr>
        <td>StudyDescription</td>
        <td>String</td>
        <td>DICOM metadata describing the study.</td>
    </tr>
    <tr>
        <td>StudyDate_anon</td>
        <td>Date</td>
        <td>De-identified date of radiograph.</td>
    </tr>
    <tr>
        <td>age_at_exam</td>
        <td>Integer</td>
        <td>Age of the patient when the radiograph was performed.</td>
    </tr>
    <tr>
        <td>dicom_path</td>
        <td>String</td>
        <td>Path to DICOM file.</td>
    </tr>
</table>

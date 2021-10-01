# Module 17 Challenge - Credit Risk Analysis - Machine Learning

## Overview

Project Origination Date: 2021-09-27

#### Special Explanatory Note

LendingClub was founded in 2006, with initial Loans offered to customers and associated Notes offered directly to qualified investors starting in 2007.
This lending model was classified as Peer-to-Peer lending, facilitated by the LendingClub Platform.

As of December 31, 2020, the Notes platform available to qualified investors was retired in the wake of LendingClub's acquisition of
Radius Bancorp and the associated corporate restructuring and adjustment of business model.

As of today (Q3-2021), Personal and Business Loans are still available to customers through LendingClub. Rather than offering these individual Loan Notes
directly to individual qualified investors as under the previous business model, the notes are sampled and marketed in bundles to
institutional investors.

The most-recent publicly available LendingClub Loan Data (via archive.org Wayback Machine) is from Q2-2019 from the Aug. 19, 2019 crawl.

### Purpose



### Tasks



### Approach



### Deliverables



### Resources

- Software:
	- Jupyter notebook server 6.3.0, running Python 3.7.10 64-bit (Dependencies: )
	- 
- Data:
	- `LoanStats_2019Q1.csv`
		- Client-provided dataset of Anonymized LendingClub Notes Approval Results and Associated Metadata.
	- `LoanStats_2019Q1_front_and_endmatter_stripped_ascii_subs.csv`
		- User-edited version of `LoanStats_2019Q1.csv`
		- In `LoanStats_2019Q1.csv`, Line 1 was originally a non-Header URL for LendingClub Prospectus: (https://www.lendingclub.com/info/prospectus.action), and the final 4 lines
		were two blank lines followed by two different Sums for total amounts funded in policy codes 1 & 2.
		- Original source file was retained, unmodified, on disk for reference purposes, but to facilitate easier analysis and data manipulation, these 5 lines were deleted in
		the copied version of the file, `{base_file_name}_front_and_endmatter_stripped.csv`
		- The 36 Non-ASCII Characters identified in the dataset were replaced as described in Appendix A, Table 3.
		- Spelling errors were identified in the dataset, but have been retained as original at this time.
		- This version of the file is completely rectangular and homogeneous, in terms of the number of rows and columns contained within.
	- `LCDataDictionary.xlsx`: LendingClub Provided Data Dictionary. Most-Recent version available from Archive.org Wayback Machine from Aug. 19, 2019.
	URL: (https://web.archive.org/web/20190819231817/https://www.lendingclub.com/info/download-data.action)
	- `credit_risk_resampling_starter_code.ipynb`
		- Client-provided Starter Code
	- `credit_risk_ensemble_starter_code.ipynb`
		- Client-provided Starter Code
	  
Additional information about `LoanStats_2019Q1.csv` and `LoanStats_2019Q1_front_and_endmatter_stripped.csv` is outlined below in [Appendix A](#appendix-a---data-lexicon), Tables 1 & 2.
                                            
#### Data Quality                           

##### ASCII Check

As a first-pass data cleaning task, `LoanStats_2019Q1_front_and_endmatter_stripped.csv` was checked for the presence of non-ASCII Characters.
36 Lines were identified containing non-ASCII characters, with one-match per line, for a total of 36 non-ASCII characters in the dataset.
The vast majority (20) of these matches were Unicode Right Single Quotes (U+2019), one was a Unicode En dash (U+2013), and the rest were accented Latin Characters,
mostly inadvertently incorrectly applied or corrupted (e.g. "Área supervisor").
In the places where these non-ASCII characters were correctly applied, they were in non-English language job titles and proper names such as "Chófer", "Construcción",
"Ana González", and "Estée Lauder". These characters were replaced with an equivalent from the ASCII Character Set, and
non-English job titles and proper names retained the spelling convention of their origin language with the exception of the non-ASCII to ASCII substitution.
Since the number of replacements were so few, and to better illustrate the nature of these updates, they have all been reproduced with explanatory notes below in
[Appendix A](#appendix-a---data-lexicon), Table 3.

## Deliverables

### Deliverable 1



### Deliverable 2



### Deliverable 3




## Results



## Summary


## Appendix A - Data Lexicon

**Table 1: Source Data Description**
| File Name                                                       | Brief Description of Contents
|-----------------------------------------------------------------|------------------------------
| `LoanStats_2019Q1.csv`                                          | 115,681 Lines, 91 MB. Double-Quoted-Field Comma-Separated-Value UTF-8 Flat Plaintext file containing LendingClub Notes Approval Results and Associated Metadata. Unix-Style Line-endings (LF-0A). Note that Field 11 (`emp_title`) is the only field to include embedded commas with current file contents.
| `LoanStats_2019Q1_front_and_endmatter_stripped_ascii_subs.csv`  | 115,676 Lines, 91 MB. Disk Copy of `LoanStats_2019Q1.csv`, with the removal of 5 lines as described above in *Resources*, and the replacement of non-ASCII Characters as described below in *Appendix A, Table 3*. Double-Quoted-Field Comma-Separated-Value ASCII Plaintext Flat file containing LendingClub Notes Approval Results and Associated Metadata. Unix-Style Line-endings (LF-0A). 1 Header Line, remainder of lines in file correspond (1 Line):(1 Loan Record)

**Table 2: `LoanStats_2019Q1_front_and_endmatter_stripped_ascii_subs.csv` Fields**
| Field Name                       | Brief Description of Contents
|----------------------------------|------------------------------
| id                               | Lorem...

**Table 3: `LoanStats_2019Q1_front_and_endmatter_stripped_ascii_subs.csv` non-ASCII Character Substitutions with Remarks**
| Original non-ASCII Representation                          | ASCII Substitution                           | Remarks
|------------------------------------------------------------|----------------------------------------------|--------
| President’s Club Banker                                    | President's Club Banker                      | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Children’s Social Worker                                   | Children's Social Worker                     | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Men’s Clothing Stylist                                     | Men's Clothing Stylist                       | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Owner  Clem’s handyman service                             | Owner  Clem's handyman service               | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Teacher’s Assistant                                        | Teacher's Assistant                          | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Children’s Lead                                            | Children's Lead                              | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Ass’t Finance Officer                                      | Ass't Finance Officer                        | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Productión Team Leader                                     | Production Team Leader                       | Correction of obvious incorrect character in job title.
| Community and Gov’t Relations                              | Community and Gov't Relations                | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Trade Manager – Ocean Services                             | Trade Manager - Ocean Services               | Unicode En Dash Replaced with ASCII Hyphen-Minus.
| Men’s Shoes                                                | Men's Shoes                                  | Unicode Right Single Quote Replaced with ASCII Apostrophe.
| Maintance mánager                                          | Maintance manager                            | Correction of obvious incorrect character in job title. Incorrect spelling retained.
| Senior Sheriif’s Records Technician                        | Senior Sheriiff's Records Technician         | Unicode Right Single Quote Replaced with ASCII Apostrophe, incorrect spelling retained.
| Súperintendent                                             | Superintendent                               | Correction of obvious incorrect character in job title.
| Médical assistand                                          | Medical assistand                            | Correction of obvious incorrect character in job title. Incorrect spelling retained.
| Children’s service worker 2                                | Children's service worker 2                  | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Ana González                                               | Ana Gonzalez                                 | Anglicized name. Potential non-anonymized name, but retained for completeness
| Workers’ Compensation Adjuster                             | Workers' Compensation Adjuster               | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Supervisión                                                | Supervision                                  | Spanish Spelling of Job Title Replaced with English Spelling
| Doctor’s Assistant                                         | Doctor's Assistant                           | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Chófer                                                     | Chofer                                       | Anglicized word. Retained Spanish-Style Spelling of Job Title rather than replacing with more common French Spelling.
| Counter manager Estée Lauder                               | Counter manager Estee Lauder                 | Despite Estée Lauder being a widely recognized American Brand Name, it is also present in this dataset as simply "Estee". For our purposes, ASCII Representation was preferred over Non-ASCII Representation, therefore the non-accented version was retained.
| Deputy’s                                                   | Deputy's                                     | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Operation’s Specialist                                     | Operation's Specialist                       | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Construcción                                               | Construccion                                 | Anglicized word. Spanish-Style Spelling of Job Title retained.
| Maitre’d                                                   | Maitre'd                                     | Unicode Right Single Quote Replaced with ASCII Apostrophe. Common French Spelling retained, as it is widely encountered in American English
| Construcción worker                                        | Construccion  worker                         | Anglicized word. Spanish-style Spelling of Job Title retained.
| Children’s Minister                                        | Children's Minister                          | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Producción                                                 | Produccion                                   | Anglicised word. Spanish-style Spelling of Job Title retained.
| Nurse’s aid                                                | Nurse's aid                                  | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Área supervisor                                            | Area supervisor                              | Correction of obvious incorrect character in job title
| Sheriff’s Officer                                          | Sheriff's Officer                            | Unicode Right Single Quote Replaced with ASCII Apostrophe
| Internet sales mánager                                     | Internet sales manager                       | Correction of obvious incorrect character in job title
| fiancé sales manager                                       | fiance sales manager                         | Correction of obvious incorrect character in job title. Incorrect spelling retained.
| Señior correctional deputy                                 | Senior correctional deputy                   | Correction of obvious incorrect character in job title



-- END --

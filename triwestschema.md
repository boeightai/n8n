# TriWest Provider Roster Schema (for LLM extraction)

This document enumerates every column in the TriWest roster template, how required it is, expected formats, and any controlled vocabularies. Use it to extract data from source PDFs and map them to the spreadsheet reliably.

## Legend

- **R** — Required for all records
- **RD** — Required for all delegated records
- **RND** — Required for all non-delegated records
- **RP** — Required for all provider/location records
- **RPD** — Required for delegated provider/location records
- **O** — Optional
- **C** — Conditionally required (see Field Notes)
- **CDI** — Conditionally required for delegates that include individual practitioners/providers
- **CDP** — Conditionally required for delegates that include practices/locations/addresses
- **C1** — Conditionally required for Provider Type 1 (Practitioner)
- **C2** — Conditionally required for Provider Type 2 (Facilities/Institutions)
- **C4** — Conditionally required for Provider Type 4 (Groups)

## Provider Type Codes

- **1** — Practitioner
- **2** — Facilities/Institutions
- **4** — Groups

## Reference Tables (Allowed Values)

### Board Certification Status
- Cert of Additional Qual
- Not Certified
- Eligible
- Certified
- In Process
- N/A
- Lifetime Certification
- Expired
- Accreditation
- Medicare Deemed
- Not Accredited

### Term Reason
- Deceased
- Personal
- Relocated
- Retired
- Left Group/Location
- License expired
- Credentialing Non Compliant
- Administrative
- Facility closed
- Facility Moved
- Left Group

### Languages (display names)
- Afghan
- Afrikaans
- Akan
- Amharic
- Arabic
- Armenian
- Asante
- Assamese
- Assyrian
- Azeri
- Balochi/Baluchi
- Bemba
- Benga
- Bengali
- Bosnian
- Bulgarian
- Burmese
- Cambodian
- Cantonese
- Cebuano
- Chamorro
- Chinese
- Creole
- Croatian
- Czech
- Danish
- Dutch
- Egyptian
- Esan
- Estonian
- Ewe
- Faroese
- Farsi
- Filipino
- Finnish
- Flemish
- French
- Gaelic
- German
- Greek
- Gujarati
- Haida
- Hakka
- Hawaiian
- Hebrew
- Hindi
- Hmong
- Hungarian
- Iban
- Igbo
- Icelandic
- Ilocano
- Indonesian
- Iranian
- Isujarati
- Italian
- Japanese
- Kannada
- Pampanga; Kapampangan
- Kiswahili
- Kituba
- Konkani
- Korean
- Kurdish
- Lakota
- Latin
- Latvian
- Lithuanian
- Luo
- Macedonian
- Malagasy
- Malayalam
- Malay
- Maltese
- Mandarin
- Mandinka
- Marathi
- Mien
- Navajo
- Nepali
- Nigerian
- Norwegian
- Ojibwe
- Oromo
- Palauan
- Pashto
- Persian
- Polish
- Ponapeian
- Portuguese
- Punjabi
- Pushtu
- Romanian
- Russian
- Salish
- Samoan
- Sanskrit
- Serbian
- Shona
- Sign Language
- Sindhi
- Sinhala
- Slavik
- Somali
- Spanish
- Swahili
- Swedish
- Tagalog
- Tamil
- Telugu
- Telvav
- Thai
- Tigrinya
- Tongan
- Tswana
- Turkish
- Twi
- Ukranian
- Urdu
- Vietnamese
- Welsh
- Wolof
- Yapese
- Yiddish
- Yoruba
- Zulu
- Dari
- Lingala
- Haitian
- Hiligaynon
- Kashmiri
- Xhosa
- Creole and pidgins, French based
- English
- Fataleka
- Caribbean Hindustani
- Ido
- Lao
- Manipuri
- Ojibwa
- Oriya
- Serbo-Croatian
- Slovak
- Yugoslavian/Slovenian
- Zuni

> Note: The language list is long; if a language is not in this list, prefer the closest standard name per ISO 639; store the display name and code if provided.

## Columns

### Request Type
- **Requirement**: `R` — Required for all records
- **Notes / Format**: A = Add
C = Change
T = Term

### Record Type Code
- **Requirement**: `R` — Required for all records
- **Notes / Format**: P = Practitioner/Location 
L = Location Only

### Provider Type
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: 1=Provider Type 1

### Provider First Name
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: Must be greater in length than 1 character and may contain the following characters only:  
     A through Z (upper and lower case)
     Special Characters ' - .
     A space between words is permitted

### Provider Last Name
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: Must be greater in length than 1 character and may contain the following characters only:  
     A through Z (upper and lower case)
     Special Characters ' - .
     A space between words is permitted

### Provider Middle Name
- **Requirement**: `O` — Optional
- **Notes / Format**: Must be greater in length than 1 character and may contain the following characters only:  
     A through Z (upper and lower case)
     Special Characters ' - .
     A space between words is permitted

### Provider Suffix
- **Requirement**: `O` — Optional
- **Notes / Format**: I; II; III; IV; V; VI; VII; VIII; IX; JR; SR

### Provider NPI
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: Numeric

### Provider DOB
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: MM/DD/YYYY

### Provider Gender
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: M =Male
F=Female

### Provider SSN
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: Numeric

### Provider Degree
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: Alpha

### Provider Initial Credential Date
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: MM/DD/YYYY

### Provider Last Credentialed Date
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: MM/DD/YYYY

### Provider Effective Date
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: MM/DD/YYYY

### Provider Term Date
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: MM/DD/YYYY

### Provider Term Reason
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: Refer to Term Reason Table
- **Allowed Values**: See *Term Reason* list above.

### Sole Practitioner
- **Requirement**: `R` — Required for all records
- **Notes / Format**: True
False
Blank=False

### Provider License Type
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: DEA, State

### Provider License Number
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: Alpha numeric

### Provider License State
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: Alpha
Two characters (XX)

### Provider License Issued Date
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: MM/DD/YYYY

### Provider License Expiration Date
- **Requirement**: `RPD` — Required for delegated provider/location records
- **Notes / Format**: MM/DD/YYYY

### Provider Specialty Taxonomy
- **Requirement**: `RP` — Required for all provider/location records
- **Notes / Format**: Alpha numeric

### Provider CAQH ID
- **Requirement**: `RND` — Required for all non-delegated records
- **Notes / Format**: Numeric

### Supervising Physician First Name
- **Requirement**: `C1
Required for Physician Assistants` — See Summary
- **Notes / Format**: Alpha

### Supervising Physician Last Name
- **Requirement**: `C1
Required for Physician Assistants` — See Summary
- **Notes / Format**: Alpha

### Supervising Physician NPI
- **Requirement**: `C1
Required for Physician Assistants` — See Summary
- **Notes / Format**: Alpha

### Provider Board Certification Issuer
- **Requirement**: `CDP` — Conditionally required for delegates that include practices/locations/addresses
- **Notes / Format**: Alpha

### Provider Board Certification Status
- **Requirement**: `CDP` — Conditionally required for delegates that include practices/locations/addresses
- **Notes / Format**: Refer to Board Status Table
- **Allowed Values**: See *Board Certification Status* list above.

### Provider Board Certification Expiration/Recertification Date
- **Requirement**: `CDP` — Conditionally required for delegates that include practices/locations/addresses
- **Notes / Format**: MM/DD/YYYY

### Provider Language
- **Requirement**: `O` — Optional
- **Notes / Format**: Refer to Language Table
- **Allowed Values**: See *Languages* list above.

### Location Type
- **Requirement**: `R` — Required for all records
- **Notes / Format**: 1 = Practitioner (Identifies this Location is a SOLO Provider)
2 = Provider Institution/Facility
4 = Group

### Primary Address Identifier
- **Requirement**: `O` — Optional
- **Notes / Format**: 0=Not Primary
1=Primary
Blank=Not Primary

### Tax Information W9 Legal Business Name
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Institution DBA Name
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### TIN Type
- **Requirement**: `O` — Optional
- **Notes / Format**: EIN/TIN
SSN
If blank, will default to EIN/TIN

### TIN
- **Requirement**: `R` — Required for all records
- **Notes / Format**: Numeric

### Location NPI
- **Requirement**: `R` — Required for all records
- **Notes / Format**: Numeric

### Location Specialty Taxonomy
- **Requirement**: `R` — Required for all records
- **Notes / Format**: Alpha numeric

### Location Telehealth Information
- **Requirement**: `O` — Optional
- **Notes / Format**: Telehealth and Office
Only Telehealth
No Telehealth

### Mon Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Mon Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Tue Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Tue Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Wed Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Wed Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Thu Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Thu Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Fri Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Fri Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Sat Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Sat Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Sun Open Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Sun Close Time
- **Requirement**: `O` — Optional
- **Notes / Format**: HH:MM (Military)

### Location Effective Date
- **Requirement**: `RD` — Required for all delegated records
- **Notes / Format**: MM/DD/YYYY

### Location Initial Credential Date
- **Requirement**: `RD` — Required for all delegated records
- **Notes / Format**: MM/DD/YYYY

### Location Last Credentialed Date
- **Requirement**: `RD` — Required for all delegated records
- **Notes / Format**: MM/DD/YYYY

### Location Term Date
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: MM/DD/YYYY

### Location Term Reason
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: Refer to Term Reason Table
- **Allowed Values**: See *Term Reason* list above.

### Physical Address Street
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Physical City
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Physical State
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Alpha
Two characters (XX)

### Physical Zip
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Numeric

### Physical Zip Ext
- **Requirement**: `O` — Optional
- **Notes / Format**: Numeric

### Physical Phone
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Numeric

### Physical Fax
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: Numeric

### Physical Address Email
- **Requirement**: `O` — Optional
- **Notes / Format**: Well-formed email address; may be alpha numeric  
Character@Character.character
Character@Character.character.character
A@B.C or A@B.C.D

### Billing Address Street
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Billing  City
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Billing State
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Alpha
Two characters (XX)

### Billing Zip
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Numeric

### Billing Zip Ext
- **Requirement**: `O` — Optional
- **Notes / Format**: Numeric

### Billing Phone
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Numeric

### Billing Fax
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: Numeric

### Billing Address Email
- **Requirement**: `O` — Optional
- **Notes / Format**: Well-formed email address; may be alpha numeric  
Character@Character.character
Character@Character.character.character
A@B.C or A@B.C.D

### Mailing Address Street
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Mailing City
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Must be greater in length than 2 characters and may contain the following only:  
     A through Z (upper and lower case)
     0 through 9 (numbers) 
     Special Characters: # ' - . & ( ) ! + / = , % @ $ :
     Space between words is permitted

May not contain the following:
     Numeric values in the format of a SSN are not permitted (###-##-####)
     Blanks and null values are not valid

### Mailing State
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Alpha
Two characters (XX)

### Mailing Zip
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Numeric

### Mailing Zip Ext
- **Requirement**: `O` — Optional
- **Notes / Format**: Numeric

### Mailing Phone
- **Requirement**: `R (Required) if New 
C (Conditional) if Change` — See Summary
- **Notes / Format**: Numeric

### Mailing Fax
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: Numeric

### Mailing Address Email
- **Requirement**: `O` — Optional
- **Notes / Format**: Well-formed email address; may be alpha numeric  
Character@Character.character
Character@Character.character.character
A@B.C or A@B.C.D

### CMS Certification Number
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: Alpha numeric

### DRG
- **Requirement**: `O` — Optional
- **Notes / Format**: Not applicable, DRG Non-Exempt/Contracted Reimbursement Arrangement, DRG Exempt, DRG Non-Exempt

### Location License Type
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: DEA, State

### Location License Number
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: Alpha numeric

### Location License State
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: Alpha
Two characters (XX)

### Location License Issued Date
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: MM/DD/YYYY

### Location License Expiration Date
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: MM/DD/YYYY

### Location CLIA Number
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: Alpha numeric

### Location CLIA Expiration Date
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: MM/DD/YYYY

### Location Accreditation Type
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: Alpha

### Location Accreditation Expiration Date
- **Requirement**: `CDI` — Conditionally required for delegates that include individual practitioners/providers
- **Notes / Format**: MM/DD/YYYY

### Accepting New Patients
- **Requirement**: `O` — Optional
- **Notes / Format**: 1=Accepting/Open
2=Not Accepting/Closed

### Accepting New Patients Timeframe FROM
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: MM/DD/YYYY
If this is blank, the Not Accepting New Patients indicator would be on until updated

### Accepting New Patients Timeframe TO
- **Requirement**: `C` — Conditionally required (see Field Notes)
- **Notes / Format**: MM/DD/YYYY
If this is blank, the Not Accepting New Patients indicator would be on until updated

### Age Restrictions MINIMUM
- **Requirement**: `O` — Optional
- **Notes / Format**: Numeric
If this field is blank, no Age Restriction will be populated

### Age Restrictions MAXIMUM
- **Requirement**: `O` — Optional
- **Notes / Format**: Numeric
If this field is blank, no Age Restriction will be populated

### Gender Restrictions
- **Requirement**: `O` — Optional
- **Notes / Format**: M / F / B
M = Male, F = Female, B = Both

### Urgent Care Info
- **Requirement**: `O` — Optional
- **Notes / Format**: Yes or No indicator
If Blank=No

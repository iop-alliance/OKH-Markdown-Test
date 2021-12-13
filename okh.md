# **The Open Know-How Manifest Specification Version 1.0**
## **Introduction**

Open Know-How is all about sharing knowledge on how to make things. With dozens of open hardware organisations and over 80 content-hosting platforms and thousands of designers sharing open hardware designs, there is little consistency as to how know-how is documented or shared. Makers struggle to locate what they need, not knowing which platform to find it, what the intended use is and therefore struggle to adapt designs. Whilst the knowledge is 'open', it is not freely flowing in the spirit that open-ness suggests.


The objective of this specification is to improve the open-ness of know-how for making hardware by improving the discoverability, portability and translatability of knowledge.


Knowledge, unlike data or information, is tacit. Documentation and representation of knowledge can take different forms for different types of hardware and audience, and specifying how knowledge is represented can limit innovation and usability in different contexts. Therefore, this specification introduces a maturity model for increasing specifications for knowledge. The intent is that a designer or platform can choose to adopt this specification appropriately, rather than an over-prescriptive approach that deters adoption. Later iterations of this standard will include specifications for different representations of knowledge, but at this stage the scope is limited to supporting the discoverability of open hardware regardless of where it resides on the World Wide Web.

### **A conceptual model for the maturity of interoperable Open Know-How**

This specification introduces a progressive approach to making knowledge about hardware interoperable. Through the maturity levels defined in the table below.

|**Maturity Level**|**Description**|
|--|--|
|**Level 1 Discoverable Know-How** |Allows know-how to be discovered, indexed and linked to using meta-data about the thing and the location of know-how.|
|**Level 2 - Portable Know-How**|Provides a format and structure for know-how so that it is represented in a consistent format and can be easily moved between platforms.|
|**Level 3 - Distributed Know-How**|Supports interoperability, creation and aggregation of know-how about a thing by different designers and makers without centralised control of the know-how.|

The mandatory aspects of this specification are kept to a minimum to lessen the friction for those who want to make their know-how discoverable. The intent behind the maturity model as presented is that the more of the recommended and permissive aspects of this specification that are adopted, the more open the know-how becomes. 


To support the use of know-how by speakers of different languages, translation of Know-How is accommodated at all maturity levels.

### **About the authors**
#### **Development of specification**

This specification has been developed by members of the Open Know-How Working Group, part of the [Internet of Production Alliance](https://www.internetofproduction.org), and supported by the Shuttleworth Foundation. The following have contributed directly towards the development of this standard:

|**Name**|**Organisation**|
|--|--|
|Jérémy Bonvoisin|University of Bath|
|Richard Bowman|University of Bath|
|Andre Maia Chagas|The University of Sussex, Mozilla Fellow 18/19|
|Pierre-Alexis Ciavaldini|MakerNet.org|
|Kaspar Emanuel|Kitspace.org|
|Martin Häuer|OSE Germany|
|Brynmor John|Field Ready|
|Andrés Barreiro|Wikifactory|
|Kshitiz Khanal|Kathmandu Living Labs|
|Andrew Lamb (Chair)|Field Ready, Shuttleworth Fellow|
|Anna Lowe|Manufacturing Change|
|Jenny Molloy|University of Cambridge|
|Neil Noble|ex-Practical Action|
|Nathan Parker|MakerNet.Work|
|Jon Schull|e-Nable|
|Balthas Seibold|GIZ|
|Julian Stirling|University of Bath|
|Emilio Velis|Appropedia|
|Michael Weinberg|Open Source Hardware Association (OSHWA)|
|Tobey Wenzel|Docubricks|
|Diderik van Wingerden|Think-innovation.com|
#### Technical authoring

Technical authoring for version 1 has been undertaken by Barbal Limited.

## **Scope**

This specification provides a mechanism for exchanging know-how for making things. It aligns with the Open Source Hardware Definition [[1]](#Ref1) and other efforts to standardise approaches for documenting how to make things. 


This version specifies the approach to Open Know-How Level 1 by providing a schema for providing metadata in a consistent format and a mode of information exchange enabling indexing and discovery of open hardware by stakeholders. 


The intended audience is:


* Designers who publish their documentation in self-hosted or generic file repositories
* Platforms that provide tools for designers to publish their documentation online
* Platforms that aggregate, index or link to open hardware designs




## **Terms and definitions**
### **know-how**

knowledge for how to make a thing


Note: Whilst know-how can be tacit, this specification is concerned with know-how represented in documentation, drawings, digital models, source code and other media

### **design**

specification of the thing in terms of its form and functionality

### **designer**

person who produces designs and/or know-how for making things

### **make**

manufacture, construct, assemble, print, configure, compile or create using another method

### **maker**

person who makes using know-how

### **platform**

website or web application that provides tools for hosting or processing know-how

### **thing**

physical item defined by know-how

#### derivative

thing where the know-how is based on modifications to the know-how for another thing

#### original

thing from which the know-how a derivative or variant is created

#### sub-thing

thing that is used as a component, part or module of another thing

#### variant

sub-version of a thing which has specific documentation compiled to support that specific variant


Example: Where a component of a thing can be printed, cast or whittled and the original documentation contains making instructions for each. The variant documentation only contains making instructions for that specific variant.


Note: Does not include translations (which are handled separately) nor adapted versions of the same know-how (e.g. published in alternative formats).

### user

person who uses the made thing




## **Specification for Open Know-How Level 1 - Discoverable Know-How**
### **Introduction**

This section specifies a mechanism for making know-how discoverable. It describes a schema for meta-data relating to designs and the location of associated know-how through a manifest.


Mandatory and recommended provisions are made along with other fields that are defined. A template is provided to aid production of the manifest.

### **Method of information exchange -  the Open Know-How Manifest**

The Open Know-How Manifest accompanies the Know-How that is documented in structured or unstructured formats. The purpose is to allow automated indexings of key properties about the thing and to identify and link to the associated documentation.


The manifest shall be used to define a version of the thing. A separate manifest should be produced for each new version, variant or derivative of the thing.


The manifest should be revised when any of the properties it defines are changed.

### **Structure of the Open Know-How Manifest as a file**
#### **Format**

Where the manifest is contained in a file, the Open Know-How Manifest uses the YAML v1.2 format [[2]](#Ref2).


Note: YAML has been selected as the file format for its ease of producing and reading by people.


Encoding shall be UTF-8.


The character set shall be Unicode.

#### Filename

The file containing the manifest shall begin with "okh".


The file extension shall be ".yml".


Example: "okh.yml"


The thing's name may be included in the filename, prefixed with a hyphen.


Example: "okh-thingname.yml"

#### **Declaration**

The manifest shall be declared by including the following as line 1 and 2:

```%Open Know-How Manifest 1.0
--- 
```
#### Absolute and relative links

Where a field requires a link to an external resource or path, absolute or relative paths may be used.


Relative paths shall be relative to the location of the Open Know-How Manifest in the documentation repository. 


Absolute paths shall include the full path to the resource including the protocol. 


Paths shall use forward slashes.

#### Location of the manifest

Where a file repository is used, the manifest should be stored in the root folder.


Where a platform does not use a file repository, the manifest should be linked to from the Project Homepage.

### **Embedding manifest information in a web page**

Where platforms choose to adopt the manifest by embedding the schema into pages, rather than producing a separate manifest file, the schema presented in this section may be applied as a microformat within the page HTML using classes. 


To declare the open know-how schema, apply the "`open-know-how v0-1`" classes to the parent HTML element.


Where this approach is adopted, the manifest content shall be contained within a single web page. A manifest shall not be distributed across more than one page.

### **Manifest metadata**
#### **Date created**

Fieldname: `date-created`


Purpose: Indicates the date the manifest was originally created.


Format: `YYYY-MM-DD`

#### **Date last updated**

Fieldname: `date-updated`


Purpose: Indicates the date the manifest was last edited.


Format: `YYYY-MM-DD`

#### **Manifest content originator**

Fieldname: `manifest-author`


Purpose: States the person who has created and is responsible for the content in the manifest.


Note: As the manifest can be automatically generated, this relates only to the content of the manifest and not the production of the manifest itself.


Format:

```manifest-author:
  name: [value]           # Text
  affiliation: [value]    # Text
  email: [value]          # Email address
```

Rules: The name field is required. Other fields are optional.

### **Descriptive properties**
#### **Title**

Fieldname: `title`


Purpose: A title to identify the thing.


Format: Text.


Rules: Required.

#### Description

Fieldname: `description`


Purpose: Describes the thing.


Format: Paragraph.


Rules: Required.

#### **Intended use**

Fieldname: `indended-use`


Purpose: Informs the maker for what purpose the designer intends the thing to be used. In particular, make reference to the context and type of users.


Format: Paragraph.


Rule: Recommended.

#### Keywords

Fieldname: `keywords`


Purpose: Provides a small number of terms that can be used to help identify.


Format: Array of text.


Rule: At least one keyword is recommended.




#### Project Homepage

Fieldname: `project-link`


Purpose: Where the thing or associated project has a web presence that is separate from the documentation (e.g. a marketing page), links to the web resource.


Format: Absolute path.


Rules: At least one of the `project-link` or `documentation-home `fields is required.

#### Health and safety notice

Fieldname: `health-safety-notice`


Purpose: Highlight health and safety risks and/or necessary precautions that the maker should be aware of as part of the decision to make the thing.


Format: Paragraph


Rules: Not an exhaustive list of all risks associated with the thing, but a summary of the most important risks and hazards associated with making, using, maintaining or disposing. Knowledge of such issues could influence the decision to make the thing.

#### Primary contact

Fieldname: `contact`


Purpose: Provides a point of contact for people who wish to discuss the thing.


Format:

```contact:
  name: [value]             # Text
  affiliation: [value]      # Text
  email: [value]            # Email address
  social:                   # Lists other web-presences through which contact can be made 
    - platform: [value]     # Text
      user-handle: [value]  # Text
```

Rules: Where used, provide at least one email address or social media user handle.
#### Contributors

Fieldname: `contributors`


Purpose: Credits the contributors to the know-how. May include people who designed, produced documentation, tested the documentation by making, reviewed and/or edited documentation, or made another contribution as deemed valued by the project or `manifest-author`.


Format: List of contributors

```contributors:
  - name: [value]          # Text
    affiliation: [value]   # Text
    email: [value]         # Email address
```

Rules: Recommended. A name is required for each contributor listed.

#### Image

Fieldname: `image `


Purpose: Provides a graphical representation of the thing.


Format: Absolute or relative path to image file.


Rule: Recommended.

#### Thing version

Fieldname: `version`


Purpose: Defines the version of the thing that is represented by this manifest.


Format: Text.

#### Stage of development

Fieldname: `development-stage`


Purpose: Indicates the maturity of the design and documentation development.


Format: Text


Note: The Open Know-How Working Group intends to develop recommended values for this field to support commonality across manifest files. This is likely to be made by reference to a external standard.

#### Has been made

Fieldname: `made`


Purpose: Indicates whether the thing has been made and verifies that it is makeable.


Format: Boolean - "`true`" or "`false`"

#### Has been made independently

Fieldname: `made-independently`


Purpose: Indicates whether the thing has been made using the documentation by someone who was not a contributor to the design or documentation and, therefore, verifies that the documentation is sufficient to make the thing.


Format: Boolean - "`true`" or "`false`"

#### Standards used

Fieldname: `standards-used`


Purpose: Indicates any standards that have been used in developing the design or documentation.


Format: Array of arrays.

```standards-used:
  - standard-title: [value]       # Required where used | Title of the standard used in developing the design or documentation
    publisher: [value]            # Publisher of the standard
    reference: [value]            # Reference indentifier of the standard (e.g. ISO 9001)
    certification:                # If certification has been granted confirming compliance with the standard
      - certifier: [value]        # Individual or organisation granting the certification. Use "Self" for self-certification
        date-awarded: [value]     # Date certification was granted
        link: [value]             # Link to evidence of certification (e.g. certificate). Use an an absolute path to an external resource or an absolute or relative path to evidence within the documentation.
```

Rules: Do not list standards to be used by the maker or user, instead these should be referenced in the relevant documentation.

#### Derivative of

Fieldname: `derivative-of`


Purpose: Where the thing is a derivative of a different thing (e.g. the documentation has been forked), links to the original thing.


Format:

```derivative-of:  
  title: [value]        # text | Title of the original
  manifest: [value]     # URL - Absolute path | OKH manifest location
  web: [value]          # URL - Absolute path | web presence location
```

Rules: Where `derivative-of` used, the `title` sub-field is required.

#### Variant of

Fieldname: `variant-of`


Purpose: Where the thing is a variant, links to the original.


Format:

```variant-of:    
  title: [value]       # text | Title of the original
  manifest: [value]    # URL - Absolute path | OKH manifest location
  web: [value]         # URL - Absolute path | web presence location 
```
#### **Sub-thing**

Fieldname: `sub`


Purpose: Where the design uses sub-components, sub-assemblies etc that are also available as open know-how, links to the documentation.


Format: List of sub-things

```sub:  
  title: [value]      # text | Title of the original
  manifest: [value]   # URL - Absolute path | OKH manifest location
  web: [value]        # URL - Absolute path | web presence location
```
### License information
#### License

Fieldname: `License`


Purpose: States the licenses under which the thing is made available.


Format:

```license: 
  hardware: [value] 
  documentation: [value] 
  software: [value] 
```

Rules: At least one license is required. All three license types are recommended. The format should be an SPDX identifier. See [https://spdx.org/licenses/](https://spdx.org/licenses/)

#### Licensor

Fieldname: `licensor`


Purpose: States who is licensing the thing.


Format:

```licensor: 
  name: [value]           # text
  affiliation: [value]    # text
  email: [value]          # email address
```
### **Documentation**
#### **Entry point to documentation**

Fieldname: `documentation-home`


Purpose: Provides a URL entry point to the documentation.


Format: Absolute path.


Rules: At least one of the `project-link` or `documentation-home `fields is required.

#### Documentation archive

Fieldname: `archive-download`


Purpose: Links to a location from which the full documentation can be downloaded as an archive (e.g. zip file).


Format: Absolute or relative path.

#### Design Files

Fieldname: `design-files`


Purpose: Links to design files.


Format: Absolute or relative path.

```design-files:
  - path: [value]         # Absolute or relative path
    title: [value]        # text
```

Rules: Recommended. May either refer to a location in which files are stored or can list and link to design files individually. In the former case, the title field is not required.

#### Schematics

Fieldname: `schematics`


Purpose: Links to schematics. Includes all types of engineering drawings.


Format: Absolute or relative path

```schematics:
  - path: [value]     # Absolute or relative path
    title: [value]    # text
```
#### Bill of Materials

Fieldname: `bom`


Purpose: Links to the bill of materials.


Format: Absolute or relative path.


Rules: Recommended. Should be provided as a single file.

#### List of Tools

Fieldname: `tool-list`


Purpose: Links to a list of tools required to make the thing.


Format: Absolute or relative path.


Rules: Recommended. Should be provided as a single file.

#### **Assembly Instructions**

Fieldname: `making-instructions`


Purpose: Links to the making instructions, e.g. assembly instructions.


Format: 

```making-instructions:
  - path: [value]      # Absolute or relative path
    title: [value]     # text
```

Rules: Recommended. May include more than one assembly instructions, e.g. where the instructions are provided in different formats.

#### Manufacturing files

Fieldname: `manufacturing-files`


Purpose: Links to the manufacturing files, such as 3D printing files.


Format: 

```manufacturing-files:
 - path: [value]       # Absolute or relative path
   title: [value]      # text
```

Rules: Recommended where applicable. 

#### Risk Assessment

Fieldname: `risk-assessment`


Purpose: Links to the risk assessment.


Format: 

```risk-assessment:
  - path: [value]     # Absolute or relative path
    title: [value]    # text
```

Rules: Recommended. May include more than one, e.g. where different assessments cover different aspects or making, operation, maintenance and disposal.

#### Tool settings and documentation

Fieldname: `tool-settings`


Purpose: Links to settings for tools and machines.


Format: 

```tool-settings: 
  - path: [value]     # Absolute or relative path 
    title: [value]    # text
```

Rules: Recommended where applicable. May include more than one.

#### Quality control instructions

Fieldname: `quality-instructions`


Purpose: Links to instructions for testing and/or quality management.


Format: 

```quality-instructions:
  - path: [value]     # Absolute or relative path
    title: [value]    # text
```

Rules: Recommended. May include more than one.

#### Operating instructions

Fieldname: `operating-instructions`


Purpose: Links to instructions for operating the thing.


Format: 

```operating-instructions:
  - path: [value]    # Absolute or relative path
    title: [value]   # text
```

Rules: Recommended.

#### Maintenance instructions

Fieldname: `maintenance-instructions`


Purpose: Links to instructions for maintaining the thing.


Format: 

```maintenance-instructions:
  - path: [value]    # Absolute or relative path
    title: [value]   # text
```

Rules: Recommended.

#### Disposal instructions

Fieldname: `disposal-instructions`


Purpose: Links to instructions for disposing the thing at the end of its life.


Format: 

```disposal-instructions:
  - path: [value]    # Absolute or relative path
    title: [value]   # text
```

Rules: Recommended.

#### Software

Fieldname: `software`


Purpose: Links to source code repository or software executables used by the thing.


Format: 

```software:
 - path: [value]     # Absolute or relative path
   title: [value]    # text
```

Rules: Recommended where applicable. May include more than one.

### **Language and translation**
#### **General******

Language shall be declared as defined in BCP 47 [4], which prescribes the format for identifying languages as the ISO 639 [5] codes for representing languages followed by the ISO 3166 [6] code for the region in which the language is used. Use the Alpha-2 code for each where available.

#### Manifest Language

Fieldname: `manifest_language`


Purpose: States the language in which the manifest has been produced.


Format: `[language-code]-[region]`


Rule: ISO 639 [5] language code. Use the Alpha-2 code where available. Optionally, the ISO 3166 [6] country code may be included as per BCP 47 [4].

#### Documentation Language

Fieldname: `documentation_language`


Purpose: States the language in which the documentation has been produced.


Format: `[language-code]-[region]`


Rule: ISO 639 [5] language code. Use the Alpha-2 code where available. Optionally, the ISO 3166 [6] country code may be included as per BCP 47 [4].

#### Translated Manifest

Fieldname: `manifest-is-translation`


Purpose: Where this manifest is a translation of another, links to the original.


Format:

```manifest-is-translation:    
  title: [value]               # text | Title of the original
  manifest: [value]            # URL - Absolute path | OKH manifest location
  web: [value]                 # URL - Absolute path | web presence location
  lang: [language]-[region]    # language of original 
```
#### Translated Documentation

Fieldname: `documentation-is-translation`


Purpose: Where this manifest references documentation that is translated, links to the original.

```documentation-is-translation:  
  title: [value]               # text | Title of the original
  manifest: [value]            # URL - Absolute path | OKH manifest location
  web: [value]                 # URL - Absolute path | web presence location
  lang: [language]-[region]    # language of original
```
### **Extending the manifest schema**

The manifest schema may be extended where this specification is not sufficient to meet the needs of the project.


When extending the schema, only siblings may be added to defined fields. New children shall not be added to fields where a child is not already defined.


Users are encouraged to share any extension of the schema with the Open Know-How Working Group so that it can be considered for future revisions of this specification.

### **Version management of the manifest**

This specification does not include provision for version management of the manifest. The context of the file from the HTTP headers, repository or page hosting the manifest can give information relating to revision or status of the manifest relative to other versions that can be located on the world wide web.

### **Template**
```%Open know-how manifest 0.1
---

# The content of this manifest file is licensed under a Creative Commons Attribution 4.0 International License. 
# Licenses for modification and distribution of the hardware, documentation, source-code, etc are stated separately.

# Remove any fields that are not used. Comments (beginning with '#') may also be removed.

# Manifest metadata

date-created: [value]                      # YYYY-MM-DD

date-updated: [value]                      # YYYY-MM-DD

manifest-author:
  name: [value]                            # required | text
  affiliation: [value]                     # text
  email: [value]                           # email address

manifest-language: [language-code]-[region] 

documentation-language: [language-code]-[region] 

manifest-is-translation:  
  title: [value]                           # text | Title of the original
  manifest: [value]                        # URL - Absolute path | OKH manifest location
  web: [value]                             # URL - Absolute path | web presence location
  lang: [language]-[region]                # language of original

documentation-is-translation:  
  title: [value]                           # text | Title of the original
  manifest: [value]                        # URL - Absolute path | OKH manifest location
  web: [value]                             # URL - Absolute path | web presence location
  lang: [language]-[region]                # language of original

# Properties

title: [value]                             # required | text | A title to identify the thing

description: |                             # required | paragraph
  [value]

intended-use: |                            # recommended | Paragraph
  [value]

keywords:                                  # At least one keyword is recommended | text array 
  - [keyword 1]
  - [keyword 2]

project-link: [value]                      # At least project-link or documentation-home is required, otherwise recommended | absolute path URL

health-safety-notice: |                    # paragraph
  [value]

contact:
  name: [value]                            # text
  affiliation: [value]                     # text
  email: [value]                           # email address
  social:
    - platform: [value]                    # text
      user-handle: [value]                 # text

contributors:                              # recommended
  - name: [contributor 1]                  # text
    affiliation: [value]                   # text
    email: [value]                         # email address

image: [value]                             # recommended | absolute or relative path

version: [value]                           # text

development-stage: [value]                 # text

made: [true/false]                         # boolean - true or false

made-independently: [true/false]           # boolean - true or false

standards-used:
  - standard-title: [value]                # Required where used | Title of the standard used in developing the design or documentation
    publisher: [value]                     # Publisher of the standard
    reference: [value]                     # Reference indentifier of the standard (e.g. ISO 9001)
    certification:                         # If certification has been granted confirming compliance with the standard
      - certifier: [value]                 # Individual or organisation granting the certification. Use "Self" for self-certification
        date-awarded: [value]              # Date certification was granted
        link: [value]                      # Link to evidence of certification (e.g. certificate). Use an an absolute path to an external resource or an absolute or relative path to evidence within the documentation.

derivative-of:  
  title: [value]                           # text | Title of the original
  manifest: [value]                        # URL - Absolute path | OKH manifest location
  web: [value]                             # URL - Absolute path | web presence location

variant-of:  
  title: [value]                           # text | Title of the original
  manifest: [value]                        # URL - Absolute path | OKH manifest location
  web: [value]                             # URL - Absolute path | web presence location

sub:  
  title: [sub 1]                           # text | Title of the original
  manifest: [value]                        # URL - Absolute path | OKH manifest location
  web: [value]                             # URL - Absolute path | web presence location

# License 

license:                                   # At least one license is required | The format should be an SPDX identifier. See [https://spdx.org/licenses/](https://spdx.org/licenses/)hardware: [value] # recommended | The license under which the hardware is released
  hardware: [value]                        # recommended | The license under which the documentation is released
  documentation: [value]                   # recommended | The license under which the documentation is released
  software: [value]                        # recommended where software is used | The license under which the software is released

licensor: 
  name: [value]                            # text
  affiliation: [value]                     # text
  email: [value]                           # email address

# Documentation

documentation-home: [value]               # At least one of the project-link or documentation-home fields is required | absolute path

archive-download: [value]                 # Absolute or relative path

design-files:                             # recommended
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

schematics:                               # recommended where applicable 
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

bom: [value]                              # recommended | absolute or relative path | Direct the maker to the Bill of Materials

tool-list: [value]                        # recommended | absolute or relative path | Direct the maker to a list of tools required to make the thing

making-instructions:                      # recommended
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

manufacturing-files:                      # recommended where applicable
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

risk-assessment:                          # recommended 
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

tool-settings:                            # recommended where applicable
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

quality-instructions:
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

operating-instructions:                   # recommended
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

maintenance-instructions: [value]         # recommended
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

disposal-instructions: [value]            # recommended
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

software:                                 # recommended where applicable | Source code or executable software that the thing uses
  - path: [value]                         # Absolute or relative path
    title: [value]                        # text

# User defined Fields 
# Include any custom / extended fields here
```
## **Governance of this Specification**

The Open Know-How Specification is governed by the Open Know-How Working Group.


Changes to the Specification are proposed in StandardsRepo.


Changes are voted on during meetings of the Open Know-How Working Group. 


Proposers should consult the Working Group prior to proposing changes so that members can contribute to the development of proposals. This can increase the likelihood of the group accepting changes to the specification.

## **Bibliography**

[[1]](#Ref1use) Open Source Definition, Open Source Hardware Association, [https://www.oshwa.org/definition/](https://www.oshwa.org/definition/)


[2] YAML Version 1.2, Oren Ben-Kiki, Clark Evans, Ingy döt Net, [https://yaml.org/spec/1.2/spec.html](https://yaml.org/spec/1.2/spec.html)


[3] SPDX License List, [https://spdx.org/licenses/](https://spdx.org/licenses/)


[4] BCP 47 Tags for Identifying Languages, IETF, [https://tools.ietf.org/html/bcp47](https://tools.ietf.org/html/bcp47)


[5] Codes for the Representation of Names of Languages, Library of Congress, [http://www.loc.gov/standards/iso639-2/php/code_list.php](http://www.loc.gov/standards/iso639-2/php/code_list.php)


[6] Country Codes - ISO 3166, ISO, [https://www.iso.org/iso-3166-country-codes.html](https://www.iso.org/iso-3166-country-codes.html)


Note: Country codes as listed in ISO 3166 can be found using the ISO Online Browsing Platform [https://www.iso.org/obp/ui/#search](https://www.iso.org/obp/ui/#search)





[![Creative Commons Licence](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)




The Open Know-How Specification by [MakerNet Alliance](https://makernetalliance.org/) is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).



Based on a work at [https://app.standardsrepo.com/MakerNetAlliance/OpenKnowHow](../../../).






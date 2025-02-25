> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 5 Federated architecture: data layer
## Federation metadata

Our concept of Federation metadata covers high-level descriptions of all the elements of the SDRI Federation, from the services that comprise its infrastructure to the data, users and projects that make it useful. It is descriptive of the Federation and its activities, and provides a very high-level view of data assets within the Federation, but does not include rich, detailed descriptions of these data assets. How best the technical infrastructure could support rich discovery and exploration of datasets from many different disciplines is a challenging question.

For now, we divide Federation metadata into three groups: metadata that capture information about the Federation itself (infrastructure metadata); metadata that capture information about the datasets accessible within the Federation (content metadata); and metadata that capture information about what purposes the Federation is being used for (we can call this governance metadata). By construction, these map to the three layers of the SDRI Federation.

In general, the visibility of metadata—private to a Participant, private to the Federation as a whole, or public—should be determined and agreed by Federation governance rules, perhaps following a “need to know” approach. Some examples:
 * Public: names of Participants in the Federation; names of Datasets available within the Federation; counts and names of active Projects; counts of active Researchers; …
 * Federation-private: Federation identities of Participants and other entities and artifacts; service capabilities; Project risk-management information; …
 * Participant-private: Researchers’ and other users’ contact details; …

### Infrastructure metadata

Our definition of infrastructure metadata is best captured by the answer to the question: if the Federation had no users at all, what metadata would we still need to describe it? We divide this further into static descriptive metadata that describe the Federation “at rest” and dynamic operational metadata that describe it “in motion”.

#### Descriptive metadata (Federation at rest)

The [Participants](../4_Infrastructure_Layer/4_3_Participants.md) require machine-readable descriptions which shall be recorded in the Registry Services, and which provide enough information to be reasoned about (e.g., for the purposes of automation).

Examples of descriptive metadata are:
 * Basic metadata: name, Federation identity, …
 * Capabilities: available computation; available software; …
 * Datasets hosted (persistently available not project-specific): count; list of Federation identities; …
 * Indexes hosted (types of linkage available): list of Federation identities; …

Most descriptive metadata should be visible within the Federation.

Some may be visible publicly (meaning able to be published rather than exposed directly from within the Federation to the public Internet!). 

#### Operational metadata (Federation in motion)

Operational metadata are metadata captured and recorded through the operation of the Federation and its Participants. 
Operational metadata notably include information on data exchange logged by the Participant Security Servers and by the Federation Services.

Clear governance rules must be established around the use of operational metadata. It must be clear, for instance, which metadata logged within a Participant’s Security Server are private to the Participant, which may be shared with Federation Services, and which might be visible to other Federation Participants.

No operational metadata should ever be visible to the public.

### Content metadata

Content metadata describe, at a high level, the Datasets the Federation supports. When structuring metadata to describe such concepts steps should be taken to eliminate or reduce any duplication of information that would risk drift, divergence or fragmentation.

#### Dataset metadata

Datasets, while treated as dynamic, are potentially persistent and long-lived. Dataset metadata should record information about the data themselves, including the Data Controllers accountable for their use, but not things like where they can be accessed. The latter information should be left to the hosting Participant to advertise, and to the Federation Registry and Discovery Services to collate for search and discovery purposes. For example:
 * Dataset record:
   - Name: Covid-19 self-reported symptoms in London, 2020
   - Federation identity: ee6574ac-8ad7-440c-8200-ca86dd556bbf
   - Data controller: …
 * TRE record:
   - Name: SAIL Databank
   - Federation identity: 5756f2c9-c6f3-4fcf-8d81-c4647e2a12bb
   - Datasets hosted: {ee6574ac-8ad7-440c-8200-ca86dd556bbf; …}
   - …

The dynamic nature of datasets arises not from their ephemerality or their movement around the Federation but from their changeability. Datasets are updated (new entries made, old entries pruned) and their schemas or formats change (more slowly). How different versions of a dataset should be managed and recorded is out of scope, but we would recommend that its Federation identity remain unchanged, just as its name would.

Summary metadata for a Dataset will be public, perhaps conforming to a common high-level catalogue schema. As a current starting point for defining the required fields in these high-level metadata records we would recommend Appendix A of the UK Statistics Authority DEA Data Capability Guidance [[49]](../References.md#ref-49). We use this to derive the example metadata records below, our goal being to design defensively and align Federation metadata as closely as possible with anticipated governance or accreditation requirements. 

> The UK Statistics Authority Digital Economy Act scheme for UK-based processors of statistical data is a rigorous approach to accreditation but does not cover health-related data. However it has been announced (June 2023; see https://transform.england.nhs.uk/key-tools-and-info/data-saves-lives/data-saves-lives-implementation-update/) that the UK NHS and Statistics Authority will work together to co-design an updated version of the DEA scheme suitable for both statistical and health data.

Particular data domains may, of course, introduce their own standards, and commonality will need to be distilled and agreed accordingly. (In the health domain, for example, the HDR Alliance have defined a useful standard for data use registers [[50]](../References.md#ref-50).)

Some detailed Dataset metadata will be Federation-private.


|      | Example metadata record: Dataset |
| ---- | -------------------------------- |
| Id                                   | A unique Federation identity number for the Dataset. |
| Data name                            | A unique name provided to identify the Dataset. |
| Data description                     | A short description. |
| Data classification                  | The type of data (perhaps using a controlled terminology such as Dublin Core, eg, household survey data, administrative data, open data). |
| Data keywords                        | A set of related keywords. |
| Data supplier                        | The owner or supplier of the data. For personal data this should be the data controller. |
| Time coverage – start                | The first point in time the data covers. |
| Time coverage – end                  | The latest point in time the data covers. |
| Data frequency                       | Where the data have a temporal frequency. |
| Update frequency                     | Where data are updated in their hosting provider environment. |
| Geography                            | The levels of geography included in the data. |

### Governance metadata

What we term governance metadata covers the users of the Federation and the activities they carry out. Central to this idea is the concept of the Project: any and all research activities across the Federation are conducted within the contexts of Projects.

Governance metadata should be viewed as a machine-readable form of the record-keeping required of TREs, data providers and researchers under research approval and accreditation regimes. As with Dataset metadata above, we recommend making use of prevailing information governance requirements to drive the metadata standards within the Federation. Where multiple accreditation regimes exist a degree of harmonisation or duplication will be required in metadata records. As before, we use the current DEA standard to derive the example metadata records below.

#### Project metadata

As discussed in Chapter 4 the Project is a strong concept within the Federation. Projects are conceived outside the Federation and, once approvals are in place, are instantiated in a hosting TRE. At the point of Project instantiation, the hosting TRE should register the Project’s existence with the Federation Registry Service.

A Project’s metadata should encapsulate its scope including its hosting TRE, the Datasets or Data Extracts it has permissions to work with, the Researchers permitted to work on it, its start and end dates and so on. It should be detailed enough that authorisation or disclosure decisions can be taken by Federation Participants, for example upon receipt of a remote query. 
Most metadata for a Project will be public.

Some detailed Project metadata may be Federation-private, and some may be Participant-private (e.g., held by the instantiating TRE).

|                                      | **Example metadata record: Project** |
| ------------------------------------ | ------------------------------------ |
| Id                                   | A unique Federation identity number for the Project. |
| Project title                        | The official Project title as approved . |
| Project abstract                     | A short paragraph summarising the purpose of the Project. |
| Expected public benefits             | A short paragraph summarising the expected public benefits. |
| Project keywords                     | A set of keywords describing the Project. |
| Project start date                   | The date this Project started in the hosting TRE. A Project is considered to start in a TRE when Researchers have access to the TRE and all data as approved in the Project application. |
| Project end date                     | The expected end date of the Project. |
| Host research environment            | The name of the hosting TRE where research will take place. In the case of a Project involving federated analytics this should be the TRE which instantiates the Project. |
| Research environments                | A list of any and all other TREs involved in the research—for instance in the case of a Project involving federated analytics. |
| Research sponsor                     | The name(s) of the organisations sponsoring this research. |
| Project approval on                  | The date this Project was approved by its governing authority. |
| Ethical approval on                  | The date ethical consideration/approval was given to this Project. |
| Ethical approval by                  | Who provided ethical approval for the Project. |
| Ethical restrictions                 | Any restrictions identified as part of the ethical approval. |
| Research Lead                        | The Federation identity for the lead Researcher (often termed ”principal investigator” in academic projects). |
| Researchers                          | A list of Federation identities for all other Researchers on the Project. |
| People restrictions                  | Any restrictions on the people involved in this project identified as part of the Project accreditation. |
| Data used                            | A list of Federation identities for all Data Extracts used in this Project. |
| Data restrictions                    | Any restrictions on the data available to the project identified as part of the Project accreditation. |
| Dissemination restrictions           | Any restrictions on the dissemination of research outputs identified as part of the Project accreditation. |

#### User metadata

Researchers within the Federation may be, and indeed should be able to be, involved in multiple Projects concurrently. Not all of these Projects need be hosted by the same participating TRE; thus Researchers will need a registered Federation identity which is common across all Participants. This echoes current best practice in DEA-accredited TREs where a researcher’s “identity number” is provided centrally by the UK Statistics Authority (the accreditation authority for DEA standards).

The primary reason we classify metadata for Researchers (and other users such as TRE Operators or Data Service Operators) under “governance” is that best practice captured in the Five Safes phrase “Safe People” requires all users or handlers of sensitive data to be trained or accredited to an acceptable level. 

“Acceptable” here typically means acceptable to the governance authority concerned with the data in question. The DEA record required for a researcher places a strong emphasis on this aspect, suggesting the example metadata record below.

|                                         | **Example metadata record: Researcher** |
| --------------------------------------- | --------------------------------------- |
| Id                                      | A unique Federation identity number for the Researcher. |
| Full name                               | This should include any middle names as recorded in official documents. |
| Research affiliation(s)                 | Where the Researcher has affiliation to an organisation or organisations all these affiliations should be recorded. |
| Type of accreditation                   | Provisional/Full accreditation. |
| Training course                         | The name of the training course attended as part of the accreditation. |
| Course provider                         | The organisation responsible for delivering this course. |
| Trained on                              | The date the researcher attended the training course. |
| Assessed on                             | The date the researcher completed the assessment. |
| Accredited on                           | The date the researcher was accredited. |

#### Data Extract Metadata

We define Data Extracts as snapshots created from Datasets according to some query—a cohort definition, for instance.

Data Extracts are one kind of structured data exchanged between Participants.

Metadata for Data Extracts will be logged by the secure data exchange layer and so must prove useful in that context (e.g., for audit purposes). Attributes could include: Data Controller; “parent” Dataset; version or timestamp of parent Dataset at extract creation; etc.

### Structured data packaging formats

While the contents of metadata records will be driven by governance requirements, the format into which they are packaged for exchange between TREs or other services is an entirely technical decision. 

The 2023 DARE UK Driver Projects pioneered the development and use of a 
[“Five Safes” profile](https://trefx.uk/5s-crate/0.4/) of the international 
[RO-Crate standard](https://www.researchobject.org/ro-crate/1.2-DRAFT/) for structured data packaging. 
RO-Crate (“Research Objects + DataCrates”) extends the 
[BagIt file packaging format](https://datatracker.ietf.org/doc/html/rfc8493 ) to include standard representation for machine-actionable metadata. The “Five Safes” RO-Crate profile adds additional metadata structure useful in the TRE context. 

The “Five Safes” RO-Crate profile has been demonstrated as fit for purpose in prototype implementations of this architectural blueprint and so we suggest that “Five Safes” RO-Crate be adopted as the packaging format for all structured data objects in the Federation (cf. Requirement R123 in [Appendix D](../7_References_And_Appendices/Appendix_D.md)).

### Other considerations

Many exchanges of structured data within the Federation will occur in a Project context: an initial Data Extract sent at Project instantiation (see above); a Linkage Spine created to connect extracts to create a Project’s working dataset; a query, sent from a TRE to one or more remote data providers.

We RECOMMEND that all such exchanges of structured data objects be tagged with a metadata record indicating this Project context. 

----

| [< Introduction](5_1_Introduction.md) | - | [Data findability >](5_3_Data_Findability.md) |
| ---- | ---- | ---- |





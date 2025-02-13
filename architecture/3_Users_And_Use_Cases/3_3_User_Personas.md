> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 3 Users and use-cases
## User personas

DARE UK has worked with relevant community groups across the UK to develop user personas to represent classes of users. Personas give voice and motivation to the abstract “actors” used later in our system architecture and consequently are a better source of genuine use-cases. In particular, a persona’s needs and motivations can be a better tool to identify non-functional requirements (how safely? how quickly?) than abstract system roles. 

Table 1 summarises DARE UK’s user personas. Phase 1a focussed on developing data supplier and data consumer personas. Phase 1b filled out the personas for the service provider roles.

Often it is easy to associate a particular persona with a single type of actor; sometimes it is not. Some personas may act in multiple ways, particularly within the service provider group: a persona representing someone running a TRE service that also hosts important datasets will, at different times, act as both TRE operator and data provider.

 | Persona	| Key Motivation	| Key Concern	| Actor | 
 |--- |--- |--- |--- |  
 | Grace Opedemi, member of the public | I want to understand how best use is being made of public sector research investments.  | Keeping my data safe from unauthorised, unethical or other “bad” uses. | Public | 
 | Peter Shaw, data custodian	| I want to share and link my data with others.	| Safety! (Don’t break the law!) Poor data quality (terminology, linkage)	| Data Custodian | 
 | Pritesh Navdra, techie data scientist	| I want to keep on the leading edge of data science, while doing some good! | 	Poor data quality (terminology, linkage); poor, ”old” tooling. | 	Researcher | 
 | Rachel Wakefield, researcher entering socio-economic research | 	I want to create more impactful research through greater access to linked data.	 | Ease of access to restricted data (skills, quality, linkage). | Researcher | 
 | Sarah Greenshaw, university public health research PI | I want to grow the research power and outward recognition of my group.  | Competition from elsewhere, being left behind. | Researcher | 
 | Jeremy Foster, ed-tech business product manager | 	I want to generate ROI through accessing and sharing sensitive data.	 | Ease of access to restricted data (skills, quality).	 | Researcher | 
 | Gill King, information governance professional | 	I want to be seen as empowering research instead of as a barrier to it.	 | Lack of standardisation, lack of automation, inefficient processes. | 	Information Governance | 
 | Helen Chow, TRE service owner	 | I want to be able to demonstrate the value of my TRE. | 	Sustainability! Maintaining multiple accreditations; implementing change is hard.	 | TRE Operator | 
 | Colin Iwobi, TRE admin and operator	 | I want to improve the user experience for our TRE users. | 	Supporting new software tools; slow safety approval process; interacting with frustrated users. | 	TRE Operator | 
 | Roy Bose, Federation operator | 	I want to support new and emerging analytical use-cases across the network. | 	Building & maintaining trust; keeping it simple & sustainable; making research more transparent. | 	Federation Operator | 

### Federation actors and roles

We can group the different “actors” in the last column of the table into three groups: Data
Providers, Data Consumers and Service Providers, the latter providing services that connect
the former two.
Most of these roles already exist in practice, except for Federation Operator, which, by
construction, is new.

#### _Data Providers_
Actors and roles in this group include:

- members of the Public, as ultimate providers of their data for research in the public
    benefit;
- Data Controllers, responsible for guarding access to public data, complying with data
    protection law and ethical guidance, and accountable to the public for the uses of
    their data;
- Data Custodians act as intermediaries between Data Controllers and Researchers.
    Data Custodians are the ones who provide sensitive data for research projects.

#### _Data Consumers_
Actors and roles in this group include:

- academic Researchers, looking for access to sensitive data to address particular
    research questions. Their requirements may be for linked datasets, or large datasets,
    or they may need significant computational analysis power or sophisticated software
    to carry out their research;
- commercial Researchers, looking for access to sensitive data to develop or test new
    products or services. Commercial researchers have different motivations to academic
    researchers but in terms of their interaction with the SDRI Federation we can treat
    them as Researchers.

#### _Service Providers_
Actors and roles in this group are more diverse than the other two and include the following:

- Information Governance (IG) professionals act as intermediaries between Data
    Providers and Data Consumers, ensuring all necessary ethical, data protection and
    legal approvals are in place for a research project to proceed. They also act as brokers
    between these two groups and the TRE and other technical service operators;
- Data Managers are responsible for providing the technical means to disseminate
    datasets approved by data controllers for release to IG for onwards sharing to data
    consumers. They are accountable to their data controllers (or data custodians) for the
    security and integrity of these technical dissemination mechanisms. In practical terms,
    data managers usually operate within TREs to provide research-ready data;
- Indexers and Linkers provide services to join different datasets together, particularly
    individual-level datasets that need to be joined using individual-level keys. These roles
    may be a subset of IG; certainly they are accountable to IG and to data controllers;
- TRE Operators are responsible for the running of a given TRE under its particular IG
    regime. This responsibility extends to all security controls required by IG;
- Federation Operators are responsible for running the technical services that connect
    TREs and data services together to form the federation. This responsibility extends to
    all the security controls required by the overall federation IG.


### Other stakeholders

There are a small number of roles who don’t interact directly with the federation but have a
stake in its outcomes, including:

- Funders (F), responsible for seeing overall return on investment in the federation
    infrastructure.



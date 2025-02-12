# DARE UK Federated Architecture Blueprint - Part 2 (Strategic Case)

## 4. A federation blueprint

In the rest of this blueprint we describe a UK-wide federation of sensitive data research infrastructure—
the SDRI Federation, or simply “the Federation”—built on common standards, with a small number of
registry and coordination services, designed to support a wide, rich ecosystem of TREs and other services.
The Federation is designed to be trustworthy, with a common set of low-level security protocols and
standards for secure data exchange, on top of which is built a rich set of application protocols and
standards to support different analytical use-cases—federated analytics, data pooling, federated machine
learning or something else. It starts from where we are—an existing ecosystem of largely independent
TREs—and builds on the ideas of federation touched on in the 2020 Health Data Research Alliance Green
Paper on TREs [6] and expanded in a companion paper from 2021 [7].

The low-level protocols and standards would define, at a purely technical level, what it means to join the
Federation—chapter one of its “rulebook”, if you will. Other rules of engagement should, in time, come to
supplement the technical—should participants require certain levels of formal accreditation before they
can join the Federation, for instance? Development of the Federation rulebook beyond the purely
technical is fundamentally a question of governance and we only touch on it here where it has a direct
bearing on the technical blueprint. How the Federation should be managed and run are decisions to be
taken by the broadest stakeholder community.

The organisation of the Federation could be designed in a number of ways. A key requirement is that the
Federation organisation and overseeing authority, any registry services and the low-level data exchange
protocols must be designed to ensure that all members of the Federation can trust one another and that,
once a Participant has joined, they enjoy the same levels of trust as all other Participants. This is our
definition of _trustworthy_. Note that this statement applies to _service Participants_ in the Federation, not to
researchers or projects or access to sensitive datasets. Governance for approving projects, encapsulating
data and researchers in authorised contexts, requires the same rigour in approval and access management
as it does today. The organisation of the Federation is a new concept, not a replacement for existing data
governance approaches.

### 4.1. Scope

In the following chapters we divide the SDRI Federation into three layers and consider each in turn. Each
layer underpins each subsequent one.

1. Infrastructure. The lowest level we discuss, infrastructure considers the services and functionality
    necessary to realise the Federation, rather than network hardware or any particular technology.
2. Data. The infrastructure layer can exist perfectly well without data but would be uninteresting. The
    mechanisms by which data are discovered, linked and made accessible are considered within the data
    layer.
3. Organisational. The highest level considered here, we use “organisation” to refer to oversight of the
    Federation infrastructure, its operational model and the definition of the “rulebook” for service
    onboarding, technical standards and change management.

Most of the focus of this blueprint is on the infrastructure layer. Some discussion of data standards and
technical governance is essential to set the infrastructure in context, but detailed treatments of these two
topics are out of scope of this document.


### 4.2. Design principles

DARE UK’s approach to the design and build of a federated network for research with sensitive data
follows a number of principles, closely aligned with the SATRE principles.

1. Public trust first, last and always. The strongest design voice should come from the “public
    persona”. (SATRE: Maintaining public trust.)
2. No TRE, no data. Reinforcing a recommendation from the Goldacre Review [33], require that any
    and all analysis of sensitive data take place within a TRE, and design accordingly. (SATRE:
    Maintaining public trust.)
3. Start from where we are. Much of the service ecosystem already exists. Our blueprint must arise
    through co-design with existing and emerging practitioners.
4. Five Safes are better than one. Secure infrastructure is only one aspect of a TRE. Adopt the Five
    Safes framework [34] as a guiding principle. Processes and governance are as important as
    infrastructure, and infrastructure choices should reflect this. (SATRE: Maintaining public trust.)
5. Separation of concerns. Different system actors have very different “security clearances”. Their
    interactions should be segregated from one another as far as possible.
6. An open-standards-based ecosystem. We seek a rich ecosystem of varied services interoperating
    through agreed standards. (SATRE: Standardisation.)
7. Be as FAIR as possible. Findability, accessibility, interoperability and reusability are excellent
    qualities to maintain even in a sensitive data environment [37]. (SATRE: Usability.)
8. The “IETF principle” [38]: rough consensus and running code over rigid specifications and
    monolithic stacks. Nucleate advances in small groups and grow outwards.
9. Open source first. Seek as often as possible to avoid proprietary lock-in. Strictly, the scope of this
    principle is that of the networked components defining the federation core. Beyond this core
    scope, “open standards” (principle 6) is the better arbiter. (SATRE: Standardisation.)
10. Low barriers. Strive to reduce barriers for researchers and for data providers. (SATRE: Usability.)
11. Observability. Human initiated and automated processes resulting in change within the TRE
    network should be observable. (SATRE: Observability.)


## 6. References

[1] DARE UK (2023); _UK Sensitive Data Research Infrastructure: A Landscape Review_ ; Zenodo;
https://doi.org/10.5281/zenodo..
[2] DARE UK; _Initial Phase 1 Recommendations_ ; https://dareuk.org.uk/our-work/dare-uk-phase- 1 -
recommendations/ (accessed 01/03/2023).
[3] F. Harkness, J. Blodgett, C. Rijneveld, E. Waind, M. Amugi, & F. McDonald (2022); _Building a
trustworthy national data research infrastructure: A UK-wide public dialogue_ (1. 0. 0 ); Zenodo;
https://doi.org/10.5281/zenodo.6451935 (accessed 27/06/2023).
[4] The HDR UK COALESCE Consortium; _Undervaccination and severe COVID-19 outcomes: meta-
analysis of national cohort studies in England, Northern Ireland, Scotland, and Wales_ ; January 15, 2024;
DOI: https://doi.org/10.1016/S0140-6736(23)02467-4; The Lancet, volume 403, issue 10426,
P554-566, February 10, 2024
[5] The Royal Society; _Science as an open enterprise_ ; The Royal Society Science Policy Centre report
02/12; https://royalsociety.org/-/media/policy/projects/sape/2012- 06 - 20 - saoe.pdf (accessed
09/03/2023).
[6] T. Hubbard, G. Reilly, S. Varma, & D. Seymour (2020); _Trusted Research Environments (TRE) Green
Paper_ (2. 0 .); Zenodo; https://doi.org/10.5281/zenodo.4594704 (accessed 10/05/2023).
[7] UK Health Data Research Alliance, & NHSX (2021); _Building Trusted Research Environments –
Principles and Best Practices; Towards TRE ecosystems (1. 0 )_ ; Zenodo;
https://doi.org/10.5281/zenodo.5767586 (accessed 10/05/2023).
[8] T. Hey and A. E. Trefethen; _The UK e-Science Core Programme and the Grid_ ; Future Generation
Computer Systems, Volume 18, Issue 8, 2002; https://doi.org/10.1016/S0167-739X(02)00082- 1
[9] The WLCG Collaboration; _The World-wide LHC Computing Grid_ ; https://wlcg.web.cern.ch/ (accessed
09/03/2023).
[10] The IVOA; _The International Virtual Observatory Alliance_ ; https://ivoa.net/ (accessed 09/03/2023).
[11] ELIXIR; _A distributed infrastructure for life science information_ ; https://elixir-europe.org/ (accessed
09/03/2023).
[12] BBMRI-ERIC; _A European research infrastructure for biobanking_ ; https://www.bbmri-eric.eu/
(accessed 09/03/2023).
[13] ESFRI; _The European Strategic Forum on Research Infrastructures_ ; https://www.esfri.eu/ (accessed
09/03/2023).
[14] CESSDA; _The Consortium of European Social Science Data Archives_ ; https://www.cessda.eu/
(accessed 09/03/2023).
[15] ESS-ERIC; _The European Social Survey_ ; https://www.europeansocialsurvey.org/ (accessed
09/03/2023).
[16] NordForsk; _A vision of a Nordic secure digital infrastructure for health data: The Nordic Commons_ ; ISSN
1504 - 8640 (2019); [http://norden.diva-portal.org/smash/get/diva2:1376735/FULLTEXT01.pdf](http://norden.diva-portal.org/smash/get/diva2:1376735/FULLTEXT01.pdf)
(accessed 10/05/2023).
[17] NIIS; _X-Road Architecture_ ; https://x-road.global/architecture (accessed 02/03/2023).
[18] NIIS; _The Nordic Institute for Interoperability Solutions_ ; https://www.niis.org/ (accessed 02/03/2023).
[19] Digital Nations; https://en.wikipedia.org/wiki/Digital_Nations (accessed 0 7 /0 8 /202 4 ).
[20] GAIA-X; _A Federated Secure Data Infrastructure_ ; https://gaia-x.eu/ (accessed 09/03/2023).
[21] GAIA-X Technical Committee; _Gaia-X Architecture Document, v 22.10_ ; 2022; https://docs.gaia-
x.eu/technical-committee/architecture-document/22.10/ (accessed 02/03/2023).


##### V 2.2 FINAL

**FOR CONSULTATION & COMMENT**

[22] International Data Spaces Association; _IDS Reference Architecture Model_ , v4., April 2022;
https://docs.internationaldataspaces.org/ids-knowledgebase/v/ids-ram-4/.
[23] European Commission; _Simpl: cloud-to-edge federations and data spaces made simple_ ; news article,
24/02/2023; https://digital-strategy.ec.europa.eu/en/news/simpl-cloud-edge-federations-and-
data-spaces-made-simple (accessed 02/03/2023).
[24] European Commission; _A European Strategy for data_ ; policy paper; https://digital-
strategy.ec.europa.eu/en/policies/strategy-data (accessed 09/03/2023).
[25] C. Cole, et al; _SATRE: Standardised Architecture for Trusted Research Environments_. Zenodo, Oct. 30,

2023. Doi: 10.5281/zenodo.10055345.
[26] SATRE: Standard Architecture for Trusted Research Environments, _specification v 1.0.0_ ,
https://satre-specification.readthedocs.io/en/v1.0.0/index.html
[27] T. Giles, et al. _TRE-FX: Delivering a Federated Network of Trusted Research Environments to Enable Safe
Data Analytics_. Zenodo, 30 Oct. 2023, doi:10.5281/zenodo.10055354.
[28] OpenSAFELY; _The OpenSAFELY Secure Analytics Platform_ ; https://www.opensafely.org/ (accessed
23/03/2023)
[29] C. Orton, et al. _TELEPORT: Connecting Researchers to Big Data at Light Speed_. Zenodo, 30 Oct. 2023,
doi:10.5281/zenodo.10055358.
[30] J. Smith, et al. _SACRO: Semi-automated Checking of Research Outputs_. Zenodo, 6 Nov. 2023,
doi:10.5281/zenodo.10055365.
[31] A. Casey, et al. _SARA: Semi-automated Risk Assessment of Data Provenance and Clinical Free-text in
Trusted Research Environments_. Zenodo, 30 Oct. 2023, doi:10.5281/zenodo.10055362.
[32] DARE UK and The PSC, _Scientific use-cases for cross-domain sensitive data research_ , March 2024. _In
preparation_.
[33] B. Goldacre et al; _Better, broader, safer: using health data for research and analysis_ ; 7 April 2022;
https://www.gov.uk/government/publications/better-broader-safer-using-health-data-for-
research-and-analysis (accessed 02/03/2023).
[34] F. Ritchie (2016); _Five Safes: designing data access for research_ ; 10.13140/RG.2.1.3661.1604.
[35] UK Government; _Data Protection Act 2018_ ;
https://www.legislation.gov.uk/ukpga/2018/12/contents/enacted (accessed 09/03/2023).
[36] UK Government; _The UK General Data Protection Regulation_ ;
https://www.legislation.gov.uk/eur/2016/679/contents (accessed 09/03/2023).
[37] M. Wilkinson, M. Dumontier, I. Aalbersberg et al; _The FAIR Guiding Principles for scientific data
management and stewardship_ ; Sci Data 3, 160018 (2016); https://doi.org/10.1038/sdata.2016.18.
[38] IETF; _The Internet Engineering Taskforce_ ; https://www.ietf.org/ (accessed 20/03/2023).


##### V 2.2 FINAL

**FOR CONSULTATION & COMMENT**

## A A comparison of contemporary federated data architectures

Annex III of the _Recommendation Report_ for the EU Smart Middleware Platform (SiMPl) [23] compares the
concepts defined in the SiMPl architecture with those defined in the GAIA-X framework [21]. The table
below extends this idea to include the concepts defined in this document and the equivalents from both
the IDSA reference architecture model (version 3.) [22] and the X-Road architecture [17].

```
DARE UK GAIA-X SiMPl IDSA X-Road Notes
Participant Participant Organisation that
deploys an SMP
Agent
```
```
Core Participant
(also Intermediary)
```
```
Organization
```
```
Federation
Services
```
```
Federator Data Space
governance
```
```
Intermediaries,
especially Clearing
House, Identity
Provider and
Vocabularly
Provider
```
```
Central
Services &
Trust Services
```
```
Security
Server
```
```
Sovereign
Data
Exchange
```
```
SMP Agent IDS Connector Security
Server
```
```
The GAIA-X mapping
is imprecise. It factors
out a number of
functions that are
encapsulated in the
other four models.
TRE Consumer
or Service
instance
```
```
Composite of
Application
Provider and
Infrastructure
Provider
```
```
Service Provider;
Composite of Data
Consumer and Data
Provider
```
```
Service
Consumer
Information
System
```
```
A DARE UK TRE has
no direct equivalent
but is a specialised
example of a generic
data consuming
service.
Data
Provider /
Data
Custodian
```
```
Provider Data Provider Data Provider Service
Provider
Information
System
Researcher
(User)
```
```
End User End user Data User Data
Requestor
Discovery
Service
```
```
Catalogue Data catalogue Broker Service
Provider
```
```
Service
Provider
Information
System
```
```
A catalogue or
discovery service in
X-Road would be a
specialised kind of
Information System
hosted by a Service
Provider.
Index
Service;
Software
Service
```
```
Consumer
or Service
instance
```
```
Composite of
Application
Provider and
Infrastructure
Provider
```
```
Service Provider Service
Provider
Information
System
```
```
All DARE UK services
can be modelled the
same way in terms of
their interaction with
the federation
structure.
```

##### V 2.2 FINAL

**FOR CONSULTATION & COMMENT**


##### V 2.2 FINAL

**FOR CONSULTATION & COMMENT**

## B Scenario analysis of the federated landscape

The 2023 DARE UK survey and review of sensitive data research infrastructure [1] reveals a fragmented
and rapidly changing landscape of data and service providers. The changeability is driven in part by a
desire to build on the research and data sharing successes of the UK’s response to covid-19, but what
form the landscape will finally take is hard to predict. A federated network of trusted research
environments could look quite different under different future scenarios, depending on a certain number
of external policy drivers. In this section we try to explore some possible futures using a “scenario
thinking” approach.

Initial thinking pulls up two principal external “landscape drivers”: the number of TREs and their
capabilities; and the mobility of data.

1. The number and capabilities of TREs. The Goldacre review [33] argues for a small number of
    highly capable TREs; the current landscape has a fairly large number of TREs. Some of these are
    large and capable, supporting national and regional research projects; many more are smaller and
    support smaller university groups, individual clinical trials and so on. Assuming that there is one
    overall budget for TRE provision across the UK, larger numbers could mean each has limited
    capability, and vice versa.
2. Mobility of data. Governance concerns and consequential risk management approaches currently
    keep data close to home, tightly controlled with a data controller or data custodian. The increasing
    volumes of certain kinds of data (e.g., medical images, genomic data) also make it increasingly
    difficult to move them around. To mitigate the first of these concerns UK Government has
    consulted on possible changes to the Data Protection Act 2018 [35] and the UK GDPR [36],
    perhaps creating governance counter-pressures towards more mobile data. Note that this doesn’t
    address the “gravity” around very large datasets (see below).

### B.1 Four quadrants

Using these two drivers we can sketch four possible future scenarios in which the DARE UK federation
might look slightly different:

- Low numbers of TREs and low data mobility;
- Low numbers of TREs and high data mobility;
- High numbers of TREs and low data mobility;
- High numbers of TREs and high data mobility.

#### B.1.1 Low numbers of TREs and low data mobility

Low data mobility for governance reasons may be relaxed in the future but it’s unlikely the same will be
true for very large datasets (high-resolution Earth observation, medical imaging, genomic data etc.). Partly
because of their size, but also often their complexity, working with datasets of this nature will typically
require specialised tooling, high-performance computing capabilities, dedicated GPU or AI hardware, or
all of these, and these capabilities typically grow “around” the datasets.

Low mobility for governance reasons leads to a similar scenario where TREs grow “around” the sensitive
datasets (this is typically what is meant by “data gravity”). Such a TRE can accumulate expertise in
working with the datasets in question, but in this scenario linkage between datasets becomes difficult. If


##### V 2.2 FINAL

**FOR CONSULTATION & COMMENT**

legal agreements for data linkage are the bottleneck for sharing data, then the incentives on TREs
towards technical interoperability are that much weaker: if data move infrequently then current ad hoc
methods of data movement may suffice.

#### B.1.2 Low numbers of TREs and high data mobility

If the gravity of large, complex datasets means a low number of highly capable TREs grow up around
them, then these TREs are also available to process smaller, neater, more mobile datasets from elsewhere.
If an easing of governance pressures makes these smaller datasets more mobile this could in turn lead to
an increase in demand on the small number of TREs. Provided these TREs can build the capacity to
manage this increased demand this should not cause any problems.

High mobility of datasets should, in principle, make linkage between them easier. Agreements between
data controllers on linkage spines, indexing etc. will be (legally) easier to come to (this almost defines what
we mean by “easing of governance pressures” on data mobility) and the necessary data and tools can be
sent to linkage teams within the TREs. This would require TREs to acquire additional capabilities in data
linkage, and perhaps knowledge of different kinds of data, on top of the expertise they will have built
around the datasets they curate themselves.

#### B.1.3 High numbers of TREs and low data mobility

The volume and complexity argument suggests that a small number of highly capable TREs are likely to
exist in all scenarios. But, if moving smaller, neater datasets remains difficult for governance or risk
management reasons, this scenario pictures a large number of additional small-scale (even “pop-up”) TREs
being created around individual datasets (e.g., a clinical trial dataset) or for individual research
organisations (e.g., a university or university department). In this scenario linkage remains difficult and the
data landscape is even more fragmented than in the low-low scenario. If data sharing is difficult for
governance reasons then there are few incentives for these TREs to maintain any level of technical
interoperability or adhere strictly to any particular standard if doing so might constrain the TRE’s core
research purpose. The risk of technical drift between TRE environments is high with a consequent
dissipation of expertise and increased friction^7.

High numbers of TREs in a landscape of low data mobility is probably a scenario to be avoided if possible.

#### B.1.4 High numbers of TREs and high data mobility

High numbers of TREs in a scenario of high data mobility is a very different prospect to the high-low
picture. In this scenario, the relative ease of data sharing provides a real incentive for small-scale TREs to
stick to interoperability standards—play the game and data linkage becomes much easier for your
researchers. While the big, highly capable TREs are ever-present this scenario envisages a true ecosystem
of TREs of many scales being able to exchange data relatively freely. Open standards are a key enabler for

(^7) Imagine an extreme version of this scenario where hundreds of research groups end up with their own TREs, each
of which has been built around the groups’ “traditional” bespoke analytics environments and domain-specific
languages. The blockers to research are never technical interoperability with the neighbouring lab’s TRE and are
always the slow and painful negotiation over data sharing – so why spend time on technical interoperability when
you need to invest more in data negotiation?


##### V 2.2 FINAL

**FOR CONSULTATION & COMMENT**

this scenario, along with open software recipes to enable many groups to create their own readily
interoperable TREs.

The biggest challenge in this scenario is governance, closely followed by a set of technical controls that
span the whole ecosystem and maintain the necessary security posture across multiple organisations,
data controllers and researchers.

### B.2 Observations

None of these scenarios expects to see a complete de-fragmentation of the distributed landscape. While
some consolidation is desirable (e.g., to avoid the high-low scenario) it seems optimistic to expect a
reduction in the numbers of centres of data gravity to one over the next 5-10 years. Thus we should
expect that the federation of distributed data sets and computational services to remain a key challenge
within the UK research landscape. This observation underlines the architectural approaches described in
the blueprint.



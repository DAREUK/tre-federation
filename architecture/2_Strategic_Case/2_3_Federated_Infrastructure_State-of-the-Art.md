# DARE UK Federated Architecture Blueprint - Part 2 (Strategic Case)

## 3. Federated infrastructure: the state of the art

Infrastructure federations have been a staple of the UK research landscape since the early 2000s and the
drivers of the UK e-Science Core Programme [8]. The World-wide LHC Compute Grid (WLCG [9]) and the
International Virtual Observatory Alliance (IVOA [10]) adopted techniques for managing “virtual
organisations” developed in those early years and are now global science federations managing petabytes
of natural science data.

Closer to the concept of sensitive data but also seeing roots in the e-science development of “Grid
computing” (a forerunner of cloud computing) are more than 15 European research infrastructures
spanning health and social sciences [13]. Notable examples include ELIXIR [11], BBMRI [12], CESSDA [14]
and ESS [15]. Of these, ELIXIR operates as an international treaty organisation through its founding
partner EMBL and the other three are incorporated as European Research Infrastructure Consortia
(ERICs).

International ambition on the sharing and pooling of routine national “register” data for research is well
illustrated in the Nordic Commons model proposed in Scandinavia [16]. With their strong traditions of
good national record-keeping, and bound by the GDPR, the Nordic countries offer a blueprint for
federated data sharing that is well worth studying.

UK research is thus not alone in seeking a federated solution to distributed resources in an environment
that requires very high levels of trust. There are a number of current and emerging technology solutions
which seek to build (or have built) federated environments between independent organisations with high
levels of assurance and trustworthiness. All follow the same pattern of inter-service standards and many
make use of a managing agency.

X-Road [17], managed by the Nordic Institute for Interoperability Solutions [18], is the open-source
platform developed by the government of Estonia from the 1990s onwards to underpin the delivery of
government services in the new nation that emerged from the Soviet Union. X-Road provides a secure
infrastructure for document exchange between government agencies, police, health services and citizens.
While X-Road is open source it remains the backbone of digital government in Estonia, Finland, Iceland
and other nations and so its core development is managed by NIIS. Estonia, along with the UK, was one of
the founders of the “Digital Five” advanced digital governments, now the “Digital Nations” [19].

GAIA-X [20], initiated in 2019 by the French and German economics ministries, is seeking to define a
reference architecture and model implementations of a secure, federated infrastructure [21]. It shares
many similar concepts with X-Road and with both IDSA and SiMPl (q.q.v.). GAIA-X’s designs and software
implementations are open source but managed by the GAIA-X aisbl (a Belgium non-profit incorporation)
which is open to join but requires a subscription fee. GAIA-X describe a number of “lighthouse projects”,
federated infrastructures in operation using their architecture in sectors spanning agriculture, automotive
and tourism.

The International Data Spaces Association (IDSA) is “a cross-industry, transnational coalition of more than
140 leading companies and research organizations” that has been developing concepts and standards for
“data spaces” since 2016. Data spaces are federations of organisations created to enable the secure
sharing of data between them, with a strong focus on contractual arrangements for commercial use.
Version 4 of the IDSA Reference Architecture Model (“IDS-RAM”) is publicly available [22].

The most recent work in this space is perhaps the launch of an invitation to tender for the European
Smart Middle Platform (variously SiMPl or SMP) [23]. SiMPl is designed to create an open standards-
based approach to cloud interoperability and provisioning (“cloud-to-edge federation”) and to underpin
the European Data Strategy [24] and the further development of data spaces. The published timetable for
SiMPl suggests a minimal viable product should be released “at the end of 2024”.

As noted, the proposed SiMPl architecture shares many common features with X-Road, IDS-RAM and
GAIA-X; these four initiatives do collaborate at various levels. Appendix A provides a comparison of these
initiatives, alongside similar concepts from the proposed SDRI Federation architecture.

### 3.1. TRE federation proofs-of-concept: the DARE UK driver projects

During 2023 the DARE UK programme funded a portfolio of driver projects to explore potential
technologies in this space, three of which in particular have a strong bearing on topics covered later in
this blueprint. For an overview of these projects,
see the [DARE UK website](https://dareuk.org.uk/our-work/phase-1-driver-projects/).

**SATRE** [25] compared openly available UK TREs hosting health, manufacturing, commercial, science and
humanities data and aligned them into a standardised TRE reference architecture. SATRE’s scope was
strongly intra-TRE, looking to answer the question: how do we specify what a TRE should be at a
technical level? Answers are recorded in the project’s principal output, the “SATRE Specification” [26].

**TRE-FX** [27] demonstrated the use of existing technologies from ELIXIR and HDR-UK to support
federated analytics across a network of TREs and data providers. Federated analytics—sending the
analysis scripts or programs to the dataset, where the dataset is split across several physical locations—is
one of a small number of key application types that would run on top of the core federation. TRE-FX
applied the “job submission” approach to federated analytics also seen in OpenSAFELY [28] and
numerous other solutions: request that a TRE download and run an analysis script developed “outside”
the environment. TRE-FX developed a standard way to submit jobs that is “5 safes” compliant, and
worked with partners from [Bitfount](https://www.bitfount.com/) and 
[DataSHIELD](https://datashield.org/) to integrate these standards into their product
suites.

**TELEPORT** [29] demonstrated how to offer a single query interface to users of a TRE that spans multiple
remote datasets – a “single pane of glass” approach whereby a researcher can log into one TRE and see
their approved project data from the other TREs as though it were all held within the same environment.
Potentially data can be linked across the different TREs if an indexing service has provided the different
TREs with the same pseudo-identifiers corresponding to the same individual. TELEPORT combined this
data federation approach with the use of “pop-up TREs” or “TREs-within-TREs”, project-specific instances
of TREs created virtually within a larger TRE infrastructure. By synchronising these “pop-up TREs” with
overlapping governance “wrappers” defined by the TREs contributing data to the project in question,
TELEPORT showed how federated querying can be made just as safe and secure as accessing data in a
single location.

Two additional projects developed enhanced tooling for assessing disclosure risk in datasets at the
beginning and the end of the research process.

**SACRO** [30] sought to reduce the operating costs of TREs and the time taken to check and release
research results by, among other things: producing a consolidated framework with a rigorous statistical
basis that provides guidance for TREs to agree consistent, standard processes to assist in quality
assurance; and, designing and implementing a semi-automated system for checks on common research
outputs, with increasing levels of support for other types of output, such as AI (artificial intelligence).

**SARA** [31] focused on semi-automated tools to improve two areas of data risk assessment and
monitoring: data provenance, describing the origins, actions performed and agents involved in data
creation and transformation; and privacy assessment, minimising the risk of identifiable information in
clinical free-text records (for example, GP letters and discharge summaries).

The five driver projects mapped well onto version 1._x_ of this blueprint but highlighted a missing
distinction between “direct query” and “indirect query” in approaches to federated analytics, and a
missing synchronisation interface for the pop-up TRE model.

Direct query—the TELEPORT approach—encapsulates everything a remote TRE might need to run the
query across its hosted data and return a result. This single pane of glass is seen in a number of current
products and is generalised in the polystore database concept.

Indirect query—the TRE-FX approach—uses a job submission model of query where the actual query
payload must be retrieved from a software repository outside any of the participating TREs. As noted
above, this approach is also used in other models.

TELEPORT’s approach to pop-up TREs relied on a “keep-alive” synchronisation channel between the two
participating TREs. This channel provides continual monitoring of the running state of a multi-TRE (and
hence multi-governance) project against a “known good”, mutually approved state. Deviations from the
approved state, or failure of the keep-alive, can result in researcher access to the pop-up project
environment being revoked—or in the entire virtual pop-up TRE being “rapidly deprovisioned”.

While this blueprint is concerned principally with connections _between_ TREs, and the SATRE specification
[26] is concerned with what it is to be a TRE, the two naturally touch. This blueprint meets the SATRE
specification where it should. A detailed mapping between the Federation requirements and SATRE
specification statements can be found in the _Master Requirements Table_, Appendix A of Part 3 (Use Cases).

This new version of the federated architecture blueprint models these developments much more
accurately than did version 1.


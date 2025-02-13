> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 2 Strategic Case
## Introduction


>“The UK Research and Innovation DARE UK (Data and Analytics Research Environments UK)
programme has been established to design and deliver a coordinated and trustworthy national
data research infrastructure to support research at scale for public good. DARE UK is a cross-
domain programme—its scope covers all types of sensitive data, including data about education,
health, the environment and much more.”

 - DARE UK Phase 1 report: Paving the way for a coordinated national infrastructure for sensitive data research

The DARE UK programme is built on the concept of a UK sensitive data research landscape which is
fundamentally distributed, both in its sources of available data and in the analytical services able to
process them [1]. While the numbers and locations of data sources and services within this landscape will
ebb and flow (see Appendix B _Scenario Analysis_ ) there is no likely future scenario which brings all data and
all compute services together in one location. To enable researchers to work with data linked from
multiple sources, a federated digital research infrastructure is needed.

### DARE UK Phase 1 recommendations

There are ten key recommendations from the DARE UK Phase 1 report [2] that shape our approach to a
federated architecture for trusted research environments (TREs) across the UK, and two from the DARE
UK 2022 public dialogue [3].

**Data and discovery**

From [2]:

1. Enhance the data lifecycle to support effective cross-domain sensitive data research.
2. Explore the implications of new data types on approaches to making these data available for
    research.
3. Develop guidelines on privacy enhancing technologies (PETs) for use by TREs.
4. Establish a UKRI-wide metadata standard working group.
5. Leverage existing Digital Object Identifier (DOI) minting services to provide persistent identifiers
    for all UKRI discoverable assets at UKRI-wide and council levels.

**Core federation services**

From [2]:

1. Develop reference architecture(s) for TREs.
2. Assemble an API (application programming interface) library to support core federation services.
3. Run a competitive call for driver projects to utilise the new infrastructure services and validate
    that they are fit for purpose.
4. Establish an approach to business continuity and disaster recovery.

**Capability and capacity**

From [2]:

4. Use automation to ensure data research infrastructure services are reliably secure, auditable and
    reproducible.

**Public engagement and dialogue**

From [3]:

4. The processes and systems supporting data research across the UK should be unified in their
    approaches where possible.
5. Where feasible, processes enabling access to sensitive data for research should be standardised
    and centralised.

Of these 12 the strongest influence on this blueprint comes from the public dialogue Recommendations 4
and 5, the public view that trustworthiness will derive in no small part from standardised, centralised
processes and systems, where feasible. These concepts sit at the heart of our proposed approach of a
common federation for sensitive data research infrastructure.


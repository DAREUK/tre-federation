> DARE UK Federated Architecture Blueprint  v2.2
----

# Appendix C. Scenario analysis of the federated landscape

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

## Four quadrants

Using these two drivers we can sketch four possible future scenarios in which the DARE UK federation
might look slightly different:

- Low numbers of TREs and low data mobility;
- Low numbers of TREs and high data mobility;
- High numbers of TREs and low data mobility;
- High numbers of TREs and high data mobility.

### Low numbers of TREs and low data mobility

Low data mobility for governance reasons may be relaxed in the future but it’s unlikely the same will be
true for very large datasets (high-resolution Earth observation, medical imaging, genomic data etc.). Partly
because of their size, but also often their complexity, working with datasets of this nature will typically
require specialised tooling, high-performance computing capabilities, dedicated GPU or AI hardware, or
all of these, and these capabilities typically grow “around” the datasets.

Low mobility for governance reasons leads to a similar scenario where TREs grow “around” the sensitive
datasets (this is typically what is meant by “data gravity”). Such a TRE can accumulate expertise in
working with the datasets in question, but in this scenario linkage between datasets becomes difficult. If
legal agreements for data linkage are the bottleneck for sharing data, then the incentives on TREs
towards technical interoperability are that much weaker: if data move infrequently then current ad hoc
methods of data movement may suffice.

### Low numbers of TREs and high data mobility

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

### High numbers of TREs and low data mobility

The volume and complexity argument suggests that a small number of highly capable TREs are likely to
exist in all scenarios. But, if moving smaller, neater datasets remains difficult for governance or risk
management reasons, this scenario pictures a large number of additional small-scale (even “pop-up”) TREs
being created around individual datasets (e.g., a clinical trial dataset) or for individual research
organisations (e.g., a university or university department). In this scenario linkage remains difficult and the
data landscape is even more fragmented than in the low-low scenario. If data sharing is difficult for
governance reasons then there are few incentives for these TREs to maintain any level of technical
interoperability or adhere strictly to any particular standard if doing so might constrain the TRE’s core
research purpose. The risk of technical drift between TRE environments is high with a consequent
dissipation of expertise and increased friction.

(Imagine an extreme version of this scenario where hundreds of research groups end up with their own TREs, each
of which has been built around the groups’ “traditional” bespoke analytics environments and domain-specific
languages. The blockers to research are never technical interoperability with the neighbouring lab’s TRE and are
always the slow and painful negotiation over data sharing – so why spend time on technical interoperability when
you need to invest more in data negotiation?)

High numbers of TREs in a landscape of low data mobility is probably a scenario to be avoided if possible.

### High numbers of TREs and high data mobility

High numbers of TREs in a scenario of high data mobility is a very different prospect to the high-low
picture. In this scenario, the relative ease of data sharing provides a real incentive for small-scale TREs to
stick to interoperability standards—play the game and data linkage becomes much easier for your
researchers. While the big, highly capable TREs are ever-present this scenario envisages a true ecosystem
of TREs of many scales being able to exchange data relatively freely. Open standards are a key enabler for
this scenario, along with open software recipes to enable many groups to create their own readily
interoperable TREs.

The biggest challenge in this scenario is governance, closely followed by a set of technical controls that
span the whole ecosystem and maintain the necessary security posture across multiple organisations,
data controllers and researchers.

## Observations

None of these scenarios expects to see a complete de-fragmentation of the distributed landscape. While
some consolidation is desirable (e.g., to avoid the high-low scenario) it seems optimistic to expect a
reduction in the numbers of centres of data gravity to one over the next 5-10 years. Thus we should
expect that the federation of distributed data sets and computational services to remain a key challenge
within the UK research landscape. This observation underlines the architectural approaches described in
the blueprint.





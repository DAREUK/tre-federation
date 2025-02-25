> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 5 Federated architecture: data layer
## 5.4 Data accessibility

Easier and more streamlined access to sensitive data is the raison d’être of the DARE UK programme and of the Federation described here. We adhere strongly to the principle of “no TRE, no data”—data access in a secure environment over data distribution to researchers’ local systems—which offers a far greater degree of data security but does place some new restrictions on data access.

One particular consideration is “data understanding”. Most models of analysis for any datasets bar the very smallest introduce an “understanding” or “exploratory” step between discovery and full-blown production analysis. A good illustration of this is the [CRISP-DM process](https://www.datascience-pm.com/crisp-dm-2/), a widely-used industry standard dating back to the 1990s. It introduces both “business [domain] understanding” and “data understanding” as steps before “data preparation” and “modelling” but crucially emphasises the iterative nature of the process. These steps are cyclic, not serial.

The data access model of TREs introduces a hard serialisation into the end-to-end data research process, especially where information governance requires a researcher to request in advance of their project being approved only the data elements they will need to answer their particular research question. Without an initial exploratory phase that request can be difficult to get right.

A proper understanding of the “linkability” of two or more datasets can also be difficult to achieve without some level of access to both datasets in advance (see also Section 5.5 Data interoperability below). Full data harmonisation of this nature (especially across our broadest possible definitions of sensitive data) is out of scope for this architecture. However, the restrictions introduced by the “no TRE, no data” principle are worthy of consideration: are there changes at architectural level that could facilitate a data harmonisation step?

OpenSAFELY [[28]](../References.md#ref-28) have shown that, for certain kinds of well-structured data, the majority of the algorithmic development and data exploration work can be done outside a TRE, on “fake data” that match the sensitive data schema and terminology sets but which contain random values. OpenSAFELY couples this development stage with an indirect query job submission model to deploy a researcher’s analysis code into the TRE without needing to grant them as an individual any kind of secure access. The “fake data” development model could be extended to other data sources even if the actual analysis step were to follow the “traditional” TRE model of secure access over remote desktop.

Enabling this degree of data exploration (or at least schema exploration) could be supported by additional Discovery Services sitting on the edge of the Federation.

----

| [< Data findability](5_3_Data_Findability.md) | - | [Data interoperability >](5_5_Data_Interoperability.md) |
| ---- | ---- | ---- |




> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 5 Federated architecture: data layer
## 5.1 Classifying sensitive data

There is no generally agreed definition of “sensitive data”. Most working classifications are built around three considerations: the subject of a given dataset; the organisation responsible for custody of a given dataset; and the potential harm, to either subject or custodian organisation (or both), from unauthorised disclosure of the dataset. 

The nature of a dataset’s subject often requires a particular legal or regulatory approach to classification. In the UK, for example, data about living natural persons is covered extensively in the UK GPDR [[36]](../References.md#ref-36). A firm’s intellectual property may fall under the Copyright Designs and Patents Act [[42]](../References.md#ref-42). Where the data subject is an endangered species, its treatment may be covered by international treaty such as CITES [[43]](../References.md#ref-43). Still other subjects may require certain approaches because of cultural sensitivity .

Organisations responsible for collecting or holding potentially sensitive data typically apply their own classification criteria. As responsible custodians, the impact of unauthorised disclosure will likely fall on them, making good data classification part of good corporate risk management practice.

In the interests of manageability, organisational risk management approaches tend to aim for a handful of sensitive data classes only. UK Government (and the US Government) apply three [[44]](../References.md#ref-44) (OFFICIAL, SECRET and TOP SECRET), or four if the UK’s OFFICIAL-SENSITIVE is counted separately. The International Information System Security Certification Consortium (ISC)<sup>2</sup> defines five in its standard commercial scale [[45]](../References.md#ref-45). Work at the Alan Turing Institute has developed a five-tier classification model [[46]](../References.md#ref-46). The NHS in England has an extensive example-driven list of over a dozen but these map onto just two on the UK Government scale [[47]](../References.md#ref-47).

The principal reason for an organisation to classify sensitive data is to help it decide how to manage them. This makes it possible to divorce the “why” from the “how”: why a particular dataset has been classified as “sensitive” doesn’t matter when it comes to storing and protecting it as a sensitive dataset. This is the approach taken in the Harvard Datatags system [48].

### A seven-point scale

DARE UK aims to facilitate the combination and linkage of datasets from any and all possible sources. Linked data typically carry higher disclosure risk than their individual constituents, so some comparative scale will be useful. We recommend that datasets used within the SDRI Federation be recorded with two key pieces of information and a number from 1-6 on a “scale of harm”.

In assessing risk of harm, we assume that any unauthorised disclosure of data brings the chance of the data falling into the hands of someone in a position to cause harm to either the data subject or data custodian. Thus, we do not distinguish between data release to a small group and data release to everyone.

Datasets should be classified by:
 * Data subject (what it’s about): individuals; firms; locations; intellectual property; …
 * Data custodian (who’s responsible for sharing it);
 * “Harm”, which can mean physical, mental, emotional, economic or reputational, depending on the context.

| Category	| Harm | UK Gov	| GDPR | (ISC)2 | Turing | 
| ------------- | ---- | ------ | ---- | ------ | ------ | 
| 	| None	| Public	| Public	| Public	| Tier 0| 
| 1	| Inconvenience	| -	| -	| Proprietary	| Tier 1| 
| 2	| Distress, embarrassment, some reputational damage	| OFFICIAL	| Personal 	| Private	| Tier 2| 
| 3	| Actual harm 	| OFFICIAL-SENSITIVE	| Personal 	| Confidential	| -| 
| 4	| Serious harm	| OFFICIAL-SENSITIVE	| Special Category	| Sensitive	| Tier 3| 
| 5	| Loss of life	| SECRET	| -	| -	| Tier 4| 
| 6	| Widespread loss of life	| TOP SECRET	| -	| -	| -| 

**NB:** It must be emphasised that data classification in this manner is not a simple badge-it-and-forget affair. The sensitivity of a given dataset (whether Dataset or Data Extract) can and will change depending on the context it is in. The classifications themselves are also something of a blunt instrument: “John has asthma” and “John has HIV” are both personal health data (GDPR Special Category), but one could cause far more harm than the other if disclosed. It is far better to use this kind of classification only as a starting point and always consider the use of sensitive data within a “Five Safes” context, managing risk holistically across a number of dimensions.

----

| [< Up](../) | - | [Federation metadata >](5_2_Federation_Metadata.md) |
| ---- | ---- | ---- |



